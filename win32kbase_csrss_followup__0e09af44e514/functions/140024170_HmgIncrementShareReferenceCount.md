# HmgIncrementShareReferenceCount

- ea: `0x140024170`
- end: `0x14002438c`
- name: `HmgIncrementShareReferenceCount`
- size: `540`
- prototype: ``
- caller_count: `13`
- callee_count: `5`
- tags: ``

## callers

- `0x14000e328`
- `0x14000e5e0`
- `0x14001a450`
- `0x14002e368`
- `0x14002ebe8`
- `0x14003b3b0`
- `0x14003e2a0`
- `0x14016459c`
- `0x14016e630`
- `0x14017598c`
- `0x140186a98`
- `0x1401e5298`
- `0x1401f1a54`

## callees

- `0x140024170`
- `0x140024f24`
- `0x140026270`
- `0x140043e04`
- `0x140238240`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x140024336`
- `ntoskrnl!PsGetCurrentProcess` at `0x140024336`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002428f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400242de`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002428f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400242de`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140024345`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140024362`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140024345`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140024362`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140024353`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140024353`
- `ntoskrnl!KeIsAttachedProcess` at `0x1400241c9`
- `ntoskrnl!KeIsAttachedProcess` at `0x1400241c9`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x1400241ba`
- `ntoskrnl!PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion` at `0x1400241ba`

## pseudocode

```c
void __fastcall HmgIncrementShareReferenceCount(__int64 a1, unsigned int *a2)
{
  unsigned int v2; // eax
  unsigned int v4; // edi
  __int64 v5; // r13
  unsigned int v6; // edi
  _QWORD *CurrentThreadWin32ThreadAndEnterCriticalRegion; // rsi
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r15
  __int64 v13; // rcx
  int v14; // ebx
  unsigned int *v15; // rax
  unsigned int *v16; // rsi
  char v17; // al
  __int64 v18; // r8
  __int64 v19; // rdx
  __int64 *v20; // rdi
  __int64 v21; // rbx
  __int64 v22; // rax
  ThreadRestrictNewHandlesRegion *v23; // rcx
  __int64 CurrentProcess; // rax
  int ProcessSessionId; // ebx
  __int64 CurrentThreadProcess; // rax
  unsigned int *v27; // [rsp+20h] [rbp-48h] BYREF
  int v28; // [rsp+28h] [rbp-40h]
  __int16 v29; // [rsp+2Ch] [rbp-3Ch]
  __int64 v30; // [rsp+30h] [rbp-38h]
  __int64 v31; // [rsp+70h] [rbp+8h] BYREF

  v2 = *a2;
  v4 = *a2;
  v30 = a1;
  v5 = a1;
  v6 = (unsigned __int16)v2 | (v4 >> 8) & 0xFF0000;
  v29 = 0;
  v31 = 0;
  CurrentThreadWin32ThreadAndEnterCriticalRegion = (_QWORD *)PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion(&v31);
  if ( (!(unsigned __int8)KeIsAttachedProcess()
     || (CurrentProcess = PsGetCurrentProcess(v10, v9, v11),
         ProcessSessionId = PsGetProcessSessionIdEx(CurrentProcess),
         CurrentThreadProcess = PsGetCurrentThreadProcess(),
         ProcessSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)))
    && CurrentThreadWin32ThreadAndEnterCriticalRegion
    && *CurrentThreadWin32ThreadAndEnterCriticalRegion )
  {
    v12 = *CurrentThreadWin32ThreadAndEnterCriticalRegion + 8LL;
  }
  else
  {
    v12 = 0;
  }
  v13 = *(_QWORD *)(a1 + 8);
  v14 = 1;
  v28 = 1;
  v15 = (unsigned int *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v13 + 40LL))(v13, v6);
  v27 = v15;
  v16 = v15;
  if ( v15 )
  {
    _m_prefetchw(v15 + 2);
    if ( (*(_BYTE *)((*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 8) + 96LL))(
                       *(_QWORD *)(a1 + 8),
                       *v15)
                   + 14)
        & 0x20) != 0
      && (!v12
       || (v23 = *(ThreadRestrictNewHandlesRegion **)(v12 + 328)) == 0
       || !*((_BYTE *)v23 + 80)
       || !ThreadRestrictNewHandlesRegion::InRegion(v23, v6)) )
    {
      LOBYTE(v29) = 1;
      HANDLELOCK::vUnlock((HANDLELOCK *)&v27);
      v5 = v30;
      v14 = v28;
      v16 = v27;
    }
  }
  else
  {
    v14 = 0;
    KeLeaveCriticalRegion();
  }
  if ( v14 )
  {
    v17 = *((_BYTE *)v16 + 14);
    switch ( v17 )
    {
      case 5:
        v18 = *((_QWORD *)a2 + 91);
        v19 = 3;
        break;
      case 4:
        v18 = *((_QWORD *)a2 + 14);
        v19 = 2;
        break;
      case 16:
        v18 = *((_QWORD *)a2 + 17);
        v19 = 0;
        break;
      default:
        goto LABEL_11;
    }
    TrackObjectReferenceIncrement(a1, v19, v18);
LABEL_11:
    ++a2[2];
    v20 = *(__int64 **)(v5 + 8);
    v21 = *v20;
    v22 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v20 + 96))(v20, *v16);
    (*(void (__fastcall **)(__int64 *, __int64))(v21 + 48))(v20, v22);
    KeLeaveCriticalRegion();
    return;
  }
  (*(void (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)(a1 + 8) + 8LL))(*(_QWORD *)(a1 + 8), a2);
}

```

