# SHFusionInitializeFromModuleID

- ea: `0x18008eed4`
- end: `0x18008efd9`
- name: `SHFusionInitializeFromModuleID`
- size: `261`
- prototype: `__int64 __fastcall(HMODULE hModule)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180018060`
- `0x18008ebb0`

## callees

- `0x18008eed4`
- `0x18008f094`
- `0x180091ef0`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18008ef30`
- `KERNEL32!GetModuleHandleW` at `0x18008ef30`
- `KERNEL32!GetModuleFileNameW` at `0x18008ef47`
- `KERNEL32!GetModuleFileNameW` at `0x18008ef47`
- `KERNEL32!CreateActCtxW` at `0x18008ef79`
- `KERNEL32!CreateActCtxW` at `0x18008ef79`
- `KERNEL32!ReleaseActCtx` at `0x18008ef97`
- `KERNEL32!ReleaseActCtx` at `0x18008ef97`

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
0x18008eed4  mov     [rsp-8+arg_10], rbx
0x18008eed9  mov     [rsp-8+arg_18], rdi
0x18008eede  push    rbp
0x18008eedf  lea     rbp, [rsp-180h]
0x18008eee7  sub     rsp, 280h
0x18008eeee  mov     rax, cs:__security_cookie
0x18008eef5  xor     rax, rsp
0x18008eef8  mov     [rbp+180h+var_10], rax
0x18008eeff  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x18008ef07  mov     rbx, rcx
0x18008ef0a  mov     edi, edx
0x18008ef0c  jnz     loc_18008EFB0
0x18008ef12  xorps   xmm0, xmm0
0x18008ef15  xor     eax, eax
0x18008ef17  mov     [rsp+280h+pActCtx.hModule], rax
0x18008ef1c  movups  xmmword ptr [rsp+280h+pActCtx.cbSize], xmm0
0x18008ef21  movups  xmmword ptr [rsp+280h+pActCtx.wProcessorArchitecture], xmm0
0x18008ef26  movups  xmmword ptr [rsp+280h+pActCtx.lpResourceName], xmm0
0x18008ef2b  test    rcx, rcx
0x18008ef2e  jnz     short loc_18008EF39
0x18008ef30  call    cs:__imp_GetModuleHandleW
0x18008ef36  mov     rbx, rax
0x18008ef39  mov     r8d, 104h; nSize
0x18008ef3f  lea     rdx, [rsp+280h+Filename]; lpFilename
0x18008ef44  mov     rcx, rbx; hModule
0x18008ef47  call    cs:__imp_GetModuleFileNameW
0x18008ef4d  movzx   ecx, di
0x18008ef50  lea     rax, [rsp+280h+Filename]
0x18008ef55  mov     [rsp+280h+pActCtx.lpResourceName], rcx
0x18008ef5a  lea     rcx, [rsp+280h+pActCtx]; pActCtx
0x18008ef5f  mov     [rsp+280h+pActCtx.cbSize], 38h ; '8'
0x18008ef67  mov     [rsp+280h+pActCtx.lpSource], rax
0x18008ef6c  mov     [rsp+280h+pActCtx.dwFlags], 88h
0x18008ef74  mov     [rsp+280h+pActCtx.hModule], rbx
0x18008ef79  call    cs:__imp_CreateActCtxW
0x18008ef7f  mov     rcx, rax; hActCtx
0x18008ef82  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18008ef86  jz      short loc_18008EFA2
0x18008ef88  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008ef8c  lock cmpxchg cs:g_hActCtx, rcx
0x18008ef95  jz      short loc_18008EF9D
0x18008ef97  call    cs:__imp_ReleaseActCtx
0x18008ef9d  call    DelayLoadCC
0x18008efa2  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x18008efaa  jnz     short loc_18008EFB0
0x18008efac  xor     eax, eax
0x18008efae  jmp     short loc_18008EFB5
0x18008efb0  mov     eax, 1
0x18008efb5  mov     rcx, [rbp+180h+var_10]
0x18008efbc  xor     rcx, rsp; StackCookie
0x18008efbf  call    __security_check_cookie
0x18008efc4  lea     r11, [rsp+280h+var_s0]
0x18008efcc  mov     rbx, [r11+20h]
0x18008efd0  mov     rdi, [r11+28h]
0x18008efd4  mov     rsp, r11
0x18008efd7  pop     rbp
0x18008efd8  retn
```
