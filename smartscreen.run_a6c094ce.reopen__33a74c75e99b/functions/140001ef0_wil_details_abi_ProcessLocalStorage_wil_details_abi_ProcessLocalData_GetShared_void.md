# wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData>::GetShared(void)

- ea: `0x140001ef0`
- end: `0x140002418`
- name: `?GetShared@?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUProcessLocalData@23@XZ`
- size: `1320`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140001e50`

## callees

- `0x1400018a8`
- `0x140001b4c`
- `0x140001ef0`
- `0x140002420`
- `0x1400031bc`
- `0x140004a30`
- `0x1400114e8`
- `0x1400184f0`
- `0x140018518`
- `0x140018600`
- `0x140026c20`
- `0x14002f0b4`
- `0x14002f80c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140001fb4`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140001fb4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400020a1`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140002296`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400020a1`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140002296`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140001ff6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140001ff6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400020bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400020bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140001f6a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140001f6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400020f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400020f4`

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
0x140001ef0  push    rbp
0x140001ef2  push    rbx
0x140001ef3  push    rsi
0x140001ef4  push    rdi
0x140001ef5  push    r12
0x140001ef7  push    r13
0x140001ef9  push    r14
0x140001efb  push    r15
0x140001efd  lea     rbp, [rsp-398h]
0x140001f05  sub     rsp, 498h
0x140001f0c  mov     rax, cs:__security_cookie
0x140001f13  xor     rax, rsp
0x140001f16  mov     [rbp+3D0h+var_50], rax
0x140001f1d  mov     rsi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140001f24  cmp     qword ptr [rsi+8], 0
0x140001f29  jz      short loc_140001F60
0x140001f2b  mov     rdx, [rsi+8]
0x140001f2f  xor     ecx, ecx
0x140001f31  test    rdx, rdx
0x140001f34  lea     rax, [rdx+20h]
0x140001f38  cmovz   rax, rcx
0x140001f3c  mov     rcx, [rbp+3D0h+var_50]
0x140001f43  xor     rcx, rsp; StackCookie
0x140001f46  call    __security_check_cookie
0x140001f4b  add     rsp, 498h
0x140001f52  pop     r15
0x140001f54  pop     r14
0x140001f56  pop     r13
0x140001f58  pop     r12
0x140001f5a  pop     rdi
0x140001f5b  pop     rsi
0x140001f5c  pop     rbx
0x140001f5d  pop     rbp
0x140001f5e  retn
0x140001f60  mov     rbx, [rsi]
0x140001f63  xor     edi, edi
0x140001f65  mov     [rsp+4D0h+var_480], rdi
0x140001f6a  call    cs:__imp_GetCurrentProcessId
0x140001f71  nop     dword ptr [rax+rax+00h]
0x140001f76  mov     r14d, 104h
0x140001f7c  mov     [rsp+4D0h+var_4A8], rbx
0x140001f81  mov     r9d, eax
0x140001f84  mov     [rsp+4D0h+var_4B0], 78h ; 'x'; int
0x140001f8c  mov     edx, r14d; unsigned __int64
0x140001f8f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140001f96  lea     rcx, [rbp+3D0h+Name]; Buffer
0x140001f9d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140001fa2  mov     r9d, 1F0001h; dwDesiredAccess
0x140001fa8  lea     rdx, [rbp+3D0h+Name]; lpName
0x140001faf  xor     r8d, r8d; dwFlags
0x140001fb2  xor     ecx, ecx; lpMutexAttributes
0x140001fb4  call    cs:__imp_CreateMutexExW
0x140001fbb  nop     dword ptr [rax+rax+00h]
0x140001fc0  mov     [rsp+4D0h+var_490], rax
0x140001fc5  mov     rbx, rax
0x140001fc8  test    rax, rax
0x140001fcb  jnz     short loc_140001FEB
0x140001fcd  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140001fd2  lea     rcx, [rsp+4D0h+var_490]
0x140001fd7  mov     ebx, eax
0x140001fd9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140001fde  test    ebx, ebx
0x140001fe0  js      loc_140001F2B
0x140001fe6  jmp     loc_140002108
0x140001feb  xor     r8d, r8d; bAlertable
0x140001fee  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x140001ff3  mov     rcx, rbx; hHandle
0x140001ff6  call    cs:__imp_WaitForSingleObjectEx
0x140001ffd  nop     dword ptr [rax+rax+00h]
0x140002002  cmp     eax, 102h
0x140002007  jz      loc_14000233C
0x14000200d  test    eax, 0FFFFFF7Fh
0x140002012  jnz     loc_14000232F
0x140002018  mov     r15, rbx
0x14000201b  mov     r13d, 7FFFFFFEh
0x140002021  lea     rdx, [rbp+3D0h+Name]
0x140002028  mov     ecx, r13d
0x14000202b  lea     r9, [rsp+4D0h+var_470]
0x140002030  xor     r12d, r12d
0x140002033  mov     r8, r14
0x140002036  test    rcx, rcx
0x140002039  jz      short loc_140002063
0x14000203b  movzx   eax, word ptr [rdx]
0x14000203e  test    ax, ax
0x140002041  jz      short loc_14000205E
0x140002043  mov     [r9], ax
0x140002047  add     rdx, 2
0x14000204b  add     r9, 2
0x14000204f  dec     rcx
0x140002052  sub     r8, 1
0x140002056  jnz     short loc_140002036
0x140002058  sub     r9, 2
0x14000205c  jmp     short loc_140002063
0x14000205e  test    r8, r8
0x140002061  jz      short loc_140002058
0x140002063  xor     eax, eax
0x140002065  mov     rcx, r14
0x140002068  mov     [r9], ax
0x14000206c  lea     rax, [rsp+4D0h+var_470]
0x140002071  cmp     [rax], di
0x140002074  jz      short loc_140002080
0x140002076  add     rax, 2
0x14000207a  sub     rcx, 1
0x14000207e  jnz     short loc_140002071
0x140002080  xor     eax, eax
0x140002082  mov     rdx, r14
0x140002085  sub     rdx, rcx
0x140002088  test    rcx, rcx
0x14000208b  cmovz   rdx, rax
0x14000208f  jnz     loc_1400021A4
0x140002095  lea     r8, [rsp+4D0h+var_470]; lpName
0x14000209a  xor     edx, edx; bInheritHandle
0x14000209c  mov     ecx, 1F0003h; dwDesiredAccess
0x1400020a1  call    cs:__imp_OpenSemaphoreW
0x1400020a8  nop     dword ptr [rax+rax+00h]
0x1400020ad  mov     [rsp+4D0h+var_498], rax
0x1400020b2  test    rax, rax
0x1400020b5  jnz     loc_140002224
0x1400020bb  call    cs:__imp_GetLastError
0x1400020c2  nop     dword ptr [rax+rax+00h]
0x1400020c7  cmp     eax, 2
0x1400020ca  jnz     short loc_14000211C
0x1400020cc  lea     rdi, ds:0[r12*4]
0x1400020d4  test    rdi, rdi
0x1400020d7  jz      loc_1400021D0
0x1400020dd  mov     eax, [rdi]
0x1400020df  inc     eax
0x1400020e1  mov     [rdi], eax
0x1400020e3  test    r15, r15
0x1400020e6  jnz     loc_1400023F9
0x1400020ec  test    rbx, rbx
0x1400020ef  jz      short loc_140002108
0x1400020f1  mov     rcx, rbx; hObject
0x1400020f4  call    cs:__imp_CloseHandle
0x1400020fb  nop     dword ptr [rax+rax+00h]
0x140002100  test    eax, eax
0x140002102  jz      loc_140002406
0x140002108  cmp     qword ptr [rsi+8], 0
0x14000210d  jnz     loc_140001F2B
0x140002113  mov     [rsi+8], rdi
0x140002117  jmp     loc_140001F2B
0x14000211c  mov     rcx, [rbp+3D8h]; this
0x140002123  mov     edx, 0D0h; void *
0x140002128  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000212d  mov     edi, eax
0x14000212f  lea     rcx, [rsp+4D0h+var_498]
0x140002134  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140002139  test    edi, edi
0x14000213b  jns     short loc_1400020CC
0x14000213d  mov     rcx, [rbp+3D8h]; this
0x140002144  lea     r8, aWil; "wil"
0x14000214b  mov     r9d, edi; char *
0x14000214e  mov     edx, 66h ; 'f'; void *
0x140002153  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002158  mov     rcx, [rbp+3D8h]; this
0x14000215f  lea     r8, aWil; "wil"
0x140002166  mov     r9d, edi; char *
0x140002169  mov     edx, 6Fh ; 'o'; void *
0x14000216e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002173  mov     rcx, [rbp+3D8h]; this
0x14000217a  lea     r8, aWil; "wil"
0x140002181  mov     r9d, edi; char *
0x140002184  mov     edx, 12Eh; void *
0x140002189  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000218e  test    r15, r15
0x140002191  jnz     loc_1400023DF
0x140002197  mov     rcx, rbx; this
0x14000219a  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x14000219f  jmp     loc_140001F2B
0x1400021a4  mov     r8, r14
0x1400021a7  lea     r9, aP0; "_p0"
0x1400021ae  sub     r8, rdx
0x1400021b1  mov     rcx, r13
0x1400021b4  lea     rdx, [rsp+rdx*2+4D0h+var_470]
0x1400021b9  jnz     short loc_140002200
0x1400021bb  sub     rdx, 2
0x1400021bf  jmp     short loc_1400021C6
0x1400021c1  test    r8, r8
0x1400021c4  jz      short loc_1400021BB
0x1400021c6  xor     eax, eax
0x1400021c8  mov     [rdx], ax
0x1400021cb  jmp     loc_140002095
0x1400021d0  lea     r8, [rsp+4D0h+var_480]
0x1400021d5  lea     rdx, [rsp+4D0h+var_490]
0x1400021da  lea     rcx, [rbp+3D0h+Name]; unsigned __int16 *
0x1400021e1  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1400021e6  test    eax, eax
0x1400021e8  js      loc_1400022FC
0x1400021ee  mov     rdi, [rsp+4D0h+var_480]
0x1400021f3  mov     rbx, [rsp+4D0h+var_490]
0x1400021f8  jmp     loc_1400020E3
0x140002200  test    rcx, rcx
0x140002203  jz      short loc_1400021C6
0x140002205  movzx   eax, word ptr [r9]
0x140002209  test    ax, ax
0x14000220c  jz      short loc_1400021C1
0x14000220e  mov     [rdx], ax
0x140002211  add     r9, 2
0x140002215  add     rdx, 2
0x140002219  dec     rcx
0x14000221c  sub     r8, 1
0x140002220  jnz     short loc_140002200
0x140002222  jmp     short loc_1400021BB
0x140002224  lea     rdx, [rsp+4D0h+var_49C]; int *
0x140002229  mov     [rsp+4D0h+var_49C], edi
0x14000222d  mov     rcx, rax; hHandle
0x140002230  mov     [rsp+4D0h+var_4A0], edi
0x140002234  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140002239  mov     edi, eax
0x14000223b  test    eax, eax
0x14000223d  js      loc_140002344
0x140002243  mov     rcx, r14
0x140002246  lea     rax, [rsp+4D0h+var_470]
0x14000224b  cmp     [rax], r12w
0x14000224f  jz      short loc_14000225B
0x140002251  add     rax, 2
0x140002255  sub     rcx, 1
0x140002259  jnz     short loc_14000224B
0x14000225b  xor     eax, eax
0x14000225d  mov     rdx, r14
0x140002260  sub     rdx, rcx
0x140002263  test    rcx, rcx
0x140002266  cmovz   rdx, rax
0x14000226a  jz      short loc_14000228A
0x14000226c  lea     rcx, [rsp+4D0h+var_470]
0x140002271  lea     rcx, [rcx+rdx*2]
0x140002275  lea     rax, pszSrc; "h"
0x14000227c  sub     r14, rdx
0x14000227f  jnz     short loc_1400022D2
0x140002281  sub     rcx, 2
0x140002285  xor     eax, eax
0x140002287  mov     [rcx], ax
0x14000228a  lea     r8, [rsp+4D0h+var_470]; lpName
0x14000228f  xor     edx, edx; bInheritHandle
0x140002291  mov     ecx, 1F0003h; dwDesiredAccess
0x140002296  call    cs:__imp_OpenSemaphoreW
0x14000229d  nop     dword ptr [rax+rax+00h]
0x1400022a2  mov     [rsp+4D0h+var_488], rax
0x1400022a7  test    rax, rax
0x1400022aa  jnz     loc_14000236E
0x1400022b0  mov     rcx, [rbp+3D8h]; this
0x1400022b7  mov     edx, 0DCh; void *
0x1400022bc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400022c1  lea     rcx, [rsp+4D0h+var_488]
0x1400022c6  mov     edi, eax
0x1400022c8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400022cd  jmp     loc_14000212F
0x1400022d2  test    r13, r13
0x1400022d5  jz      short loc_140002285
0x1400022d7  movzx   edx, word ptr [rax]
0x1400022da  test    dx, dx
0x1400022dd  jz      short loc_1400022F5
0x1400022df  mov     [rcx], dx
0x1400022e2  add     rax, 2
0x1400022e6  add     rcx, 2
0x1400022ea  dec     r13
0x1400022ed  sub     r14, 1
0x1400022f1  jnz     short loc_1400022D2
0x1400022f3  jmp     short loc_140002281
0x1400022f5  test    r14, r14
0x1400022f8  jnz     short loc_140002285
0x1400022fa  jmp     short loc_140002281
0x1400022fc  mov     rcx, [rbp+3D8h]; this
0x140002303  lea     r8, aWil; "wil"
0x14000230a  mov     r9d, eax; char *
0x14000230d  mov     edx, 137h; void *
0x140002312  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002317  test    r15, r15
0x14000231a  jnz     loc_1400023EC
0x140002320  lea     rcx, [rsp+4D0h+var_490]
0x140002325  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000232a  jmp     loc_140001F2B
0x14000232f  mov     rcx, [rbp+3D8h]; this
0x140002336  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x14000233c  xor     r15d, r15d
0x14000233f  jmp     loc_14000201B
0x140002344  mov     rcx, [rbp+3D8h]; this
0x14000234b  lea     r8, aWil; "wil"
0x140002352  mov     r9d, eax; char *
0x140002355  mov     edx, 0D6h; void *
0x14000235a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000235f  lea     rcx, [rsp+4D0h+var_498]
0x140002364  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140002369  jmp     loc_14000213D
0x14000236e  lea     rdx, [rsp+4D0h+var_4A0]; int *
0x140002373  mov     rcx, rax; hHandle
0x140002376  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000237b  mov     edi, eax
0x14000237d  test    eax, eax
0x14000237f  jns     short loc_1400023B5
0x140002381  mov     rcx, [rbp+3D8h]; this
0x140002388  lea     r8, aWil; "wil"
0x14000238f  mov     r9d, eax; char *
0x140002392  mov     edx, 0DEh; void *
0x140002397  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000239c  lea     rcx, [rsp+4D0h+var_488]
0x1400023a1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400023a6  lea     rcx, [rsp+4D0h+var_498]
0x1400023ab  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400023b0  jmp     loc_14000213D
  ... truncated ...
```
