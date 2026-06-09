# WsEnumUseInfo

- ea: `0x1800033c0`
- end: `0x180003aec`
- name: `WsEnumUseInfo`
- size: `1836`
- prototype: `__int64 __usercall@<rax>(PLUID SourceLuid@<rcx>, int, __int64, int, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003b00`

## callees

- `0x1800025f0`
- `0x1800033c0`
- `0x180005504`
- `0x1800057e0`
- `0x180005840`
- `0x18000b470`
- `0x18001fbd0`
- `0x1800204f6`

## import_xrefs

- `ntdll!RtlCopyLuid` at `0x180003461`
- `ntdll!RtlCopyLuid` at `0x1800036ae`
- `ntdll!RtlCopyLuid` at `0x180003461`
- `ntdll!RtlCopyLuid` at `0x1800036ae`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800035d5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800035d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000353d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003772`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003833`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000385d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003873`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000397f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003ad6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000353d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003772`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003833`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000385d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003873`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000397f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003ad6`

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
0x1800033c0  push    rbp
0x1800033c2  push    rbx
0x1800033c3  push    rsi
0x1800033c4  push    r12
0x1800033c6  push    r13
0x1800033c8  push    r14
0x1800033ca  push    r15
0x1800033cc  lea     rbp, [rsp-7]
0x1800033d1  sub     rsp, 0E0h
0x1800033d8  mov     rax, cs:__security_cookie
0x1800033df  xor     rax, rsp
0x1800033e2  mov     [rbp+37h+var_48], rax
0x1800033e6  mov     r13, [rbp+37h+arg_38]
0x1800033ea  mov     ebx, edx
0x1800033ec  mov     rdx, [rbp+37h+arg_48]
0x1800033f3  mov     r14, r8
0x1800033f6  mov     r8, [rbp+37h+arg_40]
0x1800033fd  mov     rax, rcx
0x180003400  mov     [rbp+37h+var_A0], rdx
0x180003404  mov     rsi, r14
0x180003407  xor     edx, edx
0x180003409  mov     [rbp+37h+var_A8], r9
0x18000340d  mov     r9, [rbp+37h+arg_28]
0x180003411  mov     r15d, edx
0x180003414  mov     r12d, edx
0x180003417  mov     [rbp+37h+SourceLuid], rcx
0x18000341b  mov     [rbp+37h+var_90], r9
0x18000341f  mov     [rbp+37h+var_98], r8
0x180003423  mov     [rsp+110h+var_38], rdi
0x18000342b  test    rsi, rsi
0x18000342e  jz      loc_18000355A
0x180003434  mov     rdi, [rsi+20h]
0x180003438  lea     rcx, [rbp+37h+DestinationLuid.HighPart]; DestinationLuid
0x18000343c  mov     [rsp+110h+hMem], rdx
0x180003441  xorps   xmm0, xmm0
0x180003444  mov     [rbp+37h+var_58], rdx
0x180003448  mov     [rbp+37h+var_50], edx
0x18000344b  mov     rdx, rax; SourceLuid
0x18000344e  movdqu  xmmword ptr [rbp-31h], xmm0
0x180003453  mov     [rbp+37h+var_70], 1
0x18000345a  mov     [rbp+37h+var_6C], 6
0x180003461  call    cs:__imp_RtlCopyLuid
0x180003468  nop     dword ptr [rax+rax+00h]
0x18000346d  xor     eax, eax
0x18000346f  mov     [rsp+110h+var_D8], 470h
0x180003477  mov     [rbp+37h+var_58+4], rax
0x18000347b  lea     r9, [rbp+37h+var_70]
0x18000347f  lea     rax, [rsp+110h+hMem]
0x180003484  mov     dword ptr [rsp+110h+var_E0], 0FFFFFFFFh
0x18000348c  mov     [rsp+110h+var_E8], rax
0x180003491  mov     r8d, 1401A3h
0x180003497  mov     rdx, rdi
0x18000349a  mov     dword ptr [rsp+110h+var_F0], 24h ; '$'
0x1800034a2  xor     ecx, ecx
0x1800034a4  mov     [rbp+37h+DestinationLuid.LowPart], 2
0x1800034ab  call    WsDeviceControlGetInfo
0x1800034b0  mov     edi, eax
0x1800034b2  test    eax, eax
0x1800034b4  jnz     loc_180003975
0x1800034ba  mov     r8, [rsp+110h+hMem]
0x1800034bf  test    r8, r8
0x1800034c2  jz      loc_18000381F
0x1800034c8  mov     rax, [rsi+8]
0x1800034cc  movzx   ecx, word ptr [rax+4]
0x1800034d0  add     cx, cx
0x1800034d3  mov     [r8+2], cx
0x1800034d8  mov     [r8], cx
0x1800034dc  mov     rax, [rsi+8]
0x1800034e0  add     rax, 8
0x1800034e4  cmp     [rbp+37h+arg_30], 0FFFFFFFFh
0x1800034e8  mov     [r8+8], rax
0x1800034ec  jnz     short loc_18000353A
0x1800034ee  mov     ecx, ebx
0x1800034f0  call    USE_FIXED_LENGTH
0x1800034f5  mov     r9d, eax
0x1800034f8  cmp     ebx, 2
0x1800034fb  jb      short loc_180003508
0x1800034fd  movzx   ecx, word ptr [r8+20h]
0x180003502  add     ecx, 2
0x180003505  add     r9d, ecx
0x180003508  movzx   eax, word ptr [r8]
0x18000350c  mov     edx, [rsi+18h]
0x18000350f  add     eax, 2
0x180003512  add     edx, eax
0x180003514  lea     edx, [r9+rdx*2]
0x180003518  mov     eax, edx
0x18000351a  not     eax
0x18000351c  cmp     r15d, eax
0x18000351f  jnb     loc_18000381F
0x180003525  add     r15d, edx
0x180003528  cmp     ebx, 2
0x18000352b  jnb     loc_180003953
0x180003531  cmp     ebx, 5
0x180003534  jnb     loc_18000396C
0x18000353a  mov     rcx, r8; hMem
0x18000353d  call    cs:__imp_LocalFree
0x180003544  nop     dword ptr [rax+rax+00h]
0x180003549  mov     rsi, [rsi]
0x18000354c  inc     r12d
0x18000354f  mov     rax, [rbp+37h+SourceLuid]
0x180003553  xor     edx, edx
0x180003555  jmp     loc_18000342B
0x18000355a  mov     ecx, [rbp+37h+arg_30]
0x18000355d  mov     eax, 20h ; ' '
0x180003562  mov     [rbp+37h+var_80], rax
0x180003566  mov     esi, 70h ; 'p'
0x18000356b  mov     [rsp+110h+var_C0], esi
0x18000356f  mov     r8d, 28h ; '('
0x180003575  cmp     ecx, 0FFFFFFFFh
0x180003578  jz      loc_180003992
0x18000357e  lea     eax, [rcx+2]
0x180003581  cmp     eax, ecx
0x180003583  jbe     loc_180003849
0x180003589  lea     r15d, [rcx+1]
0x18000358d  and     r15d, 0FFFFFFFEh
0x180003591  cmp     ebx, 5
0x180003594  jz      loc_1800038D6
0x18000359a  cmp     ebx, 4
0x18000359d  jz      loc_1800039E3
0x1800035a3  cmp     ebx, 3
0x1800035a6  jz      loc_1800038CC
0x1800035ac  cmp     ebx, 2
0x1800035af  jz      loc_1800039ED
0x1800035b5  cmp     ebx, 1
0x1800035b8  mov     eax, 10h
0x1800035bd  cmovz   eax, r8d
0x1800035c1  cmp     r15d, eax
0x1800035c4  jb      loc_1800039F7
0x1800035ca  mov     edx, r15d; uBytes
0x1800035cd  mov     ecx, 40h ; '@'; uFlags
0x1800035d2  mov     edi, r15d
0x1800035d5  call    cs:__imp_LocalAlloc
0x1800035dc  nop     dword ptr [rax+rax+00h]
0x1800035e1  mov     rsi, [rbp+37h+var_90]
0x1800035e5  mov     [rsi], rax
0x1800035e8  test    rax, rax
0x1800035eb  jz      loc_180003A18
0x1800035f1  mov     r8d, edi; Size
0x1800035f4  xor     edx, edx; Val
0x1800035f6  mov     rcx, rax; void *
0x1800035f9  call    memset_0
0x1800035fe  mov     rax, [rsi]
0x180003601  cmp     ebx, 5
0x180003604  jz      loc_1800038AF
0x18000360a  cmp     ebx, 4
0x18000360d  jz      loc_180003A22
0x180003613  cmp     ebx, 3
0x180003616  jz      loc_1800038A7
0x18000361c  cmp     ebx, 2
0x18000361f  jz      loc_180003A2F
0x180003625  mov     [rsp+110h+hMem], rax
0x18000362a  lea     r12, [rax+rdi]
0x18000362e  mov     [rbp+37h+var_B0], r12
0x180003632  mov     r15, rax
0x180003635  cmp     ebx, 1
0x180003638  jz      loc_180003812
0x18000363e  mov     [rsp+110h+var_C0], 10h
0x180003646  test    ebx, ebx
0x180003648  jnz     loc_1800038BF
0x18000364e  mov     [rbp+37h+var_80], 18h
0x180003656  mov     rcx, [rbp+37h+var_A0]
0x18000365a  xor     r8d, r8d
0x18000365d  test    rcx, rcx
0x180003660  jnz     loc_1800038DD
0x180003666  mov     esi, r8d
0x180003669  mov     [r13+0], r8d
0x18000366d  test    r14, r14
0x180003670  jz      loc_180003792
0x180003676  cmp     esi, [r14+28h]
0x18000367a  ja      loc_18000378A
0x180003680  mov     rdx, [rbp+37h+SourceLuid]; SourceLuid
0x180003684  lea     rcx, [rbp+37h+DestinationLuid.HighPart]; DestinationLuid
0x180003688  mov     rdi, [r14+20h]
0x18000368c  xorps   xmm0, xmm0
0x18000368f  movdqu  xmmword ptr [rbp+37h+DestinationLuid.LowPart], xmm0
0x180003694  mov     [rbp+37h+var_88], r8
0x180003698  mov     [rbp+37h+var_58], r8
0x18000369c  mov     [rbp+37h+var_50], r8d
0x1800036a0  mov     [rbp+37h+var_70], 1
0x1800036a7  mov     [rbp+37h+var_6C], 6
0x1800036ae  call    cs:__imp_RtlCopyLuid
0x1800036b5  nop     dword ptr [rax+rax+00h]
0x1800036ba  xor     eax, eax
0x1800036bc  mov     [rbp+37h+DestinationLuid.LowPart], ebx
0x1800036bf  mov     [rbp+37h+var_58+4], rax
0x1800036c3  lea     r9, [rbp+37h+var_70]
0x1800036c7  mov     ecx, 470h
0x1800036cc  mov     eax, 228h
0x1800036d1  cmp     ebx, 1
0x1800036d4  mov     r8d, 1401A3h
0x1800036da  mov     rdx, rdi
0x1800036dd  cmovnz  eax, ecx
0x1800036e0  xor     ecx, ecx
0x1800036e2  mov     [rsp+110h+var_D8], eax
0x1800036e6  lea     rax, [rbp+37h+var_88]
0x1800036ea  mov     dword ptr [rsp+110h+var_E0], 0FFFFFFFFh
0x1800036f2  mov     [rsp+110h+var_E8], rax
0x1800036f7  mov     dword ptr [rsp+110h+var_F0], 24h ; '$'
0x1800036ff  call    WsDeviceControlGetInfo
0x180003704  test    eax, eax
0x180003706  jnz     loc_180003850
0x18000370c  mov     rdi, [rbp+37h+var_88]
0x180003710  test    rdi, rdi
0x180003713  jz      short loc_180003787
0x180003715  mov     rax, [r14+8]
0x180003719  movzx   ecx, word ptr [rax+4]
0x18000371d  add     cx, cx
0x180003720  mov     [rdi+2], cx
0x180003724  mov     [rdi], cx
0x180003727  mov     rax, [r14+8]
0x18000372b  mov     ecx, [rsp+110h+var_C0]
0x18000372f  add     rax, 8
0x180003733  mov     [rdi+8], rax
0x180003737  lea     rax, [r15+rcx]
0x18000373b  cmp     rax, r12
0x18000373e  jnb     loc_180003A3C
0x180003744  mov     dword ptr [rsp+110h+var_E8], ecx
0x180003748  lea     rax, [rbp+37h+var_B0]
0x18000374c  mov     ecx, ebx
0x18000374e  mov     [rsp+110h+var_F0], rax
0x180003753  lea     r9, [rsp+110h+hMem]
0x180003758  mov     r8, rdi
0x18000375b  mov     rdx, r14
0x18000375e  call    WsFillUseBuffer
0x180003763  mov     rcx, rdi; hMem
0x180003766  test    eax, eax
0x180003768  jz      loc_18000386E
0x18000376e  inc     dword ptr [r13+0]
0x180003772  call    cs:__imp_LocalFree
0x180003779  nop     dword ptr [rax+rax+00h]
0x18000377e  mov     r15, [rsp+110h+hMem]
0x180003783  mov     r12, [rbp+37h+var_B0]
0x180003787  xor     r8d, r8d
0x18000378a  mov     r14, [r14]
0x18000378d  jmp     loc_18000366D
0x180003792  mov     esi, r8d
0x180003795  mov     r14d, [rbp+37h+arg_20]
0x180003799  mov     edi, r8d
0x18000379c  mov     r15d, [rsp+110h+var_C0]
0x1800037a1  mov     r12, [rbp+37h+var_80]
0x1800037a5  cmp     edi, r14d
0x1800037a8  jb      loc_180003A4F
0x1800037ae  mov     rcx, [rbp+37h+var_A0]
0x1800037b2  xor     r8d, r8d
0x1800037b5  test    rcx, rcx
0x1800037b8  jnz     loc_180003AC7
0x1800037be  mov     rdx, [rbp+37h+var_98]
0x1800037c2  mov     ebx, r8d
0x1800037c5  mov     [rbp+37h+arg_20], r8d
0x1800037c9  mov     [rdx], r8d
0x1800037cc  mov     ecx, [rbp+37h+arg_20]
0x1800037cf  add     ecx, [r13+0]
0x1800037d3  mov     [rdx], ecx
0x1800037d5  cmp     ebx, 0EAh
0x1800037db  jz      short loc_180003826
0x1800037dd  cmp     dword ptr [r13+0], 0
0x1800037e2  jz      loc_180003ACF
0x1800037e8  mov     eax, ebx
0x1800037ea  mov     rdi, [rsp+110h+var_38]
0x1800037f2  mov     rcx, [rbp+37h+var_48]
0x1800037f6  xor     rcx, rsp; StackCookie
0x1800037f9  call    __security_check_cookie
0x1800037fe  add     rsp, 0E0h
0x180003805  pop     r15
0x180003807  pop     r14
0x180003809  pop     r13
0x18000380b  pop     r12
0x18000380d  pop     rsi
0x18000380e  pop     rbx
0x18000380f  pop     rbp
0x180003810  retn
0x180003812  mov     [rsp+110h+var_C0], 28h ; '('
0x18000381a  jmp     loc_180003656
0x18000381f  mov     eax, 85Ch
0x180003824  jmp     short loc_1800037EA
0x180003826  cmp     [rbp+37h+arg_30], 0FFFFFFFFh
0x18000382a  jnz     short loc_1800037DD
0x18000382c  mov     rdi, [rbp+37h+var_90]
0x180003830  mov     rcx, [rdi]; hMem
0x180003833  call    cs:__imp_LocalFree
0x18000383a  nop     dword ptr [rax+rax+00h]
0x18000383f  mov     ebx, 8
0x180003844  jmp     loc_180003AE2
0x180003849  mov     eax, 216h
0x18000384e  jmp     short loc_1800037EA
0x180003850  mov     rcx, [rbp+37h+var_88]; hMem
0x180003854  test    rcx, rcx
0x180003857  jz      loc_180003787
0x18000385d  call    cs:__imp_LocalFree
0x180003864  nop     dword ptr [rax+rax+00h]
0x180003869  jmp     loc_180003787
0x18000386e  mov     ebx, 0EAh
0x180003873  call    cs:__imp_LocalFree
0x18000387a  nop     dword ptr [rax+rax+00h]
0x18000387f  mov     rdx, [rbp+37h+var_A0]
0x180003883  test    rdx, rdx
0x180003886  jnz     loc_180003A44
0x18000388c  mov     eax, [rbp+37h+arg_20]
0x18000388f  mov     rdx, [rbp+37h+var_98]
0x180003893  inc     eax
  ... truncated ...
```
