# FlStatus

- ea: `0x1400c7550`
- end: `0x1400c7c5e`
- name: `FlStatus`
- size: `1806`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `0`
- callee_count: `20`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x140053d20`
- `0x140053d40`
- `0x1400772e0`
- `0x1400c74e4`
- `0x1400c7550`
- `0x1400c7c64`
- `0x1400c7ce4`
- `0x1400c7da4`
- `0x1400c8414`
- `0x1400c8488`
- `0x1400c85bc`
- `0x1400c85d4`
- `0x1400c89c4`
- `0x1400c8a80`
- `0x1400c9094`
- `0x140124960`
- `0x1401bf390`
- `0x1401bf5c0`
- `0x1401bf640`
- `0x1401bf940`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1400c7636`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1400c772d`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1400c78e3`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1400c7a08`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1400c7636`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1400c772d`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1400c78e3`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1400c7a08`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x1400c76ec`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x1400c76ec`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1400c7762`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1400c7793`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1400c7a3d`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1400c7b50`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1400c7762`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1400c7793`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1400c7a3d`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1400c7b50`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c77ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c77ba`

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
0x1400c7550  push    rbp
0x1400c7552  push    rbx
0x1400c7553  push    rsi
0x1400c7554  push    rdi
0x1400c7555  push    r14
0x1400c7557  push    r15
0x1400c7559  lea     rbp, [rsp-28h]
0x1400c755e  sub     rsp, 128h
0x1400c7565  mov     rax, cs:__security_cookie
0x1400c756c  xor     rax, rsp
0x1400c756f  mov     [rbp+50h+var_40], rax
0x1400c7573  mov     r15, rdx
0x1400c7576  mov     rdi, rcx
0x1400c7579  xor     edx, edx; Val
0x1400c757b  lea     rcx, [rbp+50h+var_80]; void *
0x1400c757f  mov     r8d, 40h ; '@'; Size
0x1400c7585  call    memset
0x1400c758a  mov     esi, [r15+14h]
0x1400c758e  lea     rdx, [rbp+50h+P]
0x1400c7592  xor     r14d, r14d
0x1400c7595  xorps   xmm0, xmm0
0x1400c7598  xor     eax, eax
0x1400c759a  mov     [rsp+150h+var_E0], r14d
0x1400c759f  mov     ebx, r14d
0x1400c75a2  mov     [rbp+50h+P], r14
0x1400c75a6  mov     rcx, r15
0x1400c75a9  mov     [rbp+50h+var_D0], ebx
0x1400c75ac  movups  xmmword ptr [rbp+50h+Enumerator], xmm0
0x1400c75b0  mov     qword ptr [rbp+50h+Enumerator.BucketIndex], rax
0x1400c75b4  movups  xmmword ptr [rbp+50h+Enumerator+10h], xmm0
0x1400c75b8  call    FlpValidateAndUpdateStatusIndication
0x1400c75bd  test    al, al
0x1400c75bf  jz      loc_1400C77C6
0x1400c75c5  test    byte ptr cs:WPP_MAIN_CB+149h, 1
0x1400c75cc  mov     [rsp+150h+arg_10], r12
0x1400c75d4  mov     r12d, 9
0x1400c75da  mov     [rsp+150h+var_30], r13
0x1400c75e2  mov     r13d, r14d
0x1400c75e5  jnz     loc_1400C796B
0x1400c75eb  cmp     esi, 40010017h
0x1400c75f1  jnz     loc_1400C77E3
0x1400c75f7  mov     rsi, [r15+30h]
0x1400c75fb  mov     rcx, [rdi+4C8h]
0x1400c7602  mov     rdx, [rsi+10h]
0x1400c7606  cmp     rdx, rcx
0x1400c7609  jnz     loc_1400C781E
0x1400c760f  mov     rax, [rsi+10h]
0x1400c7613  mov     [rdi+4C8h], rax
0x1400c761a  mov     rax, [rsi+18h]
0x1400c761e  mov     [rdi+4D0h], rax
0x1400c7625  mov     byte ptr [rsp+150h+var_E0], 4
0x1400c762a  mov     rsi, rbx
0x1400c762d  mov     rcx, [rdi+48h]; RunRefCacheAware
0x1400c7631  mov     edx, 1; Count
0x1400c7636  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x1400c763d  nop     dword ptr [rax+rax+00h]
0x1400c7642  test    al, al
0x1400c7644  jz      def_1400C7818; jumptable 00000001400C7818 default case, cases 1073807366-1073807383,1073807385-1073807393,1073807396,1073807397
0x1400c764a  cmp     r12d, 9
0x1400c764e  jz      short loc_1400C7678
0x1400c7650  mov     rax, [rdi+20h]
0x1400c7654  mov     r9d, r13d
0x1400c7657  mov     r8, rsi
0x1400c765a  mov     edx, r12d
0x1400c765d  mov     rcx, [rax+0D8h]
0x1400c7664  mov     rax, [rcx+8]
0x1400c7668  mov     rcx, [rdi+128h]
0x1400c766f  mov     rax, [rax+70h]
0x1400c7673  call    _guard_dispatch_icall
0x1400c7678  test    ebx, ebx
0x1400c767a  jnz     loc_1400C79A1
0x1400c7680  cmp     [rsp+150h+var_E0], r14d
0x1400c7685  jz      loc_1400C778A
0x1400c768b  mov     rax, [rdi+130h]
0x1400c7692  lea     rdx, [rsp+150h+var_E0]
0x1400c7697  mov     [rbp+50h+var_C0], rax
0x1400c769b  mov     rcx, rdi
0x1400c769e  xor     eax, eax
0x1400c76a0  mov     [rbp+50h+var_B7+3], eax
0x1400c76a3  mov     [rbp-67h], eax
0x1400c76a6  mov     [rbp+50h+var_B3], ax
0x1400c76aa  mov     [rbp+50h+var_B1], al
0x1400c76ad  lea     rax, [rdi+4B8h]
0x1400c76b4  mov     [rbp+50h+var_B0], rax
0x1400c76b8  movzx   eax, byte ptr [rsp+150h+var_E0]
0x1400c76bd  mov     [rbp+50h+var_B8], al
0x1400c76c0  movzx   eax, word ptr [rsp+150h+var_E0+1]
0x1400c76c5  mov     word ptr [rbp+50h+var_B7], ax
0x1400c76c9  movzx   eax, byte ptr [rsp+150h+var_E0+3]
0x1400c76ce  mov     byte ptr [rbp+50h+var_B7+2], al
0x1400c76d1  xor     eax, eax
0x1400c76d3  mov     word ptr [rsp+150h+var_E0], ax
0x1400c76d8  mov     byte ptr [rsp+150h+var_E0+2], al
0x1400c76dc  call    FlpInterfaceAcquireWriteLock
0x1400c76e1  lea     rcx, [rdi+0D0h]; HashTable
0x1400c76e8  lea     rdx, [rbp+50h+Enumerator]; Enumerator
0x1400c76ec  call    cs:__imp_RtlInitEnumerationHashTable
0x1400c76f3  nop     dword ptr [rax+rax+00h]
0x1400c76f8  lea     rdx, [rsp+150h+var_E0]
0x1400c76fd  mov     rcx, rdi
0x1400c7700  call    FlpInterfaceReleaseReadLock
0x1400c7705  lea     rdx, [rbp+50h+Enumerator]
0x1400c7709  mov     rcx, rdi
0x1400c770c  call    FlpGetNextClientInterface
0x1400c7711  mov     rbx, rax
0x1400c7714  test    rax, rax
0x1400c7717  jz      short loc_1400C778A
0x1400c7719  mov     rcx, [rbx+90h]
0x1400c7720  mov     edx, 1; Count
0x1400c7725  mov     [rbp+50h+var_C0], rcx
0x1400c7729  mov     rcx, [rbx+38h]; RunRefCacheAware
0x1400c772d  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x1400c7734  nop     dword ptr [rax+rax+00h]
0x1400c7739  test    al, al
0x1400c773b  jz      short loc_1400C776E
0x1400c773d  mov     rax, [rdi+20h]
0x1400c7741  mov     rcx, [rax+0D8h]
0x1400c7748  mov     rax, [rcx+8]
0x1400c774c  lea     rcx, [rbp+50h+var_C0]
0x1400c7750  mov     rax, [rax+30h]
0x1400c7754  call    _guard_dispatch_icall
0x1400c7759  mov     rcx, [rbx+38h]; RunRef
0x1400c775d  mov     edx, 1; Count
0x1400c7762  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x1400c7769  nop     dword ptr [rax+rax+00h]
0x1400c776e  mov     rcx, rbx
0x1400c7771  call    FlpDereferenceClientInterface
0x1400c7776  lea     rdx, [rbp+50h+Enumerator]
0x1400c777a  mov     rcx, rdi
0x1400c777d  call    FlpGetNextClientInterface
0x1400c7782  mov     rbx, rax
0x1400c7785  test    rax, rax
0x1400c7788  jnz     short loc_1400C7719
0x1400c778a  mov     rcx, [rdi+48h]; RunRef
0x1400c778e  mov     edx, 1; Count
0x1400c7793  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x1400c779a  nop     dword ptr [rax+rax+00h]
0x1400c779f  mov     rcx, [rbp+50h+P]; jumptable 00000001400C7818 default case, cases 1073807366-1073807383,1073807385-1073807393,1073807396,1073807397
0x1400c77a3  mov     r13, [rsp+150h+var_30]
0x1400c77ab  mov     r12, [rsp+150h+arg_10]
0x1400c77b3  test    rcx, rcx
0x1400c77b6  jz      short loc_1400C77C6
0x1400c77b8  xor     edx, edx; Tag
0x1400c77ba  call    cs:__imp_ExFreePoolWithTag
0x1400c77c1  nop     dword ptr [rax+rax+00h]
0x1400c77c6  mov     rcx, [rbp+50h+var_40]
0x1400c77ca  xor     rcx, rsp; StackCookie
0x1400c77cd  call    __security_check_cookie
0x1400c77d2  add     rsp, 128h
0x1400c77d9  pop     r15
0x1400c77db  pop     r14
0x1400c77dd  pop     rdi
0x1400c77de  pop     rsi
0x1400c77df  pop     rbx
0x1400c77e0  pop     rbp
0x1400c77e1  retn
0x1400c77e3  cmp     esi, 40020006h
0x1400c77e9  jg      short loc_1400C786A
0x1400c77eb  jz      loc_1400C7A6A
0x1400c77f1  add     esi, 0BFFEFFFCh; switch 35 cases
0x1400c77f7  cmp     esi, 22h
0x1400c77fa  ja      short def_1400C7818; jumptable 00000001400C7818 default case, cases 1073807366-1073807383,1073807385-1073807393,1073807396,1073807397
0x1400c77fc  lea     rdx, cs:140000000h
0x1400c7803  movsxd  rax, esi
0x1400c7806  movzx   eax, ds:(byte_1401F1C7C - 140000000h)[rdx+rax]
0x1400c780e  mov     ecx, ds:(jpt_1400C7818 - 140000000h)[rdx+rax*4]
0x1400c7815  add     rcx, rdx
0x1400c7818  jmp     rcx; switch jump
0x1400c781e  test    byte ptr cs:WPP_MAIN_CB.Reserved+6, 20h
0x1400c7825  jz      loc_1400C760F
0x1400c782b  mov     eax, [rsi+4]
0x1400c782e  mov     r9d, [rdi+498h]
0x1400c7835  mov     [rsp+150h+var_E8], eax
0x1400c7839  mov     rax, [rsi+18h]
0x1400c783d  mov     [rsp+150h+var_F0], rax
0x1400c7842  mov     eax, [rdi+4A0h]
0x1400c7848  mov     [rsp+150h+var_F8], rcx
0x1400c784d  mov     [rsp+150h+var_100], eax
0x1400c7851  mov     eax, [rdi+4ECh]
0x1400c7857  mov     [rsp+150h+var_108], eax
0x1400c785b  mov     [rsp+150h+var_130], rdx
0x1400c7860  call    McTemplateK0qxqqqbr4qqxxq_EtwWriteTransfer
0x1400c7865  jmp     loc_1400C760F
0x1400c786a  sub     esi, 40020007h
0x1400c7870  jz      loc_1400C7C39
0x1400c7876  sub     esi, 79h ; 'y'
0x1400c7879  jz      loc_1400C7C00
0x1400c787f  sub     esi, 0FFD1h
0x1400c7885  jz      loc_1400C7BD3
0x1400c788b  sub     esi, 2
0x1400c788e  jz      loc_1400C7BAC
0x1400c7894  cmp     esi, 2
0x1400c7897  jnz     def_1400C7818; jumptable 00000001400C7818 default case, cases 1073807366-1073807383,1073807385-1073807393,1073807396,1073807397
0x1400c789d  mov     rcx, [r15+30h]
0x1400c78a1  cmp     dword ptr [rcx+8], 1
0x1400c78a5  jnz     def_1400C7818; jumptable 00000001400C7818 default case, cases 1073807366-1073807383,1073807385-1073807393,1073807396,1073807397
0x1400c78ab  cmp     dword ptr [rcx+10h], 9Ch
0x1400c78b2  jb      def_1400C7818; jumptable 00000001400C7818 default case, cases 1073807366-1073807383,1073807385-1073807393,1073807396,1073807397
0x1400c78b8  mov     r15d, [rcx+0Ch]
0x1400c78bc  lea     r8, [rbp+50h+var_80]
0x1400c78c0  add     r15, rcx
0x1400c78c3  mov     rcx, rdi
0x1400c78c6  mov     rdx, r15
0x1400c78c9  call    FlpPreProcessWakePacketIndication
0x1400c78ce  mov     rsi, rax
0x1400c78d1  test    rax, rax
0x1400c78d4  jz      def_1400C7818; jumptable 00000001400C7818 default case, cases 1073807366-1073807383,1073807385-1073807393,1073807396,1073807397
0x1400c78da  mov     rcx, [rdi+48h]; RunRefCacheAware
0x1400c78de  mov     edx, 1; Count
0x1400c78e3  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x1400c78ea  nop     dword ptr [rax+rax+00h]
0x1400c78ef  test    al, al
0x1400c78f1  jnz     loc_1400C7B06
0x1400c78f7  lea     r9, [rbp+50h+var_80]
0x1400c78fb  mov     r8, r15
0x1400c78fe  mov     rdx, rsi
0x1400c7901  mov     rcx, rdi
0x1400c7904  call    FlpPostProcessWakePacketIndication
0x1400c7909  jmp     loc_1400C762A
0x1400c790e  cmp     dword ptr [rdi+138h], 12h; jumptable 00000001400C7818 case 1073807395
0x1400c7915  jz      def_1400C7818; jumptable 00000001400C7818 default case, cases 1073807366-1073807383,1073807385-1073807393,1073807396,1073807397
0x1400c791b  mov     rax, [r15+30h]
0x1400c791f  mov     byte ptr [rsp+150h+var_E0], 1
0x1400c7924  mov     edx, [rax+4]
0x1400c7927  mov     [rdi+4B8h], edx
0x1400c792d  mov     rax, [r15+30h]
0x1400c7931  mov     ecx, [rax+8]
0x1400c7934  mov     [rdi+4BCh], ecx
0x1400c793a  test    byte ptr cs:WPP_MAIN_CB.Reserved+2, 4
0x1400c7941  jz      loc_1400C762A
0x1400c7947  mov     eax, [rdi+4A0h]
0x1400c794d  mov     r9d, [rdi+498h]
0x1400c7954  mov     [rsp+150h+var_120], eax
0x1400c7958  mov     [rsp+150h+var_128], rcx
0x1400c795d  mov     dword ptr [rsp+150h+var_130], edx
0x1400c7961  call    McTemplateK0qqxq_EtwWriteTransfer
0x1400c7966  jmp     loc_1400C762A
0x1400c796b  mov     rax, [rdi+20h]
0x1400c796f  lea     r8, MICROSOFT_TCPIP_PROVIDER
0x1400c7976  mov     r9d, [rdi+498h]
0x1400c797d  lea     rdx, TCPIP_STATUS_INDICATION
0x1400c7984  mov     dword ptr [rsp+150h+var_128], esi
0x1400c7988  movzx   ecx, word ptr [rax+5Ch]
0x1400c798c  mov     dword ptr [rsp+150h+var_130], ecx
0x1400c7990  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1400c7997  call    McTemplateK0qqq_EtwWriteTransfer
0x1400c799c  jmp     loc_1400C75EB
0x1400c79a1  mov     rax, [rdi+128h]
0x1400c79a8  lea     rdx, [rbp+50h+Enumerator]
0x1400c79ac  mov     [rbp+50h+var_C0], rax
0x1400c79b0  mov     rcx, rdi
0x1400c79b3  xor     eax, eax
0x1400c79b5  mov     [rbp+50h+var_B7+3], eax
0x1400c79b8  mov     [rbp+50h+var_B7], eax
0x1400c79bb  mov     [rbp+50h+var_B3], ax
0x1400c79bf  mov     [rbp+50h+var_B1], al
0x1400c79c2  lea     rax, [rdi+4D8h]
0x1400c79c9  mov     [rbp+50h+var_B0], rax
0x1400c79cd  movzx   eax, byte ptr [rbp+50h+var_D0]
0x1400c79d1  mov     [rbp+50h+var_B8], al
0x1400c79d4  movzx   eax, word ptr [rbp+50h+var_D0+1]
0x1400c79d8  mov     word ptr [rbp+50h+var_B7], ax
0x1400c79dc  movzx   eax, byte ptr [rbp+50h+var_D0+3]
0x1400c79e0  mov     byte ptr [rbp+50h+var_B7+2], al
0x1400c79e3  call    FlpGetFirstClientInterface
0x1400c79e8  mov     rbx, rax
0x1400c79eb  test    rax, rax
0x1400c79ee  jz      loc_1400C7680
0x1400c79f4  mov     rcx, [rbx+88h]
0x1400c79fb  mov     edx, 1; Count
0x1400c7a00  mov     [rbp+50h+var_C0], rcx
0x1400c7a04  mov     rcx, [rbx+38h]; RunRefCacheAware
0x1400c7a08  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x1400c7a0f  nop     dword ptr [rax+rax+00h]
0x1400c7a14  test    al, al
0x1400c7a16  jz      short loc_1400C7A49
0x1400c7a18  mov     rax, [rdi+20h]
0x1400c7a1c  mov     rcx, [rax+0D8h]
0x1400c7a23  mov     rax, [rcx+8]
0x1400c7a27  lea     rcx, [rbp+50h+var_C0]
0x1400c7a2b  mov     rax, [rax+18h]
0x1400c7a2f  call    _guard_dispatch_icall
0x1400c7a34  mov     rcx, [rbx+38h]; RunRef
0x1400c7a38  mov     edx, 1; Count
0x1400c7a3d  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x1400c7a44  nop     dword ptr [rax+rax+00h]
0x1400c7a49  mov     rcx, rbx
0x1400c7a4c  call    FlpDereferenceClientInterface
0x1400c7a51  lea     rdx, [rbp+50h+Enumerator]
0x1400c7a55  mov     rcx, rdi
0x1400c7a58  call    FlpGetNextClientInterface
0x1400c7a5d  mov     rbx, rax
0x1400c7a60  test    rax, rax
0x1400c7a63  jnz     short loc_1400C79F4
0x1400c7a65  jmp     loc_1400C7680
0x1400c7a6a  mov     rbx, [rbp+50h+P]
0x1400c7a6e  mov     rcx, rbx
0x1400c7a71  call    FlpValidateTaskOffloadCapabilityChange
0x1400c7a76  and     al, 1
0x1400c7a78  movzx   ecx, al
  ... truncated ...
```
