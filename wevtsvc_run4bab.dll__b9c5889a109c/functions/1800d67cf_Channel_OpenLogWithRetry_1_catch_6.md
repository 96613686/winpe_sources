# _Channel::OpenLogWithRetry_::_1_::catch$6

- ea: `0x1800d67cf`
- end: `0x1800d6b97`
- name: `_Channel::OpenLogWithRetry_::_1_::catch$6`
- size: `968`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180014bd0`
- `0x180017b60`
- `0x18002d204`
- `0x18002d6dc`
- `0x18002ede4`
- `0x180047194`
- `0x1800708e0`
- `0x180092008`
- `0x18009ef90`
- `0x18009f298`
- `0x18009f3bc`
- `0x1800d334c`
- `0x1800d67cf`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d6a76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d6a76`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800d69dd`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800d69dd`

## pseudocode

```c
__int64 __fastcall Channel::OpenLogWithRetry_::_1_::catch_6(__int64 a1, __int64 a2, int a3)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  char v6; // al
  _QWORD *v7; // rdi
  _QWORD *v8; // rcx
  __int64 v9; // rsi
  unsigned int v10; // ebx
  unsigned int v11; // ebx
  unsigned int v12; // ebx
  void *v13; // rdx
  unsigned int v14; // ebx
  __int64 v15; // rax
  _QWORD *v16; // rdi
  _QWORD *v17; // rbx
  DWORD LastError; // ebx

  v4 = *(_QWORD *)(a2 + 296);
  *(_BYTE *)(v4 + 36) = 1;
  v5 = *(_DWORD *)(v4 + 24);
  v6 = Microsoft_Windows_EventlogEnableBits;
  v7 = *(_QWORD **)(a2 + 328);
  if ( (Microsoft_Windows_EventlogEnableBits & 1) != 0 )
  {
    McTemplateU0qz_EventWriteTransfer(a1, &INIT_CHANNEL_LOGGING, v5, *v7);
    v6 = Microsoft_Windows_EventlogEnableBits;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    v9 = *(_QWORD *)(a2 + 336);
  }
  else
  {
    v9 = *(_QWORD *)(a2 + 336);
    *(_QWORD *)(a2 + 64) = *(_QWORD *)v9;
    *(_QWORD *)(a2 + 72) = *(_QWORD *)(v9 + 8);
    WPP_SF_D_utlwsv_(v8[2], (unsigned int)&WPP_GLOBAL_Control, a3, v5, a2 + 64);
    v6 = Microsoft_Windows_EventlogEnableBits;
  }
  v10 = v5 - 13;
  if ( !v10 || (v11 = v10 - 25) == 0 || (v12 = v11 - 1462) == 0 )
  {
    if ( (v6 & 4) == 0 )
      goto LABEL_18;
    v13 = &INIT_CHANNEL_MOVED_CORRUPT_LOG;
    goto LABEL_17;
  }
  if ( v12 - 13534 >= 2 )
    throw;
  if ( (v6 & 4) != 0 )
  {
    v13 = &INIT_CHANNEL_MOVED_UNSUPPORTED_VERSION_LOG;
LABEL_17:
    McTemplateU0z_EventWriteTransfer(v8, v13, *v7);
  }
LABEL_18:
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>((void *)(a2 + 112));
  v14 = ExpandEnvStringNoThrow(*(LPCWSTR *)v9);
  if ( v14 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_90c925f5c8ff3f4567f272a23c56f0b5_Traceguids, v14);
    }
    *(_QWORD *)(a2 + 144) = &word_1800EC961;
    *(_QWORD *)(a2 + 152) = 0;
    *(_QWORD *)(a2 + 160) = 0;
    *(_DWORD *)(a2 + 168) = v14;
    *(_QWORD *)(a2 + 172) = -1;
    *(_BYTE *)(a2 + 180) = 0;
    throw (EvtException *)(a2 + 144);
  }
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>((void *)(a2 + 264));
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(a2 + 264)
    || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append((void *)(a2 + 264)) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_90c925f5c8ff3f4567f272a23c56f0b5_Traceguids, 14);
    }
    *(_OWORD *)(a2 + 224) = 0;
    *(_QWORD *)(a2 + 240) = 0;
    *(_DWORD *)(a2 + 248) = 14;
    *(_DWORD *)(a2 + 252) = -1;
    *(_DWORD *)(a2 + 256) = 906;
    throw (EvtException *)(a2 + 224);
  }
  if ( !MoveFileExW(*(LPCWSTR *)(a2 + 112), *(LPCWSTR *)(a2 + 264), 1u) )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_90c925f5c8ff3f4567f272a23c56f0b5_Traceguids, LastError);
    }
    *(_OWORD *)(a2 + 184) = 0;
    *(_QWORD *)(a2 + 200) = 0;
    *(_DWORD *)(a2 + 208) = LastError;
    *(_DWORD *)(a2 + 212) = -1;
    *(_DWORD *)(a2 + 216) = 917;
    throw (EvtException *)(a2 + 184);
  }
  v15 = *(_QWORD *)(a2 + 112);
  *(_QWORD *)(a2 + 64) = v15;
  *(_QWORD *)(a2 + 72) = (*(_QWORD *)(a2 + 120) - v15) >> 1;
  *(_OWORD *)(a2 + 96) = *(_OWORD *)v7;
  v16 = (_QWORD *)Channel::OpenLogFileForChannel(a2 + 328, a2 + 96, a2 + 64, *(_QWORD *)(a2 + 344));
  v17 = *(_QWORD **)(a2 + 320);
  wmi::AutoRef<File>::Release(v17);
  *v17 = *v16;
  *v16 = 0;
  wmi::AutoRef<File>::Release(a2 + 328);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit((void *)(a2 + 264));
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit((void *)(a2 + 112));
  return 0;
}

```

