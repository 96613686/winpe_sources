# Smb2IsAccessAllowedEx

- ea: `0x140077628`
- end: `0x1400778aa`
- name: `Smb2IsAccessAllowedEx`
- size: `642`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG LengthNeeded, __int64, char)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140066300`
- `0x140066dc4`
- `0x140077378`

## callees

- `0x14001bd4c`
- `0x140077628`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140097775`
- `ntoskrnl!ExAllocatePool2` at `0x140097775`
- `ntoskrnl!ZwClose` at `0x14007779e`
- `ntoskrnl!ZwClose` at `0x140077872`
- `ntoskrnl!ZwClose` at `0x14007788a`
- `ntoskrnl!ZwClose` at `0x14009779b`
- `ntoskrnl!ZwClose` at `0x14007779e`
- `ntoskrnl!ZwClose` at `0x140077872`
- `ntoskrnl!ZwClose` at `0x14007788a`
- `ntoskrnl!ZwClose` at `0x14009779b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007785c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007785c`
- `ntoskrnl!IoCreateFile` at `0x1400776eb`
- `ntoskrnl!IoCreateFile` at `0x1400776eb`
- `ntoskrnl!NtQuerySecurityObject` at `0x14007771d`
- `ntoskrnl!NtQuerySecurityObject` at `0x14007771d`
- `srvnet!SrvLibSeAccessCheck` at `0x14007777d`
- `srvnet!SrvLibSeAccessCheck` at `0x14007777d`

## pseudocode

```c
__int64 __fastcall Smb2IsAccessAllowedEx(
        struct _UNICODE_STRING *a1,
        __int64 a2,
        __int64 *a3,
        unsigned int a4,
        ULONG LengthNeeded,
        void **a6,
        char a7)
{
  USHORT Length; // ax
  void *v10; // rax
  NTSTATUS v11; // eax
  unsigned int v12; // ecx
  NTSTATUS v13; // eax
  PWSTR Buffer; // rax
  unsigned __int64 v16; // rax
  __int64 v17; // rdx
  __int64 Pool2; // rax
  void *v19; // rcx
  struct _ECP_LIST *AllocationSize; // [rsp+20h] [rbp-91h]
  int FileAttributes; // [rsp+28h] [rbp-89h]
  ULONG Disposition; // [rsp+38h] [rbp-79h]
  ULONG Dispositiona; // [rsp+38h] [rbp-79h]
  int EaBuffer; // [rsp+48h] [rbp-69h]
  int EaLength; // [rsp+50h] [rbp-61h]
  CREATE_FILE_TYPE CreateFileType; // [rsp+58h] [rbp-59h]
  int InternalParameters; // [rsp+60h] [rbp-51h]
  ULONG Options; // [rsp+68h] [rbp-49h]
  int v29; // [rsp+80h] [rbp-31h] BYREF
  void *FileHandle; // [rsp+88h] [rbp-29h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+90h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-11h] BYREF
  unsigned int v33; // [rsp+100h] [rbp+4Fh] BYREF

  v33 = 0;
  Length = a1->Length;
  FileHandle = 0;
  LengthNeeded = 0;
  v29 = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  if ( Length == 2 )
  {
    if ( *a1->Buffer == 46 )
      goto LABEL_26;
  }
  else if ( Length == 4 )
  {
    Buffer = a1->Buffer;
    if ( *Buffer == 46 && Buffer[1] == 46 )
    {
LABEL_26:
      if ( a6 )
        return 3221225485LL;
      return 0;
    }
  }
  v10 = *(void **)(a2 + 88);
  ObjectAttributes.ObjectName = a1;
  ObjectAttributes.RootDirectory = v10;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( a7 )
    v11 = Smb2CreateFileWithBypassEcp(
            &FileHandle,
            0x20000u,
            &ObjectAttributes,
            &IoStatusBlock,
            AllocationSize,
            FileAttributes,
            7u,
            Disposition,
            0x200000u,
            EaBuffer,
            EaLength,
            CreateFileType,
            InternalParameters,
            Options,
            0);
  else
    v11 = IoCreateFile(
            &FileHandle,
            0x20000u,
            &ObjectAttributes,
            &IoStatusBlock,
            0,
            0,
            7u,
            1u,
            0x200000u,
            0,
            0,
            CreateFileTypeNone,
            0,
            0);
  v33 = v11;
  v12 = v11;
  if ( v11 >= 0 )
  {
    while ( 1 )
    {
      v13 = NtQuerySecurityObject(FileHandle, 0x67u, (PSECURITY_DESCRIPTOR)*a3, *((_DWORD *)a3 + 2), &LengthNeeded);
      v33 = v13;
      if ( v13 != -1073741789 )
        break;
      if ( *a3 )
        ExFreePoolWithTag((PVOID)*a3, 0);
      Pool2 = ExAllocatePool2(258, LengthNeeded, 1647465292);
      *a3 = Pool2;
      if ( !Pool2 )
      {
        v19 = FileHandle;
        *((_DWORD *)a3 + 2) = 0;
        ZwClose(v19);
        return 3221225626LL;
      }
      *((_DWORD *)a3 + 2) = LengthNeeded;
    }
    if ( v13 < 0 )
    {
      ZwClose(FileHandle);
      return v33;
    }
    LOBYTE(Dispositiona) = 1;
    if ( !(unsigned __int8)SrvLibSeAccessCheck(
                             *a3,
                             a3 + 2,
                             0,
                             a4,
                             0,
                             0,
                             &Smb2FileAccessMapping,
                             Dispositiona,
                             &v29,
                             0,
                             &v33) )
    {
      ZwClose(FileHandle);
      ++*(_DWORD *)(Srv2Statistics + 52);
      return 3221225506LL;
    }
    if ( a6 )
      *a6 = FileHandle;
    else
      ZwClose(FileHandle);
    return 0;
  }
  v16 = (unsigned int)(v11 + 1073741772);
  if ( (unsigned int)v16 <= 0x22 )
  {
    v17 = 0x400008001LL;
    if ( _bittest64(&v17, v16) )
    {
      v33 = -1073741790;
      ++*(_DWORD *)(Srv2Statistics + 52);
      return v33;
    }
  }
  return v12;
}

```

