# ParseIsolationConfigCapabilityElement(XmlNode *,bool,unsigned __int64 *,Capability *)

- ea: `0x180043010`
- end: `0x180043454`
- name: `?ParseIsolationConfigCapabilityElement@@YAHPEAVXmlNode@@_NPEA_KPEAVCapability@@@Z`
- size: `1092`
- prototype: `__int64 __fastcall(struct XmlNode *, bool, unsigned __int64 *, struct Capability *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004345c`

## callees

- `0x180016a88`
- `0x1800192a8`
- `0x180042e6c`
- `0x180042e98`
- `0x180043010`
- `0x1800456b0`
- `0x1800480f0`
- `0x18004ecbc`
- `0x18004ece0`
- `0x18004fa50`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800432fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004338c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800433d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800432fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004338c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800433d3`

## string_xrefs

- `0x1800433b1`: `name or sid`

## pseudocode

```c
__int64 __fastcall ParseIsolationConfigCapabilityElement(
        struct XmlNode *a1,
        __int64 a2,
        unsigned __int64 *a3,
        struct Capability *a4)
{
  int v5; // r15d
  __int64 v8; // rax
  char v9; // al
  __int64 v10; // rdx
  char v11; // bl
  __int64 v12; // rdx
  __int64 result; // rax
  __int64 v14; // rax
  __int64 (__fastcall *v15)(struct XmlNode *); // rax
  XmlNodeSet *v16; // rax
  struct XmlNode *i; // rax
  struct XmlNode *v18; // rdi
  int v19; // eax
  __int64 v20; // rax
  __int64 v21; // rax
  char v22; // al
  __int64 v23; // rdx
  char v24; // bl
  _WORD *v25; // rcx
  char v26; // al
  __int64 v27; // rdx
  char v28; // bl
  char v29; // al
  __int64 v30; // rdx
  char v31; // bl
  __int64 v32; // rdx
  __int64 v33; // rdx
  char v34; // al
  __int64 v35; // rdx
  char v36; // bl
  __int64 v37; // rdx
  XmlNodeSet *v38; // rcx
  __int64 v39; // rax
  __int64 v40; // rdx
  __int64 v41; // rdx
  __int64 v42; // rdx
  __int64 v43; // rdx
  __int64 v44; // rdx
  int v45; // eax
  __int64 v46; // rdx
  unsigned int v47; // ebx
  __int64 v48; // rdx
  __int64 v49; // rdx
  void *v50; // [rsp+30h] [rbp-A9h] BYREF
  _BYTE v51[32]; // [rsp+38h] [rbp-A1h] BYREF
  _WORD v52[8]; // [rsp+58h] [rbp-81h] BYREF
  __int64 v53; // [rsp+68h] [rbp-71h]
  __int64 v54; // [rsp+70h] [rbp-69h]
  _BYTE v55[32]; // [rsp+78h] [rbp-61h] BYREF
  _WORD v56[8]; // [rsp+98h] [rbp-41h] BYREF
  __int64 v57; // [rsp+A8h] [rbp-31h]
  __int64 v58; // [rsp+B0h] [rbp-29h]
  _WORD v59[8]; // [rsp+B8h] [rbp-21h] BYREF
  __int64 v60; // [rsp+C8h] [rbp-11h]
  __int64 v61; // [rsp+D0h] [rbp-9h]
  _BYTE v62[32]; // [rsp+D8h] [rbp-1h] BYREF

