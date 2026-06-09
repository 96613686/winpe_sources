# Srv2ContinueCompoundedReceive

- ea: `0x140009190`
- end: `0x140009751`
- name: `Srv2ContinueCompoundedReceive`
- size: `1473`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140008410`

## callees

- `0x140005470`
- `0x140008190`
- `0x140009190`
- `0x14000a560`
- `0x14000ab3c`
- `0x14002019c`
- `0x140022690`
- `0x140022958`
- `0x1400384d0`
- `0x140038680`
- `0x140038980`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400096bc`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400096bc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009306`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009410`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009306`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009410`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140009641`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140009641`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009364`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000945a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009607`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009364`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000945a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009607`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400091ee`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400091ee`
- `ntoskrnl!EtwActivityIdControl` at `0x1400095c8`
- `ntoskrnl!EtwActivityIdControl` at `0x1400095c8`
- `HAL!KeQueryPerformanceCounter` at `0x1400092b9`
- `HAL!KeQueryPerformanceCounter` at `0x1400095a8`
- `HAL!KeQueryPerformanceCounter` at `0x1400092b9`
- `HAL!KeQueryPerformanceCounter` at `0x1400095a8`
- `TDI!TdiCopyMdlToBuffer` at `0x140009549`
- `TDI!TdiCopyMdlToBuffer` at `0x140009549`

## pseudocode

