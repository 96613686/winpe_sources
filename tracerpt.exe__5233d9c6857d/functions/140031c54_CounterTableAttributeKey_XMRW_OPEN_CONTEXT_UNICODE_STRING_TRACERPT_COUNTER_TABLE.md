# CounterTableAttributeKey(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_COUNTER_TABLE *)

- ea: `0x140031c54`
- end: `0x140031d1f`
- name: `?CounterTableAttributeKey@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_COUNTER_TABLE@@@Z`
- size: `203`
- prototype: `unsigned int(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING *, struct _TRACERPT_COUNTER_TABLE *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140031fb8`

## callees

- `0x140031c54`
- `0x14003694c`
- `0x140037a74`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall CounterTableAttributeKey(
        struct _XMRW_OPEN_CONTEXT *a1,
        struct _UNICODE_STRING *a2,
        struct _TRACERPT_COUNTER_TABLE *a3)
{
  bool v3; // zf
  __int64 v4; // rdi
  unsigned int v7; // ebx
  __int64 v8; // r11
  unsigned int v9; // eax
  unsigned int v10; // [rsp+30h] [rbp+8h] BYREF
  unsigned int v11; // [rsp+40h] [rbp+18h] BYREF

  v3 = (*((_BYTE *)a3 + 220) & 0x20) == 0;
  v4 = *((_QWORD *)a1 + 3);
  v11 = 0;
  v10 = 0;
  if ( !v3 )
  {
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v4 + 168LL))(v4, &v10);
    PrintMessage(0x424u, v10);
    return 3221745153LL;
  }
  v7 = StringToUlong(a2, &v11);
  if ( v7 == -1073222112 )
  {
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v4 + 168LL))(v4, &v10);
    PrintMessage(0x425u, v10, a2);
    return v7;
  }
  if ( v7 )
    return v7;
  v9 = v11;
  *(_BYTE *)(v8 + 220) |= 0x20u;
  *(_DWORD *)(v8 + 212) = v9;
  return 0;
}

```

## disassembly

```asm
0x140031c54  mov     rax, rsp
0x140031c57  mov     [rax+10h], rbx
0x140031c5b  mov     [rax+20h], rsi
0x140031c5f  push    rdi
0x140031c60  sub     rsp, 20h
0x140031c64  test    byte ptr [r8+0DCh], 20h
0x140031c6c  mov     r11, r8
0x140031c6f  mov     rdi, [rcx+18h]
0x140031c73  mov     rsi, rdx
0x140031c76  mov     dword ptr [rax+18h], 0
0x140031c7d  mov     dword ptr [rax+8], 0
0x140031c84  jz      short loc_140031CB2
0x140031c86  mov     rax, [rdi]
0x140031c89  lea     rdx, [rsp+28h+arg_0]
0x140031c8e  mov     rcx, rdi
0x140031c91  mov     rax, [rax+0A8h]
0x140031c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031c9d  mov     edx, [rsp+28h+arg_0]
0x140031ca1  mov     ecx, 424h; unsigned int
0x140031ca6  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140031cab  mov     eax, 0C007EE01h
0x140031cb0  jmp     short loc_140031D0F
0x140031cb2  lea     rdx, [rsp+28h+arg_10]; unsigned int *
0x140031cb7  mov     rcx, rsi; struct _UNICODE_STRING *
0x140031cba  call    ?StringToUlong@@YAKAEAU_UNICODE_STRING@@PEAK@Z; StringToUlong(_UNICODE_STRING &,ulong *)
0x140031cbf  mov     ebx, eax
0x140031cc1  cmp     eax, 0C007EE20h
0x140031cc6  jnz     short loc_140031CF2
0x140031cc8  mov     rcx, [rdi]
0x140031ccb  lea     rdx, [rsp+28h+arg_0]
0x140031cd0  mov     rax, [rcx+0A8h]
0x140031cd7  mov     rcx, rdi
0x140031cda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031cdf  mov     edx, [rsp+28h+arg_0]
0x140031ce3  mov     r8, rsi
0x140031ce6  mov     ecx, 425h; unsigned int
0x140031ceb  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140031cf0  jmp     short loc_140031CF6
0x140031cf2  test    ebx, ebx
0x140031cf4  jz      short loc_140031CFA
0x140031cf6  mov     eax, ebx
0x140031cf8  jmp     short loc_140031D0F
0x140031cfa  mov     eax, [rsp+28h+arg_10]
0x140031cfe  or      byte ptr [r11+0DCh], 20h
0x140031d06  mov     [r11+0D4h], eax
0x140031d0d  xor     eax, eax
0x140031d0f  mov     rbx, [rsp+28h+arg_8]
0x140031d14  mov     rsi, [rsp+28h+arg_18]
0x140031d19  add     rsp, 20h
0x140031d1d  pop     rdi
0x140031d1e  retn
```
