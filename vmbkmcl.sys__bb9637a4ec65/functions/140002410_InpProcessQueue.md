# InpProcessQueue

- ea: `0x140002410`
- end: `0x1400026dd`
- name: `InpProcessQueue`
- size: `717`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140001370`
- `0x140001780`
- `0x140001ce0`
- `0x1400022c0`

## callees

- `0x140002410`
- `0x140008140`
- `0x140011ed0`

## import_xrefs

- `HAL!KeQueryPerformanceCounter` at `0x140002680`
- `HAL!KeQueryPerformanceCounter` at `0x140002680`

## pseudocode

```c
__int64 __fastcall InpProcessQueue(__int64 *a1, char a2, unsigned int a3, unsigned int *a4)
{
  __int64 v4; // r10
  unsigned int v7; // ebx
  unsigned int v8; // r13d
  __int64 *v9; // rax
  __int64 *v10; // r10
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 **v13; // rcx
  __int64 *v14; // rcx
  bool v15; // zf
  int v16; // r9d
  void (__fastcall *v17)(__int64 *, __int64, __int64); // rax
  __int64 v18; // r8
  __int64 *v19; // rbp
  __int64 *v20; // rcx
  __int64 **v21; // rdx
  unsigned int v22; // r15d
  unsigned int v23; // r14d
  void (__fastcall *v24)(__int64, _QWORD, __int64 *, __int64, unsigned int, BOOL); // rax
  int v25; // ecx
  int v26; // ecx
  int v27; // ecx
  BOOL v29; // r12d
  LARGE_INTEGER PerformanceCounter; // rax
  __int64 v31; // [rsp+80h] [rbp+8h]
  char v32; // [rsp+88h] [rbp+10h]

  v32 = a2;
  v4 = *a1;
  v7 = 0;
  v8 = 1;
  v31 = *a1;
  while ( v7 < a3 )
  {
    v9 = (__int64 *)a1[160];
    if ( v9 == a1 + 160 )
      break;
    if ( *((_DWORD *)v9 + 4) == 1 )
    {
      v10 = v9 - 18;
      v11 = *v9;
      v12 = 0;
      if ( (*((_BYTE *)v9 - 82) & 2) == 0 )
        v12 = 3221225507LL;
      if ( *(__int64 **)(v11 + 8) != v9 || (v13 = (__int64 **)v9[1], *v13 != v9) )
LABEL_13:
        __fastfail(3u);
      *v13 = (__int64 *)v11;
      *(_QWORD *)(v11 + 8) = v13;
      v14 = v9 - 18;
      v15 = (*((_BYTE *)v10 + 62) & 0x40) == 0;
      v16 = *((_DWORD *)v10 + 29);
      v17 = (void (__fastcall *)(__int64 *, __int64, __int64))v10[11];
      v18 = v10[13];
      *((_DWORD *)v10 + 6) = 1;
      *((_BYTE *)v10 + 61) = 0;
      *((_DWORD *)v10 + 29) = v16;
      if ( !v15 )
      {
        ((void (__fastcall *)(__int64 *, __int64, _QWORD, __int64, int))v17)(v14, v10[12], (unsigned int)v12, v18, v16);
        goto LABEL_11;
      }
      v17(v14, v12, v18);
      v4 = v31;
      ++v7;
      a2 = v32;
    }
    else
    {
      v19 = v9 - 3;
      if ( (*(_BYTE *)(v9 - 1) & 2) != 0 && a2 )
      {
        *((_BYTE *)a1 + 1201) = 1;
        break;
      }
      v29 = *((_DWORD *)v19 + 19) != 0;
      *(__int64 *)((char *)a1 + 1412) = 0;
      v20 = (__int64 *)*v9;
      if ( *(__int64 **)(*v9 + 8) != v9 )
        goto LABEL_13;
      v21 = (__int64 **)v9[1];
      if ( *v21 != v9 )
        goto LABEL_13;
      *v21 = v20;
      v20[1] = (__int64)v21;
      ++*((_DWORD *)a1 + 329);
      if ( *((_BYTE *)v19 + 17) )
        ++*((_DWORD *)a1 + 330);
      v22 = *((unsigned __int16 *)v19 + 81);
      v23 = 8 * *((unsigned __int16 *)v19 + 82) - v22 * 8;
      if ( KmclPerformanceCounterTimingCounters )
      {
        PerformanceCounter = KeQueryPerformanceCounter(0);
        v4 = v31;
        v19[12] = PerformanceCounter.QuadPart;
      }
      v24 = *(void (__fastcall **)(__int64, _QWORD, __int64 *, __int64, unsigned int, BOOL))(v4 + 2000);
      if ( *(_BYTE *)(v4 + 1992) )
        v24(v4, *(_QWORD *)(v4 + 2016), v19, (__int64)&v19[v22 + 20], v23, v29);
      else
        ((void (__fastcall *)(__int64, __int64 *, __int64 *, _QWORD, BOOL))v24)(v4, v19, &v19[v22 + 20], v23, v29);
      v25 = *((_DWORD *)a1 + 353);
      if ( v25 )
      {
        v26 = v25 - 1;
        if ( !v26 )
        {
          *((_DWORD *)a1 + 353) = 0;
          InRequeuePacket(a1, v19);
          v8 = 8;
          break;
        }
        v27 = v26 - 1;
        if ( !v27 )
        {
          *((_DWORD *)a1 + 353) = 0;
          InRequeuePacket(a1, v19);
          v8 = 7;
          break;
        }
        if ( v27 == 1 )
        {
          *((_DWORD *)a1 + 353) = 0;
          *((_BYTE *)a1 + 1201) = 1;
          InRequeuePacket(a1, v19);
          break;
        }
      }
LABEL_11:
      v4 = v31;
      ++v7;
      a2 = v32;
    }
  }
  *a4 = v7;
  return v8;
}

