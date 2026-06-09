# LB_RESOURCE_ID_CONFIG_ENTRY::ParseConfiguration(void)

- ea: `0x1800222b4`
- end: `0x180022768`
- name: `?ParseConfiguration@LB_RESOURCE_ID_CONFIG_ENTRY@@QEAAJXZ`
- size: `1204`
- prototype: `__int64 __fastcall(LB_RESOURCE_ID_CONFIG_ENTRY *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022770`

## callees

- `0x180001336`
- `0x18000134e`
- `0x18001e3d4`
- `0x18001efe8`
- `0x180021238`
- `0x180021c30`
- `0x180021e48`
- `0x1800222b4`
- `0x1800231a0`
- `0x1800231d4`

## import_xrefs

- `KERNEL32!GetComputerNameExW` at `0x180022302`
- `KERNEL32!GetComputerNameExW` at `0x180022359`
- `KERNEL32!GetComputerNameExW` at `0x180022372`
- `KERNEL32!GetComputerNameExW` at `0x1800223b8`
- `KERNEL32!GetComputerNameExW` at `0x180022302`
- `KERNEL32!GetComputerNameExW` at `0x180022359`
- `KERNEL32!GetComputerNameExW` at `0x180022372`
- `KERNEL32!GetComputerNameExW` at `0x1800223b8`
- `KERNEL32!GetLastError` at `0x180022308`
- `KERNEL32!GetLastError` at `0x180022378`
- `KERNEL32!GetLastError` at `0x180022308`
- `KERNEL32!GetLastError` at `0x180022378`
- `RPCRT4!I_RpcFree` at `0x180022683`
- `RPCRT4!I_RpcFree` at `0x18002270b`
- `RPCRT4!I_RpcFree` at `0x180022714`
- `RPCRT4!I_RpcFree` at `0x180022741`
- `RPCRT4!I_RpcFree` at `0x18002274f`
- `RPCRT4!I_RpcFree` at `0x180022683`
- `RPCRT4!I_RpcFree` at `0x18002270b`
- `RPCRT4!I_RpcFree` at `0x180022714`
- `RPCRT4!I_RpcFree` at `0x180022741`
- `RPCRT4!I_RpcFree` at `0x18002274f`
- `RPCRT4!I_RpcAllocate` at `0x18002233e`
- `RPCRT4!I_RpcAllocate` at `0x180022399`
- `RPCRT4!I_RpcAllocate` at `0x18002245b`
- `RPCRT4!I_RpcAllocate` at `0x180022592`
- `RPCRT4!I_RpcAllocate` at `0x18002233e`
- `RPCRT4!I_RpcAllocate` at `0x180022399`
- `RPCRT4!I_RpcAllocate` at `0x18002245b`
- `RPCRT4!I_RpcAllocate` at `0x180022592`

## pseudocode

