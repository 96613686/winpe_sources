# CWwanResetRecoveryHelper::_TriggerEnableDisable(_GUID const &,int,ulong &)

- ea: `0x180095630`
- end: `0x1800957f9`
- name: `?_TriggerEnableDisable@CWwanResetRecoveryHelper@@SAKAEBU_GUID@@HAEAK@Z`
- size: `457`
- prototype: `unsigned int __fastcall(const struct _GUID *, int, unsigned int *)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x180087fc4`
- `0x18009213c`
- `0x18009639c`

## callees

- `0x1800085d0`
- `0x180012300`
- `0x180014f1c`
- `0x18001aa1c`
- `0x180095554`
- `0x180095630`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095692`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800956e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009574f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009578c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095692`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800956e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009574f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009578c`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1800957cf`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1800957cf`
- `DEVOBJ!DevObjGetClassDevs` at `0x1800956dc`
- `DEVOBJ!DevObjGetClassDevs` at `0x1800956dc`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180095683`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180095683`
- `api-ms-win-devices-config-l1-1-1!CM_Setup_DevNode` at `0x180095729`
- `api-ms-win-devices-config-l1-1-1!CM_Setup_DevNode` at `0x180095729`

## string_xrefs

- `0x180095698`: `DevObjCreateDeviceInfoList Failure 0x%x`
- `0x180095755`: `Couldn't Enable the Device 0x%x ConfigRet 0x%x`
- `0x180095792`: `Couldn't Disable the Device 0x%x ConfigRet 0x%x`

## pseudocode

