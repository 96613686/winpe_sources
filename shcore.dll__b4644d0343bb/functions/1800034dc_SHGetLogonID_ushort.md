# SHGetLogonID(ushort * *)

- ea: `0x1800034dc`
- end: `0x180003576`
- name: `?SHGetLogonID@@YAJPEAPEAG@Z`
- size: `154`
- prototype: `__int64 __fastcall(LPWSTR *StringSid)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800048f4`

## callees

- `0x1800034dc`
- `0x18000357c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000355f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000355f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003547`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003547`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180003538`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180003538`

## pseudocode

```c
__int64 __fastcall SHGetLogonID(LPWSTR *StringSid, __int64 a2, DWORD a3)
{
  int v4; // ebx
  HLOCAL v5; // rdi
  unsigned int i; // eax
  signed int LastError; // eax
  HLOCAL hMem; // [rsp+30h] [rbp+8h] BYREF

  *StringSid = 0;
  hMem = 0;
  v4 = SHQueryToken<_TOKEN_GROUPS>((__int64)StringSid, a2, a3, &hMem);
  if ( v4 >= 0 )
  {
    v5 = hMem;
    v4 = -2147467259;
    for ( i = 0; i < *(_DWORD *)hMem; ++i )
    {
      if ( (*((_DWORD *)hMem + 4 * i + 4) & 0xC0000000) != 0 )
      {
        if ( ConvertSidToStringSidW(*((PSID *)hMem + 2 * i + 1), StringSid) )
        {
          v4 = 0;
        }
        else
        {
          LastError = GetLastError();
          v4 = LastError;
          if ( LastError > 0 )
            v4 = (unsigned __int16)LastError | 0x80070000;
        }
        break;
      }
    }
    LocalFree(v5);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800034dc  mov     rax, rsp
0x1800034df  mov     [rax+10h], rbx
0x1800034e3  mov     [rax+18h], rsi
0x1800034e7  push    rdi
0x1800034e8  sub     rsp, 20h
0x1800034ec  lea     r9, [rax+8]
0x1800034f0  mov     qword ptr [rcx], 0
0x1800034f7  mov     rsi, rcx
0x1800034fa  mov     qword ptr [rax+8], 0
0x180003502  call    ??$SHQueryToken@U_TOKEN_GROUPS@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@HPEAPEAU_TOKEN_GROUPS@@@Z; SHQueryToken<_TOKEN_GROUPS>(void *,_TOKEN_INFORMATION_CLASS,int,_TOKEN_GROUPS * *)
0x180003507  mov     ebx, eax
0x180003509  test    eax, eax
0x18000350b  js      short loc_18000354D
0x18000350d  mov     rdi, [rsp+28h+hMem]
0x180003512  mov     ebx, 80004005h
0x180003517  xor     eax, eax
0x180003519  cmp     eax, [rdi]
0x18000351b  jnb     short loc_180003544
0x18000351d  mov     ecx, eax
0x18000351f  add     rcx, rcx
0x180003522  test    dword ptr [rdi+rcx*8+10h], 0C0000000h
0x18000352a  jnz     short loc_180003530
0x18000352c  inc     eax
0x18000352e  jmp     short loc_180003519
0x180003530  mov     rcx, [rdi+rcx*8+8]; Sid
0x180003535  mov     rdx, rsi; StringSid
0x180003538  call    cs:__imp_ConvertSidToStringSidW
0x18000353e  test    eax, eax
0x180003540  jz      short loc_18000355F
0x180003542  xor     ebx, ebx
0x180003544  mov     rcx, rdi; hMem
0x180003547  call    cs:__imp_LocalFree
0x18000354d  mov     rsi, [rsp+28h+arg_10]
0x180003552  mov     eax, ebx
0x180003554  mov     rbx, [rsp+28h+arg_8]
0x180003559  add     rsp, 20h
0x18000355d  pop     rdi
0x18000355e  retn
0x18000355f  call    cs:__imp_GetLastError
0x180003565  mov     ebx, eax
0x180003567  test    eax, eax
0x180003569  jle     short loc_180003544
0x18000356b  movzx   ebx, ax
0x18000356e  or      ebx, 80070000h
0x180003574  jmp     short loc_180003544
```
