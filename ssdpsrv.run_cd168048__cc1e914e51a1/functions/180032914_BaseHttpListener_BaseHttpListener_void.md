# BaseHttpListener::~BaseHttpListener(void)

- ea: `0x180032914`
- end: `0x180032b4c`
- name: `??1BaseHttpListener@@UEAA@XZ`
- size: `568`
- prototype: `void __fastcall(BaseHttpListener *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002ff30`
- `0x180032b60`

## callees

- `0x18001c718`
- `0x1800271fc`
- `0x18002984c`
- `0x180029df0`
- `0x180032914`
- `0x180032b9c`
- `0x180033f50`
- `0x180034540`
- `0x180036778`
- `0x180036888`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180032a16`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180032a16`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800329ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800329ce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800329b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800329b5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180032b12`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180032b25`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180032b12`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180032b25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032aba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032ad9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032af8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032aba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032ad9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032af8`

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
    if ( !--dword_18004573C )
      byte_180045740 = 0;
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
0x180032914  mov     [rsp+arg_8], rbx
0x180032919  mov     [rsp+arg_10], rbp
0x18003291e  push    rsi
0x18003291f  push    rdi
0x180032920  push    r15
0x180032922  sub     rsp, 20h
0x180032926  lea     rax, ??_7BaseHttpListener@@6B@; const BaseHttpListener::`vftable'
0x18003292d  mov     rdi, rcx
0x180032930  mov     [rcx], rax
0x180032933  mov     rcx, cs:WPP_GLOBAL_Control
0x18003293a  lea     r15, WPP_GLOBAL_Control
0x180032941  mov     ebx, 100h
0x180032946  cmp     rcx, r15
0x180032949  jz      short loc_180032969
0x18003294b  test    [rcx+1Ch], ebx
0x18003294e  jz      short loc_180032969
0x180032950  mov     r9d, [rdi+70h]
0x180032954  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18003295b  mov     rcx, [rcx+10h]
0x18003295f  mov     edx, 0Bh
0x180032964  call    WPP_SF_d
0x180032969  xor     ebp, ebp
0x18003296b  cmp     [rdi+68h], ebp
0x18003296e  jz      loc_180032A0A
0x180032974  cmp     [rdi+70h], ebp
0x180032977  jle     loc_180032A07
0x18003297d  mov     dword ptr [rdi+148h], 1
0x180032987  mov     rcx, cs:WPP_GLOBAL_Control
0x18003298e  cmp     rcx, r15
0x180032991  jz      short loc_1800329AB
0x180032993  test    [rcx+1Ch], ebx
0x180032996  jz      short loc_1800329AB
0x180032998  mov     rcx, [rcx+10h]
0x18003299c  lea     edx, [rbp+0Ch]
0x18003299f  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x1800329a6  call    WPP_SF_
0x1800329ab  lea     rbx, [rdi+0B8h]
0x1800329b2  mov     rcx, rbx; lpCriticalSection
0x1800329b5  call    cs:__imp_EnterCriticalSection
0x1800329bc  nop     dword ptr [rax+rax+00h]
0x1800329c1  mov     rcx, rdi; this
0x1800329c4  call    ?OnLastUrlListened@BaseHttpListener@@QEAAJXZ; BaseHttpListener::OnLastUrlListened(void)
0x1800329c9  mov     rcx, rbx; lpCriticalSection
0x1800329cc  mov     esi, eax
0x1800329ce  call    cs:__imp_LeaveCriticalSection
0x1800329d5  nop     dword ptr [rax+rax+00h]
0x1800329da  mov     [rdi+70h], ebp
0x1800329dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800329e4  cmp     rcx, r15
0x1800329e7  jz      short loc_180032A07
0x1800329e9  test    byte ptr [rcx+1Ch], 1
0x1800329ed  jz      short loc_180032A07
0x1800329ef  mov     rcx, [rcx+10h]
0x1800329f3  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x1800329fa  mov     edx, 0Dh
0x1800329ff  mov     r9d, esi
0x180032a02  call    WPP_SF_d
0x180032a07  mov     [rdi+68h], ebp
0x180032a0a  mov     rcx, [rdi+98h]; Block
0x180032a11  test    rcx, rcx
0x180032a14  jz      short loc_180032A29
0x180032a16  call    cs:__imp_free
0x180032a1d  nop     dword ptr [rax+rax+00h]
0x180032a22  mov     [rdi+98h], rbp
0x180032a29  mov     rbx, [rdi+0A8h]
0x180032a30  test    rbx, rbx
0x180032a33  jz      short loc_180032A6E
0x180032a35  mov     rcx, rbx; this
0x180032a38  call    ??1CLKRHashTable@LKRhash@@QEAA@XZ; LKRhash::CLKRHashTable::~CLKRHashTable(void)
0x180032a3d  mov     edx, 48h ; 'H'; unsigned __int64
0x180032a42  mov     rcx, rbx; void *
0x180032a45  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180032a4a  mov     [rdi+0A8h], rbp
0x180032a51  call    ?Enter@CSimpleLock@@QEAAXXZ; CSimpleLock::Enter(void)
0x180032a56  sub     cs:dword_18004573C, 1
0x180032a5d  jnz     short loc_180032A66
0x180032a5f  mov     cs:byte_180045740, bpl
0x180032a66  mov     eax, ebp
0x180032a68  xchg    eax, cs:?g_lckLkrInit@@3VCSimpleLock@@A; CSimpleLock g_lckLkrInit
0x180032a6e  mov     rcx, [rdi+108h]; this
0x180032a75  test    rcx, rcx
0x180032a78  jz      short loc_180032A86
0x180032a7a  call    ??_GCSingleThrottleByTime@@QEAAPEAXI@Z; CSingleThrottleByTime::`scalar deleting destructor'(uint)
0x180032a7f  mov     [rdi+108h], rbp
0x180032a86  mov     rbx, [rdi+110h]
0x180032a8d  test    rbx, rbx
0x180032a90  jz      short loc_180032AAE
0x180032a92  mov     rcx, rbx; this
0x180032a95  call    ??1CMultipleIPThrottleByTime@@QEAA@XZ; CMultipleIPThrottleByTime::~CMultipleIPThrottleByTime(void)
0x180032a9a  mov     edx, 50h ; 'P'; unsigned __int64
0x180032a9f  mov     rcx, rbx; void *
0x180032aa2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180032aa7  mov     [rdi+110h], rbp
0x180032aae  mov     rcx, [rdi+120h]; hObject
0x180032ab5  test    rcx, rcx
0x180032ab8  jz      short loc_180032ACD
0x180032aba  call    cs:__imp_CloseHandle
0x180032ac1  nop     dword ptr [rax+rax+00h]
0x180032ac6  mov     [rdi+120h], rbp
0x180032acd  mov     rcx, [rdi+130h]; hObject
0x180032ad4  test    rcx, rcx
0x180032ad7  jz      short loc_180032AEC
0x180032ad9  call    cs:__imp_CloseHandle
0x180032ae0  nop     dword ptr [rax+rax+00h]
0x180032ae5  mov     [rdi+130h], rbp
0x180032aec  mov     rcx, [rdi+138h]; hObject
0x180032af3  test    rcx, rcx
0x180032af6  jz      short loc_180032B0B
0x180032af8  call    cs:__imp_CloseHandle
0x180032aff  nop     dword ptr [rax+rax+00h]
0x180032b04  mov     [rdi+138h], rbp
0x180032b0b  lea     rcx, [rdi+0E0h]; lpCriticalSection
0x180032b12  call    cs:__imp_DeleteCriticalSection
0x180032b19  nop     dword ptr [rax+rax+00h]
0x180032b1e  lea     rcx, [rdi+0B8h]; lpCriticalSection
0x180032b25  call    cs:__imp_DeleteCriticalSection
0x180032b2c  nop     dword ptr [rax+rax+00h]
0x180032b31  lea     rcx, [rdi+8]; this
0x180032b35  mov     rbx, [rsp+38h+arg_8]
0x180032b3a  mov     rbp, [rsp+38h+arg_10]
0x180032b3f  add     rsp, 20h
0x180032b43  pop     r15
0x180032b45  pop     rdi
0x180032b46  pop     rsi
0x180032b47  jmp     ??1DelayLoadHttpApi@@QEAA@XZ; DelayLoadHttpApi::~DelayLoadHttpApi(void)
```
