# CAsyncIo::PendWrite(void *,unsigned __int64,uchar *,ulong,unsigned __int64,CIoCompletion *)

- ea: `0x18007abb8`
- end: `0x18007ad2d`
- name: `?PendWrite@CAsyncIo@@QEAAKPEAX_KPEAEK1PEAVCIoCompletion@@@Z`
- size: `373`
- prototype: `unsigned int __usercall@<eax>(CAsyncIo *__hidden this@<rcx>, HANDLE hFile@<rdx>, unsigned __int64@<r8>, unsigned __int8 *@<r9>, DWORD nNumberOfBytesToWrite, unsigned __int64, struct CIoCompletion *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800787f8`
- `0x18007935c`

## callees

- `0x180001c00`
- `0x180078f4c`
- `0x180079634`
- `0x18007abb8`
- `0x18007b250`
- `0x18007b5a0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18007ac75`
- `KERNEL32!LeaveCriticalSection` at `0x18007ace3`
- `KERNEL32!LeaveCriticalSection` at `0x18007ac75`
- `KERNEL32!LeaveCriticalSection` at `0x18007ace3`
- `KERNEL32!EnterCriticalSection` at `0x18007ac43`
- `KERNEL32!EnterCriticalSection` at `0x18007acba`
- `KERNEL32!EnterCriticalSection` at `0x18007ac43`
- `KERNEL32!EnterCriticalSection` at `0x18007acba`
- `KERNEL32!GetLastError` at `0x18007aca8`
- `KERNEL32!GetLastError` at `0x18007aca8`
- `KERNEL32!WriteFile` at `0x18007ac9a`
- `KERNEL32!WriteFile` at `0x18007ac9a`

## pseudocode

