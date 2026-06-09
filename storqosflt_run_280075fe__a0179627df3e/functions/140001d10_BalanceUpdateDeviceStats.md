# BalanceUpdateDeviceStats

- ea: `0x140001d10`
- end: `0x14000215d`
- name: `BalanceUpdateDeviceStats`
- size: `1101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140001bd0`

## callees

- `0x140001d10`
- `0x140002170`

## pseudocode

```c
unsigned __int64 __fastcall BalanceUpdateDeviceStats(__int64 a1, __int64 a2)
{
  __int64 v2; // r11
  unsigned __int64 v4; // rax
  __int64 v5; // rax
  unsigned __int32 v6; // ecx
  unsigned __int32 v7; // eax
  unsigned __int64 result; // rax
  unsigned __int64 v9; // rdx
  int v10; // r8d
  unsigned int v11; // edx
  __int64 i; // rcx
  __int64 v13; // rcx
  __int64 v14; // r8
  unsigned __int64 v15; // rbx
  __int64 v16; // r11
  __int64 v17; // r11
  __int64 v18; // r11
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rcx
  unsigned __int64 v21; // rcx
  unsigned __int64 v22; // r8
  unsigned __int64 v23; // rcx
  unsigned __int64 v24; // rcx
  signed __int32 v25; // ecx
  unsigned int v26; // eax

  v2 = a1;
  _InterlockedAdd64((volatile signed __int64 *)(a1 + 4144), *(_QWORD *)(a2 + 176) - *(_QWORD *)(a2 + 160));
  _InterlockedAdd64((volatile signed __int64 *)(a1 + 4152), *(_QWORD *)(a2 + 176) - *(_QWORD *)(a2 + 168));
  _InterlockedAdd64((volatile signed __int64 *)(a1 + 4040), *(_QWORD *)(a2 + 152));
  _InterlockedAdd64(
    (volatile signed __int64 *)(a1 + 4088),
    (unsigned __int64)((1LL << dword_14000D2A4) + *(_QWORD *)(a2 + 144) - 1LL) >> dword_14000D2A4);
  _InterlockedAdd64((volatile signed __int64 *)(a1 + 4112), (unsigned __int64)(*(_QWORD *)(a2 + 144) + 1023LL) >> 10);
  _InterlockedIncrement64((volatile signed __int64 *)(a1 + 4064));
  if ( *(_DWORD *)(a1 + 1152) == 2 )
  {
    v4 = (unsigned __int64)(*(_QWORD *)(a2 + 144) + 511LL) >> 9;
    _InterlockedIncrement64((volatile signed __int64 *)(a1 + 1184));
    if ( v4 )
    {
      _InterlockedAdd64((volatile signed __int64 *)(a1 + 1200), v4);
      if ( *(_BYTE *)(a2 + 127) )
        _InterlockedIncrement64((volatile signed __int64 *)(a1 + 1192));
      v5 = _InterlockedExchange64((volatile __int64 *)(a1 + 1176), *(_QWORD *)(a2 + 40));
      if ( v5 && *(_QWORD *)(a2 + 40) != v5 )
        _InterlockedIncrement64((volatile signed __int64 *)(a1 + 1208));
    }
    v6 = *(_DWORD *)(a1 + 4136);
    v7 = *(_DWORD *)(v2 + 1264);
    if ( v6 < v7 )
      _InterlockedCompareExchange((volatile signed __int32 *)(v2 + 1264), v6, v7);
    if ( v6 < *(_DWORD *)(v2 + 1256) )
      _InterlockedCompareExchange((volatile signed __int32 *)(v2 + 1152), 0, 2);
  }
  if ( !*(_DWORD *)(v2 + 1152)
    && *(_QWORD *)(a2 + 176) >= (unsigned __int64)(qword_14000D2F0 + *(_QWORD *)(v2 + 1168))
    && !_InterlockedCompareExchange((volatile signed __int32 *)(v2 + 1152), 1, 0) )
  {
    v9 = *(_QWORD *)(a2 + 176) - *(_QWORD *)(v2 + 1272);
    if ( v9 < qword_14000D2F8 )
      v10 = (unsigned int)(*(_DWORD *)(v2 + 1268) - 4) * (qword_14000D2F8 - v9) / qword_14000D2F8 + 4;
    else
      v10 = 4;
    v11 = 60 * v10 / 0x64u;
    if ( *(_DWORD *)(v2 + 4136) >= v11 )
    {
      for ( i = 0; i != 4; ++i )
        _InterlockedExchange64((volatile __int64 *)(v2 + 8 * i + 1184), 0);
      _InterlockedExchange64((volatile __int64 *)(v2 + 1176), 0);
      v13 = *(_QWORD *)(a2 + 176);
      *(_DWORD *)(v2 + 1264) = *(_DWORD *)(v2 + 4136);
      *(_QWORD *)(v2 + 1160) = v13;
      *(_DWORD *)(v2 + 1256) = v11;
      *(_DWORD *)(v2 + 1260) = v10;
      _InterlockedCompareExchange((volatile signed __int32 *)(v2 + 1152), 2, 1);
    }
    else
    {
      _InterlockedCompareExchange((volatile signed __int32 *)(v2 + 1152), 0, 1);
    }
  }
  result = *(unsigned int *)(v2 + 1152);
  if ( (_DWORD)result == 2 && *(_QWORD *)(a2 + 176) >= (unsigned __int64)(qword_14000D2E8 + *(_QWORD *)(v2 + 1160)) )
  {
    result = (unsigned int)_InterlockedCompareExchange((volatile signed __int32 *)(v2 + 1152), 1, 2);
    if ( (_DWORD)result == 2 )
    {
      v22 = *(_QWORD *)(v2 + 4064) - *(_QWORD *)(v2 + 1280);
      *(_QWORD *)(v2 + 1280) = *(_QWORD *)(v2 + 4064);
      if ( v22 )
      {
        v23 = *(_QWORD *)(v2 + 4152) - *(_QWORD *)(v2 + 1288);
        *(_QWORD *)(v2 + 1288) = *(_QWORD *)(v2 + 4152);
        v24 = (qword_14000D298 * (v23 / v22)) >> 16;
      }
      else
      {
        v24 = 0;
      }
      if ( 100 * v24 >= qword_14000D2D8 / 0xAuLL )
      {
        *(_QWORD *)(v2 + 1216) = (*(_QWORD *)(a2 + 176) - *(_QWORD *)(v2 + 1160)) * (0x3B9ACA00uLL / qword_14000D2C0);
        v26 = *(_DWORD *)(v2 + 1264);
        if ( v26 > *(_DWORD *)(v2 + 1260) )
        {
          *(_DWORD *)(v2 + 1268) = v26;
          *(_QWORD *)(v2 + 1272) = *(_QWORD *)(a2 + 176);
        }
        v25 = 3;
      }
      else
      {
        v25 = 0;
      }
      result = (unsigned int)_InterlockedCompareExchange((volatile signed __int32 *)(v2 + 1152), v25, 1);
    }
  }
  if ( *(_QWORD *)(a2 + 176) >= (unsigned __int64)(qword_14000D310 + *(_QWORD *)(v2 + 2952))
    && !_interlockedbittestandset((volatile signed __int32 *)(v2 + 2936), 0) )
  {
    v14 = *(_QWORD *)(v2 + 2952);
    result = *(_QWORD *)(a2 + 176);
    if ( result >= v14 + qword_14000D310 )
    {
      v15 = (result - v14) / qword_14000D310;
      BalanceUpdateMovingAverage(v15, v2 + 4040);
      BalanceUpdateMovingAverage(v15, v16 + 4064);
      BalanceUpdateMovingAverage(v15, v17 + 4088);
      result = BalanceUpdateMovingAverage(v15, v18 + 4112);
      v19 = *(_QWORD *)(v2 + 4080);
      *(_QWORD *)(v2 + 2952) = *(_QWORD *)(a2 + 176);
      if ( v19 )
      {
        result = *(_QWORD *)(v2 + 4056) / v19;
        *(_QWORD *)(v2 + 2960) = result;
      }
      v20 = *(_QWORD *)(v2 + 4104);
      if ( v20 )
      {
        result = *(_QWORD *)(v2 + 4056) / v20;
        *(_QWORD *)(v2 + 2968) = result;
      }
      if ( *(_DWORD *)(v2 + 2932) > 0x14u )
      {
        v21 = *(_QWORD *)(v2 + 2968);
        if ( v21 )
        {
          result = 0x3B9ACA00 / v21;
          *(_QWORD *)(v2 + 2976) = 0x3B9ACA00 / v21;
        }
      }
    }
    _interlockedbittestandreset((volatile signed __int32 *)(v2 + 2936), 0);
  }
  return result;
}

```

