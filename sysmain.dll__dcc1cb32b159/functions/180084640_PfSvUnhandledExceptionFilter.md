# PfSvUnhandledExceptionFilter

- ea: `0x180084640`
- end: `0x180084897`
- name: `PfSvUnhandledExceptionFilter`
- size: `599`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180066924`

## callees

- `0x1800382e0`
- `0x180083234`
- `0x180084640`
- `0x1800b64c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180084867`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180084867`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800847fe`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800847fe`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180084777`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180084777`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180084785`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180084785`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180084850`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180084859`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180084850`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180084859`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180084705`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180084705`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180084727`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180084727`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18008476d`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18008476d`

## pseudocode

```c
__int64 __fastcall PfSvUnhandledExceptionFilter(unsigned int **a1)
{
  unsigned int *v1; // rbx
  HKEY v2; // rsi
  __int64 v3; // rcx
  unsigned __int64 v4; // rax
  __int64 v5; // rdx
  bool v6; // cf
  SC_HANDLE v7; // rax
  SC_HANDLE v8; // r14
  SC_HANDLE v9; // rax
  SC_HANDLE v10; // r15
  unsigned __int64 v11; // rdi
  int v12; // eax
  __int64 v13; // rax
  __int64 v15; // [rsp+60h] [rbp+7h] BYREF
  struct _FILETIME FileTime; // [rsp+68h] [rbp+Fh] BYREF
  HKEY hKey; // [rsp+70h] [rbp+17h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+78h] [rbp+1Fh] BYREF

  v1 = *a1;
  v2 = 0;
  FileTime = 0;
  v15 = 0;
  SystemTime = 0;
  v3 = *v1;
  hKey = 0;
  if ( (_DWORD)v3 == -1073740768
    || (_DWORD)v3 == -1073741596
    || (v4 = (unsigned int)(v3 + 1073741819), (unsigned int)v4 <= 0x3A)
    && (v5 = 0x400000001000001LL, _bittest64(&v5, v4))
    || (_DWORD)v3 == -1073700607 )
  {
    if ( *(_QWORD *)&PfSvcGlobals )
    {
      if ( (*(_DWORD *)(*(_QWORD *)&PfSvcGlobals + 1600LL) & 0x200) == 0 )
      {
        v6 = v1[6] < 0xF;
        *v1 = -1073741051;
        if ( v6 )
          *(_QWORD *)&v1[2 * v1[6]++ + 8] = v3;
      }
    }
    v7 = OpenSCManagerW(0, 0, 0xF003Fu);
    v8 = v7;
    if ( v7 )
    {
      v9 = OpenServiceW(v7, L"Sysmain", 2u);
      v10 = v9;
      if ( v9 )
      {
        LODWORD(v11) = -1;
        ChangeServiceConfigW(v9, 0x10u, 0xFFFFFFFF, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0);
        GetLocalTime(&SystemTime);
        SystemTimeToFileTime(&SystemTime, &FileTime);
        v12 = PfSvServiceRegistryKeyGet(&hKey, 0);
        v2 = hKey;
        if ( !v12 )
        {
          v15 = 0;
          if ( (unsigned int)PfsRegQueryValue((_DWORD)hKey, (unsigned int)L"LastCrashTime", 11, 8, (__int64)&v15)
            || (v13 = v15, v15 != -1) )
          {
            RegSetValueExW(v2, L"LastCrashTime", 0, 0xBu, (const BYTE *)&FileTime, 8u);
            v13 = v15;
          }
          if ( v1[6] < 0xF )
          {
            if ( v13 )
            {
              if ( v13 != -1 )
              {
                v11 = (*(_QWORD *)&FileTime - v13) / 0x989680uLL;
                if ( (unsigned int)v11 <= 1 )
                  LODWORD(v11) = 1;
              }
            }
            else
            {
              LODWORD(v11) = 0;
            }
            *(_QWORD *)&v1[2 * v1[6]++ + 8] = (unsigned int)v11;
          }
        }
        CloseServiceHandle(v10);
      }
      CloseServiceHandle(v8);
      if ( v2 )
        RegCloseKey(v2);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180084640  mov     [rsp-8+arg_8], rbx
0x180084645  mov     [rsp-8+arg_10], rsi
0x18008464a  push    rbp
0x18008464b  push    rdi
0x18008464c  push    r13
0x18008464e  push    r14
0x180084650  push    r15
0x180084652  lea     rbp, [rsp-37h]
0x180084657  sub     rsp, 90h
0x18008465e  mov     rax, cs:__security_cookie
0x180084665  xor     rax, rsp
0x180084668  mov     [rbp+57h+var_28], rax
0x18008466c  mov     rbx, [rcx]
0x18008466f  xor     esi, esi
0x180084671  xorps   xmm0, xmm0
0x180084674  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], 0
0x18008467c  mov     [rbp+57h+var_50], 0
0x180084684  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x180084688  mov     ecx, [rbx]
0x18008468a  mov     [rbp+57h+hKey], rsi
0x18008468e  cmp     ecx, 0C0000420h
0x180084694  jz      short loc_1800846C5
0x180084696  cmp     ecx, 0C00000E4h
0x18008469c  jz      short loc_1800846C5
0x18008469e  lea     eax, [rcx+3FFFFFFBh]
0x1800846a4  cmp     eax, 3Ah ; ':'
0x1800846a7  ja      short loc_1800846B9
0x1800846a9  mov     rdx, 400000001000001h
0x1800846b3  bt      rdx, rax
0x1800846b7  jb      short loc_1800846C5
0x1800846b9  cmp     ecx, 0C000A101h
0x1800846bf  jnz     loc_18008486D
0x1800846c5  mov     rax, cs:PfSvcGlobals
0x1800846cc  mov     r13d, 1
0x1800846d2  test    rax, rax
0x1800846d5  jz      short loc_1800846FB
0x1800846d7  test    dword ptr [rax+640h], 200h
0x1800846e1  jnz     short loc_1800846FB
0x1800846e3  cmp     dword ptr [rbx+18h], 0Fh
0x1800846e7  mov     dword ptr [rbx], 0C0000305h
0x1800846ed  jnb     short loc_1800846FB
0x1800846ef  mov     eax, [rbx+18h]
0x1800846f2  mov     [rbx+rax*8+20h], rcx
0x1800846f7  add     [rbx+18h], r13d
0x1800846fb  xor     edx, edx; lpDatabaseName
0x1800846fd  xor     ecx, ecx; lpMachineName
0x1800846ff  mov     r8d, 0F003Fh; dwDesiredAccess
0x180084705  call    cs:__imp_OpenSCManagerW
0x18008470b  mov     r14, rax
0x18008470e  test    rax, rax
0x180084711  jz      loc_18008486D
0x180084717  mov     r8d, 2; dwDesiredAccess
0x18008471d  lea     rdx, ServiceName; "Sysmain"
0x180084724  mov     rcx, rax; hSCManager
0x180084727  call    cs:__imp_OpenServiceW
0x18008472d  mov     r15, rax
0x180084730  test    rax, rax
0x180084733  jz      loc_180084856
0x180084739  mov     [rsp+0B0h+lpDisplayName], rsi; lpDisplayName
0x18008473e  or      edi, 0FFFFFFFFh
0x180084741  mov     [rsp+0B0h+lpPassword], rsi; lpPassword
0x180084746  mov     r9d, edi; dwErrorControl
0x180084749  mov     [rsp+0B0h+lpServiceStartName], rsi; lpServiceStartName
0x18008474e  mov     r8d, edi; dwStartType
0x180084751  mov     [rsp+0B0h+lpDependencies], rsi; lpDependencies
0x180084756  mov     edx, 10h; dwServiceType
0x18008475b  mov     [rsp+0B0h+lpdwTagId], rsi; lpdwTagId
0x180084760  mov     rcx, rax; hService
0x180084763  mov     [rsp+0B0h+lpLoadOrderGroup], rsi; lpLoadOrderGroup
0x180084768  mov     [rsp+0B0h+lpBinaryPathName], rsi; lpBinaryPathName
0x18008476d  call    cs:__imp_ChangeServiceConfigW
0x180084773  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x180084777  call    cs:__imp_GetLocalTime
0x18008477d  lea     rdx, [rbp+57h+FileTime]; lpFileTime
0x180084781  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x180084785  call    cs:__imp_SystemTimeToFileTime
0x18008478b  xor     edx, edx
0x18008478d  lea     rcx, [rbp+57h+hKey]
0x180084791  call    PfSvServiceRegistryKeyGet
0x180084796  mov     rsi, [rbp+57h+hKey]
0x18008479a  test    eax, eax
0x18008479c  jnz     loc_18008484D
0x1800847a2  mov     r9d, 8
0x1800847a8  mov     [rbp+57h+var_50], 0
0x1800847b0  lea     rax, [rbp+57h+var_50]
0x1800847b4  mov     rcx, rsi
0x1800847b7  lea     rdx, aLastcrashtime; "LastCrashTime"
0x1800847be  mov     [rsp+0B0h+lpBinaryPathName], rax
0x1800847c3  lea     r8d, [r9+3]
0x1800847c7  call    PfsRegQueryValue
0x1800847cc  test    eax, eax
0x1800847ce  jnz     short loc_1800847DA
0x1800847d0  mov     rax, [rbp+57h+var_50]
0x1800847d4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800847d8  jz      short loc_180084808
0x1800847da  lea     rax, [rbp+57h+FileTime]
0x1800847de  mov     dword ptr [rsp+0B0h+lpLoadOrderGroup], 8; cbData
0x1800847e6  mov     r9d, 0Bh; dwType
0x1800847ec  mov     [rsp+0B0h+lpBinaryPathName], rax; lpData
0x1800847f1  xor     r8d, r8d; Reserved
0x1800847f4  lea     rdx, aLastcrashtime; "LastCrashTime"
0x1800847fb  mov     rcx, rsi; hKey
0x1800847fe  call    cs:__imp_RegSetValueExW
0x180084804  mov     rax, [rbp+57h+var_50]
0x180084808  cmp     dword ptr [rbx+18h], 0Fh
0x18008480c  jnb     short loc_18008484D
0x18008480e  test    rax, rax
0x180084811  jnz     short loc_180084817
0x180084813  xor     edi, edi
0x180084815  jmp     short loc_18008483F
0x180084817  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18008481b  jz      short loc_18008483F
0x18008481d  mov     rcx, qword ptr [rbp+57h+FileTime.dwLowDateTime]
0x180084821  sub     rcx, rax
0x180084824  mov     rax, 0D6BF94D5E57A42BDh
0x18008482e  mul     rcx
0x180084831  mov     rdi, rdx
0x180084834  shr     rdi, 17h
0x180084838  cmp     edi, r13d
0x18008483b  cmovbe  edi, r13d
0x18008483f  mov     eax, [rbx+18h]
0x180084842  mov     edx, edi
0x180084844  mov     [rbx+rax*8+20h], rdx
0x180084849  add     [rbx+18h], r13d
0x18008484d  mov     rcx, r15; hSCObject
0x180084850  call    cs:__imp_CloseServiceHandle
0x180084856  mov     rcx, r14; hSCObject
0x180084859  call    cs:__imp_CloseServiceHandle
0x18008485f  test    rsi, rsi
0x180084862  jz      short loc_18008486D
0x180084864  mov     rcx, rsi; hKey
0x180084867  call    cs:__imp_RegCloseKey
0x18008486d  xor     eax, eax
0x18008486f  mov     rcx, [rbp+57h+var_28]
0x180084873  xor     rcx, rsp; StackCookie
0x180084876  call    __security_check_cookie
0x18008487b  lea     r11, [rsp+0B0h+var_20]
0x180084883  mov     rbx, [r11+38h]
0x180084887  mov     rsi, [r11+40h]
0x18008488b  mov     rsp, r11
0x18008488e  pop     r15
0x180084890  pop     r14
0x180084892  pop     r13
0x180084894  pop     rdi
0x180084895  pop     rbp
0x180084896  retn
```
