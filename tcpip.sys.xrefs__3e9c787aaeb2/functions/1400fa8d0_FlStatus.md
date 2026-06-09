# FlStatus

- ea: `0x1400fa8d0`
- end: `0x1400fafde`
- name: `FlStatus`
- size: `1806`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `0`
- callee_count: `20`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x140014890`
- `0x1400148b0`
- `0x140063720`
- `0x1400fa868`
- `0x1400fa8d0`
- `0x1400fafe4`
- `0x1400fb064`
- `0x1400fb124`
- `0x1400fb148`
- `0x1400fb1bc`
- `0x1400fb2f0`
- `0x1400fb308`
- `0x1400fb4c0`
- `0x1400fb57c`
- `0x1401048d0`
- `0x14012e7d8`
- `0x1401c0fd0`
- `0x1401c1200`
- `0x1401c1280`
- `0x1401c1580`

## import_xrefs

- `ntoskrnl!RtlInitEnumerationHashTable` at `0x1400faa6c`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x1400faa6c`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1400fa9b6`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1400faaad`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1400fac63`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1400fad88`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1400fa9b6`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1400faaad`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1400fac63`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1400fad88`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1400faae2`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1400fab13`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1400fadbd`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1400faed0`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1400faae2`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1400fab13`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1400fadbd`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1400faed0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400fab3a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400fab3a`

## pseudocode

