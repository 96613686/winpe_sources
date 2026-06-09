# ParseIsolationConfigOptionElement(XmlNode *,MitigationOptions *)

- ea: `0x180045044`
- end: `0x1800456a9`
- name: `?ParseIsolationConfigOptionElement@@YAHPEAVXmlNode@@PEAVMitigationOptions@@@Z`
- size: `1637`
- prototype: `__int64 __fastcall(struct XmlNode *, struct MitigationOptions *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180044e54`

## callees

- `0x180016a88`
- `0x1800192a8`
- `0x180042e6c`
- `0x180042e98`
- `0x180045044`
- `0x1800456b0`
- `0x18004741c`
- `0x1800474f8`
- `0x1800475b4`
- `0x180047670`
- `0x180047e10`
- `0x1800480f0`
- `0x1800481e4`
- `0x18004ecbc`
- `0x18004ece0`
- `0x18004fa50`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180045463`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800454e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180045560`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180045463`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800454e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180045560`

## pseudocode

```c
__int64 __fastcall ParseIsolationConfigOptionElement(struct XmlNode *a1, struct MitigationOptions *a2)
{
  struct XmlNode *v4; // r14
  unsigned int v5; // edi
  __int64 v6; // rax
  char v7; // al
  __int64 v8; // rdx
  char v9; // bl
  __int64 v10; // rdx
  __int64 v12; // rax
  bool v13; // r15
  bool v14; // r12
  __int64 (__fastcall *v15)(struct XmlNode *); // rax
  XmlNodeSet *v16; // rax
  struct XmlNode *i; // rax
  int v18; // r8d
  int v19; // r9d
  struct XmlNode *v20; // rsi
  int v21; // eax
  __int64 v22; // rax
  __int64 v23; // rax
  char v24; // al
  __int64 v25; // rdx
  char v26; // bl
  __int64 v27; // rdx
  char v28; // al
  __int64 v29; // rdx
  char v30; // bl
  int v31; // edi
  __int64 v32; // rdx
  char v33; // al
  __int64 v34; // rdx
  char v35; // bl
  int v36; // edi
  __int64 v37; // rdx
  char v38; // al
  __int64 v39; // rdx
  char v40; // bl
  char v41; // al
  __int64 v42; // rdx
  char v43; // bl
  __int64 v44; // rdx
  XmlNodeSet *v45; // rcx
  __int64 v46; // rax
  __int64 v47; // rdx
  __int64 v48; // rdx
  __int64 v49; // rdx
  __int64 v50; // rdx
  __int64 v51; // rdx
  unsigned int v52; // ebx
  __int64 v53; // rax
  char *v54; // rax
  char v55; // cl
  __int64 v56; // rax
  int v57; // ebx
  __int64 v58; // rax
  int v59; // ebx
  __int64 v60; // rdx
  int v61; // [rsp+28h] [rbp-D8h]
  int v62; // [rsp+30h] [rbp-D0h] BYREF
  int v63; // [rsp+34h] [rbp-CCh]
  unsigned int v64; // [rsp+38h] [rbp-C8h]
  void *v65; // [rsp+40h] [rbp-C0h] BYREF
  struct XmlNode *v66; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v67[32]; // [rsp+50h] [rbp-B0h] BYREF
  _WORD v68[8]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v69; // [rsp+80h] [rbp-80h]
  __int64 v70; // [rsp+88h] [rbp-78h]
  _BYTE v71[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v72[32]; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t String[8]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v74; // [rsp+E0h] [rbp-20h]
  __int64 v75; // [rsp+E8h] [rbp-18h]
  _BYTE v76[32]; // [rsp+F0h] [rbp-10h] BYREF

  v66 = a1;
  v4 = 0;
  v5 = 0;
  v62 = 0;
  std::wstring::wstring(v71, L"option");
  v6 = (*(__int64 (__fastcall **)(struct XmlNode *))(*(_QWORD *)a1 + 40LL))(a1);
  std::wstring::wstring(v76, v6);
  v7 = Compare(v76, v71);
  LOBYTE(v8) = 1;
  v9 = v7;
  std::wstring::_Tidy(v76, v8, 0);
  LOBYTE(v10) = 1;
  std::wstring::_Tidy(v71, v10, 0);
  if ( !v9 )
    return 0;
  v12 = *(_QWORD *)a1;
  v70 = 7;
  v13 = 1;
  v75 = 7;
  v14 = 0;
  v69 = 0;
  v15 = *(__int64 (__fastcall **)(struct XmlNode *))(v12 + 32);
  v68[0] = 0;
  v74 = 0;
  String[0] = 0;
  v62 = 0;
  v63 = 0;
  v64 = 0;
  v65 = 0;
  v16 = (XmlNodeSet *)v15(a1);
  for ( i = XmlNodeSet::iteratorReset(v16, &v65); ; i = XmlNodeSet::iteratorNext(v45, &v65) )
  {
    v20 = i;
    if ( !i )
      break;
    v21 = (*(__int64 (__fastcall **)(struct XmlNode *))(*(_QWORD *)i + 24LL))(i) - 2;
    if ( !v21 )
    {
      v61 = (*(__int64 (__fastcall **)(struct XmlNode *))(*(_QWORD *)v20 + 24LL))(v20);
      IsolationPolicy::TelemetryHelper::LogFormatError(1, L"option", &Options, &Options, &Options, v61);
LABEL_34:
      SetLastError(0x57u);
      goto LABEL_32;
    }
    if ( v21 == 1 )
    {
      v22 = (*(__int64 (__fastcall **)(struct XmlNode *))(*(_QWORD *)v20 + 40LL))(v20);
      std::wstring::wstring(v76, v22);
      v23 = (*(__int64 (__fastcall **)(struct XmlNode *))(*(_QWORD *)v20 + 48LL))(v20);
      std::wstring::wstring(v71, v23);
      std::wstring::wstring(v72, L"name");
      v24 = Compare(v76, v72);
      LOBYTE(v25) = 1;
      v26 = v24;
      std::wstring::_Tidy(v72, v25, 0);
      if ( v26 )
      {
        std::wstring::operator=(v68, v71);
      }
      else
      {
        std::wstring::wstring(v72, L"enabled");
        v28 = Compare(v76, v72);
        LOBYTE(v29) = 1;
        v30 = v28;
        std::wstring::_Tidy(v72, v29, 0);
        if ( v30 )
        {
          std::wstring::wstring(v67, L"false");
          v31 = v5 | 1;
          v13 = 0;
          if ( !(unsigned __int8)Compare(v71, v67) )
          {
            std::wstring::wstring(v72, L"0");
            v31 |= 2u;
            if ( !(unsigned __int8)Compare(v71, v72) )
              v13 = 1;
          }
          if ( (v31 & 2) != 0 )
          {
            v31 &= ~2u;
            LOBYTE(v32) = 1;
            std::wstring::_Tidy(v72, v32, 0);
          }
          v5 = v31 & 0xFFFFFFFE;
          LOBYTE(v32) = 1;
          std::wstring::_Tidy(v67, v32, 0);
          v62 = 1;
        }
        else
        {
          std::wstring::wstring(v67, L"audit");
          v33 = Compare(v76, v67);
          LOBYTE(v34) = 1;
          v35 = v33;
          std::wstring::_Tidy(v67, v34, 0);
          if ( v35 )
          {
            std::wstring::wstring(v72, L"false");
            v36 = v5 | 4;
            v14 = 0;
            if ( !(unsigned __int8)Compare(v71, v72) )
            {
              std::wstring::wstring(v67, L"0");
              v36 |= 8u;
              if ( !(unsigned __int8)Compare(v71, v67) )
                v14 = 1;
            }
            if ( (v36 & 8) != 0 )
            {
              v36 &= ~8u;
              LOBYTE(v37) = 1;
              std::wstring::_Tidy(v67, v37, 0);
            }
            v5 = v36 & 0xFFFFFFFB;
            LOBYTE(v37) = 1;
            std::wstring::_Tidy(v72, v37, 0);
            v63 = 1;
          }
          else
          {
            std::wstring::wstring(v67, L"data");
            v38 = Compare(v76, v67);
            LOBYTE(v39) = 1;
            v40 = v38;
            std::wstring::_Tidy(v67, v39, 0);
            if ( v40 )
            {
              std::wstring::operator=(String, v71);
              v64 = 1;
            }
            else
            {
              std::wstring::wstring(v67, L"selector");
              v41 = Compare(v76, v67);
              LOBYTE(v42) = 1;
              v43 = v41;
              std::wstring::_Tidy(v67, v42, 0);
              if ( !v43 )
              {
                v46 = (*(__int64 (__fastcall **)(struct XmlNode *))(*(_QWORD *)v20 + 40LL))(v20);
                IsolationPolicy::TelemetryHelper::LogFormatError(3, L"option", v46, &Options, &Options, 0);
                SetLastError(0x57u);
                LOBYTE(v47) = 1;
                std::wstring::_Tidy(v71, v47, 0);
                LOBYTE(v48) = 1;
                std::wstring::_Tidy(v76, v48, 0);
LABEL_32:
                LOBYTE(v49) = 1;
                std::wstring::_Tidy(String, v49, 0);
                LOBYTE(v50) = 1;
                std::wstring::_Tidy(v68, v50, 0);
                return 0;
              }
              v4 = (struct XmlNode *)ToUint64(v71);
            }
          }
        }
      }
      LOBYTE(v27) = 1;
      std::wstring::_Tidy(v71, v27, 0);
      LOBYTE(v44) = 1;
      std::wstring::_Tidy(v76, v44, 0);
    }
    (*(void (__fastcall **)(struct XmlNode *))(*(_QWORD *)v66 + 32LL))(v66);
  }
  if ( !v69 )
  {
    IsolationPolicy::TelemetryHelper::LogFormatError(5, &Options, L"option", L"name", &Options, 0);
    goto LABEL_34;
  }
  v51 = v64;
  if ( v62 + v64 + v63 <= 1 )
  {
    if ( v62 == 1 )
    {
      v66 = v4;
      v62 = MitigationOptionNames::Lookup(v68);
      if ( v62 == -1 )
        goto LABEL_52;
      v53 = std::unordered_map<enum OptionIds,std::unordered_map<unsigned __int64,unsigned char>>::operator[](a2, &v62);
      v54 = (char *)std::unordered_map<unsigned __int64,unsigned char>::operator[](v53, &v66);
      v55 = v13 ? 4 : 18;
    }
    else
    {
      if ( v63 != 1 )
      {
        if ( v64 == 1 )
        {
          v65 = v4;
          v62 = MitigationOptionNames::Lookup(v68);
          v57 = v62;
          if ( v62 != -1 )
          {
            v58 = std::unordered_map<enum OptionIds,std::unordered_map<unsigned __int64,unsigned char>>::operator[](
                    a2,
                    &v62);
            *(_BYTE *)std::unordered_map<unsigned __int64,unsigned char>::operator[](v58, &v65) = 17;
            if ( v74 )
            {
              if ( v57 == 37 )
              {
                v59 = std::stoul(String);
                *(_DWORD *)std::unordered_map<unsigned __int64,unsigned long>::operator[]((char *)a2 + 64, &v65) = v59;
              }
            }
          }
        }
        goto LABEL_52;
      }
      v66 = v4;
      v62 = MitigationOptionNames::Lookup(v68);
      if ( v62 == -1 )
      {
LABEL_52:
        v52 = 1;
        goto LABEL_53;
      }
      v56 = std::unordered_map<enum OptionIds,std::unordered_map<unsigned __int64,unsigned char>>::operator[](a2, &v62);
      v54 = (char *)std::unordered_map<unsigned __int64,unsigned char>::operator[](v56, &v66);
      v55 = v14 ? 97 : 33;
    }
    *v54 = v55;
    goto LABEL_52;
  }
  LOBYTE(v19) = v14;
  LOBYTE(v18) = v13;
  if ( (unsigned __int8)MitigationOptions::AddOption((_DWORD)a2, (unsigned int)v68, v18, v19, (char)v4, String) )
    goto LABEL_52;
  SetLastError(0x57u);
  v52 = 0;
LABEL_53:
  LOBYTE(v51) = 1;
  std::wstring::_Tidy(String, v51, 0);
  LOBYTE(v60) = 1;
  std::wstring::_Tidy(v68, v60, 0);
  return v52;
}

```

