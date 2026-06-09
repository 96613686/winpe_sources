# ExtrinsicPropertyStore::LoadBlobDataIntoMemory(ushort const *,uchar * *,uint *,uchar * *,uint *)

- ea: `0x1800838c0`
- end: `0x180083c70`
- name: `?LoadBlobDataIntoMemory@ExtrinsicPropertyStore@@AEAAJPEBGPEAPEAEPEAI12@Z`
- size: `944`
- prototype: `__int64 __fastcall(ExtrinsicPropertyStore *__hidden this, const unsigned __int16 *, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180082bf0`

## callees

- `0x18001adbc`
- `0x180038f50`
- `0x1800838c0`
- `0x180083c80`
- `0x180083c94`
- `0x180278e78`
- `0x1803b1f60`

## import_xrefs

- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180083946`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180083946`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180083a1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180083baa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180083a1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180083baa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083acb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083b45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083b59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083acb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083b45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083b59`
- `cldapi!CfUnlockProperties` at `0x180083b85`
- `cldapi!CfUnlockProperties` at `0x1806620b0`
- `cldapi!CfUnlockProperties` at `0x1806620e0`
- `cldapi!CfUnlockProperties` at `0x180083b85`
- `cldapi!CfUnlockProperties` at `0x1806620b0`
- `cldapi!CfUnlockProperties` at `0x1806620e0`
- `cldapi!CfLockProperties` at `0x180083b05`
- `cldapi!CfLockProperties` at `0x180083b05`

## pseudocode

```c
__int64 __fastcall ExtrinsicPropertyStore::LoadBlobDataIntoMemory(
        ExtrinsicPropertyStore *this,
        const unsigned __int16 *a2,
        unsigned __int8 **a3,
        unsigned int *a4,
        unsigned __int8 **a5,
        unsigned int *a6)
{
  unsigned __int8 *v7; // rsi
  __int64 File2; // rax
  const char *v11; // r9
  char *v12; // rcx
  __int64 v13; // rbx
  __int64 result; // rax
  bool v15; // zf
  int v16; // eax
  unsigned int v17; // ebx
  void *v18; // rbx
  unsigned __int8 *v19; // rax
  int v20; // eax
  unsigned int v21; // r15d
  unsigned int v22; // eax
  char *v23; // rcx
  int v24; // eax
  unsigned int v25; // ebx
  LPVOID v26; // rax
  char *v27; // rcx
  int *v28; // [rsp+20h] [rbp-79h]
  int v29[2]; // [rsp+40h] [rbp-59h] BYREF
  __int64 v30; // [rsp+48h] [rbp-51h]
  __int128 v31; // [rsp+50h] [rbp-49h]
  __int128 v32; // [rsp+60h] [rbp-39h] BYREF
  SIZE_T v33[2]; // [rsp+70h] [rbp-29h]
  SIZE_T cb[2]; // [rsp+80h] [rbp-19h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+4Fh]

  v29[0] = 32;
  v7 = 0;
  *a3 = 0;
  *a4 = 0;
  *a5 = 0;
  v28 = v29;
  *a6 = 0;
  v29[1] = 128;
  v30 = 0x2000000;
  v31 = 0;
  File2 = CreateFile2(a2, 0, 7, 3);
  v12 = (char *)*((_QWORD *)this + 14);
  v13 = File2;
  if ( (unsigned __int64)(v12 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(v12);
  *((_QWORD *)this + 14) = v13;
  if ( (unsigned __int64)(v13 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x96,
             (unsigned int)"onecoreuap\\shell\\windows.storage\\extrinsicpropertystore.cpp",
             v11);
  v15 = (*((_BYTE *)this + 88) & 3) == 0;
  v32 = 0;
  LODWORD(v32) = 65537;
  *(_OWORD *)v33 = 0;
  LODWORD(v33[1]) = 131074;
  *(_OWORD *)cb = 0;
  if ( !v15 )
  {
    LODWORD(v28) = 0;
    v24 = CfLockProperties(v13, &v32, 2, 1);
    v25 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA7,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\extrinsicpropertystore.cpp",
        (const char *)(unsigned int)v24,
        0);
      if ( !*((_BYTE *)this + 120) )
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          (char *)this + 112,
          -1);
      return v25;
    }
    *((_BYTE *)this + 120) = 1;
  }
  v16 = TestHook_RetrieveProperties(*((_QWORD *)this + 14), &v32, 2);
  v17 = v16;
  if ( v16 >= 0 )
    goto LABEL_16;
  if ( v16 != -2147024662 )
  {
    if ( v16 == -2147024895 || v16 == -2147024769 || v16 == -2147024520 || v16 == -2147024506 )
      goto LABEL_16;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB6,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\extrinsicpropertystore.cpp",
      (const char *)(unsigned int)v16,
      (int)v28);
    if ( *((_BYTE *)this + 120) )
    {
      CfUnlockProperties(*((_QWORD *)this + 14), &v32, 2);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        (char *)this + 112,
        -1);
      *((_BYTE *)this + 120) = 0;
    }
    v27 = (char *)*((_QWORD *)this + 14);
    if ( (unsigned __int64)(v27 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(v27);
    result = v17;
    *((_QWORD *)this + 14) = -1;
    return result;
  }
  v18 = 0;
  if ( LODWORD(v33[0]) )
  {
    v26 = CoTaskMemAlloc(LODWORD(v33[0]));
    v18 = v26;
    if ( !v26 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC0,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\extrinsicpropertystore.cpp",
        (const char *)0x8007000ELL,
        (int)v28);
      if ( !*((_BYTE *)this + 120) )
        goto LABEL_50;
      goto LABEL_49;
    }
    *((_QWORD *)&v32 + 1) = v26;
    DWORD1(v32) = v33[0];
  }
  if ( LODWORD(cb[1]) )
  {
    v19 = (unsigned __int8 *)CoTaskMemAlloc(LODWORD(cb[1]));
    v7 = v19;
    if ( v19 )
    {
      cb[0] = (SIZE_T)v19;
      HIDWORD(v33[1]) = cb[1];
      goto LABEL_14;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC7,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\extrinsicpropertystore.cpp",
      (const char *)0x8007000ELL,
      (int)v28);
    if ( v18 )
      CoTaskMemFree(v18);
    if ( !*((_BYTE *)this + 120) )
    {
LABEL_50:
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        (char *)this + 112,
        -1);
      return 2147942414LL;
    }
