# CAsyncIo::PendRead(void *,unsigned __int64,uchar *,ulong,unsigned __int64,CIoCompletion *)

- ea: `0x18007a89c`
- end: `0x18007aa11`
- name: `?PendRead@CAsyncIo@@QEAAKPEAX_KPEAEK1PEAVCIoCompletion@@@Z`
- size: `373`
- prototype: `unsigned int __usercall@<eax>(CAsyncIo *__hidden this@<rcx>, HANDLE hFile@<rdx>, unsigned __int64@<r8>, unsigned __int8 *@<r9>, DWORD nNumberOfBytesToRead, unsigned __int64, struct CIoCompletion *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18007aa18`

## callees

- `0x180001c00`
- `0x180078f4c`
- `0x180079634`
- `0x18007a89c`
- `0x18007b250`
- `0x18007b5a0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18007a959`
- `KERNEL32!LeaveCriticalSection` at `0x18007a9c7`
- `KERNEL32!LeaveCriticalSection` at `0x18007a959`
- `KERNEL32!LeaveCriticalSection` at `0x18007a9c7`
- `KERNEL32!EnterCriticalSection` at `0x18007a927`
- `KERNEL32!EnterCriticalSection` at `0x18007a99e`
- `KERNEL32!EnterCriticalSection` at `0x18007a927`
- `KERNEL32!EnterCriticalSection` at `0x18007a99e`
- `KERNEL32!GetLastError` at `0x18007a98c`
- `KERNEL32!GetLastError` at `0x18007a98c`
- `KERNEL32!ReadFile` at `0x18007a97e`
- `KERNEL32!ReadFile` at `0x18007a97e`

## pseudocode

```c
__int64 __fastcall CAsyncIo::PendRead(
        CAsyncIo *this,
        HANDLE hFile,
        __int64 a3,
        unsigned __int8 *a4,
        DWORD nNumberOfBytesToRead,
        unsigned __int64 a6,
        struct CIoCompletion *a7)
{
  DWORD LastError; // edi
  __int64 v12; // rax
  _QWORD *v13; // rbx
  struct _OVERLAPPED *lpOverlapped; // rdi
  _QWORD *v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rdx
  _QWORD *v18; // rax
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-38h] BYREF

  NumberOfBytesRead = 0;
  LastError = CAsyncIo::ConfirmCompletionThreadRunning_(this);
  if ( !LastError )
  {
    v12 = TStructPool<CAsyncIo::ASYNC_IO_CONTEXT,50>::Get(this);
    v13 = (_QWORD *)v12;
    if ( !v12 )
      return 8;
    lpOverlapped = (struct _OVERLAPPED *)(v12 + 16);
    *(_DWORD *)(v12 + 32) = a3;
    *(_QWORD *)(v12 + 48) = a6;
    *(_DWORD *)(v12 + 36) = HIDWORD(a3);
    *(_QWORD *)(v12 + 56) = a7;
    *(_QWORD *)(v12 + 40) = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
    v15 = (_QWORD *)((char *)this + 144);
    v16 = *((_QWORD *)this + 18);
    if ( *(CAsyncIo **)(v16 + 8) == (CAsyncIo *)((char *)this + 144) )
    {
      *v13 = v16;
      v13[1] = v15;
      *(_QWORD *)(v16 + 8) = v13;
      *v15 = v13;
      _InterlockedIncrement((volatile signed __int32 *)this + 34);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
      _InterlockedIncrement((volatile signed __int32 *)this + 46);
      if ( ReadFile(hFile, a4, nNumberOfBytesToRead, &NumberOfBytesRead, lpOverlapped) )
        return 0;
      LastError = GetLastError();
      if ( LastError == 997 )
        return LastError;
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
      v17 = *v13;
      if ( *(_QWORD **)(*v13 + 8LL) == v13 )
      {
        v18 = (_QWORD *)v13[1];
        if ( (_QWORD *)*v18 == v13 )
        {
          *v18 = v17;
          *(_QWORD *)(v17 + 8) = v18;
          _InterlockedDecrement((volatile signed __int32 *)this + 34);
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
          TStructPool<CAsyncIo::ASYNC_IO_CONTEXT,50>::Recycle(this, v13);
          CAsyncIo::Release(this);
          return LastError;
        }
      }
    }
    __fastfail(3u);
  }
  return LastError;
}

```

## disassembly

