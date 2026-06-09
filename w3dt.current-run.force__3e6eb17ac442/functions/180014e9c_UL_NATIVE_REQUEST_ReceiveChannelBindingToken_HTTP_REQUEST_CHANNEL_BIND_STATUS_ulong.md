# UL_NATIVE_REQUEST::ReceiveChannelBindingToken(_HTTP_REQUEST_CHANNEL_BIND_STATUS *,ulong *)

- ea: `0x180014e9c`
- end: `0x180014f74`
- name: `?ReceiveChannelBindingToken@UL_NATIVE_REQUEST@@QEAAJPEAU_HTTP_REQUEST_CHANNEL_BIND_STATUS@@PEAK@Z`
- size: `216`
- prototype: `int(UL_NATIVE_REQUEST *__hidden this, struct _HTTP_REQUEST_CHANNEL_BIND_STATUS *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800158c0`

## callees

- `0x180012050`
- `0x180014e9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180014f48`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180014f48`
- `HTTPAPI!HttpReceiveClientCertificate` at `0x180014f34`
- `HTTPAPI!HttpReceiveClientCertificate` at `0x180014f34`

## pseudocode

```c
__int64 __fastcall UL_NATIVE_REQUEST::ReceiveChannelBindingToken(
        UL_NATIVE_REQUEST *this,
        struct _HTTP_SSL_CLIENT_CERT_INFO *a2,
        unsigned int *a3)
{
  void *v7; // rax
  signed int v8; // ebx
  PSRWLOCK SRWLock; // [rsp+60h] [rbp+18h] BYREF

  SRWLock = 0;
  if ( !a3 || !a2 && *a3 )
    return 2147942487LL;
  if ( !*(_QWORD *)(*((_QWORD *)this + 368) + 840LL) )
    return 2147942450LL;
  v7 = UL_APP_POOL::QueryAndLockHandle((WP_CONTEXT *)((char *)g_pwpContext + 760), &SRWLock);
  if ( v7 )
    v8 = HttpReceiveClientCertificate(v7, *(_QWORD *)(*((_QWORD *)this + 368) + 8LL), 1u, a2, *a3, a3, 0);
  else
    v8 = 6;
  ReleaseSRWLockShared(SRWLock);
  if ( v8 > 0 )
    return (unsigned __int16)v8 | 0x80070000;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180014e9c  mov     [rsp+arg_0], rbx
0x180014ea1  mov     [rsp+arg_8], rsi
0x180014ea6  push    rdi
0x180014ea7  sub     rsp, 40h
0x180014eab  mov     [rsp+48h+SRWLock], 0
0x180014eb4  mov     rbx, r8
0x180014eb7  mov     rdi, rdx
0x180014eba  mov     rsi, rcx
0x180014ebd  test    r8, r8
0x180014ec0  jz      loc_180014F5F
0x180014ec6  test    rdx, rdx
0x180014ec9  jnz     short loc_180014ED4
0x180014ecb  cmp     [r8], edx
0x180014ece  jnz     loc_180014F5F
0x180014ed4  mov     rax, [rcx+0B80h]
0x180014edb  cmp     qword ptr [rax+348h], 0
0x180014ee3  jnz     short loc_180014EEC
0x180014ee5  mov     eax, 80070032h
0x180014eea  jmp     short loc_180014F64
0x180014eec  mov     rcx, cs:?g_pwpContext@@3PEAVWP_CONTEXT@@EA; WP_CONTEXT * g_pwpContext
0x180014ef3  lea     rdx, [rsp+48h+SRWLock]; void **
0x180014ef8  add     rcx, 2F8h; this
0x180014eff  call    ?QueryAndLockHandle@UL_APP_POOL@@QEAAPEAXPEAPEAX@Z; UL_APP_POOL::QueryAndLockHandle(void * *)
0x180014f04  test    rax, rax
0x180014f07  jz      short loc_180014F3E
0x180014f09  mov     ecx, [rbx]
0x180014f0b  mov     r9, rdi; SslClientCertInfo
0x180014f0e  mov     rdx, [rsi+0B80h]
0x180014f15  mov     r8d, 1; Flags
0x180014f1b  mov     [rsp+48h+Overlapped], 0; Overlapped
0x180014f24  mov     [rsp+48h+BytesReceived], rbx; BytesReceived
0x180014f29  mov     [rsp+48h+SslClientCertInfoSize], ecx; SslClientCertInfoSize
0x180014f2d  mov     rcx, rax; RequestQueueHandle
0x180014f30  mov     rdx, [rdx+8]; ConnectionId
0x180014f34  call    cs:__imp_HttpReceiveClientCertificate
0x180014f3a  mov     ebx, eax
0x180014f3c  jmp     short loc_180014F43
0x180014f3e  mov     ebx, 6
0x180014f43  mov     rcx, [rsp+48h+SRWLock]; SRWLock
0x180014f48  call    cs:__imp_ReleaseSRWLockShared
0x180014f4e  test    ebx, ebx
0x180014f50  jle     short loc_180014F5B
0x180014f52  movzx   ebx, bx
0x180014f55  or      ebx, 80070000h
0x180014f5b  mov     eax, ebx
0x180014f5d  jmp     short loc_180014F64
0x180014f5f  mov     eax, 80070057h
0x180014f64  mov     rbx, [rsp+48h+arg_0]
0x180014f69  mov     rsi, [rsp+48h+arg_8]
0x180014f6e  add     rsp, 40h
0x180014f72  pop     rdi
0x180014f73  retn
```
