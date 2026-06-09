# cldap_open

- ea: `0x18002b800`
- end: `0x18002b8fb`
- name: `cldap_open`
- size: `251`
- prototype: `LDAP *__cdecl(PSTR HostName, ULONG PortNumber)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000b440`
- `0x18001ce90`
- `0x18002b800`
- `0x180042684`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002b861`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002b8cf`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002b861`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002b8cf`

## pseudocode

```c
LDAP *__cdecl cldap_open(PSTR HostName, ULONG PortNumber)
{
  unsigned __int16 *v2; // rbx
  LDAP *v5; // r14
  __int64 v6; // r8
  PSTR v7; // rax
  __int64 v8; // rdi
  int v9; // eax
  unsigned int cchWideChar; // ebp
  unsigned int v12; // eax
  unsigned __int64 v13; // rcx
  WCHAR *lpWideCharStr; // rax

  v2 = 0;
  if ( !HostName )
    goto LABEL_13;
  v5 = 0;
  v6 = 0x7FFFFFFF;
  v7 = HostName;
  do
  {
    if ( !*v7 )
      break;
    ++v7;
    --v6;
  }
  while ( v6 );
  v8 = (0x7FFFFFFF - v6) & -(__int64)(v6 != 0);
  if ( v6 )
  {
    v9 = MultiByteToWideChar(0, 0, HostName, v8, 0, 0);
    cchWideChar = v9;
    if ( v9 || !(_DWORD)v8 )
    {
      v12 = v9 + 1;
      if ( v12 >= cchWideChar )
      {
        v13 = 2LL * v12;
        if ( v13 <= 0xFFFFFFFF )
        {
          lpWideCharStr = (WCHAR *)ldapMalloc(v13, 1768838476);
          v2 = lpWideCharStr;
          if ( lpWideCharStr )
          {
            lpWideCharStr[MultiByteToWideChar(0, 0, HostName, v8, lpWideCharStr, cchWideChar)] = 0;
LABEL_13:
            v5 = LdapConnectionOpen(v2, PortNumber, 1);
          }
        }
      }
    }
  }
  ldapFree((__int64)v2, 1768838476);
  return v5;
}

```

## disassembly

```asm
0x18002b800  push    rbx; cldap_open
0x18002b802  push    rbp
0x18002b803  push    rsi
0x18002b804  push    rdi
0x18002b805  push    r14
0x18002b807  push    r15
0x18002b809  sub     rsp, 38h
0x18002b80d  xor     ebx, ebx
0x18002b80f  mov     r15d, edx
0x18002b812  mov     rsi, rcx
0x18002b815  test    rcx, rcx
0x18002b818  jz      loc_18002B8E5
0x18002b81e  mov     r9d, 7FFFFFFFh
0x18002b824  xor     r14d, r14d
0x18002b827  mov     r8d, r9d
0x18002b82a  mov     rax, rcx
0x18002b82d  cmp     [rax], bl
0x18002b82f  jz      short loc_18002B83A
0x18002b831  inc     rax
0x18002b834  sub     r8, 1
0x18002b838  jnz     short loc_18002B82D
0x18002b83a  sub     r9, r8
0x18002b83d  mov     rax, r8
0x18002b840  neg     rax
0x18002b843  sbb     rdi, rdi
0x18002b846  and     rdi, r9
0x18002b849  test    r8, r8
0x18002b84c  jz      short loc_18002B877
0x18002b84e  mov     [rsp+68h+cchWideChar], ebx; cchWideChar
0x18002b852  mov     r9d, edi; cbMultiByte
0x18002b855  mov     r8, rsi; lpMultiByteStr
0x18002b858  mov     [rsp+68h+lpWideCharStr], rbx; lpWideCharStr
0x18002b85d  xor     edx, edx; dwFlags
0x18002b85f  xor     ecx, ecx; CodePage
0x18002b861  call    cs:__imp_MultiByteToWideChar
0x18002b868  nop     dword ptr [rax+rax+00h]
0x18002b86d  mov     ebp, eax
0x18002b86f  test    eax, eax
0x18002b871  jnz     short loc_18002B895
0x18002b873  test    edi, edi
0x18002b875  jz      short loc_18002B895
0x18002b877  mov     edx, 696E554Ch
0x18002b87c  mov     rcx, rbx
0x18002b87f  call    ldapFree
0x18002b884  mov     rax, r14
0x18002b887  add     rsp, 38h
0x18002b88b  pop     r15
0x18002b88d  pop     r14
0x18002b88f  pop     rdi
0x18002b890  pop     rsi
0x18002b891  pop     rbp
0x18002b892  pop     rbx
0x18002b893  retn
0x18002b895  inc     eax
0x18002b897  cmp     eax, ebp
0x18002b899  jb      short loc_18002B877
0x18002b89b  mov     ecx, eax
0x18002b89d  mov     eax, 0FFFFFFFFh
0x18002b8a2  add     rcx, rcx
0x18002b8a5  cmp     rcx, rax
0x18002b8a8  ja      short loc_18002B877
0x18002b8aa  mov     edx, 696E554Ch
0x18002b8af  call    ldapMalloc
0x18002b8b4  mov     rbx, rax
0x18002b8b7  test    rax, rax
0x18002b8ba  jz      short loc_18002B877
0x18002b8bc  mov     [rsp+68h+cchWideChar], ebp; cchWideChar
0x18002b8c0  mov     r9d, edi; cbMultiByte
0x18002b8c3  mov     r8, rsi; lpMultiByteStr
0x18002b8c6  mov     [rsp+68h+lpWideCharStr], rax; lpWideCharStr
0x18002b8cb  xor     edx, edx; dwFlags
0x18002b8cd  xor     ecx, ecx; CodePage
0x18002b8cf  call    cs:__imp_MultiByteToWideChar
0x18002b8d6  nop     dword ptr [rax+rax+00h]
0x18002b8db  mov     r9d, eax
0x18002b8de  xor     ecx, ecx
0x18002b8e0  mov     [rbx+r9*2], cx
0x18002b8e5  mov     r8b, 1; unsigned __int8
0x18002b8e8  mov     edx, r15d; unsigned int
0x18002b8eb  mov     rcx, rbx; Src
0x18002b8ee  call    ?LdapConnectionOpen@@YAPEAUldap@@PEAGKE@Z; LdapConnectionOpen(ushort *,ulong,uchar)
0x18002b8f3  mov     r14, rax
0x18002b8f6  jmp     loc_18002B877
```