LABEL_49:
    CfUnlockProperties(*((_QWORD *)this + 14), &v32, 2);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)this + 112,
      -1);
    *((_BYTE *)this + 120) = 0;
    goto LABEL_50;
  }
LABEL_14:
  v20 = TestHook_RetrieveProperties(*((_QWORD *)this + 14), &v32, 2);
  v21 = v20;
  if ( v20 >= 0 )
  {
    v22 = v33[0];
    *a3 = (unsigned __int8 *)v18;
    *a4 = v22;
    *a5 = v7;
    *a6 = cb[1];
LABEL_16:
    if ( !*((_BYTE *)this + 120) )
    {
      v23 = (char *)*((_QWORD *)this + 14);
      if ( (unsigned __int64)(v23 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(v23);
      *((_QWORD *)this + 14) = -1;
    }
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xCC,
    (unsigned int)"onecoreuap\\shell\\windows.storage\\extrinsicpropertystore.cpp",
    (const char *)(unsigned int)v20,
    (int)v28);
  if ( v7 )
    CoTaskMemFree(v7);
  if ( v18 )
    CoTaskMemFree(v18);
  if ( *((_BYTE *)this + 120) )
  {
    CfUnlockProperties(*((_QWORD *)this + 14), &v32, 2);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)this + 112,
      -1);
    *((_BYTE *)this + 120) = 0;
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)this + 112,
    -1);
  return v21;
}

