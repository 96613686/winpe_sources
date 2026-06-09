# SrmParseResourceControlList(_ACL *,bool,std::vector<SrmSecureProperty,std::allocator<SrmSecureProperty>> &)

- ea: `0x180083c24`
- end: `0x180084385`
- name: `?SrmParseResourceControlList@@YAXPEAU_ACL@@_NAEAV?$vector@USrmSecureProperty@@V?$allocator@USrmSecureProperty@@@std@@@std@@@Z`
- size: `1889`
- prototype: `__int64 __fastcall(PACL pAcl)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180046e20`

## callees

- `0x180001304`
- `0x180001350`
- `0x1800020ba`
- `0x180002520`
- `0x180002a6c`
- `0x180006a1c`
- `0x1800095f4`
- `0x18000ebd4`
- `0x18000eef4`
- `0x180010bc4`
- `0x1800208e8`
- `0x18003ed58`
- `0x18003ff90`
- `0x180043dac`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x180073f54`
- `0x1800821f8`
- `0x180083c24`
- `0x18008438c`
- `0x1800844d8`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `msvcrt!_i64tow_s` at `0x18008416c`
- `msvcrt!_i64tow_s` at `0x18008416c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180083e18`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180083e18`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180083da4`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180083da4`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180083df2`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180083df2`

## string_xrefs

