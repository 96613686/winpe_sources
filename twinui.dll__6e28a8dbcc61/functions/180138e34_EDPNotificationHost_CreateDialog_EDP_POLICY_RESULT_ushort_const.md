# EDPNotificationHost::_CreateDialog(EDP_POLICY_RESULT,ushort const *)

- ea: `0x180138e34`
- end: `0x1801394b6`
- name: `?_CreateDialog@EDPNotificationHost@@AEAAJW4EDP_POLICY_RESULT@@PEBG@Z`
- size: `1666`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1802cec84`

## callees

- `0x180027ee4`
- `0x18003c5e4`
- `0x180138e34`
- `0x1801394bc`
- `0x180158790`
- `0x1802cdf80`
- `0x1803a3010`

## import_xrefs

- `DUI70!?AddRef@Element@DirectUI@@QEAAKXZ` at `0x180138ff6`
- `DUI70!?AddRef@Element@DirectUI@@QEAAKXZ` at `0x180138ff6`
- `DUI70!?SetAccValue@Element@DirectUI@@QEAAJPEBG@Z` at `0x18013909b`
- `DUI70!?SetAccValue@Element@DirectUI@@QEAAJPEBG@Z` at `0x180139115`
- `DUI70!?SetAccValue@Element@DirectUI@@QEAAJPEBG@Z` at `0x18013909b`
- `DUI70!?SetAccValue@Element@DirectUI@@QEAAJPEBG@Z` at `0x180139115`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x18013907c`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1801390f5`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x18013907c`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1801390f5`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180138fe1`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180139024`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180138fe1`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180139024`
- `DUI70!StrToID` at `0x180138fd5`
- `DUI70!StrToID` at `0x180139018`
- `DUI70!StrToID` at `0x180138fd5`
- `DUI70!StrToID` at `0x180139018`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x180138f9d`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x180138f9d`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x180138f48`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x180138f48`
- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x180139052`
- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x180139052`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x180138f26`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x180138f26`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x1801391ca`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x1801392bc`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x180139367`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x1801393b2`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18013948a`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x1801391ca`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x1801392bc`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x180139367`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x1801393b2`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18013948a`

## string_xrefs

- `0x180139011`: `LearnMoreLink`

## pseudocode

```c
__int64 __fastcall EDPNotificationHost::_CreateDialog(unsigned __int64 a1, int a2, const unsigned __int16 *a3)
{
  char v6; // r15
  __int64 v7; // r8
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  int v11; // eax
  int v12; // eax
  DirectUI::Element *v13; // rbx
  unsigned __int16 v14; // ax
  DirectUI::Element *Descendent; // rax
  DirectUI::Element *v16; // rdi
  DirectUI::Element *v17; // rbx
  unsigned __int16 v18; // ax
  DirectUI::Element *v19; // r8
  __int64 v20; // rdx
  int v21; // eax
  __int64 v22; // r9
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  unsigned __int64 v30; // rbx
  int v31; // edi
  unsigned __int64 v32; // rdi
  __int64 v33; // rcx
  int v34; // r14d
  __int64 v35; // rdx
  int v36; // eax
  unsigned int v37; // esi
  __int64 v38; // rdx
  int v40; // [rsp+20h] [rbp-60h]
  int v41; // [rsp+20h] [rbp-60h]
  struct DirectUI::DUIXmlParser *v42; // [rsp+30h] [rbp-50h] BYREF
  DirectUI::Element *v43; // [rsp+38h] [rbp-48h] BYREF
  unsigned __int64 v44; // [rsp+40h] [rbp-40h] BYREF
  unsigned __int64 v45; // [rsp+48h] [rbp-38h] BYREF
  _QWORD v46[2]; // [rsp+50h] [rbp-30h] BYREF
  const unsigned __int16 *v47[4]; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  int v49; // [rsp+C8h] [rbp+48h] BYREF
  struct DirectUI::Element *v50; // [rsp+D8h] [rbp+58h] BYREF

  if ( (unsigned int)(a2 - 3) <= 1 )
  {
    v6 = 1;
    v7 = 12401;
    if ( a2 != 3 )
      v7 = 12403;
  }
  else
  {
    v6 = 0;
    v7 = 12411;
  }
  memset(v47, 0, 24);
  v8 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeResMessage(
         v47,
         &_ImageBase,
         v7);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 144;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"shell\\twinui\\edpnotificationhost\\lib\\edpnotificationhost.cpp",
      (const char *)(unsigned int)v8,
      v40);
    goto LABEL_80;
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *))(**(_QWORD **)(a1 + 152) + 32LL))(
         *(_QWORD *)(a1 + 152),
         v47[0]);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 146;
    goto LABEL_9;
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, _QWORD))(**(_QWORD **)(a1 + 152) + 256LL))(
         *(_QWORD *)(a1 + 152),
         v47[0],
         0);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 147;
    goto LABEL_9;
  }
  v42 = 0;
  v8 = DirectUI::DUIXmlParser::Create(&v42, 0, 0, 0, 0);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 150;
    goto LABEL_9;
  }
  v11 = DirectUI::DUIXmlParser::SetXMLFromResource(v42, 0x308Fu, (HINSTANCE)&_ImageBase, (HINSTANCE)&_ImageBase);
  v9 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9B,
      (unsigned int)"shell\\twinui\\edpnotificationhost\\lib\\edpnotificationhost.cpp",
      (const char *)(unsigned int)v11,
      v40);
