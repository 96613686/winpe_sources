# VsmmEpfSetup

- ea: `0x1400a8ae8`
- end: `0x1400a8d36`
- name: `VsmmEpfSetup`
- size: `590`
- prototype: `__int64 __fastcall(unsigned __int64, char, int, int, __int64, unsigned __int64, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1400a8918`
- `0x1400faac0`

## callees

- `0x140005b14`
- `0x14002534c`
- `0x14002e080`
- `0x140034554`
- `0x140034914`
- `0x1400a8ae8`
- `0x1400a8d3c`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400a8caa`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400a8caa`
- `ntoskrnl!ExAllocatePool2` at `0x1400a8be8`
- `ntoskrnl!ExAllocatePool2` at `0x1400a8be8`

## pseudocode

```c
__int64 __fastcall VsmmEpfSetup(
        unsigned __int64 a1,
        char a2,
        int a3,
        int a4,
        __int64 a5,
        unsigned __int64 a6,
        unsigned __int64 *a7)
{
  unsigned __int64 v8; // rbp
  unsigned __int64 v9; // rsi
  int v10; // ebx
  unsigned int v11; // r14d
  int v12; // ebx
  __int64 Pool2; // rax
  __int64 v14; // rdi
  unsigned int v15; // edx
  __int64 v16; // rcx
  _QWORD *v17; // rcx
  __int64 i; // [rsp+40h] [rbp-48h] BYREF
  _QWORD v20[8]; // [rsp+48h] [rbp-40h] BYREF

  v20[0] = 0;
  i = 0;
  v8 = a1;
  if ( a3 != 1 || a4 )
    return (unsigned int)-1073741811;
  v9 = a6;
  if ( a6 > 1 )
  {
    if ( !a2 )
    {
      v9 = 1;
      goto LABEL_7;
    }
    return (unsigned int)-1073741811;
  }
  if ( !a6 )
    return (unsigned int)-1073741811;
LABEL_7:
  if ( *(_QWORD *)(a1 + 10760) )
  {
    v10 = -1073741811;
  }
  else
  {
    v10 = VsmmGpaRangeLookupByGpn(a1, 0, a5, 24, 0, (__int64)v20, (__int64)&i);
    if ( v10 >= 0 )
    {
      a1 = *(_QWORD *)(i + 272) - v20[0] + 1LL;
      if ( a1 >= v9 )
      {
        v11 = 16 * *(_DWORD *)(v8 + 3200);
        v12 = (*(_BYTE *)(v8 + 24) & 0x20) != 0 ? 0xFF8 : 0;
        Pool2 = ExAllocatePool2(64, v11 * (v12 + 104) + 112, 1833788502);
        v14 = Pool2;
        if ( Pool2 )
        {
          *(_DWORD *)Pool2 = 1;
          v15 = 0;
          *(_DWORD *)(Pool2 + 4) = a4;
          *(_QWORD *)(Pool2 + 8) = ((v9 << 12) - 16) >> 3;
          *(_QWORD *)(Pool2 + 24) = v20[0];
          *(_QWORD *)(Pool2 + 32) = v9;
          *(_QWORD *)(Pool2 + 16) = i;
          for ( i = 0; v15 < v11; *(_QWORD *)(Pool2 + 40) = v17 )
          {
            v16 = v15 * (v12 + 104);
            ++v15;
            v17 = (_QWORD *)(Pool2 + v16 + 112);
            *v17 = *(_QWORD *)(Pool2 + 40);
          }
          v10 = VsmmLockGpaRange(
                  *(_QWORD *)(Pool2 + 16),
                  *(_QWORD *)(Pool2 + 24),
                  *(_QWORD *)(Pool2 + 32),
                  9,
                  Pool2 + 56);
          if ( v10 >= 0 )
          {
            if ( MmMapLockedPagesSpecifyCache((PMDL)(v14 + 56), 0, MmCached, 0, 0, 0x40000010u) )
            {
              VidObjectLockAcquireExclusive(v8 + 10472);
              if ( *(_QWORD *)(v8 + 10760) )
              {
                v10 = -1073741811;
              }
              else
              {
                v10 = 0;
                *(_QWORD *)(v8 + 10760) = v14;
                v14 = 0;
                *a7 = v9;
              }
              VidObjectLockRelease(v8 + 10472);
              if ( !v14 )
                goto LABEL_24;
            }
            else
            {
              v10 = -1073741670;
            }
          }
          VsmmEpfpContextFree(a1, v14);
        }
        else
        {
          v10 = -1073741670;
        }
      }
      else
      {
        v10 = -1073741637;
      }
    }
  }
LABEL_24:
  if ( i )
    VsmmGpaRangeRelease(a1, i, 0);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400a8ae8  push    rbx
0x1400a8aea  push    rbp
0x1400a8aeb  push    rsi
0x1400a8aec  push    rdi
0x1400a8aed  push    r14
0x1400a8aef  push    r15
0x1400a8af1  sub     rsp, 58h
0x1400a8af5  mov     [rsp+88h+var_40], 0
0x1400a8afe  mov     r15d, r9d
0x1400a8b01  mov     [rsp+88h+var_48], 0
0x1400a8b0a  mov     rbp, rcx
0x1400a8b0d  cmp     r8d, 1
0x1400a8b11  jnz     loc_1400A8D21
0x1400a8b17  test    r9d, r9d
0x1400a8b1a  jnz     loc_1400A8D21
0x1400a8b20  mov     rsi, [rsp+88h+arg_28]
0x1400a8b28  cmp     rsi, 1
0x1400a8b2c  jbe     short loc_1400A8B3B
0x1400a8b2e  test    dl, dl
0x1400a8b30  jnz     loc_1400A8D21
0x1400a8b36  mov     esi, r8d
0x1400a8b39  jmp     short loc_1400A8B44
0x1400a8b3b  test    rsi, rsi
0x1400a8b3e  jz      loc_1400A8D21
0x1400a8b44  mov     rax, [rcx+2A08h]
0x1400a8b4b  test    rax, rax
0x1400a8b4e  jz      short loc_1400A8B5A
0x1400a8b50  mov     ebx, 0C000000Dh
0x1400a8b55  jmp     loc_1400A8D0D
0x1400a8b5a  mov     r8, [rsp+88h+arg_20]
0x1400a8b62  lea     rax, [rsp+88h+var_48]
0x1400a8b67  mov     [rsp+88h+var_58], rax
0x1400a8b6c  mov     r9d, 18h
0x1400a8b72  lea     rax, [rsp+88h+var_40]
0x1400a8b77  xor     edx, edx
0x1400a8b79  mov     qword ptr [rsp+88h+Priority], rax
0x1400a8b7e  mov     qword ptr [rsp+88h+BugCheckOnFailure], 0
0x1400a8b87  call    VsmmGpaRangeLookupByGpn
0x1400a8b8c  mov     ebx, eax
0x1400a8b8e  test    eax, eax
0x1400a8b90  js      loc_1400A8D0D
0x1400a8b96  mov     rax, [rsp+88h+var_48]
0x1400a8b9b  mov     rcx, [rax+110h]
0x1400a8ba2  sub     rcx, [rsp+88h+var_40]
0x1400a8ba7  inc     rcx
0x1400a8baa  cmp     rcx, rsi
0x1400a8bad  jnb     short loc_1400A8BB9
0x1400a8baf  mov     ebx, 0C00000BBh
0x1400a8bb4  jmp     loc_1400A8D0D
0x1400a8bb9  mov     al, [rbp+18h]
0x1400a8bbc  mov     ecx, 40h ; '@'
0x1400a8bc1  mov     r14d, [rbp+0C80h]
0x1400a8bc8  and     al, 20h
0x1400a8bca  neg     al
0x1400a8bcc  mov     r8d, 6D4D6456h
0x1400a8bd2  sbb     ebx, ebx
0x1400a8bd4  shl     r14d, 4
0x1400a8bd8  and     ebx, 0FF8h
0x1400a8bde  lea     edx, [rbx+68h]
0x1400a8be1  imul    edx, r14d
0x1400a8be5  add     edx, 70h ; 'p'
0x1400a8be8  call    cs:__imp_ExAllocatePool2
0x1400a8bef  nop     dword ptr [rax+rax+00h]
0x1400a8bf4  mov     rdi, rax
0x1400a8bf7  test    rax, rax
0x1400a8bfa  jnz     short loc_1400A8C06
0x1400a8bfc  mov     ebx, 0C000009Ah
0x1400a8c01  jmp     loc_1400A8D0D
0x1400a8c06  mov     dword ptr [rax], 1
0x1400a8c0c  xor     edx, edx
0x1400a8c0e  mov     [rax+4], r15d
0x1400a8c12  mov     rax, rsi
0x1400a8c15  shl     rax, 0Ch
0x1400a8c19  sub     rax, 10h
0x1400a8c1d  shr     rax, 3
0x1400a8c21  mov     [rdi+8], rax
0x1400a8c25  mov     rax, [rsp+88h+var_40]
0x1400a8c2a  mov     [rdi+18h], rax
0x1400a8c2e  mov     [rdi+20h], rsi
0x1400a8c32  mov     rax, [rsp+88h+var_48]
0x1400a8c37  mov     [rdi+10h], rax
0x1400a8c3b  mov     [rsp+88h+var_48], 0
0x1400a8c44  test    r14d, r14d
0x1400a8c47  jz      short loc_1400A8C68
0x1400a8c49  mov     rax, [rdi+28h]
0x1400a8c4d  lea     ecx, [rbx+68h]
0x1400a8c50  imul    ecx, edx
0x1400a8c53  inc     edx
0x1400a8c55  add     rcx, 70h ; 'p'
0x1400a8c59  add     rcx, rdi
0x1400a8c5c  mov     [rcx], rax
0x1400a8c5f  mov     [rdi+28h], rcx
0x1400a8c63  cmp     edx, r14d
0x1400a8c66  jb      short loc_1400A8C49
0x1400a8c68  mov     r8, [rdi+20h]
0x1400a8c6c  lea     r14, [rdi+38h]
0x1400a8c70  mov     rdx, [rdi+18h]
0x1400a8c74  mov     r9d, 9
0x1400a8c7a  mov     rcx, [rdi+10h]
0x1400a8c7e  mov     qword ptr [rsp+88h+BugCheckOnFailure], r14
0x1400a8c83  call    VsmmLockGpaRange
0x1400a8c88  mov     ebx, eax
0x1400a8c8a  test    eax, eax
0x1400a8c8c  js      short loc_1400A8D05
0x1400a8c8e  xor     r9d, r9d; RequestedAddress
0x1400a8c91  mov     [rsp+88h+Priority], 40000010h; Priority
0x1400a8c99  xor     edx, edx; AccessMode
0x1400a8c9b  mov     [rsp+88h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400a8ca3  mov     rcx, r14; MemoryDescriptorList
0x1400a8ca6  lea     r8d, [r9+1]; CacheType
0x1400a8caa  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400a8cb1  nop     dword ptr [rax+rax+00h]
0x1400a8cb6  test    rax, rax
0x1400a8cb9  jnz     short loc_1400A8CC2
0x1400a8cbb  mov     ebx, 0C000009Ah
0x1400a8cc0  jmp     short loc_1400A8D05
0x1400a8cc2  lea     r14, [rbp+28E8h]
0x1400a8cc9  mov     rcx, r14
0x1400a8ccc  call    VidObjectLockAcquireExclusive
0x1400a8cd1  cmp     qword ptr [rbp+2A08h], 0
0x1400a8cd9  jz      short loc_1400A8CE2
0x1400a8cdb  mov     ebx, 0C000000Dh
0x1400a8ce0  jmp     short loc_1400A8CF8
0x1400a8ce2  mov     rax, [rsp+88h+arg_30]
0x1400a8cea  xor     ebx, ebx
0x1400a8cec  mov     [rbp+2A08h], rdi
0x1400a8cf3  xor     edi, edi
0x1400a8cf5  mov     [rax], rsi
0x1400a8cf8  mov     rcx, r14
0x1400a8cfb  call    VidObjectLockRelease
0x1400a8d00  test    rdi, rdi
0x1400a8d03  jz      short loc_1400A8D0D
0x1400a8d05  mov     rdx, rdi
0x1400a8d08  call    VsmmEpfpContextFree
0x1400a8d0d  mov     rdx, [rsp+88h+var_48]
0x1400a8d12  test    rdx, rdx
0x1400a8d15  jz      short loc_1400A8D26
0x1400a8d17  xor     r8d, r8d
0x1400a8d1a  call    VsmmGpaRangeRelease
0x1400a8d1f  jmp     short loc_1400A8D26
0x1400a8d21  mov     ebx, 0C000000Dh
0x1400a8d26  mov     eax, ebx
0x1400a8d28  add     rsp, 58h
0x1400a8d2c  pop     r15
0x1400a8d2e  pop     r14
0x1400a8d30  pop     rdi
0x1400a8d31  pop     rsi
0x1400a8d32  pop     rbp
0x1400a8d33  pop     rbx
0x1400a8d34  retn
```
