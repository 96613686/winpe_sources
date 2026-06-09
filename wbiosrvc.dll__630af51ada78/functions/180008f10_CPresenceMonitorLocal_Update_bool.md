# CPresenceMonitorLocal::Update(bool *)

- ea: `0x180008f10`
- end: `0x180009772`
- name: `?Update@CPresenceMonitorLocal@@UEAAJPEA_N@Z`
- size: `2146`
- prototype: `__int64 __fastcall(CPresenceMonitorLocal *__hidden this, bool *)`
- caller_count: `0`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180008d40`
- `0x180008f10`
- `0x180009778`
- `0x1800097d4`
- `0x180009ab0`
- `0x180009ac4`
- `0x18000b760`
- `0x180031540`
- `0x180033dbc`
- `0x180057618`
- `0x1800591d4`
- `0x18005e7e0`
- `0x180068f60`
- `0x18006963c`
- `0x180069cc8`
- `0x1800973fc`
- `0x180097688`
- `0x1800d2010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180009066`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180009066`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180009316`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180009316`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800095e2`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800095e2`

## string_xrefs

- `0x180008f5f`: `CPresenceMonitorLocal::Update`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CPresenceMonitorLocal::Update(CPresenceMonitorLocal *this, bool *a2)
{
  CPresenceMonitorLocal *v2; // r14
  std::_Ref_count_base *v3; // rcx
  __int64 v4; // rax
  std::_Ref_count_base *v5; // r15
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 (__fastcall *v8)(__int64, unsigned __int64 *, __int64 *); // rax
  int v9; // ebx
  char *v10; // r12
  __int64 v11; // rax
  char *v12; // r13
  __int64 v13; // rax
  __int64 v14; // rax
  int v15; // ecx
  __int64 v16; // rax
  unsigned int i; // edi
  char *v18; // rbx
  char *v19; // rdi
  _QWORD *v21; // rdi
  _QWORD *j; // rbx
  _QWORD *v23; // rdi
  _QWORD *v24; // rbx
  _QWORD *v25; // r13
  __int64 ***v26; // r12
  _QWORD *v27; // rdi
  _QWORD *v28; // rbx
  char *v29; // r13
  _QWORD *v30; // r14
  __int64 **v31; // rdi
  __int64 *v32; // rbx
  CPresenceMonitorLocal *v33; // r14
  char *v34; // r15
  _QWORD *v35; // r13
  __int64 **v36; // rdi
  __int64 *v37; // rbx
  _QWORD *v38; // r14
  __int64 v39; // r8
  _BYTE *v40; // r8
  __int64 v41; // r13
  __int64 v42; // r8
  __int64 v43; // rbx
  _DWORD *v44; // r13
  __int64 v45; // rbx
  __int64 v46; // rcx
  __int64 v47; // rax
  CPresence *v48; // rcx
  std::_Ref_count_base *v49; // rdx
  std::_Ref_count_base *v50; // rcx
  __int64 v51; // r13
  _QWORD *v52; // rax
  __int64 v53; // rcx
  _QWORD *v54; // rcx
  _QWORD *v55; // r9
  __int64 v56; // rax
  int v57; // ecx
  __int64 v58; // [rsp+20h] [rbp-168h] BYREF
  __int64 v59; // [rsp+28h] [rbp-160h] BYREF
  std::_Ref_count_base *v60; // [rsp+30h] [rbp-158h]
  __int64 v61; // [rsp+38h] [rbp-150h] BYREF
  char *v62; // [rsp+40h] [rbp-148h]
  char *v63; // [rsp+48h] [rbp-140h]
  char *v64; // [rsp+50h] [rbp-138h]
  CPresence *v65; // [rsp+58h] [rbp-130h] BYREF
  std::_Ref_count_base *v66; // [rsp+60h] [rbp-128h]
  __int64 v67; // [rsp+68h] [rbp-120h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+70h] [rbp-118h] BYREF
  CPresenceMonitorLocal *v69; // [rsp+78h] [rbp-110h]
  _QWORD *v70; // [rsp+80h] [rbp-108h] BYREF
  char *v71; // [rsp+88h] [rbp-100h]
  char *v72; // [rsp+90h] [rbp-F8h]
  char *v73; // [rsp+98h] [rbp-F0h]
  char *v74; // [rsp+A0h] [rbp-E8h]
  __int128 v75; // [rsp+A8h] [rbp-E0h]
  unsigned __int64 v76; // [rsp+B8h] [rbp-D0h] BYREF
  CPresenceMonitorLocal *v77; // [rsp+C0h] [rbp-C8h]
  _QWORD *v78; // [rsp+C8h] [rbp-C0h]
  _QWORD *v79; // [rsp+D0h] [rbp-B8h]
  _QWORD *v80; // [rsp+D8h] [rbp-B0h]
  _QWORD *v81; // [rsp+E0h] [rbp-A8h]
  bool *v82; // [rsp+E8h] [rbp-A0h]
  _QWORD v83[4]; // [rsp+F0h] [rbp-98h] BYREF
  __int64 v84; // [rsp+110h] [rbp-78h]
  char v85[8]; // [rsp+120h] [rbp-68h] BYREF
  std::_Ref_count_base *v86; // [rsp+128h] [rbp-60h]
  char v87[32]; // [rsp+130h] [rbp-58h] BYREF

  v2 = this;
  v69 = this;
  v77 = this;
  v82 = a2;
  LODWORD(v58) = 0;
  HIDWORD(v59) = 0;
  strcpy(v87, "CPresenceMonitorLocal::Update");
  v83[0] = v87;
  v83[1] = (char *)&v59 + 4;
  v83[2] = &v58;
  lambda_526c18d49885b27cb39b2b27f84d5be0_::operator()(v83);
  HIDWORD(v59) = 1;
  v70 = v83;
  v75 = 0;
  v3 = (std::_Ref_count_base *)*((_QWORD *)v2 + 2);
  if ( v3 && std::_Ref_count_base::_Incref_nz(v3) )
  {
    v4 = *((_QWORD *)v2 + 1);
    *(_QWORD *)&v75 = v4;
    v5 = (std::_Ref_count_base *)*((_QWORD *)v2 + 2);
    *((_QWORD *)&v75 + 1) = v5;
  }
  else
  {
    v5 = (std::_Ref_count_base *)*((_QWORD *)&v75 + 1);
    v4 = v75;
  }
  v60 = v5;
  v6 = *(_QWORD *)(v4 + 2704) + 16LL;
  if ( *(_QWORD *)(v4 + 2704) == -16 || (v61 = 0, v76 = 0, (v7 = *(_QWORD *)(v6 + 32)) == 0) )
  {
    v9 = -2147467261;
    goto LABEL_39;
  }
  v8 = *(__int64 (__fastcall **)(__int64, unsigned __int64 *, __int64 *))(v7 + 256);
  if ( !v8 )
  {
    v9 = -2147467263;
LABEL_39:
    LODWORD(v58) = v9;
    goto LABEL_21;
  }
  v9 = v8(v6, &v76, &v61);
  LODWORD(v58) = v9;
  if ( v9 >= 0 )
  {
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v10 = (char *)v2 + 48;
    v71 = (char *)v2 + 48;
    v78 = (_QWORD *)((char *)v2 + 56);
    v11 = *((_QWORD *)v2 + 6);
    if ( v11 != *((_QWORD *)v2 + 7) )
      *((_QWORD *)v2 + 7) = v11;
    v12 = (char *)v2 + 72;
    v62 = (char *)v2 + 72;
    v72 = (char *)v2 + 72;
    v79 = (_QWORD *)((char *)v2 + 80);
    v13 = *((_QWORD *)v2 + 9);
    if ( v13 != *((_QWORD *)v2 + 10) )
      *((_QWORD *)v2 + 10) = v13;
    v63 = (char *)v2 + 96;
    v73 = (char *)v2 + 96;
    v80 = (_QWORD *)((char *)v2 + 104);
    v14 = *((_QWORD *)v2 + 12);
    if ( v14 != *((_QWORD *)v2 + 13) )
      *((_QWORD *)v2 + 13) = v14;
    v15 = (_DWORD)v2 + 120;
    v64 = (char *)v2 + 120;
    v74 = (char *)v2 + 120;
    v81 = (_QWORD *)((char *)v2 + 128);
    v16 = *((_QWORD *)v2 + 15);
    if ( v16 != *((_QWORD *)v2 + 16) )
      *((_QWORD *)v2 + 16) = v16;
    for ( i = 0; ; ++i )
    {
      LODWORD(v59) = i;
      if ( i >= v76 )
        break;
      v43 = 496LL * i;
      v67 = v43;
      CPresenceMonitorLocal::FindByTrackingId(v2, &v65, *(_QWORD *)(v43 + v61 + 96));
      if ( !v65 )
      {
        try
        {
          v44 = operator new(0x210u);
          v45 = v61;
          v44[126] = *((_DWORD *)v2 + 6);
          *(_QWORD *)(v44 + 127) = 0;
          v44[129] = 0;
          *((_WORD *)v44 + 260) = 0;
          *((_BYTE *)v44 + 522) = 0;
          memset_0(v44, 0, 0x1F0u);
          v46 = v67;
          *v44 = *(_DWORD *)(v67 + v45);
          *((_BYTE *)v44 + 4) = *(_BYTE *)(v46 + v45 + 4);
          *((_QWORD *)v44 + 12) = *(_QWORD *)(v46 + v45 + 96);
          *((_QWORD *)v44 + 62) = 0;
          v47 = std::shared_ptr<CPresence>::shared_ptr<CPresence>(v85, v44);
          v48 = *(CPresence **)v47;
          v49 = *(std::_Ref_count_base **)(v47 + 8);
          *(_QWORD *)v47 = 0;
          *(_QWORD *)(v47 + 8) = 0;
          v65 = v48;
          v50 = v66;
          v66 = v49;
          if ( v50 )
            std::_Ref_count_base::_Decref(v50);
          if ( v86 )
            std::_Ref_count_base::_Decref(v86);
          if ( *((_QWORD *)v2 + 5) == 0x7FFFFFFFFFFFFFFLL )
            std::_Xlength_error("list too long");
          v51 = *((_QWORD *)v2 + 4);
          v83[3] = (char *)v2 + 32;
          v84 = 0;
          v52 = std::_Allocate<16,std::_Default_allocate_traits>(0x20u);
          std::_Default_allocator_traits<std::allocator<std::_List_node<std::shared_ptr<CPresenceChangeItem>,void *>>>::construct<std::shared_ptr<CPresenceChangeItem>,std::shared_ptr<CPresenceChangeItem> const &>(
            v53,
            v52 + 2,
            &v65,
            v52,
            v58,
            v59);
          ++*((_QWORD *)v2 + 5);
          v54 = *(_QWORD **)(v51 + 8);
          *v55 = v51;
          v55[1] = v54;
          v84 = 0;
          *(_QWORD *)(v51 + 8) = v55;
          *v54 = v55;
          v12 = v62;
        }
        catch ( std::bad_alloc )
        {
          LODWORD(v58) = -2147024882;
          v5 = (std::_Ref_count_base *)*((_QWORD *)&v75 + 1);
          v60 = (std::_Ref_count_base *)*((_QWORD *)&v75 + 1);
          i = v59;
          v2 = v77;
          v69 = v77;
          v10 = v71;
          v12 = v72;
          v62 = v72;
          v63 = v73;
          v64 = v74;
        }
        v43 = v67;
      }
      if ( (int)v58 < 0
        || (LODWORD(v58) = CPresence::ReportObservation(
                             v65,
                             (struct _WINBIO_PRESENCE *)(v43 + v61),
                             &SystemTimeAsFileTime),
            (int)v58 < 0) )
      {
        v15 = (int)v66;
        if ( v66 )
          std::_Ref_count_base::_Decref(v66);
        break;
      }
      v15 = (int)v66;
      if ( v66 )
        std::_Ref_count_base::_Decref(v66);
    }
    v9 = v58;
    if ( (int)v58 >= 0 )
    {
      v74 = v10;
      v71 = v12;
      v18 = v63;
      v72 = v63;
      v19 = v64;
      v73 = v64;
      LOBYTE(v15) = 0;
      LODWORD(v59) = v15;
      BYTE4(v58) = 0;
      if ( *((_QWORD *)v2 + 5) )
      {
        try
        {
          std::vector<_WINBIO_PRESENCE>::reserve(v10);
          std::vector<_WINBIO_PRESENCE>::reserve(v12);
          std::vector<_WINBIO_PRESENCE>::reserve(v18);
          std::vector<_WINBIO_PRESENCE>::reserve(v19);
        }
        catch ( std::bad_alloc )
        {
          LODWORD(v58) = -2147024882;
          v5 = (std::_Ref_count_base *)*((_QWORD *)&v75 + 1);
          LOBYTE(v15) = BYTE4(v58);
          goto LABEL_20;
        }
        catch ( std::length_error )
        {
          LODWORD(v58) = -2147024882;
          v5 = (std::_Ref_count_base *)*((_QWORD *)&v75 + 1);
          v60 = (std::_Ref_count_base *)*((_QWORD *)&v75 + 1);
          LOBYTE(v15) = BYTE4(v58);
          LODWORD(v59) = v15;
          v10 = v74;
          v2 = v77;
          v69 = v77;
          v64 = v73;
          v63 = v72;
          v62 = v71;
          goto LABEL_26;
        }
        LOBYTE(v15) = v59;
LABEL_26:
        if ( (int)v58 >= 0 )
        {
          v21 = (_QWORD *)*((_QWORD *)v2 + 4);
          for ( j = (_QWORD *)*v21; j != v21; j = (_QWORD *)*j )
          {
            v41 = j[2];
            if ( CompareFileTime(&SystemTimeAsFileTime, (const FILETIME *)(v41 + 496)) > 0 )
            {
              *(_WORD *)(v41 + 517) = 0;
              *(_WORD *)(v41 + 521) = 1;
            }
          }
          v23 = (_QWORD *)*((_QWORD *)v2 + 4);
          v24 = (_QWORD *)*v23;
          v25 = v78;
          while ( v24 != v23 )
          {
            if ( !*(_BYTE *)(v24[2] + 516LL) )
            {
              if ( *v25 == *((_QWORD *)v10 + 2) )
                std::vector<_WINBIO_PRESENCE>::_Emplace_reallocate<_WINBIO_PRESENCE const &>(v10);
              else
                std::vector<_WINBIO_PRESENCE>::_Emplace_back_with_unused_capacity<_WINBIO_PRESENCE const &>(v10, v24[2]);
              memset_0((void *)(*((_QWORD *)v2 + 7) - 480LL), 0, 0x4Cu);
              *(_DWORD *)(*((_QWORD *)v2 + 7) - 480LL) = 0;
              *(_DWORD *)(*((_QWORD *)v2 + 7) - 484LL) = 0;
              *(_DWORD *)(*((_QWORD *)v2 + 7) - 488LL) = 0;
              *(_BYTE *)(v24[2] + 516LL) = 1;
            }
            v24 = (_QWORD *)*v24;
          }
          v26 = (__int64 ***)((char *)v2 + 32);
          v27 = (_QWORD *)*((_QWORD *)v2 + 4);
          v28 = (_QWORD *)*v27;
          v29 = v62;
          v30 = v79;
          while ( v28 != v27 )
          {
            v40 = (_BYTE *)v28[2];
            if ( v40[517] && !v40[518] && !v40[521] )
            {
              if ( *v30 == *((_QWORD *)v29 + 2) )
                std::vector<_WINBIO_PRESENCE>::_Emplace_reallocate<_WINBIO_PRESENCE const &>(v29);
              else
                std::vector<_WINBIO_PRESENCE>::_Emplace_back_with_unused_capacity<_WINBIO_PRESENCE const &>(v29, v28[2]);
              *(_BYTE *)(v28[2] + 518LL) = 1;
            }
            v28 = (_QWORD *)*v28;
          }
          v31 = *v26;
          v32 = **v26;
          v33 = v69;
          v34 = v63;
          v35 = v80;
          while ( v32 != (__int64 *)v31 )
          {
            v39 = v32[2];
            if ( *(_BYTE *)(v39 + 519) && !*(_BYTE *)(v39 + 520) )
            {
              if ( *v35 == *((_QWORD *)v34 + 2) )
                std::vector<_WINBIO_PRESENCE>::_Emplace_reallocate<_WINBIO_PRESENCE const &>(v34);
              else
                std::vector<_WINBIO_PRESENCE>::_Emplace_back_with_unused_capacity<_WINBIO_PRESENCE const &>(v34, v32[2]);
              *(_BYTE *)(v32[2] + 520) = 1;
              v56 = *((_QWORD *)v33 + 13);
              if ( *(_DWORD *)(v56 - 480) == 3 )
              {
                v57 = (unsigned __int8)v59;
                if ( !*(_DWORD *)(v56 - 488) )
                  v57 = 1;
                LODWORD(v59) = v57;
              }
            }
            v32 = (__int64 *)*v32;
          }
          v36 = *v26;
          v37 = **v26;
          v5 = v60;
          v38 = v81;
          while ( v37 != (__int64 *)v36 )
          {
            v42 = v37[2];
            if ( *(_BYTE *)(v42 + 521) && !*(_BYTE *)(v42 + 522) )
            {
              if ( *v38 == *((_QWORD *)v64 + 2) )
                std::vector<_WINBIO_PRESENCE>::_Emplace_reallocate<_WINBIO_PRESENCE const &>(v64);
              else
                std::vector<_WINBIO_PRESENCE>::_Emplace_back_with_unused_capacity<_WINBIO_PRESENCE const &>(v64, v37[2]);
              *(_BYTE *)(v37[2] + 522) = 1;
            }
            v37 = (__int64 *)*v37;
          }
          std::list<std::shared_ptr<CPresence>>::remove_if<bool (*)(std::shared_ptr<CPresence>)>(v26);
          LOBYTE(v15) = v59;
        }
      }
LABEL_20:
      *v82 = v15;
      v9 = v58;
    }
  }
LABEL_21:
  if ( v5 )
    std::_Ref_count_base::_Decref(v5);
  WppTraceUnwinder__lambda_526c18d49885b27cb39b2b27f84d5be0____::_WppTraceUnwinder__lambda_526c18d49885b27cb39b2b27f84d5be0____(&v70);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180008f10  mov     r11, rsp
0x180008f13  mov     [r11+18h], rbx
0x180008f17  mov     [r11+20h], rsi
0x180008f1b  push    rdi
0x180008f1c  push    r12
0x180008f1e  push    r13
0x180008f20  push    r14
0x180008f22  push    r15
0x180008f24  sub     rsp, 160h
0x180008f2b  mov     rax, cs:__security_cookie
0x180008f32  xor     rax, rsp
0x180008f35  mov     [rsp+188h+var_38], rax
0x180008f3d  mov     r14, rcx
0x180008f40  mov     [rsp+188h+var_110], rcx
0x180008f45  mov     [rsp+188h+var_C8], rcx
0x180008f4d  mov     [rsp+188h+var_A0], rdx
0x180008f55  xor     esi, esi
0x180008f57  mov     [rsp+188h+var_168], esi
0x180008f5b  mov     [rsp+188h+var_15C], esi
0x180008f5f  movups  xmm0, xmmword ptr cs:aCpresencemonit; "CPresenceMonitorLocal::Update"
0x180008f66  movups  xmmword ptr [r11-58h], xmm0
0x180008f6b  movups  xmm1, xmmword ptr cs:aCpresencemonit+0Eh; "orLocal::Update"
0x180008f72  movups  xmmword ptr [r11-4Ah], xmm1
0x180008f77  lea     rax, [r11-58h]
0x180008f7b  mov     [r11-98h], rax
0x180008f82  lea     rax, [rsp+188h+var_15C]
0x180008f87  mov     [r11-90h], rax
0x180008f8e  lea     rax, [rsp+188h+var_168]
0x180008f93  mov     [r11-88h], rax
0x180008f9a  lea     rcx, [r11-98h]
0x180008fa1  call    _lambda_526c18d49885b27cb39b2b27f84d5be0___operator__
0x180008fa6  mov     [rsp+188h+var_15C], 1
0x180008fae  lea     rax, [rsp+188h+var_98]
0x180008fb6  mov     [rsp+188h+var_108], rax
0x180008fbe  xorps   xmm0, xmm0
0x180008fc1  movdqu  [rsp+188h+var_E0], xmm0
0x180008fca  mov     rcx, [r14+10h]; this
0x180008fce  test    rcx, rcx
0x180008fd1  jz      loc_1800091C2
0x180008fd7  call    ?_Incref_nz@_Ref_count_base@std@@QEAA_NXZ; std::_Ref_count_base::_Incref_nz(void)
0x180008fdc  test    al, al
0x180008fde  jz      loc_1800091C2
0x180008fe4  mov     rax, [r14+8]
0x180008fe8  mov     qword ptr [rsp+188h+var_E0], rax
0x180008ff0  mov     r15, [r14+10h]
0x180008ff4  mov     qword ptr [rsp+188h+var_E0+8], r15
0x180008ffc  mov     [rsp+188h+var_158], r15
0x180009001  mov     rcx, [rax+0A90h]
0x180009008  add     rcx, 10h
0x18000900c  jz      loc_180009767
0x180009012  mov     [rsp+188h+var_150], rsi
0x180009017  mov     [rsp+188h+var_D0], rsi
0x18000901f  mov     rax, [rcx+20h]
0x180009023  test    rax, rax
0x180009026  jz      loc_180009767
0x18000902c  mov     rax, [rax+100h]
0x180009033  test    rax, rax
0x180009036  jz      loc_1800092A7
0x18000903c  lea     r8, [rsp+188h+var_150]
0x180009041  lea     rdx, [rsp+188h+var_D0]
0x180009049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000904e  mov     ebx, eax
0x180009050  mov     [rsp+188h+var_168], eax
0x180009054  test    eax, eax
0x180009056  js      loc_180009178
0x18000905c  mov     qword ptr [rsp+188h+SystemTimeAsFileTime.dwLowDateTime], rsi
0x180009061  lea     rcx, [rsp+188h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180009066  call    cs:__imp_GetSystemTimeAsFileTime
0x18000906c  lea     r12, [r14+30h]
0x180009070  mov     [rsp+188h+var_100], r12
0x180009078  lea     rcx, [r12+8]
0x18000907d  mov     [rsp+188h+var_C0], rcx
0x180009085  mov     rax, [r12]
0x180009089  cmp     rax, [rcx]
0x18000908c  jnz     loc_1800094F2
0x180009092  lea     r13, [r14+48h]
0x180009096  mov     [rsp+188h+var_148], r13
0x18000909b  mov     [rsp+188h+var_F8], r13
0x1800090a3  lea     rcx, [r13+8]
0x1800090a7  mov     [rsp+188h+var_B8], rcx
0x1800090af  mov     rax, [r13+0]
0x1800090b3  cmp     rax, [rcx]
0x1800090b6  jnz     loc_1800094FA
0x1800090bc  lea     rcx, [r14+60h]
0x1800090c0  mov     [rsp+188h+var_140], rcx
0x1800090c5  mov     [rsp+188h+var_F0], rcx
0x1800090cd  lea     rdx, [rcx+8]
0x1800090d1  mov     [rsp+188h+var_B0], rdx
0x1800090d9  mov     rax, [rcx]
0x1800090dc  cmp     rax, [rdx]
0x1800090df  jnz     loc_180009502
0x1800090e5  lea     rcx, [r14+78h]
0x1800090e9  mov     [rsp+188h+var_138], rcx
0x1800090ee  mov     [rsp+188h+var_E8], rcx
0x1800090f6  lea     rdx, [rcx+8]
0x1800090fa  mov     [rsp+188h+var_A8], rdx
0x180009102  mov     rax, [rcx]
0x180009105  cmp     rax, [rdx]
0x180009108  jnz     loc_18000950A
0x18000910e  mov     edi, esi
0x180009110  mov     [rsp+188h+var_160], edi
0x180009114  mov     eax, edi
0x180009116  cmp     rax, [rsp+188h+var_D0]
0x18000911e  jb      loc_180009345
0x180009124  mov     ebx, [rsp+188h+var_168]
0x180009128  test    ebx, ebx
0x18000912a  js      short loc_180009178
0x18000912c  mov     [rsp+188h+var_E8], r12
0x180009134  mov     [rsp+188h+var_100], r13
0x18000913c  mov     rbx, [rsp+188h+var_140]
0x180009141  mov     [rsp+188h+var_F8], rbx
0x180009149  mov     rdi, [rsp+188h+var_138]
0x18000914e  mov     [rsp+188h+var_F0], rdi
0x180009156  mov     cl, sil
0x180009159  mov     [rsp+188h+var_160], ecx
0x18000915d  mov     [rsp+188h+var_164], cl
0x180009161  mov     rdx, [r14+28h]
0x180009165  test    rdx, rdx
0x180009168  jnz     short loc_1800091D7
0x18000916a  mov     rax, [rsp+188h+var_A0]
0x180009172  mov     [rax], cl
0x180009174  mov     ebx, [rsp+188h+var_168]
0x180009178  test    r15, r15
0x18000917b  jz      short loc_180009186
0x18000917d  mov     rcx, r15; this
0x180009180  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180009185  nop
0x180009186  lea     rcx, [rsp+188h+var_108]
0x18000918e  call    WppTraceUnwinder__lambda_526c18d49885b27cb39b2b27f84d5be0_______WppTraceUnwinder__lambda_526c18d49885b27cb39b2b27f84d5be0____
0x180009193  mov     eax, ebx
0x180009195  mov     rcx, [rsp+188h+var_38]
0x18000919d  xor     rcx, rsp; StackCookie
0x1800091a0  call    __security_check_cookie
0x1800091a5  lea     r11, [rsp+188h+var_28]
0x1800091ad  mov     rbx, [r11+40h]
0x1800091b1  mov     rsi, [r11+48h]
0x1800091b5  mov     rsp, r11
0x1800091b8  pop     r15
0x1800091ba  pop     r14
0x1800091bc  pop     r13
0x1800091be  pop     r12
0x1800091c0  pop     rdi
0x1800091c1  retn
0x1800091c2  mov     r15, qword ptr [rsp+188h+var_E0+8]
0x1800091ca  mov     rax, qword ptr [rsp+188h+var_E0]
0x1800091d2  jmp     loc_180008FFC
0x1800091d7  mov     rcx, r12
0x1800091da  call    ?reserve@?$vector@U_WINBIO_PRESENCE@@V?$allocator@U_WINBIO_PRESENCE@@@std@@@std@@QEAAX_K@Z; std::vector<_WINBIO_PRESENCE>::reserve(unsigned __int64)
0x1800091df  mov     rdx, [r14+28h]
0x1800091e3  mov     rcx, r13
0x1800091e6  call    ?reserve@?$vector@U_WINBIO_PRESENCE@@V?$allocator@U_WINBIO_PRESENCE@@@std@@@std@@QEAAX_K@Z; std::vector<_WINBIO_PRESENCE>::reserve(unsigned __int64)
0x1800091eb  mov     rdx, [r14+28h]
0x1800091ef  mov     rcx, rbx
0x1800091f2  call    ?reserve@?$vector@U_WINBIO_PRESENCE@@V?$allocator@U_WINBIO_PRESENCE@@@std@@@std@@QEAAX_K@Z; std::vector<_WINBIO_PRESENCE>::reserve(unsigned __int64)
0x1800091f7  mov     rdx, [r14+28h]
0x1800091fb  mov     rcx, rdi
0x1800091fe  call    ?reserve@?$vector@U_WINBIO_PRESENCE@@V?$allocator@U_WINBIO_PRESENCE@@@std@@@std@@QEAAX_K@Z; std::vector<_WINBIO_PRESENCE>::reserve(unsigned __int64)
0x180009203  nop
0x180009204  mov     ecx, [rsp+188h+var_160]
0x180009208  cmp     [rsp+188h+var_168], esi
0x18000920c  jl      loc_18000916A
0x180009212  mov     rdi, [r14+20h]
0x180009216  mov     rbx, [rdi]
0x180009219  cmp     rbx, rdi
0x18000921c  jnz     loc_180009306
0x180009222  mov     rdi, [r14+20h]
0x180009226  mov     rbx, [rdi]
0x180009229  mov     r13, [rsp+188h+var_C0]
0x180009231  cmp     rbx, rdi
0x180009234  jnz     loc_1800092CB
0x18000923a  lea     r12, [r14+20h]
0x18000923e  mov     rdi, [r12]
0x180009242  mov     rbx, [rdi]
0x180009245  mov     r13, [rsp+188h+var_148]
0x18000924a  mov     r14, [rsp+188h+var_B8]
0x180009252  cmp     rbx, rdi
0x180009255  jnz     loc_1800092E4
0x18000925b  mov     rdi, [r12]
0x18000925f  mov     rbx, [rdi]
0x180009262  mov     r14, [rsp+188h+var_110]
0x180009267  mov     r15, [rsp+188h+var_140]
0x18000926c  mov     r13, [rsp+188h+var_B0]
0x180009274  cmp     rbx, rdi
0x180009277  jnz     short loc_1800092B5
0x180009279  mov     rdi, [r12]
0x18000927d  mov     rbx, [rdi]
0x180009280  mov     r15, [rsp+188h+var_158]
0x180009285  mov     r14, [rsp+188h+var_A8]
0x18000928d  cmp     rbx, rdi
0x180009290  jnz     loc_18000932C
0x180009296  mov     rcx, r12
0x180009299  call    ??$remove_if@P6A_NV?$shared_ptr@VCPresence@@@std@@@Z@?$list@V?$shared_ptr@VCPresence@@@std@@V?$allocator@V?$shared_ptr@VCPresence@@@std@@@2@@std@@QEAAXP6A_NV?$shared_ptr@VCPresence@@@1@@Z@Z; std::list<std::shared_ptr<CPresence>>::remove_if<bool (*)(std::shared_ptr<CPresence>)>(bool (*)(std::shared_ptr<CPresence>))
0x18000929e  mov     ecx, [rsp+188h+var_160]
0x1800092a2  jmp     loc_18000916A
0x1800092a7  mov     ebx, 80004001h
0x1800092ac  mov     [rsp+188h+var_168], ebx
0x1800092b0  jmp     loc_180009178
0x1800092b5  mov     r8, [rbx+10h]
0x1800092b9  cmp     [r8+207h], sil
0x1800092c0  jnz     loc_1800094C7
0x1800092c6  mov     rbx, [rbx]
0x1800092c9  jmp     short loc_180009274
0x1800092cb  mov     r8, [rbx+10h]
0x1800092cf  cmp     [r8+204h], sil
0x1800092d6  jz      loc_180009528
0x1800092dc  mov     rbx, [rbx]
0x1800092df  jmp     loc_180009231
0x1800092e4  mov     r8, [rbx+10h]
0x1800092e8  cmp     [r8+205h], sil
0x1800092ef  jz      short loc_1800092FE
0x1800092f1  cmp     [r8+206h], sil
0x1800092f8  jz      loc_1800096F1
0x1800092fe  mov     rbx, [rbx]
0x180009301  jmp     loc_180009252
0x180009306  mov     r13, [rbx+10h]
0x18000930a  lea     rdx, [r13+1F0h]; lpFileTime2
0x180009311  lea     rcx, [rsp+188h+SystemTimeAsFileTime]; lpFileTime1
0x180009316  call    cs:__imp_CompareFileTime
0x18000931c  test    eax, eax
0x18000931e  jg      loc_1800096CE
0x180009324  mov     rbx, [rbx]
0x180009327  jmp     loc_180009219
0x18000932c  mov     r8, [rbx+10h]
0x180009330  cmp     [r8+209h], sil
0x180009337  jnz     loc_18000974B
0x18000933d  mov     rbx, [rbx]
0x180009340  jmp     loc_18000928D
0x180009345  imul    rbx, rax, 1F0h
0x18000934c  mov     [rsp+188h+var_120], rbx
0x180009351  mov     r8, [rsp+188h+var_150]
0x180009356  mov     r8, [rbx+r8+60h]
0x18000935b  lea     rdx, [rsp+188h+var_130]
0x180009360  mov     rcx, r14
0x180009363  call    ?FindByTrackingId@CPresenceMonitorLocal@@AEAA?AV?$shared_ptr@VCPresence@@@std@@_K@Z; CPresenceMonitorLocal::FindByTrackingId(unsigned __int64)
0x180009368  nop
0x180009369  cmp     [rsp+188h+var_130], rsi
0x18000936e  jnz     loc_1800094A5
0x180009374  mov     ecx, 210h; Size
0x180009379  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000937e  mov     r13, rax
0x180009381  mov     rbx, [rsp+188h+var_150]
0x180009386  mov     ecx, [r14+18h]
0x18000938a  mov     [rax+1F8h], ecx
0x180009390  mov     qword ptr [rax+1FCh], 0
0x18000939b  mov     dword ptr [rax+204h], 0
0x1800093a5  mov     word ptr [rax+208h], 0
0x1800093ae  mov     [rax+20Ah], sil
0x1800093b5  xor     edx, edx; Val
0x1800093b7  mov     r8d, 1F0h; Size
0x1800093bd  mov     rcx, rax; void *
0x1800093c0  call    memset_0
0x1800093c5  mov     rcx, [rsp+188h+var_120]
0x1800093ca  mov     eax, [rcx+rbx]
0x1800093cd  mov     [r13+0], eax
0x1800093d1  mov     al, [rcx+rbx+4]
0x1800093d5  mov     [r13+4], al
0x1800093d9  mov     rax, [rcx+rbx+60h]
0x1800093de  mov     [r13+60h], rax
0x1800093e2  mov     qword ptr [r13+1F0h], 0
0x1800093ed  mov     rdx, r13
0x1800093f0  lea     rcx, [rsp+188h+var_68]
0x1800093f8  call    ??$?0VCPresence@@$0A@@?$shared_ptr@VCPresence@@@std@@QEAA@PEAVCPresence@@@Z; std::shared_ptr<CPresence>::shared_ptr<CPresence>(CPresence *)
0x1800093fd  mov     rcx, [rax]
0x180009400  mov     rdx, [rax+8]
0x180009404  mov     [rax], rsi
0x180009407  mov     [rax+8], rsi
0x18000940b  mov     [rsp+188h+var_130], rcx
0x180009410  mov     rcx, [rsp+188h+var_128]; this
0x180009415  mov     [rsp+188h+var_128], rdx
0x18000941a  test    rcx, rcx
0x18000941d  jz      short loc_180009424
0x18000941f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180009424  mov     rcx, [rsp+188h+var_60]; this
0x18000942c  test    rcx, rcx
0x18000942f  jz      short loc_180009436
0x180009431  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180009436  lea     rbx, [r14+20h]
0x18000943a  mov     rax, 7FFFFFFFFFFFFFFh
0x180009444  cmp     [rbx+8], rax
0x180009448  jz      loc_1800095DB
0x18000944e  mov     r13, [rbx]
0x180009451  mov     [rsp+188h+var_80], rbx
0x180009459  mov     [rsp+188h+var_78], rsi
0x180009461  mov     ecx, 20h ; ' '
0x180009466  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000946b  mov     r9, rax
0x18000946e  lea     rdx, [rax+10h]
0x180009472  lea     r8, [rsp+188h+var_130]
0x180009477  call    ??$construct@V?$shared_ptr@VCPresenceChangeItem@@@std@@AEBV12@@?$_Default_allocator_traits@V?$allocator@U?$_List_node@V?$shared_ptr@VCPresenceChangeItem@@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_List_node@V?$shared_ptr@VCPresenceChangeItem@@@std@@PEAX@std@@@1@QEAV?$shared_ptr@VCPresenceChangeItem@@@1@AEBV31@@Z; std::_Default_allocator_traits<std::allocator<std::_List_node<std::shared_ptr<CPresenceChangeItem>,void *>>>::construct<std::shared_ptr<CPresenceChangeItem>,std::shared_ptr<CPresenceChangeItem> const &>(std::allocator<std::_List_node<std::shared_ptr<CPresenceChangeItem>,void *>> &,std::shared_ptr<CPresenceChangeItem> * const,std::shared_ptr<CPresenceChangeItem> const &)
0x18000947c  nop
0x18000947d  inc     qword ptr [rbx+8]
0x180009481  mov     rcx, [r13+8]
0x180009485  mov     [r9], r13
0x180009488  mov     [r9+8], rcx
0x18000948c  mov     [rsp+188h+var_78], rsi
0x180009494  mov     [r13+8], r9
0x180009498  mov     [rcx], r9
0x18000949b  mov     r13, [rsp+188h+var_148]
0x1800094a0  mov     rbx, [rsp+188h+var_120]
0x1800094a5  cmp     [rsp+188h+var_168], esi
  ... truncated ...
```
