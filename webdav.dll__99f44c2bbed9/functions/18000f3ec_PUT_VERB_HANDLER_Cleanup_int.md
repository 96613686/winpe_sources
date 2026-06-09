# PUT_VERB_HANDLER::Cleanup(int)

- ea: `0x18000f3ec`
- end: `0x18000f4d8`
- name: `?Cleanup@PUT_VERB_HANDLER@@AEAAJH@Z`
- size: `236`
- prototype: `__int64 __fastcall(PUT_VERB_HANDLER *__hidden this, int)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000f640`
- `0x18000fa00`
- `0x18000fb00`
- `0x18000fc50`

## callees

- `0x18000f3ec`
- `0x18001b2cc`
- `0x180023010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000f49c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000f4ab`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000f49c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000f4ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f480`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f480`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000f476`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000f476`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f414`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f414`

## pseudocode

```c
__int64 __fastcall PUT_VERB_HANDLER::Cleanup(PUT_VERB_HANDLER *this, int a2)
{
  __int64 *v2; // rdi
  void *v4; // rcx
  __int64 v6; // rax
  struct IHttpContext *v8; // rdx
  signed int LastError; // eax
  unsigned int v10; // ebx
  int v12; // [rsp+20h] [rbp-18h] BYREF
  __int64 v13; // [rsp+28h] [rbp-10h]

  v2 = (__int64 *)*((_QWORD *)this + 30);
  v4 = (void *)*((_QWORD *)this + 48);
  if ( v4 != (void *)-1LL )
  {
    CloseHandle(v4);
    *((_QWORD *)this + 48) = -1;
  }
  v6 = *v2;
  if ( a2 )
    return (unsigned int)(*(__int64 (__fastcall **)(__int64 *))(v6 + 16))(v2);
  if ( (*(__int64 (__fastcall **)(__int64 *))(v6 + 32))(v2) != -1 )
    return (unsigned int)(*(__int64 (__fastcall **)(__int64 *))(*v2 + 24))(v2);
  if ( *((_DWORD *)this + 100) )
    return 0;
  v8 = (struct IHttpContext *)*((_QWORD *)this + 1);
  v12 = 0;
  v13 = 0;
  AUTO_IMPERSONATE::Impersonate((AUTO_IMPERSONATE *)&v12, v8);
  if ( DeleteFileW(*((LPCWSTR *)this + 52)) )
  {
    if ( v12 )
      RevertToSelf();
    return 0;
  }
  LastError = GetLastError();
  v10 = LastError;
  if ( LastError > 0 )
    v10 = (unsigned __int16)LastError | 0x80070000;
  if ( v12 )
    RevertToSelf();
  return v10;
}

```

## disassembly

```asm
0x18000f3ec  mov     [rsp+arg_0], rbx
0x18000f3f1  mov     [rsp+arg_8], rsi
0x18000f3f6  push    rdi
0x18000f3f7  sub     rsp, 30h
0x18000f3fb  mov     rdi, [rcx+0F0h]
0x18000f402  mov     rbx, rcx
0x18000f405  mov     rcx, [rcx+180h]; hObject
0x18000f40c  mov     esi, edx
0x18000f40e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000f412  jz      short loc_18000F425
0x18000f414  call    cs:__imp_CloseHandle
0x18000f41a  mov     qword ptr [rbx+180h], 0FFFFFFFFFFFFFFFFh
0x18000f425  mov     rax, [rdi]
0x18000f428  mov     rcx, rdi
0x18000f42b  test    esi, esi
0x18000f42d  jz      short loc_18000F438
0x18000f42f  mov     rax, [rax+10h]
0x18000f433  jmp     loc_18000F4BF
0x18000f438  mov     rax, [rax+20h]
0x18000f43c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f441  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000f445  jnz     short loc_18000F4B5
0x18000f447  cmp     dword ptr [rbx+190h], 0
0x18000f44e  jnz     short loc_18000F4B1
0x18000f450  mov     rdx, [rbx+8]; struct IHttpContext *
0x18000f454  lea     rcx, [rsp+38h+var_18]; this
0x18000f459  mov     [rsp+38h+var_18], 0
0x18000f461  mov     [rsp+38h+var_10], 0
0x18000f46a  call    ?Impersonate@AUTO_IMPERSONATE@@QEAAJPEAVIHttpContext@@@Z; AUTO_IMPERSONATE::Impersonate(IHttpContext *)
0x18000f46f  mov     rcx, [rbx+1A0h]; lpFileName
0x18000f476  call    cs:__imp_DeleteFileW
0x18000f47c  test    eax, eax
0x18000f47e  jnz     short loc_18000F4A4
0x18000f480  call    cs:__imp_GetLastError
0x18000f486  mov     ebx, eax
0x18000f488  test    eax, eax
0x18000f48a  jle     short loc_18000F495
0x18000f48c  movzx   ebx, ax
0x18000f48f  or      ebx, 80070000h
0x18000f495  cmp     [rsp+38h+var_18], 0
0x18000f49a  jz      short loc_18000F4C6
0x18000f49c  call    cs:__imp_RevertToSelf
0x18000f4a2  jmp     short loc_18000F4C6
0x18000f4a4  cmp     [rsp+38h+var_18], 0
0x18000f4a9  jz      short loc_18000F4B1
0x18000f4ab  call    cs:__imp_RevertToSelf
0x18000f4b1  xor     ebx, ebx
0x18000f4b3  jmp     short loc_18000F4C6
0x18000f4b5  mov     rax, [rdi]
0x18000f4b8  mov     rcx, rdi
0x18000f4bb  mov     rax, [rax+18h]
0x18000f4bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4c4  mov     ebx, eax
0x18000f4c6  mov     rsi, [rsp+38h+arg_8]
0x18000f4cb  mov     eax, ebx
0x18000f4cd  mov     rbx, [rsp+38h+arg_0]
0x18000f4d2  add     rsp, 30h
0x18000f4d6  pop     rdi
0x18000f4d7  retn
```
