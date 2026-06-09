# ElValidateHr_10

- ea: `0x1800287cc`
- end: `0x1800288b8`
- name: `ElValidateHr_10`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800283a0`

## callees

- `0x1800063c4`
- `0x1800287cc`
- `0x180030010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180028874`
- `KERNEL32!SetLastError` at `0x18002889e`
- `KERNEL32!SetLastError` at `0x180028874`
- `KERNEL32!SetLastError` at `0x18002889e`
- `KERNEL32!GetLastError` at `0x1800287ea`
- `KERNEL32!GetLastError` at `0x180028839`
- `KERNEL32!GetLastError` at `0x180028880`
- `KERNEL32!GetLastError` at `0x1800287ea`
- `KERNEL32!GetLastError` at `0x180028839`
- `KERNEL32!GetLastError` at `0x180028880`

## string_xrefs

- `0x180028806`: `onecore\base\eco\wds\wdslib\common\src\privilege.cpp`
- `0x180028852`: `onecore\base\eco\wds\wdslib\common\src\privilege.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateHr_10(int a1)
{
  DWORD LastError; // ebx
  DWORD v3; // ebx

  if ( a1 >= 0 )
    return (unsigned int)a1;
  if ( g_ErrLibTraceFunctionEx )
  {
    LastError = GetLastError();
    g_ErrLibTraceFunctionEx(
      0x80000u,
      L"[%S:%u] Expression: %S, hr=0x%x",
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\privilege.cpp",
      330,
      &dword_1800331C4,
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
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\privilege.cpp",
      330,
      &dword_1800331C4,
      a1);
    goto LABEL_6;
  }
LABEL_7:
  v3 = GetLastError();
  if ( (g_uErrLibFlags & 1) != 0 )
    ElTraceErrorInfo();
  SetLastError(v3);
  return (unsigned int)a1;
}

```

## disassembly

```asm
0x1800287cc  mov     [rsp+arg_0], rbx
0x1800287d1  push    rdi
0x1800287d2  sub     rsp, 40h
0x1800287d6  mov     edi, ecx
0x1800287d8  test    ecx, ecx
0x1800287da  jns     loc_1800288AA
0x1800287e0  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x1800287e8  jz      short loc_18002882F
0x1800287ea  call    cs:__imp_GetLastError
0x1800287f1  nop     dword ptr [rax+rax+00h]
0x1800287f6  lea     r9, dword_1800331C4
0x1800287fd  mov     [rsp+48h+var_20], edi
0x180028801  mov     [rsp+48h+var_28], r9
0x180028806  lea     r8, aOnecoreBaseEco_11; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18002880d  mov     ebx, eax
0x18002880f  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x180028816  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18002881d  mov     r9d, 14Ah
0x180028823  mov     ecx, 80000h
0x180028828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002882d  jmp     short loc_180028872
0x18002882f  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180028837  jz      short loc_180028880
0x180028839  call    cs:__imp_GetLastError
0x180028840  nop     dword ptr [rax+rax+00h]
0x180028845  lea     r9, dword_1800331C4
0x18002884c  mov     dword ptr [rsp+48h+var_28], edi
0x180028850  mov     ebx, eax
0x180028852  lea     rdx, aOnecoreBaseEco_11; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180028859  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180028860  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x180028867  mov     r8d, 14Ah
0x18002886d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028872  mov     ecx, ebx; dwErrCode
0x180028874  call    cs:__imp_SetLastError
0x18002887b  nop     dword ptr [rax+rax+00h]
0x180028880  call    cs:__imp_GetLastError
0x180028887  nop     dword ptr [rax+rax+00h]
0x18002888c  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x180028893  mov     ebx, eax
0x180028895  jz      short loc_18002889C
0x180028897  call    ElTraceErrorInfo
0x18002889c  mov     ecx, ebx; dwErrCode
0x18002889e  call    cs:__imp_SetLastError
0x1800288a5  nop     dword ptr [rax+rax+00h]
0x1800288aa  mov     rbx, [rsp+48h+arg_0]
0x1800288af  mov     eax, edi
0x1800288b1  add     rsp, 40h
0x1800288b5  pop     rdi
0x1800288b6  retn
```
