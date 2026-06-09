# SetDefaultTempDB(void)

- ea: `0x100439050`
- end: `0x100439258`
- name: `?SetDefaultTempDB@@YAXXZ`
- size: `520`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1004369a0`

## callees

- `0x100401580`
- `0x100402ec0`
- `0x100404a30`
- `0x100439050`
- `0x1004403d0`
- `0x1004534f8`

## import_xrefs

- `sqlmin!GetMasterDataPath` at `0x100439148`
- `sqlmin!GetMasterDataPath` at `0x100439148`
- `sqlmin!?Open@AutoOpenDB@@QEAAXPEAVBaseXact@@KKH@Z` at `0x1004390bc`
- `sqlmin!?Open@AutoOpenDB@@QEAAXPEAVBaseXact@@KKH@Z` at `0x1004390bc`
- `sqlmin!?CloseDB@AutoOpenDB@@AEAAXXZ` at `0x100439229`
- `sqlmin!?CloseDB@AutoOpenDB@@AEAAXXZ` at `0x100439229`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x1004390a0`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x1004390a0`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004390ed`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004390ed`
- `sqldk!SystemThread_TlsOffset` at `0x1004390d4`
- `sqldk!SystemThread_TlsIndex` at `0x1004390cb`
- `sqldk!?CreateExecSql@@YAPEAVIExecSql@@PEAVIMemObj@@PEAVICallerParse@@@Z` at `0x100439103`
- `sqldk!?CreateExecSql@@YAPEAVIExecSql@@PEAVIMemObj@@PEAVICallerParse@@@Z` at `0x100439103`
- `sqldk!?sm_cpuCountAtStartup@SOS_PublicGlobals@@2KA` at `0x100439123`
- `svl!SvlPathGetDirectory` at `0x10043915c`
- `svl!SvlPathGetDirectory` at `0x10043915c`
- `svl!SvlPathReplaceFileName` at `0x10043919e`
- `svl!SvlPathReplaceFileName` at `0x10043919e`

## string_xrefs

- `0x1004391b1`: `ALTER DATABASE tempdb ADD FILE (NAME = N'tempdev%d', FILENAME = N'%s', SIZE = 8MB, FILEGROWTH = 64MB)`
- `0x100439173`: `tempdb%d.ndf`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void SetDefaultTempDB(void)
{
  char v0; // bp
  unsigned __int16 MasterDbId; // ax
  __int64 v2; // rbx
  __int64 v3; // rcx
  struct IExecSql *ExecSql; // rsi
  int v5; // edi
  __int64 MasterDataPath; // rax
  int v7; // ebx
  __int64 v8; // [rsp+30h] [rbp-2458h] BYREF
  int v9; // [rsp+38h] [rbp-2450h]
  __int64 v10; // [rsp+40h] [rbp-2448h]
  struct IExecSql *v11; // [rsp+48h] [rbp-2440h]
  _BYTE v12[528]; // [rsp+50h] [rbp-2438h] BYREF
  wchar_t Buffer[264]; // [rsp+260h] [rbp-2228h] BYREF
  wchar_t v14[4096]; // [rsp+470h] [rbp-2018h] BYREF

  v10 = -2;
  v0 = 1;
  v8 = 0;
  v9 = 0;
  MasterDbId = GetMasterDbId();
  AutoOpenDB::Open((AutoOpenDB *)&v8, 0, MasterDbId, 0, 1);
  v2 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v3 = *(_QWORD *)(v2 + 256);
  if ( !v3 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v3 = *(_QWORD *)(v2 + 256);
  }
  ExecSql = CreateExecSql(*(struct IMemObj **)(v3 + 1000), 0);
  v11 = ExecSql;
  (*(void (__fastcall **)(struct IExecSql *))(*(_QWORD *)ExecSql + 48LL))(ExecSql);
  (*(void (__fastcall **)(struct IExecSql *))(*(_QWORD *)ExecSql + 56LL))(ExecSql);
  v5 = SOS_PublicGlobals::sm_cpuCountAtStartup;
  if ( SOS_PublicGlobals::sm_cpuCountAtStartup > 8 )
    v5 = 8;
  memset_0(v12, 0, 0x20Au);
  MasterDataPath = GetMasterDataPath();
  SvlPathGetDirectory(MasterDataPath, v12, 261);
  v7 = 2;
  if ( v5 < 2 )
    goto LABEL_12;
  while ( 1 )
  {
    StringCchPrintfW(Buffer, 0x104u, L"tempdb%d.ndf", (unsigned int)v7);
    SvlPathReplaceFileName(v12, 261, Buffer);
    StringCchPrintfW(
      v14,
      0x1000u,
      L"ALTER DATABASE tempdb ADD FILE (NAME = N'tempdev%d', FILENAME = N'%s', SIZE = 8MB, FILEGROWTH = 64MB)",
      (unsigned int)v7,
      v12);
    if ( !(*(unsigned int (__fastcall **)(struct IExecSql *, wchar_t *, _QWORD))(*(_QWORD *)ExecSql + 8LL))(
            ExecSql,
            v14,
            0) )
      break;
    if ( ++v7 > v5 )
      goto LABEL_10;
  }
  v0 = 0;
LABEL_10:
  if ( v7 <= 2 )
  {
    if ( !v0 )
      goto LABEL_14;
LABEL_12:
    if ( v5 <= 1 )
      goto LABEL_14;
  }
  scierrlog(0x42DDu, (unsigned int)(v7 - 1));
LABEL_14:
  (*(void (__fastcall **)(struct IExecSql *, __int64))(*(_QWORD *)ExecSql + 224LL))(ExecSql, 1);
  if ( v8 )
    AutoOpenDB::CloseDB((AutoOpenDB *)&v8);
}

```

