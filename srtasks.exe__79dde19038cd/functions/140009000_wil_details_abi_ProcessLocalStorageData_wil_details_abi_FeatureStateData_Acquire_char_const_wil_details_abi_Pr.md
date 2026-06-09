# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x140009000`
- end: `0x1400093c7`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1400096a4`

## callees

- `0x140005cd0`
- `0x140005e24`
- `0x14000854c`
- `0x140009000`
- `0x1400093d0`
- `0x140009834`
- `0x14000a158`
- `0x14000bf30`
- `0x14000c5cc`
- `0x14000cdac`
- `0x14000cdbc`
- `0x14001094e`
- `0x140010980`

## import_xrefs

- `KERNEL32!InitializeCriticalSectionEx` at `0x1400092a9`
- `KERNEL32!InitializeCriticalSectionEx` at `0x1400092a9`
- `KERNEL32!ReleaseMutex` at `0x140009119`
- `KERNEL32!ReleaseMutex` at `0x140009240`
- `KERNEL32!ReleaseMutex` at `0x1400092dc`
- `KERNEL32!ReleaseMutex` at `0x140009119`
- `KERNEL32!ReleaseMutex` at `0x140009240`
- `KERNEL32!ReleaseMutex` at `0x1400092dc`
- `KERNEL32!WaitForSingleObjectEx` at `0x140009098`
- `KERNEL32!WaitForSingleObjectEx` at `0x140009098`
- `KERNEL32!CreateMutexExW` at `0x140009077`
- `KERNEL32!CreateMutexExW` at `0x140009077`
- `KERNEL32!HeapFree` at `0x14000921e`
- `KERNEL32!HeapFree` at `0x14000921e`
- `KERNEL32!GetProcessHeap` at `0x140009210`
- `KERNEL32!GetProcessHeap` at `0x140009210`
- `KERNEL32!CloseHandle` at `0x14000912a`
- `KERNEL32!CloseHandle` at `0x1400091ea`
- `KERNEL32!CloseHandle` at `0x140009202`
- `KERNEL32!CloseHandle` at `0x140009251`
- `KERNEL32!CloseHandle` at `0x1400092f2`
- `KERNEL32!CloseHandle` at `0x14000912a`
- `KERNEL32!CloseHandle` at `0x1400091ea`
- `KERNEL32!CloseHandle` at `0x140009202`
- `KERNEL32!CloseHandle` at `0x140009251`
- `KERNEL32!CloseHandle` at `0x1400092f2`
- `KERNEL32!GetCurrentProcessId` at `0x140009039`
- `KERNEL32!GetCurrentProcessId` at `0x140009039`

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
  _DWORD *v26; // r14
  unsigned int v27; // r8d
  int v28; // eax
  unsigned int v29; // r8d
  __int64 v30; // r8
  const char *v31; // r9
  __int64 v32; // r8
  const char *v33; // r9
  HANDLE ProcessHeap; // rax
  __int64 v35; // r8
  const char *v36; // r9
  __int64 v37; // r8
  const char *v38; // r9
  __int128 v39; // xmm0
  __int64 v40; // r8
  const char *v41; // r9
  __int64 v42; // r8
  const char *v43; // r9
  int v44; // [rsp+20h] [rbp-E0h]
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v44);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v45);
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
  v23 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v26 = (_DWORD *)v23;
  if ( !v23 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v25, (const char *)0x8007000ELL, 304);
LABEL_23:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v27, (const char *)v15, v46);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v35, v36);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v37, v38);
    return v15;
  }
  *(_OWORD *)hObject = 0;
  if ( (v23 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
  v28 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)hObject,
          Name,
          v25,
          v23 >> 2);
  v15 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v29, (const char *)(unsigned int)v28, 304);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v26);
    goto LABEL_23;
  }
  v39 = *(_OWORD *)hObject;
  *v26 = 1;
  *((_QWORD *)v26 + 1) = v6;
  *((_OWORD *)v26 + 1) = v39;
  memset_0(v26 + 10, 0, 0x108u);
  *((_QWORD *)v26 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v26 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v26 + 58), 0, 0);
  *((_QWORD *)v26 + 34) = 0;
  *((_QWORD *)v26 + 35) = 0;
  *((_QWORD *)v26 + 36) = 0;
  *((_QWORD *)v26 + 37) = 0;
  v6 = 0;
  *a2 = v26;
LABEL_28:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v40, v41);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v42, v43);
  return 0;
}

```

## disassembly

