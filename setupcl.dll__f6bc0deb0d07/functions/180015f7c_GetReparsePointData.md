# GetReparsePointData

- ea: `0x180015f7c`
- end: `0x180016080`
- name: `GetReparsePointData`
- size: `260`
- prototype: `__int64 __fastcall(HANDLE Handle, _QWORD *, _DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, loader_planting`

## callers

- `0x180016118`

## callees

- `0x180015f7c`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180015fb5`
- `ntdll!RtlAllocateHeap` at `0x180015fb5`
- `ntdll!RtlFreeHeap` at `0x18001606b`
- `ntdll!RtlFreeHeap` at `0x18001606b`
- `ntdll!NtFsControlFile` at `0x180016008`
- `ntdll!NtFsControlFile` at `0x180016008`
- `ntdll!NtWaitForSingleObject` at `0x18001601f`
- `ntdll!NtWaitForSingleObject` at `0x18001601f`

## pseudocode

```c
__int64 __fastcall GetReparsePointData(HANDLE Handle, _QWORD *a2, _DWORD *a3, _DWORD *a4)
{
  PVOID OutputBuffer; // rdi
  NTSTATUS Status; // ebx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-48h] BYREF

  IoStatusBlock = 0;
  OutputBuffer = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x4000u);
  if ( !OutputBuffer )
    return (unsigned int)-1073741801;
  Status = NtFsControlFile(Handle, 0, 0, 0, &IoStatusBlock, 0x900A8u, 0, 0, OutputBuffer, 0x4000u);
  if ( Status == 259 )
  {
    Status = NtWaitForSingleObject(Handle, 0, 0);
    if ( Status < 0 )
    {
LABEL_14:
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, OutputBuffer);
      return (unsigned int)Status;
    }
    Status = IoStatusBlock.Status;
  }
  if ( Status < 0 )
    goto LABEL_14;
  if ( a2 )
  {
    *a2 = OutputBuffer;
    OutputBuffer = 0;
  }
  if ( a3 )
    *a3 = IoStatusBlock.Information;
  if ( a4 )
    *a4 = 0x4000;
  if ( OutputBuffer )
    goto LABEL_14;
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x180015f7c  push    rbx
0x180015f7e  push    rbp
0x180015f7f  push    rsi
0x180015f80  push    rdi
0x180015f81  push    r14
0x180015f83  push    r15
0x180015f85  sub     rsp, 68h
0x180015f89  mov     rbp, rcx
0x180015f8c  xorps   xmm0, xmm0
0x180015f8f  movups  xmmword ptr [rsp+98h+var_48], xmm0
0x180015f94  mov     rcx, gs:60h
0x180015f9d  mov     r14, r8
0x180015fa0  mov     r15, rdx
0x180015fa3  mov     r8d, 4000h; Size
0x180015fa9  mov     edx, 8; Flags
0x180015fae  mov     rsi, r9
0x180015fb1  mov     rcx, [rcx+30h]; HeapHandle
0x180015fb5  call    cs:__imp_RtlAllocateHeap
0x180015fbb  mov     rdi, rax
0x180015fbe  test    rax, rax
0x180015fc1  jnz     short loc_180015FCD
0x180015fc3  mov     ebx, 0C0000017h
0x180015fc8  jmp     loc_180016071
0x180015fcd  mov     [rsp+98h+OutputBufferLength], 4000h; OutputBufferLength
0x180015fd5  lea     rax, [rsp+98h+var_48]
0x180015fda  mov     [rsp+98h+OutputBuffer], rdi; OutputBuffer
0x180015fdf  xor     r9d, r9d; ApcContext
0x180015fe2  mov     [rsp+98h+InputBufferLength], 0; InputBufferLength
0x180015fea  xor     r8d, r8d; ApcRoutine
0x180015fed  mov     [rsp+98h+InputBuffer], 0; InputBuffer
0x180015ff6  xor     edx, edx; Event
0x180015ff8  mov     [rsp+98h+FsControlCode], 900A8h; FsControlCode
0x180016000  mov     rcx, rbp; FileHandle
0x180016003  mov     [rsp+98h+IoStatusBlock], rax; IoStatusBlock
0x180016008  call    cs:__imp_NtFsControlFile
0x18001600e  mov     ebx, eax
0x180016010  cmp     eax, 103h
0x180016015  jnz     short loc_18001602F
0x180016017  xor     r8d, r8d; Timeout
0x18001601a  xor     edx, edx; Alertable
0x18001601c  mov     rcx, rbp; Handle
0x18001601f  call    cs:__imp_NtWaitForSingleObject
0x180016025  mov     ebx, eax
0x180016027  test    eax, eax
0x180016029  js      short loc_180016059
0x18001602b  mov     ebx, dword ptr [rsp+98h+var_48]
0x18001602f  test    ebx, ebx
0x180016031  js      short loc_180016059
0x180016033  test    r15, r15
0x180016036  jz      short loc_18001603D
0x180016038  mov     [r15], rdi
0x18001603b  xor     edi, edi
0x18001603d  test    r14, r14
0x180016040  jz      short loc_180016049
0x180016042  mov     eax, dword ptr [rsp+98h+var_48.Information]
0x180016046  mov     [r14], eax
0x180016049  test    rsi, rsi
0x18001604c  jz      short loc_180016054
0x18001604e  mov     dword ptr [rsi], 4000h
0x180016054  test    rdi, rdi
0x180016057  jz      short loc_180016071
0x180016059  mov     rcx, gs:60h
0x180016062  mov     r8, rdi; P
0x180016065  xor     edx, edx; Flags
0x180016067  mov     rcx, [rcx+30h]; HeapHandle
0x18001606b  call    cs:__imp_RtlFreeHeap
0x180016071  mov     eax, ebx
0x180016073  add     rsp, 68h
0x180016077  pop     r15
0x180016079  pop     r14
0x18001607b  pop     rdi
0x18001607c  pop     rsi
0x18001607d  pop     rbp
0x18001607e  pop     rbx
0x18001607f  retn
```