```c
__int64 __fastcall CAsyncIo::PendWrite(
        CAsyncIo *this,
        HANDLE hFile,
        __int64 a3,
        unsigned __int8 *a4,
        DWORD nNumberOfBytesToWrite,
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
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-38h] BYREF

  NumberOfBytesWritten = 0;
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
      if ( WriteFile(hFile, a4, nNumberOfBytesToWrite, &NumberOfBytesWritten, lpOverlapped) )
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
0x18007abb8  mov     [rsp+arg_10], rbx
0x18007abbd  push    rbp
0x18007abbe  push    rsi
0x18007abbf  push    rdi
0x18007abc0  push    r14
0x18007abc2  push    r15
0x18007abc4  sub     rsp, 40h
0x18007abc8  mov     rax, cs:__security_cookie
0x18007abcf  xor     rax, rsp
0x18007abd2  mov     [rsp+68h+var_30], rax
0x18007abd7  mov     r15, r9
0x18007abda  mov     [rsp+68h+NumberOfBytesWritten], 0
0x18007abe2  mov     rbp, r8
0x18007abe5  mov     r14, rdx
0x18007abe8  mov     rsi, rcx
0x18007abeb  call    ?ConfirmCompletionThreadRunning_@CAsyncIo@@AEAAKXZ; CAsyncIo::ConfirmCompletionThreadRunning_(void)
0x18007abf0  mov     edi, eax
0x18007abf2  test    eax, eax
0x18007abf4  jnz     loc_18007AD0A
0x18007abfa  mov     rcx, rsi
0x18007abfd  call    ?Get@?$TStructPool@UASYNC_IO_CONTEXT@CAsyncIo@@$0DC@@@QEAAPEAUASYNC_IO_CONTEXT@CAsyncIo@@XZ; TStructPool<CAsyncIo::ASYNC_IO_CONTEXT,50>::Get(void)
0x18007ac02  mov     rbx, rax
0x18007ac05  test    rax, rax
0x18007ac08  jz      loc_18007AD05
0x18007ac0e  mov     rcx, [rsp+68h+arg_28]
0x18007ac16  lea     rdi, [rax+10h]
0x18007ac1a  mov     [rdi+10h], ebp
0x18007ac1d  mov     [rax+30h], rcx
0x18007ac21  mov     rcx, [rsp+68h+arg_30]
0x18007ac29  shr     rbp, 20h
0x18007ac2d  mov     [rax+24h], ebp
0x18007ac30  lea     rbp, [rsi+60h]
0x18007ac34  mov     [rax+38h], rcx
0x18007ac38  mov     rcx, rbp; lpCriticalSection
0x18007ac3b  mov     qword ptr [rax+28h], 0
0x18007ac43  call    cs:__imp_EnterCriticalSection
0x18007ac49  lea     rax, [rsi+90h]
0x18007ac50  mov     rcx, [rax]
0x18007ac53  cmp     [rcx+8], rax
0x18007ac57  jnz     loc_18007ACFE
0x18007ac5d  mov     [rbx], rcx
0x18007ac60  mov     [rbx+8], rax
0x18007ac64  mov     [rcx+8], rbx
0x18007ac68  mov     [rax], rbx
0x18007ac6b  lock inc dword ptr [rsi+88h]
0x18007ac72  mov     rcx, rbp; lpCriticalSection
0x18007ac75  call    cs:__imp_LeaveCriticalSection
0x18007ac7b  lock inc dword ptr [rsi+0B8h]
0x18007ac82  mov     r8d, [rsp+68h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x18007ac8a  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18007ac8f  mov     rdx, r15; lpBuffer
0x18007ac92  mov     [rsp+68h+lpOverlapped], rdi; lpOverlapped
0x18007ac97  mov     rcx, r14; hFile
0x18007ac9a  call    cs:__imp_WriteFile
0x18007aca0  test    eax, eax
0x18007aca2  jz      short loc_18007ACA8
0x18007aca4  xor     edi, edi
0x18007aca6  jmp     short loc_18007AD0A
0x18007aca8  call    cs:__imp_GetLastError
0x18007acae  mov     edi, eax
0x18007acb0  cmp     eax, 3E5h
0x18007acb5  jz      short loc_18007AD0A
0x18007acb7  mov     rcx, rbp; lpCriticalSection
0x18007acba  call    cs:__imp_EnterCriticalSection
0x18007acc0  mov     rdx, [rbx]
0x18007acc3  cmp     [rdx+8], rbx
0x18007acc7  jnz     short loc_18007ACFE
0x18007acc9  mov     rax, [rbx+8]
0x18007accd  cmp     [rax], rbx
0x18007acd0  jnz     short loc_18007ACFE
0x18007acd2  mov     [rax], rdx
0x18007acd5  mov     rcx, rbp; lpCriticalSection
0x18007acd8  mov     [rdx+8], rax
0x18007acdc  lock dec dword ptr [rsi+88h]
0x18007ace3  call    cs:__imp_LeaveCriticalSection
0x18007ace9  mov     rdx, rbx
0x18007acec  mov     rcx, rsi
0x18007acef  call    ?Recycle@?$TStructPool@UASYNC_IO_CONTEXT@CAsyncIo@@$0DC@@@QEAAXPEAUASYNC_IO_CONTEXT@CAsyncIo@@@Z; TStructPool<CAsyncIo::ASYNC_IO_CONTEXT,50>::Recycle(CAsyncIo::ASYNC_IO_CONTEXT *)
0x18007acf4  mov     rcx, rsi; this
0x18007acf7  call    ?Release@CAsyncIo@@QEAAJXZ; CAsyncIo::Release(void)
0x18007acfc  jmp     short loc_18007AD0A
0x18007acfe  mov     ecx, 3
0x18007ad03  int     29h; Win8: RtlFailFast(ecx)
0x18007ad05  mov     edi, 8
0x18007ad0a  mov     eax, edi
0x18007ad0c  mov     rcx, [rsp+68h+var_30]
0x18007ad11  xor     rcx, rsp; StackCookie
0x18007ad14  call    __security_check_cookie
0x18007ad19  mov     rbx, [rsp+68h+arg_10]
0x18007ad21  add     rsp, 40h
0x18007ad25  pop     r15
0x18007ad27  pop     r14
0x18007ad29  pop     rdi
0x18007ad2a  pop     rsi
0x18007ad2b  pop     rbp
0x18007ad2c  retn
```
