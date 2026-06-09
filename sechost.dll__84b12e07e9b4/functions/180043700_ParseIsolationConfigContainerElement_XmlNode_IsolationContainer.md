# ParseIsolationConfigContainerElement(XmlNode *,IsolationContainer *)

- ea: `0x180043700`
- end: `0x180044135`
- name: `?ParseIsolationConfigContainerElement@@YAHPEAVXmlNode@@PEAVIsolationContainer@@@Z`
- size: `2613`
- prototype: `__int64 __fastcall(struct XmlNode *, struct IsolationContainer *)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004413c`
- `0x180044a50`

## callees

- `0x180011a78`
- `0x180016a88`
- `0x1800192a8`
- `0x180042e6c`
- `0x180042e98`
- `0x18004345c`
- `0x180043700`
- `0x180044e54`
- `0x1800456b0`
- `0x180046938`
- `0x1800480f0`
- `0x18004ecbc`
- `0x18004ece0`
- `0x18004fa50`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043f66`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180044072`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800440b6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043f66`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180044072`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800440b6`

## pseudocode

```c
__int64 __fastcall ParseIsolationConfigContainerElement(struct XmlNode *a1, struct IsolationContainer *a2)
{
  __int64 v3; // rax
  unsigned int v4; // edi
  __int64 v5; // rax
  const wchar_t *v6; // r15
  __int64 v7; // rdx
  __int64 v8; // rdx
  char v9; // bl
  __int64 v11; // rbx
  int v12; // r12d
  int v13; // r13d
  __int64 v14; // rax
  unsigned int v15; // ebx
  __int64 (*v16)(void); // rax
  int v17; // r14d
  XmlNodeSet *v18; // rax
  struct XmlNode *i; // rax
  struct XmlNode *v20; // rsi
  int v21; // eax
  _WORD *v22; // rax
  __int64 v23; // r8
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rdx
  char v27; // al
  __int64 v28; // rdx
  char v29; // bl
  int v30; // edi
  __int64 v31; // rdx
  char v32; // bl
  int v33; // edi
  __int64 v34; // rdx
  char v35; // bl
  char v36; // al
  __int64 v37; // rdx
  char v38; // bl
  int v39; // edi
  __int64 v40; // rdx
  char v41; // bl
  int v42; // edi
  __int64 v43; // rdx
  char v44; // bl
  char v45; // al
  __int64 v46; // rdx
  char v47; // bl
  int v48; // edi
  __int64 v49; // rdx
  char v50; // bl
  int v51; // edi
  __int64 v52; // rdx
  char v53; // bl
  int v54; // edi
  __int64 v55; // rdx
  char v56; // bl
  char v57; // al
  __int64 v58; // rdx
  char v59; // bl
  char v60; // al
  __int64 v61; // rdx
  char v62; // bl
  _WORD *v63; // rax
  __int64 v64; // r8
  char v65; // al
  __int64 v66; // rdx
  char v67; // bl
  int v68; // eax
  __int64 v69; // rdx
  char v70; // al
  __int64 v71; // rdx
  char v72; // bl
  XmlNodeSet *v73; // rcx
  __int64 v74; // rbx
  __int64 v75; // rax
  __int64 v76; // rdx
  __int64 v77; // rax
  __int64 v78; // rax
  __int64 v79; // rdx
  __int64 v80; // rdx
  char v81; // [rsp+40h] [rbp-C0h]
  void *v82; // [rsp+48h] [rbp-B8h] BYREF
  struct IsolationContainer *v83; // [rsp+50h] [rbp-B0h]
  struct XmlNode *v84; // [rsp+58h] [rbp-A8h]
  __int64 v85; // [rsp+60h] [rbp-A0h]
  __int64 v86; // [rsp+68h] [rbp-98h]
  _BYTE v87[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v88[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v89[32]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v90[32]; // [rsp+D0h] [rbp-30h] BYREF
  _WORD v91[8]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v92; // [rsp+100h] [rbp+0h]
  __int64 v93; // [rsp+108h] [rbp+8h]

  v83 = a2;
  LODWORD(v82) = 0;
  v3 = *(_QWORD *)a1;
  v4 = 0;
  v84 = a1;
  v5 = (*(__int64 (__fastcall **)(struct XmlNode *))(v3 + 40))(a1);
  std::wstring::wstring(v90, v5);
  v6 = L"default";
  std::wstring::wstring(v91, L"default");
  v81 = Compare(v90, v91);
  LOBYTE(v7) = 1;
  std::wstring::_Tidy(v91, v7, 0);
  if ( v81 || (std::wstring::wstring(v91, L"container"), v4 = 1, v9 = 1, (unsigned __int8)Compare(v90, v91)) )
    v9 = 0;
  if ( (v4 & 1) != 0 )
  {
    v4 &= ~1u;
    LOBYTE(v8) = 1;
    std::wstring::_Tidy(v91, v8, 0);
  }
  if ( v9 )
  {
    LOBYTE(v8) = 1;
LABEL_8:
    std::wstring::_Tidy(v90, v8, 0);
    return 0;
  }
  else
  {
    v11 = *((_QWORD *)a2 + 31);
    v12 = *((_DWORD *)a2 + 56);
    v13 = *((_DWORD *)a2 + 57);
    v86 = *((_QWORD *)a2 + 30);
    v14 = *(_QWORD *)v84;
    v85 = v11;
    v15 = 0;
    v92 = 0;
    v91[0] = 0;
    v16 = *(__int64 (**)(void))(v14 + 32);
    v17 = *((_DWORD *)a2 + 58);
    v93 = 7;
    v82 = 0;
    v18 = (XmlNodeSet *)v16();
    for ( i = XmlNodeSet::iteratorReset(v18, &v82); ; i = XmlNodeSet::iteratorNext(v73, &v82) )
    {
      v20 = i;
      if ( !i )
        break;
      v21 = (*(__int64 (__fastcall **)(struct XmlNode *))(*(_QWORD *)i + 24LL))(i) - 2;
      if ( v21 )
      {
        if ( v21 == 1 )
        {
          v22 = (_WORD *)(*(__int64 (__fastcall **)(struct XmlNode *))(*(_QWORD *)v20 + 40LL))(v20);
          if ( *v22 )
          {
            v23 = -1;
            do
              ++v23;
            while ( v22[v23] );
          }
          else
          {
            v23 = 0;
          }
          std::wstring::assign(v90, v22, v23);
          v24 = (*(__int64 (__fastcall **)(struct XmlNode *))(*(_QWORD *)v20 + 48LL))(v20);
          std::wstring::wstring(v89, v24);
          if ( !v81 )
          {
            std::wstring::wstring(v88, L"name");
            v4 |= 2u;
            if ( (unsigned __int8)Compare(v90, v88) )
              LOBYTE(v15) = 1;
          }
          if ( (v4 & 2) != 0 )
          {
            v4 &= ~2u;
            LOBYTE(v25) = 1;
            std::wstring::_Tidy(v88, v25, 0);
          }
          if ( (_BYTE)v15 )
          {
            std::wstring::operator=(v91, v89);
          }
          else
          {
            std::wstring::wstring(v88, L"type");
            v27 = Compare(v90, v88);
            LOBYTE(v28) = 1;
            v29 = v27;
            std::wstring::_Tidy(v88, v28, 0);
            if ( v29 )
            {
              std::wstring::wstring(v87, L"physical");
              v30 = v4 | 4;
              v12 = 0;
              if ( (unsigned __int8)Compare(v89, v87)
                || (std::wstring::wstring(v88, L"0"), v30 |= 8u, v32 = 0, (unsigned __int8)Compare(v89, v88)) )
              {
                v32 = 1;
              }
              if ( (v30 & 8) != 0 )
              {
                v30 &= ~8u;
                LOBYTE(v31) = 1;
                std::wstring::_Tidy(v88, v31, 0);
              }
              LOBYTE(v31) = 1;
              v4 = v30 & 0xFFFFFFFB;
              std::wstring::_Tidy(v87, v31, 0);
              if ( !v32 )
              {
                std::wstring::wstring(v88, L"virtual");
                v33 = v4 | 0x10;
                if ( (unsigned __int8)Compare(v89, v88)
                  || (std::wstring::wstring(v87, L"1"), v33 |= 0x20u, v35 = 0, (unsigned __int8)Compare(v89, v87)) )
                {
                  v35 = 1;
                }
                if ( (v33 & 0x20) != 0 )
                {
                  v33 &= ~0x20u;
                  LOBYTE(v34) = 1;
                  std::wstring::_Tidy(v87, v34, 0);
                }
                LOBYTE(v34) = 1;
                std::wstring::_Tidy(v88, v34, 0);
                if ( !v35 )
                  goto LABEL_88;
                v4 = v33 & 0xFFFFFFEF;
                v12 = 1;
              }
            }
            else
            {
              std::wstring::wstring(v87, L"protection");
              v36 = Compare(v90, v87);
              LOBYTE(v37) = 1;
              v38 = v36;
              std::wstring::_Tidy(v87, v37, 0);
              if ( v38 )
              {
                std::wstring::wstring(v88, L"none");
                v39 = v4 | 0x40;
                v13 = 0;
                if ( (unsigned __int8)Compare(v89, v88)
                  || (std::wstring::wstring(v87, L"0"), v39 |= 0x80u, v41 = 0, (unsigned __int8)Compare(v89, v87)) )
                {
                  v41 = 1;
                }
                if ( (v39 & 0x80u) != 0 )
                {
                  v39 &= ~0x80u;
                  LOBYTE(v40) = 1;
                  std::wstring::_Tidy(v87, v40, 0);
                }
                LOBYTE(v40) = 1;
                v4 = v39 & 0xFFFFFFBF;
                std::wstring::_Tidy(v88, v40, 0);
                if ( !v41 )
                {
                  std::wstring::wstring(v88, L"process");
                  v42 = v4 | 0x100;
                  if ( (unsigned __int8)Compare(v89, v88)
                    || (std::wstring::wstring(v87, L"1"), v42 |= 0x200u, v44 = 0, (unsigned __int8)Compare(v89, v87)) )
                  {
                    v44 = 1;
                  }
                  if ( (v42 & 0x200) != 0 )
                  {
                    v42 &= ~0x200u;
                    LOBYTE(v43) = 1;
                    std::wstring::_Tidy(v87, v43, 0);
                  }
                  LOBYTE(v43) = 1;
                  std::wstring::_Tidy(v88, v43, 0);
                  if ( !v44 )
                    goto LABEL_88;
                  v4 = v42 & 0xFFFFFEFF;
                  v13 = 1;
                }
              }
              else
              {
                std::wstring::wstring(v87, L"share");
                v45 = Compare(v90, v87);
                LOBYTE(v46) = 1;
                v47 = v45;
                std::wstring::_Tidy(v87, v46, 0);
                if ( v47 )
                {
                  std::wstring::wstring(v88, L"everything");
                  v48 = v4 | 0x400;
                  v17 = 0;
                  if ( (unsigned __int8)Compare(v89, v88)
                    || (std::wstring::wstring(v87, L"0"), v48 |= 0x800u, v50 = 0, (unsigned __int8)Compare(v89, v87)) )
                  {
                    v50 = 1;
                  }
                  if ( (v48 & 0x800) != 0 )
                  {
                    v48 &= ~0x800u;
                    LOBYTE(v49) = 1;
                    std::wstring::_Tidy(v87, v49, 0);
                  }
                  LOBYTE(v49) = 1;
                  v4 = v48 & 0xFFFFFBFF;
                  std::wstring::_Tidy(v88, v49, 0);
                  if ( !v50 )
                  {
                    std::wstring::wstring(v88, L"somethings");
                    v51 = v4 | 0x1000;
                    if ( (unsigned __int8)Compare(v89, v88)
                      || (std::wstring::wstring(v87, L"1"), v51 |= 0x2000u, v53 = 0, (unsigned __int8)Compare(v89, v87)) )
                    {
                      v53 = 1;
                    }
                    if ( (v51 & 0x2000) != 0 )
                    {
                      v51 &= ~0x2000u;
                      LOBYTE(v52) = 1;
                      std::wstring::_Tidy(v87, v52, 0);
                    }
                    LOBYTE(v52) = 1;
                    v4 = v51 & 0xFFFFEFFF;
                    std::wstring::_Tidy(v88, v52, 0);
                    if ( v53 )
                    {
                      v17 = 1;
                    }
                    else
                    {
                      std::wstring::wstring(v88, L"nothing");
                      v54 = v4 | 0x4000;
                      if ( (unsigned __int8)Compare(v89, v88)
                        || (std::wstring::wstring(v87, L"2"), v54 |= 0x8000u,
                                                              v56 = 0,
                                                              (unsigned __int8)Compare(v89, v87)) )
                      {
                        v56 = 1;
                      }
                      if ( (v54 & 0x8000) != 0 )
                      {
                        v54 &= ~0x8000u;
                        LOBYTE(v55) = 1;
                        std::wstring::_Tidy(v87, v55, 0);
                      }
                      LOBYTE(v55) = 1;
                      std::wstring::_Tidy(v88, v55, 0);
                      if ( !v56 )
                      {
LABEL_88:
                        v74 = (*(__int64 (__fastcall **)(struct XmlNode *))(*(_QWORD *)v20 + 48LL))(v20);
                        v75 = (*(__int64 (__fastcall **)(struct XmlNode *))(*(_QWORD *)v20 + 40LL))(v20);
                        if ( !v81 )
                          v6 = L"container";
                        IsolationPolicy::TelemetryHelper::LogFormatError(4, &Options, v6, v75, v74, 0);
                        goto LABEL_91;
                      }
                      v4 = v54 & 0xFFFFBFFF;
                      v17 = 2;
                    }
                  }
                }
                else
                {
                  std::wstring::wstring(v87, L"validselectormask");
                  v57 = Compare(v90, v87);
                  LOBYTE(v58) = 1;
                  v59 = v57;
                  std::wstring::_Tidy(v87, v58, 0);
                  if ( v59 )
                  {
                    v86 = ToUint64(v89);
                  }
                  else
                  {
                    std::wstring::wstring(v87, L"defaultselectormask");
                    v60 = Compare(v90, v87);
                    LOBYTE(v61) = 1;
                    v62 = v60;
                    std::wstring::_Tidy(v87, v61, 0);
                    if ( !v62 )
                    {
                      v77 = (*(__int64 (__fastcall **)(struct XmlNode *))(*(_QWORD *)v20 + 40LL))(v20);
                      if ( !v81 )
                        v6 = L"container";
                      IsolationPolicy::TelemetryHelper::LogFormatError(3, v6, v77, &Options, &Options, 0);
LABEL_91:
                      SetLastError(0x57u);
                      LOBYTE(v76) = 1;
                      std::wstring::_Tidy(v89, v76, 0);
LABEL_92:
                      LOBYTE(v69) = 1;
                      std::wstring::_Tidy(v91, v69, 0);
                      LOBYTE(v8) = 1;
                      goto LABEL_8;
                    }
                    v85 = ToUint64(v89);
                  }
                }
              }
            }
          }
          v15 = 0;
          LOBYTE(v26) = 1;
          std::wstring::_Tidy(v89, v26, 0);
        }
      }
      else
      {
        v63 = (_WORD *)(*(__int64 (__fastcall **)(struct XmlNode *))(*(_QWORD *)v20 + 40LL))(v20);
        if ( *v63 )
        {
          v64 = -1;
          do
            ++v64;
          while ( v63[v64] );
        }
        else
        {
          v64 = 0;
        }
        std::wstring::assign(v90, v63, v64);
        std::wstring::wstring(v87, L"consumes");
        v65 = Compare(v90, v87);
        LOBYTE(v66) = 1;
        v67 = v65;
        std::wstring::_Tidy(v87, v66, 0);
        if ( v67 )
        {
          v68 = ParseIsolationConfigConsumesElement(v20, v83);
        }
        else
        {
          std::wstring::wstring(v87, L"mitigations");
          v70 = Compare(v90, v87);
          LOBYTE(v71) = 1;
          v72 = v70;
          std::wstring::_Tidy(v87, v71, 0);
          if ( !v72 )
          {
            v78 = (*(__int64 (__fastcall **)(struct XmlNode *))(*(_QWORD *)v20 + 40LL))(v20);
            if ( !v81 )
              v6 = L"container";
            IsolationPolicy::TelemetryHelper::LogFormatError(0, v6, v78, &Options, &Options, 0);
            SetLastError(0x57u);
            goto LABEL_92;
          }
          v68 = ParseIsolationConfigMitigationsElement(v20, v83);
        }
        v15 = 0;
        if ( !v68 )
          goto LABEL_92;
      }
      (*(void (__fastcall **)(struct XmlNode *))(*(_QWORD *)v84 + 32LL))(v84);
    }
    if ( v81 || v92 )
    {
      IsolationContainer::SetProperties((_DWORD)v83, (unsigned int)v91, v12, v13, v17, v86, v85);
      v15 = 1;
    }
    else
    {
      IsolationPolicy::TelemetryHelper::LogFormatError(5, &Options, L"container", L"name", &Options, 0);
      SetLastError(0x57u);
    }
    LOBYTE(v79) = 1;
    std::wstring::_Tidy(v91, v79, 0);
    LOBYTE(v80) = 1;
    std::wstring::_Tidy(v90, v80, 0);
    return v15;
  }
}

```

## disassembly

```asm
0x180043700  mov     [rsp-8+arg_10], rbx
0x180043705  push    rbp
0x180043706  push    rsi
0x180043707  push    rdi
0x180043708  push    r12
0x18004370a  push    r13
0x18004370c  push    r14
0x18004370e  push    r15
0x180043710  lea     rbp, [rsp-20h]
0x180043715  sub     rsp, 120h
0x18004371c  mov     rax, cs:__security_cookie
0x180043723  xor     rax, rsp
0x180043726  mov     [rbp+50h+var_40], rax
0x18004372a  xor     r14d, r14d
0x18004372d  mov     [rsp+150h+var_100], rdx
0x180043732  mov     dword ptr [rsp+150h+var_108], r14d
0x180043737  mov     rsi, rdx
0x18004373a  mov     rax, [rcx]
0x18004373d  mov     edi, r14d
0x180043740  mov     [rsp+150h+var_F8], rcx
0x180043745  mov     rax, [rax+28h]
0x180043749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004374e  mov     rdx, rax
0x180043751  lea     rcx, [rbp+50h+var_80]
0x180043755  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18004375a  lea     r15, aDefault; "default"
0x180043761  mov     rdx, r15
0x180043764  lea     rcx, [rbp+50h+var_60]
0x180043768  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18004376d  lea     rdx, [rbp+50h+var_60]
0x180043771  lea     rcx, [rbp+50h+var_80]
0x180043775  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x18004377a  lea     r12d, [r14+1]
0x18004377e  mov     [rsp+150h+var_110], al
0x180043782  mov     dl, r12b
0x180043785  lea     rcx, [rbp+50h+var_60]
0x180043789  xor     r8d, r8d
0x18004378c  mov     bl, al
0x18004378e  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180043793  test    bl, bl
0x180043795  jnz     short loc_1800437BE
0x180043797  lea     rdx, aContainer; "container"
0x18004379e  lea     rcx, [rbp+50h+var_60]
0x1800437a2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800437a7  lea     rdx, [rbp+50h+var_60]
0x1800437ab  mov     edi, r12d
0x1800437ae  lea     rcx, [rbp+50h+var_80]
0x1800437b2  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x1800437b7  mov     bl, r12b
0x1800437ba  test    al, al
0x1800437bc  jz      short loc_1800437C1
0x1800437be  mov     bl, r14b
0x1800437c1  test    r12b, dil
0x1800437c4  jz      short loc_1800437D8
0x1800437c6  and     edi, 0FFFFFFFEh
0x1800437c9  lea     rcx, [rbp+50h+var_60]
0x1800437cd  xor     r8d, r8d
0x1800437d0  mov     dl, r12b
0x1800437d3  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800437d8  test    bl, bl
0x1800437da  jz      short loc_1800437F2
0x1800437dc  mov     dl, r12b
0x1800437df  xor     r8d, r8d
0x1800437e2  lea     rcx, [rbp+50h+var_80]
0x1800437e6  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800437eb  xor     eax, eax
0x1800437ed  jmp     loc_18004410E
0x1800437f2  mov     rax, [rsi+0F0h]
0x1800437f9  mov     rbx, [rsi+0F8h]
0x180043800  mov     rcx, [rsp+150h+var_F8]
0x180043805  mov     r12d, [rsi+0E0h]
0x18004380c  mov     r13d, [rsi+0E4h]
0x180043813  mov     [rsp+150h+var_E8], rax
0x180043818  mov     rax, [rcx]
0x18004381b  mov     [rsp+150h+var_F0], rbx
0x180043820  xor     ebx, ebx
0x180043822  mov     [rbp+50h+var_50], r14
0x180043826  mov     [rbp+50h+var_60], r14w
0x18004382b  mov     rax, [rax+20h]
0x18004382f  mov     r14d, [rsi+0E8h]
0x180043836  mov     [rbp+50h+var_48], 7
0x18004383e  mov     [rsp+150h+var_108], rbx
0x180043843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043848  lea     rdx, [rsp+150h+var_108]; void **
0x18004384d  mov     rcx, rax; this
0x180043850  call    ?iteratorReset@XmlNodeSet@@QEAAPEAVXmlNode@@PEAPEAX@Z; XmlNodeSet::iteratorReset(void * *)
0x180043855  mov     rsi, rax
0x180043858  test    rax, rax
0x18004385b  jz      loc_18004407D
0x180043861  mov     rax, [rax]
0x180043864  mov     rcx, rsi
0x180043867  mov     rax, [rax+18h]
0x18004386b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043870  sub     eax, 2
0x180043873  jz      loc_180043E2A
0x180043879  cmp     eax, 1
0x18004387c  jnz     loc_180043EEF
0x180043882  mov     rax, [rsi]
0x180043885  mov     rcx, rsi
0x180043888  mov     rax, [rax+28h]
0x18004388c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043891  cmp     [rax], bx
0x180043894  jnz     short loc_18004389B
0x180043896  mov     r8, rbx
0x180043899  jmp     short loc_1800438A9
0x18004389b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004389f  inc     r8
0x1800438a2  cmp     [rax+r8*2], bx
0x1800438a7  jnz     short loc_18004389F
0x1800438a9  mov     rdx, rax
0x1800438ac  lea     rcx, [rbp+50h+var_80]
0x1800438b0  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800438b5  mov     rax, [rsi]
0x1800438b8  mov     rcx, rsi
0x1800438bb  mov     rax, [rax+30h]
0x1800438bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800438c4  mov     rdx, rax
0x1800438c7  lea     rcx, [rbp+50h+var_A0]
0x1800438cb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800438d0  cmp     [rsp+150h+var_110], bl
0x1800438d4  jnz     short loc_1800438FC
0x1800438d6  lea     rdx, aName_0; "name"
0x1800438dd  lea     rcx, [rbp+50h+var_C0]
0x1800438e1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800438e6  lea     rdx, [rbp+50h+var_C0]
0x1800438ea  or      edi, 2
0x1800438ed  lea     rcx, [rbp+50h+var_80]
0x1800438f1  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x1800438f6  test    al, al
0x1800438f8  jz      short loc_1800438FC
0x1800438fa  mov     bl, 1
0x1800438fc  test    dil, 2
0x180043900  jz      short loc_180043913
0x180043902  and     edi, 0FFFFFFFDh
0x180043905  lea     rcx, [rbp+50h+var_C0]
0x180043909  xor     r8d, r8d
0x18004390c  mov     dl, 1
0x18004390e  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180043913  test    bl, bl
0x180043915  jz      short loc_180043929
0x180043917  lea     rdx, [rbp+50h+var_A0]
0x18004391b  lea     rcx, [rbp+50h+var_60]
0x18004391f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180043924  jmp     loc_180043E15
0x180043929  lea     rdx, aType; "type"
0x180043930  lea     rcx, [rbp+50h+var_C0]
0x180043934  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180043939  lea     rdx, [rbp+50h+var_C0]
0x18004393d  lea     rcx, [rbp+50h+var_80]
0x180043941  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x180043946  xor     r8d, r8d
0x180043949  lea     rcx, [rbp+50h+var_C0]
0x18004394d  mov     dl, 1
0x18004394f  mov     bl, al
0x180043951  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180043956  lea     rcx, [rsp+150h+var_E0]
0x18004395b  test    bl, bl
0x18004395d  jz      loc_180043A6C
0x180043963  lea     rdx, aPhysical; "physical"
0x18004396a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18004396f  lea     rdx, [rsp+150h+var_E0]
0x180043974  or      edi, 4
0x180043977  lea     rcx, [rbp+50h+var_A0]
0x18004397b  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x180043980  xor     r12d, r12d
0x180043983  test    al, al
0x180043985  jnz     short loc_1800439AE
0x180043987  lea     rdx, a0; "0"
0x18004398e  lea     rcx, [rbp+50h+var_C0]
0x180043992  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180043997  lea     rdx, [rbp+50h+var_C0]
0x18004399b  or      edi, 8
0x18004399e  lea     rcx, [rbp+50h+var_A0]
0x1800439a2  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x1800439a7  mov     bl, r12b
0x1800439aa  test    al, al
0x1800439ac  jz      short loc_1800439B0
0x1800439ae  mov     bl, 1
0x1800439b0  test    dil, 8
0x1800439b4  jz      short loc_1800439C7
0x1800439b6  and     edi, 0FFFFFFF7h
0x1800439b9  lea     rcx, [rbp+50h+var_C0]
0x1800439bd  xor     r8d, r8d
0x1800439c0  mov     dl, 1
0x1800439c2  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800439c7  xor     r8d, r8d
0x1800439ca  lea     rcx, [rsp+150h+var_E0]
0x1800439cf  mov     dl, 1
0x1800439d1  and     edi, 0FFFFFFFBh
0x1800439d4  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800439d9  test    bl, bl
0x1800439db  jnz     loc_180043E15
0x1800439e1  lea     rdx, aVirtual; "virtual"
0x1800439e8  lea     rcx, [rbp+50h+var_C0]
0x1800439ec  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800439f1  lea     rdx, [rbp+50h+var_C0]
0x1800439f5  or      edi, 10h
0x1800439f8  lea     rcx, [rbp+50h+var_A0]
0x1800439fc  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x180043a01  test    al, al
0x180043a03  jnz     short loc_180043A2E
0x180043a05  lea     rdx, a1; "1"
0x180043a0c  lea     rcx, [rsp+150h+var_E0]
0x180043a11  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180043a16  lea     rdx, [rsp+150h+var_E0]
0x180043a1b  or      edi, 20h
0x180043a1e  lea     rcx, [rbp+50h+var_A0]
0x180043a22  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x180043a27  mov     bl, r12b
0x180043a2a  test    al, al
0x180043a2c  jz      short loc_180043A30
0x180043a2e  mov     bl, 1
0x180043a30  test    dil, 20h
0x180043a34  jz      short loc_180043A48
0x180043a36  and     edi, 0FFFFFFDFh
0x180043a39  lea     rcx, [rsp+150h+var_E0]
0x180043a3e  xor     r8d, r8d
0x180043a41  mov     dl, 1
0x180043a43  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180043a48  xor     r8d, r8d
0x180043a4b  lea     rcx, [rbp+50h+var_C0]
0x180043a4f  mov     dl, 1
0x180043a51  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180043a56  test    bl, bl
0x180043a58  jz      loc_180043F0F
0x180043a5e  and     edi, 0FFFFFFEFh
0x180043a61  mov     r12d, 1
0x180043a67  jmp     loc_180043E15
0x180043a6c  lea     rdx, aProtection; "protection"
0x180043a73  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180043a78  lea     rdx, [rsp+150h+var_E0]
0x180043a7d  lea     rcx, [rbp+50h+var_80]
0x180043a81  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x180043a86  xor     r8d, r8d
0x180043a89  lea     rcx, [rsp+150h+var_E0]
0x180043a8e  mov     dl, 1
0x180043a90  mov     bl, al
0x180043a92  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180043a97  test    bl, bl
0x180043a99  jz      loc_180043BB2
0x180043a9f  lea     rdx, aNone; "none"
0x180043aa6  lea     rcx, [rbp+50h+var_C0]
0x180043aaa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180043aaf  lea     rdx, [rbp+50h+var_C0]
0x180043ab3  or      edi, 40h
0x180043ab6  lea     rcx, [rbp+50h+var_A0]
0x180043aba  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x180043abf  xor     r13d, r13d
0x180043ac2  test    al, al
0x180043ac4  jnz     short loc_180043AF0
0x180043ac6  lea     rdx, a0; "0"
0x180043acd  lea     rcx, [rsp+150h+var_E0]
0x180043ad2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180043ad7  lea     rdx, [rsp+150h+var_E0]
0x180043adc  bts     edi, 7
0x180043ae0  lea     rcx, [rbp+50h+var_A0]
0x180043ae4  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x180043ae9  mov     bl, r13b
0x180043aec  test    al, al
0x180043aee  jz      short loc_180043AF2
0x180043af0  mov     bl, 1
0x180043af2  test    dil, dil
0x180043af5  jns     short loc_180043B0A
0x180043af7  btr     edi, 7
0x180043afb  lea     rcx, [rsp+150h+var_E0]
0x180043b00  xor     r8d, r8d
0x180043b03  mov     dl, 1
0x180043b05  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180043b0a  xor     r8d, r8d
0x180043b0d  lea     rcx, [rbp+50h+var_C0]
0x180043b11  mov     dl, 1
0x180043b13  and     edi, 0FFFFFFBFh
0x180043b16  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180043b1b  test    bl, bl
0x180043b1d  jnz     loc_180043E15
0x180043b23  lea     rdx, aProcess; "process"
0x180043b2a  lea     rcx, [rbp+50h+var_C0]
0x180043b2e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180043b33  lea     rdx, [rbp+50h+var_C0]
0x180043b37  bts     edi, 8
0x180043b3b  lea     rcx, [rbp+50h+var_A0]
0x180043b3f  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x180043b44  test    al, al
0x180043b46  jnz     short loc_180043B72
0x180043b48  lea     rdx, a1; "1"
0x180043b4f  lea     rcx, [rsp+150h+var_E0]
0x180043b54  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180043b59  lea     rdx, [rsp+150h+var_E0]
0x180043b5e  bts     edi, 9
0x180043b62  lea     rcx, [rbp+50h+var_A0]
0x180043b66  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x180043b6b  mov     bl, r13b
0x180043b6e  test    al, al
0x180043b70  jz      short loc_180043B74
0x180043b72  mov     bl, 1
0x180043b74  bt      edi, 9
0x180043b78  jnb     short loc_180043B8D
0x180043b7a  btr     edi, 9
0x180043b7e  lea     rcx, [rsp+150h+var_E0]
0x180043b83  xor     r8d, r8d
  ... truncated ...
```