## disassembly

```asm
0x140024170  mov     [rsp+arg_10], rbx
0x140024175  push    rbp
0x140024176  push    rsi
0x140024177  push    rdi
0x140024178  push    r13
0x14002417a  push    r14
0x14002417c  sub     rsp, 40h
0x140024180  mov     eax, [rdx]
0x140024182  mov     rbp, rcx
0x140024185  mov     edi, eax
0x140024187  mov     [rsp+68h+var_38], rcx
0x14002418c  shr     edi, 8
0x14002418f  mov     r13, rcx
0x140024192  movzx   eax, ax
0x140024195  lea     rcx, [rsp+68h+arg_0]
0x14002419a  and     edi, 0FF0000h
0x1400241a0  mov     [rsp+68h+arg_8], r15
0x1400241a5  or      edi, eax
0x1400241a7  mov     [rsp+68h+var_3C], 0
0x1400241ae  mov     r14, rdx
0x1400241b1  mov     [rsp+68h+arg_0], 0
0x1400241ba  call    cs:__imp_PsGetCurrentThreadWin32ThreadAndEnterCriticalRegion
0x1400241c1  nop     dword ptr [rax+rax+00h]
0x1400241c6  mov     rsi, rax
0x1400241c9  call    cs:__imp_KeIsAttachedProcess
0x1400241d0  nop     dword ptr [rax+rax+00h]
0x1400241d5  test    al, al
0x1400241d7  jnz     loc_140024336
0x1400241dd  test    rsi, rsi
0x1400241e0  jz      loc_140024376
0x1400241e6  mov     rax, [rsi]
0x1400241e9  test    rax, rax
0x1400241ec  jz      loc_140024376
0x1400241f2  lea     r15, [rax+8]
0x1400241f6  mov     rcx, [rbp+8]
0x1400241fa  mov     ebx, 1
0x1400241ff  mov     edx, edi
0x140024201  mov     [rsp+68h+var_40], ebx
0x140024205  mov     rax, [rcx]
0x140024208  mov     rax, [rax+28h]
0x14002420c  call    _guard_dispatch_icall
0x140024211  mov     [rsp+68h+var_48], rax
0x140024216  mov     rsi, rax
0x140024219  test    rax, rax
0x14002421c  jz      loc_1400242DC
0x140024222  prefetchw byte ptr [rax+8]
0x140024226  mov     rcx, [rbp+8]
0x14002422a  mov     edx, [rsi]
0x14002422c  mov     rax, [rcx]
0x14002422f  mov     rax, [rax+60h]
0x140024233  call    _guard_dispatch_icall
0x140024238  test    byte ptr [rax+0Eh], 20h
0x14002423c  jnz     loc_1400242EF
0x140024242  mov     r15, [rsp+68h+arg_8]
0x140024247  test    ebx, ebx
0x140024249  jz      short loc_1400242B0
0x14002424b  movzx   eax, byte ptr [rsi+0Eh]
0x14002424f  cmp     al, 5
0x140024251  jnz     short loc_1400242C5
0x140024253  mov     r8, [r14+2D8h]
0x14002425a  mov     edx, 3
0x14002425f  mov     rcx, rbp
0x140024262  call    ?TrackObjectReferenceIncrement@@YAXAEAUSESSION_GLOBALS@Base@Gre@@W4ReferenceTrackerCountedType@@PEAX@Z; TrackObjectReferenceIncrement(Gre::Base::SESSION_GLOBALS &,ReferenceTrackerCountedType,void *)
0x140024267  inc     dword ptr [r14+8]
0x14002426b  mov     rdi, [r13+8]
0x14002426f  mov     edx, [rsi]
0x140024271  mov     rcx, rdi
0x140024274  mov     rbx, [rdi]
0x140024277  mov     rax, [rbx+60h]
0x14002427b  call    _guard_dispatch_icall
0x140024280  mov     rdx, rax
0x140024283  mov     rcx, rdi
0x140024286  mov     rax, [rbx+30h]
0x14002428a  call    _guard_dispatch_icall
0x14002428f  call    cs:__imp_KeLeaveCriticalRegion
0x140024296  nop     dword ptr [rax+rax+00h]
0x14002429b  mov     rbx, [rsp+68h+arg_10]
0x1400242a3  add     rsp, 40h
0x1400242a7  pop     r14
0x1400242a9  pop     r13
0x1400242ab  pop     rdi
0x1400242ac  pop     rsi
0x1400242ad  pop     rbp
0x1400242ae  retn
0x1400242b0  mov     rcx, [rbp+8]
0x1400242b4  mov     rdx, r14
0x1400242b7  mov     rax, [rcx]
0x1400242ba  mov     rax, [rax+8]
0x1400242be  call    _guard_dispatch_icall
0x1400242c3  jmp     short loc_14002429B
0x1400242c5  cmp     al, 4
0x1400242c7  jz      loc_14002437E
0x1400242cd  cmp     al, 10h
0x1400242cf  jnz     short loc_140024267
0x1400242d1  mov     r8, [r14+88h]
0x1400242d8  xor     edx, edx
0x1400242da  jmp     short loc_14002425F
0x1400242dc  xor     ebx, ebx
0x1400242de  call    cs:__imp_KeLeaveCriticalRegion
0x1400242e5  nop     dword ptr [rax+rax+00h]
0x1400242ea  jmp     loc_140024242
0x1400242ef  test    r15, r15
0x1400242f2  jz      short loc_140024315
0x1400242f4  mov     rcx, [r15+148h]; this
0x1400242fb  test    rcx, rcx
0x1400242fe  jz      short loc_140024315
0x140024300  cmp     byte ptr [rcx+50h], 0
0x140024304  jz      short loc_140024315
0x140024306  mov     edx, edi; unsigned int
0x140024308  call    ?InRegion@ThreadRestrictNewHandlesRegion@@QEAA_NI@Z; ThreadRestrictNewHandlesRegion::InRegion(uint)
0x14002430d  test    al, al
0x14002430f  jnz     loc_140024242
0x140024315  mov     byte ptr [rsp+68h+var_3C], bl
0x140024319  lea     rcx, [rsp+68h+var_48]; this
0x14002431e  call    ?vUnlock@HANDLELOCK@@QEAAXXZ; HANDLELOCK::vUnlock(void)
0x140024323  mov     r13, [rsp+68h+var_38]
0x140024328  mov     ebx, [rsp+68h+var_40]
0x14002432c  mov     rsi, [rsp+68h+var_48]
0x140024331  jmp     loc_140024242
0x140024336  call    cs:__imp_PsGetCurrentProcess
0x14002433d  nop     dword ptr [rax+rax+00h]
0x140024342  mov     rcx, rax
0x140024345  call    cs:__imp_PsGetProcessSessionIdEx
0x14002434c  nop     dword ptr [rax+rax+00h]
0x140024351  mov     ebx, eax
0x140024353  call    cs:__imp_PsGetCurrentThreadProcess
0x14002435a  nop     dword ptr [rax+rax+00h]
0x14002435f  mov     rcx, rax
0x140024362  call    cs:__imp_PsGetProcessSessionIdEx
0x140024369  nop     dword ptr [rax+rax+00h]
0x14002436e  cmp     ebx, eax
0x140024370  jz      loc_1400241DD
0x140024376  xor     r15d, r15d
0x140024379  jmp     loc_1400241F6
0x14002437e  mov     r8, [r14+70h]
0x140024382  mov     edx, 2
0x140024387  jmp     loc_14002425F
```
