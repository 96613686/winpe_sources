# RemovePhantomTSUSBDevnodes(ulong,ulong,void *)

- ea: `0x18002dc5c`
- end: `0x18002e30c`
- name: `?RemovePhantomTSUSBDevnodes@@YAJKKPEAX@Z`
- size: `1712`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, void *)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, installer_update`

## callers

- `0x18000f650`
- `0x180030f00`

## callees

- `0x180009fa8`
- `0x18000a01c`
- `0x18000b8f8`
- `0x18000b98c`
- `0x18000f75c`
- `0x18000f79c`
- `0x180017cbc`
- `0x180017dc8`
- `0x18002dc5c`
- `0x18002e314`
- `0x18002e378`
- `0x180047ebe`
- `0x180047ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002deb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002df7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e09b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002deb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002df7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e09b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002df52`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002df52`
- `KERNEL32!GetTickCount64` at `0x18002dcb9`
- `KERNEL32!GetTickCount64` at `0x18002e2a3`
- `KERNEL32!GetTickCount64` at `0x18002dcb9`
- `KERNEL32!GetTickCount64` at `0x18002e2a3`
- `SHLWAPI!StrStrIW` at `0x18002e142`
- `SHLWAPI!StrStrIW` at `0x18002e142`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_Status` at `0x18002e05f`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_Status` at `0x18002e05f`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiGetDeviceInstanceIdW` at `0x18002e091`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiGetDeviceInstanceIdW` at `0x18002e091`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiDestroyDeviceInfoList` at `0x18002e293`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiDestroyDeviceInfoList` at `0x18002e293`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiGetClassDevsW` at `0x18002dea4`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiGetClassDevsW` at `0x18002dea4`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiEnumDeviceInfo` at `0x18002df6c`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiEnumDeviceInfo` at `0x18002df6c`
- `ext-ms-win-newdev-config-l1-1-0!DiUninstallDevice` at `0x18002e1b4`
- `ext-ms-win-newdev-config-l1-1-0!DiUninstallDevice` at `0x18002e1b4`

## string_xrefs

- `0x18002dd7a`: `RemovePhantomTSUSBDevnodes:: StringCchCopy failed`
- `0x18002de45`: `RemovePhantomTSUSBDevnodes:: StringCchPrintf failed`
- `0x18002def5`: `RemovePhantomTSUSBDevnodes:: SetupDiGetClassDevs failed`
- `0x18002dfcc`: `RemovePhantomTSUSBDevnodes:: SetupDiEnumDeviceInfo failed`

## pseudocode