## disassembly

```asm
0x140001d10  push    rbx
0x140001d12  push    rbp
0x140001d13  push    rsi
0x140001d14  push    rdi
0x140001d15  push    r14
0x140001d17  sub     rsp, 20h
0x140001d1b  mov     r11, rcx
0x140001d1e  mov     rdi, rdx
0x140001d21  mov     rcx, [rdx+0B0h]
0x140001d28  sub     rcx, [rdx+0A0h]
0x140001d2f  lock add [r11+1030h], rcx
0x140001d37  mov     rcx, [rdx+0B0h]
0x140001d3e  sub     rcx, [rdx+0A8h]
0x140001d45  lock add [r11+1038h], rcx
0x140001d4d  mov     rax, [rdx+98h]
0x140001d54  lock add [r11+0FC8h], rax
0x140001d5c  mov     ecx, cs:dword_14000D2A4
0x140001d62  mov     r9d, 1
0x140001d68  mov     r8, [rdi+90h]
0x140001d6f  mov     edx, r9d
0x140001d72  shl     rdx, cl
0x140001d75  dec     r8
0x140001d78  add     r8, rdx
0x140001d7b  shr     r8, cl
0x140001d7e  lock add [r11+0FF8h], r8
0x140001d86  mov     rax, [rdi+90h]
0x140001d8d  add     rax, 3FFh
0x140001d93  shr     rax, 0Ah
0x140001d97  lock add [r11+1010h], rax
0x140001d9f  lock inc qword ptr [r11+0FE0h]
0x140001da7  mov     eax, [r11+480h]
0x140001dae  mov     ebx, 2
0x140001db3  cmp     eax, ebx
0x140001db5  jnz     loc_140001E3E
0x140001dbb  mov     rax, [rdi+90h]
0x140001dc2  add     rax, 1FFh
0x140001dc8  shr     rax, 9
0x140001dcc  lock inc qword ptr [r11+4A0h]
0x140001dd4  test    rax, rax
0x140001dd7  jz      short loc_140001E0D
0x140001dd9  lock add [r11+4B0h], rax
0x140001de1  cmp     byte ptr [rdi+7Fh], 0
0x140001de5  jz      short loc_140001DEF
0x140001de7  lock inc qword ptr [r11+4A8h]
0x140001def  mov     rax, [rdi+28h]
0x140001df3  xchg    rax, [r11+498h]
0x140001dfa  test    rax, rax
0x140001dfd  jz      short loc_140001E0D
0x140001dff  cmp     [rdi+28h], rax
0x140001e03  jz      short loc_140001E0D
0x140001e05  lock inc qword ptr [r11+4B8h]
0x140001e0d  mov     ecx, [r11+1028h]
0x140001e14  mov     eax, [r11+4F0h]
0x140001e1b  cmp     ecx, eax
0x140001e1d  jnb     short loc_140001E28
0x140001e1f  lock cmpxchg [r11+4F0h], ecx
0x140001e28  cmp     ecx, [r11+4E8h]
0x140001e2f  jnb     short loc_140001E3E
0x140001e31  xor     ecx, ecx
0x140001e33  mov     eax, ebx
0x140001e35  lock cmpxchg [r11+480h], ecx
0x140001e3e  mov     eax, [r11+480h]
0x140001e45  test    eax, eax
0x140001e47  jz      short loc_140001E96
0x140001e49  mov     eax, [r11+480h]
0x140001e50  cmp     eax, ebx
0x140001e52  jnz     short loc_140001E6F
0x140001e54  mov     rcx, [r11+488h]
0x140001e5b  add     rcx, cs:qword_14000D2E8
0x140001e62  cmp     [rdi+0B0h], rcx
0x140001e69  jnb     loc_14000207B
0x140001e6f  mov     rcx, [r11+0B88h]
0x140001e76  add     rcx, cs:qword_14000D310
0x140001e7d  cmp     [rdi+0B0h], rcx
0x140001e84  jnb     loc_140001F7E
0x140001e8a  add     rsp, 20h
0x140001e8e  pop     r14
0x140001e90  pop     rdi
0x140001e91  pop     rsi
0x140001e92  pop     rbp
0x140001e93  pop     rbx
0x140001e94  retn
0x140001e96  mov     rcx, [r11+490h]
0x140001e9d  add     rcx, cs:qword_14000D2F0
0x140001ea4  cmp     [rdi+0B0h], rcx
0x140001eab  jb      short loc_140001E49
0x140001ead  xor     eax, eax
0x140001eaf  lock cmpxchg [r11+480h], r9d
0x140001eb8  jnz     short loc_140001E49
0x140001eba  mov     rdx, [rdi+0B0h]
0x140001ec1  sub     rdx, [r11+4F8h]
0x140001ec8  mov     r8, cs:qword_14000D2F8
0x140001ecf  cmp     rdx, r8
0x140001ed2  jb      short loc_140001F06
0x140001ed4  mov     r8d, 4
0x140001eda  imul    ecx, r8d, 3Ch ; '<'
0x140001ede  mov     eax, 51EB851Fh
0x140001ee3  mul     ecx
0x140001ee5  mov     eax, [r11+1028h]
0x140001eec  shr     edx, 5
0x140001eef  cmp     eax, edx
0x140001ef1  jnb     short loc_140001F25
0x140001ef3  xor     ecx, ecx
0x140001ef5  mov     eax, r9d
0x140001ef8  lock cmpxchg [r11+480h], ecx
0x140001f01  jmp     loc_140001E49
0x140001f06  mov     ecx, [r11+4F4h]
0x140001f0d  mov     rax, r8
0x140001f10  sub     rax, rdx
0x140001f13  sub     ecx, 4
0x140001f16  imul    rax, rcx
0x140001f1a  xor     edx, edx
0x140001f1c  div     r8
0x140001f1f  lea     r8d, [rax+4]
0x140001f23  jmp     short loc_140001EDA
0x140001f25  xor     ecx, ecx
0x140001f27  xor     eax, eax
0x140001f29  xchg    rax, [r11+rcx*8+4A0h]
0x140001f31  inc     rcx
0x140001f34  cmp     rcx, 4
0x140001f38  jnz     short loc_140001F27
0x140001f3a  xor     eax, eax
0x140001f3c  xchg    rax, [r11+498h]
0x140001f43  mov     eax, [r11+1028h]
0x140001f4a  mov     rcx, [rdi+0B0h]
0x140001f51  mov     [r11+4F0h], eax
0x140001f58  mov     eax, r9d
0x140001f5b  mov     [r11+488h], rcx
0x140001f62  mov     [r11+4E8h], edx
0x140001f69  mov     [r11+4ECh], r8d
0x140001f70  lock cmpxchg [r11+480h], ebx
0x140001f79  jmp     loc_140001E49
0x140001f7e  lock bts dword ptr [r11+0B78h], 0
0x140001f88  jb      loc_140001E8A
0x140001f8e  mov     r8, [r11+0B88h]
0x140001f95  mov     r9, cs:qword_14000D310
0x140001f9c  mov     rax, [rdi+0B0h]
0x140001fa3  lea     rcx, [r8+r9]
0x140001fa7  cmp     rax, rcx
0x140001faa  jb      loc_14000204D
0x140001fb0  sub     rax, r8
0x140001fb3  xor     edx, edx
0x140001fb5  div     r9
0x140001fb8  lea     rdx, [r11+0FC8h]
0x140001fbf  mov     rcx, rax
0x140001fc2  mov     rbx, rax
0x140001fc5  call    BalanceUpdateMovingAverage
0x140001fca  mov     rcx, rbx
0x140001fcd  lea     rdx, [r11+0FE0h]
0x140001fd4  call    BalanceUpdateMovingAverage
0x140001fd9  mov     rcx, rbx
0x140001fdc  lea     rdx, [r11+0FF8h]
0x140001fe3  call    BalanceUpdateMovingAverage
0x140001fe8  mov     rcx, rbx
0x140001feb  lea     rdx, [r11+1010h]
0x140001ff2  call    BalanceUpdateMovingAverage
0x140001ff7  mov     rcx, [r11+0FF0h]
0x140001ffe  mov     rdx, [rdi+0B0h]
0x140002005  mov     [r11+0B88h], rdx
0x14000200c  test    rcx, rcx
0x14000200f  jz      short loc_140002024
0x140002011  mov     rax, [r11+0FD8h]
0x140002018  xor     edx, edx
0x14000201a  div     rcx
0x14000201d  mov     [r11+0B90h], rax
0x140002024  mov     rcx, [r11+1008h]
0x14000202b  test    rcx, rcx
0x14000202e  jz      short loc_140002043
0x140002030  mov     rax, [r11+0FD8h]
0x140002037  xor     edx, edx
0x140002039  div     rcx
0x14000203c  mov     [r11+0B98h], rax
0x140002043  cmp     dword ptr [r11+0B74h], 14h
0x14000204b  ja      short loc_14000205C
0x14000204d  lock btr dword ptr [r11+0B78h], 0
0x140002057  jmp     loc_140001E8A
0x14000205c  mov     rcx, [r11+0B98h]
0x140002063  test    rcx, rcx
0x140002066  jz      short loc_14000204D
0x140002068  xor     edx, edx
0x14000206a  mov     eax, 3B9ACA00h
0x14000206f  div     rcx
0x140002072  mov     [r11+0BA0h], rax
0x140002079  jmp     short loc_14000204D
0x14000207b  mov     eax, ebx
0x14000207d  lock cmpxchg [r11+480h], r9d
0x140002086  jnz     loc_140001E6F
0x14000208c  mov     rax, [r11+0FE0h]
0x140002093  mov     r8, rax
0x140002096  sub     r8, [r11+500h]
0x14000209d  mov     [r11+500h], rax
0x1400020a4  jz      short loc_1400020D7
0x1400020a6  mov     rax, [r11+1038h]
0x1400020ad  xor     edx, edx
0x1400020af  mov     rcx, rax
0x1400020b2  sub     rcx, [r11+508h]
0x1400020b9  mov     [r11+508h], rax
0x1400020c0  mov     rax, rcx
0x1400020c3  div     r8
0x1400020c6  mov     rcx, rax
0x1400020c9  imul    rcx, cs:qword_14000D298
0x1400020d1  shr     rcx, 10h
0x1400020d5  jmp     short loc_1400020D9
0x1400020d7  xor     ecx, ecx
0x1400020d9  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400020e3  mul     cs:qword_14000D2D8
0x1400020ea  imul    rcx, 64h ; 'd'
0x1400020ee  shr     rdx, 3
0x1400020f2  cmp     rcx, rdx
0x1400020f5  jnb     short loc_1400020FB
0x1400020f7  xor     ecx, ecx
0x1400020f9  jmp     short loc_14000214C
0x1400020fb  xor     edx, edx
0x1400020fd  mov     eax, 3B9ACA00h
0x140002102  div     cs:qword_14000D2C0
0x140002109  mov     rdx, [rdi+0B0h]
0x140002110  sub     rdx, [r11+488h]
0x140002117  imul    rax, rdx
0x14000211b  mov     [r11+4C0h], rax
0x140002122  mov     eax, [r11+4F0h]
0x140002129  cmp     eax, [r11+4ECh]
0x140002130  jbe     short loc_140002147
0x140002132  mov     [r11+4F4h], eax
0x140002139  mov     rax, [rdi+0B0h]
0x140002140  mov     [r11+4F8h], rax
0x140002147  mov     ecx, 3
0x14000214c  mov     eax, r9d
0x14000214f  lock cmpxchg [r11+480h], ecx
0x140002158  jmp     loc_140001E6F
```
