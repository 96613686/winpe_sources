# NvmeDeviceHierarchicalReset

- ea: `0x140082520`
- end: `0x140082791`
- name: `NvmeDeviceHierarchicalReset`
- size: `625`
- prototype: `__int64 __fastcall(PVOID DeferredContext, PSLIST_HEADER ListHead)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140082260`

## callees

- `0x140082520`
- `0x140082798`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14008258d`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14008258d`
- `ntoskrnl!IoQueueWorkItem` at `0x1400825e0`
- `ntoskrnl!IoQueueWorkItem` at `0x1400825e0`
- `ntoskrnl!KeWaitForSingleObject` at `0x14008265c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14008265c`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14008260f`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14008260f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400826c3`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400826c3`
- `ntoskrnl!ExQueryDepthSList` at `0x140082544`
- `ntoskrnl!ExQueryDepthSList` at `0x140082544`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x140082745`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x140082745`

## pseudocode

```c
char __fastcall NvmeDeviceHierarchicalReset(PVOID DeferredContext, PSLIST_HEADER ListHead)
{
  USHORT DepthSList; // ax
  char v5; // bp
  int v6; // r14d
  PSLIST_ENTRY v7; // rdi
  PSLIST_ENTRY v8; // rsi
  __int64 v9; // rax
  NTSTATUS v10; // edi
  bool v11; // zf
  __int64 v12; // rdx
  unsigned int v13; // ecx
  __int64 v14; // rdi
  unsigned int v15; // edx
  unsigned __int64 v16; // rsi
  signed __int32 v17; // ecx
  _QWORD *v18; // rcx
  signed __int32 v20[8]; // [rsp+0h] [rbp-88h] BYREF
  __int128 v21; // [rsp+30h] [rbp-58h]
  union _LARGE_INTEGER Timeout; // [rsp+A0h] [rbp+18h] BYREF

  DepthSList = ExQueryDepthSList(ListHead);
  Timeout.QuadPart = 0;
  if ( DepthSList )
  {
    v5 = 0;
    v6 = 0;
    *(_DWORD *)(*(_QWORD *)(*((_QWORD *)DeferredContext + 164) + 32LL) + 48LL) = DepthSList;
    *(_DWORD *)(*(_QWORD *)(*((_QWORD *)DeferredContext + 164) + 32LL) + 52LL) = 0;
    v7 = ExpInterlockedPopEntrySList(ListHead);
    if ( v7 )
    {
      do
      {
        v8 = v7 - 33;
        v7[-26].Next = (_SLIST_ENTRY *)((unsigned __int64)v7[-26].Next & ~0x80uLL);
        if ( _InterlockedCompareExchange((volatile signed __int32 *)(*((_QWORD *)&v7[-2].Next + 1) + 8LL), 1, 0) )
        {
          _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(*((_QWORD *)DeferredContext + 164) + 32LL) + 48LL));
          ExReleaseRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)&v8[7].Next + 1));
        }
        else
        {
          IoQueueWorkItem(
            **((PIO_WORKITEM **)&v8[31].Next + 1),
            NvmeNamespaceResetRecoveryRoutine,
            DelayedWorkQueue,
            &v7[-33]);
          ++*(_DWORD *)(*((_QWORD *)&v8[31].Next + 1) + 12LL);
          ++v6;
        }
        v7 = v7->Next;
      }
      while ( v7 );
      if ( v6 )
      {
        v9 = *((_QWORD *)DeferredContext + 164);
        Timeout.QuadPart = -300000000;
        v10 = KeWaitForSingleObject((PVOID)(*(_QWORD *)(v9 + 32) + 24LL), Executive, 0, 0, &Timeout);
        if ( v10 != 258 )
        {
          if ( *(_DWORD *)(*(_QWORD *)(*((_QWORD *)DeferredContext + 164) + 32LL) + 52LL) )
            v5 = NvmeControllerResetRecovery(DeferredContext);
          else
            v5 = 1;
        }
        if ( (*((_BYTE *)DeferredContext + 1384) & 0x10) != 0 )
        {
          v11 = *(_DWORD *)DeferredContext == 1314276178;
          v21 = 0;
          LODWORD(v21) = v10;
          BYTE4(v21) = v5;
          if ( v11 )
          {
            v12 = *(_QWORD *)(*((_QWORD *)DeferredContext + 174) + 8LL * KeGetCurrentProcessorNumberEx(0));
            v13 = *(_DWORD *)(v12 + 12);
            _InterlockedOr(v20, 0);
            if ( v13 )
            {
              v14 = v12 + 64;
              if ( v12 != -64 )
              {
                v15 = _InterlockedIncrement((volatile signed __int32 *)v12) % v13;
                v16 = (unsigned __int64)v15 << 6;
                v17 = v15;
                if ( (*((_DWORD *)DeferredContext + 340) & 1) != 0 )
                  v17 = _InterlockedIncrement((volatile signed __int32 *)DeferredContext + 352);
                *(_DWORD *)(v16 + v14 + 4) = v17;
                *(_DWORD *)(v16 + v14) = 65538;
                v18 = (_QWORD *)(v16 + v14 + 8);
                if ( (*((_DWORD *)DeferredContext + 340) & 2) != 0 )
                  KeQuerySystemTimePrecise(v18, 2);
                else
                  *v18 = MEMORY[0xFFFFF78000000014];
                *(_OWORD *)(v16 + v14 + 16) = v21;
                *(_OWORD *)(v16 + v14 + 32) = 0;
              }
            }
          }
        }
      }
    }
    LOBYTE(DepthSList) = v5;
  }
  return DepthSList;
}

