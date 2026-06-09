# OutSendCompletionAtDpcLevel

- ea: `0x140005750`
- end: `0x140005a72`
- name: `OutSendCompletionAtDpcLevel`
- size: `802`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400089a8`

## callees

- `0x140003ea0`
- `0x140004790`
- `0x140005230`
- `0x140005750`
- `0x140008f90`
- `0x14000a160`
- `0x140010d1c`
- `0x140011f80`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140005779`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140005779`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140005a49`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140005a49`

## pseudocode

```c
__int64 __fastcall OutSendCompletionAtDpcLevel(__int64 a1, __int64 a2, const void *a3, unsigned int a4, char a5)
{
  size_t v6; // rbp
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r15
  int v12; // ebx
  __int64 v13; // r14
  unsigned int v14; // r8d
  _DWORD *v15; // r11
  unsigned int v16; // ecx
  int v17; // edx
  unsigned int v18; // r8d
  unsigned int v19; // r9d
  __int64 v20; // r10
  unsigned int v21; // edx
  unsigned int v22; // ecx
  unsigned int v23; // eax
  unsigned int v24; // ecx
  int v25; // edx
  unsigned int v26; // r8d
  unsigned int v27; // r9d
  unsigned int v28; // eax
  int v29; // eax
  int v30; // r9d
  _DWORD *v31; // rcx
  unsigned int v32; // edx
  int v33; // r8d
  unsigned int v34; // eax
  unsigned __int8 v35; // bl
  signed __int32 v37[8]; // [rsp+0h] [rbp-78h] BYREF
  __int64 v38; // [rsp+40h] [rbp-38h]
  __int64 v39; // [rsp+80h] [rbp+8h]

  v6 = a4;
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(a1 + 256));
  if ( *(_DWORD *)(a1 + 264) == 1 )
  {
    v10 = *(_QWORD *)(a2 + 40);
    v11 = (unsigned int)(v6 + 16);
    v39 = v10;
    if ( (unsigned int)v11 > 0x7FFF8 )
    {
      v12 = -1073741811;
      goto LABEL_36;
    }
    v13 = *(unsigned int *)(a1 + 192);
    v14 = *(_DWORD *)(a1 + 80);
    v15 = (_DWORD *)(v13 + *(_QWORD *)(a1 + 72));
    v38 = ((_DWORD)v6 + 23) & 0xFFFFFFF8;
    _m_prefetchw(v15);
    v16 = *(_DWORD *)(a1 + 196) - v13 - 8;
    if ( v16 >= v14 )
      v16 += v14;
    if ( v16 < (int)v38 + 8 )
    {
      if ( !(unsigned __int8)PkpValidatePointer(v14, *(unsigned int *)(*(_QWORD *)(a1 + 64) + 4LL)) )
      {
        v12 = -1073741566;
LABEL_35:
        LODWORD(v10) = v39;
LABEL_36:
        if ( (Microsoft_Windows_Hyper_V_KMCL_ChildEnableBits & 2) != 0 )
          McTemplateK0jjxth_EtwWriteTransfer(
            *(_DWORD *)a1 + 2752,
            (unsigned int)VMBUS_SEND_PACKET,
            v10,
            *(_DWORD *)a1 + 2768,
            *(_QWORD *)a1 + 2752LL,
            v10,
            1,
            *(_WORD *)(*(_QWORD *)a1 + 3280LL));
        if ( v12 >= 0 )
          ++*(_DWORD *)(a1 + 528);
        if ( (int)OutpProcessRingResult(a1, (unsigned int)v12) >= 0 )
          goto LABEL_45;
        goto LABEL_41;
      }
      *(_DWORD *)(a1 + 196) = v17;
      v21 = v17 - v13 - 8;
      if ( v21 >= v18 )
        v21 += v18;
      if ( v21 < v19 )
      {
        if ( v19 >= v18 )
        {
          v12 = -1073741811;
          goto LABEL_35;
        }
        if ( !*(_DWORD *)(a1 + 200)
          && (unsigned int)(*(_DWORD *)(a1 + 136) + *(_DWORD *)(a1 + 204) - *(_DWORD *)(a1 + 140)) < 0x40 )
        {
          _InterlockedIncrement((volatile signed __int32 *)(a1 + 204));
        }
        v22 = v13 - *(_DWORD *)(a1 + 192);
        if ( v22 >= v18 )
          v22 += v18;
        v23 = v18 - 8;
        v24 = v19 + v22;
        if ( v24 < v18 )
          v23 = v24;
        *(_DWORD *)(v20 + 12) = v23;
        *(_DWORD *)(a1 + 200) = v38;
        _InterlockedOr(v37, 0);
        if ( !(unsigned __int8)PkpValidatePointer(v18, *(unsigned int *)(v20 + 4)) )
        {
          v12 = -1073741566;
          goto LABEL_35;
        }
        *(_DWORD *)(a1 + 196) = v25;
        v28 = v25 - v13 - 8;
        if ( v28 >= v26 )
          v28 += v26;
        if ( v28 < v27 )
        {
          v12 = -2147483643;
          goto LABEL_35;
        }
      }
    }
    *v15 = 131083;
    *((_WORD *)v15 + 2) = (unsigned __int64)(v11 + 7) >> 3;
    *((_WORD *)v15 + 3) = 0;
    *((_QWORD *)v15 + 1) = v39;
    memmove(v15 + 4, a3, v6);
    v29 = PkWritePacketFooter(a1 + 64, (unsigned int)v13, (unsigned int)v11);
    v30 = *(_DWORD *)(a1 + 192);
    v31 = *(_DWORD **)(a1 + 64);
    v32 = *(_DWORD *)(a1 + 80);
    *(_DWORD *)(a1 + 192) = v29;
    *v31 = v29;
    _InterlockedOr(v37, 0);
    v33 = v31[2];
    v34 = v31[1];
    if ( v34 >= v32 || (v34 & 7) != 0 )
    {
      v12 = -1073741566;
      goto LABEL_35;
    }
    *(_DWORD *)(a1 + 196) = v34;
    if ( v30 == v34 )
    {
      if ( !v33 )
      {
        v12 = 532;
        goto LABEL_35;
      }
      ++**(_QWORD **)(a1 + 216);
    }
    v12 = 0;
    goto LABEL_35;
  }
