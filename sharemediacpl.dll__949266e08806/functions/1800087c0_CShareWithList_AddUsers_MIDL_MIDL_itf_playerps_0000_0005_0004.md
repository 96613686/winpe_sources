# CShareWithList::AddUsers(__MIDL___MIDL_itf_playerps_0000_0005_0004 *)

- ea: `0x1800087c0`
- end: `0x180008c4d`
- name: `?AddUsers@CShareWithList@@QEAAJPEAU__MIDL___MIDL_itf_playerps_0000_0005_0004@@@Z`
- size: `1165`
- prototype: `__int64 __fastcall(CShareWithList *__hidden this, struct __MIDL___MIDL_itf_playerps_0000_0005_0004 *)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180009900`

## callees

- `0x180001914`
- `0x180001d60`
- `0x18000291e`
- `0x180003860`
- `0x180003888`
- `0x180003d5c`
- `0x180003d8c`
- `0x18000669c`
- `0x1800068e0`
- `0x180006b3c`
- `0x180006bfc`
- `0x1800087c0`
- `0x180009030`
- `0x180009460`
- `0x18000a130`
- `0x18000abd4`
- `0x18000d9e4`
- `0x18000da94`
- `0x180012cb0`
- `0x1800164b8`
- `0x18001e010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180008b96`
- `KERNEL32!LeaveCriticalSection` at `0x180008b96`
- `KERNEL32!EnterCriticalSection` at `0x180008b71`
- `KERNEL32!EnterCriticalSection` at `0x180008b71`
- `OLEAUT32!__imp_SysAllocString` at `0x18000884e`
- `OLEAUT32!__imp_SysAllocString` at `0x18000884e`
- `OLEAUT32!__imp_SysFreeString` at `0x180008927`
- `OLEAUT32!__imp_SysFreeString` at `0x180008927`
- `USER32!LoadStringW` at `0x180008a88`
- `USER32!LoadStringW` at `0x180008a88`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@P6AHPEBX1@Z@Z` at `0x180008aef`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@P6AHPEBX1@Z@Z` at `0x180008aef`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x1800089b0`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x1800089b0`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800089ca`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800089ca`

## pseudocode

