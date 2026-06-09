# SHFusionInitializeFromModuleID

- ea: `0x180027eb4`
- end: `0x180027fb9`
- name: `SHFusionInitializeFromModuleID`
- size: `261`
- prototype: `__int64 __fastcall(HMODULE hModule)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800010f0`
- `0x180027d70`

## callees

- `0x180027eb4`
- `0x1800280ac`
- `0x180029280`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180027f10`
- `KERNEL32!GetModuleHandleW` at `0x180027f10`
- `KERNEL32!GetModuleFileNameW` at `0x180027f27`
- `KERNEL32!GetModuleFileNameW` at `0x180027f27`
- `KERNEL32!ReleaseActCtx` at `0x180027f77`
- `KERNEL32!ReleaseActCtx` at `0x180027f77`
- `KERNEL32!CreateActCtxW` at `0x180027f59`
- `KERNEL32!CreateActCtxW` at `0x180027f59`

## pseudocode

```c
_BOOL8 __fastcall SHFusionInitializeFromModuleID(HMODULE hModule, unsigned __int16 a2)
{
  HMODULE ModuleHandleW; // rbx
  HANDLE v4; // rax
  ACTCTXW pActCtx; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR Filename[264]; // [rsp+60h] [rbp-A0h] BYREF

  ModuleHandleW = hModule;
  if ( g_hActCtx != (HANDLE)-1LL )
    return 1;
  memset(&pActCtx, 0, sizeof(pActCtx));
  if ( !hModule )
    ModuleHandleW = GetModuleHandleW(0);
  GetModuleFileNameW(ModuleHandleW, Filename, 0x104u);
  pActCtx.lpResourceName = (LPCWSTR)a2;
  pActCtx.cbSize = 56;
  pActCtx.lpSource = Filename;
  pActCtx.dwFlags = 136;
  pActCtx.hModule = ModuleHandleW;
  v4 = CreateActCtxW(&pActCtx);
  if ( v4 != (HANDLE)-1LL )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_hActCtx, (signed __int64)v4, -1) != -1 )
      ReleaseActCtx(v4);
    DelayLoadCC();
  }
  return g_hActCtx != (HANDLE)-1LL;
}

```

## disassembly

```asm
0x180027eb4  mov     [rsp-8+arg_10], rbx
0x180027eb9  mov     [rsp-8+arg_18], rdi
0x180027ebe  push    rbp
0x180027ebf  lea     rbp, [rsp-180h]
0x180027ec7  sub     rsp, 280h
0x180027ece  mov     rax, cs:__security_cookie
0x180027ed5  xor     rax, rsp
0x180027ed8  mov     [rbp+180h+var_10], rax
0x180027edf  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x180027ee7  mov     rbx, rcx
0x180027eea  mov     edi, edx
0x180027eec  jnz     loc_180027F90
0x180027ef2  xorps   xmm0, xmm0
0x180027ef5  xor     eax, eax
0x180027ef7  mov     [rsp+280h+pActCtx.hModule], rax
0x180027efc  movups  xmmword ptr [rsp+280h+pActCtx.cbSize], xmm0
0x180027f01  movups  xmmword ptr [rsp+280h+pActCtx.wProcessorArchitecture], xmm0
0x180027f06  movups  xmmword ptr [rsp+280h+pActCtx.lpResourceName], xmm0
0x180027f0b  test    rcx, rcx
0x180027f0e  jnz     short loc_180027F19
0x180027f10  call    cs:__imp_GetModuleHandleW
0x180027f16  mov     rbx, rax
0x180027f19  mov     r8d, 104h; nSize
0x180027f1f  lea     rdx, [rsp+280h+Filename]; lpFilename
0x180027f24  mov     rcx, rbx; hModule
0x180027f27  call    cs:__imp_GetModuleFileNameW
0x180027f2d  movzx   ecx, di
0x180027f30  lea     rax, [rsp+280h+Filename]
0x180027f35  mov     [rsp+280h+pActCtx.lpResourceName], rcx
0x180027f3a  lea     rcx, [rsp+280h+pActCtx]; pActCtx
0x180027f3f  mov     [rsp+280h+pActCtx.cbSize], 38h ; '8'
0x180027f47  mov     [rsp+280h+pActCtx.lpSource], rax
0x180027f4c  mov     [rsp+280h+pActCtx.dwFlags], 88h
0x180027f54  mov     [rsp+280h+pActCtx.hModule], rbx
0x180027f59  call    cs:__imp_CreateActCtxW
0x180027f5f  mov     rcx, rax; hActCtx
0x180027f62  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180027f66  jz      short loc_180027F82
0x180027f68  or      rax, 0FFFFFFFFFFFFFFFFh
0x180027f6c  lock cmpxchg cs:g_hActCtx, rcx
0x180027f75  jz      short loc_180027F7D
0x180027f77  call    cs:__imp_ReleaseActCtx
0x180027f7d  call    DelayLoadCC
0x180027f82  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x180027f8a  jnz     short loc_180027F90
0x180027f8c  xor     eax, eax
0x180027f8e  jmp     short loc_180027F95
0x180027f90  mov     eax, 1
0x180027f95  mov     rcx, [rbp+180h+var_10]
0x180027f9c  xor     rcx, rsp; StackCookie
0x180027f9f  call    __security_check_cookie
0x180027fa4  lea     r11, [rsp+280h+var_s0]
0x180027fac  mov     rbx, [r11+20h]
0x180027fb0  mov     rdi, [r11+28h]
0x180027fb4  mov     rsp, r11
0x180027fb7  pop     rbp
0x180027fb8  retn
```
