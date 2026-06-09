# UdmSvcImpl_OpenSession

- ea: `0x180006fc0`
- end: `0x1800072ed`
- name: `UdmSvcImpl_OpenSession`
- size: `813`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006fc0`
- `0x180007760`
- `0x1800077b4`
- `0x18000780c`
- `0x180007a60`
- `0x180008ee8`
- `0x180008f0c`
- `0x1800303cc`
- `0x1800977c4`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180007042`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180007042`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007050`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000725e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007050`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000725e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800070c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800070cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800070c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800070cf`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800070f2`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800070f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800071b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800071b4`

## string_xrefs

- `0x180007066`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x180007084`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x1800070a6`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x1800071f6`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x180007270`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x1800072b6`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`

## pseudocode

```c
__int64 __fastcall UdmSvcImpl_OpenSession(__int64 a1, ServiceDataSession **a2, _QWORD *a3)
{
  HANDLE v5; // rdi
  void *v6; // rbx
  HANDLE EventW; // rax
  void *v8; // r14
  signed int v9; // eax
  unsigned int v10; // esi
  HANDLE CurrentProcess; // rsi
  HANDLE v13; // rax
  ServiceDataSession *v14; // rax
  ServiceDataSession *v15; // rax
  ServiceDataSession *v16; // r14
  int v17; // eax
  __int64 v18; // r8
  void *v19; // rsi
  __int64 v20; // r8
  signed int LastError; // eax
  HANDLE TargetHandle; // [rsp+40h] [rbp-19h] BYREF
  HANDLE v23; // [rsp+48h] [rbp-11h] BYREF
  void *v24; // [rsp+50h] [rbp-9h] BYREF
  _QWORD v25[2]; // [rsp+58h] [rbp-1h] BYREF
  char v26[16]; // [rsp+68h] [rbp+Fh] BYREF
  _QWORD *v27; // [rsp+78h] [rbp+1Fh]
  __int64 v28; // [rsp+80h] [rbp+27h]

  if ( (Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits & 0x10000) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &MICROSOFT_WINDOWS_USERDATAACCESS_USERDATASVC_Context,
      Udm_OpenSession_START,
      a3,
      1,
      v25);
  *a2 = 0;
  v5 = 0;
  v6 = 0;
  v23 = 0;
  v24 = 0;
  *a3 = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  v8 = EventW;
  if ( EventW )
  {
    v25[0] = EventW;
    TargetHandle = 0;
    CurrentProcess = GetCurrentProcess();
    v13 = GetCurrentProcess();
    if ( DuplicateHandle(v13, v8, CurrentProcess, &TargetHandle, 0x100000u, 0, 0) )
    {
      v5 = TargetHandle;
      v6 = v8;
      v24 = v8;
      v23 = TargetHandle;
      goto LABEL_12;
    }
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    Log_HREvent(
      v10,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      2864);
    tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&TargetHandle);
    tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(v25);
  }
  else
  {
    v9 = GetLastError();
    v10 = v9;
    if ( v9 > 0 )
      v10 = (unsigned __int16)v9 | 0x80070000;
    Log_HREvent(
      v10,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      2853);
  }
  if ( (v10 & 0x80000000) != 0 )
  {
    Log_HREvent(
      v10,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      3238);
    lambda_023a1e2ddd76ace682cc3c4d2cbc627e_::operator()();
LABEL_9:
    Log_HREvent(
      v10,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      3266);
    return v10;
  }
LABEL_12:
  v14 = (ServiceDataSession *)operator new(0x7F8u);
  if ( !v14 )
  {
    TargetHandle = 0;
    goto LABEL_21;
  }
  v15 = ServiceDataSession::ServiceDataSession(v14);
  TargetHandle = v15;
  v16 = v15;
  if ( !v15 )
  {
LABEL_21:
    v10 = -2147024882;
    Log_HREvent(
      2147942414LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      3242);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&TargetHandle);
    tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&v23);
    tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&v24);
    goto LABEL_22;
  }
  v17 = AddServiceDataSession(v15);
  v10 = v17;
  if ( v17 < 0 )
  {
    Log_HREvent(
      (unsigned int)v17,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      3244);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&TargetHandle);
    tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&v23);
    tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&v24);
LABEL_22:
    if ( (Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits & 0x10000) != 0 )
      McGenEventWrite_EventWriteTransfer(
        &MICROSOFT_WINDOWS_USERDATAACCESS_USERDATASVC_Context,
        Udm_OpenSession_STOP,
        v20,
        1,
        v25);
    goto LABEL_9;
  }
  v19 = (void *)*((_QWORD *)v16 + 9);
  *((_QWORD *)v16 + 9) = v6;
  *a2 = v16;
  *a3 = v5;
  if ( (Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits & 0x10) != 0 )
  {
    v25[0] = *a2;
    v28 = 8;
    v27 = v25;
    McGenEventWrite_EventWriteTransfer(
      &MICROSOFT_WINDOWS_USERDATAACCESS_USERDATASVC_Context,
      OpenedDataSession,
      v18,
      2,
      v26);
  }
  (*(void (__fastcall **)(ServiceDataSession *))(*(_QWORD *)v16 + 16LL))(v16);
  if ( v19 )
    CloseHandle(v19);
  lambda_023a1e2ddd76ace682cc3c4d2cbc627e_::operator()();
  return 0;
}

```

