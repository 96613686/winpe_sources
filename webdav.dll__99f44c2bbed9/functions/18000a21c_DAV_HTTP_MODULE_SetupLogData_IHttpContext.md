# DAV_HTTP_MODULE::SetupLogData(IHttpContext *)

- ea: `0x18000a21c`
- end: `0x18000a385`
- name: `?SetupLogData@DAV_HTTP_MODULE@@AEAAJPEAVIHttpContext@@@Z`
- size: `361`
- prototype: `__int64 __fastcall(DAV_HTTP_MODULE *__hidden this, struct IHttpContext *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callers

- `0x180009480`

## callees

- `0x18000a21c`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x18000a245`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000a245`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000a34c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000a35b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000a34c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000a35b`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000a307`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000a307`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18000a2e8`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18000a2e8`
- `iisutil!?AppendA@STRU@@QEAAJPEBD@Z` at `0x18000a31b`
- `iisutil!?AppendA@STRU@@QEAAJPEBD@Z` at `0x18000a31b`

## pseudocode

```c
__int64 __fastcall DAV_HTTP_MODULE::SetupLogData(DAV_HTTP_MODULE *this, struct IHttpContext *a2)
{
  __int64 v3; // rax
  __int64 v4; // rbp
  __int64 v5; // rax
  const char *v6; // rax
  const char *v7; // rsi
  __int64 v8; // rdx
  int v9; // ebx
  _BYTE v11[32]; // [rsp+20h] [rbp-58h] BYREF
  __int64 v12; // [rsp+40h] [rbp-38h]
  int v13; // [rsp+50h] [rbp-28h]

  STRU::STRU((STRU *)v11);
  v3 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 24LL))(a2);
  v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
  if ( (unsigned int)(*(_DWORD *)(v4 + 36) - 12) <= 1
    && (v5 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 24LL))(a2),
        v6 = (const char *)(*(__int64 (__fastcall **)(__int64, const char *, _QWORD))(*(_QWORD *)v5 + 24LL))(
                             v5,
                             "Destination",
                             0),
        (v7 = v6) != 0)
    && *v6 )
  {
    v8 = *(_QWORD *)(v4 + 96);
    v9 = 0;
    if ( !v8
      || !*(_WORD *)(v4 + 70)
      || (v9 = STRU::Copy((STRU *)v11, (const unsigned __int16 *)(v8 + 2), (*(unsigned __int16 *)(v4 + 70) >> 1) - 1),
          v9 >= 0) )
    {
      if ( v13 )
        v9 = STRU::Append((STRU *)v11, L"&");
      if ( v9 >= 0 )
      {
        v9 = STRU::AppendA((STRU *)v11, v7);
        if ( v9 >= 0 )
          v9 = (*(__int64 (__fastcall **)(struct IHttpContext *, const char *, __int64))(*(_QWORD *)a2 + 136LL))(
                 a2,
                 "LOG_QUERY_STRING",
                 v12);
      }
    }
    STRU::~STRU((STRU *)v11);
    return (unsigned int)v9;
  }
  else
  {
    STRU::~STRU((STRU *)v11);
    return 0;
  }
}

```

## disassembly

