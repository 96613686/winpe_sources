# ATL::CDacl::Copy(_ACL const &)

- ea: `0x140092448`
- end: `0x1400926d8`
- name: `?Copy@CDacl@ATL@@AEAAXAEBU_ACL@@@Z`
- size: `656`
- prototype: `void(ATL::CDacl *__hidden this, const struct _ACL *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation`

## callers

- `0x140091fd8`

## callees

- `0x140038f58`
- `0x1400396dc`
- `0x1400447f0`
- `0x140044884`
- `0x140045f20`
- `0x140046358`
- `0x14004aab0`
- `0x14004b5e8`
- `0x14004d864`
- `0x140091e80`
- `0x140092014`
- `0x140092448`
- `0x14009e010`

## import_xrefs

- `ADVAPI32!GetAclInformation` at `0x140092510`
- `ADVAPI32!GetAclInformation` at `0x140092530`
- `ADVAPI32!GetAclInformation` at `0x140092510`
- `ADVAPI32!GetAclInformation` at `0x140092530`
- `ADVAPI32!GetAce` at `0x140092561`
- `ADVAPI32!GetAce` at `0x140092561`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400924f0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400924f0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall ATL::CDacl::Copy(ATL::CDacl *this, struct _ACL *a2)
{
  ATL::CDacl *v3; // rbx
  DWORD i; // edi
  int v5; // r15d
  struct _SID *v6; // rcx
  const struct _GUID *v7; // r14
  const struct _GUID *v8; // rsi
  ATL::CDacl::CAccessAce *v9; // rax
  ATL::CDacl::CAccessAce *v10; // rax
  ATL::CDacl::CAccessAce *v11; // [rsp+48h] [rbp-F0h] BYREF
  int v12; // [rsp+50h] [rbp-E8h] BYREF
  LPVOID pAce; // [rsp+58h] [rbp-E0h] BYREF
  ATL::CDacl *v14; // [rsp+60h] [rbp-D8h]
  PACL pAcl; // [rsp+68h] [rbp-D0h]
  ATL::CDacl::CAccessObjectAce *v16; // [rsp+70h] [rbp-C8h]
  __int64 pAclInformation; // [rsp+78h] [rbp-C0h] BYREF
  int v18; // [rsp+80h] [rbp-B8h]
  _BYTE v19[128]; // [rsp+90h] [rbp-A8h] BYREF

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
  ATL::CSid::CSid((ATL::CSid *)v19);
  v11 = 0;
  free(*((void **)v3 + 1));
  *((_QWORD *)v3 + 1) = 0;
  if ( !GetAclInformation(a2, &pAclInformation, 0xCu, AclSizeInformation)
    || !GetAclInformation(a2, &v12, 4u, AclRevisionInformation) )
  {
LABEL_26:
    ATL::AtlThrowLastWin32();
  }
  *((_DWORD *)v3 + 5) = v12;
  for ( i = 0; i < (unsigned int)pAclInformation; ++i )
  {
    if ( !GetAce(pAcl, i, &pAce) )
      goto LABEL_26;
    v5 = *((_DWORD *)pAce + 1);
    if ( !*(_BYTE *)pAce || *(_BYTE *)pAce == 1 )
    {
      ATL::CSid::operator=((ATL::CSid *)v19, (struct _SID *)((char *)pAce + 8));
      try
      {
        v10 = (ATL::CDacl::CAccessAce *)operator new(0x98u);
        v9 = ATL::CDacl::CAccessAce::CAccessAce(
               v10,
               (const struct ATL::CSid *)v19,
               v5,
               *((_BYTE *)pAce + 1),
               *(_BYTE *)pAce == 0);
        v11 = v9;
      }
      catch ( ... )
      {
        v3 = v14;
        v9 = v11;
      }
    }
    else
    {
      if ( (unsigned int)*(unsigned __int8 *)pAce - 5 > 1 )
        continue;
      v6 = (struct _SID *)((char *)pAce + 44);
      if ( (*((_DWORD *)pAce + 2) & 1) != 0 )
        v7 = (const struct _GUID *)((char *)pAce + 12);
      else
        v7 = 0;
      if ( (*((_DWORD *)pAce + 2) & 1) == 0 )
        v6 = (struct _SID *)((char *)pAce + 28);
      if ( (*((_BYTE *)pAce + 8) & 2) != 0 )
      {
        v8 = (const struct _GUID *)((char *)pAce + (v7 != 0 ? 28LL : 12LL));
      }
      else
      {
        v8 = 0;
        v6 = (struct _SID *)((char *)v6 - 16);
      }
      ATL::CSid::operator=((ATL::CSid *)v19, v6);
      try
      {
        v16 = (ATL::CDacl::CAccessObjectAce *)operator new(0xA8u);
        v9 = ATL::CDacl::CAccessObjectAce::CAccessObjectAce(
               v16,
               (const struct ATL::CSid *)v19,
               v5,
               *((_BYTE *)pAce + 1),
               *(_BYTE *)pAce == 5,
               v7,
               v8);
        v11 = v9;
      }
      catch ( ... )
      {
        v3 = v14;
        v9 = v11;
      }
    }
    if ( !v9 )
      ATL::AtlThrowImpl(-2147024882);
    ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::Add(
      (__int64 *)v3 + 3,
      (__int64 *)&v11);
  }
  ATL::CAutoPtr<CdsSortEntry>::~CAutoPtr<CdsSortEntry>(&v11);
  ATL::CSid::~CSid((ATL::CSid *)v19);
}

