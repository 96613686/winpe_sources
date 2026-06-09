# W3WP_HOST::InitializeHostedConfig(ushort const *,ushort const *,APPHOST_CONFIG * *)

- ea: `0x180004ee4`
- end: `0x180005615`
- name: `?InitializeHostedConfig@W3WP_HOST@@QEAAJPEBG0PEAPEAUAPPHOST_CONFIG@@@Z`
- size: `1841`
- prototype: `__int64 __fastcall(W3WP_HOST *this, wchar_t *, wchar_t *, unsigned __int16 ***)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180004b20`

## callees

- `0x180002090`
- `0x1800020d0`
- `0x1800034ac`
- `0x180004ee4`
- `0x18000d2be`
- `0x18000d2f0`
- `0x18000e010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000523f`
- `msvcrt!_wcsicmp` at `0x18000523f`
- `msvcrt!_ultow` at `0x180005525`
- `msvcrt!_ultow` at `0x180005525`
- `iisutil!PuDbgPrint` at `0x180004f87`
- `iisutil!PuDbgPrint` at `0x180005584`
- `iisutil!PuDbgPrint` at `0x180004f87`
- `iisutil!PuDbgPrint` at `0x180005584`
- `iisutil!PuDbgPrintError` at `0x180005048`
- `iisutil!PuDbgPrintError` at `0x180005313`
- `iisutil!PuDbgPrintError` at `0x180005048`
- `iisutil!PuDbgPrintError` at `0x180005313`
- `nativerd!GetDefaultNativeConfigurationSystem` at `0x180004faa`
- `nativerd!GetDefaultNativeConfigurationSystem` at `0x180004faa`
- `nativerd!InitializeNativeConfiguration` at `0x180004f3d`
- `nativerd!InitializeNativeConfiguration` at `0x180004f3d`

## string_xrefs

- `0x180004f7b`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x18000503d`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x18000530c`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x180005554`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\w3wphost.cxx`
- `0x180004f66`: `Could not initialize native config reader 0x%x\n`
- `0x180004f74`: `W3WP_HOST::InitializeHostedConfig`
- `0x180005031`: `W3WP_HOST::InitializeHostedConfig`
- `0x1800052f7`: `W3WP_HOST::InitializeHostedConfig`
- `0x180005546`: `W3WP_HOST::InitializeHostedConfig`
- `0x180004fd3`: `Creating config interface failed: 0x%x\n`
- `0x18000501d`: `SettingConfigPathMapping for applicationhost.config failed\n`
- `0x18000509a`: `SettingConfigPathMapping for root web.config failed\n`
- `0x18000542c`: `CLRConfigFile`

## pseudocode

