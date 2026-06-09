# CwchCallFormatMessage(ulong,void *,CErrorEventId const *,short,wchar_t *,int,wchar_t *,int,CFormattedParams *,EFormatMethod)

- ea: `0x100416000`
- end: `0x100416693`
- name: `?CwchCallFormatMessage@@YAHKPEAXPEBVCErrorEventId@@FPEA_WH2HPEAVCFormattedParams@@W4EFormatMethod@@@Z`
- size: `1683`
- prototype: `int __high(unsigned int, void *, const struct CErrorEventId *, __int16, wchar_t *, int, wchar_t *, int, struct CFormattedParams *, enum EFormatMethod)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x100417840`
- `0x100417db0`
- `0x1004183a0`

## callees

- `0x100416000`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x100416141`
- `KERNEL32!FormatMessageW` at `0x100416141`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x100416039`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x100416050`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x100416039`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x100416050`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10041632b`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10041632b`
- `sqldk!??_V@YAXPEAX@Z` at `0x100416110`
- `sqldk!??_V@YAXPEAX@Z` at `0x100416614`
- `sqldk!??_V@YAXPEAX@Z` at `0x100416110`
- `sqldk!??_V@YAXPEAX@Z` at `0x100416614`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1004160fc`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1004160fc`
- `sqldk!SystemThread_TlsIndex` at `0x1004160a8`
- `sqldk!SystemThread_TlsOffset` at `0x1004160b1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004160cc`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004160cc`
- `api-ms-win-crt-string-l1-1-0!_iswdigit_l` at `0x100416338`
- `api-ms-win-crt-string-l1-1-0!_iswdigit_l` at `0x100416338`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CwchCallFormatMessage(
        __int16 a1,
        WCHAR *a2,
        DWORD *a3,
        __int16 a4,
        _WORD *a5,
        int a6,
        _WORD *a7,
        int a8,
        __int64 a9,
        int a10)
{
  int v13; // ebx
  struct IErrorReportingManager *ErrorReportingManager; // rax
  struct IErrorReportingManager *v15; // rax
  __int64 v16; // r15
  __int64 v17; // r12
  __int64 v18; // rdi
  __int64 v19; // rdx
  WCHAR *lpBuffer; // rdi
  signed int v21; // eax
  __int64 v22; // rcx
  WCHAR *v23; // rdx
  int v24; // edi
  BOOL v25; // edx
  int v26; // r14d
  _WORD *v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // r8
  signed __int64 v30; // r9
  __int16 v31; // ax
  _WORD *v32; // rax
  int v33; // r8d
  WCHAR v34; // cx
  __int64 v35; // rbp
  _WORD *v36; // r11
  int v37; // r10d
  __int64 v38; // rdx
  int v39; // eax
  int v40; // r13d
  int v41; // r9d
  BOOL v42; // r14d
  __int64 v43; // r15
  __crt_locale_pointers *DefaultLocale; // rax
  int v45; // r8d
  int v46; // ecx
  int v47; // edi
  __int64 i; // rax
  __int64 v49; // rax
  _WORD *v50; // r11
  __int64 v51; // rcx
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 v54; // rcx
  __int64 v55; // rax
  _WORD *v56; // r10
  __int16 v57; // dx
  int v58; // ecx
  _WORD *v59; // rdx
  int v61; // [rsp+40h] [rbp-68h]
  int v62; // [rsp+44h] [rbp-64h]
  int v63; // [rsp+48h] [rbp-60h]
  int v64; // [rsp+4Ch] [rbp-5Ch]
  int v65; // [rsp+50h] [rbp-58h]
  WCHAR *v66; // [rsp+58h] [rbp-50h]
  int v67; // [rsp+B0h] [rbp+8h]
  __int16 v68; // [rsp+C8h] [rbp+20h] BYREF

  v68 = a4;
  v66 = 0;
  v13 = 0;
  if ( (a1 & 0x800) != 0 )
  {
    ErrorReportingManager = GetErrorReportingManager();
    if ( !(*(unsigned __int8 (__fastcall **)(struct IErrorReportingManager *))(*(_QWORD *)ErrorReportingManager + 72LL))(ErrorReportingManager) )
      goto LABEL_101;
    v15 = GetErrorReportingManager();
    a2 = (WCHAR *)(*(__int64 (__fastcall **)(struct IErrorReportingManager *, __int16 *))(*(_QWORD *)v15 + 64LL))(
                    v15,
                    &v68);
  }
  v16 = 1;
  if ( (a1 & 0x400) != 0 )
  {
    if ( a2 )
    {
      v17 = -1;
      do
        ++v17;
      while ( a2[v17] );
    }
    else
    {
      LODWORD(v17) = 0;
    }
    goto LABEL_21;
  }
  v18 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v19 = *(_QWORD *)(v18 + 256);
  if ( !v19 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v19 = *(_QWORD *)(v18 + 256);
  }
  lpBuffer = (WCHAR *)operator new[](
                        0x1000u,
                        *(struct IMemObj **)(v19 + 1000),
                        1,
                        "Sql\\Ntdbms\\msql\\utils\\errorreportutils.cpp",
                        445,
                        6u);
  if ( !lpBuffer )
  {
    v66 = 0;
    goto LABEL_101;
  }
  operator delete[](0);
  v66 = lpBuffer;
  v21 = FormatMessageW(0xA00u, a2, *a3, v68, lpBuffer, 0x800u, 0);
  LODWORD(v17) = v21;
  v65 = v21;
  if ( !v21 )
  {
LABEL_101:
    v13 = 0;
    goto LABEL_102;
  }
  v22 = v21;
  a2 = lpBuffer;
  if ( v21 <= 0 )
    goto LABEL_22;
  v23 = &lpBuffer[v21 - 1];
  do
  {
    if ( *v23 != 10 )
      break;
    LODWORD(v17) = v17 - 1;
    --v22;
    --v23;
    if ( v22 <= 0 )
      break;
    if ( *v23 == 13 )
    {
      LODWORD(v17) = v17 - 1;
      --v22;
      --v23;
    }
  }
  while ( v22 > 0 );
LABEL_21:
  v65 = v17;
LABEL_22:
  v24 = 0;
  v25 = 0;
  v67 = 0;
  v26 = 0;
  v27 = a7;
  if ( a7 )
  {
    v28 = a8;
    if ( (unsigned __int64)(a8 - 1LL) > 0x7FFFFFFE )
    {
      if ( a8 )
        *a7 = 0;
    }
    else
    {
      v29 = 2147483646LL - a8;
      v30 = (char *)a2 - (char *)a7;
      do
      {
        if ( !(v29 + v28) )
          break;
        v31 = *(_WORD *)((char *)v27 + v30);
        if ( !v31 )
          break;
        *v27++ = v31;
        --v28;
      }
      while ( v28 );
      v32 = v27 - 1;
      if ( v28 )
        v32 = v27;
      *v32 = 0;
    }
    v25 = 0;
  }
  v33 = a6 - 1;
  v61 = a6 - 1;
  if ( a6 - 1 <= 0 )
    goto LABEL_93;
  while ( v24 < (int)v17 )
  {
    if ( v26 )
      goto LABEL_91;
    if ( v25 )
      goto LABEL_95;
    v34 = a2[v24++];
    if ( v34 != 37 )
    {
      a5[v13] = v34;
LABEL_87:
      ++v13;
LABEL_88:
      v25 = v67;
      goto LABEL_89;
    }
    v35 = v24;
    switch ( a2[v24] )
    {
      case ' ':
      case '!':
      case '%':
      case '.':
        a5[v13++] = a2[v24];
        goto LABEL_41;
      case '0':
LABEL_41:
        ++v24;
        goto LABEL_88;
      case 'n':
        v36 = a5;
        a5[v13++] = 13;
        if ( v13 < v33 )
        {
          v36[v13] = 10;
          goto LABEL_87;
        }
        v25 = 1;
        v67 = 1;
        goto LABEL_89;
      default:
        v37 = v24;
        v63 = v24;
        v38 = a9;
        v39 = *(_DWORD *)(a9 + 4208);
        v64 = v39;
        v40 = 0;
        v41 = 0;
        v62 = 0;
        v42 = 0;
        v43 = (int)v17;
        if ( v24 >= (__int64)(int)v17 )
          goto LABEL_53;
        _mm_lfence();
        break;
    }
    while ( !v42 )
    {
      DefaultLocale = GetDefaultLocale();
      if ( !_iswdigit_l(a2[v35], DefaultLocale) )
      {
        v41 = v62;
        break;
      }
      v41 = 1;
      v62 = 1;
      v45 = a2[v35];
      v42 = v40 > (-2147483601 - v45) / 10;
      ++v24;
      ++v35;
      v40 = v45 + 2 * (5 * v40 - 24);
      if ( v35 >= (int)v17 )
        break;
    }
    LODWORD(v17) = v65;
    v37 = v63;
    v39 = v64;
    v33 = v61;
    v38 = a9;
LABEL_53:
    v46 = -1;
    if ( v41 )
      v46 = v40;
    if ( v42 || v39 != -1 && v46 > v39 || v46 <= 0 )
      goto LABEL_85;
    if ( a2[v24] == 33 )
    {
      v47 = v24 + 1;
      for ( i = v47; i < v43; ++i )
      {
        if ( a2[i] == 33 )
          break;
        ++v47;
      }
      v49 = v47;
      v24 = v47 + 1;
      if ( a2[v49] != 33 )
      {
LABEL_85:
        v16 = 1;
        v26 = 1;
        goto LABEL_88;
      }
    }
    v26 = 0;
    if ( a10 || v68 == 1033 )
    {
      if ( *(_DWORD *)(v38 + 4208) )
        v53 = *(_QWORD *)(v38 + 8LL * v46 + 4208);
      else
        v53 = 0;
      v54 = 0;
      v55 = v13;
      if ( v13 < (__int64)v61 )
      {
        v56 = a5;
        do
        {
          v57 = *(_WORD *)(v53 + 2 * v54);
          if ( !v57 )
            break;
          v56[v55] = v57;
          ++v13;
          ++v55;
          ++v54;
        }
        while ( v55 < v61 );
      }
      v25 = *(_WORD *)(v53 + 2 * v54) != 0;
      v16 = 1;
    }
    else
    {
      v50 = a5;
      if ( v13 < v33 )
        a5[v13++] = 37;
      v51 = v13;
      if ( v13 < (__int64)v33 )
      {
        v52 = v37;
        do
        {
          if ( v52 >= v24 )
            break;
          v50[v51] = a2[v52];
          ++v13;
          ++v51;
          ++v37;
          ++v52;
        }
        while ( v51 < v33 );
      }
      if ( v37 == v24 && v13 < v61 )
      {
        v50[v13] = 33;
        v16 = 1;
        v33 = v61;
        goto LABEL_87;
      }
      v16 = 1;
      v25 = 1;
    }
    v67 = v25;
    v33 = v61;
LABEL_89:
    if ( v13 >= v33 )
      break;
  }
  if ( v26 )
  {
LABEL_91:
    v13 = 0;
    *a5 = 0;
    goto LABEL_102;
  }
  if ( v25 )
  {
LABEL_95:
    if ( v13 > 0 )
    {
      v58 = v13 - 1;
      v59 = &a5[v13 - 1];
      do
      {
        if ( v16 > 3 )
          break;
        *v59 = 46;
        ++v16;
        --v59;
        --v58;
      }
      while ( v58 >= 0 );
    }
  }
  else
  {
LABEL_93:
    if ( *(_DWORD *)(a9 + 4616) || v24 < (int)v17 )
      goto LABEL_95;
  }
  a5[v13] = 0;
LABEL_102:
  operator delete[](v66);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x100416000  mov     rax, rsp
0x100416003  mov     [rax+20h], r9w
0x100416008  push    rbp
0x100416009  push    rsi
0x10041600a  push    rdi
0x10041600b  push    r12
0x10041600d  push    r13
0x10041600f  push    r14
0x100416011  push    r15
0x100416013  sub     rsp, 70h
0x100416017  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x10041601f  mov     [rax+10h], rbx
0x100416023  mov     r14, r8
0x100416026  mov     rsi, rdx
0x100416029  mov     edi, ecx
0x10041602b  xor     ebp, ebp
0x10041602d  mov     [rax-50h], rbp
0x100416031  mov     ebx, ebp
0x100416033  bt      ecx, 0Bh
0x100416037  jnb     short loc_10041606B
0x100416039  call    cs:__imp_?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ; GetErrorReportingManager(void)
0x10041603f  mov     rdx, [rax]
0x100416042  mov     rcx, rax
0x100416045  call    qword ptr [rdx+48h]
0x100416048  test    al, al
0x10041604a  jz      loc_10041660D
0x100416050  call    cs:__imp_?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ; GetErrorReportingManager(void)
0x100416056  mov     r8, [rax]
0x100416059  lea     rdx, [rsp+0A8h+arg_18]
0x100416061  mov     rcx, rax
0x100416064  call    qword ptr [r8+40h]
0x100416068  mov     rsi, rax
0x10041606b  mov     r13d, 0Dh
0x100416071  lea     r15d, [r13-0Ch]
0x100416075  bt      edi, 0Ah
0x100416079  jnb     short loc_10041609F
0x10041607b  test    rsi, rsi
0x10041607e  jnz     short loc_100416088
0x100416080  mov     r12d, ebp
0x100416083  jmp     loc_100416199
0x100416088  mov     r12, 0FFFFFFFFFFFFFFFFh
0x10041608f  nop
0x100416090  inc     r12
0x100416093  cmp     [rsi+r12*2], bx
0x100416098  jnz     short loc_100416090
0x10041609a  jmp     loc_100416199
0x10041609f  mov     rdx, gs:58h
0x1004160a8  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004160af  mov     ecx, [rax]
0x1004160b1  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004160b8  mov     edi, [rax]
0x1004160ba  add     rdi, [rdx+rcx*8]
0x1004160be  mov     rdx, [rdi+100h]
0x1004160c5  test    rdx, rdx
0x1004160c8  jnz     short loc_1004160D9
0x1004160ca  xor     ecx, ecx
0x1004160cc  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004160d2  mov     rdx, [rdi+100h]
0x1004160d9  mov     byte ptr [rsp+0A8h+nSize], 6
0x1004160de  mov     dword ptr [rsp+0A8h+lpBuffer], 1BDh
0x1004160e6  lea     r9, aSqlNtdbmsMsqlU; "Sql\\Ntdbms\\msql\\utils\\errorreportut"...
0x1004160ed  mov     r8d, r15d
0x1004160f0  mov     rdx, [rdx+3E8h]
0x1004160f7  mov     ecx, 1000h
0x1004160fc  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100416102  mov     rdi, rax
0x100416105  test    rax, rax
0x100416108  jz      loc_100416608
0x10041610e  xor     ecx, ecx
0x100416110  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100416116  mov     [rsp+0A8h+var_50], rdi
0x10041611b  movsx   r9d, [rsp+0A8h+arg_18]; dwLanguageId
0x100416124  mov     [rsp+0A8h+Arguments], rbp; Arguments
0x100416129  mov     [rsp+0A8h+nSize], 800h; nSize
0x100416131  mov     [rsp+0A8h+lpBuffer], rdi; lpBuffer
0x100416136  mov     r8d, [r14]; dwMessageId
0x100416139  mov     rdx, rsi; lpSource
0x10041613c  mov     ecx, 0A00h; dwFlags
0x100416141  call    cs:__imp_FormatMessageW
0x100416147  movsxd  r12, eax
0x10041614a  mov     [rsp+0A8h+var_58], r12
0x10041614f  test    eax, eax
0x100416151  jz      loc_10041660D
0x100416157  mov     rcx, r12
0x10041615a  mov     rsi, rdi
0x10041615d  jle     short loc_10041619E
0x10041615f  lea     rdx, [r12-1]
0x100416164  lea     rdx, [rdi+rdx*2]
0x100416168  mov     eax, 0Ah
0x10041616d  nop     dword ptr [rax]
0x100416170  cmp     ax, [rdx]
0x100416173  jnz     short loc_100416199
0x100416175  dec     r12d
0x100416178  dec     rcx
0x10041617b  sub     rdx, 2
0x10041617f  test    rcx, rcx
0x100416182  jle     short loc_100416199
0x100416184  cmp     r13w, [rdx]
0x100416188  jnz     short loc_100416194
0x10041618a  dec     r12d
0x10041618d  dec     rcx
0x100416190  sub     rdx, 2
0x100416194  test    rcx, rcx
0x100416197  jg      short loc_100416170
0x100416199  mov     [rsp+0A8h+var_58], r12
0x10041619e  xor     r11d, r11d
0x1004161a1  mov     edi, r11d
0x1004161a4  mov     edx, r11d
0x1004161a7  mov     [rsp+0A8h+arg_0], edx
0x1004161ae  mov     r14d, r11d
0x1004161b1  mov     rcx, [rsp+0A8h+arg_30]
0x1004161b9  test    rcx, rcx
0x1004161bc  jz      short loc_100416220
0x1004161be  movsxd  rdx, [rsp+0A8h+arg_38]
0x1004161c6  lea     rax, [rdx-1]
0x1004161ca  mov     r8d, 7FFFFFFEh
0x1004161d0  cmp     rax, r8
0x1004161d3  ja      short loc_100416210
0x1004161d5  sub     r8, rdx
0x1004161d8  mov     r9, rsi
0x1004161db  sub     r9, rcx
0x1004161de  xchg    ax, ax
0x1004161e0  lea     rax, [r8+rdx]
0x1004161e4  test    rax, rax
0x1004161e7  jz      short loc_1004161FF
0x1004161e9  movzx   eax, word ptr [r9+rcx]
0x1004161ee  test    ax, ax
0x1004161f1  jz      short loc_1004161FF
0x1004161f3  mov     [rcx], ax
0x1004161f6  add     rcx, 2
0x1004161fa  sub     rdx, r15
0x1004161fd  jnz     short loc_1004161E0
0x1004161ff  lea     rax, [rcx-2]
0x100416203  test    rdx, rdx
0x100416206  cmovnz  rax, rcx
0x10041620a  mov     [rax], r11w
0x10041620e  jmp     short loc_100416219
0x100416210  test    rdx, rdx
0x100416213  jz      short loc_100416219
0x100416215  mov     [rcx], r11w
0x100416219  mov     edx, [rsp+0A8h+arg_0]
0x100416220  mov     r8d, [rsp+0A8h+arg_28]
0x100416228  dec     r8d
0x10041622b  mov     [rsp+0A8h+var_68], r8d
0x100416230  test    r8d, r8d
0x100416233  jle     loc_1004165AC
0x100416239  mov     r10d, 25h ; '%'
0x10041623f  lea     r9, cs:100400000h
0x100416246  cmp     edi, r12d
0x100416249  jge     loc_10041658E
0x10041624f  test    r14d, r14d
0x100416252  jnz     loc_100416593
0x100416258  test    edx, edx
0x10041625a  jnz     loc_1004165C2
0x100416260  movsxd  rax, edi
0x100416263  movzx   ecx, word ptr [rsi+rax*2]
0x100416267  inc     edi
0x100416269  cmp     r10w, cx
0x10041626d  jnz     loc_100416567
0x100416273  movsxd  rbp, edi
0x100416276  movzx   edx, word ptr [rsi+rbp*2]
0x10041627a  lea     eax, [rdx-20h]; switch 79 cases
0x10041627d  cmp     eax, 4Eh
0x100416280  ja      short def_100416298; jumptable 0000000100416298 default case, cases 34-36,38-45,47,49-109
0x100416282  cdqe
0x100416284  movzx   eax, ds:(byte_100416644 - 100400000h)[r9+rax]
0x10041628d  mov     ecx, ds:(jpt_100416298 - 100400000h)[r9+rax*4]
0x100416295  add     rcx, r9
0x100416298  jmp     rcx; switch jump
0x10041629a  movsxd  rax, ebx; jumptable 0000000100416298 cases 32,33,37,46
0x10041629d  mov     rcx, [rsp+0A8h+arg_20]
0x1004162a5  mov     [rcx+rax*2], dx
0x1004162a9  inc     ebx
0x1004162ab  inc     edi; jumptable 0000000100416298 case 48
0x1004162ad  jmp     loc_100416578
0x1004162b2  movsxd  rax, ebx; jumptable 0000000100416298 case 110
0x1004162b5  mov     r11, [rsp+0A8h+arg_20]
0x1004162bd  mov     [r11+rax*2], r13w
0x1004162c2  inc     ebx
0x1004162c4  cmp     ebx, r8d
0x1004162c7  jge     short loc_1004162DB
0x1004162c9  movsxd  rax, ebx
0x1004162cc  mov     ecx, 0Ah
0x1004162d1  mov     [r11+rax*2], cx
0x1004162d6  jmp     loc_100416576
0x1004162db  mov     edx, r15d
0x1004162de  mov     [rsp+0A8h+arg_0], edx
0x1004162e5  jmp     loc_10041657F
0x1004162ea  mov     r10d, edi; jumptable 0000000100416298 default case, cases 34-36,38-45,47,49-109
0x1004162ed  mov     [rsp+0A8h+var_60], edi
0x1004162f1  mov     rdx, [rsp+0A8h+arg_40]
0x1004162f9  mov     eax, [rdx+1070h]
0x1004162ff  mov     [rsp+0A8h+var_5C], eax
0x100416303  mov     r13d, r11d
0x100416306  mov     r9d, r11d
0x100416309  mov     [rsp+0A8h+var_64], r11d
0x10041630e  mov     r14d, r11d
0x100416311  movsxd  r15, r12d
0x100416314  cmp     rbp, r15
0x100416317  jge     loc_1004163AE
0x10041631d  lfence
0x100416320  mov     r12d, 1
0x100416326  test    r14d, r14d
0x100416329  jnz     short loc_100416393
0x10041632b  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x100416331  mov     rdx, rax; Locale
0x100416334  movzx   ecx, word ptr [rsi+rbp*2]; C
0x100416338  call    cs:__imp__iswdigit_l
0x10041633e  xor     r11d, r11d
0x100416341  test    eax, eax
0x100416343  jz      short loc_10041638E
0x100416345  mov     r9d, r12d
0x100416348  mov     [rsp+0A8h+var_64], r12d
0x10041634d  movzx   r8d, word ptr [rsi+rbp*2]
0x100416352  mov     ecx, 8000002Fh
0x100416357  sub     ecx, r8d
0x10041635a  mov     eax, 66666667h
0x10041635f  imul    ecx
0x100416361  sar     edx, 2
0x100416364  mov     eax, edx
0x100416366  shr     eax, 1Fh
0x100416369  add     edx, eax
0x10041636b  mov     r14d, r11d
0x10041636e  cmp     r13d, edx
0x100416371  setnle  r14b
0x100416375  inc     edi
0x100416377  inc     rbp
0x10041637a  lea     r13d, [r13+r13*4+0]
0x10041637f  lea     r13d, [r13-18h]
0x100416383  lea     r13d, [r8+r13*2]
0x100416387  cmp     rbp, r15
0x10041638a  jl      short loc_100416326
0x10041638c  jmp     short loc_100416393
0x10041638e  mov     r9d, [rsp+0A8h+var_64]
0x100416393  mov     r12, [rsp+0A8h+var_58]
0x100416398  mov     r10d, [rsp+0A8h+var_60]
0x10041639d  mov     eax, [rsp+0A8h+var_5C]
0x1004163a1  mov     r8d, [rsp+0A8h+var_68]
0x1004163a6  mov     rdx, [rsp+0A8h+arg_40]
0x1004163ae  mov     ecx, 0FFFFFFFFh
0x1004163b3  test    r9d, r9d
0x1004163b6  cmovnz  ecx, r13d
0x1004163ba  test    r14d, r14d
0x1004163bd  jnz     loc_10041654D
0x1004163c3  cmp     eax, 0FFFFFFFFh
0x1004163c6  jz      short loc_1004163D0
0x1004163c8  cmp     ecx, eax
0x1004163ca  jg      loc_10041654D
0x1004163d0  test    ecx, ecx
0x1004163d2  jle     loc_10041654D
0x1004163d8  movsxd  rax, edi
0x1004163db  mov     r9d, 21h ; '!'
0x1004163e1  cmp     r9w, [rsi+rax*2]
0x1004163e6  jnz     short loc_100416413
0x1004163e8  inc     edi
0x1004163ea  movsxd  rax, edi
0x1004163ed  cmp     rax, r15
0x1004163f0  jge     short loc_100416403
0x1004163f2  cmp     r9w, [rsi+rax*2]
0x1004163f7  jz      short loc_100416403
0x1004163f9  inc     edi
0x1004163fb  inc     rax
0x1004163fe  cmp     rax, r15
0x100416401  jl      short loc_1004163F2
0x100416403  movsxd  rax, edi
0x100416406  inc     edi
0x100416408  cmp     r9w, [rsi+rax*2]
0x10041640d  jnz     loc_10041654D
0x100416413  mov     r14d, r11d
0x100416416  cmp     [rsp+0A8h+arg_48], 0
0x10041641e  jnz     loc_1004164C5
0x100416424  mov     eax, 409h
0x100416429  cmp     [rsp+0A8h+arg_18], ax
0x100416431  jz      loc_1004164C5
0x100416437  mov     r11, [rsp+0A8h+arg_20]
0x10041643f  cmp     ebx, r8d
0x100416442  jge     short loc_100416453
0x100416444  movsxd  rax, ebx
0x100416447  mov     ecx, 25h ; '%'
0x10041644c  mov     [r11+rax*2], cx
0x100416451  inc     ebx
0x100416453  movsxd  rcx, ebx
0x100416456  movsxd  r8, r8d
0x100416459  cmp     rcx, r8
0x10041645c  jge     short loc_100416488
0x10041645e  movsxd  rdx, r10d
0x100416461  movsxd  r9, edi
0x100416464  cmp     rdx, r9
0x100416467  jge     short loc_100416482
0x100416469  movzx   eax, word ptr [rsi+rdx*2]
0x10041646d  mov     [r11+rcx*2], ax
0x100416472  inc     ebx
0x100416474  inc     rcx
0x100416477  inc     r10d
0x10041647a  inc     rdx
0x10041647d  cmp     rcx, r8
0x100416480  jl      short loc_100416464
0x100416482  mov     r9d, 21h ; '!'
0x100416488  cmp     r10d, edi
0x10041648b  jnz     short loc_1004164BA
  ... truncated ...
```
