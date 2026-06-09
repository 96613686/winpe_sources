# ATL::CAtlServiceModuleT<CBlbServiceModule,102>::Install(void)

- ea: `0x14006318c`
- end: `0x140063352`
- name: `?Install@?$CAtlServiceModuleT@VCBlbServiceModule@@$0GG@@ATL@@QEAAHXZ`
- size: `454`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update`

## callers

- `0x140065ad0`

## callees

- `0x1400073a8`
- `0x1400088f0`
- `0x1400606fc`
- `0x14006318c`
- `0x140063438`
- `0x140134d20`

## import_xrefs

- `ADVAPI32!OpenSCManagerW` at `0x140063218`
- `ADVAPI32!OpenSCManagerW` at `0x140063218`
- `ADVAPI32!CreateServiceW` at `0x1400632fb`
- `ADVAPI32!CreateServiceW` at `0x1400632fb`
- `ADVAPI32!CloseServiceHandle` at `0x140063309`
- `ADVAPI32!CloseServiceHandle` at `0x140063338`
- `ADVAPI32!CloseServiceHandle` at `0x140063341`
- `ADVAPI32!CloseServiceHandle` at `0x140063309`
- `ADVAPI32!CloseServiceHandle` at `0x140063338`
- `ADVAPI32!CloseServiceHandle` at `0x140063341`
- `KERNEL32!GetModuleFileNameW` at `0x1400631c9`
- `KERNEL32!GetModuleFileNameW` at `0x1400631c9`
- `USER32!MessageBoxW` at `0x140063271`
- `USER32!MessageBoxW` at `0x140063271`
- `msvcrt!wcscpy_s` at `0x140063250`
- `msvcrt!wcscpy_s` at `0x140063250`

## string_xrefs

- `0x14006323c`: `Could not open Service Manager`
- `0x140063329`: `Could not start service`

## pseudocode

```c
__int64 ATL::CAtlServiceModuleT<CBlbServiceModule,102>::Install()
{
  DWORD ModuleFileNameW; // eax
  SC_HANDLE v2; // rbx
  int v3; // r8d
  const wchar_t *v4; // r8
  errno_t v5; // eax
  SC_HANDLE v6; // rax
  int v7; // r8d
  WCHAR BinaryPathName; // [rsp+70h] [rbp-A28h] BYREF
  WCHAR Filename[263]; // [rsp+72h] [rbp-A26h] BYREF
  wchar_t Destination[1024]; // [rsp+280h] [rbp-818h] BYREF

  if ( (unsigned int)ATL::CAtlServiceModuleT<CBlbServiceModule,102>::IsInstalled() )
    return 1;
  ModuleFileNameW = GetModuleFileNameW(0, Filename, 0x104u);
  if ( ModuleFileNameW && ModuleFileNameW != 260 )
  {
    BinaryPathName = 34;
    Filename[ModuleFileNameW] = 34;
    if ( 2 * (unsigned __int64)(ModuleFileNameW + 2) >= 0x20C )
      _report_rangecheckfailure();
    Filename[ModuleFileNameW + 1] = 0;
    v2 = OpenSCManagerW(0, 0, 0xF003Fu);
    if ( v2 )
    {
      v6 = CreateServiceW(v2, &Caption, &Caption, 0xF01FFu, 0x10u, 3u, 1u, &BinaryPathName, 0, 0, L"RPCSS", 0, 0);
      if ( v6 )
      {
        CloseServiceHandle(v6);
        CloseServiceHandle(v2);
        return 1;
      }
      CloseServiceHandle(v2);
      if ( (unsigned int)ATL::AtlLoadString(0xD80Bu, Destination, v7) )
        goto LABEL_10;
      v4 = L"Could not start service";
    }
    else
    {
      if ( (unsigned int)ATL::AtlLoadString(0xD80Au, Destination, v3) )
      {
LABEL_10:
        MessageBoxW(0, Destination, &Caption, 0);
        return 0;
      }
      v4 = L"Could not open Service Manager";
    }
    v5 = wcscpy_s(Destination, 0x400u, v4);
    ATL::AtlCrtErrorCheck(v5);
    goto LABEL_10;
  }
  return 0;
}

