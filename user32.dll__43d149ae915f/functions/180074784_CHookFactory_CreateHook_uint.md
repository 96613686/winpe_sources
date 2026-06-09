# CHookFactory::CreateHook(uint)

- ea: `0x180074784`
- end: `0x1800748aa`
- name: `?CreateHook@CHookFactory@@SAPEAVILocalHook@@I@Z`
- size: `294`
- prototype: `struct ILocalHook *__fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18007471c`

## callees

- `0x180074784`
- `0x180096dc5`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800747b4`
- `ntdll!RtlAllocateHeap` at `0x18007480a`
- `ntdll!RtlAllocateHeap` at `0x18007485d`
- `ntdll!RtlAllocateHeap` at `0x1800747b4`
- `ntdll!RtlAllocateHeap` at `0x18007480a`
- `ntdll!RtlAllocateHeap` at `0x18007485d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800747e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007483b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007488a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800747e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007483b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007488a`

## pseudocode

```c
struct ILocalHook *__fastcall CHookFactory::CreateHook(int a1)
{
  int v1; // ecx
  int v2; // ecx
  _OWORD *v4; // rax
  _OWORD *v5; // rbx
  void **v6; // rax
  _OWORD *v7; // rax
  _OWORD *Heap; // rax

  v1 = a1 - 3;
  if ( !v1 )
  {
    Heap = RtlAllocateHeap(pUserHeap, 8u, 0x68u);
    v5 = Heap;
    if ( Heap )
    {
      memset_0(Heap, 0, 0x68u);
      *((_DWORD *)v5 + 11) = 3;
      *(_QWORD *)v5 = &CBaseLocalHook<7>::`vftable';
      *((_DWORD *)v5 + 10) = GetCurrentThreadId();
      v6 = &CGetMessageHook::`vftable';
      goto LABEL_11;
    }
    return 0;
  }
  v2 = v1 - 1;
  if ( !v2 )
  {
    v7 = RtlAllocateHeap(pUserHeap, 8u, 0x30u);
    v5 = v7;
    if ( v7 )
    {
      *v7 = 0;
      v7[1] = 0;
      v7[2] = 0;
      *((_DWORD *)v7 + 11) = 4;
      *(_QWORD *)v7 = &CBaseLocalHook<7>::`vftable';
      *((_DWORD *)v7 + 10) = GetCurrentThreadId();
      v6 = &CCallWndProcHook::`vftable';
      goto LABEL_11;
    }
    return 0;
  }
  if ( v2 != 3 )
    return 0;
  v4 = RtlAllocateHeap(pUserHeap, 8u, 0x30u);
  v5 = v4;
  if ( !v4 )
    return 0;
  *v4 = 0;
  v4[1] = 0;
  v4[2] = 0;
  *((_DWORD *)v4 + 11) = 7;
  *(_QWORD *)v4 = &CBaseLocalHook<7>::`vftable';
  *((_DWORD *)v4 + 10) = GetCurrentThreadId();
  v6 = &CMouseHook::`vftable';
LABEL_11:
  *(_QWORD *)v5 = v6;
  return (struct ILocalHook *)v5;
}

```

## disassembly

```asm
0x180074784  push    rbx
0x180074786  sub     rsp, 20h
0x18007478a  sub     ecx, 3
0x18007478d  jz      loc_18007484D
0x180074793  sub     ecx, 1
0x180074796  jz      short loc_1800747FA
0x180074798  cmp     ecx, 3
0x18007479b  jz      short loc_1800747A4
0x18007479d  xor     eax, eax
0x18007479f  jmp     loc_1800748A4
0x1800747a4  mov     rcx, cs:pUserHeap; HeapHandle
0x1800747ab  mov     edx, 8; Flags
0x1800747b0  lea     r8d, [rdx+28h]; Size
0x1800747b4  call    cs:__imp_RtlAllocateHeap
0x1800747ba  mov     rbx, rax
0x1800747bd  test    rax, rax
0x1800747c0  jz      loc_18007489F
0x1800747c6  xorps   xmm0, xmm0
0x1800747c9  movups  xmmword ptr [rax], xmm0
0x1800747cc  movups  xmmword ptr [rax+10h], xmm0
0x1800747d0  movups  xmmword ptr [rax+20h], xmm0
0x1800747d4  lea     rax, ??_7?$CBaseLocalHook@$06@@6B@; const CBaseLocalHook<7>::`vftable'
0x1800747db  mov     dword ptr [rbx+2Ch], 7
0x1800747e2  mov     [rbx], rax
0x1800747e5  call    cs:__imp_GetCurrentThreadId
0x1800747eb  mov     [rbx+28h], eax
0x1800747ee  lea     rax, ??_7CMouseHook@@6B@; const CMouseHook::`vftable'
0x1800747f5  jmp     loc_18007489A
0x1800747fa  mov     rcx, cs:pUserHeap; HeapHandle
0x180074801  mov     edx, 8; Flags
0x180074806  lea     r8d, [rdx+28h]; Size
0x18007480a  call    cs:__imp_RtlAllocateHeap
0x180074810  mov     rbx, rax
0x180074813  test    rax, rax
0x180074816  jz      loc_18007489F
0x18007481c  xorps   xmm0, xmm0
0x18007481f  movups  xmmword ptr [rax], xmm0
0x180074822  movups  xmmword ptr [rax+10h], xmm0
0x180074826  movups  xmmword ptr [rax+20h], xmm0
0x18007482a  lea     rax, ??_7?$CBaseLocalHook@$06@@6B@; const CBaseLocalHook<7>::`vftable'
0x180074831  mov     dword ptr [rbx+2Ch], 4
0x180074838  mov     [rbx], rax
0x18007483b  call    cs:__imp_GetCurrentThreadId
0x180074841  mov     [rbx+28h], eax
0x180074844  lea     rax, ??_7CCallWndProcHook@@6B@; const CCallWndProcHook::`vftable'
0x18007484b  jmp     short loc_18007489A
0x18007484d  mov     rcx, cs:pUserHeap; HeapHandle
0x180074854  mov     edx, 8; Flags
0x180074859  lea     r8d, [rdx+60h]; Size
0x18007485d  call    cs:__imp_RtlAllocateHeap
0x180074863  mov     rbx, rax
0x180074866  test    rax, rax
0x180074869  jz      short loc_18007489F
0x18007486b  xor     edx, edx; Val
0x18007486d  mov     rcx, rax; void *
0x180074870  lea     r8d, [rdx+68h]; Size
0x180074874  call    memset_0
0x180074879  lea     rax, ??_7?$CBaseLocalHook@$06@@6B@; const CBaseLocalHook<7>::`vftable'
0x180074880  mov     dword ptr [rbx+2Ch], 3
0x180074887  mov     [rbx], rax
0x18007488a  call    cs:__imp_GetCurrentThreadId
0x180074890  mov     [rbx+28h], eax
0x180074893  lea     rax, ??_7CGetMessageHook@@6B@; const CGetMessageHook::`vftable'
0x18007489a  mov     [rbx], rax
0x18007489d  jmp     short loc_1800748A1
0x18007489f  xor     ebx, ebx
0x1800748a1  mov     rax, rbx
0x1800748a4  add     rsp, 20h
0x1800748a8  pop     rbx
0x1800748a9  retn
```
