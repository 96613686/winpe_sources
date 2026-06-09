# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1400036fc`
- end: `0x140003a9a`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1400048fc`

## callees

- `0x140001ee0`
- `0x1400028b8`
- `0x1400036fc`
- `0x140003ad0`
- `0x140003ff4`
- `0x140004698`
- `0x14000542c`
- `0x140005b54`
- `0x140005f18`
- `0x140005fa4`
- `0x14000635c`
- `0x14000636c`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000391d`
- `KERNEL32!HeapFree` at `0x14000391d`
- `KERNEL32!ReleaseMutex` at `0x140003816`
- `KERNEL32!ReleaseMutex` at `0x14000393f`
- `KERNEL32!ReleaseMutex` at `0x1400039af`
- `KERNEL32!ReleaseMutex` at `0x140003816`
- `KERNEL32!ReleaseMutex` at `0x14000393f`
- `KERNEL32!ReleaseMutex` at `0x1400039af`
- `KERNEL32!WaitForSingleObjectEx` at `0x140003795`
- `KERNEL32!WaitForSingleObjectEx` at `0x140003795`
- `KERNEL32!CloseHandle` at `0x140003827`
- `KERNEL32!CloseHandle` at `0x1400038e9`
- `KERNEL32!CloseHandle` at `0x140003901`
- `KERNEL32!CloseHandle` at `0x140003950`
- `KERNEL32!CloseHandle` at `0x1400039c5`
- `KERNEL32!CloseHandle` at `0x140003827`
- `KERNEL32!CloseHandle` at `0x1400038e9`
- `KERNEL32!CloseHandle` at `0x140003901`
- `KERNEL32!CloseHandle` at `0x140003950`
- `KERNEL32!CloseHandle` at `0x1400039c5`
- `KERNEL32!CreateMutexExW` at `0x140003774`
- `KERNEL32!CreateMutexExW` at `0x140003774`
- `KERNEL32!GetCurrentProcessId` at `0x140003735`
- `KERNEL32!GetCurrentProcessId` at `0x140003735`
- `KERNEL32!GetProcessHeap` at `0x14000390f`
- `KERNEL32!GetProcessHeap` at `0x14000390f`

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
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // r8d
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  __int64 v25; // r8
  _QWORD *v26; // rsi
  unsigned int v27; // r14d
  unsigned int v28; // r8d
  int v29; // eax
  unsigned int v30; // r8d
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v36; // r8d
  const char *v37; // r9
  unsigned int v38; // r8d
  const char *v39; // r9
  __int128 v40; // xmm0
  unsigned int v41; // r8d
  const char *v42; // r9
  unsigned int v43; // r8d
  const char *v44; // r9
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
  int v47; // [rsp+20h] [rbp-E0h]
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v45);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v46);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v18, v19);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
    return v15;
  }
  v22 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v22;
    ++*v22;
    goto LABEL_28;
  }
  *a2 = 0;
  v23 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v26 = (_QWORD *)v23;
  if ( v23 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v23 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    v29 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v25,
            v23 >> 2);
    v27 = v29;
    if ( v29 >= 0 )
    {
      v40 = *(_OWORD *)hObject;
      *(_DWORD *)v26 = 1;
      v26[1] = v6;
      *((_OWORD *)v26 + 1) = v40;
      memset_0((char *)v26 + 34, 0, 0x56u);
      *((_WORD *)v26 + 16) = 88;
      *((_DWORD *)v26 + 9) = 1;
      memset_0(v26 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v26;
LABEL_28:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v41, v42);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v43, v44);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v30, (const char *)(unsigned int)v29, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v26);
  }
  else
  {
    v27 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v25, (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v28, (const char *)v27, v47);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
  return v27;
}

