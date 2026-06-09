# VsmmDmSlpIoctlEnable

- ea: `0x1400e1900`
- end: `0x1400e1c7b`
- name: `VsmmDmSlpIoctlEnable`
- size: `891`
- prototype: `__int64 __fastcall(__int64, const wchar_t *)`
- caller_count: `1`
- callee_count: `16`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140035698`

## callees

- `0x140009ff4`
- `0x1400101c4`
- `0x14001badc`
- `0x14001c908`
- `0x14001cb84`
- `0x14001f7d0`
- `0x140034554`
- `0x140034914`
- `0x140038630`
- `0x14009e144`
- `0x14009e44c`
- `0x1400a9a10`
- `0x1400dd8d4`
- `0x1400e1900`
- `0x1400f30d0`
- `0x1400f69c0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400e1aa7`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400e1aa7`
- `ntoskrnl!ExAllocatePool2` at `0x1400e19f4`
- `ntoskrnl!ExAllocatePool2` at `0x1400e1a32`
- `ntoskrnl!ExAllocatePool2` at `0x1400e19f4`
- `ntoskrnl!ExAllocatePool2` at `0x1400e1a32`
- `ntoskrnl!ZwOpenFile` at `0x1400e1af7`
- `ntoskrnl!ZwOpenFile` at `0x1400e1af7`
- `ntoskrnl!RtlSetAllBitsEx` at `0x1400e1ba5`
- `ntoskrnl!RtlSetAllBitsEx` at `0x1400e1ba5`

## pseudocode

