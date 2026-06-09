# InstallManifestCommand::ValidateInstalledProviders(MsxmlDomElement &,ulong)

- ea: `0x14000116c`
- end: `0x14000172f`
- name: `?ValidateInstalledProviders@InstallManifestCommand@@AEAAXAEAVMsxmlDomElement@@K@Z`
- size: `1475`
- prototype: `void(InstallManifestCommand *__hidden this, struct MsxmlDomElement *, unsigned int)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140001ce0`

## callees

- `0x14000116c`
- `0x140002b9c`
- `0x140003480`
- `0x140004ae0`
- `0x140005600`
- `0x14000cabc`
- `0x14000d144`
- `0x14000d8c4`
- `0x140010450`
- `0x140011ce0`
- `0x14001a9b8`
- `0x140021b00`
- `0x1400223ae`
- `0x1400226dc`
- `0x140022cec`
- `0x140023c6c`
- `0x140025b2c`
- `0x140027420`
- `0x1400276c0`
- `0x14002f6c8`
- `0x140031810`
- `0x140034010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fflush` at `0x1400014ef`
- `api-ms-win-crt-private-l1-1-0!_o_fflush` at `0x140001701`
- `api-ms-win-crt-private-l1-1-0!_o_fflush` at `0x1400014ef`
- `api-ms-win-crt-private-l1-1-0!_o_fflush` at `0x140001701`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x1400014c8`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x1400016da`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x1400014c8`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x1400016da`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140001202`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140001440`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140001202`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140001440`
- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtOpenPublisherMetadata` at `0x140001417`
- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtOpenPublisherMetadata` at `0x140001417`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall InstallManifestCommand::ValidateInstalledProviders(
        InstallManifestCommand *this,
        struct MsxmlDomElement *a2,
        unsigned int a3)
{
  char Present; // al
  unsigned int ModuleHandleW; // eax
  int v7; // eax
  int v8; // ebx
  wmi::RefBase *v9; // rbx
  wmi::RefBase *v10; // rdi
  wmi::RefBase **v11; // rsi
  const wchar_t *v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rax
  const WCHAR *v15; // rdx
  unsigned int v16; // eax
  int v17; // eax
  int v18; // esi
  const char *v19; // r8
  __int64 v20; // rsi
  __int64 v21; // r14
  HANDLE v22; // rax
  FILE *v23; // rax
  const char *v24; // r8
  __int64 v25; // rbx
  __int64 v26; // rdi
  HANDLE StdHandle; // rax
  FILE *v28; // rax
  const char *Flags; // [rsp+20h] [rbp-A9h]
  __int16 *pExceptionObject; // [rsp+40h] [rbp-89h] BYREF
  __int64 v31; // [rsp+48h] [rbp-81h]
  __int64 v32; // [rsp+50h] [rbp-79h]
  int v33; // [rsp+58h] [rbp-71h]
  __int64 v34; // [rsp+5Ch] [rbp-6Dh]
  char v35; // [rsp+64h] [rbp-65h]
  __int64 v36; // [rsp+68h] [rbp-61h] BYREF
  __int64 v37; // [rsp+70h] [rbp-59h]
  wmi::RefBase *v38; // [rsp+88h] [rbp-41h] BYREF
  _QWORD v39[2]; // [rsp+90h] [rbp-39h] BYREF
  __int64 v40; // [rsp+A0h] [rbp-29h] BYREF
  __int64 v41; // [rsp+A8h] [rbp-21h]
  wmi::RefBase *v42; // [rsp+B0h] [rbp-19h] BYREF
  wmi::RefBase *v43; // [rsp+B8h] [rbp-11h]
  LPCWSTR PublisherId[4]; // [rsp+C0h] [rbp-9h] BYREF

  Present = IsEvtQueryPresent();
  if ( a3 )
  {
    if ( a3 != 126 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_ddf83515f50e3f824a6097176f506b2b_Traceguids, a3);
      }
      EvtException::EvtException((EvtException *)&pExceptionObject, a3, 0, 0, Flags, 84, 0x3Eu, 0);
      throw (EvtException *)&pExceptionObject;
    }
    if ( Present
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11);
    }
    goto LABEL_8;
  }
  if ( !Present )
  {
LABEL_8:
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v36);
    ModuleHandleW = (unsigned int)GetModuleHandleW(0);
    v7 = tlx::append_format_message_args<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
           (unsigned int)&v36,
           0,
           ModuleHandleW,
           89,
           0);
    v8 = v7;
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          &WPP_ddf83515f50e3f824a6097176f506b2b_Traceguids,
          (unsigned int)v7);
      }
      pExceptionObject = word_14003838A;
      v31 = 0;
      v32 = 0;
      v33 = v8;
      v34 = -1;
      v35 = 0;
      throw (EvtException *)&pExceptionObject;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_ddf83515f50e3f824a6097176f506b2b_Traceguids);
    }
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                             &v36,
                             10) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_ddf83515f50e3f824a6097176f506b2b_Traceguids, 14);
      }
      EvtException::EvtException((EvtException *)&pExceptionObject, 0xEu, v24, 139);
      throw (EvtException *)&pExceptionObject;
    }
    v25 = v36;
    v26 = (v37 - v36) >> 1;
    StdHandle = GetStdHandle(0xFFFFFFF5);
    v40 = v25;
    v41 = v26;
    FilePuts(StdHandle, &v40);
    v28 = o___acrt_iob_func_0(1u);
    fflush(v28);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v36);
    return;
  }
  MsxmlDomElement::GetSubElements(a2, &v42);
  v9 = 0;
  v43 = 0;
  v10 = v42;
  while ( 1 )
  {
    v11 = (wmi::RefBase **)(*(__int64 (__fastcall **)(wmi::RefBase *, wmi::RefBase **))(*(_QWORD *)v10 + 8LL))(
                             v10,
                             &v38);
    if ( v9 )
      wmi::RefBase::Release(v9);
    v9 = *v11;
    v43 = *v11;
    *v11 = 0;
    if ( v38 )
      wmi::RefBase::Release(v38);
    v38 = 0;
    if ( !v9 )
      break;
    v12 = (const wchar_t *)(*(__int64 (__fastcall **)(wmi::RefBase *))(*(_QWORD *)v9 + 16LL))(v9);
    v13 = -1;
    do
      ++v13;
    while ( v12[v13] );
    if ( v13 == 8 && !wmemcmp(L"provider", v12, 8u) )
    {
      (*(void (__fastcall **)(wmi::RefBase *, _QWORD *, const wchar_t *))(*(_QWORD *)v9 + 40LL))(v9, v39, L"name");
      if ( v39[0] )
      {
        v14 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v39[0] + 16LL))(v39[0]);
        std::wstring::wstring(PublisherId, v14);
        if ( PublisherId[2] )
        {
          v15 = (const WCHAR *)PublisherId;
          if ( PublisherId[3] > (LPCWSTR)7 )
            v15 = PublisherId[0];
          if ( EvtOpenPublisherMetadata(0, v15, 0, 0, 0) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_ddf83515f50e3f824a6097176f506b2b_Traceguids);
            }
          }
          else
          {
            utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v36);
            v16 = (unsigned int)GetModuleHandleW(0);
            v17 = tlx::append_format_message_args<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                    (unsigned int)&v36,
                    0,
                    v16,
                    69,
                    0);
            v18 = v17;
            if ( v17 < 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  13,
                  &WPP_ddf83515f50e3f824a6097176f506b2b_Traceguids,
                  (unsigned int)v17);
              }
              pExceptionObject = word_14003838A;
              v31 = 0;
              v32 = 0;
              v33 = v18;
              v34 = -1;
              v35 = 0;
              throw (EvtException *)&pExceptionObject;
            }
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
            {
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_ddf83515f50e3f824a6097176f506b2b_Traceguids);
            }
            if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                                     &v36,
                                     10) )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_ddf83515f50e3f824a6097176f506b2b_Traceguids, 14);
              }
              EvtException::EvtException((EvtException *)&pExceptionObject, 0xEu, v19, 114);
              throw (EvtException *)&pExceptionObject;
            }
            v20 = v36;
            v21 = (v37 - v36) >> 1;
            v22 = GetStdHandle(0xFFFFFFF5);
            v40 = v20;
            v41 = v21;
            FilePuts(v22, &v40);
            v23 = o___acrt_iob_func_0(1u);
            fflush(v23);
            utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v36);
          }
        }
        std::wstring::_Tidy_deallocate(PublisherId);
      }
      wmi::AutoRef<AbstractDomAttribute>::Release(v39);
    }
  }
  if ( v10 )
    wmi::RefBase::Release(v10);
}

