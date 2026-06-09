# CSpCfgInst::ResolveWords(void)

- ea: `0x18005f020`
- end: `0x18005f571`
- name: `?ResolveWords@CSpCfgInst@@IEAAJXZ`
- size: `1361`
- prototype: `__int64 __fastcall(CSpCfgInst *__hidden this)`
- caller_count: `2`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180052400`
- `0x18005e5e8`

## callees

- `0x180002470`
- `0x180002db8`
- `0x180002e00`
- `0x1800141c0`
- `0x18005bd4c`
- `0x18005c0cc`
- `0x18005cd5c`
- `0x18005eadc`
- `0x18005f020`
- `0x1800602d8`
- `0x18006032c`
- `0x1800604c4`
- `0x180060624`
- `0x1800606d0`
- `0x18009b8a4`
- `0x1800d455c`
- `0x1800d5d24`
- `0x1800d5d40`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005f190`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005f190`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSpCfgInst::ResolveWords(CSpCfgInst *this)
{
  __int64 v2; // rcx
  unsigned int *v3; // rcx
  unsigned int v4; // ebx
  __int64 v5; // rax
  int CfgPronunciationBlob; // eax
  __int64 v7; // rcx
  unsigned __int64 v8; // rsi
  SIZE_T v9; // rax
  _DWORD *v10; // r15
  HRESULT v11; // ebx
  void *v12; // r12
  unsigned __int16 *v13; // r14
  int v14; // r13d
  __int64 v15; // rcx
  unsigned int v16; // r11d
  unsigned int v17; // edx
  int v18; // r11d
  __int64 v19; // rdx
  __int64 v20; // r8
  unsigned int v21; // r12d
  IDEXTBL *v22; // r10
  __int64 v23; // rsi
  enum SPMATCHINGMODE v24; // r15d
  __int64 v25; // r8
  __int64 v26; // rdx
  SPPHONEID *aPhoneId; // r9
  __int64 v28; // rbx
  int v29; // eax
  int v30; // ecx
  unsigned int v31; // edx
  __int64 v32; // rcx
  int v33; // edx
  int v34; // r8d
  __int64 v35; // rcx
  unsigned int v37[2]; // [rsp+50h] [rbp-89h] BYREF
  int v38; // [rsp+58h] [rbp-81h] BYREF
  void *v39; // [rsp+60h] [rbp-79h]
  LPVOID v40; // [rsp+68h] [rbp-71h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp-69h] BYREF
  __int64 v42; // [rsp+78h] [rbp-61h]
  _DWORD *v43; // [rsp+80h] [rbp-59h]
  __int64 v44; // [rsp+88h] [rbp-51h]
  __int64 v45; // [rsp+90h] [rbp-49h]
  struct SPWORDENTRY v46; // [rsp+98h] [rbp-41h] BYREF
  SPMATCHINGMODE v47[4]; // [rsp+C8h] [rbp-11h] BYREF
  __int128 v48; // [rsp+D8h] [rbp-1h]

  v2 = *(_QWORD *)(*((_QWORD *)this + 32) + 224LL);
  *(_OWORD *)v47 = 0;
  v48 = 0;
  v4 = 0;
  if ( (unsigned int)CSpCfgData::SpGetCFGHeaderVersion(v2) <= 1
    || (v5 = v3[36], !(_DWORD)v5)
    || (CfgPronunciationBlob = CSpCfgData::SpGetCfgPronunciationBlob(
                                 (CSpCfgData *)v3,
                                 (const struct SPCFGSERIALIZEDHEADER *)v3,
                                 *(unsigned int *)((char *)v3 + v5 + 4),
                                 (struct SPCFGPRONUNCIATIONBLOB *)v47),
        v7 = 0,
        CfgPronunciationBlob >> 31 != -1) )
  {
    v7 = v48;
  }
  v42 = v7;
  v45 = (v7 + 8) & -(__int64)(v7 != 0);
  v44 = *((_QWORD *)this + 10);
  v8 = *((unsigned int *)this + 18);
  ppv = 0;
  v9 = 4 * v8;
  if ( !is_mul_ok(v8, 4u) )
    v9 = -1;
  v10 = CWinHeap::Alloc(&g_heap, v9, 0);
  v43 = v10;
  if ( !v10 )
  {
    v11 = -2147024882;
    goto LABEL_67;
  }
  v12 = CWinHeap::Alloc(&g_heap, 0x302u, 0);
  v39 = v12;
  if ( v12 )
  {
    v13 = (unsigned __int16 *)CWinHeap::Alloc(&g_heap, 0x6402u, 0);
    if ( !v13 )
      goto LABEL_11;
    v14 = 0;
    v38 = 0;
    v15 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 33) + 24LL) + 16LL);
    (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v15 + 144LL))(v15, &v38);
    if ( (*((_BYTE *)this + 228) & 4) != 0 )
    {
      if ( v38 )
      {
LABEL_22:
        v16 = 0;
        v17 = *((_DWORD *)this + 19);
        if ( v17 )
        {
          do
          {
            *(_QWORD *)v37 = 0;
            v10[v4] = v16;
            if ( (int)StringCchLengthW(
                        (const unsigned __int16 *)(v44 + 2LL * v16),
                        (unsigned int)v8 - v16,
                        (unsigned __int64 *)v37) < 0 )
              goto LABEL_42;
            v16 = v37[0] + 1 + v18;
            ++v4;
            v17 = *((_DWORD *)this + 19);
          }
          while ( v4 < v17 );
        }
        if ( v16 != (_DWORD)v8 )
        {
LABEL_42:
          v11 = -2147201021;
          goto LABEL_62;
        }
        v11 = IDEXTBL::SetSize((CSpCfgInst *)((char *)this + 296), v17);
        v20 = 0;
        if ( v11 < 0 )
        {
LABEL_62:
          v10 = v43;
          goto LABEL_63;
        }
        *(_OWORD *)v47 = 0;
        v21 = 0;
        if ( !*((_DWORD *)this + 30) )
        {
LABEL_58:
          v32 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 33) + 24LL) + 456LL);
          (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v32 + 304LL))(v32, v19, v20);
          v35 = *((_QWORD *)this + 1);
          if ( v35 && (**(_BYTE **)(v35 + 56) & 0x20) != 0 )
            McTemplateMofU0dd(v35 + 8, v33, v34, *((_DWORD *)this + 84), *((_DWORD *)this + 92));
LABEL_61:
          v12 = v39;
          goto LABEL_62;
        }
        while ( 1 )
        {
          CSpCfgData::GetArcDataByIndex(*((CSpCfgData **)this + 32), v21, (struct SPARCDATA *)v47);
          if ( !LOBYTE(v47[0]) )
          {
            v23 = (unsigned int)v47[2];
            if ( (unsigned int)(v47[2] - 1) <= 0x3FFFFB || v47[2] >= 0x400000u )
            {
              v37[0] = -1;
              if ( v47[2] >= *((_DWORD *)this + 19) )
              {
                v11 = -2147201021;
                goto LABEL_61;
              }
              v24 = v47[3];
              if ( IDEXTBL::WordIdx2Lwid(v22, v47[2], v47[3]) == -1 )
                break;
            }
          }
LABEL_57:
          if ( ++v21 >= *((_DWORD *)this + 30) )
            goto LABEL_58;
        }
        StringCchCopyW(v13, 0x3201u, (const unsigned __int16 *)(v44 + 2LL * (unsigned int)v43[v23]));
        memset(&v46, 0, sizeof(v46));
        LOBYTE(v25) = v24 == AllWords;
        v11 = SetWordInfo(v13, &v46, v25);
        if ( v11 < 0 )
          goto LABEL_61;
        if ( v24 )
        {
          v29 = (*(__int64 (__fastcall **)(CSpCfgInst *, struct SPWORDENTRY *, _QWORD, unsigned int *))(*(_QWORD *)this + 8LL))(
                  this,
                  &v46,
                  (unsigned int)v24,
                  v37);
        }
        else
        {
          aPhoneId = v46.aPhoneId;
          if ( !v42 || (v28 = (unsigned int)(v23 - 1), !*(_DWORD *)(v45 + 4 * v28)) || v46.aPhoneId && *v46.aPhoneId )
          {
            if ( v14 )
            {
              v30 = (int)ppv;
              v40 = ppv;
              if ( ppv )
                (*(void (__fastcall **)(LPVOID, __int64, _QWORD, SPPHONEID *))(*(_QWORD *)ppv + 8LL))(
                  ppv,
                  v26,
                  0,
                  v46.aPhoneId);
              CSpCfgInst::ConvertPhones(v30, v38, (unsigned int)&v40, (unsigned int)&v46.aPhoneId, (__int64)v39);
              aPhoneId = v46.aPhoneId;
            }
            v29 = CPPT::AddCompleteWord(
                    *((_QWORD *)this + 33),
                    v46.pszDisplayText,
                    v46.pszLexicalForm,
                    aPhoneId,
                    -73729);
            if ( v29 == -2147200999 || v29 == -2147220453 )
            {
              if ( (*(int (__fastcall **)(CSpCfgInst *, struct SPWORDENTRY *, _QWORD, unsigned int *))(*(_QWORD *)this + 8LL))(
                     this,
                     &v46,
                     0,
                     v37) >= 0 )
              {
                v31 = v37[0];
                if ( v37[0] != -1 )
                {
LABEL_56:
                  CSpCfgInst::LogPronNum(this, v31, &v46);
                  v11 = IDEXTBL::Add((CSpCfgInst *)((char *)this + 296), v23, v43[v23], v24, v37[0]);
                  if ( v11 < 0 )
                    goto LABEL_61;
                  goto LABEL_57;
                }
              }
              v29 = CPPT::AddCompleteWord(
                      *((_QWORD *)this + 33),
                      v46.pszDisplayText,
                      v46.pszLexicalForm,
                      v46.aPhoneId,
                      73728);
            }
          }
          else
          {
            v40 = ppv;
            if ( ppv )
              (*(void (__fastcall **)(LPVOID, __int64, _QWORD, SPPHONEID *))(*(_QWORD *)ppv + 8LL))(
                ppv,
                v26,
                0,
                v46.aPhoneId);
            v29 = CSpCfgInst::AddWordWithCustomProns(
                    (_DWORD)this,
                    (int)v42 + *(_DWORD *)(v45 + 4 * v28),
                    (unsigned int)&v46,
                    v14,
                    v38,
                    (__int64)&v40,
                    (__int64)v37);
          }
        }
        if ( v29 >= 0 )
        {
          v31 = v37[0];
        }
        else
        {
          v31 = -1;
          v37[0] = -1;
        }
        goto LABEL_56;
      }
    }
    else if ( !v38 )
    {
      goto LABEL_22;
    }
    v11 = CoCreateInstance(
            &CLSID_SpPhoneticAlphabetConverter,
            0,
            0x17u,
            &GUID_133adcd4_19b4_4020_9fdc_842e78253b17,
            &ppv);
    if ( v11 < 0 )
      goto LABEL_62;
    v11 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 32LL))(ppv, *((unsigned __int16 *)this + 32));
    if ( v11 < 0 )
      goto LABEL_62;
    if ( v11 != 1 )
      v14 = 1;
    v4 = 0;
    goto LABEL_22;
  }
  v13 = 0;
LABEL_11:
  v11 = -2147024882;
LABEL_63:
  operator delete(v10);
  if ( v12 )
    operator delete(v12);
  if ( v13 )
    operator delete(v13);
LABEL_67:
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&ppv);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18005f020  push    rbp
0x18005f022  push    rbx
0x18005f023  push    rsi
0x18005f024  push    rdi
0x18005f025  push    r12
0x18005f027  push    r13
0x18005f029  push    r14
0x18005f02b  push    r15
0x18005f02d  lea     rbp, [rsp-1Fh]
0x18005f032  sub     rsp, 0F8h
0x18005f039  mov     rdi, rcx
0x18005f03c  mov     rax, [rcx+100h]
0x18005f043  mov     rcx, [rax+0E0h]
0x18005f04a  xorps   xmm0, xmm0
0x18005f04d  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x18005f051  movups  [rbp+57h+var_58], xmm0
0x18005f055  call    ?SpGetCFGHeaderVersion@CSpCfgData@@SA?AW4HEADERVERSION@@PEBUSPCFGSERIALIZEDHEADER@@@Z; CSpCfgData::SpGetCFGHeaderVersion(SPCFGSERIALIZEDHEADER const *)
0x18005f05a  xor     ebx, ebx
0x18005f05c  cmp     eax, 1
0x18005f05f  jbe     short loc_18005F088
0x18005f061  mov     eax, [rcx+90h]
0x18005f067  test    eax, eax
0x18005f069  jz      short loc_18005F088
0x18005f06b  lea     r9, [rbp+57h+var_68]; struct SPCFGPRONUNCIATIONBLOB *
0x18005f06f  mov     r8d, [rax+rcx+4]; unsigned int
0x18005f074  mov     rdx, rcx; struct SPCFGSERIALIZEDHEADER *
0x18005f077  call    ?SpGetCfgPronunciationBlob@CSpCfgData@@AEAAJPEBUSPCFGSERIALIZEDHEADER@@KPEAUSPCFGPRONUNCIATIONBLOB@@@Z; CSpCfgData::SpGetCfgPronunciationBlob(SPCFGSERIALIZEDHEADER const *,ulong,SPCFGPRONUNCIATIONBLOB *)
0x18005f07c  sar     eax, 1Fh
0x18005f07f  and     eax, 80045086h
0x18005f084  mov     ecx, ebx
0x18005f086  jl      short loc_18005F08C
0x18005f088  mov     rcx, qword ptr [rbp+57h+var_58]
0x18005f08c  mov     [rbp+57h+var_B8], rcx
0x18005f090  mov     rax, rcx
0x18005f093  add     rcx, 8
0x18005f097  neg     rax
0x18005f09a  sbb     rax, rax
0x18005f09d  and     rax, rcx
0x18005f0a0  mov     [rbp+57h+var_A0], rax
0x18005f0a4  mov     rax, [rdi+50h]
0x18005f0a8  mov     [rbp+57h+var_A8], rax
0x18005f0ac  mov     esi, [rdi+48h]
0x18005f0af  mov     [rbp+57h+var_C0], rbx
0x18005f0b3  mov     eax, 4
0x18005f0b8  mul     rsi
0x18005f0bb  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18005f0c2  cmovb   rax, rcx
0x18005f0c6  xor     r8d, r8d; bool
0x18005f0c9  mov     rdx, rax; unsigned __int64
0x18005f0cc  lea     r14, ?g_heap@@3VCHeap@@A; CHeap g_heap
0x18005f0d3  mov     rcx, r14; this
0x18005f0d6  call    ?Alloc@CWinHeap@@QEAAPEAX_K_N@Z; CWinHeap::Alloc(unsigned __int64,bool)
0x18005f0db  mov     r15, rax
0x18005f0de  mov     [rbp+57h+var_B0], rax
0x18005f0e2  test    rax, rax
0x18005f0e5  jnz     short loc_18005F0F1
0x18005f0e7  mov     ebx, 8007000Eh
0x18005f0ec  jmp     loc_18005F54A
0x18005f0f1  xor     r8d, r8d; bool
0x18005f0f4  mov     edx, 302h; unsigned __int64
0x18005f0f9  mov     rcx, r14; this
0x18005f0fc  call    ?Alloc@CWinHeap@@QEAAPEAX_K_N@Z; CWinHeap::Alloc(unsigned __int64,bool)
0x18005f101  mov     r12, rax
0x18005f104  mov     [rbp+57h+var_D0], rax
0x18005f108  test    rax, rax
0x18005f10b  jnz     short loc_18005F11A
0x18005f10d  mov     r14, rbx
0x18005f110  mov     ebx, 8007000Eh
0x18005f115  jmp     loc_18005F527
0x18005f11a  xor     r8d, r8d; bool
0x18005f11d  mov     edx, 6402h; unsigned __int64
0x18005f122  mov     rcx, r14; this
0x18005f125  call    ?Alloc@CWinHeap@@QEAAPEAX_K_N@Z; CWinHeap::Alloc(unsigned __int64,bool)
0x18005f12a  mov     r14, rax
0x18005f12d  test    rax, rax
0x18005f130  jz      short loc_18005F110
0x18005f132  mov     r13d, ebx
0x18005f135  mov     [rsp+130h+var_D8], ebx
0x18005f139  mov     rax, [rdi+108h]
0x18005f140  mov     rcx, [rax+18h]
0x18005f144  mov     rcx, [rcx+10h]
0x18005f148  mov     rax, [rcx]
0x18005f14b  lea     rdx, [rsp+130h+var_D8]
0x18005f150  mov     rax, [rax+90h]
0x18005f157  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f15c  test    byte ptr [rdi+0E4h], 4
0x18005f163  jnz     short loc_18005F16D
0x18005f165  cmp     [rsp+130h+var_D8], ebx
0x18005f169  jnz     short loc_18005F173
0x18005f16b  jmp     short loc_18005F1CB
0x18005f16d  cmp     [rsp+130h+var_D8], ebx
0x18005f171  jnz     short loc_18005F1CB
0x18005f173  lea     rax, [rbp+57h+var_C0]
0x18005f177  mov     [rsp+130h+ppv], rax; ppv
0x18005f17c  lea     r9, _GUID_133adcd4_19b4_4020_9fdc_842e78253b17; riid
0x18005f183  xor     edx, edx; pUnkOuter
0x18005f185  lea     r8d, [rdx+17h]; dwClsContext
0x18005f189  lea     rcx, CLSID_SpPhoneticAlphabetConverter; rclsid
0x18005f190  call    cs:__imp_CoCreateInstance
0x18005f196  mov     ebx, eax
0x18005f198  test    eax, eax
0x18005f19a  js      loc_18005F523
0x18005f1a0  mov     rcx, [rbp+57h+var_C0]
0x18005f1a4  mov     rax, [rcx]
0x18005f1a7  movzx   edx, word ptr [rdi+40h]
0x18005f1ab  mov     rax, [rax+20h]
0x18005f1af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f1b4  mov     ebx, eax
0x18005f1b6  test    eax, eax
0x18005f1b8  js      loc_18005F523
0x18005f1be  mov     eax, 1
0x18005f1c3  cmp     ebx, eax
0x18005f1c5  cmovnz  r13d, eax
0x18005f1c9  xor     ebx, ebx
0x18005f1cb  mov     r11d, ebx
0x18005f1ce  mov     edx, [rdi+4Ch]
0x18005f1d1  xor     r8d, r8d
0x18005f1d4  test    edx, edx
0x18005f1d6  jz      short loc_18005F21A
0x18005f1d8  mov     qword ptr [rsp+130h+var_E0], r8
0x18005f1dd  mov     eax, ebx
0x18005f1df  mov     [r15+rax*4], r11d
0x18005f1e3  mov     edx, esi
0x18005f1e5  sub     edx, r11d; unsigned __int64
0x18005f1e8  mov     eax, r11d
0x18005f1eb  mov     rcx, [rbp+57h+var_A8]
0x18005f1ef  lea     rcx, [rcx+rax*2]; unsigned __int16 *
0x18005f1f3  lea     r8, [rsp+130h+var_E0]; unsigned __int64 *
0x18005f1f8  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18005f1fd  xor     r8d, r8d
0x18005f200  test    eax, eax
0x18005f202  js      loc_18005F382
0x18005f208  mov     eax, [rsp+130h+var_E0]
0x18005f20c  inc     eax
0x18005f20e  add     r11d, eax
0x18005f211  inc     ebx
0x18005f213  mov     edx, [rdi+4Ch]; unsigned int
0x18005f216  cmp     ebx, edx
0x18005f218  jb      short loc_18005F1D8
0x18005f21a  cmp     r11d, esi
0x18005f21d  jnz     loc_18005F382
0x18005f223  lea     rcx, [rdi+128h]; this
0x18005f22a  call    ?SetSize@IDEXTBL@@QEAAJK@Z; IDEXTBL::SetSize(ulong)
0x18005f22f  mov     ebx, eax
0x18005f231  xor     r8d, r8d
0x18005f234  test    eax, eax
0x18005f236  js      loc_18005F523
0x18005f23c  xorps   xmm0, xmm0
0x18005f23f  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x18005f243  mov     r12d, r8d
0x18005f246  cmp     [rdi+78h], r8d
0x18005f24a  jbe     loc_18005F4D2
0x18005f250  lea     r10, [rdi+128h]
0x18005f257  lea     r8, [rbp+57h+var_68]; struct SPARCDATA *
0x18005f25b  mov     edx, r12d; unsigned int
0x18005f25e  mov     rcx, [rdi+100h]; this
0x18005f265  call    ?GetArcDataByIndex@CSpCfgData@@QEAAXKPEAUSPARCDATA@@@Z; CSpCfgData::GetArcDataByIndex(ulong,SPARCDATA *)
0x18005f26a  cmp     byte ptr [rbp+57h+var_68], 0
0x18005f26e  jnz     loc_18005F4C5
0x18005f274  mov     esi, [rbp+57h+var_68+8]
0x18005f277  lea     eax, [rsi-1]
0x18005f27a  cmp     eax, 3FFFFBh
0x18005f27f  jbe     short loc_18005F28D
0x18005f281  cmp     esi, 400000h
0x18005f287  jb      loc_18005F4C5
0x18005f28d  mov     [rsp+130h+var_E0], 0FFFFFFFFh
0x18005f295  cmp     esi, [rdi+4Ch]
0x18005f298  jnb     loc_18005F569
0x18005f29e  mov     r15d, [rbp+57h+var_68+0Ch]
0x18005f2a2  mov     r8d, r15d; enum SPMATCHINGMODE
0x18005f2a5  mov     edx, esi; unsigned int
0x18005f2a7  mov     rcx, r10; this
0x18005f2aa  call    ?WordIdx2Lwid@IDEXTBL@@QEAAIKW4SPMATCHINGMODE@@@Z; IDEXTBL::WordIdx2Lwid(ulong,SPMATCHINGMODE)
0x18005f2af  cmp     eax, 0FFFFFFFFh
0x18005f2b2  jnz     loc_18005F4C5
0x18005f2b8  mov     rcx, [rbp+57h+var_B0]
0x18005f2bc  mov     eax, [rcx+rsi*4]
0x18005f2bf  mov     rcx, [rbp+57h+var_A8]
0x18005f2c3  lea     r8, [rcx+rax*2]; unsigned __int16 *
0x18005f2c7  mov     edx, 3201h; unsigned __int64
0x18005f2cc  mov     rcx, r14; unsigned __int16 *
0x18005f2cf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005f2d4  xorps   xmm0, xmm0
0x18005f2d7  movups  xmmword ptr [rbp+57h+var_98.hWord], xmm0
0x18005f2db  movups  xmmword ptr [rbp+57h+var_98.pszDisplayText], xmm0
0x18005f2df  movups  xmmword ptr [rbp+57h+var_98.aPhoneId], xmm0
0x18005f2e3  test    r15d, r15d
0x18005f2e6  setz    r8b
0x18005f2ea  lea     rdx, [rbp+57h+var_98]
0x18005f2ee  mov     rcx, r14
0x18005f2f1  call    SetWordInfo
0x18005f2f6  mov     ebx, eax
0x18005f2f8  xor     r8d, r8d
0x18005f2fb  test    eax, eax
0x18005f2fd  js      loc_18005F51F
0x18005f303  test    r15d, r15d
0x18005f306  jnz     loc_18005F45F
0x18005f30c  mov     r9, [rbp+57h+var_98.aPhoneId]
0x18005f310  cmp     [rbp+57h+var_B8], r8
0x18005f314  jz      short loc_18005F38C
0x18005f316  lea     ebx, [rsi-1]
0x18005f319  mov     rax, [rbp+57h+var_A0]
0x18005f31d  cmp     [rax+rbx*4], r8d
0x18005f321  jz      short loc_18005F38C
0x18005f323  test    r9, r9
0x18005f326  jz      short loc_18005F32E
0x18005f328  cmp     [r9], r8w
0x18005f32c  jnz     short loc_18005F38C
0x18005f32e  mov     rcx, [rbp+57h+var_C0]
0x18005f332  mov     [rbp+57h+var_C8], rcx
0x18005f336  test    rcx, rcx
0x18005f339  jz      short loc_18005F348
0x18005f33b  mov     rax, [rcx]
0x18005f33e  mov     rax, [rax+8]
0x18005f342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f347  nop
0x18005f348  mov     eax, [rsp+130h+var_D8]
0x18005f34c  mov     rcx, [rbp+57h+var_A0]
0x18005f350  mov     edx, [rcx+rbx*4]
0x18005f353  add     rdx, [rbp+57h+var_B8]
0x18005f357  lea     rcx, [rsp+130h+var_E0]
0x18005f35c  mov     [rsp+130h+var_100], rcx
0x18005f361  lea     rcx, [rbp+57h+var_C8]
0x18005f365  mov     [rsp+130h+var_108], rcx
0x18005f36a  mov     dword ptr [rsp+130h+ppv], eax
0x18005f36e  mov     r9d, r13d
0x18005f371  lea     r8, [rbp+57h+var_98]
0x18005f375  mov     rcx, rdi
0x18005f378  call    ?AddWordWithCustomProns@CSpCfgInst@@IEAAJPEAEPEAUSPWORDENTRY@@HHV?$CComPtr@UISpPhoneticAlphabetConverter@@@ATL@@PEAI@Z; CSpCfgInst::AddWordWithCustomProns(uchar *,SPWORDENTRY *,int,int,ATL::CComPtr<ISpPhoneticAlphabetConverter>,uint *)
0x18005f37d  jmp     loc_18005F47A
0x18005f382  mov     ebx, 80045003h
0x18005f387  jmp     loc_18005F523
0x18005f38c  test    r13d, r13d
0x18005f38f  jz      short loc_18005F3CC
0x18005f391  mov     rcx, [rbp+57h+var_C0]
0x18005f395  mov     [rbp+57h+var_C8], rcx
0x18005f399  test    rcx, rcx
0x18005f39c  jz      short loc_18005F3AB
0x18005f39e  mov     rax, [rcx]
0x18005f3a1  mov     rax, [rax+8]
0x18005f3a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f3aa  nop
0x18005f3ab  mov     rax, [rbp+57h+var_D0]
0x18005f3af  mov     [rsp+130h+ppv], rax
0x18005f3b4  lea     r9, [rbp+57h+var_98.aPhoneId]
0x18005f3b8  lea     r8, [rbp+57h+var_C8]
0x18005f3bc  mov     edx, [rsp+130h+var_D8]
0x18005f3c0  call    ?ConvertPhones@CSpCfgInst@@IEAAXHV?$CComPtr@UISpPhoneticAlphabetConverter@@@ATL@@PEAPEAGPEAGK@Z; CSpCfgInst::ConvertPhones(int,ATL::CComPtr<ISpPhoneticAlphabetConverter>,ushort * *,ushort *,ulong)
0x18005f3c5  mov     r9, [rbp+57h+var_98.aPhoneId]
0x18005f3c9  xor     r8d, r8d
0x18005f3cc  mov     [rsp+130h+var_F0], r8b
0x18005f3d1  lea     rax, [rsp+130h+var_E0]
0x18005f3d6  mov     [rsp+130h+var_F8], rax
0x18005f3db  mov     dword ptr [rsp+130h+ppv], 0FFFEDFFFh
0x18005f3e3  mov     r8, [rbp+57h+var_98.pszLexicalForm]
0x18005f3e7  mov     rdx, [rbp+57h+var_98.pszDisplayText]
0x18005f3eb  mov     rcx, [rdi+108h]
0x18005f3f2  call    ?AddCompleteWord@CPPT@@QEAAJPEBG00KGW4PronType_t@IPPT@@PEAI_N@Z; CPPT::AddCompleteWord(ushort const *,ushort const *,ushort const *,ulong,ushort,IPPT::PronType_t,uint *,bool)
0x18005f3f7  cmp     eax, 80045019h
0x18005f3fc  jz      short loc_18005F405
0x18005f3fe  cmp     eax, 8004041Bh
0x18005f403  jnz     short loc_18005F47A
0x18005f405  mov     rax, [rdi]
0x18005f408  lea     r9, [rsp+130h+var_E0]
0x18005f40d  xor     r8d, r8d
0x18005f410  lea     rdx, [rbp+57h+var_98]
0x18005f414  mov     rcx, rdi
0x18005f417  mov     rax, [rax+8]
0x18005f41b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f420  xor     ecx, ecx
0x18005f422  test    eax, eax
0x18005f424  js      short loc_18005F42F
0x18005f426  mov     edx, [rsp+130h+var_E0]
0x18005f42a  cmp     edx, 0FFFFFFFFh
0x18005f42d  jnz     short loc_18005F48B
0x18005f42f  mov     [rsp+130h+var_F0], cl
0x18005f433  lea     rax, [rsp+130h+var_E0]
0x18005f438  mov     [rsp+130h+var_F8], rax
0x18005f43d  mov     dword ptr [rsp+130h+ppv], 12000h
0x18005f445  mov     r9, [rbp+57h+var_98.aPhoneId]
0x18005f449  mov     r8, [rbp+57h+var_98.pszLexicalForm]
0x18005f44d  mov     rdx, [rbp+57h+var_98.pszDisplayText]
0x18005f451  mov     rcx, [rdi+108h]
0x18005f458  call    ?AddCompleteWord@CPPT@@QEAAJPEBG00KGW4PronType_t@IPPT@@PEAI_N@Z; CPPT::AddCompleteWord(ushort const *,ushort const *,ushort const *,ulong,ushort,IPPT::PronType_t,uint *,bool)
0x18005f45d  jmp     short loc_18005F47A
0x18005f45f  mov     rax, [rdi]
0x18005f462  lea     r9, [rsp+130h+var_E0]
0x18005f467  mov     r8d, r15d
0x18005f46a  lea     rdx, [rbp+57h+var_98]
0x18005f46e  mov     rcx, rdi
0x18005f471  mov     rax, [rax+8]
0x18005f475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f47a  test    eax, eax
0x18005f47c  jns     short loc_18005F487
0x18005f47e  or      edx, 0FFFFFFFFh
0x18005f481  mov     [rsp+130h+var_E0], edx
0x18005f485  jmp     short loc_18005F48B
0x18005f487  mov     edx, [rsp+130h+var_E0]; unsigned int
0x18005f48b  lea     r8, [rbp+57h+var_98]; struct SPWORDENTRY *
0x18005f48f  mov     rcx, rdi; this
  ... truncated ...
```
