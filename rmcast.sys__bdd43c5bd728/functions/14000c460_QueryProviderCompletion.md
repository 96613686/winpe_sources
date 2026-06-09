# QueryProviderCompletion

- ea: `0x14000c460`
- end: `0x14000c578`
- name: `QueryProviderCompletion`
- size: `280`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140005168`
- `0x1400051c8`
- `0x14000c460`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000c49c`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000c49c`

## pseudocode

```c
__int64 __fastcall QueryProviderCompletion(__int64 a1, __int64 a2)
{
  _DWORD *v2; // r8
  __int64 v4; // rcx
  unsigned int v5; // ecx
  unsigned int v6; // r10d

  v2 = 0;
  if ( *(int *)(a2 + 48) >= 0
    && ((v4 = *(_QWORD *)(a2 + 8), (*(_BYTE *)(v4 + 10) & 5) == 0)
      ? (v2 = MmMapLockedPagesSpecifyCache((PMDL)v4, 0, MmCached, 0, 0, 0x40000020u))
      : (v2 = *(_DWORD **)(v4 + 24)),
        v2) )
  {
    v5 = v2[3];
    v2[4] = 76873;
    v2[1] = 0x7FFFFFFF;
    v2[5] = 1;
    v6 = v5 - 68;
    if ( v5 <= 0x44 )
      v6 = 0;
    v2[3] = v6;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
      WPP_SF_DDd(
        WPP_GLOBAL_Control->AttachedDevice,
        13,
        WPP_ce4514d7ab2e3ec50b48eb708a42494e_Traceguids,
        76873,
        0x7FFFFFFF,
        v6);
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
  {
    WPP_SF_dq(
      WPP_GLOBAL_Control->AttachedDevice,
      14,
      WPP_ce4514d7ab2e3ec50b48eb708a42494e_Traceguids,
      *(unsigned int *)(a2 + 48),
      v2);
  }
  if ( !*(_BYTE *)(a2 + 65) )
    return 3221225494LL;
  *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
  return 259;
}

```

## disassembly

```asm
0x14000c460  push    rbx
0x14000c462  sub     rsp, 30h
0x14000c466  xor     r8d, r8d
0x14000c469  mov     rbx, rdx
0x14000c46c  cmp     [rdx+30h], r8d
0x14000c470  jl      loc_14000C51C
0x14000c476  mov     rcx, [rdx+8]; MemoryDescriptorList
0x14000c47a  test    byte ptr [rcx+0Ah], 5
0x14000c47e  jz      short loc_14000C486
0x14000c480  mov     r8, [rcx+18h]
0x14000c484  jmp     short loc_14000C4AB
0x14000c486  xor     r9d, r9d; RequestedAddress
0x14000c489  mov     [rsp+38h+Priority], 40000020h; Priority
0x14000c491  mov     [rsp+38h+BugCheckOnFailure], r8d; BugCheckOnFailure
0x14000c496  xor     edx, edx; AccessMode
0x14000c498  lea     r8d, [r9+1]; CacheType
0x14000c49c  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000c4a3  nop     dword ptr [rax+rax+00h]
0x14000c4a8  mov     r8, rax
0x14000c4ab  test    r8, r8
0x14000c4ae  jz      short loc_14000C51C
0x14000c4b0  mov     ecx, [r8+0Ch]
0x14000c4b4  mov     r9d, 12C49h
0x14000c4ba  mov     r11d, 7FFFFFFFh
0x14000c4c0  mov     [r8+10h], r9d
0x14000c4c4  mov     [r8+4], r11d
0x14000c4c8  mov     dword ptr [r8+14h], 1
0x14000c4d0  xor     eax, eax
0x14000c4d2  lea     r10d, [rcx-44h]
0x14000c4d6  cmp     ecx, 44h ; 'D'
0x14000c4d9  cmovbe  r10d, eax
0x14000c4dd  lea     rax, WPP_GLOBAL_Control
0x14000c4e4  mov     [r8+0Ch], r10d
0x14000c4e8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c4ef  cmp     rcx, rax
0x14000c4f2  jz      short loc_14000C554
0x14000c4f4  mov     eax, [rcx+2Ch]
0x14000c4f7  test    al, 10h
0x14000c4f9  jz      short loc_14000C554
0x14000c4fb  mov     rcx, [rcx+18h]
0x14000c4ff  lea     r8, WPP_ce4514d7ab2e3ec50b48eb708a42494e_Traceguids
0x14000c506  mov     [rsp+38h+Priority], r10d
0x14000c50b  mov     edx, 0Dh
0x14000c510  mov     [rsp+38h+BugCheckOnFailure], r11d
0x14000c515  call    WPP_SF_DDd
0x14000c51a  jmp     short loc_14000C554
0x14000c51c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c523  lea     rax, WPP_GLOBAL_Control
0x14000c52a  cmp     rcx, rax
0x14000c52d  jz      short loc_14000C554
0x14000c52f  mov     eax, [rcx+2Ch]
0x14000c532  test    al, 2
0x14000c534  jz      short loc_14000C554
0x14000c536  mov     r9d, [rbx+30h]
0x14000c53a  mov     edx, 0Eh
0x14000c53f  mov     rcx, [rcx+18h]
0x14000c543  mov     qword ptr [rsp+38h+BugCheckOnFailure], r8
0x14000c548  lea     r8, WPP_ce4514d7ab2e3ec50b48eb708a42494e_Traceguids
0x14000c54f  call    WPP_SF_dq
0x14000c554  cmp     byte ptr [rbx+41h], 0
0x14000c558  jz      short loc_14000C56C
0x14000c55a  mov     rax, [rbx+0B8h]
0x14000c561  or      byte ptr [rax+3], 1
0x14000c565  mov     eax, 103h
0x14000c56a  jmp     short loc_14000C571
0x14000c56c  mov     eax, 0C0000016h
0x14000c571  add     rsp, 30h
0x14000c575  pop     rbx
0x14000c576  retn
```
