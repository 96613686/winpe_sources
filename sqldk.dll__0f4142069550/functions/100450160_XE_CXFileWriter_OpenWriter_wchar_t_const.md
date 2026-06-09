# XE_CXFileWriter::OpenWriter(wchar_t const *)

- ea: `0x100450160`
- end: `0x100450611`
- name: `?OpenWriter@XE_CXFileWriter@@QEAAHPEB_W@Z`
- size: `1201`
- prototype: `__int64 __fastcall(XE_CXFileWriter *__hidden this, LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, installer_update`

## callers

- `0x1005d69b0`
- `0x1005d6e30`

## callees

- `0x100404bf2`
- `0x100420a4c`
- `0x10044fcf0`
- `0x10044fdf0`
- `0x100450160`
- `0x100451770`
- `0x1004518d0`
- `0x100611e90`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x1004501f9`
- `KERNEL32!CreateEventW` at `0x1004501f9`
- `KERNEL32!CreateFileW` at `0x1004503f0`
- `KERNEL32!CreateFileW` at `0x1004503f0`
- `KERNEL32!GetLastError` at `0x100450223`
- `KERNEL32!GetLastError` at `0x100450223`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall XE_CXFileWriter::OpenWriter(XE_CXFileWriter *this, char *lpFileName)
{
  __int64 v4; // rcx
  __int64 v5; // rdx
  unsigned int v6; // ebp
  HANDLE EventW; // rax
  __int64 *v8; // rbx
  __int64 v9; // rdi
  DWORD LastError; // eax
  unsigned int v11; // r9d
  __int64 v12; // rax
  _WORD *v13; // rcx
  __int64 v14; // rdx
  __int16 v15; // ax
  _WORD *v16; // rax
  unsigned int v17; // r8d
  __int64 v18; // rdx
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // r9
  HANDLE FileW; // rax
  unsigned __int64 v22; // rsi
  __int64 v23; // rax
  bool v24; // cf
  unsigned int v25; // eax
  unsigned __int64 *v26; // rax
  void *v27; // rdi
  unsigned int v28; // edi
  __int64 v29; // rcx
  __int64 v30; // rdx
  unsigned __int64 v31; // r8
  unsigned __int64 v32; // rdx
  unsigned __int64 v33; // rax
  int v35; // [rsp+50h] [rbp-438h] BYREF

  if ( *((_QWORD *)this + 73) != -1 )
  {
    v4 = *((_QWORD *)this + 105);
    v5 = 2415853575LL;
LABEL_59:
    (*(void (__fastcall **)(__int64, __int64, char *, _QWORD))(*(_QWORD *)v4 + 48LL))(v4, v5, lpFileName, 0);
    return 0;
  }
  *((_QWORD *)this + 77) = 0;
  *((_DWORD *)this + 156) = 0;
  *((_DWORD *)this + 170) = 0;
  *((_QWORD *)this + 86) = 0;
  *(_OWORD *)((char *)this + 632) = 0;
  *(_OWORD *)((char *)this + 648) = 0;
  *((_DWORD *)this + 7) = 0;
  v6 = 1;
  *((_DWORD *)this + 1) = 1;
  *((_DWORD *)this + 2) = 1;
  *(_DWORD *)this = 1112687958;
  if ( *((_QWORD *)this + 84) == -1 )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 84) = EventW;
    if ( !EventW )
    {
      *((_QWORD *)this + 84) = -1;
LABEL_6:
      v8 = (__int64 *)*((_QWORD *)this + 105);
      v9 = *v8;
      LastError = GetLastError();
      (*(void (__fastcall **)(__int64 *, _QWORD, char *, _QWORD))(v9 + 48))(v8, LastError, lpFileName, 0);
      return 0;
    }
  }
  if ( (*((_BYTE *)this + 20) & 1) == 0 && !*((_QWORD *)this + 87) )
  {
    _BitScanForward(&v11, *((_DWORD *)this + 3));
    v12 = Xpress9EncoderCreate((unsigned int)&v35, 0, (unsigned int)XpressAllocFnXE, v11, 1);
    *((_QWORD *)this + 87) = v12;
    if ( !v12 || v35 )
    {
LABEL_11:
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 105) + 8LL))(*((_QWORD *)this + 105));
      return 0;
    }
  }
  v13 = (_WORD *)((char *)this + 32);
  v14 = 260;
  do
  {
    if ( v14 == -2147483386 )
      break;
    v15 = *(_WORD *)((char *)v13 + lpFileName - ((char *)this + 32));
    if ( !v15 )
      break;
    *v13++ = v15;
    --v14;
  }
  while ( v14 );
  v16 = v13 - 1;
  if ( v14 )
    v16 = v13;
  *v16 = 0;
  if ( !v14 )
  {
    v5 = 2415853576LL;
LABEL_58:
    v4 = *((_QWORD *)this + 105);
    goto LABEL_59;
  }
  v17 = *((_DWORD *)this + 4);
  if ( !v17 )
  {
    v17 = 512;
    *((_DWORD *)this + 4) = 512;
  }
  v18 = 0xFFFFFFFF0LL;
  if ( (unsigned __int64)(*((_QWORD *)this + 83) - 1LL) <= 0xFFFFFFFEELL )
    v18 = *((_QWORD *)this + 83);
  v19 = *((unsigned int *)this + 3);
  v20 = ((v18 + 15) & 0xFFFFFFFFFFFFFFF0uLL) / v19;
  *((_DWORD *)this + 6) = v20;
  if ( *(_DWORD *)this != 1112687958
    || *((_DWORD *)this + 2) != 1
    || *((_DWORD *)this + 1) != 1
    || (v17 & 0x1FF) != 0 && v17 != 1
    || v17 > 0x20000
    || (unsigned int)v19 > 0x400000
    || (((_DWORD)v19 - 1) & (unsigned int)v19) != 0
    || (unsigned int)v19 < 0x10000
    || (*((_DWORD *)this + 5) & 0xFFFFFFF8) != 0
    || (unsigned int)v19 % v17
    || (unsigned int)v20 > (unsigned int)(0x1000000000LL / v19) )
  {
    v5 = 2415853577LL;
    goto LABEL_58;
  }
  FileW = CreateFileW((LPCWSTR)lpFileName, 0x40000000u, 3u, 0, 1u, *((_DWORD *)this + 148) | 0x40000000u, 0);
  *((_QWORD *)this + 73) = FileW;
  if ( FileW == (HANDLE)-1LL )
    goto LABEL_6;
  if ( !XE_CXFileWriter::WriteSync(this, this, 0x20u, 0) )
    return 0;
  if ( !(unsigned int)CXFile::SetupDirectory(this) )
    goto LABEL_11;
  if ( !XE_CXFileWriter::WriteSync(
          this,
          *((const void *const *)this + 69),
          *((_DWORD *)this + 143),
          *((_DWORD *)this + 142)) )
    return 0;
  v22 = *((unsigned int *)this + 152);
  v23 = 80 * v22;
  if ( !is_mul_ok(v22, 0x50u) )
    v23 = -1;
  v24 = __CFADD__(v23, 8);
  v25 = v23 + 8;
  if ( v24 )
    v25 = -1;
  v26 = (unsigned __int64 *)qword_100714F08(0, v25);
  if ( v26 )
  {
    *v26 = v22;
    v27 = v26 + 1;
    `eh vector constructor iterator'(
      v26 + 1,
      0x50u,
      (unsigned int)v22,
      (void (*)(void *))CXFilePage::CXFilePage,
      (void (*)(void *))CXFilePage::~CXFilePage);
  }
  else
  {
    v27 = 0;
  }
  *((_QWORD *)this + 75) = v27;
  if ( !v27 )
    goto LABEL_11;
  memset_0(v27, 0, 80LL * *((unsigned int *)this + 152));
  v28 = 0;
  if ( *((_DWORD *)this + 152) )
  {
    while ( CXFilePageBase::InitCachedPage(
              (CXFilePageBase *)(*((_QWORD *)this + 75) + 80LL * v28),
              *((_DWORD *)this + 3),
              *((_DWORD *)this + 4)) )
    {
      if ( ++v28 >= *((_DWORD *)this + 152) )
        goto LABEL_51;
    }
    goto LABEL_11;
  }
