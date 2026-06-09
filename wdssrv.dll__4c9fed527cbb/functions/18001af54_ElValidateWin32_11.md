# ElValidateWin32_11

- ea: `0x18001af54`
- end: `0x18001b01d`
- name: `ElValidateWin32_11`
- size: `201`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18001a594`
- `0x18001a910`
- `0x18001ac90`
- `0x18001ad9c`

## callees

- `0x18001af54`
- `0x18001d010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18001affe`
- `KERNEL32!SetLastError` at `0x18001affe`
- `KERNEL32!GetLastError` at `0x18001af7a`
- `KERNEL32!GetLastError` at `0x18001afc6`
- `KERNEL32!GetLastError` at `0x18001af7a`
- `KERNEL32!GetLastError` at `0x18001afc6`

## string_xrefs

- `0x18001af96`: `base\eco\wds\wdssrv\server\src\wdsvsswriter.cpp`
- `0x18001afdf`: `base\eco\wds\wdssrv\server\src\wdsvsswriter.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_11(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "base\\eco\\wds\\wdssrv\\server\\src\\wdsvsswriter.cpp",
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
        "base\\eco\\wds\\wdssrv\\server\\src\\wdsvsswriter.cpp",
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
0x18001af54  mov     [rsp+arg_0], rbx
0x18001af59  mov     [rsp+arg_8], rsi
0x18001af5e  push    rdi
0x18001af5f  sub     rsp, 40h
0x18001af63  mov     esi, r9d
0x18001af66  mov     edi, ecx
0x18001af68  test    ecx, ecx
0x18001af6a  jz      loc_18001B00A
0x18001af70  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001af78  jz      short loc_18001AFBC
0x18001af7a  call    cs:__imp_GetLastError
0x18001af81  nop     dword ptr [rax+rax+00h]
0x18001af86  lea     r9, dword_18001F974
0x18001af8d  mov     [rsp+48h+var_20], edi
0x18001af91  mov     [rsp+48h+var_28], r9
0x18001af96  lea     r8, aBaseEcoWdsWdss_19; "base\\eco\\wds\\wdssrv\\server\\src\\wd"...
0x18001af9d  mov     ebx, eax
0x18001af9f  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18001afa6  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001afad  mov     r9d, esi
0x18001afb0  mov     ecx, 80000h
0x18001afb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001afba  jmp     short loc_18001AFFC
0x18001afbc  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18001afc4  jz      short loc_18001B00A
0x18001afc6  call    cs:__imp_GetLastError
0x18001afcd  nop     dword ptr [rax+rax+00h]
0x18001afd2  lea     r9, dword_18001F974
0x18001afd9  mov     dword ptr [rsp+48h+var_28], edi
0x18001afdd  mov     ebx, eax
0x18001afdf  lea     rdx, aBaseEcoWdsWdss_19; "base\\eco\\wds\\wdssrv\\server\\src\\wd"...
0x18001afe6  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18001afed  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18001aff4  mov     r8d, esi
0x18001aff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001affc  mov     ecx, ebx; dwErrCode
0x18001affe  call    cs:__imp_SetLastError
0x18001b005  nop     dword ptr [rax+rax+00h]
0x18001b00a  mov     rbx, [rsp+48h+arg_0]
0x18001b00f  mov     eax, edi
0x18001b011  mov     rsi, [rsp+48h+arg_8]
0x18001b016  add     rsp, 40h
0x18001b01a  pop     rdi
0x18001b01b  retn
```
