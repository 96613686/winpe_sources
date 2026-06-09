# NlmManager::NlmManager(void)

- ea: `0x180071ec8`
- end: `0x180072092`
- name: `??0NlmManager@@QEAA@XZ`
- size: `458`
- prototype: `NlmManager *__fastcall(NlmManager *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180071e50`

## callees

- `0x18002706c`
- `0x180043b40`
- `0x18004e058`
- `0x18005ee18`
- `0x18006124c`
- `0x180071ec8`
- `0x18007b57c`
- `0x180084f50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180071f74`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180071f74`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18007202e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18007202e`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180071fd5`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180071fd5`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180071fb0`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180071fb0`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x180072001`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x180072001`

## string_xrefs

- `0x18007205c`: `onecoreuap\net\wcm\service\base\nlmmanager\lib\nlmmanager.cpp`
- `0x18007206e`: `onecoreuap\net\wcm\service\base\nlmmanager\lib\nlmmanager.cpp`
- `0x180072080`: `onecoreuap\net\wcm\service\base\nlmmanager\lib\nlmmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
NlmManager *__fastcall NlmManager::NlmManager(NlmManager *this, __int64 a2)
{
  __int64 v3; // rdx
  __int64 v4; // rdx
  SC_HANDLE v5; // rax
  const char *v6; // r9
  SC_HANDLE v7; // rax
  const char *v8; // r9
  unsigned int v9; // eax
  char v10; // cl
  SC_HANDLE v12; // [rsp+30h] [rbp-40h] BYREF
  _QWORD v13[4]; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v14[8]; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v13[3] = this;
  *(_DWORD *)this = 0;
  *((_BYTE *)this + 4) = 0;
  WcmCommon::ThreadPoolWorkQueue::ThreadPoolWorkQueue((char *)this + 8, a2, 1, 1);
  WcmCommon::ThreadPoolWorkQueue::ThreadPoolWorkQueue((char *)this + 288, v3, 1, 1);
  WcmCommon::ThreadPoolWorkQueue::ThreadPoolWorkQueue((char *)this + 568, v4, 1, 1);
  *((_QWORD *)this + 106) = 0;
  *((_QWORD *)this + 107) = 0;
  *((_QWORD *)this + 108) = 0;
  *((_QWORD *)this + 109) = 0;
  *((_QWORD *)this + 110) = 0;
  *((_BYTE *)this + 888) = 0;
  std::map<_GUID,NlmManager::InterfaceInfo>::map<_GUID,NlmManager::InterfaceInfo>((char *)this + 896);
  *((_DWORD *)this + 228) = 0;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)this + 23, 0xFAu, 0);
  *((_QWORD *)this + 120) = 0;
  *((_DWORD *)this + 242) = 0;
  NlmManager::InitializeCOM(this, v14);
  v13[1] = this;
  v13[2] = 1;
  v5 = OpenSCManagerW(0, 0, 5u);
  v12 = v5;
  if ( !v5 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x61,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\nlmmanager\\lib\\nlmmanager.cpp",
      v6);
  v7 = OpenServiceW(v5, L"netprofm", 4u);
  v13[0] = v7;
  if ( !v7 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x64,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\nlmmanager\\lib\\nlmmanager.cpp",
      v8);
  v9 = SubscribeServiceChangeNotifications(v7, 2, NlmManager::NlmServiceStateChangeCallback, this);
  if ( v9 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x67,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\nlmmanager\\lib\\nlmmanager.cpp",
      (const char *)v9,
      (_DWORD)this + 960);
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v13);
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v12);
  v10 = v14[0];
  v14[0] = 0;
  if ( v10 )
    CoUninitialize();
  return this;
}

```

## disassembly

