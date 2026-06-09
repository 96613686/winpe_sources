# CAsyncPipe::StartRead(CAsyncPipeOverlapped *)

- ea: `0x18000bb40`
- end: `0x18000bc82`
- name: `?StartRead@CAsyncPipe@@QEAAJPEAUCAsyncPipeOverlapped@@@Z`
- size: `322`
- prototype: `__int64 __fastcall(CAsyncPipe *this, struct _OVERLAPPED *Buffer)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000b870`
- `0x18001dc88`

## callees

- `0x18000b694`
- `0x18000baf0`
- `0x18000bb40`
- `0x18001e674`
- `0x18004d350`
- `0x180065b60`

## import_xrefs

- `KERNEL32!ReadFile` at `0x18000bbe4`
- `KERNEL32!ReadFile` at `0x18000bbe4`
- `KERNEL32!CloseHandle` at `0x18000bc3f`
- `KERNEL32!CloseHandle` at `0x18000bc3f`
- `KERNEL32!GetLastError` at `0x18000bbee`
- `KERNEL32!GetLastError` at `0x18000bbee`
- `KERNEL32!EnterCriticalSection` at `0x18000bb69`
- `KERNEL32!EnterCriticalSection` at `0x18000bb69`
- `KERNEL32!LeaveCriticalSection` at `0x18000bc61`
- `KERNEL32!LeaveCriticalSection` at `0x18000bc61`

## pseudocode

```c
__int64 __fastcall CAsyncPipe::StartRead(CAsyncPipe *this, struct _OVERLAPPED *Buffer)
{
  unsigned int LastWin32Error; // ebp
  void *v5; // r14
  DWORD LastError; // eax
  void *v7; // rcx

  LastWin32Error = 0;
  if ( *((_DWORD *)this + 16) )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v5 = (void *)*((_QWORD *)this + 2);
  if ( v5 == (void *)-1LL )
  {
    LastWin32Error = -2147467259;
  }
  else if ( Buffer || (Buffer = (struct _OVERLAPPED *)CAsyncPipe::GetBuffer(this, 0x7D00u)) != 0 )
  {
    LODWORD(Buffer[1].InternalHigh) = 0;
    Buffer[1].Offset = 0;
    HIDWORD(Buffer[1].InternalHigh) = 1;
    (*(void (__fastcall **)(CAsyncPipe *))(*(_QWORD *)this + 8LL))(this);
    if ( ReadFile(
           v5,
           (char *)&Buffer[2].InternalHigh + LODWORD(Buffer[1].hEvent),
           Buffer[1].OffsetHigh - LODWORD(Buffer[1].hEvent),
           (LPDWORD)&Buffer[1].16,
           Buffer)
      || (LastError = GetLastError(), LastError == 997)
      || LastError == 234 )
    {
      HIDWORD(Buffer[1].InternalHigh) = 0;
      goto LABEL_17;
    }
    HIDWORD(Buffer[1].InternalHigh) = 0;
    CAsyncPipe::ReturnBuffer(this, (struct CAsyncPipeOverlapped *)Buffer);
    (*(void (__fastcall **)(CAsyncPipe *))(*(_QWORD *)this + 16LL))(this);
    LastWin32Error = GetLastWin32Error();
    if ( !LastWin32Error )
      goto LABEL_17;
  }
  else
  {
    LastWin32Error = -2147024882;
  }
  v7 = (void *)*((_QWORD *)this + 2);
  if ( v7 != (void *)-1LL
    && v7 == (void *)_InterlockedCompareExchange64((volatile signed __int64 *)this + 2, -1, (signed __int64)v7) )
  {
    CloseHandle(v7);
  }
  *((_QWORD *)this + 2) = -1;
  CProcessEntry::OnProcessDied(*((CProcessEntry **)this + 9));
LABEL_17:
  if ( *((_DWORD *)this + 16) )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  return LastWin32Error;
}

```

## disassembly

