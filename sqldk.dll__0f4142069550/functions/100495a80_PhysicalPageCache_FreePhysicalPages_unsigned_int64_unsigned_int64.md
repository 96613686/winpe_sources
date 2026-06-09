# PhysicalPageCache::FreePhysicalPages(unsigned __int64 *,unsigned __int64)

- ea: `0x100495a80`
- end: `0x100495d03`
- name: `?FreePhysicalPages@PhysicalPageCache@@QEAAHPEA_K_K@Z`
- size: `643`
- prototype: `int(PhysicalPageCache *__hidden this, unsigned __int64 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x100495680`
- `0x1004a21c0`

## callees

- `0x100419380`
- `0x100420f30`
- `0x100421040`
- `0x1004360f0`
- `0x100495a80`
- `0x100495d10`

## import_xrefs

- `KERNEL32!FreeUserPhysicalPages` at `0x100495afc`
- `KERNEL32!FreeUserPhysicalPages` at `0x100495c5b`
- `KERNEL32!FreeUserPhysicalPages` at `0x100495afc`
- `KERNEL32!FreeUserPhysicalPages` at `0x100495c5b`
- `KERNEL32!GetLastError` at `0x100495b1c`
- `KERNEL32!GetLastError` at `0x100495c77`
- `KERNEL32!GetLastError` at `0x100495b1c`
- `KERNEL32!GetLastError` at `0x100495c77`
- `KERNEL32!GetCurrentProcess` at `0x100495ae8`
- `KERNEL32!GetCurrentProcess` at `0x100495c46`
- `KERNEL32!GetCurrentProcess` at `0x100495ae8`
- `KERNEL32!GetCurrentProcess` at `0x100495c46`

## string_xrefs

