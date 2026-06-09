# SeciIsProtectedUser

- ea: `0x18000f1a0`
- end: `0x18000f3ee`
- name: `SeciIsProtectedUser`
- size: `590`
- prototype: `NTSTATUS __stdcall(PBOOLEAN ProtectedUser)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x18000f1a0`
- `0x18000f3f4`
- `0x18000f490`
- `0x180016f78`
- `0x18002205f`
- `0x180022190`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18000f23b`
- `ntdll!NtQueryInformationToken` at `0x18000f23b`
- `ntdll!RtlCheckTokenMembershipEx` at `0x18000f38a`
- `ntdll!RtlCheckTokenMembershipEx` at `0x18000f38a`
- `ntdll!RtlEqualSid` at `0x18000f357`
- `ntdll!RtlEqualSid` at `0x18000f357`
- `ntdll!RtlGetNtProductType` at `0x18000f216`
- `ntdll!RtlGetNtProductType` at `0x18000f216`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f250`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f250`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f339`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f339`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f2fc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f2fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f3e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f3e3`

## pseudocode

```c
NTSTATUS __stdcall SeciIsProtectedUser(PBOOLEAN ProtectedUser)
{
  PVOID v1; // rdi
  struct _LSA_UNICODE_STRING *v3; // rcx
  NTSTATUS v4; // ebx
  ACCESS_MASK v5; // r8d
  _BYTE *v7; // rsi
  NTSTATUS v8; // eax
  POLICY_INFORMATION_CLASS v9; // edx
  LSTATUS v10; // eax
  bool v11; // cc
  BYTE Data[4]; // [rsp+30h] [rbp-89h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-85h] BYREF
  DWORD Type; // [rsp+38h] [rbp-81h] BYREF
  enum _NT_PRODUCT_TYPE ProductType; // [rsp+3Ch] [rbp-7Dh] BYREF
  ULONG ReturnLength; // [rsp+40h] [rbp-79h] BYREF
  PVOID PolicyHandle; // [rsp+48h] [rbp-71h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-69h] BYREF
  PVOID Buffer; // [rsp+58h] [rbp-61h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-59h] BYREF
  _QWORD TokenInformation[12]; // [rsp+90h] [rbp-29h] BYREF

  ProductType = 0;
  v1 = 0;
  PolicyHandle = 0;
  Buffer = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  memset_0(TokenInformation, 0, 0x58u);
  ReturnLength = 0;
  hKey = 0;
  *(_DWORD *)Data = 0;
  Type = 0;
  cbData = 0;
  *ProtectedUser = 0;
  if ( !RtlGetNtProductType(&ProductType) )
  {
    v4 = -1073741823;
    goto LABEL_3;
  }
  v4 = NtQueryInformationToken((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenUser, TokenInformation, 0x58u, &ReturnLength);
  if ( v4 >= 0 )
  {
    v7 = (_BYTE *)TokenInformation[0];
    if ( *(_BYTE *)(TokenInformation[0] + 1LL) == 5 )
    {
      *(_BYTE *)(TokenInformation[0] + 1LL) = 4;
      memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
      v8 = LsaOpenPolicy(v3, &ObjectAttributes, v5, &PolicyHandle);
      v1 = PolicyHandle;
      v4 = v8;
      if ( v8 >= 0 )
      {
        v4 = LsaQueryInformationPolicy(PolicyHandle, v9, &Buffer);
        if ( v4 >= 0 )
        {
          v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Lsa", 0, 0x20019u, &hKey);
          v11 = v10 <= 0;
          if ( !v10 )
          {
            cbData = 4;
            v10 = RegQueryValueExW(hKey, L"ProtectedUserLevel", 0, &Type, Data, &cbData);
            if ( v10 == 2 )
            {
LABEL_15:
              *(_DWORD *)Data = 0;
LABEL_16:
              if ( !RtlEqualSid(*((PSID *)Buffer + 2), v7) || ProductType == NtProductLanManNt )
              {
                if ( (Data[0] & 1) == 0 )
                {
                  *(_DWORD *)&v7[4 * (unsigned __int8)v7[1]++ + 8] = 525;
                  v10 = RtlCheckTokenMembershipEx(-6, v7, 2, ProtectedUser);
LABEL_19:
                  v4 = v10;
                  goto LABEL_3;
                }
                *ProtectedUser = 1;
              }
              goto LABEL_3;
            }
            v11 = v10 <= 0;
            if ( !v10 )
            {
              if ( Type == 4 )
                goto LABEL_16;
              goto LABEL_15;
            }
          }
          if ( v11 )
            goto LABEL_19;
          v4 = (unsigned __int16)v10 | 0xC0070000;
        }
      }
    }
  }
LABEL_3:
  if ( hKey )
    RegCloseKey(hKey);
  if ( Buffer )
    LocalFree(Buffer);
  if ( v1 )
    LsaClose(v1);
  return v4;
}

```

