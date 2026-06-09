# VhdmpiTryOpenPhysicalDisk(_UNICODE_STRING const *,void * *,_FILE_OBJECT * *)

- ea: `0x1400ea944`
- end: `0x1400eab93`
- name: `?VhdmpiTryOpenPhysicalDisk@@YAJPEBU_UNICODE_STRING@@PEAPEAXPEAPEAU_FILE_OBJECT@@@Z`
- size: `591`
- prototype: `__int64 __fastcall(const struct _UNICODE_STRING *, void **, struct _FILE_OBJECT **)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400a1a6c`

## callees

- `0x140020c94`
- `0x140023980`
- `0x140036284`
- `0x14009e1c0`
- `0x1400a3b74`
- `0x1400ea944`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400eaaac`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400eaaac`
- `ntoskrnl!ObfDereferenceObject` at `0x1400eab4e`
- `ntoskrnl!ObfDereferenceObject` at `0x1400eab4e`
- `ntoskrnl!ZwClose` at `0x1400eab63`
- `ntoskrnl!ZwClose` at `0x1400eab63`
- `ntoskrnl!ZwOpenFile` at `0x1400eaa3b`
- `ntoskrnl!ZwOpenFile` at `0x1400eaa3b`

## string_xrefs

- `0x1400ea9c6`: `Could not get NT path of source (0x%08x)`
- `0x1400eaa7a`: `Invalid source specified; no handle could be opened RO (0x%08x)`
- `0x1400ea9db`: `VhdmpiTryOpenPhysicalDisk`
- `0x1400eaafb`: `VhdmpiTryOpenPhysicalDisk`

## pseudocode

```c
__int64 __fastcall VhdmpiTryOpenPhysicalDisk(struct _UNICODE_STRING *a1, void **a2, struct _FILE_OBJECT **a3)
{
  int IsPhysicalDisk; // ebx
  unsigned int v6; // edx
  unsigned __int16 v7; // cx
  char *v8; // rax
  NTSTATUS v9; // eax
  struct _FILE_OBJECT *v10; // rdi
  unsigned int v11; // edx
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
      v9 = ObReferenceObjectByHandle(FileHandle, 0x80000000, 0, 0, &Object, 0);
      v10 = (struct _FILE_OBJECT *)Object;
      IsPhysicalDisk = v9;
      if ( v9 >= 0 )
      {
        IsPhysicalDisk = VhdmpiIsPhysicalDisk((PFILE_OBJECT)Object, &v20);
        if ( IsPhysicalDisk >= 0 )
        {
          if ( v20 )
          {
            v12 = v10;
            v10 = 0;
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
      else if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
      {
        TraceEvents(
          "VhdmpiTryOpenPhysicalDisk",
          0x13Au,
          v11 - 6,
          v11,
          "Invalid source specified; no object could be referenced (0x%08x)",
          IsPhysicalDisk);
      }
      if ( v10 )
        ObfDereferenceObject(v10);
    }
    else if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
    {
      v7 = 298;
      v8 = "Invalid source specified; no handle could be opened RO (0x%08x)";
      goto LABEL_5;
    }
  }
  else if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
  {
    v7 = 269;
    v8 = "Could not get NT path of source (0x%08x)";
LABEL_5:
    OpenOptions[0] = IsPhysicalDisk;
    TraceEvents("VhdmpiTryOpenPhysicalDisk", v7, 2u, v6, v8, *(_QWORD *)OpenOptions);
  }
  if ( FileHandle )
    ZwClose(FileHandle);
  VhdmpiFreeFilePath(&v17);
  return (unsigned int)IsPhysicalDisk;
}

```

## disassembly

