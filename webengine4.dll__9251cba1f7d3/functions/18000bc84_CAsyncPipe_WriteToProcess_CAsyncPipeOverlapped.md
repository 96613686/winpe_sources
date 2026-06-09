# CAsyncPipe::WriteToProcess(CAsyncPipeOverlapped *)

- ea: `0x18000bc84`
- end: `0x18000bdb0`
- name: `?WriteToProcess@CAsyncPipe@@QEAAJPEAUCAsyncPipeOverlapped@@@Z`
- size: `300`
- prototype: `__int64 __fastcall(CAsyncPipe *__hidden this, struct CAsyncPipeOverlapped *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001f098`
- `0x18001f150`

## callees

- `0x18000baf0`
- `0x18000bc84`
- `0x18001e674`
- `0x18004d350`
- `0x180065b60`

## import_xrefs

- `KERNEL32!WriteFile` at `0x18000bd0a`
- `KERNEL32!WriteFile` at `0x18000bd0a`
- `KERNEL32!CloseHandle` at `0x18000bd5e`
- `KERNEL32!CloseHandle` at `0x18000bd5e`
- `KERNEL32!GetLastError` at `0x18000bd14`
- `KERNEL32!GetLastError` at `0x18000bd14`
- `KERNEL32!EnterCriticalSection` at `0x18000bca7`
- `KERNEL32!EnterCriticalSection` at `0x18000bca7`
- `KERNEL32!LeaveCriticalSection` at `0x18000bd95`
- `KERNEL32!LeaveCriticalSection` at `0x18000bd95`

## pseudocode

```c
__int64 __fastcall CAsyncPipe::WriteToProcess(CAsyncPipe *this, struct CAsyncPipeOverlapped *a2)
{
  unsigned int LastWin32Error; // esi
  void *v5; // rbp
  DWORD v6; // r8d
  void *v7; // rcx

  LastWin32Error = 0;
  if ( *((_DWORD *)this + 16) )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v5 = (void *)*((_QWORD *)this + 2);
  if ( !a2 )
  {
    LastWin32Error = -2147024809;
    goto LABEL_10;
  }
  if ( v5 == (void *)-1LL )
  {
    CAsyncPipe::ReturnBuffer(this, a2);
    LastWin32Error = -2147467259;
LABEL_10:
    v7 = (void *)*((_QWORD *)this + 2);
    if ( v7 != (void *)-1LL
      && v7 == (void *)_InterlockedCompareExchange64((volatile signed __int64 *)this + 2, -1, (signed __int64)v7) )
    {
      CloseHandle(v7);
    }
    *((_QWORD *)this + 2) = -1;
    CProcessEntry::OnProcessDied(*((CProcessEntry **)this + 9));
    goto LABEL_16;
  }
  *((_DWORD *)a2 + 10) = 1;
  (*(void (__fastcall **)(CAsyncPipe *))(*(_QWORD *)this + 8LL))(this);
  v6 = *((_DWORD *)a2 + 12);
  *((_DWORD *)a2 + 11) = 2;
  if ( !WriteFile(v5, (char *)a2 + 72, v6, (LPDWORD)a2 + 12, (LPOVERLAPPED)a2) && GetLastError() != 997 )
  {
    *((_DWORD *)a2 + 11) = 0;
    CAsyncPipe::ReturnBuffer(this, a2);
    (*(void (__fastcall **)(CAsyncPipe *))(*(_QWORD *)this + 16LL))(this);
    LastWin32Error = GetLastWin32Error();
    if ( !LastWin32Error )
      goto LABEL_16;
    goto LABEL_10;
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)a2 + 11, 0xFFFFFFFF) == 1 )
    CAsyncPipe::ReturnBuffer(this, a2);
LABEL_16:
  if ( *((_DWORD *)this + 16) )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  return LastWin32Error;
}

```

## disassembly

