# UbpmRunNextSerializedAction

- ea: `0x180003da0`
- end: `0x180004278`
- name: `UbpmRunNextSerializedAction`
- size: `1240`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, int, PSID pSid, __int64, int, size_t Size, void *Src, unsigned __int8, unsigned __int16 **, int, unsigned __int8, unsigned __int16 **)`
- caller_count: `6`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800032ac`
- `0x1800060d0`
- `0x180011a90`
- `0x18001bf54`
- `0x18001da20`
- `0x18002ce98`

## callees

- `0x180003da0`
- `0x180004280`
- `0x1800053a0`
- `0x18000fbf0`
- `0x1800103c0`
- `0x1800150c0`
- `0x1800265d0`
- `0x1800351ec`
- `0x180040222`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180003fbf`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180003fbf`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180004047`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180004047`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180004151`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180004151`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003fd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000405b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800041b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004203`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003fd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000405b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800041b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004203`

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
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  DWORD v29; // ebx
  DWORD v30; // eax
  UUID v31; // xmm1
  DWORD result; // eax
  _QWORD *v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // r9
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // r9
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 v42; // r9
  DWORD LastError; // eax
  void *v44; // rax
  __int128 v45; // xmm1
  _QWORD *v46; // rax
  __int64 v47; // rdx
  _OWORD *v48; // rbx
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
    v29 = result;
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
      v29 = LastError;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids, LastError);
      goto LABEL_19;
    }
  }
  v25 = UbpmUtilsCloneStringArray(a12, (const unsigned __int16 **)a13, (const unsigned __int16 ***)v24 + 14);
  v29 = v25;
  if ( v25 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids, v25);
    v22 = 0;
    goto LABEL_19;
  }
  v30 = UbpmUtilsCloneStringArray(a15, (const unsigned __int16 **)a16, (const unsigned __int16 ***)v24 + 16);
  v29 = v30;
  if ( v30 )
  {
    v33 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_17;
    v47 = 35;
    goto LABEL_41;
  }
  *((_DWORD *)v24 + 20) = a9;
  if ( Src )
  {
    v44 = UbpmAlloc((unsigned int)Size);
    *((_QWORD *)v24 + 11) = v44;
    if ( !v44 )
    {
      v30 = GetLastError();
      v29 = v30;
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_17;
      v47 = 36;
      goto LABEL_41;
    }
    memcpy_0(v44, Src, (unsigned int)Size);
    *((_DWORD *)v24 + 21) = Size;
  }
  if ( (_WORD)v18 == 1 )
    goto LABEL_9;
  v48 = UbpmAlloc(0x50u);
  if ( !v48 )
  {
    v30 = GetLastError();
    v29 = v30;
    v33 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_17;
    v47 = 37;
LABEL_41:
    WPP_SF_d(v33[2], v47, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids, v30);
LABEL_17:
    v22 = 0;
LABEL_18:
    v19 = a3;
LABEL_19:
    UBPM_MIDL_user_free(*((_QWORD *)v24 + 14), v26, v27, v28);
    UBPM_MIDL_user_free(*((_QWORD *)v24 + 16), v34, v35, v36);
    UBPM_MIDL_user_free(*((_QWORD *)v24 + 11), v37, v38, v39);
    result = UBPM_MIDL_user_free(v24, v40, v41, v42);
LABEL_20:
    if ( v29 )
    {
      if ( v22 == 1 )
        return UbpmpRemoveQueuedSerialActions(v19, 0, 0, v18);
    }
    return result;
  }
  v48[1] = *a3;
  v45 = *a1;
  *((_QWORD *)v48 + 6) = a8;
  *((_WORD *)v48 + 28) = v18;
  v48[2] = v45;
  *((_QWORD *)v48 + 1) = v48;
  *(_QWORD *)v48 = v48;
  UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_SRWLOCK *)&g_QueuedSerialActionsLock);
  v46 = off_18004F0D8[0];
  if ( *(_UNKNOWN ***)off_18004F0D8[0] != &g_leQueuedSerialActionsListHead )
    __fastfail(3u);
  *(_QWORD *)v48 = &g_leQueuedSerialActionsListHead;
  *((_QWORD *)v48 + 1) = v46;
  *v46 = v48;
  off_18004F0D8[0] = (_UNKNOWN **)v48;
  dword_18004FFA0 = 0;
  pSida = 1;
  RtlReleaseSRWLockExclusive(&g_QueuedSerialActionsLock);
