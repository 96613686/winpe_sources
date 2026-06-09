# ParseIsolationConfigContainerGroupElement(XmlNode *,IsolationConfig *,IsolationContainer const *)

- ea: `0x18004413c`
- end: `0x180044a4a`
- name: `?ParseIsolationConfigContainerGroupElement@@YAHPEAVXmlNode@@PEAVIsolationConfig@@PEBVIsolationContainer@@@Z`
- size: `2318`
- prototype: `__int64 __fastcall(struct XmlNode *, struct IsolationConfig *, const struct IsolationContainer *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180044a50`

## callees

- `0x180016a88`
- `0x1800192a8`
- `0x180042e98`
- `0x180043700`
- `0x18004413c`
- `0x1800456b0`
- `0x180045868`
- `0x180045ad8`
- `0x180046938`
- `0x180047148`
- `0x1800480f0`
- `0x18004ecbc`
- `0x18004ece0`
- `0x18004fa50`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004494d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180044a10`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004494d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180044a10`

## pseudocode

```c
__int64 __fastcall ParseIsolationConfigContainerGroupElement(
        struct XmlNode *a1,
        struct IsolationConfig *a2,
        const struct IsolationContainer *a3)
{
  unsigned int v5; // edi
  __int64 v6; // rax
  char v7; // al
  __int64 v8; // rdx
  char v9; // bl
  __int64 v10; // rdx
  int v12; // r12d
  int v13; // r13d
  int v14; // r15d
  XmlNodeSet *v15; // rax
  struct XmlNode *i; // rax
  struct XmlNode *v17; // rsi
  int v18; // eax
  __int64 v19; // rax
  __int64 v20; // rax
  char v21; // al
  __int64 v22; // rdx
  char v23; // bl
  int v24; // edi
  __int64 v25; // rdx
  bool v26; // bl
  __int64 v27; // rdx
  int v28; // edi
  __int64 v29; // rdx
  bool v30; // bl
  char v31; // al
  __int64 v32; // rdx
  char v33; // bl
  int v34; // edi
  __int64 v35; // rdx
  bool v36; // bl
  int v37; // edi
  __int64 v38; // rdx
  bool v39; // bl
  char v40; // al
  __int64 v41; // rdx
  char v42; // bl
  int v43; // edi
  __int64 v44; // rdx
  bool v45; // bl
  int v46; // edi
  __int64 v47; // rdx
  bool v48; // bl
  int v49; // edi
  __int64 v50; // rdx
  bool v51; // bl
  char v52; // al
  __int64 v53; // rdx
  char v54; // bl
  char v55; // al
  __int64 v56; // rdx
  char v57; // bl
  __int64 v58; // rdx
  __int64 v59; // rax
  char v60; // al
  __int64 v61; // rdx
  char v62; // bl
  __int64 v63; // rdx
  bool v64; // al
  __int64 v65; // rcx
  unsigned __int64 v66; // rbx
  const struct IsolationContainer *v67; // rdx
  XmlNodeSet *v68; // rcx
  __int64 v69; // rbx
  __int64 v70; // rax
  __int64 v71; // rdx
  __int64 v72; // rdx
  __int64 v73; // rax
  __int64 v74; // rax
  __int64 v75; // [rsp+40h] [rbp-C0h]
  __int64 v77; // [rsp+50h] [rbp-B0h]
  void *v78; // [rsp+58h] [rbp-A8h] BYREF
  struct XmlNode *v79; // [rsp+60h] [rbp-A0h]
  _BYTE v80[32]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v81[32]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v82[32]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v83[40]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v84[256]; // [rsp+F0h] [rbp-10h] BYREF

  v79 = a1;
  v5 = 0;
  std::wstring::wstring(v81, L"containergroup");
  v6 = (*(__int64 (__fastcall **)(struct XmlNode *))(*(_QWORD *)a1 + 40LL))(a1);
  std::wstring::wstring(v83, v6);
  v7 = Compare(v83, v81);
  LOBYTE(v8) = 1;
  v9 = v7;
  std::wstring::_Tidy(v83, v8, 0);
  LOBYTE(v10) = 1;
  std::wstring::_Tidy(v81, v10, 0);
  if ( !v9 )
    return 0;
  v78 = 0;
  v12 = *((_DWORD *)a3 + 56);
  v13 = *((_DWORD *)a3 + 57);
  v14 = *((_DWORD *)a3 + 58);
  v77 = *((_QWORD *)a3 + 30);
  v75 = *((_QWORD *)a3 + 31);
  v15 = (XmlNodeSet *)(*(__int64 (__fastcall **)(struct XmlNode *))(*(_QWORD *)a1 + 32LL))(a1);
  for ( i = XmlNodeSet::iteratorReset(v15, &v78); ; i = XmlNodeSet::iteratorNext(v68, &v78) )
  {
    v17 = i;
    if ( !i )
      break;
    v18 = (*(__int64 (__fastcall **)(struct XmlNode *))(*(_QWORD *)i + 24LL))(i) - 2;
    if ( v18 )
    {
      if ( v18 != 1 )
        goto LABEL_86;
      v19 = (*(__int64 (__fastcall **)(struct XmlNode *))(*(_QWORD *)v17 + 40LL))(v17);
      std::wstring::wstring(v83, v19);
      v20 = (*(__int64 (__fastcall **)(struct XmlNode *))(*(_QWORD *)v17 + 48LL))(v17);
      std::wstring::wstring(v81, v20);
      std::wstring::wstring(v82, L"type");
      v21 = Compare(v83, v82);
      LOBYTE(v22) = 1;
      v23 = v21;
      std::wstring::_Tidy(v82, v22, 0);
      if ( v23 )
      {
        std::wstring::wstring(v80, L"physical");
        v24 = v5 | 1;
        v26 = 1;
        if ( !(unsigned __int8)Compare(v81, v80) )
        {
          std::wstring::wstring(v82, L"0");
          v24 |= 2u;
          if ( !(unsigned __int8)Compare(v81, v82) )
            v26 = 0;
        }
        if ( (v24 & 2) != 0 )
        {
          v24 &= ~2u;
          LOBYTE(v25) = 1;
          std::wstring::_Tidy(v82, v25, 0);
        }
        LOBYTE(v25) = 1;
        v5 = v24 & 0xFFFFFFFE;
        std::wstring::_Tidy(v80, v25, 0);
        if ( v26 )
        {
          v12 = 0;
        }
        else
        {
          std::wstring::wstring(v82, L"virtual");
          v28 = v5 | 4;
          v30 = 1;
          if ( !(unsigned __int8)Compare(v81, v82) )
          {
            std::wstring::wstring(v80, L"1");
            v28 |= 8u;
            if ( !(unsigned __int8)Compare(v81, v80) )
              v30 = 0;
          }
          if ( (v28 & 8) != 0 )
          {
            v28 &= ~8u;
            LOBYTE(v29) = 1;
            std::wstring::_Tidy(v80, v29, 0);
          }
          LOBYTE(v29) = 1;
          std::wstring::_Tidy(v82, v29, 0);
          if ( !v30 )
            goto LABEL_87;
          v5 = v28 & 0xFFFFFFFB;
          v12 = 1;
        }
      }
      else
      {
        std::wstring::wstring(v80, L"protection");
        v31 = Compare(v83, v80);
        LOBYTE(v32) = 1;
        v33 = v31;
        std::wstring::_Tidy(v80, v32, 0);
        if ( v33 )
        {
          std::wstring::wstring(v82, L"none");
          v34 = v5 | 0x10;
          v36 = 1;
          if ( !(unsigned __int8)Compare(v81, v82) )
          {
            std::wstring::wstring(v80, L"0");
            v34 |= 0x20u;
            if ( !(unsigned __int8)Compare(v81, v80) )
              v36 = 0;
          }
          if ( (v34 & 0x20) != 0 )
          {
            v34 &= ~0x20u;
            LOBYTE(v35) = 1;
            std::wstring::_Tidy(v80, v35, 0);
          }
          LOBYTE(v35) = 1;
          v5 = v34 & 0xFFFFFFEF;
          std::wstring::_Tidy(v82, v35, 0);
          if ( v36 )
          {
            v13 = 0;
          }
          else
          {
            std::wstring::wstring(v82, L"process");
            v37 = v5 | 0x40;
            v39 = 1;
            if ( !(unsigned __int8)Compare(v81, v82) )
            {
              std::wstring::wstring(v80, L"1");
              v37 |= 0x80u;
              if ( !(unsigned __int8)Compare(v81, v80) )
                v39 = 0;
            }
            if ( (v37 & 0x80u) != 0 )
            {
              v37 &= ~0x80u;
              LOBYTE(v38) = 1;
              std::wstring::_Tidy(v80, v38, 0);
            }
            LOBYTE(v38) = 1;
            std::wstring::_Tidy(v82, v38, 0);
            if ( !v39 )
              goto LABEL_87;
            v5 = v37 & 0xFFFFFFBF;
            v13 = 1;
          }
        }
        else
        {
          std::wstring::wstring(v80, L"share");
          v40 = Compare(v83, v80);
          LOBYTE(v41) = 1;
          v42 = v40;
          std::wstring::_Tidy(v80, v41, 0);
          if ( v42 )
          {
            std::wstring::wstring(v82, L"everything");
            v43 = v5 | 0x100;
            v45 = 1;
            if ( !(unsigned __int8)Compare(v81, v82) )
            {
              std::wstring::wstring(v80, L"0");
              v43 |= 0x200u;
              if ( !(unsigned __int8)Compare(v81, v80) )
                v45 = 0;
            }
            if ( (v43 & 0x200) != 0 )
            {
              v43 &= ~0x200u;
              LOBYTE(v44) = 1;
              std::wstring::_Tidy(v80, v44, 0);
            }
            LOBYTE(v44) = 1;
            v5 = v43 & 0xFFFFFEFF;
            std::wstring::_Tidy(v82, v44, 0);
            if ( v45 )
            {
              v14 = 0;
            }
            else
            {
              std::wstring::wstring(v82, L"somethings");
              v46 = v5 | 0x400;
              v48 = 1;
              if ( !(unsigned __int8)Compare(v81, v82) )
              {
                std::wstring::wstring(v80, L"1");
                v46 |= 0x800u;
                if ( !(unsigned __int8)Compare(v81, v80) )
                  v48 = 0;
              }
              if ( (v46 & 0x800) != 0 )
              {
                v46 &= ~0x800u;
                LOBYTE(v47) = 1;
                std::wstring::_Tidy(v80, v47, 0);
              }
              LOBYTE(v47) = 1;
              v5 = v46 & 0xFFFFFBFF;
              std::wstring::_Tidy(v82, v47, 0);
              if ( v48 )
              {
                v14 = 1;
              }
              else
              {
                std::wstring::wstring(v82, L"nothing");
                v49 = v5 | 0x1000;
                v51 = 1;
                if ( !(unsigned __int8)Compare(v81, v82) )
                {
                  std::wstring::wstring(v80, L"2");
                  v49 |= 0x2000u;
                  if ( !(unsigned __int8)Compare(v81, v80) )
                    v51 = 0;
                }
                if ( (v49 & 0x2000) != 0 )
                {
                  v49 &= ~0x2000u;
                  LOBYTE(v50) = 1;
                  std::wstring::_Tidy(v80, v50, 0);
                }
                LOBYTE(v50) = 1;
                std::wstring::_Tidy(v82, v50, 0);
                if ( !v51 )
                {
LABEL_87:
                  v69 = (*(__int64 (__fastcall **)(struct XmlNode *))(*(_QWORD *)v17 + 48LL))(v17);
                  v70 = (*(__int64 (__fastcall **)(struct XmlNode *))(*(_QWORD *)v17 + 40LL))(v17);
                  IsolationPolicy::TelemetryHelper::LogFormatError(4, &Options, L"containergroup", v70, v69, 0);
                  goto LABEL_88;
                }
                v5 = v49 & 0xFFFFEFFF;
                v14 = 2;
              }
            }
          }
          else
          {
            std::wstring::wstring(v80, L"validselectormask");
            v52 = Compare(v83, v80);
            LOBYTE(v53) = 1;
            v54 = v52;
            std::wstring::_Tidy(v80, v53, 0);
            if ( v54 )
            {
              v77 = ToUint64(v81);
            }
            else
            {
              std::wstring::wstring(v80, L"defaultselectormask");
              v55 = Compare(v83, v80);
              LOBYTE(v56) = 1;
              v57 = v55;
              std::wstring::_Tidy(v80, v56, 0);
              if ( !v57 )
              {
                v73 = (*(__int64 (__fastcall **)(struct XmlNode *))(*(_QWORD *)v17 + 40LL))(v17);
                IsolationPolicy::TelemetryHelper::LogFormatError(3, L"containergroup", v73, &Options, &Options, 0);
LABEL_88:
                SetLastError(0x57u);
                LOBYTE(v71) = 1;
                std::wstring::_Tidy(v81, v71, 0);
LABEL_89:
                LOBYTE(v72) = 1;
                std::wstring::_Tidy(v83, v72, 0);
                return 0;
              }
              v75 = ToUint64(v81);
            }
          }
        }
      }
      LOBYTE(v27) = 1;
      std::wstring::_Tidy(v81, v27, 0);
    }
    else
    {
      v59 = (*(__int64 (__fastcall **)(struct XmlNode *))(*(_QWORD *)v17 + 40LL))(v17);
      std::wstring::wstring(v83, v59);
      std::wstring::wstring(v80, L"container");
      v60 = Compare(v83, v80);
      LOBYTE(v61) = 1;
      v62 = v60;
      std::wstring::_Tidy(v80, v61, 0);
      if ( !v62 )
      {
        v74 = (*(__int64 (__fastcall **)(struct XmlNode *))(*(_QWORD *)v17 + 40LL))(v17);
        IsolationPolicy::TelemetryHelper::LogFormatError(0, L"containergroup", v74, &Options, &Options, 0);
        SetLastError(0x57u);
        goto LABEL_89;
      }
      IsolationContainer::IsolationContainer((IsolationContainer *)v84, a3);
      std::wstring::wstring(v80, &Options);
      IsolationContainer::SetProperties((unsigned int)v84, (unsigned int)v80, v12, v13, v14, v77, v75);
      LOBYTE(v63) = 1;
      std::wstring::_Tidy(v80, v63, 0);
      if ( !(unsigned int)ParseIsolationConfigContainerElement(v17, (struct IsolationContainer *)v84) )
      {
        IsolationContainer::~IsolationContainer((IsolationContainer *)v84);
        goto LABEL_89;
      }
      v64 = (unsigned __int64)v84 < *((_QWORD *)a2 + 1) && *(_QWORD *)a2 <= (unsigned __int64)v84;
      v65 = *((_QWORD *)a2 + 2);
      if ( v64 )
      {
        v66 = (unsigned __int64)&v84[-*(_QWORD *)a2];
        if ( *((_QWORD *)a2 + 1) == v65 )
          std::vector<IsolationContainer>::_Reserve(a2);
        v67 = (const struct IsolationContainer *)(*(_QWORD *)a2 + (v66 & 0xFFFFFFFFFFFFFF00uLL));
      }
      else
      {
        if ( *((_QWORD *)a2 + 1) == v65 )
          std::vector<IsolationContainer>::_Reserve(a2);
        v67 = (const struct IsolationContainer *)v84;
      }
      IsolationContainer::IsolationContainer(*((IsolationContainer **)a2 + 1), v67);
      *((_QWORD *)a2 + 1) += 256LL;
      IsolationContainer::~IsolationContainer((IsolationContainer *)v84);
    }
    LOBYTE(v58) = 1;
    std::wstring::_Tidy(v83, v58, 0);
LABEL_86:
    (*(void (__fastcall **)(struct XmlNode *))(*(_QWORD *)v79 + 32LL))(v79);
  }
  return 1;
}

```

