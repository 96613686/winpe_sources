# IsProcessLowIL(void *)

- ea: `0x18002c3b0`
- end: `0x18002c41b`
- name: `?IsProcessLowIL@@YAJPEAX@Z`
- size: `107`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18001a0e8`

## callees

- `0x18000b3c0`
- `0x18002c3b0`
- `0x18002c424`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c3fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c3fc`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002c3d1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002c3d1`

## pseudocode

```c
__int64 __fastcall IsProcessLowIL(void *a1)
{
  int TokenIL; // ebx
  unsigned int v3; // [rsp+38h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp+18h] BYREF

  v3 = 0;
  TokenHandle = 0;
  if ( OpenProcessToken(a1, 8u, &TokenHandle) || (TokenIL = ResultFromKnownLastError(), TokenIL >= 0) )
  {
    TokenIL = GetTokenIL(TokenHandle, &v3);
    CloseHandle(TokenHandle);
    if ( TokenIL >= 0 )
      return v3 >= 0x2000;
  }
  return (unsigned int)TokenIL;
}

```

## disassembly

```asm
0x18002c3b0  push    rbx
0x18002c3b2  sub     rsp, 20h
0x18002c3b6  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x18002c3bb  mov     [rsp+28h+arg_8], 0
0x18002c3c3  mov     edx, 8; DesiredAccess
0x18002c3c8  mov     [rsp+28h+TokenHandle], 0
0x18002c3d1  call    cs:__imp_OpenProcessToken
0x18002c3d7  test    eax, eax
0x18002c3d9  jnz     short loc_18002C3E6
0x18002c3db  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002c3e0  mov     ebx, eax
0x18002c3e2  test    eax, eax
0x18002c3e4  js      short loc_18002C413
0x18002c3e6  mov     rcx, [rsp+28h+TokenHandle]
0x18002c3eb  lea     rdx, [rsp+28h+arg_8]
0x18002c3f0  call    GetTokenIL
0x18002c3f5  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x18002c3fa  mov     ebx, eax
0x18002c3fc  call    cs:__imp_CloseHandle
0x18002c402  test    ebx, ebx
0x18002c404  js      short loc_18002C413
0x18002c406  xor     ebx, ebx
0x18002c408  cmp     [rsp+28h+arg_8], 2000h
0x18002c410  setnb   bl
0x18002c413  mov     eax, ebx
0x18002c415  add     rsp, 20h
0x18002c419  pop     rbx
0x18002c41a  retn
```
