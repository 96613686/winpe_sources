# ElValidateWin32_2

- ea: `0x18000ead4`
- end: `0x18000eb96`
- name: `ElValidateWin32_2`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a4f0`

## callees

- `0x18000ead4`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000eb7c`
- `KERNEL32!SetLastError` at `0x18000eb7c`
- `KERNEL32!GetLastError` at `0x18000eaf2`
- `KERNEL32!GetLastError` at `0x18000eb41`
- `KERNEL32!GetLastError` at `0x18000eaf2`
- `KERNEL32!GetLastError` at `0x18000eb41`

## string_xrefs

- `0x18000eb0e`: `onecore\base\eco\wds\wdslib\common\src\bufferpool.cpp`
- `0x18000eb5a`: `onecore\base\eco\wds\wdslib\common\src\bufferpool.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_2(unsigned int a1)
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\bufferpool.cpp",
        177,
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\bufferpool.cpp",
        177,
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
0x18000ead4  mov     [rsp+arg_0], rbx
0x18000ead9  push    rdi
0x18000eada  sub     rsp, 40h
0x18000eade  mov     edi, ecx
0x18000eae0  test    ecx, ecx
0x18000eae2  jz      loc_18000EB88
0x18000eae8  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000eaf0  jz      short loc_18000EB37
0x18000eaf2  call    cs:__imp_GetLastError
0x18000eaf9  nop     dword ptr [rax+rax+00h]
0x18000eafe  lea     r9, dword_18003572C
0x18000eb05  mov     [rsp+48h+var_20], edi
0x18000eb09  mov     [rsp+48h+var_28], r9
0x18000eb0e  lea     r8, aOnecoreBaseEco_29; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18000eb15  mov     ebx, eax
0x18000eb17  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18000eb1e  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000eb25  mov     r9d, 0B1h
0x18000eb2b  mov     ecx, 80000h
0x18000eb30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb35  jmp     short loc_18000EB7A
0x18000eb37  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000eb3f  jz      short loc_18000EB88
0x18000eb41  call    cs:__imp_GetLastError
0x18000eb48  nop     dword ptr [rax+rax+00h]
0x18000eb4d  lea     r9, dword_18003572C
0x18000eb54  mov     dword ptr [rsp+48h+var_28], edi
0x18000eb58  mov     ebx, eax
0x18000eb5a  lea     rdx, aOnecoreBaseEco_29; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18000eb61  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000eb68  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18000eb6f  mov     r8d, 0B1h
0x18000eb75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb7a  mov     ecx, ebx; dwErrCode
0x18000eb7c  call    cs:__imp_SetLastError
0x18000eb83  nop     dword ptr [rax+rax+00h]
0x18000eb88  mov     rbx, [rsp+48h+arg_0]
0x18000eb8d  mov     eax, edi
0x18000eb8f  add     rsp, 40h
0x18000eb93  pop     rdi
0x18000eb94  retn
```
