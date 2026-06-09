# TdiOpenNetbiosAddress

- ea: `0x140003c30`
- end: `0x140003d8f`
- name: `TdiOpenNetbiosAddress`
- size: `351`
- prototype: `NTSTATUS __stdcall(PHANDLE FileHandle, PUCHAR Buffer, PVOID DeviceName, PVOID Name)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x140003c30`

## import_xrefs

- `ntoskrnl!NtCreateFile` at `0x140003ce5`
- `ntoskrnl!NtCreateFile` at `0x140003ce5`

## pseudocode

```c
NTSTATUS __stdcall TdiOpenNetbiosAddress(PHANDLE FileHandle, PUCHAR Buffer, PVOID DeviceName, PVOID Name)
{
  ULONG EaLength; // ecx
  NTSTATUS result; // eax
  __int128 v7; // xmm1
  __int64 v8; // rax
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-68h] BYREF
  _OWORD v10[2]; // [rsp+80h] [rbp-58h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-38h] BYREF

  IoStatusBlock = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  memset(v10, 0, 26);
  if ( Name )
  {
    EaLength = 51;
    if ( !Buffer )
      return -1073741823;
    *(_DWORD *)Buffer = 0;
    *((_DWORD *)Buffer + 1) = 1708032;
    strcpy((char *)Buffer + 8, "TransportAddress");
    *(_QWORD *)&v10[0] = 0x11001200000001LL;
    WORD4(v10[0]) = 0;
    *(_OWORD *)((char *)v10 + 10) = *(_OWORD *)Name;
    v7 = *(_OWORD *)((char *)v10 + 10);
    v8 = Buffer[5];
    *(_OWORD *)&Buffer[v8 + 9] = v10[0];
    *(_OWORD *)&Buffer[v8 + 19] = v7;
  }
  else
  {
    Buffer = 0;
    EaLength = 0;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)DeviceName;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = NtCreateFile(FileHandle, 0x180u, &ObjectAttributes, &IoStatusBlock, 0, 0, 3u, 2u, 0, Buffer, EaLength);
  if ( result >= 0 )
    return IoStatusBlock.Status;
  return result;
}

```

## disassembly

```asm
0x140003c30  sub     rsp, 0D8h
0x140003c37  mov     r10, rcx
0x140003c3a  xorps   xmm0, xmm0
0x140003c3d  movups  xmmword ptr [rsp+0D8h+IoStatusBlock], xmm0
0x140003c42  xor     eax, eax
0x140003c44  xor     r11d, r11d
0x140003c47  mov     dword ptr [rsp+0D8h+ObjectAttributes+4], r11d
0x140003c4f  mov     dword ptr [rsp+0D8h+ObjectAttributes+1Ch], r11d
0x140003c57  movups  xmmword ptr [rsp+0D8h+var_58], xmm0
0x140003c5f  movups  xmmword ptr [rsp+0D8h+var_58+0Ah], xmm0
0x140003c67  test    r9, r9
0x140003c6a  jnz     loc_140003D02
0x140003c70  mov     edx, r11d
0x140003c73  mov     ecx, r11d
0x140003c76  mov     [rsp+0D8h+ObjectAttributes.Length], 30h ; '0'
0x140003c81  mov     [rsp+0D8h+ObjectAttributes.RootDirectory], r11
0x140003c89  mov     [rsp+0D8h+ObjectAttributes.Attributes], 40h ; '@'
0x140003c94  mov     [rsp+0D8h+ObjectAttributes.ObjectName], r8
0x140003c9c  xorps   xmm0, xmm0
0x140003c9f  movdqu  xmmword ptr [rsp+0D8h+ObjectAttributes.SecurityDescriptor], xmm0
0x140003ca8  mov     [rsp+0D8h+EaLength], ecx; EaLength
0x140003cac  mov     [rsp+0D8h+EaBuffer], rdx; EaBuffer
0x140003cb1  mov     [rsp+0D8h+CreateOptions], r11d; CreateOptions
0x140003cb6  mov     [rsp+0D8h+CreateDisposition], 2; CreateDisposition
0x140003cbe  mov     [rsp+0D8h+ShareAccess], 3; ShareAccess
0x140003cc6  mov     [rsp+0D8h+FileAttributes], r11d; FileAttributes
0x140003ccb  mov     [rsp+0D8h+AllocationSize], r11; AllocationSize
0x140003cd0  lea     r9, [rsp+0D8h+IoStatusBlock]; IoStatusBlock
0x140003cd5  lea     r8, [rsp+0D8h+ObjectAttributes]; ObjectAttributes
0x140003cdd  mov     edx, 180h; DesiredAccess
0x140003ce2  mov     rcx, r10; FileHandle
0x140003ce5  call    cs:__imp_NtCreateFile
0x140003cec  nop     dword ptr [rax+rax+00h]
0x140003cf1  test    eax, eax
0x140003cf3  jns     loc_140003D86
0x140003cf9  add     rsp, 0D8h
0x140003d00  retn
0x140003d02  mov     ecx, 33h ; '3'
0x140003d07  mov     [rsp+0D8h+var_78], ecx
0x140003d0b  mov     [rsp+0D8h+var_70], rdx
0x140003d10  test    rdx, rdx
0x140003d13  jnz     short loc_140003D1C
0x140003d15  mov     eax, 0C0000001h
0x140003d1a  jmp     short loc_140003CF9
0x140003d1c  mov     [rdx], r11d
0x140003d1f  mov     dword ptr [rdx+4], 1A1000h
0x140003d26  movups  xmm0, xmmword ptr cs:aTransportaddre; "TransportAddress"
0x140003d2d  movups  xmmword ptr [rdx+8], xmm0
0x140003d31  movzx   eax, byte ptr cs:aTransportaddre+10h; ""
0x140003d38  mov     [rdx+18h], al
0x140003d3b  mov     dword ptr [rsp+0D8h+var_58], 1
0x140003d46  mov     dword ptr [rsp+0D8h+var_58+4], 110012h
0x140003d51  mov     word ptr [rsp+0D8h+var_58+8], r11w
0x140003d5a  movups  xmm1, xmmword ptr [r9]
0x140003d5e  movups  xmmword ptr [rsp+0D8h+var_58+0Ah], xmm1
0x140003d66  movzx   eax, byte ptr [rdx+5]
0x140003d6a  movups  xmm0, xmmword ptr [rsp+0D8h+var_58]
0x140003d72  movups  xmmword ptr [rax+rdx+9], xmm0
0x140003d77  movups  xmmword ptr [rax+rdx+13h], xmm1
0x140003d7c  jmp     loc_140003C76
0x140003d81  jmp     loc_140003CF9
0x140003d86  mov     eax, dword ptr [rsp+0D8h+IoStatusBlock]
0x140003d8a  jmp     loc_140003CF9
```
