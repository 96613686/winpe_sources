# TdipGetMultiSZList

- ea: `0x140002240`
- end: `0x14000257b`
- name: `TdipGetMultiSZList`
- size: `827`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140002200`
- `0x1400032e0`

## callees

- `0x140002240`
- `0x1400054b0`
- `0x140005600`
- `0x140005900`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400023b1`
- `ntoskrnl!ExAllocatePool2` at `0x140002472`
- `ntoskrnl!ExAllocatePool2` at `0x1400023b1`
- `ntoskrnl!ExAllocatePool2` at `0x140002472`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400022e4`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400022e4`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400022d0`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400022fc`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400022d0`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400022fc`
- `ntoskrnl!RtlInitUnicodeString` at `0x140002314`
- `ntoskrnl!RtlInitUnicodeString` at `0x140002314`
- `ntoskrnl!ZwQueryValueKey` at `0x14000238b`
- `ntoskrnl!ZwQueryValueKey` at `0x1400023ee`
- `ntoskrnl!ZwQueryValueKey` at `0x14000238b`
- `ntoskrnl!ZwQueryValueKey` at `0x1400023ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400024a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400024f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400024a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400024f5`
- `ntoskrnl!ZwClose` at `0x140002401`
- `ntoskrnl!ZwClose` at `0x14000255b`
- `ntoskrnl!ZwClose` at `0x140002401`
- `ntoskrnl!ZwClose` at `0x14000255b`
- `ntoskrnl!ZwOpenKey` at `0x140002356`
- `ntoskrnl!ZwOpenKey` at `0x140002356`

## string_xrefs

- `0x1400022f0`: `\Linkage`
- `0x1400022bf`: `\Registry\Machine\System\CurrentControlSet\Services\`

## pseudocode

```c
void __fastcall TdipGetMultiSZList(
        _QWORD *a1,
        __int64 a2,
        const UNICODE_STRING *a3,
        __int64 a4,
        __int64 a5,
        unsigned int *a6)
{
  unsigned int *Pool2; // rax
  void *v9; // rcx
  unsigned int *v10; // rsi
  NTSTATUS v11; // ebx
  __int64 v12; // r9
  unsigned int v13; // ebx
  __int16 *v14; // r14
  unsigned int v15; // r8d
  __int16 *v16; // rdx
  __int16 v17; // cx
  __int64 v18; // rax
  __int64 v19; // rdi
  __int64 v20; // rax
  _QWORD *v21; // r15
  _WORD *v22; // rdi
  _QWORD *v23; // rdx
  ULONG v24; // r9d
  _WORD *v25; // rax
  unsigned int i; // r8d
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  _UNICODE_STRING Destination; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-B0h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v33[512]; // [rsp+90h] [rbp-70h] BYREF

  *(_QWORD *)&Destination.Length = 0x1000000;
  KeyHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  memset(v33, 0, sizeof(v33));
  ResultLength = 0;
  Destination.Buffer = (PWSTR)v33;
  RtlAppendUnicodeToString(&Destination, L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\");
  RtlAppendUnicodeStringToString(&Destination, a3);
  RtlAppendUnicodeToString(&Destination, L"\\Linkage");
  RtlInitUnicodeString(&DestinationString, L"Bind");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &Destination;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes) < 0 )
    goto LABEL_15;
  if ( ZwQueryValueKey(KeyHandle, &DestinationString, KeyValueFullInformation, 0, 0, &ResultLength) != -1073741789 )
  {
    v9 = KeyHandle;
    goto LABEL_22;
  }
  Pool2 = (unsigned int *)ExAllocatePool2(64, ResultLength, 1783186516);
  v9 = KeyHandle;
  v10 = Pool2;
  if ( !Pool2 )
  {
LABEL_22:
    ZwClose(v9);
    *a1 = 0;
    *a6 = 0;
    return;
  }
  v11 = ZwQueryValueKey(KeyHandle, &DestinationString, KeyValueFullInformation, Pool2, ResultLength, &ResultLength);
  ZwClose(KeyHandle);
  if ( v11 < 0 )
    goto LABEL_14;
  v12 = v10[3];
  ResultLength = v12;
  if ( (unsigned int)v12 <= 2 )
    goto LABEL_14;
  v13 = 0;
  v14 = (__int16 *)((char *)v10 + v10[2]);
  v15 = 0;
  v16 = v14;
  do
  {
    v17 = *v16;
    v18 = v13 + 1;
    ++v16;
    if ( v17 )
      v18 = v13;
    v15 += 2;
    v13 = v18;
  }
  while ( v15 < (unsigned int)v12 );
  v19 = 8 * v18;
  v20 = ExAllocatePool2(64, 8 * v18 + v12, 1799963732);
  v21 = (_QWORD *)v20;
  if ( !v20 )
  {
LABEL_14:
    ExFreePoolWithTag(v10, 0);
LABEL_15:
    *a1 = 0;
    *a6 = 0;
    return;
  }
  v22 = (_WORD *)(v20 + v19);
  memmove(v22, v14, ResultLength);
  ExFreePoolWithTag(v10, 0);
  if ( v13 > 1 )
  {
    *v21 = v22;
    v23 = v21 + 1;
    v24 = ResultLength;
    v25 = v22 + 1;
    for ( i = 6; i < v24; i += 2 )
    {
      if ( !*v25++ )
      {
        *v23++ = v25;
        v24 = ResultLength;
      }
    }
  }
  else
  {
    v23 = v21;
  }
  *v23 = 0;
  *a1 = v21;
  *a6 = v13;
}

