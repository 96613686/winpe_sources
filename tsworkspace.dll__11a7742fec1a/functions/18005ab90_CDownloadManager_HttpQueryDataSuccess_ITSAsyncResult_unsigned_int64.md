# CDownloadManager::HttpQueryDataSuccess(ITSAsyncResult *,unsigned __int64)

- ea: `0x18005ab90`
- end: `0x18005aef6`
- name: `?HttpQueryDataSuccess@CDownloadManager@@MEAAJPEAVITSAsyncResult@@_K@Z`
- size: `870`
- prototype: `__int64 __fastcall(CDownloadManager *this, struct ITSAsyncResult *, __int64)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops`

## callees

- `0x180003108`
- `0x18000b1d8`
- `0x18000d8d4`
- `0x18000ec54`
- `0x18000ec94`
- `0x18000ece0`
- `0x180010ba4`
- `0x18001e5d8`
- `0x18005a284`
- `0x18005ab90`
- `0x18005d018`
- `0x18005f560`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18005ad64`
- `msvcrt!??3@YAXPEAX@Z` at `0x18005ad64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ae34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ae34`
- `WINHTTP!WinHttpReadData` at `0x18005ae2a`
- `WINHTTP!WinHttpReadData` at `0x18005ae2a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDownloadManager::HttpQueryDataSuccess(
        CDownloadManager *this,
        struct ITSAsyncResult *a2,
        __int64 a3)
{
  PVOID *v5; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v7; // ecx
  signed int LastError; // edi
  unsigned int v9; // eax
  __int64 v10; // rsi
  __int64 v11; // rbx
  int v12; // edi
  __int64 v13; // rbx
  unsigned int v14; // ebx
  void *v15; // rcx
  unsigned int *v16; // rdi
  void *v17; // rax
  unsigned int v18; // eax
  DWORD v19; // r8d
  unsigned int v20; // eax
  bool v21; // sf
  _BYTE v23[32]; // [rsp+50h] [rbp-11h] BYREF
  _BYTE v24[72]; // [rsp+70h] [rbp+Fh] BYREF

  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      93,
      &WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
      CurrentThreadActivityIdPrefix);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  v7 = *(_DWORD *)(a3 + 128);
  if ( !v7 )
  {
    if ( *(_DWORD *)(a3 + 152) )
    {
      LastError = CDownloadManager::FinishCredFetch(this, (struct _DM_CONTEXT *)a3);
      if ( LastError >= 0 )
        return 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v9 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          94,
          (unsigned int)&WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
          v9,
          (__int64)"FinishCredFetch failed",
          LastError);
      }
      goto LABEL_45;
    }
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 && *((_BYTE *)v5 + 25) >= 4u )
    {
      v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3 + 80);
      v11 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3 + 48);
      v12 = *(_DWORD *)(a3 + 148);
      RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DdSS(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, v11, v10);
    }
    if ( *(_DWORD *)(a3 + 148) )
    {
      LastError = 0;
      v13 = std::wstring::wstring(v23, a3 + 80);
      std::wstring::wstring(v24, a3 + 48);
LABEL_47:
      CDownloadManager::ReportDownloadStatus(this, v13);
      return (unsigned int)LastError;
    }
    LastError = -2147220985;
LABEL_46:
    v13 = std::wstring::wstring(v24, a3 + 80);
    std::wstring::wstring(v23, a3 + 48);
    goto LABEL_47;
  }
  v14 = 0x2000;
  if ( v7 >= 0x2000 )
  {
    v14 = *(_DWORD *)(a3 + 128);
    if ( v7 > 0x80000 )
      v14 = 0x80000;
  }
  v15 = *(void **)(a3 + 136);
  v16 = (unsigned int *)(a3 + 132);
  if ( v15 )
  {
    if ( *v16 >= v14 )
      goto LABEL_33;
    operator delete(v15);
    *(_QWORD *)(a3 + 136) = 0;
    *v16 = 0;
  }
  v17 = operator new[](v14, (const struct std::nothrow_t *)&std::nothrow);
  *(_QWORD *)(a3 + 136) = v17;
  if ( !v17 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v18 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        96,
        (unsigned int)&WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
        v18,
        (__int64)"BYTE");
    }
    LastError = -2147024882;
    goto LABEL_46;
  }
  *v16 = v14;
