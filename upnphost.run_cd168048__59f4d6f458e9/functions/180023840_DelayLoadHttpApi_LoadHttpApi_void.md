# DelayLoadHttpApi::LoadHttpApi(void)

- ea: `0x180023840`
- end: `0x180023c42`
- name: `?LoadHttpApi@DelayLoadHttpApi@@QEAAJXZ`
- size: `1026`
- prototype: `__int64 __fastcall(DelayLoadHttpApi *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002344c`

## callees

- `0x180015d78`
- `0x180023840`
- `0x18003b1cc`
- `0x18003c018`
- `0x18005545c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800238ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023918`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023966`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800239b4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023a02`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023a50`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023a9e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023aec`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023b3a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023b7d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800238ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023918`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023966`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800239b4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023a02`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023a50`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023a9e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023aec`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023b3a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023b7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023888`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023888`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180023853`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180023853`

## string_xrefs

- `0x18002384c`: `httpapi.dll`
- `0x180023911`: `HttpCreateHttpHandle`
- `0x180023a49`: `HttpRemoveUrl`

## pseudocode

```c
__int64 __fastcall DelayLoadHttpApi::LoadHttpApi(DelayLoadHttpApi *this)
{
  HMODULE LibraryW; // rax
  STRSAFE_PCNZWCH v3; // rcx
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
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
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
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
    {
      if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
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
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
    {
      if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v7 = 12;
        goto LABEL_46;
      }
LABEL_47:
      if ( v3 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v3[14] & 1) != 0 )
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
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
    {
      if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
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
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
    {
      if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
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
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
    {
      if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
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
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
    {
      if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
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
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
    {
      if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
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
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
    {
      if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
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
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
    {
      if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
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
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
    {
      if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
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
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_d6f7572cc2c83d6e91d936d5e52e6ba7_Traceguids);
  return v5;
}

```

## disassembly

```asm
0x180023840  push    rbx
0x180023842  push    rbp
0x180023843  push    rsi
0x180023844  push    rdi
0x180023845  sub     rsp, 28h
0x180023849  mov     rdi, rcx
0x18002384c  lea     rcx, aHttpapiDll; "httpapi.dll"
0x180023853  call    cs:__imp_LoadLibraryW
0x18002385a  nop     dword ptr [rax+rax+00h]
0x18002385f  mov     [rdi+8], rax
0x180023863  lea     rbp, WPP_d6f7572cc2c83d6e91d936d5e52e6ba7_Traceguids
0x18002386a  test    rax, rax
0x18002386d  jnz     short loc_1800238C0
0x18002386f  mov     rcx, cs:WPP_GLOBAL_Control
0x180023876  lea     rsi, WPP_GLOBAL_Control
0x18002387d  cmp     rcx, rsi
0x180023880  jz      short loc_1800238B6
0x180023882  test    byte ptr [rcx+1Ch], 1
0x180023886  jz      short loc_1800238B6
0x180023888  call    cs:__imp_GetLastError
0x18002388f  nop     dword ptr [rax+rax+00h]
0x180023894  mov     rcx, cs:WPP_GLOBAL_Control
0x18002389b  mov     edx, 0Ah
0x1800238a0  mov     r9d, eax
0x1800238a3  mov     r8, rbp
0x1800238a6  mov     rcx, [rcx+10h]
0x1800238aa  call    WPP_SF_d
0x1800238af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800238b6  mov     ebx, 80004005h
0x1800238bb  jmp     loc_180023BC6
0x1800238c0  lea     rdx, aHttpinitialize; "HttpInitialize"
0x1800238c7  mov     rcx, rax; hModule
0x1800238ca  call    cs:__imp_GetProcAddress
0x1800238d1  nop     dword ptr [rax+rax+00h]
0x1800238d6  mov     [rdi+10h], rax
0x1800238da  test    rax, rax
0x1800238dd  jnz     short loc_18002390D
0x1800238df  mov     ebx, 8007000Eh
0x1800238e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800238eb  lea     rsi, WPP_GLOBAL_Control
0x1800238f2  cmp     rcx, rsi
0x1800238f5  jz      loc_180023BE2
0x1800238fb  test    byte ptr [rcx+1Ch], 1
0x1800238ff  jz      loc_180023BC6
0x180023905  lea     edx, [rax+0Bh]
0x180023908  jmp     loc_180023BB3
0x18002390d  mov     rcx, [rdi+8]; hModule
0x180023911  lea     rdx, aHttpcreatehttp; "HttpCreateHttpHandle"
0x180023918  call    cs:__imp_GetProcAddress
0x18002391f  nop     dword ptr [rax+rax+00h]
0x180023924  mov     [rdi+18h], rax
0x180023928  test    rax, rax
0x18002392b  jnz     short loc_18002395B
0x18002392d  mov     ebx, 8007000Eh
0x180023932  mov     rcx, cs:WPP_GLOBAL_Control
0x180023939  lea     rsi, WPP_GLOBAL_Control
0x180023940  cmp     rcx, rsi
0x180023943  jz      loc_180023BE2
0x180023949  test    byte ptr [rcx+1Ch], 1
0x18002394d  jz      loc_180023BC6
0x180023953  lea     edx, [rax+0Ch]
0x180023956  jmp     loc_180023BB3
0x18002395b  mov     rcx, [rdi+8]; hModule
0x18002395f  lea     rdx, aHttpcancelhttp; "HttpCancelHttpRequest"
0x180023966  call    cs:__imp_GetProcAddress
0x18002396d  nop     dword ptr [rax+rax+00h]
0x180023972  mov     [rdi+20h], rax
0x180023976  test    rax, rax
0x180023979  jnz     short loc_1800239A9
0x18002397b  mov     ebx, 8007000Eh
0x180023980  mov     rcx, cs:WPP_GLOBAL_Control
0x180023987  lea     rsi, WPP_GLOBAL_Control
0x18002398e  cmp     rcx, rsi
0x180023991  jz      loc_180023BE2
0x180023997  test    byte ptr [rcx+1Ch], 1
0x18002399b  jz      loc_180023BC6
0x1800239a1  lea     edx, [rax+0Dh]
0x1800239a4  jmp     loc_180023BB3
0x1800239a9  mov     rcx, [rdi+8]; hModule
0x1800239ad  lea     rdx, aHttpaddurl; "HttpAddUrl"
0x1800239b4  call    cs:__imp_GetProcAddress
0x1800239bb  nop     dword ptr [rax+rax+00h]
0x1800239c0  mov     [rdi+28h], rax
0x1800239c4  test    rax, rax
0x1800239c7  jnz     short loc_1800239F7
0x1800239c9  mov     ebx, 8007000Eh
0x1800239ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800239d5  lea     rsi, WPP_GLOBAL_Control
0x1800239dc  cmp     rcx, rsi
0x1800239df  jz      loc_180023BE2
0x1800239e5  test    byte ptr [rcx+1Ch], 1
0x1800239e9  jz      loc_180023BC6
0x1800239ef  lea     edx, [rax+0Eh]
0x1800239f2  jmp     loc_180023BB3
0x1800239f7  mov     rcx, [rdi+8]; hModule
0x1800239fb  lea     rdx, aHttpterminate; "HttpTerminate"
0x180023a02  call    cs:__imp_GetProcAddress
0x180023a09  nop     dword ptr [rax+rax+00h]
0x180023a0e  mov     [rdi+30h], rax
0x180023a12  test    rax, rax
0x180023a15  jnz     short loc_180023A45
0x180023a17  mov     ebx, 8007000Eh
0x180023a1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180023a23  lea     rsi, WPP_GLOBAL_Control
0x180023a2a  cmp     rcx, rsi
0x180023a2d  jz      loc_180023BE2
0x180023a33  test    byte ptr [rcx+1Ch], 1
0x180023a37  jz      loc_180023BC6
0x180023a3d  lea     edx, [rax+0Fh]
0x180023a40  jmp     loc_180023BB3
0x180023a45  mov     rcx, [rdi+8]; hModule
0x180023a49  lea     rdx, aHttpremoveurl; "HttpRemoveUrl"
0x180023a50  call    cs:__imp_GetProcAddress
0x180023a57  nop     dword ptr [rax+rax+00h]
0x180023a5c  mov     [rdi+38h], rax
0x180023a60  test    rax, rax
0x180023a63  jnz     short loc_180023A93
0x180023a65  mov     ebx, 8007000Eh
0x180023a6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180023a71  lea     rsi, WPP_GLOBAL_Control
0x180023a78  cmp     rcx, rsi
0x180023a7b  jz      loc_180023BE2
0x180023a81  test    byte ptr [rcx+1Ch], 1
0x180023a85  jz      loc_180023BC6
0x180023a8b  lea     edx, [rax+10h]
0x180023a8e  jmp     loc_180023BB3
0x180023a93  mov     rcx, [rdi+8]; hModule
0x180023a97  lea     rdx, aHttpreceivereq; "HttpReceiveRequestEntityBody"
0x180023a9e  call    cs:__imp_GetProcAddress
0x180023aa5  nop     dword ptr [rax+rax+00h]
0x180023aaa  mov     [rdi+40h], rax
0x180023aae  test    rax, rax
0x180023ab1  jnz     short loc_180023AE1
0x180023ab3  mov     ebx, 8007000Eh
0x180023ab8  mov     rcx, cs:WPP_GLOBAL_Control
0x180023abf  lea     rsi, WPP_GLOBAL_Control
0x180023ac6  cmp     rcx, rsi
0x180023ac9  jz      loc_180023BE2
0x180023acf  test    byte ptr [rcx+1Ch], 1
0x180023ad3  jz      loc_180023BC6
0x180023ad9  lea     edx, [rax+11h]
0x180023adc  jmp     loc_180023BB3
0x180023ae1  mov     rcx, [rdi+8]; hModule
0x180023ae5  lea     rdx, aHttpsendhttpre; "HttpSendHttpResponse"
0x180023aec  call    cs:__imp_GetProcAddress
0x180023af3  nop     dword ptr [rax+rax+00h]
0x180023af8  mov     [rdi+48h], rax
0x180023afc  test    rax, rax
0x180023aff  jnz     short loc_180023B2F
0x180023b01  mov     ebx, 8007000Eh
0x180023b06  mov     rcx, cs:WPP_GLOBAL_Control
0x180023b0d  lea     rsi, WPP_GLOBAL_Control
0x180023b14  cmp     rcx, rsi
0x180023b17  jz      loc_180023BE2
0x180023b1d  test    byte ptr [rcx+1Ch], 1
0x180023b21  jz      loc_180023BC6
0x180023b27  lea     edx, [rax+12h]
0x180023b2a  jmp     loc_180023BB3
0x180023b2f  mov     rcx, [rdi+8]; hModule
0x180023b33  lea     rdx, aHttpsendrespon; "HttpSendResponseEntityBody"
0x180023b3a  call    cs:__imp_GetProcAddress
0x180023b41  nop     dword ptr [rax+rax+00h]
0x180023b46  mov     [rdi+50h], rax
0x180023b4a  test    rax, rax
0x180023b4d  jnz     short loc_180023B72
0x180023b4f  mov     ebx, 8007000Eh
0x180023b54  mov     rcx, cs:WPP_GLOBAL_Control
0x180023b5b  lea     rsi, WPP_GLOBAL_Control
0x180023b62  cmp     rcx, rsi
0x180023b65  jz      short loc_180023BE2
0x180023b67  test    byte ptr [rcx+1Ch], 1
0x180023b6b  jz      short loc_180023BC6
0x180023b6d  lea     edx, [rax+13h]
0x180023b70  jmp     short loc_180023BB3
0x180023b72  mov     rcx, [rdi+8]; hModule
0x180023b76  lea     rdx, aHttpreceivehtt; "HttpReceiveHttpRequest"
0x180023b7d  call    cs:__imp_GetProcAddress
0x180023b84  nop     dword ptr [rax+rax+00h]
0x180023b89  mov     [rdi+58h], rax
0x180023b8d  test    rax, rax
0x180023b90  jnz     short loc_180023C03
0x180023b92  mov     ebx, 8007000Eh
0x180023b97  mov     rcx, cs:WPP_GLOBAL_Control
0x180023b9e  lea     rsi, WPP_GLOBAL_Control
0x180023ba5  cmp     rcx, rsi
0x180023ba8  jz      short loc_180023BE2
0x180023baa  test    byte ptr [rcx+1Ch], 1
0x180023bae  jz      short loc_180023BC6
0x180023bb0  lea     edx, [rax+14h]
0x180023bb3  mov     rcx, [rcx+10h]
0x180023bb7  mov     r8, rbp
0x180023bba  call    WPP_SF_
0x180023bbf  mov     rcx, cs:WPP_GLOBAL_Control
0x180023bc6  cmp     rcx, rsi
0x180023bc9  jz      short loc_180023BE2
0x180023bcb  test    byte ptr [rcx+1Ch], 1
0x180023bcf  jz      short loc_180023BE2
0x180023bd1  mov     rcx, [rcx+10h]
0x180023bd5  mov     edx, 15h
0x180023bda  mov     r8, rbp
0x180023bdd  call    WPP_SF_
0x180023be2  cmp     qword ptr [rdi+8], 0
0x180023be7  jz      short loc_180023BF9
0x180023be9  mov     rcx, rdi; this
0x180023bec  call    ?UnloadHttpApi@DelayLoadHttpApi@@QEAAJXZ; DelayLoadHttpApi::UnloadHttpApi(void)
0x180023bf1  mov     qword ptr [rdi+8], 0
0x180023bf9  mov     rcx, rdi; this
0x180023bfc  call    ?SetFailFunctionPtrs@DelayLoadHttpApi@@IEAAXXZ; DelayLoadHttpApi::SetFailFunctionPtrs(void)
0x180023c01  jmp     short loc_180023C36
0x180023c03  xor     ebx, ebx
0x180023c05  mov     dword ptr [rdi], 1
0x180023c0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180023c12  lea     rsi, WPP_GLOBAL_Control
0x180023c19  cmp     rcx, rsi
0x180023c1c  jz      short loc_180023C36
0x180023c1e  test    dword ptr [rcx+1Ch], 100h
0x180023c25  jz      short loc_180023C36
0x180023c27  mov     rcx, [rcx+10h]
0x180023c2b  lea     edx, [rbx+16h]
0x180023c2e  mov     r8, rbp
0x180023c31  call    WPP_SF_
0x180023c36  mov     eax, ebx
0x180023c38  add     rsp, 28h
0x180023c3c  pop     rdi
0x180023c3d  pop     rsi
0x180023c3e  pop     rbp
0x180023c3f  pop     rbx
0x180023c40  retn
```
