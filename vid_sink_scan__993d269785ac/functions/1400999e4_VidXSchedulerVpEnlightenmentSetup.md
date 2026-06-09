# VidXSchedulerVpEnlightenmentSetup

- ea: `0x1400999e4`
- end: `0x140099bca`
- name: `VidXSchedulerVpEnlightenmentSetup`
- size: `486`
- prototype: `__int64 __fastcall(__int64 *, int, int, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x140085260`
- `0x14009958c`

## callees

- `0x14000fa84`
- `0x1400139bc`
- `0x140021650`
- `0x140034554`
- `0x140034914`
- `0x1400999e4`
- `0x140099bd0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140099b15`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140099b15`
- `ntoskrnl!ExAllocatePool2` at `0x140099a88`
- `ntoskrnl!ExAllocatePool2` at `0x140099a88`
- `winhvr!WinHvSetSchedulerAssistData` at `0x140099b67`
- `winhvr!WinHvSetSchedulerAssistData` at `0x140099b67`
- `winhvr!WinHvConfigureSchedulerAssistNotifications` at `0x140099b87`
- `winhvr!WinHvConfigureSchedulerAssistNotifications` at `0x140099b87`

## pseudocode

```c
__int64 __fastcall VidXSchedulerVpEnlightenmentSetup(__int64 *a1, int a2, int a3, __int64 a4)
{
  __int64 v4; // rbx
  __int64 v6; // rsi
  __int64 v7; // rbp
  __int64 Pool2; // rax
  __int64 v9; // rdi
  __int64 v10; // r8
  __int128 v12; // [rsp+30h] [rbp-58h] BYREF

  v4 = a4;
  v12 = 0;
  if ( a2 != 5 )
    goto LABEL_2;
  v6 = a1[48];
  if ( !v6 )
    goto LABEL_2;
  if ( !a3 )
  {
    if ( !a4 && !*(_QWORD *)(v6 + 40) )
      return (unsigned int)v4;
LABEL_2:
    LODWORD(v4) = -1073741811;
    return (unsigned int)v4;
  }
  if ( a3 != 1 )
    goto LABEL_2;
  if ( (((a4 & 0xFFF) + 4223) & 0xFFFFFFFFFFFFF000uLL) > 0x1000 )
  {
    LODWORD(v4) = -1073741637;
    return (unsigned int)v4;
  }
  v7 = *a1;
  if ( *(_QWORD *)(v6 + 40) )
    goto LABEL_2;
  Pool2 = ExAllocatePool2(64, 72, 1917084758);
  v9 = Pool2;
  if ( !Pool2 )
  {
    LODWORD(v4) = -1073741670;
    return (unsigned int)v4;
  }
  *(_DWORD *)Pool2 = 1;
  *(_QWORD *)(Pool2 + 8) = v4;
  v12 = 0;
  LODWORD(v12) = 128;
  DWORD1(v12) = *(_DWORD *)(Pool2 + 8) & 0xFFF;
  *((_QWORD *)&v12 + 1) = *(_QWORD *)(Pool2 + 8) >> 12;
  LODWORD(v4) = VidKmIfSingleGpaLockAcquireSync(v7, &v12, 4, Pool2 + 16);
  if ( (int)v4 < 0 )
  {
LABEL_21:
    VidXSchedulerpVpAssistContextTeardown(v7, v9);
    return (unsigned int)v4;
  }
  if ( !MmMapLockedPagesSpecifyCache((PMDL)(v9 + 16), 0, MmCached, 0, 0, 0x40000010u) )
  {
    LODWORD(v4) = -1073741670;
    goto LABEL_21;
  }
  VidObjectLockAcquireExclusive(v7);
  if ( *(_QWORD *)(v6 + 40) )
  {
    LODWORD(v4) = -1073741811;
  }
  else
  {
    *(_QWORD *)(v6 + 40) = v9;
    v9 = 0;
    VidXSchedulerpSetThreadSchedulerAssist(a1);
    WinHvSetSchedulerAssistData(
      *(_QWORD *)(*a1 + 648),
      *((unsigned int *)a1 + 2),
      *(_QWORD *)(*(_QWORD *)(v6 + 40) + 40LL));
    LOBYTE(v10) = 1;
    WinHvConfigureSchedulerAssistNotifications(*(_QWORD *)(*a1 + 648), *((unsigned int *)a1 + 2), v10, v6);
    LODWORD(v4) = 0;
  }
  VidObjectLockRelease(v7);
  if ( v9 )
    goto LABEL_21;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400999e4  push    rbx
0x1400999e6  push    rbp
0x1400999e7  push    rsi
0x1400999e8  push    rdi
0x1400999e9  push    r14
0x1400999eb  push    r15
0x1400999ed  sub     rsp, 58h
0x1400999f1  mov     rax, cs:__security_cookie
0x1400999f8  xor     rax, rsp
0x1400999fb  mov     [rsp+88h+var_48], rax
0x140099a00  xorps   xmm0, xmm0
0x140099a03  mov     rbx, r9
0x140099a06  mov     r14, rcx
0x140099a09  movups  [rsp+88h+var_58], xmm0
0x140099a0e  cmp     edx, 5
0x140099a11  jz      short loc_140099A1D
0x140099a13  mov     ebx, 0C000000Dh
0x140099a18  jmp     loc_140099BAD
0x140099a1d  mov     rsi, [rcx+180h]
0x140099a24  test    rsi, rsi
0x140099a27  jz      short loc_140099A13
0x140099a29  test    r8d, r8d
0x140099a2c  jnz     short loc_140099A41
0x140099a2e  test    rbx, rbx
0x140099a31  jnz     short loc_140099A13
0x140099a33  mov     rax, [rsi+28h]
0x140099a37  test    rax, rax
0x140099a3a  jnz     short loc_140099A13
0x140099a3c  jmp     loc_140099BAD
0x140099a41  cmp     r8d, 1
0x140099a45  jnz     short loc_140099A13
0x140099a47  mov     eax, ebx
0x140099a49  mov     r15d, 0FFFh
0x140099a4f  and     rax, r15
0x140099a52  add     rax, 107Fh
0x140099a58  and     rax, 0FFFFFFFFFFFFF000h
0x140099a5e  cmp     rax, 1000h
0x140099a64  jbe     short loc_140099A70
0x140099a66  mov     ebx, 0C00000BBh
0x140099a6b  jmp     loc_140099BAD
0x140099a70  mov     rax, [rsi+28h]
0x140099a74  mov     rbp, [rcx]
0x140099a77  test    rax, rax
0x140099a7a  jnz     short loc_140099A13
0x140099a7c  lea     edx, [rax+48h]
0x140099a7f  mov     r8d, 72446456h
0x140099a85  lea     ecx, [rax+40h]
0x140099a88  call    cs:__imp_ExAllocatePool2
0x140099a8f  nop     dword ptr [rax+rax+00h]
0x140099a94  mov     rdi, rax
0x140099a97  test    rax, rax
0x140099a9a  jnz     short loc_140099AA6
0x140099a9c  mov     ebx, 0C000009Ah
0x140099aa1  jmp     loc_140099BAD
0x140099aa6  mov     dword ptr [rax], 1
0x140099aac  lea     r9, [rdi+10h]
0x140099ab0  mov     [rax+8], rbx
0x140099ab4  lea     rdx, [rsp+88h+var_58]
0x140099ab9  xorps   xmm0, xmm0
0x140099abc  mov     r8d, 4
0x140099ac2  movups  [rsp+88h+var_58], xmm0
0x140099ac7  mov     dword ptr [rsp+88h+var_58], 80h
0x140099acf  mov     rcx, rbp
0x140099ad2  mov     eax, [rax+8]
0x140099ad5  and     eax, r15d
0x140099ad8  mov     dword ptr [rsp+88h+var_58+4], eax
0x140099adc  mov     rax, [rdi+8]
0x140099ae0  shr     rax, 0Ch
0x140099ae4  mov     qword ptr [rsp+88h+var_58+8], rax
0x140099ae9  call    VidKmIfSingleGpaLockAcquireSync
0x140099aee  mov     ebx, eax
0x140099af0  test    eax, eax
0x140099af2  js      loc_140099BA2
0x140099af8  xor     r9d, r9d; RequestedAddress
0x140099afb  mov     [rsp+88h+Priority], 40000010h; Priority
0x140099b03  xor     edx, edx; AccessMode
0x140099b05  mov     [rsp+88h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140099b0d  lea     rcx, [rdi+10h]; MemoryDescriptorList
0x140099b11  lea     r8d, [r9+1]; CacheType
0x140099b15  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140099b1c  nop     dword ptr [rax+rax+00h]
0x140099b21  test    rax, rax
0x140099b24  jnz     short loc_140099B2D
0x140099b26  mov     ebx, 0C000009Ah
0x140099b2b  jmp     short loc_140099BA2
0x140099b2d  mov     rcx, rbp
0x140099b30  call    VidObjectLockAcquireExclusive
0x140099b35  cmp     qword ptr [rsi+28h], 0
0x140099b3a  jz      short loc_140099B43
0x140099b3c  mov     ebx, 0C000000Dh
0x140099b41  jmp     short loc_140099B95
0x140099b43  mov     [rsi+28h], rdi
0x140099b47  mov     rcx, r14
0x140099b4a  xor     edi, edi
0x140099b4c  call    VidXSchedulerpSetThreadSchedulerAssist
0x140099b51  mov     r8, [rsi+28h]
0x140099b55  mov     rcx, [r14]
0x140099b58  mov     edx, [r14+8]
0x140099b5c  mov     r8, [r8+28h]
0x140099b60  mov     rcx, [rcx+288h]
0x140099b67  call    cs:__imp_WinHvSetSchedulerAssistData
0x140099b6e  nop     dword ptr [rax+rax+00h]
0x140099b73  mov     rcx, [r14]
0x140099b76  mov     r9, rsi
0x140099b79  mov     edx, [r14+8]
0x140099b7d  mov     r8b, 1
0x140099b80  mov     rcx, [rcx+288h]
0x140099b87  call    cs:__imp_WinHvConfigureSchedulerAssistNotifications
0x140099b8e  nop     dword ptr [rax+rax+00h]
0x140099b93  xor     ebx, ebx
0x140099b95  mov     rcx, rbp
0x140099b98  call    VidObjectLockRelease
0x140099b9d  test    rdi, rdi
0x140099ba0  jz      short loc_140099BAD
0x140099ba2  mov     rdx, rdi
0x140099ba5  mov     rcx, rbp
0x140099ba8  call    VidXSchedulerpVpAssistContextTeardown
0x140099bad  mov     eax, ebx
0x140099baf  mov     rcx, [rsp+88h+var_48]
0x140099bb4  xor     rcx, rsp; StackCookie
0x140099bb7  call    __security_check_cookie
0x140099bbc  add     rsp, 58h
0x140099bc0  pop     r15
0x140099bc2  pop     r14
0x140099bc4  pop     rdi
0x140099bc5  pop     rsi
0x140099bc6  pop     rbp
0x140099bc7  pop     rbx
0x140099bc8  retn
```