```

## disassembly

```asm
0x140002410  mov     rax, rsp
0x140002413  mov     [rax+20h], r9
0x140002417  mov     [rax+10h], dl
0x14000241a  push    rbx
0x14000241b  push    rsi
0x14000241c  push    rdi
0x14000241d  push    r13
0x14000241f  sub     rsp, 58h
0x140002423  mov     r10, [rcx]
0x140002426  mov     esi, r8d
0x140002429  mov     [rax+18h], rbp
0x14000242d  mov     rdi, rcx
0x140002430  mov     [rax-28h], r12
0x140002434  xor     ebx, ebx
0x140002436  mov     [rax-30h], r14
0x14000243a  mov     r13d, 1
0x140002440  mov     [rax-38h], r15
0x140002444  mov     [rsp+78h+arg_0], r10
0x14000244c  mov     r9d, 0C0000023h
0x140002452  cmp     ebx, esi
0x140002454  jnb     loc_140002616
0x14000245a  lea     r8, [rdi+500h]
0x140002461  mov     rax, [r8]
0x140002464  cmp     rax, r8
0x140002467  jz      loc_140002616
0x14000246d  cmp     [rax+10h], r13d
0x140002471  jnz     loc_140002518
0x140002477  test    byte ptr [rax-52h], 2
0x14000247b  lea     r10, [rax-90h]
0x140002482  mov     r8, [rax]
0x140002485  mov     edx, 0
0x14000248a  cmovz   edx, r9d
0x14000248e  cmp     [r8+8], rax
0x140002492  jnz     short loc_140002511
0x140002494  mov     rcx, [rax+8]
0x140002498  cmp     [rcx], rax
0x14000249b  jnz     short loc_140002511
0x14000249d  mov     [rcx], r8
0x1400024a0  mov     [r8+8], rcx
0x1400024a4  mov     rcx, r10
0x1400024a7  test    byte ptr [r10+3Eh], 40h
0x1400024ac  mov     r11, [r10+58h]
0x1400024b0  mov     r9d, [r10+74h]
0x1400024b4  mov     rax, r11
0x1400024b7  mov     r8, [r10+68h]
0x1400024bb  mov     [r10+18h], r13d
0x1400024bf  mov     byte ptr [r10+3Dh], 0
0x1400024c4  mov     [r10+74h], r9d
0x1400024c8  jz      short loc_1400024F5
0x1400024ca  mov     [rsp+78h+var_58], r9d
0x1400024cf  mov     r9, r8
0x1400024d2  mov     r8d, edx
0x1400024d5  mov     rdx, [r10+60h]
0x1400024d9  call    _guard_dispatch_icall
0x1400024de  mov     r10, [rsp+78h+arg_0]
0x1400024e6  inc     ebx
0x1400024e8  movzx   edx, [rsp+78h+arg_8]
0x1400024f0  jmp     loc_14000244C
0x1400024f5  call    _guard_dispatch_icall
0x1400024fa  mov     r10, [rsp+78h+arg_0]
0x140002502  inc     ebx
0x140002504  movzx   edx, [rsp+78h+arg_8]
0x14000250c  jmp     loc_14000244C
0x140002511  mov     ecx, 3
0x140002516  int     29h; Win8: RtlFailFast(ecx)
0x140002518  test    byte ptr [rax-8], 2
0x14000251c  lea     rbp, [rax-18h]
0x140002520  jnz     loc_14000265A
0x140002526  xor     r12d, r12d
0x140002529  cmp     [rbp+4Ch], r12d
0x14000252d  ja      loc_14000266B
0x140002533  mov     qword ptr [rdi+584h], 0
0x14000253e  mov     rcx, [rax]
0x140002541  cmp     [rcx+8], rax
0x140002545  jnz     short loc_140002511
0x140002547  mov     rdx, [rax+8]
0x14000254b  cmp     [rdx], rax
0x14000254e  jnz     short loc_140002511
0x140002550  mov     [rdx], rcx
0x140002553  mov     [rcx+8], rdx
0x140002557  inc     dword ptr [rdi+524h]
0x14000255d  cmp     byte ptr [rbp+11h], 0
0x140002561  jnz     loc_140002673
0x140002567  movzx   r15d, word ptr [rbp+0A2h]
0x14000256f  movzx   r14d, word ptr [rbp+0A4h]
0x140002577  shl     r15d, 3
0x14000257b  shl     r14d, 3
0x14000257f  sub     r14d, r15d
0x140002582  cmp     cs:KmclPerformanceCounterTimingCounters, 0
0x14000258a  jnz     loc_14000267E
0x140002590  mov     rax, [r10+7D0h]
0x140002597  mov     rcx, r10
0x14000259a  mov     r8d, r15d
0x14000259d  add     r8, 0A0h
0x1400025a4  add     r8, rbp
0x1400025a7  cmp     byte ptr [r10+7C8h], 0
0x1400025af  jz      loc_140002645
0x1400025b5  mov     rdx, [r10+7E0h]
0x1400025bc  mov     r9, r8
0x1400025bf  mov     r8, rbp
0x1400025c2  mov     [rsp+78h+var_50], r12d
0x1400025c7  mov     [rsp+78h+var_58], r14d
0x1400025cc  call    _guard_dispatch_icall
0x1400025d1  mov     ecx, [rdi+584h]
0x1400025d7  test    ecx, ecx
0x1400025d9  jz      loc_1400024DE
0x1400025df  sub     ecx, r13d
0x1400025e2  jz      loc_1400026BD
0x1400025e8  sub     ecx, r13d
0x1400025eb  jz      loc_14000269D
0x1400025f1  cmp     ecx, r13d
0x1400025f4  jnz     loc_1400024DE
0x1400025fa  mov     rdx, rbp
0x1400025fd  mov     dword ptr [rdi+584h], 0
0x140002607  mov     rcx, rdi
0x14000260a  mov     [rdi+4B1h], r13b
0x140002611  call    InRequeuePacket
0x140002616  mov     rax, [rsp+78h+arg_18]
0x14000261e  mov     r15, [rsp+78h+var_38]
0x140002623  mov     r14, [rsp+78h+var_30]
0x140002628  mov     r12, [rsp+78h+var_28]
0x14000262d  mov     rbp, [rsp+78h+arg_10]
0x140002635  mov     [rax], ebx
0x140002637  mov     eax, r13d
0x14000263a  add     rsp, 58h
0x14000263e  pop     r13
0x140002640  pop     rdi
0x140002641  pop     rsi
0x140002642  pop     rbx
0x140002643  retn
0x140002645  mov     r9d, r14d
0x140002648  mov     [rsp+78h+var_58], r12d
0x14000264d  mov     rdx, rbp
0x140002650  call    _guard_dispatch_icall
0x140002655  jmp     loc_1400025D1
0x14000265a  test    dl, dl
0x14000265c  jz      loc_140002526
0x140002662  mov     [rdi+4B1h], r13b
0x140002669  jmp     short loc_140002616
0x14000266b  mov     r12d, r13d
0x14000266e  jmp     loc_140002533
0x140002673  inc     dword ptr [rdi+528h]
0x140002679  jmp     loc_140002567
0x14000267e  xor     ecx, ecx; PerformanceFrequency
0x140002680  call    cs:__imp_KeQueryPerformanceCounter
0x140002687  nop     dword ptr [rax+rax+00h]
0x14000268c  mov     r10, [rsp+78h+arg_0]
0x140002694  mov     [rbp+60h], rax
0x140002698  jmp     loc_140002590
0x14000269d  mov     rdx, rbp
0x1400026a0  mov     dword ptr [rdi+584h], 0
0x1400026aa  mov     rcx, rdi
0x1400026ad  call    InRequeuePacket
0x1400026b2  mov     r13d, 7
0x1400026b8  jmp     loc_140002616
0x1400026bd  mov     rdx, rbp
0x1400026c0  mov     dword ptr [rdi+584h], 0
0x1400026ca  mov     rcx, rdi
0x1400026cd  call    InRequeuePacket
0x1400026d2  mov     r13d, 8
0x1400026d8  jmp     loc_140002616
```
