# FH4::HandlerMap4::HandlerMap4(FH4::TryBlockMapEntry4 const *,unsigned __int64,int)

- ea: `0x1400043e0`
- end: `0x140004462`
- name: `??0HandlerMap4@FH4@@QEAA@PEBUTryBlockMapEntry4@1@_KH@Z`
- size: `130`
- prototype: `__int64 __fastcall(FH4::HandlerMap4 *__hidden this, const struct FH4::TryBlockMapEntry4 *, unsigned __int64, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140003624`
- `0x140003b64`

## callees

- `0x1400043e0`
- `0x1400048bc`

## pseudocode

```c
FH4::HandlerMap4 *__fastcall FH4::HandlerMap4::HandlerMap4(
        FH4::HandlerMap4 *this,
        const struct FH4::TryBlockMapEntry4 *a2,
        __int64 a3,
        int a4)
{
  _BYTE *v5; // rdx
  __int64 v6; // rcx
  _BYTE *v7; // rdx

  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_BYTE *)this + 24) = 0;
  *(_QWORD *)((char *)this + 28) = 0;
  *(_QWORD *)((char *)this + 36) = 0;
  *((_OWORD *)this + 3) = 0;
  *((_QWORD *)this + 8) = a3;
  *((_DWORD *)this + 18) = a4;
  if ( *((_DWORD *)a2 + 3) )
  {
    v5 = (_BYTE *)(a3 + *((int *)a2 + 3));
    *((_QWORD *)this + 1) = v5;
    v6 = *v5 & 0xF;
    v7 = &v5[-*((char *)&FH4::s_negLengthTab + v6)];
    *(_DWORD *)this = *((_DWORD *)v7 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v6);
    *((_QWORD *)this + 1) = v7;
    *((_QWORD *)this + 2) = v7;
    FH4::HandlerMap4::DecompHandler(this);
  }
  else
  {
    *(_DWORD *)this = 0;
  }
  return this;
}

```

## disassembly

```asm
0x1400043e0  push    rbx
0x1400043e2  sub     rsp, 20h
0x1400043e6  xor     eax, eax
0x1400043e8  xorps   xmm0, xmm0
0x1400043eb  mov     [rcx+8], rax
0x1400043ef  mov     rbx, rcx
0x1400043f2  mov     [rcx+10h], rax
0x1400043f6  mov     [rcx+18h], al
0x1400043f9  mov     [rcx+1Ch], rax
0x1400043fd  mov     [rcx+24h], rax
0x140004401  movups  xmmword ptr [rcx+30h], xmm0
0x140004405  mov     [rcx+40h], r8
0x140004409  mov     [rcx+48h], r9d
0x14000440d  cmp     [rdx+0Ch], eax
0x140004410  jz      short loc_140004457
0x140004412  movsxd  rdx, dword ptr [rdx+0Ch]
0x140004416  add     rdx, r8
0x140004419  lea     r8, cs:140000000h
0x140004420  mov     [rcx+8], rdx
0x140004424  movzx   ecx, byte ptr [rdx]
0x140004427  and     ecx, 0Fh
0x14000442a  movsx   rax, byte ptr [rcx+r8+7460h]
0x140004433  mov     cl, [rcx+r8+7470h]
0x14000443b  sub     rdx, rax
0x14000443e  mov     eax, [rdx-4]
0x140004441  shr     eax, cl
0x140004443  mov     rcx, rbx; this
0x140004446  mov     [rbx], eax
0x140004448  mov     [rbx+8], rdx
0x14000444c  mov     [rbx+10h], rdx
0x140004450  call    ?DecompHandler@HandlerMap4@FH4@@AEAAXXZ; FH4::HandlerMap4::DecompHandler(void)
0x140004455  jmp     short loc_140004459
0x140004457  mov     [rcx], eax
0x140004459  mov     rax, rbx
0x14000445c  add     rsp, 20h
0x140004460  pop     rbx
0x140004461  retn
```