LABEL_51:
  *((_DWORD *)this + 153) = 0;
  v29 = *((_QWORD *)this + 72);
  v30 = *((_QWORD *)this + 75);
  **(_DWORD **)v30 = 0;
  *(_DWORD *)(*(_QWORD *)v30 + 4LL) = 0;
  *(_DWORD *)(*(_QWORD *)v30 + 12LL) = 0;
  *(_DWORD *)(*(_QWORD *)v30 + 8LL) = 0;
  *(_DWORD *)(v30 + 72) = 16;
  *(_QWORD *)(v30 + 8) = v29;
  *(_OWORD *)(v30 + 40) = 0;
  *(_OWORD *)(v30 + 56) = 0;
  *(_DWORD *)(*((_QWORD *)this + 69) + 4LL * *((unsigned int *)this + 154)) = *((_QWORD *)this + 72) >> 4;
  *((_DWORD *)this + 208) = 0;
  v31 = *((_QWORD *)this + 72);
  if ( v31 >= *((_QWORD *)this + 86) + (unsigned __int64)*((unsigned int *)this + 3) )
  {
    v32 = v31 + (unsigned int)(*((_DWORD *)this + 3) << 6);
    v33 = *((_QWORD *)this + 83);
    if ( v33 )
    {
      if ( v32 >= v33 )
        v32 = *((_QWORD *)this + 83);
    }
    *((_QWORD *)this + 86) = v32;
    return (unsigned int)XE_CXFileWriter::SetFileSize(this, v32);
  }
  return v6;
}

