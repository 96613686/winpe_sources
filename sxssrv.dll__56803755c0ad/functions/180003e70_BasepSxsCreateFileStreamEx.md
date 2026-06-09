# BasepSxsCreateFileStreamEx

- ea: `0x180003e70`
- end: `0x1800040e6`
- name: `BasepSxsCreateFileStreamEx`
- size: `630`
- prototype: `__int64 __fastcall(__int64, __int128 **, __int16, void **, __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180002800`
- `0x180002c50`
- `0x180003170`

## callees

- `0x180003e70`
- `0x18000658c`
- `0x1800065a4`
- `0x1800065b0`
- `0x180006c30`

## import_xrefs

- `ntdll!NtCreateSection` at `0x180004002`
- `ntdll!NtCreateSection` at `0x180004002`

## string_xrefs

- `0x180003f02`: `BasepSxsCreateFileStreamEx`
- `0x18000409e`: `BasepSxsCreateFileStreamEx`
- `0x1800040cb`: `BasepSxsCreateFileStreamEx`
- `0x1800040aa`: `SXS: %s() NtOpenFile(%wZ) failed. Status = 0x%x\n`
- `0x1800040d2`: `SXS: %s() NtCreateSection() failed. Status = 0x%x\n`

## pseudocode

```c
__int64 __fastcall BasepSxsCreateFileStreamEx(__int64 a1, __int128 **a2, __int16 a3, void **a4, __int64 a5)
{
  NTSTATUS v7; // eax
  unsigned int v8; // edi
  ULONG v9; // eax
  NTSTATUS v10; // eax
  __int64 v12; // rcx
  NTSTATUS Section; // eax
  __int128 v14; // xmm0
  __int64 OpenOptions; // [rsp+28h] [rbp-90h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-78h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-48h] BYREF
  __int128 FileInformation; // [rsp+80h] [rbp-38h] BYREF
  __int64 v19; // [rsp+90h] [rbp-28h]

  memset(&ObjectAttributes, 0, 44);
  v19 = 0;
  IoStatusBlock = 0;
  FileInformation = 0;
  if ( *a4 )
    goto LABEL_2;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Length = 48;
  v9 = 2112;
  if ( (a3 & 0x7000) != 0x7000 )
    v9 = 64;
  ObjectAttributes.Attributes = v9;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)a2[1];
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v10 = NtOpenFile_0(a4, 0x120089u, &ObjectAttributes, &IoStatusBlock, 5u, 0x60u);
  v8 = v10;
  if ( v10 >= 0 )
  {
LABEL_2:
    v7 = NtQueryInformationFile_0(*a4, &IoStatusBlock, &FileInformation, 0x18u, FileStandardInformation);
    v8 = v7;
    if ( v7 >= 0 )
    {
      v12 = *((_QWORD *)&FileInformation + 1);
      if ( *((__int64 *)&FileInformation + 1) <= 0x800000 )
      {
        if ( !a4[2] )
        {
          Section = NtCreateSection(a4 + 2, 4u, 0, 0, 2u, 0x8000000u, *a4);
          v8 = Section;
          if ( Section < 0 )
          {
            DbgPrintEx_0(
              0x33u,
              0,
              "SXS: %s() NtCreateSection() failed. Status = 0x%x\n",
              "BasepSxsCreateFileStreamEx",
              Section);
            return v8;
          }
          v12 = *((_QWORD *)&FileInformation + 1);
        }
        v8 = 0;
        *(_QWORD *)(a5 + 24) = *a4;
        *(_WORD *)a5 = 257;
        v14 = **a2;
        *(_BYTE *)(a5 + 2) = 3;
        *(_OWORD *)(a5 + 8) = v14;
        *(_QWORD *)(a5 + 32) = a4[2];
        *(_QWORD *)(a5 + 40) = 0;
        *(_QWORD *)(a5 + 48) = v12;
        return v8;
      }
      return (unsigned int)-1072365534;
    }
    else
    {
      DbgPrintEx_0(
        0x33u,
        0,
        "SXS: %s() NtQueryInformationFile failed. Status = 0x%x\n",
        "BasepSxsCreateFileStreamEx",
        v7);
    }
  }
  else if ( v10 != -1073741772
         && (unsigned int)(v10 + 1073741687) > 2
         && v10 != -1073741308
         && v10 != -1073741809
         && v10 != -1072365566 )
  {
    LODWORD(OpenOptions) = v10;
    DbgPrintEx_0(
      0x33u,
      0,
      "SXS: %s() NtOpenFile(%wZ) failed. Status = 0x%x\n",
      "BasepSxsCreateFileStreamEx",
      ObjectAttributes.ObjectName,
      OpenOptions);
  }
  return v8;
}

```

