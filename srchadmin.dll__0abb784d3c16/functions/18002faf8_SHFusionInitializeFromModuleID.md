# SHFusionInitializeFromModuleID

- ea: `0x18002faf8`
- end: `0x18002fbfd`
- name: `SHFusionInitializeFromModuleID`
- size: `261`
- prototype: `_BOOL8 __fastcall(HMODULE hModule, unsigned __int16)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001f9f8`
- `0x18002f938`

## callees

- `0x180005cc0`
- `0x18002faf8`
- `0x180030044`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002fb54`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002fb54`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18002fb6b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18002fb6b`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x18002fbbb`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x18002fbbb`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x18002fb9d`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x18002fb9d`

## pseudocode

```c
_BOOL8 __fastcall SHFusionInitializeFromModuleID(HMODULE hModule, unsigned __int16 a2)
{
  HMODULE ModuleHandleW; // rbx
  HANDLE v4; // rax
  HANDLE v5; // rcx
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
  v5 = v4;
  if ( v4 != (HANDLE)-1LL )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_hActCtx, (signed __int64)v4, -1) != -1 )
      ReleaseActCtx(v4);
    DelayLoadCC(v5);
  }
  return g_hActCtx != (HANDLE)-1LL;
}

```

## disassembly

```asm
0x18002faf8  mov     [rsp-8+arg_10], rbx
0x18002fafd  mov     [rsp-8+arg_18], rdi
0x18002fb02  push    rbp
0x18002fb03  lea     rbp, [rsp-180h]
0x18002fb0b  sub     rsp, 280h
0x18002fb12  mov     rax, cs:__security_cookie
0x18002fb19  xor     rax, rsp
0x18002fb1c  mov     [rbp+180h+var_10], rax
0x18002fb23  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x18002fb2b  mov     rbx, rcx
0x18002fb2e  mov     edi, edx
0x18002fb30  jnz     loc_18002FBD4
0x18002fb36  xorps   xmm0, xmm0
0x18002fb39  xor     eax, eax
0x18002fb3b  mov     [rsp+280h+pActCtx.hModule], rax
0x18002fb40  movups  xmmword ptr [rsp+280h+pActCtx.cbSize], xmm0
0x18002fb45  movups  xmmword ptr [rsp+280h+pActCtx.wProcessorArchitecture], xmm0
0x18002fb4a  movups  xmmword ptr [rsp+280h+pActCtx.lpResourceName], xmm0
0x18002fb4f  test    rcx, rcx
0x18002fb52  jnz     short loc_18002FB5D
0x18002fb54  call    cs:__imp_GetModuleHandleW
0x18002fb5a  mov     rbx, rax
0x18002fb5d  mov     r8d, 104h; nSize
0x18002fb63  lea     rdx, [rsp+280h+Filename]; lpFilename
0x18002fb68  mov     rcx, rbx; hModule
0x18002fb6b  call    cs:__imp_GetModuleFileNameW
0x18002fb71  movzx   ecx, di
0x18002fb74  lea     rax, [rsp+280h+Filename]
0x18002fb79  mov     [rsp+280h+pActCtx.lpResourceName], rcx
0x18002fb7e  lea     rcx, [rsp+280h+pActCtx]; pActCtx
0x18002fb83  mov     [rsp+280h+pActCtx.cbSize], 38h ; '8'
0x18002fb8b  mov     [rsp+280h+pActCtx.lpSource], rax
0x18002fb90  mov     [rsp+280h+pActCtx.dwFlags], 88h
0x18002fb98  mov     [rsp+280h+pActCtx.hModule], rbx
0x18002fb9d  call    cs:__imp_CreateActCtxW
0x18002fba3  mov     rcx, rax; hActCtx
0x18002fba6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002fbaa  jz      short loc_18002FBC6
0x18002fbac  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002fbb0  lock cmpxchg cs:g_hActCtx, rcx
0x18002fbb9  jz      short loc_18002FBC1
0x18002fbbb  call    cs:__imp_ReleaseActCtx
0x18002fbc1  call    DelayLoadCC
0x18002fbc6  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x18002fbce  jnz     short loc_18002FBD4
0x18002fbd0  xor     eax, eax
0x18002fbd2  jmp     short loc_18002FBD9
0x18002fbd4  mov     eax, 1
0x18002fbd9  mov     rcx, [rbp+180h+var_10]
0x18002fbe0  xor     rcx, rsp; StackCookie
0x18002fbe3  call    __security_check_cookie
0x18002fbe8  lea     r11, [rsp+280h+var_s0]
0x18002fbf0  mov     rbx, [r11+20h]
0x18002fbf4  mov     rdi, [r11+28h]
0x18002fbf8  mov     rsp, r11
0x18002fbfb  pop     rbp
0x18002fbfc  retn
```
