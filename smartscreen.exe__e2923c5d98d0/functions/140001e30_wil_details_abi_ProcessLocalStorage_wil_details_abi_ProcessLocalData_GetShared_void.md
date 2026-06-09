# wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData>::GetShared(void)

- ea: `0x140001e30`
- end: `0x140002332`
- name: `?GetShared@?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUProcessLocalData@23@XZ`
- size: `1282`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140001d9c`

## callees

- `0x140001864`
- `0x140001ac4`
- `0x140001e30`
- `0x140002338`
- `0x1400030a8`
- `0x1400047dc`
- `0x140010c7c`
- `0x140016ce4`
- `0x140016d08`
- `0x140016da0`
- `0x140025aa0`
- `0x14002deb0`
- `0x14002e5d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140001eed`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140001eed`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140001fd0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400021b6`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140001fd0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400021b6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140001f29`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140001f29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001fe4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001fe4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140001ea9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140001ea9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002017`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002017`

## pseudocode

```c
__int64 wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData>::GetShared()
{
  __int64 v0; // rsi
  __int64 v1; // rdx
  __int64 result; // rax
  _DWORD *v3; // rdi
  DWORD CurrentProcessId; // eax
  wil::details *Mutex; // rax
  wil::details *v6; // rcx
  wil::details *v7; // rbx
  int LastErrorFailHr; // ebx
  DWORD v9; // eax
  void *v10; // rdx
  unsigned int v11; // r8d
  const char *v12; // r9
  wil::details *v13; // r15
  __int64 v14; // r13
  WCHAR *v15; // rdx
  __int64 v16; // rcx
  WCHAR *v17; // r9
  unsigned __int64 v18; // r12
  __int64 v19; // r8
  __int64 v20; // rcx
  WCHAR *v21; // rax
  __int64 v22; // rdx
  HANDLE v23; // rax
  void *v24; // rdx
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int LastError; // edi
  void *v30; // rdx
  const wchar_t *v31; // r9
  bool v32; // zf
  __int64 v33; // r8
  __int64 v34; // rcx
  WCHAR *v35; // rdx
  int v36; // eax
  int ValueFromSemaphore; // eax
  __int64 v38; // rcx
  WCHAR *v39; // rax
  __int64 v40; // rdx
  WCHAR *v41; // rcx
  const wchar_t *v42; // rax
  __int64 v43; // r14
  HANDLE v44; // rax
  unsigned int v45; // r8d
  const char *v46; // r9
  void *v47; // rdx
  int v48; // eax
  int v49; // [rsp+20h] [rbp-E0h]
  int v50; // [rsp+20h] [rbp-E0h]
  int v51; // [rsp+20h] [rbp-E0h]
  int v52; // [rsp+30h] [rbp-D0h] BYREF
  int v53; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v54; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v55; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE v56; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD *v57; // [rsp+50h] [rbp-B0h]
  WCHAR v58[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Name[264]; // [rsp+270h] [rbp+170h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4D8h] [rbp+3D8h]

  v0 = wil::details_abi::g_pProcessLocalData;
  if ( *(_QWORD *)(wil::details_abi::g_pProcessLocalData + 8) )
    goto LABEL_2;
  v3 = 0;
  v57 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v49 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v55 = Mutex;
  v7 = Mutex;
  if ( !Mutex )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v6);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v55);
    if ( LastErrorFailHr < 0 )
      goto LABEL_2;
    goto LABEL_28;
  }
  v9 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v9 == 258 )
  {
    v13 = 0;
  }
  else
  {
    if ( (v9 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v10, v11, v12);
    v13 = v7;
  }
  v14 = 2147483646;
  v15 = Name;
  v16 = 2147483646;
  v17 = v58;
  v18 = 0;
  v19 = 260;
  while ( v16 && *v15 )
  {
    *v17++ = *v15++;
    --v16;
    if ( !--v19 )
    {
      --v17;
      break;
    }
  }
  v20 = 260;
  *v17 = 0;
  v21 = v58;
  do
  {
    if ( !*v21 )
      break;
    ++v21;
    --v20;
  }
  while ( v20 );
  v22 = 260 - v20;
  if ( v20 )
  {
    v31 = L"_p0";
    v33 = v20;
    v32 = v22 == 260;
    v34 = 2147483646;
    v35 = &v58[v22];
    if ( v32 )
    {
LABEL_36:
      --v35;
    }
    else
    {
      while ( v34 && *v31 )
      {
        *v35++ = *v31++;
        --v34;
        if ( !--v33 )
          goto LABEL_36;
      }
    }
    *v35 = 0;
  }
  v23 = OpenSemaphoreW(0x1F0003u, 0, v58);
  v54 = v23;
  if ( v23 )
  {
    v53 = 0;
    v52 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v23, &v53);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v54);
      goto LABEL_32;
    }
    v38 = 260;
    v39 = v58;
    do
    {
      if ( !*v39 )
        break;
      ++v39;
      --v38;
    }
    while ( v38 );
    v40 = 260 - v38;
    if ( v38 )
    {
      v41 = &v58[v40];
      v42 = L"h";
      v43 = 260 - v40;
      if ( 260 == v40 )
      {
LABEL_50:
        --v41;
      }
      else
      {
        while ( v14 )
        {
          if ( !*v42 )
          {
            if ( v43 )
              break;
            goto LABEL_50;
          }
          *v41++ = *v42++;
          --v14;
          if ( !--v43 )
            goto LABEL_50;
        }
      }
      *v41 = 0;
    }
    v44 = OpenSemaphoreW(0x1F0003u, 0, v58);
    v56 = v44;
    if ( v44 )
    {
      v48 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v44, &v52);
      LastError = v48;
      if ( v48 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v56);
        v18 = v53 | (unsigned __int64)((__int64)v52 << 31);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v54);
        goto LABEL_22;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v48,
        120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v56);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v54);
      goto LABEL_32;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v45, v46);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v56);
LABEL_31:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v54);
    if ( (LastError & 0x80000000) == 0 )
      goto LABEL_22;
LABEL_32:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, (unsigned int)"wil", (const char *)LastError, v49);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)LastError, v50);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)LastError, v51);
    if ( v13 )
      wil::details::ReleaseMutex(v13, v30);
    wil::details::CloseHandle(v7, v30);
    goto LABEL_2;
  }
  if ( GetLastError() != 2 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v25, v26);
    goto LABEL_31;
  }
LABEL_22:
  v3 = (_DWORD *)(4 * v18);
  if ( 4 * v18 )
  {
    ++*v3;
LABEL_24:
    if ( v13 )
      wil::details::ReleaseMutex(v13, v24);
    if ( v7 && !CloseHandle(v7) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
LABEL_28:
    if ( !*(_QWORD *)(v0 + 8) )
      *(_QWORD *)(v0 + 8) = v3;
    goto LABEL_2;
  }
  v36 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
  if ( v36 >= 0 )
  {
    v3 = v57;
    v7 = v55;
    goto LABEL_24;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)(unsigned int)v36, 120);
  if ( v13 )
    wil::details::ReleaseMutex(v13, v47);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v55);
LABEL_2:
  v1 = *(_QWORD *)(v0 + 8);
  result = v1 + 32;
  if ( !v1 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x140001e30  push    rbp
0x140001e32  push    rbx
0x140001e33  push    rsi
0x140001e34  push    rdi
0x140001e35  push    r12
0x140001e37  push    r13
0x140001e39  push    r14
0x140001e3b  push    r15
0x140001e3d  lea     rbp, [rsp-398h]
0x140001e45  sub     rsp, 498h
0x140001e4c  mov     rax, cs:__security_cookie
0x140001e53  xor     rax, rsp
0x140001e56  mov     [rbp+3D0h+var_50], rax
0x140001e5d  mov     rsi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140001e64  cmp     qword ptr [rsi+8], 0
0x140001e69  jz      short loc_140001E9F
0x140001e6b  mov     rdx, [rsi+8]
0x140001e6f  xor     ecx, ecx
0x140001e71  test    rdx, rdx
0x140001e74  lea     rax, [rdx+20h]
0x140001e78  cmovz   rax, rcx
0x140001e7c  mov     rcx, [rbp+3D0h+var_50]
0x140001e83  xor     rcx, rsp; StackCookie
0x140001e86  call    __security_check_cookie
0x140001e8b  add     rsp, 498h
0x140001e92  pop     r15
0x140001e94  pop     r14
0x140001e96  pop     r13
0x140001e98  pop     r12
0x140001e9a  pop     rdi
0x140001e9b  pop     rsi
0x140001e9c  pop     rbx
0x140001e9d  pop     rbp
0x140001e9e  retn
0x140001e9f  mov     rbx, [rsi]
0x140001ea2  xor     edi, edi
0x140001ea4  mov     [rsp+4D0h+var_480], rdi
0x140001ea9  call    cs:__imp_GetCurrentProcessId
0x140001eaf  mov     r14d, 104h
0x140001eb5  mov     [rsp+4D0h+var_4A8], rbx
0x140001eba  mov     r9d, eax
0x140001ebd  mov     [rsp+4D0h+var_4B0], 78h ; 'x'; int
0x140001ec5  mov     edx, r14d; unsigned __int64
0x140001ec8  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140001ecf  lea     rcx, [rbp+3D0h+Name]; Buffer
0x140001ed6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140001edb  mov     r9d, 1F0001h; dwDesiredAccess
0x140001ee1  lea     rdx, [rbp+3D0h+Name]; lpName
0x140001ee8  xor     r8d, r8d; dwFlags
0x140001eeb  xor     ecx, ecx; lpMutexAttributes
0x140001eed  call    cs:__imp_CreateMutexExW
0x140001ef3  mov     [rsp+4D0h+var_490], rax
0x140001ef8  mov     rbx, rax
0x140001efb  test    rax, rax
0x140001efe  jnz     short loc_140001F1E
0x140001f00  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140001f05  lea     rcx, [rsp+4D0h+var_490]
0x140001f0a  mov     ebx, eax
0x140001f0c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140001f11  test    ebx, ebx
0x140001f13  js      loc_140001E6B
0x140001f19  jmp     loc_140002025
0x140001f1e  xor     r8d, r8d; bAlertable
0x140001f21  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x140001f26  mov     rcx, rbx; hHandle
0x140001f29  call    cs:__imp_WaitForSingleObjectEx
0x140001f2f  cmp     eax, 102h
0x140001f34  jz      loc_140002256
0x140001f3a  test    eax, 0FFFFFF7Fh
0x140001f3f  jnz     loc_140002249
0x140001f45  mov     r15, rbx
0x140001f48  mov     r13d, 7FFFFFFEh
0x140001f4e  lea     rdx, [rbp+3D0h+Name]
0x140001f55  mov     ecx, r13d
0x140001f58  lea     r9, [rsp+4D0h+var_470]
0x140001f5d  xor     r12d, r12d
0x140001f60  mov     r8, r14
0x140001f63  test    rcx, rcx
0x140001f66  jz      short loc_140001F90
0x140001f68  movzx   eax, word ptr [rdx]
0x140001f6b  test    ax, ax
0x140001f6e  jz      short loc_140001F8B
0x140001f70  mov     [r9], ax
0x140001f74  add     rdx, 2
0x140001f78  add     r9, 2
0x140001f7c  dec     rcx
0x140001f7f  sub     r8, 1
0x140001f83  jnz     short loc_140001F63
0x140001f85  sub     r9, 2
0x140001f89  jmp     short loc_140001F90
0x140001f8b  test    r8, r8
0x140001f8e  jz      short loc_140001F85
0x140001f90  xor     eax, eax
0x140001f92  mov     rcx, r14
0x140001f95  mov     [r9], ax
0x140001f99  lea     rax, [rsp+4D0h+var_470]
0x140001f9e  xchg    ax, ax
0x140001fa0  cmp     [rax], di
0x140001fa3  jz      short loc_140001FAF
0x140001fa5  add     rax, 2
0x140001fa9  sub     rcx, 1
0x140001fad  jnz     short loc_140001FA0
0x140001faf  xor     eax, eax
0x140001fb1  mov     rdx, r14
0x140001fb4  sub     rdx, rcx
0x140001fb7  test    rcx, rcx
0x140001fba  cmovz   rdx, rax
0x140001fbe  jnz     loc_1400020C1
0x140001fc4  lea     r8, [rsp+4D0h+var_470]; lpName
0x140001fc9  xor     edx, edx; bInheritHandle
0x140001fcb  mov     ecx, 1F0003h; dwDesiredAccess
0x140001fd0  call    cs:__imp_OpenSemaphoreW
0x140001fd6  mov     [rsp+4D0h+var_498], rax
0x140001fdb  test    rax, rax
0x140001fde  jnz     loc_140002144
0x140001fe4  call    cs:__imp_GetLastError
0x140001fea  cmp     eax, 2
0x140001fed  jnz     short loc_140002039
0x140001fef  lea     rdi, ds:0[r12*4]
0x140001ff7  test    rdi, rdi
0x140001ffa  jz      loc_1400020ED
0x140002000  mov     eax, [rdi]
0x140002002  inc     eax
0x140002004  mov     [rdi], eax
0x140002006  test    r15, r15
0x140002009  jnz     loc_140002313
0x14000200f  test    rbx, rbx
0x140002012  jz      short loc_140002025
0x140002014  mov     rcx, rbx; hObject
0x140002017  call    cs:__imp_CloseHandle
0x14000201d  test    eax, eax
0x14000201f  jz      loc_140002320
0x140002025  cmp     qword ptr [rsi+8], 0
0x14000202a  jnz     loc_140001E6B
0x140002030  mov     [rsi+8], rdi
0x140002034  jmp     loc_140001E6B
0x140002039  mov     rcx, [rbp+3D8h]; this
0x140002040  mov     edx, 0D0h; void *
0x140002045  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000204a  mov     edi, eax
0x14000204c  lea     rcx, [rsp+4D0h+var_498]
0x140002051  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140002056  test    edi, edi
0x140002058  jns     short loc_140001FEF
0x14000205a  mov     rcx, [rbp+3D8h]; this
0x140002061  lea     r8, aWil; "wil"
0x140002068  mov     r9d, edi; char *
0x14000206b  mov     edx, 66h ; 'f'; void *
0x140002070  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002075  mov     rcx, [rbp+3D8h]; this
0x14000207c  lea     r8, aWil; "wil"
0x140002083  mov     r9d, edi; char *
0x140002086  mov     edx, 6Fh ; 'o'; void *
0x14000208b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002090  mov     rcx, [rbp+3D8h]; this
0x140002097  lea     r8, aWil; "wil"
0x14000209e  mov     r9d, edi; char *
0x1400020a1  mov     edx, 12Eh; void *
0x1400020a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400020ab  test    r15, r15
0x1400020ae  jnz     loc_1400022F9
0x1400020b4  mov     rcx, rbx; this
0x1400020b7  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1400020bc  jmp     loc_140001E6B
0x1400020c1  mov     r8, r14
0x1400020c4  lea     r9, aP0; "_p0"
0x1400020cb  sub     r8, rdx
0x1400020ce  mov     rcx, r13
0x1400020d1  lea     rdx, [rsp+rdx*2+4D0h+var_470]
0x1400020d6  jnz     short loc_140002120
0x1400020d8  sub     rdx, 2
0x1400020dc  jmp     short loc_1400020E3
0x1400020de  test    r8, r8
0x1400020e1  jz      short loc_1400020D8
0x1400020e3  xor     eax, eax
0x1400020e5  mov     [rdx], ax
0x1400020e8  jmp     loc_140001FC4
0x1400020ed  lea     r8, [rsp+4D0h+var_480]
0x1400020f2  lea     rdx, [rsp+4D0h+var_490]
0x1400020f7  lea     rcx, [rbp+3D0h+Name]; unsigned __int16 *
0x1400020fe  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x140002103  test    eax, eax
0x140002105  js      loc_140002216
0x14000210b  mov     rdi, [rsp+4D0h+var_480]
0x140002110  mov     rbx, [rsp+4D0h+var_490]
0x140002115  jmp     loc_140002006
0x140002120  test    rcx, rcx
0x140002123  jz      short loc_1400020E3
0x140002125  movzx   eax, word ptr [r9]
0x140002129  test    ax, ax
0x14000212c  jz      short loc_1400020DE
0x14000212e  mov     [rdx], ax
0x140002131  add     r9, 2
0x140002135  add     rdx, 2
0x140002139  dec     rcx
0x14000213c  sub     r8, 1
0x140002140  jnz     short loc_140002120
0x140002142  jmp     short loc_1400020D8
0x140002144  lea     rdx, [rsp+4D0h+var_49C]; int *
0x140002149  mov     [rsp+4D0h+var_49C], edi
0x14000214d  mov     rcx, rax; hHandle
0x140002150  mov     [rsp+4D0h+var_4A0], edi
0x140002154  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140002159  mov     edi, eax
0x14000215b  test    eax, eax
0x14000215d  js      loc_14000225E
0x140002163  mov     rcx, r14
0x140002166  lea     rax, [rsp+4D0h+var_470]
0x14000216b  cmp     [rax], r12w
0x14000216f  jz      short loc_14000217B
0x140002171  add     rax, 2
0x140002175  sub     rcx, 1
0x140002179  jnz     short loc_14000216B
0x14000217b  xor     eax, eax
0x14000217d  mov     rdx, r14
0x140002180  sub     rdx, rcx
0x140002183  test    rcx, rcx
0x140002186  cmovz   rdx, rax
0x14000218a  jz      short loc_1400021AA
0x14000218c  lea     rcx, [rsp+4D0h+var_470]
0x140002191  lea     rcx, [rcx+rdx*2]
0x140002195  lea     rax, pszSrc; "h"
0x14000219c  sub     r14, rdx
0x14000219f  jnz     short loc_1400021EC
0x1400021a1  sub     rcx, 2
0x1400021a5  xor     eax, eax
0x1400021a7  mov     [rcx], ax
0x1400021aa  lea     r8, [rsp+4D0h+var_470]; lpName
0x1400021af  xor     edx, edx; bInheritHandle
0x1400021b1  mov     ecx, 1F0003h; dwDesiredAccess
0x1400021b6  call    cs:__imp_OpenSemaphoreW
0x1400021bc  mov     [rsp+4D0h+var_488], rax
0x1400021c1  test    rax, rax
0x1400021c4  jnz     loc_140002288
0x1400021ca  mov     rcx, [rbp+3D8h]; this
0x1400021d1  mov     edx, 0DCh; void *
0x1400021d6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400021db  lea     rcx, [rsp+4D0h+var_488]
0x1400021e0  mov     edi, eax
0x1400021e2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400021e7  jmp     loc_14000204C
0x1400021ec  test    r13, r13
0x1400021ef  jz      short loc_1400021A5
0x1400021f1  movzx   edx, word ptr [rax]
0x1400021f4  test    dx, dx
0x1400021f7  jz      short loc_14000220F
0x1400021f9  mov     [rcx], dx
0x1400021fc  add     rax, 2
0x140002200  add     rcx, 2
0x140002204  dec     r13
0x140002207  sub     r14, 1
0x14000220b  jnz     short loc_1400021EC
0x14000220d  jmp     short loc_1400021A1
0x14000220f  test    r14, r14
0x140002212  jnz     short loc_1400021A5
0x140002214  jmp     short loc_1400021A1
0x140002216  mov     rcx, [rbp+3D8h]; this
0x14000221d  lea     r8, aWil; "wil"
0x140002224  mov     r9d, eax; char *
0x140002227  mov     edx, 137h; void *
0x14000222c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002231  test    r15, r15
0x140002234  jnz     loc_140002306
0x14000223a  lea     rcx, [rsp+4D0h+var_490]
0x14000223f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140002244  jmp     loc_140001E6B
0x140002249  mov     rcx, [rbp+3D8h]; this
0x140002250  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140002256  xor     r15d, r15d
0x140002259  jmp     loc_140001F48
0x14000225e  mov     rcx, [rbp+3D8h]; this
0x140002265  lea     r8, aWil; "wil"
0x14000226c  mov     r9d, eax; char *
0x14000226f  mov     edx, 0D6h; void *
0x140002274  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002279  lea     rcx, [rsp+4D0h+var_498]
0x14000227e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140002283  jmp     loc_14000205A
0x140002288  lea     rdx, [rsp+4D0h+var_4A0]; int *
0x14000228d  mov     rcx, rax; hHandle
0x140002290  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140002295  mov     edi, eax
0x140002297  test    eax, eax
0x140002299  jns     short loc_1400022CF
0x14000229b  mov     rcx, [rbp+3D8h]; this
0x1400022a2  lea     r8, aWil; "wil"
0x1400022a9  mov     r9d, eax; char *
0x1400022ac  mov     edx, 0DEh; void *
0x1400022b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400022b6  lea     rcx, [rsp+4D0h+var_488]
0x1400022bb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400022c0  lea     rcx, [rsp+4D0h+var_498]
0x1400022c5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400022ca  jmp     loc_14000205A
0x1400022cf  lea     rcx, [rsp+4D0h+var_488]
0x1400022d4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400022d9  movsxd  rax, [rsp+4D0h+var_49C]
0x1400022de  lea     rcx, [rsp+4D0h+var_498]
0x1400022e3  movsxd  r12, [rsp+4D0h+var_4A0]
0x1400022e8  shl     r12, 1Fh
  ... truncated ...
```