## disassembly

```asm
0x18004413c  mov     [rsp-8+arg_18], rbx
0x180044141  push    rbp
0x180044142  push    rsi
0x180044143  push    rdi
0x180044144  push    r12
0x180044146  push    r13
0x180044148  push    r14
0x18004414a  push    r15
0x18004414c  lea     rbp, [rsp-100h]
0x180044154  sub     rsp, 200h
0x18004415b  mov     rax, cs:__security_cookie
0x180044162  xor     rax, rsp
0x180044165  mov     [rbp+130h+var_40], rax
0x18004416c  mov     r14, rdx
0x18004416f  mov     [rsp+230h+var_1D0], rcx
0x180044174  mov     rsi, rcx
0x180044177  mov     [rsp+230h+var_1E8], r8
0x18004417c  xor     edi, edi
0x18004417e  lea     rdx, aContainergroup; "containergroup"
0x180044185  lea     rcx, [rbp+130h+var_1A8]
0x180044189  mov     dword ptr [rsp+230h+var_1F0], edi
0x18004418d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180044192  mov     rax, [rsi]
0x180044195  mov     rcx, rsi
0x180044198  mov     rax, [rax+28h]
0x18004419c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800441a1  mov     rdx, rax
0x1800441a4  lea     rcx, [rbp+130h+var_168]
0x1800441a8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800441ad  lea     rdx, [rbp+130h+var_1A8]
0x1800441b1  lea     rcx, [rbp+130h+var_168]
0x1800441b5  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x1800441ba  xor     r8d, r8d
0x1800441bd  lea     rcx, [rbp+130h+var_168]
0x1800441c1  mov     dl, 1
0x1800441c3  mov     bl, al
0x1800441c5  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800441ca  xor     r8d, r8d
0x1800441cd  lea     rcx, [rbp+130h+var_1A8]
0x1800441d1  mov     dl, 1
0x1800441d3  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800441d8  test    bl, bl
0x1800441da  jnz     short loc_1800441E3
0x1800441dc  xor     eax, eax
0x1800441de  jmp     loc_180044A20
0x1800441e3  mov     rax, [rsp+230h+var_1E8]
0x1800441e8  mov     [rsp+230h+var_1D8], rdi
0x1800441ed  mov     rcx, [rax+0F0h]
0x1800441f4  mov     rbx, [rax+0F8h]
0x1800441fb  mov     r12d, [rax+0E0h]
0x180044202  mov     r13d, [rax+0E4h]
0x180044209  mov     r15d, [rax+0E8h]
0x180044210  mov     rax, [rsi]
0x180044213  mov     [rsp+230h+var_1E0], rcx
0x180044218  mov     rcx, rsi
0x18004421b  mov     [rsp+230h+var_1F0], rbx
0x180044220  mov     rax, [rax+20h]
0x180044224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044229  lea     rdx, [rsp+230h+var_1D8]; void **
0x18004422e  mov     rcx, rax; this
0x180044231  call    ?iteratorReset@XmlNodeSet@@QEAAPEAVXmlNode@@PEAPEAX@Z; XmlNodeSet::iteratorReset(void * *)
0x180044236  mov     rsi, rax
0x180044239  test    rax, rax
0x18004423c  jz      loc_180044A1B
0x180044242  mov     rax, [rax]
0x180044245  mov     rcx, rsi
0x180044248  mov     rax, [rax+18h]
0x18004424c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044251  sub     eax, 2
0x180044254  jz      loc_18004479E
0x18004425a  cmp     eax, 1
0x18004425d  jnz     loc_1800448DF
0x180044263  mov     rax, [rsi]
0x180044266  mov     rcx, rsi
0x180044269  mov     rax, [rax+28h]
0x18004426d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044272  mov     rdx, rax
0x180044275  lea     rcx, [rbp+130h+var_168]
0x180044279  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18004427e  mov     rax, [rsi]
0x180044281  mov     rcx, rsi
0x180044284  mov     rax, [rax+30h]
0x180044288  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004428d  mov     rdx, rax
0x180044290  lea     rcx, [rbp+130h+var_1A8]
0x180044294  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180044299  lea     rdx, aType; "type"
0x1800442a0  lea     rcx, [rbp+130h+var_188]
0x1800442a4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800442a9  lea     rdx, [rbp+130h+var_188]
0x1800442ad  lea     rcx, [rbp+130h+var_168]
0x1800442b1  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x1800442b6  xor     r8d, r8d
0x1800442b9  lea     rcx, [rbp+130h+var_188]
0x1800442bd  mov     dl, 1
0x1800442bf  mov     bl, al
0x1800442c1  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800442c6  lea     rcx, [rsp+230h+var_1C8]
0x1800442cb  test    bl, bl
0x1800442cd  jz      loc_1800443DF
0x1800442d3  lea     rdx, aPhysical; "physical"
0x1800442da  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800442df  lea     rdx, [rsp+230h+var_1C8]
0x1800442e4  or      edi, 1
0x1800442e7  lea     rcx, [rbp+130h+var_1A8]
0x1800442eb  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x1800442f0  test    al, al
0x1800442f2  jnz     short loc_18004431C
0x1800442f4  lea     rdx, a0; "0"
0x1800442fb  lea     rcx, [rbp+130h+var_188]
0x1800442ff  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180044304  lea     rdx, [rbp+130h+var_188]
0x180044308  or      edi, 2
0x18004430b  lea     rcx, [rbp+130h+var_1A8]
0x18004430f  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x180044314  test    al, al
0x180044316  jnz     short loc_18004431C
0x180044318  xor     bl, bl
0x18004431a  jmp     short loc_18004431E
0x18004431c  mov     bl, 1
0x18004431e  test    dil, 2
0x180044322  jz      short loc_180044335
0x180044324  and     edi, 0FFFFFFFDh
0x180044327  lea     rcx, [rbp+130h+var_188]
0x18004432b  xor     r8d, r8d
0x18004432e  mov     dl, 1
0x180044330  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180044335  xor     r8d, r8d
0x180044338  lea     rcx, [rsp+230h+var_1C8]
0x18004433d  mov     dl, 1
0x18004433f  and     edi, 0FFFFFFFEh
0x180044342  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180044347  test    bl, bl
0x180044349  jz      short loc_180044353
0x18004434b  xor     r12d, r12d
0x18004434e  jmp     loc_18004478B
0x180044353  lea     rdx, aVirtual; "virtual"
0x18004435a  lea     rcx, [rbp+130h+var_188]
0x18004435e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180044363  lea     rdx, [rbp+130h+var_188]
0x180044367  or      edi, 4
0x18004436a  lea     rcx, [rbp+130h+var_1A8]
0x18004436e  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x180044373  test    al, al
0x180044375  jnz     short loc_1800443A1
0x180044377  lea     rdx, a1; "1"
0x18004437e  lea     rcx, [rsp+230h+var_1C8]
0x180044383  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180044388  lea     rdx, [rsp+230h+var_1C8]
0x18004438d  or      edi, 8
0x180044390  lea     rcx, [rbp+130h+var_1A8]
0x180044394  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x180044399  test    al, al
0x18004439b  jnz     short loc_1800443A1
0x18004439d  xor     bl, bl
0x18004439f  jmp     short loc_1800443A3
0x1800443a1  mov     bl, 1
0x1800443a3  test    dil, 8
0x1800443a7  jz      short loc_1800443BB
0x1800443a9  and     edi, 0FFFFFFF7h
0x1800443ac  lea     rcx, [rsp+230h+var_1C8]
0x1800443b1  xor     r8d, r8d
0x1800443b4  mov     dl, 1
0x1800443b6  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800443bb  xor     r8d, r8d
0x1800443be  lea     rcx, [rbp+130h+var_188]
0x1800443c2  mov     dl, 1
0x1800443c4  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800443c9  test    bl, bl
0x1800443cb  jz      loc_1800448FF
0x1800443d1  and     edi, 0FFFFFFFBh
0x1800443d4  mov     r12d, 1
0x1800443da  jmp     loc_18004478B
0x1800443df  lea     rdx, aProtection; "protection"
0x1800443e6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800443eb  lea     rdx, [rsp+230h+var_1C8]
0x1800443f0  lea     rcx, [rbp+130h+var_168]
0x1800443f4  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x1800443f9  xor     r8d, r8d
0x1800443fc  lea     rcx, [rsp+230h+var_1C8]
0x180044401  mov     dl, 1
0x180044403  mov     bl, al
0x180044405  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18004440a  test    bl, bl
0x18004440c  jz      loc_180044524
0x180044412  lea     rdx, aNone; "none"
0x180044419  lea     rcx, [rbp+130h+var_188]
0x18004441d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180044422  lea     rdx, [rbp+130h+var_188]
0x180044426  or      edi, 10h
0x180044429  lea     rcx, [rbp+130h+var_1A8]
0x18004442d  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x180044432  test    al, al
0x180044434  jnz     short loc_180044460
0x180044436  lea     rdx, a0; "0"
0x18004443d  lea     rcx, [rsp+230h+var_1C8]
0x180044442  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180044447  lea     rdx, [rsp+230h+var_1C8]
0x18004444c  or      edi, 20h
0x18004444f  lea     rcx, [rbp+130h+var_1A8]
0x180044453  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x180044458  test    al, al
0x18004445a  jnz     short loc_180044460
0x18004445c  xor     bl, bl
0x18004445e  jmp     short loc_180044462
0x180044460  mov     bl, 1
0x180044462  test    dil, 20h
0x180044466  jz      short loc_18004447A
0x180044468  and     edi, 0FFFFFFDFh
0x18004446b  lea     rcx, [rsp+230h+var_1C8]
0x180044470  xor     r8d, r8d
0x180044473  mov     dl, 1
0x180044475  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18004447a  xor     r8d, r8d
0x18004447d  lea     rcx, [rbp+130h+var_188]
0x180044481  mov     dl, 1
0x180044483  and     edi, 0FFFFFFEFh
0x180044486  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18004448b  test    bl, bl
0x18004448d  jz      short loc_180044497
0x18004448f  xor     r13d, r13d
0x180044492  jmp     loc_18004478B
0x180044497  lea     rdx, aProcess; "process"
0x18004449e  lea     rcx, [rbp+130h+var_188]
0x1800444a2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800444a7  lea     rdx, [rbp+130h+var_188]
0x1800444ab  or      edi, 40h
0x1800444ae  lea     rcx, [rbp+130h+var_1A8]
0x1800444b2  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x1800444b7  test    al, al
0x1800444b9  jnz     short loc_1800444E6
0x1800444bb  lea     rdx, a1; "1"
0x1800444c2  lea     rcx, [rsp+230h+var_1C8]
0x1800444c7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800444cc  lea     rdx, [rsp+230h+var_1C8]
0x1800444d1  bts     edi, 7
0x1800444d5  lea     rcx, [rbp+130h+var_1A8]
0x1800444d9  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x1800444de  test    al, al
0x1800444e0  jnz     short loc_1800444E6
0x1800444e2  xor     bl, bl
0x1800444e4  jmp     short loc_1800444E8
0x1800444e6  mov     bl, 1
0x1800444e8  test    dil, dil
0x1800444eb  jns     short loc_180044500
0x1800444ed  btr     edi, 7
0x1800444f1  lea     rcx, [rsp+230h+var_1C8]
0x1800444f6  xor     r8d, r8d
0x1800444f9  mov     dl, 1
0x1800444fb  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180044500  xor     r8d, r8d
0x180044503  lea     rcx, [rbp+130h+var_188]
0x180044507  mov     dl, 1
0x180044509  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18004450e  test    bl, bl
0x180044510  jz      loc_180044974
0x180044516  and     edi, 0FFFFFFBFh
0x180044519  mov     r13d, 1
0x18004451f  jmp     loc_18004478B
0x180044524  lea     rdx, aShare; "share"
0x18004452b  lea     rcx, [rsp+230h+var_1C8]
0x180044530  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180044535  lea     rdx, [rsp+230h+var_1C8]
0x18004453a  lea     rcx, [rbp+130h+var_168]
0x18004453e  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x180044543  xor     r8d, r8d
0x180044546  lea     rcx, [rsp+230h+var_1C8]
0x18004454b  mov     dl, 1
0x18004454d  mov     bl, al
0x18004454f  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180044554  test    bl, bl
0x180044556  jz      loc_180044701
0x18004455c  lea     rdx, aEverything; "everything"
0x180044563  lea     rcx, [rbp+130h+var_188]
0x180044567  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18004456c  lea     rdx, [rbp+130h+var_188]
0x180044570  bts     edi, 8
0x180044574  lea     rcx, [rbp+130h+var_1A8]
0x180044578  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x18004457d  test    al, al
0x18004457f  jnz     short loc_1800445AC
0x180044581  lea     rdx, a0; "0"
0x180044588  lea     rcx, [rsp+230h+var_1C8]
0x18004458d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180044592  lea     rdx, [rsp+230h+var_1C8]
0x180044597  bts     edi, 9
0x18004459b  lea     rcx, [rbp+130h+var_1A8]
0x18004459f  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x1800445a4  test    al, al
0x1800445a6  jnz     short loc_1800445AC
0x1800445a8  xor     bl, bl
0x1800445aa  jmp     short loc_1800445AE
0x1800445ac  mov     bl, 1
0x1800445ae  bt      edi, 9
0x1800445b2  jnb     short loc_1800445C7
0x1800445b4  btr     edi, 9
0x1800445b8  lea     rcx, [rsp+230h+var_1C8]
0x1800445bd  xor     r8d, r8d
0x1800445c0  mov     dl, 1
0x1800445c2  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
  ... truncated ...
```
