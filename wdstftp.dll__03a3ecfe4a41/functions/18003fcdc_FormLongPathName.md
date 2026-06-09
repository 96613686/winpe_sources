# FormLongPathName

- ea: `0x18003fcdc`
- end: `0x18003fde3`
- name: `FormLongPathName`
- size: `263`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18003eba8`

## callees

- `0x18003f704`
- `0x18003fcdc`

## import_xrefs

- `KERNEL32!GetLongPathNameW` at `0x18003fd2a`
- `KERNEL32!GetLongPathNameW` at `0x18003fd75`
- `KERNEL32!GetLongPathNameW` at `0x18003fd2a`
- `KERNEL32!GetLongPathNameW` at `0x18003fd75`
- `KERNEL32!HeapFree` at `0x18003fdac`
- `KERNEL32!HeapFree` at `0x18003fdac`
- `KERNEL32!HeapAlloc` at `0x18003fd58`
- `KERNEL32!HeapAlloc` at `0x18003fd58`
- `KERNEL32!GetLastError` at `0x18003fd85`
- `KERNEL32!GetLastError` at `0x18003fd85`
- `KERNEL32!SetLastError` at `0x18003fcfc`
- `KERNEL32!SetLastError` at `0x18003fdbf`
- `KERNEL32!SetLastError` at `0x18003fcfc`
- `KERNEL32!SetLastError` at `0x18003fdbf`
- `KERNEL32!GetProcessHeap` at `0x18003fd41`
- `KERNEL32!GetProcessHeap` at `0x18003fd98`
- `KERNEL32!GetProcessHeap` at `0x18003fd41`
- `KERNEL32!GetProcessHeap` at `0x18003fd98`

## pseudocode

```c
WCHAR *__fastcall FormLongPathName(unsigned __int16 *a1)
{
  WCHAR *v1; // rbx
  DWORD LastError; // esi
  const WCHAR *v4; // rax
  WCHAR *v5; // rdi
  DWORD LongPathNameW; // ebp
  HANDLE ProcessHeap; // rax
  WCHAR *v8; // rax
  HANDLE v9; // rax

  v1 = 0;
  LastError = 0;
  if ( !a1 )
  {
    SetLastError(0x57u);
    return 0;
  }
  v4 = (const WCHAR *)PrepareUnicodePath(a1);
  v5 = (WCHAR *)v4;
  if ( v4 )
  {
    LongPathNameW = GetLongPathNameW(v4, 0, 0);
    if ( !LongPathNameW )
      goto LABEL_7;
    ProcessHeap = GetProcessHeap();
    v8 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 2LL * LongPathNameW);
    v1 = v8;
    if ( !v8 )
      goto LABEL_10;
    if ( !GetLongPathNameW(v5, v8, LongPathNameW) )
LABEL_7:
      LastError = GetLastError();
    if ( v1 )
    {
      v9 = GetProcessHeap();
      HeapFree(v9, 0, v5);
LABEL_11:
      SetLastError(LastError);
      return v1;
    }
LABEL_10:
    v1 = v5;
    goto LABEL_11;
  }
  return v1;
}

```

## disassembly

```asm
0x18003fcdc  mov     [rsp+arg_0], rbx
0x18003fce1  mov     [rsp+arg_8], rbp
0x18003fce6  mov     [rsp+arg_10], rsi
0x18003fceb  push    rdi
0x18003fcec  sub     rsp, 20h
0x18003fcf0  xor     ebx, ebx
0x18003fcf2  xor     esi, esi
0x18003fcf4  test    rcx, rcx
0x18003fcf7  jnz     short loc_18003FD0F
0x18003fcf9  lea     ecx, [rbx+57h]; dwErrCode
0x18003fcfc  call    cs:__imp_SetLastError
0x18003fd03  nop     dword ptr [rax+rax+00h]
0x18003fd08  xor     eax, eax
0x18003fd0a  jmp     loc_18003FDCE
0x18003fd0f  xor     edx, edx
0x18003fd11  call    PrepareUnicodePath
0x18003fd16  mov     rdi, rax
0x18003fd19  test    rax, rax
0x18003fd1c  jz      loc_18003FDCB
0x18003fd22  xor     r8d, r8d; cchBuffer
0x18003fd25  xor     edx, edx; lpszLongPath
0x18003fd27  mov     rcx, rax; lpszShortPath
0x18003fd2a  call    cs:__imp_GetLongPathNameW
0x18003fd31  nop     dword ptr [rax+rax+00h]
0x18003fd36  mov     ebp, eax
0x18003fd38  test    eax, eax
0x18003fd3a  jz      short loc_18003FD85
0x18003fd3c  mov     ebx, ebp
0x18003fd3e  add     rbx, rbx
0x18003fd41  call    cs:__imp_GetProcessHeap
0x18003fd48  nop     dword ptr [rax+rax+00h]
0x18003fd4d  mov     r8, rbx; dwBytes
0x18003fd50  mov     edx, 8; dwFlags
0x18003fd55  mov     rcx, rax; hHeap
0x18003fd58  call    cs:__imp_HeapAlloc
0x18003fd5f  nop     dword ptr [rax+rax+00h]
0x18003fd64  mov     rbx, rax
0x18003fd67  test    rax, rax
0x18003fd6a  jz      short loc_18003FDBA
0x18003fd6c  mov     r8d, ebp; cchBuffer
0x18003fd6f  mov     rdx, rax; lpszLongPath
0x18003fd72  mov     rcx, rdi; lpszShortPath
0x18003fd75  call    cs:__imp_GetLongPathNameW
0x18003fd7c  nop     dword ptr [rax+rax+00h]
0x18003fd81  test    eax, eax
0x18003fd83  jnz     short loc_18003FD93
0x18003fd85  call    cs:__imp_GetLastError
0x18003fd8c  nop     dword ptr [rax+rax+00h]
0x18003fd91  mov     esi, eax
0x18003fd93  test    rbx, rbx
0x18003fd96  jz      short loc_18003FDBA
0x18003fd98  call    cs:__imp_GetProcessHeap
0x18003fd9f  nop     dword ptr [rax+rax+00h]
0x18003fda4  mov     r8, rdi; lpMem
0x18003fda7  xor     edx, edx; dwFlags
0x18003fda9  mov     rcx, rax; hHeap
0x18003fdac  call    cs:__imp_HeapFree
0x18003fdb3  nop     dword ptr [rax+rax+00h]
0x18003fdb8  jmp     short loc_18003FDBD
0x18003fdba  mov     rbx, rdi
0x18003fdbd  mov     ecx, esi; dwErrCode
0x18003fdbf  call    cs:__imp_SetLastError
0x18003fdc6  nop     dword ptr [rax+rax+00h]
0x18003fdcb  mov     rax, rbx
0x18003fdce  mov     rbx, [rsp+28h+arg_0]
0x18003fdd3  mov     rbp, [rsp+28h+arg_8]
0x18003fdd8  mov     rsi, [rsp+28h+arg_10]
0x18003fddd  add     rsp, 20h
0x18003fde1  pop     rdi
0x18003fde2  retn
```
