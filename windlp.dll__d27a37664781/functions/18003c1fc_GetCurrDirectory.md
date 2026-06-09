# GetCurrDirectory

- ea: `0x18003c1fc`
- end: `0x18003c2b2`
- name: `GetCurrDirectory`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18003aa98`

## callees

- `0x18003c1fc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c220`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c262`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c220`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c262`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003c231`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003c231`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c270`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c270`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c299`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c299`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c250`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c287`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c250`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c287`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x18003c20f`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x18003c246`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x18003c20f`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x18003c246`

## pseudocode

```c
WCHAR *GetCurrDirectory()
{
  DWORD CurrentDirectoryW; // esi
  HANDLE ProcessHeap; // rax
  WCHAR *v2; // rax
  WCHAR *v3; // rdi
  DWORD LastError; // ebx
  HANDLE v5; // rax

  CurrentDirectoryW = GetCurrentDirectoryW(0, 0);
  if ( CurrentDirectoryW )
  {
    ProcessHeap = GetProcessHeap();
    v2 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 2LL * CurrentDirectoryW);
    v3 = v2;
    if ( v2 )
    {
      LastError = 0;
      if ( !GetCurrentDirectoryW(CurrentDirectoryW, v2) )
      {
        LastError = GetLastError();
        if ( !LastError )
          LastError = 31;
        v5 = GetProcessHeap();
        if ( HeapFree(v5, 0, v3) )
          v3 = 0;
      }
    }
    else
    {
      LastError = 14;
    }
  }
  else
  {
    v3 = 0;
    LastError = GetLastError();
    if ( !LastError )
      LastError = 31;
  }
  SetLastError(LastError);
  return v3;
}

```

## disassembly

```asm
0x18003c1fc  mov     [rsp+arg_0], rbx
0x18003c201  mov     [rsp+arg_8], rsi
0x18003c206  push    rdi
0x18003c207  sub     rsp, 20h
0x18003c20b  xor     edx, edx; lpBuffer
0x18003c20d  xor     ecx, ecx; nBufferLength
0x18003c20f  call    cs:__imp_GetCurrentDirectoryW
0x18003c215  mov     esi, eax
0x18003c217  test    eax, eax
0x18003c219  jz      short loc_18003C285
0x18003c21b  mov     ebx, esi
0x18003c21d  add     rbx, rbx
0x18003c220  call    cs:__imp_GetProcessHeap
0x18003c226  mov     r8, rbx; dwBytes
0x18003c229  mov     edx, 8; dwFlags
0x18003c22e  mov     rcx, rax; hHeap
0x18003c231  call    cs:__imp_HeapAlloc
0x18003c237  mov     rdi, rax
0x18003c23a  test    rax, rax
0x18003c23d  jz      short loc_18003C27E
0x18003c23f  mov     rdx, rax; lpBuffer
0x18003c242  mov     ecx, esi; nBufferLength
0x18003c244  xor     ebx, ebx
0x18003c246  call    cs:__imp_GetCurrentDirectoryW
0x18003c24c  test    eax, eax
0x18003c24e  jnz     short loc_18003C297
0x18003c250  call    cs:__imp_GetLastError
0x18003c256  mov     ebx, eax
0x18003c258  mov     eax, 1Fh
0x18003c25d  test    ebx, ebx
0x18003c25f  cmovz   ebx, eax
0x18003c262  call    cs:__imp_GetProcessHeap
0x18003c268  mov     r8, rdi; lpMem
0x18003c26b  xor     edx, edx; dwFlags
0x18003c26d  mov     rcx, rax; hHeap
0x18003c270  call    cs:__imp_HeapFree
0x18003c276  test    eax, eax
0x18003c278  jz      short loc_18003C297
0x18003c27a  xor     edi, edi
0x18003c27c  jmp     short loc_18003C297
0x18003c27e  mov     ebx, 0Eh
0x18003c283  jmp     short loc_18003C297
0x18003c285  xor     edi, edi
0x18003c287  call    cs:__imp_GetLastError
0x18003c28d  mov     ebx, eax
0x18003c28f  lea     eax, [rdi+1Fh]
0x18003c292  test    ebx, ebx
0x18003c294  cmovz   ebx, eax
0x18003c297  mov     ecx, ebx; dwErrCode
0x18003c299  call    cs:__imp_SetLastError
0x18003c29f  mov     rbx, [rsp+28h+arg_0]
0x18003c2a4  mov     rax, rdi
0x18003c2a7  mov     rsi, [rsp+28h+arg_8]
0x18003c2ac  add     rsp, 20h
0x18003c2b0  pop     rdi
0x18003c2b1  retn
```
