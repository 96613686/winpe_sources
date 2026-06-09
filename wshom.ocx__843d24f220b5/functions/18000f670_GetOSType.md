# GetOSType

- ea: `0x18000f670`
- end: `0x18000f78f`
- name: `GetOSType`
- size: `287`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000fb64`
- `0x18000fc7c`

## callees

- `0x18000f670`
- `0x180010212`
- `0x180010250`

## import_xrefs

- `KERNEL32!GetVersionExW` at `0x18000f6b6`
- `KERNEL32!GetVersionExW` at `0x18000f6cd`
- `KERNEL32!GetVersionExW` at `0x18000f6b6`
- `KERNEL32!GetVersionExW` at `0x18000f6cd`

## pseudocode

```c
__int64 GetOSType()
{
  __int64 result; // rax
  int v1; // edx
  unsigned __int16 v2; // cx
  int v3; // eax
  _OSVERSIONINFOW VersionInformation; // [rsp+20h] [rbp-138h] BYREF
  unsigned __int16 v5; // [rsp+134h] [rbp-24h]

  result = (unsigned int)dword_180018C18;
  if ( !dword_180018C18 )
  {
    memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
    VersionInformation.dwOSVersionInfoSize = 284;
    if ( !GetVersionExW(&VersionInformation) )
    {
      VersionInformation.dwOSVersionInfoSize = 276;
      GetVersionExW(&VersionInformation);
    }
    result = 0;
    dword_180018C18 = 0;
    if ( VersionInformation.dwPlatformId != 1 )
    {
      if ( VersionInformation.dwPlatformId != 2 )
        return result;
      if ( VersionInformation.dwMajorVersion == 5 )
      {
        if ( VersionInformation.dwMinorVersion )
        {
          if ( VersionInformation.dwMinorVersion == 1 )
          {
            v1 = 8;
            v2 = 2;
          }
          else
          {
            if ( VersionInformation.dwMinorVersion != 2 )
            {
              result = 20;
LABEL_26:
              dword_180018C18 = result;
              return result;
            }
            v1 = 16;
            v2 = 1;
          }
          v3 = 0;
          if ( v5 >= v2 )
            v3 = v1;
          result = v3 | 4u;
          goto LABEL_26;
        }
        result = 4;
        goto LABEL_26;
      }
      if ( VersionInformation.dwMajorVersion > 4 )
      {
        result = 32;
        goto LABEL_26;
      }
      result = 2;
      dword_180018C18 = 2;
    }
    if ( VersionInformation.dwMajorVersion == 4
      && (!VersionInformation.dwMinorVersion
       || VersionInformation.dwMinorVersion == 10
       || VersionInformation.dwMinorVersion == 90) )
    {
      result = 1;
      dword_180018C18 = 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000f670  sub     rsp, 158h
0x18000f677  mov     rax, cs:__security_cookie
0x18000f67e  xor     rax, rsp
0x18000f681  mov     [rsp+158h+var_18], rax
0x18000f689  mov     eax, cs:dword_180018C18
0x18000f68f  test    eax, eax
0x18000f691  jnz     loc_18000F76A
0x18000f697  xor     edx, edx; Val
0x18000f699  lea     rcx, [rsp+158h+VersionInformation.dwMajorVersion]; void *
0x18000f69e  mov     r8d, 118h; Size
0x18000f6a4  call    memset_0
0x18000f6a9  lea     rcx, [rsp+158h+VersionInformation]; lpVersionInformation
0x18000f6ae  mov     [rsp+158h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x18000f6b6  call    cs:__imp_GetVersionExW
0x18000f6bc  test    eax, eax
0x18000f6be  jnz     short loc_18000F6D3
0x18000f6c0  lea     rcx, [rsp+158h+VersionInformation]; lpVersionInformation
0x18000f6c5  mov     [rsp+158h+VersionInformation.dwOSVersionInfoSize], 114h
0x18000f6cd  call    cs:__imp_GetVersionExW
0x18000f6d3  mov     ecx, [rsp+158h+VersionInformation.dwPlatformId]
0x18000f6d7  xor     eax, eax
0x18000f6d9  mov     edx, [rsp+158h+VersionInformation.dwMajorVersion]
0x18000f6dd  mov     cs:dword_180018C18, eax
0x18000f6e3  lea     r8d, [rax+4]
0x18000f6e7  sub     ecx, 1
0x18000f6ea  jz      short loc_18000F746
0x18000f6ec  cmp     ecx, 1
0x18000f6ef  jnz     short loc_18000F76A
0x18000f6f1  cmp     edx, 5
0x18000f6f4  jnz     short loc_18000F734
0x18000f6f6  mov     eax, [rsp+158h+VersionInformation.dwMinorVersion]
0x18000f6fa  test    eax, eax
0x18000f6fc  jz      short loc_18000F72F
0x18000f6fe  sub     eax, ecx
0x18000f700  jz      short loc_18000F715
0x18000f702  cmp     eax, ecx
0x18000f704  jz      short loc_18000F70B
0x18000f706  lea     eax, [rdx+0Fh]
0x18000f709  jmp     short loc_18000F787
0x18000f70b  mov     edx, 10h
0x18000f710  lea     ecx, [rdx-0Fh]
0x18000f713  jmp     short loc_18000F71D
0x18000f715  mov     edx, 8
0x18000f71a  lea     ecx, [rdx-6]
0x18000f71d  xor     eax, eax
0x18000f71f  cmp     [rsp+158h+var_24], cx
0x18000f727  cmovnb  eax, edx
0x18000f72a  or      eax, r8d
0x18000f72d  jmp     short loc_18000F787
0x18000f72f  mov     eax, r8d
0x18000f732  jmp     short loc_18000F787
0x18000f734  cmp     edx, r8d
0x18000f737  ja      short loc_18000F782
0x18000f739  mov     ecx, 2
0x18000f73e  mov     eax, ecx
0x18000f740  mov     cs:dword_180018C18, ecx
0x18000f746  cmp     edx, r8d
0x18000f749  jnz     short loc_18000F76A
0x18000f74b  mov     ecx, [rsp+158h+VersionInformation.dwMinorVersion]
0x18000f74f  test    ecx, ecx
0x18000f751  jz      short loc_18000F75D
0x18000f753  cmp     ecx, 0Ah
0x18000f756  jz      short loc_18000F75D
0x18000f758  cmp     ecx, 5Ah ; 'Z'
0x18000f75b  jnz     short loc_18000F76A
0x18000f75d  mov     ecx, 1
0x18000f762  mov     eax, ecx
0x18000f764  mov     cs:dword_180018C18, ecx
0x18000f76a  mov     rcx, [rsp+158h+var_18]
0x18000f772  xor     rcx, rsp; StackCookie
0x18000f775  call    __security_check_cookie
0x18000f77a  add     rsp, 158h
0x18000f781  retn
0x18000f782  mov     eax, 20h ; ' '
0x18000f787  mov     cs:dword_180018C18, eax
0x18000f78d  jmp     short loc_18000F76A
```
