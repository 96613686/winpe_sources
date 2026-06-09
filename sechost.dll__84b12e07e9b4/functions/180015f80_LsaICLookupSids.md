# LsaICLookupSids

- ea: `0x180015f80`
- end: `0x18001649c`
- name: `LsaICLookupSids`
- size: `1308`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180015ddc`

## callees

- `0x180015f80`
- `0x18004f902`
- `0x18004f91a`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001626d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001626d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016124`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016374`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001639a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800163e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016463`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001647c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016124`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016374`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001639a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800163e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016463`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001647c`
- `RPCRT4!NdrClientCall3` at `0x1800160e7`
- `RPCRT4!NdrClientCall3` at `0x1800161dd`
- `RPCRT4!NdrClientCall3` at `0x1800160e7`
- `RPCRT4!NdrClientCall3` at `0x1800161dd`
- `RPCRT4!I_RpcExceptionFilter` at `0x18005024c`
- `RPCRT4!I_RpcExceptionFilter` at `0x180050268`
- `RPCRT4!I_RpcExceptionFilter` at `0x18005024c`
- `RPCRT4!I_RpcExceptionFilter` at `0x180050268`
- `RPCRT4!I_RpcMapWin32Status` at `0x180016135`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800163ab`
- `RPCRT4!I_RpcMapWin32Status` at `0x180016135`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800163ab`

## pseudocode

