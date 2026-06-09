# DoVDirLogon(IHttpServer *,IIS_LOGON_PROVIDER *,IHttpTraceContext *,ushort const *,ushort const *,ulong,IHttpTokenEntry * *)

- ea: `0x180019bc4`
- end: `0x180019d52`
- name: `?DoVDirLogon@@YAJPEAVIHttpServer@@PEAVIIS_LOGON_PROVIDER@@PEAVIHttpTraceContext@@PEBG3KPEAPEAVIHttpTokenEntry@@@Z`
- size: `398`
- prototype: `int(struct IHttpServer *, struct IIS_LOGON_PROVIDER *, struct IHttpTraceContext *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, struct IHttpTokenEntry **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001d080`

## callees

- `0x180019bc4`
- `0x1800213d8`
- `0x180021fa4`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x180019c12`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180019c20`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180019c12`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180019c20`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180019d1d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180019d28`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180019d1d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180019d28`

## pseudocode

```c
__int64 __fastcall DoVDirLogon(
        struct IHttpServer *a1,
        struct IIS_LOGON_PROVIDER *a2,
        struct IHttpTraceContext *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned int a6,
        struct IHttpTokenEntry **a7)
{
  int v10; // ebx
  unsigned int v11; // edi
  struct IHttpServer *v12; // rcx
  __int64 v13; // rax
  struct sockaddr *v15; // [rsp+28h] [rbp-E0h]
  wchar_t *v16; // [rsp+40h] [rbp-C8h] BYREF
  _BYTE v17[56]; // [rsp+48h] [rbp-C0h] BYREF
  _BYTE v18[64]; // [rsp+80h] [rbp-88h] BYREF

  v16 = (wchar_t *)&TOKEN_KEY::`vftable';
  STRU::STRU((STRU *)v17);
  STRU::STRU((STRU *)v18);
  *a7 = 0;
  if ( a6 )
  {
    switch ( a6 )
    {
      case 1u:
        v11 = 4;
        break;
      case 2u:
        v11 = 3;
        break;
      case 3u:
        v11 = 8;
        break;
      default:
        v10 = -2147024809;
        goto LABEL_16;
    }
  }
  else
  {
    v11 = 2;
  }
  v10 = TOKEN_KEY::CreateCacheKey(&v16, a4, (const BYTE *)a5, v11);
  if ( v10 >= 0 )
  {
    v10 = (*(__int64 (__fastcall **)(struct IHttpServer *, _QWORD, wchar_t **, struct IHttpTokenEntry **))(*(_QWORD *)a1 + 80LL))(
            a1,
            0,
            &v16,
            a7);
    if ( v10 < 0 || !*a7 )
    {
      (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)a1 + 24LL))(a1);
      v10 = IIS_LOGON_PROVIDER::IISLogonUser(a2, a4, a5, v11, 0, v15, a7);
      v12 = a1;
      v13 = *(_QWORD *)a1;
      if ( v10 >= 0 )
      {
        (*(void (__fastcall **)(struct IHttpServer *, __int64, wchar_t **, struct IHttpTokenEntry **, _QWORD))(v13 + 80))(
          a1,
          1,
          &v16,
          a7,
          0);
        v13 = *(_QWORD *)a1;
        v12 = a1;
      }
      (*(void (__fastcall **)(struct IHttpServer *))(v13 + 32))(v12);
    }
  }
LABEL_16:
  STRU::~STRU((STRU *)v18);
  STRU::~STRU((STRU *)v17);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180019bc4  push    rbx