- `0x100495b24`: `PhysicalPageCache::Free unable to free memory, GetLastError=%#x\n`
- `0x100495c7f`: `PhysicalPageCache::Free unable to free memory, GetLastError=%#x\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PhysicalPageCache::FreePhysicalPages(
        PhysicalPageCache *this,
        unsigned __int64 *a2,
        unsigned __int64 a3)
{
  __int64 v6; // rdi
  __int64 v7; // rax
  HANDLE CurrentProcess; // rax
  void (*v9)(const wchar_t *, ...); // rbx
  DWORD LastError; // eax
  __int64 v11; // rdi
  __int64 v12; // rdx
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // rcx
  HANDLE v15; // rax
  void (*v16)(const wchar_t *, ...); // rdi
  DWORD v17; // eax
  unsigned __int64 v20[3]; // [rsp+20h] [rbp-68h] BYREF
  int v21; // [rsp+38h] [rbp-50h]
  int v22; // [rsp+40h] [rbp-48h] BYREF
  __int64 v23; // [rsp+48h] [rbp-40h]
  __int64 v24; // [rsp+50h] [rbp-38h]
  __int64 v25; // [rsp+58h] [rbp-30h]
  __int64 v26; // [rsp+60h] [rbp-28h]
  unsigned __int64 NumberOfPages; // [rsp+A8h] [rbp+20h] BYREF

  v20[1] = -2;
  v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
     + (unsigned int)SystemThread_TlsOffset;
  v7 = *(_QWORD *)(v6 + 256);
  if ( !v7 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v7 = *(_QWORD *)(v6 + 256);
  }
  if ( (*(_BYTE *)(v7 + 616) & 0x40) != 0 )
  {
    NumberOfPages = a3;
    CurrentProcess = GetCurrentProcess();
    if ( !FreeUserPhysicalPages(CurrentProcess, &NumberOfPages, a2) )
    {
      v9 = (void (*)(const wchar_t *, ...))SOS_PublicGlobals::sm_LogSystemMetadataRoutine;
      if ( !SOS_PublicGlobals::sm_LogSystemMetadataRoutine )
        v9 = SOS_OS_LogUnlocalizedRoutine;
      LastError = GetLastError();
      v9(L"PhysicalPageCache::Free unable to free memory, GetLastError=%#x\n", LastError);
    }
    return 1;
  }
  if ( ((qword_1007149B5 & 0x10000000000LL) == 0
     && (qword_1007149B5 & 0x2000000000000LL) == 0
     && (unsigned int)ResourceMonitor::CheckNoQueryResourceSetSystemWide(1)
     || *((_QWORD *)this + 4113))
    && (qword_1007149B5 & 0x10000000000LL) == 0
    && (qword_1007149B5 & 0x2000000000000LL) == 0 )
  {
    EventAutoInternal<PaddedSpinlock<SuspendQueueExpSLock>>::SignalAll((char *)this + 32960);
  }
  _InterlockedIncrement64((volatile signed __int64 *)this + 4112);
  v22 = 4194406;
  v23 = 0;
  v25 = 0;
  v24 = 0;
  v26 = 0;
  v20[2] = (unsigned __int64)this;
  v21 = 0;
  v11 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
      + (unsigned int)SystemThread_TlsOffset;
  v12 = *(_QWORD *)(v11 + 256);
  if ( !v12 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v12 = *(_QWORD *)(v11 + 256);
  }
  if ( v12 == *((_QWORD *)this + 4) )
  {
    ++*((_QWORD *)this + 7);
LABEL_21:
    v21 = 1;
    goto LABEL_22;
  }
  if ( !(unsigned int)UnfairRecursiveMutexInternal<SuspendQueueExpSLock,0>::LongWait(this, v12, 0xFFFFFFFFLL, &v22) )
    goto LABEL_21;
LABEL_22:
  while ( a3 )
  {
    v13 = *((_QWORD *)this + 8);
    if ( v13 >= 0x1000 )
    {
      v20[0] = v13 - 2048;
      *((_QWORD *)this + 8) = 2048;
      v15 = GetCurrentProcess();
      if ( !FreeUserPhysicalPages(v15, v20, (PULONG_PTR)this + 2057) )
      {
        v16 = (void (*)(const wchar_t *, ...))SOS_PublicGlobals::sm_LogSystemMetadataRoutine;
        if ( !SOS_PublicGlobals::sm_LogSystemMetadataRoutine )
          v16 = SOS_OS_LogUnlocalizedRoutine;
        v17 = GetLastError();
        v16(L"PhysicalPageCache::Free unable to free memory, GetLastError=%#x\n", v17);
      }
    }
    else
    {
      v14 = a2[--a3];
      if ( v14 )
      {
        *((_QWORD *)this + v13 + 9) = v14;
        ++*((_QWORD *)this + 8);
      }
    }
  }
  _InterlockedDecrement64((volatile signed __int64 *)this + 4112);
  for ( ; v21; --v21 )
  {
    if ( !*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                    + (unsigned int)SystemThread_TlsOffset
                    + 256LL) )
      SystemThread::MakeMiniSOSThread(0);
    if ( (*((_QWORD *)this + 7))-- == 1 )
    {
      *((_QWORD *)this + 5) = 0;
      *((_QWORD *)this + 6) = 0;
      *((_QWORD *)this + 4) = 0;
      UnfairRecursiveMutexInternal<SuspendQueueExpSLock,0>::WakeUpWaiters(this);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x100495a80  mov     rax, rsp
0x100495a83  push    rsi
0x100495a84  push    rdi
0x100495a85  push    r14
0x100495a87  sub     rsp, 70h
0x100495a8b  mov     qword ptr [rax-60h], 0FFFFFFFFFFFFFFFEh
0x100495a93  mov     [rax+8], rbx
0x100495a97  mov     [rax+10h], rbp
0x100495a9b  mov     rsi, r8
0x100495a9e  mov     r14, rdx
0x100495aa1  mov     rbx, rcx
0x100495aa4  mov     rcx, gs:58h
0x100495aad  mov     eax, cs:_tls_index
0x100495ab3  mov     edi, cs:SystemThread_TlsOffset
0x100495ab9  add     rdi, [rcx+rax*8]
0x100495abd  mov     rax, [rdi+100h]
0x100495ac4  test    rax, rax
0x100495ac7  jnz     short loc_100495AD7
0x100495ac9  xor     ecx, ecx; void *
0x100495acb  call    ?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100495ad0  mov     rax, [rdi+100h]
0x100495ad7  test    byte ptr [rax+268h], 40h
0x100495ade  jz      short loc_100495B32
0x100495ae0  mov     [rsp+88h+NumberOfPages], rsi
0x100495ae8  call    cs:__imp_GetCurrentProcess
0x100495aee  mov     rcx, rax; hProcess
0x100495af1  mov     r8, r14; PageArray
0x100495af4  lea     rdx, [rsp+88h+NumberOfPages]; NumberOfPages
0x100495afc  call    cs:__imp_FreeUserPhysicalPages
0x100495b02  test    eax, eax
0x100495b04  jnz     loc_100495CE9
0x100495b0a  mov     rbx, cs:?sm_LogSystemMetadataRoutine@SOS_PublicGlobals@@2P6AXPEB_WZZEA; void (*SOS_PublicGlobals::sm_LogSystemMetadataRoutine)(wchar_t const *,...)
0x100495b11  test    rbx, rbx
0x100495b14  cmovz   rbx, cs:?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA; void (*SOS_OS_LogUnlocalizedRoutine)(wchar_t const *,...)
0x100495b1c  call    cs:__imp_GetLastError
0x100495b22  mov     edx, eax
0x100495b24  lea     rcx, aPhysicalpageca; "PhysicalPageCache::Free unable to free "...
0x100495b2b  call    rbx
0x100495b2d  jmp     loc_100495CE9
0x100495b32  test    byte ptr cs:qword_1007149B5+5, 1
0x100495b39  jnz     short loc_100495B52
0x100495b3b  test    byte ptr cs:qword_1007149B5+6, 2
0x100495b42  jnz     short loc_100495B52
0x100495b44  mov     ecx, 1
0x100495b49  call    ?CheckNoQueryResourceSetSystemWide@ResourceMonitor@@SAHW4resource_idx@@@Z; ResourceMonitor::CheckNoQueryResourceSetSystemWide(resource_idx)
0x100495b4e  test    eax, eax
0x100495b50  jnz     short loc_100495B5E
0x100495b52  mov     rax, [rbx+8088h]
0x100495b59  test    rax, rax
0x100495b5c  jz      short loc_100495B7C
0x100495b5e  test    byte ptr cs:qword_1007149B5+5, 1
0x100495b65  jnz     short loc_100495B7C
0x100495b67  test    byte ptr cs:qword_1007149B5+6, 2
0x100495b6e  jnz     short loc_100495B7C
0x100495b70  lea     rcx, [rbx+80C0h]
0x100495b77  call    ?SignalAll@?$EventAutoInternal@V?$PaddedSpinlock@USuspendQueueExpSLock@@@@@@QEAAXXZ; EventAutoInternal<PaddedSpinlock<SuspendQueueExpSLock>>::SignalAll(void)
0x100495b7c  lock inc qword ptr [rbx+8080h]
0x100495b84  mov     [rsp+88h+var_48], 400066h
0x100495b8c  xor     ebp, ebp
0x100495b8e  mov     [rsp+88h+var_40], rbp
0x100495b93  mov     [rsp+88h+var_30], rbp
0x100495b98  mov     [rsp+88h+var_38], rbp
0x100495b9d  mov     [rsp+88h+var_28], rbp
0x100495ba2  mov     [rsp+88h+var_58], rbx
0x100495ba7  mov     [rsp+88h+var_50], ebp
0x100495bab  mov     rcx, gs:58h
0x100495bb4  mov     eax, cs:_tls_index
0x100495bba  mov     edi, cs:SystemThread_TlsOffset
0x100495bc0  add     rdi, [rcx+rax*8]
0x100495bc4  mov     rdx, [rdi+100h]
0x100495bcb  test    rdx, rdx
0x100495bce  jnz     short loc_100495BDE
0x100495bd0  xor     ecx, ecx; void *
0x100495bd2  call    ?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100495bd7  mov     rdx, [rdi+100h]
0x100495bde  cmp     rdx, [rbx+20h]
0x100495be2  jz      short loc_100495BFD
0x100495be4  lea     r9, [rsp+88h+var_48]
0x100495be9  mov     r8d, 0FFFFFFFFh
0x100495bef  mov     rcx, rbx
0x100495bf2  call    ?LongWait@?$UnfairRecursiveMutexInternal@USuspendQueueExpSLock@@$0A@@@AEAA?AW4SOS_RESULT@@PEAVWorker@@KQEBVSOS_WaitInfo@@@Z; UnfairRecursiveMutexInternal<SuspendQueueExpSLock,0>::LongWait(Worker *,ulong,SOS_WaitInfo const * const)
0x100495bf7  test    eax, eax
0x100495bf9  jnz     short loc_100495C09
0x100495bfb  jmp     short loc_100495C01
0x100495bfd  inc     qword ptr [rbx+38h]
0x100495c01  mov     [rsp+88h+var_50], 1
0x100495c09  test    rsi, rsi
0x100495c0c  jz      short loc_100495C8D
0x100495c0e  mov     rax, [rbx+40h]
0x100495c12  cmp     rax, 1000h
0x100495c18  jnb     short loc_100495C31
0x100495c1a  dec     rsi
0x100495c1d  mov     rcx, [r14+rsi*8]
0x100495c21  test    rcx, rcx
0x100495c24  jz      short loc_100495C88
0x100495c26  mov     [rbx+rax*8+48h], rcx
0x100495c2b  inc     qword ptr [rbx+40h]
0x100495c2f  jmp     short loc_100495C88
0x100495c31  add     rax, 0FFFFFFFFFFFFF800h
0x100495c37  mov     [rsp+88h+var_68], rax
0x100495c3c  jz      short loc_100495C88
0x100495c3e  mov     qword ptr [rbx+40h], 800h
0x100495c46  call    cs:__imp_GetCurrentProcess
0x100495c4c  mov     rcx, rax; hProcess
0x100495c4f  lea     r8, [rbx+4048h]; PageArray
0x100495c56  lea     rdx, [rsp+88h+var_68]; NumberOfPages
0x100495c5b  call    cs:__imp_FreeUserPhysicalPages
0x100495c61  test    eax, eax
0x100495c63  jnz     short loc_100495C88
0x100495c65  mov     rdi, cs:?sm_LogSystemMetadataRoutine@SOS_PublicGlobals@@2P6AXPEB_WZZEA; void (*SOS_PublicGlobals::sm_LogSystemMetadataRoutine)(wchar_t const *,...)
0x100495c6c  test    rdi, rdi
0x100495c6f  cmovz   rdi, cs:?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA; void (*SOS_OS_LogUnlocalizedRoutine)(wchar_t const *,...)
0x100495c77  call    cs:__imp_GetLastError
0x100495c7d  mov     edx, eax
0x100495c7f  lea     rcx, aPhysicalpageca; "PhysicalPageCache::Free unable to free "...
0x100495c86  call    rdi
0x100495c88  test    rsi, rsi
0x100495c8b  jnz     short loc_100495C0E
0x100495c8d  lock dec qword ptr [rbx+8080h]
0x100495c95  cmp     [rsp+88h+var_50], 0
0x100495c9a  jbe     short loc_100495CE9
0x100495c9c  mov     rdx, gs:58h
0x100495ca5  mov     eax, cs:_tls_index
0x100495cab  mov     ecx, cs:SystemThread_TlsOffset
0x100495cb1  mov     rax, [rdx+rax*8]
0x100495cb5  cmp     qword ptr [rax+rcx+100h], 0
0x100495cbe  jnz     short loc_100495CC7
0x100495cc0  xor     ecx, ecx; void *
0x100495cc2  call    ?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100495cc7  sub     qword ptr [rbx+38h], 1
0x100495ccc  jnz     short loc_100495CE2
0x100495cce  mov     [rbx+28h], rbp
0x100495cd2  mov     [rbx+30h], rbp
0x100495cd6  mov     [rbx+20h], rbp
0x100495cda  mov     rcx, rbx
0x100495cdd  call    ?WakeUpWaiters@?$UnfairRecursiveMutexInternal@USuspendQueueExpSLock@@$0A@@@QEAAXXZ; UnfairRecursiveMutexInternal<SuspendQueueExpSLock,0>::WakeUpWaiters(void)
0x100495ce2  add     [rsp+88h+var_50], 0FFFFFFFFh
0x100495ce7  jnz     short loc_100495C9C
0x100495ce9  mov     eax, 1
0x100495cee  lea     r11, [rsp+88h+var_18]
0x100495cf3  mov     rbx, [r11+20h]
0x100495cf7  mov     rbp, [r11+28h]
0x100495cfb  mov     rsp, r11
0x100495cfe  pop     r14
0x100495d00  pop     rdi
0x100495d01  pop     rsi
0x100495d02  retn
```
