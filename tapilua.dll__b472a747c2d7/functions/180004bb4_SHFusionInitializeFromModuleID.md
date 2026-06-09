# SHFusionInitializeFromModuleID

- ea: `0x180004bb4`
- end: `0x180004cb9`
- name: `SHFusionInitializeFromModuleID`
- size: `261`
- prototype: `_BOOL8 __fastcall(HMODULE hModule, unsigned __int16)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004994`
- `0x180004b44`

## callees

- `0x180001470`
- `0x180004bb4`
- `0x180004d20`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180004c10`
- `KERNEL32!GetModuleHandleW` at `0x180004c10`
- `KERNEL32!GetModuleFileNameW` at `0x180004c27`
- `KERNEL32!GetModuleFileNameW` at `0x180004c27`
- `KERNEL32!CreateActCtxW` at `0x180004c59`
- `KERNEL32!CreateActCtxW` at `0x180004c59`
- `KERNEL32!ReleaseActCtx` at `0x180004c77`
- `KERNEL32!ReleaseActCtx` at `0x180004c77`

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
0x180004bb4  mov     [rsp-8+arg_10], rbx
0x180004bb9  mov     [rsp-8+arg_18], rdi
0x180004bbe  push    rbp
0x180004bbf  lea     rbp, [rsp-180h]
0x180004bc7  sub     rsp, 280h
0x180004bce  mov     rax, cs:__security_cookie
0x180004bd5  xor     rax, rsp
0x180004bd8  mov     [rbp+180h+var_10], rax
0x180004bdf  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x180004be7  mov     rbx, rcx
0x180004bea  mov     edi, edx
0x180004bec  jnz     loc_180004C90
0x180004bf2  xorps   xmm0, xmm0
0x180004bf5  xor     eax, eax
0x180004bf7  mov     [rsp+280h+pActCtx.hModule], rax
0x180004bfc  movups  xmmword ptr [rsp+280h+pActCtx.cbSize], xmm0
0x180004c01  movups  xmmword ptr [rsp+280h+pActCtx.wProcessorArchitecture], xmm0
0x180004c06  movups  xmmword ptr [rsp+280h+pActCtx.lpResourceName], xmm0
0x180004c0b  test    rcx, rcx
0x180004c0e  jnz     short loc_180004C19
0x180004c10  call    cs:__imp_GetModuleHandleW
0x180004c16  mov     rbx, rax
0x180004c19  mov     r8d, 104h; nSize
0x180004c1f  lea     rdx, [rsp+280h+Filename]; lpFilename
0x180004c24  mov     rcx, rbx; hModule
0x180004c27  call    cs:__imp_GetModuleFileNameW
0x180004c2d  movzx   ecx, di
0x180004c30  lea     rax, [rsp+280h+Filename]
0x180004c35  mov     [rsp+280h+pActCtx.lpResourceName], rcx
0x180004c3a  lea     rcx, [rsp+280h+pActCtx]; pActCtx
0x180004c3f  mov     [rsp+280h+pActCtx.cbSize], 38h ; '8'
0x180004c47  mov     [rsp+280h+pActCtx.lpSource], rax
0x180004c4c  mov     [rsp+280h+pActCtx.dwFlags], 88h
0x180004c54  mov     [rsp+280h+pActCtx.hModule], rbx
0x180004c59  call    cs:__imp_CreateActCtxW
0x180004c5f  mov     rcx, rax; hActCtx
0x180004c62  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180004c66  jz      short loc_180004C82
0x180004c68  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004c6c  lock cmpxchg cs:g_hActCtx, rcx
0x180004c75  jz      short loc_180004C7D
0x180004c77  call    cs:__imp_ReleaseActCtx
0x180004c7d  call    DelayLoadCC
0x180004c82  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x180004c8a  jnz     short loc_180004C90
0x180004c8c  xor     eax, eax
0x180004c8e  jmp     short loc_180004C95
0x180004c90  mov     eax, 1
0x180004c95  mov     rcx, [rbp+180h+var_10]
0x180004c9c  xor     rcx, rsp; StackCookie
0x180004c9f  call    __security_check_cookie
0x180004ca4  lea     r11, [rsp+280h+var_s0]
0x180004cac  mov     rbx, [r11+20h]
0x180004cb0  mov     rdi, [r11+28h]
0x180004cb4  mov     rsp, r11
0x180004cb7  pop     rbp
0x180004cb8  retn
```
