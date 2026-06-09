# GetInitialSockets(NicSocket * * *,uint *,uint *)

- ea: `0x180026200`
- end: `0x180026630`
- name: `?GetInitialSockets@@YAJPEAPEAPEAUNicSocket@@PEAI1@Z`
- size: `1072`
- prototype: `__int64 __fastcall(struct NicSocket ***, unsigned int *, unsigned int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800239c4`
- `0x1800301f8`

## callees

- `0x180018138`
- `0x180018dfc`
- `0x18001d9a0`
- `0x180026200`
- `0x180026640`
- `0x180029ef0`
- `0x18002c918`
- `0x18003f491`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026428`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002643c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800264b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800265c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800265ec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026428`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002643c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800264b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800265c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800265ec`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800262a3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800262c8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026373`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026399`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800262a3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800262c8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026373`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026399`
- `api-ms-win-core-handle-l1-1-0!GetHandleInformation` at `0x180026503`
- `api-ms-win-core-handle-l1-1-0!GetHandleInformation` at `0x180026503`
- `WS2_32!GetAddrInfoW` at `0x18002626a`
- `WS2_32!GetAddrInfoW` at `0x18002626a`
- `WS2_32!FreeAddrInfoW` at `0x18002633c`
- `WS2_32!FreeAddrInfoW` at `0x18002633c`
- `WS2_32!__imp_WSAGetLastError` at `0x18002647b`
- `WS2_32!__imp_WSAGetLastError` at `0x18002647b`

## string_xrefs

- `0x1800264c9`: `NtpProvider: Created %u sockets (%u listen-only): `
- `0x18002660d`: `NtpProvider: Created 0 sockets.\n`

## pseudocode

```c
__int64 __fastcall GetInitialSockets(struct NicSocket ***a1, unsigned int *a2, unsigned int *a3)
{
  unsigned int v3; // edi
  unsigned int *v4; // r15
  unsigned int *v5; // r12
  unsigned int v6; // esi
  struct NicSocket **v7; // r14
  unsigned __int64 v8; // rbp
  _DWORD *v9; // r13
  PADDRINFOW i; // rax
  struct sockaddr_storage *v11; // r12
  _DWORD *v12; // r15
  PADDRINFOW v13; // rsi
  signed int v14; // ebx
  struct sockaddr *v15; // rax
  unsigned int v16; // edi
  __int64 j; // rdx
  unsigned int v18; // eax
  int Error; // eax
  __int64 v21; // rbx
  struct NicSocket *v22; // rcx
  struct sockaddr **v23; // r15
  __int64 v24; // rdi
  struct NicSocket *v25; // rcx
  HLOCAL *v26; // r15
  ADDRINFOW v27; // [rsp+20h] [rbp-78h] BYREF
  PADDRINFOW pAddrInfo; // [rsp+B8h] [rbp+20h] BYREF

  v3 = 0;
  v27.ai_socktype = 2;
  v4 = a3;
  pAddrInfo = 0;
  v5 = a2;
  HIDWORD(v27.ai_next) = 0;
  v27.ai_family = 0;
  v27.ai_flags = 1;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  *(_OWORD *)&v27.ai_protocol = 0;
  *(_OWORD *)((char *)&v27.ai_canonname + 4) = 0;
  if ( GetAddrInfoW(0, L"123", &v27, &pAddrInfo) )
  {
    Error = WSAGetLastError();
    v14 = Error;
    if ( Error > 0 )
      v14 = (unsigned __int16)Error | 0x80070000;
  }
  else
  {
    for ( i = pAddrInfo; i; ++v3 )
      i = i->ai_next;
    v11 = (struct sockaddr_storage *)LocalAlloc(0x40u, (unsigned __int64)v3 << 7);
    if ( v11 )
    {
      v12 = LocalAlloc(0x40u, 4LL * v3);
      if ( v12 )
      {
        v13 = pAddrInfo;
        if ( v3 )
        {
          do
          {
            memcpy_0(&v11[(unsigned __int64)(unsigned int)v8], v13->ai_addr, v13->ai_addrlen);
            v12[v8] = v13->ai_addrlen;
            v8 = (unsigned int)(v8 + 1);
            v13 = v13->ai_next;
          }
          while ( (unsigned int)v8 < v3 );
        }
        v6 = v3;
        v8 = (unsigned __int64)v11;
        v3 = 0;
        v9 = v12;
        v14 = 0;
      }
      else
      {
        v14 = -2147024882;
        LocalFree(v11);
        v3 = 0;
      }
      v4 = a3;
    }
    else
    {
      v14 = -2147024882;
      v3 = 0;
    }
    v5 = a2;
  }
  if ( pAddrInfo )
    FreeAddrInfoW(pAddrInfo);
  if ( v14 >= 0 )
  {
    pAddrInfo = 0;
    if ( is_mul_ok(8u, v6) )
    {
      v7 = (struct NicSocket **)LocalAlloc(0x40u, 8LL * v6);
      if ( v7 )
      {
        while ( v3 < v6 )
        {
          v15 = (struct sockaddr *)LocalAlloc(0x40u, 0xB0u);
          v7[v3] = (struct NicSocket *)v15;
          if ( !v15 )
            goto LABEL_33;
          v14 = InitializeNicSocket(v15, (struct sockaddr_storage *)(v8 + ((unsigned __int64)v3 << 7)), v9[v3]);
          if ( v14 < 0 )
            goto LABEL_26;
          ++v3;
        }
        v16 = 0;
        for ( j = 0; (unsigned int)j < v6; v16 = v18 )
        {
          v18 = v16 + 1;
          if ( !*((_BYTE *)v7[j] + 152) )
            v18 = v16;
          j = (unsigned int)(j + 1);
        }
        if ( (unsigned __int8)FileLogAllowEntry(55) )
        {
          FileLogAdd(L"NtpProvider: Created %u sockets (%u listen-only): ", v6, v16);
          v21 = 0;
          if ( v6 )
          {
            do
            {
              v22 = v7[v21];
              v23 = (struct sockaddr **)&v7[v21];
              LODWORD(pAddrInfo) = 0;
              GetHandleInformation(*((HANDLE *)v22 + 17), (LPDWORD)&pAddrInfo);
              if ( (_DWORD)v21 )
                FileLogAppend(L", ");
              if ( (*v23)[9].sa_data[6] )
              {
                FileLogAppend(L"(");
                FileLogSockaddrInEx2(1, *v23, *(_DWORD *)&(*v23)[8].sa_family);
                FileLogAppend(L"<0x%x>", (unsigned int)pAddrInfo);
                FileLogAppend(L")");
              }
              else
              {
                FileLogSockaddrInEx2(1, *v23, *(_DWORD *)&(*v23)[8].sa_family);
                FileLogAppend(L"<0x%x>", (unsigned int)pAddrInfo);
              }
              v21 = (unsigned int)(v21 + 1);
            }
            while ( (unsigned int)v21 < v6 );
            v4 = a3;
          }
          FileLogAppend(L"\n");
        }
        v14 = 0;
        *a1 = v7;
        v7 = 0;
        *v5 = v6;
        *v4 = v16;
      }
      else
      {
LABEL_33:
        v14 = -2147024882;
      }
    }
    else
    {
      v14 = -2147024362;
    }
  }
LABEL_26:
  if ( v8 )
    LocalFree((HLOCAL)v8);
  if ( v9 )
    LocalFree(v9);
  if ( v7 )
  {
    v24 = 0;
    if ( v6 )
    {
      do
      {
        v25 = v7[v24];
        v26 = (HLOCAL *)&v7[v24];
        if ( v25 )
        {
          FinalizeNicSocket(v25);
          LocalFree(*v26);
          *v26 = 0;
        }
        v24 = (unsigned int)(v24 + 1);
      }
      while ( (unsigned int)v24 < v6 );
      v4 = a3;
    }
    LocalFree(v7);
  }
  if ( v14 < 0 )
  {
    v14 = 0;
    if ( (unsigned __int8)FileLogAllowEntry(55) )
      FileLogAdd(L"NtpProvider: Created 0 sockets.\n");
    *a1 = 0;
    *v5 = 0;
    *v4 = 0;
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180026200  mov     rax, rsp
0x180026203  mov     [rax+18h], r8
0x180026207  mov     [rax+10h], rdx
0x18002620b  mov     [rax+8], rcx
0x18002620f  push    rbx
0x180026210  push    rbp
0x180026211  push    rsi
0x180026212  push    rdi
0x180026213  push    r12
0x180026215  push    r13
0x180026217  push    r14
0x180026219  push    r15
0x18002621b  sub     rsp, 58h
0x18002621f  xor     edi, edi
0x180026221  mov     dword ptr [rax-70h], 2
0x180026228  mov     r15, r8
0x18002622b  mov     [rax+20h], rdi
0x18002622f  mov     r12, rdx
0x180026232  mov     [rax-4Ch], edi
0x180026235  xorps   xmm0, xmm0
0x180026238  mov     [rax-74h], edi
0x18002623b  xorps   xmm1, xmm1
0x18002623e  mov     dword ptr [rax-78h], 1
0x180026245  lea     r8, [rax-78h]; pHints
0x180026249  xor     ecx, ecx; pNodeName
0x18002624b  lea     rdx, ?wszPort@NtpConst@@2QBGB; "123"
0x180026252  mov     esi, edi
0x180026254  lea     r9, [rax+20h]; ppResult
0x180026258  mov     r14d, edi
0x18002625b  mov     ebp, edi
0x18002625d  mov     r13d, edi
0x180026260  movdqu  xmmword ptr [rax-6Ch], xmm0
0x180026265  movdqu  xmmword ptr [rax-5Ch], xmm1
0x18002626a  call    cs:__imp_GetAddrInfoW
0x180026271  nop     dword ptr [rax+rax+00h]
0x180026276  test    eax, eax
0x180026278  jnz     loc_18002647B
0x18002627e  mov     rax, [rsp+98h+pAddrInfo]
0x180026286  test    rax, rax
0x180026289  jz      short loc_180026296
0x18002628b  mov     rax, [rax+28h]
0x18002628f  inc     edi
0x180026291  test    rax, rax
0x180026294  jnz     short loc_18002628B
0x180026296  mov     edx, edi
0x180026298  mov     ecx, 40h ; '@'; uFlags
0x18002629d  shl     rdx, 7; uBytes
0x1800262a1  mov     ebx, edi
0x1800262a3  call    cs:__imp_LocalAlloc
0x1800262aa  nop     dword ptr [rax+rax+00h]
0x1800262af  mov     r12, rax
0x1800262b2  test    rax, rax
0x1800262b5  jz      loc_18002649F
0x1800262bb  lea     rdx, ds:0[rbx*4]; uBytes
0x1800262c3  mov     ecx, 40h ; '@'; uFlags
0x1800262c8  call    cs:__imp_LocalAlloc
0x1800262cf  nop     dword ptr [rax+rax+00h]
0x1800262d4  mov     r15, rax
0x1800262d7  test    rax, rax
0x1800262da  jz      loc_1800264AB
0x1800262e0  mov     rsi, [rsp+98h+pAddrInfo]
0x1800262e8  test    edi, edi
0x1800262ea  jz      short loc_180026313
0x1800262ec  mov     r8, [rsi+10h]; Size
0x1800262f0  mov     rdx, [rsi+20h]; Src
0x1800262f4  mov     ecx, ebp
0x1800262f6  shl     rcx, 7
0x1800262fa  add     rcx, r12; void *
0x1800262fd  call    memcpy_0
0x180026302  mov     eax, [rsi+10h]
0x180026305  mov     [r15+rbp*4], eax
0x180026309  inc     ebp
0x18002630b  mov     rsi, [rsi+28h]
0x18002630f  cmp     ebp, edi
0x180026311  jb      short loc_1800262EC
0x180026313  mov     esi, edi
0x180026315  mov     rbp, r12
0x180026318  xor     edi, edi
0x18002631a  mov     r13, r15
0x18002631d  mov     ebx, edi
0x18002631f  mov     r15, [rsp+98h+arg_10]
0x180026327  mov     r12, [rsp+98h+arg_8]
0x18002632f  mov     rcx, [rsp+98h+pAddrInfo]; pAddrInfo
0x180026337  test    rcx, rcx
0x18002633a  jz      short loc_180026348
0x18002633c  call    cs:__imp_FreeAddrInfoW
0x180026343  nop     dword ptr [rax+rax+00h]
0x180026348  test    ebx, ebx
0x18002634a  js      loc_180026420
0x180026350  mov     eax, esi
0x180026352  mov     ecx, 8
0x180026357  mul     rcx
0x18002635a  mov     [rsp+98h+pAddrInfo], rdi
0x180026362  test    rdx, rdx
0x180026365  jnz     loc_180026474
0x18002636b  mov     rdx, rax; uBytes
0x18002636e  mov     ecx, 40h ; '@'; uFlags
0x180026373  call    cs:__imp_LocalAlloc
0x18002637a  nop     dword ptr [rax+rax+00h]
0x18002637f  mov     r14, rax
0x180026382  test    rax, rax
0x180026385  jz      loc_18002646D
0x18002638b  cmp     edi, esi
0x18002638d  jnb     short loc_1800263D6
0x18002638f  mov     edx, 0B0h; uBytes
0x180026394  mov     ecx, 40h ; '@'; uFlags
0x180026399  call    cs:__imp_LocalAlloc
0x1800263a0  nop     dword ptr [rax+rax+00h]
0x1800263a5  mov     r8d, edi
0x1800263a8  mov     [r14+r8*8], rax
0x1800263ac  test    rax, rax
0x1800263af  jz      loc_18002646D
0x1800263b5  mov     edx, r8d
0x1800263b8  mov     rcx, rax; name
0x1800263bb  mov     r8d, [r13+r8*4+0]; unsigned int
0x1800263c0  shl     rdx, 7
0x1800263c4  add     rdx, rbp; struct sockaddr_storage *
0x1800263c7  call    ?InitializeNicSocket@@YAJPEAUNicSocket@@PEAUsockaddr_storage@@I@Z; InitializeNicSocket(NicSocket *,sockaddr_storage *,uint)
0x1800263cc  mov     ebx, eax
0x1800263ce  test    eax, eax
0x1800263d0  js      short loc_180026420
0x1800263d2  inc     edi
0x1800263d4  jmp     short loc_18002638B
0x1800263d6  xor     edi, edi
0x1800263d8  xor     edx, edx
0x1800263da  test    esi, esi
0x1800263dc  jz      short loc_1800263F7
0x1800263de  mov     rcx, [r14+rdx*8]
0x1800263e2  lea     eax, [rdi+1]
0x1800263e5  cmp     byte ptr [rcx+98h], 0
0x1800263ec  cmovz   eax, edi
0x1800263ef  inc     edx
0x1800263f1  mov     edi, eax
0x1800263f3  cmp     edx, esi
0x1800263f5  jb      short loc_1800263DE
0x1800263f7  mov     ecx, 37h ; '7'
0x1800263fc  call    FileLogAllowEntry
0x180026401  test    al, al
0x180026403  jnz     loc_1800264C6
0x180026409  mov     rax, [rsp+98h+arg_0]
0x180026411  xor     ebx, ebx
0x180026413  mov     [rax], r14
0x180026416  xor     r14d, r14d
0x180026419  mov     [r12], esi
0x18002641d  mov     [r15], edi
0x180026420  test    rbp, rbp
0x180026423  jz      short loc_180026434
0x180026425  mov     rcx, rbp; hMem
0x180026428  call    cs:__imp_LocalFree
0x18002642f  nop     dword ptr [rax+rax+00h]
0x180026434  test    r13, r13
0x180026437  jz      short loc_180026448
0x180026439  mov     rcx, r13; hMem
0x18002643c  call    cs:__imp_LocalFree
0x180026443  nop     dword ptr [rax+rax+00h]
0x180026448  test    r14, r14
0x18002644b  jnz     loc_1800265AD
0x180026451  test    ebx, ebx
0x180026453  js      loc_1800265FD
0x180026459  mov     eax, ebx
0x18002645b  add     rsp, 58h
0x18002645f  pop     r15
0x180026461  pop     r14
0x180026463  pop     r13
0x180026465  pop     r12
0x180026467  pop     rdi
0x180026468  pop     rsi
0x180026469  pop     rbp
0x18002646a  pop     rbx
0x18002646b  retn
0x18002646d  mov     ebx, 8007000Eh
0x180026472  jmp     short loc_180026420
0x180026474  mov     ebx, 80070216h
0x180026479  jmp     short loc_180026420
0x18002647b  call    cs:__imp_WSAGetLastError
0x180026482  nop     dword ptr [rax+rax+00h]
0x180026487  mov     ebx, eax
0x180026489  test    eax, eax
0x18002648b  jle     loc_18002632F
0x180026491  movzx   ebx, ax
0x180026494  or      ebx, 80070000h
0x18002649a  jmp     loc_18002632F
0x18002649f  mov     ebx, 8007000Eh
0x1800264a4  xor     edi, edi
0x1800264a6  jmp     loc_180026327
0x1800264ab  mov     ebx, 8007000Eh
0x1800264b0  mov     rcx, r12; hMem
0x1800264b3  call    cs:__imp_LocalFree
0x1800264ba  nop     dword ptr [rax+rax+00h]
0x1800264bf  xor     edi, edi
0x1800264c1  jmp     loc_18002631F
0x1800264c6  mov     r8d, edi
0x1800264c9  lea     rcx, aNtpproviderCre_0; "NtpProvider: Created %u sockets (%u lis"...
0x1800264d0  mov     edx, esi
0x1800264d2  call    FileLogAdd
0x1800264d7  xor     ebx, ebx
0x1800264d9  test    esi, esi
0x1800264db  jz      loc_18002659C
0x1800264e1  mov     rcx, [r14+rbx*8]
0x1800264e5  lea     r15, [r14+rbx*8]
0x1800264e9  mov     dword ptr [rsp+98h+pAddrInfo], 0
0x1800264f4  lea     rdx, [rsp+98h+pAddrInfo]; lpdwFlags
0x1800264fc  mov     rcx, [rcx+88h]; hObject
0x180026503  call    cs:__imp_GetHandleInformation
0x18002650a  nop     dword ptr [rax+rax+00h]
0x18002650f  test    ebx, ebx
0x180026511  jz      short loc_18002651F
0x180026513  lea     rcx, asc_180074278; ", "
0x18002651a  call    FileLogAppend
0x18002651f  mov     rdx, [r15]; struct sockaddr_storage *
0x180026522  cmp     byte ptr [rdx+98h], 0
0x180026529  jz      short loc_180026569
0x18002652b  lea     rcx, SubStr; "("
0x180026532  call    FileLogAppend
0x180026537  mov     rdx, [r15]; struct sockaddr_storage *
0x18002653a  mov     cl, 1; bool
0x18002653c  mov     r8d, [rdx+80h]; unsigned int
0x180026543  call    ?FileLogSockaddrInEx2@@YAX_NPEAUsockaddr_storage@@I@Z; FileLogSockaddrInEx2(bool,sockaddr_storage *,uint)
0x180026548  mov     edx, dword ptr [rsp+98h+pAddrInfo]
0x18002654f  lea     rcx, a0xX; "<0x%x>"
0x180026556  call    FileLogAppend
0x18002655b  lea     rcx, asc_180074290; ")"
0x180026562  call    FileLogAppend
0x180026567  jmp     short loc_18002658A
0x180026569  mov     r8d, [rdx+80h]; unsigned int
0x180026570  mov     cl, 1; bool
0x180026572  call    ?FileLogSockaddrInEx2@@YAX_NPEAUsockaddr_storage@@I@Z; FileLogSockaddrInEx2(bool,sockaddr_storage *,uint)
0x180026577  mov     edx, dword ptr [rsp+98h+pAddrInfo]
0x18002657e  lea     rcx, a0xX; "<0x%x>"
0x180026585  call    FileLogAppend
0x18002658a  inc     ebx
0x18002658c  cmp     ebx, esi
0x18002658e  jb      loc_1800264E1
0x180026594  mov     r15, [rsp+98h+arg_10]
0x18002659c  lea     rcx, asc_18007145C; "\n"
0x1800265a3  call    FileLogAppend
0x1800265a8  jmp     loc_180026409
0x1800265ad  xor     edi, edi
0x1800265af  test    esi, esi
0x1800265b1  jz      short loc_1800265E9
0x1800265b3  mov     rcx, [r14+rdi*8]; struct NicSocket *
0x1800265b7  lea     r15, [r14+rdi*8]
0x1800265bb  test    rcx, rcx
0x1800265be  jz      short loc_1800265DB
0x1800265c0  call    ?FinalizeNicSocket@@YAXPEAUNicSocket@@@Z; FinalizeNicSocket(NicSocket *)
0x1800265c5  mov     rcx, [r15]; hMem
0x1800265c8  call    cs:__imp_LocalFree
0x1800265cf  nop     dword ptr [rax+rax+00h]
0x1800265d4  mov     qword ptr [r15], 0
0x1800265db  inc     edi
0x1800265dd  cmp     edi, esi
0x1800265df  jb      short loc_1800265B3
0x1800265e1  mov     r15, [rsp+98h+arg_10]
0x1800265e9  mov     rcx, r14; hMem
0x1800265ec  call    cs:__imp_LocalFree
0x1800265f3  nop     dword ptr [rax+rax+00h]
0x1800265f8  jmp     loc_180026451
0x1800265fd  mov     ecx, 37h ; '7'
0x180026602  xor     ebx, ebx
0x180026604  call    FileLogAllowEntry
0x180026609  test    al, al
0x18002660b  jz      short loc_180026619
0x18002660d  lea     rcx, aNtpproviderCre; "NtpProvider: Created 0 sockets.\n"
0x180026614  call    FileLogAdd
0x180026619  mov     rax, [rsp+98h+arg_0]
0x180026621  mov     [rax], rbx
0x180026624  mov     [r12], ebx
0x180026628  mov     [r15], ebx
0x18002662b  jmp     loc_180026459
```
