# p9fs::CoroutineIoIssuer::Issue__lambda_3a1c3e959ec17d797f0bed3efcff20ab___

- ea: `0x180028c38`
- end: `0x180028d17`
- name: `p9fs::CoroutineIoIssuer::Issue__lambda_3a1c3e959ec17d797f0bed3efcff20ab___`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180029be0`

## callees

- `0x180004120`
- `0x180028c38`
- `0x1800294ec`
- `0x180029548`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028cd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028cd1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180028cbf`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180028cbf`

## pseudocode

```c
__int64 *__fastcall p9fs::CoroutineIoIssuer::Issue__lambda_3a1c3e959ec17d797f0bed3efcff20ab___(
        p9fs::CoroutineIoIssuer *a1,
        __int64 *a2,
        __int64 a3,
        struct p9fs::CancelToken *a4,
        __int64 a5)
{
  void *v9; // r10
  DWORD v10; // ecx
  DWORD LastError; // eax
  DWORD NumberOfBytesWritten[2]; // [rsp+40h] [rbp-38h] BYREF

  if ( (unsigned __int8)p9fs::CoroutineIoIssuer::PreIssue(a1, (struct p9fs::CoroutineIoOperation *)a3, a4) )
  {
    v9 = (void *)*((_QWORD *)a1 + 1);
    *(_QWORD *)(a3 + 32) = **(_QWORD **)a5;
    NumberOfBytesWritten[0] = 0;
    if ( WriteFile(
           v9,
           *(LPCVOID *)(*(_QWORD *)(a5 + 8) + 8LL),
           **(_DWORD **)(a5 + 8),
           NumberOfBytesWritten,
           (LPOVERLAPPED)(a3 + 16)) )
    {
      v10 = NumberOfBytesWritten[0];
      LastError = 0;
    }
    else
    {
      LastError = GetLastError();
      v10 = 0;
    }
    *(_QWORD *)NumberOfBytesWritten = __PAIR64__(v10, LastError);
    p9fs::CoroutineIoIssuer::PostIssue((__int64)a1, a3, (__int64)a4, __PAIR64__(v10, LastError));
  }
  *a2 = a3;
  a2[1] = (__int64)a4;
  return a2;
}

```

## disassembly

```asm
0x180028c38  push    rbx
0x180028c3a  push    rsi
0x180028c3b  push    rdi
0x180028c3c  push    r14
0x180028c3e  push    r15
0x180028c40  sub     rsp, 50h
0x180028c44  mov     rax, cs:__security_cookie
0x180028c4b  xor     rax, rsp
0x180028c4e  mov     [rsp+78h+var_30], rax
0x180028c53  mov     rsi, r9
0x180028c56  mov     rdi, r8
0x180028c59  mov     rbx, rdx
0x180028c5c  mov     r14, rcx
0x180028c5f  mov     r15, [rsp+78h+arg_20]
0x180028c67  mov     [rsp+78h+var_40], rcx
0x180028c6c  mov     [rsp+78h+var_48], r9
0x180028c71  mov     r8, r9; struct p9fs::CancelToken *
0x180028c74  mov     rdx, rdi; struct p9fs::CoroutineIoOperation *
0x180028c77  call    ?PreIssue@CoroutineIoIssuer@p9fs@@AEAA_NAEAUCoroutineIoOperation@2@AEAVCancelToken@2@@Z; p9fs::CoroutineIoIssuer::PreIssue(p9fs::CoroutineIoOperation &,p9fs::CancelToken &)
0x180028c7c  test    al, al
0x180028c7e  jz      short loc_180028CF4
0x180028c80  lea     r8, [rdi+10h]
0x180028c84  mov     r10, [r14+8]
0x180028c88  mov     rax, [r15]
0x180028c8b  mov     ecx, [rax]
0x180028c8d  mov     [r8+10h], ecx
0x180028c91  mov     rax, [r15]
0x180028c94  mov     rcx, [rax]
0x180028c97  shr     rcx, 20h
0x180028c9b  mov     [r8+14h], ecx
0x180028c9f  mov     [rsp+78h+NumberOfBytesWritten], 0
0x180028ca7  mov     rdx, [r15+8]
0x180028cab  mov     [rsp+78h+lpOverlapped], r8; lpOverlapped
0x180028cb0  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180028cb5  mov     r8d, [rdx]; nNumberOfBytesToWrite
0x180028cb8  mov     rdx, [rdx+8]; lpBuffer
0x180028cbc  mov     rcx, r10; hFile
0x180028cbf  call    cs:__imp_WriteFile
0x180028cc5  test    eax, eax
0x180028cc7  jz      short loc_180028CD1
0x180028cc9  mov     ecx, [rsp+78h+NumberOfBytesWritten]
0x180028ccd  xor     eax, eax
0x180028ccf  jmp     short loc_180028CD9
0x180028cd1  call    cs:__imp_GetLastError
0x180028cd7  xor     ecx, ecx
0x180028cd9  mov     [rsp+78h+NumberOfBytesWritten], eax
0x180028cdd  mov     [rsp+78h+NumberOfBytesWritten+4], ecx
0x180028ce1  mov     r9, qword ptr [rsp+78h+NumberOfBytesWritten]
0x180028ce6  mov     r8, rsi
0x180028ce9  mov     rdx, rdi
0x180028cec  mov     rcx, r14
0x180028cef  call    ?PostIssue@CoroutineIoIssuer@p9fs@@AEAAXAEAUCoroutineIoOperation@2@AEAVCancelToken@2@UIoResult@2@@Z; p9fs::CoroutineIoIssuer::PostIssue(p9fs::CoroutineIoOperation &,p9fs::CancelToken &,p9fs::IoResult)
0x180028cf4  mov     [rbx], rdi
0x180028cf7  mov     [rbx+8], rsi
0x180028cfb  mov     rax, rbx
0x180028cfe  mov     rcx, [rsp+78h+var_30]
0x180028d03  xor     rcx, rsp; StackCookie
0x180028d06  call    __security_check_cookie
0x180028d0b  add     rsp, 50h
0x180028d0f  pop     r15
0x180028d11  pop     r14
0x180028d13  pop     rdi
0x180028d14  pop     rsi
0x180028d15  pop     rbx
0x180028d16  retn
```
