# PiRegStateReadStackCreationSettingsFromKey

- ea: `0x14002104c`
- end: `0x14002122b`
- name: `PiRegStateReadStackCreationSettingsFromKey`
- size: `479`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140021234`

## callees

- `0x140007dc4`
- `0x14002104c`
- `0x14002151c`
- `0x14002177c`
- `0x140021a2c`

## import_xrefs

- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1400210f4`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1400210f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002111d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002115f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400211f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002111d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002115f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400211f3`

## string_xrefs

- `0x14002108e`: `Security`

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
0x14002104c  mov     [rsp-38h+arg_0], rbx
0x140021051  push    rbp
0x140021052  push    rsi
0x140021053  push    rdi
0x140021054  push    r12
0x140021056  push    r13
0x140021058  push    r14
0x14002105a  push    r15
0x14002105c  mov     rbp, rsp
0x14002105f  sub     rsp, 50h
0x140021063  xor     r10d, r10d
0x140021066  lea     r13, [rdx+4]
0x14002106a  lea     r15, [rdx+10h]
0x14002106e  mov     [rdx], r10d
0x140021071  lea     r12, [rdx+14h]
0x140021075  mov     [rdx+8], r10
0x140021079  mov     rdi, rdx
0x14002107c  mov     [rbp+SecurityDescriptor], r10
0x140021080  mov     r14, rcx
0x140021083  mov     [rbp+arg_10], r10d
0x140021087  xorps   xmm0, xmm0
0x14002108a  mov     [rbp+arg_8], r10b
0x14002108e  lea     rdx, aSecurity; "Security"
0x140021095  mov     [rbp+P], r10
0x140021099  lea     rcx, [rbp+DestinationString]; DestinationString
0x14002109d  mov     [r13+0], r10d
0x1400210a1  mov     esi, r10d
0x1400210a4  mov     [r15], r10d
0x1400210a7  mov     [r12], r10d
0x1400210ab  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400210af  call    WdmlibRtlInitUnicodeStringEx
0x1400210b4  mov     ebx, eax
0x1400210b6  test    eax, eax
0x1400210b8  js      short loc_140021104
0x1400210ba  lea     rax, [rbp+P]
0x1400210be  mov     rcx, r14; KeyHandle
0x1400210c1  lea     rdx, [rbp+DestinationString]; ValueName
0x1400210c5  mov     [rsp+50h+var_30], rax; __int64
0x1400210ca  call    CmRegUtilUcValueGetFullBuffer
0x1400210cf  mov     rsi, [rbp+P]
0x1400210d3  xor     r10d, r10d
0x1400210d6  mov     ebx, eax
0x1400210d8  test    eax, eax
0x1400210da  js      short loc_140021104
0x1400210dc  mov     ecx, [rsi+8]
0x1400210df  lea     rax, [rbp+SecurityDescriptor]
0x1400210e3  add     rcx, rsi
0x1400210e6  mov     [rsp+50h+var_30], rax
0x1400210eb  mov     r9b, 1
0x1400210ee  lea     r8d, [r10+1]
0x1400210f2  xor     edx, edx
0x1400210f4  call    cs:__imp_SeCaptureSecurityDescriptor
0x1400210fb  nop     dword ptr [rax+rax+00h]
0x140021100  mov     ebx, eax
0x140021102  jmp     short loc_140021113
0x140021104  cmp     ebx, 0C0000034h
0x14002110a  jnz     short loc_140021113
0x14002110c  mov     [rbp+SecurityDescriptor], r10
0x140021110  mov     ebx, r10d
0x140021113  test    rsi, rsi
0x140021116  jz      short loc_140021129
0x140021118  xor     edx, edx; Tag
0x14002111a  mov     rcx, rsi; P
0x14002111d  call    cs:__imp_ExFreePoolWithTag
0x140021124  nop     dword ptr [rax+rax+00h]
0x140021129  xor     esi, esi
0x14002112b  test    ebx, ebx
0x14002112d  js      loc_1400211E8
0x140021133  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140021137  test    rcx, rcx
0x14002113a  jz      short loc_140021178
0x14002113c  lea     r8, [rbp+arg_10]
0x140021140  lea     rdx, [rbp+arg_8]
0x140021144  call    SeUtilSecurityInfoFromSecurityDescriptor
0x140021149  mov     ebx, eax
0x14002114b  test    eax, eax
0x14002114d  js      loc_1400211E8
0x140021153  cmp     [rbp+arg_8], sil
0x140021157  jz      short loc_14002116D
0x140021159  mov     rcx, [rbp+SecurityDescriptor]; P
0x14002115d  xor     edx, edx; Tag
0x14002115f  call    cs:__imp_ExFreePoolWithTag
0x140021166  nop     dword ptr [rax+rax+00h]
0x14002116b  jmp     short loc_140021178
0x14002116d  mov     rax, [rbp+SecurityDescriptor]
0x140021171  or      dword ptr [rdi], 2
0x140021174  mov     [rdi+8], rax
0x140021178  mov     r9, r13
0x14002117b  lea     rdx, aDevicetype; "DeviceType"
0x140021182  mov     rcx, r14
0x140021185  call    CmRegUtilWstrValueGetDword
0x14002118a  mov     ebx, eax
0x14002118c  test    eax, eax
0x14002118e  js      short loc_140021195
0x140021190  or      dword ptr [rdi], 1
0x140021193  jmp     short loc_14002119C
0x140021195  cmp     eax, 0C0000034h
0x14002119a  jnz     short loc_1400211E8
0x14002119c  mov     r9, r15
0x14002119f  lea     rdx, aDevicecharacte; "DeviceCharacteristics"
0x1400211a6  mov     rcx, r14
0x1400211a9  call    CmRegUtilWstrValueGetDword
0x1400211ae  mov     ebx, eax
0x1400211b0  test    eax, eax
0x1400211b2  js      short loc_1400211B9
0x1400211b4  or      dword ptr [rdi], 4
0x1400211b7  jmp     short loc_1400211C0
0x1400211b9  cmp     eax, 0C0000034h
0x1400211be  jnz     short loc_1400211E8
0x1400211c0  mov     r9, r12
0x1400211c3  lea     rdx, aExclusive; "Exclusive"
0x1400211ca  mov     rcx, r14
0x1400211cd  call    CmRegUtilWstrValueGetDword
0x1400211d2  mov     ebx, eax
0x1400211d4  test    eax, eax
0x1400211d6  js      short loc_1400211DD
0x1400211d8  or      dword ptr [rdi], 8
0x1400211db  jmp     short loc_140021210
0x1400211dd  cmp     eax, 0C0000034h
0x1400211e2  jnz     short loc_1400211E8
0x1400211e4  mov     ebx, esi
0x1400211e6  jmp     short loc_140021210
0x1400211e8  mov     rcx, [rdi+8]; P
0x1400211ec  test    rcx, rcx
0x1400211ef  jz      short loc_1400211FF
0x1400211f1  xor     edx, edx; Tag
0x1400211f3  call    cs:__imp_ExFreePoolWithTag
0x1400211fa  nop     dword ptr [rax+rax+00h]
0x1400211ff  mov     [rdi], esi
0x140021201  mov     [rdi+8], rsi
0x140021205  mov     [r13+0], esi
0x140021209  mov     [r15], esi
0x14002120c  mov     [r12], esi
0x140021210  mov     eax, ebx
0x140021212  mov     rbx, [rsp+50h+arg_0]
0x14002121a  add     rsp, 50h
0x14002121e  pop     r15
0x140021220  pop     r14
0x140021222  pop     r13
0x140021224  pop     r12
0x140021226  pop     rdi
0x140021227  pop     rsi
0x140021228  pop     rbp
0x140021229  retn
```
