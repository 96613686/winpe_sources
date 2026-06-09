# QueryMultipleServicesHeapInformation

- ea: `0x140001250`
- end: `0x140001422`
- name: `QueryMultipleServicesHeapInformation`
- size: `466`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140001070`
- `0x140001110`

## callees

- `0x140001250`
- `0x140001430`
- `0x140004bd0`
- `0x1400054ee`
- `0x140005506`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140008752`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140008752`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140001417`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000873e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140001417`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000873e`
- `ntdll!RtlQueryHeapInformation` at `0x1400012ca`
- `ntdll!RtlQueryHeapInformation` at `0x1400012ca`

## pseudocode

```c
__int64 QueryMultipleServicesHeapInformation()
{
  _QWORD *v0; // rsi
  NTSTATUS v1; // eax
  unsigned int v2; // ebp
  unsigned int i; // ebx
  __int64 v4; // rdi
  int v6; // eax
  _QWORD *v7; // rax
  ULONG_PTR HeapInformationLength; // [rsp+30h] [rbp-228h] BYREF
  __int128 Key; // [rsp+38h] [rbp-220h] BYREF
  __int64 v10; // [rsp+48h] [rbp-210h]
  _BYTE HeapInformation[480]; // [rsp+50h] [rbp-208h] BYREF

  HeapInformationLength = 480;
  v10 = 0;
  Key = 0;
  v0 = HeapInformation;
  while ( 1 )
  {
    *v0 = 1;
    v0[2] = 0;
    v0[3] = 0;
    v0[4] = 0;
    v0[5] = 0;
    v0[1] = -1;
    v1 = RtlQueryHeapInformation(0, (HEAP_INFORMATION_CLASS)4, v0, HeapInformationLength, &HeapInformationLength);
    v2 = v1;
    if ( v1 != -1073741789 )
      break;
    if ( v0 != (_QWORD *)HeapInformation )
      HeapFree(g_hHeap, 0, v0);
    v0 = HeapAlloc(g_hHeap, 0, HeapInformationLength);
    if ( !v0 )
      return 3221225495LL;
  }
  if ( v1 >= 0 )
  {
    if ( (*((_BYTE *)v0 + 2) & 1) != 0 )
    {
      o_qsort_s_0(v0 + 3, v0[2], 0x18u, CompareHeapTags, 0);
      for ( i = 0; i < ServiceCount; ++i )
      {
        v4 = 96LL * i;
        if ( *(_DWORD *)(v4 + ServiceArray + 48) )
        {
          v6 = *(_DWORD *)(v4 + ServiceArray + 52);
          Key = 0;
          LODWORD(Key) = v6;
          v7 = o_bsearch_s_0(&Key, v0 + 3, v0[2], 0x18u, CompareHeapTags, 0);
          if ( v7 )
            UpdateServiceHeapInformation(v4 + ServiceArray, v7[2]);
        }
      }
    }
    else
    {
      v2 = -1073741637;
    }
  }
  if ( v0 != (_QWORD *)HeapInformation )
    HeapFree(g_hHeap, 0, v0);
  return v2;
}

```

## disassembly

