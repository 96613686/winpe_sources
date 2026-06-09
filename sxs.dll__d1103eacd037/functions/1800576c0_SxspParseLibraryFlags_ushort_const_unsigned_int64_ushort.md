# SxspParseLibraryFlags(ushort const *,unsigned __int64,ushort *)

- ea: `0x1800576c0`
- end: `0x180057850`
- name: `?SxspParseLibraryFlags@@YAHPEBG_KPEAG@Z`
- size: `400`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800358d0`

## callees

- `0x18000c000`
- `0x18000df40`
- `0x180013150`
- `0x18001c270`
- `0x1800576c0`
- `0x18006a110`

## import_xrefs

- `ntdll!wcschr` at `0x18005774e`
- `ntdll!wcschr` at `0x18005774e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800577ed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800577ed`

## string_xrefs

- `0x180057804`: `SXS.DLL: Invalid type library flags\n`
- `0x1800577d7`: `SXS.DLL: Redundant type library flags\n`
- `0x1800577fb`: `SXS.DLL: Trailing comma in type library flag string\n`

## pseudocode

```c
__int64 __fastcall SxspParseLibraryFlags(wchar_t *a1, __int64 a2, unsigned __int16 *a3)
{
  unsigned __int16 v6; // r12
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
  int *v18; // [rsp+60h] [rbp-10h]

  v12 = 0;
  v15 = &qword_1800729A8;
  v13 = 1;
  v18 = &v12;
  v14 = 0;
  v16 = 544438355;
  v17 = 2758;
  CFrame::BaseEnter((CFrame *)&v13);
  v6 = 0;
  if ( a3 )
    *a3 = 0;
  while ( 2 )
  {
    if ( a2 )
    {
      v7 = wcschr(a1, 0x2Cu);
      if ( v7 )
        v8 = v7 - a1;
      else
        v8 = a2;
      for ( i = 0; i < 4; ++i )
      {
        if ( !FusionpCompareStrings((&off_1800729D0)[3 * i], (__int16)*(&off_1800729D0 + 3 * i + 1), a1, v8, 1u) )
        {
          if ( (v6 & (__int64)(&off_1800729D0)[3 * i + 1]) != 0 )
          {
            FusionpDbgPrintEx(0xC0000000, "SXS.DLL: Redundant type library flags\n");
            goto LABEL_18;
          }
          v6 |= LOWORD((&off_1800729D0)[3 * i + 1]);
          goto LABEL_14;
        }
      }
      if ( i == 4 )
      {
        FusionpDbgPrintEx(0xC0000000, "SXS.DLL: Invalid type library flags\n");
        goto LABEL_18;
      }
LABEL_14:
      a1 += v8;
      a2 -= v8;
      if ( !a2 )
        continue;
      if ( --a2 )
      {
        ++a1;
        continue;
      }
      FusionpDbgPrintEx(0xC0000000, "SXS.DLL: Trailing comma in type library flag string\n");
LABEL_18:
      SetLastError(0x36B5u);
    }
    else
    {
      if ( a3 )
        *a3 = v6;
      v12 = 1;
    }
    break;
  }
  v10 = v12;
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v13);
  return v10;
}

