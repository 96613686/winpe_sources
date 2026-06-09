# IsPOSRedirectionRegistryEnabled(void)

- ea: `0x180027900`
- end: `0x180027a44`
- name: `?IsPOSRedirectionRegistryEnabled@@YA_NXZ`
- size: `324`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180028140`

## callees

- `0x18000b8f8`
- `0x18000f75c`
- `0x180027900`
- `0x180028640`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027935`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027935`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027974`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027974`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027a34`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027a34`

## pseudocode

```c
bool IsPOSRedirectionRegistryEnabled(void)
{
  bool v0; // bl
  int v1; // edi
  unsigned int v2; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  DWORD Type; // [rsp+50h] [rbp+20h] BYREF
  int Data; // [rsp+58h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+38h] BYREF

  hKey = 0;
  v0 = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
         0,
         0x20019u,
         &hKey) )
  {
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 4u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_D(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        14,
        WPP_94246e01360c359abb577584ca0bcde6_Traceguids,
        CurrentThreadActivityIdPrefix);
    }
  }
  else
  {
    Data = 0;
    Type = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"EnablePOSRedirection", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
    {
      v1 = Data;
      v0 = Data != 0;
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 4u )
      {
        v2 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Ddd(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          13,
          WPP_94246e01360c359abb577584ca0bcde6_Traceguids,
          v2,
          v1,
          v0);
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x180027900  push    rbp
0x180027902  push    rbx
0x180027903  push    rdi
0x180027904  mov     rbp, rsp
0x180027907  sub     rsp, 30h
0x18002790b  lea     rax, [rbp+hKey]
0x18002790f  mov     [rbp+hKey], 0
0x180027917  mov     r9d, 20019h; samDesired
0x18002791d  mov     [rsp+30h+phkResult], rax; phkResult
0x180027922  xor     r8d, r8d; ulOptions
0x180027925  lea     rdx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Control\\Ter"...
0x18002792c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180027933  xor     bl, bl
0x180027935  call    cs:__imp_RegOpenKeyExW
0x18002793b  test    eax, eax
0x18002793d  jnz     loc_1800279E8
0x180027943  mov     rcx, [rbp+hKey]; hKey
0x180027947  lea     r9, [rbp+Type]; lpType
0x18002794b  mov     [rbp+Data], eax
0x18002794e  lea     rdx, aEnableposredir; "EnablePOSRedirection"
0x180027955  mov     [rbp+Type], eax
0x180027958  xor     r8d, r8d; lpReserved
0x18002795b  lea     rax, [rbp+cbData]
0x18002795f  mov     [rbp+cbData], 4
0x180027966  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18002796b  lea     rax, [rbp+Data]
0x18002796f  mov     [rsp+30h+phkResult], rax; lpData
0x180027974  call    cs:__imp_RegQueryValueExW
0x18002797a  test    eax, eax
0x18002797c  jnz     loc_180027A2B
0x180027982  cmp     [rbp+Type], 4
0x180027986  jnz     loc_180027A2B
0x18002798c  mov     edi, [rbp+Data]
0x18002798f  test    edi, edi
0x180027991  setnz   bl
0x180027994  mov     rax, cs:WPP_GLOBAL_Control
0x18002799b  lea     rcx, WPP_GLOBAL_Control
0x1800279a2  cmp     rax, rcx
0x1800279a5  jz      loc_180027A2B
0x1800279ab  test    byte ptr [rax+1Ch], 1
0x1800279af  jz      short loc_180027A2B
0x1800279b1  cmp     byte ptr [rax+19h], 4
0x1800279b5  jb      short loc_180027A2B
0x1800279b7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800279bc  movzx   ecx, bl
0x1800279bf  lea     r8, WPP_94246e01360c359abb577584ca0bcde6_Traceguids
0x1800279c6  mov     dword ptr [rsp+30h+lpcbData], ecx
0x1800279ca  mov     edx, 0Dh
0x1800279cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800279d6  mov     r9d, eax
0x1800279d9  mov     dword ptr [rsp+30h+phkResult], edi
0x1800279dd  mov     rcx, [rcx+10h]
0x1800279e1  call    WPP_SF_Ddd
0x1800279e6  jmp     short loc_180027A2B
0x1800279e8  mov     rax, cs:WPP_GLOBAL_Control
0x1800279ef  lea     rcx, WPP_GLOBAL_Control
0x1800279f6  cmp     rax, rcx
0x1800279f9  jz      short loc_180027A2B
0x1800279fb  test    byte ptr [rax+1Ch], 1
0x1800279ff  jz      short loc_180027A2B
0x180027a01  cmp     byte ptr [rax+19h], 4
0x180027a05  jb      short loc_180027A2B
0x180027a07  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180027a0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180027a13  lea     r8, WPP_94246e01360c359abb577584ca0bcde6_Traceguids
0x180027a1a  mov     edx, 0Eh
0x180027a1f  mov     r9d, eax
0x180027a22  mov     rcx, [rcx+10h]
0x180027a26  call    WPP_SF_D
0x180027a2b  mov     rcx, [rbp+hKey]; hKey
0x180027a2f  test    rcx, rcx
0x180027a32  jz      short loc_180027A3A
0x180027a34  call    cs:__imp_RegCloseKey
0x180027a3a  mov     al, bl
0x180027a3c  add     rsp, 30h
0x180027a40  pop     rdi
0x180027a41  pop     rbx
0x180027a42  pop     rbp
0x180027a43  retn
```
