# p9fs::CoroutineIoIssuer::Issue__lambda_f76cd16b2a21180c1c31377c6a014aa4___

- ea: `0x180028ef4`
- end: `0x180028fd3`
- name: `p9fs::CoroutineIoIssuer::Issue__lambda_f76cd16b2a21180c1c31377c6a014aa4___`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800295f0`

## callees

- `0x180004120`
- `0x180028ef4`
- `0x1800294ec`
- `0x180029548`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028f8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028f8d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180028f7b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180028f7b`

## pseudocode

```c
__int64 *__fastcall p9fs::CoroutineIoIssuer::Issue__lambda_f76cd16b2a21180c1c31377c6a014aa4___(
        p9fs::CoroutineIoIssuer *a1,
        __int64 *a2,
        __int64 a3,
        struct p9fs::CancelToken *a4,
        __int64 a5)
{
  void *v9; // r10
  DWORD v10; // ecx
  DWORD LastError; // eax
  DWORD NumberOfBytesRead[2]; // [rsp+40h] [rbp-38h] BYREF

  if ( (unsigned __int8)p9fs::CoroutineIoIssuer::PreIssue(a1, (struct p9fs::CoroutineIoOperation *)a3, a4) )
  {
    v9 = (void *)*((_QWORD *)a1 + 1);
    *(_QWORD *)(a3 + 32) = **(_QWORD **)a5;
    NumberOfBytesRead[0] = 0;
    if ( ReadFile(
           v9,
           *(LPVOID *)(*(_QWORD *)(a5 + 8) + 8LL),
           **(_DWORD **)(a5 + 8),
           NumberOfBytesRead,
           (LPOVERLAPPED)(a3 + 16)) )
    {
      v10 = NumberOfBytesRead[0];
      LastError = 0;
    }
    else
    {
      LastError = GetLastError();
      v10 = 0;
    }
    *(_QWORD *)NumberOfBytesRead = __PAIR64__(v10, LastError);
    p9fs::CoroutineIoIssuer::PostIssue((__int64)a1, a3, (__int64)a4, __PAIR64__(v10, LastError));
  }
  *a2 = a3;
  a2[1] = (__int64)a4;
  return a2;
}

```

## disassembly

```asm
0x180028ef4  push    rbx
0x180028ef6  push    rsi
0x180028ef7  push    rdi
0x180028ef8  push    r14
0x180028efa  push    r15
0x180028efc  sub     rsp, 50h
0x180028f00  mov     rax, cs:__security_cookie
0x180028f07  xor     rax, rsp
0x180028f0a  mov     [rsp+78h+var_30], rax
0x180028f0f  mov     rsi, r9
0x180028f12  mov     rdi, r8
0x180028f15  mov     rbx, rdx
0x180028f18  mov     r14, rcx
0x180028f1b  mov     r15, [rsp+78h+arg_20]
0x180028f23  mov     [rsp+78h+var_40], rcx
0x180028f28  mov     [rsp+78h+var_48], r9
0x180028f2d  mov     r8, r9; struct p9fs::CancelToken *
0x180028f30  mov     rdx, rdi; struct p9fs::CoroutineIoOperation *
0x180028f33  call    ?PreIssue@CoroutineIoIssuer@p9fs@@AEAA_NAEAUCoroutineIoOperation@2@AEAVCancelToken@2@@Z; p9fs::CoroutineIoIssuer::PreIssue(p9fs::CoroutineIoOperation &,p9fs::CancelToken &)
0x180028f38  test    al, al
0x180028f3a  jz      short loc_180028FB0
0x180028f3c  lea     r8, [rdi+10h]
0x180028f40  mov     r10, [r14+8]
0x180028f44  mov     rax, [r15]
0x180028f47  mov     ecx, [rax]
0x180028f49  mov     [r8+10h], ecx
0x180028f4d  mov     rax, [r15]
0x180028f50  mov     rcx, [rax]
0x180028f53  shr     rcx, 20h
0x180028f57  mov     [r8+14h], ecx
0x180028f5b  mov     [rsp+78h+NumberOfBytesRead], 0
0x180028f63  mov     rdx, [r15+8]
0x180028f67  mov     [rsp+78h+lpOverlapped], r8; lpOverlapped
0x180028f6c  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180028f71  mov     r8d, [rdx]; nNumberOfBytesToRead
0x180028f74  mov     rdx, [rdx+8]; lpBuffer
0x180028f78  mov     rcx, r10; hFile
0x180028f7b  call    cs:__imp_ReadFile
0x180028f81  test    eax, eax
0x180028f83  jz      short loc_180028F8D
0x180028f85  mov     ecx, [rsp+78h+NumberOfBytesRead]
0x180028f89  xor     eax, eax
0x180028f8b  jmp     short loc_180028F95
0x180028f8d  call    cs:__imp_GetLastError
0x180028f93  xor     ecx, ecx
0x180028f95  mov     [rsp+78h+NumberOfBytesRead], eax
0x180028f99  mov     [rsp+78h+NumberOfBytesRead+4], ecx
0x180028f9d  mov     r9, qword ptr [rsp+78h+NumberOfBytesRead]
0x180028fa2  mov     r8, rsi
0x180028fa5  mov     rdx, rdi
0x180028fa8  mov     rcx, r14
0x180028fab  call    ?PostIssue@CoroutineIoIssuer@p9fs@@AEAAXAEAUCoroutineIoOperation@2@AEAVCancelToken@2@UIoResult@2@@Z; p9fs::CoroutineIoIssuer::PostIssue(p9fs::CoroutineIoOperation &,p9fs::CancelToken &,p9fs::IoResult)
0x180028fb0  mov     [rbx], rdi
0x180028fb3  mov     [rbx+8], rsi
0x180028fb7  mov     rax, rbx
0x180028fba  mov     rcx, [rsp+78h+var_30]
0x180028fbf  xor     rcx, rsp; StackCookie
0x180028fc2  call    __security_check_cookie
0x180028fc7  add     rsp, 50h
0x180028fcb  pop     r15
0x180028fcd  pop     r14
0x180028fcf  pop     rdi
0x180028fd0  pop     rsi
0x180028fd1  pop     rbx
0x180028fd2  retn
```