```

## disassembly

```asm
0x1800838c0  push    rbp
0x1800838c2  push    rbx
0x1800838c3  push    rsi
0x1800838c4  push    rdi
0x1800838c5  push    r12
0x1800838c7  push    r13
0x1800838c9  push    r14
0x1800838cb  lea     rbp, [rsp-17h]
0x1800838d0  sub     rsp, 0B0h
0x1800838d7  mov     rax, cs:__security_cookie
0x1800838de  xor     rax, rsp
0x1800838e1  mov     [rbp+47h+var_50], rax
0x1800838e5  mov     r14, rcx
0x1800838e8  mov     [rbp+47h+var_A0], 20h ; ' '
0x1800838ef  mov     rcx, [rbp+47h+arg_20]
0x1800838f3  xor     esi, esi
0x1800838f5  mov     [r8], rsi
0x1800838f8  mov     rax, rdx
0x1800838fb  mov     rdx, [rbp+47h+arg_28]
0x1800838ff  mov     r13, r9
0x180083902  mov     [r9], esi
0x180083905  mov     r12, r8
0x180083908  mov     [rcx], rsi
0x18008390b  xorps   xmm0, xmm0
0x18008390e  mov     [rbp+47h+var_B0], rcx
0x180083912  mov     r9d, 3
0x180083918  lea     rcx, [rbp+47h+var_A0]
0x18008391c  mov     [rbp+47h+var_A8], rdx
0x180083920  mov     qword ptr [rsp+0E0h+var_C0], rcx; int
0x180083925  mov     r8d, 7
0x18008392b  mov     [rdx], esi
0x18008392d  mov     rcx, rax
0x180083930  xor     edx, edx
0x180083932  mov     [rbp+47h+var_9C], 80h
0x180083939  mov     [rbp+47h+var_98], 2000000h
0x180083941  movdqu  [rbp+47h+var_90], xmm0
0x180083946  call    cs:__imp_CreateFile2
0x18008394d  nop     dword ptr [rax+rax+00h]
0x180083952  mov     rcx, [r14+70h]; hObject
0x180083956  mov     rbx, rax
0x180083959  lea     rdx, [rcx-1]
0x18008395d  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180083961  jbe     loc_180083C23
0x180083967  lea     rcx, [rbx-1]
0x18008396b  mov     [r14+70h], rbx
0x18008396f  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180083973  jbe     short loc_1800839A9
0x180083975  mov     rcx, [rbp+4Fh]; this
0x180083979  lea     r8, aOnecoreuapShel_77; "onecoreuap\\shell\\windows.storage\\ext"...
0x180083980  mov     edx, 96h; void *
0x180083985  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008398a  mov     rcx, [rbp+47h+var_50]
0x18008398e  xor     rcx, rsp; StackCookie
0x180083991  call    __security_check_cookie
0x180083996  add     rsp, 0B0h
0x18008399d  pop     r14
0x18008399f  pop     r13
0x1800839a1  pop     r12
0x1800839a3  pop     rdi
0x1800839a4  pop     rsi
0x1800839a5  pop     rbx
0x1800839a6  pop     rbp
0x1800839a7  retn
0x1800839a9  test    byte ptr [r14+58h], 3
0x1800839ae  xorps   xmm0, xmm0
0x1800839b1  movups  [rbp+47h+var_80], xmm0
0x1800839b5  mov     dword ptr [rbp+47h+var_80], 10001h
0x1800839bc  movups  xmmword ptr [rbp+47h+var_70], xmm0
0x1800839c0  mov     dword ptr [rbp+47h+var_70+8], 20002h
0x1800839c7  movups  xmmword ptr [rbp+47h+cb], xmm0
0x1800839cb  jnz     loc_180083AEE
0x1800839d1  mov     rcx, [r14+70h]
0x1800839d5  lea     rdx, [rbp+47h+var_80]
0x1800839d9  mov     r8d, 2
0x1800839df  mov     [rsp+0E0h+var_38], r15
0x1800839e7  call    TestHook_RetrieveProperties
0x1800839ec  mov     ebx, eax
0x1800839ee  test    eax, eax
0x1800839f0  jns     short loc_1800839FF
0x1800839f2  cmp     eax, 800700EAh
0x1800839f7  jnz     loc_180662048
0x1800839fd  jmp     short loc_180083A07
0x1800839ff  cmp     ebx, 800700EAh
0x180083a05  jnz     short loc_180083A75
0x180083a07  mov     eax, dword ptr [rbp+47h+var_70]
0x180083a0a  mov     rbx, rsi
0x180083a0d  test    eax, eax
0x180083a0f  jnz     loc_180083BA7
0x180083a15  mov     eax, dword ptr [rbp+47h+cb+8]
0x180083a18  test    eax, eax
0x180083a1a  jz      short loc_180083A3C
0x180083a1c  mov     ecx, eax; cb
0x180083a1e  call    cs:__imp_CoTaskMemAlloc
0x180083a25  nop     dword ptr [rax+rax+00h]
0x180083a2a  mov     rsi, rax
0x180083a2d  test    rax, rax
0x180083a30  jz      short loc_180083AA8
0x180083a32  mov     [rbp+47h+cb], rax
0x180083a36  mov     eax, dword ptr [rbp+47h+cb+8]
0x180083a39  mov     dword ptr [rbp+47h+var_70+0Ch], eax
0x180083a3c  mov     rcx, [r14+70h]
0x180083a40  lea     rdx, [rbp+47h+var_80]
0x180083a44  mov     r8d, 2
0x180083a4a  call    TestHook_RetrieveProperties
0x180083a4f  mov     r15d, eax
0x180083a52  test    eax, eax
0x180083a54  js      loc_180083B25
0x180083a5a  mov     eax, dword ptr [rbp+47h+var_70]
0x180083a5d  mov     rcx, [rbp+47h+var_A8]
0x180083a61  mov     [r12], rbx
0x180083a65  mov     [r13+0], eax
0x180083a69  mov     rax, [rbp+47h+var_B0]
0x180083a6d  mov     [rax], rsi
0x180083a70  mov     eax, dword ptr [rbp+47h+cb+8]
0x180083a73  mov     [rcx], eax
0x180083a75  cmp     byte ptr [r14+78h], 0
0x180083a7a  jnz     short loc_180083A99
0x180083a7c  mov     rcx, [r14+70h]; hObject
0x180083a80  lea     rax, [rcx-1]
0x180083a84  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180083a88  jbe     loc_180083C66
0x180083a8e  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180083a95  mov     [r14+70h], rsi
0x180083a99  xor     eax, eax
0x180083a9b  mov     r15, [rsp+0E0h+var_38]
0x180083aa3  jmp     loc_18008398A
0x180083aa8  mov     rcx, [rbp+4Fh]; this
0x180083aac  lea     r8, aOnecoreuapShel_77; "onecoreuap\\shell\\windows.storage\\ext"...
0x180083ab3  mov     r9d, 8007000Eh; char *
0x180083ab9  mov     edx, 0C7h; void *
0x180083abe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180083ac3  test    rbx, rbx
0x180083ac6  jz      short loc_180083AD7
0x180083ac8  mov     rcx, rbx; pv
0x180083acb  call    cs:__imp_CoTaskMemFree
0x180083ad2  nop     dword ptr [rax+rax+00h]
0x180083ad7  cmp     byte ptr [r14+78h], 0
0x180083adc  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180083ae3  jnz     loc_1806620D2
0x180083ae9  jmp     loc_1806620FD
0x180083aee  mov     r9d, 1
0x180083af4  mov     [rsp+0E0h+var_C0], esi; int
0x180083af8  mov     r8d, 2
0x180083afe  lea     rdx, [rbp+47h+var_80]
0x180083b02  mov     rcx, rbx
0x180083b05  call    cs:__imp_CfLockProperties
0x180083b0c  nop     dword ptr [rax+rax+00h]
0x180083b11  mov     ebx, eax
0x180083b13  test    eax, eax
0x180083b15  js      loc_180083BCD
0x180083b1b  mov     byte ptr [r14+78h], 1
0x180083b20  jmp     loc_1800839D1
0x180083b25  mov     rcx, [rbp+4Fh]; this
0x180083b29  lea     r8, aOnecoreuapShel_77; "onecoreuap\\shell\\windows.storage\\ext"...
0x180083b30  mov     r9d, r15d; char *
0x180083b33  mov     edx, 0CCh; void *
0x180083b38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180083b3d  test    rsi, rsi
0x180083b40  jz      short loc_180083B51
0x180083b42  mov     rcx, rsi; pv
0x180083b45  call    cs:__imp_CoTaskMemFree
0x180083b4c  nop     dword ptr [rax+rax+00h]
0x180083b51  test    rbx, rbx
0x180083b54  jz      short loc_180083B65
0x180083b56  mov     rcx, rbx; pv
0x180083b59  call    cs:__imp_CoTaskMemFree
0x180083b60  nop     dword ptr [rax+rax+00h]
0x180083b65  cmp     byte ptr [r14+78h], 0
0x180083b6a  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180083b71  jz      loc_180662113
0x180083b77  mov     rcx, [r14+70h]
0x180083b7b  lea     rdx, [rbp+47h+var_80]
0x180083b7f  mov     r8d, 2
0x180083b85  call    cs:__imp_CfUnlockProperties
0x180083b8c  nop     dword ptr [rax+rax+00h]
0x180083b91  mov     rdx, rsi
0x180083b94  lea     rcx, [r14+70h]
0x180083b98  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180083b9d  mov     byte ptr [r14+78h], 0
0x180083ba2  jmp     loc_180662113
0x180083ba7  mov     rcx, rax; cb
0x180083baa  call    cs:__imp_CoTaskMemAlloc
0x180083bb1  nop     dword ptr [rax+rax+00h]
0x180083bb6  mov     rbx, rax
0x180083bb9  test    rax, rax
0x180083bbc  jz      short loc_180083C34
0x180083bbe  mov     qword ptr [rbp+47h+var_80+8], rax
0x180083bc2  mov     eax, dword ptr [rbp+47h+var_70]
0x180083bc5  mov     dword ptr [rbp+47h+var_80+4], eax
0x180083bc8  jmp     loc_180083A15
0x180083bcd  mov     rcx, [rbp+4Fh]; this
0x180083bd1  lea     r8, aOnecoreuapShel_77; "onecoreuap\\shell\\windows.storage\\ext"...
0x180083bd8  mov     r9d, ebx; char *
0x180083bdb  mov     edx, 0A7h; void *
0x180083be0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180083be5  cmp     [r14+78h], sil
0x180083be9  jnz     short loc_180083BFB
0x180083beb  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180083bf2  lea     rcx, [r14+70h]
0x180083bf6  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180083bfb  mov     eax, ebx
0x180083bfd  jmp     loc_18008398A
0x180083c02  mov     rcx, [r14+70h]; hObject
0x180083c06  lea     rax, [rcx-1]
0x180083c0a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180083c0e  jbe     short loc_180083C2D
0x180083c10  mov     r15, [rsp+0E0h+var_38]
0x180083c18  mov     eax, ebx
0x180083c1a  mov     [r14+70h], rsi
0x180083c1e  jmp     loc_18008398A
0x180083c23  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x180083c28  jmp     loc_180083967
0x180083c2d  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x180083c32  jmp     short loc_180083C10
0x180083c34  mov     rcx, [rbp+4Fh]; this
0x180083c38  lea     r8, aOnecoreuapShel_77; "onecoreuap\\shell\\windows.storage\\ext"...
0x180083c3f  mov     r9d, 8007000Eh; char *
0x180083c45  mov     edx, 0C0h; void *
0x180083c4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180083c4f  cmp     byte ptr [r14+78h], 0
0x180083c54  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180083c5b  jnz     loc_1806620D2
0x180083c61  jmp     loc_1806620FD
0x180083c66  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x180083c6b  jmp     loc_180083A8E
0x180662048  cmp     ebx, 80070001h
0x18066204e  jz      loc_180083A75
0x180662054  cmp     ebx, 8007007Fh
0x18066205a  jz      loc_180083A75
0x180662060  cmp     ebx, 80070178h
0x180662066  jz      loc_180083A75
0x18066206c  cmp     ebx, 80070186h
0x180662072  jz      loc_180083A75
0x180662078  mov     rcx, [rbp+4Fh]; this
0x18066207c  lea     r8, aOnecoreuapShel_77; "onecoreuap\\shell\\windows.storage\\ext"...
0x180662083  mov     r9d, ebx; char *
0x180662086  mov     edx, 0B6h; void *
0x18066208b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180662090  cmp     byte ptr [r14+78h], 0
0x180662095  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18066209c  jz      loc_180083C02
0x1806620a2  mov     rcx, [r14+70h]
0x1806620a6  lea     rdx, [rbp+47h+var_80]
0x1806620aa  mov     r8d, 2
0x1806620b0  call    cs:__imp_CfUnlockProperties
0x1806620b7  nop     dword ptr [rax+rax+00h]
0x1806620bc  mov     rdx, rsi
0x1806620bf  lea     rcx, [r14+70h]
0x1806620c3  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1806620c8  mov     byte ptr [r14+78h], 0
0x1806620cd  jmp     loc_180083C02
0x1806620d2  mov     rcx, [r14+70h]
0x1806620d6  lea     rdx, [rbp+47h+var_80]
0x1806620da  mov     r8d, 2
0x1806620e0  call    cs:__imp_CfUnlockProperties
0x1806620e7  nop     dword ptr [rax+rax+00h]
0x1806620ec  mov     rdx, rsi
0x1806620ef  lea     rcx, [r14+70h]
0x1806620f3  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1806620f8  mov     byte ptr [r14+78h], 0
0x1806620fd  mov     rdx, rsi
0x180662100  lea     rcx, [r14+70h]
0x180662104  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180662109  mov     eax, 8007000Eh
0x18066210e  jmp     loc_180083A9B
0x180662113  mov     rdx, rsi
0x180662116  lea     rcx, [r14+70h]
0x18066211a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18066211f  mov     eax, r15d
0x180662122  jmp     loc_180083A9B
```
