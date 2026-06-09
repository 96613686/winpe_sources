# IppLbIndicatePackets

- ea: `0x14006cc70`
- end: `0x14006d167`
- name: `IppLbIndicatePackets`
- size: `1271`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x14006c9e0`
- `0x1401246c8`

## callees

- `0x14002f820`
- `0x14005a390`
- `0x14006bce0`
- `0x14006cc70`
- `0x14006d170`
- `0x14006d580`
- `0x14006dc40`
- `0x14006dd30`
- `0x1400955a8`
- `0x1401123d4`
- `0x1401bf700`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x14006cebb`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x14006d0d1`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x14006cebb`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x14006d0d1`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x14006cfb0`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x14006cfb0`
- `NETIO!NetioAllocateMdl` at `0x14006d069`
- `NETIO!NetioAllocateMdl` at `0x14006d081`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x14006ce39`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x14006ce39`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14006d073`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14006d08b`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14006d073`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14006d08b`

## pseudocode

```c
void __fastcall IppLbIndicatePackets(__int64 a1, __int64 a2)
{
  unsigned int v4; // esi
  _QWORD *v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rcx
  unsigned __int64 v8; // rax
  unsigned int i; // r15d
  __int64 *v10; // rdi
  __int64 v11; // rcx
  _QWORD *v12; // rcx
  __int64 *v13; // rdi
  __int64 *v14; // rax
  _QWORD *v15; // rbx
  __int64 v16; // rdx
  bool v17; // r12
  __int64 v18; // r13
  volatile signed __int64 *AnySubInterfaceOnInterface; // r15
  _QWORD *v20; // rsi
  _DWORD *v21; // rax
  __int64 v22; // rcx
  _QWORD *v23; // rdi
  int v24; // edx
  struct _NET_BUFFER *v25; // rcx
  ULONG v26; // edx
  ULONG CurrentMdlOffset; // eax
  __int64 v28; // rax
  ULONG v29; // edx
  struct _NET_BUFFER *v30; // rcx
  ULONG v31; // eax
  signed __int64 v32; // rax
  bool v33; // cc
  signed __int64 v34; // rax
  _QWORD *v35; // [rsp+30h] [rbp-19h] BYREF
  __int64 *v36; // [rsp+38h] [rbp-11h]
  __int64 v37; // [rsp+40h] [rbp-9h] BYREF
  __int64 *v38; // [rsp+48h] [rbp-1h]
  PVOID Entry; // [rsp+50h] [rbp+7h] BYREF
  PVOID *p_Entry; // [rsp+58h] [rbp+Fh]
  __int128 v41; // [rsp+60h] [rbp+17h] BYREF
  _QWORD *v42; // [rsp+70h] [rbp+27h]
  __int64 v43; // [rsp+B0h] [rbp+67h] BYREF

  p_Entry = &Entry;
  LOBYTE(v43) = 0;
  v36 = (__int64 *)&v35;
  Entry = 0;
  v38 = &v37;
  v35 = 0;
  v37 = 0;
  if ( (*((_BYTE *)&WPP_MAIN_CB.Reserved + 9) & 0x20) != 0 )
  {
    v23 = *(_QWORD **)a2;
    if ( *(_QWORD *)a2 )
    {
      do
      {
        NetioEtwTraceNblOobInfo(v23[1], 1);
        v23 = (_QWORD *)*v23;
      }
      while ( v23 );
    }
  }
  if ( !*(_DWORD *)(a1 + 19656) )
    goto LABEL_85;
  *((_QWORD *)&v41 + 1) = &v41;
  v17 = 0;
  v18 = 0;
  *(_QWORD *)&v41 = 0;
  AnySubInterfaceOnInterface = 0;
  while ( 1 )
  {
    v20 = *(_QWORD **)a2;
    if ( !*(_QWORD *)a2 )
      break;
    *(_QWORD *)a2 = *v20;
    *v20 = 0;
    if ( *(_QWORD **)(a2 + 8) == v20 )
      *(_QWORD *)(a2 + 8) = a2;
    v21 = (_DWORD *)v20[25];
    *v20 = 0;
    if ( *v21 != 1 )
      goto LABEL_41;
    if ( *(_QWORD *)(v20[27] + 8LL) != v18 )
    {
      if ( v17 )
      {
        ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(*(_QWORD *)(v18 + 96) + 16LL), 1u);
        v17 = 0;
      }
      if ( AnySubInterfaceOnInterface )
        IppDereferenceSubInterface((PVOID)AnySubInterfaceOnInterface);
      v18 = *(_QWORD *)(v20[27] + 8LL);
      AnySubInterfaceOnInterface = (volatile signed __int64 *)IppFindAnySubInterfaceOnInterface(v18);
      if ( AnySubInterfaceOnInterface )
      {
        v22 = *(_QWORD *)(v18 + 96);
        v17 = v22
           && !*(_BYTE *)(v22 + 40)
           && ExAcquireRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v22 + 16), 1u);
      }
    }
    if ( v17
      && (IppIndicatePacketsToIpsServiceChain((_DWORD)AnySubInterfaceOnInterface, (_DWORD)v20 + 8, v20[1], 0, 0, 1),
          !v20[1]) )
    {
      *p_Entry = v20;
      p_Entry = (PVOID *)v20;
    }
    else
    {
LABEL_41:
      **((_QWORD **)&v41 + 1) = v20;
      *((_QWORD *)&v41 + 1) = v20;
    }
  }
  if ( v17 )
    ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(*(_QWORD *)(v18 + 96) + 16LL), 1u);
  if ( AnySubInterfaceOnInterface )
  {
    v32 = _InterlockedExchangeAdd64(AnySubInterfaceOnInterface + 8, 0xFFFFFFFFFFFFFFFFuLL);
    v33 = v32 <= 1;
    v34 = v32 - 1;
    if ( v33 )
    {
      if ( v34 )
        __fastfail(0xEu);
      IppCleanupSubInterface((PVOID)AnySubInterfaceOnInterface);
    }
  }
  if ( (_QWORD)v41 )
  {
    **(_QWORD **)(a2 + 8) = v41;
    *(_QWORD *)(a2 + 8) = *((_QWORD *)&v41 + 1);
  }
  if ( *(_QWORD *)a2 )
  {
LABEL_85:
    v4 = IppLbPrevalidateReceive(a1, a2, &v35, &v43);
    if ( v4 )
    {
      v5 = v35;
      do
      {
        v6 = a1 + 72 * ((unsigned __int8)v43 + 7LL);
        if ( v6 )
        {
          v7 = *(_QWORD *)(v6 + 56);
          v42 = 0;
          v41 = 0;
          v8 = *(_QWORD *)(v7 + 32);
          v42 = v5;
          v41 = v8;
          (*(void (__fastcall **)(__int128 *, _QWORD))(*(_QWORD *)(v7 + 40) + 24LL))(&v41, v4);
          for ( i = 0; i < v4; ++i )
          {
            v10 = v35;
            if ( v35 )
            {
              v35 = (_QWORD *)*v35;
              *v10 = 0;
              if ( v36 == v10 )
                v36 = (__int64 *)&v35;
            }
            v11 = v10[1];
            *v10 = 0;
            if ( v11 )
            {
              v24 = *(_DWORD *)(v11 + 140);
              if ( (unsigned int)(v24 + 1073741250) <= 1
                || v24 == -1073700844
                || v24 == -1071513340
                || v24 == -1073741790
                || v24 == 1073741862 )
              {
                v25 = *(struct _NET_BUFFER **)(v11 + 8);
                v26 = *((_DWORD *)v10 + 49);
                CurrentMdlOffset = v25->CurrentMdlOffset;
                if ( CurrentMdlOffset < v26 )
                {
                  NdisRetreatNetBufferDataStart(v25, v26, 0, NetioAllocateMdl);
                }
                else
                {
                  v25->DataOffset -= v26;
                  v25->DataLength += v26;
                  v25->CurrentMdlOffset = CurrentMdlOffset - v26;
                }
                v28 = v10[1];
                if ( *(_DWORD *)(v28 + 140) == -1073700844 )
                {
                  *(_DWORD *)(v28 + 140) = 0;
                  *((_BYTE *)v10 + 16) &= ~8u;
                }
                else
                {
                  IppComputeChecksumForLoopbackPacket(a1, *((unsigned int *)v10 + 11), v10);
                  *(_QWORD *)(v10[1] + 112) = 255;
                }
                v29 = *((_DWORD *)v10 + 12) - *((_DWORD *)v10 + 49);
                v30 = *(struct _NET_BUFFER **)(v10[1] + 8);
                v31 = v30->CurrentMdlOffset;
                if ( v31 < v29 )
                {
                  NdisRetreatNetBufferDataStart(v30, v29, 0, NetioAllocateMdl);
                }
                else
                {
                  v30->DataOffset -= v29;
                  v30->DataLength += v29;
                  v30->CurrentMdlOffset = v31 - v29;
                }
                *v38 = (__int64)v10;
                v38 = v10;
              }
              else
              {
                *p_Entry = v10;
                p_Entry = (PVOID *)v10;
              }
            }
            else
            {
              *p_Entry = v10;
              p_Entry = (PVOID *)v10;
            }
          }
          if ( !*(_QWORD *)a2 )
            break;
          v4 = IppLbPrevalidateReceive(a1, a2, &v35, &v43);
        }
        else
        {
          if ( !v5 )
            continue;
          *v38 = (__int64)v5;
          v38 = v36;
        }
        v5 = v35;
      }
      while ( v4 );
    }
  }
  if ( *(_QWORD *)a2 )
  {
    *v38 = *(_QWORD *)a2;
    v38 = *(__int64 **)(a2 + 8);
  }
  if ( v37 )
    IppReceiveHeaderBatch(a1, &v37);
  v12 = Entry;
  if ( Entry )
  {
    v43 = 0;
    v13 = &v43;
    do
    {
      v14 = (__int64 *)v12[1];
      v15 = (_QWORD *)*v12;
      if ( v14 )
      {
        *v13 = (__int64)v14;
        v13 = v14;
      }
      IppFreePacket(v12);
      v12 = v15;
    }
    while ( v15 );
    if ( v43 )
    {
      LOBYTE(v16) = 1;
      NetioDereferenceNetBufferListChain(v43, v16);
    }
  }
}

