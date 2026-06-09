# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180008410`
- end: `0x180008735`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `805`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000818c`
- `0x180008bc0`

## callees

- `0x180008410`
- `0x180008740`
- `0x18000891c`
- `0x1800089a8`
- `0x180036c2c`
- `0x18003729c`
- `0x180054130`
- `0x18005c158`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008507`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800085dd`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008507`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800085dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800086c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800086c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008643`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000867d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008643`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000867d`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // r9
  __int64 v5; // rsi
  __int64 v6; // rbx
  __int64 v7; // rax
  __int64 v8; // r10
  WCHAR *v11; // rcx
  __int64 v12; // rdx
  WCHAR *v13; // rax
  __int64 v14; // rcx
  _WORD *v15; // r8
  const unsigned __int16 *v16; // r9
  _WORD *v17; // rcx
  wil::details *v18; // rax
  wil::details *v19; // rdi
  int ValueFromSemaphore; // eax
  unsigned int v21; // ebp
  WCHAR *v23; // rax
  _WORD *v24; // r8
  const unsigned __int16 *v25; // rcx
  _WORD *v26; // rdx
  wil::details *v27; // rax
  const char *v28; // r9
  wil::details *v29; // rbx
  int v30; // eax
  unsigned int v31; // esi
  void *v32; // rdx
  void *v33; // rdx
  unsigned int v34; // r8d
  const char *v35; // r9
  unsigned int v36; // r8d
  const char *v37; // r9
  unsigned int LastError; // ebx
  const char *v39; // r9
  int v40; // [rsp+20h] [rbp-258h] BYREF
  int v41; // [rsp+24h] [rbp-254h] BYREF
  wil::details *v42; // [rsp+28h] [rbp-250h] BYREF
  wil::details *v43; // [rsp+30h] [rbp-248h] BYREF
  WCHAR Name[260]; // [rsp+40h] [rbp-238h] BYREF
  _BYTE v45[8]; // [rsp+248h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  v4 = Name;
  v5 = 2147483646;
  *a3 = 0;
  v6 = 260;
  v7 = 2147483646;
  v8 = 260;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v7;
    --v8;
  }
  while ( v8 );
  v11 = v4 - 1;
  v12 = 260;
  v13 = Name;
  if ( v8 )
    v11 = v4;
  *v11 = 0;
  while ( *v13 )
  {
    ++v13;
    if ( !--v12 )
      goto LABEL_18;
  }
  v14 = 2147483646;
  v15 = &v45[-2 * v12];
  v16 = L"_p0";
  do
  {
    if ( !v14 )
      break;
    if ( !*v16 )
      break;
    *v15++ = *v16++;
    --v14;
    --v12;
  }
  while ( v12 );
  v17 = v15 - 1;
  if ( v12 )
    v17 = v15;
  *v17 = 0;
LABEL_18:
  v18 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v42 = v18;
  v19 = v18;
  if ( v18 )
  {
    v41 = 0;
    v40 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v18, &v41);
    v21 = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v40);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v42);
      return v21;
    }
    v23 = Name;
    while ( *v23 )
    {
      ++v23;
      if ( !--v6 )
        goto LABEL_32;
    }
    v24 = &v45[-2 * v6];
    v25 = L"h";
    do
    {
      if ( !v5 )
        break;
      if ( !*v25 )
        break;
      *v24++ = *v25++;
      --v5;
      --v6;
    }
    while ( v6 );
    v26 = v24 - 1;
    if ( v6 )
      v26 = v24;
    *v26 = 0;
LABEL_32:
    v27 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
    v43 = v27;
    v29 = v27;
    if ( v27 )
    {
      v30 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v27, &v40);
      v31 = v30;
      if ( v30 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xDE,
          (unsigned int)"wil",
          (const char *)(unsigned int)v30,
          v40);
        wil::details::CloseHandle(v29, v32);
        wil::details::CloseHandle(v19, v33);
        return v31;
      }
      if ( !CloseHandle(v29) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v34, v35);
      *a3 = v41 | (unsigned __int64)((__int64)v40 << 31);
      if ( !CloseHandle(v19) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v36, v37);
      return 0;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v28);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v43);
  }
  else
  {
    if ( GetLastError() == 2 )
      return 0;
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v39);
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v42);
  return LastError;
}

```

## disassembly

