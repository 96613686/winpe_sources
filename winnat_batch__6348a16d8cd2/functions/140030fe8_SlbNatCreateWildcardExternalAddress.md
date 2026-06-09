# SlbNatCreateWildcardExternalAddress

- ea: `0x140030fe8`
- end: `0x1400310f2`
- name: `SlbNatCreateWildcardExternalAddress`
- size: `266`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400308ac`

## callees

- `0x14000caa0`
- `0x14001448c`
- `0x14001ede0`
- `0x14001f440`
- `0x140030fe8`
- `0x140034638`

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
  __int64 v19; // r9
  __int128 v20; // [rsp+30h] [rbp-59h] BYREF
  __int64 v21; // [rsp+40h] [rbp-49h]
  _OWORD v22[6]; // [rsp+50h] [rbp-39h] BYREF

  memset(v22, 0, 0x54u);
  v7 = *(_OWORD *)(a1 + 96);
  v8 = *(_DWORD *)(a1 + 256);
  v21 = 0;
  v20 = 0;
  v9 = *(_OWORD *)(a1 + 80);
  v22[1] = v7;
  v10 = *(_OWORD *)(a1 + 128);
  v22[0] = v9;
  v11 = *(_OWORD *)(a1 + 112);
  v22[3] = v10;
  v22[2] = v11;
  v22[4] = *(_OWORD *)(a1 + 144);
  while ( SlbNatFindExternalAddress(a1, v8) )
  {
    v12 = v8++;
    if ( v12 == -1 )
      return 3221225473LL;
  }
  LODWORD(v22[5]) = v8;
  LOWORD(v20) = 2;
  WORD2(v21) = a3;
  HIWORD(v21) = a3;
  ExternalAddressWithLock = SlbNatCreateExternalAddressWithLock((__int64)v22, (__int16 *)&v20, 0, 0, 0);
  if ( ExternalAddressWithLock >= 0 )
  {
    ExternalAddress = SlbNatFindExternalAddress(a1, v8);
    *(_QWORD *)a4 = ExternalAddress;
    if ( !ExternalAddress )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v17, v16, v18, v19);
    *(_BYTE *)(*(_QWORD *)a4 + 92LL) |= 1u;
  }
  return (unsigned int)ExternalAddressWithLock;
}

```

## disassembly

```asm
0x140030fe8  push    rbp
0x140030fea  push    rbx
0x140030feb  push    rsi
0x140030fec  push    rdi
0x140030fed  push    r14
0x140030fef  lea     rbp, [rsp-37h]
0x140030ff4  sub     rsp, 0C0h
0x140030ffb  mov     rax, cs:__security_cookie
0x140031002  xor     rax, rsp
0x140031005  mov     [rbp+57h+var_30], rax
0x140031009  xor     edx, edx; Val
0x14003100b  movzx   esi, r8w
0x14003100f  mov     rdi, rcx
0x140031012  mov     r14, r9
0x140031015  lea     rcx, [rbp+57h+var_90]; void *
0x140031019  lea     r8d, [rdx+54h]; Size
0x14003101d  call    memset
0x140031022  movups  xmm1, xmmword ptr [rdi+60h]
0x140031026  mov     ebx, [rdi+100h]
0x14003102c  xor     eax, eax
0x14003102e  xorps   xmm0, xmm0
0x140031031  mov     [rbp+57h+var_A0], rax
0x140031035  movups  [rbp+57h+var_B0], xmm0
0x140031039  movups  xmm0, xmmword ptr [rdi+50h]
0x14003103d  movaps  [rbp+57h+var_80], xmm1
0x140031041  movups  xmm1, xmmword ptr [rdi+80h]
0x140031048  movaps  [rbp+57h+var_90], xmm0
0x14003104c  movups  xmm0, xmmword ptr [rdi+70h]
0x140031050  movaps  [rbp+57h+var_60], xmm1
0x140031054  movaps  [rbp+57h+var_70], xmm0
0x140031058  movups  xmm0, xmmword ptr [rdi+90h]
0x14003105f  movaps  [rbp+57h+var_50], xmm0
0x140031063  mov     edx, ebx
0x140031065  mov     rcx, rdi
0x140031068  call    SlbNatFindExternalAddress
0x14003106d  test    rax, rax
0x140031070  jz      short loc_140031082
0x140031072  mov     eax, ebx
0x140031074  inc     ebx
0x140031076  cmp     eax, 0FFFFFFFFh
0x140031079  jnz     short loc_140031063
0x14003107b  mov     eax, 0C0000001h
0x140031080  jmp     short loc_1400310D7
0x140031082  mov     eax, 2
0x140031087  mov     [rbp+57h+var_40], ebx
0x14003108a  xor     r9d, r9d
0x14003108d  mov     word ptr [rbp+57h+var_B0], ax
0x140031091  xor     r8d, r8d
0x140031094  mov     word ptr [rbp+57h+var_A0+4], si
0x140031098  lea     rdx, [rbp+57h+var_B0]
0x14003109c  mov     word ptr [rbp+57h+var_A0+6], si
0x1400310a0  lea     rcx, [rbp+57h+var_90]
0x1400310a4  mov     [rsp+0E0h+var_C0], 0
0x1400310ac  call    SlbNatCreateExternalAddressWithLock
0x1400310b1  mov     esi, eax
0x1400310b3  test    eax, eax
0x1400310b5  js      short loc_1400310D5
0x1400310b7  mov     edx, ebx
0x1400310b9  mov     rcx, rdi
0x1400310bc  call    SlbNatFindExternalAddress
0x1400310c1  mov     [r14], rax
0x1400310c4  test    rax, rax
0x1400310c7  jnz     short loc_1400310CE
0x1400310c9  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400310ce  mov     rax, [r14]
0x1400310d1  or      byte ptr [rax+5Ch], 1
0x1400310d5  mov     eax, esi
0x1400310d7  mov     rcx, [rbp+57h+var_30]
0x1400310db  xor     rcx, rsp; StackCookie
0x1400310de  call    __security_check_cookie
0x1400310e3  add     rsp, 0C0h
0x1400310ea  pop     r14
0x1400310ec  pop     rdi
0x1400310ed  pop     rsi
0x1400310ee  pop     rbx
0x1400310ef  pop     rbp
0x1400310f0  retn
```
