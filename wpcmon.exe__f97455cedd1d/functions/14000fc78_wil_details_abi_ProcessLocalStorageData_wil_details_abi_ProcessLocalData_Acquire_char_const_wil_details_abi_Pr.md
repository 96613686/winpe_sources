# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x14000fc78`
- end: `0x140010045`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `973`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1400126fc`

## callees

- `0x140005530`
- `0x140006314`
- `0x14000fc78`
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

- `KERNEL32!CreateMutexExW` at `0x14000fcf0`
- `KERNEL32!CreateMutexExW` at `0x14000fcf0`
- `KERNEL32!GetCurrentProcessId` at `0x14000fcb1`
- `KERNEL32!GetCurrentProcessId` at `0x14000fcb1`
- `KERNEL32!GetProcessHeap` at `0x14000feae`
- `KERNEL32!GetProcessHeap` at `0x14000feae`
- `KERNEL32!CloseHandle` at `0x14000fdb8`
- `KERNEL32!CloseHandle` at `0x14000fe88`
- `KERNEL32!CloseHandle` at `0x14000fea0`
- `KERNEL32!CloseHandle` at `0x14000fef6`
- `KERNEL32!CloseHandle` at `0x14000ff6b`
- `KERNEL32!CloseHandle` at `0x14000fdb8`
- `KERNEL32!CloseHandle` at `0x14000fe88`
- `KERNEL32!CloseHandle` at `0x14000fea0`
- `KERNEL32!CloseHandle` at `0x14000fef6`
- `KERNEL32!CloseHandle` at `0x14000ff6b`
- `KERNEL32!WaitForSingleObjectEx` at `0x14000fd11`
- `KERNEL32!WaitForSingleObjectEx` at `0x14000fd11`
- `KERNEL32!ReleaseMutex` at `0x14000fda7`
- `KERNEL32!ReleaseMutex` at `0x14000fee5`
- `KERNEL32!ReleaseMutex` at `0x14000ff55`
- `KERNEL32!ReleaseMutex` at `0x14000fda7`
- `KERNEL32!ReleaseMutex` at `0x14000fee5`
- `KERNEL32!ReleaseMutex` at `0x14000ff55`
- `KERNEL32!HeapFree` at `0x14000febc`
- `KERNEL32!HeapFree` at `0x14000febc`

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
  _QWORD *v24; // rsi
  unsigned int v25; // r14d
  int v26; // eax
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  __int128 v36; // xmm0
  unsigned int v37; // r8d
  const char *v38; // r9
  unsigned int v39; // r8d
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
0x14000fc78  mov     [rsp-8+arg_10], rbx
0x14000fc7d  push    rbp
0x14000fc7e  push    rsi
0x14000fc7f  push    rdi
0x14000fc80  push    r14
0x14000fc82  push    r15
0x14000fc84  lea     rbp, [rsp-160h]
0x14000fc8c  sub     rsp, 260h
0x14000fc93  mov     rax, cs:__security_cookie
0x14000fc9a  xor     rax, rsp
0x14000fc9d  mov     [rbp+180h+var_30], rax
0x14000fca4  mov     r15, rdx
0x14000fca7  mov     qword ptr [rdx], 0
0x14000fcae  mov     rbx, rcx
0x14000fcb1  call    cs:__imp_GetCurrentProcessId
0x14000fcb7  mov     r14d, 78h ; 'x'
0x14000fcbd  mov     [rsp+280h+var_258], rbx
0x14000fcc2  mov     r9d, eax
0x14000fcc5  mov     [rsp+280h+var_260], r14d; int
0x14000fcca  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x14000fcd1  mov     edx, 104h; unsigned __int64
0x14000fcd6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000fcdb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000fce0  mov     r9d, 1F0001h; dwDesiredAccess
0x14000fce6  lea     rdx, [rsp+280h+Name]; lpName
0x14000fceb  xor     r8d, r8d; dwFlags
0x14000fcee  xor     ecx, ecx; lpMutexAttributes
0x14000fcf0  call    cs:__imp_CreateMutexExW
0x14000fcf6  mov     rbx, rax
0x14000fcf9  test    rax, rax
0x14000fcfc  jnz     short loc_14000FD08
0x14000fcfe  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000fd03  jmp     loc_14000FF77
0x14000fd08  xor     r8d, r8d; bAlertable
0x14000fd0b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000fd0e  mov     rcx, rbx; hHandle
0x14000fd11  call    cs:__imp_WaitForSingleObjectEx
0x14000fd17  cmp     eax, 102h
0x14000fd1c  jz      short loc_14000FD2E
0x14000fd1e  test    eax, 0FFFFFF7Fh
0x14000fd23  jnz     loc_14000FFAF
0x14000fd29  mov     rdi, rbx
0x14000fd2c  jmp     short loc_14000FD30
0x14000fd2e  xor     edi, edi
0x14000fd30  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x14000fd35  mov     [rsp+280h+hObject], 0
0x14000fd3e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000fd43  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x14000fd48  mov     esi, eax
0x14000fd4a  test    eax, eax
0x14000fd4c  jns     short loc_14000FDCD
0x14000fd4e  mov     rcx, [rbp+188h]; this
0x14000fd55  lea     r8, aWil; "wil"
0x14000fd5c  mov     r9d, eax; char *
0x14000fd5f  mov     edx, 66h ; 'f'; void *
0x14000fd64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000fd69  mov     rcx, [rbp+188h]; this
0x14000fd70  lea     r8, aWil; "wil"
0x14000fd77  mov     r9d, esi; char *
0x14000fd7a  mov     edx, 6Fh ; 'o'; void *
0x14000fd7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000fd84  mov     rcx, [rbp+188h]; this
0x14000fd8b  lea     r8, aWil; "wil"
0x14000fd92  mov     r9d, esi; char *
0x14000fd95  mov     edx, 12Eh; void *
0x14000fd9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000fd9f  test    rdi, rdi
0x14000fda2  jz      short loc_14000FDB5
0x14000fda4  mov     rcx, rdi; hMutex
0x14000fda7  call    cs:__imp_ReleaseMutex
0x14000fdad  test    eax, eax
0x14000fdaf  jz      loc_14000FFC1
0x14000fdb5  mov     rcx, rbx; hObject
0x14000fdb8  call    cs:__imp_CloseHandle
0x14000fdbe  test    eax, eax
0x14000fdc0  jz      loc_14000FFD3
0x14000fdc6  mov     eax, esi
0x14000fdc8  jmp     loc_14000FF77
0x14000fdcd  mov     rax, [rsp+280h+hObject]
0x14000fdd2  lea     rcx, ds:0[rax*4]
0x14000fdda  test    rcx, rcx
0x14000fddd  jz      short loc_14000FDED
0x14000fddf  mov     [r15], rcx
0x14000fde2  mov     eax, [rcx]
0x14000fde4  inc     eax
0x14000fde6  mov     [rcx], eax
0x14000fde8  jmp     loc_14000FF4D
0x14000fded  mov     rdx, r14; dwBytes
0x14000fdf0  mov     qword ptr [r15], 0
0x14000fdf7  mov     ecx, 8; dwFlags
0x14000fdfc  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000fe01  mov     rsi, rax
0x14000fe04  test    rax, rax
0x14000fe07  jnz     short loc_14000FE2F
0x14000fe09  mov     rcx, [rbp+188h]; this
0x14000fe10  lea     r8, aWil; "wil"
0x14000fe17  mov     r14d, 8007000Eh
0x14000fe1d  mov     edx, 14Bh; void *
0x14000fe22  mov     r9d, r14d; char *
0x14000fe25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000fe2a  jmp     loc_14000FEC2
0x14000fe2f  xorps   xmm0, xmm0
0x14000fe32  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x14000fe38  test    sil, 3
0x14000fe3c  jnz     loc_14000FFE5
0x14000fe42  mov     r9, rsi
0x14000fe45  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x14000fe4a  shr     r9, 2; unsigned __int64
0x14000fe4e  lea     rcx, [rsp+280h+hObject]; this
0x14000fe53  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x14000fe58  mov     r14d, eax
0x14000fe5b  test    eax, eax
0x14000fe5d  jns     loc_14000FF09
0x14000fe63  mov     rcx, [rbp+188h]; this
0x14000fe6a  lea     r8, aWil; "wil"
0x14000fe71  mov     r9d, eax; char *
0x14000fe74  mov     edx, 14Eh; void *
0x14000fe79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000fe7e  mov     rcx, [rsp+280h+hObject+8]; hObject
0x14000fe83  test    rcx, rcx
0x14000fe86  jz      short loc_14000FE96
0x14000fe88  call    cs:__imp_CloseHandle
0x14000fe8e  test    eax, eax
0x14000fe90  jz      loc_14000FFEB
0x14000fe96  mov     rcx, [rsp+280h+hObject]; hObject
0x14000fe9b  test    rcx, rcx
0x14000fe9e  jz      short loc_14000FEAE
0x14000fea0  call    cs:__imp_CloseHandle
0x14000fea6  test    eax, eax
0x14000fea8  jz      loc_14000FFFD
0x14000feae  call    cs:__imp_GetProcessHeap
0x14000feb4  mov     r8, rsi; lpMem
0x14000feb7  xor     edx, edx; dwFlags
0x14000feb9  mov     rcx, rax; hHeap
0x14000febc  call    cs:__imp_HeapFree
0x14000fec2  mov     rcx, [rbp+188h]; this
0x14000fec9  lea     r8, aWil; "wil"
0x14000fed0  mov     r9d, r14d; char *
0x14000fed3  mov     edx, 137h; void *
0x14000fed8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000fedd  test    rdi, rdi
0x14000fee0  jz      short loc_14000FEF3
0x14000fee2  mov     rcx, rdi; hMutex
0x14000fee5  call    cs:__imp_ReleaseMutex
0x14000feeb  test    eax, eax
0x14000feed  jz      loc_14001000F
0x14000fef3  mov     rcx, rbx; hObject
0x14000fef6  call    cs:__imp_CloseHandle
0x14000fefc  test    eax, eax
0x14000fefe  jz      loc_140010021
0x14000ff04  mov     eax, r14d
0x14000ff07  jmp     short loc_14000FF77
0x14000ff09  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x14000ff0e  xor     edx, edx; Val
0x14000ff10  mov     dword ptr [rsi], 1
0x14000ff16  lea     rcx, [rsi+22h]; void *
0x14000ff1a  mov     [rsi+8], rbx
0x14000ff1e  movdqu  xmmword ptr [rsi+10h], xmm0
0x14000ff23  lea     r8d, [rdx+56h]; Size
0x14000ff27  call    memset_0
0x14000ff2c  xor     edx, edx; Val
0x14000ff2e  mov     word ptr [rsi+20h], 58h ; 'X'
0x14000ff34  lea     rcx, [rsi+28h]; void *
0x14000ff38  mov     dword ptr [rsi+24h], 1
0x14000ff3f  lea     r8d, [rdx+50h]; Size
0x14000ff43  call    memset_0
0x14000ff48  xor     ebx, ebx
0x14000ff4a  mov     [r15], rsi
0x14000ff4d  test    rdi, rdi
0x14000ff50  jz      short loc_14000FF63
0x14000ff52  mov     rcx, rdi; hMutex
0x14000ff55  call    cs:__imp_ReleaseMutex
0x14000ff5b  test    eax, eax
0x14000ff5d  jz      loc_140010033
0x14000ff63  test    rbx, rbx
0x14000ff66  jz      short loc_14000FF75
0x14000ff68  mov     rcx, rbx; hObject
0x14000ff6b  call    cs:__imp_CloseHandle
0x14000ff71  test    eax, eax
0x14000ff73  jz      short loc_14000FF9D
0x14000ff75  xor     eax, eax
0x14000ff77  mov     rcx, [rbp+180h+var_30]
0x14000ff7e  xor     rcx, rsp; StackCookie
0x14000ff81  call    __security_check_cookie
0x14000ff86  mov     rbx, [rsp+280h+arg_10]
0x14000ff8e  add     rsp, 260h
0x14000ff95  pop     r15
0x14000ff97  pop     r14
0x14000ff99  pop     rdi
0x14000ff9a  pop     rsi
0x14000ff9b  pop     rbp
0x14000ff9c  retn
0x14000ff9d  mov     rcx, [rbp+188h]; this
0x14000ffa4  mov     edx, 0A0Bh; void *
0x14000ffa9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000ffaf  mov     rcx, [rbp+188h]; this
0x14000ffb6  mov     edx, 0E01h; void *
0x14000ffbb  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x14000ffc1  mov     rcx, [rbp+188h]; this
0x14000ffc8  mov     edx, 0A15h; void *
0x14000ffcd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000ffd3  mov     rcx, [rbp+188h]; this
0x14000ffda  mov     edx, 0A0Bh; void *
0x14000ffdf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000ffe5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000ffeb  mov     rcx, [rbp+188h]; this
0x14000fff2  mov     edx, 0A0Bh; void *
0x14000fff7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000fffd  mov     rcx, [rbp+188h]; this
0x140010004  mov     edx, 0A0Bh; void *
0x140010009  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14001000f  mov     rcx, [rbp+188h]; this
0x140010016  mov     edx, 0A15h; void *
0x14001001b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140010021  mov     rcx, [rbp+188h]; this
0x140010028  mov     edx, 0A0Bh; void *
0x14001002d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140010033  mov     rcx, [rbp+188h]; this
0x14001003a  mov     edx, 0A15h; void *
0x14001003f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
