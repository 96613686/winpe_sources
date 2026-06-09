# DelayLoadHttpApi::LoadHttpApi(void)

- ea: `0x180025ddc`
- end: `0x1800261de`
- name: `?LoadHttpApi@DelayLoadHttpApi@@QEAAJXZ`
- size: `1026`
- prototype: `__int64 __fastcall(DelayLoadHttpApi *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180020bac`

## callees

- `0x180021be8`
- `0x180025ddc`
- `0x1800271fc`
- `0x180029df0`
- `0x18003455c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025e24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025e24`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025e66`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025eb4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025f02`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025f50`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025f9e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025fec`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002603a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180026088`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800260d6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180026119`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025e66`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025eb4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025f02`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025f50`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025f9e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025fec`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002603a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180026088`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800260d6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180026119`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180025def`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180025def`

## string_xrefs

- `0x180025de8`: `httpapi.dll`
- `0x180025ead`: `HttpCreateHttpHandle`
- `0x180025fe5`: `HttpRemoveUrl`

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
0x180025ddc  push    rbx
0x180025dde  push    rbp
0x180025ddf  push    rsi
0x180025de0  push    rdi
0x180025de1  sub     rsp, 28h
0x180025de5  mov     rdi, rcx
0x180025de8  lea     rcx, aHttpapiDll; "httpapi.dll"
0x180025def  call    cs:__imp_LoadLibraryW
0x180025df6  nop     dword ptr [rax+rax+00h]
0x180025dfb  mov     [rdi+8], rax
0x180025dff  lea     rbp, WPP_d6f7572cc2c83d6e91d936d5e52e6ba7_Traceguids
0x180025e06  test    rax, rax
0x180025e09  jnz     short loc_180025E5C
0x180025e0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180025e12  lea     rsi, WPP_GLOBAL_Control
0x180025e19  cmp     rcx, rsi
0x180025e1c  jz      short loc_180025E52
0x180025e1e  test    byte ptr [rcx+1Ch], 1
0x180025e22  jz      short loc_180025E52
0x180025e24  call    cs:__imp_GetLastError
0x180025e2b  nop     dword ptr [rax+rax+00h]
0x180025e30  mov     rcx, cs:WPP_GLOBAL_Control
0x180025e37  mov     edx, 0Ah
0x180025e3c  mov     r9d, eax
0x180025e3f  mov     r8, rbp
0x180025e42  mov     rcx, [rcx+10h]
0x180025e46  call    WPP_SF_d
0x180025e4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180025e52  mov     ebx, 80004005h
0x180025e57  jmp     loc_180026162
0x180025e5c  lea     rdx, aHttpinitialize; "HttpInitialize"
0x180025e63  mov     rcx, rax; hModule
0x180025e66  call    cs:__imp_GetProcAddress
0x180025e6d  nop     dword ptr [rax+rax+00h]
0x180025e72  mov     [rdi+10h], rax
0x180025e76  test    rax, rax
0x180025e79  jnz     short loc_180025EA9
0x180025e7b  mov     ebx, 8007000Eh
0x180025e80  mov     rcx, cs:WPP_GLOBAL_Control
0x180025e87  lea     rsi, WPP_GLOBAL_Control
0x180025e8e  cmp     rcx, rsi
0x180025e91  jz      loc_18002617E
0x180025e97  test    byte ptr [rcx+1Ch], 1
0x180025e9b  jz      loc_180026162
0x180025ea1  lea     edx, [rax+0Bh]
0x180025ea4  jmp     loc_18002614F
0x180025ea9  mov     rcx, [rdi+8]; hModule
0x180025ead  lea     rdx, aHttpcreatehttp; "HttpCreateHttpHandle"
0x180025eb4  call    cs:__imp_GetProcAddress
0x180025ebb  nop     dword ptr [rax+rax+00h]
0x180025ec0  mov     [rdi+18h], rax
0x180025ec4  test    rax, rax
0x180025ec7  jnz     short loc_180025EF7
0x180025ec9  mov     ebx, 8007000Eh
0x180025ece  mov     rcx, cs:WPP_GLOBAL_Control
0x180025ed5  lea     rsi, WPP_GLOBAL_Control
0x180025edc  cmp     rcx, rsi
0x180025edf  jz      loc_18002617E
0x180025ee5  test    byte ptr [rcx+1Ch], 1
0x180025ee9  jz      loc_180026162
0x180025eef  lea     edx, [rax+0Ch]
0x180025ef2  jmp     loc_18002614F
0x180025ef7  mov     rcx, [rdi+8]; hModule
0x180025efb  lea     rdx, aHttpcancelhttp; "HttpCancelHttpRequest"
0x180025f02  call    cs:__imp_GetProcAddress
0x180025f09  nop     dword ptr [rax+rax+00h]
0x180025f0e  mov     [rdi+20h], rax
0x180025f12  test    rax, rax
0x180025f15  jnz     short loc_180025F45
0x180025f17  mov     ebx, 8007000Eh
0x180025f1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180025f23  lea     rsi, WPP_GLOBAL_Control
0x180025f2a  cmp     rcx, rsi
0x180025f2d  jz      loc_18002617E
0x180025f33  test    byte ptr [rcx+1Ch], 1
0x180025f37  jz      loc_180026162
0x180025f3d  lea     edx, [rax+0Dh]
0x180025f40  jmp     loc_18002614F
0x180025f45  mov     rcx, [rdi+8]; hModule
0x180025f49  lea     rdx, aHttpaddurl; "HttpAddUrl"
0x180025f50  call    cs:__imp_GetProcAddress
0x180025f57  nop     dword ptr [rax+rax+00h]
0x180025f5c  mov     [rdi+28h], rax
0x180025f60  test    rax, rax
0x180025f63  jnz     short loc_180025F93
0x180025f65  mov     ebx, 8007000Eh
0x180025f6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180025f71  lea     rsi, WPP_GLOBAL_Control
0x180025f78  cmp     rcx, rsi
0x180025f7b  jz      loc_18002617E
0x180025f81  test    byte ptr [rcx+1Ch], 1
0x180025f85  jz      loc_180026162
0x180025f8b  lea     edx, [rax+0Eh]
0x180025f8e  jmp     loc_18002614F
0x180025f93  mov     rcx, [rdi+8]; hModule
0x180025f97  lea     rdx, aHttpterminate; "HttpTerminate"
0x180025f9e  call    cs:__imp_GetProcAddress
0x180025fa5  nop     dword ptr [rax+rax+00h]
0x180025faa  mov     [rdi+30h], rax
0x180025fae  test    rax, rax
0x180025fb1  jnz     short loc_180025FE1
0x180025fb3  mov     ebx, 8007000Eh
0x180025fb8  mov     rcx, cs:WPP_GLOBAL_Control
0x180025fbf  lea     rsi, WPP_GLOBAL_Control
0x180025fc6  cmp     rcx, rsi
0x180025fc9  jz      loc_18002617E
0x180025fcf  test    byte ptr [rcx+1Ch], 1
0x180025fd3  jz      loc_180026162
0x180025fd9  lea     edx, [rax+0Fh]
0x180025fdc  jmp     loc_18002614F
0x180025fe1  mov     rcx, [rdi+8]; hModule
0x180025fe5  lea     rdx, aHttpremoveurl; "HttpRemoveUrl"
0x180025fec  call    cs:__imp_GetProcAddress
0x180025ff3  nop     dword ptr [rax+rax+00h]
0x180025ff8  mov     [rdi+38h], rax
0x180025ffc  test    rax, rax
0x180025fff  jnz     short loc_18002602F
0x180026001  mov     ebx, 8007000Eh
0x180026006  mov     rcx, cs:WPP_GLOBAL_Control
0x18002600d  lea     rsi, WPP_GLOBAL_Control
0x180026014  cmp     rcx, rsi
0x180026017  jz      loc_18002617E
0x18002601d  test    byte ptr [rcx+1Ch], 1
0x180026021  jz      loc_180026162
0x180026027  lea     edx, [rax+10h]
0x18002602a  jmp     loc_18002614F
0x18002602f  mov     rcx, [rdi+8]; hModule
0x180026033  lea     rdx, aHttpreceivereq; "HttpReceiveRequestEntityBody"
0x18002603a  call    cs:__imp_GetProcAddress
0x180026041  nop     dword ptr [rax+rax+00h]
0x180026046  mov     [rdi+40h], rax
0x18002604a  test    rax, rax
0x18002604d  jnz     short loc_18002607D
0x18002604f  mov     ebx, 8007000Eh
0x180026054  mov     rcx, cs:WPP_GLOBAL_Control
0x18002605b  lea     rsi, WPP_GLOBAL_Control
0x180026062  cmp     rcx, rsi
0x180026065  jz      loc_18002617E
0x18002606b  test    byte ptr [rcx+1Ch], 1
0x18002606f  jz      loc_180026162
0x180026075  lea     edx, [rax+11h]
0x180026078  jmp     loc_18002614F
0x18002607d  mov     rcx, [rdi+8]; hModule
0x180026081  lea     rdx, aHttpsendhttpre; "HttpSendHttpResponse"
0x180026088  call    cs:__imp_GetProcAddress
0x18002608f  nop     dword ptr [rax+rax+00h]
0x180026094  mov     [rdi+48h], rax
0x180026098  test    rax, rax
0x18002609b  jnz     short loc_1800260CB
0x18002609d  mov     ebx, 8007000Eh
0x1800260a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800260a9  lea     rsi, WPP_GLOBAL_Control
0x1800260b0  cmp     rcx, rsi
0x1800260b3  jz      loc_18002617E
0x1800260b9  test    byte ptr [rcx+1Ch], 1
0x1800260bd  jz      loc_180026162
0x1800260c3  lea     edx, [rax+12h]
0x1800260c6  jmp     loc_18002614F
0x1800260cb  mov     rcx, [rdi+8]; hModule
0x1800260cf  lea     rdx, aHttpsendrespon; "HttpSendResponseEntityBody"
0x1800260d6  call    cs:__imp_GetProcAddress
0x1800260dd  nop     dword ptr [rax+rax+00h]
0x1800260e2  mov     [rdi+50h], rax
0x1800260e6  test    rax, rax
0x1800260e9  jnz     short loc_18002610E
0x1800260eb  mov     ebx, 8007000Eh
0x1800260f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800260f7  lea     rsi, WPP_GLOBAL_Control
0x1800260fe  cmp     rcx, rsi
0x180026101  jz      short loc_18002617E
0x180026103  test    byte ptr [rcx+1Ch], 1
0x180026107  jz      short loc_180026162
0x180026109  lea     edx, [rax+13h]
0x18002610c  jmp     short loc_18002614F
0x18002610e  mov     rcx, [rdi+8]; hModule
0x180026112  lea     rdx, aHttpreceivehtt; "HttpReceiveHttpRequest"
0x180026119  call    cs:__imp_GetProcAddress
0x180026120  nop     dword ptr [rax+rax+00h]
0x180026125  mov     [rdi+58h], rax
0x180026129  test    rax, rax
0x18002612c  jnz     short loc_18002619F
0x18002612e  mov     ebx, 8007000Eh
0x180026133  mov     rcx, cs:WPP_GLOBAL_Control
0x18002613a  lea     rsi, WPP_GLOBAL_Control
0x180026141  cmp     rcx, rsi
0x180026144  jz      short loc_18002617E
0x180026146  test    byte ptr [rcx+1Ch], 1
0x18002614a  jz      short loc_180026162
0x18002614c  lea     edx, [rax+14h]
0x18002614f  mov     rcx, [rcx+10h]
0x180026153  mov     r8, rbp
0x180026156  call    WPP_SF_
0x18002615b  mov     rcx, cs:WPP_GLOBAL_Control
0x180026162  cmp     rcx, rsi
0x180026165  jz      short loc_18002617E
0x180026167  test    byte ptr [rcx+1Ch], 1
0x18002616b  jz      short loc_18002617E
0x18002616d  mov     rcx, [rcx+10h]
0x180026171  mov     edx, 15h
0x180026176  mov     r8, rbp
0x180026179  call    WPP_SF_
0x18002617e  cmp     qword ptr [rdi+8], 0
0x180026183  jz      short loc_180026195
0x180026185  mov     rcx, rdi; this
0x180026188  call    ?UnloadHttpApi@DelayLoadHttpApi@@QEAAJXZ; DelayLoadHttpApi::UnloadHttpApi(void)
0x18002618d  mov     qword ptr [rdi+8], 0
0x180026195  mov     rcx, rdi; this
0x180026198  call    ?SetFailFunctionPtrs@DelayLoadHttpApi@@IEAAXXZ; DelayLoadHttpApi::SetFailFunctionPtrs(void)
0x18002619d  jmp     short loc_1800261D2
0x18002619f  xor     ebx, ebx
0x1800261a1  mov     dword ptr [rdi], 1
0x1800261a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800261ae  lea     rsi, WPP_GLOBAL_Control
0x1800261b5  cmp     rcx, rsi
0x1800261b8  jz      short loc_1800261D2
0x1800261ba  test    dword ptr [rcx+1Ch], 100h
0x1800261c1  jz      short loc_1800261D2
0x1800261c3  mov     rcx, [rcx+10h]
0x1800261c7  lea     edx, [rbx+16h]
0x1800261ca  mov     r8, rbp
0x1800261cd  call    WPP_SF_
0x1800261d2  mov     eax, ebx
0x1800261d4  add     rsp, 28h
0x1800261d8  pop     rdi
0x1800261d9  pop     rsi
0x1800261da  pop     rbp
0x1800261db  pop     rbx
0x1800261dc  retn
```
