# WFDSConMgr::CNotificationManager::~CNotificationManager(void)

- ea: `0x18004fbd8`
- end: `0x18004fc99`
- name: `??1CNotificationManager@WFDSConMgr@@UEAA@XZ`
- size: `193`
- prototype: `void __fastcall(WFDSConMgr::CNotificationManager *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18004fd40`

## callees

- `0x180009b5c`
- `0x18000ab00`
- `0x18004fad4`
- `0x18004fb80`
- `0x18004fbbc`
- `0x18004fbd8`
- `0x180051530`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004fc77`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004fc77`

## pseudocode

```c
void __fastcall WFDSConMgr::CNotificationManager::~CNotificationManager(WFDSConMgr::CNotificationManager *this)
{
  char *v2; // rdi
  __int64 *v3; // rax
  __int64 v4; // rbp
  const void *v5; // rdx
  __int64 v6; // [rsp+60h] [rbp+8h] BYREF

  *(_QWORD *)this = &WFDSConMgr::CNotificationManager::`vftable'{for `WFDSConMgr::INotificationManager'};
  v2 = (char *)this + 344;
  *((_QWORD *)this + 1) = &WFDSConMgr::CNotificationManager::`vftable'{for `WFDSConMgr::CWorkQueue<WFDSConMgr::CNotificationEvent>'};
  while ( *((_QWORD *)v2 + 4) )
  {
    v3 = (__int64 *)std::queue<std::unique_ptr<WFDSConMgr::CNotificationEvent>>::front(v2);
    v4 = *v3;
    v6 = *v3;
    *v3 = 0;
    std::deque<std::unique_ptr<WFDSConMgr::CNotificationEvent>>::pop_front();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_8857a33a659b3802fbdefc905f46dd3a_Traceguids, this, v4);
    }
    std::unique_ptr<WFDSConMgr::CNotificationEvent>::~unique_ptr<WFDSConMgr::CNotificationEvent>(&v6);
  }
  std::deque<std::unique_ptr<WFDSConMgr::CNotificationEvent>>::~deque<std::unique_ptr<WFDSConMgr::CNotificationEvent>>((_QWORD **)v2);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 304));
  WFDSConMgr::CWorkQueue<WFDSConMgr::CNotificationEvent>::~CWorkQueue<WFDSConMgr::CNotificationEvent>(
    (struct _RTL_CRITICAL_SECTION *)((char *)this + 8),
    v5);
  *(_QWORD *)this = &WFDSConMgr::INotificationManager::`vftable';
}

```

## disassembly

