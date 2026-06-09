# KvpEncoder::CreateInstance(IKvpEncoder * *,ushort const *)

- ea: `0x18005024c`
- end: `0x180050310`
- name: `?CreateInstance@KvpEncoder@@SAJPEAPEAUIKvpEncoder@@PEBG@Z`
- size: `196`
- prototype: `static int(struct IKvpEncoder **, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180050850`

## callees

- `0x18000e5ac`
- `0x18005024c`
- `0x180050318`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005027b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800502aa`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800502d0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005027b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800502aa`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800502d0`

## string_xrefs

- `0x1800502e5`: `onecore\base\flighting\common\inc\KvpEncoder.h`
- `0x1800502c4`: `UriPadded`

## pseudocode

```c
__int64 __fastcall KvpEncoder::CreateInstance(struct IKvpEncoder **a1, const unsigned __int16 *a2)
{
  __int64 v4; // rdx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( CompareStringOrdinal(a2, -1, L"Json", -1, 1) == 2 )
  {
    v4 = 1;
    return KvpEncoder::CreateInstance(a1, v4);
  }
  if ( CompareStringOrdinal(a2, -1, L"Uri", -1, 1) == 2 )
  {
    v4 = 2;
    return KvpEncoder::CreateInstance(a1, v4);
  }
  if ( CompareStringOrdinal(a2, -1, L"UriPadded", -1, 1) == 2 )
  {
    v4 = 3;
    return KvpEncoder::CreateInstance(a1, v4);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x11F,
    (unsigned int)"onecore\\base\\flighting\\common\\inc\\KvpEncoder.h",
    (const char *)0x80070057LL,
    bIgnoreCase);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18005024c  mov     [rsp+arg_0], rbx
0x180050251  mov     [rsp+arg_8], rsi
0x180050256  push    rdi
0x180050257  sub     rsp, 30h
0x18005025b  mov     rdi, rdx
0x18005025e  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180050266  or      esi, 0FFFFFFFFh
0x180050269  lea     r8, aJson_0; "Json"
0x180050270  mov     rbx, rcx
0x180050273  mov     r9d, esi; cchCount2
0x180050276  mov     edx, esi; cchCount1
0x180050278  mov     rcx, rdi; lpString1
0x18005027b  call    cs:__imp_CompareStringOrdinal
0x180050281  cmp     eax, 2
0x180050284  jnz     short loc_180050293
0x180050286  lea     edx, [rsi+2]
0x180050289  mov     rcx, rbx
0x18005028c  call    ?CreateInstance@KvpEncoder@@SAJPEAPEAUIKvpEncoder@@W4KvpEncoderMethod@@@Z; KvpEncoder::CreateInstance(IKvpEncoder * *,KvpEncoderMethod)
0x180050291  jmp     short loc_180050300
0x180050293  mov     r9d, esi; cchCount2
0x180050296  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18005029e  lea     r8, aUri; "Uri"
0x1800502a5  mov     edx, esi; cchCount1
0x1800502a7  mov     rcx, rdi; lpString1
0x1800502aa  call    cs:__imp_CompareStringOrdinal
0x1800502b0  cmp     eax, 2
0x1800502b3  jnz     short loc_1800502B9
0x1800502b5  mov     edx, eax
0x1800502b7  jmp     short loc_180050289
0x1800502b9  mov     r9d, esi; cchCount2
0x1800502bc  mov     [rsp+38h+bIgnoreCase], 1; int
0x1800502c4  lea     r8, aUripadded; "UriPadded"
0x1800502cb  mov     edx, esi; cchCount1
0x1800502cd  mov     rcx, rdi; lpString1
0x1800502d0  call    cs:__imp_CompareStringOrdinal
0x1800502d6  cmp     eax, 2
0x1800502d9  jnz     short loc_1800502E0
0x1800502db  lea     edx, [rax+1]
0x1800502de  jmp     short loc_180050289
0x1800502e0  mov     rcx, [rsp+38h]; this
0x1800502e5  lea     r8, aOnecoreBaseFli_7; "onecore\\base\\flighting\\common\\inc\\"...
0x1800502ec  mov     ebx, 80070057h
0x1800502f1  mov     edx, 11Fh; void *
0x1800502f6  mov     r9d, ebx; char *
0x1800502f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800502fe  mov     eax, ebx
0x180050300  mov     rbx, [rsp+38h+arg_0]
0x180050305  mov     rsi, [rsp+38h+arg_8]
0x18005030a  add     rsp, 30h
0x18005030e  pop     rdi
0x18005030f  retn
```
