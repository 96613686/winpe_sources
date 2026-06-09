# ElValidateHr_10

- ea: `0x180029938`
- end: `0x180029a24`
- name: `ElValidateHr_10`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180029500`

## callees

- `0x180006ea4`
- `0x180029938`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800299e0`
- `KERNEL32!SetLastError` at `0x180029a0a`
- `KERNEL32!SetLastError` at `0x1800299e0`
- `KERNEL32!SetLastError` at `0x180029a0a`
- `KERNEL32!GetLastError` at `0x180029956`
- `KERNEL32!GetLastError` at `0x1800299a5`
- `KERNEL32!GetLastError` at `0x1800299ec`
- `KERNEL32!GetLastError` at `0x180029956`
- `KERNEL32!GetLastError` at `0x1800299a5`
- `KERNEL32!GetLastError` at `0x1800299ec`

## string_xrefs

- `0x180029972`: `onecore\base\eco\wds\wdslib\common\src\privilege.cpp`
- `0x1800299be`: `onecore\base\eco\wds\wdslib\common\src\privilege.cpp`

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
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\privilege.cpp",
      330,
      &dword_18003572C,
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
0x180029938  mov     [rsp+arg_0], rbx
0x18002993d  push    rdi
0x18002993e  sub     rsp, 40h
0x180029942  mov     edi, ecx
0x180029944  test    ecx, ecx
0x180029946  jns     loc_180029A16
0x18002994c  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180029954  jz      short loc_18002999B
0x180029956  call    cs:__imp_GetLastError
0x18002995d  nop     dword ptr [rax+rax+00h]
0x180029962  lea     r9, dword_18003572C
0x180029969  mov     [rsp+48h+var_20], edi
0x18002996d  mov     [rsp+48h+var_28], r9
0x180029972  lea     r8, aOnecoreBaseEco_11; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180029979  mov     ebx, eax
0x18002997b  lea     rdx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x180029982  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180029989  mov     r9d, 14Ah
0x18002998f  mov     ecx, 80000h
0x180029994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029999  jmp     short loc_1800299DE
0x18002999b  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800299a3  jz      short loc_1800299EC
0x1800299a5  call    cs:__imp_GetLastError
0x1800299ac  nop     dword ptr [rax+rax+00h]
0x1800299b1  lea     r9, dword_18003572C
0x1800299b8  mov     dword ptr [rsp+48h+var_28], edi
0x1800299bc  mov     ebx, eax
0x1800299be  lea     rdx, aOnecoreBaseEco_11; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x1800299c5  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800299cc  lea     rcx, aSUExpressionSH; "[%S:%u] Expression: %S, hr=0x%x"
0x1800299d3  mov     r8d, 14Ah
0x1800299d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800299de  mov     ecx, ebx; dwErrCode
0x1800299e0  call    cs:__imp_SetLastError
0x1800299e7  nop     dword ptr [rax+rax+00h]
0x1800299ec  call    cs:__imp_GetLastError
0x1800299f3  nop     dword ptr [rax+rax+00h]
0x1800299f8  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x1800299ff  mov     ebx, eax
0x180029a01  jz      short loc_180029A08
0x180029a03  call    ElTraceErrorInfo
0x180029a08  mov     ecx, ebx; dwErrCode
0x180029a0a  call    cs:__imp_SetLastError
0x180029a11  nop     dword ptr [rax+rax+00h]
0x180029a16  mov     rbx, [rsp+48h+arg_0]
0x180029a1b  mov     eax, edi
0x180029a1d  add     rsp, 40h
0x180029a21  pop     rdi
0x180029a22  retn
```
