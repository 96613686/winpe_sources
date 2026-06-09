# EventFieldAttributeEventID(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_FIELD *)

- ea: `0x14003357c`
- end: `0x140033646`
- name: `?EventFieldAttributeEventID@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_FIELD@@@Z`
- size: `202`
- prototype: `unsigned int(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING *, struct _TRACERPT_FIELD *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400339c8`

## callees

- `0x14003357c`
- `0x14003694c`
- `0x140037a74`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall EventFieldAttributeEventID(
        struct _XMRW_OPEN_CONTEXT *a1,
        struct _UNICODE_STRING *a2,
        struct _TRACERPT_FIELD *a3)
{
  bool v3; // zf
  __int64 v4; // rdi
  unsigned int v7; // ebx
  __int64 v8; // r11
  __int16 v9; // ax
  unsigned int v10; // [rsp+30h] [rbp+8h] BYREF
  unsigned int v11; // [rsp+40h] [rbp+18h] BYREF

  v3 = (*((_BYTE *)a3 + 216) & 8) == 0;
  v4 = *((_QWORD *)a1 + 3);
  v11 = 0;
  v10 = 0;
  if ( !v3 )
  {
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v4 + 168LL))(v4, &v10);
    PrintMessage(0x446u, v10);
    return 3221745153LL;
  }
  v7 = StringToUlong(a2, &v11);
  if ( v7 == -1073222112 )
  {
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v4 + 168LL))(v4, &v10);
    PrintMessage(0x447u, v10, a2);
    return v7;
  }
  if ( v7 )
    return v7;
  v9 = v11;
  *(_BYTE *)(v8 + 216) |= 8u;
  *(_WORD *)(v8 + 96) = v9;
  return 0;
}

```

## disassembly

```asm
0x14003357c  mov     rax, rsp
0x14003357f  mov     [rax+10h], rbx
0x140033583  mov     [rax+20h], rsi
0x140033587  push    rdi
0x140033588  sub     rsp, 20h
0x14003358c  test    byte ptr [r8+0D8h], 8
0x140033594  mov     r11, r8
0x140033597  mov     rdi, [rcx+18h]
0x14003359b  mov     rsi, rdx
0x14003359e  mov     dword ptr [rax+18h], 0
0x1400335a5  mov     dword ptr [rax+8], 0
0x1400335ac  jz      short loc_1400335DA
0x1400335ae  mov     rax, [rdi]
0x1400335b1  lea     rdx, [rsp+28h+arg_0]
0x1400335b6  mov     rcx, rdi
0x1400335b9  mov     rax, [rax+0A8h]
0x1400335c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400335c5  mov     edx, [rsp+28h+arg_0]
0x1400335c9  mov     ecx, 446h; unsigned int
0x1400335ce  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x1400335d3  mov     eax, 0C007EE01h
0x1400335d8  jmp     short loc_140033636
0x1400335da  lea     rdx, [rsp+28h+arg_10]; unsigned int *
0x1400335df  mov     rcx, rsi; struct _UNICODE_STRING *
0x1400335e2  call    ?StringToUlong@@YAKAEAU_UNICODE_STRING@@PEAK@Z; StringToUlong(_UNICODE_STRING &,ulong *)
0x1400335e7  mov     ebx, eax
0x1400335e9  cmp     eax, 0C007EE20h
0x1400335ee  jnz     short loc_14003361A
0x1400335f0  mov     rcx, [rdi]
0x1400335f3  lea     rdx, [rsp+28h+arg_0]
0x1400335f8  mov     rax, [rcx+0A8h]
0x1400335ff  mov     rcx, rdi
0x140033602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033607  mov     edx, [rsp+28h+arg_0]
0x14003360b  mov     r8, rsi
0x14003360e  mov     ecx, 447h; unsigned int
0x140033613  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140033618  jmp     short loc_14003361E
0x14003361a  test    ebx, ebx
0x14003361c  jz      short loc_140033622
0x14003361e  mov     eax, ebx
0x140033620  jmp     short loc_140033636
0x140033622  movzx   eax, word ptr [rsp+28h+arg_10]
0x140033627  or      byte ptr [r11+0D8h], 8
0x14003362f  mov     [r11+60h], ax
0x140033634  xor     eax, eax
0x140033636  mov     rbx, [rsp+28h+arg_8]
0x14003363b  mov     rsi, [rsp+28h+arg_18]
0x140033640  add     rsp, 20h
0x140033644  pop     rdi
0x140033645  retn
```
