# EventTableAttributeTitle(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_EVENT_TABLE *)

- ea: `0x140034bd8`
- end: `0x140034cc1`
- name: `?EventTableAttributeTitle@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_EVENT_TABLE@@@Z`
- size: `233`
- prototype: `unsigned int __fastcall(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING *, struct _TRACERPT_EVENT_TABLE *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140034dc4`

## callees

- `0x140030910`
- `0x140034bd8`
- `0x140035a14`
- `0x1400365a8`
- `0x14003694c`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall EventTableAttributeTitle(
        struct _XMRW_OPEN_CONTEXT *a1,
        struct _UNICODE_STRING *a2,
        struct _TRACERPT_EVENT_TABLE *a3)
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
  v6 = *((_BYTE *)a3 + 680);
  v7 = *((_QWORD *)a1 + 3);
  if ( (v6 & 1) != 0 )
  {
    (*(void (__fastcall **)(_QWORD, unsigned int *))(*(_QWORD *)v7 + 168LL))(*((_QWORD *)a1 + 3), &v9);
    PrintMessage(0x412u, v9);
    return 3221745153LL;
  }
  else
  {
    v8 = (char *)a3 + 72;
    *((_BYTE *)a3 + 680) = v6 | 1;
    *((_BYTE *)a3 + 104) = 1;
    RPT_STRING::operator=((char *)a3 + 72, a2);
    result = HashTable<RPT_STRING,0,0>::Find(v3 + 48, v8 + 8, &v10);
    if ( (_DWORD)result )
    {
      if ( (_DWORD)result == 1168 )
        return HashTable<RPT_STRING,0,0>::Insert(v3 + 48, v8);
    }
    else
    {
      (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v7 + 168LL))(v7, &v9);
      PrintMessage(0x411u, v9, a2);
      return 3221745155LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140034bd8  mov     [rsp+arg_8], rbx
0x140034bdd  push    rbp
0x140034bde  push    rsi
0x140034bdf  push    rdi
0x140034be0  sub     rsp, 20h
0x140034be4  mov     rsi, [rcx+48h]
0x140034be8  mov     rbp, rdx
0x140034beb  mov     [rsp+38h+arg_18], 0
0x140034bf4  mov     [rsp+38h+arg_0], 0
0x140034bfc  test    rsi, rsi
0x140034bff  jnz     short loc_140034C08
0x140034c01  xor     eax, eax
0x140034c03  jmp     loc_140034CB4
0x140034c08  mov     al, [r8+2A8h]
0x140034c0f  mov     rbx, [rcx+18h]
0x140034c13  test    al, 1
0x140034c15  jz      short loc_140034C43
0x140034c17  mov     rax, [rbx]
0x140034c1a  lea     rdx, [rsp+38h+arg_0]
0x140034c1f  mov     rcx, rbx
0x140034c22  mov     rax, [rax+0A8h]
0x140034c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034c2e  mov     edx, [rsp+38h+arg_0]
0x140034c32  mov     ecx, 412h; unsigned int
0x140034c37  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140034c3c  mov     eax, 0C007EE01h
0x140034c41  jmp     short loc_140034CB4
0x140034c43  lea     rdi, [r8+48h]
0x140034c47  or      al, 1
0x140034c49  mov     rcx, rdi
0x140034c4c  mov     [r8+2A8h], al
0x140034c53  mov     byte ptr [rdi+20h], 1
0x140034c57  call    ??4RPT_STRING@@QEAAPEBV0@AEAU_UNICODE_STRING@@@Z; RPT_STRING::operator=(_UNICODE_STRING &)
0x140034c5c  lea     rdx, [rdi+8]
0x140034c60  lea     r8, [rsp+38h+arg_18]
0x140034c65  lea     rcx, [rsi+30h]
0x140034c69  call    ?Find@?$HashTable@VRPT_STRING@@$0A@$0A@@@QEAAKPEAU_UNICODE_STRING@@PEAPEAVRPT_STRING@@@Z; HashTable<RPT_STRING,0,0>::Find(_UNICODE_STRING *,RPT_STRING * *)
0x140034c6e  test    eax, eax
0x140034c70  jz      short loc_140034C87
0x140034c72  cmp     eax, 490h
0x140034c77  jnz     short loc_140034CB4
0x140034c79  mov     rdx, rdi
0x140034c7c  lea     rcx, [rsi+30h]
0x140034c80  call    ?Insert@?$HashTable@VRPT_STRING@@$0A@$0A@@@QEAAKPEAVRPT_STRING@@@Z; HashTable<RPT_STRING,0,0>::Insert(RPT_STRING *)
0x140034c85  jmp     short loc_140034CB4
0x140034c87  mov     rax, [rbx]
0x140034c8a  lea     rdx, [rsp+38h+arg_0]
0x140034c8f  mov     rcx, rbx
0x140034c92  mov     rax, [rax+0A8h]
0x140034c99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034c9e  mov     edx, [rsp+38h+arg_0]
0x140034ca2  mov     r8, rbp
0x140034ca5  mov     ecx, 411h; unsigned int
0x140034caa  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140034caf  mov     eax, 0C007EE03h
0x140034cb4  mov     rbx, [rsp+38h+arg_8]
0x140034cb9  add     rsp, 20h
0x140034cbd  pop     rdi
0x140034cbe  pop     rsi
0x140034cbf  pop     rbp
0x140034cc0  retn
```
