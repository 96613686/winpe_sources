# SHFusionInitializeFromModuleID

- ea: `0x180035e90`
- end: `0x180035f9f`
- name: `SHFusionInitializeFromModuleID`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180035e08`

## callees

- `0x180012550`
- `0x180035e90`
- `0x1800361f4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180035ef6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180035ef6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180035f0d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180035f0d`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x180035f3f`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x180035f3f`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x180035f5d`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x180035f5d`

## pseudocode

```c
_BOOL8 SHFusionInitializeFromModuleID()
{
  HMODULE ModuleHandleW; // rbx
  unsigned __int16 v1; // di
  HANDLE v2; // rax
  ACTCTXW pActCtx; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR Filename[264]; // [rsp+60h] [rbp-A0h] BYREF

  if ( g_hActCtx != (HANDLE)-1LL )
    return 1;
  ModuleHandleW = hModule;
  v1 = dword_180059AD8;
  memset(&pActCtx, 0, sizeof(pActCtx));
  if ( !hModule )
    ModuleHandleW = GetModuleHandleW(0);
  GetModuleFileNameW(ModuleHandleW, Filename, 0x104u);
  pActCtx.lpResourceName = (LPCWSTR)v1;
  pActCtx.cbSize = 56;
  pActCtx.lpSource = Filename;
  pActCtx.dwFlags = 136;
  pActCtx.hModule = ModuleHandleW;
  v2 = CreateActCtxW(&pActCtx);
  if ( v2 != (HANDLE)-1LL )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_hActCtx, (signed __int64)v2, -1) != -1 )
      ReleaseActCtx(v2);
    DelayLoadCC();
  }
  return g_hActCtx != (HANDLE)-1LL;
}

```

## disassembly

```asm
0x180035e90  mov     [rsp-8+arg_0], rbx
0x180035e95  mov     [rsp-8+arg_8], rdi
0x180035e9a  push    rbp
0x180035e9b  lea     rbp, [rsp-180h]
0x180035ea3  sub     rsp, 280h
0x180035eaa  mov     rax, cs:__security_cookie
0x180035eb1  xor     rax, rsp
0x180035eb4  mov     [rbp+180h+var_10], rax
0x180035ebb  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x180035ec3  jnz     loc_180035F76
0x180035ec9  mov     rbx, cs:hModule
0x180035ed0  xorps   xmm0, xmm0
0x180035ed3  mov     edi, cs:dword_180059AD8
0x180035ed9  xor     eax, eax
0x180035edb  mov     [rsp+280h+pActCtx.hModule], rax
0x180035ee0  movups  xmmword ptr [rsp+280h+pActCtx.cbSize], xmm0
0x180035ee5  movups  xmmword ptr [rsp+280h+pActCtx.wProcessorArchitecture], xmm0
0x180035eea  movups  xmmword ptr [rsp+280h+pActCtx.lpResourceName], xmm0
0x180035eef  test    rbx, rbx
0x180035ef2  jnz     short loc_180035EFF
0x180035ef4  xor     ecx, ecx; lpModuleName
0x180035ef6  call    cs:__imp_GetModuleHandleW
0x180035efc  mov     rbx, rax
0x180035eff  mov     r8d, 104h; nSize
0x180035f05  lea     rdx, [rsp+280h+Filename]; lpFilename
0x180035f0a  mov     rcx, rbx; hModule
0x180035f0d  call    cs:__imp_GetModuleFileNameW
0x180035f13  movzx   ecx, di
0x180035f16  lea     rax, [rsp+280h+Filename]
0x180035f1b  mov     [rsp+280h+pActCtx.lpResourceName], rcx
0x180035f20  lea     rcx, [rsp+280h+pActCtx]; pActCtx
0x180035f25  mov     [rsp+280h+pActCtx.cbSize], 38h ; '8'
0x180035f2d  mov     [rsp+280h+pActCtx.lpSource], rax
0x180035f32  mov     [rsp+280h+pActCtx.dwFlags], 88h
0x180035f3a  mov     [rsp+280h+pActCtx.hModule], rbx
0x180035f3f  call    cs:__imp_CreateActCtxW
0x180035f45  mov     rcx, rax; hActCtx
0x180035f48  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180035f4c  jz      short loc_180035F68
0x180035f4e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180035f52  lock cmpxchg cs:g_hActCtx, rcx
0x180035f5b  jz      short loc_180035F63
0x180035f5d  call    cs:__imp_ReleaseActCtx
0x180035f63  call    DelayLoadCC
0x180035f68  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x180035f70  jnz     short loc_180035F76
0x180035f72  xor     eax, eax
0x180035f74  jmp     short loc_180035F7B
0x180035f76  mov     eax, 1
0x180035f7b  mov     rcx, [rbp+180h+var_10]
0x180035f82  xor     rcx, rsp; StackCookie
0x180035f85  call    __security_check_cookie
0x180035f8a  lea     r11, [rsp+280h+var_s0]
0x180035f92  mov     rbx, [r11+10h]
0x180035f96  mov     rdi, [r11+18h]
0x180035f9a  mov     rsp, r11
0x180035f9d  pop     rbp
0x180035f9e  retn
```
