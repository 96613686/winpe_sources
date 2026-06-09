# IppLbIndicatePackets

- ea: `0x14006c9d0`
- end: `0x14006cec7`
- name: `IppLbIndicatePackets`
- size: `1271`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x14006c740`
- `0x140124588`

## callees

- `0x14002f580`
- `0x14005a0f0`
- `0x14006ba40`
- `0x14006c9d0`
- `0x14006ced0`
- `0x14006d2e0`
- `0x14006d9a0`
- `0x14006da90`
- `0x1400946f8`
- `0x140112294`
- `0x1401bf5c0`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x14006cd10`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x14006cd10`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x14006cc1b`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x14006ce31`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x14006cc1b`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x14006ce31`
- `NETIO!NetioAllocateMdl` at `0x14006cdc9`
- `NETIO!NetioAllocateMdl` at `0x14006cde1`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x14006cb99`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x14006cb99`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14006cdd3`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14006cdeb`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14006cdd3`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14006cdeb`

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
0x14006c9d0  push    rbp
0x14006c9d2  push    rbx
0x14006c9d3  push    rdi
0x14006c9d4  lea     rbp, [rsp-47h]
0x14006c9d9  sub     rsp, 90h
0x14006c9e0  xor     edi, edi
0x14006c9e2  mov     [rsp+0A0h+var_18], r14
0x14006c9ea  test    byte ptr cs:WPP_MAIN_CB+149h, 20h
0x14006c9f1  lea     rax, [rbp+57h+Entry]
0x14006c9f5  mov     [rbp+57h+var_48], rax
0x14006c9f9  mov     rbx, rdx
0x14006c9fc  lea     rax, [rbp+57h+var_70]
0x14006ca00  mov     byte ptr [rbp+57h+arg_0], 0
0x14006ca04  mov     [rbp+57h+var_68], rax
0x14006ca08  mov     r14, rcx
0x14006ca0b  lea     rax, [rbp+57h+var_60]
0x14006ca0f  mov     [rbp+57h+Entry], rdi
0x14006ca13  mov     [rbp+57h+var_58], rax
0x14006ca17  mov     [rbp+57h+var_70], rdi
0x14006ca1b  mov     [rbp+57h+var_60], rdi
0x14006ca1f  jnz     loc_14006CCB7
0x14006ca25  mov     eax, [r14+4CC8h]
0x14006ca2c  mov     [rsp+0A0h+arg_8], rsi
0x14006ca34  mov     [rsp+0A0h+arg_10], r12
0x14006ca3c  mov     [rsp+0A0h+var_20], r15
0x14006ca44  test    eax, eax
0x14006ca46  jnz     loc_14006CBB1
0x14006ca4c  lea     r9, [rbp+57h+arg_0]
0x14006ca50  mov     rdx, rbx
0x14006ca53  lea     r8, [rbp+57h+var_70]
0x14006ca57  mov     rcx, r14
0x14006ca5a  call    IppLbPrevalidateReceive
0x14006ca5f  mov     esi, eax
0x14006ca61  test    eax, eax
0x14006ca63  jz      loc_14006CB14
0x14006ca69  mov     rdx, [rbp+57h+var_70]
0x14006ca6d  movzx   ecx, byte ptr [rbp+57h+arg_0]
0x14006ca71  add     rcx, 7
0x14006ca75  lea     rax, [rcx+rcx*8]
0x14006ca79  lea     rcx, [r14+rax*8]
0x14006ca7d  test    rcx, rcx
0x14006ca80  jz      loc_14006CEAA
0x14006ca86  mov     rcx, [rcx+38h]
0x14006ca8a  xor     eax, eax
0x14006ca8c  mov     [rbp+57h+var_30], rax
0x14006ca90  xorps   xmm0, xmm0
0x14006ca93  movups  [rbp+57h+var_40], xmm0
0x14006ca97  mov     rax, [rcx+20h]
0x14006ca9b  mov     [rbp+57h+var_30], rdx
0x14006ca9f  mov     edx, esi
0x14006caa1  mov     qword ptr [rbp+57h+var_40], rax
0x14006caa5  mov     qword ptr [rbp+57h+var_40+8], rdi
0x14006caa9  mov     rax, [rcx+28h]
0x14006caad  lea     rcx, [rbp+57h+var_40]
0x14006cab1  mov     rax, [rax+18h]
0x14006cab5  call    _guard_dispatch_icall
0x14006caba  mov     r15d, edi
0x14006cabd  test    esi, esi
0x14006cabf  jz      short loc_14006CB0A
0x14006cac1  xor     r12d, r12d
0x14006cac4  mov     rdi, [rbp+57h+var_70]
0x14006cac8  test    rdi, rdi
0x14006cacb  jz      short loc_14006CAE5
0x14006cacd  mov     rax, [rdi]
0x14006cad0  mov     [rbp+57h+var_70], rax
0x14006cad4  mov     [rdi], r12
0x14006cad7  cmp     [rbp+57h+var_68], rdi
0x14006cadb  jnz     short loc_14006CAE5
0x14006cadd  lea     rax, [rbp+57h+var_70]
0x14006cae1  mov     [rbp+57h+var_68], rax
0x14006cae5  mov     rcx, [rdi+8]
0x14006cae9  mov     [rdi], r12
0x14006caec  test    rcx, rcx
0x14006caef  jnz     loc_14006CCC6
0x14006caf5  mov     rax, [rbp+57h+var_48]
0x14006caf9  mov     [rax], rdi
0x14006cafc  mov     [rbp+57h+var_48], rdi
0x14006cb00  inc     r15d
0x14006cb03  cmp     r15d, esi
0x14006cb06  jb      short loc_14006CAC4
0x14006cb08  xor     edi, edi
0x14006cb0a  cmp     qword ptr [rbx], 0
0x14006cb0e  jnz     loc_14006CDF9
0x14006cb14  mov     rcx, [rbx]
0x14006cb17  mov     r15, [rsp+0A0h+var_20]
0x14006cb1f  mov     r12, [rsp+0A0h+arg_10]
0x14006cb27  mov     rsi, [rsp+0A0h+arg_8]
0x14006cb2f  test    rcx, rcx
0x14006cb32  jz      short loc_14006CB43
0x14006cb34  mov     rax, [rbp+57h+var_58]
0x14006cb38  mov     [rax], rcx
0x14006cb3b  mov     rax, [rbx+8]
0x14006cb3f  mov     [rbp+57h+var_58], rax
0x14006cb43  cmp     [rbp+57h+var_60], 0
0x14006cb48  jz      short loc_14006CB56
0x14006cb4a  lea     rdx, [rbp+57h+var_60]
0x14006cb4e  mov     rcx, r14
0x14006cb51  call    IppReceiveHeaderBatch
0x14006cb56  mov     rcx, [rbp+57h+Entry]; Entry
0x14006cb5a  mov     r14, [rsp+0A0h+var_18]
0x14006cb62  test    rcx, rcx
0x14006cb65  jz      short loc_14006CBA5
0x14006cb67  mov     [rbp+57h+arg_0], rdi
0x14006cb6b  lea     rdi, [rbp+57h+arg_0]
0x14006cb6f  mov     rax, [rcx+8]
0x14006cb73  mov     rbx, [rcx]
0x14006cb76  test    rax, rax
0x14006cb79  jz      short loc_14006CB81
0x14006cb7b  mov     [rdi], rax
0x14006cb7e  mov     rdi, rax
0x14006cb81  call    IppFreePacket
0x14006cb86  mov     rcx, rbx
0x14006cb89  test    rbx, rbx
0x14006cb8c  jnz     short loc_14006CB6F
0x14006cb8e  mov     rcx, [rbp+57h+arg_0]
0x14006cb92  test    rcx, rcx
0x14006cb95  jz      short loc_14006CBA5
0x14006cb97  mov     dl, 1
0x14006cb99  call    cs:__imp_NetioDereferenceNetBufferListChain
0x14006cba0  nop     dword ptr [rax+rax+00h]
0x14006cba5  add     rsp, 90h
0x14006cbac  pop     rdi
0x14006cbad  pop     rbx
0x14006cbae  pop     rbp
0x14006cbaf  retn
0x14006cbb1  lea     rax, [rbp+57h+var_40]
0x14006cbb5  mov     [rsp+0A0h+arg_18], r13
0x14006cbbd  mov     qword ptr [rbp+57h+var_40+8], rax
0x14006cbc1  xor     r12b, r12b
0x14006cbc4  mov     r13, rdi
0x14006cbc7  mov     qword ptr [rbp+57h+var_40], rdi
0x14006cbcb  mov     r15, rdi
0x14006cbce  mov     rsi, [rbx]
0x14006cbd1  test    rsi, rsi
0x14006cbd4  jz      loc_14006CE1F
0x14006cbda  mov     rax, [rsi]
0x14006cbdd  mov     [rbx], rax
0x14006cbe0  mov     [rsi], rdi
0x14006cbe3  cmp     [rbx+8], rsi
0x14006cbe7  jnz     short loc_14006CBED
0x14006cbe9  mov     [rbx+8], rbx
0x14006cbed  mov     rax, [rsi+0C8h]
0x14006cbf4  mov     [rsi], rdi
0x14006cbf7  cmp     dword ptr [rax], 1
0x14006cbfa  jnz     short loc_14006CC6F
0x14006cbfc  mov     rax, [rsi+0D8h]
0x14006cc03  cmp     [rax+8], r13
0x14006cc07  jz      short loc_14006CC6A
0x14006cc09  test    r12b, r12b
0x14006cc0c  jz      short loc_14006CC2A
0x14006cc0e  mov     rcx, [r13+60h]
0x14006cc12  mov     edx, 1; Count
0x14006cc17  mov     rcx, [rcx+10h]; RunRef
0x14006cc1b  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x14006cc22  nop     dword ptr [rax+rax+00h]
0x14006cc27  xor     r12b, r12b
0x14006cc2a  test    r15, r15
0x14006cc2d  jz      short loc_14006CC37
0x14006cc2f  mov     rcx, r15; Context
0x14006cc32  call    IppDereferenceSubInterface
0x14006cc37  mov     rax, [rsi+0D8h]
0x14006cc3e  mov     r13, [rax+8]
0x14006cc42  mov     rcx, r13
0x14006cc45  call    IppFindAnySubInterfaceOnInterface
0x14006cc4a  mov     r15, rax
0x14006cc4d  test    rax, rax
0x14006cc50  jz      short loc_14006CC6A
0x14006cc52  mov     rcx, [r13+60h]
0x14006cc56  test    rcx, rcx
0x14006cc59  jz      short loc_14006CC67
0x14006cc5b  movzx   eax, byte ptr [rcx+28h]
0x14006cc5f  test    al, al
0x14006cc61  jz      loc_14006CD07
0x14006cc67  xor     r12b, r12b
0x14006cc6a  test    r12b, r12b
0x14006cc6d  jnz     short loc_14006CC7F
0x14006cc6f  mov     rax, qword ptr [rbp+57h+var_40+8]
0x14006cc73  mov     [rax], rsi
0x14006cc76  mov     qword ptr [rbp+57h+var_40+8], rsi
0x14006cc7a  jmp     loc_14006CBCE
0x14006cc7f  mov     r8, [rsi+8]
0x14006cc83  lea     rdx, [rsi+8]
0x14006cc87  mov     [rsp+0A0h+var_78], 1
0x14006cc8f  xor     r9d, r9d
0x14006cc92  mov     rcx, r15
0x14006cc95  mov     [rsp+0A0h+var_80], 0
0x14006cc9a  call    IppIndicatePacketsToIpsServiceChain
0x14006cc9f  xor     edi, edi
0x14006cca1  cmp     [rsi+8], rdi
0x14006cca5  jnz     short loc_14006CC6F
0x14006cca7  mov     rax, [rbp+57h+var_48]
0x14006ccab  mov     [rax], rsi
0x14006ccae  mov     [rbp+57h+var_48], rsi
0x14006ccb2  jmp     loc_14006CBCE
0x14006ccb7  mov     rdi, [rdx]
0x14006ccba  test    rdi, rdi
0x14006ccbd  jnz     short loc_14006CD30
0x14006ccbf  xor     edi, edi
0x14006ccc1  jmp     loc_14006CA25
0x14006ccc6  mov     edx, [rcx+8Ch]
0x14006cccc  lea     eax, [rdx+3FFFFDC2h]
0x14006ccd2  cmp     eax, 1
0x14006ccd5  jbe     short loc_14006CD4C
0x14006ccd7  cmp     edx, 0C000A014h
0x14006ccdd  jz      short loc_14006CD4C
0x14006ccdf  cmp     edx, 0C0220104h
0x14006cce5  jz      short loc_14006CD4C
0x14006cce7  cmp     edx, 0C0000022h
0x14006cced  jz      short loc_14006CD4C
0x14006ccef  cmp     edx, 40000026h
0x14006ccf5  jz      short loc_14006CD4C
0x14006ccf7  mov     rax, [rbp+57h+var_48]
0x14006ccfb  mov     [rax], rdi
0x14006ccfe  mov     [rbp+57h+var_48], rdi
0x14006cd02  jmp     loc_14006CB00
0x14006cd07  mov     rcx, [rcx+10h]; RunRefCacheAware
0x14006cd0b  mov     edx, 1; Count
0x14006cd10  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x14006cd17  nop     dword ptr [rax+rax+00h]
0x14006cd1c  test    al, al
0x14006cd1e  jz      loc_14006CC67
0x14006cd24  mov     r12b, 1
0x14006cd27  jmp     loc_14006CC6A
0x14006cd30  mov     rcx, [rdi+8]
0x14006cd34  mov     edx, 1
0x14006cd39  call    NetioEtwTraceNblOobInfo
0x14006cd3e  mov     rdi, [rdi]
0x14006cd41  test    rdi, rdi
0x14006cd44  jz      loc_14006CCBF
0x14006cd4a  jmp     short loc_14006CD30
0x14006cd4c  mov     rcx, [rcx+8]; NetBuffer
0x14006cd50  mov     edx, [rdi+0C4h]; DataOffsetDelta
0x14006cd56  mov     eax, [rcx+10h]
0x14006cd59  cmp     eax, edx
0x14006cd5b  jb      short loc_14006CDC9
0x14006cd5d  sub     [rcx+28h], edx
0x14006cd60  sub     eax, edx
0x14006cd62  add     [rcx+18h], edx
0x14006cd65  mov     [rcx+10h], eax
0x14006cd68  mov     rax, [rdi+8]
0x14006cd6c  cmp     dword ptr [rax+8Ch], 0C000A014h
0x14006cd76  jz      loc_14006CE9A
0x14006cd7c  mov     edx, [rdi+2Ch]
0x14006cd7f  mov     r8, rdi
0x14006cd82  mov     rcx, r14
0x14006cd85  call    IppComputeChecksumForLoopbackPacket
0x14006cd8a  mov     rax, [rdi+8]
0x14006cd8e  mov     qword ptr [rax+70h], 0FFh
0x14006cd96  mov     rax, [rdi+8]
0x14006cd9a  mov     edx, [rdi+30h]
0x14006cd9d  sub     edx, [rdi+0C4h]; DataOffsetDelta
0x14006cda3  mov     rcx, [rax+8]; NetBuffer
0x14006cda7  mov     eax, [rcx+10h]
0x14006cdaa  cmp     eax, edx
0x14006cdac  jb      short loc_14006CDE1
0x14006cdae  sub     [rcx+28h], edx
0x14006cdb1  sub     eax, edx
0x14006cdb3  add     [rcx+18h], edx
0x14006cdb6  mov     [rcx+10h], eax
0x14006cdb9  mov     rax, [rbp+57h+var_58]
0x14006cdbd  mov     [rax], rdi
0x14006cdc0  mov     [rbp+57h+var_58], rdi
0x14006cdc4  jmp     loc_14006CB00
0x14006cdc9  mov     r9, cs:__imp_NetioAllocateMdl; AllocateMdlHandler
0x14006cdd0  xor     r8d, r8d; DataBackFill
0x14006cdd3  call    cs:__imp_NdisRetreatNetBufferDataStart
0x14006cdda  nop     dword ptr [rax+rax+00h]
0x14006cddf  jmp     short loc_14006CD68
0x14006cde1  mov     r9, cs:__imp_NetioAllocateMdl; AllocateMdlHandler
0x14006cde8  xor     r8d, r8d; DataBackFill
0x14006cdeb  call    cs:__imp_NdisRetreatNetBufferDataStart
0x14006cdf2  nop     dword ptr [rax+rax+00h]
0x14006cdf7  jmp     short loc_14006CDB9
0x14006cdf9  lea     r9, [rbp+57h+arg_0]
0x14006cdfd  mov     rdx, rbx
0x14006ce00  lea     r8, [rbp+57h+var_70]
0x14006ce04  mov     rcx, r14
0x14006ce07  call    IppLbPrevalidateReceive
0x14006ce0c  mov     esi, eax
0x14006ce0e  mov     rdx, [rbp+57h+var_70]
0x14006ce12  test    esi, esi
0x14006ce14  jz      loc_14006CB14
0x14006ce1a  jmp     loc_14006CA6D
0x14006ce1f  test    r12b, r12b
0x14006ce22  jz      short loc_14006CE3D
0x14006ce24  mov     rcx, [r13+60h]
0x14006ce28  mov     edx, 1; Count
0x14006ce2d  mov     rcx, [rcx+10h]; RunRef
0x14006ce31  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x14006ce38  nop     dword ptr [rax+rax+00h]
0x14006ce3d  mov     r13, [rsp+0A0h+arg_18]
0x14006ce45  test    r15, r15
0x14006ce48  jz      short loc_14006CE69
0x14006ce4a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14006ce51  lock xadd [r15+40h], rax
0x14006ce57  sub     rax, 1
0x14006ce5b  jg      short loc_14006CE69
0x14006ce5d  test    rax, rax
0x14006ce60  jz      short loc_14006CE90
0x14006ce62  mov     ecx, 0Eh
  ... truncated ...
```
