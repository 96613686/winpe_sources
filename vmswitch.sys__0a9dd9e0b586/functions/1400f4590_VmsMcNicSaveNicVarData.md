# VmsMcNicSaveNicVarData

- ea: `0x1400f4590`
- end: `0x1400f4813`
- name: `VmsMcNicSaveNicVarData`
- size: `643`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400f9868`
- `0x14019ff68`

## callees

- `0x140027a64`
- `0x14008497c`
- `0x1400f4590`
- `0x1401bc040`

## import_xrefs

- `ntoskrnl!RtlEndEnumerationHashTable` at `0x1400f47d7`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x1400f47d7`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x1400f47bb`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x1400f47bb`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x1400f4758`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x1400f4758`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400f471c`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400f471c`
- `NDIS!NdisAcquireRWLockRead` at `0x1400f4744`
- `NDIS!NdisAcquireRWLockRead` at `0x1400f4744`
- `NDIS!NdisReleaseRWLock` at `0x1400f47f2`
- `NDIS!NdisReleaseRWLock` at `0x1400f47f2`

## string_xrefs

- `0x1400f45f8`: `Nic->HostRssConfig.IsHashContextInitialized == TRUE`
- `0x1400f4648`: `Nic->HostRssConfig.IsHashReady`

## pseudocode

```c
void __fastcall VmsMcNicSaveNicVarData(__int64 a1, __int64 a2)
{
  unsigned __int64 v4; // rbp
  char v5; // al
  __int64 v6; // rsi
  __int64 v7; // rbx
  int v8; // r14d
  unsigned __int64 v9; // r15
  KIRQL CurrentIrql; // al
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v11; // rax
  struct _RTL_DYNAMIC_HASH_TABLE_ENUMERATOR Enumerator; // [rsp+30h] [rbp-68h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+A0h] [rbp+8h] BYREF

  memset(&Enumerator, 0, sizeof(Enumerator));
  v4 = MEMORY[0xFFFFF78000000008];
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v5 = *(_BYTE *)(a1 + 4930);
  *(_BYTE *)(a2 + 4) = v5;
  if ( v5 )
  {
    if ( *(_BYTE *)(a1 + 5497) != 1 )
    {
      WPP_RECORDER_SF_s(
        VmsIfrNicLog,
        a2,
        19,
        98,
        (__int64)WPP_55628c5dac9b3e0169dfa5ae2dfc50df_Traceguids,
        "Nic->HostRssConfig.IsHashContextInitialized == TRUE",
        *(_OWORD *)&Enumerator.HashEntry.Linkage,
        Enumerator.HashEntry.Signature,
        Enumerator.ChainHead,
        *(_QWORD *)&Enumerator.BucketIndex);
      if ( *(_BYTE *)(a1 + 5497) != 1 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
  }
  if ( *(_BYTE *)(a2 + 4) && *(_BYTE *)(a1 + 5497) )
  {
    if ( !*(_BYTE *)(a1 + 5496) )
    {
      WPP_RECORDER_SF_s(
        VmsIfrNicLog,
        a2,
        19,
        99,
        (__int64)WPP_55628c5dac9b3e0169dfa5ae2dfc50df_Traceguids,
        "Nic->HostRssConfig.IsHashReady");
      if ( !*(_BYTE *)(a1 + 5496) )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
    }
    *(_DWORD *)(a2 + 8) = *(_DWORD *)(a1 + 4924) & 0xFFFF00;
    *(_DWORD *)(a2 + 12) = (unsigned __int8)*(_DWORD *)(a1 + 4924);
    *(_WORD *)(a2 + 528) = *(_WORD *)(a1 + 4976);
    memmove((void *)(a2 + 16), (const void *)(a1 + 4980), 4LL * *(unsigned __int16 *)(a1 + 4976));
    *(_WORD *)(a2 + 570) = *(_WORD *)(a1 + 4928);
    memmove((void *)(a2 + 530), (const void *)(a1 + 4932), *(unsigned __int16 *)(a1 + 4928));
    *(_BYTE *)(a2 + 572) = *(_BYTE *)(a1 + 5497);
  }
  v6 = *(_QWORD *)(a1 + 1984);
  if ( v6 )
  {
    v7 = a2 + 584;
    v8 = 0;
    v9 = v4 / 0x989680;
    CurrentIrql = KeGetCurrentIrql();
    NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(v6 + 10792), &LockState, CurrentIrql == 2);
    RtlInitEnumerationHashTable((PRTL_DYNAMIC_HASH_TABLE)(v6 + 10616), &Enumerator);
    while ( 1 )
    {
      v11 = RtlEnumerateEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)(v6 + 10616), &Enumerator);
      if ( !v11 )
        break;
      if ( (unsigned int)(LODWORD(v11[3].Linkage.Blink) - 2) <= 1 && v11[4].Linkage.Blink > (_LIST_ENTRY *)v9 )
      {
        *(_LIST_ENTRY *)v7 = v11[1].Linkage;
        *(_OWORD *)(v7 + 16) = *(_OWORD *)&v11[1].Signature;
        *(_LIST_ENTRY *)(v7 + 28) = *(_LIST_ENTRY *)((char *)&v11[2].Linkage + 4);
        *(_DWORD *)(v7 + 56) = v11[4].Signature;
        *(_QWORD *)(v7 + 48) = (char *)v11[4].Linkage.Blink - v9;
        *(_OWORD *)(v7 + 60) = *(_OWORD *)(v11[3].Signature + 16);
        v7 += 80;
        ++v8;
      }
    }
    RtlEndEnumerationHashTable((PRTL_DYNAMIC_HASH_TABLE)(v6 + 10616), &Enumerator);
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v6 + 10792), &LockState);
    *(_DWORD *)(a2 + 576) = v8;
  }
}

```

