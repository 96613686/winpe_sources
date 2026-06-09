# SNIServerEnumOpenEx

- ea: `0x383adaf60`
- end: `0x383adb35a`
- name: `SNIServerEnumOpenEx`
- size: `1018`
- prototype: `__int64 __fastcall(LPCWCH lpWideCharStr)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x383ad2a70`

## callees

- `0x3838434c0`
- `0x3838435e0`
- `0x38391ac40`
- `0x38391ae80`
- `0x38391af20`
- `0x383ad9b30`
- `0x383ad9ee0`
- `0x383adaf60`

## import_xrefs

- `MSVCR100!_stricmp` at `0x383adb07a`
- `MSVCR100!_stricmp` at `0x383adb093`
- `MSVCR100!_stricmp` at `0x383adb07a`
- `MSVCR100!_stricmp` at `0x383adb093`
- `KERNEL32!WideCharToMultiByte` at `0x383adb023`
- `KERNEL32!WideCharToMultiByte` at `0x383adb023`
- `WS2_32!__imp_WSAStartup` at `0x383adb174`
- `WS2_32!__imp_WSAStartup` at `0x383adb188`
- `WS2_32!__imp_WSAStartup` at `0x383adb174`
- `WS2_32!__imp_WSAStartup` at `0x383adb188`
- `WS2_32!__imp_WSACleanup` at `0x383adb219`
- `WS2_32!__imp_WSACleanup` at `0x383adb219`

## pseudocode

```c
SSRP::ServerEnum *__fastcall SNIServerEnumOpenEx(LPCWCH lpWideCharStr, int a2)
{
  __int64 v4; // rbx
  char *v5; // r8
  char *v6; // rcx
  __int64 v7; // rdx
  CHAR *v8; // rcx
  CHAR v9; // al
  __int64 v10; // rax
  SSRP::ServerEnum *v11; // rbx
  unsigned int v12; // r8d
  unsigned int v13; // r9d
  int lpMultiByteStr; // [rsp+20h] [rbp-2F8h]
  __int64 v16; // [rsp+40h] [rbp-2D8h] BYREF
  struct WSAData WSAData; // [rsp+50h] [rbp-2C8h] BYREF
  CHAR MultiByteStr[256]; // [rsp+1F0h] [rbp-128h] BYREF

  v16 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_383B48E88[0] )
  {
    lpMultiByteStr = 5000;
    bidScopeEnterA(&v16, off_383B48E88[0], lpWideCharStr);
  }
  memset(MultiByteStr, 0, sizeof(MultiByteStr));
  v4 = 256;
  if ( lpWideCharStr && !WideCharToMultiByte(0, 0, lpWideCharStr, -1, MultiByteStr, 256, 0, 0) )
  {
    if ( (bidGblFlags & 0x20002) != 0x20002 || !off_383B48320[0] )
      goto LABEL_39;
    v5 = off_383B48320[0];
    v6 = off_383B45CB8[0];
    v7 = 1627136;
LABEL_38:
    bidTraceA(v6, v7, v5, 0, lpMultiByteStr);
LABEL_39:
    if ( v16 != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
      off_383B15058();
    return 0;
  }
  if ( !_stricmp(MultiByteStr, "(local)") || !_stricmp(MultiByteStr, ".") )
  {
    v8 = MultiByteStr;
    while ( v4 != -2147483390 )
    {
      v9 = v8["localhost" - MultiByteStr];
      if ( !v9 )
        break;
      *v8++ = v9;
      if ( !--v4 )
      {
        --v8;
        break;
      }
    }
    *v8 = 0;
  }
  v10 = (*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)gpmo + 88LL))(gpmo, 4704);
  v11 = (SSRP::ServerEnum *)v10;
  if ( !v10 )
  {
    if ( (bidGblFlags & 0x20002) != 0x20002 || !off_383B48318[0] )
      goto LABEL_39;
    v5 = off_383B48318[0];
    v6 = off_383B45CB0[0];
    v7 = 1641472;
    goto LABEL_38;
  }
  *(_BYTE *)v10 = 0;
  *(_BYTE *)(v10 + 1) = a2 != 0;
  *(_DWORD *)(v10 + 528) = 5000;
  *(_QWORD *)(v10 + 532) = 1000;
  *(_DWORD *)(v10 + 8) = 0;
  *(_QWORD *)(v10 + 4640) = 0;
  *(_QWORD *)(v10 + 4648) = 0;
  *(_DWORD *)(v10 + 4656) = 0;
  *(_BYTE *)(v10 + 4660) = 0;
  *(_QWORD *)(v10 + 4664) = 0;
  *(_QWORD *)(v10 + 4672) = 0;
  *(_QWORD *)(v10 + 4680) = 0;
  *(_QWORD *)(v10 + 4688) = 0;
  *(_QWORD *)(v10 + 4696) = 0;
  if ( WSAStartup(0x202u, &WSAData) && WSAStartup(0x101u, &WSAData) )
  {
    SSRP::ServerEnum::~ServerEnum(v11);
    ((void (__fastcall *)(struct IMalloc *, SSRP::ServerEnum *))g_pMO->lpVtbl[1].Realloc)(g_pMO, v11);
    if ( (bidGblFlags & 0x20002) != 0x20002 || !off_383B48310[0] )
      goto LABEL_39;
    v5 = off_383B48310[0];
    v6 = off_383B45CA8[0];
    v7 = 1652736;
    goto LABEL_38;
  }
  if ( !SSRP::ServerEnum::Initialize(v11, MultiByteStr, v12, v13) )
  {
    SSRP::ServerEnum::~ServerEnum(v11);
    ((void (__fastcall *)(struct IMalloc *, SSRP::ServerEnum *))g_pMO->lpVtbl[1].Realloc)(g_pMO, v11);
    WSACleanup();
    if ( (bidGblFlags & 0x20002) != 0x20002 || !off_383B48308[0] )
      goto LABEL_39;
    v5 = off_383B48308[0];
    v6 = off_383B45CA0[0];
    v7 = 1664000;
    goto LABEL_38;
  }
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B48300[0] )
    bidTraceA(off_383B45C98[0], 1669120, off_383B48300[0], v11, lpMultiByteStr);
  if ( v16 != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
    off_383B15058();
  return v11;
}

```