## disassembly

```asm
0x180045044  mov     [rsp-8+arg_10], rbx
0x180045049  push    rbp
0x18004504a  push    rsi
0x18004504b  push    rdi
0x18004504c  push    r12
0x18004504e  push    r13
0x180045050  push    r14
0x180045052  push    r15
0x180045054  lea     rbp, [rsp-20h]
0x180045059  sub     rsp, 120h
0x180045060  mov     rax, cs:__security_cookie
0x180045067  xor     rax, rsp
0x18004506a  mov     [rbp+50h+var_40], rax
0x18004506e  mov     r13, rdx
0x180045071  mov     [rsp+150h+var_108], rcx
0x180045076  mov     rsi, rcx
0x180045079  lea     rdx, aOption; "option"
0x180045080  xor     r14d, r14d
0x180045083  lea     rcx, [rbp+50h+var_C0]
0x180045087  mov     edi, r14d
0x18004508a  mov     [rsp+150h+var_120], r14d
0x18004508f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180045094  mov     rax, [rsi]
0x180045097  mov     rcx, rsi
0x18004509a  mov     rax, [rax+28h]
0x18004509e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800450a3  mov     rdx, rax
0x1800450a6  lea     rcx, [rbp+50h+var_60]
0x1800450aa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800450af  lea     rdx, [rbp+50h+var_C0]
0x1800450b3  lea     rcx, [rbp+50h+var_60]
0x1800450b7  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x1800450bc  xor     r8d, r8d
0x1800450bf  lea     rcx, [rbp+50h+var_60]
0x1800450c3  mov     dl, 1
0x1800450c5  mov     bl, al
0x1800450c7  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800450cc  xor     r8d, r8d
0x1800450cf  lea     rcx, [rbp+50h+var_C0]
0x1800450d3  mov     dl, 1
0x1800450d5  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800450da  test    bl, bl
0x1800450dc  jnz     short loc_1800450E5
0x1800450de  xor     eax, eax
0x1800450e0  jmp     loc_180045682
0x1800450e5  mov     rax, [rsi]
0x1800450e8  mov     ecx, 7
0x1800450ed  mov     [rbp+50h+var_C8], rcx
0x1800450f1  mov     r15b, 1
0x1800450f4  mov     [rbp+50h+var_68], rcx
0x1800450f8  mov     r12b, r14b
0x1800450fb  mov     rcx, rsi
0x1800450fe  mov     [rbp+50h+var_D0], r14
0x180045102  mov     rax, [rax+20h]
0x180045106  mov     [rsp+150h+var_E0], r14w
0x18004510c  mov     [rbp+50h+var_70], r14
0x180045110  mov     [rbp+50h+String], r14w
0x180045115  mov     [rsp+150h+var_120], r14d
0x18004511a  mov     [rsp+150h+var_11C], r14d
0x18004511f  mov     [rsp+150h+var_118], r14d
0x180045124  mov     [rsp+150h+var_110], rdi
0x180045129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004512e  lea     rdx, [rsp+150h+var_110]; void **
0x180045133  mov     rcx, rax; this
0x180045136  call    ?iteratorReset@XmlNodeSet@@QEAAPEAVXmlNode@@PEAPEAX@Z; XmlNodeSet::iteratorReset(void * *)
0x18004513b  mov     rsi, rax
0x18004513e  test    rax, rax
0x180045141  jz      loc_1800454EA
0x180045147  mov     rcx, [rax]
0x18004514a  mov     rax, [rcx+18h]
0x18004514e  mov     rcx, rsi
0x180045151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045156  sub     eax, 2
0x180045159  jz      loc_1800454A7
0x18004515f  cmp     eax, 1
0x180045162  jnz     loc_180045401
0x180045168  mov     rax, [rsi]
0x18004516b  mov     rcx, rsi
0x18004516e  mov     rax, [rax+28h]
0x180045172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045177  mov     rdx, rax
0x18004517a  lea     rcx, [rbp+50h+var_60]
0x18004517e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180045183  mov     rax, [rsi]
0x180045186  mov     rcx, rsi
0x180045189  mov     rax, [rax+30h]
0x18004518d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045192  mov     rdx, rax
0x180045195  lea     rcx, [rbp+50h+var_C0]
0x180045199  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18004519e  lea     rdx, aName_0; "name"
0x1800451a5  lea     rcx, [rbp+50h+var_A0]
0x1800451a9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800451ae  lea     rdx, [rbp+50h+var_A0]
0x1800451b2  lea     rcx, [rbp+50h+var_60]
0x1800451b6  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x1800451bb  xor     r8d, r8d
0x1800451be  lea     rcx, [rbp+50h+var_A0]
0x1800451c2  mov     dl, 1
0x1800451c4  mov     bl, al
0x1800451c6  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800451cb  test    bl, bl
0x1800451cd  jz      short loc_1800451E2
0x1800451cf  lea     rdx, [rbp+50h+var_C0]
0x1800451d3  lea     rcx, [rsp+150h+var_E0]
0x1800451d8  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800451dd  jmp     loc_1800453E5
0x1800451e2  lea     rdx, aEnabled; "enabled"
0x1800451e9  lea     rcx, [rbp+50h+var_A0]
0x1800451ed  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800451f2  lea     rdx, [rbp+50h+var_A0]
0x1800451f6  lea     rcx, [rbp+50h+var_60]
0x1800451fa  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x1800451ff  xor     r8d, r8d
0x180045202  lea     rcx, [rbp+50h+var_A0]
0x180045206  mov     dl, 1
0x180045208  mov     bl, al
0x18004520a  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18004520f  lea     rcx, [rsp+150h+var_100]
0x180045214  test    bl, bl
0x180045216  jz      loc_18004529F
0x18004521c  lea     rdx, aFalse; "false"
0x180045223  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180045228  lea     rdx, [rsp+150h+var_100]
0x18004522d  or      edi, 1
0x180045230  lea     rcx, [rbp+50h+var_C0]
0x180045234  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x180045239  test    al, al
0x18004523b  jnz     short loc_180045266
0x18004523d  lea     rdx, a0; "0"
0x180045244  lea     rcx, [rbp+50h+var_A0]
0x180045248  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18004524d  lea     rdx, [rbp+50h+var_A0]
0x180045251  or      edi, 2
0x180045254  lea     rcx, [rbp+50h+var_C0]
0x180045258  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x18004525d  test    al, al
0x18004525f  jnz     short loc_180045266
0x180045261  mov     r15b, 1
0x180045264  jmp     short loc_180045269
0x180045266  xor     r15b, r15b
0x180045269  test    dil, 2
0x18004526d  jz      short loc_180045280
0x18004526f  and     edi, 0FFFFFFFDh
0x180045272  lea     rcx, [rbp+50h+var_A0]
0x180045276  xor     r8d, r8d
0x180045279  mov     dl, 1
0x18004527b  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180045280  and     edi, 0FFFFFFFEh
0x180045283  lea     rcx, [rsp+150h+var_100]
0x180045288  xor     r8d, r8d
0x18004528b  mov     dl, 1
0x18004528d  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180045292  mov     [rsp+150h+var_120], 1
0x18004529a  jmp     loc_1800453E5
0x18004529f  lea     rdx, aAudit; "audit"
0x1800452a6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800452ab  lea     rdx, [rsp+150h+var_100]
0x1800452b0  lea     rcx, [rbp+50h+var_60]
0x1800452b4  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x1800452b9  xor     r8d, r8d
0x1800452bc  lea     rcx, [rsp+150h+var_100]
0x1800452c1  mov     dl, 1
0x1800452c3  mov     bl, al
0x1800452c5  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800452ca  test    bl, bl
0x1800452cc  jz      loc_18004535A
0x1800452d2  lea     rdx, aFalse; "false"
0x1800452d9  lea     rcx, [rbp+50h+var_A0]
0x1800452dd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800452e2  lea     rdx, [rbp+50h+var_A0]
0x1800452e6  or      edi, 4
0x1800452e9  lea     rcx, [rbp+50h+var_C0]
0x1800452ed  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x1800452f2  test    al, al
0x1800452f4  jnz     short loc_180045321
0x1800452f6  lea     rdx, a0; "0"
0x1800452fd  lea     rcx, [rsp+150h+var_100]
0x180045302  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180045307  lea     rdx, [rsp+150h+var_100]
0x18004530c  or      edi, 8
0x18004530f  lea     rcx, [rbp+50h+var_C0]
0x180045313  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x180045318  test    al, al
0x18004531a  jnz     short loc_180045321
0x18004531c  mov     r12b, 1
0x18004531f  jmp     short loc_180045324
0x180045321  xor     r12b, r12b
0x180045324  test    dil, 8
0x180045328  jz      short loc_18004533C
0x18004532a  and     edi, 0FFFFFFF7h
0x18004532d  lea     rcx, [rsp+150h+var_100]
0x180045332  xor     r8d, r8d
0x180045335  mov     dl, 1
0x180045337  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18004533c  and     edi, 0FFFFFFFBh
0x18004533f  lea     rcx, [rbp+50h+var_A0]
0x180045343  xor     r8d, r8d
0x180045346  mov     dl, 1
0x180045348  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18004534d  mov     [rsp+150h+var_11C], 1
0x180045355  jmp     loc_1800453E5
0x18004535a  lea     rdx, aData; "data"
0x180045361  lea     rcx, [rsp+150h+var_100]
0x180045366  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18004536b  lea     rdx, [rsp+150h+var_100]
0x180045370  lea     rcx, [rbp+50h+var_60]
0x180045374  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x180045379  xor     r8d, r8d
0x18004537c  lea     rcx, [rsp+150h+var_100]
0x180045381  mov     dl, 1
0x180045383  mov     bl, al
0x180045385  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18004538a  test    bl, bl
0x18004538c  jz      short loc_1800453A5
0x18004538e  lea     rdx, [rbp+50h+var_C0]
0x180045392  lea     rcx, [rbp+50h+String]
0x180045396  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18004539b  mov     [rsp+150h+var_118], 1
0x1800453a3  jmp     short loc_1800453E5
0x1800453a5  lea     rdx, aSelector; "selector"
0x1800453ac  lea     rcx, [rsp+150h+var_100]
0x1800453b1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800453b6  lea     rdx, [rsp+150h+var_100]
0x1800453bb  lea     rcx, [rbp+50h+var_60]
0x1800453bf  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x1800453c4  xor     r8d, r8d
0x1800453c7  lea     rcx, [rsp+150h+var_100]
0x1800453cc  mov     dl, 1
0x1800453ce  mov     bl, al
0x1800453d0  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800453d5  test    bl, bl
0x1800453d7  jz      short loc_180045424
0x1800453d9  lea     rcx, [rbp+50h+var_C0]
0x1800453dd  call    ?ToUint64@@YA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ToUint64(std::wstring const &)
0x1800453e2  mov     r14, rax
0x1800453e5  xor     r8d, r8d
0x1800453e8  lea     rcx, [rbp+50h+var_C0]
0x1800453ec  mov     dl, 1
0x1800453ee  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800453f3  xor     r8d, r8d
0x1800453f6  lea     rcx, [rbp+50h+var_60]
0x1800453fa  mov     dl, 1
0x1800453fc  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180045401  mov     rdx, [rsp+150h+var_108]
0x180045406  mov     rcx, [rdx]
0x180045409  mov     rax, [rcx+20h]
0x18004540d  mov     rcx, rdx
0x180045410  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045415  lea     rdx, [rsp+150h+var_110]; void **
0x18004541a  call    ?iteratorNext@XmlNodeSet@@QEAAPEAVXmlNode@@PEAPEAX@Z; XmlNodeSet::iteratorNext(void * *)
0x18004541f  jmp     loc_18004513B
0x180045424  mov     rax, [rsi]
0x180045427  mov     rcx, rsi
0x18004542a  mov     rax, [rax+28h]
0x18004542e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045433  lea     rdx, Options
0x18004543a  mov     dword ptr [rsp+150h+var_128], 0
0x180045442  mov     [rsp+150h+var_130], rdx
0x180045447  mov     r9, rdx
0x18004544a  lea     rdx, aOption; "option"
0x180045451  mov     r8, rax
0x180045454  mov     ecx, 3
0x180045459  call    ?LogFormatError@TelemetryHelper@IsolationPolicy@@CAXW4ParseOperation@2@PEBG111W4_XML_TYPE@@@Z; IsolationPolicy::TelemetryHelper::LogFormatError(IsolationPolicy::ParseOperation,ushort const *,ushort const *,ushort const *,ushort const *,_XML_TYPE)
0x18004545e  mov     ecx, 57h ; 'W'; dwErrCode
0x180045463  call    cs:__imp_SetLastError
0x180045469  xor     r8d, r8d
0x18004546c  lea     rcx, [rbp+50h+var_C0]
0x180045470  mov     dl, 1
0x180045472  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180045477  xor     r8d, r8d
0x18004547a  lea     rcx, [rbp+50h+var_60]
0x18004547e  mov     dl, 1
0x180045480  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180045485  xor     r8d, r8d
0x180045488  lea     rcx, [rbp+50h+String]
0x18004548c  mov     dl, 1
0x18004548e  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180045493  xor     r8d, r8d
0x180045496  lea     rcx, [rsp+150h+var_E0]
0x18004549b  mov     dl, 1
0x18004549d  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800454a2  jmp     loc_1800450DE
0x1800454a7  mov     rax, [rsi]
0x1800454aa  mov     rcx, rsi
0x1800454ad  mov     rax, [rax+18h]
0x1800454b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800454b6  lea     rdx, Options
0x1800454bd  mov     dword ptr [rsp+150h+var_128], eax
0x1800454c1  mov     [rsp+150h+var_130], rdx
0x1800454c6  mov     r9, rdx
0x1800454c9  mov     r8, rdx
0x1800454cc  mov     ecx, 1
0x1800454d1  lea     rdx, aOption; "option"
0x1800454d8  call    ?LogFormatError@TelemetryHelper@IsolationPolicy@@CAXW4ParseOperation@2@PEBG111W4_XML_TYPE@@@Z; IsolationPolicy::TelemetryHelper::LogFormatError(IsolationPolicy::ParseOperation,ushort const *,ushort const *,ushort const *,ushort const *,_XML_TYPE)
0x1800454dd  mov     ecx, 57h ; 'W'; dwErrCode
0x1800454e2  call    cs:__imp_SetLastError
0x1800454e8  jmp     short loc_180045485
0x1800454ea  cmp     [rbp+50h+var_D0], 0
0x1800454ef  jnz     short loc_18004551A
  ... truncated ...
```
