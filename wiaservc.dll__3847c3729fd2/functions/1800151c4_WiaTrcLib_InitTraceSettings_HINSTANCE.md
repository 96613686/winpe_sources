# WiaTrcLib::InitTraceSettings(HINSTANCE__ *)

- ea: `0x1800151c4`
- end: `0x180015516`
- name: `?InitTraceSettings@WiaTrcLib@@YAJPEAUHINSTANCE__@@@Z`
- size: `850`
- prototype: `__int64 __fastcall(WiaTrcLib *__hidden this, HINSTANCE)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800767cc`

## callees

- `0x1800151c4`
- `0x18001551c`
- `0x1800156e0`
- `0x18002fa8c`
- `0x1800301f8`
- `0x180033cc0`
- `0x180034658`
- `0x180076084`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__splitpath_s` at `0x18001526f`
- `api-ms-win-crt-private-l1-1-0!_o__splitpath_s` at `0x18001526f`
- `ADVAPI32!RegCloseKey` at `0x1800154e2`
- `ADVAPI32!RegCloseKey` at `0x1800154f2`
- `ADVAPI32!RegCloseKey` at `0x1800154e2`
- `ADVAPI32!RegCloseKey` at `0x1800154f2`
- `ADVAPI32!RegQueryValueExW` at `0x1800152f0`
- `ADVAPI32!RegQueryValueExW` at `0x1800152f0`
- `ADVAPI32!RegSetValueExW` at `0x180015313`
- `ADVAPI32!RegSetValueExW` at `0x180015313`

## pseudocode

```c
__int64 __fastcall WiaTrcLib::InitTraceSettings(WiaTrcLib *this, HINSTANCE a2)
{
  WiaTrcLib *v2; // rcx
  char *v3; // r8
  int v4; // r9d
  WiaTrcLib *v5; // rcx
  HKEY *v6; // r9
  HKEY v7; // rdx
  unsigned int TracingKeys; // ebx
  unsigned int *v9; // r9
  int v10; // eax
  HKEY v11; // rbx
  unsigned int *v12; // r9
  unsigned int *v13; // r9
  unsigned int *v14; // r9
  unsigned int *v15; // r9
  unsigned int *v16; // r9
  unsigned int *v17; // r9
  int DirCount; // [rsp+20h] [rbp-E0h]
  int DirCounta; // [rsp+20h] [rbp-E0h]
  int DirCountb; // [rsp+20h] [rbp-E0h]
  int DirCountc; // [rsp+20h] [rbp-E0h]
  int DirCountd; // [rsp+20h] [rbp-E0h]
  int DirCounte; // [rsp+20h] [rbp-E0h]
  int DirCountf; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v27; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cbData; // [rsp+60h] [rbp-A0h] BYREF
  DWORD Type[3]; // [rsp+64h] [rbp-9Ch] BYREF
  char Ext[272]; // [rsp+70h] [rbp-90h] BYREF
  struct HINSTANCE__ FullPath[68]; // [rsp+180h] [rbp+80h] BYREF

  memset_0(FullPath, 0, 0x105u);
  hKey = 0;
  v27 = 0;
  memset_0(Ext, 0, 0x101u);
  g_WiaTrace_hModuleInstance = (__int64)WiaTrcLib::GetModuleNameAndInstance(v2, FullPath, v3, v4);
  _splitpath_s((const char *)FullPath, 0, 0, 0, 0, g_WiaTrace_szModuleName, 0x105u, Ext, 0x101u);
  StringCchCatA(g_WiaTrace_szModuleName, 0x105u, Ext);
  TracingKeys = WiaTrcLib::GetTracingKeys(v5, (char *)&hKey, &v27, v6);
  if ( !TracingKeys )
  {
    v10 = WiaTrcLib::SuppressOutputForThisProcess(hKey, v7);
    v11 = hKey;
    g_WiaTrace_bSuppressProcessOutput = v10;
    if ( hKey )
    {
      Type[0] = 4;
      cbData = 4;
      if ( RegQueryValueExW(hKey, L"MaxFileSize", 0, Type, &g_WiaTrace_ulMaxFileSize, &cbData) )
        RegSetValueExW(v11, L"MaxFileSize", 0, 4u, &g_WiaTrace_ulMaxFileSize, 4u);
      TracingKeys = WiaTrcLib::ReadRegValueDWORD(
                      hKey,
                      (HKEY)&stru_1800A1968,
                      &WiaTrcLib::g_WiaTrc_ulDefaultFlags,
                      v12,
                      DirCounta);
      if ( !TracingKeys )
      {
        TracingKeys = WiaTrcLib::ReadRegValueDWORD(
                        hKey,
                        (HKEY)&stru_1800A1A78,
                        &WiaTrcLib::g_WiaTrc_ulDefaultTraceMask,
                        v9,
                        DirCount);
        if ( !TracingKeys )
        {
          TracingKeys = WiaTrcLib::ReadRegValueDWORD(
                          hKey,
                          (HKEY)&stru_1800A1A50,
                          &WiaTrcLib::g_WiaTrc_ulDefaultTraceLevel,
                          v9,
                          DirCount);
          if ( !TracingKeys )
          {
            TracingKeys = WiaTrcLib::ReadRegValueDWORD(
                            hKey,
                            (HKEY)&stru_1800A1A18,
                            &WiaTrcLib::g_WiaTrc_ulDefaultTraceArraySize,
                            v9,
                            DirCount);
            if ( !TracingKeys )
            {
              TracingKeys = WiaTrcLib::ReadRegValueDWORD(
                              hKey,
                              (HKEY)&stru_1800A19E0,
                              &WiaTrcLib::g_WiaTrc_bDefaultEnableObjectTracking,
                              v9,
                              DirCount);
              if ( !TracingKeys )
                TracingKeys = WiaTrcLib::ReadRegValueDWORD(
                                hKey,
                                (HKEY)&stru_1800A1AE8,
                                &WiaTrcLib::g_WiaTrc_ulDefaultHeapOptions,
                                v9,
                                DirCount);
            }
          }
        }
      }
    }
    else
    {
      TracingKeys = -2147467261;
    }
  }
  *(_DWORD *)&g_WiaTrace_ulFlags = *(_DWORD *)&WiaTrcLib::g_WiaTrc_ulDefaultFlags;
  *(_DWORD *)&g_WiaTrace_ulTraceMask = *(_DWORD *)&WiaTrcLib::g_WiaTrc_ulDefaultTraceMask;
  *(_DWORD *)&g_WiaTrace_ulTraceLevel = *(_DWORD *)&WiaTrcLib::g_WiaTrc_ulDefaultTraceLevel;
  *(_DWORD *)&g_WiaTrace_ulTraceArraySize = *(_DWORD *)&WiaTrcLib::g_WiaTrc_ulDefaultTraceArraySize;
  *(_DWORD *)&g_WiaTrace_bEnableObjectTracking = *(_DWORD *)&WiaTrcLib::g_WiaTrc_bDefaultEnableObjectTracking;
  *(_DWORD *)&g_WiaTrace_ulHeapOptions = *(_DWORD *)&WiaTrcLib::g_WiaTrc_ulDefaultHeapOptions;
  if ( !TracingKeys )
  {
    TracingKeys = WiaTrcLib::ReadRegValueDWORD(v27, (HKEY)&stru_1800A1AD0, &g_WiaTrace_ulFlags, v9, DirCount);
    if ( !TracingKeys )
    {
      TracingKeys = WiaTrcLib::ReadRegValueDWORD(v27, (HKEY)&stru_1800A1AB8, &g_WiaTrace_ulTraceMask, v13, DirCountb);
      if ( !TracingKeys )
      {
        TracingKeys = WiaTrcLib::ReadRegValueDWORD(v27, (HKEY)&stru_1800A1AA0, &g_WiaTrace_ulTraceLevel, v14, DirCountc);
        if ( !TracingKeys )
        {
          TracingKeys = WiaTrcLib::ReadRegValueDWORD(
                          v27,
                          (HKEY)&stru_1800A1B90,
                          &g_WiaTrace_ulTraceArraySize,
                          v15,
                          DirCountd);
          if ( !TracingKeys )
          {
            TracingKeys = WiaTrcLib::ReadRegValueDWORD(
                            v27,
                            (HKEY)&stru_1800A1B60,
                            &g_WiaTrace_bEnableObjectTracking,
                            v16,
                            DirCounte);
            if ( !TracingKeys )
              TracingKeys = WiaTrcLib::ReadRegValueDWORD(
                              v27,
                              (HKEY)&stru_1800A1AE8,
                              &g_WiaTrace_ulHeapOptions,
                              v17,
                              DirCountf);
          }
        }
      }
    }
  }
  if ( v27 )
    RegCloseKey(v27);
  if ( hKey )
    RegCloseKey(hKey);
  return TracingKeys;
}

