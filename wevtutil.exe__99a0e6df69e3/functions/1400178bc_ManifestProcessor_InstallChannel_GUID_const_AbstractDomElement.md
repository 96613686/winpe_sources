# ManifestProcessor::InstallChannel(_GUID const &,AbstractDomElement &)

- ea: `0x1400178bc`
- end: `0x140017fb4`
- name: `?InstallChannel@ManifestProcessor@@AEAAXAEBU_GUID@@AEAVAbstractDomElement@@@Z`
- size: `1784`
- prototype: `void __fastcall(ManifestProcessor *__hidden this, const struct _GUID *, struct AbstractDomElement *)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, installer_update`

## callers

- `0x140017618`

## callees

- `0x140003480`
- `0x140004ab0`
- `0x140005c9c`
- `0x140005f20`
- `0x140008170`
- `0x14000cc80`
- `0x1400178bc`
- `0x1400182c4`
- `0x1400184ac`
- `0x14001853c`
- `0x14001b398`
- `0x14001eb9c`
- `0x1400203a8`
- `0x140021b00`
- `0x140022cec`
- `0x14002a9b0`
- `0x14002a9e0`
- `0x14002b2a8`
- `0x14002ba80`
- `0x14002bd08`
- `0x14002f6c8`
- `0x140031810`
- `0x140034010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140017bc7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140017be0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140017bfb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140017c16`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140017c98`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140017cb8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140017cd0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140017bc7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140017be0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140017bfb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140017c16`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140017c98`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140017cb8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140017cd0`

## string_xrefs

- `0x140017d6b`: `access`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall ManifestProcessor::InstallChannel(
        ManifestProcessor *this,
        const struct _GUID *a2,
        struct AbstractDomElement *a3)
{
  struct AbstractDomElement *v3; // r12
  const char *v5; // r8
  __int64 v6; // rax
  const struct std::nothrow_t *v7; // rdx
  __int64 v8; // rdi
  __int64 v9; // rbx
  int v10; // eax
  void *v11; // rax
  __int64 v12; // rdi
  ChannelConfigReader *v13; // rbx
  __int64 v14; // rax
  char v15; // r13
  _QWORD *v16; // rbx
  __int64 v17; // rax
  const char *v18; // r8
  __int64 v19; // rbx
  int v20; // eax
  _QWORD *v21; // rbx
  __int64 v22; // rbx
  __int64 v23; // rax
  const char *v24; // r8
  _QWORD *v25; // rbx
  __int64 v26; // rax
  __int64 v27; // rcx
  __int128 v28; // xmm0
  struct AbstractDomElement **v29; // rbx
  ManifestProcessor *v30; // rcx
  const wchar_t *v31; // rdx
  int v32; // eax
  __int64 v33; // rax
  const char *v34; // r8
  _QWORD v35[2]; // [rsp+30h] [rbp-99h] BYREF
  int v36[4]; // [rsp+40h] [rbp-89h] BYREF
  __int64 v37; // [rsp+50h] [rbp-79h] BYREF
  struct AbstractDomElement *v38; // [rsp+58h] [rbp-71h] BYREF
  ManifestProcessor *v39; // [rsp+60h] [rbp-69h]
  ChannelConfigReader *v40; // [rsp+68h] [rbp-61h] BYREF
  __int64 v41; // [rsp+70h] [rbp-59h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+78h] [rbp-51h] BYREF
  __int16 v43; // [rsp+A0h] [rbp-29h] BYREF
  _DWORD v44[19]; // [rsp+A2h] [rbp-27h] BYREF

