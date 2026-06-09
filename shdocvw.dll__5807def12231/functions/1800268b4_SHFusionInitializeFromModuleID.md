# SHFusionInitializeFromModuleID

- ea: `0x1800268b4`
- end: `0x1800269c3`
- name: `SHFusionInitializeFromModuleID`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002ca0`

## callees

- `0x180006880`
- `0x180008320`
- `0x1800268b4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180026931`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180026931`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002691a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002691a`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x180026963`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x180026963`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x180026981`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x180026981`

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
  v1 = dword_180038D48;
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
0x1800268b4  mov     [rsp-8+arg_0], rbx
0x1800268b9  mov     [rsp-8+arg_8], rdi
0x1800268be  push    rbp
0x1800268bf  lea     rbp, [rsp-180h]
0x1800268c7  sub     rsp, 280h
0x1800268ce  mov     rax, cs:__security_cookie
0x1800268d5  xor     rax, rsp
0x1800268d8  mov     [rbp+180h+var_10], rax
0x1800268df  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x1800268e7  jnz     loc_18002699A
0x1800268ed  mov     rbx, cs:hModule
0x1800268f4  xorps   xmm0, xmm0
0x1800268f7  mov     edi, cs:dword_180038D48
0x1800268fd  xor     eax, eax
0x1800268ff  mov     [rsp+280h+pActCtx.hModule], rax
0x180026904  movups  xmmword ptr [rsp+280h+pActCtx.cbSize], xmm0
0x180026909  movups  xmmword ptr [rsp+280h+pActCtx.wProcessorArchitecture], xmm0
0x18002690e  movups  xmmword ptr [rsp+280h+pActCtx.lpResourceName], xmm0
0x180026913  test    rbx, rbx
0x180026916  jnz     short loc_180026923
0x180026918  xor     ecx, ecx; lpModuleName
0x18002691a  call    cs:__imp_GetModuleHandleW
0x180026920  mov     rbx, rax
0x180026923  mov     r8d, 104h; nSize
0x180026929  lea     rdx, [rsp+280h+Filename]; lpFilename
0x18002692e  mov     rcx, rbx; hModule
0x180026931  call    cs:__imp_GetModuleFileNameW
0x180026937  movzx   ecx, di
0x18002693a  lea     rax, [rsp+280h+Filename]
0x18002693f  mov     [rsp+280h+pActCtx.lpResourceName], rcx
0x180026944  lea     rcx, [rsp+280h+pActCtx]; pActCtx
0x180026949  mov     [rsp+280h+pActCtx.cbSize], 38h ; '8'
0x180026951  mov     [rsp+280h+pActCtx.lpSource], rax
0x180026956  mov     [rsp+280h+pActCtx.dwFlags], 88h
0x18002695e  mov     [rsp+280h+pActCtx.hModule], rbx
0x180026963  call    cs:__imp_CreateActCtxW
0x180026969  mov     rcx, rax; hActCtx
0x18002696c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180026970  jz      short loc_18002698C
0x180026972  or      rax, 0FFFFFFFFFFFFFFFFh
0x180026976  lock cmpxchg cs:g_hActCtx, rcx
0x18002697f  jz      short loc_180026987
0x180026981  call    cs:__imp_ReleaseActCtx
0x180026987  call    DelayLoadCC
0x18002698c  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x180026994  jnz     short loc_18002699A
0x180026996  xor     eax, eax
0x180026998  jmp     short loc_18002699F
0x18002699a  mov     eax, 1
0x18002699f  mov     rcx, [rbp+180h+var_10]
0x1800269a6  xor     rcx, rsp; StackCookie
0x1800269a9  call    __security_check_cookie
0x1800269ae  lea     r11, [rsp+280h+var_s0]
0x1800269b6  mov     rbx, [r11+10h]
0x1800269ba  mov     rdi, [r11+18h]
0x1800269be  mov     rsp, r11
0x1800269c1  pop     rbp
0x1800269c2  retn
```
