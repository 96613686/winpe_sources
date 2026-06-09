# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18001078c`
- end: `0x180010b2a`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180011eec`

## callees

- `0x18000465c`
- `0x18001078c`
- `0x180010f00`
- `0x180011364`
- `0x180011c88`
- `0x180012878`
- `0x180013b10`
- `0x1800141ac`
- `0x18001498c`
- `0x18001499c`
- `0x1800157be`
- `0x1800157f0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800108b7`
- `KERNEL32!CloseHandle` at `0x180010979`
- `KERNEL32!CloseHandle` at `0x180010991`
- `KERNEL32!CloseHandle` at `0x1800109e0`
- `KERNEL32!CloseHandle` at `0x180010a55`
- `KERNEL32!CloseHandle` at `0x1800108b7`
- `KERNEL32!CloseHandle` at `0x180010979`
- `KERNEL32!CloseHandle` at `0x180010991`
- `KERNEL32!CloseHandle` at `0x1800109e0`
- `KERNEL32!CloseHandle` at `0x180010a55`
- `KERNEL32!GetCurrentProcessId` at `0x1800107c5`
- `KERNEL32!GetCurrentProcessId` at `0x1800107c5`
- `KERNEL32!HeapFree` at `0x1800109ad`
- `KERNEL32!HeapFree` at `0x1800109ad`
- `KERNEL32!ReleaseMutex` at `0x1800108a6`
- `KERNEL32!ReleaseMutex` at `0x1800109cf`
- `KERNEL32!ReleaseMutex` at `0x180010a3f`
- `KERNEL32!ReleaseMutex` at `0x1800108a6`
- `KERNEL32!ReleaseMutex` at `0x1800109cf`
- `KERNEL32!ReleaseMutex` at `0x180010a3f`
- `KERNEL32!WaitForSingleObjectEx` at `0x180010825`
- `KERNEL32!WaitForSingleObjectEx` at `0x180010825`
- `KERNEL32!GetProcessHeap` at `0x18001099f`
- `KERNEL32!GetProcessHeap` at `0x18001099f`
- `KERNEL32!CreateMutexExW` at `0x180010804`
- `KERNEL32!CreateMutexExW` at `0x180010804`

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
  __int64 v18; // r8
  const char *v19; // r9
  __int64 v20; // r8
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  unsigned int v25; // r8d
  _QWORD *v26; // rsi
  unsigned int v27; // r14d
  unsigned int v28; // r8d
  int v29; // eax
  unsigned int v30; // r8d
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
  const char *v34; // r9
  HANDLE ProcessHeap; // rax
  __int64 v36; // r8
  const char *v37; // r9
  __int64 v38; // r8
  const char *v39; // r9
  __int128 v40; // xmm0
  __int64 v41; // r8
  const char *v42; // r9
  __int64 v43; // r8
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
0x18001078c  mov     [rsp-8+arg_10], rbx
0x180010791  push    rbp
0x180010792  push    rsi
0x180010793  push    rdi
0x180010794  push    r14
0x180010796  push    r15
0x180010798  lea     rbp, [rsp-160h]
0x1800107a0  sub     rsp, 260h
0x1800107a7  mov     rax, cs:__security_cookie
0x1800107ae  xor     rax, rsp
0x1800107b1  mov     [rbp+180h+var_30], rax
0x1800107b8  mov     r15, rdx
0x1800107bb  mov     qword ptr [rdx], 0
0x1800107c2  mov     rbx, rcx
0x1800107c5  call    cs:__imp_GetCurrentProcessId
0x1800107cb  mov     r14d, 78h ; 'x'
0x1800107d1  mov     [rsp+280h+var_258], rbx
0x1800107d6  mov     r9d, eax
0x1800107d9  mov     [rsp+280h+var_260], r14d; int
0x1800107de  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800107e5  mov     edx, 104h; unsigned __int64
0x1800107ea  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800107ef  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800107f4  mov     r9d, 1F0001h; dwDesiredAccess
0x1800107fa  lea     rdx, [rsp+280h+Name]; lpName
0x1800107ff  xor     r8d, r8d; dwFlags
0x180010802  xor     ecx, ecx; lpMutexAttributes
0x180010804  call    cs:__imp_CreateMutexExW
0x18001080a  mov     rbx, rax
0x18001080d  test    rax, rax
0x180010810  jnz     short loc_18001081C
0x180010812  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180010817  jmp     loc_180010A61
0x18001081c  xor     r8d, r8d; bAlertable
0x18001081f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180010822  mov     rcx, rbx; hHandle
0x180010825  call    cs:__imp_WaitForSingleObjectEx
0x18001082b  cmp     eax, 102h
0x180010830  jz      short loc_180010842
0x180010832  test    eax, 0FFFFFF7Fh
0x180010837  jnz     loc_180010A99
0x18001083d  mov     rdi, rbx
0x180010840  jmp     short loc_180010844
0x180010842  xor     edi, edi
0x180010844  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180010849  mov     [rsp+280h+hObject], 0
0x180010852  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180010857  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18001085c  mov     esi, eax
0x18001085e  test    eax, eax
0x180010860  jns     short loc_1800108CC
0x180010862  mov     rcx, [rbp+188h]; this
0x180010869  mov     r9d, eax; char *
0x18001086c  mov     edx, 66h ; 'f'; void *
0x180010871  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010876  mov     rcx, [rbp+188h]; this
0x18001087d  mov     r9d, esi; char *
0x180010880  mov     edx, 6Fh ; 'o'; void *
0x180010885  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001088a  mov     rcx, [rbp+188h]; this
0x180010891  mov     r9d, esi; char *
0x180010894  mov     edx, 12Eh; void *
0x180010899  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001089e  test    rdi, rdi
0x1800108a1  jz      short loc_1800108B4
0x1800108a3  mov     rcx, rdi; hMutex
0x1800108a6  call    cs:__imp_ReleaseMutex
0x1800108ac  test    eax, eax
0x1800108ae  jz      loc_180010AA6
0x1800108b4  mov     rcx, rbx; hObject
0x1800108b7  call    cs:__imp_CloseHandle
0x1800108bd  test    eax, eax
0x1800108bf  jz      loc_180010AB8
0x1800108c5  mov     eax, esi
0x1800108c7  jmp     loc_180010A61
0x1800108cc  mov     rax, [rsp+280h+hObject]
0x1800108d1  lea     rcx, ds:0[rax*4]
0x1800108d9  test    rcx, rcx
0x1800108dc  jz      short loc_1800108EC
0x1800108de  mov     [r15], rcx
0x1800108e1  mov     eax, [rcx]
0x1800108e3  inc     eax
0x1800108e5  mov     [rcx], eax
0x1800108e7  jmp     loc_180010A37
0x1800108ec  mov     rdx, r14; dwBytes
0x1800108ef  mov     qword ptr [r15], 0
0x1800108f6  mov     ecx, 8; dwFlags
0x1800108fb  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180010900  mov     rsi, rax
0x180010903  test    rax, rax
0x180010906  jnz     short loc_180010927
0x180010908  mov     rcx, [rbp+188h]; this
0x18001090f  mov     r14d, 8007000Eh
0x180010915  mov     r9d, r14d; char *
0x180010918  mov     edx, 14Bh; void *
0x18001091d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010922  jmp     loc_1800109B3
0x180010927  xorps   xmm0, xmm0
0x18001092a  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180010930  test    sil, 3
0x180010934  jnz     loc_180010ACA
0x18001093a  mov     r9, rsi
0x18001093d  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180010942  shr     r9, 2; unsigned __int64
0x180010946  lea     rcx, [rsp+280h+hObject]; this
0x18001094b  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180010950  mov     r14d, eax
0x180010953  test    eax, eax
0x180010955  jns     loc_1800109F3
0x18001095b  mov     rcx, [rbp+188h]; this
0x180010962  mov     r9d, eax; char *
0x180010965  mov     edx, 14Eh; void *
0x18001096a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001096f  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180010974  test    rcx, rcx
0x180010977  jz      short loc_180010987
0x180010979  call    cs:__imp_CloseHandle
0x18001097f  test    eax, eax
0x180010981  jz      loc_180010AD0
0x180010987  mov     rcx, [rsp+280h+hObject]; hObject
0x18001098c  test    rcx, rcx
0x18001098f  jz      short loc_18001099F
0x180010991  call    cs:__imp_CloseHandle
0x180010997  test    eax, eax
0x180010999  jz      loc_180010AE2
0x18001099f  call    cs:__imp_GetProcessHeap
0x1800109a5  mov     r8, rsi; lpMem
0x1800109a8  xor     edx, edx; dwFlags
0x1800109aa  mov     rcx, rax; hHeap
0x1800109ad  call    cs:__imp_HeapFree
0x1800109b3  mov     rcx, [rbp+188h]; this
0x1800109ba  mov     r9d, r14d; char *
0x1800109bd  mov     edx, 137h; void *
0x1800109c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800109c7  test    rdi, rdi
0x1800109ca  jz      short loc_1800109DD
0x1800109cc  mov     rcx, rdi; hMutex
0x1800109cf  call    cs:__imp_ReleaseMutex
0x1800109d5  test    eax, eax
0x1800109d7  jz      loc_180010AF4
0x1800109dd  mov     rcx, rbx; hObject
0x1800109e0  call    cs:__imp_CloseHandle
0x1800109e6  test    eax, eax
0x1800109e8  jz      loc_180010B06
0x1800109ee  mov     eax, r14d
0x1800109f1  jmp     short loc_180010A61
0x1800109f3  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800109f8  xor     edx, edx; Val
0x1800109fa  mov     dword ptr [rsi], 1
0x180010a00  lea     rcx, [rsi+22h]; void *
0x180010a04  mov     [rsi+8], rbx
0x180010a08  movdqu  xmmword ptr [rsi+10h], xmm0
0x180010a0d  lea     r8d, [rdx+56h]; Size
0x180010a11  call    memset_0
0x180010a16  xor     edx, edx; Val
0x180010a18  mov     word ptr [rsi+20h], 58h ; 'X'
0x180010a1e  lea     rcx, [rsi+28h]; void *
0x180010a22  mov     dword ptr [rsi+24h], 1
0x180010a29  lea     r8d, [rdx+50h]; Size
0x180010a2d  call    memset_0
0x180010a32  xor     ebx, ebx
0x180010a34  mov     [r15], rsi
0x180010a37  test    rdi, rdi
0x180010a3a  jz      short loc_180010A4D
0x180010a3c  mov     rcx, rdi; hMutex
0x180010a3f  call    cs:__imp_ReleaseMutex
0x180010a45  test    eax, eax
0x180010a47  jz      loc_180010B18
0x180010a4d  test    rbx, rbx
0x180010a50  jz      short loc_180010A5F
0x180010a52  mov     rcx, rbx; hObject
0x180010a55  call    cs:__imp_CloseHandle
0x180010a5b  test    eax, eax
0x180010a5d  jz      short loc_180010A87
0x180010a5f  xor     eax, eax
0x180010a61  mov     rcx, [rbp+180h+var_30]
0x180010a68  xor     rcx, rsp; StackCookie
0x180010a6b  call    __security_check_cookie
0x180010a70  mov     rbx, [rsp+280h+arg_10]
0x180010a78  add     rsp, 260h
0x180010a7f  pop     r15
0x180010a81  pop     r14
0x180010a83  pop     rdi
0x180010a84  pop     rsi
0x180010a85  pop     rbp
0x180010a86  retn
0x180010a87  mov     rcx, [rbp+188h]; this
0x180010a8e  mov     edx, 0A0Bh; void *
0x180010a93  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010a99  mov     rcx, [rbp+188h]; this
0x180010aa0  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180010aa6  mov     rcx, [rbp+188h]; this
0x180010aad  mov     edx, 0A15h; void *
0x180010ab2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010ab8  mov     rcx, [rbp+188h]; this
0x180010abf  mov     edx, 0A0Bh; void *
0x180010ac4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010aca  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180010ad0  mov     rcx, [rbp+188h]; this
0x180010ad7  mov     edx, 0A0Bh; void *
0x180010adc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010ae2  mov     rcx, [rbp+188h]; this
0x180010ae9  mov     edx, 0A0Bh; void *
0x180010aee  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010af4  mov     rcx, [rbp+188h]; this
0x180010afb  mov     edx, 0A15h; void *
0x180010b00  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010b06  mov     rcx, [rbp+188h]; this
0x180010b0d  mov     edx, 0A0Bh; void *
0x180010b12  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010b18  mov     rcx, [rbp+188h]; this
0x180010b1f  mov     edx, 0A15h; void *
0x180010b24  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
