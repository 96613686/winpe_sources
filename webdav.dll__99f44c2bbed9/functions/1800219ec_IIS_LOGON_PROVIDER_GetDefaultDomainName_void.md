# IIS_LOGON_PROVIDER::GetDefaultDomainName(void)

- ea: `0x1800219ec`
- end: `0x180021be9`
- name: `?GetDefaultDomainName@IIS_LOGON_PROVIDER@@AEAAJXZ`
- size: `509`
- prototype: `__int64 __fastcall(wchar_t *Destination)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180022304`

## callees

- `0x1800219ec`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180021b28`
- `msvcrt!wcsncpy_s` at `0x180021b28`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180021b94`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180021b94`
- `ntdll!RtlNtStatusToDosError` at `0x180021a83`
- `ntdll!RtlNtStatusToDosError` at `0x180021af6`
- `ntdll!RtlNtStatusToDosError` at `0x180021a83`
- `ntdll!RtlNtStatusToDosError` at `0x180021af6`
- `iisutil!PuDbgPrint` at `0x180021a7b`
- `iisutil!PuDbgPrint` at `0x180021aee`
- `iisutil!PuDbgPrint` at `0x180021a7b`
- `iisutil!PuDbgPrint` at `0x180021aee`
- `ADVAPI32!LsaClose` at `0x180021bd1`
- `ADVAPI32!LsaClose` at `0x180021bd1`
- `ADVAPI32!LsaOpenPolicy` at `0x180021a3b`
- `ADVAPI32!LsaOpenPolicy` at `0x180021a3b`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x180021aae`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x180021b47`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x180021aae`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x180021b47`
- `ADVAPI32!LsaFreeMemory` at `0x180021bab`
- `ADVAPI32!LsaFreeMemory` at `0x180021bbe`
- `ADVAPI32!LsaFreeMemory` at `0x180021bab`
- `ADVAPI32!LsaFreeMemory` at `0x180021bbe`

## string_xrefs

- `0x180021a69`: `cannot open lsa policy, error %08lX\n`
- `0x180021a62`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`
- `0x180021ae2`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`

## pseudocode

```c
__int64 __fastcall IIS_LOGON_PROVIDER::GetDefaultDomainName(wchar_t *Destination)
{
  NTSTATUS v2; // eax
  NTSTATUS v3; // ebx
  signed int v4; // eax
  unsigned int v5; // ebx
  int v6; // ebx
  __int64 v7; // r8
  signed int v8; // eax
  PVOID v10; // [rsp+30h] [rbp-40h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-38h] BYREF
  DWORD nSize; // [rsp+98h] [rbp+28h] BYREF
  PVOID PolicyHandle; // [rsp+A0h] [rbp+30h] BYREF
  PVOID Buffer; // [rsp+A8h] [rbp+38h] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  nSize = 0;
  PolicyHandle = 0;
  Buffer = 0;
  v10 = 0;
  memset(&ObjectAttributes.RootDirectory, 0, 40);
  v2 = LsaOpenPolicy(0, &ObjectAttributes, 0x20801u, &PolicyHandle);
  v3 = v2;
  if ( v2 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\common\\iislogon_lib\\iislogon.cxx",
        320,
        "IIS_LOGON_PROVIDER::GetDefaultDomainName",
        "cannot open lsa policy, error %08lX\n",
        v2);
    v4 = RtlNtStatusToDosError(v3);
    v5 = v4;
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    PolicyHandle = 0;
    goto LABEL_21;
  }
  v6 = LsaQueryInformationPolicy(PolicyHandle, PolicyAccountDomainInformation, &Buffer);
  if ( v6 >= 0 )
  {
    if ( wcsncpy_s(Destination, 0x100u, *((const wchar_t **)Buffer + 1), 0xFFFFFFFFFFFFFFFFuLL) == 80 )
    {
      v5 = -2147024774;
      goto LABEL_21;
    }
    v6 = LsaQueryInformationPolicy(PolicyHandle, PolicyPrimaryDomainInformation, &v10);
    if ( v6 >= 0 )
    {
      v5 = 0;
      if ( *((_QWORD *)v10 + 2) )
      {
        *((_DWORD *)Destination + 640) = 1;
        nSize = 1024;
        GetComputerNameExW(ComputerNameDnsDomain, Destination + 256, &nSize);
      }
      else
      {
        *((_DWORD *)Destination + 640) = 0;
      }
      goto LABEL_21;
    }
    if ( (g_dwDebugFlags & 3) == 0 )
      goto LABEL_11;
    v7 = 380;
  }
  else
  {
    if ( (g_dwDebugFlags & 3) == 0 )
      goto LABEL_11;
    v7 = 347;
  }
  PuDbgPrint(
    g_pDebug,
    "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\common\\iislogon_lib\\iislogon.cxx",
    v7,
    "IIS_LOGON_PROVIDER::GetDefaultDomainName",
    "cannot query lsa policy info, error %08lX\n",
    v6);
