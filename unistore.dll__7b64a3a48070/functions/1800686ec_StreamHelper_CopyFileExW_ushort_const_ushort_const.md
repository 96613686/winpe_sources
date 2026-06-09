# StreamHelper::CopyFileExW(ushort const *,ushort const *)

- ea: `0x1800686ec`
- end: `0x180068769`
- name: `?CopyFileExW@StreamHelper@@SAJPEBG0@Z`
- size: `125`
- prototype: `__int64 __fastcall(LPCWSTR lpExistingFileName, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18004f198`
- `0x1800687f0`
- `0x1800965cc`

## callees

- `0x180034310`
- `0x1800686ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068710`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068742`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068710`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068742`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180068706`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180068734`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180068706`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180068734`

## pseudocode

```c
__int64 __fastcall StreamHelper::CopyFileExW(LPCWSTR lpExistingFileName, const unsigned __int16 *a2)
{
  int AllFolders; // ebx
  signed int LastError; // eax

  AllFolders = 0;
  if ( !CopyFileW(lpExistingFileName, a2, 0) )
  {
    LastError = GetLastError();
    AllFolders = LastError;
    if ( LastError == 3 )
    {
      AllFolders = StreamHelper::CreateAllFolders(a2);
      if ( AllFolders < 0 )
        return (unsigned int)AllFolders;
      if ( CopyFileW(lpExistingFileName, a2, 0) )
        return 0;
      LastError = GetLastError();
      AllFolders = LastError;
    }
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return (unsigned int)AllFolders;
}

```

## disassembly

```asm
0x1800686ec  mov     [rsp+arg_0], rbx
0x1800686f1  mov     [rsp+arg_8], rsi
0x1800686f6  push    rdi
0x1800686f7  sub     rsp, 20h
0x1800686fb  xor     r8d, r8d; bFailIfExists
0x1800686fe  mov     rdi, rdx
0x180068701  mov     rsi, rcx
0x180068704  xor     ebx, ebx
0x180068706  call    cs:__imp_CopyFileW
0x18006870c  test    eax, eax
0x18006870e  jnz     short loc_180068757
0x180068710  call    cs:__imp_GetLastError
0x180068716  mov     ebx, eax
0x180068718  cmp     eax, 3
0x18006871b  jnz     short loc_18006874A
0x18006871d  mov     rcx, rdi; unsigned __int16 *
0x180068720  call    ?CreateAllFolders@StreamHelper@@SAJPEBG@Z; StreamHelper::CreateAllFolders(ushort const *)
0x180068725  mov     ebx, eax
0x180068727  test    eax, eax
0x180068729  js      short loc_180068757
0x18006872b  xor     r8d, r8d; bFailIfExists
0x18006872e  mov     rdx, rdi; lpNewFileName
0x180068731  mov     rcx, rsi; lpExistingFileName
0x180068734  call    cs:__imp_CopyFileW
0x18006873a  test    eax, eax
0x18006873c  jz      short loc_180068742
0x18006873e  xor     ebx, ebx
0x180068740  jmp     short loc_180068757
0x180068742  call    cs:__imp_GetLastError
0x180068748  mov     ebx, eax
0x18006874a  test    eax, eax
0x18006874c  jle     short loc_180068757
0x18006874e  movzx   ebx, ax
0x180068751  or      ebx, 80070000h
0x180068757  mov     rsi, [rsp+28h+arg_8]
0x18006875c  mov     eax, ebx
0x18006875e  mov     rbx, [rsp+28h+arg_0]
0x180068763  add     rsp, 20h
0x180068767  pop     rdi
0x180068768  retn
```
