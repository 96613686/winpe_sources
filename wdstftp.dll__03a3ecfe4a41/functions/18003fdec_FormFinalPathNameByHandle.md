# FormFinalPathNameByHandle

- ea: `0x18003fdec`
- end: `0x18003ff0f`
- name: `FormFinalPathNameByHandle`
- size: `291`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x18003ff18`

## callees

- `0x18003fdec`

## import_xrefs

- `KERNEL32!GetFinalPathNameByHandleW` at `0x18003fe59`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x18003fea9`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x18003fe59`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x18003fea9`
- `KERNEL32!HeapAlloc` at `0x18003fe89`
- `KERNEL32!HeapAlloc` at `0x18003fe89`
- `KERNEL32!GetLastError` at `0x18003feb9`
- `KERNEL32!GetLastError` at `0x18003feb9`
- `KERNEL32!SetLastError` at `0x18003fec9`
- `KERNEL32!SetLastError` at `0x18003fee6`
- `KERNEL32!SetLastError` at `0x18003fec9`
- `KERNEL32!SetLastError` at `0x18003fee6`
- `KERNEL32!GetProcessHeap` at `0x18003fe72`
- `KERNEL32!GetProcessHeap` at `0x18003fe72`

## pseudocode

```c
WCHAR *__fastcall FormFinalPathNameByHandle(char *hFile, int a2)
{
  DWORD LastError; // edi
  WCHAR *v4; // rbx
  DWORD v5; // esi
  int v6; // edx
  int v7; // edx
  DWORD v8; // ecx
  DWORD FinalPathNameByHandleW; // ebp
  DWORD v10; // ebp
  HANDLE ProcessHeap; // rax
  WCHAR *v12; // rax

  LastError = 0;
  v4 = 0;
  if ( (unsigned __int64)(hFile - 1) > 0xFFFFFFFFFFFFFFFDuLL || (a2 & 0xFFFFFFF8) != 0 )
  {
    v8 = 87;
    goto LABEL_17;
  }
  v5 = 0;
  if ( !a2 )
    goto LABEL_10;
  v6 = a2 - 1;
  if ( !v6 )
  {
    v5 = 1;
    goto LABEL_10;
  }
  v5 = 2;
  v7 = v6 - 1;
  if ( !v7 )
  {
LABEL_10:
    FinalPathNameByHandleW = GetFinalPathNameByHandleW(hFile, 0, 0, v5);
    if ( !FinalPathNameByHandleW )
      goto LABEL_13;
    v10 = FinalPathNameByHandleW + 1;
    ProcessHeap = GetProcessHeap();
    v12 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 2LL * v10);
    v4 = v12;
    if ( !v12 )
    {
      LastError = 14;
      goto LABEL_14;
    }
    if ( !GetFinalPathNameByHandleW(hFile, v12, v10, v5) )
LABEL_13:
      LastError = GetLastError();
LABEL_14:
    SetLastError(LastError);
    return v4;
  }
  if ( v7 == 2 )
  {
    v5 = 4;
    goto LABEL_10;
  }
  v8 = 50;
LABEL_17:
  SetLastError(v8);
  return 0;
}

```

## disassembly

```asm
0x18003fdec  mov     rax, rsp
0x18003fdef  mov     [rax+8], rbx
0x18003fdf3  mov     [rax+10h], rbp
0x18003fdf7  mov     [rax+18h], rsi
0x18003fdfb  mov     [rax+20h], rdi
0x18003fdff  push    r14
0x18003fe01  sub     rsp, 20h
0x18003fe05  xor     edi, edi
0x18003fe07  lea     rax, [rcx-1]
0x18003fe0b  mov     r14, rcx
0x18003fe0e  mov     ebx, edi
0x18003fe10  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003fe14  ja      loc_18003FEE1
0x18003fe1a  test    edx, 0FFFFFFF8h
0x18003fe20  jnz     loc_18003FEE1
0x18003fe26  mov     esi, edi
0x18003fe28  test    edx, edx
0x18003fe2a  jz      short loc_18003FE51
0x18003fe2c  sub     edx, 1
0x18003fe2f  jz      short loc_18003FE4C
0x18003fe31  lea     esi, [rdi+2]
0x18003fe34  sub     edx, 1
0x18003fe37  jz      short loc_18003FE51
0x18003fe39  cmp     edx, esi
0x18003fe3b  jz      short loc_18003FE45
0x18003fe3d  lea     ecx, [rdi+32h]; hFile
0x18003fe40  jmp     loc_18003FEE6
0x18003fe45  mov     esi, 4
0x18003fe4a  jmp     short loc_18003FE51
0x18003fe4c  mov     esi, 1
0x18003fe51  mov     r9d, esi; dwFlags
0x18003fe54  xor     r8d, r8d; cchFilePath
0x18003fe57  xor     edx, edx; lpszFilePath
0x18003fe59  call    cs:__imp_GetFinalPathNameByHandleW
0x18003fe60  nop     dword ptr [rax+rax+00h]
0x18003fe65  mov     ebp, eax
0x18003fe67  test    eax, eax
0x18003fe69  jz      short loc_18003FEB9
0x18003fe6b  inc     ebp
0x18003fe6d  mov     ebx, ebp
0x18003fe6f  add     rbx, rbx
0x18003fe72  call    cs:__imp_GetProcessHeap
0x18003fe79  nop     dword ptr [rax+rax+00h]
0x18003fe7e  mov     r8, rbx; dwBytes
0x18003fe81  mov     edx, 8; dwFlags
0x18003fe86  mov     rcx, rax; hHeap
0x18003fe89  call    cs:__imp_HeapAlloc
0x18003fe90  nop     dword ptr [rax+rax+00h]
0x18003fe95  mov     rbx, rax
0x18003fe98  test    rax, rax
0x18003fe9b  jz      short loc_18003FEDA
0x18003fe9d  mov     r9d, esi; dwFlags
0x18003fea0  mov     r8d, ebp; cchFilePath
0x18003fea3  mov     rdx, rax; lpszFilePath
0x18003fea6  mov     rcx, r14; hFile
0x18003fea9  call    cs:__imp_GetFinalPathNameByHandleW
0x18003feb0  nop     dword ptr [rax+rax+00h]
0x18003feb5  test    eax, eax
0x18003feb7  jnz     short loc_18003FEC7
0x18003feb9  call    cs:__imp_GetLastError
0x18003fec0  nop     dword ptr [rax+rax+00h]
0x18003fec5  mov     edi, eax
0x18003fec7  mov     ecx, edi; dwErrCode
0x18003fec9  call    cs:__imp_SetLastError
0x18003fed0  nop     dword ptr [rax+rax+00h]
0x18003fed5  mov     rax, rbx
0x18003fed8  jmp     short loc_18003FEF4
0x18003feda  mov     edi, 0Eh
0x18003fedf  jmp     short loc_18003FEC7
0x18003fee1  mov     ecx, 57h ; 'W'; dwErrCode
0x18003fee6  call    cs:__imp_SetLastError
0x18003feed  nop     dword ptr [rax+rax+00h]
0x18003fef2  xor     eax, eax
0x18003fef4  mov     rbx, [rsp+28h+arg_0]
0x18003fef9  mov     rbp, [rsp+28h+arg_8]
0x18003fefe  mov     rsi, [rsp+28h+arg_10]
0x18003ff03  mov     rdi, [rsp+28h+arg_18]
0x18003ff08  add     rsp, 20h
0x18003ff0c  pop     r14
0x18003ff0e  retn
```
