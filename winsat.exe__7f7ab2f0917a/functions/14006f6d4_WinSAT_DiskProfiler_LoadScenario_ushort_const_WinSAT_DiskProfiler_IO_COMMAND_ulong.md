# WinSAT::DiskProfiler::LoadScenario(ushort const *,WinSAT::DiskProfiler::_IO_COMMAND * *,ulong *)

- ea: `0x14006f6d4`
- end: `0x14006fad2`
- name: `?LoadScenario@DiskProfiler@WinSAT@@AEBAKPEBGPEAPEAU_IO_COMMAND@12@PEAK@Z`
- size: `1022`
- prototype: `int __fastcall(WinSAT::DiskProfiler *this, WinSAT *, struct WinSAT::DiskProfiler::_IO_COMMAND **, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14006ad94`

## callees

- `0x140001abc`
- `0x140003164`
- `0x140004348`
- `0x140008178`
- `0x1400085b4`
- `0x140017af0`
- `0x14006f54c`
- `0x14006f6d4`
- `0x14006fb18`
- `0x14006fb8c`
- `0x14006fc08`

## import_xrefs

- `KERNEL32!lstrcmpiA` at `0x14006f9b4`
- `KERNEL32!lstrcmpiA` at `0x14006f9cd`
- `KERNEL32!lstrcmpiA` at `0x14006f9e7`
- `KERNEL32!lstrcmpiA` at `0x14006f9b4`
- `KERNEL32!lstrcmpiA` at `0x14006f9cd`
- `KERNEL32!lstrcmpiA` at `0x14006f9e7`

## string_xrefs

- `0x14006f9aa`: `IoRead`
- `0x14006f9c3`: `IoWrite`
- `0x14006f7e0`: `[IoRead | IoWrite | IoFlush ],Offset,Size,SleepUs,MaximumQueueDepth`

## pseudocode

