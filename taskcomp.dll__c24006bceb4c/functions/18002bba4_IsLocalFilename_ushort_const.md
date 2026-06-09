# IsLocalFilename(ushort const *)

- ea: `0x18002bba4`
- end: `0x18002bcfa`
- name: `?IsLocalFilename@@YAHPEBG@Z`
- size: `342`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800262d0`

## callees

- `0x18002bba4`
- `0x18002e5b0`

## import_xrefs

- `msvcrt!wcschr` at `0x18002bc00`
- `msvcrt!wcschr` at `0x18002bc00`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x18002bcc4`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x18002bcc4`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18002bc4f`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18002bc4f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18002bc2a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18002bc2a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002bc6b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002bc6b`

## pseudocode

```c
_BOOL8 __fastcall IsLocalFilename(const unsigned __int16 *a1)
{
  __int16 v2; // cx
  const WCHAR *v3; // rdi
  wchar_t *v4; // rax
  int v5; // ebx
  WCHAR *v6; // rdx
  UINT DriveTypeW; // eax
  DWORD nSize; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v10[6]; // [rsp+28h] [rbp-D8h] BYREF
  wchar_t v11; // [rsp+2Eh] [rbp-D2h]
  WCHAR Buffer[264]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR v13[264]; // [rsp+240h] [rbp+140h] BYREF

  if ( a1 )
  {
    v2 = *a1;
    if ( v2 )
    {
      if ( v2 == 92 )
      {
        if ( a1[1] == 92 )
        {
          v3 = a1 + 2;
          v4 = wcschr(a1 + 2, 0x5Cu);
          if ( v4 )
          {
            nSize = 257;
            v5 = v4 - a1 - 2;
            if ( GetComputerNameW(Buffer, &nSize) )
            {
              *(_DWORD *)v10 = 257;
              if ( GetComputerNameExW(ComputerNamePhysicalDnsFullyQualified, v13, (LPDWORD)v10) )
              {
                if ( v5 == nSize )
                {
                  v6 = Buffer;
                  return lstrcmpiW(v3, v6) == 0;
                }
                if ( v5 == *(_DWORD *)v10 )
                {
                  v6 = v13;
                  return lstrcmpiW(v3, v6) == 0;
                }
              }
            }
          }
          return 0;
        }
        return 1;
      }
      if ( (unsigned __int16)(v2 - 65) > 0x19u && (unsigned __int16)(v2 - 97) > 0x19u )
        return 1;
      if ( a1[1] != 58 )
        return 1;
      *(_DWORD *)&v10[2] = *(_DWORD *)L":\\";
      *(_WORD *)v10 = v2;
      v11 = asc_180054FA8[3];
      DriveTypeW = GetDriveTypeW((LPCWSTR)v10);
      if ( (DriveTypeW & 0xFFFFFFFA) != 0 || DriveTypeW == 5 )
        return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18002bba4  push    rbp
0x18002bba6  push    rbx
0x18002bba7  push    rsi
0x18002bba8  push    rdi
0x18002bba9  lea     rbp, [rsp-368h]
0x18002bbb1  sub     rsp, 468h
0x18002bbb8  mov     rax, cs:__security_cookie
0x18002bbbf  xor     rax, rsp
0x18002bbc2  mov     [rbp+380h+var_30], rax
0x18002bbc9  xor     esi, esi
0x18002bbcb  mov     rbx, rcx
0x18002bbce  test    rcx, rcx
0x18002bbd1  jz      loc_18002BCDD
0x18002bbd7  movzx   ecx, word ptr [rcx]
0x18002bbda  test    cx, cx
0x18002bbdd  jz      loc_18002BCDD
0x18002bbe3  lea     edx, [rsi+5Ch]; Ch
0x18002bbe6  cmp     cx, dx
0x18002bbe9  jnz     loc_18002BC8B
0x18002bbef  cmp     [rbx+2], dx
0x18002bbf3  jnz     loc_18002BCD6
0x18002bbf9  lea     rdi, [rbx+4]
0x18002bbfd  mov     rcx, rdi; Str
0x18002bc00  call    cs:__imp_wcschr
0x18002bc06  test    rax, rax
0x18002bc09  jz      loc_18002BCDD
0x18002bc0f  sub     rax, rbx
0x18002bc12  mov     [rsp+480h+nSize], 101h
0x18002bc1a  sar     rax, 1
0x18002bc1d  lea     rdx, [rsp+480h+nSize]; nSize
0x18002bc22  lea     rcx, [rsp+480h+Buffer]; lpBuffer
0x18002bc27  lea     ebx, [rax-2]
0x18002bc2a  call    cs:__imp_GetComputerNameW
0x18002bc30  test    eax, eax
0x18002bc32  jz      loc_18002BCDD
0x18002bc38  lea     r8, [rsp+480h+var_458]; nSize
0x18002bc3d  mov     dword ptr [rsp+480h+var_458], 101h
0x18002bc45  lea     rdx, [rbp+380h+var_240]; lpBuffer
0x18002bc4c  lea     ecx, [rsi+7]; NameType
0x18002bc4f  call    cs:__imp_GetComputerNameExW
0x18002bc55  test    eax, eax
0x18002bc57  jz      loc_18002BCDD
0x18002bc5d  cmp     ebx, [rsp+480h+nSize]
0x18002bc61  jnz     short loc_18002BC7C
0x18002bc63  lea     rdx, [rsp+480h+Buffer]; lpString2
0x18002bc68  mov     rcx, rdi; lpString1
0x18002bc6b  call    cs:__imp_lstrcmpiW
0x18002bc71  test    eax, eax
0x18002bc73  mov     ecx, esi
0x18002bc75  setz    cl
0x18002bc78  mov     eax, ecx
0x18002bc7a  jmp     short loc_18002BCDF
0x18002bc7c  cmp     ebx, dword ptr [rsp+480h+var_458]
0x18002bc80  jnz     short loc_18002BCDD
0x18002bc82  lea     rdx, [rbp+380h+var_240]
0x18002bc89  jmp     short loc_18002BC68
0x18002bc8b  lea     eax, [rcx-41h]
0x18002bc8e  cmp     ax, 19h
0x18002bc92  jbe     short loc_18002BC9D
0x18002bc94  lea     eax, [rcx-61h]
0x18002bc97  cmp     ax, 19h
0x18002bc9b  ja      short loc_18002BCD6
0x18002bc9d  cmp     word ptr [rbx+2], 3Ah ; ':'
0x18002bca2  jnz     short loc_18002BCD6
0x18002bca4  mov     eax, dword ptr cs:asc_180054FA8+2; ":\\"
0x18002bcaa  mov     dword ptr [rsp+480h+var_458+2], eax
0x18002bcae  movzx   eax, word ptr cs:asc_180054FA8+6; ""
0x18002bcb5  mov     word ptr [rsp+480h+var_458], cx
0x18002bcba  lea     rcx, [rsp+480h+var_458]; lpRootPathName
0x18002bcbf  mov     [rsp+480h+var_452], ax
0x18002bcc4  call    cs:__imp_GetDriveTypeW
0x18002bcca  test    eax, 0FFFFFFFAh
0x18002bccf  jnz     short loc_18002BCD6
0x18002bcd1  cmp     eax, 5
0x18002bcd4  jnz     short loc_18002BCDD
0x18002bcd6  mov     eax, 1
0x18002bcdb  jmp     short loc_18002BCDF
0x18002bcdd  xor     eax, eax
0x18002bcdf  mov     rcx, [rbp+380h+var_30]
0x18002bce6  xor     rcx, rsp; StackCookie
0x18002bce9  call    __security_check_cookie
0x18002bcee  add     rsp, 468h
0x18002bcf5  pop     rdi
0x18002bcf6  pop     rsi
0x18002bcf7  pop     rbx
0x18002bcf8  pop     rbp
0x18002bcf9  retn
```
