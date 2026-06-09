# SchedulerManager::CreateSystemThread(ulong)

- ea: `0x10042bcc0`
- end: `0x10042bea4`
- name: `?CreateSystemThread@SchedulerManager@@QEAA?AW4SOS_RESULT@@K@Z`
- size: `484`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x10042bbd0`
- `0x100477e80`

## callees

- `0x100403070`
- `0x100411fb0`
- `0x10042bcc0`
- `0x1004364b0`
- `0x1004366c0`
- `0x100436d30`
- `0x10048d250`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1004780fc`
- `KERNEL32!GetProcessHeap` at `0x1004780fc`
- `KERNEL32!HeapFree` at `0x10047810a`
- `KERNEL32!HeapFree` at `0x10047810a`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x10042bd82`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x10042bdbb`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x10042bd82`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x10042bdbb`
- `KERNEL32!UpdateProcThreadAttribute` at `0x10042be19`
- `KERNEL32!UpdateProcThreadAttribute` at `0x10042be19`
- `KERNEL32!CreateRemoteThreadEx` at `0x10042be4c`
- `KERNEL32!CreateRemoteThreadEx` at `0x10042be4c`
- `KERNEL32!DeleteProcThreadAttributeList` at `0x10042be61`
- `KERNEL32!DeleteProcThreadAttributeList` at `0x10042be61`
- `KERNEL32!CloseHandle` at `0x10042be73`
- `KERNEL32!CloseHandle` at `0x10042be73`
- `KERNEL32!GetCurrentProcess` at `0x10042be23`
- `KERNEL32!GetCurrentProcess` at `0x10042be23`
- `api-ms-win-crt-runtime-l1-1-0!_beginthreadex` at `0x10047813b`
- `api-ms-win-crt-runtime-l1-1-0!_beginthreadex` at `0x100478172`
- `api-ms-win-crt-runtime-l1-1-0!_beginthreadex` at `0x10047813b`
- `api-ms-win-crt-runtime-l1-1-0!_beginthreadex` at `0x100478172`

## pseudocode