```asm
0x18000bb40  mov     [rsp+arg_8], rbx
0x18000bb45  mov     [rsp+arg_10], rbp
0x18000bb4a  mov     [rsp+arg_18], rsi
0x18000bb4f  push    rdi
0x18000bb50  push    r12
0x18000bb52  push    r14
0x18000bb54  sub     rsp, 30h
0x18000bb58  xor     ebp, ebp
0x18000bb5a  mov     rsi, rdx
0x18000bb5d  mov     rdi, rcx
0x18000bb60  cmp     [rcx+40h], ebp
0x18000bb63  jz      short loc_18000BB6F
0x18000bb65  add     rcx, 18h; lpCriticalSection
0x18000bb69  call    cs:__imp_EnterCriticalSection
0x18000bb6f  mov     r14, [rdi+10h]
0x18000bb73  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000bb77  cmp     r14, r12
0x18000bb7a  jnz     short loc_18000BB86
0x18000bb7c  mov     ebp, 80004005h
0x18000bb81  jmp     loc_18000BC2B
0x18000bb86  test    rsi, rsi
0x18000bb89  jnz     short loc_18000BBAA
0x18000bb8b  mov     edx, 7D00h; unsigned int
0x18000bb90  mov     rcx, rdi; this
0x18000bb93  call    ?GetBuffer@CAsyncPipe@@QEAAPEAUCAsyncPipeOverlapped@@K@Z; CAsyncPipe::GetBuffer(ulong)
0x18000bb98  mov     rsi, rax
0x18000bb9b  test    rax, rax
0x18000bb9e  jnz     short loc_18000BBAA
0x18000bba0  mov     ebp, 8007000Eh
0x18000bba5  jmp     loc_18000BC2B
0x18000bbaa  and     [rsi+28h], ebp
0x18000bbad  mov     rcx, rdi
0x18000bbb0  and     [rsi+30h], ebp
0x18000bbb3  mov     dword ptr [rsi+2Ch], 1
0x18000bbba  mov     rax, [rdi]
0x18000bbbd  mov     rax, [rax+8]
0x18000bbc1  call    cs:__guard_dispatch_icall_fptr
0x18000bbc7  mov     eax, [rsi+38h]
0x18000bbca  lea     r9, [rsi+30h]; lpNumberOfBytesRead
0x18000bbce  mov     r8d, [rsi+34h]
0x18000bbd2  mov     rcx, r14; hFile
0x18000bbd5  sub     r8d, eax; nNumberOfBytesToRead
0x18000bbd8  mov     [rsp+48h+lpOverlapped], rsi; lpOverlapped
0x18000bbdd  lea     rdx, [rax+48h]
0x18000bbe1  add     rdx, rsi; lpBuffer
0x18000bbe4  call    cs:__imp_ReadFile
0x18000bbea  test    eax, eax
0x18000bbec  jnz     short loc_18000BC54
0x18000bbee  call    cs:__imp_GetLastError
0x18000bbf4  cmp     eax, 3E5h
0x18000bbf9  jz      short loc_18000BC54
0x18000bbfb  cmp     eax, 0EAh
0x18000bc00  jz      short loc_18000BC54
0x18000bc02  and     [rsi+2Ch], ebp
0x18000bc05  mov     rdx, rsi; struct CAsyncPipeOverlapped *
0x18000bc08  mov     rcx, rdi; this
0x18000bc0b  call    ?ReturnBuffer@CAsyncPipe@@QEAAXPEAUCAsyncPipeOverlapped@@@Z; CAsyncPipe::ReturnBuffer(CAsyncPipeOverlapped *)
0x18000bc10  mov     rax, [rdi]
0x18000bc13  mov     rcx, rdi
0x18000bc16  mov     rax, [rax+10h]
0x18000bc1a  call    cs:__guard_dispatch_icall_fptr
0x18000bc20  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18000bc25  mov     ebp, eax
0x18000bc27  test    eax, eax
0x18000bc29  jz      short loc_18000BC57
0x18000bc2b  mov     rcx, [rdi+10h]; hObject
0x18000bc2f  cmp     rcx, r12
0x18000bc32  jz      short loc_18000BC45
0x18000bc34  mov     rax, rcx
0x18000bc37  lock cmpxchg [rdi+10h], r12
0x18000bc3d  jnz     short loc_18000BC45
0x18000bc3f  call    cs:__imp_CloseHandle
0x18000bc45  mov     [rdi+10h], r12
0x18000bc49  mov     rcx, [rdi+48h]; this
0x18000bc4d  call    ?OnProcessDied@CProcessEntry@@QEAAXXZ; CProcessEntry::OnProcessDied(void)
0x18000bc52  jmp     short loc_18000BC57
0x18000bc54  and     [rsi+2Ch], ebp
0x18000bc57  cmp     dword ptr [rdi+40h], 0
0x18000bc5b  jz      short loc_18000BC67
0x18000bc5d  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000bc61  call    cs:__imp_LeaveCriticalSection
0x18000bc67  mov     rbx, [rsp+48h+arg_8]
0x18000bc6c  mov     eax, ebp
0x18000bc6e  mov     rbp, [rsp+48h+arg_10]
0x18000bc73  mov     rsi, [rsp+48h+arg_18]
0x18000bc78  add     rsp, 30h
0x18000bc7c  pop     r14
0x18000bc7e  pop     r12
0x18000bc80  pop     rdi
0x18000bc81  retn
```
