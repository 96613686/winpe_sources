# Smb2ReopenFile

- ea: `0x140075bb8`
- end: `0x140075d51`
- name: `Smb2ReopenFile`
- size: `409`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14006e180`

## callees

- `0x140013810`
- `0x140015960`
- `0x14002a7e8`
- `0x1400593dc`
- `0x140075bb8`
- `0x140077600`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140075cd3`
- `ntoskrnl!ZwClose` at `0x140075cd3`
- `ntoskrnl!IoCreateFile` at `0x140075ca0`
- `ntoskrnl!IoCreateFile` at `0x140075ca0`

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
0x140075bb8  mov     [rsp-8+arg_8], rbx
0x140075bbd  mov     [rsp-8+arg_10], rsi
0x140075bc2  push    rbp
0x140075bc3  push    rdi
0x140075bc4  push    r12
0x140075bc6  push    r14
0x140075bc8  push    r15
0x140075bca  lea     rbp, [rsp-37h]
0x140075bcf  sub     rsp, 0D0h
0x140075bd6  mov     eax, [rcx+0E0h]
0x140075bdc  xor     r12d, r12d
0x140075bdf  mov     dword ptr [rbp+57h+ObjectAttributes+4], r12d
0x140075be3  xorps   xmm0, xmm0
0x140075be6  mov     dword ptr [rbp+57h+ObjectAttributes+1Ch], r12d
0x140075bea  mov     r15, r9
0x140075bed  mov     [rbp+57h+FileHandle], r12
0x140075bf1  mov     rbx, r8
0x140075bf4  mov     [rbp+57h+var_78], r12
0x140075bf8  mov     r14, rcx
0x140075bfb  mov     [rbp+57h+var_70], r12
0x140075bff  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140075c03  test    al, 40h
0x140075c05  jnz     short loc_140075C11
0x140075c07  mov     eax, 0C00000BBh
0x140075c0c  jmp     loc_140075CF0
0x140075c11  mov     rax, [rdx+58h]
0x140075c15  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x140075c19  lea     rax, [rbp+57h+var_78]
0x140075c1d  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140075c21  mov     [r9], r12
0x140075c24  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140075c2b  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140075c32  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140075c37  test    rbx, rbx
0x140075c3a  jz      short loc_140075C4C
0x140075c3c  mov     rcx, rbx
0x140075c3f  call    Smb2ImpersonateSecurityContext
0x140075c44  test    eax, eax
0x140075c46  js      loc_140075CF0
0x140075c4c  mov     eax, [r14+0C0h]
0x140075c53  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140075c57  mov     edx, [r14+0B8h]; DesiredAccess
0x140075c5e  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140075c62  mov     [rsp+0F0h+Options], r12d; Options
0x140075c67  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x140075c6b  mov     [rsp+0F0h+InternalParameters], r12; InternalParameters
0x140075c70  mov     [rsp+0F0h+CreateFileType], r12d; CreateFileType
0x140075c75  mov     [rsp+0F0h+EaLength], r12d; EaLength
0x140075c7a  mov     [rsp+0F0h+EaBuffer], r12; EaBuffer
0x140075c7f  mov     [rsp+0F0h+CreateOptions], eax; CreateOptions
0x140075c83  mov     eax, [r14+0BCh]
0x140075c8a  mov     [rsp+0F0h+Disposition], 1; Disposition
0x140075c92  mov     [rsp+0F0h+ShareAccess], eax; ShareAccess
0x140075c96  mov     [rsp+0F0h+FileAttributes], r12d; FileAttributes
0x140075c9b  mov     [rsp+0F0h+AllocationSize], r12; AllocationSize
0x140075ca0  call    cs:__imp_IoCreateFile
0x140075ca7  nop     dword ptr [rax+rax+00h]
0x140075cac  mov     edi, eax
0x140075cae  test    eax, eax
0x140075cb0  js      short loc_140075CE4
0x140075cb2  mov     rdx, [rbp+57h+FileHandle]
0x140075cb6  lea     r8, [rbp+57h+var_80]
0x140075cba  mov     rcx, [r14+40h]
0x140075cbe  mov     [rbp+57h+var_80], r12
0x140075cc2  call    Smb2AllocateReferencedHandle
0x140075cc7  mov     rsi, rax
0x140075cca  test    rax, rax
0x140075ccd  jnz     short loc_140075D0D
0x140075ccf  mov     rcx, [rbp+57h+FileHandle]; Handle
0x140075cd3  call    cs:__imp_ZwClose
0x140075cda  nop     dword ptr [rax+rax+00h]
0x140075cdf  mov     edi, 0C000009Ah
0x140075ce4  test    rbx, rbx
0x140075ce7  jz      short loc_140075CEE
0x140075ce9  call    Smb2Revert
0x140075cee  mov     eax, edi
0x140075cf0  lea     r11, [rsp+0F0h+var_20]
0x140075cf8  mov     rbx, [r11+38h]
0x140075cfc  mov     rsi, [r11+40h]
0x140075d00  mov     rsp, r11
0x140075d03  pop     r15
0x140075d05  pop     r14
0x140075d07  pop     r12
0x140075d09  pop     rdi
0x140075d0a  pop     rbp
0x140075d0b  retn
0x140075d0d  mov     rdx, rsi
0x140075d10  mov     [r15], rsi
0x140075d13  mov     rcx, r14
0x140075d16  call    Smb2ReplaceFileHandle
0x140075d1b  mov     edi, eax
0x140075d1d  test    eax, eax
0x140075d1f  jns     short loc_140075D2E
0x140075d21  mov     rcx, rsi; P
0x140075d24  call    Smb2DereferenceHandle
0x140075d29  mov     [r15], r12
0x140075d2c  jmp     short loc_140075CE4
0x140075d2e  test    rbx, rbx
0x140075d31  jz      short loc_140075CEE
0x140075d33  mov     [rsi+50h], rbx
0x140075d37  mov     eax, 1
0x140075d3c  lock xadd [rbx], rax
0x140075d41  add     rax, 2
0x140075d45  test    rax, 0FFFFFFFFFFFFFFFEh
0x140075d4b  jnz     short loc_140075CE9
0x140075d4d  int     2Ch; Windows NT - assertion failure
0x140075d4f  jmp     short loc_140075CE9
```