LABEL_33:
  *(_DWORD *)a3 = g_dwDMObjectContext;
  *(_DWORD *)(a3 + 4) = 3;
  *(_QWORD *)(a3 + 8) = this;
  *(_OWORD *)(a3 + 16) = 0;
  *(_DWORD *)(a3 + 32) = 0;
  v19 = *(_DWORD *)(a3 + 128);
  if ( *v16 <= v19 )
    v19 = *v16;
  if ( WinHttpReadData(*(HINTERNET *)(a3 + 40), *(LPVOID *)(a3 + 136), v19, 0) )
  {
    LastError = 0;
    goto LABEL_45;
  }
  LastError = GetLastError();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v20 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, &WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids, v20, LastError);
  }
  v21 = LastError < 0;
  if ( LastError > 0 )
  {
    LastError = (unsigned __int16)LastError | 0x80070000;
    v21 = LastError < 0;
  }
  if ( !v21 )
  {
    LastError = -2147467259;
    goto LABEL_46;
  }
LABEL_45:
  if ( LastError < 0 )
    goto LABEL_46;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18005ab90  mov     rax, rsp
0x18005ab93  push    rbp
0x18005ab94  push    rsi
0x18005ab95  push    rdi
0x18005ab96  push    r14
0x18005ab98  push    r15
0x18005ab9a  lea     rbp, [rax-5Fh]
0x18005ab9e  sub     rsp, 90h
0x18005aba5  mov     [rbp+57h+var_70], 0FFFFFFFFFFFFFFFEh
0x18005abad  mov     [rax+8], rbx
0x18005abb1  mov     r14, r8
0x18005abb4  mov     r15, rcx
0x18005abb7  lea     rsi, WPP_GLOBAL_Control
0x18005abbe  mov     rax, cs:WPP_GLOBAL_Control
0x18005abc5  cmp     rax, rsi
0x18005abc8  jz      short loc_18005AC01
0x18005abca  test    byte ptr [rax+1Ch], 1
0x18005abce  jz      short loc_18005AC01
0x18005abd0  cmp     byte ptr [rax+19h], 4
0x18005abd4  jb      short loc_18005AC01
0x18005abd6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005abdb  mov     edx, 5Dh ; ']'
0x18005abe0  mov     r9d, eax
0x18005abe3  lea     r8, WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids
0x18005abea  mov     rcx, cs:WPP_GLOBAL_Control
0x18005abf1  mov     rcx, [rcx+10h]
0x18005abf5  call    WPP_SF_D
0x18005abfa  mov     rax, cs:WPP_GLOBAL_Control
0x18005ac01  mov     ecx, [r14+80h]
0x18005ac08  test    ecx, ecx
0x18005ac0a  jnz     loc_18005AD34
0x18005ac10  cmp     [r14+98h], ecx
0x18005ac17  jz      short loc_18005AC8E
0x18005ac19  mov     rdx, r14; struct _DM_CONTEXT *
0x18005ac1c  mov     rcx, r15; this
0x18005ac1f  call    ?FinishCredFetch@CDownloadManager@@IEAAJPEAU_DM_CONTEXT@@@Z; CDownloadManager::FinishCredFetch(_DM_CONTEXT *)
0x18005ac24  mov     edi, eax
0x18005ac26  test    eax, eax
0x18005ac28  jns     short loc_18005AC87
0x18005ac2a  mov     rax, cs:WPP_GLOBAL_Control
0x18005ac31  cmp     rax, rsi
0x18005ac34  jz      loc_18005AE96
0x18005ac3a  test    byte ptr [rax+1Ch], 8
0x18005ac3e  jz      loc_18005AE96
0x18005ac44  cmp     byte ptr [rax+19h], 2
0x18005ac48  jb      loc_18005AE96
0x18005ac4e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005ac53  mov     edx, 5Eh ; '^'
0x18005ac58  mov     dword ptr [rsp+0B0h+var_88], edi
0x18005ac5c  lea     rcx, aFinishcredfetc; "FinishCredFetch failed"
0x18005ac63  mov     qword ptr [rsp+0B0h+var_90], rcx
0x18005ac68  mov     r9d, eax
0x18005ac6b  lea     r8, WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids
0x18005ac72  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ac79  mov     rcx, [rcx+10h]
0x18005ac7d  call    WPP_SF_DsD
0x18005ac82  jmp     loc_18005AE96
0x18005ac87  xor     edi, edi
0x18005ac89  jmp     loc_18005AEDD
0x18005ac8e  cmp     rax, rsi
0x18005ac91  jz      short loc_18005ACE9
0x18005ac93  test    byte ptr [rax+1Ch], 1
0x18005ac97  jz      short loc_18005ACE9
0x18005ac99  cmp     byte ptr [rax+19h], 4
0x18005ac9d  jb      short loc_18005ACE9
0x18005ac9f  lea     rcx, [r14+50h]
0x18005aca3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005aca8  mov     rsi, rax
0x18005acab  lea     rcx, [r14+30h]
0x18005acaf  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005acb4  mov     rbx, rax
0x18005acb7  mov     edi, [r14+94h]
0x18005acbe  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005acc3  mov     edx, 5Fh ; '_'
0x18005acc8  mov     [rsp+30h], rsi; __int64
0x18005accd  mov     [rsp+0B0h+var_88], rbx; __int64
0x18005acd2  mov     dword ptr [rsp+0B0h+var_90], edi; char
0x18005acd6  mov     r9d, eax
0x18005acd9  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ace0  mov     rcx, [rcx+10h]; LoggerHandle
0x18005ace4  call    WPP_SF_DdSS
0x18005ace9  cmp     dword ptr [r14+94h], 0
0x18005acf1  jbe     short loc_18005AD2A
0x18005acf3  xor     edi, edi
0x18005acf5  lea     rax, [rbp+57h+var_68]
0x18005acf9  mov     [rbp+57h+arg_10], rax
0x18005acfd  lea     rdx, [r14+50h]
0x18005ad01  lea     rcx, [rbp+57h+var_68]
0x18005ad05  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18005ad0a  mov     rbx, rax
0x18005ad0d  lea     rax, [rbp+57h+var_48]
0x18005ad11  mov     [rbp+57h+arg_18], rax
0x18005ad15  lea     rdx, [r14+30h]
0x18005ad19  lea     rcx, [rbp+57h+var_48]
0x18005ad1d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18005ad22  nop
0x18005ad23  xor     edx, edx
0x18005ad25  jmp     loc_18005AECA
0x18005ad2a  mov     edi, 80040207h
0x18005ad2f  jmp     loc_18005AE9A
0x18005ad34  mov     ebx, 2000h
0x18005ad39  cmp     ecx, ebx
0x18005ad3b  jb      short loc_18005AD49
0x18005ad3d  mov     ebx, ecx
0x18005ad3f  mov     eax, 80000h
0x18005ad44  cmp     ecx, eax
0x18005ad46  cmova   ebx, eax
0x18005ad49  mov     rcx, [r14+88h]
0x18005ad50  lea     rdi, [r14+84h]
0x18005ad57  test    rcx, rcx
0x18005ad5a  jz      short loc_18005AD7B
0x18005ad5c  cmp     [rdi], ebx
0x18005ad5e  jnb     loc_18005ADE9
0x18005ad64  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18005ad6a  mov     qword ptr [r14+88h], 0
0x18005ad75  mov     dword ptr [rdi], 0
0x18005ad7b  mov     ecx, ebx; unsigned __int64
0x18005ad7d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005ad84  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18005ad89  mov     [r14+88h], rax
0x18005ad90  test    rax, rax
0x18005ad93  jnz     short loc_18005ADE7
0x18005ad95  mov     rax, cs:WPP_GLOBAL_Control
0x18005ad9c  cmp     rax, rsi
0x18005ad9f  jz      short loc_18005ADDD
0x18005ada1  test    byte ptr [rax+1Ch], 8
0x18005ada5  jz      short loc_18005ADDD
0x18005ada7  cmp     byte ptr [rax+19h], 2
0x18005adab  jb      short loc_18005ADDD
0x18005adad  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005adb2  mov     edx, 60h ; '`'
0x18005adb7  lea     rcx, aByte; "BYTE"
0x18005adbe  mov     qword ptr [rsp+0B0h+var_90], rcx
0x18005adc3  mov     r9d, eax
0x18005adc6  lea     r8, WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids
0x18005adcd  mov     rcx, cs:WPP_GLOBAL_Control
0x18005add4  mov     rcx, [rcx+10h]
0x18005add8  call    WPP_SF_Ds
0x18005addd  mov     edi, 8007000Eh
0x18005ade2  jmp     loc_18005AE9A
0x18005ade7  mov     [rdi], ebx
0x18005ade9  mov     eax, cs:?g_dwDMObjectContext@@3KA; ulong g_dwDMObjectContext
0x18005adef  mov     [r14], eax
0x18005adf2  mov     dword ptr [r14+4], 3
0x18005adfa  mov     [r14+8], r15
0x18005adfe  xorps   xmm0, xmm0
0x18005ae01  movups  xmmword ptr [r14+10h], xmm0
0x18005ae06  mov     dword ptr [r14+20h], 0
0x18005ae0e  mov     r8d, [r14+80h]
0x18005ae15  cmp     [rdi], r8d
0x18005ae18  cmovbe  r8d, [rdi]; dwNumberOfBytesToRead
0x18005ae1c  xor     r9d, r9d; lpdwNumberOfBytesRead
0x18005ae1f  mov     rdx, [r14+88h]; lpBuffer
0x18005ae26  mov     rcx, [r14+28h]; hRequest
0x18005ae2a  call    cs:__imp_WinHttpReadData
0x18005ae30  test    eax, eax
0x18005ae32  jnz     short loc_18005AE94
0x18005ae34  call    cs:__imp_GetLastError
0x18005ae3a  mov     edi, eax
0x18005ae3c  mov     rax, cs:WPP_GLOBAL_Control
0x18005ae43  cmp     rax, rsi
0x18005ae46  jz      short loc_18005AE7C
0x18005ae48  test    byte ptr [rax+1Ch], 8
0x18005ae4c  jz      short loc_18005AE7C
0x18005ae4e  cmp     byte ptr [rax+19h], 2
0x18005ae52  jb      short loc_18005AE7C
0x18005ae54  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005ae59  mov     edx, 61h ; 'a'
0x18005ae5e  mov     dword ptr [rsp+0B0h+var_90], edi
0x18005ae62  mov     r9d, eax
0x18005ae65  lea     r8, WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids
0x18005ae6c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ae73  mov     rcx, [rcx+10h]
0x18005ae77  call    WPP_SF_Dd
0x18005ae7c  test    edi, edi
0x18005ae7e  jle     short loc_18005AE8B
0x18005ae80  movzx   edi, di
0x18005ae83  or      edi, 80070000h
0x18005ae89  test    edi, edi
0x18005ae8b  js      short loc_18005AE96
0x18005ae8d  mov     edi, 80004005h
0x18005ae92  jmp     short loc_18005AE9A
0x18005ae94  xor     edi, edi
0x18005ae96  test    edi, edi
0x18005ae98  jns     short loc_18005AEDD
0x18005ae9a  lea     rax, [rbp+57h+var_48]
0x18005ae9e  mov     [rbp+57h+arg_10], rax
0x18005aea2  lea     rdx, [r14+50h]
0x18005aea6  lea     rcx, [rbp+57h+var_48]
0x18005aeaa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18005aeaf  mov     rbx, rax
0x18005aeb2  lea     rax, [rbp+57h+var_68]
0x18005aeb6  mov     [rbp+57h+arg_18], rax
0x18005aeba  lea     rdx, [r14+30h]
0x18005aebe  lea     rcx, [rbp+57h+var_68]
0x18005aec2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18005aec7  nop
0x18005aec8  mov     edx, edi
0x18005aeca  mov     qword ptr [rsp+0B0h+var_90], rbx; __int64
0x18005aecf  mov     r9, rax
0x18005aed2  mov     r8, r14
0x18005aed5  mov     rcx, r15; this
0x18005aed8  call    ?ReportDownloadStatus@CDownloadManager@@IEAAXJPEAU_DM_CONTEXT@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; CDownloadManager::ReportDownloadStatus(long,_DM_CONTEXT *,std::wstring,std::wstring)
0x18005aedd  mov     eax, edi
0x18005aedf  mov     rbx, [rsp+0B0h+arg_0]
0x18005aee7  add     rsp, 90h
0x18005aeee  pop     r15
0x18005aef0  pop     r14
0x18005aef2  pop     rdi
0x18005aef3  pop     rsi
0x18005aef4  pop     rbp
0x18005aef5  retn
```
