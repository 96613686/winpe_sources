# OutpTrySendCompletionPacket

- ea: `0x140005300`
- end: `0x140005581`
- name: `OutpTrySendCompletionPacket`
- size: `641`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140006700`

## callees

- `0x140003ea0`
- `0x140004790`
- `0x140005230`
- `0x140005300`
- `0x140008f90`
- `0x140011f80`

## pseudocode

```c
bool __fastcall OutpTrySendCompletionPacket(__int64 a1, __int64 a2, const void *a3, unsigned int a4)
{
  const void *v5; // r13
  size_t v6; // r10
  __int64 v8; // rbp
  int v9; // ebx
  unsigned int v10; // r8d
  __int64 v11; // rsi
  unsigned int v12; // r12d
  _DWORD *v13; // r14
  unsigned int v14; // ecx
  int v15; // edx
  unsigned int v16; // r9d
  __int64 v17; // r11
  unsigned int v18; // edx
  unsigned int v19; // ecx
  unsigned int v20; // eax
  unsigned int v21; // ecx
  int v22; // edx
  unsigned int v23; // r9d
  unsigned int v24; // eax
  int v25; // eax
  int v26; // r9d
  _DWORD *v27; // rcx
  unsigned int v28; // edx
  unsigned int v29; // eax
  signed __int32 v31[8]; // [rsp+0h] [rbp-68h] BYREF

  v5 = a3;
  v6 = a4;
  v8 = a4 + 16;
  if ( (unsigned int)v8 > 0x7FFF8 )
  {
    v9 = -1073741811;
    goto LABEL_34;
  }
  v10 = *(_DWORD *)(a1 + 80);
  v11 = *(unsigned int *)(a1 + 192);
  v12 = (a4 + 23) & 0xFFFFFFF8;
  v13 = (_DWORD *)(v11 + *(_QWORD *)(a1 + 72));
  _m_prefetchw(v13);
  v14 = *(_DWORD *)(a1 + 196) - v11 - 8;
  if ( v14 >= v10 )
    v14 += v10;
  if ( v14 < v12 + 8 )
  {
    if ( !(unsigned __int8)PkpValidatePointer(v10, *(unsigned int *)(*(_QWORD *)(a1 + 64) + 4LL)) )
    {
      v9 = -1073741566;
      goto LABEL_34;
    }
    *(_DWORD *)(a1 + 196) = v15;
    v18 = v15 - v11 - 8;
    if ( v18 >= (unsigned int)a3 )
      v18 += (unsigned int)a3;
    if ( v18 < v16 )
    {
      if ( v16 >= (unsigned int)a3 )
      {
        v9 = -1073741811;
        goto LABEL_34;
      }
      if ( !*(_DWORD *)(a1 + 200)
        && (unsigned int)(*(_DWORD *)(a1 + 136) + *(_DWORD *)(a1 + 204) - *(_DWORD *)(a1 + 140)) < 0x40 )
      {
        _InterlockedIncrement((volatile signed __int32 *)(a1 + 204));
      }
      v19 = v11 - *(_DWORD *)(a1 + 192);
      if ( v19 >= (unsigned int)a3 )
        v19 += (unsigned int)a3;
      v20 = (_DWORD)a3 - 8;
      v21 = v16 + v19;
      if ( v21 < (unsigned int)a3 )
        v20 = v21;
      *(_DWORD *)(v17 + 12) = v20;
      *(_DWORD *)(a1 + 200) = v12;
      _InterlockedOr(v31, 0);
      if ( !(unsigned __int8)PkpValidatePointer((unsigned int)a3, *(unsigned int *)(v17 + 4)) )
      {
        v9 = -1073741566;
        goto LABEL_34;
      }
      *(_DWORD *)(a1 + 196) = v22;
      v24 = v22 - v11 - 8;
      if ( v24 >= (unsigned int)a3 )
        v24 += (unsigned int)a3;
      if ( v24 < v23 )
      {
        v9 = -2147483643;
        goto LABEL_34;
      }
    }
  }
  *v13 = 131083;
  *((_WORD *)v13 + 2) = (unsigned __int64)(v8 + 7) >> 3;
  *((_WORD *)v13 + 3) = 0;
  *((_QWORD *)v13 + 1) = a2;
  memmove(v13 + 4, v5, v6);
  v25 = PkWritePacketFooter(a1 + 64, (unsigned int)v11, (unsigned int)v8);
  v26 = *(_DWORD *)(a1 + 192);
  v27 = *(_DWORD **)(a1 + 64);
  v28 = *(_DWORD *)(a1 + 80);
  *(_DWORD *)(a1 + 192) = v25;
  *v27 = v25;
  _InterlockedOr(v31, 0);
  LODWORD(a3) = v27[2];
  v29 = v27[1];
  if ( v29 >= v28 || (v29 & 7) != 0 )
  {
    v9 = -1073741566;
  }
  else
  {
    *(_DWORD *)(a1 + 196) = v29;
    if ( v26 == v29 )
    {
      if ( !(_DWORD)a3 )
      {
        v9 = 532;
        goto LABEL_34;
      }
      ++**(_QWORD **)(a1 + 216);
    }
    v9 = 0;
  }
LABEL_34:
  if ( (Microsoft_Windows_Hyper_V_KMCL_ChildEnableBits & 2) != 0 )
    McTemplateK0jjxth_EtwWriteTransfer(
      *(_DWORD *)a1 + 2752,
      (unsigned int)VMBUS_SEND_PACKET,
      (_DWORD)a3,
      *(_DWORD *)a1 + 2768,
      *(_QWORD *)a1 + 2752LL,
      a2,
      1,
      *(_WORD *)(*(_QWORD *)a1 + 3280LL));
  if ( v9 >= 0 )
    ++*(_DWORD *)(a1 + 528);
  return (int)OutpProcessRingResult(a1, (unsigned int)v9) >= 0;
}