## disassembly

```asm
0x140077628  push    rbp
0x14007762a  push    rbx
0x14007762b  push    rsi
0x14007762c  push    rdi
0x14007762d  lea     rbp, [rsp-27h]
0x140077632  sub     rsp, 0D8h
0x140077639  xor     esi, esi
0x14007763b  xorps   xmm0, xmm0
0x14007763e  xor     eax, eax
0x140077640  mov     [rbp+3Fh+arg_0], esi
0x140077643  movzx   eax, word ptr [rcx]
0x140077646  mov     edi, r9d
0x140077649  mov     [rbp+3Fh+FileHandle], rsi
0x14007764d  mov     rbx, r8
0x140077650  mov     [rbp+3Fh+LengthNeeded], esi
0x140077653  mov     [rbp+3Fh+var_70], esi
0x140077656  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.ObjectName], xmm0
0x14007765a  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.Length], xmm0
0x14007765e  movups  xmmword ptr [rbp+3Fh+ObjectAttributes+1Ch], xmm0
0x140077662  movups  xmmword ptr [rbp+3Fh+IoStatusBlock], xmm0
0x140077666  cmp     ax, 2
0x14007766a  jz      loc_1400777E1
0x140077670  cmp     ax, 4
0x140077674  jz      loc_1400777F4
0x14007767a  lea     r9, [rbp+3Fh+IoStatusBlock]; IoStatusBlock
0x14007767e  mov     rax, [rdx+58h]
0x140077682  lea     r8, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x140077686  mov     [rbp+3Fh+ObjectAttributes.ObjectName], rcx
0x14007768a  lea     rcx, [rbp+3Fh+FileHandle]; FileHandle
0x14007768e  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], rax
0x140077692  mov     edx, 20000h; DesiredAccess
0x140077697  mov     [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x14007769e  mov     [rbp+3Fh+ObjectAttributes.Attributes], 240h
0x1400776a5  movdqu  xmmword ptr [rbp+3Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x1400776aa  cmp     [rbp+3Fh+arg_30], sil
0x1400776ae  jnz     loc_1400777B9
0x1400776b4  mov     [rsp+0F0h+Options], esi; Options
0x1400776b8  mov     [rsp+0F0h+InternalParameters], rsi; InternalParameters
0x1400776bd  mov     [rsp+0F0h+CreateFileType], esi; CreateFileType
0x1400776c1  mov     [rsp+0F0h+EaLength], esi; EaLength
0x1400776c5  mov     [rsp+0F0h+EaBuffer], rsi; EaBuffer
0x1400776ca  mov     [rsp+0F0h+CreateOptions], 200000h; CreateOptions
0x1400776d2  mov     [rsp+0F0h+Disposition], 1; Disposition
0x1400776da  mov     [rsp+0F0h+ShareAccess], 7; ShareAccess
0x1400776e2  mov     [rsp+0F0h+FileAttributes], esi; FileAttributes
0x1400776e6  mov     [rsp+0F0h+AllocationSize], rsi; AllocationSize
0x1400776eb  call    cs:__imp_IoCreateFile
0x1400776f2  nop     dword ptr [rax+rax+00h]
0x1400776f7  mov     [rbp+3Fh+arg_0], eax
0x1400776fa  mov     ecx, eax
0x1400776fc  test    eax, eax
0x1400776fe  js      loc_140077812
0x140077704  mov     r9d, [rbx+8]; Length
0x140077708  lea     rax, [rbp+3Fh+LengthNeeded]
0x14007770c  mov     r8, [rbx]; SecurityDescriptor
0x14007770f  mov     edx, 67h ; 'g'; SecurityInformation
0x140077714  mov     rcx, [rbp+3Fh+FileHandle]; Handle
0x140077718  mov     [rsp+0F0h+AllocationSize], rax; LengthNeeded
0x14007771d  call    cs:__imp_NtQuerySecurityObject
0x140077724  nop     dword ptr [rax+rax+00h]
0x140077729  mov     [rbp+3Fh+arg_0], eax
0x14007772c  cmp     eax, 0C0000023h
0x140077731  jz      loc_14007784E
0x140077737  test    eax, eax
0x140077739  js      loc_14007786E
0x14007773f  mov     rcx, [rbx]
0x140077742  lea     rax, [rbp+3Fh+arg_0]
0x140077746  mov     qword ptr [rsp+0F0h+EaLength], rax
0x14007774b  lea     rdx, [rbx+10h]
0x14007774f  mov     [rsp+0F0h+EaBuffer], rsi
0x140077754  lea     rax, [rbp+3Fh+var_70]
0x140077758  mov     qword ptr [rsp+0F0h+CreateOptions], rax
0x14007775d  mov     r9d, edi
0x140077760  mov     byte ptr [rsp+0F0h+Disposition], 1
0x140077765  lea     rax, Smb2FileAccessMapping
0x14007776c  mov     qword ptr [rsp+0F0h+ShareAccess], rax
0x140077771  xor     r8d, r8d
0x140077774  mov     qword ptr [rsp+0F0h+FileAttributes], rsi
0x140077779  mov     dword ptr [rsp+0F0h+AllocationSize], esi
0x14007777d  call    cs:__imp_SrvLibSeAccessCheck
0x140077784  nop     dword ptr [rax+rax+00h]
0x140077789  test    al, al
0x14007778b  jz      loc_140077886
0x140077791  mov     rcx, [rbp+3Fh+arg_28]
0x140077795  test    rcx, rcx
0x140077798  jnz     short loc_1400777D8
0x14007779a  mov     rcx, [rbp+3Fh+FileHandle]; Handle
0x14007779e  call    cs:__imp_ZwClose
0x1400777a5  nop     dword ptr [rax+rax+00h]
0x1400777aa  xor     eax, eax
0x1400777ac  add     rsp, 0D8h
0x1400777b3  pop     rdi
0x1400777b4  pop     rsi
0x1400777b5  pop     rbx
0x1400777b6  pop     rbp
0x1400777b7  retn
0x1400777b9  mov     [rsp+0F0h+var_80], rsi; __int64
0x1400777be  mov     [rsp+0F0h+CreateOptions], 200000h; ULONG
0x1400777c6  mov     [rsp+0F0h+ShareAccess], 7; ULONG
0x1400777ce  call    Smb2CreateFileWithBypassEcp
0x1400777d3  jmp     loc_1400776F7
0x1400777d8  mov     rax, [rbp+3Fh+FileHandle]
0x1400777dc  mov     [rcx], rax
0x1400777df  jmp     short loc_1400777AA
0x1400777e1  mov     rax, [rcx+8]
0x1400777e5  cmp     word ptr [rax], 2Eh ; '.'
0x1400777e9  jz      loc_14009774C
0x1400777ef  jmp     loc_14007767A
0x1400777f4  mov     rax, [rcx+8]
0x1400777f8  cmp     word ptr [rax], 2Eh ; '.'
0x1400777fc  jnz     loc_14007767A
0x140077802  cmp     word ptr [rax+2], 2Eh ; '.'
0x140077807  jnz     loc_14007767A
0x14007780d  jmp     loc_14009774C
0x140077812  lea     eax, [rcx+3FFFFFCCh]
0x140077818  cmp     eax, 22h ; '"'
0x14007781b  ja      loc_140097760
0x140077821  mov     rdx, 400008001h
0x14007782b  bt      rdx, rax
0x14007782f  jnb     loc_140097760
0x140077835  mov     rax, cs:Srv2Statistics
0x14007783c  mov     [rbp+3Fh+arg_0], 0C0000022h
0x140077843  inc     dword ptr [rax+34h]
0x140077846  mov     ecx, [rbp+3Fh+arg_0]
0x140077849  jmp     loc_140097760
0x14007784e  mov     rcx, [rbx]; P
0x140077851  test    rcx, rcx
0x140077854  jz      loc_140097767
0x14007785a  xor     edx, edx; Tag
0x14007785c  call    cs:__imp_ExFreePoolWithTag
0x140077863  nop     dword ptr [rax+rax+00h]
0x140077868  nop
0x140077869  jmp     loc_140097767
0x14007786e  mov     rcx, [rbp+3Fh+FileHandle]; Handle
0x140077872  call    cs:__imp_ZwClose
0x140077879  nop     dword ptr [rax+rax+00h]
0x14007787e  mov     eax, [rbp+3Fh+arg_0]
0x140077881  jmp     loc_1400777AC
0x140077886  mov     rcx, [rbp+3Fh+FileHandle]; Handle
0x14007788a  call    cs:__imp_ZwClose
0x140077891  nop     dword ptr [rax+rax+00h]
0x140077896  mov     rax, cs:Srv2Statistics
0x14007789d  inc     dword ptr [rax+34h]
0x1400778a0  mov     eax, 0C0000022h
0x1400778a5  jmp     loc_1400777AC
0x14009774c  cmp     [rbp+3Fh+arg_28], rsi
0x140097750  jz      loc_1400777AA
0x140097756  mov     eax, 0C000000Dh
0x14009775b  jmp     loc_1400777AC
0x140097760  mov     eax, ecx
0x140097762  jmp     loc_1400777AC
0x140097767  mov     edx, [rbp+3Fh+LengthNeeded]
0x14009776a  mov     ecx, 102h
0x14009776f  mov     r8d, 6232534Ch
0x140097775  call    cs:__imp_ExAllocatePool2
0x14009777c  nop     dword ptr [rax+rax+00h]
0x140097781  mov     [rbx], rax
0x140097784  test    rax, rax
0x140097787  jz      short loc_140097794
0x140097789  mov     eax, [rbp+3Fh+LengthNeeded]
0x14009778c  mov     [rbx+8], eax
0x14009778f  jmp     loc_140077704
0x140097794  mov     rcx, [rbp+3Fh+FileHandle]; Handle
0x140097798  mov     [rbx+8], esi
0x14009779b  call    cs:__imp_ZwClose
0x1400977a2  nop     dword ptr [rax+rax+00h]
0x1400977a7  mov     eax, 0C000009Ah
0x1400977ac  jmp     loc_1400777AC
```
