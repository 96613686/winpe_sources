# InitCoreAuthzLib(void)

- ea: `0x1800a96f8`
- end: `0x1800a99d6`
- name: `?InitCoreAuthzLib@@YAJXZ`
- size: `734`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180058ab0`

## callees

- `0x18000b140`
- `0x1800a96f8`
- `0x1800da010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9757`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a978c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a97c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a97f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a982b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a985c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a988d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a992b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a998d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9757`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a978c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a97c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a97f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a982b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a985c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a988d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a992b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a998d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800a9729`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800a9729`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a9745`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a977a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a97af`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a97e4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a9819`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a984a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a987b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a9745`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a977a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a97af`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a97e4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a9819`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a984a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a987b`
- `wbemcomn!GetMemLogObject` at `0x1800a98a2`
- `wbemcomn!GetMemLogObject` at `0x1800a9940`
- `wbemcomn!GetMemLogObject` at `0x1800a99a6`
- `wbemcomn!GetMemLogObject` at `0x1800a98a2`
- `wbemcomn!GetMemLogObject` at `0x1800a9940`
- `wbemcomn!GetMemLogObject` at `0x1800a99a6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a98ad`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a994b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a99b1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a98ad`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a994b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a99b1`

## string_xrefs

- `0x1800a9720`: `authZ.dll`
- `0x1800a973b`: `AuthzInitializeContextFromToken`
- `0x1800a9770`: `AuthzInitializeObjectAccessAuditEvent2`
- `0x1800a97a5`: `AuthzAccessCheck`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 InitCoreAuthzLib(void)
{
  signed int v0; // ebx
  HMODULE Library; // rax
  HMODULE v2; // rdi
  signed int LastError; // eax
  signed int v4; // eax
  signed int v5; // eax
  signed int v6; // eax
  signed int v7; // eax
  signed int v8; // eax
  signed int v9; // eax
  CMemoryLog *MemLogObject; // rax
  signed int v11; // eax
  CMemoryLog *v12; // rax
  CClientCnt *v13; // rcx
  __int64 v14; // rdx
  signed int v16; // eax
  CMemoryLog *v17; // rax

  v0 = 0;
  if ( !g_pfnAuthzFreeResourceManager )
  {
    Library = LoadLibraryExW(L"authZ.dll", 0, 0);
    v2 = Library;
    if ( Library )
    {
      g_pfnAuthzInitializeContextFromToken = (int (*)(unsigned int, void *, struct AUTHZ_RESOURCE_MANAGER_HANDLE__ *, union _LARGE_INTEGER *, struct _LUID, void *, struct AUTHZ_CLIENT_CONTEXT_HANDLE__ **))GetProcAddress(Library, "AuthzInitializeContextFromToken");
      if ( !g_pfnAuthzInitializeContextFromToken )
      {
        LastError = GetLastError();
        v0 = LastError;
        if ( LastError > 0 )
          v0 = (unsigned __int16)LastError | 0x80070000;
        if ( v0 < 0 )
          goto LABEL_31;
      }
      g_pfnAuthzInitializeObjectAccessAuditEvent2 = (int (*)(unsigned int, struct AUTHZ_AUDIT_EVENT_TYPE_HANDLE__ *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, struct AUTHZ_AUDIT_EVENT_HANDLE__ **, unsigned int, ...))GetProcAddress(v2, "AuthzInitializeObjectAccessAuditEvent2");
      if ( !g_pfnAuthzInitializeObjectAccessAuditEvent2 )
      {
        v4 = GetLastError();
        v0 = v4;
        if ( v4 > 0 )
          v0 = (unsigned __int16)v4 | 0x80070000;
        if ( v0 < 0 )
          goto LABEL_31;
      }
      g_pfnAuthzAccessCheck = (int (*)(unsigned int, struct AUTHZ_CLIENT_CONTEXT_HANDLE__ *, struct _AUTHZ_ACCESS_REQUEST *, struct AUTHZ_AUDIT_EVENT_HANDLE__ *, void *, void **, unsigned int, struct _AUTHZ_ACCESS_REPLY *, struct AUTHZ_ACCESS_CHECK_RESULTS_HANDLE__ **))GetProcAddress(v2, "AuthzAccessCheck");
      if ( !g_pfnAuthzAccessCheck )
      {
        v5 = GetLastError();
        v0 = v5;
        if ( v5 > 0 )
          v0 = (unsigned __int16)v5 | 0x80070000;
        if ( v0 < 0 )
          goto LABEL_31;
      }
      g_pfnAuthzFreeAuditEvent = (int (*)(struct AUTHZ_AUDIT_EVENT_HANDLE__ *))GetProcAddress(v2, "AuthzFreeAuditEvent");
      if ( !g_pfnAuthzFreeAuditEvent )
      {
        v6 = GetLastError();
        v0 = v6;
        if ( v6 > 0 )
          v0 = (unsigned __int16)v6 | 0x80070000;
        if ( v0 < 0 )
          goto LABEL_31;
      }
      g_pfnAuthzFreeContext = (int (*)(struct AUTHZ_CLIENT_CONTEXT_HANDLE__ *))GetProcAddress(v2, "AuthzFreeContext");
      if ( !g_pfnAuthzFreeContext )
      {
        v7 = GetLastError();
        v0 = v7;
        if ( v7 > 0 )
          v0 = (unsigned __int16)v7 | 0x80070000;
        if ( v0 < 0 )
          goto LABEL_31;
      }
      g_pfnAuthzInitializeResourceManager = (int (*)(unsigned int, int (*)(struct AUTHZ_CLIENT_CONTEXT_HANDLE__ *, struct _ACE_HEADER *, void *, int *), int (*)(struct AUTHZ_CLIENT_CONTEXT_HANDLE__ *, void *, struct _SID_AND_ATTRIBUTES **, unsigned int *, struct _SID_AND_ATTRIBUTES **, unsigned int *), void (*)(struct _SID_AND_ATTRIBUTES *), const unsigned __int16 *, struct AUTHZ_RESOURCE_MANAGER_HANDLE__ **))GetProcAddress(v2, "AuthzInitializeResourceManager");
      if ( !g_pfnAuthzInitializeResourceManager )
      {
        v8 = GetLastError();
        v0 = v8;
        if ( v8 > 0 )
          v0 = (unsigned __int16)v8 | 0x80070000;
        if ( v0 < 0 )
          goto LABEL_31;
      }
      g_pfnAuthzFreeResourceManager = (int (*)(struct AUTHZ_RESOURCE_MANAGER_HANDLE__ *))GetProcAddress(
                                                                                           v2,
                                                                                           "AuthzFreeResourceManager");
      if ( !g_pfnAuthzFreeResourceManager )
      {
        v9 = GetLastError();
        v0 = v9;
        if ( v9 > 0 )
          v0 = (unsigned __int16)v9 | 0x80070000;
        if ( v0 < 0 )
        {
LABEL_31:
          MemLogObject = GetMemLogObject();
          CMemoryLog::Write(MemLogObject, v0);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              11,
              WPP_406d18b37f4a36ff5cfc0ae01cbf7be7_Traceguids,
              (unsigned int)v0);
          }
          return (unsigned int)v0;
        }
      }
    }
    else
    {
      v16 = GetLastError();
      v0 = v16;
      if ( v16 > 0 )
        v0 = (unsigned __int16)v16 | 0x80070000;
      if ( v0 < 0 )
      {
        v17 = GetMemLogObject();
        CMemoryLog::Write(v17, v0);
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return (unsigned int)v0;
        }
        v14 = 12;
LABEL_45:
        WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_406d18b37f4a36ff5cfc0ae01cbf7be7_Traceguids, (unsigned int)v0);
        return (unsigned int)v0;
      }
    }
  }
  if ( !g_AuthzResourceManager
    && !(unsigned int)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, const wchar_t *, struct AUTHZ_RESOURCE_MANAGER_HANDLE__ **))g_pfnAuthzInitializeResourceManager)(
                        0,
                        0,
                        0,
                        0,
                        L"WMI",
                        &g_AuthzResourceManager) )
  {
    v11 = GetLastError();
    v0 = v11;
    if ( v11 > 0 )
      v0 = (unsigned __int16)v11 | 0x80070000;
    if ( v0 < 0 )
    {
      v12 = GetMemLogObject();
      CMemoryLog::Write(v12, v0);
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = 13;
        goto LABEL_45;
      }
    }
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x1800a96f8  push    rbx
0x1800a96fa  push    rsi
0x1800a96fb  push    rdi
0x1800a96fc  push    r12
0x1800a96fe  sub     rsp, 48h
0x1800a9702  xor     ebx, ebx
0x1800a9704  lea     r12, WPP_GLOBAL_Control
0x1800a970b  cmp     cs:?g_pfnAuthzFreeResourceManager@@3P6AHPEAUAUTHZ_RESOURCE_MANAGER_HANDLE__@@@ZEA, rbx; int (*g_pfnAuthzFreeResourceManager)(AUTHZ_RESOURCE_MANAGER_HANDLE__ *)
0x1800a9712  mov     esi, 80070000h
0x1800a9717  jnz     loc_1800A98EB
0x1800a971d  xor     r8d, r8d; dwFlags
0x1800a9720  lea     rcx, aAuthzDll; "authZ.dll"
0x1800a9727  xor     edx, edx; hFile
0x1800a9729  call    cs:__imp_LoadLibraryExW
0x1800a972f  mov     rdi, rax
0x1800a9732  test    rax, rax
0x1800a9735  jz      loc_1800A998D
0x1800a973b  lea     rdx, aAuthzinitializ; "AuthzInitializeContextFromToken"
0x1800a9742  mov     rcx, rax; hModule
0x1800a9745  call    cs:__imp_GetProcAddress
0x1800a974b  mov     cs:?g_pfnAuthzInitializeContextFromToken@@3P6AHKPEAXPEAUAUTHZ_RESOURCE_MANAGER_HANDLE__@@PEAT_LARGE_INTEGER@@U_LUID@@0PEAPEAUAUTHZ_CLIENT_CONTEXT_HANDLE__@@@ZEA, rax; int (*g_pfnAuthzInitializeContextFromToken)(ulong,void *,AUTHZ_RESOURCE_MANAGER_HANDLE__ *,_LARGE_INTEGER *,_LUID,void *,AUTHZ_CLIENT_CONTEXT_HANDLE__ * *)
0x1800a9752  test    rax, rax
0x1800a9755  jnz     short loc_1800A9770
0x1800a9757  call    cs:__imp_GetLastError
0x1800a975d  mov     ebx, eax
0x1800a975f  test    eax, eax
0x1800a9761  jle     short loc_1800A9768
0x1800a9763  movzx   ebx, ax
0x1800a9766  or      ebx, esi
0x1800a9768  test    ebx, ebx
0x1800a976a  js      loc_1800A98A2
0x1800a9770  lea     rdx, aAuthzinitializ_0; "AuthzInitializeObjectAccessAuditEvent2"
0x1800a9777  mov     rcx, rdi; hModule
0x1800a977a  call    cs:__imp_GetProcAddress
0x1800a9780  mov     cs:?g_pfnAuthzInitializeObjectAccessAuditEvent2@@3P6AHKPEAUAUTHZ_AUDIT_EVENT_TYPE_HANDLE__@@PEAG1111PEAPEAUAUTHZ_AUDIT_EVENT_HANDLE__@@KZZEA, rax; int (*g_pfnAuthzInitializeObjectAccessAuditEvent2)(ulong,AUTHZ_AUDIT_EVENT_TYPE_HANDLE__ *,ushort *,ushort *,ushort *,ushort *,ushort *,AUTHZ_AUDIT_EVENT_HANDLE__ * *,ulong,...)
0x1800a9787  test    rax, rax
0x1800a978a  jnz     short loc_1800A97A5
0x1800a978c  call    cs:__imp_GetLastError
0x1800a9792  mov     ebx, eax
0x1800a9794  test    eax, eax
0x1800a9796  jle     short loc_1800A979D
0x1800a9798  movzx   ebx, ax
0x1800a979b  or      ebx, esi
0x1800a979d  test    ebx, ebx
0x1800a979f  js      loc_1800A98A2
0x1800a97a5  lea     rdx, aAuthzaccessche; "AuthzAccessCheck"
0x1800a97ac  mov     rcx, rdi; hModule
0x1800a97af  call    cs:__imp_GetProcAddress
0x1800a97b5  mov     cs:?g_pfnAuthzAccessCheck@@3P6AHKPEAUAUTHZ_CLIENT_CONTEXT_HANDLE__@@PEAU_AUTHZ_ACCESS_REQUEST@@PEAUAUTHZ_AUDIT_EVENT_HANDLE__@@PEAXPEAPEAXKPEAU_AUTHZ_ACCESS_REPLY@@PEAPEAUAUTHZ_ACCESS_CHECK_RESULTS_HANDLE__@@@ZEA, rax; int (*g_pfnAuthzAccessCheck)(ulong,AUTHZ_CLIENT_CONTEXT_HANDLE__ *,_AUTHZ_ACCESS_REQUEST *,AUTHZ_AUDIT_EVENT_HANDLE__ *,void *,void * *,ulong,_AUTHZ_ACCESS_REPLY *,AUTHZ_ACCESS_CHECK_RESULTS_HANDLE__ * *)
0x1800a97bc  test    rax, rax
0x1800a97bf  jnz     short loc_1800A97DA
0x1800a97c1  call    cs:__imp_GetLastError
0x1800a97c7  mov     ebx, eax
0x1800a97c9  test    eax, eax
0x1800a97cb  jle     short loc_1800A97D2
0x1800a97cd  movzx   ebx, ax
0x1800a97d0  or      ebx, esi
0x1800a97d2  test    ebx, ebx
0x1800a97d4  js      loc_1800A98A2
0x1800a97da  lea     rdx, aAuthzfreeaudit; "AuthzFreeAuditEvent"
0x1800a97e1  mov     rcx, rdi; hModule
0x1800a97e4  call    cs:__imp_GetProcAddress
0x1800a97ea  mov     cs:?g_pfnAuthzFreeAuditEvent@@3P6AHPEAUAUTHZ_AUDIT_EVENT_HANDLE__@@@ZEA, rax; int (*g_pfnAuthzFreeAuditEvent)(AUTHZ_AUDIT_EVENT_HANDLE__ *)
0x1800a97f1  test    rax, rax
0x1800a97f4  jnz     short loc_1800A980F
0x1800a97f6  call    cs:__imp_GetLastError
0x1800a97fc  mov     ebx, eax
0x1800a97fe  test    eax, eax
0x1800a9800  jle     short loc_1800A9807
0x1800a9802  movzx   ebx, ax
0x1800a9805  or      ebx, esi
0x1800a9807  test    ebx, ebx
0x1800a9809  js      loc_1800A98A2
0x1800a980f  lea     rdx, aAuthzfreeconte; "AuthzFreeContext"
0x1800a9816  mov     rcx, rdi; hModule
0x1800a9819  call    cs:__imp_GetProcAddress
0x1800a981f  mov     cs:?g_pfnAuthzFreeContext@@3P6AHPEAUAUTHZ_CLIENT_CONTEXT_HANDLE__@@@ZEA, rax; int (*g_pfnAuthzFreeContext)(AUTHZ_CLIENT_CONTEXT_HANDLE__ *)
0x1800a9826  test    rax, rax
0x1800a9829  jnz     short loc_1800A9840
0x1800a982b  call    cs:__imp_GetLastError
0x1800a9831  mov     ebx, eax
0x1800a9833  test    eax, eax
0x1800a9835  jle     short loc_1800A983C
0x1800a9837  movzx   ebx, ax
0x1800a983a  or      ebx, esi
0x1800a983c  test    ebx, ebx
0x1800a983e  js      short loc_1800A98A2
0x1800a9840  lea     rdx, aAuthzinitializ_1; "AuthzInitializeResourceManager"
0x1800a9847  mov     rcx, rdi; hModule
0x1800a984a  call    cs:__imp_GetProcAddress
0x1800a9850  mov     cs:?g_pfnAuthzInitializeResourceManager@@3P6AHKP6AHPEAUAUTHZ_CLIENT_CONTEXT_HANDLE__@@PEAU_ACE_HEADER@@PEAXPEAH@ZP6AH02PEAPEAU_SID_AND_ATTRIBUTES@@PEAK56@ZP6AXPEAU3@@ZPEBGPEAPEAUAUTHZ_RESOURCE_MANAGER_HANDLE__@@@ZEA, rax; int (*g_pfnAuthzInitializeResourceManager)(ulong,int (*)(AUTHZ_CLIENT_CONTEXT_HANDLE__ *,_ACE_HEADER *,void *,int *),int (*)(AUTHZ_CLIENT_CONTEXT_HANDLE__ *,void *,_SID_AND_ATTRIBUTES * *,ulong *,_SID_AND_ATTRIBUTES * *,ulong *),void (*)(_SID_AND_ATTRIBUTES *),ushort const *,AUTHZ_RESOURCE_MANAGER_HANDLE__ * *)
0x1800a9857  test    rax, rax
0x1800a985a  jnz     short loc_1800A9871
0x1800a985c  call    cs:__imp_GetLastError
0x1800a9862  mov     ebx, eax
0x1800a9864  test    eax, eax
0x1800a9866  jle     short loc_1800A986D
0x1800a9868  movzx   ebx, ax
0x1800a986b  or      ebx, esi
0x1800a986d  test    ebx, ebx
0x1800a986f  js      short loc_1800A98A2
0x1800a9871  lea     rdx, aAuthzfreeresou; "AuthzFreeResourceManager"
0x1800a9878  mov     rcx, rdi; hModule
0x1800a987b  call    cs:__imp_GetProcAddress
0x1800a9881  mov     cs:?g_pfnAuthzFreeResourceManager@@3P6AHPEAUAUTHZ_RESOURCE_MANAGER_HANDLE__@@@ZEA, rax; int (*g_pfnAuthzFreeResourceManager)(AUTHZ_RESOURCE_MANAGER_HANDLE__ *)
0x1800a9888  test    rax, rax
0x1800a988b  jnz     short loc_1800A98EB
0x1800a988d  call    cs:__imp_GetLastError
0x1800a9893  mov     ebx, eax
0x1800a9895  test    eax, eax
0x1800a9897  jle     short loc_1800A989E
0x1800a9899  movzx   ebx, ax
0x1800a989c  or      ebx, esi
0x1800a989e  test    ebx, ebx
0x1800a98a0  jns     short loc_1800A98EB
0x1800a98a2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a98a8  mov     rcx, rax
0x1800a98ab  mov     edx, ebx
0x1800a98ad  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a98b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a98ba  cmp     rcx, r12
0x1800a98bd  jz      short loc_1800A98E3
0x1800a98bf  test    byte ptr [rcx+1Ch], 1
0x1800a98c3  jz      short loc_1800A98E3
0x1800a98c5  cmp     byte ptr [rcx+19h], 2
0x1800a98c9  jb      short loc_1800A98E3
0x1800a98cb  mov     rcx, [rcx+10h]
0x1800a98cf  lea     r8, WPP_406d18b37f4a36ff5cfc0ae01cbf7be7_Traceguids
0x1800a98d6  mov     edx, 0Bh
0x1800a98db  mov     r9d, ebx
0x1800a98de  call    WPP_SF_d
0x1800a98e3  test    ebx, ebx
0x1800a98e5  js      loc_1800A9981
0x1800a98eb  cmp     cs:?g_AuthzResourceManager@@3PEAUAUTHZ_RESOURCE_MANAGER_HANDLE__@@EA, 0; AUTHZ_RESOURCE_MANAGER_HANDLE__ * g_AuthzResourceManager
0x1800a98f3  jnz     loc_1800A9981
0x1800a98f9  lea     rax, ?g_AuthzResourceManager@@3PEAUAUTHZ_RESOURCE_MANAGER_HANDLE__@@EA; AUTHZ_RESOURCE_MANAGER_HANDLE__ * g_AuthzResourceManager
0x1800a9900  xor     r9d, r9d
0x1800a9903  mov     [rsp+68h+var_40], rax
0x1800a9908  xor     r8d, r8d
0x1800a990b  lea     rax, aWmi; "WMI"
0x1800a9912  xor     edx, edx
0x1800a9914  mov     [rsp+68h+var_48], rax
0x1800a9919  xor     ecx, ecx
0x1800a991b  mov     rax, cs:?g_pfnAuthzInitializeResourceManager@@3P6AHKP6AHPEAUAUTHZ_CLIENT_CONTEXT_HANDLE__@@PEAU_ACE_HEADER@@PEAXPEAH@ZP6AH02PEAPEAU_SID_AND_ATTRIBUTES@@PEAK56@ZP6AXPEAU3@@ZPEBGPEAPEAUAUTHZ_RESOURCE_MANAGER_HANDLE__@@@ZEA; int (*g_pfnAuthzInitializeResourceManager)(ulong,int (*)(AUTHZ_CLIENT_CONTEXT_HANDLE__ *,_ACE_HEADER *,void *,int *),int (*)(AUTHZ_CLIENT_CONTEXT_HANDLE__ *,void *,_SID_AND_ATTRIBUTES * *,ulong *,_SID_AND_ATTRIBUTES * *,ulong *),void (*)(_SID_AND_ATTRIBUTES *),ushort const *,AUTHZ_RESOURCE_MANAGER_HANDLE__ * *)
0x1800a9922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9927  test    eax, eax
0x1800a9929  jnz     short loc_1800A9981
0x1800a992b  call    cs:__imp_GetLastError
0x1800a9931  mov     ebx, eax
0x1800a9933  test    eax, eax
0x1800a9935  jle     short loc_1800A993C
0x1800a9937  movzx   ebx, ax
0x1800a993a  or      ebx, esi
0x1800a993c  test    ebx, ebx
0x1800a993e  jns     short loc_1800A9981
0x1800a9940  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a9946  mov     rcx, rax
0x1800a9949  mov     edx, ebx
0x1800a994b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a9951  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a9958  cmp     rcx, r12
0x1800a995b  jz      short loc_1800A9981
0x1800a995d  test    byte ptr [rcx+1Ch], 1
0x1800a9961  jz      short loc_1800A9981
0x1800a9963  cmp     byte ptr [rcx+19h], 2
0x1800a9967  jb      short loc_1800A9981
0x1800a9969  mov     edx, 0Dh
0x1800a996e  mov     rcx, [rcx+10h]
0x1800a9972  lea     r8, WPP_406d18b37f4a36ff5cfc0ae01cbf7be7_Traceguids
0x1800a9979  mov     r9d, ebx
0x1800a997c  call    WPP_SF_d
0x1800a9981  mov     eax, ebx
0x1800a9983  add     rsp, 48h
0x1800a9987  pop     r12
0x1800a9989  pop     rdi
0x1800a998a  pop     rsi
0x1800a998b  pop     rbx
0x1800a998c  retn
0x1800a998d  call    cs:__imp_GetLastError
0x1800a9993  mov     ebx, eax
0x1800a9995  test    eax, eax
0x1800a9997  jle     short loc_1800A999E
0x1800a9999  movzx   ebx, ax
0x1800a999c  or      ebx, esi
0x1800a999e  test    ebx, ebx
0x1800a99a0  jns     loc_1800A98EB
0x1800a99a6  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a99ac  mov     rcx, rax
0x1800a99af  mov     edx, ebx
0x1800a99b1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a99b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a99be  cmp     rcx, r12
0x1800a99c1  jz      short loc_1800A9981
0x1800a99c3  test    byte ptr [rcx+1Ch], 1
0x1800a99c7  jz      short loc_1800A9981
0x1800a99c9  cmp     byte ptr [rcx+19h], 2
0x1800a99cd  jb      short loc_1800A9981
0x1800a99cf  mov     edx, 0Ch
0x1800a99d4  jmp     short loc_1800A996E
```
