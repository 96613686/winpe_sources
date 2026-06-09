# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180004ad0`
- end: `0x180004dee`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `798`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180003554`
- `0x180004790`

## callees

- `0x180003514`
- `0x180004ad0`
- `0x180004df4`
- `0x180004e20`
- `0x18001f038`
- `0x1800201d4`
- `0x180021ec0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180004bd3`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180004cdd`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180004bd3`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180004cdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004be8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004be8`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  __int64 v6; // rsi
  __int64 v7; // rax
  __int64 v8; // r9
  WCHAR *v9; // r8
  WCHAR v10; // cx
  WCHAR *v11; // rcx
  __int64 v12; // rcx
  WCHAR *v13; // rax
  __int64 v14; // r9
  __int64 v15; // rcx
  const unsigned __int16 *v16; // rdx
  bool v17; // zf
  __int64 v18; // r8
  WCHAR *v19; // r9
  unsigned __int16 v20; // ax
  WCHAR *v21; // rcx
  const char *v22; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  __int64 v26; // rcx
  WCHAR *v27; // rax
  __int64 v28; // rdx
  const unsigned __int16 *v29; // rcx
  __int64 v30; // rdi
  WCHAR *v31; // r8
  unsigned __int16 v32; // ax
  WCHAR *v33; // rdx
  const char *v34; // r9
  int v35; // eax
  void *v36; // rdx
  void *v37; // rdx
  HANDLE hHandle; // [rsp+20h] [rbp-E0h] BYREF
  int v39; // [rsp+28h] [rbp-D8h] BYREF
  int v40; // [rsp+2Ch] [rbp-D4h] BYREF
  HANDLE v41[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  *a3 = 0;
  v6 = 2147483646;
  v7 = 2147483646;
  v8 = 260;
  v9 = Name;
  do
  {
    if ( !v7 )
      break;
    v10 = *a1;
    if ( !*a1 )
      break;
    ++a1;
    *v9++ = v10;
    --v7;
    --v8;
  }
  while ( v8 );
  v11 = v9 - 1;
  if ( v8 )
    v11 = v9;
  *v11 = 0;
  v12 = 260;
  v13 = Name;
  do
  {
    if ( !*v13 )
      break;
    ++v13;
    --v12;
  }
  while ( v12 );
  v14 = 260 - v12;
  if ( v12 )
  {
    v15 = 2147483646;
    v16 = L"_p0";
    v18 = 260 - v14;
    v17 = v14 == 260;
    v19 = &Name[v14];
    if ( !v17 )
    {
      do
      {
        if ( !v15 )
          break;
        v20 = *v16;
        if ( !*v16 )
          break;
        ++v16;
        *v19++ = v20;
        --v15;
        --v18;
      }
      while ( v18 );
    }
    v21 = v19 - 1;
    if ( v18 )
      v21 = v19;
    *v21 = 0;
  }
  hHandle = OpenSemaphoreW(0x1F0003u, 0, Name);
  if ( hHandle )
  {
    v40 = 0;
    v39 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(hHandle, &v40);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        (int)hHandle);
      __1__unique_any_t_V__mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAA_XZ(&hHandle);
      return LastError;
    }
    v26 = 260;
    v27 = Name;
    do
    {
      if ( !*v27 )
        break;
      ++v27;
      --v26;
    }
    while ( v26 );
    v28 = 260 - v26;
    if ( v26 )
    {
      v29 = L"h";
      v30 = 260 - v28;
      v31 = &Name[v28];
      if ( 260 != v28 )
      {
        do
        {
          if ( !v6 )
            break;
          v32 = *v29;
          if ( !*v29 )
            break;
          ++v29;
          *v31++ = v32;
          --v6;
          --v30;
        }
        while ( v30 );
      }
      v33 = v31 - 1;
      if ( v30 )
        v33 = v31;
      *v33 = 0;
    }
    v41[0] = OpenSemaphoreW(0x1F0003u, 0, Name);
    if ( !v41[0] )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v34);
      if ( v41[0] )
        wil::details::CloseHandle((wil::details *)v41[0], v37);
      if ( hHandle )
        wil::details::CloseHandle((wil::details *)hHandle, v37);
      return LastError;
    }
    v35 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v41[0], &v39);
    LastError = v35;
    if ( v35 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v35,
        (int)hHandle);
      __1__unique_any_t_V__mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAA_XZ(v41);
      __1__unique_any_t_V__mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAA_XZ(&hHandle);
      return LastError;
    }
    if ( v41[0] )
      wil::details::CloseHandle((wil::details *)v41[0], v36);
    *a3 = v40 | (unsigned __int64)((__int64)v39 << 31);
    if ( hHandle )
      wil::details::CloseHandle((wil::details *)hHandle, v36);
    return 0;
  }
  else
  {
    if ( GetLastError() != 2 )
      return (unsigned int)wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v22);
    __1__unique_any_t_V__mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAA_XZ(&hHandle);
    return 0;
  }
}