```

## disassembly

```asm
0x1400036fc  mov     [rsp-8+arg_10], rbx
0x140003701  push    rbp
0x140003702  push    rsi
0x140003703  push    rdi
0x140003704  push    r14
0x140003706  push    r15
0x140003708  lea     rbp, [rsp-160h]
0x140003710  sub     rsp, 260h
0x140003717  mov     rax, cs:__security_cookie
0x14000371e  xor     rax, rsp
0x140003721  mov     [rbp+180h+var_30], rax
0x140003728  mov     r15, rdx
0x14000372b  mov     qword ptr [rdx], 0
0x140003732  mov     rbx, rcx
0x140003735  call    cs:__imp_GetCurrentProcessId
0x14000373b  mov     r14d, 78h ; 'x'
0x140003741  mov     [rsp+280h+var_258], rbx
0x140003746  mov     r9d, eax
0x140003749  mov     [rsp+280h+var_260], r14d; int
0x14000374e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140003755  mov     edx, 104h; unsigned __int64
0x14000375a  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000375f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140003764  mov     r9d, 1F0001h; dwDesiredAccess
0x14000376a  lea     rdx, [rsp+280h+Name]; lpName
0x14000376f  xor     r8d, r8d; dwFlags
0x140003772  xor     ecx, ecx; lpMutexAttributes
0x140003774  call    cs:__imp_CreateMutexExW
0x14000377a  mov     rbx, rax
0x14000377d  test    rax, rax
0x140003780  jnz     short loc_14000378C
0x140003782  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140003787  jmp     loc_1400039D1
0x14000378c  xor     r8d, r8d; bAlertable
0x14000378f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140003792  mov     rcx, rbx; hHandle
0x140003795  call    cs:__imp_WaitForSingleObjectEx
0x14000379b  cmp     eax, 102h
0x1400037a0  jz      short loc_1400037B2
0x1400037a2  test    eax, 0FFFFFF7Fh
0x1400037a7  jnz     loc_140003A09
0x1400037ad  mov     rdi, rbx
0x1400037b0  jmp     short loc_1400037B4
0x1400037b2  xor     edi, edi
0x1400037b4  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1400037b9  mov     [rsp+280h+hObject], 0
0x1400037c2  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400037c7  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1400037cc  mov     esi, eax
0x1400037ce  test    eax, eax
0x1400037d0  jns     short loc_14000383C
0x1400037d2  mov     rcx, [rbp+188h]; this
0x1400037d9  mov     r9d, eax; char *
0x1400037dc  mov     edx, 66h ; 'f'; void *
0x1400037e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400037e6  mov     rcx, [rbp+188h]; this
0x1400037ed  mov     r9d, esi; char *
0x1400037f0  mov     edx, 6Fh ; 'o'; void *
0x1400037f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400037fa  mov     rcx, [rbp+188h]; this
0x140003801  mov     r9d, esi; char *
0x140003804  mov     edx, 12Eh; void *
0x140003809  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000380e  test    rdi, rdi
0x140003811  jz      short loc_140003824
0x140003813  mov     rcx, rdi; hMutex
0x140003816  call    cs:__imp_ReleaseMutex
0x14000381c  test    eax, eax
0x14000381e  jz      loc_140003A16
0x140003824  mov     rcx, rbx; hObject
0x140003827  call    cs:__imp_CloseHandle
0x14000382d  test    eax, eax
0x14000382f  jz      loc_140003A28
0x140003835  mov     eax, esi
0x140003837  jmp     loc_1400039D1
0x14000383c  mov     rax, [rsp+280h+hObject]
0x140003841  lea     rcx, ds:0[rax*4]
0x140003849  test    rcx, rcx
0x14000384c  jz      short loc_14000385C
0x14000384e  mov     [r15], rcx
0x140003851  mov     eax, [rcx]
0x140003853  inc     eax
0x140003855  mov     [rcx], eax
0x140003857  jmp     loc_1400039A7
0x14000385c  mov     rdx, r14; dwBytes
0x14000385f  mov     qword ptr [r15], 0
0x140003866  mov     ecx, 8; dwFlags
0x14000386b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140003870  mov     rsi, rax
0x140003873  test    rax, rax
0x140003876  jnz     short loc_140003897
0x140003878  mov     rcx, [rbp+188h]; this
0x14000387f  mov     r14d, 8007000Eh
0x140003885  mov     r9d, r14d; char *
0x140003888  mov     edx, 14Bh; void *
0x14000388d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003892  jmp     loc_140003923
0x140003897  xorps   xmm0, xmm0
0x14000389a  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1400038a0  test    sil, 3
0x1400038a4  jnz     loc_140003A3A
0x1400038aa  mov     r9, rsi
0x1400038ad  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1400038b2  shr     r9, 2; unsigned __int64
0x1400038b6  lea     rcx, [rsp+280h+hObject]; this
0x1400038bb  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1400038c0  mov     r14d, eax
0x1400038c3  test    eax, eax
0x1400038c5  jns     loc_140003963
0x1400038cb  mov     rcx, [rbp+188h]; this
0x1400038d2  mov     r9d, eax; char *
0x1400038d5  mov     edx, 14Eh; void *
0x1400038da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400038df  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1400038e4  test    rcx, rcx
0x1400038e7  jz      short loc_1400038F7
0x1400038e9  call    cs:__imp_CloseHandle
0x1400038ef  test    eax, eax
0x1400038f1  jz      loc_140003A40
0x1400038f7  mov     rcx, [rsp+280h+hObject]; hObject
0x1400038fc  test    rcx, rcx
0x1400038ff  jz      short loc_14000390F
0x140003901  call    cs:__imp_CloseHandle
0x140003907  test    eax, eax
0x140003909  jz      loc_140003A52
0x14000390f  call    cs:__imp_GetProcessHeap
0x140003915  mov     r8, rsi; lpMem
0x140003918  xor     edx, edx; dwFlags
0x14000391a  mov     rcx, rax; hHeap
0x14000391d  call    cs:__imp_HeapFree
0x140003923  mov     rcx, [rbp+188h]; this
0x14000392a  mov     r9d, r14d; char *
0x14000392d  mov     edx, 137h; void *
0x140003932  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003937  test    rdi, rdi
0x14000393a  jz      short loc_14000394D
0x14000393c  mov     rcx, rdi; hMutex
0x14000393f  call    cs:__imp_ReleaseMutex
0x140003945  test    eax, eax
0x140003947  jz      loc_140003A64
0x14000394d  mov     rcx, rbx; hObject
0x140003950  call    cs:__imp_CloseHandle
0x140003956  test    eax, eax
0x140003958  jz      loc_140003A76
0x14000395e  mov     eax, r14d
0x140003961  jmp     short loc_1400039D1
0x140003963  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x140003968  xor     edx, edx; Val
0x14000396a  mov     dword ptr [rsi], 1
0x140003970  lea     rcx, [rsi+22h]; void *
0x140003974  mov     [rsi+8], rbx
0x140003978  movdqu  xmmword ptr [rsi+10h], xmm0
0x14000397d  lea     r8d, [rdx+56h]; Size
0x140003981  call    memset_0
0x140003986  xor     edx, edx; Val
0x140003988  mov     word ptr [rsi+20h], 58h ; 'X'
0x14000398e  lea     rcx, [rsi+28h]; void *
0x140003992  mov     dword ptr [rsi+24h], 1
0x140003999  lea     r8d, [rdx+50h]; Size
0x14000399d  call    memset_0
0x1400039a2  xor     ebx, ebx
0x1400039a4  mov     [r15], rsi
0x1400039a7  test    rdi, rdi
0x1400039aa  jz      short loc_1400039BD
0x1400039ac  mov     rcx, rdi; hMutex
0x1400039af  call    cs:__imp_ReleaseMutex
0x1400039b5  test    eax, eax
0x1400039b7  jz      loc_140003A88
0x1400039bd  test    rbx, rbx
0x1400039c0  jz      short loc_1400039CF
0x1400039c2  mov     rcx, rbx; hObject
0x1400039c5  call    cs:__imp_CloseHandle
0x1400039cb  test    eax, eax
0x1400039cd  jz      short loc_1400039F7
0x1400039cf  xor     eax, eax
0x1400039d1  mov     rcx, [rbp+180h+var_30]
0x1400039d8  xor     rcx, rsp; StackCookie
0x1400039db  call    __security_check_cookie
0x1400039e0  mov     rbx, [rsp+280h+arg_10]
0x1400039e8  add     rsp, 260h
0x1400039ef  pop     r15
0x1400039f1  pop     r14
0x1400039f3  pop     rdi
0x1400039f4  pop     rsi
0x1400039f5  pop     rbp
0x1400039f6  retn
0x1400039f7  mov     rcx, [rbp+188h]; this
0x1400039fe  mov     edx, 0A0Bh; void *
0x140003a03  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003a09  mov     rcx, [rbp+188h]; this
0x140003a10  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140003a16  mov     rcx, [rbp+188h]; this
0x140003a1d  mov     edx, 0A15h; void *
0x140003a22  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003a28  mov     rcx, [rbp+188h]; this
0x140003a2f  mov     edx, 0A0Bh; void *
0x140003a34  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003a3a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140003a40  mov     rcx, [rbp+188h]; this
0x140003a47  mov     edx, 0A0Bh; void *
0x140003a4c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003a52  mov     rcx, [rbp+188h]; this
0x140003a59  mov     edx, 0A0Bh; void *
0x140003a5e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003a64  mov     rcx, [rbp+188h]; this
0x140003a6b  mov     edx, 0A15h; void *
0x140003a70  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003a76  mov     rcx, [rbp+188h]; this
0x140003a7d  mov     edx, 0A0Bh; void *
0x140003a82  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003a88  mov     rcx, [rbp+188h]; this
0x140003a8f  mov     edx, 0A15h; void *
0x140003a94  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
