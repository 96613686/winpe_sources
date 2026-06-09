# PFOpenById

- ea: `0x140001188`
- end: `0x140001497`
- name: `PFOpenById`
- size: `783`
- prototype: `__int64 __usercall@<rax>(PFLT_FILTER Filter@<rcx>, PFLT_INSTANCE Instance@<rdx>, char, PVOID *Object, __int64, char)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140001628`

## callees

- `0x140001188`
- `0x140002bb0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140001468`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001468`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140001328`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140001328`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000129d`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000129d`
- `ntoskrnl!IoFileObjectType` at `0x14000127d`
- `FLTMGR!FltClose` at `0x1400012c5`
- `FLTMGR!FltClose` at `0x14000144f`
- `FLTMGR!FltClose` at `0x1400012c5`
- `FLTMGR!FltClose` at `0x14000144f`
- `FLTMGR!FltQueryInformationFile` at `0x1400012f0`
- `FLTMGR!FltQueryInformationFile` at `0x140001363`
- `FLTMGR!FltQueryInformationFile` at `0x1400012f0`
- `FLTMGR!FltQueryInformationFile` at `0x140001363`
- `FLTMGR!FltCreateFile` at `0x140001267`
- `FLTMGR!FltCreateFile` at `0x140001420`
- `FLTMGR!FltCreateFile` at `0x140001267`
- `FLTMGR!FltCreateFile` at `0x140001420`

## pseudocode

```c
__int64 __fastcall PFOpenById(
        PFLT_FILTER Filter,
        PFLT_INSTANCE Instance,
        void *a3,
        char *a4,
        char a5,
        PVOID *Object,
        void **a7,
        char a8)
{
  _DWORD *v9; // rdi
  unsigned int v10; // r12d
  NTSTATUS InformationFile; // ebx
  struct _FILE_OBJECT *v13; // rdx
  ULONG v14; // ebx
  _DWORD *PoolWithTag; // rax
  void *FileHandle; // [rsp+70h] [rbp-71h] BYREF
  __int64 v18; // [rsp+78h] [rbp-69h] BYREF
  char *v19; // [rsp+80h] [rbp-61h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-59h] BYREF
  void *v21; // [rsp+B8h] [rbp-29h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C0h] [rbp-21h] BYREF
  __int64 FileInformation; // [rsp+D0h] [rbp-11h] BYREF

  v21 = a3;
  v9 = 0;
  v10 = a8 != 0 ? 0xFEFEFEEA : 0;
  ObjectAttributes.RootDirectory = a3;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v18;
  FileHandle = 0;
  v19 = a4;
  v18 = 524296;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 512;
  IoStatusBlock = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  InformationFile = FltCreateFile(
                      Filter,
                      Instance,
                      &FileHandle,
                      v10 + 18022815,
                      &ObjectAttributes,
                      &IoStatusBlock,
                      0,
                      0x80u,
                      7u,
                      1u,
                      0x206020u,
                      0,
                      0,
                      0x800u);
  if ( InformationFile >= 0 )
  {
    InformationFile = ObReferenceObjectByHandle(FileHandle, 0xF0000u, (POBJECT_TYPE)IoFileObjectType, 0, Object, 0);
    if ( InformationFile >= 0 )
    {
      if ( !a5 )
        goto LABEL_12;
      FileInformation = 0;
      FltClose(FileHandle);
      v13 = (struct _FILE_OBJECT *)*Object;
      FileHandle = 0;
      InformationFile = FltQueryInformationFile(Instance, v13, &FileInformation, 8u, FileNameInformation, 0);
      if ( (int)(InformationFile + 0x80000000) < 0 || InformationFile == -2147483643 )
      {
        v14 = FileInformation + 8;
        PoolWithTag = ExAllocatePoolWithTag(PagedPool, (unsigned int)(FileInformation + 8), 0x50466E69u);
        v9 = PoolWithTag;
        if ( !PoolWithTag )
        {
          InformationFile = -1073741670;
          goto LABEL_14;
        }
        InformationFile = FltQueryInformationFile(
                            Instance,
                            (PFILE_OBJECT)*Object,
                            PoolWithTag,
                            v14,
                            FileNameInformation,
                            0);
        if ( InformationFile >= 0 )
        {
          if ( !*v9 )
          {
            InformationFile = -1073741823;
            goto LABEL_14;
          }
          v19 = (char *)v9 + 6;
          WORD1(v18) = *(_WORD *)v9 - 2;
          LOWORD(v18) = WORD1(v18);
          ObjectAttributes.RootDirectory = v21;
          ObjectAttributes.ObjectName = (PUNICODE_STRING)&v18;
          ObjectAttributes.Length = 48;
          ObjectAttributes.Attributes = 512;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          InformationFile = FltCreateFile(
                              Filter,
                              Instance,
                              &FileHandle,
                              v10 + 18022815,
                              &ObjectAttributes,
                              &IoStatusBlock,
                              0,
                              0x80u,
                              7u,
                              1u,
                              0x204020u,
                              0,
                              0,
                              0x800u);
          if ( InformationFile >= 0 )
          {
LABEL_12:
            if ( a7 )
            {
              *a7 = FileHandle;
              FileHandle = 0;
            }
          }
        }
      }
    }
  }
LABEL_14:
  if ( FileHandle )
    FltClose(FileHandle);
  if ( v9 )
    ExFreePoolWithTag(v9, 0x50466E69u);
  return (unsigned int)InformationFile;
}

