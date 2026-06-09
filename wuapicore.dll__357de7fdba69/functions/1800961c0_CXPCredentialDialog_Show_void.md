# CXPCredentialDialog::Show(void)

- ea: `0x1800961c0`
- end: `0x1800965a9`
- name: `?Show@CXPCredentialDialog@@UEAAJXZ`
- size: `1001`
- prototype: `__int64 __fastcall(CXPCredentialDialog *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x180005bc0`
- `0x1800961c0`
- `0x180096bb0`
- `0x18009ae75`
- `0x18009b050`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096450`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096450`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800963b7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800963b7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18009639a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18009639a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800962fa`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180096442`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800962fa`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180096442`
- `OLEAUT32!__imp_SysFreeString` at `0x1800964ad`
- `OLEAUT32!__imp_SysFreeString` at `0x180096544`
- `OLEAUT32!__imp_SysFreeString` at `0x1800964ad`
- `OLEAUT32!__imp_SysFreeString` at `0x180096544`
- `OLEAUT32!__imp_SysStringLen` at `0x180096282`
- `OLEAUT32!__imp_SysStringLen` at `0x180096338`
- `OLEAUT32!__imp_SysStringLen` at `0x180096282`
- `OLEAUT32!__imp_SysStringLen` at `0x180096338`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18009649b`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180096532`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18009649b`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180096532`

## string_xrefs

- `0x18009638d`: `credui.dll`

## pseudocode

