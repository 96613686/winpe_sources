# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x14000697c`
- end: `0x140006be8`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140003bd0`

## callees

- `0x140004a94`
- `0x140005514`
- `0x14000553c`
- `0x140006810`
- `0x14000697c`
- `0x140006e3c`
- `0x140007770`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140006a56`
- `KERNEL32!CloseHandle` at `0x140006ac1`
- `KERNEL32!CloseHandle` at `0x140006ad2`
- `KERNEL32!CloseHandle` at `0x140006ae7`
- `KERNEL32!CloseHandle` at `0x140006b0c`
- `KERNEL32!CloseHandle` at `0x140006b2e`
- `KERNEL32!CloseHandle` at `0x140006a56`
- `KERNEL32!CloseHandle` at `0x140006ac1`
- `KERNEL32!CloseHandle` at `0x140006ad2`
- `KERNEL32!CloseHandle` at `0x140006ae7`
- `KERNEL32!CloseHandle` at `0x140006b0c`
- `KERNEL32!CloseHandle` at `0x140006b2e`
- `KERNEL32!OpenSemaphoreW` at `0x140006a10`
- `KERNEL32!OpenSemaphoreW` at `0x140006a85`
- `KERNEL32!OpenSemaphoreW` at `0x140006a10`
- `KERNEL32!OpenSemaphoreW` at `0x140006a85`
- `KERNEL32!GetLastError` at `0x140006b3d`
- `KERNEL32!GetLastError` at `0x140006b3d`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v6; // rdx
  __int64 v7; // r9
  WCHAR *v8; // rcx
  HANDLE v9; // rax
  void *v10; // rbx
  int ValueFromSemaphore; // eax
  __int64 v12; // rdx
  int v13; // r8d
  unsigned int LastError; // edi
  __int64 v15; // r8
  const char *v16; // r9
  HANDLE v18; // rax
  __int64 v19; // r8
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
  __int64 v35; // r8
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
0x14000697c  push    rbp
0x14000697e  push    rbx
0x14000697f  push    rsi
0x140006980  push    rdi
0x140006981  push    r14
0x140006983  push    r15
0x140006985  lea     rbp, [rsp-158h]
0x14000698d  sub     rsp, 258h
0x140006994  mov     rax, cs:__security_cookie
0x14000699b  xor     rax, rsp
0x14000699e  mov     [rbp+180h+var_40], rax
0x1400069a5  xor     r15d, r15d
0x1400069a8  lea     rax, [rsp+280h+Name]
0x1400069ad  mov     [r8], r15
0x1400069b0  mov     r14, r8
0x1400069b3  mov     edx, 104h
0x1400069b8  mov     r9d, 7FFFFFFEh
0x1400069be  test    r9, r9
0x1400069c1  jz      short loc_1400069E2
0x1400069c3  movzx   r8d, word ptr [rcx]
0x1400069c7  test    r8w, r8w
0x1400069cb  jz      short loc_1400069E2
0x1400069cd  mov     [rax], r8w
0x1400069d1  add     rcx, 2
0x1400069d5  add     rax, 2
0x1400069d9  dec     r9
0x1400069dc  sub     rdx, 1; unsigned __int64
0x1400069e0  jnz     short loc_1400069BE
0x1400069e2  test    rdx, rdx
0x1400069e5  lea     rcx, [rax-2]
0x1400069e9  lea     r8, aP0; "_p0"
0x1400069f0  cmovnz  rcx, rax
0x1400069f4  mov     [rcx], r15w
0x1400069f8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400069fd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140006a02  mov     esi, 1F0003h
0x140006a07  lea     r8, [rsp+280h+Name]; lpName
0x140006a0c  mov     ecx, esi; dwDesiredAccess
0x140006a0e  xor     edx, edx; bInheritHandle
0x140006a10  call    cs:__imp_OpenSemaphoreW
0x140006a16  mov     rbx, rax
0x140006a19  test    rax, rax
0x140006a1c  jz      loc_140006B3D
0x140006a22  lea     rdx, [rsp+280h+var_25C]; int *
0x140006a27  mov     [rsp+280h+var_25C], r15d
0x140006a2c  mov     rcx, rax; hHandle
0x140006a2f  mov     [rsp+280h+var_260], r15d; int
0x140006a34  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140006a39  mov     edi, eax
0x140006a3b  test    eax, eax
0x140006a3d  jns     short loc_140006A6B
0x140006a3f  mov     rcx, [rbp+188h]; this
0x140006a46  mov     r9d, eax; char *
0x140006a49  mov     edx, 0D6h; void *
0x140006a4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006a53  mov     rcx, rbx; hObject
0x140006a56  call    cs:__imp_CloseHandle
0x140006a5c  test    eax, eax
0x140006a5e  jz      loc_140006BB2
0x140006a64  mov     eax, edi
0x140006a66  jmp     loc_140006B5D
0x140006a6b  lea     r8, asc_14000B118; "h"
0x140006a72  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140006a77  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140006a7c  lea     r8, [rsp+280h+Name]; lpName
0x140006a81  xor     edx, edx; bInheritHandle
0x140006a83  mov     ecx, esi; dwDesiredAccess
0x140006a85  call    cs:__imp_OpenSemaphoreW
0x140006a8b  mov     rdi, rax
0x140006a8e  test    rax, rax
0x140006a91  jz      loc_140006B18
0x140006a97  lea     rdx, [rsp+280h+var_260]; int *
0x140006a9c  mov     rcx, rax; hHandle
0x140006a9f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140006aa4  mov     esi, eax
0x140006aa6  test    eax, eax
0x140006aa8  jns     short loc_140006AE4
0x140006aaa  mov     rcx, [rbp+188h]; this
0x140006ab1  mov     r9d, eax; char *
0x140006ab4  mov     edx, 0DEh; void *
0x140006ab9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006abe  mov     rcx, rdi; hObject
0x140006ac1  call    cs:__imp_CloseHandle
0x140006ac7  test    eax, eax
0x140006ac9  jz      loc_140006BC4
0x140006acf  mov     rcx, rbx; hObject
0x140006ad2  call    cs:__imp_CloseHandle
0x140006ad8  test    eax, eax
0x140006ada  jz      loc_140006BD6
0x140006ae0  mov     eax, esi
0x140006ae2  jmp     short loc_140006B5D
0x140006ae4  mov     rcx, rdi; hObject
0x140006ae7  call    cs:__imp_CloseHandle
0x140006aed  test    eax, eax
0x140006aef  jz      loc_140006B7C
0x140006af5  movsxd  rax, [rsp+280h+var_25C]
0x140006afa  movsxd  rcx, [rsp+280h+var_260]
0x140006aff  shl     rcx, 1Fh
0x140006b03  or      rcx, rax
0x140006b06  mov     [r14], rcx
0x140006b09  mov     rcx, rbx; hObject
0x140006b0c  call    cs:__imp_CloseHandle
0x140006b12  test    eax, eax
0x140006b14  jz      short loc_140006B8E
0x140006b16  jmp     short loc_140006B48
0x140006b18  mov     rcx, [rbp+188h]; this
0x140006b1f  mov     edx, 0DCh; void *
0x140006b24  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140006b29  mov     rcx, rbx; hObject
0x140006b2c  mov     edi, eax
0x140006b2e  call    cs:__imp_CloseHandle
0x140006b34  test    eax, eax
0x140006b36  jz      short loc_140006BA0
0x140006b38  jmp     loc_140006A64
0x140006b3d  call    cs:__imp_GetLastError
0x140006b43  cmp     eax, 2
0x140006b46  jnz     short loc_140006B4C
0x140006b48  xor     eax, eax
0x140006b4a  jmp     short loc_140006B5D
0x140006b4c  mov     rcx, [rbp+188h]; this
0x140006b53  mov     edx, 0D0h; void *
0x140006b58  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140006b5d  mov     rcx, [rbp+180h+var_40]
0x140006b64  xor     rcx, rsp; StackCookie
0x140006b67  call    __security_check_cookie
0x140006b6c  add     rsp, 258h
0x140006b73  pop     r15
0x140006b75  pop     r14
0x140006b77  pop     rdi
0x140006b78  pop     rsi
0x140006b79  pop     rbx
0x140006b7a  pop     rbp
0x140006b7b  retn
0x140006b7c  mov     rcx, [rbp+188h]; this
0x140006b83  mov     edx, 0A0Bh; void *
0x140006b88  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006b8e  mov     rcx, [rbp+188h]; this
0x140006b95  mov     edx, 0A0Bh; void *
0x140006b9a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006ba0  mov     rcx, [rbp+188h]; this
0x140006ba7  mov     edx, 0A0Bh; void *
0x140006bac  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006bb2  mov     rcx, [rbp+188h]; this
0x140006bb9  mov     edx, 0A0Bh; void *
0x140006bbe  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006bc4  mov     rcx, [rbp+188h]; this
0x140006bcb  mov     edx, 0A0Bh; void *
0x140006bd0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140006bd6  mov     rcx, [rbp+188h]; this
0x140006bdd  mov     edx, 0A0Bh; void *
0x140006be2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
