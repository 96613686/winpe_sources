# CspLoader::~CspLoader(void)

- ea: `0x18006115c`
- end: `0x180061237`
- name: `??1CspLoader@@QEAA@XZ`
- size: `219`
- prototype: `void __fastcall(CspLoader *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800b7668`

## callees

- `0x180027630`
- `0x18002ea80`
- `0x18006115c`
- `0x18006124c`
- `0x18006126c`
- `0x1800612a8`
- `0x1800b7c14`
- `0x1800f7010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800611e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800611e4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800611ee`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800611ee`
- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x180061187`
- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x180061187`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CspLoader::~CspLoader(CspLoader *this)
{
  char *v2; // rdi
  LPCRITICAL_SECTION lpCriticalSection[3]; // [rsp+20h] [rbp-18h] BYREF

  v2 = (char *)this + 152;
  if ( *((_QWORD *)this + 19) && *((_QWORD *)this + 20) )
  {
    UnsubscribeServiceChangeNotifications();
    *((_QWORD *)this + 20) = 0;
  }
  CspLoader::Stop(this);
  lpCriticalSection[0] = 0;
  wil::EnterCriticalSection(lpCriticalSection, (char *)this + 232);
  if ( *((_DWORD *)this + 68) )
  {
    *((_DWORD *)this + 68) = 0;
    (*((void (**)(void))this + 2))();
  }
  if ( lpCriticalSection[0] )
    LeaveCriticalSection(lpCriticalSection[0]);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  std::_Func_class<void,_SRU_STATS_RECORD_SET *>::_Tidy((char *)this + 168);
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(v2);
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>((char *)this + 144);
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>((char *)this + 136);
  std::unique_ptr<WcmCommon::ThreadPoolWorkQueue>::~unique_ptr<WcmCommon::ThreadPoolWorkQueue>(this);
}

```

## disassembly

```asm
0x18006115c  mov     [rsp+arg_8], rbx
0x180061161  mov     [rsp+arg_10], rsi
0x180061166  push    rdi
0x180061167  sub     rsp, 30h
0x18006116b  mov     rbx, rcx
0x18006116e  lea     rdi, [rcx+98h]
0x180061175  cmp     qword ptr [rdi], 0
0x180061179  jz      short loc_180061198
0x18006117b  mov     rcx, [rcx+0A0h]
0x180061182  test    rcx, rcx
0x180061185  jz      short loc_180061198
0x180061187  call    cs:__imp_UnsubscribeServiceChangeNotifications
0x18006118d  mov     qword ptr [rbx+0A0h], 0
0x180061198  mov     rcx, rbx; this
0x18006119b  call    ?Stop@CspLoader@@QEAAKXZ; CspLoader::Stop(void)
0x1800611a0  nop
0x1800611a1  mov     [rsp+38h+lpCriticalSection], 0
0x1800611aa  lea     rsi, [rbx+0E8h]
0x1800611b1  mov     rdx, rsi
0x1800611b4  lea     rcx, [rsp+38h+lpCriticalSection]
0x1800611b9  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800611be  cmp     dword ptr [rbx+110h], 0
0x1800611c5  jz      short loc_1800611DA
0x1800611c7  mov     dword ptr [rbx+110h], 0
0x1800611d1  mov     rax, [rbx+10h]
0x1800611d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800611da  mov     rcx, [rsp+38h+lpCriticalSection]; lpCriticalSection
0x1800611df  test    rcx, rcx
0x1800611e2  jz      short loc_1800611EB
0x1800611e4  call    cs:__imp_LeaveCriticalSection
0x1800611ea  nop
0x1800611eb  mov     rcx, rsi; lpCriticalSection
0x1800611ee  call    cs:__imp_DeleteCriticalSection
0x1800611f4  lea     rcx, [rbx+0A8h]
0x1800611fb  call    ?_Tidy@?$_Func_class@XPEAU_SRU_STATS_RECORD_SET@@@std@@IEAAXXZ; std::_Func_class<void,_SRU_STATS_RECORD_SET *>::_Tidy(void)
0x180061200  mov     rcx, rdi
0x180061203  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180061208  lea     rcx, [rbx+90h]
0x18006120f  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180061214  lea     rcx, [rbx+88h]
0x18006121b  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180061220  mov     rcx, rbx
0x180061223  mov     rbx, [rsp+38h+arg_8]
0x180061228  mov     rsi, [rsp+38h+arg_10]
0x18006122d  add     rsp, 30h
0x180061231  pop     rdi
0x180061232  jmp     ??1?$unique_ptr@VThreadPoolWorkQueue@WcmCommon@@U?$default_delete@VThreadPoolWorkQueue@WcmCommon@@@std@@@std@@QEAA@XZ; std::unique_ptr<WcmCommon::ThreadPoolWorkQueue>::~unique_ptr<WcmCommon::ThreadPoolWorkQueue>(void)
```
