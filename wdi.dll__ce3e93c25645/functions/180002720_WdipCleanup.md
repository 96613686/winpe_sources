# WdipCleanup

- ea: `0x180002720`
- end: `0x18000287c`
- name: `WdipCleanup`
- size: `348`
- prototype: `void()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001980`

## callees

- `0x180002720`
- `0x1800079a0`

## import_xrefs

- `ntdll!TpReleaseAlpcCompletion` at `0x1800027b5`
- `ntdll!TpReleaseAlpcCompletion` at `0x180002869`
- `ntdll!TpReleaseAlpcCompletion` at `0x1800027b5`
- `ntdll!TpReleaseAlpcCompletion` at `0x180002869`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002780`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002780`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000275f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002794`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800027cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002838`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000275f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002794`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800027cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002838`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000276d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800027a2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800027dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002846`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000276d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800027a2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800027dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002846`

## pseudocode

```c
void WdipCleanup()
{
  LPVOID i; // rbx
  void *v1; // rdi
  HANDLE ProcessHeap; // rax
  HMODULE v3; // rcx
  void *v4; // rdi
  HANDLE v5; // rax
  HANDLE v6; // rax
  _QWORD *j; // rbx
  HANDLE v8; // rax

  for ( i = g_pWdiSessionHead; g_pWdiSessionHead; i = g_pWdiSessionHead )
  {
    v1 = (void *)*((_QWORD *)i + 8);
    g_pWdiSessionHead = (LPVOID)*((_QWORD *)i + 13);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
    v3 = (HMODULE)*((_QWORD *)i + 6);
    *((_QWORD *)i + 8) = 0;
    if ( v3 )
    {
      FreeLibrary(v3);
      *((_QWORD *)i + 6) = 0;
    }
    if ( (*((_BYTE *)i + 80) & 1) != 0 )
    {
      v4 = (void *)*((_QWORD *)i + 9);
      v5 = GetProcessHeap();
      HeapFree(v5, 0, v4);
      *((_QWORD *)i + 9) = 0;
    }
    if ( *((_QWORD *)i + 11) )
    {
      TpReleaseAlpcCompletion();
      *((_QWORD *)i + 11) = 0;
    }
    *((_QWORD *)i + 5) = 0;
    *((_QWORD *)i + 4) = 0;
    *((_QWORD *)i + 3) = 0;
    *((_QWORD *)i + 6) = 0;
    v6 = GetProcessHeap();
    HeapFree(v6, 0, i);
  }
  for ( j = g_pWdiInstanceHead; g_pWdiInstanceHead; j = g_pWdiInstanceHead )
  {
    g_pWdiInstanceHead = (LPVOID)j[8];
    if ( j[4] )
      ((void (*)(void))WdipDeleteParameterCollection)();
    if ( j[3] )
      WdipDeleteParameterCollection(j + 3);
    v8 = GetProcessHeap();
    HeapFree(v8, 0, j);
  }
  if ( g_pHostAlpcCompletion )
  {
    TpReleaseAlpcCompletion();
    g_pHostAlpcCompletion = 0;
  }
}

```

## disassembly

