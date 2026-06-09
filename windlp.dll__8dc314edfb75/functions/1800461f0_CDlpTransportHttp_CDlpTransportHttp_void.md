# CDlpTransportHttp::~CDlpTransportHttp(void)

- ea: `0x1800461f0`
- end: `0x180046299`
- name: `??1CDlpTransportHttp@@UEAA@XZ`
- size: `169`
- prototype: `void __fastcall(CDlpTransportHttp *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180046bc0`

## callees

- `0x18001fd60`
- `0x180044fc8`
- `0x1800461f0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180046209`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180046209`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180046218`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180046218`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004627a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004627a`
- `WINHTTP!WinHttpCloseHandle` at `0x18004623c`
- `WINHTTP!WinHttpCloseHandle` at `0x180046259`
- `WINHTTP!WinHttpCloseHandle` at `0x18004623c`
- `WINHTTP!WinHttpCloseHandle` at `0x180046259`

## pseudocode

```c
void __fastcall CDlpTransportHttp::~CDlpTransportHttp(CDlpTransportHttp *this)
{
  __int64 v1; // rbx
  HANDLE ProcessHeap; // rax
  void *v4; // rcx
  void *v5; // rcx

  v1 = *((_QWORD *)this + 70);
  if ( v1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v1 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    *((_QWORD *)this + 70) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 69);
  if ( v4 )
  {
    WinHttpCloseHandle(v4);
    *((_QWORD *)this + 69) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 68);
  if ( v5 )
  {
    WinHttpCloseHandle(v5);
    *((_QWORD *)this + 68) = 0;
  }
  if ( *((_DWORD *)this + 134) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 496));
    *((_DWORD *)this + 134) = 0;
  }
  CDlpTransportImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownRefChainImpl<IDlpTransport>>>>::~CDlpTransportImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownRefChainImpl<IDlpTransport>>>>((__int64)this);
}

```

## disassembly

```asm
0x1800461f0  mov     [rsp+arg_0], rbx
0x1800461f5  push    rdi
0x1800461f6  sub     rsp, 20h
0x1800461fa  mov     rbx, [rcx+230h]
0x180046201  mov     rdi, rcx
0x180046204  test    rbx, rbx
0x180046207  jz      short loc_180046230
0x180046209  call    cs:__imp_GetProcessHeap
0x18004620f  lea     r8, [rbx-4]; lpMem
0x180046213  xor     edx, edx; dwFlags
0x180046215  mov     rcx, rax; hHeap
0x180046218  call    cs:__imp_HeapFree
0x18004621e  xor     ecx, ecx
0x180046220  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180046225  mov     qword ptr [rdi+230h], 0
0x180046230  mov     rcx, [rdi+228h]; hInternet
0x180046237  test    rcx, rcx
0x18004623a  jz      short loc_18004624D
0x18004623c  call    cs:__imp_WinHttpCloseHandle
0x180046242  mov     qword ptr [rdi+228h], 0
0x18004624d  mov     rcx, [rdi+220h]; hInternet
0x180046254  test    rcx, rcx
0x180046257  jz      short loc_18004626A
0x180046259  call    cs:__imp_WinHttpCloseHandle
0x18004625f  mov     qword ptr [rdi+220h], 0
0x18004626a  lea     rbx, [rdi+1F0h]
0x180046271  cmp     dword ptr [rbx+28h], 0
0x180046275  jz      short loc_180046287
0x180046277  mov     rcx, rbx; lpCriticalSection
0x18004627a  call    cs:__imp_DeleteCriticalSection
0x180046280  mov     dword ptr [rbx+28h], 0
0x180046287  mov     rcx, rdi
0x18004628a  mov     rbx, [rsp+28h+arg_0]
0x18004628f  add     rsp, 20h
0x180046293  pop     rdi
0x180046294  jmp     ??1?$CDlpTransportImpl@V?$CDlpErrorImpl@V?$CDlpObjectInternalImpl@V?$CUnknownRefChainImpl@VIDlpTransport@@@@@@@@@@UEAA@XZ; CDlpTransportImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownRefChainImpl<IDlpTransport>>>>::~CDlpTransportImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownRefChainImpl<IDlpTransport>>>>(void)
```
