# LOCK_VERB_HANDLER::DoLockRefresh(void)

- ea: `0x18000c304`
- end: `0x18000c5ef`
- name: `?DoLockRefresh@LOCK_VERB_HANDLER@@AEAA?AW4REQUEST_NOTIFICATION_STATUS@@XZ`
- size: `747`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000c7e0`

## callees

- `0x1800033d4`
- `0x180003634`
- `0x180006cf0`
- `0x18000a3e8`
- `0x18000a7d4`
- `0x18000c304`
- `0x180015038`
- `0x18001519c`
- `0x1800153ac`
- `0x18001a0cc`
- `0x1800224c2`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `iisutil!??1STRA@@QEAA@XZ` at `0x18000c4b6`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000c4b6`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x18000c41b`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x18000c41b`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18000c340`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18000c340`

## string_xrefs

- `0x18000c475`: `LOCK: Invalid Request -- Empty Entity Body and No Lock Token`

## pseudocode

```c
__int64 __fastcall LOCK_VERB_HANDLER::DoLockRefresh(__int64 a1)
{
  const unsigned __int16 *v2; // rbx
  struct IHttpContext *v3; // rsi
  __int64 v4; // rax
  __int64 v5; // rax
  char *v6; // rax
  const char *v7; // r14
  int v8; // ebx
  int v9; // eax
  __int64 v10; // rdx
  int v11; // edx
  struct IHttpContext *v12; // rcx
  __int64 v13; // rax
  unsigned int v14; // ebx
  __int64 v16; // rdi
  __int64 v17; // rsi
  __int64 v18; // r14
  __int64 v19; // rbx
  const unsigned __int16 *EffectiveUser; // rax
  int v21; // ebx
  struct IPubLock *v22; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v23[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v24; // [rsp+60h] [rbp-A0h]
  _BYTE v25[1048]; // [rsp+68h] [rbp-98h] BYREF
  int v26; // [rsp+480h] [rbp+380h]
  int v27; // [rsp+488h] [rbp+388h]
  _BYTE v28[32]; // [rsp+490h] [rbp+390h] BYREF
  __int64 v29; // [rsp+4B0h] [rbp+3B0h]
  int v30; // [rsp+4C0h] [rbp+3C0h]

  STRA::STRA((STRA *)v28);
  v2 = *(const unsigned __int16 **)(a1 + 72);
  v3 = *(struct IHttpContext **)(a1 + 8);
  v22 = 0;
  v26 = 0;
  memset_0(v25, 0, sizeof(v25));
  v27 = 0;
  v23[1] = v23;
  v4 = *(_QWORD *)v3;
  v23[0] = 0;
  v24 = 0;
  v5 = (*(__int64 (__fastcall **)(struct IHttpContext *))(v4 + 24))(v3);
  v6 = (char *)(*(__int64 (__fastcall **)(__int64, const char *, _QWORD))(*(_QWORD *)v5 + 24LL))(v5, "If", 0);
  v7 = v6;
  if ( v6 )
  {
    v9 = IF_STATE::Parse((IF_STATE *)v23, v3, v6, v2);
    v8 = v9;
    if ( v9 < 0 || v9 == 1 )
    {
      v11 = v9;
    }
    else
    {
      if ( !v24 )
      {
        if ( v23[0] )
        {
          if ( !*(_QWORD *)v23[0] )
          {
            v10 = *(_QWORD *)(v23[0] + 8LL);
            if ( v10 )
            {
              if ( !*(_QWORD *)v10 && !*(_DWORD *)(v10 + 12) )
              {
                v8 = STRA::CopyW((STRA *)v28, *(const unsigned __int16 **)(v10 + 48));
                goto LABEL_15;
              }
            }
          }
        }
      }
      v8 = 1;
      v11 = 1;
    }
    DAV_TRACE::TraceInvalidIfHeader(v3, v11, v7);
    goto LABEL_15;
  }
  v8 = 1;
LABEL_15:
  IF_STATE::~IF_STATE((IF_STATE *)v23);
  if ( v8 < 0 || v8 == 1 )
    goto LABEL_19;
  v12 = *(struct IHttpContext **)(a1 + 8);
  if ( !v30 )
  {
    v13 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v12 + 272LL))(v12);
    (*(void (__fastcall **)(__int64, const wchar_t *, _QWORD, _QWORD, char))(*(_QWORD *)v13 + 32LL))(
      v13,
      L"LOCK: Invalid Request -- Empty Entity Body and No Lock Token",
      0,
      0,
      3);
LABEL_19:
    v14 = 2;
    DAV_BASE_HANDLER::FinishRequest((DAV_BASE_HANDLER *)a1, 0x190u, "Bad Request", 0, 0);
    goto LABEL_20;
  }
  v16 = *(_QWORD *)(a1 + 5576);
  v17 = *(_QWORD *)(a1 + 560);
  v18 = v29;
  v19 = *(_QWORD *)(*(_QWORD *)(a1 + 24) + 3328LL);
  EffectiveUser = GetEffectiveUser(v12);
  v21 = (*(__int64 (__fastcall **)(_QWORD, __int64, const unsigned __int16 *, __int64, __int64, __int64, struct IPubLock **))(**(_QWORD **)(v19 + 16) + 72LL))(
          *(_QWORD *)(v19 + 16),
          a1 + 248,
          EffectiveUser,
          v18,
          v17,
          v16,
          &v22);
  if ( v21 >= 0 )
  {
    v21 = XML_RESPONDER::BeginXmlCommon((XML_RESPONDER *)(a1 + 448), "prop", 0xC8u, "OK", 0);
    if ( v21 >= 0 )
    {
      v21 = XML_RESPONDER::SendXmlLockDiscovery(
              (XML_RESPONDER *)(a1 + 448),
              v22,
              *(const unsigned __int16 **)(a1 + 128));
      if ( v21 >= 0 )
      {
        if ( *(_DWORD *)(a1 + 544) )
          v21 = XML_RESPONDER::FinishXmlLockResponse((XML_RESPONDER *)(a1 + 448));
      }
    }
  }
  if ( v22 )
  {
    (*(void (__fastcall **)(struct IPubLock *))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  if ( v21 < 0 )
  {
    DAV_BASE_HANDLER::MapAndHandleError((DAV_BASE_HANDLER *)a1, v21);
    v14 = 2;
  }
  else
  {
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 200LL))(*(_QWORD *)(a1 + 8));
    v14 = 0;
  }
LABEL_20:
  STRA::~STRA((STRA *)v28);
  return v14;
}

```