```c
__int64 __fastcall SchedulerManager::CreateSystemThread(_QWORD *a1, unsigned int a2)
{
  unsigned int v4; // edi
  void *RemoteThread; // rbx
  unsigned int v6; // esi
  ULONG_PTR v7; // rcx
  unsigned __int64 v8; // rcx
  void *v9; // rsp
  void *v10; // rsp
  __int64 v11; // rdx
  unsigned __int64 v12; // rcx
  __int16 v13; // ax
  HANDLE CurrentProcess; // rax
  __int64 i; // rcx
  MiniSOSThreadResources *Object; // rbx
  HANDLE ProcessHeap; // rax
  signed __int32 v19; // [rsp+40h] [rbp+0h] BYREF
  signed __int32 v20; // [rsp+44h] [rbp+4h]
  __int16 Value; // [rsp+48h] [rbp+8h] BYREF
  char v22; // [rsp+4Ah] [rbp+Ah]
  char v23; // [rsp+4Bh] [rbp+Bh]
  int v24; // [rsp+4Ch] [rbp+Ch]
  int v25; // [rsp+50h] [rbp+10h]
  struct MiniSOSThreadResources *v26; // [rsp+58h] [rbp+18h] BYREF
  ULONG_PTR Size[2]; // [rsp+60h] [rbp+20h] BYREF

  v19 = dword_1007143C8;
  v24 = dword_1007143CC;
  v4 = 0;
  v20 = dword_1007143D0;
  v25 = dword_1007143D4;
  if ( dword_1007143C8 < dword_1007143CC )
  {
    v19 = dword_1007143C8;
    for ( i = (unsigned int)v20; dword_1007143C8 < v20; i = (unsigned int)v20 )
    {
      v26 = 0;
      v4 = MiniSOSThreadResourcesMgr::AllocObject(i, &v26);
      if ( v4 )
        break;
      MiniSOSThreadResourcesMgr::StoreObject(
        (MiniSOSThreadResourcesMgr *)&SOS_PublicGlobals::sm_MiniSOSThreadResourcesMgr,
        v26);
      v19 = dword_1007143C8;
    }
  }
  else if ( v19 > v25 )
  {
    v19 = dword_1007143C8;
    if ( dword_1007143C8 <= v20 )
      goto LABEL_4;
    while ( _InterlockedCompareExchange(&dword_1007143C8, v20, v19) != v19 )
    {
      _mm_pause();
      v19 = dword_1007143C8;
      if ( dword_1007143C8 <= v20 )
        goto LABEL_4;
    }
    v20 = v19 - v20;
    if ( v20 > 0 )
    {
      do
      {
        Object = (MiniSOSThreadResources *)TObjectPool<TMRUContainer<MiniSOSThreadResources,0>,ObjectPoolSLock>::RetrieveObject((SpinlockBase *)&SOS_PublicGlobals::sm_MiniSOSThreadResourcesMgr);
        MiniSOSThreadResources::~MiniSOSThreadResources(Object);
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, Object);
        --v20;
      }
      while ( v20 > 0 );
      goto LABEL_4;
    }
  }
  if ( v4 )
    return v4;
LABEL_4:
  RemoteThread = 0;
  if ( (byte_1007149B3 & 2) != 0 )
    v6 = 0;
  else
    v6 = SOS_PublicGlobals::sm_StackSize - 4096;
  if ( (SOS_PublicGlobals::sm_osStatus & 0x100) != 0 )
  {
    RemoteThread = (void *)_beginthreadex(0, v6, SchedulerManager::ThreadEntryPoint, a1, a2, 0);
  }
  else
  {
    InitializeProcThreadAttributeList(0, 1u, 0, Size);
    v7 = Size[0] + 15;
    if ( Size[0] + 15 < Size[0] )
      v7 = 0xFFFFFFFFFFFFFF0LL;
    v8 = v7 & 0xFFFFFFFFFFFFFFF0uLL;
    v9 = alloca(v8);
    v10 = alloca(v8);
    if ( !InitializeProcThreadAttributeList((LPPROC_THREAD_ATTRIBUTE_LIST)&v19, 1u, 0, Size) )
      return 2684354560LL;
    v11 = *(_QWORD *)(a1[35] + 224LL);
    _BitScanForward64(&v12, *(_QWORD *)(v11 + 8) & ~(*(_QWORD *)(v11 + 8) - 1LL));
    v13 = *(_WORD *)(v11 + 16);
    v22 = v12;
    Value = v13;
    v23 = 0;
    if ( UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)&v19, 0, 0x30005u, &Value, 4u, 0, 0) )
    {
      CurrentProcess = GetCurrentProcess();
      RemoteThread = CreateRemoteThreadEx(
                       CurrentProcess,
                       0,
                       v6,
                       SchedulerManager::ThreadEntryPoint,
                       a1,
                       a2,
                       (LPPROC_THREAD_ATTRIBUTE_LIST)&v19,
                       0);
      if ( !RemoteThread )
        RemoteThread = (void *)_beginthreadex(0, v6, SchedulerManager::ThreadEntryPoint, a1, a2, 0);
    }
    DeleteProcThreadAttributeList((LPPROC_THREAD_ATTRIBUTE_LIST)&v19);
  }
  if ( RemoteThread )
  {
    CloseHandle(RemoteThread);
    return v4;
  }
  return 2684354560LL;
}

```

## disassembly