```c
__int64 __fastcall Srv2ContinueCompoundedReceive(__int64 a1)
{
  int LockArray_high; // edi
  __int64 v3; // rsi
  int v4; // r15d
  int v5; // r12d
  struct _LOOKASIDE_LIST_EX *v6; // rbx
  char *v7; // rbx
  __int64 v8; // rax
  bool v9; // zf
  LARGE_INTEGER PerformanceCounter; // rax
  KIRQL v11; // al
  _QWORD *v12; // rdx
  int v13; // edi
  volatile signed __int64 *v14; // rcx
  KIRQL v15; // al
  __int64 v16; // rdx
  _QWORD *v17; // r8
  __int64 v18; // rax
  char *v19; // rsi
  __int64 v20; // r15
  __int64 v21; // rdi
  __int64 v22; // rcx
  PVOID v23; // r10
  __int64 v24; // rcx
  ULONG v25; // r8d
  ULONG v26; // edx
  ULONG DestinationBufferSize; // eax
  ULONG v28; // r8d
  struct _MDL *v29; // rcx
  unsigned int v30; // ebx
  __int16 v31; // dx
  __int64 v33; // rcx
  struct _LOOKASIDE_LIST_EX *v34; // rdi
  int v35; // r8d
  ULONG BytesCopied; // [rsp+60h] [rbp+8h] BYREF

  LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
  v3 = *(_QWORD *)(a1 + 96);
  v4 = *(_DWORD *)(a1 + 408);
  v5 = *(_DWORD *)(a1 + 400);
  v6 = (struct _LOOKASIDE_LIST_EX *)((char *)qword_140058148 + 128 * (unsigned __int64)(unsigned __int16)LockArray_high);
  if ( !LOBYTE(v6[3].L.Depth) )
    PplpLazyInitializeLookasideList(qword_140058148, &v6[2]);
  v7 = (char *)ExAllocateFromLookasideListEx(v6 + 2);
  if ( !v7 )
    goto LABEL_37;
  v8 = *(_QWORD *)(v3 + 64);
  *(_QWORD *)v7 = 1;
  *((_DWORD *)v7 + 2) = 5;
  *((_DWORD *)v7 + 3) = 220;
  *((_WORD *)v7 + 8) = 1888;
  *((_QWORD *)v7 + 6) = 0;
  *((_QWORD *)v7 + 7) = v7;
  *((_QWORD *)v7 + 8) = v8;
  *((_QWORD *)v7 + 11) = Srv2ProcPostToCallback;
  *((_DWORD *)v7 + 18) = 0;
  *((_QWORD *)v7 + 12) = v3;
  v9 = byte_140058150 == 0;
  *((_QWORD *)v7 + 47) = MEMORY[0xFFFFF78000000014];
  if ( v9 )
    *((_QWORD *)v7 + 48) = 0;
  else
    *((LARGE_INTEGER *)v7 + 48) = KeQueryPerformanceCounter(0);
  *((_DWORD *)v7 + 98) = *(_DWORD *)(v3 + 504);
  *((_WORD *)v7 + 198) = LockArray_high;
  memset(v7 + 400, 0, 0xA0u);
  *((_WORD *)v7 + 356) = 0;
  v7[714] = 0;
  memset(v7 + 584, 0, 0x80u);
  PerformanceCounter = KeQueryPerformanceCounter(0);
  *((LARGE_INTEGER *)v7 + 90) = PerformanceCounter;
  *((LARGE_INTEGER *)v7 + 91) = PerformanceCounter;
  *((_QWORD *)v7 + 92) = MEMORY[0xFFFFF78000000014];
  *((_QWORD *)v7 + 94) = v7;
  if ( (Microsoft_Windows_SMBServerEnableBits & 8) != 0 )
  {
    EtwActivityIdControl(3u, (LPGUID)(v7 + 584));
    v7[600] = 1;
    if ( (Microsoft_Windows_SMBServerEnableBits & 8) != 0 )
      McTemplateK0x_EtwWriteTransfer(v33, &SMB2_EVENT_WORKITEM_START, v7 + 584, v7 + 584);
  }
  else
  {
    v7[600] = 0;
  }
  v11 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 184));
  if ( *(_DWORD *)(v3 + 12) != 220 )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 184), v11);
    v34 = (struct _LOOKASIDE_LIST_EX *)((char *)qword_140058148 + 128
                                                                * (unsigned __int64)*((unsigned __int16 *)v7 + 198));
    if ( !LOBYTE(v34[3].L.Depth) )
      PplpLazyInitializeLookasideList(qword_140058148, &v34[2]);
    ExFreeToLookasideListEx(v34 + 2, v7);
LABEL_37:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, &WPP_1f56813514af312e5a39176f5ad11993_Traceguids);
    }
    *(_BYTE *)(*(_QWORD *)(a1 + 416) + 474LL) = 1;
    return Srv2ProcPartialCompleteCompoundedReceive(*(_QWORD *)(a1 + 416));
  }
  v12 = *(_QWORD **)(v3 + 200);
  if ( *v12 != v3 + 192 )
    goto LABEL_46;
  *((_QWORD *)v7 + 13) = v3 + 192;
  *((_QWORD *)v7 + 14) = v12;
  *v12 = v7 + 104;
  *(_QWORD *)(v3 + 200) = v7 + 104;
  v13 = *(_DWORD *)(v3 + 208);
  *(_DWORD *)(v3 + 208) = v13 + 1;
  KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 184), v11);
  if ( !v13 && ((_InterlockedExchangeAdd64((volatile signed __int64 *)v3, 1u) + 2) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    __int2c();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 24, &WPP_1f56813514af312e5a39176f5ad11993_Traceguids, a1, v7);
  }
  v14 = *(volatile signed __int64 **)(a1 + 416);
  *(_BYTE *)(a1 + 475) = 0;
  *((_QWORD *)v7 + 52) = v14;
  if ( ((_InterlockedExchangeAdd64(v14, 1u) + 2) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    __int2c();
  *((_QWORD *)v7 + 53) = a1;
  if ( ((_InterlockedExchangeAdd64((volatile signed __int64 *)a1, 1u) + 2) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    __int2c();
  _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 416) + 452LL));
  v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(*(_QWORD *)(a1 + 416) + 80LL));
  v16 = *((_QWORD *)v7 + 52) + 432LL;
  v17 = *(_QWORD **)(*((_QWORD *)v7 + 52) + 440LL);
  if ( *v17 != v16 )
LABEL_46:
    __fastfail(3u);
  *((_QWORD *)v7 + 54) = v16;
  *((_QWORD *)v7 + 55) = v17;
  *v17 = v7 + 432;
  *(_QWORD *)(v16 + 8) = v7 + 432;
  KeReleaseSpinLock((PKSPIN_LOCK)(*(_QWORD *)(a1 + 416) + 80LL), v15);
  v18 = *((_QWORD *)v7 + 38);
  v19 = v7 + 128;
  *((_DWORD *)v7 + 100) = 65;
  BytesCopied = 0;
  *((_DWORD *)v7 + 102) = v4 - v5;
  *(_DWORD *)(v18 + 36) = 0;
  v20 = *((_QWORD *)v7 + 38);
  v21 = *((_QWORD *)v7 + 52);
  *((_QWORD *)v7 + 21) = *((_QWORD *)v7 + 15);
  *((_QWORD *)v7 + 19) = v7;
  *((_DWORD *)v7 + 33) = 0;
  *((_DWORD *)v7 + 44) = 0;
  *((_DWORD *)v7 + 32) = 64;
  *((_QWORD *)v7 + 17) = *(_QWORD *)(v20 + 56);
  *((_QWORD *)v7 + 18) = Smb2PostAfterValidatingMessageId;
  *((_QWORD *)v7 + 6) = Srv2ContinueContinueCompoundedReceive;
  v22 = *((_QWORD *)v7 + 17);
  if ( (*(_BYTE *)(v22 + 10) & 5) != 0 )
    v23 = *(PVOID *)(v22 + 24);
  else
    v23 = MmMapLockedPagesSpecifyCache((PMDL)v22, 0, MmCached, 0, 0, 0x40000010u);
  if ( v23 )
  {
    v24 = *(_QWORD *)(v21 + 456);
    if ( v24 )
    {
      v25 = *(_DWORD *)(v24 + 36);
      v26 = *(_DWORD *)(v21 + 464);
      if ( v26 < v25 )
      {
        DestinationBufferSize = *(_DWORD *)v19;
        v28 = v25 - v26;
        v29 = *(struct _MDL **)(v24 + 56);
        if ( *(_DWORD *)v19 >= v28 )
          DestinationBufferSize = v28;
        v30 = TdiCopyMdlToBuffer(v29, v26, v23, 0, DestinationBufferSize, &BytesCopied);
        *(_DWORD *)(v21 + 464) += BytesCopied;
        if ( v20 )
        {
          v31 = *(_WORD *)(*(_QWORD *)(v21 + 456) + 22LL);
          if ( v31 )
          {
            *(_WORD *)(v20 + 22) = v31;
            memmove(
              (void *)(v20 + 100),
              (const void *)(*(_QWORD *)(v21 + 456) + 100LL),
              16LL * *(unsigned __int16 *)(*(_QWORD *)(v21 + 456) + 22LL));
          }
        }
        return (*((__int64 (__fastcall **)(_QWORD, _QWORD, char *))v19 + 2))(v30, BytesCopied, v19);
      }
    }
    v35 = -1073741811;
  }
  else
  {
    v35 = -1073741670;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 25, &WPP_1f56813514af312e5a39176f5ad11993_Traceguids, v7, v35);
  }
  Srv2ProcPartialCompleteCompoundedReceive(*(_QWORD *)(a1 + 416));
  return Srv2CompleteWorkItem(v7, 3221226011LL);
}

```

