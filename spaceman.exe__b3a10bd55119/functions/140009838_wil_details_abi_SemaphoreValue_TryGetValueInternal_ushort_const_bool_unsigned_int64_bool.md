# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x140009838`
- end: `0x140009aa4`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1400054ac`
- `0x140005850`

## callees

- `0x140006e80`
- `0x1400089c0`
- `0x1400089e0`
- `0x140009000`
- `0x140009838`
- `0x14000a01c`
- `0x14000d1f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400099f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400099f9`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400098cc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140009941`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400098cc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140009941`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009912`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000997d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000998e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400099a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400099c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400099ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009912`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000997d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000998e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400099a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400099c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400099ea`

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
  int v13; // r8d
  unsigned int LastError; // edi
  __int64 v15; // r8
  const char *v16; // r9
  HANDLE v18; // rax
  unsigned int v19; // r8d
  const char *v20; // r9
  void *v21; // rdi
  int v22; // eax
  int v23; // r8d
  unsigned int v24; // esi
  __int64 v25; // r8
  const char *v26; // r9
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
  const char *v34; // r9
  unsigned int v35; // r8d
  const char *v36; // r9
  int v37; // [rsp+20h] [rbp-E0h] BYREF
  int v38[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v35, v36);
    return 0;
  }
  v38[0] = 0;
  v37 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v38);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v13, (const char *)(unsigned int)ValueFromSemaphore);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v15, v16);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v18 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v21 = v18;
  if ( !v18 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v19, v20);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    return LastError;
  }
  v22 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v18, &v37);
  v24 = v22;
  if ( v22 >= 0 )
  {
    if ( !CloseHandle(v21) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    *a3 = v38[0] | (unsigned __int64)((__int64)v37 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v23, (const char *)(unsigned int)v22);
  if ( !CloseHandle(v21) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
  return v24;
}

```

## disassembly

```asm
0x140009838  push    rbp
0x14000983a  push    rbx
0x14000983b  push    rsi
0x14000983c  push    rdi
0x14000983d  push    r14
0x14000983f  push    r15
0x140009841  lea     rbp, [rsp-158h]
0x140009849  sub     rsp, 258h
0x140009850  mov     rax, cs:__security_cookie
0x140009857  xor     rax, rsp
0x14000985a  mov     [rbp+180h+var_40], rax
0x140009861  xor     r15d, r15d
0x140009864  lea     rax, [rsp+280h+Name]
0x140009869  mov     [r8], r15
0x14000986c  mov     r14, r8
0x14000986f  mov     edx, 104h
0x140009874  mov     r9d, 7FFFFFFEh
0x14000987a  test    r9, r9
0x14000987d  jz      short loc_14000989E
0x14000987f  movzx   r8d, word ptr [rcx]
0x140009883  test    r8w, r8w
0x140009887  jz      short loc_14000989E
0x140009889  mov     [rax], r8w
0x14000988d  add     rcx, 2
0x140009891  add     rax, 2
0x140009895  dec     r9
0x140009898  sub     rdx, 1; unsigned __int64
0x14000989c  jnz     short loc_14000987A
0x14000989e  test    rdx, rdx
0x1400098a1  lea     rcx, [rax-2]
0x1400098a5  lea     r8, aP0; "_p0"
0x1400098ac  cmovnz  rcx, rax
0x1400098b0  mov     [rcx], r15w
0x1400098b4  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400098b9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400098be  mov     esi, 1F0003h
0x1400098c3  lea     r8, [rsp+280h+Name]; lpName
0x1400098c8  mov     ecx, esi; dwDesiredAccess
0x1400098ca  xor     edx, edx; bInheritHandle
0x1400098cc  call    cs:__imp_OpenSemaphoreW
0x1400098d2  mov     rbx, rax
0x1400098d5  test    rax, rax
0x1400098d8  jz      loc_1400099F9
0x1400098de  lea     rdx, [rsp+280h+var_25C]; int *
0x1400098e3  mov     [rsp+280h+var_25C], r15d
0x1400098e8  mov     rcx, rax; hHandle
0x1400098eb  mov     [rsp+280h+var_260], r15d; int
0x1400098f0  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1400098f5  mov     edi, eax
0x1400098f7  test    eax, eax
0x1400098f9  jns     short loc_140009927
0x1400098fb  mov     rcx, [rbp+188h]; this
0x140009902  mov     r9d, eax; char *
0x140009905  mov     edx, 0D6h; void *
0x14000990a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000990f  mov     rcx, rbx; hObject
0x140009912  call    cs:__imp_CloseHandle
0x140009918  test    eax, eax
0x14000991a  jz      loc_140009A6E
0x140009920  mov     eax, edi
0x140009922  jmp     loc_140009A19
0x140009927  lea     r8, asc_14000FE38; "h"
0x14000992e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140009933  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140009938  lea     r8, [rsp+280h+Name]; lpName
0x14000993d  xor     edx, edx; bInheritHandle
0x14000993f  mov     ecx, esi; dwDesiredAccess
0x140009941  call    cs:__imp_OpenSemaphoreW
0x140009947  mov     rdi, rax
0x14000994a  test    rax, rax
0x14000994d  jz      loc_1400099D4
0x140009953  lea     rdx, [rsp+280h+var_260]; int *
0x140009958  mov     rcx, rax; hHandle
0x14000995b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140009960  mov     esi, eax
0x140009962  test    eax, eax
0x140009964  jns     short loc_1400099A0
0x140009966  mov     rcx, [rbp+188h]; this
0x14000996d  mov     r9d, eax; char *
0x140009970  mov     edx, 0DEh; void *
0x140009975  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000997a  mov     rcx, rdi; hObject
0x14000997d  call    cs:__imp_CloseHandle
0x140009983  test    eax, eax
0x140009985  jz      loc_140009A80
0x14000998b  mov     rcx, rbx; hObject
0x14000998e  call    cs:__imp_CloseHandle
0x140009994  test    eax, eax
0x140009996  jz      loc_140009A92
0x14000999c  mov     eax, esi
0x14000999e  jmp     short loc_140009A19
0x1400099a0  mov     rcx, rdi; hObject
0x1400099a3  call    cs:__imp_CloseHandle
0x1400099a9  test    eax, eax
0x1400099ab  jz      loc_140009A38
0x1400099b1  movsxd  rax, [rsp+280h+var_25C]
0x1400099b6  movsxd  rcx, [rsp+280h+var_260]
0x1400099bb  shl     rcx, 1Fh
0x1400099bf  or      rcx, rax
0x1400099c2  mov     [r14], rcx
0x1400099c5  mov     rcx, rbx; hObject
0x1400099c8  call    cs:__imp_CloseHandle
0x1400099ce  test    eax, eax
0x1400099d0  jz      short loc_140009A4A
0x1400099d2  jmp     short loc_140009A04
0x1400099d4  mov     rcx, [rbp+188h]; this
0x1400099db  mov     edx, 0DCh; void *
0x1400099e0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400099e5  mov     rcx, rbx; hObject
0x1400099e8  mov     edi, eax
0x1400099ea  call    cs:__imp_CloseHandle
0x1400099f0  test    eax, eax
0x1400099f2  jz      short loc_140009A5C
0x1400099f4  jmp     loc_140009920
0x1400099f9  call    cs:__imp_GetLastError
0x1400099ff  cmp     eax, 2
0x140009a02  jnz     short loc_140009A08
0x140009a04  xor     eax, eax
0x140009a06  jmp     short loc_140009A19
0x140009a08  mov     rcx, [rbp+188h]; this
0x140009a0f  mov     edx, 0D0h; void *
0x140009a14  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140009a19  mov     rcx, [rbp+180h+var_40]
0x140009a20  xor     rcx, rsp; StackCookie
0x140009a23  call    __security_check_cookie
0x140009a28  add     rsp, 258h
0x140009a2f  pop     r15
0x140009a31  pop     r14
0x140009a33  pop     rdi
0x140009a34  pop     rsi
0x140009a35  pop     rbx
0x140009a36  pop     rbp
0x140009a37  retn
0x140009a38  mov     rcx, [rbp+188h]; this
0x140009a3f  mov     edx, 0A0Bh; void *
0x140009a44  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140009a4a  mov     rcx, [rbp+188h]; this
0x140009a51  mov     edx, 0A0Bh; void *
0x140009a56  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140009a5c  mov     rcx, [rbp+188h]; this
0x140009a63  mov     edx, 0A0Bh; void *
0x140009a68  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140009a6e  mov     rcx, [rbp+188h]; this
0x140009a75  mov     edx, 0A0Bh; void *
0x140009a7a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140009a80  mov     rcx, [rbp+188h]; this
0x140009a87  mov     edx, 0A0Bh; void *
0x140009a8c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140009a92  mov     rcx, [rbp+188h]; this
0x140009a99  mov     edx, 0A0Bh; void *
0x140009a9e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
