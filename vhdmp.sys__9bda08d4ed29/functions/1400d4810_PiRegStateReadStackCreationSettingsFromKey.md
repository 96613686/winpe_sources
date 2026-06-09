# PiRegStateReadStackCreationSettingsFromKey

- ea: `0x1400d4810`
- end: `0x1400d49ef`
- name: `PiRegStateReadStackCreationSettingsFromKey`
- size: `479`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400d49f8`

## callees

- `0x14004f1c0`
- `0x1400d4810`
- `0x1400d4ce0`
- `0x1400d4f78`
- `0x1400d5228`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400d48e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d4923`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d49b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d48e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d4923`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d49b7`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1400d48b8`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1400d48b8`

## string_xrefs

- `0x1400d4852`: `Security`

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
0x1400d4810  mov     [rsp-38h+arg_0], rbx
0x1400d4815  push    rbp
0x1400d4816  push    rsi
0x1400d4817  push    rdi
0x1400d4818  push    r12
0x1400d481a  push    r13
0x1400d481c  push    r14
0x1400d481e  push    r15
0x1400d4820  mov     rbp, rsp
0x1400d4823  sub     rsp, 50h
0x1400d4827  xor     r10d, r10d
0x1400d482a  lea     r13, [rdx+4]
0x1400d482e  lea     r15, [rdx+10h]
0x1400d4832  mov     [rdx], r10d
0x1400d4835  lea     r12, [rdx+14h]
0x1400d4839  mov     [rdx+8], r10
0x1400d483d  mov     rdi, rdx
0x1400d4840  mov     [rbp+SecurityDescriptor], r10
0x1400d4844  mov     r14, rcx
0x1400d4847  mov     [rbp+arg_10], r10d
0x1400d484b  xorps   xmm0, xmm0
0x1400d484e  mov     [rbp+arg_8], r10b
0x1400d4852  lea     rdx, aSecurity; "Security"
0x1400d4859  mov     [rbp+P], r10
0x1400d485d  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400d4861  mov     [r13+0], r10d
0x1400d4865  mov     esi, r10d
0x1400d4868  mov     [r15], r10d
0x1400d486b  mov     [r12], r10d
0x1400d486f  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400d4873  call    WdmlibRtlInitUnicodeStringEx
0x1400d4878  mov     ebx, eax
0x1400d487a  test    eax, eax
0x1400d487c  js      short loc_1400D48C8
0x1400d487e  lea     rax, [rbp+P]
0x1400d4882  mov     rcx, r14; KeyHandle
0x1400d4885  lea     rdx, [rbp+DestinationString]; ValueName
0x1400d4889  mov     [rsp+50h+var_30], rax; __int64
0x1400d488e  call    CmRegUtilUcValueGetFullBuffer
0x1400d4893  mov     rsi, [rbp+P]
0x1400d4897  xor     r10d, r10d
0x1400d489a  mov     ebx, eax
0x1400d489c  test    eax, eax
0x1400d489e  js      short loc_1400D48C8
0x1400d48a0  mov     ecx, [rsi+8]
0x1400d48a3  lea     rax, [rbp+SecurityDescriptor]
0x1400d48a7  add     rcx, rsi
0x1400d48aa  mov     [rsp+50h+var_30], rax
0x1400d48af  mov     r9b, 1
0x1400d48b2  lea     r8d, [r10+1]
0x1400d48b6  xor     edx, edx
0x1400d48b8  call    cs:__imp_SeCaptureSecurityDescriptor
0x1400d48bf  nop     dword ptr [rax+rax+00h]
0x1400d48c4  mov     ebx, eax
0x1400d48c6  jmp     short loc_1400D48D7
0x1400d48c8  cmp     ebx, 0C0000034h
0x1400d48ce  jnz     short loc_1400D48D7
0x1400d48d0  mov     [rbp+SecurityDescriptor], r10
0x1400d48d4  mov     ebx, r10d
0x1400d48d7  test    rsi, rsi
0x1400d48da  jz      short loc_1400D48ED
0x1400d48dc  xor     edx, edx; Tag
0x1400d48de  mov     rcx, rsi; P
0x1400d48e1  call    cs:__imp_ExFreePoolWithTag
0x1400d48e8  nop     dword ptr [rax+rax+00h]
0x1400d48ed  xor     esi, esi
0x1400d48ef  test    ebx, ebx
0x1400d48f1  js      loc_1400D49AC
0x1400d48f7  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1400d48fb  test    rcx, rcx
0x1400d48fe  jz      short loc_1400D493C
0x1400d4900  lea     r8, [rbp+arg_10]
0x1400d4904  lea     rdx, [rbp+arg_8]
0x1400d4908  call    SeUtilSecurityInfoFromSecurityDescriptor
0x1400d490d  mov     ebx, eax
0x1400d490f  test    eax, eax
0x1400d4911  js      loc_1400D49AC
0x1400d4917  cmp     [rbp+arg_8], sil
0x1400d491b  jz      short loc_1400D4931
0x1400d491d  mov     rcx, [rbp+SecurityDescriptor]; P
0x1400d4921  xor     edx, edx; Tag
0x1400d4923  call    cs:__imp_ExFreePoolWithTag
0x1400d492a  nop     dword ptr [rax+rax+00h]
0x1400d492f  jmp     short loc_1400D493C
0x1400d4931  mov     rax, [rbp+SecurityDescriptor]
0x1400d4935  or      dword ptr [rdi], 2
0x1400d4938  mov     [rdi+8], rax
0x1400d493c  mov     r9, r13
0x1400d493f  lea     rdx, aDevicetype; "DeviceType"
0x1400d4946  mov     rcx, r14
0x1400d4949  call    CmRegUtilWstrValueGetDword
0x1400d494e  mov     ebx, eax
0x1400d4950  test    eax, eax
0x1400d4952  js      short loc_1400D4959
0x1400d4954  or      dword ptr [rdi], 1
0x1400d4957  jmp     short loc_1400D4960
0x1400d4959  cmp     eax, 0C0000034h
0x1400d495e  jnz     short loc_1400D49AC
0x1400d4960  mov     r9, r15
0x1400d4963  lea     rdx, aDevicecharacte; "DeviceCharacteristics"
0x1400d496a  mov     rcx, r14
0x1400d496d  call    CmRegUtilWstrValueGetDword
0x1400d4972  mov     ebx, eax
0x1400d4974  test    eax, eax
0x1400d4976  js      short loc_1400D497D
0x1400d4978  or      dword ptr [rdi], 4
0x1400d497b  jmp     short loc_1400D4984
0x1400d497d  cmp     eax, 0C0000034h
0x1400d4982  jnz     short loc_1400D49AC
0x1400d4984  mov     r9, r12
0x1400d4987  lea     rdx, aExclusive; "Exclusive"
0x1400d498e  mov     rcx, r14
0x1400d4991  call    CmRegUtilWstrValueGetDword
0x1400d4996  mov     ebx, eax
0x1400d4998  test    eax, eax
0x1400d499a  js      short loc_1400D49A1
0x1400d499c  or      dword ptr [rdi], 8
0x1400d499f  jmp     short loc_1400D49D4
0x1400d49a1  cmp     eax, 0C0000034h
0x1400d49a6  jnz     short loc_1400D49AC
0x1400d49a8  mov     ebx, esi
0x1400d49aa  jmp     short loc_1400D49D4
0x1400d49ac  mov     rcx, [rdi+8]; P
0x1400d49b0  test    rcx, rcx
0x1400d49b3  jz      short loc_1400D49C3
0x1400d49b5  xor     edx, edx; Tag
0x1400d49b7  call    cs:__imp_ExFreePoolWithTag
0x1400d49be  nop     dword ptr [rax+rax+00h]
0x1400d49c3  mov     [rdi], esi
0x1400d49c5  mov     [rdi+8], rsi
0x1400d49c9  mov     [r13+0], esi
0x1400d49cd  mov     [r15], esi
0x1400d49d0  mov     [r12], esi
0x1400d49d4  mov     eax, ebx
0x1400d49d6  mov     rbx, [rsp+50h+arg_0]
0x1400d49de  add     rsp, 50h
0x1400d49e2  pop     r15
0x1400d49e4  pop     r14
0x1400d49e6  pop     r13
0x1400d49e8  pop     r12
0x1400d49ea  pop     rdi
0x1400d49eb  pop     rsi
0x1400d49ec  pop     rbp
0x1400d49ed  retn
```
