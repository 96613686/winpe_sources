# IsSeShutdownNameEnabled(void)

- ea: `0x18006e784`
- end: `0x18006e8a8`
- name: `?IsSeShutdownNameEnabled@@YAHXZ`
- size: `292`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180077970`

## callees

- `0x18006e784`

## import_xrefs

- `ntdll!NtOpenProcessToken` at `0x18006e7cf`
- `ntdll!NtOpenProcessToken` at `0x18006e7cf`
- `ntdll!NtOpenThreadToken` at `0x18006e7ae`
- `ntdll!NtOpenThreadToken` at `0x18006e7ae`
- `ntdll!NtQueryInformationToken` at `0x18006e7fb`
- `ntdll!NtQueryInformationToken` at `0x18006e841`
- `ntdll!NtQueryInformationToken` at `0x18006e7fb`
- `ntdll!NtQueryInformationToken` at `0x18006e841`
- `ntdll!NtClose` at `0x18006e895`
- `ntdll!NtClose` at `0x18006e895`
- `ntdll!RtlFreeHeap` at `0x18006e88a`
- `ntdll!RtlFreeHeap` at `0x18006e88a`
- `ntdll!RtlAllocateHeap` at `0x18006e819`
- `ntdll!RtlAllocateHeap` at `0x18006e819`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006e797`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006e797`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006e7bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006e7bf`

## pseudocode

```c
__int64 IsSeShutdownNameEnabled(void)
{
  HANDLE CurrentThread; // rax
  NTSTATUS v1; // eax
  HANDLE CurrentProcess; // rax
  unsigned int v3; // edi
  _DWORD *Heap; // rbx
  __int64 i; // rcx
  ULONG TokenInformationLength; // [rsp+40h] [rbp+8h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp+10h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  v1 = NtOpenThreadToken(CurrentThread, 8u, 0, &TokenHandle);
  if ( v1 == -1073741700 )
  {
    CurrentProcess = GetCurrentProcess();
    v1 = NtOpenProcessToken(CurrentProcess, 8u, &TokenHandle);
  }
  else if ( v1 < 0 )
  {
    return 0;
  }
  v3 = 0;
  if ( v1 >= 0 )
  {
    TokenInformationLength = 0;
    NtQueryInformationToken(TokenHandle, TokenPrivileges, 0, 0, &TokenInformationLength);
    if ( TokenInformationLength )
    {
      Heap = RtlAllocateHeap(pUserHeap, 0, TokenInformationLength);
      if ( Heap )
      {
        if ( NtQueryInformationToken(
               TokenHandle,
               TokenPrivileges,
               Heap,
               TokenInformationLength,
               &TokenInformationLength) >= 0 )
        {
          for ( i = 0; (unsigned int)i < *Heap; i = (unsigned int)(i + 1) )
          {
            if ( !Heap[3 * i + 2] && Heap[3 * i + 1] == 19 && (Heap[3 * i + 3] & 3) != 0 )
            {
              v3 = 1;
              break;
            }
          }
        }
        RtlFreeHeap(pUserHeap, 0, Heap);
      }
    }
    NtClose(TokenHandle);
  }
  return v3;
}

```

## disassembly

```asm
0x18006e784  mov     [rsp+arg_10], rbx
0x18006e789  push    rdi
0x18006e78a  sub     rsp, 30h
0x18006e78e  mov     [rsp+38h+TokenHandle], 0
0x18006e797  call    cs:__imp_GetCurrentThread
0x18006e79d  xor     r8d, r8d; OpenAsSelf
0x18006e7a0  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x18006e7a5  mov     rcx, rax; ThreadHandle
0x18006e7a8  lea     ebx, [r8+8]
0x18006e7ac  mov     edx, ebx; DesiredAccess
0x18006e7ae  call    cs:__imp_NtOpenThreadToken
0x18006e7b4  cmp     eax, 0C000007Ch
0x18006e7b9  jnz     loc_18006E86D
0x18006e7bf  call    cs:__imp_GetCurrentProcess
0x18006e7c5  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x18006e7ca  mov     edx, ebx; DesiredAccess
0x18006e7cc  mov     rcx, rax; ProcessHandle
0x18006e7cf  call    cs:__imp_NtOpenProcessToken
0x18006e7d5  xor     edi, edi
0x18006e7d7  test    eax, eax
0x18006e7d9  js      loc_18006E89B
0x18006e7df  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x18006e7e4  lea     rax, [rsp+38h+TokenInformationLength]
0x18006e7e9  xor     r9d, r9d; TokenInformationLength
0x18006e7ec  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18006e7f1  xor     r8d, r8d; TokenInformation
0x18006e7f4  mov     [rsp+38h+TokenInformationLength], edi
0x18006e7f8  lea     edx, [rdi+3]; TokenInformationClass
0x18006e7fb  call    cs:__imp_NtQueryInformationToken
0x18006e801  mov     eax, [rsp+38h+TokenInformationLength]
0x18006e805  test    eax, eax
0x18006e807  jz      loc_18006E890
0x18006e80d  mov     rcx, cs:pUserHeap; HeapHandle
0x18006e814  mov     r8d, eax; Size
0x18006e817  xor     edx, edx; Flags
0x18006e819  call    cs:__imp_RtlAllocateHeap
0x18006e81f  mov     rbx, rax
0x18006e822  test    rax, rax
0x18006e825  jz      short loc_18006E890
0x18006e827  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18006e82c  lea     rax, [rsp+38h+TokenInformationLength]
0x18006e831  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x18006e836  lea     edx, [rdi+3]; TokenInformationClass
0x18006e839  mov     r8, rbx; TokenInformation
0x18006e83c  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18006e841  call    cs:__imp_NtQueryInformationToken
0x18006e847  test    eax, eax
0x18006e849  js      short loc_18006E87E
0x18006e84b  xor     ecx, ecx
0x18006e84d  cmp     ecx, [rbx]
0x18006e84f  jnb     short loc_18006E87E
0x18006e851  lea     rdx, [rcx+rcx*2]
0x18006e855  cmp     [rbx+rdx*4+8], edi
0x18006e859  jnz     short loc_18006E869
0x18006e85b  cmp     dword ptr [rbx+rdx*4+4], 13h
0x18006e860  jnz     short loc_18006E869
0x18006e862  test    byte ptr [rbx+rdx*4+0Ch], 3
0x18006e867  jnz     short loc_18006E879
0x18006e869  inc     ecx
0x18006e86b  jmp     short loc_18006E84D
0x18006e86d  test    eax, eax
0x18006e86f  jns     loc_18006E7D5
0x18006e875  xor     eax, eax
0x18006e877  jmp     short loc_18006E89D
0x18006e879  mov     edi, 1
0x18006e87e  mov     rcx, cs:pUserHeap; HeapHandle
0x18006e885  mov     r8, rbx; P
0x18006e888  xor     edx, edx; Flags
0x18006e88a  call    cs:__imp_RtlFreeHeap
0x18006e890  mov     rcx, [rsp+38h+TokenHandle]; Handle
0x18006e895  call    cs:__imp_NtClose
0x18006e89b  mov     eax, edi
0x18006e89d  mov     rbx, [rsp+38h+arg_10]
0x18006e8a2  add     rsp, 30h
0x18006e8a6  pop     rdi
0x18006e8a7  retn
```
