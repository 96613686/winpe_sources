# OpenSessionWithSecurityContext(ServiceDataSession *,__MIDL_UserDataModelService_0001 * *,void * *)

- ea: `0x1800073f4`
- end: `0x18000775a`
- name: `?OpenSessionWithSecurityContext@@YAJPEAVServiceDataSession@@PEAPEAU__MIDL_UserDataModelService_0001@@PEAPEAX@Z`
- size: `870`
- prototype: `__int64 __fastcall(struct ServiceDataSession *, struct __MIDL_UserDataModelService_0001 **, void **)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800055e0`

## callees

- `0x1800073f4`
- `0x180007760`
- `0x1800077b4`
- `0x18000780c`
- `0x180007a60`
- `0x180008ee8`
- `0x180008f0c`
- `0x1800303cc`
- `0x1800354d4`
- `0x1800977c4`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180007471`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180007471`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000747f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800076dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000747f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800076dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800074cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800074d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800074cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800074d8`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800074fb`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800074fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000766e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000766e`

## string_xrefs

- `0x180007495`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x1800074af`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x180007605`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x18000767f`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x1800076ee`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`

## pseudocode

```c
__int64 __fastcall OpenSessionWithSecurityContext(
        struct ServiceDataSession *a1,
        struct __MIDL_UserDataModelService_0001 **a2,
        void **a3)
{
  void *v6; // rbx
  HANDLE v7; // rdi
  HANDLE EventW; // rax
  void *v9; // r14
  signed int v10; // eax
  unsigned int v11; // esi
  HANDLE CurrentProcess; // rsi
  HANDLE v13; // rax
  ServiceDataSession *v14; // rax
  ServiceDataSession *v15; // rax
  ServiceDataSession *v16; // rsi
  __int64 v17; // r8
  int v18; // r14d
  void *v19; // r14
  __int64 v21; // r8
  __int64 v22; // r8
  signed int LastError; // eax
  __int64 v24; // r9
  HANDLE TargetHandle; // [rsp+40h] [rbp-29h] BYREF
  HANDLE v26; // [rsp+48h] [rbp-21h] BYREF
  void *v27; // [rsp+50h] [rbp-19h] BYREF
  _QWORD v28[2]; // [rsp+58h] [rbp-11h] BYREF
  _BYTE v29[16]; // [rsp+68h] [rbp-1h] BYREF
  _QWORD *v30; // [rsp+78h] [rbp+Fh]
  __int64 v31; // [rsp+80h] [rbp+17h]

  if ( (Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits & 0x10000) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &MICROSOFT_WINDOWS_USERDATAACCESS_USERDATASVC_Context,
      Udm_OpenSession_START,
      a3,
      1,
      v28);
  *a2 = 0;
  v6 = 0;
  v27 = 0;
  *a3 = 0;
  v26 = 0;
  v7 = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  v9 = EventW;
  if ( EventW )
  {
    v28[0] = EventW;
    TargetHandle = 0;
    CurrentProcess = GetCurrentProcess();
    v13 = GetCurrentProcess();
    if ( DuplicateHandle(v13, v9, CurrentProcess, &TargetHandle, 0x100000u, 0, 0) )
    {
      v7 = TargetHandle;
      v6 = v9;
      v27 = v9;
      v26 = TargetHandle;
      goto LABEL_11;
    }
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    Log_HREvent(
      v11,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      2864);
    tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&TargetHandle);
    tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(v28);
  }
  else
  {
    v10 = GetLastError();
    v11 = v10;
    if ( v10 > 0 )
      v11 = (unsigned __int16)v10 | 0x80070000;
    Log_HREvent(
      v11,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      2853);
  }
  if ( (v11 & 0x80000000) != 0 )
  {
    Log_HREvent(
      v11,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      3238);
LABEL_20:
    lambda_023a1e2ddd76ace682cc3c4d2cbc627e_::operator()();
    return v11;
  }
LABEL_11:
  v14 = (ServiceDataSession *)operator new(0x7F8u);
  if ( !v14 )
  {
    TargetHandle = 0;
    goto LABEL_22;
  }
  v15 = ServiceDataSession::ServiceDataSession(v14);
  TargetHandle = v15;
  v16 = v15;
  if ( !v15 )
  {
LABEL_22:
    Log_HREvent(
      2147942414LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      3242);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&TargetHandle);
    tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&v26);
    tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&v27);
    if ( (Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits & 0x10000) != 0 )
      McGenEventWrite_EventWriteTransfer(
        &MICROSOFT_WINDOWS_USERDATAACCESS_USERDATASVC_Context,
        Udm_OpenSession_STOP,
        v21,
        1,
        v28);
    return 2147942414LL;
  }
  v18 = AddServiceDataSession(v15);
  if ( v18 < 0 )
  {
    v24 = 3244;
  }
  else
  {
    if ( !a1 || (v18 = ServiceDataSession::InitializeSecurityContextFrom(v16, a1), v18 >= 0) )
    {
      v19 = (void *)*((_QWORD *)v16 + 9);
      *((_QWORD *)v16 + 9) = v6;
      *a2 = v16;
      *a3 = v7;
      if ( (Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits & 0x10) != 0 )
      {
        v28[0] = *a2;
        v31 = 8;
        v30 = v28;
        McGenEventWrite_EventWriteTransfer(
          &MICROSOFT_WINDOWS_USERDATAACCESS_USERDATASVC_Context,
          OpenedDataSession,
          v17,
          2,
          v29);
      }
      (*(void (__fastcall **)(ServiceDataSession *))(*(_QWORD *)v16 + 16LL))(v16);
      if ( v19 )
        CloseHandle(v19);
      v11 = 0;
      goto LABEL_20;
    }
    v24 = 3248;
  }
  Log_HREvent(
    (unsigned int)v18,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
    v24);
  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&TargetHandle);
  tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&v26);
  tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&v27);
  if ( (Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits & 0x10000) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &MICROSOFT_WINDOWS_USERDATAACCESS_USERDATASVC_Context,
      Udm_OpenSession_STOP,
      v22,
      1,
      v28);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x1800073f4  mov     [rsp-8+arg_18], rbx
0x1800073f9  push    rbp
0x1800073fa  push    rsi
0x1800073fb  push    rdi
0x1800073fc  push    r12
0x1800073fe  push    r13
0x180007400  push    r14
0x180007402  push    r15
0x180007404  lea     rbp, [rsp-27h]
0x180007409  sub     rsp, 90h
0x180007410  mov     rax, cs:__security_cookie
0x180007417  xor     rax, rsp
0x18000741a  mov     [rbp+57h+var_38], rax
0x18000741e  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits+2, 1
0x180007425  mov     r13, r8
0x180007428  mov     r15, rdx
0x18000742b  mov     r12, rcx
0x18000742e  jz      short loc_180007452
0x180007430  lea     rax, [rbp+57h+var_68]
0x180007434  mov     r9d, 1
0x18000743a  lea     rdx, Udm_OpenSession_START
0x180007441  mov     qword ptr [rsp+0C0h+dwDesiredAccess], rax
0x180007446  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_USERDATASVC_Context
0x18000744d  call    McGenEventWrite_EventWriteTransfer
0x180007452  xor     esi, esi
0x180007454  xor     r9d, r9d; lpName
0x180007457  mov     [r15], rsi
0x18000745a  mov     ebx, esi
0x18000745c  xor     r8d, r8d; bInitialState
0x18000745f  mov     [rbp+57h+var_70], rbx
0x180007463  xor     edx, edx; bManualReset
0x180007465  mov     [r13+0], rsi
0x180007469  xor     ecx, ecx; lpEventAttributes
0x18000746b  mov     [rbp+57h+var_78], rsi
0x18000746f  mov     edi, esi
0x180007471  call    cs:__imp_CreateEventW
0x180007477  mov     r14, rax
0x18000747a  test    rax, rax
0x18000747d  jnz     short loc_1800074C7
0x18000747f  call    cs:__imp_GetLastError
0x180007485  mov     esi, eax
0x180007487  test    eax, eax
0x180007489  jg      loc_180007720
0x18000748f  mov     r9d, 0B25h
0x180007495  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000749c  xor     edx, edx
0x18000749e  mov     ecx, esi
0x1800074a0  call    Log_HREvent
0x1800074a5  test    esi, esi
0x1800074a7  jns     short loc_180007518
0x1800074a9  mov     r9d, 0CA6h
0x1800074af  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800074b6  mov     edx, 1
0x1800074bb  mov     ecx, esi
0x1800074bd  call    Log_HREvent
0x1800074c2  jmp     loc_1800075CA
0x1800074c7  mov     [rbp+57h+var_68], r14
0x1800074cb  mov     [rbp+57h+TargetHandle], rsi
0x1800074cf  call    cs:__imp_GetCurrentProcess
0x1800074d5  mov     rsi, rax
0x1800074d8  call    cs:__imp_GetCurrentProcess
0x1800074de  mov     [rsp+0C0h+dwOptions], ebx; dwOptions
0x1800074e2  lea     r9, [rbp+57h+TargetHandle]; lpTargetHandle
0x1800074e6  mov     rcx, rax; hSourceProcessHandle
0x1800074e9  mov     [rsp+0C0h+bInheritHandle], ebx; bInheritHandle
0x1800074ed  mov     r8, rsi; hTargetProcessHandle
0x1800074f0  mov     [rsp+0C0h+dwDesiredAccess], 100000h; dwDesiredAccess
0x1800074f8  mov     rdx, r14; hSourceHandle
0x1800074fb  call    cs:__imp_DuplicateHandle
0x180007501  test    eax, eax
0x180007503  jz      loc_1800076DC
0x180007509  mov     rdi, [rbp+57h+TargetHandle]
0x18000750d  mov     rbx, r14
0x180007510  mov     [rbp+57h+var_70], rbx
0x180007514  mov     [rbp+57h+var_78], rdi
0x180007518  mov     ecx, 7F8h; Size
0x18000751d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007522  test    rax, rax
0x180007525  jz      loc_1800075F8
0x18000752b  mov     rcx, rax; this
0x18000752e  call    ??0ServiceDataSession@@QEAA@XZ; ServiceDataSession::ServiceDataSession(void)
0x180007533  mov     [rbp+57h+TargetHandle], rax
0x180007537  mov     rsi, rax
0x18000753a  test    rax, rax
0x18000753d  jz      loc_180007600
0x180007543  mov     rcx, rax; struct ServiceDataSession *
0x180007546  call    ?AddServiceDataSession@@YAJPEAVServiceDataSession@@@Z; AddServiceDataSession(ServiceDataSession *)
0x18000754b  mov     r14d, eax
0x18000754e  test    eax, eax
0x180007550  js      loc_18000772E
0x180007556  test    r12, r12
0x180007559  jnz     loc_180007739
0x18000755f  mov     r14, [rsi+48h]
0x180007563  mov     [rsi+48h], rbx
0x180007567  mov     [r15], rsi
0x18000756a  mov     [r13+0], rdi
0x18000756e  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits, 10h
0x180007575  jz      short loc_1800075B0
0x180007577  mov     rax, [r15]
0x18000757a  lea     rdx, OpenedDataSession
0x180007581  mov     [rbp+57h+var_68], rax
0x180007585  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_USERDATASVC_Context
0x18000758c  lea     rax, [rbp+57h+var_68]
0x180007590  mov     [rbp+57h+var_40], 8
0x180007598  mov     [rbp+57h+var_48], rax
0x18000759c  mov     r9d, 2
0x1800075a2  lea     rax, [rbp+57h+var_58]
0x1800075a6  mov     qword ptr [rsp+0C0h+dwDesiredAccess], rax
0x1800075ab  call    McGenEventWrite_EventWriteTransfer
0x1800075b0  mov     rax, [rsi]
0x1800075b3  mov     rcx, rsi
0x1800075b6  mov     rax, [rax+10h]
0x1800075ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075bf  test    r14, r14
0x1800075c2  jnz     loc_18000766B
0x1800075c8  xor     esi, esi
0x1800075ca  call    _lambda_023a1e2ddd76ace682cc3c4d2cbc627e___operator__
0x1800075cf  mov     eax, esi
0x1800075d1  mov     rcx, [rbp+57h+var_38]
0x1800075d5  xor     rcx, rsp; StackCookie
0x1800075d8  call    __security_check_cookie
0x1800075dd  mov     rbx, [rsp+0C0h+arg_18]
0x1800075e5  add     rsp, 90h
0x1800075ec  pop     r15
0x1800075ee  pop     r14
0x1800075f0  pop     r13
0x1800075f2  pop     r12
0x1800075f4  pop     rdi
0x1800075f5  pop     rsi
0x1800075f6  pop     rbp
0x1800075f7  retn
0x1800075f8  mov     [rbp+57h+TargetHandle], 0
0x180007600  mov     ebx, 8007000Eh
0x180007605  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000760c  mov     ecx, ebx
0x18000760e  mov     r9d, 0CAAh
0x180007614  xor     edx, edx
0x180007616  call    Log_HREvent
0x18000761b  lea     rcx, [rbp+57h+TargetHandle]
0x18000761f  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x180007624  lea     rcx, [rbp+57h+var_78]
0x180007628  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x18000762d  lea     rcx, [rbp+57h+var_70]
0x180007631  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x180007636  mov     r15d, 1
0x18000763c  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits+2, r15b
0x180007643  jz      short loc_180007664
0x180007645  lea     rcx, [rbp+57h+var_68]
0x180007649  mov     r9d, r15d
0x18000764c  mov     qword ptr [rsp+0C0h+dwDesiredAccess], rcx
0x180007651  lea     rdx, Udm_OpenSession_STOP
0x180007658  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_USERDATASVC_Context
0x18000765f  call    McGenEventWrite_EventWriteTransfer
0x180007664  mov     eax, ebx
0x180007666  jmp     loc_1800075D1
0x18000766b  mov     rcx, r14; hObject
0x18000766e  call    cs:__imp_CloseHandle
0x180007674  jmp     loc_1800075C8
0x180007679  mov     r15d, 1
0x18000767f  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180007686  mov     edx, r15d
0x180007689  mov     ecx, r14d
0x18000768c  call    Log_HREvent
0x180007691  lea     rcx, [rbp+57h+TargetHandle]
0x180007695  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x18000769a  lea     rcx, [rbp+57h+var_78]
0x18000769e  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x1800076a3  lea     rcx, [rbp+57h+var_70]
0x1800076a7  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x1800076ac  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits+2, r15b
0x1800076b3  jz      short loc_1800076D4
0x1800076b5  lea     rax, [rbp+57h+var_68]
0x1800076b9  mov     r9d, r15d
0x1800076bc  lea     rdx, Udm_OpenSession_STOP
0x1800076c3  mov     qword ptr [rsp+0C0h+dwDesiredAccess], rax
0x1800076c8  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_USERDATASVC_Context
0x1800076cf  call    McGenEventWrite_EventWriteTransfer
0x1800076d4  mov     eax, r14d
0x1800076d7  jmp     loc_1800075D1
0x1800076dc  call    cs:__imp_GetLastError
0x1800076e2  mov     esi, eax
0x1800076e4  test    eax, eax
0x1800076e6  jg      short loc_180007715
0x1800076e8  mov     r9d, 0B30h
0x1800076ee  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800076f5  xor     edx, edx
0x1800076f7  mov     ecx, esi
0x1800076f9  call    Log_HREvent
0x1800076fe  lea     rcx, [rbp+57h+TargetHandle]
0x180007702  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x180007707  lea     rcx, [rbp+57h+var_68]
0x18000770b  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x180007710  jmp     loc_1800074A5
0x180007715  movzx   esi, ax
0x180007718  or      esi, 80070000h
0x18000771e  jmp     short loc_1800076E8
0x180007720  movzx   esi, ax
0x180007723  or      esi, 80070000h
0x180007729  jmp     loc_18000748F
0x18000772e  mov     r9d, 0CACh
0x180007734  jmp     loc_180007679
0x180007739  mov     rdx, r12; struct ServiceDataSession *
0x18000773c  mov     rcx, rsi; this
0x18000773f  call    ?InitializeSecurityContextFrom@ServiceDataSession@@QEAAJPEAV1@@Z; ServiceDataSession::InitializeSecurityContextFrom(ServiceDataSession *)
0x180007744  mov     r14d, eax
0x180007747  test    eax, eax
0x180007749  jns     loc_18000755F
0x18000774f  mov     r9d, 0CB0h
0x180007755  jmp     loc_180007679
```
