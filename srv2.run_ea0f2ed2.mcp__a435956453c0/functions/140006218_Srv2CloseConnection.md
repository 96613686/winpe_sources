# Srv2CloseConnection

- ea: `0x140006218`
- end: `0x140006574`
- name: `Srv2CloseConnection`
- size: `860`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `10`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140004e50`
- `0x1400055b0`
- `0x140008410`
- `0x140008c40`
- `0x14000af58`
- `0x14000bbb8`
- `0x140020490`
- `0x14005d3d0`
- `0x1400749c0`
- `0x14008c744`

## callees

- `0x140004960`
- `0x140004d04`
- `0x140004dcc`
- `0x140005070`
- `0x140006218`
- `0x14000ae60`
- `0x14001a4d8`
- `0x140023e24`
- `0x1400948c0`

## import_xrefs

- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14000646f`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14000646f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400062c9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400062c9`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000622f`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000622f`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000631b`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400063b2`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400064c0`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000631b`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400063b2`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400064c0`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140006388`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140006402`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400064ff`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140006526`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140006388`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140006402`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400064ff`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140006526`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400062e7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003a6cc`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400062e7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003a6cc`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000648a`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14000648a`

## string_xrefs

- `0x140006450`: `Srv2PostToThreadPool`

## pseudocode

```c
__int64 __fastcall Srv2CloseConnection(char *P, char a2, char a3)
{
  KIRQL CurrentIrql; // r12
  __int64 Timer_high; // r8
  UCHAR v8; // al
  int v9; // ecx
  __int64 v10; // r8
  int v11; // r10d
  __int64 v12; // r11
  KIRQL v13; // r15
  KSPIN_LOCK *v15; // rcx
  __int64 *v16; // rcx
  __int64 v17; // rdx
  __int64 **v18; // rax
  __int64 v19; // rax
  __int64 **v20; // rdx
  KSPIN_LOCK *v21; // rcx
  __int64 v22; // rdx
  char *v23; // rbx
  __int64 v24; // rsi
  __int64 v25; // rcx
  char **v26; // rax
  bool v27; // zf
  __int64 v28; // rbx
  __int64 v29; // rbx
  _QWORD *v30; // rdx
  int v31; // [rsp+20h] [rbp-68h]

  CurrentIrql = KeGetCurrentIrql();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (Timer_high & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_qP(WPP_GLOBAL_Control->AttachedDevice, 21, Timer_high, P, *(_QWORD *)P);
  }
  if ( (Microsoft_Windows_SMBServerEnableBits & 0x20) != 0 )
  {
    v8 = SOCKADDR_SIZE(*((_WORD *)P + 108));
    McTemplateK0jqdqbr3qzr5_EtwWriteTransfer(
      v9,
      v8,
      v10,
      *((_QWORD *)P + 62) + 72,
      a2,
      a3,
      v8,
      v12,
      v11,
      *(_QWORD *)(v10 + 248));
  }
  v13 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)P + 23);
  if ( *((_DWORD *)P + 3) != 220 )
    goto LABEL_6;
  v15 = (KSPIN_LOCK *)(*((_QWORD *)P + 61) + 200LL);
  *((_DWORD *)P + 3) = 221;
  KeAcquireSpinLockAtDpcLevel(v15);
  v16 = (__int64 *)(P + 448);
  v17 = *((_QWORD *)P + 56);
  if ( *(char **)(v17 + 8) != P + 448 )
    goto LABEL_27;
  v18 = (__int64 **)*((_QWORD *)P + 57);
  if ( *v18 != v16 )
    goto LABEL_27;
  *v18 = (__int64 *)v17;
  *(_QWORD *)(v17 + 8) = v18;
  v19 = *((_QWORD *)P + 61) + 224LL;
  v20 = *(__int64 ***)(*((_QWORD *)P + 61) + 232LL);
  if ( *v20 != (__int64 *)v19 )
    goto LABEL_27;
  *v16 = v19;
  *((_QWORD *)P + 57) = v20;
  *v20 = v16;
  *(_QWORD *)(v19 + 8) = v16;
  v21 = (KSPIN_LOCK *)(*((_QWORD *)P + 61) + 200LL);
  P[409] = 1;
  KeReleaseSpinLockFromDpcLevel(v21);
  v23 = P + 464;
  if ( *(char **)v23 != v23 )
  {
    v24 = *(_QWORD *)(*((_QWORD *)P + 62) + 24LL);
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v24 + 80));
    v25 = *(_QWORD *)v23;
    if ( *(char **)(*(_QWORD *)v23 + 8LL) == v23 )
    {
      v26 = (char **)*((_QWORD *)P + 59);
      if ( *v26 == v23 )
      {
        *v26 = (char *)v25;
        *(_QWORD *)(v25 + 8) = v26;
        *((_QWORD *)P + 59) = P + 464;
        *(_QWORD *)v23 = v23;
        Srv2DereferenceConnection(P);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v24 + 24), 0xFFFFFFFF) != 1 )
        {
          KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v24 + 80));
          goto LABEL_16;
        }
        KeAcquireSpinLockAtDpcLevel(&Smb2ClientPendingListLock);
        v30 = (_QWORD *)qword_14004BEB8;
        if ( *(__int64 **)qword_14004BEB8 == &Smb2ClientPendingList )
        {
          *(_QWORD *)(v24 + 64) = &Smb2ClientPendingList;
          *(_QWORD *)(v24 + 72) = v30;
          *v30 = v24 + 64;
          qword_14004BEB8 = v24 + 64;
          KeReleaseSpinLockFromDpcLevel(&Smb2ClientPendingListLock);
          *(_QWORD *)(v24 + 120) = *(_QWORD *)(v24 + 128) + MEMORY[0xFFFFF78000000014];
          KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v24 + 80));
          Smb2SignalScavengerCheck(0);
          goto LABEL_16;
        }
      }
    }
