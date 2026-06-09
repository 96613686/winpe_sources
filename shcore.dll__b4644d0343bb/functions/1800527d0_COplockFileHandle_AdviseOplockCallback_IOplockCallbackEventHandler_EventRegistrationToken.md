# COplockFileHandle::AdviseOplockCallback(IOplockCallbackEventHandler *,EventRegistrationToken *)

- ea: `0x1800527d0`
- end: `0x18005290f`
- name: `?AdviseOplockCallback@COplockFileHandle@@UEAAJPEAUIOplockCallbackEventHandler@@PEAUEventRegistrationToken@@@Z`
- size: `319`
- prototype: `int(COplockFileHandle *__hidden this, struct IOplockCallbackEventHandler *, struct EventRegistrationToken *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180013578`
- `0x180035ae0`
- `0x18003dac0`
- `0x1800403a0`
- `0x180040b24`
- `0x18004a104`
- `0x1800527d0`
- `0x1800783c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800528d6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800528d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800528f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800528f5`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800528bb`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800528bb`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180052875`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180052875`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180052891`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180052891`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall COplockFileHandle::AdviseOplockCallback(
        COplockFileHandle *this,
        struct IUnknown *a2,
        struct EventRegistrationToken *a3)
{
  int CallingProcessHandle; // ebx
  __int64 v7; // rdx
  signed int LastError; // eax
  int v10; // edx
  unsigned int v11; // r8d
  int v12; // [rsp+20h] [rbp-10h] BYREF
  HANDLE hMutex; // [rsp+28h] [rbp-8h]
  HANDLE Process; // [rsp+50h] [rbp+20h] BYREF
  unsigned int Pid; // [rsp+68h] [rbp+38h] BYREF

  Microsoft::WRL::Wrappers::Mutex::Lock(&v12, *((_QWORD *)this + 20), 0xFFFFFFFFLL);
  if ( *((_DWORD *)this + 32) )
  {
    CallingProcessHandle = -2147024093;
  }
  else
  {
    if ( a2 )
    {
      CallingProcessHandle = Microsoft::WRL::EventSource<IOplockCallbackEventHandler,Microsoft::WRL::InvokeModeOptions<2>>::AddInternal(
                               (char *)this + 200,
                               a2,
                               a2->lpVtbl[1].QueryInterface,
                               a3);
      if ( CallingProcessHandle >= 0 && !(unsigned int)IsObjectSecurelyCallableInProcess(a2) )
      {
        Pid = 0;
        Process = 0;
        CallingProcessHandle = CallerIdentity::GetCallingProcessHandle(4096, v7, &Process);
        if ( CallingProcessHandle >= 0 )
          Pid = GetProcessId(Process);
        CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&Process);
        if ( CallingProcessHandle >= 0 || !I_RpcBindingInqLocalClientPID(0, &Pid) )
        {
          LOBYTE(Process) = 0;
          CallingProcessHandle = Windows::Foundation::Collections::Internal::HashMap<EventRegistrationToken,int,XWinRT::PodTypeHash,EventRegistrationTokenEqualPredicate,XWinRT::PodLifetimeTraits,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<int>,Windows::Foundation::Collections::Internal::HashMapOptions<EventRegistrationToken,int,XWinRT::PodLifetimeTraits,0,1,0>>::Insert(
                                   *((_QWORD *)this + 28),
                                   a3->value,
                                   Pid,
                                   &Process);
        }
      }
    }
    else
    {
      CallingProcessHandle = -2147024809;
    }
    a3->value = (__int64)EncodePointer((PVOID)a3->value);
  }
  if ( hMutex && (v12 & 0xFFFFFF7F) == 0 && !ReleaseMutex(hMutex) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v10, v11);
    JUMPOUT(0x18005290ELL);
  }
  return (unsigned int)CallingProcessHandle;
}