```asm
0x180008410  mov     [rsp+arg_8], rbx
0x180008415  mov     [rsp+arg_18], rsi
0x18000841a  push    rdi
0x18000841b  push    r14
0x18000841d  push    r15
0x18000841f  sub     rsp, 260h
0x180008426  mov     rax, cs:__security_cookie
0x18000842d  xor     rax, rsp
0x180008430  mov     [rsp+278h+var_28], rax
0x180008438  xor     r15d, r15d
0x18000843b  lea     r9, [rsp+278h+Name]
0x180008440  mov     esi, 7FFFFFFEh
0x180008445  mov     [r8], r15
0x180008448  mov     ebx, 104h
0x18000844d  mov     eax, esi
0x18000844f  mov     r10d, ebx
0x180008452  mov     r14, r8
0x180008455  mov     rdx, rcx
0x180008458  test    rax, rax
0x18000845b  jz      short loc_18000847A
0x18000845d  movzx   ecx, word ptr [rdx]
0x180008460  test    cx, cx
0x180008463  jz      short loc_18000847A
0x180008465  mov     [r9], cx
0x180008469  add     rdx, 2
0x18000846d  add     r9, 2
0x180008471  dec     rax
0x180008474  sub     r10, 1
0x180008478  jnz     short loc_180008458
0x18000847a  test    r10, r10
0x18000847d  lea     rcx, [r9-2]
0x180008481  mov     rdx, rbx
0x180008484  lea     rax, [rsp+278h+Name]
0x180008489  cmovnz  rcx, r9
0x18000848d  mov     [rcx], r15w
0x180008491  cmp     [rax], r15w
0x180008495  jz      short loc_1800084A3
0x180008497  add     rax, 2
0x18000849b  sub     rdx, 1
0x18000849f  jnz     short loc_180008491
0x1800084a1  jmp     short loc_1800084F3
0x1800084a3  lea     rax, [rdx+rdx]
0x1800084a7  mov     rcx, rsi
0x1800084aa  lea     r8, [rsp+278h+var_30]
0x1800084b2  sub     r8, rax
0x1800084b5  lea     r9, aP0; "_p0"
0x1800084bc  test    rdx, rdx
0x1800084bf  jz      short loc_1800084E4
0x1800084c1  test    rcx, rcx
0x1800084c4  jz      short loc_1800084E4
0x1800084c6  movzx   eax, word ptr [r9]
0x1800084ca  test    ax, ax
0x1800084cd  jz      short loc_1800084E4
0x1800084cf  mov     [r8], ax
0x1800084d3  add     r9, 2
0x1800084d7  add     r8, 2
0x1800084db  dec     rcx
0x1800084de  sub     rdx, 1
0x1800084e2  jnz     short loc_1800084C1
0x1800084e4  test    rdx, rdx
0x1800084e7  lea     rcx, [r8-2]
0x1800084eb  cmovnz  rcx, r8
0x1800084ef  mov     [rcx], r15w
0x1800084f3  lea     r8, [rsp+278h+Name]; lpName
0x1800084f8  mov     [rsp+278h+arg_0], rbp
0x180008500  xor     edx, edx; bInheritHandle
0x180008502  mov     ecx, 1F0003h; dwDesiredAccess
0x180008507  call    cs:__imp_OpenSemaphoreW
0x18000850e  nop     dword ptr [rax+rax+00h]
0x180008513  mov     [rsp+278h+var_250], rax
0x180008518  mov     rdi, rax
0x18000851b  test    rax, rax
0x18000851e  jz      loc_1800086C7
0x180008524  lea     rdx, [rsp+278h+var_254]; int *
0x180008529  mov     [rsp+278h+var_254], r15d
0x18000852e  mov     rcx, rax; hHandle
0x180008531  mov     [rsp+278h+var_258], r15d; int
0x180008536  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000853b  mov     ebp, eax
0x18000853d  test    eax, eax
0x18000853f  jns     short loc_18000856E
0x180008541  mov     rcx, [rsp+278h]; this
0x180008549  lea     r8, aWil; "wil"
0x180008550  mov     r9d, eax; char *
0x180008553  mov     edx, 0D6h; void *
0x180008558  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000855d  lea     rcx, [rsp+278h+var_250]
0x180008562  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008567  mov     eax, ebp
0x180008569  jmp     loc_180008703
0x18000856e  lea     rax, [rsp+278h+Name]
0x180008573  cmp     [rax], r15w
0x180008577  jz      short loc_180008585
0x180008579  add     rax, 2
0x18000857d  sub     rbx, 1
0x180008581  jnz     short loc_180008573
0x180008583  jmp     short loc_1800085D1
0x180008585  lea     rax, [rbx+rbx]
0x180008589  lea     r8, [rsp+278h+var_30]
0x180008591  sub     r8, rax
0x180008594  lea     rcx, asc_180105660; "h"
0x18000859b  test    rbx, rbx
0x18000859e  jz      short loc_1800085C2
0x1800085a0  test    rsi, rsi
0x1800085a3  jz      short loc_1800085C2
0x1800085a5  movzx   eax, word ptr [rcx]
0x1800085a8  test    ax, ax
0x1800085ab  jz      short loc_1800085C2
0x1800085ad  mov     [r8], ax
0x1800085b1  add     rcx, 2
0x1800085b5  add     r8, 2
0x1800085b9  dec     rsi
0x1800085bc  sub     rbx, 1
0x1800085c0  jnz     short loc_1800085A0
0x1800085c2  test    rbx, rbx
0x1800085c5  lea     rdx, [r8-2]
0x1800085c9  cmovnz  rdx, r8
0x1800085cd  mov     [rdx], r15w
0x1800085d1  lea     r8, [rsp+278h+Name]; lpName
0x1800085d6  xor     edx, edx; bInheritHandle
0x1800085d8  mov     ecx, 1F0003h; dwDesiredAccess
0x1800085dd  call    cs:__imp_OpenSemaphoreW
0x1800085e4  nop     dword ptr [rax+rax+00h]
0x1800085e9  mov     [rsp+278h+var_248], rax
0x1800085ee  mov     rbx, rax
0x1800085f1  test    rax, rax
0x1800085f4  jz      loc_1800086A0
0x1800085fa  lea     rdx, [rsp+278h+var_258]; int *
0x1800085ff  mov     rcx, rax; hHandle
0x180008602  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180008607  mov     esi, eax
0x180008609  test    eax, eax
0x18000860b  jns     short loc_180008640
0x18000860d  mov     rcx, [rsp+278h]; this
0x180008615  lea     r8, aWil; "wil"
0x18000861c  mov     r9d, eax; char *
0x18000861f  mov     edx, 0DEh; void *
0x180008624  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008629  mov     rcx, rbx; this
0x18000862c  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180008631  mov     rcx, rdi; this
0x180008634  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180008639  mov     eax, esi
0x18000863b  jmp     loc_180008703
0x180008640  mov     rcx, rbx; hObject
0x180008643  call    cs:__imp_CloseHandle
0x18000864a  nop     dword ptr [rax+rax+00h]
0x18000864f  test    eax, eax
0x180008651  jnz     short loc_180008666
0x180008653  mov     rcx, [rsp+278h]; this
0x18000865b  mov     edx, 0A0Bh; void *
0x180008660  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008666  movsxd  rax, [rsp+278h+var_254]
0x18000866b  movsxd  rcx, [rsp+278h+var_258]
0x180008670  shl     rcx, 1Fh
0x180008674  or      rcx, rax
0x180008677  mov     [r14], rcx
0x18000867a  mov     rcx, rdi; hObject
0x18000867d  call    cs:__imp_CloseHandle
0x180008684  nop     dword ptr [rax+rax+00h]
0x180008689  test    eax, eax
0x18000868b  jnz     short loc_1800086D8
0x18000868d  mov     rcx, [rsp+278h]; this
0x180008695  mov     edx, 0A0Bh; void *
0x18000869a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800086a0  mov     rcx, [rsp+278h]; this
0x1800086a8  lea     r8, aWil; "wil"
0x1800086af  mov     edx, 0DCh; void *
0x1800086b4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800086b9  lea     rcx, [rsp+278h+var_248]
0x1800086be  mov     ebx, eax
0x1800086c0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800086c5  jmp     short loc_1800086F7
0x1800086c7  call    cs:__imp_GetLastError
0x1800086ce  nop     dword ptr [rax+rax+00h]
0x1800086d3  cmp     eax, 2
0x1800086d6  jnz     short loc_1800086DC
0x1800086d8  xor     eax, eax
0x1800086da  jmp     short loc_180008703
0x1800086dc  mov     rcx, [rsp+278h]; this
0x1800086e4  lea     r8, aWil; "wil"
0x1800086eb  mov     edx, 0D0h; void *
0x1800086f0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800086f5  mov     ebx, eax
0x1800086f7  lea     rcx, [rsp+278h+var_250]
0x1800086fc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008701  mov     eax, ebx
0x180008703  mov     rbp, [rsp+278h+arg_0]
0x18000870b  mov     rcx, [rsp+278h+var_28]
0x180008713  xor     rcx, rsp; StackCookie
0x180008716  call    __security_check_cookie
0x18000871b  lea     r11, [rsp+278h+var_18]
0x180008723  mov     rbx, [r11+28h]
0x180008727  mov     rsi, [r11+38h]
0x18000872b  mov     rsp, r11
0x18000872e  pop     r15
0x180008730  pop     r14
0x180008732  pop     rdi
0x180008733  retn
```
