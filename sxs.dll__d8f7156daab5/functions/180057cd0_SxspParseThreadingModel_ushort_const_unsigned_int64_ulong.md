# SxspParseThreadingModel(ushort const *,unsigned __int64,ulong *)

- ea: `0x180057cd0`
- end: `0x180057ddf`
- name: `?SxspParseThreadingModel@@YAHPEBG_KPEAK@Z`
- size: `271`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002a70`

## callees

- `0x18000c000`
- `0x18000df40`
- `0x180013150`
- `0x18001c270`
- `0x180057cd0`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180057dce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180057dce`

## string_xrefs

- `0x180057db8`: `SXS.DLL: Invalid threading model string\n`

## pseudocode

```c
__int64 __fastcall SxspParseThreadingModel(WCHAR *a1, __int16 a2, unsigned int *a3)
{
  unsigned int v4; // ebx
  unsigned int i; // edi
  __int64 v8; // r14
  int v10; // [rsp+30h] [rbp-40h] BYREF
  int v11; // [rsp+38h] [rbp-38h] BYREF
  __int64 v12; // [rsp+40h] [rbp-30h]
  __int64 *v13; // [rsp+48h] [rbp-28h]
  __int64 v14; // [rsp+50h] [rbp-20h]
  int v15; // [rsp+58h] [rbp-18h]
  int *v16; // [rsp+60h] [rbp-10h]

  v10 = 0;
  v13 = &qword_180072A70;
  v12 = 0;
  v4 = 1;
  v16 = &v10;
  v11 = 1;
  v14 = 544438355;
  v15 = 120;
  CFrame::BaseEnter((CFrame *)&v11);
  for ( i = 0; i < 5; ++i )
  {
    v8 = 4LL * i;
    if ( !FusionpCompareStrings((WCHAR *)&qword_1800886A0[v8] + 2, qword_1800886A0[v8 + 3], a1, a2, 1u) )
    {
      if ( a3 )
        *a3 = qword_1800886A0[v8];
      goto LABEL_7;
    }
  }
  if ( i != 5 )
  {
LABEL_7:
    v10 = 1;
    goto LABEL_8;
  }
  FusionpDbgPrintEx(0xC0000000, "SXS.DLL: Invalid threading model string\n");
  SetLastError(0x36B5u);
  v4 = v10;
LABEL_8:
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v11);
  return v4;
}

```

## disassembly

```asm
0x180057cd0  mov     [rsp-38h+arg_18], rbx
0x180057cd5  push    rbp
0x180057cd6  push    rsi
0x180057cd7  push    rdi
0x180057cd8  push    r12
0x180057cda  push    r13
0x180057cdc  push    r14
0x180057cde  push    r15
0x180057ce0  mov     rbp, rsp
0x180057ce3  sub     rsp, 70h
0x180057ce7  mov     rax, cs:__security_cookie
0x180057cee  xor     rax, rsp
0x180057cf1  mov     [rbp+var_8], rax
0x180057cf5  lea     rax, qword_180072A70
0x180057cfc  mov     [rbp+var_40], 0
0x180057d03  mov     [rbp+var_28], rax
0x180057d07  mov     r15, rcx
0x180057d0a  lea     rax, [rbp+var_40]
0x180057d0e  mov     [rbp+var_30], 0
0x180057d16  mov     ebx, 1
0x180057d1b  mov     [rbp+var_10], rax
0x180057d1f  lea     rcx, [rbp+var_38]; this
0x180057d23  mov     [rbp+var_38], ebx
0x180057d26  mov     rsi, r8
0x180057d29  mov     [rbp+var_20], 20737853h
0x180057d31  mov     r12, rdx
0x180057d34  mov     [rbp+var_18], 78h ; 'x'
0x180057d3b  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180057d40  xor     edi, edi
0x180057d42  lea     r13, qword_1800886A0
0x180057d49  cmp     edi, 5
0x180057d4c  jnb     short loc_180057DB6
0x180057d4e  mov     r14d, edi
0x180057d51  lea     rcx, [r13+4]
0x180057d55  shl     r14, 5
0x180057d59  mov     r9, r12; unsigned __int64
0x180057d5c  add     rcx, r14; unsigned __int16 *
0x180057d5f  mov     [rsp+70h+var_50], bl; bool
0x180057d63  mov     r8, r15; unsigned __int16 *
0x180057d66  mov     rdx, [r14+r13+18h]; unsigned __int64
0x180057d6b  call    ?FusionpCompareStrings@@YAHPEBG_K01_N@Z; FusionpCompareStrings(ushort const *,unsigned __int64,ushort const *,unsigned __int64,bool)
0x180057d70  test    eax, eax
0x180057d72  jz      short loc_180057D78
0x180057d74  add     edi, ebx
0x180057d76  jmp     short loc_180057D49
0x180057d78  test    rsi, rsi
0x180057d7b  jz      short loc_180057D83
0x180057d7d  mov     eax, [r14+r13]
0x180057d81  mov     [rsi], eax
0x180057d83  mov     [rbp+var_40], ebx
0x180057d86  lea     rcx, [rbp+var_38]; this
0x180057d8a  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x180057d8f  mov     eax, ebx
0x180057d91  mov     rcx, [rbp+var_8]
0x180057d95  xor     rcx, rsp; StackCookie
0x180057d98  call    __security_check_cookie
0x180057d9d  mov     rbx, [rsp+70h+arg_18]
0x180057da5  add     rsp, 70h
0x180057da9  pop     r15
0x180057dab  pop     r14
0x180057dad  pop     r13
0x180057daf  pop     r12
0x180057db1  pop     rdi
0x180057db2  pop     rsi
0x180057db3  pop     rbp
0x180057db4  retn
0x180057db6  jnz     short loc_180057D83
0x180057db8  lea     rdx, aSxsDllInvalidT; "SXS.DLL: Invalid threading model string"...
0x180057dbf  mov     ecx, 0C0000000h; unsigned int
0x180057dc4  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x180057dc9  mov     ecx, 36B5h; dwErrCode
0x180057dce  call    cs:__imp_SetLastError
0x180057dd5  nop     dword ptr [rax+rax+00h]
0x180057dda  mov     ebx, [rbp+var_40]
0x180057ddd  jmp     short loc_180057D86
```
