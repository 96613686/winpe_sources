# ?GetFolder@?QITaskService@@TaskServiceImpl@@UEAAJPEAGPEAPEAUITaskFolder@@@Z

- ea: `0x18000c020`
- end: `0x18000c541`
- name: `?GetFolder@?QITaskService@@TaskServiceImpl@@UEAAJPEAGPEAPEAUITaskFolder@@@Z`
- size: `1313`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x180007e90`
- `0x18000a100`
- `0x18000aea0`
- `0x18000c020`
- `0x18000c700`
- `0x18000cb60`
- `0x18000cd44`
- `0x18000cff8`
- `0x18000dd3c`
- `0x18003b784`
- `0x18003e88c`
- `0x180058010`

## import_xrefs

- `msvcrt!free` at `0x18000c523`
- `msvcrt!free` at `0x18000c523`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c250`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c281`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c485`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c250`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c281`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c485`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c066`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c066`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c166`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c2fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c348`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c166`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c2fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c348`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c152`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c2e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c334`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c152`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c2e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c334`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall _GetFolder__QITaskService__TaskServiceImpl__UEAAJPEAGPEAPEAUITaskFolder___Z(
        __int64 a1,
        unsigned __int16 *a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  struct _RTL_CRITICAL_SECTION *v6; // rbx
  __int64 v7; // rdx
  __int64 v8; // r9
  RpcFolderSnapshot *v9; // rax
  RpcFolderSnapshot *v10; // r14
  unsigned int v11; // esi
  int v12; // eax
  int FolderSnapshotLegacy; // r12d
  void *v14; // rsi
  HANDLE ProcessHeap; // rax
  int v16; // r14d
  RpcFolderSnapshot *v17; // r12
  void *v19; // rsi
  HANDLE v20; // rax
  void *v21; // rsi
  HANDLE v22; // rax
  __int64 v23; // rax
  _QWORD *v24; // rax
  __int64 v25; // r13
  const unsigned __int16 *v26; // rdx
  unsigned __int16 *v27; // r15
  void *v28; // rcx
  int v29; // [rsp+28h] [rbp-B0h]
  RpcFolderSnapshot *v30; // [rsp+40h] [rbp-98h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-90h] BYREF
  unsigned int v32; // [rsp+50h] [rbp-88h]
  RpcFolderSnapshot *v33; // [rsp+58h] [rbp-80h]
  __int64 v34; // [rsp+60h] [rbp-78h] BYREF
  __int64 v35; // [rsp+68h] [rbp-70h]
  void **pExceptionObject; // [rsp+70h] [rbp-68h] BYREF
  char v37; // [rsp+78h] [rbp-60h]
  __int64 *v38; // [rsp+80h] [rbp-58h]
  __int64 v39; // [rsp+88h] [rbp-50h]
  __int64 v40; // [rsp+90h] [rbp-48h]
  int v41; // [rsp+98h] [rbp-40h]
  __int64 v42; // [rsp+9Ch] [rbp-3Ch]
  __int64 v43; // [rsp+A8h] [rbp-30h]
  _QWORD *v44; // [rsp+F0h] [rbp+18h] BYREF
  int v45; // [rsp+F8h] [rbp+20h]

  v44 = a3;
  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  v45 = 0;
  v6 = (struct _RTL_CRITICAL_SECTION *)(a1 + 264);
  v43 = a1 + 264;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 264));
  if ( *(_DWORD *)(a1 + 304) )
  {
    if ( !a2 || !*a2 )
      a2 = L"\\";
    v30 = 0;
    LODWORD(v34) = 0;
    v35 = *(_QWORD *)(a1 + 312);
    if ( v35 )
    {
      v9 = (RpcFolderSnapshot *)operator new(0x30u);
      v33 = v9;
      if ( v9 )
        v10 = RpcFolderSnapshot::RpcFolderSnapshot(v9);
      else
        v10 = 0;
      if ( v10 )
        _InterlockedIncrement((volatile signed __int32 *)v10 + 2);
      v30 = v10;
      if ( !v10 )
      {
        v37 = 0;
        v38 = &qword_18007B2F0;
        v39 = 0;
        v40 = 0;
        v41 = 14;
        v42 = -1;
        pExceptionObject = &wmi::GenericException::`vftable';
        throw (wmi::OutOfMemoryException *)&pExceptionObject;
      }
      v11 = 1;
      while ( 1 )
      {
        lpMem = 0;
        v32 = 0;
        v12 = v11;
        if ( v11 > 0x400 )
          v12 = 1024;
        FolderSnapshotLegacy = RpcSession::Enumerate(v35, 1, (_DWORD)a2, 1, (__int64)&v34, v12, (__int64)&lpMem);
        if ( FolderSnapshotLegacy < 0 )
        {
          v14 = lpMem;
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v14);
          goto LABEL_17;
        }
        if ( !v32 )
          break;
        if ( v32 < v11 )
          LODWORD(v33) = v11 - v32;
        else
          LODWORD(v33) = 0;
        RpcFolderSnapshot::AddBatch(v10, &lpMem);
        v21 = lpMem;
        v22 = GetProcessHeap();
        HeapFree(v22, 0, v21);
        lpMem = 0;
        v32 = 0;
        if ( FolderSnapshotLegacy == 1 )
        {
          v11 = (unsigned int)v33;
          if ( (_DWORD)v33 )
            continue;
        }
        goto LABEL_17;
      }
      v19 = lpMem;
      v20 = GetProcessHeap();
      HeapFree(v20, 0, v19);
      FolderSnapshotLegacy = 0;
