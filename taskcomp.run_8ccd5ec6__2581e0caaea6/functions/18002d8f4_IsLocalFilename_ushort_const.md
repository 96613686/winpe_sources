# IsLocalFilename(ushort const *)

- ea: `0x18002d8f4`
- end: `0x18002da69`
- name: `?IsLocalFilename@@YAHPEBG@Z`
- size: `373`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180027a80`

## callees

- `0x18002d8f4`
- `0x180030700`

## import_xrefs

- `msvcrt!wcschr` at `0x18002d950`
- `msvcrt!wcschr` at `0x18002d950`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x18002da2c`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x18002da2c`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18002d9ab`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18002d9ab`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18002d980`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18002d980`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002d9cd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002d9cd`

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
      v11 = asc_180056FB8[3];
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
0x18002d8f4  push    rbp
0x18002d8f6  push    rbx
0x18002d8f7  push    rsi
0x18002d8f8  push    rdi
0x18002d8f9  lea     rbp, [rsp-368h]
0x18002d901  sub     rsp, 468h
0x18002d908  mov     rax, cs:__security_cookie
0x18002d90f  xor     rax, rsp
0x18002d912  mov     [rbp+380h+var_30], rax
0x18002d919  xor     esi, esi
0x18002d91b  mov     rbx, rcx
0x18002d91e  test    rcx, rcx
0x18002d921  jz      loc_18002DA4B
0x18002d927  movzx   ecx, word ptr [rcx]
0x18002d92a  test    cx, cx
0x18002d92d  jz      loc_18002DA4B
0x18002d933  lea     edx, [rsi+5Ch]; Ch
0x18002d936  cmp     cx, dx
0x18002d939  jnz     loc_18002D9F3
0x18002d93f  cmp     [rbx+2], dx
0x18002d943  jnz     loc_18002DA44
0x18002d949  lea     rdi, [rbx+4]
0x18002d94d  mov     rcx, rdi; Str
0x18002d950  call    cs:__imp_wcschr
0x18002d957  nop     dword ptr [rax+rax+00h]
0x18002d95c  test    rax, rax
0x18002d95f  jz      loc_18002DA4B
0x18002d965  sub     rax, rbx
0x18002d968  mov     [rsp+480h+nSize], 101h
0x18002d970  sar     rax, 1
0x18002d973  lea     rdx, [rsp+480h+nSize]; nSize
0x18002d978  lea     rcx, [rsp+480h+Buffer]; lpBuffer
0x18002d97d  lea     ebx, [rax-2]
0x18002d980  call    cs:__imp_GetComputerNameW
0x18002d987  nop     dword ptr [rax+rax+00h]
0x18002d98c  test    eax, eax
0x18002d98e  jz      loc_18002DA4B
0x18002d994  lea     r8, [rsp+480h+var_458]; nSize
0x18002d999  mov     dword ptr [rsp+480h+var_458], 101h
0x18002d9a1  lea     rdx, [rbp+380h+var_240]; lpBuffer
0x18002d9a8  lea     ecx, [rsi+7]; NameType
0x18002d9ab  call    cs:__imp_GetComputerNameExW
0x18002d9b2  nop     dword ptr [rax+rax+00h]
0x18002d9b7  test    eax, eax
0x18002d9b9  jz      loc_18002DA4B
0x18002d9bf  cmp     ebx, [rsp+480h+nSize]
0x18002d9c3  jnz     short loc_18002D9E4
0x18002d9c5  lea     rdx, [rsp+480h+Buffer]; lpString2
0x18002d9ca  mov     rcx, rdi; lpString1
0x18002d9cd  call    cs:__imp_lstrcmpiW
0x18002d9d4  nop     dword ptr [rax+rax+00h]
0x18002d9d9  test    eax, eax
0x18002d9db  mov     ecx, esi
0x18002d9dd  setz    cl
0x18002d9e0  mov     eax, ecx
0x18002d9e2  jmp     short loc_18002DA4D
0x18002d9e4  cmp     ebx, dword ptr [rsp+480h+var_458]
0x18002d9e8  jnz     short loc_18002DA4B
0x18002d9ea  lea     rdx, [rbp+380h+var_240]
0x18002d9f1  jmp     short loc_18002D9CA
0x18002d9f3  lea     eax, [rcx-41h]
0x18002d9f6  cmp     ax, 19h
0x18002d9fa  jbe     short loc_18002DA05
0x18002d9fc  lea     eax, [rcx-61h]
0x18002d9ff  cmp     ax, 19h
0x18002da03  ja      short loc_18002DA44
0x18002da05  cmp     word ptr [rbx+2], 3Ah ; ':'
0x18002da0a  jnz     short loc_18002DA44
0x18002da0c  mov     eax, dword ptr cs:asc_180056FB8+2; ":\\"
0x18002da12  mov     dword ptr [rsp+480h+var_458+2], eax
0x18002da16  movzx   eax, word ptr cs:asc_180056FB8+6; ""
0x18002da1d  mov     word ptr [rsp+480h+var_458], cx
0x18002da22  lea     rcx, [rsp+480h+var_458]; lpRootPathName
0x18002da27  mov     [rsp+480h+var_452], ax
0x18002da2c  call    cs:__imp_GetDriveTypeW
0x18002da33  nop     dword ptr [rax+rax+00h]
0x18002da38  test    eax, 0FFFFFFFAh
0x18002da3d  jnz     short loc_18002DA44
0x18002da3f  cmp     eax, 5
0x18002da42  jnz     short loc_18002DA4B
0x18002da44  mov     eax, 1
0x18002da49  jmp     short loc_18002DA4D
0x18002da4b  xor     eax, eax
0x18002da4d  mov     rcx, [rbp+380h+var_30]
0x18002da54  xor     rcx, rsp; StackCookie
0x18002da57  call    __security_check_cookie
0x18002da5c  add     rsp, 468h
0x18002da63  pop     rdi
0x18002da64  pop     rsi
0x18002da65  pop     rbx
0x18002da66  pop     rbp
0x18002da67  retn
```
