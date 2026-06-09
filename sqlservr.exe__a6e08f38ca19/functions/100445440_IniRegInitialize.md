# IniRegInitialize

- ea: `0x100445440`
- end: `0x10044587a`
- name: `IniRegInitialize`
- size: `1082`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x100445920`

## callees

- `0x1004027c0`
- `0x100407020`
- `0x100445410`
- `0x100445440`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x100445502`
- `KERNEL32!GetModuleFileNameW` at `0x100445502`
- `KERNEL32!GetFileAttributesW` at `0x1004456d3`
- `KERNEL32!GetFileAttributesW` at `0x1004456d3`

## string_xrefs

- `0x1004457b2`: `wszIniRegDirectory %s \n`
- `0x100445470`: `IniRegistryLib is getting loaded.\n`
- `0x10044583a`: `g_wszIniRegExtPath: %s \n`

## pseudocode

```c
__int64 __fastcall IniRegInitialize(struct DkParameter *a1, _WORD *a2, int a3)
{
  struct DkParameter *v4; // rcx
  struct DkParameter *v5; // rcx
  int i; // [rsp+20h] [rbp-A8h]
  WCHAR *v7; // [rsp+28h] [rbp-A0h]
  DWORD ModuleFileNameW; // [rsp+30h] [rbp-98h]
  int v9; // [rsp+34h] [rbp-94h]
  char *j; // [rsp+38h] [rbp-90h]
  int v11; // [rsp+40h] [rbp-88h]
  __int64 v12; // [rsp+48h] [rbp-80h]
  WCHAR *v13; // [rsp+50h] [rbp-78h]
  __int64 v14; // [rsp+58h] [rbp-70h]
  __int64 v15; // [rsp+60h] [rbp-68h]
  WCHAR *v16; // [rsp+70h] [rbp-58h]
  void *v17; // [rsp+78h] [rbp-50h]
  int v18; // [rsp+80h] [rbp-48h]

  if ( dword_10049F370 )
    return 1;
  CmdLineParamProcessDash_g(a1);
  Trace(L"IniRegistryLib is getting loaded.\r\n");
  if ( a2 )
  {
    v12 = -1;
    do
      ++v12;
    while ( a2[v12] );
    v18 = v12;
  }
  else
  {
    v18 = 3;
  }
  v9 = v18 + 1;
  ModuleFileNameW = GetModuleFileNameW((HMODULE)a1, &Filename, 260 - (v18 + 1));
  if ( !ModuleFileNameW )
    goto LABEL_39;
  _mm_lfence();
  v7 = &Filename + ModuleFileNameW - 1;
  Trace(L"%s \r\n", v7);
  v13 = 0;
  v16 = 0;
  while ( !v13 && v7 > &Filename )
  {
    if ( v16 )
    {
      if ( *v7 == 92 )
        v13 = v7;
    }
    else if ( *v7 == 46 )
    {
      v16 = v7;
    }
    --v7;
  }
  if ( !v13 )
    goto LABEL_39;
  v11 = 0;
  v17 = v13 + 1;
  if ( a2 )
  {
    qmemcpy(v17, a2, (unsigned int)(2 * v9));
    v4 = 0;
  }
  else
  {
    for ( i = 0; !i; i = 1 )
    {
      _mm_lfence();
      if ( CmpString(
             (&off_1004A18B8)[2 * (unsigned __int8)i],
             *((_DWORD *)&off_1004A18B8 + 4 * (unsigned __int8)i + 2),
             (const WCHAR *)v17,
             ModuleFileNameW - (unsigned int)(((_BYTE *)v17 - (_BYTE *)&Filename) >> 1)) )
      {
        v11 = 1;
      }
    }
    qmemcpy(v16 + 1, L"ini", (unsigned int)(2 * v9));
    v4 = 0;
  }
  if ( v11 || GetFileAttributesW(&Filename) == -1 )
  {
LABEL_39:
    CmdLineParamProcessDash_g(v4);
    return 0;
  }
  else
  {
    qmemcpy(qword_1004D3FA0, &Filename, 0x208u);
    v14 = -1;
    do
      ++v14;
    while ( *((_WORD *)qword_1004D3FA0 + v14) );
    for ( j = (char *)qword_1004D3FA0 + 2 * v14 - 2; *(_WORD *)j != 92 && j > (char *)qword_1004D3FA0; j -= 2 )
      ;
    *(_WORD *)j = 0;
    dword_1004D3F90 = ((j - (char *)qword_1004D3FA0) >> 1) + 1;
    Trace(L"wszIniRegDirectory %s \r\n", qword_1004D3FA0);
    qmemcpy(&FileName, &Filename, 0x208u);
    v15 = -1;
    do
      ++v15;
    while ( *(&FileName + v15) );
    qmemcpy(&FileName + (unsigned int)v15, L".ext", 0xAu);
    Trace(L"g_wszIniRegExtPath: %s \r\n", &FileName);
    dword_10049F7A0 = a3;
    dword_10049F370 = 1;
    CmdLineParamProcessDash_g(v5);
    return 1;
  }
}

```

