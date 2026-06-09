# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x140004ee8`
- end: `0x140005154`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1400038f0`

## callees

- `0x140004354`
- `0x140004bb4`
- `0x140004bd4`
- `0x140004bf8`
- `0x140004ee8`
- `0x140005474`
- `0x1400175a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400050a9`
- `KERNEL32!GetLastError` at `0x1400050a9`
- `KERNEL32!OpenSemaphoreW` at `0x140004f7c`
- `KERNEL32!OpenSemaphoreW` at `0x140004ff1`
- `KERNEL32!OpenSemaphoreW` at `0x140004f7c`
- `KERNEL32!OpenSemaphoreW` at `0x140004ff1`
- `KERNEL32!CloseHandle` at `0x140004fc2`
- `KERNEL32!CloseHandle` at `0x14000502d`
- `KERNEL32!CloseHandle` at `0x14000503e`
- `KERNEL32!CloseHandle` at `0x140005053`
- `KERNEL32!CloseHandle` at `0x140005078`
- `KERNEL32!CloseHandle` at `0x14000509a`
- `KERNEL32!CloseHandle` at `0x140004fc2`
- `KERNEL32!CloseHandle` at `0x14000502d`
- `KERNEL32!CloseHandle` at `0x14000503e`
- `KERNEL32!CloseHandle` at `0x140005053`
- `KERNEL32!CloseHandle` at `0x140005078`
- `KERNEL32!CloseHandle` at `0x14000509a`

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
0x140004ee8  push    rbp
0x140004eea  push    rbx
0x140004eeb  push    rsi
0x140004eec  push    rdi
0x140004eed  push    r14
0x140004eef  push    r15
0x140004ef1  lea     rbp, [rsp-158h]
0x140004ef9  sub     rsp, 258h
0x140004f00  mov     rax, cs:__security_cookie
0x140004f07  xor     rax, rsp
0x140004f0a  mov     [rbp+180h+var_40], rax
0x140004f11  xor     r15d, r15d
0x140004f14  lea     rax, [rsp+280h+Name]
0x140004f19  mov     [r8], r15
0x140004f1c  mov     r14, r8
0x140004f1f  mov     edx, 104h
0x140004f24  mov     r9d, 7FFFFFFEh
0x140004f2a  test    r9, r9
0x140004f2d  jz      short loc_140004F4E
0x140004f2f  movzx   r8d, word ptr [rcx]
0x140004f33  test    r8w, r8w
0x140004f37  jz      short loc_140004F4E
0x140004f39  mov     [rax], r8w
0x140004f3d  add     rcx, 2
0x140004f41  add     rax, 2
0x140004f45  dec     r9
0x140004f48  sub     rdx, 1; unsigned __int64
0x140004f4c  jnz     short loc_140004F2A
0x140004f4e  test    rdx, rdx
0x140004f51  lea     rcx, [rax-2]
0x140004f55  lea     r8, aP0; "_p0"
0x140004f5c  cmovnz  rcx, rax
0x140004f60  mov     [rcx], r15w
0x140004f64  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140004f69  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140004f6e  mov     esi, 1F0003h
0x140004f73  lea     r8, [rsp+280h+Name]; lpName
0x140004f78  mov     ecx, esi; dwDesiredAccess
0x140004f7a  xor     edx, edx; bInheritHandle
0x140004f7c  call    cs:__imp_OpenSemaphoreW
0x140004f82  mov     rbx, rax
0x140004f85  test    rax, rax
0x140004f88  jz      loc_1400050A9
0x140004f8e  lea     rdx, [rsp+280h+var_25C]; int *
0x140004f93  mov     [rsp+280h+var_25C], r15d
0x140004f98  mov     rcx, rax; hHandle
0x140004f9b  mov     [rsp+280h+var_260], r15d; int
0x140004fa0  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140004fa5  mov     edi, eax
0x140004fa7  test    eax, eax
0x140004fa9  jns     short loc_140004FD7
0x140004fab  mov     rcx, [rbp+188h]; this
0x140004fb2  mov     r9d, eax; char *
0x140004fb5  mov     edx, 0D6h; void *
0x140004fba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004fbf  mov     rcx, rbx; hObject
0x140004fc2  call    cs:__imp_CloseHandle
0x140004fc8  test    eax, eax
0x140004fca  jz      loc_14000511E
0x140004fd0  mov     eax, edi
0x140004fd2  jmp     loc_1400050C9
0x140004fd7  lea     r8, asc_14001B0C8; "h"
0x140004fde  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140004fe3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140004fe8  lea     r8, [rsp+280h+Name]; lpName
0x140004fed  xor     edx, edx; bInheritHandle
0x140004fef  mov     ecx, esi; dwDesiredAccess
0x140004ff1  call    cs:__imp_OpenSemaphoreW
0x140004ff7  mov     rdi, rax
0x140004ffa  test    rax, rax
0x140004ffd  jz      loc_140005084
0x140005003  lea     rdx, [rsp+280h+var_260]; int *
0x140005008  mov     rcx, rax; hHandle
0x14000500b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140005010  mov     esi, eax
0x140005012  test    eax, eax
0x140005014  jns     short loc_140005050
0x140005016  mov     rcx, [rbp+188h]; this
0x14000501d  mov     r9d, eax; char *
0x140005020  mov     edx, 0DEh; void *
0x140005025  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000502a  mov     rcx, rdi; hObject
0x14000502d  call    cs:__imp_CloseHandle
0x140005033  test    eax, eax
0x140005035  jz      loc_140005130
0x14000503b  mov     rcx, rbx; hObject
0x14000503e  call    cs:__imp_CloseHandle
0x140005044  test    eax, eax
0x140005046  jz      loc_140005142
0x14000504c  mov     eax, esi
0x14000504e  jmp     short loc_1400050C9
0x140005050  mov     rcx, rdi; hObject
0x140005053  call    cs:__imp_CloseHandle
0x140005059  test    eax, eax
0x14000505b  jz      loc_1400050E8
0x140005061  movsxd  rax, [rsp+280h+var_25C]
0x140005066  movsxd  rcx, [rsp+280h+var_260]
0x14000506b  shl     rcx, 1Fh
0x14000506f  or      rcx, rax
0x140005072  mov     [r14], rcx
0x140005075  mov     rcx, rbx; hObject
0x140005078  call    cs:__imp_CloseHandle
0x14000507e  test    eax, eax
0x140005080  jz      short loc_1400050FA
0x140005082  jmp     short loc_1400050B4
0x140005084  mov     rcx, [rbp+188h]; this
0x14000508b  mov     edx, 0DCh; void *
0x140005090  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140005095  mov     rcx, rbx; hObject
0x140005098  mov     edi, eax
0x14000509a  call    cs:__imp_CloseHandle
0x1400050a0  test    eax, eax
0x1400050a2  jz      short loc_14000510C
0x1400050a4  jmp     loc_140004FD0
0x1400050a9  call    cs:__imp_GetLastError
0x1400050af  cmp     eax, 2
0x1400050b2  jnz     short loc_1400050B8
0x1400050b4  xor     eax, eax
0x1400050b6  jmp     short loc_1400050C9
0x1400050b8  mov     rcx, [rbp+188h]; this
0x1400050bf  mov     edx, 0D0h; void *
0x1400050c4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400050c9  mov     rcx, [rbp+180h+var_40]
0x1400050d0  xor     rcx, rsp; StackCookie
0x1400050d3  call    __security_check_cookie
0x1400050d8  add     rsp, 258h
0x1400050df  pop     r15
0x1400050e1  pop     r14
0x1400050e3  pop     rdi
0x1400050e4  pop     rsi
0x1400050e5  pop     rbx
0x1400050e6  pop     rbp
0x1400050e7  retn
0x1400050e8  mov     rcx, [rbp+188h]; this
0x1400050ef  mov     edx, 0A0Bh; void *
0x1400050f4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400050fa  mov     rcx, [rbp+188h]; this
0x140005101  mov     edx, 0A0Bh; void *
0x140005106  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000510c  mov     rcx, [rbp+188h]; this
0x140005113  mov     edx, 0A0Bh; void *
0x140005118  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000511e  mov     rcx, [rbp+188h]; this
0x140005125  mov     edx, 0A0Bh; void *
0x14000512a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005130  mov     rcx, [rbp+188h]; this
0x140005137  mov     edx, 0A0Bh; void *
0x14000513c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005142  mov     rcx, [rbp+188h]; this
0x140005149  mov     edx, 0A0Bh; void *
0x14000514e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
