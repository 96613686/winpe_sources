# VsmmDmSlpIoctlEnable

- ea: `0x1400e44c8`
- end: `0x1400e4846`
- name: `VsmmDmSlpIoctlEnable`
- size: `894`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `16`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140035708`

## callees

- `0x140009b24`
- `0x140010014`
- `0x14001e1f8`
- `0x14001f0ec`
- `0x14001f364`
- `0x14001fda0`
- `0x1400347a4`
- `0x140034b64`
- `0x1400386a0`
- `0x14009fb74`
- `0x14009fe7c`
- `0x1400ab790`
- `0x1400e036c`
- `0x1400e44c8`
- `0x1400f59d8`
- `0x1400f9410`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400e466f`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400e466f`
- `ntoskrnl!ExAllocatePool2` at `0x1400e45bc`
- `ntoskrnl!ExAllocatePool2` at `0x1400e45fa`
- `ntoskrnl!ExAllocatePool2` at `0x1400e45bc`
- `ntoskrnl!ExAllocatePool2` at `0x1400e45fa`
- `ntoskrnl!ZwOpenFile` at `0x1400e46bf`
- `ntoskrnl!ZwOpenFile` at `0x1400e46bf`
- `ntoskrnl!RtlSetAllBitsEx` at `0x1400e4770`
- `ntoskrnl!RtlSetAllBitsEx` at `0x1400e4770`

## pseudocode

```c
__int64 __fastcall VsmmDmSlpIoctlEnable(__int64 a1, const wchar_t *a2)
{
  __int64 v2; // r12
  int v5; // ebx
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
    if ( (*(_DWORD *)(Next + 264) & 9) == 1 )
    {
      v5 = VsmmPioFileOpen((_QWORD *)Next, *((void **)v7 + 26), *((_QWORD *)v7 + 93));
      if ( v5 < 0
        || (++*((_QWORD *)v7 + 93), v5 = VsmmMemoryBlockBitmapSetup(v13 + 624, v13), v5 < 0)
        || (v5 = VsmmMemoryBlockBitmapSetup(v13 + 648, v13), v5 < 0) )
      {
LABEL_29:
        v2 = a1 + 3736;
        goto LABEL_30;
      }
      RtlSetAllBitsEx(v13 + 656);
      VsmmMemoryBlockBitmapSubtract(v13 + 648, v13 + 416, &v19);
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
0x1400e44c8  mov     [rsp-38h+arg_8], rbx
0x1400e44cd  push    rbp
0x1400e44ce  push    rsi
0x1400e44cf  push    rdi
0x1400e44d0  push    r12
0x1400e44d2  push    r13
0x1400e44d4  push    r14
0x1400e44d6  push    r15
0x1400e44d8  mov     rbp, rsp
0x1400e44db  sub     rsp, 80h
0x1400e44e2  xorps   xmm0, xmm0
0x1400e44e5  lea     r12, [rcx+0E98h]
0x1400e44ec  mov     rdi, rcx
0x1400e44ef  mov     [rbp+var_50], r12
0x1400e44f3  xor     eax, eax
0x1400e44f5  mov     rcx, r12
0x1400e44f8  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1400e44fc  mov     r15, rdx
0x1400e44ff  mov     [rbp+arg_0], rax
0x1400e4503  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1400e4507  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1400e450b  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x1400e450f  call    VidObjectLockAcquireExclusive
0x1400e4514  cmp     byte ptr [rdi+210Ch], 0
0x1400e451b  jnz     loc_1400E481B
0x1400e4521  mov     rax, [rdi+20h]
0x1400e4525  test    rax, 31E0h
0x1400e452b  jnz     loc_1400E481B
0x1400e4531  mov     r13d, 200h
0x1400e4537  test    [rdi+10h], r13
0x1400e453b  setz    cl
0x1400e453e  bt      rax, 0Fh
0x1400e4543  setnb   al
0x1400e4546  test    al, cl
0x1400e4548  jz      loc_1400E481B
0x1400e454e  cmp     byte ptr [rdi+28B8h], 0
0x1400e4555  jnz     loc_1400E481B
0x1400e455b  mov     eax, 1
0x1400e4560  cmp     [rdi+7F8h], al
0x1400e4566  jnz     loc_1400E481B
0x1400e456c  cmp     dword ptr [rdi+21B8h], 0
0x1400e4573  jnz     loc_1400E481B
0x1400e4579  mov     edx, eax
0x1400e457b  mov     rcx, rdi
0x1400e457e  call    VsmmPartitionBlockDeviceAttach
0x1400e4583  test    al, al
0x1400e4585  jnz     short loc_1400E45A8
0x1400e4587  mov     ebx, 0C00000BBh
0x1400e458c  lea     r8d, [r13-28h]
0x1400e4590  lea     rdx, aOnecoreVmVidSy_6; "onecore\\vm\\vid\\sys\\vsmm\\vsmmdmslp."...
0x1400e4597  lea     rcx, aVsmmdmslpioctl; "VsmmDmSlpIoctlEnable"
0x1400e459e  call    VidTraceErrorInternal0
0x1400e45a3  jmp     loc_1400E4820
0x1400e45a8  mov     ebx, 6D4D6456h
0x1400e45ad  mov     esi, 40h ; '@'
0x1400e45b2  mov     r8d, ebx
0x1400e45b5  mov     ecx, esi
0x1400e45b7  mov     edx, 328h
0x1400e45bc  call    cs:__imp_ExAllocatePool2
0x1400e45c3  nop     dword ptr [rax+rax+00h]
0x1400e45c8  mov     [rdi+2110h], rax
0x1400e45cf  mov     r14, rax
0x1400e45d2  test    rax, rax
0x1400e45d5  jnz     short loc_1400E45E1
0x1400e45d7  mov     ebx, 0C000009Ah
0x1400e45dc  jmp     loc_1400E4811
0x1400e45e1  mov     rcx, r14; void *
0x1400e45e4  call    VsmmDmSlppInfoInitialize
0x1400e45e9  test    byte ptr [rdi+28h], 2
0x1400e45ed  jz      short loc_1400E462E
0x1400e45ef  mov     r8d, ebx
0x1400e45f2  mov     edx, 98h
0x1400e45f7  mov     rcx, rsi
0x1400e45fa  call    cs:__imp_ExAllocatePool2
0x1400e4601  nop     dword ptr [rax+rax+00h]
0x1400e4606  mov     [rdi+2178h], rax
0x1400e460d  test    rax, rax
0x1400e4610  jnz     short loc_1400E461C
0x1400e4612  mov     ebx, 0C000009Ah
0x1400e4617  jmp     loc_1400E47F7
0x1400e461c  mov     r8, rax
0x1400e461f  call    VsmmCryptPartitionKeysGenerateAndInitialize
0x1400e4624  mov     ebx, eax
0x1400e4626  test    eax, eax
0x1400e4628  js      loc_1400E47F7
0x1400e462e  mov     r9d, 0FFh; cchToCopy
0x1400e4634  lea     rsi, [r14+0E8h]
0x1400e463b  mov     r8, r15; pszSrc
0x1400e463e  mov     rcx, rsi; pszDest
0x1400e4641  lea     edx, [r9+1]; cchDest
0x1400e4645  call    RtlStringCchCopyNW
0x1400e464a  mov     ebx, eax
0x1400e464c  test    eax, eax
0x1400e464e  js      loc_1400E47F7
0x1400e4654  lea     rbx, [r14+0D8h]
0x1400e465b  xorps   xmm0, xmm0
0x1400e465e  movups  xmmword ptr [rbx], xmm0
0x1400e4661  mov     rcx, rbx; DestinationString
0x1400e4664  mov     [r14+0DAh], r13w
0x1400e466c  mov     rdx, rsi; SourceString
0x1400e466f  call    cs:__imp_RtlInitUnicodeString
0x1400e4676  nop     dword ptr [rax+rax+00h]
0x1400e467b  xorps   xmm0, xmm0
0x1400e467e  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400e4685  mov     esi, 1
0x1400e468a  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1400e4692  mov     [rsp+80h+OpenOptions], esi; OpenOptions
0x1400e4696  lea     rcx, [r14+0D0h]; FileHandle
0x1400e469d  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x1400e46a1  mov     [rsp+80h+ShareAccess], 3; ShareAccess
0x1400e46a9  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400e46ad  mov     [rbp+ObjectAttributes.Attributes], r13d
0x1400e46b1  mov     edx, 80000020h; DesiredAccess
0x1400e46b6  mov     [rbp+ObjectAttributes.ObjectName], rbx
0x1400e46ba  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400e46bf  call    cs:__imp_ZwOpenFile
0x1400e46c6  nop     dword ptr [rax+rax+00h]
0x1400e46cb  mov     ebx, eax
0x1400e46cd  test    eax, eax
0x1400e46cf  js      loc_1400E47FC
0x1400e46d5  xor     r15d, r15d
0x1400e46d8  mov     [rbp+arg_18], 0FFFFFFFFFFFFFFFFh
0x1400e46e0  mov     r12d, esi
0x1400e46e3  lea     rdx, [rbp+arg_18]
0x1400e46e7  lea     rcx, [rdi+0CA0h]
0x1400e46ee  call    VidHandleTableGetNext
0x1400e46f3  mov     rsi, rax
0x1400e46f6  test    rax, rax
0x1400e46f9  jz      loc_1400E47A5
0x1400e46ff  mov     ecx, [rax+108h]
0x1400e4705  and     cl, 9
0x1400e4708  cmp     cl, r12b
0x1400e470b  jnz     short loc_1400E46E3
0x1400e470d  mov     r8, [r14+2E8h]
0x1400e4714  mov     rcx, rax
0x1400e4717  mov     rdx, [r14+0D0h]
0x1400e471e  call    VsmmPioFileOpen
0x1400e4723  mov     ebx, eax
0x1400e4725  test    eax, eax
0x1400e4727  js      loc_1400E47F0
0x1400e472d  add     [r14+2E8h], r12
0x1400e4734  lea     rcx, [rsi+270h]
0x1400e473b  mov     rdx, rsi
0x1400e473e  call    VsmmMemoryBlockBitmapSetup
0x1400e4743  mov     ebx, eax
0x1400e4745  test    eax, eax
0x1400e4747  js      loc_1400E47F0
0x1400e474d  lea     r12, [rsi+288h]
0x1400e4754  mov     rdx, rsi
0x1400e4757  mov     rcx, r12
0x1400e475a  call    VsmmMemoryBlockBitmapSetup
0x1400e475f  mov     ebx, eax
0x1400e4761  test    eax, eax
0x1400e4763  js      loc_1400E47F0
0x1400e4769  lea     rcx, [rsi+290h]
0x1400e4770  call    cs:__imp_RtlSetAllBitsEx
0x1400e4777  nop     dword ptr [rax+rax+00h]
0x1400e477c  lea     rdx, [rsi+1A0h]
0x1400e4783  mov     rcx, r12
0x1400e4786  lea     r8, [rbp+arg_0]
0x1400e478a  call    VsmmMemoryBlockBitmapSubtract
0x1400e478f  mov     rax, [rsi+30h]
0x1400e4793  mov     r12d, 1
0x1400e4799  sub     rax, [rbp+arg_0]
0x1400e479d  add     r15, rax
0x1400e47a0  jmp     loc_1400E46E3
0x1400e47a5  xor     esi, esi
0x1400e47a7  cmp     esi, [rdi+0C80h]
0x1400e47ad  jnb     short loc_1400E47CF
0x1400e47af  mov     eax, esi
0x1400e47b1  imul    rcx, rax, 9D0h
0x1400e47b8  add     rcx, [rdi+0C88h]
0x1400e47bf  call    VsmmDmSlpVpInitialize
0x1400e47c4  mov     ebx, eax
0x1400e47c6  test    eax, eax
0x1400e47c8  js      short loc_1400E47F0
0x1400e47ca  add     esi, r12d
0x1400e47cd  jmp     short loc_1400E47A7
0x1400e47cf  xor     ebx, ebx
0x1400e47d1  lock xor dword ptr [rdi+2118h], 10000000h
0x1400e47dc  mov     [rdi+210Ch], r12b
0x1400e47e3  mov     r12, [rbp+var_50]
0x1400e47e7  mov     [r14+2F0h], r15
0x1400e47ee  jmp     short loc_1400E4820
0x1400e47f0  lea     r12, [rdi+0E98h]
0x1400e47f7  mov     esi, 1
0x1400e47fc  mov     rcx, rdi
0x1400e47ff  call    VsmmDmSlppDisableMemoryBlocks
0x1400e4804  mov     rcx, rdi
0x1400e4807  call    VsmmDmSlpUninitialize
0x1400e480c  test    sil, sil
0x1400e480f  jz      short loc_1400E4820
0x1400e4811  mov     rcx, rdi
0x1400e4814  call    VsmmPartitionUnblockDeviceAttach
0x1400e4819  jmp     short loc_1400E4820
0x1400e481b  mov     ebx, 0C000000Dh
0x1400e4820  mov     rcx, r12
0x1400e4823  call    VidObjectLockRelease
0x1400e4828  mov     eax, ebx
0x1400e482a  mov     rbx, [rsp+80h+arg_8]
0x1400e4832  add     rsp, 80h
0x1400e4839  pop     r15
0x1400e483b  pop     r14
0x1400e483d  pop     r13
0x1400e483f  pop     r12
0x1400e4841  pop     rdi
0x1400e4842  pop     rsi
0x1400e4843  pop     rbp
0x1400e4844  retn
```
