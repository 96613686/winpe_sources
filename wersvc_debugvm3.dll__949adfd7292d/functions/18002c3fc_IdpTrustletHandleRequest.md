# IdpTrustletHandleRequest

- ea: `0x18002c3fc`
- end: `0x18002c5c1`
- name: `IdpTrustletHandleRequest`
- size: `453`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x18002c5d0`

## callees

- `0x1800029d0`
- `0x18002c1d8`
- `0x18002c3fc`
- `0x180034550`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18002c55a`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18002c55a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002c516`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002c536`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002c516`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002c536`
- `ntdll!NtClose` at `0x18002c57f`
- `ntdll!NtClose` at `0x18002c57f`
- `ntdll!wcsrchr` at `0x18002c4a6`
- `ntdll!wcsrchr` at `0x18002c4a6`

## pseudocode

```c
__int64 __fastcall IdpTrustletHandleRequest(__int64 a1, __int64 a2, unsigned __int64 a3)
{
  unsigned int v5; // r15d
  char *v6; // r14
  DWORD v7; // ebp
  HANDLE *v8; // r12
  wchar_t *v9; // rax
  const wchar_t *v10; // rdx
  wchar_t *v11; // rcx
  void *v12; // rcx
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-268h] BYREF
  WCHAR szFilePath[264]; // [rsp+40h] [rbp-258h] BYREF

  NumberOfBytesWritten = 0;
  v5 = 0;
  if ( a3 < 0x50 || *(_DWORD *)(a1 + 8) != *(_DWORD *)(a2 + 8) || *(_QWORD *)(a2 + 56) > a3 - 80 )
    return v5;
  v6 = (char *)(a2 + 80);
  v7 = *(_DWORD *)(a2 + 56);
  if ( (*(_BYTE *)(a2 + 44) & 0x10) == 0 )
    goto LABEL_14;
  if ( v7 >= 0xC58 )
  {
    v8 = (HANDLE *)(a1 + 40);
    if ( *(_QWORD *)(a1 + 40) == -1 )
    {
      memcpy_0((void *)(a1 + 48), (const void *)(a2 + 80), 0xC58u);
      *(_WORD *)(a1 + 590) = 0;
      v9 = wcsrchr((const wchar_t *)(a1 + 72), 0x5Cu);
      v10 = L"tdmp";
      if ( !*(_DWORD *)(a1 + 1136) )
        v10 = L"dmp";
      v11 = v9 + 1;
      if ( !v9 )
        v11 = (wchar_t *)(a1 + 72);
      if ( (unsigned int)IdpTrustletCreateDump(v11, v10, *(unsigned int *)(a1 + 8), v8) )
      {
        v7 -= 3160;
        v6 += 3160;
        if ( *(_DWORD *)(a1 + 1136) )
          WriteFile(*v8, (LPCVOID)(a1 + 1112), 0x82Cu, &NumberOfBytesWritten, 0);
LABEL_14:
        v12 = *(void **)(a1 + 40);
        if ( v12 != (void *)-1LL )
        {
          WriteFile(v12, v6, v7, &NumberOfBytesWritten, 0);
          if ( (*(_BYTE *)(a2 + 44) & 2) != 0 )
          {
            if ( *(_QWORD *)(a1 + 16)
              && GetFinalPathNameByHandleW(*(HANDLE *)(a1 + 40), szFilePath, 0x105u, 0) - 1 <= 0x103 )
            {
              (*(void (__fastcall **)(__int64, WCHAR *))(a1 + 16))(a1 + 48, szFilePath);
            }
            NtClose(*(HANDLE *)(a1 + 40));
            *(_QWORD *)(a1 + 40) = -1;
          }
          return 1;
        }
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18002c3fc  mov     [rsp+arg_10], rbx
0x18002c401  push    rbp
0x18002c402  push    rsi
0x18002c403  push    rdi
0x18002c404  push    r12
0x18002c406  push    r13
0x18002c408  push    r14
0x18002c40a  push    r15
0x18002c40c  sub     rsp, 260h
0x18002c413  mov     rax, cs:__security_cookie
0x18002c41a  xor     rax, rsp
0x18002c41d  mov     [rsp+298h+var_48], rax
0x18002c425  xor     ebx, ebx
0x18002c427  mov     rsi, rdx
0x18002c42a  mov     [rsp+298h+NumberOfBytesWritten], ebx
0x18002c42e  mov     rdi, rcx
0x18002c431  mov     r15d, ebx
0x18002c434  cmp     r8, 50h ; 'P'
0x18002c438  jb      loc_18002C593
0x18002c43e  mov     eax, [rdx+8]
0x18002c441  cmp     [rcx+8], eax
0x18002c444  jnz     loc_18002C593
0x18002c44a  lea     rax, [r8-50h]
0x18002c44e  cmp     [rdx+38h], rax
0x18002c452  ja      loc_18002C593
0x18002c458  test    byte ptr [rdx+2Ch], 10h
0x18002c45c  lea     r14, [rdx+50h]
0x18002c460  mov     ebp, [rdx+38h]
0x18002c463  jz      loc_18002C51C
0x18002c469  mov     r8d, 0C58h; Size
0x18002c46f  cmp     ebp, r8d
0x18002c472  jb      loc_18002C593
0x18002c478  lea     r12, [rcx+28h]
0x18002c47c  cmp     qword ptr [r12], 0FFFFFFFFFFFFFFFFh
0x18002c481  jnz     loc_18002C593
0x18002c487  add     rcx, 30h ; '0'; void *
0x18002c48b  mov     rdx, r14; Src
0x18002c48e  call    memcpy_0
0x18002c493  mov     [rdi+24Eh], bx
0x18002c49a  mov     edx, 5Ch ; '\'; Ch
0x18002c49f  lea     rbx, [rdi+48h]
0x18002c4a3  mov     rcx, rbx; Str
0x18002c4a6  call    cs:__imp_wcsrchr
0x18002c4ac  cmp     [rdi+470h], r15d
0x18002c4b3  lea     rcx, aDmp; "dmp"
0x18002c4ba  mov     r8d, [rdi+8]
0x18002c4be  lea     rdx, aTdmp; "tdmp"
0x18002c4c5  cmovz   rdx, rcx
0x18002c4c9  mov     r9, r12
0x18002c4cc  test    rax, rax
0x18002c4cf  lea     rcx, [rax+2]
0x18002c4d3  cmovz   rcx, rbx
0x18002c4d7  call    IdpTrustletCreateDump
0x18002c4dc  xor     ebx, ebx
0x18002c4de  test    eax, eax
0x18002c4e0  jz      loc_18002C593
0x18002c4e6  add     ebp, 0FFFFF3A8h
0x18002c4ec  add     r14, 0C58h
0x18002c4f3  cmp     [rdi+470h], ebx
0x18002c4f9  jz      short loc_18002C51C
0x18002c4fb  mov     rcx, [r12]; hFile
0x18002c4ff  lea     rdx, [rdi+458h]; lpBuffer
0x18002c506  lea     r9, [rsp+298h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002c50b  mov     [rsp+298h+lpOverlapped], rbx; lpOverlapped
0x18002c510  mov     r8d, 82Ch; nNumberOfBytesToWrite
0x18002c516  call    cs:__imp_WriteFile
0x18002c51c  mov     rcx, [rdi+28h]; hFile
0x18002c520  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002c524  jz      short loc_18002C593
0x18002c526  lea     r9, [rsp+298h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002c52b  mov     [rsp+298h+lpOverlapped], rbx; lpOverlapped
0x18002c530  mov     r8d, ebp; nNumberOfBytesToWrite
0x18002c533  mov     rdx, r14; lpBuffer
0x18002c536  call    cs:__imp_WriteFile
0x18002c53c  test    byte ptr [rsi+2Ch], 2
0x18002c540  jz      short loc_18002C58D
0x18002c542  cmp     [rdi+10h], rbx
0x18002c546  jz      short loc_18002C57B
0x18002c548  mov     rcx, [rdi+28h]; hFile
0x18002c54c  lea     rdx, [rsp+298h+szFilePath]; lpszFilePath
0x18002c551  xor     r9d, r9d; dwFlags
0x18002c554  mov     r8d, 105h; cchFilePath
0x18002c55a  call    cs:__imp_GetFinalPathNameByHandleW
0x18002c560  dec     eax
0x18002c562  cmp     eax, 103h
0x18002c567  ja      short loc_18002C57B
0x18002c569  mov     rax, [rdi+10h]
0x18002c56d  lea     rcx, [rdi+30h]
0x18002c571  lea     rdx, [rsp+298h+szFilePath]
0x18002c576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c57b  mov     rcx, [rdi+28h]; Handle
0x18002c57f  call    cs:__imp_NtClose
0x18002c585  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x18002c58d  mov     r15d, 1
0x18002c593  mov     eax, r15d
0x18002c596  mov     rcx, [rsp+298h+var_48]
0x18002c59e  xor     rcx, rsp; StackCookie
0x18002c5a1  call    __security_check_cookie
0x18002c5a6  mov     rbx, [rsp+298h+arg_10]
0x18002c5ae  add     rsp, 260h
0x18002c5b5  pop     r15
0x18002c5b7  pop     r14
0x18002c5b9  pop     r13
0x18002c5bb  pop     r12
0x18002c5bd  pop     rdi
0x18002c5be  pop     rsi
0x18002c5bf  pop     rbp
0x18002c5c0  retn
```