- `0x180083c6e`: `base\fs\fsrm\utilities\security\srmsec.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
void __fastcall SrmParseResourceControlList(PACL pAcl, __int64 a2, char **a3)
{
  struct _ACL *v4; // r15
  __int64 v5; // rcx
  char *v6; // rsi
  char *v7; // rbx
  char *v8; // rdi
  _QWORD *v9; // rax
  const char *v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rcx
  char *v13; // rcx
  DWORD v14; // r13d
  char *v15; // rsi
  __int64 v16; // rdx
  __int64 v17; // rcx
  DWORD LengthSid; // eax
  unsigned int *v19; // rbx
  char v20; // di
  _WORD *v21; // r15
  unsigned int v22; // r12d
  __int64 v23; // rdx
  char *v24; // rax
  char *v25; // rdi
  char *v26; // rax
  unsigned int i; // edi
  char *v28; // rsi
  __int64 v29; // r8
  __int64 v30; // rbx
  __int64 v31; // r8
  __int64 v32; // r8
  char *j; // rbx
  int v34; // eax
  char v35; // al
  int LastFailureAsHRESULT; // eax
  char Hr; // al
  char v38; // al
  __int64 v39; // [rsp+28h] [rbp-D8h]
  char v40; // [rsp+30h] [rbp-D0h]
  __int128 v42; // [rsp+40h] [rbp-C0h] BYREF
  char *v43; // [rsp+50h] [rbp-B0h]
  LPVOID pAce; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *pExceptionObject; // [rsp+68h] [rbp-98h] BYREF
  char v46; // [rsp+70h] [rbp-90h]
  char v47[8]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD *v48; // [rsp+88h] [rbp-78h]
  __int64 v49; // [rsp+90h] [rbp-70h]
  _QWORD v50[3]; // [rsp+A0h] [rbp-60h] BYREF
  int v51; // [rsp+B8h] [rbp-48h]
  int v52; // [rsp+BCh] [rbp-44h]
  int v53; // [rsp+C0h] [rbp-40h]
  char v54[96]; // [rsp+C8h] [rbp-38h] BYREF
  int v55; // [rsp+128h] [rbp+28h]
  __int64 pAclInformation; // [rsp+130h] [rbp+30h] BYREF
  int v57; // [rsp+138h] [rbp+38h]
  void *Src[2]; // [rsp+140h] [rbp+40h] BYREF
  __int64 v59; // [rsp+150h] [rbp+50h]
  unsigned __int64 v60; // [rsp+158h] [rbp+58h]
  void *v61[2]; // [rsp+170h] [rbp+70h] BYREF
  __int64 v62; // [rsp+180h] [rbp+80h]
  unsigned __int64 v63; // [rsp+188h] [rbp+88h]
  void *v64; // [rsp+198h] [rbp+98h]
  __int64 v65; // [rsp+1A8h] [rbp+A8h]
  unsigned __int64 v66; // [rsp+1B0h] [rbp+B0h]
  void *v67[2]; // [rsp+1D0h] [rbp+D0h] BYREF
  __int64 v68; // [rsp+1E0h] [rbp+E0h]
  unsigned __int64 v69; // [rsp+1E8h] [rbp+E8h]
  void *v70; // [rsp+1F8h] [rbp+F8h]
  __int64 v71; // [rsp+208h] [rbp+108h]
  unsigned __int64 v72; // [rsp+210h] [rbp+110h]
  void *v73[3]; // [rsp+230h] [rbp+130h] BYREF
  unsigned __int64 v74; // [rsp+248h] [rbp+148h]
  bool v75; // [rsp+258h] [rbp+158h]
  void **v76; // [rsp+260h] [rbp+160h] BYREF
  int v77; // [rsp+268h] [rbp+168h]
  void *Block; // [rsp+310h] [rbp+210h]
  __int64 v79; // [rsp+320h] [rbp+220h]
  unsigned __int64 v80; // [rsp+328h] [rbp+228h]
  wchar_t Buffer; // [rsp+340h] [rbp+240h] BYREF
  char v82[126]; // [rsp+342h] [rbp+242h] BYREF

  v4 = pAcl;
  v40 = 0;
  pExceptionObject = v50;
  v50[0] = L"base\\fs\\fsrm\\utilities\\security\\srmsec.cpp";
  v50[1] = L"SrmParseResourceControlList";
  v50[2] = L"SECSECRC";
  v51 = 2631;
  v52 = 17;
  v53 = 255;
  v55 = 0x1000000;
  memset_0(v54, 0, sizeof(v54));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v76, (const struct CSrmDebugInfo *)v50, 0);
  v6 = a3[1];
  v7 = *a3;
  if ( *a3 != v6 )
  {
    v8 = *a3;
    do
    {
      std::_Dest_val<std::allocator<CPropertyValue>,CPropertyValue>(v5, v8);
      v8 += 88;
    }
    while ( v8 != v6 );
    a3[1] = v7;
  }
  if ( !v4 )
  {
    v76 = &CSrmFunctionTracer::`vftable';
    goto LABEL_7;
  }
  pAclInformation = 0;
  v57 = 0;
  v49 = 0;
  v9 = operator new(0x50u);
  if ( !v9 )
  {
    std::bad_alloc::bad_alloc((std::bad_alloc *)&pExceptionObject, v10);
    throw (std::bad_alloc *)&pExceptionObject;
  }
  v48 = v9;
  *v9 = v9;
  v9[1] = v48;
  v9[2] = v48;
  *((_WORD *)v9 + 36) = 257;
  v42 = 0;
  v43 = 0;
  if ( !GetAclInformation(v4, &pAclInformation, 0xCu, AclSizeInformation) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v12, v11);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v76, LastFailureAsHRESULT);
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v76);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v76, 0xA5Au, Hr, 0);
  }
  v77 = 0;
  std::vector<SrmSecureProperty>::reserve(&v42, (unsigned int)pAclInformation);
  v14 = 0;
  v15 = (char *)*((_QWORD *)&v42 + 1);
  if ( (_DWORD)pAclInformation )
  {
    while ( 1 )
    {
      pAce = 0;
      if ( !GetAce(v4, v14, &pAce) )
      {
        v34 = GetLastFailureAsHRESULT(v17, v16);
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v76, v34);
        v35 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v76);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v76, 0xA63u, v35, 0);
      }
      v77 = 0;
      v13 = (char *)pAce;
      if ( *(_BYTE *)pAce != 18 )
        goto LABEL_29;
      LengthSid = GetLengthSid((char *)pAce + 8);
      v19 = (unsigned int *)((char *)pAce + LengthSid + 8);
      v20 = *((_BYTE *)pAce + 1) & 0x10;
      v21 = (_WORD *)((char *)v19 + *v19);
      if ( !v21 || !*v21 )
      {
        CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v76, -2147200234);
        v38 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v76);
        CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v76, 0xA6Fu, v38, 0);
      }
      v77 = 0;
      if ( (v40 & 1) != 0 )
      {
        v40 &= ~1u;
        if ( v80 >= 8 )
          operator delete(Block);
        v80 = 7;
        v79 = 0;
        LOWORD(Block) = 0;
      }
      std::wstring::wstring(v73, v21);
      v75 = v20 != 0;
      std::_Tree<std::_Tmap_traits<std::wstring,bool,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::insert<std::pair<std::wstring,bool>>(
        v47,
        &pExceptionObject,
        v73);
      if ( v74 >= 8 )
        operator delete(v73[0]);
      v74 = 7;
      v13 = 0;
      v73[2] = 0;
      LOWORD(v73[0]) = 0;
      if ( v46 )
        goto LABEL_24;
      if ( !*((_BYTE *)pExceptionObject + 64) )
        break;
