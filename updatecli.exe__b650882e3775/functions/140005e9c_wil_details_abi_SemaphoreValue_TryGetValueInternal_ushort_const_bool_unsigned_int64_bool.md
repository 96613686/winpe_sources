# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x140005e9c`
- end: `0x14000612b`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `655`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140003a18`

## callees

- `0x140002130`
- `0x1400049a4`
- `0x140005414`
- `0x140005434`
- `0x140005d10`
- `0x140005e9c`
- `0x14000628c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140005f30`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140005fac`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140005f30`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140005fac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006079`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006079`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005f7d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005fef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006000`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006018`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000603d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000606a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005f7d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005fef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006000`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006018`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000603d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000606a`

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
  __int64 v14; // r8
  const char *v15; // r9
  HANDLE v17; // rax
  const char *v18; // r9
  void *v19; // rdi
  int v20; // eax
  unsigned int v21; // esi
  __int64 v22; // r8
  const char *v23; // r9
  __int64 v24; // r8
  const char *v25; // r9
  __int64 v26; // r8
  const char *v27; // r9
  __int64 v28; // r8
  const char *v29; // r9
  __int64 v30; // r8
  const char *v31; // r9
  const char *v32; // r9
  int v33; // [rsp+20h] [rbp-E0h] BYREF
  int v34[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (int)"wil", v32);
    return 0;
  }
  v34[0] = 0;
  v33 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v34);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, (int)"wil", (const char *)(unsigned int)ValueFromSemaphore);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v19 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (int)"wil", v18);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    return LastError;
  }
  v20 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v33);
  v21 = v20;
  if ( v20 >= 0 )
  {
    if ( !CloseHandle(v19) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    *a3 = v34[0] | (unsigned __int64)((__int64)v33 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v20);
  if ( !CloseHandle(v19) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  return v21;
}

```

## disassembly

```asm
0x140005e9c  push    rbp
0x140005e9e  push    rbx
0x140005e9f  push    rsi
0x140005ea0  push    rdi
0x140005ea1  push    r14
0x140005ea3  push    r15
0x140005ea5  lea     rbp, [rsp-158h]
0x140005ead  sub     rsp, 258h
0x140005eb4  mov     rax, cs:__security_cookie
0x140005ebb  xor     rax, rsp
0x140005ebe  mov     [rbp+180h+var_40], rax
0x140005ec5  xor     r15d, r15d
0x140005ec8  lea     rax, [rsp+280h+Name]
0x140005ecd  mov     [r8], r15
0x140005ed0  mov     r14, r8
0x140005ed3  mov     edx, 104h
0x140005ed8  mov     r9d, 7FFFFFFEh
0x140005ede  test    r9, r9
0x140005ee1  jz      short loc_140005F02
0x140005ee3  movzx   r8d, word ptr [rcx]
0x140005ee7  test    r8w, r8w
0x140005eeb  jz      short loc_140005F02
0x140005eed  mov     [rax], r8w
0x140005ef1  add     rcx, 2
0x140005ef5  add     rax, 2
0x140005ef9  dec     r9
0x140005efc  sub     rdx, 1; unsigned __int64
0x140005f00  jnz     short loc_140005EDE
0x140005f02  test    rdx, rdx
0x140005f05  lea     rcx, [rax-2]
0x140005f09  lea     r8, aP0; "_p0"
0x140005f10  cmovnz  rcx, rax
0x140005f14  mov     [rcx], r15w
0x140005f18  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140005f1d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140005f22  mov     esi, 1F0003h
0x140005f27  lea     r8, [rsp+280h+Name]; lpName
0x140005f2c  mov     ecx, esi; dwDesiredAccess
0x140005f2e  xor     edx, edx; bInheritHandle
0x140005f30  call    cs:__imp_OpenSemaphoreW
0x140005f36  mov     rbx, rax
0x140005f39  test    rax, rax
0x140005f3c  jz      loc_140006079
0x140005f42  lea     rdx, [rsp+280h+var_25C]; int *
0x140005f47  mov     [rsp+280h+var_25C], r15d
0x140005f4c  mov     rcx, rax; hHandle
0x140005f4f  mov     [rsp+280h+var_260], r15d; int
0x140005f54  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140005f59  mov     edi, eax
0x140005f5b  test    eax, eax
0x140005f5d  jns     short loc_140005F92
0x140005f5f  mov     rcx, [rbp+188h]; this
0x140005f66  lea     r8, aWil; "wil"
0x140005f6d  mov     r9d, eax; char *
0x140005f70  mov     edx, 0D6h; void *
0x140005f75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005f7a  mov     rcx, rbx; hObject
0x140005f7d  call    cs:__imp_CloseHandle
0x140005f83  test    eax, eax
0x140005f85  jz      loc_1400060F5
0x140005f8b  mov     eax, edi
0x140005f8d  jmp     loc_1400060A0
0x140005f92  lea     r8, asc_14000DC38; "h"
0x140005f99  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140005f9e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140005fa3  lea     r8, [rsp+280h+Name]; lpName
0x140005fa8  xor     edx, edx; bInheritHandle
0x140005faa  mov     ecx, esi; dwDesiredAccess
0x140005fac  call    cs:__imp_OpenSemaphoreW
0x140005fb2  mov     rdi, rax
0x140005fb5  test    rax, rax
0x140005fb8  jz      loc_14000604D
0x140005fbe  lea     rdx, [rsp+280h+var_260]; int *
0x140005fc3  mov     rcx, rax; hHandle
0x140005fc6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140005fcb  mov     esi, eax
0x140005fcd  test    eax, eax
0x140005fcf  jns     short loc_140006015
0x140005fd1  mov     rcx, [rbp+188h]; this
0x140005fd8  lea     r8, aWil; "wil"
0x140005fdf  mov     r9d, eax; char *
0x140005fe2  mov     edx, 0DEh; void *
0x140005fe7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005fec  mov     rcx, rdi; hObject
0x140005fef  call    cs:__imp_CloseHandle
0x140005ff5  test    eax, eax
0x140005ff7  jz      loc_140006107
0x140005ffd  mov     rcx, rbx; hObject
0x140006000  call    cs:__imp_CloseHandle
0x140006006  test    eax, eax
0x140006008  jz      loc_140006119
0x14000600e  mov     eax, esi
0x140006010  jmp     loc_1400060A0
0x140006015  mov     rcx, rdi; hObject
0x140006018  call    cs:__imp_CloseHandle
0x14000601e  test    eax, eax
0x140006020  jz      loc_1400060BF
0x140006026  movsxd  rax, [rsp+280h+var_25C]
0x14000602b  movsxd  rcx, [rsp+280h+var_260]
0x140006030  shl     rcx, 1Fh
0x140006034  or      rcx, rax
0x140006037  mov     [r14], rcx
0x14000603a  mov     rcx, rbx; hObject
0x14000603d  call    cs:__imp_CloseHandle
0x140006043  test    eax, eax
0x140006045  jz      loc_1400060D1
0x14000604b  jmp     short loc_140006084
0x14000604d  mov     rcx, [rbp+188h]; this
0x140006054  lea     r8, aWil; "wil"
0x14000605b  mov     edx, 0DCh; void *
0x140006060  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140006065  mov     rcx, rbx; hObject
0x140006068  mov     edi, eax
0x14000606a  call    cs:__imp_CloseHandle
0x140006070  test    eax, eax
0x140006072  jz      short loc_1400060E3
0x140006074  jmp     loc_140005F8B
0x140006079  call    cs:__imp_GetLastError
0x14000607f  cmp     eax, 2
0x140006082  jnz     short loc_140006088
0x140006084  xor     eax, eax
0x140006086  jmp     short loc_1400060A0
0x140006088  mov     rcx, [rbp+188h]; this
0x14000608f  lea     r8, aWil; "wil"
0x140006096  mov     edx, 0D0h; void *
0x14000609b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400060a0  mov     rcx, [rbp+180h+var_40]
0x1400060a7  xor     rcx, rsp; StackCookie
0x1400060aa  call    __security_check_cookie
0x1400060af  add     rsp, 258h
0x1400060b6  pop     r15
0x1400060b8  pop     r14
0x1400060ba  pop     rdi
0x1400060bb  pop     rsi
0x1400060bc  pop     rbx
0x1400060bd  pop     rbp
0x1400060be  retn
0x1400060bf  mov     rcx, [rbp+188h]; this
0x1400060c6  mov     edx, 0A0Bh; void *
0x1400060cb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400060d1  mov     rcx, [rbp+188h]; this
0x1400060d8  mov     edx, 0A0Bh; void *
0x1400060dd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400060e3  mov     rcx, [rbp+188h]; this
0x1400060ea  mov     edx, 0A0Bh; void *
0x1400060ef  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400060f5  mov     rcx, [rbp+188h]; this
0x1400060fc  mov     edx, 0A0Bh; void *
0x140006101  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006107  mov     rcx, [rbp+188h]; this
0x14000610e  mov     edx, 0A0Bh; void *
0x140006113  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006119  mov     rcx, [rbp+188h]; this
0x140006120  mov     edx, 0A0Bh; void *
0x140006125  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
