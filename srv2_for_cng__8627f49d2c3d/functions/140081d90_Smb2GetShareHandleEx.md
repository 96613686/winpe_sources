# Smb2GetShareHandleEx

- ea: `0x140081d90`
- end: `0x140081eb2`
- name: `Smb2GetShareHandleEx`
- size: `290`
- prototype: ``
- caller_count: `11`
- callee_count: `13`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140007400`
- `0x14000c070`
- `0x140063d84`
- `0x14006474c`
- `0x140064a74`
- `0x1400662b0`
- `0x140066d74`
- `0x14007a84c`
- `0x1400813b4`
- `0x140081b40`
- `0x140095f88`

## callees

- `0x140013810`
- `0x140015000`
- `0x14001bd4c`
- `0x14002019c`
- `0x140022958`
- `0x140029768`
- `0x140038680`
- `0x1400593dc`
- `0x140063d50`
- `0x140067d08`
- `0x140081d90`
- `0x14008d3f4`
- `0x140091e18`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140098ff6`
- `ntoskrnl!ExAllocatePool2` at `0x140098ff6`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140081e06`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140081e98`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140081e06`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140081e98`
- `ntoskrnl!ExReleaseResourceLite` at `0x140081e4b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140098bed`
- `ntoskrnl!ExReleaseResourceLite` at `0x140098c52`
- `ntoskrnl!ExReleaseResourceLite` at `0x140098eae`
- `ntoskrnl!ExReleaseResourceLite` at `0x140098f8a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14009912a`
- `ntoskrnl!ExReleaseResourceLite` at `0x140081e4b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140098bed`
- `ntoskrnl!ExReleaseResourceLite` at `0x140098c52`
- `ntoskrnl!ExReleaseResourceLite` at `0x140098eae`
- `ntoskrnl!ExReleaseResourceLite` at `0x140098f8a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14009912a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140098c02`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140098ec6`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140099087`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140098c02`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140098ec6`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140099087`
- `ntoskrnl!ZwClose` at `0x140098d51`
- `ntoskrnl!ZwClose` at `0x140098f53`
- `ntoskrnl!ZwClose` at `0x140098d51`
- `ntoskrnl!ZwClose` at `0x140098f53`
- `ntoskrnl!ExFreePoolWithTag` at `0x140098d27`
- `ntoskrnl!ExFreePoolWithTag` at `0x140098d27`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x140098c2c`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x140099117`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x140098c2c`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x140099117`
- `ntoskrnl!IoCreateFileEx` at `0x140098dc1`
- `ntoskrnl!IoCreateFileEx` at `0x140098dc1`
- `ntoskrnl!NtOpenFile` at `0x140098f24`
- `ntoskrnl!NtOpenFile` at `0x140098f24`

## pseudocode

```c
_QWORD *Smb2GetShareHandleEx(__int64 a1, _QWORD *a2, char a3, ...)
{
  bool v3; // zf
  unsigned int i; // esi
  __int64 v8; // rax
  _QWORD *v9; // rbx
  char v11; // dl
  struct _UNICODE_STRING **v12; // r15
  __int128 v13; // xmm6
  struct _ERESOURCE *v14; // rcx
  __int64 v15; // rax
  void *v16; // r13
  int VolumeUniqueID; // r12d
  PDEVICE_OBJECT v18; // rcx
  __int64 v19; // rdx
  PVOID v20; // rsi
  const char *v21; // r14
  __int64 v22; // rax
  struct _UNICODE_STRING *v23; // rcx
  struct _UNICODE_STRING *v24; // rsi
  _BYTE *Buffer; // rcx
  __int64 ReferencedHandle; // rax
  unsigned __int16 v27; // cx
  size_t v28; // r14
  __int64 v29; // rcx
  const char *v30; // rax
  struct _ECP_LIST *AllocationSize; // [rsp+28h] [rbp-A9h]
  ULONG FileAttributes; // [rsp+30h] [rbp-A1h]
  ULONG Disposition; // [rsp+40h] [rbp-91h]
  int EaBuffer; // [rsp+50h] [rbp-81h]
  ULONG EaLength; // [rsp+58h] [rbp-79h]
  int CreateFileType; // [rsp+60h] [rbp-71h]
  int InternalParameters; // [rsp+68h] [rbp-69h]
  int Options; // [rsp+70h] [rbp-61h]
  const char *v39; // [rsp+88h] [rbp-49h]
  const char *v40; // [rsp+90h] [rbp-41h] BYREF
  PVOID P[2]; // [rsp+98h] [rbp-39h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A8h] [rbp-29h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B8h] [rbp-19h] BYREF
  HANDLE Handle; // [rsp+138h] [rbp+67h] BYREF
  __int64 v45; // [rsp+150h] [rbp+7Fh] BYREF
  va_list va; // [rsp+150h] [rbp+7Fh]
  va_list va1; // [rsp+158h] [rbp+87h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v45 = va_arg(va1, _QWORD);
  v3 = *(_DWORD *)(a1 + 284) == 127;
  Handle = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  if ( !v3 )
  {
    for ( i = 0; ; ++i )
    {
      if ( i >= 3 )
        return 0;
      if ( a2 && *a2 )
      {
        ExAcquireResourceSharedLite((PERESOURCE)(*(_QWORD *)a1 + 200LL), 1u);
        v11 = 1;
        v12 = (struct _UNICODE_STRING **)(a1 + 336);
LABEL_46:
        v23 = *v12;
        while ( 1 )
        {
          v9 = 0;
          if ( v23 == (struct _UNICODE_STRING *)v12 )
            break;
          v24 = v23;
          v23 = *(struct _UNICODE_STRING **)&v23->Length;
          if ( *a2 == *(_QWORD *)&v24[2].Length )
          {
            Buffer = v24[1].Buffer;
            if ( Buffer && !Buffer[104] )
            {
              Srv2ReferenceConnection(Buffer);
              v9 = v24[1].Buffer;
              v24[2].Buffer = (PWSTR)MEMORY[0xFFFFF78000000014];
              break;
            }
            if ( v11 )
            {
              ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)a1 + 200LL));
              ExAcquireResourceExclusiveLite((PERESOURCE)(*(_QWORD *)a1 + 200LL), 1u);
              v11 = 0;
              goto LABEL_46;
            }
            if ( Buffer )
            {
              Smb2DereferenceHandle(Buffer);
              v24[1].Buffer = 0;
            }
            ObjectAttributes.ObjectName = v24 + 4;
            ObjectAttributes.Length = 48;
            ObjectAttributes.RootDirectory = 0;
            ObjectAttributes.Attributes = 576;
            *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
            if ( NtOpenFile(&Handle, 0x20u, &ObjectAttributes, &IoStatusBlock, 7u, 0) >= 0 )
            {
              ReferencedHandle = Smb2AllocateReferencedHandle(*(_QWORD *)(a1 + 408), Handle, 0);
              v9 = (_QWORD *)ReferencedHandle;
              if ( ReferencedHandle )
              {
                v24[1].Buffer = (PWSTR)ReferencedHandle;
                Srv2ReferenceConnection(ReferencedHandle);
                v24[2].Buffer = (PWSTR)MEMORY[0xFFFFF78000000014];
                Smb2SignalSnapShotScavengerCheck();
              }
              else
              {
                ZwClose(Handle);
              }
            }
            break;
          }
        }
        ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)a1 + 200LL));
        return v9;
      }
      ExAcquireResourceSharedLite((PERESOURCE)(*(_QWORD *)a1 + 96LL), 1u);
      if ( !a3 )
      {
        v8 = *(_QWORD *)(a1 + 320);
        if ( v8 )
        {
          if ( !*(_BYTE *)(v8 + 104) )
            goto LABEL_8;
        }
      }
      v13 = 0;
      v39 = 0;
      v14 = (struct _ERESOURCE *)(*(_QWORD *)a1 + 96LL);
      v40 = 0;
      *(_OWORD *)P = 0;
      LODWORD(v45) = 0;
      ExReleaseResourceLite(v14);
      ExAcquireResourceExclusiveLite((PERESOURCE)(*(_QWORD *)a1 + 96LL), 1u);
      if ( !a3 )
      {
        v15 = *(_QWORD *)(a1 + 320);
        if ( v15 )
        {
          if ( !*(_BYTE *)(v15 + 104) )
          {
            ExConvertExclusiveToSharedLite((PERESOURCE)(*(_QWORD *)a1 + 96LL));
LABEL_8:
            v9 = *(_QWORD **)(a1 + 320);
            Srv2ReferenceConnection(v9);
            ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)a1 + 96LL));
            return v9;
          }
        }
      }
      v16 = (void *)Smb2ReplaceShareDirectoryHandle(a1, 0);
      ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)a1 + 96LL));
      if ( v16 )
      {
        Smb2DereferenceHandle(v16);
        v16 = 0;
      }
      v3 = (*(_DWORD *)(a1 + 288) & 0x4000) == 0;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)(a1 + 120);
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      if ( v3 )
      {
        VolumeUniqueID = IoCreateFileEx(
                           &Handle,
                           0xA0u,
                           &ObjectAttributes,
                           &IoStatusBlock,
                           0,
                           0,
                           3u,
                           1u,
                           1u,
                           0,
                           0,
                           CreateFileTypeNone,
                           0,
                           0,
                           0);
        if ( VolumeUniqueID < 0 )
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            v19 = 38;
LABEL_25:
            WPP_SF_qD(v18->AttachedDevice, v19, WPP_4e8015138ece3414973dc97451d118ee_Traceguids, a1, VolumeUniqueID);
          }