```c
__int64 __fastcall CXPCredentialDialog::Show(CXPCredentialDialog *this)
{
  OLECHAR *v2; // rcx
  unsigned int v3; // esi
  __int64 v4; // rdx
  WCHAR *v5; // rcx
  __int64 v6; // r9
  WCHAR v7; // ax
  WCHAR *v8; // rax
  HINSTANCE v9; // rax
  void **v10; // r14
  OLECHAR *v11; // rcx
  signed __int64 v12; // rdi
  wchar_t *v13; // rcx
  __int64 v14; // rdx
  wchar_t v15; // ax
  wchar_t *v16; // rax
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  int v19; // ecx
  HINSTANCE LocResourceInstance; // rax
  signed int LastError; // eax
  signed int v22; // ecx
  unsigned int v24; // eax
  int v25; // eax
  __int64 (__fastcall ***v26)(_QWORD, void *); // rcx
  int v27; // r14d
  BSTR v28; // rsi
  BSTR bstr; // [rsp+68h] [rbp-A0h] BYREF
  _DWORD v30[2]; // [rsp+70h] [rbp-98h] BYREF
  __int64 v31; // [rsp+78h] [rbp-90h]
  WCHAR *v32; // [rsp+80h] [rbp-88h]
  WCHAR *v33; // [rsp+88h] [rbp-80h]
  __int64 v34; // [rsp+90h] [rbp-78h]
  int v35[4]; // [rsp+98h] [rbp-70h] BYREF
  _OWORD v36[5]; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v37; // [rsp+F8h] [rbp-10h]
  WCHAR v38[136]; // [rsp+108h] [rbp+0h] BYREF
  wchar_t v39[264]; // [rsp+218h] [rbp+110h] BYREF
  wchar_t v40[520]; // [rsp+428h] [rbp+320h] BYREF
  WCHAR Buffer[200]; // [rsp+838h] [rbp+730h] BYREF

  v36[0] = *(_OWORD *)L"SUS Client Proxy Authentication Credentials";
  v36[2] = *(_OWORD *)L" Authentication Credentials";
  v36[4] = *(_OWORD *)L"Credentials";
  v36[1] = *(_OWORD *)L"nt Proxy Authentication Credentials";
  v37 = *(_QWORD *)L"als";
  v36[3] = *(_OWORD *)L"ication Credentials";
  v40[0] = 0;
  memset_0(&v40[1], 0, 0x402u);
  v39[0] = 0;
  memset_0(&v39[1], 0, 0x200u);
  v2 = (OLECHAR *)*((_QWORD *)this + 3);
  v35[0] = 0;
  v30[1] = 0;
  v3 = 1;
  if ( SysStringLen(v2) )
  {
    v4 = *((_QWORD *)this + 3) - (_QWORD)v38;
    v5 = v38;
    v6 = 129;
    do
    {
      if ( v6 == -2147483517 )
        break;
      v7 = *(WCHAR *)((char *)v5 + v4);
      if ( !v7 )
        break;
      *v5++ = v7;
      --v6;
    }
    while ( v6 );
    v8 = v5 - 1;
    if ( v6 )
      v8 = v5;
    *v8 = 0;
  }
  else
  {
    LocResourceInstance = CModuleResHelper::GetLocResourceInstance((CModuleResHelper *)&qword_1800EEF18);
    if ( !LoadStringW(LocResourceInstance, 0xFC14u, v38, 129) )
      goto LABEL_23;
  }
  v9 = CModuleResHelper::GetLocResourceInstance((CModuleResHelper *)&qword_1800EEF18);
  if ( LoadStringW(v9, 0xFC13u, Buffer, 200) )
  {
    v30[0] = 40;
    v32 = Buffer;
    v10 = (void **)((char *)this + 40);
    v11 = (OLECHAR *)*((_QWORD *)this + 5);
    v33 = v38;
    v31 = *((_QWORD *)this + 1);
    v34 = 0;
    if ( SysStringLen(v11) )
    {
      v12 = (_BYTE *)*v10 - (_BYTE *)v40;
      v13 = v40;
      v14 = 514;
      do
      {
        if ( v14 == -2147483132 )
          break;
        v15 = *(wchar_t *)((char *)v13 + v12);
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
    }
    Library = LoadLibraryExW(L"credui.dll", 0, 0x800u);
    *((_QWORD *)this + 6) = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "CredUIPromptForCredentialsW");
      if ( ProcAddress )
      {
        v19 = ((__int64 (__fastcall *)(_DWORD *, _OWORD *, _QWORD, _QWORD, wchar_t *, int, wchar_t *, int, int *, int))ProcAddress)(
                v30,
                v36,
                0,
                0,
                v40,
                514,
                v39,
                257,
                v35,
                262274);
        if ( v19 == 1223 )
        {
          *((_DWORD *)this + 8) = 1;
        }
        else if ( v19 )
        {
          v24 = (unsigned __int16)v19 | 0x80070000;
          if ( v19 <= 0 )
            v24 = v19;
          *((_DWORD *)this + 8) = v24;
          v3 = v24;
        }
        else
        {
          if ( *v10 )
          {
            memset(*v10, 0, SysStringByteLen((BSTR)*v10));
            SysFreeString((BSTR)*v10);
            *v10 = 0;
          }
          v25 = SusSysAllocString(v40, (wchar_t **)this + 5);
          if ( v25 >= 0 )
          {
            v26 = (__int64 (__fastcall ***)(_QWORD, void *))*((_QWORD *)this + 2);
            if ( v26 )
              v25 = (**v26)(v26, *v10);
          }
          *((_DWORD *)this + 8) = v25;
          v3 = v25;
          if ( v25 >= 0 )
          {
            v27 = 0;
            if ( *((_QWORD *)this + 2) )
            {
              bstr = 0;
              v27 = SusSysAllocString(v39, &bstr);
              if ( v27 >= 0 )
              {
                v28 = bstr;
                v27 = (*(__int64 (__fastcall **)(_QWORD, BSTR))(**((_QWORD **)this + 2) + 8LL))(
                        *((_QWORD *)this + 2),
                        bstr);
                if ( v28 )
                {
                  memset(v28, 0, SysStringByteLen(v28));
                  SysFreeString(v28);
                }
              }
            }
            *((_DWORD *)this + 8) = v27;
            v3 = v27;
            if ( v27 >= 0 )
            {
              *((_DWORD *)this + 8) = 0;
              v3 = 0;
            }
          }
        }
        memset(v40, 0, 0x404u);
        memset(v39, 0, 0x202u);
        return v3;
      }
    }
  }
LABEL_23:
  LastError = GetLastError();
  v22 = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    v22 = LastError;
  if ( v22 >= 0 )
    v22 = -2147418113;
  *((_DWORD *)this + 8) = v22;
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x1800961c0  mov     rax, rsp
0x1800961c3  mov     [rax+10h], rbx
0x1800961c7  mov     [rax+18h], rsi
0x1800961cb  mov     [rax+20h], rdi
0x1800961cf  push    rbp
0x1800961d0  push    r14
0x1800961d2  push    r15
0x1800961d4  lea     rbp, [rax-8E8h]
0x1800961db  sub     rsp, 9D0h
0x1800961e2  mov     rax, cs:__security_cookie
0x1800961e9  xor     rax, rsp
0x1800961ec  mov     [rbp+8E0h+var_20], rax
0x1800961f3  movaps  xmm0, xmmword ptr cs:aSusClientProxy; "SUS Client Proxy Authentication Credent"...
0x1800961fa  mov     rbx, rcx
0x1800961fd  movaps  xmm1, xmmword ptr cs:aSusClientProxy+10h; "nt Proxy Authentication Credentials"
0x180096204  lea     rcx, [rbp+8E0h+var_5BE]; void *
0x18009620b  movaps  [rbp+8E0h+var_940], xmm0
0x18009620f  xor     r15d, r15d
0x180096212  movaps  xmm0, xmmword ptr cs:aSusClientProxy+20h; " Authentication Credentials"
0x180096219  xor     edx, edx; Val
0x18009621b  movaps  [rbp+8E0h+var_920], xmm0
0x18009621f  mov     r8d, 402h; Size
0x180096225  movaps  xmm0, xmmword ptr cs:aSusClientProxy+40h; "Credentials"
0x18009622c  movaps  [rbp+8E0h+var_900], xmm0
0x180096230  movsd   xmm0, qword ptr cs:aSusClientProxy+50h; "als"
0x180096238  movaps  [rbp+8E0h+var_930], xmm1
0x18009623c  movaps  xmm1, xmmword ptr cs:aSusClientProxy+30h; "ication Credentials"
0x180096243  movsd   [rbp+8E0h+var_8F0], xmm0
0x180096248  movaps  [rbp+8E0h+var_910], xmm1
0x18009624c  mov     [rbp+8E0h+var_5C0], r15w
0x180096254  call    memset_0
0x180096259  xor     edx, edx; Val
0x18009625b  mov     [rbp+8E0h+var_7D0], r15w
0x180096263  mov     r8d, 200h; Size
0x180096269  lea     rcx, [rbp+8E0h+var_7CE]; void *
0x180096270  call    memset_0
0x180096275  mov     rcx, [rbx+18h]; pbstr
0x180096279  mov     [rbp+8E0h+var_950], r15d
0x18009627d  mov     dword ptr [rsp+9E0h+var_978+4], r15d
0x180096282  call    cs:__imp_SysStringLen
0x180096288  lea     esi, [r15+1]
0x18009628c  test    eax, eax
0x18009628e  jz      loc_180096424
0x180096294  mov     rdx, [rbx+18h]
0x180096298  lea     rax, [rbp+8E0h+var_8E0]
0x18009629c  sub     rdx, rax
0x18009629f  lea     rcx, [rbp+8E0h+var_8E0]
0x1800962a3  mov     r9d, 81h
0x1800962a9  lea     rax, [r9+7FFFFF7Dh]
0x1800962b0  test    rax, rax
0x1800962b3  jz      short loc_1800962CA
0x1800962b5  movzx   eax, word ptr [rdx+rcx]
0x1800962b9  test    ax, ax
0x1800962bc  jz      short loc_1800962CA
0x1800962be  mov     [rcx], ax
0x1800962c1  add     rcx, 2
0x1800962c5  sub     r9, rsi
0x1800962c8  jnz     short loc_1800962A9
0x1800962ca  test    r9, r9
0x1800962cd  lea     rax, [rcx-2]
0x1800962d1  cmovnz  rax, rcx
0x1800962d5  mov     [rax], r15w
0x1800962d9  lea     rcx, qword_1800EEF18; this
0x1800962e0  call    ?GetLocResourceInstance@CModuleResHelper@@QEAAPEAUHINSTANCE__@@XZ; CModuleResHelper::GetLocResourceInstance(void)
0x1800962e5  mov     rcx, rax; hInstance
0x1800962e8  lea     r8, [rbp+8E0h+Buffer]; lpBuffer
0x1800962ef  mov     r9d, 0C8h; cchBufferMax
0x1800962f5  mov     edx, 0FC13h; uID
0x1800962fa  call    cs:__imp_LoadStringW
0x180096300  test    eax, eax
0x180096302  jz      loc_180096450
0x180096308  lea     rax, [rbp+8E0h+Buffer]
0x18009630f  mov     dword ptr [rsp+9E0h+var_978], 28h ; '('
0x180096317  mov     [rsp+9E0h+var_968], rax
0x18009631c  lea     r14, [rbx+28h]
0x180096320  mov     rcx, [r14]; pbstr
0x180096323  lea     rax, [rbp+8E0h+var_8E0]
0x180096327  mov     [rbp+8E0h+var_960], rax
0x18009632b  mov     rax, [rbx+8]
0x18009632f  mov     [rsp+9E0h+var_970], rax
0x180096334  mov     [rbp+8E0h+var_958], r15
0x180096338  call    cs:__imp_SysStringLen
0x18009633e  test    eax, eax
0x180096340  jz      short loc_18009638B
0x180096342  mov     rdi, [r14]
0x180096345  lea     rax, [rbp+8E0h+var_5C0]
0x18009634c  sub     rdi, rax
0x18009634f  lea     rcx, [rbp+8E0h+var_5C0]
0x180096356  mov     edx, 202h
0x18009635b  lea     rax, [rdx+7FFFFDFCh]
0x180096362  test    rax, rax
0x180096365  jz      short loc_18009637C
0x180096367  movzx   eax, word ptr [rcx+rdi]
0x18009636b  test    ax, ax
0x18009636e  jz      short loc_18009637C
0x180096370  mov     [rcx], ax
0x180096373  add     rcx, 2
0x180096377  sub     rdx, rsi
0x18009637a  jnz     short loc_18009635B
0x18009637c  test    rdx, rdx
0x18009637f  lea     rax, [rcx-2]
0x180096383  cmovnz  rax, rcx
0x180096387  mov     [rax], r15w
0x18009638b  xor     edx, edx; hFile
0x18009638d  lea     rcx, aCreduiDll; "credui.dll"
0x180096394  mov     r8d, 800h; dwFlags
0x18009639a  call    cs:__imp_LoadLibraryExW
0x1800963a0  mov     [rbx+30h], rax
0x1800963a4  test    rax, rax
0x1800963a7  jz      loc_180096450
0x1800963ad  lea     rdx, aCreduipromptfo; "CredUIPromptForCredentialsW"
0x1800963b4  mov     rcx, rax; hModule
0x1800963b7  call    cs:__imp_GetProcAddress
0x1800963bd  test    rax, rax
0x1800963c0  jz      loc_180096450
0x1800963c6  mov     [rsp+9E0h+var_998], 40082h
0x1800963ce  lea     rcx, [rbp+8E0h+var_950]
0x1800963d2  mov     qword ptr [rsp+9E0h+var_9A0], rcx
0x1800963d7  lea     rdx, [rbp+8E0h+var_940]
0x1800963db  mov     dword ptr [rsp+9E0h+var_9A8], 101h
0x1800963e3  lea     rcx, [rbp+8E0h+var_7D0]
0x1800963ea  mov     qword ptr [rsp+9E0h+var_9B0], rcx
0x1800963ef  xor     r9d, r9d
0x1800963f2  lea     rcx, [rbp+8E0h+var_5C0]
0x1800963f9  mov     dword ptr [rsp+9E0h+var_9B8], 202h
0x180096401  mov     qword ptr [rsp+9E0h+var_9C0], rcx
0x180096406  xor     r8d, r8d
0x180096409  lea     rcx, [rsp+9E0h+var_978]
0x18009640e  call    _guard_dispatch_icall
0x180096413  mov     ecx, eax
0x180096415  cmp     eax, 4C7h
0x18009641a  jnz     short loc_180096478
0x18009641c  mov     [rbx+20h], esi
0x18009641f  jmp     loc_18009655D
0x180096424  lea     rcx, qword_1800EEF18; this
0x18009642b  call    ?GetLocResourceInstance@CModuleResHelper@@QEAAPEAUHINSTANCE__@@XZ; CModuleResHelper::GetLocResourceInstance(void)
0x180096430  mov     rcx, rax; hInstance
0x180096433  lea     r8, [rbp+8E0h+var_8E0]; lpBuffer
0x180096437  mov     r9d, 81h; cchBufferMax
0x18009643d  mov     edx, 0FC14h; uID
0x180096442  call    cs:__imp_LoadStringW
0x180096448  test    eax, eax
0x18009644a  jnz     loc_1800962D9
0x180096450  call    cs:__imp_GetLastError
0x180096456  movzx   ecx, ax
0x180096459  or      ecx, 80070000h
0x18009645f  test    eax, eax
0x180096461  cmovle  ecx, eax
0x180096464  mov     eax, 8000FFFFh
0x180096469  test    ecx, ecx
0x18009646b  cmovns  ecx, eax
0x18009646e  mov     [rbx+20h], ecx
0x180096471  mov     eax, ecx
0x180096473  jmp     loc_18009657D
0x180096478  test    ecx, ecx
0x18009647a  jz      short loc_180096493
0x18009647c  movzx   eax, cx
0x18009647f  or      eax, 80070000h
0x180096484  test    ecx, ecx
0x180096486  cmovle  eax, ecx
0x180096489  mov     [rbx+20h], eax
0x18009648c  mov     esi, eax
0x18009648e  jmp     loc_18009655D
0x180096493  mov     rcx, [r14]; bstr
0x180096496  test    rcx, rcx
0x180096499  jz      short loc_1800964B6
0x18009649b  call    cs:__imp_SysStringByteLen
0x1800964a1  mov     rdi, [r14]
0x1800964a4  mov     ecx, eax
0x1800964a6  xor     eax, eax
0x1800964a8  rep stosb
0x1800964aa  mov     rcx, [r14]; bstrString
0x1800964ad  call    cs:__imp_SysFreeString
0x1800964b3  mov     [r14], r15
0x1800964b6  mov     rdx, r14; wchar_t **
0x1800964b9  lea     rcx, [rbp+8E0h+var_5C0]; wchar_t *
0x1800964c0  call    ?SusSysAllocString@@YAJPEB_WPEAPEA_W@Z; SusSysAllocString(wchar_t const *,wchar_t * *)
0x1800964c5  test    eax, eax
0x1800964c7  js      short loc_1800964E0
0x1800964c9  mov     rcx, [rbx+10h]
0x1800964cd  test    rcx, rcx
0x1800964d0  jz      short loc_1800964E0
0x1800964d2  mov     rax, [rcx]
0x1800964d5  mov     rdx, [r14]
0x1800964d8  mov     rax, [rax]
0x1800964db  call    _guard_dispatch_icall
0x1800964e0  mov     [rbx+20h], eax
0x1800964e3  mov     esi, eax
0x1800964e5  test    eax, eax
0x1800964e7  js      short loc_18009655D
0x1800964e9  mov     r14d, r15d
0x1800964ec  cmp     [rbx+10h], r15
0x1800964f0  jz      short loc_18009654A
0x1800964f2  lea     rdx, [rsp+9E0h+bstr]; wchar_t **
0x1800964f7  mov     [rsp+9E0h+bstr], r15
0x1800964fc  lea     rcx, [rbp+8E0h+var_7D0]; wchar_t *
0x180096503  call    ?SusSysAllocString@@YAJPEB_WPEAPEA_W@Z; SusSysAllocString(wchar_t const *,wchar_t * *)
0x180096508  mov     r14d, eax
0x18009650b  test    eax, eax
0x18009650d  js      short loc_18009654A
0x18009650f  mov     rcx, [rbx+10h]
0x180096513  mov     rsi, [rsp+9E0h+bstr]
0x180096518  mov     rdx, rsi
0x18009651b  mov     rax, [rcx]
0x18009651e  mov     rax, [rax+8]
0x180096522  call    _guard_dispatch_icall
0x180096527  mov     r14d, eax
0x18009652a  test    rsi, rsi
0x18009652d  jz      short loc_18009654A
0x18009652f  mov     rcx, rsi; bstr
0x180096532  call    cs:__imp_SysStringByteLen
0x180096538  mov     ecx, eax
0x18009653a  mov     rdi, rsi
0x18009653d  xor     eax, eax
0x18009653f  rep stosb
0x180096541  mov     rcx, rsi; bstrString
0x180096544  call    cs:__imp_SysFreeString
0x18009654a  mov     [rbx+20h], r14d
0x18009654e  mov     esi, r14d
0x180096551  test    r14d, r14d
0x180096554  js      short loc_18009655D
0x180096556  mov     [rbx+20h], r15d
0x18009655a  mov     esi, r15d
0x18009655d  xor     eax, eax
0x18009655f  lea     rdi, [rbp+8E0h+var_5C0]
0x180096566  mov     ecx, 404h
0x18009656b  rep stosb
0x18009656d  lea     rdi, [rbp+8E0h+var_7D0]
0x180096574  mov     ecx, 202h
0x180096579  rep stosb
0x18009657b  mov     eax, esi
0x18009657d  mov     rcx, [rbp+8E0h+var_20]
0x180096584  xor     rcx, rsp; StackCookie
0x180096587  call    __security_check_cookie
0x18009658c  lea     r11, [rsp+9E0h+var_10]
0x180096594  mov     rbx, [r11+28h]
0x180096598  mov     rsi, [r11+30h]
0x18009659c  mov     rdi, [r11+38h]
0x1800965a0  mov     rsp, r11
0x1800965a3  pop     r15
0x1800965a5  pop     r14
0x1800965a7  pop     rbp
0x1800965a8  retn
```
