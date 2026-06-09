# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180008af0`
- end: `0x180008db0`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `704`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180008810`
- `0x1800088cc`

## callees

- `0x180008af0`
- `0x180008db8`
- `0x18000a3b0`
- `0x18000a9a8`
- `0x18000b1cc`
- `0x18000b40c`
- `0x18000c990`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008bfc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008cc9`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008bfc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008cc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d57`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  __int64 v5; // r14
  __int64 v6; // r9
  __int64 v7; // rdx
  WCHAR *v8; // rax
  WCHAR v9; // r8
  WCHAR *v10; // rcx
  __int64 v11; // rdx
  WCHAR *v12; // rax
  __int64 v13; // r8
  __int64 v14; // rcx
  const unsigned __int16 *v15; // r9
  __int64 v16; // rax
  WCHAR *v17; // rdx
  unsigned __int16 v18; // r8
  WCHAR *v19; // rcx
  wil::details *v20; // rax
  wil::details *v21; // rdi
  int ValueFromSemaphore; // eax
  unsigned int v23; // r8d
  unsigned int LastError; // ebx
  __int64 v25; // rdx
  WCHAR *v26; // rax
  __int64 v27; // r8
  const unsigned __int16 *v28; // rcx
  __int64 v29; // rsi
  WCHAR *v30; // rax
  unsigned __int16 v31; // dx
  WCHAR *v32; // rdx
  wil::details *v33; // rax
  unsigned int v34; // r8d
  const char *v35; // r9
  wil::details *v36; // rbx
  int v37; // eax
  void *v38; // rdx
  unsigned int v39; // r8d
  int v40; // esi
  void *v41; // rdx
  void *v43; // rdx
  unsigned int v44; // r8d
  const char *v45; // r9
  int v46; // [rsp+20h] [rbp-E0h] BYREF
  int v47; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v48; // [rsp+28h] [rbp-D8h] BYREF
  wil::details *v49; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a3 = 0;
  v5 = 2147483646;
  v6 = 2147483646;
  v7 = 260;
  v8 = Name;
  do
  {
    if ( !v6 )
      break;
    v9 = *a1;
    if ( !*a1 )
      break;
    ++a1;
    *v8++ = v9;
    --v6;
    --v7;
  }
  while ( v7 );
  v10 = v8 - 1;
  if ( v7 )
    v10 = v8;
  *v10 = 0;
  v11 = 260;
  v12 = Name;
  do
  {
    if ( !*v12 )
      break;
    ++v12;
    --v11;
  }
  while ( v11 );
  v13 = (260 - v11) & -(__int64)(v11 != 0);
  if ( v11 )
  {
    v14 = 2147483646;
    v15 = L"_p0";
    v16 = 260 - v13;
    v17 = &Name[v13];
    if ( v13 != 260 )
    {
      do
      {
        if ( !v14 )
          break;
        v18 = *v15;
        if ( !*v15 )
          break;
        ++v15;
        *v17++ = v18;
        --v14;
        --v16;
      }
      while ( v16 );
    }
    v19 = v17 - 1;
    if ( v16 )
      v19 = v17;
    *v19 = 0;
  }
  v20 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v21 = v20;
  v49 = v20;
  if ( v20 )
  {
    v47 = 0;
    v46 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v20, &v47);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore >= 0 )
    {
      v25 = 260;
      v26 = Name;
      do
      {
        if ( !*v26 )
          break;
        ++v26;
        --v25;
      }
      while ( v25 );
      v27 = (260 - v25) & -(__int64)(v25 != 0);
      if ( v25 )
      {
        v28 = L"h";
        v29 = 260 - v27;
        v30 = &Name[v27];
        if ( 260 != v27 )
        {
          do
          {
            if ( !v5 )
              break;
            v31 = *v28;
            if ( !*v28 )
              break;
            ++v28;
            *v30++ = v31;
            --v5;
            --v29;
          }
          while ( v29 );
        }
        v32 = v30 - 1;
        if ( v29 )
          v32 = v30;
        *v32 = 0;
      }
      v33 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
      v36 = v33;
      v48 = v33;
      if ( !v33 )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v34, v35);
        wil::details::CloseHandle(v21, v43);
        return LastError;
      }
      v37 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v33, &v46);
      v40 = v37;
      if ( v37 >= 0 )
      {
        wil::details::CloseHandle(v36, v38);
        *a3 = v47 | (unsigned __int64)((__int64)v46 << 31);
        wil::details::CloseHandle(v21, v41);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v39, (const char *)(unsigned int)v37, v46);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v48);
      LastError = v40;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v23, (const char *)(unsigned int)ValueFromSemaphore, v46);
    }
LABEL_39:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v49);
    return LastError;
  }
  if ( GetLastError() == 2 )
  {
    LastError = 0;
    goto LABEL_39;
  }
  return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v44, v45);
}

```

