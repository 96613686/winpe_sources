# MTX_AGFACOMP_Pack_TTF_InMemory

- ea: `0x18000e12c`
- end: `0x18000e2cd`
- name: `MTX_AGFACOMP_Pack_TTF_InMemory`
- size: `417`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18000eb94`

## callees

- `0x180009c80`
- `0x18000db44`
- `0x18000e12c`
- `0x18000e2d4`
- `0x18000e580`
- `0x18000e5e4`
- `0x18000e640`
- `0x18001c574`
- `0x18001c9ec`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall MTX_AGFACOMP_Pack_TTF_InMemory(unsigned int *a1, __int64 a2, int a3, _DWORD *a4, _DWORD *a5)
{
  __int64 v9; // rbx
  __int64 i; // rsi
  __int64 *v11; // rbx
  __int64 result; // rax
  int v13; // [rsp+50h] [rbp-41h] BYREF
  int v14; // [rsp+58h] [rbp-39h] BYREF
  _BYTE v15[4]; // [rsp+5Ch] [rbp-35h] BYREF
  _BYTE v16[8]; // [rsp+60h] [rbp-31h] BYREF
  __int128 v17; // [rsp+68h] [rbp-29h] BYREF
  __int64 v18; // [rsp+78h] [rbp-19h] BYREF
  _DWORD v19[4]; // [rsp+80h] [rbp-11h] BYREF
  __int128 v20; // [rsp+90h] [rbp-1h] BYREF
  __int64 v21; // [rsp+A0h] [rbp+Fh]

  v13 = 0;
  v17 = 0;
  v18 = 0;
  v20 = 0;
  v21 = 0;
  a1[1] = a3;
  if ( !*a1 )
  {
    if ( a3 >= 1000000 )
      *a1 = 9000;
    else
      *a1 = a3 + 7232;
  }
  v9 = MTX_TTC_Create(*((_QWORD *)a1 + 8), 3);
  MTX_TTC_TTF_To_CTF(
    v9,
    a2,
    a3,
    (unsigned int)&v17,
    (__int64)&v14,
    (__int64)&v17 + 8,
    (__int64)v15,
    (__int64)&v18,
    (__int64)v16);
  DiscardPointer(*(_QWORD *)(v9 + 96), v9, 1);
  if ( *a4 )
  {
    if ( *a4 == 2 )
    {
      (*(void (__fastcall **)(__int64))(*((_QWORD *)a1 + 8) + 40LL))(a2);
    }
    else
    {
      if ( *a4 != 1 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      DiscardPointer(*((_QWORD *)a1 + 8), a2, 1);
    }
    *a4 = 0;
  }
  for ( i = 0; i != 3; ++i )
  {
    v11 = (__int64 *)MTX_LZCOMP_Create2(*((_QWORD *)a1 + 8), *a1);
    *((_QWORD *)&v20 + i) = MTX_LZCOMP_PackMemory(v11, *((_QWORD *)&v17 + i), *(_DWORD *)&v15[4 * i - 4], &v19[i]);
    MTX_LZCOMP_Destroy(v11);
    DiscardPointer(*((_QWORD *)a1 + 8), *((_QWORD *)&v17 + i), 1);
  }
  result = MergeMemory(a1, &v20, v19, &v13);
  *a5 = v13;
  return result;
}

```

## disassembly

