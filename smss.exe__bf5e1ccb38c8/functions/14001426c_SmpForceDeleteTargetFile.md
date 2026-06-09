# SmpForceDeleteTargetFile

- ea: `0x14001426c`
- end: `0x1400143aa`
- name: `SmpForceDeleteTargetFile`
- size: `318`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000e2e8`
- `0x140015ae8`

## callees

- `0x1400140c8`
- `0x14001426c`
- `0x1400158e4`
- `0x14001598c`
- `0x1400168b8`
- `0x14001cc40`

## import_xrefs

- `ntdll!NtClose` at `0x14001437e`
- `ntdll!NtClose` at `0x14001437e`
- `ntdll!NtQueryAttributesFile` at `0x140014328`
- `ntdll!NtQueryAttributesFile` at `0x140014328`

## pseudocode

```c
__int64 __fastcall SmpForceDeleteTargetFile(struct _UNICODE_STRING *a1, char a2)
{
  int v4; // edi
  NTSTATUS v5; // ebx
  HANDLE v6; // rcx
  HANDLE Handle; // [rsp+30h] [rbp-29h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-21h] BYREF
  _FILE_BASIC_INFORMATION FileInformation; // [rsp+68h] [rbp+Fh] BYREF

  ObjectAttributes.ObjectName = a1;
  Handle = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  v4 = 0;
  memset(&FileInformation, 0, sizeof(FileInformation));
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v5 = SmpOpenTargetFile(&Handle, 0x110100u, &ObjectAttributes, 0, 3u);
  if ( v5 >= 0 )
  {
    if ( a2 != 1 || SmpPathCanBeTrustedIsNotARedirection(Handle, &a1->Length, 0) )
    {
      v5 = SmpDeleteTargetFile(Handle);
      if ( v5 < 0
        && NtQueryAttributesFile(&ObjectAttributes, &FileInformation) >= 0
        && (FileInformation.FileAttributes & 1) != 0 )
      {
        v5 = SmpSetTargetAttributes(Handle, FileInformation.FileAttributes & 0xFFFFFFFE);
        if ( v5 >= 0 )
        {
          v4 = 1;
          v5 = SmpDeleteTargetFile(Handle);
          if ( v5 >= 0 )
          {
            v4 = 0;
            v5 = 0;
          }
        }
      }
    }
    else
    {
      v5 = -1073740533;
    }
  }
  v6 = Handle;
  if ( Handle )
  {
    if ( v4 )
    {
      SmpSetTargetAttributes(Handle, FileInformation.FileAttributes);
      v6 = Handle;
    }
    NtClose(v6);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14001426c  mov     [rsp-8+arg_8], rbx
0x140014271  mov     [rsp-8+arg_10], rsi
0x140014276  push    rbp
0x140014277  push    rdi
0x140014278  push    r14
0x14001427a  lea     rbp, [rsp-47h]
0x14001427f  sub     rsp, 0A0h
0x140014286  mov     rax, cs:__security_cookie
0x14001428d  xor     rax, rsp
0x140014290  mov     [rbp+57h+var_20], rax
0x140014294  xor     eax, eax
0x140014296  mov     [rbp+57h+ObjectAttributes.ObjectName], rcx
0x14001429a  xorps   xmm0, xmm0
0x14001429d  mov     [rbp+57h+Handle], rax
0x1400142a1  mov     sil, dl
0x1400142a4  mov     qword ptr [rbp+57h+FileInformation.FileAttributes], rax
0x1400142a8  mov     r14, rcx
0x1400142ab  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x1400142af  mov     edx, 110100h; int
0x1400142b4  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400142bc  lea     rcx, [rbp+57h+Handle]; int
0x1400142c0  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1400142c8  xor     r9d, r9d; int
0x1400142cb  mov     [rsp+0B0h+var_90], 3; ULONG
0x1400142d3  lea     r8, [rbp+57h+ObjectAttributes]; int
0x1400142d7  xor     edi, edi
0x1400142d9  movups  xmmword ptr [rbp+57h+FileInformation.CreationTime], xmm0
0x1400142dd  movups  xmmword ptr [rbp+57h+FileInformation.LastWriteTime], xmm0
0x1400142e1  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400142e6  call    SmpOpenTargetFile
0x1400142eb  mov     ebx, eax
0x1400142ed  test    eax, eax
0x1400142ef  js      short loc_140014365
0x1400142f1  cmp     sil, 1
0x1400142f5  jnz     short loc_140014311
0x1400142f7  mov     rcx, [rbp+57h+Handle]
0x1400142fb  xor     r8d, r8d
0x1400142fe  mov     rdx, r14
0x140014301  call    SmpPathCanBeTrustedIsNotARedirection
0x140014306  test    al, al
0x140014308  jnz     short loc_140014311
0x14001430a  mov     ebx, 0C000050Bh
0x14001430f  jmp     short loc_140014365
0x140014311  mov     rcx, [rbp+57h+Handle]
0x140014315  call    SmpDeleteTargetFile
0x14001431a  mov     ebx, eax
0x14001431c  test    eax, eax
0x14001431e  jns     short loc_140014365
0x140014320  lea     rdx, [rbp+57h+FileInformation]; FileInformation
0x140014324  lea     rcx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140014328  call    cs:__imp_NtQueryAttributesFile
0x14001432e  test    eax, eax
0x140014330  js      short loc_140014365
0x140014332  mov     rdx, qword ptr [rbp+57h+FileInformation.FileAttributes]
0x140014336  test    dl, 1
0x140014339  jz      short loc_140014365
0x14001433b  mov     rcx, [rbp+57h+Handle]
0x14001433f  and     edx, 0FFFFFFFEh
0x140014342  call    SmpSetTargetAttributes
0x140014347  mov     ebx, eax
0x140014349  test    eax, eax
0x14001434b  js      short loc_140014365
0x14001434d  mov     rcx, [rbp+57h+Handle]
0x140014351  mov     edi, 1
0x140014356  call    SmpDeleteTargetFile
0x14001435b  mov     ebx, eax
0x14001435d  test    eax, eax
0x14001435f  js      short loc_140014365
0x140014361  xor     edi, edi
0x140014363  xor     ebx, ebx
0x140014365  mov     rcx, [rbp+57h+Handle]
0x140014369  test    rcx, rcx
0x14001436c  jz      short loc_140014384
0x14001436e  test    edi, edi
0x140014370  jz      short loc_14001437E
0x140014372  mov     edx, [rbp+57h+FileInformation.FileAttributes]
0x140014375  call    SmpSetTargetAttributes
0x14001437a  mov     rcx, [rbp+57h+Handle]; Handle
0x14001437e  call    cs:__imp_NtClose
0x140014384  mov     eax, ebx
0x140014386  mov     rcx, [rbp+57h+var_20]
0x14001438a  xor     rcx, rsp; StackCookie
0x14001438d  call    __security_check_cookie
0x140014392  lea     r11, [rsp+0B0h+var_10]
0x14001439a  mov     rbx, [r11+28h]
0x14001439e  mov     rsi, [r11+30h]
0x1400143a2  mov     rsp, r11
0x1400143a5  pop     r14
0x1400143a7  pop     rdi
0x1400143a8  pop     rbp
0x1400143a9  retn
```
