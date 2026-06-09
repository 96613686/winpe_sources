# ATL::CDacl::Copy(_ACL const &)

- ea: `0x180021844`
- end: `0x180021b91`
- name: `?Copy@CDacl@ATL@@AEAAXAEBU_ACL@@@Z`
- size: `845`
- prototype: `void(ATL::CDacl *__hidden this, const struct _ACL *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180021ba0`

## callees

- `0x180021844`
- `0x1800228ec`
- `0x180022a60`
- `0x180023ad4`
- `0x180027910`
- `0x180052974`
- `0x1800529a0`
- `0x180053098`
- `0x18006e168`
- `0x18006e5f4`
- `0x180082a40`
- `0x180088010`

## import_xrefs

- `msvcrt!free` at `0x180021930`
- `msvcrt!free` at `0x180021930`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180021950`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180021974`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180021950`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180021974`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800219ab`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800219ab`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall ATL::CDacl::Copy(ATL::CDacl *this, struct _ACL *a2)
{
  ATL::CDacl *v3; // rbx
  ATL::CDacl::CAccessAce *v4; // rsi
  DWORD i; // edi
  unsigned int v6; // r12d
  char *v7; // rcx
  const struct _GUID *v8; // r14
  const struct _GUID *v9; // rsi
  ATL::CDacl::CAccessAce *v10; // rax
  ATL::CDacl::CAccessAce *v11; // [rsp+48h] [rbp-100h] BYREF
  int v12; // [rsp+50h] [rbp-F8h] BYREF
  LPVOID pAce; // [rsp+58h] [rbp-F0h] BYREF
  ATL::CDacl *v14; // [rsp+60h] [rbp-E8h]
  PACL pAcl; // [rsp+68h] [rbp-E0h]
  ATL::CDacl::CAccessAce *v16; // [rsp+70h] [rbp-D8h]
  __int64 pAclInformation; // [rsp+78h] [rbp-D0h] BYREF
  int v18; // [rsp+80h] [rbp-C8h]
  _QWORD v19[9]; // [rsp+90h] [rbp-B8h] BYREF
  char v20; // [rsp+DCh] [rbp-6Ch]
  int v21; // [rsp+E0h] [rbp-68h]
  __int64 v22; // [rsp+E8h] [rbp-60h] BYREF
  __int64 v23; // [rsp+F0h] [rbp-58h] BYREF
  __int64 v24; // [rsp+F8h] [rbp-50h] BYREF
  __int64 v25; // [rsp+100h] [rbp-48h] BYREF

  v3 = this;
  v14 = this;
  if ( !a2 )
  {
    (*(void (__fastcall **)(ATL::CDacl *))(*(_QWORD *)this + 16LL))(this);
    *((_BYTE *)v3 + 16) = 1;
    return;
  }
  pAcl = a2;
  pAclInformation = 0;
  v18 = 0;
  v12 = 0;
  pAce = 0;
  v19[0] = &ATL::CSid::`vftable';
  v20 = 0;
  v21 = 7;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v22);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v23);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v24);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v25);
  v4 = 0;
  v11 = 0;
  free(*((void **)v3 + 1));
  *((_QWORD *)v3 + 1) = 0;
  if ( !GetAclInformation(a2, &pAclInformation, 0xCu, AclSizeInformation)
    || !GetAclInformation(a2, &v12, 4u, AclRevisionInformation) )
  {
LABEL_34:
    ATL::AtlThrowLastWin32();
  }
  *((_DWORD *)v3 + 5) = v12;
  for ( i = 0; i < (unsigned int)pAclInformation; ++i )
  {
    if ( !GetAce(pAcl, i, &pAce) )
      goto LABEL_34;
    v6 = *((_DWORD *)pAce + 1);
    if ( !*(_BYTE *)pAce || *(_BYTE *)pAce == 1 )
    {
      ATL::CSid::operator=((__int64)v19, (char *)pAce + 8);
      try
      {
        v10 = (ATL::CDacl::CAccessAce *)operator new(0x98u);
        v16 = v10;
        if ( v10 )
          v10 = (ATL::CDacl::CAccessAce *)ATL::CDacl::CAccessAce::CAccessAce(
                                            v10,
                                            (const struct ATL::CSid *)v19,
                                            v6,
                                            *((_BYTE *)pAce + 1),
                                            *(_BYTE *)pAce == 0);
        v11 = v10;
      }
      catch ( ... )
      {
        v3 = v14;
        v10 = v11;
      }
    }
    else
    {
      if ( (unsigned int)*(unsigned __int8 *)pAce - 5 > 1 )
        continue;
      v7 = (char *)pAce + 44;
      if ( (*((_DWORD *)pAce + 2) & 1) != 0 )
        v8 = (const struct _GUID *)((char *)pAce + 12);
      else
        v8 = 0;
      if ( (*((_DWORD *)pAce + 2) & 1) == 0 )
        v7 = (char *)pAce + 28;
      if ( (*((_BYTE *)pAce + 8) & 2) != 0 )
      {
        v9 = (const struct _GUID *)((char *)pAce + (v8 != 0 ? 28LL : 12LL));
      }
      else
      {
        v9 = 0;
        v7 -= 16;
      }
      ATL::CSid::operator=((__int64)v19, v7);
      try
      {
        v10 = (ATL::CDacl::CAccessAce *)operator new(0xA8u);
        v16 = v10;
        if ( v10 )
          v10 = (ATL::CDacl::CAccessAce *)ATL::CDacl::CAccessObjectAce::CAccessObjectAce(
                                            v10,
                                            (const struct ATL::CSid *)v19,
                                            v6,
                                            *((_BYTE *)pAce + 1),
                                            *(_BYTE *)pAce == 5,
                                            v8,
                                            v9);
        v11 = v10;
      }
      catch ( ... )
      {
        v3 = v14;
        v10 = v11;
      }
    }
    if ( !v10 )
      ATL::PrivateAtlThrow(0x8007000E);
    ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::Add(
      (char *)v3 + 24,
      &v11);
    v4 = v11;
  }
  if ( v4 )
    (**(void (__fastcall ***)(ATL::CDacl::CAccessAce *, __int64))v4)(v4, 1);
  v19[0] = &ATL::CSid::`vftable';
  ATL::CStringData::Release((ATL::CStringData *)(v25 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v24 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v23 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v22 - 24));
}