```asm
0x18000bc84  mov     [rsp+arg_8], rbx
0x18000bc89  mov     [rsp+arg_10], rbp
0x18000bc8e  push    rsi
0x18000bc8f  push    rdi
0x18000bc90  push    r14
0x18000bc92  sub     rsp, 30h
0x18000bc96  xor     esi, esi
0x18000bc98  mov     rdi, rdx
0x18000bc9b  mov     rbx, rcx
0x18000bc9e  cmp     [rcx+40h], esi
0x18000bca1  jz      short loc_18000BCAD
0x18000bca3  add     rcx, 18h; lpCriticalSection
0x18000bca7  call    cs:__imp_EnterCriticalSection
0x18000bcad  mov     rbp, [rbx+10h]
0x18000bcb1  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000bcb5  test    rdi, rdi
0x18000bcb8  jnz     short loc_18000BCC4
0x18000bcba  mov     esi, 80070057h
0x18000bcbf  jmp     loc_18000BD4A
0x18000bcc4  mov     rcx, rbx; this
0x18000bcc7  cmp     rbp, r14
0x18000bcca  jnz     short loc_18000BCDB
0x18000bccc  mov     rdx, rdi; struct CAsyncPipeOverlapped *
0x18000bccf  call    ?ReturnBuffer@CAsyncPipe@@QEAAXPEAUCAsyncPipeOverlapped@@@Z; CAsyncPipe::ReturnBuffer(CAsyncPipeOverlapped *)
0x18000bcd4  mov     esi, 80004005h
0x18000bcd9  jmp     short loc_18000BD4A
0x18000bcdb  mov     dword ptr [rdi+28h], 1
0x18000bce2  mov     rax, [rbx]
0x18000bce5  mov     rax, [rax+8]
0x18000bce9  call    cs:__guard_dispatch_icall_fptr
0x18000bcef  mov     r8d, [rdi+30h]; nNumberOfBytesToWrite
0x18000bcf3  lea     rdx, [rdi+48h]; lpBuffer
0x18000bcf7  lea     r9, [rdi+30h]; lpNumberOfBytesWritten
0x18000bcfb  mov     dword ptr [rdi+2Ch], 2
0x18000bd02  mov     rcx, rbp; hFile
0x18000bd05  mov     [rsp+48h+lpOverlapped], rdi; lpOverlapped
0x18000bd0a  call    cs:__imp_WriteFile
0x18000bd10  test    eax, eax
0x18000bd12  jnz     short loc_18000BD73
0x18000bd14  call    cs:__imp_GetLastError
0x18000bd1a  cmp     eax, 3E5h
0x18000bd1f  jz      short loc_18000BD73
0x18000bd21  and     [rdi+2Ch], esi
0x18000bd24  mov     rdx, rdi; struct CAsyncPipeOverlapped *
0x18000bd27  mov     rcx, rbx; this
0x18000bd2a  call    ?ReturnBuffer@CAsyncPipe@@QEAAXPEAUCAsyncPipeOverlapped@@@Z; CAsyncPipe::ReturnBuffer(CAsyncPipeOverlapped *)
0x18000bd2f  mov     rax, [rbx]
0x18000bd32  mov     rcx, rbx
0x18000bd35  mov     rax, [rax+10h]
0x18000bd39  call    cs:__guard_dispatch_icall_fptr
0x18000bd3f  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18000bd44  mov     esi, eax
0x18000bd46  test    eax, eax
0x18000bd48  jz      short loc_18000BD8B
0x18000bd4a  mov     rcx, [rbx+10h]; hObject
0x18000bd4e  cmp     rcx, r14
0x18000bd51  jz      short loc_18000BD64
0x18000bd53  mov     rax, rcx
0x18000bd56  lock cmpxchg [rbx+10h], r14
0x18000bd5c  jnz     short loc_18000BD64
0x18000bd5e  call    cs:__imp_CloseHandle
0x18000bd64  mov     [rbx+10h], r14
0x18000bd68  mov     rcx, [rbx+48h]; this
0x18000bd6c  call    ?OnProcessDied@CProcessEntry@@QEAAXXZ; CProcessEntry::OnProcessDied(void)
0x18000bd71  jmp     short loc_18000BD8B
0x18000bd73  mov     eax, r14d
0x18000bd76  lock xadd [rdi+2Ch], eax
0x18000bd7b  add     eax, r14d
0x18000bd7e  jnz     short loc_18000BD8B
0x18000bd80  mov     rdx, rdi; struct CAsyncPipeOverlapped *
0x18000bd83  mov     rcx, rbx; this
0x18000bd86  call    ?ReturnBuffer@CAsyncPipe@@QEAAXPEAUCAsyncPipeOverlapped@@@Z; CAsyncPipe::ReturnBuffer(CAsyncPipeOverlapped *)
0x18000bd8b  cmp     dword ptr [rbx+40h], 0
0x18000bd8f  jz      short loc_18000BD9B
0x18000bd91  lea     rcx, [rbx+18h]; lpCriticalSection
0x18000bd95  call    cs:__imp_LeaveCriticalSection
0x18000bd9b  mov     rbx, [rsp+48h+arg_8]
0x18000bda0  mov     eax, esi
0x18000bda2  mov     rbp, [rsp+48h+arg_10]
0x18000bda7  add     rsp, 30h
0x18000bdab  pop     r14
0x18000bdad  pop     rdi
0x18000bdae  pop     rsi
0x18000bdaf  retn
```
