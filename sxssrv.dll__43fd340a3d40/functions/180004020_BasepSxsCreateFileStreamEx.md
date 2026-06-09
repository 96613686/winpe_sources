# BasepSxsCreateFileStreamEx

- ea: `0x180004020`
- end: `0x1800042a2`
- name: `BasepSxsCreateFileStreamEx`
- size: `642`
- prototype: `__int64 __fastcall(__int64, __int128 **, __int16, void **, __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800028d0`
- `0x180002d40`
- `0x180003310`

## callees

- `0x180004020`
- `0x180006660`
- `0x180006678`
- `0x180006684`
- `0x180006cf0`

## import_xrefs

- `ntdll!NtCreateSection` at `0x1800041b0`
- `ntdll!NtCreateSection` at `0x1800041b0`

## string_xrefs

- `0x180004145`: `BasepSxsCreateFileStreamEx`
- `0x180004256`: `BasepSxsCreateFileStreamEx`
- `0x18000427f`: `BasepSxsCreateFileStreamEx`
- `0x180004262`: `SXS: %s() NtOpenFile(%wZ) failed. Status = 0x%x\n`
- `0x18000428a`: `SXS: %s() NtCreateSection() failed. Status = 0x%x\n`

## pseudocode

```c
__int64 __fastcall BasepSxsCreateFileStreamEx(__int64 a1, __int128 **a2, __int16 a3, void **a4, __int64 a5)
{
  ULONG v7; // eax
  NTSTATUS v8; // eax
  unsigned int v9; // ebx
  NTSTATUS v11; // eax
  __int64 v12; // rcx
  NTSTATUS Section; // eax
  __int128 v14; // xmm0
  __int64 OpenOptions; // [rsp+28h] [rbp-90h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-78h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-48h] BYREF
  __int128 FileInformation; // [rsp+80h] [rbp-38h] BYREF
  __int64 v19; // [rsp+90h] [rbp-28h]

  v19 = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  FileInformation = 0;
  if ( *a4 )
    goto LABEL_7;
  v7 = 64;
  if ( (a3 & 0x7000) == 0x7000 )
    v7 = 2112;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)a2[1];
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = v7;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v8 = NtOpenFile_0(a4, 0x120089u, &ObjectAttributes, &IoStatusBlock, 5u, 0x60u);
  v9 = v8;
  if ( v8 >= 0 )
  {
LABEL_7:
    v11 = NtQueryInformationFile_0(*a4, &IoStatusBlock, &FileInformation, 0x18u, FileStandardInformation);
    v9 = v11;
    if ( v11 >= 0 )
    {
      v12 = *((_QWORD *)&FileInformation + 1);
      if ( *((__int64 *)&FileInformation + 1) <= 0x800000 )
      {
        if ( !a4[2] )
        {
          Section = NtCreateSection(a4 + 2, 4u, 0, 0, 2u, 0x8000000u, *a4);
          v9 = Section;
          if ( Section < 0 )
          {
            DbgPrintEx_0(
              0x33u,
              0,
              "SXS: %s() NtCreateSection() failed. Status = 0x%x\n",
              "BasepSxsCreateFileStreamEx",
              Section);
            return v9;
          }
          v12 = *((_QWORD *)&FileInformation + 1);
        }
        v9 = 0;
        *(_QWORD *)(a5 + 24) = *a4;
        *(_WORD *)a5 = 257;
        v14 = **a2;
        *(_BYTE *)(a5 + 2) = 3;
        *(_OWORD *)(a5 + 8) = v14;
        *(_QWORD *)(a5 + 32) = a4[2];
        *(_QWORD *)(a5 + 40) = 0;
        *(_QWORD *)(a5 + 48) = v12;
        return v9;
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
        v11);
    }
  }
  else if ( v8 != -1073741772
         && (unsigned int)(v8 + 1073741687) > 2
         && v8 != -1073741308
         && v8 != -1073741809
         && v8 != -1072365566 )
  {
    LODWORD(OpenOptions) = v8;
    DbgPrintEx_0(
      0x33u,
      0,
      "SXS: %s() NtOpenFile(%wZ) failed. Status = 0x%x\n",
      "BasepSxsCreateFileStreamEx",
      ObjectAttributes.ObjectName,
      OpenOptions);
  }
  return v9;
}

```