```c
__int64 __fastcall VsmmDmSlpIoctlEnable(__int64 a1, const wchar_t *a2)
{
  __int64 v2; // r12
  NTSTATUS v5; // ebx
  char *Pool2; // rax
  char *v7; // r14
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r15
  __int64 Next; // rax
  __int64 v13; // rsi
  unsigned int i; // esi
  __int64 v16; // [rsp+30h] [rbp-50h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+38h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-38h] BYREF
  __int64 v19; // [rsp+C0h] [rbp+40h] BYREF
  __int64 v20; // [rsp+D8h] [rbp+58h] BYREF

  v2 = a1 + 3736;
  v16 = a1 + 3736;
  v19 = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  VidObjectLockAcquireExclusive(a1 + 3736);
  if ( *(_BYTE *)(a1 + 8460)
    || (*(_QWORD *)(a1 + 32) & 0x31E0) != 0
    || (*(_QWORD *)(a1 + 16) & 0x200LL) != 0
    || (*(_QWORD *)(a1 + 32) & 0x8000LL) != 0
    || *(_BYTE *)(a1 + 10424)
    || *(_BYTE *)(a1 + 2040) != 1
    || *(_DWORD *)(a1 + 8632) )
  {
    v5 = -1073741811;
    goto LABEL_33;
  }
  if ( !(unsigned __int8)VsmmPartitionBlockDeviceAttach(a1, 1) )
  {
    v5 = -1073741637;
    VidTraceErrorInternal0("VsmmDmSlpIoctlEnable", "onecore\\vm\\vid\\sys\\vsmm\\vsmmdmslp.c", 472);
    goto LABEL_33;
  }
  Pool2 = (char *)ExAllocatePool2(64, 808, 1833788502);
  *(_QWORD *)(a1 + 8464) = Pool2;
  v7 = Pool2;
  if ( !Pool2 )
  {
    v5 = -1073741670;
LABEL_31:
    VsmmPartitionUnblockDeviceAttach(a1);
    goto LABEL_33;
  }
  VsmmDmSlppInfoInitialize(Pool2);
  if ( (*(_BYTE *)(a1 + 40) & 2) != 0 )
  {
    v8 = ExAllocatePool2(64, 152, 1833788502);
    *(_QWORD *)(a1 + 8568) = v8;
    if ( !v8 )
    {
      v5 = -1073741670;
LABEL_30:
      VsmmDmSlppDisableMemoryBlocks(a1);
      VsmmDmSlpUninitialize(a1);
      goto LABEL_31;
    }
    v5 = VsmmCryptPartitionKeysGenerateAndInitialize(v10, v9, v8);
    if ( v5 < 0 )
      goto LABEL_30;
  }
  v5 = RtlStringCchCopyNW((NTSTRSAFE_PWSTR)v7 + 116, 0x100u, a2, 0xFFu);
  if ( v5 < 0 )
    goto LABEL_30;
  *(_OWORD *)(v7 + 216) = 0;
  *((_WORD *)v7 + 109) = 512;
  RtlInitUnicodeString((PUNICODE_STRING)(v7 + 216), (PCWSTR)v7 + 116);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 512;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)(v7 + 216);
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v5 = ZwOpenFile((PHANDLE)v7 + 26, 0x80000020, &ObjectAttributes, &IoStatusBlock, 3u, 1u);
  if ( v5 < 0 )
    goto LABEL_30;
  v11 = 0;
  v20 = -1;
  while ( 1 )
  {
    Next = VidHandleTableGetNext(a1 + 3232, &v20);
    v13 = Next;
    if ( !Next )
      break;
    if ( (*(_DWORD *)(Next + 20) & 9) == 1 )
    {
      v5 = VsmmPioFileOpen(Next, *((_QWORD *)v7 + 26), *((_QWORD *)v7 + 93));
      if ( v5 < 0
        || (++*((_QWORD *)v7 + 93), v5 = VsmmMemoryBlockBitmapSetup(v13 + 552, v13), v5 < 0)
        || (v5 = VsmmMemoryBlockBitmapSetup(v13 + 576, v13), v5 < 0) )
      {
LABEL_29:
        v2 = a1 + 3736;
        goto LABEL_30;
      }
      RtlSetAllBitsEx(v13 + 584);
      VsmmMemoryBlockBitmapSubtract(v13 + 576, v13 + 344, &v19);
      v11 += *(_QWORD *)(v13 + 48) - v19;
    }
  }
  for ( i = 0; i < *(_DWORD *)(a1 + 3200); ++i )
  {
    v5 = VsmmDmSlpVpInitialize(*(_QWORD *)(a1 + 3208) + 2512LL * i);
    if ( v5 < 0 )
      goto LABEL_29;
  }
  v5 = 0;
  _InterlockedXor((volatile signed __int32 *)(a1 + 8472), 0x10000000u);
  *(_BYTE *)(a1 + 8460) = 1;
  v2 = v16;
  *((_QWORD *)v7 + 94) = v11;
LABEL_33:
  VidObjectLockRelease(v2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400e1900  mov     [rsp-38h+arg_8], rbx
0x1400e1905  push    rbp
0x1400e1906  push    rsi
0x1400e1907  push    rdi
0x1400e1908  push    r12
0x1400e190a  push    r13
0x1400e190c  push    r14
0x1400e190e  push    r15
0x1400e1910  mov     rbp, rsp
0x1400e1913  sub     rsp, 80h
0x1400e191a  xorps   xmm0, xmm0
0x1400e191d  lea     r12, [rcx+0E98h]
0x1400e1924  mov     rdi, rcx
0x1400e1927  mov     [rbp+var_50], r12
0x1400e192b  xor     eax, eax
0x1400e192d  mov     rcx, r12
0x1400e1930  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1400e1934  mov     r15, rdx
0x1400e1937  mov     [rbp+arg_0], rax
0x1400e193b  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1400e193f  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1400e1943  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x1400e1947  call    VidObjectLockAcquireExclusive
0x1400e194c  cmp     byte ptr [rdi+210Ch], 0
0x1400e1953  jnz     loc_1400E1C50
0x1400e1959  mov     rax, [rdi+20h]
0x1400e195d  test    rax, 31E0h
0x1400e1963  jnz     loc_1400E1C50
0x1400e1969  mov     r13d, 200h
0x1400e196f  test    [rdi+10h], r13
0x1400e1973  setz    cl
0x1400e1976  bt      rax, 0Fh
0x1400e197b  setnb   al
0x1400e197e  test    al, cl
0x1400e1980  jz      loc_1400E1C50
0x1400e1986  cmp     byte ptr [rdi+28B8h], 0
0x1400e198d  jnz     loc_1400E1C50
0x1400e1993  mov     eax, 1
0x1400e1998  cmp     [rdi+7F8h], al
0x1400e199e  jnz     loc_1400E1C50
0x1400e19a4  cmp     dword ptr [rdi+21B8h], 0
0x1400e19ab  jnz     loc_1400E1C50
0x1400e19b1  mov     edx, eax
0x1400e19b3  mov     rcx, rdi
0x1400e19b6  call    VsmmPartitionBlockDeviceAttach
0x1400e19bb  test    al, al
0x1400e19bd  jnz     short loc_1400E19E0
0x1400e19bf  mov     ebx, 0C00000BBh
0x1400e19c4  lea     r8d, [r13-28h]
0x1400e19c8  lea     rdx, aOnecoreVmVidSy_6; "onecore\\vm\\vid\\sys\\vsmm\\vsmmdmslp."...
0x1400e19cf  lea     rcx, aVsmmdmslpioctl; "VsmmDmSlpIoctlEnable"
0x1400e19d6  call    VidTraceErrorInternal0
0x1400e19db  jmp     loc_1400E1C55
0x1400e19e0  mov     ebx, 6D4D6456h
0x1400e19e5  mov     esi, 40h ; '@'
0x1400e19ea  mov     r8d, ebx
0x1400e19ed  mov     ecx, esi
0x1400e19ef  mov     edx, 328h
0x1400e19f4  call    cs:__imp_ExAllocatePool2
0x1400e19fb  nop     dword ptr [rax+rax+00h]
0x1400e1a00  mov     [rdi+2110h], rax
0x1400e1a07  mov     r14, rax
0x1400e1a0a  test    rax, rax
0x1400e1a0d  jnz     short loc_1400E1A19
0x1400e1a0f  mov     ebx, 0C000009Ah
0x1400e1a14  jmp     loc_1400E1C46
0x1400e1a19  mov     rcx, r14; void *
0x1400e1a1c  call    VsmmDmSlppInfoInitialize
0x1400e1a21  test    byte ptr [rdi+28h], 2
0x1400e1a25  jz      short loc_1400E1A66
0x1400e1a27  mov     r8d, ebx
0x1400e1a2a  mov     edx, 98h
0x1400e1a2f  mov     rcx, rsi
0x1400e1a32  call    cs:__imp_ExAllocatePool2
0x1400e1a39  nop     dword ptr [rax+rax+00h]
0x1400e1a3e  mov     [rdi+2178h], rax
0x1400e1a45  test    rax, rax
0x1400e1a48  jnz     short loc_1400E1A54
0x1400e1a4a  mov     ebx, 0C000009Ah
0x1400e1a4f  jmp     loc_1400E1C2C
0x1400e1a54  mov     r8, rax
0x1400e1a57  call    VsmmCryptPartitionKeysGenerateAndInitialize
0x1400e1a5c  mov     ebx, eax
0x1400e1a5e  test    eax, eax
0x1400e1a60  js      loc_1400E1C2C
0x1400e1a66  mov     r9d, 0FFh; cchToCopy
0x1400e1a6c  lea     rsi, [r14+0E8h]
0x1400e1a73  mov     r8, r15; pszSrc
0x1400e1a76  mov     rcx, rsi; pszDest
0x1400e1a79  lea     edx, [r9+1]; cchDest
0x1400e1a7d  call    RtlStringCchCopyNW
0x1400e1a82  mov     ebx, eax
0x1400e1a84  test    eax, eax
0x1400e1a86  js      loc_1400E1C2C
0x1400e1a8c  lea     rbx, [r14+0D8h]
0x1400e1a93  xorps   xmm0, xmm0
0x1400e1a96  movups  xmmword ptr [rbx], xmm0
0x1400e1a99  mov     rcx, rbx; DestinationString
0x1400e1a9c  mov     [r14+0DAh], r13w
0x1400e1aa4  mov     rdx, rsi; SourceString
0x1400e1aa7  call    cs:__imp_RtlInitUnicodeString
0x1400e1aae  nop     dword ptr [rax+rax+00h]
0x1400e1ab3  xorps   xmm0, xmm0
0x1400e1ab6  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400e1abd  mov     esi, 1
0x1400e1ac2  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1400e1aca  mov     [rsp+80h+OpenOptions], esi; OpenOptions
0x1400e1ace  lea     rcx, [r14+0D0h]; FileHandle
0x1400e1ad5  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x1400e1ad9  mov     [rsp+80h+ShareAccess], 3; ShareAccess
0x1400e1ae1  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400e1ae5  mov     [rbp+ObjectAttributes.Attributes], r13d
0x1400e1ae9  mov     edx, 80000020h; DesiredAccess
0x1400e1aee  mov     [rbp+ObjectAttributes.ObjectName], rbx
0x1400e1af2  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400e1af7  call    cs:__imp_ZwOpenFile
0x1400e1afe  nop     dword ptr [rax+rax+00h]
0x1400e1b03  mov     ebx, eax
0x1400e1b05  test    eax, eax
0x1400e1b07  js      loc_1400E1C31
0x1400e1b0d  xor     r15d, r15d
0x1400e1b10  mov     [rbp+arg_18], 0FFFFFFFFFFFFFFFFh
0x1400e1b18  mov     r12d, esi
0x1400e1b1b  lea     rdx, [rbp+arg_18]
0x1400e1b1f  lea     rcx, [rdi+0CA0h]
0x1400e1b26  call    VidHandleTableGetNext
0x1400e1b2b  mov     rsi, rax
0x1400e1b2e  test    rax, rax
0x1400e1b31  jz      loc_1400E1BDA
0x1400e1b37  mov     ecx, [rax+14h]
0x1400e1b3a  and     cl, 9
0x1400e1b3d  cmp     cl, r12b
0x1400e1b40  jnz     short loc_1400E1B1B
0x1400e1b42  mov     r8, [r14+2E8h]
0x1400e1b49  mov     rcx, rax
0x1400e1b4c  mov     rdx, [r14+0D0h]
0x1400e1b53  call    VsmmPioFileOpen
0x1400e1b58  mov     ebx, eax
0x1400e1b5a  test    eax, eax
0x1400e1b5c  js      loc_1400E1C25
0x1400e1b62  add     [r14+2E8h], r12
0x1400e1b69  lea     rcx, [rsi+228h]
0x1400e1b70  mov     rdx, rsi
0x1400e1b73  call    VsmmMemoryBlockBitmapSetup
0x1400e1b78  mov     ebx, eax
0x1400e1b7a  test    eax, eax
0x1400e1b7c  js      loc_1400E1C25
0x1400e1b82  lea     r12, [rsi+240h]
0x1400e1b89  mov     rdx, rsi
0x1400e1b8c  mov     rcx, r12
0x1400e1b8f  call    VsmmMemoryBlockBitmapSetup
0x1400e1b94  mov     ebx, eax
0x1400e1b96  test    eax, eax
0x1400e1b98  js      loc_1400E1C25
0x1400e1b9e  lea     rcx, [rsi+248h]
0x1400e1ba5  call    cs:__imp_RtlSetAllBitsEx
0x1400e1bac  nop     dword ptr [rax+rax+00h]
0x1400e1bb1  lea     rdx, [rsi+158h]
0x1400e1bb8  mov     rcx, r12
0x1400e1bbb  lea     r8, [rbp+arg_0]
0x1400e1bbf  call    VsmmMemoryBlockBitmapSubtract
0x1400e1bc4  mov     rax, [rsi+30h]
0x1400e1bc8  mov     r12d, 1
0x1400e1bce  sub     rax, [rbp+arg_0]
0x1400e1bd2  add     r15, rax
0x1400e1bd5  jmp     loc_1400E1B1B
0x1400e1bda  xor     esi, esi
0x1400e1bdc  cmp     esi, [rdi+0C80h]
0x1400e1be2  jnb     short loc_1400E1C04
0x1400e1be4  mov     eax, esi
0x1400e1be6  imul    rcx, rax, 9D0h
0x1400e1bed  add     rcx, [rdi+0C88h]
0x1400e1bf4  call    VsmmDmSlpVpInitialize
0x1400e1bf9  mov     ebx, eax
0x1400e1bfb  test    eax, eax
0x1400e1bfd  js      short loc_1400E1C25
0x1400e1bff  add     esi, r12d
0x1400e1c02  jmp     short loc_1400E1BDC
0x1400e1c04  xor     ebx, ebx
0x1400e1c06  lock xor dword ptr [rdi+2118h], 10000000h
0x1400e1c11  mov     [rdi+210Ch], r12b
0x1400e1c18  mov     r12, [rbp+var_50]
0x1400e1c1c  mov     [r14+2F0h], r15
0x1400e1c23  jmp     short loc_1400E1C55
0x1400e1c25  lea     r12, [rdi+0E98h]
0x1400e1c2c  mov     esi, 1
0x1400e1c31  mov     rcx, rdi
0x1400e1c34  call    VsmmDmSlppDisableMemoryBlocks
0x1400e1c39  mov     rcx, rdi
0x1400e1c3c  call    VsmmDmSlpUninitialize
0x1400e1c41  test    sil, sil
0x1400e1c44  jz      short loc_1400E1C55
0x1400e1c46  mov     rcx, rdi
0x1400e1c49  call    VsmmPartitionUnblockDeviceAttach
0x1400e1c4e  jmp     short loc_1400E1C55
0x1400e1c50  mov     ebx, 0C000000Dh
0x1400e1c55  mov     rcx, r12
0x1400e1c58  call    VidObjectLockRelease
0x1400e1c5d  mov     eax, ebx
0x1400e1c5f  mov     rbx, [rsp+80h+arg_8]
0x1400e1c67  add     rsp, 80h
0x1400e1c6e  pop     r15
0x1400e1c70  pop     r14
0x1400e1c72  pop     r13
0x1400e1c74  pop     r12
0x1400e1c76  pop     rdi
0x1400e1c77  pop     rsi
0x1400e1c78  pop     rbp
0x1400e1c79  retn
```
