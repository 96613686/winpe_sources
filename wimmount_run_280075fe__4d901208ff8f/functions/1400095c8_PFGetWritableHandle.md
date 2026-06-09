# PFGetWritableHandle

- ea: `0x1400095c8`
- end: `0x1400097de`
- name: `PFGetWritableHandle`
- size: `534`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140009aa0`

## callees

- `0x140002bb0`
- `0x1400095c8`

## import_xrefs

- `FLTMGR!FltClose` at `0x1400097b1`
- `FLTMGR!FltClose` at `0x1400097b1`
- `FLTMGR!FltQueryInformationFile` at `0x14000965a`
- `FLTMGR!FltQueryInformationFile` at `0x14000965a`
- `FLTMGR!FltSetInformationFile` at `0x14000969d`
- `FLTMGR!FltSetInformationFile` at `0x140009786`
- `FLTMGR!FltSetInformationFile` at `0x14000969d`
- `FLTMGR!FltSetInformationFile` at `0x140009786`
- `FLTMGR!FltCreateFile` at `0x140009753`
- `FLTMGR!FltCreateFile` at `0x140009753`

## pseudocode

```c
__int64 __fastcall PFGetWritableHandle(__int64 a1, __int64 a2, __int64 a3, struct _FILE_OBJECT *a4, void **a5)
{
  __int64 v5; // rcx
  __m128i v8; // xmm0
  __int16 v9; // ax
  struct _FLT_INSTANCE *v10; // rcx
  NTSTATUS InformationFile; // ebx
  int v12; // edi
  char v13; // r14
  struct _FLT_INSTANCE *v14; // rcx
  struct _FLT_INSTANCE *v15; // rdx
  struct _FLT_FILTER *v16; // rcx
  struct _FLT_INSTANCE *v17; // rcx
  void *v18; // rcx
  void *FileHandle; // [rsp+70h] [rbp-71h] BYREF
  __m128i v21; // [rsp+78h] [rbp-69h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-59h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B8h] [rbp-29h] BYREF
  _OWORD FileInformation[2]; // [rsp+C8h] [rbp-19h] BYREF
  __int64 v25; // [rsp+E8h] [rbp+7h]

  v5 = *(_QWORD *)(a1 + 40);
  v25 = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  FileHandle = 0;
  IoStatusBlock = 0;
  v8 = *(__m128i *)(a3 + 8);
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v21 = v8;
  v9 = _mm_cvtsi128_si32(v8) - *(_WORD *)(v5 + 6);
  v10 = *(struct _FLT_INSTANCE **)(a2 + 24);
  v21.m128i_i16[0] = v9;
  InformationFile = FltQueryInformationFile(v10, a4, FileInformation, 0x28u, FileBasicInformation, 0);
  if ( InformationFile < 0 )
    goto LABEL_9;
  v12 = v25;
  v13 = 0;
  if ( (v25 & 1) != 0 )
  {
    v14 = *(struct _FLT_INSTANCE **)(a2 + 24);
    LODWORD(v25) = v25 & 0xFFFFFFFE;
    InformationFile = FltSetInformationFile(v14, a4, FileInformation, 0x28u, FileBasicInformation);
    if ( InformationFile < 0 )
      goto LABEL_9;
    v13 = 1;
  }
  v15 = *(struct _FLT_INSTANCE **)(a2 + 24);
  v16 = *(struct _FLT_FILTER **)(a2 + 8);
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v21;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  InformationFile = FltCreateFile(
                      v16,
                      v15,
                      &FileHandle,
                      (v12 & 0x10) != 0 ? -1055719424 : -1072693248,
                      &ObjectAttributes,
                      &IoStatusBlock,
                      0,
                      0x80u,
                      7u,
                      3u,
                      0x204020u,
                      0,
                      0,
                      0x800u);
  if ( InformationFile >= 0 )
  {
    if ( !v13
      || (v17 = *(struct _FLT_INSTANCE **)(a2 + 24),
          LODWORD(v25) = v12,
          InformationFile = FltSetInformationFile(v17, a4, FileInformation, 0x28u, FileBasicInformation),
          InformationFile >= 0) )
    {
      v18 = 0;
      *a5 = FileHandle;
      FileHandle = 0;
      goto LABEL_10;
    }
  }
LABEL_9:
  v18 = FileHandle;
LABEL_10:
  if ( v18 )
    FltClose(v18);
  return (unsigned int)InformationFile;
}