```

## disassembly

```asm
0x1800151c4  push    rbp
0x1800151c6  push    rbx
0x1800151c7  push    rdi
0x1800151c8  push    r14
0x1800151ca  lea     rbp, [rsp-1A8h]
0x1800151d2  sub     rsp, 2A8h
0x1800151d9  mov     rax, cs:__security_cookie
0x1800151e0  xor     rax, rsp
0x1800151e3  mov     [rbp+1C0h+var_30], rax
0x1800151ea  mov     edi, 105h
0x1800151ef  lea     rcx, [rbp+1C0h+FullPath]; void *
0x1800151f6  mov     r8d, edi; Size
0x1800151f9  xor     edx, edx; Val
0x1800151fb  call    memset_0
0x180015200  lea     ebx, [rdi-4]
0x180015203  mov     [rsp+2C0h+hKey], 0
0x18001520c  mov     r8d, ebx; Size
0x18001520f  mov     [rsp+2C0h+var_268], 0
0x180015218  xor     edx, edx; Val
0x18001521a  lea     rcx, [rsp+2C0h+var_250]; void *
0x18001521f  call    memset_0
0x180015224  lea     rdx, [rbp+1C0h+FullPath]; HINSTANCE
0x18001522b  call    ?GetModuleNameAndInstance@WiaTrcLib@@YAPEAUHINSTANCE__@@PEAU2@PEADH@Z; WiaTrcLib::GetModuleNameAndInstance(HINSTANCE__ *,char *,int)
0x180015230  mov     [rsp+2C0h+ExtCount], rbx; ExtCount
0x180015235  lea     rcx, [rbp+1C0h+FullPath]; FullPath
0x18001523c  mov     cs:g_WiaTrace_hModuleInstance, rax
0x180015243  lea     rbx, g_WiaTrace_szModuleName
0x18001524a  lea     rax, [rsp+2C0h+var_250]
0x18001524f  xor     r9d, r9d; Dir
0x180015252  mov     [rsp+2C0h+Ext], rax; Ext
0x180015257  xor     r8d, r8d; DriveCount
0x18001525a  mov     [rsp+2C0h+FilenameCount], rdi; FilenameCount
0x18001525f  xor     edx, edx; Drive
0x180015261  mov     [rsp+2C0h+Filename], rbx; Filename
0x180015266  mov     [rsp+2C0h+DirCount], 0; int
0x18001526f  call    cs:__imp__splitpath_s
0x180015275  lea     r8, [rsp+2C0h+var_250]; char *
0x18001527a  mov     edx, edi; unsigned __int64
0x18001527c  mov     rcx, rbx; char *
0x18001527f  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x180015284  lea     r8, [rsp+2C0h+var_268]; HKEY *
0x180015289  lea     rdx, [rsp+2C0h+hKey]; char *
0x18001528e  call    ?GetTracingKeys@WiaTrcLib@@YAJPEADPEAPEAUHKEY__@@1@Z; WiaTrcLib::GetTracingKeys(char *,HKEY__ * *,HKEY__ * *)
0x180015293  mov     ebx, eax
0x180015295  test    eax, eax
0x180015297  jnz     loc_1800153D4
0x18001529d  mov     rcx, [rsp+2C0h+hKey]; hKey
0x1800152a2  call    ?SuppressOutputForThisProcess@WiaTrcLib@@YAHPEAUHKEY__@@@Z; WiaTrcLib::SuppressOutputForThisProcess(HKEY__ *)
0x1800152a7  mov     rbx, [rsp+2C0h+hKey]
0x1800152ac  mov     cs:g_WiaTrace_bSuppressProcessOutput, eax
0x1800152b2  test    rbx, rbx
0x1800152b5  jz      loc_1800153CF
0x1800152bb  lea     rax, [rsp+2C0h+cbData]
0x1800152c0  mov     edi, 4
0x1800152c5  mov     [rsp+2C0h+Filename], rax; lpcbData
0x1800152ca  lea     r14, g_WiaTrace_ulMaxFileSize
0x1800152d1  lea     r9, [rsp+2C0h+Type]; lpType
0x1800152d6  mov     [rsp+2C0h+DirCount], r14; lpData
0x1800152db  xor     r8d, r8d; lpReserved
0x1800152de  mov     [rsp+2C0h+Type], edi
0x1800152e2  lea     rdx, aMaxfilesize; "MaxFileSize"
0x1800152e9  mov     [rsp+2C0h+cbData], edi
0x1800152ed  mov     rcx, rbx; hKey
0x1800152f0  call    cs:__imp_RegQueryValueExW
0x1800152f6  test    eax, eax
0x1800152f8  jz      short loc_180015319
0x1800152fa  mov     dword ptr [rsp+2C0h+Filename], edi; cbData
0x1800152fe  lea     rdx, aMaxfilesize; "MaxFileSize"
0x180015305  mov     r9d, edi; dwType
0x180015308  mov     [rsp+2C0h+DirCount], r14; int
0x18001530d  xor     r8d, r8d; Reserved
0x180015310  mov     rcx, rbx; hKey
0x180015313  call    cs:__imp_RegSetValueExW
0x180015319  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18001531e  lea     r8, ?g_WiaTrc_ulDefaultFlags@WiaTrcLib@@3KA; lpData
0x180015325  lea     rdx, stru_1800A1968; lpValueName
0x18001532c  call    ?ReadRegValueDWORD@WiaTrcLib@@YAJPEAUHKEY__@@PEAGPEAKH@Z; WiaTrcLib::ReadRegValueDWORD(HKEY__ *,ushort *,ulong *,int)
0x180015331  mov     ebx, eax
0x180015333  test    eax, eax
0x180015335  jnz     loc_1800153D4
0x18001533b  mov     rcx, [rsp+2C0h+hKey]; hKey
0x180015340  lea     r8, ?g_WiaTrc_ulDefaultTraceMask@WiaTrcLib@@3KA; lpData
0x180015347  lea     rdx, stru_1800A1A78; lpValueName
0x18001534e  call    ?ReadRegValueDWORD@WiaTrcLib@@YAJPEAUHKEY__@@PEAGPEAKH@Z; WiaTrcLib::ReadRegValueDWORD(HKEY__ *,ushort *,ulong *,int)
0x180015353  mov     ebx, eax
0x180015355  test    eax, eax
0x180015357  jnz     short loc_1800153D4
0x180015359  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18001535e  lea     r8, ?g_WiaTrc_ulDefaultTraceLevel@WiaTrcLib@@3KA; lpData
0x180015365  lea     rdx, stru_1800A1A50; lpValueName
0x18001536c  call    ?ReadRegValueDWORD@WiaTrcLib@@YAJPEAUHKEY__@@PEAGPEAKH@Z; WiaTrcLib::ReadRegValueDWORD(HKEY__ *,ushort *,ulong *,int)
0x180015371  mov     ebx, eax
0x180015373  test    eax, eax
0x180015375  jnz     short loc_1800153D4
0x180015377  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18001537c  lea     r8, ?g_WiaTrc_ulDefaultTraceArraySize@WiaTrcLib@@3KA; lpData
0x180015383  lea     rdx, stru_1800A1A18; lpValueName
0x18001538a  call    ?ReadRegValueDWORD@WiaTrcLib@@YAJPEAUHKEY__@@PEAGPEAKH@Z; WiaTrcLib::ReadRegValueDWORD(HKEY__ *,ushort *,ulong *,int)
0x18001538f  mov     ebx, eax
0x180015391  test    eax, eax
0x180015393  jnz     short loc_1800153D4
0x180015395  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18001539a  lea     r8, ?g_WiaTrc_bDefaultEnableObjectTracking@WiaTrcLib@@3HA; lpData
0x1800153a1  lea     rdx, stru_1800A19E0; lpValueName
0x1800153a8  call    ?ReadRegValueDWORD@WiaTrcLib@@YAJPEAUHKEY__@@PEAGPEAKH@Z; WiaTrcLib::ReadRegValueDWORD(HKEY__ *,ushort *,ulong *,int)
0x1800153ad  mov     ebx, eax
0x1800153af  test    eax, eax
0x1800153b1  jnz     short loc_1800153D4
0x1800153b3  mov     rcx, [rsp+2C0h+hKey]; hKey
0x1800153b8  lea     r8, ?g_WiaTrc_ulDefaultHeapOptions@WiaTrcLib@@3KA; lpData
0x1800153bf  lea     rdx, stru_1800A1AE8; lpValueName
0x1800153c6  call    ?ReadRegValueDWORD@WiaTrcLib@@YAJPEAUHKEY__@@PEAGPEAKH@Z; WiaTrcLib::ReadRegValueDWORD(HKEY__ *,ushort *,ulong *,int)
0x1800153cb  mov     ebx, eax
0x1800153cd  jmp     short loc_1800153D4
0x1800153cf  mov     ebx, 80004003h
0x1800153d4  mov     eax, cs:?g_WiaTrc_ulDefaultFlags@WiaTrcLib@@3KA; ulong WiaTrcLib::g_WiaTrc_ulDefaultFlags
0x1800153da  mov     cs:g_WiaTrace_ulFlags, eax
0x1800153e0  mov     eax, cs:?g_WiaTrc_ulDefaultTraceMask@WiaTrcLib@@3KA; ulong WiaTrcLib::g_WiaTrc_ulDefaultTraceMask
0x1800153e6  mov     cs:g_WiaTrace_ulTraceMask, eax
0x1800153ec  mov     eax, cs:?g_WiaTrc_ulDefaultTraceLevel@WiaTrcLib@@3KA; ulong WiaTrcLib::g_WiaTrc_ulDefaultTraceLevel
0x1800153f2  mov     cs:g_WiaTrace_ulTraceLevel, eax
0x1800153f8  mov     eax, cs:?g_WiaTrc_ulDefaultTraceArraySize@WiaTrcLib@@3KA; ulong WiaTrcLib::g_WiaTrc_ulDefaultTraceArraySize
0x1800153fe  mov     cs:g_WiaTrace_ulTraceArraySize, eax
0x180015404  mov     eax, cs:?g_WiaTrc_bDefaultEnableObjectTracking@WiaTrcLib@@3HA; int WiaTrcLib::g_WiaTrc_bDefaultEnableObjectTracking
0x18001540a  mov     cs:g_WiaTrace_bEnableObjectTracking, eax
0x180015410  mov     eax, cs:?g_WiaTrc_ulDefaultHeapOptions@WiaTrcLib@@3KA; ulong WiaTrcLib::g_WiaTrc_ulDefaultHeapOptions
0x180015416  mov     cs:g_WiaTrace_ulHeapOptions, eax
0x18001541c  test    ebx, ebx
0x18001541e  jnz     loc_1800154D8
0x180015424  mov     rcx, [rsp+2C0h+var_268]; hKey
0x180015429  lea     r8, g_WiaTrace_ulFlags; lpData
0x180015430  lea     rdx, stru_1800A1AD0; lpValueName
0x180015437  call    ?ReadRegValueDWORD@WiaTrcLib@@YAJPEAUHKEY__@@PEAGPEAKH@Z; WiaTrcLib::ReadRegValueDWORD(HKEY__ *,ushort *,ulong *,int)
0x18001543c  mov     ebx, eax
0x18001543e  test    eax, eax
0x180015440  jnz     loc_1800154D8
0x180015446  mov     rcx, [rsp+2C0h+var_268]; hKey
0x18001544b  lea     r8, g_WiaTrace_ulTraceMask; lpData
0x180015452  lea     rdx, stru_1800A1AB8; lpValueName
0x180015459  call    ?ReadRegValueDWORD@WiaTrcLib@@YAJPEAUHKEY__@@PEAGPEAKH@Z; WiaTrcLib::ReadRegValueDWORD(HKEY__ *,ushort *,ulong *,int)
0x18001545e  mov     ebx, eax
0x180015460  test    eax, eax
0x180015462  jnz     short loc_1800154D8
0x180015464  mov     rcx, [rsp+2C0h+var_268]; hKey
0x180015469  lea     r8, g_WiaTrace_ulTraceLevel; lpData
0x180015470  lea     rdx, stru_1800A1AA0; lpValueName
0x180015477  call    ?ReadRegValueDWORD@WiaTrcLib@@YAJPEAUHKEY__@@PEAGPEAKH@Z; WiaTrcLib::ReadRegValueDWORD(HKEY__ *,ushort *,ulong *,int)
0x18001547c  mov     ebx, eax
0x18001547e  test    eax, eax
0x180015480  jnz     short loc_1800154D8
0x180015482  mov     rcx, [rsp+2C0h+var_268]; hKey
0x180015487  lea     r8, g_WiaTrace_ulTraceArraySize; lpData
0x18001548e  lea     rdx, stru_1800A1B90; lpValueName
0x180015495  call    ?ReadRegValueDWORD@WiaTrcLib@@YAJPEAUHKEY__@@PEAGPEAKH@Z; WiaTrcLib::ReadRegValueDWORD(HKEY__ *,ushort *,ulong *,int)
0x18001549a  mov     ebx, eax
0x18001549c  test    eax, eax
0x18001549e  jnz     short loc_1800154D8
0x1800154a0  mov     rcx, [rsp+2C0h+var_268]; hKey
0x1800154a5  lea     r8, g_WiaTrace_bEnableObjectTracking; lpData
0x1800154ac  lea     rdx, stru_1800A1B60; lpValueName
0x1800154b3  call    ?ReadRegValueDWORD@WiaTrcLib@@YAJPEAUHKEY__@@PEAGPEAKH@Z; WiaTrcLib::ReadRegValueDWORD(HKEY__ *,ushort *,ulong *,int)
0x1800154b8  mov     ebx, eax
0x1800154ba  test    eax, eax
0x1800154bc  jnz     short loc_1800154D8
0x1800154be  mov     rcx, [rsp+2C0h+var_268]; hKey
0x1800154c3  lea     r8, g_WiaTrace_ulHeapOptions; lpData
0x1800154ca  lea     rdx, stru_1800A1AE8; lpValueName
0x1800154d1  call    ?ReadRegValueDWORD@WiaTrcLib@@YAJPEAUHKEY__@@PEAGPEAKH@Z; WiaTrcLib::ReadRegValueDWORD(HKEY__ *,ushort *,ulong *,int)
0x1800154d6  mov     ebx, eax
0x1800154d8  mov     rcx, [rsp+2C0h+var_268]; hKey
0x1800154dd  test    rcx, rcx
0x1800154e0  jz      short loc_1800154E8
0x1800154e2  call    cs:__imp_RegCloseKey
0x1800154e8  mov     rcx, [rsp+2C0h+hKey]; hKey
0x1800154ed  test    rcx, rcx
0x1800154f0  jz      short loc_1800154F8
0x1800154f2  call    cs:__imp_RegCloseKey
0x1800154f8  mov     eax, ebx
0x1800154fa  mov     rcx, [rbp+1C0h+var_30]
0x180015501  xor     rcx, rsp; StackCookie
0x180015504  call    __security_check_cookie
0x180015509  add     rsp, 2A8h
0x180015510  pop     r14
0x180015512  pop     rdi
0x180015513  pop     rbx
0x180015514  pop     rbp
0x180015515  retn
```
