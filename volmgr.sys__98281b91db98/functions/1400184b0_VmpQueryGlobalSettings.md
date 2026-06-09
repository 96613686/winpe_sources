# VmpQueryGlobalSettings

- ea: `0x1400184b0`
- end: `0x140018675`
- name: `VmpQueryGlobalSettings`
- size: `453`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x140018078`

## callees

- `0x140005540`
- `0x1400131f0`
- `0x1400184b0`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140018597`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140018597`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x14001862e`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x14001862e`
- `ntoskrnl!RtlCheckRegistryKey` at `0x1400184fc`
- `ntoskrnl!RtlCheckRegistryKey` at `0x1400184fc`
- `ntoskrnl!IoGetBootDiskInformationLite` at `0x14001852d`
- `ntoskrnl!IoGetBootDiskInformationLite` at `0x14001852d`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x140018610`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x140018610`
- `ntoskrnl!ZwClose` at `0x14001863e`
- `ntoskrnl!ZwClose` at `0x14001863e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018655`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018655`

## string_xrefs

- `0x140018552`: `\Registry\Machine\System\Setup`

## pseudocode

```c
__int64 VmpQueryGlobalSettings()
{
  NTSTATUS v0; // eax
  NTSTATUS BootDiskInformationLite; // ebx
  int RegistryValues; // eax
  unsigned int v3; // eax
  struct VM_ROOT_EXTENSION *v4; // rcx
  unsigned int *v5; // rdx
  _QWORD v7[14]; // [rsp+30h] [rbp-19h] BYREF
  int v8; // [rsp+B0h] [rbp+67h] BYREF
  PBOOTDISK_INFORMATION_LITE BootDiskInformation; // [rsp+B8h] [rbp+6Fh] BYREF
  PCWSTR Path; // [rsp+C0h] [rbp+77h]

  BootDiskInformation = 0;
  Path = 0;
  memset(v7, 0, sizeof(v7));
  v8 = 0;
  v0 = RtlCheckRegistryKey(2u, (PWSTR)L"MiniNT");
  BootDiskInformationLite = v0;
  if ( v0 < 0 )
  {
    if ( v0 != -1073741772 )
      goto LABEL_12;
  }
  else
  {
    *((_BYTE *)VmRootExtension + 284) = 1;
  }
  BootDiskInformationLite = IoGetBootDiskInformationLite(&BootDiskInformation);
  if ( BootDiskInformationLite >= 0 )
  {
    *((_QWORD *)VmRootExtension + 43) = BootDiskInformation;
    v7[2] = L"SystemDriveLetter";
    BootDiskInformation = 0;
    v7[3] = &v8;
    LODWORD(v7[1]) = 292;
    LODWORD(v7[4]) = 0x4000000;
    RegistryValues = RtlQueryRegistryValuesEx(0, L"\\Registry\\Machine\\System\\Setup", v7, 0, 0);
    BootDiskInformationLite = RegistryValues;
    if ( RegistryValues == -1073741772 )
    {
      v3 = 0;
      v8 = 0;
    }
    else
    {
      if ( RegistryValues < 0 )
        goto LABEL_12;
      v3 = v8;
    }
    if ( v3 > 1 )
    {
      LOBYTE(v3) = 1;
      v8 = 1;
    }
    v4 = VmRootExtension;
    v5 = (unsigned int *)((char *)VmRootExtension + 352);
    *((_BYTE *)VmRootExtension + 285) = *((_BYTE *)VmRootExtension + 284) | v3;
    VmpQueryRegistryRevertEntries((struct VM_GPT_ATTRIBUTES_REVERT_ENTRY **)v4 + 45, v5);
    BootDiskInformationLite = IoOpenDriverRegistryKey(*((_QWORD *)VmRootExtension + 4), 1, 2);
    RtlDeleteRegistryValue(0x40000000u, Path, L"GptAttributeRevertEntries");
    ZwClose((HANDLE)Path);
  }
LABEL_12:
  if ( BootDiskInformation )
    ExFreePoolWithTag(BootDiskInformation, 0);
  return (unsigned int)BootDiskInformationLite;
}

```

## disassembly

