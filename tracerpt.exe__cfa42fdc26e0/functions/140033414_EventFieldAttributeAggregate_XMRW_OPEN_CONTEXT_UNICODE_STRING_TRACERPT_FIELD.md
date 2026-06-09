# EventFieldAttributeAggregate(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_FIELD *)

- ea: `0x140033414`
- end: `0x140033576`
- name: `?EventFieldAttributeAggregate@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_FIELD@@@Z`
- size: `354`
- prototype: `__int64 __fastcall(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING *, struct _TRACERPT_FIELD *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400339c8`

## callees

- `0x140016808`
- `0x140033414`
- `0x14003694c`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall EventFieldAttributeAggregate(
        struct _XMRW_OPEN_CONTEXT *a1,
        struct _UNICODE_STRING *a2,
        struct _TRACERPT_FIELD *a3)
{
  __int64 v3; // rax
  __int64 v7; // rdi
  char v8; // al
  struct _UNICODE_STRING v9; // [rsp+20h] [rbp-18h] BYREF
  unsigned int v10; // [rsp+60h] [rbp+28h] BYREF

  v3 = *((_QWORD *)a1 + 12);
  v10 = 0;
  if ( !v3 )
    return 0;
  v7 = *((_QWORD *)a1 + 3);
  if ( (*(_BYTE *)(v3 + 370) & 2) == 0 )
  {
    v8 = *((_BYTE *)a3 + 216);
    if ( (v8 & 0x40) != 0 )
    {
      (*(void (__fastcall **)(_QWORD, unsigned int *))(*(_QWORD *)v7 + 168LL))(*((_QWORD *)a1 + 3), &v10);
      PrintMessage(0x44Bu, v10);
      return 3221745153LL;
    }
    *((_BYTE *)a3 + 216) = v8 | 0x40;
    v9 = *a2;
    if ( EqualString(&v9, L"total", 0) )
    {
      *((_BYTE *)a3 + 216) &= 0xFCu;
    }
    else
    {
      v9 = *a2;
      if ( EqualString(&v9, L"average", 0) )
      {
        *((_BYTE *)a3 + 216) &= ~2u;
        *((_BYTE *)a3 + 216) |= 1u;
      }
      else
      {
        v9 = *a2;
        if ( !EqualString(&v9, L"rate", 0) )
        {
          (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v7 + 168LL))(v7, &v10);
          PrintMessage(0x44Cu, v10, a2);
          return 3221745184LL;
        }
        *((_BYTE *)a3 + 216) &= ~1u;
        *((_BYTE *)a3 + 216) |= 2u;
      }
    }
    return 0;
  }
  (*(void (__fastcall **)(_QWORD, unsigned int *))(*(_QWORD *)v7 + 168LL))(*((_QWORD *)a1 + 3), &v10);
  PrintMessage(0x44Au, v10);
  return 3221745184LL;
}

```

## disassembly

```asm
0x140033414  push    rbp
0x140033416  push    rbx
0x140033417  push    rsi
0x140033418  push    rdi
0x140033419  mov     rbp, rsp
0x14003341c  sub     rsp, 38h
0x140033420  mov     rax, [rcx+60h]
0x140033424  mov     rbx, r8
0x140033427  mov     [rbp+arg_0], 0
0x14003342e  mov     rsi, rdx
0x140033431  test    rax, rax
0x140033434  jnz     short loc_14003343D
0x140033436  xor     eax, eax
0x140033438  jmp     loc_14003356D
0x14003343d  test    byte ptr [rax+172h], 2
0x140033444  mov     rdi, [rcx+18h]
0x140033448  jz      short loc_140033472
0x14003344a  mov     rax, [rdi]
0x14003344d  lea     rdx, [rbp+arg_0]
0x140033451  mov     rcx, rdi
0x140033454  mov     rax, [rax+0A8h]
0x14003345b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033460  mov     edx, [rbp+arg_0]
0x140033463  mov     ecx, 44Ah; unsigned int
0x140033468  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x14003346d  jmp     loc_140033568
0x140033472  mov     al, [r8+0D8h]
0x140033479  test    al, 40h
0x14003347b  jz      short loc_1400334AA
0x14003347d  mov     rax, [rdi]
0x140033480  lea     rdx, [rbp+arg_0]
0x140033484  mov     rcx, rdi
0x140033487  mov     rax, [rax+0A8h]
0x14003348e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033493  mov     edx, [rbp+arg_0]
0x140033496  mov     ecx, 44Bh; unsigned int
0x14003349b  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x1400334a0  mov     eax, 0C007EE01h
0x1400334a5  jmp     loc_14003356D
0x1400334aa  or      al, 40h
0x1400334ac  lea     rcx, [rbp+var_18]; struct _UNICODE_STRING
0x1400334b0  mov     [r8+0D8h], al
0x1400334b7  xor     r8d, r8d; unsigned __int8
0x1400334ba  movups  xmm0, xmmword ptr [rdx]
0x1400334bd  lea     rdx, aTotal; "total"
0x1400334c4  movdqu  xmmword ptr [rbp+var_18.Length], xmm0
0x1400334c9  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x1400334ce  test    al, al
0x1400334d0  jz      short loc_1400334DE
0x1400334d2  and     byte ptr [rbx+0D8h], 0FCh
0x1400334d9  jmp     loc_140033436
0x1400334de  movups  xmm0, xmmword ptr [rsi]
0x1400334e1  xor     r8d, r8d; unsigned __int8
0x1400334e4  lea     rdx, aAverage; "average"
0x1400334eb  lea     rcx, [rbp+var_18]; struct _UNICODE_STRING
0x1400334ef  movdqu  xmmword ptr [rbp+var_18.Length], xmm0
0x1400334f4  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x1400334f9  test    al, al
0x1400334fb  jz      short loc_140033510
0x1400334fd  and     byte ptr [rbx+0D8h], 0FDh
0x140033504  or      byte ptr [rbx+0D8h], 1
0x14003350b  jmp     loc_140033436
0x140033510  movups  xmm0, xmmword ptr [rsi]
0x140033513  xor     r8d, r8d; unsigned __int8
0x140033516  lea     rdx, aRate; "rate"
0x14003351d  lea     rcx, [rbp+var_18]; struct _UNICODE_STRING
0x140033521  movdqu  xmmword ptr [rbp+var_18.Length], xmm0
0x140033526  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x14003352b  test    al, al
0x14003352d  jz      short loc_140033542
0x14003352f  and     byte ptr [rbx+0D8h], 0FEh
0x140033536  or      byte ptr [rbx+0D8h], 2
0x14003353d  jmp     loc_140033436
0x140033542  mov     rax, [rdi]
0x140033545  lea     rdx, [rbp+arg_0]
0x140033549  mov     rcx, rdi
0x14003354c  mov     rax, [rax+0A8h]
0x140033553  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033558  mov     edx, [rbp+arg_0]
0x14003355b  mov     r8, rsi
0x14003355e  mov     ecx, 44Ch; unsigned int
0x140033563  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140033568  mov     eax, 0C007EE20h
0x14003356d  add     rsp, 38h
0x140033571  pop     rdi
0x140033572  pop     rsi
0x140033573  pop     rbx
0x140033574  pop     rbp
0x140033575  retn
```
