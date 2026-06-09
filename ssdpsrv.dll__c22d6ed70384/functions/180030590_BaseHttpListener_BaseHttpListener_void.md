# BaseHttpListener::~BaseHttpListener(void)

- ea: `0x180030590`
- end: `0x180030794`
- name: `??1BaseHttpListener@@UEAA@XZ`
- size: `516`
- prototype: `void __fastcall(BaseHttpListener *this, unsigned int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002de30`
- `0x1800307a0`

## callees

- `0x18001b404`
- `0x1800255a8`
- `0x180027a8c`
- `0x180028000`
- `0x180030590`
- `0x1800307dc`
- `0x1800316bc`
- `0x180031c38`
- `0x180033cbc`
- `0x180033dc8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180030682`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180030682`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030640`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030640`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003062d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003062d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180030766`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180030773`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180030766`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180030773`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030720`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030739`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030752`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030720`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030739`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030752`

## pseudocode

```c
void __fastcall BaseHttpListener::~BaseHttpListener(BaseHttpListener *this, unsigned int a2)
{
  unsigned int UrlListened; // esi
  void *v4; // rcx
  void *v5; // rbx
  CSimpleLock *v6; // rcx
  CSingleThrottleByTime *v7; // rcx
  void *v8; // rbx
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx

  *(_QWORD *)this = &BaseHttpListener::`vftable';
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids,
      *((unsigned int *)this + 28));
  if ( *((_DWORD *)this + 26) )
  {
    if ( *((int *)this + 28) > 0 )
    {
      *((_DWORD *)this + 82) = 1;
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 184));
      UrlListened = BaseHttpListener::OnLastUrlListened(this);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 184));
      *((_DWORD *)this + 28) = 0;
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids, UrlListened);
    }
    *((_DWORD *)this + 26) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 19);
  if ( v4 )
  {
    free(v4);
    *((_QWORD *)this + 19) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 21);
  if ( v5 )
  {
    LKRhash::CLKRHashTable::~CLKRHashTable(*((LKRhash::CLKRHashTable **)this + 21));
    operator delete(v5, 0x48u);
    *((_QWORD *)this + 21) = 0;
    CSimpleLock::Enter(v6);
    if ( !--dword_180042654 )
      byte_180042658 = 0;
    _InterlockedExchange(&g_lckLkrInit, 0);
  }
  v7 = (CSingleThrottleByTime *)*((_QWORD *)this + 33);
  if ( v7 )
  {
    CSingleThrottleByTime::`scalar deleting destructor'(v7, a2);
    *((_QWORD *)this + 33) = 0;
  }
  v8 = (void *)*((_QWORD *)this + 34);
  if ( v8 )
  {
    CMultipleIPThrottleByTime::~CMultipleIPThrottleByTime(*((CMultipleIPThrottleByTime **)this + 34));
    operator delete(v8, 0x50u);
    *((_QWORD *)this + 34) = 0;
  }
  v9 = (void *)*((_QWORD *)this + 36);
  if ( v9 )
  {
    CloseHandle(v9);
    *((_QWORD *)this + 36) = 0;
  }
  v10 = (void *)*((_QWORD *)this + 38);
  if ( v10 )
  {
    CloseHandle(v10);
    *((_QWORD *)this + 38) = 0;
  }
  v11 = (void *)*((_QWORD *)this + 39);
  if ( v11 )
  {
    CloseHandle(v11);
    *((_QWORD *)this + 39) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 224));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 184));
  DelayLoadHttpApi::~DelayLoadHttpApi((BaseHttpListener *)((char *)this + 8));
}

