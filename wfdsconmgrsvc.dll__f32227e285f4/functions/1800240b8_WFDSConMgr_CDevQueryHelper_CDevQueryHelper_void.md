# WFDSConMgr::CDevQueryHelper::~CDevQueryHelper(void)

- ea: `0x1800240b8`
- end: `0x18002417a`
- name: `??1CDevQueryHelper@WFDSConMgr@@UEAA@XZ`
- size: `194`
- prototype: `void __fastcall(WFDSConMgr::CDevQueryHelper *this, bool)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180024280`
- `0x1800242c0`

## callees

- `0x18000475c`
- `0x180004f38`
- `0x180009ff4`
- `0x18001a21c`
- `0x180024090`
- `0x1800240b8`
- `0x180029008`
- `0x18005cd7c`
- `0x18005d27c`
- `0x18005dca0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180024114`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180024114`

## pseudocode

```c
void __fastcall WFDSConMgr::CDevQueryHelper::~CDevQueryHelper(WFDSConMgr::CDevQueryHelper *this, bool a2)
{
  std::_Ref_count_base *v3; // rcx

  *(_QWORD *)this = &WFDSConMgr::CDevQueryHelper::`vftable';
  if ( *((_QWORD *)this + 20) )
    WFDSConMgr::CDevQueryHelper::StopQuery(this);
  WFDSConMgr::CThreadpoolEnvironment::CleanupGroupMembers((WFDSConMgr::CDevQueryHelper *)((char *)this + 216), a2);
  WFDSConMgr::CEventWrapper::~CEventWrapper((WFDSConMgr::CDevQueryHelper *)((char *)this + 376));
  WFDSConMgr::CEventWrapper::~CEventWrapper((WFDSConMgr::CDevQueryHelper *)((char *)this + 368));
  WFDSConMgr::CThreadpoolEnvironment::~CThreadpoolEnvironment((WFDSConMgr::CDevQueryHelper *)((char *)this + 216));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 176));
  v3 = (std::_Ref_count_base *)*((_QWORD *)this + 21);
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
  std::unique_ptr<WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter>::~unique_ptr<WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter>((_QWORD *)this + 19);
  std::unique_ptr<_DEVPROPERTY,WFDSConMgr::DafDevPropertyListFreeDeleter>::~unique_ptr<_DEVPROPERTY,WFDSConMgr::DafDevPropertyListFreeDeleter>((__int64)this + 136);
  std::wstring::_Tidy_deallocate((char *)this + 88);
  std::wstring::_Tidy_deallocate((char *)this + 56);
  std::unique_ptr<_CEREMONY [0]>::~unique_ptr<_CEREMONY [0]>((void **)this + 6);
  std::unique_ptr<_CEREMONY [0]>::~unique_ptr<_CEREMONY [0]>((void **)this + 4);
  std::unique_ptr<_CEREMONY [0]>::~unique_ptr<_CEREMONY [0]>((void **)this + 2);
}

```

## disassembly

```asm
0x1800240b8  mov     [rsp+arg_0], rbx
0x1800240bd  push    rdi
0x1800240be  sub     rsp, 20h
0x1800240c2  mov     rdi, rcx
0x1800240c5  lea     rax, ??_7CDevQueryHelper@WFDSConMgr@@6B@; const WFDSConMgr::CDevQueryHelper::`vftable'
0x1800240cc  mov     [rcx], rax
0x1800240cf  cmp     qword ptr [rcx+0A0h], 0
0x1800240d7  jz      short loc_1800240DE
0x1800240d9  call    ?StopQuery@CDevQueryHelper@WFDSConMgr@@QEAAXXZ; WFDSConMgr::CDevQueryHelper::StopQuery(void)
0x1800240de  lea     rbx, [rdi+0D8h]
0x1800240e5  mov     rcx, rbx; this
0x1800240e8  call    ?CleanupGroupMembers@CThreadpoolEnvironment@WFDSConMgr@@QEAAX_N@Z; WFDSConMgr::CThreadpoolEnvironment::CleanupGroupMembers(bool)
0x1800240ed  lea     rcx, [rdi+178h]; this
0x1800240f4  call    ??1CEventWrapper@WFDSConMgr@@QEAA@XZ; WFDSConMgr::CEventWrapper::~CEventWrapper(void)
0x1800240f9  lea     rcx, [rdi+170h]; this
0x180024100  call    ??1CEventWrapper@WFDSConMgr@@QEAA@XZ; WFDSConMgr::CEventWrapper::~CEventWrapper(void)
0x180024105  mov     rcx, rbx; this
0x180024108  call    ??1CThreadpoolEnvironment@WFDSConMgr@@UEAA@XZ; WFDSConMgr::CThreadpoolEnvironment::~CThreadpoolEnvironment(void)
0x18002410d  lea     rcx, [rdi+0B0h]; lpCriticalSection
0x180024114  call    cs:__imp_DeleteCriticalSection
0x18002411a  mov     rcx, [rdi+0A8h]; this
0x180024121  test    rcx, rcx
0x180024124  jz      short loc_18002412B
0x180024126  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002412b  lea     rcx, [rdi+98h]
0x180024132  call    ??1?$unique_ptr@VCMaUsbNotificationWaiter@CMaUsbHelper@WFDSConMgr@@U?$default_delete@VCMaUsbNotificationWaiter@CMaUsbHelper@WFDSConMgr@@@std@@@std@@QEAA@XZ; std::unique_ptr<WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter>::~unique_ptr<WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter>(void)
0x180024137  lea     rcx, [rdi+88h]
0x18002413e  call    ??1?$unique_ptr@U_DEVPROPERTY@@UDafDevPropertyListFreeDeleter@WFDSConMgr@@@std@@QEAA@XZ; std::unique_ptr<_DEVPROPERTY,WFDSConMgr::DafDevPropertyListFreeDeleter>::~unique_ptr<_DEVPROPERTY,WFDSConMgr::DafDevPropertyListFreeDeleter>(void)
0x180024143  lea     rcx, [rdi+58h]
0x180024147  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002414c  lea     rcx, [rdi+38h]
0x180024150  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180024155  lea     rcx, [rdi+30h]
0x180024159  call    ??1?$unique_ptr@$$BY0A@U_CEREMONY@@U?$default_delete@$$BY0A@U_CEREMONY@@@std@@@std@@QEAA@XZ; std::unique_ptr<_CEREMONY [0]>::~unique_ptr<_CEREMONY [0]>(void)
0x18002415e  lea     rcx, [rdi+20h]
0x180024162  call    ??1?$unique_ptr@$$BY0A@U_CEREMONY@@U?$default_delete@$$BY0A@U_CEREMONY@@@std@@@std@@QEAA@XZ; std::unique_ptr<_CEREMONY [0]>::~unique_ptr<_CEREMONY [0]>(void)
0x180024167  lea     rcx, [rdi+10h]
0x18002416b  mov     rbx, [rsp+28h+arg_0]
0x180024170  add     rsp, 20h
0x180024174  pop     rdi
0x180024175  jmp     ??1?$unique_ptr@$$BY0A@U_CEREMONY@@U?$default_delete@$$BY0A@U_CEREMONY@@@std@@@std@@QEAA@XZ; std::unique_ptr<_CEREMONY [0]>::~unique_ptr<_CEREMONY [0]>(void)
```