```

## disassembly

```asm
0x14006cc70  push    rbp
0x14006cc72  push    rbx
0x14006cc73  push    rdi
0x14006cc74  lea     rbp, [rsp-47h]
0x14006cc79  sub     rsp, 90h
0x14006cc80  xor     edi, edi
0x14006cc82  mov     [rsp+0A0h+var_18], r14
0x14006cc8a  test    byte ptr cs:WPP_MAIN_CB+149h, 20h
0x14006cc91  lea     rax, [rbp+57h+Entry]
0x14006cc95  mov     [rbp+57h+var_48], rax
0x14006cc99  mov     rbx, rdx
0x14006cc9c  lea     rax, [rbp+57h+var_70]
0x14006cca0  mov     byte ptr [rbp+57h+arg_0], 0
0x14006cca4  mov     [rbp+57h+var_68], rax
0x14006cca8  mov     r14, rcx
0x14006ccab  lea     rax, [rbp+57h+var_60]
0x14006ccaf  mov     [rbp+57h+Entry], rdi
0x14006ccb3  mov     [rbp+57h+var_58], rax
0x14006ccb7  mov     [rbp+57h+var_70], rdi
0x14006ccbb  mov     [rbp+57h+var_60], rdi
0x14006ccbf  jnz     loc_14006CF57
0x14006ccc5  mov     eax, [r14+4CC8h]
0x14006cccc  mov     [rsp+0A0h+arg_8], rsi
0x14006ccd4  mov     [rsp+0A0h+arg_10], r12
0x14006ccdc  mov     [rsp+0A0h+var_20], r15
0x14006cce4  test    eax, eax
0x14006cce6  jnz     loc_14006CE51
0x14006ccec  lea     r9, [rbp+57h+arg_0]
0x14006ccf0  mov     rdx, rbx
0x14006ccf3  lea     r8, [rbp+57h+var_70]
0x14006ccf7  mov     rcx, r14
0x14006ccfa  call    IppLbPrevalidateReceive
0x14006ccff  mov     esi, eax
0x14006cd01  test    eax, eax
0x14006cd03  jz      loc_14006CDB4
0x14006cd09  mov     rdx, [rbp+57h+var_70]
0x14006cd0d  movzx   ecx, byte ptr [rbp+57h+arg_0]
0x14006cd11  add     rcx, 7
0x14006cd15  lea     rax, [rcx+rcx*8]
0x14006cd19  lea     rcx, [r14+rax*8]
0x14006cd1d  test    rcx, rcx
0x14006cd20  jz      loc_14006D14A
0x14006cd26  mov     rcx, [rcx+38h]
0x14006cd2a  xor     eax, eax
0x14006cd2c  mov     [rbp+57h+var_30], rax
0x14006cd30  xorps   xmm0, xmm0
0x14006cd33  movups  [rbp+57h+var_40], xmm0
0x14006cd37  mov     rax, [rcx+20h]
0x14006cd3b  mov     [rbp+57h+var_30], rdx
0x14006cd3f  mov     edx, esi
0x14006cd41  mov     qword ptr [rbp+57h+var_40], rax
0x14006cd45  mov     qword ptr [rbp+57h+var_40+8], rdi
0x14006cd49  mov     rax, [rcx+28h]
0x14006cd4d  lea     rcx, [rbp+57h+var_40]
0x14006cd51  mov     rax, [rax+18h]
0x14006cd55  call    _guard_dispatch_icall
0x14006cd5a  mov     r15d, edi
0x14006cd5d  test    esi, esi
0x14006cd5f  jz      short loc_14006CDAA
0x14006cd61  xor     r12d, r12d
0x14006cd64  mov     rdi, [rbp+57h+var_70]
0x14006cd68  test    rdi, rdi
0x14006cd6b  jz      short loc_14006CD85
0x14006cd6d  mov     rax, [rdi]
0x14006cd70  mov     [rbp+57h+var_70], rax
0x14006cd74  mov     [rdi], r12
0x14006cd77  cmp     [rbp+57h+var_68], rdi
0x14006cd7b  jnz     short loc_14006CD85
0x14006cd7d  lea     rax, [rbp+57h+var_70]
0x14006cd81  mov     [rbp+57h+var_68], rax
0x14006cd85  mov     rcx, [rdi+8]
0x14006cd89  mov     [rdi], r12
0x14006cd8c  test    rcx, rcx
0x14006cd8f  jnz     loc_14006CF66
0x14006cd95  mov     rax, [rbp+57h+var_48]
0x14006cd99  mov     [rax], rdi
0x14006cd9c  mov     [rbp+57h+var_48], rdi
0x14006cda0  inc     r15d
0x14006cda3  cmp     r15d, esi
0x14006cda6  jb      short loc_14006CD64
0x14006cda8  xor     edi, edi
0x14006cdaa  cmp     qword ptr [rbx], 0
0x14006cdae  jnz     loc_14006D099
0x14006cdb4  mov     rcx, [rbx]
0x14006cdb7  mov     r15, [rsp+0A0h+var_20]
0x14006cdbf  mov     r12, [rsp+0A0h+arg_10]
0x14006cdc7  mov     rsi, [rsp+0A0h+arg_8]
0x14006cdcf  test    rcx, rcx
0x14006cdd2  jz      short loc_14006CDE3
0x14006cdd4  mov     rax, [rbp+57h+var_58]
0x14006cdd8  mov     [rax], rcx
0x14006cddb  mov     rax, [rbx+8]
0x14006cddf  mov     [rbp+57h+var_58], rax
0x14006cde3  cmp     [rbp+57h+var_60], 0
0x14006cde8  jz      short loc_14006CDF6
0x14006cdea  lea     rdx, [rbp+57h+var_60]
0x14006cdee  mov     rcx, r14
0x14006cdf1  call    IppReceiveHeaderBatch
0x14006cdf6  mov     rcx, [rbp+57h+Entry]; Entry
0x14006cdfa  mov     r14, [rsp+0A0h+var_18]
0x14006ce02  test    rcx, rcx
0x14006ce05  jz      short loc_14006CE45
0x14006ce07  mov     [rbp+57h+arg_0], rdi
0x14006ce0b  lea     rdi, [rbp+57h+arg_0]
0x14006ce0f  mov     rax, [rcx+8]
0x14006ce13  mov     rbx, [rcx]
0x14006ce16  test    rax, rax
0x14006ce19  jz      short loc_14006CE21
0x14006ce1b  mov     [rdi], rax
0x14006ce1e  mov     rdi, rax
0x14006ce21  call    IppFreePacket
0x14006ce26  mov     rcx, rbx
0x14006ce29  test    rbx, rbx
0x14006ce2c  jnz     short loc_14006CE0F
0x14006ce2e  mov     rcx, [rbp+57h+arg_0]
0x14006ce32  test    rcx, rcx
0x14006ce35  jz      short loc_14006CE45
0x14006ce37  mov     dl, 1
0x14006ce39  call    cs:__imp_NetioDereferenceNetBufferListChain
0x14006ce40  nop     dword ptr [rax+rax+00h]
0x14006ce45  add     rsp, 90h
0x14006ce4c  pop     rdi
0x14006ce4d  pop     rbx
0x14006ce4e  pop     rbp
0x14006ce4f  retn
0x14006ce51  lea     rax, [rbp+57h+var_40]
0x14006ce55  mov     [rsp+0A0h+arg_18], r13
0x14006ce5d  mov     qword ptr [rbp+57h+var_40+8], rax
0x14006ce61  xor     r12b, r12b
0x14006ce64  mov     r13, rdi
0x14006ce67  mov     qword ptr [rbp+57h+var_40], rdi
0x14006ce6b  mov     r15, rdi
0x14006ce6e  mov     rsi, [rbx]
0x14006ce71  test    rsi, rsi
0x14006ce74  jz      loc_14006D0BF
0x14006ce7a  mov     rax, [rsi]
0x14006ce7d  mov     [rbx], rax
0x14006ce80  mov     [rsi], rdi
0x14006ce83  cmp     [rbx+8], rsi
0x14006ce87  jnz     short loc_14006CE8D
0x14006ce89  mov     [rbx+8], rbx
0x14006ce8d  mov     rax, [rsi+0C8h]
0x14006ce94  mov     [rsi], rdi
0x14006ce97  cmp     dword ptr [rax], 1
0x14006ce9a  jnz     short loc_14006CF0F
0x14006ce9c  mov     rax, [rsi+0D8h]
0x14006cea3  cmp     [rax+8], r13
0x14006cea7  jz      short loc_14006CF0A
0x14006cea9  test    r12b, r12b
0x14006ceac  jz      short loc_14006CECA
0x14006ceae  mov     rcx, [r13+60h]
0x14006ceb2  mov     edx, 1; Count
0x14006ceb7  mov     rcx, [rcx+10h]; RunRef
0x14006cebb  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x14006cec2  nop     dword ptr [rax+rax+00h]
0x14006cec7  xor     r12b, r12b
0x14006ceca  test    r15, r15
0x14006cecd  jz      short loc_14006CED7
0x14006cecf  mov     rcx, r15; Context
0x14006ced2  call    IppDereferenceSubInterface
0x14006ced7  mov     rax, [rsi+0D8h]
0x14006cede  mov     r13, [rax+8]
0x14006cee2  mov     rcx, r13
0x14006cee5  call    IppFindAnySubInterfaceOnInterface
0x14006ceea  mov     r15, rax
0x14006ceed  test    rax, rax
0x14006cef0  jz      short loc_14006CF0A
0x14006cef2  mov     rcx, [r13+60h]
0x14006cef6  test    rcx, rcx
0x14006cef9  jz      short loc_14006CF07
0x14006cefb  movzx   eax, byte ptr [rcx+28h]
0x14006ceff  test    al, al
0x14006cf01  jz      loc_14006CFA7
0x14006cf07  xor     r12b, r12b
0x14006cf0a  test    r12b, r12b
0x14006cf0d  jnz     short loc_14006CF1F
0x14006cf0f  mov     rax, qword ptr [rbp+57h+var_40+8]
0x14006cf13  mov     [rax], rsi
0x14006cf16  mov     qword ptr [rbp+57h+var_40+8], rsi
0x14006cf1a  jmp     loc_14006CE6E
0x14006cf1f  mov     r8, [rsi+8]
0x14006cf23  lea     rdx, [rsi+8]
0x14006cf27  mov     [rsp+0A0h+var_78], 1
0x14006cf2f  xor     r9d, r9d
0x14006cf32  mov     rcx, r15
0x14006cf35  mov     [rsp+0A0h+var_80], 0
0x14006cf3a  call    IppIndicatePacketsToIpsServiceChain
0x14006cf3f  xor     edi, edi
0x14006cf41  cmp     [rsi+8], rdi
0x14006cf45  jnz     short loc_14006CF0F
0x14006cf47  mov     rax, [rbp+57h+var_48]
0x14006cf4b  mov     [rax], rsi
0x14006cf4e  mov     [rbp+57h+var_48], rsi
0x14006cf52  jmp     loc_14006CE6E
0x14006cf57  mov     rdi, [rdx]
0x14006cf5a  test    rdi, rdi
0x14006cf5d  jnz     short loc_14006CFD0
0x14006cf5f  xor     edi, edi
0x14006cf61  jmp     loc_14006CCC5
0x14006cf66  mov     edx, [rcx+8Ch]
0x14006cf6c  lea     eax, [rdx+3FFFFDC2h]
0x14006cf72  cmp     eax, 1
0x14006cf75  jbe     short loc_14006CFEC
0x14006cf77  cmp     edx, 0C000A014h
0x14006cf7d  jz      short loc_14006CFEC
0x14006cf7f  cmp     edx, 0C0220104h
0x14006cf85  jz      short loc_14006CFEC
0x14006cf87  cmp     edx, 0C0000022h
0x14006cf8d  jz      short loc_14006CFEC
0x14006cf8f  cmp     edx, 40000026h
0x14006cf95  jz      short loc_14006CFEC
0x14006cf97  mov     rax, [rbp+57h+var_48]
0x14006cf9b  mov     [rax], rdi
0x14006cf9e  mov     [rbp+57h+var_48], rdi
0x14006cfa2  jmp     loc_14006CDA0
0x14006cfa7  mov     rcx, [rcx+10h]; RunRefCacheAware
0x14006cfab  mov     edx, 1; Count
0x14006cfb0  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x14006cfb7  nop     dword ptr [rax+rax+00h]
0x14006cfbc  test    al, al
0x14006cfbe  jz      loc_14006CF07
0x14006cfc4  mov     r12b, 1
0x14006cfc7  jmp     loc_14006CF0A
0x14006cfd0  mov     rcx, [rdi+8]
0x14006cfd4  mov     edx, 1
0x14006cfd9  call    NetioEtwTraceNblOobInfo
0x14006cfde  mov     rdi, [rdi]
0x14006cfe1  test    rdi, rdi
0x14006cfe4  jz      loc_14006CF5F
0x14006cfea  jmp     short loc_14006CFD0
0x14006cfec  mov     rcx, [rcx+8]; NetBuffer
0x14006cff0  mov     edx, [rdi+0C4h]; DataOffsetDelta
0x14006cff6  mov     eax, [rcx+10h]
0x14006cff9  cmp     eax, edx
0x14006cffb  jb      short loc_14006D069
0x14006cffd  sub     [rcx+28h], edx
0x14006d000  sub     eax, edx
0x14006d002  add     [rcx+18h], edx
0x14006d005  mov     [rcx+10h], eax
0x14006d008  mov     rax, [rdi+8]
0x14006d00c  cmp     dword ptr [rax+8Ch], 0C000A014h
0x14006d016  jz      loc_14006D13A
0x14006d01c  mov     edx, [rdi+2Ch]
0x14006d01f  mov     r8, rdi
0x14006d022  mov     rcx, r14
0x14006d025  call    IppComputeChecksumForLoopbackPacket
0x14006d02a  mov     rax, [rdi+8]
0x14006d02e  mov     qword ptr [rax+70h], 0FFh
0x14006d036  mov     rax, [rdi+8]
0x14006d03a  mov     edx, [rdi+30h]
0x14006d03d  sub     edx, [rdi+0C4h]; DataOffsetDelta
0x14006d043  mov     rcx, [rax+8]; NetBuffer
0x14006d047  mov     eax, [rcx+10h]
0x14006d04a  cmp     eax, edx
0x14006d04c  jb      short loc_14006D081
0x14006d04e  sub     [rcx+28h], edx
0x14006d051  sub     eax, edx
0x14006d053  add     [rcx+18h], edx
0x14006d056  mov     [rcx+10h], eax
0x14006d059  mov     rax, [rbp+57h+var_58]
0x14006d05d  mov     [rax], rdi
0x14006d060  mov     [rbp+57h+var_58], rdi
0x14006d064  jmp     loc_14006CDA0
0x14006d069  mov     r9, cs:__imp_NetioAllocateMdl; AllocateMdlHandler
0x14006d070  xor     r8d, r8d; DataBackFill
0x14006d073  call    cs:__imp_NdisRetreatNetBufferDataStart
0x14006d07a  nop     dword ptr [rax+rax+00h]
0x14006d07f  jmp     short loc_14006D008
0x14006d081  mov     r9, cs:__imp_NetioAllocateMdl; AllocateMdlHandler
0x14006d088  xor     r8d, r8d; DataBackFill
0x14006d08b  call    cs:__imp_NdisRetreatNetBufferDataStart
0x14006d092  nop     dword ptr [rax+rax+00h]
0x14006d097  jmp     short loc_14006D059
0x14006d099  lea     r9, [rbp+57h+arg_0]
0x14006d09d  mov     rdx, rbx
0x14006d0a0  lea     r8, [rbp+57h+var_70]
0x14006d0a4  mov     rcx, r14
0x14006d0a7  call    IppLbPrevalidateReceive
0x14006d0ac  mov     esi, eax
0x14006d0ae  mov     rdx, [rbp+57h+var_70]
0x14006d0b2  test    esi, esi
0x14006d0b4  jz      loc_14006CDB4
0x14006d0ba  jmp     loc_14006CD0D
0x14006d0bf  test    r12b, r12b
0x14006d0c2  jz      short loc_14006D0DD
0x14006d0c4  mov     rcx, [r13+60h]
0x14006d0c8  mov     edx, 1; Count
0x14006d0cd  mov     rcx, [rcx+10h]; RunRef
0x14006d0d1  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x14006d0d8  nop     dword ptr [rax+rax+00h]
0x14006d0dd  mov     r13, [rsp+0A0h+arg_18]
0x14006d0e5  test    r15, r15
0x14006d0e8  jz      short loc_14006D109
0x14006d0ea  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14006d0f1  lock xadd [r15+40h], rax
0x14006d0f7  sub     rax, 1
0x14006d0fb  jg      short loc_14006D109
0x14006d0fd  test    rax, rax
0x14006d100  jz      short loc_14006D130
0x14006d102  mov     ecx, 0Eh
  ... truncated ...
```