## disassembly

```asm
0x100445440  mov     [rsp+arg_10], r8d
0x100445445  mov     [rsp+arg_8], rdx
0x10044544a  mov     [rsp+hModule], rcx
0x10044544f  push    rsi
0x100445450  push    rdi
0x100445451  sub     rsp, 0B8h
0x100445458  cmp     cs:dword_10049F370, 0
0x10044545f  jz      short loc_10044546B
0x100445461  mov     eax, 1
0x100445466  jmp     loc_100445870
0x10044546b  call    ?CmdLineParamProcessDash_g@@YAXAEAVDkParameter@@@Z; CmdLineParamProcessDash_g(DkParameter &)
0x100445470  lea     rcx, aIniregistrylib; "IniRegistryLib is getting loaded.\r\n"
0x100445477  call    Trace
0x10044547c  cmp     [rsp+0C8h+arg_8], 0
0x100445485  jz      short loc_1004454C8
0x100445487  mov     rax, [rsp+0C8h+arg_8]
0x10044548f  mov     [rsp+0C8h+var_38], rax
0x100445497  mov     [rsp+0C8h+var_80], 0FFFFFFFFFFFFFFFFh
0x1004454a0  inc     [rsp+0C8h+var_80]
0x1004454a5  mov     rax, [rsp+0C8h+var_38]
0x1004454ad  mov     rcx, [rsp+0C8h+var_80]
0x1004454b2  cmp     word ptr [rax+rcx*2], 0
0x1004454b7  jnz     short loc_1004454A0
0x1004454b9  mov     rax, [rsp+0C8h+var_80]
0x1004454be  mov     [rsp+0C8h+var_48], rax
0x1004454c6  jmp     short loc_1004454D4
0x1004454c8  mov     [rsp+0C8h+var_48], 3
0x1004454d4  mov     eax, dword ptr [rsp+0C8h+var_48]
0x1004454db  inc     eax
0x1004454dd  mov     [rsp+0C8h+var_94], eax
0x1004454e1  mov     eax, [rsp+0C8h+var_94]
0x1004454e5  mov     ecx, 104h
0x1004454ea  sub     rcx, rax
0x1004454ed  mov     rax, rcx
0x1004454f0  mov     r8d, eax; nSize
0x1004454f3  lea     rdx, Filename; lpFilename
0x1004454fa  mov     rcx, [rsp+0C8h+hModule]; hModule
0x100445502  call    cs:__imp_GetModuleFileNameW
0x100445508  mov     [rsp+0C8h+var_98], eax
0x10044550c  cmp     [rsp+0C8h+var_98], 0
0x100445511  jbe     loc_100445869
0x100445517  lfence
0x10044551a  mov     eax, [rsp+0C8h+var_98]
0x10044551e  lea     rcx, Filename
0x100445525  lea     rax, [rcx+rax*2-2]
0x10044552a  mov     [rsp+0C8h+var_A0], rax
0x10044552f  mov     rdx, [rsp+0C8h+var_A0]
0x100445534  lea     rcx, aS_3; "%s \r\n"
0x10044553b  call    Trace
0x100445540  mov     [rsp+0C8h+var_78], 0
0x100445549  mov     [rsp+0C8h+var_58], 0
0x100445552  cmp     [rsp+0C8h+var_78], 0
0x100445558  jnz     short loc_1004455B0
0x10044555a  lea     rax, Filename
0x100445561  cmp     [rsp+0C8h+var_A0], rax
0x100445566  jbe     short loc_1004455B0
0x100445568  cmp     [rsp+0C8h+var_58], 0
0x10044556e  jnz     short loc_100445589
0x100445570  mov     rax, [rsp+0C8h+var_A0]
0x100445575  movzx   eax, word ptr [rax]
0x100445578  cmp     eax, 2Eh ; '.'
0x10044557b  jnz     short loc_100445587
0x10044557d  mov     rax, [rsp+0C8h+var_A0]
0x100445582  mov     [rsp+0C8h+var_58], rax
0x100445587  jmp     short loc_1004455A0
0x100445589  mov     rax, [rsp+0C8h+var_A0]
0x10044558e  movzx   eax, word ptr [rax]
0x100445591  cmp     eax, 5Ch ; '\'
0x100445594  jnz     short loc_1004455A0
0x100445596  mov     rax, [rsp+0C8h+var_A0]
0x10044559b  mov     [rsp+0C8h+var_78], rax
0x1004455a0  mov     rax, [rsp+0C8h+var_A0]
0x1004455a5  sub     rax, 2
0x1004455a9  mov     [rsp+0C8h+var_A0], rax
0x1004455ae  jmp     short loc_100445552
0x1004455b0  cmp     [rsp+0C8h+var_78], 0
0x1004455b6  jz      loc_100445869
0x1004455bc  mov     [rsp+0C8h+var_88], 0
0x1004455c4  mov     rax, [rsp+0C8h+var_78]
0x1004455c9  add     rax, 2
0x1004455cd  mov     [rsp+0C8h+var_50], rax
0x1004455d2  mov     rax, [rsp+0C8h+var_58]
0x1004455d7  add     rax, 2
0x1004455db  mov     [rsp+0C8h+var_30], rax
0x1004455e3  cmp     [rsp+0C8h+arg_8], 0
0x1004455ec  jz      short loc_10044560D
0x1004455ee  mov     eax, [rsp+0C8h+var_94]
0x1004455f2  shl     rax, 1
0x1004455f5  mov     eax, eax
0x1004455f7  mov     rdi, [rsp+0C8h+var_50]
0x1004455fc  mov     rsi, [rsp+0C8h+arg_8]
0x100445604  mov     ecx, eax
0x100445606  rep movsb
0x100445608  jmp     loc_1004456C1
0x10044560d  lea     rax, Filename
0x100445614  mov     rcx, [rsp+0C8h+var_50]
0x100445619  sub     rcx, rax
0x10044561c  mov     rax, rcx
0x10044561f  sar     rax, 1
0x100445622  mov     ecx, [rsp+0C8h+var_98]
0x100445626  sub     ecx, eax
0x100445628  mov     eax, ecx
0x10044562a  mov     [rsp+0C8h+var_60], eax
0x10044562e  mov     [rsp+0C8h+var_A8], 0
0x100445636  jmp     short loc_100445642
0x100445638  mov     eax, [rsp+0C8h+var_A8]
0x10044563c  inc     eax
0x10044563e  mov     [rsp+0C8h+var_A8], eax
0x100445642  mov     eax, [rsp+0C8h+var_A8]
0x100445646  cmp     rax, 1
0x10044564a  jnb     short loc_1004456A2
0x10044564c  lfence
0x10044564f  mov     eax, [rsp+0C8h+var_A8]
0x100445653  imul    rax, 10h
0x100445657  lea     rcx, off_1004A18B8; "msmdsrv.exe"
0x10044565e  add     rcx, rax
0x100445661  mov     rax, rcx
0x100445664  mov     [rsp+0C8h+var_40], rax
0x10044566c  mov     r9d, [rsp+0C8h+var_60]
0x100445671  mov     r8, [rsp+0C8h+var_50]
0x100445676  mov     rax, [rsp+0C8h+var_40]
0x10044567e  mov     edx, [rax+8]
0x100445681  mov     rax, [rsp+0C8h+var_40]
0x100445689  mov     rcx, [rax]
0x10044568c  call    CmpString
0x100445691  movzx   eax, al
0x100445694  test    eax, eax
0x100445696  jz      short loc_1004456A0
0x100445698  mov     [rsp+0C8h+var_88], 1
0x1004456a0  jmp     short loc_100445638
0x1004456a2  mov     eax, [rsp+0C8h+var_94]
0x1004456a6  shl     rax, 1
0x1004456a9  mov     eax, eax
0x1004456ab  lea     rcx, aIni; "ini"
0x1004456b2  mov     rdi, [rsp+0C8h+var_30]
0x1004456ba  mov     rsi, rcx
0x1004456bd  mov     ecx, eax
0x1004456bf  rep movsb
0x1004456c1  cmp     [rsp+0C8h+var_88], 0
0x1004456c6  jnz     loc_100445869
0x1004456cc  lea     rcx, Filename; lpFileName
0x1004456d3  call    cs:__imp_GetFileAttributesW
0x1004456d9  cmp     eax, 0FFFFFFFFh
0x1004456dc  jz      loc_100445869
0x1004456e2  lea     rax, qword_1004D3FA0
0x1004456e9  lea     rcx, Filename
0x1004456f0  mov     rdi, rax
0x1004456f3  mov     rsi, rcx
0x1004456f6  mov     ecx, 208h
0x1004456fb  rep movsb
0x1004456fd  lea     rax, qword_1004D3FA0
0x100445704  mov     [rsp+0C8h+var_28], rax
0x10044570c  mov     [rsp+0C8h+var_70], 0FFFFFFFFFFFFFFFFh
0x100445715  inc     [rsp+0C8h+var_70]
0x10044571a  mov     rax, [rsp+0C8h+var_28]
0x100445722  mov     rcx, [rsp+0C8h+var_70]
0x100445727  cmp     word ptr [rax+rcx*2], 0
0x10044572c  jnz     short loc_100445715
0x10044572e  mov     rax, [rsp+0C8h+var_70]
0x100445733  lea     rcx, qword_1004D3FA0
0x10044573a  lea     rax, [rcx+rax*2-2]
0x10044573f  mov     [rsp+0C8h+var_90], rax
0x100445744  mov     eax, 2
0x100445749  imul    rax, 0
0x10044574d  mov     rcx, [rsp+0C8h+var_90]
0x100445752  movzx   eax, word ptr [rcx+rax]
0x100445756  cmp     eax, 5Ch ; '\'
0x100445759  jz      short loc_100445779
0x10044575b  lea     rax, qword_1004D3FA0
0x100445762  cmp     [rsp+0C8h+var_90], rax
0x100445767  jbe     short loc_100445779
0x100445769  mov     rax, [rsp+0C8h+var_90]
0x10044576e  sub     rax, 2
0x100445772  mov     [rsp+0C8h+var_90], rax
0x100445777  jmp     short loc_100445744
0x100445779  mov     eax, 2
0x10044577e  imul    rax, 0
0x100445782  xor     ecx, ecx
0x100445784  mov     rdx, [rsp+0C8h+var_90]
0x100445789  mov     [rdx+rax], cx
0x10044578d  lea     rax, qword_1004D3FA0
0x100445794  mov     rcx, [rsp+0C8h+var_90]
0x100445799  sub     rcx, rax
0x10044579c  mov     rax, rcx
0x10044579f  sar     rax, 1
0x1004457a2  inc     rax
0x1004457a5  mov     cs:dword_1004D3F90, eax
0x1004457ab  lea     rdx, qword_1004D3FA0
0x1004457b2  lea     rcx, aWsziniregdirec; "wszIniRegDirectory %s \r\n"
0x1004457b9  call    Trace
0x1004457be  lea     rax, FileName
0x1004457c5  lea     rcx, Filename
0x1004457cc  mov     rdi, rax
0x1004457cf  mov     rsi, rcx
0x1004457d2  mov     ecx, 208h
0x1004457d7  rep movsb
0x1004457d9  lea     rax, FileName
0x1004457e0  mov     [rsp+0C8h+var_20], rax
0x1004457e8  mov     [rsp+0C8h+var_68], 0FFFFFFFFFFFFFFFFh
0x1004457f1  inc     [rsp+0C8h+var_68]
0x1004457f6  mov     rax, [rsp+0C8h+var_20]
0x1004457fe  mov     rcx, [rsp+0C8h+var_68]
0x100445803  cmp     word ptr [rax+rcx*2], 0
0x100445808  jnz     short loc_1004457F1
0x10044580a  mov     rax, [rsp+0C8h+var_68]
0x10044580f  mov     [rsp+0C8h+var_5C], eax
0x100445813  mov     eax, [rsp+0C8h+var_5C]
0x100445817  lea     rcx, FileName
0x10044581e  lea     rdx, aExt; ".ext"
0x100445825  lea     rdi, [rcx+rax*2]
0x100445829  mov     rsi, rdx
0x10044582c  mov     ecx, 0Ah
0x100445831  rep movsb
0x100445833  lea     rdx, FileName
0x10044583a  lea     rcx, aGWsziniregextp; "g_wszIniRegExtPath: %s \r\n"
0x100445841  call    Trace
0x100445846  mov     eax, [rsp+0C8h+arg_10]
0x10044584d  mov     cs:dword_10049F7A0, eax
0x100445853  mov     cs:dword_10049F370, 1
0x10044585d  call    ?CmdLineParamProcessDash_g@@YAXAEAVDkParameter@@@Z; CmdLineParamProcessDash_g(DkParameter &)
0x100445862  mov     eax, 1
0x100445867  jmp     short loc_100445870
0x100445869  call    ?CmdLineParamProcessDash_g@@YAXAEAVDkParameter@@@Z; CmdLineParamProcessDash_g(DkParameter &)
0x10044586e  xor     eax, eax
0x100445870  add     rsp, 0B8h
0x100445877  pop     rdi
0x100445878  pop     rsi
0x100445879  retn
```
