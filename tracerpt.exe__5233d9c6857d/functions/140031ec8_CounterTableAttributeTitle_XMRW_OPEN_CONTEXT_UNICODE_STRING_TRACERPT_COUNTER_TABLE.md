# CounterTableAttributeTitle(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_COUNTER_TABLE *)

- ea: `0x140031ec8`
- end: `0x140031fb1`
- name: `?CounterTableAttributeTitle@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_COUNTER_TABLE@@@Z`
- size: `233`
- prototype: `unsigned int __fastcall(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING *, struct _TRACERPT_COUNTER_TABLE *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140031fb8`

## callees

- `0x140030910`
- `0x140031ec8`
- `0x140035a14`
- `0x1400365a8`
- `0x14003694c`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall CounterTableAttributeTitle(
        struct _XMRW_OPEN_CONTEXT *a1,
        struct _UNICODE_STRING *a2,
        struct _TRACERPT_COUNTER_TABLE *a3)
{
  __int64 v3; // rsi
  __int64 result; // rax
  char v6; // al
  __int64 v7; // rbx
  char *v8; // rdi
  unsigned int v9; // [rsp+40h] [rbp+8h] BYREF
  __int64 v10; // [rsp+58h] [rbp+20h] BYREF

  v3 = *((_QWORD *)a1 + 9);
  v10 = 0;
  v9 = 0;
  if ( !v3 )
    return 0;
  v6 = *((_BYTE *)a3 + 220);
  v7 = *((_QWORD *)a1 + 3);
  if ( (v6 & 1) != 0 )
  {
    (*(void (__fastcall **)(_QWORD, unsigned int *))(*(_QWORD *)v7 + 168LL))(*((_QWORD *)a1 + 3), &v9);
    PrintMessage(0x420u, v9);
    return 3221745153LL;
  }
  else
  {
    v8 = (char *)a3 + 48;
    *((_BYTE *)a3 + 220) = v6 | 1;
    *((_BYTE *)a3 + 80) = 1;
    RPT_STRING::operator=((char *)a3 + 48, a2);
    result = HashTable<RPT_STRING,0,0>::Find(v3 + 48, v8 + 8, &v10);
    if ( (_DWORD)result )
    {
      if ( (_DWORD)result == 1168 )
        return HashTable<RPT_STRING,0,0>::Insert(v3 + 48, v8);
    }
    else
    {
      (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v7 + 168LL))(v7, &v9);
      PrintMessage(0x421u, v9, a2);
      return 3221745155LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140031ec8  mov     [rsp+arg_8], rbx
0x140031ecd  push    rbp
0x140031ece  push    rsi
0x140031ecf  push    rdi
0x140031ed0  sub     rsp, 20h
0x140031ed4  mov     rsi, [rcx+48h]
0x140031ed8  mov     rbp, rdx
0x140031edb  mov     [rsp+38h+arg_18], 0
0x140031ee4  mov     [rsp+38h+arg_0], 0
0x140031eec  test    rsi, rsi
0x140031eef  jnz     short loc_140031EF8
0x140031ef1  xor     eax, eax
0x140031ef3  jmp     loc_140031FA4
0x140031ef8  mov     al, [r8+0DCh]
0x140031eff  mov     rbx, [rcx+18h]
0x140031f03  test    al, 1
0x140031f05  jz      short loc_140031F33
0x140031f07  mov     rax, [rbx]
0x140031f0a  lea     rdx, [rsp+38h+arg_0]
0x140031f0f  mov     rcx, rbx
0x140031f12  mov     rax, [rax+0A8h]
0x140031f19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031f1e  mov     edx, [rsp+38h+arg_0]
0x140031f22  mov     ecx, 420h; unsigned int
0x140031f27  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140031f2c  mov     eax, 0C007EE01h
0x140031f31  jmp     short loc_140031FA4
0x140031f33  lea     rdi, [r8+30h]
0x140031f37  or      al, 1
0x140031f39  mov     rcx, rdi
0x140031f3c  mov     [r8+0DCh], al
0x140031f43  mov     byte ptr [rdi+20h], 1
0x140031f47  call    ??4RPT_STRING@@QEAAPEBV0@AEAU_UNICODE_STRING@@@Z; RPT_STRING::operator=(_UNICODE_STRING &)
0x140031f4c  lea     rdx, [rdi+8]
0x140031f50  lea     r8, [rsp+38h+arg_18]
0x140031f55  lea     rcx, [rsi+30h]
0x140031f59  call    ?Find@?$HashTable@VRPT_STRING@@$0A@$0A@@@QEAAKPEAU_UNICODE_STRING@@PEAPEAVRPT_STRING@@@Z; HashTable<RPT_STRING,0,0>::Find(_UNICODE_STRING *,RPT_STRING * *)
0x140031f5e  test    eax, eax
0x140031f60  jz      short loc_140031F77
0x140031f62  cmp     eax, 490h
0x140031f67  jnz     short loc_140031FA4
0x140031f69  mov     rdx, rdi
0x140031f6c  lea     rcx, [rsi+30h]
0x140031f70  call    ?Insert@?$HashTable@VRPT_STRING@@$0A@$0A@@@QEAAKPEAVRPT_STRING@@@Z; HashTable<RPT_STRING,0,0>::Insert(RPT_STRING *)
0x140031f75  jmp     short loc_140031FA4
0x140031f77  mov     rax, [rbx]
0x140031f7a  lea     rdx, [rsp+38h+arg_0]
0x140031f7f  mov     rcx, rbx
0x140031f82  mov     rax, [rax+0A8h]
0x140031f89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031f8e  mov     edx, [rsp+38h+arg_0]
0x140031f92  mov     r8, rbp
0x140031f95  mov     ecx, 421h; unsigned int
0x140031f9a  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140031f9f  mov     eax, 0C007EE03h
0x140031fa4  mov     rbx, [rsp+38h+arg_8]
0x140031fa9  add     rsp, 20h
0x140031fad  pop     rdi
0x140031fae  pop     rsi
0x140031faf  pop     rbp
0x140031fb0  retn
```
