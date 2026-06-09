# IsSystemSpecialCase_0

- ea: `0x1800180b4`
- end: `0x1800181a4`
- name: `IsSystemSpecialCase_0`
- size: `240`
- prototype: `__int64 __fastcall(LPCSTR lpString2)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800194f0`

## callees

- `0x180012550`
- `0x1800180b4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryA` at `0x180018120`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryA` at `0x180018120`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryA` at `0x1800180e6`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryA` at `0x1800180e6`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupA` at `0x1800180fa`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupA` at `0x180018137`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupA` at `0x1800180fa`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupA` at `0x180018137`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiA` at `0x18001815c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiA` at `0x180018178`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiA` at `0x18001815c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiA` at `0x180018178`

## pseudocode

```c
_BOOL8 __fastcall IsSystemSpecialCase_0(LPCSTR lpString2)
{
  const CHAR *v2; // rax
  CHAR Buffer[272]; // [rsp+20h] [rbp-238h] BYREF
  CHAR pszSrch[272]; // [rsp+130h] [rbp-128h] BYREF

  if ( !qword_1800597F0 && GetWindowsDirectoryA(Buffer, 0x104u) - 1 <= 0x102 )
    qword_1800597F0 = StrDupA(Buffer);
  v2 = qword_1800597E8;
  if ( !qword_1800597E8 )
  {
    if ( GetSystemDirectoryA(pszSrch, 0x104u) - 1 > 0x102 )
    {
      v2 = qword_1800597E8;
    }
    else
    {
      v2 = StrDupA(pszSrch);
      qword_1800597E8 = v2;
    }
  }
  if ( qword_1800597F0 )
  {
    if ( !lstrcmpiA(qword_1800597F0, lpString2) )
      return 1;
    v2 = qword_1800597E8;
  }
  return v2 && !lstrcmpiA(v2, lpString2);
}

```

## disassembly

```asm
0x1800180b4  push    rbx
0x1800180b6  sub     rsp, 250h
0x1800180bd  mov     rax, cs:__security_cookie
0x1800180c4  xor     rax, rsp
0x1800180c7  mov     [rsp+258h+var_18], rax
0x1800180cf  cmp     cs:qword_1800597F0, 0
0x1800180d7  mov     rbx, rcx
0x1800180da  jnz     short loc_180018107
0x1800180dc  mov     edx, 104h; uSize
0x1800180e1  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x1800180e6  call    cs:__imp_GetWindowsDirectoryA
0x1800180ec  dec     eax
0x1800180ee  cmp     eax, 102h
0x1800180f3  ja      short loc_180018107
0x1800180f5  lea     rcx, [rsp+258h+Buffer]; pszSrch
0x1800180fa  call    cs:__imp_StrDupA
0x180018100  mov     cs:qword_1800597F0, rax
0x180018107  mov     rax, cs:qword_1800597E8
0x18001810e  test    rax, rax
0x180018111  jnz     short loc_18001814D
0x180018113  mov     edx, 104h; uSize
0x180018118  lea     rcx, [rsp+258h+pszSrch]; lpBuffer
0x180018120  call    cs:__imp_GetSystemDirectoryA
0x180018126  dec     eax
0x180018128  cmp     eax, 102h
0x18001812d  ja      short loc_180018146
0x18001812f  lea     rcx, [rsp+258h+pszSrch]; pszSrch
0x180018137  call    cs:__imp_StrDupA
0x18001813d  mov     cs:qword_1800597E8, rax
0x180018144  jmp     short loc_18001814D
0x180018146  mov     rax, cs:qword_1800597E8
0x18001814d  mov     rcx, cs:qword_1800597F0; lpString1
0x180018154  test    rcx, rcx
0x180018157  jz      short loc_18001816D
0x180018159  mov     rdx, rbx; lpString2
0x18001815c  call    cs:__imp_lstrcmpiA
0x180018162  test    eax, eax
0x180018164  jz      short loc_180018182
0x180018166  mov     rax, cs:qword_1800597E8
0x18001816d  test    rax, rax
0x180018170  jz      short loc_180018189
0x180018172  mov     rdx, rbx; lpString2
0x180018175  mov     rcx, rax; lpString1
0x180018178  call    cs:__imp_lstrcmpiA
0x18001817e  test    eax, eax
0x180018180  jnz     short loc_180018189
0x180018182  mov     eax, 1
0x180018187  jmp     short loc_18001818B
0x180018189  xor     eax, eax
0x18001818b  mov     rcx, [rsp+258h+var_18]
0x180018193  xor     rcx, rsp; StackCookie
0x180018196  call    __security_check_cookie
0x18001819b  add     rsp, 250h
0x1800181a2  pop     rbx
0x1800181a3  retn
```
