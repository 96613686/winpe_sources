# SxspParseMiscStatusFlags(ulong &,ushort const *,unsigned __int64)

- ea: `0x18005a6bc`
- end: `0x18005a856`
- name: `?SxspParseMiscStatusFlags@@YAHAEAKPEBG_K@Z`
- size: `410`
- prototype: `int(unsigned int *, const unsigned __int16 *, unsigned __int64)`
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
- `0x18005a6bc`
- `0x18006a110`

## import_xrefs

- `ntdll!wcschr` at `0x18005a747`
- `ntdll!wcschr` at `0x18005a747`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a7e4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a80a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a7e4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a80a`

## string_xrefs

- `0x18005a7ce`: `SXS.DLL: Redundant OLEMISC flags\n`
- `0x18005a7fb`: `SXS.DLL: Invalid OLEMISC flags\n`
- `0x18005a7f2`: `SXS.DLL: Trailing comma in OLEMISC flag string\n`

## pseudocode

```c
__int64 __fastcall SxspParseMiscStatusFlags(unsigned int *a1, wchar_t *a2, __int64 a3)
{
  unsigned int v6; // r15d
  wchar_t *v7; // rax
  __int64 v8; // rdi
  unsigned __int64 i; // rsi
  unsigned int v10; // ebx
  int v12; // [rsp+30h] [rbp-40h] BYREF
  int v13; // [rsp+38h] [rbp-38h] BYREF
  __int64 v14; // [rsp+40h] [rbp-30h]
  __int64 *v15; // [rsp+48h] [rbp-28h]
  __int64 v16; // [rsp+50h] [rbp-20h]
  int v17; // [rsp+58h] [rbp-18h]
  unsigned int *v18; // [rsp+60h] [rbp-10h]

  v12 = 0;
  v15 = &qword_180072F00;
  v13 = 1;
  v18 = (unsigned int *)&v12;
  v14 = 0;
  v16 = 544438355;
  v17 = 131;
  CFrame::BaseEnter((CFrame *)&v13);
  v6 = 0;
  *a1 = 0;
  while ( 2 )
  {
    if ( a3 )
    {
      v7 = wcschr(a2, 0x2Cu);
      if ( v7 )
        v8 = v7 - a2;
      else
        v8 = a3;
      for ( i = 0; i < 0x16; ++i )
      {
        if ( !FusionpCompareStrings((&off_18007B470)[3 * i], (__int16)*(&off_18007B470 + 3 * i + 1), a2, v8, 1u) )
        {
          if ( (v6 & (__int64)(&off_18007B470)[3 * i + 1]) != 0 )
          {
            FusionpDbgPrintEx(0xC0000000, "SXS.DLL: Redundant OLEMISC flags\n");
            goto LABEL_17;
          }
          v6 |= LODWORD((&off_18007B470)[3 * i + 1]);
          goto LABEL_13;
        }
      }
      if ( i == 22 )
      {
        FusionpDbgPrintEx(0xC0000000, "SXS.DLL: Invalid OLEMISC flags\n");
        goto LABEL_17;
      }
LABEL_13:
      a2 += v8;
      a3 -= v8;
      if ( !a3 )
        continue;
      if ( --a3 )
      {
        ++a2;
        continue;
      }
      FusionpDbgPrintEx(0xC0000000, "SXS.DLL: Trailing comma in OLEMISC flag string\n");
LABEL_17:
      SetLastError(0x36B5u);
    }
    else
    {
      *a1 = v6;
      SetLastError(0);
      *v18 = 1;
    }
    break;
  }
  v10 = *v18;
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v13);
  return v10;
}

