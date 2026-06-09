# SmpMakeSystemManagedPagingFileDescriptor

- ea: `0x14000af6c`
- end: `0x14000b0e2`
- name: `SmpMakeSystemManagedPagingFileDescriptor`
- size: `374`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000b464`

## callees

- `0x14000af6c`
- `0x14000b0e8`
- `0x14000d92c`

## pseudocode

```c
__int64 __fastcall SmpMakeSystemManagedPagingFileDescriptor(__int64 a1)
{
  unsigned __int64 v2; // r8
  unsigned __int64 v3; // r10
  unsigned __int64 v4; // r8
  unsigned __int64 v5; // rax
  unsigned __int64 v6; // r10
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // r11
  __int64 v9; // r8
  __int64 v10; // rdx
  unsigned __int64 v11; // r9
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // r8
  __int64 result; // rax
  unsigned __int64 v15; // rdx
  unsigned __int64 v16; // rax
  __int64 v17; // r10
  unsigned __int64 v18; // r9
  unsigned __int64 v19; // rcx
  __int64 v20; // rcx
  unsigned __int64 v21; // rax
  unsigned __int64 v22; // r9
  __int64 v23; // r10

  SmpInitializeManagedPagefileSupport();
  v2 = 3 * SmpMemorySize;
  if ( (unsigned __int64)(3 * SmpMemorySize) < 0x100000000LL )
    v2 = 0x100000000LL;
  SmpRoundDownToPowerOf2(v2 >> 4);
  v4 = SmpDesiredPfSizeBasedOnRAM;
  v5 = 0x400000000LL;
  if ( !SmpNumberOfManagedPagefilesCreated )
    v4 = SmpDesiredPfSizeBasedOnHistory;
  if ( v4 < 0x4000000 )
    v4 = 0x4000000;
  v6 = v3 >> 4;
  if ( v6 < 0x400000000LL )
    v5 = v6;
  if ( v4 < v5 )
  {
    v4 = 0x400000000LL;
    if ( v6 < 0x400000000LL )
      v4 = v6;
  }
  v7 = SmpRoundDownToPowerOf2(v4 >> 4);
  v10 = v9 - 1;
  v12 = v11;
  v13 = v8;
  if ( v7 > v11 )
    v12 = v7;
  result = ~(v12 - 1);
  v15 = result & (v12 + v10);
  if ( v15 <= v8 )
    v13 = v15;
  if ( !SmpNumberOfManagedPagefilesCreated && v13 < SmpDesiredPfSizeForApps )
  {
    v16 = SmpRoundDownToPowerOf2((unsigned __int64)SmpDesiredPfSizeForApps >> 4);
    v19 = v18;
    if ( v16 > v18 )
      v19 = v16;
    result = ~(v19 - 1);
    v13 = result & (v19 + v17 - 1);
    *(_DWORD *)(a1 + 92) |= 8u;
  }
  v20 = v13;
  if ( !SmpNumberOfPagefilesCreated && v13 < SmpDesiredPfSizeForCrashDump )
  {
    v21 = SmpRoundDownToPowerOf2((unsigned __int64)SmpDesiredPfSizeForCrashDump >> 4);
    if ( v21 > v22 )
      v22 = v21;
    result = ~(v22 - 1);
    v20 = result & (v22 + v23 - 1);
    if ( SmpDumpType != 1 )
      v13 = result & (v22 + v23 - 1);
    if ( SmpTryHardForCrashDump == 1 )
      *(_DWORD *)(a1 + 92) |= 8u;
  }
  *(_DWORD *)(a1 + 92) |= 2u;
  *(_QWORD *)(a1 + 48) = v13;
  *(_QWORD *)(a1 + 56) = v20;
  *(_QWORD *)(a1 + 64) = v8;
  return result;
}

