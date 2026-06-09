# SHFusionInitializeFromModuleID

- ea: `0x1800161bc`
- end: `0x1800162c1`
- name: `SHFusionInitializeFromModuleID`
- size: `261`
- prototype: `__int64 __fastcall(HMODULE hModule)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000345c`
- `0x18001614c`

## callees

- `0x180001d60`
- `0x1800161bc`
- `0x180016524`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x18001622f`
- `KERNEL32!GetModuleFileNameW` at `0x18001622f`
- `KERNEL32!ReleaseActCtx` at `0x18001627f`
- `KERNEL32!ReleaseActCtx` at `0x18001627f`
- `KERNEL32!CreateActCtxW` at `0x180016261`
- `KERNEL32!CreateActCtxW` at `0x180016261`
- `KERNEL32!GetModuleHandleW` at `0x180016218`
- `KERNEL32!GetModuleHandleW` at `0x180016218`

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
0x1800161bc  mov     [rsp-8+arg_10], rbx
0x1800161c1  mov     [rsp-8+arg_18], rdi
0x1800161c6  push    rbp
0x1800161c7  lea     rbp, [rsp-180h]
0x1800161cf  sub     rsp, 280h
0x1800161d6  mov     rax, cs:__security_cookie
0x1800161dd  xor     rax, rsp
0x1800161e0  mov     [rbp+180h+var_10], rax
0x1800161e7  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x1800161ef  mov     rbx, rcx
0x1800161f2  mov     edi, edx
0x1800161f4  jnz     loc_180016298
0x1800161fa  xorps   xmm0, xmm0
0x1800161fd  xor     eax, eax
0x1800161ff  mov     [rsp+280h+pActCtx.hModule], rax
0x180016204  movups  xmmword ptr [rsp+280h+pActCtx.cbSize], xmm0
0x180016209  movups  xmmword ptr [rsp+280h+pActCtx.wProcessorArchitecture], xmm0
0x18001620e  movups  xmmword ptr [rsp+280h+pActCtx.lpResourceName], xmm0
0x180016213  test    rcx, rcx
0x180016216  jnz     short loc_180016221
0x180016218  call    cs:__imp_GetModuleHandleW
0x18001621e  mov     rbx, rax
0x180016221  mov     r8d, 104h; nSize
0x180016227  lea     rdx, [rsp+280h+Filename]; lpFilename
0x18001622c  mov     rcx, rbx; hModule
0x18001622f  call    cs:__imp_GetModuleFileNameW
0x180016235  movzx   ecx, di
0x180016238  lea     rax, [rsp+280h+Filename]
0x18001623d  mov     [rsp+280h+pActCtx.lpResourceName], rcx
0x180016242  lea     rcx, [rsp+280h+pActCtx]; pActCtx
0x180016247  mov     [rsp+280h+pActCtx.cbSize], 38h ; '8'
0x18001624f  mov     [rsp+280h+pActCtx.lpSource], rax
0x180016254  mov     [rsp+280h+pActCtx.dwFlags], 88h
0x18001625c  mov     [rsp+280h+pActCtx.hModule], rbx
0x180016261  call    cs:__imp_CreateActCtxW
0x180016267  mov     rcx, rax; hActCtx
0x18001626a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001626e  jz      short loc_18001628A
0x180016270  or      rax, 0FFFFFFFFFFFFFFFFh
0x180016274  lock cmpxchg cs:g_hActCtx, rcx
0x18001627d  jz      short loc_180016285
0x18001627f  call    cs:__imp_ReleaseActCtx
0x180016285  call    DelayLoadCC
0x18001628a  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x180016292  jnz     short loc_180016298
0x180016294  xor     eax, eax
0x180016296  jmp     short loc_18001629D
0x180016298  mov     eax, 1
0x18001629d  mov     rcx, [rbp+180h+var_10]
0x1800162a4  xor     rcx, rsp; StackCookie
0x1800162a7  call    __security_check_cookie
0x1800162ac  lea     r11, [rsp+280h+var_s0]
0x1800162b4  mov     rbx, [r11+20h]
0x1800162b8  mov     rdi, [r11+28h]
0x1800162bc  mov     rsp, r11
0x1800162bf  pop     rbp
0x1800162c0  retn
```
