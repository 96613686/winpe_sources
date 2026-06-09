# SmpOpenKnownDllsHandles

- ea: `0x140015660`
- end: `0x1400158db`
- name: `SmpOpenKnownDllsHandles`
- size: `635`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x14000c638`
- `0x14000eb40`

## callees

- `0x1400010ec`
- `0x14000d4c0`
- `0x14000d83c`
- `0x140015660`

## import_xrefs

- `ntdll!NtOpenFile` at `0x14001577b`
- `ntdll!NtOpenFile` at `0x14001577b`
- `ntdll!NtClose` at `0x1400158b0`
- `ntdll!NtClose` at `0x1400158bf`
- `ntdll!NtClose` at `0x1400158b0`
- `ntdll!NtClose` at `0x1400158bf`
- `ntdll!RtlFreeHeap` at `0x140015882`
- `ntdll!RtlFreeHeap` at `0x1400158a1`
- `ntdll!RtlFreeHeap` at `0x140015882`
- `ntdll!RtlFreeHeap` at `0x1400158a1`
- `ntdll!NtCreateDirectoryObject` at `0x1400157d6`
- `ntdll!NtCreateDirectoryObject` at `0x1400157d6`
- `ntdll!NtCreateSymbolicLinkObject` at `0x14001583d`
- `ntdll!NtCreateSymbolicLinkObject` at `0x14001583d`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x14001571c`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x14001571c`

## string_xrefs

- `0x1400156a4`: `KnownDllPath`
- `0x1400156fd`: `SmpOpenKnownDllsHandles`
- `0x1400157f5`: `SmpOpenKnownDllsHandles`

## pseudocode

```c
__int64 __fastcall SmpOpenKnownDllsHandles(
        struct _UNICODE_STRING *a1,
        const UNICODE_STRING *a2,
        int a3,
        void **a4,
        void **a5)
{
  void **v5; // r15
  NTSTATUS v10; // eax
  unsigned int v11; // ebx
  PWSTR Buffer; // r8
  __int64 v13; // rdx
  NTSTATUS v14; // eax
  __int64 v15; // rdx
  void *FileHandle; // [rsp+30h] [rbp-71h] BYREF
  void *SymbolicLinkHandle; // [rsp+38h] [rbp-69h] BYREF
  struct _UNICODE_STRING Name; // [rsp+40h] [rbp-61h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-51h] BYREF
  PVOID BaseAddress[2]; // [rsp+80h] [rbp-21h] BYREF
  _QWORD v22[2]; // [rsp+90h] [rbp-11h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A0h] [rbp-1h] BYREF
  void *DirectoryHandle; // [rsp+118h] [rbp+77h] BYREF

  v5 = a5;
  v22[0] = 1703960;
  *a4 = 0;
  FileHandle = 0;
  *v5 = 0;
  DirectoryHandle = 0;
  SymbolicLinkHandle = 0;
  v22[1] = L"KnownDllPath";
  Name = 0;
  IoStatusBlock = 0;
  *(_OWORD *)BaseAddress = 0;
  memset(&ObjectAttributes, 0, 44);
  v10 = SmpExpandKnownDllsPath(a2, &Name);
  v11 = v10;
  if ( v10 < 0 )
  {
    Name.Buffer = 0;
    if ( a2 )
      Buffer = a2->Buffer;
    else
      Buffer = 0;
    v13 = 3826;
    goto LABEL_6;
  }
  v10 = RtlDosPathNameToNtPathName_U_WithStatus(Name.Buffer, BaseAddress, 0, 0);
  v11 = v10;
  if ( v10 < 0 )
  {
    Buffer = Name.Buffer;
    v13 = 3843;
    BaseAddress[1] = 0;
LABEL_6:
    SmpLogFailureString("SmpOpenKnownDllsHandles", v13, Buffer, (unsigned int)v10);
    goto LABEL_21;
  }
  ObjectAttributes.ObjectName = (PUNICODE_STRING)BaseAddress;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v10 = NtOpenFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 3u, 0x21u);
  v11 = v10;
  if ( v10 < 0 )
  {
    FileHandle = 0;
    if ( v10 != -1073741772 || a3 )
    {
      Buffer = (PWSTR)BaseAddress[1];
      v13 = 3874;
      goto LABEL_6;
    }
    goto LABEL_20;
  }
  ObjectAttributes.SecurityDescriptor = SmpKnownDllsDirSecurityDescriptor;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 208;
  ObjectAttributes.ObjectName = a1;
  ObjectAttributes.SecurityQualityOfService = 0;
  v14 = NtCreateDirectoryObject(&DirectoryHandle, 0xF000Fu, &ObjectAttributes);
  v11 = v14;
  if ( v14 != 0x40000000 )
  {
    if ( v14 < 0 )
    {
      DirectoryHandle = 0;
      v15 = 3909;
LABEL_16:
      SmpLogFailure("SmpOpenKnownDllsHandles", v15, (unsigned int)v14);
      goto LABEL_21;
    }
    ObjectAttributes.RootDirectory = DirectoryHandle;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)v22;
    ObjectAttributes.SecurityDescriptor = SmpKnownDllsSymLinkSecurityDescriptor;
    ObjectAttributes.Attributes = 80;
    ObjectAttributes.SecurityQualityOfService = 0;
    v14 = NtCreateSymbolicLinkObject(&SymbolicLinkHandle, 0xF0001u, &ObjectAttributes, &Name);
    v11 = v14;
    if ( v14 < 0 )
    {
      SymbolicLinkHandle = 0;
      v15 = 3932;
      goto LABEL_16;
    }
  }
  *a4 = DirectoryHandle;
  *v5 = FileHandle;
  DirectoryHandle = 0;
