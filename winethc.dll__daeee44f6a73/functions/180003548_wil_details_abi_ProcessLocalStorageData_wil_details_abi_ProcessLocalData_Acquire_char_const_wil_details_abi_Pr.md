# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003548`
- end: `0x18000380d`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `709`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x180007d4c`

## callees

- `0x180003548`
- `0x180004800`
- `0x180005ad4`
- `0x18000a5c0`
- `0x18000c324`
- `0x18000caac`
- `0x18000cb58`
- `0x18000d7c4`
- `0x180012db0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000368f`
- `KERNEL32!CloseHandle` at `0x180003719`
- `KERNEL32!CloseHandle` at `0x18000375a`
- `KERNEL32!CloseHandle` at `0x18000368f`
- `KERNEL32!CloseHandle` at `0x180003719`
- `KERNEL32!CloseHandle` at `0x18000375a`
- `KERNEL32!ReleaseMutex` at `0x180003678`
- `KERNEL32!ReleaseMutex` at `0x1800036fb`
- `KERNEL32!ReleaseMutex` at `0x18000373e`
- `KERNEL32!ReleaseMutex` at `0x180003678`
- `KERNEL32!ReleaseMutex` at `0x1800036fb`
- `KERNEL32!ReleaseMutex` at `0x18000373e`
- `KERNEL32!WaitForSingleObjectEx` at `0x1800035f1`
- `KERNEL32!WaitForSingleObjectEx` at `0x1800035f1`
- `KERNEL32!GetCurrentProcessId` at `0x180003583`
- `KERNEL32!GetCurrentProcessId` at `0x180003583`
- `KERNEL32!CreateMutexExW` at `0x1800035c5`
- `KERNEL32!CreateMutexExW` at `0x1800035c5`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  HANDLE v6; // rbx
  DWORD v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  void *v12; // rdi
  int ValueInternal; // eax
  unsigned int v14; // r8d
  unsigned int v15; // esi
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // r8d
  const char *v21; // r9
  _DWORD *v22; // rcx
  int v23; // eax
  unsigned int v24; // r8d
  unsigned int v25; // ebx
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  int v34; // [rsp+20h] [rbp-E0h]
  int v35; // [rsp+20h] [rbp-E0h]
  HANDLE hObject; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v37; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  hObject = Mutex;
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
  v37 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, &v37, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v34);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v35);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v18, v19);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
    return v15;
  }
  v22 = (_DWORD *)(4 * v37);
  if ( 4 * v37 )
  {
    *a2 = v22;
    ++*v22;
    goto LABEL_21;
  }
  v23 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(
          Name,
          &hObject,
          a2);
  v25 = v23;
  if ( v23 >= 0 )
  {
    v6 = hObject;
LABEL_21:
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v30, v31);
    if ( v6 && !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v24, (const char *)(unsigned int)v23, 120);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v26, v27);
  if ( hObject && !CloseHandle(hObject) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
  return v25;
}

```

## disassembly

