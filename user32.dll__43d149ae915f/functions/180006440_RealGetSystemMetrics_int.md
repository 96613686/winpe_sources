# RealGetSystemMetrics(int)

- ea: `0x180006440`
- end: `0x180006a51`
- name: `?RealGetSystemMetrics@@YAHH@Z`
- size: `1553`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180006170`
- `0x1800318c0`

## callees

- `0x180006014`
- `0x180006440`
- `0x180006a60`
- `0x1800070e0`
- `0x180007640`
- `0x180008828`
- `0x18001346c`
- `0x180014a4c`
- `0x180014c10`
- `0x180014c30`
- `0x180014ec4`
- `0x180051664`
- `0x1800516c8`
- `0x180056f18`
- `0x18005af4c`
- `0x18006ac28`
- `0x18006ac8c`
- `0x180096e00`

## import_xrefs

- `win32u!NtUserGetThreadState` at `0x180006598`
- `win32u!NtUserGetThreadState` at `0x180006598`
- `win32u!NtUserEnsureDpiDepSysMetCacheForPlateau` at `0x18000696a`
- `win32u!NtUserEnsureDpiDepSysMetCacheForPlateau` at `0x18000696a`
- `ntdll!RtlSetLastWin32Error` at `0x180006943`
- `ntdll!RtlSetLastWin32Error` at `0x180006943`
- `ntdll!RtlGetActiveConsoleId` at `0x1800066b6`
- `ntdll!RtlGetActiveConsoleId` at `0x1800066b6`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18000669d`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18000669d`

## string_xrefs

- `0x18000656b`: `\Registry\Machine\Software\Microsoft\Windows\Tablet PC\`

## pseudocode

```c
__int64 __fastcall RealGetSystemMetrics(int a1, unsigned __int16 *a2)
{
  __int64 v2; // rbx
  unsigned __int16 v3; // di
  int DpiDepSysMetCacheMetricSlot; // eax
  __int64 v5; // rsi
  __int64 result; // rax
  unsigned int v7; // r12d
  unsigned int RegistryKeyValue; // eax
  unsigned int v9; // edx
  __int64 v10; // r15
  int DpiCacheIndex; // r14d
  char v12; // r13
  __int64 v13; // r14
  unsigned int v14; // esi
  int v15; // ecx
  ULONG SessionId; // ebx
  ULONG v17; // ebx
  unsigned __int16 v18; // ax
  unsigned __int16 v19; // ax
  unsigned __int16 v20; // ax
  unsigned __int16 CurrentThreadCompositedDpi; // ax
  unsigned __int64 MaxTrackSize; // rcx
  struct tagMONITOR *PrimaryMonitor; // rax
  struct tagMONITOR *v24; // rax
  struct tagMONITOR *v25; // rax
  int v26; // edi
  struct tagMONITOR *v27; // rax
  int v28; // ebx
  unsigned int v29; // eax
  struct tagMONITOR *v30; // rax
  int v31; // edi
  struct tagMONITOR *v32; // rax
  int v33; // ebx
  unsigned int v34; // eax
  struct tagMONITOR *v35; // rax
  struct tagMONITOR *v36; // rax
  unsigned int v37; // ebx
  unsigned int DpiForSystem; // eax
  unsigned int v39; // esi
  _DWORD v40[4]; // [rsp+20h] [rbp-48h] BYREF
  int KeyValueInformation; // [rsp+30h] [rbp-38h] BYREF
  int v42; // [rsp+34h] [rbp-34h]
  int v43; // [rsp+38h] [rbp-30h]
  unsigned int v44; // [rsp+3Ch] [rbp-2Ch]

  v2 = a1;
  if ( !NtCurrentTeb()->Win32ThreadInfo )
  {
    result = NtUserGetThreadState(14);
    if ( !result )
      return result;
  }
  if ( (int)v2 <= 95 )
  {
    switch ( (_DWORD)v2 )
    {
      case '_':
      case 'V':
        goto LABEL_16;
      case 'W':
        return GetRegistryKeyWtoIValue(0, a2) >= 5;
      case '^':
LABEL_16:
        v7 = 0;
        RegistryKeyValue = GetRegistryKeyValue(
                             L"\\Registry\\Machine\\Software\\Microsoft\\Windows\\Tablet PC\\",
                             L"IsTabletPC",
                             &KeyValueInformation,
                             4u);
        v9 = 0;
        if ( RegistryKeyValue )
          v9 = v44;
        if ( (_DWORD)v2 == 94 )
          return v9 & 0xCF;
        if ( (_DWORD)v2 == 95 )
          return (unsigned __int16)(v9 >> 8);
        if ( (v9 & 0xD) != 0 && (v9 & 0x80u) != 0 )
          return 1;
        return v7;
    }
  }
  else
  {
    if ( (_DWORD)v2 == 4096 )
    {
      SessionId = NtCurrentPeb()->SessionId;
      result = 0;
      if ( SessionId != (unsigned int)WTSGetServiceSessionId() )
      {
        v17 = NtCurrentPeb()->SessionId;
        if ( v17 != (unsigned int)RtlGetActiveConsoleId() )
          return 1;
      }
      return result;
    }
    if ( (_DWORD)v2 == 6144 )
      return 1;
    if ( (unsigned int)(v2 - 0x2000) <= 6 )
    {
      v15 = *(_DWORD *)(gpsi + 2236);
      return _bittest(&v15, (unsigned __int8)v2);
    }
  }
  if ( (unsigned int)v2 > 0x60 )
  {
    RtlSetLastWin32Error(0x57u);
    return 0;
  }
  else
  {
    v3 = NtCurrentTeb()->Win32ClientInfo[2];
    switch ( (int)v2 )
    {
      case 0:
        PrimaryMonitor = GetPrimaryMonitor();
        GetMonitorRect(&KeyValueInformation, PrimaryMonitor);
        return (unsigned int)(v43 - KeyValueInformation);
      case 1:
        v24 = GetPrimaryMonitor();
        GetMonitorRect(&KeyValueInformation, v24);
        return v44 - v42;
      case 16:
        v35 = GetPrimaryMonitor();
        GetMonitorWorkRect(&KeyValueInformation, v35);
        return (unsigned int)(v43 - KeyValueInformation);
      case 17:
        v36 = GetPrimaryMonitor();
        GetMonitorWorkRect(&KeyValueInformation, v36);
        v37 = v44;
        DpiForSystem = GetDpiForSystem();
        return v37 - (v3 < 0x400u) - v42 - (unsigned int)GetDpiDependentMetric(2, DpiForSystem);
      case 32:
      case 33:
      case 92:
        return GetWindowFrameMetric((unsigned int)v2);
      case 42:
        return (*(_DWORD *)gpsi >> 1) & 1;
      case 59:
      case 60:
        MaxTrackSize = GetMaxTrackSize();
        result = HIDWORD(MaxTrackSize);
        if ( (_DWORD)v2 == 59 )
          return MaxTrackSize;
        return result;
      case 61:
        v25 = GetPrimaryMonitor();
        GetMonitorWorkRect(&KeyValueInformation, v25);
        v26 = v43;
        v27 = GetPrimaryMonitor();
        GetMonitorWorkRect(v40, v27);
        v28 = v40[0];
        v29 = GetDpiForSystem();
        return v26 + 2 * (unsigned int)GetResizableBorderWidthForDpi(v29) - v28;
      case 62:
        v30 = GetPrimaryMonitor();
        GetMonitorWorkRect(v40, v30);
        v31 = v40[3];
        v32 = GetPrimaryMonitor();
        GetMonitorWorkRect(&KeyValueInformation, v32);
        v33 = v42;
        v34 = GetDpiForSystem();
        return v31 + 2 * (unsigned int)GetResizableBorderHeightForDpi(v34) - v33;
      case 74:
        return (*(_DWORD *)gpsi >> 3) & 1;
      case 76:
        CurrentThreadCompositedDpi = GetCurrentThreadCompositedDpi();
        GetScreenRectForDpi(v40, CurrentThreadCompositedDpi);
        return v40[0];
      case 77:
        v18 = GetCurrentThreadCompositedDpi();
        GetScreenRectForDpi(v40, v18);
        return v40[1];
      case 78:
        v19 = GetCurrentThreadCompositedDpi();
        GetScreenRectForDpi(&KeyValueInformation, v19);
        return (unsigned int)(v43 - KeyValueInformation);
      case 79:
        v20 = GetCurrentThreadCompositedDpi();
        GetScreenRectForDpi(&KeyValueInformation, v20);
        return v44 - v42;
      case 82:
        return (*(_DWORD *)gpsi >> 2) & 1;
      default:
        DpiDepSysMetCacheMetricSlot = GetDpiDepSysMetCacheMetricSlot((unsigned int)v2);
        v5 = DpiDepSysMetCacheMetricSlot;
        if ( DpiDepSysMetCacheMetricSlot >= 0 )
        {
          v10 = (unsigned int)GetDpiForSystem();
          DpiCacheIndex = GetDpiCacheIndex(v10);
          if ( (unsigned int)Feature_DpiMetricsFixes__private_IsEnabledDeviceUsageNoInline() && DpiCacheIndex == -1 )
          {
            v12 = 1;
            DpiCacheIndex = 1;
          }
          else
          {
            v12 = 0;
          }
          v13 = 4 * (v5 + 30LL * DpiCacheIndex) + 2284;
          v14 = *(_DWORD *)(v13 + gpsi);
          if ( v14 == -1 )
          {
            NtUserEnsureDpiDepSysMetCacheForPlateau((unsigned int)v10);
            v14 = *(_DWORD *)(v13 + gpsi);
            if ( v14 == -1 )
              v14 = 0;
          }
          if ( (unsigned int)Feature_DpiMetricsFixes__private_IsEnabledDeviceUsageNoInline() && v12 )
          {
            v39 = (int)((unsigned __int64)(715827883LL * (int)(v10 * v14 + 48)) >> 32) >> 4;
            v14 = (v39 >> 31) + v39;
          }
          if ( v3 < 0x400u )
          {
            if ( (_DWORD)v2 == 3 || (_DWORD)v2 == 2 || (_DWORD)v2 == 4 )
              return v14 + 1;
            if ( (_DWORD)v2 == 15 )
              --v14;
          }
          return v14;
        }
        if ( v3 >= 0x400u || (unsigned int)(v2 - 7) > 1 )
          result = *(unsigned int *)(gpsi + 4 * v2 + 1896);
        else
          result = (unsigned int)(*(_DWORD *)(gpsi + 4 * v2 + 1896) - 1);
        break;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180006440  push    rbp
0x180006442  push    rbx
0x180006443  mov     rbp, rsp
0x180006446  sub     rsp, 68h
0x18000644a  mov     rax, cs:__security_cookie
0x180006451  xor     rax, rsp
0x180006454  mov     [rbp+var_28], rax
0x180006458  mov     rax, gs:30h
0x180006461  movsxd  rbx, ecx
0x180006464  cmp     qword ptr [rax+78h], 0
0x180006469  jz      loc_180006593
0x18000646f  mov     [rsp+68h+arg_18], r12
0x180006477  mov     [rsp+68h+var_10], r14
0x18000647c  cmp     ebx, 5Fh ; '_'
0x18000647f  jle     loc_18000653C
0x180006485  cmp     ebx, 1000h
0x18000648b  jz      loc_18000668E
0x180006491  cmp     ebx, 1800h
0x180006497  jz      loc_1800068C7
0x18000649d  lea     eax, [rbx-2000h]
0x1800064a3  cmp     eax, 6
0x1800064a6  jbe     loc_18000664E
0x1800064ac  cmp     ebx, 60h ; '`'
0x1800064af  ja      loc_18000693E
0x1800064b5  mov     rax, gs:30h
0x1800064be  mov     [rsp+68h+arg_10], rdi
0x1800064c6  movzx   edi, word ptr [rax+810h]
0x1800064cd  cmp     ebx, 5Ch; switch 93 cases
0x1800064d0  jbe     loc_180006627
0x1800064d6  mov     ecx, ebx; jumptable 0000000180006640 default case, cases 2-15,18-31,34-41,43-58,63-73,75,80,81,83-91
0x1800064d8  mov     [rsp+68h+arg_8], rsi
0x1800064e0  call    GetDpiDepSysMetCacheMetricSlot
0x1800064e5  movsxd  rsi, eax
0x1800064e8  test    eax, eax
0x1800064ea  jns     loc_1800065A9
0x1800064f0  mov     ecx, 400h
0x1800064f5  cmp     di, cx
0x1800064f8  jb      loc_18000683B
0x1800064fe  mov     rax, cs:gpsi
0x180006505  mov     eax, [rax+rbx*4+768h]
0x18000650c  mov     rsi, [rsp+68h+arg_8]
0x180006514  mov     rdi, [rsp+68h+arg_10]
0x18000651c  mov     r12, [rsp+68h+arg_18]
0x180006524  mov     r14, [rsp+68h+var_10]
0x180006529  mov     rcx, [rbp+var_28]
0x18000652d  xor     rcx, rsp; StackCookie
0x180006530  call    __security_check_cookie
0x180006535  add     rsp, 68h
0x180006539  pop     rbx
0x18000653a  pop     rbp
0x18000653b  retn
0x18000653c  jz      short loc_180006557
0x18000653e  mov     ecx, ebx
0x180006540  sub     ecx, 56h ; 'V'
0x180006543  jz      short loc_180006557
0x180006545  sub     ecx, 1; unsigned __int16 *
0x180006548  jz      loc_180006950
0x18000654e  cmp     ecx, 7
0x180006551  jnz     loc_1800064AC
0x180006557  mov     r9d, 4; unsigned int
0x18000655d  lea     r8, [rbp+KeyValueInformation]; KeyValueInformation
0x180006561  lea     rdx, aIstabletpc; "IsTabletPC"
0x180006568  xor     r12d, r12d
0x18000656b  lea     rcx, aRegistryMachin_0; "\\Registry\\Machine\\Software\\Microsof"...
0x180006572  call    ?GetRegistryKeyValue@@YAKPEAG0PEAU_KEY_VALUE_PARTIAL_INFORMATION@@K@Z; GetRegistryKeyValue(ushort *,ushort *,_KEY_VALUE_PARTIAL_INFORMATION *,ulong)
0x180006577  test    eax, eax
0x180006579  mov     edx, r12d
0x18000657c  cmovnz  edx, [rbp+var_2C]
0x180006580  cmp     ebx, 5Eh ; '^'
0x180006583  jnz     loc_18000686F
0x180006589  and     edx, 0CFh
0x18000658f  mov     eax, edx
0x180006591  jmp     short loc_18000651C
0x180006593  mov     ecx, 0Eh
0x180006598  call    cs:__imp_NtUserGetThreadState
0x18000659e  test    rax, rax
0x1800065a1  jnz     loc_18000646F
0x1800065a7  jmp     short loc_180006529
0x1800065a9  mov     [rsp+68h+var_18], r15
0x1800065ae  mov     [rsp+68h+var_8], r13
0x1800065b3  call    GetDpiForSystem
0x1800065b8  mov     ecx, eax
0x1800065ba  mov     r15d, eax
0x1800065bd  call    GetDpiCacheIndex
0x1800065c2  mov     r14d, eax
0x1800065c5  call    Feature_DpiMetricsFixes__private_IsEnabledDeviceUsageNoInline
0x1800065ca  test    eax, eax
0x1800065cc  jnz     loc_180006676
0x1800065d2  xor     r13b, r13b
0x1800065d5  movsxd  rax, r14d
0x1800065d8  imul    rcx, rax, 1Eh
0x1800065dc  mov     rax, cs:gpsi
0x1800065e3  add     rcx, rsi
0x1800065e6  lea     r14, ds:8ECh[rcx*4]
0x1800065ee  mov     esi, [r14+rax]
0x1800065f2  cmp     esi, 0FFFFFFFFh
0x1800065f5  jz      loc_180006967
0x1800065fb  call    Feature_DpiMetricsFixes__private_IsEnabledDeviceUsageNoInline
0x180006600  test    eax, eax
0x180006602  jnz     loc_18000698A
0x180006608  mov     r15, [rsp+68h+var_18]
0x18000660d  mov     ecx, 400h
0x180006612  mov     r13, [rsp+68h+var_8]
0x180006617  cmp     di, cx
0x18000661a  jb      loc_18000673C
0x180006620  mov     eax, esi
0x180006622  jmp     loc_18000650C
0x180006627  lea     rdx, __ImageBase
0x18000662e  movzx   eax, ds:(byte_1800069F4 - 180000000h)[rdx+rbx]
0x180006636  mov     ecx, ds:(jpt_180006640 - 180000000h)[rdx+rax*4]
0x18000663d  add     rcx, rdx
0x180006640  jmp     rcx; switch jump
0x180006642  mov     ecx, ebx; jumptable 0000000180006640 cases 32,33,92
0x180006644  call    GetWindowFrameMetric
0x180006649  jmp     loc_180006514
0x18000664e  mov     rax, cs:gpsi
0x180006655  lea     ecx, [rbx-2000h]
0x18000665b  xor     r12d, r12d
0x18000665e  movzx   edx, cl
0x180006661  mov     ecx, [rax+8BCh]
0x180006667  bt      ecx, edx
0x18000666a  setb    r12b
0x18000666e  mov     eax, r12d
0x180006671  jmp     loc_18000651C
0x180006676  cmp     r14d, 0FFFFFFFFh
0x18000667a  jnz     loc_1800065D2
0x180006680  mov     r13b, 1
0x180006683  mov     r14d, 1
0x180006689  jmp     loc_1800065D5
0x18000668e  mov     rax, gs:60h
0x180006697  mov     ebx, [rax+2C0h]
0x18000669d  call    cs:__imp_WTSGetServiceSessionId
0x1800066a3  cmp     ebx, eax
0x1800066a5  jz      short loc_1800066C4
0x1800066a7  mov     rax, gs:60h
0x1800066b0  mov     ebx, [rax+2C0h]
0x1800066b6  call    cs:__imp_RtlGetActiveConsoleId
0x1800066bc  cmp     ebx, eax
0x1800066be  jnz     loc_1800068D1
0x1800066c4  xor     r12d, r12d
0x1800066c7  mov     r14d, r12d
0x1800066ca  mov     eax, r12d
0x1800066cd  jmp     loc_18000651C
0x1800066d2  call    GetCurrentThreadCompositedDpi; jumptable 0000000180006640 case 77
0x1800066d7  movzx   edx, ax
0x1800066da  lea     rcx, [rbp+var_48]
0x1800066de  call    GetScreenRectForDpi
0x1800066e3  mov     eax, [rbp+var_44]
0x1800066e6  jmp     loc_180006514
0x1800066eb  call    GetCurrentThreadCompositedDpi; jumptable 0000000180006640 case 78
0x1800066f0  movzx   edx, ax
0x1800066f3  lea     rcx, [rbp+KeyValueInformation]
0x1800066f7  call    GetScreenRectForDpi
0x1800066fc  mov     eax, [rbp+var_30]
0x1800066ff  sub     eax, [rbp+KeyValueInformation]
0x180006702  jmp     loc_180006514
0x180006707  call    GetCurrentThreadCompositedDpi; jumptable 0000000180006640 case 79
0x18000670c  movzx   edx, ax
0x18000670f  lea     rcx, [rbp+KeyValueInformation]
0x180006713  call    GetScreenRectForDpi
0x180006718  mov     eax, [rbp+var_2C]
0x18000671b  sub     eax, [rbp+var_34]
0x18000671e  jmp     loc_180006514
0x180006723  call    GetCurrentThreadCompositedDpi; jumptable 0000000180006640 case 76
0x180006728  movzx   edx, ax
0x18000672b  lea     rcx, [rbp+var_48]
0x18000672f  call    GetScreenRectForDpi
0x180006734  mov     eax, [rbp+var_48]
0x180006737  jmp     loc_180006514
0x18000673c  cmp     ebx, 3
0x18000673f  jnz     loc_18000681B
0x180006745  lea     eax, [rsi+1]
0x180006748  jmp     loc_18000650C
0x18000674d  call    GetMaxTrackSize; jumptable 0000000180006640 cases 59,60
0x180006752  mov     rcx, rax
0x180006755  shr     rax, 20h
0x180006759  cmp     ebx, 3Bh ; ';'
0x18000675c  cmovz   rax, rcx
0x180006760  jmp     loc_180006514
0x180006765  call    ?GetPrimaryMonitor@@YAPEAUtagMONITOR@@XZ; jumptable 0000000180006640 case 0
0x18000676a  mov     rdx, rax
0x18000676d  lea     rcx, [rbp+KeyValueInformation]
0x180006771  call    GetMonitorRect
0x180006776  mov     eax, [rbp+var_30]
0x180006779  sub     eax, [rbp+KeyValueInformation]
0x18000677c  jmp     loc_180006514
0x180006781  call    ?GetPrimaryMonitor@@YAPEAUtagMONITOR@@XZ; jumptable 0000000180006640 case 1
0x180006786  mov     rdx, rax
0x180006789  lea     rcx, [rbp+KeyValueInformation]
0x18000678d  call    GetMonitorRect
0x180006792  mov     eax, [rbp+var_2C]
0x180006795  sub     eax, [rbp+var_34]
0x180006798  jmp     loc_180006514
0x18000679d  call    ?GetPrimaryMonitor@@YAPEAUtagMONITOR@@XZ; jumptable 0000000180006640 case 61
0x1800067a2  mov     rdx, rax
0x1800067a5  lea     rcx, [rbp+KeyValueInformation]
0x1800067a9  call    GetMonitorWorkRect
0x1800067ae  mov     edi, [rbp+var_30]
0x1800067b1  call    ?GetPrimaryMonitor@@YAPEAUtagMONITOR@@XZ; GetPrimaryMonitor(void)
0x1800067b6  mov     rdx, rax
0x1800067b9  lea     rcx, [rbp+var_48]
0x1800067bd  call    GetMonitorWorkRect
0x1800067c2  mov     ebx, [rbp+var_48]
0x1800067c5  call    GetDpiForSystem
0x1800067ca  mov     ecx, eax
0x1800067cc  call    GetResizableBorderWidthForDpi
0x1800067d1  add     eax, eax
0x1800067d3  sub     eax, ebx
0x1800067d5  add     eax, edi
0x1800067d7  jmp     loc_180006514
0x1800067dc  call    ?GetPrimaryMonitor@@YAPEAUtagMONITOR@@XZ; jumptable 0000000180006640 case 62
0x1800067e1  mov     rdx, rax
0x1800067e4  lea     rcx, [rbp+var_48]
0x1800067e8  call    GetMonitorWorkRect
0x1800067ed  mov     edi, [rbp+var_3C]
0x1800067f0  call    ?GetPrimaryMonitor@@YAPEAUtagMONITOR@@XZ; GetPrimaryMonitor(void)
0x1800067f5  mov     rdx, rax
0x1800067f8  lea     rcx, [rbp+KeyValueInformation]
0x1800067fc  call    GetMonitorWorkRect
0x180006801  mov     ebx, [rbp+var_34]
0x180006804  call    GetDpiForSystem
0x180006809  mov     ecx, eax
0x18000680b  call    GetResizableBorderHeightForDpi
0x180006810  add     eax, eax
0x180006812  sub     eax, ebx
0x180006814  add     eax, edi
0x180006816  jmp     loc_180006514
0x18000681b  cmp     ebx, 2
0x18000681e  jz      loc_180006745
0x180006824  cmp     ebx, 4
0x180006827  jz      loc_180006745
0x18000682d  cmp     ebx, 0Fh
0x180006830  lea     eax, [rsi-1]
0x180006833  cmovz   esi, eax
0x180006836  jmp     loc_180006620
0x18000683b  lea     eax, [rbx-7]
0x18000683e  cmp     eax, 1
0x180006841  ja      loc_1800064FE
0x180006847  mov     rax, cs:gpsi
0x18000684e  mov     eax, [rax+rbx*4+768h]
0x180006855  dec     eax
0x180006857  jmp     loc_18000650C
0x18000685c  mov     rax, cs:gpsi; jumptable 0000000180006640 case 42
0x180006863  mov     eax, [rax]
0x180006865  shr     eax, 1
0x180006867  and     eax, 1
0x18000686a  jmp     loc_180006514
0x18000686f  cmp     ebx, 5Fh ; '_'
0x180006872  jnz     short loc_1800068A7
0x180006874  shr     edx, 8
0x180006877  movzx   eax, dx
0x18000687a  jmp     loc_18000651C
0x18000687f  mov     rax, cs:gpsi; jumptable 0000000180006640 case 82
0x180006886  mov     eax, [rax]
0x180006888  shr     eax, 2
0x18000688b  and     eax, 1
0x18000688e  jmp     loc_180006514
0x180006893  mov     rax, cs:gpsi; jumptable 0000000180006640 case 74
0x18000689a  mov     eax, [rax]
0x18000689c  shr     eax, 3
0x18000689f  and     eax, 1
0x1800068a2  jmp     loc_180006514
0x1800068a7  test    dl, 0Dh
0x1800068aa  mov     r14d, 1
0x1800068b0  setnz   cl
0x1800068b3  test    dl, 80h
0x1800068b6  setnz   al
0x1800068b9  test    al, cl
0x1800068bb  cmovnz  r12d, r14d
0x1800068bf  mov     eax, r12d
0x1800068c2  jmp     loc_18000651C
0x1800068c7  mov     eax, 1
0x1800068cc  jmp     loc_18000651C
0x1800068d1  mov     r14d, 1
0x1800068d7  mov     eax, r14d
0x1800068da  jmp     loc_18000651C
0x1800068df  call    ?GetPrimaryMonitor@@YAPEAUtagMONITOR@@XZ; jumptable 0000000180006640 case 16
0x1800068e4  mov     rdx, rax
0x1800068e7  lea     rcx, [rbp+KeyValueInformation]
0x1800068eb  call    GetMonitorWorkRect
0x1800068f0  mov     eax, [rbp+var_30]
0x1800068f3  sub     eax, [rbp+KeyValueInformation]
0x1800068f6  jmp     loc_180006514
0x1800068fb  call    ?GetPrimaryMonitor@@YAPEAUtagMONITOR@@XZ; jumptable 0000000180006640 case 17
0x180006900  mov     rdx, rax
0x180006903  lea     rcx, [rbp+KeyValueInformation]
0x180006907  call    GetMonitorWorkRect
0x18000690c  mov     ebx, [rbp+var_2C]
0x18000690f  call    GetDpiForSystem
0x180006914  mov     edx, eax
0x180006916  mov     ecx, 2
0x18000691b  call    GetDpiDependentMetric
0x180006920  xor     r12d, r12d
0x180006923  mov     ecx, 400h
0x180006928  cmp     di, cx
0x18000692b  setb    r12b
0x18000692f  sub     ebx, r12d
0x180006932  sub     ebx, [rbp+var_34]
0x180006935  sub     ebx, eax
0x180006937  mov     eax, ebx
  ... truncated ...
```
