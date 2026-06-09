# VmsCsPvtReadComputerName

- ea: `0x1400a7734`
- end: `0x1400a79fe`
- name: `VmsCsPvtReadComputerName`
- size: `714`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1400a6fd4`

## callees

- `0x14003a450`
- `0x140046f1c`
- `0x1400a7734`
- `0x1400a839c`
- `0x1400a8740`
- `0x1401bc040`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x1400a7837`
- `ntoskrnl!ZwQueryValueKey` at `0x1400a78fe`
- `ntoskrnl!ZwQueryValueKey` at `0x1400a7837`
- `ntoskrnl!ZwQueryValueKey` at `0x1400a78fe`
- `ntoskrnl!ZwOpenKey` at `0x1400a77b5`
- `ntoskrnl!ZwOpenKey` at `0x1400a77b5`
- `ntoskrnl!ZwClose` at `0x1400a79dc`
- `ntoskrnl!ZwClose` at `0x1400a79dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a79c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a79c7`
- `ntoskrnl!ExAllocatePool2` at `0x1400a789d`
- `ntoskrnl!ExAllocatePool2` at `0x1400a7952`
- `ntoskrnl!ExAllocatePool2` at `0x1400a789d`
- `ntoskrnl!ExAllocatePool2` at `0x1400a7952`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a7776`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a7808`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a7776`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a7808`

## string_xrefs

- `0x1400a77fd`: `ComputerName`
- `0x1400a774d`: `\Registry\Machine\System\CurrentControlSet\Control\ComputerName\ComputerName`

## pseudocode

```c
void VmsCsPvtReadComputerName()
{
  NTSTATUS v0; // eax
  NTSTATUS v1; // eax
  int v2; // edx
  int v3; // edx
  unsigned int *Pool2; // rbx
  NTSTATUS v5; // eax
  int v6; // edx
  int v7; // ecx
  int v8; // r8d
  int v9; // edx
  int Length; // [rsp+20h] [rbp-19h]
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp+17h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+27h] BYREF
  ULONG ResultLength; // [rsp+A0h] [rbp+67h] BYREF
  void *KeyHandle; // [rsp+A8h] [rbp+6Fh] BYREF

  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.Buffer = 0;
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  ResultLength = 0;
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\ComputerName\\ComputerName");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v0 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v0 )
  {
    WPP_RECORDER_SF_id(
      VmsIfrLog,
      2,
      20,
      62,
      (__int64)WPP_3a8656c1e584334fc686337230dfbb9f_Traceguids,
      (char)&ObjectAttributes,
      v0);
  }
  else
  {
    RtlInitUnicodeString(&DestinationString, L"ComputerName");
    v1 = ZwQueryValueKey(KeyHandle, &DestinationString, KeyValuePartialInformation, 0, 0, &ResultLength);
    if ( v1 == -1073741789 || v1 == -1073741772 )
    {
      Pool2 = (unsigned int *)ExAllocatePool2(64, ResultLength, 1933800278);
      if ( Pool2 )
      {
        v5 = ZwQueryValueKey(
               KeyHandle,
               &DestinationString,
               KeyValuePartialInformation,
               Pool2,
               ResultLength,
               &ResultLength);
        if ( !v5 || v5 == -1073741772 )
        {
          qword_1401FA150 = (PVOID)ExAllocatePool2(64, Pool2[2], 1933800278);
          if ( qword_1401FA150 )
          {
            word_1401FA14A = *((_WORD *)Pool2 + 4);
            VmsCsComputerName = word_1401FA14A - 2;
            memmove(qword_1401FA150, Pool2 + 3, (unsigned __int16)(word_1401FA14A - 2));
          }
          else
          {
            LOBYTE(v9) = 2;
            WPP_RECORDER_SF_d(VmsIfrLog, v9, 20, 66, (__int64)WPP_3a8656c1e584334fc686337230dfbb9f_Traceguids, Pool2[2]);
          }
        }
        else
        {
          WPP_RECORDER_SF_qZqDd(
            v7,
            v6,
            v8,
            65,
            Length,
            (char)KeyHandle,
            (__int64)&DestinationString,
            (char)Pool2,
            ResultLength,
            v5);
        }
        ExFreePoolWithTag(Pool2, 0);
      }
      else
      {
        LOBYTE(v3) = 2;
        WPP_RECORDER_SF_d(VmsIfrLog, v3, 20, 64, (__int64)WPP_3a8656c1e584334fc686337230dfbb9f_Traceguids, ResultLength);
      }
    }
    else
    {
      LOBYTE(v2) = 2;
      WPP_RECORDER_SF_qZd(
        VmsIfrLog,
        v2,
        20,
        63,
        (__int64)WPP_3a8656c1e584334fc686337230dfbb9f_Traceguids,
        (char)KeyHandle,
        (__int64)&DestinationString,
        v1);
    }
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
}

```