LABEL_26:
          v9 = 0;
LABEL_27:
          v20 = P[1];
          goto LABEL_28;
        }
      }
      else
      {
        VolumeUniqueID = Smb2CreateFileWithBypassEcp(
                           &Handle,
                           0xA0u,
                           &ObjectAttributes,
                           &IoStatusBlock,
                           AllocationSize,
                           FileAttributes,
                           3u,
                           Disposition,
                           1u,
                           EaBuffer,
                           EaLength,
                           CreateFileType,
                           InternalParameters,
                           Options,
                           0);
        if ( VolumeUniqueID < 0 )
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            v19 = 37;
            goto LABEL_25;
          }
          goto LABEL_26;
        }
      }
      v22 = Smb2AllocateReferencedHandle(*(_QWORD *)(a1 + 408), Handle, 0);
      v9 = (_QWORD *)v22;
      if ( !v22 )
      {
        VolumeUniqueID = -1073741670;
        goto LABEL_27;
      }
      Handle = 0;
      if ( (int)Smb2GetShareFilesystemType(a1, v22, (__int64 *)va) >= 0 )
      {
        VolumeUniqueID = Smb2ShareGetVolumeUniqueID(v9[12], &v40);
        if ( VolumeUniqueID >= 0 )
        {
          v21 = v40;
        }
        else
        {
          v21 = "\b";
          VolumeUniqueID = 0;
        }
        v39 = v21;
        v27 = *(_WORD *)(v9[12] + 88LL);
        if ( v27 <= 2u )
        {
          v20 = (PVOID)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
        }
        else
        {
          v28 = (unsigned __int16)(v27 - 2);
          LOWORD(P[0]) = v27 - 2;
          WORD1(P[0]) = v27 - 2;
          P[1] = (PVOID)ExAllocatePool2(66, v28, 1748128588);
          v20 = P[1];
          if ( !P[1] )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_4e8015138ece3414973dc97451d118ee_Traceguids);
            }
            VolumeUniqueID = -1073741670;
