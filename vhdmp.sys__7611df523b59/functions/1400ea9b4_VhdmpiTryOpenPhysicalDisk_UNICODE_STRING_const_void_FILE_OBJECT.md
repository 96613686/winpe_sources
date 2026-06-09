# VhdmpiTryOpenPhysicalDisk(_UNICODE_STRING const *,void * *,_FILE_OBJECT * *)

- ea: `0x1400ea9b4`
- end: `0x1400eac03`
- name: `?VhdmpiTryOpenPhysicalDisk@@YAJPEBU_UNICODE_STRING@@PEAPEAXPEAPEAU_FILE_OBJECT@@@Z`
- size: `591`
- prototype: `__int64 __fastcall(const struct _UNICODE_STRING *, void **, struct _FILE_OBJECT **)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400a1a6c`

## callees

- `0x140020874`
- `0x140023560`
- `0x140035e94`
- `0x14009e1c0`
- `0x1400a3b74`
- `0x1400ea9b4`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400eab1c`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400eab1c`
- `ntoskrnl!ObfDereferenceObject` at `0x1400eabbe`
- `ntoskrnl!ObfDereferenceObject` at `0x1400eabbe`
- `ntoskrnl!ZwClose` at `0x1400eabd3`
- `ntoskrnl!ZwClose` at `0x1400eabd3`
- `ntoskrnl!ZwOpenFile` at `0x1400eaaab`
- `ntoskrnl!ZwOpenFile` at `0x1400eaaab`

## string_xrefs

- `0x1400eaa4b`: `VhdmpiTryOpenPhysicalDisk`
- `0x1400eab6b`: `VhdmpiTryOpenPhysicalDisk`
- `0x1400eaa36`: `Could not get NT path of source (0x%08x)`
- `0x1400eaaea`: `Invalid source specified; no handle could be opened RO (0x%08x)`

## pseudocode

```c
__int64 __fastcall VhdmpiTryOpenPhysicalDisk(struct _UNICODE_STRING *a1, void **a2, struct _FILE_OBJECT **a3)
{
  __int64 v5; // rdx
  NTSTATUS IsPhysicalDisk; // ebx
  __int64 v7; // r8
  unsigned __int16 v8; // cx
  char *v9; // rax
  NTSTATUS v10; // eax
  struct _FILE_OBJECT *v11; // rdi
  struct _FILE_OBJECT *v12; // rcx
  ULONG OpenOptions[2]; // [rsp+28h] [rbp-21h]
  void *FileHandle; // [rsp+30h] [rbp-19h] BYREF
  PVOID Object; // [rsp+38h] [rbp-11h] BYREF
  struct _UNICODE_STRING v17; // [rsp+40h] [rbp-9h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp+7h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+17h] BYREF
  unsigned __int8 v20; // [rsp+C8h] [rbp+7Fh] BYREF

  v20 = 0;
  FileHandle = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v17 = 0;
  IsPhysicalDisk = VhdmpiCreateNtFilePath(a1, &v17);
  if ( IsPhysicalDisk >= 0 )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 1600;
    ObjectAttributes.ObjectName = &v17;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    IsPhysicalDisk = ZwOpenFile(&FileHandle, 0x80000000, &ObjectAttributes, &IoStatusBlock, 3u, 0x48u);
    if ( IsPhysicalDisk >= 0 )
    {
      Object = 0;
      v10 = ObReferenceObjectByHandle(FileHandle, 0x80000000, 0, 0, &Object, 0);
      v11 = (struct _FILE_OBJECT *)Object;
      IsPhysicalDisk = v10;
      if ( v10 >= 0 )
      {
        IsPhysicalDisk = VhdmpiIsPhysicalDisk((PFILE_OBJECT)Object, &v20);
        if ( IsPhysicalDisk >= 0 )
        {
          if ( v20 )
          {
            v12 = v11;
            v11 = 0;
            *a2 = FileHandle;
            FileHandle = 0;
          }
          else
          {
            *a2 = 0;
            v12 = 0;
          }
          *a3 = v12;
          IsPhysicalDisk = 0;
        }
      }
      else if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
      {
        TraceEvents(
          "VhdmpiTryOpenPhysicalDisk",
          0x13Au,
          v5 - 6,
          v5,
          "Invalid source specified; no object could be referenced (0x%08x)",
          IsPhysicalDisk);
      }
      if ( v11 )
        ObfDereferenceObject(v11);
    }
    else if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
    {
      v8 = 298;
      v9 = "Invalid source specified; no handle could be opened RO (0x%08x)";
      goto LABEL_5;
    }
  }
  else if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
  {
    v8 = 269;
    v9 = "Could not get NT path of source (0x%08x)";
LABEL_5:
    OpenOptions[0] = IsPhysicalDisk;
    TraceEvents("VhdmpiTryOpenPhysicalDisk", v8, 2u, v5, v9, *(_QWORD *)OpenOptions);
  }
  if ( FileHandle )
    ZwClose(FileHandle);
  VhdmpiFreeFilePath(&v17, v5, v7);
  return (unsigned int)IsPhysicalDisk;
}

```

