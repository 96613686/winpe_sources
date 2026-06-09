# wWinMain

- ea: `0x1400479b0`
- end: `0x140048080`
- name: `wWinMain`
- size: `1744`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `30`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140045d70`

## callees

- `0x140006d70`
- `0x140009a40`
- `0x14000b3b0`
- `0x14000b3f0`
- `0x14000c920`
- `0x14003b690`
- `0x14003d754`
- `0x14003f17c`
- `0x14003f1bc`
- `0x140045f20`
- `0x14004629c`
- `0x140047470`
- `0x1400475ec`
- `0x140047730`
- `0x140047768`
- `0x140047798`
- `0x1400477c0`
- `0x140047928`
- `0x1400479b0`
- `0x1400496dc`
- `0x14004a174`
- `0x14004acac`
- `0x14004b158`
- `0x14004bc88`
- `0x14004e408`
- `0x14004e7c0`
- `0x140053cf0`
- `0x1400634b4`
- `0x140091ba8`
- `0x140091d60`

## import_xrefs

- `ADVAPI32!UnregisterTraceGuids` at `0x14004802e`
- `ADVAPI32!UnregisterTraceGuids` at `0x14004802e`
- `KERNEL32!SetEvent` at `0x140047e4e`
- `KERNEL32!SetEvent` at `0x140047e4e`
- `KERNEL32!OpenEventW` at `0x140047e08`
- `KERNEL32!OpenEventW` at `0x140047e08`
- `KERNEL32!CompareStringW` at `0x140047bae`
- `KERNEL32!CompareStringW` at `0x140047bd5`
- `KERNEL32!CompareStringW` at `0x140047dae`
- `KERNEL32!CompareStringW` at `0x140047f00`
- `KERNEL32!CompareStringW` at `0x140047bae`
- `KERNEL32!CompareStringW` at `0x140047bd5`
- `KERNEL32!CompareStringW` at `0x140047dae`
- `KERNEL32!CompareStringW` at `0x140047f00`
- `KERNEL32!HeapSetInformation` at `0x140047ac1`
- `KERNEL32!HeapSetInformation` at `0x140047ac1`
- `api-ms-win-crt-private-l1-1-0!_o__wputenv` at `0x140047aaf`
- `api-ms-win-crt-private-l1-1-0!_o__wputenv` at `0x140047aaf`

## string_xrefs

- `0x140047aa8`: `OANOCACHE=1`
- `0x140047b98`: `installwithfiles`
- `0x140047bc2`: `install`
- `0x140047ce5`: `RunServiceAtInstall`
- `0x140047d90`: `uninstall`
- `0x140047ee3`: `preinstall`

## pseudocode

```c
int __stdcall wWinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)
{
  char v4; // di
  char v6; // si
  int v8; // edx
  int v9; // r8d
  PVOID *v10; // rcx
  int v11; // edx
  int v12; // r8d
  unsigned int started; // edi
  int v14; // r15d
  int v15; // r12d
  int v16; // r13d
  int v17; // r14d
  __int64 v18; // rax
  unsigned int *i; // rcx
  const WCHAR *v20; // rbx
  int v21; // esi
  int v22; // eax
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  const unsigned __int16 *v25; // rdx
  HKEY v26; // rcx
  __int64 v27; // rax
  unsigned int v28; // eax
  unsigned int v29; // edx
  unsigned int v30; // eax
  HANDLE v31; // rax
  void *v32; // rbx
  unsigned int v33; // eax
  _QWORD *v34; // rbx
  TRACEHANDLE v35; // rcx
  unsigned int v37[2]; // [rsp+40h] [rbp-C0h] BYREF
  int v38; // [rsp+48h] [rbp-B8h] BYREF
  PCNZWCH lpString1; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v40[8]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v41[8]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v42[24]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v43[720]; // [rsp+80h] [rbp-80h] BYREF

  v4 = nShowCmd;
  v6 = (char)hPrevInstance;
  _security_init_cookie();
  qword_1400BF808 = 1;
  qword_1400BF800 = 0;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_WmcCdsGuid;
  WPP_GLOBAL_Control = &WPP_MAIN_CB;
  WPP_MAIN_CB = 0;
  WppInitUm();
  McGenEventRegister_EventRegister();
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_qqSd(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, v9, (_DWORD)hInstance, v6, (__int64)lpCmdLine, v4);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 2) != 0 && *((_BYTE *)v10 + 25) >= 5u )
      WPP_SF_(v10[2], 25, &WPP_20c7d429b16f324d7146cc35a3d03fa1_Traceguids);
  }
  _o__wputenv(L"OANOCACHE=1");
  HeapSetInformation(0, HeapEnableTerminationOnCorruption, 0, 0);
  CWMCService::CWMCService((CWMCService *)v43, v11, v12);
  started = 1;
  s_hInst = hInstance;
  if ( (int)SafeGetModuleFileName() >= 0 && (int)InitializeService() >= 0 )
  {
    started = 0;
    v14 = 1;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_20c7d429b16f324d7146cc35a3d03fa1_Traceguids);
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
      v40,
      lpCmdLine);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&lpString1);
    v38 = 0;
    v15 = 0;
    v16 = 0;
    v17 = 0;
    v18 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Tokenize(
            v40,
            v37,
            L" /-",
            &v38);
    ATL::CSimpleStringT<unsigned short,0>::operator=(&lpString1, v18);
    for ( i = v37; ; i = (unsigned int *)v41 )
    {
      ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(i);
      v20 = lpString1;
      if ( !*((_DWORD *)lpString1 - 4) )
      {
        ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&lpString1);
        ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(v40);
        if ( !started )
        {
          if ( v14 != 1 )
            goto LABEL_86;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_20c7d429b16f324d7146cc35a3d03fa1_Traceguids);
          }
          started = CNTService::StartServiceW((CNTService *)v43);
          if ( !started )
          {
LABEL_86:
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_20c7d429b16f324d7146cc35a3d03fa1_Traceguids);
            }
            CNTService::WaitForServiceExit((CNTService *)v43);
          }
        }
        goto LABEL_89;
      }
      v21 = CompareStringW(0x7Fu, 1u, lpString1, -1, L"installwithfiles", -1);
      v22 = CompareStringW(0x7Fu, 1u, v20, -1, L"install", -1);
      if ( (v22 == 2 || v21 == 2) && !v15 )
        break;
      if ( CompareStringW(0x7Fu, 1u, v20, -1, L"uninstall", -1) != 2 || v16 )
      {
        if ( CompareStringW(0x7Fu, 1u, v20, -1, L"preinstall", -1) == 2 && !v17 )
        {
          v17 = 1;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_20c7d429b16f324d7146cc35a3d03fa1_Traceguids);
          }
          v14 = 0;
        }
      }
      else
      {
        v16 = 1;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_20c7d429b16f324d7146cc35a3d03fa1_Traceguids);
        }
        v31 = OpenEventW(0x100002u, 0, L"Global\\ad869ba1-7ad2-4712-a77e-a70ff958b125");
        v32 = v31;
        *(_QWORD *)v37 = v31;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_20c7d429b16f324d7146cc35a3d03fa1_Traceguids, v31);
        }
        if ( v32 )
        {
          v33 = SetEvent(v32);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_20c7d429b16f324d7146cc35a3d03fa1_Traceguids, v33);
          }
          ATL::CHandle::Close((ATL::CHandle *)v37);
        }
        ATL::CHandle::~CHandle((ATL::CHandle *)v37);
        v14 = 0;
        if ( CWMCService::Uninstall((CWMCService *)v43) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_20c7d429b16f324d7146cc35a3d03fa1_Traceguids);
          }
          started = 1;
        }
      }
