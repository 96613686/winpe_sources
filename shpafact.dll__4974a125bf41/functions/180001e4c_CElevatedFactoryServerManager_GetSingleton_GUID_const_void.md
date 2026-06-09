# CElevatedFactoryServerManager::GetSingleton(_GUID const &,void * *)

- ea: `0x180001e4c`
- end: `0x180001f56`
- name: `?GetSingleton@CElevatedFactoryServerManager@@SAJAEBU_GUID@@PEAPEAX@Z`
- size: `266`
- prototype: `__int64 __fastcall(const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180002c00`

## callees

- `0x180001e4c`
- `0x1800026d4`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001ee6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001ee6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001e62`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001e62`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001e99`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001e99`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001e87`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001e87`

## pseudocode

```c
__int64 __fastcall CElevatedFactoryServerManager::GetSingleton(const struct _GUID *a1, void **a2)
{
  struct CElevatedFactoryServerManager *v4; // rbx
  int v5; // edi
  HANDLE ProcessHeap; // rax

  EnterCriticalSection(&g_csDll);
  v4 = g_pEFSM;
  if ( g_pEFSM )
  {
    (*(void (__fastcall **)(struct CElevatedFactoryServerManager *))(*(_QWORD *)g_pEFSM + 8LL))(g_pEFSM);
    v5 = 0;
  }
  else
  {
    ProcessHeap = GetProcessHeap();
    v4 = (struct CElevatedFactoryServerManager *)HeapAlloc(ProcessHeap, 8u, 0x18u);
    if ( v4 )
    {
      *(_QWORD *)v4 = &CElevatedFactoryServerManager::`vftable';
      *((_QWORD *)v4 + 1) = 0;
      _InterlockedIncrement(&g_cDllRefs);
      _InterlockedIncrement((volatile signed __int32 *)v4 + 4);
    }
    else
    {
      v4 = 0;
    }
    g_pEFSM = v4;
    v5 = v4 == 0 ? 0x8007000E : 0;
  }
  LeaveCriticalSection(&g_csDll);
  if ( v4 )
  {
    v5 = (**(__int64 (__fastcall ***)(struct CElevatedFactoryServerManager *, const struct _GUID *, void **))v4)(
           v4,
           a1,
           a2);
    (*(void (__fastcall **)(struct CElevatedFactoryServerManager *))(*(_QWORD *)v4 + 16LL))(v4);
  }
  if ( v5 < 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      0xDu,
      (const GUID *)WPP_0f628f1b17743b1a1d642676ad7906b4_Traceguids,
      v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180001e4c  push    rbx
0x180001e4e  push    rbp
0x180001e4f  push    rsi
0x180001e50  push    rdi
0x180001e51  sub     rsp, 28h
0x180001e55  mov     rbp, rcx
0x180001e58  mov     rsi, rdx
0x180001e5b  lea     rcx, g_csDll; lpCriticalSection
0x180001e62  call    cs:__imp_EnterCriticalSection
0x180001e68  mov     rbx, cs:?g_pEFSM@@3PEAVCElevatedFactoryServerManager@@EA; CElevatedFactoryServerManager * g_pEFSM
0x180001e6f  test    rbx, rbx
0x180001e72  jz      short loc_180001E87
0x180001e74  mov     rax, [rbx]
0x180001e77  mov     rcx, rbx
0x180001e7a  mov     rax, [rax+8]
0x180001e7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e83  xor     edi, edi
0x180001e85  jmp     short loc_180001EDF
0x180001e87  call    cs:__imp_GetProcessHeap
0x180001e8d  mov     edx, 8; dwFlags
0x180001e92  mov     rcx, rax; hHeap
0x180001e95  lea     r8d, [rdx+10h]; dwBytes
0x180001e99  call    cs:__imp_HeapAlloc
0x180001e9f  mov     rbx, rax
0x180001ea2  test    rax, rax
0x180001ea5  jz      short loc_180001EC6
0x180001ea7  lea     rax, ??_7CElevatedFactoryServerManager@@6B@; const CElevatedFactoryServerManager::`vftable'
0x180001eae  mov     [rbx], rax
0x180001eb1  mov     qword ptr [rbx+8], 0
0x180001eb9  lock inc cs:?g_cDllRefs@@3JA; long g_cDllRefs
0x180001ec0  lock inc dword ptr [rbx+10h]
0x180001ec4  jmp     short loc_180001EC8
0x180001ec6  xor     ebx, ebx
0x180001ec8  mov     rax, rbx
0x180001ecb  mov     cs:?g_pEFSM@@3PEAVCElevatedFactoryServerManager@@EA, rbx; CElevatedFactoryServerManager * g_pEFSM
0x180001ed2  neg     rax
0x180001ed5  sbb     edi, edi
0x180001ed7  not     edi
0x180001ed9  and     edi, 8007000Eh
0x180001edf  lea     rcx, g_csDll; lpCriticalSection
0x180001ee6  call    cs:__imp_LeaveCriticalSection
0x180001eec  test    rbx, rbx
0x180001eef  jz      short loc_180001F16
0x180001ef1  mov     rax, [rbx]
0x180001ef4  mov     r8, rsi
0x180001ef7  mov     rdx, rbp
0x180001efa  mov     rcx, rbx
0x180001efd  mov     rax, [rax]
0x180001f00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f05  mov     rdx, [rbx]
0x180001f08  mov     edi, eax
0x180001f0a  mov     rcx, rbx
0x180001f0d  mov     rax, [rdx+10h]
0x180001f11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f16  test    edi, edi
0x180001f18  jns     short loc_180001F4B
0x180001f1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180001f21  lea     rax, WPP_GLOBAL_Control
0x180001f28  cmp     rcx, rax
0x180001f2b  jz      short loc_180001F4B
0x180001f2d  test    byte ptr [rcx+1Ch], 4
0x180001f31  jz      short loc_180001F4B
0x180001f33  mov     rcx, [rcx+10h]
0x180001f37  lea     r8, WPP_0f628f1b17743b1a1d642676ad7906b4_Traceguids
0x180001f3e  mov     edx, 0Dh
0x180001f43  mov     r9d, edi
0x180001f46  call    WPP_SF_d
0x180001f4b  mov     eax, edi
0x180001f4d  add     rsp, 28h
0x180001f51  pop     rdi
0x180001f52  pop     rsi
0x180001f53  pop     rbp
0x180001f54  pop     rbx
0x180001f55  retn
```