  v3 = a3;
  v39 = this;
  v43 = 123;
  LOBYTE(a3) = 1;
  tlx::guid_to_string_lower<wchar_t>(v44, a2, a3);
  v44[18] = 125;
  (*(void (__fastcall **)(struct AbstractDomElement *, __int64 *, const wchar_t *))(*(_QWORD *)v3 + 40LL))(
    v3,
    &v37,
    L"name");
  if ( !v37 )
  {
    eventlog::ai::WarningMessage((eventlog::ai *)0x47, (unsigned int)&v43);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 13);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, 0xDu, v5, 589);
    throw (EvtException *)pExceptionObject;
  }
  v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  v8 = v6;
  v9 = -1;
  do
    ++v9;
  while ( *(_WORD *)(v6 + 2 * v9) );
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      40,
      (unsigned int)&WPP_e92a5620c3b931af6feebe90701252ca_Traceguids,
      v10,
      (__int64)&v43);
  }
  v11 = operator new(0x168u, v7);
  v41 = (__int64)v11;
  if ( v11 )
  {
    *(_QWORD *)v36 = v8;
    *(_QWORD *)&v36[2] = v9;
    v12 = ChannelConfigWriter::ChannelConfigWriter((__int64)v11, v36, 0, *((_BYTE *)v39 + 1), *((HKEY *)v39 + 1));
  }
  else
  {
    v12 = 0;
  }
  v41 = v12;
  ChannelConfigWriter::GetChannelConfigReader(v12, &v40);
  *(struct _GUID *)v12 = *a2;
  *(_BYTE *)(v12 + 253) |= 1u;
  v13 = v40;
  *(_BYTE *)(v12 + 236) = *(_BYTE *)(v12 + 236) & 0xFE | (*((_BYTE *)v40 + 140) == 1);
  (*(void (__fastcall **)(struct AbstractDomElement *, _QWORD *, const wchar_t *))(*(_QWORD *)v3 + 40LL))(
    v3,
    v35,
    L"enabled");
  if ( v35[0] )
    v14 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v35[0] + 16LL))(v35[0]);
  else
    v14 = 0;
  v15 = ParseXmlBooleanString(v14);
  if ( !ChannelConfigReader::GetRawEnabled(v13) )
  {
    *(_BYTE *)(v12 + 56) = v15;
    *(_BYTE *)(v12 + 232) |= 1u;
  }
  v16 = (_QWORD *)(*(__int64 (__fastcall **)(struct AbstractDomElement *, int *, const wchar_t *))(*(_QWORD *)v3 + 40LL))(
                    v3,
                    v36,
                    L"type");
  wmi::AutoRef<AbstractDomAttribute>::Release(v35);
  v35[0] = *v16;
  *v16 = 0;
  wmi::AutoRef<AbstractDomAttribute>::Release(v36);
  if ( !v35[0] )
  {
    v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    eventlog::ai::WarningMessage((eventlog::ai *)0x48, (unsigned int)&v43, v17);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 13);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, 0xDu, v18, 636);
    throw (EvtException *)pExceptionObject;
  }
  v19 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v35[0] + 16LL))(v35[0]);
  if ( (unsigned int)_o__wcsicmp(v19, L"Admin") )
  {
    if ( (unsigned int)_o__wcsicmp(v19, L"Operational") )
    {
      if ( (unsigned int)_o__wcsicmp(v19, L"Analytic") )
      {
        if ( (unsigned int)_o__wcsicmp(v19, L"Debug") )
        {
          v33 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
          eventlog::ai::WarningMessage((eventlog::ai *)0x4A, (unsigned int)&v43, v33, v19);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 13);
          }
          EvtException::EvtException((EvtException *)pExceptionObject, 0xDu, v34, 659);
          throw (EvtException *)pExceptionObject;
        }
        v20 = 3;
      }
      else
      {
        v20 = 2;
      }
    }
    else
    {
      v20 = 1;
    }
  }
  else
  {
    v20 = 0;
  }
  *(_DWORD *)(v12 + 48) = v20;
  *(_BYTE *)(v12 + 234) |= 1u;
  v21 = (_QWORD *)(*(__int64 (__fastcall **)(struct AbstractDomElement *, int *, const wchar_t *))(*(_QWORD *)v3 + 40LL))(
                    v3,
                    v36,
                    L"isolation");
  wmi::AutoRef<AbstractDomAttribute>::Release(v35);
  v35[0] = *v21;
  *v21 = 0;
  wmi::AutoRef<AbstractDomAttribute>::Release(v36);
  if ( !v35[0] )
    goto LABEL_46;
  v22 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v35[0] + 16LL))(v35[0]);
  if ( !(unsigned int)_o__wcsicmp(v22, L"System") )
  {
    *(_DWORD *)(v12 + 52) = 1;
    goto LABEL_47;
  }
  if ( (unsigned int)_o__wcsicmp(v22, L"Application") )
  {
    if ( (unsigned int)_o__wcsicmp(v22, L"Custom") )
    {
      v23 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      eventlog::ai::WarningMessage((eventlog::ai *)0x4B, (unsigned int)&v43, v23, v22);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 13);
      }
      EvtException::EvtException((EvtException *)pExceptionObject, 0xDu, v24, 684);
      throw (EvtException *)pExceptionObject;
    }
    *(_DWORD *)(v12 + 52) = 2;
  }
  else
  {
LABEL_46:
    *(_DWORD *)(v12 + 52) = 0;
  }
