# CASFStreamSelector::CreateMutexGroups(void)

- ea: `0x180034874`
- end: `0x180034c47`
- name: `?CreateMutexGroups@CASFStreamSelector@@IEAAJXZ`
- size: `979`
- prototype: `__int64 __fastcall(CASFStreamSelector *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180039510`

## callees

- `0x180001174`
- `0x1800015d0`
- `0x180031360`
- `0x180033438`
- `0x1800339d4`
- `0x180033a40`
- `0x180033d00`
- `0x180033d38`
- `0x180033da0`
- `0x180034874`
- `0x180037f08`
- `0x180038604`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFStreamSelector::CreateMutexGroups(CASFStreamSelector *this)
{
  CASFStreamSelector *v1; // r13
  __int64 v2; // rcx
  int StreamInfo; // ebx
  int v4; // eax
  __int64 v5; // rcx
  _QWORD *v6; // rax
  _QWORD *v7; // rdi
  unsigned __int16 i; // r12
  CASFStreamSelector::STREAM_GROUP *v9; // rax
  CASFStreamSelector::STREAM_GROUP *v10; // rsi
  unsigned __int16 v11; // r14
  char *v12; // r15
  __int64 v13; // rcx
  struct CASFStreamSelector::STREAM_INFO *v14; // rax
  unsigned __int16 j; // r14
  unsigned int v17; // [rsp+30h] [rbp-49h] BYREF
  CASFStreamSelector *v18; // [rsp+38h] [rbp-41h]
  __int64 v19; // [rsp+40h] [rbp-39h] BYREF
  __int64 v20; // [rsp+48h] [rbp-31h] BYREF
  __int64 v21; // [rsp+50h] [rbp-29h] BYREF
  __int64 v22; // [rsp+58h] [rbp-21h] BYREF
  _WORD v23[2]; // [rsp+60h] [rbp-19h] BYREF
  unsigned __int16 v24; // [rsp+64h] [rbp-15h] BYREF
  _WORD v25[2]; // [rsp+68h] [rbp-11h] BYREF
  int v26; // [rsp+6Ch] [rbp-Dh] BYREF
  GUID v27; // [rsp+70h] [rbp-9h] BYREF

  v18 = this;
  v1 = this;
  v22 = 0;
  v2 = *((_QWORD *)this + 3);
  v21 = 0;
  v19 = 0;
  v20 = 0;
  StreamInfo = ASFGetRootObject(v2, &CLSID_ASFHeaderObject, &IID_IASFUnknownContainer, &v22);
  if ( StreamInfo >= 0 )
  {
    v26 = 0;
    StreamInfo = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v22 + 72LL))(
                   v22,
                   &CLSID_ASFMutualExclusionObject,
                   &v21);
    if ( StreamInfo >= 0 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 40LL))(v21);
      while ( !(*(unsigned int (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v21 + 24LL))(
                 v21,
                 1,
                 &v19,
                 &v26) )
      {
        if ( v20 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
          v20 = 0;
        }
        v4 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v19)(v19, &IID_IASFMutualExclusionObject, &v20);
        v5 = v19;
        StreamInfo = v4;
        if ( v19 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
          v5 = 0;
          v19 = 0;
        }
        if ( StreamInfo < 0 )
          goto LABEL_35;
        v27 = GUID_NULL;
        StreamInfo = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v20 + 80LL))(v20, &v27);
        if ( StreamInfo < 0 )
          break;
        v24 = 0;
        v23[0] = 0;
        (*(void (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v20 + 136LL))(v20, &v24);
        if ( v24 )
        {
          v6 = operator new(0xF0u);
          v7 = v6;
          if ( !v6 )
          {
LABEL_33:
            StreamInfo = -2147024882;
            break;
          }
          v6[1] = 0;
          *((_WORD *)v6 + 12) = 0;
          *((_BYTE *)v6 + 26) = 0;
          *v6 = &CTSparseBlock<unsigned long,CASFStreamPropertiesObjectBase::STREAM_NAME_REC *,20,0>::`vftable';
          v6[24] = 0;
          v6[25] = v6;
          *((_DWORD *)v6 + 52) = 0;
          *((_DWORD *)v6 + 54) = 0;
          *((_DWORD *)v6 + 56) = 0;
          v6[29] = 0;
          v6[29] = v20;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
          CTDynArray<CASFStreamSelector::MULTI_GROUP *,20>::Add((char *)v1 + 288, v7, &v17);
          for ( i = 0; i < v24; ++i )
          {
            (*(void (__fastcall **)(__int64, _QWORD, _WORD *))(*(_QWORD *)v20 + 144LL))(v20, i, v23);
            if ( v23[0] )
            {
              v9 = (CASFStreamSelector::STREAM_GROUP *)operator new(0xF0u);
              if ( !v9 )
                goto LABEL_33;
              v10 = (CASFStreamSelector::STREAM_GROUP *)CASFStreamSelector::STREAM_GROUP::STREAM_GROUP(v9);
              if ( !v10 )
                goto LABEL_33;
              v11 = 0;
              if ( v23[0] )
              {
                v12 = (char *)v1 + 64;
                do
                {
                  v25[0] = 0;
                  v17 = 0;
                  (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _WORD *))(*(_QWORD *)v20 + 152LL))(v20, i, v11, v25);
                  StreamInfo = CASFStreamSelector::GetStreamInfo(v13, v12, v25[0], &v17);
                  if ( StreamInfo >= 0 )
                  {
                    v14 = (struct CASFStreamSelector::STREAM_INFO *)CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::operator[](
                                                                      v12,
                                                                      v17);
                    CASFStreamSelector::STREAM_GROUP::Add(v10, v14);
                  }
                  ++v11;
                }
                while ( v11 < v23[0] );
                v1 = v18;
              }
              for ( j = 0; (unsigned int)j < *((_DWORD *)v7 + 54); ++j )
              {
                if ( *((_DWORD *)v10 + 57) < *(_DWORD *)(CTDynArray<CASFStreamSelector::STREAM_GROUP *,20>::operator[](
                                                           v7,
                                                           j)
                                                       + 228) )
                {
                  CTDynArray<CASFStreamSelector::STREAM_GROUP *,20>::InsertAt(v7, j, v10);
                  goto LABEL_30;
                }
              }
              CTDynArray<CASFStreamSelector::STREAM_GROUP *,20>::Add(v7, v10);
            }
LABEL_30:
            ;
          }
          if ( StreamInfo < 0 )
            break;
        }
      }
    }
  }
  v5 = v19;
LABEL_35:
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v5 = v19;
    v21 = 0;
  }
  if ( v22 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v5 = v19;
    v22 = 0;
  }
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    v19 = 0;
  }
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  return (unsigned int)StreamInfo;
}

```

## disassembly

```asm
0x180034874  push    rbp
0x180034876  push    rbx
0x180034877  push    rsi
0x180034878  push    rdi
0x180034879  push    r12
0x18003487b  push    r13
0x18003487d  push    r14
0x18003487f  push    r15
0x180034881  lea     rbp, [rsp-1Fh]
0x180034886  sub     rsp, 98h
0x18003488d  mov     rax, cs:__security_cookie
0x180034894  xor     rax, rsp
0x180034897  mov     [rbp+57h+var_50], rax
0x18003489b  xor     r15d, r15d
0x18003489e  mov     [rbp+57h+var_98], rcx
0x1800348a2  mov     r13, rcx
0x1800348a5  mov     [rbp+57h+var_78], r15
0x1800348a9  mov     rcx, [rcx+18h]
0x1800348ad  lea     r9, [rbp+57h+var_78]
0x1800348b1  lea     r8, IID_IASFUnknownContainer
0x1800348b8  mov     [rbp+57h+var_80], r15
0x1800348bc  lea     rdx, CLSID_ASFHeaderObject
0x1800348c3  mov     [rbp+57h+var_90], r15
0x1800348c7  mov     [rbp+57h+var_88], r15
0x1800348cb  call    ASFGetRootObject
0x1800348d0  mov     ebx, eax
0x1800348d2  test    eax, eax
0x1800348d4  js      loc_180034BB7
0x1800348da  mov     rcx, [rbp+57h+var_78]
0x1800348de  lea     r8, [rbp+57h+var_80]
0x1800348e2  mov     [rbp+57h+var_64], r15d
0x1800348e6  lea     rdx, CLSID_ASFMutualExclusionObject
0x1800348ed  mov     rax, [rcx]
0x1800348f0  mov     rax, [rax+48h]
0x1800348f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800348f9  mov     ebx, eax
0x1800348fb  test    eax, eax
0x1800348fd  js      loc_180034BB7
0x180034903  mov     rcx, [rbp+57h+var_80]
0x180034907  mov     rax, [rcx]
0x18003490a  mov     rax, [rax+28h]
0x18003490e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034913  lea     edx, [r15+1]
0x180034917  mov     rcx, [rbp+57h+var_80]
0x18003491b  lea     r9, [rbp+57h+var_64]
0x18003491f  lea     r8, [rbp+57h+var_90]
0x180034923  mov     rax, [rcx]
0x180034926  mov     rax, [rax+18h]
0x18003492a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003492f  test    eax, eax
0x180034931  jnz     loc_180034BB7
0x180034937  mov     rcx, [rbp+57h+var_88]
0x18003493b  test    rcx, rcx
0x18003493e  jz      short loc_180034950
0x180034940  mov     rax, [rcx]
0x180034943  mov     rax, [rax+10h]
0x180034947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003494c  mov     [rbp+57h+var_88], r15
0x180034950  mov     rcx, [rbp+57h+var_90]
0x180034954  lea     r8, [rbp+57h+var_88]
0x180034958  lea     rdx, IID_IASFMutualExclusionObject
0x18003495f  mov     rax, [rcx]
0x180034962  mov     rax, [rax]
0x180034965  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003496a  mov     rcx, [rbp+57h+var_90]
0x18003496e  mov     ebx, eax
0x180034970  test    rcx, rcx
0x180034973  jz      short loc_180034988
0x180034975  mov     rax, [rcx]
0x180034978  mov     rax, [rax+10h]
0x18003497c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034981  mov     rcx, r15
0x180034984  mov     [rbp+57h+var_90], rcx
0x180034988  test    ebx, ebx
0x18003498a  js      loc_180034BBB
0x180034990  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180034997  mov     rcx, [rbp+57h+var_88]
0x18003499b  lea     rdx, [rbp+57h+var_60]
0x18003499f  movdqu  [rbp+57h+var_60], xmm0
0x1800349a4  mov     rax, [rcx]
0x1800349a7  mov     rax, [rax+50h]
0x1800349ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800349b0  mov     ebx, eax
0x1800349b2  test    eax, eax
0x1800349b4  js      loc_180034BB7
0x1800349ba  mov     rcx, [rbp+57h+var_88]
0x1800349be  lea     rdx, [rbp+57h+var_6C]
0x1800349c2  mov     [rbp+57h+var_6C], r15w
0x1800349c7  mov     [rbp+57h+var_70], r15w
0x1800349cc  mov     rax, [rcx]
0x1800349cf  mov     rax, [rax+88h]
0x1800349d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800349db  mov     edx, 1
0x1800349e0  cmp     [rbp+57h+var_6C], r15w
0x1800349e5  jz      loc_180034917
0x1800349eb  mov     ecx, 0F0h; Size
0x1800349f0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800349f5  mov     rdi, rax
0x1800349f8  test    rax, rax
0x1800349fb  jz      loc_180034BB2
0x180034a01  mov     qword ptr [rax+8], 0
0x180034a09  xor     eax, eax
0x180034a0b  mov     [rdi+18h], ax
0x180034a0f  mov     [rdi+1Ah], al
0x180034a12  lea     rax, ??_7?$CTSparseBlock@KPEAUSTREAM_NAME_REC@CASFStreamPropertiesObjectBase@@$0BE@$0A@@@6B@; const CTSparseBlock<ulong,CASFStreamPropertiesObjectBase::STREAM_NAME_REC *,20,0>::`vftable'
0x180034a19  mov     [rdi], rax
0x180034a1c  mov     [rdi+0C0h], r15
0x180034a23  mov     [rdi+0C8h], rdi
0x180034a2a  mov     [rdi+0D0h], r15d
0x180034a31  mov     [rdi+0D8h], r15d
0x180034a38  mov     [rdi+0E0h], r15d
0x180034a3f  mov     [rdi+0E8h], r15
0x180034a46  mov     rax, [rbp+57h+var_88]
0x180034a4a  mov     [rdi+0E8h], rax
0x180034a51  mov     rcx, [rbp+57h+var_88]
0x180034a55  mov     rax, [rcx]
0x180034a58  mov     rax, [rax+8]
0x180034a5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034a61  lea     rcx, [r13+120h]
0x180034a68  mov     rdx, rdi
0x180034a6b  lea     r8, [rbp+57h+var_A0]
0x180034a6f  call    ?Add@?$CTDynArray@PEAUMULTI_GROUP@CASFStreamSelector@@$0BE@@@QEAAHPEAUMULTI_GROUP@CASFStreamSelector@@PEAK@Z; CTDynArray<CASFStreamSelector::MULTI_GROUP *,20>::Add(CASFStreamSelector::MULTI_GROUP *,ulong *)
0x180034a74  mov     edx, 1
0x180034a79  mov     r12d, r15d
0x180034a7c  mov     eax, ebx
0x180034a7e  cmp     r12w, [rbp+57h+var_6C]
0x180034a83  jnb     loc_180034BA9
0x180034a89  mov     rcx, [rbp+57h+var_88]
0x180034a8d  lea     r8, [rbp+57h+var_70]
0x180034a91  movzx   edx, r12w
0x180034a95  mov     rax, [rcx]
0x180034a98  mov     rax, [rax+90h]
0x180034a9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034aa4  cmp     [rbp+57h+var_70], r15w
0x180034aa9  jz      loc_180034B9B
0x180034aaf  mov     ecx, 0F0h; Size
0x180034ab4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180034ab9  test    rax, rax
0x180034abc  jz      loc_180034BB2
0x180034ac2  mov     rcx, rax; this
0x180034ac5  call    ??0STREAM_GROUP@CASFStreamSelector@@QEAA@XZ; CASFStreamSelector::STREAM_GROUP::STREAM_GROUP(void)
0x180034aca  mov     rsi, rax
0x180034acd  test    rax, rax
0x180034ad0  jz      loc_180034BB2
0x180034ad6  mov     r14d, r15d
0x180034ad9  cmp     r15w, [rbp+57h+var_70]
0x180034ade  jnb     short loc_180034B51
0x180034ae0  lea     r15, [r13+40h]
0x180034ae4  mov     r13d, 1
0x180034aea  mov     rcx, [rbp+57h+var_88]
0x180034aee  lea     r9, [rbp+57h+var_68]
0x180034af2  xor     eax, eax
0x180034af4  movzx   r8d, r14w
0x180034af8  mov     [rbp+57h+var_68], ax
0x180034afc  movzx   edx, r12w
0x180034b00  mov     [rbp+57h+var_A0], eax
0x180034b03  mov     rax, [rcx]
0x180034b06  mov     rax, [rax+98h]
0x180034b0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b12  movzx   r8d, [rbp+57h+var_68]
0x180034b17  lea     r9, [rbp+57h+var_A0]
0x180034b1b  mov     rdx, r15
0x180034b1e  call    ?GetStreamInfo@CASFStreamSelector@@IEAAJPEAV?$CTDynArray@PEAUSTREAM_INFO@CASFStreamSelector@@$0BE@@@GPEAK@Z; CASFStreamSelector::GetStreamInfo(CTDynArray<CASFStreamSelector::STREAM_INFO *,20> *,ushort,ulong *)
0x180034b23  mov     ebx, eax
0x180034b25  test    eax, eax
0x180034b27  js      short loc_180034B3F
0x180034b29  mov     edx, [rbp+57h+var_A0]
0x180034b2c  mov     rcx, r15
0x180034b2f  call    ??A?$CTDynArray@PEAUSTREAM_INFO@CASFStreamSelector@@$0BE@@@QEBAPEAUSTREAM_INFO@CASFStreamSelector@@K@Z; CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::operator[](ulong)
0x180034b34  mov     rdx, rax; struct CASFStreamSelector::STREAM_INFO *
0x180034b37  mov     rcx, rsi; this
0x180034b3a  call    ?Add@STREAM_GROUP@CASFStreamSelector@@QEAAXPEAUSTREAM_INFO@2@@Z; CASFStreamSelector::STREAM_GROUP::Add(CASFStreamSelector::STREAM_INFO *)
0x180034b3f  add     r14w, r13w
0x180034b43  cmp     r14w, [rbp+57h+var_70]
0x180034b48  jb      short loc_180034AEA
0x180034b4a  mov     r13, [rbp+57h+var_98]
0x180034b4e  xor     r15d, r15d
0x180034b51  mov     r14d, r15d
0x180034b54  movzx   r15d, r14w
0x180034b58  mov     rcx, rdi
0x180034b5b  cmp     r15d, [rdi+0D8h]
0x180034b62  jnb     short loc_180034B90
0x180034b64  mov     edx, r15d
0x180034b67  call    ??A?$CTDynArray@PEAUSTREAM_GROUP@CASFStreamSelector@@$0BE@@@QEBAPEAUSTREAM_GROUP@CASFStreamSelector@@K@Z; CTDynArray<CASFStreamSelector::STREAM_GROUP *,20>::operator[](ulong)
0x180034b6c  mov     eax, [rax+0E4h]
0x180034b72  cmp     [rsi+0E4h], eax
0x180034b78  jb      short loc_180034B80
0x180034b7a  inc     r14w
0x180034b7e  jmp     short loc_180034B54
0x180034b80  mov     r8, rsi
0x180034b83  mov     edx, r15d
0x180034b86  mov     rcx, rdi
0x180034b89  call    ?InsertAt@?$CTDynArray@PEAUSTREAM_GROUP@CASFStreamSelector@@$0BE@@@QEAAHKPEAUSTREAM_GROUP@CASFStreamSelector@@@Z; CTDynArray<CASFStreamSelector::STREAM_GROUP *,20>::InsertAt(ulong,CASFStreamSelector::STREAM_GROUP *)
0x180034b8e  jmp     short loc_180034B98
0x180034b90  mov     rdx, rsi
0x180034b93  call    ?Add@?$CTDynArray@PEAUSTREAM_GROUP@CASFStreamSelector@@$0BE@@@QEAAHPEAUSTREAM_GROUP@CASFStreamSelector@@PEAK@Z; CTDynArray<CASFStreamSelector::STREAM_GROUP *,20>::Add(CASFStreamSelector::STREAM_GROUP *,ulong *)
0x180034b98  xor     r15d, r15d
0x180034b9b  mov     edx, 1
0x180034ba0  add     r12w, dx
0x180034ba4  jmp     loc_180034A7C
0x180034ba9  test    eax, eax
0x180034bab  js      short loc_180034BB7
0x180034bad  jmp     loc_180034917
0x180034bb2  mov     ebx, 8007000Eh
0x180034bb7  mov     rcx, [rbp+57h+var_90]
0x180034bbb  mov     rdx, [rbp+57h+var_80]
0x180034bbf  test    rdx, rdx
0x180034bc2  jz      short loc_180034BDB
0x180034bc4  mov     rax, [rdx]
0x180034bc7  mov     rcx, rdx
0x180034bca  mov     rax, [rax+10h]
0x180034bce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034bd3  mov     rcx, [rbp+57h+var_90]
0x180034bd7  mov     [rbp+57h+var_80], r15
0x180034bdb  mov     rdx, [rbp+57h+var_78]
0x180034bdf  test    rdx, rdx
0x180034be2  jz      short loc_180034BFB
0x180034be4  mov     rax, [rdx]
0x180034be7  mov     rcx, rdx
0x180034bea  mov     rax, [rax+10h]
0x180034bee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034bf3  mov     rcx, [rbp+57h+var_90]
0x180034bf7  mov     [rbp+57h+var_78], r15
0x180034bfb  test    rcx, rcx
0x180034bfe  jz      short loc_180034C10
0x180034c00  mov     rax, [rcx]
0x180034c03  mov     rax, [rax+10h]
0x180034c07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034c0c  mov     [rbp+57h+var_90], r15
0x180034c10  mov     rcx, [rbp+57h+var_88]
0x180034c14  test    rcx, rcx
0x180034c17  jz      short loc_180034C25
0x180034c19  mov     rax, [rcx]
0x180034c1c  mov     rax, [rax+10h]
0x180034c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034c25  mov     eax, ebx
0x180034c27  mov     rcx, [rbp+57h+var_50]
0x180034c2b  xor     rcx, rsp; StackCookie
0x180034c2e  call    __security_check_cookie
0x180034c33  add     rsp, 98h
0x180034c3a  pop     r15
0x180034c3c  pop     r14
0x180034c3e  pop     r13
0x180034c40  pop     r12
0x180034c42  pop     rdi
0x180034c43  pop     rsi
0x180034c44  pop     rbx
0x180034c45  pop     rbp
0x180034c46  retn
```
