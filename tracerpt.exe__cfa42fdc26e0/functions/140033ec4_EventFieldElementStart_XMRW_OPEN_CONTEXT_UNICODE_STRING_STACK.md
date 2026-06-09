# EventFieldElementStart(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING_STACK *)

- ea: `0x140033ec4`
- end: `0x140034063`
- name: `?EventFieldElementStart@@YAKPEAU_XMRW_OPEN_CONTEXT@@PEAU_UNICODE_STRING_STACK@@@Z`
- size: `415`
- prototype: `int __fastcall(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING_STACK *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140032dcc`

## callees

- `0x140016808`
- `0x1400339c8`
- `0x140033ec4`
- `0x14003694c`
- `0x140041010`

## pseudocode

```c
int __fastcall EventFieldElementStart(struct _XMRW_OPEN_CONTEXT *a1, struct _UNICODE_STRING_STACK *a2)
{
  __int64 v2; // rdi
  __int64 v4; // rbx
  char v5; // al
  int result; // eax
  struct _UNICODE_STRING v7; // [rsp+20h] [rbp-20h] BYREF
  struct _UNICODE_STRING v8; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v9; // [rsp+60h] [rbp+20h] BYREF
  int v10; // [rsp+70h] [rbp+30h] BYREF
  WCHAR *v11; // [rsp+78h] [rbp+38h] BYREF

  v2 = *((_QWORD *)a1 + 12);
  v11 = 0;
  v10 = 0;
  v9 = 0;
  v7 = 0;
  if ( !v2 )
    return 0;
  if ( !a2 )
    return 0;
  if ( (unsigned int)(*((_DWORD *)a1 + 12) - 6) > 1 )
    return 0;
  v4 = *((_QWORD *)a1 + 3);
  v8 = *(struct _UNICODE_STRING *)((char *)a2 + 8);
  if ( !EqualString(&v8, L"Column", 0) )
    return 0;
  v5 = *(_BYTE *)(v2 + 370);
  if ( (v5 & 1) != 0 )
  {
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v4 + 168LL))(v4, &v9);
    PrintMessage(0x44Eu, v9);
    return -1073222073;
  }
  *(_BYTE *)(v2 + 370) = v5 | 1;
  for ( result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 64LL))(v4);
        !result;
        result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 72LL))(v4) )
  {
    ++*((_DWORD *)a1 + 11);
    (*(void (__fastcall **)(__int64, WCHAR **, int *))(*(_QWORD *)v4 + 112LL))(v4, &v11, &v10);
    v7.Buffer = v11;
    v7.MaximumLength = 2 * v10;
    v7.Length = 2 * v10;
    result = EventFieldAttributesCheck(a1, &v7, (struct _TRACERPT_FIELD *)(v2 + 136));
    if ( result )
      return result;
  }
  if ( result >= 0 )
  {
    if ( (*(_BYTE *)(v2 + 352) & 0x2C) != 0x2C )
    {
      (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v4 + 168LL))(v4, &v9);
      if ( (*(_BYTE *)(v2 + 352) & 0x20) == 0 )
        PrintMessage(0x3FDu, v9);
      if ( (*(_BYTE *)(v2 + 352) & 4) == 0 )
        PrintMessage(0x403u, v9);
      if ( (*(_BYTE *)(v2 + 352) & 8) == 0 )
        PrintMessage(0x404u, v9);
      return -1073222127;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140033ec4  mov     [rsp-18h+arg_8], rbx
0x140033ec9  push    rbp
0x140033eca  push    rsi
0x140033ecb  push    rdi
0x140033ecc  mov     rbp, rsp
0x140033ecf  sub     rsp, 40h
0x140033ed3  mov     rdi, [rcx+60h]
0x140033ed7  xorps   xmm0, xmm0
0x140033eda  mov     [rbp+arg_18], 0
0x140033ee2  mov     rsi, rcx
0x140033ee5  mov     [rbp+arg_10], 0
0x140033eec  mov     [rbp+arg_0], 0
0x140033ef3  movups  xmmword ptr [rbp+var_20.Length], xmm0
0x140033ef7  test    rdi, rdi
0x140033efa  jz      loc_140034054
0x140033f00  test    rdx, rdx
0x140033f03  jz      loc_140034054
0x140033f09  mov     eax, [rcx+30h]
0x140033f0c  sub     eax, 6
0x140033f0f  cmp     eax, 1
0x140033f12  ja      loc_140034054
0x140033f18  movups  xmm0, xmmword ptr [rdx+8]
0x140033f1c  mov     rbx, [rcx+18h]
0x140033f20  lea     rdx, aColumn_0; "Column"
0x140033f27  xor     r8d, r8d; unsigned __int8
0x140033f2a  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140033f2e  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140033f33  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140033f38  test    al, al
0x140033f3a  jz      loc_140034054
0x140033f40  mov     al, [rdi+172h]
0x140033f46  mov     rcx, rbx
0x140033f49  test    al, 1
0x140033f4b  jz      short loc_140033F77
0x140033f4d  mov     rax, [rbx]
0x140033f50  lea     rdx, [rbp+arg_0]
0x140033f54  mov     rax, [rax+0A8h]
0x140033f5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033f60  mov     edx, [rbp+arg_0]
0x140033f63  mov     ecx, 44Eh; unsigned int
0x140033f68  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140033f6d  mov     eax, 0C007EE47h
0x140033f72  jmp     loc_140034056
0x140033f77  or      al, 1
0x140033f79  mov     [rdi+172h], al
0x140033f7f  mov     rax, [rbx]
0x140033f82  mov     rax, [rax+40h]
0x140033f86  jmp     short loc_140033FDE
0x140033f88  inc     dword ptr [rsi+2Ch]
0x140033f8b  lea     r8, [rbp+arg_10]
0x140033f8f  mov     rax, [rbx]
0x140033f92  lea     rdx, [rbp+arg_18]
0x140033f96  mov     rcx, rbx
0x140033f99  mov     rax, [rax+70h]
0x140033f9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033fa2  mov     rax, [rbp+arg_18]
0x140033fa6  lea     r8, [rdi+88h]; struct _TRACERPT_FIELD *
0x140033fad  mov     [rbp+var_20.Buffer], rax
0x140033fb1  lea     rdx, [rbp+var_20]; struct _UNICODE_STRING *
0x140033fb5  movzx   eax, word ptr [rbp+arg_10]
0x140033fb9  mov     rcx, rsi; struct _XMRW_OPEN_CONTEXT *
0x140033fbc  add     ax, ax
0x140033fbf  mov     [rbp+var_20.MaximumLength], ax
0x140033fc3  mov     [rbp+var_20.Length], ax
0x140033fc7  call    ?EventFieldAttributesCheck@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_FIELD@@@Z; EventFieldAttributesCheck(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_FIELD *)
0x140033fcc  test    eax, eax
0x140033fce  jnz     loc_140034056
0x140033fd4  mov     rax, [rbx]
0x140033fd7  mov     rcx, rbx
0x140033fda  mov     rax, [rax+48h]
0x140033fde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033fe3  test    eax, eax
0x140033fe5  jz      short loc_140033F88
0x140033fe7  js      short loc_140034056
0x140033fe9  mov     al, [rdi+160h]
0x140033fef  and     al, 2Ch
0x140033ff1  cmp     al, 2Ch ; ','
0x140033ff3  jz      short loc_140034054
0x140033ff5  mov     rax, [rbx]
0x140033ff8  lea     rdx, [rbp+arg_0]
0x140033ffc  mov     rcx, rbx
0x140033fff  mov     rax, [rax+0A8h]
0x140034006  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003400b  test    byte ptr [rdi+160h], 20h
0x140034012  jnz     short loc_140034021
0x140034014  mov     edx, [rbp+arg_0]
0x140034017  mov     ecx, 3FDh; unsigned int
0x14003401c  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140034021  test    byte ptr [rdi+160h], 4
0x140034028  jnz     short loc_140034037
0x14003402a  mov     edx, [rbp+arg_0]
0x14003402d  mov     ecx, 403h; unsigned int
0x140034032  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140034037  test    byte ptr [rdi+160h], 8
0x14003403e  jnz     short loc_14003404D
0x140034040  mov     edx, [rbp+arg_0]
0x140034043  mov     ecx, 404h; unsigned int
0x140034048  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x14003404d  mov     eax, 0C007EE11h
0x140034052  jmp     short loc_140034056
0x140034054  xor     eax, eax
0x140034056  mov     rbx, [rsp+40h+arg_8]
0x14003405b  add     rsp, 40h
0x14003405f  pop     rdi
0x140034060  pop     rsi
0x140034061  pop     rbp
0x140034062  retn
```