```c
void __fastcall FlStatus(char *Context, __int64 a2)
{
  int v4; // esi
  int v5; // ebx
  int v6; // r8d
  unsigned int v7; // r12d
  unsigned int v8; // r13d
  __int64 v9; // rsi
  __int64 v10; // rcx
  __int64 v11; // rdx
  char *v12; // rsi
  __int64 j; // rbx
  int v14; // esi
  int v15; // esi
  int v16; // esi
  int v17; // esi
  _DWORD *v18; // rcx
  char *v19; // r15
  __int64 v20; // rsi
  __int64 v21; // rax
  int v22; // edx
  int v23; // ecx
  __int64 i; // rbx
  char *v25; // rbx
  char v26; // al
  size_t v27; // r8
  __int16 v28; // ax
  char v29; // al
  __int64 v30; // rdx
  int v31; // eax
  int v32; // [rsp+28h] [rbp-D8h]
  _DWORD v33[4]; // [rsp+70h] [rbp-90h] BYREF
  int v34; // [rsp+80h] [rbp-80h]
  PVOID P; // [rsp+88h] [rbp-78h] BYREF
  __int64 v36; // [rsp+90h] [rbp-70h] BYREF
  char v37; // [rsp+98h] [rbp-68h]
  __int16 v38; // [rsp+99h] [rbp-67h]
  __int16 v39; // [rsp+9Bh] [rbp-65h]
  __int16 v40; // [rsp+9Dh] [rbp-63h]
  char v41; // [rsp+9Fh] [rbp-61h]
  char *v42; // [rsp+A0h] [rbp-60h]
  struct _RTL_DYNAMIC_HASH_TABLE_ENUMERATOR Enumerator; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v44[64]; // [rsp+D0h] [rbp-30h] BYREF

  memset(v44, 0, sizeof(v44));
  v4 = *(_DWORD *)(a2 + 20);
  v33[0] = 0;
  v5 = 0;
  P = 0;
  v34 = 0;
  memset(&Enumerator, 0, sizeof(Enumerator));
  if ( (unsigned __int8)FlpValidateAndUpdateStatusIndication(a2, &P) )
  {
    v7 = 9;
    v8 = 0;
    if ( (BYTE1(WPP_MAIN_CB.Dpc.DeferredContext) & 1) != 0 )
      McTemplateK0qqq_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
        (unsigned int)TCPIP_STATUS_INDICATION,
        (unsigned int)MICROSOFT_TCPIP_PROVIDER,
        *((_DWORD *)Context + 294),
        *(_WORD *)(*((_QWORD *)Context + 4) + 92LL),
        v4);
    if ( v4 == 1073807383 )
    {
      v9 = *(_QWORD *)(a2 + 48);
      v10 = *((_QWORD *)Context + 153);
      v11 = *(_QWORD *)(v9 + 16);
      if ( v11 != v10 && (BYTE6(WPP_MAIN_CB.Dpc.DeferredRoutine) & 0x20) != 0 )
        McTemplateK0qxqqqbr4qqxxq_EtwWriteTransfer(v10, v11, v6, *((_DWORD *)Context + 294), v11, v32);
      *((_QWORD *)Context + 153) = *(_QWORD *)(v9 + 16);
      *((_QWORD *)Context + 154) = *(_QWORD *)(v9 + 24);
      LOBYTE(v33[0]) = 4;
      goto LABEL_7;
    }
    if ( v4 <= 1073872902 )
    {
      if ( v4 != 1073872902 )
      {
        switch ( v4 )
        {
          case 1073807364:
            v7 = 5;
            goto LABEL_7;
          case 1073807365:
            v7 = 6;
            goto LABEL_7;
          case 1073807384:
            goto LABEL_58;
          case 1073807394:
            LOBYTE(v33[0]) = 8;
            goto LABEL_7;
          case 1073807395:
            if ( *((_DWORD *)Context + 78) == 18 )
              goto LABEL_18;
            v21 = *(_QWORD *)(a2 + 48);
            LOBYTE(v33[0]) = 1;
            v22 = *(_DWORD *)(v21 + 4);
            *((_DWORD *)Context + 302) = v22;
            v23 = *(_DWORD *)(*(_QWORD *)(a2 + 48) + 8LL);
            *((_DWORD *)Context + 303) = v23;
            if ( (BYTE2(WPP_MAIN_CB.Dpc.DeferredRoutine) & 4) != 0 )
              McTemplateK0qqxq_EtwWriteTransfer(
                v23,
                v22,
                v6,
                *((_DWORD *)Context + 294),
                v22,
                v23,
                *((_DWORD *)Context + 296));
            break;
          case 1073807398:
            v30 = *(_QWORD *)(a2 + 48);
            if ( *(unsigned __int16 *)(*((_QWORD *)Context + 4) + 92LL) != *(_DWORD *)(v30 + 8) )
              goto LABEL_18;
            *((_DWORD *)Context + 302) = *(_DWORD *)(v30 + 12);
            *((_DWORD *)Context + 303) = *(_DWORD *)(*(_QWORD *)(a2 + 48) + 16LL);
LABEL_58:
            LOBYTE(v33[0]) = 1;
            break;
          default:
            goto LABEL_18;
        }
        goto LABEL_7;
      }
      v25 = (char *)P;
      v26 = FlpValidateTaskOffloadCapabilityChange(P) & 1;
      LOBYTE(v34) = 4 * v26;
      if ( v26 )
      {
        v12 = Context + 1320;
        v8 = 220;
        memset(Context + 1320, 0, 0xDCu);
        v27 = 220;
        if ( *((_WORD *)v25 + 1) <= 0xDCu )
          v27 = *((unsigned __int16 *)v25 + 1);
        memmove(Context + 1320, v25, v27);
        v28 = *((_WORD *)v25 + 1);
        v7 = 8;
        if ( (unsigned __int16)v28 > 0xDCu )
          v28 = 220;
        *((_WORD *)Context + 661) = v28;
        v29 = v25[1];
        if ( (unsigned __int8)v29 > 8u )
          v29 = 8;
        Context[1321] = v29;
        FlpModifyTaskOffloadCapabilities(Context, (__int64)(Context + 1320));
        v5 = v34;
        goto LABEL_8;
      }
LABEL_18:
      if ( P )
        ExFreePoolWithTag(P, 0);
      return;
    }
    v14 = v4 - 1073872903;
    if ( !v14 )
    {
      v12 = (char *)P;
      if ( (unsigned __int8)FlpValidateTaskOffloadCapabilityChange(P) )
      {
        v7 = 7;
        v8 = 220;
LABEL_8:
        if ( ExAcquireRundownProtectionCacheAwareEx(*((PEX_RUNDOWN_REF_CACHE_AWARE *)Context + 9), 1u) )
        {
          if ( v7 != 9 )
            (*(void (__fastcall **)(_QWORD, _QWORD, char *, _QWORD))(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)Context + 4)
                                                                                           + 216LL)
                                                                               + 8LL)
                                                                   + 112LL))(
              *((_QWORD *)Context + 37),
              v7,
              v12,
              v8);
          if ( v5 )
          {
            v36 = *((_QWORD *)Context + 37);
            v40 = 0;
            v41 = 0;
            v42 = Context + 1240;
            v37 = v34;
            v38 = *(_WORD *)((char *)&v34 + 1);
            v39 = HIBYTE(v34);
            for ( i = FlpGetFirstClientInterface(Context, &Enumerator);
                  i;
                  i = FlpGetNextClientInterface(Context, &Enumerator) )
            {
              v36 = *(_QWORD *)(i + 136);
              if ( ExAcquireRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(i + 56), 1u) )
              {
                (*(void (__fastcall **)(__int64 *))(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)Context + 4) + 216LL) + 8LL)
                                                  + 24LL))(&v36);
                ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(i + 56), 1u);
              }
              FlpDereferenceClientInterface(i);
            }
          }
          if ( v33[0] )
          {
            v36 = *((_QWORD *)Context + 38);
            v40 = 0;
            v41 = 0;
            v42 = Context + 1208;
            v37 = v33[0];
            v38 = *(_WORD *)((char *)v33 + 1);
            v39 = HIBYTE(v33[0]);
            LOWORD(v33[0]) = 0;
            BYTE2(v33[0]) = 0;
            FlpInterfaceAcquireWriteLock(Context, v33);
            RtlInitEnumerationHashTable((PRTL_DYNAMIC_HASH_TABLE)(Context + 208), &Enumerator);
            FlpInterfaceReleaseReadLock(Context, v33);
            for ( j = FlpGetNextClientInterface(Context, &Enumerator);
                  j;
                  j = FlpGetNextClientInterface(Context, &Enumerator) )
            {
              v36 = *(_QWORD *)(j + 144);
              if ( ExAcquireRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(j + 56), 1u) )
              {
                (*(void (__fastcall **)(__int64 *))(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)Context + 4) + 216LL) + 8LL)
                                                  + 48LL))(&v36);
                ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(j + 56), 1u);
              }
              FlpDereferenceClientInterface(j);
            }
          }
          ExReleaseRundownProtectionCacheAwareEx(*((PEX_RUNDOWN_REF_CACHE_AWARE *)Context + 9), 1u);
        }
        goto LABEL_18;
      }
      goto LABEL_18;
    }
    v15 = v14 - 121;
    if ( v15 )
    {
      v16 = v15 - 65489;
      if ( !v16 )
      {
        if ( (int)FlpSerializedNdisRequest(Context, (__int64)P, 0) < 0 )
          goto LABEL_18;
        goto LABEL_72;
      }
      v17 = v16 - 2;
      if ( v17 )
      {
        if ( v17 == 2 )
        {
          v18 = *(_DWORD **)(a2 + 48);
          if ( v18[2] == 1 && v18[4] >= 0x9Cu )
          {
            v19 = (char *)v18 + (unsigned int)v18[3];
            v20 = FlpPreProcessWakePacketIndication(Context, v19, v44);
            if ( v20 )
            {
              if ( ExAcquireRundownProtectionCacheAwareEx(*((PEX_RUNDOWN_REF_CACHE_AWARE *)Context + 9), 1u) )
              {
                (*(void (__fastcall **)(_QWORD, __int64, __int64, __int64, _BYTE *, int))(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)Context + 4) + 216LL) + 8LL)
                                                                                        + 128LL))(
                  *((_QWORD *)Context + 37),
                  1,
                  v20,
                  368,
                  v44,
                  64);
                ExReleaseRundownProtectionCacheAwareEx(*((PEX_RUNDOWN_REF_CACHE_AWARE *)Context + 9), 1u);
              }
              FlpPostProcessWakePacketIndication(Context, v20, v19, v44);
              goto LABEL_7;
            }
          }
        }
        goto LABEL_18;
      }
      if ( *((_DWORD *)Context + 202) != *((_DWORD *)P + 2) || *((_DWORD *)Context + 207) != *((_DWORD *)P + 7) )
      {
        v31 = FlpSerializedNdisRequest(Context, (__int64)P, 0);
        if ( v31 < 0 )
        {
          if ( (BYTE2(WPP_MAIN_CB.Dpc.DeferredRoutine) & 4) != 0 )
            McTemplateK0qqqq_EtwWriteTransfer(
              (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
              (unsigned int)TCPIP_FRAMING_WOL_CAPABILITIES_UPDATE,
              (unsigned int)MICROSOFT_TCPIP_PROVIDER,
              *((_DWORD *)Context + 294),
              *(_WORD *)(*((_QWORD *)Context + 4) + 92LL),
              2,
              v31);
          goto LABEL_18;
        }
LABEL_72:
        P = 0;
      }
    }
    else if ( *(_BYTE *)(*((_QWORD *)Context + 4) + 656LL) && (int)FlpSerializedNdisRequest(Context, 0, 0) < 0 )
    {
      goto LABEL_18;
    }
LABEL_7:
    v12 = 0;
    goto LABEL_8;
  }
}

```