## disassembly

```asm
0x1400ea9b4  mov     [rsp-8+arg_0], rbx
0x1400ea9b9  mov     [rsp-8+arg_8], rsi
0x1400ea9be  push    rbp
0x1400ea9bf  push    rdi
0x1400ea9c0  push    r14
0x1400ea9c2  lea     rbp, [rsp-47h]
0x1400ea9c7  sub     rsp, 90h
0x1400ea9ce  xorps   xmm1, xmm1
0x1400ea9d1  mov     [rbp+57h+arg_18], 0
0x1400ea9d5  xorps   xmm0, xmm0
0x1400ea9d8  mov     [rbp+57h+FileHandle], 0
0x1400ea9e0  mov     rsi, rdx
0x1400ea9e3  mov     r14, r8
0x1400ea9e6  lea     rdx, [rbp+57h+var_60]; struct _UNICODE_STRING *
0x1400ea9ea  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1400ea9ee  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x1400ea9f2  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x1400ea9f6  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x1400ea9fa  movups  xmmword ptr [rbp+57h+var_60.Length], xmm0
0x1400ea9fe  call    VhdmpiCreateNtFilePath
0x1400eaa03  mov     ebx, eax
0x1400eaa05  test    eax, eax
0x1400eaa07  jns     short loc_1400EAA62
0x1400eaa09  mov     ecx, cs:dword_140087708
0x1400eaa0f  cmp     ecx, 2
0x1400eaa12  jbe     loc_1400EABCA
0x1400eaa18  mov     edx, 8
0x1400eaa1d  lea     rcx, dword_140087708
0x1400eaa24  call    _tlgKeywordOn
0x1400eaa29  test    al, al
0x1400eaa2b  jz      loc_1400EABCA
0x1400eaa31  mov     ecx, 10Dh
0x1400eaa36  lea     rax, aCouldNotGetNtP; "Could not get NT path of source (0x%08x"...
0x1400eaa3d  mov     r9d, edx; int
0x1400eaa40  mov     [rsp+0A0h+OpenOptions], ebx; char
0x1400eaa44  mov     edx, ecx; int
0x1400eaa46  mov     qword ptr [rsp+0A0h+ShareAccess], rax; char *
0x1400eaa4b  lea     rcx, aVhdmpitryopenp; "VhdmpiTryOpenPhysicalDisk"
0x1400eaa52  mov     r8d, 2; int
0x1400eaa58  call    TraceEvents
0x1400eaa5d  jmp     loc_1400EABCA
0x1400eaa62  lea     rax, [rbp+57h+var_60]
0x1400eaa66  mov     [rsp+0A0h+OpenOptions], 48h ; 'H'; OpenOptions
0x1400eaa6e  xorps   xmm0, xmm0
0x1400eaa71  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400eaa78  mov     edi, 80000000h
0x1400eaa7d  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1400eaa85  mov     edx, edi; DesiredAccess
0x1400eaa87  mov     [rbp+57h+ObjectAttributes.Attributes], 640h
0x1400eaa8e  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1400eaa92  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400eaa96  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400eaa9a  mov     [rsp+0A0h+ShareAccess], 3; ShareAccess
0x1400eaaa2  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1400eaaa6  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400eaaab  call    cs:__imp_ZwOpenFile
0x1400eaab2  nop     dword ptr [rax+rax+00h]
0x1400eaab7  mov     ebx, eax
0x1400eaab9  test    eax, eax
0x1400eaabb  jns     short loc_1400EAAF6
0x1400eaabd  mov     eax, cs:dword_140087708
0x1400eaac3  cmp     eax, 2
0x1400eaac6  jbe     loc_1400EABCA
0x1400eaacc  mov     edx, 8
0x1400eaad1  lea     rcx, dword_140087708
0x1400eaad8  call    _tlgKeywordOn
0x1400eaadd  test    al, al
0x1400eaadf  jz      loc_1400EABCA
0x1400eaae5  mov     ecx, 12Ah
0x1400eaaea  lea     rax, aInvalidSourceS_0; "Invalid source specified; no handle cou"...
0x1400eaaf1  jmp     loc_1400EAA3D
0x1400eaaf6  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1400eaafa  lea     rax, [rbp+57h+Object]
0x1400eaafe  mov     qword ptr [rsp+0A0h+OpenOptions], 0; HandleInformation
0x1400eab07  xor     r9d, r9d; AccessMode
0x1400eab0a  xor     r8d, r8d; ObjectType
0x1400eab0d  mov     qword ptr [rsp+0A0h+ShareAccess], rax; Object
0x1400eab12  mov     edx, edi; DesiredAccess
0x1400eab14  mov     [rbp+57h+Object], 0
0x1400eab1c  call    cs:__imp_ObReferenceObjectByHandle
0x1400eab23  nop     dword ptr [rax+rax+00h]
0x1400eab28  mov     rdi, [rbp+57h+Object]
0x1400eab2c  mov     ebx, eax
0x1400eab2e  test    eax, eax
0x1400eab30  jns     short loc_1400EAB7E
0x1400eab32  mov     eax, cs:dword_140087708
0x1400eab38  cmp     eax, 2
0x1400eab3b  jbe     short loc_1400EABB6
0x1400eab3d  mov     edx, 8
0x1400eab42  lea     rcx, dword_140087708
0x1400eab49  call    _tlgKeywordOn
0x1400eab4e  test    al, al
0x1400eab50  jz      short loc_1400EABB6
0x1400eab52  mov     ecx, 13Ah
0x1400eab57  mov     [rsp+0A0h+OpenOptions], ebx; char
0x1400eab5b  mov     r9d, edx; int
0x1400eab5e  lea     r8d, [rdx-6]; int
0x1400eab62  mov     edx, ecx; int
0x1400eab64  lea     rax, aInvalidSourceS; "Invalid source specified; no object cou"...
0x1400eab6b  lea     rcx, aVhdmpitryopenp; "VhdmpiTryOpenPhysicalDisk"
0x1400eab72  mov     qword ptr [rsp+0A0h+ShareAccess], rax; char *
0x1400eab77  call    TraceEvents
0x1400eab7c  jmp     short loc_1400EABB6
0x1400eab7e  lea     rdx, [rbp+57h+arg_18]; unsigned __int8 *
0x1400eab82  mov     rcx, rdi; FileObject
0x1400eab85  call    ?VhdmpiIsPhysicalDisk@@YAJPEAU_FILE_OBJECT@@PEAE@Z; VhdmpiIsPhysicalDisk(_FILE_OBJECT *,uchar *)
0x1400eab8a  mov     ebx, eax
0x1400eab8c  test    eax, eax
0x1400eab8e  js      short loc_1400EABB6
0x1400eab90  cmp     [rbp+57h+arg_18], 0
0x1400eab94  jz      short loc_1400EABA8
0x1400eab96  mov     rax, [rbp+57h+FileHandle]
0x1400eab9a  mov     rcx, rdi
0x1400eab9d  xor     edi, edi
0x1400eab9f  mov     [rsi], rax
0x1400eaba2  mov     [rbp+57h+FileHandle], rdi
0x1400eaba6  jmp     short loc_1400EABB1
0x1400eaba8  mov     qword ptr [rsi], 0
0x1400eabaf  xor     ecx, ecx
0x1400eabb1  mov     [r14], rcx
0x1400eabb4  xor     ebx, ebx
0x1400eabb6  test    rdi, rdi
0x1400eabb9  jz      short loc_1400EABCA
0x1400eabbb  mov     rcx, rdi; Object
0x1400eabbe  call    cs:__imp_ObfDereferenceObject
0x1400eabc5  nop     dword ptr [rax+rax+00h]
0x1400eabca  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1400eabce  test    rcx, rcx
0x1400eabd1  jz      short loc_1400EABDF
0x1400eabd3  call    cs:__imp_ZwClose
0x1400eabda  nop     dword ptr [rax+rax+00h]
0x1400eabdf  lea     rcx, [rbp+57h+var_60]
0x1400eabe3  call    VhdmpiFreeFilePath
0x1400eabe8  lea     r11, [rsp+0A0h+var_10]
0x1400eabf0  mov     eax, ebx
0x1400eabf2  mov     rbx, [r11+20h]
0x1400eabf6  mov     rsi, [r11+28h]
0x1400eabfa  mov     rsp, r11
0x1400eabfd  pop     r14
0x1400eabff  pop     rdi
0x1400eac00  pop     rbp
0x1400eac01  retn
```
