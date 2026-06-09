# CInitiateWinSAT::WinSATCompletionRoutine(void *,void *)

- ea: `0x18001ea90`
- end: `0x18001ed90`
- name: `?WinSATCompletionRoutine@CInitiateWinSAT@@CAXPEAX0@Z`
- size: `768`
- prototype: `void __fastcall(void *, void *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180013f80`
- `0x180013fb6`
- `0x18001d63c`
- `0x18001dc18`
- `0x18001ea90`
- `0x18001ed98`
- `0x18002c3c8`
- `0x180031010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18001ecf8`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001ecf8`

## pseudocode

```c
void __fastcall CInitiateWinSAT::WinSATCompletionRoutine(_QWORD *a1, char *a2)
{
  __int64 v3; // rcx
  const char *v4; // rdx
  mlib *v5; // rcx
  signed int v6; // ebx
  unsigned __int16 v7; // r9
  WCHAR *v8; // rdi
  int v9; // r8d
  const unsigned __int16 *v10; // r12
  __int64 v11; // r15
  unsigned __int64 v12; // rax
  WCHAR *v13; // rax
  WCHAR *v14; // rsi
  int v15; // esi
  const WCHAR *v16; // r8
  unsigned __int64 *v17; // [rsp+28h] [rbp-30h]
  __int64 v18; // [rsp+78h] [rbp+20h] BYREF

  v3 = a1[9];
  if ( !v3 )
    return;
  if ( a2 )
  {
    (*(void (__fastcall **)(__int64, _QWORD, _QWORD, char *))(*(_QWORD *)v3 + 32LL))(
      v3,
      *(unsigned int *)a2,
      *((unsigned int *)a2 + 1),
      a2 + 8);
    return;
  }
  v6 = WinSATGetCompletionStatus();
  v8 = 0;
  if ( v6 > -2147221452 )
  {
    switch ( v6 )
    {
      case -2147221451:
        v9 = 11023;
        break;
      case -2147221450:
        v9 = 11024;
        break;
      case -2147221449:
        v9 = 11025;
        break;
      case -2147221448:
        v9 = 11026;
        break;
      case -2147221447:
        v9 = 11027;
        break;
      case 262194:
        v9 = 11020;
        break;
      case 262195:
        v9 = 11021;
        break;
      default:
LABEL_31:
        v8 = (WCHAR *)&String2;
LABEL_44:
        v15 = 0;
        goto LABEL_45;
    }
  }
  else
  {
    if ( v6 != -2147221452 )
    {
      v5 = (mlib *)(v6 + 2147221503);
      v4 = (const char *)0x180000000LL;
      switch ( v6 )
      {
        case -2147221503:
          v9 = 11001;
          goto LABEL_39;
        case -2147221502:
          v9 = 11002;
          goto LABEL_39;
        case -2147221501:
          v9 = 11003;
          goto LABEL_39;
        case -2147221498:
          v9 = 11006;
          goto LABEL_39;
        case -2147221497:
          v9 = 11007;
          goto LABEL_39;
        case -2147221496:
          v9 = 11008;
          goto LABEL_39;
        case -2147221495:
          v9 = 11009;
          goto LABEL_39;
        case -2147221494:
          v9 = 11010;
          goto LABEL_39;
        case -2147221493:
          v9 = 11011;
          goto LABEL_39;
        case -2147221492:
          v9 = 11012;
          goto LABEL_39;
        case -2147221491:
          v9 = 11013;
          goto LABEL_39;
        case -2147221490:
          v9 = 11014;
          goto LABEL_39;
        case -2147221489:
          v9 = 11015;
          goto LABEL_39;
        case -2147221488:
          v9 = 11016;
          goto LABEL_39;
        case -2147221487:
          v9 = 11017;
          goto LABEL_39;
        case -2147221486:
          v9 = 11018;
          goto LABEL_39;
        case -2147221485:
          v9 = 11019;
          goto LABEL_39;
        default:
          goto LABEL_31;
      }
    }
    v9 = 11022;
  }
LABEL_39:
  v18 = 0;
  v10 = mlib::MUIStrAndLen_(v5, v4, v9, v7, (HINSTANCE)&v18, v17);
  v11 = v18 + 1;
  v12 = 2 * (v18 + 1);
  if ( !is_mul_ok(v18 + 1, 2u) )
    v12 = -1;
  v13 = (WCHAR *)operator new[](v12, (const struct std::nothrow_t *)&std::nothrow);
  v14 = v13;
  if ( v13 )
  {
    memcpy_0(v13, v10, 2 * v11);
    v8 = v14;
    goto LABEL_44;
  }
  v15 = -2147024882;
LABEL_45:
  WriteToRegistrySuccessOfLastRunOfWinsat(v6);
  v16 = &String2;
  if ( v15 >= 0 )
    v16 = v8;
  (*(void (__fastcall **)(_QWORD, _QWORD, const WCHAR *))(*(_QWORD *)a1[9] + 24LL))(a1[9], (unsigned int)v6, v16);
  operator delete[](v8);
}

