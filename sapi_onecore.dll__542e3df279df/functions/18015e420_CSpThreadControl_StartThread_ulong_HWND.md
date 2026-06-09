# CSpThreadControl::StartThread(ulong,HWND__ * *)

- ea: `0x18015e420`
- end: `0x18015e603`
- name: `?StartThread@CSpThreadControl@@UEAAJKPEAPEAUHWND__@@@Z`
- size: `483`
- prototype: `__int64 __fastcall(CSpThreadControl *__hidden this, unsigned int, HWND *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18007d31c`
- `0x18008878c`
- `0x18015dcf8`
- `0x18015e420`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18015e46c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18015e46c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18015e485`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18015e485`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18015e44a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18015e48e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18015e49c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18015e44a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18015e48e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18015e49c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18015e475`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18015e5b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18015e5ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18015e475`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18015e5b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18015e5ec`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18015e4b9`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18015e4e2`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18015e4b9`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18015e4e2`

## pseudocode

```c
__int64 __fastcall CSpThreadControl::StartThread(struct _SECURITY_ATTRIBUTES *this, int a2, HWND *a3)
{
  int v5; // ebx
  struct _RTL_CRITICAL_SECTION *p_bInheritHandle; // r15
  __int64 v7; // rax
  __int64 v8; // rsi
  CSpThreadTask *v9; // rdi
  int lpSecurityDescriptor; // ebx
  int ThreadPriority; // eax
  HANDLE *v12; // rcx
  CSpThreadTask *v13; // r14
  int v14; // ebx
  int v15; // eax
  CSpThreadTask *v16; // rax
  unsigned int v17; // edx

  if ( a2 )
    return (unsigned int)-2147024809;
  p_bInheritHandle = (struct _RTL_CRITICAL_SECTION *)&this->bInheritHandle;
  EnterCriticalSection((LPCRITICAL_SECTION)&this->bInheritHandle);
  v7 = *(_QWORD *)&this[3].nLength;
  if ( v7 )
  {
    *(_DWORD *)(v7 + 4) = 0;
    SetEvent(*(HANDLE *)(*(_QWORD *)&this[3].nLength + 40LL));
    LeaveCriticalSection(p_bInheritHandle);
    WaitForSingleObject(this[5].lpSecurityDescriptor, 0xFFFFFFFF);
    EnterCriticalSection(p_bInheritHandle);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)&this[2].bInheritHandle + 16LL));
  v8 = *(_QWORD *)&this[2].bInheritHandle;
  v9 = *(CSpThreadTask **)(v8 + 152);
  if ( v9 )
  {
    lpSecurityDescriptor = (int)this[3].lpSecurityDescriptor;
    ThreadPriority = GetThreadPriority(*((HANDLE *)v9 + 11));
    v12 = (HANDLE *)*((_QWORD *)v9 + 12);
    if ( ThreadPriority != lpSecurityDescriptor )
    {
      do
      {
        v13 = v9;
        v9 = (CSpThreadTask *)v12;
        if ( !v12 )
        {
          v8 = *(_QWORD *)&this[2].bInheritHandle;
          goto LABEL_14;
        }
        v14 = (int)this[3].lpSecurityDescriptor;
        v15 = GetThreadPriority(v12[11]);
        v12 = (HANDLE *)*((_QWORD *)v9 + 12);
      }
      while ( v15 != v14 );
      *((_QWORD *)v13 + 12) = v12;
      if ( !*((_QWORD *)v9 + 12) )
        *(_QWORD *)(v8 + 160) = v13;
      --*(_DWORD *)(v8 + 168);
      goto LABEL_20;
    }
    *(_QWORD *)(v8 + 152) = v12;
    goto LABEL_16;
  }
