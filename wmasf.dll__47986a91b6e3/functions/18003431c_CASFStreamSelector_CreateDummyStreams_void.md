# CASFStreamSelector::CreateDummyStreams(void)

- ea: `0x18003431c`
- end: `0x180034754`
- name: `?CreateDummyStreams@CASFStreamSelector@@IEAAJXZ`
- size: `1080`
- prototype: `__int64 __fastcall(CASFStreamSelector *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180039510`

## callees

- `0x180001174`
- `0x1800015d0`
- `0x180033438`
- `0x180033484`
- `0x1800338fc`
- `0x1800339d4`
- `0x180033a40`
- `0x180033aac`
- `0x180033b04`
- `0x180033d00`
- `0x180033d38`
- `0x180033da0`
- `0x18003431c`
- `0x180038604`
- `0x180038654`
- `0x18003f294`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFStreamSelector::CreateDummyStreams(CASFStreamSelector *this, unsigned int a2)
{
  unsigned int v2; // r12d
  int v3; // ebx
  CASFStreamSelector::STREAM_GROUP *v4; // rsi
  CASFStreamSelector *v5; // r13
  char *v6; // rax
  __int64 v7; // r13
  _DWORD *v8; // r14
  unsigned int j; // r15d
  __int64 v10; // r13
  CASFStreamSelector::STREAM_GROUP *v11; // rax
  CASFStreamSelector::STREAM_INFO *v12; // rax
  __int64 v13; // rax
  struct CASFStreamSelector::STREAM_INFO *v14; // rdi
  CASFStreamSelector *v15; // r12
  unsigned int v16; // ebp
  __int64 v17; // r13
  unsigned int k; // edi
  __int64 v19; // r14
  unsigned int m; // ebp
  __int64 v21; // rax
  unsigned int n; // ebp
  __int64 v23; // r15
  CASFStreamSelector::STREAM_INFO *v24; // rax
  __int64 v25; // rax
  struct CASFStreamSelector::STREAM_INFO *v26; // r14
  CASFStreamSelector::MULTI_GROUP *v27; // rax
  CASFStreamSelector::MULTI_GROUP *v28; // rdi
  CASFStreamSelector::STREAM_GROUP *v29; // rax
  unsigned int v30; // edx
  CASFStreamSelector::STREAM_GROUP *v31; // rax
  CASFStreamSelector::STREAM_GROUP *v32; // rsi
  CASFStreamSelector::STREAM_GROUP *v33; // rax
  CASFStreamSelector::STREAM_GROUP *v34; // rax
  CASFStreamSelector::STREAM_GROUP *v35; // rsi
  int v37; // [rsp+20h] [rbp-88h] BYREF
  __int64 v38; // [rsp+28h] [rbp-80h]
  CASFStreamSelector *v39; // [rsp+30h] [rbp-78h]
  char *i; // [rsp+38h] [rbp-70h]
  __int128 Buf2; // [rsp+40h] [rbp-68h] BYREF

  v2 = 0;
  v39 = this;
  v3 = 0;
  v37 = 0;
  v4 = 0;
  v5 = this;
  if ( *((_DWORD *)this + 126) )
  {
    v6 = (char *)this + 288;
    for ( i = (char *)this + 288; ; v6 = i )
    {
      v7 = CTDynArray<CASFStreamSelector::MULTI_GROUP *,20>::operator[](v6, v2);
      v38 = v7;
      Buf2 = 0;
      v3 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)(v7 + 232) + 80LL))(
             *(_QWORD *)(v7 + 232),
             &Buf2);
      if ( v3 < 0 )
        break;
      if ( !memcmp_0(&CLSID_ASFMutexBitrate, &Buf2, 0x10u) )
      {
        v8 = (_DWORD *)CTDynArray<CASFStreamSelector::STREAM_GROUP *,20>::operator[](v7, 0);
        for ( j = 0; j < v8[54]; ++j )
        {
          v10 = CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::operator[](v8, j);
          if ( *(_DWORD *)(v10 + 12) )
          {
            if ( !v4 )
            {
              v11 = (CASFStreamSelector::STREAM_GROUP *)operator new(0xF0u);
              if ( !v11
                || (v4 = (CASFStreamSelector::STREAM_GROUP *)CASFStreamSelector::STREAM_GROUP::STREAM_GROUP(v11)) == 0 )
              {
                return (unsigned int)-2147024882;
              }
            }
            v12 = (CASFStreamSelector::STREAM_INFO *)operator new(0x110u);
            if ( !v12
              || (v13 = CASFStreamSelector::STREAM_INFO::STREAM_INFO(v12),
                  (v14 = (struct CASFStreamSelector::STREAM_INFO *)v13) == 0) )
            {
LABEL_43:
              v3 = -2147024882;
              goto LABEL_44;
            }
            v15 = v39;
            *(_WORD *)v13 = *(_WORD *)v10;
            *(_DWORD *)(v13 + 4) = *(_DWORD *)(v10 + 4) >> 1;
            v16 = 0;
            *(_WORD *)(v13 + 2) = *(_WORD *)(v10 + 2);
            *(_DWORD *)(v13 + 12) = 0;
            *(_DWORD *)(v13 + 16) = 1;
            *(_DWORD *)(v13 + 8) = *(_DWORD *)(v10 + 8);
            *(_QWORD *)(v13 + 20) = 1000;
            while ( v16 < *((_DWORD *)v15 + 70) )
            {
              if ( CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::operator[]((char *)v15 + 64, v16) == v10 )
              {
                CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::InsertAt((char *)v15 + 64, v16, v14);
                break;
              }
              ++v16;
            }
            CASFStreamSelector::STREAM_GROUP::Add(v4, v14);
          }
        }
        v17 = v38;
        if ( v4 )
        {
          *((_DWORD *)v4 + 56) = v8[56] >> 1;
          *((_DWORD *)v4 + 57) = v8[57] >> 1;
          *((_DWORD *)v4 + 58) = v8[58] >> 1;
          *((_DWORD *)v4 + 59) = v8[59];
          CTDynArray<CASFStreamSelector::STREAM_GROUP *,20>::InsertAt(v17, 0, v4);
          v4 = 0;
        }
        for ( k = 0; k < *(_DWORD *)(v17 + 216); ++k )
        {
          v19 = CTDynArray<CASFStreamSelector::STREAM_GROUP *,20>::operator[](v17, k);
          for ( m = 0; m < *(_DWORD *)(v19 + 216); *(_DWORD *)(v21 + 12) = 0 )
            v21 = CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::operator[](v19, m++);
        }
        v2 = v37;
      }
      v5 = v39;
      v37 = ++v2;
      if ( v2 >= *((_DWORD *)v39 + 126) )
        goto LABEL_30;
    }
  }
  else
  {
LABEL_30:
    for ( n = 0; n < *((_DWORD *)v5 + 70); ++n )
    {
      v23 = CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::operator[]((char *)v5 + 64, n);
      if ( *(_DWORD *)(v23 + 12) )
      {
        v24 = (CASFStreamSelector::STREAM_INFO *)operator new(0x110u);
        if ( !v24 )
          goto LABEL_43;
        v25 = CASFStreamSelector::STREAM_INFO::STREAM_INFO(v24);
        v26 = (struct CASFStreamSelector::STREAM_INFO *)v25;
        if ( !v25 )
          goto LABEL_43;
        *(_WORD *)v25 = *(_WORD *)v23;
        *(_DWORD *)(v25 + 4) = *(_DWORD *)(v23 + 4) >> 1;
        *(_WORD *)(v25 + 2) = *(_WORD *)(v23 + 2);
        *(_DWORD *)(v25 + 12) = 0;
        *(_DWORD *)(v25 + 16) = 1;
        *(_DWORD *)(v25 + 8) = *(_DWORD *)(v23 + 8);
        *(_QWORD *)(v25 + 20) = 1000;
        CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::InsertAt((char *)v5 + 64, n, v25);
        *(_DWORD *)(v23 + 12) = 0;
        v27 = (CASFStreamSelector::MULTI_GROUP *)operator new(0xF0u);
        v28 = v27;
        if ( !v27 )
          goto LABEL_43;
        *((_QWORD *)v27 + 1) = 0;
        *((_WORD *)v27 + 12) = 0;
        *((_BYTE *)v27 + 26) = 0;
        *(_QWORD *)v27 = &CTSparseBlock<unsigned long,CASFStreamPropertiesObjectBase::STREAM_NAME_REC *,20,0>::`vftable';
        *((_QWORD *)v27 + 24) = 0;
        *((_QWORD *)v27 + 25) = v27;
        *((_DWORD *)v27 + 52) = 0;
        *((_DWORD *)v27 + 54) = 0;
        *((_QWORD *)v27 + 29) = 0;
        *((_DWORD *)v27 + 56) = 1;
        v29 = (CASFStreamSelector::STREAM_GROUP *)operator new(0xF0u);
        if ( !v29
          || (v31 = (CASFStreamSelector::STREAM_GROUP *)CASFStreamSelector::STREAM_GROUP::STREAM_GROUP(v29),
              (v32 = v31) == 0)
          || (CASFStreamSelector::STREAM_GROUP::Add(v31, v26),
              CTDynArray<CASFStreamSelector::STREAM_GROUP *,20>::Add(v28, v32),
              (v33 = (CASFStreamSelector::STREAM_GROUP *)operator new(0xF0u)) == 0)
          || (v34 = (CASFStreamSelector::STREAM_GROUP *)CASFStreamSelector::STREAM_GROUP::STREAM_GROUP(v33),
              (v35 = v34) == 0) )
        {
          v3 = -2147024882;
          CASFStreamSelector::MULTI_GROUP::`scalar deleting destructor'(v28, v30);
          return (unsigned int)v3;
        }
        CASFStreamSelector::STREAM_GROUP::Add(v34, (struct CASFStreamSelector::STREAM_INFO *)v23);
        CTDynArray<CASFStreamSelector::STREAM_GROUP *,20>::Add(v28, v35);
        v4 = 0;
        CTDynArray<CASFStreamSelector::MULTI_GROUP *,20>::Add((char *)v5 + 288, v28, &v37);
      }
    }
  }
