# W3WP_HOST::InitializeHostedConfig(ushort const *,ushort const *,APPHOST_CONFIG * *)

- ea: `0x180004ad4`
- end: `0x1800051d4`
- name: `?InitializeHostedConfig@W3WP_HOST@@QEAAJPEBG0PEAPEAUAPPHOST_CONFIG@@@Z`
- size: `1792`
- prototype: `__int64 __fastcall(W3WP_HOST *this, wchar_t *, wchar_t *, unsigned __int16 ***)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180004750`

## callees

- `0x180001f68`
- `0x180001fa8`
- `0x1800032a8`
- `0x180004ad4`
- `0x18000c39e`
- `0x18000c3d0`
- `0x18000d010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180004e17`
- `msvcrt!_wcsicmp` at `0x180004e17`
- `msvcrt!_ultow` at `0x1800050f1`
- `msvcrt!_ultow` at `0x1800050f1`
- `iisutil!PuDbgPrint` at `0x180004b71`
- `iisutil!PuDbgPrint` at `0x18000514a`
- `iisutil!PuDbgPrint` at `0x180004b71`
- `iisutil!PuDbgPrint` at `0x18000514a`
- `iisutil!PuDbgPrintError` at `0x180004c26`
- `iisutil!PuDbgPrintError` at `0x180004ee5`
- `iisutil!PuDbgPrintError` at `0x180004c26`
- `iisutil!PuDbgPrintError` at `0x180004ee5`
- `nativerd!GetDefaultNativeConfigurationSystem` at `0x180004b8e`
- `nativerd!GetDefaultNativeConfigurationSystem` at `0x180004b8e`
- `nativerd!InitializeNativeConfiguration` at `0x180004b2d`
- `nativerd!InitializeNativeConfiguration` at `0x180004b2d`

## string_xrefs

- `0x180004b65`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x180004c1b`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x180004ede`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x18000511a`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x180004b50`: `Could not initialize native config reader 0x%x\n`
- `0x180004b5e`: `W3WP_HOST::InitializeHostedConfig`
- `0x180004c0f`: `W3WP_HOST::InitializeHostedConfig`
- `0x180004ec9`: `W3WP_HOST::InitializeHostedConfig`
- `0x18000510c`: `W3WP_HOST::InitializeHostedConfig`
- `0x180004bb1`: `Creating config interface failed: 0x%x\n`
- `0x180004bfb`: `SettingConfigPathMapping for applicationhost.config failed\n`
- `0x180004c72`: `SettingConfigPathMapping for root web.config failed\n`
- `0x180004ff8`: `CLRConfigFile`

## pseudocode

