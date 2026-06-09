# UndockedModuleLoader::Load

- ea: `0x1800346d8`
- end: `0x180034c8b`
- name: `UndockedModuleLoader::Load`
- size: `1459`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180035fa0`

## callees

- `0x180003950`
- `0x18000956c`
- `0x18000996c`
- `0x180009b98`
- `0x180009e38`
- `0x18000c0b4`
- `0x180031f74`
- `0x1800341ac`
- `0x180034358`
- `0x18003453c`
- `0x1800346d8`
- `0x180034c94`
- `0x180036b74`
- `0x180036c98`
- `0x180036d14`
- `0x18003dffc`
- `0x18003e16c`
- `0x18003e264`
- `0x18003e380`
- `0x180042630`
- `0x1800430f8`
- `0x180049260`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003499f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034c05`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034c1f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034c45`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003499f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034c05`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034c1f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034c45`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800349af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034c13`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034c2d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034c53`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800349af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034c13`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034c2d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034c53`

## string_xrefs

- `0x18003491e`: `UUS: Session=%ws, Module=%ws, Version=%ws, Path=%ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall UndockedModuleLoader::Load(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 *a4,
        int a5,
        int a6,
        _QWORD *a7)
{
  int v9; // edi
  uus::Session *v10; // rax
  uus::Session *v11; // rax
  void (__fastcall ***v12)(_QWORD, __int64); // rcx
  __int64 v13; // rcx
  const wchar_t *v14; // rax
  __int64 v15; // r8
  void **v16; // rdx
  void *FullPath; // rax
  int *v18; // rdx
  unsigned int v19; // r8d
  HANDLE ProcessHeap; // rax
  void *v21; // rsi
  int *v22; // rax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  wil::details::in1diag3 *v26; // rcx
  __int64 v27; // rdx
  void *v28; // r14
  HANDLE v29; // rax
  HANDLE v30; // rax
  void *v31; // rdi
  HANDLE v32; // rax
  int v33; // [rsp+20h] [rbp-138h]
  int v34; // [rsp+20h] [rbp-138h]
  int v35; // [rsp+20h] [rbp-138h]
  LPVOID lpMem; // [rsp+58h] [rbp-100h] BYREF
  LPVOID v37[2]; // [rsp+60h] [rbp-F8h] BYREF
  __int64 v38; // [rsp+70h] [rbp-E8h] BYREF
  __int128 v39; // [rsp+78h] [rbp-E0h]
  __int128 v40; // [rsp+88h] [rbp-D0h]
  __int64 v41; // [rsp+98h] [rbp-C0h]
  uus::Session *v42; // [rsp+A0h] [rbp-B8h]
  LPVOID v43; // [rsp+A8h] [rbp-B0h] BYREF
  void *Src[2]; // [rsp+B0h] [rbp-A8h] BYREF
  __int128 v45; // [rsp+C0h] [rbp-98h]
  __int128 v46; // [rsp+D0h] [rbp-88h]
  int v47[4]; // [rsp+E0h] [rbp-78h] BYREF
  __m128i v48; // [rsp+F0h] [rbp-68h]
  __int128 v49; // [rsp+100h] [rbp-58h] BYREF
  __m128i si128; // [rsp+110h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+0h]

  v37[1] = a7;
  if ( !a7 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\inc\\UndockedModuleLoader.h",
      (const char *)0x80070057LL,
      v33);
    return 2147942487LL;
  }
  *a7 = 0;
  v9 = 0;
  lpMem = 0;
  v41 = -1;
  v37[0] = 0;
  v43 = 0;
  v49 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v49) = 0;
  *(_OWORD *)v47 = 0;
  v48 = si128;
  LOWORD(v47[0]) = 0;
  if ( !*a4 )
  {
    v10 = (uus::Session *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
    v42 = v10;
    v11 = v10 ? uus::Session::Session(v10, L"wu.wuaucltcore") : 0LL;
    v12 = (void (__fastcall ***)(_QWORD, __int64))*a4;
    *a4 = (__int64)v11;
    if ( v12 )
      (**v12)(v12, 1);
  }
  v13 = *(_QWORD *)(*a4 + 8);
  if ( v13 )
    v14 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 32LL))(v13);
  else
    v14 = L"0.0.0.0";
  *(_OWORD *)Src = 0;
  v45 = 0;
  v15 = -1;
  do
    ++v15;
  while ( v14[v15] );
  std::wstring::_Construct<1,wchar_t const *>(Src, v14);
  v16 = Src;
  if ( *((_QWORD *)&v45 + 1) > 7u )
    v16 = (void **)Src[0];
  std::wstring::assign(&v49, v16);
  std::wstring::~wstring(Src);
  FullPath = uus::Session::GetFullPath(*a4, Src);
  std::filesystem::path::operator=(v47, FullPath);
  std::wstring::~wstring(Src);
  WUTrace(0, 0, 32, 4);
  v18 = v47;
  if ( v48.m128i_i64[1] > 7uLL )
    v18 = *(int **)v47;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
    &lpMem,
    v18,
    -1);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(
    v37,
    &lpMem);
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
  }
  v21 = v37[0];
  if ( !v37[0] )
  {
    v9 = -2147024882;
    wil::details::in1diag3::Log_Hr(retaddr, (void *)0x96, v19, (const char *)0x8007000ELL, 0);
  }
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v22 = v47;
  if ( v48.m128i_i64[1] > 7uLL )
    LODWORD(v22) = v47[0];
  v34 = (int)v22;
  v23 = UndockedComponentInfo::Init(&v38, (unsigned int)v9, (((v9 >> 31) & 0xE) + 2) | 1u, L"wu.wuaucltcore");
  if ( v23 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xAA,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\inc\\UndockedModuleLoader.h",
      (const char *)(unsigned int)v23,
      v34);
  Src[0] = &v43;
  Src[1] = 0;
  LOBYTE(v45) = 1;
  v24 = UndockedComponentInfo::ToString((UndockedComponentInfo *)&v38, (wchar_t **)&Src[1]);
  if ( v24 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xAB,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\inc\\UndockedModuleLoader.h",
      (const char *)(unsigned int)v24,
      v34);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(Src);
  v35 = v9;
  WUTrace(0, 0, 32, ((v9 >> 31) & 0xFFFFFFFD) + 4);
  if ( v9 < 0 )
  {
    Src[1] = 0;
    v45 = 0;
    v46 = 0;
    Src[0] = &UndockedComponentLoadFailedEvent::`vftable';
    v25 = UndockedComponentLoadEvent::Init(
            (UndockedComponentLoadEvent *)Src,
            (const struct UndockedComponentInfo *)&v38);
    v26 = retaddr;
    if ( v25 >= 0 )
    {
      v25 = UndockedComponentLoadFailedEvent::FireAsimovEvent((UndockedComponentLoadFailedEvent *)Src, 0, 0);
      v26 = retaddr;
      if ( v25 >= 0 )
      {
LABEL_34:
        UndockedComponentInfo::~UndockedComponentInfo((UndockedComponentInfo *)&Src[1]);
        goto LABEL_35;
      }
      v27 = 183;
    }
    else
    {
      v27 = 181;
    }
    wil::details::in1diag3::_Log_Hr(
      v26,
      (void *)v27,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\inc\\UndockedModuleLoader.h",
      (const char *)(unsigned int)v25,
      v9);
    goto LABEL_34;
  }
LABEL_35:
  UndockedComponentInfo::~UndockedComponentInfo((UndockedComponentInfo *)&v38);
  std::wstring::~wstring(v47);
  std::wstring::~wstring(&v49);
  if ( v9 >= 0 )
  {
    *a7 = v21;
    v31 = v43;
    if ( v43 )
    {
      v32 = GetProcessHeap();
      HeapFree(v32, 0, v31);
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x114,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\inc\\UndockedModuleLoader.h",
      (const char *)(unsigned int)v9,
      v35);
    v28 = v43;
    if ( v43 )
    {
      v29 = GetProcessHeap();
      HeapFree(v29, 0, v28);
    }
    if ( v21 )
    {
      v30 = GetProcessHeap();
      HeapFree(v30, 0, v21);
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800346d8  mov     [rsp+arg_0], rbx
0x1800346dd  mov     [rsp+arg_8], rsi
0x1800346e2  push    rdi
0x1800346e3  push    r12
0x1800346e5  push    r13
0x1800346e7  push    r14
0x1800346e9  push    r15
0x1800346eb  sub     rsp, 130h
0x1800346f2  mov     rax, cs:__security_cookie
0x1800346f9  xor     rax, rsp
0x1800346fc  mov     [rsp+158h+var_38], rax
0x180034704  mov     rsi, r9
0x180034707  mov     r15, [rsp+158h+arg_30]
0x18003470f  mov     [rsp+158h+var_F0], r15
0x180034714  xor     ebx, ebx
0x180034716  test    r15, r15
0x180034719  jnz     short loc_180034742
0x18003471b  mov     rcx, [rsp+158h]; this
0x180034723  mov     ebx, 80070057h
0x180034728  mov     r9d, ebx; char *
0x18003472b  lea     r8, aCW1SSrcClientI_0; "C:\\__w\\1\\s\\src\\Client\\inc\\Undock"...
0x180034732  lea     edx, [r15+29h]; void *
0x180034736  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003473b  mov     eax, ebx
0x18003473d  jmp     loc_180034C5E
0x180034742  mov     [r15], rbx
0x180034745  mov     edi, ebx
0x180034747  mov     [rsp+158h+lpMem], rbx
0x18003474c  or      r12, 0FFFFFFFFFFFFFFFFh
0x180034750  mov     [rsp+158h+var_C0], r12
0x180034758  mov     [rsp+158h+var_F8], rbx
0x18003475d  mov     [rsp+158h+var_B0], rbx
0x180034765  xorps   xmm0, xmm0
0x180034768  movups  [rsp+158h+var_58], xmm0
0x180034770  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180034778  movdqu  [rsp+158h+var_48], xmm1
0x180034781  mov     word ptr [rsp+158h+var_58], bx
0x180034789  movups  xmmword ptr [rsp+158h+var_78], xmm0
0x180034791  movdqu  [rsp+158h+var_68], xmm1
0x18003479a  mov     word ptr [rsp+158h+var_78], bx
0x1800347a2  mov     [rsp+158h+var_108], ebx
0x1800347a6  cmp     [r9], rbx
0x1800347a9  jnz     short loc_1800347FD
0x1800347ab  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800347b2  lea     ecx, [r12+11h]; unsigned __int64
0x1800347b7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800347bc  mov     [rsp+158h+var_B8], rax
0x1800347c4  lea     r14, aWuWuaucltcore; "wu.wuaucltcore"
0x1800347cb  test    rax, rax
0x1800347ce  jz      short loc_1800347DD
0x1800347d0  mov     rdx, r14; wchar_t *
0x1800347d3  mov     rcx, rax; this
0x1800347d6  call    ??0Session@uus@@QEAA@PEB_W@Z; uus::Session::Session(wchar_t const *)
0x1800347db  jmp     short loc_1800347E0
0x1800347dd  mov     rax, rbx
0x1800347e0  mov     rcx, [rsi]
0x1800347e3  mov     [rsi], rax
0x1800347e6  test    rcx, rcx
0x1800347e9  jz      short loc_180034804
0x1800347eb  mov     rax, [rcx]
0x1800347ee  mov     edx, 1
0x1800347f3  mov     rax, [rax]
0x1800347f6  call    _guard_dispatch_icall
0x1800347fb  jmp     short loc_180034804
0x1800347fd  lea     r14, aWuWuaucltcore; "wu.wuaucltcore"
0x180034804  mov     rax, [rsi]
0x180034807  mov     rcx, [rax+8]
0x18003480b  test    rcx, rcx
0x18003480e  jz      short loc_18003481E
0x180034810  mov     rax, [rcx]
0x180034813  mov     rax, [rax+20h]
0x180034817  call    _guard_dispatch_icall
0x18003481c  jmp     short loc_180034825
0x18003481e  lea     rax, a0000; "0.0.0.0"
0x180034825  xorps   xmm0, xmm0
0x180034828  movups  xmmword ptr [rsp+158h+Src], xmm0
0x180034830  xorps   xmm1, xmm1
0x180034833  movdqu  [rsp+158h+var_98], xmm1
0x18003483c  mov     r8, r12
0x18003483f  inc     r8
0x180034842  cmp     [rax+r8*2], bx
0x180034847  jnz     short loc_18003483F
0x180034849  mov     rdx, rax
0x18003484c  lea     rcx, [rsp+158h+Src]
0x180034854  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180034859  nop
0x18003485a  lea     rdx, [rsp+158h+Src]
0x180034862  cmp     qword ptr [rsp+158h+var_98+8], 7
0x18003486b  cmova   rdx, [rsp+158h+Src]; Src
0x180034874  mov     r8, qword ptr [rsp+158h+var_98]
0x18003487c  lea     rcx, [rsp+158h+var_58]; void *
0x180034884  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::assign(wchar_t const * const,unsigned __int64)
0x180034889  nop
0x18003488a  lea     rcx, [rsp+158h+Src]
0x180034892  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180034897  lea     rdx, [rsp+158h+Src]
0x18003489f  mov     rcx, [rsi]
0x1800348a2  call    ?GetFullPath@Session@uus@@QEBA?AVpath@filesystem@std@@PEB_W@Z; uus::Session::GetFullPath(wchar_t const *)
0x1800348a7  mov     rdx, rax
0x1800348aa  lea     rcx, [rsp+158h+var_78]
0x1800348b2  call    ??4path@filesystem@std@@QEAAAEAV012@$$QEAV012@@Z; std::filesystem::path::operator=(std::filesystem::path &&)
0x1800348b7  lea     rcx, [rsp+158h+Src]
0x1800348bf  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800348c4  mov     r13d, 1
0x1800348ca  mov     [rsp+158h+var_108], r13d
0x1800348cf  lea     rcx, [rsp+158h+var_78]
0x1800348d7  cmp     qword ptr [rsp+158h+var_68+8], 7
0x1800348e0  cmova   rcx, qword ptr [rsp+158h+var_78]
0x1800348e9  lea     rax, [rsp+158h+var_58]
0x1800348f1  cmp     qword ptr [rsp+158h+var_48+8], 7
0x1800348fa  cmova   rax, qword ptr [rsp+158h+var_58]
0x180034903  mov     [rsp+158h+var_110], rcx
0x180034908  mov     [rsp+158h+var_118], rax
0x18003490d  lea     rax, ?c_szWuaucltCoreExe@@3QB_WB; "wuaucltcore.exe"
0x180034914  mov     [rsp+158h+var_120], rax
0x180034919  mov     [rsp+158h+var_128], r14
0x18003491e  lea     rax, aUusSessionWsMo; "UUS: Session=%ws, Module=%ws, Version=%"...
0x180034925  mov     [rsp+158h+var_130], rax
0x18003492a  mov     qword ptr [rsp+158h+var_138], rbx
0x18003492f  xor     edx, edx
0x180034931  xor     ecx, ecx
0x180034933  lea     r9d, [r13+3]
0x180034937  lea     r8d, [r13+1Fh]
0x18003493b  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180034940  nop
0x180034941  jmp     short loc_180034962
0x180034943  mov     edi, dword ptr [rsp+158h+lpMem]
0x180034947  xor     ebx, ebx
0x180034949  lea     r14, aWuWuaucltcore; "wu.wuaucltcore"
0x180034950  mov     r13d, [rsp+158h+var_108]
0x180034955  mov     r15, [rsp+158h+var_F0]
0x18003495a  test    edi, edi
0x18003495c  js      short loc_1800349DB
0x18003495e  or      r12, 0FFFFFFFFFFFFFFFFh
0x180034962  lea     rdx, [rsp+158h+var_78]
0x18003496a  cmp     qword ptr [rsp+158h+var_68+8], 7
0x180034973  cmova   rdx, qword ptr [rsp+158h+var_78]
0x18003497c  mov     r8, r12
0x18003497f  lea     rcx, [rsp+158h+lpMem]
0x180034984  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)
0x180034989  lea     rdx, [rsp+158h+lpMem]
0x18003498e  lea     rcx, [rsp+158h+var_F8]
0x180034993  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &&)
0x180034998  cmp     [rsp+158h+lpMem], rbx
0x18003499d  jz      short loc_1800349B5
0x18003499f  call    cs:__imp_GetProcessHeap
0x1800349a5  mov     rcx, rax; hHeap
0x1800349a8  mov     r8, [rsp+158h+lpMem]; lpMem
0x1800349ad  xor     edx, edx; dwFlags
0x1800349af  call    cs:__imp_HeapFree
0x1800349b5  mov     rsi, [rsp+158h+var_F8]
0x1800349ba  test    rsi, rsi
0x1800349bd  jnz     short loc_1800349E0
0x1800349bf  mov     edi, 8007000Eh
0x1800349c4  mov     rcx, [rsp+158h]; this
0x1800349cc  mov     r9d, edi; char *
0x1800349cf  mov     edx, 96h; void *
0x1800349d4  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800349d9  jmp     short loc_1800349E0
0x1800349db  mov     rsi, [rsp+158h+var_F8]
0x1800349e0  mov     r12d, edi
0x1800349e3  sar     r12d, 1Fh
0x1800349e7  mov     r8d, r12d
0x1800349ea  and     r8d, 0Eh
0x1800349ee  add     r8d, 2
0x1800349f2  or      r8d, r13d
0x1800349f5  mov     [rsp+158h+var_E8], 0
0x1800349fe  xorps   xmm0, xmm0
0x180034a01  movdqu  [rsp+158h+var_E0], xmm0
0x180034a07  xorps   xmm1, xmm1
0x180034a0a  movdqu  [rsp+158h+var_D0], xmm1
0x180034a13  lea     rcx, [rsp+158h+var_58]
0x180034a1b  cmp     qword ptr [rsp+158h+var_48+8], 7
0x180034a24  cmova   rcx, qword ptr [rsp+158h+var_58]
0x180034a2d  lea     rax, [rsp+158h+var_78]
0x180034a35  cmp     qword ptr [rsp+158h+var_68+8], 7
0x180034a3e  cmova   rax, qword ptr [rsp+158h+var_78]
0x180034a47  mov     [rsp+158h+var_130], rcx
0x180034a4c  mov     qword ptr [rsp+158h+var_138], rax; int
0x180034a51  mov     r9, r14
0x180034a54  mov     edx, edi
0x180034a56  lea     rcx, [rsp+158h+var_E8]
0x180034a5b  call    ?Init@UndockedComponentInfo@@QEAAJJW4UndockedComponentLoadFlags@@PEB_W11@Z; UndockedComponentInfo::Init(long,UndockedComponentLoadFlags,wchar_t const *,wchar_t const *,wchar_t const *)
0x180034a60  mov     rcx, [rsp+158h]; this
0x180034a68  test    eax, eax
0x180034a6a  jns     short loc_180034A80
0x180034a6c  mov     r9d, eax; char *
0x180034a6f  lea     r8, aCW1SSrcClientI_0; "C:\\__w\\1\\s\\src\\Client\\inc\\Undock"...
0x180034a76  mov     edx, 0AAh; void *
0x180034a7b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180034a80  lea     rax, [rsp+158h+var_B0]
0x180034a88  mov     [rsp+158h+Src], rax
0x180034a90  mov     [rsp+158h+Src+8], rbx
0x180034a98  mov     byte ptr [rsp+158h+var_98], 1
0x180034aa0  lea     rdx, [rsp+158h+Src+8]; wchar_t **
0x180034aa8  lea     rcx, [rsp+158h+var_E8]; this
0x180034aad  call    ?ToString@UndockedComponentInfo@@QEAAJPEAPEA_W@Z; UndockedComponentInfo::ToString(wchar_t * *)
0x180034ab2  mov     rcx, [rsp+158h]; this
0x180034aba  test    eax, eax
0x180034abc  jns     short loc_180034AD2
0x180034abe  mov     r9d, eax; char *
0x180034ac1  lea     r8, aCW1SSrcClientI_0; "C:\\__w\\1\\s\\src\\Client\\inc\\Undock"...
0x180034ac8  mov     edx, 0ABh; void *
0x180034acd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180034ad2  lea     rcx, [rsp+158h+Src]
0x180034ada  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(void)
0x180034adf  and     r12d, 0FFFFFFFDh
0x180034ae3  lea     r9d, [r12+4]
0x180034ae8  mov     rax, [rsp+158h+var_B0]
0x180034af0  mov     [rsp+158h+var_128], rax
0x180034af5  lea     rax, aLoadUndockedMo; "Load undocked module: %ws"
0x180034afc  mov     [rsp+158h+var_130], rax
0x180034b01  mov     [rsp+158h+var_138], edi; int
0x180034b05  xor     edx, edx
0x180034b07  xor     ecx, ecx
0x180034b09  lea     r8d, [rdx+20h]
0x180034b0d  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180034b12  test    edi, edi
0x180034b14  jns     loc_180034BB1
0x180034b1a  mov     [rsp+158h+Src+8], 0
0x180034b26  xorps   xmm0, xmm0
0x180034b29  movdqu  [rsp+158h+var_98], xmm0
0x180034b32  xorps   xmm1, xmm1
0x180034b35  movdqu  [rsp+158h+var_88], xmm1
0x180034b3e  lea     rax, ??_7UndockedComponentLoadFailedEvent@@6B@; const UndockedComponentLoadFailedEvent::`vftable'
0x180034b45  mov     [rsp+158h+Src], rax
0x180034b4d  lea     rdx, [rsp+158h+var_E8]; struct UndockedComponentInfo *
0x180034b52  lea     rcx, [rsp+158h+Src]; this
0x180034b5a  call    ?Init@UndockedComponentLoadEvent@@QEAAJAEBUUndockedComponentInfo@@@Z; UndockedComponentLoadEvent::Init(UndockedComponentInfo const &)
0x180034b5f  mov     rcx, [rsp+158h]
0x180034b67  test    eax, eax
0x180034b69  jns     short loc_180034B72
0x180034b6b  mov     edx, 0B5h
0x180034b70  jmp     short loc_180034B95
0x180034b72  xor     r8d, r8d; char *
0x180034b75  xor     edx, edx; char *
0x180034b77  lea     rcx, [rsp+158h+Src]; this
0x180034b7f  call    ?FireAsimovEvent@UndockedComponentLoadFailedEvent@@UEAAJPEBD0@Z; UndockedComponentLoadFailedEvent::FireAsimovEvent(char const *,char const *)
0x180034b84  mov     rcx, [rsp+158h]; this
0x180034b8c  test    eax, eax
0x180034b8e  jns     short loc_180034BA4
0x180034b90  mov     edx, 0B7h; void *
0x180034b95  mov     r9d, eax; char *
0x180034b98  lea     r8, aCW1SSrcClientI_0; "C:\\__w\\1\\s\\src\\Client\\inc\\Undock"...
0x180034b9f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180034ba4  lea     rcx, [rsp+158h+Src+8]; this
0x180034bac  call    ??1UndockedComponentInfo@@QEAA@XZ; UndockedComponentInfo::~UndockedComponentInfo(void)
0x180034bb1  lea     rcx, [rsp+158h+var_E8]; this
0x180034bb6  call    ??1UndockedComponentInfo@@QEAA@XZ; UndockedComponentInfo::~UndockedComponentInfo(void)
0x180034bbb  nop
0x180034bbc  lea     rcx, [rsp+158h+var_78]
0x180034bc4  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180034bc9  nop
0x180034bca  lea     rcx, [rsp+158h+var_58]
0x180034bd2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180034bd7  test    edi, edi
0x180034bd9  jns     short loc_180034C35
0x180034bdb  mov     rcx, [rsp+158h]; this
0x180034be3  mov     r9d, edi; char *
0x180034be6  lea     r8, aCW1SSrcClientI_0; "C:\\__w\\1\\s\\src\\Client\\inc\\Undock"...
0x180034bed  mov     edx, 114h; void *
0x180034bf2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034bf7  nop
0x180034bf8  mov     r14, [rsp+158h+var_B0]
0x180034c00  test    r14, r14
0x180034c03  jz      short loc_180034C1A
0x180034c05  call    cs:__imp_GetProcessHeap
0x180034c0b  mov     rcx, rax; hHeap
0x180034c0e  mov     r8, r14; lpMem
0x180034c11  xor     edx, edx; dwFlags
0x180034c13  call    cs:__imp_HeapFree
0x180034c19  nop
0x180034c1a  test    rsi, rsi
0x180034c1d  jz      short loc_180034C5C
0x180034c1f  call    cs:__imp_GetProcessHeap
0x180034c25  mov     rcx, rax; hHeap
0x180034c28  mov     r8, rsi; lpMem
0x180034c2b  xor     edx, edx; dwFlags
0x180034c2d  call    cs:__imp_HeapFree
0x180034c33  jmp     short loc_180034C5C
0x180034c35  mov     [r15], rsi
0x180034c38  mov     rdi, [rsp+158h+var_B0]
0x180034c40  test    rdi, rdi
0x180034c43  jz      short loc_180034C5A
0x180034c45  call    cs:__imp_GetProcessHeap
0x180034c4b  mov     rcx, rax; hHeap
0x180034c4e  mov     r8, rdi; lpMem
0x180034c51  xor     edx, edx; dwFlags
0x180034c53  call    cs:__imp_HeapFree
0x180034c59  nop
0x180034c5a  mov     edi, ebx
0x180034c5c  mov     eax, edi
0x180034c5e  mov     rcx, [rsp+158h+var_38]
0x180034c66  xor     rcx, rsp; StackCookie
0x180034c69  call    __security_check_cookie
0x180034c6e  lea     r11, [rsp+158h+var_28]
0x180034c76  mov     rbx, [r11+30h]
0x180034c7a  mov     rsi, [r11+38h]
0x180034c7e  mov     rsp, r11
0x180034c81  pop     r15
  ... truncated ...
```
