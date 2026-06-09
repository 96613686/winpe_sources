# ElValidateWin32_5

- ea: `0x1800154f8`
- end: `0x1800155c1`
- name: `ElValidateWin32_5`
- size: `201`
- prototype: ``
- caller_count: `18`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180013bd0`
- `0x180013c70`
- `0x180013d10`
- `0x180013e50`
- `0x180014090`
- `0x180014330`
- `0x180014500`
- `0x180014690`
- `0x180014870`
- `0x180014920`
- `0x1800149b0`
- `0x180014a20`
- `0x180014bc0`
- `0x180014c40`
- `0x180014d50`
- `0x180014e40`
- `0x180014fc0`
- `0x180015290`

## callees

- `0x1800154f8`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800155a2`
- `KERNEL32!SetLastError` at `0x1800155a2`
- `KERNEL32!GetLastError` at `0x18001551e`
- `KERNEL32!GetLastError` at `0x18001556a`
- `KERNEL32!GetLastError` at `0x18001551e`
- `KERNEL32!GetLastError` at `0x18001556a`

## string_xrefs

- `0x18001553a`: `onecore\base\eco\wds\wdslib\common\src\ldap.cpp`
- `0x180015583`: `onecore\base\eco\wds\wdslib\common\src\ldap.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_5(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\ldap.cpp",
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\ldap.cpp",
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
0x1800154f8  mov     [rsp+arg_0], rbx
0x1800154fd  mov     [rsp+arg_8], rsi
0x180015502  push    rdi
0x180015503  sub     rsp, 40h
0x180015507  mov     esi, r9d
0x18001550a  mov     edi, ecx
0x18001550c  test    ecx, ecx
0x18001550e  jz      loc_1800155AE
0x180015514  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001551c  jz      short loc_180015560
0x18001551e  call    cs:__imp_GetLastError
0x180015525  nop     dword ptr [rax+rax+00h]
0x18001552a  lea     r9, dword_18003572C
0x180015531  mov     [rsp+48h+var_20], edi
0x180015535  mov     [rsp+48h+var_28], r9
0x18001553a  lea     r8, aOnecoreBaseEco_14; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180015541  mov     ebx, eax
0x180015543  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18001554a  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180015551  mov     r9d, esi
0x180015554  mov     ecx, 80000h
0x180015559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001555e  jmp     short loc_1800155A0
0x180015560  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180015568  jz      short loc_1800155AE
0x18001556a  call    cs:__imp_GetLastError
0x180015571  nop     dword ptr [rax+rax+00h]
0x180015576  lea     r9, dword_18003572C
0x18001557d  mov     dword ptr [rsp+48h+var_28], edi
0x180015581  mov     ebx, eax
0x180015583  lea     rdx, aOnecoreBaseEco_14; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18001558a  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180015591  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180015598  mov     r8d, esi
0x18001559b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155a0  mov     ecx, ebx; dwErrCode
0x1800155a2  call    cs:__imp_SetLastError
0x1800155a9  nop     dword ptr [rax+rax+00h]
0x1800155ae  mov     rbx, [rsp+48h+arg_0]
0x1800155b3  mov     eax, edi
0x1800155b5  mov     rsi, [rsp+48h+arg_8]
0x1800155ba  add     rsp, 40h
0x1800155be  pop     rdi
0x1800155bf  retn
```
