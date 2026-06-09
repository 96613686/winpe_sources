# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800141ac`
- end: `0x180014418`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18001078c`
- `0x180010b30`

## callees

- `0x18000e280`
- `0x180011fb0`
- `0x180013af0`
- `0x180013b10`
- `0x1800141ac`
- `0x18001499c`
- `0x1800157f0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001436d`
- `KERNEL32!GetLastError` at `0x18001436d`
- `KERNEL32!CloseHandle` at `0x180014286`
- `KERNEL32!CloseHandle` at `0x1800142f1`
- `KERNEL32!CloseHandle` at `0x180014302`
- `KERNEL32!CloseHandle` at `0x180014317`
- `KERNEL32!CloseHandle` at `0x18001433c`
- `KERNEL32!CloseHandle` at `0x18001435e`
- `KERNEL32!CloseHandle` at `0x180014286`
- `KERNEL32!CloseHandle` at `0x1800142f1`
- `KERNEL32!CloseHandle` at `0x180014302`
- `KERNEL32!CloseHandle` at `0x180014317`
- `KERNEL32!CloseHandle` at `0x18001433c`
- `KERNEL32!CloseHandle` at `0x18001435e`
- `KERNEL32!OpenSemaphoreW` at `0x180014240`
- `KERNEL32!OpenSemaphoreW` at `0x1800142b5`
- `KERNEL32!OpenSemaphoreW` at `0x180014240`
- `KERNEL32!OpenSemaphoreW` at `0x1800142b5`

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
0x1800141ac  push    rbp
0x1800141ae  push    rbx
0x1800141af  push    rsi
0x1800141b0  push    rdi
0x1800141b1  push    r14
0x1800141b3  push    r15
0x1800141b5  lea     rbp, [rsp-158h]
0x1800141bd  sub     rsp, 258h
0x1800141c4  mov     rax, cs:__security_cookie
0x1800141cb  xor     rax, rsp
0x1800141ce  mov     [rbp+180h+var_40], rax
0x1800141d5  xor     r15d, r15d
0x1800141d8  lea     rax, [rsp+280h+Name]
0x1800141dd  mov     [r8], r15
0x1800141e0  mov     r14, r8
0x1800141e3  mov     edx, 104h
0x1800141e8  mov     r9d, 7FFFFFFEh
0x1800141ee  test    r9, r9
0x1800141f1  jz      short loc_180014212
0x1800141f3  movzx   r8d, word ptr [rcx]
0x1800141f7  test    r8w, r8w
0x1800141fb  jz      short loc_180014212
0x1800141fd  mov     [rax], r8w
0x180014201  add     rcx, 2
0x180014205  add     rax, 2
0x180014209  dec     r9
0x18001420c  sub     rdx, 1; unsigned __int64
0x180014210  jnz     short loc_1800141EE
0x180014212  test    rdx, rdx
0x180014215  lea     rcx, [rax-2]
0x180014219  lea     r8, aP0; "_p0"
0x180014220  cmovnz  rcx, rax
0x180014224  mov     [rcx], r15w
0x180014228  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001422d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180014232  mov     esi, 1F0003h
0x180014237  lea     r8, [rsp+280h+Name]; lpName
0x18001423c  mov     ecx, esi; dwDesiredAccess
0x18001423e  xor     edx, edx; bInheritHandle
0x180014240  call    cs:__imp_OpenSemaphoreW
0x180014246  mov     rbx, rax
0x180014249  test    rax, rax
0x18001424c  jz      loc_18001436D
0x180014252  lea     rdx, [rsp+280h+var_25C]; int *
0x180014257  mov     [rsp+280h+var_25C], r15d
0x18001425c  mov     rcx, rax; hHandle
0x18001425f  mov     [rsp+280h+var_260], r15d; int
0x180014264  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180014269  mov     edi, eax
0x18001426b  test    eax, eax
0x18001426d  jns     short loc_18001429B
0x18001426f  mov     rcx, [rbp+188h]; this
0x180014276  mov     r9d, eax; char *
0x180014279  mov     edx, 0D6h; void *
0x18001427e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014283  mov     rcx, rbx; hObject
0x180014286  call    cs:__imp_CloseHandle
0x18001428c  test    eax, eax
0x18001428e  jz      loc_1800143E2
0x180014294  mov     eax, edi
0x180014296  jmp     loc_18001438D
0x18001429b  lea     r8, asc_18001A518; "h"
0x1800142a2  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800142a7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800142ac  lea     r8, [rsp+280h+Name]; lpName
0x1800142b1  xor     edx, edx; bInheritHandle
0x1800142b3  mov     ecx, esi; dwDesiredAccess
0x1800142b5  call    cs:__imp_OpenSemaphoreW
0x1800142bb  mov     rdi, rax
0x1800142be  test    rax, rax
0x1800142c1  jz      loc_180014348
0x1800142c7  lea     rdx, [rsp+280h+var_260]; int *
0x1800142cc  mov     rcx, rax; hHandle
0x1800142cf  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800142d4  mov     esi, eax
0x1800142d6  test    eax, eax
0x1800142d8  jns     short loc_180014314
0x1800142da  mov     rcx, [rbp+188h]; this
0x1800142e1  mov     r9d, eax; char *
0x1800142e4  mov     edx, 0DEh; void *
0x1800142e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800142ee  mov     rcx, rdi; hObject
0x1800142f1  call    cs:__imp_CloseHandle
0x1800142f7  test    eax, eax
0x1800142f9  jz      loc_1800143F4
0x1800142ff  mov     rcx, rbx; hObject
0x180014302  call    cs:__imp_CloseHandle
0x180014308  test    eax, eax
0x18001430a  jz      loc_180014406
0x180014310  mov     eax, esi
0x180014312  jmp     short loc_18001438D
0x180014314  mov     rcx, rdi; hObject
0x180014317  call    cs:__imp_CloseHandle
0x18001431d  test    eax, eax
0x18001431f  jz      loc_1800143AC
0x180014325  movsxd  rax, [rsp+280h+var_25C]
0x18001432a  movsxd  rcx, [rsp+280h+var_260]
0x18001432f  shl     rcx, 1Fh
0x180014333  or      rcx, rax
0x180014336  mov     [r14], rcx
0x180014339  mov     rcx, rbx; hObject
0x18001433c  call    cs:__imp_CloseHandle
0x180014342  test    eax, eax
0x180014344  jz      short loc_1800143BE
0x180014346  jmp     short loc_180014378
0x180014348  mov     rcx, [rbp+188h]; this
0x18001434f  mov     edx, 0DCh; void *
0x180014354  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180014359  mov     rcx, rbx; hObject
0x18001435c  mov     edi, eax
0x18001435e  call    cs:__imp_CloseHandle
0x180014364  test    eax, eax
0x180014366  jz      short loc_1800143D0
0x180014368  jmp     loc_180014294
0x18001436d  call    cs:__imp_GetLastError
0x180014373  cmp     eax, 2
0x180014376  jnz     short loc_18001437C
0x180014378  xor     eax, eax
0x18001437a  jmp     short loc_18001438D
0x18001437c  mov     rcx, [rbp+188h]; this
0x180014383  mov     edx, 0D0h; void *
0x180014388  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001438d  mov     rcx, [rbp+180h+var_40]
0x180014394  xor     rcx, rsp; StackCookie
0x180014397  call    __security_check_cookie
0x18001439c  add     rsp, 258h
0x1800143a3  pop     r15
0x1800143a5  pop     r14
0x1800143a7  pop     rdi
0x1800143a8  pop     rsi
0x1800143a9  pop     rbx
0x1800143aa  pop     rbp
0x1800143ab  retn
0x1800143ac  mov     rcx, [rbp+188h]; this
0x1800143b3  mov     edx, 0A0Bh; void *
0x1800143b8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800143be  mov     rcx, [rbp+188h]; this
0x1800143c5  mov     edx, 0A0Bh; void *
0x1800143ca  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800143d0  mov     rcx, [rbp+188h]; this
0x1800143d7  mov     edx, 0A0Bh; void *
0x1800143dc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800143e2  mov     rcx, [rbp+188h]; this
0x1800143e9  mov     edx, 0A0Bh; void *
0x1800143ee  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800143f4  mov     rcx, [rbp+188h]; this
0x1800143fb  mov     edx, 0A0Bh; void *
0x180014400  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180014406  mov     rcx, [rbp+188h]; this
0x18001440d  mov     edx, 0A0Bh; void *
0x180014412  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
