# CDlpRegistrar::~CDlpRegistrar(void)

- ea: `0x18004585c`
- end: `0x180045997`
- name: `??1CDlpRegistrar@@EEAA@XZ`
- size: `315`
- prototype: `void __fastcall(CDlpRegistrar *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180046a80`

## callees

- `0x18004585c`
- `0x180074ed4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800458b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800458e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180045917`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800458b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800458e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180045917`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800458c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800458ef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180045925`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800458c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800458ef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180045925`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180045943`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180045960`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180045981`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180045943`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180045960`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180045981`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CDlpRegistrar::~CDlpRegistrar(CDlpRegistrar *this)
{
  char *v2; // rdi
  void *v3; // rbp
  HANDLE ProcessHeap; // rax
  void *v5; // rsi
  HANDLE v6; // rax
  void *v7; // rsi
  HANDLE v8; // rax

  *(_QWORD *)this = &CDlpRegistrar::`vftable'{for `CUnknownImpl<IDlpRegistrar>'};
  v2 = (char *)this + 256;
  *((_QWORD *)this + 9) = &CDlpFile::`vftable';
  CArray<DP_COM<CDlpFile>,DP_COM<CDlpFile>,CAdaptorDefault,CPoliciesDefault>::SetSize((char *)this + 256, 0);
  CArray<DP_COM<CDlpFile>,DP_COM<CDlpFile>,CAdaptorDefault,CPoliciesDefault>::SetSize((char *)this + 272, 0);
  CArray<DP_COM<CDlpFile>,DP_COM<CDlpFile>,CAdaptorDefault,CPoliciesDefault>::SetSize((char *)this + 272, 0);
  v3 = (void *)*((_QWORD *)this + 35);
  if ( v3 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v3);
    *((_QWORD *)this + 35) = 0;
  }
  CArray<DP_COM<CDlpFile>,DP_COM<CDlpFile>,CAdaptorDefault,CPoliciesDefault>::SetSize(v2, 0);
  v5 = (void *)*((_QWORD *)v2 + 1);
  if ( v5 )
  {
    v6 = GetProcessHeap();
    HeapFree(v6, 0, v5);
    *((_QWORD *)v2 + 1) = 0;
  }
  CArray<DP_COM<CDlpFile>,DP_COM<CDlpFile>,CAdaptorDefault,CPoliciesDefault>::SetSize((char *)this + 240, 0);
  v7 = (void *)*((_QWORD *)this + 31);
  if ( v7 )
  {
    v8 = GetProcessHeap();
    HeapFree(v8, 0, v7);
    *((_QWORD *)this + 31) = 0;
  }
  if ( *((_DWORD *)this + 58) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
    *((_DWORD *)this + 58) = 0;
  }
  if ( *((_DWORD *)this + 44) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
    *((_DWORD *)this + 44) = 0;
  }
  *(_QWORD *)this = &CUnknownImpl<IDlpRegistrar>::`vftable';
  if ( *((_DWORD *)this + 16) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    *((_DWORD *)this + 16) = 0;
  }
}