```

## disassembly

```asm
0x180021844  mov     [rsp+arg_10], rbx
0x180021849  push    rsi
0x18002184a  push    rdi
0x18002184b  push    r12
0x18002184d  push    r14
0x18002184f  push    r15
0x180021851  sub     rsp, 120h
0x180021858  mov     rax, cs:__security_cookie
0x18002185f  xor     rax, rsp
0x180021862  mov     [rsp+148h+var_38], rax
0x18002186a  mov     rdi, rdx
0x18002186d  mov     rbx, rcx
0x180021870  mov     [rsp+148h+var_E8], rcx
0x180021875  test    rdx, rdx
0x180021878  jnz     short loc_1800218B3
0x18002187a  mov     rax, [rcx]
0x18002187d  mov     rax, [rax+10h]
0x180021881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021886  mov     byte ptr [rbx+10h], 1
0x18002188a  mov     rcx, [rsp+148h+var_38]
0x180021892  xor     rcx, rsp; StackCookie
0x180021895  call    __security_check_cookie
0x18002189a  mov     rbx, [rsp+148h+arg_10]
0x1800218a2  add     rsp, 120h
0x1800218a9  pop     r15
0x1800218ab  pop     r14
0x1800218ad  pop     r12
0x1800218af  pop     rdi
0x1800218b0  pop     rsi
0x1800218b1  retn
0x1800218b3  mov     [rsp+148h+pAcl], rdi
0x1800218b8  xor     eax, eax
0x1800218ba  mov     [rsp+148h+pAclInformation], rax
0x1800218bf  mov     [rsp+148h+var_C8], eax
0x1800218c6  mov     [rsp+148h+var_F8], eax
0x1800218ca  mov     [rsp+148h+pAce], rax
0x1800218cf  lea     r15, ??_7CSid@ATL@@6B@; const ATL::CSid::`vftable'
0x1800218d6  mov     [rsp+148h+var_B8], r15
0x1800218de  mov     [rsp+148h+var_6C], al
0x1800218e5  mov     [rsp+148h+var_68], 7
0x1800218f0  lea     rcx, [rsp+148h+var_60]
0x1800218f8  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800218fd  lea     rcx, [rsp+148h+var_58]
0x180021905  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18002190a  lea     rcx, [rsp+148h+var_50]
0x180021912  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180021917  lea     rcx, [rsp+148h+var_48]
0x18002191f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180021924  nop
0x180021925  xor     esi, esi
0x180021927  mov     [rsp+148h+var_100], rsi
0x18002192c  mov     rcx, [rbx+8]; Block
0x180021930  call    cs:__imp_free
0x180021937  nop     dword ptr [rax+rax+00h]
0x18002193c  mov     [rbx+8], rsi
0x180021940  lea     r9d, [rsi+2]; dwAclInformationClass
0x180021944  lea     r8d, [rsi+0Ch]; nAclInformationLength
0x180021948  lea     rdx, [rsp+148h+pAclInformation]; pAclInformation
0x18002194d  mov     rcx, rdi; pAcl
0x180021950  call    cs:__imp_GetAclInformation
0x180021957  nop     dword ptr [rax+rax+00h]
0x18002195c  test    eax, eax
0x18002195e  jz      loc_180021B8B
0x180021964  lea     r9d, [rsi+1]; dwAclInformationClass
0x180021968  lea     r8d, [rsi+4]; nAclInformationLength
0x18002196c  lea     rdx, [rsp+148h+var_F8]; pAclInformation
0x180021971  mov     rcx, rdi; pAcl
0x180021974  call    cs:__imp_GetAclInformation
0x18002197b  nop     dword ptr [rax+rax+00h]
0x180021980  test    eax, eax
0x180021982  jz      loc_180021B8B
0x180021988  mov     eax, [rsp+148h+var_F8]
0x18002198c  mov     [rbx+14h], eax
0x18002198f  xor     edi, edi
0x180021991  mov     [rsp+148h+var_108], edi
0x180021995  cmp     edi, dword ptr [rsp+148h+pAclInformation]
0x180021999  jnb     loc_180021B21
0x18002199f  lea     r8, [rsp+148h+pAce]; pAce
0x1800219a4  mov     edx, edi; dwAceIndex
0x1800219a6  mov     rcx, [rsp+148h+pAcl]; pAcl
0x1800219ab  call    cs:__imp_GetAce
0x1800219b2  nop     dword ptr [rax+rax+00h]
0x1800219b7  test    eax, eax
0x1800219b9  jz      loc_180021B8B
0x1800219bf  mov     rdx, [rsp+148h+pAce]
0x1800219c4  mov     r12d, [rdx+4]
0x1800219c8  movzx   ecx, byte ptr [rdx]
0x1800219cb  test    ecx, ecx
0x1800219cd  jz      loc_180021AB0
0x1800219d3  sub     ecx, 1
0x1800219d6  jz      loc_180021AB0
0x1800219dc  sub     ecx, 4
0x1800219df  jz      short loc_1800219EA
0x1800219e1  cmp     ecx, 1
0x1800219e4  jnz     loc_180021B1A
0x1800219ea  lea     rcx, [rdx+2Ch]
0x1800219ee  mov     r8d, [rdx+8]
0x1800219f2  and     r8d, 1
0x1800219f6  jz      short loc_1800219FE
0x1800219f8  lea     r14, [rdx+0Ch]
0x1800219fc  jmp     short loc_180021A01
0x1800219fe  xor     r14d, r14d
0x180021a01  lea     rax, [rcx-10h]
0x180021a05  test    r8d, r8d
0x180021a08  cmovz   rcx, rax
0x180021a0c  test    byte ptr [rdx+8], 2
0x180021a10  jz      short loc_180021A27
0x180021a12  mov     rax, r14
0x180021a15  neg     rax
0x180021a18  sbb     rsi, rsi
0x180021a1b  and     esi, 10h
0x180021a1e  add     rsi, 0Ch
0x180021a22  add     rsi, rdx
0x180021a25  jmp     short loc_180021A2D
0x180021a27  xor     esi, esi
0x180021a29  add     rcx, 0FFFFFFFFFFFFFFF0h
0x180021a2d  mov     rdx, rcx
0x180021a30  lea     rcx, [rsp+148h+var_B8]
0x180021a38  call    ??4CSid@ATL@@QEAAAEAV01@AEBU_SID@@@Z; ATL::CSid::operator=(_SID const &)
0x180021a3d  nop
0x180021a3e  mov     ecx, 0A8h; dwBytes
0x180021a43  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021a48  mov     [rsp+148h+var_D8], rax
0x180021a4d  test    rax, rax
0x180021a50  jz      short loc_180021A84
0x180021a52  mov     r9, [rsp+148h+pAce]
0x180021a57  cmp     byte ptr [r9], 5
0x180021a5b  setz    cl
0x180021a5e  mov     [rsp+148h+var_118], rsi; struct _GUID *
0x180021a63  mov     [rsp+148h+var_120], r14; struct _GUID *
0x180021a68  mov     [rsp+148h+var_128], cl; bool
0x180021a6c  mov     r9b, [r9+1]; unsigned __int8
0x180021a70  mov     r8d, r12d; unsigned int
0x180021a73  lea     rdx, [rsp+148h+var_B8]; struct ATL::CSid *
0x180021a7b  mov     rcx, rax; this
0x180021a7e  call    ??0CAccessObjectAce@CDacl@ATL@@QEAA@AEBVCSid@2@KE_NPEBU_GUID@@2@Z; ATL::CDacl::CAccessObjectAce::CAccessObjectAce(ATL::CSid const &,ulong,uchar,bool,_GUID const *,_GUID const *)
0x180021a83  nop
0x180021a84  mov     [rsp+148h+var_100], rax
0x180021a89  jmp     short loc_180021AA0
0x180021a8b  mov     rbx, [rsp+148h+var_E8]
0x180021a90  mov     edi, [rsp+148h+var_108]
0x180021a94  mov     rax, [rsp+148h+var_100]
0x180021a99  lea     r15, ??_7CSid@ATL@@6B@; const ATL::CSid::`vftable'
0x180021aa0  test    rax, rax
0x180021aa3  jnz     short loc_180021B07
0x180021aa5  mov     ecx, 8007000Eh; unsigned int
0x180021aaa  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x180021ab0  add     rdx, 8
0x180021ab4  lea     rcx, [rsp+148h+var_B8]
0x180021abc  call    ??4CSid@ATL@@QEAAAEAV01@AEBU_SID@@@Z; ATL::CSid::operator=(_SID const &)
0x180021ac1  nop
0x180021ac2  mov     ecx, 98h; dwBytes
0x180021ac7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021acc  mov     [rsp+148h+var_D8], rax
0x180021ad1  test    rax, rax
0x180021ad4  jz      short loc_180021AFE
0x180021ad6  mov     r9, [rsp+148h+pAce]
0x180021adb  cmp     byte ptr [r9], 0
0x180021adf  setz    cl
0x180021ae2  mov     [rsp+148h+var_128], cl; bool
0x180021ae6  mov     r9b, [r9+1]; unsigned __int8
0x180021aea  mov     r8d, r12d; unsigned int
0x180021aed  lea     rdx, [rsp+148h+var_B8]; struct ATL::CSid *
0x180021af5  mov     rcx, rax; this
0x180021af8  call    ??0CAccessAce@CDacl@ATL@@QEAA@AEBVCSid@2@KE_N@Z; ATL::CDacl::CAccessAce::CAccessAce(ATL::CSid const &,ulong,uchar,bool)
0x180021afd  nop
0x180021afe  mov     [rsp+148h+var_100], rax
0x180021b03  jmp     short loc_180021A89
0x180021b05  jmp     short loc_180021A8B
0x180021b07  lea     rcx, [rbx+18h]
0x180021b0b  lea     rdx, [rsp+148h+var_100]
0x180021b10  call    ?Add@?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@QEAA_KAEAV?$CAutoPtr@VCAccessAce@CDacl@ATL@@@2@@Z; ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::Add(ATL::CAutoPtr<ATL::CDacl::CAccessAce> &)
0x180021b15  mov     rsi, [rsp+148h+var_100]
0x180021b1a  inc     edi
0x180021b1c  jmp     loc_180021991
0x180021b21  test    rsi, rsi
0x180021b24  jz      short loc_180021B3A
0x180021b26  mov     rax, [rsi]
0x180021b29  mov     edx, 1
0x180021b2e  mov     rcx, rsi
0x180021b31  mov     rax, [rax]
0x180021b34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b39  nop
0x180021b3a  mov     [rsp+148h+var_B8], r15
0x180021b42  mov     rcx, [rsp+148h+var_48]
0x180021b4a  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180021b4e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180021b53  mov     rcx, [rsp+148h+var_50]
0x180021b5b  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180021b5f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180021b64  mov     rcx, [rsp+148h+var_58]
0x180021b6c  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180021b70  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180021b75  mov     rcx, [rsp+148h+var_60]
0x180021b7d  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180021b81  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180021b86  jmp     loc_18002188A
0x180021b8b  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
```
