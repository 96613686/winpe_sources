# FreeDirScanArgs(DIRECTORY_SCAN_FUNC_ARGS)

- ea: `0x1800210e4`
- end: `0x1800212e9`
- name: `?FreeDirScanArgs@@YAXUDIRECTORY_SCAN_FUNC_ARGS@@@Z`
- size: `517`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800227a4`

## callees

- `0x180005604`
- `0x180017bf8`
- `0x1800210e4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021111`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002112d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002114d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002116d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002118d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800211ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800211cd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800211ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002122f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021253`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021289`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800212b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021111`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002112d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002114d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002116d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002118d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800211ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800211cd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800211ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002122f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021253`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021289`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800212b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021102`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002111e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002113f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002115f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002117f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002119f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800211bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800211df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021221`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021245`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002127b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800212a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021102`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002111e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002113f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002115f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002117f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002119f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800211bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800211df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021221`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021245`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002127b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800212a4`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180021269`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180021269`

## pseudocode

```c
void __fastcall FreeDirScanArgs(__int64 a1)
{
  HANDLE ProcessHeap; // rax
  HANDLE v3; // rax
  void *v4; // rdi
  HANDLE v5; // rax
  void *v6; // rdi
  HANDLE v7; // rax
  void *v8; // rdi
  HANDLE v9; // rax
  void *v10; // rdi
  HANDLE v11; // rax
  void *v12; // rdi
  HANDLE v13; // rax
  void *v14; // rdi
  HANDLE v15; // rax
  void *v16; // rdi
  HANDLE v17; // rax
  void *v18; // rbx
  HANDLE v19; // rax
  void *v20; // rcx
  void *v21; // rdi
  HANDLE v22; // rax
  void *v23; // rdi
  HANDLE v24; // rax
  void *v25; // rbx

  if ( *(_QWORD *)(a1 + 104) )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 8u, *(LPVOID *)(a1 + 104));
  }
  if ( *(_QWORD *)(a1 + 112) )
  {
    v3 = GetProcessHeap();
    HeapFree(v3, 8u, *(LPVOID *)(a1 + 112));
  }
  v4 = *(void **)(a1 + 136);
  if ( v4 )
  {
    v5 = GetProcessHeap();
    HeapFree(v5, 8u, v4);
  }
  v6 = *(void **)(a1 + 144);
  if ( v6 )
  {
    v7 = GetProcessHeap();
    HeapFree(v7, 8u, v6);
  }
  v8 = *(void **)(a1 + 720);
  if ( v8 )
  {
    v9 = GetProcessHeap();
    HeapFree(v9, 8u, v8);
  }
  v10 = *(void **)(a1 + 728);
  if ( v10 )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 8u, v10);
  }
  v12 = *(void **)(a1 + 736);
  if ( v12 )
  {
    v13 = GetProcessHeap();
    HeapFree(v13, 8u, v12);
  }
  v14 = *(void **)(a1 + 744);
  if ( v14 )
  {
    v15 = GetProcessHeap();
    HeapFree(v15, 8u, v14);
  }
  if ( *(_DWORD *)a1 == 3 || *(_DWORD *)a1 == 4 )
  {
    v23 = *(void **)(a1 + 152);
    if ( v23 )
    {
      v24 = GetProcessHeap();
      HeapFree(v24, 8u, v23);
    }
    v25 = *(void **)(a1 + 160);
    if ( v25 )
    {
      std::_Tree<std::_Tmap_traits<unsigned long,unsigned __int64,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,unsigned __int64,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,unsigned __int64>>,0>>(v25);
      operator delete(v25);
    }
  }
  else
  {
    if ( *(_DWORD *)a1 == 7 )
    {
      v20 = *(void **)(a1 + 152);
      if ( v20 )
        BCryptCloseAlgorithmProvider(v20, 0);
      v21 = *(void **)(a1 + 176);
      if ( v21 )
      {
        v22 = GetProcessHeap();
        HeapFree(v22, 8u, v21);
      }
      v18 = *(void **)(a1 + 184);
    }
    else
    {
      if ( *(_DWORD *)a1 != 9 )
        return;
      v16 = *(void **)(a1 + 168);
      if ( v16 )
      {
        v17 = GetProcessHeap();
        HeapFree(v17, 8u, v16);
      }
      v18 = *(void **)(a1 + 176);
    }
    if ( v18 )
    {
      v19 = GetProcessHeap();
      HeapFree(v19, 8u, v18);
    }
  }
}

