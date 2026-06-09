# GetRandomNumber(void)

- ea: `0x180028b10`
- end: `0x180028b9c`
- name: `?GetRandomNumber@@YAKXZ`
- size: `140`
- prototype: `unsigned int(void)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180021fd0`
- `0x18002ea40`

## callees

- `0x180028b10`
- `0x180030390`

## import_xrefs

- `msvcrt!srand` at `0x180028b71`
- `msvcrt!srand` at `0x180028b71`
- `msvcrt!rand` at `0x180028b7d`
- `msvcrt!rand` at `0x180028b7d`
- `KERNEL32!GetTickCount` at `0x180028b63`
- `KERNEL32!GetTickCount` at `0x180028b63`
- `RPCRT4!UuidCreate` at `0x180028b30`
- `RPCRT4!UuidCreate` at `0x180028b30`

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
0x180028b10  sub     rsp, 48h
0x180028b14  mov     rax, cs:__security_cookie
0x180028b1b  xor     rax, rsp
0x180028b1e  mov     [rsp+48h+var_18], rax
0x180028b23  xorps   xmm0, xmm0
0x180028b26  lea     rcx, [rsp+48h+Uuid]; Uuid
0x180028b2b  movups  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x180028b30  call    cs:__imp_UuidCreate
0x180028b37  nop     dword ptr [rax+rax+00h]
0x180028b3c  test    eax, eax
0x180028b3e  jnz     short loc_180028B63
0x180028b40  movdqu  xmm0, xmmword ptr [rsp+48h+Uuid.Data1]
0x180028b46  movaps  xmm1, xmm0
0x180028b49  psrldq  xmm0, 8
0x180028b4e  xorps   xmm1, xmm0
0x180028b51  movdqa  xmm0, xmm1
0x180028b55  psrldq  xmm0, 4
0x180028b5a  xorps   xmm1, xmm0
0x180028b5d  movd    eax, xmm1
0x180028b61  jmp     short loc_180028B89
0x180028b63  call    cs:__imp_GetTickCount
0x180028b6a  nop     dword ptr [rax+rax+00h]
0x180028b6f  mov     ecx, eax; Seed
0x180028b71  call    cs:__imp_srand
0x180028b78  nop     dword ptr [rax+rax+00h]
0x180028b7d  call    cs:__imp_rand
0x180028b84  nop     dword ptr [rax+rax+00h]
0x180028b89  mov     rcx, [rsp+48h+var_18]
0x180028b8e  xor     rcx, rsp; StackCookie
0x180028b91  call    __security_check_cookie
0x180028b96  add     rsp, 48h
0x180028b9a  retn
```
