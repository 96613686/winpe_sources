# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000aeac`
- end: `0x18000b126`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000671c`
- `0x180006af8`

## callees

- `0x180004120`
- `0x180008170`
- `0x180009fc4`
- `0x180009fe4`
- `0x18000aa34`
- `0x18000aeac`
- `0x18000b76c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000af40`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000afbc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000af40`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000afbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b07b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b07b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000af8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000afff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b010`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b025`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b04a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b06c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000af8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000afff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b010`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b025`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b04a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b06c`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  unsigned __int64 v6; // rdx
  __int64 v7; // r9
  WCHAR *v8; // rcx
  HANDLE v9; // rax
  void *v10; // rbx
  int ValueFromSemaphore; // eax
  unsigned __int64 v12; // rdx
  unsigned int LastError; // edi
  unsigned int v14; // r8d
  const char *v15; // r9
  HANDLE v17; // rax
  unsigned int v18; // r8d
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  unsigned int v22; // esi
  unsigned int v23; // r8d
  const char *v24; // r9
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  int v35; // [rsp+20h] [rbp-E0h] BYREF
  int v36[3]; // [rsp+24h] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = Name;
  *a3 = 0;
  v6 = 260;
  v7 = 2147483646;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v7;
    --v6;
  }
  while ( v6 );
  v8 = v4 - 1;
  if ( v6 )
    v8 = v4;
  *v8 = 0;
  StringCchCatW(Name, v6, L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v33, v34);
    return 0;
  }
  v36[0] = 0;
  v35 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v36);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v35);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v18, v19);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    return LastError;
  }
  v21 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v35);
  v22 = v21;
  if ( v21 >= 0 )
  {
    if ( !CloseHandle(v20) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    *a3 = v36[0] | (unsigned __int64)((__int64)v35 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v21, v35);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  return v22;
}

```

## disassembly

