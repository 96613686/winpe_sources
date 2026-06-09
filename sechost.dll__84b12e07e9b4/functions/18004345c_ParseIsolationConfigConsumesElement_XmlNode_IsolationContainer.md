# ParseIsolationConfigConsumesElement(XmlNode *,IsolationContainer *)

- ea: `0x18004345c`
- end: `0x1800436f9`
- name: `?ParseIsolationConfigConsumesElement@@YAHPEAVXmlNode@@PEAVIsolationContainer@@@Z`
- size: `669`
- prototype: `__int64 __fastcall(struct XmlNode *, struct IsolationContainer *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180043700`

## callees

- `0x180016a88`
- `0x1800192a8`
- `0x180042e98`
- `0x180043010`
- `0x18004345c`
- `0x180045c84`
- `0x180047f70`
- `0x1800480f0`
- `0x18004ecbc`
- `0x18004ece0`
- `0x18004fa50`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004357c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043670`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800436c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004357c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043670`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800436c9`

## pseudocode

```c
__int64 __fastcall ParseIsolationConfigConsumesElement(struct XmlNode *a1, struct IsolationContainer *a2)
{
  __int64 v4; // rax
  char v5; // al
  __int64 v6; // rdx
  char v7; // bl
  __int64 v8; // rdx
  __int64 v10; // rax
  XmlNodeSet *v11; // rax
  struct XmlNode *i; // rax
  struct XmlNode *v13; // rdi
  int v14; // eax
  __int64 v15; // rax
  __int64 v16; // rax
  char v17; // al
  __int64 v18; // rdx
  char v19; // bl
  __int64 v20; // rdx
  __int64 v21; // rdx
  XmlNodeSet *v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rax
  unsigned __int64 v25; // [rsp+30h] [rbp-99h] BYREF
  void *v26; // [rsp+38h] [rbp-91h] BYREF
  _BYTE v27[32]; // [rsp+40h] [rbp-89h] BYREF
  _BYTE v28[32]; // [rsp+60h] [rbp-69h] BYREF
  _WORD v29[8]; // [rsp+80h] [rbp-49h] BYREF
  __int64 v30; // [rsp+90h] [rbp-39h]
  __int64 v31; // [rsp+98h] [rbp-31h]
  __int16 v32; // [rsp+A0h] [rbp-29h]
  __int64 v33; // [rsp+B0h] [rbp-19h]
  __int64 v34; // [rsp+B8h] [rbp-11h]
  __int16 v35; // [rsp+C0h] [rbp-9h]
  __int64 v36; // [rsp+D0h] [rbp+7h]
  __int64 v37; // [rsp+D8h] [rbp+Fh]
  int v38; // [rsp+E0h] [rbp+17h]

  std::wstring::wstring(v28, L"consumes");
  v4 = (*(__int64 (__fastcall **)(struct XmlNode *))(*(_QWORD *)a1 + 40LL))(a1);
  std::wstring::wstring(v27, v4);
  v5 = Compare(v27, v28);
  LOBYTE(v6) = 1;
  v7 = v5;
  std::wstring::_Tidy(v27, v6, 0);
  LOBYTE(v8) = 1;
  std::wstring::_Tidy(v28, v8, 0);
  if ( !v7 )
    return 0;
  v10 = *(_QWORD *)a1;
  v26 = 0;
  v11 = (XmlNodeSet *)(*(__int64 (__fastcall **)(struct XmlNode *))(v10 + 32))(a1);
  for ( i = XmlNodeSet::iteratorReset(v11, &v26); ; i = XmlNodeSet::iteratorNext(v22, &v26) )
  {
    v13 = i;
    if ( !i )
      break;
    v14 = (*(__int64 (__fastcall **)(struct XmlNode *))(*(_QWORD *)i + 24LL))(i) - 2;
    if ( v14 )
    {
      if ( v14 == 1 )
      {
        v15 = (*(__int64 (__fastcall **)(struct XmlNode *))(*(_QWORD *)v13 + 40LL))(v13);
        IsolationPolicy::TelemetryHelper::LogFormatError(3, L"consumes", v15, &Options, &Options, 0);
        SetLastError(0x57u);
        return 0;
      }
    }
    else
    {
      v16 = (*(__int64 (__fastcall **)(struct XmlNode *))(*(_QWORD *)v13 + 40LL))(v13);
      std::wstring::wstring(v27, v16);
      std::wstring::wstring(v28, L"capability");
      v17 = Compare(v27, v28);
      LOBYTE(v18) = 1;
      v19 = v17;
      std::wstring::_Tidy(v28, v18, 0);
      if ( !v19 )
      {
        v24 = (*(__int64 (__fastcall **)(struct XmlNode *))(*(_QWORD *)v13 + 40LL))(v13);
        IsolationPolicy::TelemetryHelper::LogFormatError(0, L"consumes", v24, &Options, &Options, 0);
        SetLastError(0x57u);
        goto LABEL_15;
      }
      v31 = 7;
      v29[0] = 0;
      v33 = 0;
      v32 = 0;
      v36 = 0;
      v35 = 0;
      v38 = 0;
      v25 = 0;
      v30 = 0;
      v34 = 7;
      v37 = 7;
      if ( !(unsigned int)ParseIsolationConfigCapabilityElement(v13, v20, &v25, (struct Capability *)v29) )
        goto LABEL_14;
      if ( !IsolationContainer::AddConsumerCapability(a2, (const struct Capability *)v29, v25) )
      {
        SetLastError(0x54Fu);
LABEL_14:
        Capability::~Capability((Capability *)v29);
LABEL_15:
        LOBYTE(v23) = 1;
        std::wstring::_Tidy(v27, v23, 0);
        return 0;
      }
      Capability::~Capability((Capability *)v29);
      LOBYTE(v21) = 1;
      std::wstring::_Tidy(v27, v21, 0);
    }
    (*(void (__fastcall **)(struct XmlNode *))(*(_QWORD *)a1 + 32LL))(a1);
  }
  return 1;
}

