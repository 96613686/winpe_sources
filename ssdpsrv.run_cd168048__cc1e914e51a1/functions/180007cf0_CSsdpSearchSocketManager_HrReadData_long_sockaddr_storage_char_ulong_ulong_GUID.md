# CSsdpSearchSocketManager::HrReadData(long,sockaddr_storage *,char * *,ulong *,ulong *,_GUID *)

- ea: `0x180007cf0`
- end: `0x180008189`
- name: `?HrReadData@CSsdpSearchSocketManager@@QEAAJJPEAUsockaddr_storage@@PEAPEADPEAK2PEAU_GUID@@@Z`
- size: `1177`
- prototype: `int(CSsdpSearchSocketManager *__hidden this, int, struct sockaddr_storage *, char **, unsigned int *, unsigned int *, struct _GUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800070d0`

## callees

- `0x180001da0`
- `0x180002080`
- `0x180007cf0`
- `0x1800271fc`
- `0x180029df0`
- `0x18002e8ac`
- `0x1800312cc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007eb0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007f8a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800080b8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007eb0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007f8a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800080b8`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180007e24`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180007e24`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007d4f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007da1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007d4f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007da1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007d2c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007d3c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007d2c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007d3c`
- `WS2_32!__imp_ioctlsocket` at `0x180007de0`
- `WS2_32!__imp_ioctlsocket` at `0x180007de0`
- `WS2_32!__imp_WSAGetLastError` at `0x180007fe9`
- `WS2_32!__imp_WSAGetLastError` at `0x1800080c4`
- `WS2_32!__imp_WSAGetLastError` at `0x180007fe9`
- `WS2_32!__imp_WSAGetLastError` at `0x1800080c4`
- `WS2_32!__imp___WSAFDIsSet` at `0x180007d88`
- `WS2_32!__imp___WSAFDIsSet` at `0x180007d88`

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
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_43b979ca869a37ed9d5f3367dd3407bf_Traceguids);
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
0x180007cf0  mov     rax, rsp
0x180007cf3  mov     [rax+18h], rbx
0x180007cf7  push    rbp
0x180007cf8  push    rsi
0x180007cf9  push    rdi
0x180007cfa  push    r12
0x180007cfc  push    r13
0x180007cfe  push    r14
0x180007d00  push    r15
0x180007d02  sub     rsp, 60h
0x180007d06  xor     r13d, r13d
0x180007d09  movsxd  rbp, edx
0x180007d0c  mov     rsi, rcx
0x180007d0f  mov     [rax+10h], r13d
0x180007d13  add     rcx, 8; lpCriticalSection
0x180007d17  mov     [rax+8], r13d
0x180007d1b  mov     [rax-48h], r13d
0x180007d1f  mov     r12, r9
0x180007d22  mov     r15, r8
0x180007d25  mov     dword ptr [rax-44h], 80h
0x180007d2c  call    cs:__imp_EnterCriticalSection
0x180007d33  nop     dword ptr [rax+rax+00h]
0x180007d38  lea     rcx, [rsi+8]; lpCriticalSection
0x180007d3c  call    cs:__imp_EnterCriticalSection
0x180007d43  nop     dword ptr [rax+rax+00h]
0x180007d48  mov     edi, [rsi+38h]
0x180007d4b  lea     rcx, [rsi+8]; lpCriticalSection
0x180007d4f  call    cs:__imp_LeaveCriticalSection
0x180007d56  nop     dword ptr [rax+rax+00h]
0x180007d5b  cmp     ebp, edi
0x180007d5d  jge     loc_18000802C
0x180007d63  mov     rax, [rsi+30h]
0x180007d67  lea     rdx, [rsi+58h]; fd_set *
0x180007d6b  mov     r14, rbp
0x180007d6e  mov     rbp, [rsp+98h+arg_30]
0x180007d76  shl     r14, 5
0x180007d7a  movups  xmm0, xmmword ptr [r14+rax+8]
0x180007d80  mov     rcx, [r14+rax]; fd
0x180007d84  movups  xmmword ptr [rbp+0], xmm0
0x180007d88  call    cs:__imp___WSAFDIsSet
0x180007d8f  nop     dword ptr [rax+rax+00h]
0x180007d94  test    eax, eax
0x180007d96  jnz     short loc_180007DC8
0x180007d98  mov     edi, 80070015h
0x180007d9d  lea     rcx, [rsi+8]; lpCriticalSection
0x180007da1  call    cs:__imp_LeaveCriticalSection
0x180007da8  nop     dword ptr [rax+rax+00h]
0x180007dad  mov     rbx, [rsp+98h+arg_10]
0x180007db5  mov     eax, edi
0x180007db7  add     rsp, 60h
0x180007dbb  pop     r15
0x180007dbd  pop     r14
0x180007dbf  pop     r13
0x180007dc1  pop     r12
0x180007dc3  pop     rdi
0x180007dc4  pop     rsi
0x180007dc5  pop     rbp
0x180007dc6  retn
0x180007dc8  mov     rcx, [rsi+30h]
0x180007dcc  lea     r8, [rsp+98h+argp]; argp
0x180007dd4  mov     edx, 4004667Fh; cmd
0x180007dd9  mov     edi, r13d
0x180007ddc  mov     rcx, [r14+rcx]; s
0x180007de0  call    cs:__imp_ioctlsocket
0x180007de7  nop     dword ptr [rax+rax+00h]
0x180007dec  test    eax, eax
0x180007dee  jnz     loc_180007FE9
0x180007df4  mov     r13d, [rsp+98h+argp]
0x180007dfc  test    r13d, r13d
0x180007dff  jz      short loc_180007D98
0x180007e01  test    edi, edi
0x180007e03  jns     short loc_180007E20
0x180007e05  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e0c  lea     rbp, WPP_GLOBAL_Control
0x180007e13  cmp     edi, 80070015h
0x180007e19  jz      short loc_180007D9D
0x180007e1b  jmp     loc_180007F78
0x180007e20  lea     ecx, [r13+1]; Size
0x180007e24  call    cs:__imp_malloc
0x180007e2b  nop     dword ptr [rax+rax+00h]
0x180007e30  mov     [rsp+98h+Block], rax
0x180007e35  test    rax, rax
0x180007e38  jz      loc_180008044
0x180007e3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e45  lea     rax, WPP_GLOBAL_Control
0x180007e4c  cmp     rcx, rax
0x180007e4f  jz      short loc_180007E5B
0x180007e51  test    byte ptr [rcx+1Ch], 8
0x180007e55  jnz     loc_18000808E
0x180007e5b  mov     rcx, [rsi+30h]
0x180007e5f  lea     rax, [rsp+98h+var_48]
0x180007e64  mov     r8, [rsp+98h+Block]; char *
0x180007e69  mov     r9d, r13d; int
0x180007e6c  mov     [rsp+98h+var_58], rax; int *
0x180007e71  lea     rax, [rsp+98h+arg_0]
0x180007e79  mov     [rsp+98h+var_60], rax; unsigned int *
0x180007e7e  lea     rax, [rsp+98h+var_44]
0x180007e83  mov     rcx, [r14+rcx]; unsigned __int64
0x180007e87  mov     [rsp+98h+var_68], rax; int *
0x180007e8c  mov     [rsp+98h+var_70], r15; struct sockaddr *
0x180007e91  call    ?RecvFromWithIfIndex@@YAH_KHPEADHHPEAUsockaddr@@PEAHPEAK3@Z; RecvFromWithIfIndex(unsigned __int64,int,char *,int,int,sockaddr *,int *,ulong *,int *)
0x180007e96  mov     r13d, eax
0x180007e99  cmp     eax, 0FFFFFFFFh
0x180007e9c  jz      loc_1800080B3
0x180007ea2  cmp     r13d, 2000h
0x180007ea9  jbe     short loc_180007F08
0x180007eab  mov     rcx, [rsp+98h+Block]; Block
0x180007eb0  call    cs:__imp_free
0x180007eb7  nop     dword ptr [rax+rax+00h]
0x180007ebc  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ec3  lea     rbp, WPP_GLOBAL_Control
0x180007eca  cmp     rcx, rbp
0x180007ecd  jnz     loc_180007FBE
0x180007ed3  mov     edi, 80004005h
0x180007ed8  cmp     rcx, rbp
0x180007edb  jz      loc_180007D9D
0x180007ee1  test    byte ptr [rcx+1Ch], 1
0x180007ee5  jz      loc_180007D9D
0x180007eeb  mov     rcx, [rcx+10h]
0x180007eef  lea     r8, WPP_43b979ca869a37ed9d5f3367dd3407bf_Traceguids
0x180007ef6  mov     edx, 1Fh
0x180007efb  mov     r9d, edi
0x180007efe  call    WPP_SF_d
0x180007f03  jmp     loc_180007D9D
0x180007f08  cmp     r13d, [rsp+98h+argp]
0x180007f10  ja      short loc_180007EAB
0x180007f12  mov     rcx, r15; struct sockaddr *
0x180007f15  call    ?TestSourceAddress@@YAHPEAUsockaddr@@@Z; TestSourceAddress(sockaddr *)
0x180007f1a  test    eax, eax
0x180007f1c  jz      short loc_180007F85
0x180007f1e  mov     r8, [rsp+98h+Block]
0x180007f23  mov     rax, [rsp+98h+arg_20]
0x180007f2b  mov     ecx, [rsp+98h+arg_0]
0x180007f32  mov     [r12], r8
0x180007f36  mov     byte ptr [r13+r8+0], 0
0x180007f3c  mov     rdx, [rsi+30h]
0x180007f40  mov     [rax], ecx
0x180007f42  mov     rax, [rsp+98h+arg_28]
0x180007f4a  movups  xmm0, xmmword ptr [rdx+r14+8]
0x180007f50  mov     ecx, [rdx+r14+1Ch]
0x180007f55  mov     [rax], ecx
0x180007f57  movups  xmmword ptr [rbp+0], xmm0
0x180007f5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f62  lea     rbp, WPP_GLOBAL_Control
0x180007f69  cmp     rcx, rbp
0x180007f6c  jz      short loc_180007F78
0x180007f6e  test    byte ptr [rcx+1Ch], 4
0x180007f72  jnz     loc_180008160
0x180007f78  test    edi, edi
0x180007f7a  jz      loc_180007D9D
0x180007f80  jmp     loc_180007ED8
0x180007f85  mov     rcx, [rsp+98h+Block]; Block
0x180007f8a  call    cs:__imp_free
0x180007f91  nop     dword ptr [rax+rax+00h]
0x180007f96  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f9d  lea     rbp, WPP_GLOBAL_Control
0x180007fa4  cmp     rcx, rbp
0x180007fa7  jz      loc_180007ED3
0x180007fad  test    byte ptr [rcx+1Ch], 8
0x180007fb1  jz      loc_180007ED3
0x180007fb7  mov     edx, 1Dh
0x180007fbc  jmp     short loc_180007FCD
0x180007fbe  test    byte ptr [rcx+1Ch], 8
0x180007fc2  jz      loc_180007ED3
0x180007fc8  mov     edx, 1Ch
0x180007fcd  mov     rcx, [rcx+10h]
0x180007fd1  lea     r8, WPP_43b979ca869a37ed9d5f3367dd3407bf_Traceguids
0x180007fd8  call    WPP_SF_
0x180007fdd  mov     rcx, cs:WPP_GLOBAL_Control
0x180007fe4  jmp     loc_180007ED3
0x180007fe9  call    cs:__imp_WSAGetLastError
0x180007ff0  nop     dword ptr [rax+rax+00h]
0x180007ff5  mov     edi, eax
0x180007ff7  test    eax, eax
0x180007ff9  jle     loc_180007DF4
0x180007fff  movzx   edi, ax
0x180008002  or      edi, 80070000h
0x180008008  jmp     loc_180007DF4
0x18000800d  test    edi, edi
0x18000800f  jle     short loc_18000801C
0x180008011  movzx   edi, di
0x180008014  or      edi, 80070000h
0x18000801a  test    edi, edi
0x18000801c  js      loc_180007E13
0x180008022  mov     edi, 80004005h
0x180008027  jmp     loc_180007ED8
0x18000802c  mov     rcx, cs:WPP_GLOBAL_Control
0x180008033  lea     rbp, WPP_GLOBAL_Control
0x18000803a  mov     edi, 80070057h
0x18000803f  jmp     loc_180007ED8
0x180008044  mov     edi, 8007000Eh
0x180008049  mov     rcx, cs:WPP_GLOBAL_Control
0x180008050  lea     rbp, WPP_GLOBAL_Control
0x180008057  cmp     rcx, rbp
0x18000805a  jz      loc_180007D9D
0x180008060  test    byte ptr [rcx+1Ch], 1
0x180008064  jz      loc_180007ED8
0x18000806a  mov     rcx, [rcx+10h]
0x18000806e  lea     r8, WPP_43b979ca869a37ed9d5f3367dd3407bf_Traceguids
0x180008075  mov     edx, 18h
0x18000807a  mov     r9d, edi
0x18000807d  call    WPP_SF_d
0x180008082  mov     rcx, cs:WPP_GLOBAL_Control
0x180008089  jmp     loc_180007ED8
0x18000808e  mov     rcx, [rcx+10h]
0x180008092  lea     r8, WPP_43b979ca869a37ed9d5f3367dd3407bf_Traceguids
0x180008099  mov     edx, 19h
0x18000809e  mov     r9, rsi
0x1800080a1  call    WPP_SF_q
0x1800080a6  mov     r13d, [rsp+98h+argp]
0x1800080ae  jmp     loc_180007E5B
0x1800080b3  mov     rcx, [rsp+98h+Block]; Block
0x1800080b8  call    cs:__imp_free
0x1800080bf  nop     dword ptr [rax+rax+00h]
0x1800080c4  call    cs:__imp_WSAGetLastError
0x1800080cb  nop     dword ptr [rax+rax+00h]
0x1800080d0  mov     edi, eax
0x1800080d2  cmp     eax, 2746h
0x1800080d7  jnz     short loc_18000811B
0x1800080d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800080e0  lea     rbp, WPP_GLOBAL_Control
0x1800080e7  cmp     rcx, rbp
0x1800080ea  jz      loc_180008011
0x1800080f0  test    byte ptr [rcx+1Ch], 1
0x1800080f4  jz      loc_180008011
0x1800080fa  mov     rcx, [rcx+10h]
0x1800080fe  lea     r8, WPP_43b979ca869a37ed9d5f3367dd3407bf_Traceguids
0x180008105  mov     edx, 1Ah
0x18000810a  call    WPP_SF_
0x18000810f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008116  jmp     loc_180008011
0x18000811b  mov     rcx, cs:WPP_GLOBAL_Control
0x180008122  lea     rbp, WPP_GLOBAL_Control
0x180008129  cmp     rcx, rbp
0x18000812c  jz      loc_18000800D
0x180008132  test    byte ptr [rcx+1Ch], 1
0x180008136  jz      loc_18000800D
0x18000813c  mov     rcx, [rcx+10h]
0x180008140  lea     r8, WPP_43b979ca869a37ed9d5f3367dd3407bf_Traceguids
0x180008147  mov     edx, 1Bh
0x18000814c  mov     r9d, edi
0x18000814f  call    WPP_SF_d
0x180008154  mov     rcx, cs:WPP_GLOBAL_Control
0x18000815b  jmp     loc_18000800D
0x180008160  mov     rcx, [rcx+10h]
0x180008164  mov     edx, 1Eh
0x180008169  mov     [rsp+98h+var_78], r8
0x18000816e  mov     r9, rsi
0x180008171  lea     r8, WPP_43b979ca869a37ed9d5f3367dd3407bf_Traceguids
0x180008178  call    WPP_SF_qs
0x18000817d  mov     rcx, cs:WPP_GLOBAL_Control
0x180008184  jmp     loc_180007F78
```
