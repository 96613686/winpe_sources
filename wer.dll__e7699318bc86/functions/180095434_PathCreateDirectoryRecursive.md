# PathCreateDirectoryRecursive

- ea: `0x180095434`
- end: `0x180095548`
- name: `PathCreateDirectoryRecursive`
- size: `276`
- prototype: `__int64 __fastcall(LPCWSTR lpPathName)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800953c4`
- `0x180095434`

## callees

- `0x180095320`
- `0x180095434`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009548a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009551f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009548a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009551f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180095479`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180095511`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180095479`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180095511`

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
0x180095434  mov     [rsp+arg_8], rbx
0x180095439  push    rsi
0x18009543a  push    rdi
0x18009543b  push    r15
0x18009543d  sub     rsp, 30h
0x180095441  mov     [rsp+48h+arg_18], 0
0x180095449  mov     esi, r8d
0x18009544c  mov     [rsp+48h+arg_0], 0
0x180095454  mov     edi, edx
0x180095456  mov     rbx, rcx
0x180095459  test    rcx, rcx
0x18009545c  jz      loc_180095535
0x180095462  test    edx, edx
0x180095464  jz      loc_180095535
0x18009546a  cmp     r8d, 80h
0x180095471  jnb     loc_180095535
0x180095477  xor     edx, edx; lpSecurityAttributes
0x180095479  call    cs:__imp_CreateDirectoryW
0x18009547f  test    eax, eax
0x180095481  jz      short loc_18009548A
0x180095483  xor     eax, eax
0x180095485  jmp     loc_18009553A
0x18009548a  call    cs:__imp_GetLastError
0x180095490  cmp     eax, 0B7h
0x180095495  jz      short loc_180095483
0x180095497  cmp     eax, 3
0x18009549a  jz      short loc_1800954B1
0x18009549c  test    eax, eax
0x18009549e  jle     loc_18009553A
0x1800954a4  movzx   eax, ax
0x1800954a7  or      eax, 80070000h
0x1800954ac  jmp     loc_18009553A
0x1800954b1  lea     rax, [rsp+48h+arg_0]
0x1800954b6  mov     r15d, 5Ch ; '\'
0x1800954bc  mov     [rsp+48h+var_20], rax
0x1800954c1  mov     edx, r15d
0x1800954c4  lea     rax, [rsp+48h+arg_18]
0x1800954c9  mov     r8d, edi
0x1800954cc  mov     rcx, rbx
0x1800954cf  mov     [rsp+48h+var_28], rax
0x1800954d4  call    StringFindChar
0x1800954d9  test    eax, eax
0x1800954db  js      short loc_18009553A
0x1800954dd  cmp     [rsp+48h+arg_0], 0
0x1800954e2  jnz     short loc_1800954EB
0x1800954e4  mov     eax, 80070003h
0x1800954e9  jmp     short loc_18009553A
0x1800954eb  mov     edx, [rsp+48h+arg_18]
0x1800954ef  lea     r8d, [rsi+1]
0x1800954f3  xor     eax, eax
0x1800954f5  mov     rcx, rbx; lpPathName
0x1800954f8  mov     edi, edx
0x1800954fa  mov     [rbx+rdx*2], ax
0x1800954fe  call    PathCreateDirectoryRecursive
0x180095503  test    eax, eax
0x180095505  js      short loc_18009553A
0x180095507  xor     edx, edx; lpSecurityAttributes
0x180095509  mov     [rbx+rdi*2], r15w
0x18009550e  mov     rcx, rbx; lpPathName
0x180095511  call    cs:__imp_CreateDirectoryW
0x180095517  test    eax, eax
0x180095519  jnz     loc_180095483
0x18009551f  call    cs:__imp_GetLastError
0x180095525  cmp     eax, 0B7h
0x18009552a  jz      loc_180095483
0x180095530  jmp     loc_18009549C
0x180095535  mov     eax, 80070057h
0x18009553a  mov     rbx, [rsp+48h+arg_8]
0x18009553f  add     rsp, 30h
0x180095543  pop     r15
0x180095545  pop     rdi
0x180095546  pop     rsi
0x180095547  retn
```