```asm
0x18000e12c  push    rbp
0x18000e12e  push    rbx
0x18000e12f  push    rsi
0x18000e130  push    rdi
0x18000e131  push    r12
0x18000e133  push    r14
0x18000e135  push    r15
0x18000e137  lea     rbp, [rsp-1Fh]
0x18000e13c  sub     rsp, 0B0h
0x18000e143  mov     r12, [rbp+4Fh+arg_20]
0x18000e147  xor     eax, eax
0x18000e149  xorps   xmm0, xmm0
0x18000e14c  xorps   xmm1, xmm1
0x18000e14f  mov     r15, r9
0x18000e152  mov     esi, r8d
0x18000e155  mov     r14, rdx
0x18000e158  mov     rdi, rcx
0x18000e15b  mov     [rbp+4Fh+var_90], 0
0x18000e162  movups  [rbp+4Fh+var_78], xmm0
0x18000e166  mov     [rbp+4Fh+var_68], rax
0x18000e16a  movups  [rbp+4Fh+var_50], xmm1
0x18000e16e  mov     [rbp+4Fh+var_40], rax
0x18000e172  mov     [rcx+4], r8d
0x18000e176  cmp     [rcx], eax
0x18000e178  jz      loc_18000E26B
0x18000e17e  mov     rcx, [rcx+40h]
0x18000e182  mov     edx, 3
0x18000e187  call    MTX_TTC_Create
0x18000e18c  mov     rbx, rax
0x18000e18f  lea     r9, [rbp+4Fh+var_78]
0x18000e193  lea     rax, [rbp+4Fh+var_80]
0x18000e197  mov     r8d, esi
0x18000e19a  mov     [rsp+0E0h+var_A0], rax
0x18000e19f  mov     rdx, r14
0x18000e1a2  lea     rax, [rbp+4Fh+var_68]
0x18000e1a6  mov     rcx, rbx
0x18000e1a9  mov     [rsp+0E0h+var_A8], rax
0x18000e1ae  lea     rax, [rbp+4Fh+var_84]
0x18000e1b2  mov     [rsp+0E0h+var_B0], rax
0x18000e1b7  lea     rax, [rbp+4Fh+var_78+8]
0x18000e1bb  mov     [rsp+0E0h+var_B8], rax
0x18000e1c0  lea     rax, [rbp+4Fh+var_88]
0x18000e1c4  mov     [rsp+0E0h+var_C0], rax
0x18000e1c9  call    MTX_TTC_TTF_To_CTF
0x18000e1ce  mov     rcx, [rbx+60h]
0x18000e1d2  mov     r8d, 1
0x18000e1d8  mov     rdx, rbx
0x18000e1db  call    DiscardPointer
0x18000e1e0  cmp     dword ptr [r15], 0
0x18000e1e4  jnz     loc_18000E28C
0x18000e1ea  xor     esi, esi
0x18000e1ec  mov     edx, [rdi]
0x18000e1ee  mov     rcx, [rdi+40h]
0x18000e1f2  call    MTX_LZCOMP_Create2
0x18000e1f7  mov     r8d, [rbp+rsi*4+4Fh+var_88]
0x18000e1fc  lea     r9, [rbp+4Fh+var_60]
0x18000e200  mov     rdx, qword ptr [rbp+rsi*8+4Fh+var_78]
0x18000e205  lea     r9, [r9+rsi*4]
0x18000e209  mov     rcx, rax
0x18000e20c  mov     rbx, rax
0x18000e20f  call    MTX_LZCOMP_PackMemory
0x18000e214  mov     rcx, rbx
0x18000e217  mov     qword ptr [rbp+rsi*8+4Fh+var_50], rax
0x18000e21c  call    MTX_LZCOMP_Destroy
0x18000e221  mov     rdx, qword ptr [rbp+rsi*8+4Fh+var_78]
0x18000e226  mov     r8d, 1
0x18000e22c  mov     rcx, [rdi+40h]
0x18000e230  call    DiscardPointer
0x18000e235  inc     rsi
0x18000e238  cmp     rsi, 3
0x18000e23c  jnz     short loc_18000E1EC
0x18000e23e  lea     r9, [rbp+4Fh+var_90]
0x18000e242  mov     rcx, rdi
0x18000e245  lea     r8, [rbp+4Fh+var_60]
0x18000e249  lea     rdx, [rbp+4Fh+var_50]
0x18000e24d  call    MergeMemory
0x18000e252  mov     ecx, [rbp+4Fh+var_90]
0x18000e255  mov     [r12], ecx
0x18000e259  add     rsp, 0B0h
0x18000e260  pop     r15
0x18000e262  pop     r14
0x18000e264  pop     r12
0x18000e266  pop     rdi
0x18000e267  pop     rsi
0x18000e268  pop     rbx
0x18000e269  pop     rbp
0x18000e26a  retn
0x18000e26b  cmp     esi, 0F4240h
0x18000e271  jge     short loc_18000E281
0x18000e273  lea     eax, [r8+1C40h]
0x18000e27a  mov     [rcx], eax
0x18000e27c  jmp     loc_18000E17E
0x18000e281  mov     dword ptr [rcx], 2328h
0x18000e287  jmp     loc_18000E17E
0x18000e28c  cmp     dword ptr [r15], 2
0x18000e290  jnz     short loc_18000E2A4
0x18000e292  mov     rax, [rdi+40h]
0x18000e296  mov     rcx, r14
0x18000e299  mov     rax, [rax+28h]
0x18000e29d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2a2  jmp     short loc_18000E2C1
0x18000e2a4  cmp     dword ptr [r15], 1
0x18000e2a8  jz      short loc_18000E2AF
0x18000e2aa  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000e2af  mov     rcx, [rdi+40h]
0x18000e2b3  mov     r8d, 1
0x18000e2b9  mov     rdx, r14
0x18000e2bc  call    DiscardPointer
0x18000e2c1  mov     dword ptr [r15], 0
0x18000e2c8  jmp     loc_18000E1EA
```
