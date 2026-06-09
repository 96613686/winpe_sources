# _AllocAndMapClientString(void *,ushort const *,uint,uint,ushort * *)

- ea: `0x180002f98`
- end: `0x180003082`
- name: `?_AllocAndMapClientString@@YAJPEAXPEBGIIPEAPEAG@Z`
- size: `234`
- prototype: `__int64 __fastcall(HANDLE hProcess, LPCVOID lpBaseAddress, unsigned int, __int64, unsigned __int16 **NumberOfBytesRead)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800021d0`
- `0x180002b64`
- `0x180002e40`

## callees

- `0x18000217c`
- `0x180002f98`
- `0x18000674c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000306e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000306e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002ff3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002ff3`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180003027`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180003027`

## pseudocode

```c
__int64 __fastcall _AllocAndMapClientString(
        HANDLE hProcess,
        LPCVOID lpBaseAddress,
        unsigned int a3,
        __int64 a4,
        unsigned __int16 **NumberOfBytesRead)
{
  unsigned __int16 **v5; // rsi
  __int64 v7; // rbx
  SIZE_T v9; // rax
  unsigned __int16 *v10; // rdi
  int Error; // ebx

  v5 = NumberOfBytesRead;
  v7 = a3;
  *NumberOfBytesRead = 0;
  if ( !lpBaseAddress || a3 - 1 > 0x103 )
    return (unsigned int)-1073741811;
  v9 = 2LL * a3;
  if ( !is_mul_ok(a3, 2u) )
    v9 = -1;
  v10 = (unsigned __int16 *)HeapAlloc(s_hHeapToUse, 0, v9);
  if ( !v10 )
    return (unsigned int)-1073741801;
  NumberOfBytesRead = 0;
  if ( ReadProcessMemory(hProcess, lpBaseAddress, v10, 2 * v7, (SIZE_T *)&NumberOfBytesRead) )
  {
    Error = _ValidateMappedClientString(v10, v7);
    if ( Error >= 0 )
    {
      *v5 = v10;
      return (unsigned int)Error;
    }
    goto LABEL_11;
  }
  Error = CStatusCode::StatusCodeOfLastError();
  if ( Error < 0 )
LABEL_11:
    HeapFree(s_hHeapToUse, 0, v10);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180002f98  push    rbx
0x180002f9a  push    rbp
0x180002f9b  push    rsi
0x180002f9c  push    rdi
0x180002f9d  push    r14
0x180002f9f  push    r15
0x180002fa1  sub     rsp, 38h
0x180002fa5  mov     rsi, [rsp+68h+NumberOfBytesRead]
0x180002fad  mov     rbp, rdx
0x180002fb0  mov     ebx, r8d
0x180002fb3  mov     r14, rcx
0x180002fb6  mov     qword ptr [rsi], 0
0x180002fbd  test    rdx, rdx
0x180002fc0  jz      loc_18000307B
0x180002fc6  lea     eax, [rbx-1]
0x180002fc9  cmp     eax, 103h
0x180002fce  ja      loc_18000307B
0x180002fd4  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180002fdb  mov     eax, 2
0x180002fe0  mul     rbx
0x180002fe3  cmovb   rax, rcx
0x180002fe7  mov     rcx, cs:?s_hHeapToUse@@3PEAXEA; hHeap
0x180002fee  mov     r8, rax; dwBytes
0x180002ff1  xor     edx, edx; dwFlags
0x180002ff3  call    cs:__imp_HeapAlloc
0x180002ff9  mov     rdi, rax
0x180002ffc  test    rax, rax
0x180002fff  jz      short loc_18000304B
0x180003001  lea     rax, [rsp+68h+NumberOfBytesRead]
0x180003009  mov     [rsp+68h+NumberOfBytesRead], 0
0x180003015  lea     r9, [rbx+rbx]; nSize
0x180003019  mov     [rsp+68h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x18000301e  mov     r8, rdi; lpBuffer
0x180003021  mov     rdx, rbp; lpBaseAddress
0x180003024  mov     rcx, r14; hProcess
0x180003027  call    cs:__imp_ReadProcessMemory
0x18000302d  test    eax, eax
0x18000302f  jnz     short loc_180003052
0x180003031  call    ?StatusCodeOfLastError@CStatusCode@@SAJXZ; CStatusCode::StatusCodeOfLastError(void)
0x180003036  mov     ebx, eax
0x180003038  test    eax, eax
0x18000303a  js      short loc_180003062
0x18000303c  mov     eax, ebx
0x18000303e  add     rsp, 38h
0x180003042  pop     r15
0x180003044  pop     r14
0x180003046  pop     rdi
0x180003047  pop     rsi
0x180003048  pop     rbp
0x180003049  pop     rbx
0x18000304a  retn
0x18000304b  mov     ebx, 0C0000017h
0x180003050  jmp     short loc_18000303C
0x180003052  mov     edx, ebx; unsigned int
0x180003054  mov     rcx, rdi; unsigned __int16 *
0x180003057  call    ?_ValidateMappedClientString@@YAJPEBGK@Z; _ValidateMappedClientString(ushort const *,ulong)
0x18000305c  mov     ebx, eax
0x18000305e  test    eax, eax
0x180003060  jns     short loc_180003076
0x180003062  mov     rcx, cs:?s_hHeapToUse@@3PEAXEA; hHeap
0x180003069  mov     r8, rdi; lpMem
0x18000306c  xor     edx, edx; dwFlags
0x18000306e  call    cs:__imp_HeapFree
0x180003074  jmp     short loc_18000303C
0x180003076  mov     [rsi], rdi
0x180003079  jmp     short loc_18000303C
0x18000307b  mov     ebx, 0C000000Dh
0x180003080  jmp     short loc_18000303C
```
