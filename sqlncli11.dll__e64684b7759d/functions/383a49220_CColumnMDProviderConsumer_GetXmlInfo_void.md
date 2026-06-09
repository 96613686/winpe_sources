# CColumnMDProviderConsumer::GetXmlInfo(void)

- ea: `0x383a49220`
- end: `0x383a49553`
- name: `?GetXmlInfo@CColumnMDProviderConsumer@@EEAAJXZ`
- size: `819`
- prototype: `__int64 __fastcall(CColumnMDProviderConsumer *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x38391afe0`
- `0x3839bdd50`
- `0x383a438f0`
- `0x383a49220`
- `0x383a7e3f0`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x383a49287`
- `OLEAUT32!__imp_SysStringLen` at `0x383a49313`
- `OLEAUT32!__imp_SysStringLen` at `0x383a49405`
- `OLEAUT32!__imp_SysStringLen` at `0x383a49287`
- `OLEAUT32!__imp_SysStringLen` at `0x383a49313`
- `OLEAUT32!__imp_SysStringLen` at `0x383a49405`

## string_xrefs

- `0x383a493b4`: `SSPROP_COL_XML_SCHEMACOLLECTIONNAME`
- `0x383a494a3`: `SSPROP_COL_XML_SCHEMACOLLECTION_CATALOGNAME`
- `0x383a4953a`: `SSPROP_COL_XML_SCHEMACOLLECTION_SCHEMANAME`

## pseudocode

```c
__int64 __fastcall CColumnMDProviderConsumer::GetXmlInfo(CColumnMDProviderConsumer *this)
{
  __int64 v2; // rbp
  unsigned int v3; // ebx
  __int64 v4; // rsi
  __int64 v5; // rcx
  const unsigned __int16 *v6; // rbx
  UINT v7; // eax
  int v8; // eax
  __int64 v9; // rcx
  const unsigned __int16 *v10; // rbx
  UINT v11; // eax
  int v12; // eax
  int v13; // eax
  __int64 v14; // rcx
  const unsigned __int16 *v15; // rbx
  UINT v16; // eax
  int v17; // eax
  int v18; // eax
  __int64 v19; // rax
  int v21; // eax

  v2 = *(_QWORD *)(*((_QWORD *)this + 22) + 8LL * *((_QWORD *)this + 6) - 8);
  v3 = 0;
  v4 = *((_QWORD *)this + 21) + 88LL * *((_QWORD *)this + 6);
  v5 = *(_QWORD *)(*(_QWORD *)(v2 + 48) + 40LL);
  if ( *(_WORD *)(v5 + 368) )
  {
    v6 = *(const unsigned __int16 **)(v5 + 376);
    if ( v6 )
    {
      v7 = SysStringLen(*(BSTR *)(v5 + 376));
      v8 = CBaseColumnMDProvider::AddToNamePool(
             this,
             v6,
             v7,
             (unsigned __int64 *)(*((_QWORD *)this + 8) + 264LL),
             (unsigned __int16 *)(*((_QWORD *)this + 8) + 256LL));
      v3 = v8;
      if ( v8 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
          bidTraceHR(off_383B433A8[0], 3960841, (unsigned int)v8);
        return v3;
      }
      *(_WORD *)(*((_QWORD *)this + 8) + 256LL) -= 2;
    }
    else
    {
      v13 = ChangePropStatus(
              0x24u,
              *(_DWORD *)(v4 - 56),
              *(const struct tagDBPROPSET *const *)(v4 - 72),
              *((const struct _GUID **)this + 5));
      v3 = v13;
      if ( v13 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
          v13 = bidTraceHR(off_383B433A8[0], 3976201, (unsigned int)v13);
        CErrorData::PostFormattedError(
          (CColumnMDProviderConsumer *)((char *)this + 88),
          v13,
          0xA0A1u,
          L"SSPROP_COL_XML_SCHEMACOLLECTIONNAME",
          *((_QWORD *)this + 6));
        return v3;
      }
    }
  }
  v9 = *(_QWORD *)(*(_QWORD *)(v2 + 48) + 40LL);
  if ( *(_WORD *)(v9 + 256) )
  {
    v10 = *(const unsigned __int16 **)(v9 + 264);
    if ( v10 )
    {
      v11 = SysStringLen(*(BSTR *)(v9 + 264));
      v12 = CBaseColumnMDProvider::AddToNamePool(
              this,
              v10,
              v11,
              (unsigned __int64 *)(*((_QWORD *)this + 8) + 232LL),
              (unsigned __int16 *)(*((_QWORD *)this + 8) + 224LL));
      v3 = v12;
      if ( v12 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
          bidTraceHR(off_383B433A8[0], 4006921, (unsigned int)v12);
        return v3;
      }
      *(_WORD *)(*((_QWORD *)this + 8) + 224LL) -= 2;
    }
    else
    {
      v18 = ChangePropStatus(
              0x22u,
              *(_DWORD *)(v4 - 56),
              *(const struct tagDBPROPSET *const *)(v4 - 72),
              *((const struct _GUID **)this + 5));
      v3 = v18;
      if ( v18 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
          v18 = bidTraceHR(off_383B433A8[0], 4022281, (unsigned int)v18);
        CErrorData::PostFormattedError(
          (CColumnMDProviderConsumer *)((char *)this + 88),
          v18,
          0xA0A1u,
          L"SSPROP_COL_XML_SCHEMACOLLECTION_CATALOGNAME",
          *((_QWORD *)this + 6));
        return v3;
      }
    }
  }
  v14 = *(_QWORD *)(*(_QWORD *)(v2 + 48) + 40LL);
  if ( !*(_WORD *)(v14 + 312) )
    goto LABEL_27;
  v15 = *(const unsigned __int16 **)(v14 + 320);
  if ( v15 )
  {
    v16 = SysStringLen(*(BSTR *)(v14 + 320));
    v17 = CBaseColumnMDProvider::AddToNamePool(
            this,
            v15,
            v16,
            (unsigned __int64 *)(*((_QWORD *)this + 8) + 248LL),
            (unsigned __int16 *)(*((_QWORD *)this + 8) + 240LL));
    v3 = v17;
    if ( v17 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
        bidTraceHR(off_383B433A8[0], 4054025, (unsigned int)v17);
      return v3;
    }
    *(_WORD *)(*((_QWORD *)this + 8) + 240LL) -= 2;
    goto LABEL_27;
  }
  v21 = ChangePropStatus(
          0x23u,
          *(_DWORD *)(v4 - 56),
          *(const struct tagDBPROPSET *const *)(v4 - 72),
          *((const struct _GUID **)this + 5));
  v3 = v21;
  if ( v21 >= 0 )
  {
LABEL_27:
    v19 = *((_QWORD *)this + 8);
    if ( *(_WORD *)(v19 + 256) )
      *(_WORD *)(v19 + 60) |= 4u;
    return v3;
  }
  if ( (bidGblFlags & 2) != 0 )
    v21 = bidTraceHR(off_383B433A8[0], 4069385, (unsigned int)v21);
  CErrorData::PostFormattedError(
    (CColumnMDProviderConsumer *)((char *)this + 88),
    v21,
    0xA0A1u,
    L"SSPROP_COL_XML_SCHEMACOLLECTION_SCHEMANAME",
    *((_QWORD *)this + 6));
  return v3;
}