## disassembly

```asm
0x18000f1a0  mov     [rsp-8+arg_8], rbx
0x18000f1a5  mov     [rsp-8+arg_10], rsi
0x18000f1aa  push    rbp
0x18000f1ab  push    rdi
0x18000f1ac  push    r14
0x18000f1ae  lea     rbp, [rsp-47h]
0x18000f1b3  sub     rsp, 100h
0x18000f1ba  mov     rax, cs:__security_cookie
0x18000f1c1  xor     rax, rsp
0x18000f1c4  mov     [rbp+57h+var_20], rax
0x18000f1c8  xorps   xmm0, xmm0
0x18000f1cb  mov     [rbp+57h+ProductType], 0
0x18000f1d2  xor     edi, edi
0x18000f1d4  mov     r14, rcx
0x18000f1d7  xor     edx, edx; Val
0x18000f1d9  mov     [rbp+57h+PolicyHandle], rdi
0x18000f1dd  lea     rcx, [rbp+57h+TokenInformation]; void *
0x18000f1e1  mov     [rbp+57h+Buffer], rdi
0x18000f1e5  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18000f1e9  lea     ebx, [rdi+58h]
0x18000f1ec  mov     r8d, ebx; Size
0x18000f1ef  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18000f1f3  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000f1f7  call    memset_0
0x18000f1fc  lea     rcx, [rbp+57h+ProductType]; ProductType
0x18000f200  mov     [rbp+57h+var_D0], edi
0x18000f203  mov     [rbp+57h+hKey], rdi
0x18000f207  mov     dword ptr [rsp+110h+Data], edi
0x18000f20b  mov     [rsp+110h+Type], edi
0x18000f20f  mov     [rsp+110h+cbData], edi
0x18000f213  mov     [r14], dil
0x18000f216  call    cs:__imp_RtlGetNtProductType
0x18000f21c  test    al, al
0x18000f21e  jz      loc_18000F3B4
0x18000f224  lea     rax, [rbp+57h+var_D0]
0x18000f228  mov     r9d, ebx; TokenInformationLength
0x18000f22b  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18000f22f  mov     [rsp+110h+ReturnLength], rax; ReturnLength
0x18000f234  lea     edx, [rdi+1]; TokenInformationClass
0x18000f237  lea     rcx, [rdi-6]; TokenHandle
0x18000f23b  call    cs:__imp_NtQueryInformationToken
0x18000f241  mov     ebx, eax
0x18000f243  test    eax, eax
0x18000f245  jns     short loc_18000F292
0x18000f247  mov     rcx, [rbp+57h+hKey]; hKey
0x18000f24b  test    rcx, rcx
0x18000f24e  jz      short loc_18000F256
0x18000f250  call    cs:__imp_RegCloseKey
0x18000f256  mov     rcx, [rbp+57h+Buffer]; hMem
0x18000f25a  test    rcx, rcx
0x18000f25d  jnz     loc_18000F3E3
0x18000f263  test    rdi, rdi
0x18000f266  jnz     loc_18000F397
0x18000f26c  mov     eax, ebx
0x18000f26e  mov     rcx, [rbp+57h+var_20]
0x18000f272  xor     rcx, rsp; StackCookie
0x18000f275  call    __security_check_cookie
0x18000f27a  lea     r11, [rsp+110h+var_10]
0x18000f282  mov     rbx, [r11+28h]
0x18000f286  mov     rsi, [r11+30h]
0x18000f28a  mov     rsp, r11
0x18000f28d  pop     r14
0x18000f28f  pop     rdi
0x18000f290  pop     rbp
0x18000f291  retn
0x18000f292  mov     rsi, [rbp+57h+TokenInformation]
0x18000f296  cmp     byte ptr [rsi+1], 5
0x18000f29a  jnz     short loc_18000F247
0x18000f29c  xorps   xmm0, xmm0
0x18000f29f  mov     byte ptr [rsi+1], 4
0x18000f2a3  lea     r9, [rbp+57h+PolicyHandle]; PolicyHandle
0x18000f2a7  lea     rdx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000f2ab  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18000f2af  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18000f2b3  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000f2b7  call    LsaOpenPolicy
0x18000f2bc  mov     rdi, [rbp+57h+PolicyHandle]
0x18000f2c0  mov     ebx, eax
0x18000f2c2  test    eax, eax
0x18000f2c4  js      short loc_18000F247
0x18000f2c6  lea     r8, [rbp+57h+Buffer]; Buffer
0x18000f2ca  mov     rcx, rdi; PolicyHandle
0x18000f2cd  call    LsaQueryInformationPolicy
0x18000f2d2  mov     ebx, eax
0x18000f2d4  test    eax, eax
0x18000f2d6  js      loc_18000F247
0x18000f2dc  lea     rax, [rbp+57h+hKey]
0x18000f2e0  mov     r9d, 20019h; samDesired
0x18000f2e6  xor     r8d, r8d; ulOptions
0x18000f2e9  mov     [rsp+110h+ReturnLength], rax; phkResult
0x18000f2ee  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Control\\Lsa"
0x18000f2f5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000f2fc  call    cs:__imp_RegOpenKeyExW
0x18000f302  test    eax, eax
0x18000f304  jnz     loc_18000F3A4
0x18000f30a  mov     rcx, [rbp+57h+hKey]; hKey
0x18000f30e  lea     rax, [rsp+110h+cbData]
0x18000f313  mov     [rsp+110h+lpcbData], rax; lpcbData
0x18000f318  lea     r9, [rsp+110h+Type]; lpType
0x18000f31d  lea     rax, [rsp+110h+Data]
0x18000f322  mov     [rsp+110h+cbData], 4
0x18000f32a  xor     r8d, r8d; lpReserved
0x18000f32d  mov     [rsp+110h+ReturnLength], rax; lpData
0x18000f332  lea     rdx, aProtecteduserl; "ProtectedUserLevel"
0x18000f339  call    cs:__imp_RegQueryValueExW
0x18000f33f  cmp     eax, 2
0x18000f342  jnz     short loc_18000F3BE
0x18000f344  mov     dword ptr [rsp+110h+Data], 0
0x18000f34c  mov     rcx, [rbp+57h+Buffer]
0x18000f350  mov     rdx, rsi; Sid2
0x18000f353  mov     rcx, [rcx+10h]; Sid1
0x18000f357  call    cs:__imp_RtlEqualSid
0x18000f35d  test    al, al
0x18000f35f  jnz     short loc_18000F3CE
0x18000f361  test    [rsp+110h+Data], 1
0x18000f366  jnz     short loc_18000F3DA
0x18000f368  movzx   eax, byte ptr [rsi+1]
0x18000f36c  mov     r9, r14
0x18000f36f  mov     r8d, 2
0x18000f375  mov     rdx, rsi
0x18000f378  mov     rcx, 0FFFFFFFFFFFFFFFAh
0x18000f37f  mov     dword ptr [rsi+rax*4+8], 20Dh
0x18000f387  inc     byte ptr [rsi+1]
0x18000f38a  call    cs:__imp_RtlCheckTokenMembershipEx
0x18000f390  mov     ebx, eax
0x18000f392  jmp     loc_18000F247
0x18000f397  mov     rcx, rdi; ObjectHandle
0x18000f39a  call    LsaClose
0x18000f39f  jmp     loc_18000F26C
0x18000f3a4  jle     short loc_18000F390
0x18000f3a6  movzx   ebx, ax
0x18000f3a9  or      ebx, 0C0070000h
0x18000f3af  jmp     loc_18000F247
0x18000f3b4  mov     ebx, 0C0000001h
0x18000f3b9  jmp     loc_18000F247
0x18000f3be  test    eax, eax
0x18000f3c0  jnz     short loc_18000F3A4
0x18000f3c2  cmp     [rsp+110h+Type], 4
0x18000f3c7  jz      short loc_18000F34C
0x18000f3c9  jmp     loc_18000F344
0x18000f3ce  cmp     [rbp+57h+ProductType], 2
0x18000f3d2  jnz     loc_18000F247
0x18000f3d8  jmp     short loc_18000F361
0x18000f3da  mov     byte ptr [r14], 1
0x18000f3de  jmp     loc_18000F247
0x18000f3e3  call    cs:__imp_LocalFree
0x18000f3e9  jmp     loc_18000F263
```
