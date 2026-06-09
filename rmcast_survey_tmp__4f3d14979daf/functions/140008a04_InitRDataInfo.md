# InitRDataInfo

- ea: `0x140008a04`
- end: `0x140008c10`
- name: `InitRDataInfo`
- size: `524`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140036d5c`

## callees

- `0x140005038`
- `0x1400052e4`
- `0x140008a04`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140008b94`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140008b94`
- `ntoskrnl!ExAllocatePool2` at `0x140008a71`
- `ntoskrnl!ExAllocatePool2` at `0x140008af4`
- `ntoskrnl!ExAllocatePool2` at `0x140008a71`
- `ntoskrnl!ExAllocatePool2` at `0x140008af4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008b3a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008b3a`

## pseudocode

```c
__int64 __fastcall InitRDataInfo(__int64 a1, __int64 a2)
{
  __int64 v2; // rsi
  __int64 Pool2; // rax
  __int64 v7; // rbx
  __int64 v8; // rbp
  unsigned int v9; // ecx
  unsigned __int64 v10; // rax
  unsigned int i; // edx
  unsigned int v12; // ecx
  unsigned __int16 v13; // dx
  __int64 v14; // rcx
  _QWORD *v15; // rcx

  v2 = *(_QWORD *)(a2 + 40);
  if ( *(_QWORD *)(v2 + 264) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_418d3fcde53e33810bba05463ad55e60_Traceguids, a2);
    return 3221225473LL;
  }
  Pool2 = ExAllocatePool2(64, 448, 1399678800);
  v7 = Pool2;
  if ( !Pool2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_418d3fcde53e33810bba05463ad55e60_Traceguids);
    return 3221225626LL;
  }
  *(_QWORD *)(Pool2 + 8) = Pool2;
  *(_QWORD *)Pool2 = Pool2;
  *(_DWORD *)(Pool2 + 40) = 0x8000;
  *(_DWORD *)(Pool2 + 44) = 0x7FFF;
  *(_DWORD *)(Pool2 + 48) = *((unsigned __int8 *)gFECLog2 + *(unsigned __int8 *)(a2 + 160));
  v8 = ExAllocatePool2(64, 0x80000, 1936549712);
  if ( !v8 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_418d3fcde53e33810bba05463ad55e60_Traceguids);
    ExFreePoolWithTag((PVOID)v7, 0);
    return 3221225626LL;
  }
  v9 = 8 * *(unsigned __int8 *)(a2 + 160) + 112;
  *(_DWORD *)(v7 + 16) = v9;
  ExInitializeNPagedLookasideList(
    (PNPAGED_LOOKASIDE_LIST)(v7 + 64),
    0,
    0,
    0x200u,
    v9,
    0x526D6750u,
    (*(_DWORD *)(a1 + 56) & 0x10) != 0 ? 2000 : 1000);
  v10 = *(_QWORD *)(v2 + 96);
  for ( i = 0; v10; v10 >>= 1 )
    ++i;
  v12 = 0;
  *(_DWORD *)(v7 + 28) = 32;
  *(_DWORD *)(v7 + 24) = 31;
  if ( i >= 5 )
    v12 = i - 5;
  v13 = 0;
  *(_DWORD *)(v7 + 20) = v12;
  for ( *(_QWORD *)(v7 + 56) = v8; (unsigned int)v13 < *(_DWORD *)(v7 + 40); *v15 = v15 )
  {
    v14 = v13++;
    v15 = (_QWORD *)(v8 + 16 * v14);
    v15[1] = v15;
  }
  *(_QWORD *)(v2 + 264) = v7;
  return 0;
}