```

## disassembly

```asm
0x1800576c0  mov     [rsp-38h+arg_18], rbx
0x1800576c5  push    rbp
0x1800576c6  push    rsi
0x1800576c7  push    rdi
0x1800576c8  push    r12
0x1800576ca  push    r13
0x1800576cc  push    r14
0x1800576ce  push    r15
0x1800576d0  mov     rbp, rsp
0x1800576d3  sub     rsp, 70h
0x1800576d7  mov     rax, cs:__security_cookie
0x1800576de  xor     rax, rsp
0x1800576e1  mov     [rbp+var_8], rax
0x1800576e5  lea     rax, qword_1800729A8
0x1800576ec  mov     [rbp+var_40], 0
0x1800576f3  mov     [rbp+var_28], rax
0x1800576f7  mov     r14, rcx
0x1800576fa  lea     rax, [rbp+var_40]
0x1800576fe  mov     [rbp+var_38], 1
0x180057705  lea     rcx, [rbp+var_38]; this
0x180057709  mov     [rbp+var_10], rax
0x18005770d  mov     r15, r8
0x180057710  mov     [rbp+var_30], 0
0x180057718  mov     rbx, rdx
0x18005771b  mov     [rbp+var_20], 20737853h
0x180057723  mov     [rbp+var_18], 0AC6h
0x18005772a  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18005772f  xor     r12d, r12d
0x180057732  test    r15, r15
0x180057735  jz      short loc_18005773D
0x180057737  xor     eax, eax
0x180057739  mov     [r15], ax
0x18005773d  test    rbx, rbx
0x180057740  jz      loc_18005780D
0x180057746  mov     edx, 2Ch ; ','; Ch
0x18005774b  mov     rcx, r14; Str
0x18005774e  call    cs:__imp_wcschr
0x180057755  nop     dword ptr [rax+rax+00h]
0x18005775a  mov     rdi, rax
0x18005775d  test    rax, rax
0x180057760  jz      short loc_18005776A
0x180057762  sub     rdi, r14
0x180057765  sar     rdi, 1
0x180057768  jmp     short loc_18005776D
0x18005776a  mov     rdi, rbx
0x18005776d  xor     esi, esi
0x18005776f  cmp     rsi, 4
0x180057773  jnb     short loc_1800577B9
0x180057775  lea     rax, off_1800729D0; "RESTRICTED"
0x18005777c  mov     [rsp+70h+var_50], 1; bool
0x180057781  lea     r13, [rsi+rsi*2]
0x180057785  mov     r9, rdi; unsigned __int64
0x180057788  mov     rdx, [rax+r13*8+8]; unsigned __int64
0x18005778d  mov     r8, r14; unsigned __int16 *
0x180057790  mov     rcx, [rax+r13*8]; unsigned __int16 *
0x180057794  call    ?FusionpCompareStrings@@YAHPEBG_K01_N@Z; FusionpCompareStrings(ushort const *,unsigned __int64,ushort const *,unsigned __int64,bool)
0x180057799  test    eax, eax
0x18005779b  jz      short loc_1800577A2
0x18005779d  inc     rsi
0x1800577a0  jmp     short loc_18005776F
0x1800577a2  lea     rax, off_1800729D0; "RESTRICTED"
0x1800577a9  test    [rax+r13*8+10h], r12w
0x1800577af  jnz     short loc_1800577D7
0x1800577b1  or      r12w, [rax+r13*8+10h]
0x1800577b7  jmp     short loc_1800577BB
0x1800577b9  jz      short loc_180057804
0x1800577bb  lea     r14, [r14+rdi*2]
0x1800577bf  sub     rbx, rdi
0x1800577c2  jz      loc_18005773D
0x1800577c8  sub     rbx, 1
0x1800577cc  jz      short loc_1800577FB
0x1800577ce  add     r14, 2
0x1800577d2  jmp     loc_18005773D
0x1800577d7  lea     rdx, aSxsDllRedundan_0; "SXS.DLL: Redundant type library flags\n"
0x1800577de  mov     ecx, 0C0000000h; unsigned int
0x1800577e3  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x1800577e8  mov     ecx, 36B5h; dwErrCode
0x1800577ed  call    cs:__imp_SetLastError
0x1800577f4  nop     dword ptr [rax+rax+00h]
0x1800577f9  jmp     short loc_18005781D
0x1800577fb  lea     rdx, aSxsDllTrailing; "SXS.DLL: Trailing comma in type library"...
0x180057802  jmp     short loc_1800577DE
0x180057804  lea     rdx, aSxsDllInvalidT_0; "SXS.DLL: Invalid type library flags\n"
0x18005780b  jmp     short loc_1800577DE
0x18005780d  test    r15, r15
0x180057810  jz      short loc_180057816
0x180057812  mov     [r15], r12w
0x180057816  mov     [rbp+var_40], 1
0x18005781d  mov     ebx, [rbp+var_40]
0x180057820  lea     rcx, [rbp+var_38]; this
0x180057824  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x180057829  mov     eax, ebx
0x18005782b  mov     rcx, [rbp+var_8]
0x18005782f  xor     rcx, rsp; StackCookie
0x180057832  call    __security_check_cookie
0x180057837  mov     rbx, [rsp+70h+arg_18]
0x18005783f  add     rsp, 70h
0x180057843  pop     r15
0x180057845  pop     r14
0x180057847  pop     r13
0x180057849  pop     r12
0x18005784b  pop     rdi
0x18005784c  pop     rsi
0x18005784d  pop     rbp
0x18005784e  retn
```