```

## disassembly

```asm
0x180004ad0  push    rbp
0x180004ad2  push    rbx
0x180004ad3  push    rsi
0x180004ad4  push    rdi
0x180004ad5  push    r14
0x180004ad7  push    r15
0x180004ad9  lea     rbp, [rsp-168h]
0x180004ae1  sub     rsp, 268h
0x180004ae8  mov     rax, cs:__security_cookie
0x180004aef  xor     rax, rsp
0x180004af2  mov     [rbp+190h+var_40], rax
0x180004af9  mov     r14, r8
0x180004afc  mov     rdx, rcx
0x180004aff  xor     r15d, r15d
0x180004b02  mov     [r8], r15
0x180004b05  mov     esi, 7FFFFFFEh
0x180004b0a  mov     eax, esi
0x180004b0c  mov     edi, 104h
0x180004b11  mov     r9d, edi
0x180004b14  lea     r8, [rsp+290h+Name]
0x180004b19  nop     dword ptr [rax+00000000h]
0x180004b20  test    rax, rax
0x180004b23  jz      short loc_180004B42
0x180004b25  movzx   ecx, word ptr [rdx]
0x180004b28  test    cx, cx
0x180004b2b  jz      short loc_180004B42
0x180004b2d  add     rdx, 2
0x180004b31  mov     [r8], cx
0x180004b35  add     r8, 2
0x180004b39  dec     rax
0x180004b3c  sub     r9, 1
0x180004b40  jnz     short loc_180004B20
0x180004b42  lea     rcx, [r8-2]
0x180004b46  test    r9, r9
0x180004b49  cmovnz  rcx, r8
0x180004b4d  mov     [rcx], r15w
0x180004b51  mov     rcx, rdi
0x180004b54  lea     rax, [rsp+290h+Name]
0x180004b59  nop     dword ptr [rax+00000000h]
0x180004b60  cmp     [rax], r15w
0x180004b64  jz      short loc_180004B70
0x180004b66  add     rax, 2
0x180004b6a  sub     rcx, 1
0x180004b6e  jnz     short loc_180004B60
0x180004b70  mov     r9, rdi
0x180004b73  sub     r9, rcx
0x180004b76  test    rcx, rcx
0x180004b79  cmovz   r9, r15
0x180004b7d  jz      short loc_180004BC7
0x180004b7f  mov     rcx, rsi
0x180004b82  lea     rdx, aP0; "_p0"
0x180004b89  mov     r8, rdi
0x180004b8c  sub     r8, r9
0x180004b8f  lea     r9, [rsp+r9*2+290h+Name]
0x180004b94  jz      short loc_180004BB8
0x180004b96  test    rcx, rcx
0x180004b99  jz      short loc_180004BB8
0x180004b9b  movzx   eax, word ptr [rdx]
0x180004b9e  test    ax, ax
0x180004ba1  jz      short loc_180004BB8
0x180004ba3  add     rdx, 2
0x180004ba7  mov     [r9], ax
0x180004bab  add     r9, 2
0x180004baf  dec     rcx
0x180004bb2  sub     r8, 1
0x180004bb6  jnz     short loc_180004B96
0x180004bb8  lea     rcx, [r9-2]
0x180004bbc  test    r8, r8
0x180004bbf  cmovnz  rcx, r9
0x180004bc3  mov     [rcx], r15w
0x180004bc7  lea     r8, [rsp+290h+Name]; lpName
0x180004bcc  xor     edx, edx; bInheritHandle
0x180004bce  mov     ecx, 1F0003h; dwDesiredAccess
0x180004bd3  call    cs:__imp_OpenSemaphoreW
0x180004bd9  mov     [rsp+290h+hHandle], rax; int
0x180004bde  mov     rcx, [rsp+290h+hHandle]; hHandle
0x180004be3  test    rcx, rcx
0x180004be6  jnz     short loc_180004C41
0x180004be8  call    cs:__imp_GetLastError
0x180004bee  cmp     eax, 2
0x180004bf1  jz      loc_180004DDD
0x180004bf7  mov     rcx, [rbp+198h]; this
0x180004bfe  lea     r8, aWil; "wil"
0x180004c05  mov     edx, 0D0h; void *
0x180004c0a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180004c0f  mov     ebx, eax
0x180004c11  mov     rcx, [rsp+290h+hHandle]; this
0x180004c16  test    rcx, rcx
0x180004c19  jz      short loc_180004C20
0x180004c1b  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180004c20  mov     eax, ebx
0x180004c22  mov     rcx, [rbp+190h+var_40]
0x180004c29  xor     rcx, rsp; StackCookie
0x180004c2c  call    __security_check_cookie
0x180004c31  add     rsp, 268h
0x180004c38  pop     r15
0x180004c3a  pop     r14
0x180004c3c  pop     rdi
0x180004c3d  pop     rsi
0x180004c3e  pop     rbx
0x180004c3f  pop     rbp
0x180004c40  retn
0x180004c41  mov     [rsp+290h+var_264], r15d
0x180004c46  mov     [rsp+290h+var_268], r15d
0x180004c4b  lea     rdx, [rsp+290h+var_264]; int *
0x180004c50  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180004c55  mov     ebx, eax
0x180004c57  test    eax, eax
0x180004c59  js      loc_180004D7C
0x180004c5f  mov     rcx, rdi
0x180004c62  lea     rax, [rsp+290h+Name]
0x180004c67  cmp     word ptr [rax], 0
0x180004c6b  jz      short loc_180004C77
0x180004c6d  add     rax, 2
0x180004c71  sub     rcx, 1
0x180004c75  jnz     short loc_180004C67
0x180004c77  mov     rdx, rdi
0x180004c7a  sub     rdx, rcx
0x180004c7d  test    rcx, rcx
0x180004c80  cmovz   rdx, r15
0x180004c84  jz      short loc_180004CD1
0x180004c86  lea     rcx, asc_1800457F8; "h"
0x180004c8d  sub     rdi, rdx
0x180004c90  lea     r8, [rsp+290h+Name]
0x180004c95  lea     r8, [r8+rdx*2]
0x180004c99  jz      short loc_180004CC2
0x180004c9b  nop     dword ptr [rax+rax+00h]
0x180004ca0  test    rsi, rsi
0x180004ca3  jz      short loc_180004CC2
0x180004ca5  movzx   eax, word ptr [rcx]
0x180004ca8  test    ax, ax
0x180004cab  jz      short loc_180004CC2
0x180004cad  add     rcx, 2
0x180004cb1  mov     [r8], ax
0x180004cb5  add     r8, 2
0x180004cb9  dec     rsi
0x180004cbc  sub     rdi, 1
0x180004cc0  jnz     short loc_180004CA0
0x180004cc2  lea     rdx, [r8-2]
0x180004cc6  test    rdi, rdi
0x180004cc9  cmovnz  rdx, r8
0x180004ccd  mov     [rdx], r15w
0x180004cd1  lea     r8, [rsp+290h+Name]; lpName
0x180004cd6  xor     edx, edx; bInheritHandle
0x180004cd8  mov     ecx, 1F0003h; dwDesiredAccess
0x180004cdd  call    cs:__imp_OpenSemaphoreW
0x180004ce3  mov     [rsp+290h+var_260], rax
0x180004ce8  mov     rcx, [rsp+290h+var_260]; hHandle
0x180004ced  test    rcx, rcx
0x180004cf0  jz      short loc_180004D3F
0x180004cf2  lea     rdx, [rsp+290h+var_268]; int *
0x180004cf7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180004cfc  mov     ebx, eax
0x180004cfe  test    eax, eax
0x180004d00  js      loc_180004DA7
0x180004d06  mov     rcx, [rsp+290h+var_260]; this
0x180004d0b  test    rcx, rcx
0x180004d0e  jz      short loc_180004D15
0x180004d10  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180004d15  movsxd  rcx, [rsp+290h+var_268]
0x180004d1a  shl     rcx, 1Fh
0x180004d1e  movsxd  rax, [rsp+290h+var_264]
0x180004d23  or      rcx, rax
0x180004d26  mov     [r14], rcx
0x180004d29  mov     rcx, [rsp+290h+hHandle]; this
0x180004d2e  test    rcx, rcx
0x180004d31  jz      short loc_180004D38
0x180004d33  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180004d38  xor     eax, eax
0x180004d3a  jmp     loc_180004C22
0x180004d3f  mov     rcx, [rbp+198h]; this
0x180004d46  lea     r8, aWil; "wil"
0x180004d4d  mov     edx, 0DCh; void *
0x180004d52  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180004d57  mov     ebx, eax
0x180004d59  mov     rcx, [rsp+290h+var_260]; this
0x180004d5e  test    rcx, rcx
0x180004d61  jz      short loc_180004D69
0x180004d63  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180004d68  nop
0x180004d69  mov     rcx, [rsp+290h+hHandle]
0x180004d6e  test    rcx, rcx
0x180004d71  jz      loc_180004C20
0x180004d77  jmp     loc_180004C1B
0x180004d7c  mov     rcx, [rbp+198h]; this
0x180004d83  mov     r9d, ebx; char *
0x180004d86  lea     r8, aWil; "wil"
0x180004d8d  mov     edx, 0D6h; void *
0x180004d92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004d97  nop
0x180004d98  lea     rcx, [rsp+290h+hHandle]
0x180004d9d  call    ??1?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAA@XZ
0x180004da2  jmp     loc_180004C20
0x180004da7  mov     rcx, [rbp+198h]; this
0x180004dae  mov     r9d, ebx; char *
0x180004db1  lea     r8, aWil; "wil"
0x180004db8  mov     edx, 0DEh; void *
0x180004dbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004dc2  nop
0x180004dc3  lea     rcx, [rsp+290h+var_260]
0x180004dc8  call    ??1?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAA@XZ
0x180004dcd  nop
0x180004dce  lea     rcx, [rsp+290h+hHandle]
0x180004dd3  call    ??1?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAA@XZ
0x180004dd8  jmp     loc_180004C20
0x180004ddd  lea     rcx, [rsp+290h+hHandle]
0x180004de2  call    ??1?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAA@XZ
0x180004de7  xor     eax, eax
0x180004de9  jmp     loc_180004C22
```