LABEL_47:
  *(_BYTE *)(v12 + 233) |= 1u;
  v25 = (_QWORD *)(*(__int64 (__fastcall **)(struct AbstractDomElement *, int *, const wchar_t *))(*(_QWORD *)v3 + 40LL))(
                    v3,
                    v36,
                    L"access");
  wmi::AutoRef<AbstractDomAttribute>::Release(v35);
  v35[0] = *v25;
  *v25 = 0;
  wmi::AutoRef<AbstractDomAttribute>::Release(v36);
  if ( v35[0] )
  {
    v26 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v35[0] + 16LL))(v35[0]);
    v27 = -1;
    do
      ++v27;
    while ( *(_WORD *)(v26 + 2 * v27) );
    *(_QWORD *)v36 = v26;
    *(_QWORD *)&v36[2] = v27;
  }
  else
  {
    if ( *(_DWORD *)(v12 + 52) == 1 )
      v28 = *(_OWORD *)&off_1400353B8;
    else
      v28 = *(_OWORD *)&off_1400350D0;
    *(_OWORD *)v36 = v28;
  }
  ChannelConfigWriteData::SetChannelAccessSddl(v12, v36);
  (*(void (__fastcall **)(struct AbstractDomElement *, struct AbstractDomElement **, const wchar_t *))(*(_QWORD *)v3 + 32LL))(
    v3,
    &v38,
    L"publishing");
  if ( v38 )
    ManifestProcessor::ProcessChannelPublishingConfig(v39, v38, (struct ChannelConfigWriteData *)v12);
  v29 = (struct AbstractDomElement **)(*(__int64 (__fastcall **)(struct AbstractDomElement *, int *, const wchar_t *))(*(_QWORD *)v3 + 32LL))(
                                        v3,
                                        v36,
                                        L"logging");
  wmi::AutoRef<AbstractDomElement>::~AutoRef<AbstractDomElement>(&v38);
  v38 = *v29;
  *v29 = 0;
  wmi::AutoRef<AbstractDomElement>::~AutoRef<AbstractDomElement>(v36);
  if ( v38 )
    ManifestProcessor::ProcessChannelLogConfig(v30, v38, (struct ChannelConfigWriteData *)v12);
  ChannelConfigWriter::Validate((ChannelConfigWriter *)v12, 1);
  LOBYTE(v31) = 1;
  ChannelConfigWriter::Save((ChannelConfigWriter *)v12, v31);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v32 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      44,
      (unsigned int)&WPP_e92a5620c3b931af6feebe90701252ca_Traceguids,
      v32,
      (__int64)&v43);
  }
  wmi::AutoRef<AbstractDomElement>::~AutoRef<AbstractDomElement>(&v38);
  wmi::AutoRef<AbstractDomAttribute>::Release(v35);
  utl::unique_ptr<ChannelConfigReader,utl::default_delete<ChannelConfigReader>>::~unique_ptr<ChannelConfigReader,utl::default_delete<ChannelConfigReader>>(&v40);
  utl::unique_ptr<ChannelConfigWriter,utl::default_delete<ChannelConfigWriter>>::~unique_ptr<ChannelConfigWriter,utl::default_delete<ChannelConfigWriter>>(&v41);
  wmi::AutoRef<AbstractDomAttribute>::Release(&v37);
}