```

## disassembly

```asm
0x100450160  mov     rax, rsp
0x100450163  push    rsi
0x100450164  push    rdi
0x100450165  push    r14
0x100450167  sub     rsp, 470h
0x10045016e  mov     [rsp+488h+var_448], 0FFFFFFFFFFFFFFFEh
0x100450177  mov     [rax+10h], rbx
0x10045017b  mov     [rax+20h], rbp
0x10045017f  mov     rsi, rdx
0x100450182  mov     rbx, rcx
0x100450185  cmp     qword ptr [rcx+248h], 0FFFFFFFFFFFFFFFFh
0x10045018d  jz      short loc_1004501A0
0x10045018f  mov     rcx, [rcx+348h]
0x100450196  mov     edx, 8FFF0007h
0x10045019b  jmp     loc_1004505EB
0x1004501a0  xor     r14d, r14d
0x1004501a3  mov     [rcx+268h], r14
0x1004501aa  mov     [rcx+270h], r14d
0x1004501b1  mov     [rcx+2A8h], r14d
0x1004501b8  mov     [rcx+2B0h], r14
0x1004501bf  xorps   xmm0, xmm0
0x1004501c2  movups  xmmword ptr [rcx+278h], xmm0
0x1004501c9  movups  xmmword ptr [rcx+288h], xmm0
0x1004501d0  mov     [rcx+1Ch], r14d
0x1004501d4  mov     ebp, 1
0x1004501d9  mov     [rcx+4], ebp
0x1004501dc  mov     [rcx+8], ebp
0x1004501df  mov     dword ptr [rcx], 42524556h
0x1004501e5  cmp     qword ptr [rcx+2A0h], 0FFFFFFFFFFFFFFFFh
0x1004501ed  jnz     short loc_10045023D
0x1004501ef  xor     r9d, r9d; lpName
0x1004501f2  xor     r8d, r8d; bInitialState
0x1004501f5  xor     edx, edx; bManualReset
0x1004501f7  xor     ecx, ecx; lpEventAttributes
0x1004501f9  call    cs:__imp_CreateEventW
0x1004501ff  mov     [rbx+2A0h], rax
0x100450206  test    rax, rax
0x100450209  jnz     short loc_10045023D
0x10045020b  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x100450212  mov     [rbx+2A0h], rcx
0x100450219  mov     rbx, [rbx+348h]
0x100450220  mov     rdi, [rbx]
0x100450223  call    cs:__imp_GetLastError
0x100450229  mov     edx, eax
0x10045022b  movzx   r9d, r14w
0x10045022f  mov     r8, rsi
0x100450232  mov     rcx, rbx
0x100450235  call    qword ptr [rdi+30h]
0x100450238  jmp     loc_1004505F7
0x10045023d  test    [rbx+14h], bpl
0x100450241  jnz     short loc_100450295
0x100450243  cmp     [rbx+2B8h], r14
0x10045024a  jnz     short loc_100450295
0x10045024c  mov     dword ptr [rsp+488h+arg_0], r14d
0x100450254  bsf     r9d, [rbx+0Ch]
0x100450259  mov     [rsp+488h+dwCreationDisposition], ebp
0x10045025d  lea     r8, XpressAllocFnXE
0x100450264  xor     edx, edx
0x100450266  lea     rcx, [rsp+488h+var_438]
0x10045026b  call    Xpress9EncoderCreate
0x100450270  mov     [rbx+2B8h], rax
0x100450277  test    rax, rax
0x10045027a  jz      short loc_100450283
0x10045027c  cmp     [rsp+488h+var_438], r14d
0x100450281  jz      short loc_100450295
0x100450283  mov     rcx, [rbx+348h]
0x10045028a  mov     rax, [rcx]
0x10045028d  call    qword ptr [rax+8]
0x100450290  jmp     loc_1004505F7
0x100450295  lea     rcx, [rbx+20h]
0x100450299  mov     edx, 104h
0x10045029e  mov     r8, rsi
0x1004502a1  sub     r8, rcx
0x1004502a4  lea     rax, [rdx+7FFFFEFAh]
0x1004502ab  test    rax, rax
0x1004502ae  jz      short loc_1004502C6
0x1004502b0  movzx   eax, word ptr [r8+rcx]
0x1004502b5  test    ax, ax
0x1004502b8  jz      short loc_1004502C6
0x1004502ba  mov     [rcx], ax
0x1004502bd  add     rcx, 2
0x1004502c1  sub     rdx, rbp
0x1004502c4  jnz     short loc_1004502A4
0x1004502c6  lea     rax, [rcx-2]
0x1004502ca  test    rdx, rdx
0x1004502cd  cmovnz  rax, rcx
0x1004502d1  mov     [rax], r14w
0x1004502d5  jnz     short loc_1004502E1
0x1004502d7  mov     edx, 8FFF0008h
0x1004502dc  jmp     loc_1004505E4
0x1004502e1  mov     r8d, [rbx+10h]
0x1004502e5  test    r8d, r8d
0x1004502e8  jnz     short loc_1004502F4
0x1004502ea  mov     r8d, 200h
0x1004502f0  mov     [rbx+10h], r8d
0x1004502f4  mov     rdx, 0FFFFFFFF0h
0x1004502fe  mov     rcx, [rbx+298h]
0x100450305  lea     rax, [rcx-1]
0x100450309  mov     r9, 0FFFFFFFEEh
0x100450313  cmp     rax, r9
0x100450316  cmovbe  rdx, rcx
0x10045031a  mov     ecx, [rbx+0Ch]
0x10045031d  lea     rax, [rdx+0Fh]
0x100450321  and     rax, 0FFFFFFFFFFFFFFF0h
0x100450325  xor     edx, edx
0x100450327  div     rcx
0x10045032a  mov     r9, rax
0x10045032d  mov     [rbx+18h], r9d
0x100450331  cmp     dword ptr [rbx], 42524556h
0x100450337  jnz     loc_1004505DF
0x10045033d  cmp     [rbx+8], ebp
0x100450340  jnz     loc_1004505DF
0x100450346  cmp     [rbx+4], ebp
0x100450349  jnz     loc_1004505DF
0x10045034f  test    r8d, 1FFh
0x100450356  jz      short loc_100450361
0x100450358  cmp     r8d, ebp
0x10045035b  jnz     loc_1004505DF
0x100450361  cmp     r8d, 20000h
0x100450368  ja      loc_1004505DF
0x10045036e  cmp     ecx, 400000h
0x100450374  ja      loc_1004505DF
0x10045037a  lea     eax, [rcx-1]
0x10045037d  test    ecx, eax
0x10045037f  jnz     loc_1004505DF
0x100450385  cmp     ecx, 10000h
0x10045038b  jb      loc_1004505DF
0x100450391  test    dword ptr [rbx+14h], 0FFFFFFF8h
0x100450398  jnz     loc_1004505DF
0x10045039e  test    r8d, r8d
0x1004503a1  jz      short loc_1004503B2
0x1004503a3  xor     edx, edx
0x1004503a5  mov     eax, ecx
0x1004503a7  div     r8d
0x1004503aa  test    edx, edx
0x1004503ac  jnz     loc_1004505DF
0x1004503b2  xor     edx, edx
0x1004503b4  mov     rax, 1000000000h
0x1004503be  div     rcx
0x1004503c1  cmp     r9d, eax
0x1004503c4  ja      loc_1004505DF
0x1004503ca  mov     eax, [rbx+250h]
0x1004503d0  bts     eax, 1Eh
0x1004503d4  mov     [rsp+488h+hTemplateFile], r14; hTemplateFile
0x1004503d9  mov     [rsp+488h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x1004503dd  mov     [rsp+488h+dwCreationDisposition], ebp; dwCreationDisposition
0x1004503e1  xor     r9d, r9d; lpSecurityAttributes
0x1004503e4  mov     edx, 40000000h; dwDesiredAccess
0x1004503e9  lea     r8d, [r9+3]; dwShareMode
0x1004503ed  mov     rcx, rsi; lpFileName
0x1004503f0  call    cs:__imp_CreateFileW
0x1004503f6  mov     [rbx+248h], rax
0x1004503fd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x100450401  jz      loc_100450219
0x100450407  xor     r9d, r9d; unsigned int
0x10045040a  lea     r8d, [r9+20h]; unsigned int
0x10045040e  mov     rdx, rbx; void *
0x100450411  mov     rcx, rbx; this
0x100450414  call    ?WriteSync@XE_CXFileWriter@@AEAAHQEBXKK@Z; XE_CXFileWriter::WriteSync(void const * const,ulong,ulong)
0x100450419  test    eax, eax
0x10045041b  jz      loc_1004505F7
0x100450421  mov     rcx, rbx; this
0x100450424  call    ?SetupDirectory@CXFile@@QEAAHXZ; CXFile::SetupDirectory(void)
0x100450429  test    eax, eax
0x10045042b  jz      loc_100450283
0x100450431  mov     r9d, [rbx+238h]; unsigned int
0x100450438  mov     r8d, [rbx+23Ch]; unsigned int
0x10045043f  mov     rdx, [rbx+228h]; void *
0x100450446  mov     rcx, rbx; this
0x100450449  call    ?WriteSync@XE_CXFileWriter@@AEAAHQEBXKK@Z; XE_CXFileWriter::WriteSync(void const * const,ulong,ulong)
0x10045044e  test    eax, eax
0x100450450  jz      loc_1004505F7
0x100450456  mov     esi, [rbx+260h]
0x10045045c  lea     rax, ?sm_ServiceAPI@XE_API@@2UXEEngineServicesAPI@@A; XEEngineServicesAPI XE_API::sm_ServiceAPI
0x100450463  mov     [rsp+488h+arg_0], rax
0x10045046b  mov     eax, 50h ; 'P'
0x100450470  mul     rsi
0x100450473  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10045047a  cmovo   rax, rcx
0x10045047e  add     rax, 8
0x100450482  cmovb   rax, rcx
0x100450486  mov     edx, eax
0x100450488  xor     ecx, ecx
0x10045048a  call    cs:qword_100714F08
0x100450490  mov     [rsp+488h+arg_10], rax
0x100450498  test    rax, rax
0x10045049b  jz      short loc_1004504C9
0x10045049d  mov     [rax], rsi
0x1004504a0  lea     rdi, [rax+8]
0x1004504a4  lea     rax, ??1CXFilePage@@QEAA@XZ; CXFilePage::~CXFilePage(void)
0x1004504ab  mov     qword ptr [rsp+488h+dwCreationDisposition], rax; void (*)(void *)
0x1004504b0  lea     r9, ??0CXFilePage@@QEAA@XZ; void (*)(void *)
0x1004504b7  mov     r8d, esi; unsigned __int64
0x1004504ba  mov     edx, 50h ; 'P'; unsigned __int64
0x1004504bf  mov     rcx, rdi; void *
0x1004504c2  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1004504c7  jmp     short loc_1004504CC
0x1004504c9  mov     rdi, r14
0x1004504cc  mov     [rbx+258h], rdi
0x1004504d3  test    rdi, rdi
0x1004504d6  jz      loc_100450283
0x1004504dc  mov     eax, [rbx+260h]
0x1004504e2  lea     r8, [rax+rax*4]
0x1004504e6  shl     r8, 4; Size
0x1004504ea  xor     edx, edx; Val
0x1004504ec  mov     rcx, rdi; void *
0x1004504ef  call    memset_0
0x1004504f4  mov     edi, r14d
0x1004504f7  cmp     [rbx+260h], r14d
0x1004504fe  jbe     short loc_10045052F
0x100450500  mov     eax, edi
0x100450502  lea     rcx, [rax+rax*4]
0x100450506  shl     rcx, 4
0x10045050a  add     rcx, [rbx+258h]; this
0x100450511  mov     r8d, [rbx+10h]; unsigned int
0x100450515  mov     edx, [rbx+0Ch]; unsigned int
0x100450518  call    ?InitCachedPage@CXFilePageBase@@QEAAHII@Z; CXFilePageBase::InitCachedPage(uint,uint)
0x10045051d  test    eax, eax
0x10045051f  jz      loc_100450283
0x100450525  inc     edi
0x100450527  cmp     edi, [rbx+260h]
0x10045052d  jb      short loc_100450500
0x10045052f  mov     [rbx+264h], r14d
0x100450536  mov     rcx, [rbx+240h]
0x10045053d  mov     rdx, [rbx+258h]
0x100450544  mov     rax, [rdx]
0x100450547  mov     [rax], r14d
0x10045054a  mov     rax, [rdx]
0x10045054d  mov     [rax+4], r14d
0x100450551  mov     rax, [rdx]
0x100450554  mov     [rax+0Ch], r14d
0x100450558  mov     rax, [rdx]
0x10045055b  mov     [rax+8], r14d
0x10045055f  mov     dword ptr [rdx+48h], 10h
0x100450566  mov     [rdx+8], rcx
0x10045056a  xorps   xmm0, xmm0
0x10045056d  movups  xmmword ptr [rdx+28h], xmm0
0x100450571  movups  xmmword ptr [rdx+38h], xmm0
0x100450575  mov     rdx, [rbx+240h]
0x10045057c  shr     rdx, 4
0x100450580  mov     ecx, [rbx+268h]
0x100450586  mov     rax, [rbx+228h]
0x10045058d  mov     [rax+rcx*4], edx
0x100450590  mov     [rbx+340h], r14d
0x100450597  mov     ecx, [rbx+0Ch]
0x10045059a  mov     r8, [rbx+240h]
0x1004505a1  mov     eax, ecx
0x1004505a3  add     rax, [rbx+2B0h]
0x1004505aa  cmp     r8, rax
0x1004505ad  jb      short loc_1004505DB
0x1004505af  shl     ecx, 6
0x1004505b2  mov     edx, ecx
0x1004505b4  add     rdx, r8
0x1004505b7  mov     rax, [rbx+298h]
0x1004505be  test    rax, rax
0x1004505c1  jz      short loc_1004505CA
0x1004505c3  cmp     rdx, rax
0x1004505c6  cmovnb  rdx, rax; unsigned __int64
0x1004505ca  mov     [rbx+2B0h], rdx
0x1004505d1  mov     rcx, rbx; this
0x1004505d4  call    ?SetFileSize@XE_CXFileWriter@@AEAAH_K@Z; XE_CXFileWriter::SetFileSize(unsigned __int64)
0x1004505d9  mov     ebp, eax
0x1004505db  mov     eax, ebp
0x1004505dd  jmp     short loc_1004505F9
0x1004505df  mov     edx, 8FFF0009h
0x1004505e4  mov     rcx, [rbx+348h]
0x1004505eb  mov     rax, [rcx]
0x1004505ee  xor     r9d, r9d
0x1004505f1  mov     r8, rsi
0x1004505f4  call    qword ptr [rax+30h]
0x1004505f7  xor     eax, eax
0x1004505f9  lea     r11, [rsp+488h+var_18]
0x100450601  mov     rbx, [r11+28h]
0x100450605  mov     rbp, [r11+38h]
0x100450609  mov     rsp, r11
0x10045060c  pop     r14
0x10045060e  pop     rdi
0x10045060f  pop     rsi
0x100450610  retn
```
