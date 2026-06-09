# SmpConfigureRenameTempDir

- ea: `0x140013830`
- end: `0x1400138b0`
- name: `SmpConfigureRenameTempDir`
- size: `128`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, registry_config, loader_planting`

## callees

- `0x140013830`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1400138a3`
- `ntdll!RtlFreeUnicodeString` at `0x1400138a3`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x140013867`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x140013867`
- `ntdll!RtlCopyUnicodeString` at `0x140013890`
- `ntdll!RtlCopyUnicodeString` at `0x140013890`

## pseudocode

```c
__int64 __fastcall SmpConfigureRenameTempDir(__int64 a1, int a2, const WCHAR *a3, int a4)
{
  struct _UNICODE_STRING NtPathName; // [rsp+20h] [rbp-18h] BYREF

  *(_QWORD *)&NtPathName.Length = 0;
  NtPathName.Buffer = 0;
  if ( (unsigned int)(a4 - 1) <= 0x208 && a2 == 1 && RtlDosPathNameToNtPathName_U(a3, &NtPathName, 0, 0) )
  {
    if ( NtPathName.Length < 0x20Au )
    {
      SmpTempFilesDir.MaximumLength = 522;
      RtlCopyUnicodeString(&SmpTempFilesDir, &NtPathName);
    }
    if ( NtPathName.Buffer )
      RtlFreeUnicodeString(&NtPathName);
  }
  return 0;
}

```

## disassembly

```asm
0x140013830  sub     rsp, 38h
0x140013834  lea     eax, [r9-1]
0x140013838  mov     qword ptr [rsp+38h+NtPathName.Length], 0
0x140013841  mov     [rsp+38h+NtPathName.Buffer], 0
0x14001384a  mov     r10, r8
0x14001384d  cmp     eax, 208h
0x140013852  ja      short loc_1400138A9
0x140013854  cmp     edx, 1
0x140013857  jnz     short loc_1400138A9
0x140013859  xor     r9d, r9d; DirectoryInfo
0x14001385c  lea     rdx, [rsp+38h+NtPathName]; NtPathName
0x140013861  xor     r8d, r8d; NtFileNamePart
0x140013864  mov     rcx, r10; DosPathName
0x140013867  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x14001386d  test    al, al
0x14001386f  jz      short loc_1400138A9
0x140013871  mov     eax, 20Ah
0x140013876  cmp     [rsp+38h+NtPathName.Length], ax
0x14001387b  jnb     short loc_140013896
0x14001387d  lea     rdx, [rsp+38h+NtPathName]; SourceString
0x140013882  mov     cs:SmpTempFilesDir.MaximumLength, ax
0x140013889  lea     rcx, SmpTempFilesDir; DestinationString
0x140013890  call    cs:__imp_RtlCopyUnicodeString
0x140013896  cmp     [rsp+38h+NtPathName.Buffer], 0
0x14001389c  jz      short loc_1400138A9
0x14001389e  lea     rcx, [rsp+38h+NtPathName]; UnicodeString
0x1400138a3  call    cs:__imp_RtlFreeUnicodeString
0x1400138a9  xor     eax, eax
0x1400138ab  add     rsp, 38h
0x1400138af  retn
```