```asm
0x140009000  mov     [rsp-8+arg_10], rbx
0x140009005  push    rbp
0x140009006  push    rsi
0x140009007  push    rdi
0x140009008  push    r14
0x14000900a  push    r15
0x14000900c  lea     rbp, [rsp-160h]
0x140009014  sub     rsp, 260h
0x14000901b  mov     rax, cs:__security_cookie
0x140009022  xor     rax, rsp
0x140009025  mov     [rbp+180h+var_30], rax
0x14000902c  mov     r15, rdx
0x14000902f  mov     qword ptr [rdx], 0
0x140009036  mov     rbx, rcx
0x140009039  call    cs:__imp_GetCurrentProcessId
0x14000903f  mov     r14d, 130h
0x140009045  mov     [rsp+280h+var_258], rbx
0x14000904a  mov     r9d, eax
0x14000904d  mov     [rsp+280h+var_260], r14d; int
0x140009052  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140009059  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000905e  lea     edx, [r14-2Ch]; unsigned __int64
0x140009062  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140009067  mov     r9d, 1F0001h; dwDesiredAccess
0x14000906d  lea     rdx, [rsp+280h+Name]; lpName
0x140009072  xor     r8d, r8d; dwFlags
0x140009075  xor     ecx, ecx; lpMutexAttributes
0x140009077  call    cs:__imp_CreateMutexExW
0x14000907d  mov     rbx, rax
0x140009080  test    rax, rax
0x140009083  jnz     short loc_14000908F
0x140009085  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000908a  jmp     loc_1400092FE
0x14000908f  xor     r8d, r8d; bAlertable
0x140009092  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140009095  mov     rcx, rbx; hHandle
0x140009098  call    cs:__imp_WaitForSingleObjectEx
0x14000909e  cmp     eax, 102h
0x1400090a3  jz      short loc_1400090B5
0x1400090a5  test    eax, 0FFFFFF7Fh
0x1400090aa  jnz     loc_140009348
0x1400090b0  mov     rdi, rbx
0x1400090b3  jmp     short loc_1400090B7
0x1400090b5  xor     edi, edi
0x1400090b7  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1400090bc  mov     [rsp+280h+hObject], 0
0x1400090c5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400090ca  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1400090cf  mov     esi, eax
0x1400090d1  test    eax, eax
0x1400090d3  jns     short loc_14000913F
0x1400090d5  mov     rcx, [rbp+188h]; this
0x1400090dc  mov     r9d, eax; char *
0x1400090df  mov     edx, 66h ; 'f'; void *
0x1400090e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400090e9  mov     rcx, [rbp+188h]; this
0x1400090f0  mov     r9d, esi; char *
0x1400090f3  mov     edx, 6Fh ; 'o'; void *
0x1400090f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400090fd  mov     rcx, [rbp+188h]; this
0x140009104  mov     r9d, esi; char *
0x140009107  mov     edx, 12Eh; void *
0x14000910c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009111  test    rdi, rdi
0x140009114  jz      short loc_140009127
0x140009116  mov     rcx, rdi; hMutex
0x140009119  call    cs:__imp_ReleaseMutex
0x14000911f  test    eax, eax
0x140009121  jz      loc_140009355
0x140009127  mov     rcx, rbx; hObject
0x14000912a  call    cs:__imp_CloseHandle
0x140009130  test    eax, eax
0x140009132  jz      loc_140009367
0x140009138  mov     eax, esi
0x14000913a  jmp     loc_1400092FE
0x14000913f  mov     rax, [rsp+280h+hObject]
0x140009144  lea     rcx, ds:0[rax*4]
0x14000914c  test    rcx, rcx
0x14000914f  jz      short loc_14000915F
0x140009151  mov     [r15], rcx
0x140009154  mov     eax, [rcx]
0x140009156  inc     eax
0x140009158  mov     [rcx], eax
0x14000915a  jmp     loc_1400092D4
0x14000915f  mov     rdx, r14; dwBytes
0x140009162  mov     qword ptr [r15], 0
0x140009169  mov     ecx, 8; dwFlags
0x14000916e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140009173  mov     r14, rax
0x140009176  test    rax, rax
0x140009179  jnz     short loc_140009199
0x14000917b  mov     rcx, [rbp+188h]; this
0x140009182  mov     esi, 8007000Eh
0x140009187  mov     r9d, esi; char *
0x14000918a  mov     edx, 14Bh; void *
0x14000918f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009194  jmp     loc_140009224
0x140009199  xorps   xmm0, xmm0
0x14000919c  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1400091a2  test    r14b, 3
0x1400091a6  jnz     loc_140009379
0x1400091ac  mov     r9, r14
0x1400091af  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1400091b4  shr     r9, 2; unsigned __int64
0x1400091b8  lea     rcx, [rsp+280h+hObject]; this
0x1400091bd  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1400091c2  mov     esi, eax
0x1400091c4  test    eax, eax
0x1400091c6  jns     loc_140009264
0x1400091cc  mov     rcx, [rbp+188h]; this
0x1400091d3  mov     r9d, eax; char *
0x1400091d6  mov     edx, 14Eh; void *
0x1400091db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400091e0  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1400091e5  test    rcx, rcx
0x1400091e8  jz      short loc_1400091F8
0x1400091ea  call    cs:__imp_CloseHandle
0x1400091f0  test    eax, eax
0x1400091f2  jz      loc_14000937F
0x1400091f8  mov     rcx, [rsp+280h+hObject]; hObject
0x1400091fd  test    rcx, rcx
0x140009200  jz      short loc_140009210
0x140009202  call    cs:__imp_CloseHandle
0x140009208  test    eax, eax
0x14000920a  jz      loc_140009391
0x140009210  call    cs:__imp_GetProcessHeap
0x140009216  mov     r8, r14; lpMem
0x140009219  xor     edx, edx; dwFlags
0x14000921b  mov     rcx, rax; hHeap
0x14000921e  call    cs:__imp_HeapFree
0x140009224  mov     rcx, [rbp+188h]; this
0x14000922b  mov     r9d, esi; char *
0x14000922e  mov     edx, 137h; void *
0x140009233  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009238  test    rdi, rdi
0x14000923b  jz      short loc_14000924E
0x14000923d  mov     rcx, rdi; hMutex
0x140009240  call    cs:__imp_ReleaseMutex
0x140009246  test    eax, eax
0x140009248  jz      loc_1400093A3
0x14000924e  mov     rcx, rbx; hObject
0x140009251  call    cs:__imp_CloseHandle
0x140009257  test    eax, eax
0x140009259  jz      loc_140009336
0x14000925f  jmp     loc_140009138
0x140009264  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x140009269  lea     rcx, [r14+28h]; void *
0x14000926d  mov     dword ptr [r14], 1
0x140009274  xor     edx, edx; Val
0x140009276  mov     [r14+8], rbx
0x14000927a  mov     r8d, 108h; Size
0x140009280  movdqu  xmmword ptr [r14+10h], xmm0
0x140009286  call    memset_0
0x14000928b  xor     eax, eax
0x14000928d  lea     rcx, [r14+28h]; this
0x140009291  mov     [r14+20h], rax
0x140009295  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x14000929a  lea     rbx, [r14+0E8h]
0x1400092a1  xor     r8d, r8d; Flags
0x1400092a4  mov     rcx, rbx; lpCriticalSection
0x1400092a7  xor     edx, edx; dwSpinCount
0x1400092a9  call    cs:__imp_InitializeCriticalSectionEx
0x1400092af  mov     qword ptr [rbx+28h], 0
0x1400092b7  mov     qword ptr [rbx+30h], 0
0x1400092bf  mov     qword ptr [rbx+38h], 0
0x1400092c7  mov     qword ptr [rbx+40h], 0
0x1400092cf  xor     ebx, ebx
0x1400092d1  mov     [r15], r14
0x1400092d4  test    rdi, rdi
0x1400092d7  jz      short loc_1400092EA
0x1400092d9  mov     rcx, rdi; hMutex
0x1400092dc  call    cs:__imp_ReleaseMutex
0x1400092e2  test    eax, eax
0x1400092e4  jz      loc_1400093B5
0x1400092ea  test    rbx, rbx
0x1400092ed  jz      short loc_1400092FC
0x1400092ef  mov     rcx, rbx; hObject
0x1400092f2  call    cs:__imp_CloseHandle
0x1400092f8  test    eax, eax
0x1400092fa  jz      short loc_140009324
0x1400092fc  xor     eax, eax
0x1400092fe  mov     rcx, [rbp+180h+var_30]
0x140009305  xor     rcx, rsp; StackCookie
0x140009308  call    __security_check_cookie
0x14000930d  mov     rbx, [rsp+280h+arg_10]
0x140009315  add     rsp, 260h
0x14000931c  pop     r15
0x14000931e  pop     r14
0x140009320  pop     rdi
0x140009321  pop     rsi
0x140009322  pop     rbp
0x140009323  retn
0x140009324  mov     rcx, [rbp+188h]; this
0x14000932b  mov     edx, 0A0Bh; void *
0x140009330  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140009336  mov     rcx, [rbp+188h]; this
0x14000933d  mov     edx, 0A0Bh; void *
0x140009342  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140009348  mov     rcx, [rbp+188h]; this
0x14000934f  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140009355  mov     rcx, [rbp+188h]; this
0x14000935c  mov     edx, 0A15h; void *
0x140009361  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140009367  mov     rcx, [rbp+188h]; this
0x14000936e  mov     edx, 0A0Bh; void *
0x140009373  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140009379  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000937f  mov     rcx, [rbp+188h]; this
0x140009386  mov     edx, 0A0Bh; void *
0x14000938b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140009391  mov     rcx, [rbp+188h]; this
0x140009398  mov     edx, 0A0Bh; void *
0x14000939d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400093a3  mov     rcx, [rbp+188h]; this
0x1400093aa  mov     edx, 0A15h; void *
0x1400093af  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400093b5  mov     rcx, [rbp+188h]; this
0x1400093bc  mov     edx, 0A15h; void *
0x1400093c1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
