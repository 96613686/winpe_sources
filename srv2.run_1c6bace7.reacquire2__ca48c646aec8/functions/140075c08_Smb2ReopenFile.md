# Smb2ReopenFile

- ea: `0x140075c08`
- end: `0x140075da1`
- name: `Smb2ReopenFile`
- size: `409`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14006e1d0`

## callees

- `0x140013810`
- `0x140015960`
- `0x14002a7e8`
- `0x1400593dc`
- `0x140075c08`
- `0x140077650`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140075d23`
- `ntoskrnl!ZwClose` at `0x140075d23`
- `ntoskrnl!IoCreateFile` at `0x140075cf0`
- `ntoskrnl!IoCreateFile` at `0x140075cf0`

## pseudocode

```c
SECURITY_STATUS __fastcall Smb2ReopenFile(__int64 a1, __int64 a2, volatile signed __int64 *a3, __int64 *a4)
{
  int v4; // eax
  SECURITY_STATUS result; // eax
  NTSTATUS v9; // edi
  __int64 v10; // rcx
  __int64 v11; // rax
  _QWORD *v12; // rsi
  __int64 v13; // [rsp+70h] [rbp-29h] BYREF
  _QWORD v14[2]; // [rsp+78h] [rbp-21h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+88h] [rbp-11h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-1h] BYREF
  void *FileHandle; // [rsp+100h] [rbp+67h] BYREF

  v4 = *(_DWORD *)(a1 + 224);
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  FileHandle = 0;
  v14[0] = 0;
  v14[1] = 0;
  IoStatusBlock = 0;
  if ( (v4 & 0x40) == 0 )
    return -1073741637;
  ObjectAttributes.RootDirectory = *(HANDLE *)(a2 + 88);
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v14;
  *a4 = 0;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( !a3 || (result = Smb2ImpersonateSecurityContext((__int64)a3), result >= 0) )
  {
    v9 = IoCreateFile(
           &FileHandle,
           *(_DWORD *)(a1 + 184),
           &ObjectAttributes,
           &IoStatusBlock,
           0,
           0,
           *(_DWORD *)(a1 + 188),
           1u,
           *(_DWORD *)(a1 + 192),
           0,
           0,
           CreateFileTypeNone,
           0,
           0);
    if ( v9 >= 0 )
    {
      v10 = *(_QWORD *)(a1 + 64);
      v13 = 0;
      v11 = Smb2AllocateReferencedHandle(v10, FileHandle, &v13);
      v12 = (_QWORD *)v11;
      if ( v11 )
      {
        *a4 = v11;
        v9 = Smb2ReplaceFileHandle(a1, v11);
        if ( v9 >= 0 )
        {
          if ( !a3 )
            return v9;
          v12[10] = a3;
          if ( ((_InterlockedExchangeAdd64(a3, 1u) + 2) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
            __int2c();
          goto LABEL_9;
        }
        Smb2DereferenceHandle(v12);
        *a4 = 0;
      }
      else
      {
        ZwClose(FileHandle);
        v9 = -1073741670;
      }
    }
    if ( !a3 )
      return v9;
LABEL_9:
    Smb2Revert();
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x140075c08  mov     [rsp-8+arg_8], rbx
0x140075c0d  mov     [rsp-8+arg_10], rsi
0x140075c12  push    rbp
0x140075c13  push    rdi
0x140075c14  push    r12
0x140075c16  push    r14
0x140075c18  push    r15
0x140075c1a  lea     rbp, [rsp-37h]
0x140075c1f  sub     rsp, 0D0h
0x140075c26  mov     eax, [rcx+0E0h]
0x140075c2c  xor     r12d, r12d
0x140075c2f  mov     dword ptr [rbp+57h+ObjectAttributes+4], r12d
0x140075c33  xorps   xmm0, xmm0
0x140075c36  mov     dword ptr [rbp+57h+ObjectAttributes+1Ch], r12d
0x140075c3a  mov     r15, r9
0x140075c3d  mov     [rbp+57h+FileHandle], r12
0x140075c41  mov     rbx, r8
0x140075c44  mov     [rbp+57h+var_78], r12
0x140075c48  mov     r14, rcx
0x140075c4b  mov     [rbp+57h+var_70], r12
0x140075c4f  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140075c53  test    al, 40h
0x140075c55  jnz     short loc_140075C61
0x140075c57  mov     eax, 0C00000BBh
0x140075c5c  jmp     loc_140075D40
0x140075c61  mov     rax, [rdx+58h]
0x140075c65  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x140075c69  lea     rax, [rbp+57h+var_78]
0x140075c6d  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140075c71  mov     [r9], r12
0x140075c74  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140075c7b  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140075c82  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140075c87  test    rbx, rbx
0x140075c8a  jz      short loc_140075C9C
0x140075c8c  mov     rcx, rbx
0x140075c8f  call    Smb2ImpersonateSecurityContext
0x140075c94  test    eax, eax
0x140075c96  js      loc_140075D40
0x140075c9c  mov     eax, [r14+0C0h]
0x140075ca3  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140075ca7  mov     edx, [r14+0B8h]; DesiredAccess
0x140075cae  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140075cb2  mov     [rsp+0F0h+Options], r12d; Options
0x140075cb7  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x140075cbb  mov     [rsp+0F0h+InternalParameters], r12; InternalParameters
0x140075cc0  mov     [rsp+0F0h+CreateFileType], r12d; CreateFileType
0x140075cc5  mov     [rsp+0F0h+EaLength], r12d; EaLength
0x140075cca  mov     [rsp+0F0h+EaBuffer], r12; EaBuffer
0x140075ccf  mov     [rsp+0F0h+CreateOptions], eax; CreateOptions
0x140075cd3  mov     eax, [r14+0BCh]
0x140075cda  mov     [rsp+0F0h+Disposition], 1; Disposition
0x140075ce2  mov     [rsp+0F0h+ShareAccess], eax; ShareAccess
0x140075ce6  mov     [rsp+0F0h+FileAttributes], r12d; FileAttributes
0x140075ceb  mov     [rsp+0F0h+AllocationSize], r12; AllocationSize
0x140075cf0  call    cs:__imp_IoCreateFile
0x140075cf7  nop     dword ptr [rax+rax+00h]
0x140075cfc  mov     edi, eax
0x140075cfe  test    eax, eax
0x140075d00  js      short loc_140075D34
0x140075d02  mov     rdx, [rbp+57h+FileHandle]
0x140075d06  lea     r8, [rbp+57h+var_80]
0x140075d0a  mov     rcx, [r14+40h]
0x140075d0e  mov     [rbp+57h+var_80], r12
0x140075d12  call    Smb2AllocateReferencedHandle
0x140075d17  mov     rsi, rax
0x140075d1a  test    rax, rax
0x140075d1d  jnz     short loc_140075D5D
0x140075d1f  mov     rcx, [rbp+57h+FileHandle]; Handle
0x140075d23  call    cs:__imp_ZwClose
0x140075d2a  nop     dword ptr [rax+rax+00h]
0x140075d2f  mov     edi, 0C000009Ah
0x140075d34  test    rbx, rbx
0x140075d37  jz      short loc_140075D3E
0x140075d39  call    Smb2Revert
0x140075d3e  mov     eax, edi
0x140075d40  lea     r11, [rsp+0F0h+var_20]
0x140075d48  mov     rbx, [r11+38h]
0x140075d4c  mov     rsi, [r11+40h]
0x140075d50  mov     rsp, r11
0x140075d53  pop     r15
0x140075d55  pop     r14
0x140075d57  pop     r12
0x140075d59  pop     rdi
0x140075d5a  pop     rbp
0x140075d5b  retn
0x140075d5d  mov     rdx, rsi
0x140075d60  mov     [r15], rsi
0x140075d63  mov     rcx, r14
0x140075d66  call    Smb2ReplaceFileHandle
0x140075d6b  mov     edi, eax
0x140075d6d  test    eax, eax
0x140075d6f  jns     short loc_140075D7E
0x140075d71  mov     rcx, rsi; P
0x140075d74  call    Smb2DereferenceHandle
0x140075d79  mov     [r15], r12
0x140075d7c  jmp     short loc_140075D34
0x140075d7e  test    rbx, rbx
0x140075d81  jz      short loc_140075D3E
0x140075d83  mov     [rsi+50h], rbx
0x140075d87  mov     eax, 1
0x140075d8c  lock xadd [rbx], rax
0x140075d91  add     rax, 2
0x140075d95  test    rax, 0FFFFFFFFFFFFFFFEh
0x140075d9b  jnz     short loc_140075D39
0x140075d9d  int     2Ch; Windows NT - assertion failure
0x140075d9f  jmp     short loc_140075D39
```
