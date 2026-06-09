# SdbUnregisterDatabase

- ea: `0x140018514`
- end: `0x1400186d1`
- name: `SdbUnregisterDatabase`
- size: `445`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140004df8`

## callees

- `0x14000d854`
- `0x14000fc40`
- `0x14001008c`
- `0x140018514`
- `0x14002e3e2`
- `0x14002e420`

## import_xrefs

- `ntdll!NtDeleteKey` at `0x140018686`
- `ntdll!NtDeleteKey` at `0x140018686`
- `ntdll!NtClose` at `0x1400186ae`
- `ntdll!NtClose` at `0x1400186ae`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1400185ed`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1400185ed`
- `ntdll!RtlAppendUnicodeToString` at `0x1400185cb`
- `ntdll!RtlAppendUnicodeToString` at `0x1400185dd`
- `ntdll!RtlAppendUnicodeToString` at `0x1400185cb`
- `ntdll!RtlAppendUnicodeToString` at `0x1400185dd`
- `ntdll!NtOpenKey` at `0x140018634`
- `ntdll!NtOpenKey` at `0x140018634`

## string_xrefs

- `0x140018653`: `Failed to open key "%ws" [%x]`
- `0x1400185ba`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\InstalledSDB`
- `0x140018690`: `Failed to delete key "%ws" [%x]`

## pseudocode

```c
__int64 __fastcall SdbUnregisterDatabase(__int64 a1)
{
  unsigned int v2; // edi
  int v3; // eax
  NTSTATUS v4; // eax
  const char *v5; // r9
  __int64 v6; // r8
  struct _UNICODE_STRING Destination; // [rsp+30h] [rbp-D0h] BYREF
  void *KeyHandle; // [rsp+40h] [rbp-C0h] BYREF
  UNICODE_STRING Source; // [rsp+48h] [rbp-B8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v12[528]; // [rsp+90h] [rbp-70h] BYREF

  Destination = 0;
  v2 = 0;
  Source = 0;
  memset_0(v12, 0, 0x208u);
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  v3 = AslGuidToString_UStr(&Source, a1);
  if ( v3 < 0 )
  {
    AslLogCallPrintf(1, "SdbUnregisterDatabase", 1259, "Cannot convert guid to unicode string [%x]", v3);
    goto LABEL_12;
  }
  *(_DWORD *)&Destination.Length = 34078720;
  Destination.Buffer = (PWSTR)v12;
  RtlAppendUnicodeToString(
    &Destination,
    L"\\Registry\\Machine\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\InstalledSDB");
  RtlAppendUnicodeToString(&Destination, L"\\");
  RtlAppendUnicodeStringToString(&Destination, &Source);
  AslAnsiStringFree(&Source);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &Destination;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = NtOpenKey(&KeyHandle, 0x10100u, &ObjectAttributes);
  if ( v4 < 0 && v4 != -1073741766 && v4 != -1073741772 && v4 != -1073741620 )
  {
    v5 = "Failed to open key \"%ws\" [%x]";
    v6 = 1288;
LABEL_8:
    AslLogCallPrintf(1, "SdbUnregisterDatabase", v6, v5, Destination.Buffer, v4);
    goto LABEL_12;
  }
  v4 = NtDeleteKey(KeyHandle);
  if ( v4 < 0 )
  {
    v5 = "Failed to delete key \"%ws\" [%x]";
    v6 = 1298;
    goto LABEL_8;
  }
  v2 = 1;
LABEL_12:
  if ( KeyHandle )
    NtClose(KeyHandle);
  return v2;
}

```

## disassembly