```

## disassembly

```asm
0x140082520  mov     [rsp+arg_0], rbx
0x140082525  mov     [rsp+arg_8], rbp
0x14008252a  push    rsi
0x14008252b  push    rdi
0x14008252c  push    r12
0x14008252e  push    r14
0x140082530  push    r15
0x140082532  sub     rsp, 60h
0x140082536  mov     rbx, rcx
0x140082539  movaps  [rsp+88h+var_38], xmm6
0x14008253e  mov     rcx, rdx; SListHead
0x140082541  mov     rdi, rdx
0x140082544  call    cs:__imp_ExQueryDepthSList
0x14008254b  nop     dword ptr [rax+rax+00h]
0x140082550  xor     r15d, r15d
0x140082553  mov     qword ptr [rsp+88h+arg_10], r15
0x14008255b  test    ax, ax
0x14008255e  jz      loc_140082772
0x140082564  movzx   edx, ax
0x140082567  mov     bpl, r15b
0x14008256a  mov     rax, [rbx+520h]
0x140082571  mov     r14d, r15d
0x140082574  mov     rcx, [rax+20h]
0x140082578  mov     [rcx+30h], edx
0x14008257b  mov     rax, [rbx+520h]
0x140082582  mov     rcx, [rax+20h]
0x140082586  mov     [rcx+34h], r15d
0x14008258a  mov     rcx, rdi; ListHead
0x14008258d  call    cs:__imp_ExpInterlockedPopEntrySList
0x140082594  nop     dword ptr [rax+rax+00h]
0x140082599  mov     rdi, rax
0x14008259c  test    rax, rax
0x14008259f  jz      loc_14008276F
0x1400825a5  mov     r12d, 1
0x1400825ab  lea     rsi, [rdi-210h]
0x1400825b2  btr     qword ptr [rsi+70h], 7
0x1400825b8  mov     rcx, [rsi+1F8h]
0x1400825bf  xor     eax, eax
0x1400825c1  lock cmpxchg [rcx+8], r12d
0x1400825c7  jnz     short loc_1400825FC
0x1400825c9  mov     rcx, [rsi+1F8h]
0x1400825d0  lea     rdx, NvmeNamespaceResetRecoveryRoutine; WorkerRoutine
0x1400825d7  mov     r9, rsi; Context
0x1400825da  mov     r8d, r12d; QueueType
0x1400825dd  mov     rcx, [rcx]; IoWorkItem
0x1400825e0  call    cs:__imp_IoQueueWorkItem
0x1400825e7  nop     dword ptr [rax+rax+00h]
0x1400825ec  mov     rax, [rsi+1F8h]
0x1400825f3  add     [rax+0Ch], r12d
0x1400825f7  add     r14d, r12d
0x1400825fa  jmp     short loc_14008261B
0x1400825fc  mov     rax, [rbx+520h]
0x140082603  mov     rcx, [rax+20h]
0x140082607  lock dec dword ptr [rcx+30h]
0x14008260b  mov     rcx, [rsi+78h]; RunRefCacheAware
0x14008260f  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140082616  nop     dword ptr [rax+rax+00h]
0x14008261b  mov     rdi, [rdi]
0x14008261e  test    rdi, rdi
0x140082621  jnz     short loc_1400825AB
0x140082623  test    r14d, r14d
0x140082626  jz      loc_14008276F
0x14008262c  mov     rax, [rbx+520h]
0x140082633  xor     r9d, r9d; Alertable
0x140082636  mov     qword ptr [rsp+88h+arg_10], 0FFFFFFFFEE1E5D00h
0x140082642  xor     r8d, r8d; WaitMode
0x140082645  xor     edx, edx; WaitReason
0x140082647  mov     rcx, [rax+20h]
0x14008264b  lea     rax, [rsp+88h+arg_10]
0x140082653  add     rcx, 18h; Object
0x140082657  mov     [rsp+88h+Timeout], rax; Timeout
0x14008265c  call    cs:__imp_KeWaitForSingleObject
0x140082663  nop     dword ptr [rax+rax+00h]
0x140082668  mov     edi, eax
0x14008266a  cmp     eax, 102h
0x14008266f  jz      short loc_140082697
0x140082671  mov     rcx, [rbx+520h]
0x140082678  mov     rdx, [rcx+20h]
0x14008267c  cmp     [rdx+34h], r15d
0x140082680  jnz     short loc_140082687
0x140082682  mov     bpl, r12b
0x140082685  jmp     short loc_140082697
0x140082687  mov     edx, 3
0x14008268c  mov     rcx, rbx; DeferredContext
0x14008268f  call    NvmeControllerResetRecovery
0x140082694  mov     bpl, al
0x140082697  test    byte ptr [rbx+568h], 10h
0x14008269e  jz      loc_14008276F
0x1400826a4  cmp     dword ptr [rbx], 4E564352h
0x1400826aa  xorps   xmm6, xmm6
0x1400826ad  movups  [rsp+88h+var_58], xmm6
0x1400826b2  mov     dword ptr [rsp+88h+var_58], edi
0x1400826b6  mov     byte ptr [rsp+88h+var_58+4], bpl
0x1400826bb  jnz     loc_14008276F
0x1400826c1  xor     ecx, ecx; ProcNumber
0x1400826c3  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400826ca  nop     dword ptr [rax+rax+00h]
0x1400826cf  mov     ecx, eax
0x1400826d1  mov     rax, [rbx+570h]
0x1400826d8  mov     rdx, [rax+rcx*8]
0x1400826dc  mov     ecx, [rdx+0Ch]
0x1400826df  lock or [rsp+88h+var_88], r15d
0x1400826e4  test    ecx, ecx
0x1400826e6  jz      loc_14008276F
0x1400826ec  lea     rdi, [rdx+40h]
0x1400826f0  test    rdi, rdi
0x1400826f3  jz      short loc_14008276F
0x1400826f5  mov     eax, r12d
0x1400826f8  lock xadd [rdx], eax
0x1400826fc  add     eax, r12d
0x1400826ff  xor     edx, edx
0x140082701  div     ecx
0x140082703  mov     eax, [rbx+550h]
0x140082709  mov     esi, edx
0x14008270b  shl     rsi, 6
0x14008270f  mov     ecx, edx
0x140082711  test    r12b, al
0x140082714  jz      short loc_140082724
0x140082716  mov     ecx, r12d
0x140082719  lock xadd [rbx+580h], ecx
0x140082721  add     ecx, r12d
0x140082724  mov     [rsi+rdi+4], ecx
0x140082728  mov     edx, 2
0x14008272d  lea     rcx, [rdi+8]
0x140082731  mov     dword ptr [rsi+rdi], 10002h
0x140082738  mov     eax, [rbx+550h]
0x14008273e  add     rcx, rsi
0x140082741  test    dl, al
0x140082743  jz      short loc_140082753
0x140082745  call    cs:__imp_KeQuerySystemTimePrecise
0x14008274c  nop     dword ptr [rax+rax+00h]
0x140082751  jmp     short loc_140082760
0x140082753  mov     rax, ds:0FFFFF78000000014h
0x14008275d  mov     [rcx], rax
0x140082760  movups  xmm0, [rsp+88h+var_58]
0x140082765  movups  xmmword ptr [rsi+rdi+10h], xmm0
0x14008276a  movups  xmmword ptr [rsi+rdi+20h], xmm6
0x14008276f  mov     al, bpl
0x140082772  movaps  xmm6, [rsp+88h+var_38]
0x140082777  lea     r11, [rsp+88h+var_28]
0x14008277c  mov     rbx, [r11+30h]
0x140082780  mov     rbp, [r11+38h]
0x140082784  mov     rsp, r11
0x140082787  pop     r15
0x140082789  pop     r14
0x14008278b  pop     r12
0x14008278d  pop     rdi
0x14008278e  pop     rsi
0x14008278f  retn
```
