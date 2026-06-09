# Tpm20CmdGetCommandInfos(TpmTransport *,uint,_TPM20_CMD_INFO const * *)

- ea: `0x140029130`
- end: `0x1400293b6`
- name: `?Tpm20CmdGetCommandInfos@@YAJPEAVTpmTransport@@IPEAPEBT_TPM20_CMD_INFO@@@Z`
- size: `646`
- prototype: `__int64 __fastcall(struct TpmTransport *this, unsigned int, const union _TPM20_CMD_INFO **)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14001b464`

## callees

- `0x1400078b8`
- `0x140009660`
- `0x14001a770`
- `0x140029130`
- `0x140039740`
- `0x140039b40`
- `0x140045430`
- `0x1400454a0`

## pseudocode

```c
__int64 __fastcall Tpm20CmdGetCommandInfos(
        struct TpmTransport *this,
        unsigned int a2,
        const union _TPM20_CMD_INFO **a3)
{
  __int64 v3; // r15
  unsigned __int8 *v5; // rax
  unsigned __int8 *v6; // rdi
  int v7; // ebx
  unsigned __int8 *v8; // rsi
  unsigned int v9; // r14d
  __int64 v10; // r12
  unsigned int v11; // edx
  __int64 i; // r8
  unsigned __int32 v13; // ecx
  int v14; // r14d
  unsigned int v16; // [rsp+40h] [rbp-30h] BYREF
  _BYTE v17[22]; // [rsp+48h] [rbp-28h] BYREF
  unsigned __int64 retaddr; // [rsp+A8h] [rbp+38h]

  v3 = a2;
  memset(v17, 0, sizeof(v17));
  v16 = 4 * a2 + 19;
  v5 = TpmAlloc(1, v16, retaddr);
  v6 = v5;
  if ( v5 )
  {
    memset(v5, 0, v16);
    v8 = TpmAlloc(1, 4 * v3, retaddr);
    if ( v8 )
    {
      v9 = 0;
      v10 = 0;
      while ( 1 )
      {
        *(_WORD *)v17 = 384;
        *(_DWORD *)&v17[14] = _byteswap_ulong(v9);
        *(_QWORD *)&v17[2] = 0x7A01000016000000LL;
        *(_DWORD *)&v17[18] = _byteswap_ulong(v3 - v10);
        *(_DWORD *)&v17[10] = 0x2000000;
        v7 = TpmTransport::DispatchCommand(this, v17, 0x16u, (char *)v6, &v16, 1, 0);
        if ( v7 < 0 )
          goto LABEL_28;
        if ( v16 < 0x13
          || *(_DWORD *)(v6 + 2) != _byteswap_ulong(v16)
          || *(_WORD *)v6 != 384
          || *(_DWORD *)(v6 + 6)
          || *(_DWORD *)(v6 + 11) != 0x2000000 )
        {
          break;
        }
        v11 = _byteswap_ulong(*(_DWORD *)(v6 + 15));
        if ( v11 != (_DWORD)v3 || v16 != 4LL * v11 + 19 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_d0de2f6a14273316cf6155040bbdf5a0_Traceguids, v16);
          }
LABEL_27:
          v7 = -1073741434;
          goto LABEL_28;
        }
        for ( i = 0; (unsigned int)i < v11; v9 = v14 + 1 )
        {
          v13 = _byteswap_ulong(*(_DWORD *)&v6[4 * i + 19]);
          *(_DWORD *)&v8[4 * v10] = v13;
          if ( (v13 & 0x2000FFFF) == 0x165 )
            *(_DWORD *)&v8[4 * v10] = v13 & 0xF1FFFFFF | 0x2000000;
          v10 = (unsigned int)(v10 + 1);
          v14 = *(_DWORD *)&v6[4 * i + 19] & 0x2000FFFF;
          i = (unsigned int)(i + 1);
        }
        if ( (unsigned int)v10 >= (unsigned int)v3 || !v6[10] )
        {
          Tpm20ResourceMgr::m_CommandInfoTable = v8;
          v7 = 0;
          goto LABEL_28;
        }
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_d0de2f6a14273316cf6155040bbdf5a0_Traceguids);
      goto LABEL_27;
    }
    v7 = -1073741670;
LABEL_28:
    TpmFree(v6);
    if ( v7 < 0 && v8 )
    {
      TpmFree(v8);
      Tpm20ResourceMgr::m_CommandInfoTable = 0;
    }
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140029130  mov     [rsp-38h+arg_10], rbx
0x140029135  push    rbp
0x140029136  push    rsi
0x140029137  push    rdi
0x140029138  push    r12
0x14002913a  push    r13
0x14002913c  push    r14
0x14002913e  push    r15
0x140029140  mov     rbp, rsp
0x140029143  sub     rsp, 70h
0x140029147  mov     rax, cs:__security_cookie
0x14002914e  xor     rax, rsp
0x140029151  mov     [rbp+var_10], rax
0x140029155  mov     r8, [rbp+38h]; unsigned __int64
0x140029159  xor     eax, eax
0x14002915b  mov     r15d, edx
0x14002915e  xorps   xmm0, xmm0
0x140029161  movups  [rbp+var_28], xmm0
0x140029165  mov     qword ptr [rbp+var_28+0Eh], rax
0x140029169  mov     r13, rcx
0x14002916c  mov     cl, 1; bool
0x14002916e  lea     eax, ds:13h[r15*4]
0x140029176  mov     edx, eax; unsigned __int64
0x140029178  mov     [rbp+var_30], eax
0x14002917b  mov     ebx, eax
0x14002917d  call    ?TpmAlloc@@YAPEAE_N_K1@Z; TpmAlloc(bool,unsigned __int64,unsigned __int64)
0x140029182  mov     rdi, rax
0x140029185  test    rax, rax
0x140029188  jnz     short loc_140029194
0x14002918a  mov     ebx, 0C000009Ah
0x14002918f  jmp     loc_14002938F
0x140029194  mov     r8, rbx; Size
0x140029197  xor     edx, edx; Val
0x140029199  mov     rcx, rdi; void *
0x14002919c  call    memset
0x1400291a1  mov     r8, [rbp+38h]; unsigned __int64
0x1400291a5  mov     rdx, r15
0x1400291a8  shl     rdx, 2; unsigned __int64
0x1400291ac  mov     cl, 1; bool
0x1400291ae  call    ?TpmAlloc@@YAPEAE_N_K1@Z; TpmAlloc(bool,unsigned __int64,unsigned __int64)
0x1400291b3  mov     rsi, rax
0x1400291b6  test    rax, rax
0x1400291b9  jnz     short loc_1400291C5
0x1400291bb  mov     ebx, 0C000009Ah
0x1400291c0  jmp     loc_14002936B
0x1400291c5  xor     r14d, r14d
0x1400291c8  mov     eax, 180h
0x1400291cd  xor     r12d, r12d
0x1400291d0  mov     r10d, 2000000h
0x1400291d6  mov     word ptr [rbp+var_28], ax
0x1400291da  lea     rdx, [rbp+var_28]; void *
0x1400291de  mov     eax, r14d
0x1400291e1  mov     [rsp+70h+var_40], 0; struct TpmTransport::TpmTimeouts *
0x1400291ea  bswap   eax
0x1400291ec  mov     dword ptr [rbp+var_28+0Eh], eax
0x1400291ef  mov     r9, rdi; void *
0x1400291f2  mov     eax, r15d
0x1400291f5  mov     [rsp+70h+var_48], 1; int
0x1400291fd  sub     eax, r12d
0x140029200  mov     dword ptr [rbp+var_28+2], 16000000h
0x140029207  bswap   eax
0x140029209  mov     [rbp+var_16], eax
0x14002920c  mov     r8d, 16h; unsigned int
0x140029212  lea     rax, [rbp+var_30]
0x140029216  mov     dword ptr [rbp+var_28+6], 7A010000h
0x14002921d  mov     rcx, r13; this
0x140029220  mov     [rsp+70h+var_50], rax; unsigned int *
0x140029225  mov     dword ptr [rbp+var_28+0Ah], r10d
0x140029229  call    ?DispatchCommand@TpmTransport@@QEAAJPEAXI0PEAIHPEAVTpmTimeouts@1@@Z; TpmTransport::DispatchCommand(void *,uint,void *,uint *,int,TpmTransport::TpmTimeouts *)
0x14002922e  mov     ebx, eax
0x140029230  test    eax, eax
0x140029232  js      loc_14002936B
0x140029238  mov     r9d, [rbp+var_30]
0x14002923c  cmp     r9d, 13h
0x140029240  jb      loc_140029337
0x140029246  mov     eax, r9d
0x140029249  bswap   eax
0x14002924b  cmp     [rdi+2], eax
0x14002924e  jnz     loc_140029337
0x140029254  mov     eax, 180h
0x140029259  cmp     [rdi], ax
0x14002925c  jnz     loc_140029337
0x140029262  cmp     dword ptr [rdi+6], 0
0x140029266  jnz     loc_140029337
0x14002926c  mov     r10d, 2000000h
0x140029272  cmp     [rdi+0Bh], r10d
0x140029276  jnz     loc_140029337
0x14002927c  mov     edx, [rdi+0Fh]
0x14002927f  bswap   edx
0x140029281  cmp     edx, r15d
0x140029284  jnz     short loc_1400292FB
0x140029286  mov     eax, edx
0x140029288  lea     rcx, ds:13h[rax*4]
0x140029290  cmp     r9, rcx
0x140029293  jnz     short loc_1400292FB
0x140029295  xor     r8d, r8d
0x140029298  test    edx, edx
0x14002929a  jz      short loc_1400292DC
0x14002929c  mov     r11d, 2000FFFFh
0x1400292a2  mov     ecx, [rdi+r8*4+13h]
0x1400292a7  bswap   ecx
0x1400292a9  mov     eax, ecx
0x1400292ab  mov     [rsi+r12*4], ecx
0x1400292af  and     eax, r11d
0x1400292b2  cmp     eax, 165h
0x1400292b7  jnz     short loc_1400292C6
0x1400292b9  and     ecx, 0F3FFFFFFh
0x1400292bf  or      ecx, r10d
0x1400292c2  mov     [rsi+r12*4], ecx
0x1400292c6  mov     r14d, [rdi+r8*4+13h]
0x1400292cb  inc     r12d
0x1400292ce  and     r14d, r11d
0x1400292d1  inc     r8d
0x1400292d4  inc     r14d
0x1400292d7  cmp     r8d, edx
0x1400292da  jb      short loc_1400292A2
0x1400292dc  cmp     r12d, r15d
0x1400292df  jnb     short loc_1400292F0
0x1400292e1  cmp     byte ptr [rdi+0Ah], 0
0x1400292e5  mov     eax, 180h
0x1400292ea  jnz     loc_1400291D6
0x1400292f0  mov     cs:?m_CommandInfoTable@Tpm20ResourceMgr@@0PEBT_TPM20_CMD_INFO@@EB, rsi; _TPM20_CMD_INFO const * const Tpm20ResourceMgr::m_CommandInfoTable
0x1400292f7  xor     ebx, ebx
0x1400292f9  jmp     short loc_14002936B
0x1400292fb  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140029302  lea     rax, WPP_GLOBAL_Control
0x140029309  cmp     rcx, rax
0x14002930c  jz      short loc_140029366
0x14002930e  mov     eax, [rcx+2Ch]
0x140029311  test    al, 1
0x140029313  jz      short loc_140029366
0x140029315  mov     rcx, [rcx+18h]
0x140029319  lea     eax, ds:13h[rdx*4]
0x140029320  mov     edx, 14h
0x140029325  mov     dword ptr [rsp+70h+var_50], eax
0x140029329  lea     r8, WPP_d0de2f6a14273316cf6155040bbdf5a0_Traceguids
0x140029330  call    WPP_SF_Dd
0x140029335  jmp     short loc_140029366
0x140029337  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002933e  lea     rax, WPP_GLOBAL_Control
0x140029345  cmp     rcx, rax
0x140029348  jz      short loc_140029366
0x14002934a  mov     eax, [rcx+2Ch]
0x14002934d  test    al, 1
0x14002934f  jz      short loc_140029366
0x140029351  mov     rcx, [rcx+18h]
0x140029355  lea     r8, WPP_d0de2f6a14273316cf6155040bbdf5a0_Traceguids
0x14002935c  mov     edx, 13h
0x140029361  call    WPP_SF_
0x140029366  mov     ebx, 0C0000186h
0x14002936b  mov     rcx, rdi; void *
0x14002936e  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x140029373  test    ebx, ebx
0x140029375  jns     short loc_14002938F
0x140029377  test    rsi, rsi
0x14002937a  jz      short loc_14002938F
0x14002937c  mov     rcx, rsi; void *
0x14002937f  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x140029384  mov     cs:?m_CommandInfoTable@Tpm20ResourceMgr@@0PEBT_TPM20_CMD_INFO@@EB, 0; _TPM20_CMD_INFO const * const Tpm20ResourceMgr::m_CommandInfoTable
0x14002938f  mov     eax, ebx
0x140029391  mov     rcx, [rbp+var_10]
0x140029395  xor     rcx, rsp; StackCookie
0x140029398  call    __security_check_cookie
0x14002939d  mov     rbx, [rsp+70h+arg_10]
0x1400293a5  add     rsp, 70h
0x1400293a9  pop     r15
0x1400293ab  pop     r14
0x1400293ad  pop     r13
0x1400293af  pop     r12
0x1400293b1  pop     rdi
0x1400293b2  pop     rsi
0x1400293b3  pop     rbp
0x1400293b4  retn
```
