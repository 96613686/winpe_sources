# CDlpActionInterfaceCollection::~CDlpActionInterfaceCollection(void)

- ea: `0x1800451ec`
- end: `0x180045295`
- name: `??1CDlpActionInterfaceCollection@@UEAA@XZ`
- size: `169`
- prototype: `void __fastcall(CDlpActionInterfaceCollection *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800469c0`

## callees

- `0x1800451ec`
- `0x180074ed4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180045218`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180045248`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180045218`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180045248`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180045226`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180045256`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180045226`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180045256`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180045278`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180045278`

## pseudocode

```c
void __fastcall CDlpActionInterfaceCollection::~CDlpActionInterfaceCollection(CDlpActionInterfaceCollection *this)
{
  char *v1; // rdi
  void *v3; // rsi
  HANDLE ProcessHeap; // rax
  void *v5; // rsi
  HANDLE v6; // rax

  v1 = (char *)this + 128;
  CArray<DP_COM<CDlpFile>,DP_COM<CDlpFile>,CAdaptorDefault,CPoliciesDefault>::SetSize((char *)this + 128, 0);
  v3 = (void *)*((_QWORD *)v1 + 1);
  if ( v3 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v3);
    *((_QWORD *)v1 + 1) = 0;
  }
  CArray<DP_COM<CDlpFile>,DP_COM<CDlpFile>,CAdaptorDefault,CPoliciesDefault>::SetSize((char *)this + 112, 0);
  v5 = (void *)*((_QWORD *)this + 15);
  if ( v5 )
  {
    v6 = GetProcessHeap();
    HeapFree(v6, 0, v5);
    *((_QWORD *)this + 15) = 0;
  }
  *(_QWORD *)this = &CUnknownImpl<IBackgroundCopyCallback>::`vftable';
  if ( *((_DWORD *)this + 16) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    *((_DWORD *)this + 16) = 0;
  }
}

```

## disassembly

```asm
0x1800451ec  mov     [rsp+arg_0], rbx
0x1800451f1  mov     [rsp+arg_8], rsi
0x1800451f6  push    rdi
0x1800451f7  sub     rsp, 20h
0x1800451fb  lea     rdi, [rcx+80h]
0x180045202  mov     rbx, rcx
0x180045205  mov     rcx, rdi
0x180045208  xor     edx, edx
0x18004520a  call    ?SetSize@?$CArray@V?$DP_COM@VCDlpFile@@@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<DP_COM<CDlpFile>,DP_COM<CDlpFile>,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x18004520f  mov     rsi, [rdi+8]
0x180045213  test    rsi, rsi
0x180045216  jz      short loc_180045234
0x180045218  call    cs:__imp_GetProcessHeap
0x18004521e  mov     r8, rsi; lpMem
0x180045221  xor     edx, edx; dwFlags
0x180045223  mov     rcx, rax; hHeap
0x180045226  call    cs:__imp_HeapFree
0x18004522c  mov     qword ptr [rdi+8], 0
0x180045234  xor     edx, edx
0x180045236  lea     rcx, [rbx+70h]
0x18004523a  call    ?SetSize@?$CArray@V?$DP_COM@VCDlpFile@@@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<DP_COM<CDlpFile>,DP_COM<CDlpFile>,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x18004523f  mov     rsi, [rbx+78h]
0x180045243  test    rsi, rsi
0x180045246  jz      short loc_180045264
0x180045248  call    cs:__imp_GetProcessHeap
0x18004524e  mov     r8, rsi; lpMem
0x180045251  xor     edx, edx; dwFlags
0x180045253  mov     rcx, rax; hHeap
0x180045256  call    cs:__imp_HeapFree
0x18004525c  mov     qword ptr [rbx+78h], 0
0x180045264  lea     rax, ??_7?$CUnknownImpl@UIBackgroundCopyCallback@@@@6B@; const CUnknownImpl<IBackgroundCopyCallback>::`vftable'
0x18004526b  mov     [rbx], rax
0x18004526e  cmp     dword ptr [rbx+40h], 0
0x180045272  jz      short loc_180045285
0x180045274  lea     rcx, [rbx+18h]; lpCriticalSection
0x180045278  call    cs:__imp_DeleteCriticalSection
0x18004527e  mov     dword ptr [rbx+40h], 0
0x180045285  mov     rbx, [rsp+28h+arg_0]
0x18004528a  mov     rsi, [rsp+28h+arg_8]
0x18004528f  add     rsp, 20h
0x180045293  pop     rdi
0x180045294  retn
```