```asm
0x180003548  mov     [rsp-8+arg_10], rbx
0x18000354d  mov     [rsp-8+arg_18], rsi
0x180003552  push    rbp
0x180003553  push    rdi
0x180003554  push    r14
0x180003556  lea     rbp, [rsp-160h]
0x18000355e  sub     rsp, 260h
0x180003565  mov     rax, cs:__security_cookie
0x18000356c  xor     rax, rsp
0x18000356f  mov     [rbp+170h+var_20], rax
0x180003576  mov     r14, rdx
0x180003579  mov     qword ptr [rdx], 0
0x180003580  mov     rbx, rcx
0x180003583  call    cs:__imp_GetCurrentProcessId
0x18000358a  nop     dword ptr [rax+rax+00h]
0x18000358f  mov     [rsp+270h+var_248], rbx
0x180003594  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000359b  mov     r9d, eax
0x18000359e  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800035a6  mov     edx, 104h; unsigned __int64
0x1800035ab  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800035b0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800035b5  mov     r9d, 1F0001h; dwDesiredAccess
0x1800035bb  lea     rdx, [rsp+270h+Name]; lpName
0x1800035c0  xor     r8d, r8d; dwFlags
0x1800035c3  xor     ecx, ecx; lpMutexAttributes
0x1800035c5  call    cs:__imp_CreateMutexExW
0x1800035cc  nop     dword ptr [rax+rax+00h]
0x1800035d1  mov     [rsp+270h+hObject], rax
0x1800035d6  mov     rbx, rax
0x1800035d9  test    rax, rax
0x1800035dc  jnz     short loc_1800035E8
0x1800035de  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800035e3  jmp     loc_18000376C
0x1800035e8  xor     r8d, r8d; bAlertable
0x1800035eb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800035ee  mov     rcx, rbx; hHandle
0x1800035f1  call    cs:__imp_WaitForSingleObjectEx
0x1800035f8  nop     dword ptr [rax+rax+00h]
0x1800035fd  cmp     eax, 102h
0x180003602  jz      short loc_180003614
0x180003604  test    eax, 0FFFFFF7Fh
0x180003609  jnz     loc_1800037A6
0x18000360f  mov     rdi, rbx
0x180003612  jmp     short loc_180003616
0x180003614  xor     edi, edi
0x180003616  lea     r8, [rsp+270h+var_238]; unsigned __int64 *
0x18000361b  mov     [rsp+270h+var_238], 0
0x180003624  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180003629  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000362e  mov     esi, eax
0x180003630  test    eax, eax
0x180003632  jns     short loc_1800036AA
0x180003634  mov     rcx, [rbp+178h]; this
0x18000363b  mov     r9d, eax; char *
0x18000363e  mov     edx, 66h ; 'f'; void *
0x180003643  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003648  mov     rcx, [rbp+178h]; this
0x18000364f  mov     r9d, esi; char *
0x180003652  mov     edx, 6Fh ; 'o'; void *
0x180003657  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000365c  mov     rcx, [rbp+178h]; this
0x180003663  mov     r9d, esi; char *
0x180003666  mov     edx, 12Eh; void *
0x18000366b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003670  test    rdi, rdi
0x180003673  jz      short loc_18000368C
0x180003675  mov     rcx, rdi; hMutex
0x180003678  call    cs:__imp_ReleaseMutex
0x18000367f  nop     dword ptr [rax+rax+00h]
0x180003684  test    eax, eax
0x180003686  jz      loc_1800037B3
0x18000368c  mov     rcx, rbx; hObject
0x18000368f  call    cs:__imp_CloseHandle
0x180003696  nop     dword ptr [rax+rax+00h]
0x18000369b  test    eax, eax
0x18000369d  jz      loc_1800037C5
0x1800036a3  mov     eax, esi
0x1800036a5  jmp     loc_18000376C
0x1800036aa  mov     rax, [rsp+270h+var_238]
0x1800036af  lea     rcx, ds:0[rax*4]
0x1800036b7  test    rcx, rcx
0x1800036ba  jz      short loc_1800036C7
0x1800036bc  mov     [r14], rcx
0x1800036bf  mov     eax, [rcx]
0x1800036c1  inc     eax
0x1800036c3  mov     [rcx], eax
0x1800036c5  jmp     short loc_180003736
0x1800036c7  mov     r8, r14
0x1800036ca  lea     rdx, [rsp+270h+hObject]
0x1800036cf  lea     rcx, [rsp+270h+Name]
0x1800036d4  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800036d9  mov     ebx, eax
0x1800036db  test    eax, eax
0x1800036dd  jns     short loc_180003731
0x1800036df  mov     rcx, [rbp+178h]; this
0x1800036e6  mov     r9d, eax; char *
0x1800036e9  mov     edx, 137h; void *
0x1800036ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800036f3  test    rdi, rdi
0x1800036f6  jz      short loc_18000370F
0x1800036f8  mov     rcx, rdi; hMutex
0x1800036fb  call    cs:__imp_ReleaseMutex
0x180003702  nop     dword ptr [rax+rax+00h]
0x180003707  test    eax, eax
0x180003709  jz      loc_1800037D7
0x18000370f  mov     rcx, [rsp+270h+hObject]; hObject
0x180003714  test    rcx, rcx
0x180003717  jz      short loc_18000372D
0x180003719  call    cs:__imp_CloseHandle
0x180003720  nop     dword ptr [rax+rax+00h]
0x180003725  test    eax, eax
0x180003727  jz      loc_1800037E9
0x18000372d  mov     eax, ebx
0x18000372f  jmp     short loc_18000376C
0x180003731  mov     rbx, [rsp+270h+hObject]
0x180003736  test    rdi, rdi
0x180003739  jz      short loc_180003752
0x18000373b  mov     rcx, rdi; hMutex
0x18000373e  call    cs:__imp_ReleaseMutex
0x180003745  nop     dword ptr [rax+rax+00h]
0x18000374a  test    eax, eax
0x18000374c  jz      loc_1800037FB
0x180003752  test    rbx, rbx
0x180003755  jz      short loc_18000376A
0x180003757  mov     rcx, rbx; hObject
0x18000375a  call    cs:__imp_CloseHandle
0x180003761  nop     dword ptr [rax+rax+00h]
0x180003766  test    eax, eax
0x180003768  jz      short loc_180003794
0x18000376a  xor     eax, eax
0x18000376c  mov     rcx, [rbp+170h+var_20]
0x180003773  xor     rcx, rsp; StackCookie
0x180003776  call    __security_check_cookie
0x18000377b  lea     r11, [rsp+270h+var_10]
0x180003783  mov     rbx, [r11+30h]
0x180003787  mov     rsi, [r11+38h]
0x18000378b  mov     rsp, r11
0x18000378e  pop     r14
0x180003790  pop     rdi
0x180003791  pop     rbp
0x180003792  retn
0x180003794  mov     rcx, [rbp+178h]; this
0x18000379b  mov     edx, 0A0Bh; void *
0x1800037a0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800037a6  mov     rcx, [rbp+178h]; this
0x1800037ad  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800037b3  mov     rcx, [rbp+178h]; this
0x1800037ba  mov     edx, 0A15h; void *
0x1800037bf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800037c5  mov     rcx, [rbp+178h]; this
0x1800037cc  mov     edx, 0A0Bh; void *
0x1800037d1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800037d7  mov     rcx, [rbp+178h]; this
0x1800037de  mov     edx, 0A15h; void *
0x1800037e3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800037e9  mov     rcx, [rbp+178h]; this
0x1800037f0  mov     edx, 0A0Bh; void *
0x1800037f5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800037fb  mov     rcx, [rbp+178h]; this
0x180003802  mov     edx, 0A15h; void *
0x180003807  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
