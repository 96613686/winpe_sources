# SHFusionInitializeFromModuleID

- ea: `0x180014b70`
- end: `0x180014c75`
- name: `SHFusionInitializeFromModuleID`
- size: `261`
- prototype: `__int64 __fastcall(HMODULE hModule)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005ca0`
- `0x180014b00`

## callees

- `0x180014b70`
- `0x180014dd8`
- `0x18001bf40`

## import_xrefs

- `KERNEL32!CreateActCtxW` at `0x180014c15`
- `KERNEL32!CreateActCtxW` at `0x180014c15`
- `KERNEL32!GetModuleHandleW` at `0x180014bcc`
- `KERNEL32!GetModuleHandleW` at `0x180014bcc`
- `KERNEL32!GetModuleFileNameW` at `0x180014be3`
- `KERNEL32!GetModuleFileNameW` at `0x180014be3`
- `KERNEL32!ReleaseActCtx` at `0x180014c33`
- `KERNEL32!ReleaseActCtx` at `0x180014c33`

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
0x180014b70  mov     [rsp-8+arg_10], rbx
0x180014b75  mov     [rsp-8+arg_18], rdi
0x180014b7a  push    rbp
0x180014b7b  lea     rbp, [rsp-180h]
0x180014b83  sub     rsp, 280h
0x180014b8a  mov     rax, cs:__security_cookie
0x180014b91  xor     rax, rsp
0x180014b94  mov     [rbp+180h+var_10], rax
0x180014b9b  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x180014ba3  mov     rbx, rcx
0x180014ba6  mov     edi, edx
0x180014ba8  jnz     loc_180014C4C
0x180014bae  xorps   xmm0, xmm0
0x180014bb1  xor     eax, eax
0x180014bb3  mov     [rsp+280h+pActCtx.hModule], rax
0x180014bb8  movups  xmmword ptr [rsp+280h+pActCtx.cbSize], xmm0
0x180014bbd  movups  xmmword ptr [rsp+280h+pActCtx.wProcessorArchitecture], xmm0
0x180014bc2  movups  xmmword ptr [rsp+280h+pActCtx.lpResourceName], xmm0
0x180014bc7  test    rcx, rcx
0x180014bca  jnz     short loc_180014BD5
0x180014bcc  call    cs:__imp_GetModuleHandleW
0x180014bd2  mov     rbx, rax
0x180014bd5  mov     r8d, 104h; nSize
0x180014bdb  lea     rdx, [rsp+280h+Filename]; lpFilename
0x180014be0  mov     rcx, rbx; hModule
0x180014be3  call    cs:__imp_GetModuleFileNameW
0x180014be9  movzx   ecx, di
0x180014bec  lea     rax, [rsp+280h+Filename]
0x180014bf1  mov     [rsp+280h+pActCtx.lpResourceName], rcx
0x180014bf6  lea     rcx, [rsp+280h+pActCtx]; pActCtx
0x180014bfb  mov     [rsp+280h+pActCtx.cbSize], 38h ; '8'
0x180014c03  mov     [rsp+280h+pActCtx.lpSource], rax
0x180014c08  mov     [rsp+280h+pActCtx.dwFlags], 88h
0x180014c10  mov     [rsp+280h+pActCtx.hModule], rbx
0x180014c15  call    cs:__imp_CreateActCtxW
0x180014c1b  mov     rcx, rax; hActCtx
0x180014c1e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180014c22  jz      short loc_180014C3E
0x180014c24  or      rax, 0FFFFFFFFFFFFFFFFh
0x180014c28  lock cmpxchg cs:g_hActCtx, rcx
0x180014c31  jz      short loc_180014C39
0x180014c33  call    cs:__imp_ReleaseActCtx
0x180014c39  call    DelayLoadCC
0x180014c3e  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x180014c46  jnz     short loc_180014C4C
0x180014c48  xor     eax, eax
0x180014c4a  jmp     short loc_180014C51
0x180014c4c  mov     eax, 1
0x180014c51  mov     rcx, [rbp+180h+var_10]
0x180014c58  xor     rcx, rsp; StackCookie
0x180014c5b  call    __security_check_cookie
0x180014c60  lea     r11, [rsp+280h+var_s0]
0x180014c68  mov     rbx, [r11+20h]
0x180014c6c  mov     rdi, [r11+28h]
0x180014c70  mov     rsp, r11
0x180014c73  pop     rbp
0x180014c74  retn
```