LABEL_28:
      v4 = pAcl;
LABEL_29:
      if ( ++v14 >= (unsigned int)pAclInformation )
        goto LABEL_30;
    }
    *((_BYTE *)pExceptionObject + 64) = 1;
LABEL_24:
    v22 = (v20 != 0 ? 0x2000 : 0) | ((v19[2] & 0x10000 | (v19[2] >> 3) & 0x4000) >> 2);
    v23 = *((unsigned __int16 *)v19 + 2);
    v13 = (char *)((unsigned int)*((unsigned __int16 *)v19 + 2) - 1);
    if ( *((_WORD *)v19 + 2) == 1
      || (v13 = (char *)((unsigned int)*((unsigned __int16 *)v19 + 2) - 2), *((_WORD *)v19 + 2) == 2) )
    {
      if ( v19[3] == 1 )
      {
        v30 = *(_QWORD *)((char *)v19 + v19[4]);
        Buffer = 0;
        memset_0(v82, 0, sizeof(v82));
        _i64tow_s(v30, &Buffer, 0x40u, 10);
        memset_0(v67, 0, 0x58u);
        v69 = 7;
        v68 = 0;
        LOWORD(v67[0]) = 0;
        v72 = 7;
        v71 = 0;
        LOWORD(v70) = 0;
        std::vector<SrmSecureProperty>::push_back(&v42, v67);
        if ( v72 >= 8 )
          operator delete(v70);
        v72 = 7;
        v71 = 0;
        LOWORD(v70) = 0;
        if ( v69 >= 8 )
          operator delete(v67[0]);
        v69 = 7;
        v68 = 0;
        LOWORD(v67[0]) = 0;
        v15 = (char *)*((_QWORD *)&v42 + 1);
        v31 = -1;
        do
          ++v31;
        while ( v21[v31] );
        std::wstring::assign((void *)(*((_QWORD *)&v42 + 1) - 88LL), v21);
        v32 = -1;
        do
          ++v32;
        while ( *(_WORD *)&v82[2 * v32 - 2] );
        std::wstring::assign(v15 - 48, &Buffer);
        *((_DWORD *)v15 - 2) = v22;
        *((_DWORD *)v15 - 1) = 6;
      }
    }
    else if ( *((_WORD *)v19 + 2) == 3 )
    {
      v60 = 7;
      v59 = 0;
      LOWORD(Src[0]) = 0;
      LOBYTE(v23) = 0;
      for ( i = 0; i < v19[3]; ++i )
      {
        v28 = (char *)v19 + v19[i + 4];
        if ( (_BYTE)v23 )
          std::wstring::append(Src, v23, 124);
        std::wstring::append(Src, v28);
        LOBYTE(v23) = 1;
      }
      memset_0(v61, 0, 0x58u);
      v63 = 7;
      v62 = 0;
      LOWORD(v61[0]) = 0;
      v66 = 7;
      v65 = 0;
      LOWORD(v64) = 0;
      std::vector<SrmSecureProperty>::push_back(&v42, v61);
      if ( v66 >= 8 )
        operator delete(v64);
      v66 = 7;
      v65 = 0;
      LOWORD(v64) = 0;
      if ( v63 >= 8 )
        operator delete(v61[0]);
      v63 = 7;
      v62 = 0;
      LOWORD(v61[0]) = 0;
      v15 = (char *)*((_QWORD *)&v42 + 1);
      v29 = -1;
      do
        ++v29;
      while ( v21[v29] );
      std::wstring::assign((void *)(*((_QWORD *)&v42 + 1) - 88LL), v21);
      std::wstring::swap(v15 - 48, Src);
      *((_DWORD *)v15 - 2) = v22;
      *((_DWORD *)v15 - 1) = (v19[3] > 1) + 4;
      if ( v60 >= 8 )
        operator delete(Src[0]);
      v60 = 7;
      v59 = 0;
      LOWORD(Src[0]) = 0;
    }
    else
    {
      LODWORD(v39) = *((unsigned __int16 *)v19 + 2);
      CSrmFunctionTracer::Trace(
        (CSrmFunctionTracer *)&v76,
        0x3Cu,
        0xACCu,
        L"Claim ignored because it's not a supported type(name : type): %s : %d",
        v21,
        v39);
    }
    goto LABEL_28;
  }