LABEL_28:
            v21 = v39;
LABEL_29:
            if ( v20 )
              ExFreePoolWithTag(v20, 0);
            Smb2FreeVolumeUniqueId(v21);
            if ( v16 )
              Smb2DereferenceHandle(v16);
            if ( Handle )
            {
              ZwClose(Handle);
              Handle = 0;
            }
            if ( v9 )
            {
              if ( VolumeUniqueID < 0 )
              {
                Smb2DereferenceHandle(v9);
                return 0;
              }
            }
            return v9;
          }
          memmove(P[1], (const void *)(*(_QWORD *)(v9[12] + 96LL) + 2LL), v28);
          v13 = *(_OWORD *)P;
          v21 = v39;
        }
        ExAcquireResourceExclusiveLite((PERESOURCE)(*(_QWORD *)a1 + 96LL), 1u);
        v29 = *(_QWORD *)(a1 + 320);
        if ( !v29 || *(_BYTE *)(v29 + 104) || a3 )
        {
          v16 = (void *)Smb2ReplaceShareDirectoryHandle(a1, v9);
          if ( (_DWORD)v45 == 1 )
          {
            *(_WORD *)(a1 + 279) = 1;
          }
          else if ( (_DWORD)v45 == 4 )
          {
            *(_WORD *)(a1 + 279) = 257;
          }
          else
          {
            *(_WORD *)(a1 + 279) = 256;
          }
          v30 = *(const char **)(a1 + 376);
          v20 = *(PVOID *)(a1 + 176);
          *(_QWORD *)(a1 + 376) = v21;
          v21 = v30;
          *(_OWORD *)(a1 + 168) = v13;
        }
        else
        {
          v16 = v9;
          v9 = *(_QWORD **)(a1 + 320);
          Srv2ReferenceConnection(v29);
        }
        ExConvertExclusiveToSharedLite((PERESOURCE)(*(_QWORD *)a1 + 96LL));
        ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)a1 + 96LL));
        goto LABEL_29;
      }
      Smb2DereferenceHandle(v9);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140081d90  mov     rax, rsp
