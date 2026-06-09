# HTTP_USER_REQUEST::_PostProcessReadData(ulong,PENDING_API_CALL *,ulong *)

- ea: `0x180035c4c`
- end: `0x180036051`
- name: `?_PostProcessReadData@HTTP_USER_REQUEST@@AEAAKKPEAVPENDING_API_CALL@@PEAK@Z`
- size: `1029`
- prototype: `__int64 __fastcall(HTTP_USER_REQUEST *this, unsigned int, struct PENDING_API_CALL *, unsigned int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting`

## callers

- `0x180037600`

## callees

- `0x180010f50`
- `0x1800250ec`
- `0x180026680`
- `0x180035c4c`
- `0x180036644`
- `0x180036970`
- `0x1800460c4`
- `0x180090610`
- `0x1800a1d10`
- `0x1800b7d40`
- `0x1800d4f90`
- `0x1800db6b0`
- `0x1800db704`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180035eeb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180035eeb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180035efb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180035efb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180035eb2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180035eb2`
- `ntdll!EtwEventActivityIdControl` at `0x180035d48`
- `ntdll!EtwEventActivityIdControl` at `0x180035daf`
- `ntdll!EtwEventActivityIdControl` at `0x180035d48`
- `ntdll!EtwEventActivityIdControl` at `0x180035daf`
- `webio!__imp_WebQueryHttpRequestOption` at `0x180035e27`
- `webio!__imp_WebQueryHttpRequestOption` at `0x180035e27`

## pseudocode

```c
__int64 __fastcall HTTP_USER_REQUEST::_PostProcessReadData(
        HTTP_USER_REQUEST *this,
        unsigned int a2,
        struct PENDING_API_CALL *a3,
        unsigned int *a4)
{
  char v8; // al
  unsigned int v9; // r14d
  __int64 v10; // rcx
  struct _GUID *v11; // rax
  __int64 v12; // rdx
  struct _GUID *v13; // rax
  signed int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rcx
  void (__fastcall *v17)(__int64, __int64, __int64, int *, int); // rax
  int v18; // eax
  bool v19; // sf
  WEBIO_REQUEST *v20; // rcx
  __int64 v21; // rcx
  int v23; // ebx
  void *v24; // rcx
  unsigned int StreamErrorCode; // eax
  int v26; // edx
  int v27; // ecx
  int v28; // r8d
  __int64 v29; // rdx
  int HeaderWithToken; // eax
  unsigned int v31[2]; // [rsp+20h] [rbp-A8h]
  _BYTE v32[4]; // [rsp+30h] [rbp-98h] BYREF
  int v33[3]; // [rsp+34h] [rbp-94h] BYREF
  const char *v34; // [rsp+40h] [rbp-88h] BYREF
  int v35; // [rsp+48h] [rbp-80h]
  int v36; // [rsp+4Ch] [rbp-7Ch]
  struct _GUID v37; // [rsp+50h] [rbp-78h] BYREF
  int v38; // [rsp+60h] [rbp-68h]
  struct _GUID v39; // [rsp+68h] [rbp-60h] BYREF
  __int128 v40; // [rsp+78h] [rbp-50h]

  v8 = xmmword_180107A60;
  if ( (xmmword_180107A60 & 2) != 0 )
  {
    WPP_SF_q(1025, 76, WPP_29ecff532d3a35783d73db4432e82274_Traceguids);
    v8 = xmmword_180107A60;
  }
  if ( a2 == 12030 && *((_DWORD *)this + 2671) )
  {
    StreamErrorCode = WEBIO_REQUEST::GetStreamErrorCode(*((WEBIO_REQUEST **)a3 + 16), (unsigned __int64 *)this + 1336);
    if ( StreamErrorCode && (xmmword_180107A60 & 2) != 0 )
      WPP_SF_d(1025, 78, WPP_29ecff532d3a35783d73db4432e82274_Traceguids, StreamErrorCode, *(_QWORD *)v31);
    *((_DWORD *)this + 2674) = 1;
    if ( (xmmword_180107A60 & 2) != 0 )
      WPP_SF_iq(v27, v26, v28, *((_QWORD *)this + 1336), (__int64)this);
    goto LABEL_7;
  }
  if ( (v8 & 2) != 0 )
    WPP_SF_q(1025, 77, WPP_29ecff532d3a35783d73db4432e82274_Traceguids);
  v9 = 12152;
  v33[0] = 0;
  if ( a2 != 12152 )
  {
LABEL_7:
    v9 = a2;
    if ( a2 )
      return v9;
    goto LABEL_8;
  }
  if ( CWebIOResponseHeadersShim::IsHeaderPresent((HTTP_USER_REQUEST *)((char *)this + 120), a2, v33) )
    return 12004;
  v35 = 7;
  v34 = "chunked";
  v36 = *(_DWORD *)&v39.Data4[4];
  HeaderWithToken = CWebIOResponseHeadersShim::FindHeaderWithToken((char *)this + 120, v29, &v34);
  if ( v33[0] && !HeaderWithToken )
  {
    *((_DWORD *)this + 21) = 1;
    *a4 = 0;
    HTTP_USER_REQUEST::_SafeDetachSysReq(this);
    v9 = 0;
LABEL_8:
    if ( (*((_BYTE *)a3 + 56) & 0xC0) != 0 )
    {
      v33[0] = *a4;
      v37 = 0;
      v38 = 0;
      if ( !*((_DWORD *)a3 + 10) || (v23 = *((_DWORD *)a3 + 11), GetCurrentThreadId() == v23) )
      {
        v10 = 16;
        v11 = &v37;
        v12 = 16;
        do
        {
          LOBYTE(v11->Data1) = 0;
          v11 = (struct _GUID *)((char *)v11 + 1);
          --v12;
        }
        while ( v12 );
        v38 = 0;
        v13 = &v37;
        v40 = 0;
        v39 = 0;
        do
        {
          LOBYTE(v13->Data1) = 0;
          v13 = (struct _GUID *)((char *)v13 + 1);
          --v10;
        }
        while ( v10 );
        WxEtwGetActivityId(&v39);
        HIDWORD(v34) = 0;
        v14 = EtwEventActivityIdControl(2, &WinHttpEtwNullActivityId);
        if ( v14 > 0 )
          v14 = (unsigned __int16)v14 | 0x80070000;
        if ( v14 < 0 )
          HIDWORD(v34) = 144;
        v15 = *((_QWORD *)a3 + 8);
        v16 = *((_QWORD *)this + 4);
        v17 = (void (__fastcall *)(__int64, __int64, __int64, int *, int))*((_QWORD *)a3 + 6);
        v37 = v39;
        v38 = 1;
        v17(v16, v15, 128, v33, 4);
        if ( v38 )
        {
          HIDWORD(v34) = 0;
          v18 = EtwEventActivityIdControl(2, &v37);
          v19 = v18 < 0;
          if ( v18 > 0 )
            v19 = 1;
          if ( v19 )
            HIDWORD(v34) = 144;
        }
      }
      else
      {
        v24 = (void *)*((_QWORD *)a3 + 9);
        *((_QWORD *)a3 + 19) = v33;
        *((_DWORD *)a3 + 35) = 1;
        *((_DWORD *)a3 + 36) = 128;
        *((_DWORD *)a3 + 40) = 4;
        SetEvent(v24);
        WaitForSingleObjectEx(*((HANDLE *)a3 + 10), 0xFFFFFFFF, 0);
        *(_QWORD *)((char *)a3 + 140) = 0;
        *((_QWORD *)a3 + 19) = 0;
        *((_DWORD *)a3 + 40) = 0;
      }
    }
    v20 = (WEBIO_REQUEST *)*((_QWORD *)a3 + 16);
    if ( *((_DWORD *)v20 + 181) )
    {
      WEBIO_REQUEST::GetRequestTimes(v20, (HTTP_USER_REQUEST *)((char *)this + 9048));
      WEBIO_REQUEST::GetRequestStats(*((WEBIO_REQUEST **)a3 + 16), (HTTP_USER_REQUEST *)((char *)this + 9584));
      v21 = *((_QWORD *)a3 + 16);
      v32[0] = 0;
      v34 = 0;
      if ( !(unsigned int)WebQueryHttpRequestOption(*(_QWORD *)(v21 + 184), 16391, v32, 1, &v34)
        && v32[0]
        && (*((_DWORD *)a3 + 14) & 0x300) != 0 )
      {
        HTTP_USER_REQUEST::_IndicateInformational(this, a3, 0x100u, 0, 0);
        HTTP_USER_REQUEST::_IndicateInformational(this, a3, 0x200u, 0, 0);
      }
    }
    if ( *(_DWORD *)(*((_QWORD *)a3 + 16) + 724LL) )
      *((_DWORD *)this + 21) = 1;
  }
  return v9;
}