```c
__int64 __fastcall LB_RESOURCE_ID_CONFIG_ENTRY::ParseConfiguration(LB_RESOURCE_ID_CONFIG_ENTRY *this)
{
  const wchar_t *v1; // rdi
  unsigned __int16 *v2; // r14
  wchar_t *v4; // r12
  wchar_t *v5; // r15
  unsigned int v6; // ebx
  unsigned int v7; // eax
  WCHAR *v8; // rax
  unsigned int v9; // eax
  WCHAR *v10; // rax
  unsigned int v11; // r13d
  const wchar_t *v12; // rax
  wchar_t *v13; // rax
  unsigned __int16 *v14; // rbx
  wchar_t *v15; // rax
  const wchar_t *v16; // rax
  unsigned int v17; // edi
  wchar_t *v18; // rax
  LB_RPCHTTP_SERVER *v19; // rax
  LB_RPCHTTP_SERVER *v20; // rdi
  LB_RPCHTTP_SERVER *v21; // rax
  unsigned __int16 *v22; // rax
  unsigned __int16 v23; // bx
  unsigned __int16 v24; // ax
  unsigned int i; // r12d
  LB_RPCHTTP_SERVER *v26; // rax
  LB_RPCHTTP_SERVER *v27; // rax
  unsigned __int16 *v28; // rax
  wchar_t *j; // rax
  unsigned __int16 *v30; // rax
  unsigned __int16 v31; // r8
  LB_RPCHTTP_SERVER *v32; // rdi
  unsigned int k; // ebx
  LB_RPCHTTP_SERVER *v34; // rdx
  LB_RPCHTTP_SERVER *v35; // rax
  char *v36; // rcx
  LB_RPCHTTP_SERVER *v38; // rcx
  unsigned __int16 v39; // [rsp+20h] [rbp-48h]
  unsigned __int16 *String2; // [rsp+28h] [rbp-40h]
  WCHAR *v41; // [rsp+30h] [rbp-38h]
  wchar_t *v42; // [rsp+38h] [rbp-30h]
  WCHAR *v43; // [rsp+40h] [rbp-28h]
  LB_RPCHTTP_SERVER *v44[2]; // [rsp+48h] [rbp-20h] BYREF
  unsigned __int16 v45; // [rsp+B0h] [rbp+48h] BYREF
  unsigned __int16 v46; // [rsp+B8h] [rbp+50h] BYREF
  DWORD nSize; // [rsp+C0h] [rbp+58h] BYREF
  unsigned int v48; // [rsp+C8h] [rbp+60h]

  v1 = (const wchar_t *)*((_QWORD *)this + 14);
  v2 = 0;
  v44[1] = (LB_RPCHTTP_SERVER *)v44;
  v46 = 0;
  v45 = 0;
  String2 = (unsigned __int16 *)v1;
  v44[0] = (LB_RPCHTTP_SERVER *)v44;
  nSize = 0;
  v4 = 0;
  GetComputerNameExW(ComputerNamePhysicalNetBIOS, 0, &nSize);
  if ( GetLastError() == 234 )
  {
    v7 = 2 * nSize;
    if ( !is_mul_ok(nSize, 2u) )
      v7 = -1;
    v8 = (WCHAR *)I_RpcAllocate(v7);
    v43 = v8;
    v5 = v8;
    if ( v8 )
    {
      if ( GetComputerNameExW(ComputerNamePhysicalNetBIOS, v8, &nSize) )
      {
        nSize = 0;
        GetComputerNameExW(ComputerNamePhysicalDnsFullyQualified, 0, &nSize);
        if ( GetLastError() == 234 )
        {
          v9 = 2 * nSize;
          if ( !is_mul_ok(nSize, 2u) )
            v9 = -1;
          v10 = (WCHAR *)I_RpcAllocate(v9);
          v41 = v10;
          v4 = v10;
          if ( v10 )
          {
            if ( GetComputerNameExW(ComputerNamePhysicalDnsFullyQualified, v10, &nSize) )
            {
              v48 = 0;
              v11 = 0;
              while ( 1 )
              {
                v12 = (const wchar_t *)SkipWhiteSpace_0(v1);
                v13 = wcschr_0(v12, 0x3Bu);
                v42 = v13;
                if ( v13 )
                {
                  *v13 = 0;
                  v42 = v13 + 1;
                }
                v14 = 0;
                v15 = wcschr_0(v1, 0x2Cu);
                if ( v15 )
                {
                  *v15 = 0;
                  v16 = (const wchar_t *)SkipWhiteSpace_0(v15 + 1);
                  v14 = (unsigned __int16 *)v16;
                  v17 = 0;
                  do
                  {
                    v18 = wcschr_0(v16, 0x2Cu);
                    if ( !v18 )
                      break;
                    *v18 = 0;
                    ++v17;
                    v16 = (const wchar_t *)SkipWhiteSpace_0(v18 + 1);
                    if ( !v2 )
                      v2 = (unsigned __int16 *)v16;
                  }
                  while ( v16 );
                  v5 = v43;
                  v48 = v17;
                }
                v19 = (LB_RPCHTTP_SERVER *)I_RpcAllocate(0xD0u);
                if ( !v19 )
                  break;
                v20 = LB_RPCHTTP_SERVER::LB_RPCHTTP_SERVER(v19, (LB_RESOURCE_ID_CONFIG_ENTRY *)((char *)this + 48));
                if ( !v20 )
                  break;
                v21 = v44[1];
                if ( *(LB_RPCHTTP_SERVER ***)v44[1] != v44 )
LABEL_69:
                  __fastfail(3u);
                *((LB_RPCHTTP_SERVER **)v20 + 1) = v44[1];
                *(_QWORD *)v20 = v44;
                *(_QWORD *)v21 = v20;
                v44[1] = v20;
                RemoveTrailingSpaces(String2);
                v22 = DuplicateString(String2);
                *((_QWORD *)v20 + 3) = v22;
                if ( !v22 )
                  break;
                ++v11;
                if ( !wcsicmp_0(v5, String2) || !wcsicmp_0(v4, String2) )
                  *((_DWORD *)v20 + 51) = 1;
                if ( v14 )
                {
                  if ( *v14 == 48 )
                  {
                    v23 = 0;
                    v46 = 0;
                  }
                  else
                  {
                    RemoveTrailingSpaces(v14);
                    v6 = EndpointToPortNumber(v14, &v46);
                    if ( v6 )
                      goto LABEL_59;
                    v23 = v46;
                  }
                  v39 = v23;
                  *((_WORD *)v20 + 16) = v23;
                  if ( v2 )
                  {
                    if ( *v2 == 48 )
                    {
                      v24 = 0;
                      v45 = 0;
                    }
                    else
                    {
                      RemoveTrailingSpaces(v2);
                      v6 = EndpointToPortNumber(v2, &v45);
                      if ( v6 )
                        goto LABEL_59;
                      v24 = v45;
                      v23 = v39;
                    }
                    for ( i = 1; ; ++i )
                    {
                      *((_WORD *)v20 + 17) = v24;
                      if ( i >= v48 )
                      {
                        v4 = v41;
                        goto LABEL_55;
                      }
                      v26 = (LB_RPCHTTP_SERVER *)I_RpcAllocate(0xD0u);
                      if ( !v26 )
                        break;
                      v20 = LB_RPCHTTP_SERVER::LB_RPCHTTP_SERVER(
                              v26,
                              (LB_RESOURCE_ID_CONFIG_ENTRY *)((char *)this + 48));
                      if ( !v20 )
                        break;
                      v27 = v44[1];
                      if ( *(LB_RPCHTTP_SERVER ***)v44[1] != v44 )
                        goto LABEL_69;
                      *((LB_RPCHTTP_SERVER **)v20 + 1) = v44[1];
                      *(_QWORD *)v20 = v44;
                      *(_QWORD *)v27 = v20;
                      v44[1] = v20;
                      v28 = DuplicateString(String2);
                      *((_QWORD *)v20 + 3) = v28;
                      if ( !v28 )
                        break;
                      *((_WORD *)v20 + 16) = v23;
                      for ( j = wcschr_0(v2, 0); !*j; ++j )
                        ;
                      v30 = (unsigned __int16 *)SkipWhiteSpace_0(j);
                      v2 = v30;
                      if ( *v30 == 48 )
                      {
                        v24 = v31;
                        v45 = v31;
                      }
                      else
                      {
                        RemoveTrailingSpaces(v30);
                        v6 = EndpointToPortNumber(v2, &v45);
                        if ( v6 )
                          goto LABEL_58;
                        v24 = v45;
                        v23 = v39;
                      }
                      ++v11;
                    }
                    v6 = 14;
LABEL_58:
                    v4 = v41;
                    goto LABEL_59;
                  }
                }
LABEL_55:
                v2 = 0;
                if ( !v42 )
                {
                  I_RpcFree(*((void **)this + 14));
                  *((_QWORD *)this + 14) = 0;
                  for ( k = 0; k < v11; ++k )
                    LB_RESOURCE_ID_CONFIG_ENTRY::AddReference(this);
                  v34 = v44[0];
                  if ( (LB_RPCHTTP_SERVER **)v44[0] != v44 )
                  {
                    do
                    {
                      v35 = v34;
                      v34 = *(LB_RPCHTTP_SERVER **)v34;
                      *((_QWORD *)v35 + 8) = this;
                    }
                    while ( v34 != (LB_RPCHTTP_SERVER *)v44 );
                    v34 = v44[0];
                  }
                  *((_DWORD *)this + 10) = v11;
                  v36 = (char *)this + 24;
                  if ( v34 == (LB_RPCHTTP_SERVER *)v44 )
                  {
                    *((_QWORD *)this + 4) = (char *)this + 24;
                    *(_QWORD *)v36 = v36;
                  }
                  else
                  {
                    *(_OWORD *)v36 = *(_OWORD *)v44;
                    *(_QWORD *)(*(_QWORD *)v36 + 8LL) = v36;
                    **((_QWORD **)this + 4) = (char *)this + 24;
                    v44[1] = (LB_RPCHTTP_SERVER *)v44;
                    v44[0] = (LB_RPCHTTP_SERVER *)v44;
                  }
                  I_RpcFree(v5);
                  I_RpcFree(v4);
                  return 0;
                }
                v1 = v42;
                String2 = v42;
              }
            }
          }
        }
      }
    }
  }
  else
  {
    v5 = 0;
  }
  v6 = 14;
LABEL_59:
  v32 = v44[0];
  while ( v32 != (LB_RPCHTTP_SERVER *)v44 )
  {
    v38 = v32;
    v32 = *(LB_RPCHTTP_SERVER **)v32;
    LB_RPCHTTP_SERVER::RemoveReference(v38);
  }
  if ( v5 )
    I_RpcFree(v5);
  if ( v4 )
    I_RpcFree(v4);
  return v6;
}

```

