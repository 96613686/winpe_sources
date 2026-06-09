# DirectoryExists

- ea: `0x18000b044`
- end: `0x18000b0e4`
- name: `DirectoryExists`
- size: `160`
- prototype: `__int64 __fastcall(const wchar_t *)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800040c0`
- `0x180006518`
- `0x180006868`
- `0x18000b720`

## callees

- `0x18000a0f0`
- `0x18000b044`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b0bd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b0cc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b0bd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b0cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b089`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b089`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b0a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b0a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b0b5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b0b5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000b073`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000b073`

## pseudocode

```c
__int64 __fastcall DirectoryExists(const wchar_t *a1)
{
  unsigned int v1; // edi
  const WCHAR *v2; // rax
  WCHAR *v3; // rsi
  DWORD FileAttributesW; // eax
  DWORD LastError; // ebx
  HANDLE ProcessHeap; // rax

  if ( a1 && *a1 )
  {
    v1 = 0;
    v2 = (const WCHAR *)PrepareUnicodePathEx(a1);
    v3 = (WCHAR *)v2;
    if ( v2 )
    {
      FileAttributesW = GetFileAttributesW(v2);
      if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
      {
        LastError = GetLastError();
        if ( LastError )
        {
          if ( LastError == 2 )
            LastError = 3;
        }
        else
        {
          LastError = 267;
        }
      }
      else
      {
        LastError = 0;
        v1 = 1;
      }
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v3);
      SetLastError(LastError);
    }
    return v1;
  }
  else
  {
    SetLastError(0x57u);
    return 0;
  }
}

```

## disassembly

```asm
0x18000b044  mov     [rsp+arg_0], rbx
0x18000b049  mov     [rsp+arg_8], rsi
0x18000b04e  push    rdi
0x18000b04f  sub     rsp, 20h
0x18000b053  test    rcx, rcx
0x18000b056  jz      short loc_18000B0C7
0x18000b058  xor     eax, eax
0x18000b05a  cmp     ax, [rcx]
0x18000b05d  jz      short loc_18000B0C7
0x18000b05f  xor     edx, edx
0x18000b061  xor     edi, edi
0x18000b063  call    PrepareUnicodePathEx
0x18000b068  mov     rsi, rax
0x18000b06b  test    rax, rax
0x18000b06e  jz      short loc_18000B0C3
0x18000b070  mov     rcx, rax; lpFileName
0x18000b073  call    cs:__imp_GetFileAttributesW
0x18000b079  cmp     eax, 0FFFFFFFFh
0x18000b07c  jz      short loc_18000B089
0x18000b07e  test    al, 10h
0x18000b080  jz      short loc_18000B089
0x18000b082  xor     ebx, ebx
0x18000b084  lea     edi, [rbx+1]
0x18000b087  jmp     short loc_18000B0A7
0x18000b089  call    cs:__imp_GetLastError
0x18000b08f  mov     ebx, eax
0x18000b091  test    eax, eax
0x18000b093  jnz     short loc_18000B09C
0x18000b095  mov     ebx, 10Bh
0x18000b09a  jmp     short loc_18000B0A7
0x18000b09c  cmp     ebx, 2
0x18000b09f  mov     eax, 3
0x18000b0a4  cmovz   ebx, eax
0x18000b0a7  call    cs:__imp_GetProcessHeap
0x18000b0ad  mov     r8, rsi; lpMem
0x18000b0b0  xor     edx, edx; dwFlags
0x18000b0b2  mov     rcx, rax; hHeap
0x18000b0b5  call    cs:__imp_HeapFree
0x18000b0bb  mov     ecx, ebx; dwErrCode
0x18000b0bd  call    cs:__imp_SetLastError
0x18000b0c3  mov     eax, edi
0x18000b0c5  jmp     short loc_18000B0D4
0x18000b0c7  mov     ecx, 57h ; 'W'; dwErrCode
0x18000b0cc  call    cs:__imp_SetLastError
0x18000b0d2  xor     eax, eax
0x18000b0d4  mov     rbx, [rsp+28h+arg_0]
0x18000b0d9  mov     rsi, [rsp+28h+arg_8]
0x18000b0de  add     rsp, 20h
0x18000b0e2  pop     rdi
0x18000b0e3  retn
```
