# ElValidateWin32_13

- ea: `0x180025d2c`
- end: `0x180025df5`
- name: `ElValidateWin32_13`
- size: `201`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180025f50`
- `0x180026080`

## callees

- `0x180025d2c`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180025dd6`
- `KERNEL32!SetLastError` at `0x180025dd6`
- `KERNEL32!GetLastError` at `0x180025d52`
- `KERNEL32!GetLastError` at `0x180025d9e`
- `KERNEL32!GetLastError` at `0x180025d52`
- `KERNEL32!GetLastError` at `0x180025d9e`

## string_xrefs

- `0x180025d6e`: `onecore\base\eco\wds\wdslib\common\src\setuputil.cpp`
- `0x180025db7`: `onecore\base\eco\wds\wdslib\common\src\setuputil.cpp`

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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\setuputil.cpp",
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
0x180025d2c  mov     [rsp+arg_0], rbx
0x180025d31  mov     [rsp+arg_8], rsi
0x180025d36  push    rdi
0x180025d37  sub     rsp, 40h
0x180025d3b  mov     esi, r9d
0x180025d3e  mov     edi, ecx
0x180025d40  test    ecx, ecx
0x180025d42  jz      loc_180025DE2
0x180025d48  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180025d50  jz      short loc_180025D94
0x180025d52  call    cs:__imp_GetLastError
0x180025d59  nop     dword ptr [rax+rax+00h]
0x180025d5e  lea     r9, dword_18003572C
0x180025d65  mov     [rsp+48h+var_20], edi
0x180025d69  mov     [rsp+48h+var_28], r9
0x180025d6e  lea     r8, aOnecoreBaseEco_34; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180025d75  mov     ebx, eax
0x180025d77  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180025d7e  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180025d85  mov     r9d, esi
0x180025d88  mov     ecx, 80000h
0x180025d8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d92  jmp     short loc_180025DD4
0x180025d94  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180025d9c  jz      short loc_180025DE2
0x180025d9e  call    cs:__imp_GetLastError
0x180025da5  nop     dword ptr [rax+rax+00h]
0x180025daa  lea     r9, dword_18003572C
0x180025db1  mov     dword ptr [rsp+48h+var_28], edi
0x180025db5  mov     ebx, eax
0x180025db7  lea     rdx, aOnecoreBaseEco_34; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180025dbe  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180025dc5  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180025dcc  mov     r8d, esi
0x180025dcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025dd4  mov     ecx, ebx; dwErrCode
0x180025dd6  call    cs:__imp_SetLastError
0x180025ddd  nop     dword ptr [rax+rax+00h]
0x180025de2  mov     rbx, [rsp+48h+arg_0]
0x180025de7  mov     eax, edi
0x180025de9  mov     rsi, [rsp+48h+arg_8]
0x180025dee  add     rsp, 40h
0x180025df2  pop     rdi
0x180025df3  retn
```