```asm
0x1400184b0  mov     [rsp-8+arg_18], rbx
0x1400184b5  push    rbp
0x1400184b6  lea     rbp, [rsp-57h]
0x1400184bb  sub     rsp, 0A0h
0x1400184c2  xor     edx, edx; Val
0x1400184c4  mov     [rbp+57h+BootDiskInformation], 0
0x1400184cc  lea     rcx, [rbp+57h+var_68]; void *
0x1400184d0  mov     [rbp+57h+Path], 0
0x1400184d8  mov     [rbp+57h+var_70], 0
0x1400184e0  lea     r8d, [rdx+68h]; Size
0x1400184e4  call    memset
0x1400184e9  lea     rdx, Path; "MiniNT"
0x1400184f0  mov     [rbp+57h+arg_0], 0
0x1400184f7  mov     ecx, 2; RelativeTo
0x1400184fc  call    cs:__imp_RtlCheckRegistryKey
0x140018503  nop     dword ptr [rax+rax+00h]
0x140018508  mov     ebx, eax
0x14001850a  test    eax, eax
0x14001850c  js      short loc_14001851E
0x14001850e  mov     rax, cs:?VmRootExtension@@3PEAVVM_ROOT_EXTENSION@@EA; VM_ROOT_EXTENSION * VmRootExtension
0x140018515  mov     byte ptr [rax+11Ch], 1
0x14001851c  jmp     short loc_140018529
0x14001851e  cmp     eax, 0C0000034h
0x140018523  jnz     loc_14001864A
0x140018529  lea     rcx, [rbp+57h+BootDiskInformation]; BootDiskInformation
0x14001852d  call    cs:__imp_IoGetBootDiskInformationLite
0x140018534  nop     dword ptr [rax+rax+00h]
0x140018539  mov     ebx, eax
0x14001853b  test    eax, eax
0x14001853d  js      loc_14001864A
0x140018543  mov     rcx, [rbp+57h+BootDiskInformation]
0x140018547  lea     r8, [rbp+57h+var_70]
0x14001854b  mov     rax, cs:?VmRootExtension@@3PEAVVM_ROOT_EXTENSION@@EA; VM_ROOT_EXTENSION * VmRootExtension
0x140018552  lea     rdx, aRegistryMachin_1; "\\Registry\\Machine\\System\\Setup"
0x140018559  xor     r9d, r9d
0x14001855c  mov     [rsp+0A0h+var_80], 0
0x140018565  mov     [rax+158h], rcx
0x14001856c  lea     rax, aSystemdrivelet; "SystemDriveLetter"
0x140018573  mov     [rbp+57h+var_60], rax
0x140018577  xor     ecx, ecx
0x140018579  lea     rax, [rbp+57h+arg_0]
0x14001857d  mov     [rbp+57h+BootDiskInformation], 0
0x140018585  mov     [rbp+57h+var_58], rax
0x140018589  mov     [rbp+57h+var_68], 124h
0x140018590  mov     [rbp+57h+var_50], 4000000h
0x140018597  call    cs:__imp_RtlQueryRegistryValuesEx
0x14001859e  nop     dword ptr [rax+rax+00h]
0x1400185a3  mov     ebx, eax
0x1400185a5  cmp     eax, 0C0000034h
0x1400185aa  jnz     short loc_1400185B3
0x1400185ac  xor     eax, eax
0x1400185ae  mov     [rbp+57h+arg_0], eax
0x1400185b1  jmp     short loc_1400185BE
0x1400185b3  test    eax, eax
0x1400185b5  js      loc_14001864A
0x1400185bb  mov     eax, [rbp+57h+arg_0]
0x1400185be  cmp     eax, 1
0x1400185c1  jbe     short loc_1400185CB
0x1400185c3  mov     eax, 1
0x1400185c8  mov     [rbp+57h+arg_0], eax
0x1400185cb  mov     rcx, cs:?VmRootExtension@@3PEAVVM_ROOT_EXTENSION@@EA; VM_ROOT_EXTENSION * VmRootExtension
0x1400185d2  or      al, [rcx+11Ch]
0x1400185d8  lea     rdx, [rcx+160h]; unsigned int *
0x1400185df  mov     [rcx+11Dh], al
0x1400185e5  add     rcx, 168h; struct VM_GPT_ATTRIBUTES_REVERT_ENTRY **
0x1400185ec  call    ?VmpQueryRegistryRevertEntries@@YAJPEAPEAVVM_GPT_ATTRIBUTES_REVERT_ENTRY@@PEAK@Z; VmpQueryRegistryRevertEntries(VM_GPT_ATTRIBUTES_REVERT_ENTRY * *,ulong *)
0x1400185f1  mov     rcx, cs:?VmRootExtension@@3PEAVVM_ROOT_EXTENSION@@EA; VM_ROOT_EXTENSION * VmRootExtension
0x1400185f8  lea     rax, [rbp+57h+Path]
0x1400185fc  xor     r9d, r9d
0x1400185ff  mov     [rsp+0A0h+var_80], rax
0x140018604  mov     rcx, [rcx+20h]
0x140018608  lea     edx, [r9+1]
0x14001860c  lea     r8d, [r9+2]
0x140018610  call    cs:__imp_IoOpenDriverRegistryKey
0x140018617  nop     dword ptr [rax+rax+00h]
0x14001861c  mov     rdx, [rbp+57h+Path]; Path
0x140018620  lea     r8, ValueName; "GptAttributeRevertEntries"
0x140018627  mov     ecx, 40000000h; RelativeTo
0x14001862c  mov     ebx, eax
0x14001862e  call    cs:__imp_RtlDeleteRegistryValue
0x140018635  nop     dword ptr [rax+rax+00h]
0x14001863a  mov     rcx, [rbp+57h+Path]; Handle
0x14001863e  call    cs:__imp_ZwClose
0x140018645  nop     dword ptr [rax+rax+00h]
0x14001864a  mov     rcx, [rbp+57h+BootDiskInformation]; P
0x14001864e  test    rcx, rcx
0x140018651  jz      short loc_140018661
0x140018653  xor     edx, edx; Tag
0x140018655  call    cs:__imp_ExFreePoolWithTag
0x14001865c  nop     dword ptr [rax+rax+00h]
0x140018661  mov     eax, ebx
0x140018663  mov     rbx, [rsp+0A0h+arg_18]
0x14001866b  add     rsp, 0A0h
0x140018672  pop     rbp
0x140018673  retn
```
