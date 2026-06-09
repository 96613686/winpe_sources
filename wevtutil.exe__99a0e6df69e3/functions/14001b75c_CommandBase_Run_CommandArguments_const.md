# CommandBase::Run(CommandArguments const *)

- ea: `0x14001b75c`
- end: `0x14001c09f`
- name: `?Run@CommandBase@@QEAAXPEBVCommandArguments@@@Z`
- size: `2371`
- prototype: `void __fastcall(CommandBase *this, const struct CommandArguments *, __int64, int)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x1400238ac`

## callees

- `0x140008b40`
- `0x14000cabc`
- `0x140010450`
- `0x140011a38`
- `0x140011bbc`
- `0x1400165d4`
- `0x14001b75c`
- `0x14001c1e0`
- `0x140021b00`
- `0x140022510`
- `0x140022b44`
- `0x140022cec`
- `0x140024a90`
- `0x140024adc`
- `0x140024b00`
- `0x14002894c`
- `0x140031810`
- `0x140034010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14001bd97`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14001bd97`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14001bd41`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14001bd41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001bf65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001bf65`
- `ext-ms-win-wevtapi-eventlog-l1-1-1!EvtOpenSession` at `0x14001bf49`
- `ext-ms-win-wevtapi-eventlog-l1-1-1!EvtOpenSession` at `0x14001bf49`
- `ext-ms-win-security-credui-l1-1-0!CredUICmdLinePromptForCredentialsW` at `0x14001beb7`
- `ext-ms-win-security-credui-l1-1-0!CredUICmdLinePromptForCredentialsW` at `0x14001beb7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CommandBase::Run(CommandBase *this, const struct CommandArguments *a2, __int64 a3, int a4)
{
  char HasOption; // al
  __int64 v6; // rcx
  const wchar_t *OptionString; // rcx
  __int64 v8; // rsi
  __int64 v9; // rax
  wchar_t *v10; // rbx
  _WORD *v11; // rax
  _BYTE *v12; // rbx
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // rax
  wchar_t *v15; // rax
  wchar_t *v16; // rbx
  __int128 *v17; // rcx
  WCHAR *v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rax
  int v21; // edx
  const WCHAR *v22; // rcx
  DWORD v23; // ebx
  EVT_HANDLE v24; // rax
  DWORD LastError; // ebx
  const char *ulUserBufferSize; // [rsp+20h] [rbp-E0h]
  const char *ulUserBufferSizea; // [rsp+20h] [rbp-E0h]
  char v28[16]; // [rsp+50h] [rbp-B0h] BYREF
  WINBOOL pfSave[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v30; // [rsp+68h] [rbp-98h]
  const wchar_t *v31; // [rsp+70h] [rbp-90h] BYREF
  __int64 v32; // [rsp+78h] [rbp-88h]
  __int128 pExceptionObject; // [rsp+80h] [rbp-80h] BYREF
  __int128 v34; // [rsp+90h] [rbp-70h]
  __int64 v35; // [rsp+A0h] [rbp-60h]
  _BYTE v36[40]; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR *v37; // [rsp+D0h] [rbp-30h] BYREF
  char v38; // [rsp+D8h] [rbp-28h]
  __int128 v39; // [rsp+E0h] [rbp-20h] BYREF
  __m128i si128; // [rsp+F0h] [rbp-10h]
  WCHAR pszPassword[264]; // [rsp+100h] [rbp+0h] BYREF

  *((_QWORD *)this + 1) = a2;
  *(_QWORD *)pfSave = L"uni";
  v30 = 3;
  v31 = L"unicode";
  v32 = 7;
  g_outputUnicode = CommandArguments::GetOptionBool(
                      (_DWORD)a2,
                      (unsigned int)&v31,
                      (unsigned int)pfSave,
                      a4,
                      (__int64)v28);
  (*(void (__fastcall **)(CommandBase *))(*(_QWORD *)this + 8LL))(this);
  if ( g_outputUnicode )
    WriteBOM(*((void **)this + 2));
  v31 = L"username";
  v32 = 8;
  *(_QWORD *)pfSave = L"u";
  v30 = 1;
  HasOption = CommandArguments::HasOption(*((_QWORD *)this + 1), pfSave, &v31);
  v6 = *((_QWORD *)this + 1);
  v30 = 1;
  if ( HasOption )
  {
    v31 = L"remote";
    v32 = 6;
    *(_QWORD *)pfSave = L"r";
    if ( !(unsigned __int8)CommandArguments::HasOption(v6, pfSave, &v31) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_268a439894343dd91cd92e0ef272a5e3_Traceguids, 87);
      }
      EvtException::EvtException((EvtException *)&pExceptionObject, 0x57u, 0, 0, ulUserBufferSize, 38, 0x42u, 0);
      throw (EvtException *)&pExceptionObject;
    }
  }
  else
  {
    v31 = L"password";
    v32 = 8;
    *(_QWORD *)pfSave = L"p";
    if ( (unsigned __int8)CommandArguments::HasOption(v6, pfSave, &v31) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_268a439894343dd91cd92e0ef272a5e3_Traceguids, 87);
      }
      EvtException::EvtException((EvtException *)&pExceptionObject, 0x57u, 0, 0, ulUserBufferSize, 45, 0x43u, 0);
      throw (EvtException *)&pExceptionObject;
    }
  }
  v31 = L"remote";
  v32 = 6;
  *(_QWORD *)pfSave = L"r";
  v30 = 1;
  if ( (unsigned __int8)CommandArguments::HasOption(*((_QWORD *)this + 1), pfSave, &v31) )
  {
    pExceptionObject = 0;
    v34 = 0;
    v35 = 0;
    v31 = L"r";
    v32 = 1;
    *(_QWORD *)pfSave = L"remote";
    v30 = 6;
    *(_QWORD *)&pExceptionObject = CommandArguments::GetOptionString(
                                     *((_QWORD *)this + 1),
                                     (unsigned int)pfSave,
                                     (unsigned int)&v31,
                                     0,
                                     (__int64)v28);
    v31 = L"u";
    v32 = 1;
    *(_QWORD *)pfSave = L"username";
    v30 = 8;
    *((_QWORD *)&pExceptionObject + 1) = CommandArguments::GetOptionString(
                                           *((_QWORD *)this + 1),
                                           (unsigned int)pfSave,
                                           (unsigned int)&v31,
                                           0,
                                           (__int64)v28);
    v34 = 0;
    v31 = L"a";
    v32 = 1;
    *(_QWORD *)pfSave = L"Authentication";
    v30 = 14;
    OptionString = (const wchar_t *)CommandArguments::GetOptionString(
                                      *((_QWORD *)this + 1),
                                      (unsigned int)pfSave,
                                      (unsigned int)&v31,
                                      0,
                                      (__int64)v28);
    *(_QWORD *)pfSave = OptionString;
    if ( !OptionString )
    {
      *(_QWORD *)pfSave = L"Default";
      OptionString = L"Default";
    }
    v8 = -1;
    v9 = -1;
    do
      ++v9;
    while ( OptionString[v9] );
    if ( v9 == 7 )
    {
      if ( !(unsigned int)tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>::compare(
                            OptionString,
                            L"Default",
                            7) )
      {
        LODWORD(v35) = 0;
        goto LABEL_32;
      }
    }
    else if ( v9 == 9 )
    {
      if ( !(unsigned int)tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>::compare(
                            OptionString,
                            L"Negotiate",
                            9) )
      {
        LODWORD(v35) = 1;
        goto LABEL_32;
      }
    }
    else if ( v9 == 8
           && !(unsigned int)tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>::compare(
                               OptionString,
                               L"Kerberos",
                               8) )
    {
      LODWORD(v35) = 2;
      goto LABEL_32;
    }
    if ( !(unsigned __int8)tlx::string_equal_to_base<tlx::ascii_toupper_transform>::operator()<wchar_t const *,wchar_t [5],wchar_t,wchar_t,0>(
                             OptionString,
                             pfSave,
                             L"NTLM") )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_268a439894343dd91cd92e0ef272a5e3_Traceguids, 87);
      }
      EvtException::EvtException((EvtException *)v36, 0x57u, 0, 0, ulUserBufferSizea, 87, 0x23u, L"Authentication");
      throw (EvtException *)v36;
    }
    LODWORD(v35) = 3;
