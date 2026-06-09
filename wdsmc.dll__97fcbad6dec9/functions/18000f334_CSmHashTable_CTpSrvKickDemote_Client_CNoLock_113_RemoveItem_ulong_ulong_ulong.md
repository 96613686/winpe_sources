# CSmHashTable<CTpSrvKickDemote::Client,CNoLock,113>::RemoveItem<ulong>(ulong,ulong)

- ea: `0x18000f334`
- end: `0x18000f405`
- name: `??$RemoveItem@K@?$CSmHashTable@UClient@CTpSrvKickDemote@@VCNoLock@@$0HB@@@QEAAPEAUClient@CTpSrvKickDemote@@KK@Z`
- size: `209`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e968`

## callees

- `0x18000f334`

## pseudocode

```c
__int64 __fastcall CSmHashTable<CTpSrvKickDemote::Client,CNoLock,113>::RemoveItem<unsigned long>(
        __int64 a1,
        unsigned int a2,
        int a3)
{
  __int64 v6; // r10
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rax

  v6 = 0;
  v7 = a2 % 0x71;
  v8 = 3 * v7;
  v9 = *(_QWORD *)(a1 + 24 * v7 + 8);
  if ( v9 )
  {
    v10 = *(_QWORD *)(a1 + 24 * v7 + 8);
    while ( *(_DWORD *)(v10 + 32) != a2 || *(_DWORD *)v10 != a3 )
    {
      v10 = *(_QWORD *)(v10 + 16);
      if ( !v10 )
        return v6;
    }
    if ( v10 )
    {
      v11 = *(_QWORD *)(a1 + 24 * v7 + 16);
      if ( v9 == v11 )
      {
        *(_QWORD *)(a1 + 8 * v8 + 16) = 0;
        *(_QWORD *)(a1 + 8 * v8 + 8) = 0;
      }
      else if ( v10 == v9 )
      {
        v12 = *(_QWORD *)(v9 + 16);
        *(_QWORD *)(a1 + 8 * v8 + 8) = v12;
        *(_QWORD *)(v12 + 24) = 0;
      }
      else if ( v10 == v11 )
      {
        v13 = *(_QWORD *)(v11 + 24);
        *(_QWORD *)(a1 + 8 * v8 + 16) = v13;
        *(_QWORD *)(v13 + 16) = 0;
      }
      else
      {
        *(_QWORD *)(*(_QWORD *)(v10 + 24) + 16LL) = *(_QWORD *)(v10 + 16);
        *(_QWORD *)(*(_QWORD *)(v10 + 16) + 24LL) = *(_QWORD *)(v10 + 24);
      }
      --*(_DWORD *)(a1 + 8 * v8 + 28);
    }
    --*(_DWORD *)(a1 + 2720);
    return v10;
  }
  return v6;
}

```

## disassembly

```asm
0x18000f334  mov     [rsp+arg_0], rbx
0x18000f339  mov     r11d, edx
0x18000f33c  mov     r9, rcx
0x18000f33f  mov     eax, 21FB7813h
0x18000f344  mov     ecx, r11d
0x18000f347  mul     edx
0x18000f349  mov     eax, r11d
0x18000f34c  mov     ebx, r8d
0x18000f34f  sub     eax, edx
0x18000f351  xor     r10d, r10d
0x18000f354  shr     eax, 1
0x18000f356  add     eax, edx
0x18000f358  shr     eax, 6
0x18000f35b  imul    eax, 71h ; 'q'
0x18000f35e  sub     ecx, eax
0x18000f360  lea     r8, [rcx+rcx*2]
0x18000f364  mov     rax, [r9+r8*8+8]
0x18000f369  test    rax, rax
0x18000f36c  jz      loc_18000F3FC
0x18000f372  mov     rdx, rax
0x18000f375  cmp     [rdx+20h], r11d
0x18000f379  jnz     short loc_18000F37F
0x18000f37b  cmp     [rdx], ebx
0x18000f37d  jz      short loc_18000F38A
0x18000f37f  mov     rdx, [rdx+10h]
0x18000f383  test    rdx, rdx
0x18000f386  jz      short loc_18000F3FC
0x18000f388  jmp     short loc_18000F375
0x18000f38a  or      r10d, 0FFFFFFFFh
0x18000f38e  test    rdx, rdx
0x18000f391  jz      short loc_18000F3F2
0x18000f393  mov     rcx, [r9+r8*8+10h]
0x18000f398  cmp     rax, rcx
0x18000f39b  jnz     short loc_18000F3AB
0x18000f39d  and     qword ptr [r9+r8*8+10h], 0
0x18000f3a3  and     qword ptr [r9+r8*8+8], 0
0x18000f3a9  jmp     short loc_18000F3ED
0x18000f3ab  cmp     rdx, rax
0x18000f3ae  jnz     short loc_18000F3C0
0x18000f3b0  mov     rax, [rax+10h]
0x18000f3b4  mov     [r9+r8*8+8], rax
0x18000f3b9  and     qword ptr [rax+18h], 0
0x18000f3be  jmp     short loc_18000F3ED
0x18000f3c0  cmp     rdx, rcx
0x18000f3c3  jnz     short loc_18000F3D5
0x18000f3c5  mov     rax, [rcx+18h]
0x18000f3c9  mov     [r9+r8*8+10h], rax
0x18000f3ce  and     qword ptr [rax+10h], 0
0x18000f3d3  jmp     short loc_18000F3ED
0x18000f3d5  mov     rcx, [rdx+18h]
0x18000f3d9  mov     rax, [rdx+10h]
0x18000f3dd  mov     [rcx+10h], rax
0x18000f3e1  mov     rcx, [rdx+10h]
0x18000f3e5  mov     rax, [rdx+18h]
0x18000f3e9  mov     [rcx+18h], rax
0x18000f3ed  add     [r9+r8*8+1Ch], r10d
0x18000f3f2  add     [r9+0AA0h], r10d
0x18000f3f9  mov     r10, rdx
0x18000f3fc  mov     rbx, [rsp+arg_0]
0x18000f401  mov     rax, r10
0x18000f404  retn
```
