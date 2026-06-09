# GetTempName(ushort *,unsigned __int64)

- ea: `0x1400172f4`
- end: `0x140017392`
- name: `?GetTempName@@YAKPEAG_K@Z`
- size: `158`
- prototype: `unsigned int __fastcall(unsigned __int16 *, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x140011f98`
- `0x140016ae0`
- `0x140017398`
- `0x1400192b4`
- `0x14002ec00`

## callees

- `0x140009c04`
- `0x1400172f4`
- `0x140040130`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001736b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001736b`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x140017349`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x140017349`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x140017323`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x140017323`

## pseudocode

```c
DWORD __fastcall GetTempName(unsigned __int16 *a1, unsigned __int64 a2)
{
  WCHAR PathName[264]; // [rsp+20h] [rbp-438h] BYREF
  WCHAR TempFileName[264]; // [rsp+230h] [rbp-228h] BYREF

  if ( (unsigned int)GetTempPath2W(260, PathName) - 1 <= 0x103 && GetTempFileNameW(PathName, L"RPT", 0, TempFileName) )
    return (unsigned __int16)StringCchCopyW(a1, a2, TempFileName);
  else
    return GetLastError();
}

```

## disassembly

```asm
0x1400172f4  mov     [rsp+arg_10], rbx
0x1400172f9  push    rdi
0x1400172fa  sub     rsp, 450h
0x140017301  mov     rax, cs:__security_cookie
0x140017308  xor     rax, rsp
0x14001730b  mov     [rsp+458h+var_18], rax
0x140017313  mov     rdi, rdx
0x140017316  mov     rbx, rcx
0x140017319  lea     rdx, [rsp+458h+PathName]
0x14001731e  mov     ecx, 104h
0x140017323  call    cs:__imp_GetTempPath2W
0x140017329  dec     eax
0x14001732b  cmp     eax, 103h
0x140017330  ja      short loc_14001736B
0x140017332  lea     r9, [rsp+458h+TempFileName]; lpTempFileName
0x14001733a  xor     r8d, r8d; uUnique
0x14001733d  lea     rdx, PrefixString; "RPT"
0x140017344  lea     rcx, [rsp+458h+PathName]; lpPathName
0x140017349  call    cs:__imp_GetTempFileNameW
0x14001734f  test    eax, eax
0x140017351  jz      short loc_14001736B
0x140017353  lea     r8, [rsp+458h+TempFileName]; unsigned __int16 *
0x14001735b  mov     rdx, rdi; unsigned __int64
0x14001735e  mov     rcx, rbx; unsigned __int16 *
0x140017361  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140017366  movzx   eax, ax
0x140017369  jmp     short loc_140017371
0x14001736b  call    cs:__imp_GetLastError
0x140017371  mov     rcx, [rsp+458h+var_18]
0x140017379  xor     rcx, rsp; StackCookie
0x14001737c  call    __security_check_cookie
0x140017381  mov     rbx, [rsp+458h+arg_10]
0x140017389  add     rsp, 450h
0x140017390  pop     rdi
0x140017391  retn
```
