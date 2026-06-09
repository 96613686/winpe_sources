# UbpmRunNextSerializedAction

- ea: `0x18000ae40`
- end: `0x18000b2ed`
- name: `UbpmRunNextSerializedAction`
- size: `1197`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, int, PSID pSid, __int64, int, size_t Size, void *Src, unsigned __int8, unsigned __int16 **, int, unsigned __int8, unsigned __int16 **)`
- caller_count: `6`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800057b0`
- `0x18000c650`
- `0x180021060`
- `0x180023e04`
- `0x180023f68`
- `0x180029a0c`

## callees

- `0x180003d30`
- `0x180004a30`
- `0x18000a6e0`
- `0x18000ae40`
- `0x18000f9a0`
- `0x180019d90`
- `0x180024df0`
- `0x180032e38`
- `0x18003d7d2`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000b05e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000b05e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000b0da`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000b0da`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000b1d8`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000b1d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b06b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b0e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b238`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b27e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b06b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b0e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b238`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b27e`

## pseudocode

```c
DWORD __fastcall UbpmRunNextSerializedAction(
        __int128 *a1,
        unsigned __int16 a2,
        UUID *a3,
        int a4,
        __int64 a5,
        int a6,
        PSID pSid,
        __int64 a8,
        int a9,
        size_t Size,
        void *Src,
        char a12,
        unsigned __int16 **a13,
        int a14,
        char a15,
        unsigned __int16 **a16)
{
  unsigned int v18; // ebp
  UUID *v19; // r15
  DWORD LengthSid; // edi
  char v22; // r14
  char *v23; // rax
  char *v24; // rsi
  unsigned int v25; // eax
  DWORD v26; // ebx
  DWORD v27; // eax
  UUID v28; // xmm1
  DWORD result; // eax
  _QWORD *v30; // rcx
  DWORD LastError; // eax
  void *v32; // rax
  __int128 v33; // xmm1
  _QWORD *v34; // rax
  __int64 v35; // rdx
  _OWORD *v36; // rbx
  char pSida; // [rsp+B0h] [rbp+38h]

  v18 = a2;
  v19 = a3;
  if ( pSid )
    LengthSid = GetLengthSid(pSid);
  else
    LengthSid = 0;
  v22 = 0;
  pSida = 0;
  v23 = (char *)UbpmAlloc(LengthSid + 136);
  v24 = v23;
  if ( !v23 )
  {
    result = GetLastError();
    v26 = result;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      result = WPP_SF_d(
                 *((_QWORD *)WPP_GLOBAL_Control + 2),
                 32,
                 WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
                 result);
    goto LABEL_20;
  }
  if ( pSid )
  {
    *((_QWORD *)v23 + 8) = v23 + 136;
    if ( !CopySid(LengthSid, v23 + 136, pSid) )
    {
      LastError = GetLastError();
      v26 = LastError;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids, LastError);
      goto LABEL_19;
    }
  }
  v25 = UbpmUtilsCloneStringArray(a12, (const unsigned __int16 **)a13, (const unsigned __int16 ***)v24 + 14);
  v26 = v25;
  if ( v25 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids, v25);
    v22 = 0;
    goto LABEL_19;
  }
  v27 = UbpmUtilsCloneStringArray(a15, (const unsigned __int16 **)a16, (const unsigned __int16 ***)v24 + 16);
  v26 = v27;
  if ( v27 )
  {
    v30 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_17;
    v35 = 35;
    goto LABEL_41;
  }
  *((_DWORD *)v24 + 20) = a9;
  if ( Src )
  {
    v32 = UbpmAlloc((unsigned int)Size);
    *((_QWORD *)v24 + 11) = v32;
    if ( !v32 )
    {
      v27 = GetLastError();
      v26 = v27;
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_17;
      v35 = 36;
      goto LABEL_41;
    }
    memcpy_0(v32, Src, (unsigned int)Size);
    *((_DWORD *)v24 + 21) = Size;
  }
  if ( (_WORD)v18 == 1 )
    goto LABEL_9;
  v36 = UbpmAlloc(0x50u);
  if ( !v36 )
  {
    v27 = GetLastError();
    v26 = v27;
    v30 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_17;
    v35 = 37;
LABEL_41:
    WPP_SF_d(v30[2], v35, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids, v27);
LABEL_17:
    v22 = 0;
LABEL_18:
    v19 = a3;
LABEL_19:
    UBPM_MIDL_user_free(*((_QWORD *)v24 + 14));
    UBPM_MIDL_user_free(*((_QWORD *)v24 + 16));
    UBPM_MIDL_user_free(*((_QWORD *)v24 + 11));
    result = UBPM_MIDL_user_free(v24);
LABEL_20:
    if ( v26 )
    {
      if ( v22 == 1 )
        return UbpmpRemoveQueuedSerialActions(v19, 0, 0, v18);
    }
    return result;
  }
  v36[1] = *a3;
  v33 = *a1;
  *((_QWORD *)v36 + 6) = a8;
  *((_WORD *)v36 + 28) = v18;
  v36[2] = v33;
  *((_QWORD *)v36 + 1) = v36;
  *(_QWORD *)v36 = v36;
  UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_SRWLOCK *)&g_QueuedSerialActionsLock);
  v34 = off_18004C0D8[0];
  if ( *(_UNKNOWN ***)off_18004C0D8[0] != &g_leQueuedSerialActionsListHead )
    __fastfail(3u);
  *(_QWORD *)v36 = &g_leQueuedSerialActionsListHead;
  *((_QWORD *)v36 + 1) = v34;
  *v34 = v36;
  off_18004C0D8[0] = (_UNKNOWN **)v36;
  dword_18004CEA0 = 0;
  pSida = 1;
  RtlReleaseSRWLockExclusive(&g_QueuedSerialActionsLock);
LABEL_9:
  *(_DWORD *)v24 = 1954046803;
  *(_OWORD *)(v24 + 24) = *a1;
  v28 = *a3;
  v24[96] &= ~1u;
  *((_QWORD *)v24 + 6) = a5;
  v24[104] = a12;
  v22 = pSida;
  v24[96] |= pSida;
  *((_DWORD *)v24 + 14) = a6;
  *((_DWORD *)v24 + 25) = a14;
  *(UUID *)(v24 + 4) = v28;
  *((_WORD *)v24 + 10) = v18;
  *((_DWORD *)v24 + 10) = a4;
  *((_QWORD *)v24 + 9) = a8;
  v24[120] = a15;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids, v18);
  result = UbpmUtilsSubmitThreadPoolWork(
             (void (*)(void *, unsigned __int8, void *))UbpmpRunSerializedActionCallback,
             v24,
             1,
             0,
             0);
  v26 = result;
  if ( result )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids, result);
    goto LABEL_18;
  }
  return result;
}

```

