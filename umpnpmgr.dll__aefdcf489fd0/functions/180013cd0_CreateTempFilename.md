# CreateTempFilename

- ea: `0x180013cd0`
- end: `0x180013d88`
- name: `CreateTempFilename`
- size: `184`
- prototype: `_BOOL8 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800156c0`

## callees

- `0x180001110`
- `0x180013cd0`
- `0x180018970`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013d62`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013d62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013d02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013d02`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180013d31`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180013d31`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180013cf8`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180013cf8`

## pseudocode

```c
_BOOL8 __fastcall CreateTempFilename(__int64 a1, __int64 a2)
{
  unsigned int TempPath2W; // eax
  DWORD LastError; // ebx
  DWORD v5; // r10d
  WCHAR PathName[264]; // [rsp+20h] [rbp-438h] BYREF
  WCHAR TempFileName[264]; // [rsp+230h] [rbp-228h] BYREF

  TempPath2W = GetTempPath2W(260, PathName);
  if ( !TempPath2W )
    goto LABEL_2;
  if ( TempPath2W > 0x104 )
  {
    LastError = 13;
    goto LABEL_9;
  }
  if ( GetTempFileNameW(PathName, L"PNP", 0, TempFileName) )
  {
    if ( (int)RtlStringCchCopyW(a2, 260, TempFileName) < 0 )
      v5 += 13;
    LastError = v5;
  }
  else
  {
LABEL_2:
    LastError = GetLastError();
  }
LABEL_9:
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x180013cd0  push    rbx
0x180013cd2  sub     rsp, 450h
0x180013cd9  mov     rax, cs:__security_cookie
0x180013ce0  xor     rax, rsp
0x180013ce3  mov     [rsp+458h+var_18], rax
0x180013ceb  mov     rbx, rdx
0x180013cee  mov     ecx, 104h
0x180013cf3  lea     rdx, [rsp+458h+PathName]
0x180013cf8  call    cs:__imp_GetTempPath2W
0x180013cfe  test    eax, eax
0x180013d00  jnz     short loc_180013D0C
0x180013d02  call    cs:__imp_GetLastError
0x180013d08  mov     ebx, eax
0x180013d0a  jmp     short loc_180013D60
0x180013d0c  cmp     eax, 104h
0x180013d11  jbe     short loc_180013D1A
0x180013d13  mov     ebx, 0Dh
0x180013d18  jmp     short loc_180013D60
0x180013d1a  lea     r9, [rsp+458h+TempFileName]; lpTempFileName
0x180013d22  xor     r8d, r8d; uUnique
0x180013d25  lea     rdx, PrefixString; "PNP"
0x180013d2c  lea     rcx, [rsp+458h+PathName]; lpPathName
0x180013d31  call    cs:__imp_GetTempFileNameW
0x180013d37  test    eax, eax
0x180013d39  jz      short loc_180013D02
0x180013d3b  lea     r8, [rsp+458h+TempFileName]
0x180013d43  mov     edx, 104h
0x180013d48  mov     rcx, rbx
0x180013d4b  xor     r10d, r10d
0x180013d4e  call    RtlStringCchCopyW
0x180013d53  lea     ebx, [r10+0Dh]
0x180013d57  test    eax, eax
0x180013d59  cmovs   r10d, ebx
0x180013d5d  mov     ebx, r10d
0x180013d60  mov     ecx, ebx; dwErrCode
0x180013d62  call    cs:__imp_SetLastError
0x180013d68  xor     eax, eax
0x180013d6a  test    ebx, ebx
0x180013d6c  setz    al
0x180013d6f  mov     rcx, [rsp+458h+var_18]
0x180013d77  xor     rcx, rsp; StackCookie
0x180013d7a  call    __security_check_cookie
0x180013d7f  add     rsp, 450h
0x180013d86  pop     rbx
0x180013d87  retn
```
