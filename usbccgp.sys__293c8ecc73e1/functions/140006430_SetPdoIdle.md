# SetPdoIdle

- ea: `0x140006430`
- end: `0x14000662a`
- name: `SetPdoIdle`
- size: `506`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140004640`
- `0x140005f60`
- `0x140005fc4`
- `0x14000d630`
- `0x14000e360`
- `0x14000ead0`
- `0x14002ced0`

## callees

- `0x140006430`
- `0x14000adbc`
- `0x140012474`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006460`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006538`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006460`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006538`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000659d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000660b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000659d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000660b`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentActive` at `0x14000657d`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentActive` at `0x1400065dd`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentActive` at `0x14000657d`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentActive` at `0x1400065dd`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentInactive` at `0x14000658b`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentInactive` at `0x1400065eb`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentInactive` at `0x14000658b`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_ComponentInactive` at `0x1400065eb`

## pseudocode

```c
char __fastcall SetPdoIdle(__int64 a1, __int64 a2, int a3, unsigned __int8 a4, char a5)
{
  KIRQL v5; // r12
  int v6; // esi
  int v10; // edx
  char v11; // r15
  int v12; // edi
  int v13; // eax
  KIRQL v14; // al
  int v15; // r8d
  KIRQL v16; // r14
  __int64 v17; // rcx
  int v18; // edx
  __int64 v19; // rcx

  v5 = 0;
  v6 = a4;
  if ( a5 )
    v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 696));
  v10 = *(_DWORD *)(a2 + 296);
  v11 = 1;
  v12 = v10 & 0x17;
  if ( a3 == 1 )
  {
    v13 = ((unsigned __int8)v10 ^ (unsigned __int8)(4 * v6)) & 4;
    goto LABEL_14;
  }
  if ( a3 == 2 )
  {
    v13 = (v10 ^ v6) & 1;
LABEL_14:
    v10 ^= v13;
    *(_DWORD *)(a2 + 296) = v10;
    goto LABEL_15;
  }
  if ( a3 != 3 )
  {
    if ( a3 != 4 )
      goto LABEL_15;
    v13 = ((unsigned __int8)v10 ^ (unsigned __int8)(16 * v6)) & 0x10;
    goto LABEL_14;
  }
  if ( (*(_DWORD *)(a1 + 1224) & 1) != 0 )
    v10 &= ~2u;
  else
    v10 ^= ((unsigned __int8)v10 ^ (unsigned __int8)(2 * v6)) & 2;
  *(_DWORD *)(a2 + 296) = v10;
LABEL_15:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qDL(*(_QWORD *)(a1 + 1368), v10, a3, a4);
  if ( v12 || (*(_DWORD *)(a2 + 296) & 0x17) == 0 )
    v11 = 0;
  if ( (unsigned int)Feature_UHSSRI01__private_IsEnabledDeviceUsageNoInline() )
  {
    v14 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 416));
    v15 = *(_DWORD *)(a2 + 296);
    v16 = v14;
    if ( (v12 != 0) != ((v15 & 0x17) != 0) )
    {
      v17 = *(_QWORD *)(a2 + 424);
      if ( v17 )
      {
        if ( (v15 & 7) != 0 || (v15 & 0x10) != 0 )
          SleepstudyHelper_ComponentInactive();
        else
          SleepstudyHelper_ComponentActive(v17);
      }
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 416), v16);
  }
  else
  {
    v18 = *(_DWORD *)(a2 + 296);
    if ( (v12 != 0) != ((v18 & 0x17) != 0) )
    {
      v19 = *(_QWORD *)(a2 + 424);
      if ( v19 )
      {
        if ( (v18 & 7) != 0 || (v18 & 0x10) != 0 )
          SleepstudyHelper_ComponentInactive();
        else
          SleepstudyHelper_ComponentActive(v19);
      }
    }
  }
  if ( a5 )
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 696), v5);
  return v11;
}

```

## disassembly

