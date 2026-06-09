# _bidLdrIsPathLocal

- ea: `0x38391b4a0`
- end: `0x38391b5b5`
- name: `_bidLdrIsPathLocal`
- size: `277`
- prototype: `__int64 __fastcall(LPCWSTR lpRootPathName)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x383890a60`

## callees

- `0x3838434c0`
- `0x38391b4a0`

## import_xrefs

- `MSVCR100!wcsncpy_s` at `0x38391b55c`
- `MSVCR100!wcsncpy_s` at `0x38391b55c`
- `KERNEL32!GetFullPathNameW` at `0x38391b532`
- `KERNEL32!GetFullPathNameW` at `0x38391b532`
- `KERNEL32!SearchPathW` at `0x38391b518`
- `KERNEL32!SearchPathW` at `0x38391b518`
- `KERNEL32!GetDriveTypeW` at `0x38391b575`
- `KERNEL32!GetDriveTypeW` at `0x38391b575`
- `KERNEL32!lstrlenW` at `0x38391b4be`
- `KERNEL32!lstrlenW` at `0x38391b4be`

## pseudocode

```c
__int64 __fastcall bidLdrIsPathLocal(WCHAR *lpRootPathName)
{
  WCHAR v3; // ax
  unsigned int v4; // esi
  DWORD FullPathNameW; // eax
  WCHAR v6; // bx
  UINT DriveTypeW; // eax
  LPWSTR FilePart[2]; // [rsp+30h] [rbp-248h] BYREF
  WCHAR Buffer[272]; // [rsp+40h] [rbp-238h] BYREF

  if ( lstrlenW(lpRootPathName) < 3 )
    return 0;
  v3 = *lpRootPathName;
  v4 = 0;
  if ( *lpRootPathName == 46 )
  {
    FullPathNameW = GetFullPathNameW(lpRootPathName, 0x10Eu, Buffer, FilePart);
  }
  else
  {
    if ( v3 == 92 || v3 == 47 || lpRootPathName[1] == 58 )
      goto LABEL_12;
    FullPathNameW = SearchPathW(0, lpRootPathName, 0, 0x10Eu, Buffer, FilePart);
  }
  if ( FullPathNameW && FullPathNameW < 0x10E )
  {
    Buffer[269] = 0;
    wcsncpy_s(lpRootPathName, 0x10Eu, Buffer, 0xFFFFFFFFFFFFFFFFuLL);
LABEL_12:
    v6 = lpRootPathName[3];
    lpRootPathName[3] = 0;
    DriveTypeW = GetDriveTypeW(lpRootPathName);
    lpRootPathName[3] = v6;
    LOBYTE(v4) = DriveTypeW == 3;
    return v4;
  }
  return 0;
}

```

## disassembly

```asm
0x38391b4a0  push    rdi
0x38391b4a2  sub     rsp, 270h
0x38391b4a9  mov     rax, cs:__security_cookie
0x38391b4b0  xor     rax, rsp
0x38391b4b3  mov     [rsp+278h+var_18], rax
0x38391b4bb  mov     rdi, rcx
0x38391b4be  call    cs:__imp_lstrlenW
0x38391b4c4  cmp     eax, 3
0x38391b4c7  jge     short loc_38391B4D0
0x38391b4c9  xor     eax, eax
0x38391b4cb  jmp     loc_38391B59C
0x38391b4d0  movzx   eax, word ptr [rdi]
0x38391b4d3  mov     [rsp+278h+arg_10], rsi
0x38391b4db  xor     esi, esi
0x38391b4dd  cmp     ax, 2Eh ; '.'
0x38391b4e1  jz      short loc_38391B520
0x38391b4e3  cmp     ax, 5Ch ; '\'
0x38391b4e7  jz      short loc_38391B562
0x38391b4e9  cmp     ax, 2Fh ; '/'
0x38391b4ed  jz      short loc_38391B562
0x38391b4ef  cmp     word ptr [rdi+2], 3Ah ; ':'
0x38391b4f4  jz      short loc_38391B562
0x38391b4f6  lea     rax, [rsp+278h+FilePart]
0x38391b4fb  mov     r9d, 10Eh; nBufferLength
0x38391b501  xor     r8d, r8d; lpExtension
0x38391b504  mov     [rsp+278h+lpFilePart], rax; lpFilePart
0x38391b509  lea     rax, [rsp+278h+Buffer]
0x38391b50e  mov     rdx, rdi; lpFileName
0x38391b511  xor     ecx, ecx; lpPath
0x38391b513  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x38391b518  call    cs:__imp_SearchPathW
0x38391b51e  jmp     short loc_38391B538
0x38391b520  lea     r9, [rsp+278h+FilePart]; lpFilePart
0x38391b525  lea     r8, [rsp+278h+Buffer]; lpBuffer
0x38391b52a  mov     edx, 10Eh; nBufferLength
0x38391b52f  mov     rcx, rdi; lpFileName
0x38391b532  call    cs:__imp_GetFullPathNameW
0x38391b538  test    eax, eax
0x38391b53a  jz      short loc_38391B592
0x38391b53c  cmp     eax, 10Eh
0x38391b541  jnb     short loc_38391B592
0x38391b543  lea     r8, [rsp+278h+Buffer]; Source
0x38391b548  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x38391b54c  mov     edx, 10Eh; SizeInWords
0x38391b551  mov     rcx, rdi; Destination
0x38391b554  mov     [rsp+278h+var_1E], si
0x38391b55c  call    cs:__imp_wcsncpy_s
0x38391b562  mov     [rsp+278h+arg_8], rbx
0x38391b56a  movzx   ebx, word ptr [rdi+6]
0x38391b56e  mov     rcx, rdi; lpRootPathName
0x38391b571  mov     [rdi+6], si
0x38391b575  call    cs:__imp_GetDriveTypeW
0x38391b57b  mov     [rdi+6], bx
0x38391b57f  mov     rbx, [rsp+278h+arg_8]
0x38391b587  cmp     eax, 3
0x38391b58a  setz    sil
0x38391b58e  mov     eax, esi
0x38391b590  jmp     short loc_38391B594
0x38391b592  xor     eax, eax
0x38391b594  mov     rsi, [rsp+278h+arg_10]
0x38391b59c  mov     rcx, [rsp+278h+var_18]
0x38391b5a4  xor     rcx, rsp; StackCookie
0x38391b5a7  call    __security_check_cookie
0x38391b5ac  add     rsp, 270h
0x38391b5b3  pop     rdi
0x38391b5b4  retn
```
