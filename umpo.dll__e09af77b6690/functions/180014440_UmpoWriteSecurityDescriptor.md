# UmpoWriteSecurityDescriptor

- ea: `0x180014440`
- end: `0x180014593`
- name: `UmpoWriteSecurityDescriptor`
- size: `339`
- prototype: `__int64 __fastcall(unsigned int, __int64, const BYTE *, DWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800150f0`

## callees

- `0x180010070`
- `0x180012748`
- `0x180012864`
- `0x180014440`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180014547`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180014547`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001451c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001451c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014568`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014568`

## string_xrefs

- `0x1800144b6`: `CreatePowerScheme`

## pseudocode

```c
__int64 __fastcall UmpoWriteSecurityDescriptor(unsigned int a1, __int64 a2, const BYTE *a3, DWORD a4)
{
  unsigned int v7; // ebx
  const WCHAR *v8; // rbx
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+30h] [rbp-88h] BYREF
  _WORD v11[40]; // [rsp+40h] [rbp-78h] BYREF

  SecurityDescriptor = 0;
  if ( a1 < 2 )
    goto LABEL_16;
  switch ( a1 )
  {
    case 2u:
      v8 = L"FriendlyName";
      break;
    case 3u:
      v8 = L"Description";
      break;
    case 0xEu:
      v8 = L"Default";
      break;
    case 0x10u:
LABEL_16:
      if ( !a2 )
        return 87;
      UmpoInternalConvertGuidToStringBuffer(a2, v11);
      v8 = v11;
      break;
    case 0x13u:
      v8 = L"ActivePowerScheme";
      break;
    case 0x14u:
      v8 = L"CreatePowerScheme";
      break;
    case 0x1Bu:
      v8 = L"ActiveOverlayPowerScheme";
      break;
    default:
      return 87;
  }
  if ( a4 < 2 )
    return 87;
  a3[a4 - 1] = 0;
  a3[a4 - 2] = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW((LPCWSTR)a3, 1u, &SecurityDescriptor, 0) )
  {
    v7 = RegSetValueExW(UmpoPowerSecurityDescriptorRootKey, v8, 0, 1u, a3, a4);
    if ( a1 == 14 )
      UmpoInternalCacheDefaultSecurityDescriptor((STRSAFE_LPCWSTR)a3, a4);
  }
  else
  {
    v7 = 87;
  }
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return v7;
}

```

## disassembly

```asm
0x180014440  mov     [rsp+arg_0], rbx
0x180014445  push    rbp
0x180014446  push    rsi
0x180014447  push    rdi
0x180014448  sub     rsp, 0A0h
0x18001444f  mov     rax, cs:__security_cookie
0x180014456  xor     rax, rsp
0x180014459  mov     [rsp+0B8h+var_28], rax
0x180014461  mov     [rsp+0B8h+SecurityDescriptor], 0
0x18001446a  mov     rsi, r8
0x18001446d  mov     r8, rdx
0x180014470  mov     edx, ecx
0x180014472  mov     edi, r9d
0x180014475  mov     ebp, ecx
0x180014477  test    ecx, ecx
0x180014479  jz      short loc_1800144E3
0x18001447b  sub     edx, 1
0x18001447e  jz      short loc_1800144E3
0x180014480  sub     edx, 1
0x180014483  jz      short loc_1800144DA
0x180014485  sub     edx, 1
0x180014488  jz      short loc_1800144D1
0x18001448a  sub     edx, 0Bh
0x18001448d  jz      short loc_1800144C8
0x18001448f  sub     edx, 2
0x180014492  jz      short loc_1800144E3
0x180014494  sub     edx, 3
0x180014497  jz      short loc_1800144BF
0x180014499  sub     edx, 1
0x18001449c  jz      short loc_1800144B6
0x18001449e  cmp     edx, 7
0x1800144a1  jz      short loc_1800144AD
0x1800144a3  mov     ebx, 57h ; 'W'
0x1800144a8  jmp     loc_18001456E
0x1800144ad  lea     rbx, aActiveoverlayp; "ActiveOverlayPowerScheme"
0x1800144b4  jmp     short loc_1800144FA
0x1800144b6  lea     rbx, aCreatepowersch; "CreatePowerScheme"
0x1800144bd  jmp     short loc_1800144FA
0x1800144bf  lea     rbx, ValueName; "ActivePowerScheme"
0x1800144c6  jmp     short loc_1800144FA
0x1800144c8  lea     rbx, aDefault; "Default"
0x1800144cf  jmp     short loc_1800144FA
0x1800144d1  lea     rbx, aDescription; "Description"
0x1800144d8  jmp     short loc_1800144FA
0x1800144da  lea     rbx, aFriendlyname; "FriendlyName"
0x1800144e1  jmp     short loc_1800144FA
0x1800144e3  test    r8, r8
0x1800144e6  jz      short loc_1800144A3
0x1800144e8  lea     rdx, [rsp+0B8h+var_78]
0x1800144ed  mov     rcx, r8
0x1800144f0  call    UmpoInternalConvertGuidToStringBuffer
0x1800144f5  lea     rbx, [rsp+0B8h+var_78]
0x1800144fa  cmp     edi, 2
0x1800144fd  jb      short loc_1800144A3
0x1800144ff  lea     eax, [rdi-1]
0x180014502  xor     r9d, r9d; SecurityDescriptorSize
0x180014505  mov     byte ptr [rax+rsi], 0
0x180014509  lea     r8, [rsp+0B8h+SecurityDescriptor]; SecurityDescriptor
0x18001450e  lea     eax, [rdi-2]
0x180014511  mov     rcx, rsi; StringSecurityDescriptor
0x180014514  mov     byte ptr [rax+rsi], 0
0x180014518  lea     edx, [r9+1]; StringSDRevision
0x18001451c  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180014522  test    eax, eax
0x180014524  jnz     short loc_18001452B
0x180014526  lea     ebx, [rax+57h]
0x180014529  jmp     short loc_18001455E
0x18001452b  mov     rcx, cs:UmpoPowerSecurityDescriptorRootKey; hKey
0x180014532  mov     r9d, 1; dwType
0x180014538  mov     [rsp+0B8h+cbData], edi; cbData
0x18001453c  xor     r8d, r8d; Reserved
0x18001453f  mov     rdx, rbx; lpValueName
0x180014542  mov     [rsp+0B8h+lpData], rsi; lpData
0x180014547  call    cs:__imp_RegSetValueExW
0x18001454d  mov     ebx, eax
0x18001454f  cmp     ebp, 0Eh
0x180014552  jnz     short loc_18001455E
0x180014554  mov     edx, edi; cbDest
0x180014556  mov     rcx, rsi; pszSrc
0x180014559  call    UmpoInternalCacheDefaultSecurityDescriptor
0x18001455e  mov     rcx, [rsp+0B8h+SecurityDescriptor]; hMem
0x180014563  test    rcx, rcx
0x180014566  jz      short loc_18001456E
0x180014568  call    cs:__imp_LocalFree
0x18001456e  mov     eax, ebx
0x180014570  mov     rcx, [rsp+0B8h+var_28]
0x180014578  xor     rcx, rsp; StackCookie
0x18001457b  call    __security_check_cookie
0x180014580  mov     rbx, [rsp+0B8h+arg_0]
0x180014588  add     rsp, 0A0h
0x18001458f  pop     rdi
0x180014590  pop     rsi
0x180014591  pop     rbp
0x180014592  retn
```