```asm
0x140006430  push    rbx
0x140006432  push    rbp
0x140006433  push    rsi
0x140006434  push    rdi
0x140006435  push    r12
0x140006437  push    r14
0x140006439  push    r15
0x14000643b  sub     rsp, 40h
0x14000643f  xor     r12b, r12b
0x140006442  movzx   esi, r9b
0x140006446  mov     r14d, r8d
0x140006449  mov     rbx, rdx
0x14000644c  mov     rbp, rcx
0x14000644f  cmp     [rsp+78h+arg_20], r12b
0x140006457  jz      short loc_14000646F
0x140006459  add     rcx, 2B8h; SpinLock
0x140006460  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006467  nop     dword ptr [rax+rax+00h]
0x14000646c  mov     r12b, al
0x14000646f  mov     edx, [rbx+128h]
0x140006475  mov     ecx, r14d
0x140006478  mov     edi, edx
0x14000647a  mov     r15d, 1
0x140006480  and     edi, 17h
0x140006483  sub     ecx, r15d
0x140006486  jz      short loc_1400064CF
0x140006488  sub     ecx, r15d
0x14000648b  jz      short loc_1400064C6
0x14000648d  sub     ecx, r15d
0x140006490  jz      short loc_1400064A3
0x140006492  cmp     ecx, r15d
0x140006495  jnz     short loc_1400064E3
0x140006497  mov     eax, esi
0x140006499  shl     eax, 4
0x14000649c  xor     eax, edx
0x14000649e  and     eax, 10h
0x1400064a1  jmp     short loc_1400064D9
0x1400064a3  mov     eax, [rbp+4C8h]
0x1400064a9  test    r15b, al
0x1400064ac  jnz     short loc_1400064BB
0x1400064ae  mov     eax, esi
0x1400064b0  add     eax, eax
0x1400064b2  xor     eax, edx
0x1400064b4  and     eax, 2
0x1400064b7  xor     edx, eax
0x1400064b9  jmp     short loc_1400064BE
0x1400064bb  and     edx, 0FFFFFFFDh
0x1400064be  mov     [rbx+128h], edx
0x1400064c4  jmp     short loc_1400064E3
0x1400064c6  mov     eax, esi
0x1400064c8  xor     eax, edx
0x1400064ca  and     eax, r15d
0x1400064cd  jmp     short loc_1400064D9
0x1400064cf  mov     eax, esi
0x1400064d1  shl     eax, 2
0x1400064d4  xor     eax, edx
0x1400064d6  and     eax, 4
0x1400064d9  xor     eax, edx
0x1400064db  mov     edx, eax
0x1400064dd  mov     [rbx+128h], eax
0x1400064e3  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400064ea  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400064f1  jz      short loc_140006514
0x1400064f3  mov     rax, [rbx+0E0h]
0x1400064fa  mov     rcx, [rbp+558h]
0x140006501  mov     [rsp+78h+var_40], r14d
0x140006506  mov     [rsp+78h+var_48], edx
0x14000650a  mov     [rsp+78h+var_50], rax
0x14000650f  call    WPP_RECORDER_SF_qDL
0x140006514  test    edi, edi
0x140006516  jnz     short loc_140006522
0x140006518  mov     eax, [rbx+128h]
0x14000651e  test    al, 17h
0x140006520  jnz     short loc_140006525
0x140006522  xor     r15b, r15b
0x140006525  call    Feature_UHSSRI01__private_IsEnabledDeviceUsageNoInline
0x14000652a  test    eax, eax
0x14000652c  jz      short loc_1400065AB
0x14000652e  lea     rsi, [rbx+1A0h]
0x140006535  mov     rcx, rsi; SpinLock
0x140006538  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000653f  nop     dword ptr [rax+rax+00h]
0x140006544  mov     r8d, [rbx+128h]
0x14000654b  mov     edx, 0
0x140006550  test    r8b, 17h
0x140006554  mov     r14b, al
0x140006557  setnz   dl
0x14000655a  xor     ecx, ecx
0x14000655c  test    edi, edi
0x14000655e  setnz   cl
0x140006561  cmp     ecx, edx
0x140006563  jz      short loc_140006597
0x140006565  mov     rcx, [rbx+1A8h]
0x14000656c  test    rcx, rcx
0x14000656f  jz      short loc_140006597
0x140006571  test    r8b, 7
0x140006575  jnz     short loc_14000658B
0x140006577  test    r8b, 10h
0x14000657b  jnz     short loc_14000658B
0x14000657d  call    cs:__imp_SleepstudyHelper_ComponentActive
0x140006584  nop     dword ptr [rax+rax+00h]
0x140006589  jmp     short loc_140006597
0x14000658b  call    cs:__imp_SleepstudyHelper_ComponentInactive
0x140006592  nop     dword ptr [rax+rax+00h]
0x140006597  mov     dl, r14b; NewIrql
0x14000659a  mov     rcx, rsi; SpinLock
0x14000659d  call    cs:__imp_KeReleaseSpinLock
0x1400065a4  nop     dword ptr [rax+rax+00h]
0x1400065a9  jmp     short loc_1400065F7
0x1400065ab  mov     edx, [rbx+128h]
0x1400065b1  mov     ecx, 0
0x1400065b6  test    dl, 17h
0x1400065b9  setnz   cl
0x1400065bc  xor     eax, eax
0x1400065be  test    edi, edi
0x1400065c0  setnz   al
0x1400065c3  cmp     eax, ecx
0x1400065c5  jz      short loc_1400065F7
0x1400065c7  mov     rcx, [rbx+1A8h]
0x1400065ce  test    rcx, rcx
0x1400065d1  jz      short loc_1400065F7
0x1400065d3  test    dl, 7
0x1400065d6  jnz     short loc_1400065EB
0x1400065d8  test    dl, 10h
0x1400065db  jnz     short loc_1400065EB
0x1400065dd  call    cs:__imp_SleepstudyHelper_ComponentActive
0x1400065e4  nop     dword ptr [rax+rax+00h]
0x1400065e9  jmp     short loc_1400065F7
0x1400065eb  call    cs:__imp_SleepstudyHelper_ComponentInactive
0x1400065f2  nop     dword ptr [rax+rax+00h]
0x1400065f7  cmp     [rsp+78h+arg_20], 0
0x1400065ff  jz      short loc_140006617
0x140006601  lea     rcx, [rbp+2B8h]; SpinLock
0x140006608  mov     dl, r12b; NewIrql
0x14000660b  call    cs:__imp_KeReleaseSpinLock
0x140006612  nop     dword ptr [rax+rax+00h]
0x140006617  mov     al, r15b
0x14000661a  add     rsp, 40h
0x14000661e  pop     r15
0x140006620  pop     r14
0x140006622  pop     r12
0x140006624  pop     rdi
0x140006625  pop     rsi
0x140006626  pop     rbp
0x140006627  pop     rbx
0x140006628  retn
```
