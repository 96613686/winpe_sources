# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x14000456c`
- end: `0x1400047ef`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `643`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1400026bc`
- `0x14000539c`

## callees

- `0x140003700`
- `0x1400040e0`
- `0x140004100`
- `0x14000441c`
- `0x14000456c`
- `0x14000494c`
- `0x140014910`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x140004603`
- `KERNEL32!OpenSemaphoreW` at `0x140004685`
- `KERNEL32!OpenSemaphoreW` at `0x140004603`
- `KERNEL32!OpenSemaphoreW` at `0x140004685`
- `KERNEL32!CloseHandle` at `0x140004650`
- `KERNEL32!CloseHandle` at `0x1400046c8`
- `KERNEL32!CloseHandle` at `0x1400046d9`
- `KERNEL32!CloseHandle` at `0x1400046ee`
- `KERNEL32!CloseHandle` at `0x140004713`
- `KERNEL32!CloseHandle` at `0x140004735`
- `KERNEL32!CloseHandle` at `0x140004650`
- `KERNEL32!CloseHandle` at `0x1400046c8`
- `KERNEL32!CloseHandle` at `0x1400046d9`
- `KERNEL32!CloseHandle` at `0x1400046ee`
- `KERNEL32!CloseHandle` at `0x140004713`
- `KERNEL32!CloseHandle` at `0x140004735`
- `KERNEL32!GetLastError` at `0x140004744`
- `KERNEL32!GetLastError` at `0x140004744`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v5; // rdx
  __int64 v7; // r9
  WCHAR *v8; // rcx
  HANDLE v9; // rax
  void *v10; // rbx
  int ValueFromSemaphore; // eax
  unsigned int LastError; // edi
  unsigned int v13; // r8d
  const char *v14; // r9
  HANDLE v16; // rax
  unsigned int v17; // r8d
  const char *v18; // r9
  void *v19; // rdi
  int v20; // eax
  unsigned int v21; // esi
  unsigned int v22; // r8d
  const char *v23; // r9
  unsigned int v24; // r8d
  const char *v25; // r9
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  int v34; // [rsp+20h] [rbp-E0h] BYREF
  int v35[3]; // [rsp+24h] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = Name;
  *a3 = 0;
  v5 = 260;
  v7 = 2147483646;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v7;
    --v5;
  }
  while ( v5 );
  v8 = v4 - 1;
  if ( v5 )
    v8 = v4;
  *v8 = 0;
  StringCchCatW(Name, 0x104u, L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v32, v33);
    return 0;
  }
  v35[0] = 0;
  v34 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v35);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v34);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v13, v14);
    return LastError;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v19 = v16;
  if ( !v16 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v17, v18);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    return LastError;
  }
  v20 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v16, &v34);
  v21 = v20;
  if ( v20 >= 0 )
  {
    if ( !CloseHandle(v19) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    *a3 = v35[0] | (unsigned __int64)((__int64)v34 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v20, v34);
  if ( !CloseHandle(v19) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  return v21;
}

```

## disassembly

```asm
0x14000456c  push    rbp
0x14000456e  push    rbx
0x14000456f  push    rsi
0x140004570  push    rdi
0x140004571  push    r14
0x140004573  push    r15
0x140004575  lea     rbp, [rsp-158h]
0x14000457d  sub     rsp, 258h
0x140004584  mov     rax, cs:__security_cookie
0x14000458b  xor     rax, rsp
0x14000458e  mov     [rbp+180h+var_40], rax
0x140004595  xor     r15d, r15d
0x140004598  lea     rax, [rsp+280h+Name]
0x14000459d  mov     esi, 104h
0x1400045a2  mov     [r8], r15
0x1400045a5  mov     edx, esi
0x1400045a7  mov     r14, r8
0x1400045aa  mov     r9d, 7FFFFFFEh
0x1400045b0  test    r9, r9
0x1400045b3  jz      short loc_1400045D4
0x1400045b5  movzx   r8d, word ptr [rcx]
0x1400045b9  test    r8w, r8w
0x1400045bd  jz      short loc_1400045D4
0x1400045bf  mov     [rax], r8w
0x1400045c3  add     rcx, 2
0x1400045c7  add     rax, 2
0x1400045cb  dec     r9
0x1400045ce  sub     rdx, 1
0x1400045d2  jnz     short loc_1400045B0
0x1400045d4  test    rdx, rdx
0x1400045d7  lea     rcx, [rax-2]
0x1400045db  lea     r8, aP0; "_p0"
0x1400045e2  mov     rdx, rsi; unsigned __int64
0x1400045e5  cmovnz  rcx, rax
0x1400045e9  mov     [rcx], r15w
0x1400045ed  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400045f2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400045f7  lea     r8, [rsp+280h+Name]; lpName
0x1400045fc  xor     edx, edx; bInheritHandle
0x1400045fe  mov     ecx, 1F0003h; dwDesiredAccess
0x140004603  call    cs:__imp_OpenSemaphoreW
0x140004609  mov     rbx, rax
0x14000460c  test    rax, rax
0x14000460f  jz      loc_140004744
0x140004615  lea     rdx, [rsp+280h+var_25C]; int *
0x14000461a  mov     [rsp+280h+var_25C], r15d
0x14000461f  mov     rcx, rax; hHandle
0x140004622  mov     [rsp+280h+var_260], r15d; int
0x140004627  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000462c  mov     edi, eax
0x14000462e  test    eax, eax
0x140004630  jns     short loc_140004665
0x140004632  mov     rcx, [rbp+188h]; this
0x140004639  lea     r8, aWil; "wil"
0x140004640  mov     r9d, eax; char *
0x140004643  mov     edx, 0D6h; void *
0x140004648  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000464d  mov     rcx, rbx; hObject
0x140004650  call    cs:__imp_CloseHandle
0x140004656  test    eax, eax
0x140004658  jz      loc_1400047B9
0x14000465e  mov     eax, edi
0x140004660  jmp     loc_140004764
0x140004665  lea     r8, asc_140016E78; "h"
0x14000466c  mov     rdx, rsi; unsigned __int64
0x14000466f  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140004674  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140004679  lea     r8, [rsp+280h+Name]; lpName
0x14000467e  xor     edx, edx; bInheritHandle
0x140004680  mov     ecx, 1F0003h; dwDesiredAccess
0x140004685  call    cs:__imp_OpenSemaphoreW
0x14000468b  mov     rdi, rax
0x14000468e  test    rax, rax
0x140004691  jz      loc_14000471F
0x140004697  lea     rdx, [rsp+280h+var_260]; int *
0x14000469c  mov     rcx, rax; hHandle
0x14000469f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1400046a4  mov     esi, eax
0x1400046a6  test    eax, eax
0x1400046a8  jns     short loc_1400046EB
0x1400046aa  mov     rcx, [rbp+188h]; this
0x1400046b1  lea     r8, aWil; "wil"
0x1400046b8  mov     r9d, eax; char *
0x1400046bb  mov     edx, 0DEh; void *
0x1400046c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400046c5  mov     rcx, rdi; hObject
0x1400046c8  call    cs:__imp_CloseHandle
0x1400046ce  test    eax, eax
0x1400046d0  jz      loc_1400047CB
0x1400046d6  mov     rcx, rbx; hObject
0x1400046d9  call    cs:__imp_CloseHandle
0x1400046df  test    eax, eax
0x1400046e1  jz      loc_1400047DD
0x1400046e7  mov     eax, esi
0x1400046e9  jmp     short loc_140004764
0x1400046eb  mov     rcx, rdi; hObject
0x1400046ee  call    cs:__imp_CloseHandle
0x1400046f4  test    eax, eax
0x1400046f6  jz      loc_140004783
0x1400046fc  movsxd  rax, [rsp+280h+var_25C]
0x140004701  movsxd  rcx, [rsp+280h+var_260]
0x140004706  shl     rcx, 1Fh
0x14000470a  or      rcx, rax
0x14000470d  mov     [r14], rcx
0x140004710  mov     rcx, rbx; hObject
0x140004713  call    cs:__imp_CloseHandle
0x140004719  test    eax, eax
0x14000471b  jz      short loc_140004795
0x14000471d  jmp     short loc_14000474F
0x14000471f  mov     rcx, [rbp+188h]; this
0x140004726  mov     edx, 0DCh; void *
0x14000472b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140004730  mov     rcx, rbx; hObject
0x140004733  mov     edi, eax
0x140004735  call    cs:__imp_CloseHandle
0x14000473b  test    eax, eax
0x14000473d  jz      short loc_1400047A7
0x14000473f  jmp     loc_14000465E
0x140004744  call    cs:__imp_GetLastError
0x14000474a  cmp     eax, 2
0x14000474d  jnz     short loc_140004753
0x14000474f  xor     eax, eax
0x140004751  jmp     short loc_140004764
0x140004753  mov     rcx, [rbp+188h]; this
0x14000475a  mov     edx, 0D0h; void *
0x14000475f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140004764  mov     rcx, [rbp+180h+var_40]
0x14000476b  xor     rcx, rsp; StackCookie
0x14000476e  call    __security_check_cookie
0x140004773  add     rsp, 258h
0x14000477a  pop     r15
0x14000477c  pop     r14
0x14000477e  pop     rdi
0x14000477f  pop     rsi
0x140004780  pop     rbx
0x140004781  pop     rbp
0x140004782  retn
0x140004783  mov     rcx, [rbp+188h]; this
0x14000478a  mov     edx, 0A0Bh; void *
0x14000478f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004795  mov     rcx, [rbp+188h]; this
0x14000479c  mov     edx, 0A0Bh; void *
0x1400047a1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400047a7  mov     rcx, [rbp+188h]; this
0x1400047ae  mov     edx, 0A0Bh; void *
0x1400047b3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400047b9  mov     rcx, [rbp+188h]; this
0x1400047c0  mov     edx, 0A0Bh; void *
0x1400047c5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400047cb  mov     rcx, [rbp+188h]; this
0x1400047d2  mov     edx, 0A0Bh; void *
0x1400047d7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400047dd  mov     rcx, [rbp+188h]; this
0x1400047e4  mov     edx, 0A0Bh; void *
0x1400047e9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
