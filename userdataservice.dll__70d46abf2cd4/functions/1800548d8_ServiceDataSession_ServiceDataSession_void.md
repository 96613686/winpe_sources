# ServiceDataSession::~ServiceDataSession(void)

- ea: `0x1800548d8`
- end: `0x180054a9e`
- name: `??1ServiceDataSession@@UEAA@XZ`
- size: `454`
- prototype: `void __fastcall(ServiceDataSession *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, service_task`

## callers

- `0x1800546a8`
- `0x1800548a0`

## callees

- `0x1800548d8`
- `0x180083c78`
- `0x1800977ac`
- `0x18009dfc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800548f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180054a69`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800548f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180054a69`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005498d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800549eb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180054a11`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005498d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800549eb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180054a11`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180054925`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180054925`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180054916`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180054a82`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180054916`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180054a82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054a08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054a08`

## pseudocode

```c
void __fastcall ServiceDataSession::~ServiceDataSession(ServiceDataSession *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  struct UdmNotifyStructure *v3; // rdx
  __int64 i; // rsi
  void *v5; // rcx
  char *v6; // rcx
  __int64 **v7; // rsi
  __int64 *v8; // rcx
  void *v9; // rcx
  char *v10; // rcx
  char *v11; // rcx
  char *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  __int64 *v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rcx

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  *(_QWORD *)this = &ServiceDataSession::`vftable';
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 433); i = (unsigned int)(i + 1) )
    Udm::FreeUdmNotify(*((HLOCAL *)this + i + 16), v3);
  *((_DWORD *)this + 433) = 0;
  LeaveCriticalSection(v2);
  v5 = (void *)*((_QWORD *)this + 9);
  if ( v5 )
    SetEvent(v5);
  if ( *((_DWORD *)this + 508) )
  {
    EnterCriticalSection(&g_testProcessMapLock);
    utl::_HashTable<unsigned long,unsigned long,utl::hash<unsigned long>,utl::equal_to<unsigned long>,utl::allocator<unsigned long>,0>::_EraseImpl<unsigned long>(
      v17,
      (char *)this + 1884);
    LeaveCriticalSection(&g_testProcessMapLock);
  }
  v6 = (char *)*((_QWORD *)this + 250);
  if ( v6 != (char *)this + 2016 )
    operator delete(v6);
  v7 = (__int64 **)((char *)this + 1960);
  while ( 1 )
  {
    v8 = *v7;
    if ( *v7 == (__int64 *)v7 )
      break;
    v15 = (__int64 *)v8[1];
    v16 = *v8;
    *v15 = *v8;
    *(_QWORD *)(v16 + 8) = v15;
    operator delete(v8);
  }
  v9 = (void *)*((_QWORD *)this + 247);
  *((_QWORD *)this + 248) = 0;
  if ( v9 )
    operator delete(v9);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 48);
  v10 = (char *)*((_QWORD *)this + 236);
  if ( v10 != (char *)this + 1904 )
    operator delete(v10);
  v11 = (char *)*((_QWORD *)this + 230);
  if ( v11 != (char *)this + 1856 )
    operator delete(v11);
  v12 = (char *)*((_QWORD *)this + 226);
  if ( v12 != (char *)this + 1824 )
    operator delete(v12);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1744));
  v13 = (void *)*((_QWORD *)this + 13);
  if ( v13 != (void *)-1LL )
  {
    *((_QWORD *)this + 14) = v13;
    operator delete(v13);
  }
  v14 = (void *)*((_QWORD *)this + 9);
  if ( v14 )
    CloseHandle(v14);
  DeleteCriticalSection(v2);
  *(_QWORD *)this = &UnusedUnknown<IUnknown>::`vftable';
}

