# ExportLogCommand::Init(void)

- ea: `0x14001cfd0`
- end: `0x14001d383`
- name: `?Init@ExportLogCommand@@UEAAXXZ`
- size: `947`
- prototype: `void __fastcall(ExportLogCommand *__hidden this)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callees

- `0x14000ebbc`
- `0x140010450`
- `0x140011a38`
- `0x140011bbc`
- `0x1400163cc`
- `0x1400165a4`
- `0x14001cfd0`
- `0x14001d38c`
- `0x140022cec`
- `0x14002445c`
- `0x1400247c8`
- `0x140024b00`
- `0x140031810`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14001d37c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14001cff5`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14001cff5`

## string_xrefs

- `0x14001d1cb`: `overwrite`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ExportLogCommand::Init(CommandArguments **this)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  wchar_t **v4; // rbx
  __int64 Argument; // rax
  __int64 v6; // rax
  __int64 v7; // r9
  __int64 v8; // r9
  __int64 v9; // r9
  wchar_t *v10; // rcx
  char *v11; // [rsp+20h] [rbp-39h]
  char *v12; // [rsp+20h] [rbp-39h]
  __int128 v13; // [rsp+40h] [rbp-19h] BYREF
  __int128 v14; // [rsp+50h] [rbp-9h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+60h] [rbp+7h] BYREF
  char v16; // [rsp+C8h] [rbp+6Fh] BYREF
  char v17; // [rsp+D1h] [rbp+78h]

  v2 = CoInitializeEx(0, 0);
  v3 = v2;
  if ( v2 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_86b388a84c2d3f26078be78498fb4b90_Traceguids,
        (unsigned int)v2);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, v3, 0, 0, v11, 23, 3u, 0);
    throw (EvtException *)pExceptionObject;
  }
  v17 = 1;
  CommandArguments::ValidateArgumentCount(this[1], 3u);
  *(_QWORD *)&v13 = off_140042030;
  *((_QWORD *)&v13 + 1) = 8;
  CommandArguments::ValidateOptions((__int64 ***)this[1], (__int64)&v13);
  v4 = (wchar_t **)(this + 5);
  Argument = CommandArguments::GetArgument(this[1], 1);
  std::wstring::operator=(this + 5, Argument);
  v6 = CommandArguments::GetArgument(this[1], 2);
  std::wstring::operator=(this + 13, v6);
  *(_QWORD *)&v13 = L"q";
  *((_QWORD *)&v13 + 1) = 1;
  *(_QWORD *)&v14 = L"query";
  *((_QWORD *)&v14 + 1) = 5;
  CommandArguments::GetOptionString(
    (unsigned int)this[1],
    (unsigned int)&v14,
    (unsigned int)&v13,
    (unsigned int)L"*",
    (__int64)&v16);
  std::wstring::assign(this + 9);
  *(_QWORD *)&v14 = L"lf";
  *((_QWORD *)&v14 + 1) = 2;
  *(_QWORD *)&v13 = L"logfile";
  *((_QWORD *)&v13 + 1) = 7;
  *((_BYTE *)this + 136) = CommandArguments::GetOptionBool(this[1], &v13, &v14, v7, &v16);
  *(_QWORD *)&v14 = L"sq";
  *((_QWORD *)&v14 + 1) = 2;
  *(_QWORD *)&v13 = L"structuredquery";
  *((_QWORD *)&v13 + 1) = 15;
  *((_BYTE *)this + 137) = CommandArguments::GetOptionBool(this[1], &v13, &v14, v8, &v16);
  *(_QWORD *)&v14 = L"ow";
  *((_QWORD *)&v14 + 1) = 2;
  *(_QWORD *)&v13 = L"overwrite";
  *((_QWORD *)&v13 + 1) = 9;
  *((_BYTE *)this + 138) = CommandArguments::GetOptionBool(this[1], &v13, &v14, v9, &v16);
  if ( *((_BYTE *)this + 137) )
  {
    *(_QWORD *)&v14 = L"q";
    *((_QWORD *)&v14 + 1) = 1;
    *(_QWORD *)&v13 = L"query";
    *((_QWORD *)&v13 + 1) = 5;
    if ( (unsigned __int8)CommandArguments::HasOption(this[1], &v13, &v14) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_86b388a84c2d3f26078be78498fb4b90_Traceguids, 87);
      }
      EvtException::EvtException((EvtException *)pExceptionObject, 0x57u, 0, 0, v12, 42, 0x30u, 0);
      throw (EvtException *)pExceptionObject;
    }
    if ( *((_BYTE *)this + 136) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_86b388a84c2d3f26078be78498fb4b90_Traceguids, 87);
      }
      EvtException::EvtException((EvtException *)pExceptionObject, 0x57u, 0, 0, v12, 47, 0xEu, 0);
      throw (EvtException *)pExceptionObject;
    }
    if ( (unsigned __int64)this[8] <= 7 )
      v10 = (wchar_t *)(this + 5);
    else
      v10 = *v4;
    ReadTextFile(v10, (__int64)(this + 9));
    this[7] = 0;
    if ( (unsigned __int64)this[8] > 7 )
      v4 = (wchar_t **)*v4;
    *(_WORD *)v4 = 0;
  }
  CoUninitialize();
}

```