  v5 = 0;
  LODWORD(v50) = 0;
  std::wstring::wstring(v52, L"capability");
  v8 = (*(__int64 (__fastcall **)(struct XmlNode *))(*(_QWORD *)a1 + 40LL))(a1);
  std::wstring::wstring(v55, v8);
  v9 = Compare(v55, v52);
  LOBYTE(v10) = 1;
  v11 = v9;
  std::wstring::_Tidy(v55, v10, 0);
  LOBYTE(v12) = 1;
  std::wstring::_Tidy(v52, v12, 0);
  result = 0;
  if ( !v11 )
    return result;
  v59[0] = 0;
  v53 = 0;
  v52[0] = 0;
  v57 = 0;
  v56[0] = 0;
  v50 = 0;
  *a3 = 0;
  v14 = *(_QWORD *)a1;
  v61 = 7;
  v54 = 7;
  v58 = 7;
  v15 = *(__int64 (__fastcall **)(struct XmlNode *))(v14 + 32);
  v60 = 0;
  v16 = (XmlNodeSet *)v15(a1);
  for ( i = XmlNodeSet::iteratorReset(v16, &v50); ; i = XmlNodeSet::iteratorNext(v38, &v50) )
  {
    v18 = i;
    if ( !i )
      break;
    v19 = (*(__int64 (__fastcall **)(struct XmlNode *))(*(_QWORD *)i + 24LL))(i) - 2;
    if ( !v19 )
    {
      v45 = (*(__int64 (__fastcall **)(struct XmlNode *))(*(_QWORD *)v18 + 24LL))(v18);
      IsolationPolicy::TelemetryHelper::LogFormatError(1, L"consumes\\capability", &Options, &Options, &Options, v45);
      SetLastError(0x57u);
      goto LABEL_18;
    }
    if ( v19 == 1 )
    {
      v20 = (*(__int64 (__fastcall **)(struct XmlNode *))(*(_QWORD *)v18 + 40LL))(v18);
      std::wstring::wstring(v62, v20);
      v21 = (*(__int64 (__fastcall **)(struct XmlNode *))(*(_QWORD *)v18 + 48LL))(v18);
      std::wstring::wstring(v55, v21);
      std::wstring::wstring(v51, L"name");
      v22 = Compare(v62, v51);
      LOBYTE(v23) = 1;
      v24 = v22;
      std::wstring::_Tidy(v51, v23, 0);
      if ( v24 )
      {
        v25 = v59;
        goto LABEL_12;
      }
      std::wstring::wstring(v51, L"namespace");
      v26 = Compare(v62, v51);
      LOBYTE(v27) = 1;
      v28 = v26;
      std::wstring::_Tidy(v51, v27, 0);
      if ( v28 )
      {
        v25 = v52;
        goto LABEL_12;
      }
      std::wstring::wstring(v51, L"sid");
      v29 = Compare(v62, v51);
      LOBYTE(v30) = 1;
      v31 = v29;
      std::wstring::_Tidy(v51, v30, 0);
      if ( v31 )
      {
        v25 = v56;
LABEL_12:
        std::wstring::operator=(v25, v55);
      }
      else
      {
        std::wstring::wstring(v51, L"protection");
        Compare(v62, v51);
        LOBYTE(v33) = 1;
        std::wstring::_Tidy(v51, v33, 0);
        std::wstring::wstring(v51, L"selector");
        v34 = Compare(v62, v51);
        LOBYTE(v35) = 1;
        v36 = v34;
        std::wstring::_Tidy(v51, v35, 0);
        if ( !v36 )
        {
          v39 = (*(__int64 (__fastcall **)(struct XmlNode *))(*(_QWORD *)v18 + 40LL))(v18);
          IsolationPolicy::TelemetryHelper::LogFormatError(3, L"consumes\\capability", v39, &Options, &Options, 0);
          SetLastError(0x57u);
          LOBYTE(v40) = 1;
          std::wstring::_Tidy(v55, v40, 0);
          LOBYTE(v41) = 1;
          std::wstring::_Tidy(v62, v41, 0);
LABEL_18:
          LOBYTE(v42) = 1;
          std::wstring::_Tidy(v56, v42, 0);
          LOBYTE(v43) = 1;
          std::wstring::_Tidy(v52, v43, 0);
          LOBYTE(v44) = 1;
          std::wstring::_Tidy(v59, v44, 0);
          return 0;
        }
        v5 &= ~1u;
        *a3 = ToUint64(v55);
      }
      LOBYTE(v32) = 1;
      std::wstring::_Tidy(v55, v32, 0);
      LOBYTE(v37) = 1;
      std::wstring::_Tidy(v62, v37, 0);
    }
    (*(void (__fastcall **)(struct XmlNode *))(*(_QWORD *)a1 + 32LL))(a1);
  }
  if ( v60 || v57 )
  {
    std::wstring::operator=(a4, v59);
    std::wstring::operator=((char *)a4 + 32, v56);
    std::wstring::operator=((char *)a4 + 64, v52);
    v47 = 1;
  }
  else
  {
    IsolationPolicy::TelemetryHelper::LogFormatError(5, &Options, L"consumes\\capability", L"name or sid", &Options, 0);
    SetLastError(0x57u);
    v47 = 0;
  }
  LOBYTE(v46) = 1;
  std::wstring::_Tidy(v56, v46, 0);
  LOBYTE(v48) = 1;
  std::wstring::_Tidy(v52, v48, 0);
  LOBYTE(v49) = 1;
  std::wstring::_Tidy(v59, v49, 0);
  return v47;
}

