# CWerComReportKeyValueList<&WerpGetNumSigParams(void *,ulong *),&WerpGetSigParamByIndex(void *,ulong,ushort const * *,ushort const * *)>::_Get(long,ushort * *,ushort * *)

- ea: `0x18000f364`
- end: `0x18000f465`
- name: `?_Get@?$CWerComReportKeyValueList@$1?WerpGetNumSigParams@@YAJPEAXPEAK@Z$1?WerpGetSigParamByIndex@@YAJ0KPEAPEBG2@Z@@QEAAJJPEAPEAG0@Z`
- size: `257`
- prototype: `__int64 __fastcall(__int64, __int64, BSTR *, BSTR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000ae80`

## callees

- `0x180002850`
- `0x180006c9c`
- `0x18000f364`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000f3fc`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f40a`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f3fc`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f40a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f3e8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f3f1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f3e8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f3f1`
- `wer!WerpGetSigParamByIndex` at `0x18000f396`
- `wer!WerpGetSigParamByIndex` at `0x18000f396`

## pseudocode

```c
__int64 __fastcall CWerComReportKeyValueList<&long WerpGetNumSigParams(void *,unsigned long *),&long WerpGetSigParamByIndex(void *,unsigned long,unsigned short const * *,unsigned short const * *)>::_Get(
        __int64 a1,
        __int64 a2,
        BSTR *a3,
        BSTR *a4)
{
  __int64 v4; // rcx
  int SigParamByIndex; // eax
  unsigned int v8; // ebx
  BSTR v10; // rax
  OLECHAR *v11; // rcx
  BSTR v12; // rax
  OLECHAR *v13; // [rsp+20h] [rbp-18h] BYREF
  OLECHAR *psz; // [rsp+40h] [rbp+8h] BYREF

  v4 = *(_QWORD *)(a1 + 32);
  psz = 0;
  v13 = 0;
  SigParamByIndex = WerpGetSigParamByIndex(v4, a2, &psz, &v13);
  v8 = SigParamByIndex;
  if ( SigParamByIndex < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids,
        (unsigned int)SigParamByIndex);
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
0x18000f364  mov     rax, rsp
0x18000f367  mov     [rax+10h], rbx
0x18000f36b  mov     [rax+18h], rsi
0x18000f36f  push    rdi
0x18000f370  sub     rsp, 30h
0x18000f374  mov     rcx, [rcx+20h]
0x18000f378  mov     rsi, r9
0x18000f37b  mov     rdi, r8
0x18000f37e  mov     qword ptr [rax+8], 0
0x18000f386  lea     r9, [rax-18h]
0x18000f38a  mov     qword ptr [rax-18h], 0
0x18000f392  lea     r8, [rax+8]
0x18000f396  call    cs:__imp_WerpGetSigParamByIndex
0x18000f39c  mov     ebx, eax
0x18000f39e  test    eax, eax
0x18000f3a0  jns     short loc_18000F3E5
0x18000f3a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f3a9  lea     rdx, WPP_GLOBAL_Control
0x18000f3b0  cmp     rcx, rdx
0x18000f3b3  jz      short loc_18000F3D3
0x18000f3b5  test    byte ptr [rcx+1Ch], 1
0x18000f3b9  jz      short loc_18000F3D3
0x18000f3bb  mov     rcx, [rcx+10h]
0x18000f3bf  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18000f3c6  mov     edx, 12h
0x18000f3cb  mov     r9d, eax
0x18000f3ce  call    WPP_SF_d
0x18000f3d3  mov     eax, ebx
0x18000f3d5  mov     rbx, [rsp+38h+arg_8]
0x18000f3da  mov     rsi, [rsp+38h+arg_10]
0x18000f3df  add     rsp, 30h
0x18000f3e3  pop     rdi
0x18000f3e4  retn
0x18000f3e5  mov     rcx, [rdi]; bstrString
0x18000f3e8  call    cs:__imp_SysFreeString
0x18000f3ee  mov     rcx, [rsi]; bstrString
0x18000f3f1  call    cs:__imp_SysFreeString
0x18000f3f7  mov     rcx, [rsp+38h+psz]; psz
0x18000f3fc  call    cs:__imp_SysAllocString
0x18000f402  mov     rcx, [rsp+38h+var_18]; psz
0x18000f407  mov     [rdi], rax
0x18000f40a  call    cs:__imp_SysAllocString
0x18000f410  mov     [rsi], rax
0x18000f413  cmp     qword ptr [rdi], 0
0x18000f417  jnz     short loc_18000F421
0x18000f419  cmp     [rsp+38h+psz], 0
0x18000f41f  jnz     short loc_18000F42D
0x18000f421  test    rax, rax
0x18000f424  jnz     short loc_18000F3D3
0x18000f426  cmp     [rsp+38h+var_18], rax
0x18000f42b  jz      short loc_18000F3D3
0x18000f42d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f434  lea     rdx, WPP_GLOBAL_Control
0x18000f43b  cmp     rcx, rdx
0x18000f43e  jz      short loc_18000F45B
0x18000f440  test    byte ptr [rcx+1Ch], 1
0x18000f444  jz      short loc_18000F45B
0x18000f446  mov     rcx, [rcx+10h]
0x18000f44a  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18000f451  mov     edx, 13h
0x18000f456  call    WPP_SF_
0x18000f45b  mov     eax, 8007000Eh
0x18000f460  jmp     loc_18000F3D5
```
