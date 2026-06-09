# WiaTrcLib::GetTracingKeys(char *,HKEY__ * *,HKEY__ * *)

- ea: `0x18001551c`
- end: `0x1800156d3`
- name: `?GetTracingKeys@WiaTrcLib@@YAJPEADPEAPEAUHKEY__@@1@Z`
- size: `439`
- prototype: `int(WiaTrcLib *__hidden this, char *, HKEY *, HKEY *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800151c4`

## callees

- `0x18001551c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18001569d`
- `ADVAPI32!RegCloseKey` at `0x1800156b2`
- `ADVAPI32!RegCloseKey` at `0x18001569d`
- `ADVAPI32!RegCloseKey` at `0x1800156b2`
- `KERNEL32!LocalFree` at `0x18001568b`
- `KERNEL32!LocalFree` at `0x18001568b`
- `KERNEL32!GetLastError` at `0x18001557b`
- `KERNEL32!GetLastError` at `0x18001557b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800155fe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18001566d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800155fe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18001566d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800155d8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x18001564b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800155d8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x18001564b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180015571`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180015571`

## pseudocode

```c
__int64 __fastcall WiaTrcLib::GetTracingKeys(WiaTrcLib *this, HKEY *a2, HKEY *a3, HKEY *a4)
{
  signed int v6; // ebx
  signed int LastError; // eax
  LSTATUS v8; // eax
  int v9; // ecx
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+50h] [rbp-28h] BYREF
  DWORD dwDisposition; // [rsp+80h] [rbp+8h] BYREF
  int v13; // [rsp+84h] [rbp+Ch]

  v13 = HIDWORD(this);
  dwDisposition = 0;
  *a2 = 0;
  *a3 = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  SecurityAttributes.nLength = 24;
  v6 = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:(A;OICI;GRGW;;;SY)(A;OICI;GRGW;;;BA)(A;OICI;GRGW;;;LS)(A;OICI;GR;;;AU)",
         1u,
         &SecurityAttributes.lpSecurityDescriptor,
         0) )
  {
    goto LABEL_22;
  }
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( !v6 )
  {
LABEL_22:
    if ( RegCreateKeyExA(
           HKEY_LOCAL_MACHINE,
           "SYSTEM\\CurrentControlSet\\Control\\StillImage\\Trace",
           0,
           0,
           0,
           0x2001Fu,
           &SecurityAttributes,
           a2,
           &dwDisposition)
      && RegOpenKeyExA(HKEY_LOCAL_MACHINE, "SYSTEM\\CurrentControlSet\\Control\\StillImage\\Trace", 0, 0x20019u, a2) )
    {
      v6 = -2147467259;
    }
    else if ( RegCreateKeyExA(*a2, g_WiaTrace_szModuleName, 0, 0, 0, 0x2001Fu, &SecurityAttributes, a3, &dwDisposition) )
    {
      v8 = RegOpenKeyExA(*a2, g_WiaTrace_szModuleName, 0, 0x20019u, a3);
      v9 = v6;
      if ( v8 )
        v9 = -2147467259;
      v6 = v9;
    }
  }
  if ( SecurityAttributes.lpSecurityDescriptor )
    LocalFree(SecurityAttributes.lpSecurityDescriptor);
  if ( v6 < 0 )
  {
    if ( *a2 )
    {
      RegCloseKey(*a2);
      *a2 = 0;
    }
    if ( *a3 )
    {
      RegCloseKey(*a3);
      *a3 = 0;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001551c  mov     r11, rsp
0x18001551f  mov     [r11+10h], rbx
0x180015523  mov     [r11+18h], rsi
0x180015527  mov     [r11+8], rcx
0x18001552b  push    rdi
0x18001552c  sub     rsp, 70h
0x180015530  xor     eax, eax
0x180015532  mov     dword ptr [r11+8], 0
0x18001553a  mov     [rdx], rax
0x18001553d  lea     rcx, StringSecurityDescriptor; "D:(A;OICI;GRGW;;;SY)(A;OICI;GRGW;;;BA)("...
0x180015544  xorps   xmm0, xmm0
0x180015547  mov     [r8], rax
0x18001554a  movups  xmmword ptr [rsp+78h+SecurityAttributes.nLength], xmm0
0x18001554f  mov     [r11-18h], rax
0x180015553  mov     rsi, r8
0x180015556  mov     rdi, rdx
0x180015559  mov     [rsp+78h+SecurityAttributes.nLength], 18h
0x180015561  lea     edx, [rax+1]; StringSDRevision
0x180015564  mov     [rsp+78h+SecurityAttributes.bInheritHandle], eax
0x180015568  xor     r9d, r9d; SecurityDescriptorSize
0x18001556b  lea     r8, [r11-20h]; SecurityDescriptor
0x18001556f  xor     ebx, ebx
0x180015571  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180015577  test    eax, eax
0x180015579  jnz     short loc_180015598
0x18001557b  call    cs:__imp_GetLastError
0x180015581  mov     ebx, eax
0x180015583  test    eax, eax
0x180015585  jle     short loc_180015590
0x180015587  movzx   ebx, ax
0x18001558a  or      ebx, 80070000h
0x180015590  test    ebx, ebx
0x180015592  jnz     loc_180015681
0x180015598  lea     rax, [rsp+78h+dwDisposition]
0x1800155a0  xor     r9d, r9d; lpClass
0x1800155a3  mov     [rsp+78h+lpdwDisposition], rax; lpdwDisposition
0x1800155a8  lea     rdx, aSystemCurrentc_4; "SYSTEM\\CurrentControlSet\\Control\\Sti"...
0x1800155af  mov     [rsp+78h+phkResult], rdi; phkResult
0x1800155b4  lea     rax, [rsp+78h+SecurityAttributes]
0x1800155b9  mov     [rsp+78h+lpSecurityAttributes], rax; lpSecurityAttributes
0x1800155be  xor     r8d, r8d; Reserved
0x1800155c1  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x1800155c9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800155d0  mov     [rsp+78h+dwOptions], 0; dwOptions
0x1800155d8  call    cs:__imp_RegCreateKeyExA
0x1800155de  test    eax, eax
0x1800155e0  jz      short loc_18001560F
0x1800155e2  mov     r9d, 20019h; samDesired
0x1800155e8  mov     qword ptr [rsp+78h+dwOptions], rdi; phkResult
0x1800155ed  xor     r8d, r8d; ulOptions
0x1800155f0  lea     rdx, aSystemCurrentc_4; "SYSTEM\\CurrentControlSet\\Control\\Sti"...
0x1800155f7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800155fe  call    cs:__imp_RegOpenKeyExA
0x180015604  test    eax, eax
0x180015606  jz      short loc_18001560F
0x180015608  mov     ebx, 80004005h
0x18001560d  jmp     short loc_180015681
0x18001560f  mov     rcx, [rdi]; hKey
0x180015612  lea     rax, [rsp+78h+dwDisposition]
0x18001561a  mov     [rsp+78h+lpdwDisposition], rax; lpdwDisposition
0x18001561f  lea     rdx, g_WiaTrace_szModuleName; lpSubKey
0x180015626  mov     [rsp+78h+phkResult], rsi; phkResult
0x18001562b  lea     rax, [rsp+78h+SecurityAttributes]
0x180015630  mov     [rsp+78h+lpSecurityAttributes], rax; lpSecurityAttributes
0x180015635  xor     r9d, r9d; lpClass
0x180015638  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x180015640  xor     r8d, r8d; Reserved
0x180015643  mov     [rsp+78h+dwOptions], 0; dwOptions
0x18001564b  call    cs:__imp_RegCreateKeyExA
0x180015651  test    eax, eax
0x180015653  jz      short loc_180015681
0x180015655  mov     rcx, [rdi]; hKey
0x180015658  lea     rdx, g_WiaTrace_szModuleName; lpSubKey
0x18001565f  mov     r9d, 20019h; samDesired
0x180015665  mov     qword ptr [rsp+78h+dwOptions], rsi; phkResult
0x18001566a  xor     r8d, r8d; ulOptions
0x18001566d  call    cs:__imp_RegOpenKeyExA
0x180015673  mov     ecx, ebx
0x180015675  mov     ebx, 80004005h
0x18001567a  test    eax, eax
0x18001567c  cmovnz  ecx, ebx
0x18001567f  mov     ebx, ecx
0x180015681  mov     rcx, [rsp+78h+SecurityAttributes.lpSecurityDescriptor]; hMem
0x180015686  test    rcx, rcx
0x180015689  jz      short loc_180015691
0x18001568b  call    cs:__imp_LocalFree
0x180015691  test    ebx, ebx
0x180015693  jns     short loc_1800156BF
0x180015695  mov     rcx, [rdi]; hKey
0x180015698  test    rcx, rcx
0x18001569b  jz      short loc_1800156AA
0x18001569d  call    cs:__imp_RegCloseKey
0x1800156a3  mov     qword ptr [rdi], 0
0x1800156aa  mov     rcx, [rsi]; hKey
0x1800156ad  test    rcx, rcx
0x1800156b0  jz      short loc_1800156BF
0x1800156b2  call    cs:__imp_RegCloseKey
0x1800156b8  mov     qword ptr [rsi], 0
0x1800156bf  lea     r11, [rsp+78h+var_8]
0x1800156c4  mov     eax, ebx
0x1800156c6  mov     rbx, [r11+18h]
0x1800156ca  mov     rsi, [r11+20h]
0x1800156ce  mov     rsp, r11
0x1800156d1  pop     rdi
0x1800156d2  retn
```
