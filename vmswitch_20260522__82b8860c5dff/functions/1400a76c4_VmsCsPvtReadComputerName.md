# VmsCsPvtReadComputerName

- ea: `0x1400a76c4`
- end: `0x1400a798e`
- name: `VmsCsPvtReadComputerName`
- size: `714`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1400a6f64`

## callees

- `0x14003a450`
- `0x140046f1c`
- `0x1400a76c4`
- `0x1400a832c`
- `0x1400a86d0`
- `0x1401bbfc0`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x1400a77c7`
- `ntoskrnl!ZwQueryValueKey` at `0x1400a788e`
- `ntoskrnl!ZwQueryValueKey` at `0x1400a77c7`
- `ntoskrnl!ZwQueryValueKey` at `0x1400a788e`
- `ntoskrnl!ZwOpenKey` at `0x1400a7745`
- `ntoskrnl!ZwOpenKey` at `0x1400a7745`
- `ntoskrnl!ZwClose` at `0x1400a796c`
- `ntoskrnl!ZwClose` at `0x1400a796c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a7957`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a7957`
- `ntoskrnl!ExAllocatePool2` at `0x1400a782d`
- `ntoskrnl!ExAllocatePool2` at `0x1400a78e2`
- `ntoskrnl!ExAllocatePool2` at `0x1400a782d`
- `ntoskrnl!ExAllocatePool2` at `0x1400a78e2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a7706`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a7798`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a7706`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400a7798`

## string_xrefs