```

## disassembly

```asm
0x1400178bc  mov     [rsp-8+arg_8], rbx
0x1400178c1  mov     [rsp-8+arg_18], rsi
0x1400178c6  push    rbp
0x1400178c7  push    rdi
0x1400178c8  push    r12
0x1400178ca  push    r13
0x1400178cc  push    r15
0x1400178ce  lea     rbp, [rsp-37h]
0x1400178d3  sub     rsp, 100h
0x1400178da  mov     rax, cs:__security_cookie
0x1400178e1  xor     rax, rsp
0x1400178e4  mov     [rbp+57h+var_30], rax
0x1400178e8  mov     r12, r8
0x1400178eb  mov     r13, rdx
0x1400178ee  mov     [rbp+57h+var_C0], rcx
0x1400178f2  xor     esi, esi
0x1400178f4  lea     eax, [rsi+7Bh]
0x1400178f7  mov     word ptr [rbp+57h+var_80], ax
0x1400178fb  mov     r8b, 1
0x1400178fe  lea     rcx, [rbp+57h+var_80+2]
0x140017902  call    ??$guid_to_string_lower@_W@tlx@@YAXPEA_WAEBU_GUID@@_N@Z; tlx::guid_to_string_lower<wchar_t>(wchar_t *,_GUID const &,bool)
0x140017907  mov     [rbp+57h+var_36], 7Dh ; '}'
0x14001790e  mov     rax, [r12]
0x140017912  lea     r8, aName_0; "name"
0x140017919  lea     rdx, [rbp+57h+var_D0]
0x14001791d  mov     rcx, r12
0x140017920  mov     rax, [rax+28h]
0x140017924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017929  nop
0x14001792a  mov     rcx, [rbp+57h+var_D0]
0x14001792e  test    rcx, rcx
0x140017931  jnz     short loc_14001799C
0x140017933  lea     rdx, [rbp+57h+var_80]; unsigned int
0x140017937  lea     ecx, [rsi+47h]; this
0x14001793a  call    ?WarningMessage@ai@eventlog@@YAXIZZ; eventlog::ai::WarningMessage(uint,...)
0x14001793f  lea     r15, WPP_GLOBAL_Control
0x140017946  lea     ebx, [rsi+0Dh]
0x140017949  mov     rcx, cs:WPP_GLOBAL_Control
0x140017950  cmp     rcx, r15
0x140017953  jz      short loc_14001797A
0x140017955  mov     sil, 4
0x140017958  test    [rcx+1Ch], sil
0x14001795c  jz      short loc_14001797A
0x14001795e  cmp     byte ptr [rcx+19h], 2
0x140017962  jb      short loc_14001797A
0x140017964  lea     edx, [rbx+1Ah]
0x140017967  mov     r9d, ebx
0x14001796a  lea     r8, WPP_e92a5620c3b931af6feebe90701252ca_Traceguids
0x140017971  mov     rcx, [rcx+10h]
0x140017975  call    WPP_SF_d
0x14001797a  mov     r9d, 24Dh; int
0x140017980  mov     edx, ebx; unsigned int
0x140017982  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140017986  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x14001798b  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140017992  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140017996  call    _CxxThrowException_0
0x14001799c  mov     rax, [rcx]
0x14001799f  mov     rax, [rax+10h]
0x1400179a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400179a8  mov     rdi, rax
0x1400179ab  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400179af  inc     rbx
0x1400179b2  cmp     [rax+rbx*2], si
0x1400179b6  jnz     short loc_1400179AF
0x1400179b8  lea     r15, WPP_GLOBAL_Control
0x1400179bf  mov     sil, 4
0x1400179c2  mov     rax, cs:WPP_GLOBAL_Control
0x1400179c9  cmp     rax, r15
0x1400179cc  jz      short loc_140017A12
0x1400179ce  test    [rax+1Ch], sil
0x1400179d2  jz      short loc_140017A12
0x1400179d4  cmp     byte ptr [rax+19h], 5
0x1400179d8  jb      short loc_140017A12
0x1400179da  mov     rcx, [rbp+57h+var_D0]
0x1400179de  mov     rax, [rcx]
0x1400179e1  mov     rax, [rax+10h]
0x1400179e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400179ea  mov     edx, 28h ; '('
0x1400179ef  lea     rcx, [rbp+57h+var_80]
0x1400179f3  mov     [rsp+120h+var_100], rcx
0x1400179f8  mov     r9, rax
0x1400179fb  lea     r8, WPP_e92a5620c3b931af6feebe90701252ca_Traceguids
0x140017a02  mov     rcx, cs:WPP_GLOBAL_Control
0x140017a09  mov     rcx, [rcx+10h]
0x140017a0d  call    WPP_SF_SS
0x140017a12  mov     ecx, 168h; unsigned __int64
0x140017a17  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140017a1c  mov     [rbp+57h+var_B0], rax
0x140017a20  test    rax, rax
0x140017a23  jz      short loc_140017A55
0x140017a25  mov     qword ptr [rsp+120h+var_E0], rdi
0x140017a2a  mov     qword ptr [rsp+120h+var_E0+8], rbx
0x140017a2f  mov     rdx, [rbp+57h+var_C0]
0x140017a33  mov     rcx, [rdx+8]
0x140017a37  mov     [rsp+120h+var_100], rcx; HKEY
0x140017a3c  mov     r9b, [rdx+1]; int
0x140017a40  xor     r8d, r8d; int
0x140017a43  lea     rdx, [rsp+120h+var_E0]; int
0x140017a48  mov     rcx, rax; int
0x140017a4b  call    ??0ChannelConfigWriter@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@K_NPEAX@Z; ChannelConfigWriter::ChannelConfigWriter(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,ulong,bool,void *)
0x140017a50  mov     rdi, rax
0x140017a53  jmp     short loc_140017A57
0x140017a55  xor     edi, edi
0x140017a57  mov     [rbp+57h+var_B0], rdi
0x140017a5b  lea     rdx, [rbp+57h+var_B8]
0x140017a5f  mov     rcx, rdi
0x140017a62  call    ?GetChannelConfigReader@ChannelConfigWriter@@QEAA?AV?$unique_ptr@VChannelConfigReader@@U?$default_delete@VChannelConfigReader@@@utl@@@utl@@XZ; ChannelConfigWriter::GetChannelConfigReader(void)
0x140017a67  nop
0x140017a68  movups  xmm0, xmmword ptr [r13+0]
0x140017a6d  movdqu  xmmword ptr [rdi], xmm0
0x140017a71  or      byte ptr [rdi+0FDh], 1
0x140017a78  mov     rbx, [rbp+57h+var_B8]
0x140017a7c  cmp     byte ptr [rbx+8Ch], 1
0x140017a83  setz    cl
0x140017a86  mov     al, [rdi+0ECh]
0x140017a8c  and     al, 0FEh
0x140017a8e  or      cl, al
0x140017a90  mov     [rdi+0ECh], cl
0x140017a96  mov     rax, [r12]
0x140017a9a  lea     r8, aEnabled_0; "enabled"
0x140017aa1  lea     rdx, [rsp+120h+var_F0]
0x140017aa6  mov     rcx, r12
0x140017aa9  mov     rax, [rax+28h]
0x140017aad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017ab2  nop
0x140017ab3  mov     rcx, [rsp+120h+var_F0]
0x140017ab8  test    rcx, rcx
0x140017abb  jnz     short loc_140017AC1
0x140017abd  xor     eax, eax
0x140017abf  jmp     short loc_140017ACD
0x140017ac1  mov     rax, [rcx]
0x140017ac4  mov     rax, [rax+10h]
0x140017ac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017acd  mov     rcx, rax
0x140017ad0  call    ParseXmlBooleanString
0x140017ad5  mov     r13b, al
0x140017ad8  mov     rcx, rbx; this
0x140017adb  call    ?GetRawEnabled@ChannelConfigReader@@QEBA_NXZ; ChannelConfigReader::GetRawEnabled(void)
0x140017ae0  test    al, al
0x140017ae2  jnz     short loc_140017AEF
0x140017ae4  mov     [rdi+38h], r13b
0x140017ae8  or      byte ptr [rdi+0E8h], 1
0x140017aef  mov     rax, [r12]
0x140017af3  lea     r8, aType; "type"
0x140017afa  lea     rdx, [rsp+120h+var_E0]
0x140017aff  mov     rcx, r12
0x140017b02  mov     rax, [rax+28h]
0x140017b06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017b0b  mov     rbx, rax
0x140017b0e  lea     rcx, [rsp+120h+var_F0]
0x140017b13  call    ?Release@?$AutoRef@VAbstractDomAttribute@@@wmi@@QEAAXXZ; wmi::AutoRef<AbstractDomAttribute>::Release(void)
0x140017b18  mov     rcx, [rbx]
0x140017b1b  mov     [rsp+120h+var_F0], rcx
0x140017b20  xor     r13d, r13d
0x140017b23  mov     [rbx], r13
0x140017b26  lea     rcx, [rsp+120h+var_E0]
0x140017b2b  call    ?Release@?$AutoRef@VAbstractDomAttribute@@@wmi@@QEAAXXZ; wmi::AutoRef<AbstractDomAttribute>::Release(void)
0x140017b30  mov     rcx, [rsp+120h+var_F0]
0x140017b35  test    rcx, rcx
0x140017b38  jnz     short loc_140017BAE
0x140017b3a  mov     rcx, [rbp+57h+var_D0]
0x140017b3e  mov     rax, [rcx]
0x140017b41  mov     rax, [rax+10h]
0x140017b45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017b4a  mov     r8, rax
0x140017b4d  lea     rdx, [rbp+57h+var_80]; unsigned int
0x140017b51  lea     ecx, [r13+48h]; this
0x140017b55  call    ?WarningMessage@ai@eventlog@@YAXIZZ; eventlog::ai::WarningMessage(uint,...)
0x140017b5a  lea     ebx, [r13+0Dh]
0x140017b5e  mov     rcx, cs:WPP_GLOBAL_Control
0x140017b65  cmp     rcx, r15
0x140017b68  jz      short loc_140017B8C
0x140017b6a  test    [rcx+1Ch], sil
0x140017b6e  jz      short loc_140017B8C
0x140017b70  cmp     byte ptr [rcx+19h], 2
0x140017b74  jb      short loc_140017B8C
0x140017b76  lea     edx, [rbx+1Ch]
0x140017b79  mov     r9d, ebx
0x140017b7c  lea     r8, WPP_e92a5620c3b931af6feebe90701252ca_Traceguids
0x140017b83  mov     rcx, [rcx+10h]
0x140017b87  call    WPP_SF_d
0x140017b8c  mov     r9d, 27Ch; int
0x140017b92  mov     edx, ebx; unsigned int
0x140017b94  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140017b98  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x140017b9d  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140017ba4  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140017ba8  call    _CxxThrowException_0
0x140017bae  mov     rax, [rcx]
0x140017bb1  mov     rax, [rax+10h]
0x140017bb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017bba  mov     rbx, rax
0x140017bbd  lea     rdx, aAdmin; "Admin"
0x140017bc4  mov     rcx, rax
0x140017bc7  call    cs:__imp__o__wcsicmp
0x140017bcd  test    eax, eax
0x140017bcf  jnz     short loc_140017BD6
0x140017bd1  mov     eax, r13d
0x140017bd4  jmp     short loc_140017C29
0x140017bd6  lea     rdx, aOperational; "Operational"
0x140017bdd  mov     rcx, rbx
0x140017be0  call    cs:__imp__o__wcsicmp
0x140017be6  test    eax, eax
0x140017be8  jnz     short loc_140017BF1
0x140017bea  mov     eax, 1
0x140017bef  jmp     short loc_140017C29
0x140017bf1  lea     rdx, aAnalytic; "Analytic"
0x140017bf8  mov     rcx, rbx
0x140017bfb  call    cs:__imp__o__wcsicmp
0x140017c01  test    eax, eax
0x140017c03  jnz     short loc_140017C0C
0x140017c05  mov     eax, 2
0x140017c0a  jmp     short loc_140017C29
0x140017c0c  lea     rdx, aDebug; "Debug"
0x140017c13  mov     rcx, rbx
0x140017c16  call    cs:__imp__o__wcsicmp
0x140017c1c  test    eax, eax
0x140017c1e  jnz     loc_140017F3B
0x140017c24  mov     eax, 3
0x140017c29  mov     [rdi+30h], eax
0x140017c2c  or      byte ptr [rdi+0EAh], 1
0x140017c33  mov     rax, [r12]
0x140017c37  lea     r8, aIsolation_0; "isolation"
0x140017c3e  lea     rdx, [rsp+120h+var_E0]
0x140017c43  mov     rcx, r12
0x140017c46  mov     rax, [rax+28h]
0x140017c4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017c4f  mov     rbx, rax
0x140017c52  lea     rcx, [rsp+120h+var_F0]
0x140017c57  call    ?Release@?$AutoRef@VAbstractDomAttribute@@@wmi@@QEAAXXZ; wmi::AutoRef<AbstractDomAttribute>::Release(void)
0x140017c5c  mov     rcx, [rbx]
0x140017c5f  mov     [rsp+120h+var_F0], rcx
0x140017c64  mov     [rbx], r13
0x140017c67  lea     rcx, [rsp+120h+var_E0]
0x140017c6c  call    ?Release@?$AutoRef@VAbstractDomAttribute@@@wmi@@QEAAXXZ; wmi::AutoRef<AbstractDomAttribute>::Release(void)
0x140017c71  mov     rcx, [rsp+120h+var_F0]
0x140017c76  test    rcx, rcx
0x140017c79  jz      loc_140017D5C
0x140017c7f  mov     rax, [rcx]
0x140017c82  mov     rax, [rax+10h]
0x140017c86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017c8b  mov     rbx, rax
0x140017c8e  lea     rdx, aSystem; "System"
0x140017c95  mov     rcx, rax
0x140017c98  call    cs:__imp__o__wcsicmp
0x140017c9e  test    eax, eax
0x140017ca0  jnz     short loc_140017CAE
0x140017ca2  mov     dword ptr [rdi+34h], 1
0x140017ca9  jmp     loc_140017D60
0x140017cae  lea     rdx, aApplication; "Application"
0x140017cb5  mov     rcx, rbx
0x140017cb8  call    cs:__imp__o__wcsicmp
0x140017cbe  test    eax, eax
0x140017cc0  jz      loc_140017D5C
0x140017cc6  lea     rdx, String2; "Custom"
0x140017ccd  mov     rcx, rbx
0x140017cd0  call    cs:__imp__o__wcsicmp
0x140017cd6  test    eax, eax
0x140017cd8  jnz     short loc_140017CE3
0x140017cda  mov     dword ptr [rdi+34h], 2
0x140017ce1  jmp     short loc_140017D60
0x140017ce3  mov     rcx, [rbp+57h+var_D0]
0x140017ce7  mov     rax, [rcx]
0x140017cea  mov     rax, [rax+10h]
0x140017cee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017cf3  mov     r8, rax
0x140017cf6  mov     r9, rbx
0x140017cf9  lea     rdx, [rbp+57h+var_80]; unsigned int
0x140017cfd  mov     ecx, 4Bh ; 'K'; this
0x140017d02  call    ?WarningMessage@ai@eventlog@@YAXIZZ; eventlog::ai::WarningMessage(uint,...)
0x140017d07  mov     ebx, 0Dh
0x140017d0c  mov     rcx, cs:WPP_GLOBAL_Control
0x140017d13  cmp     rcx, r15
0x140017d16  jz      short loc_140017D3A
0x140017d18  test    [rcx+1Ch], sil
0x140017d1c  jz      short loc_140017D3A
0x140017d1e  cmp     byte ptr [rcx+19h], 2
0x140017d22  jb      short loc_140017D3A
0x140017d24  lea     edx, [rbx+1Eh]
0x140017d27  mov     r9d, ebx
0x140017d2a  lea     r8, WPP_e92a5620c3b931af6feebe90701252ca_Traceguids
0x140017d31  mov     rcx, [rcx+10h]
0x140017d35  call    WPP_SF_d
0x140017d3a  mov     r9d, 2ACh; int
0x140017d40  mov     edx, ebx; unsigned int
0x140017d42  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140017d46  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x140017d4b  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140017d52  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140017d56  call    _CxxThrowException_0
0x140017d5c  mov     [rdi+34h], r13d
0x140017d60  or      byte ptr [rdi+0E9h], 1
0x140017d67  mov     rax, [r12]
0x140017d6b  lea     r8, aAccess_0; "access"
0x140017d72  lea     rdx, [rsp+120h+var_E0]
0x140017d77  mov     rcx, r12
0x140017d7a  mov     rax, [rax+28h]
0x140017d7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017d83  mov     rbx, rax
  ... truncated ...
```
