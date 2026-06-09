# DBSession::DBSession(void)

- ea: `0x180022434`
- end: `0x180022520`
- name: `??0DBSession@@IEAA@XZ`
- size: `236`
- prototype: `DBSession *__fastcall(DBSession *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180021db8`

## callees

- `0x180004464`
- `0x18000b9ac`
- `0x180022528`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18002246e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800224e9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18002246e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800224e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022506`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022506`

## pseudocode

```c
DBSession *__fastcall DBSession::DBSession(DBSession *this)
{
  __int64 v2; // rdx
  __int64 v3; // r8

  *((_DWORD *)this + 2) = 0;
  *((_OWORD *)this + 1) = 0;
  *((_OWORD *)this + 2) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_BYTE *)this + 56) = 0;
  *(_QWORD *)this = &DBSession::`vftable';
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)((char *)this + 64), 0, 0);
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_DWORD *)this + 32) = 0;
  utl::unordered_map<enum US_TABLEID,ATL::CComPtr<IDBTable>,utl::hash<enum US_TABLEID>,utl::equal_to<enum US_TABLEID>,utl::allocator<utl::pair<enum US_TABLEID const,ATL::CComPtr<IDBTable>>>>::unordered_map<enum US_TABLEID,ATL::CComPtr<IDBTable>,utl::hash<enum US_TABLEID>,utl::equal_to<enum US_TABLEID>,utl::allocator<utl::pair<enum US_TABLEID const,ATL::CComPtr<IDBTable>>>>((char *)this + 136);
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 26) = -1;
  *((_QWORD *)this + 27) = -1;
  *((_QWORD *)this + 24) = 0;
  *((_DWORD *)this + 50) = 0;
  *((_DWORD *)this + 56) = -1;
  utl::list<TableHandleInfo *,utl::allocator<TableHandleInfo *>>::list<TableHandleInfo *,utl::allocator<TableHandleInfo *>>((char *)this + 232);
  utl::list<TableHandleInfo *,utl::allocator<TableHandleInfo *>>::list<TableHandleInfo *,utl::allocator<TableHandleInfo *>>((char *)this + 256);
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)this + 7, 0, 0);
  utl::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>>>::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>>>(
    (char *)this + 320,
    v2,
    v3);
  *((_BYTE *)this + 344) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_DWORD *)this + 57) = GetCurrentThreadId();
  return this;
}

```

## disassembly

```asm
0x180022434  mov     [rsp+arg_0], rbx
0x180022439  push    rdi
0x18002243a  sub     rsp, 20h
0x18002243e  xorps   xmm0, xmm0
0x180022441  xor     eax, eax
0x180022443  xor     edi, edi
0x180022445  mov     rbx, rcx
0x180022448  mov     [rcx+8], edi
0x18002244b  xor     r8d, r8d; Flags
0x18002244e  movups  xmmword ptr [rcx+10h], xmm0
0x180022452  xor     edx, edx; dwSpinCount
0x180022454  movups  xmmword ptr [rcx+20h], xmm0
0x180022458  mov     [rcx+30h], rax
0x18002245c  lea     rax, ??_7DBSession@@6B@; const DBSession::`vftable'
0x180022463  mov     [rcx+38h], dil
0x180022467  mov     [rcx], rax
0x18002246a  add     rcx, 40h ; '@'; lpCriticalSection
0x18002246e  call    cs:__imp_InitializeCriticalSectionEx
0x180022474  mov     [rbx+68h], rdi
0x180022478  lea     rcx, [rbx+88h]
0x18002247f  mov     [rbx+70h], rdi
0x180022483  mov     [rbx+80h], edi
0x180022489  call    ??0?$unordered_map@W4US_TABLEID@@V?$CComPtr@VIDBTable@@@ATL@@U?$hash@W4US_TABLEID@@@utl@@U?$equal_to@W4US_TABLEID@@@5@V?$allocator@U?$pair@$$CBW4US_TABLEID@@V?$CComPtr@VIDBTable@@@ATL@@@utl@@@5@@utl@@QEAA@XZ; utl::unordered_map<US_TABLEID,ATL::CComPtr<IDBTable>,utl::hash<US_TABLEID>,utl::equal_to<US_TABLEID>,utl::allocator<utl::pair<US_TABLEID const,ATL::CComPtr<IDBTable>>>>::unordered_map<US_TABLEID,ATL::CComPtr<IDBTable>,utl::hash<US_TABLEID>,utl::equal_to<US_TABLEID>,utl::allocator<utl::pair<US_TABLEID const,ATL::CComPtr<IDBTable>>>>(void)
0x18002248e  mov     [rbx+0B0h], rdi
0x180022495  lea     rcx, [rbx+0E8h]
0x18002249c  mov     [rbx+0B8h], rdi
0x1800224a3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800224a7  mov     [rbx+0D0h], rax
0x1800224ae  mov     [rbx+0D8h], rax
0x1800224b5  mov     [rbx+0C0h], rdi
0x1800224bc  mov     [rbx+0C8h], edi
0x1800224c2  mov     dword ptr [rbx+0E0h], 0FFFFFFFFh
0x1800224cc  call    ??0?$list@PEAUTableHandleInfo@@V?$allocator@PEAUTableHandleInfo@@@utl@@@utl@@QEAA@XZ; utl::list<TableHandleInfo *,utl::allocator<TableHandleInfo *>>::list<TableHandleInfo *,utl::allocator<TableHandleInfo *>>(void)
0x1800224d1  lea     rcx, [rbx+100h]
0x1800224d8  call    ??0?$list@PEAUTableHandleInfo@@V?$allocator@PEAUTableHandleInfo@@@utl@@@utl@@QEAA@XZ; utl::list<TableHandleInfo *,utl::allocator<TableHandleInfo *>>::list<TableHandleInfo *,utl::allocator<TableHandleInfo *>>(void)
0x1800224dd  lea     rcx, [rbx+118h]; lpCriticalSection
0x1800224e4  xor     r8d, r8d; Flags
0x1800224e7  xor     edx, edx; dwSpinCount
0x1800224e9  call    cs:__imp_InitializeCriticalSectionEx
0x1800224ef  lea     rcx, [rbx+140h]
0x1800224f6  call    ??0?$vector@V?$auto_xxx@PEAU_USPROPVAL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAU_USPROPVAL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>>>::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>>>(void)
0x1800224fb  mov     [rbx+158h], dil
0x180022502  mov     [rbx+78h], rdi
0x180022506  call    cs:__imp_GetCurrentThreadId
0x18002250c  mov     [rbx+0E4h], eax
0x180022512  mov     rax, rbx
0x180022515  mov     rbx, [rsp+28h+arg_0]
0x18002251a  add     rsp, 20h
0x18002251e  pop     rdi
0x18002251f  retn
```