```c
__int64 __fastcall LsaICLookupSids(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        HLOCAL *a4,
        HLOCAL *a5,
        int a6,
        int a7,
        __int64 a8,
        _DWORD *a9)
{
  char v12; // r14
  int v13; // r8d
  HLOCAL v14; // rcx
  int v15; // eax
  int v16; // eax
  CLIENT_CALL_RETURN v17; // rbx
  unsigned int v18; // edx
  unsigned int v19; // r8d
  unsigned int v20; // r9d
  size_t v21; // rdi
  HLOCAL v22; // rax
  char *v23; // r15
  unsigned int v24; // r13d
  __int64 v25; // rdi
  int v26; // edi
  _DWORD *v27; // r8
  unsigned int i; // ecx
  __int64 v29; // rdx
  int v30; // eax
  __int64 v31; // [rsp+38h] [rbp-C0h]
  _DWORD v32[2]; // [rsp+68h] [rbp-90h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp-88h]
  unsigned int v34; // [rsp+78h] [rbp-80h]
  int Pointer; // [rsp+7Ch] [rbp-7Ch]
  __int64 v36; // [rsp+80h] [rbp-78h] BYREF
  HLOCAL v37; // [rsp+88h] [rbp-70h]
  unsigned int v38; // [rsp+90h] [rbp-68h]
  char *v39; // [rsp+98h] [rbp-60h]
  _DWORD v40[2]; // [rsp+A0h] [rbp-58h] BYREF
  __int64 v41; // [rsp+A8h] [rbp-50h]
  CLIENT_CALL_RETURN v42; // [rsp+B0h] [rbp-48h]
  HLOCAL *v43; // [rsp+118h] [rbp+20h]

  v43 = a4;
  v40[1] = 0;
  v32[1] = 0;
  v36 = 0;
  v37 = 0;
  if ( a9 )
    *a9 = 2;
  if ( !a1 )
    return 3221225480LL;
  if ( !a2 )
    return 3221225485LL;
  if ( a2 > 0x5000 )
    return 3221225854LL;
  v12 = 0;
  v40[0] = a2;
  v41 = a3;
  v13 = a6;
  if ( a6 == 1 )
  {
    *a4 = 0;
    *a5 = 0;
  }
  v32[0] = 0;
  hMem = 0;
  v14 = *a5;
  if ( *a5 )
  {
    v32[0] = a2;
    hMem = v14;
    v12 = 1;
  }
  v15 = 2;
  if ( (a7 & 2) != 0 )
    v15 = 1;
  v16 = v15 - 1;
  if ( v16 )
  {
    if ( v16 != 1 )
    {
      LODWORD(v17.Pointer) = -1073741811;
      goto LABEL_34;
    }
    v42.Simple = 0;
    v17.Pointer = NdrClientCall3(
                    (MIDL_STUBLESS_PROXY_INFO *)&stru_1800524F0,
                    0x39u,
                    0,
                    *(_QWORD *)(a1 + 8),
                    v40,
                    a4,
                    v32,
                    a6,
                    a8,
                    a7 & 0xFFFFFFF8,
                    2).Pointer;
    v42.Pointer = v17.Pointer;
    Pointer = (int)v17.Pointer;
    *a5 = hMem;
    if ( LODWORD(v17.Pointer) != -1073610734 && LODWORD(v17.Pointer) != -1073610706 )
      goto LABEL_34;
    v13 = a6;
    a4 = v43;
  }
  if ( a9 )
    *a9 = 1;
  LODWORD(v31) = v13;
  LODWORD(v17.Pointer) = (unsigned int)NdrClientCall3(
                                         (MIDL_STUBLESS_PROXY_INFO *)&stru_1800524F0,
                                         0xFu,
                                         0,
                                         *(_QWORD *)(a1 + 8),
                                         v40,
                                         a4,
                                         &v36,
                                         v31,
                                         a8).Pointer;
  Pointer = (int)v17.Pointer;
  if ( v37 )
  {
    v39 = 0;
    v18 = v36;
    v19 = 32 * v36;
    v38 = 32 * v36;
    v20 = 0;
    v34 = 0;
    while ( v20 < (unsigned int)v36 )
    {
      v19 += *((unsigned __int16 *)v37 + 16 * v20 + 5);
      v38 = v19;
      v34 = ++v20;
    }
    if ( !v12 )
    {
      v21 = v19;
      v22 = LocalAlloc(0x40u, v19);
      hMem = v22;
      if ( !v22 )
      {
        LODWORD(v17.Pointer) = -1073741670;
        Pointer = -1073741670;
        goto LABEL_34;
      }
      memset_0(v22, 0, v21);
      v18 = v36;
      v32[0] = v36;
    }
    v23 = (char *)hMem + 32 * v18;
    v39 = v23;
    v32[0] = v18;
    v24 = 0;
    v34 = 0;
    while ( v24 < v18 )
    {
      v25 = 32LL * v24;
      *(_DWORD *)((char *)hMem + v25) = *(_DWORD *)((char *)v37 + v25);
      *(_OWORD *)((char *)hMem + v25 + 8) = *(_OWORD *)((char *)v37 + v25 + 8);
      memcpy_0(v23, *(const void **)((char *)v37 + v25 + 16), *(unsigned __int16 *)((char *)v37 + v25 + 8));
      *(_QWORD *)((char *)hMem + v25 + 16) = v23;
      *(_DWORD *)((char *)hMem + v25 + 24) = *(_DWORD *)((char *)v37 + v25 + 24);
      v23 += *(unsigned __int16 *)((char *)v37 + v25 + 10);
      v39 = v23;
      v34 = ++v24;
      v18 = v36;
    }
  }
LABEL_34:
  *a5 = hMem;
  if ( v37 )
    LocalFree(v37);
  if ( SLODWORD(v17.Simple) >= 0 )
  {
    if ( v32[0] == a2 && hMem )
    {
      v27 = *v43;
      v26 = 0;
      for ( i = 0; i < a2; ++i )
      {
        v29 = 32LL * i;
        if ( (unsigned int)(*(_DWORD *)((char *)hMem + v29) - 6) > 2 )
        {
          if ( !v27 )
            goto LABEL_38;
          v30 = *(_DWORD *)((char *)hMem + v29 + 24);
          if ( v30 < 0 || (unsigned int)v30 >= *v27 )
          {
            v26 = -1073741629;
            break;
          }
        }
      }
      if ( v26 >= 0 )
        return LODWORD(v17.Pointer);
    }
    else
    {
LABEL_38:
      v26 = -1073741629;
    }
    if ( !v12 && hMem )
    {
      LocalFree(hMem);
      *a5 = 0;
    }
    if ( *v43 )
    {
      LocalFree(*v43);
      *v43 = 0;
    }
    LODWORD(v17.Pointer) = v26;
  }
  return LODWORD(v17.Pointer);
}

```

## disassembly

