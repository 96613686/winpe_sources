# WsEnumUseInfo

- ea: `0x1800031d0`
- end: `0x1800038bf`
- name: `WsEnumUseInfo`
- size: `1775`
- prototype: `__int64 __fastcall(PLUID SourceLuid, DWORD, __int64 *, unsigned __int16 *, unsigned int, HLOCAL *, unsigned int, _DWORD *, _DWORD *, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800038d0`

## callees

- `0x1800024a0`
- `0x1800031d0`
- `0x1800051c0`
- `0x180005470`
- `0x1800054d0`
- `0x18000a650`
- `0x18001e420`
- `0x18001ed46`

## import_xrefs

- `ntdll!RtlCopyLuid` at `0x180003271`
- `ntdll!RtlCopyLuid` at `0x1800034ac`
- `ntdll!RtlCopyLuid` at `0x180003271`
- `ntdll!RtlCopyLuid` at `0x1800034ac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800033d9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800033d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003347`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000356a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003624`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003648`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003658`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000375e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800038af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003347`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000356a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003624`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003648`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003658`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000375e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800038af`

## pseudocode

```c
__int64 __fastcall WsEnumUseInfo(
        PLUID SourceLuid,
        DWORD a2,
        __int64 *a3,
        unsigned __int16 *a4,
        unsigned int a5,
        HLOCAL *a6,
        unsigned int a7,
        _DWORD *a8,
        _DWORD *a9,
        int *a10)
{
  __int64 *v11; // r14
  struct _LUID *v12; // rax
  __int64 *v13; // rsi
  unsigned int v14; // r15d
  int v15; // r12d
  __int64 v16; // rdi
  unsigned int Info; // edi
  unsigned __int16 *v18; // r8
  unsigned __int16 v19; // cx
  int v20; // r9d
  unsigned int v21; // eax
  HLOCAL v22; // rax
  HLOCAL *v23; // rsi
  char *v24; // rax
  char *v25; // r12
  char *v26; // r15
  unsigned int v27; // esi
  __int64 v28; // rdi
  int v29; // eax
  _QWORD *v30; // rdi
  __int16 v31; // cx
  int v32; // eax
  void *v33; // rcx
  unsigned int v35; // edi
  __int64 v36; // r12
  _DWORD *v37; // rdx
  unsigned int v38; // ebx
  HLOCAL *v40; // rdi
  unsigned int v41; // eax
  int v42; // eax
  unsigned __int16 *v43; // r10
  unsigned int v44; // ecx
  int v45; // r11d
  __int64 v46; // r10
  int v47; // eax
  unsigned __int16 *v48; // r11
  unsigned int i; // edi
  __int64 v50; // r10
  __int64 v51; // r11
  unsigned __int16 *v52; // rax
  unsigned int v53; // [rsp+50h] [rbp-89h]
  HLOCAL hMem; // [rsp+58h] [rbp-81h] BYREF
  char *v55; // [rsp+60h] [rbp-79h] BYREF
  unsigned __int16 *v56; // [rsp+68h] [rbp-71h]
  int *v57; // [rsp+70h] [rbp-69h]
  _DWORD *v58; // [rsp+78h] [rbp-61h]
  HLOCAL *v59; // [rsp+80h] [rbp-59h]
  HLOCAL v60; // [rsp+88h] [rbp-51h] BYREF
  __int64 v61; // [rsp+90h] [rbp-49h]
  PLUID SourceLuida; // [rsp+98h] [rbp-41h]
  int v63; // [rsp+A0h] [rbp-39h] BYREF
  int v64; // [rsp+A4h] [rbp-35h]
  struct _LUID DestinationLuid[2]; // [rsp+A8h] [rbp-31h] BYREF
  _QWORD v66[2]; // [rsp+B8h] [rbp-21h] BYREF
  int v67; // [rsp+140h] [rbp+67h]

  v11 = a3;
  v12 = SourceLuid;
  v57 = a10;
  v13 = a3;
  v56 = a4;
  v14 = 0;
  v15 = 0;
  SourceLuida = SourceLuid;
  v59 = a6;
  v58 = a9;
  while ( v13 )
  {
    v16 = v13[4];
    hMem = 0;
    memset(v66, 0, 12);
    *(_OWORD *)&DestinationLuid[0].LowPart = 0;
    v63 = 1;
    v64 = 6;
    RtlCopyLuid((PLUID)&DestinationLuid[0].HighPart, v12);
    *(_QWORD *)((char *)v66 + 4) = 0;
    DestinationLuid[0].LowPart = 2;
    Info = WsDeviceControlGetInfo(0, v16, 1311139, &v63, 36, &hMem, -1, 1136);
    if ( Info )
    {
      if ( hMem )
        LocalFree(hMem);
      return Info;
    }
    v18 = (unsigned __int16 *)hMem;
    if ( !hMem )
      return 2140;
    v19 = 2 * *(_WORD *)(v13[1] + 4);
    *((_WORD *)hMem + 1) = v19;
    *v18 = v19;
    *((_QWORD *)v18 + 1) = v13[1] + 8;
    if ( a7 == -1 )
    {
      v20 = USE_FIXED_LENGTH(a2);
      if ( a2 >= 2 )
        v20 += v18[16] + 2;
      if ( v14 >= ~(v20 + 2 * ((unsigned int)*v18 + 2 + *((_DWORD *)v13 + 6))) )
        return 2140;
      v14 += v20 + 2 * (*v18 + 2 + *((_DWORD *)v13 + 6));
      if ( a2 >= 2 )
      {
        v47 = v18[24];
        if ( (_WORD)v47 )
          v14 += v47 + 2;
      }
      if ( a2 >= 5 )
        v14 += 64;
    }
    LocalFree(v18);
    v13 = (__int64 *)*v13;
    ++v15;
    v12 = SourceLuida;
  }
  v61 = 32;
  v53 = 112;
  if ( a7 == -1 )
  {
    if ( a2 > 1 )
    {
      if ( a5 )
      {
        v43 = v56;
        do
        {
          v44 = USE_TOTAL_LENGTH(a2, (unsigned int)*v43 + 4, (unsigned int)v43[16] + 2) + v14 + 512;
          v43 = (unsigned __int16 *)(v46 + 96);
          v14 = v44 + 48;
          if ( a2 < 5 )
            v14 = v44;
        }
        while ( v45 + 1 < a5 );
      }
    }
    else if ( a5 )
    {
      v48 = v56;
      for ( i = 0; i < a5; ++i )
      {
        v14 += USE_TOTAL_LENGTH(a2, (unsigned int)*v48 + 4, (unsigned int)v48[16] + 2);
        v48 = (unsigned __int16 *)(v50 + v51);
      }
    }
  }
  else
  {
    if ( a7 + 2 < a7 )
      return 534;
    v14 = (a7 + 1) & 0xFFFFFFFE;
    switch ( a2 )
    {
      case 5u:
        v21 = 112;
        break;
      case 4u:
        v21 = 80;
        break;
      case 3u:
        v21 = 64;
        break;
      case 2u:
        v21 = 56;
        break;
      default:
        v21 = 16;
        if ( a2 == 1 )
          v21 = 40;
        break;
    }
    if ( v14 < v21 )
    {
      *v59 = 0;
      *a8 = 0;
      *v58 = v15 + a5;
      return 234;
    }
  }
  v22 = LocalAlloc(0x40u, v14);
  v23 = v59;
  *v59 = v22;
  if ( !v22 )
    return 8;
  memset_0(v22, 0, v14);
  v24 = (char *)*v23;
  switch ( a2 )
  {
    case 5u:
      goto LABEL_64;
    case 4u:
      v53 = 80;
      goto LABEL_64;
    case 3u:
      v53 = 64;
LABEL_64:
      v25 = &v24[v14];
      hMem = *v23;
      v55 = v25;
      v26 = v24;
      goto LABEL_65;
    case 2u:
      v53 = 56;
      goto LABEL_64;
  }
  hMem = *v23;
  v25 = &v24[v14];
  v55 = v25;
  v26 = v24;
  if ( a2 == 1 )
  {
    v53 = 40;
    goto LABEL_30;
  }
  v53 = 16;
  if ( a2 )
  {
LABEL_65:
    v61 = 96;
    goto LABEL_30;
  }
  v61 = 24;
LABEL_30:
  if ( !v57 )
  {
    v27 = 0;
    *a8 = 0;
    goto LABEL_32;
  }
  v42 = *v57;
  v27 = *v57 & 0x7FFFFFFF;
  *a8 = 0;
  if ( v42 >= 0 )
  {
LABEL_32:
    while ( v11 )
    {
      if ( v27 <= *((_DWORD *)v11 + 10) )
      {
        v28 = v11[4];
        *(_OWORD *)&DestinationLuid[0].LowPart = 0;
        v60 = 0;
        memset(v66, 0, 12);
        v63 = 1;
        v64 = 6;
        RtlCopyLuid((PLUID)&DestinationLuid[0].HighPart, SourceLuida);
        DestinationLuid[0].LowPart = a2;
        *(_QWORD *)((char *)v66 + 4) = 0;
        v29 = 552;
        if ( a2 != 1 )
          v29 = 1136;
        if ( (unsigned int)WsDeviceControlGetInfo(0, v28, 1311139, &v63, 36, &v60, -1, v29) )
        {
          if ( v60 )
            LocalFree(v60);
        }
        else
        {
          v30 = v60;
          if ( v60 )
          {
            v31 = 2 * *(_WORD *)(v11[1] + 4);
            *((_WORD *)v60 + 1) = v31;
            *(_WORD *)v30 = v31;
            v30[1] = v11[1] + 8;
            if ( &v26[v53] >= v25 )
            {
              v33 = v30;
LABEL_58:
              v38 = 234;
              LocalFree(v33);
              if ( v57 )
                *v57 = *((_DWORD *)v11 + 10);
              v41 = a5;
              v37 = v58;
              do
              {
                *v37 = ++v41;
                v11 = (__int64 *)*v11;
              }
              while ( v11 );
              v67 = v41;
              goto LABEL_48;
            }
            v32 = WsFillUseBuffer(a2, (_DWORD)v11, (_DWORD)v30, (unsigned int)&hMem, (__int64)&v55, v53);
            v33 = v30;
            if ( !v32 )
              goto LABEL_58;
            ++*a8;
            LocalFree(v30);
            v26 = (char *)hMem;
            v25 = v55;
          }
        }
      }
      v11 = (__int64 *)*v11;
    }
    v27 = 0;
  }
  v35 = 0;
  v36 = v61;
  while ( 1 )
  {
    if ( v35 >= a5 )
    {
      if ( v57 )
        *v57 = 0;
      v37 = v58;
      v38 = 0;
      v67 = 0;
      *v58 = 0;
      goto LABEL_48;
    }
    v52 = v56;
    if ( v27 <= *((_DWORD *)v56 + 4) )
      break;
LABEL_96:
    v56 = (unsigned __int16 *)((char *)v52 + v36);
    ++v35;
  }
  if ( (unsigned int)WsGetCombinedUseInfo(a2, v53, 0, (_DWORD)v56, (__int64)&hMem, (__int64)&v55, (__int64)a8) != 234 )
  {
    v52 = v56;
    goto LABEL_96;
  }
  if ( v57 )
    *v57 = *((_DWORD *)v56 + 4) | 0x80000000;
  v37 = v58;
  v38 = 234;
  v67 = a5 - v35;
  *v58 = a5 - v35;
LABEL_48:
  *v37 = *a8 + v67;
  if ( v38 == 234 && a7 == -1 )
  {
    v40 = v59;
    LocalFree(*v59);
    v38 = 8;
    goto LABEL_101;
  }
  if ( !*a8 )
  {
    v40 = v59;
    LocalFree(*v59);
LABEL_101:
    *v40 = 0;
  }
  return v38;
}

```

