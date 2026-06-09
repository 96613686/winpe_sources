# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18001a7c0`
- end: `0x18001aa88`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `712`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18002e3b0`

## callees

- `0x18001a7c0`
- `0x180027c44`
- `0x180027d94`
- `0x1800296d4`
- `0x18002c4ec`
- `0x18003fc30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001a85c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001a95c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001a85c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001a95c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a86e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a86e`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  __int64 v4; // rbp
  __int64 v5; // rsi
  WCHAR *v6; // r9
  __int64 v7; // rdx
  __int64 v8; // r10
  WCHAR *v10; // rcx
  __int64 v11; // rdx
  WCHAR *v12; // rax
  wil::details *v13; // rax
  wil::details *v14; // rbx
  unsigned int v15; // r8d
  const char *v16; // r9
  __int64 v18; // rcx
  _WORD *v19; // r9
  const unsigned __int16 *v20; // r8
  _WORD *v21; // rcx
  int ValueFromSemaphore; // eax
  unsigned int LastError; // edi
  WCHAR *v24; // rax
  wil::details *v25; // rax
  unsigned int v26; // r8d
  const char *v27; // r9
  wil::details *v28; // rdi
  void *v29; // rdx
  _WORD *v30; // r8
  const unsigned __int16 *v31; // rcx
  _WORD *v32; // rdx
  int v33; // eax
  void *v34; // rdx
  unsigned int v35; // esi
  void *v36; // rdx
  void *v37; // rdx
  void *v38; // rdx
  int v39; // [rsp+20h] [rbp-248h] BYREF
  int v40[3]; // [rsp+24h] [rbp-244h] BYREF
  WCHAR Name[260]; // [rsp+30h] [rbp-238h] BYREF
  _BYTE v42[8]; // [rsp+238h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  v4 = 2147483646;
  *a3 = 0;
  v5 = 260;
  v6 = Name;
  v7 = 2147483646;
  v8 = 260;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *v6++ = *a1++;
    --v7;
    --v8;
  }
  while ( v8 );
  v10 = v6 - 1;
  v11 = 260;
  if ( v8 )
    v10 = v6;
  *v10 = 0;
  v12 = Name;
  while ( *v12 )
  {
    ++v12;
    if ( !--v11 )
      goto LABEL_10;
  }
  v18 = 2147483646;
  v19 = &v42[-2 * v11];
  v20 = L"_p0";
  do
  {
    if ( !v18 )
      break;
    if ( !*v20 )
      break;
    *v19++ = *v20++;
    --v18;
    --v11;
  }
  while ( v11 );
  v21 = v19 - 1;
  if ( v11 )
    v21 = v19;
  *v21 = 0;
LABEL_10:
  v13 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v14 = v13;
  if ( !v13 )
  {
    if ( GetLastError() == 2 )
      return 0;
    else
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v15, v16);
  }
  v40[0] = 0;
  v39 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, v40);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v39);
    goto LABEL_26;
  }
  v24 = Name;
  while ( *v24 )
  {
    ++v24;
    if ( !--v5 )
      goto LABEL_24;
  }
  v30 = &v42[-2 * v5];
  v31 = L"h";
  do
  {
    if ( !v4 )
      break;
    if ( !*v31 )
      break;
    *v30++ = *v31++;
    --v4;
    --v5;
  }
  while ( v5 );
  v32 = v30 - 1;
  if ( v5 )
    v32 = v30;
  *v32 = 0;
LABEL_24:
  v25 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v28 = v25;
  if ( !v25 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v26, v27);
LABEL_26:
    wil::details::CloseHandle(v14, v29);
    return LastError;
  }
  v33 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v25, &v39);
  v35 = v33;
  if ( v33 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v33, v39);
    wil::details::CloseHandle(v28, v37);
    wil::details::CloseHandle(v14, v38);
    return v35;
  }
  else
  {
    wil::details::CloseHandle(v28, v34);
    *a3 = v40[0] | (unsigned __int64)((__int64)v39 << 31);
    wil::details::CloseHandle(v14, v36);
    return 0;
  }
}

```

## disassembly

