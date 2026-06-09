# CheckOptInWinUsbPrint

- ea: `0x14002610c`
- end: `0x14002628b`
- name: `CheckOptInWinUsbPrint`
- size: `383`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140023938`

## callees

- `0x14000db98`
- `0x140014d10`
- `0x14002610c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140026258`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026258`
- `ntoskrnl!ZwQueryValueKey` at `0x140026230`
- `ntoskrnl!ZwQueryValueKey` at `0x140026230`
- `ntoskrnl!ZwClose` at `0x140026242`
- `ntoskrnl!ZwClose` at `0x140026242`
- `ntoskrnl!ZwOpenKey` at `0x140026201`
- `ntoskrnl!ZwOpenKey` at `0x140026201`
- `ntoskrnl!ExAllocatePool2` at `0x14002616e`
- `ntoskrnl!ExAllocatePool2` at `0x14002616e`
- `ntoskrnl!RtlInitUnicodeString` at `0x140026191`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400261c8`
- `ntoskrnl!RtlInitUnicodeString` at `0x140026191`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400261c8`

## string_xrefs

- `0x140026186`: `\Registry\Machine\System\CurrentControlSet\Control\Print\Monitors\WinUsbMon\OptInModels`

## pseudocode

```c
_BOOL8 __fastcall CheckOptInWinUsbPrint(unsigned __int16 a1, unsigned __int16 a2)
{
  int v2; // r14d
  unsigned int v3; // esi
  BOOL v4; // ebx
  void *Pool2; // rdi
  NTSTATUS v6; // ebx
  ULONG Length; // [rsp+30h] [rbp-49h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-41h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-39h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-9h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+80h] [rbp+7h] BYREF
  wchar_t pszDest[20]; // [rsp+90h] [rbp+17h] BYREF

  v2 = a2;
  v3 = a1;
  KeyHandle = 0;
  v4 = 0;
  Length = 20;
  DestinationString = 0;
  ValueName = 0;
  memset(&ObjectAttributes, 0, 44);
  Pool2 = (void *)ExAllocatePool2(256, 20, 1130525525);
  if ( Pool2 )
  {
    RtlInitUnicodeString(
      &DestinationString,
      L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Print\\Monitors\\WinUsbMon\\OptInModels");
    if ( RtlStringCbPrintfW(pszDest, 0x24u, L"VID_%04X&PID_%04X", v3, v2) >= 0 )
    {
      RtlInitUnicodeString(&ValueName, pszDest);
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes) >= 0 )
      {
        v6 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, Pool2, Length, &Length);
        ZwClose(KeyHandle);
        v4 = v6 >= 0;
      }
    }
    ExFreePoolWithTag(Pool2, 0);
  }
  return v4;
}

```

## disassembly

```asm
0x14002610c  mov     [rsp-8+arg_10], rbx
0x140026111  mov     [rsp-8+arg_18], rsi
0x140026116  push    rbp
0x140026117  push    rdi
0x140026118  push    r14
0x14002611a  lea     rbp, [rsp-47h]
0x14002611f  sub     rsp, 0C0h
0x140026126  mov     rax, cs:__security_cookie
0x14002612d  xor     rax, rsp
0x140026130  mov     [rbp+57h+var_18], rax
0x140026134  xorps   xmm0, xmm0
0x140026137  movzx   r14d, dx
0x14002613b  xor     eax, eax
0x14002613d  movzx   esi, cx
0x140026140  xorps   xmm1, xmm1
0x140026143  mov     [rbp+57h+KeyHandle], rax
0x140026147  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14002614b  mov     ecx, 100h
0x140026150  mov     r8d, 43627355h
0x140026156  lea     edx, [rax+14h]
0x140026159  xor     ebx, ebx
0x14002615b  mov     [rbp+57h+var_A0], edx
0x14002615e  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140026162  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x140026166  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14002616a  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14002616e  call    cs:__imp_ExAllocatePool2
0x140026175  nop     dword ptr [rax+rax+00h]
0x14002617a  mov     rdi, rax
0x14002617d  test    rax, rax
0x140026180  jz      loc_140026264
0x140026186  lea     rdx, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x14002618d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140026191  call    cs:__imp_RtlInitUnicodeString
0x140026198  nop     dword ptr [rax+rax+00h]
0x14002619d  mov     r9d, esi
0x1400261a0  mov     [rsp+0D0h+Length], r14d
0x1400261a5  lea     r8, aVid04xPid04x; "VID_%04X&PID_%04X"
0x1400261ac  lea     edx, [rbx+24h]; cbDest
0x1400261af  lea     rcx, [rbp+57h+pszDest]; pszDest
0x1400261b3  call    RtlStringCbPrintfW
0x1400261b8  test    eax, eax
0x1400261ba  js      loc_140026253
0x1400261c0  lea     rdx, [rbp+57h+pszDest]; SourceString
0x1400261c4  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x1400261c8  call    cs:__imp_RtlInitUnicodeString
0x1400261cf  nop     dword ptr [rax+rax+00h]
0x1400261d4  lea     rax, [rbp+57h+DestinationString]
0x1400261d8  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400261df  xorps   xmm0, xmm0
0x1400261e2  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400261e6  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400261ea  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x1400261ee  lea     edx, [rbx+1]; DesiredAccess
0x1400261f1  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1400261f8  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400261fc  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140026201  call    cs:__imp_ZwOpenKey
0x140026208  nop     dword ptr [rax+rax+00h]
0x14002620d  test    eax, eax
0x14002620f  js      short loc_140026253
0x140026211  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140026215  lea     rax, [rbp+57h+var_A0]
0x140026219  mov     [rsp+0D0h+ResultLength], rax; ResultLength
0x14002621e  lea     r8d, [rbx+2]; KeyValueInformationClass
0x140026222  mov     eax, [rbp+57h+var_A0]
0x140026225  lea     rdx, [rbp+57h+ValueName]; ValueName
0x140026229  mov     r9, rdi; KeyValueInformation
0x14002622c  mov     [rsp+0D0h+Length], eax; Length
0x140026230  call    cs:__imp_ZwQueryValueKey
0x140026237  nop     dword ptr [rax+rax+00h]
0x14002623c  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x140026240  mov     ebx, eax
0x140026242  call    cs:__imp_ZwClose
0x140026249  nop     dword ptr [rax+rax+00h]
0x14002624e  not     ebx
0x140026250  shr     ebx, 1Fh
0x140026253  xor     edx, edx; Tag
0x140026255  mov     rcx, rdi; P
0x140026258  call    cs:__imp_ExFreePoolWithTag
0x14002625f  nop     dword ptr [rax+rax+00h]
0x140026264  mov     eax, ebx
0x140026266  mov     rcx, [rbp+57h+var_18]
0x14002626a  xor     rcx, rsp; StackCookie
0x14002626d  call    __security_check_cookie
0x140026272  lea     r11, [rsp+0D0h+var_10]
0x14002627a  mov     rbx, [r11+30h]
0x14002627e  mov     rsi, [r11+38h]
0x140026282  mov     rsp, r11
0x140026285  pop     r14
0x140026287  pop     rdi
0x140026288  pop     rbp
0x140026289  retn
```