## disassembly

```asm
0x180003e70  mov     r11, rsp
0x180003e73  mov     [r11+18h], rbx
0x180003e77  push    rsi
0x180003e78  push    rdi
0x180003e79  push    r14
0x180003e7b  sub     rsp, 0A0h
0x180003e82  mov     rax, cs:__security_cookie
0x180003e89  xor     rax, rsp
0x180003e8c  mov     [rsp+0B8h+var_20], rax
0x180003e94  mov     r14, [rsp+0B8h+arg_20]
0x180003e9c  xor     eax, eax
0x180003e9e  xorps   xmm0, xmm0
0x180003ea1  xorps   xmm1, xmm1
0x180003ea4  mov     rbx, r9
0x180003ea7  mov     rsi, rdx
0x180003eaa  movups  xmmword ptr [rsp+0B8h+ObjectAttributes.Length], xmm0
0x180003eaf  mov     [r11-28h], rax
0x180003eb3  movups  xmmword ptr [rsp+0B8h+ObjectAttributes.ObjectName], xmm0
0x180003eb8  mov     [r11-58h], rax
0x180003ebc  mov     dword ptr [rsp+0B8h+ObjectAttributes.SecurityQualityOfService], eax
0x180003ec0  movups  xmmword ptr [rsp+0B8h+IoStatusBlock], xmm0
0x180003ec5  movups  xmmword ptr [r11-38h], xmm1
0x180003eca  cmp     [r9], rax
0x180003ecd  jz      short loc_180003F1A
0x180003ecf  mov     rcx, [rbx]; FileHandle
0x180003ed2  lea     r8, [rsp+0B8h+FileInformation]; FileInformation
0x180003eda  mov     r9d, 18h; Length
0x180003ee0  mov     [rsp+0B8h+FileInformationClass], 5; FileInformationClass
0x180003ee8  lea     rdx, [rsp+0B8h+IoStatusBlock]; IoStatusBlock
0x180003eed  call    NtQueryInformationFile_0
0x180003ef2  mov     edi, eax
0x180003ef4  test    eax, eax
0x180003ef6  jns     loc_180003FB8
0x180003efc  xor     edx, edx; Level
0x180003efe  mov     [rsp+0B8h+FileInformationClass], eax
0x180003f02  lea     r9, aBasepsxscreate; "BasepSxsCreateFileStreamEx"
0x180003f09  lea     r8, aSxsSNtqueryinf; "SXS: %s() NtQueryInformationFile failed"...
0x180003f10  lea     ecx, [rdx+33h]; ComponentId
0x180003f13  call    DbgPrintEx_0
0x180003f18  jmp     short loc_180003F91
0x180003f1a  mov     [rsp+0B8h+ObjectAttributes.RootDirectory], rax
0x180003f1f  lea     r9, [rsp+0B8h+IoStatusBlock]; IoStatusBlock
0x180003f24  and     r8d, 7000h
0x180003f2b  mov     dword ptr [rsp+0B8h+OpenOptions], 60h ; '`'; OpenOptions
0x180003f33  cmp     r8d, 7000h
0x180003f3a  mov     [rsp+0B8h+ObjectAttributes.Length], 30h ; '0'
0x180003f42  mov     eax, 840h
0x180003f47  mov     [rsp+0B8h+FileInformationClass], 5; ShareAccess
0x180003f4f  mov     ecx, 40h ; '@'
0x180003f54  lea     r8, [rsp+0B8h+ObjectAttributes]; ObjectAttributes
0x180003f59  cmovnz  eax, ecx
0x180003f5c  mov     rcx, rbx; FileHandle
0x180003f5f  mov     [rsp+0B8h+ObjectAttributes.Attributes], eax
0x180003f63  mov     rax, [rdx+8]
0x180003f67  mov     edx, 120089h; DesiredAccess
0x180003f6c  mov     [rsp+0B8h+ObjectAttributes.ObjectName], rax
0x180003f71  movdqu  xmmword ptr [rsp+60h], xmm0
0x180003f77  call    NtOpenFile_0
0x180003f7c  mov     edi, eax
0x180003f7e  test    eax, eax
0x180003f80  jns     loc_180003ECF
0x180003f86  cmp     eax, 0C0000034h
0x180003f8b  jnz     loc_18000406A
0x180003f91  mov     eax, edi
0x180003f93  mov     rcx, [rsp+0B8h+var_20]
0x180003f9b  xor     rcx, rsp; StackCookie
0x180003f9e  call    __security_check_cookie
0x180003fa3  mov     rbx, [rsp+0B8h+arg_10]
0x180003fab  add     rsp, 0A0h
0x180003fb2  pop     r14
0x180003fb4  pop     rdi
0x180003fb5  pop     rsi
0x180003fb6  retn
0x180003fb8  mov     rcx, [rsp+0B8h+var_30]
0x180003fc0  cmp     rcx, 800000h
0x180003fc7  jg      loc_180004060
0x180003fcd  cmp     qword ptr [rbx+10h], 0
0x180003fd2  mov     [rsp+0B8h+arg_0], r15
0x180003fda  jnz     short loc_180004020
0x180003fdc  mov     rax, [rbx]
0x180003fdf  lea     rcx, [rbx+10h]; SectionHandle
0x180003fe3  mov     [rsp+0B8h+FileHandle], rax; FileHandle
0x180003fe8  xor     r9d, r9d; MaximumSize
0x180003feb  mov     dword ptr [rsp+0B8h+OpenOptions], 8000000h; AllocationAttributes
0x180003ff3  xor     r8d, r8d; ObjectAttributes
0x180003ff6  mov     [rsp+0B8h+FileInformationClass], 2; SectionPageProtection
0x180003ffe  lea     edx, [r9+4]; DesiredAccess
0x180004002  call    cs:__imp_NtCreateSection
0x180004009  nop     dword ptr [rax+rax+00h]
0x18000400e  mov     edi, eax
0x180004010  test    eax, eax
0x180004012  js      loc_1800040C5
0x180004018  mov     rcx, [rsp+0B8h+var_30]
0x180004020  mov     rax, [rbx]
0x180004023  xor     edi, edi
0x180004025  mov     [r14+18h], rax
0x180004029  mov     word ptr [r14], 101h
0x18000402f  mov     rax, [rsi]
0x180004032  movups  xmm0, xmmword ptr [rax]
0x180004035  mov     byte ptr [r14+2], 3
0x18000403a  movups  xmmword ptr [r14+8], xmm0
0x18000403f  mov     rax, [rbx+10h]
0x180004043  mov     [r14+20h], rax
0x180004047  mov     qword ptr [r14+28h], 0
0x18000404f  mov     [r14+30h], rcx
0x180004053  mov     r15, [rsp+0B8h+arg_0]
0x18000405b  jmp     loc_180003F91
0x180004060  mov     edi, 0C0150022h
0x180004065  jmp     loc_180003F91
0x18000406a  lea     ecx, [rax+3FFFFF77h]
0x180004070  cmp     ecx, 2
0x180004073  jbe     loc_180003F91
0x180004079  cmp     eax, 0C0000204h
0x18000407e  jz      loc_180003F91
0x180004084  cmp     eax, 0C000000Fh
0x180004089  jz      loc_180003F91
0x18000408f  cmp     eax, 0C0150002h
0x180004094  jz      loc_180003F91
0x18000409a  mov     dword ptr [rsp+0B8h+OpenOptions], eax
0x18000409e  lea     r9, aBasepsxscreate; "BasepSxsCreateFileStreamEx"
0x1800040a5  mov     rax, [rsp+0B8h+ObjectAttributes.ObjectName]
0x1800040aa  lea     r8, aSxsSNtopenfile; "SXS: %s() NtOpenFile(%wZ) failed. Statu"...
0x1800040b1  xor     edx, edx; Level
0x1800040b3  mov     qword ptr [rsp+0B8h+FileInformationClass], rax
0x1800040b8  lea     ecx, [rdx+33h]; ComponentId
0x1800040bb  call    DbgPrintEx_0
0x1800040c0  jmp     loc_180003F91
0x1800040c5  xor     edx, edx; Level
0x1800040c7  mov     [rsp+0B8h+FileInformationClass], eax
0x1800040cb  lea     r9, aBasepsxscreate; "BasepSxsCreateFileStreamEx"
0x1800040d2  lea     r8, aSxsSNtcreatese; "SXS: %s() NtCreateSection() failed. Sta"...
0x1800040d9  lea     ecx, [rdx+33h]; ComponentId
0x1800040dc  call    DbgPrintEx_0
0x1800040e1  jmp     loc_180004053
```