LABEL_17:
      v3 = v44;
    }
    else
    {
      FolderSnapshotLegacy = UniSession::GetFolderSnapshotLegacy(a1 + 304, v7, &v34, v8, a2, v29, (__int64)&v30);
      v10 = v30;
    }
    if ( v10 && _InterlockedExchangeAdd((volatile signed __int32 *)v10 + 2, 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(RpcFolderSnapshot *, __int64))v10)(v10, 1);
    v45 = FolderSnapshotLegacy;
    if ( FolderSnapshotLegacy < 0 )
    {
      LeaveCriticalSection(v6);
      return (unsigned int)FolderSnapshotLegacy;
    }
    else
    {
      v34 = a1;
      if ( a1 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
      v44 = 0;
      v30 = 0;
      v16 = ATL::CComObject<TaskFolderImpl>::CreateInstance(&v30);
      if ( v16 < 0 )
      {
        if ( v44 )
          (*(void (__fastcall **)(_QWORD *))(*v44 + 16LL))(v44);
      }
      else
      {
        v17 = v30;
        v16 = (**(__int64 (__fastcall ***)(RpcFolderSnapshot *, GUID *, _QWORD **))v30)(
                v30,
                &GUID_8cfac062_a080_4c15_9a88_aa7c2af80dfc,
                &v44);
        if ( v16 >= 0 )
        {
          *((_DWORD *)v17 + 20) = *(_DWORD *)(a1 + 304);
          *((_DWORD *)v17 + 21) = *(_DWORD *)(a1 + 308);
          v23 = *(_QWORD *)(a1 + 312);
          v35 = v23;
          if ( v23 )
            _InterlockedIncrement((volatile signed __int32 *)(v23 + 8));
          wmi::AutoRef<RpcFolderSnapshot>::Release((char *)v17 + 88);
          *((_QWORD *)v17 + 11) = v35;
          v24 = (_QWORD *)((char *)v17 + 96);
          v25 = *(_QWORD *)(a1 + 320);
          if ( *((_QWORD *)v17 + 12) != v25 && v17 != (RpcFolderSnapshot *)-96LL )
          {
            if ( v25 )
            {
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v25 + 8LL))(*(_QWORD *)(a1 + 320));
              v24 = (_QWORD *)((char *)v17 + 96);
            }
            if ( *v24 )
            {
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v24 + 16LL))(*v24);
              v24 = (_QWORD *)((char *)v17 + 96);
            }
            *v24 = v25;
          }
          if ( a1 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
          wmi::AutoRef<RunningTaskCollectionImpl>::~AutoRef<RunningTaskCollectionImpl>((char *)v17 + 104);
          *((_QWORD *)v17 + 13) = a1;
          v27 = tsched::PathCopy((tsched *)a2, v26);
          v28 = (void *)*((_QWORD *)v17 + 14);
          if ( v28 )
            free(v28);
          *((_QWORD *)v17 + 14) = v27;
          *v3 = v44;
        }
        else if ( v44 )
        {
          (*(void (__fastcall **)(_QWORD *))(*v44 + 16LL))(v44);
        }
      }
      v45 = v16;
      if ( a1 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
      LeaveCriticalSection(v6);
      return (unsigned int)v16;
    }
  }
  else
  {
    LeaveCriticalSection(v6);
    return 2147943651LL;
  }
}

