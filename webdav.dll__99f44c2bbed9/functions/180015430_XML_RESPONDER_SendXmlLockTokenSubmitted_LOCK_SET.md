# XML_RESPONDER::SendXmlLockTokenSubmitted(LOCK_SET *)

- ea: `0x180015430`
- end: `0x1800155cd`
- name: `?SendXmlLockTokenSubmitted@XML_RESPONDER@@QEAAJPEAVLOCK_SET@@@Z`
- size: `413`
- prototype: `__int64 __fastcall(XML_RESPONDER *__hidden this, struct LOCK_SET *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800036a4`

## callees

- `0x180013fd4`
- `0x180014388`
- `0x180014ef4`
- `0x18001526c`
- `0x180015430`
- `0x180022520`
- `0x180023010`

## string_xrefs

- `0x18001555d`: `lock-token-submitted`
- `0x18001558b`: `lock-token-submitted`

## pseudocode

```c
__int64 __fastcall XML_RESPONDER::SendXmlLockTokenSubmitted(XML_RESPONDER *this, struct LOCK_SET *a2)
{
  _BYTE *v2; // rax
  struct IPubUriLockList *v5; // rax
  int appended; // ebx
  struct IPubUriLockList *v7; // rax
  struct IPubUriLockList *v8; // r14
  struct IPubUriLockList *v9; // rax
  const unsigned __int16 *v10; // rsi
  int v12[4]; // [rsp+20h] [rbp-78h] BYREF
  _BYTE v13[64]; // [rsp+30h] [rbp-68h] BYREF

  v2 = (_BYTE *)*((_QWORD *)this + 7);
  v12[0] = 1;
  *v2 = 0;
  *((_DWORD *)this + 18) = 0;
  v5 = (struct IPubUriLockList *)(*(__int64 (__fastcall **)(struct LOCK_SET *, _BYTE *))(*(_QWORD *)a2 + 48LL))(a2, v13);
  if ( !v5 )
    goto LABEL_4;
  do
  {
    appended = XML_RENDERER::AppendLockTokenSubmittedIfNecessary(this, v5, v12);
    v5 = (struct IPubUriLockList *)(*(__int64 (__fastcall **)(struct LOCK_SET *, _BYTE *))(*(_QWORD *)a2 + 56LL))(
                                     a2,
                                     v13);
  }
  while ( v5 );
  if ( appended >= 0 )
  {
LABEL_4:
    v7 = (struct IPubUriLockList *)(*(__int64 (__fastcall **)(struct LOCK_SET *))(*(_QWORD *)a2 + 40LL))(a2);
    v8 = v7;
    if ( v7 )
    {
      appended = XML_RENDERER::AppendLockTokenSubmittedIfNecessary(this, v7, v12);
      if ( appended < 0 )
      {
LABEL_17:
        if ( appended >= 0 )
          return (unsigned int)XML_RESPONDER::Flush(this);
        return (unsigned int)appended;
      }
    }
    v9 = (struct IPubUriLockList *)(*(__int64 (__fastcall **)(struct LOCK_SET *, _BYTE *))(*(_QWORD *)a2 + 72LL))(
                                     a2,
                                     v13);
    if ( !v9 )
      goto LABEL_15;
    do
    {
      appended = XML_RENDERER::AppendLockTokenSubmittedIfNecessary(this, v9, v12);
      v9 = (struct IPubUriLockList *)(*(__int64 (__fastcall **)(struct LOCK_SET *, _BYTE *))(*(_QWORD *)a2 + 80LL))(
                                       a2,
                                       v13);
    }
    while ( v9 );
    if ( appended >= 0 )
    {
LABEL_15:
      if ( !v12[0] )
        goto LABEL_16;
      if ( !v8
        || (v10 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IPubUriLockList *))(*(_QWORD *)v8 + 16LL))(v8)) == 0 )
      {
        v10 = L"/unknown";
      }
      appended = XML_RENDERER::OpenOrCloseXmlTag(this, "lock-token-submitted", 0);
      if ( appended >= 0 )
        appended = XML_RENDERER::AppendHRef((const char **)this, 0, v10);
      if ( appended >= 0 )
      {
LABEL_16:
        appended = XML_RENDERER::OpenOrCloseXmlTag(this, "lock-token-submitted", 1);
        goto LABEL_17;
      }
    }
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180015430  mov     [rsp+arg_10], rbx
0x180015435  push    rsi
0x180015436  push    rdi
0x180015437  push    r14
0x180015439  sub     rsp, 80h
0x180015440  mov     rax, cs:__security_cookie
0x180015447  xor     rax, rsp
0x18001544a  mov     [rsp+98h+var_28], rax
0x18001544f  mov     rax, [rcx+38h]
0x180015453  mov     rsi, rdx
0x180015456  mov     rdi, rcx
0x180015459  mov     [rsp+98h+var_78], 1
0x180015461  mov     byte ptr [rax], 0
0x180015464  mov     dword ptr [rcx+48h], 0
0x18001546b  mov     rcx, rsi
0x18001546e  mov     rax, [rdx]
0x180015471  lea     rdx, [rsp+98h+var_68]
0x180015476  mov     rax, [rax+30h]
0x18001547a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001547f  test    rax, rax
0x180015482  jz      short loc_1800154B7
0x180015484  lea     r8, [rsp+98h+var_78]; int *
0x180015489  mov     rdx, rax; struct IPubUriLockList *
0x18001548c  mov     rcx, rdi; this
0x18001548f  call    ?AppendLockTokenSubmittedIfNecessary@XML_RENDERER@@AEAAJPEAVIPubUriLockList@@PEAH@Z; XML_RENDERER::AppendLockTokenSubmittedIfNecessary(IPubUriLockList *,int *)
0x180015494  mov     ebx, eax
0x180015496  lea     rdx, [rsp+98h+var_68]
0x18001549b  mov     rax, [rsi]
0x18001549e  mov     rcx, rsi
0x1800154a1  mov     rax, [rax+38h]
0x1800154a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154aa  test    rax, rax
0x1800154ad  jnz     short loc_180015484
0x1800154af  test    ebx, ebx
0x1800154b1  js      loc_1800155AA
0x1800154b7  mov     rax, [rsi]
0x1800154ba  mov     rcx, rsi
0x1800154bd  mov     rax, [rax+28h]
0x1800154c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154c6  mov     r14, rax
0x1800154c9  test    rax, rax
0x1800154cc  jz      short loc_1800154E8
0x1800154ce  lea     r8, [rsp+98h+var_78]; int *
0x1800154d3  mov     rdx, rax; struct IPubUriLockList *
0x1800154d6  mov     rcx, rdi; this
0x1800154d9  call    ?AppendLockTokenSubmittedIfNecessary@XML_RENDERER@@AEAAJPEAVIPubUriLockList@@PEAH@Z; XML_RENDERER::AppendLockTokenSubmittedIfNecessary(IPubUriLockList *,int *)
0x1800154de  mov     ebx, eax
0x1800154e0  test    eax, eax
0x1800154e2  js      loc_18001559C
0x1800154e8  mov     rcx, [rsi]
0x1800154eb  lea     rdx, [rsp+98h+var_68]
0x1800154f0  mov     rax, [rcx+48h]
0x1800154f4  mov     rcx, rsi
0x1800154f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154fc  test    rax, rax
0x1800154ff  jz      short loc_180015530
0x180015501  lea     r8, [rsp+98h+var_78]; int *
0x180015506  mov     rdx, rax; struct IPubUriLockList *
0x180015509  mov     rcx, rdi; this
0x18001550c  call    ?AppendLockTokenSubmittedIfNecessary@XML_RENDERER@@AEAAJPEAVIPubUriLockList@@PEAH@Z; XML_RENDERER::AppendLockTokenSubmittedIfNecessary(IPubUriLockList *,int *)
0x180015511  mov     ebx, eax
0x180015513  lea     rdx, [rsp+98h+var_68]
0x180015518  mov     rax, [rsi]
0x18001551b  mov     rcx, rsi
0x18001551e  mov     rax, [rax+50h]
0x180015522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015527  test    rax, rax
0x18001552a  jnz     short loc_180015501
0x18001552c  test    ebx, ebx
0x18001552e  js      short loc_1800155AA
0x180015530  cmp     [rsp+98h+var_78], 0
0x180015535  jz      short loc_180015585
0x180015537  test    r14, r14
0x18001553a  jz      short loc_180015553
0x18001553c  mov     rax, [r14]
0x18001553f  mov     rcx, r14
0x180015542  mov     rax, [rax+10h]
0x180015546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001554b  mov     rsi, rax
0x18001554e  test    rax, rax
0x180015551  jnz     short loc_18001555A
0x180015553  lea     rsi, aUnknown_0; "/unknown"
0x18001555a  xor     r8d, r8d; int
0x18001555d  lea     rdx, aLockTokenSubmi; "lock-token-submitted"
0x180015564  mov     rcx, rdi; this
0x180015567  call    ?OpenOrCloseXmlTag@XML_RENDERER@@AEAAJPEBDH@Z; XML_RENDERER::OpenOrCloseXmlTag(char const *,int)
0x18001556c  mov     ebx, eax
0x18001556e  test    eax, eax
0x180015570  js      short loc_180015581
0x180015572  mov     r8, rsi; unsigned __int16 *
0x180015575  xor     edx, edx; unsigned __int16 *
0x180015577  mov     rcx, rdi; this
0x18001557a  call    ?AppendHRef@XML_RENDERER@@AEAAJPEBG0@Z; XML_RENDERER::AppendHRef(ushort const *,ushort const *)
0x18001557f  mov     ebx, eax
0x180015581  test    ebx, ebx
0x180015583  js      short loc_1800155AA
0x180015585  mov     r8d, 1; int
0x18001558b  lea     rdx, aLockTokenSubmi; "lock-token-submitted"
0x180015592  mov     rcx, rdi; this
0x180015595  call    ?OpenOrCloseXmlTag@XML_RENDERER@@AEAAJPEBDH@Z; XML_RENDERER::OpenOrCloseXmlTag(char const *,int)
0x18001559a  mov     ebx, eax
0x18001559c  test    ebx, ebx
0x18001559e  js      short loc_1800155AA
0x1800155a0  mov     rcx, rdi; this
0x1800155a3  call    ?Flush@XML_RESPONDER@@AEAAJXZ; XML_RESPONDER::Flush(void)
0x1800155a8  mov     ebx, eax
0x1800155aa  mov     eax, ebx
0x1800155ac  mov     rcx, [rsp+98h+var_28]
0x1800155b1  xor     rcx, rsp; StackCookie
0x1800155b4  call    __security_check_cookie
0x1800155b9  mov     rbx, [rsp+98h+arg_10]
0x1800155c1  add     rsp, 80h
0x1800155c8  pop     r14
0x1800155ca  pop     rdi
0x1800155cb  pop     rsi
0x1800155cc  retn
```
