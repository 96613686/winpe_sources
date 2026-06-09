# CSsdpSearchSocketManager::HrReadData(long,sockaddr_storage *,char * *,ulong *,ulong *,_GUID *)

- ea: `0x180006910`
- end: `0x180006d60`
- name: `?HrReadData@CSsdpSearchSocketManager@@QEAAJJPEAUsockaddr_storage@@PEAPEADPEAK2PEAU_GUID@@@Z`
- size: `1104`
- prototype: `__int64 __fastcall(CSsdpSearchSocketManager *this, int, struct sockaddr *, char **, unsigned int *, unsigned int *, struct _GUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180005d90`

## callees

- `0x180006910`
- `0x180017bd0`
- `0x180017e90`
- `0x1800255a8`
- `0x180028000`
- `0x18002c8cc`
- `0x18002f078`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180006aa5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180006b79`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180006c9b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180006aa5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180006b79`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180006c9b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180006a1f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180006a1f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006963`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800069a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006963`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800069a9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000694c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006956`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000694c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006956`
- `WS2_32!__imp_ioctlsocket` at `0x1800069e1`
- `WS2_32!__imp_ioctlsocket` at `0x1800069e1`
- `WS2_32!__imp_WSAGetLastError` at `0x180006bd2`
- `WS2_32!__imp_WSAGetLastError` at `0x180006ca1`
- `WS2_32!__imp_WSAGetLastError` at `0x180006bd2`
- `WS2_32!__imp_WSAGetLastError` at `0x180006ca1`
- `WS2_32!__imp___WSAFDIsSet` at `0x180006996`
- `WS2_32!__imp___WSAFDIsSet` at `0x180006996`

## pseudocode