## disassembly

```asm
0x1400fa8d0  push    rbp
0x1400fa8d2  push    rbx
0x1400fa8d3  push    rsi
0x1400fa8d4  push    rdi
0x1400fa8d5  push    r14
0x1400fa8d7  push    r15
0x1400fa8d9  lea     rbp, [rsp-28h]
0x1400fa8de  sub     rsp, 128h
0x1400fa8e5  mov     rax, cs:__security_cookie
0x1400fa8ec  xor     rax, rsp
0x1400fa8ef  mov     [rbp+50h+var_40], rax
0x1400fa8f3  mov     r15, rdx
0x1400fa8f6  mov     rdi, rcx
0x1400fa8f9  xor     edx, edx; Val
0x1400fa8fb  lea     rcx, [rbp+50h+var_80]; void *
0x1400fa8ff  mov     r8d, 40h ; '@'; Size
0x1400fa905  call    memset
0x1400fa90a  mov     esi, [r15+14h]
0x1400fa90e  lea     rdx, [rbp+50h+P]
0x1400fa912  xor     r14d, r14d
0x1400fa915  xorps   xmm0, xmm0
0x1400fa918  xor     eax, eax
0x1400fa91a  mov     [rsp+150h+var_E0], r14d
0x1400fa91f  mov     ebx, r14d
0x1400fa922  mov     [rbp+50h+P], r14
0x1400fa926  mov     rcx, r15
0x1400fa929  mov     [rbp+50h+var_D0], ebx
0x1400fa92c  movups  xmmword ptr [rbp+50h+Enumerator], xmm0
0x1400fa930  mov     qword ptr [rbp+50h+Enumerator.BucketIndex], rax
0x1400fa934  movups  xmmword ptr [rbp+50h+Enumerator+10h], xmm0
0x1400fa938  call    FlpValidateAndUpdateStatusIndication
0x1400fa93d  test    al, al
0x1400fa93f  jz      loc_1400FAB46
0x1400fa945  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredContext+1, 1
0x1400fa94c  mov     [rsp+150h+arg_10], r12
0x1400fa954  mov     r12d, 9
0x1400fa95a  mov     [rsp+150h+var_30], r13
0x1400fa962  mov     r13d, r14d
0x1400fa965  jnz     loc_1400FACEB
0x1400fa96b  cmp     esi, 40010017h
0x1400fa971  jnz     loc_1400FAB63
0x1400fa977  mov     rsi, [r15+30h]
0x1400fa97b  mov     rcx, [rdi+4C8h]
0x1400fa982  mov     rdx, [rsi+10h]
0x1400fa986  cmp     rdx, rcx
0x1400fa989  jnz     loc_1400FAB9E
0x1400fa98f  mov     rax, [rsi+10h]
0x1400fa993  mov     [rdi+4C8h], rax
0x1400fa99a  mov     rax, [rsi+18h]
0x1400fa99e  mov     [rdi+4D0h], rax
0x1400fa9a5  mov     byte ptr [rsp+150h+var_E0], 4
0x1400fa9aa  mov     rsi, rbx
0x1400fa9ad  mov     rcx, [rdi+48h]; RunRefCacheAware
0x1400fa9b1  mov     edx, 1; Count
0x1400fa9b6  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x1400fa9bd  nop     dword ptr [rax+rax+00h]
0x1400fa9c2  test    al, al
0x1400fa9c4  jz      def_1400FAB98; jumptable 00000001400FAB98 default case, cases 1073807366-1073807383,1073807385-1073807393,1073807396,1073807397
0x1400fa9ca  cmp     r12d, 9
0x1400fa9ce  jz      short loc_1400FA9F8
0x1400fa9d0  mov     rax, [rdi+20h]
0x1400fa9d4  mov     r9d, r13d
0x1400fa9d7  mov     r8, rsi
0x1400fa9da  mov     edx, r12d
0x1400fa9dd  mov     rcx, [rax+0D8h]
0x1400fa9e4  mov     rax, [rcx+8]
0x1400fa9e8  mov     rcx, [rdi+128h]
0x1400fa9ef  mov     rax, [rax+70h]
0x1400fa9f3  call    _guard_dispatch_icall
0x1400fa9f8  test    ebx, ebx
0x1400fa9fa  jnz     loc_1400FAD21
0x1400faa00  cmp     [rsp+150h+var_E0], r14d
0x1400faa05  jz      loc_1400FAB0A
0x1400faa0b  mov     rax, [rdi+130h]
0x1400faa12  lea     rdx, [rsp+150h+var_E0]
0x1400faa17  mov     [rbp+50h+var_C0], rax
0x1400faa1b  mov     rcx, rdi
0x1400faa1e  xor     eax, eax
0x1400faa20  mov     [rbp+50h+var_B7+3], eax
0x1400faa23  mov     [rbp-67h], eax
0x1400faa26  mov     [rbp+50h+var_B3], ax
0x1400faa2a  mov     [rbp+50h+var_B1], al
0x1400faa2d  lea     rax, [rdi+4B8h]
0x1400faa34  mov     [rbp+50h+var_B0], rax
0x1400faa38  movzx   eax, byte ptr [rsp+150h+var_E0]
0x1400faa3d  mov     [rbp+50h+var_B8], al
0x1400faa40  movzx   eax, word ptr [rsp+150h+var_E0+1]
0x1400faa45  mov     word ptr [rbp+50h+var_B7], ax
0x1400faa49  movzx   eax, byte ptr [rsp+150h+var_E0+3]
0x1400faa4e  mov     byte ptr [rbp+50h+var_B7+2], al
0x1400faa51  xor     eax, eax
0x1400faa53  mov     word ptr [rsp+150h+var_E0], ax
0x1400faa58  mov     byte ptr [rsp+150h+var_E0+2], al
0x1400faa5c  call    FlpInterfaceAcquireWriteLock
0x1400faa61  lea     rcx, [rdi+0D0h]; HashTable
0x1400faa68  lea     rdx, [rbp+50h+Enumerator]; Enumerator
0x1400faa6c  call    cs:__imp_RtlInitEnumerationHashTable
0x1400faa73  nop     dword ptr [rax+rax+00h]
0x1400faa78  lea     rdx, [rsp+150h+var_E0]
0x1400faa7d  mov     rcx, rdi
0x1400faa80  call    FlpInterfaceReleaseReadLock
0x1400faa85  lea     rdx, [rbp+50h+Enumerator]
0x1400faa89  mov     rcx, rdi
0x1400faa8c  call    FlpGetNextClientInterface
0x1400faa91  mov     rbx, rax
0x1400faa94  test    rax, rax
0x1400faa97  jz      short loc_1400FAB0A
0x1400faa99  mov     rcx, [rbx+90h]
0x1400faaa0  mov     edx, 1; Count
0x1400faaa5  mov     [rbp+50h+var_C0], rcx
0x1400faaa9  mov     rcx, [rbx+38h]; RunRefCacheAware
0x1400faaad  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x1400faab4  nop     dword ptr [rax+rax+00h]
0x1400faab9  test    al, al
0x1400faabb  jz      short loc_1400FAAEE
0x1400faabd  mov     rax, [rdi+20h]
0x1400faac1  mov     rcx, [rax+0D8h]
0x1400faac8  mov     rax, [rcx+8]
0x1400faacc  lea     rcx, [rbp+50h+var_C0]
0x1400faad0  mov     rax, [rax+30h]
0x1400faad4  call    _guard_dispatch_icall
0x1400faad9  mov     rcx, [rbx+38h]; RunRef
0x1400faadd  mov     edx, 1; Count
0x1400faae2  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x1400faae9  nop     dword ptr [rax+rax+00h]
0x1400faaee  mov     rcx, rbx
0x1400faaf1  call    FlpDereferenceClientInterface
0x1400faaf6  lea     rdx, [rbp+50h+Enumerator]
0x1400faafa  mov     rcx, rdi
0x1400faafd  call    FlpGetNextClientInterface
0x1400fab02  mov     rbx, rax
0x1400fab05  test    rax, rax
0x1400fab08  jnz     short loc_1400FAA99
0x1400fab0a  mov     rcx, [rdi+48h]; RunRef
0x1400fab0e  mov     edx, 1; Count
0x1400fab13  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x1400fab1a  nop     dword ptr [rax+rax+00h]
0x1400fab1f  mov     rcx, [rbp+50h+P]; jumptable 00000001400FAB98 default case, cases 1073807366-1073807383,1073807385-1073807393,1073807396,1073807397
0x1400fab23  mov     r13, [rsp+150h+var_30]
0x1400fab2b  mov     r12, [rsp+150h+arg_10]
0x1400fab33  test    rcx, rcx
0x1400fab36  jz      short loc_1400FAB46
0x1400fab38  xor     edx, edx; Tag
0x1400fab3a  call    cs:__imp_ExFreePoolWithTag
0x1400fab41  nop     dword ptr [rax+rax+00h]
0x1400fab46  mov     rcx, [rbp+50h+var_40]
0x1400fab4a  xor     rcx, rsp; StackCookie
0x1400fab4d  call    __security_check_cookie
0x1400fab52  add     rsp, 128h
0x1400fab59  pop     r15
0x1400fab5b  pop     r14
0x1400fab5d  pop     rdi
0x1400fab5e  pop     rsi
0x1400fab5f  pop     rbx
0x1400fab60  pop     rbp
0x1400fab61  retn
0x1400fab63  cmp     esi, 40020006h
0x1400fab69  jg      short loc_1400FABEA
0x1400fab6b  jz      loc_1400FADEA
0x1400fab71  add     esi, 0BFFEFFFCh; switch 35 cases
0x1400fab77  cmp     esi, 22h
0x1400fab7a  ja      short def_1400FAB98; jumptable 00000001400FAB98 default case, cases 1073807366-1073807383,1073807385-1073807393,1073807396,1073807397
0x1400fab7c  lea     rdx, cs:140000000h
0x1400fab83  movsxd  rax, esi
0x1400fab86  movzx   eax, ds:(byte_1401F5818 - 140000000h)[rdx+rax]
0x1400fab8e  mov     ecx, ds:(jpt_1400FAB98 - 140000000h)[rdx+rax*4]
0x1400fab95  add     rcx, rdx
0x1400fab98  jmp     rcx; switch jump
0x1400fab9e  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+6, 20h
0x1400faba5  jz      loc_1400FA98F
0x1400fabab  mov     eax, [rsi+4]
0x1400fabae  mov     r9d, [rdi+498h]
0x1400fabb5  mov     [rsp+150h+var_E8], eax
0x1400fabb9  mov     rax, [rsi+18h]
0x1400fabbd  mov     [rsp+150h+var_F0], rax
0x1400fabc2  mov     eax, [rdi+4A0h]
0x1400fabc8  mov     [rsp+150h+var_F8], rcx
0x1400fabcd  mov     [rsp+150h+var_100], eax
0x1400fabd1  mov     eax, [rdi+4ECh]
0x1400fabd7  mov     [rsp+150h+var_108], eax
0x1400fabdb  mov     [rsp+150h+var_130], rdx
0x1400fabe0  call    McTemplateK0qxqqqbr4qqxxq_EtwWriteTransfer
0x1400fabe5  jmp     loc_1400FA98F
0x1400fabea  sub     esi, 40020007h
0x1400fabf0  jz      loc_1400FAFB9
0x1400fabf6  sub     esi, 79h ; 'y'
0x1400fabf9  jz      loc_1400FAF80
0x1400fabff  sub     esi, 0FFD1h
0x1400fac05  jz      loc_1400FAF53
0x1400fac0b  sub     esi, 2
0x1400fac0e  jz      loc_1400FAF2C
0x1400fac14  cmp     esi, 2
0x1400fac17  jnz     def_1400FAB98; jumptable 00000001400FAB98 default case, cases 1073807366-1073807383,1073807385-1073807393,1073807396,1073807397
0x1400fac1d  mov     rcx, [r15+30h]
0x1400fac21  cmp     dword ptr [rcx+8], 1
0x1400fac25  jnz     def_1400FAB98; jumptable 00000001400FAB98 default case, cases 1073807366-1073807383,1073807385-1073807393,1073807396,1073807397
0x1400fac2b  cmp     dword ptr [rcx+10h], 9Ch
0x1400fac32  jb      def_1400FAB98; jumptable 00000001400FAB98 default case, cases 1073807366-1073807383,1073807385-1073807393,1073807396,1073807397
0x1400fac38  mov     r15d, [rcx+0Ch]
0x1400fac3c  lea     r8, [rbp+50h+var_80]
0x1400fac40  add     r15, rcx
0x1400fac43  mov     rcx, rdi
0x1400fac46  mov     rdx, r15
0x1400fac49  call    FlpPreProcessWakePacketIndication
0x1400fac4e  mov     rsi, rax
0x1400fac51  test    rax, rax
0x1400fac54  jz      def_1400FAB98; jumptable 00000001400FAB98 default case, cases 1073807366-1073807383,1073807385-1073807393,1073807396,1073807397
0x1400fac5a  mov     rcx, [rdi+48h]; RunRefCacheAware
0x1400fac5e  mov     edx, 1; Count
0x1400fac63  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x1400fac6a  nop     dword ptr [rax+rax+00h]
0x1400fac6f  test    al, al
0x1400fac71  jnz     loc_1400FAE86
0x1400fac77  lea     r9, [rbp+50h+var_80]
0x1400fac7b  mov     r8, r15
0x1400fac7e  mov     rdx, rsi
0x1400fac81  mov     rcx, rdi
0x1400fac84  call    FlpPostProcessWakePacketIndication
0x1400fac89  jmp     loc_1400FA9AA
0x1400fac8e  cmp     dword ptr [rdi+138h], 12h; jumptable 00000001400FAB98 case 1073807395
0x1400fac95  jz      def_1400FAB98; jumptable 00000001400FAB98 default case, cases 1073807366-1073807383,1073807385-1073807393,1073807396,1073807397
0x1400fac9b  mov     rax, [r15+30h]
0x1400fac9f  mov     byte ptr [rsp+150h+var_E0], 1
0x1400faca4  mov     edx, [rax+4]
0x1400faca7  mov     [rdi+4B8h], edx
0x1400facad  mov     rax, [r15+30h]
0x1400facb1  mov     ecx, [rax+8]
0x1400facb4  mov     [rdi+4BCh], ecx
0x1400facba  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+2, 4
0x1400facc1  jz      loc_1400FA9AA
0x1400facc7  mov     eax, [rdi+4A0h]
0x1400faccd  mov     r9d, [rdi+498h]
0x1400facd4  mov     [rsp+150h+var_120], eax
0x1400facd8  mov     [rsp+150h+var_128], rcx
0x1400facdd  mov     dword ptr [rsp+150h+var_130], edx
0x1400face1  call    McTemplateK0qqxq_EtwWriteTransfer
0x1400face6  jmp     loc_1400FA9AA
0x1400faceb  mov     rax, [rdi+20h]
0x1400facef  lea     r8, MICROSOFT_TCPIP_PROVIDER
0x1400facf6  mov     r9d, [rdi+498h]
0x1400facfd  lea     rdx, TCPIP_STATUS_INDICATION
0x1400fad04  mov     dword ptr [rsp+150h+var_128], esi
0x1400fad08  movzx   ecx, word ptr [rax+5Ch]
0x1400fad0c  mov     dword ptr [rsp+150h+var_130], ecx
0x1400fad10  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1400fad17  call    McTemplateK0qqq_EtwWriteTransfer
0x1400fad1c  jmp     loc_1400FA96B
0x1400fad21  mov     rax, [rdi+128h]
0x1400fad28  lea     rdx, [rbp+50h+Enumerator]
0x1400fad2c  mov     [rbp+50h+var_C0], rax
0x1400fad30  mov     rcx, rdi
0x1400fad33  xor     eax, eax
0x1400fad35  mov     [rbp+50h+var_B7+3], eax
0x1400fad38  mov     [rbp+50h+var_B7], eax
0x1400fad3b  mov     [rbp+50h+var_B3], ax
0x1400fad3f  mov     [rbp+50h+var_B1], al
0x1400fad42  lea     rax, [rdi+4D8h]
0x1400fad49  mov     [rbp+50h+var_B0], rax
0x1400fad4d  movzx   eax, byte ptr [rbp+50h+var_D0]
0x1400fad51  mov     [rbp+50h+var_B8], al
0x1400fad54  movzx   eax, word ptr [rbp+50h+var_D0+1]
0x1400fad58  mov     word ptr [rbp+50h+var_B7], ax
0x1400fad5c  movzx   eax, byte ptr [rbp+50h+var_D0+3]
0x1400fad60  mov     byte ptr [rbp+50h+var_B7+2], al
0x1400fad63  call    FlpGetFirstClientInterface
0x1400fad68  mov     rbx, rax
0x1400fad6b  test    rax, rax
0x1400fad6e  jz      loc_1400FAA00
0x1400fad74  mov     rcx, [rbx+88h]
0x1400fad7b  mov     edx, 1; Count
0x1400fad80  mov     [rbp+50h+var_C0], rcx
0x1400fad84  mov     rcx, [rbx+38h]; RunRefCacheAware
0x1400fad88  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x1400fad8f  nop     dword ptr [rax+rax+00h]
0x1400fad94  test    al, al
0x1400fad96  jz      short loc_1400FADC9
0x1400fad98  mov     rax, [rdi+20h]
0x1400fad9c  mov     rcx, [rax+0D8h]
0x1400fada3  mov     rax, [rcx+8]
0x1400fada7  lea     rcx, [rbp+50h+var_C0]
0x1400fadab  mov     rax, [rax+18h]
0x1400fadaf  call    _guard_dispatch_icall
0x1400fadb4  mov     rcx, [rbx+38h]; RunRef
0x1400fadb8  mov     edx, 1; Count
0x1400fadbd  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x1400fadc4  nop     dword ptr [rax+rax+00h]
0x1400fadc9  mov     rcx, rbx
0x1400fadcc  call    FlpDereferenceClientInterface
0x1400fadd1  lea     rdx, [rbp+50h+Enumerator]
0x1400fadd5  mov     rcx, rdi
0x1400fadd8  call    FlpGetNextClientInterface
0x1400faddd  mov     rbx, rax
0x1400fade0  test    rax, rax
0x1400fade3  jnz     short loc_1400FAD74
0x1400fade5  jmp     loc_1400FAA00
0x1400fadea  mov     rbx, [rbp+50h+P]
0x1400fadee  mov     rcx, rbx
0x1400fadf1  call    FlpValidateTaskOffloadCapabilityChange
0x1400fadf6  and     al, 1
0x1400fadf8  movzx   ecx, al
  ... truncated ...
```
