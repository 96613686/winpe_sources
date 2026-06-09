# DAV_WEB_CONFIG_VALIDATOR::Validate(unsigned __int64)

- ea: `0x180011f30`
- end: `0x180011fe4`
- name: `?Validate@DAV_WEB_CONFIG_VALIDATOR@@UEAAJ_K@Z`
- size: `180`
- prototype: `__int64 __fastcall(struct IHttpContext **this, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180011aec`
- `0x180011cf8`
- `0x180011e14`
- `0x180011f30`
- `0x18001b2cc`
- `0x180023010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180011fcc`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180011fcc`

## pseudocode

```c
__int64 __fastcall DAV_WEB_CONFIG_VALIDATOR::Validate(struct IHttpContext **this, unsigned __int64 a2)
{
  int v4; // ebx
  int v6; // [rsp+20h] [rbp-18h] BYREF
  __int64 v7; // [rsp+28h] [rbp-10h]
  struct INativeSectionException *v8; // [rsp+48h] [rbp+10h] BYREF

  v6 = 0;
  v7 = 0;
  v8 = 0;
  if ( a2 && (v4 = DAV_WEB_CONFIG_VALIDATOR::TestNewWebConfig((DAV_WEB_CONFIG_VALIDATOR *)this, &v8), v4 < 0)
    || (v4 = AUTO_IMPERSONATE::Impersonate((AUTO_IMPERSONATE *)&v6, this[1]), v4 < 0)
    || (v4 = DAV_WEB_CONFIG_VALIDATOR::ReplaceWebConfig((DAV_WEB_CONFIG_VALIDATOR *)this, a2), v4 < 0) )
  {
    DAV_TRACE::TraceValidationError(this[1], v4, v8);
  }
  if ( v8 )
  {
    (*(void (__fastcall **)(struct INativeSectionException *))(*(_QWORD *)v8 + 16LL))(v8);
    v8 = 0;
  }
  if ( v6 )
    RevertToSelf();
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180011f30  mov     rax, rsp
0x180011f33  mov     [rax+8], rbx
0x180011f37  mov     [rax+18h], rsi
0x180011f3b  push    rdi
0x180011f3c  sub     rsp, 30h
0x180011f40  mov     dword ptr [rax-18h], 0
0x180011f47  mov     rsi, rdx
0x180011f4a  mov     qword ptr [rax-10h], 0
0x180011f52  mov     rdi, rcx
0x180011f55  mov     qword ptr [rax+10h], 0
0x180011f5d  test    rdx, rdx
0x180011f60  jz      short loc_180011F71
0x180011f62  lea     rdx, [rax+10h]; struct INativeSectionException **
0x180011f66  call    ?TestNewWebConfig@DAV_WEB_CONFIG_VALIDATOR@@AEAAJPEAPEAVINativeSectionException@@@Z; DAV_WEB_CONFIG_VALIDATOR::TestNewWebConfig(INativeSectionException * *)
0x180011f6b  mov     ebx, eax
0x180011f6d  test    eax, eax
0x180011f6f  js      short loc_180011F96
0x180011f71  mov     rdx, [rdi+8]; struct IHttpContext *
0x180011f75  lea     rcx, [rsp+38h+var_18]; this
0x180011f7a  call    ?Impersonate@AUTO_IMPERSONATE@@QEAAJPEAVIHttpContext@@@Z; AUTO_IMPERSONATE::Impersonate(IHttpContext *)
0x180011f7f  mov     ebx, eax
0x180011f81  test    eax, eax
0x180011f83  js      short loc_180011F96
0x180011f85  mov     rdx, rsi; unsigned __int64
0x180011f88  mov     rcx, rdi; this
0x180011f8b  call    ?ReplaceWebConfig@DAV_WEB_CONFIG_VALIDATOR@@AEAAJ_K@Z; DAV_WEB_CONFIG_VALIDATOR::ReplaceWebConfig(unsigned __int64)
0x180011f90  mov     ebx, eax
0x180011f92  test    eax, eax
0x180011f94  jns     short loc_180011FA6
0x180011f96  mov     r8, [rsp+38h+arg_8]; struct INativeSectionException *
0x180011f9b  mov     edx, ebx; int
0x180011f9d  mov     rcx, [rdi+8]; struct IHttpContext *
0x180011fa1  call    ?TraceValidationError@DAV_TRACE@@SAXPEAVIHttpContext@@JPEAVINativeSectionException@@@Z; DAV_TRACE::TraceValidationError(IHttpContext *,long,INativeSectionException *)
0x180011fa6  mov     rcx, [rsp+38h+arg_8]
0x180011fab  test    rcx, rcx
0x180011fae  jz      short loc_180011FC5
0x180011fb0  mov     rax, [rcx]
0x180011fb3  mov     rax, [rax+10h]
0x180011fb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011fbc  mov     [rsp+38h+arg_8], 0
0x180011fc5  cmp     [rsp+38h+var_18], 0
0x180011fca  jz      short loc_180011FD2
0x180011fcc  call    cs:__imp_RevertToSelf
0x180011fd2  mov     rsi, [rsp+38h+arg_10]
0x180011fd7  mov     eax, ebx
0x180011fd9  mov     rbx, [rsp+38h+arg_0]
0x180011fde  add     rsp, 30h
0x180011fe2  pop     rdi
0x180011fe3  retn
```