```

## disassembly

```asm
0x14000af6c  push    rbx
0x14000af6e  sub     rsp, 20h
0x14000af72  mov     rbx, rcx
0x14000af75  call    SmpInitializeManagedPagefileSupport
0x14000af7a  mov     r10, cs:SmpMemorySize
0x14000af81  mov     rax, 100000000h
0x14000af8b  lea     r8, [r10+r10*2]
0x14000af8f  cmp     r8, rax
0x14000af92  cmovb   r8, rax
0x14000af96  mov     rcx, r8
0x14000af99  shr     rcx, 4
0x14000af9d  call    SmpRoundDownToPowerOf2
0x14000afa2  mov     r9d, 4000000h
0x14000afa8  lea     r11, [r8-1]
0x14000afac  mov     r8, cs:SmpDesiredPfSizeBasedOnRAM
0x14000afb3  cmp     rax, r9
0x14000afb6  mov     ecx, r9d
0x14000afb9  cmova   rcx, rax
0x14000afbd  add     r11, rcx
0x14000afc0  lea     rax, [rcx-1]
0x14000afc4  mov     rcx, 400000000h
0x14000afce  not     rax
0x14000afd1  and     r11, rax
0x14000afd4  mov     rax, rcx
0x14000afd7  cmp     cs:SmpNumberOfManagedPagefilesCreated, 0
0x14000afde  cmovz   r8, cs:SmpDesiredPfSizeBasedOnHistory
0x14000afe6  cmp     r8, r9
0x14000afe9  cmovb   r8, r9
0x14000afed  shr     r10, 4
0x14000aff1  cmp     r10, rcx
0x14000aff4  cmovb   rax, r10
0x14000aff8  cmp     r8, rax
0x14000affb  jnb     short loc_14000B007
0x14000affd  cmp     r10, rcx
0x14000b000  mov     r8, rcx
0x14000b003  cmovb   r8, r10
0x14000b007  mov     rcx, r8
0x14000b00a  shr     rcx, 4
0x14000b00e  call    SmpRoundDownToPowerOf2
0x14000b013  cmp     rax, r9
0x14000b016  lea     rdx, [r8-1]
0x14000b01a  mov     rcx, r9
0x14000b01d  mov     r8, r11
0x14000b020  cmova   rcx, rax
0x14000b024  add     rdx, rcx
0x14000b027  lea     rax, [rcx-1]
0x14000b02b  not     rax
0x14000b02e  and     rdx, rax
0x14000b031  cmp     rdx, r11
0x14000b034  cmovbe  r8, rdx
0x14000b038  cmp     cs:SmpNumberOfManagedPagefilesCreated, 0
0x14000b03f  jnz     short loc_14000B078
0x14000b041  mov     r10, cs:SmpDesiredPfSizeForApps
0x14000b048  cmp     r8, r10
0x14000b04b  jnb     short loc_14000B078
0x14000b04d  mov     rcx, r10
0x14000b050  shr     rcx, 4
0x14000b054  call    SmpRoundDownToPowerOf2
0x14000b059  cmp     rax, r9
0x14000b05c  lea     r8, [r10-1]
0x14000b060  mov     rcx, r9
0x14000b063  cmova   rcx, rax
0x14000b067  add     r8, rcx
0x14000b06a  lea     rax, [rcx-1]
0x14000b06e  not     rax
0x14000b071  and     r8, rax
0x14000b074  or      dword ptr [rbx+5Ch], 8
0x14000b078  cmp     cs:SmpNumberOfPagefilesCreated, 0
0x14000b07f  mov     rcx, r8
0x14000b082  jnz     short loc_14000B0CC
0x14000b084  mov     r10, cs:SmpDesiredPfSizeForCrashDump
0x14000b08b  cmp     r8, r10
0x14000b08e  jnb     short loc_14000B0CC
0x14000b090  mov     rcx, r10
0x14000b093  shr     rcx, 4
0x14000b097  call    SmpRoundDownToPowerOf2
0x14000b09c  cmp     rax, r9
0x14000b09f  lea     rcx, [r10-1]
0x14000b0a3  cmova   r9, rax
0x14000b0a7  add     rcx, r9
0x14000b0aa  lea     rax, [r9-1]
0x14000b0ae  not     rax
0x14000b0b1  and     rcx, rax
0x14000b0b4  cmp     cs:SmpDumpType, 1
0x14000b0bb  cmovnz  r8, rcx
0x14000b0bf  cmp     cs:SmpTryHardForCrashDump, 1
0x14000b0c6  jnz     short loc_14000B0CC
0x14000b0c8  or      dword ptr [rbx+5Ch], 8
0x14000b0cc  or      dword ptr [rbx+5Ch], 2
0x14000b0d0  mov     [rbx+30h], r8
0x14000b0d4  mov     [rbx+38h], rcx
0x14000b0d8  mov     [rbx+40h], r11
0x14000b0dc  add     rsp, 20h
0x14000b0e0  pop     rbx
0x14000b0e1  retn
```
