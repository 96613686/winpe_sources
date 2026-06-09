# XE_FileWriter<XE_FileWriterDefaultPolicy<1,&wchar_t near * XEPackage0::DefaultFileExtension>,XE_MetadataTracker>::WriteBufferInternal(XE_Log *,XEBufferHeader * const,uint,unsigned __int64 &,int)

- ea: `0x10043c550`
- end: `0x10043c77e`
- name: `?WriteBufferInternal@?$XE_FileWriter@V?$XE_FileWriterDefaultPolicy@$00$1?DefaultFileExtension@XEPackage0@@3PA_WA@@VXE_MetadataTracker@@@@AEAAHPEAVXE_Log@@QEAUXEBufferHeader@@IAEA_KH@Z`
- size: `558`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x10043c470`
- `0x1005bdfb0`

## callees

- `0x100403070`
- `0x10043c550`
- `0x10043c790`
- `0x1005beb90`
- `0x1005bec50`
- `0x1005bef10`

## import_xrefs

- `KERNEL32!GetSystemTime` at `0x1005be341`
- `KERNEL32!GetSystemTime` at `0x1005be341`
- `KERNEL32!SetEndOfFile` at `0x1005be2fb`
- `KERNEL32!SetEndOfFile` at `0x1005be2fb`
- `KERNEL32!SetFilePointerEx` at `0x1005be2e7`
- `KERNEL32!SetFilePointerEx` at `0x1005be2e7`
- `KERNEL32!GetLastError` at `0x1005be193`
- `KERNEL32!GetLastError` at `0x1005be312`
- `KERNEL32!GetLastError` at `0x1005be193`
- `KERNEL32!GetLastError` at `0x1005be312`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall XE_FileWriter<XE_FileWriterDefaultPolicy<1,&wchar_t near * XEPackage0::DefaultFileExtension>,XE_MetadataTracker>::WriteBufferInternal(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned __int64 *a5,
        int a6)
{
  __int64 v6; // r10
  unsigned int v9; // ecx
  DWORD v10; // r13d
  unsigned int v11; // eax
  __int64 v12; // r9
  _BYTE *v13; // r8
  unsigned int v14; // edx
  unsigned __int64 v15; // r12
  unsigned __int64 v16; // rdx
  int v17; // ebp
  DWORD v18; // r14d
  unsigned __int64 v19; // r8
  __int64 v20; // rcx
  __int64 v21; // rsi
  unsigned int v22; // eax
  int v23; // edi
  unsigned __int64 v24; // rdi
  __int64 v26; // r13
  unsigned int v27; // eax
  unsigned __int8 (__fastcall ***v28)(_QWORD, __int64); // rax
  __int64 v29; // rdx
  int v30; // ecx
  unsigned __int64 v31; // r14
  unsigned __int64 v32; // rax
  bool v33; // zf
  void *v34; // rcx
  int v35; // eax
  __int64 *v36; // rsi
  __int64 v37; // rbp
  DWORD LastError; // eax
  int v39; // [rsp+30h] [rbp-538h]
  DWORD v40; // [rsp+34h] [rbp-534h]
  int v41; // [rsp+38h] [rbp-530h]
  DWORD v42; // [rsp+3Ch] [rbp-52Ch]
  unsigned __int64 v43; // [rsp+40h] [rbp-528h]
  unsigned __int64 v44; // [rsp+48h] [rbp-520h]
  BOOL v46; // [rsp+64h] [rbp-504h]
  BOOL v47; // [rsp+74h] [rbp-4F4h]
  struct _SYSTEMTIME SystemTime; // [rsp+90h] [rbp-4D8h] BYREF
  char v49[4]; // [rsp+A0h] [rbp-4C8h] BYREF
  unsigned int v50; // [rsp+A4h] [rbp-4C4h]
  int v51; // [rsp+508h] [rbp-60h]

  v6 = a3;
  v9 = a4 + *(unsigned __int16 *)(a3 + 22);
  v10 = v9 + *(_DWORD *)(a2 + 8) - 1 - (v9 + *(_DWORD *)(a2 + 8) - 1) % *(_DWORD *)(a2 + 8);
  v42 = v10;
  *(_DWORD *)(a3 + 16) = v10;
  *(_DWORD *)(a3 + 24) = a4;
  v11 = 1024;
  if ( a4 <= 0x400 )
    v11 = a4;
  v12 = v11;
  v13 = (_BYTE *)(a3 + v9 - (unsigned __int64)v11);
  v14 = -1;
  if ( v11 )
  {
    do
    {
      v14 = *((_DWORD *)&crctab + (unsigned __int8)(v14 ^ *v13++)) ^ (v14 >> 8);
      --v12;
    }
    while ( v12 );
  }
  *(_DWORD *)(v6 + 28) = v14;
  v15 = 0;
  v16 = 0;
  v43 = 0;
  v17 = 1;
  v39 = 1;
  v41 = -1;
  v18 = 0;
  v40 = 0;
  v19 = v10;
  v44 = v10;
  v20 = (unsigned __int64)v10 <= *(_QWORD *)(a1 + 24);
  if ( (unsigned __int64)v10 > *(_QWORD *)(a1 + 24) )
    return 0;
  while ( 1 )
  {
    v21 = *(_QWORD *)a2;
    v46 = 0;
    if ( a6 )
    {
      v22 = qword_100714F70(v21, 0, 0xFFFFFFFFLL);
      v20 = v22;
      v46 = v22 == 0;
      if ( v22 )
      {
        v23 = 0;
        (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 1656) + 40LL))(*(_QWORD *)(a1 + 1656), 0);
        goto LABEL_21;
      }
      v16 = v43;
      v19 = v44;
      v6 = a3;
    }
    v23 = 1;
    if ( v17 )
    {
      v41 = *(_DWORD *)(a2 + 40);
      v15 = v19 + _InterlockedExchangeAdd64((volatile signed __int64 *)(a2 + 24), v19);
      if ( *(_DWORD *)(a1 + 1832) )
      {
        v16 = _InterlockedIncrement64((volatile signed __int64 *)(a2 + 32));
        v43 = v16;
      }
      v17 = 0;
      v39 = 0;
    }
    if ( v15 <= *(_QWORD *)(a2 + 16) && *(_QWORD *)(a2 + 632) != -1 && (!*(_DWORD *)(a1 + 1832) || v16 <= 0xC350) )
      break;
LABEL_21:
    if ( v46 )
      qword_100714F78(v21, 0);
    v26 = *(_QWORD *)a2;
    v47 = 0;
    if ( a6 && (v27 = qword_100714F70(v26, 1, 0xFFFFFFFFLL), v20 = v27, v47 = v27 == 0, v27) )
    {
      (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 1656) + 40LL))(*(_QWORD *)(a1 + 1656), 1);
      v23 = 0;
    }
    else
    {
      if ( !v23 )
      {
        XE_FileWriter<XE_FileWriterDefaultPolicy<1,&wchar_t near * XEPackage0::DefaultFileExtension>,XE_MetadataTracker>::CloseLog(
          v20,
          a2,
          *(_QWORD *)(a2 + 648));
        goto LABEL_26;
      }
      if ( v18 == 6 || (v30 = 0, *(_QWORD *)(a2 + 632) == -1) )
        v30 = 1;
      if ( v41 >= *(_DWORD *)(a2 + 40) )
      {
        if ( (*(_QWORD *)(a2 + 24) > *(_QWORD *)(a1 + 24) || v30)
          && (!(unsigned int)XE_FileWriter<XE_FileWriterDefaultPolicy<1,&wchar_t near * XEPackage0::DefaultFileExtension>,XE_MetadataTracker>::IsSessionClosing(a1)
           || !*(_DWORD *)(a2 + 52))
          || *(_DWORD *)(a1 + 1832) && *(_QWORD *)(a2 + 32) > 0xC350u )
        {
          GetSystemTime(&SystemTime);
          *(struct _SYSTEMTIME *)(a2 + 72) = SystemTime;
          v23 = XE_FileWriter<XE_FileWriterDefaultPolicy<1,&wchar_t near * XEPackage0::DefaultFileExtension>,XE_MetadataTracker>::RolloverLog(
                  a1,
                  a2);
          v17 = 1;
          v39 = 1;
          goto LABEL_26;
        }
        v23 = 1;
        if ( v15 + *(_QWORD *)(a2 + 24) <= *(_QWORD *)(a2 + 16) )
          goto LABEL_65;
        v31 = (v15 + 511) & 0xFFFFFFFFFFFFFE00uLL;
        if ( !(unsigned int)XE_FileWriter<XE_FileWriterDefaultPolicy<1,&wchar_t near * XEPackage0::DefaultFileExtension>,XE_MetadataTracker>::IsSessionClosing(a1) )
          v31 = v15 + *(_QWORD *)(a1 + 32) - 1LL - (v15 + *(_QWORD *)(a1 + 32) - 1LL) % *(_QWORD *)(a1 + 32);
        if ( v31 )
          v32 = *(unsigned int *)(a2 + 8) * ((v31 + *(unsigned int *)(a2 + 8) - 1LL) / *(unsigned int *)(a2 + 8));
        else
          v32 = 0;
        v33 = *(_DWORD *)(a2 + 52) == 0;
        _mm_lfence();
        v34 = *(void **)(a2 + 632);
        if ( v33 )
        {
          if ( !SetFilePointerEx(v34, (LARGE_INTEGER)v32, 0, 0) )
          {
LABEL_64:
            _mm_lfence();
            v36 = *(__int64 **)(a1 + 1656);
            v37 = *v36;
            LastError = GetLastError();
            (*(void (__fastcall **)(__int64 *, _QWORD, unsigned __int64, __int64))(v37 + 56))(
              v36,
              LastError,
              v31,
              a2 + 112);
            v23 = 0;
            v18 = v40;
LABEL_65:
            v17 = v39;
            goto LABEL_26;
          }
          _mm_lfence();
          v35 = SetEndOfFile(*(HANDLE *)(a2 + 632));
        }
        else
        {
          v35 = qword_100715080(v34, v32);
        }
        if ( !v35 )
          goto LABEL_64;
        *(_QWORD *)(a2 + 16) = v31;
        v18 = v40;
        v17 = v39;
      }
      else
      {
        v17 = 1;
        v39 = 1;
      }
    }
LABEL_26:
    v51 = -1;
    v28 = (unsigned __int8 (__fastcall ***)(_QWORD, __int64))qword_1007152F8();
    LOBYTE(v29) = 8;
    if ( (**v28)(v28, v29) )
    {
      v20 = *(_QWORD *)(a1 + 1944);
      if ( v20 )
      {
        if ( (unsigned int)qword_1007151F0(v20, v49)
          && ((v50 >> 7) & 1) != 0
          && *(_QWORD *)(a2 + 632) == -1
          && *(_DWORD *)(a2 + 52) )
        {
          v23 = 0;
        }
      }
    }
    if ( v47 )
      qword_100714F78(v26, 1);
    if ( !v23 )
      return 0;
    v16 = v43;
    v19 = v44;
    v10 = v42;
    v6 = a3;
  }
  v24 = v15 - v19;
  _mm_lfence();
  if ( !(unsigned int)XE_FileWriter<XE_FileWriterDefaultPolicy<1,&wchar_t near * XEPackage0::DefaultFileExtension>,XE_MetadataTracker>::WriteLog(
                        a1,
                        a2,
                        (char *)(v15 - v19),
                        (char *)v6,
                        v10) )
  {
    _mm_lfence();
    v18 = GetLastError();
    v40 = v18;
    (*(void (__fastcall **)(_QWORD, _QWORD, unsigned __int64, _QWORD, __int64))(**(_QWORD **)(a1 + 1656) + 64LL))(
      *(_QWORD *)(a1 + 1656),
      v18,
      v24,
      v10,
      a2 + 112);
    v23 = v18 == 6;
    goto LABEL_21;
  }
  *a5 = v24;
  if ( v46 )
    qword_100714F78(v21, 0);
  return 1;
}

```

