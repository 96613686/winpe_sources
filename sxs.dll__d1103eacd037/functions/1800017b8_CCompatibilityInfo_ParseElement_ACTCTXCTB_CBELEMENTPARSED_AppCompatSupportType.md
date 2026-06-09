# CCompatibilityInfo::ParseElement(_ACTCTXCTB_CBELEMENTPARSED *,AppCompatSupportType)

- ea: `0x1800017b8`
- end: `0x180001b4c`
- name: `?ParseElement@CCompatibilityInfo@@AEAAHPEAU_ACTCTXCTB_CBELEMENTPARSED@@W4AppCompatSupportType@@@Z`
- size: `916`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800011f0`

## callees

- `0x1800017b8`
- `0x180001d4c`
- `0x180002540`
- `0x1800075a0`
- `0x18000df40`
- `0x18000dffc`
- `0x18001c270`
- `0x180020820`
- `0x180027160`
- `0x180058578`
- `0x18005d2b0`
- `0x18006a110`

## import_xrefs

- `ntdll!_wcsicmp` at `0x1800019d2`
- `ntdll!_wcsicmp` at `0x1800019d2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001880`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800018e4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800018fb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001a04`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001a12`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001a2c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001a7f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001ac9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001880`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800018e4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800018fb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001a04`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001a12`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001a2c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001a7f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001ac9`

## pseudocode

```c
__int64 __fastcall CCompatibilityInfo::ParseElement(CCompatibilityInfo *a1, __int64 a2, int a3)
{
  int v6; // edi
  int v7; // eax
  const char *v8; // rcx
  int v9; // ebx
  char **v10; // rcx
  wchar_t *v11; // rsi
  unsigned int i; // ebx
  __int64 v13; // rdi
  unsigned int v14; // ebx
  _BYTE v16[4]; // [rsp+60h] [rbp-A0h] BYREF
  int v17; // [rsp+64h] [rbp-9Ch] BYREF
  int v18; // [rsp+68h] [rbp-98h] BYREF
  __int64 v19; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v20; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v21[32]; // [rsp+80h] [rbp-80h] BYREF
  int v22; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v23; // [rsp+A8h] [rbp-58h]
  __int64 *v24; // [rsp+B0h] [rbp-50h]
  __int64 v25; // [rsp+B8h] [rbp-48h]
  int v26; // [rsp+C0h] [rbp-40h]
  unsigned int *v27; // [rsp+C8h] [rbp-38h]
  int v28; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v29; // [rsp+D8h] [rbp-28h]
  __int64 *v30; // [rsp+E0h] [rbp-20h]
  __int64 v31; // [rsp+E8h] [rbp-18h]
  int v32; // [rsp+F0h] [rbp-10h]
  int *v33; // [rsp+F8h] [rbp-8h]
  _QWORD v34[2]; // [rsp+100h] [rbp+0h] BYREF
  wchar_t *String1; // [rsp+110h] [rbp+10h]
  __int64 v36; // [rsp+118h] [rbp+18h]
  unsigned __int64 v37; // [rsp+120h] [rbp+20h]
  char v38; // [rsp+128h] [rbp+28h] BYREF

  v25 = 544438355;
  v18 = 0;
  v24 = &qword_18006C100;
  v23 = 0;
  v26 = 445;
  v22 = 1;
  v27 = (unsigned int *)&v18;
  CFrame::BaseEnter((CFrame *)&v22);
  CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(v34);
  v20 = 0;
  v19 = 0;
  memset(v21, 0, sizeof(v21));
  if ( a3 )
  {
    v6 = 2;
    if ( a3 == 1 )
    {
      *(_DWORD *)&v21[16] = 2;
    }
    else
    {
      v7 = 0;
      if ( a3 == 2 )
        v7 = 3;
      v6 = v7;
      *(_DWORD *)&v21[16] = v7;
    }
  }
  else
  {
    v6 = 1;
    *(_DWORD *)&v21[16] = 1;
  }
  SetLastError(0);
  v17 = 0;
  v30 = &qword_18006D2E0;
  v28 = 1;
  v33 = &v17;
  v29 = 0;
  v31 = 544438355;
  v32 = 2077;
  CFrame::BaseEnter((CFrame *)&v28);
  v16[0] = 0;
  v19 = 0;
  if ( a2 )
  {
    SetLastError(0);
    if ( (unsigned int)SxspGetAttributeValue(
                         0,
                         (WCHAR **)qword_18006C0E0,
                         *(_QWORD *)(a2 + 104),
                         *(unsigned int *)(a2 + 96),
                         *(_QWORD *)(a2 + 88),
                         v16,
                         168,
                         (__int64)v34,
                         &v19,
                         0) )
    {
      v17 = 1;
    }
    else
    {
      *v33 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_1800756B0);
    }
  }
  else
  {
    v32 = 2083;
    FusionpTraceParameterCheck(v8);
    SetLastError(0x57u);
    *v33 = 0;
  }
  v9 = v17;
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v28);
  if ( !v9 )
  {
    v10 = off_18007A9F0;
LABEL_15:
    *v27 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v10);
    goto LABEL_36;
  }
  if ( v16[0] )
  {
    if ( v6 == 1 )
    {
      v11 = String1;
      if ( String1 )
      {
        for ( i = 0; i < 5; ++i )
        {
          v13 = 4LL * i;
          if ( !_wcsicmp(v11, (const wchar_t *)SbSupportedOsList[v13 + 3]) )
          {
            *(_OWORD *)v21 = *(_OWORD *)((char *)&SbSupportedOsList[v13] + 4);
            goto LABEL_24;
          }
        }
      }
      SetLastError(0);
      if ( !(unsigned int)SxspParseGUID(String1, v37, (struct _GUID *)v21) )
      {
        v10 = off_18007A9D0;
        goto LABEL_15;
      }
    }
    else if ( v6 == 3 )
    {
      if ( (unsigned int)VersionToQword(String1, &v20) )
        *(_QWORD *)&v21[24] = v20;
    }
    else
    {
      SetLastError(0);
      if ( !(unsigned int)SxspParseGUID(String1, v37, (struct _GUID *)v21) )
      {
        v10 = off_18007A9B0;
        goto LABEL_15;
      }
    }
LABEL_24:
    if ( *(_DWORD *)(a2 + 4) != 1 )
    {
      SetLastError(0);
LABEL_26:
      SetLastError(0);
      *v27 = 1;
      goto LABEL_36;
    }
    if ( (unsigned int)CCompatibilityInfo::Append(a1, (const struct _COMPATIBILITY_CONTEXT_ELEMENT *)v21) )
      goto LABEL_26;
  }
  SetLastError(0x54Fu);
  *v27 = 0;
