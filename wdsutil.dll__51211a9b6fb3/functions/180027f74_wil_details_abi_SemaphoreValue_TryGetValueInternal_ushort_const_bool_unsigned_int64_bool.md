# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180027f74`
- end: `0x180028227`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `691`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180024a60`

## callees

- `0x180025c14`
- `0x1800272d4`
- `0x180027300`
- `0x180027a64`
- `0x180027f74`
- `0x180028824`
- `0x1800319f0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180028175`
- `KERNEL32!GetLastError` at `0x180028175`
- `KERNEL32!CloseHandle` at `0x180028057`
- `KERNEL32!CloseHandle` at `0x1800280d4`
- `KERNEL32!CloseHandle` at `0x1800280eb`
- `KERNEL32!CloseHandle` at `0x180028109`
- `KERNEL32!CloseHandle` at `0x180028134`
- `KERNEL32!CloseHandle` at `0x180028160`
- `KERNEL32!CloseHandle` at `0x180028057`
- `KERNEL32!CloseHandle` at `0x1800280d4`
- `KERNEL32!CloseHandle` at `0x1800280eb`
- `KERNEL32!CloseHandle` at `0x180028109`
- `KERNEL32!CloseHandle` at `0x180028134`
- `KERNEL32!CloseHandle` at `0x180028160`
- `KERNEL32!OpenSemaphoreW` at `0x18002800b`
- `KERNEL32!OpenSemaphoreW` at `0x180028092`
- `KERNEL32!OpenSemaphoreW` at `0x18002800b`
- `KERNEL32!OpenSemaphoreW` at `0x180028092`

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
  unsigned int v12; // r8d
  unsigned int LastError; // edi
  unsigned int v14; // r8d
  const char *v15; // r9
  HANDLE v17; // rax
  unsigned int v18; // r8d
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  unsigned int v22; // r8d
  unsigned int v23; // esi
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
  unsigned int v34; // r8d
  const char *v35; // r9
  int v36; // [rsp+20h] [rbp-E0h] BYREF
  int v37[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v34, v35);
    return 0;
  }
  v37[0] = 0;
  v36 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v37);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore, v36);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v18, v19);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    return LastError;
  }
  v21 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v36);
  v23 = v21;
  if ( v21 >= 0 )
  {
    if ( !CloseHandle(v20) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    *a3 = v37[0] | (unsigned __int64)((__int64)v36 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v22, (const char *)(unsigned int)v21, v36);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
  return v23;
}

```

## disassembly

