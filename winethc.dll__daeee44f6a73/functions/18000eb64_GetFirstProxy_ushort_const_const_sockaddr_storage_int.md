# GetFirstProxy(ushort const * const,sockaddr_storage *,int *)

- ea: `0x18000eb64`
- end: `0x18000f0e3`
- name: `?GetFirstProxy@@YAJQEBGPEAUsockaddr_storage@@PEAH@Z`
- size: `1407`
- prototype: `__int64 __fastcall(const unsigned __int16 *const, struct sockaddr_storage *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180009528`

## callees

- `0x18000eb64`
- `0x18000f0ec`
- `0x180012d6e`
- `0x180012db0`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000ee25`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000ef69`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000ee25`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000ef69`
- `WS2_32!__imp_bind` at `0x18000ed9c`
- `WS2_32!__imp_bind` at `0x18000ed9c`
- `WS2_32!__imp_closesocket` at `0x18000ede7`
- `WS2_32!__imp_closesocket` at `0x18000ef44`
- `WS2_32!__imp_closesocket` at `0x18000efa5`
- `WS2_32!__imp_closesocket` at `0x18000ede7`
- `WS2_32!__imp_closesocket` at `0x18000ef44`
- `WS2_32!__imp_closesocket` at `0x18000efa5`
- `WS2_32!__imp_connect` at `0x18000edb9`
- `WS2_32!__imp_connect` at `0x18000edb9`
- `WS2_32!__imp_ioctlsocket` at `0x18000ed75`
- `WS2_32!__imp_ioctlsocket` at `0x18000ed75`
- `WS2_32!__imp_select` at `0x18000eedb`
- `WS2_32!__imp_select` at `0x18000eedb`
- `WS2_32!__imp_socket` at `0x18000ed43`
- `WS2_32!__imp_socket` at `0x18000ed43`
- `WS2_32!__imp_WSAGetLastError` at `0x18000ec76`
- `WS2_32!__imp_WSAGetLastError` at `0x18000edce`
- `WS2_32!__imp_WSAGetLastError` at `0x18000f0af`
- `WS2_32!__imp_WSAGetLastError` at `0x18000ec76`
- `WS2_32!__imp_WSAGetLastError` at `0x18000edce`
- `WS2_32!__imp_WSAGetLastError` at `0x18000f0af`
- `WS2_32!__imp_WSAStartup` at `0x18000ec66`
- `WS2_32!__imp_WSAStartup` at `0x18000ec66`
- `WS2_32!__imp_WSACleanup` at `0x18000efcb`
- `WS2_32!__imp_WSACleanup` at `0x18000efcb`
- `WS2_32!__imp___WSAFDIsSet` at `0x18000ef10`
- `WS2_32!__imp___WSAFDIsSet` at `0x18000ef2e`
- `WS2_32!__imp___WSAFDIsSet` at `0x18000ef10`
- `WS2_32!__imp___WSAFDIsSet` at `0x18000ef2e`

## pseudocode