LABEL_44:
  if ( v4 )
    CASFStreamSelector::STREAM_GROUP::`scalar deleting destructor'(v4, a2);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18003431c  push    rbx
0x18003431e  push    rbp
0x18003431f  push    rsi
0x180034320  push    rdi
0x180034321  push    r12
0x180034323  push    r13
0x180034325  push    r14
0x180034327  push    r15
0x180034329  sub     rsp, 68h
0x18003432d  mov     rax, cs:__security_cookie
0x180034334  xor     rax, rsp
0x180034337  mov     [rsp+0A8h+var_58], rax
0x18003433c  xor     r12d, r12d
0x18003433f  mov     [rsp+0A8h+var_78], rcx
0x180034344  xor     ebx, ebx
0x180034346  mov     [rsp+0A8h+var_88], r12d
0x18003434b  xor     esi, esi
0x18003434d  mov     r13, rcx
0x180034350  cmp     [rcx+1F8h], ebx
0x180034356  jbe     loc_180034598
0x18003435c  lea     rax, [rcx+120h]
0x180034363  mov     [rsp+0A8h+var_70], rax
0x180034368  mov     edx, r12d
0x18003436b  mov     rcx, rax
0x18003436e  call    ??A?$CTDynArray@PEAUMULTI_GROUP@CASFStreamSelector@@$0BE@@@QEBAPEAUMULTI_GROUP@CASFStreamSelector@@K@Z; CTDynArray<CASFStreamSelector::MULTI_GROUP *,20>::operator[](ulong)
0x180034373  mov     r13, rax
0x180034376  mov     [rsp+0A8h+var_80], rax
0x18003437b  xorps   xmm0, xmm0
0x18003437e  lea     rdx, [rsp+0A8h+Buf2]
0x180034383  movups  [rsp+0A8h+Buf2], xmm0
0x180034388  mov     rcx, [rax+0E8h]
0x18003438f  mov     rax, [rcx]
0x180034392  mov     rax, [rax+50h]
0x180034396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003439b  mov     ebx, eax
0x18003439d  test    eax, eax
0x18003439f  js      loc_180034727
0x1800343a5  mov     r8d, 10h; Size
0x1800343ab  lea     rdx, [rsp+0A8h+Buf2]; Buf2
0x1800343b0  lea     rcx, CLSID_ASFMutexBitrate; Buf1
0x1800343b7  call    memcmp_0
0x1800343bc  test    eax, eax
0x1800343be  jnz     loc_18003456E
0x1800343c4  xor     edx, edx
0x1800343c6  mov     rcx, r13
0x1800343c9  call    ??A?$CTDynArray@PEAUSTREAM_GROUP@CASFStreamSelector@@$0BE@@@QEBAPEAUSTREAM_GROUP@CASFStreamSelector@@K@Z; CTDynArray<CASFStreamSelector::STREAM_GROUP *,20>::operator[](ulong)
0x1800343ce  mov     r14, rax
0x1800343d1  xor     r15d, r15d
0x1800343d4  cmp     r15d, [r14+0D8h]
0x1800343db  jnb     loc_1800344CB
0x1800343e1  mov     edx, r15d
0x1800343e4  mov     rcx, r14
0x1800343e7  call    ??A?$CTDynArray@PEAUSTREAM_INFO@CASFStreamSelector@@$0BE@@@QEBAPEAUSTREAM_INFO@CASFStreamSelector@@K@Z; CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::operator[](ulong)
0x1800343ec  mov     r13, rax
0x1800343ef  cmp     dword ptr [rax+0Ch], 0
0x1800343f3  jz      loc_1800344C3
0x1800343f9  test    rsi, rsi
0x1800343fc  jnz     short loc_180034425
0x1800343fe  mov     ecx, 0F0h; Size
0x180034403  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180034408  test    rax, rax
0x18003440b  jz      loc_18003458E
0x180034411  mov     rcx, rax; this
0x180034414  call    ??0STREAM_GROUP@CASFStreamSelector@@QEAA@XZ; CASFStreamSelector::STREAM_GROUP::STREAM_GROUP(void)
0x180034419  mov     rsi, rax
0x18003441c  test    rax, rax
0x18003441f  jz      loc_18003458E
0x180034425  mov     ecx, 110h; Size
0x18003442a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003442f  test    rax, rax
0x180034432  jz      loc_180034722
0x180034438  mov     rcx, rax; this
0x18003443b  call    ??0STREAM_INFO@CASFStreamSelector@@QEAA@XZ; CASFStreamSelector::STREAM_INFO::STREAM_INFO(void)
0x180034440  mov     rdi, rax
0x180034443  test    rax, rax
0x180034446  jz      loc_180034722
0x18003444c  movzx   ecx, word ptr [r13+0]
0x180034451  mov     r12, [rsp+0A8h+var_78]
0x180034456  mov     [rax], cx
0x180034459  mov     ecx, [r13+4]
0x18003445d  shr     ecx, 1
0x18003445f  mov     [rax+4], ecx
0x180034462  xor     ebp, ebp
0x180034464  movzx   ecx, word ptr [r13+2]
0x180034469  mov     [rax+2], cx
0x18003446d  mov     dword ptr [rax+0Ch], 0
0x180034474  mov     dword ptr [rax+10h], 1
0x18003447b  mov     ecx, [r13+8]
0x18003447f  mov     [rax+8], ecx
0x180034482  mov     qword ptr [rax+14h], 3E8h
0x18003448a  cmp     ebp, [r12+118h]
0x180034492  jnb     short loc_1800344B8
0x180034494  mov     edx, ebp
0x180034496  lea     rcx, [r12+40h]
0x18003449b  call    ??A?$CTDynArray@PEAUSTREAM_INFO@CASFStreamSelector@@$0BE@@@QEBAPEAUSTREAM_INFO@CASFStreamSelector@@K@Z; CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::operator[](ulong)
0x1800344a0  cmp     rax, r13
0x1800344a3  jz      short loc_1800344A9
0x1800344a5  inc     ebp
0x1800344a7  jmp     short loc_18003448A
0x1800344a9  mov     r8, rdi
0x1800344ac  lea     rcx, [r12+40h]
0x1800344b1  mov     edx, ebp
0x1800344b3  call    ?InsertAt@?$CTDynArray@PEAUSTREAM_INFO@CASFStreamSelector@@$0BE@@@QEAAHKPEAUSTREAM_INFO@CASFStreamSelector@@@Z; CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::InsertAt(ulong,CASFStreamSelector::STREAM_INFO *)
0x1800344b8  mov     rdx, rdi; struct CASFStreamSelector::STREAM_INFO *
0x1800344bb  mov     rcx, rsi; this
0x1800344be  call    ?Add@STREAM_GROUP@CASFStreamSelector@@QEAAXPEAUSTREAM_INFO@2@@Z; CASFStreamSelector::STREAM_GROUP::Add(CASFStreamSelector::STREAM_INFO *)
0x1800344c3  inc     r15d
0x1800344c6  jmp     loc_1800343D4
0x1800344cb  mov     r13, [rsp+0A8h+var_80]
0x1800344d0  test    rsi, rsi
0x1800344d3  jz      short loc_18003451E
0x1800344d5  mov     eax, [r14+0E0h]
0x1800344dc  mov     r8, rsi
0x1800344df  shr     eax, 1
0x1800344e1  xor     edx, edx
0x1800344e3  mov     [rsi+0E0h], eax
0x1800344e9  mov     rcx, r13
0x1800344ec  mov     eax, [r14+0E4h]
0x1800344f3  shr     eax, 1
0x1800344f5  mov     [rsi+0E4h], eax
0x1800344fb  mov     eax, [r14+0E8h]
0x180034502  shr     eax, 1
0x180034504  mov     [rsi+0E8h], eax
0x18003450a  mov     eax, [r14+0ECh]
0x180034511  mov     [rsi+0ECh], eax
0x180034517  call    ?InsertAt@?$CTDynArray@PEAUSTREAM_GROUP@CASFStreamSelector@@$0BE@@@QEAAHKPEAUSTREAM_GROUP@CASFStreamSelector@@@Z; CTDynArray<CASFStreamSelector::STREAM_GROUP *,20>::InsertAt(ulong,CASFStreamSelector::STREAM_GROUP *)
0x18003451c  xor     esi, esi
0x18003451e  xor     edi, edi
0x180034520  xor     r15d, r15d
0x180034523  cmp     [r13+0D8h], r15d
0x18003452a  jbe     short loc_180034569
0x18003452c  mov     edx, edi
0x18003452e  mov     rcx, r13
0x180034531  call    ??A?$CTDynArray@PEAUSTREAM_GROUP@CASFStreamSelector@@$0BE@@@QEBAPEAUSTREAM_GROUP@CASFStreamSelector@@K@Z; CTDynArray<CASFStreamSelector::STREAM_GROUP *,20>::operator[](ulong)
0x180034536  mov     r14, rax
0x180034539  mov     ebp, r15d
0x18003453c  cmp     [rax+0D8h], r15d
0x180034543  jbe     short loc_18003455E
0x180034545  mov     edx, ebp
0x180034547  mov     rcx, r14
0x18003454a  call    ??A?$CTDynArray@PEAUSTREAM_INFO@CASFStreamSelector@@$0BE@@@QEBAPEAUSTREAM_INFO@CASFStreamSelector@@K@Z; CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::operator[](ulong)
0x18003454f  inc     ebp
0x180034551  mov     [rax+0Ch], r15d
0x180034555  cmp     ebp, [r14+0D8h]
0x18003455c  jb      short loc_180034545
0x18003455e  inc     edi
0x180034560  cmp     edi, [r13+0D8h]
0x180034567  jb      short loc_18003452C
0x180034569  mov     r12d, [rsp+0A8h+var_88]
0x18003456e  mov     r13, [rsp+0A8h+var_78]
0x180034573  inc     r12d
0x180034576  mov     [rsp+0A8h+var_88], r12d
0x18003457b  cmp     r12d, [r13+1F8h]
0x180034582  jnb     short loc_180034598
0x180034584  mov     rax, [rsp+0A8h+var_70]
0x180034589  jmp     loc_180034368
0x18003458e  mov     ebx, 8007000Eh
0x180034593  jmp     loc_180034734
0x180034598  xor     ebp, ebp
0x18003459a  cmp     ebp, [r13+118h]
0x1800345a1  jnb     loc_180034727
0x1800345a7  mov     edx, ebp
0x1800345a9  lea     rcx, [r13+40h]
0x1800345ad  call    ??A?$CTDynArray@PEAUSTREAM_INFO@CASFStreamSelector@@$0BE@@@QEBAPEAUSTREAM_INFO@CASFStreamSelector@@K@Z; CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::operator[](ulong)
0x1800345b2  mov     r15, rax
0x1800345b5  cmp     dword ptr [rax+0Ch], 0
0x1800345b9  jz      loc_18003470C
0x1800345bf  mov     ecx, 110h; Size
0x1800345c4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800345c9  test    rax, rax
0x1800345cc  jz      loc_180034722
0x1800345d2  mov     rcx, rax; this
0x1800345d5  call    ??0STREAM_INFO@CASFStreamSelector@@QEAA@XZ; CASFStreamSelector::STREAM_INFO::STREAM_INFO(void)
0x1800345da  mov     r14, rax
0x1800345dd  test    rax, rax
0x1800345e0  jz      loc_180034722
0x1800345e6  movzx   ecx, word ptr [r15]
0x1800345ea  mov     r8, rax
0x1800345ed  mov     [rax], cx
0x1800345f0  mov     edx, ebp
0x1800345f2  mov     ecx, [r15+4]
0x1800345f6  shr     ecx, 1
0x1800345f8  mov     [rax+4], ecx
0x1800345fb  movzx   ecx, word ptr [r15+2]
0x180034600  mov     [rax+2], cx
0x180034604  mov     dword ptr [rax+0Ch], 0
0x18003460b  mov     dword ptr [rax+10h], 1
0x180034612  mov     ecx, [r15+8]
0x180034616  mov     [rax+8], ecx
0x180034619  lea     rcx, [r13+40h]
0x18003461d  mov     qword ptr [rax+14h], 3E8h
0x180034625  call    ?InsertAt@?$CTDynArray@PEAUSTREAM_INFO@CASFStreamSelector@@$0BE@@@QEAAHKPEAUSTREAM_INFO@CASFStreamSelector@@@Z; CTDynArray<CASFStreamSelector::STREAM_INFO *,20>::InsertAt(ulong,CASFStreamSelector::STREAM_INFO *)
0x18003462a  mov     ecx, 0F0h; Size
0x18003462f  mov     dword ptr [r15+0Ch], 0
0x180034637  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003463c  mov     rdi, rax
0x18003463f  test    rax, rax
0x180034642  jz      loc_180034722
0x180034648  xor     esi, esi
0x18003464a  mov     ecx, 0F0h; Size
0x18003464f  mov     [rax+8], rsi
0x180034653  xor     eax, eax
0x180034655  mov     [rdi+18h], ax
0x180034659  mov     [rdi+1Ah], al
0x18003465c  lea     rax, ??_7?$CTSparseBlock@KPEAUSTREAM_NAME_REC@CASFStreamPropertiesObjectBase@@$0BE@$0A@@@6B@; const CTSparseBlock<ulong,CASFStreamPropertiesObjectBase::STREAM_NAME_REC *,20,0>::`vftable'
0x180034663  mov     [rdi], rax
0x180034666  mov     [rdi+0C0h], rsi
0x18003466d  mov     [rdi+0C8h], rdi
0x180034674  mov     [rdi+0D0h], esi
0x18003467a  mov     [rdi+0D8h], esi
0x180034680  mov     [rdi+0E8h], rsi
0x180034687  mov     dword ptr [rdi+0E0h], 1
0x180034691  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180034696  test    rax, rax
0x180034699  jz      short loc_180034713
0x18003469b  mov     rcx, rax; this
0x18003469e  call    ??0STREAM_GROUP@CASFStreamSelector@@QEAA@XZ; CASFStreamSelector::STREAM_GROUP::STREAM_GROUP(void)
0x1800346a3  mov     rsi, rax
0x1800346a6  test    rax, rax
0x1800346a9  jz      short loc_180034713
0x1800346ab  mov     rdx, r14; struct CASFStreamSelector::STREAM_INFO *
0x1800346ae  mov     rcx, rax; this
0x1800346b1  call    ?Add@STREAM_GROUP@CASFStreamSelector@@QEAAXPEAUSTREAM_INFO@2@@Z; CASFStreamSelector::STREAM_GROUP::Add(CASFStreamSelector::STREAM_INFO *)
0x1800346b6  mov     rdx, rsi
0x1800346b9  mov     rcx, rdi
0x1800346bc  call    ?Add@?$CTDynArray@PEAUSTREAM_GROUP@CASFStreamSelector@@$0BE@@@QEAAHPEAUSTREAM_GROUP@CASFStreamSelector@@PEAK@Z; CTDynArray<CASFStreamSelector::STREAM_GROUP *,20>::Add(CASFStreamSelector::STREAM_GROUP *,ulong *)
0x1800346c1  mov     ecx, 0F0h; Size
0x1800346c6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800346cb  test    rax, rax
0x1800346ce  jz      short loc_180034713
0x1800346d0  mov     rcx, rax; this
0x1800346d3  call    ??0STREAM_GROUP@CASFStreamSelector@@QEAA@XZ; CASFStreamSelector::STREAM_GROUP::STREAM_GROUP(void)
0x1800346d8  mov     rsi, rax
0x1800346db  test    rax, rax
0x1800346de  jz      short loc_180034713
0x1800346e0  mov     rdx, r15; struct CASFStreamSelector::STREAM_INFO *
0x1800346e3  mov     rcx, rax; this
0x1800346e6  call    ?Add@STREAM_GROUP@CASFStreamSelector@@QEAAXPEAUSTREAM_INFO@2@@Z; CASFStreamSelector::STREAM_GROUP::Add(CASFStreamSelector::STREAM_INFO *)
0x1800346eb  mov     rdx, rsi
0x1800346ee  mov     rcx, rdi
0x1800346f1  call    ?Add@?$CTDynArray@PEAUSTREAM_GROUP@CASFStreamSelector@@$0BE@@@QEAAHPEAUSTREAM_GROUP@CASFStreamSelector@@PEAK@Z; CTDynArray<CASFStreamSelector::STREAM_GROUP *,20>::Add(CASFStreamSelector::STREAM_GROUP *,ulong *)
0x1800346f6  lea     rcx, [r13+120h]
0x1800346fd  mov     rdx, rdi
0x180034700  lea     r8, [rsp+0A8h+var_88]
0x180034705  xor     esi, esi
0x180034707  call    ?Add@?$CTDynArray@PEAUMULTI_GROUP@CASFStreamSelector@@$0BE@@@QEAAHPEAUMULTI_GROUP@CASFStreamSelector@@PEAK@Z; CTDynArray<CASFStreamSelector::MULTI_GROUP *,20>::Add(CASFStreamSelector::MULTI_GROUP *,ulong *)
0x18003470c  inc     ebp
0x18003470e  jmp     loc_18003459A
0x180034713  mov     rcx, rdi; this
0x180034716  mov     ebx, 8007000Eh
0x18003471b  call    ??_GMULTI_GROUP@CASFStreamSelector@@QEAAPEAXI@Z; CASFStreamSelector::MULTI_GROUP::`scalar deleting destructor'(uint)
0x180034720  jmp     short loc_180034734
0x180034722  mov     ebx, 8007000Eh
0x180034727  test    rsi, rsi
0x18003472a  jz      short loc_180034734
0x18003472c  mov     rcx, rsi; this
0x18003472f  call    ??_GSTREAM_GROUP@CASFStreamSelector@@QEAAPEAXI@Z; CASFStreamSelector::STREAM_GROUP::`scalar deleting destructor'(uint)
0x180034734  mov     eax, ebx
0x180034736  mov     rcx, [rsp+0A8h+var_58]
0x18003473b  xor     rcx, rsp; StackCookie
0x18003473e  call    __security_check_cookie
0x180034743  add     rsp, 68h
0x180034747  pop     r15
0x180034749  pop     r14
0x18003474b  pop     r13
0x18003474d  pop     r12
0x18003474f  pop     rdi
0x180034750  pop     rsi
0x180034751  pop     rbp
0x180034752  pop     rbx
0x180034753  retn
```