```

## disassembly

```asm
0x1800548d8  push    rbx
0x1800548da  push    rbp
0x1800548db  push    rsi
0x1800548dc  push    rdi
0x1800548dd  sub     rsp, 28h
0x1800548e1  lea     rax, ??_7ServiceDataSession@@6B@; const ServiceDataSession::`vftable'
0x1800548e8  mov     rdi, rcx
0x1800548eb  lea     rbx, [rcx+20h]
0x1800548ef  mov     [rcx], rax
0x1800548f2  mov     rcx, rbx; lpCriticalSection
0x1800548f5  call    cs:__imp_EnterCriticalSection
0x1800548fb  xor     esi, esi
0x1800548fd  cmp     [rdi+6C4h], esi
0x180054903  ja      loc_180054A45
0x180054909  mov     rcx, rbx; lpCriticalSection
0x18005490c  mov     dword ptr [rdi+6C4h], 0
0x180054916  call    cs:__imp_LeaveCriticalSection
0x18005491c  mov     rcx, [rdi+48h]; hEvent
0x180054920  test    rcx, rcx
0x180054923  jz      short loc_18005492B
0x180054925  call    cs:__imp_SetEvent
0x18005492b  cmp     dword ptr [rdi+7F0h], 0
0x180054932  jnz     loc_180054A62
0x180054938  mov     rcx, [rdi+7D0h]; Block
0x18005493f  lea     rax, [rdi+7E0h]
0x180054946  lea     rbp, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18005494d  cmp     rcx, rax
0x180054950  jz      short loc_18005495A
0x180054952  mov     rdx, rbp
0x180054955  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18005495a  lea     rsi, [rdi+7A8h]
0x180054961  mov     rcx, [rsi]; Block
0x180054964  cmp     rcx, rsi
0x180054967  jnz     loc_180054A2A
0x18005496d  mov     rcx, [rsi+10h]; Block
0x180054971  mov     qword ptr [rsi+18h], 0
0x180054979  test    rcx, rcx
0x18005497c  jz      short loc_180054986
0x18005497e  mov     rdx, rbp
0x180054981  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180054986  lea     rcx, [rdi+780h]; lpCriticalSection
0x18005498d  call    cs:__imp_DeleteCriticalSection
0x180054993  mov     rcx, [rdi+760h]; Block
0x18005499a  lea     rax, [rdi+770h]
0x1800549a1  cmp     rcx, rax
0x1800549a4  jz      short loc_1800549AE
0x1800549a6  mov     rdx, rbp
0x1800549a9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800549ae  mov     rcx, [rdi+730h]; Block
0x1800549b5  lea     rax, [rdi+740h]
0x1800549bc  cmp     rcx, rax
0x1800549bf  jz      short loc_1800549C9
0x1800549c1  mov     rdx, rbp
0x1800549c4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800549c9  mov     rcx, [rdi+710h]; Block
0x1800549d0  lea     rax, [rdi+720h]
0x1800549d7  cmp     rcx, rax
0x1800549da  jz      short loc_1800549E4
0x1800549dc  mov     rdx, rbp
0x1800549df  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800549e4  lea     rcx, [rdi+6D0h]; lpCriticalSection
0x1800549eb  call    cs:__imp_DeleteCriticalSection
0x1800549f1  mov     rcx, [rdi+68h]; Block
0x1800549f5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800549f9  jnz     loc_180054A8D
0x1800549ff  mov     rcx, [rdi+48h]; hObject
0x180054a03  test    rcx, rcx
0x180054a06  jz      short loc_180054A0E
0x180054a08  call    cs:__imp_CloseHandle
0x180054a0e  mov     rcx, rbx; lpCriticalSection
0x180054a11  call    cs:__imp_DeleteCriticalSection
0x180054a17  lea     rax, ??_7?$UnusedUnknown@UIUnknown@@@@6B@; const UnusedUnknown<IUnknown>::`vftable'
0x180054a1e  mov     [rdi], rax
0x180054a21  add     rsp, 28h
0x180054a25  pop     rdi
0x180054a26  pop     rsi
0x180054a27  pop     rbp
0x180054a28  pop     rbx
0x180054a29  retn
0x180054a2a  mov     rdx, [rcx+8]
0x180054a2e  mov     rax, [rcx]
0x180054a31  mov     [rdx], rax
0x180054a34  mov     [rax+8], rdx
0x180054a38  mov     rdx, rbp
0x180054a3b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180054a40  jmp     loc_180054961
0x180054a45  mov     rcx, [rdi+rsi*8+80h]; hMem
0x180054a4d  call    ?FreeUdmNotify@Udm@@YAXPEAUUdmNotifyStructure@@@Z; Udm::FreeUdmNotify(UdmNotifyStructure *)
0x180054a52  inc     esi
0x180054a54  cmp     esi, [rdi+6C4h]
0x180054a5a  jnb     loc_180054909
0x180054a60  jmp     short loc_180054A45
0x180054a62  lea     rcx, ?g_testProcessMapLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x180054a69  call    cs:__imp_EnterCriticalSection
0x180054a6f  lea     rdx, [rdi+75Ch]
0x180054a76  call    ??$_EraseImpl@K@?$_HashTable@KKU?$hash@K@utl@@U?$equal_to@K@2@V?$allocator@K@2@$0A@@utl@@AEAA_KAEBK@Z; utl::_HashTable<ulong,ulong,utl::hash<ulong>,utl::equal_to<ulong>,utl::allocator<ulong>,0>::_EraseImpl<ulong>(ulong const &)
0x180054a7b  lea     rcx, ?g_testProcessMapLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x180054a82  call    cs:__imp_LeaveCriticalSection
0x180054a88  jmp     loc_180054938
0x180054a8d  mov     rdx, rbp
0x180054a90  mov     [rdi+70h], rcx
0x180054a94  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180054a99  jmp     loc_1800549FF
```
