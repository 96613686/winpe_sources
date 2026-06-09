# WofOpenReparseIndex

- ea: `0x14000bcbc`
- end: `0x14000becb`
- name: `WofOpenReparseIndex`
- size: `527`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140023ec4`
- `0x14003ec00`

## callees

- `0x14000bcbc`
- `0x1400116c0`

## import_xrefs

- `ntoskrnl!IoGetSiloParameters` at `0x14000bdbb`
- `ntoskrnl!IoGetSiloParameters` at `0x14000bdbb`
- `ntoskrnl!PsGetHostSilo` at `0x14000bdd2`
- `ntoskrnl!PsGetHostSilo` at `0x14000bdd2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000be8d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000be8d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000bd3e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000bd3e`
- `FLTMGR!FltCreateFileEx2` at `0x14000be79`
- `FLTMGR!FltCreateFileEx2` at `0x14000be79`

## string_xrefs

- `0x14000bd7c`: `\$Extend\$Reparse:$R:$INDEX_ALLOCATION`

## pseudocode

```c
__int64 __fastcall WofOpenReparseIndex(__int64 a1, __int64 a2, PFILE_OBJECT *a3, void **a4)
{
  int v4; // esi
  unsigned int v8; // esi
  NTSTATUS v10; // ebx
  size_t v11; // r8
  const void *v12; // rdx
  __int64 SiloParameters; // rax
  __int64 HostSilo; // rax
  struct _FLT_INSTANCE *v15; // rdx
  struct _FLT_FILTER *v16; // rcx
  PVOID P[2]; // [rsp+80h] [rbp-49h] BYREF
  void *FileHandle; // [rsp+90h] [rbp-39h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+98h] [rbp-31h] BYREF
  __int64 v21; // [rsp+B8h] [rbp-11h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C0h] [rbp-9h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+F0h] [rbp+27h] BYREF
  PFILE_OBJECT FileObject; // [rsp+130h] [rbp+67h] BYREF

  v4 = *(unsigned __int16 *)(a1 + 64);
  FileHandle = 0;
  FileObject = 0;
  v8 = v4 + 76;
  LOWORD(v21) = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  *(_OWORD *)P = 0;
  memset(&DriverContext, 0, sizeof(DriverContext));
  if ( v8 < 0xFFFF )
  {
    P[1] = ExAllocatePoolWithTag(PagedPool, v8, 0x47666F57u);
    if ( P[1] )
    {
      v11 = *(unsigned __int16 *)(a1 + 64);
      v12 = *(const void **)(a1 + 72);
      LOWORD(P[0]) = 0;
      WORD1(P[0]) = v8;
      memmove(P[1], v12, v11);
      memmove((char *)P[1] + *(unsigned __int16 *)(a1 + 64), L"\\$Extend\\$Reparse:$R:$INDEX_ALLOCATION", 0x4Cu);
      LOWORD(P[0]) = *(_WORD *)(a1 + 64) + 76;
      memset(&DriverContext, 0, sizeof(DriverContext));
      DriverContext.Size = 40;
      v21 = 1;
      if ( a2 )
      {
        SiloParameters = IoGetSiloParameters(a2);
        if ( SiloParameters )
          HostSilo = *(_QWORD *)(SiloParameters + 8);
        else
          HostSilo = PsGetHostSilo();
        v21 = HostSilo;
      }
      v15 = *(struct _FLT_INSTANCE **)(a1 + 120);
      v16 = *(struct _FLT_FILTER **)(a1 + 104);
      ObjectAttributes.ObjectName = (PUNICODE_STRING)P;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v10 = FltCreateFileEx2(
              v16,
              v15,
              &FileHandle,
              &FileObject,
              0x100001u,
              &ObjectAttributes,
              &IoStatusBlock,
              0,
              0,
              7u,
              1u,
              0x200021u,
              0,
              0,
              0,
              &DriverContext);
      ExFreePoolWithTag(P[1], 0);
      if ( v10 >= 0 )
      {
        *a3 = FileObject;
        *a4 = FileHandle;
      }
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  else
  {
    return (unsigned int)-1073741773;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14000bcbc  mov     [rsp-8+arg_8], rbx
0x14000bcc1  mov     [rsp-8+arg_10], rsi
0x14000bcc6  push    rbp
0x14000bcc7  push    rdi
0x14000bcc8  push    r12
0x14000bcca  push    r14
0x14000bccc  push    r15
0x14000bcce  lea     rbp, [rsp-37h]
0x14000bcd3  sub     rsp, 100h
0x14000bcda  movzx   esi, word ptr [rcx+40h]
0x14000bcde  xorps   xmm0, xmm0
0x14000bce1  xor     eax, eax
0x14000bce3  mov     r15, r9
0x14000bce6  movups  xmmword ptr [rbp+57h+var_60.ObjectName], xmm0
0x14000bcea  mov     dword ptr [rbp+57h+P+4], eax
0x14000bced  mov     r12, r8
0x14000bcf0  mov     r14, rdx
0x14000bcf3  mov     [rbp+57h+FileHandle], rax
0x14000bcf7  lea     edi, [rax+4Ch]
0x14000bcfa  mov     [rbp+57h+FileObject], rax
0x14000bcfe  add     esi, edi
0x14000bd00  mov     word ptr [rbp+57h+var_68], ax
0x14000bd04  mov     rbx, rcx
0x14000bd07  movups  xmmword ptr [rbp+57h+var_60.Length], xmm0
0x14000bd0b  movups  xmmword ptr [rbp+57h+var_60+1Ch], xmm0
0x14000bd0f  movups  xmmword ptr [rbp+57h+var_30], xmm0
0x14000bd13  movups  xmmword ptr [rbp+57h+P], xmm0
0x14000bd17  movups  xmmword ptr [rbp+57h+var_88.Size], xmm0
0x14000bd1b  movups  xmmword ptr [rbp+57h+var_88.DeviceObjectHint], xmm0
0x14000bd1f  cmp     esi, 0FFFFh
0x14000bd25  jb      short loc_14000BD31
0x14000bd27  mov     ebx, 0C0000033h
0x14000bd2c  jmp     loc_14000BEAC
0x14000bd31  mov     edx, esi; NumberOfBytes
0x14000bd33  mov     ecx, 1; PoolType
0x14000bd38  mov     r8d, 47666F57h; Tag
0x14000bd3e  call    cs:__imp_ExAllocatePoolWithTag
0x14000bd45  nop     dword ptr [rax+rax+00h]
0x14000bd4a  mov     [rbp+57h+P+8], rax
0x14000bd4e  mov     rcx, rax; void *
0x14000bd51  test    rax, rax
0x14000bd54  jnz     short loc_14000BD60
0x14000bd56  mov     ebx, 0C000009Ah
0x14000bd5b  jmp     loc_14000BEAC
0x14000bd60  movzx   r8d, word ptr [rbx+40h]; Size
0x14000bd65  xor     eax, eax
0x14000bd67  mov     rdx, [rbx+48h]; Src
0x14000bd6b  mov     word ptr [rbp+57h+P], ax
0x14000bd6f  mov     word ptr [rbp+57h+P+2], si
0x14000bd73  call    memmove
0x14000bd78  movzx   ecx, word ptr [rbx+40h]
0x14000bd7c  lea     rdx, aExtendReparseR; "\\$Extend\\$Reparse:$R:$INDEX_ALLOCATIO"...
0x14000bd83  add     rcx, [rbp+57h+P+8]; void *
0x14000bd87  movzx   r8d, di; Size
0x14000bd8b  call    memmove
0x14000bd90  add     di, [rbx+40h]
0x14000bd94  mov     eax, 28h ; '('
0x14000bd99  mov     word ptr [rbp+57h+P], di
0x14000bd9d  xorps   xmm0, xmm0
0x14000bda0  movups  xmmword ptr [rbp+57h+var_88.Size], xmm0
0x14000bda4  mov     [rbp+57h+var_88.Size], ax
0x14000bda8  lea     edi, [rax-27h]
0x14000bdab  mov     [rbp+57h+var_68], rdi
0x14000bdaf  movups  xmmword ptr [rbp+57h+var_88.DeviceObjectHint], xmm0
0x14000bdb3  test    r14, r14
0x14000bdb6  jz      short loc_14000BDE2
0x14000bdb8  mov     rcx, r14
0x14000bdbb  call    cs:__imp_IoGetSiloParameters
0x14000bdc2  nop     dword ptr [rax+rax+00h]
0x14000bdc7  test    rax, rax
0x14000bdca  jz      short loc_14000BDD2
0x14000bdcc  mov     rax, [rax+8]
0x14000bdd0  jmp     short loc_14000BDDE
0x14000bdd2  call    cs:__imp_PsGetHostSilo
0x14000bdd9  nop     dword ptr [rax+rax+00h]
0x14000bdde  mov     [rbp+57h+var_68], rax
0x14000bde2  mov     rdx, [rbx+78h]; Instance
0x14000bde6  lea     rax, [rbp+57h+P]
0x14000bdea  mov     rcx, [rbx+68h]; Filter
0x14000bdee  lea     r9, [rbp+57h+FileObject]; FileObject
0x14000bdf2  mov     [rbp+57h+var_60.ObjectName], rax
0x14000bdf6  lea     r8, [rbp+57h+FileHandle]; FileHandle
0x14000bdfa  lea     rax, [rbp+57h+var_88]
0x14000bdfe  mov     [rbp+57h+var_60.Length], 30h ; '0'
0x14000be05  mov     [rsp+120h+DriverContext], rax; DriverContext
0x14000be0a  xorps   xmm0, xmm0
0x14000be0d  mov     [rsp+120h+Flags], 0; Flags
0x14000be15  lea     rax, [rbp+57h+var_30]
0x14000be19  mov     [rsp+120h+EaLength], 0; EaLength
0x14000be21  mov     [rsp+120h+EaBuffer], 0; EaBuffer
0x14000be2a  mov     [rsp+120h+CreateOptions], 200021h; CreateOptions
0x14000be32  mov     [rsp+120h+CreateDisposition], edi; CreateDisposition
0x14000be36  mov     [rsp+120h+ShareAccess], 7; ShareAccess
0x14000be3e  mov     [rsp+120h+FileAttributes], 0; FileAttributes
0x14000be46  mov     [rsp+120h+AllocationSize], 0; AllocationSize
0x14000be4f  mov     [rsp+120h+IoStatusBlock], rax; IoStatusBlock
0x14000be54  lea     rax, [rbp+57h+var_60]
0x14000be58  mov     [rsp+120h+ObjectAttributes], rax; ObjectAttributes
0x14000be5d  mov     [rsp+120h+DesiredAccess], 100001h; DesiredAccess
0x14000be65  mov     [rbp+57h+var_60.RootDirectory], 0
0x14000be6d  mov     [rbp+57h+var_60.Attributes], 240h
0x14000be74  movdqu  xmmword ptr [rbp+57h+var_60.SecurityDescriptor], xmm0
0x14000be79  call    cs:__imp_FltCreateFileEx2
0x14000be80  nop     dword ptr [rax+rax+00h]
0x14000be85  mov     rcx, [rbp+57h+P+8]; P
0x14000be89  xor     edx, edx; Tag
0x14000be8b  mov     ebx, eax
0x14000be8d  call    cs:__imp_ExFreePoolWithTag
0x14000be94  nop     dword ptr [rax+rax+00h]
0x14000be99  test    ebx, ebx
0x14000be9b  js      short loc_14000BEAC
0x14000be9d  mov     rcx, [rbp+57h+FileObject]
0x14000bea1  mov     [r12], rcx
0x14000bea5  mov     rcx, [rbp+57h+FileHandle]
0x14000bea9  mov     [r15], rcx
0x14000beac  lea     r11, [rsp+120h+var_20]
0x14000beb4  mov     eax, ebx
0x14000beb6  mov     rbx, [r11+38h]
0x14000beba  mov     rsi, [r11+40h]
0x14000bebe  mov     rsp, r11
0x14000bec1  pop     r15
0x14000bec3  pop     r14
0x14000bec5  pop     r12
0x14000bec7  pop     rdi
0x14000bec8  pop     rbp
0x14000bec9  retn
```