## disassembly

```asm
0x140009190  mov     [rsp+arg_18], rbx
0x140009195  push    rbp
0x140009196  push    rsi
0x140009197  push    rdi
0x140009198  push    r12
0x14000919a  push    r15
0x14000919c  sub     rsp, 30h
0x1400091a0  mov     edi, gs:1A4h
0x1400091a8  mov     rbp, rcx
0x1400091ab  mov     rsi, [rcx+60h]
0x1400091af  mov     r15d, [rcx+198h]
0x1400091b6  mov     r12d, [rcx+190h]
0x1400091bd  mov     rcx, cs:qword_140058148
0x1400091c4  movzx   ebx, di
0x1400091c7  shl     rbx, 7
0x1400091cb  add     rbx, rcx
0x1400091ce  movzx   eax, byte ptr [rbx+130h]
0x1400091d5  test    al, al
0x1400091d7  jz      loc_140009696
0x1400091dd  mov     [rsp+58h+arg_8], r13
0x1400091e2  lea     rcx, [rbx+0C0h]; Lookaside
0x1400091e9  mov     [rsp+58h+arg_10], r14
0x1400091ee  call    cs:__imp_ExAllocateFromLookasideListEx
0x1400091f5  nop     dword ptr [rax+rax+00h]
0x1400091fa  mov     rbx, rax
0x1400091fd  test    rax, rax
0x140009200  jz      loc_14000964D
0x140009206  mov     rax, [rsi+40h]
0x14000920a  xor     ecx, ecx; PerformanceFrequency
0x14000920c  mov     qword ptr [rbx], 1
0x140009213  mov     dword ptr [rbx+8], 5
0x14000921a  mov     dword ptr [rbx+0Ch], 0DCh
0x140009221  mov     word ptr [rbx+10h], 760h
0x140009227  mov     [rbx+30h], rcx
0x14000922b  mov     [rbx+38h], rbx
0x14000922f  mov     [rbx+40h], rax
0x140009233  lea     rax, Srv2ProcPostToCallback
0x14000923a  mov     [rbx+58h], rax
0x14000923e  mov     [rbx+48h], ecx
0x140009241  mov     [rbx+60h], rsi
0x140009245  mov     rax, ds:0FFFFF78000000014h
0x14000924f  cmp     cs:byte_140058150, cl
0x140009255  mov     [rbx+178h], rax
0x14000925c  jnz     loc_1400095A8
0x140009262  mov     [rbx+180h], rcx
0x140009269  mov     eax, [rsi+1F8h]
0x14000926f  lea     rcx, [rbx+190h]; void *
0x140009276  xor     edx, edx; Val
0x140009278  mov     [rbx+188h], eax
0x14000927e  mov     r8d, 0A0h; Size
0x140009284  mov     [rbx+18Ch], di
0x14000928b  call    memset
0x140009290  lea     rdi, [rbx+248h]
0x140009297  xor     edx, edx; Val
0x140009299  mov     rcx, rdi; void *
0x14000929c  mov     word ptr [rdi+80h], 0
0x1400092a5  mov     r8d, 80h; Size
0x1400092ab  mov     byte ptr [rdi+82h], 0
0x1400092b2  call    memset
0x1400092b7  xor     ecx, ecx; PerformanceFrequency
0x1400092b9  call    cs:__imp_KeQueryPerformanceCounter
0x1400092c0  nop     dword ptr [rax+rax+00h]
0x1400092c5  mov     [rdi+88h], rax
0x1400092cc  mov     [rdi+90h], rax
0x1400092d3  mov     rax, 0FFFFF78000000014h
0x1400092dd  mov     rax, [rax]
0x1400092e0  mov     [rdi+98h], rax
0x1400092e7  mov     [rdi+0A8h], rbx
0x1400092ee  test    cs:Microsoft_Windows_SMBServerEnableBits, 8
0x1400092f5  jnz     loc_1400095C0
0x1400092fb  mov     byte ptr [rdi+10h], 0
0x1400092ff  lea     rcx, [rsi+0B8h]; SpinLock
0x140009306  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000930d  nop     dword ptr [rax+rax+00h]
0x140009312  cmp     dword ptr [rsi+0Ch], 0DCh
0x140009319  movzx   r8d, al
0x14000931d  jnz     loc_1400095FC
0x140009323  lea     rcx, [rsi+0C0h]
0x14000932a  mov     rdx, [rcx+8]
0x14000932e  cmp     [rdx], rcx
0x140009331  jnz     loc_14000974A
0x140009337  mov     [rbx+68h], rcx
0x14000933b  lea     rax, [rbx+68h]
0x14000933f  mov     [rax+8], rdx
0x140009343  mov     [rdx], rax
0x140009346  movzx   edx, r8b; NewIrql
0x14000934a  mov     [rcx+8], rax
0x14000934e  lea     rcx, [rsi+0B8h]; SpinLock
0x140009355  mov     edi, [rsi+0D0h]
0x14000935b  lea     eax, [rdi+1]
0x14000935e  mov     [rsi+0D0h], eax
0x140009364  call    cs:__imp_KeReleaseSpinLock
0x14000936b  nop     dword ptr [rax+rax+00h]
0x140009370  test    edi, edi
0x140009372  jnz     short loc_14000938C
0x140009374  mov     eax, 1
0x140009379  lock xadd [rsi], rax
0x14000937e  add     rax, 2
0x140009382  test    rax, 0FFFFFFFFFFFFFFFEh
0x140009388  jnz     short loc_14000938C
0x14000938a  int     2Ch; Windows NT - assertion failure
0x14000938c  mov     rcx, cs:WPP_GLOBAL_Control
0x140009393  lea     r14, WPP_GLOBAL_Control
0x14000939a  cmp     rcx, r14
0x14000939d  jz      short loc_1400093AA
0x14000939f  mov     eax, [rcx+2Ch]
0x1400093a2  test    al, 1
0x1400093a4  jnz     loc_1400096E1
0x1400093aa  mov     rcx, [rbp+1A0h]
0x1400093b1  mov     eax, 1
0x1400093b6  mov     byte ptr [rbp+1DBh], 0
0x1400093bd  mov     [rbx+1A0h], rcx
0x1400093c4  lock xadd [rcx], rax
0x1400093c9  add     rax, 2
0x1400093cd  test    rax, 0FFFFFFFFFFFFFFFEh
0x1400093d3  jnz     short loc_1400093D7
0x1400093d5  int     2Ch; Windows NT - assertion failure
0x1400093d7  mov     [rbx+1A8h], rbp
0x1400093de  mov     eax, 1
0x1400093e3  lock xadd [rbp+0], rax
0x1400093e9  add     rax, 2
0x1400093ed  test    rax, 0FFFFFFFFFFFFFFFEh
0x1400093f3  jnz     short loc_1400093F7
0x1400093f5  int     2Ch; Windows NT - assertion failure
0x1400093f7  mov     rax, [rbp+1A0h]
0x1400093fe  lock inc dword ptr [rax+1C4h]
0x140009405  mov     rcx, [rbp+1A0h]
0x14000940c  add     rcx, 50h ; 'P'; SpinLock
0x140009410  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140009417  nop     dword ptr [rax+rax+00h]
0x14000941c  mov     rdx, [rbx+1A0h]
0x140009423  add     rdx, 1B0h
0x14000942a  mov     r8, [rdx+8]
0x14000942e  cmp     [r8], rdx
0x140009431  jnz     loc_14000974A
0x140009437  lea     rcx, [rbx+1B0h]
0x14000943e  mov     [rcx], rdx
0x140009441  mov     [rcx+8], r8
0x140009445  mov     [r8], rcx
0x140009448  mov     [rdx+8], rcx
0x14000944c  movzx   edx, al; NewIrql
0x14000944f  mov     rcx, [rbp+1A0h]
0x140009456  add     rcx, 50h ; 'P'; SpinLock
0x14000945a  call    cs:__imp_KeReleaseSpinLock
0x140009461  nop     dword ptr [rax+rax+00h]
0x140009466  mov     rax, [rbx+130h]
0x14000946d  lea     rsi, [rbx+80h]
0x140009474  xor     edx, edx; AccessMode
0x140009476  mov     dword ptr [rbx+190h], 41h ; 'A'
0x140009480  sub     r15d, r12d
0x140009483  mov     [rsp+58h+arg_0], edx
0x140009487  mov     [rbx+198h], r15d
0x14000948e  mov     [rax+24h], edx
0x140009491  mov     rax, [rbx+78h]
0x140009495  mov     r15, [rbx+130h]
0x14000949c  mov     rdi, [rbx+1A0h]
0x1400094a3  mov     [rbx+0A8h], rax
0x1400094aa  mov     [rbx+98h], rbx
0x1400094b1  mov     [rbx+84h], edx
0x1400094b7  mov     [rbx+0B0h], edx
0x1400094bd  mov     dword ptr [rsi], 40h ; '@'
0x1400094c3  mov     rax, [r15+38h]
0x1400094c7  mov     [rbx+88h], rax
0x1400094ce  lea     rax, Smb2PostAfterValidatingMessageId
0x1400094d5  mov     [rbx+90h], rax
0x1400094dc  lea     rax, Srv2ContinueContinueCompoundedReceive
0x1400094e3  mov     [rbx+30h], rax
0x1400094e7  mov     rcx, [rsi+8]; MemoryDescriptorList
0x1400094eb  test    byte ptr [rcx+0Ah], 5
0x1400094ef  jz      loc_1400096A7
0x1400094f5  mov     r10, [rcx+18h]
0x1400094f9  test    r10, r10
0x1400094fc  jz      loc_14000970D
0x140009502  mov     rcx, [rdi+1C8h]
0x140009509  test    rcx, rcx
0x14000950c  jz      loc_14000973F
0x140009512  mov     r8d, [rcx+24h]
0x140009516  mov     edx, [rdi+1D0h]; SourceOffset
0x14000951c  cmp     edx, r8d
0x14000951f  jnb     loc_14000973F
0x140009525  mov     eax, [rsi]
0x140009527  sub     r8d, edx
0x14000952a  mov     rcx, [rcx+38h]; SourceMdlChain
0x14000952e  cmp     eax, r8d
0x140009531  cmovnb  eax, r8d
0x140009535  lea     r8, [rsp+58h+arg_0]
0x14000953a  mov     [rsp+58h+BytesCopied], r8; BytesCopied
0x14000953f  xor     r9d, r9d; DestinationOffset
0x140009542  mov     r8, r10; DestinationBuffer
0x140009545  mov     [rsp+58h+DestinationBufferSize], eax; DestinationBufferSize
0x140009549  call    cs:__imp_TdiCopyMdlToBuffer
0x140009550  nop     dword ptr [rax+rax+00h]
0x140009555  mov     ecx, [rsp+58h+arg_0]
0x140009559  mov     ebx, eax
0x14000955b  add     [rdi+1D0h], ecx
0x140009561  test    r15, r15
0x140009564  jz      short loc_14000957A
0x140009566  mov     rcx, [rdi+1C8h]
0x14000956d  movzx   edx, word ptr [rcx+16h]
0x140009571  test    dx, dx
0x140009574  jnz     loc_140009718
0x14000957a  mov     rax, [rsi+10h]
0x14000957e  mov     r8, rsi
0x140009581  mov     edx, [rsp+58h+arg_0]
0x140009585  mov     ecx, ebx
0x140009587  call    _guard_dispatch_icall
0x14000958c  mov     r14, [rsp+58h+arg_10]
0x140009591  mov     r13, [rsp+58h+arg_8]
0x140009596  mov     rbx, [rsp+58h+arg_18]
0x14000959b  add     rsp, 30h
0x14000959f  pop     r15
0x1400095a1  pop     r12
0x1400095a3  pop     rdi
0x1400095a4  pop     rsi
0x1400095a5  pop     rbp
0x1400095a6  retn
0x1400095a8  call    cs:__imp_KeQueryPerformanceCounter
0x1400095af  nop     dword ptr [rax+rax+00h]
0x1400095b4  mov     [rbx+180h], rax
0x1400095bb  jmp     loc_140009269
0x1400095c0  mov     rdx, rdi; ActivityId
0x1400095c3  mov     ecx, 3; ControlCode
0x1400095c8  call    cs:__imp_EtwActivityIdControl
0x1400095cf  nop     dword ptr [rax+rax+00h]
0x1400095d4  mov     byte ptr [rdi+10h], 1
0x1400095d8  test    cs:Microsoft_Windows_SMBServerEnableBits, 8
0x1400095df  jz      loc_1400092FF
0x1400095e5  mov     r9, rdi
0x1400095e8  lea     rdx, SMB2_EVENT_WORKITEM_START
0x1400095ef  mov     r8, rdi
0x1400095f2  call    McTemplateK0x_EtwWriteTransfer
0x1400095f7  jmp     loc_1400092FF
0x1400095fc  movzx   edx, r8b; NewIrql
0x140009600  lea     rcx, [rsi+0B8h]; SpinLock
0x140009607  call    cs:__imp_KeReleaseSpinLock
0x14000960e  nop     dword ptr [rax+rax+00h]
0x140009613  movzx   edi, word ptr [rbx+18Ch]
0x14000961a  mov     rcx, cs:qword_140058148
0x140009621  shl     rdi, 7
0x140009625  add     rdi, rcx
0x140009628  movzx   eax, byte ptr [rdi+130h]
0x14000962f  test    al, al
0x140009631  jz      loc_1400096D0
0x140009637  mov     rdx, rbx; Entry
0x14000963a  lea     rcx, [rdi+0C0h]; Lookaside
0x140009641  call    cs:__imp_ExFreeToLookasideListEx
0x140009648  nop     dword ptr [rax+rax+00h]
0x14000964d  mov     rcx, cs:WPP_GLOBAL_Control
0x140009654  lea     r14, WPP_GLOBAL_Control
0x14000965b  cmp     rcx, r14
0x14000965e  jz      loc_14003ABA9
0x140009664  test    dword ptr [rcx+2Ch], 200h
0x14000966b  jz      loc_14003ABA9
0x140009671  cmp     byte ptr [rcx+29h], 1
0x140009675  jb      loc_14003ABA9
0x14000967b  mov     rcx, [rcx+18h]
0x14000967f  lea     r8, WPP_1f56813514af312e5a39176f5ad11993_Traceguids
0x140009686  mov     edx, 17h
0x14000968b  call    WPP_SF_
0x140009690  nop
0x140009691  jmp     loc_14003ABA9
0x140009696  lea     rdx, [rbx+0C0h]
0x14000969d  call    PplpLazyInitializeLookasideList
0x1400096a2  jmp     loc_1400091DD
0x1400096a7  mov     dword ptr [rsp+58h+BytesCopied], 40000010h; Priority
0x1400096af  xor     r9d, r9d; RequestedAddress
0x1400096b2  mov     r8d, 1; CacheType
0x1400096b8  mov     [rsp+58h+DestinationBufferSize], edx; BugCheckOnFailure
0x1400096bc  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400096c3  nop     dword ptr [rax+rax+00h]
0x1400096c8  mov     r10, rax
0x1400096cb  jmp     loc_1400094F9
0x1400096d0  lea     rdx, [rdi+0C0h]
0x1400096d7  call    PplpLazyInitializeLookasideList
0x1400096dc  jmp     loc_140009637
0x1400096e1  cmp     byte ptr [rcx+29h], 2
0x1400096e5  jb      loc_1400093AA
0x1400096eb  mov     rcx, [rcx+18h]
0x1400096ef  lea     r8, WPP_1f56813514af312e5a39176f5ad11993_Traceguids
0x1400096f6  mov     edx, 18h
0x1400096fb  mov     qword ptr [rsp+58h+DestinationBufferSize], rbx
0x140009700  mov     r9, rbp
0x140009703  call    WPP_SF_qq
0x140009708  jmp     loc_1400093AA
0x14000970d  mov     r8d, 0C000009Ah
0x140009713  jmp     loc_14003AB54
0x140009718  mov     [r15+16h], dx
0x14000971d  lea     rcx, [r15+64h]; void *
0x140009721  mov     rdx, [rdi+1C8h]
0x140009728  movzx   r8d, word ptr [rdx+16h]
0x14000972d  add     rdx, 64h ; 'd'; Src
0x140009731  shl     r8, 4; Size
0x140009735  call    memmove
0x14000973a  jmp     loc_14000957A
0x14000973f  mov     r8d, 0C000000Dh
0x140009745  jmp     loc_14003AB54
0x14000974a  mov     ecx, 3
0x14000974f  int     29h; Win8: RtlFailFast(ecx)
0x14003ab54  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ab5b  cmp     rcx, r14
  ... truncated ...
```
