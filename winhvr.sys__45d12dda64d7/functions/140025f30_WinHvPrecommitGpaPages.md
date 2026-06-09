# WinHvPrecommitGpaPages

- ea: `0x140025f30`
- end: `0x14002605d`
- name: `WinHvPrecommitGpaPages`
- size: `301`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001a38`
- `0x140002358`
- `0x140009c50`
- `0x140009c90`
- `0x14000a040`
- `0x140025f30`

## pseudocode

```c
__int64 __fastcall WinHvPrecommitGpaPages(__int64 a1, int a2, __int64 a3, __int64 a4, _QWORD *a5)
{
  int v9; // edi
  int v10; // eax
  __int64 v11; // r14
  int v12; // ebx
  __int64 v14; // [rsp+40h] [rbp-51h] BYREF
  _QWORD v15[8]; // [rsp+50h] [rbp-41h] BYREF
  __int64 v16; // [rsp+90h] [rbp-1h] BYREF
  int v17; // [rsp+98h] [rbp+7h]
  int v18; // [rsp+9Ch] [rbp+Bh]
  __int64 v19; // [rsp+A0h] [rbp+Fh] BYREF

  memset(v15, 0, sizeof(v15));
  v19 = a3;
  v9 = 0;
  v18 = 0;
  v14 = 0;
  *a5 = 0;
  v15[0] = 0;
  v16 = a1;
  v17 = a2;
  while ( 1 )
  {
    v10 = WinHvpRangeRepHypercall(190, a4, &v16, 24, &v19, 1, v15, &v14);
    v11 = v14;
    v12 = v10;
    *a5 += v14;
    if ( v10 != -1070268405 && v10 != -1070268299 && (unsigned int)(v10 + 1070268287) > 1 )
      break;
    v12 = WinHvpLowMemoryHandler(a1, -2147418113, v10, 190, v9, 0);
    if ( v12 < 0 )
      break;
    a4 -= v11;
    ++v9;
  }
  if ( v15[0] )
    ((void (*)(void))v15[7])();
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140025f30  push    rbp
0x140025f32  push    rbx
0x140025f33  push    rsi
0x140025f34  push    rdi
0x140025f35  push    r12
0x140025f37  push    r14
0x140025f39  push    r15
0x140025f3b  lea     rbp, [rsp-1Fh]
0x140025f40  sub     rsp, 0B0h
0x140025f47  mov     rax, cs:__security_cookie
0x140025f4e  xor     rax, rsp
0x140025f51  mov     [rbp+4Fh+var_38], rax
0x140025f55  mov     r15, [rbp+4Fh+arg_20]
0x140025f59  mov     ebx, edx
0x140025f5b  xor     edx, edx; Val
0x140025f5d  mov     rdi, r8
0x140025f60  mov     r12, rcx
0x140025f63  mov     rsi, r9
0x140025f66  lea     rcx, [rbp+4Fh+var_90]; void *
0x140025f6a  lea     r8d, [rdx+40h]; Size
0x140025f6e  call    memset
0x140025f73  mov     [rbp+4Fh+var_40], rdi
0x140025f77  xor     edi, edi
0x140025f79  mov     [rbp+4Fh+var_44], 0
0x140025f80  mov     [rbp+4Fh+var_A0], 0
0x140025f88  mov     qword ptr [r15], 0
0x140025f8f  mov     [rbp+4Fh+var_90], 0
0x140025f97  mov     [rbp+4Fh+var_50], r12
0x140025f9b  mov     [rbp+4Fh+var_48], ebx
0x140025f9e  lea     rax, [rbp+4Fh+var_A0]
0x140025fa2  mov     r9d, 18h
0x140025fa8  mov     [rsp+0E0h+var_A8], rax
0x140025fad  lea     r8, [rbp+4Fh+var_50]
0x140025fb1  lea     rax, [rbp+4Fh+var_90]
0x140025fb5  mov     rdx, rsi
0x140025fb8  mov     [rsp+0E0h+var_B0], rax
0x140025fbd  mov     ecx, 0BEh
0x140025fc2  lea     rax, [rbp+4Fh+var_40]
0x140025fc6  mov     [rsp+0E0h+var_B8], 1
0x140025fcf  mov     [rsp+0E0h+var_C0], rax
0x140025fd4  call    WinHvpRangeRepHypercall
0x140025fd9  mov     r14, [rbp+4Fh+var_A0]
0x140025fdd  mov     ebx, eax
0x140025fdf  add     [r15], r14
0x140025fe2  cmp     eax, 0C035000Bh
0x140025fe7  jz      short loc_14002602E
0x140025fe9  cmp     eax, 0C0350075h
0x140025fee  jz      short loc_14002602E
0x140025ff0  lea     ecx, [rax+3FCAFF7Fh]
0x140025ff6  cmp     ecx, 1
0x140025ff9  jbe     short loc_14002602E
0x140025ffb  mov     rcx, [rbp+4Fh+var_90]
0x140025fff  test    rcx, rcx
0x140026002  jz      short loc_14002600D
0x140026004  mov     rax, [rbp+4Fh+var_58]
0x140026008  call    _guard_dispatch_icall
0x14002600d  mov     eax, ebx
0x14002600f  mov     rcx, [rbp+4Fh+var_38]
0x140026013  xor     rcx, rsp; StackCookie
0x140026016  call    __security_check_cookie
0x14002601b  add     rsp, 0B0h
0x140026022  pop     r15
0x140026024  pop     r14
0x140026026  pop     r12
0x140026028  pop     rdi
0x140026029  pop     rsi
0x14002602a  pop     rbx
0x14002602b  pop     rbp
0x14002602c  retn
0x14002602e  mov     byte ptr [rsp+0E0h+var_B8], 0
0x140026033  mov     r9d, 0BEh
0x140026039  mov     r8d, eax
0x14002603c  mov     dword ptr [rsp+0E0h+var_C0], edi
0x140026040  mov     edx, 8000FFFFh
0x140026045  mov     rcx, r12
0x140026048  call    WinHvpLowMemoryHandler
0x14002604d  mov     ebx, eax
0x14002604f  test    eax, eax
0x140026051  js      short loc_140025FFB
0x140026053  sub     rsi, r14
0x140026056  inc     edi
0x140026058  jmp     loc_140025F9E
```
