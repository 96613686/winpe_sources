# TsCryptSetSecurityDescriptorDacl(unsigned __int64,_ACL const *,int)

- ea: `0x18003f0b0`
- end: `0x18003f18e`
- name: `?TsCryptSetSecurityDescriptorDacl@@YAH_KPEBU_ACL@@H@Z`
- size: `222`
- prototype: `__int64 __fastcall(NCRYPT_HANDLE hObject, PACL pDacl, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002b830`
- `0x18003eae0`

## callees

- `0x18003f0b0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18003f118`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18003f118`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18003f0e4`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18003f0e4`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x18003f101`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x18003f101`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18003f14b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18003f14b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003f0cc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003f0cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f17b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f17b`
- `ncrypt!NCryptIsKeyHandle` at `0x18003f125`
- `ncrypt!NCryptIsKeyHandle` at `0x18003f125`
- `ncrypt!NCryptSetProperty` at `0x18003f169`
- `ncrypt!NCryptSetProperty` at `0x18003f169`
- `CRYPTSP!CryptSetProvParam` at `0x18003f13c`
- `CRYPTSP!CryptSetProvParam` at `0x18003f13c`

## string_xrefs

- `0x18003f15f`: `Security Descr`

## pseudocode

```c
__int64 __fastcall TsCryptSetSecurityDescriptorDacl(NCRYPT_HANDLE hObject, PACL pDacl, int a3)
{
  unsigned int v3; // edi
  HLOCAL v7; // rax
  void *v8; // rbx
  DWORD SecurityDescriptorLength; // eax

  v3 = 0;
  v7 = LocalAlloc(0x40u, 0x28u);
  v8 = v7;
  if ( v7 )
  {
    if ( !InitializeSecurityDescriptor(v7, 1u)
      || a3 && !SetSecurityDescriptorControl(v8, 0x1000u, 0x1000u)
      || !SetSecurityDescriptorDacl(v8, 1, pDacl, 0) )
    {
      goto LABEL_11;
    }
    if ( NCryptIsKeyHandle(hObject) )
    {
      SecurityDescriptorLength = GetSecurityDescriptorLength(v8);
      if ( NCryptSetProperty(hObject, L"Security Descr", (PBYTE)v8, SecurityDescriptorLength, 4u) >= 0 )
LABEL_10:
        v3 = 1;
    }
    else if ( CryptSetProvParam(hObject, 8u, (const BYTE *)v8, 4u) )
    {
      goto LABEL_10;
    }
LABEL_11:
    LocalFree(v8);
  }
  return v3;
}

```

## disassembly

```asm
0x18003f0b0  push    rbx
0x18003f0b2  push    rbp
0x18003f0b3  push    rsi
0x18003f0b4  push    rdi
0x18003f0b5  push    r14
0x18003f0b7  sub     rsp, 30h
0x18003f0bb  xor     edi, edi
0x18003f0bd  mov     r14, rdx
0x18003f0c0  mov     rsi, rcx
0x18003f0c3  mov     ebp, r8d
0x18003f0c6  lea     edx, [rdi+28h]; uBytes
0x18003f0c9  lea     ecx, [rdi+40h]; uFlags
0x18003f0cc  call    cs:__imp_LocalAlloc
0x18003f0d2  mov     rbx, rax
0x18003f0d5  test    rax, rax
0x18003f0d8  jz      loc_18003F181
0x18003f0de  lea     edx, [rdi+1]; dwRevision
0x18003f0e1  mov     rcx, rax; pSecurityDescriptor
0x18003f0e4  call    cs:__imp_InitializeSecurityDescriptor
0x18003f0ea  test    eax, eax
0x18003f0ec  jz      loc_18003F178
0x18003f0f2  test    ebp, ebp
0x18003f0f4  jz      short loc_18003F10B
0x18003f0f6  mov     edx, 1000h; ControlBitsOfInterest
0x18003f0fb  mov     rcx, rbx; pSecurityDescriptor
0x18003f0fe  mov     r8d, edx; ControlBitsToSet
0x18003f101  call    cs:__imp_SetSecurityDescriptorControl
0x18003f107  test    eax, eax
0x18003f109  jz      short loc_18003F178
0x18003f10b  xor     r9d, r9d; bDaclDefaulted
0x18003f10e  mov     r8, r14; pDacl
0x18003f111  mov     rcx, rbx; pSecurityDescriptor
0x18003f114  lea     edx, [r9+1]; bDaclPresent
0x18003f118  call    cs:__imp_SetSecurityDescriptorDacl
0x18003f11e  test    eax, eax
0x18003f120  jz      short loc_18003F178
0x18003f122  mov     rcx, rsi; hKey
0x18003f125  call    cs:__imp_NCryptIsKeyHandle
0x18003f12b  test    eax, eax
0x18003f12d  jnz     short loc_18003F148
0x18003f12f  lea     r9d, [rax+4]; dwFlags
0x18003f133  mov     r8, rbx; pbData
0x18003f136  lea     edx, [rax+8]; dwParam
0x18003f139  mov     rcx, rsi; hProv
0x18003f13c  call    cs:__imp_CryptSetProvParam
0x18003f142  test    eax, eax
0x18003f144  jz      short loc_18003F178
0x18003f146  jmp     short loc_18003F173
0x18003f148  mov     rcx, rbx; pSecurityDescriptor
0x18003f14b  call    cs:__imp_GetSecurityDescriptorLength
0x18003f151  mov     r8, rbx; pbInput
0x18003f154  mov     [rsp+58h+dwFlags], 4; dwFlags
0x18003f15c  mov     r9d, eax; cbInput
0x18003f15f  lea     rdx, pszProperty; "Security Descr"
0x18003f166  mov     rcx, rsi; hObject
0x18003f169  call    cs:__imp_NCryptSetProperty
0x18003f16f  test    eax, eax
0x18003f171  js      short loc_18003F178
0x18003f173  mov     edi, 1
0x18003f178  mov     rcx, rbx; hMem
0x18003f17b  call    cs:__imp_LocalFree
0x18003f181  mov     eax, edi
0x18003f183  add     rsp, 30h
0x18003f187  pop     r14
0x18003f189  pop     rdi
0x18003f18a  pop     rsi
0x18003f18b  pop     rbp
0x18003f18c  pop     rbx
0x18003f18d  retn
```
