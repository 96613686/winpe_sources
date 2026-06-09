# DelayLoadHttpApi::LoadHttpApi(void)

- ea: `0x180024328`
- end: `0x1800246de`
- name: `?LoadHttpApi@DelayLoadHttpApi@@QEAAJXZ`
- size: `950`
- prototype: `__int64 __fastcall(DelayLoadHttpApi *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001f3e0`

## callees

- `0x180020690`
- `0x180024328`
- `0x1800255a8`
- `0x180028000`
- `0x180031c54`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002436a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002436a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800243a6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800243ee`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180024436`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002447e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800244c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002450e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180024556`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002459e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800245e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180024620`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800243a6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800243ee`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180024436`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002447e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800244c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002450e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180024556`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002459e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800245e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180024620`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18002433b`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18002433b`

## string_xrefs

- `0x180024334`: `httpapi.dll`
- `0x1800243e7`: `HttpCreateHttpHandle`
- `0x180024507`: `HttpRemoveUrl`

## pseudocode

```c
__int64 __fastcall DelayLoadHttpApi::LoadHttpApi(DelayLoadHttpApi *this)
{
  HMODULE LibraryW; // rax
  LPCSTR v3; // rcx
  DWORD LastError; // eax
  unsigned int v5; // ebx
  FARPROC ProcAddress; // rax
  __int64 v7; // rdx
  FARPROC v8; // rax
  FARPROC v9; // rax
  FARPROC v10; // rax
  FARPROC v11; // rax
  FARPROC v12; // rax
  FARPROC v13; // rax
  FARPROC v14; // rax
  FARPROC v15; // rax
  FARPROC v16; // rax

  LibraryW = LoadLibraryW(L"httpapi.dll");
  *((_QWORD *)this + 1) = LibraryW;
  if ( !LibraryW )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_d6f7572cc2c83d6e91d936d5e52e6ba7_Traceguids, LastError);
      v3 = WPP_GLOBAL_Control;
    }
    v5 = -2147467259;
    goto LABEL_47;
  }
  ProcAddress = GetProcAddress(LibraryW, "HttpInitialize");
  *((_QWORD *)this + 2) = ProcAddress;
  if ( !ProcAddress )
  {
    v5 = -2147024882;
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control )
    {
      if ( (WPP_GLOBAL_Control[28] & 1) != 0 )
      {
        v7 = 11;
LABEL_46:
        WPP_SF_(*((_QWORD *)v3 + 2), v7, WPP_d6f7572cc2c83d6e91d936d5e52e6ba7_Traceguids);
        v3 = WPP_GLOBAL_Control;
        goto LABEL_47;
      }
      goto LABEL_47;
    }
    goto LABEL_50;
  }
  v8 = GetProcAddress(*((HMODULE *)this + 1), "HttpCreateHttpHandle");
  *((_QWORD *)this + 3) = v8;
  if ( !v8 )
  {
    v5 = -2147024882;
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control )
    {
      if ( (WPP_GLOBAL_Control[28] & 1) != 0 )
      {
        v7 = 12;
        goto LABEL_46;
      }
LABEL_47:
      if ( v3 != (LPCSTR)&WPP_GLOBAL_Control && (v3[28] & 1) != 0 )
        WPP_SF_(*((_QWORD *)v3 + 2), 21, WPP_d6f7572cc2c83d6e91d936d5e52e6ba7_Traceguids);
    }
LABEL_50:
    if ( *((_QWORD *)this + 1) )
    {
      DelayLoadHttpApi::UnloadHttpApi(this);
      *((_QWORD *)this + 1) = 0;
    }
    DelayLoadHttpApi::SetFailFunctionPtrs(this);
    return v5;
  }
  v9 = GetProcAddress(*((HMODULE *)this + 1), "HttpCancelHttpRequest");
  *((_QWORD *)this + 4) = v9;
  if ( !v9 )
  {
    v5 = -2147024882;
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control )
    {
      if ( (WPP_GLOBAL_Control[28] & 1) != 0 )
      {
        v7 = 13;
        goto LABEL_46;
      }
      goto LABEL_47;
    }
    goto LABEL_50;
  }
  v10 = GetProcAddress(*((HMODULE *)this + 1), "HttpAddUrl");
  *((_QWORD *)this + 5) = v10;
  if ( !v10 )
  {
    v5 = -2147024882;
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control )
    {
      if ( (WPP_GLOBAL_Control[28] & 1) != 0 )
      {
        v7 = 14;
        goto LABEL_46;
      }
      goto LABEL_47;
    }
    goto LABEL_50;
  }
  v11 = GetProcAddress(*((HMODULE *)this + 1), "HttpTerminate");
  *((_QWORD *)this + 6) = v11;
  if ( !v11 )
  {
    v5 = -2147024882;
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control )
    {
      if ( (WPP_GLOBAL_Control[28] & 1) != 0 )
      {
        v7 = 15;
        goto LABEL_46;
      }
      goto LABEL_47;
    }
    goto LABEL_50;
  }
  v12 = GetProcAddress(*((HMODULE *)this + 1), "HttpRemoveUrl");
  *((_QWORD *)this + 7) = v12;
  if ( !v12 )
  {
    v5 = -2147024882;
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control )
    {
      if ( (WPP_GLOBAL_Control[28] & 1) != 0 )
      {
        v7 = 16;
        goto LABEL_46;
      }
      goto LABEL_47;
    }
    goto LABEL_50;
  }
  v13 = GetProcAddress(*((HMODULE *)this + 1), "HttpReceiveRequestEntityBody");
  *((_QWORD *)this + 8) = v13;
  if ( !v13 )
  {
    v5 = -2147024882;
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control )
    {
      if ( (WPP_GLOBAL_Control[28] & 1) != 0 )
      {
        v7 = 17;
        goto LABEL_46;
      }
      goto LABEL_47;
    }
    goto LABEL_50;
  }
  v14 = GetProcAddress(*((HMODULE *)this + 1), "HttpSendHttpResponse");
  *((_QWORD *)this + 9) = v14;
  if ( !v14 )
  {
    v5 = -2147024882;
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control )
    {
      if ( (WPP_GLOBAL_Control[28] & 1) != 0 )
      {
        v7 = 18;
        goto LABEL_46;
      }
      goto LABEL_47;
    }
    goto LABEL_50;
  }
  v15 = GetProcAddress(*((HMODULE *)this + 1), "HttpSendResponseEntityBody");
  *((_QWORD *)this + 10) = v15;
  if ( !v15 )
  {
    v5 = -2147024882;
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control )
    {
      if ( (WPP_GLOBAL_Control[28] & 1) != 0 )
      {
        v7 = 19;
        goto LABEL_46;
      }
      goto LABEL_47;
    }
    goto LABEL_50;
  }
  v16 = GetProcAddress(*((HMODULE *)this + 1), "HttpReceiveHttpRequest");
  *((_QWORD *)this + 11) = v16;
  if ( !v16 )
  {
    v5 = -2147024882;
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control )
    {
      if ( (WPP_GLOBAL_Control[28] & 1) != 0 )
      {
        v7 = 20;
        goto LABEL_46;
      }
      goto LABEL_47;
    }
    goto LABEL_50;
  }
  v5 = 0;
  *(_DWORD *)this = 1;
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_d6f7572cc2c83d6e91d936d5e52e6ba7_Traceguids);
  return v5;
}

```