LABEL_20:
  v11 = 0;
LABEL_21:
  if ( BaseAddress[1] )
    RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, BaseAddress[1]);
  if ( Name.Buffer )
    RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, Name.Buffer);
  if ( SymbolicLinkHandle )
    NtClose(SymbolicLinkHandle);
  if ( DirectoryHandle )
    NtClose(DirectoryHandle);
  return v11;
}

```

## disassembly

```asm
0x140015660  push    rbp
0x140015662  push    rbx
0x140015663  push    rsi
0x140015664  push    rdi
0x140015665  push    r12
0x140015667  push    r13
0x140015669  push    r14
0x14001566b  push    r15
0x14001566d  lea     rbp, [rsp-17h]
0x140015672  sub     rsp, 0B8h
0x140015679  mov     r15, [rbp+4Fh+arg_20]
0x14001567d  xorps   xmm0, xmm0
0x140015680  xor     r13d, r13d
0x140015683  mov     [rbp+4Fh+var_60], 1A0018h
0x14001568b  mov     rdi, rdx
0x14001568e  mov     [r9], r13
0x140015691  xor     eax, eax
0x140015693  mov     [rbp+4Fh+FileHandle], r13
0x140015697  mov     r12, rcx
0x14001569a  mov     [r15], r13
0x14001569d  xorps   xmm1, xmm1
0x1400156a0  mov     [rbp+4Fh+DirectoryHandle], r13
0x1400156a4  lea     rax, aKnowndllpath; "KnownDllPath"
0x1400156ab  mov     [rbp+4Fh+SymbolicLinkHandle], r13
0x1400156af  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x1400156b3  lea     rdx, [rbp+4Fh+Name]; Destination
0x1400156b7  mov     [rbp+4Fh+var_58], rax
0x1400156bb  mov     rcx, rdi; Source
0x1400156be  mov     r14, r9
0x1400156c1  mov     esi, r8d
0x1400156c4  movups  xmmword ptr [rbp+4Fh+Name.Length], xmm0
0x1400156c8  movups  xmmword ptr [rbp+4Fh+IoStatusBlock], xmm0
0x1400156cc  movups  xmmword ptr [rbp+4Fh+BaseAddress], xmm1
0x1400156d0  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x1400156d4  movups  xmmword ptr [rbp+4Fh+ObjectAttributes+1Ch], xmm0
0x1400156d8  call    SmpExpandKnownDllsPath
0x1400156dd  mov     ebx, eax
0x1400156df  test    eax, eax
0x1400156e1  jns     short loc_14001570E
0x1400156e3  mov     [rbp+4Fh+Name.Buffer], r13
0x1400156e7  test    rdi, rdi
0x1400156ea  jz      short loc_1400156F2
0x1400156ec  mov     r8, [rdi+8]
0x1400156f0  jmp     short loc_1400156F5
0x1400156f2  mov     r8, r13
0x1400156f5  mov     edx, 0EF2h
0x1400156fa  mov     r9d, eax
0x1400156fd  lea     rcx, aSmpopenknowndl; "SmpOpenKnownDllsHandles"
0x140015704  call    SmpLogFailureString
0x140015709  jmp     loc_140015869
0x14001570e  mov     rcx, [rbp+4Fh+Name.Buffer]
0x140015712  lea     rdx, [rbp+4Fh+BaseAddress]
0x140015716  xor     r9d, r9d
0x140015719  xor     r8d, r8d
0x14001571c  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x140015722  mov     ebx, eax
0x140015724  test    eax, eax
0x140015726  jns     short loc_140015737
0x140015728  mov     r8, [rbp+4Fh+Name.Buffer]
0x14001572c  mov     edx, 0F03h
0x140015731  mov     [rbp+4Fh+BaseAddress+8], r13
0x140015735  jmp     short loc_1400156FA
0x140015737  lea     rax, [rbp+4Fh+BaseAddress]
0x14001573b  mov     [rsp+0F0h+OpenOptions], 21h ; '!'; OpenOptions
0x140015743  xorps   xmm0, xmm0
0x140015746  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x14001574a  mov     edi, 30h ; '0'
0x14001574f  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], r13
0x140015753  lea     r9, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x140015757  mov     [rbp+4Fh+ObjectAttributes.Length], edi
0x14001575a  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x14001575e  mov     [rbp+4Fh+ObjectAttributes.Attributes], 40h ; '@'
0x140015765  mov     edx, 100001h; DesiredAccess
0x14001576a  mov     [rsp+0F0h+ShareAccess], 3; ShareAccess
0x140015772  lea     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x140015776  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x14001577b  call    cs:__imp_NtOpenFile
0x140015781  mov     ebx, eax
0x140015783  test    eax, eax
0x140015785  jns     short loc_1400157A8
0x140015787  mov     [rbp+4Fh+FileHandle], r13
0x14001578b  cmp     eax, 0C0000034h
0x140015790  jnz     short loc_14001579A
0x140015792  test    esi, esi
0x140015794  jz      loc_140015866
0x14001579a  mov     r8, [rbp+4Fh+BaseAddress+8]
0x14001579e  mov     edx, 0F22h
0x1400157a3  jmp     loc_1400156FA
0x1400157a8  mov     rax, cs:SmpKnownDllsDirSecurityDescriptor
0x1400157af  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x1400157b3  mov     edx, 0F000Fh; DesiredAccess
0x1400157b8  mov     [rbp+4Fh+ObjectAttributes.SecurityDescriptor], rax
0x1400157bc  lea     rcx, [rbp+4Fh+DirectoryHandle]; DirectoryHandle
0x1400157c0  mov     [rbp+4Fh+ObjectAttributes.Length], edi
0x1400157c3  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], r13
0x1400157c7  mov     [rbp+4Fh+ObjectAttributes.Attributes], 0D0h
0x1400157ce  mov     [rbp+4Fh+ObjectAttributes.ObjectName], r12
0x1400157d2  mov     [rbp+4Fh+ObjectAttributes.SecurityQualityOfService], r13
0x1400157d6  call    cs:__imp_NtCreateDirectoryObject
0x1400157dc  mov     ebx, eax
0x1400157de  cmp     eax, 40000000h
0x1400157e3  jz      short loc_140015854
0x1400157e5  test    eax, eax
0x1400157e7  jns     short loc_140015803
0x1400157e9  mov     [rbp+4Fh+DirectoryHandle], r13
0x1400157ed  mov     edx, 0F45h
0x1400157f2  mov     r8d, eax
0x1400157f5  lea     rcx, aSmpopenknowndl; "SmpOpenKnownDllsHandles"
0x1400157fc  call    SmpLogFailure
0x140015801  jmp     short loc_140015869
0x140015803  mov     rax, [rbp+4Fh+DirectoryHandle]
0x140015807  lea     r9, [rbp+4Fh+Name]; Name
0x14001580b  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rax
0x14001580f  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x140015813  lea     rax, [rbp+4Fh+var_60]
0x140015817  mov     [rbp+4Fh+ObjectAttributes.Length], edi
0x14001581a  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x14001581e  lea     rcx, [rbp+4Fh+SymbolicLinkHandle]; SymbolicLinkHandle
0x140015822  mov     rax, cs:SmpKnownDllsSymLinkSecurityDescriptor
0x140015829  mov     edx, 0F0001h; DesiredAccess
0x14001582e  mov     [rbp+4Fh+ObjectAttributes.SecurityDescriptor], rax
0x140015832  mov     [rbp+4Fh+ObjectAttributes.Attributes], 50h ; 'P'
0x140015839  mov     [rbp+4Fh+ObjectAttributes.SecurityQualityOfService], r13
0x14001583d  call    cs:__imp_NtCreateSymbolicLinkObject
0x140015843  mov     ebx, eax
0x140015845  test    eax, eax
0x140015847  jns     short loc_140015854
0x140015849  mov     [rbp+4Fh+SymbolicLinkHandle], r13
0x14001584d  mov     edx, 0F5Ch
0x140015852  jmp     short loc_1400157F2
0x140015854  mov     rax, [rbp+4Fh+DirectoryHandle]
0x140015858  mov     [r14], rax
0x14001585b  mov     rax, [rbp+4Fh+FileHandle]
0x14001585f  mov     [r15], rax
0x140015862  mov     [rbp+4Fh+DirectoryHandle], r13
0x140015866  mov     ebx, r13d
0x140015869  cmp     [rbp+4Fh+BaseAddress+8], r13
0x14001586d  jz      short loc_140015888
0x14001586f  mov     rcx, gs:60h
0x140015878  xor     edx, edx; Flags
0x14001587a  mov     r8, [rbp+4Fh+BaseAddress+8]; BaseAddress
0x14001587e  mov     rcx, [rcx+30h]; HeapHandle
0x140015882  call    cs:__imp_RtlFreeHeap
0x140015888  cmp     [rbp+4Fh+Name.Buffer], r13
0x14001588c  jz      short loc_1400158A7
0x14001588e  mov     rcx, gs:60h
0x140015897  xor     edx, edx; Flags
0x140015899  mov     r8, [rbp+4Fh+Name.Buffer]; BaseAddress
0x14001589d  mov     rcx, [rcx+30h]; HeapHandle
0x1400158a1  call    cs:__imp_RtlFreeHeap
0x1400158a7  mov     rcx, [rbp+4Fh+SymbolicLinkHandle]; Handle
0x1400158ab  test    rcx, rcx
0x1400158ae  jz      short loc_1400158B6
0x1400158b0  call    cs:__imp_NtClose
0x1400158b6  mov     rcx, [rbp+4Fh+DirectoryHandle]; Handle
0x1400158ba  test    rcx, rcx
0x1400158bd  jz      short loc_1400158C5
0x1400158bf  call    cs:__imp_NtClose
0x1400158c5  mov     eax, ebx
0x1400158c7  add     rsp, 0B8h
0x1400158ce  pop     r15
0x1400158d0  pop     r14
0x1400158d2  pop     r13
0x1400158d4  pop     r12
0x1400158d6  pop     rdi
0x1400158d7  pop     rsi
0x1400158d8  pop     rbx
0x1400158d9  pop     rbp
0x1400158da  retn
```