```

## disassembly

```asm
0x14000116c  push    rbp
0x14000116e  push    rbx
0x14000116f  push    rsi
0x140001170  push    rdi
0x140001171  push    r12
0x140001173  push    r14
0x140001175  push    r15
0x140001177  lea     rbp, [rsp-27h]
0x14000117c  sub     rsp, 0F0h
0x140001183  mov     rax, cs:__security_cookie
0x14000118a  xor     rax, rsp
0x14000118d  mov     [rbp+57h+var_40], rax
0x140001191  mov     ebx, r8d
0x140001194  mov     rsi, rdx
0x140001197  mov     rdi, rcx
0x14000119a  call    IsEvtQueryPresent
0x14000119f  lea     r12, WPP_GLOBAL_Control
0x1400011a6  mov     r15d, 400000h
0x1400011ac  xor     r14d, r14d
0x1400011af  test    ebx, ebx
0x1400011b1  jz      loc_1400012FF
0x1400011b7  cmp     ebx, 7Eh ; '~'
0x1400011ba  jnz     loc_140001296
0x1400011c0  test    al, al
0x1400011c2  jz      short loc_1400011E8
0x1400011c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400011cb  cmp     rcx, r12
0x1400011ce  jz      short loc_1400011E8
0x1400011d0  test    [rcx+1Ch], r15d
0x1400011d4  jz      short loc_1400011E8
0x1400011d6  cmp     byte ptr [rcx+19h], 3
0x1400011da  jb      short loc_1400011E8
0x1400011dc  lea     edx, [rbx-73h]
0x1400011df  mov     rcx, [rcx+10h]
0x1400011e3  call    WPP_SF_
0x1400011e8  lea     rcx, [rbp+57h+var_B8]
0x1400011ec  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1400011f1  nop
0x1400011f2  lea     rbx, [rdi+28h]
0x1400011f6  cmp     qword ptr [rbx+18h], 7
0x1400011fb  jbe     short loc_140001200
0x1400011fd  mov     rbx, [rbx]
0x140001200  xor     ecx, ecx; lpModuleName
0x140001202  call    cs:__imp_GetModuleHandleW
0x140001208  mov     qword ptr [rsp+120h+var_F8], rbx
0x14000120d  mov     qword ptr [rsp+120h+Flags], r14
0x140001212  mov     r9d, 59h ; 'Y'
0x140001218  mov     r8, rax
0x14000121b  xor     edx, edx
0x14000121d  lea     rcx, [rbp+57h+var_B8]
0x140001221  call    ??$append_format_message_args@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@IPEAUHINSTANCE__@@IIZZ; tlx::append_format_message_args<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,uint,HINSTANCE__ *,uint,uint,...)
0x140001226  mov     ebx, eax
0x140001228  test    eax, eax
0x14000122a  jns     loc_14000162E
0x140001230  mov     rcx, cs:WPP_GLOBAL_Control
0x140001237  cmp     rcx, r12
0x14000123a  jz      short loc_140001260
0x14000123c  test    [rcx+1Ch], r15d
0x140001240  jz      short loc_140001260
0x140001242  cmp     byte ptr [rcx+19h], 2
0x140001246  jb      short loc_140001260
0x140001248  mov     edx, 11h
0x14000124d  mov     r9d, eax
0x140001250  lea     r8, WPP_ddf83515f50e3f824a6097176f506b2b_Traceguids
0x140001257  mov     rcx, [rcx+10h]
0x14000125b  call    WPP_SF_d
0x140001260  lea     rax, word_14003838A
0x140001267  mov     [rsp+120h+pExceptionObject], rax
0x14000126c  mov     [rsp+120h+var_D8], r14
0x140001271  mov     [rbp+57h+var_D0], r14
0x140001275  mov     [rbp+57h+var_C8], ebx
0x140001278  mov     [rbp+57h+var_C4], 0FFFFFFFFFFFFFFFFh
0x140001280  mov     [rbp+57h+var_BC], r14b
0x140001284  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14000128b  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x140001290  call    _CxxThrowException_0
0x140001296  mov     rcx, cs:WPP_GLOBAL_Control
0x14000129d  cmp     rcx, r12
0x1400012a0  jz      short loc_1400012C6
0x1400012a2  test    [rcx+1Ch], r15d
0x1400012a6  jz      short loc_1400012C6
0x1400012a8  cmp     byte ptr [rcx+19h], 2
0x1400012ac  jb      short loc_1400012C6
0x1400012ae  mov     edx, 0Ch
0x1400012b3  mov     r9d, ebx
0x1400012b6  lea     r8, WPP_ddf83515f50e3f824a6097176f506b2b_Traceguids
0x1400012bd  mov     rcx, [rcx+10h]
0x1400012c1  call    WPP_SF_d
0x1400012c6  mov     [rsp+120h+Src], r14; Src
0x1400012cb  mov     [rsp+120h+var_F0], 3Eh ; '>'; unsigned int
0x1400012d3  mov     [rsp+120h+var_F8], 54h ; 'T'; int
0x1400012db  xor     r9d, r9d; unsigned int
0x1400012de  xor     r8d, r8d; unsigned int
0x1400012e1  mov     edx, ebx; unsigned int
0x1400012e3  lea     rcx, [rsp+120h+pExceptionObject]; this
0x1400012e8  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x1400012ed  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1400012f4  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x1400012f9  call    _CxxThrowException_0
0x1400012ff  test    al, al
0x140001301  jz      loc_1400011E8
0x140001307  lea     rdx, [rbp+57h+var_70]
0x14000130b  mov     rcx, rsi
0x14000130e  call    ?GetSubElements@MsxmlDomElement@@UEAA?AV?$AutoRef@VAbstractDomElementList@@@wmi@@XZ; MsxmlDomElement::GetSubElements(void)
0x140001313  nop
0x140001314  mov     rbx, r14
0x140001317  mov     [rbp+57h+var_68], rbx
0x14000131b  mov     rdi, [rbp+57h+var_70]
0x14000131f  lea     r12, WPP_GLOBAL_Control
0x140001326  mov     r15d, 400000h
0x14000132c  mov     rax, [rdi]
0x14000132f  lea     rdx, [rbp+57h+var_98]
0x140001333  mov     rcx, rdi
0x140001336  mov     rax, [rax+8]
0x14000133a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000133f  mov     rsi, rax
0x140001342  test    rbx, rbx
0x140001345  jz      short loc_14000134F
0x140001347  mov     rcx, rbx; this
0x14000134a  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x14000134f  mov     rbx, [rsi]
0x140001352  mov     [rbp+57h+var_68], rbx
0x140001356  mov     [rsi], r14
0x140001359  mov     rcx, [rbp+57h+var_98]; this
0x14000135d  test    rcx, rcx
0x140001360  jz      short loc_140001367
0x140001362  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x140001367  mov     [rbp+57h+var_98], r14
0x14000136b  test    rbx, rbx
0x14000136e  jz      loc_140001618
0x140001374  mov     rax, [rbx]
0x140001377  mov     rcx, rbx
0x14000137a  mov     rax, [rax+10h]
0x14000137e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001383  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140001387  inc     rcx
0x14000138a  cmp     [rax+rcx*2], r14w
0x14000138f  jnz     short loc_140001387
0x140001391  cmp     rcx, 8
0x140001395  jnz     short loc_14000132C
0x140001397  mov     r8, rcx; N
0x14000139a  mov     rdx, rax; S2
0x14000139d  lea     rcx, aProvider; "provider"
0x1400013a4  call    wmemcmp
0x1400013a9  test    eax, eax
0x1400013ab  jnz     loc_14000132C
0x1400013b1  mov     rax, [rbx]
0x1400013b4  lea     r8, aName_0; "name"
0x1400013bb  lea     rdx, [rbp+57h+var_90]
0x1400013bf  mov     rcx, rbx
0x1400013c2  mov     rax, [rax+28h]
0x1400013c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400013cb  nop
0x1400013cc  mov     rcx, [rbp+57h+var_90]
0x1400013d0  test    rcx, rcx
0x1400013d3  jz      loc_14000154A
0x1400013d9  mov     rax, [rcx]
0x1400013dc  mov     rax, [rax+10h]
0x1400013e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400013e5  mov     rdx, rax
0x1400013e8  lea     rcx, [rbp+57h+PublisherId]
0x1400013ec  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1400013f1  nop
0x1400013f2  cmp     [rbp+57h+var_50], r14
0x1400013f6  jz      loc_140001540
0x1400013fc  lea     rdx, [rbp+57h+PublisherId]
0x140001400  cmp     [rbp+57h+var_48], 7
0x140001405  cmova   rdx, [rbp+57h+PublisherId]; PublisherId
0x14000140a  mov     [rsp+120h+Flags], r14d; Flags
0x14000140f  xor     r9d, r9d; Locale
0x140001412  xor     r8d, r8d; LogFilePath
0x140001415  xor     ecx, ecx; Session
0x140001417  call    cs:__imp_EvtOpenPublisherMetadata
0x14000141d  test    rax, rax
0x140001420  jnz     loc_140001504
0x140001426  lea     rcx, [rbp+57h+var_B8]
0x14000142a  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14000142f  nop
0x140001430  lea     rsi, [rbp+57h+PublisherId]
0x140001434  cmp     [rbp+57h+var_48], 7
0x140001439  cmova   rsi, [rbp+57h+PublisherId]
0x14000143e  xor     ecx, ecx; lpModuleName
0x140001440  call    cs:__imp_GetModuleHandleW
0x140001446  mov     qword ptr [rsp+120h+var_F8], rsi
0x14000144b  mov     qword ptr [rsp+120h+Flags], r14
0x140001450  mov     r9d, 45h ; 'E'
0x140001456  mov     r8, rax
0x140001459  xor     edx, edx
0x14000145b  lea     rcx, [rbp+57h+var_B8]
0x14000145f  call    ??$append_format_message_args@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@IPEAUHINSTANCE__@@IIZZ; tlx::append_format_message_args<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,uint,HINSTANCE__ *,uint,uint,...)
0x140001464  mov     esi, eax
0x140001466  test    eax, eax
0x140001468  js      loc_1400015AE
0x14000146e  mov     rcx, cs:WPP_GLOBAL_Control
0x140001475  cmp     rcx, r12
0x140001478  jz      short loc_14000149F
0x14000147a  test    [rcx+1Ch], r15d
0x14000147e  jz      short loc_14000149F
0x140001480  cmp     byte ptr [rcx+19h], 3
0x140001484  jb      short loc_14000149F
0x140001486  mov     edx, 0Eh
0x14000148b  mov     r9, [rbp+57h+var_B8]
0x14000148f  lea     r8, WPP_ddf83515f50e3f824a6097176f506b2b_Traceguids
0x140001496  mov     rcx, [rcx+10h]
0x14000149a  call    WPP_SF_S
0x14000149f  mov     edx, 0Ah
0x1400014a4  lea     rcx, [rbp+57h+var_B8]
0x1400014a8  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x1400014ad  test    al, al
0x1400014af  jz      loc_140001558
0x1400014b5  mov     r14, [rbp+57h+var_B0]
0x1400014b9  mov     rsi, [rbp+57h+var_B8]
0x1400014bd  sub     r14, rsi
0x1400014c0  sar     r14, 1
0x1400014c3  mov     ecx, 0FFFFFFF5h; nStdHandle
0x1400014c8  call    cs:__imp_GetStdHandle
0x1400014ce  mov     [rbp+57h+var_80], rsi
0x1400014d2  mov     [rbp+57h+var_78], r14
0x1400014d6  lea     rdx, [rbp+57h+var_80]
0x1400014da  mov     rcx, rax; hFile
0x1400014dd  call    ?FilePuts@@YAJPEAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; FilePuts(void *,std::wstring_view)
0x1400014e2  mov     ecx, 1; Ix
0x1400014e7  call    _o___acrt_iob_func_0
0x1400014ec  mov     rcx, rax; Stream
0x1400014ef  call    cs:__imp_fflush
0x1400014f5  nop
0x1400014f6  lea     rcx, [rbp+57h+var_B8]
0x1400014fa  call    ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1400014ff  xor     r14d, r14d
0x140001502  jmp     short loc_140001540
0x140001504  mov     rcx, cs:WPP_GLOBAL_Control
0x14000150b  cmp     rcx, r12
0x14000150e  jz      short loc_140001540
0x140001510  test    [rcx+1Ch], r15d
0x140001514  jz      short loc_140001540
0x140001516  cmp     byte ptr [rcx+19h], 4
0x14000151a  jb      short loc_140001540
0x14000151c  lea     r9, [rbp+57h+PublisherId]
0x140001520  cmp     [rbp+57h+var_48], 7
0x140001525  cmova   r9, [rbp+57h+PublisherId]
0x14000152a  mov     edx, 10h
0x14000152f  lea     r8, WPP_ddf83515f50e3f824a6097176f506b2b_Traceguids
0x140001536  mov     rcx, [rcx+10h]
0x14000153a  call    WPP_SF_S
0x14000153f  nop
0x140001540  lea     rcx, [rbp+57h+PublisherId]
0x140001544  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140001549  nop
0x14000154a  lea     rcx, [rbp+57h+var_90]
0x14000154e  call    ?Release@?$AutoRef@VAbstractDomAttribute@@@wmi@@QEAAXXZ; wmi::AutoRef<AbstractDomAttribute>::Release(void)
0x140001553  jmp     loc_14000132C
0x140001558  mov     rcx, cs:WPP_GLOBAL_Control
0x14000155f  cmp     rcx, r12
0x140001562  jz      short loc_140001589
0x140001564  test    [rcx+1Ch], r15d
0x140001568  jz      short loc_140001589
0x14000156a  cmp     byte ptr [rcx+19h], 2
0x14000156e  jb      short loc_140001589
0x140001570  mov     edx, 0Fh
0x140001575  lea     r9d, [rdx-1]
0x140001579  lea     r8, WPP_ddf83515f50e3f824a6097176f506b2b_Traceguids
0x140001580  mov     rcx, [rcx+10h]
0x140001584  call    WPP_SF_d
0x140001589  mov     edx, 0Eh; unsigned int
0x14000158e  lea     r9d, [rdx+64h]; int
0x140001592  lea     rcx, [rsp+120h+pExceptionObject]; this
0x140001597  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x14000159c  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1400015a3  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x1400015a8  call    _CxxThrowException_0
0x1400015ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400015b5  cmp     rcx, r12
0x1400015b8  jz      short loc_1400015DE
0x1400015ba  test    [rcx+1Ch], r15d
0x1400015be  jz      short loc_1400015DE
0x1400015c0  cmp     byte ptr [rcx+19h], 2
0x1400015c4  jb      short loc_1400015DE
0x1400015c6  mov     edx, 0Dh
0x1400015cb  mov     r9d, esi
0x1400015ce  lea     r8, WPP_ddf83515f50e3f824a6097176f506b2b_Traceguids
0x1400015d5  mov     rcx, [rcx+10h]
0x1400015d9  call    WPP_SF_d
0x1400015de  lea     rax, word_14003838A
0x1400015e5  mov     [rsp+120h+pExceptionObject], rax
0x1400015ea  mov     [rsp+120h+var_D8], r14
0x1400015ef  mov     [rbp+57h+var_D0], 0
0x1400015f7  mov     [rbp+57h+var_C8], esi
0x1400015fa  mov     [rbp+57h+var_C4], 0FFFFFFFFFFFFFFFFh
0x140001602  mov     [rbp+57h+var_BC], r14b
0x140001606  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14000160d  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x140001612  call    _CxxThrowException_0
0x140001618  test    rdi, rdi
0x14000161b  jz      loc_140001711
0x140001621  mov     rcx, rdi; this
0x140001624  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x140001629  jmp     loc_140001711
0x14000162e  mov     rcx, cs:WPP_GLOBAL_Control
0x140001635  cmp     rcx, r12
0x140001638  jz      short loc_14000165F
  ... truncated ...
```
