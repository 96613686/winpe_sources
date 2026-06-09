# WdfDevNode::QueryAppVerifierFilter(void *,_DO_DEVINFO_DATA *)

- ea: `0x14008e804`
- end: `0x14008ecf5`
- name: `?QueryAppVerifierFilter@WdfDevNode@@AEAAXPEAXPEAU_DO_DEVINFO_DATA@@@Z`
- size: `1265`
- prototype: `void __fastcall(WdfDevNode *__hidden this, void *, struct _DO_DEVINFO_DATA *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x14002ba14`

## callees

- `0x140004c58`
- `0x1400188fc`
- `0x14001f99c`
- `0x140027998`
- `0x140044300`
- `0x14004af50`
- `0x14004b1c0`
- `0x14004c360`
- `0x1400575b0`
- `0x14008e804`
- `0x140094020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008ea5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008ea5b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14008e885`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14008e885`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14008ecbb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14008ecbb`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x14008ea51`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x14008ea51`

## pseudocode

```c
void __fastcall WdfDevNode::QueryAppVerifierFilter(WdfDevNode *this, void *a2, struct _DO_DEVINFO_DATA *a3)
{
  struct _DO_DEVINFO_DATA *v3; // r13
  void *v4; // r12
  WdfDevNode *v5; // r15
  unsigned __int16 *v6; // r14
  unsigned __int16 *v7; // rax
  wchar_t *i; // rcx
  unsigned __int64 v9; // rax
  PRPC_ASYNC_STATE v10; // rcx
  __int64 v11; // rdx
  unsigned int v12; // eax
  unsigned int v13; // r15d
  const wchar_t *v14; // r12
  DWORD LastError; // eax
  PRPC_ASYNC_STATE v16; // rcx
  __int64 v17; // rdx
  const wchar_t *v18; // rdx
  wchar_t *v19; // rsi
  unsigned int v20; // [rsp+40h] [rbp-69h] BYREF
  unsigned int v21; // [rsp+44h] [rbp-65h] BYREF
  WdfDevNode *v22; // [rsp+48h] [rbp-61h]
  int v23; // [rsp+50h] [rbp-59h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-51h] BYREF
  wchar_t *Context; // [rsp+60h] [rbp-49h] BYREF
  void *v26; // [rsp+68h] [rbp-41h]
  struct _DO_DEVINFO_DATA *v27; // [rsp+70h] [rbp-39h]
  wchar_t String2[32]; // [rsp+80h] [rbp-29h] BYREF

  v27 = a3;
  v3 = a3;
  v4 = a2;
  v5 = this;
  v26 = a2;
  v22 = this;
  hKey = 0;
  v21 = 0;
  v20 = 0;
  Context = 0;
  v23 = 0;
  if ( !*((_DWORD *)this + 75) )
  {
    v6 = 0;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Image File Execution Options\\WUDFHost.exe",
            0,
            0x20019u,
            &hKey) )
    {
      v7 = WdfRegQueryString(hKey, L"VerifierActivationFilter", &v21, &v20);
      v6 = v7;
      if ( v7 )
      {
        if ( v20 && (v20 != 2 || *v7) && (v20 != 4 || *v7 != 42 || v7[1]) )
        {
          if ( v21 == 1 && v20 >= 0x16 )
          {
            if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) != 0
              && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 4u )
            {
              WPP_SF_S(WPP_GLOBAL_Control->u.APC.hThread, 126, &WPP_bad7cb52cb61361e2ed56d413b131532_Traceguids, v7);
            }
            for ( i = v6; ; i = 0 )
            {
              v19 = wcstok_s(i, L" ", &Context);
              if ( !v19 )
                goto LABEL_77;
              v9 = -1;
              do
                ++v9;
              while ( v19[v9] );
              if ( v9 <= 0x100 )
              {
                if ( wcsnicmp(v19, L"-AppVerifierDriver:", 0x13u) )
                {
                  if ( wcsnicmp(v19, L"-AppVerifierInfSetupClass:", 0x1Au) )
                  {
                    if ( wcsnicmp(v19, L"-DeviceGroupId:", 0xFu) )
                    {
                      v10 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                        && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) != 0
                        && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 3u )
                      {
                        v11 = 134;
                        goto LABEL_55;
                      }
                    }
                    else
                    {
                      v18 = (const wchar_t *)*((_QWORD *)v5 + 31);
                      if ( v18 && !wcsicmp(v19 + 15, v18) )
                      {
                        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                          && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) != 0
                          && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 4u )
                        {
                          WPP_SF_S(
                            WPP_GLOBAL_Control->u.APC.hThread,
                            133,
                            &WPP_bad7cb52cb61361e2ed56d413b131532_Traceguids,
                            *((_QWORD *)v5 + 31));
                        }
                        goto LABEL_77;
                      }
                    }
                  }
                  else if ( (unsigned int)DevObjGetDeviceProperty(
                                            v4,
                                            v3,
                                            &DEVPKEY_Device_Class,
                                            &v23,
                                            String2,
                                            64,
                                            &v20,
                                            0) )
                  {
                    if ( !wcsicmp(v19 + 26, String2) )
                    {
                      if ( (*(int (__fastcall **)(struct IUMDFPlatform *, __int64, wchar_t *, __int64, _QWORD))(*(_QWORD *)g_Platform + 264LL))(
                             g_Platform,
                             809782613,
                             v19,
                             (__int64)v5 + 344,
                             0) >= 0 )
                      {
                        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                          && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) != 0
                          && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 4u )
                        {
                          WPP_SF_S(
                            WPP_GLOBAL_Control->u.APC.hThread,
                            132,
                            &WPP_bad7cb52cb61361e2ed56d413b131532_Traceguids,
                            String2);
                        }
                      }
                      else
                      {
                        v16 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                          && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) != 0
                          && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
                        {
                          v17 = 131;
                          goto LABEL_76;
                        }
                      }
                      goto LABEL_77;
                    }
                  }
                  else
                  {
                    LastError = GetLastError();
                    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                      && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) != 0
                      && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
                    {
                      WPP_SF_d(
                        WPP_GLOBAL_Control->u.APC.hThread,
                        130,
                        &WPP_bad7cb52cb61361e2ed56d413b131532_Traceguids,
                        LastError);
                    }
                  }
                }
                else
                {
                  v12 = *((_DWORD *)v5 + 34);
                  if ( v12 )
                  {
                    v13 = 0;
                    while ( 1 )
                    {
                      v14 = 0;
                      if ( v13 < v12 )
                        v14 = *(const wchar_t **)(*(_QWORD *)(*((_QWORD *)v22 + 23) + 8LL * v13) + 72LL);
                      if ( !wcsicmp(v19 + 19, v14) )
                        break;
                      ++v13;
                      v12 = *((_DWORD *)v22 + 34);
                      if ( v13 >= v12 )
                      {
                        v5 = v22;
                        v4 = v26;
                        v3 = v27;
                        goto LABEL_56;
                      }
                    }
                    if ( (*(int (__fastcall **)(struct IUMDFPlatform *, __int64, wchar_t *, __int64, _QWORD))(*(_QWORD *)g_Platform + 264LL))(
                           g_Platform,
                           809782613,
                           v19,
                           (__int64)v22 + 344,
                           0) >= 0 )
                    {
                      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                        && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) != 0
                        && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 4u )
                      {
                        WPP_SF_S(
                          WPP_GLOBAL_Control->u.APC.hThread,
                          129,
                          &WPP_bad7cb52cb61361e2ed56d413b131532_Traceguids,
                          v14);
                      }
                    }
                    else
                    {
                      v16 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                        && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) != 0
                        && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
                      {
                        v17 = 128;
                        goto LABEL_76;
                      }
                    }
                    goto LABEL_77;
                  }
                }
              }
              else
              {
                v10 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                  && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) != 0
                  && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 3u )
                {
                  v11 = 127;
LABEL_55:
                  WPP_SF_S(v10->u.APC.hThread, v11, &WPP_bad7cb52cb61361e2ed56d413b131532_Traceguids, v19);
                  continue;
                }
              }
LABEL_56:
              ;
            }
          }
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 4) != 0
            && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
          {
            v17 = 125;
LABEL_76:
            WPP_SF_(v16->u.APC.hThread, v17, &WPP_bad7cb52cb61361e2ed56d413b131532_Traceguids);
          }
        }
      }
    }
LABEL_77:
    if ( hKey )
      RegCloseKey(hKey);
    if ( v6 )
      operator delete(v6);
  }
}

```

