# CBlbApplicationBackupAsync::PrepareTarget(ulong,CBlbVolumeBackupContext *,ushort *,CBlbImpersonationHelper *)

- ea: `0x14001218c`
- end: `0x14001271e`
- name: `?PrepareTarget@CBlbApplicationBackupAsync@@QEAAJKPEAVCBlbVolumeBackupContext@@PEAGPEAVCBlbImpersonationHelper@@@Z`
- size: `1426`
- prototype: `int(CBlbApplicationBackupAsync *__hidden this, unsigned int, struct CBlbVolumeBackupContext *, unsigned __int16 *, struct CBlbImpersonationHelper *)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, service_task`

## callers

- `0x140019fd0`

## callees

- `0x140005334`
- `0x140006ca8`
- `0x14000bb24`
- `0x14001218c`
- `0x140013008`
- `0x1400130fc`
- `0x14001358c`
- `0x140020bf0`
- `0x14002d79c`
- `0x14008863c`
- `0x1400889f0`
- `0x140088d0c`
- `0x14008bb44`
- `0x14008e8e8`
- `0x1400f007c`
- `0x1400f07dc`
- `0x14012365c`
- `0x140123a04`
- `0x140134d20`
- `0x140137010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1400122c5`
- `ole32!CoTaskMemFree` at `0x1400122dc`
- `ole32!CoTaskMemFree` at `0x14001248d`
- `ole32!CoTaskMemFree` at `0x140012670`
- `ole32!CoTaskMemFree` at `0x14001268a`
- `ole32!CoTaskMemFree` at `0x140012698`
- `ole32!CoTaskMemFree` at `0x1400126a8`
- `ole32!CoTaskMemFree` at `0x1400126bf`
- `ole32!CoTaskMemFree` at `0x1400122c5`
- `ole32!CoTaskMemFree` at `0x1400122dc`
- `ole32!CoTaskMemFree` at `0x14001248d`
- `ole32!CoTaskMemFree` at `0x140012670`
- `ole32!CoTaskMemFree` at `0x14001268a`
- `ole32!CoTaskMemFree` at `0x140012698`
- `ole32!CoTaskMemFree` at `0x1400126a8`
- `ole32!CoTaskMemFree` at `0x1400126bf`
- `RPCRT4!UuidToStringW` at `0x140012315`
- `RPCRT4!UuidToStringW` at `0x140012315`
- `RPCRT4!RpcStringFreeW` at `0x1400122f3`
- `RPCRT4!RpcStringFreeW` at `0x1400122f3`

## string_xrefs

- `0x140012285`: `base\stor\blb\engine\service\appbackup.cpp`
- `0x14001243c`: `base\stor\blb\engine\service\appbackup.cpp`
- `0x1400125b8`: `base\stor\blb\engine\service\appbackup.cpp`
- `0x1400125ac`: `pVolCtxt->m_wszMountedVhdPath == NULL`

## pseudocode

