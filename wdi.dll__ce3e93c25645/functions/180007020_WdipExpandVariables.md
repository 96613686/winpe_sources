# WdipExpandVariables

- ea: `0x180007020`
- end: `0x180007156`
- name: `WdipExpandVariables`
- size: `310`
- prototype: `__int64 __fastcall(_WORD *, unsigned __int64, const WCHAR *)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003420`
- `0x18000b980`
- `0x18000bcd0`
- `0x18000c390`
- `0x18000c610`

## callees

- `0x180002ba0`
- `0x180007020`
- `0x18000f1f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007065`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007065`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000705b`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000705b`

## string_xrefs

- `0x180007109`: `clientcore\base\diagnosis\pdi\wdi\framework\common\utils.cpp`

## pseudocode

```c
__int64 __fastcall WdipExpandVariables(_WORD *a1, unsigned __int64 a2, const WCHAR *a3)
{
  signed int LastError; // eax
  signed int v6; // esi
  char Args; // cl
  int v8; // r8d
  __int64 result; // rax
  __int64 v10; // rax
  WCHAR *v11; // rcx
  _WORD *v12; // rax
  WCHAR Dst[1024]; // [rsp+30h] [rbp-818h] BYREF

  if ( ExpandEnvironmentStringsW(a3, Dst, 0x400u) )
    goto LABEL_6;
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( v6 >= 0 )
  {
LABEL_6:
    if ( a2 )
    {
      if ( a2 > 0x7FFFFFFF )
      {
        v6 = -2147024809;
        LOBYTE(result) = 87;
        *a1 = 0;
LABEL_18:
        Args = result;
        v8 = 140;
        goto LABEL_19;
      }
      v10 = 2147483646;
      v11 = Dst;
      do
      {
        if ( !v10 )
          break;
        if ( !*v11 )
          break;
        *a1++ = *v11++;
        --v10;
        --a2;
      }
      while ( a2 );
      v12 = a1 - 1;
      if ( a2 )
        v12 = a1;
      *v12 = 0;
      result = 2147942522LL;
      if ( a2 )
        result = 0;
    }
    else
    {
      result = 2147942487LL;
    }
    v6 = result;
    if ( (int)result >= 0 )
      return result;
    goto LABEL_18;
  }
  Args = v6;
  v8 = 137;
LABEL_19:
  WdipTraceError(
    (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\utils.cpp",
    (int)L"WdipExpandVariables",
    v8,
    (int)L"Error = %d",
    Args);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180007020  mov     [rsp+arg_8], rbx
0x180007025  mov     [rsp+arg_18], rsi
0x18000702a  push    rdi
0x18000702b  sub     rsp, 840h
0x180007032  mov     rax, cs:__security_cookie
0x180007039  xor     rax, rsp
0x18000703c  mov     [rsp+848h+var_18], rax
0x180007044  mov     rax, r8
0x180007047  mov     rbx, rdx
0x18000704a  mov     rdi, rcx
0x18000704d  lea     rdx, [rsp+848h+Dst]; lpDst
0x180007052  mov     rcx, rax; lpSrc
0x180007055  mov     r8d, 400h; nSize
0x18000705b  call    cs:__imp_ExpandEnvironmentStringsW
0x180007061  test    eax, eax
0x180007063  jnz     short loc_180007089
0x180007065  call    cs:__imp_GetLastError
0x18000706b  mov     esi, eax
0x18000706d  test    eax, eax
0x18000706f  jle     short loc_18000707A
0x180007071  movzx   esi, ax
0x180007074  or      esi, 80070000h
0x18000707a  test    esi, esi
0x18000707c  jns     short loc_180007089
0x18000707e  movzx   ecx, si
0x180007081  mov     r8d, 89h
0x180007087  jmp     short loc_1800070FE
0x180007089  test    rbx, rbx
0x18000708c  jz      loc_180007143
0x180007092  cmp     rbx, 7FFFFFFFh
0x180007099  jbe     short loc_1800070A9
0x18000709b  mov     esi, 80070057h
0x1800070a0  xor     ecx, ecx
0x1800070a2  mov     eax, esi
0x1800070a4  mov     [rdi], cx
0x1800070a7  jmp     short loc_1800070F5
0x1800070a9  mov     eax, 7FFFFFFEh
0x1800070ae  lea     rcx, [rsp+848h+Dst]
0x1800070b3  test    rax, rax
0x1800070b6  jz      short loc_1800070D4
0x1800070b8  movzx   edx, word ptr [rcx]
0x1800070bb  test    dx, dx
0x1800070be  jz      short loc_1800070D4
0x1800070c0  mov     [rdi], dx
0x1800070c3  add     rcx, 2
0x1800070c7  add     rdi, 2
0x1800070cb  dec     rax
0x1800070ce  sub     rbx, 1
0x1800070d2  jnz     short loc_1800070B3
0x1800070d4  test    rbx, rbx
0x1800070d7  lea     rax, [rdi-2]
0x1800070db  cmovnz  rax, rdi
0x1800070df  xor     ecx, ecx
0x1800070e1  test    rbx, rbx
0x1800070e4  mov     [rax], cx
0x1800070e7  mov     eax, 8007007Ah
0x1800070ec  cmovnz  eax, ecx
0x1800070ef  mov     esi, eax
0x1800070f1  test    eax, eax
0x1800070f3  jns     short loc_18000711E
0x1800070f5  movzx   ecx, ax
0x1800070f8  mov     r8d, 8Ch; int
0x1800070fe  mov     dword ptr [rsp+848h+Args], ecx; Args
0x180007102  lea     r9, aErrorD_0; "Error = %d"
0x180007109  lea     rcx, aClientcoreBase_0; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180007110  lea     rdx, aWdipexpandvari; "WdipExpandVariables"
0x180007117  call    WdipTraceError
0x18000711c  mov     eax, esi
0x18000711e  mov     rcx, [rsp+848h+var_18]
0x180007126  xor     rcx, rsp; StackCookie
0x180007129  call    __security_check_cookie
0x18000712e  lea     r11, [rsp+848h+var_8]
0x180007136  mov     rbx, [r11+18h]
0x18000713a  mov     rsi, [r11+28h]
0x18000713e  mov     rsp, r11
0x180007141  pop     rdi
0x180007142  retn
0x180007143  mov     esi, 80070057h
0x180007148  mov     eax, esi
0x18000714a  test    rbx, rbx
0x18000714d  jz      short loc_1800070EF
0x18000714f  xor     ecx, ecx
0x180007151  mov     [rdi], cx
0x180007154  jmp     short loc_1800070F5
```
