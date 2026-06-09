# PublisherConfigWriter::PublisherConfigWriter(_GUID const &,ulong,_SECURITY_ATTRIBUTES *,HKEY__ *,void *)

- ea: `0x14002ecf4`
- end: `0x14002ef3c`
- name: `??0PublisherConfigWriter@@QEAA@AEBU_GUID@@KPEAU_SECURITY_ATTRIBUTES@@PEAUHKEY__@@PEAX@Z`
- size: `584`
- prototype: `PublisherConfigWriter *(PublisherConfigWriter *__hidden this, const struct _GUID *, unsigned int, struct _SECURITY_ATTRIBUTES *, HKEY, void *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14001663c`

## callees

- `0x140004ae0`
- `0x140005600`
- `0x140005a80`
- `0x140006db0`
- `0x1400099c8`
- `0x14000a4d8`
- `0x140021b00`
- `0x140022510`
- `0x140022cec`
- `0x14002c8ac`
- `0x14002ecf4`
- `0x140031810`

## import_xrefs

- `ntdll!RtlGetVersion` at `0x14002ee4c`
- `ntdll!RtlGetVersion` at `0x14002ee4c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
PublisherConfigWriter *__fastcall PublisherConfigWriter::PublisherConfigWriter(
        PublisherConfigWriter *this,
        const struct _GUID *a2,
        REGSAM a3,
        struct _SECURITY_ATTRIBUTES *a4,
        HKEY a5,
        void *a6)
{
  __int64 v10; // r8
  __int64 v11; // r8
  __int64 v12; // r8
  __int64 v13; // r8
  __int64 v14; // r8
  __int64 v15; // r8
  __int64 v16; // r8
  int v17; // esi
  HKEY *v18; // rax
  unsigned int RegKey; // ebx
  __int16 *pExceptionObject; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v22; // [rsp+48h] [rbp-B8h]
  __int64 v23; // [rsp+50h] [rbp-B0h]
  unsigned int v24; // [rsp+58h] [rbp-A8h]
  __int64 v25; // [rsp+5Ch] [rbp-A4h]
  char v26; // [rsp+64h] [rbp-9Ch]
  PublisherConfigWriter *v27; // [rsp+68h] [rbp-98h]
  wchar_t *v28[4]; // [rsp+70h] [rbp-90h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+90h] [rbp-70h] BYREF

  v27 = this;
  PublisherConfigReader::PublisherConfigReader(this, a6);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>((char *)this + 144);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v10 + 32);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v11 + 64);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v12 + 96);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v13 + 128);
  utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(v14 + 160);
  *(_QWORD *)(v15 + 184) = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v28);
  LOBYTE(v16) = 1;
  v17 = tlx::assign_guid<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v28, a2, v16);
  if ( v17 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_06fac479fca53b99d55b1e2801ac1dd1_Traceguids,
        (unsigned int)v17);
    }
    pExceptionObject = word_14003838A;
    v22 = 0;
    v23 = 0;
    v24 = v17;
    v25 = -1;
    v26 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  *((struct _GUID *)this + 1) = *a2;
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x110u);
  VersionInformation.dwOSVersionInfoSize = 276;
  if ( RtlGetVersion(&VersionInformation) >= 0
    && (VersionInformation.dwMajorVersion > 6
     || VersionInformation.dwMajorVersion == 6 && VersionInformation.dwMinorVersion) )
  {
    a3 |= 0x100u;
  }
  v18 = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>((HKEY *)this);
  RegKey = CreateRegKey(a5, v28[0], a3, a4, v18, 0, a6);
  if ( RegKey )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_06fac479fca53b99d55b1e2801ac1dd1_Traceguids, RegKey);
    }
    pExceptionObject = word_14003838A;
    v22 = 0;
    v23 = 0;
    v24 = RegKey;
    v25 = -1;
    v26 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v28);
  return this;
}

```

## disassembly