```c
__int64 __fastcall W3WP_HOST::InitializeHostedConfig(W3WP_HOST *this, wchar_t *a2, wchar_t *a3, unsigned __int16 ***a4)
{
  W3WP_HOST *v4; // r15
  int DefaultNativeConfigurationSystem; // edi
  __int64 v9; // r8
  const char *v10; // rax
  const char *v11; // rax
  __int64 v12; // r8
  unsigned __int16 **v13; // rax
  unsigned __int16 **v14; // rbx
  __int64 v15; // rcx
  unsigned int i; // esi
  unsigned __int16 *v17; // rcx
  unsigned __int16 *v18; // rcx
  unsigned __int16 *v19; // rcx
  unsigned __int16 *v20; // rcx
  unsigned __int16 *v21; // rcx
  unsigned __int16 *v22; // rcx
  __int64 v24; // [rsp+40h] [rbp-59h] BYREF
  wchar_t *Source; // [rsp+48h] [rbp-51h] BYREF
  __int64 v26; // [rsp+50h] [rbp-49h] BYREF
  __int64 v27; // [rsp+58h] [rbp-41h] BYREF
  unsigned int v28; // [rsp+60h] [rbp-39h] BYREF
  unsigned int Value; // [rsp+64h] [rbp-35h] BYREF
  __int64 v30; // [rsp+68h] [rbp-31h] BYREF
  wchar_t *String1; // [rsp+70h] [rbp-29h] BYREF
  __int128 v32; // [rsp+78h] [rbp-21h] BYREF
  wchar_t *v33; // [rsp+88h] [rbp-11h]
  wchar_t Buffer[16]; // [rsp+90h] [rbp-9h] BYREF

  v4 = g_pW3WPHost;
  v30 = 0;
  v24 = 0;
  v26 = 0;
  v27 = 0;
  String1 = 0;
  v28 = 0;
  Source = 0;
  DefaultNativeConfigurationSystem = InitializeNativeConfiguration();
  if ( DefaultNativeConfigurationSystem < 0 )
  {
    if ( (g_dwDebugFlags & 3) == 0 )
      goto LABEL_69;
    v9 = 1589;
    v10 = "Could not initialize native config reader 0x%x\n";
    goto LABEL_4;
  }
  *((_DWORD *)v4 + 46) = 1;
  DefaultNativeConfigurationSystem = GetDefaultNativeConfigurationSystem((struct INativeConfigurationSystem **)v4 + 24);
  if ( DefaultNativeConfigurationSystem >= 0 )
  {
    if ( a2 )
    {
      if ( *a2 )
      {
        DefaultNativeConfigurationSystem = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, wchar_t *, __int64))(**((_QWORD **)v4 + 24) + 64LL))(
                                             *((_QWORD *)v4 + 24),
                                             L"MACHINE/WEBROOT/APPHOST",
                                             a2,
                                             3);
        if ( DefaultNativeConfigurationSystem < 0 )
        {
          if ( (g_dwDebugFlags & 0xF) == 0 )
            goto LABEL_69;
          v11 = "SettingConfigPathMapping for applicationhost.config failed\n";
          v12 = 1630;
          goto LABEL_13;
        }
      }
    }
    if ( a3 )
    {
      if ( *a3 )
      {
        DefaultNativeConfigurationSystem = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, wchar_t *, __int64))(**((_QWORD **)v4 + 24) + 64LL))(
                                             *((_QWORD *)v4 + 24),
                                             L"MACHINE/WEBROOT",
                                             a3,
                                             2);
        if ( DefaultNativeConfigurationSystem < 0 )
        {
          if ( (g_dwDebugFlags & 0xF) == 0 )
            goto LABEL_69;
          v11 = "SettingConfigPathMapping for root web.config failed\n";
          v12 = 1653;
LABEL_13:
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
            v12,
            "W3WP_HOST::InitializeHostedConfig",
            DefaultNativeConfigurationSystem,
            v11);
          goto LABEL_69;
        }
      }
    }
    v13 = (unsigned __int16 **)operator new(0x70u);
    v14 = v13;
    if ( !v13 )
    {
      DefaultNativeConfigurationSystem = -2147024882;
      goto LABEL_69;
    }
    *v13 = 0;
    v13[1] = 0;
    *((_DWORD *)v13 + 4) = 0;
    v13[3] = 0;
    v13[4] = 0;
    v13[5] = 0;
    v13[6] = 0;
    *((_DWORD *)v13 + 14) = 0;
    v13[8] = 0;
    v13[9] = 0;
    v13[10] = 0;
    v13[11] = 0;
    *((_DWORD *)v13 + 24) = 1;
    v13[13] = 0;
    memset_0(v13, 0, 0x70u);
    DefaultNativeConfigurationSystem = AllocAndCopyString(a2, v14 + 8);
    if ( DefaultNativeConfigurationSystem >= 0 )
    {
      DefaultNativeConfigurationSystem = AllocAndCopyString(a3, v14 + 9);
      if ( DefaultNativeConfigurationSystem >= 0 )
      {
        DefaultNativeConfigurationSystem = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *, __int64 *, __int64 *, _QWORD))(**((_QWORD **)v4 + 24) + 24LL))(
                                             *((_QWORD *)v4 + 24),
                                             L"system.applicationHost/applicationPools",
                                             L"MACHINE/WEBROOT/APPHOST",
                                             &v30,
                                             &v26,
                                             0);
        if ( DefaultNativeConfigurationSystem >= 0 )
        {
          DefaultNativeConfigurationSystem = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v30 + 40LL))(
                                               v30,
                                               &v27);
          if ( DefaultNativeConfigurationSystem >= 0 )
          {
            DefaultNativeConfigurationSystem = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v27 + 24LL))(
                                                 v27,
                                                 &v28);
            if ( DefaultNativeConfigurationSystem >= 0 )
            {
              if ( ::Source && *::Source )
              {
                DefaultNativeConfigurationSystem = AllocAndCopyString(::Source, v14 + 3);
                if ( DefaultNativeConfigurationSystem < 0 )
                  goto LABEL_41;
                v15 = v24;
                for ( i = 0; i < v28; ++i )
                {
                  DefaultNativeConfigurationSystem = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v27 + 32LL))(
                                                       v27,
                                                       i,
                                                       &v24);
                  if ( DefaultNativeConfigurationSystem < 0 )
                    goto LABEL_41;
                  DefaultNativeConfigurationSystem = (*(__int64 (__fastcall **)(__int64, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v24 + 64LL))(
                                                       v24,
                                                       L"name",
                                                       &String1,
                                                       0,
                                                       0);
                  if ( DefaultNativeConfigurationSystem < 0 )
                    goto LABEL_41;
                  if ( !_wcsicmp(String1, v14[3]) )
                    goto LABEL_37;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
                  v15 = 0;
                  v24 = 0;
                }
              }
              else
              {
                DefaultNativeConfigurationSystem = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v27 + 32LL))(
                                                     v27,
                                                     0,
                                                     &v24);
                if ( DefaultNativeConfigurationSystem < 0 )
                  goto LABEL_41;
                DefaultNativeConfigurationSystem = (*(__int64 (__fastcall **)(__int64, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v24 + 64LL))(
                                                     v24,
                                                     L"name",
                                                     &Source,
                                                     0,
                                                     0);
                if ( DefaultNativeConfigurationSystem < 0 )
                  goto LABEL_41;
                DefaultNativeConfigurationSystem = AllocAndCopyString(Source, v14 + 3);
                if ( DefaultNativeConfigurationSystem < 0 )
                  goto LABEL_41;
LABEL_37:
                v15 = v24;
              }
              if ( !v15 )
              {
                DefaultNativeConfigurationSystem = -2147020584;
                if ( (g_dwDebugFlags & 0xF) != 0 )
                  PuDbgPrintError(
                    g_pDebug,
                    "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
                    1771,
                    "W3WP_HOST::InitializeHostedConfig",
                    -2147020584,
                    "Worker process application pool not found\n");
                goto LABEL_41;
              }
              DefaultNativeConfigurationSystem = (*(__int64 (__fastcall **)(__int64, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v15 + 64LL))(
                                                   v15,
                                                   L"managedRuntimeVersion",
                                                   &Source,
                                                   0,
                                                   0);
              if ( DefaultNativeConfigurationSystem >= 0 )
              {
                DefaultNativeConfigurationSystem = AllocAndCopyString(Source, v14 + 5);
                if ( DefaultNativeConfigurationSystem >= 0 )
                {
                  DefaultNativeConfigurationSystem = (*(__int64 (__fastcall **)(__int64, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v24 + 64LL))(
                                                       v24,
                                                       L"managedRuntimeLoader",
                                                       &Source,
                                                       0,
                                                       0);
                  if ( DefaultNativeConfigurationSystem >= 0 )
                  {
                    DefaultNativeConfigurationSystem = AllocAndCopyString(Source, v14 + 13);
                    if ( DefaultNativeConfigurationSystem >= 0 )
                    {
                      DefaultNativeConfigurationSystem = (*(__int64 (__fastcall **)(__int64, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v24 + 64LL))(
                                                           v24,
                                                           L"CLRConfigFile",
                                                           &Source,
                                                           0,
                                                           0);
                      if ( DefaultNativeConfigurationSystem >= 0 )
                      {
                        if ( Source && *Source )
                        {
                          DefaultNativeConfigurationSystem = AllocAndCopyString(Source, v14 + 6);
                          if ( DefaultNativeConfigurationSystem < 0 )
                            goto LABEL_41;
                        }
                        else
                        {
                          v14[6] = 0;
                        }
                        DefaultNativeConfigurationSystem = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v24 + 48LL))(
                                                             v24,
                                                             L"managedPipelineMode",
                                                             v14 + 7,
                                                             0,
                                                             0);
                        if ( DefaultNativeConfigurationSystem >= 0 )
                        {
                          if ( v26 )
                          {
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
                            v26 = 0;
                          }
                          *a4 = v14;
                          goto LABEL_69;
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
LABEL_41:
    v17 = v14[5];
    if ( v17 )
    {
      operator delete(v17);
      v14[5] = 0;
    }
    v18 = v14[13];
    if ( v18 )
    {
      operator delete(v18);
      v14[13] = 0;
    }
    v19 = v14[6];
    if ( v19 )
    {
      operator delete(v19);
      v14[6] = 0;
    }
    v20 = v14[8];
    if ( v20 )
    {
      operator delete(v20);
      v14[8] = 0;
    }
    v21 = v14[9];
    if ( v21 )
    {
      operator delete(v21);
      v14[9] = 0;
    }
    v22 = v14[3];
    if ( v22 )
    {
      operator delete(v22);
      v14[3] = 0;
    }
    operator delete(v14);
    goto LABEL_69;
  }
  if ( (g_dwDebugFlags & 3) != 0 )
  {
    v9 = 1602;
    v10 = "Creating config interface failed: 0x%x\n";
LABEL_4:
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
      v9,
      "W3WP_HOST::InitializeHostedConfig",
      v10);
  }
LABEL_69:
  if ( v26 )
  {
    Value = 0;
    v33 = 0;
    v32 = 0;
    (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v26 + 24LL))(v26, &v32);
    (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v26 + 40LL))(v26, (char *)&v32 + 8);
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v26 + 32LL))(v26, &Value);
    _ultow(Value, Buffer, 10);
    v33 = Buffer;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
        1895,
        "W3WP_HOST::InitializeHostedConfig",
        "File Name: %S \nLine number:%S \nError:%S");
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    v26 = 0;
  }
  if ( v24 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    v24 = 0;
  }
  if ( v27 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    v27 = 0;
  }
  if ( v30 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  return (unsigned int)DefaultNativeConfigurationSystem;
}

```