## disassembly

```asm
0x180008af0  mov     [rsp-8+arg_0], rbx
0x180008af5  mov     [rsp-8+arg_8], rsi
0x180008afa  push    rbp
0x180008afb  push    rdi
0x180008afc  push    r12
0x180008afe  push    r14
0x180008b00  push    r15
0x180008b02  lea     rbp, [rsp-160h]
0x180008b0a  sub     rsp, 260h
0x180008b11  mov     rax, cs:__security_cookie
0x180008b18  xor     rax, rsp
0x180008b1b  mov     [rbp+180h+var_30], rax
0x180008b22  mov     r15, r8
0x180008b25  xor     r12d, r12d
0x180008b28  mov     [r8], r12
0x180008b2b  mov     r14d, 7FFFFFFEh
0x180008b31  mov     r9d, r14d
0x180008b34  mov     esi, 104h
0x180008b39  mov     edx, esi
0x180008b3b  lea     rax, [rsp+280h+Name]
0x180008b40  test    r9, r9
0x180008b43  jz      short loc_180008B64
0x180008b45  movzx   r8d, word ptr [rcx]
0x180008b49  test    r8w, r8w
0x180008b4d  jz      short loc_180008B64
0x180008b4f  add     rcx, 2
0x180008b53  mov     [rax], r8w
0x180008b57  add     rax, 2
0x180008b5b  dec     r9
0x180008b5e  sub     rdx, 1
0x180008b62  jnz     short loc_180008B40
0x180008b64  lea     rcx, [rax-2]
0x180008b68  test    rdx, rdx
0x180008b6b  cmovnz  rcx, rax
0x180008b6f  mov     [rcx], r12w
0x180008b73  mov     rdx, rsi
0x180008b76  lea     rax, [rsp+280h+Name]
0x180008b7b  cmp     [rax], r12w
0x180008b7f  jz      short loc_180008B8B
0x180008b81  add     rax, 2
0x180008b85  sub     rdx, 1
0x180008b89  jnz     short loc_180008B7B
0x180008b8b  mov     rax, rdx
0x180008b8e  mov     rcx, rsi
0x180008b91  sub     rcx, rdx
0x180008b94  neg     rax
0x180008b97  sbb     r8, r8
0x180008b9a  and     r8, rcx
0x180008b9d  test    rdx, rdx
0x180008ba0  jz      short loc_180008BF0
0x180008ba2  mov     rcx, r14
0x180008ba5  lea     r9, aP0; "_p0"
0x180008bac  mov     rax, rsi
0x180008baf  sub     rax, r8
0x180008bb2  lea     rdx, [rsp+280h+Name]
0x180008bb7  lea     rdx, [rdx+r8*2]
0x180008bbb  jz      short loc_180008BE1
0x180008bbd  test    rcx, rcx
0x180008bc0  jz      short loc_180008BE1
0x180008bc2  movzx   r8d, word ptr [r9]
0x180008bc6  test    r8w, r8w
0x180008bca  jz      short loc_180008BE1
0x180008bcc  add     r9, 2
0x180008bd0  mov     [rdx], r8w
0x180008bd4  add     rdx, 2
0x180008bd8  dec     rcx
0x180008bdb  sub     rax, 1
0x180008bdf  jnz     short loc_180008BBD
0x180008be1  lea     rcx, [rdx-2]
0x180008be5  test    rax, rax
0x180008be8  cmovnz  rcx, rdx
0x180008bec  mov     [rcx], r12w
0x180008bf0  lea     r8, [rsp+280h+Name]; lpName
0x180008bf5  xor     edx, edx; bInheritHandle
0x180008bf7  mov     ecx, 1F0003h; dwDesiredAccess
0x180008bfc  call    cs:__imp_OpenSemaphoreW
0x180008c02  mov     rdi, rax
0x180008c05  mov     [rsp+280h+var_250], rax
0x180008c0a  test    rax, rax
0x180008c0d  jz      loc_180008D57
0x180008c13  mov     [rsp+280h+var_25C], r12d
0x180008c18  mov     [rsp+280h+var_260], r12d; int
0x180008c1d  lea     rdx, [rsp+280h+var_25C]; int *
0x180008c22  mov     rcx, rax; hHandle
0x180008c25  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180008c2a  mov     ebx, eax
0x180008c2c  test    eax, eax
0x180008c2e  jns     short loc_180008C49
0x180008c30  mov     rcx, [rbp+188h]; this
0x180008c37  mov     r9d, eax; char *
0x180008c3a  mov     edx, 0D6h; void *
0x180008c3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008c44  jmp     loc_180008D65
0x180008c49  mov     rdx, rsi
0x180008c4c  lea     rax, [rsp+280h+Name]
0x180008c51  cmp     [rax], r12w
0x180008c55  jz      short loc_180008C61
0x180008c57  add     rax, 2
0x180008c5b  sub     rdx, 1
0x180008c5f  jnz     short loc_180008C51
0x180008c61  mov     rax, rdx
0x180008c64  mov     rcx, rsi
0x180008c67  sub     rcx, rdx
0x180008c6a  neg     rax
0x180008c6d  sbb     r8, r8
0x180008c70  and     r8, rcx
0x180008c73  test    rdx, rdx
0x180008c76  jz      short loc_180008CBD
0x180008c78  lea     rcx, asc_18001D200; "h"
0x180008c7f  sub     rsi, r8
0x180008c82  lea     rax, [rsp+280h+Name]
0x180008c87  lea     rax, [rax+r8*2]
0x180008c8b  jz      short loc_180008CAE
0x180008c8d  test    r14, r14
0x180008c90  jz      short loc_180008CAE
0x180008c92  movzx   edx, word ptr [rcx]
0x180008c95  test    dx, dx
0x180008c98  jz      short loc_180008CAE
0x180008c9a  add     rcx, 2
0x180008c9e  mov     [rax], dx
0x180008ca1  add     rax, 2
0x180008ca5  dec     r14
0x180008ca8  sub     rsi, 1
0x180008cac  jnz     short loc_180008C8D
0x180008cae  lea     rdx, [rax-2]
0x180008cb2  test    rsi, rsi
0x180008cb5  cmovnz  rdx, rax
0x180008cb9  mov     [rdx], r12w
0x180008cbd  lea     r8, [rsp+280h+Name]; lpName
0x180008cc2  xor     edx, edx; bInheritHandle
0x180008cc4  mov     ecx, 1F0003h; dwDesiredAccess
0x180008cc9  call    cs:__imp_OpenSemaphoreW
0x180008ccf  mov     rbx, rax
0x180008cd2  mov     [rsp+280h+var_258], rax
0x180008cd7  test    rax, rax
0x180008cda  jz      short loc_180008D3A
0x180008cdc  lea     rdx, [rsp+280h+var_260]; int *
0x180008ce1  mov     rcx, rax; hHandle
0x180008ce4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180008ce9  mov     esi, eax
0x180008ceb  test    eax, eax
0x180008ced  jns     short loc_180008D12
0x180008cef  mov     rcx, [rbp+188h]; this
0x180008cf6  mov     r9d, eax; char *
0x180008cf9  mov     edx, 0DEh; void *
0x180008cfe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008d03  nop
0x180008d04  lea     rcx, [rsp+280h+var_258]
0x180008d09  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008d0e  mov     ebx, esi
0x180008d10  jmp     short loc_180008D65
0x180008d12  mov     rcx, rbx; this
0x180008d15  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180008d1a  movsxd  rcx, [rsp+280h+var_260]
0x180008d1f  shl     rcx, 1Fh
0x180008d23  movsxd  rax, [rsp+280h+var_25C]
0x180008d28  or      rcx, rax
0x180008d2b  mov     [r15], rcx
0x180008d2e  mov     rcx, rdi; this
0x180008d31  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180008d36  xor     eax, eax
0x180008d38  jmp     short loc_180008D85
0x180008d3a  mov     rcx, [rbp+188h]; this
0x180008d41  mov     edx, 0DCh; void *
0x180008d46  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008d4b  mov     ebx, eax
0x180008d4d  mov     rcx, rdi; this
0x180008d50  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180008d55  jmp     short loc_180008D6F
0x180008d57  call    cs:__imp_GetLastError
0x180008d5d  cmp     eax, 2
0x180008d60  jnz     short loc_180008D73
0x180008d62  mov     ebx, r12d
0x180008d65  lea     rcx, [rsp+280h+var_250]
0x180008d6a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008d6f  mov     eax, ebx
0x180008d71  jmp     short loc_180008D85
0x180008d73  mov     rcx, [rbp+188h]; this
0x180008d7a  mov     edx, 0D0h; void *
0x180008d7f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008d84  nop
0x180008d85  mov     rcx, [rbp+180h+var_30]
0x180008d8c  xor     rcx, rsp; StackCookie
0x180008d8f  call    __security_check_cookie
0x180008d94  lea     r11, [rsp+280h+var_20]
0x180008d9c  mov     rbx, [r11+30h]
0x180008da0  mov     rsi, [r11+38h]
0x180008da4  mov     rsp, r11
0x180008da7  pop     r15
0x180008da9  pop     r14
0x180008dab  pop     r12
0x180008dad  pop     rdi
0x180008dae  pop     rbp
0x180008daf  retn
```