```c
__int64 __fastcall W3WP_HOST::InitializeHostedConfig(W3WP_HOST *this, wchar_t *a2, wchar_t *a3, unsigned __int16 ***a4)
{
  W3WP_HOST *v4; // r15
  int v8; // eax
  int v9; // edi
  int DefaultNativeConfigurationSystem; // eax
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
  v8 = InitializeNativeConfiguration();
  v9 = v8;
  if ( v8 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
        1589,
        "W3WP_HOST::InitializeHostedConfig",
        "Could not initialize native config reader 0x%x\n",
        v8);
    goto LABEL_69;
  }
  *((_DWORD *)v4 + 46) = 1;
  DefaultNativeConfigurationSystem = GetDefaultNativeConfigurationSystem((struct INativeConfigurationSystem **)v4 + 24);
  v9 = DefaultNativeConfigurationSystem;
  if ( DefaultNativeConfigurationSystem < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\w3wphost.cxx",
        1602,
        "W3WP_HOST::InitializeHostedConfig",
        "Creating config interface failed: 0x%x\n",
        DefaultNativeConfigurationSystem);
    goto LABEL_69;
  }
  if ( a2 )
  {
    if ( *a2 )
    {
      v9 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, wchar_t *, __int64))(**((_QWORD **)v4 + 24) + 64LL))(
             *((_QWORD *)v4 + 24),
             L"MACHINE/WEBROOT/APPHOST",
             a2,
             3);
      if ( v9 < 0 )
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
      v9 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, wchar_t *, __int64))(**((_QWORD **)v4 + 24) + 64LL))(
             *((_QWORD *)v4 + 24),
             L"MACHINE/WEBROOT",
             a3,
             2);
      if ( v9 < 0 )
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
          v9,
          v11);
        goto LABEL_69;
      }
    }
  }
  v13 = (unsigned __int16 **)operator new(0x70u);
  v14 = v13;
  if ( !v13 )
  {
    v9 = -2147024882;
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
  v9 = AllocAndCopyString(a2, v14 + 8);
  if ( v9 < 0 )
    goto LABEL_41;
  v9 = AllocAndCopyString(a3, v14 + 9);
  if ( v9 < 0 )
    goto LABEL_41;
  v9 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *, __int64 *, __int64 *, _QWORD))(**((_QWORD **)v4 + 24) + 24LL))(
         *((_QWORD *)v4 + 24),
         L"system.applicationHost/applicationPools",
         L"MACHINE/WEBROOT/APPHOST",
         &v30,
         &v26,
         0);
  if ( v9 < 0 )
    goto LABEL_41;
  v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v30 + 40LL))(v30, &v27);
  if ( v9 < 0 )
    goto LABEL_41;
  v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v27 + 24LL))(v27, &v28);
  if ( v9 < 0 )
    goto LABEL_41;
  if ( ::Source && *::Source )
  {
    v9 = AllocAndCopyString(::Source, v14 + 3);
    if ( v9 < 0 )
      goto LABEL_41;
    v15 = v24;
    for ( i = 0; i < v28; ++i )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v27 + 32LL))(v27, i, &v24);
      if ( v9 < 0 )
        goto LABEL_41;
      v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v24 + 64LL))(
             v24,
             L"name",
             &String1,
             0,
             0);
      if ( v9 < 0 )
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
    v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v27 + 32LL))(v27, 0, &v24);
    if ( v9 < 0 )
      goto LABEL_41;
    v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v24 + 64LL))(
           v24,
           L"name",
           &Source,
           0,
           0);
    if ( v9 < 0 )
      goto LABEL_41;
    v9 = AllocAndCopyString(Source, v14 + 3);
    if ( v9 < 0 )
      goto LABEL_41;
LABEL_37:
    v15 = v24;
  }
  if ( !v15 )
  {
    v9 = -2147020584;
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
  v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v15 + 64LL))(
         v15,
         L"managedRuntimeVersion",
         &Source,
         0,
         0);
  if ( v9 < 0 )
    goto LABEL_41;
  v9 = AllocAndCopyString(Source, v14 + 5);
  if ( v9 < 0 )
    goto LABEL_41;
  v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v24 + 64LL))(
         v24,
         L"managedRuntimeLoader",
         &Source,
         0,
         0);
  if ( v9 < 0 )
    goto LABEL_41;
  v9 = AllocAndCopyString(Source, v14 + 13);
  if ( v9 < 0 )
    goto LABEL_41;
  v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v24 + 64LL))(
         v24,
         L"CLRConfigFile",
         &Source,
         0,
         0);
  if ( v9 < 0 )
    goto LABEL_41;
  if ( !Source || !*Source )
  {
    v14[6] = 0;
    goto LABEL_64;
  }
  v9 = AllocAndCopyString(Source, v14 + 6);
  if ( v9 < 0 )
  {
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
LABEL_64:
  v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v24 + 48LL))(
         v24,
         L"managedPipelineMode",
         v14 + 7,
         0,
         0);
  if ( v9 < 0 )
    goto LABEL_41;
  if ( v26 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    v26 = 0;
  }
  *a4 = v14;
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
        "File Name: %S \nLine number:%S \nError:%S",
        *((const wchar_t **)&v32 + 1),
        Buffer,
        (const wchar_t *)v32);
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
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180004ee4  mov     [rsp-8+arg_0], rbx
0x180004ee9  push    rbp
0x180004eea  push    rsi
0x180004eeb  push    rdi
0x180004eec  push    r12
0x180004eee  push    r13
0x180004ef0  push    r14
0x180004ef2  push    r15
0x180004ef4  lea     rbp, [rsp-27h]
0x180004ef9  sub     rsp, 0C0h
0x180004f00  mov     rax, cs:__security_cookie
0x180004f07  xor     rax, rsp
0x180004f0a  mov     [rbp+57h+var_40], rax
0x180004f0e  mov     r15, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x180004f15  xor     r13d, r13d
0x180004f18  mov     [rbp+57h+var_88], r13
0x180004f1c  mov     r12, r9
0x180004f1f  mov     [rbp+57h+var_B0], r13
0x180004f23  mov     rsi, r8
0x180004f26  mov     [rbp+57h+var_A0], r13
0x180004f2a  mov     r14, rdx
0x180004f2d  mov     [rbp+57h+var_98], r13
0x180004f31  mov     [rbp+57h+String1], r13
0x180004f35  mov     [rbp+57h+var_90], r13d
0x180004f39  mov     [rbp+57h+Source], r13
0x180004f3d  call    cs:__imp_?InitializeNativeConfiguration@@YAJXZ; InitializeNativeConfiguration(void)
0x180004f44  nop     dword ptr [rax+rax+00h]
0x180004f49  mov     edi, eax
0x180004f4b  test    eax, eax
0x180004f4d  jns     short loc_180004F98
0x180004f4f  test    byte ptr cs:g_dwDebugFlags, 3
0x180004f56  jz      loc_1800054C2
0x180004f5c  mov     dword ptr [rsp+0F0h+var_C8], eax
0x180004f60  mov     r8d, 635h
0x180004f66  lea     rax, aCouldNotInitia; "Could not initialize native config read"...
0x180004f6d  mov     rcx, cs:g_pDebug
0x180004f74  lea     r9, aW3wpHostInitia_0; "W3WP_HOST::InitializeHostedConfig"
0x180004f7b  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180004f82  mov     [rsp+0F0h+var_D0], rax
0x180004f87  call    cs:__imp_PuDbgPrint
0x180004f8e  nop     dword ptr [rax+rax+00h]
0x180004f93  jmp     loc_1800054C2
0x180004f98  lea     rcx, [r15+0C0h]
0x180004f9f  mov     dword ptr [r15+0B8h], 1
0x180004faa  call    cs:__imp_?GetDefaultNativeConfigurationSystem@@YAJPEAPEAVINativeConfigurationSystem@@@Z; GetDefaultNativeConfigurationSystem(INativeConfigurationSystem * *)
0x180004fb1  nop     dword ptr [rax+rax+00h]
0x180004fb6  mov     edi, eax
0x180004fb8  test    eax, eax
0x180004fba  jns     short loc_180004FDC
0x180004fbc  test    byte ptr cs:g_dwDebugFlags, 3
0x180004fc3  jz      loc_1800054C2
0x180004fc9  mov     dword ptr [rsp+0F0h+var_C8], eax
0x180004fcd  mov     r8d, 642h
0x180004fd3  lea     rax, aCreatingConfig; "Creating config interface failed: 0x%x"...
0x180004fda  jmp     short loc_180004F6D
0x180004fdc  test    r14, r14
0x180004fdf  jz      short loc_180005059
0x180004fe1  cmp     [r14], r13w
0x180004fe5  jz      short loc_180005059
0x180004fe7  mov     rcx, [r15+0C0h]
0x180004fee  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180004ff5  mov     r9d, 3
0x180004ffb  mov     r8, r14
0x180004ffe  mov     rax, [rcx]
0x180005001  mov     rax, [rax+40h]
0x180005005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000500a  mov     edi, eax
0x18000500c  test    eax, eax
0x18000500e  jns     short loc_180005059
0x180005010  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180005017  jz      loc_1800054C2
0x18000501d  lea     rax, aSettingconfigp_0; "SettingConfigPathMapping for applicatio"...
0x180005024  mov     r8d, 65Eh
0x18000502a  mov     rcx, cs:g_pDebug
0x180005031  lea     r9, aW3wpHostInitia_0; "W3WP_HOST::InitializeHostedConfig"
0x180005038  mov     [rsp+0F0h+var_C8], rax
0x18000503d  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180005044  mov     dword ptr [rsp+0F0h+var_D0], edi
0x180005048  call    cs:__imp_PuDbgPrintError
0x18000504f  nop     dword ptr [rax+rax+00h]
0x180005054  jmp     loc_1800054C2
0x180005059  test    rsi, rsi
0x18000505c  jz      short loc_1800050A9
0x18000505e  cmp     [rsi], r13w
0x180005062  jz      short loc_1800050A9
0x180005064  mov     rcx, [r15+0C0h]
0x18000506b  lea     rdx, aMachineWebroot_0; "MACHINE/WEBROOT"
0x180005072  mov     r9d, 2
0x180005078  mov     r8, rsi
0x18000507b  mov     rax, [rcx]
0x18000507e  mov     rax, [rax+40h]
0x180005082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005087  mov     edi, eax
0x180005089  test    eax, eax
0x18000508b  jns     short loc_1800050A9
0x18000508d  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180005094  jz      loc_1800054C2
0x18000509a  lea     rax, aSettingconfigp; "SettingConfigPathMapping for root web.c"...
0x1800050a1  mov     r8d, 675h
0x1800050a7  jmp     short loc_18000502A
0x1800050a9  mov     edi, 70h ; 'p'
0x1800050ae  mov     ecx, edi; Size
0x1800050b0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800050b5  mov     rbx, rax
0x1800050b8  test    rax, rax
0x1800050bb  jz      loc_1800054BD
0x1800050c1  mov     r8d, edi; Size
0x1800050c4  mov     [rax], r13
0x1800050c7  xor     edx, edx; Val
0x1800050c9  mov     [rax+8], r13
0x1800050cd  mov     rcx, rax; void *
0x1800050d0  mov     [rax+10h], r13d
0x1800050d4  mov     [rax+18h], r13
0x1800050d8  mov     [rax+20h], r13
0x1800050dc  mov     [rax+28h], r13
0x1800050e0  mov     [rax+30h], r13
0x1800050e4  mov     [rax+38h], r13d
0x1800050e8  mov     [rax+40h], r13
0x1800050ec  mov     [rax+48h], r13
0x1800050f0  mov     [rax+50h], r13
0x1800050f4  mov     [rax+58h], r13
0x1800050f8  mov     dword ptr [rax+60h], 1
0x1800050ff  mov     [rax+68h], r13
0x180005103  call    memset_0
0x180005108  lea     rdx, [rbx+40h]; unsigned __int16 **
0x18000510c  mov     rcx, r14; Source
0x18000510f  call    ?AllocAndCopyString@@YAJPEBGPEAPEAG@Z; AllocAndCopyString(ushort const *,ushort * *)
0x180005114  mov     edi, eax
0x180005116  test    eax, eax
0x180005118  js      loc_18000531F
0x18000511e  lea     rdx, [rbx+48h]; unsigned __int16 **
0x180005122  mov     rcx, rsi; Source
0x180005125  call    ?AllocAndCopyString@@YAJPEBGPEAPEAG@Z; AllocAndCopyString(ushort const *,ushort * *)
0x18000512a  mov     edi, eax
0x18000512c  test    eax, eax
0x18000512e  js      loc_18000531F
0x180005134  mov     rcx, [r15+0C0h]
0x18000513b  lea     rdx, [rbp+57h+var_A0]
0x18000513f  mov     [rsp+0F0h+var_C8], r13
0x180005144  lea     r9, [rbp+57h+var_88]
0x180005148  mov     [rsp+0F0h+var_D0], rdx
0x18000514d  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180005154  lea     rdx, aSystemApplicat_1; "system.applicationHost/applicationPools"
0x18000515b  mov     rax, [rcx]
0x18000515e  mov     rax, [rax+18h]
0x180005162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005167  mov     edi, eax
0x180005169  test    eax, eax
0x18000516b  js      loc_18000531F
0x180005171  mov     rcx, [rbp+57h+var_88]
0x180005175  lea     rdx, [rbp+57h+var_98]
0x180005179  mov     rax, [rcx]
0x18000517c  mov     rax, [rax+28h]
0x180005180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005185  mov     edi, eax
0x180005187  test    eax, eax
0x180005189  js      loc_18000531F
0x18000518f  mov     rcx, [rbp+57h+var_98]
0x180005193  lea     rdx, [rbp+57h+var_90]
0x180005197  mov     rax, [rcx]
0x18000519a  mov     rax, [rax+18h]
0x18000519e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051a3  mov     edi, eax
0x1800051a5  test    eax, eax
0x1800051a7  js      loc_18000531F
0x1800051ad  mov     rcx, cs:Source; Source
0x1800051b4  test    rcx, rcx
0x1800051b7  jz      loc_18000526D
0x1800051bd  cmp     [rcx], r13w
0x1800051c1  jz      loc_18000526D
0x1800051c7  lea     rdx, [rbx+18h]; unsigned __int16 **
0x1800051cb  call    ?AllocAndCopyString@@YAJPEBGPEAPEAG@Z; AllocAndCopyString(ushort const *,ushort * *)
0x1800051d0  mov     edi, eax
0x1800051d2  test    eax, eax
0x1800051d4  js      loc_18000531F
0x1800051da  mov     rcx, [rbp+57h+var_B0]
0x1800051de  mov     esi, r13d
0x1800051e1  cmp     esi, [rbp+57h+var_90]
0x1800051e4  jnb     loc_1800052CD
0x1800051ea  mov     rcx, [rbp+57h+var_98]
0x1800051ee  lea     r8, [rbp+57h+var_B0]
0x1800051f2  mov     edx, esi
0x1800051f4  mov     rax, [rcx]
0x1800051f7  mov     rax, [rax+20h]
0x1800051fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005200  mov     edi, eax
0x180005202  test    eax, eax
0x180005204  js      loc_18000531F
0x18000520a  mov     rcx, [rbp+57h+var_B0]
0x18000520e  lea     r8, [rbp+57h+String1]
0x180005212  xor     r9d, r9d
0x180005215  mov     [rsp+0F0h+var_D0], r13
0x18000521a  lea     rdx, aName; "name"
0x180005221  mov     rax, [rcx]
0x180005224  mov     rax, [rax+40h]
0x180005228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000522d  mov     edi, eax
0x18000522f  test    eax, eax
0x180005231  js      loc_18000531F
0x180005237  mov     rdx, [rbx+18h]; String2
0x18000523b  mov     rcx, [rbp+57h+String1]; String1
0x18000523f  call    cs:__imp__wcsicmp
0x180005246  nop     dword ptr [rax+rax+00h]
0x18000524b  test    eax, eax
0x18000524d  jz      short loc_1800052C9
0x18000524f  mov     rcx, [rbp+57h+var_B0]
0x180005253  mov     rax, [rcx]
0x180005256  mov     rax, [rax+10h]
0x18000525a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000525f  mov     rcx, r13
0x180005262  inc     esi
0x180005264  mov     [rbp+57h+var_B0], rcx
0x180005268  jmp     loc_1800051E1
0x18000526d  mov     rcx, [rbp+57h+var_98]
0x180005271  lea     r8, [rbp+57h+var_B0]
0x180005275  xor     edx, edx
0x180005277  mov     rax, [rcx]
0x18000527a  mov     rax, [rax+20h]
0x18000527e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005283  mov     edi, eax
0x180005285  test    eax, eax
0x180005287  js      loc_18000531F
0x18000528d  mov     rcx, [rbp+57h+var_B0]
0x180005291  lea     r8, [rbp+57h+Source]
0x180005295  xor     r9d, r9d
0x180005298  mov     [rsp+0F0h+var_D0], r13
0x18000529d  lea     rdx, aName; "name"
0x1800052a4  mov     rax, [rcx]
0x1800052a7  mov     rax, [rax+40h]
0x1800052ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052b0  mov     edi, eax
0x1800052b2  test    eax, eax
0x1800052b4  js      short loc_18000531F
0x1800052b6  mov     rcx, [rbp+57h+Source]; Source
0x1800052ba  lea     rdx, [rbx+18h]; unsigned __int16 **
0x1800052be  call    ?AllocAndCopyString@@YAJPEBGPEAPEAG@Z; AllocAndCopyString(ushort const *,ushort * *)
0x1800052c3  mov     edi, eax
0x1800052c5  test    eax, eax
0x1800052c7  js      short loc_18000531F
0x1800052c9  mov     rcx, [rbp+57h+var_B0]
0x1800052cd  test    rcx, rcx
0x1800052d0  jnz     loc_180005398
0x1800052d6  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800052dd  mov     edi, 800710D8h
0x1800052e2  jz      short loc_18000531F
0x1800052e4  mov     rcx, cs:g_pDebug
0x1800052eb  lea     rax, aWorkerProcessA; "Worker process application pool not fou"...
0x1800052f2  mov     [rsp+0F0h+var_C8], rax
0x1800052f7  lea     r9, aW3wpHostInitia_0; "W3WP_HOST::InitializeHostedConfig"
0x1800052fe  mov     r8d, 6EBh
0x180005304  mov     dword ptr [rsp+0F0h+var_D0], 800710D8h
0x18000530c  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180005313  call    cs:__imp_PuDbgPrintError
0x18000531a  nop     dword ptr [rax+rax+00h]
0x18000531f  mov     rcx, [rbx+28h]; Block
0x180005323  test    rcx, rcx
0x180005326  jz      short loc_180005331
0x180005328  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000532d  mov     [rbx+28h], r13
0x180005331  mov     rcx, [rbx+68h]; Block
0x180005335  test    rcx, rcx
0x180005338  jz      short loc_180005343
0x18000533a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000533f  mov     [rbx+68h], r13
0x180005343  mov     rcx, [rbx+30h]; Block
0x180005347  test    rcx, rcx
0x18000534a  jz      short loc_180005355
0x18000534c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005351  mov     [rbx+30h], r13
0x180005355  mov     rcx, [rbx+40h]; Block
0x180005359  test    rcx, rcx
0x18000535c  jz      short loc_180005367
0x18000535e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005363  mov     [rbx+40h], r13
0x180005367  mov     rcx, [rbx+48h]; Block
0x18000536b  test    rcx, rcx
0x18000536e  jz      short loc_180005379
0x180005370  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005375  mov     [rbx+48h], r13
0x180005379  mov     rcx, [rbx+18h]; Block
0x18000537d  test    rcx, rcx
0x180005380  jz      short loc_18000538B
0x180005382  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005387  mov     [rbx+18h], r13
0x18000538b  mov     rcx, rbx; Block
0x18000538e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005393  jmp     loc_1800054C2
0x180005398  mov     rax, [rcx]
0x18000539b  lea     r8, [rbp+57h+Source]
0x18000539f  xor     r9d, r9d
0x1800053a2  mov     [rsp+0F0h+var_D0], r13
0x1800053a7  lea     rdx, aManagedruntime_0; "managedRuntimeVersion"
0x1800053ae  mov     rax, [rax+40h]
0x1800053b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053b7  mov     edi, eax
0x1800053b9  test    eax, eax
0x1800053bb  js      loc_18000531F
0x1800053c1  mov     rcx, [rbp+57h+Source]; Source
0x1800053c5  lea     rdx, [rbx+28h]; unsigned __int16 **
0x1800053c9  call    ?AllocAndCopyString@@YAJPEBGPEAPEAG@Z; AllocAndCopyString(ushort const *,ushort * *)
  ... truncated ...
```
