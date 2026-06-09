# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180008434`
- end: `0x1800086a0`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003e4c`
- `0x1800041f0`

## callees

- `0x180001670`
- `0x1800059a0`
- `0x180007b70`
- `0x180007b90`
- `0x180007fac`
- `0x180008434`
- `0x180008d18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085f5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800084c8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000853d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800084c8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000853d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000850e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008579`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000858a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000859f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800085c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800085e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000850e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008579`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000858a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000859f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800085c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800085e6`

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
  unsigned int v13; // r8d
  unsigned int LastError; // edi
  unsigned int v15; // r8d
  const char *v16; // r9
  HANDLE v18; // rax
  unsigned int v19; // r8d
  const char *v20; // r9
  void *v21; // rdi
  int v22; // eax
  unsigned int v23; // r8d
  unsigned int v24; // esi
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v13, (const char *)(unsigned int)ValueFromSemaphore, v37);
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
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v23, (const char *)(unsigned int)v22, v37);
  if ( !CloseHandle(v21) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
  return v24;
}

```

## disassembly

```asm
0x180008434  push    rbp
0x180008436  push    rbx
0x180008437  push    rsi
0x180008438  push    rdi
0x180008439  push    r14
0x18000843b  push    r15
0x18000843d  lea     rbp, [rsp-158h]
0x180008445  sub     rsp, 258h
0x18000844c  mov     rax, cs:__security_cookie
0x180008453  xor     rax, rsp
0x180008456  mov     [rbp+180h+var_40], rax
0x18000845d  xor     r15d, r15d
0x180008460  lea     rax, [rsp+280h+Name]
0x180008465  mov     [r8], r15
0x180008468  mov     r14, r8
0x18000846b  mov     edx, 104h
0x180008470  mov     r9d, 7FFFFFFEh
0x180008476  test    r9, r9
0x180008479  jz      short loc_18000849A
0x18000847b  movzx   r8d, word ptr [rcx]
0x18000847f  test    r8w, r8w
0x180008483  jz      short loc_18000849A
0x180008485  mov     [rax], r8w
0x180008489  add     rcx, 2
0x18000848d  add     rax, 2
0x180008491  dec     r9
0x180008494  sub     rdx, 1; unsigned __int64
0x180008498  jnz     short loc_180008476
0x18000849a  test    rdx, rdx
0x18000849d  lea     rcx, [rax-2]
0x1800084a1  lea     r8, aP0; "_p0"
0x1800084a8  cmovnz  rcx, rax
0x1800084ac  mov     [rcx], r15w
0x1800084b0  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800084b5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800084ba  mov     esi, 1F0003h
0x1800084bf  lea     r8, [rsp+280h+Name]; lpName
0x1800084c4  mov     ecx, esi; dwDesiredAccess
0x1800084c6  xor     edx, edx; bInheritHandle
0x1800084c8  call    cs:__imp_OpenSemaphoreW
0x1800084ce  mov     rbx, rax
0x1800084d1  test    rax, rax
0x1800084d4  jz      loc_1800085F5
0x1800084da  lea     rdx, [rsp+280h+var_25C]; int *
0x1800084df  mov     [rsp+280h+var_25C], r15d
0x1800084e4  mov     rcx, rax; hHandle
0x1800084e7  mov     [rsp+280h+var_260], r15d; int
0x1800084ec  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800084f1  mov     edi, eax
0x1800084f3  test    eax, eax
0x1800084f5  jns     short loc_180008523
0x1800084f7  mov     rcx, [rbp+188h]; this
0x1800084fe  mov     r9d, eax; char *
0x180008501  mov     edx, 0D6h; void *
0x180008506  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000850b  mov     rcx, rbx; hObject
0x18000850e  call    cs:__imp_CloseHandle
0x180008514  test    eax, eax
0x180008516  jz      loc_18000866A
0x18000851c  mov     eax, edi
0x18000851e  jmp     loc_180008615
0x180008523  lea     r8, asc_18000FDC8; "h"
0x18000852a  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000852f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008534  lea     r8, [rsp+280h+Name]; lpName
0x180008539  xor     edx, edx; bInheritHandle
0x18000853b  mov     ecx, esi; dwDesiredAccess
0x18000853d  call    cs:__imp_OpenSemaphoreW
0x180008543  mov     rdi, rax
0x180008546  test    rax, rax
0x180008549  jz      loc_1800085D0
0x18000854f  lea     rdx, [rsp+280h+var_260]; int *
0x180008554  mov     rcx, rax; hHandle
0x180008557  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000855c  mov     esi, eax
0x18000855e  test    eax, eax
0x180008560  jns     short loc_18000859C
0x180008562  mov     rcx, [rbp+188h]; this
0x180008569  mov     r9d, eax; char *
0x18000856c  mov     edx, 0DEh; void *
0x180008571  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008576  mov     rcx, rdi; hObject
0x180008579  call    cs:__imp_CloseHandle
0x18000857f  test    eax, eax
0x180008581  jz      loc_18000867C
0x180008587  mov     rcx, rbx; hObject
0x18000858a  call    cs:__imp_CloseHandle
0x180008590  test    eax, eax
0x180008592  jz      loc_18000868E
0x180008598  mov     eax, esi
0x18000859a  jmp     short loc_180008615
0x18000859c  mov     rcx, rdi; hObject
0x18000859f  call    cs:__imp_CloseHandle
0x1800085a5  test    eax, eax
0x1800085a7  jz      loc_180008634
0x1800085ad  movsxd  rax, [rsp+280h+var_25C]
0x1800085b2  movsxd  rcx, [rsp+280h+var_260]
0x1800085b7  shl     rcx, 1Fh
0x1800085bb  or      rcx, rax
0x1800085be  mov     [r14], rcx
0x1800085c1  mov     rcx, rbx; hObject
0x1800085c4  call    cs:__imp_CloseHandle
0x1800085ca  test    eax, eax
0x1800085cc  jz      short loc_180008646
0x1800085ce  jmp     short loc_180008600
0x1800085d0  mov     rcx, [rbp+188h]; this
0x1800085d7  mov     edx, 0DCh; void *
0x1800085dc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800085e1  mov     rcx, rbx; hObject
0x1800085e4  mov     edi, eax
0x1800085e6  call    cs:__imp_CloseHandle
0x1800085ec  test    eax, eax
0x1800085ee  jz      short loc_180008658
0x1800085f0  jmp     loc_18000851C
0x1800085f5  call    cs:__imp_GetLastError
0x1800085fb  cmp     eax, 2
0x1800085fe  jnz     short loc_180008604
0x180008600  xor     eax, eax
0x180008602  jmp     short loc_180008615
0x180008604  mov     rcx, [rbp+188h]; this
0x18000860b  mov     edx, 0D0h; void *
0x180008610  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008615  mov     rcx, [rbp+180h+var_40]
0x18000861c  xor     rcx, rsp; StackCookie
0x18000861f  call    __security_check_cookie
0x180008624  add     rsp, 258h
0x18000862b  pop     r15
0x18000862d  pop     r14
0x18000862f  pop     rdi
0x180008630  pop     rsi
0x180008631  pop     rbx
0x180008632  pop     rbp
0x180008633  retn
0x180008634  mov     rcx, [rbp+188h]; this
0x18000863b  mov     edx, 0A0Bh; void *
0x180008640  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008646  mov     rcx, [rbp+188h]; this
0x18000864d  mov     edx, 0A0Bh; void *
0x180008652  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008658  mov     rcx, [rbp+188h]; this
0x18000865f  mov     edx, 0A0Bh; void *
0x180008664  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000866a  mov     rcx, [rbp+188h]; this
0x180008671  mov     edx, 0A0Bh; void *
0x180008676  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000867c  mov     rcx, [rbp+188h]; this
0x180008683  mov     edx, 0A0Bh; void *
0x180008688  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000868e  mov     rcx, [rbp+188h]; this
0x180008695  mov     edx, 0A0Bh; void *
0x18000869a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