```

## disassembly

```asm
0x180035c4c  push    rbx
0x180035c4e  push    rsi
0x180035c4f  push    rdi
0x180035c50  push    r12
0x180035c52  push    r13
0x180035c54  push    r14
0x180035c56  push    r15
0x180035c58  sub     rsp, 90h
0x180035c5f  mov     rax, cs:__security_cookie
0x180035c66  xor     rax, rsp
0x180035c69  mov     [rsp+0C8h+var_40], rax
0x180035c71  mov     r15, r9
0x180035c74  mov     rdi, r8
0x180035c77  mov     ebx, edx
0x180035c79  mov     rsi, rcx
0x180035c7c  mov     al, byte ptr cs:xmmword_180107A60
0x180035c82  test    al, 2
0x180035c84  jnz     loc_180035F94
0x180035c8a  xor     r12d, r12d
0x180035c8d  mov     r13d, 1
0x180035c93  cmp     ebx, 2EFEh
0x180035c99  jz      loc_180035F1B
0x180035c9f  test    al, 2
0x180035ca1  jnz     loc_180035FB8
0x180035ca7  mov     r14d, 2F78h
0x180035cad  mov     [rsp+0C8h+var_94], r12d
0x180035cb2  cmp     ebx, r14d
0x180035cb5  jz      loc_180035FD6
0x180035cbb  mov     r14d, ebx
0x180035cbe  test    ebx, ebx
0x180035cc0  jnz     loc_180035E4C
0x180035cc6  test    byte ptr [rdi+38h], 0C0h
0x180035cca  jz      loc_180035DC9
0x180035cd0  mov     eax, [r15]
0x180035cd3  xorps   xmm0, xmm0
0x180035cd6  mov     [rsp+0C8h+var_94], eax
0x180035cda  xor     eax, eax
0x180035cdc  movups  [rsp+0C8h+var_78], xmm0
0x180035ce1  mov     [rsp+0C8h+var_68], eax
0x180035ce5  cmp     [rdi+28h], r12d
0x180035ce9  jnz     loc_180035EAF
0x180035cef  mov     ecx, 10h
0x180035cf4  lea     rax, [rsp+0C8h+var_78]
0x180035cf9  mov     edx, ecx
0x180035cfb  mov     [rax], r12b
0x180035cfe  add     rax, r13
0x180035d01  sub     rdx, r13
0x180035d04  jnz     short loc_180035CFB
0x180035d06  xorps   xmm0, xmm0
0x180035d09  mov     [rsp+0C8h+var_68], r12d
0x180035d0e  xorps   xmm1, xmm1
0x180035d11  lea     rax, [rsp+0C8h+var_78]
0x180035d16  movups  [rsp+0C8h+var_50], xmm0
0x180035d1b  movups  xmmword ptr [rsp+0C8h+var_60.Data1], xmm1
0x180035d20  mov     [rax], r12b
0x180035d23  add     rax, r13
0x180035d26  sub     rcx, r13
0x180035d29  jnz     short loc_180035D20
0x180035d2b  lea     rcx, [rsp+0C8h+var_60]; struct _GUID *
0x180035d30  call    ?WxEtwGetActivityId@@YAXPEAU_GUID@@@Z; WxEtwGetActivityId(_GUID *)
0x180035d35  mov     ebx, 2
0x180035d3a  mov     dword ptr [rsp+0C8h+var_88+4], r12d
0x180035d3f  mov     ecx, ebx
0x180035d41  lea     rdx, ?WinHttpEtwNullActivityId@@3U_GUID@@B; _GUID const WinHttpEtwNullActivityId
0x180035d48  call    cs:__imp_EtwEventActivityIdControl
0x180035d4e  test    eax, eax
0x180035d50  jle     short loc_180035D5A
0x180035d52  movzx   eax, ax
0x180035d55  or      eax, 80070000h
0x180035d5a  mov     r15d, 90h
0x180035d60  test    eax, eax
0x180035d62  js      loc_180036047
0x180035d68  movups  xmm0, xmmword ptr [rsp+0C8h+var_60.Data1]
0x180035d6d  mov     rdx, [rdi+40h]
0x180035d71  lea     r9, [rsp+0C8h+var_94]
0x180035d76  mov     rcx, [rsi+20h]
0x180035d7a  mov     r8d, 80h
0x180035d80  mov     rax, [rdi+30h]
0x180035d84  movdqu  [rsp+0C8h+var_78], xmm0
0x180035d8a  mov     [rsp+0C8h+var_68], r13d
0x180035d8f  mov     [rsp+0C8h+var_A8], 4
0x180035d97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035d9c  cmp     [rsp+0C8h+var_68], r12d
0x180035da1  jz      short loc_180035DC9
0x180035da3  lea     rdx, [rsp+0C8h+var_78]
0x180035da8  mov     dword ptr [rsp+0C8h+var_88+4], r12d
0x180035dad  mov     ecx, ebx
0x180035daf  call    cs:__imp_EtwEventActivityIdControl
0x180035db5  test    eax, eax
0x180035db7  jle     short loc_180035DC3
0x180035db9  movzx   eax, ax
0x180035dbc  or      eax, 80070000h
0x180035dc1  test    eax, eax
0x180035dc3  js      loc_180035F8A
0x180035dc9  mov     rcx, [rdi+80h]; this
0x180035dd0  cmp     [rcx+2D4h], r12d
0x180035dd7  jz      short loc_180035E38
0x180035dd9  lea     rdx, [rsi+2358h]; struct _WINHTTP_REQUEST_TIMES *
0x180035de0  call    ?GetRequestTimes@WEBIO_REQUEST@@QEAAKPEAU_WINHTTP_REQUEST_TIMES@@@Z; WEBIO_REQUEST::GetRequestTimes(_WINHTTP_REQUEST_TIMES *)
0x180035de5  mov     rcx, [rdi+80h]; this
0x180035dec  lea     rdx, [rsi+2570h]; struct _WINHTTP_REQUEST_STATS *
0x180035df3  call    ?GetRequestStats@WEBIO_REQUEST@@QEAAKPEAU_WINHTTP_REQUEST_STATS@@@Z; WEBIO_REQUEST::GetRequestStats(_WINHTTP_REQUEST_STATS *)
0x180035df8  mov     rcx, [rdi+80h]
0x180035dff  lea     rax, [rsp+0C8h+var_88]
0x180035e04  mov     r9, r13
0x180035e07  mov     [rsp+0C8h+var_98], r12b
0x180035e0c  lea     r8, [rsp+0C8h+var_98]
0x180035e11  mov     [rsp+0C8h+var_88], r12
0x180035e16  mov     edx, 4007h
0x180035e1b  mov     qword ptr [rsp+0C8h+var_A8], rax
0x180035e20  mov     rcx, [rcx+0B8h]
0x180035e27  call    cs:__imp_WebQueryHttpRequestOption
0x180035e2d  test    eax, eax
0x180035e2f  jnz     short loc_180035E38
0x180035e31  cmp     [rsp+0C8h+var_98], r12b
0x180035e36  jnz     short loc_180035E72
0x180035e38  mov     rcx, [rdi+80h]
0x180035e3f  cmp     [rcx+2D4h], r12d
0x180035e46  jz      short loc_180035E4C
0x180035e48  mov     [rsi+54h], r13d
0x180035e4c  mov     eax, r14d
0x180035e4f  mov     rcx, [rsp+0C8h+var_40]
0x180035e57  xor     rcx, rsp; StackCookie
0x180035e5a  call    __security_check_cookie
0x180035e5f  add     rsp, 90h
0x180035e66  pop     r15
0x180035e68  pop     r14
0x180035e6a  pop     r13
0x180035e6c  pop     r12
0x180035e6e  pop     rdi
0x180035e6f  pop     rsi
0x180035e70  pop     rbx
0x180035e71  retn
0x180035e72  test    dword ptr [rdi+38h], 300h
0x180035e79  jz      short loc_180035E38
0x180035e7b  xor     r9d, r9d; void *
0x180035e7e  mov     [rsp+0C8h+var_A8], r12d; unsigned int
0x180035e83  mov     r8d, 100h; unsigned int
0x180035e89  mov     rdx, rdi; struct PENDING_API_CALL *
0x180035e8c  mov     rcx, rsi; this
0x180035e8f  call    ?_IndicateInformational@HTTP_USER_REQUEST@@AEAAXPEAVPENDING_API_CALL@@KPEAXK@Z; HTTP_USER_REQUEST::_IndicateInformational(PENDING_API_CALL *,ulong,void *,ulong)
0x180035e94  xor     r9d, r9d; void *
0x180035e97  mov     [rsp+0C8h+var_A8], r12d; unsigned int
0x180035e9c  mov     r8d, 200h; unsigned int
0x180035ea2  mov     rdx, rdi; struct PENDING_API_CALL *
0x180035ea5  mov     rcx, rsi; this
0x180035ea8  call    ?_IndicateInformational@HTTP_USER_REQUEST@@AEAAXPEAVPENDING_API_CALL@@KPEAXK@Z; HTTP_USER_REQUEST::_IndicateInformational(PENDING_API_CALL *,ulong,void *,ulong)
0x180035ead  jmp     short loc_180035E38
0x180035eaf  mov     ebx, [rdi+2Ch]
0x180035eb2  call    cs:__imp_GetCurrentThreadId
0x180035eb8  cmp     eax, ebx
0x180035eba  jz      loc_180035CEF
0x180035ec0  mov     rcx, [rdi+48h]; hEvent
0x180035ec4  lea     rax, [rsp+0C8h+var_94]
0x180035ec9  mov     [rdi+98h], rax
0x180035ed0  mov     [rdi+8Ch], r13d
0x180035ed7  mov     dword ptr [rdi+90h], 80h
0x180035ee1  mov     dword ptr [rdi+0A0h], 4
0x180035eeb  call    cs:__imp_SetEvent
0x180035ef1  mov     rcx, [rdi+50h]; hHandle
0x180035ef5  xor     r8d, r8d; bAlertable
0x180035ef8  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180035efb  call    cs:__imp_WaitForSingleObjectEx
0x180035f01  mov     [rdi+8Ch], r12
0x180035f08  mov     [rdi+98h], r12
0x180035f0f  mov     [rdi+0A0h], r12d
0x180035f16  jmp     loc_180035DC9
0x180035f1b  cmp     [rsi+29BCh], r12d
0x180035f22  jz      loc_180035C9F
0x180035f28  mov     rcx, [rdi+80h]; this
0x180035f2f  lea     r14, [rsi+29C0h]
0x180035f36  mov     rdx, r14; unsigned __int64 *
0x180035f39  call    ?GetStreamErrorCode@WEBIO_REQUEST@@QEAAKPEA_K@Z; WEBIO_REQUEST::GetStreamErrorCode(unsigned __int64 *)
0x180035f3e  test    eax, eax
0x180035f40  jz      short loc_180035F64
0x180035f42  test    byte ptr cs:xmmword_180107A60, 2
0x180035f49  jz      short loc_180035F64
0x180035f4b  mov     edx, 4Eh ; 'N'
0x180035f50  lea     r8, WPP_29ecff532d3a35783d73db4432e82274_Traceguids
0x180035f57  mov     ecx, 401h
0x180035f5c  mov     r9d, eax
0x180035f5f  call    WPP_SF_d
0x180035f64  mov     [rsi+29C8h], r13d
0x180035f6b  test    byte ptr cs:xmmword_180107A60, 2
0x180035f72  jz      loc_180035CBB
0x180035f78  mov     r9, [r14]
0x180035f7b  mov     qword ptr [rsp+0C8h+var_A8], rsi
0x180035f80  call    WPP_SF_iq
0x180035f85  jmp     loc_180035CBB
0x180035f8a  mov     dword ptr [rsp+0C8h+var_88+4], r15d
0x180035f8f  jmp     loc_180035DC9
0x180035f94  mov     edx, 4Ch ; 'L'
0x180035f99  lea     r8, WPP_29ecff532d3a35783d73db4432e82274_Traceguids
0x180035fa0  mov     ecx, 401h
0x180035fa5  mov     r9, rsi
0x180035fa8  call    WPP_SF_q
0x180035fad  mov     al, byte ptr cs:xmmword_180107A60
0x180035fb3  jmp     loc_180035C8A
0x180035fb8  mov     edx, 4Dh ; 'M'
0x180035fbd  lea     r8, WPP_29ecff532d3a35783d73db4432e82274_Traceguids
0x180035fc4  mov     ecx, 401h
0x180035fc9  mov     r9, rsi
0x180035fcc  call    WPP_SF_q
0x180035fd1  jmp     loc_180035CA7
0x180035fd6  lea     r8, [rsp+0C8h+var_94]; int *
0x180035fdb  lea     rcx, [rsi+78h]; this
0x180035fdf  call    ?IsHeaderPresent@CWebIOResponseHeadersShim@@QEAAKKPEAH@Z; CWebIOResponseHeadersShim::IsHeaderPresent(ulong,int *)
0x180035fe4  test    eax, eax
0x180035fe6  jz      short loc_180035FF3
0x180035fe8  mov     r14d, 2EE4h
0x180035fee  jmp     loc_180035E4C
0x180035ff3  lea     rax, aChunked; "chunked"
0x180035ffa  mov     [rsp+0C8h+var_80], 7
0x180036002  mov     [rsp+0C8h+var_88], rax
0x180036007  lea     r8, [rsp+0C8h+var_88]
0x18003600c  mov     eax, dword ptr [rsp+0C8h+var_60.Data4+4]
0x180036010  lea     rcx, [rsi+78h]
0x180036014  mov     [rsp+0C8h+var_7C], eax
0x180036018  call    ?FindHeaderWithToken@CWebIOResponseHeadersShim@@QEBAHKU?$string@D@@@Z; CWebIOResponseHeadersShim::FindHeaderWithToken(ulong,string<char>)
0x18003601d  cmp     [rsp+0C8h+var_94], r12d
0x180036022  jz      loc_180035E4C
0x180036028  test    eax, eax
0x18003602a  jnz     loc_180035E4C
0x180036030  mov     [rsi+54h], r13d
0x180036034  mov     rcx, rsi; this
0x180036037  mov     [r15], r12d
0x18003603a  call    ?_SafeDetachSysReq@HTTP_USER_REQUEST@@AEAAXXZ; HTTP_USER_REQUEST::_SafeDetachSysReq(void)
0x18003603f  mov     r14d, r12d
0x180036042  jmp     loc_180035CC6
0x180036047  mov     dword ptr [rsp+0C8h+var_88+4], r15d
0x18003604c  jmp     loc_180035D68
```