## disassembly

```asm
0x1400a7734  mov     [rsp-8+arg_10], rbx
0x1400a7739  mov     [rsp-8+arg_18], rdi
0x1400a773e  push    rbp
0x1400a773f  lea     rbp, [rsp-57h]
0x1400a7744  sub     rsp, 90h
0x1400a774b  xor     eax, eax
0x1400a774d  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400a7754  xorps   xmm0, xmm0
0x1400a7757  mov     qword ptr [rbp+57h+DestinationString.Length], rax
0x1400a775b  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1400a775f  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400a7763  mov     [rbp+57h+DestinationString.Buffer], rax
0x1400a7767  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1400a776b  mov     [rbp+57h+KeyHandle], rax
0x1400a776f  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1400a7773  mov     [rbp+57h+arg_0], eax
0x1400a7776  call    cs:__imp_RtlInitUnicodeString
0x1400a777d  nop     dword ptr [rax+rax+00h]
0x1400a7782  lea     rax, [rbp+57h+DestinationString]
0x1400a7786  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400a778d  xorps   xmm0, xmm0
0x1400a7790  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400a7794  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400a7798  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1400a77a0  mov     edx, 20019h; DesiredAccess
0x1400a77a5  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1400a77ac  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400a77b0  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400a77b5  call    cs:__imp_ZwOpenKey
0x1400a77bc  nop     dword ptr [rax+rax+00h]
0x1400a77c1  test    eax, eax
0x1400a77c3  jz      short loc_1400A77FD
0x1400a77c5  mov     rcx, cs:VmsIfrLog
0x1400a77cc  mov     r9d, 3Eh ; '>'
0x1400a77d2  mov     dword ptr [rsp+90h+var_60], eax
0x1400a77d6  lea     rax, [rbp+57h+ObjectAttributes]
0x1400a77da  mov     [rsp+90h+ResultLength], rax
0x1400a77df  lea     rax, WPP_3a8656c1e584334fc686337230dfbb9f_Traceguids
0x1400a77e6  mov     qword ptr [rsp+90h+Length], rax
0x1400a77eb  lea     edx, [r9-3Ch]
0x1400a77ef  lea     r8d, [r9-2Ah]
0x1400a77f3  call    WPP_RECORDER_SF_id
0x1400a77f8  jmp     loc_1400A79D3
0x1400a77fd  lea     rdx, aComputername; "ComputerName"
0x1400a7804  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400a7808  call    cs:__imp_RtlInitUnicodeString
0x1400a780f  nop     dword ptr [rax+rax+00h]
0x1400a7814  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400a7818  lea     rax, [rbp+57h+arg_0]
0x1400a781c  xor     r9d, r9d; KeyValueInformation
0x1400a781f  mov     [rsp+90h+ResultLength], rax; ResultLength
0x1400a7824  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x1400a7828  mov     [rsp+90h+Length], 0; Length
0x1400a7830  lea     edi, [r9+2]
0x1400a7834  mov     r8d, edi; KeyValueInformationClass
0x1400a7837  call    cs:__imp_ZwQueryValueKey
0x1400a783e  nop     dword ptr [rax+rax+00h]
0x1400a7843  cmp     eax, 0C0000023h
0x1400a7848  jz      short loc_1400A788F
0x1400a784a  cmp     eax, 0C0000034h
0x1400a784f  jz      short loc_1400A788F
0x1400a7851  mov     rcx, cs:VmsIfrLog
0x1400a7858  lea     r9d, [rdi+3Dh]
0x1400a785c  mov     dword ptr [rsp+90h+var_58], eax
0x1400a7860  lea     r8d, [rdi+12h]
0x1400a7864  lea     rax, [rbp+57h+DestinationString]
0x1400a7868  mov     dl, dil
0x1400a786b  mov     [rsp+90h+var_60], rax
0x1400a7870  mov     rax, [rbp+57h+KeyHandle]
0x1400a7874  mov     [rsp+90h+ResultLength], rax
0x1400a7879  lea     rax, WPP_3a8656c1e584334fc686337230dfbb9f_Traceguids
0x1400a7880  mov     qword ptr [rsp+90h+Length], rax
0x1400a7885  call    WPP_RECORDER_SF_qZd
0x1400a788a  jmp     loc_1400A79D3
0x1400a788f  mov     edx, [rbp+57h+arg_0]
0x1400a7892  mov     ecx, 40h ; '@'
0x1400a7897  mov     r8d, 73437356h
0x1400a789d  call    cs:__imp_ExAllocatePool2
0x1400a78a4  nop     dword ptr [rax+rax+00h]
0x1400a78a9  mov     rbx, rax
0x1400a78ac  test    rax, rax
0x1400a78af  jnz     short loc_1400A78E0
0x1400a78b1  mov     rcx, cs:VmsIfrLog
0x1400a78b8  lea     r9d, [rax+40h]
0x1400a78bc  mov     eax, [rbp+57h+arg_0]
0x1400a78bf  lea     r8d, [rbx+14h]
0x1400a78c3  mov     dword ptr [rsp+90h+ResultLength], eax
0x1400a78c7  mov     dl, dil
0x1400a78ca  lea     rax, WPP_3a8656c1e584334fc686337230dfbb9f_Traceguids
0x1400a78d1  mov     qword ptr [rsp+90h+Length], rax
0x1400a78d6  call    WPP_RECORDER_SF_d
0x1400a78db  jmp     loc_1400A79D3
0x1400a78e0  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400a78e4  lea     rax, [rbp+57h+arg_0]
0x1400a78e8  mov     [rsp+90h+ResultLength], rax; ResultLength
0x1400a78ed  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x1400a78f1  mov     eax, [rbp+57h+arg_0]
0x1400a78f4  mov     r9, rbx; KeyValueInformation
0x1400a78f7  mov     r8d, edi; KeyValueInformationClass
0x1400a78fa  mov     [rsp+90h+Length], eax; Length
0x1400a78fe  call    cs:__imp_ZwQueryValueKey
0x1400a7905  nop     dword ptr [rax+rax+00h]
0x1400a790a  test    eax, eax
0x1400a790c  jz      short loc_1400A7944
0x1400a790e  cmp     eax, 0C0000034h
0x1400a7913  jz      short loc_1400A7944
0x1400a7915  mov     [rsp+90h+var_48], eax
0x1400a7919  mov     r9d, 41h ; 'A'
0x1400a791f  mov     eax, [rbp+57h+arg_0]
0x1400a7922  mov     [rsp+90h+var_50], eax
0x1400a7926  lea     rax, [rbp+57h+DestinationString]
0x1400a792a  mov     [rsp+90h+var_58], rbx
0x1400a792f  mov     [rsp+90h+var_60], rax
0x1400a7934  mov     rax, [rbp+57h+KeyHandle]
0x1400a7938  mov     [rsp+90h+ResultLength], rax
0x1400a793d  call    WPP_RECORDER_SF_qZqDd
0x1400a7942  jmp     short loc_1400A79C2
0x1400a7944  mov     edx, [rbx+8]
0x1400a7947  mov     ecx, 40h ; '@'
0x1400a794c  mov     r8d, 73437356h
0x1400a7952  call    cs:__imp_ExAllocatePool2
0x1400a7959  nop     dword ptr [rax+rax+00h]
0x1400a795e  mov     cs:qword_1401FA150, rax
0x1400a7965  mov     r9, rax
0x1400a7968  test    rax, rax
0x1400a796b  jnz     short loc_1400A7999
0x1400a796d  mov     rcx, cs:VmsIfrLog
0x1400a7974  lea     r9d, [rax+42h]
0x1400a7978  mov     eax, [rbx+8]
0x1400a797b  lea     r8d, [r9-2Eh]
0x1400a797f  mov     dword ptr [rsp+90h+ResultLength], eax
0x1400a7983  mov     dl, dil
0x1400a7986  lea     rax, WPP_3a8656c1e584334fc686337230dfbb9f_Traceguids
0x1400a798d  mov     qword ptr [rsp+90h+Length], rax
0x1400a7992  call    WPP_RECORDER_SF_d
0x1400a7997  jmp     short loc_1400A79C2
0x1400a7999  movzx   ecx, word ptr [rbx+8]
0x1400a799d  lea     rdx, [rbx+0Ch]; Src
0x1400a79a1  movzx   eax, cx
0x1400a79a4  mov     cs:word_1401FA14A, cx
0x1400a79ab  sub     ax, di
0x1400a79ae  mov     rcx, r9; void *
0x1400a79b1  movzx   r8d, ax; Size
0x1400a79b5  mov     cs:VmsCsComputerName, r8w
0x1400a79bd  call    memmove
0x1400a79c2  xor     edx, edx; Tag
0x1400a79c4  mov     rcx, rbx; P
0x1400a79c7  call    cs:__imp_ExFreePoolWithTag
0x1400a79ce  nop     dword ptr [rax+rax+00h]
0x1400a79d3  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1400a79d7  test    rcx, rcx
0x1400a79da  jz      short loc_1400A79E8
0x1400a79dc  call    cs:__imp_ZwClose
0x1400a79e3  nop     dword ptr [rax+rax+00h]
0x1400a79e8  lea     r11, [rsp+90h+var_s0]
0x1400a79f0  mov     rbx, [r11+20h]
0x1400a79f4  mov     rdi, [r11+28h]
0x1400a79f8  mov     rsp, r11
0x1400a79fb  pop     rbp
0x1400a79fc  retn
```