```c
__int64 __fastcall RemovePhantomTSUSBDevnodes(unsigned int a1, int a2, void *a3)
{
  DWORD v3; // r15d
  ULONGLONG v6; // r12
  unsigned int CurrentThreadActivityIdPrefix; // eax
  signed int v8; // ebx
  unsigned int v9; // eax
  int v10; // edx
  const char *v11; // rcx
  unsigned int v12; // eax
  unsigned int v13; // eax
  HDEVINFO ClassDevsW; // r12
  signed int LastError; // eax
  unsigned int v16; // eax
  signed int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  CONFIGRET DevNode_Status; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  int v24; // edx
  int v25; // r8d
  unsigned int v26; // eax
  WINBOOL v27; // ebx
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // eax
  ULONGLONG v31; // rsi
  unsigned int v32; // eax
  __int64 v33; // rdx
  __int64 v34; // r8
  PDWORD RequiredSize; // [rsp+20h] [rbp-E0h]
  DWORD v37; // [rsp+40h] [rbp-C0h]
  DWORD MemberIndex; // [rsp+44h] [rbp-BCh]
  ULONGLONG TickCount64; // [rsp+50h] [rbp-B0h]
  WINBOOL NeedReboot; // [rsp+58h] [rbp-A8h] BYREF
  ULONG pulProblemNumber; // [rsp+5Ch] [rbp-A4h] BYREF
  ULONG pulStatus; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE hHandle; // [rsp+68h] [rbp-98h]
  struct _SP_DEVINFO_DATA DeviceInfoData; // [rsp+70h] [rbp-90h] BYREF
  WCHAR pszSrch[208]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR DeviceInstanceId[208]; // [rsp+230h] [rbp+130h] BYREF

  hHandle = a3;
  v3 = 0;
  memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
  v37 = 0;
  pulStatus = 0;
  pulProblemNumber = 0;
  TickCount64 = GetTickCount64();
  v6 = TickCount64;
  memset_0(pszSrch, 0, 0x192u);
  if ( !a1 && !a2 )
  {
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 4u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_D(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        10,
        &WPP_6d35608225a031b6e1549a53bee401ae_Traceguids,
        CurrentThreadActivityIdPrefix);
    }
    v8 = StringCchCopyW(pszSrch, 0xC9u, L"tsusb-session");
    if ( v8 < 0 )
    {
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v9 = RdpWppGetCurrentThreadActivityIdPrefix();
        v10 = 11;
        v11 = "RemovePhantomTSUSBDevnodes:: StringCchCopy failed";
LABEL_12:
        WPP_SF_DsD(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          v10,
          (unsigned int)&WPP_6d35608225a031b6e1549a53bee401ae_Traceguids,
          v9,
          (__int64)v11,
          v8);
        goto LABEL_87;
      }
      goto LABEL_87;
    }
LABEL_22:
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 4u )
    {
      v13 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DS(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        14,
        (unsigned int)&WPP_6d35608225a031b6e1549a53bee401ae_Traceguids,
        v13,
        (__int64)pszSrch);
    }
    ClassDevsW = SetupDiGetClassDevsW(0, L"USB", 0, 4u);
    if ( ClassDevsW != (HDEVINFO)-1LL )
      goto LABEL_34;
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( v8 < 0 )
    {
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v16 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          15,
          (unsigned int)&WPP_6d35608225a031b6e1549a53bee401ae_Traceguids,
          v16,
          (__int64)"RemovePhantomTSUSBDevnodes:: SetupDiGetClassDevs failed",
          v8);
      }
    }
    else
    {
LABEL_34:
      MemberIndex = 0;
      DeviceInfoData.cbSize = 32;
      do
      {
        while ( 1 )
        {
          while ( 1 )
          {
            if ( v3 == 259 )
              goto LABEL_82;
            if ( hHandle && !WaitForSingleObject(hHandle, 0) )
            {
              if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
                && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
              {
                v30 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_D(
                  *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
                  16,
                  &WPP_6d35608225a031b6e1549a53bee401ae_Traceguids,
                  v30);
              }
LABEL_82:
              v8 = 0;
              goto LABEL_83;
            }
            if ( !SetupDiEnumDeviceInfo(ClassDevsW, MemberIndex++, &DeviceInfoData) )
              break;
            DevNode_Status = CM_Get_DevNode_Status(&pulStatus, &pulProblemNumber, DeviceInfoData.DevInst, 0);
            if ( DevNode_Status == 13 || DevNode_Status == 37 )
            {
              if ( SetupDiGetDeviceInstanceIdW(ClassDevsW, &DeviceInfoData, DeviceInstanceId, 0xC9u, 0) )
              {
                if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
                  && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 5u )
                {
                  v23 = RdpWppGetCurrentThreadActivityIdPrefix();
                  WPP_SF_DSDD(
                    *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
                    v24,
                    v25,
                    v23,
                    (__int64)DeviceInstanceId,
                    a1,
                    a2);
                }
                if ( StrStrIW(DeviceInstanceId, pszSrch) )
                {
                  if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
                    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 4u )
                  {
                    v26 = RdpWppGetCurrentThreadActivityIdPrefix();
                    WPP_SF_DS(
                      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
                      21,
                      (unsigned int)&WPP_6d35608225a031b6e1549a53bee401ae_Traceguids,
                      v26,
                      (__int64)DeviceInstanceId);
                  }
                  NeedReboot = 0;
                  if ( DiUninstallDevice(0, ClassDevsW, &DeviceInfoData, 0, &NeedReboot) )
                  {
                    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
                      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 4u )
                    {
                      v27 = NeedReboot;
                      v28 = RdpWppGetCurrentThreadActivityIdPrefix();
                      WPP_SF_Dd(
                        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
                        22,
                        &WPP_6d35608225a031b6e1549a53bee401ae_Traceguids,
                        v28,
                        v27);
                    }
                    ++v37;
                  }
                  else if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                         && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
                         && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
                  {
                    v29 = RdpWppGetCurrentThreadActivityIdPrefix();
                    WPP_SF_D(
                      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
                      23,
                      &WPP_6d35608225a031b6e1549a53bee401ae_Traceguids,
                      v29);
                  }
                }
              }
              else
              {
                v3 = GetLastError();
                if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
                  && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
                {
                  v22 = RdpWppGetCurrentThreadActivityIdPrefix();
                  WPP_SF_Dd(
                    *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
                    19,
                    &WPP_6d35608225a031b6e1549a53bee401ae_Traceguids,
                    v22,
                    v3);
                }
              }
            }
          }
          v18 = GetLastError();
          v3 = v18;
          if ( v18 != 259 )
            break;
          if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
            && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 4u )
          {
            v20 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_DDd(
              *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
              18,
              &WPP_6d35608225a031b6e1549a53bee401ae_Traceguids,
              v20,
              a1,
              a2);
          }
        }
        if ( v18 > 0 )
          v8 = (unsigned __int16)v18 | 0x80070000;
        else
          v8 = v18;
      }
      while ( v8 >= 0 );
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v19 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          17,
          (unsigned int)&WPP_6d35608225a031b6e1549a53bee401ae_Traceguids,
          v19,
          (__int64)"RemovePhantomTSUSBDevnodes:: SetupDiEnumDeviceInfo failed",
          v8);
      }
LABEL_83:
      if ( ClassDevsW != (HDEVINFO)-1LL )
        SetupDiDestroyDeviceInfoList(ClassDevsW);
      v3 = v37;
    }
    v6 = TickCount64;
    goto LABEL_87;
  }
  if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 4u )
  {
    v12 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DDd(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      12,
      &WPP_6d35608225a031b6e1549a53bee401ae_Traceguids,
      v12,
      a1,
      a2);
  }
  LODWORD(RequiredSize) = a2;
  v8 = StringCchPrintfW(pszSrch, 0xC9u, L"tsusb-session%u-%u&", a1, RequiredSize);
  if ( v8 >= 0 )
    goto LABEL_22;
  if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    v9 = RdpWppGetCurrentThreadActivityIdPrefix();
    v10 = 13;
    v11 = "RemovePhantomTSUSBDevnodes:: StringCchPrintf failed";
    goto LABEL_12;
  }
LABEL_87:
  v31 = GetTickCount64();
  if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 4u )
  {
    v32 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DID(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL), v33, v34, v32, v31 - v6, v3);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002dc5c  push    rbp
0x18002dc5e  push    rbx
0x18002dc5f  push    rsi
0x18002dc60  push    rdi
0x18002dc61  push    r12
0x18002dc63  push    r13
0x18002dc65  push    r15
0x18002dc67  lea     rbp, [rsp-2E0h]
0x18002dc6f  sub     rsp, 3E0h
0x18002dc76  mov     rax, cs:__security_cookie
0x18002dc7d  xor     rax, rsp
0x18002dc80  mov     [rbp+310h+var_40], rax
0x18002dc87  xorps   xmm0, xmm0
0x18002dc8a  mov     [rsp+410h+hHandle], r8
0x18002dc8f  xor     r15d, r15d
0x18002dc92  mov     [rsp+410h+var_3C8], ecx
0x18002dc96  movups  xmmword ptr [rsp+410h+DeviceInfoData.cbSize], xmm0
0x18002dc9b  mov     [rsp+410h+var_3D0], r15d
0x18002dca0  mov     r13d, edx
0x18002dca3  movups  xmmword ptr [rbp+310h+DeviceInfoData.ClassGuid.Data4+4], xmm0
0x18002dca7  mov     ebx, ecx
0x18002dca9  mov     [rsp+410h+pulStatus], 0
0x18002dcb1  mov     [rsp+410h+pulProblemNumber], 0
0x18002dcb9  call    cs:__imp_GetTickCount64
0x18002dcbf  xor     edx, edx; Val
0x18002dcc1  lea     rcx, [rbp+310h+pszSrch]; void *
0x18002dcc5  mov     r8d, 192h; Size
0x18002dccb  mov     [rsp+410h+var_3C0], rax
0x18002dcd0  mov     r12, rax
0x18002dcd3  call    memset_0
0x18002dcd8  test    ebx, ebx
0x18002dcda  jnz     loc_18002DDA5
0x18002dce0  test    r13d, r13d
0x18002dce3  jnz     loc_18002DDA5
0x18002dce9  mov     rax, cs:WPP_GLOBAL_Control
0x18002dcf0  lea     rdi, WPP_GLOBAL_Control
0x18002dcf7  lea     rsi, WPP_6d35608225a031b6e1549a53bee401ae_Traceguids
0x18002dcfe  cmp     rax, rdi
0x18002dd01  jz      short loc_18002DD2D
0x18002dd03  test    byte ptr [rax+1Ch], 1
0x18002dd07  jz      short loc_18002DD2D
0x18002dd09  cmp     byte ptr [rax+19h], 4
0x18002dd0d  jb      short loc_18002DD2D
0x18002dd0f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002dd14  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dd1b  lea     edx, [rbx+0Ah]
0x18002dd1e  mov     r9d, eax
0x18002dd21  mov     r8, rsi
0x18002dd24  mov     rcx, [rcx+10h]
0x18002dd28  call    WPP_SF_D
0x18002dd2d  lea     r8, aTsusbSession; "tsusb-session"
0x18002dd34  mov     edx, 0C9h; unsigned __int64
0x18002dd39  lea     rcx, [rbp+310h+pszSrch]; unsigned __int16 *
0x18002dd3d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002dd42  mov     ebx, eax
0x18002dd44  test    eax, eax
0x18002dd46  jns     loc_18002DE51
0x18002dd4c  mov     rax, cs:WPP_GLOBAL_Control
0x18002dd53  cmp     rax, rdi
0x18002dd56  jz      loc_18002E2A3
0x18002dd5c  test    byte ptr [rax+1Ch], 8
0x18002dd60  jz      loc_18002E2A3
0x18002dd66  cmp     byte ptr [rax+19h], 2
0x18002dd6a  jb      loc_18002E2A3
0x18002dd70  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002dd75  mov     edx, 0Bh
0x18002dd7a  lea     rcx, aRemovephantomt; "RemovePhantomTSUSBDevnodes:: StringCchC"...
0x18002dd81  mov     [rsp+410h+var_3E8], ebx
0x18002dd85  mov     r9d, eax
0x18002dd88  mov     [rsp+410h+RequiredSize], rcx
0x18002dd8d  mov     r8, rsi
0x18002dd90  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dd97  mov     rcx, [rcx+10h]
0x18002dd9b  call    WPP_SF_DsD
0x18002dda0  jmp     loc_18002E2A3
0x18002dda5  mov     rax, cs:WPP_GLOBAL_Control
0x18002ddac  lea     rdi, WPP_GLOBAL_Control
0x18002ddb3  lea     rsi, WPP_6d35608225a031b6e1549a53bee401ae_Traceguids
0x18002ddba  cmp     rax, rdi
0x18002ddbd  jz      short loc_18002DDF4
0x18002ddbf  test    byte ptr [rax+1Ch], 1
0x18002ddc3  jz      short loc_18002DDF4
0x18002ddc5  cmp     byte ptr [rax+19h], 4
0x18002ddc9  jb      short loc_18002DDF4
0x18002ddcb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002ddd0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ddd7  mov     edx, 0Ch
0x18002dddc  mov     [rsp+410h+var_3E8], r13d
0x18002dde1  mov     r9d, eax
0x18002dde4  mov     r8, rsi
0x18002dde7  mov     dword ptr [rsp+410h+RequiredSize], ebx
0x18002ddeb  mov     rcx, [rcx+10h]
0x18002ddef  call    WPP_SF_DDd
0x18002ddf4  mov     r9d, ebx
0x18002ddf7  mov     dword ptr [rsp+410h+RequiredSize], r13d
0x18002ddfc  lea     r8, aTsusbSessionUU; "tsusb-session%u-%u&"
0x18002de03  mov     edx, 0C9h; unsigned __int64
0x18002de08  lea     rcx, [rbp+310h+pszSrch]; unsigned __int16 *
0x18002de0c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002de11  mov     ebx, eax
0x18002de13  test    eax, eax
0x18002de15  jns     short loc_18002DE51
0x18002de17  mov     rax, cs:WPP_GLOBAL_Control
0x18002de1e  cmp     rax, rdi
0x18002de21  jz      loc_18002E2A3
0x18002de27  test    byte ptr [rax+1Ch], 8
0x18002de2b  jz      loc_18002E2A3
0x18002de31  cmp     byte ptr [rax+19h], 2
0x18002de35  jb      loc_18002E2A3
0x18002de3b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002de40  mov     edx, 0Dh
0x18002de45  lea     rcx, aRemovephantomt_2; "RemovePhantomTSUSBDevnodes:: StringCchP"...
0x18002de4c  jmp     loc_18002DD81
0x18002de51  mov     rax, cs:WPP_GLOBAL_Control
0x18002de58  cmp     rax, rdi
0x18002de5b  jz      short loc_18002DE92
0x18002de5d  test    byte ptr [rax+1Ch], 1
0x18002de61  jz      short loc_18002DE92
0x18002de63  cmp     byte ptr [rax+19h], 4
0x18002de67  jb      short loc_18002DE92
0x18002de69  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002de6e  lea     rcx, [rbp+310h+pszSrch]
0x18002de72  mov     edx, 0Eh
0x18002de77  mov     [rsp+410h+RequiredSize], rcx
0x18002de7c  mov     r9d, eax
0x18002de7f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002de86  mov     r8, rsi
0x18002de89  mov     rcx, [rcx+10h]
0x18002de8d  call    WPP_SF_DS
0x18002de92  mov     r9d, 4; Flags
0x18002de98  lea     rdx, Enumerator; "USB"
0x18002de9f  xor     r8d, r8d; hwndParent
0x18002dea2  xor     ecx, ecx; ClassGuid
0x18002dea4  call    cs:__imp_SetupDiGetClassDevsW
0x18002deaa  mov     r12, rax
0x18002dead  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002deb1  jnz     short loc_18002DF25
0x18002deb3  call    cs:__imp_GetLastError
0x18002deb9  mov     ebx, eax
0x18002debb  test    eax, eax
0x18002debd  jle     short loc_18002DEC8
0x18002debf  movzx   ebx, ax
0x18002dec2  or      ebx, 80070000h
0x18002dec8  test    ebx, ebx
0x18002deca  jns     short loc_18002DF25
0x18002decc  mov     rax, cs:WPP_GLOBAL_Control
0x18002ded3  cmp     rax, rdi
0x18002ded6  jz      loc_18002E29E
0x18002dedc  test    byte ptr [rax+1Ch], 8
0x18002dee0  jz      loc_18002E29E
0x18002dee6  cmp     byte ptr [rax+19h], 2
0x18002deea  jb      loc_18002E29E
0x18002def0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002def5  lea     rcx, aRemovephantomt_0; "RemovePhantomTSUSBDevnodes:: SetupDiGet"...
0x18002defc  mov     [rsp+410h+var_3E8], ebx
0x18002df00  mov     [rsp+410h+RequiredSize], rcx
0x18002df05  mov     edx, 0Fh
0x18002df0a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002df11  mov     r9d, eax
0x18002df14  mov     r8, rsi
0x18002df17  mov     rcx, [rcx+10h]
0x18002df1b  call    WPP_SF_DsD
0x18002df20  jmp     loc_18002E29E
0x18002df25  mov     [rsp+410h+MemberIndex], r15d
0x18002df2a  mov     [rsp+410h+DeviceInfoData.cbSize], 20h ; ' '
0x18002df32  mov     ebx, [rsp+410h+var_3C8]
0x18002df36  cmp     r15d, 103h
0x18002df3d  jz      loc_18002E288
0x18002df43  mov     rax, [rsp+410h+hHandle]
0x18002df48  test    rax, rax
0x18002df4b  jz      short loc_18002DF60
0x18002df4d  xor     edx, edx; dwMilliseconds
0x18002df4f  mov     rcx, rax; hHandle
0x18002df52  call    cs:__imp_WaitForSingleObject
0x18002df58  test    eax, eax
0x18002df5a  jz      loc_18002E250
0x18002df60  mov     edx, [rsp+410h+MemberIndex]; MemberIndex
0x18002df64  lea     r8, [rsp+410h+DeviceInfoData]; DeviceInfoData
0x18002df69  mov     rcx, r12; DeviceInfoSet
0x18002df6c  call    cs:__imp_SetupDiEnumDeviceInfo
0x18002df72  inc     [rsp+410h+MemberIndex]
0x18002df76  test    eax, eax
0x18002df78  jnz     loc_18002E04E
0x18002df7e  call    cs:__imp_GetLastError
0x18002df84  mov     r15d, eax
0x18002df87  cmp     eax, 103h
0x18002df8c  jz      short loc_18002DFFC
0x18002df8e  test    eax, eax
0x18002df90  jg      short loc_18002DF96
0x18002df92  mov     ebx, eax
0x18002df94  jmp     short loc_18002DF9F
0x18002df96  movzx   ebx, ax
0x18002df99  or      ebx, 80070000h
0x18002df9f  test    ebx, ebx
0x18002dfa1  jns     short loc_18002DF32
0x18002dfa3  mov     rax, cs:WPP_GLOBAL_Control
0x18002dfaa  cmp     rax, rdi
0x18002dfad  jz      loc_18002E28A
0x18002dfb3  test    byte ptr [rax+1Ch], 8
0x18002dfb7  jz      loc_18002E28A
0x18002dfbd  cmp     byte ptr [rax+19h], 2
0x18002dfc1  jb      loc_18002E28A
0x18002dfc7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002dfcc  lea     rcx, aRemovephantomt_1; "RemovePhantomTSUSBDevnodes:: SetupDiEnu"...
0x18002dfd3  mov     [rsp+410h+var_3E8], ebx
0x18002dfd7  mov     [rsp+410h+RequiredSize], rcx
0x18002dfdc  mov     edx, 11h
0x18002dfe1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dfe8  mov     r9d, eax
0x18002dfeb  mov     r8, rsi
0x18002dfee  mov     rcx, [rcx+10h]
0x18002dff2  call    WPP_SF_DsD
0x18002dff7  jmp     loc_18002E28A
0x18002dffc  mov     rax, cs:WPP_GLOBAL_Control
0x18002e003  cmp     rax, rdi
0x18002e006  jz      loc_18002DF36
0x18002e00c  test    byte ptr [rax+1Ch], 1
0x18002e010  jz      loc_18002DF36
0x18002e016  cmp     byte ptr [rax+19h], 4
0x18002e01a  jb      loc_18002DF36
0x18002e020  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002e025  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e02c  mov     edx, 12h
0x18002e031  mov     [rsp+410h+var_3E8], r13d
0x18002e036  mov     r9d, eax
0x18002e039  mov     r8, rsi
0x18002e03c  mov     dword ptr [rsp+410h+RequiredSize], ebx
0x18002e040  mov     rcx, [rcx+10h]
0x18002e044  call    WPP_SF_DDd
0x18002e049  jmp     loc_18002DF36
0x18002e04e  mov     r8d, [rbp+310h+DeviceInfoData.DevInst]; dnDevInst
0x18002e052  lea     rdx, [rsp+410h+pulProblemNumber]; pulProblemNumber
0x18002e057  xor     r9d, r9d; ulFlags
0x18002e05a  lea     rcx, [rsp+410h+pulStatus]; pulStatus
0x18002e05f  call    cs:__imp_CM_Get_DevNode_Status
0x18002e065  cmp     eax, 0Dh
0x18002e068  jz      short loc_18002E073
0x18002e06a  cmp     eax, 25h ; '%'
0x18002e06d  jnz     loc_18002DF36
0x18002e073  mov     r9d, 0C9h; DeviceInstanceIdSize
0x18002e079  mov     [rsp+410h+RequiredSize], 0; RequiredSize
0x18002e082  lea     r8, [rbp+310h+DeviceInstanceId]; DeviceInstanceId
0x18002e089  mov     rcx, r12; DeviceInfoSet
0x18002e08c  lea     rdx, [rsp+410h+DeviceInfoData]; DeviceInfoData
0x18002e091  call    cs:__imp_SetupDiGetDeviceInstanceIdW
0x18002e097  test    eax, eax
0x18002e099  jnz     short loc_18002E0F2
0x18002e09b  call    cs:__imp_GetLastError
0x18002e0a1  mov     r15d, eax
0x18002e0a4  mov     rax, cs:WPP_GLOBAL_Control
0x18002e0ab  cmp     rax, rdi
0x18002e0ae  jz      loc_18002DF36
0x18002e0b4  test    byte ptr [rax+1Ch], 1
0x18002e0b8  jz      loc_18002DF36
0x18002e0be  cmp     byte ptr [rax+19h], 2
0x18002e0c2  jb      loc_18002DF36
0x18002e0c8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002e0cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e0d4  mov     edx, 13h
0x18002e0d9  mov     r9d, eax
0x18002e0dc  mov     dword ptr [rsp+410h+RequiredSize], r15d
0x18002e0e1  mov     r8, rsi
0x18002e0e4  mov     rcx, [rcx+10h]
0x18002e0e8  call    WPP_SF_Dd
0x18002e0ed  jmp     loc_18002DF36
0x18002e0f2  mov     rax, cs:WPP_GLOBAL_Control
0x18002e0f9  cmp     rax, rdi
0x18002e0fc  jz      short loc_18002E137
0x18002e0fe  test    byte ptr [rax+1Ch], 1
0x18002e102  jz      short loc_18002E137
0x18002e104  cmp     byte ptr [rax+19h], 5
0x18002e108  jb      short loc_18002E137
0x18002e10a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002e10f  lea     rcx, [rbp+310h+DeviceInstanceId]
0x18002e116  mov     [rsp+410h+var_3E0], r13d
0x18002e11b  mov     [rsp+410h+var_3E8], ebx
0x18002e11f  mov     r9d, eax
0x18002e122  mov     [rsp+410h+RequiredSize], rcx
0x18002e127  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e12e  mov     rcx, [rcx+10h]
0x18002e132  call    WPP_SF_DSDD
0x18002e137  lea     rdx, [rbp+310h+pszSrch]; pszSrch
0x18002e13b  lea     rcx, [rbp+310h+DeviceInstanceId]; pszFirst
0x18002e142  call    cs:__imp_StrStrIW
0x18002e148  test    rax, rax
0x18002e14b  jz      loc_18002DF36
0x18002e151  mov     rax, cs:WPP_GLOBAL_Control
0x18002e158  cmp     rax, rdi
0x18002e15b  jz      short loc_18002E195
0x18002e15d  test    byte ptr [rax+1Ch], 1
0x18002e161  jz      short loc_18002E195
0x18002e163  cmp     byte ptr [rax+19h], 4
0x18002e167  jb      short loc_18002E195
0x18002e169  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002e16e  lea     rcx, [rbp+310h+DeviceInstanceId]
0x18002e175  mov     edx, 15h
0x18002e17a  mov     [rsp+410h+RequiredSize], rcx
0x18002e17f  mov     r9d, eax
0x18002e182  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e189  mov     r8, rsi
  ... truncated ...
```
