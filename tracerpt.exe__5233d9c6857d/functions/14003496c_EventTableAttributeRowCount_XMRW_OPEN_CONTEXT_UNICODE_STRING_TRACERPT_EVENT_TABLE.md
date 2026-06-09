# EventTableAttributeRowCount(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_EVENT_TABLE *)

- ea: `0x14003496c`
- end: `0x140034a32`
- name: `?EventTableAttributeRowCount@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_EVENT_TABLE@@@Z`
- size: `198`
- prototype: `unsigned int(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING *, struct _TRACERPT_EVENT_TABLE *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140034dc4`

## callees

- `0x14003496c`
- `0x14003694c`
- `0x140037a74`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall EventTableAttributeRowCount(
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

  v3 = (*((_BYTE *)a3 + 681) & 8) == 0;
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
      PrintMessage(0x41Cu, v12, a2);
    }
    if ( v11 )
    {
      return v11;
    }
    else
    {
      *((_BYTE *)a3 + 681) |= 8u;
      result = 0;
      *((_DWORD *)a3 + 51) = v10;
    }
  }
  else
  {
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v5 + 168LL))(v5, &v12);
    PrintMessage(0x41Bu, v12);
    return 3221745153LL;
  }
  return result;
}

```

## disassembly

```asm
0x14003496c  mov     [rsp+arg_8], rbx
0x140034971  push    rbp
0x140034972  push    rsi
0x140034973  push    rdi
0x140034974  sub     rsp, 20h
0x140034978  test    byte ptr [r8+2A9h], 8
0x140034980  mov     rbx, r8
0x140034983  mov     r11, [rcx+18h]
0x140034987  mov     rbp, rdx
0x14003498a  mov     [rsp+38h+arg_10], 0
0x140034992  mov     [rsp+38h+arg_0], 0
0x14003499a  jz      short loc_1400349C8
0x14003499c  mov     rax, [r11]
0x14003499f  lea     rdx, [rsp+38h+arg_0]
0x1400349a4  mov     rcx, r11
0x1400349a7  mov     rax, [rax+0A8h]
0x1400349ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400349b3  mov     edx, [rsp+38h+arg_0]
0x1400349b7  mov     ecx, 41Bh; unsigned int
0x1400349bc  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x1400349c1  mov     eax, 0C007EE01h
0x1400349c6  jmp     short loc_140034A25
0x1400349c8  lea     rdx, [rsp+38h+arg_10]; unsigned int *
0x1400349cd  mov     rcx, rbp; struct _UNICODE_STRING *
0x1400349d0  call    ?StringToUlong@@YAKAEAU_UNICODE_STRING@@PEAK@Z; StringToUlong(_UNICODE_STRING &,ulong *)
0x1400349d5  mov     esi, [rsp+38h+arg_10]
0x1400349d9  mov     edi, eax
0x1400349db  cmp     eax, 0C007EE20h
0x1400349e0  jz      short loc_1400349E6
0x1400349e2  test    esi, esi
0x1400349e4  jnz     short loc_140034A0E
0x1400349e6  mov     rcx, [r11]
0x1400349e9  lea     rdx, [rsp+38h+arg_0]
0x1400349ee  mov     rax, [rcx+0A8h]
0x1400349f5  mov     rcx, r11
0x1400349f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400349fd  mov     edx, [rsp+38h+arg_0]
0x140034a01  mov     r8, rbp
0x140034a04  mov     ecx, 41Ch; unsigned int
0x140034a09  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140034a0e  test    edi, edi
0x140034a10  jz      short loc_140034A16
0x140034a12  mov     eax, edi
0x140034a14  jmp     short loc_140034A25
0x140034a16  or      byte ptr [rbx+2A9h], 8
0x140034a1d  xor     eax, eax
0x140034a1f  mov     [rbx+0CCh], esi
0x140034a25  mov     rbx, [rsp+38h+arg_8]
0x140034a2a  add     rsp, 20h
0x140034a2e  pop     rdi
0x140034a2f  pop     rsi
0x140034a30  pop     rbp
0x140034a31  retn
```