LABEL_79:
    DirectUI::DUIXmlParser::Destroy(v42);
    goto LABEL_80;
  }
  v50 = 0;
  Microsoft::WRL::ComPtr<DirectUI::Element>::InternalRelease(&v50);
  v12 = DirectUI::DUIXmlParser::CreateElement(v42, L"edpmain", 0, 0, 0, &v50);
  v9 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9E,
      (unsigned int)"shell\\twinui\\edpnotificationhost\\lib\\edpnotificationhost.cpp",
      (const char *)(unsigned int)v12,
      v41);
LABEL_78:
    Microsoft::WRL::ComPtr<DirectUI::Element>::InternalRelease(&v50);
    goto LABEL_79;
  }
  v13 = v50;
  v43 = 0;
  v14 = StrToID(L"ModalElement");
  Descendent = DirectUI::Element::FindDescendent(v13, v14);
  v16 = Descendent;
  if ( !Descendent )
  {
    v20 = 162;
    goto LABEL_76;
  }
  DirectUI::Element::AddRef(Descendent);
  v44 = 0;
  v43 = v16;
  Microsoft::WRL::ComPtr<DirectUI::Element>::InternalRelease(&v44);
  v17 = v50;
  v18 = StrToID(L"LearnMoreLink");
  v19 = DirectUI::Element::FindDescendent(v17, v18);
  if ( !v19 )
  {
    v20 = 166;
LABEL_76:
    v9 = -2147467259;
    v22 = 2147500037LL;
    goto LABEL_77;
  }
  v21 = DirectUI::Element::AddListener(
          v19,
          (struct DirectUI::IElementListener *)((a1 + 136) & ((unsigned __int128)-(__int128)a1 >> 64)));
  v9 = v21;
  if ( v21 < 0 )
  {
    v22 = (unsigned int)v21;
    v20 = 167;
LABEL_77:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"shell\\twinui\\edpnotificationhost\\lib\\edpnotificationhost.cpp",
      (const char *)v22,
      v41);
    Microsoft::WRL::ComPtr<DirectUI::Element>::InternalRelease(&v43);
    goto LABEL_78;
  }
  if ( a3 && *a3 )
  {
    v23 = DirectUI::Element::SetContentString(v16, a3);
    v9 = v23;
    if ( v23 < 0 )
    {
      v22 = (unsigned int)v23;
      v20 = 178;
      goto LABEL_77;
    }
    v24 = DirectUI::Element::SetAccValue(v16, a3);
    v9 = v24;
    if ( v24 < 0 )
    {
      v22 = (unsigned int)v24;
      v20 = 179;
      goto LABEL_77;
    }
  }
  else
  {
    v25 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeResMessage(
            v47,
            &_ImageBase,
            v6 != 0 ? 12402 : 12412);
    v9 = v25;
    if ( v25 < 0 )
    {
      v22 = (unsigned int)v25;
      v20 = 172;
      goto LABEL_77;
    }
    v26 = DirectUI::Element::SetContentString(v16, v47[0]);
    v9 = v26;
    if ( v26 < 0 )
    {
      v22 = (unsigned int)v26;
      v20 = 173;
      goto LABEL_77;
    }
    v27 = DirectUI::Element::SetAccValue(v16, v47[0]);
    v9 = v27;
    if ( v27 < 0 )
    {
      v22 = (unsigned int)v27;
      v20 = 174;
      goto LABEL_77;
    }
  }
  v28 = (*(__int64 (__fastcall **)(_QWORD, struct DirectUI::Element *))(**(_QWORD **)(a1 + 152) + 352LL))(
          *(_QWORD *)(a1 + 152),
          v50);
  v9 = v28;
  if ( v28 < 0 )
  {
    v22 = (unsigned int)v28;
    v20 = 182;
    goto LABEL_77;
  }
  if ( v6 )
    v29 = (a2 != 3) + 12423;
  else
    v29 = 12422;
  v49 = v29;
  v44 = a1;
  Microsoft::WRL::Details::Make<EDPPopupCommand,unsigned long const &,EDPNotificationHost *>(&v45, &v49, &v44);
  v30 = v45;
  if ( !v45 )
  {
    v31 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBF,
      (unsigned int)"shell\\twinui\\edpnotificationhost\\lib\\edpnotificationhost.cpp",
      (const char *)0x8007000ELL,
      v41);