```asm
0x18000aeac  push    rbp
0x18000aeae  push    rbx
0x18000aeaf  push    rsi
0x18000aeb0  push    rdi
0x18000aeb1  push    r14
0x18000aeb3  push    r15
0x18000aeb5  lea     rbp, [rsp-158h]
0x18000aebd  sub     rsp, 258h
0x18000aec4  mov     rax, cs:__security_cookie
0x18000aecb  xor     rax, rsp
0x18000aece  mov     [rbp+180h+var_40], rax
0x18000aed5  xor     r15d, r15d
0x18000aed8  lea     rax, [rsp+280h+Name]
0x18000aedd  mov     [r8], r15
0x18000aee0  mov     r14, r8
0x18000aee3  mov     edx, 104h
0x18000aee8  mov     r9d, 7FFFFFFEh
0x18000aeee  test    r9, r9
0x18000aef1  jz      short loc_18000AF12
0x18000aef3  movzx   r8d, word ptr [rcx]
0x18000aef7  test    r8w, r8w
0x18000aefb  jz      short loc_18000AF12
0x18000aefd  mov     [rax], r8w
0x18000af01  add     rcx, 2
0x18000af05  add     rax, 2
0x18000af09  dec     r9
0x18000af0c  sub     rdx, 1; unsigned __int64
0x18000af10  jnz     short loc_18000AEEE
0x18000af12  test    rdx, rdx
0x18000af15  lea     rcx, [rax-2]
0x18000af19  lea     r8, aP0; "_p0"
0x18000af20  cmovnz  rcx, rax
0x18000af24  mov     [rcx], r15w
0x18000af28  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000af2d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000af32  mov     esi, 1F0003h
0x18000af37  lea     r8, [rsp+280h+Name]; lpName
0x18000af3c  mov     ecx, esi; dwDesiredAccess
0x18000af3e  xor     edx, edx; bInheritHandle
0x18000af40  call    cs:__imp_OpenSemaphoreW
0x18000af46  mov     rbx, rax
0x18000af49  test    rax, rax
0x18000af4c  jz      loc_18000B07B
0x18000af52  lea     rdx, [rsp+280h+var_25C]; int *
0x18000af57  mov     [rsp+280h+var_25C], r15d
0x18000af5c  mov     rcx, rax; hHandle
0x18000af5f  mov     [rsp+280h+var_260], r15d; int
0x18000af64  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000af69  mov     edi, eax
0x18000af6b  test    eax, eax
0x18000af6d  jns     short loc_18000AFA2
0x18000af6f  mov     rcx, [rbp+188h]; this
0x18000af76  lea     r8, aWil; "wil"
0x18000af7d  mov     r9d, eax; char *
0x18000af80  mov     edx, 0D6h; void *
0x18000af85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000af8a  mov     rcx, rbx; hObject
0x18000af8d  call    cs:__imp_CloseHandle
0x18000af93  test    eax, eax
0x18000af95  jz      loc_18000B0F0
0x18000af9b  mov     eax, edi
0x18000af9d  jmp     loc_18000B09B
0x18000afa2  lea     r8, asc_180036AB0; "h"
0x18000afa9  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000afae  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000afb3  lea     r8, [rsp+280h+Name]; lpName
0x18000afb8  xor     edx, edx; bInheritHandle
0x18000afba  mov     ecx, esi; dwDesiredAccess
0x18000afbc  call    cs:__imp_OpenSemaphoreW
0x18000afc2  mov     rdi, rax
0x18000afc5  test    rax, rax
0x18000afc8  jz      loc_18000B056
0x18000afce  lea     rdx, [rsp+280h+var_260]; int *
0x18000afd3  mov     rcx, rax; hHandle
0x18000afd6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000afdb  mov     esi, eax
0x18000afdd  test    eax, eax
0x18000afdf  jns     short loc_18000B022
0x18000afe1  mov     rcx, [rbp+188h]; this
0x18000afe8  lea     r8, aWil; "wil"
0x18000afef  mov     r9d, eax; char *
0x18000aff2  mov     edx, 0DEh; void *
0x18000aff7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000affc  mov     rcx, rdi; hObject
0x18000afff  call    cs:__imp_CloseHandle
0x18000b005  test    eax, eax
0x18000b007  jz      loc_18000B102
0x18000b00d  mov     rcx, rbx; hObject
0x18000b010  call    cs:__imp_CloseHandle
0x18000b016  test    eax, eax
0x18000b018  jz      loc_18000B114
0x18000b01e  mov     eax, esi
0x18000b020  jmp     short loc_18000B09B
0x18000b022  mov     rcx, rdi; hObject
0x18000b025  call    cs:__imp_CloseHandle
0x18000b02b  test    eax, eax
0x18000b02d  jz      loc_18000B0BA
0x18000b033  movsxd  rax, [rsp+280h+var_25C]
0x18000b038  movsxd  rcx, [rsp+280h+var_260]
0x18000b03d  shl     rcx, 1Fh
0x18000b041  or      rcx, rax
0x18000b044  mov     [r14], rcx
0x18000b047  mov     rcx, rbx; hObject
0x18000b04a  call    cs:__imp_CloseHandle
0x18000b050  test    eax, eax
0x18000b052  jz      short loc_18000B0CC
0x18000b054  jmp     short loc_18000B086
0x18000b056  mov     rcx, [rbp+188h]; this
0x18000b05d  mov     edx, 0DCh; void *
0x18000b062  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b067  mov     rcx, rbx; hObject
0x18000b06a  mov     edi, eax
0x18000b06c  call    cs:__imp_CloseHandle
0x18000b072  test    eax, eax
0x18000b074  jz      short loc_18000B0DE
0x18000b076  jmp     loc_18000AF9B
0x18000b07b  call    cs:__imp_GetLastError
0x18000b081  cmp     eax, 2
0x18000b084  jnz     short loc_18000B08A
0x18000b086  xor     eax, eax
0x18000b088  jmp     short loc_18000B09B
0x18000b08a  mov     rcx, [rbp+188h]; this
0x18000b091  mov     edx, 0D0h; void *
0x18000b096  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b09b  mov     rcx, [rbp+180h+var_40]
0x18000b0a2  xor     rcx, rsp; StackCookie
0x18000b0a5  call    __security_check_cookie
0x18000b0aa  add     rsp, 258h
0x18000b0b1  pop     r15
0x18000b0b3  pop     r14
0x18000b0b5  pop     rdi
0x18000b0b6  pop     rsi
0x18000b0b7  pop     rbx
0x18000b0b8  pop     rbp
0x18000b0b9  retn
0x18000b0ba  mov     rcx, [rbp+188h]; this
0x18000b0c1  mov     edx, 0A0Bh; void *
0x18000b0c6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b0cc  mov     rcx, [rbp+188h]; this
0x18000b0d3  mov     edx, 0A0Bh; void *
0x18000b0d8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b0de  mov     rcx, [rbp+188h]; this
0x18000b0e5  mov     edx, 0A0Bh; void *
0x18000b0ea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b0f0  mov     rcx, [rbp+188h]; this
0x18000b0f7  mov     edx, 0A0Bh; void *
0x18000b0fc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b102  mov     rcx, [rbp+188h]; this
0x18000b109  mov     edx, 0A0Bh; void *
0x18000b10e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b114  mov     rcx, [rbp+188h]; this
0x18000b11b  mov     edx, 0A0Bh; void *
0x18000b120  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
