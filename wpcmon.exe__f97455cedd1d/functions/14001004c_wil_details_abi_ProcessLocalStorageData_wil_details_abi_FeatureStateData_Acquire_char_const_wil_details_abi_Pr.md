# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x14001004c`
- end: `0x140010442`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1014`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x140010844`

## callees

- `0x140005530`
- `0x140006314`
- `0x14000bd5c`
- `0x14001004c`
- `0x140010554`
- `0x140010a98`
- `0x140011fec`
- `0x14001458c`
- `0x140016854`
- `0x140018680`
- `0x140018b30`
- `0x14001b500`
- `0x14001b510`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x1400100c3`
- `KERNEL32!CreateMutexExW` at `0x1400100c3`
- `KERNEL32!GetCurrentProcessId` at `0x140010085`
- `KERNEL32!GetCurrentProcessId` at `0x140010085`
- `KERNEL32!GetProcessHeap` at `0x14001027f`
- `KERNEL32!GetProcessHeap` at `0x14001027f`
- `KERNEL32!CloseHandle` at `0x14001018b`
- `KERNEL32!CloseHandle` at `0x140010259`
- `KERNEL32!CloseHandle` at `0x140010271`
- `KERNEL32!CloseHandle` at `0x1400102c7`
- `KERNEL32!CloseHandle` at `0x140010368`
- `KERNEL32!CloseHandle` at `0x14001018b`
- `KERNEL32!CloseHandle` at `0x140010259`
- `KERNEL32!CloseHandle` at `0x140010271`
- `KERNEL32!CloseHandle` at `0x1400102c7`
- `KERNEL32!CloseHandle` at `0x140010368`
- `KERNEL32!WaitForSingleObjectEx` at `0x1400100e4`
- `KERNEL32!WaitForSingleObjectEx` at `0x1400100e4`
- `KERNEL32!ReleaseMutex` at `0x14001017a`
- `KERNEL32!ReleaseMutex` at `0x1400102b6`
- `KERNEL32!ReleaseMutex` at `0x140010352`
- `KERNEL32!ReleaseMutex` at `0x14001017a`
- `KERNEL32!ReleaseMutex` at `0x1400102b6`
- `KERNEL32!ReleaseMutex` at `0x140010352`
- `KERNEL32!InitializeCriticalSectionEx` at `0x14001031f`
- `KERNEL32!InitializeCriticalSectionEx` at `0x14001031f`
- `KERNEL32!HeapFree` at `0x14001028d`
- `KERNEL32!HeapFree` at `0x14001028d`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rbx
  DWORD v8; // eax
  bool v9; // dl
  unsigned int v10; // r8d
  char *v11; // r9
  void *v12; // rdi
  int ValueInternal; // eax
  unsigned __int64 v14; // r8
  unsigned int v15; // esi
  unsigned int v16; // r8d
  const char *v17; // r9
  unsigned int v18; // r8d
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  __int64 v23; // r8
  _DWORD *v24; // r14
  int v25; // eax
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  __int128 v35; // xmm0
  unsigned int v36; // r8d
  const char *v37; // r9
  unsigned int v38; // r8d
  const char *v39; // r9
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  HANDLE hObject[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  v6 = Mutex;
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v5);
  v8 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v8 == 258 )
  {
    v12 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xE01, v10, v11);
    v12 = v6;
  }
  hObject[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    v9,
                    (unsigned __int64 *)hObject,
                    (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v40);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v41);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v16, v17);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v18, v19);
    return v15;
  }
  v20 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v20;
    ++*v20;
    goto LABEL_28;
  }
  *a2 = 0;
  v21 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v24 = (_DWORD *)v21;
  if ( !v21 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
LABEL_23:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v15, v42);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v31, v32);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    return v15;
  }
  *(_OWORD *)hObject = 0;
  if ( (v21 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
  v25 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)hObject,
          Name,
          v23,
          v21 >> 2);
  v15 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v25, 304);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
    goto LABEL_23;
  }
  v35 = *(_OWORD *)hObject;
  *v24 = 1;
  *((_QWORD *)v24 + 1) = v6;
  *((_OWORD *)v24 + 1) = v35;
  memset_0(v24 + 10, 0, 0x108u);
  *((_QWORD *)v24 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v24 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v24 + 58), 0, 0);
  *((_QWORD *)v24 + 34) = 0;
  *((_QWORD *)v24 + 35) = 0;
  *((_QWORD *)v24 + 36) = 0;
  *((_QWORD *)v24 + 37) = 0;
  v6 = 0;
  *a2 = v24;
LABEL_28:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
  return 0;
}

```

## disassembly

