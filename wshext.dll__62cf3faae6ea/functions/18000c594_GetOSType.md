# GetOSType

- ea: `0x18000c594`
- end: `0x18000c6b3`
- name: `GetOSType`
- size: `287`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ca88`
- `0x18000cba0`

## callees

- `0x18000c594`
- `0x18000d17e`
- `0x18000d1c0`

## import_xrefs

- `KERNEL32!GetVersionExW` at `0x18000c5da`
- `KERNEL32!GetVersionExW` at `0x18000c5f1`
- `KERNEL32!GetVersionExW` at `0x18000c5da`
- `KERNEL32!GetVersionExW` at `0x18000c5f1`

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

  result = (unsigned int)dword_180014910;
  if ( !dword_180014910 )
  {
    memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
    VersionInformation.dwOSVersionInfoSize = 284;
    if ( !GetVersionExW(&VersionInformation) )
    {
      VersionInformation.dwOSVersionInfoSize = 276;
      GetVersionExW(&VersionInformation);
    }
    result = 0;
    dword_180014910 = 0;
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
              dword_180014910 = result;
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
      dword_180014910 = 2;
    }
    if ( VersionInformation.dwMajorVersion == 4
      && (!VersionInformation.dwMinorVersion
       || VersionInformation.dwMinorVersion == 10
       || VersionInformation.dwMinorVersion == 90) )
    {
      result = 1;
      dword_180014910 = 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000c594  sub     rsp, 158h
0x18000c59b  mov     rax, cs:__security_cookie
0x18000c5a2  xor     rax, rsp
0x18000c5a5  mov     [rsp+158h+var_18], rax
0x18000c5ad  mov     eax, cs:dword_180014910
0x18000c5b3  test    eax, eax
0x18000c5b5  jnz     loc_18000C68E
0x18000c5bb  xor     edx, edx; Val
0x18000c5bd  lea     rcx, [rsp+158h+VersionInformation.dwMajorVersion]; void *
0x18000c5c2  mov     r8d, 118h; Size
0x18000c5c8  call    memset_0
0x18000c5cd  lea     rcx, [rsp+158h+VersionInformation]; lpVersionInformation
0x18000c5d2  mov     [rsp+158h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x18000c5da  call    cs:__imp_GetVersionExW
0x18000c5e0  test    eax, eax
0x18000c5e2  jnz     short loc_18000C5F7
0x18000c5e4  lea     rcx, [rsp+158h+VersionInformation]; lpVersionInformation
0x18000c5e9  mov     [rsp+158h+VersionInformation.dwOSVersionInfoSize], 114h
0x18000c5f1  call    cs:__imp_GetVersionExW
0x18000c5f7  mov     ecx, [rsp+158h+VersionInformation.dwPlatformId]
0x18000c5fb  xor     eax, eax
0x18000c5fd  mov     edx, [rsp+158h+VersionInformation.dwMajorVersion]
0x18000c601  mov     cs:dword_180014910, eax
0x18000c607  lea     r8d, [rax+4]
0x18000c60b  sub     ecx, 1
0x18000c60e  jz      short loc_18000C66A
0x18000c610  cmp     ecx, 1
0x18000c613  jnz     short loc_18000C68E
0x18000c615  cmp     edx, 5
0x18000c618  jnz     short loc_18000C658
0x18000c61a  mov     eax, [rsp+158h+VersionInformation.dwMinorVersion]
0x18000c61e  test    eax, eax
0x18000c620  jz      short loc_18000C653
0x18000c622  sub     eax, ecx
0x18000c624  jz      short loc_18000C639
0x18000c626  cmp     eax, ecx
0x18000c628  jz      short loc_18000C62F
0x18000c62a  lea     eax, [rdx+0Fh]
0x18000c62d  jmp     short loc_18000C6AB
0x18000c62f  mov     edx, 10h
0x18000c634  lea     ecx, [rdx-0Fh]
0x18000c637  jmp     short loc_18000C641
0x18000c639  mov     edx, 8
0x18000c63e  lea     ecx, [rdx-6]
0x18000c641  xor     eax, eax
0x18000c643  cmp     [rsp+158h+var_24], cx
0x18000c64b  cmovnb  eax, edx
0x18000c64e  or      eax, r8d
0x18000c651  jmp     short loc_18000C6AB
0x18000c653  mov     eax, r8d
0x18000c656  jmp     short loc_18000C6AB
0x18000c658  cmp     edx, r8d
0x18000c65b  ja      short loc_18000C6A6
0x18000c65d  mov     ecx, 2
0x18000c662  mov     eax, ecx
0x18000c664  mov     cs:dword_180014910, ecx
0x18000c66a  cmp     edx, r8d
0x18000c66d  jnz     short loc_18000C68E
0x18000c66f  mov     ecx, [rsp+158h+VersionInformation.dwMinorVersion]
0x18000c673  test    ecx, ecx
0x18000c675  jz      short loc_18000C681
0x18000c677  cmp     ecx, 0Ah
0x18000c67a  jz      short loc_18000C681
0x18000c67c  cmp     ecx, 5Ah ; 'Z'
0x18000c67f  jnz     short loc_18000C68E
0x18000c681  mov     ecx, 1
0x18000c686  mov     eax, ecx
0x18000c688  mov     cs:dword_180014910, ecx
0x18000c68e  mov     rcx, [rsp+158h+var_18]
0x18000c696  xor     rcx, rsp; StackCookie
0x18000c699  call    __security_check_cookie
0x18000c69e  add     rsp, 158h
0x18000c6a5  retn
0x18000c6a6  mov     eax, 20h ; ' '
0x18000c6ab  mov     cs:dword_180014910, eax
0x18000c6b1  jmp     short loc_18000C68E
```
