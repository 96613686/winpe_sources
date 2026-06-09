# CreateAndActivateContext

- ea: `0x180009f14`
- end: `0x180009fce`
- name: `CreateAndActivateContext`
- size: `186`
- prototype: `__int64 __fastcall(ULONG_PTR *lpCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180009590`

## callees

- `0x180009f14`
- `0x18000a640`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180009f61`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180009f61`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x180009fa4`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x180009fa4`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x180009f8f`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x180009f8f`

## pseudocode

```c
HANDLE __fastcall CreateAndActivateContext(ULONG_PTR *lpCookie)
{
  HANDLE v2; // rax
  HANDLE v3; // rbx
  ACTCTXW pActCtx; // [rsp+20h] [rbp-268h] BYREF
  WCHAR Filename[264]; // [rsp+60h] [rbp-228h] BYREF

  memset(&pActCtx.wProcessorArchitecture, 0, 40);
  GetModuleFileNameW(g_hinst, Filename, 0x104u);
  pActCtx.cbSize = 56;
  pActCtx.lpSource = Filename;
  pActCtx.dwFlags = 8;
  pActCtx.lpResourceName = (LPCWSTR)2;
  v2 = CreateActCtxW(&pActCtx);
  v3 = v2;
  if ( v2 != (HANDLE)-1LL )
    ActivateActCtx(v2, lpCookie);
  return v3;
}

```

## disassembly

```asm
0x180009f14  mov     [rsp+arg_8], rbx
0x180009f19  push    rdi
0x180009f1a  sub     rsp, 280h
0x180009f21  mov     rax, cs:__security_cookie
0x180009f28  xor     rax, rsp
0x180009f2b  mov     [rsp+288h+var_18], rax
0x180009f33  xorps   xmm0, xmm0
0x180009f36  lea     rdx, [rsp+288h+Filename]; lpFilename
0x180009f3b  mov     rdi, rcx
0x180009f3e  xor     eax, eax
0x180009f40  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hModule
0x180009f47  mov     r8d, 104h; nSize
0x180009f4d  movups  xmmword ptr [rsp+288h+pActCtx.cbSize], xmm0
0x180009f52  mov     [rsp+288h+pActCtx.hModule], rax
0x180009f57  movups  xmmword ptr [rsp+288h+pActCtx.wProcessorArchitecture], xmm0
0x180009f5c  movups  xmmword ptr [rsp+288h+pActCtx.lpResourceName], xmm0
0x180009f61  call    cs:__imp_GetModuleFileNameW
0x180009f67  lea     rax, [rsp+288h+Filename]
0x180009f6c  mov     [rsp+288h+pActCtx.cbSize], 38h ; '8'
0x180009f74  lea     rcx, [rsp+288h+pActCtx]; pActCtx
0x180009f79  mov     [rsp+288h+pActCtx.lpSource], rax
0x180009f7e  mov     [rsp+288h+pActCtx.dwFlags], 8
0x180009f86  mov     [rsp+288h+pActCtx.lpResourceName], 2
0x180009f8f  call    cs:__imp_CreateActCtxW
0x180009f95  mov     rbx, rax
0x180009f98  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180009f9c  jz      short loc_180009FAA
0x180009f9e  mov     rdx, rdi; lpCookie
0x180009fa1  mov     rcx, rax; hActCtx
0x180009fa4  call    cs:__imp_ActivateActCtx
0x180009faa  mov     rax, rbx
0x180009fad  mov     rcx, [rsp+288h+var_18]
0x180009fb5  xor     rcx, rsp; StackCookie
0x180009fb8  call    __security_check_cookie
0x180009fbd  mov     rbx, [rsp+288h+arg_8]
0x180009fc5  add     rsp, 280h
0x180009fcc  pop     rdi
0x180009fcd  retn
```
