# CopyMpGeneralAttributes

- ea: `0x14000c39c`
- end: `0x14000c5a7`
- name: `CopyMpGeneralAttributes`
- size: `523`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14000745c`
- `0x14000ea3c`

## callees

- `0x140007d00`
- `0x14000c39c`
- `0x14000d91c`
- `0x14000f200`

## import_xrefs

- `NDIS!NdisFreeMemory` at `0x14000c55c`
- `NDIS!NdisFreeMemory` at `0x14000c55c`

## pseudocode

```c
__int64 __fastcall CopyMpGeneralAttributes(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 *v6; // r14
  unsigned int v7; // ebx
  __int64 v8; // rax
  char v9; // bp
  __int64 v10; // rcx
  void *v11; // rcx

  *(_OWORD *)a3 = *(_OWORD *)a2;
  *(_OWORD *)(a3 + 16) = *(_OWORD *)(a2 + 16);
  *(_OWORD *)(a3 + 32) = *(_OWORD *)(a2 + 32);
  *(_OWORD *)(a3 + 48) = *(_OWORD *)(a2 + 48);
  *(_OWORD *)(a3 + 64) = *(_OWORD *)(a2 + 64);
  *(_OWORD *)(a3 + 80) = *(_OWORD *)(a2 + 80);
  *(_OWORD *)(a3 + 96) = *(_OWORD *)(a2 + 96);
  *(_OWORD *)(a3 + 112) = *(_OWORD *)(a2 + 112);
  *(_OWORD *)(a3 + 128) = *(_OWORD *)(a2 + 128);
  *(_OWORD *)(a3 + 144) = *(_OWORD *)(a2 + 144);
  *(_OWORD *)(a3 + 160) = *(_OWORD *)(a2 + 160);
  *(_OWORD *)(a3 + 176) = *(_OWORD *)(a2 + 176);
  *(_OWORD *)(a3 + 192) = *(_OWORD *)(a2 + 192);
  *(_OWORD *)(a3 + 208) = *(_OWORD *)(a2 + 208);
  if ( *(_QWORD *)(a2 + 160) )
  {
    v6 = (__int64 *)(a3 + 160);
    v7 = AllocMem(a1, 20, a3, a3 + 160);
    if ( v7 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_63d282d22d9e3f2cd53cfde58a2ac431_Traceguids);
      return v7;
    }
    v8 = *(_QWORD *)(a2 + 160);
    v9 = 1;
    v10 = *v6;
    *(_OWORD *)v10 = *(_OWORD *)v8;
    *(_DWORD *)(v10 + 16) = *(_DWORD *)(v8 + 16);
  }
  else
  {
    v7 = 0;
    v9 = 0;
  }
  if ( *(_DWORD *)(a2 + 208) && *(_QWORD *)(a2 + 200) )
  {
    *(_DWORD *)(a3 + 208) = 0;
    v7 = AllocMem(a1, *(unsigned int *)(a2 + 208), a3, a3 + 200);
    if ( v7 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_63d282d22d9e3f2cd53cfde58a2ac431_Traceguids);
      if ( v9 )
      {
        NdisFreeMemory(*(PVOID *)(a3 + 160), 0, 0);
        *(_QWORD *)(a3 + 160) = 0;
      }
    }
    else
    {
      v11 = *(void **)(a3 + 200);
      *(_DWORD *)(a3 + 208) = *(_DWORD *)(a2 + 208);
      memmove(v11, *(const void **)(a2 + 200), *(unsigned int *)(a2 + 208));
    }
  }
  return v7;
}

