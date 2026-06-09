# UL_NATIVE_REQUEST::PushPromise(_HTTP_VERB,ushort const *,ushort const *,_HTTP_REQUEST_HEADERS *)

- ea: `0x180014d64`
- end: `0x180014e95`
- name: `?PushPromise@UL_NATIVE_REQUEST@@QEAAJW4_HTTP_VERB@@PEBG1PEAU_HTTP_REQUEST_HEADERS@@@Z`
- size: `305`
- prototype: `__int64 __fastcall(UL_NATIVE_REQUEST *__hidden this, enum _HTTP_VERB, const unsigned __int16 *, const unsigned __int16 *, struct _HTTP_REQUEST_HEADERS *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180015810`

## callees

- `0x180012050`
- `0x180014d64`
- `0x1800160a0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180014e4d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180014e4d`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180014e13`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180014e13`
- `iisutil!?IsEmpty@STRA@@QEBA_NXZ` at `0x180014e00`
- `iisutil!?IsEmpty@STRA@@QEBA_NXZ` at `0x180014e00`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z` at `0x180014dcc`
- `iisutil!?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z` at `0x180014dcc`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180014daa`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180014daa`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180014e6b`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180014e6b`

## pseudocode

```c
__int64 __fastcall UL_NATIVE_REQUEST::PushPromise(
        UL_NATIVE_REQUEST *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct _HTTP_REQUEST_HEADERS *a5)
{
  unsigned int v9; // ebx
  void *v10; // rdi
  unsigned int (*v11)(void *, unsigned __int64, enum _HTTP_VERB, const unsigned __int16 *, const char *, struct _HTTP_REQUEST_HEADERS *); // rsi
  char *Str; // rax
  int v13; // edi
  PSRWLOCK SRWLock; // [rsp+40h] [rbp-88h] BYREF
  _BYTE v16[56]; // [rsp+48h] [rbp-80h] BYREF

  SRWLock = 0;
  STRA::STRA((STRA *)v16);
  v9 = 0;
  if ( UL_NATIVE_REQUEST::sm_pfnHttpDeclarePush )
  {
    if ( a4 )
      v9 = STRA::CopyWToUTF8Unescaped((STRA *)v16, a4);
    v10 = UL_APP_POOL::QueryAndLockHandle((WP_CONTEXT *)((char *)g_pwpContext + 760), &SRWLock);
    if ( v10 )
    {
      v11 = UL_NATIVE_REQUEST::sm_pfnHttpDeclarePush;
      if ( STRA::IsEmpty((STRA *)v16) )
        Str = 0;
      else
        Str = STRA::QueryStr((STRA *)v16);
      v13 = ((__int64 (__fastcall *)(void *, _QWORD, _QWORD, const unsigned __int16 *, char *, struct _HTTP_REQUEST_HEADERS *))v11)(
              v10,
              *(_QWORD *)(*((_QWORD *)this + 368) + 16LL),
              a2,
              a3,
              Str,
              a5);
    }
    else
    {
      v13 = 6;
    }
    ReleaseSRWLockShared(SRWLock);
    if ( v13 )
    {
      if ( v13 > 0 )
        v9 = (unsigned __int16)v13 | 0x80070000;
      else
        v9 = v13;
    }
  }
  STRA::~STRA((STRA *)v16);
  return v9;
}

