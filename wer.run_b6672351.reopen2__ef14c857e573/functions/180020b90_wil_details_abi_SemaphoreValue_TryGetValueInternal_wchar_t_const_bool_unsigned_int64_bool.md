# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x180020b90`
- end: `0x180020e01`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `625`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18002099c`
- `0x18003f91c`

## callees

- `0x180020b90`
- `0x180020e08`
- `0x18002a1dc`
- `0x18003fb94`
- `0x180040cdc`
- `0x1800410bc`
- `0x180053300`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020da0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020da0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180020c93`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180020d08`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180020c93`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180020d08`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v5; // r10
  __int64 v6; // r9
  __int64 v7; // rdx
  bool v9; // zf
  WCHAR *v10; // rcx
  __int64 v11; // rdx
  WCHAR *v12; // rax
  __int64 v13; // r8
  const wchar_t *v14; // rcx
  WCHAR *v15; // rdx
  __int64 v16; // rax
  WCHAR *v17; // rcx
  HANDLE v18; // rax
  int ValueFromSemaphore; // eax
  unsigned int LastError; // ebx
  HANDLE v21; // rax
  const char *v22; // r9
  int v23; // eax
  const char *v25; // r9
  int v26; // [rsp+20h] [rbp-E0h] BYREF
  int v27; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v28; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v29[2]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  v4 = Name;
  v5 = 2147483646;
  *a3 = 0;
  v6 = 2147483646;
  v7 = 260;
  do
  {
    if ( !v6 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v6;
    --v7;
  }
  while ( v7 );
  v9 = v7 == 0;
  v10 = v4 - 1;
  v11 = 260;
  if ( !v9 )
    v10 = v4;
  v12 = Name;
  *v10 = 0;
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
    v14 = L"_p0";
    v15 = &Name[v13];
    v16 = 260 - v13;
    if ( v13 != 260 )
    {
      do
      {
        if ( !v5 )
          break;
        if ( !*v14 )
          break;
        *v15++ = *v14++;
        --v5;
        --v16;
      }
      while ( v16 );
    }
    v17 = v15 - 1;
    if ( v16 )
      v17 = v15;
    *v17 = 0;
  }
  v18 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v29[0] = v18;
  if ( v18 )
  {
    v27 = 0;
    v26 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v18, &v27);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore >= 0 )
    {
      StringCchCatW(Name, 0x104u, L"h");
      v21 = OpenSemaphoreW(0x1F0003u, 0, Name);
      v28 = v21;
      if ( v21 )
      {
        v23 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v21, &v26);
        LastError = v23;
        if ( v23 >= 0 )
        {
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v28);
          *a3 = v27 | (unsigned __int64)((__int64)v26 << 31);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v29);
          return 0;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xDE,
          (unsigned int)"wil",
          (const char *)(unsigned int)v23,
          v26);
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v22);
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v28);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v26);
    }
    goto LABEL_29;
  }
  if ( GetLastError() == 2 )
  {
    LastError = 0;
LABEL_29:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v29);
    return LastError;
  }
  return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v25);
}

```

## disassembly

