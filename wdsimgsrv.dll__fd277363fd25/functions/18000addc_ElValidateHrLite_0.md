# ElValidateHrLite_0

- ea: `0x18000addc`
- end: `0x18000aea5`
- name: `ElValidateHrLite_0`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ad88`

## callees

- `0x18000addc`
- `0x180017010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000ae86`
- `KERNEL32!SetLastError` at `0x18000ae86`
- `KERNEL32!GetLastError` at `0x18000ae02`
- `KERNEL32!GetLastError` at `0x18000ae4e`
- `KERNEL32!GetLastError` at `0x18000ae02`
- `KERNEL32!GetLastError` at `0x18000ae4e`

## string_xrefs

- `0x18000ae1e`: `base\eco\wds\wdssrv\wdsimgsrv\src\imagecache.cpp`
- `0x18000ae67`: `base\eco\wds\wdssrv\wdsimgsrv\src\imagecache.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateHrLite_0(int a1, __int64 a2, __int64 a3, unsigned int a4)
{
  DWORD LastError; // ebx

  if ( a1 < 0 )
  {
    if ( g_ErrLibTraceFunctionEx )
    {
      LastError = GetLastError();
      g_ErrLibTraceFunctionEx(
        0x80000u,
        L"[%S:%u] Expression: %S, hr=0x%x",
        "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp",
        a4,
        &dword_18001A184,
        a1);
LABEL_6:
      SetLastError(LastError);
      return (unsigned int)a1;
    }
    if ( g_ErrLibTraceFunction )
    {
      LastError = GetLastError();
      g_ErrLibTraceFunction(
        L"[%S:%u] Expression: %S, hr=0x%x",
        "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src\\imagecache.cpp",
        a4,
        &dword_18001A184,
        a1);
      goto LABEL_6;
    }
  }
  return (unsigned int)a1;
}

```

## disassembly

```asm
0x18000addc  mov     [rsp+arg_0], rbx
0x18000ade1  mov     [rsp+arg_8], rsi
0x18000ade6  push    rdi
0x18000ade7  sub     rsp, 40h
0x18000adeb  mov     esi, r9d
0x18000adee  mov     edi, ecx
0x18000adf0  test    ecx, ecx
0x18000adf2  jns     loc_18000AE92
0x18000adf8  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000ae00  jz      short loc_18000AE44
0x18000ae02  call    cs:__imp_GetLastError
0x18000ae09  nop     dword ptr [rax+rax+00h]
0x18000ae0e  lea     r9, dword_18001A184
0x18000ae15  mov     [rsp+48h+var_20], edi
0x18000ae19  mov     [rsp+48h+var_28], r9
0x18000ae1e  lea     r8, aBaseEcoWdsWdss_0; "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src"...
0x18000ae25  mov     ebx, eax
0x18000ae27  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18000ae2e  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000ae35  mov     r9d, esi
0x18000ae38  mov     ecx, 80000h
0x18000ae3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae42  jmp     short loc_18000AE84
0x18000ae44  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000ae4c  jz      short loc_18000AE92
0x18000ae4e  call    cs:__imp_GetLastError
0x18000ae55  nop     dword ptr [rax+rax+00h]
0x18000ae5a  lea     r9, dword_18001A184
0x18000ae61  mov     dword ptr [rsp+48h+var_28], edi
0x18000ae65  mov     ebx, eax
0x18000ae67  lea     rdx, aBaseEcoWdsWdss_0; "base\\eco\\wds\\wdssrv\\wdsimgsrv\\src"...
0x18000ae6e  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000ae75  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18000ae7c  mov     r8d, esi
0x18000ae7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae84  mov     ecx, ebx; dwErrCode
0x18000ae86  call    cs:__imp_SetLastError
0x18000ae8d  nop     dword ptr [rax+rax+00h]
0x18000ae92  mov     rbx, [rsp+48h+arg_0]
0x18000ae97  mov     eax, edi
0x18000ae99  mov     rsi, [rsp+48h+arg_8]
0x18000ae9e  add     rsp, 40h
0x18000aea2  pop     rdi
0x18000aea3  retn
```
