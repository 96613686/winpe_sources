# PiRegStateReadStackCreationSettingsFromKey

- ea: `0x140021c0c`
- end: `0x140021deb`
- name: `PiRegStateReadStackCreationSettingsFromKey`
- size: `479`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140021df4`

## callees

- `0x1400120a8`
- `0x140021c0c`
- `0x1400220dc`
- `0x140022374`
- `0x140022624`

## import_xrefs

- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140021cb4`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140021cb4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021cdd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021d1f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021db3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021cdd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021d1f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021db3`

## string_xrefs

- `0x140021c4e`: `Security`

## pseudocode

```c
__int64 __fastcall PiRegStateReadStackCreationSettingsFromKey(HANDLE KeyHandle, __int64 a2)
{
  _DWORD *v2; // r13
  _DWORD *v3; // r15
  _DWORD *v4; // r12
  PVOID v7; // rsi
  NTSTATUS inited; // ebx
  __int64 v9; // r8
  void *v10; // r10
  int FullBuffer; // eax
  __int64 v12; // r9
  PVOID v13; // rax
  int Dword; // eax
  __int64 v15; // r8
  int v16; // eax
  __int64 v17; // r8
  int v18; // eax
  void *v19; // rcx
  PVOID P; // [rsp+30h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int8 v23; // [rsp+98h] [rbp+48h] BYREF
  int v24; // [rsp+A0h] [rbp+50h] BYREF
  PVOID SecurityDescriptor; // [rsp+A8h] [rbp+58h] BYREF

  v2 = (_DWORD *)(a2 + 4);
  v3 = (_DWORD *)(a2 + 16);
  *(_DWORD *)a2 = 0;
  v4 = (_DWORD *)(a2 + 20);
  *(_QWORD *)(a2 + 8) = 0;
  SecurityDescriptor = 0;
  v24 = 0;
  v23 = 0;
  P = 0;
  *(_DWORD *)(a2 + 4) = 0;
  v7 = 0;
  *(_DWORD *)(a2 + 16) = 0;
  *(_DWORD *)(a2 + 20) = 0;
  DestinationString = 0;
  inited = WdmlibRtlInitUnicodeStringEx(&DestinationString, L"Security");
  if ( inited < 0
    || (FullBuffer = CmRegUtilUcValueGetFullBuffer(KeyHandle, &DestinationString, (__int64)&P),
        v7 = P,
        v10 = 0,
        inited = FullBuffer,
        FullBuffer < 0) )
  {
    if ( inited == -1073741772 )
    {
      SecurityDescriptor = v10;
      inited = (int)v10;
    }
  }
  else
  {
    LOBYTE(v12) = 1;
    inited = SeCaptureSecurityDescriptor((char *)P + *((unsigned int *)P + 2), 0, 1, v12, &SecurityDescriptor);
  }
  if ( v7 )
    ExFreePoolWithTag(v7, 0);
  if ( inited < 0 )
    goto LABEL_24;
  if ( SecurityDescriptor )
  {
    inited = SeUtilSecurityInfoFromSecurityDescriptor(SecurityDescriptor, &v23, &v24);
    if ( inited < 0 )
      goto LABEL_24;
    if ( v23 )
    {
      ExFreePoolWithTag(SecurityDescriptor, 0);
    }
    else
    {
      v13 = SecurityDescriptor;
      *(_DWORD *)a2 |= 2u;
      *(_QWORD *)(a2 + 8) = v13;
    }
  }
  Dword = CmRegUtilWstrValueGetDword(KeyHandle, L"DeviceType", v9, v2);
  inited = Dword;
  if ( Dword < 0 )
  {
    if ( Dword != -1073741772 )
      goto LABEL_24;
  }
  else
  {
    *(_DWORD *)a2 |= 1u;
  }
  v16 = CmRegUtilWstrValueGetDword(KeyHandle, L"DeviceCharacteristics", v15, v3);
  inited = v16;
  if ( v16 < 0 )
  {
    if ( v16 != -1073741772 )
      goto LABEL_24;
  }
  else
  {
    *(_DWORD *)a2 |= 4u;
  }
  v18 = CmRegUtilWstrValueGetDword(KeyHandle, L"Exclusive", v17, v4);
  inited = v18;
  if ( v18 >= 0 )
  {
    *(_DWORD *)a2 |= 8u;
    return (unsigned int)inited;
  }
  if ( v18 == -1073741772 )
    return 0;
LABEL_24:
  v19 = *(void **)(a2 + 8);
  if ( v19 )
    ExFreePoolWithTag(v19, 0);
  *(_DWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *v2 = 0;
  *v3 = 0;
  *v4 = 0;
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x140021c0c  mov     [rsp-38h+arg_0], rbx
0x140021c11  push    rbp
0x140021c12  push    rsi
0x140021c13  push    rdi
0x140021c14  push    r12
0x140021c16  push    r13
0x140021c18  push    r14
0x140021c1a  push    r15
0x140021c1c  mov     rbp, rsp
0x140021c1f  sub     rsp, 50h
0x140021c23  xor     r10d, r10d
0x140021c26  lea     r13, [rdx+4]
0x140021c2a  lea     r15, [rdx+10h]
0x140021c2e  mov     [rdx], r10d
0x140021c31  lea     r12, [rdx+14h]
0x140021c35  mov     [rdx+8], r10
0x140021c39  mov     rdi, rdx
0x140021c3c  mov     [rbp+SecurityDescriptor], r10
0x140021c40  mov     r14, rcx
0x140021c43  mov     [rbp+arg_10], r10d
0x140021c47  xorps   xmm0, xmm0
0x140021c4a  mov     [rbp+arg_8], r10b
0x140021c4e  lea     rdx, aSecurity; "Security"
0x140021c55  mov     [rbp+P], r10
0x140021c59  lea     rcx, [rbp+DestinationString]; DestinationString
0x140021c5d  mov     [r13+0], r10d
0x140021c61  mov     esi, r10d
0x140021c64  mov     [r15], r10d
0x140021c67  mov     [r12], r10d
0x140021c6b  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140021c6f  call    WdmlibRtlInitUnicodeStringEx
0x140021c74  mov     ebx, eax
0x140021c76  test    eax, eax
0x140021c78  js      short loc_140021CC4
0x140021c7a  lea     rax, [rbp+P]
0x140021c7e  mov     rcx, r14; KeyHandle
0x140021c81  lea     rdx, [rbp+DestinationString]; ValueName
0x140021c85  mov     [rsp+50h+var_30], rax; __int64
0x140021c8a  call    CmRegUtilUcValueGetFullBuffer
0x140021c8f  mov     rsi, [rbp+P]
0x140021c93  xor     r10d, r10d
0x140021c96  mov     ebx, eax
0x140021c98  test    eax, eax
0x140021c9a  js      short loc_140021CC4
0x140021c9c  mov     ecx, [rsi+8]
0x140021c9f  lea     rax, [rbp+SecurityDescriptor]
0x140021ca3  add     rcx, rsi
0x140021ca6  mov     [rsp+50h+var_30], rax
0x140021cab  mov     r9b, 1
0x140021cae  lea     r8d, [r10+1]
0x140021cb2  xor     edx, edx
0x140021cb4  call    cs:__imp_SeCaptureSecurityDescriptor
0x140021cbb  nop     dword ptr [rax+rax+00h]
0x140021cc0  mov     ebx, eax
0x140021cc2  jmp     short loc_140021CD3
0x140021cc4  cmp     ebx, 0C0000034h
0x140021cca  jnz     short loc_140021CD3
0x140021ccc  mov     [rbp+SecurityDescriptor], r10
0x140021cd0  mov     ebx, r10d
0x140021cd3  test    rsi, rsi
0x140021cd6  jz      short loc_140021CE9
0x140021cd8  xor     edx, edx; Tag
0x140021cda  mov     rcx, rsi; P
0x140021cdd  call    cs:__imp_ExFreePoolWithTag
0x140021ce4  nop     dword ptr [rax+rax+00h]
0x140021ce9  xor     esi, esi
0x140021ceb  test    ebx, ebx
0x140021ced  js      loc_140021DA8
0x140021cf3  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140021cf7  test    rcx, rcx
0x140021cfa  jz      short loc_140021D38
0x140021cfc  lea     r8, [rbp+arg_10]
0x140021d00  lea     rdx, [rbp+arg_8]
0x140021d04  call    SeUtilSecurityInfoFromSecurityDescriptor
0x140021d09  mov     ebx, eax
0x140021d0b  test    eax, eax
0x140021d0d  js      loc_140021DA8
0x140021d13  cmp     [rbp+arg_8], sil
0x140021d17  jz      short loc_140021D2D
0x140021d19  mov     rcx, [rbp+SecurityDescriptor]; P
0x140021d1d  xor     edx, edx; Tag
0x140021d1f  call    cs:__imp_ExFreePoolWithTag
0x140021d26  nop     dword ptr [rax+rax+00h]
0x140021d2b  jmp     short loc_140021D38
0x140021d2d  mov     rax, [rbp+SecurityDescriptor]
0x140021d31  or      dword ptr [rdi], 2
0x140021d34  mov     [rdi+8], rax
0x140021d38  mov     r9, r13
0x140021d3b  lea     rdx, aDevicetype; "DeviceType"
0x140021d42  mov     rcx, r14
0x140021d45  call    CmRegUtilWstrValueGetDword
0x140021d4a  mov     ebx, eax
0x140021d4c  test    eax, eax
0x140021d4e  js      short loc_140021D55
0x140021d50  or      dword ptr [rdi], 1
0x140021d53  jmp     short loc_140021D5C
0x140021d55  cmp     eax, 0C0000034h
0x140021d5a  jnz     short loc_140021DA8
0x140021d5c  mov     r9, r15
0x140021d5f  lea     rdx, aDevicecharacte; "DeviceCharacteristics"
0x140021d66  mov     rcx, r14
0x140021d69  call    CmRegUtilWstrValueGetDword
0x140021d6e  mov     ebx, eax
0x140021d70  test    eax, eax
0x140021d72  js      short loc_140021D79
0x140021d74  or      dword ptr [rdi], 4
0x140021d77  jmp     short loc_140021D80
0x140021d79  cmp     eax, 0C0000034h
0x140021d7e  jnz     short loc_140021DA8
0x140021d80  mov     r9, r12
0x140021d83  lea     rdx, aExclusive; "Exclusive"
0x140021d8a  mov     rcx, r14
0x140021d8d  call    CmRegUtilWstrValueGetDword
0x140021d92  mov     ebx, eax
0x140021d94  test    eax, eax
0x140021d96  js      short loc_140021D9D
0x140021d98  or      dword ptr [rdi], 8
0x140021d9b  jmp     short loc_140021DD0
0x140021d9d  cmp     eax, 0C0000034h
0x140021da2  jnz     short loc_140021DA8
0x140021da4  mov     ebx, esi
0x140021da6  jmp     short loc_140021DD0
0x140021da8  mov     rcx, [rdi+8]; P
0x140021dac  test    rcx, rcx
0x140021daf  jz      short loc_140021DBF
0x140021db1  xor     edx, edx; Tag
0x140021db3  call    cs:__imp_ExFreePoolWithTag
0x140021dba  nop     dword ptr [rax+rax+00h]
0x140021dbf  mov     [rdi], esi
0x140021dc1  mov     [rdi+8], rsi
0x140021dc5  mov     [r13+0], esi
0x140021dc9  mov     [r15], esi
0x140021dcc  mov     [r12], esi
0x140021dd0  mov     eax, ebx
0x140021dd2  mov     rbx, [rsp+50h+arg_0]
0x140021dda  add     rsp, 50h
0x140021dde  pop     r15
0x140021de0  pop     r14
0x140021de2  pop     r13
0x140021de4  pop     r12
0x140021de6  pop     rdi
0x140021de7  pop     rsi
0x140021de8  pop     rbp
0x140021de9  retn
```
