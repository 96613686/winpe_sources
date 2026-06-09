# GetAssertionId(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)

- ea: `0x180057e94`
- end: `0x180057f37`
- name: `?GetAssertionId@@YAJAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z`
- size: `163`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18005733c`

## callees

- `0x180002da0`
- `0x18000ed94`
- `0x180012da8`
- `0x18005721c`
- `0x180057e94`

## import_xrefs

- `RPCRT4!UuidToStringA` at `0x180057ee5`
- `RPCRT4!UuidToStringA` at `0x180057ee5`
- `RPCRT4!UuidCreate` at `0x180057ed1`
- `RPCRT4!UuidCreate` at `0x180057ed1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetAssertionId(__int64 a1)
{
  __int64 v2; // r8
  unsigned int v3; // ebx
  void **v5; // [rsp+20h] [rbp-38h] BYREF
  RPC_CSTR StringUuid; // [rsp+28h] [rbp-30h] BYREF
  UUID Uuid; // [rsp+30h] [rbp-28h] BYREF

  Uuid = 0;
  StringUuid = 0;
  v5 = &SmartRPC_CSTR::`vftable';
  ATL::CSimpleStringT<char,0>::Truncate(a1);
  if ( UuidCreate(&Uuid) || UuidToStringA(&Uuid, &StringUuid) || !StringUuid )
  {
    v3 = -2147188735;
  }
  else
  {
    v2 = -1;
    do
      ++v2;
    while ( StringUuid[v2] );
    ATL::CSimpleStringT<char,0>::SetString(a1, StringUuid, v2);
    v3 = 0;
  }
  SmartRPC_CSTR::~SmartRPC_CSTR((SmartRPC_CSTR *)&v5);
  return v3;
}

```

## disassembly

```asm
0x180057e94  push    rbx
0x180057e96  sub     rsp, 50h
0x180057e9a  mov     rax, cs:__security_cookie
0x180057ea1  xor     rax, rsp
0x180057ea4  mov     [rsp+58h+var_18], rax
0x180057ea9  mov     rbx, rcx
0x180057eac  xorps   xmm0, xmm0
0x180057eaf  movups  xmmword ptr [rsp+58h+Uuid.Data1], xmm0
0x180057eb4  xor     eax, eax
0x180057eb6  mov     [rsp+58h+StringUuid], rax
0x180057ebb  lea     rax, ??_7SmartRPC_CSTR@@6B@; const SmartRPC_CSTR::`vftable'
0x180057ec2  mov     [rsp+58h+var_38], rax
0x180057ec7  call    ?Truncate@?$CSimpleStringT@D$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<char,0>::Truncate(int)
0x180057ecc  lea     rcx, [rsp+58h+Uuid]; Uuid
0x180057ed1  call    cs:__imp_UuidCreate
0x180057ed7  test    eax, eax
0x180057ed9  jnz     short loc_180057F13
0x180057edb  lea     rdx, [rsp+58h+StringUuid]; StringUuid
0x180057ee0  lea     rcx, [rsp+58h+Uuid]; Uuid
0x180057ee5  call    cs:__imp_UuidToStringA
0x180057eeb  test    eax, eax
0x180057eed  jnz     short loc_180057F13
0x180057eef  mov     rdx, [rsp+58h+StringUuid]
0x180057ef4  test    rdx, rdx
0x180057ef7  jz      short loc_180057F13
0x180057ef9  or      r8, 0FFFFFFFFFFFFFFFFh
0x180057efd  inc     r8
0x180057f00  cmp     byte ptr [rdx+r8], 0
0x180057f05  jnz     short loc_180057EFD
0x180057f07  mov     rcx, rbx
0x180057f0a  call    ?SetString@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBDH@Z; ATL::CSimpleStringT<char,0>::SetString(char const *,int)
0x180057f0f  xor     ebx, ebx
0x180057f11  jmp     short loc_180057F18
0x180057f13  mov     ebx, 80048001h
0x180057f18  lea     rcx, [rsp+58h+var_38]; this
0x180057f1d  call    ??1SmartRPC_CSTR@@UEAA@XZ; SmartRPC_CSTR::~SmartRPC_CSTR(void)
0x180057f22  mov     eax, ebx
0x180057f24  mov     rcx, [rsp+58h+var_18]
0x180057f29  xor     rcx, rsp; StackCookie
0x180057f2c  call    __security_check_cookie
0x180057f31  add     rsp, 50h
0x180057f35  pop     rbx
0x180057f36  retn
```
