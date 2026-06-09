# CShareMediaCore::s_EnumDevicesThreadProc(void *)

- ea: `0x1800125c0`
- end: `0x1800129fd`
- name: `?s_EnumDevicesThreadProc@CShareMediaCore@@CAKPEAX@Z`
- size: `1085`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001d60`
- `0x180003860`
- `0x180003888`
- `0x1800125c0`
- `0x180012c58`
- `0x1800166a0`
- `0x180016d00`
- `0x18001e010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180012977`
- `KERNEL32!CloseHandle` at `0x180012977`
- `KERNEL32!WaitForSingleObject` at `0x180012812`
- `KERNEL32!WaitForSingleObject` at `0x180012812`
- `KERNEL32!CreateEventW` at `0x18001267b`
- `KERNEL32!CreateEventW` at `0x18001267b`
- `KERNEL32!GetLastError` at `0x18001268d`
- `KERNEL32!GetLastError` at `0x18001268d`
- `ole32!CoCreateInstance` at `0x18001271a`
- `ole32!CoCreateInstance` at `0x1800127ac`
- `ole32!CoCreateInstance` at `0x18001271a`
- `ole32!CoCreateInstance` at `0x1800127ac`
- `ole32!CoUninitialize` at `0x1800129a3`
- `ole32!CoUninitialize` at `0x1800129a3`
- `ole32!CoInitializeEx` at `0x180012624`
- `ole32!CoInitializeEx` at `0x180012624`
- `OLEAUT32!__imp_SysFreeString` at `0x1800128c9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800128c9`

## pseudocode

```c
__int64 __fastcall CShareMediaCore::s_EnumDevicesThreadProc(unsigned int *Parameter)
{
  int Instance; // edi
  __int64 v3; // rcx
  __int64 v4; // rdx
  HANDLE EventW; // rax
  __int64 v6; // rcx
  __int64 v7; // r8
  signed int LastError; // eax
  __int64 v9; // rcx
  __int64 v10; // r8
  struct __MIDL___MIDL_itf_playerps_0000_0005_0004 *v11; // r9
  int WMPDeviceSettings; // eax
  unsigned __int16 *v13; // r9
  int v14; // ebx
  struct __MIDL___MIDL_itf_playerps_0000_0005_0004 *v15; // rdx
  unsigned int i; // r14d
  struct __MIDL___MIDL_itf_playerps_0000_0005_0004 *v17; // r9
  int v18; // eax
  unsigned __int16 *v19; // r9
  int v20; // ebx
  struct __MIDL___MIDL_itf_playerps_0000_0005_0004 *v21; // rdx
  int v23; // [rsp+30h] [rbp-39h] BYREF
  __int64 v24; // [rsp+38h] [rbp-31h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-29h] BYREF
  HMEHelpers *ppv; // [rsp+48h] [rbp-21h] BYREF
  __int64 v27; // [rsp+50h] [rbp-19h] BYREF
  __int64 v28; // [rsp+58h] [rbp-11h] BYREF
  LPVOID v29; // [rsp+60h] [rbp-9h] BYREF
  unsigned __int16 v30[4]; // [rsp+68h] [rbp-1h] BYREF
  int v31; // [rsp+70h] [rbp+7h]
  int v32; // [rsp+74h] [rbp+Bh]
  __int128 v33; // [rsp+78h] [rbp+Fh]
  BSTR *p_bstrString; // [rsp+88h] [rbp+1Fh]
  __int64 v35; // [rsp+90h] [rbp+27h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
  Instance = CoInitializeEx(0, 2u);
  if ( Instance >= 0 )
  {
    if ( Parameter )
    {
      v3 = *((_QWORD *)Parameter + 5);
      v4 = Parameter[12];
      v27 = 0;
      Instance = (*(__int64 (__fastcall **)(__int64, __int64, GUID *, __int64 *))(*(_QWORD *)v3 + 40LL))(
                   v3,
                   v4,
                   &GUID_595d6e65_732c_4736_853f_db64f5aa1eec,
                   &v27);
      if ( Instance >= 0 )
      {
        EventW = CreateEventW(0, 1, 0, 0);
        *((_QWORD *)Parameter + 21) = EventW;
        if ( EventW )
          goto LABEL_11;
        LastError = GetLastError();
        Instance = LastError;
        if ( LastError > 0 )
          Instance = (unsigned __int16)LastError | 0x80070000;
        if ( Instance >= 0 )
        {
LABEL_11:
          v23 = 0;
          if ( (Microsoft_Windows_ShareMedia_ControlPanelEnableBits & 1) != 0 )
          {
            LODWORD(bstrString) = 0;
            *(_QWORD *)&v33 = &v24;
            LODWORD(v24) = 0;
            p_bstrString = &bstrString;
            *((_QWORD *)&v33 + 1) = 4;
            v35 = 4;
            McGenEventWrite_EventWriteTransfer(v6, ShareMediaCPL_PopulateShareWithListView_Start, v7, 3, v30);
          }
          ppv = 0;
          Instance = CoCreateInstance(
                       &GUID_6bf52a52_394a_11d3_b153_00c04f79faa6,
                       0,
                       1u,
                       &GUID_2712e1d1_c205_442e_8a24_b1874058fdee,
                       (LPVOID *)&ppv);
          if ( Instance >= 0 )
          {
            HIDWORD(v33) = 0;
            *(_QWORD *)v30 = 1;
            p_bstrString = 0;
            *(_QWORD *)((char *)&v33 + 4) = 1;
            v31 = 1;
            LODWORD(v33) = 1;
            v32 = 1;
            WMPDeviceSettings = HMEHelpers::RetrieveWMPDeviceSettings(
                                  ppv,
                                  (struct IWMPPlayerInternalMarshalled *)L"00-00-00-00-00-00",
                                  v30,
                                  v11);
            v13 = v30;
            v14 = WMPDeviceSettings;
            if ( WMPDeviceSettings < 0 )
              v13 = 0;
            (*(void (__fastcall **)(__int64, __int64, _QWORD, unsigned __int16 *))(*(_QWORD *)v27 + 24LL))(
              v27,
              1,
              0,
              v13);
            if ( v14 >= 0 )
              HMEHelpers::CleanupWMPDeviceSettings((HMEHelpers *)v30, v15);
            v29 = 0;
            Instance = CoCreateInstance(
                         &GUID_92498132_4d1a_4297_9b78_9e2e4ba99c07,
                         0,
                         1u,
                         &GUID_301936dc_7aa2_4c82_bf04_239ded72c828,
                         &v29);
            if ( Instance >= 0 )
            {
              v24 = 0;
              Instance = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v29 + 88LL))(v29, &v24);
              if ( Instance >= 0 )
              {
                Instance = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v24 + 64LL))(v24, &v23);
                for ( i = 0; (int)i < v23; ++i )
                {
                  if ( Instance < 0 || !WaitForSingleObject(*((HANDLE *)Parameter + 21), 0) )
                    break;
                  v28 = 0;
                  Instance = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v24 + 56LL))(
                               v24,
                               i,
                               &v28);
                  if ( Instance >= 0 )
                  {
                    bstrString = 0;
                    Instance = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v28 + 56LL))(v28, &bstrString);
                    if ( Instance >= 0 )
                    {
                      *(_QWORD *)v30 = 1;
                      p_bstrString = 0;
                      v31 = 1;
                      *(_QWORD *)&v33 = 0x100000001LL;
                      v32 = 1;
                      DWORD2(v33) = 0;
                      v18 = HMEHelpers::RetrieveWMPDeviceSettings(
                              ppv,
                              (struct IWMPPlayerInternalMarshalled *)bstrString,
                              v30,
                              v17);
                      v19 = v30;
                      v20 = v18;
                      if ( v18 < 0 )
                        v19 = 0;
                      (*(void (__fastcall **)(__int64, __int64, BSTR, unsigned __int16 *))(*(_QWORD *)v27 + 24LL))(
                        v27,
                        2,
                        bstrString,
                        v19);
                      if ( v20 >= 0 )
                        HMEHelpers::CleanupWMPDeviceSettings((HMEHelpers *)v30, v21);
                      SysFreeString(bstrString);
                    }
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
                  }
                }
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
              }
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v29 + 16LL))(v29);
            }
            (*(void (__fastcall **)(HMEHelpers *))(*(_QWORD *)ppv + 16LL))(ppv);
          }
          if ( (Microsoft_Windows_ShareMedia_ControlPanelEnableBits & 1) != 0 )
          {
            LODWORD(bstrString) = v23;
            LODWORD(v24) = Instance;
            *(_QWORD *)&v33 = &bstrString;
            p_bstrString = (BSTR *)&v24;
            *((_QWORD *)&v33 + 1) = 4;
            v35 = 4;
            McGenEventWrite_EventWriteTransfer(v9, ShareMediaCPL_PopulateShareWithListView_Stop, v10, 3, v30);
          }
          CloseHandle(*((HANDLE *)Parameter + 21));
          *((_QWORD *)Parameter + 21) = 0;
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      }
      (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)Parameter + 16LL))(Parameter);
    }
    CoUninitialize();
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      93,
      &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids,
      (unsigned int)Instance);
  return 0;
}

