# CRequestClient::DisableNotify(void)

- ea: `0x1800eae08`
- end: `0x1800eaec8`
- name: `?DisableNotify@CRequestClient@@QEAAXXZ`
- size: `192`
- prototype: `void __fastcall(CRequestClient *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800768f4`
- `0x1800eadf8`

## callees

- `0x1800699a0`
- `0x180072768`
- `0x1800eae08`
- `0x1800eb364`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800eae24`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800eae24`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800eae7c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800eaeae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800eae7c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800eaeae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800eae2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800eae2f`

## string_xrefs

- `0x1800eae41`: `onecoreuap\base\appmodel\search\tquery\cicommon\crequest.cxx`
- `0x1800eae69`: `onecoreuap\base\appmodel\search\tquery\cicommon\crequest.cxx`

## pseudocode

```c
void __fastcall CRequestClient::DisableNotify(CRequestClient *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  int v3; // esi
  const wchar_t *v4; // r9
  const wchar_t *v5; // r9
  bool v6; // zf

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 184);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 184));
  v3 = 1;
  GetCurrentThreadId();
  SearchIndexerDebug::Verbose(
    (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\tquery\\cicommon\\crequest.cxx",
    (const wchar_t *)0x3B5,
    (unsigned int)L"[Proxy] disable notify\n",
    v4);
  v6 = *((_DWORD *)this + 32) == 0;
  *((_DWORD *)this + 30) = 0;
  if ( !v6 )
  {
    *((_QWORD *)this + 17) = 0;
    CEventSem::Set((CRequestClient *)((char *)this + 168));
    v3 = 0;
    LeaveCriticalSection(v1);
    CEventSem::Wait((CRequestClient *)((char *)this + 176), 0xFFFFFFFF, 0);
  }
  SearchIndexerDebug::Verbose(
    (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\tquery\\cicommon\\crequest.cxx",
    (const wchar_t *)0x3C5,
    (unsigned int)L"[Proxy] disabled notify\n",
    v5);
  if ( v3 )
    LeaveCriticalSection(v1);
}

```

## disassembly

```asm
0x1800eae08  mov     [rsp+arg_0], rbx
0x1800eae0d  mov     [rsp+arg_8], rsi
0x1800eae12  push    rdi
0x1800eae13  sub     rsp, 20h
0x1800eae17  lea     rdi, [rcx+0B8h]
0x1800eae1e  mov     rbx, rcx
0x1800eae21  mov     rcx, rdi; lpCriticalSection
0x1800eae24  call    cs:__imp_EnterCriticalSection
0x1800eae2a  mov     esi, 1
0x1800eae2f  call    cs:__imp_GetCurrentThreadId
0x1800eae35  lea     r8, aProxyDisableNo; "[Proxy] disable notify\n"
0x1800eae3c  mov     edx, 3B5h; wchar_t *
0x1800eae41  lea     rcx, aOnecoreuapBase_173; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1800eae48  call    ?Verbose@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x1800eae4d  cmp     dword ptr [rbx+80h], 0
0x1800eae54  mov     dword ptr [rbx+78h], 0
0x1800eae5b  jnz     short loc_1800EAE92
0x1800eae5d  lea     r8, aProxyDisabledN; "[Proxy] disabled notify\n"
0x1800eae64  mov     edx, 3C5h; wchar_t *
0x1800eae69  lea     rcx, aOnecoreuapBase_173; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1800eae70  call    ?Verbose@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x1800eae75  test    esi, esi
0x1800eae77  jz      short loc_1800EAE82
0x1800eae79  mov     rcx, rdi; lpCriticalSection
0x1800eae7c  call    cs:__imp_LeaveCriticalSection
0x1800eae82  mov     rbx, [rsp+28h+arg_0]
0x1800eae87  mov     rsi, [rsp+28h+arg_8]
0x1800eae8c  add     rsp, 20h
0x1800eae90  pop     rdi
0x1800eae91  retn
0x1800eae92  lea     rcx, [rbx+0A8h]; this
0x1800eae99  mov     qword ptr [rbx+88h], 0
0x1800eaea4  call    ?Set@CEventSem@@QEAAXXZ; CEventSem::Set(void)
0x1800eaea9  mov     rcx, rdi; lpCriticalSection
0x1800eaeac  xor     esi, esi
0x1800eaeae  call    cs:__imp_LeaveCriticalSection
0x1800eaeb4  lea     rcx, [rbx+0B0h]; this
0x1800eaebb  xor     r8d, r8d; int
0x1800eaebe  or      edx, 0FFFFFFFFh; unsigned int
0x1800eaec1  call    ?Wait@CEventSem@@QEAAKKH@Z; CEventSem::Wait(ulong,int)
0x1800eaec6  jmp     short loc_1800EAE5D
```