```

## disassembly

```asm
0x18004345c  mov     [rsp-8+arg_10], rbx
0x180043461  push    rbp
0x180043462  push    rsi
0x180043463  push    rdi
0x180043464  push    r12
0x180043466  push    r14
0x180043468  lea     rbp, [rsp-37h]
0x18004346d  sub     rsp, 100h
0x180043474  mov     rax, cs:__security_cookie
0x18004347b  xor     rax, rsp
0x18004347e  mov     [rbp+57h+var_30], rax
0x180043482  mov     r14, rdx
0x180043485  mov     rsi, rcx
0x180043488  lea     rdx, aConsumes; "consumes"
0x18004348f  lea     rcx, [rbp+57h+var_C0]
0x180043493  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180043498  mov     rax, [rsi]
0x18004349b  mov     rcx, rsi
0x18004349e  mov     rax, [rax+28h]
0x1800434a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800434a7  mov     rdx, rax
0x1800434aa  lea     rcx, [rsp+120h+var_E0]
0x1800434af  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800434b4  lea     rdx, [rbp+57h+var_C0]
0x1800434b8  lea     rcx, [rsp+120h+var_E0]
0x1800434bd  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x1800434c2  xor     r8d, r8d
0x1800434c5  lea     rcx, [rsp+120h+var_E0]
0x1800434ca  mov     dl, 1
0x1800434cc  mov     bl, al
0x1800434ce  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800434d3  xor     r8d, r8d
0x1800434d6  lea     rcx, [rbp+57h+var_C0]
0x1800434da  mov     dl, 1
0x1800434dc  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800434e1  test    bl, bl
0x1800434e3  jnz     short loc_1800434EC
0x1800434e5  xor     eax, eax
0x1800434e7  jmp     loc_1800436D6
0x1800434ec  mov     rax, [rsi]
0x1800434ef  mov     rcx, rsi
0x1800434f2  mov     [rsp+120h+var_E8], 0
0x1800434fb  mov     rax, [rax+20h]
0x1800434ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043504  lea     rdx, [rsp+120h+var_E8]; void **
0x180043509  mov     rcx, rax; this
0x18004350c  call    ?iteratorReset@XmlNodeSet@@QEAAPEAVXmlNode@@PEAPEAX@Z; XmlNodeSet::iteratorReset(void * *)
0x180043511  mov     r12d, 7
0x180043517  mov     rdi, rax
0x18004351a  test    rax, rax
0x18004351d  jz      loc_1800436D1
0x180043523  mov     rcx, [rax]
0x180043526  mov     rax, [rcx+18h]
0x18004352a  mov     rcx, rdi
0x18004352d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043532  sub     eax, 2
0x180043535  jz      short loc_180043587
0x180043537  cmp     eax, 1
0x18004353a  jnz     loc_18004364D
0x180043540  mov     rax, [rdi]
0x180043543  mov     rcx, rdi
0x180043546  mov     rax, [rax+28h]
0x18004354a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004354f  lea     r9, Options
0x180043556  mov     [rsp+120h+var_F8], 0
0x18004355e  mov     r8, rax
0x180043561  mov     [rsp+120h+var_100], r9
0x180043566  lea     rdx, aConsumes; "consumes"
0x18004356d  mov     ecx, 3
0x180043572  call    ?LogFormatError@TelemetryHelper@IsolationPolicy@@CAXW4ParseOperation@2@PEBG111W4_XML_TYPE@@@Z; IsolationPolicy::TelemetryHelper::LogFormatError(IsolationPolicy::ParseOperation,ushort const *,ushort const *,ushort const *,ushort const *,_XML_TYPE)
0x180043577  mov     ecx, 57h ; 'W'; dwErrCode
0x18004357c  call    cs:__imp_SetLastError
0x180043582  jmp     loc_1800434E5
0x180043587  mov     rax, [rdi]
0x18004358a  mov     rcx, rdi
0x18004358d  mov     rax, [rax+28h]
0x180043591  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043596  mov     rdx, rax
0x180043599  lea     rcx, [rsp+120h+var_E0]
0x18004359e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800435a3  lea     rdx, aCapability; "capability"
0x1800435aa  lea     rcx, [rbp+57h+var_C0]
0x1800435ae  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800435b3  lea     rdx, [rbp+57h+var_C0]
0x1800435b7  lea     rcx, [rsp+120h+var_E0]
0x1800435bc  call    ?Compare@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z; Compare(std::wstring const &,std::wstring const &,bool)
0x1800435c1  xor     r8d, r8d
0x1800435c4  lea     rcx, [rbp+57h+var_C0]
0x1800435c8  mov     dl, 1
0x1800435ca  mov     bl, al
0x1800435cc  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800435d1  mov     rcx, rdi; struct XmlNode *
0x1800435d4  test    bl, bl
0x1800435d6  jz      loc_180043693
0x1800435dc  xor     eax, eax
0x1800435de  mov     [rbp+57h+var_88], r12
0x1800435e2  lea     r9, [rbp+57h+var_A0]; struct Capability *
0x1800435e6  mov     [rbp+57h+var_A0], ax
0x1800435ea  lea     r8, [rsp+120h+var_F0]; unsigned __int64 *
0x1800435ef  mov     [rbp+57h+var_70], rax
0x1800435f3  mov     [rbp+57h+var_80], ax
0x1800435f7  mov     [rbp+57h+var_50], rax
0x1800435fb  mov     [rbp+57h+var_60], ax
0x1800435ff  mov     [rbp+57h+var_40], eax
0x180043602  mov     [rsp+120h+var_F0], rax
0x180043607  mov     [rbp+57h+var_90], 0
0x18004360f  mov     [rbp+57h+var_68], r12
0x180043613  mov     [rbp+57h+var_48], r12
0x180043617  call    ?ParseIsolationConfigCapabilityElement@@YAHPEAVXmlNode@@_NPEA_KPEAVCapability@@@Z; ParseIsolationConfigCapabilityElement(XmlNode *,bool,unsigned __int64 *,Capability *)
0x18004361c  test    eax, eax
0x18004361e  jz      short loc_180043676
0x180043620  mov     r8, [rsp+120h+var_F0]; unsigned __int64
0x180043625  lea     rdx, [rbp+57h+var_A0]; struct Capability *
0x180043629  mov     rcx, r14; this
0x18004362c  call    ?AddConsumerCapability@IsolationContainer@@QEAA_NPEBVCapability@@_K@Z; IsolationContainer::AddConsumerCapability(Capability const *,unsigned __int64)
0x180043631  test    al, al
0x180043633  jz      short loc_18004366B
0x180043635  lea     rcx, [rbp+57h+var_A0]; this
0x180043639  call    ??1Capability@@QEAA@XZ; Capability::~Capability(void)
0x18004363e  xor     r8d, r8d
0x180043641  lea     rcx, [rsp+120h+var_E0]
0x180043646  mov     dl, 1
0x180043648  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18004364d  mov     rax, [rsi]
0x180043650  mov     rcx, rsi
0x180043653  mov     rax, [rax+20h]
0x180043657  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004365c  lea     rdx, [rsp+120h+var_E8]; void **
0x180043661  call    ?iteratorNext@XmlNodeSet@@QEAAPEAVXmlNode@@PEAPEAX@Z; XmlNodeSet::iteratorNext(void * *)
0x180043666  jmp     loc_180043517
0x18004366b  mov     ecx, 54Fh; dwErrCode
0x180043670  call    cs:__imp_SetLastError
0x180043676  lea     rcx, [rbp+57h+var_A0]; this
0x18004367a  call    ??1Capability@@QEAA@XZ; Capability::~Capability(void)
0x18004367f  xor     r8d, r8d
0x180043682  lea     rcx, [rsp+120h+var_E0]
0x180043687  mov     dl, 1
0x180043689  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18004368e  jmp     loc_1800434E5
0x180043693  mov     rax, [rdi]
0x180043696  mov     rax, [rax+28h]
0x18004369a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004369f  lea     r9, Options
0x1800436a6  mov     [rsp+120h+var_F8], 0
0x1800436ae  mov     r8, rax
0x1800436b1  mov     [rsp+120h+var_100], r9
0x1800436b6  lea     rdx, aConsumes; "consumes"
0x1800436bd  xor     ecx, ecx
0x1800436bf  call    ?LogFormatError@TelemetryHelper@IsolationPolicy@@CAXW4ParseOperation@2@PEBG111W4_XML_TYPE@@@Z; IsolationPolicy::TelemetryHelper::LogFormatError(IsolationPolicy::ParseOperation,ushort const *,ushort const *,ushort const *,ushort const *,_XML_TYPE)
0x1800436c4  mov     ecx, 57h ; 'W'; dwErrCode
0x1800436c9  call    cs:__imp_SetLastError
0x1800436cf  jmp     short loc_18004367F
0x1800436d1  mov     eax, 1
0x1800436d6  mov     rcx, [rbp+57h+var_30]
0x1800436da  xor     rcx, rsp; StackCookie
0x1800436dd  call    __security_check_cookie
0x1800436e2  mov     rbx, [rsp+120h+arg_10]
0x1800436ea  add     rsp, 100h
0x1800436f1  pop     r14
0x1800436f3  pop     r12
0x1800436f5  pop     rdi
0x1800436f6  pop     rsi
0x1800436f7  pop     rbp
0x1800436f8  retn
```
