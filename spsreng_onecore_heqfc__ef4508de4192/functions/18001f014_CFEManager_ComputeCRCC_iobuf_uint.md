# CFEManager::ComputeCRCC(_iobuf *,uint *)

- ea: `0x18001f014`
- end: `0x18001f18e`
- name: `?ComputeCRCC@CFEManager@@AEAAJPEAU_iobuf@@PEAI@Z`
- size: `378`
- prototype: `__int64 __fastcall(CFEManager *__hidden this, struct _iobuf *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180021188`

## callees

- `0x1800034b0`
- `0x18001f014`
- `0x1800ff490`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_ferror` at `0x18001f0ab`
- `api-ms-win-crt-private-l1-1-0!_o_ferror` at `0x18001f106`
- `api-ms-win-crt-private-l1-1-0!_o_ferror` at `0x18001f13b`
- `api-ms-win-crt-private-l1-1-0!_o_ferror` at `0x18001f0ab`
- `api-ms-win-crt-private-l1-1-0!_o_ferror` at `0x18001f106`
- `api-ms-win-crt-private-l1-1-0!_o_ferror` at `0x18001f13b`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18001f08a`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18001f0f8`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18001f08a`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18001f0f8`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x18001f05f`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x18001f14e`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x18001f05f`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x18001f14e`
- `api-ms-win-crt-private-l1-1-0!_o_ftell` at `0x18001f04c`
- `api-ms-win-crt-private-l1-1-0!_o_ftell` at `0x18001f04c`

## pseudocode

```c
int __fastcall CFEManager::ComputeCRCC(CFEManager *this, struct _iobuf *a2, unsigned int *a3)
{
  int v5; // r13d
  unsigned __int64 v6; // rbx
  bool v7; // si
  size_t v8; // r15
  __int64 i; // r14
  int result; // eax
  _DWORD Buffer[2048]; // [rsp+20h] [rbp-2048h] BYREF

  v5 = _o_ftell(a2);
  if ( fseek(a2, 32, 0) )
    return -2147418113;
  v6 = 0;
  v7 = 0;
  while ( !v7 )
  {
    v8 = fread(Buffer, 4u, 0x800u, a2);
    v7 = v8 < 0x800;
    for ( i = 0; (unsigned int)i < v8; i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)_o_ferror(a2) )
        return -2147418113;
      v6 = ((unsigned int)Buffer[i] + (v6 << 32)) % 0xFFFFFFFB;
    }
  }
  Buffer[0] = 0;
  if ( fread(Buffer, 1u, 4u, a2) )
  {
    if ( (unsigned int)_o_ferror(a2) )
      return -2147418113;
    v6 = (Buffer[0] + (v6 << 32)) % 0xFFFFFFFB;
  }
  if ( !(unsigned int)_o_ferror(a2) )
  {
    result = fseek(a2, v5, 0);
    if ( !result )
    {
      *a3 = v6;
      return result;
    }
  }
  return -2147418113;
}

