# VmsMcNicSaveNicVarData

- ea: `0x1400f4520`
- end: `0x1400f47a3`
- name: `VmsMcNicSaveNicVarData`
- size: `643`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400f97f8`
- `0x14019fef8`

## callees

- `0x140027a64`
- `0x14008497c`
- `0x1400f4520`
- `0x1401bbfc0`

## import_xrefs

- `ntoskrnl!RtlEndEnumerationHashTable` at `0x1400f4767`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x1400f4767`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x1400f474b`
- `ntoskrnl!RtlEnumerateEntryHashTable` at `0x1400f474b`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x1400f46e8`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x1400f46e8`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400f46ac`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400f46ac`
- `NDIS!NdisAcquireRWLockRead` at `0x1400f46d4`
- `NDIS!NdisAcquireRWLockRead` at `0x1400f46d4`
- `NDIS!NdisReleaseRWLock` at `0x1400f4782`
- `NDIS!NdisReleaseRWLock` at `0x1400f4782`

## string_xrefs

- `0x1400f4588`: `Nic->HostRssConfig.IsHashContextInitialized == TRUE`
- `0x1400f45d8`: `Nic->HostRssConfig.IsHashReady`

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
0x1400f4520  mov     r11, rsp
0x1400f4523  push    rbx
0x1400f4524  push    rbp
0x1400f4525  push    rsi
0x1400f4526  push    rdi
0x1400f4527  push    r14
0x1400f4529  push    r15
0x1400f452b  sub     rsp, 68h
0x1400f452f  xor     eax, eax
0x1400f4531  lea     r14, WPP_55628c5dac9b3e0169dfa5ae2dfc50df_Traceguids
0x1400f4538  xorps   xmm0, xmm0
0x1400f453b  mov     rbp, 0FFFFF78000000008h
0x1400f4545  movups  xmmword ptr [rsp+98h+Enumerator.___u0], xmm0
0x1400f454a  mov     rdi, rdx
0x1400f454d  mov     rbx, rcx
0x1400f4550  movups  xmmword ptr [rsp+98h+Enumerator.___u0+10h], xmm0
0x1400f4555  mov     [r11-48h], rax
0x1400f4559  mov     esi, 13h
0x1400f455e  mov     rbp, [rbp+0]
0x1400f4562  mov     [r11+8], ax
0x1400f4567  mov     [r11+0Ah], al
0x1400f456b  mov     al, [rcx+1342h]
0x1400f4571  mov     [rdx+4], al
0x1400f4574  test    al, al
0x1400f4576  jz      short loc_1400F45B1
0x1400f4578  cmp     byte ptr [rcx+1579h], 1
0x1400f457f  jz      short loc_1400F45B1
0x1400f4581  mov     rcx, cs:VmsIfrNicLog
0x1400f4588  lea     rax, aNicHostrssconf_1; "Nic->HostRssConfig.IsHashContextInitial"...
0x1400f458f  mov     [r11-70h], rax
0x1400f4593  lea     r9d, [rsi+4Fh]
0x1400f4597  mov     r8d, esi
0x1400f459a  mov     [r11-78h], r14
0x1400f459e  call    WPP_RECORDER_SF_s
0x1400f45a3  cmp     byte ptr [rbx+1579h], 1
0x1400f45aa  jz      short loc_1400F45B1
0x1400f45ac  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "Nic->HostRssConfig.IsHashContextInitialized == 1")
0x1400f45b1  cmp     byte ptr [rdi+4], 0
0x1400f45b5  jz      loc_1400F467E
0x1400f45bb  cmp     byte ptr [rbx+1579h], 0
0x1400f45c2  jz      loc_1400F467E
0x1400f45c8  cmp     byte ptr [rbx+1578h], 0
0x1400f45cf  jnz     short loc_1400F4605
0x1400f45d1  mov     rcx, cs:VmsIfrNicLog
0x1400f45d8  lea     rax, aNicHostrssconf; "Nic->HostRssConfig.IsHashReady"
0x1400f45df  mov     [rsp+98h+var_70], rax
0x1400f45e4  mov     r9d, 63h ; 'c'
0x1400f45ea  mov     r8d, esi
0x1400f45ed  mov     [rsp+98h+var_78], r14
0x1400f45f2  call    WPP_RECORDER_SF_s
0x1400f45f7  cmp     byte ptr [rbx+1578h], 0
0x1400f45fe  jnz     short loc_1400F4605
0x1400f4600  call    MicrosoftTelemetryAssertTriggeredNoArgsKM; __annotation("Debug", "TelemetryAssert", "Nic->HostRssConfig.IsHashReady")
0x1400f4605  mov     eax, [rbx+133Ch]
0x1400f460b  lea     rdx, [rbx+1374h]; Src
0x1400f4612  and     eax, 0FFFF00h
0x1400f4617  mov     [rdi+8], eax
0x1400f461a  mov     eax, [rbx+133Ch]
0x1400f4620  movzx   ecx, al
0x1400f4623  mov     [rdi+0Ch], ecx
0x1400f4626  lea     rcx, [rdi+10h]; void *
0x1400f462a  movzx   eax, word ptr [rbx+1370h]
0x1400f4631  mov     [rdi+210h], ax
0x1400f4638  movzx   r8d, word ptr [rbx+1370h]
0x1400f4640  shl     r8, 2; Size
0x1400f4644  call    memmove
0x1400f4649  movzx   eax, word ptr [rbx+1340h]
0x1400f4650  lea     rdx, [rbx+1344h]; Src
0x1400f4657  mov     [rdi+23Ah], ax
0x1400f465e  lea     rcx, [rdi+212h]; void *
0x1400f4665  movzx   r8d, word ptr [rbx+1340h]; Size
0x1400f466d  call    memmove
0x1400f4672  mov     al, [rbx+1579h]
0x1400f4678  mov     [rdi+23Ch], al
0x1400f467e  mov     rsi, [rbx+7C0h]
0x1400f4685  test    rsi, rsi
0x1400f4688  jz      loc_1400F4795
0x1400f468e  mov     rax, 0D6BF94D5E57A42BDh
0x1400f4698  lea     rbx, [rdi+248h]
0x1400f469f  mul     rbp
0x1400f46a2  xor     r14d, r14d
0x1400f46a5  mov     r15, rdx
0x1400f46a8  shr     r15, 17h
0x1400f46ac  call    cs:__imp_KeGetCurrentIrql
0x1400f46b3  nop     dword ptr [rax+rax+00h]
0x1400f46b8  cmp     al, 2
0x1400f46ba  lea     rbp, [rsi+2978h]
0x1400f46c1  mov     rcx, [rbp+0B0h]; Lock
0x1400f46c8  lea     rdx, [rsp+98h+LockState]; LockState
0x1400f46d0  setz    r8b; Flags
0x1400f46d4  call    cs:__imp_NdisAcquireRWLockRead
0x1400f46db  nop     dword ptr [rax+rax+00h]
0x1400f46e0  lea     rdx, [rsp+98h+Enumerator]; Enumerator
0x1400f46e5  mov     rcx, rbp; HashTable
0x1400f46e8  call    cs:__imp_RtlInitEnumerationHashTable
0x1400f46ef  nop     dword ptr [rax+rax+00h]
0x1400f46f4  jmp     short loc_1400F4743
0x1400f46f6  mov     ecx, [rdx+50h]
0x1400f46f9  sub     ecx, 2
0x1400f46fc  cmp     ecx, 1
0x1400f46ff  ja      short loc_1400F4743
0x1400f4701  cmp     [rdx+68h], r15
0x1400f4705  jbe     short loc_1400F4743
0x1400f4707  movups  xmm0, xmmword ptr [rdx+18h]
0x1400f470b  movups  xmmword ptr [rbx], xmm0
0x1400f470e  movups  xmm1, xmmword ptr [rdx+28h]
0x1400f4712  movups  xmmword ptr [rbx+10h], xmm1
0x1400f4716  movups  xmm0, xmmword ptr [rdx+34h]
0x1400f471a  movups  xmmword ptr [rbx+1Ch], xmm0
0x1400f471e  mov     eax, [rdx+70h]
0x1400f4721  mov     [rbx+38h], eax
0x1400f4724  mov     rax, [rdx+68h]
0x1400f4728  sub     rax, r15
0x1400f472b  mov     [rbx+30h], rax
0x1400f472f  mov     rax, [rdx+58h]
0x1400f4733  movups  xmm0, xmmword ptr [rax+10h]
0x1400f4737  movdqu  xmmword ptr [rbx+3Ch], xmm0
0x1400f473c  add     rbx, 50h ; 'P'
0x1400f4740  inc     r14d
0x1400f4743  lea     rdx, [rsp+98h+Enumerator]; Enumerator
0x1400f4748  mov     rcx, rbp; HashTable
0x1400f474b  call    cs:__imp_RtlEnumerateEntryHashTable
0x1400f4752  nop     dword ptr [rax+rax+00h]
0x1400f4757  mov     rdx, rax
0x1400f475a  test    rax, rax
0x1400f475d  jnz     short loc_1400F46F6
0x1400f475f  lea     rdx, [rsp+98h+Enumerator]; Enumerator
0x1400f4764  mov     rcx, rbp; HashTable
0x1400f4767  call    cs:__imp_RtlEndEnumerationHashTable
0x1400f476e  nop     dword ptr [rax+rax+00h]
0x1400f4773  mov     rcx, [rsi+2A28h]; Lock
0x1400f477a  lea     rdx, [rsp+98h+LockState]; LockState
0x1400f4782  call    cs:__imp_NdisReleaseRWLock
0x1400f4789  nop     dword ptr [rax+rax+00h]
0x1400f478e  mov     [rdi+240h], r14d
0x1400f4795  add     rsp, 68h
0x1400f4799  pop     r15
0x1400f479b  pop     r14
0x1400f479d  pop     rdi
0x1400f479e  pop     rsi
0x1400f479f  pop     rbp
0x1400f47a0  pop     rbx
0x1400f47a1  retn
```