```asm
0x10042bcc0  push    rbp
0x10042bcc2  push    r12
0x10042bcc4  push    r13
0x10042bcc6  push    r14
0x10042bcc8  push    r15
0x10042bcca  sub     rsp, 80h
0x10042bcd1  lea     rbp, [rsp+40h]
0x10042bcd6  mov     [rbp+60h+arg_0], rbx
0x10042bcda  mov     [rbp+60h+arg_8], rsi
0x10042bcde  mov     [rbp+60h+arg_10], rdi
0x10042bce5  mov     rax, cs:__security_cookie
0x10042bcec  xor     rax, rbp
0x10042bcef  mov     [rbp+60h+var_30], rax
0x10042bcf3  mov     eax, cs:dword_1007143C8
0x10042bcf9  xor     r13d, r13d
0x10042bcfc  mov     [rbp+60h+var_60], eax
0x10042bcff  mov     r12d, edx
0x10042bd02  mov     eax, cs:dword_1007143CC
0x10042bd08  mov     r15, rcx
0x10042bd0b  mov     [rbp+60h+var_54], eax
0x10042bd0e  mov     edi, r13d
0x10042bd11  mov     eax, cs:dword_1007143D0
0x10042bd17  mov     [rbp+60h+var_5C], eax
0x10042bd1a  mov     eax, cs:dword_1007143D4
0x10042bd20  mov     [rbp+60h+var_50], eax
0x10042bd23  mov     r8d, [rbp+60h+var_54]
0x10042bd27  mov     eax, [rbp+60h+var_60]
0x10042bd2a  cmp     eax, r8d
0x10042bd2d  jl      loc_100478018
0x10042bd33  mov     ecx, [rbp+60h+var_50]
0x10042bd36  mov     eax, [rbp+60h+var_60]
0x10042bd39  cmp     eax, ecx
0x10042bd3b  jg      loc_100478079
0x10042bd41  test    edi, edi
0x10042bd43  jnz     loc_10042BE79
0x10042bd49  test    cs:byte_1007149B3, 2
0x10042bd50  mov     rbx, r13
0x10042bd53  jnz     loc_100478070
0x10042bd59  mov     esi, dword ptr cs:?sm_StackSize@SOS_PublicGlobals@@2_KA; unsigned __int64 SOS_PublicGlobals::sm_StackSize
0x10042bd5f  add     esi, 0FFFFF000h
0x10042bd65  xor     ecx, ecx; Security
0x10042bd67  test    cs:?sm_osStatus@SOS_PublicGlobals@@2KA, 100h; ulong SOS_PublicGlobals::sm_osStatus
0x10042bd71  jnz     loc_100478125
0x10042bd77  xor     r8d, r8d; dwFlags
0x10042bd7a  lea     r9, [rbp+60h+Size]; lpSize
0x10042bd7e  lea     edx, [r8+1]; dwAttributeCount
0x10042bd82  call    cs:__imp_InitializeProcThreadAttributeList
0x10042bd88  mov     rax, [rbp+60h+Size]
0x10042bd8c  lea     rcx, [rax+0Fh]
0x10042bd90  cmp     rcx, rax
0x10042bd93  jbe     loc_10047814A
0x10042bd99  and     rcx, 0FFFFFFFFFFFFFFF0h
0x10042bd9d  mov     rax, rcx
0x10042bda0  call    _alloca_probe
0x10042bda5  sub     rsp, rcx
0x10042bda8  lea     r9, [rbp+60h+Size]; lpSize
0x10042bdac  xor     r8d, r8d; dwFlags
0x10042bdaf  lea     r14, [rsp+0A0h+var_60]
0x10042bdb4  mov     rcx, r14; lpAttributeList
0x10042bdb7  lea     edx, [r8+1]; dwAttributeCount
0x10042bdbb  call    cs:__imp_InitializeProcThreadAttributeList
0x10042bdc1  test    eax, eax
0x10042bdc3  jz      loc_100478181
0x10042bdc9  mov     rax, [r15+118h]
0x10042bdd0  lea     r9, [rbp+60h+Value]; lpValue
0x10042bdd4  mov     [rsp+0A0h+lpReturnSize], r13; lpReturnSize
0x10042bdd9  mov     r8d, 30005h; Attribute
0x10042bddf  mov     [rsp+0A0h+lpPreviousValue], r13; lpPreviousValue
0x10042bde4  mov     [rsp+0A0h+cbSize], 4; cbSize
0x10042bded  mov     rdx, [rax+0E0h]
0x10042bdf4  mov     rcx, [rdx+8]
0x10042bdf8  lea     rax, [rcx-1]
0x10042bdfc  not     rax
0x10042bdff  and     rax, rcx
0x10042be02  bsf     rcx, rax
0x10042be06  movzx   eax, word ptr [rdx+10h]
0x10042be0a  xor     edx, edx; dwFlags
0x10042be0c  mov     [rbp+60h+var_56], cl
0x10042be0f  mov     rcx, r14; lpAttributeList
0x10042be12  mov     [rbp+60h+Value], ax
0x10042be16  mov     [rbp+60h+var_55], bl
0x10042be19  call    cs:__imp_UpdateProcThreadAttribute
0x10042be1f  test    eax, eax
0x10042be21  jz      short loc_10042BE5E
0x10042be23  call    cs:__imp_GetCurrentProcess
0x10042be29  mov     [rsp+0A0h+lpThreadId], r13; lpThreadId
0x10042be2e  lea     r9, ?ThreadEntryPoint@SchedulerManager@@SAIPEAX@Z; lpStartAddress
0x10042be35  mov     [rsp+0A0h+lpReturnSize], r14; lpAttributeList
0x10042be3a  mov     rcx, rax; hProcess
0x10042be3d  mov     dword ptr [rsp+0A0h+lpPreviousValue], r12d; dwCreationFlags
0x10042be42  xor     edx, edx; lpThreadAttributes
0x10042be44  mov     r8d, esi; dwStackSize
0x10042be47  mov     [rsp+0A0h+cbSize], r15; lpParameter
0x10042be4c  call    cs:__imp_CreateRemoteThreadEx
0x10042be52  mov     rbx, rax
0x10042be55  test    rax, rax
0x10042be58  jz      loc_10047815A
0x10042be5e  mov     rcx, r14; lpAttributeList
0x10042be61  call    cs:__imp_DeleteProcThreadAttributeList
0x10042be67  test    rbx, rbx
0x10042be6a  jz      loc_100478181
0x10042be70  mov     rcx, rbx; hObject
0x10042be73  call    cs:__imp_CloseHandle
0x10042be79  mov     eax, edi
0x10042be7b  mov     rcx, [rbp+60h+var_30]
0x10042be7f  xor     rcx, rbp; StackCookie
0x10042be82  call    __security_check_cookie
0x10042be87  mov     rbx, [rbp+60h+arg_0]
0x10042be8b  mov     rsi, [rbp+60h+arg_8]
0x10042be8f  mov     rdi, [rbp+60h+arg_10]
0x10042be96  lea     rsp, [rbp+40h]
0x10042be9a  pop     r15
0x10042be9c  pop     r14
0x10042be9e  pop     r13
0x10042bea0  pop     r12
0x10042bea2  pop     rbp
0x10042bea3  retn
0x100478018  mov     eax, cs:dword_1007143C8
0x10047801e  mov     [rbp+60h+var_60], eax
0x100478021  mov     ecx, [rbp+60h+var_5C]
0x100478024  mov     eax, [rbp+60h+var_60]
0x100478027  cmp     eax, ecx
0x100478029  jge     loc_10042BD41
0x10047802f  lea     rdx, [rbp+60h+var_48]
0x100478033  mov     [rbp+60h+var_48], r13
0x100478037  call    ?AllocObject@MiniSOSThreadResourcesMgr@@AEAA?AW4SOS_RESULT@@PEAPEAVMiniSOSThreadResources@@@Z; MiniSOSThreadResourcesMgr::AllocObject(MiniSOSThreadResources * *)
0x10047803c  mov     edi, eax
0x10047803e  test    eax, eax
0x100478040  jnz     loc_10042BD41
0x100478046  mov     rdx, [rbp+60h+var_48]; struct MiniSOSThreadResources *
0x10047804a  lea     rcx, ?sm_MiniSOSThreadResourcesMgr@SOS_PublicGlobals@@2VMiniSOSThreadResourcesMgr@@A; this
0x100478051  call    ?StoreObject@MiniSOSThreadResourcesMgr@@QEAAXPEAVMiniSOSThreadResources@@@Z; MiniSOSThreadResourcesMgr::StoreObject(MiniSOSThreadResources *)
0x100478056  mov     eax, cs:dword_1007143C8
0x10047805c  mov     [rbp+60h+var_60], eax
0x10047805f  mov     ecx, [rbp+60h+var_5C]
0x100478062  mov     eax, [rbp+60h+var_60]
0x100478065  cmp     eax, ecx
0x100478067  jge     loc_10042BD41
0x10047806d  jmp     short loc_10047802F
0x100478070  mov     esi, r13d
0x100478073  jmp     loc_10042BD65
0x100478079  mov     eax, cs:dword_1007143C8
0x10047807f  mov     [rbp+60h+var_60], eax
0x100478082  mov     ecx, [rbp+60h+var_5C]
0x100478085  mov     eax, [rbp+60h+var_60]
0x100478088  cmp     eax, ecx
0x10047808a  jle     loc_10042BD49
0x100478090  nop     word ptr [rax+rax]
0x100478095  nop     word ptr [rax+rax+00000000h]
0x1004780a0  mov     eax, [rbp+60h+var_60]
0x1004780a3  mov     ecx, [rbp+60h+var_5C]
0x1004780a6  lock cmpxchg cs:dword_1007143C8, ecx
0x1004780ae  mov     ecx, [rbp+60h+var_60]
0x1004780b1  cmp     eax, ecx
0x1004780b3  jz      short loc_1004780CF
0x1004780b5  pause
0x1004780b7  mov     eax, cs:dword_1007143C8
0x1004780bd  mov     [rbp+60h+var_60], eax
0x1004780c0  mov     ecx, [rbp+60h+var_5C]
0x1004780c3  mov     eax, [rbp+60h+var_60]
0x1004780c6  cmp     eax, ecx
0x1004780c8  jg      short loc_1004780A0
0x1004780ca  jmp     loc_10042BD49
0x1004780cf  mov     eax, [rbp+60h+var_5C]
0x1004780d2  mov     ecx, [rbp+60h+var_60]
0x1004780d5  sub     ecx, eax
0x1004780d7  mov     [rbp+60h+var_5C], ecx
0x1004780da  mov     eax, [rbp+60h+var_5C]
0x1004780dd  test    eax, eax
0x1004780df  jle     loc_10042BD41
0x1004780e5  lea     rcx, ?sm_MiniSOSThreadResourcesMgr@SOS_PublicGlobals@@2VMiniSOSThreadResourcesMgr@@A; MiniSOSThreadResourcesMgr SOS_PublicGlobals::sm_MiniSOSThreadResourcesMgr
0x1004780ec  call    ?RetrieveObject@?$TObjectPool@V?$TMRUContainer@VMiniSOSThreadResources@@$0A@@@UObjectPoolSLock@@@@QEAAPEAVMiniSOSThreadResources@@XZ; TObjectPool<TMRUContainer<MiniSOSThreadResources,0>,ObjectPoolSLock>::RetrieveObject(void)
0x1004780f1  mov     rcx, rax; this
0x1004780f4  mov     rbx, rax
0x1004780f7  call    ??1MiniSOSThreadResources@@AEAA@XZ; MiniSOSThreadResources::~MiniSOSThreadResources(void)
0x1004780fc  call    cs:__imp_GetProcessHeap
0x100478102  mov     r8, rbx; lpMem
0x100478105  xor     edx, edx; dwFlags
0x100478107  mov     rcx, rax; hHeap
0x10047810a  call    cs:__imp_HeapFree
0x100478110  mov     eax, [rbp+60h+var_5C]
0x100478113  dec     eax
0x100478115  mov     [rbp+60h+var_5C], eax
0x100478118  mov     eax, [rbp+60h+var_5C]
0x10047811b  test    eax, eax
0x10047811d  jg      short loc_1004780E5
0x10047811f  jmp     loc_10042BD49
0x100478125  mov     [rsp+0A0h+lpPreviousValue], r13; ThrdAddr
0x10047812a  lea     r8, ?ThreadEntryPoint@SchedulerManager@@SAIPEAX@Z; StartAddress
0x100478131  mov     r9, r15; ArgList
0x100478134  mov     dword ptr [rsp+0A0h+cbSize], r12d; InitFlag
0x100478139  mov     edx, esi; StackSize
0x10047813b  call    cs:__imp__beginthreadex
0x100478141  mov     rbx, rax
0x100478144  jmp     loc_10042BE67
0x10047814a  mov     rcx, 0FFFFFFFFFFFFFF0h
0x100478154  jmp     loc_10042BD99
0x10047815a  mov     [rsp+0A0h+lpPreviousValue], r13; ThrdAddr
0x10047815f  lea     r8, ?ThreadEntryPoint@SchedulerManager@@SAIPEAX@Z; StartAddress
0x100478166  mov     r9, r15; ArgList
0x100478169  mov     dword ptr [rsp+0A0h+cbSize], r12d; InitFlag
0x10047816e  mov     edx, esi; StackSize
0x100478170  xor     ecx, ecx; Security
0x100478172  call    cs:__imp__beginthreadex
0x100478178  mov     rbx, rax
0x10047817b  jmp     loc_10042BE5E
0x100478181  mov     eax, 0A0000000h
0x100478186  jmp     loc_10042BE7B
```
