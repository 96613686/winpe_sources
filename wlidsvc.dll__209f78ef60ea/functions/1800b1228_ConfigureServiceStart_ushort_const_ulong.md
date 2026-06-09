# ConfigureServiceStart(ushort const *,ulong)

- ea: `0x1800b1228`
- end: `0x1800b13b6`
- name: `?ConfigureServiceStart@@YAJPEBGK@Z`
- size: `398`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18008a17c`

## callees

- `0x18002d36c`
- `0x1800aecec`
- `0x1800b1228`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1259`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b12b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1352`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1259`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b12b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1352`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800b1246`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800b1246`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800b12a4`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800b12a4`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x1800b1348`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x1800b1348`

## string_xrefs

- `0x1800b127b`: `onecoreuap\ds\ext\Live\identity\Include\ServiceHelper.h`
- `0x1800b12d5`: `onecoreuap\ds\ext\Live\identity\Include\ServiceHelper.h`
- `0x1800b1370`: `onecoreuap\ds\ext\Live\identity\Include\ServiceHelper.h`
- `0x1800b123d`: `ServicesActive`

## pseudocode

```c
__int64 __fastcall ConfigureServiceStart(const unsigned __int16 *a1)
{
  SC_HANDLE v1; // rax
  signed int v2; // eax
  signed int v3; // ebx
  SC_HANDLE v4; // rbx
  signed int LastError; // eax
  signed int v6; // edi
  signed int v7; // eax
  int lpBinaryPathName; // [rsp+20h] [rbp-48h]
  int lpBinaryPathNamea; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  SC_HANDLE v12; // [rsp+70h] [rbp+8h] BYREF
  SC_HANDLE v13; // [rsp+80h] [rbp+18h] BYREF

  v12 = (SC_HANDLE)a1;
  v1 = OpenSCManagerW(0, L"ServicesActive", 0xF003Fu);
  v13 = v1;
  if ( v1 )
  {
    v12 = OpenServiceW(v1, L"wlidsvc", 2u);
    v4 = v12;
    if ( !v12 )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( v6 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x16,
          (unsigned int)"onecoreuap\\ds\\ext\\Live\\identity\\Include\\ServiceHelper.h",
          (const char *)(unsigned int)v6,
          lpBinaryPathName);
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v12);
        v3 = v6;
        goto LABEL_18;
      }
    }
    if ( !ChangeServiceConfigW(v4, 0xFFFFFFFF, 4u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
    {
      v7 = GetLastError();
      v3 = v7;
      if ( v7 > 0 )
        v3 = (unsigned __int16)v7 | 0x80070000;
      if ( v3 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1B,
          (unsigned int)"onecoreuap\\ds\\ext\\Live\\identity\\Include\\ServiceHelper.h",
          (const char *)(unsigned int)v3,
          lpBinaryPathNamea);
        wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v12);
        goto LABEL_18;
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v12);
LABEL_17:
    v3 = 0;
    goto LABEL_18;
  }
  v2 = GetLastError();
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( v3 >= 0 )
    goto LABEL_17;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xF,
    (unsigned int)"onecoreuap\\ds\\ext\\Live\\identity\\Include\\ServiceHelper.h",
    (const char *)(unsigned int)v3,
    lpBinaryPathName);