```asm
0x140001250  mov     [rsp+arg_18], rbx
0x140001255  push    rbp
0x140001256  push    rsi
0x140001257  push    r15
0x140001259  sub     rsp, 240h
0x140001260  mov     rax, cs:__security_cookie
0x140001267  xor     rax, rsp
0x14000126a  mov     [rsp+258h+var_28], rax
0x140001272  xor     eax, eax
0x140001274  mov     [rsp+258h+HeapInformationLength], 1E0h
0x14000127d  xorps   xmm0, xmm0
0x140001280  mov     [rsp+258h+var_210], rax
0x140001285  movups  [rsp+258h+Key], xmm0
0x14000128a  xor     r15d, r15d
0x14000128d  lea     rsi, [rsp+258h+HeapInformation]
0x140001292  mov     qword ptr [rsi], 1
0x140001299  lea     rax, [rsp+258h+HeapInformationLength]
0x14000129e  mov     [rsi+10h], r15
0x1400012a2  mov     r8, rsi; HeapInformation
0x1400012a5  mov     [rsi+18h], r15
0x1400012a9  mov     edx, 4; HeapInformationClass
0x1400012ae  mov     [rsi+20h], r15
0x1400012b2  xor     ecx, ecx; HeapHandle
0x1400012b4  mov     [rsi+28h], r15
0x1400012b8  mov     qword ptr [rsi+8], 0FFFFFFFFFFFFFFFFh
0x1400012c0  mov     r9, [rsp+258h+HeapInformationLength]; HeapInformationLength
0x1400012c5  mov     [rsp+258h+ReturnLength], rax; ReturnLength
0x1400012ca  call    cs:__imp_RtlQueryHeapInformation
0x1400012d0  mov     ebp, eax
0x1400012d2  cmp     eax, 0C0000023h
0x1400012d7  jz      loc_140008728
0x1400012dd  test    eax, eax
0x1400012df  js      loc_14000137A
0x1400012e5  test    byte ptr [rsi+2], 1
0x1400012e9  jz      loc_140001401
0x1400012ef  mov     rdx, [rsi+10h]; NumOfElements
0x1400012f3  lea     rcx, [rsi+18h]; Base
0x1400012f7  mov     [rsp+258h+arg_8], r12
0x1400012ff  mov     r8d, 18h; SizeOfElements
0x140001305  lea     r12, CompareHeapTags
0x14000130c  mov     [rsp+258h+arg_10], r14
0x140001314  mov     r9, r12; CompareFunction
0x140001317  mov     [rsp+258h+ReturnLength], r15; Context
0x14000131c  call    _o_qsort_s_0
0x140001321  cmp     cs:ServiceCount, r15d
0x140001328  mov     ebx, r15d
0x14000132b  jbe     short loc_14000136A
0x14000132d  mov     [rsp+258h+arg_0], rdi
0x140001335  nop     word ptr [rax+rax+00000000h]
0x140001340  mov     eax, ebx
0x140001342  lea     rdi, [rax+rax*2]
0x140001346  mov     rax, cs:ServiceArray
0x14000134d  shl     rdi, 5
0x140001351  cmp     [rdi+rax+30h], r15d
0x140001356  jnz     short loc_1400013AE
0x140001358  inc     ebx
0x14000135a  cmp     ebx, cs:ServiceCount
0x140001360  jb      short loc_140001340
0x140001362  mov     rdi, [rsp+258h+arg_0]
0x14000136a  mov     r12, [rsp+258h+arg_8]
0x140001372  mov     r14, [rsp+258h+arg_10]
0x14000137a  lea     rax, [rsp+258h+HeapInformation]
0x14000137f  cmp     rsi, rax
0x140001382  jnz     loc_14000140B
0x140001388  mov     eax, ebp
0x14000138a  mov     rcx, [rsp+258h+var_28]
0x140001392  xor     rcx, rsp; StackCookie
0x140001395  call    __security_check_cookie
0x14000139a  mov     rbx, [rsp+258h+arg_18]
0x1400013a2  add     rsp, 240h
0x1400013a9  pop     r15
0x1400013ab  pop     rsi
0x1400013ac  pop     rbp
0x1400013ad  retn
0x1400013ae  mov     eax, [rdi+rax+34h]
0x1400013b2  lea     rdx, [rsi+18h]; Base
0x1400013b6  xorps   xmm0, xmm0
0x1400013b9  mov     [rsp+258h+Context], r15; Context
0x1400013be  movups  [rsp+258h+Key], xmm0
0x1400013c3  mov     dword ptr [rsp+258h+Key], eax
0x1400013c7  lea     rcx, [rsp+258h+Key]; Key
0x1400013cc  mov     r8, [rsi+10h]; NumOfElements
0x1400013d0  mov     r9d, 18h; SizeOfElements
0x1400013d6  mov     [rsp+258h+ReturnLength], r12; CompareFunction
0x1400013db  call    _o_bsearch_s_0
0x1400013e0  test    rax, rax
0x1400013e3  jz      loc_140001358
0x1400013e9  mov     rcx, cs:ServiceArray
0x1400013f0  mov     rdx, [rax+10h]
0x1400013f4  add     rcx, rdi
0x1400013f7  call    UpdateServiceHeapInformation
0x1400013fc  jmp     loc_140001358
0x140001401  mov     ebp, 0C00000BBh
0x140001406  jmp     loc_14000137A
0x14000140b  mov     rcx, cs:g_hHeap; hHeap
0x140001412  mov     r8, rsi; lpMem
0x140001415  xor     edx, edx; dwFlags
0x140001417  call    cs:__imp_HeapFree
0x14000141d  jmp     loc_140001388
0x140008728  lea     rax, [rsp+258h+HeapInformation]
0x14000872d  cmp     rsi, rax
0x140008730  jz      short loc_140008744
0x140008732  mov     rcx, cs:g_hHeap; hHeap
0x140008739  mov     r8, rsi; lpMem
0x14000873c  xor     edx, edx; dwFlags
0x14000873e  call    cs:__imp_HeapFree
0x140008744  mov     r8, [rsp+258h+HeapInformationLength]; dwBytes
0x140008749  xor     edx, edx; dwFlags
0x14000874b  mov     rcx, cs:g_hHeap; hHeap
0x140008752  call    cs:__imp_HeapAlloc
0x140008758  mov     rsi, rax
0x14000875b  test    rax, rax
0x14000875e  jnz     loc_140001292
0x140008764  mov     eax, 0C0000017h
0x140008769  jmp     loc_14000138A
```
