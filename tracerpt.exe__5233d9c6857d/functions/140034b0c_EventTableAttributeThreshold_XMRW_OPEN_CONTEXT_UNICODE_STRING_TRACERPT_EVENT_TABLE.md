# EventTableAttributeThreshold(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_EVENT_TABLE *)

- ea: `0x140034b0c`
- end: `0x140034bd2`
- name: `?EventTableAttributeThreshold@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_EVENT_TABLE@@@Z`
- size: `198`
- prototype: `unsigned int(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING *, struct _TRACERPT_EVENT_TABLE *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140034dc4`

## callees

- `0x140034b0c`
- `0x14003694c`
- `0x140037a74`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall EventTableAttributeThreshold(
        struct _XMRW_OPEN_CONTEXT *a1,
        struct _UNICODE_STRING *a2,
        struct _TRACERPT_EVENT_TABLE *a3)
{
  bool v3; // zf
  __int64 v5; // r11
  __int64 result; // rax
  unsigned int v8; // eax
  __int64 v9; // r11
  unsigned int v10; // esi
  unsigned int v11; // edi
  unsigned int v12; // [rsp+40h] [rbp+8h] BYREF
  unsigned int v13; // [rsp+50h] [rbp+18h] BYREF

  v3 = (*((_BYTE *)a3 + 680) & 0x20) == 0;
  v5 = *((_QWORD *)a1 + 3);
  v13 = 0;
  v12 = 0;
  if ( v3 )
  {
    v8 = StringToUlong(a2, &v13);
    v10 = v13;
    v11 = v8;
    if ( v8 == -1073222112 || !v13 )
    {
      (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v9 + 168LL))(v9, &v12);
      PrintMessage(0x416u, v12, a2);
    }
    if ( v11 )
    {
      return v11;
    }
    else
    {
      *((_BYTE *)a3 + 680) |= 0x20u;
      result = 0;
      *((_DWORD *)a3 + 50) = v10;
    }
  }
  else
  {
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v5 + 168LL))(v5, &v12);
    PrintMessage(0x415u, v12);
    return 3221745153LL;
  }
  return result;
}

```

## disassembly

```asm
0x140034b0c  mov     [rsp+arg_8], rbx
0x140034b11  push    rbp
0x140034b12  push    rsi
0x140034b13  push    rdi
0x140034b14  sub     rsp, 20h
0x140034b18  test    byte ptr [r8+2A8h], 20h
0x140034b20  mov     rbx, r8
0x140034b23  mov     r11, [rcx+18h]
0x140034b27  mov     rbp, rdx
0x140034b2a  mov     [rsp+38h+arg_10], 0
0x140034b32  mov     [rsp+38h+arg_0], 0
0x140034b3a  jz      short loc_140034B68
0x140034b3c  mov     rax, [r11]
0x140034b3f  lea     rdx, [rsp+38h+arg_0]
0x140034b44  mov     rcx, r11
0x140034b47  mov     rax, [rax+0A8h]
0x140034b4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034b53  mov     edx, [rsp+38h+arg_0]
0x140034b57  mov     ecx, 415h; unsigned int
0x140034b5c  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140034b61  mov     eax, 0C007EE01h
0x140034b66  jmp     short loc_140034BC5
0x140034b68  lea     rdx, [rsp+38h+arg_10]; unsigned int *
0x140034b6d  mov     rcx, rbp; struct _UNICODE_STRING *
0x140034b70  call    ?StringToUlong@@YAKAEAU_UNICODE_STRING@@PEAK@Z; StringToUlong(_UNICODE_STRING &,ulong *)
0x140034b75  mov     esi, [rsp+38h+arg_10]
0x140034b79  mov     edi, eax
0x140034b7b  cmp     eax, 0C007EE20h
0x140034b80  jz      short loc_140034B86
0x140034b82  test    esi, esi
0x140034b84  jnz     short loc_140034BAE
0x140034b86  mov     rcx, [r11]
0x140034b89  lea     rdx, [rsp+38h+arg_0]
0x140034b8e  mov     rax, [rcx+0A8h]
0x140034b95  mov     rcx, r11
0x140034b98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034b9d  mov     edx, [rsp+38h+arg_0]
0x140034ba1  mov     r8, rbp
0x140034ba4  mov     ecx, 416h; unsigned int
0x140034ba9  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140034bae  test    edi, edi
0x140034bb0  jz      short loc_140034BB6
0x140034bb2  mov     eax, edi
0x140034bb4  jmp     short loc_140034BC5
0x140034bb6  or      byte ptr [rbx+2A8h], 20h
0x140034bbd  xor     eax, eax
0x140034bbf  mov     [rbx+0C8h], esi
0x140034bc5  mov     rbx, [rsp+38h+arg_8]
0x140034bca  add     rsp, 20h
0x140034bce  pop     rdi
0x140034bcf  pop     rsi
0x140034bd0  pop     rbp
0x140034bd1  retn
```