```

## disassembly

```asm
0x1800125c0  mov     [rsp-8+arg_8], rbx
0x1800125c5  mov     [rsp-8+arg_10], rsi
0x1800125ca  push    rbp
0x1800125cb  push    rdi
0x1800125cc  push    r12
0x1800125ce  push    r14
0x1800125d0  push    r15
0x1800125d2  lea     rbp, [rsp-37h]
0x1800125d7  sub     rsp, 0A0h
0x1800125de  mov     rax, cs:__security_cookie
0x1800125e5  xor     rax, rsp
0x1800125e8  mov     [rbp+57h+var_28], rax
0x1800125ec  mov     rsi, rcx
0x1800125ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800125f6  lea     rbx, WPP_GLOBAL_Control
0x1800125fd  cmp     rcx, rbx
0x180012600  jz      short loc_18001261D
0x180012602  test    byte ptr [rcx+1Ch], 20h
0x180012606  jz      short loc_18001261D
0x180012608  mov     rcx, [rcx+10h]
0x18001260c  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x180012613  mov     edx, 5Ch ; '\'
0x180012618  call    WPP_SF_
0x18001261d  mov     edx, 2; dwCoInit
0x180012622  xor     ecx, ecx; pvReserved
0x180012624  call    cs:__imp_CoInitializeEx
0x18001262a  xor     r15d, r15d
0x18001262d  mov     edi, eax
0x18001262f  test    eax, eax
0x180012631  js      loc_1800129A9
0x180012637  test    rsi, rsi
0x18001263a  jz      loc_1800129A3
0x180012640  mov     rcx, [rsi+28h]
0x180012644  lea     r9, [rbp+57h+var_70]
0x180012648  mov     edx, [rsi+30h]
0x18001264b  lea     r8, _GUID_595d6e65_732c_4736_853f_db64f5aa1eec
0x180012652  mov     [rbp+57h+var_70], r15
0x180012656  mov     rax, [rcx]
0x180012659  mov     rax, [rax+28h]
0x18001265d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012662  mov     edi, eax
0x180012664  test    eax, eax
0x180012666  js      loc_180012994
0x18001266c  lea     r12d, [r15+1]
0x180012670  xor     r9d, r9d; lpName
0x180012673  mov     edx, r12d; bManualReset
0x180012676  xor     r8d, r8d; bInitialState
0x180012679  xor     ecx, ecx; lpEventAttributes
0x18001267b  call    cs:__imp_CreateEventW
0x180012681  mov     [rsi+0A8h], rax
0x180012688  test    rax, rax
0x18001268b  jnz     short loc_1800126AA
0x18001268d  call    cs:__imp_GetLastError
0x180012693  mov     edi, eax
0x180012695  test    eax, eax
0x180012697  jle     short loc_1800126A2
0x180012699  movzx   edi, ax
0x18001269c  or      edi, 80070000h
0x1800126a2  test    edi, edi
0x1800126a4  js      loc_180012984
0x1800126aa  test    cs:Microsoft_Windows_ShareMedia_ControlPanelEnableBits, r12b
0x1800126b1  mov     [rbp+57h+var_90], r15d
0x1800126b5  jz      short loc_1800126FA
0x1800126b7  lea     rax, [rbp+57h+var_88]
0x1800126bb  mov     dword ptr [rbp+57h+bstrString], r15d
0x1800126bf  mov     [rbp+57h+var_48], rax
0x1800126c3  lea     rdx, ShareMediaCPL_PopulateShareWithListView_Start
0x1800126ca  lea     rax, [rbp+57h+bstrString]
0x1800126ce  mov     dword ptr [rbp+57h+var_88], r15d
0x1800126d2  mov     [rbp+57h+var_38], rax
0x1800126d6  mov     r9d, 3
0x1800126dc  lea     rax, [rbp+57h+var_58]
0x1800126e0  mov     [rbp+57h+var_40], 4
0x1800126e8  mov     [rsp+0C0h+ppv], rax
0x1800126ed  mov     [rbp+57h+var_30], 4
0x1800126f5  call    McGenEventWrite_EventWriteTransfer
0x1800126fa  lea     rax, [rbp+57h+var_78]
0x1800126fe  mov     [rbp+57h+var_78], r15
0x180012702  lea     r9, _GUID_2712e1d1_c205_442e_8a24_b1874058fdee; riid
0x180012709  mov     [rsp+0C0h+ppv], rax; ppv
0x18001270e  mov     r8d, r12d; dwClsContext
0x180012711  lea     rcx, _GUID_6bf52a52_394a_11d3_b153_00c04f79faa6; rclsid
0x180012718  xor     edx, edx; pUnkOuter
0x18001271a  call    cs:__imp_CoCreateInstance
0x180012720  mov     edi, eax
0x180012722  test    eax, eax
0x180012724  js      loc_180012923
0x18001272a  mov     rcx, [rbp+57h+var_78]; this
0x18001272e  lea     r8, [rbp+57h+var_58]; unsigned __int16 *
0x180012732  lea     rdx, psz; "00-00-00-00-00-00"
0x180012739  mov     [rbp+57h+var_40], r15
0x18001273d  mov     qword ptr [rbp+57h+var_58], r12
0x180012741  mov     [rbp+57h+var_38], r15
0x180012745  mov     dword ptr [rbp+57h+var_48+4], r12d
0x180012749  mov     [rbp+57h+var_50], r12d
0x18001274d  mov     dword ptr [rbp+57h+var_48], r12d
0x180012751  mov     [rbp+57h+var_4C], r12d
0x180012755  call    ?RetrieveWMPDeviceSettings@HMEHelpers@@YAJPEAUIWMPPlayerInternalMarshalled@@PEAGPEAU__MIDL___MIDL_itf_playerps_0000_0005_0004@@@Z; HMEHelpers::RetrieveWMPDeviceSettings(IWMPPlayerInternalMarshalled *,ushort *,__MIDL___MIDL_itf_playerps_0000_0005_0004 *)
0x18001275a  mov     r10, [rbp+57h+var_70]
0x18001275e  lea     r9, [rbp+57h+var_58]
0x180012762  test    eax, eax
0x180012764  mov     ebx, eax
0x180012766  mov     rcx, r10
0x180012769  cmovs   r9, r15
0x18001276d  xor     r8d, r8d
0x180012770  mov     rdx, [r10]
0x180012773  mov     rax, [rdx+18h]
0x180012777  mov     edx, r12d
0x18001277a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001277f  test    ebx, ebx
0x180012781  js      short loc_18001278C
0x180012783  lea     rcx, [rbp+57h+var_58]; this
0x180012787  call    ?CleanupWMPDeviceSettings@HMEHelpers@@YAJPEAU__MIDL___MIDL_itf_playerps_0000_0005_0004@@@Z; HMEHelpers::CleanupWMPDeviceSettings(__MIDL___MIDL_itf_playerps_0000_0005_0004 *)
0x18001278c  lea     rax, [rbp+57h+var_60]
0x180012790  mov     [rbp+57h+var_60], r15
0x180012794  lea     r9, _GUID_301936dc_7aa2_4c82_bf04_239ded72c828; riid
0x18001279b  mov     [rsp+0C0h+ppv], rax; ppv
0x1800127a0  mov     r8d, r12d; dwClsContext
0x1800127a3  lea     rcx, _GUID_92498132_4d1a_4297_9b78_9e2e4ba99c07; rclsid
0x1800127aa  xor     edx, edx; pUnkOuter
0x1800127ac  call    cs:__imp_CoCreateInstance
0x1800127b2  mov     edi, eax
0x1800127b4  test    eax, eax
0x1800127b6  js      loc_18001290C
0x1800127bc  mov     rcx, [rbp+57h+var_60]
0x1800127c0  lea     rdx, [rbp+57h+var_88]
0x1800127c4  mov     [rbp+57h+var_88], r15
0x1800127c8  mov     rax, [rcx]
0x1800127cb  mov     rax, [rax+58h]
0x1800127cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127d4  mov     edi, eax
0x1800127d6  test    eax, eax
0x1800127d8  js      loc_1800128FC
0x1800127de  mov     rcx, [rbp+57h+var_88]
0x1800127e2  lea     rdx, [rbp+57h+var_90]
0x1800127e6  mov     rax, [rcx]
0x1800127e9  mov     rax, [rax+40h]
0x1800127ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127f2  mov     edi, eax
0x1800127f4  mov     r14d, r15d
0x1800127f7  cmp     [rbp+57h+var_90], r15d
0x1800127fb  jle     loc_1800128EC
0x180012801  test    edi, edi
0x180012803  js      loc_1800128EC
0x180012809  mov     rcx, [rsi+0A8h]; hHandle
0x180012810  xor     edx, edx; dwMilliseconds
0x180012812  call    cs:__imp_WaitForSingleObject
0x180012818  test    eax, eax
0x18001281a  jz      loc_1800128EC
0x180012820  mov     rcx, [rbp+57h+var_88]
0x180012824  lea     r8, [rbp+57h+var_68]
0x180012828  mov     [rbp+57h+var_68], r15
0x18001282c  mov     edx, r14d
0x18001282f  mov     rax, [rcx]
0x180012832  mov     rax, [rax+38h]
0x180012836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001283b  mov     edi, eax
0x18001283d  test    eax, eax
0x18001283f  js      loc_1800128DF
0x180012845  mov     rcx, [rbp+57h+var_68]
0x180012849  lea     rdx, [rbp+57h+bstrString]
0x18001284d  mov     [rbp+57h+bstrString], r15
0x180012851  mov     rax, [rcx]
0x180012854  mov     rax, [rax+38h]
0x180012858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001285d  mov     edi, eax
0x18001285f  test    eax, eax
0x180012861  js      short loc_1800128CF
0x180012863  mov     rdx, [rbp+57h+bstrString]; struct IWMPPlayerInternalMarshalled *
0x180012867  lea     r8, [rbp+57h+var_58]; unsigned __int16 *
0x18001286b  mov     rcx, [rbp+57h+var_78]; this
0x18001286f  mov     qword ptr [rbp+57h+var_58], r12
0x180012873  mov     [rbp+57h+var_38], r15
0x180012877  mov     dword ptr [rbp+57h+var_48+4], r12d
0x18001287b  mov     [rbp+57h+var_50], r12d
0x18001287f  mov     dword ptr [rbp+57h+var_48], r12d
0x180012883  mov     [rbp+57h+var_4C], r12d
0x180012887  mov     dword ptr [rbp+57h+var_40], r15d
0x18001288b  call    ?RetrieveWMPDeviceSettings@HMEHelpers@@YAJPEAUIWMPPlayerInternalMarshalled@@PEAGPEAU__MIDL___MIDL_itf_playerps_0000_0005_0004@@@Z; HMEHelpers::RetrieveWMPDeviceSettings(IWMPPlayerInternalMarshalled *,ushort *,__MIDL___MIDL_itf_playerps_0000_0005_0004 *)
0x180012890  mov     r10, [rbp+57h+var_70]
0x180012894  lea     r9, [rbp+57h+var_58]
0x180012898  mov     r8, [rbp+57h+bstrString]
0x18001289c  test    eax, eax
0x18001289e  mov     ebx, eax
0x1800128a0  mov     rcx, r10
0x1800128a3  cmovs   r9, r15
0x1800128a7  mov     rdx, [r10]
0x1800128aa  mov     rax, [rdx+18h]
0x1800128ae  mov     edx, 2
0x1800128b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128b8  test    ebx, ebx
0x1800128ba  js      short loc_1800128C5
0x1800128bc  lea     rcx, [rbp+57h+var_58]; this
0x1800128c0  call    ?CleanupWMPDeviceSettings@HMEHelpers@@YAJPEAU__MIDL___MIDL_itf_playerps_0000_0005_0004@@@Z; HMEHelpers::CleanupWMPDeviceSettings(__MIDL___MIDL_itf_playerps_0000_0005_0004 *)
0x1800128c5  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1800128c9  call    cs:__imp_SysFreeString
0x1800128cf  mov     rcx, [rbp+57h+var_68]
0x1800128d3  mov     rax, [rcx]
0x1800128d6  mov     rax, [rax+10h]
0x1800128da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128df  add     r14d, r12d
0x1800128e2  cmp     r14d, [rbp+57h+var_90]
0x1800128e6  jl      loc_180012801
0x1800128ec  mov     rcx, [rbp+57h+var_88]
0x1800128f0  mov     rax, [rcx]
0x1800128f3  mov     rax, [rax+10h]
0x1800128f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128fc  mov     rcx, [rbp+57h+var_60]
0x180012900  mov     rax, [rcx]
0x180012903  mov     rax, [rax+10h]
0x180012907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001290c  mov     rcx, [rbp+57h+var_78]
0x180012910  mov     rax, [rcx]
0x180012913  mov     rax, [rax+10h]
0x180012917  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001291c  lea     rbx, WPP_GLOBAL_Control
0x180012923  test    cs:Microsoft_Windows_ShareMedia_ControlPanelEnableBits, r12b
0x18001292a  jz      short loc_180012970
0x18001292c  mov     eax, [rbp+57h+var_90]
0x18001292f  lea     rdx, ShareMediaCPL_PopulateShareWithListView_Stop
0x180012936  mov     dword ptr [rbp+57h+bstrString], eax
0x180012939  mov     r9d, 3
0x18001293f  lea     rax, [rbp+57h+bstrString]
0x180012943  mov     dword ptr [rbp+57h+var_88], edi
0x180012946  mov     [rbp+57h+var_48], rax
0x18001294a  lea     rax, [rbp+57h+var_88]
0x18001294e  mov     [rbp+57h+var_38], rax
0x180012952  lea     rax, [rbp+57h+var_58]
0x180012956  mov     [rsp+0C0h+ppv], rax
0x18001295b  mov     [rbp+57h+var_40], 4
0x180012963  mov     [rbp+57h+var_30], 4
0x18001296b  call    McGenEventWrite_EventWriteTransfer
0x180012970  mov     rcx, [rsi+0A8h]; hObject
0x180012977  call    cs:__imp_CloseHandle
0x18001297d  mov     [rsi+0A8h], r15
0x180012984  mov     rcx, [rbp+57h+var_70]
0x180012988  mov     rax, [rcx]
0x18001298b  mov     rax, [rax+10h]
0x18001298f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012994  mov     rax, [rsi]
0x180012997  mov     rcx, rsi
0x18001299a  mov     rax, [rax+10h]
0x18001299e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800129a3  call    cs:__imp_CoUninitialize
0x1800129a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800129b0  cmp     rcx, rbx
0x1800129b3  jz      short loc_1800129D3
0x1800129b5  test    byte ptr [rcx+1Ch], 20h
0x1800129b9  jz      short loc_1800129D3
0x1800129bb  mov     rcx, [rcx+10h]
0x1800129bf  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x1800129c6  mov     edx, 5Dh ; ']'
0x1800129cb  mov     r9d, edi
0x1800129ce  call    WPP_SF_d
0x1800129d3  xor     eax, eax
0x1800129d5  mov     rcx, [rbp+57h+var_28]
0x1800129d9  xor     rcx, rsp; StackCookie
0x1800129dc  call    __security_check_cookie
0x1800129e1  lea     r11, [rsp+0C0h+var_20]
0x1800129e9  mov     rbx, [r11+38h]
0x1800129ed  mov     rsi, [r11+40h]
0x1800129f1  mov     rsp, r11
0x1800129f4  pop     r15
0x1800129f6  pop     r14
0x1800129f8  pop     r12
0x1800129fa  pop     rdi
0x1800129fb  pop     rbp
0x1800129fc  retn
```
