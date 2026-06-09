# CreateOutprocAdviseRouterInstance

- ea: `0x180063fb0`
- end: `0x1800641e0`
- name: `CreateOutprocAdviseRouterInstance`
- size: `560`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180063e20`

## callees

- `0x1800068f0`
- `0x180013524`
- `0x180022544`
- `0x18002995c`
- `0x180063fb0`
- `0x1800c50f0`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800640ea`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800640ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800640fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800640fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006419b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800641b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006419b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800641b9`
- `RPCRT4!UuidCreate` at `0x180063fe3`
- `RPCRT4!UuidCreate` at `0x180063fe3`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18006415f`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800641aa`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18006415f`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800641aa`
- `api-ms-win-security-accesshlpr-l1-1-0!BuildSecurityDescriptorForSharingAccess` at `0x18006409d`
- `api-ms-win-security-accesshlpr-l1-1-0!BuildSecurityDescriptorForSharingAccess` at `0x18006409d`
- `UserDataPlatformHelperUtil!GetRpcClientThreadToken` at `0x18006405b`
- `UserDataPlatformHelperUtil!GetRpcClientThreadToken` at `0x18006405b`

## string_xrefs

- `0x180063ff5`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\rpcservice.cpp`
- `0x18006406d`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\rpcservice.cpp`
- `0x1800640af`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\rpcservice.cpp`
- `0x180064141`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\rpcservice.cpp`

## pseudocode

```c
__int64 __fastcall CreateOutprocAdviseRouterInstance(_QWORD *a1, unsigned __int16 *a2)
{
  int v4; // ebx
  __int64 v5; // r9
  int RpcClientThreadToken; // eax
  int v8; // eax
  HANDLE v9; // rdi
  signed int LastError; // eax
  __int64 v11; // r9
  __int64 v12; // rdx
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rbx
  void *v16; // rcx
  void *v17; // [rsp+40h] [rbp-9h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-1h] BYREF
  HANDLE v19; // [rsp+50h] [rbp+7h] BYREF
  __int64 v20; // [rsp+58h] [rbp+Fh] BYREF
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+60h] [rbp+17h] BYREF
  UUID Uuid; // [rsp+78h] [rbp+2Fh] BYREF

  Uuid = 0;
  v4 = UuidCreate(&Uuid);
  if ( v4 < 0 )
  {
    v5 = 270;
LABEL_3:
    Log_UnistoreHREvent_0(
      (unsigned int)v4,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\rpcservice.cpp",
      v5);
    return (unsigned int)v4;
  }
  v4 = StringCchPrintfW(
         a2,
         0x64u,
         L"Global\\USEvt-%08lx%08lx%08lx%08lx",
         Uuid.Data1,
         *(_DWORD *)&Uuid.Data2,
         *(_DWORD *)Uuid.Data4,
         *(_DWORD *)&Uuid.Data4[4]);
  if ( v4 < 0 )
  {
    v5 = 278;
    goto LABEL_3;
  }
  hObject = 0;
  RpcClientThreadToken = GetRpcClientThreadToken(8u, &hObject);
  v4 = RpcClientThreadToken;
  if ( RpcClientThreadToken < 0 )
  {
    Log_UnistoreHREvent_0(
      (unsigned int)RpcClientThreadToken,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\rpcservice.cpp",
      283);
LABEL_20:
    tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&hObject);
    return (unsigned int)v4;
  }
  v17 = 0;
  v8 = BuildSecurityDescriptorForSharingAccess(hObject, 0, 0x10000000, &v17);
  if ( v8 < 0 )
  {
    v4 = v8 | 0x10000000;
    Log_UnistoreHREvent_0(
      v8 | 0x10000000u,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\rpcservice.cpp",
      290);
    goto LABEL_18;
  }
  EventAttributes.lpSecurityDescriptor = v17;
  *(_QWORD *)&EventAttributes.nLength = 24;
  *(_QWORD *)&EventAttributes.bInheritHandle = 1;
  v19 = CreateEventW(&EventAttributes, 0, 0, a2);
  v9 = v19;
  if ( !v19 )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    v11 = 300;
    v12 = 0;
    v13 = (unsigned int)v4;
    goto LABEL_17;
  }
  v20 = 0;
  v14 = ATL::CComObject<AdviseRouter>::CreateInstance(&v20);
  v4 = v14;
  if ( v14 < 0 )
  {
    v11 = 305;
    v12 = 1;
    v13 = (unsigned int)v14;
LABEL_17:
    Log_UnistoreHREvent_0(
      v13,
      v12,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\rpcservice.cpp",
      v11);
    tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&v19);
