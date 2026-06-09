# DeleteFileWithRetry(ushort const *)

- ea: `0x18002957c`
- end: `0x180029607`
- name: `?DeleteFileWithRetry@@YAJPEBG@Z`
- size: `139`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001730`

## callees

- `0x18002957c`

## import_xrefs

- `msvcrt!rand` at `0x1800295b1`
- `msvcrt!rand` at `0x1800295b1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800295d8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800295d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800295a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800295a4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002959a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002959a`

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
0x18002957c  mov     [rsp+arg_0], rbx
0x180029581  mov     [rsp+arg_8], rsi
0x180029586  push    rdi
0x180029587  sub     rsp, 20h
0x18002958b  xor     ebx, ebx
0x18002958d  mov     rsi, rcx
0x180029590  lea     edi, [rbx+3]
0x180029593  test    edi, edi
0x180029595  jz      short loc_1800295E2
0x180029597  mov     rcx, rsi; lpFileName
0x18002959a  call    cs:__imp_DeleteFileW
0x1800295a0  test    eax, eax
0x1800295a2  jnz     short loc_1800295F5
0x1800295a4  call    cs:__imp_GetLastError
0x1800295aa  mov     ebx, eax
0x1800295ac  cmp     eax, 20h ; ' '
0x1800295af  jnz     short loc_1800295E2
0x1800295b1  call    cs:__imp_rand
0x1800295b7  mov     ecx, eax
0x1800295b9  mov     eax, 10624DD3h
0x1800295be  imul    ecx
0x1800295c0  sar     edx, 4
0x1800295c3  mov     eax, edx
0x1800295c5  shr     eax, 1Fh
0x1800295c8  add     edx, eax
0x1800295ca  imul    eax, edx, 0FAh
0x1800295d0  sub     ecx, eax
0x1800295d2  add     ecx, 0FAh; dwMilliseconds
0x1800295d8  call    cs:__imp_Sleep
0x1800295de  dec     edi
0x1800295e0  jmp     short loc_180029593
0x1800295e2  test    ebx, ebx
0x1800295e4  jz      short loc_1800295F5
0x1800295e6  jle     short loc_1800295F1
0x1800295e8  movzx   ebx, bx
0x1800295eb  or      ebx, 80070000h
0x1800295f1  mov     eax, ebx
0x1800295f3  jmp     short loc_1800295F7
0x1800295f5  xor     eax, eax
0x1800295f7  mov     rbx, [rsp+28h+arg_0]
0x1800295fc  mov     rsi, [rsp+28h+arg_8]
0x180029601  add     rsp, 20h
0x180029605  pop     rdi
0x180029606  retn
```
