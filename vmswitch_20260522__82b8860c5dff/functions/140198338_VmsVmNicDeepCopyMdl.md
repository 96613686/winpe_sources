# VmsVmNicDeepCopyMdl

- ea: `0x140198338`
- end: `0x14019875e`
- name: `VmsVmNicDeepCopyMdl`
- size: `1062`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400468a0`

## callees

- `0x140006620`
- `0x140198338`
- `0x1401bbe10`
- `0x1401bbfc0`

## import_xrefs

- `ntoskrnl!MmSizeOfMdl` at `0x1401983bd`
- `ntoskrnl!MmSizeOfMdl` at `0x1401983bd`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140198736`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140198736`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140198591`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140198591`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14019843d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14019843d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140198390`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140198390`
- `ntoskrnl!ExAllocatePool2` at `0x14019840f`
- `ntoskrnl!ExAllocatePool2` at `0x14019840f`

## pseudocode

```c
struct _MDL *__fastcall VmsVmNicDeepCopyMdl(__int64 a1, __int64 a2, __int64 *a3)
{
  struct _MDL *Pool2; // r14
  __int64 *v5; // r15
  SIZE_T v7; // r12
  struct _MDL *v8; // rdi
  PVOID MappedSystemVa; // rax
  __int64 ByteCount; // rax
  SIZE_T v11; // rbp
  signed int v12; // edi
  int v13; // edx
  signed __int32 v14; // eax
  signed __int32 v15; // ecx
  __int64 v16; // rdx
  _DWORD *v17; // r8
  unsigned __int64 v18; // r13
  char *v19; // rbp
  void *v20; // r11
  unsigned int v21; // r10d
  __int64 *v22; // rdi
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // rax
  unsigned int v26; // eax
  __int64 v27; // rsi
  unsigned int v28; // esi
  _DWORD *v29; // rax
  int v30; // ecx
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // rax
  __int64 v34; // rdx
  __int64 v35; // r9
  volatile signed __int32 *v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // r9
  __int64 v39; // rax
  __int64 v40; // rdx
  __int64 v41; // r9
  __int64 v42; // rcx
  __int64 v43; // rdx
  __int64 v44; // rcx
  char *v46; // [rsp+38h] [rbp-40h]
  unsigned int v47; // [rsp+90h] [rbp+18h]
  void *Src; // [rsp+98h] [rbp+20h]