LABEL_9:
  *(_DWORD *)v24 = 1954046803;
  *(_OWORD *)(v24 + 24) = *a1;
  v31 = *a3;
  v24[96] &= ~1u;
  *((_QWORD *)v24 + 6) = a5;
  v24[104] = a12;
  v22 = pSida;
  v24[96] |= pSida;
  *((_DWORD *)v24 + 14) = a6;
  *((_DWORD *)v24 + 25) = a14;
  *(UUID *)(v24 + 4) = v31;
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
  v29 = result;
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
0x180003da0  mov     [rsp+Uuid1], r8
0x180003da5  push    rbx
0x180003da6  push    rbp
0x180003da7  push    rsi
0x180003da8  push    rdi
0x180003da9  push    r12
0x180003dab  push    r13
0x180003dad  push    r14
0x180003daf  push    r15
0x180003db1  sub     rsp, 38h
0x180003db5  mov     rbx, [rsp+78h+pSid]
0x180003dbd  mov     r13d, r9d
0x180003dc0  movzx   ebp, dx
0x180003dc3  mov     r15, r8
0x180003dc6  mov     r12, rcx
0x180003dc9  test    rbx, rbx
0x180003dcc  jnz     loc_180003FBC
0x180003dd2  xor     edi, edi
0x180003dd4  xor     r14b, r14b
0x180003dd7  lea     ecx, [rdi+88h]; Size
0x180003ddd  mov     byte ptr [rsp+78h+pSid], r14b
0x180003de5  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x180003dea  mov     rsi, rax
0x180003ded  test    rax, rax
0x180003df0  jz      loc_180003FD2
0x180003df6  test    rbx, rbx
0x180003df9  jnz     loc_180004037
0x180003dff  mov     r14b, [rsp+78h+arg_58]
0x180003e07  lea     r8, [rsi+70h]; unsigned __int16 ***
0x180003e0b  mov     rdx, [rsp+78h+arg_60]; unsigned __int16 **
0x180003e13  mov     cl, r14b; unsigned __int8
0x180003e16  call    ?UbpmUtilsCloneStringArray@@YAKEPEAPEBGPEAPEAPEBG@Z; UbpmUtilsCloneStringArray(uchar,ushort const * *,ushort const * * *)
0x180003e1b  mov     ebx, eax
0x180003e1d  test    eax, eax
0x180003e1f  jnz     loc_180004013
0x180003e25  mov     r15b, [rsp+78h+arg_70]
0x180003e2d  lea     r8, [rsi+80h]; unsigned __int16 ***
0x180003e34  mov     rdx, [rsp+78h+arg_78]; unsigned __int16 **
0x180003e3c  mov     cl, r15b; unsigned __int8
0x180003e3f  call    ?UbpmUtilsCloneStringArray@@YAKEPEAPEBGPEAPEAPEBG@Z; UbpmUtilsCloneStringArray(uchar,ushort const * *,ushort const * * *)
0x180003e44  mov     ebx, eax
0x180003e46  test    eax, eax
0x180003e48  jnz     loc_180003F55
0x180003e4e  mov     rdi, [rsp+78h+Src]
0x180003e56  mov     eax, [rsp+78h+arg_40]
0x180003e5d  mov     [rsi+50h], eax
0x180003e60  test    rdi, rdi
0x180003e63  jnz     loc_1800040A7
0x180003e69  mov     rdi, [rsp+78h+arg_38]
0x180003e71  mov     eax, 1
0x180003e76  cmp     bp, ax
0x180003e79  jnz     loc_1800041ED
0x180003e7f  mov     rax, [rsp+78h+Uuid1]
0x180003e87  mov     dword ptr [rsi], 74786353h
0x180003e8d  movups  xmm0, xmmword ptr [r12]
0x180003e92  movdqu  xmmword ptr [rsi+18h], xmm0
0x180003e97  movups  xmm1, xmmword ptr [rax]
0x180003e9a  mov     rax, [rsp+78h+arg_20]
0x180003ea2  and     byte ptr [rsi+60h], 0FEh
0x180003ea6  mov     [rsi+30h], rax
0x180003eaa  mov     eax, [rsp+78h+arg_28]
0x180003eb1  mov     [rsi+68h], r14b
0x180003eb5  mov     r14b, byte ptr [rsp+78h+pSid]
0x180003ebd  or      [rsi+60h], r14b
0x180003ec1  mov     [rsi+38h], eax
0x180003ec4  mov     eax, [rsp+78h+arg_68]
0x180003ecb  mov     [rsi+64h], eax
0x180003ece  movdqu  xmmword ptr [rsi+4], xmm1
0x180003ed3  mov     [rsi+14h], bp
0x180003ed7  mov     [rsi+28h], r13d
0x180003edb  mov     [rsi+48h], rdi
0x180003edf  mov     [rsi+78h], r15b
0x180003ee3  mov     rcx, cs:WPP_GLOBAL_Control
0x180003eea  lea     rdi, WPP_GLOBAL_Control
0x180003ef1  cmp     rcx, rdi
0x180003ef4  jz      short loc_180003F00
0x180003ef6  test    byte ptr [rcx+1Ch], 20h
0x180003efa  jnz     loc_180004237
0x180003f00  xor     r9d, r9d; struct _TP_CALLBACK_ENVIRON_V3 *
0x180003f03  mov     [rsp+78h+var_58], 0; struct _UBPM_SRWLOCK *
0x180003f0c  mov     rdx, rsi; void *
0x180003f0f  lea     rcx, ?UbpmpRunSerializedActionCallback@@YAXPEAXE0@Z; void (*)(void *, unsigned __int8, void *)
0x180003f16  lea     r8d, [r9+1]; int
0x180003f1a  call    ?UbpmUtilsSubmitThreadPoolWork@@YAKP6AXPEAXE0@Z0HPEAU_TP_CALLBACK_ENVIRON_V3@@PEAU_UBPM_SRWLOCK@@@Z; UbpmUtilsSubmitThreadPoolWork(void (*)(void *,uchar,void *),void *,int,_TP_CALLBACK_ENVIRON_V3 *,_UBPM_SRWLOCK *)
0x180003f1f  mov     ebx, eax
0x180003f21  test    eax, eax
0x180003f23  jz      loc_180003FAA
0x180003f29  mov     rcx, cs:WPP_GLOBAL_Control
0x180003f30  cmp     rcx, rdi
0x180003f33  jz      short loc_180003F74
0x180003f35  test    byte ptr [rcx+1Ch], 1
0x180003f39  jz      short loc_180003F74
0x180003f3b  mov     rcx, [rcx+10h]
0x180003f3f  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x180003f46  mov     edx, 27h ; '''
0x180003f4b  mov     r9d, eax
0x180003f4e  call    WPP_SF_d
0x180003f53  jmp     short loc_180003F74
0x180003f55  mov     rcx, cs:WPP_GLOBAL_Control
0x180003f5c  lea     rdi, WPP_GLOBAL_Control
0x180003f63  cmp     rcx, rdi
0x180003f66  jnz     loc_180004189
0x180003f6c  mov     r14b, byte ptr [rsp+78h+pSid]
0x180003f74  mov     r15, [rsp+78h+Uuid1]
0x180003f7c  mov     rcx, [rsi+70h]
0x180003f80  call    UBPM_MIDL_user_free
0x180003f85  mov     rcx, [rsi+80h]
0x180003f8c  call    UBPM_MIDL_user_free
0x180003f91  mov     rcx, [rsi+58h]
0x180003f95  call    UBPM_MIDL_user_free
0x180003f9a  mov     rcx, rsi
0x180003f9d  call    UBPM_MIDL_user_free
0x180003fa2  test    ebx, ebx
0x180003fa4  jnz     loc_180004254
0x180003faa  add     rsp, 38h
0x180003fae  pop     r15
0x180003fb0  pop     r14
0x180003fb2  pop     r13
0x180003fb4  pop     r12
0x180003fb6  pop     rdi
0x180003fb7  pop     rsi
0x180003fb8  pop     rbp
0x180003fb9  pop     rbx
0x180003fba  retn
0x180003fbc  mov     rcx, rbx; pSid
0x180003fbf  call    cs:__imp_GetLengthSid
0x180003fc6  nop     dword ptr [rax+rax+00h]
0x180003fcb  mov     edi, eax
0x180003fcd  jmp     loc_180003DD4
0x180003fd2  call    cs:__imp_GetLastError
0x180003fd9  nop     dword ptr [rax+rax+00h]
0x180003fde  mov     ebx, eax
0x180003fe0  mov     rcx, cs:WPP_GLOBAL_Control
0x180003fe7  lea     rdi, WPP_GLOBAL_Control
0x180003fee  cmp     rcx, rdi
0x180003ff1  jz      short loc_180003FA2
0x180003ff3  test    byte ptr [rcx+1Ch], 1
0x180003ff7  jz      short loc_180003FA2
0x180003ff9  mov     rcx, [rcx+10h]
0x180003ffd  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x180004004  mov     edx, 20h ; ' '
0x180004009  mov     r9d, eax
0x18000400c  call    WPP_SF_d
0x180004011  jmp     short loc_180003FA2
0x180004013  mov     rcx, cs:WPP_GLOBAL_Control
0x18000401a  lea     rdi, WPP_GLOBAL_Control
0x180004021  cmp     rcx, rdi
0x180004024  jnz     loc_180004162
0x18000402a  mov     r14b, byte ptr [rsp+78h+pSid]
0x180004032  jmp     loc_180003F7C
0x180004037  lea     rdx, [rax+88h]; pDestinationSid
0x18000403e  mov     r8, rbx; pSourceSid
0x180004041  mov     ecx, edi; nDestinationSidLength
0x180004043  mov     [rax+40h], rdx
0x180004047  call    cs:__imp_CopySid
0x18000404e  nop     dword ptr [rax+rax+00h]
0x180004053  test    eax, eax
0x180004055  jnz     loc_180003DFF
0x18000405b  call    cs:__imp_GetLastError
0x180004062  nop     dword ptr [rax+rax+00h]
0x180004067  mov     ebx, eax
0x180004069  mov     rcx, cs:WPP_GLOBAL_Control
0x180004070  lea     rdi, WPP_GLOBAL_Control
0x180004077  cmp     rcx, rdi
0x18000407a  jz      loc_180003F7C
0x180004080  test    byte ptr [rcx+1Ch], 1
0x180004084  jz      loc_180003F7C
0x18000408a  mov     rcx, [rcx+10h]
0x18000408e  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x180004095  mov     edx, 21h ; '!'
0x18000409a  mov     r9d, eax
0x18000409d  call    WPP_SF_d
0x1800040a2  jmp     loc_180003F7C
0x1800040a7  mov     ebx, dword ptr [rsp+78h+Size]
0x1800040ae  mov     ecx, ebx; Size
0x1800040b0  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x1800040b5  mov     [rsi+58h], rax
0x1800040b9  test    rax, rax
0x1800040bc  jz      loc_1800041B7
0x1800040c2  mov     r8d, ebx; Size
0x1800040c5  mov     rdx, rdi; Src
0x1800040c8  mov     rcx, rax; void *
0x1800040cb  call    memcpy_0
0x1800040d0  mov     [rsi+54h], ebx
0x1800040d3  jmp     loc_180003E69
0x1800040d8  mov     rax, [rsp+78h+Uuid1]
0x1800040e0  lea     rcx, g_QueuedSerialActionsLock; struct _UBPM_SRWLOCK *
0x1800040e7  movups  xmm0, xmmword ptr [rax]
0x1800040ea  movdqu  xmmword ptr [rbx+10h], xmm0
0x1800040ef  movups  xmm1, xmmword ptr [r12]
0x1800040f4  mov     [rbx+30h], rdi
0x1800040f8  mov     [rbx+38h], bp
0x1800040fc  movdqu  xmmword ptr [rbx+20h], xmm1
0x180004101  mov     [rbx+8], rbx
0x180004105  mov     [rbx], rbx
0x180004108  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x18000410d  mov     rax, cs:off_18004F0D8
0x180004114  lea     rcx, g_leQueuedSerialActionsListHead
0x18000411b  cmp     [rax], rcx
0x18000411e  jz      short loc_180004127
0x180004120  mov     ecx, 3
0x180004125  int     29h; Win8: RtlFailFast(ecx)
0x180004127  mov     [rbx], rcx
0x18000412a  lea     rcx, g_QueuedSerialActionsLock
0x180004131  mov     [rbx+8], rax
0x180004135  mov     [rax], rbx
0x180004138  mov     cs:off_18004F0D8, rbx
0x18000413f  mov     cs:dword_18004FFA0, 0
0x180004149  mov     byte ptr [rsp+78h+pSid], 1
0x180004151  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180004158  nop     dword ptr [rax+rax+00h]
0x18000415d  jmp     loc_180003E7F
0x180004162  test    byte ptr [rcx+1Ch], 1
0x180004166  jz      loc_18000402A
0x18000416c  mov     rcx, [rcx+10h]
0x180004170  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x180004177  mov     edx, 22h ; '"'
0x18000417c  mov     r9d, eax
0x18000417f  call    WPP_SF_d
0x180004184  jmp     loc_18000402A
0x180004189  test    byte ptr [rcx+1Ch], 1
0x18000418d  jz      loc_180003F6C
0x180004193  mov     edx, 23h ; '#'
0x180004198  jmp     short loc_18000419F
0x18000419a  mov     edx, 25h ; '%'
0x18000419f  mov     rcx, [rcx+10h]
0x1800041a3  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x1800041aa  mov     r9d, eax
0x1800041ad  call    WPP_SF_d
0x1800041b2  jmp     loc_180003F6C
0x1800041b7  call    cs:__imp_GetLastError
0x1800041be  nop     dword ptr [rax+rax+00h]
0x1800041c3  mov     ebx, eax
0x1800041c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800041cc  lea     rdi, WPP_GLOBAL_Control
0x1800041d3  cmp     rcx, rdi
0x1800041d6  jz      loc_180003F6C
0x1800041dc  test    byte ptr [rcx+1Ch], 1
0x1800041e0  jz      loc_180003F6C
0x1800041e6  mov     edx, 24h ; '$'
0x1800041eb  jmp     short loc_18000419F
0x1800041ed  mov     ecx, 50h ; 'P'; Size
0x1800041f2  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x1800041f7  mov     rbx, rax
0x1800041fa  test    rax, rax
0x1800041fd  jnz     loc_1800040D8
0x180004203  call    cs:__imp_GetLastError
0x18000420a  nop     dword ptr [rax+rax+00h]
0x18000420f  mov     ebx, eax
0x180004211  mov     rcx, cs:WPP_GLOBAL_Control
0x180004218  lea     rdi, WPP_GLOBAL_Control
0x18000421f  cmp     rcx, rdi
0x180004222  jz      loc_180003F6C
0x180004228  test    byte ptr [rcx+1Ch], 1
0x18000422c  jz      loc_180003F6C
0x180004232  jmp     loc_18000419A
0x180004237  mov     rcx, [rcx+10h]
0x18000423b  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x180004242  mov     r9d, ebp
0x180004245  mov     edx, 26h ; '&'
0x18000424a  call    WPP_SF_d
0x18000424f  jmp     loc_180003F00
0x180004254  cmp     r14b, 1
0x180004258  jnz     loc_180003FAA
0x18000425e  xor     r9d, r9d
0x180004261  mov     word ptr [rsp+78h+var_58], bp; __int16
0x180004266  xor     r8d, r8d; UUID *
0x180004269  xor     edx, edx; UUID *
0x18000426b  mov     rcx, r15; Uuid1
0x18000426e  call    UbpmpRemoveQueuedSerialActions
0x180004273  jmp     loc_180003FAA
```
