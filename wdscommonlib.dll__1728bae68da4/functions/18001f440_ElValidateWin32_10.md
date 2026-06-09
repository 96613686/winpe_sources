# ElValidateWin32_10

- ea: `0x18001f440`
- end: `0x18001f509`
- name: `ElValidateWin32_10`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001f2c0`

## callees

- `0x18001f440`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18001f4ea`
- `KERNEL32!SetLastError` at `0x18001f4ea`
- `KERNEL32!GetLastError` at `0x18001f466`
- `KERNEL32!GetLastError` at `0x18001f4b2`
- `KERNEL32!GetLastError` at `0x18001f466`
- `KERNEL32!GetLastError` at `0x18001f4b2`

## string_xrefs

- `0x18001f482`: `onecore\base\eco\wds\wdslib\common\src\ldapconnection.cpp`
- `0x18001f4cb`: `onecore\base\eco\wds\wdslib\common\src\ldapconnection.cpp`

## pseudocode

```c
__int64 __fastcall ElValidateWin32_10(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4)
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\ldapconnection.cpp",
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
        "onecore\\base\\eco\\wds\\wdslib\\common\\src\\ldapconnection.cpp",
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
0x18001f440  mov     [rsp+arg_0], rbx
0x18001f445  mov     [rsp+arg_8], rsi
0x18001f44a  push    rdi
0x18001f44b  sub     rsp, 40h
0x18001f44f  mov     esi, r9d
0x18001f452  mov     edi, ecx
0x18001f454  test    ecx, ecx
0x18001f456  jz      loc_18001F4F6
0x18001f45c  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001f464  jz      short loc_18001F4A8
0x18001f466  call    cs:__imp_GetLastError
0x18001f46d  nop     dword ptr [rax+rax+00h]
0x18001f472  lea     r9, dword_18003572C
0x18001f479  mov     [rsp+48h+var_20], edi
0x18001f47d  mov     [rsp+48h+var_28], r9
0x18001f482  lea     r8, aOnecoreBaseEco_5; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18001f489  mov     ebx, eax
0x18001f48b  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18001f492  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001f499  mov     r9d, esi
0x18001f49c  mov     ecx, 80000h
0x18001f4a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f4a6  jmp     short loc_18001F4E8
0x18001f4a8  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18001f4b0  jz      short loc_18001F4F6
0x18001f4b2  call    cs:__imp_GetLastError
0x18001f4b9  nop     dword ptr [rax+rax+00h]
0x18001f4be  lea     r9, dword_18003572C
0x18001f4c5  mov     dword ptr [rsp+48h+var_28], edi
0x18001f4c9  mov     ebx, eax
0x18001f4cb  lea     rdx, aOnecoreBaseEco_5; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18001f4d2  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18001f4d9  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x18001f4e0  mov     r8d, esi
0x18001f4e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f4e8  mov     ecx, ebx; dwErrCode
0x18001f4ea  call    cs:__imp_SetLastError
0x18001f4f1  nop     dword ptr [rax+rax+00h]
0x18001f4f6  mov     rbx, [rsp+48h+arg_0]
0x18001f4fb  mov     eax, edi
0x18001f4fd  mov     rsi, [rsp+48h+arg_8]
0x18001f502  add     rsp, 40h
0x18001f506  pop     rdi
0x18001f507  retn
```