LABEL_42:
    Microsoft::WRL::ComPtr<DirectUI::Element>::InternalRelease(&v43);
    Microsoft::WRL::ComPtr<DirectUI::Element>::InternalRelease(&v50);
    DirectUI::DUIXmlParser::Destroy(v42);
    v9 = v31;
    goto LABEL_80;
  }
  if ( !v6 )
  {
    v31 = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned __int64 *))(**(_QWORD **)(a1 + 152) + 64LL))(
            *(_QWORD *)(a1 + 152),
            1,
            &v45);
    if ( v31 >= 0 )
    {
      v31 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 152) + 88LL))(*(_QWORD *)(a1 + 152), 0);
      if ( v31 >= 0 )
      {
        v31 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 152) + 120LL))(*(_QWORD *)(a1 + 152), 0);
        if ( v31 >= 0 )
          goto LABEL_64;
        v38 = 213;
      }
      else
      {
        v38 = 212;
      }
    }
    else
    {
      v38 = 209;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v38,
      (unsigned int)"shell\\twinui\\edpnotificationhost\\lib\\edpnotificationhost.cpp",
      (const char *)(unsigned int)v31,
      v41);
    if ( !v30 )
      goto LABEL_42;
    goto LABEL_46;
  }
  v45 = a1;
  v49 = 12421;
  Microsoft::WRL::Details::Make<EDPPopupCommand,unsigned long const &,EDPNotificationHost *>(&v44, &v49, &v45);
  v32 = v44;
  if ( !v44 )
  {
    v31 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC5,
      (unsigned int)"shell\\twinui\\edpnotificationhost\\lib\\edpnotificationhost.cpp",
      (const char *)0x8007000ELL,
      v41);
    if ( !v30 )
      goto LABEL_42;
LABEL_46:
    (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v30 + 16LL))(v30);
    goto LABEL_42;
  }
  v33 = *(_QWORD *)(a1 + 152);
  v46[0] = v44;
  v46[1] = v30;
  v34 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD *))(*(_QWORD *)v33 + 64LL))(v33, 2, v46);
  if ( v34 < 0 )
  {
    v35 = 200;
LABEL_49:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v35,
      (unsigned int)"shell\\twinui\\edpnotificationhost\\lib\\edpnotificationhost.cpp",
      (const char *)(unsigned int)v34,
      v41);
    if ( v32 )
      (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v32 + 16LL))(v32);
    if ( v30 )
      (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v30 + 16LL))(v30);
    Microsoft::WRL::ComPtr<DirectUI::Element>::InternalRelease(&v43);
    Microsoft::WRL::ComPtr<DirectUI::Element>::InternalRelease(&v50);
    DirectUI::DUIXmlParser::Destroy(v42);
    v9 = v34;
    goto LABEL_80;
  }
  v34 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 152) + 88LL))(*(_QWORD *)(a1 + 152), 1);
  if ( v34 < 0 )
  {
    v35 = 203;
    goto LABEL_49;
  }
  v36 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 152) + 120LL))(*(_QWORD *)(a1 + 152), 1);
  v37 = v36;
  if ( v36 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCC,
      (unsigned int)"shell\\twinui\\edpnotificationhost\\lib\\edpnotificationhost.cpp",
      (const char *)(unsigned int)v36,
      v41);
    if ( v32 )
      (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v32 + 16LL))(v32);
    if ( v30 )
      (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v30 + 16LL))(v30);
    Microsoft::WRL::ComPtr<DirectUI::Element>::InternalRelease(&v43);
    Microsoft::WRL::ComPtr<DirectUI::Element>::InternalRelease(&v50);
    DirectUI::DUIXmlParser::Destroy(v42);
    v9 = v37;
    goto LABEL_80;
  }
  if ( v32 )
    (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v32 + 16LL))(v32);
