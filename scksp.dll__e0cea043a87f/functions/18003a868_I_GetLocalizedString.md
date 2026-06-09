# I_GetLocalizedString

- ea: `0x18003a868`
- end: `0x18003a90e`
- name: `I_GetLocalizedString`
- size: `166`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18003a914`

## callees

- `0x18003a868`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x18003a890`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x18003a890`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18003a87d`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18003a87d`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x18003a89c`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x18003a89c`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x18003a8e8`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x18003a8e8`

## pseudocode

```c
LCID __fastcall I_GetLocalizedString(__int64 a1, unsigned int a2, _QWORD *a3)
{
  LCID result; // eax
  LCID v7; // esi
  __int64 v8; // rbx
  __int64 v9; // rcx
  __int64 v10; // rbx
  __int64 v11; // r14

  result = GetThreadLocale();
  v7 = result;
  if ( a1 )
  {
    v8 = 0;
    if ( !result )
    {
      result = GetUserDefaultLCID();
      v7 = result;
      if ( !result )
      {
        result = GetSystemDefaultLCID();
        v7 = result;
      }
    }
    while ( (unsigned int)v8 < a2 )
    {
      v9 = (unsigned int)v8;
      while ( *(_WORD *)(a1 + 2 * v8) != 44 )
      {
        v8 = (unsigned int)(v8 + 1);
        if ( (unsigned int)v8 >= a2 )
        {
          if ( (_DWORD)v8 == a2 )
            return result;
          break;
        }
      }
      *(_WORD *)(a1 + 2 * v8) = 0;
      v10 = (unsigned int)(v8 + 1);
      v11 = (unsigned int)v10;
      while ( (unsigned int)v10 < a2 && *(_WORD *)(a1 + 2 * v10) != 59 )
        v10 = (unsigned int)(v10 + 1);
      *(_WORD *)(a1 + 2 * v10) = 0;
      result = LocaleNameToLCID((LPCWSTR)(a1 + 2 * v9), 0);
      if ( result && result == v7 )
      {
        *a3 = a1 + 2 * v11;
        return result;
      }
      v8 = (unsigned int)(v10 + 1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18003a868  push    rbx
0x18003a86a  push    rbp
0x18003a86b  push    rsi
0x18003a86c  push    rdi
0x18003a86d  push    r14
0x18003a86f  push    r15
0x18003a871  sub     rsp, 28h
0x18003a875  mov     r15, r8
0x18003a878  mov     ebp, edx
0x18003a87a  mov     rdi, rcx
0x18003a87d  call    cs:__imp_GetThreadLocale
0x18003a883  mov     esi, eax
0x18003a885  test    rdi, rdi
0x18003a888  jz      short loc_18003A901
0x18003a88a  xor     ebx, ebx
0x18003a88c  test    eax, eax
0x18003a88e  jnz     short loc_18003A8A4
0x18003a890  call    cs:__imp_GetUserDefaultLCID
0x18003a896  mov     esi, eax
0x18003a898  test    eax, eax
0x18003a89a  jnz     short loc_18003A8A4
0x18003a89c  call    cs:__imp_GetSystemDefaultLCID
0x18003a8a2  mov     esi, eax
0x18003a8a4  cmp     ebx, ebp
0x18003a8a6  jnb     short loc_18003A901
0x18003a8a8  mov     ecx, ebx
0x18003a8aa  mov     edx, 2Ch ; ','
0x18003a8af  cmp     dx, [rdi+rbx*2]
0x18003a8b3  jz      short loc_18003A8BD
0x18003a8b5  inc     ebx
0x18003a8b7  cmp     ebx, ebp
0x18003a8b9  jb      short loc_18003A8AA
0x18003a8bb  jz      short loc_18003A901
0x18003a8bd  xor     eax, eax
0x18003a8bf  lea     r8, [rdi+rcx*2]
0x18003a8c3  mov     [rdi+rbx*2], ax
0x18003a8c7  inc     ebx
0x18003a8c9  mov     r14d, ebx
0x18003a8cc  jmp     short loc_18003A8DB
0x18003a8ce  mov     ecx, 3Bh ; ';'
0x18003a8d3  cmp     cx, [rdi+rbx*2]
0x18003a8d7  jz      short loc_18003A8DF
0x18003a8d9  inc     ebx
0x18003a8db  cmp     ebx, ebp
0x18003a8dd  jb      short loc_18003A8CE
0x18003a8df  xor     edx, edx; dwFlags
0x18003a8e1  mov     [rdi+rbx*2], ax
0x18003a8e5  mov     rcx, r8; lpName
0x18003a8e8  call    cs:__imp_LocaleNameToLCID
0x18003a8ee  test    eax, eax
0x18003a8f0  jz      short loc_18003A8FA
0x18003a8f2  lea     rcx, [rdi+r14*2]
0x18003a8f6  cmp     eax, esi
0x18003a8f8  jz      short loc_18003A8FE
0x18003a8fa  inc     ebx
0x18003a8fc  jmp     short loc_18003A8A4
0x18003a8fe  mov     [r15], rcx
0x18003a901  add     rsp, 28h
0x18003a905  pop     r15
0x18003a907  pop     r14
0x18003a909  pop     rdi
0x18003a90a  pop     rsi
0x18003a90b  pop     rbp
0x18003a90c  pop     rbx
0x18003a90d  retn
```