```asm
0x140018514  push    rbp
0x140018516  push    rbx
0x140018517  push    rsi
0x140018518  push    rdi
0x140018519  lea     rbp, [rsp-1B8h]
0x140018521  sub     rsp, 2B8h
0x140018528  mov     rax, cs:__security_cookie
0x14001852f  xor     rax, rsp
0x140018532  mov     [rbp+1D0h+var_30], rax
0x140018539  mov     rbx, rcx
0x14001853c  xorps   xmm0, xmm0
0x14001853f  xorps   xmm1, xmm1
0x140018542  lea     rcx, [rbp+1D0h+var_240]; void *
0x140018546  xor     edx, edx; Val
0x140018548  mov     r8d, 208h; Size
0x14001854e  movups  xmmword ptr [rsp+2D0h+Destination.Length], xmm0
0x140018553  xor     edi, edi
0x140018555  movups  xmmword ptr [rsp+2D0h+Source.Length], xmm1
0x14001855a  call    memset_0
0x14001855f  xorps   xmm0, xmm0
0x140018562  mov     [rsp+2D0h+KeyHandle], rdi
0x140018567  movups  xmmword ptr [rsp+2D0h+ObjectAttributes.ObjectName], xmm0
0x14001856c  xor     eax, eax
0x14001856e  lea     rcx, [rsp+2D0h+Source]
0x140018573  mov     rdx, rbx
0x140018576  movups  xmmword ptr [rsp+2D0h+ObjectAttributes+1Ch], xmm0
0x14001857b  movups  xmmword ptr [rsp+2D0h+ObjectAttributes.Length], xmm0
0x140018580  call    AslGuidToString_UStr
0x140018585  test    eax, eax
0x140018587  jns     short loc_1400185AE
0x140018589  lea     r9, aCannotConvertG; "Cannot convert guid to unicode string ["...
0x140018590  mov     dword ptr [rsp+2D0h+var_2B0], eax
0x140018594  mov     r8d, 4EBh
0x14001859a  lea     rdx, aSdbunregisterd; "SdbUnregisterDatabase"
0x1400185a1  lea     ecx, [rdi+1]
0x1400185a4  call    AslLogCallPrintf
0x1400185a9  jmp     loc_1400186A4
0x1400185ae  lea     rax, [rbp+1D0h+var_240]
0x1400185b2  mov     dword ptr [rsp+2D0h+Destination.Length], 2080000h
0x1400185ba  lea     rdx, aRegistryMachin_2; "\\Registry\\Machine\\Software\\Microsof"...
0x1400185c1  mov     [rsp+2D0h+Destination.Buffer], rax
0x1400185c6  lea     rcx, [rsp+2D0h+Destination]; Destination
0x1400185cb  call    cs:__imp_RtlAppendUnicodeToString
0x1400185d1  lea     rdx, asc_1400326D0; "\\"
0x1400185d8  lea     rcx, [rsp+2D0h+Destination]; Destination
0x1400185dd  call    cs:__imp_RtlAppendUnicodeToString
0x1400185e3  lea     rdx, [rsp+2D0h+Source]; Source
0x1400185e8  lea     rcx, [rsp+2D0h+Destination]; Destination
0x1400185ed  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400185f3  lea     rcx, [rsp+2D0h+Source]
0x1400185f8  call    AslAnsiStringFree
0x1400185fd  lea     rax, [rsp+2D0h+Destination]
0x140018602  mov     [rsp+2D0h+ObjectAttributes.Length], 30h ; '0'
0x14001860a  xorps   xmm0, xmm0
0x14001860d  mov     [rsp+2D0h+ObjectAttributes.ObjectName], rax
0x140018612  lea     r8, [rsp+2D0h+ObjectAttributes]; ObjectAttributes
0x140018617  mov     [rsp+2D0h+ObjectAttributes.RootDirectory], rdi
0x14001861c  mov     edx, 10100h; DesiredAccess
0x140018621  mov     [rsp+2D0h+ObjectAttributes.Attributes], 40h ; '@'
0x140018629  lea     rcx, [rsp+2D0h+KeyHandle]; KeyHandle
0x14001862e  movdqu  xmmword ptr [rsp+2D0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140018634  call    cs:__imp_NtOpenKey
0x14001863a  test    eax, eax
0x14001863c  jns     short loc_140018681
0x14001863e  cmp     eax, 0C000003Ah
0x140018643  jz      short loc_140018681
0x140018645  cmp     eax, 0C0000034h
0x14001864a  jz      short loc_140018681
0x14001864c  cmp     eax, 0C00000CCh
0x140018651  jz      short loc_140018681
0x140018653  lea     r9, aFailedToOpenKe; "Failed to open key \"%ws\" [%x]"
0x14001865a  mov     r8d, 508h
0x140018660  mov     [rsp+2D0h+var_2A8], eax
0x140018664  lea     rdx, aSdbunregisterd; "SdbUnregisterDatabase"
0x14001866b  mov     rax, [rsp+2D0h+Destination.Buffer]
0x140018670  mov     ecx, 1
0x140018675  mov     [rsp+2D0h+var_2B0], rax
0x14001867a  call    AslLogCallPrintf
0x14001867f  jmp     short loc_1400186A4
0x140018681  mov     rcx, [rsp+2D0h+KeyHandle]; KeyHandle
0x140018686  call    cs:__imp_NtDeleteKey
0x14001868c  test    eax, eax
0x14001868e  jns     short loc_14001869F
0x140018690  lea     r9, aFailedToDelete; "Failed to delete key \"%ws\" [%x]"
0x140018697  mov     r8d, 512h
0x14001869d  jmp     short loc_140018660
0x14001869f  mov     edi, 1
0x1400186a4  mov     rcx, [rsp+2D0h+KeyHandle]; Handle
0x1400186a9  test    rcx, rcx
0x1400186ac  jz      short loc_1400186B4
0x1400186ae  call    cs:__imp_NtClose
0x1400186b4  mov     eax, edi
0x1400186b6  mov     rcx, [rbp+1D0h+var_30]
0x1400186bd  xor     rcx, rsp; StackCookie
0x1400186c0  call    __security_check_cookie
0x1400186c5  add     rsp, 2B8h
0x1400186cc  pop     rdi
0x1400186cd  pop     rsi
0x1400186ce  pop     rbx
0x1400186cf  pop     rbp
0x1400186d0  retn
```
