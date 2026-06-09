# PiRegStateReadStackCreationSettingsFromKey

- ea: `0x140018e4c`
- end: `0x14001902b`
- name: `PiRegStateReadStackCreationSettingsFromKey`
- size: `479`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140019034`

## callees

- `0x140004f04`
- `0x140018e4c`
- `0x14001931c`
- `0x1400195b4`
- `0x140019864`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140018f1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018f5f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018ff3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018f1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018f5f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018ff3`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140018ef4`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140018ef4`

## string_xrefs

- `0x140018e8e`: `Security`

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
0x140018e4c  mov     [rsp-38h+arg_0], rbx
0x140018e51  push    rbp
0x140018e52  push    rsi
0x140018e53  push    rdi
0x140018e54  push    r12
0x140018e56  push    r13
0x140018e58  push    r14
0x140018e5a  push    r15
0x140018e5c  mov     rbp, rsp
0x140018e5f  sub     rsp, 50h
0x140018e63  xor     r10d, r10d
0x140018e66  lea     r13, [rdx+4]
0x140018e6a  lea     r15, [rdx+10h]
0x140018e6e  mov     [rdx], r10d
0x140018e71  lea     r12, [rdx+14h]
0x140018e75  mov     [rdx+8], r10
0x140018e79  mov     rdi, rdx
0x140018e7c  mov     [rbp+SecurityDescriptor], r10
0x140018e80  mov     r14, rcx
0x140018e83  mov     [rbp+arg_10], r10d
0x140018e87  xorps   xmm0, xmm0
0x140018e8a  mov     [rbp+arg_8], r10b
0x140018e8e  lea     rdx, aSecurity; "Security"
0x140018e95  mov     [rbp+P], r10
0x140018e99  lea     rcx, [rbp+DestinationString]; DestinationString
0x140018e9d  mov     [r13+0], r10d
0x140018ea1  mov     esi, r10d
0x140018ea4  mov     [r15], r10d
0x140018ea7  mov     [r12], r10d
0x140018eab  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140018eaf  call    WdmlibRtlInitUnicodeStringEx
0x140018eb4  mov     ebx, eax
0x140018eb6  test    eax, eax
0x140018eb8  js      short loc_140018F04
0x140018eba  lea     rax, [rbp+P]
0x140018ebe  mov     rcx, r14; KeyHandle
0x140018ec1  lea     rdx, [rbp+DestinationString]; ValueName
0x140018ec5  mov     [rsp+50h+var_30], rax; __int64
0x140018eca  call    CmRegUtilUcValueGetFullBuffer
0x140018ecf  mov     rsi, [rbp+P]
0x140018ed3  xor     r10d, r10d
0x140018ed6  mov     ebx, eax
0x140018ed8  test    eax, eax
0x140018eda  js      short loc_140018F04
0x140018edc  mov     ecx, [rsi+8]
0x140018edf  lea     rax, [rbp+SecurityDescriptor]
0x140018ee3  add     rcx, rsi
0x140018ee6  mov     [rsp+50h+var_30], rax
0x140018eeb  mov     r9b, 1
0x140018eee  lea     r8d, [r10+1]
0x140018ef2  xor     edx, edx
0x140018ef4  call    cs:__imp_SeCaptureSecurityDescriptor
0x140018efb  nop     dword ptr [rax+rax+00h]
0x140018f00  mov     ebx, eax
0x140018f02  jmp     short loc_140018F13
0x140018f04  cmp     ebx, 0C0000034h
0x140018f0a  jnz     short loc_140018F13
0x140018f0c  mov     [rbp+SecurityDescriptor], r10
0x140018f10  mov     ebx, r10d
0x140018f13  test    rsi, rsi
0x140018f16  jz      short loc_140018F29
0x140018f18  xor     edx, edx; Tag
0x140018f1a  mov     rcx, rsi; P
0x140018f1d  call    cs:__imp_ExFreePoolWithTag
0x140018f24  nop     dword ptr [rax+rax+00h]
0x140018f29  xor     esi, esi
0x140018f2b  test    ebx, ebx
0x140018f2d  js      loc_140018FE8
0x140018f33  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140018f37  test    rcx, rcx
0x140018f3a  jz      short loc_140018F78
0x140018f3c  lea     r8, [rbp+arg_10]
0x140018f40  lea     rdx, [rbp+arg_8]
0x140018f44  call    SeUtilSecurityInfoFromSecurityDescriptor
0x140018f49  mov     ebx, eax
0x140018f4b  test    eax, eax
0x140018f4d  js      loc_140018FE8
0x140018f53  cmp     [rbp+arg_8], sil
0x140018f57  jz      short loc_140018F6D
0x140018f59  mov     rcx, [rbp+SecurityDescriptor]; P
0x140018f5d  xor     edx, edx; Tag
0x140018f5f  call    cs:__imp_ExFreePoolWithTag
0x140018f66  nop     dword ptr [rax+rax+00h]
0x140018f6b  jmp     short loc_140018F78
0x140018f6d  mov     rax, [rbp+SecurityDescriptor]
0x140018f71  or      dword ptr [rdi], 2
0x140018f74  mov     [rdi+8], rax
0x140018f78  mov     r9, r13
0x140018f7b  lea     rdx, aDevicetype; "DeviceType"
0x140018f82  mov     rcx, r14
0x140018f85  call    CmRegUtilWstrValueGetDword
0x140018f8a  mov     ebx, eax
0x140018f8c  test    eax, eax
0x140018f8e  js      short loc_140018F95
0x140018f90  or      dword ptr [rdi], 1
0x140018f93  jmp     short loc_140018F9C
0x140018f95  cmp     eax, 0C0000034h
0x140018f9a  jnz     short loc_140018FE8
0x140018f9c  mov     r9, r15
0x140018f9f  lea     rdx, aDevicecharacte; "DeviceCharacteristics"
0x140018fa6  mov     rcx, r14
0x140018fa9  call    CmRegUtilWstrValueGetDword
0x140018fae  mov     ebx, eax
0x140018fb0  test    eax, eax
0x140018fb2  js      short loc_140018FB9
0x140018fb4  or      dword ptr [rdi], 4
0x140018fb7  jmp     short loc_140018FC0
0x140018fb9  cmp     eax, 0C0000034h
0x140018fbe  jnz     short loc_140018FE8
0x140018fc0  mov     r9, r12
0x140018fc3  lea     rdx, aExclusive; "Exclusive"
0x140018fca  mov     rcx, r14
0x140018fcd  call    CmRegUtilWstrValueGetDword
0x140018fd2  mov     ebx, eax
0x140018fd4  test    eax, eax
0x140018fd6  js      short loc_140018FDD
0x140018fd8  or      dword ptr [rdi], 8
0x140018fdb  jmp     short loc_140019010
0x140018fdd  cmp     eax, 0C0000034h
0x140018fe2  jnz     short loc_140018FE8
0x140018fe4  mov     ebx, esi
0x140018fe6  jmp     short loc_140019010
0x140018fe8  mov     rcx, [rdi+8]; P
0x140018fec  test    rcx, rcx
0x140018fef  jz      short loc_140018FFF
0x140018ff1  xor     edx, edx; Tag
0x140018ff3  call    cs:__imp_ExFreePoolWithTag
0x140018ffa  nop     dword ptr [rax+rax+00h]
0x140018fff  mov     [rdi], esi
0x140019001  mov     [rdi+8], rsi
0x140019005  mov     [r13+0], esi
0x140019009  mov     [r15], esi
0x14001900c  mov     [r12], esi
0x140019010  mov     eax, ebx
0x140019012  mov     rbx, [rsp+50h+arg_0]
0x14001901a  add     rsp, 50h
0x14001901e  pop     r15
0x140019020  pop     r14
0x140019022  pop     r13
0x140019024  pop     r12
0x140019026  pop     rdi
0x140019027  pop     rsi
0x140019028  pop     rbp
0x140019029  retn
```