```asm
0x180002720  push    rsi
0x180002722  sub     rsp, 20h
0x180002726  mov     [rsp+28h+arg_0], rbx
0x18000272b  xor     esi, esi
0x18000272d  mov     rbx, cs:g_pWdiSessionHead
0x180002734  test    rbx, rbx
0x180002737  jz      loc_1800027F8
0x18000273d  mov     [rsp+28h+arg_8], rdi
0x180002742  nop     dword ptr [rax+00h]
0x180002746  nop     word ptr [rax+rax+00000000h]
0x180002750  mov     rax, [rbx+68h]
0x180002754  mov     rdi, [rbx+40h]
0x180002758  mov     cs:g_pWdiSessionHead, rax
0x18000275f  call    cs:__imp_GetProcessHeap
0x180002765  mov     r8, rdi; lpMem
0x180002768  xor     edx, edx; dwFlags
0x18000276a  mov     rcx, rax; hHeap
0x18000276d  call    cs:__imp_HeapFree
0x180002773  mov     rcx, [rbx+30h]; hLibModule
0x180002777  mov     [rbx+40h], rsi
0x18000277b  test    rcx, rcx
0x18000277e  jz      short loc_18000278A
0x180002780  call    cs:__imp_FreeLibrary
0x180002786  mov     [rbx+30h], rsi
0x18000278a  test    byte ptr [rbx+50h], 1
0x18000278e  jz      short loc_1800027AC
0x180002790  mov     rdi, [rbx+48h]
0x180002794  call    cs:__imp_GetProcessHeap
0x18000279a  mov     r8, rdi; lpMem
0x18000279d  xor     edx, edx; dwFlags
0x18000279f  mov     rcx, rax; hHeap
0x1800027a2  call    cs:__imp_HeapFree
0x1800027a8  mov     [rbx+48h], rsi
0x1800027ac  mov     rcx, [rbx+58h]
0x1800027b0  test    rcx, rcx
0x1800027b3  jz      short loc_1800027BF
0x1800027b5  call    cs:__imp_TpReleaseAlpcCompletion
0x1800027bb  mov     [rbx+58h], rsi
0x1800027bf  mov     [rbx+28h], rsi
0x1800027c3  mov     [rbx+20h], rsi
0x1800027c7  mov     [rbx+18h], rsi
0x1800027cb  mov     [rbx+30h], rsi
0x1800027cf  call    cs:__imp_GetProcessHeap
0x1800027d5  mov     r8, rbx; lpMem
0x1800027d8  xor     edx, edx; dwFlags
0x1800027da  mov     rcx, rax; hHeap
0x1800027dd  call    cs:__imp_HeapFree
0x1800027e3  mov     rbx, cs:g_pWdiSessionHead
0x1800027ea  test    rbx, rbx
0x1800027ed  jnz     loc_180002750
0x1800027f3  mov     rdi, [rsp+28h+arg_8]
0x1800027f8  mov     rbx, cs:g_pWdiInstanceHead
0x1800027ff  test    rbx, rbx
0x180002802  jz      short loc_180002858
0x180002804  nop     dword ptr [rax+00h]
0x180002808  nop     dword ptr [rax+rax+00000000h]
0x180002810  lea     rcx, [rbx+20h]
0x180002814  mov     rax, [rbx+40h]
0x180002818  mov     cs:g_pWdiInstanceHead, rax
0x18000281f  cmp     [rcx], rsi
0x180002822  jz      short loc_180002829
0x180002824  call    WdipDeleteParameterCollection
0x180002829  cmp     [rbx+18h], rsi
0x18000282d  lea     rcx, [rbx+18h]
0x180002831  jz      short loc_180002838
0x180002833  call    WdipDeleteParameterCollection
0x180002838  call    cs:__imp_GetProcessHeap
0x18000283e  mov     r8, rbx; lpMem
0x180002841  xor     edx, edx; dwFlags
0x180002843  mov     rcx, rax; hHeap
0x180002846  call    cs:__imp_HeapFree
0x18000284c  mov     rbx, cs:g_pWdiInstanceHead
0x180002853  test    rbx, rbx
0x180002856  jnz     short loc_180002810
0x180002858  mov     rcx, cs:g_pHostAlpcCompletion
0x18000285f  mov     rbx, [rsp+28h+arg_0]
0x180002864  test    rcx, rcx
0x180002867  jz      short loc_180002876
0x180002869  call    cs:__imp_TpReleaseAlpcCompletion
0x18000286f  mov     cs:g_pHostAlpcCompletion, rsi
0x180002876  add     rsp, 20h
0x18000287a  pop     rsi
0x18000287b  retn
```
