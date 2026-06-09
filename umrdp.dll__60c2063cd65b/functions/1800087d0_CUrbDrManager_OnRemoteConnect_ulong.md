# CUrbDrManager::OnRemoteConnect(ulong)

- ea: `0x1800087d0`
- end: `0x180008aba`
- name: `?OnRemoteConnect@CUrbDrManager@@AEAAJK@Z`
- size: `746`
- prototype: `__int64 __fastcall(CUrbDrManager *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180002170`

## callees

- `0x1800087d0`
- `0x18000b8f8`
- `0x18000bd44`
- `0x18000f79c`
- `0x180019d90`
- `0x18002ed04`
- `0x1800303c4`
- `0x180030b3c`
- `0x180031200`
- `0x1800334cc`
- `0x180047ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a3f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000888e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000888e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000891f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000897c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000891f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000897c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008a85`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008a85`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x180008845`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x180008845`
- `WTSAPI32!WTSFreeMemory` at `0x180008864`
- `WTSAPI32!WTSFreeMemory` at `0x180008864`

## string_xrefs

- `0x180008880`: `Software\Policies\Microsoft\Windows NT\Terminal Services`

## pseudocode

```c
__int64 __fastcall CUrbDrManager::OnRemoteConnect(CUrbDrManager *this, unsigned int a2)
{
  void **v2; // rdi
  unsigned int v5; // ebx
  int v6; // r12d
  unsigned __int8 v7; // r13
  LSTATUS v8; // r15d
  unsigned int CurrentThreadActivityIdPrefix; // eax
  CUrbDrManager *v10; // rcx
  __int64 v11; // r8
  HKEY v12; // rcx
  unsigned int v13; // ecx
  signed int LastError; // eax
  DWORD cbData; // [rsp+38h] [rbp-29h] BYREF
  DWORD Type; // [rsp+3Ch] [rbp-25h] BYREF
  BYTE Data[8]; // [rsp+40h] [rbp-21h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-19h] BYREF
  DWORD pBytesReturned; // [rsp+50h] [rbp-11h] BYREF
  LPWSTR ppBuffer; // [rsp+58h] [rbp-9h] BYREF
  __int128 v22; // [rsp+60h] [rbp-1h] BYREF
  struct CSimpleHash *v23; // [rsp+70h] [rbp+Fh] BYREF

  v2 = 0;
  v23 = 0;
  pBytesReturned = 0;
  cbData = 0;
  Type = 0;
  *(_DWORD *)Data = 0;
  phkResult = 0;
  ppBuffer = 0;
  v22 = 0;
  if ( WTSQuerySessionInformationW(0, a2, WTSConnectState, &ppBuffer, &pBytesReturned) )
  {
    v5 = 0;
    v6 = *(_DWORD *)ppBuffer;
    v7 = *(_DWORD *)ppBuffer == 0;
    WTSFreeMemory(ppBuffer);
    ppBuffer = 0;
    v8 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services",
           0,
           0x20019u,
           &phkResult);
    if ( v8 )
    {
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          54,
          WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids,
          CurrentThreadActivityIdPrefix,
          v8);
      }
    }
    else
    {
      cbData = 4;
      if ( !RegQueryValueExW(phkResult, L"fDisableUSBRedir", 0, &Type, Data, &cbData)
        && Type == 4
        && cbData == 4
        && *(_DWORD *)Data
        || !(unsigned int)CUrbDrManager::IsPnPRedirectionEnabled(v10, a2) )
      {
        if ( !*((_BYTE *)this + 120) )
        {
          if ( (Microsoft_Windows_TerminalServices_ServerUSBDevicesEnableBits & 8) != 0 )
            McGenEventWrite_EventWriteTransfer(v10, &EVENT_NOTIFY_DEVICE_REDIRECT_POLICY_DISABLED, v11, 1, &v22);
          *((_BYTE *)this + 120) = 1;
        }
      }
      else
      {
        v12 = phkResult;
        *((_BYTE *)this + 120) = 0;
        cbData = 4;
        if ( RegQueryValueExW(v12, L"MaxNumUsbDevices", 0, &Type, Data, &cbData) || Type != 4 || cbData != 4 )
          goto LABEL_17;
        LODWORD(v22) = *(_DWORD *)Data;
        if ( !*(_DWORD *)Data )
          goto LABEL_30;
        if ( *(_DWORD *)Data > 0xFFu )
LABEL_17:
          LODWORD(v22) = 255;
        HIDWORD(v22) = _InterlockedIncrement((volatile signed __int32 *)this + 24);
        if ( (int)CSimpleHash::CreateInstance(v13, &v23) >= 0 )
        {
          if ( (unsigned int)DynArray<_SESSION_DATA,unsigned long>::AddAt((char *)this + 80, a2, &v22) )
          {
            if ( !v6 )
              v5 = CUrbDrManager::OnLogon(this, a2, v7);
          }
          else
          {
            v2 = (void **)v23;
            v5 = -2147024882;
          }
        }
        else
        {
          v2 = (void **)v23;
          v5 = -2147024882;
        }
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_30:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v2 )
  {
    operator delete(v2[1]);
    operator delete(v2);
  }
  return v5;
}

