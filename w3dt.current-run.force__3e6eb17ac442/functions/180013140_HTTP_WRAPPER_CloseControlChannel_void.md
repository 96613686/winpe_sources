# HTTP_WRAPPER::CloseControlChannel(void)

- ea: `0x180013140`
- end: `0x180013168`
- name: `?CloseControlChannel@HTTP_WRAPPER@@QEAAKXZ`
- size: `40`
- prototype: `unsigned int __fastcall(HTTP_WRAPPER *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180013084`
- `0x1800130e8`

## callees

- `0x180013140`

## import_xrefs

- `HTTPAPI!HttpCloseServerSession` at `0x180013152`
- `HTTPAPI!HttpCloseServerSession` at `0x180013152`

## pseudocode

```c
__int64 __fastcall HTTP_WRAPPER::CloseControlChannel(HTTP_WRAPPER *this)
{
  HTTP_SERVER_SESSION_ID v2; // rcx

  v2 = *((_QWORD *)this + 2);
  if ( v2 )
  {
    HttpCloseServerSession(v2);
    *((_QWORD *)this + 2) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180013140  push    rbx
0x180013142  sub     rsp, 20h
0x180013146  mov     rbx, rcx
0x180013149  mov     rcx, [rcx+10h]; ServerSessionId
0x18001314d  test    rcx, rcx
0x180013150  jz      short loc_180013160
0x180013152  call    cs:__imp_HttpCloseServerSession
0x180013158  mov     qword ptr [rbx+10h], 0
0x180013160  xor     eax, eax
0x180013162  add     rsp, 20h
0x180013166  pop     rbx
0x180013167  retn
```