```asm
0x14002ecf4  push    rbp
0x14002ecf6  push    rbx
0x14002ecf7  push    rsi
0x14002ecf8  push    rdi
0x14002ecf9  push    r12
0x14002ecfb  push    r13
0x14002ecfd  push    r14
0x14002ecff  push    r15
0x14002ed01  lea     rbp, [rsp-0C8h]
0x14002ed09  sub     rsp, 1C8h
0x14002ed10  mov     rax, cs:__security_cookie
0x14002ed17  xor     rax, rsp
0x14002ed1a  mov     [rbp+100h+var_50], rax
0x14002ed21  mov     r12, r9
0x14002ed24  mov     ebx, r8d
0x14002ed27  mov     r14, rdx
0x14002ed2a  mov     rdi, rcx
0x14002ed2d  mov     [rsp+200h+var_198], rcx
0x14002ed32  mov     r13, [rbp+100h+arg_20]
0x14002ed39  mov     r15, [rbp+100h+arg_28]
0x14002ed40  mov     rdx, r15; void *
0x14002ed43  call    ??0PublisherConfigReader@@IEAA@PEAX@Z; PublisherConfigReader::PublisherConfigReader(void *)
0x14002ed48  nop
0x14002ed49  lea     r8, [rdi+90h]
0x14002ed50  mov     rcx, r8
0x14002ed53  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14002ed58  lea     rcx, [r8+20h]
0x14002ed5c  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14002ed61  lea     rcx, [r8+40h]
0x14002ed65  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14002ed6a  lea     rcx, [r8+60h]
0x14002ed6e  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14002ed73  lea     rcx, [r8+80h]
0x14002ed7a  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14002ed7f  lea     rcx, [r8+0A0h]
0x14002ed86  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(void)
0x14002ed8b  xor     eax, eax
0x14002ed8d  mov     [r8+0B8h], rax
0x14002ed94  lea     rcx, [rsp+200h+var_190]
0x14002ed99  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14002ed9e  nop
0x14002ed9f  mov     r8b, 1
0x14002eda2  mov     rdx, r14
0x14002eda5  lea     rcx, [rsp+200h+var_190]
0x14002edaa  call    ??$assign_guid@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEBU_GUID@@_N@Z; tlx::assign_guid<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,_GUID const &,bool)
0x14002edaf  mov     esi, eax
0x14002edb1  test    eax, eax
0x14002edb3  jns     short loc_14002EE27
0x14002edb5  lea     rax, WPP_GLOBAL_Control
0x14002edbc  mov     rcx, cs:WPP_GLOBAL_Control
0x14002edc3  cmp     rcx, rax
0x14002edc6  jz      short loc_14002EDEC
0x14002edc8  test    byte ptr [rcx+1Ch], 4
0x14002edcc  jz      short loc_14002EDEC
0x14002edce  cmp     byte ptr [rcx+19h], 2
0x14002edd2  jb      short loc_14002EDEC
0x14002edd4  mov     edx, 0Ah
0x14002edd9  mov     r9d, esi
0x14002eddc  lea     r8, WPP_06fac479fca53b99d55b1e2801ac1dd1_Traceguids
0x14002ede3  mov     rcx, [rcx+10h]
0x14002ede7  call    WPP_SF_d
0x14002edec  lea     rax, word_14003838A
0x14002edf3  mov     [rsp+200h+pExceptionObject], rax
0x14002edf8  xor     eax, eax
0x14002edfa  mov     [rsp+200h+var_1B8], rax
0x14002edff  mov     [rsp+200h+var_1B0], rax
0x14002ee04  mov     [rsp+200h+var_1A8], esi
0x14002ee08  mov     [rsp+200h+var_1A4], 0FFFFFFFFFFFFFFFFh
0x14002ee11  mov     [rsp+200h+var_19C], al
0x14002ee15  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14002ee1c  lea     rcx, [rsp+200h+pExceptionObject]; pExceptionObject
0x14002ee21  call    _CxxThrowException_0
0x14002ee27  movups  xmm0, xmmword ptr [r14]
0x14002ee2b  movdqu  xmmword ptr [rdi+10h], xmm0
0x14002ee30  xor     edx, edx; Val
0x14002ee32  mov     r8d, 110h; Size
0x14002ee38  lea     rcx, [rbp+100h+VersionInformation.dwMajorVersion]; void *
0x14002ee3c  call    memset_0
0x14002ee41  mov     [rbp+100h+VersionInformation.dwOSVersionInfoSize], 114h
0x14002ee48  lea     rcx, [rbp+100h+VersionInformation]; lpVersionInformation
0x14002ee4c  call    cs:__imp_RtlGetVersion
0x14002ee52  xor     esi, esi
0x14002ee54  test    eax, eax
0x14002ee56  js      short loc_14002EE6A
0x14002ee58  cmp     [rbp+100h+VersionInformation.dwMajorVersion], 6
0x14002ee5c  ja      short loc_14002EE66
0x14002ee5e  jnz     short loc_14002EE6A
0x14002ee60  cmp     [rbp+100h+VersionInformation.dwMinorVersion], 1
0x14002ee64  jb      short loc_14002EE6A
0x14002ee66  bts     ebx, 8
0x14002ee6a  mov     rcx, rdi
0x14002ee6d  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14002ee72  mov     [rsp+200h+var_1D0], r15; void *
0x14002ee77  mov     [rsp+200h+var_1D8], rsi; unsigned int *
0x14002ee7c  mov     [rsp+200h+var_1E0], rax; HKEY *
0x14002ee81  mov     r9, r12; struct _SECURITY_ATTRIBUTES *
0x14002ee84  mov     r8d, ebx; unsigned int
0x14002ee87  mov     rdx, [rsp+200h+var_190]; wchar_t *
0x14002ee8c  mov     rcx, r13; HKEY
0x14002ee8f  call    ?CreateRegKey@@YAJPEAUHKEY__@@PEB_WKQEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAKPEAX@Z; CreateRegKey(HKEY__ *,wchar_t const *,ulong,_SECURITY_ATTRIBUTES * const,HKEY__ * *,ulong *,void *)
0x14002ee94  mov     ebx, eax
0x14002ee96  test    eax, eax
0x14002ee98  jz      short loc_14002EF0B
0x14002ee9a  lea     rax, WPP_GLOBAL_Control
0x14002eea1  mov     rcx, cs:WPP_GLOBAL_Control
0x14002eea8  cmp     rcx, rax
0x14002eeab  jz      short loc_14002EED1
0x14002eead  test    byte ptr [rcx+1Ch], 4
0x14002eeb1  jz      short loc_14002EED1
0x14002eeb3  cmp     byte ptr [rcx+19h], 2
0x14002eeb7  jb      short loc_14002EED1
0x14002eeb9  mov     edx, 0Bh
0x14002eebe  mov     r9d, ebx
0x14002eec1  lea     r8, WPP_06fac479fca53b99d55b1e2801ac1dd1_Traceguids
0x14002eec8  mov     rcx, [rcx+10h]
0x14002eecc  call    WPP_SF_d
0x14002eed1  lea     rax, word_14003838A
0x14002eed8  mov     [rsp+200h+pExceptionObject], rax
0x14002eedd  mov     [rsp+200h+var_1B8], rsi
0x14002eee2  mov     [rsp+200h+var_1B0], rsi
0x14002eee7  mov     [rsp+200h+var_1A8], ebx
0x14002eeeb  mov     [rsp+200h+var_1A4], 0FFFFFFFFFFFFFFFFh
0x14002eef4  mov     [rsp+200h+var_19C], sil
0x14002eef9  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14002ef00  lea     rcx, [rsp+200h+pExceptionObject]; pExceptionObject
0x14002ef05  call    _CxxThrowException_0
0x14002ef0b  lea     rcx, [rsp+200h+var_190]
0x14002ef10  call    ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14002ef15  nop
0x14002ef16  mov     rax, rdi
0x14002ef19  mov     rcx, [rbp+100h+var_50]
0x14002ef20  xor     rcx, rsp; StackCookie
0x14002ef23  call    __security_check_cookie
0x14002ef28  add     rsp, 1C8h
0x14002ef2f  pop     r15
0x14002ef31  pop     r14
0x14002ef33  pop     r13
0x14002ef35  pop     r12
0x14002ef37  pop     rdi
0x14002ef38  pop     rsi
0x14002ef39  pop     rbx
0x14002ef3a  pop     rbp
0x14002ef3b  retn
```
