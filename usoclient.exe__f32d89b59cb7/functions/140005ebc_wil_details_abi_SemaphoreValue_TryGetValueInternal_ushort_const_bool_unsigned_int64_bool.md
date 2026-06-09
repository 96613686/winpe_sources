# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x140005ebc`
- end: `0x14000614b`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `655`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140003a38`

## callees

- `0x140002120`
- `0x1400049c4`
- `0x140005434`
- `0x140005454`
- `0x140005d30`
- `0x140005ebc`
- `0x1400062ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140005f50`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140005fcc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140005f50`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140005fcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006099`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006099`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005f9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000600f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006020`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006038`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000605d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000608a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005f9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000600f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006020`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006038`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000605d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000608a`

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
0x140005ebc  push    rbp
0x140005ebe  push    rbx
0x140005ebf  push    rsi
0x140005ec0  push    rdi
0x140005ec1  push    r14
0x140005ec3  push    r15
0x140005ec5  lea     rbp, [rsp-158h]
0x140005ecd  sub     rsp, 258h
0x140005ed4  mov     rax, cs:__security_cookie
0x140005edb  xor     rax, rsp
0x140005ede  mov     [rbp+180h+var_40], rax
0x140005ee5  xor     r15d, r15d
0x140005ee8  lea     rax, [rsp+280h+Name]
0x140005eed  mov     [r8], r15
0x140005ef0  mov     r14, r8
0x140005ef3  mov     edx, 104h
0x140005ef8  mov     r9d, 7FFFFFFEh
0x140005efe  test    r9, r9
0x140005f01  jz      short loc_140005F22
0x140005f03  movzx   r8d, word ptr [rcx]
0x140005f07  test    r8w, r8w
0x140005f0b  jz      short loc_140005F22
0x140005f0d  mov     [rax], r8w
0x140005f11  add     rcx, 2
0x140005f15  add     rax, 2
0x140005f19  dec     r9
0x140005f1c  sub     rdx, 1; unsigned __int64
0x140005f20  jnz     short loc_140005EFE
0x140005f22  test    rdx, rdx
0x140005f25  lea     rcx, [rax-2]
0x140005f29  lea     r8, aP0; "_p0"
0x140005f30  cmovnz  rcx, rax
0x140005f34  mov     [rcx], r15w
0x140005f38  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140005f3d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140005f42  mov     esi, 1F0003h
0x140005f47  lea     r8, [rsp+280h+Name]; lpName
0x140005f4c  mov     ecx, esi; dwDesiredAccess
0x140005f4e  xor     edx, edx; bInheritHandle
0x140005f50  call    cs:__imp_OpenSemaphoreW
0x140005f56  mov     rbx, rax
0x140005f59  test    rax, rax
0x140005f5c  jz      loc_140006099
0x140005f62  lea     rdx, [rsp+280h+var_25C]; int *
0x140005f67  mov     [rsp+280h+var_25C], r15d
0x140005f6c  mov     rcx, rax; hHandle
0x140005f6f  mov     [rsp+280h+var_260], r15d; int
0x140005f74  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140005f79  mov     edi, eax
0x140005f7b  test    eax, eax
0x140005f7d  jns     short loc_140005FB2
0x140005f7f  mov     rcx, [rbp+188h]; this
0x140005f86  lea     r8, aWil; "wil"
0x140005f8d  mov     r9d, eax; char *
0x140005f90  mov     edx, 0D6h; void *
0x140005f95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005f9a  mov     rcx, rbx; hObject
0x140005f9d  call    cs:__imp_CloseHandle
0x140005fa3  test    eax, eax
0x140005fa5  jz      loc_140006115
0x140005fab  mov     eax, edi
0x140005fad  jmp     loc_1400060C0
0x140005fb2  lea     r8, asc_14000DC38; "h"
0x140005fb9  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140005fbe  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140005fc3  lea     r8, [rsp+280h+Name]; lpName
0x140005fc8  xor     edx, edx; bInheritHandle
0x140005fca  mov     ecx, esi; dwDesiredAccess
0x140005fcc  call    cs:__imp_OpenSemaphoreW
0x140005fd2  mov     rdi, rax
0x140005fd5  test    rax, rax
0x140005fd8  jz      loc_14000606D
0x140005fde  lea     rdx, [rsp+280h+var_260]; int *
0x140005fe3  mov     rcx, rax; hHandle
0x140005fe6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140005feb  mov     esi, eax
0x140005fed  test    eax, eax
0x140005fef  jns     short loc_140006035
0x140005ff1  mov     rcx, [rbp+188h]; this
0x140005ff8  lea     r8, aWil; "wil"
0x140005fff  mov     r9d, eax; char *
0x140006002  mov     edx, 0DEh; void *
0x140006007  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000600c  mov     rcx, rdi; hObject
0x14000600f  call    cs:__imp_CloseHandle
0x140006015  test    eax, eax
0x140006017  jz      loc_140006127
0x14000601d  mov     rcx, rbx; hObject
0x140006020  call    cs:__imp_CloseHandle
0x140006026  test    eax, eax
0x140006028  jz      loc_140006139
0x14000602e  mov     eax, esi
0x140006030  jmp     loc_1400060C0
0x140006035  mov     rcx, rdi; hObject
0x140006038  call    cs:__imp_CloseHandle
0x14000603e  test    eax, eax
0x140006040  jz      loc_1400060DF
0x140006046  movsxd  rax, [rsp+280h+var_25C]
0x14000604b  movsxd  rcx, [rsp+280h+var_260]
0x140006050  shl     rcx, 1Fh
0x140006054  or      rcx, rax
0x140006057  mov     [r14], rcx
0x14000605a  mov     rcx, rbx; hObject
0x14000605d  call    cs:__imp_CloseHandle
0x140006063  test    eax, eax
0x140006065  jz      loc_1400060F1
0x14000606b  jmp     short loc_1400060A4
0x14000606d  mov     rcx, [rbp+188h]; this
0x140006074  lea     r8, aWil; "wil"
0x14000607b  mov     edx, 0DCh; void *
0x140006080  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140006085  mov     rcx, rbx; hObject
0x140006088  mov     edi, eax
0x14000608a  call    cs:__imp_CloseHandle
0x140006090  test    eax, eax
0x140006092  jz      short loc_140006103
0x140006094  jmp     loc_140005FAB
0x140006099  call    cs:__imp_GetLastError
0x14000609f  cmp     eax, 2
0x1400060a2  jnz     short loc_1400060A8
0x1400060a4  xor     eax, eax
0x1400060a6  jmp     short loc_1400060C0
0x1400060a8  mov     rcx, [rbp+188h]; this
0x1400060af  lea     r8, aWil; "wil"
0x1400060b6  mov     edx, 0D0h; void *
0x1400060bb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400060c0  mov     rcx, [rbp+180h+var_40]
0x1400060c7  xor     rcx, rsp; StackCookie
0x1400060ca  call    __security_check_cookie
0x1400060cf  add     rsp, 258h
0x1400060d6  pop     r15
0x1400060d8  pop     r14
0x1400060da  pop     rdi
0x1400060db  pop     rsi
0x1400060dc  pop     rbx
0x1400060dd  pop     rbp
0x1400060de  retn
0x1400060df  mov     rcx, [rbp+188h]; this
0x1400060e6  mov     edx, 0A0Bh; void *
0x1400060eb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400060f1  mov     rcx, [rbp+188h]; this
0x1400060f8  mov     edx, 0A0Bh; void *
0x1400060fd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006103  mov     rcx, [rbp+188h]; this
0x14000610a  mov     edx, 0A0Bh; void *
0x14000610f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006115  mov     rcx, [rbp+188h]; this
0x14000611c  mov     edx, 0A0Bh; void *
0x140006121  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006127  mov     rcx, [rbp+188h]; this
0x14000612e  mov     edx, 0A0Bh; void *
0x140006133  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006139  mov     rcx, [rbp+188h]; this
0x140006140  mov     edx, 0A0Bh; void *
0x140006145  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