LABEL_64:
  if ( v30 )
    (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v30 + 16LL))(v30);
  Microsoft::WRL::ComPtr<DirectUI::Element>::InternalRelease(&v43);
  Microsoft::WRL::ComPtr<DirectUI::Element>::InternalRelease(&v50);
  DirectUI::DUIXmlParser::Destroy(v42);
  v9 = 0;
LABEL_80:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v47);
  return v9;
}

```

## disassembly

```asm
0x180138e34  mov     [rsp-38h+arg_0], rbx
0x180138e39  push    rbp
0x180138e3a  push    rsi
0x180138e3b  push    rdi
0x180138e3c  push    r12
0x180138e3e  push    r13
0x180138e40  push    r14
0x180138e42  push    r15
0x180138e44  mov     rbp, rsp
0x180138e47  sub     rsp, 80h
0x180138e4e  lea     eax, [rdx-3]
0x180138e51  xor     r12d, r12d
0x180138e54  mov     r14, r8
0x180138e57  mov     r13d, edx
0x180138e5a  mov     rsi, rcx
0x180138e5d  cmp     eax, 1
0x180138e60  jbe     short loc_180138E6D
0x180138e62  mov     r15b, r12b
0x180138e65  mov     r8d, 307Bh
0x180138e6b  jmp     short loc_180138E81
0x180138e6d  mov     eax, 3073h
0x180138e72  cmp     r13d, 3
0x180138e76  mov     r15b, 1
0x180138e79  lea     r8d, [rax-2]
0x180138e7d  cmovnz  r8d, eax
0x180138e81  lea     rdi, __ImageBase
0x180138e88  mov     [rbp+var_20], r12
0x180138e8c  mov     rdx, rdi
0x180138e8f  mov     [rbp+var_18], r12
0x180138e93  lea     rcx, [rbp+var_20]
0x180138e97  mov     [rbp+var_10], r12
0x180138e9b  call    ?InitializeResMessage@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@HZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeResMessage(HINSTANCE__ *,int,...)
0x180138ea0  mov     ebx, eax
0x180138ea2  test    eax, eax
0x180138ea4  jns     short loc_180138EAD
0x180138ea6  mov     edx, 90h
0x180138eab  jmp     short loc_180138ECF
0x180138ead  mov     rcx, [rsi+98h]
0x180138eb4  mov     rdx, [rbp+var_20]
0x180138eb8  mov     rax, [rcx]
0x180138ebb  mov     rax, [rax+20h]
0x180138ebf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180138ec4  mov     ebx, eax
0x180138ec6  test    eax, eax
0x180138ec8  jns     short loc_180138EE7
0x180138eca  mov     edx, 92h; void *
0x180138ecf  mov     rcx, [rbp+38h]; this
0x180138ed3  lea     r8, aShellTwinuiEdp; "shell\\twinui\\edpnotificationhost\\lib"...
0x180138eda  mov     r9d, eax; char *
0x180138edd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180138ee2  jmp     loc_180139490
0x180138ee7  mov     rcx, [rsi+98h]
0x180138eee  xor     r8d, r8d
0x180138ef1  mov     rdx, [rbp+var_20]
0x180138ef5  mov     rax, [rcx]
0x180138ef8  mov     rax, [rax+100h]
0x180138eff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180138f04  mov     ebx, eax
0x180138f06  test    eax, eax
0x180138f08  jns     short loc_180138F11
0x180138f0a  mov     edx, 93h
0x180138f0f  jmp     short loc_180138ECF
0x180138f11  xor     r9d, r9d
0x180138f14  mov     [rbp+var_50], r12
0x180138f18  xor     r8d, r8d
0x180138f1b  mov     qword ptr [rsp+80h+var_60], r12; int
0x180138f20  xor     edx, edx
0x180138f22  lea     rcx, [rbp+var_50]
0x180138f26  call    cs:__imp_?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z; DirectUI::DUIXmlParser::Create(DirectUI::DUIXmlParser * *,DirectUI::Value * (*)(ushort const *,void *),void *,void (*)(ushort const *,ushort const *,int,void *),void *)
0x180138f2c  mov     ebx, eax
0x180138f2e  test    eax, eax
0x180138f30  jns     short loc_180138F39
0x180138f32  mov     edx, 96h
0x180138f37  jmp     short loc_180138ECF
0x180138f39  mov     rcx, [rbp+var_50]
0x180138f3d  mov     r9, rdi
0x180138f40  mov     r8, rdi
0x180138f43  mov     edx, 308Fh
0x180138f48  call    cs:__imp_?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z; DirectUI::DUIXmlParser::SetXMLFromResource(uint,HINSTANCE__ *,HINSTANCE__ *)
0x180138f4e  mov     ebx, eax
0x180138f50  test    eax, eax
0x180138f52  jns     short loc_180138F71
0x180138f54  mov     rcx, [rbp+38h]; this
0x180138f58  lea     r8, aShellTwinuiEdp; "shell\\twinui\\edpnotificationhost\\lib"...
0x180138f5f  mov     r9d, eax; char *
0x180138f62  mov     edx, 9Bh; void *
0x180138f67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180138f6c  jmp     loc_180139486
0x180138f71  lea     rcx, [rbp+arg_18]
0x180138f75  mov     [rbp+arg_18], r12
0x180138f79  call    ?InternalRelease@?$ComPtr@VElement@DirectUI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<DirectUI::Element>::InternalRelease(void)
0x180138f7e  mov     rcx, [rbp+var_50]
0x180138f82  lea     rax, [rbp+arg_18]
0x180138f86  mov     [rsp+80h+var_58], rax
0x180138f8b  lea     rdx, aEdpmain; "edpmain"
0x180138f92  xor     r9d, r9d
0x180138f95  mov     qword ptr [rsp+80h+var_60], r12; int
0x180138f9a  xor     r8d, r8d
0x180138f9d  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x180138fa3  mov     ebx, eax
0x180138fa5  test    eax, eax
0x180138fa7  jns     short loc_180138FC6
0x180138fa9  mov     rcx, [rbp+38h]; this
0x180138fad  lea     r8, aShellTwinuiEdp; "shell\\twinui\\edpnotificationhost\\lib"...
0x180138fb4  mov     r9d, eax; char *
0x180138fb7  mov     edx, 9Eh; void *
0x180138fbc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180138fc1  jmp     loc_18013947D
0x180138fc6  mov     rbx, [rbp+arg_18]
0x180138fca  lea     rcx, aModalelement; "ModalElement"
0x180138fd1  mov     [rbp+var_48], r12
0x180138fd5  call    cs:__imp_StrToID
0x180138fdb  movzx   edx, ax
0x180138fde  mov     rcx, rbx
0x180138fe1  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180138fe7  mov     rdi, rax
0x180138fea  test    rax, rax
0x180138fed  jz      loc_180139457
0x180138ff3  mov     rcx, rax
0x180138ff6  call    cs:__imp_?AddRef@Element@DirectUI@@QEAAKXZ; DirectUI::Element::AddRef(void)
0x180138ffc  lea     rcx, [rbp+var_40]
0x180139000  mov     [rbp+var_40], r12
0x180139004  mov     [rbp+var_48], rdi
0x180139008  call    ?InternalRelease@?$ComPtr@VElement@DirectUI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<DirectUI::Element>::InternalRelease(void)
0x18013900d  mov     rbx, [rbp+arg_18]
0x180139011  lea     rcx, aLearnmorelink; "LearnMoreLink"
0x180139018  call    cs:__imp_StrToID
0x18013901e  movzx   edx, ax
0x180139021  mov     rcx, rbx
0x180139024  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18013902a  mov     r8, rax
0x18013902d  test    rax, rax
0x180139030  jnz     short loc_18013903C
0x180139032  mov     edx, 0A6h
0x180139037  jmp     loc_18013945C
0x18013903c  lea     rcx, [rsi+88h]
0x180139043  mov     rax, rsi
0x180139046  neg     rax
0x180139049  sbb     rdx, rdx
0x18013904c  and     rdx, rcx
0x18013904f  mov     rcx, r8
0x180139052  call    cs:__imp_?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z; DirectUI::Element::AddListener(DirectUI::IElementListener *)
0x180139058  mov     ebx, eax
0x18013905a  test    eax, eax
0x18013905c  jns     short loc_18013906B
0x18013905e  mov     r9d, eax
0x180139061  mov     edx, 0A7h
0x180139066  jmp     loc_180139464
0x18013906b  test    r14, r14
0x18013906e  jz      short loc_1801390B8
0x180139070  cmp     [r14], r12w
0x180139074  jz      short loc_1801390B8
0x180139076  mov     rdx, r14
0x180139079  mov     rcx, rdi
0x18013907c  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x180139082  mov     ebx, eax
0x180139084  test    eax, eax
0x180139086  jns     short loc_180139095
0x180139088  mov     r9d, eax
0x18013908b  mov     edx, 0B2h
0x180139090  jmp     loc_180139464
0x180139095  mov     rdx, r14
0x180139098  mov     rcx, rdi
0x18013909b  call    cs:__imp_?SetAccValue@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccValue(ushort const *)
0x1801390a1  mov     ebx, eax
0x1801390a3  test    eax, eax
0x1801390a5  jns     loc_18013912E
0x1801390ab  mov     r9d, eax
0x1801390ae  mov     edx, 0B3h
0x1801390b3  jmp     loc_180139464
0x1801390b8  mov     al, r15b
0x1801390bb  lea     rdx, __ImageBase
0x1801390c2  neg     al
0x1801390c4  lea     rcx, [rbp+var_20]
0x1801390c8  sbb     r8d, r8d
0x1801390cb  and     r8d, 0FFFFFFF6h
0x1801390cf  add     r8d, 307Ch
0x1801390d6  call    ?InitializeResMessage@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@HZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeResMessage(HINSTANCE__ *,int,...)
0x1801390db  mov     ebx, eax
0x1801390dd  test    eax, eax
0x1801390df  jns     short loc_1801390EE
0x1801390e1  mov     r9d, eax
0x1801390e4  mov     edx, 0ACh
0x1801390e9  jmp     loc_180139464
0x1801390ee  mov     rdx, [rbp+var_20]
0x1801390f2  mov     rcx, rdi
0x1801390f5  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x1801390fb  mov     ebx, eax
0x1801390fd  test    eax, eax
0x1801390ff  jns     short loc_18013910E
0x180139101  mov     r9d, eax
0x180139104  mov     edx, 0ADh
0x180139109  jmp     loc_180139464
0x18013910e  mov     rdx, [rbp+var_20]
0x180139112  mov     rcx, rdi
0x180139115  call    cs:__imp_?SetAccValue@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccValue(ushort const *)
0x18013911b  mov     ebx, eax
0x18013911d  test    eax, eax
0x18013911f  jns     short loc_18013912E
0x180139121  mov     r9d, eax
0x180139124  mov     edx, 0AEh
0x180139129  jmp     loc_180139464
0x18013912e  mov     rcx, [rsi+98h]
0x180139135  mov     rdx, [rbp+arg_18]
0x180139139  mov     rax, [rcx]
0x18013913c  mov     rax, [rax+160h]
0x180139143  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180139148  mov     ebx, eax
0x18013914a  test    eax, eax
0x18013914c  jns     short loc_18013915B
0x18013914e  mov     r9d, eax
0x180139151  mov     edx, 0B6h
0x180139156  jmp     loc_180139464
0x18013915b  test    r15b, r15b
0x18013915e  jz      short loc_180139171
0x180139160  cmp     r13d, 3
0x180139164  mov     eax, r12d
0x180139167  setnz   al
0x18013916a  add     eax, 3087h
0x18013916f  jmp     short loc_180139176
0x180139171  mov     eax, 3086h
0x180139176  lea     r8, [rbp+var_40]
0x18013917a  mov     [rbp+arg_8], eax
0x18013917d  lea     rdx, [rbp+arg_8]
0x180139181  mov     [rbp+var_40], rsi
0x180139185  lea     rcx, [rbp+var_38]
0x180139189  call    ??$Make@VEDPPopupCommand@@AEBKPEAVEDPNotificationHost@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VEDPPopupCommand@@@12@AEBK$$QEAPEAVEDPNotificationHost@@@Z; Microsoft::WRL::Details::Make<EDPPopupCommand,ulong const &,EDPNotificationHost *>(ulong const &,EDPNotificationHost * &&)
0x18013918e  mov     rbx, [rbp+var_38]
0x180139192  test    rbx, rbx
0x180139195  jnz     short loc_1801391D7
0x180139197  mov     rcx, [rbp+38h]; this
0x18013919b  lea     r8, aShellTwinuiEdp; "shell\\twinui\\edpnotificationhost\\lib"...
0x1801391a2  mov     edi, 8007000Eh
0x1801391a7  mov     edx, 0BFh; void *
0x1801391ac  mov     r9d, edi; char *
0x1801391af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801391b4  lea     rcx, [rbp+var_48]
0x1801391b8  call    ?InternalRelease@?$ComPtr@VElement@DirectUI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<DirectUI::Element>::InternalRelease(void)
0x1801391bd  lea     rcx, [rbp+arg_18]
0x1801391c1  call    ?InternalRelease@?$ComPtr@VElement@DirectUI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<DirectUI::Element>::InternalRelease(void)
0x1801391c6  mov     rcx, [rbp+var_50]
0x1801391ca  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x1801391d0  mov     ebx, edi
0x1801391d2  jmp     loc_180139490
0x1801391d7  lea     r8, [rbp+var_38]
0x1801391db  test    r15b, r15b
0x1801391de  jz      loc_1801393C0
0x1801391e4  lea     rdx, [rbp+arg_8]
0x1801391e8  mov     [rbp+var_38], rsi
0x1801391ec  lea     rcx, [rbp+var_40]
0x1801391f0  mov     [rbp+arg_8], 3085h
0x1801391f7  call    ??$Make@VEDPPopupCommand@@AEBKPEAVEDPNotificationHost@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VEDPPopupCommand@@@12@AEBK$$QEAPEAVEDPNotificationHost@@@Z; Microsoft::WRL::Details::Make<EDPPopupCommand,ulong const &,EDPNotificationHost *>(ulong const &,EDPNotificationHost * &&)
0x1801391fc  mov     rdi, [rbp+var_40]
0x180139200  test    rdi, rdi
0x180139203  jnz     short loc_18013923B
0x180139205  mov     rcx, [rbp+38h]; this
0x180139209  lea     r8, aShellTwinuiEdp; "shell\\twinui\\edpnotificationhost\\lib"...
0x180139210  mov     edi, 8007000Eh
0x180139215  mov     edx, 0C5h; void *
0x18013921a  mov     r9d, edi; char *
0x18013921d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180139222  test    rbx, rbx
0x180139225  jz      short loc_1801391B4
0x180139227  mov     rax, [rbx]
0x18013922a  mov     rax, [rax+10h]
0x18013922e  mov     rcx, rbx
0x180139231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180139236  jmp     loc_1801391B4
0x18013923b  mov     rcx, [rsi+98h]
0x180139242  lea     r8, [rbp+var_30]
0x180139246  mov     [rbp+var_30], rdi
0x18013924a  mov     edx, 2
0x18013924f  mov     [rbp+var_28], rbx
0x180139253  mov     rax, [rcx]
0x180139256  mov     rax, [rax+40h]
0x18013925a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013925f  mov     r14d, eax
0x180139262  test    eax, eax
0x180139264  jns     short loc_1801392CA
0x180139266  mov     edx, 0C8h; void *
0x18013926b  mov     rcx, [rbp+38h]; this
0x18013926f  lea     r8, aShellTwinuiEdp; "shell\\twinui\\edpnotificationhost\\lib"...
0x180139276  mov     r9d, r14d; char *
0x180139279  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013927e  test    rdi, rdi
0x180139281  jz      short loc_180139292
0x180139283  mov     rcx, [rdi]
0x180139286  mov     rax, [rcx+10h]
0x18013928a  mov     rcx, rdi
0x18013928d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180139292  test    rbx, rbx
0x180139295  jz      short loc_1801392A6
0x180139297  mov     rax, [rbx]
0x18013929a  mov     rcx, rbx
0x18013929d  mov     rax, [rax+10h]
0x1801392a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801392a6  lea     rcx, [rbp+var_48]
0x1801392aa  call    ?InternalRelease@?$ComPtr@VElement@DirectUI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<DirectUI::Element>::InternalRelease(void)
0x1801392af  lea     rcx, [rbp+arg_18]
0x1801392b3  call    ?InternalRelease@?$ComPtr@VElement@DirectUI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<DirectUI::Element>::InternalRelease(void)
  ... truncated ...
```