```asm
0x18007a89c  mov     [rsp+arg_10], rbx
0x18007a8a1  push    rbp
0x18007a8a2  push    rsi
0x18007a8a3  push    rdi
0x18007a8a4  push    r14
0x18007a8a6  push    r15
0x18007a8a8  sub     rsp, 40h
0x18007a8ac  mov     rax, cs:__security_cookie
0x18007a8b3  xor     rax, rsp
0x18007a8b6  mov     [rsp+68h+var_30], rax
0x18007a8bb  mov     r15, r9
0x18007a8be  mov     [rsp+68h+NumberOfBytesRead], 0
0x18007a8c6  mov     rbp, r8
0x18007a8c9  mov     r14, rdx
0x18007a8cc  mov     rsi, rcx
0x18007a8cf  call    ?ConfirmCompletionThreadRunning_@CAsyncIo@@AEAAKXZ; CAsyncIo::ConfirmCompletionThreadRunning_(void)
0x18007a8d4  mov     edi, eax
0x18007a8d6  test    eax, eax
0x18007a8d8  jnz     loc_18007A9EE
0x18007a8de  mov     rcx, rsi
0x18007a8e1  call    ?Get@?$TStructPool@UASYNC_IO_CONTEXT@CAsyncIo@@$0DC@@@QEAAPEAUASYNC_IO_CONTEXT@CAsyncIo@@XZ; TStructPool<CAsyncIo::ASYNC_IO_CONTEXT,50>::Get(void)
0x18007a8e6  mov     rbx, rax
0x18007a8e9  test    rax, rax
0x18007a8ec  jz      loc_18007A9E9
0x18007a8f2  mov     rcx, [rsp+68h+arg_28]
0x18007a8fa  lea     rdi, [rax+10h]
0x18007a8fe  mov     [rdi+10h], ebp
0x18007a901  mov     [rax+30h], rcx
0x18007a905  mov     rcx, [rsp+68h+arg_30]
0x18007a90d  shr     rbp, 20h
0x18007a911  mov     [rax+24h], ebp
0x18007a914  lea     rbp, [rsi+60h]
0x18007a918  mov     [rax+38h], rcx
0x18007a91c  mov     rcx, rbp; lpCriticalSection
0x18007a91f  mov     qword ptr [rax+28h], 0
0x18007a927  call    cs:__imp_EnterCriticalSection
0x18007a92d  lea     rax, [rsi+90h]
0x18007a934  mov     rcx, [rax]
0x18007a937  cmp     [rcx+8], rax
0x18007a93b  jnz     loc_18007A9E2
0x18007a941  mov     [rbx], rcx
0x18007a944  mov     [rbx+8], rax
0x18007a948  mov     [rcx+8], rbx
0x18007a94c  mov     [rax], rbx
0x18007a94f  lock inc dword ptr [rsi+88h]
0x18007a956  mov     rcx, rbp; lpCriticalSection
0x18007a959  call    cs:__imp_LeaveCriticalSection
0x18007a95f  lock inc dword ptr [rsi+0B8h]
0x18007a966  mov     r8d, [rsp+68h+nNumberOfBytesToRead]; nNumberOfBytesToRead
0x18007a96e  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18007a973  mov     rdx, r15; lpBuffer
0x18007a976  mov     [rsp+68h+lpOverlapped], rdi; lpOverlapped
0x18007a97b  mov     rcx, r14; hFile
0x18007a97e  call    cs:__imp_ReadFile
0x18007a984  test    eax, eax
0x18007a986  jz      short loc_18007A98C
0x18007a988  xor     edi, edi
0x18007a98a  jmp     short loc_18007A9EE
0x18007a98c  call    cs:__imp_GetLastError
0x18007a992  mov     edi, eax
0x18007a994  cmp     eax, 3E5h
0x18007a999  jz      short loc_18007A9EE
0x18007a99b  mov     rcx, rbp; lpCriticalSection
0x18007a99e  call    cs:__imp_EnterCriticalSection
0x18007a9a4  mov     rdx, [rbx]
0x18007a9a7  cmp     [rdx+8], rbx
0x18007a9ab  jnz     short loc_18007A9E2
0x18007a9ad  mov     rax, [rbx+8]
0x18007a9b1  cmp     [rax], rbx
0x18007a9b4  jnz     short loc_18007A9E2
0x18007a9b6  mov     [rax], rdx
0x18007a9b9  mov     rcx, rbp; lpCriticalSection
0x18007a9bc  mov     [rdx+8], rax
0x18007a9c0  lock dec dword ptr [rsi+88h]
0x18007a9c7  call    cs:__imp_LeaveCriticalSection
0x18007a9cd  mov     rdx, rbx
0x18007a9d0  mov     rcx, rsi
0x18007a9d3  call    ?Recycle@?$TStructPool@UASYNC_IO_CONTEXT@CAsyncIo@@$0DC@@@QEAAXPEAUASYNC_IO_CONTEXT@CAsyncIo@@@Z; TStructPool<CAsyncIo::ASYNC_IO_CONTEXT,50>::Recycle(CAsyncIo::ASYNC_IO_CONTEXT *)
0x18007a9d8  mov     rcx, rsi; this
0x18007a9db  call    ?Release@CAsyncIo@@QEAAJXZ; CAsyncIo::Release(void)
0x18007a9e0  jmp     short loc_18007A9EE
0x18007a9e2  mov     ecx, 3
0x18007a9e7  int     29h; Win8: RtlFailFast(ecx)
0x18007a9e9  mov     edi, 8
0x18007a9ee  mov     eax, edi
0x18007a9f0  mov     rcx, [rsp+68h+var_30]
0x18007a9f5  xor     rcx, rsp; StackCookie
0x18007a9f8  call    __security_check_cookie
0x18007a9fd  mov     rbx, [rsp+68h+arg_10]
0x18007aa05  add     rsp, 40h
0x18007aa09  pop     r15
0x18007aa0b  pop     r14
0x18007aa0d  pop     rdi
0x18007aa0e  pop     rsi
0x18007aa0f  pop     rbp
0x18007aa10  retn
```