- `0x1400a778d`: `ComputerName`
- `0x1400a76dd`: `\Registry\Machine\System\CurrentControlSet\Control\ComputerName\ComputerName`

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
0x1400a76c4  mov     [rsp-8+arg_10], rbx
0x1400a76c9  mov     [rsp-8+arg_18], rdi
0x1400a76ce  push    rbp
0x1400a76cf  lea     rbp, [rsp-57h]
0x1400a76d4  sub     rsp, 90h
0x1400a76db  xor     eax, eax
0x1400a76dd  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400a76e4  xorps   xmm0, xmm0
0x1400a76e7  mov     qword ptr [rbp+57h+DestinationString.Length], rax
0x1400a76eb  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1400a76ef  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400a76f3  mov     [rbp+57h+DestinationString.Buffer], rax
0x1400a76f7  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1400a76fb  mov     [rbp+57h+KeyHandle], rax
0x1400a76ff  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1400a7703  mov     [rbp+57h+arg_0], eax
0x1400a7706  call    cs:__imp_RtlInitUnicodeString
0x1400a770d  nop     dword ptr [rax+rax+00h]
0x1400a7712  lea     rax, [rbp+57h+DestinationString]
0x1400a7716  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400a771d  xorps   xmm0, xmm0
0x1400a7720  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400a7724  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400a7728  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1400a7730  mov     edx, 20019h; DesiredAccess
0x1400a7735  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1400a773c  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400a7740  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400a7745  call    cs:__imp_ZwOpenKey
0x1400a774c  nop     dword ptr [rax+rax+00h]
0x1400a7751  test    eax, eax
0x1400a7753  jz      short loc_1400A778D
0x1400a7755  mov     rcx, cs:VmsIfrLog
0x1400a775c  mov     r9d, 3Eh ; '>'
0x1400a7762  mov     dword ptr [rsp+90h+var_60], eax
0x1400a7766  lea     rax, [rbp+57h+ObjectAttributes]
0x1400a776a  mov     [rsp+90h+ResultLength], rax
0x1400a776f  lea     rax, WPP_3a8656c1e584334fc686337230dfbb9f_Traceguids
0x1400a7776  mov     qword ptr [rsp+90h+Length], rax
0x1400a777b  lea     edx, [r9-3Ch]
0x1400a777f  lea     r8d, [r9-2Ah]
0x1400a7783  call    WPP_RECORDER_SF_id
0x1400a7788  jmp     loc_1400A7963
0x1400a778d  lea     rdx, aComputername; "ComputerName"
0x1400a7794  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400a7798  call    cs:__imp_RtlInitUnicodeString
0x1400a779f  nop     dword ptr [rax+rax+00h]
0x1400a77a4  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400a77a8  lea     rax, [rbp+57h+arg_0]
0x1400a77ac  xor     r9d, r9d; KeyValueInformation
0x1400a77af  mov     [rsp+90h+ResultLength], rax; ResultLength
0x1400a77b4  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x1400a77b8  mov     [rsp+90h+Length], 0; Length
0x1400a77c0  lea     edi, [r9+2]
0x1400a77c4  mov     r8d, edi; KeyValueInformationClass
0x1400a77c7  call    cs:__imp_ZwQueryValueKey
0x1400a77ce  nop     dword ptr [rax+rax+00h]
0x1400a77d3  cmp     eax, 0C0000023h
0x1400a77d8  jz      short loc_1400A781F
0x1400a77da  cmp     eax, 0C0000034h
0x1400a77df  jz      short loc_1400A781F
0x1400a77e1  mov     rcx, cs:VmsIfrLog
0x1400a77e8  lea     r9d, [rdi+3Dh]
0x1400a77ec  mov     dword ptr [rsp+90h+var_58], eax
0x1400a77f0  lea     r8d, [rdi+12h]
0x1400a77f4  lea     rax, [rbp+57h+DestinationString]
0x1400a77f8  mov     dl, dil
0x1400a77fb  mov     [rsp+90h+var_60], rax
0x1400a7800  mov     rax, [rbp+57h+KeyHandle]
0x1400a7804  mov     [rsp+90h+ResultLength], rax
0x1400a7809  lea     rax, WPP_3a8656c1e584334fc686337230dfbb9f_Traceguids
0x1400a7810  mov     qword ptr [rsp+90h+Length], rax
0x1400a7815  call    WPP_RECORDER_SF_qZd
0x1400a781a  jmp     loc_1400A7963
0x1400a781f  mov     edx, [rbp+57h+arg_0]
0x1400a7822  mov     ecx, 40h ; '@'
0x1400a7827  mov     r8d, 73437356h
0x1400a782d  call    cs:__imp_ExAllocatePool2
0x1400a7834  nop     dword ptr [rax+rax+00h]
0x1400a7839  mov     rbx, rax
0x1400a783c  test    rax, rax
0x1400a783f  jnz     short loc_1400A7870
0x1400a7841  mov     rcx, cs:VmsIfrLog
0x1400a7848  lea     r9d, [rax+40h]
0x1400a784c  mov     eax, [rbp+57h+arg_0]
0x1400a784f  lea     r8d, [rbx+14h]
0x1400a7853  mov     dword ptr [rsp+90h+ResultLength], eax
0x1400a7857  mov     dl, dil
0x1400a785a  lea     rax, WPP_3a8656c1e584334fc686337230dfbb9f_Traceguids
0x1400a7861  mov     qword ptr [rsp+90h+Length], rax
0x1400a7866  call    WPP_RECORDER_SF_d
0x1400a786b  jmp     loc_1400A7963
0x1400a7870  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400a7874  lea     rax, [rbp+57h+arg_0]
0x1400a7878  mov     [rsp+90h+ResultLength], rax; ResultLength
0x1400a787d  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x1400a7881  mov     eax, [rbp+57h+arg_0]
0x1400a7884  mov     r9, rbx; KeyValueInformation
0x1400a7887  mov     r8d, edi; KeyValueInformationClass
0x1400a788a  mov     [rsp+90h+Length], eax; Length
0x1400a788e  call    cs:__imp_ZwQueryValueKey
0x1400a7895  nop     dword ptr [rax+rax+00h]
0x1400a789a  test    eax, eax
0x1400a789c  jz      short loc_1400A78D4
0x1400a789e  cmp     eax, 0C0000034h
0x1400a78a3  jz      short loc_1400A78D4
0x1400a78a5  mov     [rsp+90h+var_48], eax
0x1400a78a9  mov     r9d, 41h ; 'A'
0x1400a78af  mov     eax, [rbp+57h+arg_0]
0x1400a78b2  mov     [rsp+90h+var_50], eax
0x1400a78b6  lea     rax, [rbp+57h+DestinationString]
0x1400a78ba  mov     [rsp+90h+var_58], rbx
0x1400a78bf  mov     [rsp+90h+var_60], rax
0x1400a78c4  mov     rax, [rbp+57h+KeyHandle]
0x1400a78c8  mov     [rsp+90h+ResultLength], rax
0x1400a78cd  call    WPP_RECORDER_SF_qZqDd
0x1400a78d2  jmp     short loc_1400A7952
0x1400a78d4  mov     edx, [rbx+8]
0x1400a78d7  mov     ecx, 40h ; '@'
0x1400a78dc  mov     r8d, 73437356h
0x1400a78e2  call    cs:__imp_ExAllocatePool2
0x1400a78e9  nop     dword ptr [rax+rax+00h]
0x1400a78ee  mov     cs:qword_1401FA150, rax
0x1400a78f5  mov     r9, rax
0x1400a78f8  test    rax, rax
0x1400a78fb  jnz     short loc_1400A7929
0x1400a78fd  mov     rcx, cs:VmsIfrLog
0x1400a7904  lea     r9d, [rax+42h]
0x1400a7908  mov     eax, [rbx+8]
0x1400a790b  lea     r8d, [r9-2Eh]
0x1400a790f  mov     dword ptr [rsp+90h+ResultLength], eax
0x1400a7913  mov     dl, dil
0x1400a7916  lea     rax, WPP_3a8656c1e584334fc686337230dfbb9f_Traceguids
0x1400a791d  mov     qword ptr [rsp+90h+Length], rax
0x1400a7922  call    WPP_RECORDER_SF_d
0x1400a7927  jmp     short loc_1400A7952
0x1400a7929  movzx   ecx, word ptr [rbx+8]
0x1400a792d  lea     rdx, [rbx+0Ch]; Src
0x1400a7931  movzx   eax, cx
0x1400a7934  mov     cs:word_1401FA14A, cx
0x1400a793b  sub     ax, di
0x1400a793e  mov     rcx, r9; void *
0x1400a7941  movzx   r8d, ax; Size
0x1400a7945  mov     cs:VmsCsComputerName, r8w
0x1400a794d  call    memmove
0x1400a7952  xor     edx, edx; Tag
0x1400a7954  mov     rcx, rbx; P
0x1400a7957  call    cs:__imp_ExFreePoolWithTag
0x1400a795e  nop     dword ptr [rax+rax+00h]
0x1400a7963  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1400a7967  test    rcx, rcx
0x1400a796a  jz      short loc_1400A7978
0x1400a796c  call    cs:__imp_ZwClose
0x1400a7973  nop     dword ptr [rax+rax+00h]
0x1400a7978  lea     r11, [rsp+90h+var_s0]
0x1400a7980  mov     rbx, [r11+20h]
0x1400a7984  mov     rdi, [r11+28h]
0x1400a7988  mov     rsp, r11
0x1400a798b  pop     rbp
0x1400a798c  retn
```
