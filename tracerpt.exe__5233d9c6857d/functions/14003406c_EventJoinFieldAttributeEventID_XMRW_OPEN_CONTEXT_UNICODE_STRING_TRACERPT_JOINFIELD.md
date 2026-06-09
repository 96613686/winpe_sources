# EventJoinFieldAttributeEventID(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_JOINFIELD *)

- ea: `0x14003406c`
- end: `0x140034136`
- name: `?EventJoinFieldAttributeEventID@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_JOINFIELD@@@Z`
- size: `202`
- prototype: `unsigned int(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING *, struct _TRACERPT_JOINFIELD *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14003451c`

## callees

- `0x14003406c`
- `0x14003694c`
- `0x140037a74`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall EventJoinFieldAttributeEventID(
        struct _XMRW_OPEN_CONTEXT *a1,
        struct _UNICODE_STRING *a2,
        struct _TRACERPT_JOINFIELD *a3)
{
  bool v3; // zf
  __int64 v4; // rdi
  unsigned int v7; // ebx
  __int64 v8; // r11
  __int16 v9; // ax
  unsigned int v10; // [rsp+30h] [rbp+8h] BYREF
  unsigned int v11; // [rsp+40h] [rbp+18h] BYREF

  v3 = (*((_BYTE *)a3 + 176) & 2) == 0;
  v4 = *((_QWORD *)a1 + 3);
  v11 = 0;
  v10 = 0;
  if ( !v3 )
  {
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v4 + 168LL))(v4, &v10);
    PrintMessage(0x454u, v10);
    return 3221745153LL;
  }
  v7 = StringToUlong(a2, &v11);
  if ( v7 == -1073222112 )
  {
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v4 + 168LL))(v4, &v10);
    PrintMessage(0x455u, v10, a2);
    return v7;
  }
  if ( v7 )
    return v7;
  v9 = v11;
  *(_BYTE *)(v8 + 176) |= 2u;
  *(_WORD *)(v8 + 56) = v9;
  return 0;
}

```

## disassembly

```asm
0x14003406c  mov     rax, rsp
0x14003406f  mov     [rax+10h], rbx
0x140034073  mov     [rax+20h], rsi
0x140034077  push    rdi
0x140034078  sub     rsp, 20h
0x14003407c  test    byte ptr [r8+0B0h], 2
0x140034084  mov     r11, r8
0x140034087  mov     rdi, [rcx+18h]
0x14003408b  mov     rsi, rdx
0x14003408e  mov     dword ptr [rax+18h], 0
0x140034095  mov     dword ptr [rax+8], 0
0x14003409c  jz      short loc_1400340CA
0x14003409e  mov     rax, [rdi]
0x1400340a1  lea     rdx, [rsp+28h+arg_0]
0x1400340a6  mov     rcx, rdi
0x1400340a9  mov     rax, [rax+0A8h]
0x1400340b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400340b5  mov     edx, [rsp+28h+arg_0]
0x1400340b9  mov     ecx, 454h; unsigned int
0x1400340be  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x1400340c3  mov     eax, 0C007EE01h
0x1400340c8  jmp     short loc_140034126
0x1400340ca  lea     rdx, [rsp+28h+arg_10]; unsigned int *
0x1400340cf  mov     rcx, rsi; struct _UNICODE_STRING *
0x1400340d2  call    ?StringToUlong@@YAKAEAU_UNICODE_STRING@@PEAK@Z; StringToUlong(_UNICODE_STRING &,ulong *)
0x1400340d7  mov     ebx, eax
0x1400340d9  cmp     eax, 0C007EE20h
0x1400340de  jnz     short loc_14003410A
0x1400340e0  mov     rcx, [rdi]
0x1400340e3  lea     rdx, [rsp+28h+arg_0]
0x1400340e8  mov     rax, [rcx+0A8h]
0x1400340ef  mov     rcx, rdi
0x1400340f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400340f7  mov     edx, [rsp+28h+arg_0]
0x1400340fb  mov     r8, rsi
0x1400340fe  mov     ecx, 455h; unsigned int
0x140034103  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140034108  jmp     short loc_14003410E
0x14003410a  test    ebx, ebx
0x14003410c  jz      short loc_140034112
0x14003410e  mov     eax, ebx
0x140034110  jmp     short loc_140034126
0x140034112  movzx   eax, word ptr [rsp+28h+arg_10]
0x140034117  or      byte ptr [r11+0B0h], 2
0x14003411f  mov     [r11+38h], ax
0x140034124  xor     eax, eax
0x140034126  mov     rbx, [rsp+28h+arg_8]
0x14003412b  mov     rsi, [rsp+28h+arg_18]
0x140034130  add     rsp, 20h
0x140034134  pop     rdi
0x140034135  retn
```
