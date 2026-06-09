# SIPolicyVerifySignedData

- ea: `0x18002151c`
- end: `0x180021655`
- name: `SIPolicyVerifySignedData`
- size: `313`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d098`
- `0x18001dc98`
- `0x18004f184`

## callees

- `0x180015624`
- `0x1800187d4`
- `0x180019410`
- `0x18002151c`
- `0x180033980`
- `0x18004dd2c`

## import_xrefs

- `securekernel!RtlCompareMemory` at `0x1800215b6`
- `securekernel!RtlCompareMemory` at `0x1800215b6`

## pseudocode

```c
__int64 __fastcall SIPolicyVerifySignedData(
        __int64 a1,
        unsigned int a2,
        const void *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  int v9; // ebx
  int v11[4]; // [rsp+50h] [rbp-89h] BYREF
  __int128 v12; // [rsp+60h] [rbp-79h]
  __int128 v13; // [rsp+70h] [rbp-69h]
  char v14[8]; // [rsp+80h] [rbp-59h] BYREF
  void *Source2; // [rsp+88h] [rbp-51h]
  unsigned int v16; // [rsp+90h] [rbp-49h]
  __int64 v17; // [rsp+98h] [rbp-41h]

  *(_OWORD *)v11 = 0;
  v12 = 0;
  v13 = 0;
  v9 = MinCrypK_VerifySignedDataKModeEx(a1, a2, 0, 0, a5, (__int64)v11, v14, 0, 0);
  if ( v9 >= 0 )
  {
    if ( *(_DWORD *)v14 == 9
      && RtlCompareMemory(a3, Source2, 9u) == 9
      && (int)MinAsn1ExtractContent(v17, v16, a7, a6) >= 0
      && (!a5 || (*(_DWORD *)(a5 + 4) & 0x20) == 0 || (v11[2] & 0x4000) != 0)
      && v11[0]
      && (_QWORD)v12
      && (v11[2] & 0xFFFF0000) == 0 )
    {
      if ( a8 )
        v9 = SIPolicyConvertChainInfo(v12, a8);
    }
    else
    {
      v9 = -1073740760;
    }
  }
  if ( v11[0] )
    SIPolicyFree(v12);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002151c  push    rbp
0x18002151e  push    rbx
0x18002151f  push    rsi
0x180021520  push    rdi
0x180021521  push    r12
0x180021523  push    r14
0x180021525  push    r15
0x180021527  lea     rbp, [rsp-7]
0x18002152c  sub     rsp, 0E0h
0x180021533  mov     rax, cs:__security_cookie
0x18002153a  xor     rax, rsp
0x18002153d  mov     [rbp+37h+var_40], rax
0x180021541  mov     rdi, [rbp+37h+arg_20]
0x180021545  lea     rax, [rbp+37h+var_90]
0x180021549  mov     r15, [rbp+37h+arg_28]
0x18002154d  xorps   xmm0, xmm0
0x180021550  mov     r12, [rbp+37h+arg_30]
0x180021554  mov     r14, r8
0x180021557  mov     rsi, [rbp+37h+arg_38]
0x18002155b  xor     r9d, r9d; int
0x18002155e  mov     [rsp+110h+var_D0], 0; __int64
0x180021567  xor     r8d, r8d; int
0x18002156a  mov     [rsp+110h+var_D8], 0; __int64
0x180021573  mov     [rsp+110h+var_E0], rax; void *
0x180021578  lea     rax, [rsp+110h+var_C0]
0x18002157d  mov     qword ptr [rsp+110h+var_E8], rax; int
0x180021582  mov     [rsp+110h+var_F0], rdi; __int64
0x180021587  movups  xmmword ptr [rsp+110h+var_C0], xmm0
0x18002158c  movups  [rbp+37h+var_B0], xmm0
0x180021590  movups  [rbp+37h+var_A0], xmm0
0x180021594  call    MinCrypK_VerifySignedDataKModeEx
0x180021599  mov     ebx, eax
0x18002159b  test    eax, eax
0x18002159d  js      loc_180021624
0x1800215a3  cmp     dword ptr [rbp+37h+var_90], 9
0x1800215a7  jnz     short loc_18002161F
0x1800215a9  mov     rdx, [rbp+37h+Source2]; Source2
0x1800215ad  mov     r8d, 9; Length
0x1800215b3  mov     rcx, r14; Source1
0x1800215b6  call    cs:__imp_RtlCompareMemory
0x1800215bd  nop     dword ptr [rax+rax+00h]
0x1800215c2  cmp     rax, 9
0x1800215c6  jnz     short loc_18002161F
0x1800215c8  mov     edx, [rbp+37h+var_80]
0x1800215cb  mov     r9, r15
0x1800215ce  mov     rcx, [rbp+37h+var_78]
0x1800215d2  mov     r8, r12
0x1800215d5  call    MinAsn1ExtractContent
0x1800215da  test    eax, eax
0x1800215dc  js      short loc_18002161F
0x1800215de  test    rdi, rdi
0x1800215e1  jz      short loc_1800215F4
0x1800215e3  mov     eax, [rdi+4]
0x1800215e6  test    al, 20h
0x1800215e8  jz      short loc_1800215F4
0x1800215ea  test    [rsp+110h+var_C0+8], 4000h
0x1800215f2  jz      short loc_18002161F
0x1800215f4  cmp     [rsp+110h+var_C0], 0
0x1800215f9  jz      short loc_18002161F
0x1800215fb  mov     rcx, qword ptr [rbp+37h+var_B0]
0x1800215ff  test    rcx, rcx
0x180021602  jz      short loc_18002161F
0x180021604  test    [rsp+110h+var_C0+8], 0FFFF0000h
0x18002160c  jnz     short loc_18002161F
0x18002160e  test    rsi, rsi
0x180021611  jz      short loc_180021624
0x180021613  mov     rdx, rsi
0x180021616  call    SIPolicyConvertChainInfo
0x18002161b  mov     ebx, eax
0x18002161d  jmp     short loc_180021624
0x18002161f  mov     ebx, 0C0000428h
0x180021624  cmp     [rsp+110h+var_C0], 0
0x180021629  jz      short loc_180021634
0x18002162b  mov     rcx, qword ptr [rbp+37h+var_B0]
0x18002162f  call    SIPolicyFree
0x180021634  mov     eax, ebx
0x180021636  mov     rcx, [rbp+37h+var_40]
0x18002163a  xor     rcx, rsp; StackCookie
0x18002163d  call    __security_check_cookie
0x180021642  add     rsp, 0E0h
0x180021649  pop     r15
0x18002164b  pop     r14
0x18002164d  pop     r12
0x18002164f  pop     rdi
0x180021650  pop     rsi
0x180021651  pop     rbx
0x180021652  pop     rbp
0x180021653  retn
```