```

## disassembly

```asm
0x1800210e4  mov     [rsp+arg_0], rbx
0x1800210e9  mov     [rsp+arg_8], rsi
0x1800210ee  push    rdi
0x1800210ef  sub     rsp, 20h
0x1800210f3  cmp     qword ptr [rcx+68h], 0
0x1800210f8  mov     rbx, rcx
0x1800210fb  mov     esi, 8
0x180021100  jz      short loc_180021117
0x180021102  call    cs:__imp_GetProcessHeap
0x180021108  mov     r8, [rbx+68h]; lpMem
0x18002110c  mov     edx, esi; dwFlags
0x18002110e  mov     rcx, rax; hHeap
0x180021111  call    cs:__imp_HeapFree
0x180021117  cmp     qword ptr [rbx+70h], 0
0x18002111c  jz      short loc_180021133
0x18002111e  call    cs:__imp_GetProcessHeap
0x180021124  mov     r8, [rbx+70h]; lpMem
0x180021128  mov     edx, esi; dwFlags
0x18002112a  mov     rcx, rax; hHeap
0x18002112d  call    cs:__imp_HeapFree
0x180021133  mov     rdi, [rbx+88h]
0x18002113a  test    rdi, rdi
0x18002113d  jz      short loc_180021153
0x18002113f  call    cs:__imp_GetProcessHeap
0x180021145  mov     r8, rdi; lpMem
0x180021148  mov     edx, esi; dwFlags
0x18002114a  mov     rcx, rax; hHeap
0x18002114d  call    cs:__imp_HeapFree
0x180021153  mov     rdi, [rbx+90h]
0x18002115a  test    rdi, rdi
0x18002115d  jz      short loc_180021173
0x18002115f  call    cs:__imp_GetProcessHeap
0x180021165  mov     r8, rdi; lpMem
0x180021168  mov     edx, esi; dwFlags
0x18002116a  mov     rcx, rax; hHeap
0x18002116d  call    cs:__imp_HeapFree
0x180021173  mov     rdi, [rbx+2D0h]
0x18002117a  test    rdi, rdi
0x18002117d  jz      short loc_180021193
0x18002117f  call    cs:__imp_GetProcessHeap
0x180021185  mov     r8, rdi; lpMem
0x180021188  mov     edx, esi; dwFlags
0x18002118a  mov     rcx, rax; hHeap
0x18002118d  call    cs:__imp_HeapFree
0x180021193  mov     rdi, [rbx+2D8h]
0x18002119a  test    rdi, rdi
0x18002119d  jz      short loc_1800211B3
0x18002119f  call    cs:__imp_GetProcessHeap
0x1800211a5  mov     r8, rdi; lpMem
0x1800211a8  mov     edx, esi; dwFlags
0x1800211aa  mov     rcx, rax; hHeap
0x1800211ad  call    cs:__imp_HeapFree
0x1800211b3  mov     rdi, [rbx+2E0h]
0x1800211ba  test    rdi, rdi
0x1800211bd  jz      short loc_1800211D3
0x1800211bf  call    cs:__imp_GetProcessHeap
0x1800211c5  mov     r8, rdi; lpMem
0x1800211c8  mov     edx, esi; dwFlags
0x1800211ca  mov     rcx, rax; hHeap
0x1800211cd  call    cs:__imp_HeapFree
0x1800211d3  mov     rdi, [rbx+2E8h]
0x1800211da  test    rdi, rdi
0x1800211dd  jz      short loc_1800211F3
0x1800211df  call    cs:__imp_GetProcessHeap
0x1800211e5  mov     r8, rdi; lpMem
0x1800211e8  mov     edx, esi; dwFlags
0x1800211ea  mov     rcx, rax; hHeap
0x1800211ed  call    cs:__imp_HeapFree
0x1800211f3  mov     ecx, [rbx]
0x1800211f5  sub     ecx, 3
0x1800211f8  jz      loc_180021298
0x1800211fe  sub     ecx, 1
0x180021201  jz      loc_180021298
0x180021207  sub     ecx, 3
0x18002120a  jz      short loc_18002125B
0x18002120c  cmp     ecx, 2
0x18002120f  jnz     loc_1800212D9
0x180021215  mov     rdi, [rbx+0A8h]
0x18002121c  test    rdi, rdi
0x18002121f  jz      short loc_180021235
0x180021221  call    cs:__imp_GetProcessHeap
0x180021227  mov     r8, rdi; lpMem
0x18002122a  mov     edx, esi; dwFlags
0x18002122c  mov     rcx, rax; hHeap
0x18002122f  call    cs:__imp_HeapFree
0x180021235  mov     rbx, [rbx+0B0h]
0x18002123c  test    rbx, rbx
0x18002123f  jz      loc_1800212D9
0x180021245  call    cs:__imp_GetProcessHeap
0x18002124b  mov     r8, rbx; lpMem
0x18002124e  mov     edx, esi; dwFlags
0x180021250  mov     rcx, rax; hHeap
0x180021253  call    cs:__imp_HeapFree
0x180021259  jmp     short loc_1800212D9
0x18002125b  mov     rcx, [rbx+98h]; hAlgorithm
0x180021262  test    rcx, rcx
0x180021265  jz      short loc_18002126F
0x180021267  xor     edx, edx; dwFlags
0x180021269  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18002126f  mov     rdi, [rbx+0B0h]
0x180021276  test    rdi, rdi
0x180021279  jz      short loc_18002128F
0x18002127b  call    cs:__imp_GetProcessHeap
0x180021281  mov     r8, rdi; lpMem
0x180021284  mov     edx, esi; dwFlags
0x180021286  mov     rcx, rax; hHeap
0x180021289  call    cs:__imp_HeapFree
0x18002128f  mov     rbx, [rbx+0B8h]
0x180021296  jmp     short loc_18002123C
0x180021298  mov     rdi, [rbx+98h]
0x18002129f  test    rdi, rdi
0x1800212a2  jz      short loc_1800212B8
0x1800212a4  call    cs:__imp_GetProcessHeap
0x1800212aa  mov     r8, rdi; lpMem
0x1800212ad  mov     edx, esi; dwFlags
0x1800212af  mov     rcx, rax; hHeap
0x1800212b2  call    cs:__imp_HeapFree
0x1800212b8  mov     rbx, [rbx+0A0h]
0x1800212bf  test    rbx, rbx
0x1800212c2  jz      short loc_1800212D9
0x1800212c4  mov     rcx, rbx
0x1800212c7  call    ??1?$_Tree@V?$_Tmap_traits@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ulong,unsigned __int64,std::less<ulong>,std::allocator<std::pair<ulong const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<ulong,unsigned __int64,std::less<ulong>,std::allocator<std::pair<ulong const,unsigned __int64>>,0>>(void)
0x1800212cc  mov     edx, 10h
0x1800212d1  mov     rcx, rbx; Block
0x1800212d4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800212d9  mov     rbx, [rsp+28h+arg_0]
0x1800212de  mov     rsi, [rsp+28h+arg_8]
0x1800212e3  add     rsp, 20h
0x1800212e7  pop     rdi
0x1800212e8  retn
```