```

## disassembly

```asm
0x140002240  mov     [rsp-8+arg_8], rbx
0x140002245  push    rbp
0x140002246  push    rsi
0x140002247  push    rdi
0x140002248  push    r12
0x14000224a  push    r13
0x14000224c  push    r14
0x14000224e  push    r15
0x140002250  lea     rbp, [rsp-1A0h]
0x140002258  sub     rsp, 2A0h
0x14000225f  mov     rax, cs:__security_cookie
0x140002266  xor     rax, rsp
0x140002269  mov     [rbp+1D0h+var_40], rax
0x140002270  mov     r13, [rbp+1D0h+arg_28]
0x140002277  xorps   xmm0, xmm0
0x14000227a  mov     rbx, r8
0x14000227d  mov     qword ptr [rsp+2D0h+Destination.Length], 1000000h
0x140002286  mov     r12, rcx
0x140002289  xor     edi, edi
0x14000228b  movups  xmmword ptr [rsp+2D0h+ObjectAttributes.ObjectName], xmm0
0x140002290  xor     eax, eax
0x140002292  mov     [rsp+2D0h+KeyHandle], rdi
0x140002297  xor     edx, edx; Val
0x140002299  lea     rcx, [rbp+1D0h+var_240]; void *
0x14000229d  mov     r8d, 200h; Size
0x1400022a3  movups  xmmword ptr [rsp+2D0h+ObjectAttributes+1Ch], xmm0
0x1400022a8  movups  xmmword ptr [rsp+2D0h+DestinationString.Length], xmm0
0x1400022ad  movups  xmmword ptr [rsp+2D0h+ObjectAttributes.Length], xmm0
0x1400022b2  call    memset
0x1400022b7  lea     rax, [rbp+1D0h+var_240]
0x1400022bb  mov     [rsp+2D0h+var_2A0], edi
0x1400022bf  lea     rdx, Source; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400022c6  mov     [rsp+2D0h+Destination.Buffer], rax
0x1400022cb  lea     rcx, [rsp+2D0h+Destination]; Destination
0x1400022d0  call    cs:__imp_RtlAppendUnicodeToString
0x1400022d7  nop     dword ptr [rax+rax+00h]
0x1400022dc  mov     rdx, rbx; Source
0x1400022df  lea     rcx, [rsp+2D0h+Destination]; Destination
0x1400022e4  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400022eb  nop     dword ptr [rax+rax+00h]
0x1400022f0  lea     rdx, aLinkage; "\\Linkage"
0x1400022f7  lea     rcx, [rsp+2D0h+Destination]; Destination
0x1400022fc  call    cs:__imp_RtlAppendUnicodeToString
0x140002303  nop     dword ptr [rax+rax+00h]
0x140002308  lea     rdx, SourceString; "Bind"
0x14000230f  lea     rcx, [rsp+2D0h+DestinationString]; DestinationString
0x140002314  call    cs:__imp_RtlInitUnicodeString
0x14000231b  nop     dword ptr [rax+rax+00h]
0x140002320  lea     rax, [rsp+2D0h+Destination]
0x140002325  mov     [rsp+2D0h+ObjectAttributes.Length], 30h ; '0'
0x14000232d  xorps   xmm0, xmm0
0x140002330  mov     [rsp+2D0h+ObjectAttributes.ObjectName], rax
0x140002335  lea     r8, [rsp+2D0h+ObjectAttributes]; ObjectAttributes
0x14000233a  mov     [rsp+2D0h+ObjectAttributes.RootDirectory], rdi
0x14000233f  mov     edx, 1; DesiredAccess
0x140002344  mov     [rsp+2D0h+ObjectAttributes.Attributes], 240h
0x14000234c  lea     rcx, [rsp+2D0h+KeyHandle]; KeyHandle
0x140002351  movdqu  xmmword ptr [rbp+1D0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140002356  call    cs:__imp_ZwOpenKey
0x14000235d  nop     dword ptr [rax+rax+00h]
0x140002362  test    eax, eax
0x140002364  js      loc_140002501
0x14000236a  mov     rcx, [rsp+2D0h+KeyHandle]; KeyHandle
0x14000236f  lea     rax, [rsp+2D0h+var_2A0]
0x140002374  mov     [rsp+2D0h+ResultLength], rax; ResultLength
0x140002379  lea     rdx, [rsp+2D0h+DestinationString]; ValueName
0x14000237e  xor     r9d, r9d; KeyValueInformation
0x140002381  mov     [rsp+2D0h+Length], edi; Length
0x140002385  mov     r8d, 1; KeyValueInformationClass
0x14000238b  call    cs:__imp_ZwQueryValueKey
0x140002392  nop     dword ptr [rax+rax+00h]
0x140002397  cmp     eax, 0C0000023h
0x14000239c  jnz     loc_140002556
0x1400023a2  mov     edx, [rsp+2D0h+var_2A0]
0x1400023a6  mov     ecx, 40h ; '@'
0x1400023ab  mov     r8d, 6A494454h
0x1400023b1  call    cs:__imp_ExAllocatePool2
0x1400023b8  nop     dword ptr [rax+rax+00h]
0x1400023bd  mov     rcx, [rsp+2D0h+KeyHandle]; KeyHandle
0x1400023c2  mov     rsi, rax
0x1400023c5  test    rax, rax
0x1400023c8  jz      loc_14000255B
0x1400023ce  lea     rax, [rsp+2D0h+var_2A0]
0x1400023d3  mov     r9, rsi; KeyValueInformation
0x1400023d6  mov     [rsp+2D0h+ResultLength], rax; ResultLength
0x1400023db  lea     rdx, [rsp+2D0h+DestinationString]; ValueName
0x1400023e0  mov     eax, [rsp+2D0h+var_2A0]
0x1400023e4  mov     r8d, 1; KeyValueInformationClass
0x1400023ea  mov     [rsp+2D0h+Length], eax; Length
0x1400023ee  call    cs:__imp_ZwQueryValueKey
0x1400023f5  nop     dword ptr [rax+rax+00h]
0x1400023fa  mov     rcx, [rsp+2D0h+KeyHandle]; Handle
0x1400023ff  mov     ebx, eax
0x140002401  call    cs:__imp_ZwClose
0x140002408  nop     dword ptr [rax+rax+00h]
0x14000240d  test    ebx, ebx
0x14000240f  js      loc_1400024F0
0x140002415  mov     r9d, [rsi+0Ch]
0x140002419  mov     [rsp+2D0h+var_2A0], r9d
0x14000241e  cmp     r9d, 2
0x140002422  jbe     loc_1400024F0
0x140002428  mov     r14d, [rsi+8]
0x14000242c  mov     ebx, edi
0x14000242e  add     r14, rsi
0x140002431  mov     r8d, edi
0x140002434  mov     rdx, r14
0x140002437  nop     word ptr [rax+rax+00000000h]
0x140002440  movzx   ecx, word ptr [rdx]
0x140002443  lea     eax, [rbx+1]
0x140002446  test    cx, cx
0x140002449  lea     rdx, [rdx+2]
0x14000244d  cmovnz  eax, ebx
0x140002450  add     r8d, 2
0x140002454  mov     ebx, eax
0x140002456  cmp     r8d, r9d
0x140002459  jb      short loc_140002440
0x14000245b  lea     rdi, ds:0[rax*8]
0x140002463  mov     ecx, 40h ; '@'
0x140002468  lea     rdx, [rdi+r9]
0x14000246c  mov     r8d, 6B494454h
0x140002472  call    cs:__imp_ExAllocatePool2
0x140002479  nop     dword ptr [rax+rax+00h]
0x14000247e  mov     r15, rax
0x140002481  test    rax, rax
0x140002484  jz      loc_140002574
0x14000248a  mov     r8d, [rsp+2D0h+var_2A0]; Size
0x14000248f  add     rdi, rax
0x140002492  mov     rcx, rdi; void *
0x140002495  mov     rdx, r14; Src
0x140002498  call    memmove
0x14000249d  xor     edx, edx; Tag
0x14000249f  mov     rcx, rsi; P
0x1400024a2  call    cs:__imp_ExFreePoolWithTag
0x1400024a9  nop     dword ptr [rax+rax+00h]
0x1400024ae  cmp     ebx, 1
0x1400024b1  ja      short loc_14000250B
0x1400024b3  mov     rdx, r15
0x1400024b6  mov     qword ptr [rdx], 0
0x1400024bd  mov     [r12], r15
0x1400024c1  mov     [r13+0], ebx
0x1400024c5  mov     rcx, [rbp+1D0h+var_40]
0x1400024cc  xor     rcx, rsp; StackCookie
0x1400024cf  call    __security_check_cookie
0x1400024d4  mov     rbx, [rsp+2D0h+arg_8]
0x1400024dc  add     rsp, 2A0h
0x1400024e3  pop     r15
0x1400024e5  pop     r14
0x1400024e7  pop     r13
0x1400024e9  pop     r12
0x1400024eb  pop     rdi
0x1400024ec  pop     rsi
0x1400024ed  pop     rbp
0x1400024ee  retn
0x1400024f0  xor     edx, edx; Tag
0x1400024f2  mov     rcx, rsi; P
0x1400024f5  call    cs:__imp_ExFreePoolWithTag
0x1400024fc  nop     dword ptr [rax+rax+00h]
0x140002501  mov     [r12], rdi
0x140002505  mov     [r13+0], edi
0x140002509  jmp     short loc_1400024C5
0x14000250b  mov     [r15], rdi
0x14000250e  lea     rdx, [r15+8]
0x140002512  mov     r9d, [rsp+2D0h+var_2A0]
0x140002517  lea     rax, [rdi+2]
0x14000251b  mov     r8d, 6
0x140002521  cmp     r9d, r8d
0x140002524  jbe     short loc_1400024B6
0x140002526  nop     word ptr [rax+rax+00000000h]
0x140002530  movzx   ecx, word ptr [rax]
0x140002533  add     rax, 2
0x140002537  test    cx, cx
0x14000253a  jnz     short loc_140002548
0x14000253c  mov     [rdx], rax
0x14000253f  add     rdx, 8
0x140002543  mov     r9d, [rsp+2D0h+var_2A0]
0x140002548  add     r8d, 2
0x14000254c  cmp     r8d, r9d
0x14000254f  jb      short loc_140002530
0x140002551  jmp     loc_1400024B6
0x140002556  mov     rcx, [rsp+2D0h+KeyHandle]; Handle
0x14000255b  call    cs:__imp_ZwClose
0x140002562  nop     dword ptr [rax+rax+00h]
0x140002567  mov     [r12], rdi
0x14000256b  mov     [r13+0], edi
0x14000256f  jmp     loc_1400024C5
0x140002574  xor     edi, edi
0x140002576  jmp     loc_1400024F0
```
