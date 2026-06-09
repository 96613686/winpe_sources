# ElValidateHr_0

- ea: `0x180008878`
- end: `0x18000896b`
- name: `ElValidateHr_0`
- size: `243`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180007310`
- `0x180007f80`
- `0x1800082c0`
- `0x1800086f0`

## callees

- `0x180006ea4`
- `0x180008878`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180008922`
- `KERNEL32!SetLastError` at `0x18000894c`
- `KERNEL32!SetLastError` at `0x180008922`
- `KERNEL32!SetLastError` at `0x18000894c`
- `KERNEL32!GetLastError` at `0x18000889e`
- `KERNEL32!GetLastError` at `0x1800088ea`
- `KERNEL32!GetLastError` at `0x18000892e`
- `KERNEL32!GetLastError` at `0x18000889e`
- `KERNEL32!GetLastError` at `0x1800088ea`
- `KERNEL32!GetLastError` at `0x18000892e`

## string_xrefs

- `0x1800088ba`: `onecore\base\eco\wds\wdslib\common\src\wdscommon.cpp`
- `0x180008903`: `onecore\base\eco\wds\wdslib\common\src\wdscommon.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateHr_0(int a1, __int64 a2, __int64 a3, unsigned int a4)
{
  DWORD LastError; // ebx
  DWORD v7; // ebx

  if ( a1 >= 0 )
    return (unsigned int)a1;
  if ( g_ErrLibTraceFunctionEx )
  {
    LastError = GetLastError();
    g_ErrLibTraceFunctionEx(
      0x80000u,
      L"[%S:%u] Expression: %S, hr=0x%x",
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\wdscommon.cpp",
      a4,
      &dword_18003572C,
      a1);
LABEL_6:
    SetLastError(LastError);
    goto LABEL_7;
  }
  if ( g_ErrLibTraceFunction )
  {
    LastError = GetLastError();
    g_ErrLibTraceFunction(
      L"[%S:%u] Expression: %S, hr=0x%x",
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\wdscommon.cpp",
      a4,
      &dword_18003572C,
      a1);
    goto LABEL_6;
  }
LABEL_7:
  v7 = GetLastError();
  if ( (g_uErrLibFlags & 1) != 0 )
    ElTraceErrorInfo();
  SetLastError(v7);
  return (unsigned int)a1;
}

```

## disassembly

```asm
0x180008878  mov     [rsp+arg_0], rbx
0x18000887d  mov     [rsp+arg_8], rsi
0x180008882  push    rdi
0x180008883  sub     rsp, 40h
0x180008887  mov     esi, r9d
0x18000888a  mov     edi, ecx
0x18000888c  test    ecx, ecx
0x18000888e  jns     loc_180008958
0x180008894  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000889c  jz      short loc_1800088E0
0x18000889e  call    cs:__imp_GetLastError
0x1800088a5  nop     dword ptr [rax+rax+00h]
0x1800088aa  lea     r9, dword_18003572C
0x1800088b1  mov     [rsp+48h+var_20], edi
0x1800088b5  mov     [rsp+48h+var_28], r9
0x1800088ba  lea     r8, aOnecoreBaseEco_17; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x1800088c1  mov     ebx, eax
0x1800088c3  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x1800088ca  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800088d1  mov     r9d, esi
0x1800088d4  mov     ecx, 80000h
0x1800088d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088de  jmp     short loc_180008920
0x1800088e0  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800088e8  jz      short loc_18000892E
0x1800088ea  call    cs:__imp_GetLastError
0x1800088f1  nop     dword ptr [rax+rax+00h]
0x1800088f6  lea     r9, dword_18003572C
0x1800088fd  mov     dword ptr [rsp+48h+var_28], edi
0x180008901  mov     ebx, eax
0x180008903  lea     rdx, aOnecoreBaseEco_17; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18000890a  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180008911  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x180008918  mov     r8d, esi
0x18000891b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008920  mov     ecx, ebx; dwErrCode
0x180008922  call    cs:__imp_SetLastError
0x180008929  nop     dword ptr [rax+rax+00h]
0x18000892e  call    cs:__imp_GetLastError
0x180008935  nop     dword ptr [rax+rax+00h]
0x18000893a  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x180008941  mov     ebx, eax
0x180008943  jz      short loc_18000894A
0x180008945  call    ElTraceErrorInfo
0x18000894a  mov     ecx, ebx; dwErrCode
0x18000894c  call    cs:__imp_SetLastError
0x180008953  nop     dword ptr [rax+rax+00h]
0x180008958  mov     rbx, [rsp+48h+arg_0]
0x18000895d  mov     eax, edi
0x18000895f  mov     rsi, [rsp+48h+arg_8]
0x180008964  add     rsp, 40h
0x180008968  pop     rdi
0x180008969  retn
```