```

## disassembly

```asm
0x18005a6bc  mov     [rsp-38h+arg_18], rbx
0x18005a6c1  push    rbp
0x18005a6c2  push    rsi
0x18005a6c3  push    rdi
0x18005a6c4  push    r12
0x18005a6c6  push    r13
0x18005a6c8  push    r14
0x18005a6ca  push    r15
0x18005a6cc  mov     rbp, rsp
0x18005a6cf  sub     rsp, 70h
0x18005a6d3  mov     rax, cs:__security_cookie
0x18005a6da  xor     rax, rsp
0x18005a6dd  mov     [rbp+var_8], rax
0x18005a6e1  lea     rax, qword_180072F00
0x18005a6e8  mov     [rbp+var_40], 0
0x18005a6ef  mov     [rbp+var_28], rax
0x18005a6f3  mov     r13, rcx
0x18005a6f6  lea     rax, [rbp+var_40]
0x18005a6fa  mov     [rbp+var_38], 1
0x18005a701  lea     rcx, [rbp+var_38]; this
0x18005a705  mov     [rbp+var_10], rax
0x18005a709  mov     rbx, r8
0x18005a70c  mov     [rbp+var_30], 0
0x18005a714  mov     r14, rdx
0x18005a717  mov     [rbp+var_20], 20737853h
0x18005a71f  mov     [rbp+var_18], 83h
0x18005a726  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18005a72b  xor     r15d, r15d
0x18005a72e  mov     dword ptr [r13+0], 0
0x18005a736  test    rbx, rbx
0x18005a739  jz      loc_18005A804
0x18005a73f  mov     edx, 2Ch ; ','; Ch
0x18005a744  mov     rcx, r14; Str
0x18005a747  call    cs:__imp_wcschr
0x18005a74e  nop     dword ptr [rax+rax+00h]
0x18005a753  mov     rdi, rax
0x18005a756  test    rax, rax
0x18005a759  jz      short loc_18005A763
0x18005a75b  sub     rdi, r14
0x18005a75e  sar     rdi, 1
0x18005a761  jmp     short loc_18005A766
0x18005a763  mov     rdi, rbx
0x18005a766  xor     esi, esi
0x18005a768  cmp     rsi, 16h
0x18005a76c  jnb     short loc_18005A7B0
0x18005a76e  lea     rax, off_18007B470; "RECOMPOSEONRESIZE"
0x18005a775  mov     [rsp+70h+var_50], 1; bool
0x18005a77a  lea     r12, [rsi+rsi*2]
0x18005a77e  mov     r9, rdi; unsigned __int64
0x18005a781  mov     rdx, [rax+r12*8+8]; unsigned __int64
0x18005a786  mov     r8, r14; unsigned __int16 *
0x18005a789  mov     rcx, [rax+r12*8]; unsigned __int16 *
0x18005a78d  call    ?FusionpCompareStrings@@YAHPEBG_K01_N@Z; FusionpCompareStrings(ushort const *,unsigned __int64,ushort const *,unsigned __int64,bool)
0x18005a792  test    eax, eax
0x18005a794  jz      short loc_18005A79B
0x18005a796  inc     rsi
0x18005a799  jmp     short loc_18005A768
0x18005a79b  lea     rax, off_18007B470; "RECOMPOSEONRESIZE"
0x18005a7a2  test    [rax+r12*8+10h], r15d
0x18005a7a7  jnz     short loc_18005A7CE
0x18005a7a9  or      r15d, [rax+r12*8+10h]
0x18005a7ae  jmp     short loc_18005A7B2
0x18005a7b0  jz      short loc_18005A7FB
0x18005a7b2  lea     r14, [r14+rdi*2]
0x18005a7b6  sub     rbx, rdi
0x18005a7b9  jz      loc_18005A736
0x18005a7bf  sub     rbx, 1
0x18005a7c3  jz      short loc_18005A7F2
0x18005a7c5  add     r14, 2
0x18005a7c9  jmp     loc_18005A736
0x18005a7ce  lea     rdx, aSxsDllRedundan; "SXS.DLL: Redundant OLEMISC flags\n"
0x18005a7d5  mov     ecx, 0C0000000h; unsigned int
0x18005a7da  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x18005a7df  mov     ecx, 36B5h; dwErrCode
0x18005a7e4  call    cs:__imp_SetLastError
0x18005a7eb  nop     dword ptr [rax+rax+00h]
0x18005a7f0  jmp     short loc_18005A820
0x18005a7f2  lea     rdx, aSxsDllTrailing_0; "SXS.DLL: Trailing comma in OLEMISC flag"...
0x18005a7f9  jmp     short loc_18005A7D5
0x18005a7fb  lea     rdx, aSxsDllInvalidO; "SXS.DLL: Invalid OLEMISC flags\n"
0x18005a802  jmp     short loc_18005A7D5
0x18005a804  xor     ecx, ecx; dwErrCode
0x18005a806  mov     [r13+0], r15d
0x18005a80a  call    cs:__imp_SetLastError
0x18005a811  nop     dword ptr [rax+rax+00h]
0x18005a816  mov     rax, [rbp+var_10]
0x18005a81a  mov     dword ptr [rax], 1
0x18005a820  mov     rax, [rbp+var_10]
0x18005a824  lea     rcx, [rbp+var_38]; this
0x18005a828  mov     ebx, [rax]
0x18005a82a  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x18005a82f  mov     eax, ebx
0x18005a831  mov     rcx, [rbp+var_8]
0x18005a835  xor     rcx, rsp; StackCookie
0x18005a838  call    __security_check_cookie
0x18005a83d  mov     rbx, [rsp+70h+arg_18]
0x18005a845  add     rsp, 70h
0x18005a849  pop     r15
0x18005a84b  pop     r14
0x18005a84d  pop     r13
0x18005a84f  pop     r12
0x18005a851  pop     rdi
0x18005a852  pop     rsi
0x18005a853  pop     rbp
0x18005a854  retn
```