LABEL_36:
      v27 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Tokenize(
              v40,
              v41,
              L" /-",
              &v38);
      ATL::CSimpleStringT<unsigned short,0>::operator=(&lpString1, v27);
    }
    v15 = 1;
    if ( v22 == 2 )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v24 = 27;
LABEL_29:
        WPP_SF_(v23[2], v24, &WPP_20c7d429b16f324d7146cc35a3d03fa1_Traceguids);
      }
    }
    else
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v24 = 28;
        goto LABEL_29;
      }
    }
    v14 = 0;
    if ( CWMCService::Install((CWMCService *)v43, L"http") )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_20c7d429b16f324d7146cc35a3d03fa1_Traceguids);
      }
      started = 1;
    }
    else
    {
      v37[0] = 0;
      if ( CheckDWORDRegistryValue(v26, v25, L"RunServiceAtInstall", 0, v37, 1) >= 0 && v37[0] == 1 )
      {
        CServiceControl::CServiceControl((CServiceControl *)v42);
        v28 = CServiceControl::Start((CServiceControl *)v42);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_20c7d429b16f324d7146cc35a3d03fa1_Traceguids, v28);
        }
        v30 = CServiceControl::SetStartType((CServiceControl *)v42, v29);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_20c7d429b16f324d7146cc35a3d03fa1_Traceguids, v30);
        }
        CServiceControl::~CServiceControl((CServiceControl *)v42);
      }
    }
    goto LABEL_36;
  }
