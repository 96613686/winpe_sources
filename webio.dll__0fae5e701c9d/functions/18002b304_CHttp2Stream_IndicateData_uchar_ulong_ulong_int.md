# CHttp2Stream::IndicateData(uchar *,ulong,ulong,int)

- ea: `0x18002b304`
- end: `0x18002b776`
- name: `?IndicateData@CHttp2Stream@@QEAAXPEAEKKH@Z`
- size: `1138`
- prototype: `void __fastcall(CHttp2Stream *__hidden this, unsigned __int8 *, unsigned int, unsigned int, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002ab70`
- `0x1800666cc`

## callees

- `0x1800180e0`
- `0x18002b304`
- `0x18002b77c`
- `0x18002c94c`
- `0x18002db48`
- `0x18002e488`
- `0x180034504`
- `0x18004f424`
- `0x18004f6c8`
- `0x1800521ec`
- `0x1800722f0`
- `0x18009218c`
- `0x1800921ec`
- `0x180092564`
- `0x1800971ec`
- `0x1800975b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b36f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b36f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b4a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b4d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b4a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b4d7`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002b5d4`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002b5d4`

## pseudocode

```c
void __fastcall CHttp2Stream::IndicateData(
        CHttp2Stream *this,
        unsigned __int8 *a2,
        unsigned int a3,
        unsigned int a4,
        int a5)
{
  int updated; // edi
  struct _RTL_CRITICAL_SECTION *v6; // r15
  __int64 v7; // rbx
  unsigned __int8 *v11; // rdx
  __int64 v12; // r8
  unsigned int v13; // r12d
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rdx
  int v17; // r14d
  __int64 v18; // r14
  __int64 v19; // rcx
  int v20; // [rsp+40h] [rbp-81h]
  int v21; // [rsp+44h] [rbp-7Dh] BYREF
  __int64 v22; // [rsp+48h] [rbp-79h] BYREF
  int v23; // [rsp+50h] [rbp-71h] BYREF
  int v24; // [rsp+54h] [rbp-6Dh]
  int v25; // [rsp+58h] [rbp-69h] BYREF
  unsigned __int8 *v26; // [rsp+60h] [rbp-61h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v27; // [rsp+70h] [rbp-51h] BYREF
  __int64 *v28; // [rsp+80h] [rbp-41h]
  __int64 v29; // [rsp+88h] [rbp-39h]
  int *v30; // [rsp+90h] [rbp-31h]
  __int64 v31; // [rsp+98h] [rbp-29h]
  unsigned __int8 **v32; // [rsp+A0h] [rbp-21h]
  __int64 v33; // [rsp+A8h] [rbp-19h]
  int *v34; // [rsp+B0h] [rbp-11h]
  __int64 v35; // [rsp+B8h] [rbp-9h]

  updated = 0;
  v26 = a2;
  v24 = 0;
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 104);
  v25 = 0;
  v7 = 0;
  v21 = 0;
  v20 = 0;
  if ( (BYTE3(xmmword_1800AD720) & 4) != 0 )
  {
    WPP_SF_qqddl((_DWORD)this, (_DWORD)a2, a3, (_DWORD)this, (__int64)a2);
    if ( (BYTE3(xmmword_1800AD720) & 4) != 0 )
      WPP_SF_ddd(v19, 72, WPP_a7f56d08f8993c62676a3a151a0e9be5_Traceguids, *((unsigned int *)this + 4), a3, a4, a4, a5);
  }
  if ( a5 && (BYTE3(xmmword_1800AD720) & 4) != 0 )
    WPP_SF_d(1050, 73, WPP_a7f56d08f8993c62676a3a151a0e9be5_Traceguids, *((unsigned int *)this + 4));
  if ( v6 )
  {
    EnterCriticalSection(v6);
    v20 = 1;
  }
  v24 = 0;
  if ( *((_DWORD *)this + 51) )
  {
    updated = *((_DWORD *)this + 52);
    v24 = 690;
  }
  if ( updated < 0 )
  {
    v24 = 2368;
LABEL_43:
    v13 = 8;
    goto LABEL_17;
  }
  if ( !*((_DWORD *)this + 62) || *((_DWORD *)this + 44) )
  {
    v13 = 1;
    v24 = 2386;
    goto LABEL_32;
  }
  v11 = v26;
  *((_DWORD *)this + 63) = 1;
  updated = CHttp2Stream::CopyDataIntoStreamBuffer(this, v11, a3, a4, a5, &v25);
  if ( updated < 0 )
  {
    v24 = 2403;
    goto LABEL_43;
  }
  if ( v25 )
  {
    if ( (BYTE3(xmmword_1800AD720) & 4) != 0 )
      WPP_SF_(1050, 74, WPP_a7f56d08f8993c62676a3a151a0e9be5_Traceguids);
    v13 = 3;
    v24 = 2408;
    goto LABEL_32;
  }
  v13 = 8;
  if ( (Microsoft_Windows_WebIOEnableBits & 0x2000) != 0 )
  {
    v25 = *((_DWORD *)this + 4);
    v14 = *((_QWORD *)this + 3);
    v23 = 0;
    LODWORD(v26) = a3;
    v29 = 8;
    v15 = *(_QWORD *)(v14 + 8);
    v28 = &v22;
    v30 = &v25;
    v32 = &v26;
    v34 = &v23;
    v22 = v15;
    v31 = 4;
    v33 = 4;
    v35 = 4;
    McGenEventWrite_EventWriteTransfer(
      &WEB_ETW_PROVIDER_ID_Context,
      (const EVENT_DESCRIPTOR *)ReadStreamDataIndicated,
      v12,
      5u,
      &v27);
  }
  if ( a4 )
  {
    updated = CHttp2Stream::UpdateWindowIncrement(this, a4);
    if ( updated < 0 )
    {
      v24 = 2422;
      goto LABEL_17;
    }
  }
  v16 = *((_QWORD *)this + 21);
  if ( !v16 )
  {
    updated = 0;
    goto LABEL_17;
  }
  if ( *(_DWORD *)(v16 + 4) == 1 )
  {
    v24 = 2440;
LABEL_32:
    updated = -2147024838;
    goto LABEL_17;
  }
  if ( *(_DWORD *)(v16 + 4) )
  {
    updated = -2147023537;
    v24 = 2445;
  }
  else
  {
    updated = CHttp2Stream::ProcessReceiveBuffer(
                this,
                *(unsigned __int8 **)(v16 + 40),
                *(_DWORD *)(v16 + 48),
                (unsigned int *)(v16 + 52),
                &v21);
    if ( updated < 0 )
    {
      v24 = 2450;
    }
    else if ( v21 )
    {
      if ( (BYTE3(xmmword_1800AD720) & 4) != 0 )
        WPP_SF_dd(
          1050,
          75,
          WPP_a7f56d08f8993c62676a3a151a0e9be5_Traceguids,
          *((unsigned int *)this + 4),
          *(_DWORD *)(*((_QWORD *)this + 21) + 52LL));
      v7 = *((_QWORD *)this + 21);
      *((_QWORD *)this + 21) = 0;
      if ( *((_DWORD *)this + 36) )
      {
        v18 = *((_QWORD *)this + 3);
        if ( (unsigned __int8)WaCancelTwTimer(v18 + 184) )
        {
          *(_QWORD *)(v18 + 248) = 0;
          *(_QWORD *)(v18 + 256) = 0;
          *((_DWORD *)this + 36) = 0;
          CHttp2Stream::Release(this);
        }
      }
      *(_DWORD *)(v7 + 16) = 0;
      _InterlockedIncrement((volatile signed __int32 *)v7);
      SubmitThreadpoolWork(*(PTP_WORK *)(*(_QWORD *)(v7 + 8) + 8LL));
    }
    else
    {
      CHttp2Stream::ResetReceiveTimer(this);
    }
  }
LABEL_17:
  v17 = v20;
  if ( v6 && v20 )
  {
    LeaveCriticalSection(v6);
    v17 = 0;
  }
  if ( v7 )
    CHttp2ReceiveContext::Release((CHttp2ReceiveContext *)v7);
  if ( updated < 0 )
    CHttp2Stream::AbortHr(this, updated, v13);
  if ( (BYTE3(xmmword_1800AD720) & 4) != 0 )
    WPP_SF_d(1050, 76, WPP_a7f56d08f8993c62676a3a151a0e9be5_Traceguids, (unsigned int)updated);
  if ( v17 )
  {
    if ( v6 )
      LeaveCriticalSection(v6);
  }
}

```