LABEL_27:
    __fastfail(3u);
  }
LABEL_16:
  if ( CurrentIrql < 2u )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)P + 23, v13);
    Srv2CloseConnectionInternal(P);
    return 0;
  }
  if ( !P[408] )
  {
    v27 = *((_DWORD *)P + 2) == 5;
    *((_QWORD *)P + 6) = Srv2CloseConnectionInternal;
    P[408] = 1;
    *((_DWORD *)P + 18) = 0;
    if ( v27 )
    {
      LOBYTE(v31) = 1;
      LOBYTE(v22) = 1;
      SRV2_PERF_ENTER_EX(P + 584, v22, 391, "Srv2PostToThreadPool", v31);
    }
    v28 = *(_QWORD *)(*((_QWORD *)P + 8) + 136LL);
    v29 = *(_QWORD *)(v28 + 8LL * KeGetCurrentNodeNumber() + 8);
    if ( !ExpInterlockedPushEntrySList((PSLIST_HEADER)v29, (PSLIST_ENTRY)P + 2) && *(_WORD *)(v29 + 66) )
      RfspThreadPoolNodeWakeIdleWorker((struct _KEVENT *)v29);
  }
LABEL_6:
  KeReleaseSpinLock((PKSPIN_LOCK)P + 23, v13);
  return 0;
}