## disassembly

```asm
0x10043c550  push    rbx
0x10043c552  push    rbp
0x10043c553  push    rsi
0x10043c554  push    rdi
0x10043c555  push    r12
0x10043c557  push    r13
0x10043c559  push    r14
0x10043c55b  push    r15
0x10043c55d  sub     rsp, 528h
0x10043c564  mov     [rsp+568h+var_4E0], 0FFFFFFFFFFFFFFFEh
0x10043c570  mov     rax, cs:__security_cookie
0x10043c577  xor     rax, rsp
0x10043c57a  mov     [rsp+568h+var_58], rax
0x10043c582  mov     r10, r8
0x10043c585  mov     [rsp+568h+var_518], r8
0x10043c58a  mov     rbx, rdx
0x10043c58d  mov     r15, rcx
0x10043c590  mov     rax, [rsp+568h+arg_20]
0x10043c598  mov     [rsp+568h+var_4E8], rax
0x10043c5a0  mov     r8d, [rdx+8]
0x10043c5a4  movzx   ecx, word ptr [r10+16h]
0x10043c5a9  add     ecx, r9d
0x10043c5ac  lea     r13d, [r8-1]
0x10043c5b0  add     r13d, ecx
0x10043c5b3  xor     edx, edx
0x10043c5b5  mov     eax, r13d
0x10043c5b8  div     r8d
0x10043c5bb  sub     r13d, edx
0x10043c5be  mov     [rsp+568h+var_52C], r13d
0x10043c5c3  mov     [r10+10h], r13d
0x10043c5c7  mov     [r10+18h], r9d
0x10043c5cb  mov     eax, 400h
0x10043c5d0  cmp     r9d, eax
0x10043c5d3  cmovbe  eax, r9d
0x10043c5d7  mov     r9d, eax
0x10043c5da  mov     r8d, ecx
0x10043c5dd  sub     r8, r9
0x10043c5e0  add     r8, r10
0x10043c5e3  mov     edx, 0FFFFFFFFh
0x10043c5e8  test    eax, eax
0x10043c5ea  jz      short loc_10043C61D
0x10043c5ec  lea     r11, ?crctab@@3QBKB; ulong const near * const crctab
0x10043c5f3  nop     dword ptr [rax+00h]
0x10043c5f7  nop     word ptr [rax+rax+00000000h]
0x10043c600  movzx   ecx, byte ptr [r8]
0x10043c604  mov     eax, edx
0x10043c606  xor     rcx, rax
0x10043c609  movzx   eax, cl
0x10043c60c  shr     edx, 8
0x10043c60f  xor     edx, [r11+rax*4]
0x10043c613  lea     r8, [r8+1]
0x10043c617  sub     r9, 1
0x10043c61b  jnz     short loc_10043C600
0x10043c61d  mov     [r10+1Ch], edx
0x10043c621  xor     r11d, r11d
0x10043c624  mov     r12d, r11d
0x10043c627  mov     edx, r11d
0x10043c62a  mov     [rsp+568h+var_528], rdx
0x10043c62f  mov     ebp, 1
0x10043c634  mov     [rsp+568h+var_538], ebp
0x10043c638  mov     [rsp+568h+var_530], 0FFFFFFFFh
0x10043c640  mov     r14d, r11d
0x10043c643  mov     [rsp+568h+var_534], r11d
0x10043c648  mov     r8d, r13d
0x10043c64b  mov     [rsp+568h+var_520], r8
0x10043c650  mov     ecx, r11d
0x10043c653  cmp     r8, [r15+18h]
0x10043c657  setbe   cl
0x10043c65a  ja      loc_1005BE38B
0x10043c660  mov     rsi, [rbx]
0x10043c663  mov     [rsp+568h+var_510], rsi
0x10043c668  mov     [rsp+568h+var_508], 0
0x10043c671  cmp     [rsp+568h+arg_28], 0
0x10043c679  jz      short loc_10043C6B4
0x10043c67b  xor     edx, edx
0x10043c67d  mov     r8d, 0FFFFFFFFh
0x10043c683  mov     rcx, rsi
0x10043c686  call    cs:qword_100714F70
0x10043c68c  mov     ecx, eax
0x10043c68e  xor     r11d, r11d
0x10043c691  mov     eax, r11d
0x10043c694  test    ecx, ecx
0x10043c696  setz    al
0x10043c699  mov     dword ptr [rsp+568h+var_508+4], eax
0x10043c69d  test    ecx, ecx
0x10043c69f  jnz     loc_1005BE04C
0x10043c6a5  mov     rdx, [rsp+568h+var_528]
0x10043c6aa  mov     r8, [rsp+568h+var_520]
0x10043c6af  mov     r10, [rsp+568h+var_518]
0x10043c6b4  mov     edi, 1
0x10043c6b9  test    ebp, ebp
0x10043c6bb  jz      short loc_10043C6E8
0x10043c6bd  mov     r9d, [rbx+28h]
0x10043c6c1  mov     [rsp+568h+var_530], r9d
0x10043c6c6  mov     r12, r8
0x10043c6c9  lock xadd [rbx+18h], r12
0x10043c6cf  add     r12, r8
0x10043c6d2  cmp     dword ptr [r15+728h], 0
0x10043c6da  jnz     loc_1005BE167
0x10043c6e0  mov     ebp, r11d
0x10043c6e3  mov     [rsp+568h+var_538], r11d
0x10043c6e8  cmp     r12, [rbx+10h]
0x10043c6ec  ja      loc_1005BE061
0x10043c6f2  cmp     qword ptr [rbx+278h], 0FFFFFFFFFFFFFFFFh
0x10043c6fa  jz      loc_1005BE061
0x10043c700  cmp     dword ptr [r15+728h], 0
0x10043c708  jnz     loc_1005BE17D
0x10043c70e  mov     rdi, r12
0x10043c711  sub     rdi, r8
0x10043c714  lfence
0x10043c717  mov     dword ptr [rsp+568h+var_548], r13d
0x10043c71c  mov     r9, r10
0x10043c71f  mov     r8, rdi
0x10043c722  mov     rdx, rbx
0x10043c725  mov     rcx, r15
0x10043c728  call    ?WriteLog@?$XE_FileWriter@V?$XE_FileWriterDefaultPolicy@$00$1?DefaultFileExtension@XEPackage0@@3PA_WA@@VXE_MetadataTracker@@@@AEAAHPEAVXE_Log@@_KQEBXI@Z; XE_FileWriter<XE_FileWriterDefaultPolicy<1,&wchar_t near * XEPackage0::DefaultFileExtension>,XE_MetadataTracker>::WriteLog(XE_Log *,unsigned __int64,void const * const,uint)
0x10043c72d  test    eax, eax
0x10043c72f  jz      loc_1005BE190
0x10043c735  mov     rcx, [rsp+568h+var_4E8]
0x10043c73d  mov     [rcx], rdi
0x10043c740  cmp     dword ptr [rsp+568h+var_508+4], 0
0x10043c745  jz      short loc_10043C752
0x10043c747  xor     edx, edx
0x10043c749  mov     rcx, rsi
0x10043c74c  call    cs:qword_100714F78
0x10043c752  mov     eax, 1
0x10043c757  jmp     short loc_10043C75A
0x10043c75a  mov     rcx, [rsp+568h+var_58]
0x10043c762  xor     rcx, rsp; StackCookie
0x10043c765  call    __security_check_cookie
0x10043c76a  add     rsp, 528h
0x10043c771  pop     r15
0x10043c773  pop     r14
0x10043c775  pop     r13
0x10043c777  pop     r12
0x10043c779  pop     rdi
0x10043c77a  pop     rsi
0x10043c77b  pop     rbp
0x10043c77c  pop     rbx
0x10043c77d  retn
0x1005be04c  mov     edi, r11d
0x1005be04f  mov     rcx, [r15+678h]
0x1005be056  mov     rax, [rcx]
0x1005be059  xor     edx, edx
0x1005be05b  call    qword ptr [rax+28h]
0x1005be05e  jmp     short loc_1005BE061
0x1005be061  cmp     dword ptr [rsp+568h+var_508+4], 0
0x1005be066  jz      short loc_1005BE073
0x1005be068  xor     edx, edx
0x1005be06a  mov     rcx, rsi
0x1005be06d  call    cs:qword_100714F78
0x1005be073  mov     r13, [rbx]
0x1005be076  mov     [rsp+568h+var_500], r13
0x1005be07b  mov     qword ptr [rsp+568h+var_4F8], 1
0x1005be084  xor     esi, esi
0x1005be086  cmp     [rsp+568h+arg_28], esi
0x1005be08d  jz      loc_1005BE1D0
0x1005be093  lea     edx, [rsi+1]
0x1005be096  mov     r8d, 0FFFFFFFFh
0x1005be09c  mov     rcx, r13
0x1005be09f  call    cs:qword_100714F70
0x1005be0a5  mov     ecx, eax
0x1005be0a7  mov     eax, esi
0x1005be0a9  test    ecx, ecx
0x1005be0ab  setz    al
0x1005be0ae  mov     [rsp+568h+var_4F8+4], eax
0x1005be0b2  test    ecx, ecx
0x1005be0b4  jz      loc_1005BE1D0
0x1005be0ba  mov     rcx, [r15+678h]
0x1005be0c1  mov     rax, [rcx]
0x1005be0c4  lea     edx, [rsi+1]
0x1005be0c7  call    qword ptr [rax+28h]
0x1005be0ca  mov     edi, esi
0x1005be0cc  jmp     short loc_1005BE0CF
0x1005be0cf  mov     [rsp+568h+var_60], 0FFFFFFFFh
0x1005be0da  call    cs:qword_1007152F8
0x1005be0e0  mov     r8, [rax]
0x1005be0e3  mov     dl, 8
0x1005be0e5  mov     rcx, rax
0x1005be0e8  call    qword ptr [r8]
0x1005be0eb  test    al, al
0x1005be0ed  jz      short loc_1005BE12D
0x1005be0ef  mov     rcx, [r15+798h]
0x1005be0f6  test    rcx, rcx
0x1005be0f9  jz      short loc_1005BE12D
0x1005be0fb  lea     rdx, [rsp+568h+var_4C8]
0x1005be103  call    cs:qword_1007151F0
0x1005be109  test    eax, eax
0x1005be10b  jz      short loc_1005BE12D
0x1005be10d  mov     eax, [rsp+568h+var_4C4]
0x1005be114  shr     eax, 7
0x1005be117  and     eax, 1
0x1005be11a  jz      short loc_1005BE12D
0x1005be11c  cmp     qword ptr [rbx+278h], 0FFFFFFFFFFFFFFFFh
0x1005be124  jnz     short loc_1005BE12D
0x1005be126  cmp     dword ptr [rbx+34h], 0
0x1005be12a  cmovnz  edi, esi
0x1005be12d  cmp     [rsp+568h+var_4F8+4], 0
0x1005be132  jz      short loc_1005BE142
0x1005be134  mov     edx, 1
0x1005be139  mov     rcx, r13
0x1005be13c  call    cs:qword_100714F78
0x1005be142  test    edi, edi
0x1005be144  jz      loc_1005BE384
0x1005be14a  mov     rdx, [rsp+568h+var_528]
0x1005be14f  mov     r8, [rsp+568h+var_520]
0x1005be154  mov     r13d, [rsp+568h+var_52C]
0x1005be159  mov     r10, [rsp+568h+var_518]
0x1005be15e  xor     r11d, r11d
0x1005be161  jmp     loc_10043C660
0x1005be167  mov     edx, edi
0x1005be169  lock xadd [rbx+20h], rdx
0x1005be16f  inc     rdx
0x1005be172  mov     [rsp+568h+var_528], rdx
0x1005be177  jmp     loc_10043C6E0
0x1005be17d  cmp     rdx, 0C350h
0x1005be184  jbe     loc_10043C70E
0x1005be18a  jmp     loc_1005BE061
0x1005be190  lfence
0x1005be193  call    cs:__imp_GetLastError
0x1005be199  mov     r14d, eax
0x1005be19c  mov     [rsp+568h+var_534], eax
0x1005be1a0  mov     rcx, [r15+678h]
0x1005be1a7  mov     r10, [rcx]
0x1005be1aa  lea     rax, [rbx+70h]
0x1005be1ae  mov     [rsp+568h+var_548], rax
0x1005be1b3  mov     r9d, r13d
0x1005be1b6  mov     r8, rdi
0x1005be1b9  mov     edx, r14d
0x1005be1bc  call    qword ptr [r10+40h]
0x1005be1c0  xor     edi, edi
0x1005be1c2  cmp     r14d, 6
0x1005be1c6  setz    dil
0x1005be1ca  jmp     loc_1005BE061
0x1005be1d0  test    edi, edi
0x1005be1d2  jz      loc_1005BE36E
0x1005be1d8  cmp     r14d, 6
0x1005be1dc  jz      short loc_1005BE1EA
0x1005be1de  cmp     qword ptr [rbx+278h], 0FFFFFFFFFFFFFFFFh
0x1005be1e6  mov     ecx, esi
0x1005be1e8  jnz     short loc_1005BE1EF
0x1005be1ea  mov     ecx, 1
0x1005be1ef  mov     eax, [rbx+28h]
0x1005be1f2  cmp     [rsp+568h+var_530], eax
0x1005be1f6  jge     short loc_1005BE206
0x1005be1f8  mov     ebp, 1
0x1005be1fd  mov     [rsp+568h+var_538], ebp
0x1005be201  jmp     loc_1005BE0CF
0x1005be206  mov     rax, [r15+18h]
0x1005be20a  cmp     [rbx+18h], rax
0x1005be20e  ja      short loc_1005BE214
0x1005be210  test    ecx, ecx
0x1005be212  jz      short loc_1005BE22E
0x1005be214  mov     rcx, r15
0x1005be217  call    ?IsSessionClosing@?$XE_FileWriter@V?$XE_FileWriterDefaultPolicy@$00$1?DefaultFileExtension@XEPackage0@@3PA_WA@@VXE_MetadataTracker@@@@AEBAHXZ; XE_FileWriter<XE_FileWriterDefaultPolicy<1,&wchar_t near * XEPackage0::DefaultFileExtension>,XE_MetadataTracker>::IsSessionClosing(void)
0x1005be21c  test    eax, eax
0x1005be21e  jz      loc_1005BE339
0x1005be224  cmp     dword ptr [rbx+34h], 0
0x1005be228  jz      loc_1005BE339
0x1005be22e  cmp     dword ptr [r15+728h], 0
0x1005be236  jz      short loc_1005BE246
0x1005be238  cmp     qword ptr [rbx+20h], 0C350h
0x1005be240  ja      loc_1005BE339
0x1005be246  mov     edi, 1
0x1005be24b  mov     rcx, [rbx+18h]
0x1005be24f  add     rcx, r12
0x1005be252  cmp     rcx, [rbx+10h]
0x1005be256  jbe     loc_1005BE330
0x1005be25c  lea     r14, [r12+1FFh]
0x1005be264  and     r14, 0FFFFFFFFFFFFFE00h
0x1005be26b  mov     rcx, r15
0x1005be26e  call    ?IsSessionClosing@?$XE_FileWriter@V?$XE_FileWriterDefaultPolicy@$00$1?DefaultFileExtension@XEPackage0@@3PA_WA@@VXE_MetadataTracker@@@@AEBAHXZ; XE_FileWriter<XE_FileWriterDefaultPolicy<1,&wchar_t near * XEPackage0::DefaultFileExtension>,XE_MetadataTracker>::IsSessionClosing(void)
0x1005be273  test    eax, eax
0x1005be275  jnz     short loc_1005BE28D
0x1005be277  mov     rcx, [r15+20h]
0x1005be27b  lea     r14, [rcx-1]
0x1005be27f  add     r14, r12
0x1005be282  xor     edx, edx
0x1005be284  mov     rax, r14
0x1005be287  div     rcx
0x1005be28a  sub     r14, rdx
0x1005be28d  test    r14, r14
0x1005be290  jz      short loc_1005BE2DB
0x1005be292  mov     ecx, [rbx+8]
0x1005be295  lea     rax, [rcx-1]
0x1005be299  add     rax, r14
0x1005be29c  xor     edx, edx
0x1005be29e  div     rcx
0x1005be2a1  imul    rax, rcx
0x1005be2a5  jmp     short loc_1005BE2A8
0x1005be2a8  mov     rdx, rax; liDistanceToMove
0x1005be2ab  cmp     dword ptr [rbx+34h], 0
0x1005be2af  lfence
0x1005be2b2  mov     rcx, [rbx+278h]; hFile
0x1005be2b9  jz      short loc_1005BE2E1
0x1005be2bb  call    cs:qword_100715080
0x1005be2c1  jmp     short loc_1005BE2C4
0x1005be2c4  test    eax, eax
0x1005be2c6  jz      short loc_1005BE305
0x1005be2c8  mov     [rbx+10h], r14
  ... truncated ...
```
