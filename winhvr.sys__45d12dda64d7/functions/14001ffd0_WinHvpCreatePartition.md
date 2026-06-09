# WinHvpCreatePartition

- ea: `0x14001ffd0`
- end: `0x140020128`
- name: `WinHvpCreatePartition`
- size: `344`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x14001f2d0`
- `0x140021a10`

## callees

- `0x140002240`
- `0x140003610`
- `0x140004408`
- `0x1400048b8`
- `0x140009c90`
- `0x14000a040`
- `0x14001ffd0`

## pseudocode

```c
__int64 __fastcall WinHvpCreatePartition(
        __int64 a1,
        unsigned int a2,
        int a3,
        __int64 a4,
        _QWORD *a5,
        char a6,
        _QWORD *a7)
{
  int v7; // edi
  __int64 v9; // r14
  _QWORD *v11; // r12
  unsigned int v12; // esi
  __int64 v13; // rbx
  char v14; // r9
  __int64 *v15; // rcx
  __int64 v16; // rax
  int v17; // edi
  __int64 v18; // r14
  __int64 *v20; // [rsp+20h] [rbp-50h] BYREF
  __int64 *v21; // [rsp+28h] [rbp-48h] BYREF
  _QWORD v22[8]; // [rsp+30h] [rbp-40h] BYREF
  __int64 v25; // [rsp+C8h] [rbp+58h] BYREF

  v7 = a3;
  v20 = 0;
  v9 = a1;
  v21 = 0;
  memset(v22, 0, sizeof(v22));
  v25 = 0;
  WinHvpSetProximityDomain(&v25, a2 | (a6 != 0 ? 0x80000000 : 0));
  v11 = a5;
  v12 = 0;
  v13 = v25;
  LOBYTE(v22[3]) = v14;
  while ( 1 )
  {
    WinHvpSetupHypercall(&v20, (__int64 *)&v21, (__int64)v22);
    v15 = v20;
    *v20 = v9;
    v15[1] = v13;
    *((_DWORD *)v15 + 4) = v7;
    if ( a4 )
    {
      *(_OWORD *)(v15 + 3) = *(_OWORD *)a4;
      v15[5] = *(_QWORD *)(a4 + 16);
    }
    else
    {
      *(_OWORD *)(v15 + 3) = 0;
      v15[5] = 0;
    }
    v16 = v11 ? *v11 : 0LL;
    v15[6] = v16;
    v17 = WinHvpSimplePoolHypercall_CallViaMacro(v22[0], 64);
    v18 = *v21;
    ((void (__fastcall *)(_QWORD))v22[7])(v22[0]);
    if ( v17 != -1070268299 && v17 != -1070268405 && (unsigned int)(v17 + 1070268287) > 1 )
      break;
    v17 = WinHvpCurrentPartitionLowMemoryHandler((unsigned int)v17, a2, 64, v12);
    if ( v17 < 0 )
      return (unsigned int)v17;
    v7 = a3;
    ++v12;
    v9 = a1;
  }
  if ( v17 >= 0 )
    *a7 = v18;
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x14001ffd0  mov     [rsp-38h+arg_8], rbx
0x14001ffd5  mov     [rsp-38h+arg_10], r8d
0x14001ffda  mov     [rsp-38h+arg_0], rcx
0x14001ffdf  push    rbp
0x14001ffe0  push    rsi
0x14001ffe1  push    rdi
0x14001ffe2  push    r12
0x14001ffe4  push    r13
0x14001ffe6  push    r14
0x14001ffe8  push    r15
0x14001ffea  mov     rbp, rsp
0x14001ffed  sub     rsp, 70h
0x14001fff1  xor     ebx, ebx
0x14001fff3  mov     edi, r8d
0x14001fff6  mov     r13d, edx
0x14001fff9  mov     [rbp+var_50], rbx
0x14001fffd  mov     r14, rcx
0x140020000  mov     [rbp+var_48], rbx
0x140020004  xor     edx, edx; Val
0x140020006  lea     rcx, [rbp+var_40]; void *
0x14002000a  lea     r8d, [rbx+40h]; Size
0x14002000e  mov     r15, r9
0x140020011  call    memset
0x140020016  mov     r9b, [rbp+arg_28]
0x14002001a  lea     rcx, [rbp+arg_18]
0x14002001e  mov     al, r9b
0x140020021  mov     [rbp+arg_18], rbx
0x140020025  neg     al
0x140020027  sbb     edx, edx
0x140020029  and     edx, 80000000h
0x14002002f  or      edx, r13d
0x140020032  call    WinHvpSetProximityDomain
0x140020037  mov     r12, [rbp+arg_20]
0x14002003b  mov     esi, ebx
0x14002003d  mov     rbx, [rbp+arg_18]
0x140020041  mov     [rbp+var_28], r9b
0x140020045  lea     r8, [rbp+var_40]
0x140020049  lea     rdx, [rbp+var_48]
0x14002004d  lea     rcx, [rbp+var_50]
0x140020051  call    WinHvpSetupHypercall
0x140020056  mov     rcx, [rbp+var_50]
0x14002005a  mov     [rcx], r14
0x14002005d  mov     [rcx+8], rbx
0x140020061  mov     [rcx+10h], edi
0x140020064  test    r15, r15
0x140020067  jz      short loc_14002007E
0x140020069  movups  xmm0, xmmword ptr [r15]
0x14002006d  movups  xmmword ptr [rcx+18h], xmm0
0x140020071  movsd   xmm1, qword ptr [r15+10h]
0x140020077  movsd   qword ptr [rcx+28h], xmm1
0x14002007c  jmp     short loc_14002008B
0x14002007e  xorps   xmm0, xmm0
0x140020081  xor     eax, eax
0x140020083  movups  xmmword ptr [rcx+18h], xmm0
0x140020087  mov     [rcx+28h], rax
0x14002008b  test    r12, r12
0x14002008e  jz      short loc_140020096
0x140020090  mov     rax, [r12]
0x140020094  jmp     short loc_140020098
0x140020096  xor     eax, eax
0x140020098  mov     [rcx+30h], rax
0x14002009c  mov     edx, 40h ; '@'
0x1400200a1  mov     rcx, [rbp+var_40]
0x1400200a5  call    WinHvpSimplePoolHypercall_CallViaMacro
0x1400200aa  mov     rcx, [rbp+var_48]
0x1400200ae  mov     edi, eax
0x1400200b0  mov     rax, [rbp+var_8]
0x1400200b4  mov     r14, [rcx]
0x1400200b7  mov     rcx, [rbp+var_40]
0x1400200bb  call    _guard_dispatch_icall
0x1400200c0  cmp     edi, 0C0350075h
0x1400200c6  jz      short loc_1400200DB
0x1400200c8  cmp     edi, 0C035000Bh
0x1400200ce  jz      short loc_1400200DB
0x1400200d0  lea     ecx, [rdi+3FCAFF7Fh]
0x1400200d6  cmp     ecx, 1
0x1400200d9  ja      short loc_140020102
0x1400200db  mov     r9d, esi
0x1400200de  mov     r8d, 40h ; '@'
0x1400200e4  mov     edx, r13d
0x1400200e7  mov     ecx, edi
0x1400200e9  call    WinHvpCurrentPartitionLowMemoryHandler
0x1400200ee  mov     edi, eax
0x1400200f0  test    eax, eax
0x1400200f2  js      short loc_14002010D
0x1400200f4  mov     edi, [rbp+arg_10]
0x1400200f7  inc     esi
0x1400200f9  mov     r14, [rbp+arg_0]
0x1400200fd  jmp     loc_140020045
0x140020102  test    edi, edi
0x140020104  js      short loc_14002010D
0x140020106  mov     rax, [rbp+arg_30]
0x14002010a  mov     [rax], r14
0x14002010d  mov     rbx, [rsp+70h+arg_8]
0x140020115  mov     eax, edi
0x140020117  add     rsp, 70h
0x14002011b  pop     r15
0x14002011d  pop     r14
0x14002011f  pop     r13
0x140020121  pop     r12
0x140020123  pop     rdi
0x140020124  pop     rsi
0x140020125  pop     rbp
0x140020126  retn
```
