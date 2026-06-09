# CDlpFile::~CDlpFile(void)

- ea: `0x18004529c`
- end: `0x180045413`
- name: `??1CDlpFile@@UEAA@XZ`
- size: `375`
- prototype: `void __fastcall(CDlpFile *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180046a00`

## callees

- `0x18001fd60`
- `0x180044dd0`
- `0x18004529c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004534c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004537b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800453aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800453d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004534c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004537b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800453aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800453d9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004535b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004538a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800453b9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800453e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004535b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004538a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800453b9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800453e8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800452bf`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800452d7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800452ef`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180045307`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004531f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180045337`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800452bf`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800452d7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800452ef`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180045307`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004531f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180045337`

## pseudocode

```c
void __fastcall CDlpFile::~CDlpFile(CDlpFile *this)
{
  char *v1; // rbx
  __int64 v3; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v5; // rbx
  HANDLE v6; // rax
  __int64 v7; // rbx
  HANDLE v8; // rax
  __int64 v9; // rbx
  HANDLE v10; // rax

  v1 = (char *)this + 560;
  if ( *((_DWORD *)this + 150) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)this + 14);
    *((_DWORD *)v1 + 10) = 0;
  }
  if ( *((_DWORD *)this + 134) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 496));
    *((_DWORD *)this + 134) = 0;
  }
  if ( *((_DWORD *)this + 118) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 432));
    *((_DWORD *)this + 118) = 0;
  }
  if ( *((_DWORD *)this + 104) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 376));
    *((_DWORD *)this + 104) = 0;
  }
  if ( *((_DWORD *)this + 90) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)this + 8);
    *((_DWORD *)this + 90) = 0;
  }
  if ( *((_DWORD *)this + 76) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 264));
    *((_DWORD *)this + 76) = 0;
  }
  v3 = *((_QWORD *)this + 30);
  if ( v3 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v3 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    *((_QWORD *)this + 30) = 0;
  }
  v5 = *((_QWORD *)this + 29);
  if ( v5 )
  {
    v6 = GetProcessHeap();
    HeapFree(v6, 0, (LPVOID)(v5 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    *((_QWORD *)this + 29) = 0;
  }
  v7 = *((_QWORD *)this + 28);
  if ( v7 )
  {
    v8 = GetProcessHeap();
    HeapFree(v8, 0, (LPVOID)(v7 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    *((_QWORD *)this + 28) = 0;
  }
  v9 = *((_QWORD *)this + 27);
  if ( v9 )
  {
    v10 = GetProcessHeap();
    HeapFree(v10, 0, (LPVOID)(v9 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    *((_QWORD *)this + 27) = 0;
  }
  CDlpErrorImpl<CUnknownRefChainImpl<IDlpFile>>::~CDlpErrorImpl<CUnknownRefChainImpl<IDlpFile>>(this);
}

```

## disassembly

```asm
0x18004529c  mov     [rsp+arg_0], rbx
0x1800452a1  mov     [rsp+arg_8], rsi
0x1800452a6  push    rdi
0x1800452a7  sub     rsp, 20h
0x1800452ab  lea     rbx, [rcx+230h]
0x1800452b2  xor     esi, esi
0x1800452b4  mov     rdi, rcx
0x1800452b7  cmp     [rbx+28h], esi
0x1800452ba  jz      short loc_1800452C8
0x1800452bc  mov     rcx, rbx; lpCriticalSection
0x1800452bf  call    cs:__imp_DeleteCriticalSection
0x1800452c5  mov     [rbx+28h], esi
0x1800452c8  lea     rbx, [rdi+1F0h]
0x1800452cf  cmp     [rbx+28h], esi
0x1800452d2  jz      short loc_1800452E0
0x1800452d4  mov     rcx, rbx; lpCriticalSection
0x1800452d7  call    cs:__imp_DeleteCriticalSection
0x1800452dd  mov     [rbx+28h], esi
0x1800452e0  lea     rbx, [rdi+1B0h]
0x1800452e7  cmp     [rbx+28h], esi
0x1800452ea  jz      short loc_1800452F8
0x1800452ec  mov     rcx, rbx; lpCriticalSection
0x1800452ef  call    cs:__imp_DeleteCriticalSection
0x1800452f5  mov     [rbx+28h], esi
0x1800452f8  lea     rbx, [rdi+178h]
0x1800452ff  cmp     [rbx+28h], esi
0x180045302  jz      short loc_180045310
0x180045304  mov     rcx, rbx; lpCriticalSection
0x180045307  call    cs:__imp_DeleteCriticalSection
0x18004530d  mov     [rbx+28h], esi
0x180045310  lea     rbx, [rdi+140h]
0x180045317  cmp     [rbx+28h], esi
0x18004531a  jz      short loc_180045328
0x18004531c  mov     rcx, rbx; lpCriticalSection
0x18004531f  call    cs:__imp_DeleteCriticalSection
0x180045325  mov     [rbx+28h], esi
0x180045328  lea     rbx, [rdi+108h]
0x18004532f  cmp     [rbx+28h], esi
0x180045332  jz      short loc_180045340
0x180045334  mov     rcx, rbx; lpCriticalSection
0x180045337  call    cs:__imp_DeleteCriticalSection
0x18004533d  mov     [rbx+28h], esi
0x180045340  mov     rbx, [rdi+0F0h]
0x180045347  test    rbx, rbx
0x18004534a  jz      short loc_18004536F
0x18004534c  call    cs:__imp_GetProcessHeap
0x180045352  lea     r8, [rbx-4]; lpMem
0x180045356  xor     edx, edx; dwFlags
0x180045358  mov     rcx, rax; hHeap
0x18004535b  call    cs:__imp_HeapFree
0x180045361  xor     ecx, ecx
0x180045363  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180045368  mov     [rdi+0F0h], rsi
0x18004536f  mov     rbx, [rdi+0E8h]
0x180045376  test    rbx, rbx
0x180045379  jz      short loc_18004539E
0x18004537b  call    cs:__imp_GetProcessHeap
0x180045381  lea     r8, [rbx-4]; lpMem
0x180045385  xor     edx, edx; dwFlags
0x180045387  mov     rcx, rax; hHeap
0x18004538a  call    cs:__imp_HeapFree
0x180045390  xor     ecx, ecx
0x180045392  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180045397  mov     [rdi+0E8h], rsi
0x18004539e  mov     rbx, [rdi+0E0h]
0x1800453a5  test    rbx, rbx
0x1800453a8  jz      short loc_1800453CD
0x1800453aa  call    cs:__imp_GetProcessHeap
0x1800453b0  lea     r8, [rbx-4]; lpMem
0x1800453b4  xor     edx, edx; dwFlags
0x1800453b6  mov     rcx, rax; hHeap
0x1800453b9  call    cs:__imp_HeapFree
0x1800453bf  xor     ecx, ecx
0x1800453c1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800453c6  mov     [rdi+0E0h], rsi
0x1800453cd  mov     rbx, [rdi+0D8h]
0x1800453d4  test    rbx, rbx
0x1800453d7  jz      short loc_1800453FC
0x1800453d9  call    cs:__imp_GetProcessHeap
0x1800453df  lea     r8, [rbx-4]; lpMem
0x1800453e3  xor     edx, edx; dwFlags
0x1800453e5  mov     rcx, rax; hHeap
0x1800453e8  call    cs:__imp_HeapFree
0x1800453ee  xor     ecx, ecx
0x1800453f0  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800453f5  mov     [rdi+0D8h], rsi
0x1800453fc  mov     rcx, rdi
0x1800453ff  mov     rbx, [rsp+28h+arg_0]
0x180045404  mov     rsi, [rsp+28h+arg_8]
0x180045409  add     rsp, 20h
0x18004540d  pop     rdi
0x18004540e  jmp     ??1?$CDlpErrorImpl@V?$CUnknownRefChainImpl@VIDlpFile@@@@@@UEAA@XZ; CDlpErrorImpl<CUnknownRefChainImpl<IDlpFile>>::~CDlpErrorImpl<CUnknownRefChainImpl<IDlpFile>>(void)
```