LABEL_18:
    if ( v17 )
      FreeTransientObjectSecurityDescriptor(v17);
    goto LABEL_20;
  }
  v15 = v20;
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
  v16 = *(void **)(v15 + 80);
  *(_QWORD *)(v15 + 80) = v9;
  *a1 = v15;
  if ( v16 )
    CloseHandle(v16);
  if ( v17 )
    FreeTransientObjectSecurityDescriptor(v17);
  if ( hObject )
    CloseHandle(hObject);
  return 0;
}

```

## disassembly

```asm
0x180063fb0  mov     [rsp-8+arg_10], rbx
0x180063fb5  push    rbp
0x180063fb6  push    rsi
0x180063fb7  push    rdi
0x180063fb8  lea     rbp, [rsp-47h]
0x180063fbd  sub     rsp, 90h
0x180063fc4  mov     rax, cs:__security_cookie
0x180063fcb  xor     rax, rsp
0x180063fce  mov     [rbp+57h+var_18], rax
0x180063fd2  mov     rsi, rcx
0x180063fd5  xorps   xmm0, xmm0
0x180063fd8  lea     rcx, [rbp+57h+Uuid]; Uuid
0x180063fdc  mov     rdi, rdx
0x180063fdf  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x180063fe3  call    cs:__imp_UuidCreate
0x180063fe9  mov     ebx, eax
0x180063feb  test    eax, eax
0x180063fed  jns     short loc_18006400F
0x180063fef  mov     r9d, 10Eh
0x180063ff5  lea     r8, aOnecoreuapBase_28; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180063ffc  mov     edx, 1
0x180064001  mov     ecx, ebx
0x180064003  call    Log_UnistoreHREvent_0
0x180064008  mov     eax, ebx
0x18006400a  jmp     loc_1800641C1
0x18006400f  mov     eax, dword ptr [rbp+57h+Uuid.Data4+4]
0x180064012  lea     r8, aGlobalUsevt08l; "Global\\USEvt-%08lx%08lx%08lx%08lx"
0x180064019  mov     r9d, [rbp+57h+Uuid.Data1]
0x18006401d  mov     edx, 64h ; 'd'; unsigned __int64
0x180064022  mov     [rsp+0A0h+var_70], eax
0x180064026  mov     rcx, rdi; unsigned __int16 *
0x180064029  mov     eax, dword ptr [rbp+57h+Uuid.Data4]
0x18006402c  mov     [rsp+0A0h+var_78], eax
0x180064030  mov     eax, dword ptr [rbp+57h+Uuid.Data2]
0x180064033  mov     [rsp+0A0h+var_80], eax
0x180064037  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006403c  mov     ebx, eax
0x18006403e  test    eax, eax
0x180064040  jns     short loc_18006404A
0x180064042  mov     r9d, 116h
0x180064048  jmp     short loc_180063FF5
0x18006404a  lea     rdx, [rbp+57h+hObject]
0x18006404e  mov     [rbp+57h+hObject], 0
0x180064056  mov     ecx, 8
0x18006405b  call    cs:__imp_?GetRpcClientThreadToken@@YAJKPEAPEAX@Z; GetRpcClientThreadToken(ulong,void * *)
0x180064061  mov     ebx, eax
0x180064063  test    eax, eax
0x180064065  jns     short loc_180064085
0x180064067  mov     r9d, 11Bh
0x18006406d  lea     r8, aOnecoreuapBase_28; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180064074  mov     edx, 1
0x180064079  mov     ecx, eax
0x18006407b  call    Log_UnistoreHREvent_0
0x180064080  jmp     loc_180064165
0x180064085  mov     rcx, [rbp+57h+hObject]
0x180064089  lea     r9, [rbp+57h+var_60]
0x18006408d  xor     edx, edx
0x18006408f  mov     [rbp+57h+var_60], 0
0x180064097  mov     r8d, 10000000h
0x18006409d  call    cs:__imp_BuildSecurityDescriptorForSharingAccess
0x1800640a3  xor     edx, edx; bManualReset
0x1800640a5  mov     ebx, eax
0x1800640a7  test    eax, eax
0x1800640a9  jns     short loc_1800640C8
0x1800640ab  bts     ebx, 1Ch
0x1800640af  lea     r8, aOnecoreuapBase_28; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800640b6  mov     ecx, ebx
0x1800640b8  mov     r9d, 122h
0x1800640be  call    Log_UnistoreHREvent_0
0x1800640c3  jmp     loc_180064156
0x1800640c8  mov     rax, [rbp+57h+var_60]
0x1800640cc  lea     rcx, [rbp+57h+EventAttributes]; lpEventAttributes
0x1800640d0  mov     r9, rdi; lpName
0x1800640d3  mov     [rbp+57h+EventAttributes.lpSecurityDescriptor], rax
0x1800640d7  xor     r8d, r8d; bInitialState
0x1800640da  mov     qword ptr [rbp+57h+EventAttributes.nLength], 18h
0x1800640e2  mov     qword ptr [rbp+57h+EventAttributes.bInheritHandle], 1
0x1800640ea  call    cs:__imp_CreateEventW
0x1800640f0  mov     [rbp+57h+var_50], rax
0x1800640f4  mov     rdi, rax
0x1800640f7  test    rax, rax
0x1800640fa  jnz     short loc_18006411D
0x1800640fc  call    cs:__imp_GetLastError
0x180064102  mov     ebx, eax
0x180064104  test    eax, eax
0x180064106  jle     short loc_180064111
0x180064108  movzx   ebx, ax
0x18006410b  or      ebx, 80070000h
0x180064111  mov     r9d, 12Ch
0x180064117  xor     edx, edx
0x180064119  mov     ecx, ebx
0x18006411b  jmp     short loc_180064141
0x18006411d  lea     rcx, [rbp+57h+var_48]
0x180064121  mov     [rbp+57h+var_48], 0
0x180064129  call    ?CreateInstance@?$CComObject@VAdviseRouter@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<AdviseRouter>::CreateInstance(ATL::CComObject<AdviseRouter> * *)
0x18006412e  mov     ebx, eax
0x180064130  test    eax, eax
0x180064132  jns     short loc_180064173
0x180064134  mov     r9d, 131h
0x18006413a  mov     edx, 1
0x18006413f  mov     ecx, eax
0x180064141  lea     r8, aOnecoreuapBase_28; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180064148  call    Log_UnistoreHREvent_0
0x18006414d  lea     rcx, [rbp+57h+var_50]
0x180064151  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x180064156  mov     rcx, [rbp+57h+var_60]
0x18006415a  test    rcx, rcx
0x18006415d  jz      short loc_180064165
0x18006415f  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x180064165  lea     rcx, [rbp+57h+hObject]
0x180064169  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x18006416e  jmp     loc_180064008
0x180064173  mov     rbx, [rbp+57h+var_48]
0x180064177  test    rbx, rbx
0x18006417a  jz      short loc_18006418B
0x18006417c  mov     rax, [rbx]
0x18006417f  mov     rcx, rbx
0x180064182  mov     rax, [rax+8]
0x180064186  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006418b  mov     rcx, [rbx+50h]; hObject
0x18006418f  mov     [rbx+50h], rdi
0x180064193  mov     [rsi], rbx
0x180064196  test    rcx, rcx
0x180064199  jz      short loc_1800641A1
0x18006419b  call    cs:__imp_CloseHandle
0x1800641a1  mov     rcx, [rbp+57h+var_60]
0x1800641a5  test    rcx, rcx
0x1800641a8  jz      short loc_1800641B0
0x1800641aa  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x1800641b0  mov     rcx, [rbp+57h+hObject]; hObject
0x1800641b4  test    rcx, rcx
0x1800641b7  jz      short loc_1800641BF
0x1800641b9  call    cs:__imp_CloseHandle
0x1800641bf  xor     eax, eax
0x1800641c1  mov     rcx, [rbp+57h+var_18]
0x1800641c5  xor     rcx, rsp; StackCookie
0x1800641c8  call    __security_check_cookie
0x1800641cd  mov     rbx, [rsp+0A0h+arg_10]
0x1800641d5  add     rsp, 90h
0x1800641dc  pop     rdi
0x1800641dd  pop     rsi
0x1800641de  pop     rbp
0x1800641df  retn
```
