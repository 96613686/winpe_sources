# UmpoReadSecurityDescriptor

- ea: `0x180003a00`
- end: `0x180003ca8`
- name: `UmpoReadSecurityDescriptor`
- size: `680`
- prototype: `__int64 __fastcall(int, __int64, wchar_t *, DWORD *)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800037b0`
- `0x180003a00`
- `0x180014cf0`

## callees

- `0x1800010f0`
- `0x180003a00`
- `0x180010070`
- `0x180012748`
- `0x180012864`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180003aa2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180003aa2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180003b0f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180003b28`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180003b3f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180003b0f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180003b28`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180003b3f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003b8d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003bd3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003b8d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003bd3`

## string_xrefs

- `0x180003a83`: `CreatePowerScheme`

## pseudocode

```c
__int64 __fastcall UmpoReadSecurityDescriptor(int a1, __int64 a2, wchar_t *a3, DWORD *a4)
{
  const WCHAR *v7; // rdi
  STRSAFE_LPCWSTR v8; // rax
  __int64 v9; // rcx
  size_t v10; // rax
  size_t v11; // rdx
  unsigned int Value; // ebx
  DWORD v13; // eax
  size_t v14; // rdx
  DWORD cbData[4]; // [rsp+30h] [rbp-98h] BYREF
  _WORD v17[40]; // [rsp+40h] [rbp-88h] BYREF

  *(_QWORD *)cbData = 0;
  switch ( a1 )
  {
    case 0:
    case 1:
    case 16:
      if ( !a2 )
        return 87;
      UmpoInternalConvertGuidToStringBuffer(a2, v17);
      v7 = v17;
      goto LABEL_21;
    case 2:
      v7 = L"FriendlyName";
      goto LABEL_21;
    case 3:
      v7 = L"Description";
      goto LABEL_21;
    case 14:
      AcquireSRWLockShared(&UmpoDefaultSecurityDescriptorLock);
      if ( !UmpoDefaultSecurityDescriptor )
        goto LABEL_18;
      v8 = UmpoDefaultSecurityDescriptor;
      v9 = 0x7FFFFFFF;
      do
      {
        if ( !*v8 )
          break;
        ++v8;
        --v9;
      }
      while ( v9 );
      if ( v9 )
      {
        v10 = *a4;
        v11 = 2 * (0x7FFFFFFF - v9) + 2;
        *(_QWORD *)cbData = v11;
        if ( v10 < v11 || !a3 )
        {
          *a4 = v11;
          Value = 234;
          ReleaseSRWLockShared(&UmpoDefaultSecurityDescriptorLock);
          return Value;
        }
        if ( !StringCbCopyW(a3, v11, UmpoDefaultSecurityDescriptor) )
        {
          Value = 0;
          ReleaseSRWLockShared(&UmpoDefaultSecurityDescriptorLock);
          return Value;
        }
      }
      else
      {
        *(_QWORD *)cbData = 0;
      }
LABEL_18:
      ReleaseSRWLockShared(&UmpoDefaultSecurityDescriptorLock);
      v7 = L"Default";
LABEL_21:
      *(_QWORD *)cbData = 0;
      Value = RegQueryValueExW(UmpoPowerSecurityDescriptorRootKey, v7, 0, 0, 0, cbData);
      if ( Value )
        goto LABEL_30;
      v13 = cbData[0] + 2;
      *(_QWORD *)cbData += 2LL;
      if ( a3 && v13 <= *a4 )
      {
        Value = RegQueryValueExW(UmpoPowerSecurityDescriptorRootKey, v7, 0, 0, (LPBYTE)a3, cbData);
        if ( Value )
        {
LABEL_30:
          if ( a1 != 14 )
            return (unsigned int)UmpoReadSecurityDescriptor(14, 0, a3, a4);
        }
        else
        {
          v14 = *(_QWORD *)cbData + 2LL;
          *(_QWORD *)cbData = v14;
          if ( (unsigned int)v14 <= *a4 )
          {
            a3[(v14 >> 1) - 1] = 0;
            if ( a1 == 14 )
              UmpoInternalCacheDefaultSecurityDescriptor(a3, v14);
          }
          else
          {
            Value = 234;
            *a4 = v14;
          }
        }
      }
      else
      {
        Value = 234;
        *a4 = v13;
      }
      return Value;
    case 19:
      v7 = L"ActivePowerScheme";
      goto LABEL_21;
    case 20:
      v7 = L"CreatePowerScheme";
      goto LABEL_21;
    case 27:
      v7 = L"ActiveOverlayPowerScheme";
      goto LABEL_21;
    default:
      return 87;
  }
}

