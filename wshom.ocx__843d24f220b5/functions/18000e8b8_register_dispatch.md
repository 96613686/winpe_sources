# register_dispatch

- ea: `0x18000e8b8`
- end: `0x18000eba6`
- name: `register_dispatch`
- size: `750`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18000e1b0`

## callees

- `0x18000e474`
- `0x18000e4a8`
- `0x18000e52c`
- `0x18000e748`
- `0x18000e81c`
- `0x18000e8b8`
- `0x18000ebac`
- `0x18000edd0`
- `0x180010250`

## import_xrefs

- `msvcrt!sprintf_s` at `0x18000e948`
- `msvcrt!sprintf_s` at `0x18000e9eb`
- `msvcrt!sprintf_s` at `0x18000ea7b`
- `msvcrt!sprintf_s` at `0x18000eb06`
- `msvcrt!sprintf_s` at `0x18000eb4c`
- `msvcrt!sprintf_s` at `0x18000e948`
- `msvcrt!sprintf_s` at `0x18000e9eb`
- `msvcrt!sprintf_s` at `0x18000ea7b`
- `msvcrt!sprintf_s` at `0x18000eb06`
- `msvcrt!sprintf_s` at `0x18000eb4c`

## string_xrefs

- `0x18000e97d`: `CLSID`
- `0x18000ea39`: `CLSID`
- `0x18000ea6d`: `CLSID\%s`

## pseudocode

```c
__int64 __fastcall register_dispatch(char *a1, __int64 a2)
{
  const char *v2; // r14
  int v3; // r15d
  const struct _GUID *v5; // r12
  int v7; // ebx
  char v8; // r8
  RegHelper *v9; // rcx
  RegHelper *v10; // rcx
  RegHelper *v11; // rcx
  char v12; // r8
  RegHelper *v13; // rcx
  RegHelper *v14; // rcx
  char v15; // r8
  int v16; // r8d
  RegHelper *v17; // rcx
  RegHelper *v18; // rcx
  RegHelper *v19; // rcx
  HKEY phkResult[2]; // [rsp+30h] [rbp-D0h] BYREF
  char v22[112]; // [rsp+40h] [rbp-C0h] BYREF
  char Buffer[1024]; // [rsp+B0h] [rbp-50h] BYREF

  v2 = *(const char **)(a2 + 8);
  v3 = *(unsigned __int16 *)(a2 + 48);
  v5 = *(const struct _GUID **)(a2 + 32);
  *(_OWORD *)phkResult = 0;
  v7 = unregister_0(a1);
  if ( v7 >= 0 )
  {
    v7 = register_unknown(a1, a2);
    if ( v7 >= 0 )
    {
      sprintf_s(Buffer, 0x400u, "%s.%s", "WScript", v2);
      if ( RegHelper::Create(phkResult, Buffer, v8)
        && RegHelper::Set(v9, phkResult[0], *(const BYTE **)(a2 + 24), 0)
        && RegHelper::CreateSub((RegHelper *)phkResult, "CLSID")
        && RegHelper::Set(v10, phkResult[1], (const BYTE *)a1, 0)
        && RegHelper::CreateSub((RegHelper *)phkResult, "CurVer")
        && (sprintf_s(Buffer, 0x400u, "%s.%s.%u", "WScript", v2, v3),
            RegHelper::Set(v11, phkResult[1], (const BYTE *)Buffer, 0))
        && RegHelper::Create(phkResult, Buffer, v12)
        && RegHelper::Set(v13, phkResult[0], *(const BYTE **)(a2 + 24), 0)
        && RegHelper::CreateSub((RegHelper *)phkResult, "CLSID")
        && RegHelper::Set(v14, phkResult[1], (const BYTE *)a1, 0)
        && (sprintf_s(Buffer, 0x400u, "CLSID\\%s", a1), RegHelper::Create(phkResult, Buffer, v15))
        && RegHelper::CreateSub((RegHelper *)phkResult, "TypeLib")
        && (StringFromGUID2A(v5, v22, v16), RegHelper::Set(v17, phkResult[1], (const BYTE *)v22, 0))
        && RegHelper::CreateSub((RegHelper *)phkResult, "ProgID")
        && (sprintf_s(Buffer, 0x400u, "%s.%s.%u", "WScript", v2, v3),
            RegHelper::Set(v18, phkResult[1], (const BYTE *)Buffer, 0))
        && RegHelper::CreateSub((RegHelper *)phkResult, "VersionIndependentProgID")
        && (sprintf_s(Buffer, 0x400u, "%s.%s", "WScript", v2), RegHelper::Set(
                                                                 v19,
                                                                 phkResult[1],
                                                                 (const BYTE *)Buffer,
                                                                 0)) )
      {
        v7 = 0;
      }
      else
      {
        v7 = -2147418113;
      }
    }
  }
  RegHelper::~RegHelper((RegHelper *)phkResult);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000e8b8  mov     [rsp-8+arg_10], rbx
0x18000e8bd  push    rbp
0x18000e8be  push    rsi
0x18000e8bf  push    rdi
0x18000e8c0  push    r12
0x18000e8c2  push    r13
0x18000e8c4  push    r14
0x18000e8c6  push    r15
0x18000e8c8  lea     rbp, [rsp-3C0h]
0x18000e8d0  sub     rsp, 4C0h
0x18000e8d7  mov     rax, cs:__security_cookie
0x18000e8de  xor     rax, rsp
0x18000e8e1  mov     [rbp+3F0h+var_40], rax
0x18000e8e8  mov     r14, [rdx+8]
0x18000e8ec  xorps   xmm0, xmm0
0x18000e8ef  movzx   r15d, word ptr [rdx+30h]
0x18000e8f4  mov     rdi, rdx
0x18000e8f7  mov     r12, [rdx+20h]
0x18000e8fb  mov     rsi, rcx
0x18000e8fe  movdqu  xmmword ptr [rsp+4F0h+phkResult], xmm0
0x18000e904  call    unregister_0
0x18000e909  mov     ebx, eax
0x18000e90b  test    eax, eax
0x18000e90d  js      loc_18000EB70
0x18000e913  mov     rdx, rdi
0x18000e916  mov     rcx, rsi
0x18000e919  call    register_unknown
0x18000e91e  mov     ebx, eax
0x18000e920  test    eax, eax
0x18000e922  js      loc_18000EB70
0x18000e928  mov     r13d, 400h
0x18000e92e  mov     [rsp+4F0h+var_4D0], r14
0x18000e933  mov     edx, r13d; BufferCount
0x18000e936  lea     r9, aWscript; "WScript"
0x18000e93d  lea     r8, aSS_0; "%s.%s"
0x18000e944  lea     rcx, [rbp+3F0h+Buffer]; Buffer
0x18000e948  call    cs:__imp_sprintf_s
0x18000e94e  lea     rdx, [rbp+3F0h+Buffer]; lpSubKey
0x18000e952  lea     rcx, [rsp+4F0h+phkResult]; phkResult
0x18000e957  call    ?Create@RegHelper@@QEAA_NPEBD_N@Z; RegHelper::Create(char const *,bool)
0x18000e95c  test    al, al
0x18000e95e  jz      loc_18000EB6B
0x18000e964  mov     r8, [rdi+18h]; char *
0x18000e968  xor     r9d, r9d; char *
0x18000e96b  mov     rdx, [rsp+4F0h+phkResult]; HKEY
0x18000e970  call    ?Set@RegHelper@@QEAA_NPEAUHKEY__@@PEBD1@Z; RegHelper::Set(HKEY__ *,char const *,char const *)
0x18000e975  test    al, al
0x18000e977  jz      loc_18000EB6B
0x18000e97d  lea     rdx, aClsid; "CLSID"
0x18000e984  lea     rcx, [rsp+4F0h+phkResult]; this
0x18000e989  call    ?CreateSub@RegHelper@@QEAA_NPEBD@Z; RegHelper::CreateSub(char const *)
0x18000e98e  test    al, al
0x18000e990  jz      loc_18000EB6B
0x18000e996  mov     rdx, [rsp+4F0h+phkResult+8]; HKEY
0x18000e99b  xor     r9d, r9d; char *
0x18000e99e  mov     r8, rsi; char *
0x18000e9a1  call    ?Set@RegHelper@@QEAA_NPEAUHKEY__@@PEBD1@Z; RegHelper::Set(HKEY__ *,char const *,char const *)
0x18000e9a6  test    al, al
0x18000e9a8  jz      loc_18000EB6B
0x18000e9ae  lea     rdx, aCurver; "CurVer"
0x18000e9b5  lea     rcx, [rsp+4F0h+phkResult]; this
0x18000e9ba  call    ?CreateSub@RegHelper@@QEAA_NPEBD@Z; RegHelper::CreateSub(char const *)
0x18000e9bf  test    al, al
0x18000e9c1  jz      loc_18000EB6B
0x18000e9c7  mov     ebx, r15d
0x18000e9ca  lea     r8, aSSU; "%s.%s.%u"
0x18000e9d1  lea     r15, aWscript; "WScript"
0x18000e9d8  mov     [rsp+4F0h+var_4C8], ebx
0x18000e9dc  mov     r9, r15
0x18000e9df  mov     [rsp+4F0h+var_4D0], r14
0x18000e9e4  mov     edx, r13d; BufferCount
0x18000e9e7  lea     rcx, [rbp+3F0h+Buffer]; Buffer
0x18000e9eb  call    cs:__imp_sprintf_s
0x18000e9f1  mov     rdx, [rsp+4F0h+phkResult+8]; HKEY
0x18000e9f6  lea     r8, [rbp+3F0h+Buffer]; char *
0x18000e9fa  xor     r9d, r9d; char *
0x18000e9fd  call    ?Set@RegHelper@@QEAA_NPEAUHKEY__@@PEBD1@Z; RegHelper::Set(HKEY__ *,char const *,char const *)
0x18000ea02  test    al, al
0x18000ea04  jz      loc_18000EB6B
0x18000ea0a  lea     rdx, [rbp+3F0h+Buffer]; lpSubKey
0x18000ea0e  lea     rcx, [rsp+4F0h+phkResult]; phkResult
0x18000ea13  call    ?Create@RegHelper@@QEAA_NPEBD_N@Z; RegHelper::Create(char const *,bool)
0x18000ea18  test    al, al
0x18000ea1a  jz      loc_18000EB6B
0x18000ea20  mov     r8, [rdi+18h]; char *
0x18000ea24  xor     r9d, r9d; char *
0x18000ea27  mov     rdx, [rsp+4F0h+phkResult]; HKEY
0x18000ea2c  call    ?Set@RegHelper@@QEAA_NPEAUHKEY__@@PEBD1@Z; RegHelper::Set(HKEY__ *,char const *,char const *)
0x18000ea31  test    al, al
0x18000ea33  jz      loc_18000EB6B
0x18000ea39  lea     rdx, aClsid; "CLSID"
0x18000ea40  lea     rcx, [rsp+4F0h+phkResult]; this
0x18000ea45  call    ?CreateSub@RegHelper@@QEAA_NPEBD@Z; RegHelper::CreateSub(char const *)
0x18000ea4a  test    al, al
0x18000ea4c  jz      loc_18000EB6B
0x18000ea52  mov     rdx, [rsp+4F0h+phkResult+8]; HKEY
0x18000ea57  xor     r9d, r9d; char *
0x18000ea5a  mov     r8, rsi; char *
0x18000ea5d  call    ?Set@RegHelper@@QEAA_NPEAUHKEY__@@PEBD1@Z; RegHelper::Set(HKEY__ *,char const *,char const *)
0x18000ea62  test    al, al
0x18000ea64  jz      loc_18000EB6B
0x18000ea6a  mov     r9, rsi
0x18000ea6d  lea     r8, aClsidS; "CLSID\\%s"
0x18000ea74  mov     edx, r13d; BufferCount
0x18000ea77  lea     rcx, [rbp+3F0h+Buffer]; Buffer
0x18000ea7b  call    cs:__imp_sprintf_s
0x18000ea81  lea     rdx, [rbp+3F0h+Buffer]; lpSubKey
0x18000ea85  lea     rcx, [rsp+4F0h+phkResult]; phkResult
0x18000ea8a  call    ?Create@RegHelper@@QEAA_NPEBD_N@Z; RegHelper::Create(char const *,bool)
0x18000ea8f  test    al, al
0x18000ea91  jz      loc_18000EB6B
0x18000ea97  lea     rdx, aTypelib; "TypeLib"
0x18000ea9e  lea     rcx, [rsp+4F0h+phkResult]; this
0x18000eaa3  call    ?CreateSub@RegHelper@@QEAA_NPEBD@Z; RegHelper::CreateSub(char const *)
0x18000eaa8  test    al, al
0x18000eaaa  jz      loc_18000EB6B
0x18000eab0  lea     rdx, [rsp+4F0h+var_4B0]; char *
0x18000eab5  mov     rcx, r12; struct _GUID *
0x18000eab8  call    ?StringFromGUID2A@@YAHAEBU_GUID@@PEADH@Z; StringFromGUID2A(_GUID const &,char *,int)
0x18000eabd  mov     rdx, [rsp+4F0h+phkResult+8]; HKEY
0x18000eac2  lea     r8, [rsp+4F0h+var_4B0]; char *
0x18000eac7  xor     r9d, r9d; char *
0x18000eaca  call    ?Set@RegHelper@@QEAA_NPEAUHKEY__@@PEBD1@Z; RegHelper::Set(HKEY__ *,char const *,char const *)
0x18000eacf  test    al, al
0x18000ead1  jz      loc_18000EB6B
0x18000ead7  lea     rdx, aProgid; "ProgID"
0x18000eade  lea     rcx, [rsp+4F0h+phkResult]; this
0x18000eae3  call    ?CreateSub@RegHelper@@QEAA_NPEBD@Z; RegHelper::CreateSub(char const *)
0x18000eae8  test    al, al
0x18000eaea  jz      short loc_18000EB6B
0x18000eaec  mov     [rsp+4F0h+var_4C8], ebx
0x18000eaf0  lea     r8, aSSU; "%s.%s.%u"
0x18000eaf7  mov     r9, r15
0x18000eafa  mov     [rsp+4F0h+var_4D0], r14
0x18000eaff  mov     edx, r13d; BufferCount
0x18000eb02  lea     rcx, [rbp+3F0h+Buffer]; Buffer
0x18000eb06  call    cs:__imp_sprintf_s
0x18000eb0c  mov     rdx, [rsp+4F0h+phkResult+8]; HKEY
0x18000eb11  lea     r8, [rbp+3F0h+Buffer]; char *
0x18000eb15  xor     r9d, r9d; char *
0x18000eb18  call    ?Set@RegHelper@@QEAA_NPEAUHKEY__@@PEBD1@Z; RegHelper::Set(HKEY__ *,char const *,char const *)
0x18000eb1d  test    al, al
0x18000eb1f  jz      short loc_18000EB6B
0x18000eb21  lea     rdx, aVersionindepen; "VersionIndependentProgID"
0x18000eb28  lea     rcx, [rsp+4F0h+phkResult]; this
0x18000eb2d  call    ?CreateSub@RegHelper@@QEAA_NPEBD@Z; RegHelper::CreateSub(char const *)
0x18000eb32  test    al, al
0x18000eb34  jz      short loc_18000EB6B
0x18000eb36  mov     r9, r15
0x18000eb39  mov     [rsp+4F0h+var_4D0], r14
0x18000eb3e  lea     r8, aSS_0; "%s.%s"
0x18000eb45  mov     edx, r13d; BufferCount
0x18000eb48  lea     rcx, [rbp+3F0h+Buffer]; Buffer
0x18000eb4c  call    cs:__imp_sprintf_s
0x18000eb52  mov     rdx, [rsp+4F0h+phkResult+8]; HKEY
0x18000eb57  lea     r8, [rbp+3F0h+Buffer]; char *
0x18000eb5b  xor     r9d, r9d; char *
0x18000eb5e  call    ?Set@RegHelper@@QEAA_NPEAUHKEY__@@PEBD1@Z; RegHelper::Set(HKEY__ *,char const *,char const *)
0x18000eb63  test    al, al
0x18000eb65  jz      short loc_18000EB6B
0x18000eb67  xor     ebx, ebx
0x18000eb69  jmp     short loc_18000EB70
0x18000eb6b  mov     ebx, 8000FFFFh
0x18000eb70  lea     rcx, [rsp+4F0h+phkResult]; this
0x18000eb75  call    ??1RegHelper@@QEAA@XZ; RegHelper::~RegHelper(void)
0x18000eb7a  mov     eax, ebx
0x18000eb7c  mov     rcx, [rbp+3F0h+var_40]
0x18000eb83  xor     rcx, rsp; StackCookie
0x18000eb86  call    __security_check_cookie
0x18000eb8b  mov     rbx, [rsp+4F0h+arg_10]
0x18000eb93  add     rsp, 4C0h
0x18000eb9a  pop     r15
0x18000eb9c  pop     r14
0x18000eb9e  pop     r13
0x18000eba0  pop     r12
0x18000eba2  pop     rdi
0x18000eba3  pop     rsi
0x18000eba4  pop     rbp
0x18000eba5  retn
```
