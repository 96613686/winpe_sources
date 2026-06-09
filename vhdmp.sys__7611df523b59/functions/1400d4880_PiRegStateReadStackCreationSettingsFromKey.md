# PiRegStateReadStackCreationSettingsFromKey

- ea: `0x1400d4880`
- end: `0x1400d4a5f`
- name: `PiRegStateReadStackCreationSettingsFromKey`
- size: `479`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400d4a68`

## callees

- `0x14004edd0`
- `0x1400d4880`
- `0x1400d4d50`
- `0x1400d4fe8`
- `0x1400d5298`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400d4951`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d4993`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d4a27`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d4951`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d4993`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d4a27`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1400d4928`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1400d4928`

## string_xrefs

- `0x1400d48c2`: `Security`

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
0x1400d4880  mov     [rsp-38h+arg_0], rbx
0x1400d4885  push    rbp
0x1400d4886  push    rsi
0x1400d4887  push    rdi
0x1400d4888  push    r12
0x1400d488a  push    r13
0x1400d488c  push    r14
0x1400d488e  push    r15
0x1400d4890  mov     rbp, rsp
0x1400d4893  sub     rsp, 50h
0x1400d4897  xor     r10d, r10d
0x1400d489a  lea     r13, [rdx+4]
0x1400d489e  lea     r15, [rdx+10h]
0x1400d48a2  mov     [rdx], r10d
0x1400d48a5  lea     r12, [rdx+14h]
0x1400d48a9  mov     [rdx+8], r10
0x1400d48ad  mov     rdi, rdx
0x1400d48b0  mov     [rbp+SecurityDescriptor], r10
0x1400d48b4  mov     r14, rcx
0x1400d48b7  mov     [rbp+arg_10], r10d
0x1400d48bb  xorps   xmm0, xmm0
0x1400d48be  mov     [rbp+arg_8], r10b
0x1400d48c2  lea     rdx, aSecurity; "Security"
0x1400d48c9  mov     [rbp+P], r10
0x1400d48cd  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400d48d1  mov     [r13+0], r10d
0x1400d48d5  mov     esi, r10d
0x1400d48d8  mov     [r15], r10d
0x1400d48db  mov     [r12], r10d
0x1400d48df  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400d48e3  call    WdmlibRtlInitUnicodeStringEx
0x1400d48e8  mov     ebx, eax
0x1400d48ea  test    eax, eax
0x1400d48ec  js      short loc_1400D4938
0x1400d48ee  lea     rax, [rbp+P]
0x1400d48f2  mov     rcx, r14; KeyHandle
0x1400d48f5  lea     rdx, [rbp+DestinationString]; ValueName
0x1400d48f9  mov     [rsp+50h+var_30], rax; __int64
0x1400d48fe  call    CmRegUtilUcValueGetFullBuffer
0x1400d4903  mov     rsi, [rbp+P]
0x1400d4907  xor     r10d, r10d
0x1400d490a  mov     ebx, eax
0x1400d490c  test    eax, eax
0x1400d490e  js      short loc_1400D4938
0x1400d4910  mov     ecx, [rsi+8]
0x1400d4913  lea     rax, [rbp+SecurityDescriptor]
0x1400d4917  add     rcx, rsi
0x1400d491a  mov     [rsp+50h+var_30], rax
0x1400d491f  mov     r9b, 1
0x1400d4922  lea     r8d, [r10+1]
0x1400d4926  xor     edx, edx
0x1400d4928  call    cs:__imp_SeCaptureSecurityDescriptor
0x1400d492f  nop     dword ptr [rax+rax+00h]
0x1400d4934  mov     ebx, eax
0x1400d4936  jmp     short loc_1400D4947
0x1400d4938  cmp     ebx, 0C0000034h
0x1400d493e  jnz     short loc_1400D4947
0x1400d4940  mov     [rbp+SecurityDescriptor], r10
0x1400d4944  mov     ebx, r10d
0x1400d4947  test    rsi, rsi
0x1400d494a  jz      short loc_1400D495D
0x1400d494c  xor     edx, edx; Tag
0x1400d494e  mov     rcx, rsi; P
0x1400d4951  call    cs:__imp_ExFreePoolWithTag
0x1400d4958  nop     dword ptr [rax+rax+00h]
0x1400d495d  xor     esi, esi
0x1400d495f  test    ebx, ebx
0x1400d4961  js      loc_1400D4A1C
0x1400d4967  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1400d496b  test    rcx, rcx
0x1400d496e  jz      short loc_1400D49AC
0x1400d4970  lea     r8, [rbp+arg_10]
0x1400d4974  lea     rdx, [rbp+arg_8]
0x1400d4978  call    SeUtilSecurityInfoFromSecurityDescriptor
0x1400d497d  mov     ebx, eax
0x1400d497f  test    eax, eax
0x1400d4981  js      loc_1400D4A1C
0x1400d4987  cmp     [rbp+arg_8], sil
0x1400d498b  jz      short loc_1400D49A1
0x1400d498d  mov     rcx, [rbp+SecurityDescriptor]; P
0x1400d4991  xor     edx, edx; Tag
0x1400d4993  call    cs:__imp_ExFreePoolWithTag
0x1400d499a  nop     dword ptr [rax+rax+00h]
0x1400d499f  jmp     short loc_1400D49AC
0x1400d49a1  mov     rax, [rbp+SecurityDescriptor]
0x1400d49a5  or      dword ptr [rdi], 2
0x1400d49a8  mov     [rdi+8], rax
0x1400d49ac  mov     r9, r13
0x1400d49af  lea     rdx, aDevicetype; "DeviceType"
0x1400d49b6  mov     rcx, r14
0x1400d49b9  call    CmRegUtilWstrValueGetDword
0x1400d49be  mov     ebx, eax
0x1400d49c0  test    eax, eax
0x1400d49c2  js      short loc_1400D49C9
0x1400d49c4  or      dword ptr [rdi], 1
0x1400d49c7  jmp     short loc_1400D49D0
0x1400d49c9  cmp     eax, 0C0000034h
0x1400d49ce  jnz     short loc_1400D4A1C
0x1400d49d0  mov     r9, r15
0x1400d49d3  lea     rdx, aDevicecharacte; "DeviceCharacteristics"
0x1400d49da  mov     rcx, r14
0x1400d49dd  call    CmRegUtilWstrValueGetDword
0x1400d49e2  mov     ebx, eax
0x1400d49e4  test    eax, eax
0x1400d49e6  js      short loc_1400D49ED
0x1400d49e8  or      dword ptr [rdi], 4
0x1400d49eb  jmp     short loc_1400D49F4
0x1400d49ed  cmp     eax, 0C0000034h
0x1400d49f2  jnz     short loc_1400D4A1C
0x1400d49f4  mov     r9, r12
0x1400d49f7  lea     rdx, aExclusive; "Exclusive"
0x1400d49fe  mov     rcx, r14
0x1400d4a01  call    CmRegUtilWstrValueGetDword
0x1400d4a06  mov     ebx, eax
0x1400d4a08  test    eax, eax
0x1400d4a0a  js      short loc_1400D4A11
0x1400d4a0c  or      dword ptr [rdi], 8
0x1400d4a0f  jmp     short loc_1400D4A44
0x1400d4a11  cmp     eax, 0C0000034h
0x1400d4a16  jnz     short loc_1400D4A1C
0x1400d4a18  mov     ebx, esi
0x1400d4a1a  jmp     short loc_1400D4A44
0x1400d4a1c  mov     rcx, [rdi+8]; P
0x1400d4a20  test    rcx, rcx
0x1400d4a23  jz      short loc_1400D4A33
0x1400d4a25  xor     edx, edx; Tag
0x1400d4a27  call    cs:__imp_ExFreePoolWithTag
0x1400d4a2e  nop     dword ptr [rax+rax+00h]
0x1400d4a33  mov     [rdi], esi
0x1400d4a35  mov     [rdi+8], rsi
0x1400d4a39  mov     [r13+0], esi
0x1400d4a3d  mov     [r15], esi
0x1400d4a40  mov     [r12], esi
0x1400d4a44  mov     eax, ebx
0x1400d4a46  mov     rbx, [rsp+50h+arg_0]
0x1400d4a4e  add     rsp, 50h
0x1400d4a52  pop     r15
0x1400d4a54  pop     r14
0x1400d4a56  pop     r13
0x1400d4a58  pop     r12
0x1400d4a5a  pop     rdi
0x1400d4a5b  pop     rsi
0x1400d4a5c  pop     rbp
0x1400d4a5d  retn
```