```

## disassembly

```asm
0x14000c39c  push    rbx
0x14000c39e  push    rbp
0x14000c39f  push    rsi
0x14000c3a0  push    rdi
0x14000c3a1  push    r14
0x14000c3a3  push    r15
0x14000c3a5  sub     rsp, 28h
0x14000c3a9  movups  xmm0, xmmword ptr [rdx]
0x14000c3ac  mov     rsi, r8
0x14000c3af  mov     rdi, rdx
0x14000c3b2  mov     r15, rcx
0x14000c3b5  movups  xmmword ptr [r8], xmm0
0x14000c3b9  movups  xmm1, xmmword ptr [rdx+10h]
0x14000c3bd  movups  xmmword ptr [r8+10h], xmm1
0x14000c3c2  movups  xmm0, xmmword ptr [rdx+20h]
0x14000c3c6  movups  xmmword ptr [r8+20h], xmm0
0x14000c3cb  movups  xmm1, xmmword ptr [rdx+30h]
0x14000c3cf  movups  xmmword ptr [r8+30h], xmm1
0x14000c3d4  movups  xmm0, xmmword ptr [rdx+40h]
0x14000c3d8  movups  xmmword ptr [r8+40h], xmm0
0x14000c3dd  movups  xmm1, xmmword ptr [rdx+50h]
0x14000c3e1  movups  xmmword ptr [r8+50h], xmm1
0x14000c3e6  movups  xmm0, xmmword ptr [rdx+60h]
0x14000c3ea  movups  xmmword ptr [r8+60h], xmm0
0x14000c3ef  movups  xmm1, xmmword ptr [rdx+70h]
0x14000c3f3  movups  xmmword ptr [r8+70h], xmm1
0x14000c3f8  movups  xmm0, xmmword ptr [rdx+80h]
0x14000c3ff  movups  xmmword ptr [r8+80h], xmm0
0x14000c407  movups  xmm1, xmmword ptr [rdx+90h]
0x14000c40e  movups  xmmword ptr [r8+90h], xmm1
0x14000c416  movups  xmm0, xmmword ptr [rdx+0A0h]
0x14000c41d  movups  xmmword ptr [r8+0A0h], xmm0
0x14000c425  movups  xmm1, xmmword ptr [rdx+0B0h]
0x14000c42c  movups  xmmword ptr [r8+0B0h], xmm1
0x14000c434  movups  xmm0, xmmword ptr [rdx+0C0h]
0x14000c43b  movups  xmmword ptr [r8+0C0h], xmm0
0x14000c443  movups  xmm1, xmmword ptr [rdx+0D0h]
0x14000c44a  movups  xmmword ptr [r8+0D0h], xmm1
0x14000c452  cmp     qword ptr [rdx+0A0h], 0
0x14000c45a  jz      short loc_14000C4D1
0x14000c45c  lea     r14, [r8+0A0h]
0x14000c463  mov     edx, 14h
0x14000c468  mov     r9, r14
0x14000c46b  call    AllocMem
0x14000c470  mov     ebx, eax
0x14000c472  test    eax, eax
0x14000c474  jz      short loc_14000C4B6
0x14000c476  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c47d  lea     rax, WPP_GLOBAL_Control
0x14000c484  cmp     rcx, rax
0x14000c487  jz      loc_14000C597
0x14000c48d  mov     edx, [rcx+2Ch]
0x14000c490  test    dl, 1
0x14000c493  jz      loc_14000C597
0x14000c499  mov     rcx, [rcx+18h]
0x14000c49d  lea     r8, WPP_63d282d22d9e3f2cd53cfde58a2ac431_Traceguids
0x14000c4a4  mov     edx, 0Dh
0x14000c4a9  mov     r9d, ebx
0x14000c4ac  call    WPP_SF_d
0x14000c4b1  jmp     loc_14000C597
0x14000c4b6  mov     rax, [rdi+0A0h]
0x14000c4bd  mov     bpl, 1
0x14000c4c0  mov     rcx, [r14]
0x14000c4c3  movups  xmm0, xmmword ptr [rax]
0x14000c4c6  movups  xmmword ptr [rcx], xmm0
0x14000c4c9  mov     eax, [rax+10h]
0x14000c4cc  mov     [rcx+10h], eax
0x14000c4cf  jmp     short loc_14000C4D6
0x14000c4d1  xor     ebx, ebx
0x14000c4d3  xor     bpl, bpl
0x14000c4d6  cmp     dword ptr [rdi+0D0h], 0
0x14000c4dd  jz      loc_14000C597
0x14000c4e3  cmp     qword ptr [rdi+0C8h], 0
0x14000c4eb  jz      loc_14000C597
0x14000c4f1  mov     dword ptr [rsi+0D0h], 0
0x14000c4fb  lea     r14, [rsi+0C8h]
0x14000c502  mov     edx, [rdi+0D0h]
0x14000c508  mov     r9, r14
0x14000c50b  mov     rcx, r15
0x14000c50e  call    AllocMem
0x14000c513  mov     ebx, eax
0x14000c515  test    eax, eax
0x14000c517  jz      short loc_14000C575
0x14000c519  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c520  lea     rax, WPP_GLOBAL_Control
0x14000c527  cmp     rcx, rax
0x14000c52a  jz      short loc_14000C54B
0x14000c52c  mov     eax, [rcx+2Ch]
0x14000c52f  test    al, 1
0x14000c531  jz      short loc_14000C54B
0x14000c533  mov     rcx, [rcx+18h]
0x14000c537  lea     r8, WPP_63d282d22d9e3f2cd53cfde58a2ac431_Traceguids
0x14000c53e  mov     edx, 0Eh
0x14000c543  mov     r9d, ebx
0x14000c546  call    WPP_SF_d
0x14000c54b  test    bpl, bpl
0x14000c54e  jz      short loc_14000C597
0x14000c550  mov     rcx, [rsi+0A0h]; VirtualAddress
0x14000c557  xor     r8d, r8d; MemoryFlags
0x14000c55a  xor     edx, edx; Length
0x14000c55c  call    cs:__imp_NdisFreeMemory
0x14000c563  nop     dword ptr [rax+rax+00h]
0x14000c568  mov     qword ptr [rsi+0A0h], 0
0x14000c573  jmp     short loc_14000C597
0x14000c575  mov     eax, [rdi+0D0h]
0x14000c57b  mov     rcx, [r14]; void *
0x14000c57e  mov     [rsi+0D0h], eax
0x14000c584  mov     r8d, [rdi+0D0h]; Size
0x14000c58b  mov     rdx, [rdi+0C8h]; Src
0x14000c592  call    memmove
0x14000c597  mov     eax, ebx
0x14000c599  add     rsp, 28h
0x14000c59d  pop     r15
0x14000c59f  pop     r14
0x14000c5a1  pop     rdi
0x14000c5a2  pop     rsi
0x14000c5a3  pop     rbp
0x14000c5a4  pop     rbx
0x14000c5a5  retn
```
