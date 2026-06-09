# CElevatedFactoryServerManager::SetFactory(_GUID const &,IElevatedFactoryServer *)

- ea: `0x180002150`
- end: `0x180002337`
- name: `?SetFactory@CElevatedFactoryServerManager@@UEAAJAEBU_GUID@@PEAUIElevatedFactoryServer@@@Z`
- size: `487`
- prototype: `__int64 __fastcall(CElevatedFactoryServerManager *__hidden this, const struct _GUID *, struct IElevatedFactoryServer *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180002150`
- `0x1800026ac`
- `0x1800026d4`
- `0x180003320`
- `0x180003460`
- `0x180003520`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800022d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800022d1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002203`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002203`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800021a2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800021a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002190`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002190`

## pseudocode

```c
__int64 __fastcall CElevatedFactoryServerManager::SetFactory(
        CElevatedFactoryServerManager *this,
        const struct _GUID *a2,
        struct IElevatedFactoryServer *a3)
{
  int v3; // edi
  HDPA v7; // rax
  HANDLE ProcessHeap; // rax
  char *v9; // rax
  _QWORD *v10; // rbx
  __int64 v11; // rcx
  int i; // ebp
  struct _DPA *v13; // rcx
  int v14; // eax
  _QWORD *Ptr; // rdi
  __int64 v16; // rcx

  v3 = -2147024882;
  if ( !*((_QWORD *)this + 1) )
  {
    v7 = g_pfn_DPA_Create(8);
    *((_QWORD *)this + 1) = v7;
    if ( !v7 )
      goto LABEL_33;
  }
  ProcessHeap = GetProcessHeap();
  v9 = (char *)HeapAlloc(ProcessHeap, 8u, 0x20u);
  v10 = v9;
  if ( !v9 )
    goto LABEL_33;
  *((_QWORD *)v9 + 3) = 0;
  *(_QWORD *)v9 = &CElevatedFactoryServerManager::CFactoryData::`vftable';
  *(struct _GUID *)(v9 + 8) = *a2;
  if ( a3 )
  {
    (*(void (__fastcall **)(struct IElevatedFactoryServer *))(*(_QWORD *)a3 + 8LL))(a3);
    v11 = v10[3];
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v10[3] = a3;
  }
  EnterCriticalSection(&g_csDll);
  for ( i = 0; ; ++i )
  {
    v13 = (struct _DPA *)*((_QWORD *)this + 1);
    v14 = v13 ? *(_DWORD *)v13 : 0;
    if ( i >= v14 )
      break;
    Ptr = g_pfn_DPA_GetPtr(v13, i);
    if ( Ptr[1] == *(_QWORD *)&a2->Data1 && Ptr[2] == *(_QWORD *)a2->Data4 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_0f628f1b17743b1a1d642676ad7906b4_Traceguids);
      if ( (struct IElevatedFactoryServer *)Ptr[3] != a3 )
      {
        if ( a3 )
          (*(void (__fastcall **)(struct IElevatedFactoryServer *))(*(_QWORD *)a3 + 8LL))(a3);
        v16 = Ptr[3];
        if ( v16 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
        Ptr[3] = a3;
      }
      v3 = 0;
      goto LABEL_29;
    }
  }
  v3 = 0;
  if ( DPA_InsertPtr(v13, 0x7FFFFFFF, v10) == -1 )
    v3 = -2147024882;
  v10 = 0;
LABEL_29:
  LeaveCriticalSection(&g_csDll);
  if ( v10 )
    (*(void (__fastcall **)(_QWORD *, __int64))*v10)(v10, 1);
  if ( v3 < 0 )
  {
LABEL_33:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        WPP_0f628f1b17743b1a1d642676ad7906b4_Traceguids,
        (unsigned int)v3);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180002150  push    rbx
