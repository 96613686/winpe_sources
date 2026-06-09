# XML_RENDERER::AppendActiveLock(IPubLock *,ushort const *)

- ea: `0x180013bb0`
- end: `0x180013e71`
- name: `?AppendActiveLock@XML_RENDERER@@AEAAJPEAVIPubLock@@PEBG@Z`
- size: `705`
- prototype: `__int64 __fastcall(XML_RENDERER *__hidden this, struct IPubLock *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180013e78`
- `0x1800153ac`

## callees

- `0x180013bb0`
- `0x180013fd4`
- `0x1800141b4`
- `0x1800142bc`
- `0x180014ef4`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z` at `0x180013d38`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z` at `0x180013d38`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x180013d4c`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x180013d4c`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180013d2d`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180013d74`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180013e2f`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180013d2d`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180013d74`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180013e2f`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180013c11`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180013c2c`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180013c6b`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180013c8a`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180013cd7`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180013cf6`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180013d67`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180013c11`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180013c2c`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180013c6b`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180013c8a`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180013cd7`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180013cf6`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180013d67`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180013d1d`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180013de1`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180013d1d`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180013de1`

## string_xrefs

- `0x180013c0a`: `<D:locktype><D:write/></D:locktype>`

## pseudocode

```c
__int64 __fastcall XML_RENDERER::AppendActiveLock(XML_RENDERER *this, struct IPubLock *a2, const unsigned __int16 *a3)
{
  int appended; // ebx
  int v7; // eax
  const char *v8; // rdx
  int v9; // eax
  const char *v10; // rdx
  const unsigned __int16 *v11; // rbx
  unsigned __int64 v12; // rax
  const unsigned __int16 *v13; // rax
  const unsigned __int16 *v14; // rdi
  _BYTE v16[56]; // [rsp+20h] [rbp-68h] BYREF

  appended = XML_RENDERER::OpenOrCloseXmlTag(this, "activelock", 0);
  if ( appended < 0 )
    return (unsigned int)appended;
  if ( (*(unsigned int (__fastcall **)(struct IPubLock *))(*(_QWORD *)a2 + 80LL))(a2) )
    return (unsigned int)-2147024809;
  appended = STRA::Append((XML_RENDERER *)((char *)this + 24), "<D:locktype><D:write/></D:locktype>");
  if ( appended >= 0 && !*(_DWORD *)this )
    appended = STRA::Append((XML_RENDERER *)((char *)this + 24), "\r\n");
  if ( appended < 0 )
    return (unsigned int)appended;
  v7 = (*(__int64 (__fastcall **)(struct IPubLock *))(*(_QWORD *)a2 + 72LL))(a2);
  if ( v7 )
  {
    if ( v7 != 1 )
      return (unsigned int)-2147024809;
    v8 = "<D:lockscope><D:shared/></D:lockscope>";
  }
  else
  {
    v8 = "<D:lockscope><D:exclusive/></D:lockscope>";
  }
  appended = STRA::Append((XML_RENDERER *)((char *)this + 24), v8);
  if ( appended < 0 )
    return (unsigned int)appended;
  if ( !*(_DWORD *)this )
    appended = STRA::Append((XML_RENDERER *)((char *)this + 24), "\r\n");
  if ( appended < 0 )
    return (unsigned int)appended;
  v9 = (*(__int64 (__fastcall **)(struct IPubLock *))(*(_QWORD *)a2 + 56LL))(a2);
  if ( v9 )
  {
    if ( v9 == 1 )
    {
      v10 = "<D:depth>1</D:depth>";
      goto LABEL_21;
    }
    if ( v9 == 2 )
    {
      v10 = "<D:depth>infinity</D:depth>";
      goto LABEL_21;
    }
    return (unsigned int)-2147024809;
  }
  v10 = "<D:depth>0</D:depth>";
LABEL_21:
  appended = STRA::Append((XML_RENDERER *)((char *)this + 24), v10);
  if ( appended >= 0 )
  {
    if ( !*(_DWORD *)this )
      appended = STRA::Append((XML_RENDERER *)((char *)this + 24), "\r\n");
    if ( appended >= 0 )
    {
      v11 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IPubLock *))(*(_QWORD *)a2 + 40LL))(a2);
      STRA::STRA((STRA *)v16);
      if ( !v11 )
      {
        STRA::~STRA((STRA *)v16);
LABEL_32:
        v12 = (*(__int64 (__fastcall **)(struct IPubLock *))(*(_QWORD *)a2 + 64LL))(a2);
        appended = XML_RENDERER::AppendLockTimeout(this, v12);
        if ( appended >= 0 )
        {
          v13 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IPubLock *))(*(_QWORD *)a2 + 24LL))(a2);
          appended = XML_RENDERER::AppendLockToken(this, v13);
          if ( appended >= 0 )
          {
            v14 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IPubLock *))(*(_QWORD *)a2 + 32LL))(a2);
            STRA::STRA((STRA *)v16);
            appended = XML_RENDERER::OpenOrCloseXmlTag(this, "lockroot", 0);
            if ( appended >= 0 )
            {
              appended = XML_RENDERER::AppendHRef((const char **)this, a3, v14);
              if ( appended >= 0 )
                appended = XML_RENDERER::OpenOrCloseXmlTag(this, "lockroot", 1);
            }
            STRA::~STRA((STRA *)v16);
            if ( appended >= 0 )
              return (unsigned int)XML_RENDERER::OpenOrCloseXmlTag(this, "activelock", 1);
          }
        }
        return (unsigned int)appended;
      }
      appended = STRA::CopyWToUTF8Unescaped((STRA *)v16, v11);
      if ( appended >= 0 )
      {
        appended = STRA::Append((XML_RENDERER *)((char *)this + 24), (const struct STRA *)v16);
        if ( appended >= 0 && !*(_DWORD *)this )
          appended = STRA::Append((XML_RENDERER *)((char *)this + 24), "\r\n");
      }
      STRA::~STRA((STRA *)v16);
      if ( appended >= 0 )
        goto LABEL_32;
    }
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180013bb0  push    rbx
0x180013bb2  push    rbp
0x180013bb3  push    rsi
0x180013bb4  push    rdi
0x180013bb5  push    r14
0x180013bb7  sub     rsp, 60h
0x180013bbb  mov     rax, cs:__security_cookie
0x180013bc2  xor     rax, rsp
0x180013bc5  mov     [rsp+88h+var_30], rax
0x180013bca  mov     rbp, r8
0x180013bcd  mov     r14, rdx
0x180013bd0  xor     r8d, r8d; int
0x180013bd3  lea     rdx, aActivelock; "activelock"
0x180013bda  mov     rsi, rcx
0x180013bdd  call    ?OpenOrCloseXmlTag@XML_RENDERER@@AEAAJPEBDH@Z; XML_RENDERER::OpenOrCloseXmlTag(char const *,int)
0x180013be2  mov     ebx, eax
0x180013be4  test    eax, eax
0x180013be6  js      loc_180013E57
0x180013bec  mov     rax, [r14]
0x180013bef  mov     rcx, r14
0x180013bf2  mov     rax, [rax+50h]
0x180013bf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013bfb  test    eax, eax
0x180013bfd  jnz     loc_180013E52
0x180013c03  lea     rdi, [rsi+18h]
0x180013c07  mov     rcx, rdi
0x180013c0a  lea     rdx, aDLocktypeDWrit; "<D:locktype><D:write/></D:locktype>"
0x180013c11  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180013c17  mov     ebx, eax
0x180013c19  test    eax, eax
0x180013c1b  js      short loc_180013C34
0x180013c1d  cmp     dword ptr [rsi], 0
0x180013c20  jnz     short loc_180013C34
0x180013c22  lea     rdx, asc_1800263B4; "\r\n"
0x180013c29  mov     rcx, rdi
0x180013c2c  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180013c32  mov     ebx, eax
0x180013c34  test    ebx, ebx
0x180013c36  js      loc_180013E57
0x180013c3c  mov     rax, [r14]
0x180013c3f  mov     rcx, r14
0x180013c42  mov     rax, [rax+48h]
0x180013c46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c4b  test    eax, eax
0x180013c4d  jnz     short loc_180013C58
0x180013c4f  lea     rdx, aDLockscopeDExc; "<D:lockscope><D:exclusive/></D:lockscop"...
0x180013c56  jmp     short loc_180013C68
0x180013c58  cmp     eax, 1
0x180013c5b  jnz     loc_180013E52
0x180013c61  lea     rdx, aDLockscopeDSha; "<D:lockscope><D:shared/></D:lockscope>"
0x180013c68  mov     rcx, rdi
0x180013c6b  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180013c71  mov     ebx, eax
0x180013c73  test    eax, eax
0x180013c75  js      loc_180013E57
0x180013c7b  cmp     dword ptr [rsi], 0
0x180013c7e  jnz     short loc_180013C92
0x180013c80  lea     rdx, asc_1800263B4; "\r\n"
0x180013c87  mov     rcx, rdi
0x180013c8a  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180013c90  mov     ebx, eax
0x180013c92  test    ebx, ebx
0x180013c94  js      loc_180013E57
0x180013c9a  mov     rax, [r14]
0x180013c9d  mov     rcx, r14
0x180013ca0  mov     rax, [rax+38h]
0x180013ca4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ca9  test    eax, eax
0x180013cab  jnz     short loc_180013CB6
0x180013cad  lea     rdx, aDDepth0DDepth; "<D:depth>0</D:depth>"
0x180013cb4  jmp     short loc_180013CD4
0x180013cb6  cmp     eax, 1
0x180013cb9  jnz     short loc_180013CC4
0x180013cbb  lea     rdx, aDDepth1DDepth; "<D:depth>1</D:depth>"
0x180013cc2  jmp     short loc_180013CD4
0x180013cc4  cmp     eax, 2
0x180013cc7  jnz     loc_180013E52
0x180013ccd  lea     rdx, aDDepthInfinity; "<D:depth>infinity</D:depth>"
0x180013cd4  mov     rcx, rdi
0x180013cd7  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180013cdd  mov     ebx, eax
0x180013cdf  test    eax, eax
0x180013ce1  js      loc_180013E57
0x180013ce7  cmp     dword ptr [rsi], 0
0x180013cea  jnz     short loc_180013CFE
0x180013cec  lea     rdx, asc_1800263B4; "\r\n"
0x180013cf3  mov     rcx, rdi
0x180013cf6  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180013cfc  mov     ebx, eax
0x180013cfe  test    ebx, ebx
0x180013d00  js      loc_180013E57
0x180013d06  mov     rax, [r14]
0x180013d09  mov     rcx, r14
0x180013d0c  mov     rax, [rax+28h]
0x180013d10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d15  lea     rcx, [rsp+88h+var_68]
0x180013d1a  mov     rbx, rax
0x180013d1d  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180013d23  lea     rcx, [rsp+88h+var_68]
0x180013d28  test    rbx, rbx
0x180013d2b  jnz     short loc_180013D35
0x180013d2d  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180013d33  jmp     short loc_180013D82
0x180013d35  mov     rdx, rbx
0x180013d38  call    cs:__imp_?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z; STRA::CopyWToUTF8Unescaped(ushort const *)
0x180013d3e  mov     ebx, eax
0x180013d40  test    eax, eax
0x180013d42  js      short loc_180013D6F
0x180013d44  lea     rdx, [rsp+88h+var_68]
0x180013d49  mov     rcx, rdi
0x180013d4c  call    cs:__imp_?Append@STRA@@QEAAJAEBV1@@Z; STRA::Append(STRA const &)
0x180013d52  mov     ebx, eax
0x180013d54  test    eax, eax
0x180013d56  js      short loc_180013D6F
0x180013d58  cmp     dword ptr [rsi], 0
0x180013d5b  jnz     short loc_180013D6F
0x180013d5d  lea     rdx, asc_1800263B4; "\r\n"
0x180013d64  mov     rcx, rdi
0x180013d67  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180013d6d  mov     ebx, eax
0x180013d6f  lea     rcx, [rsp+88h+var_68]
0x180013d74  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180013d7a  test    ebx, ebx
0x180013d7c  js      loc_180013E57
0x180013d82  mov     rax, [r14]
0x180013d85  mov     rcx, r14
0x180013d88  mov     rax, [rax+40h]
0x180013d8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d91  mov     rdx, rax; unsigned __int64
0x180013d94  mov     rcx, rsi; this
0x180013d97  call    ?AppendLockTimeout@XML_RENDERER@@AEAAJ_K@Z; XML_RENDERER::AppendLockTimeout(unsigned __int64)
0x180013d9c  mov     ebx, eax
0x180013d9e  test    eax, eax
0x180013da0  js      loc_180013E57
0x180013da6  mov     rax, [r14]
0x180013da9  mov     rcx, r14
0x180013dac  mov     rax, [rax+18h]
0x180013db0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013db5  mov     rdx, rax; unsigned __int16 *
0x180013db8  mov     rcx, rsi; this
0x180013dbb  call    ?AppendLockToken@XML_RENDERER@@AEAAJPEBG@Z; XML_RENDERER::AppendLockToken(ushort const *)
0x180013dc0  mov     ebx, eax
0x180013dc2  test    eax, eax
0x180013dc4  js      loc_180013E57
0x180013dca  mov     rax, [r14]
0x180013dcd  mov     rcx, r14
0x180013dd0  mov     rax, [rax+20h]
0x180013dd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013dd9  lea     rcx, [rsp+88h+var_68]
0x180013dde  mov     rdi, rax
0x180013de1  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180013de7  xor     r8d, r8d; int
0x180013dea  lea     rdx, aLockroot; "lockroot"
0x180013df1  mov     rcx, rsi; this
0x180013df4  call    ?OpenOrCloseXmlTag@XML_RENDERER@@AEAAJPEBDH@Z; XML_RENDERER::OpenOrCloseXmlTag(char const *,int)
0x180013df9  mov     ebx, eax
0x180013dfb  test    eax, eax
0x180013dfd  js      short loc_180013E2A
0x180013dff  mov     r8, rdi; unsigned __int16 *
0x180013e02  mov     rdx, rbp; unsigned __int16 *
0x180013e05  mov     rcx, rsi; this
0x180013e08  call    ?AppendHRef@XML_RENDERER@@AEAAJPEBG0@Z; XML_RENDERER::AppendHRef(ushort const *,ushort const *)
0x180013e0d  mov     ebx, eax
0x180013e0f  test    eax, eax
0x180013e11  js      short loc_180013E2A
0x180013e13  mov     r8d, 1; int
0x180013e19  lea     rdx, aLockroot; "lockroot"
0x180013e20  mov     rcx, rsi; this
0x180013e23  call    ?OpenOrCloseXmlTag@XML_RENDERER@@AEAAJPEBDH@Z; XML_RENDERER::OpenOrCloseXmlTag(char const *,int)
0x180013e28  mov     ebx, eax
0x180013e2a  lea     rcx, [rsp+88h+var_68]
0x180013e2f  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180013e35  test    ebx, ebx
0x180013e37  js      short loc_180013E57
0x180013e39  mov     r8d, 1; int
0x180013e3f  lea     rdx, aActivelock; "activelock"
0x180013e46  mov     rcx, rsi; this
0x180013e49  call    ?OpenOrCloseXmlTag@XML_RENDERER@@AEAAJPEBDH@Z; XML_RENDERER::OpenOrCloseXmlTag(char const *,int)
0x180013e4e  mov     ebx, eax
0x180013e50  jmp     short loc_180013E57
0x180013e52  mov     ebx, 80070057h
0x180013e57  mov     eax, ebx
0x180013e59  mov     rcx, [rsp+88h+var_30]
0x180013e5e  xor     rcx, rsp; StackCookie
0x180013e61  call    __security_check_cookie
0x180013e66  add     rsp, 60h
0x180013e6a  pop     r14
0x180013e6c  pop     rdi
0x180013e6d  pop     rsi
0x180013e6e  pop     rbp
0x180013e6f  pop     rbx
0x180013e70  retn
```
