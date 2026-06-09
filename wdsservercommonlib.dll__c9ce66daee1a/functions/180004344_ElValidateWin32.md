# ElValidateWin32

- ea: `0x180004344`
- end: `0x18000440d`
- name: `ElValidateWin32`
- size: `201`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003110`
- `0x180003270`
- `0x1800032e0`
- `0x180003560`
- `0x1800036b0`
- `0x180003710`
- `0x1800040b0`
- `0x180013670`
- `0x180014170`

## callees

- `0x180004344`
- `0x180030010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800043ee`
- `KERNEL32!SetLastError` at `0x1800043ee`
- `KERNEL32!GetLastError` at `0x18000436a`
- `KERNEL32!GetLastError` at `0x1800043b6`
- `KERNEL32!GetLastError` at `0x18000436a`
- `KERNEL32!GetLastError` at `0x1800043b6`

## string_xrefs

- `0x180004386`: `onecore\base\Eco\WDS\wdslib\common\inc\Ldap.h`
- `0x1800043cf`: `onecore\base\Eco\WDS\wdslib\common\inc\Ldap.h`

## pseudocode

```c
__int64 __fastcall ElValidateWin32(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "onecore\\base\\Eco\\WDS\\wdslib\\common\\inc\\Ldap.h",
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
        "onecore\\base\\Eco\\WDS\\wdslib\\common\\inc\\Ldap.h",
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
0x180004344  mov     [rsp+arg_0], rbx
0x180004349  mov     [rsp+arg_8], rsi
0x18000434e  push    rdi
0x18000434f  sub     rsp, 40h
0x180004353  mov     esi, r9d
0x180004356  mov     edi, ecx
0x180004358  test    ecx, ecx
0x18000435a  jz      loc_1800043FA
0x180004360  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180004368  jz      short loc_1800043AC
0x18000436a  call    cs:__imp_GetLastError
0x180004371  nop     dword ptr [rax+rax+00h]
0x180004376  lea     r9, dword_1800331C4
0x18000437d  mov     [rsp+48h+var_20], edi
0x180004381  mov     [rsp+48h+var_28], r9
0x180004386  lea     r8, aOnecoreBaseEco_14; "onecore\\base\\Eco\\WDS\\wdslib\\common"...
0x18000438d  mov     ebx, eax
0x18000438f  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180004396  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000439d  mov     r9d, esi
0x1800043a0  mov     ecx, 80000h
0x1800043a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043aa  jmp     short loc_1800043EC
0x1800043ac  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800043b4  jz      short loc_1800043FA
0x1800043b6  call    cs:__imp_GetLastError
0x1800043bd  nop     dword ptr [rax+rax+00h]
0x1800043c2  lea     r9, dword_1800331C4
0x1800043c9  mov     dword ptr [rsp+48h+var_28], edi
0x1800043cd  mov     ebx, eax
0x1800043cf  lea     rdx, aOnecoreBaseEco_14; "onecore\\base\\Eco\\WDS\\wdslib\\common"...
0x1800043d6  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800043dd  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x1800043e4  mov     r8d, esi
0x1800043e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043ec  mov     ecx, ebx; dwErrCode
0x1800043ee  call    cs:__imp_SetLastError
0x1800043f5  nop     dword ptr [rax+rax+00h]
0x1800043fa  mov     rbx, [rsp+48h+arg_0]
0x1800043ff  mov     eax, edi
0x180004401  mov     rsi, [rsp+48h+arg_8]
0x180004406  add     rsp, 40h
0x18000440a  pop     rdi
0x18000440b  retn
```
