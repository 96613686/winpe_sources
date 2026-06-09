# VmsVmNicDeepCopyMdl

- ea: `0x1401983a8`
- end: `0x1401987ce`
- name: `VmsVmNicDeepCopyMdl`
- size: `1062`
- prototype: `struct _MDL *__fastcall(__int64, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400468a0`

## callees

- `0x140006620`
- `0x1401983a8`
- `0x1401bbe80`
- `0x1401bc040`

## import_xrefs

- `ntoskrnl!MmSizeOfMdl` at `0x14019842d`
- `ntoskrnl!MmSizeOfMdl` at `0x14019842d`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1401987a6`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1401987a6`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140198601`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140198601`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1401984ad`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1401984ad`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140198400`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140198400`
- `ntoskrnl!ExAllocatePool2` at `0x14019847f`
- `ntoskrnl!ExAllocatePool2` at `0x14019847f`

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
0x1401983a8  mov     [rsp+arg_0], rbx
0x1401983ad  push    rbp
0x1401983ae  push    rsi
0x1401983af  push    rdi
0x1401983b0  push    r12
0x1401983b2  push    r13
0x1401983b4  push    r14
0x1401983b6  push    r15
0x1401983b8  sub     rsp, 40h
0x1401983bc  xor     r14d, r14d
0x1401983bf  mov     rsi, rcx
0x1401983c2  mov     r15, r8
0x1401983c5  mov     rbx, rdx
0x1401983c8  xor     r12d, r12d
0x1401983cb  mov     rdi, r8
0x1401983ce  lea     ecx, [r14+1]
0x1401983d2  mov     [rsp+78h+var_48], r12
0x1401983d7  test    rdi, rdi
0x1401983da  jz      short loc_140198425
0x1401983dc  test    byte ptr [rdi+0Ah], 5
0x1401983e0  jz      short loc_1401983E8
0x1401983e2  mov     rax, [rdi+18h]
0x1401983e6  jmp     short loc_140198411
0x1401983e8  mov     r8d, ecx; CacheType
0x1401983eb  mov     [rsp+78h+Priority], 40000000h; Priority
0x1401983f3  mov     rcx, rdi; MemoryDescriptorList
0x1401983f6  mov     [rsp+78h+BugCheckOnFailure], r14d; BugCheckOnFailure
0x1401983fb  xor     r9d, r9d; RequestedAddress
0x1401983fe  xor     edx, edx; AccessMode
0x140198400  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140198407  nop     dword ptr [rax+rax+00h]
0x14019840c  mov     ecx, 1
0x140198411  test    rax, rax
0x140198414  jz      loc_1401987B2
0x14019841a  mov     eax, [rdi+28h]
0x14019841d  mov     rdi, [rdi]
0x140198420  add     r12, rax
0x140198423  jmp     short loc_1401983D2
0x140198425  mov     rdx, r12; Length
0x140198428  mov     ecx, 0FFFh; Base
0x14019842d  call    cs:__imp_MmSizeOfMdl
0x140198434  nop     dword ptr [rax+rax+00h]
0x140198439  mov     rbp, rax
0x14019843c  lea     edi, [rax+8]
0x14019843f  add     edi, r12d
0x140198442  js      loc_1401987B2
0x140198448  mov     edx, cs:VmsVmNicMaxSendShadowSizeInBytes
0x14019844e  mov     eax, [rsi+180h]
0x140198454  lea     ecx, [rax+rdi]
0x140198457  test    ecx, ecx
0x140198459  js      loc_1401987B2
0x14019845f  cmp     ecx, edx
0x140198461  jge     loc_1401987B2
0x140198467  lock cmpxchg [rsi+180h], ecx
0x14019846f  jnz     short loc_14019844E
0x140198471  movsxd  rdx, edi
0x140198474  mov     ecx, 40h ; '@'
0x140198479  mov     r8d, 4E567356h
0x14019847f  call    cs:__imp_ExAllocatePool2
0x140198486  nop     dword ptr [rax+rax+00h]
0x14019848b  mov     r14, rax
0x14019848e  test    rax, rax
0x140198491  jnz     short loc_1401984A1
0x140198493  neg     edi
0x140198495  lock add [rsi+180h], edi
0x14019849c  jmp     loc_1401987B2
0x1401984a1  mov     eax, cs:VmsDiagnosticFlags
0x1401984a7  test    al, 4
0x1401984a9  jz      short loc_1401984D1
0x1401984ab  xor     ecx, ecx; ProcNumber
0x1401984ad  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1401984b4  nop     dword ptr [rax+rax+00h]
0x1401984b9  mov     ecx, eax
0x1401984bb  mov     rax, cs:VmsPlanCpuTable
0x1401984c2  imul    rdx, rcx, 1540h
0x1401984c9  lock add [rdx+rax+1F0h], edi
0x1401984d1  mov     [r14], edi
0x1401984d4  add     r14, 8
0x1401984d8  mov     edi, 6
0x1401984dd  lea     r13, [r14+rbp]
0x1401984e1  mov     [rsp+78h+var_40], r13
0x1401984e6  mov     rbp, r13
0x1401984e9  test    r15, r15
0x1401984ec  jz      loc_140198749
0x1401984f2  lea     r13d, [rdi-5]
0x1401984f6  mov     r12d, edi
0x1401984f9  mov     r11, [r15+18h]
0x1401984fd  mov     r10d, [r15+28h]
0x140198501  mov     [rsp+78h+Src], r11
0x140198509  mov     [rsp+78h+arg_10], r10d
0x140198511  test    rbx, rbx
0x140198514  jz      loc_14019871B
0x14019851a  lea     rdi, [rbx+50h]
0x14019851e  mov     rcx, [rdi]
0x140198521  cmp     [rcx+1], r13b
0x140198525  jnz     short loc_140198554
0x140198527  cmp     byte ptr [rbx+4], 0
0x14019852b  jnz     short loc_140198554
0x14019852d  mov     r8d, [rbx+0Ch]
0x140198531  xor     eax, eax
0x140198533  mov     [rbx+4], r13b
0x140198537  cmp     r8d, 0FFFFFFFFh
0x14019853b  jz      short loc_14019854E
0x14019853d  mov     rdx, [rcx+18h]
0x140198541  test    rdx, rdx
0x140198544  jz      short loc_14019854E
0x140198546  lea     rcx, [r8+r8*4]
0x14019854a  lea     rax, [rdx+rcx*4]
0x14019854e  lock add [rax+10h], r13w
0x140198554  mov     rcx, [rdi]
0x140198557  mov     eax, [rcx+4]
0x14019855a  test    eax, eax
0x14019855c  jnz     short loc_1401985CD
0x14019855e  cmp     [rbx+14h], eax
0x140198561  jz      short loc_140198581
0x140198563  xor     r8d, r8d
0x140198566  mov     dl, r13b
0x140198569  mov     rcx, rbx
0x14019856c  call    BLFlushBatchOpContextEx
0x140198571  mov     r10d, [rsp+78h+arg_10]
0x140198579  mov     r11, [rsp+78h+Src]
0x140198581  mov     eax, [rbx+8]
0x140198584  and     eax, 5
0x140198587  cmp     al, 5
0x140198589  jz      short loc_14019859A
0x14019858b  mov     eax, [rbx+8]
0x14019858e  and     eax, r12d
0x140198591  cmp     al, r12b
0x140198594  jnz     loc_14019871B
0x14019859a  mov     rax, [rdi]
0x14019859d  mov     esi, r10d
0x1401985a0  mov     rax, [rax+20h]
0x1401985a4  call    _guard_dispatch_icall
0x1401985a9  mov     rdx, [rsp+78h+Src]; Src
0x1401985b1  mov     r8d, esi; Size
0x1401985b4  mov     rcx, rbp; void *
0x1401985b7  call    memmove
0x1401985bc  mov     rax, [rdi]
0x1401985bf  mov     rax, [rax+28h]
0x1401985c3  call    _guard_dispatch_icall
0x1401985c8  jmp     loc_14019872C
0x1401985cd  mov     r8, [rbx+20h]
0x1401985d1  mov     esi, [r8+8]
0x1401985d5  cmp     esi, [r8+0Ch]
0x1401985d9  jb      loc_14019869D
0x1401985df  xor     esi, esi
0x1401985e1  cmp     [rbx+10h], eax
0x1401985e4  jb      short loc_1401985FD
0x1401985e6  xor     r8d, r8d
0x1401985e9  mov     dl, r13b
0x1401985ec  mov     rcx, rbx
0x1401985ef  call    BLFlushBatchOpContextEx
0x1401985f4  lea     r8, [rbx+38h]
0x1401985f8  jmp     loc_14019868D
0x1401985fd  add     rcx, 40h ; '@'; Lookaside
0x140198601  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140198608  nop     dword ptr [rax+rax+00h]
0x14019860d  mov     r8, rax
0x140198610  test    rax, rax
0x140198613  jz      short loc_1401985E6
0x140198615  mov     [rax], rsi
0x140198618  mov     [rax+8], esi
0x14019861b  mov     rax, [rdi]
0x14019861e  mov     ecx, [rax+8]
0x140198621  lea     rax, [r8+18h]
0x140198625  mov     [r8+10h], rax
0x140198629  mov     [r8+0Ch], ecx
0x14019862d  mov     rax, [rbx+20h]
0x140198631  mov     [rax], r8
0x140198634  mov     rdx, [rdi]
0x140198637  add     [rbx+10h], r13d
0x14019863b  mov     [rbx+20h], r8
0x14019863f  cmp     [rdx+1], r13b
0x140198643  jnz     short loc_14019868D
0x140198645  mov     ecx, [rbx+0Ch]
0x140198648  xor     eax, eax
0x14019864a  or      r10d, 0FFFFFFFFh
0x14019864e  cmp     ecx, r10d
0x140198651  jz      short loc_140198664
0x140198653  mov     rdx, [rdx+18h]
0x140198657  test    rdx, rdx
0x14019865a  jz      short loc_140198664
0x14019865c  lea     rcx, [rcx+rcx*4]
0x140198660  lea     rax, [rdx+rcx*4]
0x140198664  lock add [rax+0Ch], r13w
0x14019866a  mov     r9d, [rbx+0Ch]
0x14019866e  xor     ecx, ecx
0x140198670  cmp     r9d, r10d
0x140198673  jz      short loc_140198689
0x140198675  mov     rax, [rdi]
0x140198678  mov     rdx, [rax+18h]
0x14019867c  test    rdx, rdx
0x14019867f  jz      short loc_140198689
0x140198681  lea     rcx, [r9+r9*4]
0x140198685  lea     rcx, [rdx+rcx*4]
0x140198689  lock add [rcx], r13d
0x14019868d  mov     r11, [rsp+78h+Src]
0x140198695  mov     r10d, [rsp+78h+arg_10]
0x14019869d  add     [rbx+14h], r13d
0x1401986a1  add     [r8+8], r13d
0x1401986a5  mov     rcx, [rdi]
0x1401986a8  cmp     [rcx+1], r13b
0x1401986ac  jnz     short loc_1401986F6
0x1401986ae  mov     r9d, [rbx+0Ch]
0x1401986b2  xor     eax, eax
0x1401986b4  cmp     r9d, 0FFFFFFFFh
0x1401986b8  jz      short loc_1401986CB
0x1401986ba  mov     rdx, [rcx+18h]
0x1401986be  test    rdx, rdx
0x1401986c1  jz      short loc_1401986CB
0x1401986c3  lea     rcx, [r9+r9*4]
0x1401986c7  lea     rax, [rdx+rcx*4]
0x1401986cb  lock add [rax+0Eh], r13w
0x1401986d1  mov     r9d, [rbx+0Ch]
0x1401986d5  xor     ecx, ecx
0x1401986d7  cmp     r9d, 0FFFFFFFFh
0x1401986db  jz      short loc_1401986F1
0x1401986dd  mov     rax, [rdi]
0x1401986e0  mov     rdx, [rax+18h]
0x1401986e4  test    rdx, rdx
0x1401986e7  jz      short loc_1401986F1
0x1401986e9  lea     rcx, [r9+r9*4]
0x1401986ed  lea     rcx, [rdx+rcx*4]
0x1401986f1  lock add [rcx+4], r13d
0x1401986f6  mov     rcx, [r8+10h]
0x1401986fa  mov     eax, esi
0x1401986fc  lea     rdx, [rax+rax*2]
0x140198700  mov     eax, r10d
0x140198703  mov     [rcx+rdx*8], rbp
0x140198707  shl     eax, 4
0x14019870a  or      eax, r13d
0x14019870d  mov     [rcx+rdx*8+8], r11
0x140198712  mov     [rcx+rdx*8+10h], eax
0x140198716  mov     esi, r10d
0x140198719  jmp     short loc_14019872C
0x14019871b  mov     r8d, r10d; Size
0x14019871e  mov     rdx, r11; Src
0x140198721  mov     rcx, rbp; void *
0x140198724  mov     esi, r10d
0x140198727  call    memmove
0x14019872c  mov     r15, [r15]
0x14019872f  add     rbp, rsi
0x140198732  test    r15, r15
0x140198735  jnz     loc_1401984F9
0x14019873b  mov     r12, [rsp+78h+var_48]
0x140198740  lea     edi, [r15+6]
0x140198744  mov     r13, [rsp+78h+var_40]
0x140198749  mov     r8b, 1
0x14019874c  xor     edx, edx
0x14019874e  mov     rcx, rbx
0x140198751  call    BLFlushBatchOpContextEx
0x140198756  mov     edx, r13d
0x140198759  mov     qword ptr [r14], 0
0x140198760  mov     eax, edx
0x140198762  mov     [r14+28h], r12d
0x140198766  mov     r8d, 0FFFh
0x14019876c  lea     rcx, [r12+0FFFh]
0x140198774  and     rax, r8
0x140198777  and     r13, 0FFFFFFFFFFFFF000h
0x14019877e  add     rcx, rax
0x140198781  mov     [r14+20h], r13
0x140198785  shr     rcx, 0Ch
0x140198789  xor     eax, eax
0x14019878b  add     cx, di
0x14019878e  mov     [r14+0Ah], ax
0x140198793  shl     cx, 3
0x140198797  and     edx, r8d
0x14019879a  mov     [r14+8], cx
0x14019879f  mov     rcx, r14; MemoryDescriptorList
0x1401987a2  mov     [r14+2Ch], edx
0x1401987a6  call    cs:__imp_MmBuildMdlForNonPagedPool
0x1401987ad  nop     dword ptr [rax+rax+00h]
0x1401987b2  mov     rbx, [rsp+78h+arg_0]
0x1401987ba  mov     rax, r14
0x1401987bd  add     rsp, 40h
0x1401987c1  pop     r15
0x1401987c3  pop     r14
0x1401987c5  pop     r13
0x1401987c7  pop     r12
0x1401987c9  pop     rdi
0x1401987ca  pop     rsi
0x1401987cb  pop     rbp
0x1401987cc  retn
```
