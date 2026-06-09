# WriteRootVersion(IMSAdminBaseW *)

- ea: `0x18002ad40`
- end: `0x18002aec3`
- name: `?WriteRootVersion@@YAJPEAUIMSAdminBaseW@@@Z`
- size: `387`
- prototype: `__int64 __fastcall(struct IMSAdminBaseW *)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180028744`
- `0x180028ef4`
- `0x18002aaec`

## callees

- `0x180027ae0`
- `0x18002ad40`
- `0x18004d030`
- `0x18004d690`
- `0x18004f048`
- `0x18004f21c`
- `0x18004f22c`
- `0x180064810`
- `0x1800653c0`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x18002ae2d`
- `KERNEL32!lstrlenW` at `0x18002ae2d`
- `ADVAPI32!RegCloseKey` at `0x18002ae88`
- `ADVAPI32!RegCloseKey` at `0x18002ae88`
- `ADVAPI32!RegCreateKeyExW` at `0x18002ae0e`
- `ADVAPI32!RegCreateKeyExW` at `0x18002ae0e`
- `ADVAPI32!RegSetValueExW` at `0x18002ae6b`
- `ADVAPI32!RegSetValueExW` at `0x18002ae6b`

## pseudocode

```c
__int64 __fastcall WriteRootVersion(struct IMSAdminBaseW *a1)
{
  ASPNETVER *v2; // rax
  ASPNETVER *v3; // rbx
  unsigned int RootVersion; // edi
  LSTATUS v5; // eax
  DWORD v6; // eax
  HKEY hKey; // [rsp+50h] [rbp-238h] BYREF
  WCHAR String[264]; // [rsp+60h] [rbp-228h] BYREF

  hKey = 0;
  v2 = (ASPNETVER *)MemAlloc(0x14u);
  if ( !v2 )
  {
    v3 = 0;
    goto LABEL_14;
  }
  v3 = ASPNETVER::ASPNETVER(v2);
  if ( !v3 )
  {
LABEL_14:
    RootVersion = -2147024882;
    goto LABEL_15;
  }
  memset_0(String, 0, 0x208u);
  RootVersion = GetRootVersion(a1, v3);
  if ( RootVersion )
  {
    ASPNETVER::Reset(v3);
    RootVersion = 0;
  }
  *((_DWORD *)v3 + 3) = 0;
  ASPNETVER::ToString(v3, String, 259);
  v5 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\ASP.NET", 0, (LPWSTR)&Class, 0, 0x20006u, 0, &hKey, 0);
  if ( v5 )
    goto LABEL_6;
  v6 = 2 * lstrlenW(String) + 2;
  if ( v6 > 0x208 )
  {
    RootVersion = -2147418113;
    goto LABEL_15;
  }
  v5 = RegSetValueExW(hKey, L"RootVer", 0, 1u, (const BYTE *)String, v6);
  if ( v5 )
  {
LABEL_6:
    RootVersion = (unsigned __int16)v5 | 0x80070000;
    if ( v5 <= 0 )
      RootVersion = v5;
  }
LABEL_15:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v3 )
    operator delete(v3, 0x14u);
  return RootVersion;
}