LABEL_36:
  v14 = *v27;
  v34[0] = &CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable';
  if ( String1 != (wchar_t *)&v38 )
    CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(v34);
  String1 = 0;
  v34[0] = &CGenericBaseStringBuffer<CUnicodeCharTraits>::`vftable';
  v36 = 0;
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v22);
  return v14;
}

```

## disassembly

```asm
0x1800017b8  mov     [rsp-8+arg_10], rbx
0x1800017bd  push    rbp
0x1800017be  push    rsi
0x1800017bf  push    rdi
0x1800017c0  push    r12
0x1800017c2  push    r13
0x1800017c4  push    r14
0x1800017c6  push    r15
0x1800017c8  lea     rbp, [rsp-0C0h]
0x1800017d0  sub     rsp, 1C0h
0x1800017d7  mov     rax, cs:__security_cookie
0x1800017de  xor     rax, rsp
0x1800017e1  mov     [rbp+0F0h+var_40], rax
0x1800017e8  xor     r12d, r12d
0x1800017eb  mov     [rbp+0F0h+var_138], 20737853h
0x1800017f3  lea     rax, qword_18006C100
0x1800017fa  mov     [rsp+1F0h+var_188], r12d
0x1800017ff  mov     [rbp+0F0h+var_140], rax
0x180001803  mov     r15, rcx
0x180001806  lea     rax, [rsp+1F0h+var_188]
0x18000180b  mov     [rbp+0F0h+var_148], r12
0x18000180f  lea     r13d, [r12+1]
0x180001814  mov     [rbp+0F0h+var_130], 1BDh
0x18000181b  lea     rcx, [rbp+0F0h+var_150]; this
0x18000181f  mov     [rbp+0F0h+var_150], r13d
0x180001823  mov     ebx, r8d
0x180001826  mov     [rbp+0F0h+var_128], rax
0x18000182a  mov     r14, rdx
0x18000182d  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180001832  lea     rcx, [rbp+0F0h+var_F0]
0x180001836  call    ??0?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(void)
0x18000183b  mov     [rsp+1F0h+var_178], r12
0x180001840  xorps   xmm0, xmm0
0x180001843  mov     [rsp+1F0h+var_180], r12
0x180001848  lea     esi, [r12+3]
0x18000184d  movups  xmmword ptr [rbp+0F0h+var_170], xmm0
0x180001851  movups  xmmword ptr [rbp+0F0h+var_170+10h], xmm0
0x180001855  test    ebx, ebx
0x180001857  jnz     short loc_180001862
0x180001859  mov     edi, r13d
0x18000185c  mov     dword ptr [rbp+0F0h+var_170+10h], r13d
0x180001860  jmp     short loc_18000187E
0x180001862  mov     edi, 2
0x180001867  cmp     ebx, r13d
0x18000186a  jnz     short loc_180001871
0x18000186c  mov     dword ptr [rbp+0F0h+var_170+10h], edi
0x18000186f  jmp     short loc_18000187E
0x180001871  cmp     ebx, edi
0x180001873  mov     eax, r12d
0x180001876  cmovz   eax, esi
0x180001879  mov     edi, eax
0x18000187b  mov     dword ptr [rbp+0F0h+var_170+10h], eax
0x18000187e  xor     ecx, ecx; dwErrCode
0x180001880  call    cs:__imp_SetLastError
0x180001887  nop     dword ptr [rax+rax+00h]
0x18000188c  lea     rax, qword_18006D2E0
0x180001893  mov     [rsp+1F0h+var_18C], r12d
0x180001898  mov     [rbp+0F0h+var_110], rax
0x18000189c  lea     rcx, [rbp+0F0h+var_120]; this
0x1800018a0  lea     rax, [rsp+1F0h+var_18C]
0x1800018a5  mov     [rbp+0F0h+var_120], r13d
0x1800018a9  mov     [rbp+0F0h+var_F8], rax
0x1800018ad  mov     [rbp+0F0h+var_118], r12
0x1800018b1  mov     [rbp+0F0h+var_108], 20737853h
0x1800018b9  mov     [rbp+0F0h+var_100], 81Dh
0x1800018c0  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x1800018c5  mov     [rsp+1F0h+var_190], r12b
0x1800018ca  mov     [rsp+1F0h+var_180], r12
0x1800018cf  test    r14, r14
0x1800018d2  jnz     short loc_1800018F9
0x1800018d4  mov     [rbp+0F0h+var_100], 823h
0x1800018db  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x1800018e0  lea     ecx, [r14+57h]; dwErrCode
0x1800018e4  call    cs:__imp_SetLastError
0x1800018eb  nop     dword ptr [rax+rax+00h]
0x1800018f0  mov     rax, [rbp+0F0h+var_F8]
0x1800018f4  mov     [rax], r12d
0x1800018f7  jmp     short loc_18000196F
0x1800018f9  xor     ecx, ecx; dwErrCode
0x1800018fb  call    cs:__imp_SetLastError
0x180001902  nop     dword ptr [rax+rax+00h]
0x180001907  mov     r9d, [r14+60h]
0x18000190b  lea     rax, [rsp+1F0h+var_180]
0x180001910  mov     r8, [r14+68h]
0x180001914  lea     rdx, qword_18006C0E0
0x18000191b  mov     [rsp+1F0h+var_1A8], r12
0x180001920  xor     ecx, ecx
0x180001922  mov     [rsp+1F0h+var_1B0], rax
0x180001927  lea     rax, [rbp+0F0h+var_F0]
0x18000192b  mov     [rsp+1F0h+var_1B8], rax
0x180001930  lea     rax, [rsp+1F0h+var_190]
0x180001935  mov     [rsp+1F0h+var_1C0], 0A8h
0x18000193e  mov     [rsp+1F0h+var_1C8], rax
0x180001943  mov     rax, [r14+58h]
0x180001947  mov     [rsp+1F0h+var_1D0], rax
0x18000194c  call    ?SxspGetAttributeValue@@YAHKPEBU_ATTRIBUTE_NAME_DESCRIPTOR@@PEBU_SXS_NODE_INFO@@_KPEBU_ACTCTXCTB_PARSE_CONTEXT@@AEA_N2PEAXAEA_KP6AHKAEBV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@4256@ZK@Z; SxspGetAttributeValue(ulong,_ATTRIBUTE_NAME_DESCRIPTOR const *,_SXS_NODE_INFO const *,unsigned __int64,_ACTCTXCTB_PARSE_CONTEXT const *,bool &,unsigned __int64,void *,unsigned __int64 &,int (*)(ulong,CGenericBaseStringBuffer<CUnicodeCharTraits> const &,bool &,unsigned __int64,void *,unsigned __int64 &),ulong)
0x180001951  test    eax, eax
0x180001953  jnz     short loc_18000196A
0x180001955  mov     rax, [rbp+0F0h+var_F8]
0x180001959  lea     rcx, off_1800756B0; struct _CALL_SITE_INFO *
0x180001960  mov     [rax], r12d
0x180001963  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x180001968  jmp     short loc_18000196F
0x18000196a  mov     [rsp+1F0h+var_18C], r13d
0x18000196f  mov     ebx, [rsp+1F0h+var_18C]
0x180001973  lea     rcx, [rbp+0F0h+var_120]; this
0x180001977  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x18000197c  test    ebx, ebx
0x18000197e  jnz     short loc_180001998
0x180001980  lea     rcx, off_18007A9F0; struct _CALL_SITE_INFO *
0x180001987  mov     rax, [rbp+0F0h+var_128]
0x18000198b  mov     [rax], r12d
0x18000198e  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x180001993  jmp     loc_180001ADC
0x180001998  cmp     [rsp+1F0h+var_190], r12b
0x18000199d  jz      loc_180001AC4
0x1800019a3  cmp     edi, r13d
0x1800019a6  jnz     loc_180001A59
0x1800019ac  mov     rsi, [rbp+0F0h+String1]
0x1800019b0  test    rsi, rsi
0x1800019b3  jz      short loc_180001A2A
0x1800019b5  mov     ebx, r12d
0x1800019b8  lea     rax, SbSupportedOsList
0x1800019bf  cmp     ebx, 5
0x1800019c2  jnb     short loc_180001A2A
0x1800019c4  mov     edi, ebx
0x1800019c6  mov     rcx, rsi; String1
0x1800019c9  shl     rdi, 5
0x1800019cd  mov     rdx, [rdi+rax+18h]; String2
0x1800019d2  call    cs:__imp__wcsicmp
0x1800019d9  nop     dword ptr [rax+rax+00h]
0x1800019de  test    eax, eax
0x1800019e0  lea     rax, SbSupportedOsList
0x1800019e7  jz      short loc_1800019EE
0x1800019e9  add     ebx, r13d
0x1800019ec  jmp     short loc_1800019BF
0x1800019ee  movups  xmm0, xmmword ptr [rdi+rax+4]
0x1800019f3  movdqu  xmmword ptr [rbp+0F0h+var_170], xmm0
0x1800019f8  cmp     [r14+4], r13d
0x1800019fc  jz      loc_180001AB0
0x180001a02  xor     ecx, ecx; dwErrCode
0x180001a04  call    cs:__imp_SetLastError
0x180001a0b  nop     dword ptr [rax+rax+00h]
0x180001a10  xor     ecx, ecx; dwErrCode
0x180001a12  call    cs:__imp_SetLastError
0x180001a19  nop     dword ptr [rax+rax+00h]
0x180001a1e  mov     rax, [rbp+0F0h+var_128]
0x180001a22  mov     [rax], r13d
0x180001a25  jmp     loc_180001ADC
0x180001a2a  xor     ecx, ecx; dwErrCode
0x180001a2c  call    cs:__imp_SetLastError
0x180001a33  nop     dword ptr [rax+rax+00h]
0x180001a38  mov     rdx, [rbp+0F0h+var_D0]; unsigned __int64
0x180001a3c  lea     r8, [rbp+0F0h+var_170]; struct _GUID *
0x180001a40  mov     rcx, [rbp+0F0h+String1]; unsigned __int16 *
0x180001a44  call    ?SxspParseGUID@@YAHPEBG_KAEAU_GUID@@@Z; SxspParseGUID(ushort const *,unsigned __int64,_GUID &)
0x180001a49  test    eax, eax
0x180001a4b  jnz     short loc_1800019F8
0x180001a4d  lea     rcx, off_18007A9D0; "clientcore\\base\\win32\\fusion\\sxs\\c"...
0x180001a54  jmp     loc_180001987
0x180001a59  cmp     edi, esi
0x180001a5b  jnz     short loc_180001A7D
0x180001a5d  mov     rcx, [rbp+0F0h+String1]; String
0x180001a61  lea     rdx, [rsp+1F0h+var_178]; unsigned __int64 *
0x180001a66  call    ?VersionToQword@@YAHPEBGPEA_K@Z; VersionToQword(ushort const *,unsigned __int64 *)
0x180001a6b  test    eax, eax
0x180001a6d  jz      short loc_1800019F8
0x180001a6f  mov     rax, [rsp+1F0h+var_178]
0x180001a74  mov     qword ptr [rbp+0F0h+var_170+18h], rax
0x180001a78  jmp     loc_1800019F8
0x180001a7d  xor     ecx, ecx; dwErrCode
0x180001a7f  call    cs:__imp_SetLastError
0x180001a86  nop     dword ptr [rax+rax+00h]
0x180001a8b  mov     rdx, [rbp+0F0h+var_D0]; unsigned __int64
0x180001a8f  lea     r8, [rbp+0F0h+var_170]; struct _GUID *
0x180001a93  mov     rcx, [rbp+0F0h+String1]; unsigned __int16 *
0x180001a97  call    ?SxspParseGUID@@YAHPEBG_KAEAU_GUID@@@Z; SxspParseGUID(ushort const *,unsigned __int64,_GUID &)
0x180001a9c  test    eax, eax
0x180001a9e  jnz     loc_1800019F8
0x180001aa4  lea     rcx, off_18007A9B0; "clientcore\\base\\win32\\fusion\\sxs\\c"...
0x180001aab  jmp     loc_180001987
0x180001ab0  lea     rdx, [rbp+0F0h+var_170]; struct _COMPATIBILITY_CONTEXT_ELEMENT *
0x180001ab4  mov     rcx, r15; this
0x180001ab7  call    ?Append@CCompatibilityInfo@@AEAAHPEBU_COMPATIBILITY_CONTEXT_ELEMENT@@@Z; CCompatibilityInfo::Append(_COMPATIBILITY_CONTEXT_ELEMENT const *)
0x180001abc  test    eax, eax
0x180001abe  jnz     loc_180001A10
0x180001ac4  mov     ecx, 54Fh; dwErrCode
0x180001ac9  call    cs:__imp_SetLastError
0x180001ad0  nop     dword ptr [rax+rax+00h]
0x180001ad5  mov     rax, [rbp+0F0h+var_128]
0x180001ad9  mov     [rax], r12d
0x180001adc  mov     rax, [rbp+0F0h+var_128]
0x180001ae0  mov     rdx, [rbp+0F0h+String1]
0x180001ae4  mov     ebx, [rax]
0x180001ae6  lea     rax, ??_7?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@6B@; const CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable'
0x180001aed  mov     [rbp+0F0h+var_F0], rax
0x180001af1  lea     rax, [rbp+0F0h+var_C8]
0x180001af5  cmp     rdx, rax
0x180001af8  jz      short loc_180001B03
0x180001afa  lea     rcx, [rbp+0F0h+var_F0]
0x180001afe  call    ?DeallocateBuffer@?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@MEBAXPEAG@Z; CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(ushort *)
0x180001b03  lea     rax, ??_7?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@6B@; const CGenericBaseStringBuffer<CUnicodeCharTraits>::`vftable'
0x180001b0a  mov     [rbp+0F0h+String1], r12
0x180001b0e  lea     rcx, [rbp+0F0h+var_150]; this
0x180001b12  mov     [rbp+0F0h+var_F0], rax
0x180001b16  mov     [rbp+0F0h+var_D8], r12
0x180001b1a  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x180001b1f  mov     eax, ebx
0x180001b21  mov     rcx, [rbp+0F0h+var_40]
0x180001b28  xor     rcx, rsp; StackCookie
0x180001b2b  call    __security_check_cookie
0x180001b30  mov     rbx, [rsp+1F0h+arg_10]
0x180001b38  add     rsp, 1C0h
0x180001b3f  pop     r15
0x180001b41  pop     r14
0x180001b43  pop     r13
0x180001b45  pop     r12
0x180001b47  pop     rdi
0x180001b48  pop     rsi
0x180001b49  pop     rbp
0x180001b4a  retn
```
