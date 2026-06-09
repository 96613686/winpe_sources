# CSusSecurityChecker::~CSusSecurityChecker(void)

- ea: `0x180080de8`
- end: `0x180080eec`
- name: `??1CSusSecurityChecker@@QEAA@XZ`
- size: `260`
- prototype: `void __fastcall(CSusSecurityChecker *__hidden this)`
- caller_count: `9`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001bb8`
- `0x180002ec0`
- `0x18004124c`
- `0x18005c0fc`
- `0x18005c298`
- `0x18005c438`
- `0x180081bdc`
- `0x18008d284`
- `0x1800a2154`

## callees

- `0x180080de8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180080dfe`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180080e15`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180080e2c`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180080e43`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180080e5a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180080e71`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180080e88`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180080e9f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180080eb6`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180080dfe`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180080e15`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180080e2c`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180080e43`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180080e5a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180080e71`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180080e88`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180080e9f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180080eb6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180080eca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180080eca`

## pseudocode

```c
void __fastcall CSusSecurityChecker::~CSusSecurityChecker(CSusSecurityChecker *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  __int64 i; // rdi

  v2 = (void *)*((_QWORD *)this + 8);
  if ( v2 )
    FreeSid(v2);
  *((_QWORD *)this + 8) = 0;
  v3 = (void *)*((_QWORD *)this + 9);
  if ( v3 )
    FreeSid(v3);
  *((_QWORD *)this + 9) = 0;
  v4 = (void *)*((_QWORD *)this + 10);
  if ( v4 )
    FreeSid(v4);
  *((_QWORD *)this + 10) = 0;
  v5 = (void *)*((_QWORD *)this + 6);
  if ( v5 )
    FreeSid(v5);
  *((_QWORD *)this + 6) = 0;
  v6 = (void *)*((_QWORD *)this + 7);
  if ( v6 )
    FreeSid(v6);
  *((_QWORD *)this + 7) = 0;
  v7 = (void *)*((_QWORD *)this + 11);
  if ( v7 )
    FreeSid(v7);
  *((_QWORD *)this + 11) = 0;
  v8 = (void *)*((_QWORD *)this + 5);
  if ( v8 )
    FreeSid(v8);
  *((_QWORD *)this + 5) = 0;
  v9 = (void *)*((_QWORD *)this + 12);
  if ( v9 )
    FreeSid(v9);
  *((_QWORD *)this + 12) = 0;
  v10 = (void *)*((_QWORD *)this + 13);
  if ( v10 )
    FreeSid(v10);
  *((_QWORD *)this + 13) = 0;
  for ( i = 0; i < 5; ++i )
  {
    LocalFree(*((HLOCAL *)this + i));
    *((_QWORD *)this + i) = 0;
  }
}

```

## disassembly

```asm
0x180080de8  mov     [rsp+arg_0], rbx
0x180080ded  push    rdi
0x180080dee  sub     rsp, 20h
0x180080df2  mov     rbx, rcx
0x180080df5  mov     rcx, [rcx+40h]; pSid
0x180080df9  test    rcx, rcx
0x180080dfc  jz      short loc_180080E04
0x180080dfe  call    cs:__imp_FreeSid
0x180080e04  mov     qword ptr [rbx+40h], 0
0x180080e0c  mov     rcx, [rbx+48h]; pSid
0x180080e10  test    rcx, rcx
0x180080e13  jz      short loc_180080E1B
0x180080e15  call    cs:__imp_FreeSid
0x180080e1b  mov     qword ptr [rbx+48h], 0
0x180080e23  mov     rcx, [rbx+50h]; pSid
0x180080e27  test    rcx, rcx
0x180080e2a  jz      short loc_180080E32
0x180080e2c  call    cs:__imp_FreeSid
0x180080e32  mov     qword ptr [rbx+50h], 0
0x180080e3a  mov     rcx, [rbx+30h]; pSid
0x180080e3e  test    rcx, rcx
0x180080e41  jz      short loc_180080E49
0x180080e43  call    cs:__imp_FreeSid
0x180080e49  mov     qword ptr [rbx+30h], 0
0x180080e51  mov     rcx, [rbx+38h]; pSid
0x180080e55  test    rcx, rcx
0x180080e58  jz      short loc_180080E60
0x180080e5a  call    cs:__imp_FreeSid
0x180080e60  mov     qword ptr [rbx+38h], 0
0x180080e68  mov     rcx, [rbx+58h]; pSid
0x180080e6c  test    rcx, rcx
0x180080e6f  jz      short loc_180080E77
0x180080e71  call    cs:__imp_FreeSid
0x180080e77  mov     qword ptr [rbx+58h], 0
0x180080e7f  mov     rcx, [rbx+28h]; pSid
0x180080e83  test    rcx, rcx
0x180080e86  jz      short loc_180080E8E
0x180080e88  call    cs:__imp_FreeSid
0x180080e8e  mov     qword ptr [rbx+28h], 0
0x180080e96  mov     rcx, [rbx+60h]; pSid
0x180080e9a  test    rcx, rcx
0x180080e9d  jz      short loc_180080EA5
0x180080e9f  call    cs:__imp_FreeSid
0x180080ea5  mov     qword ptr [rbx+60h], 0
0x180080ead  mov     rcx, [rbx+68h]; pSid
0x180080eb1  test    rcx, rcx
0x180080eb4  jz      short loc_180080EBC
0x180080eb6  call    cs:__imp_FreeSid
0x180080ebc  mov     qword ptr [rbx+68h], 0
0x180080ec4  xor     edi, edi
0x180080ec6  mov     rcx, [rbx+rdi*8]; hMem
0x180080eca  call    cs:__imp_LocalFree
0x180080ed0  mov     qword ptr [rbx+rdi*8], 0
0x180080ed8  inc     rdi
0x180080edb  cmp     rdi, 5
0x180080edf  jl      short loc_180080EC6
0x180080ee1  mov     rbx, [rsp+28h+arg_0]
0x180080ee6  add     rsp, 20h
0x180080eea  pop     rdi
0x180080eeb  retn
```
