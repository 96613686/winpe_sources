# VhdmpiExtractRawScsiUserBuffer(_VHD_RAW_SCSI *)

- ea: `0x140046a58`
- end: `0x140046c98`
- name: `?VhdmpiExtractRawScsiUserBuffer@@YAJPEAU_VHD_RAW_SCSI@@@Z`
- size: `576`
- prototype: `__int64 __fastcall(struct _VHD_RAW_SCSI *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400479f8`

## callees

- `0x140046a58`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x140046c71`
- `ntoskrnl!IoFreeMdl` at `0x140046c71`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140046c17`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140046c17`
- `ntoskrnl!IoAllocateMdl` at `0x140046b05`
- `ntoskrnl!IoAllocateMdl` at `0x140046b05`
- `ntoskrnl!MmProbeAndLockPages` at `0x140046b9f`
- `ntoskrnl!MmProbeAndLockPages` at `0x140046b9f`
- `ntoskrnl!MmUnlockPages` at `0x140046c62`
- `ntoskrnl!MmUnlockPages` at `0x140046c62`

## pseudocode

```c
__int64 __fastcall VhdmpiExtractRawScsiUserBuffer(struct _VHD_RAW_SCSI *a1)
{
  __int64 v2; // r13
  ULONG v3; // edx
  unsigned int v4; // ebx
  char v5; // r14
  unsigned int v6; // ebx
  LOCK_OPERATION v7; // esi
  __int64 v8; // r15
  PMDL Mdl; // rdi
  bool v10; // zf
  unsigned int v11; // ebx
  unsigned int v12; // ebx
  unsigned int v13; // ebx
  unsigned int v14; // ebx
  PVOID v15; // rax

  v2 = *((_QWORD *)a1 + 13);
  v3 = *(_DWORD *)(v2 + 12);
  if ( !v3 )
    return 0;
  v5 = 0;
  v6 = *(unsigned __int8 *)(v2 + 24);
  if ( v6 > 0x5A )
  {
    if ( v6 > 0x89 )
    {
      if ( v6 != 138 && v6 != 147 )
      {
        if ( v6 == 158 || v6 == 168 )
          goto LABEL_12;
        if ( v6 != 170 )
          goto LABEL_33;
      }
      goto LABEL_17;
    }
    if ( v6 == 137 )
      goto LABEL_17;
    if ( v6 != 94 )
    {
      if ( v6 != 95 && v6 != 131 )
      {
        if ( v6 == 132 || v6 == 136 )
          goto LABEL_12;
        goto LABEL_33;
      }
      goto LABEL_17;
    }
LABEL_12:
    v7 = IoWriteAccess;
    goto LABEL_18;
  }
  if ( v6 == 90 )
    goto LABEL_12;
  if ( v6 > 0x1D )
  {
    if ( v6 == 37 || v6 == 40 )
      goto LABEL_12;
    if ( v6 != 42 && v6 - 65 > 1 )
      goto LABEL_33;
LABEL_17:
    v7 = IoReadAccess;
LABEL_18:
    v8 = *(_QWORD *)(*((_QWORD *)a1 + 1) + 24LL);
    Mdl = IoAllocateMdl(*(PVOID *)(v2 + 16), v3, 0, 0, 0);
    if ( !Mdl )
    {
LABEL_19:
      v4 = -1073741670;
      goto LABEL_52;
    }
    MmProbeAndLockPages(Mdl, *(_BYTE *)(*(_QWORD *)(*((_QWORD *)a1 + 1) + 96LL) + 64LL), v7);
    v5 = 1;
    if ( v6 > 0x88 )
    {
      v11 = v6 - 137;
      if ( !v11 )
        goto LABEL_51;
      v12 = v11 - 1;
      if ( !v12 )
        goto LABEL_51;
      v13 = v12 - 9;
      if ( !v13 )
        goto LABEL_51;
      v14 = v13 - 21;
      if ( !v14 )
        goto LABEL_51;
      v10 = v14 == 2;
    }
    else
    {
      if ( v6 == 136 || v6 == 8 || v6 == 10 || v6 == 40 || v6 == 42 )
        goto LABEL_51;
      v10 = v6 == 65;
    }
    if ( !v10 )
    {
      v15 = (Mdl->MdlFlags & 5) != 0
          ? Mdl->MappedSystemVa
          : MmMapLockedPagesSpecifyCache(Mdl, 0, MmCached, 0, 0, 0x40000010u);
      *(_QWORD *)(v8 + 24) = v15;
      if ( !v15 )
        goto LABEL_19;
    }
LABEL_51:
    *(_DWORD *)(v8 + 16) = *(_DWORD *)(v2 + 12);
    *(_QWORD *)(*((_QWORD *)a1 + 1) + 72LL) = Mdl;
    return 0;
  }
  switch ( v6 )
  {
    case 0x1Du:
      goto LABEL_17;
    case 3u:
    case 8u:
      goto LABEL_12;
    case 0xAu:
      goto LABEL_17;
    case 0x12u:
    case 0x1Au:
      goto LABEL_12;
  }
LABEL_33:
  Mdl = 0;
  v4 = -1073741637;
LABEL_52:
  if ( Mdl )
  {
    if ( v5 )
      MmUnlockPages(Mdl);
    IoFreeMdl(Mdl);
  }
  return v4;
}