```

## disassembly

```asm
0x1800087d0  mov     r11, rsp
0x1800087d3  push    rbp
0x1800087d4  push    rbx
0x1800087d5  push    rdi
0x1800087d6  lea     rbp, [r11-5Fh]
0x1800087da  sub     rsp, 0A0h
0x1800087e1  mov     rax, cs:__security_cookie
0x1800087e8  xor     rax, rsp
0x1800087eb  mov     [rbp+57h+var_40], rax
0x1800087ef  mov     [r11+18h], rsi
0x1800087f3  lea     rax, [rbp+57h+var_68]
0x1800087f7  mov     [r11-20h], r12
0x1800087fb  lea     r9, [rbp+57h+ppBuffer]; ppBuffer
0x1800087ff  mov     [r11-28h], r13
0x180008803  xorps   xmm0, xmm0
0x180008806  mov     [r11-30h], r14
0x18000880a  xor     edi, edi
0x18000880c  mov     [r11-38h], r15
0x180008810  mov     r14, rcx
0x180008813  xor     r15d, r15d
0x180008816  mov     [rbp+57h+var_48], rdi
0x18000881a  xor     ecx, ecx; hServer
0x18000881c  mov     [rbp+57h+var_68], r15d
0x180008820  mov     r8d, 8; WTSInfoClass
0x180008826  mov     [rbp+57h+cbData], r15d
0x18000882a  mov     [rbp+57h+Type], r15d
0x18000882e  mov     esi, edx
0x180008830  mov     dword ptr [rbp+57h+Data], r15d
0x180008834  mov     [rbp+57h+phkResult], r15
0x180008838  mov     [rbp+57h+ppBuffer], r15
0x18000883c  movups  [rbp+57h+var_58], xmm0
0x180008840  mov     [rsp+0B0h+pBytesReturned], rax; pBytesReturned
0x180008845  call    cs:__imp_WTSQuerySessionInformationW
0x18000884b  test    eax, eax
0x18000884d  jz      loc_180008A3F
0x180008853  mov     rcx, [rbp+57h+ppBuffer]; pMemory
0x180008857  mov     ebx, r15d
0x18000885a  mov     r12d, [rcx]
0x18000885d  test    r12d, r12d
0x180008860  setz    r13b
0x180008864  call    cs:__imp_WTSFreeMemory
0x18000886a  lea     rax, [rbp+57h+phkResult]
0x18000886e  mov     [rbp+57h+ppBuffer], r15
0x180008872  mov     r9d, 20019h; samDesired
0x180008878  mov     [rsp+0B0h+pBytesReturned], rax; phkResult
0x18000887d  xor     r8d, r8d; ulOptions
0x180008880  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows "...
0x180008887  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000888e  call    cs:__imp_RegOpenKeyExW
0x180008894  mov     r15d, eax
0x180008897  test    eax, eax
0x180008899  jz      short loc_1800088F4
0x18000889b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800088a2  lea     rax, WPP_GLOBAL_Control
0x1800088a9  cmp     rcx, rax
0x1800088ac  jz      loc_180008A54
0x1800088b2  test    byte ptr [rcx+1Ch], 1
0x1800088b6  jz      loc_180008A54
0x1800088bc  cmp     byte ptr [rcx+19h], 2
0x1800088c0  jb      loc_180008A54
0x1800088c6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800088cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800088d2  lea     r8, WPP_e96ad774d77a3b20501daafc53de2dbd_Traceguids
0x1800088d9  mov     edx, 36h ; '6'
0x1800088de  mov     dword ptr [rsp+0B0h+pBytesReturned], r15d
0x1800088e3  mov     r9d, eax
0x1800088e6  mov     rcx, [rcx+10h]
0x1800088ea  call    WPP_SF_Dd
0x1800088ef  jmp     loc_180008A54
0x1800088f4  mov     rcx, [rbp+57h+phkResult]; hKey
0x1800088f8  lea     rax, [rbp+57h+cbData]
0x1800088fc  mov     [rsp+28h], rax; lpcbData
0x180008901  lea     r9, [rbp+57h+Type]; lpType
0x180008905  lea     rax, [rbp+57h+Data]
0x180008909  mov     [rbp+57h+cbData], 4
0x180008910  xor     r8d, r8d; lpReserved
0x180008913  mov     [rsp+0B0h+pBytesReturned], rax; lpData
0x180008918  lea     rdx, aFdisableusbred; "fDisableUSBRedir"
0x18000891f  call    cs:__imp_RegQueryValueExW
0x180008925  test    eax, eax
0x180008927  jnz     short loc_18000893E
0x180008929  cmp     [rbp+57h+Type], 4
0x18000892d  jnz     short loc_18000893E
0x18000892f  cmp     [rbp+57h+cbData], 4
0x180008933  jnz     short loc_18000893E
0x180008935  cmp     dword ptr [rbp+57h+Data], ebx
0x180008938  jnz     loc_180008A0E
0x18000893e  mov     edx, esi; unsigned int
0x180008940  call    ?IsPnPRedirectionEnabled@CUrbDrManager@@AEAAHK@Z; CUrbDrManager::IsPnPRedirectionEnabled(ulong)
0x180008945  test    eax, eax
0x180008947  jz      loc_180008A0E
0x18000894d  mov     rcx, [rbp+57h+phkResult]; hKey
0x180008951  lea     rax, [rbp+57h+cbData]
0x180008955  mov     [rsp+28h], rax; lpcbData
0x18000895a  lea     r9, [rbp+57h+Type]; lpType
0x18000895e  lea     rax, [rbp+57h+Data]
0x180008962  mov     [r14+78h], bl
0x180008966  xor     r8d, r8d; lpReserved
0x180008969  mov     [rsp+0B0h+pBytesReturned], rax; lpData
0x18000896e  lea     rdx, aMaxnumusbdevic; "MaxNumUsbDevices"
0x180008975  mov     [rbp+57h+cbData], 4
0x18000897c  call    cs:__imp_RegQueryValueExW
0x180008982  test    eax, eax
0x180008984  jnz     short loc_1800089A7
0x180008986  cmp     [rbp+57h+Type], 4
0x18000898a  jnz     short loc_1800089A7
0x18000898c  cmp     [rbp+57h+cbData], 4
0x180008990  jnz     short loc_1800089A7
0x180008992  mov     eax, dword ptr [rbp+57h+Data]
0x180008995  mov     dword ptr [rbp+57h+var_58], eax
0x180008998  test    eax, eax
0x18000899a  jz      loc_180008A54
0x1800089a0  cmp     eax, 0FFh
0x1800089a5  jbe     short loc_1800089AE
0x1800089a7  mov     dword ptr [rbp+57h+var_58], 0FFh
0x1800089ae  mov     r9d, 1
0x1800089b4  lock xadd [r14+60h], r9d
0x1800089ba  inc     r9d
0x1800089bd  lea     rdx, [rbp+57h+var_48]; struct CSimpleHash **
0x1800089c1  mov     dword ptr [rbp+57h+var_58+0Ch], r9d
0x1800089c5  call    ?CreateInstance@CSimpleHash@@SAJKPEAPEAV1@@Z; CSimpleHash::CreateInstance(ulong,CSimpleHash * *)
0x1800089ca  test    eax, eax
0x1800089cc  jns     short loc_1800089D9
0x1800089ce  mov     rdi, [rbp+57h+var_48]
0x1800089d2  mov     ebx, 8007000Eh
0x1800089d7  jmp     short loc_180008A54
0x1800089d9  lea     rcx, [r14+50h]
0x1800089dd  mov     edx, esi
0x1800089df  lea     r8, [rbp+57h+var_58]
0x1800089e3  call    ?AddAt@?$DynArray@U_SESSION_DATA@@K@@QEAAHKAEAU_SESSION_DATA@@@Z; DynArray<_SESSION_DATA,ulong>::AddAt(ulong,_SESSION_DATA &)
0x1800089e8  test    eax, eax
0x1800089ea  jnz     short loc_1800089F7
0x1800089ec  mov     rdi, [rbp+57h+var_48]
0x1800089f0  mov     ebx, 8007000Eh
0x1800089f5  jmp     short loc_180008A54
0x1800089f7  test    r12d, r12d
0x1800089fa  jnz     short loc_180008A54
0x1800089fc  movzx   r8d, r13b; unsigned __int8
0x180008a00  mov     edx, esi; unsigned int
0x180008a02  mov     rcx, r14; this
0x180008a05  call    ?OnLogon@CUrbDrManager@@AEAAJKE@Z; CUrbDrManager::OnLogon(ulong,uchar)
0x180008a0a  mov     ebx, eax
0x180008a0c  jmp     short loc_180008A54
0x180008a0e  cmp     [r14+78h], bl
0x180008a12  jnz     short loc_180008A54
0x180008a14  test    cs:Microsoft_Windows_TerminalServices_ServerUSBDevicesEnableBits, 8
0x180008a1b  jz      short loc_180008A38
0x180008a1d  lea     rax, [rbp+57h+var_58]
0x180008a21  mov     r9d, 1
0x180008a27  lea     rdx, EVENT_NOTIFY_DEVICE_REDIRECT_POLICY_DISABLED
0x180008a2e  mov     [rsp+0B0h+pBytesReturned], rax
0x180008a33  call    McGenEventWrite_EventWriteTransfer
0x180008a38  mov     byte ptr [r14+78h], 1
0x180008a3d  jmp     short loc_180008A54
0x180008a3f  call    cs:__imp_GetLastError
0x180008a45  mov     ebx, eax
0x180008a47  test    eax, eax
0x180008a49  jle     short loc_180008A54
0x180008a4b  movzx   ebx, ax
0x180008a4e  or      ebx, 80070000h
0x180008a54  mov     rcx, [rbp+57h+phkResult]; hKey
0x180008a58  mov     r15, [rsp+0B0h+var_30]
0x180008a60  mov     r14, [rsp+0B0h+var_28]
0x180008a68  mov     r13, [rsp+0B0h+var_20]
0x180008a70  mov     r12, [rsp+98h]
0x180008a78  mov     rsi, [rsp+0B0h+arg_10]
0x180008a80  test    rcx, rcx
0x180008a83  jz      short loc_180008A8B
0x180008a85  call    cs:__imp_RegCloseKey
0x180008a8b  test    rdi, rdi
0x180008a8e  jz      short loc_180008AA1
0x180008a90  mov     rcx, [rdi+8]; Block
0x180008a94  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180008a99  mov     rcx, rdi; Block
0x180008a9c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008aa1  mov     eax, ebx
0x180008aa3  mov     rcx, [rbp+57h+var_40]
0x180008aa7  xor     rcx, rsp; StackCookie
0x180008aaa  call    __security_check_cookie
0x180008aaf  add     rsp, 0A0h
0x180008ab6  pop     rdi
0x180008ab7  pop     rbx
0x180008ab8  pop     rbp
0x180008ab9  retn
```
