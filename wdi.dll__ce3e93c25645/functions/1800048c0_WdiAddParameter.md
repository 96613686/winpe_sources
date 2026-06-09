# WdiAddParameter

- ea: `0x1800048c0`
- end: `0x180004d10`
- name: `WdiAddParameter`
- size: `1104`
- prototype: `__int64 __fastcall(__int64, int, _WORD *, unsigned int, void *Src)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180001340`
- `0x180002ba0`
- `0x1800048c0`
- `0x180007630`
- `0x18000f1b6`

## import_xrefs

- `ntdll!AlpcMaxAllowedMessageLength` at `0x180004bd7`
- `ntdll!AlpcMaxAllowedMessageLength` at `0x180004bd7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800048ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800048ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004a07`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004c18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004c9d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004a07`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004c18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004c9d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ca7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004cc7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ce3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ca7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004cc7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ce3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004cb5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004cd5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004cf1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004cb5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004cd5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004cf1`
- `RPCRT4!UuidCreate` at `0x180004a2e`
- `RPCRT4!UuidCreate` at `0x180004a2e`

## pseudocode

```c
__int64 __fastcall WdiAddParameter(__int64 a1, int a2, _WORD *a3, unsigned int a4, void *Src)
{
  size_t v6; // r13
  __int64 v9; // rsi
  int v10; // edi
  unsigned int *v11; // r14
  __int64 v12; // rax
  __int64 v13; // rcx
  _WORD *v14; // rax
  int Args; // edx
  unsigned __int64 v16; // rbx
  __int64 v17; // rax
  unsigned __int64 v18; // rax
  size_t v19; // r15
  void *v20; // rax
  void *v21; // rax
  unsigned __int16 *v22; // rcx
  int v23; // edx
  unsigned __int16 *i; // r8
  int v25; // eax
  int v26; // ecx
  int v27; // eax
  unsigned int v28; // ecx
  unsigned int v29; // edx
  int v30; // r8d
  void *v31; // rbx
  HANDLE v32; // rax
  void *v33; // rbx
  HANDLE v34; // rax
  HANDLE ProcessHeap; // rax
  _DWORD *v37; // [rsp+60h] [rbp+8h]

  v6 = a4;
  v9 = 0;
  EnterCriticalSection(&g_csWDI);
  if ( !a1 )
  {
    v10 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\library.cpp",
      (int)L"WdiAddParameter",
      408,
      (int)L"Error = %d",
      87);
LABEL_17:
    LeaveCriticalSection(&g_csWDI);
LABEL_59:
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)v9);
    return (unsigned int)v10;
  }
  if ( !a3 )
  {
    v10 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\library.cpp",
      (int)L"WdiAddParameter",
      409,
      (int)L"Error = %d",
      87);
    goto LABEL_17;
  }
  if ( !Src )
  {
    v10 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\library.cpp",
      (int)L"WdiAddParameter",
      410,
      (int)L"Error = %d",
      87);
    goto LABEL_17;
  }
  if ( *(_DWORD *)(a1 + 16) == 2 )
  {
    v10 = -2147020579;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\library.cpp",
      (int)L"WdiAddParameter",
      414,
      (int)L"Error = %d",
      221);
    goto LABEL_17;
  }
  v11 = *(unsigned int **)(a1 + 32);
  if ( !v11 )
  {
    v10 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\library.cpp",
      (int)L"WdiAddParameter",
      419,
      (int)L"Error = %d",
      87);
    goto LABEL_17;
  }
  v37 = *(_DWORD **)(a1 + 24);
  if ( !v37 )
  {
    v10 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\library.cpp",
      (int)L"WdiAddParameter",
      420,
      (int)L"Error = %d",
      87);
    goto LABEL_17;
  }
  if ( a2 )
  {
    v10 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\library.cpp",
      (int)L"WdiAddParameter",
      429,
      (int)L"Error = %d",
      87);
    goto LABEL_17;
  }
  v12 = WdipAlloc(64);
  v9 = v12;
  if ( !v12 )
  {
    v10 = -2147024882;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\library.cpp",
      (int)L"WdiAddParameter",
      433,
      (int)L"Error = %d",
      14);
    goto LABEL_17;
  }
  *(_OWORD *)v12 = 0;
  *(_OWORD *)(v12 + 16) = 0;
  *(_OWORD *)(v12 + 32) = 0;
  *(_OWORD *)(v12 + 48) = 0;
  *(_OWORD *)v12 = *(_OWORD *)a1;
  UuidCreate((UUID *)(v12 + 16));
  *(_DWORD *)(v9 + 36) = 0;
  *(_DWORD *)(v9 + 40) = v6;
  *(_QWORD *)(v9 + 56) = 0;
  v13 = 0x7FFFFFFF;
  *(_QWORD *)(v9 + 48) = 0;
  v14 = a3;
  do
  {
    if ( !*v14 )
      break;
    ++v14;
    --v13;
  }
  while ( v13 );
  v10 = -2147024809;
  Args = -2147024809;
  if ( v13 )
    Args = 0;
  v16 = 0x7FFFFFFF - v13;
  if ( !v13 )
  {
    v10 = Args;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\library.cpp",
      (int)L"WdiAddParameter",
      456,
      (int)L"Error = %d",
      Args);
LABEL_58:
    LeaveCriticalSection(&g_csWDI);
    v31 = *(void **)(v9 + 48);
    v32 = GetProcessHeap();
    HeapFree(v32, 0, v31);
    v33 = *(void **)(v9 + 56);
    *(_QWORD *)(v9 + 48) = 0;
    v34 = GetProcessHeap();
    HeapFree(v34, 0, v33);
    *(_QWORD *)(v9 + 56) = 0;
    goto LABEL_59;
  }
  if ( v16 > 0xFFFFFFFF )
  {
    v30 = 459;
    goto LABEL_57;
  }
  v17 = (unsigned int)(v16 + 1);
  if ( (unsigned int)v17 < (unsigned int)v16 )
  {
    v30 = 462;
    goto LABEL_57;
  }
  v18 = 2 * v17;
  if ( v18 > 0xFFFFFFFF )
  {
    v30 = 465;
    goto LABEL_57;
  }
  v19 = (unsigned int)v18;
  v20 = (void *)WdipAlloc((unsigned int)v18);
  *(_QWORD *)(v9 + 48) = v20;
  if ( !v20 )
  {
    v10 = -2147024882;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\library.cpp",
      (int)L"WdiAddParameter",
      468,
      (int)L"Error = %d",
      14);
    goto LABEL_58;
  }
  memcpy_0(v20, a3, v19);
  v21 = (void *)WdipAlloc(v6);
  *(_QWORD *)(v9 + 56) = v21;
  if ( !v21 )
  {
    v10 = -2147024882;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\library.cpp",
      (int)L"WdiAddParameter",
      472,
      (int)L"Error = %d",
      14);
    goto LABEL_58;
  }
  memcpy_0(v21, Src, v6);
  v22 = *(unsigned __int16 **)(v9 + 48);
  if ( !v22 || v9 == -44 )
  {
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\library.cpp",
      (int)L"WdiAddParameter",
      478,
      (int)L"Error = %d",
      87);
    goto LABEL_58;
  }
  v23 = 0;
  for ( i = &v22[(unsigned int)v16]; v22 < i; v23 = v25 + 37 * v23 )
    v25 = *v22++;
  v26 = -314159269 * v23;
  if ( -314159269 * v23 < 0 )
    v26 = 314159269 * v23;
  v27 = v19 + 52;
  *(_DWORD *)(v9 + 44) = v26 % 1000000007;
  if ( (int)v19 + 52 < (unsigned int)v19 )
  {
    *(_DWORD *)(v9 + 32) = -1;
    v30 = 497;
    goto LABEL_57;
  }
  v28 = v27 + v6;
  if ( v27 + (int)v6 < (unsigned int)v6 )
  {
    *(_DWORD *)(v9 + 32) = -1;
    v30 = 504;
    goto LABEL_57;
  }
  *(_DWORD *)(v9 + 32) = v28;
  if ( (unsigned int)(*v37 + 256) < *v37 )
  {
    v30 = 519;
    goto LABEL_57;
  }
  v29 = *v11 + *v37 + 256;
  if ( v29 < *v11 )
  {
    v30 = 526;
    goto LABEL_57;
  }
  if ( v28 + v29 < v28 )
  {
    v30 = 533;
LABEL_57:
    v10 = -2147024362;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\library.cpp",
      (int)L"WdiAddParameter",
      v30,
      (int)L"Error = %d",
      22);
    goto LABEL_58;
  }
  if ( v28 + v29 > (unsigned __int64)AlpcMaxAllowedMessageLength() )
  {
    v10 = -2147467259;
    goto LABEL_58;
  }
  v10 = WdipAddParameterToCollection(v11, v9);
  if ( v10 < 0 )
  {
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\library.cpp",
      (int)L"WdiAddParameter",
      544,
      (int)L"Error = %d",
      v10);
    goto LABEL_58;
  }
  LeaveCriticalSection(&g_csWDI);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800048c0  mov     [rsp+arg_8], rbx
0x1800048c5  mov     [rsp+arg_10], rbp
0x1800048ca  push    rsi
0x1800048cb  push    rdi
0x1800048cc  push    r13
0x1800048ce  push    r14
0x1800048d0  push    r15
0x1800048d2  sub     rsp, 30h
0x1800048d6  mov     rbx, rcx
0x1800048d9  mov     r13d, r9d
0x1800048dc  lea     rcx, g_csWDI; lpCriticalSection
0x1800048e3  mov     rbp, r8
0x1800048e6  mov     edi, edx
0x1800048e8  xor     esi, esi
0x1800048ea  call    cs:__imp_EnterCriticalSection
0x1800048f0  test    rbx, rbx
0x1800048f3  jnz     short loc_18000490D
0x1800048f5  mov     edi, 80070057h
0x1800048fa  mov     dword ptr [rsp+58h+Args], 57h ; 'W'
0x180004902  mov     r8d, 198h
0x180004908  jmp     loc_1800049E6
0x18000490d  test    rbp, rbp
0x180004910  jnz     short loc_18000492A
0x180004912  mov     edi, 80070057h
0x180004917  mov     dword ptr [rsp+58h+Args], 57h ; 'W'
0x18000491f  mov     r8d, 199h
0x180004925  jmp     loc_1800049E6
0x18000492a  cmp     [rsp+58h+Src], rsi
0x180004932  jnz     short loc_18000494C
0x180004934  mov     edi, 80070057h
0x180004939  mov     dword ptr [rsp+58h+Args], 57h ; 'W'
0x180004941  mov     r8d, 19Ah
0x180004947  jmp     loc_1800049E6
0x18000494c  cmp     dword ptr [rbx+10h], 2
0x180004950  jnz     short loc_180004967
0x180004952  mov     edi, 800710DDh
0x180004957  mov     dword ptr [rsp+58h+Args], 10DDh
0x18000495f  mov     r8d, 19Eh
0x180004965  jmp     short loc_1800049E6
0x180004967  mov     r14, [rbx+20h]
0x18000496b  test    r14, r14
0x18000496e  jnz     short loc_180004985
0x180004970  mov     edi, 80070057h
0x180004975  mov     dword ptr [rsp+58h+Args], 57h ; 'W'
0x18000497d  mov     r8d, 1A3h
0x180004983  jmp     short loc_1800049E6
0x180004985  mov     rax, [rbx+18h]
0x180004989  mov     [rsp+58h+arg_0], rax
0x18000498e  test    rax, rax
0x180004991  jnz     short loc_1800049A8
0x180004993  mov     edi, 80070057h
0x180004998  mov     dword ptr [rsp+58h+Args], 57h ; 'W'
0x1800049a0  mov     r8d, 1A4h
0x1800049a6  jmp     short loc_1800049E6
0x1800049a8  test    edi, edi
0x1800049aa  jz      short loc_1800049C1
0x1800049ac  mov     edi, 80070057h
0x1800049b1  mov     dword ptr [rsp+58h+Args], 57h ; 'W'
0x1800049b9  mov     r8d, 1ADh
0x1800049bf  jmp     short loc_1800049E6
0x1800049c1  mov     ecx, 40h ; '@'
0x1800049c6  call    WdipAlloc
0x1800049cb  mov     rsi, rax
0x1800049ce  test    rax, rax
0x1800049d1  jnz     short loc_180004A12
0x1800049d3  mov     edi, 8007000Eh
0x1800049d8  mov     dword ptr [rsp+58h+Args], 0Eh; Args
0x1800049e0  mov     r8d, 1B1h; int
0x1800049e6  lea     r9, aErrorD_0; "Error = %d"
0x1800049ed  lea     rdx, aWdiaddparamete_0; "WdiAddParameter"
0x1800049f4  lea     rcx, aClientcoreBase_6; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800049fb  call    WdipTraceError
0x180004a00  lea     rcx, g_csWDI; lpCriticalSection
0x180004a07  call    cs:__imp_LeaveCriticalSection
0x180004a0d  jmp     loc_180004CE3
0x180004a12  xorps   xmm0, xmm0
0x180004a15  lea     rcx, [rax+10h]; Uuid
0x180004a19  movups  xmmword ptr [rax], xmm0
0x180004a1c  movups  xmmword ptr [rax+10h], xmm0
0x180004a20  movups  xmmword ptr [rax+20h], xmm0
0x180004a24  movups  xmmword ptr [rax+30h], xmm0
0x180004a28  movups  xmm0, xmmword ptr [rbx]
0x180004a2b  movups  xmmword ptr [rax], xmm0
0x180004a2e  call    cs:__imp_UuidCreate
0x180004a34  mov     [rsi+24h], edi
0x180004a37  xor     r8d, r8d
0x180004a3a  mov     [rsi+28h], r13d
0x180004a3e  mov     ebx, 7FFFFFFFh
0x180004a43  mov     [rsi+38h], r8
0x180004a47  mov     ecx, ebx
0x180004a49  mov     [rsi+30h], r8
0x180004a4d  mov     rax, rbp
0x180004a50  cmp     [rax], r8w
0x180004a54  jz      short loc_180004A60
0x180004a56  add     rax, 2
0x180004a5a  sub     rcx, 1
0x180004a5e  jnz     short loc_180004A50
0x180004a60  test    rcx, rcx
0x180004a63  mov     edi, 80070057h
0x180004a68  mov     edx, edi
0x180004a6a  cmovnz  edx, r8d
0x180004a6e  sub     rbx, rcx
0x180004a71  test    rcx, rcx
0x180004a74  cmovz   rbx, r8
0x180004a78  jnz     short loc_180004A8E
0x180004a7a  movzx   eax, dx
0x180004a7d  mov     edi, edx
0x180004a7f  mov     dword ptr [rsp+58h+Args], eax
0x180004a83  mov     r8d, 1C8h
0x180004a89  jmp     loc_180004C7C
0x180004a8e  mov     ecx, 0FFFFFFFFh
0x180004a93  cmp     rbx, rcx
0x180004a96  ja      loc_180004C69
0x180004a9c  lea     eax, [rbx+1]
0x180004a9f  cmp     eax, ebx
0x180004aa1  jb      loc_180004C61
0x180004aa7  add     rax, rax
0x180004aaa  cmp     rax, rcx
0x180004aad  ja      loc_180004C59
0x180004ab3  mov     ecx, eax
0x180004ab5  mov     r15d, eax
0x180004ab8  call    WdipAlloc
0x180004abd  mov     [rsi+30h], rax
0x180004ac1  test    rax, rax
0x180004ac4  jnz     short loc_180004ADE
0x180004ac6  mov     edi, 8007000Eh
0x180004acb  mov     dword ptr [rsp+58h+Args], 0Eh
0x180004ad3  mov     r8d, 1D4h
0x180004ad9  jmp     loc_180004C7C
0x180004ade  mov     r8, r15; Size
0x180004ae1  mov     rdx, rbp; Src
0x180004ae4  mov     rcx, rax; void *
0x180004ae7  call    memcpy_0
0x180004aec  mov     rcx, r13
0x180004aef  call    WdipAlloc
0x180004af4  mov     [rsi+38h], rax
0x180004af8  test    rax, rax
0x180004afb  jnz     short loc_180004B15
0x180004afd  mov     edi, 8007000Eh
0x180004b02  mov     dword ptr [rsp+58h+Args], 0Eh
0x180004b0a  mov     r8d, 1D8h
0x180004b10  jmp     loc_180004C7C
0x180004b15  mov     rdx, [rsp+58h+Src]; Src
0x180004b1d  mov     r8, r13; Size
0x180004b20  mov     rcx, rax; void *
0x180004b23  call    memcpy_0
0x180004b28  mov     rcx, [rsi+30h]
0x180004b2c  test    rcx, rcx
0x180004b2f  jnz     short loc_180004B44
0x180004b31  mov     dword ptr [rsp+58h+Args], 57h ; 'W'
0x180004b39  mov     r8d, 1DEh
0x180004b3f  jmp     loc_180004C7C
0x180004b44  lea     r9, [rsi+2Ch]
0x180004b48  test    r9, r9
0x180004b4b  jz      short loc_180004B31
0x180004b4d  mov     eax, ebx
0x180004b4f  xor     edx, edx
0x180004b51  lea     r8, [rcx+rax*2]
0x180004b55  cmp     rcx, r8
0x180004b58  jnb     short loc_180004B71
0x180004b5a  nop     word ptr [rax+rax+00h]
0x180004b60  movzx   eax, word ptr [rcx]
0x180004b63  add     rcx, 2
0x180004b67  imul    edx, 25h ; '%'
0x180004b6a  add     edx, eax
0x180004b6c  cmp     rcx, r8
0x180004b6f  jb      short loc_180004B60
0x180004b71  imul    eax, edx, 12B9B0A5h
0x180004b77  mov     ecx, eax
0x180004b79  neg     ecx
0x180004b7b  cmovs   ecx, eax
0x180004b7e  mov     eax, 44B82F99h
0x180004b83  imul    ecx
0x180004b85  sar     edx, 1Ch
0x180004b88  mov     eax, edx
0x180004b8a  shr     eax, 1Fh
0x180004b8d  add     edx, eax
0x180004b8f  imul    eax, edx, 3B9ACA07h
0x180004b95  sub     ecx, eax
0x180004b97  lea     eax, [r15+34h]
0x180004b9b  mov     [r9], ecx
0x180004b9e  cmp     eax, r15d
0x180004ba1  jb      loc_180004C4A
0x180004ba7  lea     ecx, [rax+r13]
0x180004bab  cmp     ecx, r13d
0x180004bae  jb      loc_180004C3B
0x180004bb4  mov     rax, [rsp+58h+arg_0]
0x180004bb9  mov     [rsi+20h], ecx
0x180004bbc  mov     eax, [rax]
0x180004bbe  lea     edx, [rax+100h]
0x180004bc4  cmp     edx, eax
0x180004bc6  jb      short loc_180004C33
0x180004bc8  add     edx, [r14]
0x180004bcb  cmp     edx, [r14]
0x180004bce  jb      short loc_180004C2B
0x180004bd0  lea     ebx, [rcx+rdx]
0x180004bd3  cmp     ebx, ecx
0x180004bd5  jb      short loc_180004C23
0x180004bd7  call    cs:__imp_AlpcMaxAllowedMessageLength
0x180004bdd  mov     rcx, rax
0x180004be0  mov     eax, ebx
0x180004be2  cmp     rax, rcx
0x180004be5  jbe     short loc_180004BF1
0x180004be7  mov     edi, 80004005h
0x180004bec  jmp     loc_180004C96
0x180004bf1  mov     rdx, rsi
0x180004bf4  mov     rcx, r14
0x180004bf7  call    WdipAddParameterToCollection
0x180004bfc  mov     edi, eax
0x180004bfe  test    eax, eax
0x180004c00  jns     short loc_180004C11
0x180004c02  movzx   ecx, di
0x180004c05  mov     r8d, 220h
0x180004c0b  mov     dword ptr [rsp+58h+Args], ecx
0x180004c0f  jmp     short loc_180004C7C
0x180004c11  lea     rcx, g_csWDI; lpCriticalSection
0x180004c18  call    cs:__imp_LeaveCriticalSection
0x180004c1e  jmp     loc_180004CF7
0x180004c23  mov     r8d, 215h
0x180004c29  jmp     short loc_180004C6F
0x180004c2b  mov     r8d, 20Eh
0x180004c31  jmp     short loc_180004C6F
0x180004c33  mov     r8d, 207h
0x180004c39  jmp     short loc_180004C6F
0x180004c3b  mov     dword ptr [rsi+20h], 0FFFFFFFFh
0x180004c42  mov     r8d, 1F8h
0x180004c48  jmp     short loc_180004C6F
0x180004c4a  mov     dword ptr [rsi+20h], 0FFFFFFFFh
0x180004c51  mov     r8d, 1F1h
0x180004c57  jmp     short loc_180004C6F
0x180004c59  mov     r8d, 1D1h
0x180004c5f  jmp     short loc_180004C6F
0x180004c61  mov     r8d, 1CEh
0x180004c67  jmp     short loc_180004C6F
0x180004c69  mov     r8d, 1CBh; int
0x180004c6f  mov     dword ptr [rsp+58h+Args], 216h; Args
0x180004c77  mov     edi, 80070216h
0x180004c7c  lea     r9, aErrorD_0; "Error = %d"
0x180004c83  lea     rdx, aWdiaddparamete_0; "WdiAddParameter"
0x180004c8a  lea     rcx, aClientcoreBase_6; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180004c91  call    WdipTraceError
0x180004c96  lea     rcx, g_csWDI; lpCriticalSection
0x180004c9d  call    cs:__imp_LeaveCriticalSection
0x180004ca3  mov     rbx, [rsi+30h]
0x180004ca7  call    cs:__imp_GetProcessHeap
0x180004cad  mov     r8, rbx; lpMem
0x180004cb0  xor     edx, edx; dwFlags
0x180004cb2  mov     rcx, rax; hHeap
0x180004cb5  call    cs:__imp_HeapFree
0x180004cbb  mov     rbx, [rsi+38h]
0x180004cbf  mov     qword ptr [rsi+30h], 0
0x180004cc7  call    cs:__imp_GetProcessHeap
0x180004ccd  mov     r8, rbx; lpMem
0x180004cd0  xor     edx, edx; dwFlags
0x180004cd2  mov     rcx, rax; hHeap
0x180004cd5  call    cs:__imp_HeapFree
0x180004cdb  mov     qword ptr [rsi+38h], 0
0x180004ce3  call    cs:__imp_GetProcessHeap
0x180004ce9  mov     r8, rsi; lpMem
0x180004cec  xor     edx, edx; dwFlags
0x180004cee  mov     rcx, rax; hHeap
0x180004cf1  call    cs:__imp_HeapFree
0x180004cf7  mov     rbx, [rsp+58h+arg_8]
0x180004cfc  mov     eax, edi
0x180004cfe  mov     rbp, [rsp+58h+arg_10]
0x180004d03  add     rsp, 30h
0x180004d07  pop     r15
0x180004d09  pop     r14
0x180004d0b  pop     r13
0x180004d0d  pop     rdi
0x180004d0e  pop     rsi
0x180004d0f  retn
```