## disassembly

```asm
0x18000ae40  mov     [rsp+Uuid1], r8
0x18000ae45  push    rbx
0x18000ae46  push    rbp
0x18000ae47  push    rsi
0x18000ae48  push    rdi
0x18000ae49  push    r12
0x18000ae4b  push    r13
0x18000ae4d  push    r14
0x18000ae4f  push    r15
0x18000ae51  sub     rsp, 38h
0x18000ae55  mov     rbx, [rsp+78h+pSid]
0x18000ae5d  mov     r13d, r9d
0x18000ae60  movzx   ebp, dx
0x18000ae63  mov     r15, r8
0x18000ae66  mov     r12, rcx
0x18000ae69  test    rbx, rbx
0x18000ae6c  jnz     loc_18000B05B
0x18000ae72  xor     edi, edi
0x18000ae74  xor     r14b, r14b
0x18000ae77  lea     ecx, [rdi+88h]; Size
0x18000ae7d  mov     byte ptr [rsp+78h+pSid], r14b
0x18000ae85  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x18000ae8a  mov     rsi, rax
0x18000ae8d  test    rax, rax
0x18000ae90  jz      loc_18000B06B
0x18000ae96  test    rbx, rbx
0x18000ae99  jnz     loc_18000B0CA
0x18000ae9f  mov     r14b, [rsp+78h+arg_58]
0x18000aea7  lea     r8, [rsi+70h]; unsigned __int16 ***
0x18000aeab  mov     rdx, [rsp+78h+arg_60]; unsigned __int16 **
0x18000aeb3  mov     cl, r14b; unsigned __int8
0x18000aeb6  call    ?UbpmUtilsCloneStringArray@@YAKEPEAPEBGPEAPEAPEBG@Z; UbpmUtilsCloneStringArray(uchar,ushort const * *,ushort const * * *)
0x18000aebb  mov     ebx, eax
0x18000aebd  test    eax, eax
0x18000aebf  jnz     loc_18000B0A6
0x18000aec5  mov     r15b, [rsp+78h+arg_70]
0x18000aecd  lea     r8, [rsi+80h]; unsigned __int16 ***
0x18000aed4  mov     rdx, [rsp+78h+arg_78]; unsigned __int16 **
0x18000aedc  mov     cl, r15b; unsigned __int8
0x18000aedf  call    ?UbpmUtilsCloneStringArray@@YAKEPEAPEBGPEAPEAPEBG@Z; UbpmUtilsCloneStringArray(uchar,ushort const * *,ushort const * * *)
0x18000aee4  mov     ebx, eax
0x18000aee6  test    eax, eax
0x18000aee8  jnz     loc_18000AFF5
0x18000aeee  mov     rdi, [rsp+78h+Src]
0x18000aef6  mov     eax, [rsp+78h+arg_40]
0x18000aefd  mov     [rsi+50h], eax
0x18000af00  test    rdi, rdi
0x18000af03  jnz     loc_18000B12E
0x18000af09  mov     rdi, [rsp+78h+arg_38]
0x18000af11  mov     eax, 1
0x18000af16  cmp     bp, ax
0x18000af19  jnz     loc_18000B268
0x18000af1f  mov     rax, [rsp+78h+Uuid1]
0x18000af27  mov     dword ptr [rsi], 74786353h
0x18000af2d  movups  xmm0, xmmword ptr [r12]
0x18000af32  movdqu  xmmword ptr [rsi+18h], xmm0
0x18000af37  movups  xmm1, xmmword ptr [rax]
0x18000af3a  mov     rax, [rsp+78h+arg_20]
0x18000af42  and     byte ptr [rsi+60h], 0FEh
0x18000af46  mov     [rsi+30h], rax
0x18000af4a  mov     eax, [rsp+78h+arg_28]
0x18000af51  mov     [rsi+68h], r14b
0x18000af55  mov     r14b, byte ptr [rsp+78h+pSid]
0x18000af5d  or      [rsi+60h], r14b
0x18000af61  mov     [rsi+38h], eax
0x18000af64  mov     eax, [rsp+78h+arg_68]
0x18000af6b  mov     [rsi+64h], eax
0x18000af6e  movdqu  xmmword ptr [rsi+4], xmm1
0x18000af73  mov     [rsi+14h], bp
0x18000af77  mov     [rsi+28h], r13d
0x18000af7b  mov     [rsi+48h], rdi
0x18000af7f  mov     [rsi+78h], r15b
0x18000af83  mov     rcx, cs:WPP_GLOBAL_Control
0x18000af8a  lea     rdi, WPP_GLOBAL_Control
0x18000af91  cmp     rcx, rdi
0x18000af94  jz      short loc_18000AFA0
0x18000af96  test    byte ptr [rcx+1Ch], 20h
0x18000af9a  jnz     loc_18000B2AC
0x18000afa0  xor     r9d, r9d; struct _TP_CALLBACK_ENVIRON_V3 *
0x18000afa3  mov     [rsp+78h+var_58], 0; struct _UBPM_SRWLOCK *
0x18000afac  mov     rdx, rsi; void *
0x18000afaf  lea     rcx, ?UbpmpRunSerializedActionCallback@@YAXPEAXE0@Z; void (*)(void *, unsigned __int8, void *)
0x18000afb6  lea     r8d, [r9+1]; int
0x18000afba  call    ?UbpmUtilsSubmitThreadPoolWork@@YAKP6AXPEAXE0@Z0HPEAU_TP_CALLBACK_ENVIRON_V3@@PEAU_UBPM_SRWLOCK@@@Z; UbpmUtilsSubmitThreadPoolWork(void (*)(void *,uchar,void *),void *,int,_TP_CALLBACK_ENVIRON_V3 *,_UBPM_SRWLOCK *)
0x18000afbf  mov     ebx, eax
0x18000afc1  test    eax, eax
0x18000afc3  jz      loc_18000B04A
0x18000afc9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000afd0  cmp     rcx, rdi
0x18000afd3  jz      short loc_18000B014
0x18000afd5  test    byte ptr [rcx+1Ch], 1
0x18000afd9  jz      short loc_18000B014
0x18000afdb  mov     rcx, [rcx+10h]
0x18000afdf  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x18000afe6  mov     edx, 27h ; '''
0x18000afeb  mov     r9d, eax
0x18000afee  call    WPP_SF_d
0x18000aff3  jmp     short loc_18000B014
0x18000aff5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000affc  lea     rdi, WPP_GLOBAL_Control
0x18000b003  cmp     rcx, rdi
0x18000b006  jnz     loc_18000B20A
0x18000b00c  mov     r14b, byte ptr [rsp+78h+pSid]
0x18000b014  mov     r15, [rsp+78h+Uuid1]
0x18000b01c  mov     rcx, [rsi+70h]
0x18000b020  call    UBPM_MIDL_user_free
0x18000b025  mov     rcx, [rsi+80h]
0x18000b02c  call    UBPM_MIDL_user_free
0x18000b031  mov     rcx, [rsi+58h]
0x18000b035  call    UBPM_MIDL_user_free
0x18000b03a  mov     rcx, rsi
0x18000b03d  call    UBPM_MIDL_user_free
0x18000b042  test    ebx, ebx
0x18000b044  jnz     loc_18000B2C9
0x18000b04a  add     rsp, 38h
0x18000b04e  pop     r15
0x18000b050  pop     r14
0x18000b052  pop     r13
0x18000b054  pop     r12
0x18000b056  pop     rdi
0x18000b057  pop     rsi
0x18000b058  pop     rbp
0x18000b059  pop     rbx
0x18000b05a  retn
0x18000b05b  mov     rcx, rbx; pSid
0x18000b05e  call    cs:__imp_GetLengthSid
0x18000b064  mov     edi, eax
0x18000b066  jmp     loc_18000AE74
0x18000b06b  call    cs:__imp_GetLastError
0x18000b071  mov     ebx, eax
0x18000b073  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b07a  lea     rdi, WPP_GLOBAL_Control
0x18000b081  cmp     rcx, rdi
0x18000b084  jz      short loc_18000B042
0x18000b086  test    byte ptr [rcx+1Ch], 1
0x18000b08a  jz      short loc_18000B042
0x18000b08c  mov     rcx, [rcx+10h]
0x18000b090  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x18000b097  mov     edx, 20h ; ' '
0x18000b09c  mov     r9d, eax
0x18000b09f  call    WPP_SF_d
0x18000b0a4  jmp     short loc_18000B042
0x18000b0a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b0ad  lea     rdi, WPP_GLOBAL_Control
0x18000b0b4  cmp     rcx, rdi
0x18000b0b7  jnz     loc_18000B1E3
0x18000b0bd  mov     r14b, byte ptr [rsp+78h+pSid]
0x18000b0c5  jmp     loc_18000B01C
0x18000b0ca  lea     rdx, [rax+88h]; pDestinationSid
0x18000b0d1  mov     r8, rbx; pSourceSid
0x18000b0d4  mov     ecx, edi; nDestinationSidLength
0x18000b0d6  mov     [rax+40h], rdx
0x18000b0da  call    cs:__imp_CopySid
0x18000b0e0  test    eax, eax
0x18000b0e2  jnz     loc_18000AE9F
0x18000b0e8  call    cs:__imp_GetLastError
0x18000b0ee  mov     ebx, eax
0x18000b0f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b0f7  lea     rdi, WPP_GLOBAL_Control
0x18000b0fe  cmp     rcx, rdi
0x18000b101  jz      loc_18000B01C
0x18000b107  test    byte ptr [rcx+1Ch], 1
0x18000b10b  jz      loc_18000B01C
0x18000b111  mov     rcx, [rcx+10h]
0x18000b115  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x18000b11c  mov     edx, 21h ; '!'
0x18000b121  mov     r9d, eax
0x18000b124  call    WPP_SF_d
0x18000b129  jmp     loc_18000B01C
0x18000b12e  mov     ebx, dword ptr [rsp+78h+Size]
0x18000b135  mov     ecx, ebx; Size
0x18000b137  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x18000b13c  mov     [rsi+58h], rax
0x18000b140  test    rax, rax
0x18000b143  jz      loc_18000B238
0x18000b149  mov     r8d, ebx; Size
0x18000b14c  mov     rdx, rdi; Src
0x18000b14f  mov     rcx, rax; void *
0x18000b152  call    memcpy_0
0x18000b157  mov     [rsi+54h], ebx
0x18000b15a  jmp     loc_18000AF09
0x18000b15f  mov     rax, [rsp+78h+Uuid1]
0x18000b167  lea     rcx, g_QueuedSerialActionsLock; struct _UBPM_SRWLOCK *
0x18000b16e  movups  xmm0, xmmword ptr [rax]
0x18000b171  movdqu  xmmword ptr [rbx+10h], xmm0
0x18000b176  movups  xmm1, xmmword ptr [r12]
0x18000b17b  mov     [rbx+30h], rdi
0x18000b17f  mov     [rbx+38h], bp
0x18000b183  movdqu  xmmword ptr [rbx+20h], xmm1
0x18000b188  mov     [rbx+8], rbx
0x18000b18c  mov     [rbx], rbx
0x18000b18f  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x18000b194  mov     rax, cs:off_18004C0D8
0x18000b19b  lea     rcx, g_leQueuedSerialActionsListHead
0x18000b1a2  cmp     [rax], rcx
0x18000b1a5  jz      short loc_18000B1AE
0x18000b1a7  mov     ecx, 3
0x18000b1ac  int     29h; Win8: RtlFailFast(ecx)
0x18000b1ae  mov     [rbx], rcx
0x18000b1b1  lea     rcx, g_QueuedSerialActionsLock
0x18000b1b8  mov     [rbx+8], rax
0x18000b1bc  mov     [rax], rbx
0x18000b1bf  mov     cs:off_18004C0D8, rbx
0x18000b1c6  mov     cs:dword_18004CEA0, 0
0x18000b1d0  mov     byte ptr [rsp+78h+pSid], 1
0x18000b1d8  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000b1de  jmp     loc_18000AF1F
0x18000b1e3  test    byte ptr [rcx+1Ch], 1
0x18000b1e7  jz      loc_18000B0BD
0x18000b1ed  mov     rcx, [rcx+10h]
0x18000b1f1  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x18000b1f8  mov     edx, 22h ; '"'
0x18000b1fd  mov     r9d, eax
0x18000b200  call    WPP_SF_d
0x18000b205  jmp     loc_18000B0BD
0x18000b20a  test    byte ptr [rcx+1Ch], 1
0x18000b20e  jz      loc_18000B00C
0x18000b214  mov     edx, 23h ; '#'
0x18000b219  jmp     short loc_18000B220
0x18000b21b  mov     edx, 25h ; '%'
0x18000b220  mov     rcx, [rcx+10h]
0x18000b224  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x18000b22b  mov     r9d, eax
0x18000b22e  call    WPP_SF_d
0x18000b233  jmp     loc_18000B00C
0x18000b238  call    cs:__imp_GetLastError
0x18000b23e  mov     ebx, eax
0x18000b240  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b247  lea     rdi, WPP_GLOBAL_Control
0x18000b24e  cmp     rcx, rdi
0x18000b251  jz      loc_18000B00C
0x18000b257  test    byte ptr [rcx+1Ch], 1
0x18000b25b  jz      loc_18000B00C
0x18000b261  mov     edx, 24h ; '$'
0x18000b266  jmp     short loc_18000B220
0x18000b268  mov     ecx, 50h ; 'P'; Size
0x18000b26d  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x18000b272  mov     rbx, rax
0x18000b275  test    rax, rax
0x18000b278  jnz     loc_18000B15F
0x18000b27e  call    cs:__imp_GetLastError
0x18000b284  mov     ebx, eax
0x18000b286  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b28d  lea     rdi, WPP_GLOBAL_Control
0x18000b294  cmp     rcx, rdi
0x18000b297  jz      loc_18000B00C
0x18000b29d  test    byte ptr [rcx+1Ch], 1
0x18000b2a1  jz      loc_18000B00C
0x18000b2a7  jmp     loc_18000B21B
0x18000b2ac  mov     rcx, [rcx+10h]
0x18000b2b0  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x18000b2b7  mov     r9d, ebp
0x18000b2ba  mov     edx, 26h ; '&'
0x18000b2bf  call    WPP_SF_d
0x18000b2c4  jmp     loc_18000AFA0
0x18000b2c9  cmp     r14b, 1
0x18000b2cd  jnz     loc_18000B04A
0x18000b2d3  xor     r9d, r9d
0x18000b2d6  mov     word ptr [rsp+78h+var_58], bp; __int16
0x18000b2db  xor     r8d, r8d; UUID *
0x18000b2de  xor     edx, edx; UUID *
0x18000b2e0  mov     rcx, r15; Uuid1
0x18000b2e3  call    UbpmpRemoveQueuedSerialActions
0x18000b2e8  jmp     loc_18000B04A
```