LABEL_32:
    v39 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v39) = 0;
    v10 = (wchar_t *)*((_QWORD *)&pExceptionObject + 1);
    if ( *((_QWORD *)&pExceptionObject + 1) )
    {
      if ( **((_WORD **)&pExceptionObject + 1) )
      {
        v14 = -1;
        do
          ++v14;
        while ( *(_WORD *)(*((_QWORD *)&pExceptionObject + 1) + 2 * v14) );
        if ( v14 > 0x201 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_268a439894343dd91cd92e0ef272a5e3_Traceguids, 2202);
          }
          EvtException::EvtException((EvtException *)v36, 0x89Au, 0, 0, ulUserBufferSizea, 102, 0x13u, 0);
          throw (EvtException *)v36;
        }
        v15 = wcschr(*((const wchar_t **)&pExceptionObject + 1), 0x5Cu);
        v16 = v15;
        if ( v15 )
        {
          std::wstring::_Assign<wchar_t>(
            &v39,
            *((_QWORD *)&pExceptionObject + 1),
            ((__int64)v15 - *((_QWORD *)&pExceptionObject + 1)) >> 1);
          v17 = &v39;
          if ( si128.m128i_i64[1] > 7uLL )
            v17 = (__int128 *)v39;
          *(_QWORD *)&v34 = v17;
          v10 = v16 + 1;
          *((_QWORD *)&pExceptionObject + 1) = v10;
        }
        else
        {
          v10 = (wchar_t *)*((_QWORD *)&pExceptionObject + 1);
        }