LABEL_41:
  if ( !a5 )
  {
    *(_QWORD *)(a2 + 48) = a3;
    goto LABEL_47;
  }
  if ( (unsigned int)v6 <= *(_DWORD *)(a2 + 24) )
  {
    memmove(*(void **)(a2 + 48), a3, v6);
LABEL_47:
    *(_DWORD *)(a2 + 24) = v6;
    *(_DWORD *)(a2 + 16) = 2;
    OutpEnqueuePacket(a1, a2);
    v35 = 0;
    goto LABEL_48;
  }
  MicrosoftTelemetryAssertTriggeredArgsKM(v9, (unsigned int)v6);
LABEL_45:
  v35 = 1;
LABEL_48:
  KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(a1 + 256));
  return v35;
}

```

## disassembly

```asm
0x140005750  mov     [rsp+arg_10], rbx
0x140005755  mov     [rsp+arg_18], rbp
0x14000575a  push    rsi
0x14000575b  push    rdi
0x14000575c  push    r12
0x14000575e  push    r13
0x140005760  push    r14
0x140005762  sub     rsp, 50h
0x140005766  mov     rdi, rcx
0x140005769  mov     ebp, r9d
0x14000576c  add     rcx, 100h; SpinLock
0x140005773  mov     r12, r8
0x140005776  mov     rsi, rdx
0x140005779  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140005780  nop     dword ptr [rax+rax+00h]
0x140005785  cmp     dword ptr [rdi+108h], 1
0x14000578c  mov     r14d, 2
0x140005792  jnz     loc_1400059FB
0x140005798  mov     r8, [rsi+28h]
0x14000579c  mov     [rsp+78h+arg_8], r15
0x1400057a4  lea     r15d, [rbp+10h]
0x1400057a8  mov     [rsp+78h+arg_0], r8
0x1400057b0  cmp     r15d, 7FFF8h
0x1400057b7  jbe     short loc_1400057C3
0x1400057b9  mov     ebx, 0C000000Dh
0x1400057be  jmp     loc_140005997
0x1400057c3  mov     r14d, [rdi+0C0h]
0x1400057ca  lea     eax, [r15+7]
0x1400057ce  mov     r11, [rdi+48h]
0x1400057d2  and     eax, 0FFFFFFF8h
0x1400057d5  mov     r8d, [rdi+50h]
0x1400057d9  add     r11, r14
0x1400057dc  mov     [rsp+78h+var_38], rax
0x1400057e1  lea     r9d, [rax+8]
0x1400057e5  prefetchw byte ptr [r11]
0x1400057e9  mov     ecx, [rdi+0C4h]
0x1400057ef  sub     ecx, r14d
0x1400057f2  add     ecx, 0FFFFFFF8h
0x1400057f5  cmp     ecx, r8d
0x1400057f8  lea     eax, [rcx+r8]
0x1400057fc  cmovnb  ecx, eax
0x1400057ff  cmp     ecx, r9d
0x140005802  jnb     loc_1400058EE
0x140005808  mov     r10, [rdi+40h]
0x14000580c  mov     ecx, r8d
0x14000580f  mov     edx, [r10+4]
0x140005813  call    PkpValidatePointer
0x140005818  test    al, al
0x14000581a  jnz     short loc_140005826
0x14000581c  mov     ebx, 0C0000102h
0x140005821  jmp     loc_140005989
0x140005826  mov     [rdi+0C4h], edx
0x14000582c  sub     edx, r14d
0x14000582f  add     edx, 0FFFFFFF8h
0x140005832  cmp     edx, r8d
0x140005835  jb      short loc_14000583A
0x140005837  add     edx, r8d
0x14000583a  cmp     edx, r9d
0x14000583d  jnb     loc_1400058EE
0x140005843  cmp     r9d, r8d
0x140005846  jb      short loc_140005852
0x140005848  mov     ebx, 0C000000Dh
0x14000584d  jmp     loc_140005989
0x140005852  cmp     dword ptr [rdi+0C8h], 0
0x140005859  jnz     short loc_14000587D
0x14000585b  mov     edx, [rdi+88h]
0x140005861  mov     ecx, [rdi+0CCh]
0x140005867  mov     eax, [rdi+8Ch]
0x14000586d  sub     ecx, eax
0x14000586f  add     ecx, edx
0x140005871  cmp     ecx, 40h ; '@'
0x140005874  jnb     short loc_14000587D
0x140005876  lock inc dword ptr [rdi+0CCh]
0x14000587d  mov     ecx, r14d
0x140005880  sub     ecx, [rdi+0C0h]
0x140005886  cmp     ecx, r8d
0x140005889  lea     eax, [rcx+r8]
0x14000588d  cmovnb  ecx, eax
0x140005890  lea     eax, [r8-8]
0x140005894  add     ecx, r9d
0x140005897  cmp     ecx, r8d
0x14000589a  cmovb   eax, ecx
0x14000589d  mov     [r10+0Ch], eax
0x1400058a1  mov     rax, [rsp+78h+var_38]
0x1400058a6  mov     [rdi+0C8h], eax
0x1400058ac  lock or [rsp+78h+var_78], 0
0x1400058b1  mov     edx, [r10+4]
0x1400058b5  mov     ecx, r8d
0x1400058b8  call    PkpValidatePointer
0x1400058bd  test    al, al
0x1400058bf  jnz     short loc_1400058CB
0x1400058c1  mov     ebx, 0C0000102h
0x1400058c6  jmp     loc_140005989
0x1400058cb  mov     [rdi+0C4h], edx
0x1400058d1  sub     edx, r14d
0x1400058d4  lea     eax, [rdx-8]
0x1400058d7  cmp     eax, r8d
0x1400058da  jb      short loc_1400058DF
0x1400058dc  add     eax, r8d
0x1400058df  cmp     eax, r9d
0x1400058e2  jnb     short loc_1400058EE
0x1400058e4  mov     ebx, 80000005h
0x1400058e9  jmp     loc_140005989
0x1400058ee  nop
0x1400058ef  lea     rax, [r15+7]
0x1400058f3  shr     rax, 3
0x1400058f7  lea     rcx, [r11+10h]; void *
0x1400058fb  mov     dword ptr [r11], 2000Bh
0x140005902  mov     r8, rbp; Size
0x140005905  mov     [r11+4], ax
0x14000590a  mov     rdx, r12; Src
0x14000590d  xor     eax, eax
0x14000590f  mov     [r11+6], ax
0x140005914  mov     rax, [rsp+78h+arg_0]
0x14000591c  mov     [r11+8], rax
0x140005920  call    memmove
0x140005925  mov     r8d, r15d
0x140005928  lea     rcx, [rdi+40h]
0x14000592c  mov     edx, r14d
0x14000592f  call    PkWritePacketFooter
0x140005934  mov     r9d, [rdi+0C0h]
0x14000593b  mov     rcx, [rdi+40h]
0x14000593f  mov     edx, [rdi+50h]
0x140005942  mov     [rdi+0C0h], eax
0x140005948  mov     [rcx], eax
0x14000594a  lock or [rsp+78h+var_78], 0
0x14000594f  mov     r8d, [rcx+8]
0x140005953  mov     eax, [rcx+4]
0x140005956  cmp     eax, edx
0x140005958  jnb     short loc_140005983
0x14000595a  test    al, 7
0x14000595c  jnz     short loc_140005983
0x14000595e  mov     [rdi+0C4h], eax
0x140005964  cmp     r9d, eax
0x140005967  jnz     short loc_14000597F
0x140005969  test    r8d, r8d
0x14000596c  jnz     short loc_140005975
0x14000596e  mov     ebx, 214h
0x140005973  jmp     short loc_140005988
0x140005975  mov     rax, [rdi+0D8h]
0x14000597c  inc     qword ptr [rax]
0x14000597f  xor     ebx, ebx
0x140005981  jmp     short loc_140005988
0x140005983  mov     ebx, 0C0000102h
0x140005988  nop
0x140005989  mov     r8, [rsp+78h+arg_0]
0x140005991  mov     r14d, 2
0x140005997  test    cs:Microsoft_Windows_Hyper_V_KMCL_ChildEnableBits, 2
0x14000599e  mov     r15, [rsp+78h+arg_8]
0x1400059a6  jz      short loc_1400059E3
0x1400059a8  mov     rax, [rdi]
0x1400059ab  lea     rdx, VMBUS_SEND_PACKET
0x1400059b2  lea     rcx, [rax+0AC0h]
0x1400059b9  lea     r9, [rax+0AD0h]
0x1400059c0  movzx   eax, word ptr [rax+0CD0h]
0x1400059c7  mov     [rsp+78h+var_40], ax
0x1400059cc  mov     [rsp+78h+var_48], 1
0x1400059d4  mov     [rsp+78h+var_50], r8
0x1400059d9  mov     [rsp+78h+var_58], rcx
0x1400059de  call    McTemplateK0jjxth_EtwWriteTransfer
0x1400059e3  test    ebx, ebx
0x1400059e5  js      short loc_1400059ED
0x1400059e7  inc     dword ptr [rdi+210h]
0x1400059ed  mov     edx, ebx
0x1400059ef  mov     rcx, rdi
0x1400059f2  call    OutpProcessRingResult
0x1400059f7  test    eax, eax
0x1400059f9  jns     short loc_140005A26
0x1400059fb  cmp     [rsp+78h+arg_20], 0
0x140005a03  jz      short loc_140005A2A
0x140005a05  mov     r8d, [rsi+18h]
0x140005a09  cmp     ebp, r8d
0x140005a0c  ja      short loc_140005A1F
0x140005a0e  mov     rcx, [rsi+30h]; void *
0x140005a12  mov     r8, rbp; Size
0x140005a15  mov     rdx, r12; Src
0x140005a18  call    memmove
0x140005a1d  jmp     short loc_140005A2E
0x140005a1f  mov     edx, ebp
0x140005a21  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x140005a26  mov     bl, 1
0x140005a28  jmp     short loc_140005A42
0x140005a2a  mov     [rsi+30h], r12
0x140005a2e  mov     rdx, rsi
0x140005a31  mov     [rsi+18h], ebp
0x140005a34  mov     rcx, rdi
0x140005a37  mov     [rsi+10h], r14d
0x140005a3b  call    OutpEnqueuePacket
0x140005a40  xor     bl, bl
0x140005a42  lea     rcx, [rdi+100h]; SpinLock
0x140005a49  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140005a50  nop     dword ptr [rax+rax+00h]
0x140005a55  lea     r11, [rsp+78h+var_28]
0x140005a5a  movzx   eax, bl
0x140005a5d  mov     rbx, [r11+40h]
0x140005a61  mov     rbp, [r11+48h]
0x140005a65  mov     rsp, r11
0x140005a68  pop     r14
0x140005a6a  pop     r13
0x140005a6c  pop     r12
0x140005a6e  pop     rdi
0x140005a6f  pop     rsi
0x140005a70  retn
```
