# UtilCollectMemoryInfoHandle(tlx::unique_any<tlx::file_handle_traits>)

- ea: `0x18000d640`
- end: `0x18000dd00`
- name: `?UtilCollectMemoryInfoHandle@@YAJV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z`
- size: `1728`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180018e90`

## callees

- `0x1800029d0`
- `0x1800029f4`
- `0x180002ff0`
- `0x180004a44`
- `0x180006a80`
- `0x18000d640`
- `0x18000f7e4`
- `0x18000fe10`
- `0x180010f04`
- `0x180011b3c`
- `0x180011ef8`
- `0x180013724`
- `0x1800137a0`
- `0x180013df4`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d715`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d715`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000dc7e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000dc7e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dcdc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dcdc`

## string_xrefs

- `0x18000d8c4`: `,Services\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall UtilCollectMemoryInfoHandle(HANDLE *a1)
{
  HANDLE v2; // rax
  FARPROC ProcAddress; // rdi
  int ServicesInfo; // ebx
  char v5; // al
  unsigned int *v6; // r14
  __int64 v7; // r8
  int v8; // eax
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  unsigned int i; // edi
  unsigned int *v12; // rdi
  unsigned __int16 *v13; // r9
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  unsigned int j; // esi
  __int64 v18; // r8
  int v19; // edx
  unsigned int v20; // esi
  __int64 v21; // r9
  char *v22; // r10
  int *v23; // r8
  unsigned int v25; // [rsp+30h] [rbp-69h] BYREF
  DWORD v26; // [rsp+34h] [rbp-65h] BYREF
  _QWORD v27[2]; // [rsp+38h] [rbp-61h] BYREF
  HMODULE hModule; // [rsp+48h] [rbp-51h] BYREF
  wchar_t *v29; // [rsp+50h] [rbp-49h] BYREF
  wchar_t *v30; // [rsp+58h] [rbp-41h]
  _WORD v31[8]; // [rsp+60h] [rbp-39h] BYREF
  void *Block; // [rsp+70h] [rbp-29h] BYREF
  void *v33[2]; // [rsp+78h] [rbp-21h] BYREF
  __int64 v34; // [rsp+88h] [rbp-11h]
  _QWORD v35[3]; // [rsp+90h] [rbp-9h] BYREF
  __int64 v36; // [rsp+A8h] [rbp+Fh] BYREF
  int v37; // [rsp+B0h] [rbp+17h]
  wchar_t v38; // [rsp+B4h] [rbp+1Bh]

  v35[2] = a1;
  v27[0] = &CFileByteStream::`vftable';
  *(__m128i *)v33 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v34 = -1;
  Block = 0;
  v26 = 0;
  v29 = v31;
  v30 = v31;
  v31[0] = 0;
  v36 = *(_QWORD *)L"[Idle]";
  v37 = *(_DWORD *)L"e]";
  v38 = aIdle[6];
  v35[0] = 917516;
  v35[1] = &v36;
  v2 = *a1;
  *a1 = 0;
  v27[1] = v2;
  v25 = 51200;
  UtilLoadModFromSystem(&hModule);
  if ( !hModule )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
    ServicesInfo = -2147023739;
    goto LABEL_92;
  }
  ProcAddress = GetProcAddress(hModule, "ZwQuerySystemInformation");
  if ( !ProcAddress )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
    ServicesInfo = -2147024769;