```asm
0x18000a21c  mov     [rsp+arg_0], rbx
0x18000a221  mov     [rsp+arg_10], rbp
0x18000a226  push    rsi
0x18000a227  push    rdi
0x18000a228  push    r14
0x18000a22a  sub     rsp, 60h
0x18000a22e  mov     rax, cs:__security_cookie
0x18000a235  xor     rax, rsp
0x18000a238  mov     [rsp+78h+var_20], rax
0x18000a23d  lea     rcx, [rsp+78h+var_58]
0x18000a242  mov     rdi, rdx
0x18000a245  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000a24b  mov     rax, [rdi]
0x18000a24e  mov     rcx, rdi
0x18000a251  mov     rax, [rax+18h]
0x18000a255  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a25a  mov     rdx, rax
0x18000a25d  mov     rcx, [rax]
0x18000a260  mov     rax, [rcx+8]
0x18000a264  mov     rcx, rdx
0x18000a267  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a26c  mov     rbp, rax
0x18000a26f  mov     ecx, [rax+24h]
0x18000a272  sub     ecx, 0Ch
0x18000a275  cmp     ecx, 1
0x18000a278  ja      loc_18000A356
0x18000a27e  mov     rcx, [rdi]
0x18000a281  mov     rax, [rcx+18h]
0x18000a285  mov     rcx, rdi
0x18000a288  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a28d  mov     r9, rax
0x18000a290  lea     rdx, aDestination; "Destination"
0x18000a297  xor     r8d, r8d
0x18000a29a  mov     rcx, [rax]
0x18000a29d  mov     rax, [rcx+18h]
0x18000a2a1  mov     rcx, r9
0x18000a2a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2a9  xor     r14d, r14d
0x18000a2ac  mov     rsi, rax
0x18000a2af  test    rax, rax
0x18000a2b2  jz      loc_18000A356
0x18000a2b8  cmp     [rax], r14b
0x18000a2bb  jz      loc_18000A356
0x18000a2c1  mov     rdx, [rbp+60h]
0x18000a2c5  mov     ebx, r14d
0x18000a2c8  test    rdx, rdx
0x18000a2cb  jz      short loc_18000A2F4
0x18000a2cd  cmp     [rbp+46h], r14w
0x18000a2d2  jbe     short loc_18000A2F4
0x18000a2d4  movzx   r8d, word ptr [rbp+46h]
0x18000a2d9  lea     rcx, [rsp+78h+var_58]
0x18000a2de  shr     r8d, 1
0x18000a2e1  add     rdx, 2
0x18000a2e5  dec     r8d
0x18000a2e8  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18000a2ee  mov     ebx, eax
0x18000a2f0  test    eax, eax
0x18000a2f2  js      short loc_18000A347
0x18000a2f4  cmp     [rsp+78h+var_28], r14d
0x18000a2f9  jbe     short loc_18000A30F
0x18000a2fb  lea     rdx, asc_180026D60; "&"
0x18000a302  lea     rcx, [rsp+78h+var_58]
0x18000a307  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000a30d  mov     ebx, eax
0x18000a30f  test    ebx, ebx
0x18000a311  js      short loc_18000A347
0x18000a313  mov     rdx, rsi
0x18000a316  lea     rcx, [rsp+78h+var_58]
0x18000a31b  call    cs:__imp_?AppendA@STRU@@QEAAJPEBD@Z; STRU::AppendA(char const *)
0x18000a321  mov     ebx, eax
0x18000a323  test    eax, eax
0x18000a325  js      short loc_18000A347
0x18000a327  mov     rax, [rdi]
0x18000a32a  lea     rdx, aLogQueryString; "LOG_QUERY_STRING"
0x18000a331  mov     r8, [rsp+78h+var_38]
0x18000a336  mov     rcx, rdi
0x18000a339  mov     rax, [rax+88h]
0x18000a340  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a345  mov     ebx, eax
0x18000a347  lea     rcx, [rsp+78h+var_58]
0x18000a34c  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000a352  mov     eax, ebx
0x18000a354  jmp     short loc_18000A363
0x18000a356  lea     rcx, [rsp+78h+var_58]
0x18000a35b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000a361  xor     eax, eax
0x18000a363  mov     rcx, [rsp+78h+var_20]
0x18000a368  xor     rcx, rsp; StackCookie
0x18000a36b  call    __security_check_cookie
0x18000a370  lea     r11, [rsp+78h+var_18]
0x18000a375  mov     rbx, [r11+20h]
0x18000a379  mov     rbp, [r11+30h]
0x18000a37d  mov     rsp, r11
0x18000a380  pop     r14
0x18000a382  pop     rdi
0x18000a383  pop     rsi
0x18000a384  retn
```
