# ElValidateWin32_13

- ea: `0x180024c1c`
- end: `0x180024ce5`
- name: `ElValidateWin32_13`
- size: `201`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180024e40`
- `0x180024f60`

## callees

- `0x180024c1c`
- `0x180030010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180024cc6`
- `KERNEL32!SetLastError` at `0x180024cc6`
- `KERNEL32!GetLastError` at `0x180024c42`
- `KERNEL32!GetLastError` at `0x180024c8e`
- `KERNEL32!GetLastError` at `0x180024c42`
- `KERNEL32!GetLastError` at `0x180024c8e`

## string_xrefs

- `0x180024c5e`: `onecore\base\eco\wds\wdslib\common\src\setuputil.cpp`
- `0x180024ca7`: `onecore\base\eco\wds\wdslib\common\src\setuputil.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_13(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\setuputil.cpp",
        a4,
        &dword_1800331C4,
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\setuputil.cpp",
        a4,
        &dword_1800331C4,
        a1);
      goto LABEL_6;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180024c1c  mov     [rsp+arg_0], rbx
0x180024c21  mov     [rsp+arg_8], rsi
0x180024c26  push    rdi
0x180024c27  sub     rsp, 40h
0x180024c2b  mov     esi, r9d
0x180024c2e  mov     edi, ecx
0x180024c30  test    ecx, ecx
0x180024c32  jz      loc_180024CD2
0x180024c38  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180024c40  jz      short loc_180024C84
0x180024c42  call    cs:__imp_GetLastError
0x180024c49  nop     dword ptr [rax+rax+00h]
0x180024c4e  lea     r9, dword_1800331C4
0x180024c55  mov     [rsp+48h+var_20], edi
0x180024c59  mov     [rsp+48h+var_28], r9
0x180024c5e  lea     r8, aOnecoreBaseEco_35; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180024c65  mov     ebx, eax
0x180024c67  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180024c6e  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180024c75  mov     r9d, esi
0x180024c78  mov     ecx, 80000h
0x180024c7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c82  jmp     short loc_180024CC4
0x180024c84  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180024c8c  jz      short loc_180024CD2
0x180024c8e  call    cs:__imp_GetLastError
0x180024c95  nop     dword ptr [rax+rax+00h]
0x180024c9a  lea     r9, dword_1800331C4
0x180024ca1  mov     dword ptr [rsp+48h+var_28], edi
0x180024ca5  mov     ebx, eax
0x180024ca7  lea     rdx, aOnecoreBaseEco_35; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180024cae  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180024cb5  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180024cbc  mov     r8d, esi
0x180024cbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024cc4  mov     ecx, ebx; dwErrCode
0x180024cc6  call    cs:__imp_SetLastError
0x180024ccd  nop     dword ptr [rax+rax+00h]
0x180024cd2  mov     rbx, [rsp+48h+arg_0]
0x180024cd7  mov     eax, edi
0x180024cd9  mov     rsi, [rsp+48h+arg_8]
0x180024cde  add     rsp, 40h
0x180024ce2  pop     rdi
0x180024ce3  retn
```