LABEL_36:
        memset_0(pszPassword, 0, 0x202u);
        v37 = pszPassword;
        v38 = 1;
        if ( !v10 )
        {
LABEL_86:
          v24 = EvtOpenSession(EvtRpcLogin, &pExceptionObject, 0, 0);
          tlx::unique_any<tlx::handle_traits<void *,int (void *),&int EvtClose(void *),0>>::reset(
            (char *)this + 24,
            v24);
          if ( !*((_QWORD *)this + 3) )
          {
            LastError = GetLastError();
            if ( !LastError )
              LastError = 1287;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                18,
                WPP_268a439894343dd91cd92e0ef272a5e3_Traceguids,
                LastError);
            }
            EvtException::EvtException(
              (EvtException *)v36,
              LastError,
              0,
              0,
              ulUserBufferSizea,
              195,
              0x12u,
              (const wchar_t *)pExceptionObject);
            throw (EvtException *)v36;
          }
          tlx::_UndoSolo__CommandBase::Run_::_25_::_lambda_1___::__UndoSolo__CommandBase::Run_::_25_::_lambda_1___(&v37);
          std::wstring::_Tidy_deallocate(&v39);
          goto LABEL_95;
        }
        v28[0] = 0;
        v31 = L"p";
        v32 = 1;
        *(_QWORD *)pfSave = L"password";
        v30 = 8;
        v11 = (_WORD *)CommandArguments::GetOptionString(
                         *((_QWORD *)this + 1),
                         (unsigned int)pfSave,
                         (unsigned int)&v31,
                         0,
                         (__int64)v28);
        v12 = v11;
        if ( v28[0] && v11 && *v11 )
        {
          v13 = -1;
          do
            ++v13;
          while ( *(_WORD *)&v12[2 * v13] );
          if ( v13 > 0x100 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_268a439894343dd91cd92e0ef272a5e3_Traceguids, 86);
            }
            EvtException::EvtException((EvtException *)v36, 0x56u, 0, 0, ulUserBufferSizea, 141, 0x13u, 0);
            throw (EvtException *)v36;
          }
          _o_wcscpy_s(pszPassword, 257, v12);
          v18 = pszPassword;
          *((_QWORD *)&v34 + 1) = pszPassword;
          v19 = -1;
          do
            ++v19;
          while ( *(_WORD *)&v12[2 * v19] );
          v20 = 2 * v19;
          if ( !v20 )
            goto LABEL_66;
          do
          {
            *v12++ = 0;
            --v20;
          }
          while ( v20 );
        }
        v18 = (WCHAR *)*((_QWORD *)&v34 + 1);
        if ( !*((_QWORD *)&v34 + 1) )
        {
LABEL_69:
          pfSave[0] = 0;
          if ( !(unsigned __int8)IsCredUICmdLinePromptForCredentialsWPresent() )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_268a439894343dd91cd92e0ef272a5e3_Traceguids, 50);
            }
            EvtException::EvtException((EvtException *)v36, 0x32u, 0, 0, ulUserBufferSizea, 161, 0x57u, 0);
            throw (EvtException *)v36;
          }
          v22 = &ValueName;
          if ( (_QWORD)pExceptionObject )
            v22 = (const WCHAR *)pExceptionObject;
          *(_QWORD *)&pExceptionObject = v22;
          do
            ++v8;
          while ( *(_WORD *)(*((_QWORD *)&pExceptionObject + 1) + 2 * v8) );
          v23 = CredUICmdLinePromptForCredentialsW(
                  v22,
                  0,
                  0,
                  *((PWSTR *)&pExceptionObject + 1),
                  v8 + 1,
                  pszPassword,
                  0x101u,
                  pfSave,
                  0x4020Au);
          if ( v23 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_268a439894343dd91cd92e0ef272a5e3_Traceguids, v23);
            }
            EvtException::EvtException((EvtException *)v36, v23, 0, 0, ulUserBufferSizea, 184, 0x13u, 0);
            throw (EvtException *)v36;
          }
          *((_QWORD *)&v34 + 1) = pszPassword;
          goto LABEL_86;
        }
