# CShareWithList::AddDevice(ushort *,__MIDL___MIDL_itf_playerps_0000_0005_0004 *)

- ea: `0x18000822c`
- end: `0x180008698`
- name: `?AddDevice@CShareWithList@@QEAAJPEAGPEAU__MIDL___MIDL_itf_playerps_0000_0005_0004@@@Z`
- size: `1132`
- prototype: `__int64 __fastcall(CShareWithList *__hidden this, unsigned __int16 *, struct __MIDL___MIDL_itf_playerps_0000_0005_0004 *)`
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180009900`

## callees

- `0x180001914`
- `0x180003860`
- `0x180003888`
- `0x180003d5c`
- `0x180003d8c`
- `0x18000669c`
- `0x180006b3c`
- `0x180006bfc`
- `0x18000822c`
- `0x180009030`
- `0x1800092d4`
- `0x18000a058`
- `0x18000a130`
- `0x18000abd4`
- `0x18000d9e4`
- `0x18000da94`
- `0x18000db20`
- `0x18000df2c`
- `0x180012cb0`
- `0x180012dd8`
- `0x1800164b8`
- `0x18001e010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800085aa`
- `KERNEL32!LeaveCriticalSection` at `0x1800085aa`
- `KERNEL32!EnterCriticalSection` at `0x18000854f`
- `KERNEL32!EnterCriticalSection` at `0x18000854f`
- `KERNEL32!lstrcmpiW` at `0x180008316`
- `KERNEL32!lstrcmpiW` at `0x180008316`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@P6AHPEBX1@Z@Z` at `0x180008599`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@P6AHPEBX1@Z@Z` at `0x180008599`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x1800084bd`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x1800084bd`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1800085d3`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1800085d3`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800084d3`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800084d3`

## pseudocode

```c
__int64 __fastcall CShareWithList::AddDevice(
        CShareWithList *this,
        unsigned __int16 *a2,
        struct __MIDL___MIDL_itf_playerps_0000_0005_0004 *a3)
{
  _QWORD *v6; // r10
  unsigned __int16 *v7; // rax
  __int64 v8; // r9
  __int64 v9; // rcx
  __int64 v10; // rcx
  int updated; // ebx
  __int64 v12; // rcx
  CDeviceSettings *v13; // r14
  CDeviceSettings *v14; // rax
  CDeviceSettings *v15; // rax
  struct INSSDevice *v16; // rcx
  struct DirectUI::Element *v17; // rcx
  DirectUI::Element *v18; // rdi
  DirectUI::DUIXmlParser *v19; // rcx
  __int64 v20; // rax
  CDeviceSettings *v22; // [rsp+30h] [rbp-10h] BYREF
  struct DirectUI::Element *v23; // [rsp+38h] [rbp-8h] BYREF
  void *p; // [rsp+88h] [rbp+48h] BYREF
  struct INSSDevice *v25; // [rsp+98h] [rbp+58h] BYREF

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 118, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
    goto LABEL_70;
  v7 = a2;
  v8 = 0x7FFFFFFF;
  do
  {
    if ( !*v7 )
      break;
    ++v7;
    --v8;
  }
  while ( v8 );
  v9 = (0x7FFFFFFF - (_DWORD)v8) & (unsigned int)-(v8 != 0);
  if ( (v8 != 0 ? 0x7FFFFFFF - (_DWORD)v8 : 0) == 0 )
  {
LABEL_70:
    updated = -2147467261;
    goto LABEL_71;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
    WPP_SF_S(v6[2], 119, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids, a2);
  if ( (Microsoft_Windows_ShareMedia_ControlPanelEnableBits & 1) != 0 )
    McTemplateU0zq_EventWriteTransfer(v9, ShareMediaCPL_AddDevice_Start, a2, 0);
  if ( !lstrcmpiW(a2, L"00-00-00-00-00-00") )
  {
    updated = 1;
    goto LABEL_67;
  }
  LODWORD(p) = -1;
  if ( CShareWithList::FindItem(this, a2, (int *)&p) < 0 || (_DWORD)p == -1 )
  {
    v12 = *((_QWORD *)this + 5);
    v25 = 0;
    if ( v12 )
    {
      p = 0;
      updated = (*(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v12 + 88LL))(v12, &p);
      if ( updated >= 0 )
      {
        updated = (*(__int64 (__fastcall **)(void *, unsigned __int16 *, struct INSSDevice **))(*(_QWORD *)p + 72LL))(
                    p,
                    a2,
                    &v25);
        (*(void (__fastcall **)(void *))(*(_QWORD *)p + 16LL))(p);
      }
      v22 = 0;
      v13 = 0;
      if ( updated >= 0 )
      {
        v14 = (CDeviceSettings *)operator new(0x70u);
        if ( v14 && (v15 = CDeviceSettings::CDeviceSettings(v14), v22 = v15, (v13 = v15) != 0) )
        {
          updated = CDeviceSettings::SetID(v15, a2);
          if ( updated >= 0 )
          {
            updated = CDeviceSettings::SetDevice(v13, v25);
            if ( updated >= 0 )
            {
              if ( !a3 || (updated = CDeviceSettings::SetWMPDeviceSettings(v13, a3), updated >= 0) )
                updated = CShareWithList::ApplyAutoAuthorizationStatus(this, v13);
            }
          }
        }
        else
        {
          updated = -2147024882;
        }
      }
      v16 = v25;
      if ( v25 )
      {
        v25 = 0;
        (*(void (__fastcall **)(struct INSSDevice *))(*(_QWORD *)v16 + 16LL))(v16);
      }
      if ( updated < 0 || !*((_QWORD *)this + 4) || !v13 )
        goto LABEL_65;
      if ( !*((_DWORD *)this + 29) )
      {
        v17 = (struct DirectUI::Element *)*((_QWORD *)this + 2);
        if ( v17 )
        {
          if ( (*((_BYTE *)v17 + 151) & 4) == 0 )
          {
            p = 0;
            updated = CShareWithListItemDevice::Create(v17, 0, (struct DirectUI::Element **)&p);
            if ( updated < 0 )
              goto LABEL_65;
            v18 = (DirectUI::Element *)p;
            v19 = (DirectUI::DUIXmlParser *)*((_QWORD *)this + 4);
            v23 = 0;
            updated = DirectUI::DUIXmlParser::CreateElement(
                        v19,
                        L"macro_sharing_list_item",
                        (struct DirectUI::Element *)p,
                        0,
                        0,
                        &v23);
            if ( updated < 0 )
              goto LABEL_65;
            DirectUI::Element::SetID(v18, a2);
            updated = CShareWithListItemBase::SetDeviceSettings(v18, v13);
            if ( updated >= 0 )
            {
              updated = CShareWithListItemBase::SetParent(v18, *((HWND *)this + 7));
              if ( updated >= 0 )
              {
                updated = CShareWithListItemBase::SetShowPowerManagementLabel(v18, *((_BYTE *)this + 112) == 0);
                if ( updated >= 0 )
                {
                  if ( !*((_DWORD *)this + 29) )
                  {
                    v20 = *((_QWORD *)this + 2);
                    if ( v20 )
                    {
                      if ( (*(_BYTE *)(v20 + 151) & 4) == 0 && (*((_BYTE *)v18 + 151) & 4) == 0 )
                      {
                        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
                        LODWORD(p) = -1;
                        if ( CShareWithList::FindItem(this, a2, (int *)&p) >= 0 && (_DWORD)p != -1
                          || DPA_InsertPtr(*((HDPA *)this + 3), 0x7FFFFFFF, v18) == -1 )
                        {
                          updated = -2147467259;
                        }
                        else
                        {
                          updated = DirectUI::Element::Add(
                                      *((DirectUI::Element **)this + 2),
                                      v18,
                                      (int (*)(const void *, const void *))SortChildrenProc);
                        }
                        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
                        if ( updated < 0 )
                          goto LABEL_55;
                        if ( (*((_BYTE *)v18 + 151) & 4) == 0 )
                        {
                          updated = CShareWithListItemBase::InitializeUI(v18);
                          if ( updated < 0 )
                          {
LABEL_65:
                            IUnknown_SafeReleaseAndNullPtr<CDeviceSettings>(&v22);
                            goto LABEL_67;
                          }
                          if ( (*((_BYTE *)v18 + 151) & 4) == 0 )
                          {
                            updated = CShareWithList::FilterDevice(this, v18);
                            goto LABEL_65;
                          }
                        }
                        updated = -2147467259;
                        goto LABEL_65;
                      }
                    }
                  }
                  updated = -2147467259;
                }
              }
            }
LABEL_55:
            if ( (*((_BYTE *)v18 + 151) & 4) == 0 )
              IUnknown_SafeReleaseAndNullPtr<CDeviceSettings>((char *)v18 + 216);
            DirectUI::Element::Destroy(v18, 1);
            goto LABEL_65;
          }
        }
      }
    }
    else
    {
      v22 = 0;
    }
    updated = -2147467259;
    goto LABEL_65;
  }
  updated = CShareWithList::UpdateDevice(this, a2);
LABEL_67:
  if ( (Microsoft_Windows_ShareMedia_ControlPanelEnableBits & 1) != 0 )
    McTemplateU0zq_EventWriteTransfer(v10, ShareMediaCPL_AddDevice_Stop, a2, (unsigned int)updated);
  v6 = WPP_GLOBAL_Control;
LABEL_71:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x20) != 0 )
    WPP_SF_d(v6[2], 120, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids, (unsigned int)updated);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18000822c  mov     [rsp-38h+arg_0], rbx
