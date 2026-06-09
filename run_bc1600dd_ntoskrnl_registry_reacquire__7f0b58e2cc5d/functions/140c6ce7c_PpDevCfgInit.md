# PpDevCfgInit

- ea: `0x140c6ce7c`
- end: `0x140c6d201`
- name: `PpDevCfgInit`
- size: `901`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140c669ac`

## callees

- `0x1405e51c8`
- `0x1406dc8c0`
- `0x1406dd5c0`
- `0x1406f7380`
- `0x140734f48`
- `0x14076f6b0`
- `0x14077987c`
- `0x14077a7cc`
- `0x14086daf0`
- `0x140878678`
- `0x1408efd10`
- `0x1408fc6c0`
- `0x140a87f94`
- `0x140a92ae0`
- `0x140aa90e8`
- `0x140c6ce7c`

## string_xrefs

- `0x140c6cf9d`: `DeviceInstall`
- `0x140c6d03a`: `DeviceInstallMode`
- `0x140c6d081`: `DriverUpdatesPending`

## pseudocode

```c
__int64 PpDevCfgInit()
{
  char v0; // r14
  int v1; // ecx
  int ObjectProperties; // esi
  __int64 v3; // rdx
  __int64 v4; // rcx
  int v5; // edi
  int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rcx
  int v10; // eax
  int SyncNodesUpdated; // eax
  __int64 v12; // rcx
  int v14; // [rsp+20h] [rbp-E0h]
  int v15; // [rsp+28h] [rbp-D8h]
  char v16; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v17[3]; // [rsp+61h] [rbp-9Fh] BYREF
  int v18; // [rsp+64h] [rbp-9Ch] BYREF
  int v19; // [rsp+68h] [rbp-98h] BYREF
  int v20; // [rsp+6Ch] [rbp-94h] BYREF
  int v21; // [rsp+70h] [rbp-90h] BYREF
  int v22; // [rsp+74h] [rbp-8Ch] BYREF
  int v23; // [rsp+78h] [rbp-88h] BYREF
  HANDLE Handle; // [rsp+80h] [rbp-80h] BYREF
  HANDLE v25; // [rsp+88h] [rbp-78h] BYREF
  __int128 v26; // [rsp+90h] [rbp-70h] BYREF
  __int64 *v27; // [rsp+A0h] [rbp-60h] BYREF
  int v28; // [rsp+A8h] [rbp-58h]
  int *v29; // [rsp+B0h] [rbp-50h]
  int v30; // [rsp+B8h] [rbp-48h]
  int v31; // [rsp+C0h] [rbp-40h]
  __int64 *v32; // [rsp+C8h] [rbp-38h]
  int v33; // [rsp+D0h] [rbp-30h]
  int *v34; // [rsp+D8h] [rbp-28h]
  int v35; // [rsp+E0h] [rbp-20h]
  int v36; // [rsp+E8h] [rbp-18h]
  __int64 *v37; // [rsp+F0h] [rbp-10h]
  int v38; // [rsp+F8h] [rbp-8h]
  char *v39; // [rsp+100h] [rbp+0h]
  int v40; // [rsp+108h] [rbp+8h]
  int v41; // [rsp+110h] [rbp+10h]

  v19 = 0;
  v21 = 0;
  v16 = 0;
  v0 = 0;
  v17[0] = 0;
  v26 = 0;
  v25 = 0;
  Handle = 0;
  v20 = 0;
  memset_0(&v27, 0, 0x78u);
  v28 = 7;
  v27 = DEVPKEY_DriverDatabase_ConfigMode;
  v30 = 4;
  v29 = &v19;
  v32 = DEVPKEY_DriverDatabase_ConfigOptions;
  v33 = 7;
  v34 = &v21;
  v35 = 4;
  v39 = &v16;
  v37 = DEVPKEY_DriverDatabase_Updated;
  v38 = 17;
  v40 = 1;
  ObjectProperties = PiDevCfgQueryObjectProperties(v1, (unsigned int)L"SYSTEM", 7, 0, (__int64)&v27, 3);
  if ( ObjectProperties >= 0 )
  {
    if ( v31 >= 0 )
    {
      if ( (v19 & 3) == 0 )
        v19 = 0;
    }
    else
    {
      v19 = 3;
    }
    if ( v36 < 0 )
      v21 = 0;
    if ( v41 < 0 )
      v16 = 0;
    LODWORD(v26) = 1835034;
    *((_QWORD *)&v26 + 1) = L"DeviceInstall";
    LOBYTE(v14) = 0;
    if ( (int)PipOpenServiceEnumKeys(&v26, 131097, &v25, 0, v14) >= 0 )
    {
      v5 = 1;
      v6 = 0;
      v22 = 1;
      v23 = 0;
      if ( (int)PnpCtxRegOpenKey(PiPnpRtlCtx, (_DWORD)v25, (unsigned int)L"Parameters", 0, 131097, (__int64)&Handle) >= 0 )
      {
        if ( (unsigned __int8)RtlIsStateSeparationEnabled(v8, v7) )
        {
          v18 = 4;
          if ( (int)PnpCtxRegQueryValue(v9, Handle, L"DeviceInstallMode", &v20, &v22, &v18) < 0
            || v20 != 4
            || (v5 = v22, v18 != 4) )
          {
            v5 = 0;
          }
        }
        v18 = 4;
        if ( (int)PnpCtxRegQueryValue(v9, Handle, L"DriverUpdatesPending", &v20, &v23, &v18) >= 0
          && v20 == 4
          && v18 == 4 )
        {
          v6 = v23;
        }
        ZwClose(Handle);
      }
      ZwClose(v25);
      if ( v5 )
      {
        PiDevCfgFlags |= 2u;
        if ( v6 )
          PpDevCfgRequestDeviceInstall();
      }
    }
    *(_DWORD *)((char *)&NlsMbCodePageTag + 7) = v19;
    PiDevCfgOptions = v21;
    if ( (Feature_KernelPnP_CheckDriverIntegrity__private_featureState & 0x10) != 0 )
      v10 = Feature_KernelPnP_CheckDriverIntegrity__private_featureState & 1;
    else
      v10 = Feature_KernelPnP_CheckDriverIntegrity__private_IsEnabledDeviceUsageNoInline();
    if ( v10 )
    {
      LOBYTE(v4) = 1;
      PiDevCfgReadDriverPolicy(v4, &PiDevCfgSystemDriverPolicy);
    }
    if ( *(_DWORD *)((char *)&NlsMbCodePageTag + 7) )
    {
      if ( (PiDevCfgOptions & 0x20) != 0 || (PiDevCfgFlags & 2) == 0 )
      {
        SyncNodesUpdated = PiDrvDbQuerySyncNodesUpdated(0, v17);
        v0 = v17[0];
        if ( SyncNodesUpdated >= 0 )
        {
          if ( v17[0] )
            PiDevCfgFlags |= 1u;
        }
      }
      if ( v16 == -1 )
        PiDevCfgFlags |= 1u;
    }
    if ( (PiDevCfgFlags & 1) != 0 )
    {
      if ( !(unsigned __int8)RtlIsStateSeparationEnabled(v4, v3)
        || (ObjectProperties = PiDrvDbEnumNodes(), ObjectProperties >= 0) )
      {
        ObjectProperties = PiDmEnumObjectsWithCallback(1, PiDevCfgInitDeviceCallback);
        if ( ObjectProperties >= 0 )
        {
          if ( v16 == -1 )
            PiDevCfgSetObjectProperty(
              PiPnpRtlCtx,
              0,
              (unsigned int)L"SYSTEM",
              7,
              0,
              v15,
              (__int64)DEVPKEY_DriverDatabase_Updated,
              0,
              0,
              0,
              0);
          if ( v0 )
          {
            LOBYTE(v12) = 1;
            PiDrvDbQuerySyncNodesUpdated(v12, 0);
          }
        }
      }
    }
  }
  return (unsigned int)ObjectProperties;
}