```c
int __fastcall WinSAT::DiskProfiler::LoadScenario(
        WinSAT::DiskProfiler *this,
        WinSAT *a2,
        struct WinSAT::DiskProfiler::_IO_COMMAND **a3,
        unsigned int *a4)
{
  unsigned int *v5; // r12
  int result; // eax
  _BYTE *v7; // r14
  unsigned int v8; // esi
  _BYTE *v9; // rax
  char *v10; // rcx
  _BYTE *i; // rdx
  char v12; // r8
  int v13; // ebx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  unsigned __int64 v31; // rax
  struct WinSAT::DiskProfiler::_IO_COMMAND *v32; // rax
  bool v33; // r8
  _BYTE *v34; // rdi
  _DWORD *v35; // r15
  _BYTE *v36; // rcx
  char v37; // al
  char **v38; // rdx
  bool v39; // r8
  const CHAR *v40; // r12
  char **v41; // rdx
  bool v42; // r8
  char **v43; // rdx
  bool v44; // r8
  char **v45; // rdx
  bool v46; // r8
  unsigned __int64 *v47; // r8
  unsigned int *v48; // r8
  unsigned __int64 *v49; // r8
  unsigned int *v50; // r8
  unsigned int v51; // r11d
  __int64 v52; // rcx
  int v53; // eax
  void *Block; // [rsp+20h] [rbp-30h] BYREF
  char v55[8]; // [rsp+28h] [rbp-28h] BYREF
  char v56[8]; // [rsp+30h] [rbp-20h] BYREF
  WinSAT *v57; // [rsp+38h] [rbp-18h] BYREF
  WinSAT *v58; // [rsp+40h] [rbp-10h]
  WinSAT *v59; // [rsp+48h] [rbp-8h]
  int v60; // [rsp+90h] [rbp+40h] BYREF
  int v61; // [rsp+94h] [rbp+44h]
  int v62; // [rsp+A0h] [rbp+50h] BYREF
  unsigned int *v63; // [rsp+A8h] [rbp+58h]

  v63 = a4;
  v61 = HIDWORD(this);
  *a4 = 0;
  *a3 = 0;
  Block = 0;
  v5 = a4;
  v57 = 0;
  *(_QWORD *)v55 = 0;
  v60 = 0;
  *(_QWORD *)v56 = 0;
  v62 = 0;
  result = WinSAT::LoadFile(a2, (const unsigned __int16 *)&Block, (char **)&v57, (unsigned __int64 *)a4);
  if ( result )
    return result;
  v7 = Block;
  v8 = 0;
  v9 = Block;
  v10 = (char *)Block;
  for ( i = Block; ; i = v9 )
  {
    v12 = *v9;
    if ( !*v9 )
      break;
    if ( v12 == 10 )
    {
      ++v8;
LABEL_6:
      v9 = v10 + 1;
      goto LABEL_7;
    }
    if ( v12 != 13 )
      goto LABEL_6;
    if ( i[1] != 10 )
      goto LABEL_11;
    ++v8;
    v9 = v10 + 2;
LABEL_7:
    v10 = v9;
  }
  if ( !v8 )
  {
LABEL_11:
    v13 = 11;
    goto LABEL_12;
  }
  v31 = 40LL * v8;
  if ( !is_mul_ok(v8, 0x28u) )
    v31 = -1;
  v32 = (struct WinSAT::DiskProfiler::_IO_COMMAND *)operator new[](v31, (const struct std::nothrow_t *)std::nothrow);
  *a3 = v32;
  if ( !v32 )
  {
    v13 = 14;
LABEL_12:
    v14 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&mlib::stdoutw);
    v15 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
            v14 + 240,
            L"There was an error in the scenario file on line: ");
    v16 = std::basic_ostream<unsigned short>::operator<<(v15, v8 + 1);
    v17 = std::endl(v16);
    std::endl(v17);
    v18 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&mlib::stdoutw);
    v19 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v18 + 240, L"The format of each line is:");
    std::endl(v19);
    v20 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&mlib::stdoutw);
    v21 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
            v20 + 240,
            L"[IoRead | IoWrite | IoFlush ],Offset,Size,SleepUs,MaximumQueueDepth");
    v22 = std::endl(v21);
    std::endl(v22);
    v23 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&mlib::stdoutw);
    v24 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v23 + 240, L"Check the follwing as well ");
    std::endl(v24);
    v25 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&mlib::stdoutw);
    v26 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
            v25 + 240,
            L"    Flushes should have 0 offset and 0 size");
    std::endl(v26);
    v27 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&mlib::stdoutw);
    v28 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
            v27 + 240,
            L"    All numbers are in Hex.  e.g. 0x1 ");
    std::endl(v28);
    v29 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&mlib::stdoutw);
    v30 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
            v29 + 240,
            L"    The file should end in an empty line.");
    std::endl(v30);
    if ( *a3 )
    {
      operator delete(*a3);
      *a3 = 0;
    }
    goto LABEL_50;
  }
  *v5 = v8;
  v34 = v7;
  v35 = *a3;
  v8 = 0;
  v13 = 11;
  Block = v7;
  v36 = v7;
  while ( *v34 )
  {
    if ( v8 >= *v5 )
      goto LABEL_12;
    v37 = *v36;
    v34 = v36;
    while ( v37 && v37 != 10 && v37 != 13 )
      v37 = *++v34;
    if ( *v34 == 10 )
    {
      *v34++ = 0;
    }
    else if ( *v34 == 13 )
    {
      *v34 = 0;
      v34 += 2;
    }
    v40 = WinSAT::TokenizeOneString((WinSAT *)&Block, 0, v33);
    if ( !v40 )
      goto LABEL_12;
    v57 = (WinSAT *)WinSAT::TokenizeOneString((WinSAT *)&Block, v38, v39);
    if ( !v57 )
      goto LABEL_12;
    v58 = (WinSAT *)WinSAT::TokenizeOneString((WinSAT *)&Block, v41, v42);
    if ( !v58 )
      goto LABEL_12;
    v59 = (WinSAT *)WinSAT::TokenizeOneString((WinSAT *)&Block, v43, v44);
    if ( !v59 )
      goto LABEL_12;
    LOBYTE(v45) = 1;
    Block = WinSAT::TokenizeOneString((WinSAT *)&Block, v45, v46);
    if ( !Block || lstrcmpiA(v40, "IoRead") && lstrcmpiA(v40, "IoWrite") && lstrcmpiA(v40, "IoFlush") )
      goto LABEL_12;
    if ( !WinSAT::ParseUlonglongHex(v57, v55, v47)
      || !WinSAT::ParseUlongHex(v58, (const char *)&v60, v48)
      || !WinSAT::ParseUlonglongHex(v59, v56, v49)
      || !WinSAT::ParseUlongHex((WinSAT *)Block, (const char *)&v62, v50)
      || v51 <= 1 && !v60 )
    {
      goto LABEL_12;
    }
    v52 = *(_QWORD *)v55;
    if ( v51 == 2 && (*(_QWORD *)v55 || v60) )
      goto LABEL_12;
    v5 = v63;
    ++v8;
    v35[4] = v60;
    *((_QWORD *)v35 + 3) = *(_QWORD *)v56;
    v53 = v62;
    *((_QWORD *)v35 + 1) = v52;
    v36 = v34;
    v35[8] = v53;
    *v35 = v51;
    v35 += 10;
    Block = v34;
  }
  v13 = 0;
LABEL_50:
  if ( v7 )
    operator delete(v7);
  return v13;
}

```