## disassembly

```asm
0x180006fc0  mov     [rsp-8+arg_0], rbx
0x180006fc5  mov     [rsp-8+arg_18], rsi
0x180006fca  push    rbp
0x180006fcb  push    rdi
0x180006fcc  push    r12
0x180006fce  push    r14
0x180006fd0  push    r15
0x180006fd2  lea     rbp, [rsp-37h]
0x180006fd7  sub     rsp, 90h
0x180006fde  mov     rax, cs:__security_cookie
0x180006fe5  xor     rax, rsp
0x180006fe8  mov     [rbp+57h+var_28], rax
0x180006fec  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits+2, 1
0x180006ff3  mov     r12, r8
0x180006ff6  mov     r15, rdx
0x180006ff9  jz      short loc_18000701D
0x180006ffb  lea     rax, [rbp+57h+var_58]
0x180006fff  mov     r9d, 1
0x180007005  lea     rdx, Udm_OpenSession_START
0x18000700c  mov     qword ptr [rsp+0B0h+dwDesiredAccess], rax
0x180007011  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_USERDATASVC_Context
0x180007018  call    McGenEventWrite_EventWriteTransfer
0x18000701d  mov     qword ptr [r15], 0
0x180007024  xor     edi, edi
0x180007026  xor     ebx, ebx
0x180007028  mov     [rbp+57h+var_68], rdi
0x18000702c  xor     r9d, r9d; lpName
0x18000702f  mov     [rbp+57h+var_60], rbx
0x180007033  xor     r8d, r8d; bInitialState
0x180007036  mov     qword ptr [r12], 0
0x18000703e  xor     edx, edx; bManualReset
0x180007040  xor     ecx, ecx; lpEventAttributes
0x180007042  call    cs:__imp_CreateEventW
0x180007048  mov     r14, rax
0x18000704b  test    rax, rax
0x18000704e  jnz     short loc_1800070BE
0x180007050  call    cs:__imp_GetLastError
0x180007056  mov     esi, eax
0x180007058  test    eax, eax
0x18000705a  jg      loc_1800072A2
0x180007060  mov     r9d, 0B25h
0x180007066  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000706d  xor     edx, edx
0x18000706f  mov     ecx, esi
0x180007071  call    Log_HREvent
0x180007076  test    esi, esi
0x180007078  jns     loc_18000710F
0x18000707e  mov     r14d, 1
0x180007084  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000708b  mov     edx, r14d
0x18000708e  mov     r9d, 0CA6h
0x180007094  mov     ecx, esi
0x180007096  call    Log_HREvent
0x18000709b  call    _lambda_023a1e2ddd76ace682cc3c4d2cbc627e___operator__
0x1800070a0  mov     r9d, 0CC2h
0x1800070a6  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800070ad  mov     edx, r14d
0x1800070b0  mov     ecx, esi
0x1800070b2  call    Log_HREvent
0x1800070b7  mov     eax, esi
0x1800070b9  jmp     loc_1800071C1
0x1800070be  mov     [rbp+57h+var_58], r14
0x1800070c2  mov     [rbp+57h+TargetHandle], rbx
0x1800070c6  call    cs:__imp_GetCurrentProcess
0x1800070cc  mov     rsi, rax
0x1800070cf  call    cs:__imp_GetCurrentProcess
0x1800070d5  mov     [rsp+0B0h+dwOptions], ebx; dwOptions
0x1800070d9  lea     r9, [rbp+57h+TargetHandle]; lpTargetHandle
0x1800070dd  mov     rcx, rax; hSourceProcessHandle
0x1800070e0  mov     [rsp+0B0h+bInheritHandle], ebx; bInheritHandle
0x1800070e4  mov     r8, rsi; hTargetProcessHandle
0x1800070e7  mov     [rsp+0B0h+dwDesiredAccess], 100000h; dwDesiredAccess
0x1800070ef  mov     rdx, r14; hSourceHandle
0x1800070f2  call    cs:__imp_DuplicateHandle
0x1800070f8  test    eax, eax
0x1800070fa  jz      loc_18000725E
0x180007100  mov     rdi, [rbp+57h+TargetHandle]
0x180007104  mov     rbx, r14
0x180007107  mov     [rbp+57h+var_60], rbx
0x18000710b  mov     [rbp+57h+var_68], rdi
0x18000710f  mov     ecx, 7F8h; Size
0x180007114  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007119  test    rax, rax
0x18000711c  jz      loc_1800071E9
0x180007122  mov     rcx, rax; this
0x180007125  call    ??0ServiceDataSession@@QEAA@XZ; ServiceDataSession::ServiceDataSession(void)
0x18000712a  mov     [rbp+57h+TargetHandle], rax
0x18000712e  mov     r14, rax
0x180007131  test    rax, rax
0x180007134  jz      loc_1800071F1
0x18000713a  mov     rcx, rax; struct ServiceDataSession *
0x18000713d  call    ?AddServiceDataSession@@YAJPEAVServiceDataSession@@@Z; AddServiceDataSession(ServiceDataSession *)
0x180007142  mov     esi, eax
0x180007144  test    eax, eax
0x180007146  js      loc_1800072B0
0x18000714c  mov     rsi, [r14+48h]
0x180007150  mov     [r14+48h], rbx
0x180007154  mov     [r15], r14
0x180007157  mov     [r12], rdi
0x18000715b  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits, 10h
0x180007162  jz      short loc_18000719D
0x180007164  mov     rax, [r15]
0x180007167  lea     rdx, OpenedDataSession
0x18000716e  mov     [rbp+57h+var_58], rax
0x180007172  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_USERDATASVC_Context
0x180007179  lea     rax, [rbp+57h+var_58]
0x18000717d  mov     [rbp+57h+var_30], 8
0x180007185  mov     [rbp+57h+var_38], rax
0x180007189  mov     r9d, 2
0x18000718f  lea     rax, [rbp+57h+var_48]
0x180007193  mov     qword ptr [rsp+0B0h+dwDesiredAccess], rax
0x180007198  call    McGenEventWrite_EventWriteTransfer
0x18000719d  mov     rax, [r14]
0x1800071a0  mov     rcx, r14
0x1800071a3  mov     rax, [rax+10h]
0x1800071a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071ac  test    rsi, rsi
0x1800071af  jz      short loc_1800071BA
0x1800071b1  mov     rcx, rsi; hObject
0x1800071b4  call    cs:__imp_CloseHandle
0x1800071ba  call    _lambda_023a1e2ddd76ace682cc3c4d2cbc627e___operator__
0x1800071bf  xor     eax, eax
0x1800071c1  mov     rcx, [rbp+57h+var_28]
0x1800071c5  xor     rcx, rsp; StackCookie
0x1800071c8  call    __security_check_cookie
0x1800071cd  lea     r11, [rsp+0B0h+var_20]
0x1800071d5  mov     rbx, [r11+30h]
0x1800071d9  mov     rsi, [r11+48h]
0x1800071dd  mov     rsp, r11
0x1800071e0  pop     r15
0x1800071e2  pop     r14
0x1800071e4  pop     r12
0x1800071e6  pop     rdi
0x1800071e7  pop     rbp
0x1800071e8  retn
0x1800071e9  mov     [rbp+57h+TargetHandle], 0
0x1800071f1  mov     esi, 8007000Eh
0x1800071f6  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800071fd  mov     ecx, esi
0x1800071ff  mov     r9d, 0CAAh
0x180007205  xor     edx, edx
0x180007207  call    Log_HREvent
0x18000720c  lea     rcx, [rbp+57h+TargetHandle]
0x180007210  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x180007215  lea     rcx, [rbp+57h+var_68]
0x180007219  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x18000721e  lea     rcx, [rbp+57h+var_60]
0x180007222  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x180007227  mov     r14d, 1
0x18000722d  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits+2, r14b
0x180007234  jz      loc_1800070A0
0x18000723a  lea     rax, [rbp+57h+var_58]
0x18000723e  mov     r9d, r14d
0x180007241  lea     rdx, Udm_OpenSession_STOP
0x180007248  mov     qword ptr [rsp+0B0h+dwDesiredAccess], rax
0x18000724d  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_USERDATASVC_Context
0x180007254  call    McGenEventWrite_EventWriteTransfer
0x180007259  jmp     loc_1800070A0
0x18000725e  call    cs:__imp_GetLastError
0x180007264  mov     esi, eax
0x180007266  test    eax, eax
0x180007268  jg      short loc_180007297
0x18000726a  mov     r9d, 0B30h
0x180007270  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180007277  xor     edx, edx
0x180007279  mov     ecx, esi
0x18000727b  call    Log_HREvent
0x180007280  lea     rcx, [rbp+57h+TargetHandle]
0x180007284  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x180007289  lea     rcx, [rbp+57h+var_58]
0x18000728d  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x180007292  jmp     loc_180007076
0x180007297  movzx   esi, ax
0x18000729a  or      esi, 80070000h
0x1800072a0  jmp     short loc_18000726A
0x1800072a2  movzx   esi, ax
0x1800072a5  or      esi, 80070000h
0x1800072ab  jmp     loc_180007060
0x1800072b0  mov     r14d, 1
0x1800072b6  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800072bd  mov     edx, r14d
0x1800072c0  mov     r9d, 0CACh
0x1800072c6  mov     ecx, eax
0x1800072c8  call    Log_HREvent
0x1800072cd  lea     rcx, [rbp+57h+TargetHandle]
0x1800072d1  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800072d6  lea     rcx, [rbp+57h+var_68]
0x1800072da  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x1800072df  lea     rcx, [rbp+57h+var_60]
0x1800072e3  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x1800072e8  jmp     loc_18000722D
```
