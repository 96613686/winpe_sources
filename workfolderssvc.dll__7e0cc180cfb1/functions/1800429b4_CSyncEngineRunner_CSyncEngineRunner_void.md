# CSyncEngineRunner::~CSyncEngineRunner(void)

- ea: `0x1800429b4`
- end: `0x180042b27`
- name: `??1CSyncEngineRunner@@QEAA@XZ`
- size: `371`
- prototype: `void __fastcall(CSyncEngineRunner *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180036fdc`

## callees

- `0x180007e10`
- `0x180009384`
- `0x180010d38`
- `0x180011314`
- `0x1800428e4`
- `0x1800429b4`
- `0x180042e28`
- `0x180047cb0`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x180042a54`
- `KERNEL32!SetThreadpoolTimer` at `0x180042a54`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180042a66`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180042a66`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180042ad6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180042afa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180042ad6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180042afa`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
void __fastcall CSyncEngineRunner::~CSyncEngineRunner(CSyncEngineRunner *this, bool a2)
{
  CSyncEngineRunner *v2; // rbx
  _BYTE *v3; // rax
  char v4; // al
  int v5; // [rsp+20h] [rbp-38h] BYREF
  const ATL::CAtlException *v6; // [rsp+28h] [rbp-30h] BYREF
  int v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+34h] [rbp-24h]
  char v9; // [rsp+38h] [rbp-20h]
  const char *v10; // [rsp+40h] [rbp-18h]
  __int64 v11; // [rsp+48h] [rbp-10h]
  __int64 v14; // [rsp+68h] [rbp+10h] BYREF
  char *v15; // [rsp+70h] [rbp+18h]

  v2 = this;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) == 0 )
    {
LABEL_8:
      v4 = 0;
      goto LABEL_9;
    }
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, WPP_dc9db4428004346aee7dbf67e68d245c_Traceguids);
      v3 = WPP_GLOBAL_Control;
    }
  }
  if ( (v3[68] & 8) == 0 || v3[65] < 6u )
    goto LABEL_8;
  v4 = 1;
LABEL_9:
  v7 = 0;
  v8 = 74;
  v9 = v4;
  v10 = "CSyncEngineRunner::~CSyncEngineRunner";
  v11 = 0;
  try
  {
    CEcsThreadPool::Cleanup((CSyncEngineRunner *)((char *)v2 + 256), a2);
    SetThreadpoolTimer(*((PTP_TIMER *)v2 + 22), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)v2 + 22), 1);
  }
  catch ( long v5 )
  {
    v7 = v5;
    v2 = this;
  }
  catch ( std::bad_alloc )
  {
    HIWORD(v8) = 90;
    v7 = -2147024882;
    v2 = this;
  }
  catch ( std::exception )
  {
    HIWORD(v8) = 90;
    v7 = -2147418113;
    v2 = this;
  }
  catch ( const ATL::CAtlException *v6 )
  {
    HIWORD(v8) = 90;
    v7 = *(_DWORD *)v6;
    v2 = this;
  }
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v7);
  std::wstring::~wstring((char *)v2 + 416);
  std::_Ptr_base<CEcsWebRequest::RequestBody>::_Decref((char *)v2 + 224);
  std::wstring::~wstring((char *)v2 + 192);
  v14 = 0;
  EcsUniqueHandle<_TP_TIMER *,Win32ThreadPoolTimerDeleter,0>::reset((char *)v2 + 176, &v14);
  std::_Ptr_base<CEcsWebRequest::RequestBody>::_Decref((char *)v2 + 160);
  DeleteCriticalSection((LPCRITICAL_SECTION)v2 + 3);
  v15 = (char *)v2 + 104;
  std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<PartnershipSyncState>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<PartnershipSyncState>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<PartnershipSyncState>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<PartnershipSyncState>>>,0>>();
  std::_Ptr_base<CEcsWebRequest::RequestBody>::_Decref((char *)v2 + 88);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)v2 + 48));
  std::_Ptr_base<CEcsWebRequest::RequestBody>::_Decref((char *)v2 + 32);
  std::_Ptr_base<CEcsWebRequest::RequestBody>::_Decref((char *)v2 + 16);
  std::_Ptr_base<CEcsWebRequest::RequestBody>::_Decref(v2);
}

