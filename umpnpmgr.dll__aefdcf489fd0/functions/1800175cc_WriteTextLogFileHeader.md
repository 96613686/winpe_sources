# WriteTextLogFileHeader

- ea: `0x1800175cc`
- end: `0x1800176ff`
- name: `WriteTextLogFileHeader`
- size: `307`
- prototype: `HRESULT __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, service_task, installer_update`

## callers

- `0x18000b360`

## callees

- `0x18000fb9c`
- `0x1800175cc`
- `0x18001893e`
- `0x180018970`

## import_xrefs

- `ntdll!RtlGetVersion` at `0x18001761c`
- `ntdll!RtlGetVersion` at `0x180017633`
- `ntdll!RtlGetVersion` at `0x18001761c`
- `ntdll!RtlGetVersion` at `0x180017633`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800176d9`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800176d9`

## string_xrefs

- `0x180017690`: `[Device Install Log]\n     OS Version = %d.%d.%d\n     Service Pack = %d.%d\n     Suite = 0x%04x\n     ProductType = %d\n     Architecture = %s\n\n[BeginLog]\n`

## pseudocode

```c
HRESULT __fastcall WriteTextLogFileHeader(HANDLE hFile)
{
  HRESULT result; // eax
  __int64 v3; // r8
  DWORD NumberOfBytesWritten; // [rsp+60h] [rbp-A0h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v6; // [rsp+184h] [rbp+84h]
  unsigned __int16 v7; // [rsp+186h] [rbp+86h]
  unsigned __int16 v8; // [rsp+188h] [rbp+88h]
  unsigned __int8 v9; // [rsp+18Ah] [rbp+8Ah]
  char pszDest[256]; // [rsp+190h] [rbp+90h] BYREF

  NumberOfBytesWritten = 0;
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  if ( RtlGetVersion(&VersionInformation) >= 0
    || (VersionInformation.dwOSVersionInfoSize = 276, result = RtlGetVersion(&VersionInformation), result >= 0) )
  {
    result = StringCchPrintfA(
               pszDest,
               0xFFu,
               "[Device Install Log]\r\n"
               "     OS Version = %d.%d.%d\r\n"
               "     Service Pack = %d.%d\r\n"
               "     Suite = 0x%04x\r\n"
               "     ProductType = %d\r\n"
               "     Architecture = %s\r\n"
               "\r\n"
               "[BeginLog]\r\n",
               VersionInformation.dwMajorVersion,
               VersionInformation.dwMinorVersion,
               VersionInformation.dwBuildNumber,
               v6,
               v7,
               v8,
               v9,
               "amd64");
    if ( result >= 0 )
    {
      v3 = -1;
      do
        ++v3;
      while ( pszDest[v3] );
      return WriteFile(hFile, pszDest, v3, &NumberOfBytesWritten, 0);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800175cc  mov     [rsp-8+arg_8], rbx
0x1800175d1  push    rbp
0x1800175d2  lea     rbp, [rsp-1A0h]
0x1800175da  sub     rsp, 2A0h
0x1800175e1  mov     rax, cs:__security_cookie
0x1800175e8  xor     rax, rsp
0x1800175eb  mov     [rbp+1A0h+var_10], rax
0x1800175f2  mov     rbx, rcx
0x1800175f5  mov     [rsp+2A0h+NumberOfBytesWritten], 0
0x1800175fd  lea     rcx, [rsp+2A0h+VersionInformation.dwMajorVersion]; void *
0x180017602  xor     edx, edx; Val
0x180017604  mov     r8d, 118h; Size
0x18001760a  call    memset_0
0x18001760f  lea     rcx, [rsp+2A0h+VersionInformation]; lpVersionInformation
0x180017614  mov     [rsp+2A0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x18001761c  call    cs:__imp_RtlGetVersion
0x180017622  test    eax, eax
0x180017624  jns     short loc_180017641
0x180017626  lea     rcx, [rsp+2A0h+VersionInformation]; lpVersionInformation
0x18001762b  mov     [rsp+2A0h+VersionInformation.dwOSVersionInfoSize], 114h
0x180017633  call    cs:__imp_RtlGetVersion
0x180017639  test    eax, eax
0x18001763b  js      loc_1800176DF
0x180017641  movzx   eax, [rbp+1A0h+var_116]
0x180017648  lea     r9, aAmd64; "amd64"
0x18001764f  movzx   ecx, [rbp+1A0h+var_118]
0x180017656  movzx   edx, [rbp+1A0h+var_11A]
0x18001765d  movzx   r8d, [rbp+1A0h+var_11C]
0x180017665  mov     [rsp+2A0h+var_250], r9
0x18001766a  mov     r9d, [rsp+2A0h+VersionInformation.dwMajorVersion]
0x18001766f  mov     [rsp+2A0h+var_258], eax
0x180017673  mov     eax, [rsp+2A0h+VersionInformation.dwBuildNumber]
0x180017677  mov     [rsp+2A0h+var_260], ecx
0x18001767b  lea     rcx, [rbp+1A0h+pszDest]; pszDest
0x180017682  mov     [rsp+2A0h+var_268], edx
0x180017686  mov     edx, 0FFh; cchDest
0x18001768b  mov     [rsp+2A0h+var_270], r8d
0x180017690  lea     r8, aDeviceInstallL; "[Device Install Log]\r\n     OS Version"...
0x180017697  mov     [rsp+2A0h+var_278], eax
0x18001769b  mov     eax, [rsp+2A0h+VersionInformation.dwMinorVersion]
0x18001769f  mov     dword ptr [rsp+2A0h+lpOverlapped], eax
0x1800176a3  call    StringCchPrintfA
0x1800176a8  test    eax, eax
0x1800176aa  js      short loc_1800176DF
0x1800176ac  lea     rax, [rbp+1A0h+pszDest]
0x1800176b3  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800176b7  inc     r8; nNumberOfBytesToWrite
0x1800176ba  cmp     byte ptr [rax+r8], 0
0x1800176bf  jnz     short loc_1800176B7
0x1800176c1  lea     r9, [rsp+2A0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800176c6  mov     [rsp+2A0h+lpOverlapped], 0; lpOverlapped
0x1800176cf  lea     rdx, [rbp+1A0h+pszDest]; lpBuffer
0x1800176d6  mov     rcx, rbx; hFile
0x1800176d9  call    cs:__imp_WriteFile
0x1800176df  mov     rcx, [rbp+1A0h+var_10]
0x1800176e6  xor     rcx, rsp; StackCookie
0x1800176e9  call    __security_check_cookie
0x1800176ee  mov     rbx, [rsp+2A0h+arg_8]
0x1800176f6  add     rsp, 2A0h
0x1800176fd  pop     rbp
0x1800176fe  retn
```