```asm
0x180020b90  mov     [rsp-8+arg_0], rbx
0x180020b95  mov     [rsp-8+arg_8], rsi
0x180020b9a  push    rbp
0x180020b9b  push    rdi
0x180020b9c  push    r15
0x180020b9e  lea     rbp, [rsp-160h]
0x180020ba6  sub     rsp, 260h
0x180020bad  mov     rax, cs:__security_cookie
0x180020bb4  xor     rax, rsp
0x180020bb7  mov     [rbp+170h+var_20], rax
0x180020bbe  xor     esi, esi
0x180020bc0  lea     rax, [rsp+270h+Name]
0x180020bc5  mov     r10d, 7FFFFFFEh
0x180020bcb  mov     [r8], rsi
0x180020bce  mov     r15d, 104h
0x180020bd4  mov     r9d, r10d
0x180020bd7  mov     edx, r15d
0x180020bda  mov     rdi, r8
0x180020bdd  test    r9, r9
0x180020be0  jz      short loc_180020C01
0x180020be2  movzx   r8d, word ptr [rcx]
0x180020be6  test    r8w, r8w
0x180020bea  jz      short loc_180020C01
0x180020bec  mov     [rax], r8w
0x180020bf0  add     rcx, 2
0x180020bf4  add     rax, 2
0x180020bf8  dec     r9
0x180020bfb  sub     rdx, 1
0x180020bff  jnz     short loc_180020BDD
0x180020c01  test    rdx, rdx
0x180020c04  lea     rcx, [rax-2]
0x180020c08  mov     rdx, r15
0x180020c0b  cmovnz  rcx, rax
0x180020c0f  lea     rax, [rsp+270h+Name]
0x180020c14  mov     [rcx], si
0x180020c17  cmp     [rax], si
0x180020c1a  jz      short loc_180020C26
0x180020c1c  add     rax, 2
0x180020c20  sub     rdx, 1
0x180020c24  jnz     short loc_180020C17
0x180020c26  mov     rcx, r15
0x180020c29  mov     rax, rdx
0x180020c2c  sub     rcx, rdx
0x180020c2f  neg     rax
0x180020c32  sbb     r8, r8
0x180020c35  and     r8, rcx
0x180020c38  test    rdx, rdx
0x180020c3b  jz      short loc_180020C87
0x180020c3d  mov     rax, r15
0x180020c40  lea     rdx, [rsp+270h+Name]
0x180020c45  lea     rcx, aP0; "_p0"
0x180020c4c  lea     rdx, [rdx+r8*2]
0x180020c50  sub     rax, r8
0x180020c53  jz      short loc_180020C79
0x180020c55  test    r10, r10
0x180020c58  jz      short loc_180020C79
0x180020c5a  movzx   r8d, word ptr [rcx]
0x180020c5e  test    r8w, r8w
0x180020c62  jz      short loc_180020C79
0x180020c64  mov     [rdx], r8w
0x180020c68  add     rcx, 2
0x180020c6c  add     rdx, 2
0x180020c70  dec     r10
0x180020c73  sub     rax, 1
0x180020c77  jnz     short loc_180020C55
0x180020c79  test    rax, rax
0x180020c7c  lea     rcx, [rdx-2]
0x180020c80  cmovnz  rcx, rdx
0x180020c84  mov     [rcx], si
0x180020c87  lea     r8, [rsp+270h+Name]; lpName
0x180020c8c  xor     edx, edx; bInheritHandle
0x180020c8e  mov     ecx, 1F0003h; dwDesiredAccess
0x180020c93  call    cs:__imp_OpenSemaphoreW
0x180020c9a  nop     dword ptr [rax+rax+00h]
0x180020c9f  mov     [rsp+270h+var_240], rax
0x180020ca4  test    rax, rax
0x180020ca7  jz      loc_180020DA0
0x180020cad  lea     rdx, [rsp+270h+var_24C]; int *
0x180020cb2  mov     [rsp+270h+var_24C], esi
0x180020cb6  mov     rcx, rax; hHandle
0x180020cb9  mov     [rsp+270h+var_250], esi; int
0x180020cbd  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180020cc2  mov     ebx, eax
0x180020cc4  test    eax, eax
0x180020cc6  jns     short loc_180020CE8
0x180020cc8  mov     rcx, [rbp+178h]; this
0x180020ccf  lea     r8, aWil; "wil"
0x180020cd6  mov     r9d, eax; char *
0x180020cd9  mov     edx, 0D6h; void *
0x180020cde  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020ce3  jmp     loc_180020DB3
0x180020ce8  lea     r8, asc_1800B8E48; "h"
0x180020cef  mov     rdx, r15; unsigned __int64
0x180020cf2  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180020cf7  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180020cfc  lea     r8, [rsp+270h+Name]; lpName
0x180020d01  xor     edx, edx; bInheritHandle
0x180020d03  mov     ecx, 1F0003h; dwDesiredAccess
0x180020d08  call    cs:__imp_OpenSemaphoreW
0x180020d0f  nop     dword ptr [rax+rax+00h]
0x180020d14  mov     [rsp+270h+var_248], rax
0x180020d19  test    rax, rax
0x180020d1c  jz      short loc_180020D7A
0x180020d1e  lea     rdx, [rsp+270h+var_250]; int *
0x180020d23  mov     rcx, rax; hHandle
0x180020d26  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180020d2b  mov     ebx, eax
0x180020d2d  test    eax, eax
0x180020d2f  jns     short loc_180020D4E
0x180020d31  mov     rcx, [rbp+178h]; this
0x180020d38  lea     r8, aWil; "wil"
0x180020d3f  mov     r9d, eax; char *
0x180020d42  mov     edx, 0DEh; void *
0x180020d47  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020d4c  jmp     short loc_180020D94
0x180020d4e  lea     rcx, [rsp+270h+var_248]
0x180020d53  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180020d58  movsxd  rax, [rsp+270h+var_24C]
0x180020d5d  movsxd  rcx, [rsp+270h+var_250]
0x180020d62  shl     rcx, 1Fh
0x180020d66  or      rcx, rax
0x180020d69  mov     [rdi], rcx
0x180020d6c  lea     rcx, [rsp+270h+var_240]
0x180020d71  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180020d76  xor     eax, eax
0x180020d78  jmp     short loc_180020DD9
0x180020d7a  mov     rcx, [rbp+178h]; this
0x180020d81  lea     r8, aWil; "wil"
0x180020d88  mov     edx, 0DCh; void *
0x180020d8d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180020d92  mov     ebx, eax
0x180020d94  lea     rcx, [rsp+270h+var_248]
0x180020d99  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180020d9e  jmp     short loc_180020DB3
0x180020da0  call    cs:__imp_GetLastError
0x180020da7  nop     dword ptr [rax+rax+00h]
0x180020dac  cmp     eax, 2
0x180020daf  jnz     short loc_180020DC1
0x180020db1  mov     ebx, esi
0x180020db3  lea     rcx, [rsp+270h+var_240]
0x180020db8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180020dbd  mov     eax, ebx
0x180020dbf  jmp     short loc_180020DD9
0x180020dc1  mov     rcx, [rbp+178h]; this
0x180020dc8  lea     r8, aWil; "wil"
0x180020dcf  mov     edx, 0D0h; void *
0x180020dd4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180020dd9  mov     rcx, [rbp+170h+var_20]
0x180020de0  xor     rcx, rsp; StackCookie
0x180020de3  call    __security_check_cookie
0x180020de8  lea     r11, [rsp+270h+var_10]
0x180020df0  mov     rbx, [r11+20h]
0x180020df4  mov     rsi, [r11+28h]
0x180020df8  mov     rsp, r11
0x180020dfb  pop     r15
0x180020dfd  pop     rdi
0x180020dfe  pop     rbp
0x180020dff  retn
```