LABEL_92:
    v6 = (unsigned int *)v33[0];
    goto LABEL_93;
  }
  do
  {
    v25 += 7680;
    v5 = utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(v33, v25);
    v6 = (unsigned int *)v33[0];
    if ( !v5 )
    {
      ServicesInfo = -2147024882;
      goto LABEL_93;
    }
    v7 = v34 - (unsigned __int64)v33[0];
    if ( v34 - (unsigned __int64)v33[0] >= 0xFFFFFFFF )
      v7 = 0xFFFFFFFFLL;
    v25 = v7;
    v8 = ((__int64 (__fastcall *)(__int64, void *, __int64, unsigned int *))ProcAddress)(5, v33[0], v7, &v25);
  }
  while ( v8 == -1073741820 );
  if ( v8 < 0 )
  {
    ServicesInfo = v8 | 0x10000000;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_93;
    v10 = 110;
    goto LABEL_15;
  }
  ServicesInfo = UtilGetServicesInfo(&Block, &v26);
  if ( ServicesInfo < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_93;
    v10 = 111;
    goto LABEL_15;
  }
  ServicesInfo = UtilWriteStringToByteStream((struct IWerByteStream *)v27, L"ImageName");
  if ( ServicesInfo < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_93;
    v10 = 112;
    goto LABEL_15;
  }
  for ( i = 0; i < 0x1F; ++i )
  {
    ServicesInfo = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                     &v29,
                     L",%ls",
                     (&off_1800372A0)[2 * i]);
    if ( ServicesInfo < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_93;
      v10 = 113;
      goto LABEL_15;
    }
    ServicesInfo = UtilWriteStringToByteStream((struct IWerByteStream *)v27, v29);
    if ( ServicesInfo < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_93;
      v10 = 114;
      goto LABEL_15;
    }
  }
  ServicesInfo = UtilWriteStringToByteStream((struct IWerByteStream *)v27, L",Services\r\n");
  if ( ServicesInfo < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_93;
    v10 = 115;
    goto LABEL_15;
  }
  v12 = v6;
  while ( 2 )
  {
    v13 = (unsigned __int16 *)v35;
    if ( *((_QWORD *)v12 + 10) )
      v13 = (unsigned __int16 *)(v12 + 14);
    ServicesInfo = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                     &v29,
                     L"\"%.*ls\",",
                     *v13 >> 1,
                     *((_QWORD *)v13 + 1));
    if ( ServicesInfo < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_93;
      v10 = 116;
      goto LABEL_15;
    }
    ServicesInfo = UtilWriteStringToByteStream((struct IWerByteStream *)v27, v29);
    if ( ServicesInfo < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_93;
      v10 = 117;
      goto LABEL_15;
    }
    for ( j = 0; j < 0x1F; ++j )
    {
      if ( ((*((_DWORD *)&off_1800372A0 + 4 * j + 3) - 4) & 0xFFFFFFFB) != 0 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v14, &off_1800372A0, v15, v16);
      v18 = *((unsigned int *)&off_1800372A0 + 4 * j + 2);
      v30 = v29;
      *v29 = 0;
      if ( *((_DWORD *)&off_1800372A0 + 4 * j + 3) == 4 )
      {
        ServicesInfo = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                         &v29,
                         L"%lu,",
                         *(unsigned int *)((char *)v12 + v18));
        if ( ServicesInfo < 0 )
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_93;
          v10 = 118;
          goto LABEL_15;
        }
      }
      else
      {
        ServicesInfo = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                         &v29,
                         L"%llu,",
                         *(_QWORD *)((char *)v12 + v18));
        if ( ServicesInfo < 0 )
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_93;
          v10 = 119;
          goto LABEL_15;
        }
      }
      ServicesInfo = UtilWriteStringToByteStream((struct IWerByteStream *)v27, v29);
      if ( ServicesInfo < 0 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_93;
        v10 = 120;
        goto LABEL_15;
      }
    }
    v19 = 1;
    v20 = 0;
    if ( !v26 )
    {
LABEL_56:
      ServicesInfo = UtilWriteStringToByteStream((struct IWerByteStream *)v27, L"\r\n");
      if ( ServicesInfo >= 0 )
      {
        if ( !*v12 )
        {
          ServicesInfo = 0;
          goto LABEL_93;
        }
        v12 = (unsigned int *)((char *)v12 + *v12);
        continue;
      }
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_93;
      v10 = 123;
LABEL_15:
      WPP_SF_d(v9[2], v10, WPP_988ce82756cb3ec502560a762615dae0_Traceguids, (unsigned int)ServicesInfo);
      goto LABEL_93;
    }
    break;
  }
  while ( 1 )
  {
    v21 = 56LL * v20;
    v22 = (char *)Block;
    if ( *(_DWORD *)((char *)Block + v21 + 44) != v12[20] )
      goto LABEL_55;
    v30 = v29;
    *v29 = 0;
    v23 = &dword_180039414;
    if ( !v19 )
      v23 = (int *)L"|";
    ServicesInfo = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                     &v29,
                     L"%ls%ls",
                     v23,
                     *(_QWORD *)&v22[v21]);
    if ( ServicesInfo < 0 )
      break;
    ServicesInfo = UtilWriteStringToByteStream((struct IWerByteStream *)v27, v29);
    if ( ServicesInfo < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v10 = 122;
        goto LABEL_15;
      }
      goto LABEL_93;
    }
    v19 = 0;
