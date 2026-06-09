# WofTransactionNotificationCallback

- ea: `0x140023490`
- end: `0x1400236cd`
- name: `WofTransactionNotificationCallback`
- size: `573`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140011640`
- `0x140023490`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400235fe`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400236a6`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400235fe`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400236a6`
- `ntoskrnl!ExReInitializeRundownProtection` at `0x14002367f`
- `ntoskrnl!ExReInitializeRundownProtection` at `0x14002367f`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140023640`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140023640`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400234ad`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140023520`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400234ad`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140023520`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x14002368e`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x14002368e`

## pseudocode

```c
__int64 __fastcall WofTransactionNotificationCallback(__int64 a1, __int64 a2, int a3)
{
  _QWORD *v6; // rax
  __int64 v7; // r8
  _QWORD *v8; // rcx
  _QWORD *v9; // rsi
  _QWORD *v10; // rbx
  struct _EX_RUNDOWN_REF **v11; // rdi
  _QWORD *v12; // rcx
  _QWORD *v13; // rax
  int v14; // eax
  struct _EX_RUNDOWN_REF *v15; // r15
  int v16; // eax
  char v17; // bl
  int v18; // eax
  ULONG_PTR Count; // r9
  __int64 v20; // rax
  __int64 v21; // rcx
  void (__fastcall *v22)(ULONG_PTR, struct _EX_RUNDOWN_REF **); // rax
  __int64 v23; // rax
  ULONG_PTR v24; // rbx

  ExAcquireFastMutexUnsafe((PFAST_MUTEX)a2);
  *(_DWORD *)(a2 + 56) |= 2u;
  v6 = *(_QWORD **)(a2 + 80);
  if ( v6 != (_QWORD *)(a2 + 80) )
  {
    do
    {
      v7 = *v6;
      *((_DWORD *)v6 - 6) |= 1u;
      *(v6 - 2) = 0;
      *(v6 - 1) = 0;
      if ( *(_QWORD **)(v7 + 8) != v6 || (v8 = (_QWORD *)v6[1], (_QWORD *)*v8 != v6) )
LABEL_26:
        __fastfail(3u);
      *v8 = v7;
      v6 = (_QWORD *)v7;
      *(_QWORD *)(v7 + 8) = v8;
    }
    while ( v7 != a2 + 80 );
  }
  v9 = *(_QWORD **)(a2 + 64);
  while ( v9 != (_QWORD *)(a2 + 64) )
  {
    v10 = (_QWORD *)*v9;
    v11 = (struct _EX_RUNDOWN_REF **)(v9 - 4);
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(v9 - 4) + 32LL));
    *(_QWORD *)(*(_QWORD *)(*(v9 - 4) + 16LL) + 56LL) = 0;
    v12 = (_QWORD *)*v9;
    if ( *(_QWORD **)(*v9 + 8LL) != v9 )
      goto LABEL_26;
    v13 = (_QWORD *)v9[1];
    if ( (_QWORD *)*v13 != v9 )
      goto LABEL_26;
    *v13 = v12;
    v9 = v10;
    v12[1] = v13;
    v14 = *((_DWORD *)v11 + 2);
    v15 = v11[3];
    v11[3] = 0;
    v16 = v14 & 4;
    if ( v16 && a3 == 4 )
    {
      v17 = 1;
      *((_DWORD *)v11 + 2) &= 0xF0FFFFFF;
      v18 = *((_DWORD *)v11 + 2) | 0x4000000;
    }
    else
    {
      v17 = 0;
      if ( v16 )
      {
        Count = (*v11)[1].Count;
        *((_DWORD *)v11 + 2) |= 8u;
        v20 = *((unsigned int *)v11 + 3);
        if ( (unsigned int)v20 < 4 )
        {
          v21 = 424 * v20;
          if ( *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 424 * v20) )
          {
            v22 = *(void (__fastcall **)(ULONG_PTR, struct _EX_RUNDOWN_REF **))((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels
                                                                              + v21
                                                                              + 208);
            if ( v22 )
            {
              if ( *((_DWORD *)v11 + 4) )
                v22(Count + *(unsigned int *)((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v21 + 20), v11 + 8);
            }
          }
        }
      }
      *((_DWORD *)v11 + 2) &= 0xF0FFFFFB;
      v18 = *((_DWORD *)v11 + 2) | 0x1000000;
    }
    *((_DWORD *)v11 + 2) = v18;
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)&(*v11)[4]);
    if ( v17 )
    {
      v23 = *((unsigned int *)v11 + 3);
      if ( (unsigned int)v23 < 4
        && *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 424 * v23)
        && *((_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 53 * v23 + 27) )
      {
        v24 = (*v11)[1].Count;
        ExWaitForRundownProtectionRelease(*v11 + 3);
        (*((void (__fastcall **)(__int64, ULONG_PTR, struct _EX_RUNDOWN_REF **))&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels
         + 53 * *((unsigned int *)v11 + 3)
         + 27))(
          a1,
          v24 + *(&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 106 * *((unsigned int *)v11 + 3) + 5),
          v11 + 8);
        ExReInitializeRundownProtection(*v11 + 3);
      }
    }
    ObDereferenceObjectDeferDelete(v15);
  }
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)a2);
  return 0;
}

