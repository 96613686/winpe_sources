# FlStatus

- ea: `0x1400c7330`
- end: `0x1400c7a3e`
- name: `FlStatus`
- size: `1806`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `0`
- callee_count: `20`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x140053fc0`
- `0x140053fe0`
- `0x140077580`
- `0x1400c72c4`
- `0x1400c7330`
- `0x1400c7a44`
- `0x1400c7ac4`
- `0x1400c7b84`
- `0x1400c81f4`
- `0x1400c8268`
- `0x1400c839c`
- `0x1400c83b4`
- `0x1400c87a4`
- `0x1400c8860`
- `0x1400c8e74`
- `0x140124aa0`
- `0x1401bf4d0`
- `0x1401bf700`
- `0x1401bf780`
- `0x1401bfa80`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1400c7542`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1400c7573`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1400c781d`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1400c7930`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1400c7542`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1400c7573`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1400c781d`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1400c7930`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1400c7416`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1400c750d`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1400c76c3`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1400c77e8`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1400c7416`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1400c750d`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1400c76c3`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1400c77e8`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x1400c74cc`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x1400c74cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c759a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c759a`

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
    if ( (*((_BYTE *)&WPP_MAIN_CB.Reserved + 9) & 1) != 0 )
      McTemplateK0qqq_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
        (unsigned int)&TCPIP_STATUS_INDICATION,
        (unsigned int)&MICROSOFT_TCPIP_PROVIDER,
        *((_DWORD *)Context + 294),
        *(_WORD *)(*((_QWORD *)Context + 4) + 92LL),
        v4);
    if ( v4 == 1073807383 )
    {
      v9 = *(_QWORD *)(a2 + 48);
      v10 = *((_QWORD *)Context + 153);
      v11 = *(_QWORD *)(v9 + 16);
      if ( v11 != v10 && (BYTE6(WPP_MAIN_CB.Reserved) & 0x20) != 0 )
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
            if ( (BYTE2(WPP_MAIN_CB.Reserved) & 4) != 0 )
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
        FlpModifyTaskOffloadCapabilities(Context, Context + 1320);
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
          if ( (BYTE2(WPP_MAIN_CB.Reserved) & 4) != 0 )
            McTemplateK0qqqq_EtwWriteTransfer(
              (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
              (unsigned int)&TCPIP_FRAMING_WOL_CAPABILITIES_UPDATE,
              (unsigned int)&MICROSOFT_TCPIP_PROVIDER,
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
0x1400c7330  push    rbp
0x1400c7332  push    rbx
0x1400c7333  push    rsi
0x1400c7334  push    rdi
0x1400c7335  push    r14
0x1400c7337  push    r15
0x1400c7339  lea     rbp, [rsp-28h]
0x1400c733e  sub     rsp, 128h
0x1400c7345  mov     rax, cs:__security_cookie
0x1400c734c  xor     rax, rsp
0x1400c734f  mov     [rbp+50h+var_40], rax
0x1400c7353  mov     r15, rdx
0x1400c7356  mov     rdi, rcx
0x1400c7359  xor     edx, edx; Val
0x1400c735b  lea     rcx, [rbp+50h+var_80]; void *
0x1400c735f  mov     r8d, 40h ; '@'; Size
0x1400c7365  call    memset
0x1400c736a  mov     esi, [r15+14h]
0x1400c736e  lea     rdx, [rbp+50h+P]
0x1400c7372  xor     r14d, r14d
0x1400c7375  xorps   xmm0, xmm0
0x1400c7378  xor     eax, eax
0x1400c737a  mov     [rsp+150h+var_E0], r14d
0x1400c737f  mov     ebx, r14d
0x1400c7382  mov     [rbp+50h+P], r14
0x1400c7386  mov     rcx, r15
0x1400c7389  mov     [rbp+50h+var_D0], ebx
0x1400c738c  movups  xmmword ptr [rbp+50h+Enumerator], xmm0
0x1400c7390  mov     qword ptr [rbp+50h+Enumerator.BucketIndex], rax
0x1400c7394  movups  xmmword ptr [rbp+50h+Enumerator+10h], xmm0
0x1400c7398  call    FlpValidateAndUpdateStatusIndication
0x1400c739d  test    al, al
0x1400c739f  jz      loc_1400C75A6
0x1400c73a5  test    byte ptr cs:WPP_MAIN_CB+149h, 1
0x1400c73ac  mov     [rsp+150h+arg_10], r12
0x1400c73b4  mov     r12d, 9
0x1400c73ba  mov     [rsp+150h+var_30], r13
0x1400c73c2  mov     r13d, r14d
0x1400c73c5  jnz     loc_1400C774B
0x1400c73cb  cmp     esi, 40010017h
0x1400c73d1  jnz     loc_1400C75C3
0x1400c73d7  mov     rsi, [r15+30h]
0x1400c73db  mov     rcx, [rdi+4C8h]
0x1400c73e2  mov     rdx, [rsi+10h]
0x1400c73e6  cmp     rdx, rcx
0x1400c73e9  jnz     loc_1400C75FE
0x1400c73ef  mov     rax, [rsi+10h]
0x1400c73f3  mov     [rdi+4C8h], rax
0x1400c73fa  mov     rax, [rsi+18h]
0x1400c73fe  mov     [rdi+4D0h], rax
0x1400c7405  mov     byte ptr [rsp+150h+var_E0], 4
0x1400c740a  mov     rsi, rbx
0x1400c740d  mov     rcx, [rdi+48h]; RunRefCacheAware
0x1400c7411  mov     edx, 1; Count
0x1400c7416  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x1400c741d  nop     dword ptr [rax+rax+00h]
0x1400c7422  test    al, al
0x1400c7424  jz      def_1400C75F8; jumptable 00000001400C75F8 default case, cases 1073807366-1073807383,1073807385-1073807393,1073807396,1073807397
0x1400c742a  cmp     r12d, 9
0x1400c742e  jz      short loc_1400C7458
0x1400c7430  mov     rax, [rdi+20h]
0x1400c7434  mov     r9d, r13d
0x1400c7437  mov     r8, rsi
0x1400c743a  mov     edx, r12d
0x1400c743d  mov     rcx, [rax+0D8h]
0x1400c7444  mov     rax, [rcx+8]
0x1400c7448  mov     rcx, [rdi+128h]
0x1400c744f  mov     rax, [rax+70h]
0x1400c7453  call    _guard_dispatch_icall
0x1400c7458  test    ebx, ebx
0x1400c745a  jnz     loc_1400C7781
0x1400c7460  cmp     [rsp+150h+var_E0], r14d
0x1400c7465  jz      loc_1400C756A
0x1400c746b  mov     rax, [rdi+130h]
0x1400c7472  lea     rdx, [rsp+150h+var_E0]
0x1400c7477  mov     [rbp+50h+var_C0], rax
0x1400c747b  mov     rcx, rdi
0x1400c747e  xor     eax, eax
0x1400c7480  mov     [rbp+50h+var_B7+3], eax
0x1400c7483  mov     [rbp-67h], eax
0x1400c7486  mov     [rbp+50h+var_B3], ax
0x1400c748a  mov     [rbp+50h+var_B1], al
0x1400c748d  lea     rax, [rdi+4B8h]
0x1400c7494  mov     [rbp+50h+var_B0], rax
0x1400c7498  movzx   eax, byte ptr [rsp+150h+var_E0]
0x1400c749d  mov     [rbp+50h+var_B8], al
0x1400c74a0  movzx   eax, word ptr [rsp+150h+var_E0+1]
0x1400c74a5  mov     word ptr [rbp+50h+var_B7], ax
0x1400c74a9  movzx   eax, byte ptr [rsp+150h+var_E0+3]
0x1400c74ae  mov     byte ptr [rbp+50h+var_B7+2], al
0x1400c74b1  xor     eax, eax
0x1400c74b3  mov     word ptr [rsp+150h+var_E0], ax
0x1400c74b8  mov     byte ptr [rsp+150h+var_E0+2], al
0x1400c74bc  call    FlpInterfaceAcquireWriteLock
0x1400c74c1  lea     rcx, [rdi+0D0h]; HashTable
0x1400c74c8  lea     rdx, [rbp+50h+Enumerator]; Enumerator
0x1400c74cc  call    cs:__imp_RtlInitEnumerationHashTable
0x1400c74d3  nop     dword ptr [rax+rax+00h]
0x1400c74d8  lea     rdx, [rsp+150h+var_E0]
0x1400c74dd  mov     rcx, rdi
0x1400c74e0  call    FlpInterfaceReleaseReadLock
0x1400c74e5  lea     rdx, [rbp+50h+Enumerator]
0x1400c74e9  mov     rcx, rdi
0x1400c74ec  call    FlpGetNextClientInterface
0x1400c74f1  mov     rbx, rax
0x1400c74f4  test    rax, rax
0x1400c74f7  jz      short loc_1400C756A
0x1400c74f9  mov     rcx, [rbx+90h]
0x1400c7500  mov     edx, 1; Count
0x1400c7505  mov     [rbp+50h+var_C0], rcx
0x1400c7509  mov     rcx, [rbx+38h]; RunRefCacheAware
0x1400c750d  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x1400c7514  nop     dword ptr [rax+rax+00h]
0x1400c7519  test    al, al
0x1400c751b  jz      short loc_1400C754E
0x1400c751d  mov     rax, [rdi+20h]
0x1400c7521  mov     rcx, [rax+0D8h]
0x1400c7528  mov     rax, [rcx+8]
0x1400c752c  lea     rcx, [rbp+50h+var_C0]
0x1400c7530  mov     rax, [rax+30h]
0x1400c7534  call    _guard_dispatch_icall
0x1400c7539  mov     rcx, [rbx+38h]; RunRef
0x1400c753d  mov     edx, 1; Count
0x1400c7542  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x1400c7549  nop     dword ptr [rax+rax+00h]
0x1400c754e  mov     rcx, rbx
0x1400c7551  call    FlpDereferenceClientInterface
0x1400c7556  lea     rdx, [rbp+50h+Enumerator]
0x1400c755a  mov     rcx, rdi
0x1400c755d  call    FlpGetNextClientInterface
0x1400c7562  mov     rbx, rax
0x1400c7565  test    rax, rax
0x1400c7568  jnz     short loc_1400C74F9
0x1400c756a  mov     rcx, [rdi+48h]; RunRef
0x1400c756e  mov     edx, 1; Count
0x1400c7573  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x1400c757a  nop     dword ptr [rax+rax+00h]
0x1400c757f  mov     rcx, [rbp+50h+P]; jumptable 00000001400C75F8 default case, cases 1073807366-1073807383,1073807385-1073807393,1073807396,1073807397
0x1400c7583  mov     r13, [rsp+150h+var_30]
0x1400c758b  mov     r12, [rsp+150h+arg_10]
0x1400c7593  test    rcx, rcx
0x1400c7596  jz      short loc_1400C75A6
0x1400c7598  xor     edx, edx; Tag
0x1400c759a  call    cs:__imp_ExFreePoolWithTag
0x1400c75a1  nop     dword ptr [rax+rax+00h]
0x1400c75a6  mov     rcx, [rbp+50h+var_40]
0x1400c75aa  xor     rcx, rsp; StackCookie
0x1400c75ad  call    __security_check_cookie
0x1400c75b2  add     rsp, 128h
0x1400c75b9  pop     r15
0x1400c75bb  pop     r14
0x1400c75bd  pop     rdi
0x1400c75be  pop     rsi
0x1400c75bf  pop     rbx
0x1400c75c0  pop     rbp
0x1400c75c1  retn
0x1400c75c3  cmp     esi, 40020006h
0x1400c75c9  jg      short loc_1400C764A
0x1400c75cb  jz      loc_1400C784A
0x1400c75d1  add     esi, 0BFFEFFFCh; switch 35 cases
0x1400c75d7  cmp     esi, 22h
0x1400c75da  ja      short def_1400C75F8; jumptable 00000001400C75F8 default case, cases 1073807366-1073807383,1073807385-1073807393,1073807396,1073807397
0x1400c75dc  lea     rdx, cs:140000000h
0x1400c75e3  movsxd  rax, esi
0x1400c75e6  movzx   eax, ds:(byte_1401F1C6C - 140000000h)[rdx+rax]
0x1400c75ee  mov     ecx, ds:(jpt_1400C75F8 - 140000000h)[rdx+rax*4]
0x1400c75f5  add     rcx, rdx
0x1400c75f8  jmp     rcx; switch jump
0x1400c75fe  test    byte ptr cs:WPP_MAIN_CB.Reserved+6, 20h
0x1400c7605  jz      loc_1400C73EF
0x1400c760b  mov     eax, [rsi+4]
0x1400c760e  mov     r9d, [rdi+498h]
0x1400c7615  mov     [rsp+150h+var_E8], eax
0x1400c7619  mov     rax, [rsi+18h]
0x1400c761d  mov     [rsp+150h+var_F0], rax
0x1400c7622  mov     eax, [rdi+4A0h]
0x1400c7628  mov     [rsp+150h+var_F8], rcx
0x1400c762d  mov     [rsp+150h+var_100], eax
0x1400c7631  mov     eax, [rdi+4ECh]
0x1400c7637  mov     [rsp+150h+var_108], eax
0x1400c763b  mov     [rsp+150h+var_130], rdx
0x1400c7640  call    McTemplateK0qxqqqbr4qqxxq_EtwWriteTransfer
0x1400c7645  jmp     loc_1400C73EF
0x1400c764a  sub     esi, 40020007h
0x1400c7650  jz      loc_1400C7A19
0x1400c7656  sub     esi, 79h ; 'y'
0x1400c7659  jz      loc_1400C79E0
0x1400c765f  sub     esi, 0FFD1h
0x1400c7665  jz      loc_1400C79B3
0x1400c766b  sub     esi, 2
0x1400c766e  jz      loc_1400C798C
0x1400c7674  cmp     esi, 2
0x1400c7677  jnz     def_1400C75F8; jumptable 00000001400C75F8 default case, cases 1073807366-1073807383,1073807385-1073807393,1073807396,1073807397
0x1400c767d  mov     rcx, [r15+30h]
0x1400c7681  cmp     dword ptr [rcx+8], 1
0x1400c7685  jnz     def_1400C75F8; jumptable 00000001400C75F8 default case, cases 1073807366-1073807383,1073807385-1073807393,1073807396,1073807397
0x1400c768b  cmp     dword ptr [rcx+10h], 9Ch
0x1400c7692  jb      def_1400C75F8; jumptable 00000001400C75F8 default case, cases 1073807366-1073807383,1073807385-1073807393,1073807396,1073807397
0x1400c7698  mov     r15d, [rcx+0Ch]
0x1400c769c  lea     r8, [rbp+50h+var_80]
0x1400c76a0  add     r15, rcx
0x1400c76a3  mov     rcx, rdi
0x1400c76a6  mov     rdx, r15
0x1400c76a9  call    FlpPreProcessWakePacketIndication
0x1400c76ae  mov     rsi, rax
0x1400c76b1  test    rax, rax
0x1400c76b4  jz      def_1400C75F8; jumptable 00000001400C75F8 default case, cases 1073807366-1073807383,1073807385-1073807393,1073807396,1073807397
0x1400c76ba  mov     rcx, [rdi+48h]; RunRefCacheAware
0x1400c76be  mov     edx, 1; Count
0x1400c76c3  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x1400c76ca  nop     dword ptr [rax+rax+00h]
0x1400c76cf  test    al, al
0x1400c76d1  jnz     loc_1400C78E6
0x1400c76d7  lea     r9, [rbp+50h+var_80]
0x1400c76db  mov     r8, r15
0x1400c76de  mov     rdx, rsi
0x1400c76e1  mov     rcx, rdi
0x1400c76e4  call    FlpPostProcessWakePacketIndication
0x1400c76e9  jmp     loc_1400C740A
0x1400c76ee  cmp     dword ptr [rdi+138h], 12h; jumptable 00000001400C75F8 case 1073807395
0x1400c76f5  jz      def_1400C75F8; jumptable 00000001400C75F8 default case, cases 1073807366-1073807383,1073807385-1073807393,1073807396,1073807397
0x1400c76fb  mov     rax, [r15+30h]
0x1400c76ff  mov     byte ptr [rsp+150h+var_E0], 1
0x1400c7704  mov     edx, [rax+4]
0x1400c7707  mov     [rdi+4B8h], edx
0x1400c770d  mov     rax, [r15+30h]
0x1400c7711  mov     ecx, [rax+8]
0x1400c7714  mov     [rdi+4BCh], ecx
0x1400c771a  test    byte ptr cs:WPP_MAIN_CB.Reserved+2, 4
0x1400c7721  jz      loc_1400C740A
0x1400c7727  mov     eax, [rdi+4A0h]
0x1400c772d  mov     r9d, [rdi+498h]
0x1400c7734  mov     [rsp+150h+var_120], eax
0x1400c7738  mov     [rsp+150h+var_128], rcx
0x1400c773d  mov     dword ptr [rsp+150h+var_130], edx
0x1400c7741  call    McTemplateK0qqxq_EtwWriteTransfer
0x1400c7746  jmp     loc_1400C740A
0x1400c774b  mov     rax, [rdi+20h]
0x1400c774f  lea     r8, MICROSOFT_TCPIP_PROVIDER
0x1400c7756  mov     r9d, [rdi+498h]
0x1400c775d  lea     rdx, TCPIP_STATUS_INDICATION
0x1400c7764  mov     dword ptr [rsp+150h+var_128], esi
0x1400c7768  movzx   ecx, word ptr [rax+5Ch]
0x1400c776c  mov     dword ptr [rsp+150h+var_130], ecx
0x1400c7770  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1400c7777  call    McTemplateK0qqq_EtwWriteTransfer
0x1400c777c  jmp     loc_1400C73CB
0x1400c7781  mov     rax, [rdi+128h]
0x1400c7788  lea     rdx, [rbp+50h+Enumerator]
0x1400c778c  mov     [rbp+50h+var_C0], rax
0x1400c7790  mov     rcx, rdi
0x1400c7793  xor     eax, eax
0x1400c7795  mov     [rbp+50h+var_B7+3], eax
0x1400c7798  mov     [rbp+50h+var_B7], eax
0x1400c779b  mov     [rbp+50h+var_B3], ax
0x1400c779f  mov     [rbp+50h+var_B1], al
0x1400c77a2  lea     rax, [rdi+4D8h]
0x1400c77a9  mov     [rbp+50h+var_B0], rax
0x1400c77ad  movzx   eax, byte ptr [rbp+50h+var_D0]
0x1400c77b1  mov     [rbp+50h+var_B8], al
0x1400c77b4  movzx   eax, word ptr [rbp+50h+var_D0+1]
0x1400c77b8  mov     word ptr [rbp+50h+var_B7], ax
0x1400c77bc  movzx   eax, byte ptr [rbp+50h+var_D0+3]
0x1400c77c0  mov     byte ptr [rbp+50h+var_B7+2], al
0x1400c77c3  call    FlpGetFirstClientInterface
0x1400c77c8  mov     rbx, rax
0x1400c77cb  test    rax, rax
0x1400c77ce  jz      loc_1400C7460
0x1400c77d4  mov     rcx, [rbx+88h]
0x1400c77db  mov     edx, 1; Count
0x1400c77e0  mov     [rbp+50h+var_C0], rcx
0x1400c77e4  mov     rcx, [rbx+38h]; RunRefCacheAware
0x1400c77e8  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x1400c77ef  nop     dword ptr [rax+rax+00h]
0x1400c77f4  test    al, al
0x1400c77f6  jz      short loc_1400C7829
0x1400c77f8  mov     rax, [rdi+20h]
0x1400c77fc  mov     rcx, [rax+0D8h]
0x1400c7803  mov     rax, [rcx+8]
0x1400c7807  lea     rcx, [rbp+50h+var_C0]
0x1400c780b  mov     rax, [rax+18h]
0x1400c780f  call    _guard_dispatch_icall
0x1400c7814  mov     rcx, [rbx+38h]; RunRef
0x1400c7818  mov     edx, 1; Count
0x1400c781d  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x1400c7824  nop     dword ptr [rax+rax+00h]
0x1400c7829  mov     rcx, rbx
0x1400c782c  call    FlpDereferenceClientInterface
0x1400c7831  lea     rdx, [rbp+50h+Enumerator]
0x1400c7835  mov     rcx, rdi
0x1400c7838  call    FlpGetNextClientInterface
0x1400c783d  mov     rbx, rax
0x1400c7840  test    rax, rax
0x1400c7843  jnz     short loc_1400C77D4
0x1400c7845  jmp     loc_1400C7460
0x1400c784a  mov     rbx, [rbp+50h+P]
0x1400c784e  mov     rcx, rbx
0x1400c7851  call    FlpValidateTaskOffloadCapabilityChange
0x1400c7856  and     al, 1
0x1400c7858  movzx   ecx, al
  ... truncated ...
```
