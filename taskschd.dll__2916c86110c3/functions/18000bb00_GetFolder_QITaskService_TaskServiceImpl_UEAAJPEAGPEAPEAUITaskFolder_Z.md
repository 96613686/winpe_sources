# ?GetFolder@?QITaskService@@TaskServiceImpl@@UEAAJPEAGPEAPEAUITaskFolder@@@Z

- ea: `0x18000bb00`
- end: `0x18000bfe4`
- name: `?GetFolder@?QITaskService@@TaskServiceImpl@@UEAAJPEAGPEAPEAUITaskFolder@@@Z`
- size: `1252`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x180007aa0`
- `0x180009a30`
- `0x18000aac0`
- `0x18000bb00`
- `0x18000c190`
- `0x18000c5c0`
- `0x18000c77c`
- `0x18000ca30`
- `0x18000d67c`
- `0x1800385a0`
- `0x18003b51c`
- `0x180054010`

## import_xrefs

- `msvcrt!free` at `0x18000bfcc`
- `msvcrt!free` at `0x18000bfcc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bd24`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bd4e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bf34`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bd24`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bd4e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bf34`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bb46`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bb46`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bc40`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bdbe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bdfd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bc40`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bdbe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bdfd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bc32`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bdb0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bdef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bc32`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bdb0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bdef`

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
        v38 = &qword_180077320;
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
0x18000bb00  mov     rax, rsp
0x18000bb03  mov     [rax+8], rbx
0x18000bb07  mov     [rax+10h], rsi
0x18000bb0b  mov     [rax+18h], r8
0x18000bb0f  push    rdi
0x18000bb10  push    r12
0x18000bb12  push    r13
0x18000bb14  push    r14
0x18000bb16  push    r15
0x18000bb18  sub     rsp, 0B0h
0x18000bb1f  mov     rsi, r8
0x18000bb22  mov     r15, rdx
0x18000bb25  mov     rdi, rcx
0x18000bb28  test    r8, r8
0x18000bb2b  jz      loc_18000BF27
0x18000bb31  xor     r12d, r12d
0x18000bb34  mov     [rax+20h], r12d
0x18000bb38  lea     rbx, [rcx+108h]
0x18000bb3f  mov     [rax-30h], rbx
0x18000bb43  mov     rcx, rbx; lpCriticalSection
0x18000bb46  call    cs:__imp_EnterCriticalSection
0x18000bb4c  nop
0x18000bb4d  lea     r13, [rdi+130h]
0x18000bb54  cmp     [r13+0], r12d
0x18000bb58  jz      loc_18000BF31
0x18000bb5e  test    r15, r15
0x18000bb61  jz      short loc_18000BBCB
0x18000bb63  cmp     [r15], r12w
0x18000bb67  jz      short loc_18000BBCB
0x18000bb69  mov     [rsp+0D8h+var_98], r12
0x18000bb6e  mov     dword ptr [rsp+0D8h+var_78], r12d
0x18000bb73  mov     rax, [r13+8]
0x18000bb77  mov     [rsp+0D8h+var_70], rax
0x18000bb7c  test    rax, rax
0x18000bb7f  jz      loc_18000BD7A
0x18000bb85  mov     ecx, 30h ; '0'; unsigned __int64
0x18000bb8a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bb8f  mov     [rsp+0D8h+var_80], rax
0x18000bb94  test    rax, rax
0x18000bb97  jz      loc_18000BEF7
0x18000bb9d  mov     rcx, rax; this
0x18000bba0  call    ??0RpcFolderSnapshot@@AEAA@XZ; RpcFolderSnapshot::RpcFolderSnapshot(void)
0x18000bba5  mov     r14, rax
0x18000bba8  test    r14, r14
0x18000bbab  jnz     loc_18000BF44
0x18000bbb1  mov     [rsp+0D8h+var_98], r14
0x18000bbb6  test    r14, r14
0x18000bbb9  jz      loc_18000BF4E
0x18000bbbf  mov     esi, 1
0x18000bbc4  mov     ecx, 400h
0x18000bbc9  jmp     short loc_18000BBE3
0x18000bbcb  lea     r15, asc_180077260; "\\"
0x18000bbd2  jmp     short loc_18000BB69
0x18000bbe0  xor     r12d, r12d
0x18000bbe3  mov     [rsp+0D8h+lpMem], r12
0x18000bbe8  mov     [rsp+0D8h+var_88], r12d
0x18000bbed  mov     eax, esi
0x18000bbef  cmp     esi, ecx
0x18000bbf1  cmova   eax, ecx
0x18000bbf4  lea     rcx, [rsp+0D8h+lpMem]
0x18000bbf9  mov     [rsp+0D8h+var_A8], rcx
0x18000bbfe  mov     [rsp+0D8h+var_B0], eax
0x18000bc02  lea     rax, [rsp+0D8h+var_78]
0x18000bc07  mov     [rsp+0D8h+var_B8], rax
0x18000bc0c  mov     r9d, 1
0x18000bc12  mov     r8, r15
0x18000bc15  mov     edx, r9d
0x18000bc18  mov     rcx, [rsp+0D8h+var_70]
0x18000bc1d  call    ?Enumerate@RpcSession@@AEBAJW4RpcEnumType@@TRpcEnumParam@@KPEAKKAEAV?$RpcArray@PEBG@@@Z; RpcSession::Enumerate(RpcEnumType,RpcEnumParam,ulong,ulong *,ulong,RpcArray<ushort const *> &)
0x18000bc22  mov     r12d, eax
0x18000bc25  test    eax, eax
0x18000bc27  jns     loc_18000BDA3
0x18000bc2d  mov     rsi, [rsp+0D8h+lpMem]
0x18000bc32  call    cs:__imp_GetProcessHeap
0x18000bc38  mov     r8, rsi; lpMem
0x18000bc3b  xor     edx, edx; dwFlags
0x18000bc3d  mov     rcx, rax; hHeap
0x18000bc40  call    cs:__imp_HeapFree
0x18000bc46  mov     rsi, [rsp+0D8h+arg_10]
0x18000bc4e  test    r14, r14
0x18000bc51  jz      short loc_18000BC67
0x18000bc53  mov     eax, 0FFFFFFFFh
0x18000bc58  lock xadd [r14+8], eax
0x18000bc5e  cmp     eax, 1
0x18000bc61  jz      loc_18000BD59
0x18000bc67  mov     [rsp+0D8h+arg_18], r12d
0x18000bc6f  test    r12d, r12d
0x18000bc72  js      loc_18000BD4B
0x18000bc78  mov     [rsp+0D8h+var_78], rdi
0x18000bc7d  test    rdi, rdi
0x18000bc80  jz      short loc_18000BC92
0x18000bc82  mov     rax, [rdi]
0x18000bc85  mov     rcx, rdi
0x18000bc88  mov     rax, [rax+8]
0x18000bc8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc91  nop
0x18000bc92  mov     [rsp+0D8h+arg_10], 0
0x18000bc9e  mov     [rsp+0D8h+var_98], 0
0x18000bca7  lea     rcx, [rsp+0D8h+var_98]
0x18000bcac  call    ?CreateInstance@?$CComObject@VTaskFolderImpl@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<TaskFolderImpl>::CreateInstance(ATL::CComObject<TaskFolderImpl> * *)
0x18000bcb1  mov     r14d, eax
0x18000bcb4  test    eax, eax
0x18000bcb6  js      loc_18000BF08
0x18000bcbc  mov     r12, [rsp+0D8h+var_98]
0x18000bcc1  mov     rax, [r12]
0x18000bcc5  lea     r8, [rsp+0D8h+arg_10]
0x18000bccd  lea     rdx, _GUID_8cfac062_a080_4c15_9a88_aa7c2af80dfc
0x18000bcd4  mov     rcx, r12
0x18000bcd7  mov     rax, [rax]
0x18000bcda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcdf  mov     r14d, eax
0x18000bce2  test    eax, eax
0x18000bce4  jns     loc_18000BE34
0x18000bcea  mov     rcx, [rsp+0D8h+arg_10]
0x18000bcf2  test    rcx, rcx
0x18000bcf5  jz      short loc_18000BD04
0x18000bcf7  mov     rax, [rcx]
0x18000bcfa  mov     rax, [rax+10h]
0x18000bcfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd03  nop
0x18000bd04  mov     [rsp+0D8h+arg_18], r14d
0x18000bd0c  test    rdi, rdi
0x18000bd0f  jz      short loc_18000BD21
0x18000bd11  mov     rax, [rdi]
0x18000bd14  mov     rcx, rdi
0x18000bd17  mov     rax, [rax+10h]
0x18000bd1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd20  nop
0x18000bd21  mov     rcx, rbx; lpCriticalSection
0x18000bd24  call    cs:__imp_LeaveCriticalSection
0x18000bd2a  nop
0x18000bd2b  mov     eax, r14d
0x18000bd2e  lea     r11, [rsp+0D8h+var_28]
0x18000bd36  mov     rbx, [r11+30h]
0x18000bd3a  mov     rsi, [r11+38h]
0x18000bd3e  mov     rsp, r11
0x18000bd41  pop     r15
0x18000bd43  pop     r14
0x18000bd45  pop     r13
0x18000bd47  pop     r12
0x18000bd49  pop     rdi
0x18000bd4a  retn
0x18000bd4b  mov     rcx, rbx; lpCriticalSection
0x18000bd4e  call    cs:__imp_LeaveCriticalSection
0x18000bd54  mov     eax, r12d
0x18000bd57  jmp     short loc_18000BD2E
0x18000bd59  test    r14, r14
0x18000bd5c  jz      loc_18000BC67
0x18000bd62  mov     rax, [r14]
0x18000bd65  mov     edx, 1
0x18000bd6a  mov     rcx, r14
0x18000bd6d  mov     rax, [rax]
0x18000bd70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd75  jmp     loc_18000BC67
0x18000bd7a  lea     rax, [rsp+0D8h+var_98]
0x18000bd7f  mov     [rsp+0D8h+var_A8], rax
0x18000bd84  mov     [rsp+0D8h+var_B8], r15
0x18000bd89  lea     r8, [rsp+0D8h+var_78]
0x18000bd8e  mov     rcx, r13
0x18000bd91  call    ?GetFolderSnapshotLegacy@UniSession@@IEBAJW4RpcEnumType@@PEAKKPEBGKAEAV?$AutoRef@VRpcFolderSnapshot@@@wmi@@@Z; UniSession::GetFolderSnapshotLegacy(RpcEnumType,ulong *,ulong,ushort const *,ulong,wmi::AutoRef<RpcFolderSnapshot> &)
0x18000bd96  mov     r12d, eax
0x18000bd99  mov     r14, [rsp+0D8h+var_98]
0x18000bd9e  jmp     loc_18000BC4E
0x18000bda3  mov     eax, [rsp+0D8h+var_88]
0x18000bda7  test    eax, eax
0x18000bda9  jnz     short loc_18000BDCC
0x18000bdab  mov     rsi, [rsp+0D8h+lpMem]
0x18000bdb0  call    cs:__imp_GetProcessHeap
0x18000bdb6  mov     r8, rsi; lpMem
0x18000bdb9  xor     edx, edx; dwFlags
0x18000bdbb  mov     rcx, rax; hHeap
0x18000bdbe  call    cs:__imp_HeapFree
0x18000bdc4  xor     r12d, r12d
0x18000bdc7  jmp     loc_18000BC46
0x18000bdcc  cmp     eax, esi
0x18000bdce  jb      loc_18000BFA7
0x18000bdd4  mov     dword ptr [rsp+0D8h+var_80], 0
0x18000bddc  lea     rdx, [rsp+0D8h+lpMem]
0x18000bde1  mov     rcx, r14
0x18000bde4  call    ?AddBatch@RpcFolderSnapshot@@AEAAXAEAV?$RpcArray@PEBG@@@Z; RpcFolderSnapshot::AddBatch(RpcArray<ushort const *> &)
0x18000bde9  nop
0x18000bdea  mov     rsi, [rsp+0D8h+lpMem]
0x18000bdef  call    cs:__imp_GetProcessHeap
0x18000bdf5  mov     r8, rsi; lpMem
0x18000bdf8  xor     edx, edx; dwFlags
0x18000bdfa  mov     rcx, rax; hHeap
0x18000bdfd  call    cs:__imp_HeapFree
0x18000be03  mov     [rsp+0D8h+lpMem], 0
0x18000be0c  mov     [rsp+0D8h+var_88], 0
0x18000be14  cmp     r12d, 1
0x18000be18  jnz     loc_18000BC46
0x18000be1e  mov     esi, dword ptr [rsp+0D8h+var_80]
0x18000be22  test    esi, esi
0x18000be24  mov     ecx, 400h
0x18000be29  jz      loc_18000BC46
0x18000be2f  jmp     loc_18000BBE0
0x18000be34  mov     eax, [r13+0]
0x18000be38  mov     [r12+50h], eax
0x18000be3d  mov     eax, [r13+4]
0x18000be41  mov     [r12+54h], eax
0x18000be46  lea     rcx, [r12+58h]
0x18000be4b  mov     rax, [r13+8]
0x18000be4f  mov     [rsp+0D8h+var_70], rax
0x18000be54  test    rax, rax
0x18000be57  jnz     loc_18000BEFF
0x18000be5d  call    ?Release@?$AutoRef@VRpcFolderSnapshot@@@wmi@@QEAAXXZ; wmi::AutoRef<RpcFolderSnapshot>::Release(void)
0x18000be62  mov     rax, [rsp+0D8h+var_70]
0x18000be67  mov     [r12+58h], rax
0x18000be6c  lea     rax, [r12+60h]
0x18000be71  mov     r13, [r13+10h]
0x18000be75  cmp     [rax], r13
0x18000be78  jnz     short loc_18000BECB
0x18000be7a  test    rdi, rdi
0x18000be7d  jz      short loc_18000BE8E
0x18000be7f  mov     rax, [rdi]
0x18000be82  mov     rcx, rdi
0x18000be85  mov     rax, [rax+8]
0x18000be89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be8e  lea     rcx, [r12+68h]
0x18000be93  call    ??1?$AutoRef@VRunningTaskCollectionImpl@@@wmi@@QEAA@XZ; wmi::AutoRef<RunningTaskCollectionImpl>::~AutoRef<RunningTaskCollectionImpl>(void)
0x18000be98  mov     [r12+68h], rdi
0x18000be9d  mov     rcx, r15; this
0x18000bea0  call    ?PathCopy@tsched@@YAPEAGPEBG@Z; tsched::PathCopy(ushort const *)
0x18000bea5  mov     r15, rax
0x18000bea8  mov     rcx, [r12+70h]; Block
0x18000bead  test    rcx, rcx
0x18000beb0  jnz     loc_18000BFCC
0x18000beb6  mov     [r12+70h], r15
0x18000bebb  mov     rax, [rsp+0D8h+arg_10]
0x18000bec3  mov     [rsi], rax
0x18000bec6  jmp     loc_18000BD04
0x18000becb  test    rax, rax
0x18000bece  jz      short loc_18000BE7A
0x18000bed0  test    r13, r13
0x18000bed3  jnz     loc_18000BFB2
0x18000bed9  mov     rcx, [rax]
0x18000bedc  test    rcx, rcx
0x18000bedf  jz      short loc_18000BEF2
0x18000bee1  mov     rax, [rcx]
0x18000bee4  mov     rax, [rax+10h]
0x18000bee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000beed  lea     rax, [r12+60h]
0x18000bef2  mov     [rax], r13
0x18000bef5  jmp     short loc_18000BE7A
0x18000bef7  mov     r14, r12
0x18000befa  jmp     loc_18000BBA8
0x18000beff  lock inc dword ptr [rax+8]
0x18000bf03  jmp     loc_18000BE5D
0x18000bf08  mov     rcx, [rsp+0D8h+arg_10]
0x18000bf10  test    rcx, rcx
0x18000bf13  jz      short loc_18000BF22
0x18000bf15  mov     rax, [rcx]
0x18000bf18  mov     rax, [rax+10h]
0x18000bf1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf21  nop
0x18000bf22  jmp     loc_18000BD04
0x18000bf27  mov     eax, 80004003h
0x18000bf2c  jmp     loc_18000BD2E
0x18000bf31  mov     rcx, rbx; lpCriticalSection
0x18000bf34  call    cs:__imp_LeaveCriticalSection
0x18000bf3a  mov     eax, 800704E3h
0x18000bf3f  jmp     loc_18000BD2E
0x18000bf44  lock inc dword ptr [r14+8]
0x18000bf49  jmp     loc_18000BBB1
0x18000bf4e  mov     [rsp+0D8h+var_60], 0
0x18000bf53  lea     rax, qword_180077320
0x18000bf5a  mov     [rsp+0D8h+var_58], rax
0x18000bf62  mov     [rsp+0D8h+var_50], r12
0x18000bf6a  mov     [rsp+0D8h+var_48], r12
0x18000bf72  mov     [rsp+0D8h+var_40], 0Eh
0x18000bf7d  mov     [rsp+0D8h+var_3C], 0FFFFFFFFFFFFFFFFh
0x18000bf89  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000bf90  mov     [rsp+0D8h+pExceptionObject], rax
0x18000bf95  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18000bf9c  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x18000bfa1  call    _CxxThrowException_0
0x18000bfa7  sub     esi, eax
0x18000bfa9  mov     dword ptr [rsp+0D8h+var_80], esi
0x18000bfad  jmp     loc_18000BDDC
0x18000bfb2  mov     rax, [r13+0]
0x18000bfb6  mov     rcx, r13
0x18000bfb9  mov     rax, [rax+8]
0x18000bfbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfc2  lea     rax, [r12+60h]
0x18000bfc7  jmp     loc_18000BED9
0x18000bfcc  call    cs:__imp_free
0x18000bfd2  jmp     loc_18000BEB6
0x18000bfd7  mov     r14d, [rsp+0D8h+arg_18]
0x18000bfdf  jmp     loc_18000BD2B
```