```

## disassembly

```asm
0x140023490  push    rbx
0x140023492  push    rbp
0x140023493  push    rsi
0x140023494  push    rdi
0x140023495  push    r12
0x140023497  push    r13
0x140023499  push    r14
0x14002349b  push    r15
0x14002349d  sub     rsp, 28h
0x1400234a1  mov     r13, rcx
0x1400234a4  mov     r12d, r8d
0x1400234a7  mov     rcx, rdx; FastMutex
0x1400234aa  mov     rbp, rdx
0x1400234ad  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400234b4  nop     dword ptr [rax+rax+00h]
0x1400234b9  or      dword ptr [rbp+38h], 2
0x1400234bd  lea     r9, [rbp+50h]
0x1400234c1  mov     rax, [r9]
0x1400234c4  cmp     rax, r9
0x1400234c7  jz      short loc_140023506
0x1400234c9  mov     r8, [rax]
0x1400234cc  or      dword ptr [rax-18h], 1
0x1400234d0  mov     qword ptr [rax-10h], 0
0x1400234d8  mov     qword ptr [rax-8], 0
0x1400234e0  cmp     [r8+8], rax
0x1400234e4  jnz     loc_1400236C6
0x1400234ea  mov     rcx, [rax+8]
0x1400234ee  cmp     [rcx], rax
0x1400234f1  jnz     loc_1400236C6
0x1400234f7  mov     [rcx], r8
0x1400234fa  mov     rax, r8
0x1400234fd  mov     [r8+8], rcx
0x140023501  cmp     r8, r9
0x140023504  jnz     short loc_1400234C9
0x140023506  lea     r14, [rbp+40h]
0x14002350a  mov     rsi, [r14]
0x14002350d  jmp     loc_14002369A
0x140023512  mov     rbx, [rsi]
0x140023515  lea     rdi, [rsi-20h]
0x140023519  mov     rcx, [rdi]
0x14002351c  add     rcx, 20h ; ' '; FastMutex
0x140023520  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140023527  nop     dword ptr [rax+rax+00h]
0x14002352c  mov     rax, [rdi]
0x14002352f  xor     edx, edx
0x140023531  mov     rcx, [rax+10h]
0x140023535  mov     [rcx+38h], rdx
0x140023539  mov     rcx, [rsi]
0x14002353c  cmp     [rcx+8], rsi
0x140023540  jnz     loc_1400236C6
0x140023546  mov     rax, [rsi+8]
0x14002354a  cmp     [rax], rsi
0x14002354d  jnz     loc_1400236C6
0x140023553  mov     [rax], rcx
0x140023556  mov     rsi, rbx
0x140023559  mov     [rcx+8], rax
0x14002355d  mov     eax, [rdi+8]
0x140023560  mov     r15, [rdi+18h]
0x140023564  mov     [rdi+18h], rdx
0x140023568  and     eax, 4
0x14002356b  jz      short loc_140023589
0x14002356d  cmp     r12d, 4
0x140023571  jnz     short loc_140023589
0x140023573  mov     eax, [rdi+8]
0x140023576  mov     bl, 1
0x140023578  and     eax, 0F0FFFFFFh
0x14002357d  mov     [rdi+8], eax
0x140023580  mov     eax, [rdi+8]
0x140023583  bts     eax, 1Ah
0x140023587  jmp     short loc_1400235F4
0x140023589  mov     bl, dl
0x14002358b  test    eax, eax
0x14002358d  jz      short loc_1400235E2
0x14002358f  mov     rax, [rdi]
0x140023592  mov     r9, [rax+8]
0x140023596  mov     eax, [rdi+8]
0x140023599  or      eax, 8
0x14002359c  mov     [rdi+8], eax
0x14002359f  mov     eax, [rdi+0Ch]
0x1400235a2  cmp     eax, 4
0x1400235a5  jnb     short loc_1400235E2
0x1400235a7  imul    rcx, rax, 1A8h
0x1400235ae  lea     r10, WPP_MAIN_CB.Queue+10h
0x1400235b5  cmp     [rcx+r10], dl
0x1400235b9  jz      short loc_1400235E2
0x1400235bb  mov     rax, [rcx+r10+0D0h]
0x1400235c3  test    rax, rax
0x1400235c6  jz      short loc_1400235E2
0x1400235c8  mov     r8d, [rdi+10h]
0x1400235cc  test    r8d, r8d
0x1400235cf  jz      short loc_1400235E2
0x1400235d1  mov     ecx, [rcx+r10+14h]
0x1400235d6  lea     rdx, [rdi+40h]
0x1400235da  add     rcx, r9
0x1400235dd  call    _guard_dispatch_icall
0x1400235e2  mov     eax, [rdi+8]
0x1400235e5  and     eax, 0F0FFFFFBh
0x1400235ea  mov     [rdi+8], eax
0x1400235ed  mov     eax, [rdi+8]
0x1400235f0  bts     eax, 18h
0x1400235f4  mov     [rdi+8], eax
0x1400235f7  mov     rcx, [rdi]
0x1400235fa  add     rcx, 20h ; ' '; FastMutex
0x1400235fe  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140023605  nop     dword ptr [rax+rax+00h]
0x14002360a  test    bl, bl
0x14002360c  jz      short loc_14002368B
0x14002360e  mov     eax, [rdi+0Ch]
0x140023611  cmp     eax, 4
0x140023614  jnb     short loc_14002368B
0x140023616  imul    rcx, rax, 1A8h
0x14002361d  lea     rax, WPP_MAIN_CB.Queue+10h
0x140023624  cmp     byte ptr [rcx+rax], 0
0x140023628  jz      short loc_14002368B
0x14002362a  cmp     qword ptr [rcx+rax+0D8h], 0
0x140023633  jz      short loc_14002368B
0x140023635  mov     rcx, [rdi]
0x140023638  mov     rbx, [rcx+8]
0x14002363c  add     rcx, 18h; RunRef
0x140023640  call    cs:__imp_ExWaitForRundownProtectionRelease
0x140023647  nop     dword ptr [rax+rax+00h]
0x14002364c  mov     eax, [rdi+0Ch]
0x14002364f  lea     rcx, WPP_MAIN_CB.Queue+10h
0x140023656  imul    rax, 1A8h
0x14002365d  lea     r8, [rdi+40h]
0x140023661  mov     edx, [rax+rcx+14h]
0x140023665  mov     rax, [rax+rcx+0D8h]
0x14002366d  add     rdx, rbx
0x140023670  mov     rcx, r13
0x140023673  call    _guard_dispatch_icall
0x140023678  mov     rcx, [rdi]
0x14002367b  add     rcx, 18h; RunRef
0x14002367f  call    cs:__imp_ExReInitializeRundownProtection
0x140023686  nop     dword ptr [rax+rax+00h]
0x14002368b  mov     rcx, r15; Object
0x14002368e  call    cs:__imp_ObDereferenceObjectDeferDelete
0x140023695  nop     dword ptr [rax+rax+00h]
0x14002369a  cmp     rsi, r14
0x14002369d  jnz     loc_140023512
0x1400236a3  mov     rcx, rbp; FastMutex
0x1400236a6  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1400236ad  nop     dword ptr [rax+rax+00h]
0x1400236b2  xor     eax, eax
0x1400236b4  add     rsp, 28h
0x1400236b8  pop     r15
0x1400236ba  pop     r14
0x1400236bc  pop     r13
0x1400236be  pop     r12
0x1400236c0  pop     rdi
0x1400236c1  pop     rsi
0x1400236c2  pop     rbp
0x1400236c3  pop     rbx
0x1400236c4  retn
0x1400236c6  mov     ecx, 3
0x1400236cb  int     29h; Win8: RtlFailFast(ecx)
```