0x180019bc6  push    rbp
0x180019bc7  push    rsi
0x180019bc8  push    rdi
0x180019bc9  push    r12
0x180019bcb  push    r14
0x180019bcd  push    r15
0x180019bcf  sub     rsp, 0D0h
0x180019bd6  mov     rax, cs:__security_cookie
0x180019bdd  xor     rax, rsp
0x180019be0  mov     [rsp+108h+var_48], rax
0x180019be8  mov     r15, [rsp+108h+arg_20]
0x180019bf0  lea     rax, ??_7TOKEN_KEY@@6B@; const TOKEN_KEY::`vftable'
0x180019bf7  mov     r14, [rsp+108h+arg_30]
0x180019bff  mov     rsi, rcx
0x180019c02  lea     rcx, [rsp+108h+var_C0]
0x180019c07  mov     [rsp+108h+var_C8], rax
0x180019c0c  mov     rbp, r9
0x180019c0f  mov     r12, rdx
0x180019c12  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180019c18  lea     rcx, [rsp+108h+var_88]
0x180019c20  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180019c26  mov     eax, [rsp+108h+arg_28]
0x180019c2d  mov     qword ptr [r14], 0
0x180019c34  test    eax, eax
0x180019c36  jz      short loc_180019C66
0x180019c38  sub     eax, 1
0x180019c3b  jz      short loc_180019C5F
0x180019c3d  sub     eax, 1
0x180019c40  jz      short loc_180019C58
0x180019c42  cmp     eax, 1
0x180019c45  jz      short loc_180019C51
0x180019c47  mov     ebx, 80070057h
0x180019c4c  jmp     loc_180019D15
0x180019c51  mov     edi, 8
0x180019c56  jmp     short loc_180019C6B
0x180019c58  mov     edi, 3
0x180019c5d  jmp     short loc_180019C6B
0x180019c5f  mov     edi, 4
0x180019c64  jmp     short loc_180019C6B
0x180019c66  mov     edi, 2
0x180019c6b  mov     r9d, edi; unsigned int
0x180019c6e  lea     rcx, [rsp+108h+var_C8]; this
0x180019c73  mov     r8, r15; unsigned __int16 *
0x180019c76  mov     rdx, rbp; unsigned __int16 *
0x180019c79  call    ?CreateCacheKey@TOKEN_KEY@@QEAAJPEBG0K@Z; TOKEN_KEY::CreateCacheKey(ushort const *,ushort const *,ulong)
0x180019c7e  mov     ebx, eax
0x180019c80  test    eax, eax
0x180019c82  js      loc_180019D15
0x180019c88  mov     rax, [rsi]
0x180019c8b  lea     r8, [rsp+108h+var_C8]
0x180019c90  mov     r9, r14
0x180019c93  mov     [rsp+108h+var_E8], 0; unsigned __int16 *
0x180019c9c  xor     edx, edx
0x180019c9e  mov     rcx, rsi
0x180019ca1  mov     rax, [rax+50h]
0x180019ca5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019caa  mov     ebx, eax
0x180019cac  test    eax, eax
0x180019cae  js      short loc_180019CB6
0x180019cb0  cmp     qword ptr [r14], 0
0x180019cb4  jnz     short loc_180019D15
0x180019cb6  mov     rax, [rsi]
0x180019cb9  mov     rcx, rsi
0x180019cbc  mov     rax, [rax+18h]
0x180019cc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019cc5  mov     r9d, edi; unsigned int
0x180019cc8  mov     [rsp+108h+var_D8], r14; struct IHttpTokenEntry **
0x180019ccd  mov     r8, r15; unsigned __int16 *
0x180019cd0  mov     rdx, rbp; unsigned __int16 *
0x180019cd3  mov     rcx, r12; this
0x180019cd6  call    ?IISLogonUser@IIS_LOGON_PROVIDER@@QEAAJPEBG0K0PEAUsockaddr@@PEAPEAVIHttpTokenEntry@@@Z; IIS_LOGON_PROVIDER::IISLogonUser(ushort const *,ushort const *,ulong,ushort const *,sockaddr *,IHttpTokenEntry * *)
0x180019cdb  mov     ebx, eax
0x180019cdd  mov     rcx, rsi
0x180019ce0  mov     rax, [rsi]
0x180019ce3  test    ebx, ebx
0x180019ce5  js      short loc_180019D0C
0x180019ce7  mov     rax, [rax+50h]
0x180019ceb  lea     r8, [rsp+108h+var_C8]
0x180019cf0  mov     r9, r14
0x180019cf3  mov     [rsp+108h+var_E8], 0
0x180019cfc  mov     edx, 1
0x180019d01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d06  mov     rax, [rsi]
0x180019d09  mov     rcx, rsi
0x180019d0c  mov     rax, [rax+20h]
0x180019d10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d15  lea     rcx, [rsp+108h+var_88]
0x180019d1d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180019d23  lea     rcx, [rsp+108h+var_C0]
0x180019d28  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180019d2e  mov     eax, ebx
0x180019d30  mov     rcx, [rsp+108h+var_48]
0x180019d38  xor     rcx, rsp; StackCookie
0x180019d3b  call    __security_check_cookie
0x180019d40  add     rsp, 0D0h
0x180019d47  pop     r15
0x180019d49  pop     r14
0x180019d4b  pop     r12
0x180019d4d  pop     rdi
0x180019d4e  pop     rsi
0x180019d4f  pop     rbp
0x180019d50  pop     rbx
0x180019d51  retn
```
