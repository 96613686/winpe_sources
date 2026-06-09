# HTTP_WRAPPER::CreateRequestQueue(void * *,ushort const *,_SECURITY_ATTRIBUTES *)

- ea: `0x180012f88`
- end: `0x180012ff7`
- name: `?CreateRequestQueue@HTTP_WRAPPER@@QEAAKPEAPEAXPEBGPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `111`
- prototype: `unsigned int(HTTP_WRAPPER *__hidden this, void **, const unsigned __int16 *, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012530`

## callees

- `0x180012f88`
- `0x180015f6c`

## import_xrefs

- `HTTPAPI!HttpCloseRequestQueue` at `0x180012fdf`
- `HTTPAPI!HttpCloseRequestQueue` at `0x180012fdf`
- `HTTPAPI!HttpCreateRequestQueue` at `0x180012fb6`
- `HTTPAPI!HttpCreateRequestQueue` at `0x180012fb6`

## pseudocode

```c
__int64 __fastcall HTTP_WRAPPER::CreateRequestQueue(
        HTTP_WRAPPER *this,
        void **RequestQueueHandle,
        const unsigned __int16 *a3,
        struct _SECURITY_ATTRIBUTES *a4)
{
  ULONG RequestQueue; // edi

  RequestQueue = HttpCreateRequestQueue((HTTPAPI_VERSION)2, a3, a4, 2u, RequestQueueHandle);
  if ( RequestQueue || (RequestQueue = HTTP_WRAPPER::SetRequestQueueState(this, *RequestQueueHandle, 2)) != 0 )
  {
    if ( *RequestQueueHandle )
    {
      HttpCloseRequestQueue(RequestQueueHandle);
      *RequestQueueHandle = 0;
    }
  }
  return RequestQueue;
}

```

## disassembly

```asm
0x180012f88  push    rbx
0x180012f8a  push    rbp
0x180012f8b  push    rsi
0x180012f8c  push    rdi
0x180012f8d  sub     rsp, 48h
0x180012f91  mov     r10, r9
0x180012f94  mov     [rsp+68h+RequestQueueHandle], rdx; RequestQueueHandle
0x180012f99  mov     r11, r8
0x180012f9c  mov     ebp, 2
0x180012fa1  mov     rbx, rdx
0x180012fa4  mov     [rsp+68h+var_38], ebp
0x180012fa8  mov     rsi, rcx
0x180012fab  mov     r9d, ebp; Flags
0x180012fae  mov     r8, r10; SecurityAttributes
0x180012fb1  mov     rdx, r11; Name
0x180012fb4  mov     ecx, ebp; Version
0x180012fb6  call    cs:__imp_HttpCreateRequestQueue
0x180012fbc  mov     edi, eax
0x180012fbe  test    eax, eax
0x180012fc0  jnz     short loc_180012FD6
0x180012fc2  mov     rdx, [rbx]
0x180012fc5  mov     r8d, ebp
0x180012fc8  mov     rcx, rsi
0x180012fcb  call    ?SetRequestQueueState@HTTP_WRAPPER@@QEAAKPEAXW4HTTP_WRAPPER_PROTOCOL_APPPOOL_STATE_REASON@@@Z; HTTP_WRAPPER::SetRequestQueueState(void *,HTTP_WRAPPER_PROTOCOL_APPPOOL_STATE_REASON)
0x180012fd0  mov     edi, eax
0x180012fd2  test    eax, eax
0x180012fd4  jz      short loc_180012FEC
0x180012fd6  cmp     qword ptr [rbx], 0
0x180012fda  jz      short loc_180012FEC
0x180012fdc  mov     rcx, rbx; RequestQueueHandle
0x180012fdf  call    cs:__imp_HttpCloseRequestQueue
0x180012fe5  mov     qword ptr [rbx], 0
0x180012fec  mov     eax, edi
0x180012fee  add     rsp, 48h
0x180012ff2  pop     rdi
0x180012ff3  pop     rsi
0x180012ff4  pop     rbp
0x180012ff5  pop     rbx
0x180012ff6  retn
```
