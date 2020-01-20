export const bookApiUrl = 'http://localhost:3000/books'

export function httpGet(path) {
  return req(path)
}

export function httpPost(path, data) {
  return req(path, 'POST', data)
}

export function httpPut(path, data) {
  return req(path, 'PUT', data)
}

async function req(path, method = 'GET', data) {
  const res = await fetch(bookApiUrl + path, {
    method,
    headers: {
      'Content-Type': 'application/json'
    },
    body: data && JSON.stringify(data)
  })
  const json = await res.json()
  return { ok: res.ok, data: json }
}