## disassembly

```asm
0x14008e804  mov     [rsp-8+arg_18], rbx
0x14008e809  push    rbp
0x14008e80a  push    rsi
0x14008e80b  push    rdi
0x14008e80c  push    r12
0x14008e80e  push    r13
0x14008e810  push    r14
0x14008e812  push    r15
0x14008e814  lea     rbp, [rsp-27h]
0x14008e819  sub     rsp, 0D0h
0x14008e820  mov     rax, cs:__security_cookie
0x14008e827  xor     rax, rsp
0x14008e82a  mov     [rbp+57h+var_40], rax
0x14008e82e  xor     eax, eax
0x14008e830  mov     [rbp+57h+var_90], r8
0x14008e834  mov     r13, r8
0x14008e837  mov     r12, rdx
0x14008e83a  mov     r15, rcx
0x14008e83d  mov     [rbp+57h+var_98], rdx
0x14008e841  mov     [rbp+57h+var_B8], rcx
0x14008e845  mov     [rbp+57h+hKey], rax
0x14008e849  mov     [rbp+57h+var_BC], eax
0x14008e84c  mov     [rbp+57h+var_C0], eax
0x14008e84f  mov     [rbp+57h+Context], rax
0x14008e853  mov     [rbp+57h+var_B0], eax
0x14008e856  cmp     [rcx+12Ch], eax
0x14008e85c  jnz     loc_14008ECCE
0x14008e862  mov     r14d, eax
0x14008e865  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14008e86c  lea     rax, [rbp+57h+hKey]
0x14008e870  mov     r9d, 20019h; samDesired
0x14008e876  xor     r8d, r8d; ulOptions
0x14008e879  mov     [rsp+100h+phkResult], rax; phkResult
0x14008e87e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14008e885  call    cs:__imp_RegOpenKeyExW
0x14008e88b  xor     esi, esi
0x14008e88d  test    eax, eax
0x14008e88f  jnz     loc_14008ECB2
0x14008e895  mov     rcx, [rbp+57h+hKey]; hKey
0x14008e899  lea     r9, [rbp+57h+var_C0]; unsigned int *
0x14008e89d  lea     r8, [rbp+57h+var_BC]; unsigned int *
0x14008e8a1  lea     rdx, aVerifieractiva; "VerifierActivationFilter"
0x14008e8a8  call    ?WdfRegQueryString@@YAPEAGPEAUHKEY__@@PEBGPEAK2@Z; WdfRegQueryString(HKEY__ *,ushort const *,ulong *,ulong *)
0x14008e8ad  mov     r14, rax
0x14008e8b0  test    rax, rax
0x14008e8b3  jz      loc_14008ECB2
0x14008e8b9  mov     ecx, [rbp+57h+var_C0]
0x14008e8bc  test    ecx, ecx
0x14008e8be  jz      loc_14008ECB2
0x14008e8c4  cmp     ecx, 2
0x14008e8c7  jnz     short loc_14008E8D2
0x14008e8c9  cmp     [rax], si
0x14008e8cc  jz      loc_14008ECB2
0x14008e8d2  cmp     ecx, 4
0x14008e8d5  jnz     short loc_14008E8E7
0x14008e8d7  cmp     word ptr [rax], 2Ah ; '*'
0x14008e8db  jnz     short loc_14008E8E7
0x14008e8dd  cmp     [rax+2], si
0x14008e8e1  jz      loc_14008ECB2
0x14008e8e7  cmp     [rbp+57h+var_BC], 1
0x14008e8eb  jnz     loc_14008EC7E
0x14008e8f1  cmp     ecx, 16h
0x14008e8f4  jb      loc_14008EC7E
0x14008e8fa  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008e901  lea     rbx, WPP_GLOBAL_Control
0x14008e908  lea     rdi, WPP_bad7cb52cb61361e2ed56d413b131532_Traceguids
0x14008e90f  cmp     rcx, rbx
0x14008e912  jz      short loc_14008E934
0x14008e914  test    byte ptr [rcx+44h], 4
0x14008e918  jz      short loc_14008E934
0x14008e91a  cmp     byte ptr [rcx+41h], 4
0x14008e91e  jb      short loc_14008E934
0x14008e920  mov     rcx, [rcx+38h]
0x14008e924  mov     edx, 7Eh ; '~'
0x14008e929  mov     r9, r14
0x14008e92c  mov     r8, rdi
0x14008e92f  call    WPP_SF_S
0x14008e934  mov     rcx, r14
0x14008e937  jmp     loc_14008EBAA
0x14008e93c  or      rax, 0FFFFFFFFFFFFFFFFh
0x14008e940  inc     rax
0x14008e943  cmp     [rsi+rax*2], cx
0x14008e947  jnz     short loc_14008E940
0x14008e949  cmp     rax, 100h
0x14008e94f  jbe     short loc_14008E97F
0x14008e951  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008e958  cmp     rcx, rbx
0x14008e95b  jz      loc_14008EBA8
0x14008e961  test    byte ptr [rcx+44h], 4
0x14008e965  jz      loc_14008EBA8
0x14008e96b  cmp     byte ptr [rcx+41h], 3
0x14008e96f  jb      loc_14008EBA8
0x14008e975  mov     edx, 7Fh
0x14008e97a  jmp     loc_14008EB99
0x14008e97f  mov     r8d, 13h; MaxCount
0x14008e985  lea     rdx, aAppverifierdri; "-AppVerifierDriver:"
0x14008e98c  mov     rcx, rsi; String1
0x14008e98f  call    _wcsnicmp
0x14008e994  xor     edx, edx
0x14008e996  test    eax, eax
0x14008e998  jnz     short loc_14008EA03
0x14008e99a  mov     eax, [r15+88h]
0x14008e9a1  test    eax, eax
0x14008e9a3  jz      loc_14008EBA8
0x14008e9a9  mov     r15d, edx
0x14008e9ac  mov     r12, rdx
0x14008e9af  cmp     r15d, eax
0x14008e9b2  jnb     short loc_14008E9CA
0x14008e9b4  mov     rax, [rbp+57h+var_B8]
0x14008e9b8  mov     ecx, r15d
0x14008e9bb  mov     rax, [rax+0B8h]
0x14008e9c2  mov     rcx, [rax+rcx*8]
0x14008e9c6  mov     r12, [rcx+48h]
0x14008e9ca  mov     rdx, r12; String2
0x14008e9cd  lea     rcx, [rsi+26h]; String1
0x14008e9d1  call    _wcsicmp
0x14008e9d6  xor     edx, edx
0x14008e9d8  test    eax, eax
0x14008e9da  jz      loc_14008EBCD
0x14008e9e0  mov     rax, [rbp+57h+var_B8]
0x14008e9e4  inc     r15d
0x14008e9e7  mov     eax, [rax+88h]
0x14008e9ed  cmp     r15d, eax
0x14008e9f0  jb      short loc_14008E9AC
0x14008e9f2  mov     r15, [rbp+57h+var_B8]
0x14008e9f6  mov     r12, [rbp+57h+var_98]
0x14008e9fa  mov     r13, [rbp+57h+var_90]
0x14008e9fe  jmp     loc_14008EBA8
0x14008ea03  mov     r8d, 1Ah; MaxCount
0x14008ea09  lea     rdx, aAppverifierinf; "-AppVerifierInfSetupClass:"
0x14008ea10  mov     rcx, rsi; String1
0x14008ea13  call    _wcsnicmp
0x14008ea18  xor     ecx, ecx
0x14008ea1a  test    eax, eax
0x14008ea1c  jnz     loc_14008EB15
0x14008ea22  mov     [rsp+100h+var_C8], ecx
0x14008ea26  lea     rax, [rbp+57h+var_C0]
0x14008ea2a  mov     [rsp+100h+var_D0], rax
0x14008ea2f  lea     r9, [rbp+57h+var_B0]
0x14008ea33  lea     rax, [rbp+57h+String2]
0x14008ea37  mov     [rsp+100h+var_D8], 40h ; '@'
0x14008ea3f  lea     r8, DEVPKEY_Device_Class
0x14008ea46  mov     [rsp+100h+phkResult], rax
0x14008ea4b  mov     rdx, r13
0x14008ea4e  mov     rcx, r12
0x14008ea51  call    cs:__imp_DevObjGetDeviceProperty
0x14008ea57  test    eax, eax
0x14008ea59  jnz     short loc_14008EA9E
0x14008ea5b  call    cs:__imp_GetLastError
0x14008ea61  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008ea68  cmp     rcx, rbx
0x14008ea6b  jz      loc_14008EBA8
0x14008ea71  test    byte ptr [rcx+44h], 4
0x14008ea75  jz      loc_14008EBA8
0x14008ea7b  cmp     byte ptr [rcx+41h], 2
0x14008ea7f  jb      loc_14008EBA8
0x14008ea85  mov     rcx, [rcx+38h]
0x14008ea89  mov     edx, 82h
0x14008ea8e  mov     r9d, eax
0x14008ea91  mov     r8, rdi
0x14008ea94  call    WPP_SF_d
0x14008ea99  jmp     loc_14008EBA8
0x14008ea9e  lea     rcx, [rsi+34h]; String1
0x14008eaa2  lea     rdx, [rbp+57h+String2]; String2
0x14008eaa6  call    _wcsicmp
0x14008eaab  xor     edx, edx
0x14008eaad  test    eax, eax
0x14008eaaf  jnz     loc_14008EBA8
0x14008eab5  mov     rcx, cs:?g_Platform@@3PEAUIUMDFPlatform@@EA; IUMDFPlatform * g_Platform
0x14008eabc  lea     r9, [r15+158h]
0x14008eac3  mov     [rsp+100h+phkResult], rdx
0x14008eac8  mov     r8, rsi
0x14008eacb  mov     edx, 30444D55h
0x14008ead0  mov     rax, [rcx]
0x14008ead3  mov     rax, [rax+108h]
0x14008eada  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008eadf  test    eax, eax
0x14008eae1  jns     loc_14008EC5B
0x14008eae7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008eaee  cmp     rcx, rbx
0x14008eaf1  jz      loc_14008ECB2
0x14008eaf7  test    byte ptr [rcx+44h], 4
0x14008eafb  jz      loc_14008ECB2
0x14008eb01  cmp     byte ptr [rcx+41h], 2
0x14008eb05  jb      loc_14008ECB2
0x14008eb0b  mov     edx, 83h
0x14008eb10  jmp     loc_14008EC28
0x14008eb15  mov     r8d, 0Fh; MaxCount
0x14008eb1b  lea     rdx, aDevicegroupid_0; "-DeviceGroupId:"
0x14008eb22  mov     rcx, rsi; String1
0x14008eb25  call    _wcsnicmp
0x14008eb2a  test    eax, eax
0x14008eb2c  jnz     short loc_14008EB7C
0x14008eb2e  mov     rdx, [r15+0F8h]; String2
0x14008eb35  test    rdx, rdx
0x14008eb38  jz      short loc_14008EBA8
0x14008eb3a  lea     rcx, [rsi+1Eh]; String1
0x14008eb3e  call    _wcsicmp
0x14008eb43  test    eax, eax
0x14008eb45  jnz     short loc_14008EBA8
0x14008eb47  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008eb4e  cmp     rcx, rbx
0x14008eb51  jz      loc_14008ECB2
0x14008eb57  test    byte ptr [rcx+44h], 4
0x14008eb5b  jz      loc_14008ECB2
0x14008eb61  cmp     byte ptr [rcx+41h], 4
0x14008eb65  jb      loc_14008ECB2
0x14008eb6b  mov     r9, [r15+0F8h]
0x14008eb72  mov     edx, 85h
0x14008eb77  jmp     loc_14008EC4D
0x14008eb7c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008eb83  cmp     rcx, rbx
0x14008eb86  jz      short loc_14008EBA8
0x14008eb88  test    byte ptr [rcx+44h], 4
0x14008eb8c  jz      short loc_14008EBA8
0x14008eb8e  cmp     byte ptr [rcx+41h], 3
0x14008eb92  jb      short loc_14008EBA8
0x14008eb94  mov     edx, 86h
0x14008eb99  mov     rcx, [rcx+38h]
0x14008eb9d  mov     r9, rsi
0x14008eba0  mov     r8, rdi
0x14008eba3  call    WPP_SF_S
0x14008eba8  xor     ecx, ecx; String
0x14008ebaa  lea     r8, [rbp+57h+Context]; Context
0x14008ebae  lea     rdx, Delimiter; " "
0x14008ebb5  call    wcstok_s
0x14008ebba  xor     ecx, ecx
0x14008ebbc  mov     rsi, rax
0x14008ebbf  test    rax, rax
0x14008ebc2  jnz     loc_14008E93C
0x14008ebc8  jmp     loc_14008ECB2
0x14008ebcd  mov     rcx, cs:?g_Platform@@3PEAUIUMDFPlatform@@EA; IUMDFPlatform * g_Platform
0x14008ebd4  mov     r8, rsi
0x14008ebd7  mov     r9, [rbp+57h+var_B8]
0x14008ebdb  mov     [rsp+100h+phkResult], rdx
0x14008ebe0  add     r9, 158h
0x14008ebe7  mov     edx, 30444D55h
0x14008ebec  mov     rax, [rcx]
0x14008ebef  mov     rax, [rax+108h]
0x14008ebf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008ebfb  test    eax, eax
0x14008ebfd  jns     short loc_14008EC2D
0x14008ebff  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008ec06  cmp     rcx, rbx
0x14008ec09  jz      loc_14008ECB2
0x14008ec0f  test    byte ptr [rcx+44h], 4
0x14008ec13  jz      loc_14008ECB2
0x14008ec19  cmp     byte ptr [rcx+41h], 2
0x14008ec1d  jb      loc_14008ECB2
0x14008ec23  mov     edx, 80h
0x14008ec28  mov     r8, rdi
0x14008ec2b  jmp     short loc_14008ECA9
0x14008ec2d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008ec34  cmp     rcx, rbx
0x14008ec37  jz      short loc_14008ECB2
0x14008ec39  test    byte ptr [rcx+44h], 4
0x14008ec3d  jz      short loc_14008ECB2
0x14008ec3f  cmp     byte ptr [rcx+41h], 4
0x14008ec43  jb      short loc_14008ECB2
0x14008ec45  mov     edx, 81h
0x14008ec4a  mov     r9, r12
0x14008ec4d  mov     rcx, [rcx+38h]
0x14008ec51  mov     r8, rdi
0x14008ec54  call    WPP_SF_S
0x14008ec59  jmp     short loc_14008ECB2
0x14008ec5b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008ec62  cmp     rcx, rbx
0x14008ec65  jz      short loc_14008ECB2
0x14008ec67  test    byte ptr [rcx+44h], 4
0x14008ec6b  jz      short loc_14008ECB2
0x14008ec6d  cmp     byte ptr [rcx+41h], 4
0x14008ec71  jb      short loc_14008ECB2
0x14008ec73  mov     edx, 84h
0x14008ec78  lea     r9, [rbp+57h+String2]
0x14008ec7c  jmp     short loc_14008EC4D
0x14008ec7e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14008ec85  lea     rbx, WPP_GLOBAL_Control
0x14008ec8c  cmp     rcx, rbx
0x14008ec8f  jz      short loc_14008ECB2
0x14008ec91  test    byte ptr [rcx+44h], 4
0x14008ec95  jz      short loc_14008ECB2
0x14008ec97  cmp     byte ptr [rcx+41h], 2
0x14008ec9b  jb      short loc_14008ECB2
0x14008ec9d  mov     edx, 7Dh ; '}'
0x14008eca2  lea     r8, WPP_bad7cb52cb61361e2ed56d413b131532_Traceguids
0x14008eca9  mov     rcx, [rcx+38h]
0x14008ecad  call    WPP_SF_
0x14008ecb2  mov     rcx, [rbp+57h+hKey]; hKey
0x14008ecb6  test    rcx, rcx
0x14008ecb9  jz      short loc_14008ECC1
0x14008ecbb  call    cs:__imp_RegCloseKey
0x14008ecc1  test    r14, r14
0x14008ecc4  jz      short loc_14008ECCE
0x14008ecc6  mov     rcx, r14; void *
0x14008ecc9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14008ecce  mov     rcx, [rbp+57h+var_40]
0x14008ecd2  xor     rcx, rsp; StackCookie
0x14008ecd5  call    __security_check_cookie
0x14008ecda  mov     rbx, [rsp+100h+arg_18]
0x14008ece2  add     rsp, 0D0h
  ... truncated ...
```
