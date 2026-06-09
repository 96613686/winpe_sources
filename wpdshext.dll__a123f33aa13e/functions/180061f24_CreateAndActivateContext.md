# CreateAndActivateContext

- ea: `0x180061f24`
- end: `0x180061fde`
- name: `CreateAndActivateContext`
- size: `186`
- prototype: `__int64 __fastcall(ULONG_PTR *lpCookie)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18006e410`
- `0x18006e494`
- `0x180071c14`

## callees

- `0x180035590`
- `0x180061f24`

## import_xrefs

- `KERNEL32!ActivateActCtx` at `0x180061fb4`
- `KERNEL32!ActivateActCtx` at `0x180061fb4`
- `KERNEL32!CreateActCtxW` at `0x180061f9f`
- `KERNEL32!CreateActCtxW` at `0x180061f9f`
- `KERNEL32!GetModuleFileNameW` at `0x180061f71`
- `KERNEL32!GetModuleFileNameW` at `0x180061f71`

## pseudocode

```c
HANDLE __fastcall CreateAndActivateContext(ULONG_PTR *lpCookie)
{
  HANDLE v2; // rax
  HANDLE v3; // rbx
  ACTCTXW pActCtx; // [rsp+20h] [rbp-268h] BYREF
  WCHAR Filename[264]; // [rsp+60h] [rbp-228h] BYREF

  memset(&pActCtx.wProcessorArchitecture, 0, 40);
  GetModuleFileNameW(g_hInst, Filename, 0x104u);
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
0x180061f24  mov     [rsp+arg_8], rbx
0x180061f29  push    rdi
0x180061f2a  sub     rsp, 280h
0x180061f31  mov     rax, cs:__security_cookie
0x180061f38  xor     rax, rsp
0x180061f3b  mov     [rsp+288h+var_18], rax
0x180061f43  xorps   xmm0, xmm0
0x180061f46  lea     rdx, [rsp+288h+Filename]; lpFilename
0x180061f4b  mov     rdi, rcx
0x180061f4e  xor     eax, eax
0x180061f50  mov     rcx, cs:g_hInst; hModule
0x180061f57  mov     r8d, 104h; nSize
0x180061f5d  movups  xmmword ptr [rsp+288h+pActCtx.cbSize], xmm0
0x180061f62  mov     [rsp+288h+pActCtx.hModule], rax
0x180061f67  movups  xmmword ptr [rsp+288h+pActCtx.wProcessorArchitecture], xmm0
0x180061f6c  movups  xmmword ptr [rsp+288h+pActCtx.lpResourceName], xmm0
0x180061f71  call    cs:__imp_GetModuleFileNameW
0x180061f77  lea     rax, [rsp+288h+Filename]
0x180061f7c  mov     [rsp+288h+pActCtx.cbSize], 38h ; '8'
0x180061f84  lea     rcx, [rsp+288h+pActCtx]; pActCtx
0x180061f89  mov     [rsp+288h+pActCtx.lpSource], rax
0x180061f8e  mov     [rsp+288h+pActCtx.dwFlags], 8
0x180061f96  mov     [rsp+288h+pActCtx.lpResourceName], 2
0x180061f9f  call    cs:__imp_CreateActCtxW
0x180061fa5  mov     rbx, rax
0x180061fa8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180061fac  jz      short loc_180061FBA
0x180061fae  mov     rdx, rdi; lpCookie
0x180061fb1  mov     rcx, rax; hActCtx
0x180061fb4  call    cs:__imp_ActivateActCtx
0x180061fba  mov     rax, rbx
0x180061fbd  mov     rcx, [rsp+288h+var_18]
0x180061fc5  xor     rcx, rsp; StackCookie
0x180061fc8  call    __security_check_cookie
0x180061fcd  mov     rbx, [rsp+288h+arg_8]
0x180061fd5  add     rsp, 280h
0x180061fdc  pop     rdi
0x180061fdd  retn
```
