# MemoryNode::ShrinkIfNecessary(void)

- ea: `0x100419620`
- end: `0x1004197c9`
- name: `?ShrinkIfNecessary@MemoryNode@@QEAAHXZ`
- size: `425`
- prototype: `__int64 __fastcall(MemoryNode *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x100419ba0`

## callees

- `0x1004058f0`
- `0x100413ec0`
- `0x100419620`
- `0x1004197d0`
- `0x100419a60`
- `0x10043e730`
- `0x1004a31a0`
- `0x1005b1fc0`

## import_xrefs

- `KERNEL32!SetThreadPriority` at `0x1004a3c52`
- `KERNEL32!SetThreadPriority` at `0x1004a3c90`
- `KERNEL32!SetThreadPriority` at `0x1004a3c52`
- `KERNEL32!SetThreadPriority` at `0x1004a3c90`
- `KERNEL32!GetCurrentThread` at `0x100419702`
- `KERNEL32!GetCurrentThread` at `0x1004a3c27`
- `KERNEL32!GetCurrentThread` at `0x100419702`
- `KERNEL32!GetCurrentThread` at `0x1004a3c27`
- `KERNEL32!GetThreadPriority` at `0x100419713`
- `KERNEL32!GetThreadPriority` at `0x1004a3c38`
- `KERNEL32!GetThreadPriority` at `0x100419713`
- `KERNEL32!GetThreadPriority` at `0x1004a3c38`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MemoryNode::ShrinkIfNecessary(MemoryNode *this)
{
  int v2; // ebp
  unsigned __int64 v3; // r12
  unsigned int v4; // esi
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rcx
  int v8; // edi
  HANDLE CurrentThread; // rbp
  int ThreadPriority; // r15d
  char v11; // r14
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  unsigned __int16 v16; // di
  unsigned int v17; // r15d
  unsigned __int16 v18; // r14
  MemoryNode *MemoryNode; // rax
  unsigned int v20; // ecx
  unsigned __int16 v21; // ax
  unsigned __int16 v22; // di
  unsigned int v23; // ebp
  unsigned __int16 v24; // r14
  MemoryNode *v25; // rax
  unsigned int v26; // ecx
  unsigned __int16 v27; // ax
  unsigned __int64 v28; // [rsp+48h] [rbp-30h] BYREF
  int v29; // [rsp+50h] [rbp-28h]

  v2 = dword_100720F58;
  if ( dword_100720F58 == 1 )
    return 0;
  v3 = (unsigned __int64)((*((_DWORD *)this + 40) & 2) == 0) << 10;
  v4 = 0;
  if ( MemoryNode_MemoryPhase == 1 )
  {
    v16 = *((_WORD *)this + 64);
    v17 = SOS_OS_NumberOfMemoryNodeInfos;
    v18 = 0;
    if ( SOS_OS_NumberOfMemoryNodeInfos )
    {
      do
      {
        MemoryNode = MemoryNodeManager::GetMemoryNode(
                       (MemoryNodeManager *)&SOS_PublicGlobals::sm_MemoryNodeManager,
                       v16);
        MemoryNode::ReleaseAwayBlocks(MemoryNode, 0xFFFFFFFFFFFFFFFFuLL, 0, 0, 0);
        ++v18;
        v20 = v16 + 1;
        v21 = v16 + 1;
        v16 = 0;
        if ( v20 < (unsigned __int16)v17 )
          v16 = v21;
      }
      while ( v18 < v17 );
      v2 = dword_100720F58;
    }
  }
  v5 = *((_QWORD *)this + 8) + *((_QWORD *)this + 10) + *((_QWORD *)this + 9);
  if ( v2 == 1 )
    v5 += *((_QWORD *)this + 13) - *((_QWORD *)this + 12);
  v6 = (v5 + 1) / 2;
  v7 = *((_QWORD *)this + 21);
  if ( v7 >= *((_QWORD *)this + 18) )
    v7 = *((_QWORD *)this + 18);
  if ( v7 < v6 || (unsigned int)MemoryNode::ShouldShrinkOffline(this) )
  {
    do
    {
      if ( *((__int64 *)this + 14) <= 0 )
        break;
      v22 = *((_WORD *)this + 64);
      v23 = SOS_OS_NumberOfMemoryNodeInfos;
      v24 = 0;
      while ( v24 < v23 )
      {
        v25 = MemoryNodeManager::GetMemoryNode((MemoryNodeManager *)&SOS_PublicGlobals::sm_MemoryNodeManager, v22);
        MemoryNode::ReleaseAwayBlocks(v25, 1u, 0, 0, 0);
        ++v24;
        v26 = v22 + 1;
        v27 = v22 + 1;
        v22 = 0;
        if ( v26 < (unsigned __int16)v23 )
          v22 = v27;
      }
    }
    while ( (unsigned int)MemoryNode::ShouldShrink(this) || (unsigned int)MemoryNode::ShouldShrinkOffline(this) );
    v2 = dword_100720F58;
  }
  v28 = v3;
  v29 = 1;
  v8 = 0;
  if ( (qword_1007149B5 & 0x40000000000LL) != 0
    || (qword_1007149B5 & 0x2000000000000LL) != 0
    || (unsigned int)SOS_PublicGlobals::sm_cpuCount <= 4
    || v2 != 2 )
  {
    CurrentThread = GetCurrentThread();
    ThreadPriority = GetThreadPriority(CurrentThread);
    v11 = 0;
  }
  else
  {
    CurrentThread = GetCurrentThread();
    ThreadPriority = GetThreadPriority(CurrentThread);
    SetThreadPriority(CurrentThread, 1);
    v11 = 1;
  }
  do
  {
    if ( !v8 )
    {
      v12 = MemoryNode::ShrinkUsingBlockAllocators(this, &v28);
LABEL_16:
      v8 = v12;
      continue;
    }
    if ( v8 == 1 )
    {
      v12 = MemoryNode::ShrinkUsingExternalCaches(this, &v28);
      goto LABEL_16;
    }
    utassert_fail(1u, "FALSE", "MemoryNode.cpp", 4864, 0);
  }
  while ( v8 != 2 );
  if ( v11 )
    SetThreadPriority(CurrentThread, ThreadPriority);
  v13 = *((_QWORD *)this + 8) + *((_QWORD *)this + 10) + *((_QWORD *)this + 9);
  if ( dword_100720F58 == 1 )
    v13 += *((_QWORD *)this + 13) - *((_QWORD *)this + 12);
  v14 = *((_QWORD *)this + 21);
  if ( v14 >= *((_QWORD *)this + 18) )
    v14 = *((_QWORD *)this + 18);
  if ( v14 < (v13 + 1) / 2 || (unsigned int)MemoryNode::ShouldShrinkOffline(this) )
    return 1;
  return v4;
}