```

## disassembly

```asm
0x140c6ce7c  push    rbp
0x140c6ce7e  push    rbx
0x140c6ce7f  push    rsi
0x140c6ce80  push    rdi
0x140c6ce81  push    r13
0x140c6ce83  push    r14
0x140c6ce85  push    r15
0x140c6ce87  lea     rbp, [rsp-30h]
0x140c6ce8c  sub     rsp, 130h
0x140c6ce93  mov     rax, cs:__security_cookie
0x140c6ce9a  xor     rax, rsp
0x140c6ce9d  mov     [rbp+60h+var_40], rax
0x140c6cea1  xor     r15d, r15d
0x140c6cea4  lea     rcx, [rbp+60h+var_C0]; void *
0x140c6cea8  xorps   xmm0, xmm0
0x140c6ceab  mov     [rsp+160h+var_F8], r15d
0x140c6ceb0  xor     edx, edx; Val
0x140c6ceb2  mov     [rsp+160h+var_F0], r15d
0x140c6ceb7  mov     [rsp+160h+var_100], r15b
0x140c6cebc  mov     r14b, r15b
0x140c6cebf  lea     r8d, [r15+78h]; Size
0x140c6cec3  mov     [rsp+160h+var_FF], r15b
0x140c6cec8  movups  [rbp+60h+var_D0], xmm0
0x140c6cecc  mov     [rbp+60h+var_D8], r15
0x140c6ced0  mov     [rbp+60h+Handle], r15
0x140c6ced4  mov     [rsp+160h+var_F4], r15d
0x140c6ced9  call    memset_0
0x140c6cede  lea     rax, DEVPKEY_DriverDatabase_ConfigMode
0x140c6cee5  mov     [rbp+60h+var_B8], 7
0x140c6ceec  mov     [rbp+60h+var_C0], rax
0x140c6cef0  lea     r13d, [r15+4]
0x140c6cef4  lea     rax, [rsp+160h+var_F8]
0x140c6cef9  mov     [rbp+60h+var_A8], r13d
0x140c6cefd  mov     [rbp+60h+var_B0], rax
0x140c6cf01  lea     ebx, [r15+3]
0x140c6cf05  lea     rax, DEVPKEY_DriverDatabase_ConfigOptions
0x140c6cf0c  mov     dword ptr [rsp+160h+var_138], ebx
0x140c6cf10  mov     [rbp+60h+var_98], rax
0x140c6cf14  lea     rdi, DEVPKEY_DriverDatabase_Updated
0x140c6cf1b  lea     rax, [rsp+160h+var_F0]
0x140c6cf20  mov     [rbp+60h+var_90], 7
0x140c6cf27  mov     [rbp+60h+var_88], rax
0x140c6cf2b  lea     r8d, [r15+7]
0x140c6cf2f  lea     rax, [rsp+160h+var_100]
0x140c6cf34  mov     [rbp+60h+var_80], r13d
0x140c6cf38  mov     [rbp+60h+var_60], rax
0x140c6cf3c  lea     rdx, aSystem_7; "SYSTEM"
0x140c6cf43  lea     rax, [rbp+60h+var_C0]
0x140c6cf47  mov     [rbp+60h+var_70], rdi
0x140c6cf4b  xor     r9d, r9d
0x140c6cf4e  mov     [rsp+160h+var_140], rax
0x140c6cf53  mov     [rbp+60h+var_68], 11h
0x140c6cf5a  mov     [rbp+60h+var_58], 1
0x140c6cf61  call    PiDevCfgQueryObjectProperties
0x140c6cf66  mov     esi, eax
0x140c6cf68  test    eax, eax
0x140c6cf6a  js      loc_140C6D1E0
0x140c6cf70  cmp     [rbp+60h+var_A0], r15d
0x140c6cf74  jge     short loc_140C6CF7C
0x140c6cf76  mov     [rsp+160h+var_F8], ebx
0x140c6cf7a  jmp     short loc_140C6CF87
0x140c6cf7c  test    byte ptr [rsp+160h+var_F8], bl
0x140c6cf80  jnz     short loc_140C6CF87
0x140c6cf82  mov     [rsp+160h+var_F8], r15d
0x140c6cf87  cmp     [rbp+60h+var_78], r15d
0x140c6cf8b  jge     short loc_140C6CF92
0x140c6cf8d  mov     [rsp+160h+var_F0], r15d
0x140c6cf92  cmp     [rbp+60h+var_50], r15d
0x140c6cf96  jge     short loc_140C6CF9D
0x140c6cf98  mov     [rsp+160h+var_100], r15b
0x140c6cf9d  lea     rax, aDeviceinstall; "DeviceInstall"
0x140c6cfa4  mov     dword ptr [rbp+60h+var_D0], 1C001Ah
0x140c6cfab  xor     r9d, r9d
0x140c6cfae  mov     qword ptr [rbp+60h+var_D0+8], rax
0x140c6cfb2  lea     r8, [rbp+60h+var_D8]
0x140c6cfb6  mov     byte ptr [rsp+160h+var_140], r15b
0x140c6cfbb  mov     edx, 20019h
0x140c6cfc0  lea     rcx, [rbp+60h+var_D0]
0x140c6cfc4  call    PipOpenServiceEnumKeys
0x140c6cfc9  test    eax, eax
0x140c6cfcb  js      loc_140C6D0D5
0x140c6cfd1  mov     rdx, [rbp+60h+var_D8]
0x140c6cfd5  lea     rax, [rbp+60h+Handle]
0x140c6cfd9  mov     rcx, cs:PiPnpRtlCtx
0x140c6cfe0  lea     r8, aParameters_0; "Parameters"
0x140c6cfe7  mov     [rsp+160h+var_138], rax
0x140c6cfec  mov     edi, 1
0x140c6cff1  mov     ebx, r15d
0x140c6cff4  mov     dword ptr [rsp+160h+var_140], 20019h
0x140c6cffc  xor     r9d, r9d
0x140c6cfff  mov     [rsp+160h+var_EC], edi
0x140c6d003  mov     [rsp+160h+var_E8], ebx
0x140c6d007  call    _PnpCtxRegOpenKey
0x140c6d00c  test    eax, eax
0x140c6d00e  js      loc_140C6D0B1
0x140c6d014  call    RtlIsStateSeparationEnabled
0x140c6d019  test    al, al
0x140c6d01b  jz      short loc_140C6D064
0x140c6d01d  mov     rdx, [rbp+60h+Handle]
0x140c6d021  lea     rax, [rsp+160h+var_FC]
0x140c6d026  mov     [rsp+160h+var_138], rax
0x140c6d02b  lea     r9, [rsp+160h+var_F4]
0x140c6d030  lea     rax, [rsp+160h+var_EC]
0x140c6d035  mov     [rsp+160h+var_FC], r13d
0x140c6d03a  lea     r8, aDeviceinstallm; "DeviceInstallMode"
0x140c6d041  mov     [rsp+160h+var_140], rax
0x140c6d046  call    _PnpCtxRegQueryValue
0x140c6d04b  test    eax, eax
0x140c6d04d  js      short loc_140C6D061
0x140c6d04f  cmp     [rsp+160h+var_F4], r13d
0x140c6d054  jnz     short loc_140C6D061
0x140c6d056  mov     edi, [rsp+160h+var_EC]
0x140c6d05a  cmp     [rsp+160h+var_FC], r13d
0x140c6d05f  jz      short loc_140C6D064
0x140c6d061  mov     edi, r15d
0x140c6d064  mov     rdx, [rbp+60h+Handle]
0x140c6d068  lea     rax, [rsp+160h+var_FC]
0x140c6d06d  mov     [rsp+160h+var_138], rax
0x140c6d072  lea     r9, [rsp+160h+var_F4]
0x140c6d077  lea     rax, [rsp+160h+var_E8]
0x140c6d07c  mov     [rsp+160h+var_FC], r13d
0x140c6d081  lea     r8, aDriverupdatesp; "DriverUpdatesPending"
0x140c6d088  mov     [rsp+160h+var_140], rax
0x140c6d08d  call    _PnpCtxRegQueryValue
0x140c6d092  test    eax, eax
0x140c6d094  js      short loc_140C6D0A8
0x140c6d096  cmp     [rsp+160h+var_F4], r13d
0x140c6d09b  jnz     short loc_140C6D0A8
0x140c6d09d  cmp     [rsp+160h+var_FC], r13d
0x140c6d0a2  jnz     short loc_140C6D0A8
0x140c6d0a4  mov     ebx, [rsp+160h+var_E8]
0x140c6d0a8  mov     rcx, [rbp+60h+Handle]; Handle
0x140c6d0ac  call    ZwClose
0x140c6d0b1  mov     rcx, [rbp+60h+var_D8]; Handle
0x140c6d0b5  call    ZwClose
0x140c6d0ba  test    edi, edi
0x140c6d0bc  jz      short loc_140C6D0CE
0x140c6d0be  or      cs:PiDevCfgFlags, 2
0x140c6d0c5  test    ebx, ebx
0x140c6d0c7  jz      short loc_140C6D0CE
0x140c6d0c9  call    PpDevCfgRequestDeviceInstall
0x140c6d0ce  lea     rdi, DEVPKEY_DriverDatabase_Updated
0x140c6d0d5  mov     eax, [rsp+160h+var_F8]
0x140c6d0d9  mov     dword ptr cs:NlsMbCodePageTag+7, eax
0x140c6d0df  mov     eax, [rsp+160h+var_F0]
0x140c6d0e3  mov     cs:PiDevCfgOptions, eax
0x140c6d0e9  mov     eax, cs:Feature_KernelPnP_CheckDriverIntegrity__private_featureState
0x140c6d0ef  test    al, 10h
0x140c6d0f1  jz      short loc_140C6D0F8
0x140c6d0f3  and     eax, 1
0x140c6d0f6  jmp     short loc_140C6D0FD
0x140c6d0f8  call    Feature_KernelPnP_CheckDriverIntegrity__private_IsEnabledDeviceUsageNoInline
0x140c6d0fd  test    eax, eax
0x140c6d0ff  jz      short loc_140C6D10F
0x140c6d101  lea     rdx, PiDevCfgSystemDriverPolicy
0x140c6d108  mov     cl, 1
0x140c6d10a  call    PiDevCfgReadDriverPolicy
0x140c6d10f  cmp     dword ptr cs:NlsMbCodePageTag+7, r15d
0x140c6d116  jz      short loc_140C6D15B
0x140c6d118  mov     eax, cs:PiDevCfgOptions
0x140c6d11e  test    al, 20h
0x140c6d120  jnz     short loc_140C6D12C
0x140c6d122  mov     eax, cs:PiDevCfgFlags
0x140c6d128  test    al, 2
0x140c6d12a  jnz     short loc_140C6D14D
0x140c6d12c  lea     rdx, [rsp+160h+var_FF]
0x140c6d131  xor     ecx, ecx
0x140c6d133  call    PiDrvDbQuerySyncNodesUpdated
0x140c6d138  mov     r14b, [rsp+160h+var_FF]
0x140c6d13d  test    eax, eax
0x140c6d13f  js      short loc_140C6D14D
0x140c6d141  test    r14b, r14b
0x140c6d144  jz      short loc_140C6D14D
0x140c6d146  or      cs:PiDevCfgFlags, 1
0x140c6d14d  cmp     [rsp+160h+var_100], 0FFh
0x140c6d152  jnz     short loc_140C6D15B
0x140c6d154  or      cs:PiDevCfgFlags, 1
0x140c6d15b  mov     eax, cs:PiDevCfgFlags
0x140c6d161  test    al, 1
0x140c6d163  jz      short loc_140C6D1E0
0x140c6d165  call    RtlIsStateSeparationEnabled
0x140c6d16a  test    al, al
0x140c6d16c  jz      short loc_140C6D179
0x140c6d16e  call    PiDrvDbEnumNodes
0x140c6d173  mov     esi, eax
0x140c6d175  test    eax, eax
0x140c6d177  js      short loc_140C6D1E0
0x140c6d179  xor     r8d, r8d
0x140c6d17c  lea     rdx, PiDevCfgInitDeviceCallback
0x140c6d183  lea     ecx, [r8+1]
0x140c6d187  call    PiDmEnumObjectsWithCallback
0x140c6d18c  mov     esi, eax
0x140c6d18e  test    eax, eax
0x140c6d190  js      short loc_140C6D1E0
0x140c6d192  cmp     [rsp+160h+var_100], 0FFh
0x140c6d197  jnz     short loc_140C6D1D2
0x140c6d199  mov     rcx, cs:PiPnpRtlCtx
0x140c6d1a0  lea     r8, aSystem_7; "SYSTEM"
0x140c6d1a7  mov     [rsp+160h+var_110], r15d
0x140c6d1ac  mov     r9d, 7
0x140c6d1b2  mov     [rsp+160h+var_118], r15d
0x140c6d1b7  xor     edx, edx
0x140c6d1b9  mov     [rsp+160h+var_120], r15
0x140c6d1be  mov     [rsp+160h+var_128], r15d
0x140c6d1c3  mov     [rsp+160h+var_130], rdi
0x140c6d1c8  mov     [rsp+160h+var_140], r15
0x140c6d1cd  call    PiDevCfgSetObjectProperty
0x140c6d1d2  test    r14b, r14b
0x140c6d1d5  jz      short loc_140C6D1E0
0x140c6d1d7  xor     edx, edx
0x140c6d1d9  mov     cl, 1
0x140c6d1db  call    PiDrvDbQuerySyncNodesUpdated
0x140c6d1e0  mov     eax, esi
0x140c6d1e2  mov     rcx, [rbp+60h+var_40]
0x140c6d1e6  xor     rcx, rsp; StackCookie
0x140c6d1e9  call    __security_check_cookie
0x140c6d1ee  add     rsp, 130h
0x140c6d1f5  pop     r15
0x140c6d1f7  pop     r14
0x140c6d1f9  pop     r13
0x140c6d1fb  pop     rdi
0x140c6d1fc  pop     rsi
0x140c6d1fd  pop     rbx
0x140c6d1fe  pop     rbp
0x140c6d1ff  retn
```