## disassembly

```asm
0x180004ad4  mov     [rsp-8+arg_0], rbx
0x180004ad9  push    rbp
0x180004ada  push    rsi
0x180004adb  push    rdi
0x180004adc  push    r12
0x180004ade  push    r13
0x180004ae0  push    r14
0x180004ae2  push    r15
0x180004ae4  lea     rbp, [rsp-27h]
0x180004ae9  sub     rsp, 0C0h
0x180004af0  mov     rax, cs:__security_cookie
0x180004af7  xor     rax, rsp
0x180004afa  mov     [rbp+57h+var_40], rax
0x180004afe  mov     r15, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x180004b05  xor     r13d, r13d
0x180004b08  mov     [rbp+57h+var_88], r13
0x180004b0c  mov     r12, r9
0x180004b0f  mov     [rbp+57h+var_B0], r13
0x180004b13  mov     rsi, r8
0x180004b16  mov     [rbp+57h+var_A0], r13
0x180004b1a  mov     r14, rdx
0x180004b1d  mov     [rbp+57h+var_98], r13
0x180004b21  mov     [rbp+57h+String1], r13
0x180004b25  mov     [rbp+57h+var_90], r13d
0x180004b29  mov     [rbp+57h+Source], r13
0x180004b2d  call    cs:__imp_?InitializeNativeConfiguration@@YAJXZ; InitializeNativeConfiguration(void)
0x180004b33  mov     edi, eax
0x180004b35  test    eax, eax
0x180004b37  jns     short loc_180004B7C
0x180004b39  test    byte ptr cs:g_dwDebugFlags, 3
0x180004b40  jz      loc_18000508E
0x180004b46  mov     dword ptr [rsp+0F0h+var_C8], eax
0x180004b4a  mov     r8d, 635h
0x180004b50  lea     rax, aCouldNotInitia; "Could not initialize native config read"...
0x180004b57  mov     rcx, cs:g_pDebug
0x180004b5e  lea     r9, aW3wpHostInitia_0; "W3WP_HOST::InitializeHostedConfig"
0x180004b65  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180004b6c  mov     [rsp+0F0h+var_D0], rax
0x180004b71  call    cs:__imp_PuDbgPrint
0x180004b77  jmp     loc_18000508E
0x180004b7c  lea     rcx, [r15+0C0h]
0x180004b83  mov     dword ptr [r15+0B8h], 1
0x180004b8e  call    cs:__imp_?GetDefaultNativeConfigurationSystem@@YAJPEAPEAVINativeConfigurationSystem@@@Z; GetDefaultNativeConfigurationSystem(INativeConfigurationSystem * *)
0x180004b94  mov     edi, eax
0x180004b96  test    eax, eax
0x180004b98  jns     short loc_180004BBA
0x180004b9a  test    byte ptr cs:g_dwDebugFlags, 3
0x180004ba1  jz      loc_18000508E
0x180004ba7  mov     dword ptr [rsp+0F0h+var_C8], eax
0x180004bab  mov     r8d, 642h
0x180004bb1  lea     rax, aCreatingConfig; "Creating config interface failed: 0x%x"...
0x180004bb8  jmp     short loc_180004B57
0x180004bba  test    r14, r14
0x180004bbd  jz      short loc_180004C31
0x180004bbf  cmp     [r14], r13w
0x180004bc3  jz      short loc_180004C31
0x180004bc5  mov     rcx, [r15+0C0h]
0x180004bcc  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180004bd3  mov     r9d, 3
0x180004bd9  mov     r8, r14
0x180004bdc  mov     rax, [rcx]
0x180004bdf  mov     rax, [rax+40h]
0x180004be3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004be8  mov     edi, eax
0x180004bea  test    eax, eax
0x180004bec  jns     short loc_180004C31
0x180004bee  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180004bf5  jz      loc_18000508E
0x180004bfb  lea     rax, aSettingconfigp_0; "SettingConfigPathMapping for applicatio"...
0x180004c02  mov     r8d, 65Eh
0x180004c08  mov     rcx, cs:g_pDebug
0x180004c0f  lea     r9, aW3wpHostInitia_0; "W3WP_HOST::InitializeHostedConfig"
0x180004c16  mov     [rsp+0F0h+var_C8], rax
0x180004c1b  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180004c22  mov     dword ptr [rsp+0F0h+var_D0], edi
0x180004c26  call    cs:__imp_PuDbgPrintError
0x180004c2c  jmp     loc_18000508E
0x180004c31  test    rsi, rsi
0x180004c34  jz      short loc_180004C81
0x180004c36  cmp     [rsi], r13w
0x180004c3a  jz      short loc_180004C81
0x180004c3c  mov     rcx, [r15+0C0h]
0x180004c43  lea     rdx, aMachineWebroot_0; "MACHINE/WEBROOT"
0x180004c4a  mov     r9d, 2
0x180004c50  mov     r8, rsi
0x180004c53  mov     rax, [rcx]
0x180004c56  mov     rax, [rax+40h]
0x180004c5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c5f  mov     edi, eax
0x180004c61  test    eax, eax
0x180004c63  jns     short loc_180004C81
0x180004c65  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180004c6c  jz      loc_18000508E
0x180004c72  lea     rax, aSettingconfigp; "SettingConfigPathMapping for root web.c"...
0x180004c79  mov     r8d, 675h
0x180004c7f  jmp     short loc_180004C08
0x180004c81  mov     edi, 70h ; 'p'
0x180004c86  mov     ecx, edi; Size
0x180004c88  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004c8d  mov     rbx, rax
0x180004c90  test    rax, rax
0x180004c93  jz      loc_180005089
0x180004c99  mov     r8d, edi; Size
0x180004c9c  mov     [rax], r13
0x180004c9f  xor     edx, edx; Val
0x180004ca1  mov     [rax+8], r13
0x180004ca5  mov     rcx, rax; void *
0x180004ca8  mov     [rax+10h], r13d
0x180004cac  mov     [rax+18h], r13
0x180004cb0  mov     [rax+20h], r13
0x180004cb4  mov     [rax+28h], r13
0x180004cb8  mov     [rax+30h], r13
0x180004cbc  mov     [rax+38h], r13d
0x180004cc0  mov     [rax+40h], r13
0x180004cc4  mov     [rax+48h], r13
0x180004cc8  mov     [rax+50h], r13
0x180004ccc  mov     [rax+58h], r13
0x180004cd0  mov     dword ptr [rax+60h], 1
0x180004cd7  mov     [rax+68h], r13
0x180004cdb  call    memset_0
0x180004ce0  lea     rdx, [rbx+40h]; unsigned __int16 **
0x180004ce4  mov     rcx, r14; Source
0x180004ce7  call    ?AllocAndCopyString@@YAJPEBGPEAPEAG@Z; AllocAndCopyString(ushort const *,ushort * *)
0x180004cec  mov     edi, eax
0x180004cee  test    eax, eax
0x180004cf0  js      loc_180004EEB
0x180004cf6  lea     rdx, [rbx+48h]; unsigned __int16 **
0x180004cfa  mov     rcx, rsi; Source
0x180004cfd  call    ?AllocAndCopyString@@YAJPEBGPEAPEAG@Z; AllocAndCopyString(ushort const *,ushort * *)
0x180004d02  mov     edi, eax
0x180004d04  test    eax, eax
0x180004d06  js      loc_180004EEB
0x180004d0c  mov     rcx, [r15+0C0h]
0x180004d13  lea     rdx, [rbp+57h+var_A0]
0x180004d17  mov     [rsp+0F0h+var_C8], r13
0x180004d1c  lea     r9, [rbp+57h+var_88]
0x180004d20  mov     [rsp+0F0h+var_D0], rdx
0x180004d25  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180004d2c  lea     rdx, aSystemApplicat_1; "system.applicationHost/applicationPools"
0x180004d33  mov     rax, [rcx]
0x180004d36  mov     rax, [rax+18h]
0x180004d3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d3f  mov     edi, eax
0x180004d41  test    eax, eax
0x180004d43  js      loc_180004EEB
0x180004d49  mov     rcx, [rbp+57h+var_88]
0x180004d4d  lea     rdx, [rbp+57h+var_98]
0x180004d51  mov     rax, [rcx]
0x180004d54  mov     rax, [rax+28h]
0x180004d58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d5d  mov     edi, eax
0x180004d5f  test    eax, eax
0x180004d61  js      loc_180004EEB
0x180004d67  mov     rcx, [rbp+57h+var_98]
0x180004d6b  lea     rdx, [rbp+57h+var_90]
0x180004d6f  mov     rax, [rcx]
0x180004d72  mov     rax, [rax+18h]
0x180004d76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d7b  mov     edi, eax
0x180004d7d  test    eax, eax
0x180004d7f  js      loc_180004EEB
0x180004d85  mov     rcx, cs:Source; Source
0x180004d8c  test    rcx, rcx
0x180004d8f  jz      loc_180004E3F
0x180004d95  cmp     [rcx], r13w
0x180004d99  jz      loc_180004E3F
0x180004d9f  lea     rdx, [rbx+18h]; unsigned __int16 **
0x180004da3  call    ?AllocAndCopyString@@YAJPEBGPEAPEAG@Z; AllocAndCopyString(ushort const *,ushort * *)
0x180004da8  mov     edi, eax
0x180004daa  test    eax, eax
0x180004dac  js      loc_180004EEB
0x180004db2  mov     rcx, [rbp+57h+var_B0]
0x180004db6  mov     esi, r13d
0x180004db9  cmp     esi, [rbp+57h+var_90]
0x180004dbc  jnb     loc_180004E9F
0x180004dc2  mov     rcx, [rbp+57h+var_98]
0x180004dc6  lea     r8, [rbp+57h+var_B0]
0x180004dca  mov     edx, esi
0x180004dcc  mov     rax, [rcx]
0x180004dcf  mov     rax, [rax+20h]
0x180004dd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dd8  mov     edi, eax
0x180004dda  test    eax, eax
0x180004ddc  js      loc_180004EEB
0x180004de2  mov     rcx, [rbp+57h+var_B0]
0x180004de6  lea     r8, [rbp+57h+String1]
0x180004dea  xor     r9d, r9d
0x180004ded  mov     [rsp+0F0h+var_D0], r13
0x180004df2  lea     rdx, aName; "name"
0x180004df9  mov     rax, [rcx]
0x180004dfc  mov     rax, [rax+40h]
0x180004e00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e05  mov     edi, eax
0x180004e07  test    eax, eax
0x180004e09  js      loc_180004EEB
0x180004e0f  mov     rdx, [rbx+18h]; String2
0x180004e13  mov     rcx, [rbp+57h+String1]; String1
0x180004e17  call    cs:__imp__wcsicmp
0x180004e1d  test    eax, eax
0x180004e1f  jz      short loc_180004E9B
0x180004e21  mov     rcx, [rbp+57h+var_B0]
0x180004e25  mov     rax, [rcx]
0x180004e28  mov     rax, [rax+10h]
0x180004e2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e31  mov     rcx, r13
0x180004e34  inc     esi
0x180004e36  mov     [rbp+57h+var_B0], rcx
0x180004e3a  jmp     loc_180004DB9
0x180004e3f  mov     rcx, [rbp+57h+var_98]
0x180004e43  lea     r8, [rbp+57h+var_B0]
0x180004e47  xor     edx, edx
0x180004e49  mov     rax, [rcx]
0x180004e4c  mov     rax, [rax+20h]
0x180004e50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e55  mov     edi, eax
0x180004e57  test    eax, eax
0x180004e59  js      loc_180004EEB
0x180004e5f  mov     rcx, [rbp+57h+var_B0]
0x180004e63  lea     r8, [rbp+57h+Source]
0x180004e67  xor     r9d, r9d
0x180004e6a  mov     [rsp+0F0h+var_D0], r13
0x180004e6f  lea     rdx, aName; "name"
0x180004e76  mov     rax, [rcx]
0x180004e79  mov     rax, [rax+40h]
0x180004e7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e82  mov     edi, eax
0x180004e84  test    eax, eax
0x180004e86  js      short loc_180004EEB
0x180004e88  mov     rcx, [rbp+57h+Source]; Source
0x180004e8c  lea     rdx, [rbx+18h]; unsigned __int16 **
0x180004e90  call    ?AllocAndCopyString@@YAJPEBGPEAPEAG@Z; AllocAndCopyString(ushort const *,ushort * *)
0x180004e95  mov     edi, eax
0x180004e97  test    eax, eax
0x180004e99  js      short loc_180004EEB
0x180004e9b  mov     rcx, [rbp+57h+var_B0]
0x180004e9f  test    rcx, rcx
0x180004ea2  jnz     loc_180004F64
0x180004ea8  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180004eaf  mov     edi, 800710D8h
0x180004eb4  jz      short loc_180004EEB
0x180004eb6  mov     rcx, cs:g_pDebug
0x180004ebd  lea     rax, aWorkerProcessA; "Worker process application pool not fou"...
0x180004ec4  mov     [rsp+0F0h+var_C8], rax
0x180004ec9  lea     r9, aW3wpHostInitia_0; "W3WP_HOST::InitializeHostedConfig"
0x180004ed0  mov     r8d, 6EBh
0x180004ed6  mov     dword ptr [rsp+0F0h+var_D0], 800710D8h
0x180004ede  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180004ee5  call    cs:__imp_PuDbgPrintError
0x180004eeb  mov     rcx, [rbx+28h]; Block
0x180004eef  test    rcx, rcx
0x180004ef2  jz      short loc_180004EFD
0x180004ef4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004ef9  mov     [rbx+28h], r13
0x180004efd  mov     rcx, [rbx+68h]; Block
0x180004f01  test    rcx, rcx
0x180004f04  jz      short loc_180004F0F
0x180004f06  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004f0b  mov     [rbx+68h], r13
0x180004f0f  mov     rcx, [rbx+30h]; Block
0x180004f13  test    rcx, rcx
0x180004f16  jz      short loc_180004F21
0x180004f18  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004f1d  mov     [rbx+30h], r13
0x180004f21  mov     rcx, [rbx+40h]; Block
0x180004f25  test    rcx, rcx
0x180004f28  jz      short loc_180004F33
0x180004f2a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004f2f  mov     [rbx+40h], r13
0x180004f33  mov     rcx, [rbx+48h]; Block
0x180004f37  test    rcx, rcx
0x180004f3a  jz      short loc_180004F45
0x180004f3c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004f41  mov     [rbx+48h], r13
0x180004f45  mov     rcx, [rbx+18h]; Block
0x180004f49  test    rcx, rcx
0x180004f4c  jz      short loc_180004F57
0x180004f4e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004f53  mov     [rbx+18h], r13
0x180004f57  mov     rcx, rbx; Block
0x180004f5a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004f5f  jmp     loc_18000508E
0x180004f64  mov     rax, [rcx]
0x180004f67  lea     r8, [rbp+57h+Source]
0x180004f6b  xor     r9d, r9d
0x180004f6e  mov     [rsp+0F0h+var_D0], r13
0x180004f73  lea     rdx, aManagedruntime_0; "managedRuntimeVersion"
0x180004f7a  mov     rax, [rax+40h]
0x180004f7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f83  mov     edi, eax
0x180004f85  test    eax, eax
0x180004f87  js      loc_180004EEB
0x180004f8d  mov     rcx, [rbp+57h+Source]; Source
0x180004f91  lea     rdx, [rbx+28h]; unsigned __int16 **
0x180004f95  call    ?AllocAndCopyString@@YAJPEBGPEAPEAG@Z; AllocAndCopyString(ushort const *,ushort * *)
0x180004f9a  mov     edi, eax
0x180004f9c  test    eax, eax
0x180004f9e  js      loc_180004EEB
0x180004fa4  mov     rcx, [rbp+57h+var_B0]
0x180004fa8  lea     r8, [rbp+57h+Source]
0x180004fac  xor     r9d, r9d
  ... truncated ...
```
