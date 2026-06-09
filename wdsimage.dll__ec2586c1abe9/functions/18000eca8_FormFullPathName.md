# FormFullPathName

- ea: `0x18000eca8`
- end: `0x18000ed89`
- name: `FormFullPathName`
- size: `225`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000efbc`

## callees

- `0x18000eca8`

## import_xrefs

- `KERNEL32!GetFullPathNameW` at `0x18000ecdd`
- `KERNEL32!GetFullPathNameW` at `0x18000ed28`
- `KERNEL32!GetFullPathNameW` at `0x18000ecdd`
- `KERNEL32!GetFullPathNameW` at `0x18000ed28`
- `KERNEL32!HeapAlloc` at `0x18000ed09`
- `KERNEL32!HeapAlloc` at `0x18000ed09`
- `KERNEL32!GetProcessHeap` at `0x18000ecf4`
- `KERNEL32!GetProcessHeap` at `0x18000ecf4`
- `KERNEL32!GetLastError` at `0x18000ed38`
- `KERNEL32!GetLastError` at `0x18000ed38`
- `KERNEL32!SetLastError` at `0x18000ed48`
- `KERNEL32!SetLastError` at `0x18000ed65`
- `KERNEL32!SetLastError` at `0x18000ed48`
- `KERNEL32!SetLastError` at `0x18000ed65`

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
    if ( !FullPathNameW )
      goto LABEL_6;
    ProcessHeap = GetProcessHeap();
    v6 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 2LL * FullPathNameW);
    v3 = v6;
    if ( !v6 )
    {
      LastError = 14;
      goto LABEL_7;
    }
    if ( !GetFullPathNameW(lpFileName, FullPathNameW, v6, 0) )
LABEL_6:
      LastError = GetLastError();
LABEL_7:
    SetLastError(LastError);
    return v3;
  }
  SetLastError(0x57u);
  return 0;
}

```

## disassembly

```asm
0x18000eca8  mov     [rsp+arg_0], rbx
0x18000ecad  mov     [rsp+arg_8], rbp
0x18000ecb2  mov     [rsp+arg_10], rsi
0x18000ecb7  push    rdi
0x18000ecb8  sub     rsp, 20h
0x18000ecbc  xor     edi, edi
0x18000ecbe  mov     rsi, rcx
0x18000ecc1  mov     ebx, edi
0x18000ecc3  test    rcx, rcx
0x18000ecc6  jz      loc_18000ED60
0x18000eccc  cmp     di, [rcx]
0x18000eccf  jz      loc_18000ED60
0x18000ecd5  xor     r9d, r9d; lpFilePart
0x18000ecd8  xor     r8d, r8d; lpBuffer
0x18000ecdb  xor     edx, edx; nBufferLength
0x18000ecdd  call    cs:__imp_GetFullPathNameW
0x18000ece4  nop     dword ptr [rax+rax+00h]
0x18000ece9  mov     ebp, eax
0x18000eceb  test    eax, eax
0x18000eced  jz      short loc_18000ED38
0x18000ecef  mov     ebx, ebp
0x18000ecf1  add     rbx, rbx
0x18000ecf4  call    cs:__imp_GetProcessHeap
0x18000ecfb  nop     dword ptr [rax+rax+00h]
0x18000ed00  mov     r8, rbx; dwBytes
0x18000ed03  lea     edx, [rdi+8]; dwFlags
0x18000ed06  mov     rcx, rax; hHeap
0x18000ed09  call    cs:__imp_HeapAlloc
0x18000ed10  nop     dword ptr [rax+rax+00h]
0x18000ed15  mov     rbx, rax
0x18000ed18  test    rax, rax
0x18000ed1b  jz      short loc_18000ED59
0x18000ed1d  xor     r9d, r9d; lpFilePart
0x18000ed20  mov     r8, rax; lpBuffer
0x18000ed23  mov     edx, ebp; nBufferLength
0x18000ed25  mov     rcx, rsi; lpFileName
0x18000ed28  call    cs:__imp_GetFullPathNameW
0x18000ed2f  nop     dword ptr [rax+rax+00h]
0x18000ed34  test    eax, eax
0x18000ed36  jnz     short loc_18000ED46
0x18000ed38  call    cs:__imp_GetLastError
0x18000ed3f  nop     dword ptr [rax+rax+00h]
0x18000ed44  mov     edi, eax
0x18000ed46  mov     ecx, edi; dwErrCode
0x18000ed48  call    cs:__imp_SetLastError
0x18000ed4f  nop     dword ptr [rax+rax+00h]
0x18000ed54  mov     rax, rbx
0x18000ed57  jmp     short loc_18000ED73
0x18000ed59  mov     edi, 0Eh
0x18000ed5e  jmp     short loc_18000ED46
0x18000ed60  mov     ecx, 57h ; 'W'; dwErrCode
0x18000ed65  call    cs:__imp_SetLastError
0x18000ed6c  nop     dword ptr [rax+rax+00h]
0x18000ed71  xor     eax, eax
0x18000ed73  mov     rbx, [rsp+28h+arg_0]
0x18000ed78  mov     rbp, [rsp+28h+arg_8]
0x18000ed7d  mov     rsi, [rsp+28h+arg_10]
0x18000ed82  add     rsp, 20h
0x18000ed86  pop     rdi
0x18000ed87  retn
```
