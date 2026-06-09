# DelayLoadHttpApi::LoadHttpApi(void)

- ea: `0x180022bc8`
- end: `0x180022f7e`
- name: `?LoadHttpApi@DelayLoadHttpApi@@QEAAJXZ`
- size: `950`
- prototype: `__int64 __fastcall(DelayLoadHttpApi *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800227e8`

## callees

- `0x180020b50`
- `0x180022bc8`
- `0x180038ce4`
- `0x180039a84`
- `0x180051c68`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022c46`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022c8e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022cd6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022d1e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022d66`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022dae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022df6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022e3e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022e83`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022ec0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022c46`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022c8e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022cd6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022d1e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022d66`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022dae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022df6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022e3e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022e83`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022ec0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022c0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022c0a`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180022bdb`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180022bdb`

## string_xrefs

- `0x180022bd4`: `httpapi.dll`
- `0x180022c87`: `HttpCreateHttpHandle`
- `0x180022da7`: `HttpRemoveUrl`

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
0x180022bc8  push    rbx
0x180022bca  push    rbp
0x180022bcb  push    rsi
0x180022bcc  push    rdi
0x180022bcd  sub     rsp, 28h
0x180022bd1  mov     rdi, rcx
0x180022bd4  lea     rcx, aHttpapiDll; "httpapi.dll"
0x180022bdb  call    cs:__imp_LoadLibraryW
0x180022be1  mov     [rdi+8], rax
0x180022be5  lea     rbp, WPP_d6f7572cc2c83d6e91d936d5e52e6ba7_Traceguids
0x180022bec  test    rax, rax
0x180022bef  jnz     short loc_180022C3C
0x180022bf1  mov     rcx, cs:WPP_GLOBAL_Control
0x180022bf8  lea     rsi, WPP_GLOBAL_Control
0x180022bff  cmp     rcx, rsi
0x180022c02  jz      short loc_180022C32
0x180022c04  test    byte ptr [rcx+1Ch], 1
0x180022c08  jz      short loc_180022C32
0x180022c0a  call    cs:__imp_GetLastError
0x180022c10  mov     rcx, cs:WPP_GLOBAL_Control
0x180022c17  mov     edx, 0Ah
0x180022c1c  mov     r9d, eax
0x180022c1f  mov     r8, rbp
0x180022c22  mov     rcx, [rcx+10h]
0x180022c26  call    WPP_SF_d
0x180022c2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180022c32  mov     ebx, 80004005h
0x180022c37  jmp     loc_180022F03
0x180022c3c  lea     rdx, aHttpinitialize; "HttpInitialize"
0x180022c43  mov     rcx, rax; hModule
0x180022c46  call    cs:__imp_GetProcAddress
0x180022c4c  mov     [rdi+10h], rax
0x180022c50  test    rax, rax
0x180022c53  jnz     short loc_180022C83
0x180022c55  mov     ebx, 8007000Eh
0x180022c5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180022c61  lea     rsi, WPP_GLOBAL_Control
0x180022c68  cmp     rcx, rsi
0x180022c6b  jz      loc_180022F1F
0x180022c71  test    byte ptr [rcx+1Ch], 1
0x180022c75  jz      loc_180022F03
0x180022c7b  lea     edx, [rax+0Bh]
0x180022c7e  jmp     loc_180022EF0
0x180022c83  mov     rcx, [rdi+8]; hModule
0x180022c87  lea     rdx, aHttpcreatehttp; "HttpCreateHttpHandle"
0x180022c8e  call    cs:__imp_GetProcAddress
0x180022c94  mov     [rdi+18h], rax
0x180022c98  test    rax, rax
0x180022c9b  jnz     short loc_180022CCB
0x180022c9d  mov     ebx, 8007000Eh
0x180022ca2  mov     rcx, cs:WPP_GLOBAL_Control
0x180022ca9  lea     rsi, WPP_GLOBAL_Control
0x180022cb0  cmp     rcx, rsi
0x180022cb3  jz      loc_180022F1F
0x180022cb9  test    byte ptr [rcx+1Ch], 1
0x180022cbd  jz      loc_180022F03
0x180022cc3  lea     edx, [rax+0Ch]
0x180022cc6  jmp     loc_180022EF0
0x180022ccb  mov     rcx, [rdi+8]; hModule
0x180022ccf  lea     rdx, aHttpcancelhttp; "HttpCancelHttpRequest"
0x180022cd6  call    cs:__imp_GetProcAddress
0x180022cdc  mov     [rdi+20h], rax
0x180022ce0  test    rax, rax
0x180022ce3  jnz     short loc_180022D13
0x180022ce5  mov     ebx, 8007000Eh
0x180022cea  mov     rcx, cs:WPP_GLOBAL_Control
0x180022cf1  lea     rsi, WPP_GLOBAL_Control
0x180022cf8  cmp     rcx, rsi
0x180022cfb  jz      loc_180022F1F
0x180022d01  test    byte ptr [rcx+1Ch], 1
0x180022d05  jz      loc_180022F03
0x180022d0b  lea     edx, [rax+0Dh]
0x180022d0e  jmp     loc_180022EF0
0x180022d13  mov     rcx, [rdi+8]; hModule
0x180022d17  lea     rdx, aHttpaddurl; "HttpAddUrl"
0x180022d1e  call    cs:__imp_GetProcAddress
0x180022d24  mov     [rdi+28h], rax
0x180022d28  test    rax, rax
0x180022d2b  jnz     short loc_180022D5B
0x180022d2d  mov     ebx, 8007000Eh
0x180022d32  mov     rcx, cs:WPP_GLOBAL_Control
0x180022d39  lea     rsi, WPP_GLOBAL_Control
0x180022d40  cmp     rcx, rsi
0x180022d43  jz      loc_180022F1F
0x180022d49  test    byte ptr [rcx+1Ch], 1
0x180022d4d  jz      loc_180022F03
0x180022d53  lea     edx, [rax+0Eh]
0x180022d56  jmp     loc_180022EF0
0x180022d5b  mov     rcx, [rdi+8]; hModule
0x180022d5f  lea     rdx, aHttpterminate; "HttpTerminate"
0x180022d66  call    cs:__imp_GetProcAddress
0x180022d6c  mov     [rdi+30h], rax
0x180022d70  test    rax, rax
0x180022d73  jnz     short loc_180022DA3
0x180022d75  mov     ebx, 8007000Eh
0x180022d7a  mov     rcx, cs:WPP_GLOBAL_Control
0x180022d81  lea     rsi, WPP_GLOBAL_Control
0x180022d88  cmp     rcx, rsi
0x180022d8b  jz      loc_180022F1F
0x180022d91  test    byte ptr [rcx+1Ch], 1
0x180022d95  jz      loc_180022F03
0x180022d9b  lea     edx, [rax+0Fh]
0x180022d9e  jmp     loc_180022EF0
0x180022da3  mov     rcx, [rdi+8]; hModule
0x180022da7  lea     rdx, aHttpremoveurl; "HttpRemoveUrl"
0x180022dae  call    cs:__imp_GetProcAddress
0x180022db4  mov     [rdi+38h], rax
0x180022db8  test    rax, rax
0x180022dbb  jnz     short loc_180022DEB
0x180022dbd  mov     ebx, 8007000Eh
0x180022dc2  mov     rcx, cs:WPP_GLOBAL_Control
0x180022dc9  lea     rsi, WPP_GLOBAL_Control
0x180022dd0  cmp     rcx, rsi
0x180022dd3  jz      loc_180022F1F
0x180022dd9  test    byte ptr [rcx+1Ch], 1
0x180022ddd  jz      loc_180022F03
0x180022de3  lea     edx, [rax+10h]
0x180022de6  jmp     loc_180022EF0
0x180022deb  mov     rcx, [rdi+8]; hModule
0x180022def  lea     rdx, aHttpreceivereq; "HttpReceiveRequestEntityBody"
0x180022df6  call    cs:__imp_GetProcAddress
0x180022dfc  mov     [rdi+40h], rax
0x180022e00  test    rax, rax
0x180022e03  jnz     short loc_180022E33
0x180022e05  mov     ebx, 8007000Eh
0x180022e0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180022e11  lea     rsi, WPP_GLOBAL_Control
0x180022e18  cmp     rcx, rsi
0x180022e1b  jz      loc_180022F1F
0x180022e21  test    byte ptr [rcx+1Ch], 1
0x180022e25  jz      loc_180022F03
0x180022e2b  lea     edx, [rax+11h]
0x180022e2e  jmp     loc_180022EF0
0x180022e33  mov     rcx, [rdi+8]; hModule
0x180022e37  lea     rdx, aHttpsendhttpre; "HttpSendHttpResponse"
0x180022e3e  call    cs:__imp_GetProcAddress
0x180022e44  mov     [rdi+48h], rax
0x180022e48  test    rax, rax
0x180022e4b  jnz     short loc_180022E78
0x180022e4d  mov     ebx, 8007000Eh
0x180022e52  mov     rcx, cs:WPP_GLOBAL_Control
0x180022e59  lea     rsi, WPP_GLOBAL_Control
0x180022e60  cmp     rcx, rsi
0x180022e63  jz      loc_180022F1F
0x180022e69  test    byte ptr [rcx+1Ch], 1
0x180022e6d  jz      loc_180022F03
0x180022e73  lea     edx, [rax+12h]
0x180022e76  jmp     short loc_180022EF0
0x180022e78  mov     rcx, [rdi+8]; hModule
0x180022e7c  lea     rdx, aHttpsendrespon; "HttpSendResponseEntityBody"
0x180022e83  call    cs:__imp_GetProcAddress
0x180022e89  mov     [rdi+50h], rax
0x180022e8d  test    rax, rax
0x180022e90  jnz     short loc_180022EB5
0x180022e92  mov     ebx, 8007000Eh
0x180022e97  mov     rcx, cs:WPP_GLOBAL_Control
0x180022e9e  lea     rsi, WPP_GLOBAL_Control
0x180022ea5  cmp     rcx, rsi
0x180022ea8  jz      short loc_180022F1F
0x180022eaa  test    byte ptr [rcx+1Ch], 1
0x180022eae  jz      short loc_180022F03
0x180022eb0  lea     edx, [rax+13h]
0x180022eb3  jmp     short loc_180022EF0
0x180022eb5  mov     rcx, [rdi+8]; hModule
0x180022eb9  lea     rdx, aHttpreceivehtt; "HttpReceiveHttpRequest"
0x180022ec0  call    cs:__imp_GetProcAddress
0x180022ec6  mov     [rdi+58h], rax
0x180022eca  test    rax, rax
0x180022ecd  jnz     short loc_180022F40
0x180022ecf  mov     ebx, 8007000Eh
0x180022ed4  mov     rcx, cs:WPP_GLOBAL_Control
0x180022edb  lea     rsi, WPP_GLOBAL_Control
0x180022ee2  cmp     rcx, rsi
0x180022ee5  jz      short loc_180022F1F
0x180022ee7  test    byte ptr [rcx+1Ch], 1
0x180022eeb  jz      short loc_180022F03
0x180022eed  lea     edx, [rax+14h]
0x180022ef0  mov     rcx, [rcx+10h]
0x180022ef4  mov     r8, rbp
0x180022ef7  call    WPP_SF_
0x180022efc  mov     rcx, cs:WPP_GLOBAL_Control
0x180022f03  cmp     rcx, rsi
0x180022f06  jz      short loc_180022F1F
0x180022f08  test    byte ptr [rcx+1Ch], 1
0x180022f0c  jz      short loc_180022F1F
0x180022f0e  mov     rcx, [rcx+10h]
0x180022f12  mov     edx, 15h
0x180022f17  mov     r8, rbp
0x180022f1a  call    WPP_SF_
0x180022f1f  cmp     qword ptr [rdi+8], 0
0x180022f24  jz      short loc_180022F36
0x180022f26  mov     rcx, rdi; this
0x180022f29  call    ?UnloadHttpApi@DelayLoadHttpApi@@QEAAJXZ; DelayLoadHttpApi::UnloadHttpApi(void)
0x180022f2e  mov     qword ptr [rdi+8], 0
0x180022f36  mov     rcx, rdi; this
0x180022f39  call    ?SetFailFunctionPtrs@DelayLoadHttpApi@@IEAAXXZ; DelayLoadHttpApi::SetFailFunctionPtrs(void)
0x180022f3e  jmp     short loc_180022F73
0x180022f40  xor     ebx, ebx
0x180022f42  mov     dword ptr [rdi], 1
0x180022f48  mov     rcx, cs:WPP_GLOBAL_Control
0x180022f4f  lea     rsi, WPP_GLOBAL_Control
0x180022f56  cmp     rcx, rsi
0x180022f59  jz      short loc_180022F73
0x180022f5b  test    dword ptr [rcx+1Ch], 100h
0x180022f62  jz      short loc_180022F73
0x180022f64  mov     rcx, [rcx+10h]
0x180022f68  lea     edx, [rbx+16h]
0x180022f6b  mov     r8, rbp
0x180022f6e  call    WPP_SF_
0x180022f73  mov     eax, ebx
0x180022f75  add     rsp, 28h
0x180022f79  pop     rdi
0x180022f7a  pop     rsi
0x180022f7b  pop     rbp
0x180022f7c  pop     rbx
0x180022f7d  retn
```
