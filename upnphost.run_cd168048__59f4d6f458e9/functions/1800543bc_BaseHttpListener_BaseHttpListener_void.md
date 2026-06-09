# BaseHttpListener::~BaseHttpListener(void)

- ea: `0x1800543bc`
- end: `0x1800545f4`
- name: `??1BaseHttpListener@@UEAA@XZ`
- size: `568`
- prototype: `void __fastcall(BaseHttpListener *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180051400`
- `0x180054600`

## callees

- `0x180023c48`
- `0x180032ab0`
- `0x180034578`
- `0x18003b1cc`
- `0x18003c018`
- `0x18003c0a8`
- `0x18003cb84`
- `0x1800543bc`
- `0x18005463c`
- `0x180055250`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800544be`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800544be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005445d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005445d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800545ba`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800545cd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800545ba`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800545cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180054476`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180054476`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054562`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054581`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800545a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054562`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054581`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800545a0`

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
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
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
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids);
      }
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 184));
      UrlListened = BaseHttpListener::OnLastUrlListened(this);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 184));
      *((_DWORD *)this + 28) = 0;
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
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
    if ( !--dword_1800761F4 )
      byte_1800761F0 = 0;
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
0x1800543bc  mov     [rsp+arg_8], rbx
0x1800543c1  mov     [rsp+arg_10], rbp
0x1800543c6  push    rsi
0x1800543c7  push    rdi
0x1800543c8  push    r15
0x1800543ca  sub     rsp, 20h
0x1800543ce  lea     rax, ??_7BaseHttpListener@@6B@; const BaseHttpListener::`vftable'
0x1800543d5  mov     rdi, rcx
0x1800543d8  mov     [rcx], rax
0x1800543db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800543e2  lea     r15, WPP_GLOBAL_Control
0x1800543e9  mov     ebx, 100h
0x1800543ee  cmp     rcx, r15
0x1800543f1  jz      short loc_180054411
0x1800543f3  test    [rcx+1Ch], ebx
0x1800543f6  jz      short loc_180054411
0x1800543f8  mov     r9d, [rdi+70h]
0x1800543fc  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180054403  mov     rcx, [rcx+10h]
0x180054407  mov     edx, 0Bh
0x18005440c  call    WPP_SF_d
0x180054411  xor     ebp, ebp
0x180054413  cmp     [rdi+68h], ebp
0x180054416  jz      loc_1800544B2
0x18005441c  cmp     [rdi+70h], ebp
0x18005441f  jle     loc_1800544AF
0x180054425  mov     dword ptr [rdi+148h], 1
0x18005442f  mov     rcx, cs:WPP_GLOBAL_Control
0x180054436  cmp     rcx, r15
0x180054439  jz      short loc_180054453
0x18005443b  test    [rcx+1Ch], ebx
0x18005443e  jz      short loc_180054453
0x180054440  mov     rcx, [rcx+10h]
0x180054444  lea     edx, [rbp+0Ch]
0x180054447  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18005444e  call    WPP_SF_
0x180054453  lea     rbx, [rdi+0B8h]
0x18005445a  mov     rcx, rbx; lpCriticalSection
0x18005445d  call    cs:__imp_EnterCriticalSection
0x180054464  nop     dword ptr [rax+rax+00h]
0x180054469  mov     rcx, rdi; this
0x18005446c  call    ?OnLastUrlListened@BaseHttpListener@@QEAAJXZ; BaseHttpListener::OnLastUrlListened(void)
0x180054471  mov     rcx, rbx; lpCriticalSection
0x180054474  mov     esi, eax
0x180054476  call    cs:__imp_LeaveCriticalSection
0x18005447d  nop     dword ptr [rax+rax+00h]
0x180054482  mov     [rdi+70h], ebp
0x180054485  mov     rcx, cs:WPP_GLOBAL_Control
0x18005448c  cmp     rcx, r15
0x18005448f  jz      short loc_1800544AF
0x180054491  test    byte ptr [rcx+1Ch], 1
0x180054495  jz      short loc_1800544AF
0x180054497  mov     rcx, [rcx+10h]
0x18005449b  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x1800544a2  mov     edx, 0Dh
0x1800544a7  mov     r9d, esi
0x1800544aa  call    WPP_SF_d
0x1800544af  mov     [rdi+68h], ebp
0x1800544b2  mov     rcx, [rdi+98h]; Block
0x1800544b9  test    rcx, rcx
0x1800544bc  jz      short loc_1800544D1
0x1800544be  call    cs:__imp_free
0x1800544c5  nop     dword ptr [rax+rax+00h]
0x1800544ca  mov     [rdi+98h], rbp
0x1800544d1  mov     rbx, [rdi+0A8h]
0x1800544d8  test    rbx, rbx
0x1800544db  jz      short loc_180054516
0x1800544dd  mov     rcx, rbx; this
0x1800544e0  call    ??1CLKRHashTable@LKRhash@@QEAA@XZ; LKRhash::CLKRHashTable::~CLKRHashTable(void)
0x1800544e5  mov     edx, 48h ; 'H'; unsigned __int64
0x1800544ea  mov     rcx, rbx; void *
0x1800544ed  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800544f2  mov     [rdi+0A8h], rbp
0x1800544f9  call    ?Enter@CSimpleLock@@QEAAXXZ; CSimpleLock::Enter(void)
0x1800544fe  sub     cs:dword_1800761F4, 1
0x180054505  jnz     short loc_18005450E
0x180054507  mov     cs:byte_1800761F0, bpl
0x18005450e  mov     eax, ebp
0x180054510  xchg    eax, cs:?g_lckLkrInit@@3VCSimpleLock@@A; CSimpleLock g_lckLkrInit
0x180054516  mov     rcx, [rdi+108h]; this
0x18005451d  test    rcx, rcx
0x180054520  jz      short loc_18005452E
0x180054522  call    ??_GCSingleThrottleByTime@@QEAAPEAXI@Z; CSingleThrottleByTime::`scalar deleting destructor'(uint)
0x180054527  mov     [rdi+108h], rbp
0x18005452e  mov     rbx, [rdi+110h]
0x180054535  test    rbx, rbx
0x180054538  jz      short loc_180054556
0x18005453a  mov     rcx, rbx; this
0x18005453d  call    ??1CMultipleIPThrottleByTime@@QEAA@XZ; CMultipleIPThrottleByTime::~CMultipleIPThrottleByTime(void)
0x180054542  mov     edx, 50h ; 'P'; unsigned __int64
0x180054547  mov     rcx, rbx; void *
0x18005454a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005454f  mov     [rdi+110h], rbp
0x180054556  mov     rcx, [rdi+120h]; hObject
0x18005455d  test    rcx, rcx
0x180054560  jz      short loc_180054575
0x180054562  call    cs:__imp_CloseHandle
0x180054569  nop     dword ptr [rax+rax+00h]
0x18005456e  mov     [rdi+120h], rbp
0x180054575  mov     rcx, [rdi+130h]; hObject
0x18005457c  test    rcx, rcx
0x18005457f  jz      short loc_180054594
0x180054581  call    cs:__imp_CloseHandle
0x180054588  nop     dword ptr [rax+rax+00h]
0x18005458d  mov     [rdi+130h], rbp
0x180054594  mov     rcx, [rdi+138h]; hObject
0x18005459b  test    rcx, rcx
0x18005459e  jz      short loc_1800545B3
0x1800545a0  call    cs:__imp_CloseHandle
0x1800545a7  nop     dword ptr [rax+rax+00h]
0x1800545ac  mov     [rdi+138h], rbp
0x1800545b3  lea     rcx, [rdi+0E0h]; lpCriticalSection
0x1800545ba  call    cs:__imp_DeleteCriticalSection
0x1800545c1  nop     dword ptr [rax+rax+00h]
0x1800545c6  lea     rcx, [rdi+0B8h]; lpCriticalSection
0x1800545cd  call    cs:__imp_DeleteCriticalSection
0x1800545d4  nop     dword ptr [rax+rax+00h]
0x1800545d9  lea     rcx, [rdi+8]; this
0x1800545dd  mov     rbx, [rsp+38h+arg_8]
0x1800545e2  mov     rbp, [rsp+38h+arg_10]
0x1800545e7  add     rsp, 20h
0x1800545eb  pop     r15
0x1800545ed  pop     rdi
0x1800545ee  pop     rsi
0x1800545ef  jmp     ??1DelayLoadHttpApi@@QEAA@XZ; DelayLoadHttpApi::~DelayLoadHttpApi(void)
```