```

## disassembly

```asm
0x180030590  mov     [rsp+arg_8], rbx
0x180030595  mov     [rsp+arg_10], rbp
0x18003059a  push    rsi
0x18003059b  push    rdi
0x18003059c  push    r15
0x18003059e  sub     rsp, 20h
0x1800305a2  lea     rax, ??_7BaseHttpListener@@6B@; const BaseHttpListener::`vftable'
0x1800305a9  mov     rdi, rcx
0x1800305ac  mov     [rcx], rax
0x1800305af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800305b6  lea     r15, WPP_GLOBAL_Control
0x1800305bd  mov     ebx, 100h
0x1800305c2  cmp     rcx, r15
0x1800305c5  jz      short loc_1800305E5
0x1800305c7  test    [rcx+1Ch], ebx
0x1800305ca  jz      short loc_1800305E5
0x1800305cc  mov     r9d, [rdi+70h]
0x1800305d0  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x1800305d7  mov     rcx, [rcx+10h]
0x1800305db  mov     edx, 0Bh
0x1800305e0  call    WPP_SF_d
0x1800305e5  xor     ebp, ebp
0x1800305e7  cmp     [rdi+68h], ebp
0x1800305ea  jz      loc_180030676
0x1800305f0  cmp     [rdi+70h], ebp
0x1800305f3  jle     short loc_180030673
0x1800305f5  mov     dword ptr [rdi+148h], 1
0x1800305ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180030606  cmp     rcx, r15
0x180030609  jz      short loc_180030623
0x18003060b  test    [rcx+1Ch], ebx
0x18003060e  jz      short loc_180030623
0x180030610  mov     rcx, [rcx+10h]
0x180030614  lea     edx, [rbp+0Ch]
0x180030617  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18003061e  call    WPP_SF_
0x180030623  lea     rbx, [rdi+0B8h]
0x18003062a  mov     rcx, rbx; lpCriticalSection
0x18003062d  call    cs:__imp_EnterCriticalSection
0x180030633  mov     rcx, rdi; this
0x180030636  call    ?OnLastUrlListened@BaseHttpListener@@QEAAJXZ; BaseHttpListener::OnLastUrlListened(void)
0x18003063b  mov     rcx, rbx; lpCriticalSection
0x18003063e  mov     esi, eax
0x180030640  call    cs:__imp_LeaveCriticalSection
0x180030646  mov     [rdi+70h], ebp
0x180030649  mov     rcx, cs:WPP_GLOBAL_Control
0x180030650  cmp     rcx, r15
0x180030653  jz      short loc_180030673
0x180030655  test    byte ptr [rcx+1Ch], 1
0x180030659  jz      short loc_180030673
0x18003065b  mov     rcx, [rcx+10h]
0x18003065f  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180030666  mov     edx, 0Dh
0x18003066b  mov     r9d, esi
0x18003066e  call    WPP_SF_d
0x180030673  mov     [rdi+68h], ebp
0x180030676  mov     rcx, [rdi+98h]; Block
0x18003067d  test    rcx, rcx
0x180030680  jz      short loc_18003068F
0x180030682  call    cs:__imp_free
0x180030688  mov     [rdi+98h], rbp
0x18003068f  mov     rbx, [rdi+0A8h]
0x180030696  test    rbx, rbx
0x180030699  jz      short loc_1800306D4
0x18003069b  mov     rcx, rbx; this
0x18003069e  call    ??1CLKRHashTable@LKRhash@@QEAA@XZ; LKRhash::CLKRHashTable::~CLKRHashTable(void)
0x1800306a3  mov     edx, 48h ; 'H'; unsigned __int64
0x1800306a8  mov     rcx, rbx; void *
0x1800306ab  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800306b0  mov     [rdi+0A8h], rbp
0x1800306b7  call    ?Enter@CSimpleLock@@QEAAXXZ; CSimpleLock::Enter(void)
0x1800306bc  sub     cs:dword_180042654, 1
0x1800306c3  jnz     short loc_1800306CC
0x1800306c5  mov     cs:byte_180042658, bpl
0x1800306cc  mov     eax, ebp
0x1800306ce  xchg    eax, cs:?g_lckLkrInit@@3VCSimpleLock@@A; CSimpleLock g_lckLkrInit
0x1800306d4  mov     rcx, [rdi+108h]; this
0x1800306db  test    rcx, rcx
0x1800306de  jz      short loc_1800306EC
0x1800306e0  call    ??_GCSingleThrottleByTime@@QEAAPEAXI@Z; CSingleThrottleByTime::`scalar deleting destructor'(uint)
0x1800306e5  mov     [rdi+108h], rbp
0x1800306ec  mov     rbx, [rdi+110h]
0x1800306f3  test    rbx, rbx
0x1800306f6  jz      short loc_180030714
0x1800306f8  mov     rcx, rbx; this
0x1800306fb  call    ??1CMultipleIPThrottleByTime@@QEAA@XZ; CMultipleIPThrottleByTime::~CMultipleIPThrottleByTime(void)
0x180030700  mov     edx, 50h ; 'P'; unsigned __int64
0x180030705  mov     rcx, rbx; void *
0x180030708  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003070d  mov     [rdi+110h], rbp
0x180030714  mov     rcx, [rdi+120h]; hObject
0x18003071b  test    rcx, rcx
0x18003071e  jz      short loc_18003072D
0x180030720  call    cs:__imp_CloseHandle
0x180030726  mov     [rdi+120h], rbp
0x18003072d  mov     rcx, [rdi+130h]; hObject
0x180030734  test    rcx, rcx
0x180030737  jz      short loc_180030746
0x180030739  call    cs:__imp_CloseHandle
0x18003073f  mov     [rdi+130h], rbp
0x180030746  mov     rcx, [rdi+138h]; hObject
0x18003074d  test    rcx, rcx
0x180030750  jz      short loc_18003075F
0x180030752  call    cs:__imp_CloseHandle
0x180030758  mov     [rdi+138h], rbp
0x18003075f  lea     rcx, [rdi+0E0h]; lpCriticalSection
0x180030766  call    cs:__imp_DeleteCriticalSection
0x18003076c  lea     rcx, [rdi+0B8h]; lpCriticalSection
0x180030773  call    cs:__imp_DeleteCriticalSection
0x180030779  lea     rcx, [rdi+8]; this
0x18003077d  mov     rbx, [rsp+38h+arg_8]
0x180030782  mov     rbp, [rsp+38h+arg_10]
0x180030787  add     rsp, 20h
0x18003078b  pop     r15
0x18003078d  pop     rdi
0x18003078e  pop     rsi
0x18003078f  jmp     ??1DelayLoadHttpApi@@QEAA@XZ; DelayLoadHttpApi::~DelayLoadHttpApi(void)
```
