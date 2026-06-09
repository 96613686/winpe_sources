# GetRandomNumber(void)

- ea: `0x1800279c0`
- end: `0x180027a4c`
- name: `?GetRandomNumber@@YAKXZ`
- size: `140`
- prototype: `unsigned int(void)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180020f80`
- `0x18002d820`

## callees

- `0x1800279c0`
- `0x18002f3e0`

## import_xrefs

- `msvcrt!srand` at `0x180027a21`
- `msvcrt!srand` at `0x180027a21`
- `msvcrt!rand` at `0x180027a2d`
- `msvcrt!rand` at `0x180027a2d`
- `KERNEL32!GetTickCount` at `0x180027a13`
- `KERNEL32!GetTickCount` at `0x180027a13`
- `RPCRT4!UuidCreate` at `0x1800279e0`
- `RPCRT4!UuidCreate` at `0x1800279e0`

## pseudocode

```c
int GetRandomNumber(void)
{
  __m128 v0; // xmm1
  __m128 v1; // xmm1
  DWORD TickCount; // eax
  UUID Uuid; // [rsp+20h] [rbp-28h] BYREF

  Uuid = 0;
  if ( UuidCreate(&Uuid) )
  {
    TickCount = GetTickCount();
    srand(TickCount);
    return rand();
  }
  else
  {
    v0 = (__m128)_mm_loadu_si128((const __m128i *)&Uuid);
    v1 = _mm_xor_ps(v0, (__m128)_mm_srli_si128((__m128i)v0, 8));
    return _mm_cvtsi128_si32((__m128i)_mm_xor_ps(v1, (__m128)_mm_srli_si128((__m128i)v1, 4)));
  }
}

```

## disassembly

```asm
0x1800279c0  sub     rsp, 48h
0x1800279c4  mov     rax, cs:__security_cookie
0x1800279cb  xor     rax, rsp
0x1800279ce  mov     [rsp+48h+var_18], rax
0x1800279d3  xorps   xmm0, xmm0
0x1800279d6  lea     rcx, [rsp+48h+Uuid]; Uuid
0x1800279db  movups  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x1800279e0  call    cs:__imp_UuidCreate
0x1800279e7  nop     dword ptr [rax+rax+00h]
0x1800279ec  test    eax, eax
0x1800279ee  jnz     short loc_180027A13
0x1800279f0  movdqu  xmm0, xmmword ptr [rsp+48h+Uuid.Data1]
0x1800279f6  movaps  xmm1, xmm0
0x1800279f9  psrldq  xmm0, 8
0x1800279fe  xorps   xmm1, xmm0
0x180027a01  movdqa  xmm0, xmm1
0x180027a05  psrldq  xmm0, 4
0x180027a0a  xorps   xmm1, xmm0
0x180027a0d  movd    eax, xmm1
0x180027a11  jmp     short loc_180027A39
0x180027a13  call    cs:__imp_GetTickCount
0x180027a1a  nop     dword ptr [rax+rax+00h]
0x180027a1f  mov     ecx, eax; Seed
0x180027a21  call    cs:__imp_srand
0x180027a28  nop     dword ptr [rax+rax+00h]
0x180027a2d  call    cs:__imp_rand
0x180027a34  nop     dword ptr [rax+rax+00h]
0x180027a39  mov     rcx, [rsp+48h+var_18]
0x180027a3e  xor     rcx, rsp; StackCookie
0x180027a41  call    __security_check_cookie
0x180027a46  add     rsp, 48h
0x180027a4a  retn
```