## disassembly

```asm
0x1800031d0  push    rbp
0x1800031d2  push    rbx
0x1800031d3  push    rsi
0x1800031d4  push    r12
0x1800031d6  push    r13
0x1800031d8  push    r14
0x1800031da  push    r15
0x1800031dc  lea     rbp, [rsp-7]
0x1800031e1  sub     rsp, 0E0h
0x1800031e8  mov     rax, cs:__security_cookie
0x1800031ef  xor     rax, rsp
0x1800031f2  mov     [rbp+37h+var_48], rax
0x1800031f6  mov     r13, [rbp+37h+arg_38]
0x1800031fa  mov     ebx, edx
0x1800031fc  mov     rdx, [rbp+37h+arg_48]
0x180003203  mov     r14, r8
0x180003206  mov     r8, [rbp+37h+arg_40]
0x18000320d  mov     rax, rcx
0x180003210  mov     [rbp+37h+var_A0], rdx
0x180003214  mov     rsi, r14
0x180003217  xor     edx, edx
0x180003219  mov     [rbp+37h+var_A8], r9
0x18000321d  mov     r9, [rbp+37h+arg_28]
0x180003221  mov     r15d, edx
0x180003224  mov     r12d, edx
0x180003227  mov     [rbp+37h+SourceLuid], rcx
0x18000322b  mov     [rbp+37h+var_90], r9
0x18000322f  mov     [rbp+37h+var_98], r8
0x180003233  mov     [rsp+110h+var_38], rdi
0x18000323b  test    rsi, rsi
0x18000323e  jz      loc_18000335E
0x180003244  mov     rdi, [rsi+20h]
0x180003248  lea     rcx, [rbp+37h+DestinationLuid.HighPart]; DestinationLuid
0x18000324c  mov     [rsp+110h+hMem], rdx
0x180003251  xorps   xmm0, xmm0
0x180003254  mov     [rbp+37h+var_58], rdx
0x180003258  mov     [rbp+37h+var_50], edx
0x18000325b  mov     rdx, rax; SourceLuid
0x18000325e  movdqu  xmmword ptr [rbp-31h], xmm0
0x180003263  mov     [rbp+37h+var_70], 1
0x18000326a  mov     [rbp+37h+var_6C], 6
0x180003271  call    cs:__imp_RtlCopyLuid
0x180003277  xor     eax, eax
0x180003279  mov     [rsp+110h+var_D8], 470h
0x180003281  mov     [rbp+37h+var_58+4], rax
0x180003285  lea     r9, [rbp+37h+var_70]
0x180003289  lea     rax, [rsp+110h+hMem]
0x18000328e  mov     dword ptr [rsp+110h+var_E0], 0FFFFFFFFh
0x180003296  mov     [rsp+110h+var_E8], rax
0x18000329b  mov     r8d, 1401A3h
0x1800032a1  mov     rdx, rdi
0x1800032a4  mov     dword ptr [rsp+110h+var_F0], 24h ; '$'
0x1800032ac  xor     ecx, ecx
0x1800032ae  mov     [rbp+37h+DestinationLuid.LowPart], 2
0x1800032b5  call    WsDeviceControlGetInfo
0x1800032ba  mov     edi, eax
0x1800032bc  test    eax, eax
0x1800032be  jnz     loc_180003754
0x1800032c4  mov     r8, [rsp+110h+hMem]
0x1800032c9  test    r8, r8
0x1800032cc  jz      loc_180003610
0x1800032d2  mov     rax, [rsi+8]
0x1800032d6  movzx   ecx, word ptr [rax+4]
0x1800032da  add     cx, cx
0x1800032dd  mov     [r8+2], cx
0x1800032e2  mov     [r8], cx
0x1800032e6  mov     rax, [rsi+8]
0x1800032ea  add     rax, 8
0x1800032ee  cmp     [rbp+37h+arg_30], 0FFFFFFFFh
0x1800032f2  mov     [r8+8], rax
0x1800032f6  jnz     short loc_180003344
0x1800032f8  mov     ecx, ebx
0x1800032fa  call    USE_FIXED_LENGTH
0x1800032ff  mov     r9d, eax
0x180003302  cmp     ebx, 2
0x180003305  jb      short loc_180003312
0x180003307  movzx   ecx, word ptr [r8+20h]
0x18000330c  add     ecx, 2
0x18000330f  add     r9d, ecx
0x180003312  movzx   eax, word ptr [r8]
0x180003316  mov     edx, [rsi+18h]
0x180003319  add     eax, 2
0x18000331c  add     edx, eax
0x18000331e  lea     edx, [r9+rdx*2]
0x180003322  mov     eax, edx
0x180003324  not     eax
0x180003326  cmp     r15d, eax
0x180003329  jnb     loc_180003610
0x18000332f  add     r15d, edx
0x180003332  cmp     ebx, 2
0x180003335  jnb     loc_180003732
0x18000333b  cmp     ebx, 5
0x18000333e  jnb     loc_18000374B
0x180003344  mov     rcx, r8; hMem
0x180003347  call    cs:__imp_LocalFree
0x18000334d  mov     rsi, [rsi]
0x180003350  inc     r12d
0x180003353  mov     rax, [rbp+37h+SourceLuid]
0x180003357  xor     edx, edx
0x180003359  jmp     loc_18000323B
0x18000335e  mov     ecx, [rbp+37h+arg_30]
0x180003361  mov     eax, 20h ; ' '
0x180003366  mov     [rbp+37h+var_80], rax
0x18000336a  mov     esi, 70h ; 'p'
0x18000336f  mov     [rsp+110h+var_C0], esi
0x180003373  mov     r8d, 28h ; '('
0x180003379  cmp     ecx, 0FFFFFFFFh
0x18000337c  jz      loc_18000376B
0x180003382  lea     eax, [rcx+2]
0x180003385  cmp     eax, ecx
0x180003387  jbe     loc_180003634
0x18000338d  lea     r15d, [rcx+1]
0x180003391  and     r15d, 0FFFFFFFEh
0x180003395  cmp     ebx, 5
0x180003398  jz      loc_1800036B5
0x18000339e  cmp     ebx, 4
0x1800033a1  jz      loc_1800037BC
0x1800033a7  cmp     ebx, 3
0x1800033aa  jz      loc_1800036AB
0x1800033b0  cmp     ebx, 2
0x1800033b3  jz      loc_1800037C6
0x1800033b9  cmp     ebx, 1
0x1800033bc  mov     eax, 10h
0x1800033c1  cmovz   eax, r8d
0x1800033c5  cmp     r15d, eax
0x1800033c8  jb      loc_1800037D0
0x1800033ce  mov     edx, r15d; uBytes
0x1800033d1  mov     ecx, 40h ; '@'; uFlags
0x1800033d6  mov     edi, r15d
0x1800033d9  call    cs:__imp_LocalAlloc
0x1800033df  mov     rsi, [rbp+37h+var_90]
0x1800033e3  mov     [rsi], rax
0x1800033e6  test    rax, rax
0x1800033e9  jz      loc_1800037F1
0x1800033ef  mov     r8d, edi; Size
0x1800033f2  xor     edx, edx; Val
0x1800033f4  mov     rcx, rax; void *
0x1800033f7  call    memset_0
0x1800033fc  mov     rax, [rsi]
0x1800033ff  cmp     ebx, 5
0x180003402  jz      loc_18000368E
0x180003408  cmp     ebx, 4
0x18000340b  jz      loc_1800037FB
0x180003411  cmp     ebx, 3
0x180003414  jz      loc_180003686
0x18000341a  cmp     ebx, 2
0x18000341d  jz      loc_180003808
0x180003423  mov     [rsp+110h+hMem], rax
0x180003428  lea     r12, [rax+rdi]
0x18000342c  mov     [rbp+37h+var_B0], r12
0x180003430  mov     r15, rax
0x180003433  cmp     ebx, 1
0x180003436  jz      loc_180003603
0x18000343c  mov     [rsp+110h+var_C0], 10h
0x180003444  test    ebx, ebx
0x180003446  jnz     loc_18000369E
0x18000344c  mov     [rbp+37h+var_80], 18h
0x180003454  mov     rcx, [rbp+37h+var_A0]
0x180003458  xor     r8d, r8d
0x18000345b  test    rcx, rcx
0x18000345e  jnz     loc_1800036BC
0x180003464  mov     esi, r8d
0x180003467  mov     [r13+0], r8d
0x18000346b  test    r14, r14
0x18000346e  jz      loc_180003584
0x180003474  cmp     esi, [r14+28h]
0x180003478  ja      loc_18000357C
0x18000347e  mov     rdx, [rbp+37h+SourceLuid]; SourceLuid
0x180003482  lea     rcx, [rbp+37h+DestinationLuid.HighPart]; DestinationLuid
0x180003486  mov     rdi, [r14+20h]
0x18000348a  xorps   xmm0, xmm0
0x18000348d  movdqu  xmmword ptr [rbp+37h+DestinationLuid.LowPart], xmm0
0x180003492  mov     [rbp+37h+var_88], r8
0x180003496  mov     [rbp+37h+var_58], r8
0x18000349a  mov     [rbp+37h+var_50], r8d
0x18000349e  mov     [rbp+37h+var_70], 1
0x1800034a5  mov     [rbp+37h+var_6C], 6
0x1800034ac  call    cs:__imp_RtlCopyLuid
0x1800034b2  xor     eax, eax
0x1800034b4  mov     [rbp+37h+DestinationLuid.LowPart], ebx
0x1800034b7  mov     [rbp+37h+var_58+4], rax
0x1800034bb  lea     r9, [rbp+37h+var_70]
0x1800034bf  mov     ecx, 470h
0x1800034c4  mov     eax, 228h
0x1800034c9  cmp     ebx, 1
0x1800034cc  mov     r8d, 1401A3h
0x1800034d2  mov     rdx, rdi
0x1800034d5  cmovnz  eax, ecx
0x1800034d8  xor     ecx, ecx
0x1800034da  mov     [rsp+110h+var_D8], eax
0x1800034de  lea     rax, [rbp+37h+var_88]
0x1800034e2  mov     dword ptr [rsp+110h+var_E0], 0FFFFFFFFh
0x1800034ea  mov     [rsp+110h+var_E8], rax
0x1800034ef  mov     dword ptr [rsp+110h+var_F0], 24h ; '$'
0x1800034f7  call    WsDeviceControlGetInfo
0x1800034fc  test    eax, eax
0x1800034fe  jnz     loc_18000363B
0x180003504  mov     rdi, [rbp+37h+var_88]
0x180003508  test    rdi, rdi
0x18000350b  jz      short loc_180003579
0x18000350d  mov     rax, [r14+8]
0x180003511  movzx   ecx, word ptr [rax+4]
0x180003515  add     cx, cx
0x180003518  mov     [rdi+2], cx
0x18000351c  mov     [rdi], cx
0x18000351f  mov     rax, [r14+8]
0x180003523  mov     ecx, [rsp+110h+var_C0]
0x180003527  add     rax, 8
0x18000352b  mov     [rdi+8], rax
0x18000352f  lea     rax, [r15+rcx]
0x180003533  cmp     rax, r12
0x180003536  jnb     loc_180003815
0x18000353c  mov     dword ptr [rsp+110h+var_E8], ecx
0x180003540  lea     rax, [rbp+37h+var_B0]
0x180003544  mov     ecx, ebx
0x180003546  mov     [rsp+110h+var_F0], rax
0x18000354b  lea     r9, [rsp+110h+hMem]
0x180003550  mov     r8, rdi
0x180003553  mov     rdx, r14
0x180003556  call    WsFillUseBuffer
0x18000355b  mov     rcx, rdi; hMem
0x18000355e  test    eax, eax
0x180003560  jz      loc_180003653
0x180003566  inc     dword ptr [r13+0]
0x18000356a  call    cs:__imp_LocalFree
0x180003570  mov     r15, [rsp+110h+hMem]
0x180003575  mov     r12, [rbp+37h+var_B0]
0x180003579  xor     r8d, r8d
0x18000357c  mov     r14, [r14]
0x18000357f  jmp     loc_18000346B
0x180003584  mov     esi, r8d
0x180003587  mov     r14d, [rbp+37h+arg_20]
0x18000358b  mov     edi, r8d
0x18000358e  mov     r15d, [rsp+110h+var_C0]
0x180003593  mov     r12, [rbp+37h+var_80]
0x180003597  cmp     edi, r14d
0x18000359a  jb      loc_180003828
0x1800035a0  mov     rcx, [rbp+37h+var_A0]
0x1800035a4  xor     r8d, r8d
0x1800035a7  test    rcx, rcx
0x1800035aa  jnz     loc_1800038A0
0x1800035b0  mov     rdx, [rbp+37h+var_98]
0x1800035b4  mov     ebx, r8d
0x1800035b7  mov     [rbp+37h+arg_20], r8d
0x1800035bb  mov     [rdx], r8d
0x1800035be  mov     ecx, [rbp+37h+arg_20]
0x1800035c1  add     ecx, [r13+0]
0x1800035c5  mov     [rdx], ecx
0x1800035c7  cmp     ebx, 0EAh
0x1800035cd  jz      short loc_180003617
0x1800035cf  cmp     dword ptr [r13+0], 0
0x1800035d4  jz      loc_1800038A8
0x1800035da  mov     eax, ebx
0x1800035dc  mov     rdi, [rsp+110h+var_38]
0x1800035e4  mov     rcx, [rbp+37h+var_48]
0x1800035e8  xor     rcx, rsp; StackCookie
0x1800035eb  call    __security_check_cookie
0x1800035f0  add     rsp, 0E0h
0x1800035f7  pop     r15
0x1800035f9  pop     r14
0x1800035fb  pop     r13
0x1800035fd  pop     r12
0x1800035ff  pop     rsi
0x180003600  pop     rbx
0x180003601  pop     rbp
0x180003602  retn
0x180003603  mov     [rsp+110h+var_C0], 28h ; '('
0x18000360b  jmp     loc_180003454
0x180003610  mov     eax, 85Ch
0x180003615  jmp     short loc_1800035DC
0x180003617  cmp     [rbp+37h+arg_30], 0FFFFFFFFh
0x18000361b  jnz     short loc_1800035CF
0x18000361d  mov     rdi, [rbp+37h+var_90]
0x180003621  mov     rcx, [rdi]; hMem
0x180003624  call    cs:__imp_LocalFree
0x18000362a  mov     ebx, 8
0x18000362f  jmp     loc_1800038B5
0x180003634  mov     eax, 216h
0x180003639  jmp     short loc_1800035DC
0x18000363b  mov     rcx, [rbp+37h+var_88]; hMem
0x18000363f  test    rcx, rcx
0x180003642  jz      loc_180003579
0x180003648  call    cs:__imp_LocalFree
0x18000364e  jmp     loc_180003579
0x180003653  mov     ebx, 0EAh
0x180003658  call    cs:__imp_LocalFree
0x18000365e  mov     rdx, [rbp+37h+var_A0]
0x180003662  test    rdx, rdx
0x180003665  jnz     loc_18000381D
0x18000366b  mov     eax, [rbp+37h+arg_20]
0x18000366e  mov     rdx, [rbp+37h+var_98]
0x180003672  inc     eax
0x180003674  mov     [rdx], eax
0x180003676  mov     r14, [r14]
0x180003679  test    r14, r14
0x18000367c  jnz     short loc_180003672
0x18000367e  mov     [rbp+37h+arg_20], eax
0x180003681  jmp     loc_1800035BE
0x180003686  mov     [rsp+110h+var_C0], 40h ; '@'
0x18000368e  lea     r12, [rax+rdi]
  ... truncated ...
```
