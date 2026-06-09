# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140003410`
- end: `0x1400037d8`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x140004a58`

## callees

- `0x140003410`
- `0x1400038f0`
- `0x140003b40`
- `0x1400047f0`
- `0x1400063dc`
- `0x140006844`
- `0x140007098`
- `0x140007308`
- `0x140007d54`
- `0x140007d64`
- `0x14002e3e2`
- `0x14002e420`

## import_xrefs

- `KERNEL32!ReleaseMutex` at `0x14000353f`
- `KERNEL32!ReleaseMutex` at `0x14000367d`
- `KERNEL32!ReleaseMutex` at `0x1400036ed`
- `KERNEL32!ReleaseMutex` at `0x14000353f`
- `KERNEL32!ReleaseMutex` at `0x14000367d`
- `KERNEL32!ReleaseMutex` at `0x1400036ed`
- `KERNEL32!WaitForSingleObjectEx` at `0x1400034a9`
- `KERNEL32!WaitForSingleObjectEx` at `0x1400034a9`
- `KERNEL32!CloseHandle` at `0x140003550`
- `KERNEL32!CloseHandle` at `0x140003620`
- `KERNEL32!CloseHandle` at `0x140003638`
- `KERNEL32!CloseHandle` at `0x14000368e`
- `KERNEL32!CloseHandle` at `0x140003703`
- `KERNEL32!CloseHandle` at `0x140003550`
- `KERNEL32!CloseHandle` at `0x140003620`
- `KERNEL32!CloseHandle` at `0x140003638`
- `KERNEL32!CloseHandle` at `0x14000368e`
- `KERNEL32!CloseHandle` at `0x140003703`
- `KERNEL32!CreateMutexExW` at `0x140003488`
- `KERNEL32!CreateMutexExW` at `0x140003488`
- `KERNEL32!GetCurrentProcessId` at `0x140003449`
- `KERNEL32!GetCurrentProcessId` at `0x140003449`
- `KERNEL32!GetProcessHeap` at `0x140003646`
- `KERNEL32!GetProcessHeap` at `0x140003646`
- `KERNEL32!HeapFree` at `0x140003654`
- `KERNEL32!HeapFree` at `0x140003654`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rbx
  DWORD v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  void *v12; // rdi
  int ValueInternal; // eax
  unsigned __int64 v14; // r8
  unsigned int v15; // esi
  __int64 v16; // r8
  const char *v17; // r9
  __int64 v18; // r8
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  bool v23; // r8
  _QWORD *v24; // rsi
  unsigned int v25; // r14d
  int v26; // eax
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  HANDLE ProcessHeap; // rax
  __int64 v32; // r8
  const char *v33; // r9
  __int64 v34; // r8
  const char *v35; // r9
  __int128 v36; // xmm0
  __int64 v37; // r8
  const char *v38; // r9
  __int64 v39; // r8
  const char *v40; // r9
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  int v43; // [rsp+20h] [rbp-E0h]
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
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v9, v10, v11);
    v12 = v6;
  }
  hObject[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    (bool)v9,
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
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v41);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v42);
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
  v21 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v24 = (_QWORD *)v21;
  if ( v21 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v21 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    v26 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v23,
            v21 >> 2);
    v25 = v26;
    if ( v26 >= 0 )
    {
      v36 = *(_OWORD *)hObject;
      *(_DWORD *)v24 = 1;
      v24[1] = v6;
      *((_OWORD *)v24 + 1) = v36;
      memset_0((char *)v24 + 34, 0, 0x56u);
      *((_WORD *)v24 + 16) = 88;
      *((_DWORD *)v24 + 9) = 1;
      memset_0(v24 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v24;
LABEL_28:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v37, v38);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v39, v40);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v26, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
  }
  else
  {
    v25 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v25, v43);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v32, v33);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v34, v35);
  return v25;
}

```

## disassembly

