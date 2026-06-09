# CDownloadManager::HttpReadDataSuccess(ITSAsyncResult *,unsigned __int64)

- ea: `0x18005af00`
- end: `0x18005b413`
- name: `?HttpReadDataSuccess@CDownloadManager@@MEAAJPEAVITSAsyncResult@@_K@Z`
- size: `1299`
- prototype: `__int64 __fastcall(CDownloadManager *this, struct ITSAsyncResult *, __int64)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops`

## callees

- `0x180003108`
- `0x180003136`
- `0x18000b1d8`
- `0x18000d8d4`
- `0x18000ec54`
- `0x18000ec94`
- `0x18000ece0`
- `0x18001e5d8`
- `0x180020964`
- `0x180059088`
- `0x18005a284`
- `0x18005af00`
- `0x18005be94`
- `0x18005d018`
- `0x18005f560`
- `0x18009a520`

## import_xrefs

- `msvcrt!free` at `0x18005b1a9`
- `msvcrt!free` at `0x18005b1a9`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18005b3e0`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18005b3e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b216`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b24f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b28e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b216`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b24f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b28e`
- `KERNEL32!CreateFileW` at `0x18005b1e9`
- `KERNEL32!CreateFileW` at `0x18005b1e9`
- `KERNEL32!WriteFile` at `0x18005b284`
- `KERNEL32!WriteFile` at `0x18005b284`

## pseudocode