## disassembly

```asm
0x1800d67cf  mov     [rsp+arg_8], rdx
0x1800d67d4  push    rbx
0x1800d67d5  push    rbp
0x1800d67d6  push    rsi
0x1800d67d7  push    rdi
0x1800d67d8  push    r14
0x1800d67da  push    r15
0x1800d67dc  sub     rsp, 38h
0x1800d67e0  mov     rbp, rdx
0x1800d67e3  mov     rax, [rbp+128h]
0x1800d67ea  mov     byte ptr [rax+24h], 1
0x1800d67ee  mov     ebx, [rax+18h]
0x1800d67f1  mov     eax, cs:Microsoft_Windows_EventlogEnableBits
0x1800d67f7  mov     rdi, [rbp+148h]
0x1800d67fe  test    al, 1
0x1800d6800  jz      short loc_1800D681A
0x1800d6802  mov     r9, [rdi]
0x1800d6805  mov     r8d, ebx
0x1800d6808  lea     rdx, INIT_CHANNEL_LOGGING
0x1800d680f  call    McTemplateU0qz_EventWriteTransfer
0x1800d6814  mov     eax, cs:Microsoft_Windows_EventlogEnableBits
0x1800d681a  lea     rdx, WPP_GLOBAL_Control
0x1800d6821  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d6828  cmp     rcx, rdx
0x1800d682b  jz      short loc_1800D686F
0x1800d682d  test    dword ptr [rcx+1Ch], 800h
0x1800d6834  jz      short loc_1800D686F
0x1800d6836  cmp     byte ptr [rcx+19h], 2
0x1800d683a  jb      short loc_1800D686F
0x1800d683c  mov     rsi, [rbp+150h]
0x1800d6843  mov     rax, [rsi]
0x1800d6846  mov     [rbp+40h], rax
0x1800d684a  mov     rax, [rsi+8]
0x1800d684e  mov     [rbp+48h], rax
0x1800d6852  lea     rax, [rbp+40h]
0x1800d6856  mov     [rsp+68h+var_48], rax
0x1800d685b  mov     r9d, ebx
0x1800d685e  mov     rcx, [rcx+10h]
0x1800d6862  call    WPP_SF_D_utlwsv_
0x1800d6867  mov     eax, cs:Microsoft_Windows_EventlogEnableBits
0x1800d686d  jmp     short loc_1800D6876
0x1800d686f  mov     rsi, [rbp+150h]
0x1800d6876  sub     ebx, 0Dh
0x1800d6879  jz      short loc_1800D68B9
0x1800d687b  sub     ebx, 19h
0x1800d687e  jz      short loc_1800D68B9
0x1800d6880  sub     ebx, 5B6h
0x1800d6886  jz      short loc_1800D68B9
0x1800d6888  sub     ebx, 34DEh
0x1800d688e  jz      short loc_1800D689F
0x1800d6890  cmp     ebx, 1
0x1800d6893  jz      short loc_1800D689F
0x1800d6895  xor     edx, edx; pThrowInfo
0x1800d6897  xor     ecx, ecx; pExceptionObject
0x1800d6899  call    _CxxThrowException_0
0x1800d689f  lea     r14, aUnsupportedver; ".UnsupportedVer"
0x1800d68a6  mov     r15d, 0Fh
0x1800d68ac  test    al, 4
0x1800d68ae  jz      short loc_1800D68D9
0x1800d68b0  lea     rdx, INIT_CHANNEL_MOVED_UNSUPPORTED_VERSION_LOG
0x1800d68b7  jmp     short loc_1800D68D1
0x1800d68b9  lea     r14, aCorrupt; ".corrupt"
0x1800d68c0  mov     r15d, 8
0x1800d68c6  test    al, 4
0x1800d68c8  jz      short loc_1800D68D9
0x1800d68ca  lea     rdx, INIT_CHANNEL_MOVED_CORRUPT_LOG
0x1800d68d1  mov     r8, [rdi]
0x1800d68d4  call    McTemplateU0z_EventWriteTransfer
0x1800d68d9  lea     rcx, [rbp+70h]; void *
0x1800d68dd  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800d68e2  nop
0x1800d68e3  lea     rdx, [rbp+70h]
0x1800d68e7  mov     rcx, [rsi]; lpSrc
0x1800d68ea  call    ?ExpandEnvStringNoThrow@@YAKPEB_WAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; ExpandEnvStringNoThrow(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x1800d68ef  mov     ebx, eax
0x1800d68f1  test    eax, eax
0x1800d68f3  jz      loc_1800D6983
0x1800d68f9  lea     rax, WPP_GLOBAL_Control
0x1800d6900  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d6907  cmp     rcx, rax
0x1800d690a  jz      short loc_1800D6933
0x1800d690c  test    dword ptr [rcx+1Ch], 800h
0x1800d6913  jz      short loc_1800D6933
0x1800d6915  cmp     byte ptr [rcx+19h], 2
0x1800d6919  jb      short loc_1800D6933
0x1800d691b  mov     edx, 1Dh
0x1800d6920  mov     r9d, ebx
0x1800d6923  lea     r8, WPP_90c925f5c8ff3f4567f272a23c56f0b5_Traceguids
0x1800d692a  mov     rcx, [rcx+10h]
0x1800d692e  call    WPP_SF_d
0x1800d6933  lea     rax, word_1800EC961
0x1800d693a  mov     [rbp+90h], rax
0x1800d6941  mov     qword ptr [rbp+98h], 0
0x1800d694c  mov     qword ptr [rbp+0A0h], 0
0x1800d6957  mov     [rbp+0A8h], ebx
0x1800d695d  mov     qword ptr [rbp+0ACh], 0FFFFFFFFFFFFFFFFh
0x1800d6968  mov     byte ptr [rbp+0B4h], 0
0x1800d696f  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800d6976  lea     rcx, [rbp+90h]; pExceptionObject
0x1800d697d  call    _CxxThrowException_0
0x1800d6983  lea     rcx, [rbp+108h]; void *
0x1800d698a  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800d698f  nop
0x1800d6990  mov     r8, [rbp+78h]
0x1800d6994  mov     rdx, [rbp+70h]
0x1800d6998  sub     r8, rdx
0x1800d699b  sar     r8, 1
0x1800d699e  lea     rcx, [rbp+108h]
0x1800d69a5  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x1800d69aa  test    al, al
0x1800d69ac  jz      loc_1800D6B06
0x1800d69b2  mov     r8, r15
0x1800d69b5  mov     rdx, r14
0x1800d69b8  lea     rcx, [rbp+108h]
0x1800d69bf  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x1800d69c4  test    al, al
0x1800d69c6  jz      loc_1800D6B06
0x1800d69cc  mov     r8d, 1; dwFlags
0x1800d69d2  mov     rdx, [rbp+108h]; lpNewFileName
0x1800d69d9  mov     rcx, [rbp+70h]; lpExistingFileName
0x1800d69dd  call    cs:__imp_MoveFileExW
0x1800d69e3  test    eax, eax
0x1800d69e5  jz      loc_1800D6A76
0x1800d69eb  mov     rax, [rbp+70h]
0x1800d69ef  mov     [rbp+40h], rax
0x1800d69f3  mov     rcx, [rbp+78h]
0x1800d69f7  sub     rcx, rax
0x1800d69fa  sar     rcx, 1
0x1800d69fd  mov     [rbp+48h], rcx
0x1800d6a01  movaps  xmm0, xmmword ptr [rdi]
0x1800d6a04  movdqa  xmmword ptr [rbp+60h], xmm0
0x1800d6a09  mov     r9, [rbp+158h]
0x1800d6a10  lea     r8, [rbp+40h]
0x1800d6a14  lea     rdx, [rbp+60h]
0x1800d6a18  lea     rcx, [rbp+148h]
0x1800d6a1f  call    ?OpenLogFileForChannel@Channel@@CA?AV?$AutoRef@VFile@@@wmi@@V?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@0_K@Z; Channel::OpenLogFileForChannel(tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>,tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>,unsigned __int64)
0x1800d6a24  mov     rdi, rax
0x1800d6a27  mov     rbx, [rbp+140h]
0x1800d6a2e  mov     rcx, rbx
0x1800d6a31  call    ?Release@?$AutoRef@VFile@@@wmi@@QEAAXXZ; wmi::AutoRef<File>::Release(void)
0x1800d6a36  mov     rcx, [rdi]
0x1800d6a39  mov     [rbx], rcx
0x1800d6a3c  mov     qword ptr [rdi], 0
0x1800d6a43  lea     rcx, [rbp+148h]
0x1800d6a4a  call    ?Release@?$AutoRef@VFile@@@wmi@@QEAAXXZ; wmi::AutoRef<File>::Release(void)
0x1800d6a4f  nop
0x1800d6a50  lea     rcx, [rbp+108h]; void *
0x1800d6a57  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800d6a5c  nop
0x1800d6a5d  lea     rcx, [rbp+70h]; void *
0x1800d6a61  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800d6a66  nop
0x1800d6a67  mov     rax, 0
0x1800d6a71  jmp     loc_1800D6B89
0x1800d6a76  call    cs:__imp_GetLastError
0x1800d6a7c  mov     ebx, eax
0x1800d6a7e  mov     eax, 507h
0x1800d6a83  test    ebx, ebx
0x1800d6a85  cmovz   ebx, eax
0x1800d6a88  lea     rax, WPP_GLOBAL_Control
0x1800d6a8f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d6a96  cmp     rcx, rax
0x1800d6a99  jz      short loc_1800D6AC2
0x1800d6a9b  test    dword ptr [rcx+1Ch], 800h
0x1800d6aa2  jz      short loc_1800D6AC2
0x1800d6aa4  cmp     byte ptr [rcx+19h], 2
0x1800d6aa8  jb      short loc_1800D6AC2
0x1800d6aaa  mov     edx, 1Fh
0x1800d6aaf  mov     r9d, ebx
0x1800d6ab2  lea     r8, WPP_90c925f5c8ff3f4567f272a23c56f0b5_Traceguids
0x1800d6ab9  mov     rcx, [rcx+10h]
0x1800d6abd  call    WPP_SF_d
0x1800d6ac2  xorps   xmm0, xmm0
0x1800d6ac5  movdqu  xmmword ptr [rbp+0B8h], xmm0
0x1800d6acd  mov     qword ptr [rbp+0C8h], 0
0x1800d6ad8  mov     [rbp+0D0h], ebx
0x1800d6ade  mov     dword ptr [rbp+0D4h], 0FFFFFFFFh
0x1800d6ae8  mov     dword ptr [rbp+0D8h], 395h
0x1800d6af2  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800d6af9  lea     rcx, [rbp+0B8h]; pExceptionObject
0x1800d6b00  call    _CxxThrowException_0
0x1800d6b06  lea     rax, WPP_GLOBAL_Control
0x1800d6b0d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d6b14  cmp     rcx, rax
0x1800d6b17  jz      short loc_1800D6B41
0x1800d6b19  test    dword ptr [rcx+1Ch], 800h
0x1800d6b20  jz      short loc_1800D6B41
0x1800d6b22  cmp     byte ptr [rcx+19h], 2
0x1800d6b26  jb      short loc_1800D6B41
0x1800d6b28  mov     edx, 1Eh
0x1800d6b2d  lea     r9d, [rdx-10h]
0x1800d6b31  lea     r8, WPP_90c925f5c8ff3f4567f272a23c56f0b5_Traceguids
0x1800d6b38  mov     rcx, [rcx+10h]
0x1800d6b3c  call    WPP_SF_d
0x1800d6b41  xorps   xmm0, xmm0
0x1800d6b44  movdqu  xmmword ptr [rbp+0E0h], xmm0
0x1800d6b4c  mov     qword ptr [rbp+0F0h], 0
0x1800d6b57  mov     dword ptr [rbp+0F8h], 0Eh
0x1800d6b61  mov     dword ptr [rbp+0FCh], 0FFFFFFFFh
0x1800d6b6b  mov     dword ptr [rbp+100h], 38Ah
0x1800d6b75  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800d6b7c  lea     rcx, [rbp+0E0h]; pExceptionObject
0x1800d6b83  call    _CxxThrowException_0
0x1800d6b89  add     rsp, 38h
0x1800d6b8d  pop     r15
0x1800d6b8f  pop     r14
0x1800d6b91  pop     rdi
0x1800d6b92  pop     rsi
0x1800d6b93  pop     rbp
0x1800d6b94  pop     rbx
0x1800d6b95  retn
```