## disassembly

```asm
0x383adaf60  mov     [rsp+arg_10], rbx
0x383adaf65  push    rbp
0x383adaf66  push    rsi
0x383adaf67  push    rdi
0x383adaf68  sub     rsp, 300h
0x383adaf6f  mov     rax, cs:__security_cookie
0x383adaf76  xor     rax, rsp
0x383adaf79  mov     [rsp+318h+var_28], rax
0x383adaf81  mov     eax, cs:_bidGblFlags
0x383adaf87  mov     esi, edx
0x383adaf89  mov     rdi, rcx
0x383adaf8c  and     eax, 20004h
0x383adaf91  mov     [rsp+318h+var_2D8], 0FFFFFFFFFFFFFFFFh
0x383adaf9a  cmp     eax, 20004h
0x383adaf9f  jnz     short loc_383ADAFD4
0x383adafa1  mov     rax, cs:off_383B48E88; "<SNIServerEnumOpenEx|API|SNI> pwszServe"...
0x383adafa8  test    rax, rax
0x383adafab  jz      short loc_383ADAFD4
0x383adafad  mov     r9d, edx
0x383adafb0  mov     rdx, cs:off_383B48E88; "<SNIServerEnumOpenEx|API|SNI> pwszServe"...
0x383adafb7  mov     r8, rcx
0x383adafba  lea     rcx, [rsp+318h+var_2D8]
0x383adafbf  mov     [rsp+318h+cbMultiByte], 3E8h
0x383adafc7  mov     dword ptr [rsp+318h+lpMultiByteStr], 1388h
0x383adafcf  call    _bidScopeEnterA
0x383adafd4  lea     rcx, [rsp+318h+var_127]; void *
0x383adafdc  xor     edx, edx; Val
0x383adafde  mov     r8d, 0FFh; Size
0x383adafe4  mov     [rsp+318h+MultiByteStr], 0
0x383adafec  call    memset
0x383adaff1  xor     ebp, ebp
0x383adaff3  mov     ebx, 100h
0x383adaff8  test    rdi, rdi
0x383adaffb  jz      short loc_383ADB06B
0x383adaffd  mov     [rsp+318h+lpUsedDefaultChar], rbp; lpUsedDefaultChar
0x383adb002  lea     rax, [rsp+318h+MultiByteStr]
0x383adb00a  mov     [rsp+318h+lpDefaultChar], rbp; lpDefaultChar
0x383adb00f  or      r9d, 0FFFFFFFFh; cchWideChar
0x383adb013  mov     r8, rdi; lpWideCharStr
0x383adb016  xor     edx, edx; dwFlags
0x383adb018  xor     ecx, ecx; CodePage
0x383adb01a  mov     [rsp+318h+cbMultiByte], ebx; cbMultiByte
0x383adb01e  mov     [rsp+318h+lpMultiByteStr], rax; lpMultiByteStr
0x383adb023  call    cs:__imp_WideCharToMultiByte
0x383adb029  test    eax, eax
0x383adb02b  jnz     short loc_383ADB06B
0x383adb02d  mov     eax, cs:_bidGblFlags
0x383adb033  and     eax, 20002h
0x383adb038  cmp     eax, 20002h
0x383adb03d  jnz     loc_383ADB307
0x383adb043  mov     rax, cs:off_383B48320; "<SNIServerEnumOpenEx|RET|SNI> %p\n"
0x383adb04a  test    rax, rax
0x383adb04d  jz      loc_383ADB307
0x383adb053  mov     r8, cs:off_383B48320; "<SNIServerEnumOpenEx|RET|SNI> %p\n"
0x383adb05a  mov     rcx, cs:off_383B45CB8; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383adb061  mov     edx, 18D400h
0x383adb066  jmp     loc_383ADB2FF
0x383adb06b  lea     rdx, aLocal; "(local)"
0x383adb072  lea     rcx, [rsp+318h+MultiByteStr]; String1
0x383adb07a  call    cs:__imp__stricmp
0x383adb080  test    eax, eax
0x383adb082  jz      short loc_383ADB09D
0x383adb084  lea     rdx, asc_38387C770; "."
0x383adb08b  lea     rcx, [rsp+318h+MultiByteStr]; String1
0x383adb093  call    cs:__imp__stricmp
0x383adb099  test    eax, eax
0x383adb09b  jnz     short loc_383ADB0EB
0x383adb09d  lea     rdx, aLocalhost; "localhost"
0x383adb0a4  lea     rax, [rsp+318h+MultiByteStr]
0x383adb0ac  lea     rcx, [rsp+318h+MultiByteStr]
0x383adb0b4  sub     rdx, rax
0x383adb0b7  nop     word ptr [rax+rax+00000000h]
0x383adb0c0  lea     rax, [rbx+7FFFFEFEh]
0x383adb0c7  test    rax, rax
0x383adb0ca  jz      short loc_383ADB0E0
0x383adb0cc  movzx   eax, byte ptr [rdx+rcx]
0x383adb0d0  test    al, al
0x383adb0d2  jz      short loc_383ADB0E0
0x383adb0d4  mov     [rcx], al
0x383adb0d6  inc     rcx
0x383adb0d9  dec     rbx
0x383adb0dc  jnz     short loc_383ADB0C0
0x383adb0de  jmp     short loc_383ADB0E5
0x383adb0e0  test    rbx, rbx
0x383adb0e3  jnz     short loc_383ADB0E8
0x383adb0e5  dec     rcx
0x383adb0e8  mov     [rcx], bpl
0x383adb0eb  mov     rcx, cs:?gpmo@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * gpmo
0x383adb0f2  mov     edx, 1260h
0x383adb0f7  mov     rax, [rcx]
0x383adb0fa  call    qword ptr [rax+58h]
0x383adb0fd  mov     rbx, rax
0x383adb100  test    rax, rax
0x383adb103  jz      loc_383ADB2CE
0x383adb109  mov     [rax], bpl
0x383adb10c  test    esi, esi
0x383adb10e  lea     rdx, [rsp+318h+WSAData]; lpWSAData
0x383adb113  setnz   cl
0x383adb116  mov     [rax+1], cl
0x383adb119  mov     dword ptr [rax+210h], 1388h
0x383adb123  mov     qword ptr [rax+214h], 3E8h
0x383adb12e  mov     [rax+8], ebp
0x383adb131  mov     ecx, 202h; wVersionRequested
0x383adb136  mov     [rax+1220h], rbp
0x383adb13d  mov     [rax+1228h], rbp
0x383adb144  mov     [rax+1230h], ebp
0x383adb14a  mov     [rax+1234h], bpl
0x383adb151  mov     [rax+1238h], rbp
0x383adb158  mov     [rax+1240h], rbp
0x383adb15f  mov     [rax+1248h], rbp
0x383adb166  mov     [rax+1250h], rbp
0x383adb16d  mov     [rax+1258h], rbp
0x383adb174  call    cs:__imp_WSAStartup
0x383adb17a  test    eax, eax
0x383adb17c  jz      short loc_383ADB1ED
0x383adb17e  lea     rdx, [rsp+318h+WSAData]; lpWSAData
0x383adb183  mov     ecx, 101h; wVersionRequested
0x383adb188  call    cs:__imp_WSAStartup
0x383adb18e  test    eax, eax
0x383adb190  jz      short loc_383ADB1ED
0x383adb192  mov     rcx, rbx; this
0x383adb195  call    ??1ServerEnum@SSRP@@QEAA@XZ; SSRP::ServerEnum::~ServerEnum(void)
0x383adb19a  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x383adb1a1  mov     rdx, rbx
0x383adb1a4  mov     rax, [rcx]
0x383adb1a7  call    qword ptr [rax+68h]
0x383adb1aa  mov     r11d, cs:_bidGblFlags
0x383adb1b1  and     r11d, 20002h
0x383adb1b8  cmp     r11d, 20002h
0x383adb1bf  jnz     loc_383ADB307
0x383adb1c5  mov     rax, cs:off_383B48310; "<SNIServerEnumOpenEx|RET|SNI> %p\n"
0x383adb1cc  test    rax, rax
0x383adb1cf  jz      loc_383ADB307
0x383adb1d5  mov     r8, cs:off_383B48310; "<SNIServerEnumOpenEx|RET|SNI> %p\n"
0x383adb1dc  mov     rcx, cs:off_383B45CA8; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383adb1e3  mov     edx, 193800h
0x383adb1e8  jmp     loc_383ADB2FF
0x383adb1ed  lea     rdx, [rsp+318h+MultiByteStr]; char *
0x383adb1f5  mov     rcx, rbx; this
0x383adb1f8  call    ?Initialize@ServerEnum@SSRP@@QEAA_NPEBDKK@Z; SSRP::ServerEnum::Initialize(char const *,ulong,ulong)
0x383adb1fd  test    al, al
0x383adb1ff  jnz     short loc_383ADB262
0x383adb201  mov     rcx, rbx; this
0x383adb204  call    ??1ServerEnum@SSRP@@QEAA@XZ; SSRP::ServerEnum::~ServerEnum(void)
0x383adb209  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x383adb210  mov     rdx, rbx
0x383adb213  mov     rax, [rcx]
0x383adb216  call    qword ptr [rax+68h]
0x383adb219  call    cs:__imp_WSACleanup
0x383adb21f  mov     r11d, cs:_bidGblFlags
0x383adb226  and     r11d, 20002h
0x383adb22d  cmp     r11d, 20002h
0x383adb234  jnz     loc_383ADB307
0x383adb23a  mov     rax, cs:off_383B48308; "<SNIServerEnumOpenEx|RET|SNI> %p\n"
0x383adb241  test    rax, rax
0x383adb244  jz      loc_383ADB307
0x383adb24a  mov     r8, cs:off_383B48308; "<SNIServerEnumOpenEx|RET|SNI> %p\n"
0x383adb251  mov     rcx, cs:off_383B45CA0; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383adb258  mov     edx, 196400h
0x383adb25d  jmp     loc_383ADB2FF
0x383adb262  mov     eax, cs:_bidGblFlags
0x383adb268  and     eax, 20002h
0x383adb26d  cmp     eax, 20002h
0x383adb272  jnz     short loc_383ADB29B
0x383adb274  mov     rax, cs:off_383B48300; "<SNIServerEnumOpenEx|RET|SNI> %p\n"
0x383adb27b  test    rax, rax
0x383adb27e  jz      short loc_383ADB29B
0x383adb280  mov     r8, cs:off_383B48300; "<SNIServerEnumOpenEx|RET|SNI> %p\n"
0x383adb287  mov     rcx, cs:off_383B45C98; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383adb28e  mov     r9, rbx
0x383adb291  mov     edx, 197800h
0x383adb296  call    _bidTraceA
0x383adb29b  cmp     [rsp+318h+var_2D8], 0FFFFFFFFFFFFFFFFh
0x383adb2a1  jz      short loc_383ADB2C9
0x383adb2a3  test    byte ptr cs:_bidGblFlags, 4
0x383adb2aa  jz      short loc_383ADB2C9
0x383adb2ac  mov     rcx, cs:_bidID
0x383adb2b3  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x383adb2b7  jz      short loc_383ADB2C9
0x383adb2b9  lea     r9, [rsp+318h+var_2D8]
0x383adb2be  xor     r8d, r8d
0x383adb2c1  xor     edx, edx
0x383adb2c3  call    cs:off_383B15058
0x383adb2c9  mov     rax, rbx
0x383adb2cc  jmp     short loc_383ADB337
0x383adb2ce  mov     eax, cs:_bidGblFlags
0x383adb2d4  and     eax, 20002h
0x383adb2d9  cmp     eax, 20002h
0x383adb2de  jnz     short loc_383ADB307
0x383adb2e0  mov     rax, cs:off_383B48318; "<SNIServerEnumOpenEx|RET|SNI> %p\n"
0x383adb2e7  test    rax, rax
0x383adb2ea  jz      short loc_383ADB307
0x383adb2ec  mov     r8, cs:off_383B48318; "<SNIServerEnumOpenEx|RET|SNI> %p\n"
0x383adb2f3  mov     rcx, cs:off_383B45CB0; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383adb2fa  mov     edx, 190C00h
0x383adb2ff  xor     r9d, r9d
0x383adb302  call    _bidTraceA
0x383adb307  cmp     [rsp+318h+var_2D8], 0FFFFFFFFFFFFFFFFh
0x383adb30d  jz      short loc_383ADB335
0x383adb30f  test    byte ptr cs:_bidGblFlags, 4
0x383adb316  jz      short loc_383ADB335
0x383adb318  mov     rcx, cs:_bidID
0x383adb31f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x383adb323  jz      short loc_383ADB335
0x383adb325  lea     r9, [rsp+318h+var_2D8]
0x383adb32a  xor     r8d, r8d
0x383adb32d  xor     edx, edx
0x383adb32f  call    cs:off_383B15058
0x383adb335  xor     eax, eax
0x383adb337  mov     rcx, [rsp+318h+var_28]
0x383adb33f  xor     rcx, rsp; StackCookie
0x383adb342  call    __security_check_cookie
0x383adb347  mov     rbx, [rsp+318h+arg_10]
0x383adb34f  add     rsp, 300h
0x383adb356  pop     rdi
0x383adb357  pop     rsi
0x383adb358  pop     rbp
0x383adb359  retn
```
