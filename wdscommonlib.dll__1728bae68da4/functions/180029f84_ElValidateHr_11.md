# ElValidateHr_11

- ea: `0x180029f84`
- end: `0x18002a077`
- name: `ElValidateHr_11`
- size: `243`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180029b00`
- `0x180029e80`

## callees

- `0x180006ea4`
- `0x180029f84`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18002a02e`
- `KERNEL32!SetLastError` at `0x18002a058`
- `KERNEL32!SetLastError` at `0x18002a02e`
- `KERNEL32!SetLastError` at `0x18002a058`
- `KERNEL32!GetLastError` at `0x180029faa`
- `KERNEL32!GetLastError` at `0x180029ff6`
- `KERNEL32!GetLastError` at `0x18002a03a`
- `KERNEL32!GetLastError` at `0x180029faa`
- `KERNEL32!GetLastError` at `0x180029ff6`
- `KERNEL32!GetLastError` at `0x18002a03a`

## string_xrefs

- `0x180029fc6`: `onecore\base\eco\wds\wdslib\common\src\langpacks.cpp`
- `0x18002a00f`: `onecore\base\eco\wds\wdslib\common\src\langpacks.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateHr_11(int a1, __int64 a2, __int64 a3, unsigned int a4)
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
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\langpacks.cpp",
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
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\langpacks.cpp",
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
0x180029f84  mov     [rsp+arg_0], rbx
0x180029f89  mov     [rsp+arg_8], rsi
0x180029f8e  push    rdi
0x180029f8f  sub     rsp, 40h
0x180029f93  mov     esi, r9d
0x180029f96  mov     edi, ecx
0x180029f98  test    ecx, ecx
0x180029f9a  jns     loc_18002A064
0x180029fa0  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180029fa8  jz      short loc_180029FEC
0x180029faa  call    cs:__imp_GetLastError
0x180029fb1  nop     dword ptr [rax+rax+00h]
0x180029fb6  lea     r9, dword_18003572C
0x180029fbd  mov     [rsp+48h+var_20], edi
0x180029fc1  mov     [rsp+48h+var_28], r9
0x180029fc6  lea     r8, aOnecoreBaseEco_25; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180029fcd  mov     ebx, eax
0x180029fcf  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x180029fd6  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180029fdd  mov     r9d, esi
0x180029fe0  mov     ecx, 80000h
0x180029fe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029fea  jmp     short loc_18002A02C
0x180029fec  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180029ff4  jz      short loc_18002A03A
0x180029ff6  call    cs:__imp_GetLastError
0x180029ffd  nop     dword ptr [rax+rax+00h]
0x18002a002  lea     r9, dword_18003572C
0x18002a009  mov     dword ptr [rsp+48h+var_28], edi
0x18002a00d  mov     ebx, eax
0x18002a00f  lea     rdx, aOnecoreBaseEco_25; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18002a016  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18002a01d  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x18002a024  mov     r8d, esi
0x18002a027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a02c  mov     ecx, ebx; dwErrCode
0x18002a02e  call    cs:__imp_SetLastError
0x18002a035  nop     dword ptr [rax+rax+00h]
0x18002a03a  call    cs:__imp_GetLastError
0x18002a041  nop     dword ptr [rax+rax+00h]
0x18002a046  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x18002a04d  mov     ebx, eax
0x18002a04f  jz      short loc_18002A056
0x18002a051  call    ElTraceErrorInfo
0x18002a056  mov     ecx, ebx; dwErrCode
0x18002a058  call    cs:__imp_SetLastError
0x18002a05f  nop     dword ptr [rax+rax+00h]
0x18002a064  mov     rbx, [rsp+48h+arg_0]
0x18002a069  mov     eax, edi
0x18002a06b  mov     rsi, [rsp+48h+arg_8]
0x18002a070  add     rsp, 40h
0x18002a074  pop     rdi
0x18002a075  retn
```
