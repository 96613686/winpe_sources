# EventTableAttributeKey(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_EVENT_TABLE *)

- ea: `0x1400347c4`
- end: `0x14003488f`
- name: `?EventTableAttributeKey@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_EVENT_TABLE@@@Z`
- size: `203`
- prototype: `unsigned int(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING *, struct _TRACERPT_EVENT_TABLE *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140034dc4`

## callees

- `0x1400347c4`
- `0x14003694c`
- `0x140037a74`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall EventTableAttributeKey(
        struct _XMRW_OPEN_CONTEXT *a1,
        struct _UNICODE_STRING *a2,
        struct _TRACERPT_EVENT_TABLE *a3)
{
  bool v3; // zf
  __int64 v4; // rdi
  unsigned int v7; // ebx
  __int64 v8; // r11
  unsigned int v9; // eax
  unsigned int v10; // [rsp+30h] [rbp+8h] BYREF
  unsigned int v11; // [rsp+40h] [rbp+18h] BYREF

  v3 = (*((_BYTE *)a3 + 680) & 0x10) == 0;
  v4 = *((_QWORD *)a1 + 3);
  v11 = 0;
  v10 = 0;
  if ( !v3 )
  {
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v4 + 168LL))(v4, &v10);
    PrintMessage(0x41Du, v10);
    return 3221745153LL;
  }
  v7 = StringToUlong(a2, &v11);
  if ( v7 == -1073222112 )
  {
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v4 + 168LL))(v4, &v10);
    PrintMessage(0x41Eu, v10, a2);
    return v7;
  }
  if ( v7 )
    return v7;
  v9 = v11;
  *(_BYTE *)(v8 + 680) |= 0x10u;
  *(_DWORD *)(v8 + 196) = v9;
  return 0;
}

```

## disassembly

```asm
0x1400347c4  mov     rax, rsp
0x1400347c7  mov     [rax+10h], rbx
0x1400347cb  mov     [rax+20h], rsi
0x1400347cf  push    rdi
0x1400347d0  sub     rsp, 20h
0x1400347d4  test    byte ptr [r8+2A8h], 10h
0x1400347dc  mov     r11, r8
0x1400347df  mov     rdi, [rcx+18h]
0x1400347e3  mov     rsi, rdx
0x1400347e6  mov     dword ptr [rax+18h], 0
0x1400347ed  mov     dword ptr [rax+8], 0
0x1400347f4  jz      short loc_140034822
0x1400347f6  mov     rax, [rdi]
0x1400347f9  lea     rdx, [rsp+28h+arg_0]
0x1400347fe  mov     rcx, rdi
0x140034801  mov     rax, [rax+0A8h]
0x140034808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003480d  mov     edx, [rsp+28h+arg_0]
0x140034811  mov     ecx, 41Dh; unsigned int
0x140034816  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x14003481b  mov     eax, 0C007EE01h
0x140034820  jmp     short loc_14003487F
0x140034822  lea     rdx, [rsp+28h+arg_10]; unsigned int *
0x140034827  mov     rcx, rsi; struct _UNICODE_STRING *
0x14003482a  call    ?StringToUlong@@YAKAEAU_UNICODE_STRING@@PEAK@Z; StringToUlong(_UNICODE_STRING &,ulong *)
0x14003482f  mov     ebx, eax
0x140034831  cmp     eax, 0C007EE20h
0x140034836  jnz     short loc_140034862
0x140034838  mov     rcx, [rdi]
0x14003483b  lea     rdx, [rsp+28h+arg_0]
0x140034840  mov     rax, [rcx+0A8h]
0x140034847  mov     rcx, rdi
0x14003484a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003484f  mov     edx, [rsp+28h+arg_0]
0x140034853  mov     r8, rsi
0x140034856  mov     ecx, 41Eh; unsigned int
0x14003485b  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140034860  jmp     short loc_140034866
0x140034862  test    ebx, ebx
0x140034864  jz      short loc_14003486A
0x140034866  mov     eax, ebx
0x140034868  jmp     short loc_14003487F
0x14003486a  mov     eax, [rsp+28h+arg_10]
0x14003486e  or      byte ptr [r11+2A8h], 10h
0x140034876  mov     [r11+0C4h], eax
0x14003487d  xor     eax, eax
0x14003487f  mov     rbx, [rsp+28h+arg_8]
0x140034884  mov     rsi, [rsp+28h+arg_18]
0x140034889  add     rsp, 20h
0x14003488d  pop     rdi
0x14003488e  retn
```