```asm
0x180071ec8  mov     [rsp-18h+arg_8], rbx
0x180071ecd  mov     [rsp-18h+arg_10], rsi
0x180071ed2  push    rbp
0x180071ed3  push    rdi
0x180071ed4  push    r14
0x180071ed6  mov     rbp, rsp
0x180071ed9  sub     rsp, 70h
0x180071edd  mov     rax, cs:__security_cookie
0x180071ee4  xor     rax, rsp
0x180071ee7  mov     [rbp+var_10], rax
0x180071eeb  mov     rdi, rcx
0x180071eee  mov     [rbp+var_20], rcx
0x180071ef2  xor     r14d, r14d
0x180071ef5  mov     [rcx], r14d
0x180071ef8  mov     [rcx+4], r14b
0x180071efc  add     rcx, 8
0x180071f00  lea     esi, [r14+1]
0x180071f04  mov     r9d, esi
0x180071f07  mov     r8d, esi
0x180071f0a  call    ??0ThreadPoolWorkQueue@WcmCommon@@QEAA@KKW4QueueingScheme@1@@Z; WcmCommon::ThreadPoolWorkQueue::ThreadPoolWorkQueue(ulong,ulong,WcmCommon::QueueingScheme)
0x180071f0f  nop
0x180071f10  lea     rcx, [rdi+120h]
0x180071f17  mov     r9d, esi
0x180071f1a  mov     r8d, esi
0x180071f1d  call    ??0ThreadPoolWorkQueue@WcmCommon@@QEAA@KKW4QueueingScheme@1@@Z; WcmCommon::ThreadPoolWorkQueue::ThreadPoolWorkQueue(ulong,ulong,WcmCommon::QueueingScheme)
0x180071f22  nop
0x180071f23  lea     rcx, [rdi+238h]
0x180071f2a  mov     r9d, esi
0x180071f2d  mov     r8d, esi
0x180071f30  call    ??0ThreadPoolWorkQueue@WcmCommon@@QEAA@KKW4QueueingScheme@1@@Z; WcmCommon::ThreadPoolWorkQueue::ThreadPoolWorkQueue(ulong,ulong,WcmCommon::QueueingScheme)
0x180071f35  nop
0x180071f36  lea     rbx, [rdi+350h]
0x180071f3d  mov     [rbp+var_40], rbx
0x180071f41  mov     [rbx], r14
0x180071f44  mov     [rbx+8], r14
0x180071f48  mov     [rbx+10h], r14
0x180071f4c  mov     [rbx+18h], r14
0x180071f50  mov     [rbx+20h], r14
0x180071f54  mov     [rbx+28h], r14b
0x180071f58  lea     rcx, [rbx+30h]
0x180071f5c  call    ??0?$map@U_GUID@@UInterfaceInfo@NlmManager@@U?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@UInterfaceInfo@NlmManager@@@std@@@5@@std@@QEAA@XZ; std::map<_GUID,NlmManager::InterfaceInfo>::map<_GUID,NlmManager::InterfaceInfo>(void)
0x180071f61  mov     [rbx+40h], r14d
0x180071f65  lea     rcx, [rdi+398h]; lpCriticalSection
0x180071f6c  xor     r8d, r8d; Flags
0x180071f6f  mov     edx, 0FAh; dwSpinCount
0x180071f74  call    cs:__imp_InitializeCriticalSectionEx
0x180071f7a  nop
0x180071f7b  lea     rbx, [rdi+3C0h]
0x180071f82  mov     [rbx], r14
0x180071f85  mov     [rdi+3C8h], r14d
0x180071f8c  lea     rdx, [rbp+var_18]
0x180071f90  mov     rcx, rdi
0x180071f93  call    ?InitializeCOM@NlmManager@@AEAA?AV?$unique_call@P6AXXZ$1?CoUninitialize@@YAXXZ$00@wil@@XZ; NlmManager::InitializeCOM(void)
0x180071f98  nop
0x180071f99  xorps   xmm0, xmm0
0x180071f9c  movups  [rbp+var_30], xmm0
0x180071fa0  mov     qword ptr [rbp+var_30], rdi
0x180071fa4  mov     byte ptr [rbp+var_30+8], sil
0x180071fa8  xor     edx, edx; lpDatabaseName
0x180071faa  xor     ecx, ecx; lpMachineName
0x180071fac  lea     r8d, [r14+5]; dwDesiredAccess
0x180071fb0  call    cs:__imp_OpenSCManagerW
0x180071fb6  mov     [rbp+var_40], rax
0x180071fba  mov     rcx, [rbp+18h]; this
0x180071fbe  test    rax, rax
0x180071fc1  jz      loc_18007206E
0x180071fc7  lea     r8d, [r14+4]; dwDesiredAccess
0x180071fcb  lea     rdx, aNetprofm; "netprofm"
0x180071fd2  mov     rcx, rax; hSCManager
0x180071fd5  call    cs:__imp_OpenServiceW
0x180071fdb  mov     [rbp+var_38], rax
0x180071fdf  mov     rcx, [rbp+18h]; this
0x180071fe3  test    rax, rax
0x180071fe6  jz      loc_180072080
0x180071fec  mov     qword ptr [rsp+70h+var_50], rbx; unsigned int
0x180071ff1  mov     r9, rdi
0x180071ff4  lea     r8, ?NlmServiceStateChangeCallback@NlmManager@@CAXKPEAX@Z; NlmManager::NlmServiceStateChangeCallback(ulong,void *)
0x180071ffb  lea     edx, [rsi+1]
0x180071ffe  mov     rcx, rax
0x180072001  call    cs:__imp_SubscribeServiceChangeNotifications
0x180072007  mov     rcx, [rbp+18h]; this
0x18007200b  test    eax, eax
0x18007200d  jnz     short loc_180072059
0x18007200f  lea     rcx, [rbp+var_38]
0x180072013  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180072018  nop
0x180072019  lea     rcx, [rbp+var_40]
0x18007201d  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180072022  nop
0x180072023  mov     cl, [rbp+var_18]
0x180072026  mov     [rbp+var_18], r14b
0x18007202a  test    cl, cl
0x18007202c  jz      short loc_180072035
0x18007202e  call    cs:__imp_CoUninitialize
0x180072034  nop
0x180072035  mov     rax, rdi
0x180072038  mov     rcx, [rbp+var_10]
0x18007203c  xor     rcx, rsp; StackCookie
0x18007203f  call    __security_check_cookie
0x180072044  lea     r11, [rsp+70h+var_s0]
0x180072049  mov     rbx, [r11+28h]
0x18007204d  mov     rsi, [r11+30h]
0x180072051  mov     rsp, r11
0x180072054  pop     r14
0x180072056  pop     rdi
0x180072057  pop     rbp
0x180072058  retn
0x180072059  mov     r9d, eax; char *
0x18007205c  lea     r8, aOnecoreuapNetW_33; "onecoreuap\\net\\wcm\\service\\base\\nl"...
0x180072063  mov     edx, 67h ; 'g'; void *
0x180072068  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18007206e  lea     r8, aOnecoreuapNetW_33; "onecoreuap\\net\\wcm\\service\\base\\nl"...
0x180072075  mov     edx, 61h ; 'a'; void *
0x18007207a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180072080  lea     r8, aOnecoreuapNetW_33; "onecoreuap\\net\\wcm\\service\\base\\nl"...
0x180072087  mov     edx, 64h ; 'd'; void *
0x18007208c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