## disassembly

```asm
0x14006f6d4  mov     [rsp-38h+arg_8], rbx
0x14006f6d9  mov     [rsp-38h+arg_18], r9
0x14006f6de  mov     qword ptr [rsp-38h+arg_0], rcx
0x14006f6e3  push    rbp
0x14006f6e4  push    rsi
0x14006f6e5  push    rdi
0x14006f6e6  push    r12
0x14006f6e8  push    r13
0x14006f6ea  push    r14
0x14006f6ec  push    r15
0x14006f6ee  mov     rbp, rsp
0x14006f6f1  sub     rsp, 50h
0x14006f6f5  xor     ebx, ebx
0x14006f6f7  mov     r13, r8
0x14006f6fa  mov     [r9], ebx
0x14006f6fd  mov     rcx, rdx; this
0x14006f700  mov     [r8], rbx
0x14006f703  lea     rdx, [rbp+Block]; unsigned __int16 *
0x14006f707  lea     r8, [rbp+var_18]; char **
0x14006f70b  mov     [rbp+Block], rbx
0x14006f70f  mov     r12, r9
0x14006f712  mov     [rbp+var_18], rbx
0x14006f716  mov     qword ptr [rbp+var_28], rbx
0x14006f71a  mov     [rbp+arg_0], ebx
0x14006f71d  mov     qword ptr [rbp+var_20], rbx
0x14006f721  mov     [rbp+arg_10], ebx
0x14006f724  call    ?LoadFile@WinSAT@@YAKPEBGPEAPEADPEA_K@Z; WinSAT::LoadFile(ushort const *,char * *,unsigned __int64 *)
0x14006f729  test    eax, eax
0x14006f72b  jnz     loc_14006FABA
0x14006f731  mov     r14, [rbp+Block]
0x14006f735  mov     esi, ebx
0x14006f737  mov     rax, r14
0x14006f73a  mov     rcx, r14
0x14006f73d  mov     rdx, r14
0x14006f740  mov     r8b, [rax]
0x14006f743  test    r8b, r8b
0x14006f746  jz      loc_14006F89F
0x14006f74c  cmp     r8b, 0Ah
0x14006f750  jnz     short loc_14006F760
0x14006f752  inc     esi
0x14006f754  lea     rax, [rcx+1]
0x14006f758  mov     rcx, rax
0x14006f75b  mov     rdx, rax
0x14006f75e  jmp     short loc_14006F740
0x14006f760  cmp     r8b, 0Dh
0x14006f764  jnz     short loc_14006F754
0x14006f766  cmp     byte ptr [rdx+1], 0Ah
0x14006f76a  jnz     short loc_14006F774
0x14006f76c  inc     esi
0x14006f76e  lea     rax, [rcx+2]
0x14006f772  jmp     short loc_14006F758
0x14006f774  mov     ebx, 0Bh
0x14006f779  lea     r15, ?stdoutw@mlib@@3V?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@A; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>> mlib::stdoutw
0x14006f780  mov     rcx, r15
0x14006f783  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14006f788  mov     edi, 0F0h
0x14006f78d  lea     rdx, aThereWasAnErro; "There was an error in the scenario file"...
0x14006f794  lea     rcx, [rdi+rax]
0x14006f798  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14006f79d  lea     edx, [rsi+1]
0x14006f7a0  mov     rcx, rax
0x14006f7a3  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x14006f7a8  mov     rcx, rax
0x14006f7ab  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x14006f7b0  mov     rcx, rax
0x14006f7b3  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x14006f7b8  mov     rcx, r15
0x14006f7bb  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14006f7c0  lea     rdx, aTheFormatOfEac; "The format of each line is:"
0x14006f7c7  lea     rcx, [rdi+rax]
0x14006f7cb  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14006f7d0  mov     rcx, rax
0x14006f7d3  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x14006f7d8  mov     rcx, r15
0x14006f7db  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14006f7e0  lea     rdx, aIoreadIowriteI; "[IoRead | IoWrite | IoFlush ],Offset,Si"...
0x14006f7e7  lea     rcx, [rdi+rax]
0x14006f7eb  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14006f7f0  mov     rcx, rax
0x14006f7f3  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x14006f7f8  mov     rcx, rax
0x14006f7fb  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x14006f800  mov     rcx, r15
0x14006f803  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14006f808  lea     rdx, aCheckTheFollwi; "Check the follwing as well "
0x14006f80f  lea     rcx, [rdi+rax]
0x14006f813  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14006f818  mov     rcx, rax
0x14006f81b  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x14006f820  mov     rcx, r15
0x14006f823  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14006f828  lea     rdx, aFlushesShouldH; "    Flushes should have 0 offset and 0 "...
0x14006f82f  lea     rcx, [rdi+rax]
0x14006f833  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14006f838  mov     rcx, rax
0x14006f83b  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x14006f840  mov     rcx, r15
0x14006f843  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14006f848  lea     rdx, aAllNumbersAreI; "    All numbers are in Hex.  e.g. 0x1 "
0x14006f84f  lea     rcx, [rdi+rax]
0x14006f853  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14006f858  mov     rcx, rax
0x14006f85b  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x14006f860  mov     rcx, r15
0x14006f863  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14006f868  lea     rdx, aTheFileShouldE; "    The file should end in an empty lin"...
0x14006f86f  lea     rcx, [rdi+rax]
0x14006f873  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14006f878  mov     rcx, rax
0x14006f87b  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x14006f880  mov     rcx, [r13+0]; Block
0x14006f884  test    rcx, rcx
0x14006f887  jz      loc_14006FAAB
0x14006f88d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14006f892  mov     qword ptr [r13+0], 0
0x14006f89a  jmp     loc_14006FAAB
0x14006f89f  test    esi, esi
0x14006f8a1  jz      loc_14006F774
0x14006f8a7  mov     ecx, esi
0x14006f8a9  mov     eax, 28h ; '('
0x14006f8ae  mul     rcx
0x14006f8b1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14006f8b8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14006f8bf  cmovb   rax, rcx
0x14006f8c3  mov     rcx, rax; unsigned __int64
0x14006f8c6  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14006f8cb  mov     [r13+0], rax
0x14006f8cf  test    rax, rax
0x14006f8d2  jnz     short loc_14006F8DC
0x14006f8d4  lea     ebx, [rax+0Eh]
0x14006f8d7  jmp     loc_14006F779
0x14006f8dc  mov     [r12], esi
0x14006f8e0  mov     rdi, r14
0x14006f8e3  mov     r15, [r13+0]
0x14006f8e7  mov     esi, ebx
0x14006f8e9  mov     ebx, 0Bh
0x14006f8ee  mov     [rbp+Block], r14
0x14006f8f2  mov     rcx, r14
0x14006f8f5  cmp     byte ptr [rdi], 0
0x14006f8f8  jz      loc_14006FAA9
0x14006f8fe  cmp     esi, [r12]
0x14006f902  jnb     loc_14006F779
0x14006f908  mov     al, [rcx]
0x14006f90a  mov     rdi, rcx
0x14006f90d  test    al, al
0x14006f90f  jz      short loc_14006F920
0x14006f911  cmp     al, 0Ah
0x14006f913  jz      short loc_14006F920
0x14006f915  cmp     al, 0Dh
0x14006f917  jz      short loc_14006F920
0x14006f919  inc     rdi
0x14006f91c  mov     al, [rdi]
0x14006f91e  jmp     short loc_14006F90D
0x14006f920  cmp     byte ptr [rdi], 0Ah
0x14006f923  jnz     short loc_14006F92D
0x14006f925  mov     byte ptr [rdi], 0
0x14006f928  inc     rdi
0x14006f92b  jmp     short loc_14006F939
0x14006f92d  cmp     byte ptr [rdi], 0Dh
0x14006f930  jnz     short loc_14006F939
0x14006f932  mov     byte ptr [rdi], 0
0x14006f935  add     rdi, 2
0x14006f939  xor     edx, edx; char **
0x14006f93b  lea     rcx, [rbp+Block]; this
0x14006f93f  call    ?TokenizeOneString@WinSAT@@YAPEADPEAPEAD_N@Z; WinSAT::TokenizeOneString(char * *,bool)
0x14006f944  mov     r12, rax
0x14006f947  test    rax, rax
0x14006f94a  jz      loc_14006F779
0x14006f950  lea     rcx, [rbp+Block]; this
0x14006f954  call    ?TokenizeOneString@WinSAT@@YAPEADPEAPEAD_N@Z; WinSAT::TokenizeOneString(char * *,bool)
0x14006f959  mov     [rbp+var_18], rax
0x14006f95d  test    rax, rax
0x14006f960  jz      loc_14006F779
0x14006f966  lea     rcx, [rbp+Block]; this
0x14006f96a  call    ?TokenizeOneString@WinSAT@@YAPEADPEAPEAD_N@Z; WinSAT::TokenizeOneString(char * *,bool)
0x14006f96f  mov     [rbp+var_10], rax
0x14006f973  test    rax, rax
0x14006f976  jz      loc_14006F779
0x14006f97c  lea     rcx, [rbp+Block]; this
0x14006f980  call    ?TokenizeOneString@WinSAT@@YAPEADPEAPEAD_N@Z; WinSAT::TokenizeOneString(char * *,bool)
0x14006f985  mov     [rbp+var_8], rax
0x14006f989  test    rax, rax
0x14006f98c  jz      loc_14006F779
0x14006f992  mov     dl, 1; char **
0x14006f994  lea     rcx, [rbp+Block]; this
0x14006f998  call    ?TokenizeOneString@WinSAT@@YAPEADPEAPEAD_N@Z; WinSAT::TokenizeOneString(char * *,bool)
0x14006f99d  mov     [rbp+Block], rax
0x14006f9a1  test    rax, rax
0x14006f9a4  jz      loc_14006F779
0x14006f9aa  lea     rdx, aIoread; "IoRead"
0x14006f9b1  mov     rcx, r12; lpString1
0x14006f9b4  call    cs:__imp_lstrcmpiA
0x14006f9ba  test    eax, eax
0x14006f9bc  jnz     short loc_14006F9C3
0x14006f9be  xor     r11d, r11d
0x14006f9c1  jmp     short loc_14006F9F9
0x14006f9c3  lea     rdx, aIowrite; "IoWrite"
0x14006f9ca  mov     rcx, r12; lpString1
0x14006f9cd  call    cs:__imp_lstrcmpiA
0x14006f9d3  test    eax, eax
0x14006f9d5  jnz     short loc_14006F9DD
0x14006f9d7  lea     r11d, [rax+1]
0x14006f9db  jmp     short loc_14006F9F9
0x14006f9dd  lea     rdx, aIoflush; "IoFlush"
0x14006f9e4  mov     rcx, r12; lpString1
0x14006f9e7  call    cs:__imp_lstrcmpiA
0x14006f9ed  test    eax, eax
0x14006f9ef  jnz     loc_14006F779
0x14006f9f5  lea     r11d, [rax+2]
0x14006f9f9  mov     rcx, [rbp+var_18]; this
0x14006f9fd  lea     rdx, [rbp+var_28]; char *
0x14006fa01  call    ?ParseUlonglongHex@WinSAT@@YAEPEBDPEA_K@Z; WinSAT::ParseUlonglongHex(char const *,unsigned __int64 *)
0x14006fa06  test    al, al
0x14006fa08  jz      loc_14006F779
0x14006fa0e  mov     rcx, [rbp+var_10]; this
0x14006fa12  lea     rdx, [rbp+arg_0]; char *
0x14006fa16  call    ?ParseUlongHex@WinSAT@@YAEPEBDPEAK@Z; WinSAT::ParseUlongHex(char const *,ulong *)
0x14006fa1b  test    al, al
0x14006fa1d  jz      loc_14006F779
0x14006fa23  mov     rcx, [rbp+var_8]; this
0x14006fa27  lea     rdx, [rbp+var_20]; char *
0x14006fa2b  call    ?ParseUlonglongHex@WinSAT@@YAEPEBDPEA_K@Z; WinSAT::ParseUlonglongHex(char const *,unsigned __int64 *)
0x14006fa30  test    al, al
0x14006fa32  jz      loc_14006F779
0x14006fa38  mov     rcx, [rbp+Block]; this
0x14006fa3c  lea     rdx, [rbp+arg_10]; char *
0x14006fa40  call    ?ParseUlongHex@WinSAT@@YAEPEBDPEAK@Z; WinSAT::ParseUlongHex(char const *,ulong *)
0x14006fa45  test    al, al
0x14006fa47  jz      loc_14006F779
0x14006fa4d  mov     eax, [rbp+arg_0]
0x14006fa50  cmp     r11d, 1
0x14006fa54  ja      short loc_14006FA5E
0x14006fa56  test    eax, eax
0x14006fa58  jz      loc_14006F779
0x14006fa5e  mov     rcx, qword ptr [rbp+var_28]
0x14006fa62  cmp     r11d, 2
0x14006fa66  jnz     short loc_14006FA79
0x14006fa68  test    rcx, rcx
0x14006fa6b  jnz     loc_14006F779
0x14006fa71  test    eax, eax
0x14006fa73  jnz     loc_14006F779
0x14006fa79  mov     r12, [rbp+arg_18]
0x14006fa7d  inc     esi
0x14006fa7f  mov     [r15+10h], eax
0x14006fa83  mov     rax, qword ptr [rbp+var_20]
0x14006fa87  mov     [r15+18h], rax
0x14006fa8b  mov     eax, [rbp+arg_10]
0x14006fa8e  mov     [r15+8], rcx
0x14006fa92  mov     rcx, rdi
0x14006fa95  mov     [r15+20h], eax
0x14006fa99  mov     [r15], r11d
0x14006fa9c  add     r15, 28h ; '('
0x14006faa0  mov     [rbp+Block], rdi
0x14006faa4  jmp     loc_14006F8F5
0x14006faa9  xor     ebx, ebx
0x14006faab  test    r14, r14
0x14006faae  jz      short loc_14006FAB8
0x14006fab0  mov     rcx, r14; Block
0x14006fab3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14006fab8  mov     eax, ebx
0x14006faba  mov     rbx, [rsp+50h+arg_8]
0x14006fac2  add     rsp, 50h
0x14006fac6  pop     r15
0x14006fac8  pop     r14
0x14006faca  pop     r13
0x14006facc  pop     r12
0x14006face  pop     rdi
0x14006facf  pop     rsi
0x14006fad0  pop     rbp
0x14006fad1  retn
```
