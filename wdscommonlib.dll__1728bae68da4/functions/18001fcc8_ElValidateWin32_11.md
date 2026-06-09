# ElValidateWin32_11

- ea: `0x18001fcc8`
- end: `0x18001fd91`
- name: `ElValidateWin32_11`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001f980`

## callees

- `0x18001fcc8`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18001fd72`
- `KERNEL32!SetLastError` at `0x18001fd72`
- `KERNEL32!GetLastError` at `0x18001fcee`
- `KERNEL32!GetLastError` at `0x18001fd3a`
- `KERNEL32!GetLastError` at `0x18001fcee`
- `KERNEL32!GetLastError` at `0x18001fd3a`

## string_xrefs

- `0x18001fd0a`: `onecore\base\eco\wds\wdslib\common\src\errormessage.cpp`
- `0x18001fd53`: `onecore\base\eco\wds\wdslib\common\src\errormessage.cpp`

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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\errormessage.cpp",
        a4,
        &dword_18003572C,
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\errormessage.cpp",
        a4,
        &dword_18003572C,
        a1);
      goto LABEL_6;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18001fcc8  mov     [rsp+arg_0], rbx
0x18001fccd  mov     [rsp+arg_8], rsi
0x18001fcd2  push    rdi
0x18001fcd3  sub     rsp, 40h
0x18001fcd7  mov     esi, r9d
0x18001fcda  mov     edi, ecx
0x18001fcdc  test    ecx, ecx
0x18001fcde  jz      loc_18001FD7E
0x18001fce4  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001fcec  jz      short loc_18001FD30
0x18001fcee  call    cs:__imp_GetLastError
0x18001fcf5  nop     dword ptr [rax+rax+00h]
0x18001fcfa  lea     r9, dword_18003572C
0x18001fd01  mov     [rsp+48h+var_20], edi
0x18001fd05  mov     [rsp+48h+var_28], r9
0x18001fd0a  lea     r8, aOnecoreBaseEco_15; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18001fd11  mov     ebx, eax
0x18001fd13  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18001fd1a  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001fd21  mov     r9d, esi
0x18001fd24  mov     ecx, 80000h
0x18001fd29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd2e  jmp     short loc_18001FD70
0x18001fd30  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18001fd38  jz      short loc_18001FD7E
0x18001fd3a  call    cs:__imp_GetLastError
0x18001fd41  nop     dword ptr [rax+rax+00h]
0x18001fd46  lea     r9, dword_18003572C
0x18001fd4d  mov     dword ptr [rsp+48h+var_28], edi
0x18001fd51  mov     ebx, eax
0x18001fd53  lea     rdx, aOnecoreBaseEco_15; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18001fd5a  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18001fd61  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18001fd68  mov     r8d, esi
0x18001fd6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd70  mov     ecx, ebx; dwErrCode
0x18001fd72  call    cs:__imp_SetLastError
0x18001fd79  nop     dword ptr [rax+rax+00h]
0x18001fd7e  mov     rbx, [rsp+48h+arg_0]
0x18001fd83  mov     eax, edi
0x18001fd85  mov     rsi, [rsp+48h+arg_8]
0x18001fd8a  add     rsp, 40h
0x18001fd8e  pop     rdi
0x18001fd8f  retn
```
