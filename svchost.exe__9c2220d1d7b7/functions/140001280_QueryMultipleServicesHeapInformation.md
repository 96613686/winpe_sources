# QueryMultipleServicesHeapInformation

- ea: `0x140001280`
- end: `0x14000143c`
- name: `QueryMultipleServicesHeapInformation`
- size: `444`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140001070`
- `0x140001120`

## callees

- `0x140001280`
- `0x140001450`
- `0x140004f90`
- `0x1400058ce`
- `0x1400058e6`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140008da8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140008da8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008d8e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008dd6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008d8e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008dd6`
- `ntdll!RtlQueryHeapInformation` at `0x1400012fa`
- `ntdll!RtlQueryHeapInformation` at `0x1400012fa`

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
0x140001280  mov     [rsp+arg_18], rbx
0x140001285  push    rbp
0x140001286  push    rsi
0x140001287  push    r15
0x140001289  sub     rsp, 240h
0x140001290  mov     rax, cs:__security_cookie
0x140001297  xor     rax, rsp
0x14000129a  mov     [rsp+258h+var_28], rax
0x1400012a2  xor     eax, eax
0x1400012a4  mov     [rsp+258h+HeapInformationLength], 1E0h
0x1400012ad  xorps   xmm0, xmm0
0x1400012b0  mov     [rsp+258h+var_210], rax
0x1400012b5  movups  [rsp+258h+Key], xmm0
0x1400012ba  xor     r15d, r15d
0x1400012bd  lea     rsi, [rsp+258h+HeapInformation]
0x1400012c2  mov     qword ptr [rsi], 1
0x1400012c9  lea     rax, [rsp+258h+HeapInformationLength]
0x1400012ce  mov     [rsi+10h], r15
0x1400012d2  mov     r8, rsi; HeapInformation
0x1400012d5  mov     [rsi+18h], r15
0x1400012d9  mov     edx, 4; HeapInformationClass
0x1400012de  mov     [rsi+20h], r15
0x1400012e2  xor     ecx, ecx; HeapHandle
0x1400012e4  mov     [rsi+28h], r15
0x1400012e8  mov     qword ptr [rsi+8], 0FFFFFFFFFFFFFFFFh
0x1400012f0  mov     r9, [rsp+258h+HeapInformationLength]; HeapInformationLength
0x1400012f5  mov     [rsp+258h+ReturnLength], rax; ReturnLength
0x1400012fa  call    cs:__imp_RtlQueryHeapInformation
0x140001301  nop     dword ptr [rax+rax+00h]
0x140001306  mov     ebp, eax
0x140001308  cmp     eax, 0C0000023h
0x14000130d  jz      loc_140008D78
0x140001313  test    eax, eax
0x140001315  js      loc_1400013AA
0x14000131b  test    byte ptr [rsi+2], 1
0x14000131f  jz      loc_140001432
0x140001325  mov     rdx, [rsi+10h]; NumOfElements
0x140001329  lea     rcx, [rsi+18h]; Base
0x14000132d  mov     [rsp+258h+arg_8], r12
0x140001335  mov     r8d, 18h; SizeOfElements
0x14000133b  lea     r12, CompareHeapTags
0x140001342  mov     [rsp+258h+arg_10], r14
0x14000134a  mov     r9, r12; CompareFunction
0x14000134d  mov     [rsp+258h+ReturnLength], r15; Context
0x140001352  call    _o_qsort_s_0
0x140001357  cmp     cs:ServiceCount, r15d
0x14000135e  mov     ebx, r15d
0x140001361  jbe     short loc_14000139A
0x140001363  mov     [rsp+258h+arg_0], rdi
0x14000136b  nop     dword ptr [rax+rax+00h]
0x140001370  mov     eax, ebx
0x140001372  lea     rdi, [rax+rax*2]
0x140001376  mov     rax, cs:ServiceArray
0x14000137d  shl     rdi, 5
0x140001381  cmp     [rdi+rax+30h], r15d
0x140001386  jnz     short loc_1400013DF
0x140001388  inc     ebx
0x14000138a  cmp     ebx, cs:ServiceCount
0x140001390  jb      short loc_140001370
0x140001392  mov     rdi, [rsp+258h+arg_0]
0x14000139a  mov     r12, [rsp+258h+arg_8]
0x1400013a2  mov     r14, [rsp+258h+arg_10]
0x1400013aa  lea     rax, [rsp+258h+HeapInformation]
0x1400013af  cmp     rsi, rax
0x1400013b2  jnz     loc_140008DCA
0x1400013b8  mov     eax, ebp
0x1400013ba  mov     rcx, [rsp+258h+var_28]
0x1400013c2  xor     rcx, rsp; StackCookie
0x1400013c5  call    __security_check_cookie
0x1400013ca  mov     rbx, [rsp+258h+arg_18]
0x1400013d2  add     rsp, 240h
0x1400013d9  pop     r15
0x1400013db  pop     rsi
0x1400013dc  pop     rbp
0x1400013dd  retn
0x1400013df  mov     eax, [rdi+rax+34h]
0x1400013e3  lea     rdx, [rsi+18h]; Base
0x1400013e7  xorps   xmm0, xmm0
0x1400013ea  mov     [rsp+258h+Context], r15; Context
0x1400013ef  movups  [rsp+258h+Key], xmm0
0x1400013f4  mov     dword ptr [rsp+258h+Key], eax
0x1400013f8  lea     rcx, [rsp+258h+Key]; Key
0x1400013fd  mov     r8, [rsi+10h]; NumOfElements
0x140001401  mov     r9d, 18h; SizeOfElements
0x140001407  mov     [rsp+258h+ReturnLength], r12; CompareFunction
0x14000140c  call    _o_bsearch_s_0
0x140001411  test    rax, rax
0x140001414  jz      loc_140001388
0x14000141a  mov     rcx, cs:ServiceArray
0x140001421  mov     rdx, [rax+10h]
0x140001425  add     rcx, rdi
0x140001428  call    UpdateServiceHeapInformation
0x14000142d  jmp     loc_140001388
0x140001432  mov     ebp, 0C00000BBh
0x140001437  jmp     loc_1400013AA
0x140008d78  lea     rax, [rsp+258h+HeapInformation]
0x140008d7d  cmp     rsi, rax
0x140008d80  jz      short loc_140008D9A
0x140008d82  mov     rcx, cs:g_hHeap; hHeap
0x140008d89  mov     r8, rsi; lpMem
0x140008d8c  xor     edx, edx; dwFlags
0x140008d8e  call    cs:__imp_HeapFree
0x140008d95  nop     dword ptr [rax+rax+00h]
0x140008d9a  mov     r8, [rsp+258h+HeapInformationLength]; dwBytes
0x140008d9f  xor     edx, edx; dwFlags
0x140008da1  mov     rcx, cs:g_hHeap; hHeap
0x140008da8  call    cs:__imp_HeapAlloc
0x140008daf  nop     dword ptr [rax+rax+00h]
0x140008db4  mov     rsi, rax
0x140008db7  test    rax, rax
0x140008dba  jnz     loc_1400012C2
0x140008dc0  mov     eax, 0C0000017h
0x140008dc5  jmp     loc_1400013BA
0x140008dca  mov     rcx, cs:g_hHeap; hHeap
0x140008dd1  mov     r8, rsi; lpMem
0x140008dd4  xor     edx, edx; dwFlags
0x140008dd6  call    cs:__imp_HeapFree
0x140008ddd  nop     dword ptr [rax+rax+00h]
0x140008de2  nop
0x140008de3  jmp     loc_1400013B8
```