## disassembly

```asm
0x14001cfd0  mov     [rsp-8+arg_0], rbx
0x14001cfd5  mov     [rsp-8+arg_18], rsi
0x14001cfda  push    rbp
0x14001cfdb  push    rdi
0x14001cfdc  push    r12
0x14001cfde  push    r13
0x14001cfe0  push    r14
0x14001cfe2  lea     rbp, [rsp-37h]
0x14001cfe7  sub     rsp, 90h
0x14001cfee  mov     rsi, rcx
0x14001cff1  xor     edx, edx; dwCoInit
0x14001cff3  xor     ecx, ecx; pvReserved
0x14001cff5  call    cs:__imp_CoInitializeEx
0x14001cffb  mov     ebx, eax
0x14001cffd  test    eax, eax
0x14001cfff  jns     short loc_14001D07A
0x14001d001  lea     rcx, WPP_GLOBAL_Control
0x14001d008  mov     r10, cs:WPP_GLOBAL_Control
0x14001d00f  cmp     r10, rcx
0x14001d012  jz      short loc_14001D03F
0x14001d014  test    dword ptr [r10+1Ch], 400000h
0x14001d01c  jz      short loc_14001D03F
0x14001d01e  mov     edi, 2
0x14001d023  cmp     [r10+19h], dil
0x14001d027  jb      short loc_14001D03F
0x14001d029  lea     edx, [rdi+8]
0x14001d02c  mov     r9d, eax
0x14001d02f  lea     r8, WPP_86b388a84c2d3f26078be78498fb4b90_Traceguids
0x14001d036  mov     rcx, [r10+10h]
0x14001d03a  call    WPP_SF_d
0x14001d03f  mov     [rsp+0B0h+Src], 0; Src
0x14001d048  mov     [rsp+0B0h+var_80], 3; unsigned int
0x14001d050  mov     [rsp+0B0h+var_88], 17h; int
0x14001d058  xor     r9d, r9d; unsigned int
0x14001d05b  xor     r8d, r8d; unsigned int
0x14001d05e  mov     edx, ebx; unsigned int
0x14001d060  lea     rcx, [rbp+57h+pExceptionObject]; this
0x14001d064  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14001d069  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14001d070  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14001d074  call    _CxxThrowException_0
0x14001d07a  mov     r12d, 1
0x14001d080  mov     [rbp+57h+arg_11], r12b
0x14001d084  lea     edx, [r12+2]; unsigned __int64
0x14001d089  mov     rcx, [rsi+8]; this
0x14001d08d  call    ?ValidateArgumentCount@CommandArguments@@QEBAX_K@Z; CommandArguments::ValidateArgumentCount(unsigned __int64)
0x14001d092  lea     rax, off_140042030; "logfile"
0x14001d099  mov     [rbp+57h+var_70], rax
0x14001d09d  mov     [rbp+57h+var_68], 8
0x14001d0a5  lea     rdx, [rbp+57h+var_70]
0x14001d0a9  mov     rcx, [rsi+8]
0x14001d0ad  call    ?ValidateOptions@CommandArguments@@QEBAXV?$span@PEB_W$0?0@utl@@@Z; CommandArguments::ValidateOptions(utl::span<wchar_t const *,-1>)
0x14001d0b2  lea     rbx, [rsi+28h]
0x14001d0b6  mov     edx, r12d
0x14001d0b9  mov     rcx, [rsi+8]
0x14001d0bd  call    ?GetArgument@CommandArguments@@QEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@Z; CommandArguments::GetArgument(unsigned __int64)
0x14001d0c2  mov     rdx, rax
0x14001d0c5  mov     rcx, rbx
0x14001d0c8  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14001d0cd  lea     edi, [r12+1]
0x14001d0d2  mov     edx, edi
0x14001d0d4  mov     rcx, [rsi+8]
0x14001d0d8  call    ?GetArgument@CommandArguments@@QEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@Z; CommandArguments::GetArgument(unsigned __int64)
0x14001d0dd  mov     rdx, rax
0x14001d0e0  lea     rcx, [rsi+68h]
0x14001d0e4  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14001d0e9  lea     r13, aQ; "q"
0x14001d0f0  mov     [rbp+57h+var_70], r13
0x14001d0f4  mov     [rbp+57h+var_68], r12
0x14001d0f8  lea     rax, aQuery; "query"
0x14001d0ff  mov     [rbp+57h+var_60], rax
0x14001d103  mov     [rbp+57h+var_58], 5
0x14001d10b  lea     rax, [rbp+57h+arg_8]
0x14001d10f  mov     [rsp+0B0h+var_90], rax
0x14001d114  lea     r9, asc_14003879C; "*"
0x14001d11b  lea     r8, [rbp+57h+var_70]
0x14001d11f  lea     rdx, [rbp+57h+var_60]
0x14001d123  mov     rcx, [rsi+8]
0x14001d127  call    ?GetOptionString@CommandArguments@@QEBAPEB_WV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0PEB_WAEA_N@Z; CommandArguments::GetOptionString(std::wstring_view,std::wstring_view,wchar_t const *,bool &)
0x14001d12c  mov     rdx, rax
0x14001d12f  lea     rcx, [rsi+48h]
0x14001d133  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x14001d138  lea     rax, aLf; "lf"
0x14001d13f  mov     [rbp+57h+var_60], rax
0x14001d143  mov     [rbp+57h+var_58], rdi
0x14001d147  lea     rax, aLogfile; "logfile"
0x14001d14e  mov     [rbp+57h+var_70], rax
0x14001d152  mov     [rbp+57h+var_68], 7
0x14001d15a  lea     rax, [rbp+57h+arg_8]
0x14001d15e  mov     [rsp+0B0h+var_90], rax
0x14001d163  lea     r8, [rbp+57h+var_60]
0x14001d167  lea     rdx, [rbp+57h+var_70]
0x14001d16b  mov     rcx, [rsi+8]
0x14001d16f  call    ?GetOptionBool@CommandArguments@@QEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0_NAEA_N@Z; CommandArguments::GetOptionBool(std::wstring_view,std::wstring_view,bool,bool &)
0x14001d174  mov     [rsi+88h], al
0x14001d17a  lea     rax, aSq; "sq"
0x14001d181  mov     [rbp+57h+var_60], rax
0x14001d185  mov     [rbp+57h+var_58], rdi
0x14001d189  lea     rax, aStructuredquer; "structuredquery"
0x14001d190  mov     [rbp+57h+var_70], rax
0x14001d194  mov     [rbp+57h+var_68], 0Fh
0x14001d19c  lea     rax, [rbp+57h+arg_8]
0x14001d1a0  mov     [rsp+0B0h+var_90], rax
0x14001d1a5  lea     r8, [rbp+57h+var_60]
0x14001d1a9  lea     rdx, [rbp+57h+var_70]
0x14001d1ad  mov     rcx, [rsi+8]
0x14001d1b1  call    ?GetOptionBool@CommandArguments@@QEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0_NAEA_N@Z; CommandArguments::GetOptionBool(std::wstring_view,std::wstring_view,bool,bool &)
0x14001d1b6  mov     [rsi+89h], al
0x14001d1bc  lea     rax, aOw; "ow"
0x14001d1c3  mov     [rbp+57h+var_60], rax
0x14001d1c7  mov     [rbp+57h+var_58], rdi
0x14001d1cb  lea     rax, aOverwrite; "overwrite"
0x14001d1d2  mov     [rbp+57h+var_70], rax
0x14001d1d6  mov     [rbp+57h+var_68], 9
0x14001d1de  lea     rax, [rbp+57h+arg_8]
0x14001d1e2  mov     [rsp+0B0h+var_90], rax; char *
0x14001d1e7  lea     r8, [rbp+57h+var_60]
0x14001d1eb  lea     rdx, [rbp+57h+var_70]
0x14001d1ef  mov     rcx, [rsi+8]
0x14001d1f3  call    ?GetOptionBool@CommandArguments@@QEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0_NAEA_N@Z; CommandArguments::GetOptionBool(std::wstring_view,std::wstring_view,bool,bool &)
0x14001d1f8  mov     [rsi+8Ah], al
0x14001d1fe  cmp     byte ptr [rsi+89h], 0
0x14001d205  jz      loc_14001D361
0x14001d20b  mov     [rbp+57h+var_60], r13
0x14001d20f  mov     [rbp+57h+var_58], r12
0x14001d213  lea     rax, aQuery; "query"
0x14001d21a  mov     [rbp+57h+var_70], rax
0x14001d21e  mov     [rbp+57h+var_68], 5
0x14001d226  lea     r8, [rbp+57h+var_60]
0x14001d22a  lea     rdx, [rbp+57h+var_70]
0x14001d22e  mov     rcx, [rsi+8]
0x14001d232  call    ?HasOption@CommandArguments@@QEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; CommandArguments::HasOption(std::wstring_view,std::wstring_view)
0x14001d237  test    al, al
0x14001d239  jz      short loc_14001D2B1
0x14001d23b  lea     rcx, WPP_GLOBAL_Control
0x14001d242  lea     ebx, [rdi+55h]
0x14001d245  mov     rax, cs:WPP_GLOBAL_Control
0x14001d24c  cmp     rax, rcx
0x14001d24f  jz      short loc_14001D276
0x14001d251  test    dword ptr [rax+1Ch], 400000h
0x14001d258  jz      short loc_14001D276
0x14001d25a  cmp     [rax+19h], dil
0x14001d25e  jb      short loc_14001D276
0x14001d260  lea     edx, [rdi+9]
0x14001d263  mov     r9d, ebx
0x14001d266  lea     r8, WPP_86b388a84c2d3f26078be78498fb4b90_Traceguids
0x14001d26d  mov     rcx, [rax+10h]
0x14001d271  call    WPP_SF_d
0x14001d276  mov     [rsp+0B0h+Src], 0; Src
0x14001d27f  mov     [rsp+0B0h+var_80], 30h ; '0'; unsigned int
0x14001d287  mov     [rsp+0B0h+var_88], 2Ah ; '*'; int
0x14001d28f  xor     r9d, r9d; unsigned int
0x14001d292  xor     r8d, r8d; unsigned int
0x14001d295  mov     edx, ebx; unsigned int
0x14001d297  lea     rcx, [rbp+57h+pExceptionObject]; this
0x14001d29b  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14001d2a0  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14001d2a7  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14001d2ab  call    _CxxThrowException_0
0x14001d2b1  cmp     byte ptr [rsi+88h], 0
0x14001d2b8  jz      short loc_14001D332
0x14001d2ba  lea     rcx, WPP_GLOBAL_Control
0x14001d2c1  mov     ebx, 57h ; 'W'
0x14001d2c6  mov     rax, cs:WPP_GLOBAL_Control
0x14001d2cd  cmp     rax, rcx
0x14001d2d0  jz      short loc_14001D2F7
0x14001d2d2  test    dword ptr [rax+1Ch], 400000h
0x14001d2d9  jz      short loc_14001D2F7
0x14001d2db  cmp     [rax+19h], dil
0x14001d2df  jb      short loc_14001D2F7
0x14001d2e1  lea     edx, [rbx-4Bh]
0x14001d2e4  mov     r9d, ebx
0x14001d2e7  lea     r8, WPP_86b388a84c2d3f26078be78498fb4b90_Traceguids
0x14001d2ee  mov     rcx, [rax+10h]
0x14001d2f2  call    WPP_SF_d
0x14001d2f7  mov     [rsp+0B0h+Src], 0; Src
0x14001d300  mov     [rsp+0B0h+var_80], 0Eh; unsigned int
0x14001d308  mov     [rsp+0B0h+var_88], 2Fh ; '/'; int
0x14001d310  xor     r9d, r9d; unsigned int
0x14001d313  xor     r8d, r8d; unsigned int
0x14001d316  mov     edx, ebx; unsigned int
0x14001d318  lea     rcx, [rbp+57h+pExceptionObject]; this
0x14001d31c  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14001d321  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14001d328  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14001d32c  call    _CxxThrowException_0
0x14001d332  cmp     qword ptr [rbx+18h], 7
0x14001d337  jbe     short loc_14001D33E
0x14001d339  mov     rcx, [rbx]
0x14001d33c  jmp     short loc_14001D341
0x14001d33e  mov     rcx, rbx; Src
0x14001d341  lea     rdx, [rsi+48h]
0x14001d345  call    ?ReadTextFile@@YAXPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; ReadTextFile(wchar_t const *,std::wstring &)
0x14001d34a  mov     qword ptr [rbx+10h], 0
0x14001d352  cmp     qword ptr [rbx+18h], 7
0x14001d357  jbe     short loc_14001D35C
0x14001d359  mov     rbx, [rbx]
0x14001d35c  xor     eax, eax
0x14001d35e  mov     [rbx], ax
0x14001d361  lea     r11, [rsp+0B0h+var_20]
0x14001d369  mov     rbx, [r11+30h]
0x14001d36d  mov     rsi, [r11+48h]
0x14001d371  mov     rsp, r11
0x14001d374  pop     r14
0x14001d376  pop     r13
0x14001d378  pop     r12
0x14001d37a  pop     rdi
0x14001d37b  pop     rbp
0x14001d37c  jmp     cs:__imp_CoUninitialize
```