## disassembly

```asm
0x1400f4590  mov     r11, rsp
0x1400f4593  push    rbx
0x1400f4594  push    rbp
0x1400f4595  push    rsi
0x1400f4596  push    rdi
0x1400f4597  push    r14
0x1400f4599  push    r15
0x1400f459b  sub     rsp, 68h
0x1400f459f  xor     eax, eax
0x1400f45a1  lea     r14, WPP_55628c5dac9b3e0169dfa5ae2dfc50df_Traceguids
0x1400f45a8  xorps   xmm0, xmm0
0x1400f45ab  mov     rbp, 0FFFFF78000000008h
0x1400f45b5  movups  xmmword ptr [rsp+98h+Enumerator.___u0], xmm0
0x1400f45ba  mov     rdi, rdx
0x1400f45bd  mov     rbx, rcx
0x1400f45c0  movups  xmmword ptr [rsp+98h+Enumerator.___u0+10h], xmm0
0x1400f45c5  mov     [r11-48h], rax
0x1400f45c9  mov     esi, 13h
0x1400f45ce  mov     rbp, [rbp+0]
0x1400f45d2  mov     [r11+8], ax
0x1400f45d7  mov     [r11+0Ah], al
0x1400f45db  mov     al, [rcx+1342h]
0x1400f45e1  mov     [rdx+4], al
0x1400f45e4  test    al, al
0x1400f45e6  jz      short loc_1400F4621
0x1400f45e8  cmp     byte ptr [rcx+1579h], 1
0x1400f45ef  jz      short loc_1400F4621
0x1400f45f1  mov     rcx, cs:VmsIfrNicLog
0x1400f45f8  lea     rax, aNicHostrssconf_1; "Nic->HostRssConfig.IsHashContextInitial"...
0x1400f45ff  mov     [r11-70h], rax
0x1400f4603  lea     r9d, [rsi+4Fh]
0x1400f4607  mov     r8d, esi
0x1400f460a  mov     [r11-78h], r14
0x1400f460e  call    WPP_RECORDER_SF_s
0x1400f4613  cmp     byte ptr [rbx+1579h], 1
0x1400f461a  jz      short loc_1400F4621
0x1400f461c  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "Nic->HostRssConfig.IsHashContextInitialized == 1")
0x1400f4621  cmp     byte ptr [rdi+4], 0
0x1400f4625  jz      loc_1400F46EE
0x1400f462b  cmp     byte ptr [rbx+1579h], 0
0x1400f4632  jz      loc_1400F46EE
0x1400f4638  cmp     byte ptr [rbx+1578h], 0
0x1400f463f  jnz     short loc_1400F4675
0x1400f4641  mov     rcx, cs:VmsIfrNicLog
0x1400f4648  lea     rax, aNicHostrssconf; "Nic->HostRssConfig.IsHashReady"
0x1400f464f  mov     [rsp+98h+var_70], rax
0x1400f4654  mov     r9d, 63h ; 'c'
0x1400f465a  mov     r8d, esi
0x1400f465d  mov     [rsp+98h+var_78], r14
0x1400f4662  call    WPP_RECORDER_SF_s
0x1400f4667  cmp     byte ptr [rbx+1578h], 0
0x1400f466e  jnz     short loc_1400F4675
0x1400f4670  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "Nic->HostRssConfig.IsHashReady")
0x1400f4675  mov     eax, [rbx+133Ch]
0x1400f467b  lea     rdx, [rbx+1374h]; Src
0x1400f4682  and     eax, 0FFFF00h
0x1400f4687  mov     [rdi+8], eax
0x1400f468a  mov     eax, [rbx+133Ch]
0x1400f4690  movzx   ecx, al
0x1400f4693  mov     [rdi+0Ch], ecx
0x1400f4696  lea     rcx, [rdi+10h]; void *
0x1400f469a  movzx   eax, word ptr [rbx+1370h]
0x1400f46a1  mov     [rdi+210h], ax
0x1400f46a8  movzx   r8d, word ptr [rbx+1370h]
0x1400f46b0  shl     r8, 2; Size
0x1400f46b4  call    memmove
0x1400f46b9  movzx   eax, word ptr [rbx+1340h]
0x1400f46c0  lea     rdx, [rbx+1344h]; Src
0x1400f46c7  mov     [rdi+23Ah], ax
0x1400f46ce  lea     rcx, [rdi+212h]; void *
0x1400f46d5  movzx   r8d, word ptr [rbx+1340h]; Size
0x1400f46dd  call    memmove
0x1400f46e2  mov     al, [rbx+1579h]
0x1400f46e8  mov     [rdi+23Ch], al
0x1400f46ee  mov     rsi, [rbx+7C0h]
0x1400f46f5  test    rsi, rsi
0x1400f46f8  jz      loc_1400F4805
0x1400f46fe  mov     rax, 0D6BF94D5E57A42BDh
0x1400f4708  lea     rbx, [rdi+248h]
0x1400f470f  mul     rbp
0x1400f4712  xor     r14d, r14d
0x1400f4715  mov     r15, rdx
0x1400f4718  shr     r15, 17h
0x1400f471c  call    cs:__imp_KeGetCurrentIrql
0x1400f4723  nop     dword ptr [rax+rax+00h]
0x1400f4728  cmp     al, 2
0x1400f472a  lea     rbp, [rsi+2978h]
0x1400f4731  mov     rcx, [rbp+0B0h]; Lock
0x1400f4738  lea     rdx, [rsp+98h+LockState]; LockState
0x1400f4740  setz    r8b; Flags
0x1400f4744  call    cs:__imp_NdisAcquireRWLockRead
0x1400f474b  nop     dword ptr [rax+rax+00h]
0x1400f4750  lea     rdx, [rsp+98h+Enumerator]; Enumerator
0x1400f4755  mov     rcx, rbp; HashTable
0x1400f4758  call    cs:__imp_RtlInitEnumerationHashTable
0x1400f475f  nop     dword ptr [rax+rax+00h]
0x1400f4764  jmp     short loc_1400F47B3
0x1400f4766  mov     ecx, [rdx+50h]
0x1400f4769  sub     ecx, 2
0x1400f476c  cmp     ecx, 1
0x1400f476f  ja      short loc_1400F47B3
0x1400f4771  cmp     [rdx+68h], r15
0x1400f4775  jbe     short loc_1400F47B3
0x1400f4777  movups  xmm0, xmmword ptr [rdx+18h]
0x1400f477b  movups  xmmword ptr [rbx], xmm0
0x1400f477e  movups  xmm1, xmmword ptr [rdx+28h]
0x1400f4782  movups  xmmword ptr [rbx+10h], xmm1
0x1400f4786  movups  xmm0, xmmword ptr [rdx+34h]
0x1400f478a  movups  xmmword ptr [rbx+1Ch], xmm0
0x1400f478e  mov     eax, [rdx+70h]
0x1400f4791  mov     [rbx+38h], eax
0x1400f4794  mov     rax, [rdx+68h]
0x1400f4798  sub     rax, r15
0x1400f479b  mov     [rbx+30h], rax
0x1400f479f  mov     rax, [rdx+58h]
0x1400f47a3  movups  xmm0, xmmword ptr [rax+10h]
0x1400f47a7  movdqu  xmmword ptr [rbx+3Ch], xmm0
0x1400f47ac  add     rbx, 50h ; 'P'
0x1400f47b0  inc     r14d
0x1400f47b3  lea     rdx, [rsp+98h+Enumerator]; Enumerator
0x1400f47b8  mov     rcx, rbp; HashTable
0x1400f47bb  call    cs:__imp_RtlEnumerateEntryHashTable
0x1400f47c2  nop     dword ptr [rax+rax+00h]
0x1400f47c7  mov     rdx, rax
0x1400f47ca  test    rax, rax
0x1400f47cd  jnz     short loc_1400F4766
0x1400f47cf  lea     rdx, [rsp+98h+Enumerator]; Enumerator
0x1400f47d4  mov     rcx, rbp; HashTable
0x1400f47d7  call    cs:__imp_RtlEndEnumerationHashTable
0x1400f47de  nop     dword ptr [rax+rax+00h]
0x1400f47e3  mov     rcx, [rsi+2A28h]; Lock
0x1400f47ea  lea     rdx, [rsp+98h+LockState]; LockState
0x1400f47f2  call    cs:__imp_NdisReleaseRWLock
0x1400f47f9  nop     dword ptr [rax+rax+00h]
0x1400f47fe  mov     [rdi+240h], r14d
0x1400f4805  add     rsp, 68h
0x1400f4809  pop     r15
0x1400f480b  pop     r14
0x1400f480d  pop     rdi
0x1400f480e  pop     rsi
0x1400f480f  pop     rbp
0x1400f4810  pop     rbx
0x1400f4811  retn
```