  Pool2 = 0;
  v5 = a3;
  v7 = 0;
  v8 = (struct _MDL *)a3;
  while ( v8 )
  {
    if ( (v8->MdlFlags & 5) != 0 )
      MappedSystemVa = v8->MappedSystemVa;
    else
      MappedSystemVa = MmMapLockedPagesSpecifyCache(v8, 0, MmCached, 0, 0, 0x40000000u);
    if ( !MappedSystemVa )
      return Pool2;
    ByteCount = v8->ByteCount;
    v8 = v8->Next;
    v7 += ByteCount;
  }
  v11 = MmSizeOfMdl((PVOID)0xFFF, v7);
  v12 = v7 + v11 + 8;
  if ( v12 >= 0 )
  {
    v13 = VmsVmNicMaxSendShadowSizeInBytes;
    do
    {
      v14 = *(_DWORD *)(a1 + 384);
      v15 = v14 + v12;
      if ( v14 + v12 < 0 || v15 >= v13 )
        return Pool2;
    }
    while ( v14 != _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 384), v15, v14) );
    Pool2 = (struct _MDL *)ExAllocatePool2(64, v12, 1314288470);
    if ( !Pool2 )
    {
      _InterlockedAdd((volatile signed __int32 *)(a1 + 384), -v12);
      return Pool2;
    }
    if ( (VmsDiagnosticFlags & 4) != 0 )
    {
      v16 = 5440LL * KeGetCurrentProcessorNumberEx(0);
      _InterlockedAdd((volatile signed __int32 *)((char *)VmsPlanCpuTable + v16 + 496), v12);
    }
    LODWORD(Pool2->Next) = v12;
    Pool2 = (struct _MDL *)((char *)Pool2 + 8);
    v18 = (unsigned __int64)Pool2 + v11;
    v46 = (char *)Pool2 + v11;
    v19 = (char *)Pool2 + v11;
    if ( !v5 )
    {
LABEL_56:
      LOBYTE(v17) = 1;
      BLFlushBatchOpContextEx(a2, 0, v17);
      Pool2->Next = 0;
      Pool2->ByteCount = v7;
      Pool2->StartVa = (void *)(v18 & 0xFFFFFFFFFFFFF000uLL);
      Pool2->MdlFlags = 0;
      Pool2->Size = 8 * ((((v18 & 0xFFF) + v7 + 4095) >> 12) + 6);
      Pool2->ByteOffset = v18 & 0xFFF;
      MmBuildMdlForNonPagedPool(Pool2);
      return Pool2;
    }
    while ( 1 )
    {
      v20 = (void *)v5[3];
      v21 = *((_DWORD *)v5 + 10);
      Src = v20;
      v47 = v21;
      if ( !a2 )
        goto LABEL_53;
      v22 = (__int64 *)(a2 + 80);
      v23 = *(_QWORD *)(a2 + 80);
      if ( *(_BYTE *)(v23 + 1) == 1 && !*(_BYTE *)(a2 + 4) )
      {
        v24 = *(unsigned int *)(a2 + 12);
        v25 = 0;
        *(_BYTE *)(a2 + 4) = 1;
        if ( (_DWORD)v24 != -1 )
        {
          v16 = *(_QWORD *)(v23 + 24);
          if ( v16 )
            v25 = v16 + 20 * v24;
        }
        _InterlockedAdd16((volatile signed __int16 *)(v25 + 16), 1u);
      }
      v26 = *(_DWORD *)(*v22 + 4);
      if ( v26 )
      {
        v17 = *(_DWORD **)(a2 + 32);
        v28 = v17[2];
        if ( v28 >= v17[3] )
        {
          v28 = 0;
          if ( *(_DWORD *)(a2 + 16) < v26
            && (v29 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*v22 + 64)), (v17 = v29) != 0) )
          {
            *(_QWORD *)v29 = 0;
            v29[2] = 0;
            v30 = *(_DWORD *)(*v22 + 8);
            *((_QWORD *)v29 + 2) = v29 + 6;
            v29[3] = v30;
            **(_QWORD **)(a2 + 32) = v29;
            v31 = *v22;
            ++*(_DWORD *)(a2 + 16);
            *(_QWORD *)(a2 + 32) = v29;
            if ( *(_BYTE *)(v31 + 1) == 1 )
            {
              v32 = *(unsigned int *)(a2 + 12);
              v33 = 0;
              if ( (_DWORD)v32 != -1 )
              {
                v34 = *(_QWORD *)(v31 + 24);
                if ( v34 )
                  v33 = v34 + 20 * v32;
              }
              _InterlockedAdd16((volatile signed __int16 *)(v33 + 12), 1u);
              v35 = *(unsigned int *)(a2 + 12);
              v36 = 0;
              if ( (_DWORD)v35 != -1 )
              {
                v37 = *(_QWORD *)(*v22 + 24);
                if ( v37 )
                  v36 = (volatile signed __int32 *)(v37 + 20 * v35);
              }
              _InterlockedAdd(v36, 1u);
            }
          }
          else
          {
            LOBYTE(v16) = 1;
            BLFlushBatchOpContextEx(a2, v16, 0);
            v17 = (_DWORD *)(a2 + 56);
          }
          v20 = Src;
          v21 = v47;
        }
        ++*(_DWORD *)(a2 + 20);
        ++v17[2];
        if ( *(_BYTE *)(*v22 + 1) == 1 )
        {
          v38 = *(unsigned int *)(a2 + 12);
          v39 = 0;
          if ( (_DWORD)v38 != -1 )
          {
            v40 = *(_QWORD *)(*v22 + 24);
            if ( v40 )
              v39 = v40 + 20 * v38;
          }
          _InterlockedAdd16((volatile signed __int16 *)(v39 + 14), 1u);
          v41 = *(unsigned int *)(a2 + 12);
          v42 = 0;
          if ( (_DWORD)v41 != -1 )
          {
            v43 = *(_QWORD *)(*v22 + 24);
            if ( v43 )
              v42 = v43 + 20 * v41;
          }
          _InterlockedAdd((volatile signed __int32 *)(v42 + 4), 1u);
        }
        v44 = *((_QWORD *)v17 + 2);
        v16 = 3LL * v28;
        *(_QWORD *)(v44 + 8 * v16) = v19;
        *(_QWORD *)(v44 + 8 * v16 + 8) = v20;
        *(_DWORD *)(v44 + 8 * v16 + 16) = (16 * v21) | 1;
        v27 = v21;
        goto LABEL_54;
      }
      if ( *(_DWORD *)(a2 + 20) )
      {
        LOBYTE(v16) = 1;
        BLFlushBatchOpContextEx(a2, v16, 0);
        v21 = v47;
        v20 = Src;
      }
      if ( (*(_BYTE *)(a2 + 8) & 5) == 5 || (*(_BYTE *)(a2 + 8) & 6) == 6 )
      {
        v27 = v21;
        (*(void (**)(void))(*v22 + 32))();
        memmove(v19, Src, (unsigned int)v27);
        (*(void (**)(void))(*v22 + 40))();
      }
      else
      {
LABEL_53:
        v27 = v21;
        memmove(v19, v20, v21);
      }
