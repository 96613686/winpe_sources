# SHFusionInitializeFromModuleID

- ea: `0x18000a220`
- end: `0x18000a32f`
- name: `SHFusionInitializeFromModuleID`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000a198`

## callees

- `0x18000a03c`
- `0x18000a220`
- `0x18000a640`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000a29d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000a29d`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x18000a2cf`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x18000a2cf`
- `KERNEL32!ReleaseActCtx` at `0x18000a2ed`
- `KERNEL32!ReleaseActCtx` at `0x18000a2ed`
- `KERNEL32!GetModuleHandleW` at `0x18000a286`
- `KERNEL32!GetModuleHandleW` at `0x18000a286`

## pseudocode

```c
_BOOL8 SHFusionInitializeFromModuleID()
{
  HMODULE ModuleHandleW; // rbx
  unsigned __int16 v1; // di
  HANDLE v2; // rax
  ACTCTXW pActCtx; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR Filename[264]; // [rsp+60h] [rbp-A0h] BYREF

  if ( g_hActCtx != -1 )
    return 1;
  ModuleHandleW = hModule;
  v1 = dword_180014AF8;
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
    if ( _InterlockedCompareExchange64(&g_hActCtx, (signed __int64)v2, -1) != -1 )
      ReleaseActCtx(v2);
    DelayLoadCC();
  }
  return g_hActCtx != -1;
}

```

## disassembly

```asm
0x18000a220  mov     [rsp-8+arg_0], rbx
0x18000a225  mov     [rsp-8+arg_8], rdi
0x18000a22a  push    rbp
0x18000a22b  lea     rbp, [rsp-180h]
0x18000a233  sub     rsp, 280h
0x18000a23a  mov     rax, cs:__security_cookie
0x18000a241  xor     rax, rsp
0x18000a244  mov     [rbp+180h+var_10], rax
0x18000a24b  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x18000a253  jnz     loc_18000A306
0x18000a259  mov     rbx, cs:hModule
0x18000a260  xorps   xmm0, xmm0
0x18000a263  mov     edi, cs:dword_180014AF8
0x18000a269  xor     eax, eax
0x18000a26b  mov     [rsp+280h+pActCtx.hModule], rax
0x18000a270  movups  xmmword ptr [rsp+280h+pActCtx.cbSize], xmm0
0x18000a275  movups  xmmword ptr [rsp+280h+pActCtx.wProcessorArchitecture], xmm0
0x18000a27a  movups  xmmword ptr [rsp+280h+pActCtx.lpResourceName], xmm0
0x18000a27f  test    rbx, rbx
0x18000a282  jnz     short loc_18000A28F
0x18000a284  xor     ecx, ecx; lpModuleName
0x18000a286  call    cs:__imp_GetModuleHandleW
0x18000a28c  mov     rbx, rax
0x18000a28f  mov     r8d, 104h; nSize
0x18000a295  lea     rdx, [rsp+280h+Filename]; lpFilename
0x18000a29a  mov     rcx, rbx; hModule
0x18000a29d  call    cs:__imp_GetModuleFileNameW
0x18000a2a3  movzx   ecx, di
0x18000a2a6  lea     rax, [rsp+280h+Filename]
0x18000a2ab  mov     [rsp+280h+pActCtx.lpResourceName], rcx
0x18000a2b0  lea     rcx, [rsp+280h+pActCtx]; pActCtx
0x18000a2b5  mov     [rsp+280h+pActCtx.cbSize], 38h ; '8'
0x18000a2bd  mov     [rsp+280h+pActCtx.lpSource], rax
0x18000a2c2  mov     [rsp+280h+pActCtx.dwFlags], 88h
0x18000a2ca  mov     [rsp+280h+pActCtx.hModule], rbx
0x18000a2cf  call    cs:__imp_CreateActCtxW
0x18000a2d5  mov     rcx, rax; hActCtx
0x18000a2d8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000a2dc  jz      short loc_18000A2F8
0x18000a2de  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a2e2  lock cmpxchg cs:g_hActCtx, rcx
0x18000a2eb  jz      short loc_18000A2F3
0x18000a2ed  call    cs:__imp_ReleaseActCtx
0x18000a2f3  call    DelayLoadCC
0x18000a2f8  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x18000a300  jnz     short loc_18000A306
0x18000a302  xor     eax, eax
0x18000a304  jmp     short loc_18000A30B
0x18000a306  mov     eax, 1
0x18000a30b  mov     rcx, [rbp+180h+var_10]
0x18000a312  xor     rcx, rsp; StackCookie
0x18000a315  call    __security_check_cookie
0x18000a31a  lea     r11, [rsp+280h+var_s0]
0x18000a322  mov     rbx, [r11+10h]
0x18000a326  mov     rdi, [r11+18h]
0x18000a32a  mov     rsp, r11
0x18000a32d  pop     rbp
0x18000a32e  retn
```
