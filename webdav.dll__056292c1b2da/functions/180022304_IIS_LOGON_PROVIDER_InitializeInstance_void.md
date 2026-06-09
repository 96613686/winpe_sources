# IIS_LOGON_PROVIDER::InitializeInstance(void)

- ea: `0x180022304`
- end: `0x1800223cf`
- name: `?InitializeInstance@IIS_LOGON_PROVIDER@@QEAAJXZ`
- size: `203`
- prototype: `__int64 __fastcall(IIS_LOGON_PROVIDER *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18001ccc0`

## callees

- `0x1800219ec`
- `0x180022304`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800223a4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800223a4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022356`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022356`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180022384`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180022384`

## string_xrefs

- `0x180022333`: `System\CurrentControlSet\Services\inetinfo\Parameters`

## pseudocode

```c
__int64 __fastcall IIS_LOGON_PROVIDER::InitializeInstance(IIS_LOGON_PROVIDER *this)
{
  wchar_t *v1; // rbx
  LSTATUS v2; // eax
  __int64 result; // rax
  DWORD Type; // [rsp+50h] [rbp+18h] BYREF
  int v5; // [rsp+54h] [rbp+1Ch]
  int Data; // [rsp+58h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  v5 = HIDWORD(this);
  v1 = IIS_VDIR::sm_LogonProvider;
  hKey = 0;
  Data = 0;
  Type = 0;
  cbData = 4;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\inetinfo\\Parameters",
          0,
          0x20019u,
          &hKey) )
  {
    v2 = RegQueryValueExW(hKey, L"LastPriorityUPNLogon", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( !v2 && Type == 4 )
    {
      LOBYTE(v2) = Data != 0;
      *((_DWORD *)v1 + 641) = v2;
    }
    RegCloseKey(hKey);
    hKey = 0;
  }
  result = IIS_LOGON_PROVIDER::GetDefaultDomainName(v1);
  if ( (int)result >= 0 )
    *((_DWORD *)v1 + 642) = 1;
  return result;
}

```

## disassembly

```asm
0x180022304  mov     qword ptr [rsp-10h+Type], rcx
0x180022309  push    rbp
0x18002230a  push    rbx
0x18002230b  mov     rbp, rsp
0x18002230e  sub     rsp, 38h
0x180022312  mov     rbx, cs:?sm_LogonProvider@IIS_VDIR@@0PEAVIIS_LOGON_PROVIDER@@EA; IIS_LOGON_PROVIDER * IIS_VDIR::sm_LogonProvider
0x180022319  lea     rax, [rbp+hKey]
0x18002231d  mov     r9d, 20019h; samDesired
0x180022323  mov     [rsp+38h+phkResult], rax; phkResult
0x180022328  xor     r8d, r8d; ulOptions
0x18002232b  mov     [rbp+hKey], 0
0x180022333  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\in"...
0x18002233a  mov     [rbp+Data], 0
0x180022341  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180022348  mov     [rbp+Type], 0
0x18002234f  mov     [rbp+cbData], 4
0x180022356  call    cs:__imp_RegOpenKeyExW
0x18002235c  test    eax, eax
0x18002235e  jnz     short loc_1800223B2
0x180022360  mov     rcx, [rbp+hKey]; hKey
0x180022364  lea     rax, [rbp+cbData]
0x180022368  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18002236d  lea     r9, [rbp+Type]; lpType
0x180022371  lea     rax, [rbp+Data]
0x180022375  xor     r8d, r8d; lpReserved
0x180022378  lea     rdx, aLastpriorityup; "LastPriorityUPNLogon"
0x18002237f  mov     [rsp+38h+phkResult], rax; lpData
0x180022384  call    cs:__imp_RegQueryValueExW
0x18002238a  test    eax, eax
0x18002238c  jnz     short loc_1800223A0
0x18002238e  cmp     [rbp+Type], 4
0x180022392  jnz     short loc_1800223A0
0x180022394  cmp     [rbp+Data], eax
0x180022397  setnz   al
0x18002239a  mov     [rbx+0A04h], eax
0x1800223a0  mov     rcx, [rbp+hKey]; hKey
0x1800223a4  call    cs:__imp_RegCloseKey
0x1800223aa  mov     [rbp+hKey], 0
0x1800223b2  mov     rcx, rbx; Destination
0x1800223b5  call    ?GetDefaultDomainName@IIS_LOGON_PROVIDER@@AEAAJXZ; IIS_LOGON_PROVIDER::GetDefaultDomainName(void)
0x1800223ba  test    eax, eax
0x1800223bc  js      short loc_1800223C8
0x1800223be  mov     dword ptr [rbx+0A08h], 1
0x1800223c8  add     rsp, 38h
0x1800223cc  pop     rbx
0x1800223cd  pop     rbp
0x1800223ce  retn
```