```

## disassembly

```asm
0x1400095c8  push    rbp
0x1400095ca  push    rbx
0x1400095cb  push    rsi
0x1400095cc  push    rdi
0x1400095cd  push    r12
0x1400095cf  push    r14
0x1400095d1  push    r15
0x1400095d3  lea     rbp, [rsp-1Fh]
0x1400095d8  sub     rsp, 100h
0x1400095df  mov     rax, cs:__security_cookie
0x1400095e6  xor     rax, rsp
0x1400095e9  mov     [rbp+4Fh+var_40], rax
0x1400095ed  mov     rcx, [rcx+28h]
0x1400095f1  xorps   xmm0, xmm0
0x1400095f4  mov     r12, [rbp+4Fh+arg_20]
0x1400095f8  xor     eax, eax
0x1400095fa  xorps   xmm1, xmm1
0x1400095fd  mov     [rbp+4Fh+var_48], rax
0x140009601  movups  [rbp+4Fh+FileInformation], xmm0
0x140009605  mov     [rbp+4Fh+FileHandle], rax
0x140009609  mov     rsi, rdx
0x14000960c  movups  [rbp+4Fh+var_58], xmm0
0x140009610  mov     r15, r9
0x140009613  mov     [rsp+130h+LengthReturned], 0; LengthReturned
0x14000961c  movups  xmmword ptr [rbp+4Fh+IoStatusBlock], xmm0
0x140009620  mov     r9d, 28h ; '('; Length
0x140009626  mov     rdx, r15; FileObject
0x140009629  movups  xmm0, xmmword ptr [r8+8]
0x14000962e  lea     r8, [rbp+4Fh+FileInformation]; FileInformation
0x140009632  mov     [rsp+130h+FileInformationClass], 4; FileInformationClass
0x14000963a  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm1
0x14000963e  movups  [rbp+4Fh+var_B8], xmm0
0x140009642  movd    eax, xmm0
0x140009646  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm1
0x14000964a  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm1
0x14000964e  sub     ax, [rcx+6]
0x140009652  mov     rcx, [rsi+18h]; Instance
0x140009656  mov     word ptr [rbp+4Fh+var_B8], ax
0x14000965a  call    cs:__imp_FltQueryInformationFile
0x140009661  nop     dword ptr [rax+rax+00h]
0x140009666  mov     ebx, eax
0x140009668  test    eax, eax
0x14000966a  js      loc_1400097A8
0x140009670  mov     edi, dword ptr [rbp+4Fh+var_48]
0x140009673  xor     r14b, r14b
0x140009676  test    dil, 1
0x14000967a  jz      short loc_1400096B6
0x14000967c  mov     rcx, [rsi+18h]; Instance
0x140009680  lea     r8, [rbp+4Fh+FileInformation]; FileInformation
0x140009684  mov     eax, edi
0x140009686  mov     [rsp+130h+FileInformationClass], 4; FileInformationClass
0x14000968e  and     eax, 0FFFFFFFEh
0x140009691  mov     r9d, 28h ; '('; Length
0x140009697  mov     rdx, r15; FileObject
0x14000969a  mov     dword ptr [rbp+4Fh+var_48], eax
0x14000969d  call    cs:__imp_FltSetInformationFile
0x1400096a4  nop     dword ptr [rax+rax+00h]
0x1400096a9  mov     ebx, eax
0x1400096ab  test    eax, eax
0x1400096ad  js      loc_1400097A8
0x1400096b3  mov     r14b, 1
0x1400096b6  mov     rdx, [rsi+18h]; Instance
0x1400096ba  lea     rax, [rbp+4Fh+var_B8]
0x1400096be  mov     rcx, [rsi+8]; Filter
0x1400096c2  lea     r8, [rbp+4Fh+FileHandle]; FileHandle
0x1400096c6  mov     [rsp+130h+Flags], 800h; Flags
0x1400096ce  xorps   xmm0, xmm0
0x1400096d1  mov     [rsp+130h+EaLength], 0; EaLength
0x1400096d9  mov     [rsp+130h+EaBuffer], 0; EaBuffer
0x1400096e2  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x1400096e6  mov     eax, edi
0x1400096e8  mov     [rsp+130h+CreateOptions], 204020h; CreateOptions
0x1400096f0  and     al, 10h
0x1400096f2  mov     [rsp+130h+CreateDisposition], 3; CreateDisposition
0x1400096fa  neg     al
0x1400096fc  mov     [rsp+130h+ShareAccess], 7; ShareAccess
0x140009704  lea     rax, [rbp+4Fh+IoStatusBlock]
0x140009708  sbb     r9d, r9d
0x14000970b  mov     [rsp+130h+FileAttributes], 80h; FileAttributes
0x140009713  mov     [rsp+130h+AllocationSize], 0; AllocationSize
0x14000971c  and     r9d, 1030000h
0x140009723  mov     [rsp+130h+LengthReturned], rax; IoStatusBlock
0x140009728  add     r9d, 0C0100000h; DesiredAccess
0x14000972f  lea     rax, [rbp+4Fh+ObjectAttributes]
0x140009733  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x14000973a  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], 0
0x140009742  mov     [rbp+4Fh+ObjectAttributes.Attributes], 240h
0x140009749  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x14000974e  mov     qword ptr [rsp+130h+FileInformationClass], rax; ObjectAttributes
0x140009753  call    cs:__imp_FltCreateFile
0x14000975a  nop     dword ptr [rax+rax+00h]
0x14000975f  mov     ebx, eax
0x140009761  test    eax, eax
0x140009763  js      short loc_1400097A8
0x140009765  test    r14b, r14b
0x140009768  jz      short loc_140009798
0x14000976a  mov     rcx, [rsi+18h]; Instance
0x14000976e  lea     r8, [rbp+4Fh+FileInformation]; FileInformation
0x140009772  mov     r9d, 28h ; '('; Length
0x140009778  mov     dword ptr [rbp+4Fh+var_48], edi
0x14000977b  mov     rdx, r15; FileObject
0x14000977e  mov     [rsp+130h+FileInformationClass], 4; FileInformationClass
0x140009786  call    cs:__imp_FltSetInformationFile
0x14000978d  nop     dword ptr [rax+rax+00h]
0x140009792  mov     ebx, eax
0x140009794  test    eax, eax
0x140009796  js      short loc_1400097A8
0x140009798  mov     rax, [rbp+4Fh+FileHandle]
0x14000979c  xor     ecx, ecx
0x14000979e  mov     [r12], rax
0x1400097a2  mov     [rbp+4Fh+FileHandle], rcx
0x1400097a6  jmp     short loc_1400097AC
0x1400097a8  mov     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x1400097ac  test    rcx, rcx
0x1400097af  jz      short loc_1400097BD
0x1400097b1  call    cs:__imp_FltClose
0x1400097b8  nop     dword ptr [rax+rax+00h]
0x1400097bd  mov     eax, ebx
0x1400097bf  mov     rcx, [rbp+4Fh+var_40]
0x1400097c3  xor     rcx, rsp; StackCookie
0x1400097c6  call    __security_check_cookie
0x1400097cb  add     rsp, 100h
0x1400097d2  pop     r15
0x1400097d4  pop     r14
0x1400097d6  pop     r12
0x1400097d8  pop     rdi
0x1400097d9  pop     rsi
0x1400097da  pop     rbx
0x1400097db  pop     rbp
0x1400097dc  retn
```