```c
__int64 __fastcall CBlbApplicationBackupAsync::PrepareTarget(
        CBlbApplicationBackupAsync *this,
        unsigned int a2,
        struct CBlbVolumeBackupContext *a3,
        unsigned __int16 *a4,
        struct CBlbImpersonationHelper *a5)
{
  struct CBlbVolumeBackupContext *v6; // r9
  unsigned int v7; // r8d
  PVOID *v9; // rcx
  unsigned int v10; // eax
  int appended; // edi
  WCHAR *v12; // rsi
  unsigned __int16 *v13; // r12
  unsigned __int16 *v14; // r13
  __int64 i; // rbx
  __int64 v16; // r15
  bool v17; // bl
  __int64 v18; // r9
  char *v19; // rdx
  unsigned int v20; // r8d
  char *v21; // r10
  unsigned __int64 v22; // rcx
  const unsigned __int16 *v23; // rcx
  unsigned __int16 **p_pv; // rdx
  char v25; // bl
  __int64 v26; // rcx
  int v27; // eax
  unsigned int j; // edx
  __int64 v29; // r9
  char *v30; // r8
  unsigned __int64 v31; // rcx
  unsigned __int16 **v32; // rbx
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v35; // [rsp+48h] [rbp-B8h]
  unsigned int v36; // [rsp+4Ch] [rbp-B4h] BYREF
  int v37; // [rsp+50h] [rbp-B0h]
  RPC_WSTR String; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v39; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v40; // [rsp+68h] [rbp-98h] BYREF
  PCWSTR v41; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v42; // [rsp+78h] [rbp-88h] BYREF
  struct CBlbVolumeBackupContext *v43; // [rsp+80h] [rbp-80h]
  CBlbImpersonationHelper *v44; // [rsp+88h] [rbp-78h]
  unsigned __int64 v45; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v46[264]; // [rsp+A0h] [rbp-60h] BYREF

  v6 = a3;
  v43 = a3;
  v7 = a2;
  v44 = a5;
  v35 = a2;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_7d2043e956a53eb416ccda4830c6c098_Traceguids);
    v9 = (PVOID *)WPP_GLOBAL_Control;
    v7 = v35;
    v6 = v43;
  }
  v10 = *((_DWORD *)this + 72) - 4;
  v42 = 0;
  v41 = 0;
  appended = 0;
  pv = 0;
  v12 = 0;
  v39 = 0;
  v13 = 0;
  String = 0;
  v14 = 0;
  v45 = 0;
  v40 = 0;
  if ( v10 > 1 )
  {
    if ( (v7 == 0) != (v6 == 0) )
      BlbAssert(
        "base\\stor\\blb\\engine\\service\\appbackup.cpp",
        0x51Au,
        "(cVolumesInBackup == 0) == (rgVolumesInBackup == NULL)");
    appended = BlbutilSlashTerminatePath(a4, (LPVOID *)&v42);
    if ( appended >= 0 )
    {
      for ( i = 0; ; i = (unsigned int)(v37 + 1) )
      {
        v37 = i;
        if ( (unsigned int)i >= *((_DWORD *)this + 55) )
        {
LABEL_63:
          if ( v13 )
            CoTaskMemFree(v13);
          break;
        }
        if ( v12 )
        {
          CoTaskMemFree(v12);
          v12 = 0;
          v41 = 0;
        }
        if ( pv )
        {
          CoTaskMemFree(pv);
          pv = 0;
        }
        if ( String )
        {
          RpcStringFreeW(&String);
          String = 0;
        }
        v16 = 96 * i;
        if ( UuidToStringW((const UUID *)(96 * i + *((_QWORD *)this + 28)), &String) )
        {
          appended = -2147024882;
          goto LABEL_63;
        }
        appended = StringCchPrintfW(v46, 0x104u, L"%s.vhdx", String);
        if ( appended < 0 )
          goto LABEL_63;
        appended = BlbutilAppendString(v42, v46, (unsigned __int16 **)&v41);
        if ( appended < 0 || (appended = CBlbImpersonationHelper::ImpersonateCaller(v44, 0), appended < 0) )
        {
          v12 = (WCHAR *)v41;
          goto LABEL_63;
        }
        v12 = (WCHAR *)v41;
        v17 = FileExists((unsigned __int16 *)v41);
        CBlbImpersonationHelper::Revert(v44);
        v18 = *((_QWORD *)this + 28);
        if ( !v17 )
        {
          appended = BlbutilQueryVolumeSpace(*(unsigned __int16 **)(v16 + v18 + 16), &v45);
          if ( appended < 0 )
            goto LABEL_63;
          if ( v13 )
          {
            CoTaskMemFree(v13);
            v39 = 0;
          }
          appended = BlbQueryVolumeLabel(*(unsigned __int16 **)(v16 + *((_QWORD *)this + 28) + 16), &v39);
          if ( appended < 0
            || (v26 = *((_QWORD *)this + 28),
                v36 = 0,
                appended = BlbQueryVolumeSectorSize(*(unsigned __int16 **)(v16 + v26 + 16), &v36),
                appended < 0) )
          {
            v13 = v39;
            goto LABEL_63;
          }
          v27 = BlbQueryVolumeFileSystem(*(unsigned __int16 **)(v16 + *((_QWORD *)this + 28) + 16), &v40);
          v14 = v40;
          appended = v27;
          v13 = v39;
          if ( v27 < 0 )
            goto LABEL_63;
          appended = CBlbBackupAsync::CreateVHD(
                       *((CBlbBackupAsync **)this + 30),
                       v12,
                       v45,
                       v39,
                       0,
                       v36,
                       v40,
                       (unsigned __int16 **)&pv);
          if ( appended < 0 )
          {
            CBlbApplicationBackupAsync::SetState(this, 5);
            (*(void (__fastcall **)(CBlbApplicationBackupAsync *, __int64, _QWORD))(*(_QWORD *)this + 64LL))(
              this,
              2155348165LL,
              (unsigned int)appended);
            CBlbAsync::SetResult((CBlbAsync *)(*((_QWORD *)this + 30) + 24LL), -2139619131, appended, 0);
            goto LABEL_63;
          }
          v25 = 1;
          for ( j = 0; j < v35; ++j )
          {
            v29 = *((_QWORD *)this + 28);
            v30 = (char *)v43 + 368 * j;
            v31 = *(_QWORD *)(v16 + v29) - *(_QWORD *)(v30 + 68);
            if ( !v31 )
              v31 = *(_QWORD *)(v16 + v29 + 8) - _mm_srli_si128(*(__m128i *)(v30 + 68), 8).m128i_u64[0];
            if ( !v31 )
            {
              if ( !v30 )
                goto LABEL_56;
              v32 = (unsigned __int16 **)(v30 + 224);
              if ( *((_QWORD *)v30 + 28) )
                BlbAssert(
                  "base\\stor\\blb\\engine\\service\\appbackup.cpp",
                  0x5BAu,
                  "pVolCtxt->m_wszMountedVhdPath == NULL");
              v23 = (const unsigned __int16 *)pv;
              p_pv = v32;
              goto LABEL_54;
            }
          }
          goto LABEL_56;
        }
        if ( *(_QWORD *)(v16 + v18 + 80) )
          continue;
        v19 = 0;
        v20 = 0;
        if ( v35 )
        {
          do
          {
            v21 = (char *)v43 + 368 * v20;
            v22 = *(_QWORD *)(v16 + v18) - *(_QWORD *)(v21 + 68);
            if ( !v22 )
              v22 = *(_QWORD *)(v16 + v18 + 8) - _mm_srli_si128(*(__m128i *)(v21 + 68), 8).m128i_u64[0];
            if ( !v22 )
              v19 = (char *)v43 + 368 * v20;
            ++v20;
          }
          while ( v20 < v35 );
          v14 = v40;
          if ( v19 )
          {
            v23 = (const unsigned __int16 *)*((_QWORD *)v19 + 28);
            if ( v23 )
            {
              p_pv = (unsigned __int16 **)&pv;
LABEL_54:
              appended = BlbutilDuplicateString(v23, p_pv, 0);
              if ( appended < 0 )
                goto LABEL_63;
              v25 = 0;
              goto LABEL_56;
            }
            if ( (v19[84] & 8) == 0 && (v19[84] & 0x10) == 0 )
              BlbAssert(
                "base\\stor\\blb\\engine\\service\\appbackup.cpp",
                0x56Cu,
                "pVolCtxt == NULL || VOLUME_IS_BLOCKLEVEL(pVolCtxt->m_dwVolumeFlags) || VOLUME_IS_INCREMENTAL(pVolCtxt->m_dwVolumeFlags)");
          }
        }
        appended = CBlbBackupAsync::MountVHD(*((CBlbBackupAsync **)this + 30), v12, (unsigned __int16 **)&pv);
        if ( appended < 0 )
          goto LABEL_63;
        v25 = 1;
LABEL_56:
        appended = BlbutilSlashTerminatePath((unsigned __int16 *)pv, (LPVOID *)(v16 + *((_QWORD *)this + 28) + 80LL));
        if ( appended < 0 )
          goto LABEL_63;
        *(_BYTE *)(v16 + *((_QWORD *)this + 28) + 44) = v25;
      }
    }
    if ( v42 )
      CoTaskMemFree(v42);
    if ( v12 )
      CoTaskMemFree(v12);
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    if ( v14 )
      CoTaskMemFree(v14);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 && *((_BYTE *)v9 + 25) >= 4u )
    WPP_SF_(v9[2], 55, WPP_7d2043e956a53eb416ccda4830c6c098_Traceguids);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x14001218c  mov     [rsp-8+arg_8], rbx
0x140012191  push    rbp
0x140012192  push    rsi
0x140012193  push    rdi
0x140012194  push    r12
0x140012196  push    r13
0x140012198  push    r14
0x14001219a  push    r15
0x14001219c  lea     rbp, [rsp-1C0h]
0x1400121a4  sub     rsp, 2C0h
0x1400121ab  mov     rax, cs:__security_cookie
0x1400121b2  xor     rax, rsp
0x1400121b5  mov     [rbp+1F0h+var_40], rax
0x1400121bc  mov     rax, [rbp+1F0h+arg_20]
0x1400121c3  mov     rbx, r9
0x1400121c6  mov     r9, r8
0x1400121c9  mov     [rbp+1F0h+var_270], r8
0x1400121cd  mov     r8d, edx
0x1400121d0  mov     [rbp+1F0h+var_268], rax
0x1400121d4  mov     [rsp+2F0h+var_2A8], edx
0x1400121d8  mov     r14, rcx
0x1400121db  mov     rcx, cs:WPP_GLOBAL_Control
0x1400121e2  lea     r15, WPP_GLOBAL_Control
0x1400121e9  cmp     rcx, r15
0x1400121ec  jz      short loc_14001221F
0x1400121ee  test    byte ptr [rcx+1Ch], 1
0x1400121f2  jz      short loc_14001221F
0x1400121f4  cmp     byte ptr [rcx+19h], 4
0x1400121f8  jb      short loc_14001221F
0x1400121fa  mov     rcx, [rcx+10h]
0x1400121fe  lea     r8, WPP_7d2043e956a53eb416ccda4830c6c098_Traceguids
0x140012205  mov     edx, 36h ; '6'
0x14001220a  call    WPP_SF_
0x14001220f  mov     rcx, cs:WPP_GLOBAL_Control
0x140012216  mov     r8d, [rsp+2F0h+var_2A8]
0x14001221b  mov     r9, [rbp+1F0h+var_270]
0x14001221f  mov     eax, [r14+120h]
0x140012226  xor     r10d, r10d
0x140012229  sub     eax, 4
0x14001222c  mov     [rsp+2F0h+var_278], r10
0x140012231  mov     [rsp+2F0h+var_280], r10
0x140012236  mov     edi, r10d
0x140012239  mov     [rsp+2F0h+pv], r10
0x14001223e  mov     esi, r10d
0x140012241  mov     [rsp+2F0h+var_290], r10
0x140012246  mov     r12d, r10d
0x140012249  mov     [rsp+2F0h+String], r10
0x14001224e  mov     r13d, r10d
0x140012251  mov     [rbp+1F0h+var_260], r10
0x140012255  mov     [rsp+2F0h+var_288], r10
0x14001225a  cmp     eax, 1
0x14001225d  jbe     loc_1400126CC
0x140012263  test    r9, r9
0x140012266  mov     edx, r10d
0x140012269  mov     eax, r10d
0x14001226c  setz    dl
0x14001226f  test    r8d, r8d
0x140012272  setz    al
0x140012275  cmp     eax, edx
0x140012277  jz      short loc_140012291
0x140012279  lea     r8, aCvolumesinback; "(cVolumesInBackup == 0) == (rgVolumesIn"...
0x140012280  mov     edx, 51Ah; unsigned int
0x140012285  lea     rcx, aBaseStorBlbEng_47; "base\\stor\\blb\\engine\\service\\appba"...
0x14001228c  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140012291  lea     rdx, [rsp+2F0h+var_278]; unsigned __int16 **
0x140012296  mov     rcx, rbx; unsigned __int16 *
0x140012299  call    ?BlbutilSlashTerminatePath@@YAJPEAGPEAPEAG@Z; BlbutilSlashTerminatePath(ushort *,ushort * *)
0x14001229e  mov     edi, eax
0x1400122a0  test    eax, eax
0x1400122a2  js      loc_14001267D
0x1400122a8  xor     ebx, ebx
0x1400122aa  mov     [rsp+2F0h+var_2A0], ebx
0x1400122ae  cmp     ebx, [r14+0DCh]
0x1400122b5  jnb     loc_140012668
0x1400122bb  xor     edi, edi
0x1400122bd  test    rsi, rsi
0x1400122c0  jz      short loc_1400122D2
0x1400122c2  mov     rcx, rsi; pv
0x1400122c5  call    cs:__imp_CoTaskMemFree
0x1400122cb  mov     esi, edi
0x1400122cd  mov     [rsp+2F0h+var_280], rdi
0x1400122d2  mov     rcx, [rsp+2F0h+pv]; pv
0x1400122d7  test    rcx, rcx
0x1400122da  jz      short loc_1400122E7
0x1400122dc  call    cs:__imp_CoTaskMemFree
0x1400122e2  mov     [rsp+2F0h+pv], rdi
0x1400122e7  cmp     [rsp+2F0h+String], rdi
0x1400122ec  jz      short loc_1400122FE
0x1400122ee  lea     rcx, [rsp+2F0h+String]; String
0x1400122f3  call    cs:__imp_RpcStringFreeW
0x1400122f9  mov     [rsp+2F0h+String], rdi
0x1400122fe  mov     rcx, [r14+0E0h]
0x140012305  lea     r15, [rbx+rbx*2]
0x140012309  shl     r15, 5
0x14001230d  lea     rdx, [rsp+2F0h+String]; StringUuid
0x140012312  add     rcx, r15; Uuid
0x140012315  call    cs:__imp_UuidToStringW
0x14001231b  test    eax, eax
0x14001231d  jnz     loc_140012663
0x140012323  mov     r9, [rsp+2F0h+String]
0x140012328  lea     r8, aSVhdx; "%s.vhdx"
0x14001232f  mov     edx, 104h; unsigned __int64
0x140012334  lea     rcx, [rbp+1F0h+var_250]; unsigned __int16 *
0x140012338  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14001233d  mov     edi, eax
0x14001233f  test    eax, eax
0x140012341  js      loc_140012668
0x140012347  mov     rcx, [rsp+2F0h+var_278]; unsigned __int16 *
0x14001234c  lea     r8, [rsp+2F0h+var_280]; unsigned __int16 **
0x140012351  lea     rdx, [rbp+1F0h+var_250]; unsigned __int16 *
0x140012355  call    ?BlbutilAppendString@@YAJPEBG0PEAPEAG@Z; BlbutilAppendString(ushort const *,ushort const *,ushort * *)
0x14001235a  mov     edi, eax
0x14001235c  test    eax, eax
0x14001235e  js      loc_14001265C
0x140012364  mov     rcx, [rbp+1F0h+var_268]; this
0x140012368  xor     edx, edx; unsigned __int8
0x14001236a  call    ?ImpersonateCaller@CBlbImpersonationHelper@@QEAAJE@Z; CBlbImpersonationHelper::ImpersonateCaller(uchar)
0x14001236f  mov     edi, eax
0x140012371  test    eax, eax
0x140012373  js      loc_14001265C
0x140012379  mov     rsi, [rsp+2F0h+var_280]
0x14001237e  mov     rcx, rsi; unsigned __int16 *
0x140012381  call    ?FileExists@@YA_NPEAG@Z; FileExists(ushort *)
0x140012386  mov     rcx, [rbp+1F0h+var_268]; this
0x14001238a  mov     bl, al
0x14001238c  call    ?Revert@CBlbImpersonationHelper@@QEAAXXZ; CBlbImpersonationHelper::Revert(void)
0x140012391  mov     r9, [r14+0E0h]
0x140012398  test    bl, bl
0x14001239a  jz      loc_14001246D
0x1400123a0  cmp     qword ptr [r15+r9+50h], 0
0x1400123a6  jnz     loc_14001260A
0x1400123ac  mov     r11d, [rsp+2F0h+var_2A8]
0x1400123b1  xor     edx, edx
0x1400123b3  xor     r8d, r8d
0x1400123b6  test    r11d, r11d
0x1400123b9  jz      loc_140012448
0x1400123bf  mov     r13, [rbp+1F0h+var_270]
0x1400123c3  mov     rcx, [r15+r9]
0x1400123c7  mov     eax, r8d
0x1400123ca  imul    r10, rax, 170h
0x1400123d1  add     r10, r13
0x1400123d4  movups  xmm0, xmmword ptr [r10+44h]
0x1400123d9  movq    rax, xmm0
0x1400123de  sub     rcx, rax
0x1400123e1  jnz     short loc_1400123F5
0x1400123e3  mov     rcx, [r15+r9+8]
0x1400123e8  psrldq  xmm0, 8
0x1400123ed  movq    rax, xmm0
0x1400123f2  sub     rcx, rax
0x1400123f5  test    rcx, rcx
0x1400123f8  cmovz   rdx, r10
0x1400123fc  inc     r8d
0x1400123ff  cmp     r8d, r11d
0x140012402  jb      short loc_1400123C3
0x140012404  mov     r13, [rsp+2F0h+var_288]
0x140012409  test    rdx, rdx
0x14001240c  jz      short loc_140012448
0x14001240e  mov     rcx, [rdx+0E0h]
0x140012415  test    rcx, rcx
0x140012418  jz      short loc_140012424
0x14001241a  lea     rdx, [rsp+2F0h+pv]
0x14001241f  jmp     loc_1400125CC
0x140012424  test    byte ptr [rdx+54h], 8
0x140012428  jnz     short loc_140012448
0x14001242a  test    byte ptr [rdx+54h], 10h
0x14001242e  jnz     short loc_140012448
0x140012430  lea     r8, aPvolctxtNullVo; "pVolCtxt == NULL || VOLUME_IS_BLOCKLEVE"...
0x140012437  mov     edx, 56Ch; unsigned int
0x14001243c  lea     rcx, aBaseStorBlbEng_47; "base\\stor\\blb\\engine\\service\\appba"...
0x140012443  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140012448  mov     rcx, [r14+0F0h]; this
0x14001244f  lea     r8, [rsp+2F0h+pv]; unsigned __int16 **
0x140012454  mov     rdx, rsi; PCWSTR
0x140012457  call    ?MountVHD@CBlbBackupAsync@@QEAAJPEBGPEAPEAG@Z; CBlbBackupAsync::MountVHD(ushort const *,ushort * *)
0x14001245c  mov     edi, eax
0x14001245e  test    eax, eax
0x140012460  js      loc_140012668
0x140012466  mov     bl, 1
0x140012468  jmp     loc_1400125E0
0x14001246d  mov     rcx, [r15+r9+10h]; unsigned __int16 *
0x140012472  lea     rdx, [rbp+1F0h+var_260]; unsigned __int64 *
0x140012476  call    ?BlbutilQueryVolumeSpace@@YAJPEAGPEA_K@Z; BlbutilQueryVolumeSpace(ushort *,unsigned __int64 *)
0x14001247b  mov     edi, eax
0x14001247d  test    eax, eax
0x14001247f  js      loc_140012668
0x140012485  test    r12, r12
0x140012488  jz      short loc_14001249C
0x14001248a  mov     rcx, r12; pv
0x14001248d  call    cs:__imp_CoTaskMemFree
0x140012493  mov     [rsp+2F0h+var_290], 0
0x14001249c  mov     rcx, [r14+0E0h]
0x1400124a3  lea     rdx, [rsp+2F0h+var_290]; unsigned __int16 **
0x1400124a8  mov     rcx, [r15+rcx+10h]; unsigned __int16 *
0x1400124ad  call    ?BlbQueryVolumeLabel@@YAJPEAGPEAPEAG@Z; BlbQueryVolumeLabel(ushort *,ushort * *)
0x1400124b2  mov     edi, eax
0x1400124b4  test    eax, eax
0x1400124b6  js      loc_140012655
0x1400124bc  mov     rcx, [r14+0E0h]
0x1400124c3  lea     rdx, [rsp+2F0h+var_2A4]; unsigned int *
0x1400124c8  mov     [rsp+2F0h+var_2A4], 0
0x1400124d0  mov     rcx, [r15+rcx+10h]; unsigned __int16 *
0x1400124d5  call    ?BlbQueryVolumeSectorSize@@YAJPEAGPEAK@Z; BlbQueryVolumeSectorSize(ushort *,ulong *)
0x1400124da  mov     edi, eax
0x1400124dc  test    eax, eax
0x1400124de  js      loc_140012655
0x1400124e4  mov     rcx, [r14+0E0h]
0x1400124eb  lea     rdx, [rsp+2F0h+var_288]; unsigned __int16 **
0x1400124f0  mov     rcx, [r15+rcx+10h]; unsigned __int16 *
0x1400124f5  call    ?BlbQueryVolumeFileSystem@@YAJPEAGPEAPEAG@Z; BlbQueryVolumeFileSystem(ushort *,ushort * *)
0x1400124fa  mov     r13, [rsp+2F0h+var_288]
0x1400124ff  mov     edi, eax
0x140012501  mov     r12, [rsp+2F0h+var_290]
0x140012506  test    eax, eax
0x140012508  js      loc_140012668
0x14001250e  mov     r8, [rbp+1F0h+var_260]; unsigned __int64
0x140012512  lea     rax, [rsp+2F0h+pv]
0x140012517  mov     rcx, [r14+0F0h]; this
0x14001251e  mov     r9, r12; unsigned __int16 *
0x140012521  mov     [rsp+2F0h+var_2B8], rax; unsigned __int16 **
0x140012526  mov     rdx, rsi; unsigned __int16 *
0x140012529  mov     eax, [rsp+2F0h+var_2A4]
0x14001252d  mov     [rsp+2F0h+var_2C0], r13; unsigned __int16 *
0x140012532  mov     [rsp+2F0h+var_2C8], eax; unsigned int
0x140012536  mov     [rsp+2F0h+var_2D0], 0; unsigned __int8
0x14001253b  call    ?CreateVHD@CBlbBackupAsync@@QEAAJPEAG_K0EK0PEAPEAG@Z; CBlbBackupAsync::CreateVHD(ushort *,unsigned __int64,ushort *,uchar,ulong,ushort *,ushort * *)
0x140012540  mov     edi, eax
0x140012542  test    eax, eax
0x140012544  js      loc_140012615
0x14001254a  mov     bl, 1
0x14001254c  xor     edx, edx
0x14001254e  cmp     edx, [rsp+2F0h+var_2A8]
0x140012552  jnb     loc_1400125E0
0x140012558  mov     r9, [r14+0E0h]
0x14001255f  mov     eax, edx
0x140012561  imul    r8, rax, 170h
0x140012568  mov     rcx, [r15+r9]
0x14001256c  add     r8, [rbp+1F0h+var_270]
0x140012570  movups  xmm0, xmmword ptr [r8+44h]
0x140012575  movq    rax, xmm0
0x14001257a  sub     rcx, rax
0x14001257d  jnz     short loc_140012591
0x14001257f  mov     rcx, [r15+r9+8]
0x140012584  psrldq  xmm0, 8
0x140012589  movq    rax, xmm0
0x14001258e  sub     rcx, rax
0x140012591  test    rcx, rcx
0x140012594  jz      short loc_14001259A
0x140012596  inc     edx
0x140012598  jmp     short loc_14001254E
0x14001259a  test    r8, r8
0x14001259d  jz      short loc_1400125E0
0x14001259f  lea     rbx, [r8+0E0h]
0x1400125a6  cmp     qword ptr [rbx], 0
0x1400125aa  jz      short loc_1400125C4
0x1400125ac  lea     r8, aPvolctxtMWszmo; "pVolCtxt->m_wszMountedVhdPath == NULL"
0x1400125b3  mov     edx, 5BAh; unsigned int
0x1400125b8  lea     rcx, aBaseStorBlbEng_47; "base\\stor\\blb\\engine\\service\\appba"...
0x1400125bf  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400125c4  mov     rcx, [rsp+2F0h+pv]; unsigned __int16 *
0x1400125c9  mov     rdx, rbx; unsigned __int16 **
0x1400125cc  xor     r8d, r8d; unsigned __int64
0x1400125cf  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x1400125d4  mov     edi, eax
0x1400125d6  test    eax, eax
0x1400125d8  js      loc_140012668
0x1400125de  xor     bl, bl
0x1400125e0  mov     rdx, [r14+0E0h]
0x1400125e7  mov     rcx, [rsp+2F0h+pv]; unsigned __int16 *
0x1400125ec  add     rdx, 50h ; 'P'
0x1400125f0  add     rdx, r15; unsigned __int16 **
0x1400125f3  call    ?BlbutilSlashTerminatePath@@YAJPEAGPEAPEAG@Z; BlbutilSlashTerminatePath(ushort *,ushort * *)
0x1400125f8  mov     edi, eax
0x1400125fa  test    eax, eax
0x1400125fc  js      short loc_140012668
0x1400125fe  mov     rax, [r14+0E0h]
0x140012605  mov     [r15+rax+2Ch], bl
0x14001260a  mov     ebx, [rsp+2F0h+var_2A0]
0x14001260e  inc     ebx
0x140012610  jmp     loc_1400122AA
0x140012615  mov     edx, 5
0x14001261a  mov     rcx, r14
0x14001261d  call    ?SetState@CBlbApplicationBackupAsync@@QEAAXW4BLB_APPLICATION_BACKUP_STATE@@@Z; CBlbApplicationBackupAsync::SetState(BLB_APPLICATION_BACKUP_STATE)
0x140012622  mov     rax, [r14]
0x140012625  mov     ebx, 807800C5h
0x14001262a  mov     r8d, edi
0x14001262d  mov     edx, ebx
0x14001262f  mov     rcx, r14
0x140012632  mov     rax, [rax+40h]
0x140012636  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001263b  mov     rcx, [r14+0F0h]
0x140012642  xor     r9d, r9d; unsigned __int8
0x140012645  add     rcx, 18h; this
0x140012649  mov     r8d, edi; int
0x14001264c  mov     edx, ebx; int
0x14001264e  call    ?SetResult@CBlbAsync@@QEAAXJJE@Z; CBlbAsync::SetResult(long,long,uchar)
0x140012653  jmp     short loc_140012668
0x140012655  mov     r12, [rsp+2F0h+var_290]
0x14001265a  jmp     short loc_140012668
0x14001265c  mov     rsi, [rsp+2F0h+var_280]
0x140012661  jmp     short loc_140012668
  ... truncated ...
```
