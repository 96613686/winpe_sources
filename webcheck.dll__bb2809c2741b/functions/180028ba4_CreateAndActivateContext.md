# CreateAndActivateContext

- ea: `0x180028ba4`
- end: `0x180028c66`
- name: `CreateAndActivateContext`
- size: `194`
- prototype: `__int64 __fastcall(ULONG_PTR *lpCookie)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800286e8`

## callees

- `0x180028ba4`
- `0x180029280`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x180028bf5`
- `KERNEL32!GetModuleFileNameW` at `0x180028bf5`
- `KERNEL32!CreateActCtxW` at `0x180028c27`
- `KERNEL32!CreateActCtxW` at `0x180028c27`
- `KERNEL32!ActivateActCtx` at `0x180028c3c`
- `KERNEL32!ActivateActCtx` at `0x180028c3c`

## pseudocode

```c
__int64 __fastcall CreateAndActivateContext(ULONG_PTR *lpCookie)
{
  __int64 v2; // rbx
  HANDLE v3; // rax
  ACTCTXW pActCtx; // [rsp+20h] [rbp-268h] BYREF
  WCHAR Filename[264]; // [rsp+60h] [rbp-228h] BYREF

  memset(&pActCtx, 0, sizeof(pActCtx));
  v2 = -1;
  if ( GetModuleFileNameW(g_hinst, Filename, 0x104u) )
  {
    pActCtx.cbSize = 56;
    pActCtx.lpSource = Filename;
    pActCtx.dwFlags = 8;
    pActCtx.lpResourceName = (LPCWSTR)123;
    v3 = CreateActCtxW(&pActCtx);
    v2 = (__int64)v3;
    if ( v3 != (HANDLE)-1LL )
      ActivateActCtx(v3, lpCookie);
  }
  return v2;
}

```

## disassembly

```asm
0x180028ba4  mov     [rsp+arg_8], rbx
0x180028ba9  push    rdi
0x180028baa  sub     rsp, 280h
0x180028bb1  mov     rax, cs:__security_cookie
0x180028bb8  xor     rax, rsp
0x180028bbb  mov     [rsp+288h+var_18], rax
0x180028bc3  xorps   xmm0, xmm0
0x180028bc6  lea     rdx, [rsp+288h+Filename]; lpFilename
0x180028bcb  mov     rdi, rcx
0x180028bce  xor     eax, eax
0x180028bd0  mov     rcx, cs:g_hinst; hModule
0x180028bd7  mov     r8d, 104h; nSize
0x180028bdd  movups  xmmword ptr [rsp+288h+pActCtx.cbSize], xmm0
0x180028be2  mov     [rsp+288h+pActCtx.hModule], rax
0x180028be7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180028beb  movups  xmmword ptr [rsp+288h+pActCtx.wProcessorArchitecture], xmm0
0x180028bf0  movups  xmmword ptr [rsp+288h+pActCtx.lpResourceName], xmm0
0x180028bf5  call    cs:__imp_GetModuleFileNameW
0x180028bfb  test    eax, eax
0x180028bfd  jz      short loc_180028C42
0x180028bff  lea     rax, [rsp+288h+Filename]
0x180028c04  mov     [rsp+288h+pActCtx.cbSize], 38h ; '8'
0x180028c0c  lea     rcx, [rsp+288h+pActCtx]; pActCtx
0x180028c11  mov     [rsp+288h+pActCtx.lpSource], rax
0x180028c16  mov     [rsp+288h+pActCtx.dwFlags], 8
0x180028c1e  mov     [rsp+288h+pActCtx.lpResourceName], 7Bh ; '{'
0x180028c27  call    cs:__imp_CreateActCtxW
0x180028c2d  mov     rbx, rax
0x180028c30  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180028c34  jz      short loc_180028C42
0x180028c36  mov     rdx, rdi; lpCookie
0x180028c39  mov     rcx, rax; hActCtx
0x180028c3c  call    cs:__imp_ActivateActCtx
0x180028c42  mov     rax, rbx
0x180028c45  mov     rcx, [rsp+288h+var_18]
0x180028c4d  xor     rcx, rsp; StackCookie
0x180028c50  call    __security_check_cookie
0x180028c55  mov     rbx, [rsp+288h+arg_8]
0x180028c5d  add     rsp, 280h
0x180028c64  pop     rdi
0x180028c65  retn
```