```

## disassembly

```asm
0x180043010  push    rbp
0x180043012  push    rbx
0x180043013  push    rsi
0x180043014  push    rdi
0x180043015  push    r12
0x180043017  push    r14
0x180043019  push    r15
0x18004301b  lea     rbp, [rsp-27h]
0x180043020  sub     rsp, 100h
0x180043027  mov     rax, cs:__security_cookie
0x18004302e  xor     rax, rsp
0x180043031  mov     [rbp+57h+var_38], rax
0x180043035  mov     rsi, rcx
0x180043038  lea     rdx, aCapability; "capability"
0x18004303f  xor     r15d, r15d
0x180043042  lea     rcx, [rsp+130h+var_D8]
0x180043047  mov     dword ptr [rsp+130h+var_100], r15d
0x18004304c  mov     r14, r9
0x18004304f  mov     r12, r8
0x180043052  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180043057  mov     rax, [rsi]
0x18004305a  mov     rcx, rsi
0x18004305d  mov     rax, [rax+28h]
0x180043061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043066  mov     rdx, rax
0x180043069  lea     rcx, [rbp+57h+var_B8]
0x18004306d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180043072  lea     rdx, [rsp+130h+var_D8]
0x180043077  lea     rcx, [rbp+57h+var_B8]
0x18004307b  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x180043080  xor     r8d, r8d
0x180043083  lea     rcx, [rbp+57h+var_B8]
0x180043087  mov     dl, 1
0x180043089  mov     bl, al
0x18004308b  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180043090  xor     r8d, r8d
0x180043093  lea     rcx, [rsp+130h+var_D8]
0x180043098  mov     dl, 1
0x18004309a  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18004309f  xor     eax, eax
0x1800430a1  test    bl, bl
0x1800430a3  jz      loc_180043436
0x1800430a9  lea     ecx, [rax+7]
0x1800430ac  mov     [rbp+57h+var_78], ax
0x1800430b0  mov     [rbp+57h+var_C8], rax
0x1800430b4  mov     [rsp+130h+var_D8], ax
0x1800430b9  mov     [rbp+57h+var_88], rax
0x1800430bd  mov     [rbp+57h+var_98], ax
0x1800430c1  mov     [rsp+130h+var_100], rax
0x1800430c6  mov     [r12], r15
0x1800430ca  mov     rax, [rsi]
0x1800430cd  mov     [rbp+57h+var_60], rcx
0x1800430d1  mov     [rbp+57h+var_C0], rcx
0x1800430d5  mov     [rbp+57h+var_80], rcx
0x1800430d9  mov     rcx, rsi
0x1800430dc  mov     rax, [rax+20h]
0x1800430e0  mov     [rbp+57h+var_68], r15
0x1800430e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800430e9  lea     rdx, [rsp+130h+var_100]; void **
0x1800430ee  mov     rcx, rax; this
0x1800430f1  call    ?iteratorReset@XmlNodeSet@@QEAAPEAVXmlNode@@PEAPEAX@Z; XmlNodeSet::iteratorReset(void * *)
0x1800430f6  mov     rdi, rax
0x1800430f9  test    rax, rax
0x1800430fc  jz      loc_180043394
0x180043102  mov     rcx, [rax]
0x180043105  mov     rax, [rcx+18h]
0x180043109  mov     rcx, rdi
0x18004310c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043111  sub     eax, 2
0x180043114  jz      loc_180043351
0x18004311a  cmp     eax, 1
0x18004311d  jnz     loc_1800432A0
0x180043123  mov     rax, [rdi]
0x180043126  mov     rcx, rdi
0x180043129  mov     rax, [rax+28h]
0x18004312d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043132  mov     rdx, rax
0x180043135  lea     rcx, [rbp+57h+var_58]
0x180043139  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18004313e  mov     rax, [rdi]
0x180043141  mov     rcx, rdi
0x180043144  mov     rax, [rax+30h]
0x180043148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004314d  mov     rdx, rax
0x180043150  lea     rcx, [rbp+57h+var_B8]
0x180043154  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180043159  lea     rdx, aName_0; "name"
0x180043160  lea     rcx, [rsp+130h+var_F8]
0x180043165  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18004316a  lea     rdx, [rsp+130h+var_F8]
0x18004316f  lea     rcx, [rbp+57h+var_58]
0x180043173  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x180043178  xor     r8d, r8d
0x18004317b  lea     rcx, [rsp+130h+var_F8]
0x180043180  mov     dl, 1
0x180043182  mov     bl, al
0x180043184  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180043189  test    bl, bl
0x18004318b  jz      short loc_180043193
0x18004318d  lea     rcx, [rbp+57h+var_78]
0x180043191  jmp     short loc_180043206
0x180043193  lea     rdx, aNamespace; "namespace"
0x18004319a  lea     rcx, [rsp+130h+var_F8]
0x18004319f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800431a4  lea     rdx, [rsp+130h+var_F8]
0x1800431a9  lea     rcx, [rbp+57h+var_58]
0x1800431ad  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x1800431b2  xor     r8d, r8d
0x1800431b5  lea     rcx, [rsp+130h+var_F8]
0x1800431ba  mov     dl, 1
0x1800431bc  mov     bl, al
0x1800431be  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800431c3  test    bl, bl
0x1800431c5  jz      short loc_1800431CE
0x1800431c7  lea     rcx, [rsp+130h+var_D8]
0x1800431cc  jmp     short loc_180043206
0x1800431ce  lea     rdx, aSid; "sid"
0x1800431d5  lea     rcx, [rsp+130h+var_F8]
0x1800431da  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800431df  lea     rdx, [rsp+130h+var_F8]
0x1800431e4  lea     rcx, [rbp+57h+var_58]
0x1800431e8  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x1800431ed  xor     r8d, r8d
0x1800431f0  lea     rcx, [rsp+130h+var_F8]
0x1800431f5  mov     dl, 1
0x1800431f7  mov     bl, al
0x1800431f9  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800431fe  test    bl, bl
0x180043200  jz      short loc_180043211
0x180043202  lea     rcx, [rbp+57h+var_98]
0x180043206  lea     rdx, [rbp+57h+var_B8]
0x18004320a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18004320f  jmp     short loc_180043284
0x180043211  lea     rdx, aProtection; "protection"
0x180043218  lea     rcx, [rsp+130h+var_F8]
0x18004321d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180043222  lea     rdx, [rsp+130h+var_F8]
0x180043227  lea     rcx, [rbp+57h+var_58]
0x18004322b  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x180043230  xor     r8d, r8d
0x180043233  lea     rcx, [rsp+130h+var_F8]
0x180043238  mov     dl, 1
0x18004323a  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18004323f  lea     rdx, aSelector; "selector"
0x180043246  lea     rcx, [rsp+130h+var_F8]
0x18004324b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180043250  lea     rdx, [rsp+130h+var_F8]
0x180043255  lea     rcx, [rbp+57h+var_58]
0x180043259  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x18004325e  xor     r8d, r8d
0x180043261  lea     rcx, [rsp+130h+var_F8]
0x180043266  mov     dl, 1
0x180043268  mov     bl, al
0x18004326a  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18004326f  test    bl, bl
0x180043271  jz      short loc_1800432BE
0x180043273  and     r15d, 0FFFFFFFEh
0x180043277  lea     rcx, [rbp+57h+var_B8]
0x18004327b  call    ?ToUint64@@YA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ToUint64(std::wstring const &)
0x180043280  mov     [r12], rax
0x180043284  xor     r8d, r8d
0x180043287  lea     rcx, [rbp+57h+var_B8]
0x18004328b  mov     dl, 1
0x18004328d  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180043292  xor     r8d, r8d
0x180043295  lea     rcx, [rbp+57h+var_58]
0x180043299  mov     dl, 1
0x18004329b  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800432a0  mov     rax, [rsi]
0x1800432a3  mov     rcx, rsi
0x1800432a6  mov     rax, [rax+20h]
0x1800432aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800432af  lea     rdx, [rsp+130h+var_100]; void **
0x1800432b4  call    ?iteratorNext@XmlNodeSet@@QEAAPEAVXmlNode@@PEAPEAX@Z; XmlNodeSet::iteratorNext(void * *)
0x1800432b9  jmp     loc_1800430F6
0x1800432be  mov     rax, [rdi]
0x1800432c1  mov     rcx, rdi
0x1800432c4  mov     rax, [rax+28h]
0x1800432c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800432cd  lea     rdx, Options
0x1800432d4  mov     [rsp+130h+var_108], 0
0x1800432dc  mov     [rsp+130h+var_110], rdx
0x1800432e1  mov     r9, rdx
0x1800432e4  lea     rdx, aConsumesCapabi; "consumes\\capability"
0x1800432eb  mov     r8, rax
0x1800432ee  mov     ecx, 3
0x1800432f3  call    ?LogFormatError@TelemetryHelper@IsolationPolicy@@CAXW4ParseOperation@2@PEBG111W4_XML_TYPE@@@Z; IsolationPolicy::TelemetryHelper::LogFormatError(IsolationPolicy::ParseOperation,ushort const *,ushort const *,ushort const *,ushort const *,_XML_TYPE)
0x1800432f8  mov     ecx, 57h ; 'W'; dwErrCode
0x1800432fd  call    cs:__imp_SetLastError
0x180043303  xor     r8d, r8d
0x180043306  lea     rcx, [rbp+57h+var_B8]
0x18004330a  mov     dl, 1
0x18004330c  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180043311  xor     r8d, r8d
0x180043314  lea     rcx, [rbp+57h+var_58]
0x180043318  mov     dl, 1
0x18004331a  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18004331f  xor     r8d, r8d
0x180043322  lea     rcx, [rbp+57h+var_98]
0x180043326  mov     dl, 1
0x180043328  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18004332d  xor     r8d, r8d
0x180043330  lea     rcx, [rsp+130h+var_D8]
0x180043335  mov     dl, 1
0x180043337  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18004333c  xor     r8d, r8d
0x18004333f  lea     rcx, [rbp+57h+var_78]
0x180043343  mov     dl, 1
0x180043345  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18004334a  xor     eax, eax
0x18004334c  jmp     loc_180043436
0x180043351  mov     rax, [rdi]
0x180043354  mov     rcx, rdi
0x180043357  mov     rax, [rax+18h]
0x18004335b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043360  lea     rdx, Options
0x180043367  mov     [rsp+130h+var_108], eax
0x18004336b  mov     [rsp+130h+var_110], rdx
0x180043370  mov     r9, rdx
0x180043373  mov     r8, rdx
0x180043376  mov     ecx, 1
0x18004337b  lea     rdx, aConsumesCapabi; "consumes\\capability"
0x180043382  call    ?LogFormatError@TelemetryHelper@IsolationPolicy@@CAXW4ParseOperation@2@PEBG111W4_XML_TYPE@@@Z; IsolationPolicy::TelemetryHelper::LogFormatError(IsolationPolicy::ParseOperation,ushort const *,ushort const *,ushort const *,ushort const *,_XML_TYPE)
0x180043387  mov     ecx, 57h ; 'W'; dwErrCode
0x18004338c  call    cs:__imp_SetLastError
0x180043392  jmp     short loc_18004331F
0x180043394  cmp     [rbp+57h+var_68], 0
0x180043399  jnz     short loc_1800433DD
0x18004339b  cmp     [rbp+57h+var_88], 0
0x1800433a0  jnz     short loc_1800433DD
0x1800433a2  lea     rdx, Options
0x1800433a9  mov     [rsp+130h+var_108], 0
0x1800433b1  lea     r9, aNameOrSid; "name or sid"
0x1800433b8  mov     [rsp+130h+var_110], rdx
0x1800433bd  lea     r8, aConsumesCapabi; "consumes\\capability"
0x1800433c4  mov     ecx, 5
0x1800433c9  call    ?LogFormatError@TelemetryHelper@IsolationPolicy@@CAXW4ParseOperation@2@PEBG111W4_XML_TYPE@@@Z; IsolationPolicy::TelemetryHelper::LogFormatError(IsolationPolicy::ParseOperation,ushort const *,ushort const *,ushort const *,ushort const *,_XML_TYPE)
0x1800433ce  mov     ecx, 57h ; 'W'; dwErrCode
0x1800433d3  call    cs:__imp_SetLastError
0x1800433d9  xor     ebx, ebx
0x1800433db  jmp     short loc_180043409
0x1800433dd  lea     rdx, [rbp+57h+var_78]
0x1800433e1  mov     rcx, r14
0x1800433e4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800433e9  lea     rcx, [r14+20h]
0x1800433ed  lea     rdx, [rbp+57h+var_98]
0x1800433f1  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800433f6  lea     rcx, [r14+40h]
0x1800433fa  lea     rdx, [rsp+130h+var_D8]
0x1800433ff  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180043404  mov     ebx, 1
0x180043409  xor     r8d, r8d
0x18004340c  lea     rcx, [rbp+57h+var_98]
0x180043410  mov     dl, 1
0x180043412  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180043417  xor     r8d, r8d
0x18004341a  lea     rcx, [rsp+130h+var_D8]
0x18004341f  mov     dl, 1
0x180043421  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180043426  xor     r8d, r8d
0x180043429  lea     rcx, [rbp+57h+var_78]
0x18004342d  mov     dl, 1
0x18004342f  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180043434  mov     eax, ebx
0x180043436  mov     rcx, [rbp+57h+var_38]
0x18004343a  xor     rcx, rsp; StackCookie
0x18004343d  call    __security_check_cookie
0x180043442  add     rsp, 100h
0x180043449  pop     r15
0x18004344b  pop     r14
0x18004344d  pop     r12
0x18004344f  pop     rdi
0x180043450  pop     rsi
0x180043451  pop     rbx
0x180043452  pop     rbp
0x180043453  retn
```