```asm
0x180027f74  push    rbp
0x180027f76  push    rbx
0x180027f77  push    rsi
0x180027f78  push    rdi
0x180027f79  push    r14
0x180027f7b  push    r15
0x180027f7d  lea     rbp, [rsp-158h]
0x180027f85  sub     rsp, 258h
0x180027f8c  mov     rax, cs:__security_cookie
0x180027f93  xor     rax, rsp
0x180027f96  mov     [rbp+180h+var_40], rax
0x180027f9d  xor     r15d, r15d
0x180027fa0  lea     rax, [rsp+280h+Name]
0x180027fa5  mov     esi, 104h
0x180027faa  mov     [r8], r15
0x180027fad  mov     edx, esi
0x180027faf  mov     r14, r8
0x180027fb2  mov     r9d, 7FFFFFFEh
0x180027fb8  test    r9, r9
0x180027fbb  jz      short loc_180027FDC
0x180027fbd  movzx   r8d, word ptr [rcx]
0x180027fc1  test    r8w, r8w
0x180027fc5  jz      short loc_180027FDC
0x180027fc7  mov     [rax], r8w
0x180027fcb  add     rcx, 2
0x180027fcf  add     rax, 2
0x180027fd3  dec     r9
0x180027fd6  sub     rdx, 1
0x180027fda  jnz     short loc_180027FB8
0x180027fdc  test    rdx, rdx
0x180027fdf  lea     rcx, [rax-2]
0x180027fe3  lea     r8, aP0; "_p0"
0x180027fea  mov     rdx, rsi; unsigned __int64
0x180027fed  cmovnz  rcx, rax
0x180027ff1  mov     [rcx], r15w
0x180027ff5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180027ffa  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180027fff  lea     r8, [rsp+280h+Name]; lpName
0x180028004  xor     edx, edx; bInheritHandle
0x180028006  mov     ecx, 1F0003h; dwDesiredAccess
0x18002800b  call    cs:__imp_OpenSemaphoreW
0x180028012  nop     dword ptr [rax+rax+00h]
0x180028017  mov     rbx, rax
0x18002801a  test    rax, rax
0x18002801d  jz      loc_180028175
0x180028023  lea     rdx, [rsp+280h+var_25C]; int *
0x180028028  mov     [rsp+280h+var_25C], r15d
0x18002802d  mov     rcx, rax; hHandle
0x180028030  mov     [rsp+280h+var_260], r15d; int
0x180028035  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18002803a  mov     edi, eax
0x18002803c  test    eax, eax
0x18002803e  jns     short loc_180028072
0x180028040  mov     rcx, [rbp+188h]; this
0x180028047  mov     r9d, eax; char *
0x18002804a  mov     edx, 0D6h; void *
0x18002804f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028054  mov     rcx, rbx; hObject
0x180028057  call    cs:__imp_CloseHandle
0x18002805e  nop     dword ptr [rax+rax+00h]
0x180028063  test    eax, eax
0x180028065  jz      loc_1800281F1
0x18002806b  mov     eax, edi
0x18002806d  jmp     loc_18002819B
0x180028072  lea     r8, asc_18003B738; "h"
0x180028079  mov     rdx, rsi; unsigned __int64
0x18002807c  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180028081  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180028086  lea     r8, [rsp+280h+Name]; lpName
0x18002808b  xor     edx, edx; bInheritHandle
0x18002808d  mov     ecx, 1F0003h; dwDesiredAccess
0x180028092  call    cs:__imp_OpenSemaphoreW
0x180028099  nop     dword ptr [rax+rax+00h]
0x18002809e  mov     rdi, rax
0x1800280a1  test    rax, rax
0x1800280a4  jz      loc_18002814A
0x1800280aa  lea     rdx, [rsp+280h+var_260]; int *
0x1800280af  mov     rcx, rax; hHandle
0x1800280b2  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800280b7  mov     esi, eax
0x1800280b9  test    eax, eax
0x1800280bb  jns     short loc_180028106
0x1800280bd  mov     rcx, [rbp+188h]; this
0x1800280c4  mov     r9d, eax; char *
0x1800280c7  mov     edx, 0DEh; void *
0x1800280cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800280d1  mov     rcx, rdi; hObject
0x1800280d4  call    cs:__imp_CloseHandle
0x1800280db  nop     dword ptr [rax+rax+00h]
0x1800280e0  test    eax, eax
0x1800280e2  jz      loc_180028203
0x1800280e8  mov     rcx, rbx; hObject
0x1800280eb  call    cs:__imp_CloseHandle
0x1800280f2  nop     dword ptr [rax+rax+00h]
0x1800280f7  test    eax, eax
0x1800280f9  jz      loc_180028215
0x1800280ff  mov     eax, esi
0x180028101  jmp     loc_18002819B
0x180028106  mov     rcx, rdi; hObject
0x180028109  call    cs:__imp_CloseHandle
0x180028110  nop     dword ptr [rax+rax+00h]
0x180028115  test    eax, eax
0x180028117  jz      loc_1800281BB
0x18002811d  movsxd  rax, [rsp+280h+var_25C]
0x180028122  movsxd  rcx, [rsp+280h+var_260]
0x180028127  shl     rcx, 1Fh
0x18002812b  or      rcx, rax
0x18002812e  mov     [r14], rcx
0x180028131  mov     rcx, rbx; hObject
0x180028134  call    cs:__imp_CloseHandle
0x18002813b  nop     dword ptr [rax+rax+00h]
0x180028140  test    eax, eax
0x180028142  jz      loc_1800281CD
0x180028148  jmp     short loc_180028186
0x18002814a  mov     rcx, [rbp+188h]; this
0x180028151  mov     edx, 0DCh; void *
0x180028156  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002815b  mov     rcx, rbx; hObject
0x18002815e  mov     edi, eax
0x180028160  call    cs:__imp_CloseHandle
0x180028167  nop     dword ptr [rax+rax+00h]
0x18002816c  test    eax, eax
0x18002816e  jz      short loc_1800281DF
0x180028170  jmp     loc_18002806B
0x180028175  call    cs:__imp_GetLastError
0x18002817c  nop     dword ptr [rax+rax+00h]
0x180028181  cmp     eax, 2
0x180028184  jnz     short loc_18002818A
0x180028186  xor     eax, eax
0x180028188  jmp     short loc_18002819B
0x18002818a  mov     rcx, [rbp+188h]; this
0x180028191  mov     edx, 0D0h; void *
0x180028196  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002819b  mov     rcx, [rbp+180h+var_40]
0x1800281a2  xor     rcx, rsp; StackCookie
0x1800281a5  call    __security_check_cookie
0x1800281aa  add     rsp, 258h
0x1800281b1  pop     r15
0x1800281b3  pop     r14
0x1800281b5  pop     rdi
0x1800281b6  pop     rsi
0x1800281b7  pop     rbx
0x1800281b8  pop     rbp
0x1800281b9  retn
0x1800281bb  mov     rcx, [rbp+188h]; this
0x1800281c2  mov     edx, 0A0Bh; void *
0x1800281c7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800281cd  mov     rcx, [rbp+188h]; this
0x1800281d4  mov     edx, 0A0Bh; void *
0x1800281d9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800281df  mov     rcx, [rbp+188h]; this
0x1800281e6  mov     edx, 0A0Bh; void *
0x1800281eb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800281f1  mov     rcx, [rbp+188h]; this
0x1800281f8  mov     edx, 0A0Bh; void *
0x1800281fd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180028203  mov     rcx, [rbp+188h]; this
0x18002820a  mov     edx, 0A0Bh; void *
0x18002820f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180028215  mov     rcx, [rbp+188h]; this
0x18002821c  mov     edx, 0A0Bh; void *
0x180028221  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