```

## disassembly

```asm
0x383a49220  mov     [rsp+arg_0], rbx
0x383a49225  mov     [rsp+arg_8], rbp
0x383a4922a  mov     [rsp+arg_10], rsi
0x383a4922f  mov     [rsp+arg_18], rdi
0x383a49234  push    r14
0x383a49236  sub     rsp, 30h
0x383a4923a  mov     r8, [rcx+30h]
0x383a4923e  mov     rax, [rcx+0B0h]
0x383a49245  mov     rdi, rcx
0x383a49248  mov     rbp, [rax+r8*8-8]
0x383a4924d  mov     rsi, r8
0x383a49250  xor     ebx, ebx
0x383a49252  mov     rax, [rbp+30h]
0x383a49256  mov     r14d, 0FFFEh
0x383a4925c  imul    rsi, 58h ; 'X'
0x383a49260  add     rsi, [rcx+0A8h]
0x383a49267  mov     rcx, [rax+28h]
0x383a4926b  cmp     [rcx+170h], bx
0x383a49272  jz      short loc_383A492EA
0x383a49274  mov     rbx, [rcx+178h]
0x383a4927b  test    rbx, rbx
0x383a4927e  jz      loc_383A4936E
0x383a49284  mov     rcx, rbx; pbstr
0x383a49287  call    cs:__imp_SysStringLen
0x383a4928d  mov     r9, [rdi+40h]
0x383a49291  mov     rdx, rbx; unsigned __int16 *
0x383a49294  mov     r8d, eax; unsigned __int64
0x383a49297  lea     rax, [r9+100h]
0x383a4929e  add     r9, 108h; unsigned __int64 *
0x383a492a5  mov     rcx, rdi; this
0x383a492a8  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x383a492ad  call    ?AddToNamePool@CBaseColumnMDProvider@@IEAAJPEBG_KPEA_KPEAG@Z; CBaseColumnMDProvider::AddToNamePool(ushort const *,unsigned __int64,unsigned __int64 *,ushort *)
0x383a492b2  mov     ebx, eax
0x383a492b4  test    eax, eax
0x383a492b6  jns     short loc_383A492DE
0x383a492b8  test    byte ptr cs:_bidGblFlags, 2
0x383a492bf  jz      loc_383A494DB
0x383a492c5  mov     rcx, cs:off_383B433A8; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a492cc  mov     r8d, eax
0x383a492cf  mov     edx, 3C7009h
0x383a492d4  call    _bidTraceHR
0x383a492d9  jmp     loc_383A494DB
0x383a492de  mov     rax, [rdi+40h]
0x383a492e2  add     [rax+100h], r14w
0x383a492ea  mov     rax, [rbp+30h]
0x383a492ee  mov     rcx, [rax+28h]
0x383a492f2  cmp     word ptr [rcx+100h], 0
0x383a492fa  jz      loc_383A493DC
0x383a49300  mov     rbx, [rcx+108h]
0x383a49307  test    rbx, rbx
0x383a4930a  jz      loc_383A4945D
0x383a49310  mov     rcx, rbx; pbstr
0x383a49313  call    cs:__imp_SysStringLen
0x383a49319  mov     r9, [rdi+40h]
0x383a4931d  mov     rdx, rbx; unsigned __int16 *
0x383a49320  mov     r8d, eax; unsigned __int64
0x383a49323  lea     rax, [r9+0E0h]
0x383a4932a  add     r9, 0E8h; unsigned __int64 *
0x383a49331  mov     rcx, rdi; this
0x383a49334  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x383a49339  call    ?AddToNamePool@CBaseColumnMDProvider@@IEAAJPEBG_KPEA_KPEAG@Z; CBaseColumnMDProvider::AddToNamePool(ushort const *,unsigned __int64,unsigned __int64 *,ushort *)
0x383a4933e  mov     ebx, eax
0x383a49340  test    eax, eax
0x383a49342  jns     loc_383A493D0
0x383a49348  test    byte ptr cs:_bidGblFlags, 2
0x383a4934f  jz      loc_383A494DB
0x383a49355  mov     rcx, cs:off_383B433A8; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a4935c  mov     r8d, eax
0x383a4935f  mov     edx, 3D2409h
0x383a49364  call    _bidTraceHR
0x383a49369  jmp     loc_383A494DB
0x383a4936e  mov     r9, [rdi+28h]; struct _GUID *
0x383a49372  mov     r8, [rsi-48h]; struct tagDBPROPSET *
0x383a49376  mov     edx, [rsi-38h]; unsigned int
0x383a49379  mov     ecx, 24h ; '$'; unsigned int
0x383a4937e  call    ?ChangePropStatus@@YAJKKQEBUtagDBPROPSET@@PEBU_GUID@@@Z; ChangePropStatus(ulong,ulong,tagDBPROPSET const * const,_GUID const *)
0x383a49383  mov     ebx, eax
0x383a49385  test    eax, eax
0x383a49387  jns     loc_383A492EA
0x383a4938d  test    byte ptr cs:_bidGblFlags, 2
0x383a49394  jz      short loc_383A493AA
0x383a49396  mov     rcx, cs:off_383B433A8; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a4939d  mov     r8d, eax
0x383a493a0  mov     edx, 3CAC09h
0x383a493a5  call    _bidTraceHR
0x383a493aa  mov     edx, eax; int
0x383a493ac  mov     rax, [rdi+30h]
0x383a493b0  lea     rcx, [rdi+58h]; this
0x383a493b4  lea     r9, aSspropColXmlSc_1; "SSPROP_COL_XML_SCHEMACOLLECTIONNAME"
0x383a493bb  mov     r8d, 0A0A1h; unsigned int
0x383a493c1  mov     [rsp+38h+var_18], rax
0x383a493c6  call    ?PostFormattedError@CErrorData@@QEAAJJIZZ; CErrorData::PostFormattedError(long,uint,...)
0x383a493cb  jmp     loc_383A494DB
0x383a493d0  mov     rax, [rdi+40h]
0x383a493d4  add     [rax+0E0h], r14w
0x383a493dc  mov     rax, [rbp+30h]
0x383a493e0  mov     rcx, [rax+28h]
0x383a493e4  cmp     word ptr [rcx+138h], 0
0x383a493ec  jz      loc_383A494C8
0x383a493f2  mov     rbx, [rcx+140h]
0x383a493f9  test    rbx, rbx
0x383a493fc  jz      loc_383A494F8
0x383a49402  mov     rcx, rbx; pbstr
0x383a49405  call    cs:__imp_SysStringLen
0x383a4940b  mov     r9, [rdi+40h]
0x383a4940f  mov     rdx, rbx; unsigned __int16 *
0x383a49412  mov     r8d, eax; unsigned __int64
0x383a49415  lea     rax, [r9+0F0h]
0x383a4941c  add     r9, 0F8h; unsigned __int64 *
0x383a49423  mov     rcx, rdi; this
0x383a49426  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x383a4942b  call    ?AddToNamePool@CBaseColumnMDProvider@@IEAAJPEBG_KPEA_KPEAG@Z; CBaseColumnMDProvider::AddToNamePool(ushort const *,unsigned __int64,unsigned __int64 *,ushort *)
0x383a49430  mov     ebx, eax
0x383a49432  test    eax, eax
0x383a49434  jns     loc_383A494BC
0x383a4943a  test    byte ptr cs:_bidGblFlags, 2
0x383a49441  jz      loc_383A494DB
0x383a49447  mov     rcx, cs:off_383B433A8; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a4944e  mov     r8d, eax
0x383a49451  mov     edx, 3DDC09h
0x383a49456  call    _bidTraceHR
0x383a4945b  jmp     short loc_383A494DB
0x383a4945d  mov     r9, [rdi+28h]; struct _GUID *
0x383a49461  mov     r8, [rsi-48h]; struct tagDBPROPSET *
0x383a49465  mov     edx, [rsi-38h]; unsigned int
0x383a49468  mov     ecx, 22h ; '"'; unsigned int
0x383a4946d  call    ?ChangePropStatus@@YAJKKQEBUtagDBPROPSET@@PEBU_GUID@@@Z; ChangePropStatus(ulong,ulong,tagDBPROPSET const * const,_GUID const *)
0x383a49472  mov     ebx, eax
0x383a49474  test    eax, eax
0x383a49476  jns     loc_383A493DC
0x383a4947c  test    byte ptr cs:_bidGblFlags, 2
0x383a49483  jz      short loc_383A49499
0x383a49485  mov     rcx, cs:off_383B433A8; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a4948c  mov     r8d, eax
0x383a4948f  mov     edx, 3D6009h
0x383a49494  call    _bidTraceHR
0x383a49499  mov     edx, eax; int
0x383a4949b  mov     rax, [rdi+30h]
0x383a4949f  lea     rcx, [rdi+58h]; this
0x383a494a3  lea     r9, aSspropColXmlSc_0; "SSPROP_COL_XML_SCHEMACOLLECTION_CATALOG"...
0x383a494aa  mov     r8d, 0A0A1h; unsigned int
0x383a494b0  mov     [rsp+38h+var_18], rax
0x383a494b5  call    ?PostFormattedError@CErrorData@@QEAAJJIZZ; CErrorData::PostFormattedError(long,uint,...)
0x383a494ba  jmp     short loc_383A494DB
0x383a494bc  mov     rax, [rdi+40h]
0x383a494c0  add     [rax+0F0h], r14w
0x383a494c8  mov     rax, [rdi+40h]
0x383a494cc  cmp     word ptr [rax+100h], 0
0x383a494d4  jz      short loc_383A494DB
0x383a494d6  or      word ptr [rax+3Ch], 4
0x383a494db  mov     rbp, [rsp+38h+arg_8]
0x383a494e0  mov     rsi, [rsp+38h+arg_10]
0x383a494e5  mov     rdi, [rsp+38h+arg_18]
0x383a494ea  mov     eax, ebx
0x383a494ec  mov     rbx, [rsp+38h+arg_0]
0x383a494f1  add     rsp, 30h
0x383a494f5  pop     r14
0x383a494f7  retn
0x383a494f8  mov     r9, [rdi+28h]; struct _GUID *
0x383a494fc  mov     r8, [rsi-48h]; struct tagDBPROPSET *
0x383a49500  mov     edx, [rsi-38h]; unsigned int
0x383a49503  mov     ecx, 23h ; '#'; unsigned int
0x383a49508  call    ?ChangePropStatus@@YAJKKQEBUtagDBPROPSET@@PEBU_GUID@@@Z; ChangePropStatus(ulong,ulong,tagDBPROPSET const * const,_GUID const *)
0x383a4950d  mov     ebx, eax
0x383a4950f  test    eax, eax
0x383a49511  jns     short loc_383A494C8
0x383a49513  test    byte ptr cs:_bidGblFlags, 2
0x383a4951a  jz      short loc_383A49530
0x383a4951c  mov     rcx, cs:off_383B433A8; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a49523  mov     r8d, eax
0x383a49526  mov     edx, 3E1809h
0x383a4952b  call    _bidTraceHR
0x383a49530  mov     edx, eax; int
0x383a49532  mov     rax, [rdi+30h]
0x383a49536  lea     rcx, [rdi+58h]; this
0x383a4953a  lea     r9, aSspropColXmlSc; "SSPROP_COL_XML_SCHEMACOLLECTION_SCHEMAN"...
0x383a49541  mov     r8d, 0A0A1h; unsigned int
0x383a49547  mov     [rsp+38h+var_18], rax
0x383a4954c  call    ?PostFormattedError@CErrorData@@QEAAJJIZZ; CErrorData::PostFormattedError(long,uint,...)
0x383a49551  jmp     short loc_383A494DB
```