```c
__int64 __fastcall CShareWithList::AddUsers(CShareWithList *this, struct __MIDL___MIDL_itf_playerps_0000_0005_0004 *a2)
{
  void *v4; // rcx
  BSTR v5; // rax
  unsigned __int16 *v6; // rbx
  __int64 v7; // r9
  int v8; // edi
  int v9; // esi
  __int64 v10; // rcx
  struct DirectUI::Element *v11; // rcx
  DirectUI::Element *v12; // rsi
  DirectUI::DUIXmlParser *v13; // rcx
  CDeviceSettings *v14; // rax
  CDeviceSettings *v15; // rax
  struct CDeviceSettings *v16; // rbx
  DirectUI::Element *v17; // rcx
  struct INSSDevice *v18; // rcx
  void *p; // [rsp+30h] [rbp-D0h] BYREF
  struct INSSDevice *v21; // [rsp+38h] [rbp-C8h] BYREF
  struct DirectUI::Element *v22; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[104]; // [rsp+50h] [rbp-B0h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 121, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
  if ( (Microsoft_Windows_ShareMedia_ControlPanelEnableBits & 1) != 0 )
    McTemplateU0zq_EventWriteTransfer(v4, ShareMediaCPL_AddDevice_Start, L"00-00-00-00-00-00", 0);
  v21 = 0;
  v5 = SysAllocString(L"00-00-00-00-00-00");
  v6 = v5;
  if ( !v5 )
    goto LABEL_63;
  v7 = 0x7FFFFFFF;
  do
  {
    if ( !*v5 )
      break;
    ++v5;
    --v7;
  }
  while ( v7 );
  if ( (v7 != 0 ? 0x7FFFFFFF - (_DWORD)v7 : 0) == 0 )
  {
LABEL_63:
    v8 = -2147024882;
    goto LABEL_53;
  }
  LODWORD(p) = -1;
  if ( CShareWithList::FindItem(this, v6, (int *)&p) < 0 || (_DWORD)p == -1 )
  {
    v10 = *((_QWORD *)this + 5);
    v9 = 0;
    if ( v10 )
    {
      p = 0;
      v8 = (*(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v10 + 88LL))(v10, &p);
      if ( v8 >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(void *, unsigned __int16 *, struct INSSDevice **))(*(_QWORD *)p + 72LL))(
               p,
               v6,
               &v21);
        (*(void (__fastcall **)(void *))(*(_QWORD *)p + 16LL))(p);
      }
    }
    else
    {
      v8 = -2147467259;
    }
  }
  else
  {
    v8 = 0;
    v9 = 1;
  }
  SysFreeString(v6);
  if ( v8 >= 0 && !v9 )
  {
    if ( *((_DWORD *)this + 29)
      || !*((_QWORD *)this + 4)
      || (v11 = (struct DirectUI::Element *)*((_QWORD *)this + 2)) == 0
      || (*((_BYTE *)v11 + 151) & 4) != 0 )
    {
      v8 = -2147467259;
      goto LABEL_53;
    }
    p = 0;
    v8 = CShareWithListItemUsers::Create(v11, 0, (struct DirectUI::Element **)&p);
    if ( v8 >= 0 )
    {
      v12 = (DirectUI::Element *)p;
      v13 = (DirectUI::DUIXmlParser *)*((_QWORD *)this + 4);
      v22 = 0;
      v8 = DirectUI::DUIXmlParser::CreateElement(
             v13,
             L"macro_sharing_list_item",
             (struct DirectUI::Element *)p,
             0,
             0,
             &v22);
      if ( v8 >= 0 )
      {
        DirectUI::Element::SetID(v12, L"00-00-00-00-00-00");
        v14 = (CDeviceSettings *)operator new(0x70u);
        if ( !v14 || (v15 = CDeviceSettings::CDeviceSettings(v14), p = v15, (v16 = v15) == 0) )
        {
          v8 = -2147024882;
LABEL_46:
          if ( (*((_BYTE *)v12 + 151) & 4) == 0 )
            IUnknown_SafeReleaseAndNullPtr<CDeviceSettings>((char *)v12 + 216);
          goto LABEL_53;
        }
        v8 = CDeviceSettings::SetID(v15, L"00-00-00-00-00-00");
        if ( v8 >= 0 )
        {
          if ( !v21 || (v8 = CDeviceSettings::SetDevice(v16, v21), v8 >= 0) )
          {
            if ( !a2 || (v8 = CDeviceSettings::SetWMPDeviceSettings(v16, a2), v8 >= 0) )
            {
              v8 = CShareWithList::ApplyAutoAuthorizationStatus(this, v16);
              if ( v8 >= 0 )
              {
                memset_0(Buffer, 0, 0xC8u);
                LoadStringW(g_hinst, 0x1Fu, Buffer, 100);
                v8 = CDeviceSettings::SetDeviceName(v16, Buffer);
                if ( v8 >= 0 )
                {
                  v8 = CShareWithListItemBase::SetDeviceSettings(v12, v16);
                  if ( v8 >= 0 )
                  {
                    v8 = CShareWithListItemBase::SetParent(v12, *((HWND *)this + 7));
                    if ( v8 >= 0 )
                    {
                      if ( *((_DWORD *)this + 29)
                        || (v17 = (DirectUI::Element *)*((_QWORD *)this + 2)) == 0
                        || (*((_BYTE *)v17 + 151) & 4) != 0
                        || (*((_BYTE *)v12 + 151) & 4) != 0 )
                      {
                        v8 = -2147467259;
                      }
                      else
                      {
                        v8 = DirectUI::Element::Add(v17, v12, (int (*)(const void *, const void *))SortChildrenProc);
                      }
                    }
                  }
                }
              }
            }
          }
        }
        IUnknown_SafeReleaseAndNullPtr<CDeviceSettings>(&p);
        if ( v8 < 0 )
          goto LABEL_46;
        if ( (*((_BYTE *)v12 + 151) & 4) != 0 )
        {
          v8 = -2147467259;
        }
        else
        {
          v8 = CShareWithListItemBase::InitializeUI(v12);
          (*(void (__fastcall **)(_QWORD, DirectUI::Element *))(**((_QWORD **)v12 + 10) + 360LL))(
            *((_QWORD *)v12 + 10),
            v12);
          if ( v8 >= 0 )
          {
            EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
            v8 = 0;
            if ( DPA_InsertPtr(*((HDPA *)this + 3), 0x7FFFFFFF, v12) == -1 )
              v8 = -2147467259;
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
          }
        }
      }
    }
  }
LABEL_53:
  v18 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*(void (__fastcall **)(struct INSSDevice *))(*(_QWORD *)v18 + 16LL))(v18);
  }
  if ( (Microsoft_Windows_ShareMedia_ControlPanelEnableBits & 1) != 0 )
    McTemplateU0zq_EventWriteTransfer(v18, ShareMediaCPL_AddDevice_Stop, L"00-00-00-00-00-00", (unsigned int)v8);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      122,
      &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids,
      (unsigned int)v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800087c0  mov     [rsp-8+arg_10], rbx
0x1800087c5  mov     [rsp-8+arg_18], rsi
0x1800087ca  push    rbp
0x1800087cb  push    rdi
0x1800087cc  push    r12
0x1800087ce  push    r14
0x1800087d0  push    r15
0x1800087d2  lea     rbp, [rsp-30h]
0x1800087d7  sub     rsp, 130h
0x1800087de  mov     rax, cs:__security_cookie
0x1800087e5  xor     rax, rsp
0x1800087e8  mov     [rbp+50h+var_30], rax
0x1800087ec  mov     r15, rdx
0x1800087ef  mov     r14, rcx
0x1800087f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800087f9  lea     rsi, WPP_GLOBAL_Control
0x180008800  cmp     rcx, rsi
0x180008803  jz      short loc_180008820
0x180008805  test    byte ptr [rcx+1Ch], 20h
0x180008809  jz      short loc_180008820
0x18000880b  mov     rcx, [rcx+10h]
0x18000880f  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x180008816  mov     edx, 79h ; 'y'
0x18000881b  call    WPP_SF_
0x180008820  test    cs:Microsoft_Windows_ShareMedia_ControlPanelEnableBits, 1
0x180008827  jz      short loc_18000883F
0x180008829  xor     r9d, r9d
0x18000882c  lea     r8, psz; "00-00-00-00-00-00"
0x180008833  lea     rdx, ShareMediaCPL_AddDevice_Start
0x18000883a  call    McTemplateU0zq_EventWriteTransfer
0x18000883f  xor     r12d, r12d
0x180008842  lea     rcx, psz; "00-00-00-00-00-00"
0x180008849  mov     [rsp+150h+var_118], r12
0x18000884e  call    cs:__imp_SysAllocString
0x180008854  mov     rbx, rax
0x180008857  test    rax, rax
0x18000885a  jz      loc_180008C43
0x180008860  mov     ecx, 7FFFFFFFh
0x180008865  mov     r9d, ecx
0x180008868  cmp     [rax], r12w
0x18000886c  jz      short loc_180008878
0x18000886e  add     rax, 2
0x180008872  sub     r9, 1
0x180008876  jnz     short loc_180008868
0x180008878  sub     ecx, r9d
0x18000887b  mov     rax, r9
0x18000887e  neg     rax
0x180008881  mov     r8, r9
0x180008884  sbb     edx, edx
0x180008886  and     edx, ecx
0x180008888  neg     r8
0x18000888b  sbb     ecx, ecx
0x18000888d  and     ecx, edx
0x18000888f  neg     r9
0x180008892  sbb     eax, eax
0x180008894  test    ecx, eax
0x180008896  jbe     loc_180008C43
0x18000889c  lea     r8, [rsp+150h+p]; int *
0x1800088a1  mov     dword ptr [rsp+150h+p], 0FFFFFFFFh
0x1800088a9  mov     rdx, rbx; unsigned __int16 *
0x1800088ac  mov     rcx, r14; this
0x1800088af  call    ?FindItem@CShareWithList@@QEAAJPEAGPEAH@Z; CShareWithList::FindItem(ushort *,int *)
0x1800088b4  test    eax, eax
0x1800088b6  js      short loc_1800088C9
0x1800088b8  cmp     dword ptr [rsp+150h+p], 0FFFFFFFFh
0x1800088bd  jz      short loc_1800088C9
0x1800088bf  mov     edi, r12d
0x1800088c2  mov     esi, 1
0x1800088c7  jmp     short loc_180008924
0x1800088c9  mov     rcx, [r14+28h]
0x1800088cd  mov     esi, r12d
0x1800088d0  test    rcx, rcx
0x1800088d3  jz      short loc_18000891F
0x1800088d5  mov     [rsp+150h+p], r12
0x1800088da  lea     rdx, [rsp+150h+p]
0x1800088df  mov     rax, [rcx]
0x1800088e2  mov     rax, [rax+58h]
0x1800088e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088eb  mov     edi, eax
0x1800088ed  test    eax, eax
0x1800088ef  js      short loc_180008924
0x1800088f1  mov     rcx, [rsp+150h+p]
0x1800088f6  lea     r8, [rsp+150h+var_118]
0x1800088fb  mov     rdx, rbx
0x1800088fe  mov     rax, [rcx]
0x180008901  mov     rax, [rax+48h]
0x180008905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000890a  mov     rcx, [rsp+150h+p]
0x18000890f  mov     edi, eax
0x180008911  mov     rax, [rcx]
0x180008914  mov     rax, [rax+10h]
0x180008918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000891d  jmp     short loc_180008924
0x18000891f  mov     edi, 80004005h
0x180008924  mov     rcx, rbx; bstrString
0x180008927  call    cs:__imp_SysFreeString
0x18000892d  test    edi, edi
0x18000892f  js      loc_180008B9C
0x180008935  test    esi, esi
0x180008937  jnz     loc_180008B9C
0x18000893d  cmp     [r14+74h], r12d
0x180008941  jnz     loc_180008C39
0x180008947  cmp     [r14+20h], r12
0x18000894b  jz      loc_180008C39
0x180008951  mov     rcx, [r14+10h]; struct DirectUI::Element *
0x180008955  test    rcx, rcx
0x180008958  jz      loc_180008C39
0x18000895e  test    byte ptr [rcx+97h], 4
0x180008965  jnz     loc_180008C39
0x18000896b  lea     r8, [rsp+150h+p]; struct DirectUI::Element **
0x180008970  mov     [rsp+150h+p], r12
0x180008975  xor     edx, edx; unsigned int *
0x180008977  call    ?Create@CShareWithListItemUsers@@SAJPEAVElement@DirectUI@@PEAKPEAPEAV23@@Z; CShareWithListItemUsers::Create(DirectUI::Element *,ulong *,DirectUI::Element * *)
0x18000897c  mov     edi, eax
0x18000897e  test    eax, eax
0x180008980  js      loc_180008B9C
0x180008986  mov     rsi, [rsp+150h+p]
0x18000898b  lea     rax, [rsp+150h+var_110]
0x180008990  mov     rcx, [r14+20h]
0x180008994  lea     rdx, aMacroSharingLi; "macro_sharing_list_item"
0x18000899b  mov     [rsp+150h+var_128], rax
0x1800089a0  mov     r8, rsi
0x1800089a3  xor     r9d, r9d
0x1800089a6  mov     [rsp+150h+var_130], r12
0x1800089ab  mov     [rsp+150h+var_110], r12
0x1800089b0  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x1800089b6  mov     edi, eax
0x1800089b8  test    eax, eax
0x1800089ba  js      loc_180008B9C
0x1800089c0  lea     rdx, psz; "00-00-00-00-00-00"
0x1800089c7  mov     rcx, rsi
0x1800089ca  call    cs:__imp_?SetID@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetID(ushort const *)
0x1800089d0  mov     ecx, 70h ; 'p'; Size
0x1800089d5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800089da  test    rax, rax
0x1800089dd  jz      loc_180008B18
0x1800089e3  mov     rcx, rax; this
0x1800089e6  call    ??0CDeviceSettings@@QEAA@XZ; CDeviceSettings::CDeviceSettings(void)
0x1800089eb  mov     [rsp+150h+p], rax
0x1800089f0  mov     rbx, rax
0x1800089f3  test    rax, rax
0x1800089f6  jz      loc_180008B18
0x1800089fc  lea     rdx, psz; "00-00-00-00-00-00"
0x180008a03  mov     rcx, rax; this
0x180008a06  call    ?SetID@CDeviceSettings@@QEAAJPEBG@Z; CDeviceSettings::SetID(ushort const *)
0x180008a0b  mov     edi, eax
0x180008a0d  test    eax, eax
0x180008a0f  js      loc_180008AF7
0x180008a15  mov     rdx, [rsp+150h+var_118]; struct INSSDevice *
0x180008a1a  test    rdx, rdx
0x180008a1d  jz      short loc_180008A31
0x180008a1f  mov     rcx, rbx; this
0x180008a22  call    ?SetDevice@CDeviceSettings@@QEAAJPEAUINSSDevice@@@Z; CDeviceSettings::SetDevice(INSSDevice *)
0x180008a27  mov     edi, eax
0x180008a29  test    eax, eax
0x180008a2b  js      loc_180008AF7
0x180008a31  test    r15, r15
0x180008a34  jz      short loc_180008A4B
0x180008a36  mov     rdx, r15; struct __MIDL___MIDL_itf_playerps_0000_0005_0004 *
0x180008a39  mov     rcx, rbx; this
0x180008a3c  call    ?SetWMPDeviceSettings@CDeviceSettings@@QEAAJPEAU__MIDL___MIDL_itf_playerps_0000_0005_0004@@@Z; CDeviceSettings::SetWMPDeviceSettings(__MIDL___MIDL_itf_playerps_0000_0005_0004 *)
0x180008a41  mov     edi, eax
0x180008a43  test    eax, eax
0x180008a45  js      loc_180008AF7
0x180008a4b  mov     rdx, rbx; struct CDeviceSettings *
0x180008a4e  mov     rcx, r14; this
0x180008a51  call    ?ApplyAutoAuthorizationStatus@CShareWithList@@QEAAJPEAVCDeviceSettings@@@Z; CShareWithList::ApplyAutoAuthorizationStatus(CDeviceSettings *)
0x180008a56  mov     edi, eax
0x180008a58  test    eax, eax
0x180008a5a  js      loc_180008AF7
0x180008a60  xor     edx, edx; Val
0x180008a62  lea     rcx, [rsp+150h+Buffer]; void *
0x180008a67  mov     r8d, 0C8h; Size
0x180008a6d  call    memset_0
0x180008a72  mov     rcx, cs:g_hinst; hInstance
0x180008a79  lea     r8, [rsp+150h+Buffer]; lpBuffer
0x180008a7e  mov     r9d, 64h ; 'd'; cchBufferMax
0x180008a84  lea     edx, [r9-45h]; uID
0x180008a88  call    cs:__imp_LoadStringW
0x180008a8e  lea     rdx, [rsp+150h+Buffer]; unsigned __int16 *
0x180008a93  mov     rcx, rbx; this
0x180008a96  call    ?SetDeviceName@CDeviceSettings@@QEAAJPEBG@Z; CDeviceSettings::SetDeviceName(ushort const *)
0x180008a9b  mov     edi, eax
0x180008a9d  test    eax, eax
0x180008a9f  js      short loc_180008AF7
0x180008aa1  mov     rdx, rbx; struct CDeviceSettings *
0x180008aa4  mov     rcx, rsi; this
0x180008aa7  call    ?SetDeviceSettings@CShareWithListItemBase@@QEAAJPEAVCDeviceSettings@@@Z; CShareWithListItemBase::SetDeviceSettings(CDeviceSettings *)
0x180008aac  mov     edi, eax
0x180008aae  test    eax, eax
0x180008ab0  js      short loc_180008AF7
0x180008ab2  mov     rdx, [r14+38h]; HWND
0x180008ab6  mov     rcx, rsi; this
0x180008ab9  call    ?SetParent@CShareWithListItemBase@@QEAAJPEAUHWND__@@@Z; CShareWithListItemBase::SetParent(HWND__ *)
0x180008abe  mov     edi, eax
0x180008ac0  test    eax, eax
0x180008ac2  js      short loc_180008AF7
0x180008ac4  cmp     [r14+74h], r12d
0x180008ac8  jnz     short loc_180008B0D
0x180008aca  mov     rcx, [r14+10h]
0x180008ace  test    rcx, rcx
0x180008ad1  jz      short loc_180008B0D
0x180008ad3  test    byte ptr [rcx+97h], 4
0x180008ada  jnz     short loc_180008B0D
0x180008adc  test    byte ptr [rsi+97h], 4
0x180008ae3  jnz     short loc_180008B0D
0x180008ae5  lea     r8, ?SortChildrenProc@@YAHPEBX0@Z; SortChildrenProc(void const *,void const *)
0x180008aec  mov     rdx, rsi
0x180008aef  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@P6AHPEBX1@Z@Z; DirectUI::Element::Add(DirectUI::Element *,int (*)(void const *,void const *))
0x180008af5  mov     edi, eax
0x180008af7  mov     r15d, 80004005h
0x180008afd  lea     rcx, [rsp+150h+p]
0x180008b02  call    ??$IUnknown_SafeReleaseAndNullPtr@VCDeviceSettings@@@@YAXAEAPEAVCDeviceSettings@@@Z; IUnknown_SafeReleaseAndNullPtr<CDeviceSettings>(CDeviceSettings * &)
0x180008b07  test    edi, edi
0x180008b09  jns     short loc_180008B3C
0x180008b0b  jmp     short loc_180008B23
0x180008b0d  mov     r15d, 80004005h
0x180008b13  mov     edi, r15d
0x180008b16  jmp     short loc_180008AFD
0x180008b18  mov     edi, 8007000Eh
0x180008b1d  mov     r15d, 80004005h
0x180008b23  test    byte ptr [rsi+97h], 4
0x180008b2a  jnz     short loc_180008B9C
0x180008b2c  lea     rcx, [rsi+0D8h]
0x180008b33  call    ??$IUnknown_SafeReleaseAndNullPtr@VCDeviceSettings@@@@YAXAEAPEAVCDeviceSettings@@@Z; IUnknown_SafeReleaseAndNullPtr<CDeviceSettings>(CDeviceSettings * &)
0x180008b38  test    edi, edi
0x180008b3a  js      short loc_180008B9C
0x180008b3c  test    byte ptr [rsi+97h], 4
0x180008b43  jnz     loc_180008C31
0x180008b49  mov     rcx, rsi; this
0x180008b4c  call    ?InitializeUI@CShareWithListItemBase@@QEAAJXZ; CShareWithListItemBase::InitializeUI(void)
0x180008b51  mov     rcx, [rsi+50h]
0x180008b55  mov     edi, eax
0x180008b57  mov     rdx, rsi
0x180008b5a  mov     rax, [rcx]
0x180008b5d  mov     rax, [rax+168h]
0x180008b64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b69  test    edi, edi
0x180008b6b  js      short loc_180008B9C
0x180008b6d  lea     rcx, [r14+48h]; lpCriticalSection
0x180008b71  call    cs:__imp_EnterCriticalSection
0x180008b77  mov     rcx, [r14+18h]; hdpa
0x180008b7b  mov     r8, rsi; p
0x180008b7e  mov     edx, 7FFFFFFFh; i
0x180008b83  call    DPA_InsertPtr
0x180008b88  cmp     eax, 0FFFFFFFFh
0x180008b8b  lea     rcx, [r14+48h]; lpCriticalSection
0x180008b8f  mov     edi, r12d
0x180008b92  cmovz   edi, r15d
0x180008b96  call    cs:__imp_LeaveCriticalSection
0x180008b9c  lea     rsi, WPP_GLOBAL_Control
0x180008ba3  mov     rcx, [rsp+150h+var_118]
0x180008ba8  test    rcx, rcx
0x180008bab  jz      short loc_180008BBE
0x180008bad  mov     [rsp+150h+var_118], r12
0x180008bb2  mov     rax, [rcx]
0x180008bb5  mov     rax, [rax+10h]
0x180008bb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bbe  test    cs:Microsoft_Windows_ShareMedia_ControlPanelEnableBits, 1
0x180008bc5  jz      short loc_180008BDD
0x180008bc7  mov     r9d, edi
0x180008bca  lea     r8, psz; "00-00-00-00-00-00"
0x180008bd1  lea     rdx, ShareMediaCPL_AddDevice_Stop
0x180008bd8  call    McTemplateU0zq_EventWriteTransfer
0x180008bdd  mov     rcx, cs:WPP_GLOBAL_Control
0x180008be4  cmp     rcx, rsi
0x180008be7  jz      short loc_180008C07
0x180008be9  test    byte ptr [rcx+1Ch], 20h
0x180008bed  jz      short loc_180008C07
0x180008bef  mov     rcx, [rcx+10h]
0x180008bf3  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x180008bfa  mov     edx, 7Ah ; 'z'
0x180008bff  mov     r9d, edi
0x180008c02  call    WPP_SF_d
0x180008c07  mov     eax, edi
0x180008c09  mov     rcx, [rbp+50h+var_30]
0x180008c0d  xor     rcx, rsp; StackCookie
0x180008c10  call    __security_check_cookie
0x180008c15  lea     r11, [rsp+150h+var_20]
0x180008c1d  mov     rbx, [r11+40h]
0x180008c21  mov     rsi, [r11+48h]
0x180008c25  mov     rsp, r11
0x180008c28  pop     r15
0x180008c2a  pop     r14
0x180008c2c  pop     r12
0x180008c2e  pop     rdi
0x180008c2f  pop     rbp
0x180008c30  retn
0x180008c31  mov     edi, r15d
0x180008c34  jmp     loc_180008B9C
0x180008c39  mov     edi, 80004005h
0x180008c3e  jmp     loc_180008B9C
0x180008c43  mov     edi, 8007000Eh
0x180008c48  jmp     loc_180008BA3
```
