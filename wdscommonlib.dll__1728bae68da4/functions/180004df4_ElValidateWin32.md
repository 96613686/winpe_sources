# ElValidateWin32

- ea: `0x180004df4`
- end: `0x180004ebd`
- name: `ElValidateWin32`
- size: `201`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003bb0`
- `0x180003d10`
- `0x180003d80`
- `0x180004000`
- `0x180004150`
- `0x1800041b0`
- `0x180004b50`
- `0x180014330`
- `0x180014e40`

## callees

- `0x180004df4`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180004e9e`
- `KERNEL32!SetLastError` at `0x180004e9e`
- `KERNEL32!GetLastError` at `0x180004e1a`
- `KERNEL32!GetLastError` at `0x180004e66`
- `KERNEL32!GetLastError` at `0x180004e1a`
- `KERNEL32!GetLastError` at `0x180004e66`

## string_xrefs

- `0x180004e36`: `onecore\base\Eco\WDS\wdslib\common\inc\Ldap.h`
- `0x180004e7f`: `onecore\base\Eco\WDS\wdslib\common\inc\Ldap.h`

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
        "onecore\\base\\Eco\\WDS\\wdslib\\common\\inc\\Ldap.h",
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
0x180004df4  mov     [rsp+arg_0], rbx
0x180004df9  mov     [rsp+arg_8], rsi
0x180004dfe  push    rdi
0x180004dff  sub     rsp, 40h
0x180004e03  mov     esi, r9d
0x180004e06  mov     edi, ecx
0x180004e08  test    ecx, ecx
0x180004e0a  jz      loc_180004EAA
0x180004e10  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180004e18  jz      short loc_180004E5C
0x180004e1a  call    cs:__imp_GetLastError
0x180004e21  nop     dword ptr [rax+rax+00h]
0x180004e26  lea     r9, dword_18003572C
0x180004e2d  mov     [rsp+48h+var_20], edi
0x180004e31  mov     [rsp+48h+var_28], r9
0x180004e36  lea     r8, aOnecoreBaseEco_13; "onecore\\base\\Eco\\WDS\\wdslib\\common"...
0x180004e3d  mov     ebx, eax
0x180004e3f  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180004e46  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180004e4d  mov     r9d, esi
0x180004e50  mov     ecx, 80000h
0x180004e55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e5a  jmp     short loc_180004E9C
0x180004e5c  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180004e64  jz      short loc_180004EAA
0x180004e66  call    cs:__imp_GetLastError
0x180004e6d  nop     dword ptr [rax+rax+00h]
0x180004e72  lea     r9, dword_18003572C
0x180004e79  mov     dword ptr [rsp+48h+var_28], edi
0x180004e7d  mov     ebx, eax
0x180004e7f  lea     rdx, aOnecoreBaseEco_13; "onecore\\base\\Eco\\WDS\\wdslib\\common"...
0x180004e86  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180004e8d  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180004e94  mov     r8d, esi
0x180004e97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e9c  mov     ecx, ebx; dwErrCode
0x180004e9e  call    cs:__imp_SetLastError
0x180004ea5  nop     dword ptr [rax+rax+00h]
0x180004eaa  mov     rbx, [rsp+48h+arg_0]
0x180004eaf  mov     eax, edi
0x180004eb1  mov     rsi, [rsp+48h+arg_8]
0x180004eb6  add     rsp, 40h
0x180004eba  pop     rdi
0x180004ebb  retn
```
