# TmpPropagationComplete

- ea: `0x14001953c`
- end: `0x140019766`
- name: `TmpPropagationComplete`
- size: `554`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140018700`
- `0x140018720`
- `0x1400187b0`
- `0x14001904c`
- `0x14001953c`

## callees

- `0x1400025c0`
- `0x140002640`
- `0x14000cfa8`
- `0x14001953c`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1400195be`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400195be`
- `ntoskrnl!KeReleaseMutex` at `0x140019723`
- `ntoskrnl!KeReleaseMutex` at `0x140022c3b`
- `ntoskrnl!KeReleaseMutex` at `0x140019723`
- `ntoskrnl!KeReleaseMutex` at `0x140022c3b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400196eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022bf5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400196eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022bf5`
- `ntoskrnl!ExAllocatePoolWithQuotaTag` at `0x14001960a`
- `ntoskrnl!ExAllocatePoolWithQuotaTag` at `0x14001960a`
- `ntoskrnl!KeCancelTimer` at `0x14001967d`
- `ntoskrnl!KeCancelTimer` at `0x14001967d`
- `ntoskrnl!KeRemoveQueueDpc` at `0x140019692`
- `ntoskrnl!KeRemoveQueueDpc` at `0x140019692`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140022baf`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140022baf`

## pseudocode

```c
__int64 __fastcall TmpPropagationComplete(__int64 a1, unsigned int a2, const void *a3, int a4)
{
  size_t v6; // rbx
  int v8; // esi
  int v9; // r15d
  char v10; // r14
  PVOID PoolWithQuotaTag; // rax
  __int64 (__fastcall *v12)(__int64, _QWORD, _QWORD, __int128 *); // rax
  BOOLEAN v13; // bl
  BOOLEAN v14; // r12
  void *v15; // rcx
  struct _KMUTANT *Mutex; // [rsp+40h] [rbp-48h]
  __int128 v18; // [rsp+50h] [rbp-38h] BYREF

  v6 = a2;
  if ( !a1 )
    return 3221225485LL;
  if ( a4 == 259 )
    return 3221225485LL;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  if ( a2 )
  {
    if ( !a3 )
      return 3221225485LL;
  }
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 8));
  Mutex = (struct _KMUTANT *)(a1 + 112);
  KeWaitForSingleObject((PVOID)(a1 + 112), Executive, 0, 0, 0);
  if ( *(_BYTE *)(a1 + 384) == 1 )
  {
    v10 = 1;
    v8 = -1073741823;
  }
  else
  {
    *(_DWORD *)(a1 + 92) = a4;
    *(_DWORD *)(a1 + 368) = v6;
    if ( !(_DWORD)v6
      || (PoolWithQuotaTag = ExAllocatePoolWithQuotaTag((POOL_TYPE)9, v6, 0x6F506D54u),
          (*(_QWORD *)(a1 + 376) = PoolWithQuotaTag) != 0) )
    {
      if ( (_DWORD)v6 )
        memmove(*(void **)(a1 + 376), a3, v6);
      *(_BYTE *)(a1 + 384) = 1;
      v12 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int128 *))(a1 + 96);
      if ( v12 )
      {
        v18 = *(_OWORD *)(a1 + 72);
        v9 = v12(a1, *(_QWORD *)(a1 + 104), *(unsigned int *)(a1 + 92), &v18);
      }
      v13 = KeCancelTimer((PKTIMER)(a1 + 264));
      v14 = KeRemoveQueueDpc((PRKDPC)(a1 + 200));
      if ( v13 )
        TmpDereferencePropagateRequest((PVOID)a1);
      if ( v14 )
        TmpDereferencePropagateRequest((PVOID)a1);
    }
    else
    {
      v8 = -1073741670;
    }
  }
  if ( v8 < 0 && !v10 )
  {
    v15 = *(void **)(a1 + 376);
    if ( v15 )
    {
      ExFreePoolWithTag(v15, 0);
      *(_QWORD *)(a1 + 376) = 0;
    }
    *(_DWORD *)(a1 + 368) = 0;
    TmpPropagationComplete(a1, 0, 0, (unsigned int)v8);
  }
  KeReleaseMutex(Mutex, 0);
  TmpDereferencePropagateRequest((PVOID)a1);
  if ( v8 >= 0 && v9 < 0 )
    return (unsigned int)v9;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14001953c  mov     rax, rsp