```

## disassembly

```asm
0x14006318c  push    rbx
0x14006318e  sub     rsp, 0A90h
0x140063195  mov     rax, cs:__security_cookie
0x14006319c  xor     rax, rsp
0x14006319f  mov     [rsp+0A98h+var_18], rax
0x1400631a7  call    ?IsInstalled@?$CAtlServiceModuleT@VCBlbServiceModule@@$0GG@@ATL@@QEAAHXZ; ATL::CAtlServiceModuleT<CBlbServiceModule,102>::IsInstalled(void)
0x1400631ac  test    eax, eax
0x1400631ae  jz      short loc_1400631BA
0x1400631b0  mov     eax, 1
0x1400631b5  jmp     loc_140063279
0x1400631ba  mov     ebx, 104h
0x1400631bf  lea     rdx, [rsp+0A98h+Filename]; lpFilename
0x1400631c4  mov     r8d, ebx; nSize
0x1400631c7  xor     ecx, ecx; hModule
0x1400631c9  call    cs:__imp_GetModuleFileNameW
0x1400631cf  test    eax, eax
0x1400631d1  jz      loc_140063277
0x1400631d7  cmp     eax, ebx
0x1400631d9  jz      loc_140063277
0x1400631df  lea     ecx, [rax+1]
0x1400631e2  mov     r8d, 22h ; '"'
0x1400631e8  mov     [rsp+0A98h+BinaryPathName], r8w
0x1400631ee  mov     [rsp+rcx*2+0A98h+BinaryPathName], r8w
0x1400631f4  lea     ecx, [rax+2]
0x1400631f7  add     rcx, rcx
0x1400631fa  cmp     rcx, 20Ch
0x140063201  jnb     loc_14006334C
0x140063207  xor     eax, eax
0x140063209  xor     edx, edx; lpDatabaseName
0x14006320b  mov     [rsp+rcx+0A98h+BinaryPathName], ax
0x140063210  mov     r8d, 0F003Fh; dwDesiredAccess
0x140063216  xor     ecx, ecx; lpMachineName
0x140063218  call    cs:__imp_OpenSCManagerW
0x14006321e  mov     rbx, rax
0x140063221  test    rax, rax
0x140063224  jnz     short loc_140063292
0x140063226  lea     rdx, [rsp+0A98h+Destination]; lpBuffer
0x14006322e  mov     ecx, 0D80Ah; uID
0x140063233  call    ?AtlLoadString@ATL@@YAHIPEAGH@Z; ATL::AtlLoadString(uint,ushort *,int)
0x140063238  test    eax, eax
0x14006323a  jnz     short loc_14006325D
0x14006323c  lea     r8, aCouldNotOpenSe; "Could not open Service Manager"
0x140063243  mov     edx, 400h; SizeInWords
0x140063248  lea     rcx, [rsp+0A98h+Destination]; Destination
0x140063250  call    cs:__imp_wcscpy_s
0x140063256  mov     ecx, eax; int
0x140063258  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x14006325d  xor     r9d, r9d; uType
0x140063260  lea     r8, Caption; lpCaption
0x140063267  lea     rdx, [rsp+0A98h+Destination]; lpText
0x14006326f  xor     ecx, ecx; hWnd
0x140063271  call    cs:__imp_MessageBoxW
0x140063277  xor     eax, eax
0x140063279  mov     rcx, [rsp+0A98h+var_18]
0x140063281  xor     rcx, rsp; StackCookie
0x140063284  call    __security_check_cookie
0x140063289  add     rsp, 0A90h
0x140063290  pop     rbx
0x140063291  retn
0x140063292  mov     [rsp+0A98h+lpPassword], 0; lpPassword
0x14006329b  lea     rax, Dependencies; "RPCSS"
0x1400632a2  mov     [rsp+0A98h+lpServiceStartName], 0; lpServiceStartName
0x1400632ab  lea     r8, Caption; lpDisplayName
0x1400632b2  mov     [rsp+0A98h+lpDependencies], rax; lpDependencies
0x1400632b7  lea     rdx, Caption; lpServiceName
0x1400632be  mov     [rsp+0A98h+lpdwTagId], 0; lpdwTagId
0x1400632c7  lea     rax, [rsp+0A98h+BinaryPathName]
0x1400632cc  mov     [rsp+0A98h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x1400632d5  mov     r9d, 0F01FFh; dwDesiredAccess
0x1400632db  mov     [rsp+0A98h+lpBinaryPathName], rax; lpBinaryPathName
0x1400632e0  mov     rcx, rbx; hSCManager
0x1400632e3  mov     [rsp+0A98h+dwErrorControl], 1; dwErrorControl
0x1400632eb  mov     [rsp+0A98h+dwStartType], 3; dwStartType
0x1400632f3  mov     [rsp+0A98h+dwServiceType], 10h; dwServiceType
0x1400632fb  call    cs:__imp_CreateServiceW
0x140063301  test    rax, rax
0x140063304  jnz     short loc_140063335
0x140063306  mov     rcx, rbx; hSCObject
0x140063309  call    cs:__imp_CloseServiceHandle
0x14006330f  lea     rdx, [rsp+0A98h+Destination]; lpBuffer
0x140063317  mov     ecx, 0D80Bh; uID
0x14006331c  call    ?AtlLoadString@ATL@@YAHIPEAGH@Z; ATL::AtlLoadString(uint,ushort *,int)
0x140063321  test    eax, eax
0x140063323  jnz     loc_14006325D
0x140063329  lea     r8, aCouldNotStartS; "Could not start service"
0x140063330  jmp     loc_140063243
0x140063335  mov     rcx, rax; hSCObject
0x140063338  call    cs:__imp_CloseServiceHandle
0x14006333e  mov     rcx, rbx; hSCObject
0x140063341  call    cs:__imp_CloseServiceHandle
0x140063347  jmp     loc_1400631B0
0x14006334c  call    __report_rangecheckfailure
```