## disassembly

```asm
0x180024328  push    rbx
0x18002432a  push    rbp
0x18002432b  push    rsi
0x18002432c  push    rdi
0x18002432d  sub     rsp, 28h
0x180024331  mov     rdi, rcx
0x180024334  lea     rcx, aHttpapiDll; "httpapi.dll"
0x18002433b  call    cs:__imp_LoadLibraryW
0x180024341  mov     [rdi+8], rax
0x180024345  lea     rbp, WPP_d6f7572cc2c83d6e91d936d5e52e6ba7_Traceguids
0x18002434c  test    rax, rax
0x18002434f  jnz     short loc_18002439C
0x180024351  mov     rcx, cs:WPP_GLOBAL_Control
0x180024358  lea     rsi, WPP_GLOBAL_Control
0x18002435f  cmp     rcx, rsi
0x180024362  jz      short loc_180024392
0x180024364  test    byte ptr [rcx+1Ch], 1
0x180024368  jz      short loc_180024392
0x18002436a  call    cs:__imp_GetLastError
0x180024370  mov     rcx, cs:WPP_GLOBAL_Control
0x180024377  mov     edx, 0Ah
0x18002437c  mov     r9d, eax
0x18002437f  mov     r8, rbp
0x180024382  mov     rcx, [rcx+10h]
0x180024386  call    WPP_SF_d
0x18002438b  mov     rcx, cs:WPP_GLOBAL_Control
0x180024392  mov     ebx, 80004005h
0x180024397  jmp     loc_180024663
0x18002439c  lea     rdx, aHttpinitialize; "HttpInitialize"
0x1800243a3  mov     rcx, rax; hModule
0x1800243a6  call    cs:__imp_GetProcAddress
0x1800243ac  mov     [rdi+10h], rax
0x1800243b0  test    rax, rax
0x1800243b3  jnz     short loc_1800243E3
0x1800243b5  mov     ebx, 8007000Eh
0x1800243ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800243c1  lea     rsi, WPP_GLOBAL_Control
0x1800243c8  cmp     rcx, rsi
0x1800243cb  jz      loc_18002467F
0x1800243d1  test    byte ptr [rcx+1Ch], 1
0x1800243d5  jz      loc_180024663
0x1800243db  lea     edx, [rax+0Bh]
0x1800243de  jmp     loc_180024650
0x1800243e3  mov     rcx, [rdi+8]; hModule
0x1800243e7  lea     rdx, aHttpcreatehttp; "HttpCreateHttpHandle"
0x1800243ee  call    cs:__imp_GetProcAddress
0x1800243f4  mov     [rdi+18h], rax
0x1800243f8  test    rax, rax
0x1800243fb  jnz     short loc_18002442B
0x1800243fd  mov     ebx, 8007000Eh
0x180024402  mov     rcx, cs:WPP_GLOBAL_Control
0x180024409  lea     rsi, WPP_GLOBAL_Control
0x180024410  cmp     rcx, rsi
0x180024413  jz      loc_18002467F
0x180024419  test    byte ptr [rcx+1Ch], 1
0x18002441d  jz      loc_180024663
0x180024423  lea     edx, [rax+0Ch]
0x180024426  jmp     loc_180024650
0x18002442b  mov     rcx, [rdi+8]; hModule
0x18002442f  lea     rdx, aHttpcancelhttp; "HttpCancelHttpRequest"
0x180024436  call    cs:__imp_GetProcAddress
0x18002443c  mov     [rdi+20h], rax
0x180024440  test    rax, rax
0x180024443  jnz     short loc_180024473
0x180024445  mov     ebx, 8007000Eh
0x18002444a  mov     rcx, cs:WPP_GLOBAL_Control
0x180024451  lea     rsi, WPP_GLOBAL_Control
0x180024458  cmp     rcx, rsi
0x18002445b  jz      loc_18002467F
0x180024461  test    byte ptr [rcx+1Ch], 1
0x180024465  jz      loc_180024663
0x18002446b  lea     edx, [rax+0Dh]
0x18002446e  jmp     loc_180024650
0x180024473  mov     rcx, [rdi+8]; hModule
0x180024477  lea     rdx, aHttpaddurl; "HttpAddUrl"
0x18002447e  call    cs:__imp_GetProcAddress
0x180024484  mov     [rdi+28h], rax
0x180024488  test    rax, rax
0x18002448b  jnz     short loc_1800244BB
0x18002448d  mov     ebx, 8007000Eh
0x180024492  mov     rcx, cs:WPP_GLOBAL_Control
0x180024499  lea     rsi, WPP_GLOBAL_Control
0x1800244a0  cmp     rcx, rsi
0x1800244a3  jz      loc_18002467F
0x1800244a9  test    byte ptr [rcx+1Ch], 1
0x1800244ad  jz      loc_180024663
0x1800244b3  lea     edx, [rax+0Eh]
0x1800244b6  jmp     loc_180024650
0x1800244bb  mov     rcx, [rdi+8]; hModule
0x1800244bf  lea     rdx, aHttpterminate; "HttpTerminate"
0x1800244c6  call    cs:__imp_GetProcAddress
0x1800244cc  mov     [rdi+30h], rax
0x1800244d0  test    rax, rax
0x1800244d3  jnz     short loc_180024503
0x1800244d5  mov     ebx, 8007000Eh
0x1800244da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800244e1  lea     rsi, WPP_GLOBAL_Control
0x1800244e8  cmp     rcx, rsi
0x1800244eb  jz      loc_18002467F
0x1800244f1  test    byte ptr [rcx+1Ch], 1
0x1800244f5  jz      loc_180024663
0x1800244fb  lea     edx, [rax+0Fh]
0x1800244fe  jmp     loc_180024650
0x180024503  mov     rcx, [rdi+8]; hModule
0x180024507  lea     rdx, aHttpremoveurl; "HttpRemoveUrl"
0x18002450e  call    cs:__imp_GetProcAddress
0x180024514  mov     [rdi+38h], rax
0x180024518  test    rax, rax
0x18002451b  jnz     short loc_18002454B
0x18002451d  mov     ebx, 8007000Eh
0x180024522  mov     rcx, cs:WPP_GLOBAL_Control
0x180024529  lea     rsi, WPP_GLOBAL_Control
0x180024530  cmp     rcx, rsi
0x180024533  jz      loc_18002467F
0x180024539  test    byte ptr [rcx+1Ch], 1
0x18002453d  jz      loc_180024663
0x180024543  lea     edx, [rax+10h]
0x180024546  jmp     loc_180024650
0x18002454b  mov     rcx, [rdi+8]; hModule
0x18002454f  lea     rdx, aHttpreceivereq; "HttpReceiveRequestEntityBody"
0x180024556  call    cs:__imp_GetProcAddress
0x18002455c  mov     [rdi+40h], rax
0x180024560  test    rax, rax
0x180024563  jnz     short loc_180024593
0x180024565  mov     ebx, 8007000Eh
0x18002456a  mov     rcx, cs:WPP_GLOBAL_Control
0x180024571  lea     rsi, WPP_GLOBAL_Control
0x180024578  cmp     rcx, rsi
0x18002457b  jz      loc_18002467F
0x180024581  test    byte ptr [rcx+1Ch], 1
0x180024585  jz      loc_180024663
0x18002458b  lea     edx, [rax+11h]
0x18002458e  jmp     loc_180024650
0x180024593  mov     rcx, [rdi+8]; hModule
0x180024597  lea     rdx, aHttpsendhttpre; "HttpSendHttpResponse"
0x18002459e  call    cs:__imp_GetProcAddress
0x1800245a4  mov     [rdi+48h], rax
0x1800245a8  test    rax, rax
0x1800245ab  jnz     short loc_1800245D8
0x1800245ad  mov     ebx, 8007000Eh
0x1800245b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800245b9  lea     rsi, WPP_GLOBAL_Control
0x1800245c0  cmp     rcx, rsi
0x1800245c3  jz      loc_18002467F
0x1800245c9  test    byte ptr [rcx+1Ch], 1
0x1800245cd  jz      loc_180024663
0x1800245d3  lea     edx, [rax+12h]
0x1800245d6  jmp     short loc_180024650
0x1800245d8  mov     rcx, [rdi+8]; hModule
0x1800245dc  lea     rdx, aHttpsendrespon; "HttpSendResponseEntityBody"
0x1800245e3  call    cs:__imp_GetProcAddress
0x1800245e9  mov     [rdi+50h], rax
0x1800245ed  test    rax, rax
0x1800245f0  jnz     short loc_180024615
0x1800245f2  mov     ebx, 8007000Eh
0x1800245f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800245fe  lea     rsi, WPP_GLOBAL_Control
0x180024605  cmp     rcx, rsi
0x180024608  jz      short loc_18002467F
0x18002460a  test    byte ptr [rcx+1Ch], 1
0x18002460e  jz      short loc_180024663
0x180024610  lea     edx, [rax+13h]
0x180024613  jmp     short loc_180024650
0x180024615  mov     rcx, [rdi+8]; hModule
0x180024619  lea     rdx, aHttpreceivehtt; "HttpReceiveHttpRequest"
0x180024620  call    cs:__imp_GetProcAddress
0x180024626  mov     [rdi+58h], rax
0x18002462a  test    rax, rax
0x18002462d  jnz     short loc_1800246A0
0x18002462f  mov     ebx, 8007000Eh
0x180024634  mov     rcx, cs:WPP_GLOBAL_Control
0x18002463b  lea     rsi, WPP_GLOBAL_Control
0x180024642  cmp     rcx, rsi
0x180024645  jz      short loc_18002467F
0x180024647  test    byte ptr [rcx+1Ch], 1
0x18002464b  jz      short loc_180024663
0x18002464d  lea     edx, [rax+14h]
0x180024650  mov     rcx, [rcx+10h]
0x180024654  mov     r8, rbp
0x180024657  call    WPP_SF_
0x18002465c  mov     rcx, cs:WPP_GLOBAL_Control
0x180024663  cmp     rcx, rsi
0x180024666  jz      short loc_18002467F
0x180024668  test    byte ptr [rcx+1Ch], 1
0x18002466c  jz      short loc_18002467F
0x18002466e  mov     rcx, [rcx+10h]
0x180024672  mov     edx, 15h
0x180024677  mov     r8, rbp
0x18002467a  call    WPP_SF_
0x18002467f  cmp     qword ptr [rdi+8], 0
0x180024684  jz      short loc_180024696
0x180024686  mov     rcx, rdi; this
0x180024689  call    ?UnloadHttpApi@DelayLoadHttpApi@@QEAAJXZ; DelayLoadHttpApi::UnloadHttpApi(void)
0x18002468e  mov     qword ptr [rdi+8], 0
0x180024696  mov     rcx, rdi; this
0x180024699  call    ?SetFailFunctionPtrs@DelayLoadHttpApi@@IEAAXXZ; DelayLoadHttpApi::SetFailFunctionPtrs(void)
0x18002469e  jmp     short loc_1800246D3
0x1800246a0  xor     ebx, ebx
0x1800246a2  mov     dword ptr [rdi], 1
0x1800246a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800246af  lea     rsi, WPP_GLOBAL_Control
0x1800246b6  cmp     rcx, rsi
0x1800246b9  jz      short loc_1800246D3
0x1800246bb  test    dword ptr [rcx+1Ch], 100h
0x1800246c2  jz      short loc_1800246D3
0x1800246c4  mov     rcx, [rcx+10h]
0x1800246c8  lea     edx, [rbx+16h]
0x1800246cb  mov     r8, rbp
0x1800246ce  call    WPP_SF_
0x1800246d3  mov     eax, ebx
0x1800246d5  add     rsp, 28h
0x1800246d9  pop     rdi
0x1800246da  pop     rsi
0x1800246db  pop     rbp
0x1800246dc  pop     rbx
0x1800246dd  retn
```