```

## disassembly

```asm
0x140008a04  push    rbx
0x140008a06  push    rbp
0x140008a07  push    rsi
0x140008a08  push    rdi
0x140008a09  push    r14
0x140008a0b  sub     rsp, 40h
0x140008a0f  mov     rsi, [rdx+28h]
0x140008a13  mov     rdi, rdx
0x140008a16  mov     r14, rcx
0x140008a19  cmp     qword ptr [rsi+108h], 0
0x140008a21  jz      short loc_140008A5F
0x140008a23  mov     rcx, cs:WPP_GLOBAL_Control
0x140008a2a  lea     rax, WPP_GLOBAL_Control
0x140008a31  cmp     rcx, rax
0x140008a34  jz      short loc_140008A55
0x140008a36  mov     eax, [rcx+2Ch]
0x140008a39  test    al, 2
0x140008a3b  jz      short loc_140008A55
0x140008a3d  mov     rcx, [rcx+18h]
0x140008a41  lea     r8, WPP_418d3fcde53e33810bba05463ad55e60_Traceguids
0x140008a48  mov     edx, 0Ah
0x140008a4d  mov     r9, rdi
0x140008a50  call    WPP_SF_q
0x140008a55  mov     eax, 0C0000001h
0x140008a5a  jmp     loc_140008C04
0x140008a5f  mov     ebp, 40h ; '@'
0x140008a64  mov     edx, 1C0h
0x140008a69  mov     ecx, ebp
0x140008a6b  mov     r8d, 536D6750h
0x140008a71  call    cs:__imp_ExAllocatePool2
0x140008a78  nop     dword ptr [rax+rax+00h]
0x140008a7d  mov     rbx, rax
0x140008a80  test    rax, rax
0x140008a83  jnz     short loc_140008ABC
0x140008a85  mov     rcx, cs:WPP_GLOBAL_Control
0x140008a8c  lea     rax, WPP_GLOBAL_Control
0x140008a93  cmp     rcx, rax
0x140008a96  jz      short loc_140008AB2
0x140008a98  mov     eax, [rcx+2Ch]
0x140008a9b  test    al, 2
0x140008a9d  jz      short loc_140008AB2
0x140008a9f  mov     rcx, [rcx+18h]
0x140008aa3  lea     edx, [rbp-35h]
0x140008aa6  lea     r8, WPP_418d3fcde53e33810bba05463ad55e60_Traceguids
0x140008aad  call    WPP_SF_
0x140008ab2  mov     eax, 0C000009Ah
0x140008ab7  jmp     loc_140008C04
0x140008abc  mov     [rax+8], rbx
0x140008ac0  lea     rdx, gFECLog2
0x140008ac7  mov     [rax], rbx
0x140008aca  mov     r8d, 736D6750h
0x140008ad0  mov     dword ptr [rax+28h], 8000h
0x140008ad7  mov     rcx, rbp
0x140008ada  mov     dword ptr [rax+2Ch], 7FFFh
0x140008ae1  movzx   eax, byte ptr [rdi+0A0h]
0x140008ae8  movzx   eax, byte ptr [rax+rdx]
0x140008aec  mov     edx, 80000h
0x140008af1  mov     [rbx+30h], eax
0x140008af4  call    cs:__imp_ExAllocatePool2
0x140008afb  nop     dword ptr [rax+rax+00h]
0x140008b00  mov     rbp, rax
0x140008b03  test    rax, rax
0x140008b06  jnz     short loc_140008B4B
0x140008b08  mov     rcx, cs:WPP_GLOBAL_Control
0x140008b0f  lea     rax, WPP_GLOBAL_Control
0x140008b16  cmp     rcx, rax
0x140008b19  jz      short loc_140008B35
0x140008b1b  mov     eax, [rcx+2Ch]
0x140008b1e  test    al, 2
0x140008b20  jz      short loc_140008B35
0x140008b22  mov     rcx, [rcx+18h]
0x140008b26  lea     edx, [rbp+0Ch]
0x140008b29  lea     r8, WPP_418d3fcde53e33810bba05463ad55e60_Traceguids
0x140008b30  call    WPP_SF_
0x140008b35  xor     edx, edx; Tag
0x140008b37  mov     rcx, rbx; P
0x140008b3a  call    cs:__imp_ExFreePoolWithTag
0x140008b41  nop     dword ptr [rax+rax+00h]
0x140008b46  jmp     loc_140008AB2
0x140008b4b  movzx   eax, byte ptr [rdi+0A0h]
0x140008b52  mov     r9d, 200h; Flags
0x140008b58  lea     ecx, ds:70h[rax*8]
0x140008b5f  mov     [rbx+10h], ecx
0x140008b62  mov     eax, [r14+38h]
0x140008b66  and     al, 10h
0x140008b68  neg     al
0x140008b6a  mov     ax, 3E8h
0x140008b6e  sbb     dx, dx
0x140008b71  xor     r8d, r8d; Free
0x140008b74  and     dx, ax
0x140008b77  add     dx, ax
0x140008b7a  mov     eax, ecx
0x140008b7c  mov     [rsp+68h+Depth], dx; Depth
0x140008b81  lea     rcx, [rbx+40h]; Lookaside
0x140008b85  mov     [rsp+68h+Tag], 526D6750h; Tag
0x140008b8d  xor     edx, edx; Allocate
0x140008b8f  mov     [rsp+68h+Size], rax; Size
0x140008b94  call    cs:__imp_ExInitializeNPagedLookasideList
0x140008b9b  nop     dword ptr [rax+rax+00h]
0x140008ba0  mov     rax, [rsi+60h]
0x140008ba4  xor     edx, edx
0x140008ba6  lea     r8d, [rdx+1]
0x140008baa  test    rax, rax
0x140008bad  jz      short loc_140008BB7
0x140008baf  add     edx, r8d
0x140008bb2  shr     rax, 1
0x140008bb5  jnz     short loc_140008BAF
0x140008bb7  xor     ecx, ecx
0x140008bb9  mov     dword ptr [rbx+1Ch], 20h ; ' '
0x140008bc0  cmp     edx, 5
0x140008bc3  mov     dword ptr [rbx+18h], 1Fh
0x140008bca  lea     eax, [rdx-5]
0x140008bcd  cmovnb  ecx, eax
0x140008bd0  xor     edx, edx
0x140008bd2  mov     [rbx+14h], ecx
0x140008bd5  mov     [rbx+38h], rbp
0x140008bd9  cmp     [rbx+28h], edx
0x140008bdc  jbe     short loc_140008BFB
0x140008bde  movzx   ecx, dx
0x140008be1  add     dx, r8w
0x140008be5  shl     rcx, 4
0x140008be9  add     rcx, rbp
0x140008bec  movzx   eax, dx
0x140008bef  mov     [rcx+8], rcx
0x140008bf3  mov     [rcx], rcx
0x140008bf6  cmp     eax, [rbx+28h]
0x140008bf9  jb      short loc_140008BDE
0x140008bfb  mov     [rsi+108h], rbx
0x140008c02  xor     eax, eax
0x140008c04  add     rsp, 40h
0x140008c08  pop     r14
0x140008c0a  pop     rdi
0x140008c0b  pop     rsi
0x140008c0c  pop     rbp
0x140008c0d  pop     rbx
0x140008c0e  retn
```