```

## disassembly

```asm
0x18002ad40  mov     [rsp+arg_8], rbx
0x18002ad45  push    rdi
0x18002ad46  sub     rsp, 280h
0x18002ad4d  mov     rax, cs:__security_cookie
0x18002ad54  xor     rax, rsp
0x18002ad57  mov     [rsp+288h+var_18], rax
0x18002ad5f  and     [rsp+288h+hKey], 0
0x18002ad65  mov     rdi, rcx
0x18002ad68  mov     ecx, 14h; unsigned __int64
0x18002ad6d  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x18002ad72  test    rax, rax
0x18002ad75  jz      loc_18002AE77
0x18002ad7b  mov     rcx, rax; this
0x18002ad7e  call    ??0ASPNETVER@@QEAA@XZ; ASPNETVER::ASPNETVER(void)
0x18002ad83  mov     rbx, rax
0x18002ad86  test    rax, rax
0x18002ad89  jz      loc_18002AE79
0x18002ad8f  xor     edx, edx; Val
0x18002ad91  lea     rcx, [rsp+288h+String]; void *
0x18002ad96  mov     r8d, 208h; Size
0x18002ad9c  call    memset_0
0x18002ada1  mov     rdx, rbx; struct ASPNETVER *
0x18002ada4  mov     rcx, rdi; struct IMSAdminBaseW *
0x18002ada7  call    ?GetRootVersion@@YAJPEAUIMSAdminBaseW@@PEAVASPNETVER@@@Z; GetRootVersion(IMSAdminBaseW *,ASPNETVER *)
0x18002adac  mov     edi, eax
0x18002adae  test    eax, eax
0x18002adb0  jz      short loc_18002ADBC
0x18002adb2  mov     rcx, rbx; this
0x18002adb5  call    ?Reset@ASPNETVER@@QEAAXXZ; ASPNETVER::Reset(void)
0x18002adba  xor     edi, edi
0x18002adbc  and     dword ptr [rbx+0Ch], 0
0x18002adc0  lea     rdx, [rsp+288h+String]; unsigned __int16 *
0x18002adc5  mov     r8d, 103h; int
0x18002adcb  mov     rcx, rbx; this
0x18002adce  call    ?ToString@ASPNETVER@@QEAAHPEAGH@Z; ASPNETVER::ToString(ushort *,int)
0x18002add3  and     [rsp+288h+var_248], 0
0x18002add9  lea     rax, [rsp+288h+hKey]
0x18002adde  mov     [rsp+288h+phkResult], rax; phkResult
0x18002ade3  lea     r9, Class; lpClass
0x18002adea  and     [rsp+288h+var_258], 0
0x18002adf0  lea     rdx, aSoftwareMicros_9; "Software\\Microsoft\\ASP.NET"
0x18002adf7  mov     [rsp+288h+samDesired], 20006h; samDesired
0x18002adff  xor     r8d, r8d; Reserved
0x18002ae02  and     dword ptr [rsp+288h+lpData], 0
0x18002ae07  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002ae0e  call    cs:__imp_RegCreateKeyExW
0x18002ae14  test    eax, eax
0x18002ae16  jz      short loc_18002AE28
0x18002ae18  movzx   edi, ax
0x18002ae1b  or      edi, 80070000h
0x18002ae21  test    eax, eax
0x18002ae23  cmovle  edi, eax
0x18002ae26  jmp     short loc_18002AE7E
0x18002ae28  lea     rcx, [rsp+288h+String]; lpString
0x18002ae2d  call    cs:__imp_lstrlenW
0x18002ae33  lea     eax, ds:2[rax*2]
0x18002ae3a  cmp     eax, 208h
0x18002ae3f  jbe     short loc_18002AE48
0x18002ae41  mov     edi, 8000FFFFh
0x18002ae46  jmp     short loc_18002AE7E
0x18002ae48  mov     rcx, [rsp+288h+hKey]; hKey
0x18002ae4d  lea     rdx, aRootver; "RootVer"
0x18002ae54  mov     [rsp+288h+samDesired], eax; cbData
0x18002ae58  mov     r9d, 1; dwType
0x18002ae5e  lea     rax, [rsp+288h+String]
0x18002ae63  xor     r8d, r8d; Reserved
0x18002ae66  mov     [rsp+288h+lpData], rax; lpData
0x18002ae6b  call    cs:__imp_RegSetValueExW
0x18002ae71  test    eax, eax
0x18002ae73  jz      short loc_18002AE7E
0x18002ae75  jmp     short loc_18002AE18
0x18002ae77  xor     ebx, ebx
0x18002ae79  mov     edi, 8007000Eh
0x18002ae7e  mov     rcx, [rsp+288h+hKey]; hKey
0x18002ae83  test    rcx, rcx
0x18002ae86  jz      short loc_18002AE8E
0x18002ae88  call    cs:__imp_RegCloseKey
0x18002ae8e  test    rbx, rbx
0x18002ae91  jz      short loc_18002AEA0
0x18002ae93  mov     edx, 14h; unsigned __int64
0x18002ae98  mov     rcx, rbx; void *
0x18002ae9b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002aea0  mov     eax, edi
0x18002aea2  mov     rcx, [rsp+288h+var_18]
0x18002aeaa  xor     rcx, rsp; StackCookie
0x18002aead  call    __security_check_cookie
0x18002aeb2  mov     rbx, [rsp+288h+arg_8]
0x18002aeba  add     rsp, 280h
0x18002aec1  pop     rdi
0x18002aec2  retn
```