```

## disassembly

```asm
0x180014d64  push    rbx
0x180014d66  push    rbp
0x180014d67  push    rsi
0x180014d68  push    rdi
0x180014d69  push    r12
0x180014d6b  push    r14
0x180014d6d  push    r15
0x180014d6f  sub     rsp, 90h
0x180014d76  mov     rax, cs:__security_cookie
0x180014d7d  xor     rax, rsp
0x180014d80  mov     [rsp+0C8h+var_48], rax
0x180014d88  mov     r12, [rsp+0C8h+arg_20]
0x180014d90  mov     rbp, rcx
0x180014d93  lea     rcx, [rsp+0C8h+var_80]
0x180014d98  mov     [rsp+0C8h+SRWLock], 0
0x180014da1  mov     rdi, r9
0x180014da4  mov     r15, r8
0x180014da7  mov     r14d, edx
0x180014daa  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180014db0  xor     ebx, ebx
0x180014db2  cmp     cs:?sm_pfnHttpDeclarePush@UL_NATIVE_REQUEST@@0P6AKPEAX_KW4_HTTP_VERB@@PEBGPEBDPEAU_HTTP_REQUEST_HEADERS@@@ZEA, rbx; ulong (*UL_NATIVE_REQUEST::sm_pfnHttpDeclarePush)(void *,unsigned __int64,_HTTP_VERB,ushort const *,char const *,_HTTP_REQUEST_HEADERS *)
0x180014db9  jz      loc_180014E66
0x180014dbf  test    rdi, rdi
0x180014dc2  jz      short loc_180014DD4
0x180014dc4  mov     rdx, rdi
0x180014dc7  lea     rcx, [rsp+0C8h+var_80]
0x180014dcc  call    cs:__imp_?CopyWToUTF8Unescaped@STRA@@QEAAJPEBG@Z; STRA::CopyWToUTF8Unescaped(ushort const *)
0x180014dd2  mov     ebx, eax
0x180014dd4  mov     rcx, cs:?g_pwpContext@@3PEAVWP_CONTEXT@@EA; WP_CONTEXT * g_pwpContext
0x180014ddb  lea     rdx, [rsp+0C8h+SRWLock]; void **
0x180014de0  add     rcx, 2F8h; this
0x180014de7  call    ?QueryAndLockHandle@UL_APP_POOL@@QEAAPEAXPEAPEAX@Z; UL_APP_POOL::QueryAndLockHandle(void * *)
0x180014dec  mov     rdi, rax
0x180014def  test    rax, rax
0x180014df2  jz      short loc_180014E43
0x180014df4  mov     rsi, cs:?sm_pfnHttpDeclarePush@UL_NATIVE_REQUEST@@0P6AKPEAX_KW4_HTTP_VERB@@PEBGPEBDPEAU_HTTP_REQUEST_HEADERS@@@ZEA; ulong (*UL_NATIVE_REQUEST::sm_pfnHttpDeclarePush)(void *,unsigned __int64,_HTTP_VERB,ushort const *,char const *,_HTTP_REQUEST_HEADERS *)
0x180014dfb  lea     rcx, [rsp+0C8h+var_80]
0x180014e00  call    cs:__imp_?IsEmpty@STRA@@QEBA_NXZ; STRA::IsEmpty(void)
0x180014e06  test    al, al
0x180014e08  jz      short loc_180014E0E
0x180014e0a  xor     eax, eax
0x180014e0c  jmp     short loc_180014E19
0x180014e0e  lea     rcx, [rsp+0C8h+var_80]
0x180014e13  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180014e19  mov     rdx, [rbp+0B80h]
0x180014e20  mov     r9, r15
0x180014e23  mov     [rsp+0C8h+var_A0], r12
0x180014e28  mov     r8d, r14d
0x180014e2b  mov     [rsp+0C8h+var_A8], rax
0x180014e30  mov     rcx, rdi
0x180014e33  mov     rax, rsi
0x180014e36  mov     rdx, [rdx+10h]
0x180014e3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e3f  mov     edi, eax
0x180014e41  jmp     short loc_180014E48
0x180014e43  mov     edi, 6
0x180014e48  mov     rcx, [rsp+0C8h+SRWLock]; SRWLock
0x180014e4d  call    cs:__imp_ReleaseSRWLockShared
0x180014e53  test    edi, edi
0x180014e55  jz      short loc_180014E66
0x180014e57  jg      short loc_180014E5D
0x180014e59  mov     ebx, edi
0x180014e5b  jmp     short loc_180014E66
0x180014e5d  movzx   ebx, di
0x180014e60  or      ebx, 80070000h
0x180014e66  lea     rcx, [rsp+0C8h+var_80]
0x180014e6b  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180014e71  mov     eax, ebx
0x180014e73  mov     rcx, [rsp+0C8h+var_48]
0x180014e7b  xor     rcx, rsp; StackCookie
0x180014e7e  call    __security_check_cookie
0x180014e83  add     rsp, 90h
0x180014e8a  pop     r15
0x180014e8c  pop     r14
0x180014e8e  pop     r12
0x180014e90  pop     rdi
0x180014e91  pop     rsi
0x180014e92  pop     rbp
0x180014e93  pop     rbx
0x180014e94  retn
```
