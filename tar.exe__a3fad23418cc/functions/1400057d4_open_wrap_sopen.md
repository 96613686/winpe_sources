# _open_wrap_sopen

- ea: `0x1400057d4`
- end: `0x140005835`
- name: `_open_wrap_sopen`
- size: `97`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400063bc`
- `0x140006650`

## callees

- `0x1400057d4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__sopen_s` at `0x14000581e`
- `api-ms-win-crt-private-l1-1-0!_o__sopen_s` at `0x14000581e`

## pseudocode

```c
__int64 __fastcall open_wrap_sopen(__int64 a1, unsigned int a2, __int16 a3)
{
  __int16 v3; // ax
  __int64 result; // rax
  _QWORD v5[3]; // [rsp+30h] [rbp-18h] BYREF

  v5[0] = 0;
  v3 = 0;
  if ( (a2 & 0x100) != 0 )
    v3 = a3;
  _o__sopen_s(v5, a1, a2, 64, v3 & 0x180);
  result = LODWORD(v5[0]);
  if ( SLODWORD(v5[0]) < 0 )
    return 0xFFFFFFFFLL;
  return result;
}

```

## disassembly

```asm
0x1400057d4  mov     rax, rsp
0x1400057d7  mov     [rax+10h], edx
0x1400057da  mov     [rax+18h], r8
0x1400057de  mov     [rax+20h], r9
0x1400057e2  sub     rsp, 48h
0x1400057e6  mov     qword ptr [rax-18h], 0
0x1400057ee  mov     dword ptr [rax-18h], 0
0x1400057f5  xor     eax, eax
0x1400057f7  bt      edx, 8
0x1400057fb  jnb     short loc_140005804
0x1400057fd  lea     rax, [rsp+48h+arg_10]
0x140005802  mov     eax, [rax]
0x140005804  mov     r8d, edx
0x140005807  and     eax, 180h
0x14000580c  mov     rdx, rcx
0x14000580f  mov     [rsp+48h+var_28], eax
0x140005813  lea     rcx, [rsp+48h+var_18]
0x140005818  mov     r9d, 40h ; '@'
0x14000581e  call    cs:__imp__o__sopen_s
0x140005824  mov     eax, dword ptr [rsp+48h+var_18]
0x140005828  or      ecx, 0FFFFFFFFh
0x14000582b  test    eax, eax
0x14000582d  cmovs   eax, ecx
0x140005830  add     rsp, 48h
0x140005834  retn
```
