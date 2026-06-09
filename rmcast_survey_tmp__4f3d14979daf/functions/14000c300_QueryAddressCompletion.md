# QueryAddressCompletion

- ea: `0x14000c300`
- end: `0x14000c450`
- name: `QueryAddressCompletion`
- size: `336`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1400050ac`
- `0x1400051c8`
- `0x1400052e4`
- `0x14000c300`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000c351`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000c351`

## pseudocode

```c
__int64 __fastcall QueryAddressCompletion(__int64 a1, __int64 a2)
{
  unsigned __int16 *v2; // rbx
  __int64 v4; // rdi
  __int64 v5; // rcx
  int v6; // eax
  ULONG BugCheckOnFailure[2]; // [rsp+20h] [rbp-18h]

  v2 = 0;
  if ( *(int *)(a2 + 48) >= 0
    && ((v4 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 184) + 48LL) + 24LL),
         v5 = *(_QWORD *)(a2 + 8),
         (*(_BYTE *)(v5 + 10) & 5) == 0)
      ? (v2 = (unsigned __int16 *)MmMapLockedPagesSpecifyCache((PMDL)v5, 0, MmCached, 0, 0, 0x40000020u))
      : (v2 = *(unsigned __int16 **)(v5 + 24)),
        v2) )
  {
    if ( v4 && ((v6 = *(_DWORD *)(v4 + 16), v6 == 810763603) || v6 == 1397966163 || v6 == 1381188947) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
      {
        BugCheckOnFailure[0] = v2[6];
        WPP_SF_Dd(
          (__int64)WPP_GLOBAL_Control->AttachedDevice,
          0xAu,
          (__int64)WPP_ce4514d7ab2e3ec50b48eb708a42494e_Traceguids,
          *(_DWORD *)(v2 + 7),
          *(_QWORD *)BugCheckOnFailure);
      }
      *(_DWORD *)(v4 + 56) = *(_DWORD *)(v2 + 7);
      *(_WORD *)(v4 + 60) = v2[6];
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_ce4514d7ab2e3ec50b48eb708a42494e_Traceguids, v4);
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
  {
    WPP_SF_dq(
      WPP_GLOBAL_Control->AttachedDevice,
      12,
      WPP_ce4514d7ab2e3ec50b48eb708a42494e_Traceguids,
      *(unsigned int *)(a2 + 48),
      v2);
  }
  return 0;
}

```

## disassembly

```asm
0x14000c300  mov     [rsp+arg_0], rbx
0x14000c305  mov     [rsp+arg_8], rsi
0x14000c30a  push    rdi
0x14000c30b  sub     rsp, 30h
0x14000c30f  xor     ebx, ebx
0x14000c311  mov     rsi, rdx
0x14000c314  cmp     [rdx+30h], ebx
0x14000c317  jl      loc_14000C405
0x14000c31d  mov     rax, [rdx+0B8h]
0x14000c324  mov     rcx, [rax+30h]
0x14000c328  mov     rdi, [rcx+18h]
0x14000c32c  mov     rcx, [rdx+8]; MemoryDescriptorList
0x14000c330  test    byte ptr [rcx+0Ah], 5
0x14000c334  jz      short loc_14000C33C
0x14000c336  mov     rbx, [rcx+18h]
0x14000c33a  jmp     short loc_14000C360
0x14000c33c  xor     r9d, r9d; RequestedAddress
0x14000c33f  mov     [rsp+38h+Priority], 40000020h; Priority
0x14000c347  xor     edx, edx; AccessMode
0x14000c349  mov     [rsp+38h+BugCheckOnFailure], ebx; BugCheckOnFailure
0x14000c34d  lea     r8d, [r9+1]; CacheType
0x14000c351  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000c358  nop     dword ptr [rax+rax+00h]
0x14000c35d  mov     rbx, rax
0x14000c360  test    rbx, rbx
0x14000c363  jz      loc_14000C405
0x14000c369  test    rdi, rdi
0x14000c36c  jz      short loc_14000C3D1
0x14000c36e  mov     eax, [rdi+10h]
0x14000c371  cmp     eax, 30534553h
0x14000c376  jz      short loc_14000C386
0x14000c378  cmp     eax, 53534553h
0x14000c37d  jz      short loc_14000C386
0x14000c37f  cmp     eax, 52534553h
0x14000c384  jnz     short loc_14000C3D1
0x14000c386  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c38d  lea     rax, WPP_GLOBAL_Control
0x14000c394  cmp     rcx, rax
0x14000c397  jz      short loc_14000C3C1
0x14000c399  mov     eax, [rcx+2Ch]
0x14000c39c  test    al, 10h
0x14000c39e  jz      short loc_14000C3C1
0x14000c3a0  movzx   eax, word ptr [rbx+0Ch]
0x14000c3a4  lea     r8, WPP_ce4514d7ab2e3ec50b48eb708a42494e_Traceguids
0x14000c3ab  mov     r9d, [rbx+0Eh]
0x14000c3af  mov     edx, 0Ah
0x14000c3b4  mov     rcx, [rcx+18h]
0x14000c3b8  mov     [rsp+38h+BugCheckOnFailure], eax
0x14000c3bc  call    WPP_SF_Dd
0x14000c3c1  mov     eax, [rbx+0Eh]
0x14000c3c4  mov     [rdi+38h], eax
0x14000c3c7  movzx   eax, word ptr [rbx+0Ch]
0x14000c3cb  mov     [rdi+3Ch], ax
0x14000c3cf  jmp     short loc_14000C43D
0x14000c3d1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c3d8  lea     rax, WPP_GLOBAL_Control
0x14000c3df  cmp     rcx, rax
0x14000c3e2  jz      short loc_14000C43D
0x14000c3e4  mov     eax, [rcx+2Ch]
0x14000c3e7  test    al, 2
0x14000c3e9  jz      short loc_14000C43D
0x14000c3eb  mov     rcx, [rcx+18h]
0x14000c3ef  lea     r8, WPP_ce4514d7ab2e3ec50b48eb708a42494e_Traceguids
0x14000c3f6  mov     edx, 0Bh
0x14000c3fb  mov     r9, rdi
0x14000c3fe  call    WPP_SF_q
0x14000c403  jmp     short loc_14000C43D
0x14000c405  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c40c  lea     rax, WPP_GLOBAL_Control
0x14000c413  cmp     rcx, rax
0x14000c416  jz      short loc_14000C43D
0x14000c418  mov     eax, [rcx+2Ch]
0x14000c41b  test    al, 2
0x14000c41d  jz      short loc_14000C43D
0x14000c41f  mov     r9d, [rsi+30h]
0x14000c423  lea     r8, WPP_ce4514d7ab2e3ec50b48eb708a42494e_Traceguids
0x14000c42a  mov     rcx, [rcx+18h]
0x14000c42e  mov     edx, 0Ch
0x14000c433  mov     qword ptr [rsp+38h+BugCheckOnFailure], rbx
0x14000c438  call    WPP_SF_dq
0x14000c43d  mov     rbx, [rsp+38h+arg_0]
0x14000c442  xor     eax, eax
0x14000c444  mov     rsi, [rsp+38h+arg_8]
0x14000c449  add     rsp, 30h
0x14000c44d  pop     rdi
0x14000c44e  retn
```