```c
__int64 __fastcall CSsdpSearchSocketManager::HrReadData(
        CSsdpSearchSocketManager *this,
        int a2,
        struct sockaddr *a3,
        char **a4,
        unsigned int *a5,
        unsigned int *a6,
        struct _GUID *a7)
{
  __int64 v7; // rbp
  int v11; // edi
  __int64 v12; // rax
  __int64 v13; // r14
  struct _GUID *v14; // rbp
  __int64 v15; // r14
  SOCKET v16; // rcx
  signed int v17; // edi
  u_long v19; // r13d
  LPCSTR v20; // rcx
  int v21; // edx
  u_long v22; // eax
  __int64 v23; // r13
  _BYTE *v24; // r8
  unsigned int *v25; // rax
  unsigned int v26; // ecx
  __int64 v27; // rdx
  struct _GUID v28; // xmm0
  __int64 v29; // rdx
  int Error; // eax
  bool v31; // sf
  unsigned int v32; // eax
  int v33; // [rsp+20h] [rbp-78h]
  int v34; // [rsp+50h] [rbp-48h] BYREF
  int v35; // [rsp+54h] [rbp-44h] BYREF
  void *Block; // [rsp+58h] [rbp-40h]
  unsigned int v37; // [rsp+A0h] [rbp+8h] BYREF
  u_long argp; // [rsp+A8h] [rbp+10h] BYREF

  v7 = a2;
  argp = 0;
  v37 = 0;
  v34 = 0;
  v35 = 128;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v11 = *((_DWORD *)this + 14);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( (int)v7 >= v11 )
  {
    v20 = WPP_GLOBAL_Control;
    v17 = -2147024809;
    goto LABEL_19;
  }
  v12 = *((_QWORD *)this + 6);
  v13 = v7;
  v14 = a7;
  v15 = 32 * v13;
  v16 = *(_QWORD *)(v15 + v12);
  *a7 = *(struct _GUID *)(v15 + v12 + 8);
  if ( !__WSAFDIsSet(v16, (fd_set *)((char *)this + 88)) )
    goto LABEL_3;
  v17 = 0;
  if ( ioctlsocket(*(_QWORD *)(v15 + *((_QWORD *)this + 6)), 1074030207, &argp) )
  {
    Error = WSAGetLastError();
    v17 = Error;
    if ( Error > 0 )
      v17 = (unsigned __int16)Error | 0x80070000;
  }
  v19 = argp;
  if ( !argp )
  {
LABEL_3:
    v17 = -2147024875;
    goto LABEL_4;
  }
  if ( v17 < 0 )
  {
    v20 = WPP_GLOBAL_Control;
    goto LABEL_9;
  }
  Block = malloc(argp + 1);
  if ( !Block )
  {
    v17 = -2147024882;
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control )
      goto LABEL_4;
    if ( (WPP_GLOBAL_Control[28] & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_43b979ca869a37ed9d5f3367dd3407bf_Traceguids, 2147942414LL);
      v20 = WPP_GLOBAL_Control;
    }
    goto LABEL_19;
  }
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_43b979ca869a37ed9d5f3367dd3407bf_Traceguids, this);
    v19 = argp;
  }
  v22 = RecvFromWithIfIndex(
          *(_QWORD *)(v15 + *((_QWORD *)this + 6)),
          v21,
          (char *)Block,
          v19,
          v33,
          a3,
          &v35,
          &v37,
          &v34);
  v23 = v22;
  if ( v22 != -1 )
  {
    if ( v22 > 0x2000 || v22 > argp )
    {
      free(Block);
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 8) == 0 )
        goto LABEL_18;
      v29 = 28;
    }
    else
    {
      if ( (unsigned int)TestSourceAddress(a3) )
      {
        v24 = Block;
        v25 = a5;
        v26 = v37;
        *a4 = (char *)Block;
        v24[v23] = 0;
        v27 = *((_QWORD *)this + 6);
        *v25 = v26;
        v28 = *(struct _GUID *)(v27 + v15 + 8);
        *a6 = *(_DWORD *)(v27 + v15 + 28);
        *v14 = v28;
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 4) != 0 )
        {
          WPP_SF_qs(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            30,
            (unsigned int)WPP_43b979ca869a37ed9d5f3367dd3407bf_Traceguids,
            (_DWORD)this,
            (__int64)v24);
          v20 = WPP_GLOBAL_Control;
        }
LABEL_27:
        if ( !v17 )
          goto LABEL_4;
        goto LABEL_19;
      }
      free(Block);
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 8) == 0 )
        goto LABEL_18;
      v29 = 29;
    }
    WPP_SF_(*((_QWORD *)v20 + 2), v29, WPP_43b979ca869a37ed9d5f3367dd3407bf_Traceguids);
    v20 = WPP_GLOBAL_Control;
LABEL_18:
    v17 = -2147467259;
    goto LABEL_19;
  }
  free(Block);
  v32 = WSAGetLastError();
  v17 = v32;
  if ( v32 == 10054 )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_43b979ca869a37ed9d5f3367dd3407bf_Traceguids);
      v20 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_43b979ca869a37ed9d5f3367dd3407bf_Traceguids, v32);
      v20 = WPP_GLOBAL_Control;
    }
    v31 = v17 < 0;
    if ( v17 <= 0 )
      goto LABEL_39;
  }
  v17 = (unsigned __int16)v17 | 0x80070000;
  v31 = v17 < 0;
LABEL_39:
  if ( v31 )
  {
LABEL_9:
    if ( v17 == -2147024875 )
      goto LABEL_4;
    goto LABEL_27;
  }
  v17 = -2147467259;
LABEL_19:
  if ( v20 != (LPCSTR)&WPP_GLOBAL_Control && (v20[28] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)v20 + 2), 31, WPP_43b979ca869a37ed9d5f3367dd3407bf_Traceguids, (unsigned int)v17);
LABEL_4:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180006910  mov     rax, rsp
0x180006913  mov     [rax+18h], rbx
0x180006917  push    rbp
0x180006918  push    rsi
0x180006919  push    rdi
0x18000691a  push    r12
0x18000691c  push    r13
0x18000691e  push    r14
0x180006920  push    r15
0x180006922  sub     rsp, 60h
0x180006926  xor     r13d, r13d
0x180006929  movsxd  rbp, edx
0x18000692c  mov     rsi, rcx
0x18000692f  mov     [rax+10h], r13d
0x180006933  add     rcx, 8; lpCriticalSection
0x180006937  mov     [rax+8], r13d
0x18000693b  mov     [rax-48h], r13d
0x18000693f  mov     r12, r9
0x180006942  mov     r15, r8
0x180006945  mov     dword ptr [rax-44h], 80h
0x18000694c  call    cs:__imp_EnterCriticalSection
0x180006952  lea     rcx, [rsi+8]; lpCriticalSection
0x180006956  call    cs:__imp_EnterCriticalSection
0x18000695c  mov     edi, [rsi+38h]
0x18000695f  lea     rcx, [rsi+8]; lpCriticalSection
0x180006963  call    cs:__imp_LeaveCriticalSection
0x180006969  cmp     ebp, edi
0x18000696b  jge     loc_180006C0F
0x180006971  mov     rax, [rsi+30h]
0x180006975  lea     rdx, [rsi+58h]; fd_set *
0x180006979  mov     r14, rbp
0x18000697c  mov     rbp, [rsp+98h+arg_30]
0x180006984  shl     r14, 5
0x180006988  movups  xmm0, xmmword ptr [r14+rax+8]
0x18000698e  mov     rcx, [r14+rax]; fd
0x180006992  movups  xmmword ptr [rbp+0], xmm0
0x180006996  call    cs:__imp___WSAFDIsSet
0x18000699c  test    eax, eax
0x18000699e  jnz     short loc_1800069C9
0x1800069a0  mov     edi, 80070015h
0x1800069a5  lea     rcx, [rsi+8]; lpCriticalSection
0x1800069a9  call    cs:__imp_LeaveCriticalSection
0x1800069af  mov     rbx, [rsp+98h+arg_10]
0x1800069b7  mov     eax, edi
0x1800069b9  add     rsp, 60h
0x1800069bd  pop     r15
0x1800069bf  pop     r14
0x1800069c1  pop     r13
0x1800069c3  pop     r12
0x1800069c5  pop     rdi
0x1800069c6  pop     rsi
0x1800069c7  pop     rbp
0x1800069c8  retn
0x1800069c9  mov     rcx, [rsi+30h]
0x1800069cd  lea     r8, [rsp+98h+argp]; argp
0x1800069d5  mov     edx, 4004667Fh; cmd
0x1800069da  mov     edi, r13d
0x1800069dd  mov     rcx, [r14+rcx]; s
0x1800069e1  call    cs:__imp_ioctlsocket
0x1800069e7  test    eax, eax
0x1800069e9  jnz     loc_180006BD2
0x1800069ef  mov     r13d, [rsp+98h+argp]
0x1800069f7  test    r13d, r13d
0x1800069fa  jz      short loc_1800069A0
0x1800069fc  test    edi, edi
0x1800069fe  jns     short loc_180006A1B
0x180006a00  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a07  lea     rbp, WPP_GLOBAL_Control
0x180006a0e  cmp     edi, 80070015h
0x180006a14  jz      short loc_1800069A5
0x180006a16  jmp     loc_180006B67
0x180006a1b  lea     ecx, [r13+1]; Size
0x180006a1f  call    cs:__imp_malloc
0x180006a25  mov     [rsp+98h+Block], rax
0x180006a2a  test    rax, rax
0x180006a2d  jz      loc_180006C27
0x180006a33  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a3a  lea     rax, WPP_GLOBAL_Control
0x180006a41  cmp     rcx, rax
0x180006a44  jz      short loc_180006A50
0x180006a46  test    byte ptr [rcx+1Ch], 8
0x180006a4a  jnz     loc_180006C71
0x180006a50  mov     rcx, [rsi+30h]
0x180006a54  lea     rax, [rsp+98h+var_48]
0x180006a59  mov     r8, [rsp+98h+Block]; char *
0x180006a5e  mov     r9d, r13d; int
0x180006a61  mov     [rsp+98h+var_58], rax; int *
0x180006a66  lea     rax, [rsp+98h+arg_0]
0x180006a6e  mov     [rsp+98h+var_60], rax; unsigned int *
0x180006a73  lea     rax, [rsp+98h+var_44]
0x180006a78  mov     rcx, [r14+rcx]; unsigned __int64
0x180006a7c  mov     [rsp+98h+var_68], rax; int *
0x180006a81  mov     [rsp+98h+var_70], r15; struct sockaddr *
0x180006a86  call    ?RecvFromWithIfIndex@@YAH_KHPEADHHPEAUsockaddr@@PEAHPEAK3@Z; RecvFromWithIfIndex(unsigned __int64,int,char *,int,int,sockaddr *,int *,ulong *,int *)
0x180006a8b  mov     r13d, eax
0x180006a8e  cmp     eax, 0FFFFFFFFh
0x180006a91  jz      loc_180006C96
0x180006a97  cmp     r13d, 2000h
0x180006a9e  jbe     short loc_180006AF7
0x180006aa0  mov     rcx, [rsp+98h+Block]; Block
0x180006aa5  call    cs:__imp_free
0x180006aab  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ab2  lea     rbp, WPP_GLOBAL_Control
0x180006ab9  cmp     rcx, rbp
0x180006abc  jnz     loc_180006BA7
0x180006ac2  mov     edi, 80004005h
0x180006ac7  cmp     rcx, rbp
0x180006aca  jz      loc_1800069A5
0x180006ad0  test    byte ptr [rcx+1Ch], 1
0x180006ad4  jz      loc_1800069A5
0x180006ada  mov     rcx, [rcx+10h]
0x180006ade  lea     r8, WPP_43b979ca869a37ed9d5f3367dd3407bf_Traceguids
0x180006ae5  mov     edx, 1Fh
0x180006aea  mov     r9d, edi
0x180006aed  call    WPP_SF_d
0x180006af2  jmp     loc_1800069A5
0x180006af7  cmp     r13d, [rsp+98h+argp]
0x180006aff  ja      short loc_180006AA0
0x180006b01  mov     rcx, r15; struct sockaddr *
0x180006b04  call    ?TestSourceAddress@@YAHPEAUsockaddr@@@Z; TestSourceAddress(sockaddr *)
0x180006b09  test    eax, eax
0x180006b0b  jz      short loc_180006B74
0x180006b0d  mov     r8, [rsp+98h+Block]
0x180006b12  mov     rax, [rsp+98h+arg_20]
0x180006b1a  mov     ecx, [rsp+98h+arg_0]
0x180006b21  mov     [r12], r8
0x180006b25  mov     byte ptr [r13+r8+0], 0
0x180006b2b  mov     rdx, [rsi+30h]
0x180006b2f  mov     [rax], ecx
0x180006b31  mov     rax, [rsp+98h+arg_28]
0x180006b39  movups  xmm0, xmmword ptr [rdx+r14+8]
0x180006b3f  mov     ecx, [rdx+r14+1Ch]
0x180006b44  mov     [rax], ecx
0x180006b46  movups  xmmword ptr [rbp+0], xmm0
0x180006b4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b51  lea     rbp, WPP_GLOBAL_Control
0x180006b58  cmp     rcx, rbp
0x180006b5b  jz      short loc_180006B67
0x180006b5d  test    byte ptr [rcx+1Ch], 4
0x180006b61  jnz     loc_180006D37
0x180006b67  test    edi, edi
0x180006b69  jz      loc_1800069A5
0x180006b6f  jmp     loc_180006AC7
0x180006b74  mov     rcx, [rsp+98h+Block]; Block
0x180006b79  call    cs:__imp_free
0x180006b7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b86  lea     rbp, WPP_GLOBAL_Control
0x180006b8d  cmp     rcx, rbp
0x180006b90  jz      loc_180006AC2
0x180006b96  test    byte ptr [rcx+1Ch], 8
0x180006b9a  jz      loc_180006AC2
0x180006ba0  mov     edx, 1Dh
0x180006ba5  jmp     short loc_180006BB6
0x180006ba7  test    byte ptr [rcx+1Ch], 8
0x180006bab  jz      loc_180006AC2
0x180006bb1  mov     edx, 1Ch
0x180006bb6  mov     rcx, [rcx+10h]
0x180006bba  lea     r8, WPP_43b979ca869a37ed9d5f3367dd3407bf_Traceguids
0x180006bc1  call    WPP_SF_
0x180006bc6  mov     rcx, cs:WPP_GLOBAL_Control
0x180006bcd  jmp     loc_180006AC2
0x180006bd2  call    cs:__imp_WSAGetLastError
0x180006bd8  mov     edi, eax
0x180006bda  test    eax, eax
0x180006bdc  jle     loc_1800069EF
0x180006be2  movzx   edi, ax
0x180006be5  or      edi, 80070000h
0x180006beb  jmp     loc_1800069EF
0x180006bf0  test    edi, edi
0x180006bf2  jle     short loc_180006BFF
0x180006bf4  movzx   edi, di
0x180006bf7  or      edi, 80070000h
0x180006bfd  test    edi, edi
0x180006bff  js      loc_180006A0E
0x180006c05  mov     edi, 80004005h
0x180006c0a  jmp     loc_180006AC7
0x180006c0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006c16  lea     rbp, WPP_GLOBAL_Control
0x180006c1d  mov     edi, 80070057h
0x180006c22  jmp     loc_180006AC7
0x180006c27  mov     edi, 8007000Eh
0x180006c2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006c33  lea     rbp, WPP_GLOBAL_Control
0x180006c3a  cmp     rcx, rbp
0x180006c3d  jz      loc_1800069A5
0x180006c43  test    byte ptr [rcx+1Ch], 1
0x180006c47  jz      loc_180006AC7
0x180006c4d  mov     rcx, [rcx+10h]
0x180006c51  lea     r8, WPP_43b979ca869a37ed9d5f3367dd3407bf_Traceguids
0x180006c58  mov     edx, 18h
0x180006c5d  mov     r9d, edi
0x180006c60  call    WPP_SF_d
0x180006c65  mov     rcx, cs:WPP_GLOBAL_Control
0x180006c6c  jmp     loc_180006AC7
0x180006c71  mov     rcx, [rcx+10h]
0x180006c75  lea     r8, WPP_43b979ca869a37ed9d5f3367dd3407bf_Traceguids
0x180006c7c  mov     edx, 19h
0x180006c81  mov     r9, rsi
0x180006c84  call    WPP_SF_q
0x180006c89  mov     r13d, [rsp+98h+argp]
0x180006c91  jmp     loc_180006A50
0x180006c96  mov     rcx, [rsp+98h+Block]; Block
0x180006c9b  call    cs:__imp_free
0x180006ca1  call    cs:__imp_WSAGetLastError
0x180006ca7  mov     edi, eax
0x180006ca9  cmp     eax, 2746h
0x180006cae  jnz     short loc_180006CF2
0x180006cb0  mov     rcx, cs:WPP_GLOBAL_Control
0x180006cb7  lea     rbp, WPP_GLOBAL_Control
0x180006cbe  cmp     rcx, rbp
0x180006cc1  jz      loc_180006BF4
0x180006cc7  test    byte ptr [rcx+1Ch], 1
0x180006ccb  jz      loc_180006BF4
0x180006cd1  mov     rcx, [rcx+10h]
0x180006cd5  lea     r8, WPP_43b979ca869a37ed9d5f3367dd3407bf_Traceguids
0x180006cdc  mov     edx, 1Ah
0x180006ce1  call    WPP_SF_
0x180006ce6  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ced  jmp     loc_180006BF4
0x180006cf2  mov     rcx, cs:WPP_GLOBAL_Control
0x180006cf9  lea     rbp, WPP_GLOBAL_Control
0x180006d00  cmp     rcx, rbp
0x180006d03  jz      loc_180006BF0
0x180006d09  test    byte ptr [rcx+1Ch], 1
0x180006d0d  jz      loc_180006BF0
0x180006d13  mov     rcx, [rcx+10h]
0x180006d17  lea     r8, WPP_43b979ca869a37ed9d5f3367dd3407bf_Traceguids
0x180006d1e  mov     edx, 1Bh
0x180006d23  mov     r9d, edi
0x180006d26  call    WPP_SF_d
0x180006d2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d32  jmp     loc_180006BF0
0x180006d37  mov     rcx, [rcx+10h]
0x180006d3b  mov     edx, 1Eh
0x180006d40  mov     [rsp+98h+var_78], r8
0x180006d45  mov     r9, rsi
0x180006d48  lea     r8, WPP_43b979ca869a37ed9d5f3367dd3407bf_Traceguids
0x180006d4f  call    WPP_SF_qs
0x180006d54  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d5b  jmp     loc_180006B67
```
