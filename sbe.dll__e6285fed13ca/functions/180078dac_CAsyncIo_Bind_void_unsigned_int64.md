# CAsyncIo::Bind(void *,unsigned __int64)

- ea: `0x180078dac`
- end: `0x180078e4a`
- name: `?Bind@CAsyncIo@@QEAAKPEAX_K@Z`
- size: `158`
- prototype: `unsigned int __fastcall(ULONG_PTR CompletionKey, HANDLE FileHandle, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18007776c`
- `0x180077a4c`

## callees

- `0x180078dac`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180078e30`
- `KERNEL32!CloseHandle` at `0x180078e30`
- `KERNEL32!GetLastError` at `0x180078de7`
- `KERNEL32!GetLastError` at `0x180078e1b`
- `KERNEL32!GetLastError` at `0x180078de7`
- `KERNEL32!GetLastError` at `0x180078e1b`
- `KERNEL32!CreateIoCompletionPort` at `0x180078dd5`
- `KERNEL32!CreateIoCompletionPort` at `0x180078e05`
- `KERNEL32!CreateIoCompletionPort` at `0x180078dd5`
- `KERNEL32!CreateIoCompletionPort` at `0x180078e05`

## pseudocode

```c
__int64 __fastcall CAsyncIo::Bind(ULONG_PTR CompletionKey, HANDLE FileHandle)
{
  HANDLE IoCompletionPort; // rax
  void *v5; // rdx
  char *v6; // rdi
  DWORD LastError; // ebx

  if ( !*(_QWORD *)(CompletionKey + 176) )
  {
    IoCompletionPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, CompletionKey, 1u);
    *(_QWORD *)(CompletionKey + 176) = IoCompletionPort;
    if ( !IoCompletionPort )
      GetLastError();
  }
  v5 = *(void **)(CompletionKey + 176);
  if ( v5 )
  {
    v6 = (char *)CreateIoCompletionPort(FileHandle, v5, 0, 1u);
    if ( v6 == *(char **)(CompletionKey + 176) )
    {
      return 0;
    }
    else
    {
      LastError = GetLastError();
      if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v6);
    }
  }
  else
  {
    return 31;
  }
  return LastError;
}

```

## disassembly

```asm
0x180078dac  mov     [rsp+arg_0], rbx
0x180078db1  push    rdi
0x180078db2  sub     rsp, 20h
0x180078db6  cmp     qword ptr [rcx+0B0h], 0
0x180078dbe  mov     rdi, rdx
0x180078dc1  mov     rbx, rcx
0x180078dc4  jnz     short loc_180078DED
0x180078dc6  mov     r8, rcx; CompletionKey
0x180078dc9  mov     r9d, 1; NumberOfConcurrentThreads
0x180078dcf  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x180078dd3  xor     edx, edx; ExistingCompletionPort
0x180078dd5  call    cs:__imp_CreateIoCompletionPort
0x180078ddb  mov     [rbx+0B0h], rax
0x180078de2  test    rax, rax
0x180078de5  jnz     short loc_180078DED
0x180078de7  call    cs:__imp_GetLastError
0x180078ded  mov     rdx, [rbx+0B0h]; ExistingCompletionPort
0x180078df4  test    rdx, rdx
0x180078df7  jz      short loc_180078E38
0x180078df9  mov     r9d, 1; NumberOfConcurrentThreads
0x180078dff  xor     r8d, r8d; CompletionKey
0x180078e02  mov     rcx, rdi; FileHandle
0x180078e05  call    cs:__imp_CreateIoCompletionPort
0x180078e0b  mov     rdi, rax
0x180078e0e  cmp     rax, [rbx+0B0h]
0x180078e15  jnz     short loc_180078E1B
0x180078e17  xor     ebx, ebx
0x180078e19  jmp     short loc_180078E3D
0x180078e1b  call    cs:__imp_GetLastError
0x180078e21  lea     rcx, [rdi-1]
0x180078e25  mov     ebx, eax
0x180078e27  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180078e2b  ja      short loc_180078E3D
0x180078e2d  mov     rcx, rdi; hObject
0x180078e30  call    cs:__imp_CloseHandle
0x180078e36  jmp     short loc_180078E3D
0x180078e38  mov     ebx, 1Fh
0x180078e3d  mov     eax, ebx
0x180078e3f  mov     rbx, [rsp+28h+arg_0]
0x180078e44  add     rsp, 20h
0x180078e48  pop     rdi
0x180078e49  retn
```
