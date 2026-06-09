# ExtensionUnitGetHandler

- ea: `0x140008500`
- end: `0x140008638`
- name: `ExtensionUnitGetHandler`
- size: `312`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x140008500`
- `0x140008640`
- `0x140008f80`

## pseudocode

```c
__int64 __fastcall ExtensionUnitGetHandler(__int64 a1, __int64 a2, unsigned __int8 *a3)
{
  unsigned __int16 v3; // di
  int NodeInfoAndValidate; // ecx
  __int64 v7; // r14
  __int64 v8; // r15
  char v9; // r12
  unsigned __int16 v10; // si
  __int64 v11; // rdi
  unsigned int v12; // ecx
  int v14; // [rsp+20h] [rbp-50h]
  int v15; // [rsp+20h] [rbp-50h]
  size_t Size; // [rsp+30h] [rbp-40h]
  size_t Sizea; // [rsp+30h] [rbp-40h]
  __int64 v18; // [rsp+50h] [rbp-20h] BYREF
  __int64 v19; // [rsp+58h] [rbp-18h] BYREF
  _BYTE v20[16]; // [rsp+60h] [rbp-10h] BYREF
  int v21; // [rsp+B0h] [rbp+40h] BYREF
  int v22; // [rsp+B8h] [rbp+48h] BYREF
  unsigned __int16 v23; // [rsp+C8h] [rbp+58h] BYREF

  v3 = *(_WORD *)(a2 + 16);
  LOBYTE(v21) = 0;
  LOBYTE(v22) = 0;
  v23 = 0;
  v19 = 0;
  v18 = 0;
  NodeInfoAndValidate = GetNodeInfoAndValidate(a1, a2, a3, v3, 9, &v21, &v22, &v19, &v18, v20);
  if ( NodeInfoAndValidate >= 0 )
  {
    v7 = v18;
    v8 = v19;
    v9 = v22;
    LODWORD(Size) = 2;
    v10 = v3 << 8;
    LOBYTE(v14) = v22;
    NodeInfoAndValidate = SubmitControlRequest(0xA1u, 0x85u, v3 << 8, v21, v14, (unsigned __int8 *)&v23, Size, v19, v18);
    if ( NodeInfoAndValidate >= 0 )
    {
      v11 = v23;
      v12 = *(_DWORD *)(*(_QWORD *)(a1 + 184) + 8LL);
      if ( !v12 )
      {
        NodeInfoAndValidate = -2147483643;
LABEL_6:
        *(_QWORD *)(a1 + 56) = v11;
        goto LABEL_7;
      }
      if ( v12 < v23 )
      {
        NodeInfoAndValidate = -1073741789;
        goto LABEL_7;
      }
      LODWORD(Sizea) = v23;
      LOBYTE(v15) = v9;
      NodeInfoAndValidate = SubmitControlRequest(0xA1u, 0x81u, v10, v21, v15, a3, Sizea, v8, v7);
      if ( NodeInfoAndValidate >= 0 )
        goto LABEL_6;
    }
  }
LABEL_7:
  *(_DWORD *)(a1 + 48) = NodeInfoAndValidate;
  return (unsigned int)NodeInfoAndValidate;
}

