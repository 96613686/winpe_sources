# Smb2IsAccessAllowedEx

- ea: `0x140077678`
- end: `0x1400778fa`
- name: `Smb2IsAccessAllowedEx`
- size: `642`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG LengthNeeded, __int64, char)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140066300`
- `0x140066dc4`
- `0x1400773c8`

## callees

- `0x14001bd4c`
- `0x140077678`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400977c5`
- `ntoskrnl!ExAllocatePool2` at `0x1400977c5`
- `ntoskrnl!ZwClose` at `0x1400777ee`
- `ntoskrnl!ZwClose` at `0x1400778c2`
- `ntoskrnl!ZwClose` at `0x1400778da`
- `ntoskrnl!ZwClose` at `0x1400977eb`
- `ntoskrnl!ZwClose` at `0x1400777ee`
- `ntoskrnl!ZwClose` at `0x1400778c2`
- `ntoskrnl!ZwClose` at `0x1400778da`
- `ntoskrnl!ZwClose` at `0x1400977eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400778ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400778ac`
- `ntoskrnl!IoCreateFile` at `0x14007773b`
- `ntoskrnl!IoCreateFile` at `0x14007773b`
- `ntoskrnl!NtQuerySecurityObject` at `0x14007776d`
- `ntoskrnl!NtQuerySecurityObject` at `0x14007776d`
- `srvnet!SrvLibSeAccessCheck` at `0x1400777cd`
- `srvnet!SrvLibSeAccessCheck` at `0x1400777cd`

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
0x140077678  push    rbp
0x14007767a  push    rbx
0x14007767b  push    rsi
0x14007767c  push    rdi
0x14007767d  lea     rbp, [rsp-27h]
0x140077682  sub     rsp, 0D8h
0x140077689  xor     esi, esi
0x14007768b  xorps   xmm0, xmm0
0x14007768e  xor     eax, eax
0x140077690  mov     [rbp+3Fh+arg_0], esi
0x140077693  movzx   eax, word ptr [rcx]
0x140077696  mov     edi, r9d
0x140077699  mov     [rbp+3Fh+FileHandle], rsi
0x14007769d  mov     rbx, r8
0x1400776a0  mov     [rbp+3Fh+LengthNeeded], esi
0x1400776a3  mov     [rbp+3Fh+var_70], esi
0x1400776a6  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.ObjectName], xmm0
0x1400776aa  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.Length], xmm0
0x1400776ae  movups  xmmword ptr [rbp+3Fh+ObjectAttributes+1Ch], xmm0
0x1400776b2  movups  xmmword ptr [rbp+3Fh+IoStatusBlock], xmm0
0x1400776b6  cmp     ax, 2
0x1400776ba  jz      loc_140077831
0x1400776c0  cmp     ax, 4
0x1400776c4  jz      loc_140077844
0x1400776ca  lea     r9, [rbp+3Fh+IoStatusBlock]; IoStatusBlock
0x1400776ce  mov     rax, [rdx+58h]
0x1400776d2  lea     r8, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x1400776d6  mov     [rbp+3Fh+ObjectAttributes.ObjectName], rcx
0x1400776da  lea     rcx, [rbp+3Fh+FileHandle]; FileHandle
0x1400776de  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], rax
0x1400776e2  mov     edx, 20000h; DesiredAccess
0x1400776e7  mov     [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x1400776ee  mov     [rbp+3Fh+ObjectAttributes.Attributes], 240h
0x1400776f5  movdqu  xmmword ptr [rbp+3Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x1400776fa  cmp     [rbp+3Fh+arg_30], sil
0x1400776fe  jnz     loc_140077809
0x140077704  mov     [rsp+0F0h+Options], esi; Options
0x140077708  mov     [rsp+0F0h+InternalParameters], rsi; InternalParameters
0x14007770d  mov     [rsp+0F0h+CreateFileType], esi; CreateFileType
0x140077711  mov     [rsp+0F0h+EaLength], esi; EaLength
0x140077715  mov     [rsp+0F0h+EaBuffer], rsi; EaBuffer
0x14007771a  mov     [rsp+0F0h+CreateOptions], 200000h; CreateOptions
0x140077722  mov     [rsp+0F0h+Disposition], 1; Disposition
0x14007772a  mov     [rsp+0F0h+ShareAccess], 7; ShareAccess
0x140077732  mov     [rsp+0F0h+FileAttributes], esi; FileAttributes
0x140077736  mov     [rsp+0F0h+AllocationSize], rsi; AllocationSize
0x14007773b  call    cs:__imp_IoCreateFile
0x140077742  nop     dword ptr [rax+rax+00h]
0x140077747  mov     [rbp+3Fh+arg_0], eax
0x14007774a  mov     ecx, eax
0x14007774c  test    eax, eax
0x14007774e  js      loc_140077862
0x140077754  mov     r9d, [rbx+8]; Length
0x140077758  lea     rax, [rbp+3Fh+LengthNeeded]
0x14007775c  mov     r8, [rbx]; SecurityDescriptor
0x14007775f  mov     edx, 67h ; 'g'; SecurityInformation
0x140077764  mov     rcx, [rbp+3Fh+FileHandle]; Handle
0x140077768  mov     [rsp+0F0h+AllocationSize], rax; LengthNeeded
0x14007776d  call    cs:__imp_NtQuerySecurityObject
0x140077774  nop     dword ptr [rax+rax+00h]
0x140077779  mov     [rbp+3Fh+arg_0], eax
0x14007777c  cmp     eax, 0C0000023h
0x140077781  jz      loc_14007789E
0x140077787  test    eax, eax
0x140077789  js      loc_1400778BE
0x14007778f  mov     rcx, [rbx]
0x140077792  lea     rax, [rbp+3Fh+arg_0]
0x140077796  mov     qword ptr [rsp+0F0h+EaLength], rax
0x14007779b  lea     rdx, [rbx+10h]
0x14007779f  mov     [rsp+0F0h+EaBuffer], rsi
0x1400777a4  lea     rax, [rbp+3Fh+var_70]
0x1400777a8  mov     qword ptr [rsp+0F0h+CreateOptions], rax
0x1400777ad  mov     r9d, edi
0x1400777b0  mov     byte ptr [rsp+0F0h+Disposition], 1
0x1400777b5  lea     rax, Smb2FileAccessMapping
0x1400777bc  mov     qword ptr [rsp+0F0h+ShareAccess], rax
0x1400777c1  xor     r8d, r8d
0x1400777c4  mov     qword ptr [rsp+0F0h+FileAttributes], rsi
0x1400777c9  mov     dword ptr [rsp+0F0h+AllocationSize], esi
0x1400777cd  call    cs:__imp_SrvLibSeAccessCheck
0x1400777d4  nop     dword ptr [rax+rax+00h]
0x1400777d9  test    al, al
0x1400777db  jz      loc_1400778D6
0x1400777e1  mov     rcx, [rbp+3Fh+arg_28]
0x1400777e5  test    rcx, rcx
0x1400777e8  jnz     short loc_140077828
0x1400777ea  mov     rcx, [rbp+3Fh+FileHandle]; Handle
0x1400777ee  call    cs:__imp_ZwClose
0x1400777f5  nop     dword ptr [rax+rax+00h]
0x1400777fa  xor     eax, eax
0x1400777fc  add     rsp, 0D8h
0x140077803  pop     rdi
0x140077804  pop     rsi
0x140077805  pop     rbx
0x140077806  pop     rbp
0x140077807  retn
0x140077809  mov     [rsp+0F0h+var_80], rsi; __int64
0x14007780e  mov     [rsp+0F0h+CreateOptions], 200000h; ULONG
0x140077816  mov     [rsp+0F0h+ShareAccess], 7; ULONG
0x14007781e  call    Smb2CreateFileWithBypassEcp
0x140077823  jmp     loc_140077747
0x140077828  mov     rax, [rbp+3Fh+FileHandle]
0x14007782c  mov     [rcx], rax
0x14007782f  jmp     short loc_1400777FA
0x140077831  mov     rax, [rcx+8]
0x140077835  cmp     word ptr [rax], 2Eh ; '.'
0x140077839  jz      loc_14009779C
0x14007783f  jmp     loc_1400776CA
0x140077844  mov     rax, [rcx+8]
0x140077848  cmp     word ptr [rax], 2Eh ; '.'
0x14007784c  jnz     loc_1400776CA
0x140077852  cmp     word ptr [rax+2], 2Eh ; '.'
0x140077857  jnz     loc_1400776CA
0x14007785d  jmp     loc_14009779C
0x140077862  lea     eax, [rcx+3FFFFFCCh]
0x140077868  cmp     eax, 22h ; '"'
0x14007786b  ja      loc_1400977B0
0x140077871  mov     rdx, 400008001h
0x14007787b  bt      rdx, rax
0x14007787f  jnb     loc_1400977B0
0x140077885  mov     rax, cs:Srv2Statistics
0x14007788c  mov     [rbp+3Fh+arg_0], 0C0000022h
0x140077893  inc     dword ptr [rax+34h]
0x140077896  mov     ecx, [rbp+3Fh+arg_0]
0x140077899  jmp     loc_1400977B0
0x14007789e  mov     rcx, [rbx]; P
0x1400778a1  test    rcx, rcx
0x1400778a4  jz      loc_1400977B7
0x1400778aa  xor     edx, edx; Tag
0x1400778ac  call    cs:__imp_ExFreePoolWithTag
0x1400778b3  nop     dword ptr [rax+rax+00h]
0x1400778b8  nop
0x1400778b9  jmp     loc_1400977B7
0x1400778be  mov     rcx, [rbp+3Fh+FileHandle]; Handle
0x1400778c2  call    cs:__imp_ZwClose
0x1400778c9  nop     dword ptr [rax+rax+00h]
0x1400778ce  mov     eax, [rbp+3Fh+arg_0]
0x1400778d1  jmp     loc_1400777FC
0x1400778d6  mov     rcx, [rbp+3Fh+FileHandle]; Handle
0x1400778da  call    cs:__imp_ZwClose
0x1400778e1  nop     dword ptr [rax+rax+00h]
0x1400778e6  mov     rax, cs:Srv2Statistics
0x1400778ed  inc     dword ptr [rax+34h]
0x1400778f0  mov     eax, 0C0000022h
0x1400778f5  jmp     loc_1400777FC
0x14009779c  cmp     [rbp+3Fh+arg_28], rsi
0x1400977a0  jz      loc_1400777FA
0x1400977a6  mov     eax, 0C000000Dh
0x1400977ab  jmp     loc_1400777FC
0x1400977b0  mov     eax, ecx
0x1400977b2  jmp     loc_1400777FC
0x1400977b7  mov     edx, [rbp+3Fh+LengthNeeded]
0x1400977ba  mov     ecx, 102h
0x1400977bf  mov     r8d, 6232534Ch
0x1400977c5  call    cs:__imp_ExAllocatePool2
0x1400977cc  nop     dword ptr [rax+rax+00h]
0x1400977d1  mov     [rbx], rax
0x1400977d4  test    rax, rax
0x1400977d7  jz      short loc_1400977E4
0x1400977d9  mov     eax, [rbp+3Fh+LengthNeeded]
0x1400977dc  mov     [rbx+8], eax
0x1400977df  jmp     loc_140077754
0x1400977e4  mov     rcx, [rbp+3Fh+FileHandle]; Handle
0x1400977e8  mov     [rbx+8], esi
0x1400977eb  call    cs:__imp_ZwClose
0x1400977f2  nop     dword ptr [rax+rax+00h]
0x1400977f7  mov     eax, 0C000009Ah
0x1400977fc  jmp     loc_1400777FC
```