```asm
0x14001004c  mov     [rsp-8+arg_10], rbx
0x140010051  push    rbp
0x140010052  push    rsi
0x140010053  push    rdi
0x140010054  push    r14
0x140010056  push    r15
0x140010058  lea     rbp, [rsp-160h]
0x140010060  sub     rsp, 260h
0x140010067  mov     rax, cs:__security_cookie
0x14001006e  xor     rax, rsp
0x140010071  mov     [rbp+180h+var_30], rax
0x140010078  mov     r15, rdx
0x14001007b  mov     qword ptr [rdx], 0
0x140010082  mov     rbx, rcx
0x140010085  call    cs:__imp_GetCurrentProcessId
0x14001008b  mov     r14d, 130h
0x140010091  mov     [rsp+280h+var_258], rbx
0x140010096  mov     r9d, eax
0x140010099  mov     [rsp+280h+var_260], r14d; int
0x14001009e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1400100a5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400100aa  lea     edx, [r14-2Ch]; unsigned __int64
0x1400100ae  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400100b3  mov     r9d, 1F0001h; dwDesiredAccess
0x1400100b9  lea     rdx, [rsp+280h+Name]; lpName
0x1400100be  xor     r8d, r8d; dwFlags
0x1400100c1  xor     ecx, ecx; lpMutexAttributes
0x1400100c3  call    cs:__imp_CreateMutexExW
0x1400100c9  mov     rbx, rax
0x1400100cc  test    rax, rax
0x1400100cf  jnz     short loc_1400100DB
0x1400100d1  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400100d6  jmp     loc_140010374
0x1400100db  xor     r8d, r8d; bAlertable
0x1400100de  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400100e1  mov     rcx, rbx; hHandle
0x1400100e4  call    cs:__imp_WaitForSingleObjectEx
0x1400100ea  cmp     eax, 102h
0x1400100ef  jz      short loc_140010101
0x1400100f1  test    eax, 0FFFFFF7Fh
0x1400100f6  jnz     loc_1400103BE
0x1400100fc  mov     rdi, rbx
0x1400100ff  jmp     short loc_140010103
0x140010101  xor     edi, edi
0x140010103  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140010108  mov     [rsp+280h+hObject], 0
0x140010111  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140010116  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x14001011b  mov     esi, eax
0x14001011d  test    eax, eax
0x14001011f  jns     short loc_1400101A0
0x140010121  mov     rcx, [rbp+188h]; this
0x140010128  lea     r8, aWil; "wil"
0x14001012f  mov     r9d, eax; char *
0x140010132  mov     edx, 66h ; 'f'; void *
0x140010137  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001013c  mov     rcx, [rbp+188h]; this
0x140010143  lea     r8, aWil; "wil"
0x14001014a  mov     r9d, esi; char *
0x14001014d  mov     edx, 6Fh ; 'o'; void *
0x140010152  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140010157  mov     rcx, [rbp+188h]; this
0x14001015e  lea     r8, aWil; "wil"
0x140010165  mov     r9d, esi; char *
0x140010168  mov     edx, 12Eh; void *
0x14001016d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140010172  test    rdi, rdi
0x140010175  jz      short loc_140010188
0x140010177  mov     rcx, rdi; hMutex
0x14001017a  call    cs:__imp_ReleaseMutex
0x140010180  test    eax, eax
0x140010182  jz      loc_1400103D0
0x140010188  mov     rcx, rbx; hObject
0x14001018b  call    cs:__imp_CloseHandle
0x140010191  test    eax, eax
0x140010193  jz      loc_1400103E2
0x140010199  mov     eax, esi
0x14001019b  jmp     loc_140010374
0x1400101a0  mov     rax, [rsp+280h+hObject]
0x1400101a5  lea     rcx, ds:0[rax*4]
0x1400101ad  test    rcx, rcx
0x1400101b0  jz      short loc_1400101C0
0x1400101b2  mov     [r15], rcx
0x1400101b5  mov     eax, [rcx]
0x1400101b7  inc     eax
0x1400101b9  mov     [rcx], eax
0x1400101bb  jmp     loc_14001034A
0x1400101c0  mov     rdx, r14; dwBytes
0x1400101c3  mov     qword ptr [r15], 0
0x1400101ca  mov     ecx, 8; dwFlags
0x1400101cf  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400101d4  mov     r14, rax
0x1400101d7  test    rax, rax
0x1400101da  jnz     short loc_140010201
0x1400101dc  mov     rcx, [rbp+188h]; this
0x1400101e3  lea     r8, aWil; "wil"
0x1400101ea  mov     esi, 8007000Eh
0x1400101ef  mov     edx, 14Bh; void *
0x1400101f4  mov     r9d, esi; char *
0x1400101f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400101fc  jmp     loc_140010293
0x140010201  xorps   xmm0, xmm0
0x140010204  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x14001020a  test    r14b, 3
0x14001020e  jnz     loc_1400103F4
0x140010214  mov     r9, r14
0x140010217  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x14001021c  shr     r9, 2; unsigned __int64
0x140010220  lea     rcx, [rsp+280h+hObject]; this
0x140010225  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x14001022a  mov     esi, eax
0x14001022c  test    eax, eax
0x14001022e  jns     loc_1400102DA
0x140010234  mov     rcx, [rbp+188h]; this
0x14001023b  lea     r8, aWil; "wil"
0x140010242  mov     r9d, eax; char *
0x140010245  mov     edx, 14Eh; void *
0x14001024a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001024f  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140010254  test    rcx, rcx
0x140010257  jz      short loc_140010267
0x140010259  call    cs:__imp_CloseHandle
0x14001025f  test    eax, eax
0x140010261  jz      loc_1400103FA
0x140010267  mov     rcx, [rsp+280h+hObject]; hObject
0x14001026c  test    rcx, rcx
0x14001026f  jz      short loc_14001027F
0x140010271  call    cs:__imp_CloseHandle
0x140010277  test    eax, eax
0x140010279  jz      loc_14001040C
0x14001027f  call    cs:__imp_GetProcessHeap
0x140010285  mov     r8, r14; lpMem
0x140010288  xor     edx, edx; dwFlags
0x14001028a  mov     rcx, rax; hHeap
0x14001028d  call    cs:__imp_HeapFree
0x140010293  mov     rcx, [rbp+188h]; this
0x14001029a  lea     r8, aWil; "wil"
0x1400102a1  mov     r9d, esi; char *
0x1400102a4  mov     edx, 137h; void *
0x1400102a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400102ae  test    rdi, rdi
0x1400102b1  jz      short loc_1400102C4
0x1400102b3  mov     rcx, rdi; hMutex
0x1400102b6  call    cs:__imp_ReleaseMutex
0x1400102bc  test    eax, eax
0x1400102be  jz      loc_14001041E
0x1400102c4  mov     rcx, rbx; hObject
0x1400102c7  call    cs:__imp_CloseHandle
0x1400102cd  test    eax, eax
0x1400102cf  jz      loc_1400103AC
0x1400102d5  jmp     loc_140010199
0x1400102da  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1400102df  lea     rcx, [r14+28h]; void *
0x1400102e3  mov     dword ptr [r14], 1
0x1400102ea  xor     edx, edx; Val
0x1400102ec  mov     [r14+8], rbx
0x1400102f0  mov     r8d, 108h; Size
0x1400102f6  movdqu  xmmword ptr [r14+10h], xmm0
0x1400102fc  call    memset_0
0x140010301  xor     eax, eax
0x140010303  lea     rcx, [r14+28h]; this
0x140010307  mov     [r14+20h], rax
0x14001030b  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140010310  lea     rbx, [r14+0E8h]
0x140010317  xor     r8d, r8d; Flags
0x14001031a  mov     rcx, rbx; lpCriticalSection
0x14001031d  xor     edx, edx; dwSpinCount
0x14001031f  call    cs:__imp_InitializeCriticalSectionEx
0x140010325  mov     qword ptr [rbx+28h], 0
0x14001032d  mov     qword ptr [rbx+30h], 0
0x140010335  mov     qword ptr [rbx+38h], 0
0x14001033d  mov     qword ptr [rbx+40h], 0
0x140010345  xor     ebx, ebx
0x140010347  mov     [r15], r14
0x14001034a  test    rdi, rdi
0x14001034d  jz      short loc_140010360
0x14001034f  mov     rcx, rdi; hMutex
0x140010352  call    cs:__imp_ReleaseMutex
0x140010358  test    eax, eax
0x14001035a  jz      loc_140010430
0x140010360  test    rbx, rbx
0x140010363  jz      short loc_140010372
0x140010365  mov     rcx, rbx; hObject
0x140010368  call    cs:__imp_CloseHandle
0x14001036e  test    eax, eax
0x140010370  jz      short loc_14001039A
0x140010372  xor     eax, eax
0x140010374  mov     rcx, [rbp+180h+var_30]
0x14001037b  xor     rcx, rsp; StackCookie
0x14001037e  call    __security_check_cookie
0x140010383  mov     rbx, [rsp+280h+arg_10]
0x14001038b  add     rsp, 260h
0x140010392  pop     r15
0x140010394  pop     r14
0x140010396  pop     rdi
0x140010397  pop     rsi
0x140010398  pop     rbp
0x140010399  retn
0x14001039a  mov     rcx, [rbp+188h]; this
0x1400103a1  mov     edx, 0A0Bh; void *
0x1400103a6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400103ac  mov     rcx, [rbp+188h]; this
0x1400103b3  mov     edx, 0A0Bh; void *
0x1400103b8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400103be  mov     rcx, [rbp+188h]; this
0x1400103c5  mov     edx, 0E01h; void *
0x1400103ca  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1400103d0  mov     rcx, [rbp+188h]; this
0x1400103d7  mov     edx, 0A15h; void *
0x1400103dc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400103e2  mov     rcx, [rbp+188h]; this
0x1400103e9  mov     edx, 0A0Bh; void *
0x1400103ee  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400103f4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1400103fa  mov     rcx, [rbp+188h]; this
0x140010401  mov     edx, 0A0Bh; void *
0x140010406  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14001040c  mov     rcx, [rbp+188h]; this
0x140010413  mov     edx, 0A0Bh; void *
0x140010418  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14001041e  mov     rcx, [rbp+188h]; this
0x140010425  mov     edx, 0A15h; void *
0x14001042a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140010430  mov     rcx, [rbp+188h]; this
0x140010437  mov     edx, 0A15h; void *
0x14001043c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