```

## disassembly

```asm
0x140001188  push    rbp
0x14000118a  push    rbx
0x14000118b  push    rsi
0x14000118c  push    rdi
0x14000118d  push    r12
0x14000118f  push    r13
0x140001191  push    r14
0x140001193  push    r15
0x140001195  lea     rbp, [rsp-7]
0x14000119a  sub     rsp, 0E8h
0x1400011a1  mov     rax, cs:__security_cookie
0x1400011a8  xor     rax, rsp
0x1400011ab  mov     [rbp+3Fh+var_48], rax
0x1400011af  mov     r14, [rbp+3Fh+Object]
0x1400011b3  mov     rax, r8
0x1400011b6  mov     rsi, [rbp+3Fh+arg_30]
0x1400011ba  lea     r8, [rbp+3Fh+FileHandle]; FileHandle
0x1400011be  mov     [rsp+120h+Flags], 800h; Flags
0x1400011c6  mov     r13, rcx
0x1400011c9  xor     ecx, ecx
0x1400011cb  mov     [rbp+3Fh+var_68], rax
0x1400011cf  neg     [rbp+3Fh+arg_38]
0x1400011d5  xorps   xmm0, xmm0
0x1400011d8  mov     [rsp+120h+EaLength], ecx; EaLength
0x1400011dc  mov     edi, ecx
0x1400011de  mov     [rsp+120h+EaBuffer], rcx; EaBuffer
0x1400011e3  sbb     r12d, r12d
0x1400011e6  mov     [rsp+120h+CreateOptions], 206020h; CreateOptions
0x1400011ee  and     r12d, 0FEFEFEEAh
0x1400011f5  mov     [rsp+120h+CreateDisposition], 1; CreateDisposition
0x1400011fd  mov     r15, rdx
0x140001200  mov     [rbp+3Fh+var_98.RootDirectory], rax
0x140001204  lea     rax, [rbp+3Fh+var_A8]
0x140001208  mov     [rsp+120h+ShareAccess], 7; ShareAccess
0x140001210  mov     [rbp+3Fh+var_98.ObjectName], rax
0x140001214  lea     rax, [rbp+3Fh+var_60]
0x140001218  mov     [rsp+120h+FileAttributes], 80h; FileAttributes
0x140001220  mov     [rsp+120h+AllocationSize], rcx; AllocationSize
0x140001225  mov     [rsp+120h+IoStatusBlock], rax; IoStatusBlock
0x14000122a  lea     rax, [rbp+3Fh+var_98]
0x14000122e  mov     [rbp+3Fh+FileHandle], rcx
0x140001232  mov     rcx, r13; Filter
0x140001235  mov     [rbp+3Fh+var_A0], r9
0x140001239  lea     r9d, [r12+113019Fh]; DesiredAccess
0x140001241  mov     [rbp+3Fh+var_A8], 80008h
0x140001249  mov     qword ptr [rbp+3Fh+var_98.Length], 30h ; '0'
0x140001251  mov     qword ptr [rbp+3Fh+var_98.Attributes], 200h
0x140001259  movups  xmmword ptr [rbp+3Fh+var_60], xmm0
0x14000125d  mov     [rsp+120h+ObjectAttributes], rax; ObjectAttributes
0x140001262  movdqu  xmmword ptr [rbp+3Fh+var_98.SecurityDescriptor], xmm0
0x140001267  call    cs:__imp_FltCreateFile
0x14000126e  nop     dword ptr [rax+rax+00h]
0x140001273  mov     ebx, eax
0x140001275  test    eax, eax
0x140001277  js      loc_140001446
0x14000127d  mov     r8, cs:__imp_IoFileObjectType
0x140001284  xor     r9d, r9d; AccessMode
0x140001287  mov     rcx, [rbp+3Fh+FileHandle]; Handle
0x14000128b  mov     edx, 0F0000h; DesiredAccess
0x140001290  mov     [rsp+120h+IoStatusBlock], rdi; HandleInformation
0x140001295  mov     [rsp+120h+ObjectAttributes], r14; Object
0x14000129a  mov     r8, [r8]; ObjectType
0x14000129d  call    cs:__imp_ObReferenceObjectByHandle
0x1400012a4  nop     dword ptr [rax+rax+00h]
0x1400012a9  mov     ebx, eax
0x1400012ab  test    eax, eax
0x1400012ad  js      loc_140001446
0x1400012b3  cmp     [rbp+3Fh+arg_20], dil
0x1400012b7  jz      loc_140001432
0x1400012bd  mov     rcx, [rbp+3Fh+FileHandle]; FileHandle
0x1400012c1  mov     [rbp+3Fh+FileInformation], rdi
0x1400012c5  call    cs:__imp_FltClose
0x1400012cc  nop     dword ptr [rax+rax+00h]
0x1400012d1  mov     rdx, [r14]; FileObject
0x1400012d4  lea     r9d, [rdi+8]; Length
0x1400012d8  lea     r8, [rbp+3Fh+FileInformation]; FileInformation
0x1400012dc  mov     [rsp+120h+IoStatusBlock], rdi; LengthReturned
0x1400012e1  mov     rcx, r15; Instance
0x1400012e4  mov     [rbp+3Fh+FileHandle], rdi
0x1400012e8  mov     dword ptr [rsp+120h+ObjectAttributes], 9; FileInformationClass
0x1400012f0  call    cs:__imp_FltQueryInformationFile
0x1400012f7  nop     dword ptr [rax+rax+00h]
0x1400012fc  mov     ecx, 80000000h
0x140001301  mov     ebx, eax
0x140001303  add     eax, ecx
0x140001305  test    ecx, eax
0x140001307  jnz     short loc_140001315
0x140001309  cmp     ebx, 80000005h
0x14000130f  jnz     loc_140001446
0x140001315  mov     ebx, dword ptr [rbp+3Fh+FileInformation]
0x140001318  mov     ecx, 1; PoolType
0x14000131d  add     ebx, 8
0x140001320  mov     r8d, 50466E69h; Tag
0x140001326  mov     edx, ebx; NumberOfBytes
0x140001328  call    cs:__imp_ExAllocatePoolWithTag
0x14000132f  nop     dword ptr [rax+rax+00h]
0x140001334  mov     rdi, rax
0x140001337  test    rax, rax
0x14000133a  jnz     short loc_140001346
0x14000133c  mov     ebx, 0C000009Ah
0x140001341  jmp     loc_140001446
0x140001346  mov     rdx, [r14]; FileObject
0x140001349  mov     r9d, ebx; Length
0x14000134c  mov     [rsp+120h+IoStatusBlock], 0; LengthReturned
0x140001355  mov     r8, rdi; FileInformation
0x140001358  mov     rcx, r15; Instance
0x14000135b  mov     dword ptr [rsp+120h+ObjectAttributes], 9; FileInformationClass
0x140001363  call    cs:__imp_FltQueryInformationFile
0x14000136a  nop     dword ptr [rax+rax+00h]
0x14000136f  xor     ecx, ecx
0x140001371  mov     ebx, eax
0x140001373  test    eax, eax
0x140001375  js      loc_140001446
0x14000137b  cmp     [rdi], ecx
0x14000137d  jnz     short loc_140001389
0x14000137f  mov     ebx, 0C0000001h
0x140001384  jmp     loc_140001446
0x140001389  mov     [rsp+120h+Flags], 800h; Flags
0x140001391  lea     rax, [rdi+6]
0x140001395  mov     [rsp+120h+EaLength], ecx; EaLength
0x140001399  lea     r9d, [r12+113019Fh]; DesiredAccess
0x1400013a1  mov     [rsp+120h+EaBuffer], rcx; EaBuffer
0x1400013a6  lea     r8, [rbp+3Fh+FileHandle]; FileHandle
0x1400013aa  mov     [rbp+3Fh+var_A0], rax
0x1400013ae  xorps   xmm0, xmm0
0x1400013b1  movzx   eax, word ptr [rdi]
0x1400013b4  mov     rdx, r15; Instance
0x1400013b7  sub     ax, 2
0x1400013bb  mov     [rsp+120h+CreateOptions], 204020h; CreateOptions
0x1400013c3  mov     word ptr [rbp+3Fh+var_A8+2], ax
0x1400013c7  mov     word ptr [rbp+3Fh+var_A8], ax
0x1400013cb  mov     rax, [rbp+3Fh+var_68]
0x1400013cf  mov     [rsp+120h+CreateDisposition], 1; CreateDisposition
0x1400013d7  mov     [rbp+3Fh+var_98.RootDirectory], rax
0x1400013db  lea     rax, [rbp+3Fh+var_A8]
0x1400013df  mov     [rsp+120h+ShareAccess], 7; ShareAccess
0x1400013e7  mov     [rbp+3Fh+var_98.ObjectName], rax
0x1400013eb  lea     rax, [rbp+3Fh+var_60]
0x1400013ef  mov     [rsp+120h+FileAttributes], 80h; FileAttributes
0x1400013f7  mov     [rsp+120h+AllocationSize], rcx; AllocationSize
0x1400013fc  mov     rcx, r13; Filter
0x1400013ff  mov     [rsp+120h+IoStatusBlock], rax; IoStatusBlock
0x140001404  lea     rax, [rbp+3Fh+var_98]
0x140001408  mov     [rsp+120h+ObjectAttributes], rax; ObjectAttributes
0x14000140d  mov     [rbp+3Fh+var_98.Length], 30h ; '0'
0x140001414  mov     [rbp+3Fh+var_98.Attributes], 200h
0x14000141b  movdqu  xmmword ptr [rbp+3Fh+var_98.SecurityDescriptor], xmm0
0x140001420  call    cs:__imp_FltCreateFile
0x140001427  nop     dword ptr [rax+rax+00h]
0x14000142c  mov     ebx, eax
0x14000142e  test    eax, eax
0x140001430  js      short loc_140001446
0x140001432  test    rsi, rsi
0x140001435  jz      short loc_140001446
0x140001437  mov     rax, [rbp+3Fh+FileHandle]
0x14000143b  mov     [rsi], rax
0x14000143e  mov     [rbp+3Fh+FileHandle], 0
0x140001446  mov     rcx, [rbp+3Fh+FileHandle]; FileHandle
0x14000144a  test    rcx, rcx
0x14000144d  jz      short loc_14000145B
0x14000144f  call    cs:__imp_FltClose
0x140001456  nop     dword ptr [rax+rax+00h]
0x14000145b  test    rdi, rdi
0x14000145e  jz      short loc_140001474
0x140001460  mov     edx, 50466E69h; Tag
0x140001465  mov     rcx, rdi; P
0x140001468  call    cs:__imp_ExFreePoolWithTag
0x14000146f  nop     dword ptr [rax+rax+00h]
0x140001474  mov     eax, ebx
0x140001476  mov     rcx, [rbp+3Fh+var_48]
0x14000147a  xor     rcx, rsp; StackCookie
0x14000147d  call    __security_check_cookie
0x140001482  add     rsp, 0E8h
0x140001489  pop     r15
0x14000148b  pop     r14
0x14000148d  pop     r13
0x14000148f  pop     r12
0x140001491  pop     rdi
0x140001492  pop     rsi
0x140001493  pop     rbx
0x140001494  pop     rbp
0x140001495  retn
```
