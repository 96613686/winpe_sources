# SHFusionInitializeFromModuleID

- ea: `0x180026f04`
- end: `0x180027009`
- name: `SHFusionInitializeFromModuleID`
- size: `261`
- prototype: `__int64 __fastcall(HMODULE hModule)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800011d0`
- `0x180026e74`

## callees

- `0x180026f04`
- `0x180027068`
- `0x18002d840`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180026f60`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180026f60`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180026f77`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180026f77`
- `KERNEL32!ReleaseActCtx` at `0x180026fc7`
- `KERNEL32!ReleaseActCtx` at `0x180026fc7`
- `KERNEL32!CreateActCtxW` at `0x180026fa9`
- `KERNEL32!CreateActCtxW` at `0x180026fa9`

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
0x180026f04  mov     [rsp-8+arg_10], rbx
0x180026f09  mov     [rsp-8+arg_18], rdi
0x180026f0e  push    rbp
0x180026f0f  lea     rbp, [rsp-180h]
0x180026f17  sub     rsp, 280h
0x180026f1e  mov     rax, cs:__security_cookie
0x180026f25  xor     rax, rsp
0x180026f28  mov     [rbp+180h+var_10], rax
0x180026f2f  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x180026f37  mov     rbx, rcx
0x180026f3a  mov     edi, edx
0x180026f3c  jnz     loc_180026FE0
0x180026f42  xorps   xmm0, xmm0
0x180026f45  xor     eax, eax
0x180026f47  mov     [rsp+280h+pActCtx.hModule], rax
0x180026f4c  movups  xmmword ptr [rsp+280h+pActCtx.cbSize], xmm0
0x180026f51  movups  xmmword ptr [rsp+280h+pActCtx.wProcessorArchitecture], xmm0
0x180026f56  movups  xmmword ptr [rsp+280h+pActCtx.lpResourceName], xmm0
0x180026f5b  test    rcx, rcx
0x180026f5e  jnz     short loc_180026F69
0x180026f60  call    cs:__imp_GetModuleHandleW
0x180026f66  mov     rbx, rax
0x180026f69  mov     r8d, 104h; nSize
0x180026f6f  lea     rdx, [rsp+280h+Filename]; lpFilename
0x180026f74  mov     rcx, rbx; hModule
0x180026f77  call    cs:__imp_GetModuleFileNameW
0x180026f7d  movzx   ecx, di
0x180026f80  lea     rax, [rsp+280h+Filename]
0x180026f85  mov     [rsp+280h+pActCtx.lpResourceName], rcx
0x180026f8a  lea     rcx, [rsp+280h+pActCtx]; pActCtx
0x180026f8f  mov     [rsp+280h+pActCtx.cbSize], 38h ; '8'
0x180026f97  mov     [rsp+280h+pActCtx.lpSource], rax
0x180026f9c  mov     [rsp+280h+pActCtx.dwFlags], 88h
0x180026fa4  mov     [rsp+280h+pActCtx.hModule], rbx
0x180026fa9  call    cs:__imp_CreateActCtxW
0x180026faf  mov     rcx, rax; hActCtx
0x180026fb2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180026fb6  jz      short loc_180026FD2
0x180026fb8  or      rax, 0FFFFFFFFFFFFFFFFh
0x180026fbc  lock cmpxchg cs:g_hActCtx, rcx
0x180026fc5  jz      short loc_180026FCD
0x180026fc7  call    cs:__imp_ReleaseActCtx
0x180026fcd  call    DelayLoadCC
0x180026fd2  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x180026fda  jnz     short loc_180026FE0
0x180026fdc  xor     eax, eax
0x180026fde  jmp     short loc_180026FE5
0x180026fe0  mov     eax, 1
0x180026fe5  mov     rcx, [rbp+180h+var_10]
0x180026fec  xor     rcx, rsp; StackCookie
0x180026fef  call    __security_check_cookie
0x180026ff4  lea     r11, [rsp+280h+var_s0]
0x180026ffc  mov     rbx, [r11+20h]
0x180027000  mov     rdi, [r11+28h]
0x180027004  mov     rsp, r11
0x180027007  pop     rbp
0x180027008  retn
```
