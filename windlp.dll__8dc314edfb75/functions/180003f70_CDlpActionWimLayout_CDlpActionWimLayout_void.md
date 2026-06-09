# CDlpActionWimLayout::~CDlpActionWimLayout(void)

- ea: `0x180003f70`
- end: `0x180004139`
- name: `??1CDlpActionWimLayout@@UEAA@XZ`
- size: `457`
- prototype: `void __fastcall(CDlpActionWimLayout *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004940`

## callees

- `0x180003350`
- `0x180003f70`
- `0x18001fd60`
- `0x18002baec`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f8a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003fb9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003fe8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004017`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004046`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004075`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800040a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004111`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f8a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003fb9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003fe8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004017`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004046`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004075`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800040a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004111`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f99`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003fc8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003ff7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004026`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004055`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004084`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800040b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000411f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f99`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003fc8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003ff7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004026`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004055`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004084`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800040b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000411f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800040d6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800040ee`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800040d6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800040ee`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CDlpActionWimLayout::~CDlpActionWimLayout(CDlpActionWimLayout *this)
{
  __int64 v1; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v4; // rbx
  HANDLE v5; // rax
  __int64 v6; // rbx
  HANDLE v7; // rax
  __int64 v8; // rbx
  HANDLE v9; // rax
  __int64 v10; // rbx
  HANDLE v11; // rax
  __int64 v12; // rbx
  HANDLE v13; // rax
  __int64 v14; // rbx
  HANDLE v15; // rax
  void *v16; // rsi
  HANDLE v17; // rax

  v1 = *((_QWORD *)this + 93);
  if ( v1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v1 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    *((_QWORD *)this + 93) = 0;
  }
  v4 = *((_QWORD *)this + 92);
  if ( v4 )
  {
    v5 = GetProcessHeap();
    HeapFree(v5, 0, (LPVOID)(v4 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    *((_QWORD *)this + 92) = 0;
  }
  v6 = *((_QWORD *)this + 91);
  if ( v6 )
  {
    v7 = GetProcessHeap();
    HeapFree(v7, 0, (LPVOID)(v6 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    *((_QWORD *)this + 91) = 0;
  }
  v8 = *((_QWORD *)this + 90);
  if ( v8 )
  {
    v9 = GetProcessHeap();
    HeapFree(v9, 0, (LPVOID)(v8 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    *((_QWORD *)this + 90) = 0;
  }
  v10 = *((_QWORD *)this + 89);
  if ( v10 )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, (LPVOID)(v10 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    *((_QWORD *)this + 89) = 0;
  }
  v12 = *((_QWORD *)this + 88);
  if ( v12 )
  {
    v13 = GetProcessHeap();
    HeapFree(v13, 0, (LPVOID)(v12 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    *((_QWORD *)this + 88) = 0;
  }
  v14 = *((_QWORD *)this + 87);
  if ( v14 )
  {
    v15 = GetProcessHeap();
    HeapFree(v15, 0, (LPVOID)(v14 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    *((_QWORD *)this + 87) = 0;
  }
  if ( *((_DWORD *)this + 172) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 648));
    *((_DWORD *)this + 172) = 0;
  }
  if ( *((_DWORD *)this + 156) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 584));
    *((_DWORD *)this + 156) = 0;
  }
  CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::SetSize((char *)this + 552, 0);
  v16 = (void *)*((_QWORD *)this + 70);
  if ( v16 )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v16);
    *((_QWORD *)this + 70) = 0;
  }
  CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::~CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>((__int64)this);
}

```

## disassembly

```asm
0x180003f70  push    rbx
0x180003f72  push    rbp
0x180003f73  push    rsi
0x180003f74  push    rdi
0x180003f75  sub     rsp, 28h
0x180003f79  mov     rbx, [rcx+2E8h]
0x180003f80  xor     ebp, ebp
0x180003f82  mov     rdi, rcx
0x180003f85  test    rbx, rbx
0x180003f88  jz      short loc_180003FAD
0x180003f8a  call    cs:__imp_GetProcessHeap
0x180003f90  lea     r8, [rbx-4]; lpMem
0x180003f94  xor     edx, edx; dwFlags
0x180003f96  mov     rcx, rax; hHeap
0x180003f99  call    cs:__imp_HeapFree
0x180003f9f  xor     ecx, ecx
0x180003fa1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180003fa6  mov     [rdi+2E8h], rbp
0x180003fad  mov     rbx, [rdi+2E0h]
0x180003fb4  test    rbx, rbx
0x180003fb7  jz      short loc_180003FDC
0x180003fb9  call    cs:__imp_GetProcessHeap
0x180003fbf  lea     r8, [rbx-4]; lpMem
0x180003fc3  xor     edx, edx; dwFlags
0x180003fc5  mov     rcx, rax; hHeap
0x180003fc8  call    cs:__imp_HeapFree
0x180003fce  xor     ecx, ecx
0x180003fd0  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180003fd5  mov     [rdi+2E0h], rbp
0x180003fdc  mov     rbx, [rdi+2D8h]
0x180003fe3  test    rbx, rbx
0x180003fe6  jz      short loc_18000400B
0x180003fe8  call    cs:__imp_GetProcessHeap
0x180003fee  lea     r8, [rbx-4]; lpMem
0x180003ff2  xor     edx, edx; dwFlags
0x180003ff4  mov     rcx, rax; hHeap
0x180003ff7  call    cs:__imp_HeapFree
0x180003ffd  xor     ecx, ecx
0x180003fff  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180004004  mov     [rdi+2D8h], rbp
0x18000400b  mov     rbx, [rdi+2D0h]
0x180004012  test    rbx, rbx
0x180004015  jz      short loc_18000403A
0x180004017  call    cs:__imp_GetProcessHeap
0x18000401d  lea     r8, [rbx-4]; lpMem
0x180004021  xor     edx, edx; dwFlags
0x180004023  mov     rcx, rax; hHeap
0x180004026  call    cs:__imp_HeapFree
0x18000402c  xor     ecx, ecx
0x18000402e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180004033  mov     [rdi+2D0h], rbp
0x18000403a  mov     rbx, [rdi+2C8h]
0x180004041  test    rbx, rbx
0x180004044  jz      short loc_180004069
0x180004046  call    cs:__imp_GetProcessHeap
0x18000404c  lea     r8, [rbx-4]; lpMem
0x180004050  xor     edx, edx; dwFlags
0x180004052  mov     rcx, rax; hHeap
0x180004055  call    cs:__imp_HeapFree
0x18000405b  xor     ecx, ecx
0x18000405d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180004062  mov     [rdi+2C8h], rbp
0x180004069  mov     rbx, [rdi+2C0h]
0x180004070  test    rbx, rbx
0x180004073  jz      short loc_180004098
0x180004075  call    cs:__imp_GetProcessHeap
0x18000407b  lea     r8, [rbx-4]; lpMem
0x18000407f  xor     edx, edx; dwFlags
0x180004081  mov     rcx, rax; hHeap
0x180004084  call    cs:__imp_HeapFree
0x18000408a  xor     ecx, ecx
0x18000408c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180004091  mov     [rdi+2C0h], rbp
0x180004098  mov     rbx, [rdi+2B8h]
0x18000409f  test    rbx, rbx
0x1800040a2  jz      short loc_1800040C7
0x1800040a4  call    cs:__imp_GetProcessHeap
0x1800040aa  lea     r8, [rbx-4]; lpMem
0x1800040ae  xor     edx, edx; dwFlags
0x1800040b0  mov     rcx, rax; hHeap
0x1800040b3  call    cs:__imp_HeapFree
0x1800040b9  xor     ecx, ecx
0x1800040bb  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800040c0  mov     [rdi+2B8h], rbp
0x1800040c7  lea     rbx, [rdi+288h]
0x1800040ce  cmp     [rbx+28h], ebp
0x1800040d1  jz      short loc_1800040DF
0x1800040d3  mov     rcx, rbx; lpCriticalSection
0x1800040d6  call    cs:__imp_DeleteCriticalSection
0x1800040dc  mov     [rbx+28h], ebp
0x1800040df  lea     rbx, [rdi+248h]
0x1800040e6  cmp     [rbx+28h], ebp
0x1800040e9  jz      short loc_1800040F7
0x1800040eb  mov     rcx, rbx; lpCriticalSection
0x1800040ee  call    cs:__imp_DeleteCriticalSection
0x1800040f4  mov     [rbx+28h], ebp
0x1800040f7  lea     rbx, [rdi+228h]
0x1800040fe  xor     edx, edx
0x180004100  mov     rcx, rbx
0x180004103  call    ?SetSize@?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x180004108  mov     rsi, [rbx+8]
0x18000410c  test    rsi, rsi
0x18000410f  jz      short loc_180004129
0x180004111  call    cs:__imp_GetProcessHeap
0x180004117  mov     r8, rsi; lpMem
0x18000411a  xor     edx, edx; dwFlags
0x18000411c  mov     rcx, rax; hHeap
0x18000411f  call    cs:__imp_HeapFree
0x180004125  mov     [rbx+8], rbp
0x180004129  mov     rcx, rdi
0x18000412c  add     rsp, 28h
0x180004130  pop     rdi
0x180004131  pop     rsi
0x180004132  pop     rbp
0x180004133  pop     rbx
0x180004134  jmp     ??1?$CDlpActionImpl@V?$CDlpErrorImpl@V?$CDlpObjectInternalImpl@V?$CUnknownImpl@VIDlpAction@@@@@@@@@@UEAA@XZ; CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::~CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>(void)
```
