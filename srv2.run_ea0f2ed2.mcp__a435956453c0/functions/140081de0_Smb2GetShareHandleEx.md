# Smb2GetShareHandleEx

- ea: `0x140081de0`
- end: `0x140081f02`
- name: `Smb2GetShareHandleEx`
- size: `290`
- prototype: ``
- caller_count: `11`
- callee_count: `13`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140007400`
- `0x14000c070`
- `0x140063dd4`
- `0x14006479c`
- `0x140064ac4`
- `0x140066300`
- `0x140066dc4`
- `0x14007a89c`
- `0x140081404`
- `0x140081b90`
- `0x140095fd8`

## callees

- `0x140013810`
- `0x140015000`
- `0x14001bd4c`
- `0x14002019c`
- `0x140022958`
- `0x140029768`
- `0x140038680`
- `0x1400593dc`
- `0x140063da0`
- `0x140067d58`
- `0x140081de0`
- `0x14008d444`
- `0x140091e68`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140099046`
- `ntoskrnl!ExAllocatePool2` at `0x140099046`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140081e56`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140081ee8`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140081e56`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140081ee8`
- `ntoskrnl!ExReleaseResourceLite` at `0x140081e9b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140098c3d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140098ca2`
- `ntoskrnl!ExReleaseResourceLite` at `0x140098efe`
- `ntoskrnl!ExReleaseResourceLite` at `0x140098fda`
- `ntoskrnl!ExReleaseResourceLite` at `0x14009917a`
- `ntoskrnl!ExReleaseResourceLite` at `0x140081e9b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140098c3d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140098ca2`
- `ntoskrnl!ExReleaseResourceLite` at `0x140098efe`
- `ntoskrnl!ExReleaseResourceLite` at `0x140098fda`
- `ntoskrnl!ExReleaseResourceLite` at `0x14009917a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140098c52`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140098f16`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400990d7`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140098c52`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140098f16`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400990d7`
- `ntoskrnl!ZwClose` at `0x140098da1`
- `ntoskrnl!ZwClose` at `0x140098fa3`
- `ntoskrnl!ZwClose` at `0x140098da1`
- `ntoskrnl!ZwClose` at `0x140098fa3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140098d77`
- `ntoskrnl!ExFreePoolWithTag` at `0x140098d77`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x140098c7c`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x140099167`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x140098c7c`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x140099167`
- `ntoskrnl!IoCreateFileEx` at `0x140098e11`
- `ntoskrnl!IoCreateFileEx` at `0x140098e11`
- `ntoskrnl!NtOpenFile` at `0x140098f74`
- `ntoskrnl!NtOpenFile` at `0x140098f74`

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
            WPP_SF_qD(v18->AttachedDevice, v19, &WPP_4e8015138ece3414973dc97451d118ee_Traceguids, a1, VolumeUniqueID);
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
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 39, &WPP_4e8015138ece3414973dc97451d118ee_Traceguids);
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
0x140081de0  mov     rax, rsp
0x140081de3  mov     [rax+10h], rbx
0x140081de7  mov     [rax+20h], r9
0x140081deb  push    rbp
0x140081dec  push    rsi
0x140081ded  push    rdi
0x140081dee  push    r12
0x140081df0  push    r13
0x140081df2  push    r14
0x140081df4  push    r15
0x140081df6  lea     rbp, [rax-5Fh]
0x140081dfa  sub     rsp, 0F0h
0x140081e01  xorps   xmm0, xmm0
0x140081e04  movaps  xmmword ptr [rax-48h], xmm6
0x140081e08  xor     r12d, r12d
0x140081e0b  xor     eax, eax
0x140081e0d  cmp     dword ptr [rcx+11Ch], 7Fh
0x140081e14  movzx   r15d, r8b
0x140081e18  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140081e1c  mov     r14, rdx
0x140081e1f  mov     [rbp+57h+Handle], r12
0x140081e23  mov     rdi, rcx
0x140081e26  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140081e2a  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140081e2e  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140081e32  jz      loc_140081ECE
0x140081e38  mov     esi, r12d
0x140081e3b  cmp     esi, 3
0x140081e3e  jnb     loc_140081ECE
0x140081e44  test    r14, r14
0x140081e47  jnz     loc_140081ED2
0x140081e4d  mov     rcx, [rdi]
0x140081e50  mov     dl, 1; Wait
0x140081e52  add     rcx, 60h ; '`'; Resource
0x140081e56  call    cs:__imp_ExAcquireResourceSharedLite
0x140081e5d  nop     dword ptr [rax+rax+00h]
0x140081e62  test    r15b, r15b
0x140081e65  jnz     loc_140098C20
0x140081e6b  mov     rax, [rdi+140h]
0x140081e72  test    rax, rax
0x140081e75  jz      loc_140098C20
0x140081e7b  cmp     [rax+68h], r15b
0x140081e7f  jnz     loc_140098C20
0x140081e85  mov     rbx, [rdi+140h]
0x140081e8c  mov     rcx, rbx
0x140081e8f  call    Srv2ReferenceConnection
0x140081e94  mov     rcx, [rdi]
0x140081e97  add     rcx, 60h ; '`'; Resource
0x140081e9b  call    cs:__imp_ExReleaseResourceLite
0x140081ea2  nop     dword ptr [rax+rax+00h]
0x140081ea7  mov     rax, rbx
0x140081eaa  mov     rbx, [rsp+120h+arg_8]
0x140081eb2  movaps  xmm6, xmmword ptr [rsp+0E0h]
0x140081eba  add     rsp, 0F0h
0x140081ec1  pop     r15
0x140081ec3  pop     r14
0x140081ec5  pop     r13
0x140081ec7  pop     r12
0x140081ec9  pop     rdi
0x140081eca  pop     rsi
0x140081ecb  pop     rbp
0x140081ecc  retn
0x140081ece  xor     eax, eax
0x140081ed0  jmp     short loc_140081EAA
0x140081ed2  cmp     qword ptr [r14], 0
0x140081ed6  jz      loc_140081E4D
0x140081edc  mov     rcx, [rdi]
0x140081edf  mov     dl, 1; Wait
0x140081ee1  add     rcx, 0C8h; Resource
0x140081ee8  call    cs:__imp_ExAcquireResourceSharedLite
0x140081eef  nop     dword ptr [rax+rax+00h]
0x140081ef4  mov     dl, 1
0x140081ef6  lea     r15, [rdi+150h]
0x140081efd  jmp     loc_140098EA7
0x140098c20  mov     rcx, [rdi]
0x140098c23  mov     rax, r12
0x140098c26  xorps   xmm6, xmm6
0x140098c29  mov     [rbp+57h+var_A0], rax
0x140098c2d  add     rcx, 60h ; '`'; Resource
0x140098c31  mov     [rbp+57h+var_98], rax
0x140098c35  movups  xmmword ptr [rbp+57h+P], xmm6
0x140098c39  mov     dword ptr [rbp+57h+arg_18], r12d
0x140098c3d  call    cs:__imp_ExReleaseResourceLite
0x140098c44  nop     dword ptr [rax+rax+00h]
0x140098c49  mov     rcx, [rdi]
0x140098c4c  mov     dl, 1; Wait
0x140098c4e  add     rcx, 60h ; '`'; Resource
0x140098c52  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140098c59  nop     dword ptr [rax+rax+00h]
0x140098c5e  test    r15b, r15b
0x140098c61  jnz     short loc_140098C8E
0x140098c63  mov     rax, [rdi+140h]
0x140098c6a  test    rax, rax
0x140098c6d  jz      short loc_140098C8E
0x140098c6f  cmp     [rax+68h], r15b
0x140098c73  jnz     short loc_140098C8E
0x140098c75  mov     rcx, [rdi]
0x140098c78  add     rcx, 60h ; '`'; Resource
0x140098c7c  call    cs:__imp_ExConvertExclusiveToSharedLite
0x140098c83  nop     dword ptr [rax+rax+00h]
0x140098c88  nop
0x140098c89  jmp     loc_140081E85
0x140098c8e  xor     edx, edx
0x140098c90  mov     rcx, rdi
0x140098c93  call    Smb2ReplaceShareDirectoryHandle
0x140098c98  mov     rcx, [rdi]
0x140098c9b  mov     r13, rax
0x140098c9e  add     rcx, 60h ; '`'; Resource
0x140098ca2  call    cs:__imp_ExReleaseResourceLite
0x140098ca9  nop     dword ptr [rax+rax+00h]
0x140098cae  test    r13, r13
0x140098cb1  jz      short loc_140098CBE
0x140098cb3  mov     rcx, r13; P
0x140098cb6  call    Smb2DereferenceHandle
0x140098cbb  mov     r13, r12
0x140098cbe  test    dword ptr [rdi+120h], 4000h
0x140098cc8  lea     rax, [rdi+78h]
0x140098ccc  xorps   xmm0, xmm0
0x140098ccf  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140098cd3  movdqu  xmmword ptr [rbp+7], xmm0
0x140098cd8  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140098cdf  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140098ce3  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x140098ce7  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140098ceb  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140098cf2  lea     rcx, [rbp+57h+Handle]; FileHandle
0x140098cf6  mov     qword ptr [rsp+120h+Options+8], r12; __int64
0x140098cfb  mov     edx, 0A0h; DesiredAccess
0x140098d00  jz      loc_140098DD6
0x140098d06  mov     [rsp+120h+CreateOptions], 1; ULONG
0x140098d0e  mov     [rsp+120h+ShareAccess], 3; ULONG
0x140098d16  call    Smb2CreateFileWithBypassEcp
0x140098d1b  mov     r12d, eax
0x140098d1e  test    eax, eax
0x140098d20  jns     loc_140098E5A
0x140098d26  mov     rcx, cs:WPP_GLOBAL_Control
0x140098d2d  lea     rax, WPP_GLOBAL_Control
0x140098d34  cmp     rcx, rax
0x140098d37  jz      short loc_140098D63
0x140098d39  mov     eax, [rcx+2Ch]
0x140098d3c  test    al, 1
0x140098d3e  jz      short loc_140098D63
0x140098d40  cmp     byte ptr [rcx+29h], 1
0x140098d44  jb      short loc_140098D63
0x140098d46  mov     edx, 25h ; '%'
0x140098d4b  mov     rcx, [rcx+18h]
0x140098d4f  lea     r8, WPP_4e8015138ece3414973dc97451d118ee_Traceguids
0x140098d56  mov     r9, rdi
0x140098d59  mov     dword ptr [rsp+120h+AllocationSize], r12d
0x140098d5e  call    WPP_SF_qD
0x140098d63  xor     ebx, ebx
0x140098d65  mov     rsi, [rbp+57h+P+8]
0x140098d69  mov     r14, [rbp+57h+var_A0]
0x140098d6d  test    rsi, rsi
0x140098d70  jz      short loc_140098D83
0x140098d72  xor     edx, edx; Tag
0x140098d74  mov     rcx, rsi; P
0x140098d77  call    cs:__imp_ExFreePoolWithTag
0x140098d7e  nop     dword ptr [rax+rax+00h]
0x140098d83  mov     rcx, r14
0x140098d86  call    Smb2FreeVolumeUniqueId
0x140098d8b  test    r13, r13
0x140098d8e  jz      short loc_140098D98
0x140098d90  mov     rcx, r13; P
0x140098d93  call    Smb2DereferenceHandle
0x140098d98  mov     rcx, [rbp+57h+Handle]; Handle
0x140098d9c  test    rcx, rcx
0x140098d9f  jz      short loc_140098DB5
0x140098da1  call    cs:__imp_ZwClose
0x140098da8  nop     dword ptr [rax+rax+00h]
0x140098dad  mov     [rbp+57h+Handle], 0
0x140098db5  test    rbx, rbx
0x140098db8  jz      loc_140081EA7
0x140098dbe  test    r12d, r12d
0x140098dc1  jns     loc_140081EA7
0x140098dc7  mov     rcx, rbx; P
0x140098dca  call    Smb2DereferenceHandle
0x140098dcf  xor     ebx, ebx
0x140098dd1  jmp     loc_140081EA7
0x140098dd6  mov     [rsp+120h+Options], r12d; Options
0x140098ddb  mov     [rsp+120h+InternalParameters], r12; InternalParameters
0x140098de0  mov     [rsp+120h+CreateFileType], r12d; CreateFileType
0x140098de5  mov     [rsp+120h+EaLength], r12d; EaLength
0x140098dea  mov     [rsp+120h+EaBuffer], r12; EaBuffer
0x140098def  mov     [rsp+120h+CreateOptions], 1; CreateOptions
0x140098df7  mov     [rsp+120h+Disposition], 1; Disposition
0x140098dff  mov     [rsp+120h+ShareAccess], 3; ShareAccess
0x140098e07  mov     [rsp+120h+FileAttributes], r12d; FileAttributes
0x140098e0c  mov     [rsp+120h+AllocationSize], r12; AllocationSize
0x140098e11  call    cs:__imp_IoCreateFileEx
0x140098e18  nop     dword ptr [rax+rax+00h]
0x140098e1d  mov     r12d, eax
0x140098e20  test    eax, eax
0x140098e22  jns     short loc_140098E5A
0x140098e24  mov     rcx, cs:WPP_GLOBAL_Control
0x140098e2b  lea     rax, WPP_GLOBAL_Control
0x140098e32  cmp     rcx, rax
0x140098e35  jz      loc_140098D63
0x140098e3b  mov     eax, [rcx+2Ch]
0x140098e3e  test    al, 1
0x140098e40  jz      loc_140098D63
0x140098e46  cmp     byte ptr [rcx+29h], 1
0x140098e4a  jb      loc_140098D63
0x140098e50  mov     edx, 26h ; '&'
0x140098e55  jmp     loc_140098D4B
0x140098e5a  mov     rdx, [rbp+57h+Handle]
0x140098e5e  xor     r8d, r8d
0x140098e61  mov     rcx, [rdi+198h]
0x140098e68  call    Smb2AllocateReferencedHandle
0x140098e6d  mov     rbx, rax
0x140098e70  test    rax, rax
0x140098e73  jz      loc_14009918B
0x140098e79  xor     r12d, r12d
0x140098e7c  lea     r8, [rbp+57h+arg_18]
0x140098e80  mov     rdx, rax
0x140098e83  mov     [rbp+57h+Handle], r12
0x140098e87  mov     rcx, rdi
0x140098e8a  call    Smb2GetShareFilesystemType
0x140098e8f  test    eax, eax
0x140098e91  jns     loc_140098FEC
0x140098e97  inc     esi
0x140098e99  mov     rcx, rbx; P
0x140098e9c  call    Smb2DereferenceHandle
0x140098ea1  nop
0x140098ea2  jmp     loc_140081E3B
0x140098ea7  mov     rcx, [r15]
0x140098eaa  mov     rbx, r12
0x140098ead  cmp     rcx, r15
0x140098eb0  jz      loc_140098FD0
0x140098eb6  mov     rsi, rcx
0x140098eb9  mov     rcx, [rcx]
0x140098ebc  mov     rax, [rsi+20h]
0x140098ec0  cmp     [r14], rax
0x140098ec3  jnz     short loc_140098EAA
0x140098ec5  mov     rcx, [rsi+18h]; P
0x140098ec9  test    rcx, rcx
0x140098ecc  jz      short loc_140098EF0
0x140098ece  cmp     byte ptr [rcx+68h], 0
0x140098ed2  jnz     short loc_140098EF0
0x140098ed4  call    Srv2ReferenceConnection
0x140098ed9  mov     rax, ds:0FFFFF78000000014h
0x140098ee3  mov     rbx, [rsi+18h]
0x140098ee7  mov     [rsi+28h], rax
0x140098eeb  jmp     loc_140098FD0
0x140098ef0  test    dl, dl
0x140098ef2  jz      short loc_140098F26
0x140098ef4  mov     rcx, [rdi]
0x140098ef7  add     rcx, 0C8h; Resource
0x140098efe  call    cs:__imp_ExReleaseResourceLite
0x140098f05  nop     dword ptr [rax+rax+00h]
0x140098f0a  mov     rcx, [rdi]
0x140098f0d  mov     dl, 1; Wait
0x140098f0f  add     rcx, 0C8h; Resource
0x140098f16  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140098f1d  nop     dword ptr [rax+rax+00h]
0x140098f22  xor     dl, dl
0x140098f24  jmp     short loc_140098EA7
0x140098f26  test    rcx, rcx
0x140098f29  jz      short loc_140098F34
0x140098f2b  call    Smb2DereferenceHandle
0x140098f30  mov     [rsi+18h], r12
0x140098f34  lea     rax, [rsi+40h]
0x140098f38  mov     [rsp+120h+FileAttributes], r12d; OpenOptions
0x140098f3d  xorps   xmm0, xmm0
0x140098f40  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140098f44  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140098f48  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140098f4f  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140098f53  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x140098f57  mov     edx, 20h ; ' '; DesiredAccess
0x140098f5c  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140098f63  lea     rcx, [rbp+57h+Handle]; FileHandle
0x140098f67  mov     dword ptr [rsp+120h+AllocationSize], 7; ShareAccess
0x140098f6f  movdqu  xmmword ptr [rbp+7], xmm0
0x140098f74  call    cs:__imp_NtOpenFile
0x140098f7b  nop     dword ptr [rax+rax+00h]
0x140098f80  test    eax, eax
0x140098f82  js      short loc_140098FD0
0x140098f84  mov     rdx, [rbp+57h+Handle]
0x140098f88  xor     r8d, r8d
0x140098f8b  mov     rcx, [rdi+198h]
0x140098f92  call    Smb2AllocateReferencedHandle
0x140098f97  mov     rbx, rax
0x140098f9a  test    rax, rax
0x140098f9d  jnz     short loc_140098FB1
0x140098f9f  mov     rcx, [rbp+57h+Handle]; Handle
0x140098fa3  call    cs:__imp_ZwClose
0x140098faa  nop     dword ptr [rax+rax+00h]
0x140098faf  jmp     short loc_140098FD0
0x140098fb1  mov     rcx, rax
0x140098fb4  mov     [rsi+18h], rax
0x140098fb8  call    Srv2ReferenceConnection
0x140098fbd  mov     rax, ds:0FFFFF78000000014h
0x140098fc7  mov     [rsi+28h], rax
0x140098fcb  call    Smb2SignalSnapShotScavengerCheck
0x140098fd0  mov     rcx, [rdi]
0x140098fd3  add     rcx, 0C8h; Resource
0x140098fda  call    cs:__imp_ExReleaseResourceLite
0x140098fe1  nop     dword ptr [rax+rax+00h]
0x140098fe6  nop
  ... truncated ...
```