LABEL_89:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_20c7d429b16f324d7146cc35a3d03fa1_Traceguids, started);
  }
  McGenEventUnregister_EventUnregister();
  v34 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    while ( v34 )
    {
      v35 = v34[1];
      if ( v35 )
      {
        UnregisterTraceGuids(v35);
        v34[1] = 0;
      }
      v34 = (_QWORD *)*v34;
    }
    WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
  }
  CWMCService::~CWMCService((CWMCService *)v43);
  return started;
}

```

## disassembly

```asm
0x1400479b0  mov     [rsp-8+arg_18], rbx
0x1400479b5  push    rbp
0x1400479b6  push    rsi
0x1400479b7  push    rdi
0x1400479b8  push    r12
0x1400479ba  push    r13
0x1400479bc  push    r14
0x1400479be  push    r15
0x1400479c0  lea     rbp, [rsp-260h]
0x1400479c8  sub     rsp, 360h
0x1400479cf  mov     rax, cs:__security_cookie
0x1400479d6  xor     rax, rsp
0x1400479d9  mov     [rbp+290h+var_40], rax
0x1400479e0  mov     edi, r9d
0x1400479e3  mov     r14, r8
0x1400479e6  mov     rsi, rdx
0x1400479e9  mov     rbx, rcx
0x1400479ec  call    __security_init_cookie
0x1400479f1  xor     ecx, ecx
0x1400479f3  mov     cs:qword_1400BF808, 1
0x1400479fe  lea     rax, WPP_ThisDir_CTLGUID_WmcCdsGuid
0x140047a05  mov     cs:qword_1400BF800, rcx
0x140047a0c  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x140047a13  lea     rax, WPP_MAIN_CB
0x140047a1a  mov     cs:WPP_GLOBAL_Control, rax
0x140047a21  mov     cs:WPP_MAIN_CB, rcx
0x140047a28  call    WppInitUm
0x140047a2d  call    McGenEventRegister_EventRegister
0x140047a32  mov     rcx, cs:WPP_GLOBAL_Control
0x140047a39  lea     rax, WPP_GLOBAL_Control
0x140047a40  cmp     rcx, rax
0x140047a43  jz      short loc_140047AA1
0x140047a45  test    byte ptr [rcx+1Ch], 1
0x140047a49  jz      short loc_140047A72
0x140047a4b  cmp     byte ptr [rcx+19h], 5
0x140047a4f  jb      short loc_140047A72
0x140047a51  mov     rcx, [rcx+10h]
0x140047a55  mov     r9, rbx
0x140047a58  mov     [rsp+390h+var_360], edi
0x140047a5c  mov     qword ptr [rsp+390h+cchCount2], r14
0x140047a61  mov     [rsp+390h+lpString2], rsi
0x140047a66  call    WPP_SF_qqSd
0x140047a6b  mov     rcx, cs:WPP_GLOBAL_Control
0x140047a72  lea     rsi, WPP_GLOBAL_Control
0x140047a79  cmp     rcx, rsi
0x140047a7c  jz      short loc_140047AA8
0x140047a7e  test    byte ptr [rcx+1Ch], 2
0x140047a82  jz      short loc_140047AA8
0x140047a84  cmp     byte ptr [rcx+19h], 5
0x140047a88  jb      short loc_140047AA8
0x140047a8a  mov     rcx, [rcx+10h]
0x140047a8e  lea     r8, WPP_20c7d429b16f324d7146cc35a3d03fa1_Traceguids
0x140047a95  mov     edx, 19h
0x140047a9a  call    WPP_SF_
0x140047a9f  jmp     short loc_140047AA8
0x140047aa1  lea     rsi, WPP_GLOBAL_Control
0x140047aa8  lea     rcx, aOanocache1; "OANOCACHE=1"
0x140047aaf  call    cs:__imp__o__wputenv
0x140047ab5  xor     r9d, r9d; HeapInformationLength
0x140047ab8  xor     r8d, r8d; HeapInformation
0x140047abb  xor     ecx, ecx; HeapHandle
0x140047abd  lea     edx, [r9+1]; HeapInformationClass
0x140047ac1  call    cs:__imp_HeapSetInformation
0x140047ac7  lea     rcx, [rbp+290h+var_310]; this
0x140047acb  call    ??0CWMCService@@QEAA@HH@Z; CWMCService::CWMCService(int,int)
0x140047ad0  mov     edi, 1
0x140047ad5  mov     cs:s_hInst, rbx
0x140047adc  call    ?SafeGetModuleFileName@@YAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@Z; SafeGetModuleFileName(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &)
0x140047ae1  test    eax, eax
0x140047ae3  js      loc_140047FE2
0x140047ae9  call    ?InitializeService@@YAJXZ; InitializeService(void)
0x140047aee  test    eax, eax
0x140047af0  js      loc_140047FE2
0x140047af6  xor     edi, edi
0x140047af8  lea     r15d, [rdi+1]
0x140047afc  mov     rcx, cs:WPP_GLOBAL_Control
0x140047b03  cmp     rcx, rsi
0x140047b06  jz      short loc_140047B27
0x140047b08  test    byte ptr [rcx+1Ch], 2
0x140047b0c  jz      short loc_140047B27
0x140047b0e  cmp     byte ptr [rcx+19h], 4
0x140047b12  jb      short loc_140047B27
0x140047b14  mov     rcx, [rcx+10h]
0x140047b18  lea     edx, [rdi+1Ah]
0x140047b1b  lea     r8, WPP_20c7d429b16f324d7146cc35a3d03fa1_Traceguids
0x140047b22  call    WPP_SF_
0x140047b27  mov     rdx, r14
0x140047b2a  lea     rcx, [rsp+390h+var_338]
0x140047b2f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x140047b34  lea     rcx, [rsp+390h+lpString1]
0x140047b39  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x140047b3e  lea     r9, [rsp+390h+var_348]
0x140047b43  mov     [rsp+390h+var_348], edi
0x140047b47  lea     r8, asc_1400A6538; " /-"
0x140047b4e  xor     r12d, r12d
0x140047b51  lea     rdx, [rsp+390h+var_350]
0x140047b56  xor     r13d, r13d
0x140047b59  lea     rcx, [rsp+390h+var_338]
0x140047b5e  xor     r14d, r14d
0x140047b61  call    ?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Tokenize(ushort const *,int &)
0x140047b66  mov     rdx, rax
0x140047b69  lea     rcx, [rsp+390h+lpString1]
0x140047b6e  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x140047b73  lea     rcx, [rsp+390h+var_350]
0x140047b78  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140047b7d  mov     rbx, [rsp+390h+lpString1]
0x140047b82  cmp     dword ptr [rbx-10h], 0
0x140047b86  jz      loc_140047F54
0x140047b8c  or      r9d, 0FFFFFFFFh; cchCount1
0x140047b90  mov     [rsp+390h+cchCount2], 0FFFFFFFFh; cchCount2
0x140047b98  lea     rax, aInstallwithfil; "installwithfiles"
0x140047b9f  mov     r8, rbx; lpString1
0x140047ba2  mov     [rsp+390h+lpString2], rax; lpString2
0x140047ba7  lea     edx, [r9+2]; dwCmpFlags
0x140047bab  lea     ecx, [rdx+7Eh]; Locale
0x140047bae  call    cs:__imp_CompareStringW
0x140047bb4  or      r9d, 0FFFFFFFFh; cchCount1
0x140047bb8  mov     r8, rbx; lpString1
0x140047bbb  mov     esi, eax
0x140047bbd  mov     [rsp+390h+cchCount2], r9d; cchCount2
0x140047bc2  lea     rax, aInstall; "install"
0x140047bc9  mov     [rsp+390h+lpString2], rax; lpString2
0x140047bce  lea     edx, [r9+2]; dwCmpFlags
0x140047bd2  lea     ecx, [rdx+7Eh]; Locale
0x140047bd5  call    cs:__imp_CompareStringW
0x140047bdb  cmp     eax, 2
0x140047bde  jz      short loc_140047BE9
0x140047be0  cmp     esi, 2
0x140047be3  jnz     loc_140047D8D
0x140047be9  test    r12d, r12d
0x140047bec  jnz     loc_140047D8D
0x140047bf2  lea     esi, [r12+1]
0x140047bf7  mov     r12d, esi
0x140047bfa  cmp     eax, 2
0x140047bfd  jnz     short loc_140047C22
0x140047bff  mov     rcx, cs:WPP_GLOBAL_Control
0x140047c06  lea     rbx, WPP_GLOBAL_Control
0x140047c0d  cmp     rcx, rbx
0x140047c10  jz      short loc_140047C56
0x140047c12  test    [rcx+1Ch], al
0x140047c15  jz      short loc_140047C56
0x140047c17  cmp     byte ptr [rcx+19h], 4
0x140047c1b  jb      short loc_140047C56
0x140047c1d  lea     edx, [rsi+1Ah]
0x140047c20  jmp     short loc_140047C46
0x140047c22  mov     rcx, cs:WPP_GLOBAL_Control
0x140047c29  lea     rbx, WPP_GLOBAL_Control
0x140047c30  cmp     rcx, rbx
0x140047c33  jz      short loc_140047C56
0x140047c35  test    byte ptr [rcx+1Ch], 2
0x140047c39  jz      short loc_140047C56
0x140047c3b  cmp     byte ptr [rcx+19h], 4
0x140047c3f  jb      short loc_140047C56
0x140047c41  mov     edx, 1Ch
0x140047c46  mov     rcx, [rcx+10h]
0x140047c4a  lea     r8, WPP_20c7d429b16f324d7146cc35a3d03fa1_Traceguids
0x140047c51  call    WPP_SF_
0x140047c56  lea     rdx, Dependencies; "http"
0x140047c5d  xor     r15d, r15d
0x140047c60  lea     rcx, [rbp+290h+var_310]; this
0x140047c64  call    ?Install@CWMCService@@UEAAKPEAG@Z; CWMCService::Install(ushort *)
0x140047c69  test    eax, eax
0x140047c6b  jz      short loc_140047CD4
0x140047c6d  mov     rcx, cs:WPP_GLOBAL_Control
0x140047c74  cmp     rcx, rbx
0x140047c77  jz      short loc_140047C99
0x140047c79  test    byte ptr [rcx+1Ch], 2
0x140047c7d  jz      short loc_140047C99
0x140047c7f  cmp     byte ptr [rcx+19h], 2
0x140047c83  jb      short loc_140047C99
0x140047c85  mov     rcx, [rcx+10h]
0x140047c89  lea     edx, [r15+1Dh]
0x140047c8d  lea     r8, WPP_20c7d429b16f324d7146cc35a3d03fa1_Traceguids
0x140047c94  call    WPP_SF_
0x140047c99  mov     edi, esi
0x140047c9b  lea     rsi, WPP_GLOBAL_Control
0x140047ca2  lea     r9, [rsp+390h+var_348]
0x140047ca7  lea     r8, asc_1400A6538; " /-"
0x140047cae  lea     rdx, [rsp+390h+var_330]
0x140047cb3  lea     rcx, [rsp+390h+var_338]
0x140047cb8  call    ?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Tokenize(ushort const *,int &)
0x140047cbd  mov     rdx, rax
0x140047cc0  lea     rcx, [rsp+390h+lpString1]
0x140047cc5  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x140047cca  lea     rcx, [rsp+390h+var_330]
0x140047ccf  jmp     loc_140047B78
0x140047cd4  lea     rax, [rsp+390h+var_350]
0x140047cd9  mov     [rsp+390h+cchCount2], esi; int
0x140047cdd  xor     r9d, r9d; unsigned int
0x140047ce0  mov     [rsp+390h+lpString2], rax; unsigned int *
0x140047ce5  lea     r8, aRunserviceatin; "RunServiceAtInstall"
0x140047cec  mov     [rsp+390h+var_350], r15d
0x140047cf1  call    ?CheckDWORDRegistryValue@@YAJPEAUHKEY__@@PEBG1KAEAKH@Z; CheckDWORDRegistryValue(HKEY__ *,ushort const *,ushort const *,ulong,ulong &,int)
0x140047cf6  test    eax, eax
0x140047cf8  js      short loc_140047C9B
0x140047cfa  cmp     [rsp+390h+var_350], esi
0x140047cfe  jnz     short loc_140047C9B
0x140047d00  lea     rcx, [rsp+390h+var_328]; this
0x140047d05  call    ??0CServiceControl@@QEAA@XZ; CServiceControl::CServiceControl(void)
0x140047d0a  lea     rcx, [rsp+390h+var_328]; this
0x140047d0f  call    ?Start@CServiceControl@@QEAAHXZ; CServiceControl::Start(void)
0x140047d14  mov     rcx, cs:WPP_GLOBAL_Control
0x140047d1b  cmp     rcx, rbx
0x140047d1e  jz      short loc_140047D44
0x140047d20  test    byte ptr [rcx+1Ch], 2
0x140047d24  jz      short loc_140047D44
0x140047d26  cmp     byte ptr [rcx+19h], 4
0x140047d2a  jb      short loc_140047D44
0x140047d2c  mov     rcx, [rcx+10h]
0x140047d30  lea     r8, WPP_20c7d429b16f324d7146cc35a3d03fa1_Traceguids
0x140047d37  mov     edx, 1Eh
0x140047d3c  mov     r9d, eax
0x140047d3f  call    WPP_SF_d
0x140047d44  lea     rcx, [rsp+390h+var_328]; this
0x140047d49  call    ?SetStartType@CServiceControl@@QEAAHK@Z; CServiceControl::SetStartType(ulong)
0x140047d4e  mov     rcx, cs:WPP_GLOBAL_Control
0x140047d55  cmp     rcx, rbx
0x140047d58  jz      short loc_140047D7E
0x140047d5a  test    byte ptr [rcx+1Ch], 2
0x140047d5e  jz      short loc_140047D7E
0x140047d60  cmp     byte ptr [rcx+19h], 4
0x140047d64  jb      short loc_140047D7E
0x140047d66  mov     rcx, [rcx+10h]
0x140047d6a  lea     r8, WPP_20c7d429b16f324d7146cc35a3d03fa1_Traceguids
0x140047d71  mov     edx, 1Fh
0x140047d76  mov     r9d, eax
0x140047d79  call    WPP_SF_d
0x140047d7e  lea     rcx, [rsp+390h+var_328]; this
0x140047d83  call    ??1CServiceControl@@QEAA@XZ; CServiceControl::~CServiceControl(void)
0x140047d88  jmp     loc_140047C9B
0x140047d8d  or      ecx, 0FFFFFFFFh
0x140047d90  lea     rax, aUninstall; "uninstall"
0x140047d97  mov     [rsp+390h+cchCount2], ecx; cchCount2
0x140047d9b  mov     r9d, ecx; cchCount1
0x140047d9e  mov     r8, rbx; lpString1
0x140047da1  mov     [rsp+390h+lpString2], rax; lpString2
0x140047da6  lea     esi, [rcx+2]
0x140047da9  mov     edx, esi; dwCmpFlags
0x140047dab  lea     ecx, [rsi+7Eh]; Locale
0x140047dae  call    cs:__imp_CompareStringW
0x140047db4  cmp     eax, 2
0x140047db7  jnz     loc_140047EE0
0x140047dbd  test    r13d, r13d
0x140047dc0  jnz     loc_140047EE0
0x140047dc6  mov     r13d, esi
0x140047dc9  mov     rcx, cs:WPP_GLOBAL_Control
0x140047dd0  lea     rsi, WPP_GLOBAL_Control
0x140047dd7  cmp     rcx, rsi
0x140047dda  jz      short loc_140047DFA
0x140047ddc  test    [rcx+1Ch], al
0x140047ddf  jz      short loc_140047DFA
0x140047de1  cmp     byte ptr [rcx+19h], 4
0x140047de5  jb      short loc_140047DFA
0x140047de7  mov     rcx, [rcx+10h]
0x140047deb  lea     edx, [rax+1Eh]
0x140047dee  lea     r8, WPP_20c7d429b16f324d7146cc35a3d03fa1_Traceguids
0x140047df5  call    WPP_SF_
0x140047dfa  lea     r8, Name; "Global\\ad869ba1-7ad2-4712-a77e-a70ff95"...
0x140047e01  xor     edx, edx; bInheritHandle
0x140047e03  mov     ecx, 100002h; dwDesiredAccess
0x140047e08  call    cs:__imp_OpenEventW
0x140047e0e  mov     rbx, rax
0x140047e11  mov     qword ptr [rsp+390h+var_350], rax
0x140047e16  mov     rcx, cs:WPP_GLOBAL_Control
0x140047e1d  cmp     rcx, rsi
0x140047e20  jz      short loc_140047E46
0x140047e22  test    byte ptr [rcx+1Ch], 2
0x140047e26  jz      short loc_140047E46
0x140047e28  cmp     byte ptr [rcx+19h], 4
0x140047e2c  jb      short loc_140047E46
0x140047e2e  mov     rcx, [rcx+10h]
0x140047e32  lea     r8, WPP_20c7d429b16f324d7146cc35a3d03fa1_Traceguids
0x140047e39  mov     edx, 21h ; '!'
0x140047e3e  mov     r9, rax
0x140047e41  call    WPP_SF_q
0x140047e46  test    rbx, rbx
0x140047e49  jz      short loc_140047E8E
0x140047e4b  mov     rcx, rbx; hEvent
0x140047e4e  call    cs:__imp_SetEvent
0x140047e54  mov     rcx, cs:WPP_GLOBAL_Control
0x140047e5b  cmp     rcx, rsi
0x140047e5e  jz      short loc_140047E84
0x140047e60  test    byte ptr [rcx+1Ch], 2
0x140047e64  jz      short loc_140047E84
0x140047e66  cmp     byte ptr [rcx+19h], 4
0x140047e6a  jb      short loc_140047E84
0x140047e6c  mov     rcx, [rcx+10h]
0x140047e70  lea     r8, WPP_20c7d429b16f324d7146cc35a3d03fa1_Traceguids
0x140047e77  mov     edx, 22h ; '"'
0x140047e7c  mov     r9d, eax
0x140047e7f  call    WPP_SF_d
0x140047e84  lea     rcx, [rsp+390h+var_350]; this
0x140047e89  call    ?Close@CHandle@ATL@@QEAAXXZ; ATL::CHandle::Close(void)
0x140047e8e  lea     rcx, [rsp+390h+var_350]; this
0x140047e93  call    ??1CHandle@ATL@@QEAA@XZ; ATL::CHandle::~CHandle(void)
0x140047e98  lea     rcx, [rbp+290h+var_310]; this
0x140047e9c  xor     r15d, r15d
0x140047e9f  call    ?Uninstall@CWMCService@@UEAAKXZ; CWMCService::Uninstall(void)
0x140047ea4  test    eax, eax
0x140047ea6  jz      loc_140047CA2
  ... truncated ...
```
