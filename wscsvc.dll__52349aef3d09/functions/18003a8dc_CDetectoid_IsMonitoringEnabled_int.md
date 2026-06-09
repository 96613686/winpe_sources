# CDetectoid::IsMonitoringEnabled(int &)

- ea: `0x18003a8dc`
- end: `0x18003aa63`
- name: `?IsMonitoringEnabled@CDetectoid@@QEAAJAEAH@Z`
- size: `391`
- prototype: `__int64 __fastcall(const unsigned __int16 **this, int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a570`
- `0x18000a740`

## callees

- `0x180002db0`
- `0x18001b3a0`
- `0x18003a8dc`
- `0x18003fbf2`
- `0x18003fc30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003a9c4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003a9c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003aa20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003aa20`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003aa07`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003aa07`

## string_xrefs

- `0x18003a933`: `SOFTWARE\Microsoft\Security Center\Monitoring`

## pseudocode

```c
__int64 __fastcall CDetectoid::IsMonitoringEnabled(const unsigned __int16 **this, int *a2)
{
  signed int v2; // ebx
  unsigned __int64 v5; // rdx
  unsigned __int64 v6; // rdx
  LSTATUS v7; // eax
  BYTE Data[4]; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData; // [rsp+54h] [rbp-ACh] BYREF
  DWORD Type; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[264]; // [rsp+70h] [rbp-90h] BYREF

  v2 = 0;
  *a2 = 1;
  if ( this[6] )
  {
    hKey = 0;
    memset_0(SubKey, 0, 0x208u);
    v2 = StringCchCopyW(SubKey, 0x104u, L"SOFTWARE\\Microsoft\\Security Center\\Monitoring");
    if ( v2 >= 0 )
    {
      v2 = StringCchCatW(SubKey, v5, L"\\");
      if ( v2 >= 0 )
      {
        v2 = StringCchCatW(SubKey, v6, this[6]);
        if ( v2 >= 0 )
        {
          v7 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 1u, 0, &hKey, 0);
          v2 = v7;
          if ( v7 )
          {
            if ( v7 > 0 )
              v2 = (unsigned __int16)v7 | 0x80070000;
          }
          else
          {
            Type = 4;
            cbData = 4;
            *(_DWORD *)Data = 0;
            if ( !RegQueryValueExW(hKey, L"DisableMonitoring", 0, &Type, Data, &cbData) )
              *a2 = *(_DWORD *)Data != 1;
            RegCloseKey(hKey);
          }
        }
      }
    }
    if ( !*a2 )
      *((_DWORD *)this + 14) = 0;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18003a8dc  mov     [rsp-8+arg_10], rbx
0x18003a8e1  push    rbp
0x18003a8e2  push    rsi
0x18003a8e3  push    rdi
0x18003a8e4  lea     rbp, [rsp-190h]
0x18003a8ec  sub     rsp, 290h
0x18003a8f3  mov     rax, cs:__security_cookie
0x18003a8fa  xor     rax, rsp
0x18003a8fd  mov     [rbp+1A0h+var_20], rax
0x18003a904  xor     ebx, ebx
0x18003a906  mov     dword ptr [rdx], 1
0x18003a90c  mov     rdi, rdx
0x18003a90f  mov     rsi, rcx
0x18003a912  cmp     [rcx+30h], rbx
0x18003a916  jz      loc_18003AA3F
0x18003a91c  xor     edx, edx; Val
0x18003a91e  mov     [rsp+2A0h+hKey], rbx
0x18003a923  mov     r8d, 208h; Size
0x18003a929  lea     rcx, [rsp+2A0h+SubKey]; void *
0x18003a92e  call    memset_0
0x18003a933  lea     r8, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Security Center\\M"...
0x18003a93a  mov     edx, 104h; unsigned __int64
0x18003a93f  lea     rcx, [rsp+2A0h+SubKey]; unsigned __int16 *
0x18003a944  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003a949  mov     ebx, eax
0x18003a94b  test    eax, eax
0x18003a94d  js      loc_18003AA33
0x18003a953  lea     r8, asc_1800465F0; "\\"
0x18003a95a  lea     rcx, [rsp+2A0h+SubKey]; unsigned __int16 *
0x18003a95f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003a964  mov     ebx, eax
0x18003a966  test    eax, eax
0x18003a968  js      loc_18003AA33
0x18003a96e  mov     r8, [rsi+30h]; unsigned __int16 *
0x18003a972  lea     rcx, [rsp+2A0h+SubKey]; unsigned __int16 *
0x18003a977  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003a97c  mov     ebx, eax
0x18003a97e  test    eax, eax
0x18003a980  js      loc_18003AA33
0x18003a986  mov     [rsp+2A0h+lpdwDisposition], 0; lpdwDisposition
0x18003a98f  lea     rax, [rsp+2A0h+hKey]
0x18003a994  mov     [rsp+2A0h+phkResult], rax; phkResult
0x18003a999  lea     rdx, [rsp+2A0h+SubKey]; lpSubKey
0x18003a99e  mov     [rsp+2A0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18003a9a7  xor     r9d, r9d; lpClass
0x18003a9aa  mov     [rsp+2A0h+samDesired], 1; samDesired
0x18003a9b2  xor     r8d, r8d; Reserved
0x18003a9b5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003a9bc  mov     [rsp+2A0h+dwOptions], 0; dwOptions
0x18003a9c4  call    cs:__imp_RegCreateKeyExW
0x18003a9ca  mov     ebx, eax
0x18003a9cc  test    eax, eax
0x18003a9ce  jnz     short loc_18003AA28
0x18003a9d0  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18003a9d5  lea     eax, [rbx+4]
0x18003a9d8  mov     [rsp+2A0h+Type], eax
0x18003a9dc  lea     r9, [rsp+2A0h+Type]; lpType
0x18003a9e1  mov     [rsp+2A0h+cbData], eax
0x18003a9e5  lea     rdx, aDisablemonitor; "DisableMonitoring"
0x18003a9ec  lea     rax, [rsp+2A0h+cbData]
0x18003a9f1  mov     dword ptr [rsp+2A0h+Data], ebx
0x18003a9f5  mov     qword ptr [rsp+2A0h+samDesired], rax; lpcbData
0x18003a9fa  xor     r8d, r8d; lpReserved
0x18003a9fd  lea     rax, [rsp+2A0h+Data]
0x18003aa02  mov     qword ptr [rsp+2A0h+dwOptions], rax; lpData
0x18003aa07  call    cs:__imp_RegQueryValueExW
0x18003aa0d  test    eax, eax
0x18003aa0f  jnz     short loc_18003AA1B
0x18003aa11  cmp     dword ptr [rsp+2A0h+Data], 1
0x18003aa16  setnz   al
0x18003aa19  mov     [rdi], eax
0x18003aa1b  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18003aa20  call    cs:__imp_RegCloseKey
0x18003aa26  jmp     short loc_18003AA33
0x18003aa28  jle     short loc_18003AA33
0x18003aa2a  movzx   ebx, ax
0x18003aa2d  or      ebx, 80070000h
0x18003aa33  cmp     dword ptr [rdi], 0
0x18003aa36  jnz     short loc_18003AA3F
0x18003aa38  mov     dword ptr [rsi+38h], 0
0x18003aa3f  mov     eax, ebx
0x18003aa41  mov     rcx, [rbp+1A0h+var_20]
0x18003aa48  xor     rcx, rsp; StackCookie
0x18003aa4b  call    __security_check_cookie
0x18003aa50  mov     rbx, [rsp+2A0h+arg_10]
0x18003aa58  add     rsp, 290h
0x18003aa5f  pop     rdi
0x18003aa60  pop     rsi
0x18003aa61  pop     rbp
0x18003aa62  retn
```