```

## disassembly

```asm
0x18000c020  mov     rax, rsp
0x18000c023  mov     [rax+8], rbx
0x18000c027  mov     [rax+10h], rsi
0x18000c02b  mov     [rax+18h], r8
0x18000c02f  push    rdi
0x18000c030  push    r12
0x18000c032  push    r13
0x18000c034  push    r14
0x18000c036  push    r15
0x18000c038  sub     rsp, 0B0h
0x18000c03f  mov     rsi, r8
0x18000c042  mov     r15, rdx
0x18000c045  mov     rdi, rcx
0x18000c048  test    r8, r8
0x18000c04b  jz      loc_18000C478
0x18000c051  xor     r12d, r12d
0x18000c054  mov     [rax+20h], r12d
0x18000c058  lea     rbx, [rcx+108h]
0x18000c05f  mov     [rax-30h], rbx
0x18000c063  mov     rcx, rbx; lpCriticalSection
0x18000c066  call    cs:__imp_EnterCriticalSection
0x18000c06d  nop     dword ptr [rax+rax+00h]
0x18000c072  nop
0x18000c073  lea     r13, [rdi+130h]
0x18000c07a  cmp     [r13+0], r12d
0x18000c07e  jz      loc_18000C482
0x18000c084  test    r15, r15
0x18000c087  jz      short loc_18000C0F1
0x18000c089  cmp     [r15], r12w
0x18000c08d  jz      short loc_18000C0F1
0x18000c08f  mov     [rsp+0D8h+var_98], r12
0x18000c094  mov     dword ptr [rsp+0D8h+var_78], r12d
0x18000c099  mov     rax, [r13+8]
0x18000c09d  mov     [rsp+0D8h+var_70], rax
0x18000c0a2  test    rax, rax
0x18000c0a5  jz      loc_18000C2B3
0x18000c0ab  mov     ecx, 30h ; '0'; unsigned __int64
0x18000c0b0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c0b5  mov     [rsp+0D8h+var_80], rax
0x18000c0ba  test    rax, rax
0x18000c0bd  jz      loc_18000C448
0x18000c0c3  mov     rcx, rax; this
0x18000c0c6  call    ??0RpcFolderSnapshot@@AEAA@XZ; RpcFolderSnapshot::RpcFolderSnapshot(void)
0x18000c0cb  mov     r14, rax
0x18000c0ce  test    r14, r14
0x18000c0d1  jnz     loc_18000C49B
0x18000c0d7  mov     [rsp+0D8h+var_98], r14
0x18000c0dc  test    r14, r14
0x18000c0df  jz      loc_18000C4A5
0x18000c0e5  mov     esi, 1
0x18000c0ea  mov     ecx, 400h
0x18000c0ef  jmp     short loc_18000C103
0x18000c0f1  lea     r15, asc_18007B230; "\\"
0x18000c0f8  jmp     short loc_18000C08F
0x18000c100  xor     r12d, r12d
0x18000c103  mov     [rsp+0D8h+lpMem], r12
0x18000c108  mov     [rsp+0D8h+var_88], r12d
0x18000c10d  mov     eax, esi
0x18000c10f  cmp     esi, ecx
0x18000c111  cmova   eax, ecx
0x18000c114  lea     rcx, [rsp+0D8h+lpMem]
0x18000c119  mov     [rsp+0D8h+var_A8], rcx
0x18000c11e  mov     [rsp+0D8h+var_B0], eax
0x18000c122  lea     rax, [rsp+0D8h+var_78]
0x18000c127  mov     [rsp+0D8h+var_B8], rax
0x18000c12c  mov     r9d, 1
0x18000c132  mov     r8, r15
0x18000c135  mov     edx, r9d
0x18000c138  mov     rcx, [rsp+0D8h+var_70]
0x18000c13d  call    ?Enumerate@RpcSession@@AEBAJW4RpcEnumType@@TRpcEnumParam@@KPEAKKAEAV?$RpcArray@PEBG@@@Z; RpcSession::Enumerate(RpcEnumType,RpcEnumParam,ulong,ulong *,ulong,RpcArray<ushort const *> &)
0x18000c142  mov     r12d, eax
0x18000c145  test    eax, eax
0x18000c147  jns     loc_18000C2DC
0x18000c14d  mov     rsi, [rsp+0D8h+lpMem]
0x18000c152  call    cs:__imp_GetProcessHeap
0x18000c159  nop     dword ptr [rax+rax+00h]
0x18000c15e  mov     r8, rsi; lpMem
0x18000c161  xor     edx, edx; dwFlags
0x18000c163  mov     rcx, rax; hHeap
0x18000c166  call    cs:__imp_HeapFree
0x18000c16d  nop     dword ptr [rax+rax+00h]
0x18000c172  mov     rsi, [rsp+0D8h+arg_10]
0x18000c17a  test    r14, r14
0x18000c17d  jz      short loc_18000C193
0x18000c17f  mov     eax, 0FFFFFFFFh
0x18000c184  lock xadd [r14+8], eax
0x18000c18a  cmp     eax, 1
0x18000c18d  jz      loc_18000C292
0x18000c193  mov     [rsp+0D8h+arg_18], r12d
0x18000c19b  test    r12d, r12d
0x18000c19e  js      loc_18000C27E
0x18000c1a4  mov     [rsp+0D8h+var_78], rdi
0x18000c1a9  test    rdi, rdi
0x18000c1ac  jz      short loc_18000C1BE
0x18000c1ae  mov     rax, [rdi]
0x18000c1b1  mov     rcx, rdi
0x18000c1b4  mov     rax, [rax+8]
0x18000c1b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1bd  nop
0x18000c1be  mov     [rsp+0D8h+arg_10], 0
0x18000c1ca  mov     [rsp+0D8h+var_98], 0
0x18000c1d3  lea     rcx, [rsp+0D8h+var_98]
0x18000c1d8  call    ?CreateInstance@?$CComObject@VTaskFolderImpl@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<TaskFolderImpl>::CreateInstance(ATL::CComObject<TaskFolderImpl> * *)
0x18000c1dd  mov     r14d, eax
0x18000c1e0  test    eax, eax
0x18000c1e2  js      loc_18000C459
0x18000c1e8  mov     r12, [rsp+0D8h+var_98]
0x18000c1ed  mov     rax, [r12]
0x18000c1f1  lea     r8, [rsp+0D8h+arg_10]
0x18000c1f9  lea     rdx, _GUID_8cfac062_a080_4c15_9a88_aa7c2af80dfc
0x18000c200  mov     rcx, r12
0x18000c203  mov     rax, [rax]
0x18000c206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c20b  mov     r14d, eax
0x18000c20e  test    eax, eax
0x18000c210  jns     loc_18000C385
0x18000c216  mov     rcx, [rsp+0D8h+arg_10]
0x18000c21e  test    rcx, rcx
0x18000c221  jz      short loc_18000C230
0x18000c223  mov     rax, [rcx]
0x18000c226  mov     rax, [rax+10h]
0x18000c22a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c22f  nop
0x18000c230  mov     [rsp+0D8h+arg_18], r14d
0x18000c238  test    rdi, rdi
0x18000c23b  jz      short loc_18000C24D
0x18000c23d  mov     rax, [rdi]
0x18000c240  mov     rcx, rdi
0x18000c243  mov     rax, [rax+10h]
0x18000c247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c24c  nop
0x18000c24d  mov     rcx, rbx; lpCriticalSection
0x18000c250  call    cs:__imp_LeaveCriticalSection
0x18000c257  nop     dword ptr [rax+rax+00h]
0x18000c25c  nop
0x18000c25d  mov     eax, r14d
0x18000c260  lea     r11, [rsp+0D8h+var_28]
0x18000c268  mov     rbx, [r11+30h]
0x18000c26c  mov     rsi, [r11+38h]
0x18000c270  mov     rsp, r11
0x18000c273  pop     r15
0x18000c275  pop     r14
0x18000c277  pop     r13
0x18000c279  pop     r12
0x18000c27b  pop     rdi
0x18000c27c  retn
0x18000c27e  mov     rcx, rbx; lpCriticalSection
0x18000c281  call    cs:__imp_LeaveCriticalSection
0x18000c288  nop     dword ptr [rax+rax+00h]
0x18000c28d  mov     eax, r12d
0x18000c290  jmp     short loc_18000C260
0x18000c292  test    r14, r14
0x18000c295  jz      loc_18000C193
0x18000c29b  mov     rax, [r14]
0x18000c29e  mov     edx, 1
0x18000c2a3  mov     rcx, r14
0x18000c2a6  mov     rax, [rax]
0x18000c2a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2ae  jmp     loc_18000C193
0x18000c2b3  lea     rax, [rsp+0D8h+var_98]
0x18000c2b8  mov     [rsp+0D8h+var_A8], rax
0x18000c2bd  mov     [rsp+0D8h+var_B8], r15
0x18000c2c2  lea     r8, [rsp+0D8h+var_78]
0x18000c2c7  mov     rcx, r13
0x18000c2ca  call    ?GetFolderSnapshotLegacy@UniSession@@IEBAJW4RpcEnumType@@PEAKKPEBGKAEAV?$AutoRef@VRpcFolderSnapshot@@@wmi@@@Z; UniSession::GetFolderSnapshotLegacy(RpcEnumType,ulong *,ulong,ushort const *,ulong,wmi::AutoRef<RpcFolderSnapshot> &)
0x18000c2cf  mov     r12d, eax
0x18000c2d2  mov     r14, [rsp+0D8h+var_98]
0x18000c2d7  jmp     loc_18000C17A
0x18000c2dc  mov     eax, [rsp+0D8h+var_88]
0x18000c2e0  test    eax, eax
0x18000c2e2  jnz     short loc_18000C311
0x18000c2e4  mov     rsi, [rsp+0D8h+lpMem]
0x18000c2e9  call    cs:__imp_GetProcessHeap
0x18000c2f0  nop     dword ptr [rax+rax+00h]
0x18000c2f5  mov     r8, rsi; lpMem
0x18000c2f8  xor     edx, edx; dwFlags
0x18000c2fa  mov     rcx, rax; hHeap
0x18000c2fd  call    cs:__imp_HeapFree
0x18000c304  nop     dword ptr [rax+rax+00h]
0x18000c309  xor     r12d, r12d
0x18000c30c  jmp     loc_18000C172
0x18000c311  cmp     eax, esi
0x18000c313  jb      loc_18000C4FE
0x18000c319  mov     dword ptr [rsp+0D8h+var_80], 0
0x18000c321  lea     rdx, [rsp+0D8h+lpMem]
0x18000c326  mov     rcx, r14
0x18000c329  call    ?AddBatch@RpcFolderSnapshot@@AEAAXAEAV?$RpcArray@PEBG@@@Z; RpcFolderSnapshot::AddBatch(RpcArray<ushort const *> &)
0x18000c32e  nop
0x18000c32f  mov     rsi, [rsp+0D8h+lpMem]
0x18000c334  call    cs:__imp_GetProcessHeap
0x18000c33b  nop     dword ptr [rax+rax+00h]
0x18000c340  mov     r8, rsi; lpMem
0x18000c343  xor     edx, edx; dwFlags
0x18000c345  mov     rcx, rax; hHeap
0x18000c348  call    cs:__imp_HeapFree
0x18000c34f  nop     dword ptr [rax+rax+00h]
0x18000c354  mov     [rsp+0D8h+lpMem], 0
0x18000c35d  mov     [rsp+0D8h+var_88], 0
0x18000c365  cmp     r12d, 1
0x18000c369  jnz     loc_18000C172
0x18000c36f  mov     esi, dword ptr [rsp+0D8h+var_80]
0x18000c373  test    esi, esi
0x18000c375  mov     ecx, 400h
0x18000c37a  jz      loc_18000C172
0x18000c380  jmp     loc_18000C100
0x18000c385  mov     eax, [r13+0]
0x18000c389  mov     [r12+50h], eax
0x18000c38e  mov     eax, [r13+4]
0x18000c392  mov     [r12+54h], eax
0x18000c397  lea     rcx, [r12+58h]
0x18000c39c  mov     rax, [r13+8]
0x18000c3a0  mov     [rsp+0D8h+var_70], rax
0x18000c3a5  test    rax, rax
0x18000c3a8  jnz     loc_18000C450
0x18000c3ae  call    ?Release@?$AutoRef@VRpcFolderSnapshot@@@wmi@@QEAAXXZ; wmi::AutoRef<RpcFolderSnapshot>::Release(void)
0x18000c3b3  mov     rax, [rsp+0D8h+var_70]
0x18000c3b8  mov     [r12+58h], rax
0x18000c3bd  lea     rax, [r12+60h]
0x18000c3c2  mov     r13, [r13+10h]
0x18000c3c6  cmp     [rax], r13
0x18000c3c9  jnz     short loc_18000C41C
0x18000c3cb  test    rdi, rdi
0x18000c3ce  jz      short loc_18000C3DF
0x18000c3d0  mov     rax, [rdi]
0x18000c3d3  mov     rcx, rdi
0x18000c3d6  mov     rax, [rax+8]
0x18000c3da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3df  lea     rcx, [r12+68h]
0x18000c3e4  call    ??1?$AutoRef@VRunningTaskCollectionImpl@@@wmi@@QEAA@XZ; wmi::AutoRef<RunningTaskCollectionImpl>::~AutoRef<RunningTaskCollectionImpl>(void)
0x18000c3e9  mov     [r12+68h], rdi
0x18000c3ee  mov     rcx, r15; this
0x18000c3f1  call    ?PathCopy@tsched@@YAPEAGPEBG@Z; tsched::PathCopy(ushort const *)
0x18000c3f6  mov     r15, rax
0x18000c3f9  mov     rcx, [r12+70h]; Block
0x18000c3fe  test    rcx, rcx
0x18000c401  jnz     loc_18000C523
0x18000c407  mov     [r12+70h], r15
0x18000c40c  mov     rax, [rsp+0D8h+arg_10]
0x18000c414  mov     [rsi], rax
0x18000c417  jmp     loc_18000C230
0x18000c41c  test    rax, rax
0x18000c41f  jz      short loc_18000C3CB
0x18000c421  test    r13, r13
0x18000c424  jnz     loc_18000C509
0x18000c42a  mov     rcx, [rax]
0x18000c42d  test    rcx, rcx
0x18000c430  jz      short loc_18000C443
0x18000c432  mov     rax, [rcx]
0x18000c435  mov     rax, [rax+10h]
0x18000c439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c43e  lea     rax, [r12+60h]
0x18000c443  mov     [rax], r13
0x18000c446  jmp     short loc_18000C3CB
0x18000c448  mov     r14, r12
0x18000c44b  jmp     loc_18000C0CE
0x18000c450  lock inc dword ptr [rax+8]
0x18000c454  jmp     loc_18000C3AE
0x18000c459  mov     rcx, [rsp+0D8h+arg_10]
0x18000c461  test    rcx, rcx
0x18000c464  jz      short loc_18000C473
0x18000c466  mov     rax, [rcx]
0x18000c469  mov     rax, [rax+10h]
0x18000c46d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c472  nop
0x18000c473  jmp     loc_18000C230
0x18000c478  mov     eax, 80004003h
0x18000c47d  jmp     loc_18000C260
0x18000c482  mov     rcx, rbx; lpCriticalSection
0x18000c485  call    cs:__imp_LeaveCriticalSection
0x18000c48c  nop     dword ptr [rax+rax+00h]
0x18000c491  mov     eax, 800704E3h
0x18000c496  jmp     loc_18000C260
0x18000c49b  lock inc dword ptr [r14+8]
0x18000c4a0  jmp     loc_18000C0D7
0x18000c4a5  mov     [rsp+0D8h+var_60], 0
0x18000c4aa  lea     rax, qword_18007B2F0
0x18000c4b1  mov     [rsp+0D8h+var_58], rax
0x18000c4b9  mov     [rsp+0D8h+var_50], r12
0x18000c4c1  mov     [rsp+0D8h+var_48], r12
0x18000c4c9  mov     [rsp+0D8h+var_40], 0Eh
0x18000c4d4  mov     [rsp+0D8h+var_3C], 0FFFFFFFFFFFFFFFFh
0x18000c4e0  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000c4e7  mov     [rsp+0D8h+pExceptionObject], rax
0x18000c4ec  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18000c4f3  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x18000c4f8  call    _CxxThrowException_0
0x18000c4fe  sub     esi, eax
0x18000c500  mov     dword ptr [rsp+0D8h+var_80], esi
0x18000c504  jmp     loc_18000C321
0x18000c509  mov     rax, [r13+0]
0x18000c50d  mov     rcx, r13
0x18000c510  mov     rax, [rax+8]
0x18000c514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c519  lea     rax, [r12+60h]
0x18000c51e  jmp     loc_18000C42A
0x18000c523  call    cs:__imp_free
0x18000c52a  nop     dword ptr [rax+rax+00h]
0x18000c52f  jmp     loc_18000C407
0x18000c534  mov     r14d, [rsp+0D8h+arg_18]
0x18000c53c  jmp     loc_18000C25D
  ... truncated ...
```