```

## disassembly

```asm
0x180003a00  mov     [rsp+arg_0], rbx
0x180003a05  push    rbp
0x180003a06  push    rsi
0x180003a07  push    rdi
0x180003a08  push    r14
0x180003a0a  push    r15
0x180003a0c  sub     rsp, 0A0h
0x180003a13  mov     rax, cs:__security_cookie
0x180003a1a  xor     rax, rsp
0x180003a1d  mov     [rsp+0C8h+var_38], rax
0x180003a25  xor     r15d, r15d
0x180003a28  movsxd  r14, ecx
0x180003a2b  mov     qword ptr [rsp+0C8h+cbData], r15
0x180003a30  mov     rbp, r8
0x180003a33  mov     rsi, r9
0x180003a36  mov     r8, rdx
0x180003a39  cmp     r14d, 1Bh; switch 28 cases
0x180003a3d  ja      def_180003A5D; jumptable 0000000180003A5D default case, cases 4-13,15,17,18,21-26
0x180003a43  lea     rdx, __ImageBase
0x180003a4a  movzx   eax, ds:(byte_180003C8C - 180000000h)[rdx+r14]
0x180003a53  mov     ecx, ds:(jpt_180003A5D - 180000000h)[rdx+rax*4]
0x180003a5a  add     rcx, rdx
0x180003a5d  jmp     rcx; switch jump
0x180003a5f  lea     rdi, aFriendlyname; jumptable 0000000180003A5D case 2
0x180003a66  jmp     loc_180003B69
0x180003a6b  lea     rdi, aDescription; jumptable 0000000180003A5D case 3
0x180003a72  jmp     loc_180003B69
0x180003a77  lea     rdi, ValueName; jumptable 0000000180003A5D case 19
0x180003a7e  jmp     loc_180003B69
0x180003a83  lea     rdi, aCreatepowersch; jumptable 0000000180003A5D case 20
0x180003a8a  jmp     loc_180003B69
0x180003a8f  lea     rdi, aActiveoverlayp; jumptable 0000000180003A5D case 27
0x180003a96  jmp     loc_180003B69
0x180003a9b  lea     rcx, UmpoDefaultSecurityDescriptorLock; jumptable 0000000180003A5D case 14
0x180003aa2  call    cs:__imp_AcquireSRWLockShared
0x180003aa8  mov     r8, cs:UmpoDefaultSecurityDescriptor; pszSrc
0x180003aaf  test    r8, r8
0x180003ab2  jz      loc_180003B38
0x180003ab8  mov     edx, 7FFFFFFFh
0x180003abd  mov     rax, r8
0x180003ac0  mov     ecx, edx
0x180003ac2  cmp     [rax], r15w
0x180003ac6  jz      short loc_180003AD2
0x180003ac8  add     rax, 2
0x180003acc  sub     rcx, 1
0x180003ad0  jnz     short loc_180003AC2
0x180003ad2  test    rcx, rcx
0x180003ad5  jz      short loc_180003B33
0x180003ad7  mov     eax, [rsi]
0x180003ad9  sub     rdx, rcx
0x180003adc  add     rdx, rdx
0x180003adf  test    rcx, rcx
0x180003ae2  cmovz   rdx, r15
0x180003ae6  add     rdx, 2; cbDest
0x180003aea  mov     qword ptr [rsp+0C8h+cbData], rdx
0x180003aef  cmp     rax, rdx
0x180003af2  jb      short loc_180003B1A
0x180003af4  test    rbp, rbp
0x180003af7  jz      short loc_180003B1A
0x180003af9  mov     rcx, rbp; pszDest
0x180003afc  call    StringCbCopyW
0x180003b01  test    eax, eax
0x180003b03  jnz     short loc_180003B38
0x180003b05  lea     rcx, UmpoDefaultSecurityDescriptorLock; SRWLock
0x180003b0c  mov     ebx, r15d
0x180003b0f  call    cs:__imp_ReleaseSRWLockShared
0x180003b15  jmp     loc_180003C40
0x180003b1a  lea     rcx, UmpoDefaultSecurityDescriptorLock; SRWLock
0x180003b21  mov     [rsi], edx
0x180003b23  mov     ebx, 0EAh
0x180003b28  call    cs:__imp_ReleaseSRWLockShared
0x180003b2e  jmp     loc_180003C40
0x180003b33  mov     qword ptr [rsp+0C8h+cbData], r15
0x180003b38  lea     rcx, UmpoDefaultSecurityDescriptorLock; SRWLock
0x180003b3f  call    cs:__imp_ReleaseSRWLockShared
0x180003b45  lea     rdi, aDefault; "Default"
0x180003b4c  jmp     short loc_180003B69
0x180003b4e  test    r8, r8; jumptable 0000000180003A5D cases 0,1,16
0x180003b51  jz      def_180003A5D; jumptable 0000000180003A5D default case, cases 4-13,15,17,18,21-26
0x180003b57  lea     rdx, [rsp+0C8h+var_88]
0x180003b5c  mov     rcx, r8
0x180003b5f  call    UmpoInternalConvertGuidToStringBuffer
0x180003b64  lea     rdi, [rsp+0C8h+var_88]
0x180003b69  mov     rcx, cs:UmpoPowerSecurityDescriptorRootKey; hKey
0x180003b70  lea     rax, [rsp+0C8h+cbData]
0x180003b75  mov     [rsp+0C8h+lpcbData], rax; lpcbData
0x180003b7a  xor     r9d, r9d; lpType
0x180003b7d  xor     r8d, r8d; lpReserved
0x180003b80  mov     [rsp+0C8h+lpData], r15; lpData
0x180003b85  mov     rdx, rdi; lpValueName
0x180003b88  mov     qword ptr [rsp+0C8h+cbData], r15
0x180003b8d  call    cs:__imp_RegQueryValueExW
0x180003b93  mov     ebx, eax
0x180003b95  test    eax, eax
0x180003b97  jnz     loc_180003C1F
0x180003b9d  mov     rax, qword ptr [rsp+0C8h+cbData]
0x180003ba2  add     rax, 2
0x180003ba6  mov     qword ptr [rsp+0C8h+cbData], rax
0x180003bab  test    rbp, rbp
0x180003bae  jz      short loc_180003C16
0x180003bb0  cmp     eax, [rsi]
0x180003bb2  ja      short loc_180003C16
0x180003bb4  mov     rcx, cs:UmpoPowerSecurityDescriptorRootKey; hKey
0x180003bbb  lea     rax, [rsp+0C8h+cbData]
0x180003bc0  mov     [rsp+0C8h+lpcbData], rax; lpcbData
0x180003bc5  xor     r9d, r9d; lpType
0x180003bc8  xor     r8d, r8d; lpReserved
0x180003bcb  mov     [rsp+0C8h+lpData], rbp; lpData
0x180003bd0  mov     rdx, rdi; lpValueName
0x180003bd3  call    cs:__imp_RegQueryValueExW
0x180003bd9  mov     ebx, eax
0x180003bdb  test    eax, eax
0x180003bdd  jnz     short loc_180003C1F
0x180003bdf  mov     rdx, qword ptr [rsp+0C8h+cbData]
0x180003be4  add     rdx, 2; cbDest
0x180003be8  mov     qword ptr [rsp+0C8h+cbData], rdx
0x180003bed  cmp     edx, [rsi]
0x180003bef  jbe     short loc_180003BFA
0x180003bf1  mov     ebx, 0EAh
0x180003bf6  mov     [rsi], edx
0x180003bf8  jmp     short loc_180003C40
0x180003bfa  mov     r8, rdx
0x180003bfd  shr     r8, 1
0x180003c00  mov     [rbp+r8*2-2], r15w
0x180003c06  cmp     r14d, 0Eh
0x180003c0a  jnz     short loc_180003C40
0x180003c0c  mov     rcx, rbp; pszSrc
0x180003c0f  call    UmpoInternalCacheDefaultSecurityDescriptor
0x180003c14  jmp     short loc_180003C40
0x180003c16  mov     ebx, 0EAh
0x180003c1b  mov     [rsi], eax
0x180003c1d  jmp     short loc_180003C40
0x180003c1f  cmp     r14d, 0Eh
0x180003c23  jz      short loc_180003C40
0x180003c25  mov     r9, rsi
0x180003c28  mov     r8, rbp
0x180003c2b  xor     edx, edx
0x180003c2d  mov     ecx, 0Eh
0x180003c32  call    UmpoReadSecurityDescriptor
0x180003c37  mov     ebx, eax
0x180003c39  jmp     short loc_180003C40
0x180003c3b  mov     ebx, 57h ; 'W'; jumptable 0000000180003A5D default case, cases 4-13,15,17,18,21-26
0x180003c40  mov     eax, ebx
0x180003c42  mov     rcx, [rsp+0C8h+var_38]
0x180003c4a  xor     rcx, rsp; StackCookie
0x180003c4d  call    __security_check_cookie
0x180003c52  mov     rbx, [rsp+0C8h+arg_0]
0x180003c5a  add     rsp, 0A0h
0x180003c61  pop     r15
0x180003c63  pop     r14
0x180003c65  pop     rdi
0x180003c66  pop     rsi
0x180003c67  pop     rbp
0x180003c68  retn
```
