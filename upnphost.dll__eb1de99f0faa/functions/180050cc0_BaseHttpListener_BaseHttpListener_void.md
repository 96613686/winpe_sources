# BaseHttpListener::~BaseHttpListener(void)

- ea: `0x180050cc0`
- end: `0x180050ec4`
- name: `??1BaseHttpListener@@UEAA@XZ`
- size: `516`
- prototype: `void __fastcall(BaseHttpListener *this, unsigned int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18004df40`
- `0x180050ed0`

## callees

- `0x180022f84`
- `0x180030ef0`
- `0x180032744`
- `0x180038ce4`
- `0x180039a84`
- `0x180039acc`
- `0x18003a584`
- `0x180050cc0`
- `0x180050f0c`
- `0x180051a78`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180050db2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180050db2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050d5d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050d5d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180050e96`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180050ea3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180050e96`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180050ea3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180050d70`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180050d70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180050e50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180050e69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180050e82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180050e50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180050e69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180050e82`

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
    if ( !--dword_1800720EC )
      byte_1800720E8 = 0;
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
0x180050cc0  mov     [rsp+arg_8], rbx
0x180050cc5  mov     [rsp+arg_10], rbp
0x180050cca  push    rsi
0x180050ccb  push    rdi
0x180050ccc  push    r15
0x180050cce  sub     rsp, 20h
0x180050cd2  lea     rax, ??_7BaseHttpListener@@6B@; const BaseHttpListener::`vftable'
0x180050cd9  mov     rdi, rcx
0x180050cdc  mov     [rcx], rax
0x180050cdf  mov     rcx, cs:WPP_GLOBAL_Control
0x180050ce6  lea     r15, WPP_GLOBAL_Control
0x180050ced  mov     ebx, 100h
0x180050cf2  cmp     rcx, r15
0x180050cf5  jz      short loc_180050D15
0x180050cf7  test    [rcx+1Ch], ebx
0x180050cfa  jz      short loc_180050D15
0x180050cfc  mov     r9d, [rdi+70h]
0x180050d00  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180050d07  mov     rcx, [rcx+10h]
0x180050d0b  mov     edx, 0Bh
0x180050d10  call    WPP_SF_d
0x180050d15  xor     ebp, ebp
0x180050d17  cmp     [rdi+68h], ebp
0x180050d1a  jz      loc_180050DA6
0x180050d20  cmp     [rdi+70h], ebp
0x180050d23  jle     short loc_180050DA3
0x180050d25  mov     dword ptr [rdi+148h], 1
0x180050d2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180050d36  cmp     rcx, r15
0x180050d39  jz      short loc_180050D53
0x180050d3b  test    [rcx+1Ch], ebx
0x180050d3e  jz      short loc_180050D53
0x180050d40  mov     rcx, [rcx+10h]
0x180050d44  lea     edx, [rbp+0Ch]
0x180050d47  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180050d4e  call    WPP_SF_
0x180050d53  lea     rbx, [rdi+0B8h]
0x180050d5a  mov     rcx, rbx; lpCriticalSection
0x180050d5d  call    cs:__imp_EnterCriticalSection
0x180050d63  mov     rcx, rdi; this
0x180050d66  call    ?OnLastUrlListened@BaseHttpListener@@QEAAJXZ; BaseHttpListener::OnLastUrlListened(void)
0x180050d6b  mov     rcx, rbx; lpCriticalSection
0x180050d6e  mov     esi, eax
0x180050d70  call    cs:__imp_LeaveCriticalSection
0x180050d76  mov     [rdi+70h], ebp
0x180050d79  mov     rcx, cs:WPP_GLOBAL_Control
0x180050d80  cmp     rcx, r15
0x180050d83  jz      short loc_180050DA3
0x180050d85  test    byte ptr [rcx+1Ch], 1
0x180050d89  jz      short loc_180050DA3
0x180050d8b  mov     rcx, [rcx+10h]
0x180050d8f  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180050d96  mov     edx, 0Dh
0x180050d9b  mov     r9d, esi
0x180050d9e  call    WPP_SF_d
0x180050da3  mov     [rdi+68h], ebp
0x180050da6  mov     rcx, [rdi+98h]; Block
0x180050dad  test    rcx, rcx
0x180050db0  jz      short loc_180050DBF
0x180050db2  call    cs:__imp_free
0x180050db8  mov     [rdi+98h], rbp
0x180050dbf  mov     rbx, [rdi+0A8h]
0x180050dc6  test    rbx, rbx
0x180050dc9  jz      short loc_180050E04
0x180050dcb  mov     rcx, rbx; this
0x180050dce  call    ??1CLKRHashTable@LKRhash@@QEAA@XZ; LKRhash::CLKRHashTable::~CLKRHashTable(void)
0x180050dd3  mov     edx, 48h ; 'H'; unsigned __int64
0x180050dd8  mov     rcx, rbx; void *
0x180050ddb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180050de0  mov     [rdi+0A8h], rbp
0x180050de7  call    ?Enter@CSimpleLock@@QEAAXXZ; CSimpleLock::Enter(void)
0x180050dec  sub     cs:dword_1800720EC, 1
0x180050df3  jnz     short loc_180050DFC
0x180050df5  mov     cs:byte_1800720E8, bpl
0x180050dfc  mov     eax, ebp
0x180050dfe  xchg    eax, cs:?g_lckLkrInit@@3VCSimpleLock@@A; CSimpleLock g_lckLkrInit
0x180050e04  mov     rcx, [rdi+108h]; this
0x180050e0b  test    rcx, rcx
0x180050e0e  jz      short loc_180050E1C
0x180050e10  call    ??_GCSingleThrottleByTime@@QEAAPEAXI@Z; CSingleThrottleByTime::`scalar deleting destructor'(uint)
0x180050e15  mov     [rdi+108h], rbp
0x180050e1c  mov     rbx, [rdi+110h]
0x180050e23  test    rbx, rbx
0x180050e26  jz      short loc_180050E44
0x180050e28  mov     rcx, rbx; this
0x180050e2b  call    ??1CMultipleIPThrottleByTime@@QEAA@XZ; CMultipleIPThrottleByTime::~CMultipleIPThrottleByTime(void)
0x180050e30  mov     edx, 50h ; 'P'; unsigned __int64
0x180050e35  mov     rcx, rbx; void *
0x180050e38  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180050e3d  mov     [rdi+110h], rbp
0x180050e44  mov     rcx, [rdi+120h]; hObject
0x180050e4b  test    rcx, rcx
0x180050e4e  jz      short loc_180050E5D
0x180050e50  call    cs:__imp_CloseHandle
0x180050e56  mov     [rdi+120h], rbp
0x180050e5d  mov     rcx, [rdi+130h]; hObject
0x180050e64  test    rcx, rcx
0x180050e67  jz      short loc_180050E76
0x180050e69  call    cs:__imp_CloseHandle
0x180050e6f  mov     [rdi+130h], rbp
0x180050e76  mov     rcx, [rdi+138h]; hObject
0x180050e7d  test    rcx, rcx
0x180050e80  jz      short loc_180050E8F
0x180050e82  call    cs:__imp_CloseHandle
0x180050e88  mov     [rdi+138h], rbp
0x180050e8f  lea     rcx, [rdi+0E0h]; lpCriticalSection
0x180050e96  call    cs:__imp_DeleteCriticalSection
0x180050e9c  lea     rcx, [rdi+0B8h]; lpCriticalSection
0x180050ea3  call    cs:__imp_DeleteCriticalSection
0x180050ea9  lea     rcx, [rdi+8]; this
0x180050ead  mov     rbx, [rsp+38h+arg_8]
0x180050eb2  mov     rbp, [rsp+38h+arg_10]
0x180050eb7  add     rsp, 20h
0x180050ebb  pop     r15
0x180050ebd  pop     rdi
0x180050ebe  pop     rsi
0x180050ebf  jmp     ??1DelayLoadHttpApi@@QEAA@XZ; DelayLoadHttpApi::~DelayLoadHttpApi(void)
```