LABEL_30:
  if ( &v42 == (__int128 *)a3 )
  {
    v25 = (char *)v42;
  }
  else
  {
    v24 = (char *)v42;
    v25 = *a3;
    *(_QWORD *)&v42 = *a3;
    *a3 = v24;
    v26 = v15;
    v15 = a3[1];
    *((_QWORD *)&v42 + 1) = v15;
    a3[1] = v26;
    v13 = v43;
    v43 = a3[2];
    a3[2] = v13;
  }
  if ( v25 )
  {
    for ( j = v25; j != v15; j += 88 )
      std::_Dest_val<std::allocator<CPropertyValue>,CPropertyValue>(v13, j);
    operator delete(v25);
  }
  v42 = 0;
  v43 = 0;
  std::_Tree<std::_Tmap_traits<std::wstring,unsigned long,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned long,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>(v47);
  v76 = &CSrmFunctionTracer::`vftable';
LABEL_7:
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v76);
}

```

## disassembly

```asm
0x180083c24  mov     [rsp-8+arg_8], rbx
0x180083c29  push    rbp
0x180083c2a  push    rsi
0x180083c2b  push    rdi
0x180083c2c  push    r12
0x180083c2e  push    r13
0x180083c30  push    r14
0x180083c32  push    r15
0x180083c34  lea     rbp, [rsp-2D0h]
0x180083c3c  sub     rsp, 3D0h
0x180083c43  mov     rax, cs:__security_cookie
0x180083c4a  xor     rax, rsp
0x180083c4d  mov     [rbp+300h+var_40], rax
0x180083c54  mov     r14, r8
0x180083c57  mov     r15, rcx
0x180083c5a  mov     [rsp+400h+var_3C8], rcx
0x180083c5f  xor     edi, edi
0x180083c61  mov     dword ptr [rsp+400h+var_3D0], edi
0x180083c65  lea     rax, [rbp+300h+var_360]
0x180083c69  mov     [rsp+400h+pExceptionObject], rax
0x180083c6e  lea     rax, aBaseFsFsrmUtil_11; "base\\fs\\fsrm\\utilities\\security\\sr"...
0x180083c75  mov     [rbp+300h+var_360], rax
0x180083c79  lea     rax, aSrmparseresour; "SrmParseResourceControlList"
0x180083c80  mov     [rbp+300h+var_358], rax
0x180083c84  lea     rax, aSecsecrc; "SECSECRC"
0x180083c8b  mov     [rbp+300h+var_350], rax
0x180083c8f  mov     [rbp+300h+var_348], 0A47h
0x180083c96  mov     [rbp+300h+var_344], 11h
0x180083c9d  mov     [rbp+300h+var_340], 0FFh
0x180083ca4  mov     [rbp+300h+var_2D8], 1000000h
0x180083cab  xor     edx, edx; Val
0x180083cad  lea     r8d, [rdi+60h]; Size
0x180083cb1  lea     rcx, [rbp+300h+var_338]; void *
0x180083cb5  call    memset_0
0x180083cba  nop
0x180083cbb  xor     r8d, r8d
0x180083cbe  lea     rdx, [rbp+300h+var_360]
0x180083cc2  lea     rcx, [rbp+300h+var_1A0]
0x180083cc9  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180083cce  nop
0x180083ccf  mov     rsi, [r14+8]
0x180083cd3  mov     rbx, [r14]
0x180083cd6  cmp     rbx, rsi
0x180083cd9  jz      short loc_180083CF5
0x180083cdb  mov     rdi, rbx
0x180083cde  mov     rdx, rdi
0x180083ce1  call    ??$_Dest_val@V?$allocator@VCPropertyValue@@@std@@VCPropertyValue@@@std@@YAXAEAV?$allocator@VCPropertyValue@@@0@PEAVCPropertyValue@@@Z; std::_Dest_val<std::allocator<CPropertyValue>,CPropertyValue>(std::allocator<CPropertyValue> &,CPropertyValue *)
0x180083ce6  add     rdi, 58h ; 'X'
0x180083cea  cmp     rdi, rsi
0x180083ced  jnz     short loc_180083CDE
0x180083cef  mov     [r14+8], rbx
0x180083cf3  xor     edi, edi
0x180083cf5  test    r15, r15
0x180083cf8  jnz     short loc_180083D3E
0x180083cfa  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180083d01  mov     [rbp+300h+var_1A0], rax
0x180083d08  lea     rcx, [rbp+300h+var_1A0]; this
0x180083d0f  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180083d14  mov     rcx, [rbp+300h+var_40]
0x180083d1b  xor     rcx, rsp; StackCookie
0x180083d1e  call    __security_check_cookie
0x180083d23  mov     rbx, [rsp+400h+arg_8]
0x180083d2b  add     rsp, 3D0h
0x180083d32  pop     r15
0x180083d34  pop     r14
0x180083d36  pop     r13
0x180083d38  pop     r12
0x180083d3a  pop     rdi
0x180083d3b  pop     rsi
0x180083d3c  pop     rbp
0x180083d3d  retn
0x180083d3e  xor     eax, eax
0x180083d40  mov     [rbp+300h+pAclInformation], rax
0x180083d44  mov     [rbp+300h+var_2C8], eax
0x180083d47  mov     [rbp+300h+var_370], rdi
0x180083d4b  lea     ecx, [rax+50h]; Size
0x180083d4e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180083d53  test    rax, rax
0x180083d56  jz      loc_1800842FD
0x180083d5c  mov     [rbp+300h+var_378], rax
0x180083d60  mov     [rax], rax
0x180083d63  mov     rcx, [rbp+300h+var_378]
0x180083d67  mov     [rax+8], rcx
0x180083d6b  mov     rcx, [rbp+300h+var_378]
0x180083d6f  mov     [rax+10h], rcx
0x180083d73  mov     word ptr [rax+48h], 101h
0x180083d79  xorps   xmm0, xmm0
0x180083d7c  movdqu  [rsp+400h+var_3C0], xmm0
0x180083d82  mov     [rsp+400h+var_3B0], rdi
0x180083d87  mov     eax, [rbp+300h+var_198]
0x180083d8d  mov     [rbp+300h+var_198], eax
0x180083d93  mov     r9d, 2; dwAclInformationClass
0x180083d99  lea     r8d, [r9+0Ah]; nAclInformationLength
0x180083d9d  lea     rdx, [rbp+300h+pAclInformation]; pAclInformation
0x180083da1  mov     rcx, r15; pAcl
0x180083da4  call    cs:__imp_GetAclInformation
0x180083daa  test    eax, eax
0x180083dac  jz      loc_180084319
0x180083db2  mov     [rbp+300h+var_198], edi
0x180083db8  mov     edx, dword ptr [rbp+300h+pAclInformation]
0x180083dbb  lea     rcx, [rsp+400h+var_3C0]
0x180083dc0  call    ?reserve@?$vector@USrmSecureProperty@@V?$allocator@USrmSecureProperty@@@std@@@std@@QEAAX_K@Z; std::vector<SrmSecureProperty>::reserve(unsigned __int64)
0x180083dc5  mov     r13d, edi
0x180083dc8  mov     rsi, qword ptr [rsp+400h+var_3C0+8]
0x180083dcd  cmp     dword ptr [rbp+300h+pAclInformation], edi
0x180083dd0  jbe     loc_180083F9C
0x180083dd6  mov     [rsp+400h+pAce], rdi
0x180083ddb  mov     eax, [rbp+300h+var_198]
0x180083de1  mov     [rbp+300h+var_198], eax
0x180083de7  lea     r8, [rsp+400h+pAce]; pAce
0x180083dec  mov     edx, r13d; dwAceIndex
0x180083def  mov     rcx, r15; pAcl
0x180083df2  call    cs:__imp_GetAce
0x180083df8  test    eax, eax
0x180083dfa  jz      loc_1800842C6
0x180083e00  mov     [rbp+300h+var_198], edi
0x180083e06  mov     rcx, [rsp+400h+pAce]
0x180083e0b  cmp     byte ptr [rcx], 12h
0x180083e0e  jnz     loc_180083F8F
0x180083e14  add     rcx, 8; pSid
0x180083e18  call    cs:__imp_GetLengthSid
0x180083e1e  mov     eax, eax
0x180083e20  mov     rcx, [rsp+400h+pAce]
0x180083e25  lea     rbx, [rcx+8]
0x180083e29  add     rbx, rax
0x180083e2c  mov     r15d, [rbx]
0x180083e2f  mov     dil, [rcx+1]
0x180083e33  and     dil, 10h
0x180083e37  setnz   r12b
0x180083e3b  mov     eax, [rbp+300h+var_198]
0x180083e41  mov     [rbp+300h+var_198], eax
0x180083e47  xor     ecx, ecx
0x180083e49  add     r15, rbx
0x180083e4c  jz      loc_180084350
0x180083e52  cmp     [r15], cx
0x180083e56  jz      loc_180084350
0x180083e5c  mov     [rbp+300h+var_198], ecx
0x180083e62  mov     eax, dword ptr [rsp+400h+var_3D0]
0x180083e66  test    al, 1
0x180083e68  jz      short loc_180083EA2
0x180083e6a  and     eax, 0FFFFFFFEh
0x180083e6d  mov     dword ptr [rsp+400h+var_3D0], eax
0x180083e71  cmp     [rbp+300h+var_D8], 8
0x180083e79  jb      short loc_180083E89
0x180083e7b  mov     rcx, [rbp+300h+Block]; Block
0x180083e82  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180083e87  xor     ecx, ecx
0x180083e89  mov     [rbp+300h+var_D8], 7
0x180083e94  mov     [rbp+300h+var_E0], rcx
0x180083e9b  mov     word ptr [rbp+300h+Block], cx
0x180083ea2  mov     rdx, r15
0x180083ea5  lea     rcx, [rbp+300h+var_1D0]; void *
0x180083eac  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180083eb1  nop
0x180083eb2  mov     [rbp+300h+var_1A8], r12b
0x180083eb9  lea     r8, [rbp+300h+var_1D0]
0x180083ec0  lea     rdx, [rsp+400h+pExceptionObject]
0x180083ec5  lea     rcx, [rbp+300h+var_380]
0x180083ec9  call    ??$insert@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NU?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NU?$CCaseInsensitiveLess@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@2@$0A@@std@@@std@@@std@@_N@1@$$QEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,bool,CCaseInsensitiveLess<std::wstring,std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::insert<std::pair<std::wstring,bool>>(std::pair<std::wstring,bool> &&)
0x180083ece  nop
0x180083ecf  cmp     [rbp+300h+var_1B8], 8
0x180083ed7  jb      short loc_180083EE5
0x180083ed9  mov     rcx, [rbp+300h+var_1D0]; Block
0x180083ee0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180083ee5  mov     r8d, 7
0x180083eeb  mov     [rbp+300h+var_1B8], r8
0x180083ef2  xor     ecx, ecx
0x180083ef4  mov     [rbp+300h+var_1C0], rcx
0x180083efb  mov     word ptr [rbp+300h+var_1D0], cx
0x180083f02  cmp     [rsp+400h+var_390], cl
0x180083f06  jnz     short loc_180083F16
0x180083f08  mov     rax, [rsp+400h+pExceptionObject]
0x180083f0d  cmp     [rax+40h], cl
0x180083f10  jnz     short loc_180083F88
0x180083f12  mov     byte ptr [rax+40h], 1
0x180083f16  mov     eax, [rbx+8]
0x180083f19  mov     r12d, eax
0x180083f1c  shr     r12d, 3
0x180083f20  and     r12d, 4000h
0x180083f27  and     eax, 10000h
0x180083f2c  or      r12d, eax
0x180083f2f  shr     r12d, 2
0x180083f33  neg     dil
0x180083f36  sbb     eax, eax
0x180083f38  and     eax, 2000h
0x180083f3d  or      r12d, eax
0x180083f40  movzx   edx, word ptr [rbx+4]
0x180083f44  mov     ecx, edx
0x180083f46  sub     ecx, 1
0x180083f49  jz      loc_18008412E
0x180083f4f  sub     ecx, 1
0x180083f52  jz      loc_18008412E
0x180083f58  cmp     ecx, 1
0x180083f5b  jz      loc_180083FE1
0x180083f61  mov     dword ptr [rsp+400h+var_3D8], edx
0x180083f65  mov     [rsp+400h+var_3E0], r15
0x180083f6a  lea     r9, aClaimIgnoredBe; "Claim ignored because it's not a suppor"...
0x180083f71  mov     edx, 3Ch ; '<'; unsigned int
0x180083f76  mov     r8d, 0ACCh; unsigned int
0x180083f7c  lea     rcx, [rbp+300h+var_1A0]; this
0x180083f83  call    ?Trace@CSrmFunctionTracer@@QEAAXKKPEBGZZ; CSrmFunctionTracer::Trace(ulong,ulong,ushort const *,...)
0x180083f88  xor     edi, edi
0x180083f8a  mov     r15, [rsp+400h+var_3C8]
0x180083f8f  inc     r13d
0x180083f92  cmp     r13d, dword ptr [rbp+300h+pAclInformation]
0x180083f96  jb      loc_180083DD6
0x180083f9c  lea     rax, [rsp+400h+var_3C0]
0x180083fa1  cmp     rax, r14
0x180083fa4  jz      loc_18008426D
0x180083faa  mov     rax, qword ptr [rsp+400h+var_3C0]
0x180083faf  mov     rdi, [r14]
0x180083fb2  mov     qword ptr [rsp+400h+var_3C0], rdi
0x180083fb7  mov     [r14], rax
0x180083fba  mov     rax, rsi
0x180083fbd  mov     rsi, [r14+8]
0x180083fc1  mov     qword ptr [rsp+400h+var_3C0+8], rsi
0x180083fc6  mov     [r14+8], rax
0x180083fca  mov     rcx, [rsp+400h+var_3B0]
0x180083fcf  mov     rax, [r14+10h]
0x180083fd3  mov     [rsp+400h+var_3B0], rax
0x180083fd8  mov     [r14+10h], rcx
0x180083fdc  jmp     loc_180084272
0x180083fe1  mov     [rbp+300h+var_2A8], r8
0x180083fe5  xor     esi, esi
0x180083fe7  mov     [rbp+300h+var_2B0], rsi
0x180083feb  mov     word ptr [rbp+300h+Src], si
0x180083fef  mov     dl, sil
0x180083ff2  mov     edi, esi
0x180083ff4  cmp     [rbx+0Ch], esi
0x180083ff7  jbe     short loc_18008402C
0x180083ff9  mov     eax, edi
0x180083ffb  mov     esi, [rbx+rax*4+10h]
0x180083fff  add     rsi, rbx
0x180084002  test    dl, dl
0x180084004  jz      short loc_180084015
0x180084006  mov     r8d, 7Ch ; '|'
0x18008400c  lea     rcx, [rbp+300h+Src]
0x180084010  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_KG@Z; std::wstring::append(unsigned __int64,ushort)
0x180084015  mov     rdx, rsi; void *
0x180084018  lea     rcx, [rbp+300h+Src]; Src
0x18008401c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x180084021  mov     dl, 1
0x180084023  inc     edi
0x180084025  cmp     edi, [rbx+0Ch]
0x180084028  jb      short loc_180083FF9
0x18008402a  xor     esi, esi
0x18008402c  xor     edx, edx; Val
0x18008402e  lea     r8d, [rdx+58h]; Size
0x180084032  lea     rcx, [rbp+300h+var_290]; void *
0x180084036  call    memset_0
0x18008403b  mov     edi, 7
0x180084040  mov     [rbp+300h+var_278], rdi
0x180084047  mov     [rbp+300h+var_280], rsi
0x18008404e  mov     word ptr [rbp+300h+var_290], si
0x180084052  mov     [rbp+300h+var_250], rdi
0x180084059  mov     [rbp+300h+var_258], rsi
0x180084060  mov     word ptr [rbp+300h+var_268], si
0x180084067  lea     rdx, [rbp+300h+var_290]
0x18008406b  lea     rcx, [rsp+400h+var_3C0]
0x180084070  call    ?push_back@?$vector@USrmSecureProperty@@V?$allocator@USrmSecureProperty@@@std@@@std@@QEAAX$$QEAUSrmSecureProperty@@@Z; std::vector<SrmSecureProperty>::push_back(SrmSecureProperty &&)
0x180084075  nop
0x180084076  cmp     [rbp+300h+var_250], 8
0x18008407e  jb      short loc_18008408C
0x180084080  mov     rcx, [rbp+300h+var_268]; Block
0x180084087  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18008408c  mov     [rbp+300h+var_250], rdi
0x180084093  mov     [rbp+300h+var_258], rsi
0x18008409a  mov     word ptr [rbp+300h+var_268], si
0x1800840a1  cmp     [rbp+300h+var_278], 8
0x1800840a9  jb      short loc_1800840B4
0x1800840ab  mov     rcx, [rbp+300h+var_290]; Block
0x1800840af  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800840b4  mov     [rbp+300h+var_278], rdi
0x1800840bb  mov     [rbp+300h+var_280], rsi
0x1800840c2  mov     word ptr [rbp+300h+var_290], si
0x1800840c6  mov     rsi, qword ptr [rsp+400h+var_3C0+8]
0x1800840cb  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800840cf  xor     eax, eax
0x1800840d1  inc     r8
0x1800840d4  cmp     [r15+r8*2], ax
0x1800840d9  jnz     short loc_1800840D1
0x1800840db  mov     rdx, r15; Src
0x1800840de  lea     rcx, [rsi-58h]; void *
0x1800840e2  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800840e7  lea     rcx, [rsi-30h]
0x1800840eb  lea     rdx, [rbp+300h+Src]
0x1800840ef  call    ?swap@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXAEAV12@@Z; std::wstring::swap(std::wstring &)
0x1800840f4  mov     [rsi-8], r12d
0x1800840f8  xor     eax, eax
0x1800840fa  cmp     dword ptr [rbx+0Ch], 1
0x1800840fe  setnbe  al
0x180084101  add     eax, 4
0x180084104  mov     [rsi-4], eax
0x180084107  cmp     [rbp+300h+var_2A8], 8
0x18008410c  jb      short loc_180084117
0x18008410e  mov     rcx, [rbp+300h+Src]; Block
0x180084112  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180084117  mov     [rbp+300h+var_2A8], 7
0x18008411f  xor     edi, edi
0x180084121  mov     [rbp+300h+var_2B0], rdi
  ... truncated ...
```