```asm
0x140003410  mov     [rsp-8+arg_10], rbx
0x140003415  push    rbp
0x140003416  push    rsi
0x140003417  push    rdi
0x140003418  push    r14
0x14000341a  push    r15
0x14000341c  lea     rbp, [rsp-160h]
0x140003424  sub     rsp, 260h
0x14000342b  mov     rax, cs:__security_cookie
0x140003432  xor     rax, rsp
0x140003435  mov     [rbp+180h+var_30], rax
0x14000343c  mov     r15, rdx
0x14000343f  mov     qword ptr [rdx], 0
0x140003446  mov     rbx, rcx
0x140003449  call    cs:__imp_GetCurrentProcessId
0x14000344f  mov     r14d, 78h ; 'x'
0x140003455  mov     [rsp+280h+var_258], rbx
0x14000345a  mov     r9d, eax
0x14000345d  mov     [rsp+280h+var_260], r14d; int
0x140003462  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140003469  mov     edx, 104h; unsigned __int64
0x14000346e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140003473  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140003478  mov     r9d, 1F0001h; dwDesiredAccess
0x14000347e  lea     rdx, [rsp+280h+Name]; lpName
0x140003483  xor     r8d, r8d; dwFlags
0x140003486  xor     ecx, ecx; lpMutexAttributes
0x140003488  call    cs:__imp_CreateMutexExW
0x14000348e  mov     rbx, rax
0x140003491  test    rax, rax
0x140003494  jnz     short loc_1400034A0
0x140003496  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000349b  jmp     loc_14000370F
0x1400034a0  xor     r8d, r8d; bAlertable
0x1400034a3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400034a6  mov     rcx, rbx; hHandle
0x1400034a9  call    cs:__imp_WaitForSingleObjectEx
0x1400034af  cmp     eax, 102h
0x1400034b4  jz      short loc_1400034C6
0x1400034b6  test    eax, 0FFFFFF7Fh
0x1400034bb  jnz     loc_140003747
0x1400034c1  mov     rdi, rbx
0x1400034c4  jmp     short loc_1400034C8
0x1400034c6  xor     edi, edi
0x1400034c8  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1400034cd  mov     [rsp+280h+hObject], 0
0x1400034d6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400034db  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1400034e0  mov     esi, eax
0x1400034e2  test    eax, eax
0x1400034e4  jns     short loc_140003565
0x1400034e6  mov     rcx, [rbp+188h]; this
0x1400034ed  lea     r8, aWil; "wil"
0x1400034f4  mov     r9d, eax; char *
0x1400034f7  mov     edx, 66h ; 'f'; void *
0x1400034fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003501  mov     rcx, [rbp+188h]; this
0x140003508  lea     r8, aWil; "wil"
0x14000350f  mov     r9d, esi; char *
0x140003512  mov     edx, 6Fh ; 'o'; void *
0x140003517  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000351c  mov     rcx, [rbp+188h]; this
0x140003523  lea     r8, aWil; "wil"
0x14000352a  mov     r9d, esi; char *
0x14000352d  mov     edx, 12Eh; void *
0x140003532  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003537  test    rdi, rdi
0x14000353a  jz      short loc_14000354D
0x14000353c  mov     rcx, rdi; hMutex
0x14000353f  call    cs:__imp_ReleaseMutex
0x140003545  test    eax, eax
0x140003547  jz      loc_140003754
0x14000354d  mov     rcx, rbx; hObject
0x140003550  call    cs:__imp_CloseHandle
0x140003556  test    eax, eax
0x140003558  jz      loc_140003766
0x14000355e  mov     eax, esi
0x140003560  jmp     loc_14000370F
0x140003565  mov     rax, [rsp+280h+hObject]
0x14000356a  lea     rcx, ds:0[rax*4]
0x140003572  test    rcx, rcx
0x140003575  jz      short loc_140003585
0x140003577  mov     [r15], rcx
0x14000357a  mov     eax, [rcx]
0x14000357c  inc     eax
0x14000357e  mov     [rcx], eax
0x140003580  jmp     loc_1400036E5
0x140003585  mov     rdx, r14; dwBytes
0x140003588  mov     qword ptr [r15], 0
0x14000358f  mov     ecx, 8; dwFlags
0x140003594  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140003599  mov     rsi, rax
0x14000359c  test    rax, rax
0x14000359f  jnz     short loc_1400035C7
0x1400035a1  mov     rcx, [rbp+188h]; this
0x1400035a8  lea     r8, aWil; "wil"
0x1400035af  mov     r14d, 8007000Eh
0x1400035b5  mov     edx, 14Bh; void *
0x1400035ba  mov     r9d, r14d; char *
0x1400035bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400035c2  jmp     loc_14000365A
0x1400035c7  xorps   xmm0, xmm0
0x1400035ca  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1400035d0  test    sil, 3
0x1400035d4  jnz     loc_140003778
0x1400035da  mov     r9, rsi
0x1400035dd  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1400035e2  shr     r9, 2; unsigned __int64
0x1400035e6  lea     rcx, [rsp+280h+hObject]; this
0x1400035eb  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1400035f0  mov     r14d, eax
0x1400035f3  test    eax, eax
0x1400035f5  jns     loc_1400036A1
0x1400035fb  mov     rcx, [rbp+188h]; this
0x140003602  lea     r8, aWil; "wil"
0x140003609  mov     r9d, eax; char *
0x14000360c  mov     edx, 14Eh; void *
0x140003611  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003616  mov     rcx, [rsp+280h+hObject+8]; hObject
0x14000361b  test    rcx, rcx
0x14000361e  jz      short loc_14000362E
0x140003620  call    cs:__imp_CloseHandle
0x140003626  test    eax, eax
0x140003628  jz      loc_14000377E
0x14000362e  mov     rcx, [rsp+280h+hObject]; hObject
0x140003633  test    rcx, rcx
0x140003636  jz      short loc_140003646
0x140003638  call    cs:__imp_CloseHandle
0x14000363e  test    eax, eax
0x140003640  jz      loc_140003790
0x140003646  call    cs:__imp_GetProcessHeap
0x14000364c  mov     r8, rsi; lpMem
0x14000364f  xor     edx, edx; dwFlags
0x140003651  mov     rcx, rax; hHeap
0x140003654  call    cs:__imp_HeapFree
0x14000365a  mov     rcx, [rbp+188h]; this
0x140003661  lea     r8, aWil; "wil"
0x140003668  mov     r9d, r14d; char *
0x14000366b  mov     edx, 137h; void *
0x140003670  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003675  test    rdi, rdi
0x140003678  jz      short loc_14000368B
0x14000367a  mov     rcx, rdi; hMutex
0x14000367d  call    cs:__imp_ReleaseMutex
0x140003683  test    eax, eax
0x140003685  jz      loc_1400037A2
0x14000368b  mov     rcx, rbx; hObject
0x14000368e  call    cs:__imp_CloseHandle
0x140003694  test    eax, eax
0x140003696  jz      loc_1400037B4
0x14000369c  mov     eax, r14d
0x14000369f  jmp     short loc_14000370F
0x1400036a1  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1400036a6  xor     edx, edx; Val
0x1400036a8  mov     dword ptr [rsi], 1
0x1400036ae  lea     rcx, [rsi+22h]; void *
0x1400036b2  mov     [rsi+8], rbx
0x1400036b6  movdqu  xmmword ptr [rsi+10h], xmm0
0x1400036bb  lea     r8d, [rdx+56h]; Size
0x1400036bf  call    memset_0
0x1400036c4  xor     edx, edx; Val
0x1400036c6  mov     word ptr [rsi+20h], 58h ; 'X'
0x1400036cc  lea     rcx, [rsi+28h]; void *
0x1400036d0  mov     dword ptr [rsi+24h], 1
0x1400036d7  lea     r8d, [rdx+50h]; Size
0x1400036db  call    memset_0
0x1400036e0  xor     ebx, ebx
0x1400036e2  mov     [r15], rsi
0x1400036e5  test    rdi, rdi
0x1400036e8  jz      short loc_1400036FB
0x1400036ea  mov     rcx, rdi; hMutex
0x1400036ed  call    cs:__imp_ReleaseMutex
0x1400036f3  test    eax, eax
0x1400036f5  jz      loc_1400037C6
0x1400036fb  test    rbx, rbx
0x1400036fe  jz      short loc_14000370D
0x140003700  mov     rcx, rbx; hObject
0x140003703  call    cs:__imp_CloseHandle
0x140003709  test    eax, eax
0x14000370b  jz      short loc_140003735
0x14000370d  xor     eax, eax
0x14000370f  mov     rcx, [rbp+180h+var_30]
0x140003716  xor     rcx, rsp; StackCookie
0x140003719  call    __security_check_cookie
0x14000371e  mov     rbx, [rsp+280h+arg_10]
0x140003726  add     rsp, 260h
0x14000372d  pop     r15
0x14000372f  pop     r14
0x140003731  pop     rdi
0x140003732  pop     rsi
0x140003733  pop     rbp
0x140003734  retn
0x140003735  mov     rcx, [rbp+188h]; this
0x14000373c  mov     edx, 0A0Bh; void *
0x140003741  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003747  mov     rcx, [rbp+188h]; this
0x14000374e  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140003754  mov     rcx, [rbp+188h]; this
0x14000375b  mov     edx, 0A15h; void *
0x140003760  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003766  mov     rcx, [rbp+188h]; this
0x14000376d  mov     edx, 0A0Bh; void *
0x140003772  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003778  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000377e  mov     rcx, [rbp+188h]; this
0x140003785  mov     edx, 0A0Bh; void *
0x14000378a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003790  mov     rcx, [rbp+188h]; this
0x140003797  mov     edx, 0A0Bh; void *
0x14000379c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400037a2  mov     rcx, [rbp+188h]; this
0x1400037a9  mov     edx, 0A15h; void *
0x1400037ae  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400037b4  mov     rcx, [rbp+188h]; this
0x1400037bb  mov     edx, 0A0Bh; void *
0x1400037c0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400037c6  mov     rcx, [rbp+188h]; this
0x1400037cd  mov     edx, 0A15h; void *
0x1400037d2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
