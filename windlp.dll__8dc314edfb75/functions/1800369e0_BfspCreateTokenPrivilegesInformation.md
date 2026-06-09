# BfspCreateTokenPrivilegesInformation

- ea: `0x1800369e0`
- end: `0x180036ad4`
- name: `BfspCreateTokenPrivilegesInformation`
- size: `244`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180031344`
- `0x180032518`
- `0x1800345e8`

## callees

- `0x1800366b8`
- `0x1800369e0`
- `0x18007ec9a`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036a0f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036ab6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036a0f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036ab6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180036a22`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180036a22`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036ac4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036ac4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036acc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036acc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036a9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036a9a`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180036a64`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180036a64`

## pseudocode

```c
__int64 __fastcall BfspCreateTokenPrivilegesInformation(__int64 a1, unsigned int a2, int a3, unsigned int **a4)
{
  SIZE_T v8; // r14
  HANDLE ProcessHeap; // rax
  __int64 LastError; // rsi
  unsigned int *v11; // rax
  unsigned int *v12; // rdi
  unsigned int v13; // ebx
  __int64 v14; // rsi
  HANDLE v16; // rax

  v8 = 12LL * a2 + 4;
  ProcessHeap = GetProcessHeap();
  LODWORD(LastError) = 8;
  v11 = (unsigned int *)HeapAlloc(ProcessHeap, 8u, v8);
  v12 = v11;
  if ( !v11 )
  {
    v13 = 0;
LABEL_11:
    SetLastError(LastError);
    return v13;
  }
  v13 = 1;
  memset_0(v11, 0, v8);
  v14 = 0;
  *v12 = a2;
  if ( a2 )
  {
    while ( 1 )
    {
      v13 = LookupPrivilegeValueW(0, *(LPCWSTR *)(a1 + 8 * v14), (PLUID)&v12[3 * v14 + 1]);
      if ( !v13 )
        break;
      if ( a3 )
        v12[3 * v14 + 3] = 2;
      v14 = (unsigned int)(v14 + 1);
      if ( (unsigned int)v14 >= a2 )
        goto LABEL_8;
    }
    LastError = GetLastError();
    BfspLogMessage(4, L"Failed to lookup privelege! Error code = %#x", LastError);
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v12);
    goto LABEL_11;
  }
LABEL_8:
  *a4 = v12;
  return v13;
}

```

## disassembly

```asm
0x1800369e0  push    rbx
0x1800369e2  push    rbp
0x1800369e3  push    rsi
0x1800369e4  push    rdi
0x1800369e5  push    r12
0x1800369e7  push    r13
0x1800369e9  push    r14
0x1800369eb  push    r15
0x1800369ed  sub     rsp, 28h
0x1800369f1  mov     ebp, edx
0x1800369f3  mov     r15, r9
0x1800369f6  mov     r12d, r8d
0x1800369f9  mov     r13, rcx
0x1800369fc  lea     r10, ds:0[rbp*2]
0x180036a04  add     r10, rbp
0x180036a07  lea     r14, ds:4[r10*4]
0x180036a0f  call    cs:__imp_GetProcessHeap
0x180036a15  mov     esi, 8
0x180036a1a  mov     r8, r14; dwBytes
0x180036a1d  mov     rcx, rax; hHeap
0x180036a20  mov     edx, esi; dwFlags
0x180036a22  call    cs:__imp_HeapAlloc
0x180036a28  mov     rdi, rax
0x180036a2b  test    rax, rax
0x180036a2e  jnz     short loc_180036A37
0x180036a30  xor     ebx, ebx
0x180036a32  jmp     loc_180036ACA
0x180036a37  mov     r8, r14; Size
0x180036a3a  xor     edx, edx; Val
0x180036a3c  mov     rcx, rdi; void *
0x180036a3f  mov     ebx, 1
0x180036a44  call    memset_0
0x180036a49  xor     esi, esi
0x180036a4b  mov     [rdi], ebp
0x180036a4d  test    ebp, ebp
0x180036a4f  jz      short loc_180036A84
0x180036a51  mov     rdx, [r13+rsi*8+0]; lpName
0x180036a56  lea     r14, [rsi+rsi*2]
0x180036a5a  lea     r8, [rdi+4]
0x180036a5e  xor     ecx, ecx; lpSystemName
0x180036a60  lea     r8, [r8+r14*4]; lpLuid
0x180036a64  call    cs:__imp_LookupPrivilegeValueW
0x180036a6a  mov     ebx, eax
0x180036a6c  test    eax, eax
0x180036a6e  jz      short loc_180036A9A
0x180036a70  test    r12d, r12d
0x180036a73  jz      short loc_180036A7E
0x180036a75  mov     dword ptr [rdi+r14*4+0Ch], 2
0x180036a7e  inc     esi
0x180036a80  cmp     esi, ebp
0x180036a82  jb      short loc_180036A51
0x180036a84  mov     [r15], rdi
0x180036a87  mov     eax, ebx
0x180036a89  add     rsp, 28h
0x180036a8d  pop     r15
0x180036a8f  pop     r14
0x180036a91  pop     r13
0x180036a93  pop     r12
0x180036a95  pop     rdi
0x180036a96  pop     rsi
0x180036a97  pop     rbp
0x180036a98  pop     rbx
0x180036a99  retn
0x180036a9a  call    cs:__imp_GetLastError
0x180036aa0  lea     rdx, aFailedToLookup; "Failed to lookup privelege! Error code "...
0x180036aa7  mov     ecx, 4
0x180036aac  mov     r8d, eax
0x180036aaf  mov     esi, eax
0x180036ab1  call    BfspLogMessage
0x180036ab6  call    cs:__imp_GetProcessHeap
0x180036abc  mov     r8, rdi; lpMem
0x180036abf  xor     edx, edx; dwFlags
0x180036ac1  mov     rcx, rax; hHeap
0x180036ac4  call    cs:__imp_HeapFree
0x180036aca  mov     ecx, esi; dwErrCode
0x180036acc  call    cs:__imp_SetLastError
0x180036ad2  jmp     short loc_180036A87
```