```

## disassembly

```asm
0x140005300  push    rbx
0x140005302  push    rdi
0x140005303  sub     rsp, 58h
0x140005307  mov     [rsp+68h+arg_0], rbp
0x14000530c  mov     rdi, rcx
0x14000530f  mov     [rsp+68h+var_18], r13
0x140005314  mov     r13, r8
0x140005317  mov     r10d, r9d
0x14000531a  mov     [rsp+68h+var_28], r15
0x14000531f  mov     r15, rdx
0x140005322  lea     ebp, [r10+10h]
0x140005326  cmp     ebp, 7FFF8h
0x14000532c  jbe     short loc_140005338
0x14000532e  mov     ebx, 0C000000Dh
0x140005333  jmp     loc_14000550D
0x140005338  mov     r8d, [rcx+50h]
0x14000533c  lea     eax, [rbp+7]
0x14000533f  and     eax, 0FFFFFFF8h
0x140005342  mov     [rsp+68h+arg_8], rsi
0x140005347  mov     esi, [rcx+0C0h]
0x14000534d  mov     [rsp+68h+arg_10], r12
0x140005355  mov     r12d, eax
0x140005358  mov     [rsp+68h+var_20], r14
0x14000535d  mov     r14, [rcx+48h]
0x140005361  lea     r9d, [rax+8]
0x140005365  add     r14, rsi
0x140005368  prefetchw byte ptr [r14]
0x14000536c  mov     ecx, [rcx+0C4h]
0x140005372  sub     ecx, esi
0x140005374  add     ecx, 0FFFFFFF8h
0x140005377  cmp     ecx, r8d
0x14000537a  lea     eax, [rcx+r8]
0x14000537e  cmovnb  ecx, eax
0x140005381  cmp     ecx, r9d
0x140005384  jnb     loc_140005469
0x14000538a  mov     r11, [rdi+40h]
0x14000538e  mov     ecx, r8d
0x140005391  mov     edx, [r11+4]
0x140005395  call    PkpValidatePointer
0x14000539a  test    al, al
0x14000539c  jnz     short loc_1400053A8
0x14000539e  mov     ebx, 0C0000102h
0x1400053a3  jmp     loc_1400054FB
0x1400053a8  mov     [rdi+0C4h], edx
0x1400053ae  sub     edx, esi
0x1400053b0  add     edx, 0FFFFFFF8h
0x1400053b3  cmp     edx, r8d
0x1400053b6  jb      short loc_1400053BB
0x1400053b8  add     edx, r8d
0x1400053bb  cmp     edx, r9d
0x1400053be  jnb     loc_140005469
0x1400053c4  cmp     r9d, r8d
0x1400053c7  jb      short loc_1400053D3
0x1400053c9  mov     ebx, 0C000000Dh
0x1400053ce  jmp     loc_1400054FB
0x1400053d3  cmp     dword ptr [rdi+0C8h], 0
0x1400053da  jnz     short loc_1400053FE
0x1400053dc  mov     edx, [rdi+88h]
0x1400053e2  mov     ecx, [rdi+0CCh]
0x1400053e8  mov     eax, [rdi+8Ch]
0x1400053ee  sub     ecx, eax
0x1400053f0  add     ecx, edx
0x1400053f2  cmp     ecx, 40h ; '@'
0x1400053f5  jnb     short loc_1400053FE
0x1400053f7  lock inc dword ptr [rdi+0CCh]
0x1400053fe  mov     ecx, esi
0x140005400  sub     ecx, [rdi+0C0h]
0x140005406  cmp     ecx, r8d
0x140005409  lea     eax, [rcx+r8]
0x14000540d  cmovnb  ecx, eax
0x140005410  lea     eax, [r8-8]
0x140005414  add     ecx, r9d
0x140005417  cmp     ecx, r8d
0x14000541a  cmovb   eax, ecx
0x14000541d  mov     [r11+0Ch], eax
0x140005421  mov     [rdi+0C8h], r12d
0x140005428  lock or [rsp+68h+var_68], 0
0x14000542d  mov     edx, [r11+4]
0x140005431  mov     ecx, r8d
0x140005434  call    PkpValidatePointer
0x140005439  test    al, al
0x14000543b  jnz     short loc_140005447
0x14000543d  mov     ebx, 0C0000102h
0x140005442  jmp     loc_1400054FB
0x140005447  mov     [rdi+0C4h], edx
0x14000544d  sub     edx, esi
0x14000544f  lea     eax, [rdx-8]
0x140005452  cmp     eax, r8d
0x140005455  jb      short loc_14000545A
0x140005457  add     eax, r8d
0x14000545a  cmp     eax, r9d
0x14000545d  jnb     short loc_140005469
0x14000545f  mov     ebx, 80000005h
0x140005464  jmp     loc_1400054FB
0x140005469  nop
0x14000546a  lea     rax, [rbp+7]
0x14000546e  mov     dword ptr [r14], 2000Bh
0x140005475  lea     rcx, [r14+10h]; void *
0x140005479  shr     rax, 3
0x14000547d  mov     r8, r10; Size
0x140005480  mov     [r14+4], ax
0x140005485  mov     rdx, r13; Src
0x140005488  xor     eax, eax
0x14000548a  mov     [r14+6], ax
0x14000548f  mov     [r14+8], r15
0x140005493  call    memmove
0x140005498  mov     r8d, ebp
0x14000549b  lea     rcx, [rdi+40h]
0x14000549f  mov     edx, esi
0x1400054a1  call    PkWritePacketFooter
0x1400054a6  mov     r9d, [rdi+0C0h]
0x1400054ad  mov     rcx, [rdi+40h]
0x1400054b1  mov     edx, [rdi+50h]
0x1400054b4  mov     [rdi+0C0h], eax
0x1400054ba  mov     [rcx], eax
0x1400054bc  lock or [rsp+68h+var_68], 0
0x1400054c1  mov     r8d, [rcx+8]
0x1400054c5  mov     eax, [rcx+4]
0x1400054c8  cmp     eax, edx
0x1400054ca  jnb     short loc_1400054F5
0x1400054cc  test    al, 7
0x1400054ce  jnz     short loc_1400054F5
0x1400054d0  mov     [rdi+0C4h], eax
0x1400054d6  cmp     r9d, eax
0x1400054d9  jnz     short loc_1400054F1
0x1400054db  test    r8d, r8d
0x1400054de  jnz     short loc_1400054E7
0x1400054e0  mov     ebx, 214h
0x1400054e5  jmp     short loc_1400054FA
0x1400054e7  mov     rax, [rdi+0D8h]
0x1400054ee  inc     qword ptr [rax]
0x1400054f1  xor     ebx, ebx
0x1400054f3  jmp     short loc_1400054FA
0x1400054f5  mov     ebx, 0C0000102h
0x1400054fa  nop
0x1400054fb  mov     r12, [rsp+68h+arg_10]
0x140005503  mov     rsi, [rsp+68h+arg_8]
0x140005508  mov     r14, [rsp+68h+var_20]
0x14000550d  test    cs:Microsoft_Windows_Hyper_V_KMCL_ChildEnableBits, 2
0x140005514  mov     r13, [rsp+68h+var_18]
0x140005519  mov     rbp, [rsp+68h+arg_0]
0x14000551e  jz      short loc_14000555B
0x140005520  mov     rax, [rdi]
0x140005523  lea     rdx, VMBUS_SEND_PACKET
0x14000552a  lea     rcx, [rax+0AC0h]
0x140005531  lea     r9, [rax+0AD0h]
0x140005538  movzx   eax, word ptr [rax+0CD0h]
0x14000553f  mov     [rsp+68h+var_30], ax
0x140005544  mov     [rsp+68h+var_38], 1
0x14000554c  mov     [rsp+68h+var_40], r15
0x140005551  mov     [rsp+68h+var_48], rcx
0x140005556  call    McTemplateK0jjxth_EtwWriteTransfer
0x14000555b  mov     r15, [rsp+68h+var_28]
0x140005560  test    ebx, ebx
0x140005562  js      short loc_14000556A
0x140005564  inc     dword ptr [rdi+210h]
0x14000556a  mov     edx, ebx
0x14000556c  mov     rcx, rdi
0x14000556f  call    OutpProcessRingResult
0x140005574  shr     eax, 1Fh
0x140005577  xor     al, 1
0x140005579  add     rsp, 58h
0x14000557d  pop     rdi
0x14000557e  pop     rbx
0x14000557f  retn
```