```asm
0x18001a7c0  mov     [rsp+arg_8], rbx
0x18001a7c5  push    rbp
0x18001a7c6  push    rsi
0x18001a7c7  push    r14
0x18001a7c9  sub     rsp, 250h
0x18001a7d0  mov     rax, cs:__security_cookie
0x18001a7d7  xor     rax, rsp
0x18001a7da  mov     [rsp+268h+var_28], rax
0x18001a7e2  mov     ebp, 7FFFFFFEh
0x18001a7e7  mov     qword ptr [r8], 0
0x18001a7ee  mov     esi, 104h
0x18001a7f3  lea     r9, [rsp+268h+Name]
0x18001a7f8  mov     edx, ebp
0x18001a7fa  mov     r10d, esi
0x18001a7fd  mov     r14, r8
0x18001a800  test    rdx, rdx
0x18001a803  jz      short loc_18001A822
0x18001a805  movzx   eax, word ptr [rcx]
0x18001a808  test    ax, ax
0x18001a80b  jz      short loc_18001A822
0x18001a80d  mov     [r9], ax
0x18001a811  add     rcx, 2
0x18001a815  add     r9, 2
0x18001a819  dec     rdx
0x18001a81c  sub     r10, 1
0x18001a820  jnz     short loc_18001A800
0x18001a822  test    r10, r10
0x18001a825  lea     rcx, [r9-2]
0x18001a829  mov     rdx, rsi
0x18001a82c  cmovnz  rcx, r9
0x18001a830  xor     eax, eax
0x18001a832  mov     [rcx], ax
0x18001a835  lea     rax, [rsp+268h+Name]
0x18001a83a  nop     word ptr [rax+rax+00h]
0x18001a840  cmp     word ptr [rax], 0
0x18001a844  jz      short loc_18001A8B3
0x18001a846  add     rax, 2
0x18001a84a  sub     rdx, 1
0x18001a84e  jnz     short loc_18001A840
0x18001a850  lea     r8, [rsp+268h+Name]; lpName
0x18001a855  xor     edx, edx; bInheritHandle
0x18001a857  mov     ecx, 1F0003h; dwDesiredAccess
0x18001a85c  call    cs:__imp_OpenSemaphoreW
0x18001a862  mov     rbx, rax
0x18001a865  test    rax, rax
0x18001a868  jnz     loc_18001A909
0x18001a86e  call    cs:__imp_GetLastError
0x18001a874  cmp     eax, 2
0x18001a877  jz      loc_18001AA81
0x18001a87d  mov     rcx, [rsp+268h]; this
0x18001a885  mov     edx, 0D0h; void *
0x18001a88a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001a88f  mov     rcx, [rsp+268h+var_28]
0x18001a897  xor     rcx, rsp; StackCookie
0x18001a89a  call    __security_check_cookie
0x18001a89f  mov     rbx, [rsp+268h+arg_8]
0x18001a8a7  add     rsp, 250h
0x18001a8ae  pop     r14
0x18001a8b0  pop     rsi
0x18001a8b1  pop     rbp
0x18001a8b2  retn
0x18001a8b3  lea     rax, [rdx+rdx]
0x18001a8b7  mov     rcx, rbp
0x18001a8ba  lea     r9, [rsp+268h+var_30]
0x18001a8c2  sub     r9, rax
0x18001a8c5  lea     r8, aP0; "_p0"
0x18001a8cc  test    rdx, rdx
0x18001a8cf  jz      short loc_18001A8F4
0x18001a8d1  test    rcx, rcx
0x18001a8d4  jz      short loc_18001A8F4
0x18001a8d6  movzx   eax, word ptr [r8]
0x18001a8da  test    ax, ax
0x18001a8dd  jz      short loc_18001A8F4
0x18001a8df  mov     [r9], ax
0x18001a8e3  add     r8, 2
0x18001a8e7  add     r9, 2
0x18001a8eb  dec     rcx
0x18001a8ee  sub     rdx, 1
0x18001a8f2  jnz     short loc_18001A8D1
0x18001a8f4  test    rdx, rdx
0x18001a8f7  lea     rcx, [r9-2]
0x18001a8fb  cmovnz  rcx, r9
0x18001a8ff  xor     eax, eax
0x18001a901  mov     [rcx], ax
0x18001a904  jmp     loc_18001A850
0x18001a909  lea     rdx, [rsp+268h+var_244]; int *
0x18001a90e  mov     [rsp+268h+arg_0], rdi
0x18001a916  mov     rcx, rbx; hHandle
0x18001a919  mov     [rsp+268h+var_244], 0
0x18001a921  mov     [rsp+268h+var_248], 0; int
0x18001a929  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001a92e  mov     edi, eax
0x18001a930  test    eax, eax
0x18001a932  js      loc_18001AA2D
0x18001a938  lea     rax, [rsp+268h+Name]
0x18001a93d  nop     dword ptr [rax]
0x18001a940  cmp     word ptr [rax], 0
0x18001a944  jz      short loc_18001A995
0x18001a946  add     rax, 2
0x18001a94a  sub     rsi, 1
0x18001a94e  jnz     short loc_18001A940
0x18001a950  lea     r8, [rsp+268h+Name]; lpName
0x18001a955  xor     edx, edx; bInheritHandle
0x18001a957  mov     ecx, 1F0003h; dwDesiredAccess
0x18001a95c  call    cs:__imp_OpenSemaphoreW
0x18001a962  mov     rdi, rax
0x18001a965  test    rax, rax
0x18001a968  jnz     short loc_18001A9E7
0x18001a96a  mov     rcx, [rsp+268h]; this
0x18001a972  mov     edx, 0DCh; void *
0x18001a977  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001a97c  mov     edi, eax
0x18001a97e  mov     rcx, rbx; this
0x18001a981  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18001a986  mov     eax, edi
0x18001a988  mov     rdi, [rsp+268h+arg_0]
0x18001a990  jmp     loc_18001A88F
0x18001a995  lea     rax, [rsi+rsi]
0x18001a999  lea     r8, [rsp+268h+var_30]
0x18001a9a1  sub     r8, rax
0x18001a9a4  lea     rcx, asc_1800466C8; "h"
0x18001a9ab  test    rsi, rsi
0x18001a9ae  jz      short loc_18001A9D2
0x18001a9b0  test    rbp, rbp
0x18001a9b3  jz      short loc_18001A9D2
0x18001a9b5  movzx   eax, word ptr [rcx]
0x18001a9b8  test    ax, ax
0x18001a9bb  jz      short loc_18001A9D2
0x18001a9bd  mov     [r8], ax
0x18001a9c1  add     rcx, 2
0x18001a9c5  add     r8, 2
0x18001a9c9  dec     rbp
0x18001a9cc  sub     rsi, 1
0x18001a9d0  jnz     short loc_18001A9B0
0x18001a9d2  test    rsi, rsi
0x18001a9d5  lea     rdx, [r8-2]
0x18001a9d9  cmovnz  rdx, r8
0x18001a9dd  xor     eax, eax
0x18001a9df  mov     [rdx], ax
0x18001a9e2  jmp     loc_18001A950
0x18001a9e7  lea     rdx, [rsp+268h+var_248]; int *
0x18001a9ec  mov     rcx, rdi; hHandle
0x18001a9ef  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001a9f4  mov     esi, eax
0x18001a9f6  test    eax, eax
0x18001a9f8  js      short loc_18001AA4E
0x18001a9fa  mov     rcx, rdi; this
0x18001a9fd  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18001aa02  movsxd  rax, [rsp+268h+var_244]
0x18001aa07  movsxd  rcx, [rsp+268h+var_248]
0x18001aa0c  shl     rcx, 1Fh
0x18001aa10  or      rcx, rax
0x18001aa13  mov     [r14], rcx
0x18001aa16  mov     rcx, rbx; this
0x18001aa19  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18001aa1e  mov     rdi, [rsp+268h+arg_0]
0x18001aa26  xor     eax, eax
0x18001aa28  jmp     loc_18001A88F
0x18001aa2d  mov     rcx, [rsp+268h]; this
0x18001aa35  lea     r8, aWil; "wil"
0x18001aa3c  mov     r9d, edi; char *
0x18001aa3f  mov     edx, 0D6h; void *
0x18001aa44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001aa49  jmp     loc_18001A97E
0x18001aa4e  mov     rcx, [rsp+268h]; this
0x18001aa56  lea     r8, aWil; "wil"
0x18001aa5d  mov     r9d, esi; char *
0x18001aa60  mov     edx, 0DEh; void *
0x18001aa65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001aa6a  mov     rcx, rdi; this
0x18001aa6d  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18001aa72  mov     rcx, rbx; this
0x18001aa75  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18001aa7a  mov     eax, esi
0x18001aa7c  jmp     loc_18001A988
0x18001aa81  xor     eax, eax
0x18001aa83  jmp     loc_18001A88F
```