```

## disassembly

```asm
0x18001ea90  mov     [rsp+arg_8], rbx
0x18001ea95  mov     [rsp+arg_0], rcx
0x18001ea9a  push    rsi
0x18001ea9b  push    rdi
0x18001ea9c  push    r12
0x18001ea9e  push    r14
0x18001eaa0  push    r15
0x18001eaa2  sub     rsp, 30h
0x18001eaa6  mov     r14, rcx
0x18001eaa9  mov     rcx, [rcx+48h]
0x18001eaad  test    rcx, rcx
0x18001eab0  jz      loc_18001ED2F
0x18001eab6  test    rdx, rdx
0x18001eab9  jnz     loc_18001ED00
0x18001eabf  call    WinSATGetCompletionStatus
0x18001eac4  mov     ebx, eax
0x18001eac6  xor     edi, edi
0x18001eac8  mov     [rsp+58h+arg_10], rdi
0x18001eacd  mov     eax, 80040034h
0x18001ead2  cmp     ebx, eax
0x18001ead4  jg      loc_18001EBC8
0x18001eada  jz      loc_18001EBC0
0x18001eae0  lea     eax, [rbx+7FFBFFFFh]; switch 19 cases
0x18001eae6  cmp     eax, 12h
0x18001eae9  ja      def_18001EB03; jumptable 000000018001EB03 default case, cases -2147221500,-2147221499
0x18001eaef  movsxd  rcx, eax
0x18001eaf2  lea     rdx, cs:180000000h
0x18001eaf9  mov     eax, ds:(jpt_18001EB03 - 180000000h)[rdx+rcx*4]
0x18001eb00  add     rax, rdx
0x18001eb03  jmp     rax; switch jump
0x18001eb05  mov     r8d, 2AF9h; jumptable 000000018001EB03 case -2147221503
0x18001eb0b  jmp     loc_18001EC47
0x18001eb10  mov     r8d, 2AFAh; jumptable 000000018001EB03 case -2147221502
0x18001eb16  jmp     loc_18001EC47
0x18001eb1b  mov     r8d, 2AFBh; jumptable 000000018001EB03 case -2147221501
0x18001eb21  jmp     loc_18001EC47
0x18001eb26  mov     r8d, 2AFEh; jumptable 000000018001EB03 case -2147221498
0x18001eb2c  jmp     loc_18001EC47
0x18001eb31  mov     r8d, 2AFFh; jumptable 000000018001EB03 case -2147221497
0x18001eb37  jmp     loc_18001EC47
0x18001eb3c  mov     r8d, 2B00h; jumptable 000000018001EB03 case -2147221496
0x18001eb42  jmp     loc_18001EC47
0x18001eb47  mov     r8d, 2B01h; jumptable 000000018001EB03 case -2147221495
0x18001eb4d  jmp     loc_18001EC47
0x18001eb52  mov     r8d, 2B02h; jumptable 000000018001EB03 case -2147221494
0x18001eb58  jmp     loc_18001EC47
0x18001eb5d  mov     r8d, 2B03h; jumptable 000000018001EB03 case -2147221493
0x18001eb63  jmp     loc_18001EC47
0x18001eb68  mov     r8d, 2B04h; jumptable 000000018001EB03 case -2147221492
0x18001eb6e  jmp     loc_18001EC47
0x18001eb73  mov     r8d, 2B05h; jumptable 000000018001EB03 case -2147221491
0x18001eb79  jmp     loc_18001EC47
0x18001eb7e  mov     r8d, 2B06h; jumptable 000000018001EB03 case -2147221490
0x18001eb84  jmp     loc_18001EC47
0x18001eb89  mov     r8d, 2B07h; jumptable 000000018001EB03 case -2147221489
0x18001eb8f  jmp     loc_18001EC47
0x18001eb94  mov     r8d, 2B08h; jumptable 000000018001EB03 case -2147221488
0x18001eb9a  jmp     loc_18001EC47
0x18001eb9f  mov     r8d, 2B09h; jumptable 000000018001EB03 case -2147221487
0x18001eba5  jmp     loc_18001EC47
0x18001ebaa  mov     r8d, 2B0Ah; jumptable 000000018001EB03 case -2147221486
0x18001ebb0  jmp     loc_18001EC47
0x18001ebb5  mov     r8d, 2B0Bh; jumptable 000000018001EB03 case -2147221485
0x18001ebbb  jmp     loc_18001EC47
0x18001ebc0  mov     r8d, 2B0Eh
0x18001ebc6  jmp     short loc_18001EC47
0x18001ebc8  cmp     ebx, 80040035h
0x18001ebce  jz      short loc_18001EC41
0x18001ebd0  cmp     ebx, 80040036h
0x18001ebd6  jz      short loc_18001EC39
0x18001ebd8  cmp     ebx, 80040037h
0x18001ebde  jz      short loc_18001EC31
0x18001ebe0  cmp     ebx, 80040038h
0x18001ebe6  jz      short loc_18001EC29
0x18001ebe8  cmp     ebx, 80040039h
0x18001ebee  jz      short loc_18001EC21
0x18001ebf0  cmp     ebx, 40032h
0x18001ebf6  jz      short loc_18001EC19
0x18001ebf8  cmp     ebx, 40033h
0x18001ebfe  jz      short loc_18001EC11
0x18001ec00  lea     rdi, String2; jumptable 000000018001EB03 default case, cases -2147221500,-2147221499
0x18001ec07  mov     [rsp+58h+arg_10], rdi
0x18001ec0c  jmp     loc_18001ECAE
0x18001ec11  mov     r8d, 2B0Dh
0x18001ec17  jmp     short loc_18001EC47
0x18001ec19  mov     r8d, 2B0Ch
0x18001ec1f  jmp     short loc_18001EC47
0x18001ec21  mov     r8d, 2B13h
0x18001ec27  jmp     short loc_18001EC47
0x18001ec29  mov     r8d, 2B12h
0x18001ec2f  jmp     short loc_18001EC47
0x18001ec31  mov     r8d, 2B11h
0x18001ec37  jmp     short loc_18001EC47
0x18001ec39  mov     r8d, 2B10h
0x18001ec3f  jmp     short loc_18001EC47
0x18001ec41  mov     r8d, 2B0Fh; int
0x18001ec47  mov     [rsp+58h+arg_18], rdi
0x18001ec4c  lea     rax, [rsp+58h+arg_18]
0x18001ec51  mov     [rsp+58h+var_38], rax; HINSTANCE
0x18001ec56  call    ?MUIStrAndLen_@mlib@@YAPEBGPEBDHGPEAUHINSTANCE__@@AEA_K@Z; mlib::MUIStrAndLen_(char const *,int,ushort,HINSTANCE__ *,unsigned __int64 &)
0x18001ec5b  mov     r12, rax
0x18001ec5e  mov     r15, [rsp+58h+arg_18]
0x18001ec63  inc     r15
0x18001ec66  mov     eax, 2
0x18001ec6b  mul     r15
0x18001ec6e  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001ec75  cmovb   rax, rcx
0x18001ec79  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001ec80  mov     rcx, rax; unsigned __int64
0x18001ec83  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001ec88  mov     rsi, rax
0x18001ec8b  test    rax, rax
0x18001ec8e  jnz     short loc_18001EC97
0x18001ec90  mov     esi, 8007000Eh
0x18001ec95  jmp     short loc_18001ECB0
0x18001ec97  lea     r8, [r15+r15]; Size
0x18001ec9b  mov     rdx, r12; Src
0x18001ec9e  mov     rcx, rsi; void *
0x18001eca1  call    memcpy_0
0x18001eca6  mov     rdi, rsi
0x18001eca9  mov     [rsp+58h+arg_10], rsi
0x18001ecae  xor     esi, esi
0x18001ecb0  mov     ecx, ebx; unsigned int
0x18001ecb2  call    ?WriteToRegistrySuccessOfLastRunOfWinsat@@YA_NJ@Z; WriteToRegistrySuccessOfLastRunOfWinsat(long)
0x18001ecb7  nop
0x18001ecb8  mov     rcx, [r14+48h]
0x18001ecbc  mov     rax, [rcx]
0x18001ecbf  mov     edx, ebx
0x18001ecc1  mov     rax, [rax+18h]
0x18001ecc5  test    esi, esi
0x18001ecc7  lea     r8, String2
0x18001ecce  js      short loc_18001ECD3
0x18001ecd0  mov     r8, rdi
0x18001ecd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ecd8  jmp     short loc_18001ECF5
0x18001ecda  mov     rcx, [rsp+58h+arg_0]
0x18001ecdf  add     rcx, 48h ; 'H'; struct IUnknown **
0x18001ece3  cmp     qword ptr [rcx], 0
0x18001ece7  jz      short loc_18001ECF0
0x18001ece9  xor     edx, edx; struct IUnknown *
0x18001eceb  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18001ecf0  mov     rdi, [rsp+58h+arg_10]
0x18001ecf5  mov     rcx, rdi
0x18001ecf8  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001ecfe  jmp     short loc_18001ED2F
0x18001ed00  mov     rax, [rcx]
0x18001ed03  lea     r9, [rdx+8]
0x18001ed07  mov     r8d, [rdx+4]
0x18001ed0b  mov     edx, [rdx]
0x18001ed0d  mov     rax, [rax+20h]
0x18001ed11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed16  jmp     short loc_18001ED2F
0x18001ed18  mov     rcx, [rsp+58h+arg_0]
0x18001ed1d  add     rcx, 48h ; 'H'; struct IUnknown **
0x18001ed21  cmp     qword ptr [rcx], 0
0x18001ed25  jz      short loc_18001ED2F
0x18001ed27  xor     edx, edx; struct IUnknown *
0x18001ed29  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18001ed2e  nop
0x18001ed2f  mov     rbx, [rsp+58h+arg_8]
0x18001ed34  add     rsp, 30h
0x18001ed38  pop     r15
0x18001ed3a  pop     r14
0x18001ed3c  pop     r12
0x18001ed3e  pop     rdi
0x18001ed3f  pop     rsi
0x18001ed40  retn
0x18002ffe5  push    rbp
0x18002ffe7  sub     rsp, 30h
0x18002ffeb  mov     rbp, rdx
0x18002ffee  mov     rax, [rcx]
0x18002fff1  xor     ecx, ecx
0x18002fff3  cmp     dword ptr [rax], 0C0000005h
0x18002fff9  setz    cl
0x18002fffc  mov     eax, ecx
0x18002fffe  add     rsp, 30h
0x180030002  pop     rbp
0x180030003  retn
0x180030005  push    rbp
0x180030007  sub     rsp, 30h
0x18003000b  mov     rbp, rdx
0x18003000e  mov     rax, [rcx]
0x180030011  xor     ecx, ecx
0x180030013  cmp     dword ptr [rax], 0C0000005h
0x180030019  setz    cl
0x18003001c  mov     eax, ecx
0x18003001e  add     rsp, 30h
0x180030022  pop     rbp
0x180030023  retn
```