## disassembly

```asm
0x180004020  mov     r11, rsp
0x180004023  mov     [r11+18h], rbx
0x180004027  push    rsi
0x180004028  push    rdi
0x180004029  push    r14
0x18000402b  sub     rsp, 0A0h
0x180004032  mov     rax, cs:__security_cookie
0x180004039  xor     rax, rsp
0x18000403c  mov     [rsp+0B8h+var_20], rax
0x180004044  mov     r14, [rsp+0B8h+arg_20]
0x18000404c  xorps   xmm0, xmm0
0x18000404f  xor     eax, eax
0x180004051  xorps   xmm1, xmm1
0x180004054  mov     rsi, r9
0x180004057  mov     rdi, rdx
0x18000405a  movups  xmmword ptr [rsp+0B8h+ObjectAttributes.ObjectName], xmm0
0x18000405f  mov     [r11-28h], rax
0x180004063  movups  xmmword ptr [rsp+0B8h+ObjectAttributes+1Ch], xmm0
0x180004068  movups  xmmword ptr [rsp+0B8h+ObjectAttributes.Length], xmm0
0x18000406d  movups  xmmword ptr [rsp+0B8h+IoStatusBlock], xmm0
0x180004072  movups  xmmword ptr [r11-38h], xmm1
0x180004077  cmp     [r9], rax
0x18000407a  jnz     loc_18000411C
0x180004080  mov     rcx, [rdx+8]
0x180004084  and     r8d, 7000h
0x18000408b  mov     eax, 40h ; '@'
0x180004090  cmp     r8d, 7000h
0x180004097  jz      loc_180004218
0x18000409d  mov     [rsp+0B8h+ObjectAttributes.ObjectName], rcx
0x1800040a2  lea     r9, [rsp+0B8h+IoStatusBlock]; IoStatusBlock
0x1800040a7  mov     rcx, rsi; FileHandle
0x1800040aa  mov     dword ptr [rsp+0B8h+OpenOptions], 60h ; '`'; OpenOptions
0x1800040b2  lea     r8, [rsp+0B8h+ObjectAttributes]; ObjectAttributes
0x1800040b7  mov     [rsp+0B8h+ObjectAttributes.Length], 30h ; '0'
0x1800040bf  mov     edx, 120089h; DesiredAccess
0x1800040c4  mov     [rsp+0B8h+ObjectAttributes.RootDirectory], 0
0x1800040cd  mov     [rsp+0B8h+ObjectAttributes.Attributes], eax
0x1800040d1  movdqu  xmmword ptr [rsp+0B8h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800040d7  mov     [rsp+0B8h+ShareAccess], 5; ShareAccess
0x1800040df  call    NtOpenFile_0
0x1800040e4  mov     ebx, eax
0x1800040e6  test    eax, eax
0x1800040e8  jns     short loc_18000411C
0x1800040ea  cmp     eax, 0C0000034h
0x1800040ef  jnz     loc_180004222
0x1800040f5  mov     eax, ebx
0x1800040f7  mov     rcx, [rsp+0B8h+var_20]
0x1800040ff  xor     rcx, rsp; StackCookie
0x180004102  call    __security_check_cookie
0x180004107  mov     rbx, [rsp+0B8h+arg_10]
0x18000410f  add     rsp, 0A0h
0x180004116  pop     r14
0x180004118  pop     rdi
0x180004119  pop     rsi
0x18000411a  retn
0x18000411c  mov     rcx, [rsi]; FileHandle
0x18000411f  lea     r8, [rsp+0B8h+FileInformation]; FileInformation
0x180004127  mov     r9d, 18h; Length
0x18000412d  mov     [rsp+0B8h+ShareAccess], 5; FileInformationClass
0x180004135  lea     rdx, [rsp+0B8h+IoStatusBlock]; IoStatusBlock
0x18000413a  call    NtQueryInformationFile_0
0x18000413f  mov     ebx, eax
0x180004141  test    eax, eax
0x180004143  jns     short loc_180004165
0x180004145  lea     r9, aBasepsxscreate; "BasepSxsCreateFileStreamEx"
0x18000414c  mov     [rsp+0B8h+ShareAccess], eax
0x180004150  lea     r8, aSxsSNtqueryinf; "SXS: %s() NtQueryInformationFile failed"...
0x180004157  xor     edx, edx; Level
0x180004159  mov     ecx, 33h ; '3'; ComponentId
0x18000415e  call    DbgPrintEx_0
0x180004163  jmp     short loc_1800040F5
0x180004165  mov     rcx, [rsp+0B8h+var_30]
0x18000416d  cmp     rcx, 800000h
0x180004174  jg      loc_18000420E
0x18000417a  cmp     qword ptr [rsi+10h], 0
0x18000417f  mov     [rsp+0B8h+arg_0], r15
0x180004187  jnz     short loc_1800041CE
0x180004189  mov     rax, [rsi]
0x18000418c  lea     rcx, [rsi+10h]; SectionHandle
0x180004190  mov     [rsp+0B8h+FileHandle], rax; FileHandle
0x180004195  xor     r9d, r9d; MaximumSize
0x180004198  mov     dword ptr [rsp+0B8h+OpenOptions], 8000000h; AllocationAttributes
0x1800041a0  xor     r8d, r8d; ObjectAttributes
0x1800041a3  mov     edx, 4; DesiredAccess
0x1800041a8  mov     [rsp+0B8h+ShareAccess], 2; SectionPageProtection
0x1800041b0  call    cs:__imp_NtCreateSection
0x1800041b7  nop     dword ptr [rax+rax+00h]
0x1800041bc  mov     ebx, eax
0x1800041be  test    eax, eax
0x1800041c0  js      loc_18000427F
0x1800041c6  mov     rcx, [rsp+0B8h+var_30]
0x1800041ce  mov     rax, [rsi]
0x1800041d1  xor     ebx, ebx
0x1800041d3  mov     [r14+18h], rax
0x1800041d7  mov     word ptr [r14], 101h
0x1800041dd  mov     rax, [rdi]
0x1800041e0  movups  xmm0, xmmword ptr [rax]
0x1800041e3  mov     byte ptr [r14+2], 3
0x1800041e8  movups  xmmword ptr [r14+8], xmm0
0x1800041ed  mov     rax, [rsi+10h]
0x1800041f1  mov     [r14+20h], rax
0x1800041f5  mov     qword ptr [r14+28h], 0
0x1800041fd  mov     [r14+30h], rcx
0x180004201  mov     r15, [rsp+0B8h+arg_0]
0x180004209  jmp     loc_1800040F5
0x18000420e  mov     ebx, 0C0150022h
0x180004213  jmp     loc_1800040F5
0x180004218  mov     eax, 840h
0x18000421d  jmp     loc_18000409D
0x180004222  lea     ecx, [rax+3FFFFF77h]
0x180004228  cmp     ecx, 2
0x18000422b  jbe     loc_1800040F5
0x180004231  cmp     eax, 0C0000204h
0x180004236  jz      loc_1800040F5
0x18000423c  cmp     eax, 0C000000Fh
0x180004241  jz      loc_1800040F5
0x180004247  cmp     eax, 0C0150002h
0x18000424c  jz      loc_1800040F5
0x180004252  mov     dword ptr [rsp+0B8h+OpenOptions], eax
0x180004256  lea     r9, aBasepsxscreate; "BasepSxsCreateFileStreamEx"
0x18000425d  mov     rax, [rsp+0B8h+ObjectAttributes.ObjectName]
0x180004262  lea     r8, aSxsSNtopenfile; "SXS: %s() NtOpenFile(%wZ) failed. Statu"...
0x180004269  xor     edx, edx; Level
0x18000426b  mov     qword ptr [rsp+0B8h+ShareAccess], rax
0x180004270  mov     ecx, 33h ; '3'; ComponentId
0x180004275  call    DbgPrintEx_0
0x18000427a  jmp     loc_1800040F5
0x18000427f  lea     r9, aBasepsxscreate; "BasepSxsCreateFileStreamEx"
0x180004286  mov     [rsp+0B8h+ShareAccess], eax
0x18000428a  lea     r8, aSxsSNtcreatese; "SXS: %s() NtCreateSection() failed. Sta"...
0x180004291  xor     edx, edx; Level
0x180004293  mov     ecx, 33h ; '3'; ComponentId
0x180004298  call    DbgPrintEx_0
0x18000429d  jmp     loc_180004201
```
