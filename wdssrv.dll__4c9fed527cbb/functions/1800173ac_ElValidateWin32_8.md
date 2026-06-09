# ElValidateWin32_8

- ea: `0x1800173ac`
- end: `0x180017475`
- name: `ElValidateWin32_8`
- size: `201`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800160e8`
- `0x1800162d4`
- `0x180016948`
- `0x180016b08`
- `0x180016da4`
- `0x180016f98`
- `0x1800171d0`

## callees

- `0x1800173ac`
- `0x18001d010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180017456`
- `KERNEL32!SetLastError` at `0x180017456`
- `KERNEL32!GetLastError` at `0x1800173d2`
- `KERNEL32!GetLastError` at `0x18001741e`
- `KERNEL32!GetLastError` at `0x1800173d2`
- `KERNEL32!GetLastError` at `0x18001741e`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_8(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
{
  DWORD LastError; // ebx

  if ( a1 )
  {
    if ( g_ErrLibTraceFunctionEx )
    {
      LastError = GetLastError();
      g_ErrLibTraceFunctionEx(
        0x80000u,
        L"[%S:%u] Expression: %S, Win32 Error=0x%x",
        "base\\eco\\wds\\wdssrv\\server\\src\\madcaphandler.cpp",
        a4,
        &dword_18001F974,
        a1);
LABEL_6:
      SetLastError(LastError);
      return a1;
    }
    if ( g_ErrLibTraceFunction )
    {
      LastError = GetLastError();
      g_ErrLibTraceFunction(
        L"[%S:%u] Expression: %S, Win32 Error=0x%x",
        "base\\eco\\wds\\wdssrv\\server\\src\\madcaphandler.cpp",
        a4,
        &dword_18001F974,
        a1);
      goto LABEL_6;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1800173ac  mov     [rsp+arg_0], rbx
0x1800173b1  mov     [rsp+arg_8], rsi
0x1800173b6  push    rdi
0x1800173b7  sub     rsp, 40h
0x1800173bb  mov     esi, r9d
0x1800173be  mov     edi, ecx
0x1800173c0  test    ecx, ecx
0x1800173c2  jz      loc_180017462
0x1800173c8  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800173d0  jz      short loc_180017414
0x1800173d2  call    cs:__imp_GetLastError
0x1800173d9  nop     dword ptr [rax+rax+00h]
0x1800173de  lea     r9, dword_18001F974
0x1800173e5  mov     [rsp+48h+var_20], edi
0x1800173e9  mov     [rsp+48h+var_28], r9
0x1800173ee  lea     r8, aBaseEcoWdsWdss_3; "base\\eco\\wds\\wdssrv\\server\\src\\ma"...
0x1800173f5  mov     ebx, eax
0x1800173f7  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x1800173fe  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180017405  mov     r9d, esi
0x180017408  mov     ecx, 80000h
0x18001740d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017412  jmp     short loc_180017454
0x180017414  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18001741c  jz      short loc_180017462
0x18001741e  call    cs:__imp_GetLastError
0x180017425  nop     dword ptr [rax+rax+00h]
0x18001742a  lea     r9, dword_18001F974
0x180017431  mov     dword ptr [rsp+48h+var_28], edi
0x180017435  mov     ebx, eax
0x180017437  lea     rdx, aBaseEcoWdsWdss_3; "base\\eco\\wds\\wdssrv\\server\\src\\ma"...
0x18001743e  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180017445  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18001744c  mov     r8d, esi
0x18001744f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017454  mov     ecx, ebx; dwErrCode
0x180017456  call    cs:__imp_SetLastError
0x18001745d  nop     dword ptr [rax+rax+00h]
0x180017462  mov     rbx, [rsp+48h+arg_0]
0x180017467  mov     eax, edi
0x180017469  mov     rsi, [rsp+48h+arg_8]
0x18001746e  add     rsp, 40h
0x180017472  pop     rdi
0x180017473  retn
```