LABEL_55:
    if ( ++v20 >= v26 )
      goto LABEL_56;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v10 = 121;
    goto LABEL_15;
  }
LABEL_93:
  CFileByteStream::Close((CFileByteStream *)v27);
  if ( hModule )
    FreeLibrary(hModule);
  if ( v29 != v31 )
    operator delete(v29, (const struct std::nothrow_t *)&std::nothrow);
  if ( Block )
    operator delete(Block);
  if ( v6 != (unsigned int *)-1LL )
    operator delete(v6, (const struct std::nothrow_t *)&std::nothrow);
  CFileByteStream::~CFileByteStream((CFileByteStream *)v27);
  if ( (unsigned __int64)*a1 + 1 > 1 )
    CloseHandle(*a1);
  return (unsigned int)ServicesInfo;
}

```

## disassembly

```asm
0x18000d640  push    rbp
0x18000d642  push    rbx
0x18000d643  push    rsi
0x18000d644  push    rdi
0x18000d645  push    r13
0x18000d647  push    r14
0x18000d649  lea     rbp, [rsp-2Fh]
0x18000d64e  sub     rsp, 0C8h
0x18000d655  mov     rax, cs:__security_cookie
0x18000d65c  xor     rax, rsp
0x18000d65f  mov     [rbp+57h+var_38], rax
0x18000d663  mov     r13, rcx
0x18000d666  mov     [rbp+57h+var_50], rcx
0x18000d66a  lea     rax, ??_7CFileByteStream@@6B@; const CFileByteStream::`vftable'
0x18000d671  mov     [rbp+57h+var_B8], rax
0x18000d675  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18000d67d  movdqu  xmmword ptr [rbp+57h+var_78], xmm0
0x18000d682  mov     [rbp+57h+var_68], 0FFFFFFFFFFFFFFFFh
0x18000d68a  mov     [rbp+57h+Block], 0
0x18000d692  mov     [rbp+57h+var_BC], 0
0x18000d699  lea     rax, [rbp+57h+var_90]
0x18000d69d  mov     [rbp+57h+var_A0], rax
0x18000d6a1  lea     rax, [rbp+57h+var_90]
0x18000d6a5  mov     [rbp+57h+var_98], rax
0x18000d6a9  xor     eax, eax
0x18000d6ab  mov     [rbp+57h+var_90], ax
0x18000d6af  movsd   xmm0, qword ptr cs:aIdle; "[Idle]"
0x18000d6b7  movsd   [rbp+57h+var_48], xmm0
0x18000d6bc  mov     eax, dword ptr cs:aIdle+8; "e]"
0x18000d6c2  mov     [rbp+57h+var_40], eax
0x18000d6c5  movzx   eax, word ptr cs:aIdle+0Ch; ""
0x18000d6cc  mov     [rbp+57h+var_3C], ax
0x18000d6d0  mov     [rbp+57h+var_60], 0E000Ch
0x18000d6d8  lea     rax, [rbp+57h+var_48]
0x18000d6dc  mov     [rbp+57h+var_58], rax
0x18000d6e0  mov     rax, [rcx]
0x18000d6e3  mov     qword ptr [rcx], 0
0x18000d6ea  mov     [rbp+57h+var_B0], rax
0x18000d6ee  mov     [rbp+57h+var_C0], 0C800h
0x18000d6f5  lea     rcx, [rbp+57h+hModule]
0x18000d6f9  call    ?UtilLoadModFromSystem@@YA?AV?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@PEB_W@Z; UtilLoadModFromSystem(wchar_t const *)
0x18000d6fe  nop
0x18000d6ff  cmp     [rbp+57h+hModule], 0
0x18000d704  jz      loc_18000DC32
0x18000d70a  lea     rdx, aZwquerysystemi; "ZwQuerySystemInformation"
0x18000d711  mov     rcx, [rbp+57h+hModule]; hModule
0x18000d715  call    cs:__imp_GetProcAddress
0x18000d71b  mov     rdi, rax
0x18000d71e  test    rax, rax
0x18000d721  jnz     short loc_18000D759
0x18000d723  lea     rax, WPP_GLOBAL_Control
0x18000d72a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d731  cmp     rcx, rax
0x18000d734  jz      short loc_18000D74F
0x18000d736  test    byte ptr [rcx+1Ch], 1
0x18000d73a  jz      short loc_18000D74F
0x18000d73c  lea     edx, [rdi+6Dh]
0x18000d73f  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18000d746  mov     rcx, [rcx+10h]
0x18000d74a  call    WPP_SF_
0x18000d74f  mov     ebx, 8007007Fh
0x18000d754  jmp     loc_18000DC65
0x18000d759  mov     esi, 0FFFFFFFFh
0x18000d75e  mov     eax, [rbp+57h+var_C0]
0x18000d761  add     eax, 1E00h
0x18000d766  mov     [rbp+57h+var_C0], eax
0x18000d769  mov     edx, eax
0x18000d76b  lea     rcx, [rbp+57h+var_78]
0x18000d76f  call    ?reserve@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::reserve(unsigned __int64)
0x18000d774  mov     r14, [rbp+57h+var_78]
0x18000d778  test    al, al
0x18000d77a  jz      loc_18000DC2B
0x18000d780  mov     r8, [rbp+57h+var_68]
0x18000d784  sub     r8, r14
0x18000d787  cmp     r8, rsi
0x18000d78a  jb      short loc_18000D78F
0x18000d78c  mov     r8d, esi
0x18000d78f  mov     [rbp+57h+var_C0], r8d
0x18000d793  lea     r9, [rbp+57h+var_C0]
0x18000d797  mov     rdx, r14
0x18000d79a  mov     ecx, 5
0x18000d79f  mov     rax, rdi
0x18000d7a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7a7  mov     ebx, eax
0x18000d7a9  cmp     eax, 0C0000004h
0x18000d7ae  jz      short loc_18000D75E
0x18000d7b0  test    eax, eax
0x18000d7b2  jns     short loc_18000D7F6
0x18000d7b4  bts     ebx, 1Ch
0x18000d7b8  lea     rax, WPP_GLOBAL_Control
0x18000d7bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d7c6  cmp     rcx, rax
0x18000d7c9  jz      loc_18000DC69
0x18000d7cf  test    byte ptr [rcx+1Ch], 1
0x18000d7d3  jz      loc_18000DC69
0x18000d7d9  mov     edx, 6Eh ; 'n'
0x18000d7de  mov     r9d, ebx
0x18000d7e1  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18000d7e8  mov     rcx, [rcx+10h]
0x18000d7ec  call    WPP_SF_d
0x18000d7f1  jmp     loc_18000DC69
0x18000d7f6  lea     rdx, [rbp+57h+var_BC]
0x18000d7fa  lea     rcx, [rbp+57h+Block]
0x18000d7fe  call    UtilGetServicesInfo
0x18000d803  mov     ebx, eax
0x18000d805  test    eax, eax
0x18000d807  jns     short loc_18000D831
0x18000d809  lea     rax, WPP_GLOBAL_Control
0x18000d810  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d817  cmp     rcx, rax
0x18000d81a  jz      loc_18000DC69
0x18000d820  test    byte ptr [rcx+1Ch], 1
0x18000d824  jz      loc_18000DC69
0x18000d82a  mov     edx, 6Fh ; 'o'
0x18000d82f  jmp     short loc_18000D7DE
0x18000d831  lea     rdx, aImagename; "ImageName"
0x18000d838  lea     rcx, [rbp+57h+var_B8]; struct IWerByteStream *
0x18000d83c  call    ?UtilWriteStringToByteStream@@YAJPEAUIWerByteStream@@PEB_W@Z; UtilWriteStringToByteStream(IWerByteStream *,wchar_t const *)
0x18000d841  mov     ebx, eax
0x18000d843  test    eax, eax
0x18000d845  jns     short loc_18000D872
0x18000d847  lea     rax, WPP_GLOBAL_Control
0x18000d84e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d855  cmp     rcx, rax
0x18000d858  jz      loc_18000DC69
0x18000d85e  test    byte ptr [rcx+1Ch], 1
0x18000d862  jz      loc_18000DC69
0x18000d868  mov     edx, 70h ; 'p'
0x18000d86d  jmp     loc_18000D7DE
0x18000d872  xor     edi, edi
0x18000d874  lea     rax, off_1800372A0; "UniqueProcessId"
0x18000d87b  mov     r8d, edi
0x18000d87e  add     r8, r8
0x18000d881  mov     r8, [rax+r8*8]
0x18000d885  lea     rdx, aLs_1; ",%ls"
0x18000d88c  lea     rcx, [rbp+57h+var_A0]
0x18000d890  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18000d895  mov     ebx, eax
0x18000d897  test    eax, eax
0x18000d899  js      loc_18000DC08
0x18000d89f  mov     rdx, [rbp+57h+var_A0]; wchar_t *
0x18000d8a3  lea     rcx, [rbp+57h+var_B8]; struct IWerByteStream *
0x18000d8a7  call    ?UtilWriteStringToByteStream@@YAJPEAUIWerByteStream@@PEB_W@Z; UtilWriteStringToByteStream(IWerByteStream *,wchar_t const *)
0x18000d8ac  mov     ebx, eax
0x18000d8ae  test    eax, eax
0x18000d8b0  js      loc_18000DBE5
0x18000d8b6  inc     edi
0x18000d8b8  cmp     edi, 1Fh
0x18000d8bb  lea     rax, off_1800372A0; "UniqueProcessId"
0x18000d8c2  jb      short loc_18000D87B
0x18000d8c4  lea     rdx, aServices; ",Services\r\n"
0x18000d8cb  lea     rcx, [rbp+57h+var_B8]; struct IWerByteStream *
0x18000d8cf  call    ?UtilWriteStringToByteStream@@YAJPEAUIWerByteStream@@PEB_W@Z; UtilWriteStringToByteStream(IWerByteStream *,wchar_t const *)
0x18000d8d4  mov     ebx, eax
0x18000d8d6  test    eax, eax
0x18000d8d8  jns     short loc_18000D905
0x18000d8da  lea     rax, WPP_GLOBAL_Control
0x18000d8e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d8e8  cmp     rcx, rax
0x18000d8eb  jz      loc_18000DC69
0x18000d8f1  test    byte ptr [rcx+1Ch], 1
0x18000d8f5  jz      loc_18000DC69
0x18000d8fb  mov     edx, 73h ; 's'
0x18000d900  jmp     loc_18000D7DE
0x18000d905  mov     rdi, r14
0x18000d908  cmp     qword ptr [rdi+50h], 0
0x18000d90d  lea     r9, [rbp+57h+var_60]
0x18000d911  jz      short loc_18000D917
0x18000d913  lea     r9, [rdi+38h]
0x18000d917  movzx   r8d, word ptr [r9]
0x18000d91b  shr     r8d, 1
0x18000d91e  mov     r9, [r9+8]
0x18000d922  lea     rdx, aLs_0; "\"%.*ls\","
0x18000d929  lea     rcx, [rbp+57h+var_A0]
0x18000d92d  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18000d932  mov     ebx, eax
0x18000d934  test    eax, eax
0x18000d936  js      loc_18000DBBA
0x18000d93c  mov     rdx, [rbp+57h+var_A0]; wchar_t *
0x18000d940  lea     rcx, [rbp+57h+var_B8]; struct IWerByteStream *
0x18000d944  call    ?UtilWriteStringToByteStream@@YAJPEAUIWerByteStream@@PEB_W@Z; UtilWriteStringToByteStream(IWerByteStream *,wchar_t const *)
0x18000d949  mov     ebx, eax
0x18000d94b  test    eax, eax
0x18000d94d  js      loc_18000DB8F
0x18000d953  xor     esi, esi
0x18000d955  mov     ebx, esi
0x18000d957  add     rbx, rbx
0x18000d95a  lea     rdx, off_1800372A0; "UniqueProcessId"
0x18000d961  mov     eax, [rdx+rbx*8+0Ch]
0x18000d965  sub     eax, 4
0x18000d968  test    eax, 0FFFFFFFBh
0x18000d96d  jz      short loc_18000D97B
0x18000d96f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000d974  lea     rdx, off_1800372A0; "UniqueProcessId"
0x18000d97b  mov     r8d, [rdx+rbx*8+8]
0x18000d980  mov     rcx, [rbp+57h+var_A0]
0x18000d984  mov     [rbp+57h+var_98], rcx
0x18000d988  xor     eax, eax
0x18000d98a  mov     [rcx], ax
0x18000d98d  lea     rcx, [rbp+57h+var_A0]
0x18000d991  cmp     dword ptr [rdx+rbx*8+0Ch], 4
0x18000d996  jnz     short loc_18000D9D9
0x18000d998  mov     r8d, [r8+rdi]
0x18000d99c  lea     rdx, aLu; "%lu,"
0x18000d9a3  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18000d9a8  mov     ebx, eax
0x18000d9aa  test    eax, eax
0x18000d9ac  jns     short loc_18000D9F3
0x18000d9ae  lea     rax, WPP_GLOBAL_Control
0x18000d9b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d9bc  cmp     rcx, rax
0x18000d9bf  jz      loc_18000DC69
0x18000d9c5  test    byte ptr [rcx+1Ch], 1
0x18000d9c9  jz      loc_18000DC69
0x18000d9cf  mov     edx, 76h ; 'v'
0x18000d9d4  jmp     loc_18000D7DE
0x18000d9d9  mov     r8, [r8+rdi]
0x18000d9dd  lea     rdx, aLlu; "%llu,"
0x18000d9e4  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18000d9e9  mov     ebx, eax
0x18000d9eb  test    eax, eax
0x18000d9ed  js      loc_18000DB64
0x18000d9f3  mov     rdx, [rbp+57h+var_A0]; wchar_t *
0x18000d9f7  lea     rcx, [rbp+57h+var_B8]; struct IWerByteStream *
0x18000d9fb  call    ?UtilWriteStringToByteStream@@YAJPEAUIWerByteStream@@PEB_W@Z; UtilWriteStringToByteStream(IWerByteStream *,wchar_t const *)
0x18000da00  mov     ebx, eax
0x18000da02  test    eax, eax
0x18000da04  js      loc_18000DB39
0x18000da0a  inc     esi
0x18000da0c  cmp     esi, 1Fh
0x18000da0f  jb      loc_18000D955
0x18000da15  mov     edx, 1
0x18000da1a  xor     esi, esi
0x18000da1c  cmp     [rbp+57h+var_BC], esi
0x18000da1f  jbe     short loc_18000DA8C
0x18000da21  mov     eax, esi
0x18000da23  imul    r9, rax, 38h ; '8'
0x18000da27  mov     r10, [rbp+57h+Block]
0x18000da2b  mov     eax, [rdi+50h]
0x18000da2e  cmp     [r9+r10+2Ch], eax
0x18000da33  jnz     short loc_18000DA85
0x18000da35  mov     rcx, [rbp+57h+var_A0]
0x18000da39  mov     [rbp+57h+var_98], rcx
0x18000da3d  xor     eax, eax
0x18000da3f  mov     [rcx], ax
0x18000da42  lea     rax, asc_18003B504; "|"
0x18000da49  lea     r8, dword_180039414
0x18000da50  test    edx, edx
0x18000da52  cmovz   r8, rax
0x18000da56  mov     r9, [r9+r10]
0x18000da5a  lea     rdx, aLsLs_0; "%ls%ls"
0x18000da61  lea     rcx, [rbp+57h+var_A0]
0x18000da65  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18000da6a  mov     ebx, eax
0x18000da6c  test    eax, eax
0x18000da6e  js      short loc_18000DADC
0x18000da70  mov     rdx, [rbp+57h+var_A0]; wchar_t *
0x18000da74  lea     rcx, [rbp+57h+var_B8]; struct IWerByteStream *
0x18000da78  call    ?UtilWriteStringToByteStream@@YAJPEAUIWerByteStream@@PEB_W@Z; UtilWriteStringToByteStream(IWerByteStream *,wchar_t const *)
0x18000da7d  mov     ebx, eax
0x18000da7f  test    eax, eax
0x18000da81  js      short loc_18000DAB1
0x18000da83  xor     edx, edx
0x18000da85  inc     esi
0x18000da87  cmp     esi, [rbp+57h+var_BC]
0x18000da8a  jb      short loc_18000DA21
0x18000da8c  lea     rdx, asc_18003B518; "\r\n"
0x18000da93  lea     rcx, [rbp+57h+var_B8]; struct IWerByteStream *
0x18000da97  call    ?UtilWriteStringToByteStream@@YAJPEAUIWerByteStream@@PEB_W@Z; UtilWriteStringToByteStream(IWerByteStream *,wchar_t const *)
0x18000da9c  mov     ebx, eax
0x18000da9e  test    eax, eax
0x18000daa0  js      short loc_18000DB0E
0x18000daa2  cmp     dword ptr [rdi], 0
0x18000daa5  jz      short loc_18000DB07
0x18000daa7  mov     eax, [rdi]
0x18000daa9  add     rdi, rax
0x18000daac  jmp     loc_18000D908
0x18000dab1  lea     rax, WPP_GLOBAL_Control
0x18000dab8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dabf  cmp     rcx, rax
0x18000dac2  jz      loc_18000DC69
0x18000dac8  test    byte ptr [rcx+1Ch], 1
0x18000dacc  jz      loc_18000DC69
0x18000dad2  mov     edx, 7Ah ; 'z'
0x18000dad7  jmp     loc_18000D7DE
0x18000dadc  lea     rax, WPP_GLOBAL_Control
0x18000dae3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000daea  cmp     rcx, rax
0x18000daed  jz      loc_18000DC69
0x18000daf3  test    byte ptr [rcx+1Ch], 1
0x18000daf7  jz      loc_18000DC69
0x18000dafd  mov     edx, 79h ; 'y'
0x18000db02  jmp     loc_18000D7DE
0x18000db07  xor     ebx, ebx
0x18000db09  jmp     loc_18000DC69
0x18000db0e  lea     rax, WPP_GLOBAL_Control
0x18000db15  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db1c  cmp     rcx, rax
0x18000db1f  jz      loc_18000DC69
0x18000db25  test    byte ptr [rcx+1Ch], 1
  ... truncated ...
```
