# Windows::UI::Core::CDispatcher::CreateDispatcherQueue(void)

- ea: `0x180037904`
- end: `0x1800379e8`
- name: `?CreateDispatcherQueue@CDispatcher@Core@UI@Windows@@AEAAXXZ`
- size: `228`
- prototype: `void __fastcall(Windows::UI::Core::CDispatcher *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180037760`

## callees

- `0x1800038e0`
- `0x180037904`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoFailFastWithErrorContext` at `0x1800379bf`
- `api-ms-win-core-winrt-error-l1-1-0!RoFailFastWithErrorContext` at `0x1800379cc`
- `api-ms-win-core-winrt-error-l1-1-0!RoFailFastWithErrorContext` at `0x1800379d6`
- `api-ms-win-core-winrt-error-l1-1-0!RoFailFastWithErrorContext` at `0x1800379e0`
- `api-ms-win-core-winrt-error-l1-1-0!RoFailFastWithErrorContext` at `0x1800379bf`
- `api-ms-win-core-winrt-error-l1-1-0!RoFailFastWithErrorContext` at `0x1800379cc`
- `api-ms-win-core-winrt-error-l1-1-0!RoFailFastWithErrorContext` at `0x1800379d6`
- `api-ms-win-core-winrt-error-l1-1-0!RoFailFastWithErrorContext` at `0x1800379e0`
- `CoreMessaging!CoreUICreate` at `0x1800379aa`
- `CoreMessaging!CoreUICreate` at `0x1800379aa`
- `CoreMessaging!GetDispatcherQueueForCurrentThread` at `0x180037934`
- `CoreMessaging!GetDispatcherQueueForCurrentThread` at `0x180037934`
- `CoreMessaging!CreateDispatcherQueueController` at `0x18003796a`
- `CoreMessaging!CreateDispatcherQueueController` at `0x18003796a`

## pseudocode

```c
void __fastcall Windows::UI::Core::CDispatcher::CreateDispatcherQueue(void **this)
{
  _QWORD *v1; // rsi
  int DispatcherQueueForCurrentThread; // eax
  HRESULT v4; // eax
  void *v5; // rdi
  __int64 (__fastcall *v6)(void *, _QWORD *); // rbx
  int v7; // eax
  int v8; // eax
  DispatcherQueueOptions options; // [rsp+20h] [rbp-38h] BYREF

  v1 = this + 98;
  options.dwSize = 12;
  options.threadType = DQTYPE_THREAD_CURRENT;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(this + 98);
  DispatcherQueueForCurrentThread = GetDispatcherQueueForCurrentThread(v1);
  if ( DispatcherQueueForCurrentThread < 0 )
    RoFailFastWithErrorContext((unsigned int)DispatcherQueueForCurrentThread);
  if ( !*v1 )
  {
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(this + 99);
    options.apartmentType = DQTAT_COM_NONE;
    v4 = CreateDispatcherQueueController(&options, this + 99);
    if ( v4 < 0 )
      RoFailFastWithErrorContext((unsigned int)v4);
    v5 = this[99];
    v6 = *(__int64 (__fastcall **)(void *, _QWORD *))(*(_QWORD *)v5 + 48LL);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(v1);
    v7 = v6(v5, v1);
    if ( v7 < 0 )
      RoFailFastWithErrorContext((unsigned int)v7);
  }
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(this + 96);
  v8 = CoreUICreate(this + 96);
  if ( v8 < 0 )
    RoFailFastWithErrorContext((unsigned int)v8);
}

```

## disassembly

```asm
0x180037904  push    rbx
0x180037906  push    rbp
0x180037907  push    rsi
0x180037908  push    rdi
0x180037909  sub     rsp, 38h
0x18003790d  lea     rsi, [rcx+310h]
0x180037914  mov     [rsp+58h+options.dwSize], 0Ch
0x18003791c  mov     rbp, rcx
0x18003791f  mov     [rsp+58h+options.threadType], 2
0x180037927  mov     rcx, rsi
0x18003792a  xor     ebx, ebx
0x18003792c  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180037931  mov     rcx, rsi
0x180037934  call    cs:__imp_GetDispatcherQueueForCurrentThread
0x18003793a  test    eax, eax
0x18003793c  js      short loc_1800379BD
0x18003793e  cmp     [rsi], rbx
0x180037941  jnz     short loc_180037998
0x180037943  lea     rdi, [rbp+318h]
0x18003794a  mov     rcx, rdi
0x18003794d  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180037952  movsd   xmm0, qword ptr [rsp+58h+options.dwSize]
0x180037958  lea     rcx, [rsp+58h+options]; options
0x18003795d  mov     rdx, rdi; dispatcherQueueController
0x180037960  movsd   qword ptr [rsp+58h+options.dwSize], xmm0
0x180037966  mov     [rsp+58h+options.apartmentType], ebx
0x18003796a  call    cs:__imp_CreateDispatcherQueueController
0x180037970  test    eax, eax
0x180037972  js      short loc_1800379CA
0x180037974  mov     rdi, [rdi]
0x180037977  mov     rcx, rsi
0x18003797a  mov     rax, [rdi]
0x18003797d  mov     rbx, [rax+30h]
0x180037981  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180037986  mov     rdx, rsi
0x180037989  mov     rcx, rdi
0x18003798c  mov     rax, rbx
0x18003798f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037994  test    eax, eax
0x180037996  js      short loc_1800379D4
0x180037998  lea     rbx, [rbp+300h]
0x18003799f  mov     rcx, rbx
0x1800379a2  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800379a7  mov     rcx, rbx
0x1800379aa  call    cs:__imp_CoreUICreate
0x1800379b0  test    eax, eax
0x1800379b2  js      short loc_1800379DE
0x1800379b4  add     rsp, 38h
0x1800379b8  pop     rdi
0x1800379b9  pop     rsi
0x1800379ba  pop     rbp
0x1800379bb  pop     rbx
0x1800379bc  retn
0x1800379bd  mov     ecx, eax
0x1800379bf  call    cs:__imp_RoFailFastWithErrorContext
0x1800379c5  jmp     loc_18003793E
0x1800379ca  mov     ecx, eax
0x1800379cc  call    cs:__imp_RoFailFastWithErrorContext
0x1800379d2  jmp     short loc_180037974
0x1800379d4  mov     ecx, eax
0x1800379d6  call    cs:__imp_RoFailFastWithErrorContext
0x1800379dc  jmp     short loc_180037998
0x1800379de  mov     ecx, eax
0x1800379e0  call    cs:__imp_RoFailFastWithErrorContext
0x1800379e6  jmp     short loc_1800379B4
```