```

## disassembly

```asm
0x100419620  mov     rax, rsp
0x100419623  push    r12
0x100419625  push    r14
0x100419627  push    r15
0x100419629  sub     rsp, 60h
0x10041962d  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x100419635  mov     [rax+8], rbx
0x100419639  mov     [rax+10h], rbp
0x10041963d  mov     [rax+18h], rsi
0x100419641  mov     [rax+20h], rdi
0x100419645  mov     rbx, rcx
0x100419648  mov     ebp, cs:dword_100720F58
0x10041964e  cmp     ebp, 1
0x100419651  jz      loc_1004A3B07
0x100419657  mov     r12d, [rcx+0A0h]
0x10041965e  shr     r12d, 1
0x100419661  not     r12d
0x100419664  and     r12d, 1
0x100419668  shl     r12, 0Ah
0x10041966c  xor     esi, esi
0x10041966e  cmp     cs:?MemoryNode_MemoryPhase@@3W4MemoryPhase@MemoryNode@@A, 1; MemoryNode::MemoryPhase MemoryNode_MemoryPhase
0x100419675  jz      loc_1004A3B0F
0x10041967b  mov     rcx, [rbx+48h]
0x10041967f  add     rcx, [rbx+50h]
0x100419683  add     rcx, [rbx+40h]
0x100419687  cmp     ebp, 1
0x10041968a  jz      loc_1004A3B7F
0x100419690  lea     rax, [rcx+1]
0x100419694  cqo
0x100419696  sub     rax, rdx
0x100419699  sar     rax, 1
0x10041969c  mov     rdx, rax
0x10041969f  mov     rcx, [rbx+0A8h]
0x1004196a6  mov     rax, [rbx+90h]
0x1004196ad  cmp     rcx, rax
0x1004196b0  cmovge  rcx, rax
0x1004196b4  cmp     rcx, rdx
0x1004196b7  jl      loc_1004A3BA0
0x1004196bd  mov     rcx, rbx; this
0x1004196c0  call    ?ShouldShrinkOffline@MemoryNode@@QEBAHXZ; MemoryNode::ShouldShrinkOffline(void)
0x1004196c5  test    eax, eax
0x1004196c7  jnz     loc_1004A3B90
0x1004196cd  mov     [rsp+78h+var_30], r12
0x1004196d2  mov     [rsp+78h+var_28], 1
0x1004196da  mov     edi, esi
0x1004196dc  test    byte ptr cs:qword_1007149B5+5, 4
0x1004196e3  jnz     short loc_100419702
0x1004196e5  test    byte ptr cs:qword_1007149B5+6, 2
0x1004196ec  jnz     short loc_100419702
0x1004196ee  mov     eax, cs:?sm_cpuCount@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_cpuCount
0x1004196f4  cmp     eax, 4
0x1004196f7  jbe     short loc_100419702
0x1004196f9  cmp     ebp, 2
0x1004196fc  jz      loc_1004A3C27
0x100419702  call    cs:__imp_GetCurrentThread
0x100419708  mov     rbp, rax
0x10041970b  mov     [rsp+78h+var_40], rax
0x100419710  mov     rcx, rax; hThread
0x100419713  call    cs:__imp_GetThreadPriority
0x100419719  mov     r15d, eax
0x10041971c  mov     [rsp+78h+var_38], eax
0x100419720  xor     r14b, r14b
0x100419723  mov     [rsp+78h+var_34], r14b
0x100419728  nop     dword ptr [rax+rax+00000000h]
0x100419730  test    edi, edi
0x100419732  jnz     loc_100437A74
0x100419738  lea     rdx, [rsp+78h+var_30]
0x10041973d  mov     rcx, rbx
0x100419740  call    ?ShrinkUsingBlockAllocators@MemoryNode@@AEAA?AW4ShrinkState@1@PEAUShrinkInfo@1@@Z; MemoryNode::ShrinkUsingBlockAllocators(MemoryNode::ShrinkInfo *)
0x100419745  mov     edi, eax
0x100419747  cmp     edi, 2
0x10041974a  jnz     short loc_100419730
0x10041974c  test    r14b, r14b
0x10041974f  jnz     loc_1004A3C8A
0x100419755  mov     rdx, [rbx+48h]
0x100419759  add     rdx, [rbx+50h]
0x10041975d  add     rdx, [rbx+40h]
0x100419761  cmp     cs:dword_100720F58, 1
0x100419768  jz      loc_1004A3C9D
0x10041976e  mov     rcx, [rbx+0A8h]
0x100419775  mov     rax, [rbx+90h]
0x10041977c  cmp     rcx, rax
0x10041977f  cmovge  rcx, rax
0x100419783  lea     rax, [rdx+1]
0x100419787  cqo
0x100419789  sub     rax, rdx
0x10041978c  sar     rax, 1
0x10041978f  cmp     rcx, rax
0x100419792  jl      loc_1004A3CAE
0x100419798  mov     rcx, rbx; this
0x10041979b  call    ?ShouldShrinkOffline@MemoryNode@@QEBAHXZ; MemoryNode::ShouldShrinkOffline(void)
0x1004197a0  test    eax, eax
0x1004197a2  jnz     loc_1004A3CAE
0x1004197a8  mov     eax, esi
0x1004197aa  lea     r11, [rsp+78h+var_18]
0x1004197af  mov     rbx, [r11+20h]
0x1004197b3  mov     rbp, [r11+28h]
0x1004197b7  mov     rsi, [r11+30h]
0x1004197bb  mov     rdi, [r11+38h]
0x1004197bf  mov     rsp, r11
0x1004197c2  pop     r15
0x1004197c4  pop     r14
0x1004197c6  pop     r12
0x1004197c8  retn
0x100437a74  cmp     edi, 1
0x100437a77  jnz     loc_1004A3C61
0x100437a7d  lea     rdx, [rsp+78h+var_30]
0x100437a82  mov     rcx, rbx
0x100437a85  call    ?ShrinkUsingExternalCaches@MemoryNode@@AEAA?AW4ShrinkState@1@PEAUShrinkInfo@1@@Z; MemoryNode::ShrinkUsingExternalCaches(MemoryNode::ShrinkInfo *)
0x100437a8a  jmp     loc_100419745
0x1004a3b07  xor     eax, eax
0x1004a3b09  jmp     loc_1004197AA
0x1004a3b0f  movzx   edi, word ptr [rcx+80h]
0x1004a3b16  mov     r15d, cs:?SOS_OS_NumberOfMemoryNodeInfos@@3KA; ulong SOS_OS_NumberOfMemoryNodeInfos
0x1004a3b1d  movzx   r14d, si
0x1004a3b21  test    r15d, r15d
0x1004a3b24  jz      loc_10041967B
0x1004a3b2a  movzx   ebp, r15w
0x1004a3b2e  xchg    ax, ax
0x1004a3b30  movzx   edx, di; unsigned __int16
0x1004a3b33  lea     rcx, ?sm_MemoryNodeManager@SOS_PublicGlobals@@2VMemoryNodeManager@@A; this
0x1004a3b3a  call    ?GetMemoryNode@MemoryNodeManager@@QEAAPEAVMemoryNode@@G@Z; MemoryNodeManager::GetMemoryNode(ushort)
0x1004a3b3f  mov     [rsp+78h+Format], rsi; unsigned __int64 *
0x1004a3b44  xor     r9d, r9d; unsigned __int64 *
0x1004a3b47  xor     r8d, r8d; int
0x1004a3b4a  lea     rdx, [r9-1]; unsigned __int64
0x1004a3b4e  mov     rcx, rax; this
0x1004a3b51  call    ?ReleaseAwayBlocks@MemoryNode@@QEAAX_KHPEA_K1@Z; MemoryNode::ReleaseAwayBlocks(unsigned __int64,int,unsigned __int64 *,unsigned __int64 *)
0x1004a3b56  inc     r14w
0x1004a3b5a  movzx   ecx, di
0x1004a3b5d  inc     ecx
0x1004a3b5f  lea     eax, [rdi+1]
0x1004a3b62  mov     edi, esi
0x1004a3b64  cmp     ecx, ebp
0x1004a3b66  cmovb   di, ax
0x1004a3b6a  movzx   eax, r14w
0x1004a3b6e  cmp     eax, r15d
0x1004a3b71  jb      short loc_1004A3B30
0x1004a3b73  mov     ebp, cs:dword_100720F58
0x1004a3b79  jmp     loc_10041967B
0x1004a3b7f  mov     rax, [rbx+68h]
0x1004a3b83  sub     rax, [rbx+60h]
0x1004a3b87  add     rcx, rax
0x1004a3b8a  jmp     loc_100419690
0x1004a3b90  nop
0x1004a3b91  nop     dword ptr [rax+00h]
0x1004a3b95  nop     word ptr [rax+rax+00000000h]
0x1004a3ba0  cmp     [rbx+70h], rsi
0x1004a3ba4  jle     short loc_1004A3C1B
0x1004a3ba6  movzx   edi, word ptr [rbx+80h]
0x1004a3bad  mov     ebp, cs:?SOS_OS_NumberOfMemoryNodeInfos@@3KA; ulong SOS_OS_NumberOfMemoryNodeInfos
0x1004a3bb3  movzx   r14d, si
0x1004a3bb7  test    ebp, ebp
0x1004a3bb9  jz      short loc_1004A3C03
0x1004a3bbb  movzx   r15d, bp
0x1004a3bbf  nop
0x1004a3bc0  movzx   edx, di; unsigned __int16
0x1004a3bc3  lea     rcx, ?sm_MemoryNodeManager@SOS_PublicGlobals@@2VMemoryNodeManager@@A; this
0x1004a3bca  call    ?GetMemoryNode@MemoryNodeManager@@QEAAPEAVMemoryNode@@G@Z; MemoryNodeManager::GetMemoryNode(ushort)
0x1004a3bcf  mov     [rsp+78h+Format], rsi; unsigned __int64 *
0x1004a3bd4  xor     r9d, r9d; unsigned __int64 *
0x1004a3bd7  xor     r8d, r8d; int
0x1004a3bda  lea     edx, [r9+1]; unsigned __int64
0x1004a3bde  mov     rcx, rax; this
0x1004a3be1  call    ?ReleaseAwayBlocks@MemoryNode@@QEAAX_KHPEA_K1@Z; MemoryNode::ReleaseAwayBlocks(unsigned __int64,int,unsigned __int64 *,unsigned __int64 *)
0x1004a3be6  inc     r14w
0x1004a3bea  movzx   ecx, di
0x1004a3bed  inc     ecx
0x1004a3bef  lea     eax, [rdi+1]
0x1004a3bf2  mov     edi, esi
0x1004a3bf4  cmp     ecx, r15d
0x1004a3bf7  cmovb   di, ax
0x1004a3bfb  movzx   eax, r14w
0x1004a3bff  cmp     eax, ebp
0x1004a3c01  jb      short loc_1004A3BC0
0x1004a3c03  mov     rcx, rbx; this
0x1004a3c06  call    ?ShouldShrink@MemoryNode@@QEBAHXZ; MemoryNode::ShouldShrink(void)
0x1004a3c0b  test    eax, eax
0x1004a3c0d  jnz     short loc_1004A3BA0
0x1004a3c0f  mov     rcx, rbx; this
0x1004a3c12  call    ?ShouldShrinkOffline@MemoryNode@@QEBAHXZ; MemoryNode::ShouldShrinkOffline(void)
0x1004a3c17  test    eax, eax
0x1004a3c19  jnz     short loc_1004A3BA0
0x1004a3c1b  mov     ebp, cs:dword_100720F58
0x1004a3c21  jmp     loc_1004196CD
0x1004a3c27  call    cs:__imp_GetCurrentThread
0x1004a3c2d  mov     rbp, rax
0x1004a3c30  mov     [rsp+78h+var_40], rax
0x1004a3c35  mov     rcx, rax; hThread
0x1004a3c38  call    cs:__imp_GetThreadPriority
0x1004a3c3e  mov     r15d, eax
0x1004a3c41  mov     [rsp+78h+var_38], eax
0x1004a3c45  mov     [rsp+78h+var_34], sil
0x1004a3c4a  mov     edx, 1; nPriority
0x1004a3c4f  mov     rcx, rbp; hThread
0x1004a3c52  call    cs:__imp_SetThreadPriority
0x1004a3c58  mov     r14b, 1
0x1004a3c5b  jmp     loc_100419723
0x1004a3c61  mov     [rsp+78h+Format], rsi; Format
0x1004a3c66  mov     r9d, 1300h; int
0x1004a3c6c  lea     r8, aMemorynodeCpp; "MemoryNode.cpp"
0x1004a3c73  lea     rdx, ?szExpression@?8??GetNumberOfPartitions@?$CMemPartitioned@V?$CMemDetour@V?$CMemThread@VCMemLargePageObj@@@@@@@@SAKW4PartitioningType@@@Z@4QBDB; "FALSE"
0x1004a3c7a  mov     ecx, 1; unsigned int
0x1004a3c7f  call    ?utassert_fail@@YAXIPEBD0H0ZZ; utassert_fail(uint,char const *,char const *,int,char const *,...)
0x1004a3c84  jmp     loc_100419747
0x1004a3c8a  mov     edx, r15d; nPriority
0x1004a3c8d  mov     rcx, rbp; hThread
0x1004a3c90  call    cs:__imp_SetThreadPriority
0x1004a3c96  nop
0x1004a3c97  jmp     loc_100419755
0x1004a3c9d  mov     rax, [rbx+68h]
0x1004a3ca1  sub     rax, [rbx+60h]
0x1004a3ca5  add     rdx, rax
0x1004a3ca8  jmp     loc_10041976E
0x1004a3cae  mov     esi, 1
0x1004a3cb3  jmp     loc_1004197A8
```