```

## disassembly

```asm
0x140008500  mov     r11, rsp
0x140008503  mov     [r11+18h], rbx
0x140008507  push    rbp
0x140008508  push    rsi
0x140008509  push    rdi
0x14000850a  push    r12
0x14000850c  push    r13
0x14000850e  push    r14
0x140008510  push    r15
0x140008512  mov     rbp, rsp
0x140008515  sub     rsp, 70h
0x140008519  movzx   edi, word ptr [rdx+10h]
0x14000851d  lea     rax, [rbp+var_10]
0x140008521  mov     [r11-60h], rax
0x140008525  xor     esi, esi
0x140008527  lea     rax, [rbp+var_20]
0x14000852b  mov     byte ptr [rbp+arg_0], sil
0x14000852f  mov     [r11-68h], rax
0x140008533  movzx   r9d, di
0x140008537  lea     rax, [rbp+var_18]
0x14000853b  mov     byte ptr [rbp+arg_8], sil
0x14000853f  mov     [r11-70h], rax
0x140008543  mov     r13, r8
0x140008546  lea     rax, [rbp+arg_8]
0x14000854a  mov     [rbp+arg_18], si
0x14000854e  mov     [r11-78h], rax
0x140008552  mov     rbx, rcx
0x140008555  lea     rax, [rbp+arg_0]
0x140008559  mov     [rbp+var_18], rsi
0x14000855d  mov     [r11-80h], rax
0x140008561  mov     byte ptr [rsp+70h+var_50], 9
0x140008566  mov     [rbp+var_20], rsi
0x14000856a  call    GetNodeInfoAndValidate
0x14000856f  mov     ecx, eax
0x140008571  test    eax, eax
0x140008573  js      loc_14000860C
0x140008579  mov     r14, [rbp+var_20]
0x14000857d  lea     rax, [rbp+arg_18]
0x140008581  mov     r15, [rbp+var_18]
0x140008585  mov     dl, 85h; int
0x140008587  mov     r12b, byte ptr [rbp+arg_8]
0x14000858b  mov     cl, 0A1h; int
0x14000858d  mov     r9b, byte ptr [rbp+arg_0]; int
0x140008591  mov     [rsp+70h+var_30], r14; __int64
0x140008596  mov     [rsp+70h+var_38], r15; __int64
0x14000859b  shl     di, 8
0x14000859f  mov     dword ptr [rsp+70h+Size], 2; Size
0x1400085a7  movzx   r8d, di; int
0x1400085ab  mov     [rsp+70h+var_48], rax; void *
0x1400085b0  movzx   esi, di
0x1400085b3  mov     byte ptr [rsp+70h+var_50], r12b; int
0x1400085b8  call    SubmitControlRequest
0x1400085bd  mov     ecx, eax
0x1400085bf  test    eax, eax
0x1400085c1  js      short loc_14000860C
0x1400085c3  mov     rax, [rbx+0B8h]
0x1400085ca  movzx   edi, [rbp+arg_18]
0x1400085ce  mov     ecx, [rax+8]
0x1400085d1  test    ecx, ecx
0x1400085d3  jz      short loc_14000862A
0x1400085d5  cmp     ecx, edi
0x1400085d7  jb      short loc_140008631
0x1400085d9  mov     r9b, byte ptr [rbp+arg_0]; int
0x1400085dd  movzx   r8d, si; int
0x1400085e1  mov     [rsp+70h+var_30], r14; __int64
0x1400085e6  mov     dl, 81h; int
0x1400085e8  mov     [rsp+70h+var_38], r15; __int64
0x1400085ed  mov     cl, 0A1h; int
0x1400085ef  mov     dword ptr [rsp+70h+Size], edi; Size
0x1400085f3  mov     [rsp+70h+var_48], r13; void *
0x1400085f8  mov     byte ptr [rsp+70h+var_50], r12b; int
0x1400085fd  call    SubmitControlRequest
0x140008602  mov     ecx, eax
0x140008604  test    eax, eax
0x140008606  js      short loc_14000860C
0x140008608  mov     [rbx+38h], rdi
0x14000860c  mov     [rbx+30h], ecx
0x14000860f  mov     eax, ecx
0x140008611  mov     rbx, [rsp+70h+arg_10]
0x140008619  add     rsp, 70h
0x14000861d  pop     r15
0x14000861f  pop     r14
0x140008621  pop     r13
0x140008623  pop     r12
0x140008625  pop     rdi
0x140008626  pop     rsi
0x140008627  pop     rbp
0x140008628  retn
0x14000862a  mov     ecx, 80000005h
0x14000862f  jmp     short loc_140008608
0x140008631  mov     ecx, 0C0000023h
0x140008636  jmp     short loc_14000860C
```