## disassembly

```asm
0x18002b304  push    rbp
0x18002b306  push    rbx
0x18002b307  push    rsi
0x18002b308  push    rdi
0x18002b309  push    r12
0x18002b30b  push    r13
0x18002b30d  push    r14
0x18002b30f  push    r15
0x18002b311  lea     rbp, [rsp-17h]
0x18002b316  sub     rsp, 0D8h
0x18002b31d  mov     rax, cs:__security_cookie
0x18002b324  xor     rax, rsp
0x18002b327  mov     [rbp+4Fh+var_50], rax
0x18002b32b  xor     edi, edi
0x18002b32d  mov     [rbp+4Fh+var_B0], rdx
0x18002b331  mov     [rbp+4Fh+var_BC], edi
0x18002b334  lea     r15, [rcx+68h]
0x18002b338  mov     [rbp+4Fh+var_B8], edi
0x18002b33b  mov     ebx, edi
0x18002b33d  mov     [rbp+4Fh+var_CC], edi
0x18002b340  mov     r14d, r9d
0x18002b343  mov     [rsp+110h+var_D0], edi
0x18002b347  mov     r13d, r8d
0x18002b34a  mov     rsi, rcx
0x18002b34d  test    byte ptr cs:xmmword_1800AD720+3, 4
0x18002b354  mov     r12d, [rbp+4Fh+arg_20]
0x18002b358  jnz     loc_18002B64B
0x18002b35e  test    r12d, r12d
0x18002b361  jnz     loc_18002B5F7
0x18002b367  test    r15, r15
0x18002b36a  jz      short loc_18002B383
0x18002b36c  mov     rcx, r15; lpCriticalSection
0x18002b36f  call    cs:__imp_EnterCriticalSection
0x18002b376  nop     dword ptr [rax+rax+00h]
0x18002b37b  mov     [rsp+110h+var_D0], 1
0x18002b383  mov     [rbp+4Fh+var_BC], edi
0x18002b386  cmp     [rsi+0CCh], edi
0x18002b38c  jnz     loc_18002B639
0x18002b392  test    edi, edi
0x18002b394  js      loc_18002B5E5
0x18002b39a  cmp     [rsi+0F8h], ebx
0x18002b3a0  jz      loc_18002B734
0x18002b3a6  cmp     [rsi+0B0h], ebx
0x18002b3ac  jnz     loc_18002B734
0x18002b3b2  mov     rdx, [rbp+4Fh+var_B0]; unsigned __int8 *
0x18002b3b6  lea     rax, [rbp+4Fh+var_B8]
0x18002b3ba  mov     [rsp+110h+var_E8], rax; int *
0x18002b3bf  mov     r9d, r14d; unsigned int
0x18002b3c2  mov     r8d, r13d; unsigned int
0x18002b3c5  mov     dword ptr [rsp+110h+var_F0], r12d; int
0x18002b3ca  mov     rcx, rsi; this
0x18002b3cd  mov     dword ptr [rsi+0FCh], 1
0x18002b3d7  call    ?CopyDataIntoStreamBuffer@CHttp2Stream@@AEAAJPEAEKKHPEAH@Z; CHttp2Stream::CopyDataIntoStreamBuffer(uchar *,ulong,ulong,int,int *)
0x18002b3dc  mov     edi, eax
0x18002b3de  test    eax, eax
0x18002b3e0  js      loc_18002B623
0x18002b3e6  cmp     [rbp+4Fh+var_B8], ebx
0x18002b3e9  jnz     loc_18002B698
0x18002b3ef  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits+1, 20h
0x18002b3f6  mov     r12d, 8
0x18002b3fc  jz      short loc_18002B474
0x18002b3fe  mov     eax, [rsi+10h]
0x18002b401  lea     r9d, [r12-3]
0x18002b406  mov     [rbp+4Fh+var_B8], eax
0x18002b409  lea     rdx, ReadStreamDataIndicated
0x18002b410  mov     rax, [rsi+18h]
0x18002b414  mov     [rbp+4Fh+var_C0], ebx
0x18002b417  mov     dword ptr [rbp+4Fh+var_B0], r13d
0x18002b41b  mov     [rbp+4Fh+var_88], r12
0x18002b41f  mov     rcx, [rax+8]
0x18002b423  lea     rax, [rbp+4Fh+var_C8]
0x18002b427  mov     [rbp+4Fh+var_90], rax
0x18002b42b  lea     rax, [rbp+4Fh+var_B8]
0x18002b42f  mov     [rbp+4Fh+var_80], rax
0x18002b433  lea     rax, [rbp+4Fh+var_B0]
0x18002b437  mov     [rbp+4Fh+var_70], rax
0x18002b43b  lea     rax, [rbp+4Fh+var_C0]
0x18002b43f  mov     [rbp+4Fh+var_60], rax
0x18002b443  lea     rax, [rbp+4Fh+var_A0]
0x18002b447  mov     [rbp+4Fh+var_C8], rcx
0x18002b44b  lea     rcx, WEB_ETW_PROVIDER_ID_Context
0x18002b452  mov     [rsp+110h+var_F0], rax
0x18002b457  mov     [rbp+4Fh+var_78], 4
0x18002b45f  mov     [rbp+4Fh+var_68], 4
0x18002b467  mov     [rbp+4Fh+var_58], 4
0x18002b46f  call    McGenEventWrite_EventWriteTransfer
0x18002b474  test    r14d, r14d
0x18002b477  jnz     loc_18002B6C9
0x18002b47d  mov     rdx, [rsi+0A8h]
0x18002b484  test    rdx, rdx
0x18002b487  jnz     loc_18002B50E
0x18002b48d  xor     edi, edi
0x18002b48f  mov     r14d, [rsp+110h+var_D0]
0x18002b494  test    r15, r15
0x18002b497  jz      short loc_18002B4B0
0x18002b499  test    r14d, r14d
0x18002b49c  jz      short loc_18002B4B0
0x18002b49e  mov     rcx, r15; lpCriticalSection
0x18002b4a1  call    cs:__imp_LeaveCriticalSection
0x18002b4a8  nop     dword ptr [rax+rax+00h]
0x18002b4ad  xor     r14d, r14d
0x18002b4b0  test    rbx, rbx
0x18002b4b3  jnz     short loc_18002B504
0x18002b4b5  test    edi, edi
0x18002b4b7  js      loc_18002B746
0x18002b4bd  test    byte ptr cs:xmmword_1800AD720+3, 4
0x18002b4c4  jnz     loc_18002B758
0x18002b4ca  test    r14d, r14d
0x18002b4cd  jz      short loc_18002B4E3
0x18002b4cf  test    r15, r15
0x18002b4d2  jz      short loc_18002B4E3
0x18002b4d4  mov     rcx, r15; lpCriticalSection
0x18002b4d7  call    cs:__imp_LeaveCriticalSection
0x18002b4de  nop     dword ptr [rax+rax+00h]
0x18002b4e3  mov     rcx, [rbp+4Fh+var_50]
0x18002b4e7  xor     rcx, rsp; StackCookie
0x18002b4ea  call    __security_check_cookie
0x18002b4ef  add     rsp, 0D8h
0x18002b4f6  pop     r15
0x18002b4f8  pop     r14
0x18002b4fa  pop     r13
0x18002b4fc  pop     r12
0x18002b4fe  pop     rdi
0x18002b4ff  pop     rsi
0x18002b500  pop     rbx
0x18002b501  pop     rbp
0x18002b502  retn
0x18002b504  mov     rcx, rbx; this
0x18002b507  call    ?Release@CHttp2ReceiveContext@@QEAAKXZ; CHttp2ReceiveContext::Release(void)
0x18002b50c  jmp     short loc_18002B4B5
0x18002b50e  cmp     dword ptr [rdx+4], 1
0x18002b512  jnz     short loc_18002B525
0x18002b514  mov     [rbp+4Fh+var_BC], 988h
0x18002b51b  mov     edi, 8007003Ah
0x18002b520  jmp     loc_18002B48F
0x18002b525  cmp     [rdx+4], ebx
0x18002b528  jnz     loc_18002B6EA
0x18002b52e  mov     r8d, [rdx+30h]; unsigned int
0x18002b532  lea     r9, [rdx+34h]; unsigned int *
0x18002b536  mov     rdx, [rdx+28h]; unsigned __int8 *
0x18002b53a  lea     rax, [rbp+4Fh+var_CC]
0x18002b53e  mov     rcx, rsi; this
0x18002b541  mov     [rsp+110h+var_F0], rax; int *
0x18002b546  call    ?ProcessReceiveBuffer@CHttp2Stream@@AEAAJPEAEKPEAKPEAH@Z; CHttp2Stream::ProcessReceiveBuffer(uchar *,ulong,ulong *,int *)
0x18002b54b  mov     edi, eax
0x18002b54d  test    eax, eax
0x18002b54f  js      loc_18002B6FB
0x18002b555  cmp     [rbp+4Fh+var_CC], ebx
0x18002b558  jz      loc_18002B62C
0x18002b55e  test    byte ptr cs:xmmword_1800AD720+3, 4
0x18002b565  jnz     loc_18002B707
0x18002b56b  mov     rbx, [rsi+0A8h]
0x18002b572  mov     qword ptr [rsi+0A8h], 0
0x18002b57d  cmp     dword ptr [rsi+90h], 0
0x18002b584  jz      short loc_18002B5C2
0x18002b586  mov     r14, [rsi+18h]
0x18002b58a  lea     rcx, [r14+0B8h]
0x18002b591  call    WaCancelTwTimer
0x18002b596  test    al, al
0x18002b598  jz      short loc_18002B5C2
0x18002b59a  mov     qword ptr [r14+0F8h], 0
0x18002b5a5  mov     rcx, rsi; this
0x18002b5a8  mov     qword ptr [r14+100h], 0
0x18002b5b3  mov     dword ptr [rsi+90h], 0
0x18002b5bd  call    ?Release@CHttp2Stream@@QEAAKXZ; CHttp2Stream::Release(void)
0x18002b5c2  mov     dword ptr [rbx+10h], 0
0x18002b5c9  lock inc dword ptr [rbx]
0x18002b5cc  mov     rcx, [rbx+8]
0x18002b5d0  mov     rcx, [rcx+8]; pwk
0x18002b5d4  call    cs:__imp_SubmitThreadpoolWork
0x18002b5db  nop     dword ptr [rax+rax+00h]
0x18002b5e0  jmp     loc_18002B48F
0x18002b5e5  mov     [rbp+4Fh+var_BC], 940h
0x18002b5ec  mov     r12d, 8
0x18002b5f2  jmp     loc_18002B48F
0x18002b5f7  test    byte ptr cs:xmmword_1800AD720+3, 4
0x18002b5fe  jz      loc_18002B367
0x18002b604  mov     r9d, [rsi+10h]
0x18002b608  lea     r8, WPP_a7f56d08f8993c62676a3a151a0e9be5_Traceguids
0x18002b60f  mov     edx, 49h ; 'I'
0x18002b614  mov     ecx, 41Ah
0x18002b619  call    WPP_SF_d
0x18002b61e  jmp     loc_18002B367
0x18002b623  mov     [rbp+4Fh+var_BC], 963h
0x18002b62a  jmp     short loc_18002B5EC
0x18002b62c  mov     rcx, rsi; this
0x18002b62f  call    ?ResetReceiveTimer@CHttp2Stream@@AEAAXXZ; CHttp2Stream::ResetReceiveTimer(void)
0x18002b634  jmp     loc_18002B48F
0x18002b639  mov     edi, [rsi+0D0h]
0x18002b63f  mov     [rbp+4Fh+var_BC], 2B2h
0x18002b646  jmp     loc_18002B392
0x18002b64b  mov     [rsp+110h+var_D8], r12d
0x18002b650  mov     r9, rsi
0x18002b653  mov     [rsp+110h+var_E0], r14d
0x18002b658  mov     dword ptr [rsp+110h+var_E8], r13d
0x18002b65d  mov     [rsp+110h+var_F0], rdx
0x18002b662  call    WPP_SF_qqddl
0x18002b667  test    byte ptr cs:xmmword_1800AD720+3, 4
0x18002b66e  jz      loc_18002B35E
0x18002b674  mov     r9d, [rsi+10h]
0x18002b678  lea     r8, WPP_a7f56d08f8993c62676a3a151a0e9be5_Traceguids
0x18002b67f  mov     edx, 48h ; 'H'
0x18002b684  mov     dword ptr [rsp+110h+var_E8], r14d
0x18002b689  mov     dword ptr [rsp+110h+var_F0], r13d
0x18002b68e  call    WPP_SF_ddd
0x18002b693  jmp     loc_18002B35E
0x18002b698  test    byte ptr cs:xmmword_1800AD720+3, 4
0x18002b69f  jz      short loc_18002B6B7
0x18002b6a1  mov     edx, 4Ah ; 'J'
0x18002b6a6  lea     r8, WPP_a7f56d08f8993c62676a3a151a0e9be5_Traceguids
0x18002b6ad  mov     ecx, 41Ah
0x18002b6b2  call    WPP_SF_
0x18002b6b7  mov     r12d, 3
0x18002b6bd  mov     [rbp+4Fh+var_BC], 968h
0x18002b6c4  jmp     loc_18002B51B
0x18002b6c9  mov     edx, r14d; unsigned int
0x18002b6cc  mov     rcx, rsi; this
0x18002b6cf  call    ?UpdateWindowIncrement@CHttp2Stream@@AEAAJK@Z; CHttp2Stream::UpdateWindowIncrement(ulong)
0x18002b6d4  mov     edi, eax
0x18002b6d6  test    eax, eax
0x18002b6d8  jns     loc_18002B47D
0x18002b6de  mov     [rbp+4Fh+var_BC], 976h
0x18002b6e5  jmp     loc_18002B48F
0x18002b6ea  mov     edi, 8007054Fh
0x18002b6ef  mov     [rbp+4Fh+var_BC], 98Dh
0x18002b6f6  jmp     loc_18002B48F
0x18002b6fb  mov     [rbp+4Fh+var_BC], 992h
0x18002b702  jmp     loc_18002B48F
0x18002b707  mov     rax, [rsi+0A8h]
0x18002b70e  lea     r8, WPP_a7f56d08f8993c62676a3a151a0e9be5_Traceguids
0x18002b715  mov     r9d, [rsi+10h]
0x18002b719  mov     edx, 4Bh ; 'K'
0x18002b71e  mov     ecx, 41Ah
0x18002b723  mov     eax, [rax+34h]
0x18002b726  mov     dword ptr [rsp+110h+var_F0], eax
0x18002b72a  call    WPP_SF_dd
0x18002b72f  jmp     loc_18002B56B
0x18002b734  mov     r12d, 1
0x18002b73a  mov     [rbp+4Fh+var_BC], 952h
0x18002b741  jmp     loc_18002B51B
0x18002b746  mov     r8d, r12d; unsigned int
0x18002b749  mov     edx, edi; int
0x18002b74b  mov     rcx, rsi; this
0x18002b74e  call    ?AbortHr@CHttp2Stream@@QEAAHJK@Z; CHttp2Stream::AbortHr(long,ulong)
0x18002b753  jmp     loc_18002B4BD
0x18002b758  mov     edx, 4Ch ; 'L'
0x18002b75d  lea     r8, WPP_a7f56d08f8993c62676a3a151a0e9be5_Traceguids
0x18002b764  mov     ecx, 41Ah
0x18002b769  mov     r9d, edi
0x18002b76c  call    WPP_SF_d
0x18002b771  jmp     loc_18002B4CA
```