```

## disassembly

```asm
0x140006218  push    rbx
0x14000621a  push    rbp
0x14000621b  push    rsi
0x14000621c  push    rdi
0x14000621d  push    r12
0x14000621f  push    r14
0x140006221  push    r15
0x140006223  sub     rsp, 50h
0x140006227  mov     ebx, r8d
0x14000622a  mov     esi, edx
0x14000622c  mov     rdi, rcx
0x14000622f  call    cs:__imp_KeGetCurrentIrql
0x140006236  nop     dword ptr [rax+rax+00h]
0x14000623b  mov     r12b, al
0x14000623e  mov     rcx, cs:WPP_GLOBAL_Control
0x140006245  lea     rax, WPP_GLOBAL_Control
0x14000624c  cmp     rcx, rax
0x14000624f  jz      short loc_14000625F
0x140006251  mov     r8d, [rcx+2Ch]
0x140006255  test    r8b, 1
0x140006259  jnz     loc_14000653E
0x14000625f  test    cs:Microsoft_Windows_SMBServerEnableBits, 20h
0x140006266  jz      short loc_1400062BF
0x140006268  mov     r8, [rdi+1E8h]
0x14000626f  lea     r11, [rdi+0D8h]
0x140006276  movzx   ecx, word ptr [r11]; af
0x14000627a  movzx   r10d, word ptr [r8+0F0h]
0x140006282  shr     r10d, 1
0x140006285  call    SOCKADDR_SIZE
0x14000628a  mov     r9, [rdi+1F0h]
0x140006291  movzx   edx, al
0x140006294  add     r9, 48h ; 'H'
0x140006298  mov     rax, [r8+0F8h]
0x14000629f  mov     [rsp+88h+var_40], rax
0x1400062a4  mov     [rsp+88h+var_48], r10d
0x1400062a9  mov     [rsp+88h+var_50], r11
0x1400062ae  mov     [rsp+88h+var_58], edx
0x1400062b2  mov     [rsp+88h+var_60], ebx
0x1400062b6  mov     dword ptr [rsp+88h+var_68], esi
0x1400062ba  call    McTemplateK0jqdqbr3qzr5_EtwWriteTransfer
0x1400062bf  lea     rbp, [rdi+0B8h]
0x1400062c6  mov     rcx, rbp; SpinLock
0x1400062c9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400062d0  nop     dword ptr [rax+rax+00h]
0x1400062d5  cmp     dword ptr [rdi+0Ch], 0DCh
0x1400062dc  mov     r15b, al
0x1400062df  jz      short loc_140006305
0x1400062e1  mov     dl, r15b; NewIrql
0x1400062e4  mov     rcx, rbp; SpinLock
0x1400062e7  call    cs:__imp_KeReleaseSpinLock
0x1400062ee  nop     dword ptr [rax+rax+00h]
0x1400062f3  xor     eax, eax
0x1400062f5  add     rsp, 50h
0x1400062f9  pop     r15
0x1400062fb  pop     r14
0x1400062fd  pop     r12
0x1400062ff  pop     rdi
0x140006300  pop     rsi
0x140006301  pop     rbp
0x140006302  pop     rbx
0x140006303  retn
0x140006305  mov     rcx, [rdi+1E8h]
0x14000630c  mov     ebx, 0C8h
0x140006311  add     rcx, rbx; SpinLock
0x140006314  mov     dword ptr [rdi+0Ch], 0DDh
0x14000631b  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140006322  nop     dword ptr [rax+rax+00h]
0x140006327  lea     rcx, [rdi+1C0h]
0x14000632e  mov     rdx, [rcx]
0x140006331  cmp     [rdx+8], rcx
0x140006335  jnz     loc_14000656D
0x14000633b  mov     rax, [rcx+8]
0x14000633f  cmp     [rax], rcx
0x140006342  jnz     loc_14000656D
0x140006348  mov     [rax], rdx
0x14000634b  mov     [rdx+8], rax
0x14000634f  mov     rax, [rdi+1E8h]
0x140006356  add     rax, 0E0h
0x14000635c  mov     rdx, [rax+8]
0x140006360  cmp     [rdx], rax
0x140006363  jnz     loc_14000656D
0x140006369  mov     [rcx], rax
0x14000636c  mov     [rcx+8], rdx
0x140006370  mov     [rdx], rcx
0x140006373  mov     [rax+8], rcx
0x140006377  mov     rcx, [rdi+1E8h]
0x14000637e  add     rcx, rbx; SpinLock
0x140006381  mov     byte ptr [rdi+199h], 1
0x140006388  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000638f  nop     dword ptr [rax+rax+00h]
0x140006394  lea     rbx, [rdi+1D0h]
0x14000639b  cmp     [rbx], rbx
0x14000639e  jz      short loc_14000640E
0x1400063a0  mov     rax, [rdi+1F0h]
0x1400063a7  mov     rsi, [rax+18h]
0x1400063ab  lea     r14, [rsi+50h]
0x1400063af  mov     rcx, r14; SpinLock
0x1400063b2  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400063b9  nop     dword ptr [rax+rax+00h]
0x1400063be  mov     rcx, [rbx]
0x1400063c1  cmp     [rcx+8], rbx
0x1400063c5  jnz     loc_14000656D
0x1400063cb  mov     rax, [rbx+8]
0x1400063cf  cmp     [rax], rbx
0x1400063d2  jnz     loc_14000656D
0x1400063d8  mov     [rax], rcx
0x1400063db  mov     [rcx+8], rax
0x1400063df  mov     rcx, rdi; P
0x1400063e2  mov     [rbx+8], rbx
0x1400063e6  mov     [rbx], rbx
0x1400063e9  call    Srv2DereferenceConnection
0x1400063ee  or      eax, 0FFFFFFFFh
0x1400063f1  lock xadd [rsi+18h], eax
0x1400063f6  cmp     eax, 1
0x1400063f9  jz      loc_1400064B9
0x1400063ff  mov     rcx, r14; SpinLock
0x140006402  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140006409  nop     dword ptr [rax+rax+00h]
0x14000640e  cmp     r12b, 2
0x140006412  jb      loc_14003A6C6
0x140006418  cmp     byte ptr [rdi+198h], 0
0x14000641f  jnz     loc_1400062E1
0x140006425  cmp     dword ptr [rdi+8], 5
0x140006429  lea     rax, Srv2CloseConnectionInternal
0x140006430  mov     [rdi+30h], rax
0x140006434  mov     byte ptr [rdi+198h], 1
0x14000643b  mov     dword ptr [rdi+48h], 0
0x140006442  jnz     short loc_140006464
0x140006444  lea     rcx, [rdi+248h]
0x14000644b  mov     byte ptr [rsp+88h+var_68], 1
0x140006450  lea     r9, SourceString; "Srv2PostToThreadPool"
0x140006457  mov     r8d, 187h
0x14000645d  mov     dl, 1
0x14000645f  call    SRV2_PERF_ENTER_EX
0x140006464  mov     rax, [rdi+40h]
0x140006468  mov     rbx, [rax+88h]
0x14000646f  call    cs:__imp_KeGetCurrentNodeNumber
0x140006476  nop     dword ptr [rax+rax+00h]
0x14000647b  movzx   eax, ax
0x14000647e  lea     rdx, [rdi+20h]; ListEntry
0x140006482  mov     rbx, [rbx+rax*8+8]
0x140006487  mov     rcx, rbx; ListHead
0x14000648a  call    cs:__imp_ExpInterlockedPushEntrySList
0x140006491  nop     dword ptr [rax+rax+00h]
0x140006496  test    rax, rax
0x140006499  jnz     loc_1400062E1
0x14000649f  movzx   edx, word ptr [rbx+42h]
0x1400064a3  cmp     ax, dx
0x1400064a6  jz      loc_1400062E1
0x1400064ac  mov     rcx, rbx
0x1400064af  call    RfspThreadPoolNodeWakeIdleWorker
0x1400064b4  jmp     loc_1400062E1
0x1400064b9  lea     rcx, Smb2ClientPendingListLock; SpinLock
0x1400064c0  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400064c7  nop     dword ptr [rax+rax+00h]
0x1400064cc  mov     rdx, cs:qword_14004BEB8
0x1400064d3  lea     rcx, Smb2ClientPendingList
0x1400064da  cmp     [rdx], rcx
0x1400064dd  jnz     loc_14000656D
0x1400064e3  lea     rax, [rsi+40h]
0x1400064e7  mov     [rax], rcx
0x1400064ea  lea     rcx, Smb2ClientPendingListLock; SpinLock
0x1400064f1  mov     [rax+8], rdx
0x1400064f5  mov     [rdx], rax
0x1400064f8  mov     cs:qword_14004BEB8, rax
0x1400064ff  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140006506  nop     dword ptr [rax+rax+00h]
0x14000650b  mov     rdx, 0FFFFF78000000014h
0x140006515  mov     rcx, r14; SpinLock
0x140006518  mov     rdx, [rdx]
0x14000651b  add     rdx, [rsi+80h]
0x140006522  mov     [rsi+78h], rdx
0x140006526  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000652d  nop     dword ptr [rax+rax+00h]
0x140006532  xor     ecx, ecx
0x140006534  call    Smb2SignalScavengerCheck
0x140006539  jmp     loc_14000640E
0x14000653e  cmp     byte ptr [rcx+29h], 2
0x140006542  jb      loc_14000625F
0x140006548  mov     rax, [rdi]
0x14000654b  mov     edx, 15h
0x140006550  mov     rcx, cs:WPP_GLOBAL_Control
0x140006557  mov     r9, rdi
0x14000655a  mov     [rsp+88h+var_68], rax
0x14000655f  mov     rcx, [rcx+18h]
0x140006563  call    WPP_SF_qP
0x140006568  jmp     loc_14000625F
0x14000656d  mov     ecx, 3
0x140006572  int     29h; Win8: RtlFailFast(ecx)
0x14003a6c6  mov     dl, r15b; NewIrql
0x14003a6c9  mov     rcx, rbp; SpinLock
0x14003a6cc  call    cs:__imp_KeReleaseSpinLock
0x14003a6d3  nop     dword ptr [rax+rax+00h]
0x14003a6d8  mov     rcx, rdi; P
0x14003a6db  call    Srv2CloseConnectionInternal
0x14003a6e0  nop
0x14003a6e1  jmp     loc_1400062F3
```
