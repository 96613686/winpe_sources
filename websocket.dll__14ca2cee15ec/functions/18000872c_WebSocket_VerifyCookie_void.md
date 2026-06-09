# WebSocket::VerifyCookie(void)

- ea: `0x18000872c`
- end: `0x18000874d`
- name: `?VerifyCookie@WebSocket@@AEAAXXZ`
- size: `33`
- prototype: `void __fastcall(WebSocket *__hidden this)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x1800020a0`
- `0x1800020f0`
- `0x180002170`
- `0x180002200`
- `0x180002320`
- `0x1800023b0`
- `0x1800023f0`
- `0x1800024e0`
- `0x180002530`
- `0x180003cf8`

## callees

- `0x18000872c`
- `0x180009b68`

## pseudocode

```c
void __fastcall WebSocket::VerifyCookie(WebSocket *this)
{
  if ( !this || *(_DWORD *)this != 1396852055 )
    WebSocket_invalid_object_handle_fatal_error(this, 0, 1);
}

```

## disassembly

```asm
0x18000872c  sub     rsp, 28h
0x180008730  test    rcx, rcx
0x180008733  jz      short loc_18000873D
0x180008735  cmp     dword ptr [rcx], 53424557h
0x18000873b  jz      short loc_180008748
0x18000873d  xor     edx, edx
0x18000873f  lea     r8d, [rdx+1]
0x180008743  call    ?WebSocket_invalid_object_handle_fatal_error@@YAX_KKW4FATAL_FAILURE_REASON_TYPE@@@Z; WebSocket_invalid_object_handle_fatal_error(unsigned __int64,ulong,FATAL_FAILURE_REASON_TYPE)
0x180008748  add     rsp, 28h
0x18000874c  retn
```
