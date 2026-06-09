# GetCurrDirectory

- ea: `0x180009ee4`
- end: `0x180009f86`
- name: `GetCurrDirectory`
- size: `162`
- prototype: `WCHAR *()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b5f8`

## callees

- `0x1800097e0`
- `0x180009ee4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009f6d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009f6d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009f19`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009f19`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009f08`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009f3f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009f08`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009f3f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009f4d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009f4d`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x180009ef7`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x180009f2e`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x180009ef7`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x180009f2e`

## pseudocode

```c
WCHAR *GetCurrDirectory()
{
  DWORD CurrentDirectoryW; // esi
  HANDLE ProcessHeap; // rax
  WCHAR *v2; // rax
  WCHAR *v3; // rbx
  DWORD v4; // edi
  HANDLE v5; // rax

  CurrentDirectoryW = GetCurrentDirectoryW(0, 0);
  if ( CurrentDirectoryW )
  {
    ProcessHeap = GetProcessHeap();
    v2 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 2LL * CurrentDirectoryW);
    v3 = v2;
    if ( v2 )
    {
      v4 = 0;
      if ( !GetCurrentDirectoryW(CurrentDirectoryW, v2) )
      {
        v4 = GET_LASTERROR_FORCE();
        v5 = GetProcessHeap();
        if ( HeapFree(v5, 0, v3) )
          v3 = 0;
      }
    }
    else
    {
      v4 = 14;
    }
  }
  else
  {
    v3 = 0;
    v4 = GET_LASTERROR_FORCE();
  }
  SetLastError(v4);
  return v3;
}

```

## disassembly

```asm
0x180009ee4  mov     [rsp+arg_0], rbx
0x180009ee9  mov     [rsp+arg_8], rsi
0x180009eee  push    rdi
0x180009eef  sub     rsp, 20h
0x180009ef3  xor     edx, edx; lpBuffer
0x180009ef5  xor     ecx, ecx; nBufferLength
0x180009ef7  call    cs:__imp_GetCurrentDirectoryW
0x180009efd  mov     esi, eax
0x180009eff  test    eax, eax
0x180009f01  jz      short loc_180009F62
0x180009f03  mov     ebx, esi
0x180009f05  add     rbx, rbx
0x180009f08  call    cs:__imp_GetProcessHeap
0x180009f0e  mov     r8, rbx; dwBytes
0x180009f11  mov     edx, 8; dwFlags
0x180009f16  mov     rcx, rax; hHeap
0x180009f19  call    cs:__imp_HeapAlloc
0x180009f1f  mov     rbx, rax
0x180009f22  test    rax, rax
0x180009f25  jz      short loc_180009F5B
0x180009f27  mov     rdx, rax; lpBuffer
0x180009f2a  mov     ecx, esi; nBufferLength
0x180009f2c  xor     edi, edi
0x180009f2e  call    cs:__imp_GetCurrentDirectoryW
0x180009f34  test    eax, eax
0x180009f36  jnz     short loc_180009F6B
0x180009f38  call    GET_LASTERROR_FORCE
0x180009f3d  mov     edi, eax
0x180009f3f  call    cs:__imp_GetProcessHeap
0x180009f45  mov     r8, rbx; lpMem
0x180009f48  xor     edx, edx; dwFlags
0x180009f4a  mov     rcx, rax; hHeap
0x180009f4d  call    cs:__imp_HeapFree
0x180009f53  test    eax, eax
0x180009f55  jz      short loc_180009F6B
0x180009f57  xor     ebx, ebx
0x180009f59  jmp     short loc_180009F6B
0x180009f5b  mov     edi, 0Eh
0x180009f60  jmp     short loc_180009F6B
0x180009f62  xor     ebx, ebx
0x180009f64  call    GET_LASTERROR_FORCE
0x180009f69  mov     edi, eax
0x180009f6b  mov     ecx, edi; dwErrCode
0x180009f6d  call    cs:__imp_SetLastError
0x180009f73  mov     rsi, [rsp+28h+arg_8]
0x180009f78  mov     rax, rbx
0x180009f7b  mov     rbx, [rsp+28h+arg_0]
0x180009f80  add     rsp, 20h
0x180009f84  pop     rdi
0x180009f85  retn
```