```c
__int64 __fastcall GetFirstProxy(const unsigned __int16 *a1, struct sockaddr_storage *a2, int *a3)
{
  int v6; // r15d
  __m128i si128; // xmm0
  int Error; // edi
  unsigned int v9; // r8d
  unsigned int v10; // r13d
  __int64 v11; // rax
  __int128 v12; // xmm1
  int v13; // r14d
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int64 v20; // r12
  sockaddr_storage *v21; // rsi
  SOCKET v22; // rax
  SOCKET v23; // r15
  int v24; // eax
  SOCKET v25; // rcx
  int v26; // eax
  unsigned int v27; // ecx
  unsigned int v28; // edx
  __int64 v29; // r10
  SOCKET v30; // r9
  __int64 i; // r8
  __int64 j; // r8
  __int64 v33; // r15
  SOCKET v34; // r12
  __int64 k; // rbx
  SOCKET v36; // rcx
  __int128 v38; // xmm1
  __int128 v39; // xmm0
  __int128 v40; // xmm1
  __int128 v41; // xmm0
  __int128 v42; // xmm1
  __int128 v43; // xmm0
  __int128 v44; // xmm1
  int *v45; // rax
  unsigned __int64 v46; // rsi
  __int128 v47; // xmm1
  __int128 v48; // xmm0
  __int128 v49; // xmm1
  __int128 v50; // xmm0
  __int128 v51; // xmm1
  int v52; // eax
  unsigned int v53; // [rsp+34h] [rbp-CCh] BYREF
  u_long argp; // [rsp+38h] [rbp-C8h] BYREF
  timeval timeout; // [rsp+40h] [rbp-C0h] BYREF
  struct _FILETIME v56; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+50h] [rbp-B0h] BYREF
  int *v58; // [rsp+58h] [rbp-A8h]
  sockaddr name; // [rsp+60h] [rbp-A0h] BYREF
  fd_set writefds; // [rsp+E0h] [rbp-20h] BYREF
  fd_set exceptfds; // [rsp+2F0h] [rbp+1F0h] BYREF
  WSAData WSAData; // [rsp+500h] [rbp+400h] BYREF
  SOCKET fd[2]; // [rsp+6A0h] [rbp+5A0h]
  __int64 v64; // [rsp+6B0h] [rbp+5B0h]
  sockaddr_storage v65[3]; // [rsp+6C0h] [rbp+5C0h] BYREF

  v58 = a3;
  v6 = 0;
  memset_0(&WSAData, 0, sizeof(WSAData));
  memset_0(v65, 0, sizeof(v65));
  v53 = 0;
  memset_0(&name, 0, 0x80u);
  argp = 1;
  memset_0(&writefds, 0, sizeof(writefds));
  memset_0(&exceptfds, 0, sizeof(exceptfds));
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v64 = si128.m128i_i64[0];
  timeout = (timeval)1LL;
  SystemTimeAsFileTime = 0;
  v56 = 0;
  *(__m128i *)fd = si128;
  if ( !a1 || !a2 || !a3 )
  {
    Error = -2147024809;
    goto LABEL_45;
  }
  Error = 0;
  *a3 = 0;
  if ( WSAStartup(0x202u, &WSAData) )
  {
    Error = WSAGetLastError();
    if ( Error < 0 )
      goto LABEL_45;
  }
  v6 = 1;
  GetProxyAddresses(a1, v65, v9, &v53);
  v10 = v53;
  if ( v53 - 1 > 2 )
    goto LABEL_45;
  v11 = 0;
  v12 = *(_OWORD *)v65[0].__ss_pad2;
  v13 = 0;
  v53 = 0;
  *(_OWORD *)&a2->ss_family = *(_OWORD *)&v65[0].ss_family;
  v14 = *(_OWORD *)&v65[0].__ss_pad2[16];
  *(_OWORD *)a2->__ss_pad2 = v12;
  v15 = *(_OWORD *)&v65[0].__ss_pad2[32];
  *(_OWORD *)&a2->__ss_pad2[16] = v14;
  v16 = *(_OWORD *)&v65[0].__ss_pad2[48];
  *(_OWORD *)&a2->__ss_pad2[32] = v15;
  v17 = *(_OWORD *)&v65[0].__ss_pad2[64];
  *(_OWORD *)&a2->__ss_pad2[48] = v16;
  v18 = *(_OWORD *)&v65[0].__ss_pad2[80];
  *(_OWORD *)&a2->__ss_pad2[64] = v17;
  v19 = *(_OWORD *)&v65[0].__ss_pad2[96];
  *(_OWORD *)&a2->__ss_pad2[80] = v18;
  *(_OWORD *)&a2->__ss_pad2[96] = v19;
  if ( v10 )
  {
    while ( 1 )
    {
      v20 = (unsigned int)v11;
      v21 = &v65[v11];
      v22 = socket(v21->ss_family, 1, 6);
      fd[v20] = v22;
      v23 = v22;
      if ( v22 == -1 )
      {
        ++v13;
      }
      else
      {
        v24 = ioctlsocket(v22, -2147195266, &argp);
        v25 = v23;
        if ( v24 != -1 )
        {
          name.sa_family = v21->ss_family;
          v26 = bind(v23, &name, 128);
          v25 = v23;
          if ( v26 != -1 )
          {
            if ( connect(v23, (const struct sockaddr *)v21, 128) != -1 )
            {
              v38 = *(_OWORD *)v21->__ss_pad2;
              *(_OWORD *)&a2->ss_family = *(_OWORD *)&v21->ss_family;
              v39 = *(_OWORD *)&v21->__ss_pad2[16];
              *(_OWORD *)a2->__ss_pad2 = v38;
              v40 = *(_OWORD *)&v21->__ss_pad2[32];
              *(_OWORD *)&a2->__ss_pad2[16] = v39;
              v41 = *(_OWORD *)&v21->__ss_pad2[48];
              *(_OWORD *)&a2->__ss_pad2[32] = v40;
              v42 = *(_OWORD *)&v21->__ss_pad2[64];
              *(_OWORD *)&a2->__ss_pad2[48] = v41;
              v43 = *(_OWORD *)&v21->__ss_pad2[80];
              *(_OWORD *)&a2->__ss_pad2[64] = v42;
              v44 = *(_OWORD *)&v21->__ss_pad2[96];
              goto LABEL_53;
            }
            if ( WSAGetLastError() == 10035 )
              goto LABEL_16;
            v25 = v23;
          }
        }
        ++v13;
        closesocket(v25);
        fd[v20] = -1;
      }
LABEL_16:
      v11 = v53 + 1;
      v53 = v11;
      if ( (unsigned int)v11 >= v10 )
      {
        v6 = 1;
        break;
      }
    }
  }
  if ( v13 == v10 )
    goto LABEL_45;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  while ( 1 )
  {
    v27 = 0;
    v28 = 0;
    v29 = 0;
    writefds.fd_count = 0;
    for ( exceptfds.fd_count = 0; (unsigned int)v29 < v10; v29 = (unsigned int)(v29 + 1) )
    {
      v30 = fd[v29];
      if ( v30 != -1 )
      {
        for ( i = 0; (unsigned int)i < v27; i = (unsigned int)(i + 1) )
        {
          if ( writefds.fd_array[i] == v30 )
            break;
        }
        if ( (_DWORD)i == v27 && v27 < 0x40 )
        {
          writefds.fd_array[i] = v30;
          v27 = ++writefds.fd_count;
        }
        for ( j = 0; (unsigned int)j < v28; j = (unsigned int)(j + 1) )
        {
          if ( exceptfds.fd_array[j] == v30 )
            break;
        }
        if ( (_DWORD)j == v28 && v28 < 0x40 )
        {
          exceptfds.fd_array[j] = v30;
          v28 = ++exceptfds.fd_count;
        }
      }
    }
    if ( select(0, 0, &writefds, &exceptfds, &timeout) == -1 )
    {
      v52 = WSAGetLastError();
      Error = v52;
      if ( v52 > 0 )
        Error = (unsigned __int16)v52 | 0x80070000;
      if ( Error >= 0 )
        Error = -2147467259;
      goto LABEL_44;
    }
    v33 = 0;
    if ( v10 )
      break;
LABEL_42:
    GetSystemTimeAsFileTime(&v56);
    if ( *(_QWORD *)&v56 - *(_QWORD *)&SystemTimeAsFileTime >= 0x2FAF080u || v13 == v10 )
      goto LABEL_44;
  }
  while ( 1 )
  {
    v34 = fd[v33];
    if ( v34 != -1 )
      break;
LABEL_41:
    v33 = (unsigned int)(v33 + 1);
    if ( (unsigned int)v33 >= v10 )
      goto LABEL_42;
  }
  if ( !__WSAFDIsSet(fd[v33], &writefds) )
  {
    if ( __WSAFDIsSet(v34, &exceptfds) )
    {
      ++v13;
      closesocket(v34);
      fd[v33] = -1;
    }
    goto LABEL_41;
  }
  v46 = (unsigned __int64)(unsigned int)v33 << 7;
  v47 = *(_OWORD *)&v65[0].__ss_pad2[v46];
  *(_OWORD *)&a2->ss_family = *(_OWORD *)((char *)&v65[0].ss_family + v46);
  v48 = *(_OWORD *)&v65[0].__ss_pad2[v46 + 16];
  *(_OWORD *)a2->__ss_pad2 = v47;
  v49 = *(_OWORD *)&v65[0].__ss_pad2[v46 + 32];
  *(_OWORD *)&a2->__ss_pad2[16] = v48;
  v50 = *(_OWORD *)&v65[0].__ss_pad2[v46 + 48];
  *(_OWORD *)&a2->__ss_pad2[32] = v49;
  v51 = *(_OWORD *)&v65[0].__ss_pad2[v46 + 64];
  *(_OWORD *)&a2->__ss_pad2[48] = v50;
  v43 = *(_OWORD *)&v65[0].__ss_pad2[v46 + 80];
  *(_OWORD *)&a2->__ss_pad2[64] = v51;
  v44 = *(_OWORD *)&v65[0].__ss_pad2[v46 + 96];
LABEL_53:
  v45 = v58;
  *(_OWORD *)&a2->__ss_pad2[80] = v43;
  *(_OWORD *)&a2->__ss_pad2[96] = v44;
  *v45 = 1;
LABEL_44:
  v6 = 1;
LABEL_45:
  for ( k = 0; k != 3; ++k )
  {
    v36 = fd[k];
    if ( v36 != -1 )
    {
      closesocket(v36);
      fd[k] = -1;
    }
  }
  if ( v6 )
    WSACleanup();
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18000eb64  mov     [rsp-8+arg_18], rbx
0x18000eb69  push    rbp
0x18000eb6a  push    rsi
0x18000eb6b  push    rdi
0x18000eb6c  push    r12
0x18000eb6e  push    r13
0x18000eb70  push    r14
0x18000eb72  push    r15
0x18000eb74  lea     rbp, [rsp-750h]
0x18000eb7c  sub     rsp, 850h
0x18000eb83  mov     rax, cs:__security_cookie
0x18000eb8a  xor     rax, rsp
0x18000eb8d  mov     [rbp+780h+var_40], rax
0x18000eb94  mov     r14, r8
0x18000eb97  mov     [rsp+880h+var_828], r8
0x18000eb9c  mov     rbx, rdx
0x18000eb9f  mov     rsi, rcx
0x18000eba2  xor     edx, edx; Val
0x18000eba4  lea     rcx, [rbp+780h+WSAData]; void *
0x18000ebab  mov     r8d, 198h; Size
0x18000ebb1  xor     r15d, r15d
0x18000ebb4  call    memset_0
0x18000ebb9  xor     edx, edx; Val
0x18000ebbb  lea     rcx, [rbp+780h+var_1C0]; void *
0x18000ebc2  mov     r8d, 180h; Size
0x18000ebc8  call    memset_0
0x18000ebcd  xor     edx, edx; Val
0x18000ebcf  mov     [rsp+880h+var_84C], r15d
0x18000ebd4  mov     r8d, 80h; Size
0x18000ebda  lea     rcx, [rsp+880h+name]; void *
0x18000ebdf  call    memset_0
0x18000ebe4  mov     edi, 208h
0x18000ebe9  mov     [rsp+880h+argp], 1
0x18000ebf1  mov     r8d, edi; Size
0x18000ebf4  lea     rcx, [rbp+780h+writefds]; void *
0x18000ebf8  xor     edx, edx; Val
0x18000ebfa  call    memset_0
0x18000ebff  mov     r8d, edi; Size
0x18000ec02  lea     rcx, [rbp+780h+exceptfds]; void *
0x18000ec09  xor     edx, edx; Val
0x18000ec0b  call    memset_0
0x18000ec10  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18000ec18  movq    [rbp+780h+var_1D0], xmm0
0x18000ec20  mov     qword ptr [rsp+880h+var_840.tv_sec], 1
0x18000ec29  mov     qword ptr [rsp+880h+SystemTimeAsFileTime.dwLowDateTime], r15
0x18000ec2e  mov     qword ptr [rsp+880h+var_838.dwLowDateTime], r15
0x18000ec33  movups  xmmword ptr [rbp+780h+fd], xmm0
0x18000ec3a  test    rsi, rsi
0x18000ec3d  jz      loc_18000F0D9
0x18000ec43  test    rbx, rbx
0x18000ec46  jz      loc_18000F0D9
0x18000ec4c  test    r14, r14
0x18000ec4f  jz      loc_18000F0D9
0x18000ec55  xor     edi, edi
0x18000ec57  lea     rdx, [rbp+780h+WSAData]; lpWSAData
0x18000ec5e  mov     ecx, 202h; wVersionRequested
0x18000ec63  mov     [r14], edi
0x18000ec66  call    cs:__imp_WSAStartup
0x18000ec6d  nop     dword ptr [rax+rax+00h]
0x18000ec72  test    eax, eax
0x18000ec74  jz      short loc_18000EC8C
0x18000ec76  call    cs:__imp_WSAGetLastError
0x18000ec7d  nop     dword ptr [rax+rax+00h]
0x18000ec82  mov     edi, eax
0x18000ec84  test    eax, eax
0x18000ec86  js      loc_18000EF95
0x18000ec8c  mov     r15d, 1
0x18000ec92  lea     r9, [rsp+880h+var_84C]; unsigned int *
0x18000ec97  lea     rdx, [rbp+780h+var_1C0]; struct sockaddr_storage *
0x18000ec9e  mov     [rsp+880h+var_850], r15d
0x18000eca3  mov     rcx, rsi; unsigned __int16 *
0x18000eca6  call    ?GetProxyAddresses@@YAXQEBGPEAUsockaddr_storage@@IPEAI@Z; GetProxyAddresses(ushort const * const,sockaddr_storage *,uint,uint *)
0x18000ecab  mov     r13d, [rsp+880h+var_84C]
0x18000ecb0  lea     ecx, [r13-1]
0x18000ecb4  cmp     ecx, 2
0x18000ecb7  ja      loc_18000EF95
0x18000ecbd  movaps  xmm0, xmmword ptr [rbp+780h+var_1C0.ss_family]
0x18000ecc4  xor     eax, eax
0x18000ecc6  movaps  xmm1, xmmword ptr [rbp+780h+var_1C0.__ss_pad2]
0x18000eccd  xor     r14d, r14d
0x18000ecd0  mov     [rsp+880h+var_84C], eax
0x18000ecd4  movups  xmmword ptr [rbx], xmm0
0x18000ecd7  movaps  xmm0, xmmword ptr [rbp+780h+var_1C0.__ss_pad2+10h]
0x18000ecde  movups  xmmword ptr [rbx+10h], xmm1
0x18000ece2  movaps  xmm1, xmmword ptr [rbp+780h+var_1C0.__ss_pad2+20h]
0x18000ece9  movups  xmmword ptr [rbx+20h], xmm0
0x18000eced  movaps  xmm0, xmmword ptr [rbp+780h+var_1C0.__ss_pad2+30h]
0x18000ecf4  movups  xmmword ptr [rbx+30h], xmm1
0x18000ecf8  movaps  xmm1, xmmword ptr [rbp+780h+var_1C0.__ss_pad2+40h]
0x18000ecff  movups  xmmword ptr [rbx+40h], xmm0
0x18000ed03  movaps  xmm0, xmmword ptr [rbp+780h+var_1C0.__ss_pad2+50h]
0x18000ed0a  movups  xmmword ptr [rbx+50h], xmm1
0x18000ed0e  movaps  xmm1, xmmword ptr [rbp+780h+var_1C0.__ss_pad2+60h]
0x18000ed15  movups  xmmword ptr [rbx+60h], xmm0
0x18000ed19  movups  xmmword ptr [rbx+70h], xmm1
0x18000ed1d  test    r13d, r13d
0x18000ed20  jz      loc_18000EE17
0x18000ed26  mov     r12d, eax
0x18000ed29  lea     rsi, [rbp+780h+var_1C0]
0x18000ed30  shl     rax, 7
0x18000ed34  mov     edx, 1; type
0x18000ed39  add     rsi, rax
0x18000ed3c  lea     r8d, [rdx+5]; protocol
0x18000ed40  movzx   ecx, word ptr [rsi]; af
0x18000ed43  call    cs:__imp_socket
0x18000ed4a  nop     dword ptr [rax+rax+00h]
0x18000ed4f  mov     [rbp+r12*8+780h+fd], rax
0x18000ed57  mov     r15, rax
0x18000ed5a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000ed5e  jnz     short loc_18000ED68
0x18000ed60  inc     r14d
0x18000ed63  jmp     loc_18000EDFF
0x18000ed68  lea     r8, [rsp+880h+argp]; argp
0x18000ed6d  mov     edx, 8004667Eh; cmd
0x18000ed72  mov     rcx, r15; s
0x18000ed75  call    cs:__imp_ioctlsocket
0x18000ed7c  nop     dword ptr [rax+rax+00h]
0x18000ed81  mov     rcx, r15; s
0x18000ed84  cmp     eax, 0FFFFFFFFh
0x18000ed87  jz      short loc_18000EDE4
0x18000ed89  movzx   eax, word ptr [rsi]
0x18000ed8c  lea     rdx, [rsp+880h+name]; name
0x18000ed91  mov     r8d, 80h; namelen
0x18000ed97  mov     [rsp+880h+name.sa_family], ax
0x18000ed9c  call    cs:__imp_bind
0x18000eda3  nop     dword ptr [rax+rax+00h]
0x18000eda8  mov     rcx, r15; s
0x18000edab  cmp     eax, 0FFFFFFFFh
0x18000edae  jz      short loc_18000EDE4
0x18000edb0  mov     r8d, 80h; namelen
0x18000edb6  mov     rdx, rsi; name
0x18000edb9  call    cs:__imp_connect
0x18000edc0  nop     dword ptr [rax+rax+00h]
0x18000edc5  cmp     eax, 0FFFFFFFFh
0x18000edc8  jnz     loc_18000F004
0x18000edce  call    cs:__imp_WSAGetLastError
0x18000edd5  nop     dword ptr [rax+rax+00h]
0x18000edda  cmp     eax, 2733h
0x18000eddf  jz      short loc_18000EDFF
0x18000ede1  mov     rcx, r15; s
0x18000ede4  inc     r14d
0x18000ede7  call    cs:__imp_closesocket
0x18000edee  nop     dword ptr [rax+rax+00h]
0x18000edf3  mov     [rbp+r12*8+780h+fd], 0FFFFFFFFFFFFFFFFh
0x18000edff  mov     eax, [rsp+880h+var_84C]
0x18000ee03  inc     eax
0x18000ee05  mov     [rsp+880h+var_84C], eax
0x18000ee09  cmp     eax, r13d
0x18000ee0c  jb      loc_18000ED26
0x18000ee12  mov     r15d, [rsp+880h+var_850]
0x18000ee17  cmp     r14d, r13d
0x18000ee1a  jz      loc_18000EF95
0x18000ee20  lea     rcx, [rsp+880h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000ee25  call    cs:__imp_GetSystemTimeAsFileTime
0x18000ee2c  nop     dword ptr [rax+rax+00h]
0x18000ee31  xor     ecx, ecx
0x18000ee33  xor     edx, edx
0x18000ee35  xor     r10d, r10d
0x18000ee38  mov     [rbp+780h+writefds.fd_count], ecx
0x18000ee3b  mov     [rbp+780h+exceptfds.fd_count], edx
0x18000ee41  test    r13d, r13d
0x18000ee44  jz      short loc_18000EEC2
0x18000ee46  mov     r9, [rbp+r10*8+780h+fd]
0x18000ee4e  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x18000ee52  jz      short loc_18000EEBA
0x18000ee54  xor     r8d, r8d
0x18000ee57  test    ecx, ecx
0x18000ee59  jz      short loc_18000EE6A
0x18000ee5b  cmp     [rbp+r8*8+780h+writefds.fd_array], r9
0x18000ee60  jz      short loc_18000EE6A
0x18000ee62  inc     r8d
0x18000ee65  cmp     r8d, ecx
0x18000ee68  jb      short loc_18000EE5B
0x18000ee6a  cmp     r8d, ecx
0x18000ee6d  jnz     short loc_18000EE81
0x18000ee6f  cmp     ecx, 40h ; '@'
0x18000ee72  jnb     short loc_18000EE81
0x18000ee74  mov     [rbp+r8*8+780h+writefds.fd_array], r9
0x18000ee79  mov     ecx, [rbp+780h+writefds.fd_count]
0x18000ee7c  inc     ecx
0x18000ee7e  mov     [rbp+780h+writefds.fd_count], ecx
0x18000ee81  xor     r8d, r8d
0x18000ee84  test    edx, edx
0x18000ee86  jz      short loc_18000EE9A
0x18000ee88  cmp     [rbp+r8*8+780h+exceptfds.fd_array], r9
0x18000ee90  jz      short loc_18000EE9A
0x18000ee92  inc     r8d
0x18000ee95  cmp     r8d, edx
0x18000ee98  jb      short loc_18000EE88
0x18000ee9a  cmp     r8d, edx
0x18000ee9d  jnz     short loc_18000EEBA
0x18000ee9f  cmp     edx, 40h ; '@'
0x18000eea2  jnb     short loc_18000EEBA
0x18000eea4  mov     [rbp+r8*8+780h+exceptfds.fd_array], r9
0x18000eeac  mov     edx, [rbp+780h+exceptfds.fd_count]
0x18000eeb2  inc     edx
0x18000eeb4  mov     [rbp+780h+exceptfds.fd_count], edx
0x18000eeba  inc     r10d
0x18000eebd  cmp     r10d, r13d
0x18000eec0  jb      short loc_18000EE46
0x18000eec2  lea     rax, [rsp+880h+var_840]
0x18000eec7  xor     edx, edx; readfds
0x18000eec9  lea     r9, [rbp+780h+exceptfds]; exceptfds
0x18000eed0  mov     [rsp+880h+timeout], rax; timeout
0x18000eed5  lea     r8, [rbp+780h+writefds]; writefds
0x18000eed9  xor     ecx, ecx; nfds
0x18000eedb  call    cs:__imp_select
0x18000eee2  nop     dword ptr [rax+rax+00h]
0x18000eee7  cmp     eax, 0FFFFFFFFh
0x18000eeea  jz      loc_18000F0AF
0x18000eef0  xor     r15d, r15d
0x18000eef3  test    r13d, r13d
0x18000eef6  jz      short loc_18000EF64
0x18000eef8  mov     r12, [rbp+r15*8+780h+fd]
0x18000ef00  mov     esi, r15d
0x18000ef03  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x18000ef07  jz      short loc_18000EF5C
0x18000ef09  lea     rdx, [rbp+780h+writefds]; fd_set *
0x18000ef0d  mov     rcx, r12; fd
0x18000ef10  call    cs:__imp___WSAFDIsSet
0x18000ef17  nop     dword ptr [rax+rax+00h]
0x18000ef1c  test    eax, eax
0x18000ef1e  jnz     loc_18000F052
0x18000ef24  lea     rdx, [rbp+780h+exceptfds]; fd_set *
0x18000ef2b  mov     rcx, r12; fd
0x18000ef2e  call    cs:__imp___WSAFDIsSet
0x18000ef35  nop     dword ptr [rax+rax+00h]
0x18000ef3a  test    eax, eax
0x18000ef3c  jz      short loc_18000EF5C
0x18000ef3e  inc     r14d
0x18000ef41  mov     rcx, r12; s
0x18000ef44  call    cs:__imp_closesocket
0x18000ef4b  nop     dword ptr [rax+rax+00h]
0x18000ef50  mov     [rbp+r15*8+780h+fd], 0FFFFFFFFFFFFFFFFh
0x18000ef5c  inc     r15d
0x18000ef5f  cmp     r15d, r13d
0x18000ef62  jb      short loc_18000EEF8
0x18000ef64  lea     rcx, [rsp+880h+var_838]; lpSystemTimeAsFileTime
0x18000ef69  call    cs:__imp_GetSystemTimeAsFileTime
0x18000ef70  nop     dword ptr [rax+rax+00h]
0x18000ef75  mov     rax, qword ptr [rsp+880h+var_838.dwLowDateTime]
0x18000ef7a  sub     rax, qword ptr [rsp+880h+SystemTimeAsFileTime.dwLowDateTime]
0x18000ef7f  cmp     rax, 2FAF080h
0x18000ef85  jnb     short loc_18000EF90
0x18000ef87  cmp     r14d, r13d
0x18000ef8a  jnz     loc_18000EE31
0x18000ef90  mov     r15d, [rsp+880h+var_850]
0x18000ef95  xor     ebx, ebx
0x18000ef97  mov     rcx, [rbp+rbx*8+780h+fd]; s
0x18000ef9f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000efa3  jz      short loc_18000EFBD
0x18000efa5  call    cs:__imp_closesocket
0x18000efac  nop     dword ptr [rax+rax+00h]
0x18000efb1  mov     [rbp+rbx*8+780h+fd], 0FFFFFFFFFFFFFFFFh
0x18000efbd  inc     rbx
0x18000efc0  cmp     rbx, 3
0x18000efc4  jnz     short loc_18000EF97
0x18000efc6  test    r15d, r15d
0x18000efc9  jz      short loc_18000EFD7
0x18000efcb  call    cs:__imp_WSACleanup
0x18000efd2  nop     dword ptr [rax+rax+00h]
0x18000efd7  mov     eax, edi
0x18000efd9  mov     rcx, [rbp+780h+var_40]
0x18000efe0  xor     rcx, rsp; StackCookie
0x18000efe3  call    __security_check_cookie
0x18000efe8  mov     rbx, [rsp+880h+arg_18]
0x18000eff0  add     rsp, 850h
0x18000eff7  pop     r15
0x18000eff9  pop     r14
0x18000effb  pop     r13
0x18000effd  pop     r12
0x18000efff  pop     rdi
0x18000f000  pop     rsi
0x18000f001  pop     rbp
0x18000f002  retn
0x18000f004  movups  xmm0, xmmword ptr [rsi]
0x18000f007  movups  xmm1, xmmword ptr [rsi+10h]
0x18000f00b  movups  xmmword ptr [rbx], xmm0
0x18000f00e  movups  xmm0, xmmword ptr [rsi+20h]
0x18000f012  movups  xmmword ptr [rbx+10h], xmm1
0x18000f016  movups  xmm1, xmmword ptr [rsi+30h]
0x18000f01a  movups  xmmword ptr [rbx+20h], xmm0
0x18000f01e  movups  xmm0, xmmword ptr [rsi+40h]
0x18000f022  movups  xmmword ptr [rbx+30h], xmm1
0x18000f026  movups  xmm1, xmmword ptr [rsi+50h]
0x18000f02a  movups  xmmword ptr [rbx+40h], xmm0
0x18000f02e  movups  xmm0, xmmword ptr [rsi+60h]
0x18000f032  movups  xmmword ptr [rbx+50h], xmm1
0x18000f036  movups  xmm1, xmmword ptr [rsi+70h]
0x18000f03a  mov     rax, [rsp+880h+var_828]
0x18000f03f  movups  xmmword ptr [rbx+60h], xmm0
0x18000f043  movups  xmmword ptr [rbx+70h], xmm1
0x18000f047  mov     dword ptr [rax], 1
0x18000f04d  jmp     loc_18000EF90
0x18000f052  shl     rsi, 7
0x18000f056  movups  xmm0, xmmword ptr [rbp+rsi+780h+var_1C0.ss_family]
0x18000f05e  movups  xmm1, xmmword ptr [rbp+rsi+780h+var_1C0.__ss_pad2]
0x18000f066  movups  xmmword ptr [rbx], xmm0
0x18000f069  movups  xmm0, xmmword ptr [rbp+rsi+780h+var_1C0.__ss_pad2+10h]
0x18000f071  movups  xmmword ptr [rbx+10h], xmm1
  ... truncated ...
```