```

## disassembly

```asm
0x1800429b4  mov     [rsp+arg_18], rbx
0x1800429b9  mov     [rsp+arg_0], rcx
0x1800429be  push    rdi
0x1800429bf  sub     rsp, 50h
0x1800429c3  mov     rbx, rcx
0x1800429c6  lea     rcx, WPP_GLOBAL_Control
0x1800429cd  mov     rax, cs:WPP_GLOBAL_Control
0x1800429d4  cmp     rax, rcx
0x1800429d7  jz      short loc_180042A01
0x1800429d9  test    byte ptr [rax+44h], 8
0x1800429dd  jz      short loc_180042A13
0x1800429df  cmp     byte ptr [rax+41h], 6
0x1800429e3  jb      short loc_180042A01
0x1800429e5  mov     edx, 0Ch
0x1800429ea  lea     r8, WPP_dc9db4428004346aee7dbf67e68d245c_Traceguids
0x1800429f1  mov     rcx, [rax+38h]
0x1800429f5  call    WPP_SF_
0x1800429fa  mov     rax, cs:WPP_GLOBAL_Control
0x180042a01  test    byte ptr [rax+44h], 8
0x180042a05  jz      short loc_180042A13
0x180042a07  cmp     byte ptr [rax+41h], 6
0x180042a0b  jb      short loc_180042A13
0x180042a0d  mov     al, 1
0x180042a0f  xor     edi, edi
0x180042a11  jmp     short loc_180042A18
0x180042a13  xor     edi, edi
0x180042a15  mov     al, dil
0x180042a18  mov     [rsp+58h+var_28], edi
0x180042a1c  mov     [rsp+58h+var_24], 4Ah ; 'J'
0x180042a24  mov     [rsp+58h+var_20], al
0x180042a28  lea     rax, aCsyncenginerun_0; "CSyncEngineRunner::~CSyncEngineRunner"
0x180042a2f  mov     [rsp+58h+var_18], rax
0x180042a34  mov     [rsp+58h+var_10], rdi
0x180042a39  lea     rcx, [rbx+100h]; this
0x180042a40  call    ?Cleanup@CEcsThreadPool@@QEAAX_N@Z; CEcsThreadPool::Cleanup(bool)
0x180042a45  xor     r9d, r9d; msWindowLength
0x180042a48  xor     r8d, r8d; msPeriod
0x180042a4b  xor     edx, edx; pftDueTime
0x180042a4d  mov     rcx, [rbx+0B0h]; pti
0x180042a54  call    cs:__imp_SetThreadpoolTimer
0x180042a5a  mov     edx, 1; fCancelPendingCallbacks
0x180042a5f  mov     rcx, [rbx+0B0h]; pti
0x180042a66  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180042a6c  nop
0x180042a6d  jmp     short loc_180042A7C
0x180042a6f  jmp     short loc_180042A75
0x180042a71  jmp     short loc_180042A75
0x180042a73  jmp     short $+2
0x180042a75  mov     rbx, [rsp+58h+arg_0]
0x180042a7a  xor     edi, edi
0x180042a7c  lea     rcx, [rsp+58h+var_28]; this
0x180042a81  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x180042a86  nop
0x180042a87  lea     rcx, [rbx+1A0h]
0x180042a8e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180042a93  nop
0x180042a94  lea     rcx, [rbx+0E0h]
0x180042a9b  call    ?_Decref@?$_Ptr_base@VRequestBody@CEcsWebRequest@@@std@@IEAAXXZ; std::_Ptr_base<CEcsWebRequest::RequestBody>::_Decref(void)
0x180042aa0  nop
0x180042aa1  lea     rcx, [rbx+0C0h]
0x180042aa8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180042aad  nop
0x180042aae  mov     [rsp+58h+arg_8], rdi
0x180042ab3  lea     rcx, [rbx+0B0h]
0x180042aba  lea     rdx, [rsp+58h+arg_8]
0x180042abf  call    ?reset@?$EcsUniqueHandle@PEAU_TP_TIMER@@UWin32ThreadPoolTimerDeleter@@$0A@@@QEAAXAEBQEAU_TP_TIMER@@@Z; EcsUniqueHandle<_TP_TIMER *,Win32ThreadPoolTimerDeleter,0>::reset(_TP_TIMER * const &)
0x180042ac4  nop
0x180042ac5  lea     rcx, [rbx+0A0h]
0x180042acc  call    ?_Decref@?$_Ptr_base@VRequestBody@CEcsWebRequest@@@std@@IEAAXXZ; std::_Ptr_base<CEcsWebRequest::RequestBody>::_Decref(void)
0x180042ad1  nop
0x180042ad2  lea     rcx, [rbx+78h]; lpCriticalSection
0x180042ad6  call    cs:__imp_DeleteCriticalSection
0x180042adc  nop
0x180042add  lea     rcx, [rbx+68h]
0x180042ae1  mov     [rsp+58h+arg_10], rcx
0x180042ae6  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPartnershipSyncState@@U?$default_delete@UPartnershipSyncState@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPartnershipSyncState@@U?$default_delete@UPartnershipSyncState@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<PartnershipSyncState>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<PartnershipSyncState>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<PartnershipSyncState>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<PartnershipSyncState>>>,0>>(void)
0x180042aeb  nop
0x180042aec  lea     rcx, [rbx+58h]
0x180042af0  call    ?_Decref@?$_Ptr_base@VRequestBody@CEcsWebRequest@@@std@@IEAAXXZ; std::_Ptr_base<CEcsWebRequest::RequestBody>::_Decref(void)
0x180042af5  nop
0x180042af6  lea     rcx, [rbx+30h]; lpCriticalSection
0x180042afa  call    cs:__imp_DeleteCriticalSection
0x180042b00  nop
0x180042b01  lea     rcx, [rbx+20h]
0x180042b05  call    ?_Decref@?$_Ptr_base@VRequestBody@CEcsWebRequest@@@std@@IEAAXXZ; std::_Ptr_base<CEcsWebRequest::RequestBody>::_Decref(void)
0x180042b0a  nop
0x180042b0b  lea     rcx, [rbx+10h]
0x180042b0f  call    ?_Decref@?$_Ptr_base@VRequestBody@CEcsWebRequest@@@std@@IEAAXXZ; std::_Ptr_base<CEcsWebRequest::RequestBody>::_Decref(void)
0x180042b14  nop
0x180042b15  mov     rcx, rbx
0x180042b18  mov     rbx, [rsp+58h+arg_18]
0x180042b1d  add     rsp, 50h
0x180042b21  pop     rdi
0x180042b22  jmp     ?_Decref@?$_Ptr_base@VRequestBody@CEcsWebRequest@@@std@@IEAAXXZ; std::_Ptr_base<CEcsWebRequest::RequestBody>::_Decref(void)
```