```c
__int64 __fastcall CWwanResetRecoveryHelper::_TriggerEnableDisable(const struct _GUID *a1, int a2, unsigned int *a3)
{
  __int64 DeviceInfoList; // rax
  void *v7; // r14
  __int64 LastError; // rbx
  unsigned int DeviceInfo; // eax
  CONFIGRET v10; // eax
  unsigned int v11; // esi
  DWORD v12; // eax
  const unsigned __int16 *v13; // r8
  unsigned int v14; // eax
  __int64 v16; // [rsp+20h] [rbp-68h]
  __int128 v17; // [rsp+30h] [rbp-58h] BYREF
  DEVINST dnDevInst[4]; // [rsp+40h] [rbp-48h]
  __int128 v19; // [rsp+50h] [rbp-38h]

  v17 = 0;
  *(_OWORD *)dnDevInst = 0;
  v19 = 0;
  DeviceInfoList = DevObjCreateDeviceInfoList(&GUID_DEVCLASS_NET, 0, 0, 0, 0);
  v7 = (void *)DeviceInfoList;
  if ( DeviceInfoList != -1 )
  {
    if ( !(unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVCLASS_NET, 0, 2, 0, 0) )
    {
      LastError = GetLastError();
      WwanLog::Error(
        "CWwanResetRecoveryHelper::_TriggerEnableDisable",
        0,
        L"DevObjGetClassDevs Failure 0x%x",
        LastError);
LABEL_16:
      DevObjDestroyDeviceInfoList(v7);
      return (unsigned int)LastError;
    }
    LODWORD(v17) = 48;
    DeviceInfo = CWwanDeviceEnumerator::getDeviceInfo(v7, a1, (struct _DO_DEVINFO_DATA *)&v17, 0);
    LODWORD(LastError) = DeviceInfo;
    if ( DeviceInfo )
    {
      WwanLog::Error(
        "CWwanResetRecoveryHelper::_TriggerEnableDisable",
        0,
        L"Device that we were looking for was not found 0x%x",
        DeviceInfo);
      goto LABEL_16;
    }
    if ( a2 )
    {
      v10 = CM_Setup_DevNode(dnDevInst[1], 0);
      v11 = v10;
      if ( !v10 )
      {
        *a3 = 0;
        WwanLog::Info(
          "CWwanResetRecoveryHelper::_TriggerEnableDisable",
          a1,
          L"Successfully triggered PnP Enable on the Interface!");
        goto LABEL_16;
      }
      WwanLog::Error("CWwanResetRecoveryHelper::_TriggerEnableDevice", 0, L"Unable to Enable the Device 0x%x", v10);
      *a3 = v11;
      v12 = GetLastError();
      v13 = L"Couldn't Enable the Device 0x%x ConfigRet 0x%x";
    }
    else
    {
      v14 = CWwanResetRecoveryHelper::_TriggerDisableDevice(dnDevInst[1]);
      *a3 = v14;
      if ( !v14 )
      {
        WwanLog::Info(
          "CWwanResetRecoveryHelper::_TriggerEnableDisable",
          a1,
          L"Successfully triggered PnP Disable on the Interface!");
        goto LABEL_16;
      }
      v12 = GetLastError();
      v13 = L"Couldn't Disable the Device 0x%x ConfigRet 0x%x";
    }
    LODWORD(LastError) = v12;
    LODWORD(v16) = *a3;
    WwanLog::Error("CWwanResetRecoveryHelper::_TriggerEnableDisable", 0, v13, v12, v16);
    goto LABEL_16;
  }
  LastError = GetLastError();
  WwanLog::Error(
    "CWwanResetRecoveryHelper::_TriggerEnableDisable",
    0,
    L"DevObjCreateDeviceInfoList Failure 0x%x",
    LastError);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180095630  mov     [rsp+arg_8], rbx
0x180095635  mov     [rsp+arg_18], rbp
0x18009563a  push    rsi
0x18009563b  push    rdi
0x18009563c  push    r14
0x18009563e  sub     rsp, 70h
0x180095642  mov     rax, cs:__security_cookie
0x180095649  xor     rax, rsp
0x18009564c  mov     [rsp+88h+var_28], rax
0x180095651  xorps   xmm0, xmm0
0x180095654  mov     [rsp+88h+var_68], 0
0x18009565d  mov     rdi, r8
0x180095660  mov     esi, edx
0x180095662  mov     rbp, rcx
0x180095665  xor     r8d, r8d
0x180095668  xor     edx, edx
0x18009566a  lea     rcx, GUID_DEVCLASS_NET
0x180095671  xor     r9d, r9d
0x180095674  movups  [rsp+88h+var_58], xmm0
0x180095679  movups  xmmword ptr [rsp+88h+dnDevInst], xmm0
0x18009567e  movups  [rsp+88h+var_38], xmm0
0x180095683  call    cs:__imp_DevObjCreateDeviceInfoList
0x180095689  mov     r14, rax
0x18009568c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180095690  jnz     short loc_1800956B7
0x180095692  call    cs:__imp_GetLastError
0x180095698  lea     r8, aDevobjcreatede_1; "DevObjCreateDeviceInfoList Failure 0x%x"
0x18009569f  xor     edx, edx; struct _GUID *
0x1800956a1  mov     r9d, eax
0x1800956a4  lea     rcx, aCwwanresetreco_19; "CWwanResetRecoveryHelper::_TriggerEnabl"...
0x1800956ab  mov     ebx, eax
0x1800956ad  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800956b2  jmp     loc_1800957D5
0x1800956b7  mov     [rsp+88h+var_60], 0
0x1800956c0  lea     rdx, GUID_DEVCLASS_NET
0x1800956c7  mov     r9d, 2
0x1800956cd  mov     [rsp+88h+var_68], 0
0x1800956d6  xor     r8d, r8d
0x1800956d9  mov     rcx, r14
0x1800956dc  call    cs:__imp_DevObjGetClassDevs
0x1800956e2  test    eax, eax
0x1800956e4  jnz     short loc_1800956FA
0x1800956e6  call    cs:__imp_GetLastError
0x1800956ec  mov     ebx, eax
0x1800956ee  lea     r8, aDevobjgetclass_0; "DevObjGetClassDevs Failure 0x%x"
0x1800956f5  jmp     loc_1800957BB
0x1800956fa  xor     r9d, r9d; bool *
0x1800956fd  mov     dword ptr [rsp+88h+var_58], 30h ; '0'
0x180095705  lea     r8, [rsp+88h+var_58]; struct _DO_DEVINFO_DATA *
0x18009570a  mov     rdx, rbp; struct _GUID *
0x18009570d  mov     rcx, r14; void *
0x180095710  call    ?getDeviceInfo@CWwanDeviceEnumerator@@CAKPEAXAEBU_GUID@@AEAU_DO_DEVINFO_DATA@@PEA_N@Z; CWwanDeviceEnumerator::getDeviceInfo(void *,_GUID const &,_DO_DEVINFO_DATA &,bool *)
0x180095715  mov     ebx, eax
0x180095717  test    eax, eax
0x180095719  jnz     loc_1800957B4
0x18009571f  mov     ecx, [rsp+88h+dnDevInst+4]; dnAncestor
0x180095723  test    esi, esi
0x180095725  jz      short loc_180095778
0x180095727  xor     edx, edx; ulFlags
0x180095729  call    cs:__imp_CM_Setup_DevNode
0x18009572f  mov     esi, eax
0x180095731  test    eax, eax
0x180095733  jz      short loc_18009575E
0x180095735  mov     r9d, eax
0x180095738  lea     r8, aUnableToEnable; "Unable to Enable the Device 0x%x"
0x18009573f  xor     edx, edx; struct _GUID *
0x180095741  lea     rcx, aCwwanresetreco_17; "CWwanResetRecoveryHelper::_TriggerEnabl"...
0x180095748  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18009574d  mov     [rdi], esi
0x18009574f  call    cs:__imp_GetLastError
0x180095755  lea     r8, aCouldnTEnableT; "Couldn't Enable the Device 0x%x ConfigR"...
0x18009575c  jmp     short loc_180095799
0x18009575e  mov     [rdi], esi
0x180095760  lea     r8, aSuccessfullyTr_1; "Successfully triggered PnP Enable on th"...
0x180095767  mov     rdx, rbp; struct _GUID *
0x18009576a  lea     rcx, aCwwanresetreco_19; "CWwanResetRecoveryHelper::_TriggerEnabl"...
0x180095771  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180095776  jmp     short loc_1800957CC
0x180095778  call    ?_TriggerDisableDevice@CWwanResetRecoveryHelper@@CAKK@Z; CWwanResetRecoveryHelper::_TriggerDisableDevice(ulong)
0x18009577d  mov     [rdi], eax
0x18009577f  test    eax, eax
0x180095781  jnz     short loc_18009578C
0x180095783  lea     r8, aSuccessfullyTr_0; "Successfully triggered PnP Disable on t"...
0x18009578a  jmp     short loc_180095767
0x18009578c  call    cs:__imp_GetLastError
0x180095792  lea     r8, aCouldnTDisable; "Couldn't Disable the Device 0x%x Config"...
0x180095799  mov     ebx, eax
0x18009579b  lea     rcx, aCwwanresetreco_19; "CWwanResetRecoveryHelper::_TriggerEnabl"...
0x1800957a2  mov     eax, [rdi]
0x1800957a4  mov     r9d, ebx
0x1800957a7  xor     edx, edx; struct _GUID *
0x1800957a9  mov     dword ptr [rsp+88h+var_68], eax
0x1800957ad  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800957b2  jmp     short loc_1800957CC
0x1800957b4  lea     r8, aDeviceThatWeWe; "Device that we were looking for was not"...
0x1800957bb  mov     r9d, eax
0x1800957be  lea     rcx, aCwwanresetreco_19; "CWwanResetRecoveryHelper::_TriggerEnabl"...
0x1800957c5  xor     edx, edx; struct _GUID *
0x1800957c7  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800957cc  mov     rcx, r14
0x1800957cf  call    cs:__imp_DevObjDestroyDeviceInfoList
0x1800957d5  mov     eax, ebx
0x1800957d7  mov     rcx, [rsp+88h+var_28]
0x1800957dc  xor     rcx, rsp; StackCookie
0x1800957df  call    __security_check_cookie
0x1800957e4  lea     r11, [rsp+88h+var_18]
0x1800957e9  mov     rbx, [r11+28h]
0x1800957ed  mov     rbp, [r11+38h]
0x1800957f1  mov     rsp, r11
0x1800957f4  pop     r14
0x1800957f6  pop     rdi
0x1800957f7  pop     rsi
0x1800957f8  retn
```
