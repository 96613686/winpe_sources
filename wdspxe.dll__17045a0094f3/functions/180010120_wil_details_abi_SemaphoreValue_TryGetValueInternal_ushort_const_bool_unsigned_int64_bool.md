# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180010120`
- end: `0x1800103d9`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `697`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000a204`
- `0x18000a5fc`

## callees

- `0x18000c14c`
- `0x18000e9f8`
- `0x18000ea18`
- `0x18000fc3c`
- `0x180010120`
- `0x180010a48`
- `0x180011a90`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800101d3`
- `KERNEL32!GetLastError` at `0x1800101d3`
- `KERNEL32!CloseHandle` at `0x180010232`
- `KERNEL32!CloseHandle` at `0x180010291`
- `KERNEL32!CloseHandle` at `0x1800102d1`
- `KERNEL32!CloseHandle` at `0x1800102e8`
- `KERNEL32!CloseHandle` at `0x180010303`
- `KERNEL32!CloseHandle` at `0x18001032e`
- `KERNEL32!CloseHandle` at `0x180010232`
- `KERNEL32!CloseHandle` at `0x180010291`
- `KERNEL32!CloseHandle` at `0x1800102d1`
- `KERNEL32!CloseHandle` at `0x1800102e8`
- `KERNEL32!CloseHandle` at `0x180010303`
- `KERNEL32!CloseHandle` at `0x18001032e`
- `KERNEL32!OpenSemaphoreW` at `0x1800101bf`
- `KERNEL32!OpenSemaphoreW` at `0x180010267`
- `KERNEL32!OpenSemaphoreW` at `0x1800101bf`
- `KERNEL32!OpenSemaphoreW` at `0x180010267`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        char *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rdx
  signed __int64 v5; // rcx
  __int64 v7; // r9
  WCHAR v8; // ax
  WCHAR *v9; // rax
  HANDLE v10; // rax
  void *v11; // rbx
  unsigned int v12; // r8d
  const char *v13; // r9
  int ValueFromSemaphore; // eax
  unsigned __int64 v16; // rdx
  unsigned int v17; // r8d
  unsigned int LastError; // edi
  unsigned int v19; // r8d
  const char *v20; // r9
  HANDLE v21; // rax
  unsigned int v22; // r8d
  const char *v23; // r9
  void *v24; // rdi
  unsigned int v25; // r8d
  const char *v26; // r9
  int v27; // eax
  unsigned int v28; // r8d
  unsigned int v29; // esi
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  unsigned int v36; // r8d
  const char *v37; // r9
  int v38; // [rsp+28h] [rbp-E0h] BYREF
  int v39[3]; // [rsp+2Ch] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+38h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+270h] [rbp+168h]

  *a3 = 0;
  v4 = Name;
  v5 = a1 - (char *)Name;
  v7 = 260;
  do
  {
    if ( v7 == -2147483386 )
      break;
    v8 = *(WCHAR *)((char *)v4 + v5);
    if ( !v8 )
      break;
    *v4++ = v8;
    --v7;
  }
  while ( v7 );
  v9 = v4 - 1;
  if ( v7 )
    v9 = v4;
  *v9 = 0;
  StringCchCatW(Name, (unsigned __int64)v4, L"_p0");
  v10 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v11 = v10;
  if ( !v10 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xCD, v12, v13);
    return 0;
  }
  v39[0] = 0;
  v38 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, v39);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD3, v17, (const char *)(unsigned int)ValueFromSemaphore, v38);
    if ( !CloseHandle(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v19, v20);
    return LastError;
  }
  StringCchCatW(Name, v16, L"h");
  v21 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v24 = v21;
  if ( !v21 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD9, v22, v23);
    if ( !CloseHandle(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v25, v26);
    return LastError;
  }
  v27 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v21, &v38);
  v29 = v27;
  if ( v27 >= 0 )
  {
    if ( !CloseHandle(v24) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v34, v35);
    *a3 = v39[0] | (unsigned __int64)((__int64)v38 << 31);
    if ( !CloseHandle(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v36, v37);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDB, v28, (const char *)(unsigned int)v27, v38);
  if ( !CloseHandle(v24) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v30, v31);
  if ( !CloseHandle(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v32, v33);
  return v29;
}

```

## disassembly

```asm
0x180010120  mov     rax, rsp
0x180010123  mov     [rax+8], rbx
0x180010127  mov     [rax+10h], rsi
0x18001012b  mov     [rax+20h], rdi
0x18001012f  push    rbp
0x180010130  push    r14
0x180010132  push    r15
0x180010134  lea     rbp, [rax-168h]
0x18001013b  sub     rsp, 250h
0x180010142  mov     rax, cs:__security_cookie
0x180010149  xor     rax, rsp
0x18001014c  mov     [rbp+160h+var_20], rax
0x180010153  xor     r15d, r15d
0x180010156  lea     rax, [rsp+260h+Name]
0x18001015b  mov     [r8], r15
0x18001015e  lea     rdx, [rsp+260h+Name]
0x180010163  sub     rcx, rax
0x180010166  mov     r14, r8
0x180010169  mov     r9d, 104h
0x18001016f  lea     rax, [r9+7FFFFEFAh]
0x180010176  test    rax, rax
0x180010179  jz      short loc_180010191
0x18001017b  movzx   eax, word ptr [rcx+rdx]
0x18001017f  test    ax, ax
0x180010182  jz      short loc_180010191
0x180010184  mov     [rdx], ax
0x180010187  add     rdx, 2; unsigned __int64
0x18001018b  sub     r9, 1
0x18001018f  jnz     short loc_18001016F
0x180010191  test    r9, r9
0x180010194  lea     rax, [rdx-2]
0x180010198  lea     r8, aP0; "_p0"
0x18001019f  cmovnz  rax, rdx
0x1800101a3  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800101a8  mov     [rax], r15w
0x1800101ac  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800101b1  mov     esi, 1F0003h
0x1800101b6  lea     r8, [rsp+260h+Name]; lpName
0x1800101bb  mov     ecx, esi; dwDesiredAccess
0x1800101bd  xor     edx, edx; bInheritHandle
0x1800101bf  call    cs:__imp_OpenSemaphoreW
0x1800101c6  nop     dword ptr [rax+rax+00h]
0x1800101cb  mov     rbx, rax
0x1800101ce  test    rax, rax
0x1800101d1  jnz     short loc_1800101FE
0x1800101d3  call    cs:__imp_GetLastError
0x1800101da  nop     dword ptr [rax+rax+00h]
0x1800101df  cmp     eax, 2
0x1800101e2  jz      loc_18001033E
0x1800101e8  mov     rcx, [rbp+168h]; this
0x1800101ef  mov     edx, 0CDh; void *
0x1800101f4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800101f9  jmp     loc_180010340
0x1800101fe  lea     rdx, [rsp+260h+var_23C]; int *
0x180010203  mov     [rsp+260h+var_23C], r15d
0x180010208  mov     rcx, rbx; hHandle
0x18001020b  mov     [rsp+260h+var_240], r15d; int
0x180010210  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180010215  mov     edi, eax
0x180010217  test    eax, eax
0x180010219  jns     short loc_18001024D
0x18001021b  mov     rcx, [rbp+168h]; this
0x180010222  mov     r9d, eax; char *
0x180010225  mov     edx, 0D3h; void *
0x18001022a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001022f  mov     rcx, rbx; hObject
0x180010232  call    cs:__imp_CloseHandle
0x180010239  nop     dword ptr [rax+rax+00h]
0x18001023e  test    eax, eax
0x180010240  jz      loc_180010391
0x180010246  mov     eax, edi
0x180010248  jmp     loc_180010340
0x18001024d  lea     r8, asc_180017258; "h"
0x180010254  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180010259  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001025e  lea     r8, [rsp+260h+Name]; lpName
0x180010263  xor     edx, edx; bInheritHandle
0x180010265  mov     ecx, esi; dwDesiredAccess
0x180010267  call    cs:__imp_OpenSemaphoreW
0x18001026e  nop     dword ptr [rax+rax+00h]
0x180010273  mov     rdi, rax
0x180010276  test    rax, rax
0x180010279  jnz     short loc_1800102A7
0x18001027b  mov     rcx, [rbp+168h]; this
0x180010282  mov     edx, 0D9h; void *
0x180010287  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001028c  mov     rcx, rbx; hObject
0x18001028f  mov     edi, eax
0x180010291  call    cs:__imp_CloseHandle
0x180010298  nop     dword ptr [rax+rax+00h]
0x18001029d  test    eax, eax
0x18001029f  jz      loc_18001037F
0x1800102a5  jmp     short loc_180010246
0x1800102a7  lea     rdx, [rsp+260h+var_240]; int *
0x1800102ac  mov     rcx, rdi; hHandle
0x1800102af  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800102b4  mov     esi, eax
0x1800102b6  test    eax, eax
0x1800102b8  jns     short loc_180010300
0x1800102ba  mov     rcx, [rbp+168h]; this
0x1800102c1  mov     r9d, eax; char *
0x1800102c4  mov     edx, 0DBh; void *
0x1800102c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800102ce  mov     rcx, rdi; hObject
0x1800102d1  call    cs:__imp_CloseHandle
0x1800102d8  nop     dword ptr [rax+rax+00h]
0x1800102dd  test    eax, eax
0x1800102df  jz      loc_1800103A3
0x1800102e5  mov     rcx, rbx; hObject
0x1800102e8  call    cs:__imp_CloseHandle
0x1800102ef  nop     dword ptr [rax+rax+00h]
0x1800102f4  test    eax, eax
0x1800102f6  jz      loc_1800103B5
0x1800102fc  mov     eax, esi
0x1800102fe  jmp     short loc_180010340
0x180010300  mov     rcx, rdi; hObject
0x180010303  call    cs:__imp_CloseHandle
0x18001030a  nop     dword ptr [rax+rax+00h]
0x18001030f  test    eax, eax
0x180010311  jz      loc_1800103C7
0x180010317  movsxd  rax, [rsp+260h+var_23C]
0x18001031c  movsxd  rcx, [rsp+260h+var_240]
0x180010321  shl     rcx, 1Fh
0x180010325  or      rcx, rax
0x180010328  mov     [r14], rcx
0x18001032b  mov     rcx, rbx; hObject
0x18001032e  call    cs:__imp_CloseHandle
0x180010335  nop     dword ptr [rax+rax+00h]
0x18001033a  test    eax, eax
0x18001033c  jz      short loc_18001036D
0x18001033e  xor     eax, eax
0x180010340  mov     rcx, [rbp+160h+var_20]
0x180010347  xor     rcx, rsp; StackCookie
0x18001034a  call    __security_check_cookie
0x18001034f  lea     r11, [rsp+260h+var_10]
0x180010357  mov     rbx, [r11+20h]
0x18001035b  mov     rsi, [r11+28h]
0x18001035f  mov     rdi, [r11+38h]
0x180010363  mov     rsp, r11
0x180010366  pop     r15
0x180010368  pop     r14
0x18001036a  pop     rbp
0x18001036b  retn
0x18001036d  mov     rcx, [rbp+168h]; this
0x180010374  mov     edx, 9CDh; void *
0x180010379  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001037f  mov     rcx, [rbp+168h]; this
0x180010386  mov     edx, 9CDh; void *
0x18001038b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010391  mov     rcx, [rbp+168h]; this
0x180010398  mov     edx, 9CDh; void *
0x18001039d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800103a3  mov     rcx, [rbp+168h]; this
0x1800103aa  mov     edx, 9CDh; void *
0x1800103af  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800103b5  mov     rcx, [rbp+168h]; this
0x1800103bc  mov     edx, 9CDh; void *
0x1800103c1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800103c7  mov     rcx, [rbp+168h]; this
0x1800103ce  mov     edx, 9CDh; void *
0x1800103d3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
