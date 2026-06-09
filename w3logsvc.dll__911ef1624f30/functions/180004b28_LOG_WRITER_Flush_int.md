# LOG_WRITER::Flush(int)

- ea: `0x180004b28`
- end: `0x180004be4`
- name: `?Flush@LOG_WRITER@@AEAAJH@Z`
- size: `188`
- prototype: `__int64 __fastcall(LOG_WRITER *__hidden this, int)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800022a4`
- `0x180005bd4`
- `0x180006148`
- `0x180008120`

## callees

- `0x180004b28`
- `0x180004bec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004bc4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004bc4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004b56`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004b56`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180004b46`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180004b46`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180004bd1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180004bd1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004ba4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004ba4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180004b88`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180004b88`

## pseudocode

```c
__int64 __fastcall LOG_WRITER::Flush(LOG_WRITER *this, int a2)
{
  RTL_SRWLOCK *v2; // rdi
  unsigned int v5; // ebp
  _WORD *v6; // rdx

  v2 = (RTL_SRWLOCK *)((char *)this + 720);
  if ( !a2 )
    AcquireSRWLockShared(v2);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 17);
  v5 = LOG_WRITER::Flush(this, (LOG_WRITER *)((char *)this + 128), 1, 0);
  if ( !v5 )
    *((_DWORD *)this + 155) = 0;
  if ( *((_QWORD *)this + 79) != -1 && GetTickCount64() - *((_QWORD *)this + 83) >= 0x7530 )
  {
    CloseHandle(*((HANDLE *)this + 79));
    v6 = (_WORD *)*((_QWORD *)this + 13);
    *((_QWORD *)this + 79) = -1;
    *v6 = 0;
    *((_DWORD *)this + 30) = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 17);
  if ( !a2 )
    ReleaseSRWLockShared(v2);
  return v5;
}

```

## disassembly

```asm
0x180004b28  push    rbx
0x180004b2a  push    rbp
0x180004b2b  push    rsi
0x180004b2c  push    rdi
0x180004b2d  push    r14
0x180004b2f  sub     rsp, 20h
0x180004b33  lea     rdi, [rcx+2D0h]
0x180004b3a  mov     esi, edx
0x180004b3c  mov     rbx, rcx
0x180004b3f  test    edx, edx
0x180004b41  jnz     short loc_180004B4C
0x180004b43  mov     rcx, rdi; SRWLock
0x180004b46  call    cs:__imp_AcquireSRWLockShared
0x180004b4c  lea     r14, [rbx+2A8h]
0x180004b53  mov     rcx, r14; lpCriticalSection
0x180004b56  call    cs:__imp_EnterCriticalSection
0x180004b5c  xor     r9d, r9d; void *
0x180004b5f  lea     rdx, [rbx+80h]; struct STRA *
0x180004b66  mov     rcx, rbx; this
0x180004b69  lea     r8d, [r9+1]; int
0x180004b6d  call    ?Flush@LOG_WRITER@@AEAAJPEAVSTRA@@HPEAX@Z; LOG_WRITER::Flush(STRA *,int,void *)
0x180004b72  mov     ebp, eax
0x180004b74  test    eax, eax
0x180004b76  jnz     short loc_180004B7E
0x180004b78  mov     [rbx+26Ch], eax
0x180004b7e  cmp     qword ptr [rbx+278h], 0FFFFFFFFFFFFFFFFh
0x180004b86  jz      short loc_180004BC1
0x180004b88  call    cs:__imp_GetTickCount64
0x180004b8e  sub     rax, [rbx+298h]
0x180004b95  cmp     rax, 7530h
0x180004b9b  jb      short loc_180004BC1
0x180004b9d  mov     rcx, [rbx+278h]; hObject
0x180004ba4  call    cs:__imp_CloseHandle
0x180004baa  mov     rdx, [rbx+68h]
0x180004bae  xor     eax, eax
0x180004bb0  mov     qword ptr [rbx+278h], 0FFFFFFFFFFFFFFFFh
0x180004bbb  mov     [rdx], ax
0x180004bbe  mov     [rbx+78h], eax
0x180004bc1  mov     rcx, r14; lpCriticalSection
0x180004bc4  call    cs:__imp_LeaveCriticalSection
0x180004bca  test    esi, esi
0x180004bcc  jnz     short loc_180004BD7
0x180004bce  mov     rcx, rdi; SRWLock
0x180004bd1  call    cs:__imp_ReleaseSRWLockShared
0x180004bd7  mov     eax, ebp
0x180004bd9  add     rsp, 20h
0x180004bdd  pop     r14
0x180004bdf  pop     rdi
0x180004be0  pop     rsi
0x180004be1  pop     rbp
0x180004be2  pop     rbx
0x180004be3  retn
```