0x180008231  push    rbp
0x180008232  push    rsi
0x180008233  push    rdi
0x180008234  push    r12
0x180008236  push    r13
0x180008238  push    r14
0x18000823a  push    r15
0x18000823c  mov     rbp, rsp
0x18000823f  sub     rsp, 40h
0x180008243  mov     rdi, r8
0x180008246  mov     r15, rdx
0x180008249  mov     rsi, rcx
0x18000824c  mov     r10, cs:WPP_GLOBAL_Control
0x180008253  lea     r14, WPP_GLOBAL_Control
0x18000825a  cmp     r10, r14
0x18000825d  jz      short loc_180008282
0x18000825f  test    byte ptr [r10+1Ch], 20h
0x180008264  jz      short loc_180008282
0x180008266  mov     rcx, [r10+10h]
0x18000826a  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x180008271  mov     edx, 76h ; 'v'
0x180008276  call    WPP_SF_
0x18000827b  mov     r10, cs:WPP_GLOBAL_Control
0x180008282  xor     r13d, r13d
0x180008285  test    r15, r15
0x180008288  jz      loc_180008655
0x18000828e  mov     ecx, 7FFFFFFFh
0x180008293  mov     rax, r15
0x180008296  mov     r9d, ecx
0x180008299  cmp     [rax], r13w
0x18000829d  jz      short loc_1800082A9
0x18000829f  add     rax, 2
0x1800082a3  sub     r9, 1
0x1800082a7  jnz     short loc_180008299
0x1800082a9  sub     ecx, r9d
0x1800082ac  mov     rax, r9
0x1800082af  neg     rax
0x1800082b2  mov     r8, r9
0x1800082b5  sbb     edx, edx
0x1800082b7  and     edx, ecx
0x1800082b9  neg     r8
0x1800082bc  sbb     ecx, ecx
0x1800082be  and     ecx, edx
0x1800082c0  neg     r9
0x1800082c3  sbb     eax, eax
0x1800082c5  test    ecx, eax
0x1800082c7  jbe     loc_180008655
0x1800082cd  cmp     r10, r14
0x1800082d0  jz      short loc_1800082F1
0x1800082d2  test    byte ptr [r10+1Ch], 8
0x1800082d7  jz      short loc_1800082F1
0x1800082d9  mov     rcx, [r10+10h]
0x1800082dd  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x1800082e4  mov     edx, 77h ; 'w'
0x1800082e9  mov     r9, r15
0x1800082ec  call    WPP_SF_S
0x1800082f1  test    cs:Microsoft_Windows_ShareMedia_ControlPanelEnableBits, 1
0x1800082f8  jz      short loc_18000830C
0x1800082fa  xor     r9d, r9d
0x1800082fd  lea     rdx, ShareMediaCPL_AddDevice_Start
0x180008304  mov     r8, r15
0x180008307  call    McTemplateU0zq_EventWriteTransfer
0x18000830c  lea     rdx, psz; "00-00-00-00-00-00"
0x180008313  mov     rcx, r15; lpString1
0x180008316  call    cs:__imp_lstrcmpiW
0x18000831c  test    eax, eax
0x18000831e  jz      loc_18000862C
0x180008324  lea     r8, [rbp+p]; int *
0x180008328  mov     dword ptr [rbp+p], 0FFFFFFFFh
0x18000832f  mov     rdx, r15; unsigned __int16 *
0x180008332  mov     rcx, rsi; this
0x180008335  call    ?FindItem@CShareWithList@@QEAAJPEAGPEAH@Z; CShareWithList::FindItem(ushort *,int *)
0x18000833a  test    eax, eax
0x18000833c  js      short loc_180008356
0x18000833e  cmp     dword ptr [rbp+p], 0FFFFFFFFh
0x180008342  jz      short loc_180008356
0x180008344  mov     rdx, r15; unsigned __int16 *
0x180008347  mov     rcx, rsi; this
0x18000834a  call    ?UpdateDevice@CShareWithList@@QEAAJPEAG@Z; CShareWithList::UpdateDevice(ushort *)
0x18000834f  mov     ebx, eax
0x180008351  jmp     loc_180008631
0x180008356  mov     rcx, [rsi+28h]
0x18000835a  mov     [rbp+arg_18], r13
0x18000835e  test    rcx, rcx
0x180008361  jz      loc_180008611
0x180008367  mov     [rbp+p], r13
0x18000836b  lea     rdx, [rbp+p]
0x18000836f  mov     rax, [rcx]
0x180008372  mov     rax, [rax+58h]
0x180008376  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000837b  mov     ebx, eax
0x18000837d  test    eax, eax
0x18000837f  js      short loc_1800083AA
0x180008381  mov     rcx, [rbp+p]
0x180008385  lea     r8, [rbp+arg_18]
0x180008389  mov     rdx, r15
0x18000838c  mov     rax, [rcx]
0x18000838f  mov     rax, [rax+48h]
0x180008393  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008398  mov     rcx, [rbp+p]
0x18000839c  mov     ebx, eax
0x18000839e  mov     rax, [rcx]
0x1800083a1  mov     rax, [rax+10h]
0x1800083a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083aa  mov     [rbp+var_10], r13
0x1800083ae  mov     r14, r13
0x1800083b1  test    ebx, ebx
0x1800083b3  js      short loc_180008425
0x1800083b5  mov     ecx, 70h ; 'p'; Size
0x1800083ba  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800083bf  test    rax, rax
0x1800083c2  jz      short loc_180008420
0x1800083c4  mov     rcx, rax; this
0x1800083c7  call    ??0CDeviceSettings@@QEAA@XZ; CDeviceSettings::CDeviceSettings(void)
0x1800083cc  mov     [rbp+var_10], rax
0x1800083d0  mov     r14, rax
0x1800083d3  test    rax, rax
0x1800083d6  jz      short loc_180008420
0x1800083d8  mov     rdx, r15; unsigned __int16 *
0x1800083db  mov     rcx, rax; this
0x1800083de  call    ?SetID@CDeviceSettings@@QEAAJPEBG@Z; CDeviceSettings::SetID(ushort const *)
0x1800083e3  mov     ebx, eax
0x1800083e5  test    eax, eax
0x1800083e7  js      short loc_180008425
0x1800083e9  mov     rdx, [rbp+arg_18]; struct INSSDevice *
0x1800083ed  mov     rcx, r14; this
0x1800083f0  call    ?SetDevice@CDeviceSettings@@QEAAJPEAUINSSDevice@@@Z; CDeviceSettings::SetDevice(INSSDevice *)
0x1800083f5  mov     ebx, eax
0x1800083f7  test    eax, eax
0x1800083f9  js      short loc_180008425
0x1800083fb  test    rdi, rdi
0x1800083fe  jz      short loc_180008411
0x180008400  mov     rdx, rdi; struct __MIDL___MIDL_itf_playerps_0000_0005_0004 *
0x180008403  mov     rcx, r14; this
0x180008406  call    ?SetWMPDeviceSettings@CDeviceSettings@@QEAAJPEAU__MIDL___MIDL_itf_playerps_0000_0005_0004@@@Z; CDeviceSettings::SetWMPDeviceSettings(__MIDL___MIDL_itf_playerps_0000_0005_0004 *)
0x18000840b  mov     ebx, eax
0x18000840d  test    eax, eax
0x18000840f  js      short loc_180008425
0x180008411  mov     rdx, r14; struct CDeviceSettings *
0x180008414  mov     rcx, rsi; this
0x180008417  call    ?ApplyAutoAuthorizationStatus@CShareWithList@@QEAAJPEAVCDeviceSettings@@@Z; CShareWithList::ApplyAutoAuthorizationStatus(CDeviceSettings *)
0x18000841c  mov     ebx, eax
0x18000841e  jmp     short loc_180008425
0x180008420  mov     ebx, 8007000Eh
0x180008425  mov     rcx, [rbp+arg_18]
0x180008429  test    rcx, rcx
0x18000842c  jz      short loc_18000843E
0x18000842e  mov     [rbp+arg_18], r13
0x180008432  mov     rax, [rcx]
0x180008435  mov     rax, [rax+10h]
0x180008439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000843e  test    ebx, ebx
0x180008440  js      loc_18000861A
0x180008446  cmp     [rsi+20h], r13
0x18000844a  jz      loc_18000861A
0x180008450  test    r14, r14
0x180008453  jz      loc_18000861A
0x180008459  cmp     [rsi+74h], r13d
0x18000845d  jnz     loc_180008615
0x180008463  mov     rcx, [rsi+10h]; struct DirectUI::Element *
0x180008467  test    rcx, rcx
0x18000846a  jz      loc_180008615
0x180008470  test    byte ptr [rcx+97h], 4
0x180008477  jnz     loc_180008615
0x18000847d  lea     r8, [rbp+p]; struct DirectUI::Element **
0x180008481  mov     [rbp+p], r13
0x180008485  xor     edx, edx; unsigned int *
0x180008487  call    ?Create@CShareWithListItemDevice@@SAJPEAVElement@DirectUI@@PEAKPEAPEAV23@@Z; CShareWithListItemDevice::Create(DirectUI::Element *,ulong *,DirectUI::Element * *)
0x18000848c  mov     ebx, eax
0x18000848e  test    eax, eax
0x180008490  js      loc_18000861A
0x180008496  mov     rdi, [rbp+p]
0x18000849a  lea     rax, [rbp+var_8]
0x18000849e  mov     rcx, [rsi+20h]
0x1800084a2  lea     rdx, aMacroSharingLi; "macro_sharing_list_item"
0x1800084a9  mov     [rsp+40h+var_18], rax
0x1800084ae  mov     r8, rdi
0x1800084b1  xor     r9d, r9d
0x1800084b4  mov     [rsp+40h+var_20], r13
0x1800084b9  mov     [rbp+var_8], r13
0x1800084bd  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x1800084c3  mov     ebx, eax
0x1800084c5  test    eax, eax
0x1800084c7  js      loc_18000861A
0x1800084cd  mov     rdx, r15
0x1800084d0  mov     rcx, rdi
0x1800084d3  call    cs:__imp_?SetID@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetID(ushort const *)
0x1800084d9  mov     rdx, r14; struct CDeviceSettings *
0x1800084dc  mov     rcx, rdi; this
0x1800084df  call    ?SetDeviceSettings@CShareWithListItemBase@@QEAAJPEAVCDeviceSettings@@@Z; CShareWithListItemBase::SetDeviceSettings(CDeviceSettings *)
0x1800084e4  mov     ebx, eax
0x1800084e6  mov     r14d, 80004005h
0x1800084ec  test    eax, eax
0x1800084ee  js      loc_1800085B9
0x1800084f4  mov     rdx, [rsi+38h]; HWND
0x1800084f8  mov     rcx, rdi; this
0x1800084fb  call    ?SetParent@CShareWithListItemBase@@QEAAJPEAUHWND__@@@Z; CShareWithListItemBase::SetParent(HWND__ *)
0x180008500  mov     ebx, eax
0x180008502  test    eax, eax
0x180008504  js      loc_1800085B9
0x18000850a  cmp     [rsi+70h], r13b
0x18000850e  mov     edx, r13d
0x180008511  mov     rcx, rdi; this
0x180008514  setz    dl; int
0x180008517  call    ?SetShowPowerManagementLabel@CShareWithListItemBase@@QEAAJH@Z; CShareWithListItemBase::SetShowPowerManagementLabel(int)
0x18000851c  mov     ebx, eax
0x18000851e  test    eax, eax
0x180008520  js      loc_1800085B9
0x180008526  cmp     [rsi+74h], r13d
0x18000852a  jnz     loc_1800085B6
0x180008530  mov     rax, [rsi+10h]
0x180008534  test    rax, rax
0x180008537  jz      short loc_1800085B6
0x180008539  test    byte ptr [rax+97h], 4
0x180008540  jnz     short loc_1800085B6
0x180008542  test    byte ptr [rdi+97h], 4
0x180008549  jnz     short loc_1800085B6
0x18000854b  lea     rcx, [rsi+48h]; lpCriticalSection
0x18000854f  call    cs:__imp_EnterCriticalSection
0x180008555  lea     r8, [rbp+p]; int *
0x180008559  mov     dword ptr [rbp+p], 0FFFFFFFFh
0x180008560  mov     rdx, r15; unsigned __int16 *
0x180008563  mov     rcx, rsi; this
0x180008566  call    ?FindItem@CShareWithList@@QEAAJPEAGPEAH@Z; CShareWithList::FindItem(ushort *,int *)
0x18000856b  test    eax, eax
0x18000856d  js      short loc_180008575
0x18000856f  cmp     dword ptr [rbp+p], 0FFFFFFFFh
0x180008573  jnz     short loc_1800085A3
0x180008575  mov     rcx, [rsi+18h]; hdpa
0x180008579  mov     r8, rdi; p
0x18000857c  mov     edx, 7FFFFFFFh; i
0x180008581  call    DPA_InsertPtr
0x180008586  cmp     eax, 0FFFFFFFFh
0x180008589  jz      short loc_1800085A3
0x18000858b  mov     rcx, [rsi+10h]
0x18000858f  lea     r8, ?SortChildrenProc@@YAHPEBX0@Z; SortChildrenProc(void const *,void const *)
0x180008596  mov     rdx, rdi
0x180008599  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@P6AHPEBX1@Z@Z; DirectUI::Element::Add(DirectUI::Element *,int (*)(void const *,void const *))
0x18000859f  mov     ebx, eax
0x1800085a1  jmp     short loc_1800085A6
0x1800085a3  mov     ebx, r14d
0x1800085a6  lea     rcx, [rsi+48h]; lpCriticalSection
0x1800085aa  call    cs:__imp_LeaveCriticalSection
0x1800085b0  test    ebx, ebx
0x1800085b2  jns     short loc_1800085DD
0x1800085b4  jmp     short loc_1800085B9
0x1800085b6  mov     ebx, r14d
0x1800085b9  test    byte ptr [rdi+97h], 4
0x1800085c0  jnz     short loc_1800085CE
0x1800085c2  lea     rcx, [rdi+0D8h]
0x1800085c9  call    ??$IUnknown_SafeReleaseAndNullPtr@VCDeviceSettings@@@@YAXAEAPEAVCDeviceSettings@@@Z; IUnknown_SafeReleaseAndNullPtr<CDeviceSettings>(CDeviceSettings * &)
0x1800085ce  mov     dl, 1
0x1800085d0  mov     rcx, rdi
0x1800085d3  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x1800085d9  test    ebx, ebx
0x1800085db  js      short loc_18000861A
0x1800085dd  test    byte ptr [rdi+97h], 4
0x1800085e4  jnz     short loc_18000860C
0x1800085e6  mov     rcx, rdi; this
0x1800085e9  call    ?InitializeUI@CShareWithListItemBase@@QEAAJXZ; CShareWithListItemBase::InitializeUI(void)
0x1800085ee  mov     ebx, eax
0x1800085f0  test    eax, eax
0x1800085f2  js      short loc_18000861A
0x1800085f4  test    byte ptr [rdi+97h], 4
0x1800085fb  jnz     short loc_18000860C
0x1800085fd  mov     rdx, rdi; struct CShareWithListItemBase *
0x180008600  mov     rcx, rsi; this
0x180008603  call    ?FilterDevice@CShareWithList@@QEAAJPEAVCShareWithListItemBase@@@Z; CShareWithList::FilterDevice(CShareWithListItemBase *)
0x180008608  mov     ebx, eax
0x18000860a  jmp     short loc_18000861A
0x18000860c  mov     ebx, r14d
0x18000860f  jmp     short loc_18000861A
0x180008611  mov     [rbp+var_10], r13
0x180008615  mov     ebx, 80004005h
0x18000861a  lea     rcx, [rbp+var_10]
0x18000861e  call    ??$IUnknown_SafeReleaseAndNullPtr@VCDeviceSettings@@@@YAXAEAPEAVCDeviceSettings@@@Z; IUnknown_SafeReleaseAndNullPtr<CDeviceSettings>(CDeviceSettings * &)
0x180008623  lea     r14, WPP_GLOBAL_Control
0x18000862a  jmp     short loc_180008631
0x18000862c  mov     ebx, 1
0x180008631  test    cs:Microsoft_Windows_ShareMedia_ControlPanelEnableBits, 1
0x180008638  jz      short loc_18000864C
0x18000863a  mov     r9d, ebx
0x18000863d  lea     rdx, ShareMediaCPL_AddDevice_Stop
0x180008644  mov     r8, r15
0x180008647  call    McTemplateU0zq_EventWriteTransfer
0x18000864c  mov     r10, cs:WPP_GLOBAL_Control
0x180008653  jmp     short loc_18000865A
0x180008655  mov     ebx, 80004003h
0x18000865a  cmp     r10, r14
0x18000865d  jz      short loc_18000867E
0x18000865f  test    byte ptr [r10+1Ch], 20h
0x180008664  jz      short loc_18000867E
0x180008666  mov     rcx, [r10+10h]
0x18000866a  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x180008671  mov     edx, 78h ; 'x'
0x180008676  mov     r9d, ebx
0x180008679  call    WPP_SF_d
0x18000867e  mov     eax, ebx
0x180008680  mov     rbx, [rsp+40h+arg_0]
  ... truncated ...
```