## disassembly

```asm
0x18000c304  mov     [rsp-8+arg_8], rbx
0x18000c309  mov     [rsp-8+arg_10], rsi
0x18000c30e  push    rbp
0x18000c30f  push    rdi
0x18000c310  push    r12
0x18000c312  push    r14
0x18000c314  push    r15
0x18000c316  lea     rbp, [rsp-3D0h]
0x18000c31e  sub     rsp, 4D0h
0x18000c325  mov     rax, cs:__security_cookie
0x18000c32c  xor     rax, rsp
0x18000c32f  mov     [rbp+3F0h+var_28], rax
0x18000c336  mov     r15, rcx
0x18000c339  lea     rcx, [rbp+3F0h+var_60]
0x18000c340  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x18000c346  mov     rbx, [r15+48h]
0x18000c34a  lea     rcx, [rsp+4F0h+var_488]; void *
0x18000c34f  mov     rsi, [r15+8]
0x18000c353  xor     r12d, r12d
0x18000c356  xor     edx, edx; Val
0x18000c358  mov     [rsp+4F0h+var_4B0], r12
0x18000c35d  mov     r8d, 418h; Size
0x18000c363  mov     [rbp+3F0h+var_70], r12d
0x18000c36a  call    memset_0
0x18000c36f  lea     rax, [rsp+4F0h+var_4A0]
0x18000c374  mov     [rbp+3F0h+var_68], r12d
0x18000c37b  mov     [rsp+4F0h+var_498], rax
0x18000c380  mov     rcx, rsi
0x18000c383  mov     rax, [rsi]
0x18000c386  mov     [rsp+4F0h+var_4A0], r12
0x18000c38b  mov     [rsp+4F0h+var_490], r12d
0x18000c390  mov     rax, [rax+18h]
0x18000c394  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c399  mov     r9, rax
0x18000c39c  lea     rdx, aIf; "If"
0x18000c3a3  xor     r8d, r8d
0x18000c3a6  mov     rcx, [rax]
0x18000c3a9  mov     rax, [rcx+18h]
0x18000c3ad  mov     rcx, r9
0x18000c3b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3b5  mov     r14, rax
0x18000c3b8  test    rax, rax
0x18000c3bb  jnz     short loc_18000C3C4
0x18000c3bd  lea     edi, [rax+1]
0x18000c3c0  mov     ebx, edi
0x18000c3c2  jmp     short loc_18000C438
0x18000c3c4  mov     r9, rbx; unsigned __int16 *
0x18000c3c7  lea     rcx, [rsp+4F0h+var_4A0]; this
0x18000c3cc  mov     r8, r14; char *
0x18000c3cf  mov     rdx, rsi; struct IHttpContext *
0x18000c3d2  call    ?Parse@IF_STATE@@QEAAJPEAVIHttpContext@@PEBDPEBG@Z; IF_STATE::Parse(IHttpContext *,char const *,ushort const *)
0x18000c3d7  mov     ebx, eax
0x18000c3d9  mov     edi, 1
0x18000c3de  test    eax, eax
0x18000c3e0  js      short loc_18000C42B
0x18000c3e2  cmp     eax, edi
0x18000c3e4  jz      short loc_18000C42B
0x18000c3e6  cmp     [rsp+4F0h+var_490], r12d
0x18000c3eb  jnz     short loc_18000C425
0x18000c3ed  mov     rdx, [rsp+4F0h+var_4A0]
0x18000c3f2  test    rdx, rdx
0x18000c3f5  jz      short loc_18000C425
0x18000c3f7  cmp     [rdx], r12
0x18000c3fa  jnz     short loc_18000C425
0x18000c3fc  mov     rdx, [rdx+8]
0x18000c400  test    rdx, rdx
0x18000c403  jz      short loc_18000C425
0x18000c405  cmp     [rdx], r12
0x18000c408  jnz     short loc_18000C425
0x18000c40a  cmp     [rdx+0Ch], r12d
0x18000c40e  jnz     short loc_18000C425
0x18000c410  mov     rdx, [rdx+30h]
0x18000c414  lea     rcx, [rbp+3F0h+var_60]
0x18000c41b  call    cs:__imp_?CopyW@STRA@@QEAAJPEBG@Z; STRA::CopyW(ushort const *)
0x18000c421  mov     ebx, eax
0x18000c423  jmp     short loc_18000C438
0x18000c425  mov     ebx, edi
0x18000c427  mov     edx, ebx
0x18000c429  jmp     short loc_18000C42D
0x18000c42b  mov     edx, eax; int
0x18000c42d  mov     r8, r14; char *
0x18000c430  mov     rcx, rsi; struct IHttpContext *
0x18000c433  call    ?TraceInvalidIfHeader@DAV_TRACE@@SAXPEAVIHttpContext@@JPEBD@Z; DAV_TRACE::TraceInvalidIfHeader(IHttpContext *,long,char const *)
0x18000c438  lea     rcx, [rsp+4F0h+var_4A0]; this
0x18000c43d  call    ??1IF_STATE@@QEAA@XZ; IF_STATE::~IF_STATE(void)
0x18000c442  test    ebx, ebx
0x18000c444  js      short loc_18000C48E
0x18000c446  cmp     ebx, edi
0x18000c448  jz      short loc_18000C48E
0x18000c44a  mov     rcx, [r15+8]; struct IHttpContext *
0x18000c44e  cmp     [rbp+3F0h+var_30], r12d
0x18000c455  jnz     loc_18000C4E9
0x18000c45b  mov     rax, [rcx]
0x18000c45e  mov     rax, [rax+110h]
0x18000c465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c46a  mov     r10, rax
0x18000c46d  mov     byte ptr [rsp+4F0h+var_4D0], 3
0x18000c472  xor     r9d, r9d
0x18000c475  lea     rdx, aLockInvalidReq; "LOCK: Invalid Request -- Empty Entity B"...
0x18000c47c  xor     r8d, r8d
0x18000c47f  mov     rcx, [rax]
0x18000c482  mov     rax, [rcx+20h]
0x18000c486  mov     rcx, r10
0x18000c489  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c48e  xor     r9d, r9d; unsigned __int16
0x18000c491  mov     dword ptr [rsp+4F0h+var_4D0], r12d; int
0x18000c496  mov     edx, 190h; unsigned __int16
0x18000c49b  lea     r8, aBadRequest; "Bad Request"
0x18000c4a2  mov     rcx, r15; this
0x18000c4a5  mov     ebx, 2
0x18000c4aa  call    ?FinishRequest@DAV_BASE_HANDLER@@QEAAXGPEBDGJ@Z; DAV_BASE_HANDLER::FinishRequest(ushort,char const *,ushort,long)
0x18000c4af  lea     rcx, [rbp+3F0h+var_60]
0x18000c4b6  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000c4bc  mov     eax, ebx
0x18000c4be  mov     rcx, [rbp+3F0h+var_28]
0x18000c4c5  xor     rcx, rsp; StackCookie
0x18000c4c8  call    __security_check_cookie
0x18000c4cd  lea     r11, [rsp+4F0h+var_20]
0x18000c4d5  mov     rbx, [r11+38h]
0x18000c4d9  mov     rsi, [r11+40h]
0x18000c4dd  mov     rsp, r11
0x18000c4e0  pop     r15
0x18000c4e2  pop     r14
0x18000c4e4  pop     r12
0x18000c4e6  pop     rdi
0x18000c4e7  pop     rbp
0x18000c4e8  retn
0x18000c4e9  mov     rax, [r15+18h]
0x18000c4ed  mov     rdi, [r15+15C8h]
0x18000c4f4  mov     rsi, [r15+230h]
0x18000c4fb  mov     r14, [rbp+3F0h+var_40]
0x18000c502  mov     rbx, [rax+0D00h]
0x18000c509  call    ?GetEffectiveUser@@YAPEBGPEAVIHttpContext@@@Z; GetEffectiveUser(IHttpContext *)
0x18000c50e  mov     r10, [rbx+10h]
0x18000c512  lea     rdx, [r15+0F8h]
0x18000c519  mov     r8, rax
0x18000c51c  mov     r9, r14
0x18000c51f  mov     rcx, [r10]
0x18000c522  mov     rax, [rcx+48h]
0x18000c526  lea     rcx, [rsp+4F0h+var_4B0]
0x18000c52b  mov     [rsp+4F0h+var_4C0], rcx
0x18000c530  mov     rcx, r10
0x18000c533  mov     [rsp+4F0h+var_4C8], rdi
0x18000c538  mov     qword ptr [rsp+4F0h+var_4D0], rsi
0x18000c53d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c542  mov     ebx, eax
0x18000c544  test    eax, eax
0x18000c546  js      short loc_18000C5A1
0x18000c548  lea     rdi, [r15+1C0h]
0x18000c54f  mov     [rsp+4F0h+var_4D0], r12w; unsigned __int16
0x18000c555  mov     rcx, rdi; this
0x18000c558  lea     r9, aOk; "OK"
0x18000c55f  mov     r8d, 0C8h; unsigned __int16
0x18000c565  lea     rdx, aProp_0; "prop"
0x18000c56c  call    ?BeginXmlCommon@XML_RESPONDER@@AEAAJPEBDG0G@Z; XML_RESPONDER::BeginXmlCommon(char const *,ushort,char const *,ushort)
0x18000c571  mov     ebx, eax
0x18000c573  test    eax, eax
0x18000c575  js      short loc_18000C5A1
0x18000c577  mov     r8, [r15+80h]; unsigned __int16 *
0x18000c57e  mov     rcx, rdi; this
0x18000c581  mov     rdx, [rsp+4F0h+var_4B0]; struct IPubLock *
0x18000c586  call    ?SendXmlLockDiscovery@XML_RESPONDER@@QEAAJPEAVIPubLock@@PEBG@Z; XML_RESPONDER::SendXmlLockDiscovery(IPubLock *,ushort const *)
0x18000c58b  mov     ebx, eax
0x18000c58d  test    eax, eax
0x18000c58f  js      short loc_18000C5A1
0x18000c591  cmp     [rdi+60h], r12d
0x18000c595  jz      short loc_18000C5A1
0x18000c597  mov     rcx, rdi; this
0x18000c59a  call    ?FinishXmlLockResponse@XML_RESPONDER@@QEAAJXZ; XML_RESPONDER::FinishXmlLockResponse(void)
0x18000c59f  mov     ebx, eax
0x18000c5a1  mov     rcx, [rsp+4F0h+var_4B0]
0x18000c5a6  test    rcx, rcx
0x18000c5a9  jz      short loc_18000C5BC
0x18000c5ab  mov     rax, [rcx]
0x18000c5ae  mov     rax, [rax+10h]
0x18000c5b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5b7  mov     [rsp+4F0h+var_4B0], r12
0x18000c5bc  test    ebx, ebx
0x18000c5be  js      short loc_18000C5DB
0x18000c5c0  mov     rcx, [r15+8]
0x18000c5c4  mov     rax, [rcx]
0x18000c5c7  mov     rax, [rax+0C8h]
0x18000c5ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5d3  mov     ebx, r12d
0x18000c5d6  jmp     loc_18000C4AF
0x18000c5db  mov     edx, ebx; int
0x18000c5dd  mov     rcx, r15; this
0x18000c5e0  call    ?MapAndHandleError@DAV_BASE_HANDLER@@QEAAXJ@Z; DAV_BASE_HANDLER::MapAndHandleError(long)
0x18000c5e5  mov     ebx, 2
0x18000c5ea  jmp     loc_18000C4AF
```