```

## disassembly

```asm
0x18001f014  mov     [rsp+arg_0], rbx
0x18001f019  push    rbp
0x18001f01a  push    rsi
0x18001f01b  push    rdi
0x18001f01c  push    r12
0x18001f01e  push    r13
0x18001f020  push    r14
0x18001f022  push    r15
0x18001f024  mov     eax, 2030h
0x18001f029  call    _alloca_probe
0x18001f02e  sub     rsp, rax
0x18001f031  mov     rax, cs:__security_cookie
0x18001f038  xor     rax, rsp
0x18001f03b  mov     [rsp+2068h+var_48], rax
0x18001f043  mov     rcx, rdx
0x18001f046  mov     r12, r8
0x18001f049  mov     rdi, rdx
0x18001f04c  call    cs:__imp__o_ftell
0x18001f052  xor     r8d, r8d; Origin
0x18001f055  mov     rcx, rdi; Stream
0x18001f058  mov     r13d, eax
0x18001f05b  lea     edx, [r8+20h]; Offset
0x18001f05f  call    cs:__imp_fseek
0x18001f065  test    eax, eax
0x18001f067  jnz     loc_18001F15E
0x18001f06d  xor     ebx, ebx
0x18001f06f  xor     sil, sil
0x18001f072  lea     rcx, [rsp+2068h+Buffer]; Buffer
0x18001f077  mov     r9, rdi; Stream
0x18001f07a  test    sil, sil
0x18001f07d  jnz     short loc_18001F0E7
0x18001f07f  mov     edx, 4; ElementSize
0x18001f084  mov     r8d, 800h; ElementCount
0x18001f08a  call    cs:__imp_fread
0x18001f090  cmp     rax, 800h
0x18001f096  mov     r15, rax
0x18001f099  setb    sil
0x18001f09d  xor     r14d, r14d
0x18001f0a0  mov     ebp, r14d
0x18001f0a3  cmp     rbp, r15
0x18001f0a6  jnb     short loc_18001F072
0x18001f0a8  mov     rcx, rdi
0x18001f0ab  call    cs:__imp__o_ferror
0x18001f0b1  test    eax, eax
0x18001f0b3  jnz     loc_18001F15E
0x18001f0b9  mov     eax, [rsp+r14*4+2068h+Buffer]
0x18001f0be  shl     rbx, 20h
0x18001f0c2  add     rbx, rax
0x18001f0c5  mov     rax, 800000028000000Dh
0x18001f0cf  mul     rbx
0x18001f0d2  mov     eax, 0FFFFFFFBh
0x18001f0d7  shr     rdx, 1Fh
0x18001f0db  imul    rdx, rax
0x18001f0df  sub     rbx, rdx
0x18001f0e2  inc     r14d
0x18001f0e5  jmp     short loc_18001F0A0
0x18001f0e7  mov     edx, 1; ElementSize
0x18001f0ec  mov     [rsp+2068h+Buffer], 0
0x18001f0f4  lea     r8d, [rdx+3]; ElementCount
0x18001f0f8  call    cs:__imp_fread
0x18001f0fe  test    rax, rax
0x18001f101  jz      short loc_18001F138
0x18001f103  mov     rcx, rdi
0x18001f106  call    cs:__imp__o_ferror
0x18001f10c  test    eax, eax
0x18001f10e  jnz     short loc_18001F15E
0x18001f110  mov     ecx, [rsp+2068h+Buffer]
0x18001f114  mov     rax, 800000028000000Dh
0x18001f11e  shl     rbx, 20h
0x18001f122  add     rbx, rcx
0x18001f125  mul     rbx
0x18001f128  mov     eax, 0FFFFFFFBh
0x18001f12d  shr     rdx, 1Fh
0x18001f131  imul    rdx, rax
0x18001f135  sub     rbx, rdx
0x18001f138  mov     rcx, rdi
0x18001f13b  call    cs:__imp__o_ferror
0x18001f141  test    eax, eax
0x18001f143  jnz     short loc_18001F15E
0x18001f145  xor     r8d, r8d; Origin
0x18001f148  mov     edx, r13d; Offset
0x18001f14b  mov     rcx, rdi; Stream
0x18001f14e  call    cs:__imp_fseek
0x18001f154  test    eax, eax
0x18001f156  jnz     short loc_18001F15E
0x18001f158  mov     [r12], ebx
0x18001f15c  jmp     short loc_18001F163
0x18001f15e  mov     eax, 8000FFFFh
0x18001f163  mov     rcx, [rsp+2068h+var_48]
0x18001f16b  xor     rcx, rsp; StackCookie
0x18001f16e  call    __security_check_cookie
0x18001f173  mov     rbx, [rsp+2068h+arg_0]
0x18001f17b  add     rsp, 2030h
0x18001f182  pop     r15
0x18001f184  pop     r14
0x18001f186  pop     r13
0x18001f188  pop     r12
0x18001f18a  pop     rdi
0x18001f18b  pop     rsi
0x18001f18c  pop     rbp
0x18001f18d  retn
```