```asm
0x1400ea944  mov     [rsp-8+arg_0], rbx
0x1400ea949  mov     [rsp-8+arg_8], rsi
0x1400ea94e  push    rbp
0x1400ea94f  push    rdi
0x1400ea950  push    r14
0x1400ea952  lea     rbp, [rsp-47h]
0x1400ea957  sub     rsp, 90h
0x1400ea95e  xorps   xmm1, xmm1
0x1400ea961  mov     [rbp+57h+arg_18], 0
0x1400ea965  xorps   xmm0, xmm0
0x1400ea968  mov     [rbp+57h+FileHandle], 0
0x1400ea970  mov     rsi, rdx
0x1400ea973  mov     r14, r8
0x1400ea976  lea     rdx, [rbp+57h+var_60]; struct _UNICODE_STRING *
0x1400ea97a  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1400ea97e  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x1400ea982  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x1400ea986  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x1400ea98a  movups  xmmword ptr [rbp+57h+var_60.Length], xmm0
0x1400ea98e  call    VhdmpiCreateNtFilePath
0x1400ea993  mov     ebx, eax
0x1400ea995  test    eax, eax
0x1400ea997  jns     short loc_1400EA9F2
0x1400ea999  mov     ecx, cs:dword_1400876D0
0x1400ea99f  cmp     ecx, 2
0x1400ea9a2  jbe     loc_1400EAB5A
0x1400ea9a8  mov     edx, 8
0x1400ea9ad  lea     rcx, dword_1400876D0
0x1400ea9b4  call    _tlgKeywordOn
0x1400ea9b9  test    al, al
0x1400ea9bb  jz      loc_1400EAB5A
0x1400ea9c1  mov     ecx, 10Dh
0x1400ea9c6  lea     rax, aCouldNotGetNtP; "Could not get NT path of source (0x%08x"...
0x1400ea9cd  mov     r9d, edx; int
0x1400ea9d0  mov     [rsp+0A0h+OpenOptions], ebx; char
0x1400ea9d4  mov     edx, ecx; int
0x1400ea9d6  mov     qword ptr [rsp+0A0h+ShareAccess], rax; char *
0x1400ea9db  lea     rcx, aVhdmpitryopenp; "VhdmpiTryOpenPhysicalDisk"
0x1400ea9e2  mov     r8d, 2; int
0x1400ea9e8  call    TraceEvents
0x1400ea9ed  jmp     loc_1400EAB5A
0x1400ea9f2  lea     rax, [rbp+57h+var_60]
0x1400ea9f6  mov     [rsp+0A0h+OpenOptions], 48h ; 'H'; OpenOptions
0x1400ea9fe  xorps   xmm0, xmm0
0x1400eaa01  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400eaa08  mov     edi, 80000000h
0x1400eaa0d  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1400eaa15  mov     edx, edi; DesiredAccess
0x1400eaa17  mov     [rbp+57h+ObjectAttributes.Attributes], 640h
0x1400eaa1e  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1400eaa22  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400eaa26  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400eaa2a  mov     [rsp+0A0h+ShareAccess], 3; ShareAccess
0x1400eaa32  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1400eaa36  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400eaa3b  call    cs:__imp_ZwOpenFile
0x1400eaa42  nop     dword ptr [rax+rax+00h]
0x1400eaa47  mov     ebx, eax
0x1400eaa49  test    eax, eax
0x1400eaa4b  jns     short loc_1400EAA86
0x1400eaa4d  mov     eax, cs:dword_1400876D0
0x1400eaa53  cmp     eax, 2
0x1400eaa56  jbe     loc_1400EAB5A
0x1400eaa5c  mov     edx, 8
0x1400eaa61  lea     rcx, dword_1400876D0
0x1400eaa68  call    _tlgKeywordOn
0x1400eaa6d  test    al, al
0x1400eaa6f  jz      loc_1400EAB5A
0x1400eaa75  mov     ecx, 12Ah
0x1400eaa7a  lea     rax, aInvalidSourceS_0; "Invalid source specified; no handle cou"...
0x1400eaa81  jmp     loc_1400EA9CD
0x1400eaa86  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1400eaa8a  lea     rax, [rbp+57h+Object]
0x1400eaa8e  mov     qword ptr [rsp+0A0h+OpenOptions], 0; HandleInformation
0x1400eaa97  xor     r9d, r9d; AccessMode
0x1400eaa9a  xor     r8d, r8d; ObjectType
0x1400eaa9d  mov     qword ptr [rsp+0A0h+ShareAccess], rax; Object
0x1400eaaa2  mov     edx, edi; DesiredAccess
0x1400eaaa4  mov     [rbp+57h+Object], 0
0x1400eaaac  call    cs:__imp_ObReferenceObjectByHandle
0x1400eaab3  nop     dword ptr [rax+rax+00h]
0x1400eaab8  mov     rdi, [rbp+57h+Object]
0x1400eaabc  mov     ebx, eax
0x1400eaabe  test    eax, eax
0x1400eaac0  jns     short loc_1400EAB0E
0x1400eaac2  mov     eax, cs:dword_1400876D0
0x1400eaac8  cmp     eax, 2
0x1400eaacb  jbe     short loc_1400EAB46
0x1400eaacd  mov     edx, 8
0x1400eaad2  lea     rcx, dword_1400876D0
0x1400eaad9  call    _tlgKeywordOn
0x1400eaade  test    al, al
0x1400eaae0  jz      short loc_1400EAB46
0x1400eaae2  mov     ecx, 13Ah
0x1400eaae7  mov     [rsp+0A0h+OpenOptions], ebx; char
0x1400eaaeb  mov     r9d, edx; int
0x1400eaaee  lea     r8d, [rdx-6]; int
0x1400eaaf2  mov     edx, ecx; int
0x1400eaaf4  lea     rax, aInvalidSourceS; "Invalid source specified; no object cou"...
0x1400eaafb  lea     rcx, aVhdmpitryopenp; "VhdmpiTryOpenPhysicalDisk"
0x1400eab02  mov     qword ptr [rsp+0A0h+ShareAccess], rax; char *
0x1400eab07  call    TraceEvents
0x1400eab0c  jmp     short loc_1400EAB46
0x1400eab0e  lea     rdx, [rbp+57h+arg_18]; unsigned __int8 *
0x1400eab12  mov     rcx, rdi; FileObject
0x1400eab15  call    ?VhdmpiIsPhysicalDisk@@YAJPEAU_FILE_OBJECT@@PEAE@Z; VhdmpiIsPhysicalDisk(_FILE_OBJECT *,uchar *)
0x1400eab1a  mov     ebx, eax
0x1400eab1c  test    eax, eax
0x1400eab1e  js      short loc_1400EAB46
0x1400eab20  cmp     [rbp+57h+arg_18], 0
0x1400eab24  jz      short loc_1400EAB38
0x1400eab26  mov     rax, [rbp+57h+FileHandle]
0x1400eab2a  mov     rcx, rdi
0x1400eab2d  xor     edi, edi
0x1400eab2f  mov     [rsi], rax
0x1400eab32  mov     [rbp+57h+FileHandle], rdi
0x1400eab36  jmp     short loc_1400EAB41
0x1400eab38  mov     qword ptr [rsi], 0
0x1400eab3f  xor     ecx, ecx
0x1400eab41  mov     [r14], rcx
0x1400eab44  xor     ebx, ebx
0x1400eab46  test    rdi, rdi
0x1400eab49  jz      short loc_1400EAB5A
0x1400eab4b  mov     rcx, rdi; Object
0x1400eab4e  call    cs:__imp_ObfDereferenceObject
0x1400eab55  nop     dword ptr [rax+rax+00h]
0x1400eab5a  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1400eab5e  test    rcx, rcx
0x1400eab61  jz      short loc_1400EAB6F
0x1400eab63  call    cs:__imp_ZwClose
0x1400eab6a  nop     dword ptr [rax+rax+00h]
0x1400eab6f  lea     rcx, [rbp+57h+var_60]
0x1400eab73  call    VhdmpiFreeFilePath
0x1400eab78  lea     r11, [rsp+0A0h+var_10]
0x1400eab80  mov     eax, ebx
0x1400eab82  mov     rbx, [r11+20h]
0x1400eab86  mov     rsi, [r11+28h]
0x1400eab8a  mov     rsp, r11
0x1400eab8d  pop     r14
0x1400eab8f  pop     rdi
0x1400eab90  pop     rbp
0x1400eab91  retn
```
