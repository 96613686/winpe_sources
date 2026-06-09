# AuthValue::DeleteKeys(void)

- ea: `0x180061ee0`
- end: `0x180061fd4`
- name: `?DeleteKeys@AuthValue@@QEAAJXZ`
- size: `244`
- prototype: `__int64 __fastcall(AuthValue *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800260f8`
- `0x180026288`
- `0x1800533f8`

## callees

- `0x180011d90`
- `0x180027af8`
- `0x18003f2dc`
- `0x180061ee0`
- `0x180061fdc`
- `0x1800620d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180061f63`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180061f63`

## string_xrefs

- `0x180061f0f`: `onecore\ds\security\biometrics\service\server\authvalue.cpp`
- `0x180061f36`: `onecore\ds\security\biometrics\service\server\authvalue.cpp`
- `0x180061f72`: `onecore\ds\security\biometrics\service\server\authvalue.cpp`
- `0x180061f91`: `onecore\ds\security\biometrics\service\server\authvalue.cpp`
- `0x180061f58`: `BioServiceKey`

## pseudocode

```c
__int64 __fastcall AuthValue::DeleteKeys(HKEY *this)
{
  AuthValue *v2; // rcx
  int v3; // eax
  int v4; // edi
  int v5; // eax
  int v6; // esi
  HKEY v7; // rax
  unsigned int v8; // eax
  int v9; // eax
  int v10; // ebx
  __int64 result; // rax
  unsigned int v12; // [rsp+20h] [rbp-8h]
  int v13; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !AuthValue::Provisioned((AuthValue *)this) )
    return 0;
  v3 = AuthValue::DeleteTpmKey(v2);
  v4 = v3;
  if ( v3 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x11E,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\authvalue.cpp",
      (const char *)(unsigned int)v3,
      v12);
  v5 = AuthValue::DeleteSensorKey((AuthValue *)this);
  v6 = v5;
  if ( v5 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x11F,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\authvalue.cpp",
      (const char *)(unsigned int)v5,
      v12);
  v7 = this[5];
  if ( v7 == this[6] || (this[6] = v7, (v8 = RegDeleteValueW(this[4], L"BioServiceKey")) == 0) )
  {
    v10 = 0;
  }
  else
  {
    v9 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x245,
           (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\authvalue.cpp",
           (const char *)v8,
           v12);
    v10 = v9;
    if ( v9 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x120,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\authvalue.cpp",
        (const char *)(unsigned int)v9,
        v13);
  }
  if ( v4 < 0 )
    return (unsigned int)v4;
  if ( v6 < 0 )
    return (unsigned int)v6;
  result = 0;
  if ( v10 < 0 )
    return (unsigned int)v10;
  return result;
}

```

## disassembly

```asm
0x180061ee0  mov     [rsp+arg_0], rbx
0x180061ee5  mov     [rsp+arg_8], rsi
0x180061eea  push    rdi; int
0x180061eeb  sub     rsp, 20h
0x180061eef  mov     rbx, rcx
0x180061ef2  call    ?Provisioned@AuthValue@@QEBA_NXZ; AuthValue::Provisioned(void)
0x180061ef7  test    al, al
0x180061ef9  jz      loc_180061FC2
0x180061eff  call    ?DeleteTpmKey@AuthValue@@QEAAJXZ; AuthValue::DeleteTpmKey(void)
0x180061f04  mov     edi, eax
0x180061f06  test    eax, eax
0x180061f08  jns     short loc_180061F23
0x180061f0a  mov     rcx, [rsp+28h]; this
0x180061f0f  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\biometrics\\serv"...
0x180061f16  mov     r9d, eax; char *
0x180061f19  mov     edx, 11Eh; void *
0x180061f1e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180061f23  mov     rcx, rbx; this
0x180061f26  call    ?DeleteSensorKey@AuthValue@@QEAAJXZ; AuthValue::DeleteSensorKey(void)
0x180061f2b  mov     esi, eax
0x180061f2d  test    eax, eax
0x180061f2f  jns     short loc_180061F4A
0x180061f31  mov     rcx, [rsp+28h]; this
0x180061f36  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\biometrics\\serv"...
0x180061f3d  mov     r9d, eax; char *
0x180061f40  mov     edx, 11Fh; void *
0x180061f45  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180061f4a  mov     rax, [rbx+28h]
0x180061f4e  cmp     rax, [rbx+30h]
0x180061f52  jz      short loc_180061FA7
0x180061f54  mov     [rbx+30h], rax
0x180061f58  lea     rdx, aBioservicekey; "BioServiceKey"
0x180061f5f  mov     rcx, [rbx+20h]; hKey
0x180061f63  call    cs:__imp_RegDeleteValueW
0x180061f69  test    eax, eax
0x180061f6b  jz      short loc_180061FA7
0x180061f6d  mov     rcx, [rsp+28h]; this
0x180061f72  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\biometrics\\serv"...
0x180061f79  mov     r9d, eax; char *
0x180061f7c  mov     edx, 245h; void *
0x180061f81  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180061f86  mov     ebx, eax
0x180061f88  test    eax, eax
0x180061f8a  jns     short loc_180061FA9
0x180061f8c  mov     rcx, [rsp+28h]; this
0x180061f91  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\biometrics\\serv"...
0x180061f98  mov     r9d, eax; char *
0x180061f9b  mov     edx, 120h; void *
0x180061fa0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180061fa5  jmp     short loc_180061FA9
0x180061fa7  xor     ebx, ebx
0x180061fa9  test    edi, edi
0x180061fab  jns     short loc_180061FB1
0x180061fad  mov     eax, edi
0x180061faf  jmp     short loc_180061FC4
0x180061fb1  test    esi, esi
0x180061fb3  jns     short loc_180061FB9
0x180061fb5  mov     eax, esi
0x180061fb7  jmp     short loc_180061FC4
0x180061fb9  xor     eax, eax
0x180061fbb  test    ebx, ebx
0x180061fbd  cmovs   eax, ebx
0x180061fc0  jmp     short loc_180061FC4
0x180061fc2  xor     eax, eax
0x180061fc4  mov     rbx, [rsp+28h+arg_0]
0x180061fc9  mov     rsi, [rsp+28h+arg_8]
0x180061fce  add     rsp, 20h
0x180061fd2  pop     rdi
0x180061fd3  retn
```