```

## disassembly

```asm
0x18004585c  push    rbx
0x18004585e  push    rbp
0x18004585f  push    rsi
0x180045860  push    rdi
0x180045861  sub     rsp, 28h
0x180045865  lea     rax, ??_7CDlpRegistrar@@6B?$CUnknownImpl@VIDlpRegistrar@@@@@; const CDlpRegistrar::`vftable'{for `CUnknownImpl<IDlpRegistrar>'}
0x18004586c  mov     rbx, rcx
0x18004586f  mov     [rcx], rax
0x180045872  lea     rdi, [rcx+100h]
0x180045879  lea     rax, ??_7CDlpFile@@6B@; const CDlpFile::`vftable'
0x180045880  xor     edx, edx
0x180045882  mov     [rcx+48h], rax
0x180045886  mov     rcx, rdi
0x180045889  call    ?SetSize@?$CArray@V?$DP_COM@VCDlpFile@@@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<DP_COM<CDlpFile>,DP_COM<CDlpFile>,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x18004588e  lea     rsi, [rbx+110h]
0x180045895  xor     edx, edx
0x180045897  mov     rcx, rsi
0x18004589a  call    ?SetSize@?$CArray@V?$DP_COM@VCDlpFile@@@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<DP_COM<CDlpFile>,DP_COM<CDlpFile>,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x18004589f  xor     edx, edx
0x1800458a1  mov     rcx, rsi
0x1800458a4  call    ?SetSize@?$CArray@V?$DP_COM@VCDlpFile@@@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<DP_COM<CDlpFile>,DP_COM<CDlpFile>,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x1800458a9  mov     rbp, [rsi+8]
0x1800458ad  test    rbp, rbp
0x1800458b0  jz      short loc_1800458CE
0x1800458b2  call    cs:__imp_GetProcessHeap
0x1800458b8  mov     r8, rbp; lpMem
0x1800458bb  xor     edx, edx; dwFlags
0x1800458bd  mov     rcx, rax; hHeap
0x1800458c0  call    cs:__imp_HeapFree
0x1800458c6  mov     qword ptr [rsi+8], 0
0x1800458ce  xor     edx, edx
0x1800458d0  mov     rcx, rdi
0x1800458d3  call    ?SetSize@?$CArray@V?$DP_COM@VCDlpFile@@@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<DP_COM<CDlpFile>,DP_COM<CDlpFile>,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x1800458d8  mov     rsi, [rdi+8]
0x1800458dc  test    rsi, rsi
0x1800458df  jz      short loc_1800458FD
0x1800458e1  call    cs:__imp_GetProcessHeap
0x1800458e7  mov     r8, rsi; lpMem
0x1800458ea  xor     edx, edx; dwFlags
0x1800458ec  mov     rcx, rax; hHeap
0x1800458ef  call    cs:__imp_HeapFree
0x1800458f5  mov     qword ptr [rdi+8], 0
0x1800458fd  lea     rdi, [rbx+0F0h]
0x180045904  xor     edx, edx
0x180045906  mov     rcx, rdi
0x180045909  call    ?SetSize@?$CArray@V?$DP_COM@VCDlpFile@@@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<DP_COM<CDlpFile>,DP_COM<CDlpFile>,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x18004590e  mov     rsi, [rdi+8]
0x180045912  test    rsi, rsi
0x180045915  jz      short loc_180045933
0x180045917  call    cs:__imp_GetProcessHeap
0x18004591d  mov     r8, rsi; lpMem
0x180045920  xor     edx, edx; dwFlags
0x180045922  mov     rcx, rax; hHeap
0x180045925  call    cs:__imp_HeapFree
0x18004592b  mov     qword ptr [rdi+8], 0
0x180045933  lea     rdi, [rbx+0C0h]
0x18004593a  cmp     dword ptr [rdi+28h], 0
0x18004593e  jz      short loc_180045950
0x180045940  mov     rcx, rdi; lpCriticalSection
0x180045943  call    cs:__imp_DeleteCriticalSection
0x180045949  mov     dword ptr [rdi+28h], 0
0x180045950  lea     rdi, [rbx+88h]
0x180045957  cmp     dword ptr [rdi+28h], 0
0x18004595b  jz      short loc_18004596D
0x18004595d  mov     rcx, rdi; lpCriticalSection
0x180045960  call    cs:__imp_DeleteCriticalSection
0x180045966  mov     dword ptr [rdi+28h], 0
0x18004596d  lea     rax, ??_7?$CUnknownImpl@VIDlpRegistrar@@@@6B@; const CUnknownImpl<IDlpRegistrar>::`vftable'
0x180045974  mov     [rbx], rax
0x180045977  cmp     dword ptr [rbx+40h], 0
0x18004597b  jz      short loc_18004598E
0x18004597d  lea     rcx, [rbx+18h]; lpCriticalSection
0x180045981  call    cs:__imp_DeleteCriticalSection
0x180045987  mov     dword ptr [rbx+40h], 0
0x18004598e  add     rsp, 28h
0x180045992  pop     rdi
0x180045993  pop     rsi
0x180045994  pop     rbp
0x180045995  pop     rbx
0x180045996  retn
```
