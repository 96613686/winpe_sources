# FormFullPathName

- ea: `0x18003fbfc`
- end: `0x18003fcd5`
- name: `FormFullPathName`
- size: `217`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18003e138`
- `0x18003eba8`
- `0x18003f704`

## callees

- `0x18003fbfc`

## import_xrefs

- `KERNEL32!GetFullPathNameW` at `0x18003fc31`
- `KERNEL32!GetFullPathNameW` at `0x18003fc7c`
- `KERNEL32!GetFullPathNameW` at `0x18003fc31`
- `KERNEL32!GetFullPathNameW` at `0x18003fc7c`
- `KERNEL32!HeapAlloc` at `0x18003fc5d`
- `KERNEL32!HeapAlloc` at `0x18003fc5d`
- `KERNEL32!GetLastError` at `0x18003fc8c`
- `KERNEL32!GetLastError` at `0x18003fc8c`
- `KERNEL32!SetLastError` at `0x18003fc9c`
- `KERNEL32!SetLastError` at `0x18003fcb2`
- `KERNEL32!SetLastError` at `0x18003fc9c`
- `KERNEL32!SetLastError` at `0x18003fcb2`
- `KERNEL32!GetProcessHeap` at `0x18003fc48`
- `KERNEL32!GetProcessHeap` at `0x18003fc48`

## pseudocode

```c
WCHAR *__fastcall FormFullPathName(LPCWSTR lpFileName)
{
  DWORD LastError; // edi
  WCHAR *v3; // rbx
  DWORD FullPathNameW; // ebp
  HANDLE ProcessHeap; // rax
  WCHAR *v6; // rax

  LastError = 0;
  v3 = 0;
  if ( lpFileName && *lpFileName )
  {
    FullPathNameW = GetFullPathNameW(lpFileName, 0, 0, 0);
    if ( !FullPathNameW
      || (ProcessHeap = GetProcessHeap(), v6 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 2LL * FullPathNameW), (v3 = v6) != 0)
      && !GetFullPathNameW(lpFileName, FullPathNameW, v6, 0) )
    {
      LastError = GetLastError();
    }
    SetLastError(LastError);
    return v3;
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
0x18003fbfc  mov     [rsp+arg_0], rbx
0x18003fc01  mov     [rsp+arg_8], rbp
0x18003fc06  mov     [rsp+arg_10], rsi
0x18003fc0b  push    rdi
0x18003fc0c  sub     rsp, 20h
0x18003fc10  xor     edi, edi
0x18003fc12  mov     rsi, rcx
0x18003fc15  mov     ebx, edi
0x18003fc17  test    rcx, rcx
0x18003fc1a  jz      loc_18003FCAD
0x18003fc20  cmp     di, [rcx]
0x18003fc23  jz      loc_18003FCAD
0x18003fc29  xor     r9d, r9d; lpFilePart
0x18003fc2c  xor     r8d, r8d; lpBuffer
0x18003fc2f  xor     edx, edx; nBufferLength
0x18003fc31  call    cs:__imp_GetFullPathNameW
0x18003fc38  nop     dword ptr [rax+rax+00h]
0x18003fc3d  mov     ebp, eax
0x18003fc3f  test    eax, eax
0x18003fc41  jz      short loc_18003FC8C
0x18003fc43  mov     ebx, ebp
0x18003fc45  add     rbx, rbx
0x18003fc48  call    cs:__imp_GetProcessHeap
0x18003fc4f  nop     dword ptr [rax+rax+00h]
0x18003fc54  mov     r8, rbx; dwBytes
0x18003fc57  lea     edx, [rdi+8]; dwFlags
0x18003fc5a  mov     rcx, rax; hHeap
0x18003fc5d  call    cs:__imp_HeapAlloc
0x18003fc64  nop     dword ptr [rax+rax+00h]
0x18003fc69  mov     rbx, rax
0x18003fc6c  test    rax, rax
0x18003fc6f  jz      short loc_18003FC9A
0x18003fc71  xor     r9d, r9d; lpFilePart
0x18003fc74  mov     r8, rax; lpBuffer
0x18003fc77  mov     edx, ebp; nBufferLength
0x18003fc79  mov     rcx, rsi; lpFileName
0x18003fc7c  call    cs:__imp_GetFullPathNameW
0x18003fc83  nop     dword ptr [rax+rax+00h]
0x18003fc88  test    eax, eax
0x18003fc8a  jnz     short loc_18003FC9A
0x18003fc8c  call    cs:__imp_GetLastError
0x18003fc93  nop     dword ptr [rax+rax+00h]
0x18003fc98  mov     edi, eax
0x18003fc9a  mov     ecx, edi; dwErrCode
0x18003fc9c  call    cs:__imp_SetLastError
0x18003fca3  nop     dword ptr [rax+rax+00h]
0x18003fca8  mov     rax, rbx
0x18003fcab  jmp     short loc_18003FCC0
0x18003fcad  mov     ecx, 57h ; 'W'; dwErrCode
0x18003fcb2  call    cs:__imp_SetLastError
0x18003fcb9  nop     dword ptr [rax+rax+00h]
0x18003fcbe  xor     eax, eax
0x18003fcc0  mov     rbx, [rsp+28h+arg_0]
0x18003fcc5  mov     rbp, [rsp+28h+arg_8]
0x18003fcca  mov     rsi, [rsp+28h+arg_10]
0x18003fccf  add     rsp, 20h
0x18003fcd3  pop     rdi
0x18003fcd4  retn
```