```

## disassembly

```asm
0x1800527d0  mov     [rsp-18h+arg_8], rbx
0x1800527d5  mov     [rsp-18h+arg_10], rsi
0x1800527da  push    rbp
0x1800527db  push    rdi
0x1800527dc  push    r14
0x1800527de  mov     rbp, rsp
0x1800527e1  sub     rsp, 30h
0x1800527e5  mov     rsi, r8
0x1800527e8  mov     rdi, rdx
0x1800527eb  mov     r14, rcx
0x1800527ee  or      r8d, 0FFFFFFFFh
0x1800527f2  mov     rdx, [rcx+0A0h]
0x1800527f9  lea     rcx, [rbp+var_10]
0x1800527fd  call    ?Lock@Mutex@Wrappers@WRL@Microsoft@@SA?AV?$SyncLockWithStatusT@UMutexTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Details@234@PEAXK@Z; Microsoft::WRL::Wrappers::Mutex::Lock(void *,ulong)
0x180052802  nop
0x180052803  mov     eax, [r14+80h]
0x18005280a  test    eax, eax
0x18005280c  jz      short loc_180052818
0x18005280e  mov     ebx, 80070323h
0x180052813  jmp     loc_1800528C4
0x180052818  test    rdi, rdi
0x18005281b  jnz     short loc_180052827
0x18005281d  mov     ebx, 80070057h
0x180052822  jmp     loc_1800528B8
0x180052827  mov     r8, [rdi]
0x18005282a  lea     rcx, [r14+0C8h]
0x180052831  mov     r9, rsi
0x180052834  mov     r8, [r8+18h]
0x180052838  mov     rdx, rdi
0x18005283b  call    ?AddInternal@?$EventSource@UIOplockCallbackEventHandler@@U?$InvokeModeOptions@$01@WRL@Microsoft@@@WRL@Microsoft@@AEAAJPEAUIOplockCallbackEventHandler@@PEAXPEAUEventRegistrationToken@@@Z; Microsoft::WRL::EventSource<IOplockCallbackEventHandler,Microsoft::WRL::InvokeModeOptions<2>>::AddInternal(IOplockCallbackEventHandler *,void *,EventRegistrationToken *)
0x180052840  mov     ebx, eax
0x180052842  test    eax, eax
0x180052844  js      short loc_1800528B8
0x180052846  mov     rcx, rdi; struct IUnknown *
0x180052849  call    ?IsObjectSecurelyCallableInProcess@@YAHPEAUIUnknown@@@Z; IsObjectSecurelyCallableInProcess(IUnknown *)
0x18005284e  test    eax, eax
0x180052850  jnz     short loc_1800528B8
0x180052852  mov     [rbp+Pid], eax
0x180052855  mov     [rbp+Process], 0
0x18005285d  lea     r8, [rbp+Process]
0x180052861  mov     ecx, 1000h
0x180052866  call    ?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z; CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)
0x18005286b  mov     ebx, eax
0x18005286d  test    eax, eax
0x18005286f  js      short loc_18005287E
0x180052871  mov     rcx, [rbp+Process]; Process
0x180052875  call    cs:__imp_GetProcessId
0x18005287b  mov     [rbp+Pid], eax
0x18005287e  lea     rcx, [rbp+Process]
0x180052882  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x180052887  test    ebx, ebx
0x180052889  jns     short loc_18005289B
0x18005288b  lea     rdx, [rbp+Pid]; Pid
0x18005288f  xor     ecx, ecx; Binding
0x180052891  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180052897  test    eax, eax
0x180052899  jnz     short loc_1800528B8
0x18005289b  mov     byte ptr [rbp+Process], 0
0x18005289f  lea     r9, [rbp+Process]
0x1800528a3  mov     r8d, [rbp+Pid]
0x1800528a7  mov     rdx, [rsi]
0x1800528aa  mov     rcx, [r14+0E0h]
0x1800528b1  call    ?Insert@?$HashMap@UEventRegistrationToken@@HUPodTypeHash@XWinRT@@UEventRegistrationTokenEqualPredicate@@UPodLifetimeTraits@3@U?$DefaultLifetimeTraits@H@Internal@Collections@Foundation@Windows@@U?$HashMapOptions@UEventRegistrationToken@@HUPodLifetimeTraits@XWinRT@@$0A@$00$0A@@789Windows@@@Internal@Collections@Foundation@Windows@@UEAAJUEventRegistrationToken@@HPEAE@Z; Windows::Foundation::Collections::Internal::HashMap<EventRegistrationToken,int,XWinRT::PodTypeHash,EventRegistrationTokenEqualPredicate,XWinRT::PodLifetimeTraits,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<int>,Windows::Foundation::Collections::Internal::HashMapOptions<EventRegistrationToken,int,XWinRT::PodLifetimeTraits,0,1,0>>::Insert(EventRegistrationToken,int,uchar *)
0x1800528b6  mov     ebx, eax
0x1800528b8  mov     rcx, [rsi]; Ptr
0x1800528bb  call    cs:__imp_EncodePointer
0x1800528c1  mov     [rsi], rax
0x1800528c4  mov     rcx, [rbp+hMutex]; hMutex
0x1800528c8  test    rcx, rcx
0x1800528cb  jz      short loc_1800528E0
0x1800528cd  test    [rbp+var_10], 0FFFFFF7Fh
0x1800528d4  jnz     short loc_1800528E0
0x1800528d6  call    cs:__imp_ReleaseMutex
0x1800528dc  test    eax, eax
0x1800528de  jz      short loc_1800528F5
0x1800528e0  mov     eax, ebx
0x1800528e2  mov     rbx, [rsp+30h+arg_8]
0x1800528e7  mov     rsi, [rsp+30h+arg_10]
0x1800528ec  add     rsp, 30h
0x1800528f0  pop     r14
0x1800528f2  pop     rdi
0x1800528f3  pop     rbp
0x1800528f4  retn
0x1800528f5  call    cs:__imp_GetLastError
0x1800528fb  test    eax, eax
0x1800528fd  jle     short loc_180052907
0x1800528ff  movzx   eax, ax
0x180052902  or      eax, 80070000h
0x180052907  mov     ecx, eax; this
0x180052909  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
