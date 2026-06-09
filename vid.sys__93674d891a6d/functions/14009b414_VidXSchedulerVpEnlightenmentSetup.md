# VidXSchedulerVpEnlightenmentSetup

- ea: `0x14009b414`
- end: `0x14009b5fa`
- name: `VidXSchedulerVpEnlightenmentSetup`
- size: `486`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x1400863e0`
- `0x14009afbc`

## callees

- `0x14000f8d4`
- `0x14001380c`
- `0x140021c60`
- `0x1400347a4`
- `0x140034b64`
- `0x14009b414`
- `0x14009b600`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14009b545`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14009b545`
- `ntoskrnl!ExAllocatePool2` at `0x14009b4b8`
- `ntoskrnl!ExAllocatePool2` at `0x14009b4b8`
- `winhvr!WinHvConfigureSchedulerAssistNotifications` at `0x14009b5b7`
- `winhvr!WinHvConfigureSchedulerAssistNotifications` at `0x14009b5b7`
- `winhvr!WinHvSetSchedulerAssistData` at `0x14009b597`
- `winhvr!WinHvSetSchedulerAssistData` at `0x14009b597`

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
0x14009b414  push    rbx
0x14009b416  push    rbp
0x14009b417  push    rsi
0x14009b418  push    rdi
0x14009b419  push    r14
0x14009b41b  push    r15
0x14009b41d  sub     rsp, 58h
0x14009b421  mov     rax, cs:__security_cookie
0x14009b428  xor     rax, rsp
0x14009b42b  mov     [rsp+88h+var_48], rax
0x14009b430  xorps   xmm0, xmm0
0x14009b433  mov     rbx, r9
0x14009b436  mov     r14, rcx
0x14009b439  movups  [rsp+88h+var_58], xmm0
0x14009b43e  cmp     edx, 5
0x14009b441  jz      short loc_14009B44D
0x14009b443  mov     ebx, 0C000000Dh
0x14009b448  jmp     loc_14009B5DD
0x14009b44d  mov     rsi, [rcx+180h]
0x14009b454  test    rsi, rsi
0x14009b457  jz      short loc_14009B443
0x14009b459  test    r8d, r8d
0x14009b45c  jnz     short loc_14009B471
0x14009b45e  test    rbx, rbx
0x14009b461  jnz     short loc_14009B443
0x14009b463  mov     rax, [rsi+28h]
0x14009b467  test    rax, rax
0x14009b46a  jnz     short loc_14009B443
0x14009b46c  jmp     loc_14009B5DD
0x14009b471  cmp     r8d, 1
0x14009b475  jnz     short loc_14009B443
0x14009b477  mov     eax, ebx
0x14009b479  mov     r15d, 0FFFh
0x14009b47f  and     rax, r15
0x14009b482  add     rax, 107Fh
0x14009b488  and     rax, 0FFFFFFFFFFFFF000h
0x14009b48e  cmp     rax, 1000h
0x14009b494  jbe     short loc_14009B4A0
0x14009b496  mov     ebx, 0C00000BBh
0x14009b49b  jmp     loc_14009B5DD
0x14009b4a0  mov     rax, [rsi+28h]
0x14009b4a4  mov     rbp, [rcx]
0x14009b4a7  test    rax, rax
0x14009b4aa  jnz     short loc_14009B443
0x14009b4ac  lea     edx, [rax+48h]
0x14009b4af  mov     r8d, 72446456h
0x14009b4b5  lea     ecx, [rax+40h]
0x14009b4b8  call    cs:__imp_ExAllocatePool2
0x14009b4bf  nop     dword ptr [rax+rax+00h]
0x14009b4c4  mov     rdi, rax
0x14009b4c7  test    rax, rax
0x14009b4ca  jnz     short loc_14009B4D6
0x14009b4cc  mov     ebx, 0C000009Ah
0x14009b4d1  jmp     loc_14009B5DD
0x14009b4d6  mov     dword ptr [rax], 1
0x14009b4dc  lea     r9, [rdi+10h]
0x14009b4e0  mov     [rax+8], rbx
0x14009b4e4  lea     rdx, [rsp+88h+var_58]
0x14009b4e9  xorps   xmm0, xmm0
0x14009b4ec  mov     r8d, 4
0x14009b4f2  movups  [rsp+88h+var_58], xmm0
0x14009b4f7  mov     dword ptr [rsp+88h+var_58], 80h
0x14009b4ff  mov     rcx, rbp
0x14009b502  mov     eax, [rax+8]
0x14009b505  and     eax, r15d
0x14009b508  mov     dword ptr [rsp+88h+var_58+4], eax
0x14009b50c  mov     rax, [rdi+8]
0x14009b510  shr     rax, 0Ch
0x14009b514  mov     qword ptr [rsp+88h+var_58+8], rax
0x14009b519  call    VidKmIfSingleGpaLockAcquireSync
0x14009b51e  mov     ebx, eax
0x14009b520  test    eax, eax
0x14009b522  js      loc_14009B5D2
0x14009b528  xor     r9d, r9d; RequestedAddress
0x14009b52b  mov     [rsp+88h+Priority], 40000010h; Priority
0x14009b533  xor     edx, edx; AccessMode
0x14009b535  mov     [rsp+88h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14009b53d  lea     rcx, [rdi+10h]; MemoryDescriptorList
0x14009b541  lea     r8d, [r9+1]; CacheType
0x14009b545  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14009b54c  nop     dword ptr [rax+rax+00h]
0x14009b551  test    rax, rax
0x14009b554  jnz     short loc_14009B55D
0x14009b556  mov     ebx, 0C000009Ah
0x14009b55b  jmp     short loc_14009B5D2
0x14009b55d  mov     rcx, rbp
0x14009b560  call    VidObjectLockAcquireExclusive
0x14009b565  cmp     qword ptr [rsi+28h], 0
0x14009b56a  jz      short loc_14009B573
0x14009b56c  mov     ebx, 0C000000Dh
0x14009b571  jmp     short loc_14009B5C5
0x14009b573  mov     [rsi+28h], rdi
0x14009b577  mov     rcx, r14
0x14009b57a  xor     edi, edi
0x14009b57c  call    VidXSchedulerpSetThreadSchedulerAssist
0x14009b581  mov     r8, [rsi+28h]
0x14009b585  mov     rcx, [r14]
0x14009b588  mov     edx, [r14+8]
0x14009b58c  mov     r8, [r8+28h]
0x14009b590  mov     rcx, [rcx+288h]
0x14009b597  call    cs:__imp_WinHvSetSchedulerAssistData
0x14009b59e  nop     dword ptr [rax+rax+00h]
0x14009b5a3  mov     rcx, [r14]
0x14009b5a6  mov     r9, rsi
0x14009b5a9  mov     edx, [r14+8]
0x14009b5ad  mov     r8b, 1
0x14009b5b0  mov     rcx, [rcx+288h]
0x14009b5b7  call    cs:__imp_WinHvConfigureSchedulerAssistNotifications
0x14009b5be  nop     dword ptr [rax+rax+00h]
0x14009b5c3  xor     ebx, ebx
0x14009b5c5  mov     rcx, rbp
0x14009b5c8  call    VidObjectLockRelease
0x14009b5cd  test    rdi, rdi
0x14009b5d0  jz      short loc_14009B5DD
0x14009b5d2  mov     rdx, rdi
0x14009b5d5  mov     rcx, rbp
0x14009b5d8  call    VidXSchedulerpVpAssistContextTeardown
0x14009b5dd  mov     eax, ebx
0x14009b5df  mov     rcx, [rsp+88h+var_48]
0x14009b5e4  xor     rcx, rsp; StackCookie
0x14009b5e7  call    __security_check_cookie
0x14009b5ec  add     rsp, 58h
0x14009b5f0  pop     r15
0x14009b5f2  pop     r14
0x14009b5f4  pop     rdi
0x14009b5f5  pop     rsi
0x14009b5f6  pop     rbp
0x14009b5f7  pop     rbx
0x14009b5f8  retn
```
