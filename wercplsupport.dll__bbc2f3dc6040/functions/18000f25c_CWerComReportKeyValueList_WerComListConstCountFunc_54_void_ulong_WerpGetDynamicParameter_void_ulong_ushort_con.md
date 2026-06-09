# CWerComReportKeyValueList<&WerComListConstCountFunc<54>(void *,ulong *),&WerpGetDynamicParameter(void *,ulong,ushort const * *,ushort const * *)>::_Get(long,ushort * *,ushort * *)

- ea: `0x18000f25c`
- end: `0x18000f35d`
- name: `?_Get@?$CWerComReportKeyValueList@$1??$WerComListConstCountFunc@$0DG@@@YAJPEAXPEAK@Z$1?WerpGetDynamicParameter@@YAJ0KPEAPEBG2@Z@@QEAAJJPEAPEAG0@Z`
- size: `257`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000ae20`

## callees

- `0x180002850`
- `0x180006c9c`
- `0x18000f25c`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000f2f4`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f302`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f2f4`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f302`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f2e0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f2e9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f2e0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f2e9`
- `wer!WerpGetDynamicParameter` at `0x18000f28e`
- `wer!WerpGetDynamicParameter` at `0x18000f28e`

## pseudocode

```c
__int64 __fastcall CWerComReportKeyValueList<&long WerComListConstCountFunc<54>(void *,unsigned long *),&long WerpGetDynamicParameter(void *,unsigned long,unsigned short const * *,unsigned short const * *)>::_Get(
        __int64 a1,
        __int64 a2,
        BSTR *a3,
        BSTR *a4)
{
  __int64 v4; // rcx
  int DynamicParameter; // eax
  unsigned int v8; // ebx
  BSTR v10; // rax
  OLECHAR *v11; // rcx
  BSTR v12; // rax
  OLECHAR *v13; // [rsp+20h] [rbp-18h] BYREF
  OLECHAR *psz; // [rsp+40h] [rbp+8h] BYREF

  v4 = *(_QWORD *)(a1 + 32);
  psz = 0;
  v13 = 0;
  DynamicParameter = WerpGetDynamicParameter(v4, a2, &psz, &v13);
  v8 = DynamicParameter;
  if ( DynamicParameter < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids,
        (unsigned int)DynamicParameter);
    return v8;
  }
  SysFreeString(*a3);
  SysFreeString(*a4);
  v10 = SysAllocString(psz);
  v11 = v13;
  *a3 = v10;
  v12 = SysAllocString(v11);
  *a4 = v12;
  if ( (*a3 || !psz) && (v12 || !v13) )
    return v8;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids);
  return 2147942414LL;
}

```

## disassembly

```asm
0x18000f25c  mov     rax, rsp
0x18000f25f  mov     [rax+10h], rbx
0x18000f263  mov     [rax+18h], rsi
0x18000f267  push    rdi
0x18000f268  sub     rsp, 30h
0x18000f26c  mov     rcx, [rcx+20h]
0x18000f270  mov     rsi, r9
0x18000f273  mov     rdi, r8
0x18000f276  mov     qword ptr [rax+8], 0
0x18000f27e  lea     r9, [rax-18h]
0x18000f282  mov     qword ptr [rax-18h], 0
0x18000f28a  lea     r8, [rax+8]
0x18000f28e  call    cs:__imp_WerpGetDynamicParameter
0x18000f294  mov     ebx, eax
0x18000f296  test    eax, eax
0x18000f298  jns     short loc_18000F2DD
0x18000f29a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f2a1  lea     rdx, WPP_GLOBAL_Control
0x18000f2a8  cmp     rcx, rdx
0x18000f2ab  jz      short loc_18000F2CB
0x18000f2ad  test    byte ptr [rcx+1Ch], 1
0x18000f2b1  jz      short loc_18000F2CB
0x18000f2b3  mov     rcx, [rcx+10h]
0x18000f2b7  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18000f2be  mov     edx, 12h
0x18000f2c3  mov     r9d, eax
0x18000f2c6  call    WPP_SF_d
0x18000f2cb  mov     eax, ebx
0x18000f2cd  mov     rbx, [rsp+38h+arg_8]
0x18000f2d2  mov     rsi, [rsp+38h+arg_10]
0x18000f2d7  add     rsp, 30h
0x18000f2db  pop     rdi
0x18000f2dc  retn
0x18000f2dd  mov     rcx, [rdi]; bstrString
0x18000f2e0  call    cs:__imp_SysFreeString
0x18000f2e6  mov     rcx, [rsi]; bstrString
0x18000f2e9  call    cs:__imp_SysFreeString
0x18000f2ef  mov     rcx, [rsp+38h+psz]; psz
0x18000f2f4  call    cs:__imp_SysAllocString
0x18000f2fa  mov     rcx, [rsp+38h+var_18]; psz
0x18000f2ff  mov     [rdi], rax
0x18000f302  call    cs:__imp_SysAllocString
0x18000f308  mov     [rsi], rax
0x18000f30b  cmp     qword ptr [rdi], 0
0x18000f30f  jnz     short loc_18000F319
0x18000f311  cmp     [rsp+38h+psz], 0
0x18000f317  jnz     short loc_18000F325
0x18000f319  test    rax, rax
0x18000f31c  jnz     short loc_18000F2CB
0x18000f31e  cmp     [rsp+38h+var_18], rax
0x18000f323  jz      short loc_18000F2CB
0x18000f325  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f32c  lea     rdx, WPP_GLOBAL_Control
0x18000f333  cmp     rcx, rdx
0x18000f336  jz      short loc_18000F353
0x18000f338  test    byte ptr [rcx+1Ch], 1
0x18000f33c  jz      short loc_18000F353
0x18000f33e  mov     rcx, [rcx+10h]
0x18000f342  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18000f349  mov     edx, 13h
0x18000f34e  call    WPP_SF_
0x18000f353  mov     eax, 8007000Eh
0x18000f358  jmp     loc_18000F2CD
```