LABEL_18:
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v13);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800b1228  mov     [rsp+arg_8], rbx
0x1800b122d  mov     [rsp+arg_0], rcx
0x1800b1232  push    rdi
0x1800b1233  sub     rsp, 60h
0x1800b1237  mov     r8d, 0F003Fh; dwDesiredAccess
0x1800b123d  lea     rdx, DatabaseName; "ServicesActive"
0x1800b1244  xor     ecx, ecx; lpMachineName
0x1800b1246  call    cs:__imp_OpenSCManagerW
0x1800b124c  mov     [rsp+68h+arg_10], rax
0x1800b1254  test    rax, rax
0x1800b1257  jnz     short loc_1800B1294
0x1800b1259  call    cs:__imp_GetLastError
0x1800b125f  mov     ebx, eax
0x1800b1261  test    eax, eax
0x1800b1263  jle     short loc_1800B126E
0x1800b1265  movzx   ebx, ax
0x1800b1268  or      ebx, 80070000h
0x1800b126e  test    ebx, ebx
0x1800b1270  jns     loc_1800B139A
0x1800b1276  mov     rcx, [rsp+68h]; this
0x1800b127b  lea     r8, aOnecoreuapDsEx_29; "onecoreuap\\ds\\ext\\Live\\identity\\In"...
0x1800b1282  mov     r9d, ebx; char *
0x1800b1285  mov     edx, 0Fh; void *
0x1800b128a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b128f  jmp     loc_1800B139C
0x1800b1294  mov     r8d, 2; dwDesiredAccess
0x1800b129a  lea     rdx, ServiceName; "wlidsvc"
0x1800b12a1  mov     rcx, rax; hSCManager
0x1800b12a4  call    cs:__imp_OpenServiceW
0x1800b12aa  mov     [rsp+68h+arg_0], rax
0x1800b12af  mov     rbx, rax
0x1800b12b2  test    rax, rax
0x1800b12b5  jnz     short loc_1800B12FA
0x1800b12b7  call    cs:__imp_GetLastError
0x1800b12bd  mov     edi, eax
0x1800b12bf  test    eax, eax
0x1800b12c1  jle     short loc_1800B12CC
0x1800b12c3  movzx   edi, ax
0x1800b12c6  or      edi, 80070000h
0x1800b12cc  test    edi, edi
0x1800b12ce  jns     short loc_1800B12FA
0x1800b12d0  mov     rcx, [rsp+68h]; this
0x1800b12d5  lea     r8, aOnecoreuapDsEx_29; "onecoreuap\\ds\\ext\\Live\\identity\\In"...
0x1800b12dc  mov     r9d, edi; char *
0x1800b12df  mov     edx, 16h; void *
0x1800b12e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b12e9  lea     rcx, [rsp+68h+arg_0]
0x1800b12ee  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800b12f3  mov     ebx, edi
0x1800b12f5  jmp     loc_1800B139C
0x1800b12fa  mov     [rsp+68h+lpDisplayName], 0; lpDisplayName
0x1800b1303  or      edx, 0FFFFFFFFh; dwServiceType
0x1800b1306  mov     [rsp+68h+lpPassword], 0; lpPassword
0x1800b130f  mov     r9d, edx; dwErrorControl
0x1800b1312  mov     [rsp+68h+lpServiceStartName], 0; lpServiceStartName
0x1800b131b  mov     r8d, 4; dwStartType
0x1800b1321  mov     [rsp+68h+lpDependencies], 0; lpDependencies
0x1800b132a  mov     rcx, rbx; hService
0x1800b132d  mov     [rsp+68h+lpdwTagId], 0; lpdwTagId
0x1800b1336  mov     [rsp+68h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x1800b133f  mov     [rsp+68h+lpBinaryPathName], 0; int
0x1800b1348  call    cs:__imp_ChangeServiceConfigW
0x1800b134e  test    eax, eax
0x1800b1350  jnz     short loc_1800B1390
0x1800b1352  call    cs:__imp_GetLastError
0x1800b1358  mov     ebx, eax
0x1800b135a  test    eax, eax
0x1800b135c  jle     short loc_1800B1367
0x1800b135e  movzx   ebx, ax
0x1800b1361  or      ebx, 80070000h
0x1800b1367  test    ebx, ebx
0x1800b1369  jns     short loc_1800B1390
0x1800b136b  mov     rcx, [rsp+68h]; this
0x1800b1370  lea     r8, aOnecoreuapDsEx_29; "onecoreuap\\ds\\ext\\Live\\identity\\In"...
0x1800b1377  mov     r9d, ebx; char *
0x1800b137a  mov     edx, 1Bh; void *
0x1800b137f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b1384  lea     rcx, [rsp+68h+arg_0]
0x1800b1389  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800b138e  jmp     short loc_1800B139C
0x1800b1390  lea     rcx, [rsp+68h+arg_0]
0x1800b1395  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800b139a  xor     ebx, ebx
0x1800b139c  lea     rcx, [rsp+68h+arg_10]
0x1800b13a4  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800b13a9  mov     eax, ebx
0x1800b13ab  mov     rbx, [rsp+68h+arg_8]
0x1800b13b0  add     rsp, 60h
0x1800b13b4  pop     rdi
0x1800b13b5  retn
```
