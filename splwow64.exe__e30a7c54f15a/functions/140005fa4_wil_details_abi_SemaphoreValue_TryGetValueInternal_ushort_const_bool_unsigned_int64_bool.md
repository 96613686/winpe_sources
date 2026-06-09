# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x140005fa4`
- end: `0x140006210`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1400036fc`
- `0x140009214`

## callees

- `0x140001ee0`
- `0x1400049c0`
- `0x140005b34`
- `0x140005b54`
- `0x140005e68`
- `0x140005fa4`
- `0x14000636c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140006165`
- `KERNEL32!GetLastError` at `0x140006165`
- `KERNEL32!OpenSemaphoreW` at `0x140006038`
- `KERNEL32!OpenSemaphoreW` at `0x1400060ad`
- `KERNEL32!OpenSemaphoreW` at `0x140006038`
- `KERNEL32!OpenSemaphoreW` at `0x1400060ad`
- `KERNEL32!CloseHandle` at `0x14000607e`
- `KERNEL32!CloseHandle` at `0x1400060e9`
- `KERNEL32!CloseHandle` at `0x1400060fa`
- `KERNEL32!CloseHandle` at `0x14000610f`
- `KERNEL32!CloseHandle` at `0x140006134`
- `KERNEL32!CloseHandle` at `0x140006156`
- `KERNEL32!CloseHandle` at `0x14000607e`
- `KERNEL32!CloseHandle` at `0x1400060e9`
- `KERNEL32!CloseHandle` at `0x1400060fa`
- `KERNEL32!CloseHandle` at `0x14000610f`
- `KERNEL32!CloseHandle` at `0x140006134`
- `KERNEL32!CloseHandle` at `0x140006156`

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
0x140005fa4  push    rbp
0x140005fa6  push    rbx
0x140005fa7  push    rsi
0x140005fa8  push    rdi
0x140005fa9  push    r14
0x140005fab  push    r15
0x140005fad  lea     rbp, [rsp-158h]
0x140005fb5  sub     rsp, 258h
0x140005fbc  mov     rax, cs:__security_cookie
0x140005fc3  xor     rax, rsp
0x140005fc6  mov     [rbp+180h+var_40], rax
0x140005fcd  xor     r15d, r15d
0x140005fd0  lea     rax, [rsp+280h+Name]
0x140005fd5  mov     [r8], r15
0x140005fd8  mov     r14, r8
0x140005fdb  mov     edx, 104h
0x140005fe0  mov     r9d, 7FFFFFFEh
0x140005fe6  test    r9, r9
0x140005fe9  jz      short loc_14000600A
0x140005feb  movzx   r8d, word ptr [rcx]
0x140005fef  test    r8w, r8w
0x140005ff3  jz      short loc_14000600A
0x140005ff5  mov     [rax], r8w
0x140005ff9  add     rcx, 2
0x140005ffd  add     rax, 2
0x140006001  dec     r9
0x140006004  sub     rdx, 1; unsigned __int64
0x140006008  jnz     short loc_140005FE6
0x14000600a  test    rdx, rdx
0x14000600d  lea     rcx, [rax-2]
0x140006011  lea     r8, aP0; "_p0"
0x140006018  cmovnz  rcx, rax
0x14000601c  mov     [rcx], r15w
0x140006020  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140006025  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000602a  mov     esi, 1F0003h
0x14000602f  lea     r8, [rsp+280h+Name]; lpName
0x140006034  mov     ecx, esi; dwDesiredAccess
0x140006036  xor     edx, edx; bInheritHandle
0x140006038  call    cs:__imp_OpenSemaphoreW
0x14000603e  mov     rbx, rax
0x140006041  test    rax, rax
0x140006044  jz      loc_140006165
0x14000604a  lea     rdx, [rsp+280h+var_25C]; int *
0x14000604f  mov     [rsp+280h+var_25C], r15d
0x140006054  mov     rcx, rax; hHandle
0x140006057  mov     [rsp+280h+var_260], r15d; int
0x14000605c  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140006061  mov     edi, eax
0x140006063  test    eax, eax
0x140006065  jns     short loc_140006093
0x140006067  mov     rcx, [rbp+188h]; this
0x14000606e  mov     r9d, eax; char *
0x140006071  mov     edx, 0D6h; void *
0x140006076  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000607b  mov     rcx, rbx; hObject
0x14000607e  call    cs:__imp_CloseHandle
0x140006084  test    eax, eax
0x140006086  jz      loc_1400061DA
0x14000608c  mov     eax, edi
0x14000608e  jmp     loc_140006185
0x140006093  lea     r8, asc_140019528; "h"
0x14000609a  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000609f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400060a4  lea     r8, [rsp+280h+Name]; lpName
0x1400060a9  xor     edx, edx; bInheritHandle
0x1400060ab  mov     ecx, esi; dwDesiredAccess
0x1400060ad  call    cs:__imp_OpenSemaphoreW
0x1400060b3  mov     rdi, rax
0x1400060b6  test    rax, rax
0x1400060b9  jz      loc_140006140
0x1400060bf  lea     rdx, [rsp+280h+var_260]; int *
0x1400060c4  mov     rcx, rax; hHandle
0x1400060c7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1400060cc  mov     esi, eax
0x1400060ce  test    eax, eax
0x1400060d0  jns     short loc_14000610C
0x1400060d2  mov     rcx, [rbp+188h]; this
0x1400060d9  mov     r9d, eax; char *
0x1400060dc  mov     edx, 0DEh; void *
0x1400060e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400060e6  mov     rcx, rdi; hObject
0x1400060e9  call    cs:__imp_CloseHandle
0x1400060ef  test    eax, eax
0x1400060f1  jz      loc_1400061EC
0x1400060f7  mov     rcx, rbx; hObject
0x1400060fa  call    cs:__imp_CloseHandle
0x140006100  test    eax, eax
0x140006102  jz      loc_1400061FE
0x140006108  mov     eax, esi
0x14000610a  jmp     short loc_140006185
0x14000610c  mov     rcx, rdi; hObject
0x14000610f  call    cs:__imp_CloseHandle
0x140006115  test    eax, eax
0x140006117  jz      loc_1400061A4
0x14000611d  movsxd  rax, [rsp+280h+var_25C]
0x140006122  movsxd  rcx, [rsp+280h+var_260]
0x140006127  shl     rcx, 1Fh
0x14000612b  or      rcx, rax
0x14000612e  mov     [r14], rcx
0x140006131  mov     rcx, rbx; hObject
0x140006134  call    cs:__imp_CloseHandle
0x14000613a  test    eax, eax
0x14000613c  jz      short loc_1400061B6
0x14000613e  jmp     short loc_140006170
0x140006140  mov     rcx, [rbp+188h]; this
0x140006147  mov     edx, 0DCh; void *
0x14000614c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140006151  mov     rcx, rbx; hObject
0x140006154  mov     edi, eax
0x140006156  call    cs:__imp_CloseHandle
0x14000615c  test    eax, eax
0x14000615e  jz      short loc_1400061C8
0x140006160  jmp     loc_14000608C
0x140006165  call    cs:__imp_GetLastError
0x14000616b  cmp     eax, 2
0x14000616e  jnz     short loc_140006174
0x140006170  xor     eax, eax
0x140006172  jmp     short loc_140006185
0x140006174  mov     rcx, [rbp+188h]; this
0x14000617b  mov     edx, 0D0h; void *
0x140006180  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140006185  mov     rcx, [rbp+180h+var_40]
0x14000618c  xor     rcx, rsp; StackCookie
0x14000618f  call    __security_check_cookie
0x140006194  add     rsp, 258h
0x14000619b  pop     r15
0x14000619d  pop     r14
0x14000619f  pop     rdi
0x1400061a0  pop     rsi
0x1400061a1  pop     rbx
0x1400061a2  pop     rbp
0x1400061a3  retn
0x1400061a4  mov     rcx, [rbp+188h]; this
0x1400061ab  mov     edx, 0A0Bh; void *
0x1400061b0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400061b6  mov     rcx, [rbp+188h]; this
0x1400061bd  mov     edx, 0A0Bh; void *
0x1400061c2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400061c8  mov     rcx, [rbp+188h]; this
0x1400061cf  mov     edx, 0A0Bh; void *
0x1400061d4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400061da  mov     rcx, [rbp+188h]; this
0x1400061e1  mov     edx, 0A0Bh; void *
0x1400061e6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400061ec  mov     rcx, [rbp+188h]; this
0x1400061f3  mov     edx, 0A0Bh; void *
0x1400061f8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400061fe  mov     rcx, [rbp+188h]; this
0x140006205  mov     edx, 0A0Bh; void *
0x14000620a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
