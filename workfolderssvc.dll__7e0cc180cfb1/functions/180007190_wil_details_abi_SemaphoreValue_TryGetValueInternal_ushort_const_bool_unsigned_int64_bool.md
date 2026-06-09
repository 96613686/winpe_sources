# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180007190`
- end: `0x180007342`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `434`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000711c`

## callees

- `0x180002ab0`
- `0x18000500c`
- `0x180005edc`
- `0x180006984`
- `0x1800069a4`
- `0x180006ed0`
- `0x180006f5c`
- `0x180007190`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x1800071f9`
- `KERNEL32!OpenSemaphoreW` at `0x18000728e`
- `KERNEL32!OpenSemaphoreW` at `0x1800071f9`
- `KERNEL32!OpenSemaphoreW` at `0x18000728e`
- `KERNEL32!GetLastError` at `0x180007209`
- `KERNEL32!GetLastError` at `0x180007209`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  HANDLE v5; // rax
  unsigned int v6; // r8d
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned int v10; // r8d
  HANDLE v11; // rax
  unsigned int v12; // r8d
  const char *v13; // r9
  int v14; // eax
  unsigned int v15; // r8d
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v19; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v20[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20[0] = v5;
  if ( v5 )
  {
    v18 = 0;
    v17 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v18);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v10, (const char *)(unsigned int)ValueFromSemaphore, v17);
      goto LABEL_12;
    }
    StringCchCatW(Name, 0x104u, L"h");
    v11 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v19 = v11;
    if ( !v11 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v12, v13);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
      goto LABEL_12;
    }
    v14 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v11, &v17);
    LastError = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v15, (const char *)(unsigned int)v14, v17);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
      goto LABEL_12;
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
    *a3 = v18 | (unsigned __int64)((__int64)v17 << 31);
LABEL_11:
    LastError = 0;
    goto LABEL_12;
  }
  if ( GetLastError() == 2 )
    goto LABEL_11;
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v6, v7);
LABEL_12:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v20);
  return LastError;
}

```

## disassembly

```asm
0x180007190  mov     [rsp-8+arg_8], rbx
0x180007195  push    rbp
0x180007196  push    rdi
0x180007197  push    r14
0x180007199  lea     rbp, [rsp-160h]
0x1800071a1  sub     rsp, 260h
0x1800071a8  mov     rax, cs:__security_cookie
0x1800071af  xor     rax, rsp
0x1800071b2  mov     [rbp+170h+var_20], rax
0x1800071b9  mov     rdi, r8
0x1800071bc  mov     qword ptr [r8], 0
0x1800071c3  mov     r8, rcx; unsigned __int16 *
0x1800071c6  mov     r14d, 104h
0x1800071cc  mov     edx, r14d; unsigned __int64
0x1800071cf  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800071d4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800071d9  lea     r8, aP0; "_p0"
0x1800071e0  mov     edx, r14d; unsigned __int64
0x1800071e3  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800071e8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800071ed  lea     r8, [rsp+270h+Name]; lpName
0x1800071f2  xor     edx, edx; bInheritHandle
0x1800071f4  mov     ecx, 1F0003h; dwDesiredAccess
0x1800071f9  call    cs:__imp_OpenSemaphoreW
0x1800071ff  mov     [rsp+270h+var_240], rax
0x180007204  test    rax, rax
0x180007207  jnz     short loc_180007231
0x180007209  call    cs:__imp_GetLastError
0x18000720f  cmp     eax, 2
0x180007212  jnz     short loc_180007219
0x180007214  jmp     loc_180007311
0x180007219  mov     rcx, [rbp+178h]; this
0x180007220  mov     edx, 0D0h; void *
0x180007225  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000722a  mov     ebx, eax
0x18000722c  jmp     loc_180007313
0x180007231  mov     [rsp+270h+var_24C], 0
0x180007239  mov     [rsp+270h+var_250], 0; int
0x180007241  lea     rdx, [rsp+270h+var_24C]; int *
0x180007246  mov     rcx, rax; hHandle
0x180007249  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000724e  mov     ebx, eax
0x180007250  test    eax, eax
0x180007252  jns     short loc_18000726E
0x180007254  mov     rcx, [rbp+178h]; this
0x18000725b  mov     r9d, eax; char *
0x18000725e  mov     edx, 0D6h; void *
0x180007263  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007268  nop
0x180007269  jmp     loc_180007313
0x18000726e  lea     r8, asc_18014D770; "h"
0x180007275  mov     rdx, r14; unsigned __int64
0x180007278  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000727d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007282  lea     r8, [rsp+270h+Name]; lpName
0x180007287  xor     edx, edx; bInheritHandle
0x180007289  mov     ecx, 1F0003h; dwDesiredAccess
0x18000728e  call    cs:__imp_OpenSemaphoreW
0x180007294  mov     [rsp+270h+var_248], rax
0x180007299  test    rax, rax
0x18000729c  jnz     short loc_1800072BE
0x18000729e  mov     rcx, [rbp+178h]; this
0x1800072a5  mov     edx, 0DCh; void *
0x1800072aa  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800072af  mov     ebx, eax
0x1800072b1  lea     rcx, [rsp+270h+var_248]
0x1800072b6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800072bb  nop
0x1800072bc  jmp     short loc_180007313
0x1800072be  lea     rdx, [rsp+270h+var_250]; int *
0x1800072c3  mov     rcx, rax; hHandle
0x1800072c6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800072cb  mov     ebx, eax
0x1800072cd  test    eax, eax
0x1800072cf  jns     short loc_1800072F3
0x1800072d1  mov     rcx, [rbp+178h]; this
0x1800072d8  mov     r9d, eax; char *
0x1800072db  mov     edx, 0DEh; void *
0x1800072e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800072e5  nop
0x1800072e6  lea     rcx, [rsp+270h+var_248]
0x1800072eb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800072f0  nop
0x1800072f1  jmp     short loc_180007313
0x1800072f3  lea     rcx, [rsp+270h+var_248]
0x1800072f8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800072fd  movsxd  rcx, [rsp+270h+var_250]
0x180007302  shl     rcx, 1Fh
0x180007306  movsxd  rax, [rsp+270h+var_24C]
0x18000730b  or      rcx, rax
0x18000730e  mov     [rdi], rcx
0x180007311  xor     ebx, ebx
0x180007313  lea     rcx, [rsp+270h+var_240]
0x180007318  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000731d  mov     eax, ebx
0x18000731f  mov     rcx, [rbp+170h+var_20]
0x180007326  xor     rcx, rsp; StackCookie
0x180007329  call    __security_check_cookie
0x18000732e  mov     rbx, [rsp+270h+arg_8]
0x180007336  add     rsp, 260h
0x18000733d  pop     r14
0x18000733f  pop     rdi
0x180007340  pop     rbp
0x180007341  retn
```