LABEL_66:
        v21 = *v18 - 42;
        if ( *v18 == 42 )
          v21 = v18[1];
        if ( v21 )
          goto LABEL_86;
        goto LABEL_69;
      }
      v10 = 0;
      *((_QWORD *)&pExceptionObject + 1) = 0;
    }
    *((_QWORD *)&v34 + 1) = 0;
    goto LABEL_36;
  }
LABEL_95:
  (*(void (__fastcall **)(CommandBase *))(*(_QWORD *)this + 16LL))(this);
}

```

## disassembly

```asm
0x14001b75c  push    rbp
0x14001b75e  push    rbx
0x14001b75f  push    rsi
0x14001b760  push    rdi
0x14001b761  push    r12
0x14001b763  push    r13
0x14001b765  push    r14
0x14001b767  push    r15
0x14001b769  lea     rbp, [rsp-228h]
0x14001b771  sub     rsp, 328h
0x14001b778  mov     rax, cs:__security_cookie
0x14001b77f  xor     rax, rsp
0x14001b782  mov     [rbp+260h+var_50], rax
0x14001b789  mov     rax, rdx
0x14001b78c  mov     rdi, rcx
0x14001b78f  mov     [rcx+8], rdx
0x14001b793  lea     rcx, aUni; "uni"
0x14001b79a  mov     qword ptr [rsp+360h+var_300], rcx
0x14001b79f  mov     [rsp+360h+var_2F8], 3
0x14001b7a8  lea     rcx, aUnicode; "unicode"
0x14001b7af  mov     [rsp+360h+var_2F0], rcx
0x14001b7b4  mov     [rsp+360h+var_2E8], 7
0x14001b7bd  lea     rcx, [rsp+360h+var_310]
0x14001b7c2  mov     qword ptr [rsp+360h+ulUserBufferSize], rcx; char *
0x14001b7c7  lea     r8, [rsp+360h+var_300]
0x14001b7cc  lea     rdx, [rsp+360h+var_2F0]
0x14001b7d1  mov     rcx, rax
0x14001b7d4  call    ?GetOptionBool@CommandArguments@@QEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0_NAEA_N@Z; CommandArguments::GetOptionBool(std::wstring_view,std::wstring_view,bool,bool &)
0x14001b7d9  mov     cs:?g_outputUnicode@@3_NA, al; bool g_outputUnicode
0x14001b7df  mov     rax, [rdi]
0x14001b7e2  mov     rcx, rdi
0x14001b7e5  mov     rax, [rax+8]
0x14001b7e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b7ee  xor     r14d, r14d
0x14001b7f1  cmp     cs:?g_outputUnicode@@3_NA, r14b; bool g_outputUnicode
0x14001b7f8  jz      short loc_14001B803
0x14001b7fa  mov     rcx, [rdi+10h]; void *
0x14001b7fe  call    ?WriteBOM@@YAXPEAX@Z; WriteBOM(void *)
0x14001b803  lea     rax, aUsername; "username"
0x14001b80a  mov     [rsp+360h+var_2F0], rax
0x14001b80f  mov     r12d, 8
0x14001b815  mov     [rsp+360h+var_2E8], r12
0x14001b81a  lea     rax, aU; "u"
0x14001b821  mov     qword ptr [rsp+360h+var_300], rax
0x14001b826  lea     r15d, [r12-7]
0x14001b82b  mov     [rsp+360h+var_2F8], r15
0x14001b830  lea     r8, [rsp+360h+var_2F0]
0x14001b835  lea     rdx, [rsp+360h+var_300]
0x14001b83a  mov     rcx, [rdi+8]
0x14001b83e  call    ?HasOption@CommandArguments@@QEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; CommandArguments::HasOption(std::wstring_view,std::wstring_view)
0x14001b843  mov     rcx, [rdi+8]
0x14001b847  lea     rbx, aRemote; "remote"
0x14001b84e  lea     esi, [r12-2]
0x14001b853  lea     r13, aR; "r"
0x14001b85a  lea     rdx, aPassword; "password"
0x14001b861  lea     r8, aP; "p"
0x14001b868  mov     [rsp+360h+var_2F8], r15
0x14001b86d  test    al, al
0x14001b86f  jz      loc_14001B90D
0x14001b875  mov     [rsp+360h+var_2F0], rbx
0x14001b87a  mov     [rsp+360h+var_2E8], rsi
0x14001b87f  mov     qword ptr [rsp+360h+var_300], r13
0x14001b884  lea     r8, [rsp+360h+var_2F0]
0x14001b889  lea     rdx, [rsp+360h+var_300]
0x14001b88e  call    ?HasOption@CommandArguments@@QEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; CommandArguments::HasOption(std::wstring_view,std::wstring_view)
0x14001b893  test    al, al
0x14001b895  jnz     loc_14001B9A3
0x14001b89b  lea     rax, WPP_GLOBAL_Control
0x14001b8a2  lea     ebx, [rsi+51h]
0x14001b8a5  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b8ac  cmp     rcx, rax
0x14001b8af  jz      short loc_14001B8D6
0x14001b8b1  test    dword ptr [rcx+1Ch], 400000h
0x14001b8b8  jz      short loc_14001B8D6
0x14001b8ba  cmp     byte ptr [rcx+19h], 2
0x14001b8be  jb      short loc_14001B8D6
0x14001b8c0  lea     edx, [rsi+5]
0x14001b8c3  mov     r9d, ebx
0x14001b8c6  lea     r8, WPP_268a439894343dd91cd92e0ef272a5e3_Traceguids
0x14001b8cd  mov     rcx, [rcx+10h]
0x14001b8d1  call    WPP_SF_d
0x14001b8d6  mov     [rsp+360h+pfSave], r14; Src
0x14001b8db  mov     [rsp+360h+ulPasswordBufferSize], 42h ; 'B'; unsigned int
0x14001b8e3  mov     dword ptr [rsp+360h+pszPassword], 26h ; '&'; int
0x14001b8eb  xor     r9d, r9d; unsigned int
0x14001b8ee  xor     r8d, r8d; unsigned int
0x14001b8f1  mov     edx, ebx; unsigned int
0x14001b8f3  lea     rcx, [rbp+260h+pExceptionObject]; this
0x14001b8f7  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14001b8fc  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14001b903  lea     rcx, [rbp+260h+pExceptionObject]; pExceptionObject
0x14001b907  call    _CxxThrowException_0
0x14001b90d  mov     [rsp+360h+var_2F0], rdx
0x14001b912  mov     [rsp+360h+var_2E8], r12
0x14001b917  mov     qword ptr [rsp+360h+var_300], r8
0x14001b91c  lea     r8, [rsp+360h+var_2F0]
0x14001b921  lea     rdx, [rsp+360h+var_300]
0x14001b926  call    ?HasOption@CommandArguments@@QEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; CommandArguments::HasOption(std::wstring_view,std::wstring_view)
0x14001b92b  test    al, al
0x14001b92d  jz      short loc_14001B9A3
0x14001b92f  lea     rax, WPP_GLOBAL_Control
0x14001b936  mov     ebx, 57h ; 'W'
0x14001b93b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b942  cmp     rcx, rax
0x14001b945  jz      short loc_14001B96C
0x14001b947  test    dword ptr [rcx+1Ch], 400000h
0x14001b94e  jz      short loc_14001B96C
0x14001b950  cmp     byte ptr [rcx+19h], 2
0x14001b954  jb      short loc_14001B96C
0x14001b956  lea     edx, [rbx-4Bh]
0x14001b959  mov     r9d, ebx
0x14001b95c  lea     r8, WPP_268a439894343dd91cd92e0ef272a5e3_Traceguids
0x14001b963  mov     rcx, [rcx+10h]
0x14001b967  call    WPP_SF_d
0x14001b96c  mov     [rsp+360h+pfSave], r14; Src
0x14001b971  mov     [rsp+360h+ulPasswordBufferSize], 43h ; 'C'; unsigned int
0x14001b979  mov     dword ptr [rsp+360h+pszPassword], 2Dh ; '-'; int
0x14001b981  xor     r9d, r9d; unsigned int
0x14001b984  xor     r8d, r8d; unsigned int
0x14001b987  mov     edx, ebx; unsigned int
0x14001b989  lea     rcx, [rbp+260h+pExceptionObject]; this
0x14001b98d  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14001b992  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14001b999  lea     rcx, [rbp+260h+pExceptionObject]; pExceptionObject
0x14001b99d  call    _CxxThrowException_0
0x14001b9a3  mov     [rsp+360h+var_2F0], rbx
0x14001b9a8  mov     [rsp+360h+var_2E8], rsi
0x14001b9ad  mov     qword ptr [rsp+360h+var_300], r13
0x14001b9b2  mov     [rsp+360h+var_2F8], r15
0x14001b9b7  lea     r8, [rsp+360h+var_2F0]
0x14001b9bc  lea     rdx, [rsp+360h+var_300]
0x14001b9c1  mov     rcx, [rdi+8]
0x14001b9c5  call    ?HasOption@CommandArguments@@QEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; CommandArguments::HasOption(std::wstring_view,std::wstring_view)
0x14001b9ca  test    al, al
0x14001b9cc  jz      loc_14001BFFD
0x14001b9d2  xorps   xmm0, xmm0
0x14001b9d5  xor     eax, eax
0x14001b9d7  movups  [rbp+260h+pExceptionObject], xmm0
0x14001b9db  movups  [rbp+260h+var_2D0], xmm0
0x14001b9df  mov     [rbp+260h+var_2C0], rax
0x14001b9e3  mov     [rsp+360h+var_2F0], r13
0x14001b9e8  mov     [rsp+360h+var_2E8], r15
0x14001b9ed  mov     qword ptr [rsp+360h+var_300], rbx
0x14001b9f2  mov     [rsp+360h+var_2F8], rsi
0x14001b9f7  lea     rax, [rsp+360h+var_310]
0x14001b9fc  mov     qword ptr [rsp+360h+ulUserBufferSize], rax
0x14001ba01  xor     r9d, r9d
0x14001ba04  lea     r8, [rsp+360h+var_2F0]
0x14001ba09  lea     rdx, [rsp+360h+var_300]
0x14001ba0e  mov     rcx, [rdi+8]
0x14001ba12  call    ?GetOptionString@CommandArguments@@QEBAPEB_WV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0PEB_WAEA_N@Z; CommandArguments::GetOptionString(std::wstring_view,std::wstring_view,wchar_t const *,bool &)
0x14001ba17  mov     qword ptr [rbp+260h+pExceptionObject], rax
0x14001ba1b  lea     rax, aU; "u"
0x14001ba22  mov     [rsp+360h+var_2F0], rax
0x14001ba27  mov     [rsp+360h+var_2E8], r15
0x14001ba2c  lea     rax, aUsername; "username"
0x14001ba33  mov     qword ptr [rsp+360h+var_300], rax
0x14001ba38  mov     [rsp+360h+var_2F8], r12
0x14001ba3d  lea     rax, [rsp+360h+var_310]
0x14001ba42  mov     qword ptr [rsp+360h+ulUserBufferSize], rax
0x14001ba47  xor     r9d, r9d
0x14001ba4a  lea     r8, [rsp+360h+var_2F0]
0x14001ba4f  lea     rdx, [rsp+360h+var_300]
0x14001ba54  mov     rcx, [rdi+8]
0x14001ba58  call    ?GetOptionString@CommandArguments@@QEBAPEB_WV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0PEB_WAEA_N@Z; CommandArguments::GetOptionString(std::wstring_view,std::wstring_view,wchar_t const *,bool &)
0x14001ba5d  mov     qword ptr [rbp+260h+pExceptionObject+8], rax
0x14001ba61  xorps   xmm0, xmm0
0x14001ba64  movdqu  [rbp+260h+var_2D0], xmm0
0x14001ba69  lea     rax, aA; "a"
0x14001ba70  mov     [rsp+360h+var_2F0], rax
0x14001ba75  mov     [rsp+360h+var_2E8], r15
0x14001ba7a  lea     r13, aAuthentication; "Authentication"
0x14001ba81  mov     qword ptr [rsp+360h+var_300], r13
0x14001ba86  mov     [rsp+360h+var_2F8], 0Eh
0x14001ba8f  lea     rax, [rsp+360h+var_310]
0x14001ba94  mov     qword ptr [rsp+360h+ulUserBufferSize], rax; char *
0x14001ba99  xor     r9d, r9d
0x14001ba9c  lea     r8, [rsp+360h+var_2F0]
0x14001baa1  lea     rdx, [rsp+360h+var_300]
0x14001baa6  mov     rcx, [rdi+8]
0x14001baaa  call    ?GetOptionString@CommandArguments@@QEBAPEB_WV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0PEB_WAEA_N@Z; CommandArguments::GetOptionString(std::wstring_view,std::wstring_view,wchar_t const *,bool &)
0x14001baaf  mov     rcx, rax
0x14001bab2  mov     qword ptr [rsp+360h+var_300], rax
0x14001bab7  lea     rdx, aDefault; "Default"
0x14001babe  test    rax, rax
0x14001bac1  jnz     short loc_14001BACB
0x14001bac3  mov     qword ptr [rsp+360h+var_300], rdx
0x14001bac8  mov     rcx, rdx
0x14001bacb  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14001bacf  mov     rax, rsi
0x14001bad2  inc     rax
0x14001bad5  cmp     [rcx+rax*2], r14w
0x14001bada  jnz     short loc_14001BAD2
0x14001badc  cmp     rax, 7
0x14001bae0  jnz     short loc_14001BAF4
0x14001bae2  mov     r8, rax
0x14001bae5  call    ?compare@?$transform_traits@_WUascii_toupper_transform@tlx@@@tlx@@SAHPEB_W0_K@Z; tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>::compare(wchar_t const *,wchar_t const *,unsigned __int64)
0x14001baea  test    eax, eax
0x14001baec  jnz     short loc_14001BB36
0x14001baee  mov     dword ptr [rbp+260h+var_2C0], r14d
0x14001baf2  jmp     short loc_14001BB56
0x14001baf4  mov     r8d, 9
0x14001bafa  cmp     rax, r8
0x14001bafd  jnz     short loc_14001BB15
0x14001baff  lea     rdx, aNegotiate; "Negotiate"
0x14001bb06  call    ?compare@?$transform_traits@_WUascii_toupper_transform@tlx@@@tlx@@SAHPEB_W0_K@Z; tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>::compare(wchar_t const *,wchar_t const *,unsigned __int64)
0x14001bb0b  test    eax, eax
0x14001bb0d  jnz     short loc_14001BB36
0x14001bb0f  mov     dword ptr [rbp+260h+var_2C0], r15d
0x14001bb13  jmp     short loc_14001BB56
0x14001bb15  cmp     rax, r12
0x14001bb18  jnz     short loc_14001BB36
0x14001bb1a  mov     r8, r12
0x14001bb1d  lea     rdx, aKerberos; "Kerberos"
0x14001bb24  call    ?compare@?$transform_traits@_WUascii_toupper_transform@tlx@@@tlx@@SAHPEB_W0_K@Z; tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>::compare(wchar_t const *,wchar_t const *,unsigned __int64)
0x14001bb29  test    eax, eax
0x14001bb2b  jnz     short loc_14001BB36
0x14001bb2d  mov     dword ptr [rbp+260h+var_2C0], 2
0x14001bb34  jmp     short loc_14001BB56
0x14001bb36  lea     r8, aNtlm; "NTLM"
0x14001bb3d  lea     rdx, [rsp+360h+var_300]
0x14001bb42  call    ??$?RPEB_W$$BY04_W_W_W$0A@@?$string_equal_to_base@Uascii_toupper_transform@tlx@@@tlx@@QEBA_NAEBQEB_WAEAY04$$CB_W@Z; tlx::string_equal_to_base<tlx::ascii_toupper_transform>::operator()<wchar_t const *,wchar_t [5],wchar_t,wchar_t,0>(wchar_t const * const &,wchar_t const (&)[5])
0x14001bb47  test    al, al
0x14001bb49  jz      loc_14001C02F
0x14001bb4f  mov     dword ptr [rbp+260h+var_2C0], 3
0x14001bb56  xorps   xmm0, xmm0
0x14001bb59  movups  [rbp+260h+var_280], xmm0
0x14001bb5d  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x14001bb65  movdqu  [rbp+260h+var_270], xmm1
0x14001bb6a  mov     word ptr [rbp+260h+var_280], r14w
0x14001bb6f  mov     rbx, qword ptr [rbp+260h+pExceptionObject+8]
0x14001bb73  test    rbx, rbx
0x14001bb76  jz      short loc_14001BB89
0x14001bb78  cmp     [rbx], r14w
0x14001bb7c  jnz     loc_14001BCAE
0x14001bb82  mov     rbx, r14
0x14001bb85  mov     qword ptr [rbp+260h+pExceptionObject+8], rbx
0x14001bb89  mov     qword ptr [rbp+260h+var_2D0+8], r14
0x14001bb8d  xor     edx, edx; Val
0x14001bb8f  mov     r8d, 202h; Size
0x14001bb95  lea     rcx, [rbp+260h+var_260]; void *
0x14001bb99  call    memset_0
0x14001bb9e  lea     rax, [rbp+260h+var_260]
0x14001bba2  mov     [rbp+260h+var_290], rax
0x14001bba6  mov     [rbp+260h+var_288], r15b
0x14001bbaa  test    rbx, rbx
0x14001bbad  jz      loc_14001BF3C
0x14001bbb3  mov     [rsp+360h+var_310], r14b
0x14001bbb8  lea     rax, aP; "p"
0x14001bbbf  mov     [rsp+360h+var_2F0], rax
0x14001bbc4  mov     [rsp+360h+var_2E8], r15
0x14001bbc9  lea     rax, aPassword; "password"
0x14001bbd0  mov     qword ptr [rsp+360h+var_300], rax
0x14001bbd5  mov     [rsp+360h+var_2F8], r12
0x14001bbda  lea     rax, [rsp+360h+var_310]
0x14001bbdf  mov     qword ptr [rsp+360h+ulUserBufferSize], rax; char *
0x14001bbe4  xor     r9d, r9d
0x14001bbe7  lea     r8, [rsp+360h+var_2F0]
0x14001bbec  lea     rdx, [rsp+360h+var_300]
0x14001bbf1  mov     rcx, [rdi+8]
0x14001bbf5  call    ?GetOptionString@CommandArguments@@QEBAPEB_WV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0PEB_WAEA_N@Z; CommandArguments::GetOptionString(std::wstring_view,std::wstring_view,wchar_t const *,bool &)
0x14001bbfa  mov     rbx, rax
0x14001bbfd  mov     r12d, 101h
0x14001bc03  cmp     [rsp+360h+var_310], r14b
0x14001bc08  jz      loc_14001BDC2
0x14001bc0e  test    rax, rax
0x14001bc11  jz      loc_14001BDC2
0x14001bc17  cmp     [rax], r14w
0x14001bc1b  jz      loc_14001BDC2
0x14001bc21  mov     rax, rsi
0x14001bc24  inc     rax
0x14001bc27  cmp     [rbx+rax*2], r14w
0x14001bc2c  jnz     short loc_14001BC24
0x14001bc2e  cmp     rax, 100h
0x14001bc34  jbe     loc_14001BD8D
0x14001bc3a  lea     rax, WPP_GLOBAL_Control
0x14001bc41  mov     ebx, 56h ; 'V'
0x14001bc46  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bc4d  cmp     rcx, rax
0x14001bc50  jz      short loc_14001BC77
0x14001bc52  test    dword ptr [rcx+1Ch], 400000h
0x14001bc59  jz      short loc_14001BC77
0x14001bc5b  cmp     byte ptr [rcx+19h], 2
0x14001bc5f  jb      short loc_14001BC77
0x14001bc61  lea     edx, [rbx-47h]
0x14001bc64  mov     r9d, ebx
0x14001bc67  lea     r8, WPP_268a439894343dd91cd92e0ef272a5e3_Traceguids
0x14001bc6e  mov     rcx, [rcx+10h]
0x14001bc72  call    WPP_SF_d
0x14001bc77  mov     [rsp+360h+pfSave], r14; Src
0x14001bc7c  mov     [rsp+360h+ulPasswordBufferSize], 13h; unsigned int
0x14001bc84  mov     dword ptr [rsp+360h+pszPassword], 8Dh; int
0x14001bc8c  xor     r9d, r9d; unsigned int
0x14001bc8f  xor     r8d, r8d; unsigned int
0x14001bc92  mov     edx, ebx; unsigned int
0x14001bc94  lea     rcx, [rbp+260h+var_2B8]; this
0x14001bc98  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14001bc9d  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14001bca4  lea     rcx, [rbp+260h+var_2B8]; pExceptionObject
0x14001bca8  call    _CxxThrowException_0
  ... truncated ...
```
