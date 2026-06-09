# ManifestProcessor::ProcessChannelsNode(_GUID const &,AbstractDomElement &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &)

- ea: `0x140017618`
- end: `0x1400178b4`
- name: `?ProcessChannelsNode@ManifestProcessor@@AEAAXAEBU_GUID@@AEAVAbstractDomElement@@AEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `668`
- prototype: `__int64 __fastcall(ManifestProcessor *this, struct _GUID *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, installer_update`

## callers

- `0x14001663c`

## callees

- `0x140003480`
- `0x140004ae0`
- `0x140005600`
- `0x140005a80`
- `0x140008170`
- `0x14000cc80`
- `0x140017618`
- `0x1400178bc`
- `0x140022cec`
- `0x14002ab70`
- `0x14002f6c8`
- `0x140031804`
- `0x140031810`
- `0x140034010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ManifestProcessor::ProcessChannelsNode(
        ManifestProcessor *this,
        struct _GUID *a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v8; // r8
  int v9; // eax
  int v10; // ebx
  struct AbstractDomElement **v11; // rdi
  struct AbstractDomElement *v12; // rbx
  const wchar_t *v13; // rdi
  const char *v14; // r8
  const char *v15; // r8
  struct AbstractDomElement *v17; // [rsp+20h] [rbp-49h] BYREF
  __int64 v18; // [rsp+28h] [rbp-41h] BYREF
  __int64 v19; // [rsp+30h] [rbp-39h] BYREF
  _QWORD pExceptionObject[3]; // [rsp+38h] [rbp-31h] BYREF
  int v21; // [rsp+50h] [rbp-19h]
  __int64 v22; // [rsp+54h] [rbp-15h]
  char v23; // [rsp+5Ch] [rbp-Dh]
  char v24[8]; // [rsp+60h] [rbp-9h] BYREF
  unsigned int v25[2]; // [rsp+68h] [rbp-1h] BYREF

  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v25);
  LOBYTE(v8) = 1;
  v9 = tlx::assign_guid<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v25, a2, v8);
  v10 = v9;
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        49,
        &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids,
        (unsigned int)v9);
    }
    pExceptionObject[0] = word_14003838A;
    pExceptionObject[1] = 0;
    pExceptionObject[2] = 0;
    v21 = v10;
    v22 = -1;
    v23 = 0;
    throw (EvtException *)pExceptionObject;
  }
  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a3 + 24LL))(a3, &v19);
  v17 = 0;
  while ( 1 )
  {
    v11 = (struct AbstractDomElement **)(*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v19 + 8LL))(v19, v24);
    wmi::AutoRef<AbstractDomElement>::~AutoRef<AbstractDomElement>(&v17);
    v17 = *v11;
    v12 = v17;
    *v11 = 0;
    wmi::AutoRef<AbstractDomElement>::~AutoRef<AbstractDomElement>(v24);
    if ( !v12 )
      break;
    v13 = (const wchar_t *)(*(__int64 (__fastcall **)(struct AbstractDomElement *))(*(_QWORD *)v12 + 16LL))(v12);
    if ( !wcscmp_0(L"channel", v13) )
    {
      (*(void (__fastcall **)(struct AbstractDomElement *, __int64 *, const wchar_t *))(*(_QWORD *)v12 + 40LL))(
        v12,
        &v18,
        L"name");
      if ( !v18 )
      {
        eventlog::ai::WarningMessage((eventlog::ai *)0x47, v25[0]);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 13);
        }
        EvtException::EvtException((EvtException *)pExceptionObject, 0xDu, v15, 881);
        throw (EvtException *)pExceptionObject;
      }
      ManifestProcessor::InstallChannel(this, a2, v12);
      wmi::AutoRef<AbstractDomAttribute>::Release(&v18);
    }
    else
    {
      if ( wcscmp_0(L"importChannel", v13) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 13);
        }
        EvtException::EvtException((EvtException *)pExceptionObject, 0xDu, v14, 892);
        throw (EvtException *)pExceptionObject;
      }
      ManifestProcessor::InstallImportedChannel(this, (__int64)v12, (__int64 *)v25, a4);
    }
  }
  wmi::AutoRef<AbstractDomElement>::~AutoRef<AbstractDomElement>(&v17);
  wmi::AutoRef<AbstractDomElement>::~AutoRef<AbstractDomElement>(&v19);
  return utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v25);
}

