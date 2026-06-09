# TpmApiShaInit

- ea: `0x140034148`
- end: `0x140034202`
- name: `TpmApiShaInit`
- size: `186`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140034694`
- `0x14003487c`
- `0x140034ac8`

## callees

- `0x140033d74`
- `0x140034148`

## import_xrefs

- `cng!BCryptCloseAlgorithmProvider` at `0x1400341f4`
- `cng!BCryptCloseAlgorithmProvider` at `0x1400341f4`
- `cng!BCryptCreateHash` at `0x1400341b7`
- `cng!BCryptCreateHash` at `0x1400341b7`

## pseudocode

```c
__int64 __fastcall TpmApiShaInit(__int64 a1, unsigned __int16 *a2, void *a3)
{
  int v4; // ebx
  int v5; // eax
  NTSTATUS Hash; // eax
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+60h] [rbp+18h] BYREF

  hAlgorithm = a3;
  if ( !a2 )
    return (unsigned int)-2144796412;
  v4 = 0;
  hAlgorithm = 0;
  if ( ::hAlgorithm )
    goto LABEL_6;
  v5 = TpmApiOpenAlgorithmProvider(&hAlgorithm, a2);
  if ( v5 < 0 )
  {
    v4 = v5 | 0x10000000;
    goto LABEL_6;
  }
  if ( !_InterlockedCompareExchange64((volatile signed __int64 *)&::hAlgorithm, (signed __int64)hAlgorithm, 0) )
  {
LABEL_6:
    if ( v4 < 0 )
      return (unsigned int)v4;
    goto LABEL_7;
  }
  BCryptCloseAlgorithmProvider(hAlgorithm, 0);
LABEL_7:
  Hash = BCryptCreateHash(::hAlgorithm, (BCRYPT_HASH_HANDLE *)a2, 0, 0, 0, 0, 0);
  if ( Hash < 0 )
    return (unsigned int)(Hash | 0x10000000);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140034148  mov     [rsp+arg_8], rbx
0x14003414d  mov     [rsp+hAlgorithm], r8
0x140034152  push    rdi
0x140034153  sub     rsp, 40h
0x140034157  mov     rdi, rdx
0x14003415a  test    rdx, rdx
0x14003415d  jnz     short loc_140034166
0x14003415f  mov     ebx, 80290104h
0x140034164  jmp     short loc_1400341CD
0x140034166  xor     ebx, ebx
0x140034168  cmp     cs:hAlgorithm, rbx
0x14003416f  mov     [rsp+48h+hAlgorithm], rbx
0x140034174  jnz     short loc_14003418A
0x140034176  lea     rcx, [rsp+48h+hAlgorithm]; phAlgorithm
0x14003417b  call    ?TpmApiOpenAlgorithmProvider@@YAJPEAPEAXPEBG@Z; TpmApiOpenAlgorithmProvider(void * *,ushort const *)
0x140034180  test    eax, eax
0x140034182  jns     short loc_1400341DB
0x140034184  mov     ebx, eax
0x140034186  bts     ebx, 1Ch
0x14003418a  test    ebx, ebx
0x14003418c  js      short loc_1400341CD
0x14003418e  mov     rcx, cs:hAlgorithm; hAlgorithm
0x140034195  xor     r9d, r9d; cbHashObject
0x140034198  mov     [rsp+48h+dwFlags], 0; dwFlags
0x1400341a0  xor     r8d, r8d; pbHashObject
0x1400341a3  mov     [rsp+48h+cbSecret], 0; cbSecret
0x1400341ab  mov     rdx, rdi; phHash
0x1400341ae  mov     [rsp+48h+pbSecret], 0; pbSecret
0x1400341b7  call    cs:__imp_BCryptCreateHash
0x1400341be  nop     dword ptr [rax+rax+00h]
0x1400341c3  test    eax, eax
0x1400341c5  jns     short loc_1400341CD
0x1400341c7  mov     ebx, eax
0x1400341c9  bts     ebx, 1Ch
0x1400341cd  mov     eax, ebx
0x1400341cf  mov     rbx, [rsp+48h+arg_8]
0x1400341d4  add     rsp, 40h
0x1400341d8  pop     rdi
0x1400341d9  retn
0x1400341db  mov     rcx, [rsp+48h+hAlgorithm]
0x1400341e0  xor     eax, eax
0x1400341e2  lock cmpxchg cs:hAlgorithm, rcx
0x1400341eb  jz      short loc_14003418A
0x1400341ed  mov     rcx, [rsp+48h+hAlgorithm]; hAlgorithm
0x1400341f2  xor     edx, edx; dwFlags
0x1400341f4  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1400341fb  nop     dword ptr [rax+rax+00h]
0x140034200  jmp     short loc_14003418E
```