```c
__int64 __fastcall CDownloadManager::HttpReadDataSuccess(CDownloadManager *this, struct ITSAsyncResult *a2, __int64 a3)
{
  _BYTE *v5; // r15
  PVOID *v6; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v8; // edx
  int v9; // ecx
  signed int v10; // edi
  unsigned int v11; // eax
  int v12; // edx
  const char *v13; // rcx
  __int64 v14; // rsi
  __int64 v15; // rbx
  int v16; // edi
  __int64 v17; // rbx
  _BYTE *v18; // rax
  unsigned int v19; // eax
  HANDLE FileW; // rax
  const WCHAR *v21; // rax
  signed int LastError; // eax
  unsigned int v23; // ebx
  unsigned int v24; // eax
  signed int v25; // eax
  unsigned int v26; // eax
  bool v27; // sf
  unsigned int v28; // eax
  __int64 v29; // rbx
  DWORD dwFlagsAndAttributes[2]; // [rsp+30h] [rbp-D8h]
  DWORD NumberOfBytesWritten[2]; // [rsp+48h] [rbp-C0h] BYREF
  _BYTE *v33; // [rsp+50h] [rbp-B8h]
  _BYTE *v34; // [rsp+58h] [rbp-B0h]
  __int64 v35; // [rsp+60h] [rbp-A8h]
  _BYTE v36[32]; // [rsp+68h] [rbp-A0h] BYREF
  _BYTE v37[32]; // [rsp+88h] [rbp-80h] BYREF
  void *Block; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE v39[264]; // [rsp+B0h] [rbp-58h] BYREF

  v35 = -2;
  NumberOfBytesWritten[0] = 0;
  v5 = 0;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      98,
      &WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
      CurrentThreadActivityIdPrefix);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  v8 = *(_DWORD *)(a3 + 144);
  v9 = *(_DWORD *)(a3 + 152);
  if ( v8 )
  {
    if ( v9 )
    {
      v18 = operator new[]((unsigned int)(v8 + 1), (const struct std::nothrow_t *)&std::nothrow);
      v5 = v18;
      if ( !v18 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v19 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            101,
            &WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
            v19,
            -2147024882);
        }
        v10 = -2147024882;
        goto LABEL_63;
      }
      memcpy_0(v18, *(const void **)(a3 + 136), *(unsigned int *)(a3 + 144));
      v5[*(unsigned int *)(a3 + 144)] = 0;
      Block = v39;
      ATL::CA2WEX<128>::Init(&Block, v5, 3);
      std::wstring::append((char *)this + 1984, Block);
      if ( Block != v39 )
        free(Block);
    }
    else
    {
      FileW = *(HANDLE *)(a3 + 112);
      if ( !FileW )
      {
        v21 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3 + 80);
        FileW = CreateFileW(v21, 0x40000000u, 4u, 0, 4u, 1u, 0);
        *(_QWORD *)(a3 + 112) = FileW;
        if ( FileW == (HANDLE)-1LL )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            LastError = GetLastError();
            v23 = LastError;
            if ( LastError > 0 )
              v23 = (unsigned __int16)LastError | 0x80070000;
            v24 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              102,
              &WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
              v24,
              v23);
          }
          v25 = GetLastError();
          v10 = v25;
          if ( v25 > 0 )
            v10 = (unsigned __int16)v25 | 0x80070000;
          goto LABEL_62;
        }
      }
      if ( !WriteFile(FileW, *(LPCVOID *)(a3 + 136), *(_DWORD *)(a3 + 144), NumberOfBytesWritten, 0) )
      {
        v10 = GetLastError();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v26 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            103,
            &WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
            v26,
            v10);
        }
        v27 = v10 < 0;
        if ( v10 > 0 )
        {
          v10 = (unsigned __int16)v10 | 0x80070000;
          v27 = v10 < 0;
        }
        if ( v27 )
          goto LABEL_62;
        v10 = -2147467259;
        goto LABEL_63;
      }
      if ( NumberOfBytesWritten[0] != *(_DWORD *)(a3 + 144) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v28 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            104,
            &WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
            v28,
            -2147418113);
        }
        v10 = -2147418113;
        goto LABEL_63;
      }
      *(_DWORD *)(a3 + 148) += NumberOfBytesWritten[0];
    }
    v10 = CDownloadManager::CallQueryData(this, (struct _DM_CONTEXT *)a3);
    if ( v10 >= 0 )
    {
      v10 = 0;
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = RdpWppGetCurrentThreadActivityIdPrefix();
      v12 = 105;
      v13 = "CallQueryData failed";
      goto LABEL_12;
    }
LABEL_62:
    if ( v10 >= 0 )
      goto LABEL_64;
    goto LABEL_63;
  }
  if ( v9 )
  {
    v10 = CDownloadManager::FinishCredFetch(this, (struct _DM_CONTEXT *)a3);
    if ( v10 >= 0 )
      return 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = RdpWppGetCurrentThreadActivityIdPrefix();
      v12 = 99;
      v13 = "FinishCredFetch failed";
LABEL_12:
      dwFlagsAndAttributes[0] = v10;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v12,
        (unsigned int)&WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
        v11,
        (__int64)v13,
        *(_QWORD *)dwFlagsAndAttributes);
      goto LABEL_62;
    }
    goto LABEL_62;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 4u )
  {
    v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3 + 80);
    v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3 + 48);
    v16 = *(_DWORD *)(a3 + 148);
    RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DdSS(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, v15, v14);
  }
  if ( *(_DWORD *)(a3 + 148) )
  {
    v10 = 0;
    v33 = v36;
    v17 = std::wstring::wstring(v36, a3 + 80);
    v34 = v37;
    std::wstring::wstring(v37, a3 + 48);
    CDownloadManager::ReportDownloadStatus(this, v17);
    return (unsigned int)v10;
  }
  v10 = -2147220985;
LABEL_63:
  v34 = v37;
  v29 = std::wstring::wstring(v37, a3 + 80);
  v33 = v36;
  std::wstring::wstring(v36, a3 + 48);
  CDownloadManager::ReportDownloadStatus(this, v29);
LABEL_64:
  if ( v5 )
    operator delete[](v5);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18005af00  mov     rax, rsp
0x18005af03  push    rbp
0x18005af04  push    rdi
0x18005af05  push    r13
0x18005af07  push    r14
0x18005af09  push    r15
0x18005af0b  lea     rbp, [rax-0E8h]
0x18005af12  sub     rsp, 1C0h
0x18005af19  mov     [rsp+1E0h+var_188], 0FFFFFFFFFFFFFFFEh
0x18005af22  mov     [rax+10h], rbx
0x18005af26  mov     [rax+20h], rsi
0x18005af2a  mov     rax, cs:__security_cookie
0x18005af31  xor     rax, rsp
0x18005af34  mov     [rbp+0E0h+var_30], rax
0x18005af3b  mov     r14, r8
0x18005af3e  mov     r13, rcx
0x18005af41  mov     [rsp+1E0h+NumberOfBytesWritten], 0
0x18005af49  xor     r15d, r15d
0x18005af4c  lea     rbx, WPP_GLOBAL_Control
0x18005af53  lea     edi, [r15+4]
0x18005af57  lea     rsi, WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids
0x18005af5e  mov     rax, cs:WPP_GLOBAL_Control
0x18005af65  cmp     rax, rbx
0x18005af68  jz      short loc_18005AF9B
0x18005af6a  test    byte ptr [rax+1Ch], 1
0x18005af6e  jz      short loc_18005AF9B
0x18005af70  cmp     [rax+19h], dil
0x18005af74  jb      short loc_18005AF9B
0x18005af76  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005af7b  lea     edx, [rdi+5Eh]
0x18005af7e  mov     r9d, eax
0x18005af81  mov     r8, rsi
0x18005af84  mov     rcx, cs:WPP_GLOBAL_Control
0x18005af8b  mov     rcx, [rcx+10h]
0x18005af8f  call    WPP_SF_D
0x18005af94  mov     rax, cs:WPP_GLOBAL_Control
0x18005af9b  mov     edx, [r14+90h]
0x18005afa2  mov     ecx, [r14+98h]
0x18005afa9  test    edx, edx
0x18005afab  jnz     loc_18005B0E2
0x18005afb1  test    ecx, ecx
0x18005afb3  jz      short loc_18005B026
0x18005afb5  mov     rdx, r14; struct _DM_CONTEXT *
0x18005afb8  mov     rcx, r13; this
0x18005afbb  call    ?FinishCredFetch@CDownloadManager@@IEAAJPEAU_DM_CONTEXT@@@Z; CDownloadManager::FinishCredFetch(_DM_CONTEXT *)
0x18005afc0  mov     edi, eax
0x18005afc2  test    eax, eax
0x18005afc4  jns     short loc_18005B01F
0x18005afc6  mov     rax, cs:WPP_GLOBAL_Control
0x18005afcd  cmp     rax, rbx
0x18005afd0  jz      loc_18005B38D
0x18005afd6  test    byte ptr [rax+1Ch], 8
0x18005afda  jz      loc_18005B38D
0x18005afe0  cmp     byte ptr [rax+19h], 2
0x18005afe4  jb      loc_18005B38D
0x18005afea  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005afef  mov     edx, 63h ; 'c'
0x18005aff4  lea     rcx, aFinishcredfetc; "FinishCredFetch failed"
0x18005affb  mov     [rsp+1E0h+dwFlagsAndAttributes], edi
0x18005afff  mov     qword ptr [rsp+1E0h+dwCreationDisposition], rcx
0x18005b004  mov     r9d, eax
0x18005b007  mov     r8, rsi
0x18005b00a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b011  mov     rcx, [rcx+10h]
0x18005b015  call    WPP_SF_DsD
0x18005b01a  jmp     loc_18005B38D
0x18005b01f  xor     edi, edi
0x18005b021  jmp     loc_18005B3E6
0x18005b026  cmp     rax, rbx
0x18005b029  jz      short loc_18005B081
0x18005b02b  test    byte ptr [rax+1Ch], 1
0x18005b02f  jz      short loc_18005B081
0x18005b031  cmp     [rax+19h], dil
0x18005b035  jb      short loc_18005B081
0x18005b037  lea     rcx, [r14+50h]
0x18005b03b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005b040  mov     rsi, rax
0x18005b043  lea     rcx, [r14+30h]
0x18005b047  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005b04c  mov     rbx, rax
0x18005b04f  mov     edi, [r14+94h]
0x18005b056  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005b05b  mov     edx, 64h ; 'd'
0x18005b060  mov     [rsp+1E0h+hTemplateFile], rsi; __int64
0x18005b065  mov     qword ptr [rsp+1E0h+dwFlagsAndAttributes], rbx; __int64
0x18005b06a  mov     [rsp+1E0h+dwCreationDisposition], edi; char
0x18005b06e  mov     r9d, eax
0x18005b071  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b078  mov     rcx, [rcx+10h]; LoggerHandle
0x18005b07c  call    WPP_SF_DdSS
0x18005b081  cmp     [r14+94h], r15d
0x18005b088  jbe     short loc_18005B0D8
0x18005b08a  xor     edi, edi
0x18005b08c  lea     rax, [rsp+1E0h+var_180]
0x18005b091  mov     [rsp+1E0h+var_198], rax
0x18005b096  lea     rdx, [r14+50h]
0x18005b09a  lea     rcx, [rsp+1E0h+var_180]
0x18005b09f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18005b0a4  mov     rbx, rax
0x18005b0a7  lea     rax, [rbp+0E0h+var_160]
0x18005b0ab  mov     [rsp+1E0h+var_190], rax
0x18005b0b0  lea     rdx, [r14+30h]
0x18005b0b4  lea     rcx, [rbp+0E0h+var_160]
0x18005b0b8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18005b0bd  nop
0x18005b0be  mov     qword ptr [rsp+1E0h+dwCreationDisposition], rbx; __int64
0x18005b0c3  mov     r9, rax
0x18005b0c6  mov     r8, r14
0x18005b0c9  xor     edx, edx
0x18005b0cb  mov     rcx, r13; this
0x18005b0ce  call    ?ReportDownloadStatus@CDownloadManager@@IEAAXJPEAU_DM_CONTEXT@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; CDownloadManager::ReportDownloadStatus(long,_DM_CONTEXT *,std::wstring,std::wstring)
0x18005b0d3  jmp     loc_18005B3E6
0x18005b0d8  mov     edi, 80040207h
0x18005b0dd  jmp     loc_18005B391
0x18005b0e2  test    ecx, ecx
0x18005b0e4  jz      loc_18005B1B4
0x18005b0ea  lea     ecx, [rdx+1]; unsigned __int64
0x18005b0ed  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005b0f4  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18005b0f9  mov     r15, rax
0x18005b0fc  test    rax, rax
0x18005b0ff  jnz     short loc_18005B14A
0x18005b101  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b108  cmp     rcx, rbx
0x18005b10b  jz      short loc_18005B140
0x18005b10d  test    byte ptr [rcx+1Ch], 8
0x18005b111  jz      short loc_18005B140
0x18005b113  cmp     byte ptr [rcx+19h], 2
0x18005b117  jb      short loc_18005B140
0x18005b119  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005b11e  lea     edx, [r15+65h]
0x18005b122  mov     [rsp+1E0h+dwCreationDisposition], 8007000Eh
0x18005b12a  mov     r9d, eax
0x18005b12d  mov     r8, rsi
0x18005b130  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b137  mov     rcx, [rcx+10h]
0x18005b13b  call    WPP_SF_Dd
0x18005b140  mov     edi, 8007000Eh
0x18005b145  jmp     loc_18005B391
0x18005b14a  mov     r8d, [r14+90h]; Size
0x18005b151  mov     rdx, [r14+88h]; Src
0x18005b158  mov     rcx, r15; void *
0x18005b15b  call    memcpy_0
0x18005b160  mov     eax, [r14+90h]
0x18005b167  mov     byte ptr [rax+r15], 0
0x18005b16c  lea     rax, [rbp+0E0h+var_138]
0x18005b170  mov     [rbp+0E0h+Block], rax
0x18005b174  mov     r8d, 3
0x18005b17a  mov     rdx, r15
0x18005b17d  lea     rcx, [rbp+0E0h+Block]
0x18005b181  call    ?Init@?$CA2WEX@$0IA@@ATL@@AEAAXPEBDI@Z; ATL::CA2WEX<128>::Init(char const *,uint)
0x18005b186  nop
0x18005b187  lea     rcx, [r13+7C0h]
0x18005b18e  mov     rdx, [rbp+0E0h+Block]
0x18005b192  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18005b197  nop
0x18005b198  mov     rcx, [rbp+0E0h+Block]; Block
0x18005b19c  lea     rax, [rbp+0E0h+var_138]
0x18005b1a0  cmp     rcx, rax
0x18005b1a3  jz      loc_18005B34C
0x18005b1a9  call    cs:__imp_free
0x18005b1af  jmp     loc_18005B34C
0x18005b1b4  mov     rax, [r14+70h]
0x18005b1b8  test    rax, rax
0x18005b1bb  jnz     loc_18005B269
0x18005b1c1  lea     rcx, [r14+50h]
0x18005b1c5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005b1ca  mov     [rsp+1E0h+hTemplateFile], r15; hTemplateFile
0x18005b1cf  mov     [rsp+1E0h+dwFlagsAndAttributes], 1; dwFlagsAndAttributes
0x18005b1d7  mov     [rsp+1E0h+dwCreationDisposition], edi; dwCreationDisposition
0x18005b1db  xor     r9d, r9d; lpSecurityAttributes
0x18005b1de  mov     r8d, edi; dwShareMode
0x18005b1e1  mov     edx, 40000000h; dwDesiredAccess
0x18005b1e6  mov     rcx, rax; lpFileName
0x18005b1e9  call    cs:__imp_CreateFileW
0x18005b1ef  mov     [r14+70h], rax
0x18005b1f3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005b1f7  jnz     short loc_18005B269
0x18005b1f9  mov     esi, 80070000h
0x18005b1fe  mov     rax, cs:WPP_GLOBAL_Control
0x18005b205  cmp     rax, rbx
0x18005b208  jz      short loc_18005B24F
0x18005b20a  test    byte ptr [rax+1Ch], 8
0x18005b20e  jz      short loc_18005B24F
0x18005b210  cmp     byte ptr [rax+19h], 2
0x18005b214  jb      short loc_18005B24F
0x18005b216  call    cs:__imp_GetLastError
0x18005b21c  mov     ebx, eax
0x18005b21e  test    eax, eax
0x18005b220  jle     short loc_18005B227
0x18005b222  movzx   ebx, ax
0x18005b225  or      ebx, esi
0x18005b227  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005b22c  mov     edx, 66h ; 'f'
0x18005b231  mov     [rsp+1E0h+dwCreationDisposition], ebx
0x18005b235  mov     r9d, eax
0x18005b238  lea     r8, WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids
0x18005b23f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b246  mov     rcx, [rcx+10h]
0x18005b24a  call    WPP_SF_Dd
0x18005b24f  call    cs:__imp_GetLastError
0x18005b255  mov     edi, eax
0x18005b257  test    eax, eax
0x18005b259  jle     loc_18005B38D
0x18005b25f  movzx   edi, ax
0x18005b262  or      edi, esi
0x18005b264  jmp     loc_18005B38D
0x18005b269  mov     qword ptr [rsp+1E0h+dwCreationDisposition], r15; lpOverlapped
0x18005b26e  lea     r9, [rsp+1E0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18005b273  mov     r8d, [r14+90h]; nNumberOfBytesToWrite
0x18005b27a  mov     rdx, [r14+88h]; lpBuffer
0x18005b281  mov     rcx, rax; hFile
0x18005b284  call    cs:__imp_WriteFile
0x18005b28a  test    eax, eax
0x18005b28c  jnz     short loc_18005B2F1
0x18005b28e  call    cs:__imp_GetLastError
0x18005b294  mov     edi, eax
0x18005b296  mov     rax, cs:WPP_GLOBAL_Control
0x18005b29d  cmp     rax, rbx
0x18005b2a0  jz      short loc_18005B2D2
0x18005b2a2  test    byte ptr [rax+1Ch], 8
0x18005b2a6  jz      short loc_18005B2D2
0x18005b2a8  cmp     byte ptr [rax+19h], 2
0x18005b2ac  jb      short loc_18005B2D2
0x18005b2ae  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005b2b3  mov     edx, 67h ; 'g'
0x18005b2b8  mov     [rsp+1E0h+dwCreationDisposition], edi
0x18005b2bc  mov     r9d, eax
0x18005b2bf  mov     r8, rsi
0x18005b2c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b2c9  mov     rcx, [rcx+10h]
0x18005b2cd  call    WPP_SF_Dd
0x18005b2d2  test    edi, edi
0x18005b2d4  jle     short loc_18005B2E1
0x18005b2d6  movzx   edi, di
0x18005b2d9  or      edi, 80070000h
0x18005b2df  test    edi, edi
0x18005b2e1  js      loc_18005B38D
0x18005b2e7  mov     edi, 80004005h
0x18005b2ec  jmp     loc_18005B391
0x18005b2f1  mov     eax, [rsp+1E0h+NumberOfBytesWritten]
0x18005b2f5  cmp     eax, [r14+90h]
0x18005b2fc  jz      short loc_18005B345
0x18005b2fe  mov     rax, cs:WPP_GLOBAL_Control
0x18005b305  cmp     rax, rbx
0x18005b308  jz      short loc_18005B33E
0x18005b30a  test    byte ptr [rax+1Ch], 8
0x18005b30e  jz      short loc_18005B33E
0x18005b310  cmp     byte ptr [rax+19h], 2
0x18005b314  jb      short loc_18005B33E
0x18005b316  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005b31b  mov     edx, 68h ; 'h'
0x18005b320  mov     [rsp+1E0h+dwCreationDisposition], 8000FFFFh
0x18005b328  mov     r9d, eax
0x18005b32b  mov     r8, rsi
0x18005b32e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b335  mov     rcx, [rcx+10h]
0x18005b339  call    WPP_SF_Dd
0x18005b33e  mov     edi, 8000FFFFh
0x18005b343  jmp     short loc_18005B391
0x18005b345  add     [r14+94h], eax
0x18005b34c  mov     rdx, r14; struct _DM_CONTEXT *
0x18005b34f  mov     rcx, r13; this
0x18005b352  call    ?CallQueryData@CDownloadManager@@IEAAJPEAU_DM_CONTEXT@@@Z; CDownloadManager::CallQueryData(_DM_CONTEXT *)
0x18005b357  mov     edi, eax
0x18005b359  test    eax, eax
0x18005b35b  jns     short loc_18005B38B
0x18005b35d  mov     rax, cs:WPP_GLOBAL_Control
0x18005b364  cmp     rax, rbx
0x18005b367  jz      short loc_18005B38D
0x18005b369  test    byte ptr [rax+1Ch], 8
0x18005b36d  jz      short loc_18005B38D
0x18005b36f  cmp     byte ptr [rax+19h], 2
0x18005b373  jb      short loc_18005B38D
0x18005b375  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005b37a  mov     edx, 69h ; 'i'
0x18005b37f  lea     rcx, aCallquerydataF; "CallQueryData failed"
0x18005b386  jmp     loc_18005AFFB
0x18005b38b  xor     edi, edi
0x18005b38d  test    edi, edi
0x18005b38f  jns     short loc_18005B3D8
0x18005b391  lea     rax, [rbp+0E0h+var_160]
0x18005b395  mov     [rsp+1E0h+var_190], rax
0x18005b39a  lea     rdx, [r14+50h]
0x18005b39e  lea     rcx, [rbp+0E0h+var_160]
0x18005b3a2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18005b3a7  mov     rbx, rax
0x18005b3aa  lea     rax, [rsp+1E0h+var_180]
0x18005b3af  mov     [rsp+1E0h+var_198], rax
0x18005b3b4  lea     rdx, [r14+30h]
0x18005b3b8  lea     rcx, [rsp+1E0h+var_180]
0x18005b3bd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18005b3c2  nop
0x18005b3c3  mov     qword ptr [rsp+1E0h+dwCreationDisposition], rbx; __int64
0x18005b3c8  mov     r9, rax
0x18005b3cb  mov     r8, r14
0x18005b3ce  mov     edx, edi
0x18005b3d0  mov     rcx, r13; this
0x18005b3d3  call    ?ReportDownloadStatus@CDownloadManager@@IEAAXJPEAU_DM_CONTEXT@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; CDownloadManager::ReportDownloadStatus(long,_DM_CONTEXT *,std::wstring,std::wstring)
0x18005b3d8  test    r15, r15
  ... truncated ...
```