```

## disassembly

```asm
0x140092448  mov     [rsp+arg_10], rbx
0x14009244d  mov     [rsp+arg_18], rsi
0x140092452  push    rdi
0x140092453  push    r14
0x140092455  push    r15
0x140092457  sub     rsp, 120h
0x14009245e  mov     rax, cs:__security_cookie
0x140092465  xor     rax, rsp
0x140092468  mov     [rsp+138h+var_28], rax
0x140092470  mov     rdi, rdx
0x140092473  mov     rbx, rcx
0x140092476  mov     [rsp+138h+var_D8], rcx
0x14009247b  test    rdx, rdx
0x14009247e  jnz     short loc_1400924B9
0x140092480  mov     rax, [rcx]
0x140092483  mov     rax, [rax+10h]
0x140092487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009248c  mov     byte ptr [rbx+10h], 1
0x140092490  mov     rcx, [rsp+138h+var_28]
0x140092498  xor     rcx, rsp; StackCookie
0x14009249b  call    __security_check_cookie
0x1400924a0  lea     r11, [rsp+138h+var_18]
0x1400924a8  mov     rbx, [r11+30h]
0x1400924ac  mov     rsi, [r11+38h]
0x1400924b0  mov     rsp, r11
0x1400924b3  pop     r15
0x1400924b5  pop     r14
0x1400924b7  pop     rdi
0x1400924b8  retn
0x1400924b9  mov     [rsp+138h+pAcl], rdi
0x1400924be  xor     eax, eax
0x1400924c0  mov     [rsp+138h+pAclInformation], rax
0x1400924c5  mov     [rsp+138h+var_B8], eax
0x1400924cc  mov     [rsp+138h+var_E8], eax
0x1400924d0  mov     [rsp+138h+pAce], rax
0x1400924d5  lea     rcx, [rsp+138h+var_A8]; this
0x1400924dd  call    ??0CSid@ATL@@QEAA@XZ; ATL::CSid::CSid(void)
0x1400924e2  nop
0x1400924e3  mov     [rsp+138h+var_F0], 0
0x1400924ec  mov     rcx, [rbx+8]; Block
0x1400924f0  call    cs:__imp_free
0x1400924f6  mov     qword ptr [rbx+8], 0
0x1400924fe  mov     r9d, 2; dwAclInformationClass
0x140092504  lea     r8d, [r9+0Ah]; nAclInformationLength
0x140092508  lea     rdx, [rsp+138h+pAclInformation]; pAclInformation
0x14009250d  mov     rcx, rdi; pAcl
0x140092510  call    cs:__imp_GetAclInformation
0x140092516  test    eax, eax
0x140092518  jz      loc_1400926D2
0x14009251e  mov     r9d, 1; dwAclInformationClass
0x140092524  lea     r8d, [r9+3]; nAclInformationLength
0x140092528  lea     rdx, [rsp+138h+var_E8]; pAclInformation
0x14009252d  mov     rcx, rdi; pAcl
0x140092530  call    cs:__imp_GetAclInformation
0x140092536  test    eax, eax
0x140092538  jz      loc_1400926D2
0x14009253e  mov     eax, [rsp+138h+var_E8]
0x140092542  mov     [rbx+14h], eax
0x140092545  xor     edi, edi
0x140092547  mov     [rsp+138h+var_F8], edi
0x14009254b  cmp     edi, dword ptr [rsp+138h+pAclInformation]
0x14009254f  jnb     loc_1400926B5
0x140092555  lea     r8, [rsp+138h+pAce]; pAce
0x14009255a  mov     edx, edi; dwAceIndex
0x14009255c  mov     rcx, [rsp+138h+pAcl]; pAcl
0x140092561  call    cs:__imp_GetAce
0x140092567  test    eax, eax
0x140092569  jz      loc_1400926D2
0x14009256f  mov     rdx, [rsp+138h+pAce]
0x140092574  mov     r15d, [rdx+4]
0x140092578  movzx   ecx, byte ptr [rdx]
0x14009257b  test    ecx, ecx
0x14009257d  jz      loc_14009265E
0x140092583  sub     ecx, 1
0x140092586  jz      loc_14009265E
0x14009258c  sub     ecx, 4
0x14009258f  jz      short loc_14009259A
0x140092591  cmp     ecx, 1
0x140092594  jnz     loc_140092657
0x14009259a  lea     rcx, [rdx+2Ch]
0x14009259e  mov     r8d, [rdx+8]
0x1400925a2  and     r8d, 1
0x1400925a6  jz      short loc_1400925AE
0x1400925a8  lea     r14, [rdx+0Ch]
0x1400925ac  jmp     short loc_1400925B1
0x1400925ae  xor     r14d, r14d
0x1400925b1  lea     rax, [rcx-10h]
0x1400925b5  test    r8d, r8d
0x1400925b8  cmovz   rcx, rax
0x1400925bc  test    byte ptr [rdx+8], 2
0x1400925c0  jz      short loc_1400925D7
0x1400925c2  mov     rax, r14
0x1400925c5  neg     rax
0x1400925c8  sbb     rsi, rsi
0x1400925cb  and     esi, 10h
0x1400925ce  add     rsi, 0Ch
0x1400925d2  add     rsi, rdx
0x1400925d5  jmp     short loc_1400925DD
0x1400925d7  xor     esi, esi
0x1400925d9  add     rcx, 0FFFFFFFFFFFFFFF0h
0x1400925dd  mov     rdx, rcx; struct _SID *
0x1400925e0  lea     rcx, [rsp+138h+var_A8]; this
0x1400925e8  call    ??4CSid@ATL@@QEAAAEAV01@AEBU_SID@@@Z; ATL::CSid::operator=(_SID const &)
0x1400925ed  nop
0x1400925ee  mov     ecx, 0A8h; Size
0x1400925f3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400925f8  mov     [rsp+138h+var_C8], rax
0x1400925fd  mov     r9, [rsp+138h+pAce]
0x140092602  cmp     byte ptr [r9], 5
0x140092606  setz    cl
0x140092609  mov     [rsp+138h+var_108], rsi; struct _GUID *
0x14009260e  mov     [rsp+138h+var_110], r14; struct _GUID *
0x140092613  mov     [rsp+138h+var_118], cl; bool
0x140092617  mov     r9b, [r9+1]; unsigned __int8
0x14009261b  mov     r8d, r15d; unsigned int
0x14009261e  lea     rdx, [rsp+138h+var_A8]; struct ATL::CSid *
0x140092626  mov     rcx, rax; this
0x140092629  call    ??0CAccessObjectAce@CDacl@ATL@@QEAA@AEBVCSid@2@KE_NPEBU_GUID@@2@Z; ATL::CDacl::CAccessObjectAce::CAccessObjectAce(ATL::CSid const &,ulong,uchar,bool,_GUID const *,_GUID const *)
0x14009262e  nop
0x14009262f  mov     [rsp+138h+var_F0], rax
0x140092634  jmp     short loc_140092644
0x140092636  mov     rbx, [rsp+138h+var_D8]
0x14009263b  mov     edi, [rsp+138h+var_F8]
0x14009263f  mov     rax, [rsp+138h+var_F0]
0x140092644  test    rax, rax
0x140092647  jz      short loc_1400926AA
0x140092649  lea     rcx, [rbx+18h]
0x14009264d  lea     rdx, [rsp+138h+var_F0]
0x140092652  call    ?Add@?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@QEAA_KAEAV?$CAutoPtr@VCAccessAce@CDacl@ATL@@@2@@Z; ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::Add(ATL::CAutoPtr<ATL::CDacl::CAccessAce> &)
0x140092657  inc     edi
0x140092659  jmp     loc_140092547
0x14009265e  add     rdx, 8; struct _SID *
0x140092662  lea     rcx, [rsp+138h+var_A8]; this
0x14009266a  call    ??4CSid@ATL@@QEAAAEAV01@AEBU_SID@@@Z; ATL::CSid::operator=(_SID const &)
0x14009266f  nop
0x140092670  mov     ecx, 98h; Size
0x140092675  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14009267a  mov     r9, [rsp+138h+pAce]
0x14009267f  cmp     byte ptr [r9], 0
0x140092683  setz    cl
0x140092686  mov     [rsp+138h+var_118], cl; bool
0x14009268a  mov     r9b, [r9+1]; unsigned __int8
0x14009268e  mov     r8d, r15d; unsigned int
0x140092691  lea     rdx, [rsp+138h+var_A8]; struct ATL::CSid *
0x140092699  mov     rcx, rax; this
0x14009269c  call    ??0CAccessAce@CDacl@ATL@@QEAA@AEBVCSid@2@KE_N@Z; ATL::CDacl::CAccessAce::CAccessAce(ATL::CSid const &,ulong,uchar,bool)
0x1400926a1  mov     [rsp+138h+var_F0], rax
0x1400926a6  jmp     short loc_140092634
0x1400926a8  jmp     short loc_140092636
0x1400926aa  mov     ecx, 8007000Eh; int
0x1400926af  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1400926b5  lea     rcx, [rsp+138h+var_F0]
0x1400926ba  call    ??1?$CAutoPtr@VCdsSortEntry@@@ATL@@QEAA@XZ; ATL::CAutoPtr<CdsSortEntry>::~CAutoPtr<CdsSortEntry>(void)
0x1400926bf  nop
0x1400926c0  lea     rcx, [rsp+138h+var_A8]; this
0x1400926c8  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x1400926cd  jmp     loc_140092490
0x1400926d2  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
```
