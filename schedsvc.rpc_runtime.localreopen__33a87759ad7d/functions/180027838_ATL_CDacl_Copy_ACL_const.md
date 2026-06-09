# ATL::CDacl::Copy(_ACL const &)

- ea: `0x180027838`
- end: `0x180027b6c`
- name: `?Copy@CDacl@ATL@@AEAAXAEBU_ACL@@@Z`
- size: `820`
- prototype: `void(ATL::CDacl *__hidden this, const struct _ACL *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800269f0`

## callees

- `0x180027838`
- `0x180027bc8`
- `0x180027bf0`
- `0x180028bc4`
- `0x180030f80`
- `0x180050490`
- `0x1800504b4`
- `0x180050b30`
- `0x18006ac80`
- `0x18006b0e4`
- `0x18007e6d0`
- `0x180084010`

## import_xrefs

- `msvcrt!free` at `0x180027923`
- `msvcrt!free` at `0x180027923`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18002793d`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18002795b`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18002793d`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18002795b`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18002798c`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18002798c`

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
0x180027838  mov     [rsp+arg_10], rbx
0x18002783d  push    rsi
0x18002783e  push    rdi
0x18002783f  push    r12
0x180027841  push    r14
0x180027843  push    r15
0x180027845  sub     rsp, 120h
0x18002784c  mov     rax, cs:__security_cookie
0x180027853  xor     rax, rsp
0x180027856  mov     [rsp+148h+var_38], rax
0x18002785e  mov     rdi, rdx
0x180027861  mov     rbx, rcx
0x180027864  mov     [rsp+148h+var_E8], rcx
0x180027869  test    rdx, rdx
0x18002786c  jnz     short loc_1800278A6
0x18002786e  mov     rax, [rcx]
0x180027871  mov     rax, [rax+10h]
0x180027875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002787a  mov     byte ptr [rbx+10h], 1
0x18002787e  mov     rcx, [rsp+148h+var_38]
0x180027886  xor     rcx, rsp; StackCookie
0x180027889  call    __security_check_cookie
0x18002788e  mov     rbx, [rsp+148h+arg_10]
0x180027896  add     rsp, 120h
0x18002789d  pop     r15
0x18002789f  pop     r14
0x1800278a1  pop     r12
0x1800278a3  pop     rdi
0x1800278a4  pop     rsi
0x1800278a5  retn
0x1800278a6  mov     [rsp+148h+pAcl], rdi
0x1800278ab  xor     eax, eax
0x1800278ad  mov     [rsp+148h+pAclInformation], rax
0x1800278b2  mov     [rsp+148h+var_C8], eax
0x1800278b9  mov     [rsp+148h+var_F8], eax
0x1800278bd  mov     [rsp+148h+pAce], rax
0x1800278c2  lea     r15, ??_7CSid@ATL@@6B@; const ATL::CSid::`vftable'
0x1800278c9  mov     [rsp+148h+var_B8], r15
0x1800278d1  mov     [rsp+148h+var_6C], al
0x1800278d8  mov     [rsp+148h+var_68], 7
0x1800278e3  lea     rcx, [rsp+148h+var_60]
0x1800278eb  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800278f0  lea     rcx, [rsp+148h+var_58]
0x1800278f8  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800278fd  lea     rcx, [rsp+148h+var_50]
0x180027905  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18002790a  lea     rcx, [rsp+148h+var_48]
0x180027912  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180027917  nop
0x180027918  xor     esi, esi
0x18002791a  mov     [rsp+148h+var_100], rsi
0x18002791f  mov     rcx, [rbx+8]; Block
0x180027923  call    cs:__imp_free
0x180027929  mov     [rbx+8], rsi
0x18002792d  lea     r9d, [rsi+2]; dwAclInformationClass
0x180027931  lea     r8d, [rsi+0Ch]; nAclInformationLength
0x180027935  lea     rdx, [rsp+148h+pAclInformation]; pAclInformation
0x18002793a  mov     rcx, rdi; pAcl
0x18002793d  call    cs:__imp_GetAclInformation
0x180027943  test    eax, eax
0x180027945  jz      loc_180027B66
0x18002794b  lea     r9d, [rsi+1]; dwAclInformationClass
0x18002794f  lea     r8d, [rsi+4]; nAclInformationLength
0x180027953  lea     rdx, [rsp+148h+var_F8]; pAclInformation
0x180027958  mov     rcx, rdi; pAcl
0x18002795b  call    cs:__imp_GetAclInformation
0x180027961  test    eax, eax
0x180027963  jz      loc_180027B66
0x180027969  mov     eax, [rsp+148h+var_F8]
0x18002796d  mov     [rbx+14h], eax
0x180027970  xor     edi, edi
0x180027972  mov     [rsp+148h+var_108], edi
0x180027976  cmp     edi, dword ptr [rsp+148h+pAclInformation]
0x18002797a  jnb     loc_180027AFC
0x180027980  lea     r8, [rsp+148h+pAce]; pAce
0x180027985  mov     edx, edi; dwAceIndex
0x180027987  mov     rcx, [rsp+148h+pAcl]; pAcl
0x18002798c  call    cs:__imp_GetAce
0x180027992  test    eax, eax
0x180027994  jz      loc_180027B66
0x18002799a  mov     rdx, [rsp+148h+pAce]
0x18002799f  mov     r12d, [rdx+4]
0x1800279a3  movzx   ecx, byte ptr [rdx]
0x1800279a6  test    ecx, ecx
0x1800279a8  jz      loc_180027A8B
0x1800279ae  sub     ecx, 1
0x1800279b1  jz      loc_180027A8B
0x1800279b7  sub     ecx, 4
0x1800279ba  jz      short loc_1800279C5
0x1800279bc  cmp     ecx, 1
0x1800279bf  jnz     loc_180027AF5
0x1800279c5  lea     rcx, [rdx+2Ch]
0x1800279c9  mov     r8d, [rdx+8]
0x1800279cd  and     r8d, 1
0x1800279d1  jz      short loc_1800279D9
0x1800279d3  lea     r14, [rdx+0Ch]
0x1800279d7  jmp     short loc_1800279DC
0x1800279d9  xor     r14d, r14d
0x1800279dc  lea     rax, [rcx-10h]
0x1800279e0  test    r8d, r8d
0x1800279e3  cmovz   rcx, rax
0x1800279e7  test    byte ptr [rdx+8], 2
0x1800279eb  jz      short loc_180027A02
0x1800279ed  mov     rax, r14
0x1800279f0  neg     rax
0x1800279f3  sbb     rsi, rsi
0x1800279f6  and     esi, 10h
0x1800279f9  add     rsi, 0Ch
0x1800279fd  add     rsi, rdx
0x180027a00  jmp     short loc_180027A08
0x180027a02  xor     esi, esi
0x180027a04  add     rcx, 0FFFFFFFFFFFFFFF0h
0x180027a08  mov     rdx, rcx
0x180027a0b  lea     rcx, [rsp+148h+var_B8]
0x180027a13  call    ??4CSid@ATL@@QEAAAEAV01@AEBU_SID@@@Z; ATL::CSid::operator=(_SID const &)
0x180027a18  nop
0x180027a19  mov     ecx, 0A8h; dwBytes
0x180027a1e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180027a23  mov     [rsp+148h+var_D8], rax
0x180027a28  test    rax, rax
0x180027a2b  jz      short loc_180027A5F
0x180027a2d  mov     r9, [rsp+148h+pAce]
0x180027a32  cmp     byte ptr [r9], 5
0x180027a36  setz    cl
0x180027a39  mov     [rsp+148h+var_118], rsi; struct _GUID *
0x180027a3e  mov     [rsp+148h+var_120], r14; struct _GUID *
0x180027a43  mov     [rsp+148h+var_128], cl; bool
0x180027a47  mov     r9b, [r9+1]; unsigned __int8
0x180027a4b  mov     r8d, r12d; unsigned int
0x180027a4e  lea     rdx, [rsp+148h+var_B8]; struct ATL::CSid *
0x180027a56  mov     rcx, rax; this
0x180027a59  call    ??0CAccessObjectAce@CDacl@ATL@@QEAA@AEBVCSid@2@KE_NPEBU_GUID@@2@Z; ATL::CDacl::CAccessObjectAce::CAccessObjectAce(ATL::CSid const &,ulong,uchar,bool,_GUID const *,_GUID const *)
0x180027a5e  nop
0x180027a5f  mov     [rsp+148h+var_100], rax
0x180027a64  jmp     short loc_180027A7B
0x180027a66  mov     rbx, [rsp+148h+var_E8]
0x180027a6b  mov     edi, [rsp+148h+var_108]
0x180027a6f  mov     rax, [rsp+148h+var_100]
0x180027a74  lea     r15, ??_7CSid@ATL@@6B@; const ATL::CSid::`vftable'
0x180027a7b  test    rax, rax
0x180027a7e  jnz     short loc_180027AE2
0x180027a80  mov     ecx, 8007000Eh; unsigned int
0x180027a85  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x180027a8b  add     rdx, 8
0x180027a8f  lea     rcx, [rsp+148h+var_B8]
0x180027a97  call    ??4CSid@ATL@@QEAAAEAV01@AEBU_SID@@@Z; ATL::CSid::operator=(_SID const &)
0x180027a9c  nop
0x180027a9d  mov     ecx, 98h; dwBytes
0x180027aa2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180027aa7  mov     [rsp+148h+var_D8], rax
0x180027aac  test    rax, rax
0x180027aaf  jz      short loc_180027AD9
0x180027ab1  mov     r9, [rsp+148h+pAce]
0x180027ab6  cmp     byte ptr [r9], 0
0x180027aba  setz    cl
0x180027abd  mov     [rsp+148h+var_128], cl; bool
0x180027ac1  mov     r9b, [r9+1]; unsigned __int8
0x180027ac5  mov     r8d, r12d; unsigned int
0x180027ac8  lea     rdx, [rsp+148h+var_B8]; struct ATL::CSid *
0x180027ad0  mov     rcx, rax; this
0x180027ad3  call    ??0CAccessAce@CDacl@ATL@@QEAA@AEBVCSid@2@KE_N@Z; ATL::CDacl::CAccessAce::CAccessAce(ATL::CSid const &,ulong,uchar,bool)
0x180027ad8  nop
0x180027ad9  mov     [rsp+148h+var_100], rax
0x180027ade  jmp     short loc_180027A64
0x180027ae0  jmp     short loc_180027A66
0x180027ae2  lea     rcx, [rbx+18h]
0x180027ae6  lea     rdx, [rsp+148h+var_100]
0x180027aeb  call    ?Add@?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@QEAA_KAEAV?$CAutoPtr@VCAccessAce@CDacl@ATL@@@2@@Z; ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::Add(ATL::CAutoPtr<ATL::CDacl::CAccessAce> &)
0x180027af0  mov     rsi, [rsp+148h+var_100]
0x180027af5  inc     edi
0x180027af7  jmp     loc_180027972
0x180027afc  test    rsi, rsi
0x180027aff  jz      short loc_180027B15
0x180027b01  mov     rax, [rsi]
0x180027b04  mov     edx, 1
0x180027b09  mov     rcx, rsi
0x180027b0c  mov     rax, [rax]
0x180027b0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b14  nop
0x180027b15  mov     [rsp+148h+var_B8], r15
0x180027b1d  mov     rcx, [rsp+148h+var_48]
0x180027b25  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180027b29  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180027b2e  mov     rcx, [rsp+148h+var_50]
0x180027b36  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180027b3a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180027b3f  mov     rcx, [rsp+148h+var_58]
0x180027b47  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180027b4b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180027b50  mov     rcx, [rsp+148h+var_60]
0x180027b58  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180027b5c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180027b61  jmp     loc_18002787E
0x180027b66  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
```