```

## disassembly

```asm
0x140017618  push    rbp
0x14001761a  push    rbx
0x14001761b  push    rsi
0x14001761c  push    rdi
0x14001761d  push    r14
0x14001761f  push    r15
0x140017621  lea     rbp, [rsp-2Fh]
0x140017626  sub     rsp, 98h
0x14001762d  mov     r15, r9
0x140017630  mov     rdi, r8
0x140017633  mov     r14, rdx
0x140017636  mov     rsi, rcx
0x140017639  lea     rcx, [rbp+57h+var_58]
0x14001763d  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x140017642  nop
0x140017643  mov     r8b, 1
0x140017646  mov     rdx, r14
0x140017649  lea     rcx, [rbp+57h+var_58]
0x14001764d  call    ??$assign_guid@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEBU_GUID@@_N@Z; tlx::assign_guid<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,_GUID const &,bool)
0x140017652  mov     ebx, eax
0x140017654  test    eax, eax
0x140017656  jns     short loc_1400176CC
0x140017658  lea     rcx, WPP_GLOBAL_Control
0x14001765f  mov     r10, cs:WPP_GLOBAL_Control
0x140017666  cmp     r10, rcx
0x140017669  jz      short loc_140017691
0x14001766b  test    byte ptr [r10+1Ch], 4
0x140017670  jz      short loc_140017691
0x140017672  cmp     byte ptr [r10+19h], 2
0x140017677  jb      short loc_140017691
0x140017679  mov     edx, 31h ; '1'
0x14001767e  mov     r9d, eax
0x140017681  lea     r8, WPP_e92a5620c3b931af6feebe90701252ca_Traceguids
0x140017688  mov     rcx, [r10+10h]
0x14001768c  call    WPP_SF_d
0x140017691  lea     rax, word_14003838A
0x140017698  mov     [rbp+57h+pExceptionObject], rax
0x14001769c  mov     [rbp+57h+var_80], 0
0x1400176a4  mov     [rbp+57h+var_78], 0
0x1400176ac  mov     [rbp+57h+var_70], ebx
0x1400176af  mov     [rbp+57h+var_6C], 0FFFFFFFFFFFFFFFFh
0x1400176b7  mov     [rbp+57h+var_64], 0
0x1400176bb  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1400176c2  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1400176c6  call    _CxxThrowException_0
0x1400176cc  mov     rax, [rdi]
0x1400176cf  lea     rdx, [rbp+57h+var_90]
0x1400176d3  mov     rcx, rdi
0x1400176d6  mov     rax, [rax+18h]
0x1400176da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400176df  nop
0x1400176e0  mov     [rbp+57h+var_A0], 0
0x1400176e8  mov     rcx, [rbp+57h+var_90]
0x1400176ec  mov     rax, [rcx]
0x1400176ef  lea     rdx, [rbp+57h+var_60]
0x1400176f3  mov     rax, [rax+8]
0x1400176f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400176fc  mov     rdi, rax
0x1400176ff  lea     rcx, [rbp+57h+var_A0]
0x140017703  call    ??1?$AutoRef@VAbstractDomElement@@@wmi@@QEAA@XZ; wmi::AutoRef<AbstractDomElement>::~AutoRef<AbstractDomElement>(void)
0x140017708  mov     rbx, [rdi]
0x14001770b  mov     [rbp+57h+var_A0], rbx
0x14001770f  mov     qword ptr [rdi], 0
0x140017716  test    rbx, rbx
0x140017719  setnz   dil
0x14001771d  lea     rcx, [rbp+57h+var_60]
0x140017721  call    ??1?$AutoRef@VAbstractDomElement@@@wmi@@QEAA@XZ; wmi::AutoRef<AbstractDomElement>::~AutoRef<AbstractDomElement>(void)
0x140017726  test    dil, dil
0x140017729  jz      loc_140017887
0x14001772f  mov     rax, [rbx]
0x140017732  mov     rcx, rbx
0x140017735  mov     rax, [rax+10h]
0x140017739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001773e  mov     rdi, rax
0x140017741  mov     rdx, rax; String2
0x140017744  lea     rcx, aChannel; "channel"
0x14001774b  call    wcscmp_0
0x140017750  test    eax, eax
0x140017752  jnz     short loc_140017793
0x140017754  mov     rax, [rbx]
0x140017757  lea     r8, aName_0; "name"
0x14001775e  lea     rdx, [rbp+57h+var_98]
0x140017762  mov     rcx, rbx
0x140017765  mov     rax, [rax+28h]
0x140017769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001776e  nop
0x14001776f  cmp     [rbp+57h+var_98], 0
0x140017774  jz      short loc_1400177C1
0x140017776  mov     r8, rbx; struct AbstractDomElement *
0x140017779  mov     rdx, r14; struct _GUID *
0x14001777c  mov     rcx, rsi; this
0x14001777f  call    ?InstallChannel@ManifestProcessor@@AEAAXAEBU_GUID@@AEAVAbstractDomElement@@@Z; ManifestProcessor::InstallChannel(_GUID const &,AbstractDomElement &)
0x140017784  nop
0x140017785  lea     rcx, [rbp+57h+var_98]
0x140017789  call    ?Release@?$AutoRef@VAbstractDomAttribute@@@wmi@@QEAAXXZ; wmi::AutoRef<AbstractDomAttribute>::Release(void)
0x14001778e  jmp     loc_1400176E8
0x140017793  mov     rdx, rdi; String2
0x140017796  lea     rcx, aImportchannel; "importChannel"
0x14001779d  call    wcscmp_0
0x1400177a2  test    eax, eax
0x1400177a4  jnz     loc_14001782B
0x1400177aa  mov     r9, r15
0x1400177ad  lea     r8, [rbp+57h+var_58]
0x1400177b1  mov     rdx, rbx
0x1400177b4  mov     rcx, rsi
0x1400177b7  call    ?InstallImportedChannel@ManifestProcessor@@AEAAXAEAVAbstractDomElement@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEBV34@@Z; ManifestProcessor::InstallImportedChannel(AbstractDomElement &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &)
0x1400177bc  jmp     loc_1400176E8
0x1400177c1  mov     rdx, qword ptr [rbp+57h+var_58]; unsigned int
0x1400177c5  mov     ecx, 47h ; 'G'; this
0x1400177ca  call    ?WarningMessage@ai@eventlog@@YAXIZZ; eventlog::ai::WarningMessage(uint,...)
0x1400177cf  lea     rcx, WPP_GLOBAL_Control
0x1400177d6  mov     ebx, 0Dh
0x1400177db  mov     rax, cs:WPP_GLOBAL_Control
0x1400177e2  cmp     rax, rcx
0x1400177e5  jz      short loc_140017809
0x1400177e7  test    byte ptr [rax+1Ch], 4
0x1400177eb  jz      short loc_140017809
0x1400177ed  cmp     byte ptr [rax+19h], 2
0x1400177f1  jb      short loc_140017809
0x1400177f3  lea     edx, [rbx+25h]
0x1400177f6  mov     r9d, ebx
0x1400177f9  lea     r8, WPP_e92a5620c3b931af6feebe90701252ca_Traceguids
0x140017800  mov     rcx, [rax+10h]
0x140017804  call    WPP_SF_d
0x140017809  mov     r9d, 371h; int
0x14001780f  mov     edx, ebx; unsigned int
0x140017811  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140017815  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x14001781a  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140017821  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140017825  call    _CxxThrowException_0
0x14001782b  lea     rcx, WPP_GLOBAL_Control
0x140017832  mov     ebx, 0Dh
0x140017837  mov     rax, cs:WPP_GLOBAL_Control
0x14001783e  cmp     rax, rcx
0x140017841  jz      short loc_140017865
0x140017843  test    byte ptr [rax+1Ch], 4
0x140017847  jz      short loc_140017865
0x140017849  cmp     byte ptr [rax+19h], 2
0x14001784d  jb      short loc_140017865
0x14001784f  lea     edx, [rbx+26h]
0x140017852  mov     r9d, ebx
0x140017855  lea     r8, WPP_e92a5620c3b931af6feebe90701252ca_Traceguids
0x14001785c  mov     rcx, [rax+10h]
0x140017860  call    WPP_SF_d
0x140017865  mov     r9d, 37Ch; int
0x14001786b  mov     edx, ebx; unsigned int
0x14001786d  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140017871  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x140017876  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14001787d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140017881  call    _CxxThrowException_0
0x140017887  lea     rcx, [rbp+57h+var_A0]
0x14001788b  call    ??1?$AutoRef@VAbstractDomElement@@@wmi@@QEAA@XZ; wmi::AutoRef<AbstractDomElement>::~AutoRef<AbstractDomElement>(void)
0x140017890  nop
0x140017891  lea     rcx, [rbp+57h+var_90]
0x140017895  call    ??1?$AutoRef@VAbstractDomElement@@@wmi@@QEAA@XZ; wmi::AutoRef<AbstractDomElement>::~AutoRef<AbstractDomElement>(void)
0x14001789a  nop
0x14001789b  lea     rcx, [rbp+57h+var_58]
0x14001789f  call    ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1400178a4  add     rsp, 98h
0x1400178ab  pop     r15
0x1400178ad  pop     r14
0x1400178af  pop     rdi
0x1400178b0  pop     rsi
0x1400178b1  pop     rbx
0x1400178b2  pop     rbp
0x1400178b3  retn
```