LABEL_14:
  v9 = *(CSpThreadTask **)(v8 + 152);
  if ( v9 )
  {
    *(_QWORD *)(v8 + 152) = *((_QWORD *)v9 + 12);
LABEL_16:
    --*(_DWORD *)(v8 + 168);
    goto LABEL_20;
  }
  v16 = (CSpThreadTask *)operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v16;
  if ( v16 )
  {
    *((_QWORD *)v16 + 5) = 0;
    *((_QWORD *)v16 + 4) = &CSpAutoEvent::`vftable';
    *((_QWORD *)v16 + 6) = &CSpAutoEvent::`vftable';
    *((_QWORD *)v16 + 7) = 0;
    *((_QWORD *)v16 + 8) = &CSpAutoEvent::`vftable';
    *((_QWORD *)v16 + 9) = 0;
    *((_QWORD *)v16 + 10) = &CSpAutoEvent::`vftable';
    *((_QWORD *)v16 + 11) = 0;
    *(_DWORD *)v16 = 0;
    *((_QWORD *)v16 + 3) = 0;
    *((_QWORD *)v16 + 1) = 0;
    *((_DWORD *)v16 + 5) = 0;
  }
  else
  {
    v9 = 0;
  }
LABEL_20:
  LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)&this[2].bInheritHandle + 16LL));
  if ( v9 )
  {
    v5 = CSpThreadTask::Init(v9, this, a3);
    if ( v5 >= 0 )
      *(_QWORD *)&this[3].nLength = v9;
    else
      CSpThreadTask::`scalar deleting destructor'(v9, v17);
  }
  else
  {
    v5 = -2147024882;
  }
  LeaveCriticalSection(p_bInheritHandle);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18015e420  push    rbx
0x18015e422  push    rbp
0x18015e423  push    rsi
0x18015e424  push    rdi
0x18015e425  push    r12
0x18015e427  push    r14
0x18015e429  push    r15
0x18015e42b  sub     rsp, 20h
0x18015e42f  mov     r12, r8
0x18015e432  mov     rbp, rcx
0x18015e435  test    edx, edx
0x18015e437  jz      short loc_18015E443
0x18015e439  mov     ebx, 80070057h
0x18015e43e  jmp     loc_18015E5F2
0x18015e443  lea     r15, [rcx+10h]
0x18015e447  mov     rcx, r15; lpCriticalSection
0x18015e44a  call    cs:__imp_EnterCriticalSection
0x18015e450  mov     rax, [rbp+48h]
0x18015e454  or      r14d, 0FFFFFFFFh
0x18015e458  test    rax, rax
0x18015e45b  jz      short loc_18015E494
0x18015e45d  mov     dword ptr [rax+4], 0
0x18015e464  mov     rcx, [rbp+48h]
0x18015e468  mov     rcx, [rcx+28h]; hEvent
0x18015e46c  call    cs:__imp_SetEvent
0x18015e472  mov     rcx, r15; lpCriticalSection
0x18015e475  call    cs:__imp_LeaveCriticalSection
0x18015e47b  mov     rcx, [rbp+80h]; hHandle
0x18015e482  mov     edx, r14d; dwMilliseconds
0x18015e485  call    cs:__imp_WaitForSingleObject
0x18015e48b  mov     rcx, r15; lpCriticalSection
0x18015e48e  call    cs:__imp_EnterCriticalSection
0x18015e494  mov     rcx, [rbp+40h]
0x18015e498  add     rcx, 10h; lpCriticalSection
0x18015e49c  call    cs:__imp_EnterCriticalSection
0x18015e4a2  mov     rsi, [rbp+40h]
0x18015e4a6  mov     rdi, [rsi+98h]
0x18015e4ad  test    rdi, rdi
0x18015e4b0  jz      short loc_18015E515
0x18015e4b2  mov     rcx, [rdi+58h]; hThread
0x18015e4b6  mov     ebx, [rbp+50h]
0x18015e4b9  call    cs:__imp_GetThreadPriority
0x18015e4bf  mov     rcx, [rdi+60h]
0x18015e4c3  cmp     eax, ebx
0x18015e4c5  jnz     short loc_18015E4D0
0x18015e4c7  mov     [rsi+98h], rcx
0x18015e4ce  jmp     short loc_18015E52C
0x18015e4d0  mov     r14, rdi
0x18015e4d3  mov     rdi, rcx
0x18015e4d6  test    rcx, rcx
0x18015e4d9  jz      short loc_18015E50D
0x18015e4db  mov     rcx, [rcx+58h]; hThread
0x18015e4df  mov     ebx, [rbp+50h]
0x18015e4e2  call    cs:__imp_GetThreadPriority
0x18015e4e8  mov     rcx, [rdi+60h]
0x18015e4ec  cmp     eax, ebx
0x18015e4ee  jnz     short loc_18015E4D0
0x18015e4f0  mov     [r14+60h], rcx
0x18015e4f4  cmp     qword ptr [rdi+60h], 0
0x18015e4f9  jnz     short loc_18015E502
0x18015e4fb  mov     [rsi+0A0h], r14
0x18015e502  dec     dword ptr [rsi+0A8h]
0x18015e508  jmp     loc_18015E5AD
0x18015e50d  mov     rsi, [rbp+40h]
0x18015e511  or      r14d, 0FFFFFFFFh
0x18015e515  mov     rdi, [rsi+98h]
0x18015e51c  test    rdi, rdi
0x18015e51f  jz      short loc_18015E535
0x18015e521  mov     rax, [rdi+60h]
0x18015e525  mov     [rsi+98h], rax
0x18015e52c  add     [rsi+0A8h], r14d
0x18015e533  jmp     short loc_18015E5AD
0x18015e535  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18015e53c  mov     ecx, 68h ; 'h'; unsigned __int64
0x18015e541  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18015e546  mov     rdi, rax
0x18015e549  test    rax, rax
0x18015e54c  jz      short loc_18015E5AB
0x18015e54e  mov     qword ptr [rax+28h], 0
0x18015e556  lea     rax, ??_7CSpAutoEvent@@6B@; const CSpAutoEvent::`vftable'
0x18015e55d  mov     [rdi+20h], rax
0x18015e561  mov     [rdi+30h], rax
0x18015e565  mov     qword ptr [rdi+38h], 0
0x18015e56d  mov     [rdi+40h], rax
0x18015e571  lea     rax, ??_7CSpAutoEvent@@6B@; const CSpAutoEvent::`vftable'
0x18015e578  mov     qword ptr [rdi+48h], 0
0x18015e580  mov     [rdi+50h], rax
0x18015e584  mov     qword ptr [rdi+58h], 0
0x18015e58c  mov     dword ptr [rdi], 0
0x18015e592  mov     qword ptr [rdi+18h], 0
0x18015e59a  mov     qword ptr [rdi+8], 0
0x18015e5a2  mov     dword ptr [rdi+14h], 0
0x18015e5a9  jmp     short loc_18015E5AD
0x18015e5ab  xor     edi, edi
0x18015e5ad  mov     rcx, [rbp+40h]
0x18015e5b1  add     rcx, 10h; lpCriticalSection
0x18015e5b5  call    cs:__imp_LeaveCriticalSection
0x18015e5bb  test    rdi, rdi
0x18015e5be  jnz     short loc_18015E5C7
0x18015e5c0  mov     ebx, 8007000Eh
0x18015e5c5  jmp     short loc_18015E5E9
0x18015e5c7  mov     r8, r12; HWND *
0x18015e5ca  mov     rdx, rbp; struct CSpThreadControl *
0x18015e5cd  mov     rcx, rdi; this
0x18015e5d0  call    ?Init@CSpThreadTask@@QEAAJPEAVCSpThreadControl@@PEAPEAUHWND__@@@Z; CSpThreadTask::Init(CSpThreadControl *,HWND__ * *)
0x18015e5d5  mov     ebx, eax
0x18015e5d7  test    eax, eax
0x18015e5d9  jns     short loc_18015E5E5
0x18015e5db  mov     rcx, rdi; this
0x18015e5de  call    ??_GCSpThreadTask@@QEAAPEAXI@Z; CSpThreadTask::`scalar deleting destructor'(uint)
0x18015e5e3  jmp     short loc_18015E5E9
0x18015e5e5  mov     [rbp+48h], rdi
0x18015e5e9  mov     rcx, r15; lpCriticalSection
0x18015e5ec  call    cs:__imp_LeaveCriticalSection
0x18015e5f2  mov     eax, ebx
0x18015e5f4  add     rsp, 20h
0x18015e5f8  pop     r15
0x18015e5fa  pop     r14
0x18015e5fc  pop     r12
0x18015e5fe  pop     rdi
0x18015e5ff  pop     rsi
0x18015e600  pop     rbp
0x18015e601  pop     rbx
0x18015e602  retn
```
