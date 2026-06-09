# SxspParseUSHORT(ushort const *,unsigned __int64,ushort *)

- ea: `0x180037c74`
- end: `0x180037d8c`
- name: `?SxspParseUSHORT@@YAHPEBG_KPEAG@Z`
- size: `280`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800358d0`

## callees

- `0x18000c000`
- `0x18000df40`
- `0x18001c270`
- `0x180037c74`
- `0x18005d2b0`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037cf1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037d4b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037cf1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037d4b`

## string_xrefs

- `0x180037d35`: `SXS.DLL: Error parsing 16-bit unsigned short integer; character other than 0-9 found\n`

## pseudocode

```c
__int64 __fastcall SxspParseUSHORT(const unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3)
{
  const char *v6; // rcx
  unsigned __int16 v7; // cx
  __int16 v8; // dx
  unsigned int v9; // ebx
  int v11; // [rsp+20h] [rbp-48h] BYREF
  int v12; // [rsp+28h] [rbp-40h] BYREF
  __int64 v13; // [rsp+30h] [rbp-38h]
  __int64 *v14; // [rsp+38h] [rbp-30h]
  __int64 v15; // [rsp+40h] [rbp-28h]
  int v16; // [rsp+48h] [rbp-20h]
  int *v17; // [rsp+50h] [rbp-18h]

  v11 = 0;
  v14 = &qword_180070330;
  v12 = 1;
  v17 = &v11;
  v13 = 0;
  v15 = 544438355;
  v16 = 2585;
  CFrame::BaseEnter((CFrame *)&v12);
  if ( a1 || !a2 )
  {
    v7 = 0;
    while ( a2 )
    {
      v8 = *a1;
      if ( (unsigned __int16)(*a1 - 48) > 9u )
      {
        FusionpDbgPrintEx(
          0xC0000000,
          "SXS.DLL: Error parsing 16-bit unsigned short integer; character other than 0-9 found\n");
        SetLastError(0x36B5u);
        goto LABEL_12;
      }
      ++a1;
      v7 = v8 + 10 * v7 - 48;
      --a2;
    }
    if ( a3 )
      *a3 = v7;
    v11 = 1;
  }
  else
  {
    v16 = 2588;
    FusionpTraceParameterCheck(v6);
    SetLastError(0x57u);
    *v17 = 0;
  }
LABEL_12:
  v9 = v11;
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v12);
  return v9;
}

```

## disassembly

```asm
0x180037c74  push    rbp
0x180037c76  push    rbx
0x180037c77  push    rsi
0x180037c78  push    rdi
0x180037c79  mov     rbp, rsp
0x180037c7c  sub     rsp, 68h
0x180037c80  mov     rax, cs:__security_cookie
0x180037c87  xor     rax, rsp
0x180037c8a  mov     [rbp+var_10], rax
0x180037c8e  lea     rax, qword_180070330
0x180037c95  mov     [rbp+var_48], 0
0x180037c9c  mov     [rbp+var_30], rax
0x180037ca0  mov     rsi, rcx
0x180037ca3  lea     rax, [rbp+var_48]
0x180037ca7  mov     [rbp+var_40], 1
0x180037cae  lea     rcx, [rbp+var_40]; this
0x180037cb2  mov     [rbp+var_18], rax
0x180037cb6  mov     rdi, r8
0x180037cb9  mov     [rbp+var_38], 0
0x180037cc1  mov     rbx, rdx
0x180037cc4  mov     [rbp+var_28], 20737853h
0x180037ccc  mov     [rbp+var_20], 0A19h
0x180037cd3  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180037cd8  test    rsi, rsi
0x180037cdb  jnz     short loc_180037D05
0x180037cdd  test    rbx, rbx
0x180037ce0  jz      short loc_180037D05
0x180037ce2  mov     [rbp+var_20], 0A1Ch
0x180037ce9  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x180037cee  lea     ecx, [rsi+57h]; dwErrCode
0x180037cf1  call    cs:__imp_SetLastError
0x180037cf8  nop     dword ptr [rax+rax+00h]
0x180037cfd  mov     rax, [rbp+var_18]
0x180037d01  mov     [rax], esi
0x180037d03  jmp     short loc_180037D68
0x180037d05  xor     ecx, ecx
0x180037d07  test    rbx, rbx
0x180037d0a  jz      short loc_180037D59
0x180037d0c  movzx   edx, word ptr [rsi]
0x180037d0f  lea     eax, [rdx-30h]
0x180037d12  cmp     ax, 9
0x180037d16  ja      short loc_180037D35
0x180037d18  movzx   eax, cx
0x180037d1b  add     rsi, 2
0x180037d1f  shl     ax, 2
0x180037d23  add     cx, ax
0x180037d26  add     cx, cx
0x180037d29  sub     cx, 30h ; '0'
0x180037d2d  add     cx, dx
0x180037d30  dec     rbx
0x180037d33  jmp     short loc_180037D07
0x180037d35  lea     rdx, aSxsDllErrorPar; "SXS.DLL: Error parsing 16-bit unsigned "...
0x180037d3c  mov     ecx, 0C0000000h; unsigned int
0x180037d41  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x180037d46  mov     ecx, 36B5h; dwErrCode
0x180037d4b  call    cs:__imp_SetLastError
0x180037d52  nop     dword ptr [rax+rax+00h]
0x180037d57  jmp     short loc_180037D68
0x180037d59  test    rdi, rdi
0x180037d5c  jz      short loc_180037D61
0x180037d5e  mov     [rdi], cx
0x180037d61  mov     [rbp+var_48], 1
0x180037d68  mov     ebx, [rbp+var_48]
0x180037d6b  lea     rcx, [rbp+var_40]; this
0x180037d6f  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x180037d74  mov     eax, ebx
0x180037d76  mov     rcx, [rbp+var_10]
0x180037d7a  xor     rcx, rsp; StackCookie
0x180037d7d  call    __security_check_cookie
0x180037d82  add     rsp, 68h
0x180037d86  pop     rdi
0x180037d87  pop     rsi
0x180037d88  pop     rbx
0x180037d89  pop     rbp
0x180037d8a  retn
```