0x14001953f  mov     [rax+10h], rbx
0x140019543  mov     [rax+18h], rsi
0x140019547  mov     [rax+8], rcx
0x14001954b  push    rdi
0x14001954c  push    r12
0x14001954e  push    r13
0x140019550  push    r14
0x140019552  push    r15
0x140019554  sub     rsp, 60h
0x140019558  mov     r12d, r9d
0x14001955b  mov     r13, r8
0x14001955e  mov     ebx, edx
0x140019560  mov     rdi, rcx
0x140019563  test    rcx, rcx
0x140019566  jz      loc_140019746
0x14001956c  cmp     r9d, 103h
0x140019573  jz      loc_140019746
0x140019579  xor     esi, esi
0x14001957b  mov     [rax-54h], esi
0x14001957e  xor     r15d, r15d
0x140019581  mov     [rax-50h], r15d
0x140019585  mov     [rax-57h], sil
0x140019589  xor     r14b, r14b
0x14001958c  mov     [rax-58h], r14b
0x140019590  test    edx, edx
0x140019592  jz      short loc_14001959D
0x140019594  test    r8, r8
0x140019597  jz      loc_140019746
0x14001959d  lock inc dword ptr [rcx+8]
0x1400195a1  lea     rax, [rcx+70h]
0x1400195a5  mov     [rsp+88h+Mutex], rax
0x1400195aa  mov     [rsp+88h+Timeout], 0; Timeout
0x1400195b3  xor     r9d, r9d; Alertable
0x1400195b6  xor     r8d, r8d; WaitMode
0x1400195b9  xor     edx, edx; WaitReason
0x1400195bb  mov     rcx, rax; Object
0x1400195be  call    cs:__imp_KeWaitForSingleObject
0x1400195c5  nop     dword ptr [rax+rax+00h]
0x1400195ca  mov     [rsp+88h+var_57], 1
0x1400195cf  cmp     byte ptr [rdi+180h], 1
0x1400195d6  jnz     short loc_1400195EE
0x1400195d8  mov     r14b, 1
0x1400195db  mov     [rsp+88h+var_58], r14b
0x1400195e0  mov     esi, 0C0000001h
0x1400195e5  mov     [rsp+88h+var_54], esi
0x1400195e9  jmp     loc_1400196D4
0x1400195ee  mov     [rdi+5Ch], r12d
0x1400195f2  mov     [rdi+170h], ebx
0x1400195f8  test    ebx, ebx
0x1400195fa  jz      short loc_140019629
0x1400195fc  mov     r8d, 6F506D54h; Tag
0x140019602  mov     rdx, rbx; NumberOfBytes
0x140019605  mov     ecx, 9; PoolType
0x14001960a  call    cs:__imp_ExAllocatePoolWithQuotaTag
0x140019611  nop     dword ptr [rax+rax+00h]
0x140019616  mov     [rdi+178h], rax
0x14001961d  test    rax, rax
0x140019620  jnz     short loc_140019629
0x140019622  mov     esi, 0C000009Ah
0x140019627  jmp     short loc_1400195E5
0x140019629  test    ebx, ebx
0x14001962b  jz      short loc_140019640
0x14001962d  mov     r8, rbx; Size
0x140019630  mov     rdx, r13; Src
0x140019633  mov     rcx, [rdi+178h]; void *
0x14001963a  call    memmove
0x14001963f  nop
0x140019640  mov     byte ptr [rdi+180h], 1
0x140019647  mov     rax, [rdi+60h]
0x14001964b  test    rax, rax
0x14001964e  jz      short loc_140019676
0x140019650  movups  xmm0, xmmword ptr [rdi+48h]
0x140019654  movdqu  [rsp+88h+var_38], xmm0
0x14001965a  lea     r9, [rsp+88h+var_38]
0x14001965f  mov     r8d, [rdi+5Ch]
0x140019663  mov     rdx, [rdi+68h]
0x140019667  mov     rcx, rdi
0x14001966a  call    _guard_dispatch_icall
0x14001966f  mov     r15d, eax
0x140019672  mov     [rsp+88h+var_50], eax
0x140019676  lea     rcx, [rdi+108h]; PKTIMER
0x14001967d  call    cs:__imp_KeCancelTimer
0x140019684  nop     dword ptr [rax+rax+00h]
0x140019689  mov     bl, al
0x14001968b  lea     rcx, [rdi+0C8h]; Dpc
0x140019692  call    cs:__imp_KeRemoveQueueDpc
0x140019699  nop     dword ptr [rax+rax+00h]
0x14001969e  mov     r12b, al
0x1400196a1  test    bl, bl
0x1400196a3  jz      short loc_1400196AD
0x1400196a5  mov     rcx, rdi; P
0x1400196a8  call    TmpDereferencePropagateRequest
0x1400196ad  test    r12b, r12b
0x1400196b0  jz      short loc_1400196D4
0x1400196b2  mov     rcx, rdi; P
0x1400196b5  call    TmpDereferencePropagateRequest
0x1400196ba  jmp     short loc_1400196D4
0x1400196bc  mov     esi, eax
0x1400196be  mov     [rsp+88h+var_54], eax
0x1400196c2  mov     rdi, [rsp+88h+arg_0]
0x1400196ca  mov     r15d, [rsp+88h+var_50]
0x1400196cf  mov     r14b, [rsp+88h+var_58]
0x1400196d4  test    esi, esi
0x1400196d6  jns     short loc_14001971C
0x1400196d8  test    r14b, r14b
0x1400196db  jnz     short loc_14001971C
0x1400196dd  mov     rcx, [rdi+178h]; P
0x1400196e4  test    rcx, rcx
0x1400196e7  jz      short loc_140019702
0x1400196e9  xor     edx, edx; Tag
0x1400196eb  call    cs:__imp_ExFreePoolWithTag
0x1400196f2  nop     dword ptr [rax+rax+00h]
0x1400196f7  mov     qword ptr [rdi+178h], 0
0x140019702  mov     dword ptr [rdi+170h], 0
0x14001970c  mov     r9d, esi
0x14001970f  xor     r8d, r8d
0x140019712  xor     edx, edx
0x140019714  mov     rcx, rdi
0x140019717  call    TmpPropagationComplete
0x14001971c  xor     edx, edx; Wait
0x14001971e  mov     rcx, [rsp+88h+Mutex]; Mutex
0x140019723  call    cs:__imp_KeReleaseMutex
0x14001972a  nop     dword ptr [rax+rax+00h]
0x14001972f  mov     rcx, rdi; P
0x140019732  call    TmpDereferencePropagateRequest
0x140019737  test    esi, esi
0x140019739  js      short loc_140019742
0x14001973b  test    r15d, r15d
0x14001973e  cmovs   esi, r15d
0x140019742  mov     eax, esi
0x140019744  jmp     short loc_14001974B
0x140019746  mov     eax, 0C000000Dh
0x14001974b  lea     r11, [rsp+88h+var_28]
0x140019750  mov     rbx, [r11+38h]
0x140019754  mov     rsi, [r11+40h]
0x140019758  mov     rsp, r11
0x14001975b  pop     r15
0x14001975d  pop     r14
0x14001975f  pop     r13
0x140019761  pop     r12
0x140019763  pop     rdi
0x140019764  retn
0x140022ba6  push    rbp
0x140022ba8  sub     rsp, 30h
0x140022bac  mov     rbp, rdx
0x140022baf  call    cs:__imp_ExSystemExceptionFilter
0x140022bb6  nop     dword ptr [rax+rax+00h]
0x140022bbb  nop
0x140022bbc  add     rsp, 30h
0x140022bc0  pop     rbp
0x140022bc1  retn
0x140022bc3  push    rbx
0x140022bc5  push    rbp
0x140022bc6  push    rdi
0x140022bc7  sub     rsp, 30h
0x140022bcb  mov     rbp, rdx
0x140022bce  mov     edi, [rbp+34h]
0x140022bd1  test    edi, edi
0x140022bd3  jns     short loc_140022C28
0x140022bd5  cmp     byte ptr [rbp+30h], 0
0x140022bd9  jnz     short loc_140022C28
0x140022bdb  mov     rbx, [rbp+90h]
0x140022be2  cmp     qword ptr [rbx+178h], 0
0x140022bea  jz      short loc_140022C0C
0x140022bec  xor     edx, edx; Tag
0x140022bee  mov     rcx, [rbx+178h]; P
0x140022bf5  call    cs:__imp_ExFreePoolWithTag
0x140022bfc  nop     dword ptr [rax+rax+00h]
0x140022c01  mov     qword ptr [rbx+178h], 0
0x140022c0c  mov     dword ptr [rbx+170h], 0
0x140022c16  mov     r9d, edi
0x140022c19  xor     r8d, r8d
0x140022c1c  xor     edx, edx
0x140022c1e  mov     rcx, rbx
0x140022c21  call    TmpPropagationComplete
0x140022c26  jmp     short loc_140022C2F
0x140022c28  mov     rbx, [rbp+90h]
0x140022c2f  cmp     byte ptr [rbp+31h], 0
0x140022c33  jz      short loc_140022C4B
0x140022c35  lea     rcx, [rbx+70h]; Mutex
0x140022c39  xor     edx, edx; Wait
0x140022c3b  call    cs:__imp_KeReleaseMutex
0x140022c42  nop     dword ptr [rax+rax+00h]
0x140022c47  mov     byte ptr [rbp+31h], 0
0x140022c4b  mov     rcx, rbx; P
0x140022c4e  call    TmpDereferencePropagateRequest
0x140022c53  nop
0x140022c54  add     rsp, 30h
0x140022c58  pop     rdi
0x140022c59  pop     rbp
0x140022c5a  pop     rbx
0x140022c5b  retn
```
