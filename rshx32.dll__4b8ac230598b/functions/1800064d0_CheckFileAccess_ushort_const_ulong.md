# CheckFileAccess(ushort const *,ulong *)

- ea: `0x1800064d0`
- end: `0x1800065fe`
- name: `?CheckFileAccess@@YAJPEBGPEAK@Z`
- size: `302`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000a0e4`
- `0x18000a440`

## callees

- `0x1800064d0`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1800065de`
- `ntdll!RtlFreeUnicodeString` at `0x1800065de`
- `ntdll!NtOpenFile` at `0x1800065ae`
- `ntdll!NtOpenFile` at `0x1800065ae`
- `ntdll!RtlNtStatusToDosError` at `0x1800065b6`
- `ntdll!RtlNtStatusToDosError` at `0x1800065b6`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180006536`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180006536`
- `ntdll!NtClose` at `0x1800065c7`
- `ntdll!NtClose` at `0x1800065c7`

## pseudocode

```c
__int64 __fastcall CheckFileAccess(const unsigned __int16 *a1, unsigned int *a2)
{
  unsigned int v3; // esi
  __int64 i; // rdi
  ACCESS_MASK v5; // r14d
  unsigned int v6; // eax
  NTSTATUS v7; // eax
  _UNICODE_STRING NtPathName; // [rsp+30h] [rbp-29h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-19h] BYREF
  ACCESS_MASK DesiredAccess[6]; // [rsp+50h] [rbp-9h]
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp+Fh] BYREF
  void *FileHandle; // [rsp+C8h] [rbp+6Fh] BYREF

  DesiredAccess[0] = 17694720;
  DesiredAccess[1] = 0x20000;
  DesiredAccess[2] = 0x40000;
  DesiredAccess[3] = 0x80000;
  DesiredAccess[4] = 0x1000000;
  NtPathName = 0;
  if ( a2 )
  {
    *a2 = 0;
    if ( RtlDosPathNameToNtPathName_U(a1, &NtPathName, 0, 0) )
    {
      v3 = 0;
      for ( i = 0; i != 5; ++i )
      {
        v5 = DesiredAccess[i];
        v6 = v5 & *a2;
        FileHandle = 0;
        memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
        IoStatusBlock = 0;
        if ( v6 != v5 )
        {
          ObjectAttributes.ObjectName = &NtPathName;
          ObjectAttributes.Length = 48;
          ObjectAttributes.RootDirectory = 0;
          ObjectAttributes.Attributes = 64;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          v7 = NtOpenFile(&FileHandle, v5, &ObjectAttributes, &IoStatusBlock, 3u, 0);
          if ( !RtlNtStatusToDosError(v7) )
          {
            *a2 |= v5;
            NtClose(FileHandle);
          }
        }
      }
    }
    else
    {
      v3 = -2147024882;
    }
  }
  else
  {
    v3 = -2147467261;
  }
  RtlFreeUnicodeString(&NtPathName);
  return v3;
}

```

## disassembly

```asm
0x1800064d0  mov     [rsp-8+arg_0], rbx
0x1800064d5  mov     [rsp-8+arg_10], rsi
0x1800064da  push    rbp
0x1800064db  push    rdi
0x1800064dc  push    r14
0x1800064de  lea     rbp, [rsp-47h]
0x1800064e3  sub     rsp, 0A0h
0x1800064ea  mov     [rbp+57h+DesiredAccess], 10E0000h
0x1800064f1  xorps   xmm0, xmm0
0x1800064f4  mov     [rbp+57h+var_5C], 20000h
0x1800064fb  mov     rbx, rdx
0x1800064fe  mov     [rbp+57h+var_58], 40000h
0x180006505  mov     [rbp+57h+var_54], 80000h
0x18000650c  mov     [rbp+57h+var_50], 1000000h
0x180006513  movups  xmmword ptr [rbp+57h+NtPathName.Length], xmm0
0x180006517  test    rdx, rdx
0x18000651a  jnz     short loc_180006526
0x18000651c  mov     esi, 80004003h
0x180006521  jmp     loc_1800065DA
0x180006526  mov     dword ptr [rdx], 0
0x18000652c  xor     r9d, r9d; DirectoryInfo
0x18000652f  lea     rdx, [rbp+57h+NtPathName]; NtPathName
0x180006533  xor     r8d, r8d; NtFileNamePart
0x180006536  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x18000653c  test    al, al
0x18000653e  jnz     short loc_18000654A
0x180006540  mov     esi, 8007000Eh
0x180006545  jmp     loc_1800065DA
0x18000654a  xor     esi, esi
0x18000654c  xor     edi, edi
0x18000654e  mov     r14d, [rbp+rdi*4+57h+DesiredAccess]
0x180006553  xorps   xmm0, xmm0
0x180006556  mov     eax, [rbx]
0x180006558  and     eax, r14d
0x18000655b  mov     [rbp+57h+FileHandle], rsi
0x18000655f  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180006563  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180006567  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000656b  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18000656f  cmp     eax, r14d
0x180006572  jz      short loc_1800065CD
0x180006574  lea     rax, [rbp+57h+NtPathName]
0x180006578  mov     [rsp+0B0h+OpenOptions], esi; OpenOptions
0x18000657c  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180006580  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180006584  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180006588  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18000658f  mov     edx, r14d; DesiredAccess
0x180006592  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x180006596  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18000659a  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800065a1  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800065a6  mov     [rsp+0B0h+ShareAccess], 3; ShareAccess
0x1800065ae  call    cs:__imp_NtOpenFile
0x1800065b4  mov     ecx, eax; Status
0x1800065b6  call    cs:__imp_RtlNtStatusToDosError
0x1800065bc  test    eax, eax
0x1800065be  jnz     short loc_1800065CD
0x1800065c0  or      [rbx], r14d
0x1800065c3  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800065c7  call    cs:__imp_NtClose
0x1800065cd  inc     rdi
0x1800065d0  cmp     rdi, 5
0x1800065d4  jnz     loc_18000654E
0x1800065da  lea     rcx, [rbp+57h+NtPathName]; UnicodeString
0x1800065de  call    cs:__imp_RtlFreeUnicodeString
0x1800065e4  lea     r11, [rsp+0B0h+var_10]
0x1800065ec  mov     eax, esi
0x1800065ee  mov     rbx, [r11+20h]
0x1800065f2  mov     rsi, [r11+30h]
0x1800065f6  mov     rsp, r11
0x1800065f9  pop     r14
0x1800065fb  pop     rdi
0x1800065fc  pop     rbp
0x1800065fd  retn
```
