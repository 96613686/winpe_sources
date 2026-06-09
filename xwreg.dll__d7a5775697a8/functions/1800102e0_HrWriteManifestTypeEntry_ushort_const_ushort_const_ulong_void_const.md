# HrWriteManifestTypeEntry(ushort * const,ushort * const,ulong,void * const)

- ea: `0x1800102e0`
- end: `0x1800103fa`
- name: `?HrWriteManifestTypeEntry@@YAJQEAG0KQEAX@Z`
- size: `282`
- prototype: `int(unsigned __int16 *const, unsigned __int16 *const, unsigned int, void *const)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000b114`

## callees

- `0x180003b90`
- `0x180007820`
- `0x1800102e0`
- `0x1800105c0`
- `0x1800109d8`
- `0x1800122b0`
- `0x180012800`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180010379`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180010379`

## string_xrefs

- `0x180010326`: `    <registryKey\n        buildFilter=""\n        keyName="HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\XWizards\Factory\%S\Wrapped Interfaces\%#0*.*lx\"\n        >\n      <registryValue\n          buildFilter=""\n          name=""\n          value="%S"\n          valueType="REG_SZ"\n          />\n    </registryKey>\n`

## pseudocode

```c
__int64 __fastcall HrWriteManifestTypeEntry(
        unsigned __int16 *const a1,
        unsigned __int16 *const a2,
        int a3,
        void *const a4)
{
  unsigned int v4; // ebx
  __int64 v6; // r8
  unsigned int LastErrorHRESULT; // eax
  int v8; // r8d
  PVOID *v9; // rcx
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-1E8h] BYREF
  char Buffer[432]; // [rsp+50h] [rbp-1D8h] BYREF

  v4 = 0;
  if ( !a4 )
    goto LABEL_9;
  NumberOfBytesWritten = 0;
  sprintf_sfn(
    Buffer,
    0x1A9u,
    "    <registryKey\r\n"
    "        buildFilter=\"\"\r\n"
    "        keyName=\"HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\XWizards\\Factory\\%S\\Wrapped I"
    "nterfaces\\%#0*.*lx\\\"\r\n"
    "        >\r\n"
    "      <registryValue\r\n"
    "          buildFilter=\"\"\r\n"
    "          name=\"\"\r\n"
    "          value=\"%S\"\r\n"
    "          valueType=\"REG_SZ\"\r\n"
    "          />\r\n"
    "    </registryKey>\r\n",
    a1,
    8,
    8,
    a3,
    a2);
  if ( (unsigned int)IsDuplicateManifestFileEntry(a4, Buffer) )
    goto LABEL_9;
  v6 = -1;
  do
    ++v6;
  while ( Buffer[v6] );
  if ( WriteFile(a4, Buffer, v6, &NumberOfBytesWritten, 0) )
    goto LABEL_9;
  LastErrorHRESULT = GetLastErrorHRESULT();
  v4 = LastErrorHRESULT;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v4;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, v8, (unsigned int)Buffer, LastErrorHRESULT);
LABEL_9:
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x10) != 0 )
    WPP_SF_D(v9[2], 30, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x1800102e0  push    rbx
0x1800102e2  push    rbp
0x1800102e3  push    rdi
0x1800102e4  sub     rsp, 210h
0x1800102eb  mov     rax, cs:__security_cookie
0x1800102f2  xor     rax, rsp
0x1800102f5  mov     [rsp+228h+var_28], rax
0x1800102fd  xor     ebx, ebx
0x1800102ff  lea     rbp, WPP_GLOBAL_Control
0x180010306  mov     rdi, r9
0x180010309  test    r9, r9
0x18001030c  jz      loc_1800103B3
0x180010312  mov     [rsp+228h+var_1F0], rdx
0x180010317  lea     eax, [rbx+8]
0x18001031a  mov     [rsp+228h+var_1F8], r8d
0x18001031f  mov     r9, rcx
0x180010322  mov     [rsp+228h+var_200], eax
0x180010326  lea     r8, aRegistrykeyBui_4; "    <registryKey\r\n        buildFilter"...
0x18001032d  mov     edx, 1A9h; unsigned __int64
0x180010332  mov     dword ptr [rsp+228h+lpOverlapped], eax
0x180010336  lea     rcx, [rsp+228h+Buffer]; char *
0x18001033b  mov     [rsp+228h+NumberOfBytesWritten], ebx
0x18001033f  call    ?sprintf_sfn@@YAXPEAD_KPEBDZZ; sprintf_sfn(char *,unsigned __int64,char const *,...)
0x180010344  lea     rdx, [rsp+228h+Buffer]; char *
0x180010349  mov     rcx, rdi; hFile
0x18001034c  call    ?IsDuplicateManifestFileEntry@@YAHQEAXQEAD@Z; IsDuplicateManifestFileEntry(void * const,char * const)
0x180010351  test    eax, eax
0x180010353  jnz     short loc_1800103B3
0x180010355  lea     rax, [rsp+228h+Buffer]
0x18001035a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001035e  inc     r8; nNumberOfBytesToWrite
0x180010361  cmp     [rax+r8], bl
0x180010365  jnz     short loc_18001035E
0x180010367  lea     r9, [rsp+228h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001036c  mov     [rsp+228h+lpOverlapped], rbx; lpOverlapped
0x180010371  lea     rdx, [rsp+228h+Buffer]; lpBuffer
0x180010376  mov     rcx, rdi; hFile
0x180010379  call    cs:__imp_WriteFile
0x18001037f  test    eax, eax
0x180010381  jnz     short loc_1800103B3
0x180010383  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x180010388  mov     ebx, eax
0x18001038a  mov     rcx, cs:WPP_GLOBAL_Control
0x180010391  cmp     rcx, rbp
0x180010394  jz      short loc_1800103DD
0x180010396  test    byte ptr [rcx+1Ch], 4
0x18001039a  jz      short loc_1800103BA
0x18001039c  mov     rcx, [rcx+10h]
0x1800103a0  lea     r9, [rsp+228h+Buffer]
0x1800103a5  mov     edx, 1Dh
0x1800103aa  mov     dword ptr [rsp+228h+lpOverlapped], eax
0x1800103ae  call    WPP_SF_sD
0x1800103b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800103ba  cmp     rcx, rbp
0x1800103bd  jz      short loc_1800103DD
0x1800103bf  test    byte ptr [rcx+1Ch], 10h
0x1800103c3  jz      short loc_1800103DD
0x1800103c5  mov     rcx, [rcx+10h]
0x1800103c9  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x1800103d0  mov     edx, 1Eh
0x1800103d5  mov     r9d, ebx
0x1800103d8  call    WPP_SF_D
0x1800103dd  mov     eax, ebx
0x1800103df  mov     rcx, [rsp+228h+var_28]
0x1800103e7  xor     rcx, rsp; StackCookie
0x1800103ea  call    __security_check_cookie
0x1800103ef  add     rsp, 210h
0x1800103f6  pop     rdi
0x1800103f7  pop     rbp
0x1800103f8  pop     rbx
0x1800103f9  retn
```
