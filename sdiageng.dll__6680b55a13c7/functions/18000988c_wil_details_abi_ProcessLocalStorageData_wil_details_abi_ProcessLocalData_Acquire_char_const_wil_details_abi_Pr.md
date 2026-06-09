# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000988c`
- end: `0x180009c2a`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18000c690`

## callees

- `0x180002978`
- `0x18000988c`
- `0x18000aa8c`
- `0x18000b2dc`
- `0x18000bd6c`
- `0x18000e5e4`
- `0x18000ffb4`
- `0x1800111dc`
- `0x1800125a4`
- `0x1800125b4`
- `0x180029882`
- `0x1800298c0`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180009a9f`
- `KERNEL32!GetProcessHeap` at `0x180009a9f`
- `KERNEL32!HeapFree` at `0x180009aad`
- `KERNEL32!HeapFree` at `0x180009aad`
- `KERNEL32!CloseHandle` at `0x1800099b7`
- `KERNEL32!CloseHandle` at `0x180009a79`
- `KERNEL32!CloseHandle` at `0x180009a91`
- `KERNEL32!CloseHandle` at `0x180009ae0`
- `KERNEL32!CloseHandle` at `0x180009b55`
- `KERNEL32!CloseHandle` at `0x1800099b7`
- `KERNEL32!CloseHandle` at `0x180009a79`
- `KERNEL32!CloseHandle` at `0x180009a91`
- `KERNEL32!CloseHandle` at `0x180009ae0`
- `KERNEL32!CloseHandle` at `0x180009b55`
- `KERNEL32!ReleaseMutex` at `0x1800099a6`
- `KERNEL32!ReleaseMutex` at `0x180009acf`
- `KERNEL32!ReleaseMutex` at `0x180009b3f`
- `KERNEL32!ReleaseMutex` at `0x1800099a6`
- `KERNEL32!ReleaseMutex` at `0x180009acf`
- `KERNEL32!ReleaseMutex` at `0x180009b3f`
- `KERNEL32!WaitForSingleObjectEx` at `0x180009925`
- `KERNEL32!WaitForSingleObjectEx` at `0x180009925`
- `KERNEL32!GetCurrentProcessId` at `0x1800098c5`
- `KERNEL32!GetCurrentProcessId` at `0x1800098c5`
- `KERNEL32!CreateMutexExW` at `0x180009904`
- `KERNEL32!CreateMutexExW` at `0x180009904`

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
0x18000988c  mov     [rsp-8+arg_10], rbx
0x180009891  push    rbp
0x180009892  push    rsi
0x180009893  push    rdi
0x180009894  push    r14
0x180009896  push    r15
0x180009898  lea     rbp, [rsp-160h]
0x1800098a0  sub     rsp, 260h
0x1800098a7  mov     rax, cs:__security_cookie
0x1800098ae  xor     rax, rsp
0x1800098b1  mov     [rbp+180h+var_30], rax
0x1800098b8  mov     r15, rdx
0x1800098bb  mov     qword ptr [rdx], 0
0x1800098c2  mov     rbx, rcx
0x1800098c5  call    cs:__imp_GetCurrentProcessId
0x1800098cb  mov     r14d, 78h ; 'x'
0x1800098d1  mov     [rsp+280h+var_258], rbx
0x1800098d6  mov     r9d, eax
0x1800098d9  mov     [rsp+280h+var_260], r14d; int
0x1800098de  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800098e5  mov     edx, 104h; unsigned __int64
0x1800098ea  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800098ef  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800098f4  mov     r9d, 1F0001h; dwDesiredAccess
0x1800098fa  lea     rdx, [rsp+280h+Name]; lpName
0x1800098ff  xor     r8d, r8d; dwFlags
0x180009902  xor     ecx, ecx; lpMutexAttributes
0x180009904  call    cs:__imp_CreateMutexExW
0x18000990a  mov     rbx, rax
0x18000990d  test    rax, rax
0x180009910  jnz     short loc_18000991C
0x180009912  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009917  jmp     loc_180009B61
0x18000991c  xor     r8d, r8d; bAlertable
0x18000991f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180009922  mov     rcx, rbx; hHandle
0x180009925  call    cs:__imp_WaitForSingleObjectEx
0x18000992b  cmp     eax, 102h
0x180009930  jz      short loc_180009942
0x180009932  test    eax, 0FFFFFF7Fh
0x180009937  jnz     loc_180009B99
0x18000993d  mov     rdi, rbx
0x180009940  jmp     short loc_180009944
0x180009942  xor     edi, edi
0x180009944  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180009949  mov     [rsp+280h+hObject], 0
0x180009952  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180009957  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000995c  mov     esi, eax
0x18000995e  test    eax, eax
0x180009960  jns     short loc_1800099CC
0x180009962  mov     rcx, [rbp+188h]; this
0x180009969  mov     r9d, eax; char *
0x18000996c  mov     edx, 66h ; 'f'; void *
0x180009971  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009976  mov     rcx, [rbp+188h]; this
0x18000997d  mov     r9d, esi; char *
0x180009980  mov     edx, 6Fh ; 'o'; void *
0x180009985  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000998a  mov     rcx, [rbp+188h]; this
0x180009991  mov     r9d, esi; char *
0x180009994  mov     edx, 12Eh; void *
0x180009999  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000999e  test    rdi, rdi
0x1800099a1  jz      short loc_1800099B4
0x1800099a3  mov     rcx, rdi; hMutex
0x1800099a6  call    cs:__imp_ReleaseMutex
0x1800099ac  test    eax, eax
0x1800099ae  jz      loc_180009BA6
0x1800099b4  mov     rcx, rbx; hObject
0x1800099b7  call    cs:__imp_CloseHandle
0x1800099bd  test    eax, eax
0x1800099bf  jz      loc_180009BB8
0x1800099c5  mov     eax, esi
0x1800099c7  jmp     loc_180009B61
0x1800099cc  mov     rax, [rsp+280h+hObject]
0x1800099d1  lea     rcx, ds:0[rax*4]
0x1800099d9  test    rcx, rcx
0x1800099dc  jz      short loc_1800099EC
0x1800099de  mov     [r15], rcx
0x1800099e1  mov     eax, [rcx]
0x1800099e3  inc     eax
0x1800099e5  mov     [rcx], eax
0x1800099e7  jmp     loc_180009B37
0x1800099ec  mov     rdx, r14; dwBytes
0x1800099ef  mov     qword ptr [r15], 0
0x1800099f6  mov     ecx, 8; dwFlags
0x1800099fb  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009a00  mov     rsi, rax
0x180009a03  test    rax, rax
0x180009a06  jnz     short loc_180009A27
0x180009a08  mov     rcx, [rbp+188h]; this
0x180009a0f  mov     r14d, 8007000Eh
0x180009a15  mov     r9d, r14d; char *
0x180009a18  mov     edx, 14Bh; void *
0x180009a1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009a22  jmp     loc_180009AB3
0x180009a27  xorps   xmm0, xmm0
0x180009a2a  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180009a30  test    sil, 3
0x180009a34  jnz     loc_180009BCA
0x180009a3a  mov     r9, rsi
0x180009a3d  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180009a42  shr     r9, 2; unsigned __int64
0x180009a46  lea     rcx, [rsp+280h+hObject]; this
0x180009a4b  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180009a50  mov     r14d, eax
0x180009a53  test    eax, eax
0x180009a55  jns     loc_180009AF3
0x180009a5b  mov     rcx, [rbp+188h]; this
0x180009a62  mov     r9d, eax; char *
0x180009a65  mov     edx, 14Eh; void *
0x180009a6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009a6f  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180009a74  test    rcx, rcx
0x180009a77  jz      short loc_180009A87
0x180009a79  call    cs:__imp_CloseHandle
0x180009a7f  test    eax, eax
0x180009a81  jz      loc_180009BD0
0x180009a87  mov     rcx, [rsp+280h+hObject]; hObject
0x180009a8c  test    rcx, rcx
0x180009a8f  jz      short loc_180009A9F
0x180009a91  call    cs:__imp_CloseHandle
0x180009a97  test    eax, eax
0x180009a99  jz      loc_180009BE2
0x180009a9f  call    cs:__imp_GetProcessHeap
0x180009aa5  mov     r8, rsi; lpMem
0x180009aa8  xor     edx, edx; dwFlags
0x180009aaa  mov     rcx, rax; hHeap
0x180009aad  call    cs:__imp_HeapFree
0x180009ab3  mov     rcx, [rbp+188h]; this
0x180009aba  mov     r9d, r14d; char *
0x180009abd  mov     edx, 137h; void *
0x180009ac2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009ac7  test    rdi, rdi
0x180009aca  jz      short loc_180009ADD
0x180009acc  mov     rcx, rdi; hMutex
0x180009acf  call    cs:__imp_ReleaseMutex
0x180009ad5  test    eax, eax
0x180009ad7  jz      loc_180009BF4
0x180009add  mov     rcx, rbx; hObject
0x180009ae0  call    cs:__imp_CloseHandle
0x180009ae6  test    eax, eax
0x180009ae8  jz      loc_180009C06
0x180009aee  mov     eax, r14d
0x180009af1  jmp     short loc_180009B61
0x180009af3  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180009af8  xor     edx, edx; Val
0x180009afa  mov     dword ptr [rsi], 1
0x180009b00  lea     rcx, [rsi+22h]; void *
0x180009b04  mov     [rsi+8], rbx
0x180009b08  movdqu  xmmword ptr [rsi+10h], xmm0
0x180009b0d  lea     r8d, [rdx+56h]; Size
0x180009b11  call    memset_0
0x180009b16  xor     edx, edx; Val
0x180009b18  mov     word ptr [rsi+20h], 58h ; 'X'
0x180009b1e  lea     rcx, [rsi+28h]; void *
0x180009b22  mov     dword ptr [rsi+24h], 1
0x180009b29  lea     r8d, [rdx+50h]; Size
0x180009b2d  call    memset_0
0x180009b32  xor     ebx, ebx
0x180009b34  mov     [r15], rsi
0x180009b37  test    rdi, rdi
0x180009b3a  jz      short loc_180009B4D
0x180009b3c  mov     rcx, rdi; hMutex
0x180009b3f  call    cs:__imp_ReleaseMutex
0x180009b45  test    eax, eax
0x180009b47  jz      loc_180009C18
0x180009b4d  test    rbx, rbx
0x180009b50  jz      short loc_180009B5F
0x180009b52  mov     rcx, rbx; hObject
0x180009b55  call    cs:__imp_CloseHandle
0x180009b5b  test    eax, eax
0x180009b5d  jz      short loc_180009B87
0x180009b5f  xor     eax, eax
0x180009b61  mov     rcx, [rbp+180h+var_30]
0x180009b68  xor     rcx, rsp; StackCookie
0x180009b6b  call    __security_check_cookie
0x180009b70  mov     rbx, [rsp+280h+arg_10]
0x180009b78  add     rsp, 260h
0x180009b7f  pop     r15
0x180009b81  pop     r14
0x180009b83  pop     rdi
0x180009b84  pop     rsi
0x180009b85  pop     rbp
0x180009b86  retn
0x180009b87  mov     rcx, [rbp+188h]; this
0x180009b8e  mov     edx, 0A0Bh; void *
0x180009b93  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009b99  mov     rcx, [rbp+188h]; this
0x180009ba0  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180009ba6  mov     rcx, [rbp+188h]; this
0x180009bad  mov     edx, 0A15h; void *
0x180009bb2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009bb8  mov     rcx, [rbp+188h]; this
0x180009bbf  mov     edx, 0A0Bh; void *
0x180009bc4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009bca  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180009bd0  mov     rcx, [rbp+188h]; this
0x180009bd7  mov     edx, 0A0Bh; void *
0x180009bdc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009be2  mov     rcx, [rbp+188h]; this
0x180009be9  mov     edx, 0A0Bh; void *
0x180009bee  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009bf4  mov     rcx, [rbp+188h]; this
0x180009bfb  mov     edx, 0A15h; void *
0x180009c00  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009c06  mov     rcx, [rbp+188h]; this
0x180009c0d  mov     edx, 0A0Bh; void *
0x180009c12  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009c18  mov     rcx, [rbp+188h]; this
0x180009c1f  mov     edx, 0A15h; void *
0x180009c24  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