```asm
0x18004fbd8  push    rbx
0x18004fbda  push    rbp
0x18004fbdb  push    rsi
0x18004fbdc  push    rdi
0x18004fbdd  sub     rsp, 38h
0x18004fbe1  lea     rax, ??_7CNotificationManager@WFDSConMgr@@6BINotificationManager@1@@; const WFDSConMgr::CNotificationManager::`vftable'{for `WFDSConMgr::INotificationManager'}
0x18004fbe8  mov     rbx, rcx
0x18004fbeb  mov     [rcx], rax
0x18004fbee  lea     rdi, [rcx+158h]
0x18004fbf5  lea     rax, ??_7CNotificationManager@WFDSConMgr@@6B?$CWorkQueue@VCNotificationEvent@WFDSConMgr@@@1@@; const WFDSConMgr::CNotificationManager::`vftable'{for `WFDSConMgr::CWorkQueue<WFDSConMgr::CNotificationEvent>'}
0x18004fbfc  mov     [rcx+8], rax
0x18004fc00  cmp     qword ptr [rdi+20h], 0
0x18004fc05  mov     rcx, rdi
0x18004fc08  jz      short loc_18004FC6B
0x18004fc0a  call    ?front@?$queue@V?$unique_ptr@VCNotificationEvent@WFDSConMgr@@U?$default_delete@VCNotificationEvent@WFDSConMgr@@@std@@@std@@V?$deque@V?$unique_ptr@VCNotificationEvent@WFDSConMgr@@U?$default_delete@VCNotificationEvent@WFDSConMgr@@@std@@@std@@V?$allocator@V?$unique_ptr@VCNotificationEvent@WFDSConMgr@@U?$default_delete@VCNotificationEvent@WFDSConMgr@@@std@@@std@@@2@@2@@std@@QEAAAEAV?$unique_ptr@VCNotificationEvent@WFDSConMgr@@U?$default_delete@VCNotificationEvent@WFDSConMgr@@@std@@@2@XZ; std::queue<std::unique_ptr<WFDSConMgr::CNotificationEvent>>::front(void)
0x18004fc0f  mov     rbp, [rax]
0x18004fc12  mov     [rsp+58h+arg_0], rbp
0x18004fc17  mov     qword ptr [rax], 0
0x18004fc1e  call    ?pop_front@?$deque@V?$unique_ptr@VCNotificationEvent@WFDSConMgr@@U?$default_delete@VCNotificationEvent@WFDSConMgr@@@std@@@std@@V?$allocator@V?$unique_ptr@VCNotificationEvent@WFDSConMgr@@U?$default_delete@VCNotificationEvent@WFDSConMgr@@@std@@@std@@@2@@std@@QEAAXXZ; std::deque<std::unique_ptr<WFDSConMgr::CNotificationEvent>>::pop_front(void)
0x18004fc23  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fc2a  lea     rax, WPP_GLOBAL_Control
0x18004fc31  cmp     rcx, rax
0x18004fc34  jz      short loc_18004FC5F
0x18004fc36  cmp     byte ptr [rcx+19h], 2
0x18004fc3a  jb      short loc_18004FC5F
0x18004fc3c  test    byte ptr [rcx+1Ch], 1
0x18004fc40  jz      short loc_18004FC5F
0x18004fc42  mov     rcx, [rcx+10h]
0x18004fc46  lea     r8, WPP_8857a33a659b3802fbdefc905f46dd3a_Traceguids
0x18004fc4d  mov     edx, 0Bh
0x18004fc52  mov     [rsp+58h+var_38], rbp
0x18004fc57  mov     r9, rbx
0x18004fc5a  call    WPP_SF_qq
0x18004fc5f  lea     rcx, [rsp+58h+arg_0]
0x18004fc64  call    ??1?$unique_ptr@VCNotificationEvent@WFDSConMgr@@U?$default_delete@VCNotificationEvent@WFDSConMgr@@@std@@@std@@QEAA@XZ; std::unique_ptr<WFDSConMgr::CNotificationEvent>::~unique_ptr<WFDSConMgr::CNotificationEvent>(void)
0x18004fc69  jmp     short loc_18004FC00
0x18004fc6b  call    ??1?$deque@V?$unique_ptr@VCNotificationEvent@WFDSConMgr@@U?$default_delete@VCNotificationEvent@WFDSConMgr@@@std@@@std@@V?$allocator@V?$unique_ptr@VCNotificationEvent@WFDSConMgr@@U?$default_delete@VCNotificationEvent@WFDSConMgr@@@std@@@std@@@2@@std@@QEAA@XZ; std::deque<std::unique_ptr<WFDSConMgr::CNotificationEvent>>::~deque<std::unique_ptr<WFDSConMgr::CNotificationEvent>>(void)
0x18004fc70  lea     rcx, [rbx+130h]; lpCriticalSection
0x18004fc77  call    cs:__imp_DeleteCriticalSection
0x18004fc7d  lea     rcx, [rbx+8]; this
0x18004fc81  call    ??1?$CWorkQueue@VCNotificationEvent@WFDSConMgr@@@WFDSConMgr@@UEAA@XZ; WFDSConMgr::CWorkQueue<WFDSConMgr::CNotificationEvent>::~CWorkQueue<WFDSConMgr::CNotificationEvent>(void)
0x18004fc86  lea     rax, ??_7INotificationManager@WFDSConMgr@@6B@; const WFDSConMgr::INotificationManager::`vftable'
0x18004fc8d  mov     [rbx], rax
0x18004fc90  add     rsp, 38h
0x18004fc94  pop     rdi
0x18004fc95  pop     rsi
0x18004fc96  pop     rbp
0x18004fc97  pop     rbx
0x18004fc98  retn
```
