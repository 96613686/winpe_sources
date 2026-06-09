# DeleteFileWithRetry(ushort const *)

- ea: `0x18002af48`
- end: `0x18002afec`
- name: `?DeleteFileWithRetry@@YAJPEBG@Z`
- size: `164`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001760`

## callees

- `0x18002af48`

## import_xrefs

- `msvcrt!rand` at `0x18002af89`
- `msvcrt!rand` at `0x18002af89`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002afb6`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002afb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002af76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002af76`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002af66`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002af66`

## pseudocode

```c
__int64 __fastcall DeleteFileWithRetry(LPCWSTR lpFileName)
{
  signed int LastError; // ebx
  int i; // edi
  int v4; // eax

  LastError = 0;
  for ( i = 3; i; --i )
  {
    if ( DeleteFileW(lpFileName) )
      return 0;
    LastError = GetLastError();
    if ( LastError != 32 )
      break;
    v4 = rand();
    Sleep(v4 % 250 + 250);
  }
  if ( !LastError )
    return 0;
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18002af48  mov     [rsp+arg_0], rbx
0x18002af4d  mov     [rsp+arg_8], rsi
0x18002af52  push    rdi
0x18002af53  sub     rsp, 20h
0x18002af57  xor     ebx, ebx
0x18002af59  mov     rsi, rcx
0x18002af5c  lea     edi, [rbx+3]
0x18002af5f  test    edi, edi
0x18002af61  jz      short loc_18002AFC6
0x18002af63  mov     rcx, rsi; lpFileName
0x18002af66  call    cs:__imp_DeleteFileW
0x18002af6d  nop     dword ptr [rax+rax+00h]
0x18002af72  test    eax, eax
0x18002af74  jnz     short loc_18002AFD9
0x18002af76  call    cs:__imp_GetLastError
0x18002af7d  nop     dword ptr [rax+rax+00h]
0x18002af82  mov     ebx, eax
0x18002af84  cmp     eax, 20h ; ' '
0x18002af87  jnz     short loc_18002AFC6
0x18002af89  call    cs:__imp_rand
0x18002af90  nop     dword ptr [rax+rax+00h]
0x18002af95  mov     ecx, eax
0x18002af97  mov     eax, 10624DD3h
0x18002af9c  imul    ecx
0x18002af9e  sar     edx, 4
0x18002afa1  mov     eax, edx
0x18002afa3  shr     eax, 1Fh
0x18002afa6  add     edx, eax
0x18002afa8  imul    eax, edx, 0FAh
0x18002afae  sub     ecx, eax
0x18002afb0  add     ecx, 0FAh; dwMilliseconds
0x18002afb6  call    cs:__imp_Sleep
0x18002afbd  nop     dword ptr [rax+rax+00h]
0x18002afc2  dec     edi
0x18002afc4  jmp     short loc_18002AF5F
0x18002afc6  test    ebx, ebx
0x18002afc8  jz      short loc_18002AFD9
0x18002afca  jle     short loc_18002AFD5
0x18002afcc  movzx   ebx, bx
0x18002afcf  or      ebx, 80070000h
0x18002afd5  mov     eax, ebx
0x18002afd7  jmp     short loc_18002AFDB
0x18002afd9  xor     eax, eax
0x18002afdb  mov     rbx, [rsp+28h+arg_0]
0x18002afe0  mov     rsi, [rsp+28h+arg_8]
0x18002afe5  add     rsp, 20h
0x18002afe9  pop     rdi
0x18002afea  retn
```
