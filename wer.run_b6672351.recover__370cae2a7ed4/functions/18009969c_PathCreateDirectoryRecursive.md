# PathCreateDirectoryRecursive

- ea: `0x18009969c`
- end: `0x1800997c9`
- name: `PathCreateDirectoryRecursive`
- size: `301`
- prototype: `__int64 __fastcall(LPCWSTR lpPathName)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18009962c`
- `0x18009969c`

## callees

- `0x180099588`
- `0x18009969c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800996f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099799`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800996f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099799`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800996e1`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180099785`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800996e1`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180099785`

## pseudocode

```c
signed int __fastcall PathCreateDirectoryRecursive(LPCWSTR lpPathName, int a2, unsigned int a3)
{
  signed int result; // eax
  int v6; // r9d
  __int64 v7; // rdi
  int v8; // [rsp+50h] [rbp+8h] BYREF
  unsigned int v9; // [rsp+68h] [rbp+20h] BYREF

  v9 = 0;
  v8 = 0;
  if ( !lpPathName || !a2 || a3 >= 0x80 )
    return -2147024809;
  if ( CreateDirectoryW(lpPathName, 0) )
    return 0;
  result = GetLastError();
  if ( result == 183 )
    return 0;
  if ( result != 3 )
  {
LABEL_8:
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  result = StringFindChar((_DWORD)lpPathName, 92, a2, v6, (__int64)&v9, (__int64)&v8);
  if ( result < 0 )
    return result;
  if ( !v8 )
    return -2147024893;
  v7 = v9;
  lpPathName[v9] = 0;
  result = PathCreateDirectoryRecursive(lpPathName);
  if ( result >= 0 )
  {
    lpPathName[v7] = 92;
    if ( !CreateDirectoryW(lpPathName, 0) )
    {
      result = GetLastError();
      if ( result != 183 )
        goto LABEL_8;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18009969c  mov     [rsp+arg_8], rbx
0x1800996a1  push    rsi
0x1800996a2  push    rdi
0x1800996a3  push    r15
0x1800996a5  sub     rsp, 30h
0x1800996a9  mov     [rsp+48h+arg_18], 0
0x1800996b1  mov     esi, r8d
0x1800996b4  mov     [rsp+48h+arg_0], 0
0x1800996bc  mov     edi, edx
0x1800996be  mov     rbx, rcx
0x1800996c1  test    rcx, rcx
0x1800996c4  jz      loc_1800997B5
0x1800996ca  test    edx, edx
0x1800996cc  jz      loc_1800997B5
0x1800996d2  cmp     r8d, 80h
0x1800996d9  jnb     loc_1800997B5
0x1800996df  xor     edx, edx; lpSecurityAttributes
0x1800996e1  call    cs:__imp_CreateDirectoryW
0x1800996e8  nop     dword ptr [rax+rax+00h]
0x1800996ed  test    eax, eax
0x1800996ef  jz      short loc_1800996F8
0x1800996f1  xor     eax, eax
0x1800996f3  jmp     loc_1800997BA
0x1800996f8  call    cs:__imp_GetLastError
0x1800996ff  nop     dword ptr [rax+rax+00h]
0x180099704  cmp     eax, 0B7h
0x180099709  jz      short loc_1800996F1
0x18009970b  cmp     eax, 3
0x18009970e  jz      short loc_180099725
0x180099710  test    eax, eax
0x180099712  jle     loc_1800997BA
0x180099718  movzx   eax, ax
0x18009971b  or      eax, 80070000h
0x180099720  jmp     loc_1800997BA
0x180099725  lea     rax, [rsp+48h+arg_0]
0x18009972a  mov     r15d, 5Ch ; '\'
0x180099730  mov     [rsp+48h+var_20], rax
0x180099735  mov     edx, r15d
0x180099738  lea     rax, [rsp+48h+arg_18]
0x18009973d  mov     r8d, edi
0x180099740  mov     rcx, rbx
0x180099743  mov     [rsp+48h+var_28], rax
0x180099748  call    StringFindChar
0x18009974d  test    eax, eax
0x18009974f  js      short loc_1800997BA
0x180099751  cmp     [rsp+48h+arg_0], 0
0x180099756  jnz     short loc_18009975F
0x180099758  mov     eax, 80070003h
0x18009975d  jmp     short loc_1800997BA
0x18009975f  mov     edx, [rsp+48h+arg_18]
0x180099763  lea     r8d, [rsi+1]
0x180099767  xor     eax, eax
0x180099769  mov     rcx, rbx; lpPathName
0x18009976c  mov     edi, edx
0x18009976e  mov     [rbx+rdx*2], ax
0x180099772  call    PathCreateDirectoryRecursive
0x180099777  test    eax, eax
0x180099779  js      short loc_1800997BA
0x18009977b  xor     edx, edx; lpSecurityAttributes
0x18009977d  mov     [rbx+rdi*2], r15w
0x180099782  mov     rcx, rbx; lpPathName
0x180099785  call    cs:__imp_CreateDirectoryW
0x18009978c  nop     dword ptr [rax+rax+00h]
0x180099791  test    eax, eax
0x180099793  jnz     loc_1800996F1
0x180099799  call    cs:__imp_GetLastError
0x1800997a0  nop     dword ptr [rax+rax+00h]
0x1800997a5  cmp     eax, 0B7h
0x1800997aa  jz      loc_1800996F1
0x1800997b0  jmp     loc_180099710
0x1800997b5  mov     eax, 80070057h
0x1800997ba  mov     rbx, [rsp+48h+arg_8]
0x1800997bf  add     rsp, 30h
0x1800997c3  pop     r15
0x1800997c5  pop     rdi
0x1800997c6  pop     rsi
0x1800997c7  retn
```
