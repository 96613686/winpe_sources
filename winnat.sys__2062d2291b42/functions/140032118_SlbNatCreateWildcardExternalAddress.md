# SlbNatCreateWildcardExternalAddress

- ea: `0x140032118`
- end: `0x140032222`
- name: `SlbNatCreateWildcardExternalAddress`
- size: `266`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400319dc`

## callees

- `0x14000caa0`
- `0x140014dcc`
- `0x14001f320`
- `0x14001f980`
- `0x140032118`
- `0x140035948`

## pseudocode

```c
__int64 __fastcall SlbNatCreateWildcardExternalAddress(__int64 a1, __int64 a2, __int16 a3, __int64 a4)
{
  __int128 v7; // xmm1
  unsigned int v8; // ebx
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  int v12; // eax
  int ExternalAddressWithLock; // esi
  __int64 ExternalAddress; // rax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int128 v19; // [rsp+30h] [rbp-59h] BYREF
  __int64 v20; // [rsp+40h] [rbp-49h]
  _OWORD v21[6]; // [rsp+50h] [rbp-39h] BYREF

  memset(v21, 0, 0x54u);
  v7 = *(_OWORD *)(a1 + 96);
  v8 = *(_DWORD *)(a1 + 256);
  v20 = 0;
  v19 = 0;
  v9 = *(_OWORD *)(a1 + 80);
  v21[1] = v7;
  v10 = *(_OWORD *)(a1 + 128);
  v21[0] = v9;
  v11 = *(_OWORD *)(a1 + 112);
  v21[3] = v10;
  v21[2] = v11;
  v21[4] = *(_OWORD *)(a1 + 144);
  while ( SlbNatFindExternalAddress(a1, v8) )
  {
    v12 = v8++;
    if ( v12 == -1 )
      return 3221225473LL;
  }
  LODWORD(v21[5]) = v8;
  LOWORD(v19) = 2;
  WORD2(v20) = a3;
  HIWORD(v20) = a3;
  ExternalAddressWithLock = SlbNatCreateExternalAddressWithLock((__int64)v21, (__int16 *)&v19, 0, 0, 0);
  if ( ExternalAddressWithLock >= 0 )
  {
    ExternalAddress = SlbNatFindExternalAddress(a1, v8);
    *(_QWORD *)a4 = ExternalAddress;
    if ( !ExternalAddress )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v17, v16, v18);
    *(_BYTE *)(*(_QWORD *)a4 + 92LL) |= 1u;
  }
  return (unsigned int)ExternalAddressWithLock;
}

```

## disassembly

```asm
0x140032118  push    rbp
0x14003211a  push    rbx
0x14003211b  push    rsi
0x14003211c  push    rdi
0x14003211d  push    r14
0x14003211f  lea     rbp, [rsp-37h]
0x140032124  sub     rsp, 0C0h
0x14003212b  mov     rax, cs:__security_cookie
0x140032132  xor     rax, rsp
0x140032135  mov     [rbp+57h+var_30], rax
0x140032139  xor     edx, edx; Val
0x14003213b  movzx   esi, r8w
0x14003213f  mov     rdi, rcx
0x140032142  mov     r14, r9
0x140032145  lea     rcx, [rbp+57h+var_90]; void *
0x140032149  lea     r8d, [rdx+54h]; Size
0x14003214d  call    memset
0x140032152  movups  xmm1, xmmword ptr [rdi+60h]
0x140032156  mov     ebx, [rdi+100h]
0x14003215c  xor     eax, eax
0x14003215e  xorps   xmm0, xmm0
0x140032161  mov     [rbp+57h+var_A0], rax
0x140032165  movups  [rbp+57h+var_B0], xmm0
0x140032169  movups  xmm0, xmmword ptr [rdi+50h]
0x14003216d  movaps  [rbp+57h+var_80], xmm1
0x140032171  movups  xmm1, xmmword ptr [rdi+80h]
0x140032178  movaps  [rbp+57h+var_90], xmm0
0x14003217c  movups  xmm0, xmmword ptr [rdi+70h]
0x140032180  movaps  [rbp+57h+var_60], xmm1
0x140032184  movaps  [rbp+57h+var_70], xmm0
0x140032188  movups  xmm0, xmmword ptr [rdi+90h]
0x14003218f  movaps  [rbp+57h+var_50], xmm0
0x140032193  mov     edx, ebx
0x140032195  mov     rcx, rdi
0x140032198  call    SlbNatFindExternalAddress
0x14003219d  test    rax, rax
0x1400321a0  jz      short loc_1400321B2
0x1400321a2  mov     eax, ebx
0x1400321a4  inc     ebx
0x1400321a6  cmp     eax, 0FFFFFFFFh
0x1400321a9  jnz     short loc_140032193
0x1400321ab  mov     eax, 0C0000001h
0x1400321b0  jmp     short loc_140032207
0x1400321b2  mov     eax, 2
0x1400321b7  mov     [rbp+57h+var_40], ebx
0x1400321ba  xor     r9d, r9d
0x1400321bd  mov     word ptr [rbp+57h+var_B0], ax
0x1400321c1  xor     r8d, r8d
0x1400321c4  mov     word ptr [rbp+57h+var_A0+4], si
0x1400321c8  lea     rdx, [rbp+57h+var_B0]
0x1400321cc  mov     word ptr [rbp+57h+var_A0+6], si
0x1400321d0  lea     rcx, [rbp+57h+var_90]
0x1400321d4  mov     [rsp+0E0h+var_C0], 0
0x1400321dc  call    SlbNatCreateExternalAddressWithLock
0x1400321e1  mov     esi, eax
0x1400321e3  test    eax, eax
0x1400321e5  js      short loc_140032205
0x1400321e7  mov     edx, ebx
0x1400321e9  mov     rcx, rdi
0x1400321ec  call    SlbNatFindExternalAddress
0x1400321f1  mov     [r14], rax
0x1400321f4  test    rax, rax
0x1400321f7  jnz     short loc_1400321FE
0x1400321f9  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400321fe  mov     rax, [r14]
0x140032201  or      byte ptr [rax+5Ch], 1
0x140032205  mov     eax, esi
0x140032207  mov     rcx, [rbp+57h+var_30]
0x14003220b  xor     rcx, rsp; StackCookie
0x14003220e  call    __security_check_cookie
0x140032213  add     rsp, 0C0h
0x14003221a  pop     r14
0x14003221c  pop     rdi
0x14003221d  pop     rsi
0x14003221e  pop     rbx
0x14003221f  pop     rbp
0x140032220  retn
```