0x180002152  push    rbp
0x180002153  push    rsi
0x180002154  push    rdi
0x180002155  push    r13
0x180002157  push    r14
0x180002159  push    r15
0x18000215b  sub     rsp, 20h
0x18000215f  cmp     qword ptr [rcx+8], 0
0x180002164  mov     r13d, 8007000Eh
0x18000216a  mov     edi, r13d
0x18000216d  mov     rsi, r8
0x180002170  mov     r15, rdx
0x180002173  mov     r14, rcx
0x180002176  jnz     short loc_180002190
0x180002178  mov     ecx, 8; cItemGrow
0x18000217d  call    cs:g_pfn_DPA_Create
0x180002183  mov     [r14+8], rax
0x180002187  test    rax, rax
0x18000218a  jz      loc_1800022F5
0x180002190  call    cs:__imp_GetProcessHeap
0x180002196  mov     edx, 8; dwFlags
0x18000219b  mov     rcx, rax; hHeap
0x18000219e  lea     r8d, [rdx+18h]; dwBytes
0x1800021a2  call    cs:__imp_HeapAlloc
0x1800021a8  mov     rbx, rax
0x1800021ab  test    rax, rax
0x1800021ae  jz      loc_1800022F5
0x1800021b4  mov     qword ptr [rbx+18h], 0
0x1800021bc  lea     rax, ??_7CFactoryData@CElevatedFactoryServerManager@@6B@; const CElevatedFactoryServerManager::CFactoryData::`vftable'
0x1800021c3  mov     [rbx], rax
0x1800021c6  movups  xmm0, xmmword ptr [r15]
0x1800021ca  movdqu  xmmword ptr [rbx+8], xmm0
0x1800021cf  test    rsi, rsi
0x1800021d2  jz      short loc_1800021FC
0x1800021d4  mov     rax, [rsi]
0x1800021d7  mov     rcx, rsi
0x1800021da  mov     rax, [rax+8]
0x1800021de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021e3  mov     rcx, [rbx+18h]
0x1800021e7  test    rcx, rcx
0x1800021ea  jz      short loc_1800021F8
0x1800021ec  mov     rax, [rcx]
0x1800021ef  mov     rax, [rax+10h]
0x1800021f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021f8  mov     [rbx+18h], rsi
0x1800021fc  lea     rcx, g_csDll; lpCriticalSection
0x180002203  call    cs:__imp_EnterCriticalSection
0x180002209  xor     ebp, ebp
0x18000220b  mov     rcx, [r14+8]; hdpa
0x18000220f  test    rcx, rcx
0x180002212  jz      short loc_180002218
0x180002214  mov     eax, [rcx]
0x180002216  jmp     short loc_18000221A
0x180002218  xor     eax, eax
0x18000221a  cmp     ebp, eax
0x18000221c  jge     loc_1800022AA
0x180002222  movsxd  rdx, ebp; i
0x180002225  call    cs:g_pfn_DPA_GetPtr
0x18000222b  mov     rdi, rax
0x18000222e  mov     rax, [rax+8]
0x180002232  cmp     rax, [r15]
0x180002235  jnz     short loc_180002241
0x180002237  mov     rax, [rdi+10h]
0x18000223b  cmp     rax, [r15+8]
0x18000223f  jz      short loc_180002245
0x180002241  inc     ebp
0x180002243  jmp     short loc_18000220B
0x180002245  mov     rcx, cs:WPP_GLOBAL_Control
0x18000224c  lea     rbp, WPP_GLOBAL_Control
0x180002253  cmp     rcx, rbp
0x180002256  jz      short loc_180002273
0x180002258  test    byte ptr [rcx+1Ch], 8
0x18000225c  jz      short loc_180002273
0x18000225e  mov     rcx, [rcx+10h]
0x180002262  lea     r8, WPP_0f628f1b17743b1a1d642676ad7906b4_Traceguids
0x180002269  mov     edx, 0Eh
0x18000226e  call    WPP_SF_
0x180002273  cmp     [rdi+18h], rsi
0x180002277  jz      short loc_1800022A6
0x180002279  test    rsi, rsi
0x18000227c  jz      short loc_18000228D
0x18000227e  mov     rax, [rsi]
0x180002281  mov     rcx, rsi
0x180002284  mov     rax, [rax+8]
0x180002288  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000228d  mov     rcx, [rdi+18h]
0x180002291  test    rcx, rcx
0x180002294  jz      short loc_1800022A2
0x180002296  mov     rax, [rcx]
0x180002299  mov     rax, [rax+10h]
0x18000229d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022a2  mov     [rdi+18h], rsi
0x1800022a6  xor     edi, edi
0x1800022a8  jmp     short loc_1800022CA
0x1800022aa  mov     r8, rbx; p
0x1800022ad  mov     edx, 7FFFFFFFh; i
0x1800022b2  call    cs:__imp_DPA_InsertPtr
0x1800022b8  xor     edi, edi
0x1800022ba  lea     rbp, WPP_GLOBAL_Control
0x1800022c1  cmp     eax, 0FFFFFFFFh
0x1800022c4  cmovz   edi, r13d
0x1800022c8  xor     ebx, ebx
0x1800022ca  lea     rcx, g_csDll; lpCriticalSection
0x1800022d1  call    cs:__imp_LeaveCriticalSection
0x1800022d7  test    rbx, rbx
0x1800022da  jz      short loc_1800022EF
0x1800022dc  mov     rax, [rbx]
0x1800022df  mov     edx, 1
0x1800022e4  mov     rcx, rbx
0x1800022e7  mov     rax, [rax]
0x1800022ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022ef  test    edi, edi
0x1800022f1  jns     short loc_180002326
0x1800022f3  jmp     short loc_1800022FC
0x1800022f5  lea     rbp, WPP_GLOBAL_Control
0x1800022fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180002303  cmp     rcx, rbp
0x180002306  jz      short loc_180002326
0x180002308  test    byte ptr [rcx+1Ch], 4
0x18000230c  jz      short loc_180002326
0x18000230e  mov     rcx, [rcx+10h]
0x180002312  lea     r8, WPP_0f628f1b17743b1a1d642676ad7906b4_Traceguids
0x180002319  mov     edx, 0Fh
0x18000231e  mov     r9d, edi
0x180002321  call    WPP_SF_d
0x180002326  mov     eax, edi
0x180002328  add     rsp, 20h
0x18000232c  pop     r15
0x18000232e  pop     r14
0x180002330  pop     r13
0x180002332  pop     rdi
0x180002333  pop     rsi
0x180002334  pop     rbp
0x180002335  pop     rbx
0x180002336  retn
```