```asm
0x180015f80  mov     r11, rsp
0x180015f83  mov     [r11+20h], r9
0x180015f87  mov     [rsp+arg_8], edx
0x180015f8b  mov     [r11+8], rcx
0x180015f8f  push    rbx
0x180015f90  push    rsi
0x180015f91  push    rdi
0x180015f92  push    r12
0x180015f94  push    r13
0x180015f96  push    r14
0x180015f98  push    r15
0x180015f9a  sub     rsp, 0C0h
0x180015fa1  mov     r12d, edx
0x180015fa4  mov     r13, rcx
0x180015fa7  xor     eax, eax
0x180015fa9  xor     esi, esi
0x180015fab  mov     [r11-54h], esi
0x180015faf  mov     [rsp+0F8h+var_8C], eax
0x180015fb3  mov     [r11-78h], rsi
0x180015fb7  mov     [r11-70h], rsi
0x180015fbb  mov     r15, [rsp+0F8h+arg_40]
0x180015fc3  test    r15, r15
0x180015fc6  jz      short loc_180015FCF
0x180015fc8  mov     dword ptr [r15], 2
0x180015fcf  test    r13, r13
0x180015fd2  jnz     short loc_180015FDE
0x180015fd4  mov     eax, 0C0000008h
0x180015fd9  jmp     loc_180016489
0x180015fde  test    r12d, r12d
0x180015fe1  jnz     short loc_180015FED
0x180015fe3  mov     eax, 0C000000Dh
0x180015fe8  jmp     loc_180016489
0x180015fed  cmp     r12d, 5000h
0x180015ff4  jbe     short loc_180016000
0x180015ff6  mov     eax, 0C000017Eh
0x180015ffb  jmp     loc_180016489
0x180016000  mov     r14b, sil
0x180016003  mov     [rsp+0F8h+var_98], sil
0x180016008  mov     edx, [rsp+0F8h+arg_30]
0x18001600f  and     edx, 0FFFFFFF8h
0x180016012  mov     [rsp+0F8h+var_58], r12d
0x18001601a  mov     [rsp+0F8h+var_50], r8
0x180016022  mov     edi, 1
0x180016027  mov     r8d, [rsp+0F8h+arg_28]
0x18001602f  cmp     r8d, edi
0x180016032  jnz     short loc_180016042
0x180016034  mov     [r9], rsi
0x180016037  mov     rax, [rsp+0F8h+arg_20]
0x18001603f  mov     [rax], rsi
0x180016042  mov     [rsp+0F8h+var_90], esi
0x180016046  mov     [rsp+0F8h+hMem], rsi
0x18001604b  mov     rax, [rsp+0F8h+arg_20]
0x180016053  mov     rcx, [rax]
0x180016056  test    rcx, rcx
0x180016059  jz      short loc_18001606D
0x18001605b  mov     [rsp+0F8h+var_90], r12d
0x180016060  mov     [rsp+0F8h+hMem], rcx
0x180016065  mov     r14b, dil
0x180016068  mov     [rsp+0F8h+var_98], dil
0x18001606d  test    byte ptr [rsp+0F8h+arg_30], 2
0x180016075  mov     eax, 2
0x18001607a  cmovnz  eax, edi
0x18001607d  sub     eax, edi
0x18001607f  jz      loc_18001618A
0x180016085  cmp     eax, edi
0x180016087  jz      short loc_180016093
0x180016089  mov     ebx, 0C000000Dh
0x18001608e  jmp     loc_1800163C9
0x180016093  mov     [rsp+0F8h+var_48], rsi
0x18001609b  mov     [rsp+0F8h+var_A8], 2
0x1800160a3  mov     [rsp+0F8h+var_B0], edx
0x1800160a7  mov     rax, [rsp+0F8h+arg_38]
0x1800160af  mov     [rsp+0F8h+var_B8], rax
0x1800160b4  mov     dword ptr [rsp+0F8h+var_C0], r8d
0x1800160b9  lea     rax, [rsp+0F8h+var_90]
0x1800160be  mov     [rsp+0F8h+var_C8], rax
0x1800160c3  mov     [rsp+0F8h+var_D0], r9
0x1800160c8  lea     rax, [rsp+0F8h+var_58]
0x1800160d0  mov     [rsp+0F8h+var_D8], rax
0x1800160d5  mov     r9, [r13+8]
0x1800160d9  xor     r8d, r8d; pReturnValue
0x1800160dc  lea     edx, [r8+39h]; nProcNum
0x1800160e0  lea     rcx, stru_1800524F0; pProxyInfo
0x1800160e7  call    cs:__imp_NdrClientCall3
0x1800160ed  mov     rbx, rax
0x1800160f0  mov     [rsp+0F8h+var_48], rax
0x1800160f8  mov     [rsp+0F8h+var_7C], eax
0x1800160fc  mov     rcx, [rsp+0F8h+arg_20]
0x180016104  mov     rax, [rsp+0F8h+hMem]
0x180016109  mov     [rcx], rax
0x18001610c  jmp     short loc_180016166
0x18001610e  mov     ebx, eax
0x180016110  mov     r14b, [rsp+0F8h+var_98]
0x180016115  test    r14b, r14b
0x180016118  jnz     short loc_180016133
0x18001611a  mov     rcx, [rsp+0F8h+hMem]; hMem
0x18001611f  test    rcx, rcx
0x180016122  jz      short loc_180016133
0x180016124  call    cs:__imp_LocalFree
0x18001612a  mov     [rsp+0F8h+hMem], 0
0x180016133  mov     ecx, ebx; Status
0x180016135  call    cs:__imp_I_RpcMapWin32Status
0x18001613b  mov     ebx, 0C0000001h
0x180016140  test    eax, eax
0x180016142  cmovs   ebx, eax
0x180016145  mov     [rsp+0F8h+var_7C], ebx
0x180016149  xor     esi, esi
0x18001614b  lea     edi, [rsi+1]
0x18001614e  mov     r15, [rsp+0F8h+arg_40]
0x180016156  mov     r12d, [rsp+0F8h+arg_8]
0x18001615e  mov     r13, [rsp+0F8h+arg_0]
0x180016166  cmp     ebx, 0C0020012h
0x18001616c  jz      short loc_18001617A
0x18001616e  cmp     ebx, 0C002002Eh
0x180016174  jnz     loc_1800163C9
0x18001617a  mov     r8d, [rsp+0F8h+arg_28]
0x180016182  mov     r9, [rsp+0F8h+arg_18]
0x18001618a  test    r15, r15
0x18001618d  jz      short loc_180016192
0x18001618f  mov     [r15], edi
0x180016192  mov     [rsp+0F8h+arg_40], rsi
0x18001619a  mov     rax, [rsp+0F8h+arg_38]
0x1800161a2  mov     [rsp+0F8h+var_B8], rax
0x1800161a7  mov     dword ptr [rsp+0F8h+var_C0], r8d
0x1800161ac  lea     rax, [rsp+0F8h+var_78]
0x1800161b4  mov     [rsp+0F8h+var_C8], rax
0x1800161b9  mov     [rsp+0F8h+var_D0], r9
0x1800161be  lea     rax, [rsp+0F8h+var_58]
0x1800161c6  mov     [rsp+0F8h+var_D8], rax
0x1800161cb  mov     r9, [r13+8]
0x1800161cf  xor     r8d, r8d; pReturnValue
0x1800161d2  lea     edx, [r8+0Fh]; nProcNum
0x1800161d6  lea     rcx, stru_1800524F0; pProxyInfo
0x1800161dd  call    cs:__imp_NdrClientCall3
0x1800161e3  mov     [rsp+0F8h+arg_40], rax
0x1800161eb  mov     ebx, eax
0x1800161ed  mov     [rsp+0F8h+var_7C], eax
0x1800161f1  cmp     [rsp+0F8h+var_70], rsi
0x1800161f9  jz      loc_180016363
0x1800161ff  mov     [rsp+0F8h+var_80], esi
0x180016203  mov     [rsp+0F8h+var_68], esi
0x18001620a  mov     [rsp+0F8h+var_60], rsi
0x180016212  mov     edx, dword ptr [rsp+0F8h+var_78]
0x180016219  mov     r8d, edx
0x18001621c  shl     r8d, 5
0x180016220  mov     [rsp+0F8h+var_68], r8d
0x180016228  mov     r9d, esi
0x18001622b  mov     [rsp+0F8h+var_80], esi
0x18001622f  cmp     r9d, edx
0x180016232  jnb     short loc_18001625D
0x180016234  mov     ecx, r9d
0x180016237  shl     rcx, 5
0x18001623b  mov     rax, [rsp+0F8h+var_70]
0x180016243  movzx   ecx, word ptr [rcx+rax+0Ah]
0x180016248  add     r8d, ecx
0x18001624b  mov     [rsp+0F8h+var_68], r8d
0x180016253  add     r9d, edi
0x180016256  mov     [rsp+0F8h+var_80], r9d
0x18001625b  jmp     short loc_18001622F
0x18001625d  test    r14b, r14b
0x180016260  jnz     short loc_1800162A3
0x180016262  mov     edi, r8d
0x180016265  mov     edx, r8d; uBytes
0x180016268  mov     ecx, 40h ; '@'; uFlags
0x18001626d  call    cs:__imp_LocalAlloc
0x180016273  mov     [rsp+0F8h+hMem], rax
0x180016278  test    rax, rax
0x18001627b  jnz     short loc_18001628B
0x18001627d  mov     ebx, 0C000009Ah
0x180016282  mov     [rsp+0F8h+var_7C], ebx
0x180016286  jmp     loc_180016363
0x18001628b  mov     r8, rdi; Size
0x18001628e  xor     edx, edx; Val
0x180016290  mov     rcx, rax; void *
0x180016293  call    memset_0
0x180016298  mov     edx, dword ptr [rsp+0F8h+var_78]
0x18001629f  mov     [rsp+0F8h+var_90], edx
0x1800162a3  mov     r15d, edx
0x1800162a6  shl     r15, 5
0x1800162aa  add     r15, [rsp+0F8h+hMem]
0x1800162af  mov     [rsp+0F8h+var_60], r15
0x1800162b7  mov     [rsp+0F8h+var_90], edx
0x1800162bb  mov     r13d, esi
0x1800162be  mov     [rsp+0F8h+var_80], esi
0x1800162c2  cmp     r13d, edx
0x1800162c5  jnb     loc_180016363
0x1800162cb  mov     edi, r13d
0x1800162ce  shl     rdi, 5
0x1800162d2  mov     rax, [rsp+0F8h+var_70]
0x1800162da  mov     ecx, [rdi+rax]
0x1800162dd  mov     rax, [rsp+0F8h+hMem]
0x1800162e2  mov     [rdi+rax], ecx
0x1800162e5  mov     rax, [rsp+0F8h+var_70]
0x1800162ed  movups  xmm0, xmmword ptr [rdi+rax+8]
0x1800162f2  mov     rax, [rsp+0F8h+hMem]
0x1800162f7  movdqu  xmmword ptr [rdi+rax+8], xmm0
0x1800162fd  mov     rdx, [rsp+0F8h+var_70]
0x180016305  movzx   r8d, word ptr [rdi+rdx+8]; Size
0x18001630b  mov     rdx, [rdi+rdx+10h]; Src
0x180016310  mov     rcx, r15; void *
0x180016313  call    memcpy_0
0x180016318  mov     rax, [rsp+0F8h+hMem]
0x18001631d  mov     [rdi+rax+10h], r15
0x180016322  mov     rax, [rsp+0F8h+var_70]
0x18001632a  mov     ecx, [rdi+rax+18h]
0x18001632e  mov     rax, [rsp+0F8h+hMem]
0x180016333  mov     [rdi+rax+18h], ecx
0x180016337  mov     rax, [rsp+0F8h+var_70]
0x18001633f  movzx   ecx, word ptr [rdi+rax+0Ah]
0x180016344  add     r15, rcx
0x180016347  mov     [rsp+0F8h+var_60], r15
0x18001634f  inc     r13d
0x180016352  mov     [rsp+0F8h+var_80], r13d
0x180016357  mov     edx, dword ptr [rsp+0F8h+var_78]
0x18001635e  jmp     loc_1800162C2
0x180016363  jmp     short loc_1800163C9
0x180016365  mov     ebx, eax
0x180016367  mov     rcx, [rsp+0F8h+var_70]; hMem
0x18001636f  test    rcx, rcx
0x180016372  jz      short loc_180016386
0x180016374  call    cs:__imp_LocalFree
0x18001637a  mov     [rsp+0F8h+var_70], 0
0x180016386  mov     r14b, [rsp+0F8h+var_98]
0x18001638b  test    r14b, r14b
0x18001638e  jnz     short loc_1800163A9
0x180016390  mov     rcx, [rsp+0F8h+hMem]; hMem
0x180016395  test    rcx, rcx
0x180016398  jz      short loc_1800163A9
0x18001639a  call    cs:__imp_LocalFree
0x1800163a0  mov     [rsp+0F8h+hMem], 0
0x1800163a9  mov     ecx, ebx; Status
0x1800163ab  call    cs:__imp_I_RpcMapWin32Status
0x1800163b1  mov     ebx, 0C0000001h
0x1800163b6  test    eax, eax
0x1800163b8  cmovs   ebx, eax
0x1800163bb  mov     [rsp+0F8h+var_7C], ebx
0x1800163bf  xor     esi, esi
0x1800163c1  mov     r12d, [rsp+0F8h+arg_8]
0x1800163c9  mov     rcx, [rsp+0F8h+arg_20]
0x1800163d1  mov     rax, [rsp+0F8h+hMem]
0x1800163d6  mov     [rcx], rax
0x1800163d9  mov     rcx, [rsp+0F8h+var_70]; hMem
0x1800163e1  test    rcx, rcx
0x1800163e4  jz      short loc_1800163EC
0x1800163e6  call    cs:__imp_LocalFree
0x1800163ec  test    ebx, ebx
0x1800163ee  js      loc_180016487
0x1800163f4  mov     r15, [rsp+0F8h+arg_18]
0x1800163fc  cmp     [rsp+0F8h+var_90], r12d
0x180016401  jz      short loc_18001640A
0x180016403  mov     edi, 0C00000C3h
0x180016408  jmp     short loc_180016454
0x18001640a  cmp     [rsp+0F8h+hMem], rsi
0x18001640f  jz      short loc_180016403
0x180016411  mov     r8, [r15]
0x180016414  mov     edi, esi
0x180016416  mov     ecx, esi
0x180016418  cmp     ecx, r12d
0x18001641b  jnb     short loc_180016450
0x18001641d  mov     edx, ecx
0x18001641f  shl     rdx, 5
0x180016423  mov     r9, [rsp+0F8h+hMem]
0x180016428  mov     eax, [rdx+r9]
0x18001642c  sub     eax, 6
0x18001642f  cmp     eax, 2
0x180016432  jbe     short loc_180016447
0x180016434  test    r8, r8
0x180016437  jz      short loc_180016403
0x180016439  mov     eax, [rdx+r9+18h]
0x18001643e  test    eax, eax
0x180016440  js      short loc_18001644B
0x180016442  cmp     eax, [r8]
0x180016445  jnb     short loc_18001644B
0x180016447  inc     ecx
0x180016449  jmp     short loc_180016418
0x18001644b  mov     edi, 0C00000C3h
0x180016450  test    edi, edi
0x180016452  jns     short loc_180016487
0x180016454  test    r14b, r14b
0x180016457  jnz     short loc_180016474
0x180016459  mov     rcx, [rsp+0F8h+hMem]; hMem
0x18001645e  test    rcx, rcx
0x180016461  jz      short loc_180016474
0x180016463  call    cs:__imp_LocalFree
0x180016469  mov     rax, [rsp+0F8h+arg_20]
0x180016471  mov     [rax], rsi
0x180016474  cmp     [r15], rsi
0x180016477  jz      short loc_180016485
0x180016479  mov     rcx, [r15]; hMem
0x18001647c  call    cs:__imp_LocalFree
0x180016482  mov     [r15], rsi
0x180016485  mov     ebx, edi
0x180016487  mov     eax, ebx
0x180016489  add     rsp, 0C0h
0x180016490  pop     r15
0x180016492  pop     r14
0x180016494  pop     r13
0x180016496  pop     r12
0x180016498  pop     rdi
0x180016499  pop     rsi
  ... truncated ...
```