LABEL_54:
      v5 = (__int64 *)*v5;
      v19 += v27;
      if ( !v5 )
      {
        v18 = (unsigned __int64)v46;
        goto LABEL_56;
      }
    }
  }
  return Pool2;
}

```

## disassembly

```asm
0x140198338  mov     [rsp+arg_0], rbx
0x14019833d  push    rbp
0x14019833e  push    rsi
0x14019833f  push    rdi
0x140198340  push    r12
0x140198342  push    r13
0x140198344  push    r14
0x140198346  push    r15
0x140198348  sub     rsp, 40h
0x14019834c  xor     r14d, r14d
0x14019834f  mov     rsi, rcx
0x140198352  mov     r15, r8
0x140198355  mov     rbx, rdx
0x140198358  xor     r12d, r12d
0x14019835b  mov     rdi, r8
0x14019835e  lea     ecx, [r14+1]
0x140198362  mov     [rsp+78h+var_48], r12
0x140198367  test    rdi, rdi
0x14019836a  jz      short loc_1401983B5
0x14019836c  test    byte ptr [rdi+0Ah], 5
0x140198370  jz      short loc_140198378
0x140198372  mov     rax, [rdi+18h]
0x140198376  jmp     short loc_1401983A1
0x140198378  mov     r8d, ecx; CacheType
0x14019837b  mov     [rsp+78h+Priority], 40000000h; Priority
0x140198383  mov     rcx, rdi; MemoryDescriptorList
0x140198386  mov     [rsp+78h+BugCheckOnFailure], r14d; BugCheckOnFailure
0x14019838b  xor     r9d, r9d; RequestedAddress
0x14019838e  xor     edx, edx; AccessMode
0x140198390  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140198397  nop     dword ptr [rax+rax+00h]
0x14019839c  mov     ecx, 1
0x1401983a1  test    rax, rax
0x1401983a4  jz      loc_140198742
0x1401983aa  mov     eax, [rdi+28h]
0x1401983ad  mov     rdi, [rdi]
0x1401983b0  add     r12, rax
0x1401983b3  jmp     short loc_140198362
0x1401983b5  mov     rdx, r12; Length
0x1401983b8  mov     ecx, 0FFFh; Base
0x1401983bd  call    cs:__imp_MmSizeOfMdl
0x1401983c4  nop     dword ptr [rax+rax+00h]
0x1401983c9  mov     rbp, rax
0x1401983cc  lea     edi, [rax+8]
0x1401983cf  add     edi, r12d
0x1401983d2  js      loc_140198742
0x1401983d8  mov     edx, cs:VmsVmNicMaxSendShadowSizeInBytes
0x1401983de  mov     eax, [rsi+180h]
0x1401983e4  lea     ecx, [rax+rdi]
0x1401983e7  test    ecx, ecx
0x1401983e9  js      loc_140198742
0x1401983ef  cmp     ecx, edx
0x1401983f1  jge     loc_140198742
0x1401983f7  lock cmpxchg [rsi+180h], ecx
0x1401983ff  jnz     short loc_1401983DE
0x140198401  movsxd  rdx, edi
0x140198404  mov     ecx, 40h ; '@'
0x140198409  mov     r8d, 4E567356h
0x14019840f  call    cs:__imp_ExAllocatePool2
0x140198416  nop     dword ptr [rax+rax+00h]
0x14019841b  mov     r14, rax
0x14019841e  test    rax, rax
0x140198421  jnz     short loc_140198431
0x140198423  neg     edi
0x140198425  lock add [rsi+180h], edi
0x14019842c  jmp     loc_140198742
0x140198431  mov     eax, cs:VmsDiagnosticFlags
0x140198437  test    al, 4
0x140198439  jz      short loc_140198461
0x14019843b  xor     ecx, ecx; ProcNumber
0x14019843d  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140198444  nop     dword ptr [rax+rax+00h]
0x140198449  mov     ecx, eax
0x14019844b  mov     rax, cs:VmsPlanCpuTable
0x140198452  imul    rdx, rcx, 1540h
0x140198459  lock add [rdx+rax+1F0h], edi
0x140198461  mov     [r14], edi
0x140198464  add     r14, 8
0x140198468  mov     edi, 6
0x14019846d  lea     r13, [r14+rbp]
0x140198471  mov     [rsp+78h+var_40], r13
0x140198476  mov     rbp, r13
0x140198479  test    r15, r15
0x14019847c  jz      loc_1401986D9
0x140198482  lea     r13d, [rdi-5]
0x140198486  mov     r12d, edi
0x140198489  mov     r11, [r15+18h]
0x14019848d  mov     r10d, [r15+28h]
0x140198491  mov     [rsp+78h+Src], r11
0x140198499  mov     [rsp+78h+arg_10], r10d
0x1401984a1  test    rbx, rbx
0x1401984a4  jz      loc_1401986AB
0x1401984aa  lea     rdi, [rbx+50h]
0x1401984ae  mov     rcx, [rdi]
0x1401984b1  cmp     [rcx+1], r13b
0x1401984b5  jnz     short loc_1401984E4
0x1401984b7  cmp     byte ptr [rbx+4], 0
0x1401984bb  jnz     short loc_1401984E4
0x1401984bd  mov     r8d, [rbx+0Ch]
0x1401984c1  xor     eax, eax
0x1401984c3  mov     [rbx+4], r13b
0x1401984c7  cmp     r8d, 0FFFFFFFFh
0x1401984cb  jz      short loc_1401984DE
0x1401984cd  mov     rdx, [rcx+18h]
0x1401984d1  test    rdx, rdx
0x1401984d4  jz      short loc_1401984DE
0x1401984d6  lea     rcx, [r8+r8*4]
0x1401984da  lea     rax, [rdx+rcx*4]
0x1401984de  lock add [rax+10h], r13w
0x1401984e4  mov     rcx, [rdi]
0x1401984e7  mov     eax, [rcx+4]
0x1401984ea  test    eax, eax
0x1401984ec  jnz     short loc_14019855D
0x1401984ee  cmp     [rbx+14h], eax
0x1401984f1  jz      short loc_140198511
0x1401984f3  xor     r8d, r8d
0x1401984f6  mov     dl, r13b
0x1401984f9  mov     rcx, rbx
0x1401984fc  call    BLFlushBatchOpContextEx
0x140198501  mov     r10d, [rsp+78h+arg_10]
0x140198509  mov     r11, [rsp+78h+Src]
0x140198511  mov     eax, [rbx+8]
0x140198514  and     eax, 5
0x140198517  cmp     al, 5
0x140198519  jz      short loc_14019852A
0x14019851b  mov     eax, [rbx+8]
0x14019851e  and     eax, r12d
0x140198521  cmp     al, r12b
0x140198524  jnz     loc_1401986AB
0x14019852a  mov     rax, [rdi]
0x14019852d  mov     esi, r10d
0x140198530  mov     rax, [rax+20h]
0x140198534  call    _guard_dispatch_icall
0x140198539  mov     rdx, [rsp+78h+Src]; Src
0x140198541  mov     r8d, esi; Size
0x140198544  mov     rcx, rbp; void *
0x140198547  call    memmove
0x14019854c  mov     rax, [rdi]
0x14019854f  mov     rax, [rax+28h]
0x140198553  call    _guard_dispatch_icall
0x140198558  jmp     loc_1401986BC
0x14019855d  mov     r8, [rbx+20h]
0x140198561  mov     esi, [r8+8]
0x140198565  cmp     esi, [r8+0Ch]
0x140198569  jb      loc_14019862D
0x14019856f  xor     esi, esi
0x140198571  cmp     [rbx+10h], eax
0x140198574  jb      short loc_14019858D
0x140198576  xor     r8d, r8d
0x140198579  mov     dl, r13b
0x14019857c  mov     rcx, rbx
0x14019857f  call    BLFlushBatchOpContextEx
0x140198584  lea     r8, [rbx+38h]
0x140198588  jmp     loc_14019861D
0x14019858d  add     rcx, 40h ; '@'; Lookaside
0x140198591  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140198598  nop     dword ptr [rax+rax+00h]
0x14019859d  mov     r8, rax
0x1401985a0  test    rax, rax
0x1401985a3  jz      short loc_140198576
0x1401985a5  mov     [rax], rsi
0x1401985a8  mov     [rax+8], esi
0x1401985ab  mov     rax, [rdi]
0x1401985ae  mov     ecx, [rax+8]
0x1401985b1  lea     rax, [r8+18h]
0x1401985b5  mov     [r8+10h], rax
0x1401985b9  mov     [r8+0Ch], ecx
0x1401985bd  mov     rax, [rbx+20h]
0x1401985c1  mov     [rax], r8
0x1401985c4  mov     rdx, [rdi]
0x1401985c7  add     [rbx+10h], r13d
0x1401985cb  mov     [rbx+20h], r8
0x1401985cf  cmp     [rdx+1], r13b
0x1401985d3  jnz     short loc_14019861D
0x1401985d5  mov     ecx, [rbx+0Ch]
0x1401985d8  xor     eax, eax
0x1401985da  or      r10d, 0FFFFFFFFh
0x1401985de  cmp     ecx, r10d
0x1401985e1  jz      short loc_1401985F4
0x1401985e3  mov     rdx, [rdx+18h]
0x1401985e7  test    rdx, rdx
0x1401985ea  jz      short loc_1401985F4
0x1401985ec  lea     rcx, [rcx+rcx*4]
0x1401985f0  lea     rax, [rdx+rcx*4]
0x1401985f4  lock add [rax+0Ch], r13w
0x1401985fa  mov     r9d, [rbx+0Ch]
0x1401985fe  xor     ecx, ecx
0x140198600  cmp     r9d, r10d
0x140198603  jz      short loc_140198619
0x140198605  mov     rax, [rdi]
0x140198608  mov     rdx, [rax+18h]
0x14019860c  test    rdx, rdx
0x14019860f  jz      short loc_140198619
0x140198611  lea     rcx, [r9+r9*4]
0x140198615  lea     rcx, [rdx+rcx*4]
0x140198619  lock add [rcx], r13d
0x14019861d  mov     r11, [rsp+78h+Src]
0x140198625  mov     r10d, [rsp+78h+arg_10]
0x14019862d  add     [rbx+14h], r13d
0x140198631  add     [r8+8], r13d
0x140198635  mov     rcx, [rdi]
0x140198638  cmp     [rcx+1], r13b
0x14019863c  jnz     short loc_140198686
0x14019863e  mov     r9d, [rbx+0Ch]
0x140198642  xor     eax, eax
0x140198644  cmp     r9d, 0FFFFFFFFh
0x140198648  jz      short loc_14019865B
0x14019864a  mov     rdx, [rcx+18h]
0x14019864e  test    rdx, rdx
0x140198651  jz      short loc_14019865B
0x140198653  lea     rcx, [r9+r9*4]
0x140198657  lea     rax, [rdx+rcx*4]
0x14019865b  lock add [rax+0Eh], r13w
0x140198661  mov     r9d, [rbx+0Ch]
0x140198665  xor     ecx, ecx
0x140198667  cmp     r9d, 0FFFFFFFFh
0x14019866b  jz      short loc_140198681
0x14019866d  mov     rax, [rdi]
0x140198670  mov     rdx, [rax+18h]
0x140198674  test    rdx, rdx
0x140198677  jz      short loc_140198681
0x140198679  lea     rcx, [r9+r9*4]
0x14019867d  lea     rcx, [rdx+rcx*4]
0x140198681  lock add [rcx+4], r13d
0x140198686  mov     rcx, [r8+10h]
0x14019868a  mov     eax, esi
0x14019868c  lea     rdx, [rax+rax*2]
0x140198690  mov     eax, r10d
0x140198693  mov     [rcx+rdx*8], rbp
0x140198697  shl     eax, 4
0x14019869a  or      eax, r13d
0x14019869d  mov     [rcx+rdx*8+8], r11
0x1401986a2  mov     [rcx+rdx*8+10h], eax
0x1401986a6  mov     esi, r10d
0x1401986a9  jmp     short loc_1401986BC
0x1401986ab  mov     r8d, r10d; Size
0x1401986ae  mov     rdx, r11; Src
0x1401986b1  mov     rcx, rbp; void *
0x1401986b4  mov     esi, r10d
0x1401986b7  call    memmove
0x1401986bc  mov     r15, [r15]
0x1401986bf  add     rbp, rsi
0x1401986c2  test    r15, r15
0x1401986c5  jnz     loc_140198489
0x1401986cb  mov     r12, [rsp+78h+var_48]
0x1401986d0  lea     edi, [r15+6]
0x1401986d4  mov     r13, [rsp+78h+var_40]
0x1401986d9  mov     r8b, 1
0x1401986dc  xor     edx, edx
0x1401986de  mov     rcx, rbx
0x1401986e1  call    BLFlushBatchOpContextEx
0x1401986e6  mov     edx, r13d
0x1401986e9  mov     qword ptr [r14], 0
0x1401986f0  mov     eax, edx
0x1401986f2  mov     [r14+28h], r12d
0x1401986f6  mov     r8d, 0FFFh
0x1401986fc  lea     rcx, [r12+0FFFh]
0x140198704  and     rax, r8
0x140198707  and     r13, 0FFFFFFFFFFFFF000h
0x14019870e  add     rcx, rax
0x140198711  mov     [r14+20h], r13
0x140198715  shr     rcx, 0Ch
0x140198719  xor     eax, eax
0x14019871b  add     cx, di
0x14019871e  mov     [r14+0Ah], ax
0x140198723  shl     cx, 3
0x140198727  and     edx, r8d
0x14019872a  mov     [r14+8], cx
0x14019872f  mov     rcx, r14; MemoryDescriptorList
0x140198732  mov     [r14+2Ch], edx
0x140198736  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14019873d  nop     dword ptr [rax+rax+00h]
0x140198742  mov     rbx, [rsp+78h+arg_0]
0x14019874a  mov     rax, r14
0x14019874d  add     rsp, 40h
0x140198751  pop     r15
0x140198753  pop     r14
0x140198755  pop     r13
0x140198757  pop     r12
0x140198759  pop     rdi
0x14019875a  pop     rsi
0x14019875b  pop     rbp
0x14019875c  retn
```