0x140081d93  mov     [rax+10h], rbx
0x140081d97  mov     [rax+20h], r9
0x140081d9b  push    rbp
0x140081d9c  push    rsi
0x140081d9d  push    rdi
0x140081d9e  push    r12
0x140081da0  push    r13
0x140081da2  push    r14
0x140081da4  push    r15
0x140081da6  lea     rbp, [rax-5Fh]
0x140081daa  sub     rsp, 0F0h
0x140081db1  xorps   xmm0, xmm0
0x140081db4  movaps  xmmword ptr [rax-48h], xmm6
0x140081db8  xor     r12d, r12d
0x140081dbb  xor     eax, eax
0x140081dbd  cmp     dword ptr [rcx+11Ch], 7Fh
0x140081dc4  movzx   r15d, r8b
0x140081dc8  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140081dcc  mov     r14, rdx
0x140081dcf  mov     [rbp+57h+Handle], r12
0x140081dd3  mov     rdi, rcx
0x140081dd6  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140081dda  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140081dde  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140081de2  jz      loc_140081E7E
0x140081de8  mov     esi, r12d
0x140081deb  cmp     esi, 3
0x140081dee  jnb     loc_140081E7E
0x140081df4  test    r14, r14
0x140081df7  jnz     loc_140081E82
0x140081dfd  mov     rcx, [rdi]
0x140081e00  mov     dl, 1; Wait
0x140081e02  add     rcx, 60h ; '`'; Resource
0x140081e06  call    cs:__imp_ExAcquireResourceSharedLite
0x140081e0d  nop     dword ptr [rax+rax+00h]
0x140081e12  test    r15b, r15b
0x140081e15  jnz     loc_140098BD0
0x140081e1b  mov     rax, [rdi+140h]
0x140081e22  test    rax, rax
0x140081e25  jz      loc_140098BD0
0x140081e2b  cmp     [rax+68h], r15b
0x140081e2f  jnz     loc_140098BD0
0x140081e35  mov     rbx, [rdi+140h]
0x140081e3c  mov     rcx, rbx
0x140081e3f  call    Srv2ReferenceConnection
0x140081e44  mov     rcx, [rdi]
0x140081e47  add     rcx, 60h ; '`'; Resource
0x140081e4b  call    cs:__imp_ExReleaseResourceLite
0x140081e52  nop     dword ptr [rax+rax+00h]
0x140081e57  mov     rax, rbx
0x140081e5a  mov     rbx, [rsp+120h+arg_8]
0x140081e62  movaps  xmm6, xmmword ptr [rsp+0E0h]
0x140081e6a  add     rsp, 0F0h
0x140081e71  pop     r15
0x140081e73  pop     r14
0x140081e75  pop     r13
0x140081e77  pop     r12
0x140081e79  pop     rdi
0x140081e7a  pop     rsi
0x140081e7b  pop     rbp
0x140081e7c  retn
0x140081e7e  xor     eax, eax
0x140081e80  jmp     short loc_140081E5A
0x140081e82  cmp     qword ptr [r14], 0
0x140081e86  jz      loc_140081DFD
0x140081e8c  mov     rcx, [rdi]
0x140081e8f  mov     dl, 1; Wait
0x140081e91  add     rcx, 0C8h; Resource
0x140081e98  call    cs:__imp_ExAcquireResourceSharedLite
0x140081e9f  nop     dword ptr [rax+rax+00h]
0x140081ea4  mov     dl, 1
0x140081ea6  lea     r15, [rdi+150h]
0x140081ead  jmp     loc_140098E57
0x140098bd0  mov     rcx, [rdi]
0x140098bd3  mov     rax, r12
0x140098bd6  xorps   xmm6, xmm6
0x140098bd9  mov     [rbp+57h+var_A0], rax
0x140098bdd  add     rcx, 60h ; '`'; Resource
0x140098be1  mov     [rbp+57h+var_98], rax
0x140098be5  movups  xmmword ptr [rbp+57h+P], xmm6
0x140098be9  mov     dword ptr [rbp+57h+arg_18], r12d
0x140098bed  call    cs:__imp_ExReleaseResourceLite
0x140098bf4  nop     dword ptr [rax+rax+00h]
0x140098bf9  mov     rcx, [rdi]
0x140098bfc  mov     dl, 1; Wait
0x140098bfe  add     rcx, 60h ; '`'; Resource
0x140098c02  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140098c09  nop     dword ptr [rax+rax+00h]
0x140098c0e  test    r15b, r15b
0x140098c11  jnz     short loc_140098C3E
0x140098c13  mov     rax, [rdi+140h]
0x140098c1a  test    rax, rax
0x140098c1d  jz      short loc_140098C3E
0x140098c1f  cmp     [rax+68h], r15b
0x140098c23  jnz     short loc_140098C3E
0x140098c25  mov     rcx, [rdi]
0x140098c28  add     rcx, 60h ; '`'; Resource
0x140098c2c  call    cs:__imp_ExConvertExclusiveToSharedLite
0x140098c33  nop     dword ptr [rax+rax+00h]
0x140098c38  nop
0x140098c39  jmp     loc_140081E35
0x140098c3e  xor     edx, edx
0x140098c40  mov     rcx, rdi
0x140098c43  call    Smb2ReplaceShareDirectoryHandle
0x140098c48  mov     rcx, [rdi]
0x140098c4b  mov     r13, rax
0x140098c4e  add     rcx, 60h ; '`'; Resource
0x140098c52  call    cs:__imp_ExReleaseResourceLite
0x140098c59  nop     dword ptr [rax+rax+00h]
0x140098c5e  test    r13, r13
0x140098c61  jz      short loc_140098C6E
0x140098c63  mov     rcx, r13; P
0x140098c66  call    Smb2DereferenceHandle
0x140098c6b  mov     r13, r12
0x140098c6e  test    dword ptr [rdi+120h], 4000h
0x140098c78  lea     rax, [rdi+78h]
0x140098c7c  xorps   xmm0, xmm0
0x140098c7f  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140098c83  movdqu  xmmword ptr [rbp+7], xmm0
0x140098c88  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140098c8f  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140098c93  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x140098c97  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140098c9b  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140098ca2  lea     rcx, [rbp+57h+Handle]; FileHandle
0x140098ca6  mov     qword ptr [rsp+120h+Options+8], r12; __int64
0x140098cab  mov     edx, 0A0h; DesiredAccess
0x140098cb0  jz      loc_140098D86
0x140098cb6  mov     [rsp+120h+CreateOptions], 1; ULONG
0x140098cbe  mov     [rsp+120h+ShareAccess], 3; ULONG
0x140098cc6  call    Smb2CreateFileWithBypassEcp
0x140098ccb  mov     r12d, eax
0x140098cce  test    eax, eax
0x140098cd0  jns     loc_140098E0A
0x140098cd6  mov     rcx, cs:WPP_GLOBAL_Control
0x140098cdd  lea     rax, WPP_GLOBAL_Control
0x140098ce4  cmp     rcx, rax
0x140098ce7  jz      short loc_140098D13
0x140098ce9  mov     eax, [rcx+2Ch]
0x140098cec  test    al, 1
0x140098cee  jz      short loc_140098D13
0x140098cf0  cmp     byte ptr [rcx+29h], 1
0x140098cf4  jb      short loc_140098D13
0x140098cf6  mov     edx, 25h ; '%'
0x140098cfb  mov     rcx, [rcx+18h]
0x140098cff  lea     r8, WPP_4e8015138ece3414973dc97451d118ee_Traceguids
0x140098d06  mov     r9, rdi
0x140098d09  mov     dword ptr [rsp+120h+AllocationSize], r12d
0x140098d0e  call    WPP_SF_qD
0x140098d13  xor     ebx, ebx
0x140098d15  mov     rsi, [rbp+57h+P+8]
0x140098d19  mov     r14, [rbp+57h+var_A0]
0x140098d1d  test    rsi, rsi
0x140098d20  jz      short loc_140098D33
0x140098d22  xor     edx, edx; Tag
0x140098d24  mov     rcx, rsi; P
0x140098d27  call    cs:__imp_ExFreePoolWithTag
0x140098d2e  nop     dword ptr [rax+rax+00h]
0x140098d33  mov     rcx, r14
0x140098d36  call    Smb2FreeVolumeUniqueId
0x140098d3b  test    r13, r13
0x140098d3e  jz      short loc_140098D48
0x140098d40  mov     rcx, r13; P
0x140098d43  call    Smb2DereferenceHandle
0x140098d48  mov     rcx, [rbp+57h+Handle]; Handle
0x140098d4c  test    rcx, rcx
0x140098d4f  jz      short loc_140098D65
0x140098d51  call    cs:__imp_ZwClose
0x140098d58  nop     dword ptr [rax+rax+00h]
0x140098d5d  mov     [rbp+57h+Handle], 0
0x140098d65  test    rbx, rbx
0x140098d68  jz      loc_140081E57
0x140098d6e  test    r12d, r12d
0x140098d71  jns     loc_140081E57
0x140098d77  mov     rcx, rbx; P
0x140098d7a  call    Smb2DereferenceHandle
0x140098d7f  xor     ebx, ebx
0x140098d81  jmp     loc_140081E57
0x140098d86  mov     [rsp+120h+Options], r12d; Options
0x140098d8b  mov     [rsp+120h+InternalParameters], r12; InternalParameters
0x140098d90  mov     [rsp+120h+CreateFileType], r12d; CreateFileType
0x140098d95  mov     [rsp+120h+EaLength], r12d; EaLength
0x140098d9a  mov     [rsp+120h+EaBuffer], r12; EaBuffer
0x140098d9f  mov     [rsp+120h+CreateOptions], 1; CreateOptions
0x140098da7  mov     [rsp+120h+Disposition], 1; Disposition
0x140098daf  mov     [rsp+120h+ShareAccess], 3; ShareAccess
0x140098db7  mov     [rsp+120h+FileAttributes], r12d; FileAttributes
0x140098dbc  mov     [rsp+120h+AllocationSize], r12; AllocationSize
0x140098dc1  call    cs:__imp_IoCreateFileEx
0x140098dc8  nop     dword ptr [rax+rax+00h]
0x140098dcd  mov     r12d, eax
0x140098dd0  test    eax, eax
0x140098dd2  jns     short loc_140098E0A
0x140098dd4  mov     rcx, cs:WPP_GLOBAL_Control
0x140098ddb  lea     rax, WPP_GLOBAL_Control
0x140098de2  cmp     rcx, rax
0x140098de5  jz      loc_140098D13
0x140098deb  mov     eax, [rcx+2Ch]
0x140098dee  test    al, 1
0x140098df0  jz      loc_140098D13
0x140098df6  cmp     byte ptr [rcx+29h], 1
0x140098dfa  jb      loc_140098D13
0x140098e00  mov     edx, 26h ; '&'
0x140098e05  jmp     loc_140098CFB
0x140098e0a  mov     rdx, [rbp+57h+Handle]
0x140098e0e  xor     r8d, r8d
0x140098e11  mov     rcx, [rdi+198h]
0x140098e18  call    Smb2AllocateReferencedHandle
0x140098e1d  mov     rbx, rax
0x140098e20  test    rax, rax
0x140098e23  jz      loc_14009913B
0x140098e29  xor     r12d, r12d
0x140098e2c  lea     r8, [rbp+57h+arg_18]
0x140098e30  mov     rdx, rax
0x140098e33  mov     [rbp+57h+Handle], r12
0x140098e37  mov     rcx, rdi
0x140098e3a  call    Smb2GetShareFilesystemType
0x140098e3f  test    eax, eax
0x140098e41  jns     loc_140098F9C
0x140098e47  inc     esi
0x140098e49  mov     rcx, rbx; P
0x140098e4c  call    Smb2DereferenceHandle
0x140098e51  nop
0x140098e52  jmp     loc_140081DEB
0x140098e57  mov     rcx, [r15]
0x140098e5a  mov     rbx, r12
0x140098e5d  cmp     rcx, r15
0x140098e60  jz      loc_140098F80
0x140098e66  mov     rsi, rcx
0x140098e69  mov     rcx, [rcx]
0x140098e6c  mov     rax, [rsi+20h]
0x140098e70  cmp     [r14], rax
0x140098e73  jnz     short loc_140098E5A
0x140098e75  mov     rcx, [rsi+18h]; P
0x140098e79  test    rcx, rcx
0x140098e7c  jz      short loc_140098EA0
0x140098e7e  cmp     byte ptr [rcx+68h], 0
0x140098e82  jnz     short loc_140098EA0
0x140098e84  call    Srv2ReferenceConnection
0x140098e89  mov     rax, ds:0FFFFF78000000014h
0x140098e93  mov     rbx, [rsi+18h]
0x140098e97  mov     [rsi+28h], rax
0x140098e9b  jmp     loc_140098F80
0x140098ea0  test    dl, dl
0x140098ea2  jz      short loc_140098ED6
0x140098ea4  mov     rcx, [rdi]
0x140098ea7  add     rcx, 0C8h; Resource
0x140098eae  call    cs:__imp_ExReleaseResourceLite
0x140098eb5  nop     dword ptr [rax+rax+00h]
0x140098eba  mov     rcx, [rdi]
0x140098ebd  mov     dl, 1; Wait
0x140098ebf  add     rcx, 0C8h; Resource
0x140098ec6  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140098ecd  nop     dword ptr [rax+rax+00h]
0x140098ed2  xor     dl, dl
0x140098ed4  jmp     short loc_140098E57
0x140098ed6  test    rcx, rcx
0x140098ed9  jz      short loc_140098EE4
0x140098edb  call    Smb2DereferenceHandle
0x140098ee0  mov     [rsi+18h], r12
0x140098ee4  lea     rax, [rsi+40h]
0x140098ee8  mov     [rsp+120h+FileAttributes], r12d; OpenOptions
0x140098eed  xorps   xmm0, xmm0
0x140098ef0  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140098ef4  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140098ef8  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140098eff  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140098f03  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x140098f07  mov     edx, 20h ; ' '; DesiredAccess
0x140098f0c  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140098f13  lea     rcx, [rbp+57h+Handle]; FileHandle
0x140098f17  mov     dword ptr [rsp+120h+AllocationSize], 7; ShareAccess
0x140098f1f  movdqu  xmmword ptr [rbp+7], xmm0
0x140098f24  call    cs:__imp_NtOpenFile
0x140098f2b  nop     dword ptr [rax+rax+00h]
0x140098f30  test    eax, eax
0x140098f32  js      short loc_140098F80
0x140098f34  mov     rdx, [rbp+57h+Handle]
0x140098f38  xor     r8d, r8d
0x140098f3b  mov     rcx, [rdi+198h]
0x140098f42  call    Smb2AllocateReferencedHandle
0x140098f47  mov     rbx, rax
0x140098f4a  test    rax, rax
0x140098f4d  jnz     short loc_140098F61
0x140098f4f  mov     rcx, [rbp+57h+Handle]; Handle
0x140098f53  call    cs:__imp_ZwClose
0x140098f5a  nop     dword ptr [rax+rax+00h]
0x140098f5f  jmp     short loc_140098F80
0x140098f61  mov     rcx, rax
0x140098f64  mov     [rsi+18h], rax
0x140098f68  call    Srv2ReferenceConnection
0x140098f6d  mov     rax, ds:0FFFFF78000000014h
0x140098f77  mov     [rsi+28h], rax
0x140098f7b  call    Smb2SignalSnapShotScavengerCheck
0x140098f80  mov     rcx, [rdi]
0x140098f83  add     rcx, 0C8h; Resource
0x140098f8a  call    cs:__imp_ExReleaseResourceLite
0x140098f91  nop     dword ptr [rax+rax+00h]
0x140098f96  nop
  ... truncated ...
```