```

## disassembly

```asm
0x140046a58  mov     [rsp+arg_10], rbx
0x140046a5d  mov     [rsp+arg_18], rsi
0x140046a62  push    rdi
0x140046a63  push    r12
0x140046a65  push    r13
0x140046a67  push    r14
0x140046a69  push    r15
0x140046a6b  sub     rsp, 30h
0x140046a6f  mov     r12, rcx
0x140046a72  mov     r13, [rcx+68h]
0x140046a76  mov     edx, [r13+0Ch]; Length
0x140046a7a  test    edx, edx
0x140046a7c  jnz     short loc_140046A85
0x140046a7e  xor     ebx, ebx
0x140046a80  jmp     loc_140046C7D
0x140046a85  xor     r14b, r14b
0x140046a88  mov     [rsp+58h+arg_0], r14b
0x140046a8d  movzx   ebx, byte ptr [r13+18h]
0x140046a92  cmp     ebx, 5Ah ; 'Z'
0x140046a95  ja      loc_140046B28
0x140046a9b  jz      short loc_140046AC1
0x140046a9d  cmp     ebx, 1Dh
0x140046aa0  ja      short loc_140046AC8
0x140046aa2  jz      short loc_140046AE7
0x140046aa4  cmp     ebx, 3
0x140046aa7  jz      short loc_140046AC1
0x140046aa9  cmp     ebx, 8
0x140046aac  jz      short loc_140046AC1
0x140046aae  cmp     ebx, 0Ah
0x140046ab1  jz      short loc_140046AE7
0x140046ab3  cmp     ebx, 12h
0x140046ab6  jz      short loc_140046AC1
0x140046ab8  cmp     ebx, 1Ah
0x140046abb  jnz     loc_140046B81
0x140046ac1  mov     esi, 1
0x140046ac6  jmp     short loc_140046AE9
0x140046ac8  mov     ecx, ebx
0x140046aca  sub     ecx, 25h ; '%'
0x140046acd  jz      short loc_140046AC1
0x140046acf  sub     ecx, 3
0x140046ad2  jz      short loc_140046AC1
0x140046ad4  sub     ecx, 2
0x140046ad7  jz      short loc_140046AE7
0x140046ad9  sub     ecx, 17h
0x140046adc  jz      short loc_140046AE7
0x140046ade  cmp     ecx, 1
0x140046ae1  jnz     loc_140046B81
0x140046ae7  xor     esi, esi
0x140046ae9  mov     rax, [r12+8]
0x140046aee  mov     r15, [rax+18h]
0x140046af2  mov     [rsp+58h+Irp], 0; Irp
0x140046afb  xor     r9d, r9d; ChargeQuota
0x140046afe  xor     r8d, r8d; SecondaryBuffer
0x140046b01  mov     rcx, [r13+10h]; VirtualAddress
0x140046b05  call    cs:__imp_IoAllocateMdl
0x140046b0c  nop     dword ptr [rax+rax+00h]
0x140046b11  mov     rdi, rax
0x140046b14  mov     [rsp+58h+arg_8], rax
0x140046b19  test    rax, rax
0x140046b1c  jnz     short loc_140046B8D
0x140046b1e  mov     ebx, 0C000009Ah
0x140046b23  jmp     loc_140046C55
0x140046b28  cmp     ebx, 89h
0x140046b2e  ja      short loc_140046B57
0x140046b30  jz      short loc_140046AE7
0x140046b32  mov     ecx, ebx
0x140046b34  sub     ecx, 5Eh ; '^'
0x140046b37  jz      short loc_140046AC1
0x140046b39  sub     ecx, 1
0x140046b3c  jz      short loc_140046AE7
0x140046b3e  sub     ecx, 24h ; '$'
0x140046b41  jz      short loc_140046AE7
0x140046b43  sub     ecx, 1
0x140046b46  jz      loc_140046AC1
0x140046b4c  cmp     ecx, 4
0x140046b4f  jz      loc_140046AC1
0x140046b55  jmp     short loc_140046B81
0x140046b57  mov     ecx, ebx
0x140046b59  sub     ecx, 8Ah
0x140046b5f  jz      short loc_140046AE7
0x140046b61  sub     ecx, 9
0x140046b64  jz      short loc_140046AE7
0x140046b66  sub     ecx, 0Bh
0x140046b69  jz      loc_140046AC1
0x140046b6f  sub     ecx, 0Ah
0x140046b72  jz      loc_140046AC1
0x140046b78  cmp     ecx, 2
0x140046b7b  jz      loc_140046AE7
0x140046b81  xor     edi, edi
0x140046b83  mov     ebx, 0C00000BBh
0x140046b88  jmp     loc_140046C55
0x140046b8d  mov     rax, [r12+8]
0x140046b92  mov     rdx, [rax+60h]
0x140046b96  mov     r8d, esi; Operation
0x140046b99  mov     dl, [rdx+40h]; AccessMode
0x140046b9c  mov     rcx, rdi; MemoryDescriptorList
0x140046b9f  call    cs:__imp_MmProbeAndLockPages
0x140046ba6  nop     dword ptr [rax+rax+00h]
0x140046bab  nop
0x140046bac  mov     r14b, 1
0x140046baf  mov     eax, 88h
0x140046bb4  cmp     ebx, eax
0x140046bb6  ja      short loc_140046BD3
0x140046bb8  jz      short loc_140046C30
0x140046bba  cmp     ebx, 8
0x140046bbd  jz      short loc_140046C30
0x140046bbf  cmp     ebx, 0Ah
0x140046bc2  jz      short loc_140046C30
0x140046bc4  cmp     ebx, 28h ; '('
0x140046bc7  jz      short loc_140046C30
0x140046bc9  cmp     ebx, 2Ah ; '*'
0x140046bcc  jz      short loc_140046C30
0x140046bce  cmp     ebx, 41h ; 'A'
0x140046bd1  jmp     short loc_140046BED
0x140046bd3  sub     ebx, 89h
0x140046bd9  jz      short loc_140046C30
0x140046bdb  sub     ebx, 1
0x140046bde  jz      short loc_140046C30
0x140046be0  sub     ebx, 9
0x140046be3  jz      short loc_140046C30
0x140046be5  sub     ebx, 15h
0x140046be8  jz      short loc_140046C30
0x140046bea  cmp     ebx, 2
0x140046bed  jz      short loc_140046C30
0x140046bef  test    byte ptr [rdi+0Ah], 5
0x140046bf3  jz      short loc_140046BFB
0x140046bf5  mov     rax, [rdi+18h]
0x140046bf9  jmp     short loc_140046C23
0x140046bfb  mov     [rsp+58h+Priority], 40000010h; Priority
0x140046c03  mov     dword ptr [rsp+58h+Irp], 0; BugCheckOnFailure
0x140046c0b  xor     r9d, r9d; RequestedAddress
0x140046c0e  xor     edx, edx; AccessMode
0x140046c10  lea     r8d, [r9+1]; CacheType
0x140046c14  mov     rcx, rdi; MemoryDescriptorList
0x140046c17  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140046c1e  nop     dword ptr [rax+rax+00h]
0x140046c23  mov     [r15+18h], rax
0x140046c27  test    rax, rax
0x140046c2a  jz      loc_140046B1E
0x140046c30  mov     eax, [r13+0Ch]
0x140046c34  mov     [r15+10h], eax
0x140046c38  mov     rax, [r12+8]
0x140046c3d  mov     [rax+48h], rdi
0x140046c41  xor     ebx, ebx
0x140046c43  jmp     short loc_140046C51
0x140046c45  mov     ebx, eax
0x140046c47  mov     rdi, [rsp+58h+arg_8]
0x140046c4c  mov     r14b, [rsp+58h+arg_0]
0x140046c51  test    ebx, ebx
0x140046c53  jns     short loc_140046C7D
0x140046c55  test    rdi, rdi
0x140046c58  jz      short loc_140046C7D
0x140046c5a  test    r14b, r14b
0x140046c5d  jz      short loc_140046C6E
0x140046c5f  mov     rcx, rdi; MemoryDescriptorList
0x140046c62  call    cs:__imp_MmUnlockPages
0x140046c69  nop     dword ptr [rax+rax+00h]
0x140046c6e  mov     rcx, rdi; Mdl
0x140046c71  call    cs:__imp_IoFreeMdl
0x140046c78  nop     dword ptr [rax+rax+00h]
0x140046c7d  mov     eax, ebx
0x140046c7f  mov     rbx, [rsp+58h+arg_10]
0x140046c84  mov     rsi, [rsp+58h+arg_18]
0x140046c89  add     rsp, 30h
0x140046c8d  pop     r15
0x140046c8f  pop     r14
0x140046c91  pop     r13
0x140046c93  pop     r12
0x140046c95  pop     rdi
0x140046c96  retn
```