LABEL_11:
  v8 = RtlNtStatusToDosError(v6);
  v5 = v8;
  if ( v8 > 0 )
    v5 = (unsigned __int16)v8 | 0x80070000;
LABEL_21:
  if ( Buffer )
  {
    LsaFreeMemory(Buffer);
    Buffer = 0;
  }
  if ( v10 )
  {
    LsaFreeMemory(v10);
    v10 = 0;
  }
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  return v5;
}

```

## disassembly

```asm
0x1800219ec  mov     [rsp-18h+arg_0], rbx
0x1800219f1  push    rbp
0x1800219f2  push    rsi
0x1800219f3  push    rdi
0x1800219f4  mov     rbp, rsp
0x1800219f7  sub     rsp, 70h
0x1800219fb  xor     esi, esi
0x1800219fd  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x180021a05  mov     rdi, rcx
0x180021a08  mov     qword ptr [rbp+ObjectAttributes.Attributes], rsi
0x180021a0c  xorps   xmm0, xmm0
0x180021a0f  mov     [rbp+nSize], esi
0x180021a12  xor     ecx, ecx; SystemName
0x180021a14  mov     [rbp+PolicyHandle], rsi
0x180021a18  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x180021a1c  mov     [rbp+Buffer], rsi
0x180021a20  mov     r8d, 20801h; DesiredAccess
0x180021a26  mov     [rbp+var_40], rsi
0x180021a2a  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x180021a2e  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x180021a32  mov     [rbp+ObjectAttributes.ObjectName], rsi
0x180021a36  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180021a3b  call    cs:__imp_LsaOpenPolicy
0x180021a41  mov     ebx, eax
0x180021a43  test    eax, eax
0x180021a45  jns     short loc_180021AA1
0x180021a47  test    byte ptr cs:g_dwDebugFlags, 3
0x180021a4e  jz      short loc_180021A81
0x180021a50  mov     rcx, cs:g_pDebug
0x180021a57  lea     r9, aIisLogonProvid; "IIS_LOGON_PROVIDER::GetDefaultDomainNam"...
0x180021a5e  mov     [rsp+70h+var_48], eax
0x180021a62  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180021a69  lea     rax, aCannotOpenLsaP; "cannot open lsa policy, error %08lX\n"
0x180021a70  mov     r8d, 140h
0x180021a76  mov     [rsp+70h+var_50], rax
0x180021a7b  call    cs:__imp_PuDbgPrint
0x180021a81  mov     ecx, ebx; Status
0x180021a83  call    cs:__imp_RtlNtStatusToDosError
0x180021a89  mov     ebx, eax
0x180021a8b  test    eax, eax
0x180021a8d  jle     short loc_180021A98
0x180021a8f  movzx   ebx, ax
0x180021a92  or      ebx, 80070000h
0x180021a98  mov     [rbp+PolicyHandle], rsi
0x180021a9c  jmp     loc_180021BA2
0x180021aa1  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x180021aa5  lea     r8, [rbp+Buffer]; Buffer
0x180021aa9  mov     edx, 5; InformationClass
0x180021aae  call    cs:__imp_LsaQueryInformationPolicy
0x180021ab4  mov     ebx, eax
0x180021ab6  test    eax, eax
0x180021ab8  jns     short loc_180021B14
0x180021aba  test    byte ptr cs:g_dwDebugFlags, 3
0x180021ac1  jz      short loc_180021AF4
0x180021ac3  mov     r8d, 15Bh
0x180021ac9  mov     rcx, cs:g_pDebug
0x180021ad0  lea     rax, aCannotQueryLsa; "cannot query lsa policy info, error %08"...
0x180021ad7  mov     [rsp+70h+var_48], ebx
0x180021adb  lea     r9, aIisLogonProvid; "IIS_LOGON_PROVIDER::GetDefaultDomainNam"...
0x180021ae2  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180021ae9  mov     [rsp+70h+var_50], rax
0x180021aee  call    cs:__imp_PuDbgPrint
0x180021af4  mov     ecx, ebx; Status
0x180021af6  call    cs:__imp_RtlNtStatusToDosError
0x180021afc  mov     ebx, eax
0x180021afe  test    eax, eax
0x180021b00  jle     loc_180021BA2
0x180021b06  movzx   ebx, ax
0x180021b09  or      ebx, 80070000h
0x180021b0f  jmp     loc_180021BA2
0x180021b14  mov     r8, [rbp+Buffer]
0x180021b18  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180021b1c  mov     edx, 100h; SizeInWords
0x180021b21  mov     rcx, rdi; Destination
0x180021b24  mov     r8, [r8+8]; Source
0x180021b28  call    cs:__imp_wcsncpy_s
0x180021b2e  cmp     eax, 50h ; 'P'
0x180021b31  jnz     short loc_180021B3A
0x180021b33  mov     ebx, 8007007Ah
0x180021b38  jmp     short loc_180021BA2
0x180021b3a  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x180021b3e  lea     r8, [rbp+var_40]; Buffer
0x180021b42  mov     edx, 3; InformationClass
0x180021b47  call    cs:__imp_LsaQueryInformationPolicy
0x180021b4d  mov     ebx, eax
0x180021b4f  test    eax, eax
0x180021b51  jns     short loc_180021B67
0x180021b53  test    byte ptr cs:g_dwDebugFlags, 3
0x180021b5a  jz      short loc_180021AF4
0x180021b5c  mov     r8d, 17Ch
0x180021b62  jmp     loc_180021AC9
0x180021b67  mov     rax, [rbp+var_40]
0x180021b6b  mov     ebx, esi
0x180021b6d  cmp     [rax+10h], rsi
0x180021b71  jz      short loc_180021B9C
0x180021b73  lea     rdx, [rdi+200h]; lpBuffer
0x180021b7a  mov     dword ptr [rdi+0A00h], 1
0x180021b84  lea     r8, [rbp+nSize]; nSize
0x180021b88  mov     [rbp+nSize], 400h
0x180021b8f  mov     ecx, 2; NameType
0x180021b94  call    cs:__imp_GetComputerNameExW
0x180021b9a  jmp     short loc_180021BA2
0x180021b9c  mov     [rdi+0A00h], esi
0x180021ba2  mov     rcx, [rbp+Buffer]; Buffer
0x180021ba6  test    rcx, rcx
0x180021ba9  jz      short loc_180021BB5
0x180021bab  call    cs:__imp_LsaFreeMemory
0x180021bb1  mov     [rbp+Buffer], rsi
0x180021bb5  mov     rcx, [rbp+var_40]; Buffer
0x180021bb9  test    rcx, rcx
0x180021bbc  jz      short loc_180021BC8
0x180021bbe  call    cs:__imp_LsaFreeMemory
0x180021bc4  mov     [rbp+var_40], rsi
0x180021bc8  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x180021bcc  test    rcx, rcx
0x180021bcf  jz      short loc_180021BD7
0x180021bd1  call    cs:__imp_LsaClose
0x180021bd7  mov     eax, ebx
0x180021bd9  mov     rbx, [rsp+70h+arg_0]
0x180021be1  add     rsp, 70h
0x180021be5  pop     rdi
0x180021be6  pop     rsi
0x180021be7  pop     rbp
0x180021be8  retn
```
