# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180013724`
- end: `0x180013982`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `606`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180018288`

## callees

- `0x180012c5c`
- `0x180013724`
- `0x180013988`
- `0x180018094`
- `0x1800180e4`
- `0x18001830c`
- `0x180019a20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180013827`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180013896`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180013827`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180013896`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013928`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013928`

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
  const unsigned __int16 *v14; // rcx
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
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
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
0x180013724  mov     [rsp-8+arg_0], rbx
0x180013729  mov     [rsp-8+arg_8], rsi
0x18001372e  push    rbp
0x18001372f  push    rdi
0x180013730  push    r15
0x180013732  lea     rbp, [rsp-160h]
0x18001373a  sub     rsp, 260h
0x180013741  mov     rax, cs:__security_cookie
0x180013748  xor     rax, rsp
0x18001374b  mov     [rbp+170h+var_20], rax
0x180013752  xor     esi, esi
0x180013754  lea     rax, [rsp+270h+Name]
0x180013759  mov     r10d, 7FFFFFFEh
0x18001375f  mov     [r8], rsi
0x180013762  mov     r15d, 104h
0x180013768  mov     r9d, r10d
0x18001376b  mov     edx, r15d
0x18001376e  mov     rdi, r8
0x180013771  test    r9, r9
0x180013774  jz      short loc_180013795
0x180013776  movzx   r8d, word ptr [rcx]
0x18001377a  test    r8w, r8w
0x18001377e  jz      short loc_180013795
0x180013780  mov     [rax], r8w
0x180013784  add     rcx, 2
0x180013788  add     rax, 2
0x18001378c  dec     r9
0x18001378f  sub     rdx, 1
0x180013793  jnz     short loc_180013771
0x180013795  test    rdx, rdx
0x180013798  lea     rcx, [rax-2]
0x18001379c  mov     rdx, r15
0x18001379f  cmovnz  rcx, rax
0x1800137a3  lea     rax, [rsp+270h+Name]
0x1800137a8  mov     [rcx], si
0x1800137ab  cmp     [rax], si
0x1800137ae  jz      short loc_1800137BA
0x1800137b0  add     rax, 2
0x1800137b4  sub     rdx, 1
0x1800137b8  jnz     short loc_1800137AB
0x1800137ba  mov     rcx, r15
0x1800137bd  mov     rax, rdx
0x1800137c0  sub     rcx, rdx
0x1800137c3  neg     rax
0x1800137c6  sbb     r8, r8
0x1800137c9  and     r8, rcx
0x1800137cc  test    rdx, rdx
0x1800137cf  jz      short loc_18001381B
0x1800137d1  mov     rax, r15
0x1800137d4  lea     rdx, [rsp+270h+Name]
0x1800137d9  lea     rcx, aP0; "_p0"
0x1800137e0  lea     rdx, [rdx+r8*2]
0x1800137e4  sub     rax, r8
0x1800137e7  jz      short loc_18001380D
0x1800137e9  test    r10, r10
0x1800137ec  jz      short loc_18001380D
0x1800137ee  movzx   r8d, word ptr [rcx]
0x1800137f2  test    r8w, r8w
0x1800137f6  jz      short loc_18001380D
0x1800137f8  mov     [rdx], r8w
0x1800137fc  add     rcx, 2
0x180013800  add     rdx, 2
0x180013804  dec     r10
0x180013807  sub     rax, 1
0x18001380b  jnz     short loc_1800137E9
0x18001380d  test    rax, rax
0x180013810  lea     rcx, [rdx-2]
0x180013814  cmovnz  rcx, rdx
0x180013818  mov     [rcx], si
0x18001381b  lea     r8, [rsp+270h+Name]; lpName
0x180013820  xor     edx, edx; bInheritHandle
0x180013822  mov     ecx, 1F0003h; dwDesiredAccess
0x180013827  call    cs:__imp_OpenSemaphoreW
0x18001382d  mov     [rsp+270h+var_240], rax
0x180013832  test    rax, rax
0x180013835  jz      loc_180013928
0x18001383b  lea     rdx, [rsp+270h+var_24C]; int *
0x180013840  mov     [rsp+270h+var_24C], esi
0x180013844  mov     rcx, rax; hHandle
0x180013847  mov     [rsp+270h+var_250], esi; int
0x18001384b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180013850  mov     ebx, eax
0x180013852  test    eax, eax
0x180013854  jns     short loc_180013876
0x180013856  mov     rcx, [rbp+178h]; this
0x18001385d  lea     r8, aWil; "wil"
0x180013864  mov     r9d, eax; char *
0x180013867  mov     edx, 0D6h; void *
0x18001386c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013871  jmp     loc_180013935
0x180013876  lea     r8, asc_180070BF0; "h"
0x18001387d  mov     rdx, r15; unsigned __int64
0x180013880  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180013885  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001388a  lea     r8, [rsp+270h+Name]; lpName
0x18001388f  xor     edx, edx; bInheritHandle
0x180013891  mov     ecx, 1F0003h; dwDesiredAccess
0x180013896  call    cs:__imp_OpenSemaphoreW
0x18001389c  mov     [rsp+270h+var_248], rax
0x1800138a1  test    rax, rax
0x1800138a4  jz      short loc_180013902
0x1800138a6  lea     rdx, [rsp+270h+var_250]; int *
0x1800138ab  mov     rcx, rax; hHandle
0x1800138ae  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800138b3  mov     ebx, eax
0x1800138b5  test    eax, eax
0x1800138b7  jns     short loc_1800138D6
0x1800138b9  mov     rcx, [rbp+178h]; this
0x1800138c0  lea     r8, aWil; "wil"
0x1800138c7  mov     r9d, eax; char *
0x1800138ca  mov     edx, 0DEh; void *
0x1800138cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800138d4  jmp     short loc_18001391C
0x1800138d6  lea     rcx, [rsp+270h+var_248]
0x1800138db  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800138e0  movsxd  rax, [rsp+270h+var_24C]
0x1800138e5  movsxd  rcx, [rsp+270h+var_250]
0x1800138ea  shl     rcx, 1Fh
0x1800138ee  or      rcx, rax
0x1800138f1  mov     [rdi], rcx
0x1800138f4  lea     rcx, [rsp+270h+var_240]
0x1800138f9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800138fe  xor     eax, eax
0x180013900  jmp     short loc_18001395B
0x180013902  mov     rcx, [rbp+178h]; this
0x180013909  lea     r8, aWil; "wil"
0x180013910  mov     edx, 0DCh; void *
0x180013915  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001391a  mov     ebx, eax
0x18001391c  lea     rcx, [rsp+270h+var_248]
0x180013921  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180013926  jmp     short loc_180013935
0x180013928  call    cs:__imp_GetLastError
0x18001392e  cmp     eax, 2
0x180013931  jnz     short loc_180013943
0x180013933  mov     ebx, esi
0x180013935  lea     rcx, [rsp+270h+var_240]
0x18001393a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001393f  mov     eax, ebx
0x180013941  jmp     short loc_18001395B
0x180013943  mov     rcx, [rbp+178h]; this
0x18001394a  lea     r8, aWil; "wil"
0x180013951  mov     edx, 0D0h; void *
0x180013956  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001395b  mov     rcx, [rbp+170h+var_20]
0x180013962  xor     rcx, rsp; StackCookie
0x180013965  call    __security_check_cookie
0x18001396a  lea     r11, [rsp+270h+var_10]
0x180013972  mov     rbx, [r11+20h]
0x180013976  mov     rsi, [r11+28h]
0x18001397a  mov     rsp, r11
0x18001397d  pop     r15
0x18001397f  pop     rdi
0x180013980  pop     rbp
0x180013981  retn
```