## disassembly

```asm
0x100439050  push    rdi
0x100439052  mov     eax, 2480h
0x100439057  call    _alloca_probe
0x10043905c  sub     rsp, rax
0x10043905f  mov     [rsp+2488h+var_2448], 0FFFFFFFFFFFFFFFEh
0x100439068  mov     [rsp+2488h+arg_0], rbx
0x100439070  mov     [rsp+2488h+arg_8], rbp
0x100439078  mov     [rsp+2488h+arg_10], rsi
0x100439080  mov     rax, cs:__security_cookie
0x100439087  xor     rax, rsp
0x10043908a  mov     [rsp+2488h+var_18], rax
0x100439092  mov     bpl, 1
0x100439095  xor     eax, eax
0x100439097  mov     [rsp+2488h+var_2458], rax
0x10043909c  mov     [rsp+2488h+var_2450], eax
0x1004390a0  call    cs:__imp_?GetMasterDbId@@YAGXZ; GetMasterDbId(void)
0x1004390a6  movzx   r8d, ax
0x1004390aa  mov     dword ptr [rsp+2488h+var_2468], 1
0x1004390b2  xor     r9d, r9d
0x1004390b5  xor     edx, edx
0x1004390b7  lea     rcx, [rsp+2488h+var_2458]
0x1004390bc  call    cs:__imp_?Open@AutoOpenDB@@QEAAXPEAVBaseXact@@KKH@Z; AutoOpenDB::Open(BaseXact *,ulong,ulong,int)
0x1004390c2  mov     rdx, gs:58h
0x1004390cb  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004390d2  mov     ecx, [rax]
0x1004390d4  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004390db  mov     ebx, [rax]
0x1004390dd  add     rbx, [rdx+rcx*8]
0x1004390e1  mov     rcx, [rbx+100h]
0x1004390e8  test    rcx, rcx
0x1004390eb  jnz     short loc_1004390FA
0x1004390ed  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004390f3  mov     rcx, [rbx+100h]
0x1004390fa  xor     edx, edx
0x1004390fc  mov     rcx, [rcx+3E8h]
0x100439103  call    cs:__imp_?CreateExecSql@@YAPEAVIExecSql@@PEAVIMemObj@@PEAVICallerParse@@@Z; CreateExecSql(IMemObj *,ICallerParse *)
0x100439109  mov     rsi, rax
0x10043910c  mov     [rsp+2488h+var_2440], rax
0x100439111  mov     rdx, [rax]
0x100439114  mov     rcx, rax
0x100439117  call    qword ptr [rdx+30h]
0x10043911a  mov     rdx, [rsi]
0x10043911d  mov     rcx, rsi
0x100439120  call    qword ptr [rdx+38h]
0x100439123  mov     rcx, cs:__imp_?sm_cpuCountAtStartup@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_cpuCountAtStartup
0x10043912a  mov     edi, [rcx]
0x10043912c  mov     eax, 8
0x100439131  cmp     edi, eax
0x100439133  cmova   edi, eax
0x100439136  xor     edx, edx; Val
0x100439138  mov     r8d, 20Ah; Size
0x10043913e  lea     rcx, [rsp+2488h+var_2438]; void *
0x100439143  call    memset_0
0x100439148  call    cs:__imp_GetMasterDataPath
0x10043914e  mov     rcx, rax
0x100439151  mov     r8d, 105h
0x100439157  lea     rdx, [rsp+2488h+var_2438]
0x10043915c  call    cs:__imp_SvlPathGetDirectory
0x100439162  mov     ebx, 2
0x100439167  cmp     edi, ebx
0x100439169  jl      loc_1004391F7
0x10043916f  nop
0x100439170  mov     r9d, ebx
0x100439173  lea     r8, aTempdbDNdf; "tempdb%d.ndf"
0x10043917a  mov     edx, 104h; unsigned __int64
0x10043917f  lea     rcx, [rsp+2488h+Buffer]; Buffer
0x100439187  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x10043918c  lea     r8, [rsp+2488h+Buffer]
0x100439194  mov     edx, 105h
0x100439199  lea     rcx, [rsp+2488h+var_2438]
0x10043919e  call    cs:__imp_SvlPathReplaceFileName
0x1004391a4  lea     rax, [rsp+2488h+var_2438]
0x1004391a9  mov     [rsp+2488h+var_2468], rax
0x1004391ae  mov     r9d, ebx
0x1004391b1  lea     r8, aAlterDatabaseT; "ALTER DATABASE tempdb ADD FILE (NAME = "...
0x1004391b8  mov     edx, 1000h; unsigned __int64
0x1004391bd  lea     rcx, [rsp+2488h+var_2018]; Buffer
0x1004391c5  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1004391ca  mov     rax, [rsi]
0x1004391cd  xor     r8d, r8d
0x1004391d0  lea     rdx, [rsp+2488h+var_2018]
0x1004391d8  mov     rcx, rsi
0x1004391db  call    qword ptr [rax+8]
0x1004391de  test    eax, eax
0x1004391e0  jz      short loc_1004391EA
0x1004391e2  inc     ebx
0x1004391e4  cmp     ebx, edi
0x1004391e6  jle     short loc_100439170
0x1004391e8  jmp     short loc_1004391ED
0x1004391ea  xor     bpl, bpl
0x1004391ed  cmp     ebx, 2
0x1004391f0  jg      short loc_1004391FC
0x1004391f2  test    bpl, bpl
0x1004391f5  jz      short loc_10043920A
0x1004391f7  cmp     edi, 1
0x1004391fa  jle     short loc_10043920A
0x1004391fc  lea     edx, [rbx-1]
0x1004391ff  mov     ecx, 42DDh; unsigned int
0x100439204  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x100439209  nop
0x10043920a  mov     rax, [rsi]
0x10043920d  mov     edx, 1
0x100439212  mov     rcx, rsi
0x100439215  call    qword ptr [rax+0E0h]
0x10043921b  nop
0x10043921c  cmp     [rsp+2488h+var_2458], 0
0x100439222  jz      short loc_10043922F
0x100439224  lea     rcx, [rsp+2488h+var_2458]
0x100439229  call    cs:__imp_?CloseDB@AutoOpenDB@@AEAAXXZ; AutoOpenDB::CloseDB(void)
0x10043922f  mov     rcx, [rsp+2488h+var_18]
0x100439237  xor     rcx, rsp; StackCookie
0x10043923a  call    __security_check_cookie
0x10043923f  lea     r11, [rsp+2488h+var_8]
0x100439247  mov     rbx, [r11+10h]
0x10043924b  mov     rbp, [r11+18h]
0x10043924f  mov     rsi, [r11+20h]
0x100439253  mov     rsp, r11
0x100439256  pop     rdi
0x100439257  retn
```