## disassembly

```asm
0x1800222b4  push    rbp
0x1800222b6  push    rbx
0x1800222b7  push    rsi
0x1800222b8  push    rdi
0x1800222b9  push    r12
0x1800222bb  push    r13
0x1800222bd  push    r14
0x1800222bf  push    r15
0x1800222c1  mov     rbp, rsp
0x1800222c4  sub     rsp, 68h
0x1800222c8  mov     rdi, [rcx+70h]
0x1800222cc  lea     rax, [rbp+var_20]
0x1800222d0  xor     r14d, r14d
0x1800222d3  mov     [rbp+var_20+8], rax
0x1800222d7  xor     edx, edx; lpBuffer
0x1800222d9  mov     [rbp+arg_8], r14w
0x1800222de  mov     rsi, rcx
0x1800222e1  mov     [rbp+arg_0], r14w
0x1800222e6  lea     rax, [rbp+var_20]
0x1800222ea  mov     [rbp+String2], rdi
0x1800222ee  lea     r8, [rbp+nSize]; nSize
0x1800222f2  mov     [rbp+var_20], rax
0x1800222f6  lea     ebx, [rdx+4]
0x1800222f9  mov     [rbp+nSize], r14d
0x1800222fd  mov     ecx, ebx; NameType
0x1800222ff  mov     r12d, r14d
0x180022302  call    cs:__imp_GetComputerNameExW
0x180022308  call    cs:__imp_GetLastError
0x18002230e  mov     r13d, 0EAh
0x180022314  cmp     eax, r13d
0x180022317  jz      short loc_180022326
0x180022319  mov     r15d, r14d
0x18002231c  mov     ebx, 0Eh
0x180022321  jmp     loc_180022676
0x180022326  mov     ecx, [rbp+nSize]
0x180022329  mov     eax, 2
0x18002232e  mul     rcx
0x180022331  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180022338  cmovb   rax, rcx
0x18002233c  mov     ecx, eax; Size
0x18002233e  call    cs:__imp_I_RpcAllocate
0x180022344  mov     [rbp+var_28], rax
0x180022348  mov     r15, rax
0x18002234b  test    rax, rax
0x18002234e  jz      short loc_18002231C
0x180022350  lea     r8, [rbp+nSize]; nSize
0x180022354  mov     rdx, rax; lpBuffer
0x180022357  mov     ecx, ebx; NameType
0x180022359  call    cs:__imp_GetComputerNameExW
0x18002235f  test    eax, eax
0x180022361  jz      short loc_18002231C
0x180022363  xor     edx, edx; lpBuffer
0x180022365  mov     [rbp+nSize], r14d
0x180022369  lea     r8, [rbp+nSize]; nSize
0x18002236d  lea     ebx, [rdx+7]
0x180022370  mov     ecx, ebx; NameType
0x180022372  call    cs:__imp_GetComputerNameExW
0x180022378  call    cs:__imp_GetLastError
0x18002237e  cmp     eax, r13d
0x180022381  jnz     short loc_18002231C
0x180022383  mov     ecx, [rbp+nSize]
0x180022386  lea     eax, [rbx-5]
0x180022389  mul     rcx
0x18002238c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180022393  cmovb   rax, rcx
0x180022397  mov     ecx, eax; Size
0x180022399  call    cs:__imp_I_RpcAllocate
0x18002239f  mov     [rbp+var_38], rax
0x1800223a3  mov     r12, rax
0x1800223a6  test    rax, rax
0x1800223a9  jz      loc_18002231C
0x1800223af  lea     r8, [rbp+nSize]; nSize
0x1800223b3  mov     rdx, rax; lpBuffer
0x1800223b6  mov     ecx, ebx; NameType
0x1800223b8  call    cs:__imp_GetComputerNameExW
0x1800223be  test    eax, eax
0x1800223c0  jz      loc_18002231C
0x1800223c6  mov     [rbp+arg_18], r14d
0x1800223ca  mov     r13d, r14d
0x1800223cd  mov     rcx, rdi
0x1800223d0  call    SkipWhiteSpace_0
0x1800223d5  mov     edx, 3Bh ; ';'; Ch
0x1800223da  mov     rcx, rax; Str
0x1800223dd  call    wcschr_0
0x1800223e2  mov     [rbp+var_30], rax
0x1800223e6  test    rax, rax
0x1800223e9  jz      short loc_1800223F7
0x1800223eb  mov     [rax], r14w
0x1800223ef  add     rax, 2
0x1800223f3  mov     [rbp+var_30], rax
0x1800223f7  mov     edx, 2Ch ; ','; Ch
0x1800223fc  mov     rcx, rdi; Str
0x1800223ff  mov     rbx, r14
0x180022402  call    wcschr_0
0x180022407  test    rax, rax
0x18002240a  jz      short loc_180022456
0x18002240c  xor     r15d, r15d
0x18002240f  lea     rcx, [rax+2]
0x180022413  mov     [rax], r15w
0x180022417  call    SkipWhiteSpace_0
0x18002241c  mov     rbx, rax
0x18002241f  mov     edi, r15d
0x180022422  mov     edx, 2Ch ; ','; Ch
0x180022427  mov     rcx, rax; Str
0x18002242a  call    wcschr_0
0x18002242f  test    rax, rax
0x180022432  jz      short loc_18002244F
0x180022434  lea     rcx, [rax+2]
0x180022438  mov     [rax], r15w
0x18002243c  inc     edi
0x18002243e  call    SkipWhiteSpace_0
0x180022443  test    r14, r14
0x180022446  cmovz   r14, rax
0x18002244a  test    rax, rax
0x18002244d  jnz     short loc_180022422
0x18002244f  mov     r15, [rbp+var_28]
0x180022453  mov     [rbp+arg_18], edi
0x180022456  mov     ecx, 0D0h; Size
0x18002245b  call    cs:__imp_I_RpcAllocate
0x180022461  test    rax, rax
0x180022464  jz      loc_18002231C
0x18002246a  lea     rdx, [rsi+30h]; struct MUTEX *
0x18002246e  mov     rcx, rax; this
0x180022471  call    ??0LB_RPCHTTP_SERVER@@QEAA@PEAVMUTEX@@@Z; LB_RPCHTTP_SERVER::LB_RPCHTTP_SERVER(MUTEX *)
0x180022476  mov     rdi, rax
0x180022479  test    rax, rax
0x18002247c  jz      loc_18002231C
0x180022482  mov     rax, [rbp+var_20+8]
0x180022486  lea     rcx, [rbp+var_20]
0x18002248a  cmp     [rax], rcx
0x18002248d  jnz     loc_18002271E
0x180022493  mov     [rdi+8], rax
0x180022497  lea     rcx, [rbp+var_20]
0x18002249b  mov     [rdi], rcx
0x18002249e  mov     rcx, [rbp+String2]; unsigned __int16 *
0x1800224a2  mov     [rax], rdi
0x1800224a5  mov     [rbp+var_20+8], rdi
0x1800224a9  call    ?RemoveTrailingSpaces@@YAXPEAG@Z; RemoveTrailingSpaces(ushort *)
0x1800224ae  mov     rcx, [rbp+String2]; Src
0x1800224b2  call    ?DuplicateString@@YAPEAGPEBG@Z; DuplicateString(ushort const *)
0x1800224b7  mov     [rdi+18h], rax
0x1800224bb  test    rax, rax
0x1800224be  jz      loc_18002231C
0x1800224c4  mov     rdx, [rbp+String2]; String2
0x1800224c8  mov     rcx, r15; String1
0x1800224cb  inc     r13d
0x1800224ce  call    _wcsicmp_0
0x1800224d3  xor     r8d, r8d
0x1800224d6  test    eax, eax
0x1800224d8  jz      short loc_1800224ED
0x1800224da  mov     rdx, [rbp+String2]; String2
0x1800224de  mov     rcx, r12; String1
0x1800224e1  call    _wcsicmp_0
0x1800224e6  xor     r8d, r8d
0x1800224e9  test    eax, eax
0x1800224eb  jnz     short loc_1800224F7
0x1800224ed  mov     dword ptr [rdi+0CCh], 1
0x1800224f7  test    rbx, rbx
0x1800224fa  jz      loc_180022655
0x180022500  cmp     word ptr [rbx], 30h ; '0'
0x180022504  jnz     short loc_18002250F
0x180022506  mov     ebx, r8d
0x180022509  mov     [rbp+arg_8], bx
0x18002250d  jmp     short loc_180022534
0x18002250f  mov     rcx, rbx; unsigned __int16 *
0x180022512  call    ?RemoveTrailingSpaces@@YAXPEAG@Z; RemoveTrailingSpaces(ushort *)
0x180022517  lea     rdx, [rbp+arg_8]; unsigned __int16 *
0x18002251b  mov     rcx, rbx; unsigned __int16 *
0x18002251e  call    ?EndpointToPortNumber@@YAJPEAGAEAG@Z; EndpointToPortNumber(ushort *,ushort &)
0x180022523  xor     r8d, r8d
0x180022526  mov     ebx, eax
0x180022528  test    eax, eax
0x18002252a  jnz     loc_180022676
0x180022530  movzx   ebx, [rbp+arg_8]
0x180022534  mov     dword ptr [rbp+var_48], ebx
0x180022537  mov     [rdi+20h], bx
0x18002253b  test    r14, r14
0x18002253e  jz      loc_180022655
0x180022544  cmp     word ptr [r14], 30h ; '0'
0x180022549  jnz     short loc_180022554
0x18002254b  mov     eax, r8d
0x18002254e  mov     [rbp+arg_0], ax
0x180022552  jmp     short loc_180022579
0x180022554  mov     rcx, r14; unsigned __int16 *
0x180022557  call    ?RemoveTrailingSpaces@@YAXPEAG@Z; RemoveTrailingSpaces(ushort *)
0x18002255c  lea     rdx, [rbp+arg_0]; unsigned __int16 *
0x180022560  mov     rcx, r14; unsigned __int16 *
0x180022563  call    ?EndpointToPortNumber@@YAJPEAGAEAG@Z; EndpointToPortNumber(ushort *,ushort &)
0x180022568  mov     ebx, eax
0x18002256a  test    eax, eax
0x18002256c  jnz     loc_180022676
0x180022572  movzx   eax, [rbp+arg_0]
0x180022576  mov     ebx, dword ptr [rbp+var_48]
0x180022579  mov     r12d, 1
0x18002257f  mov     [rdi+22h], ax
0x180022583  cmp     r12d, [rbp+arg_18]
0x180022587  jnb     loc_180022651
0x18002258d  mov     ecx, 0D0h; Size
0x180022592  call    cs:__imp_I_RpcAllocate
0x180022598  test    rax, rax
0x18002259b  jz      loc_18002266D
0x1800225a1  lea     rdx, [rsi+30h]; struct MUTEX *
0x1800225a5  mov     rcx, rax; this
0x1800225a8  call    ??0LB_RPCHTTP_SERVER@@QEAA@PEAVMUTEX@@@Z; LB_RPCHTTP_SERVER::LB_RPCHTTP_SERVER(MUTEX *)
0x1800225ad  mov     rdi, rax
0x1800225b0  test    rax, rax
0x1800225b3  jz      loc_18002266D
0x1800225b9  mov     rax, [rbp+var_20+8]
0x1800225bd  lea     rcx, [rbp+var_20]
0x1800225c1  cmp     [rax], rcx
0x1800225c4  jnz     loc_18002271E
0x1800225ca  mov     [rdi+8], rax
0x1800225ce  lea     rcx, [rbp+var_20]
0x1800225d2  mov     [rdi], rcx
0x1800225d5  mov     rcx, [rbp+String2]; Src
0x1800225d9  mov     [rax], rdi
0x1800225dc  mov     [rbp+var_20+8], rdi
0x1800225e0  call    ?DuplicateString@@YAPEAGPEBG@Z; DuplicateString(ushort const *)
0x1800225e5  mov     [rdi+18h], rax
0x1800225e9  test    rax, rax
0x1800225ec  jz      short loc_18002266D
0x1800225ee  xor     edx, edx; Ch
0x1800225f0  mov     [rdi+20h], bx
0x1800225f4  mov     rcx, r14; Str
0x1800225f7  call    wcschr_0
0x1800225fc  xor     r8d, r8d
0x1800225ff  jmp     short loc_180022605
0x180022601  add     rax, 2
0x180022605  cmp     [rax], r8w
0x180022609  jz      short loc_180022601
0x18002260b  mov     rcx, rax
0x18002260e  call    SkipWhiteSpace_0
0x180022613  mov     r14, rax
0x180022616  cmp     word ptr [rax], 30h ; '0'
0x18002261a  jnz     short loc_180022625
0x18002261c  mov     eax, r8d
0x18002261f  mov     [rbp+arg_0], ax
0x180022623  jmp     short loc_180022646
0x180022625  mov     rcx, r14; unsigned __int16 *
0x180022628  call    ?RemoveTrailingSpaces@@YAXPEAG@Z; RemoveTrailingSpaces(ushort *)
0x18002262d  lea     rdx, [rbp+arg_0]; unsigned __int16 *
0x180022631  mov     rcx, r14; unsigned __int16 *
0x180022634  call    ?EndpointToPortNumber@@YAJPEAGAEAG@Z; EndpointToPortNumber(ushort *,ushort &)
0x180022639  mov     ebx, eax
0x18002263b  test    eax, eax
0x18002263d  jnz     short loc_180022672
0x18002263f  movzx   eax, [rbp+arg_0]
0x180022643  mov     ebx, dword ptr [rbp+var_48]
0x180022646  inc     r13d
0x180022649  inc     r12d
0x18002264c  jmp     loc_18002257F
0x180022651  mov     r12, [rbp+var_38]
0x180022655  mov     rax, [rbp+var_30]
0x180022659  xor     r14d, r14d
0x18002265c  test    rax, rax
0x18002265f  jz      short loc_18002267F
0x180022661  mov     rdi, rax
0x180022664  mov     [rbp+String2], rax
0x180022668  jmp     loc_1800223CD
0x18002266d  mov     ebx, 0Eh
0x180022672  mov     r12, [rbp+var_38]
0x180022676  mov     rdi, [rbp+var_20]
0x18002267a  jmp     loc_180022730
0x18002267f  mov     rcx, [rsi+70h]; Object
0x180022683  call    cs:__imp_I_RpcFree
0x180022689  mov     [rsi+70h], r14
0x18002268d  mov     ebx, r14d
0x180022690  test    r13d, r13d
0x180022693  jz      short loc_1800226A4
0x180022695  mov     rcx, rsi; this
0x180022698  call    ?AddReference@LB_RESOURCE_ID_CONFIG_ENTRY@@QEAAXXZ; LB_RESOURCE_ID_CONFIG_ENTRY::AddReference(void)
0x18002269d  inc     ebx
0x18002269f  cmp     ebx, r13d
0x1800226a2  jb      short loc_180022695
0x1800226a4  mov     rdx, [rbp+var_20]
0x1800226a8  lea     rax, [rbp+var_20]
0x1800226ac  cmp     rdx, rax
0x1800226af  jz      short loc_1800226C8
0x1800226b1  lea     rax, [rdx]
0x1800226b4  mov     rdx, [rdx]
0x1800226b7  mov     [rax+40h], rsi
0x1800226bb  lea     rax, [rbp+var_20]
0x1800226bf  cmp     rdx, rax
0x1800226c2  jnz     short loc_1800226B1
0x1800226c4  mov     rdx, [rbp+var_20]
0x1800226c8  lea     rax, [rbp+var_20]
0x1800226cc  mov     [rsi+28h], r13d
0x1800226d0  lea     rcx, [rsi+18h]
0x1800226d4  cmp     rdx, rax
0x1800226d7  jnz     short loc_1800226E2
0x1800226d9  mov     [rcx+8], rcx
0x1800226dd  mov     [rcx], rcx
0x1800226e0  jmp     short loc_180022708
0x1800226e2  movups  xmm0, xmmword ptr [rbp+var_20]
0x1800226e6  movdqu  xmmword ptr [rcx], xmm0
0x1800226ea  mov     rax, [rcx]
0x1800226ed  mov     [rax+8], rcx
0x1800226f1  mov     rax, [rcx+8]
0x1800226f5  mov     [rax], rcx
0x1800226f8  lea     rax, [rbp+var_20]
  ... truncated ...
```
