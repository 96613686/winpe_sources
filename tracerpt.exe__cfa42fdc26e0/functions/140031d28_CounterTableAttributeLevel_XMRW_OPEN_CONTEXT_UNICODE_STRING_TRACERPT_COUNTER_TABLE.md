# CounterTableAttributeLevel(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_COUNTER_TABLE *)

- ea: `0x140031d28`
- end: `0x140031df3`
- name: `?CounterTableAttributeLevel@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_COUNTER_TABLE@@@Z`
- size: `203`
- prototype: `__int64 __fastcall(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING *, struct _TRACERPT_COUNTER_TABLE *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140031fb8`

## callees

- `0x140031d28`
- `0x14003694c`
- `0x140037a74`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall CounterTableAttributeLevel(
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

  v3 = (*((_BYTE *)a3 + 220) & 0x10) == 0;
  v4 = *((_QWORD *)a1 + 3);
  v11 = 0;
  v10 = 0;
  if ( !v3 )
  {
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v4 + 168LL))(v4, &v10);
    PrintMessage(0x426u, v10);
    return 3221745153LL;
  }
  v7 = StringToUlong(a2, &v11);
  if ( v7 == -1073222112 )
  {
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v4 + 168LL))(v4, &v10);
    PrintMessage(0x427u, v10, a2);
    return v7;
  }
  if ( v7 )
    return v7;
  v9 = v11;
  *(_BYTE *)(v8 + 220) |= 0x10u;
  *(_DWORD *)(v8 + 208) = v9;
  return 0;
}

```

## disassembly

```asm
0x140031d28  mov     rax, rsp
0x140031d2b  mov     [rax+10h], rbx
0x140031d2f  mov     [rax+20h], rsi
0x140031d33  push    rdi
0x140031d34  sub     rsp, 20h
0x140031d38  test    byte ptr [r8+0DCh], 10h
0x140031d40  mov     r11, r8
0x140031d43  mov     rdi, [rcx+18h]
0x140031d47  mov     rsi, rdx
0x140031d4a  mov     dword ptr [rax+18h], 0
0x140031d51  mov     dword ptr [rax+8], 0
0x140031d58  jz      short loc_140031D86
0x140031d5a  mov     rax, [rdi]
0x140031d5d  lea     rdx, [rsp+28h+arg_0]
0x140031d62  mov     rcx, rdi
0x140031d65  mov     rax, [rax+0A8h]
0x140031d6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031d71  mov     edx, [rsp+28h+arg_0]
0x140031d75  mov     ecx, 426h; unsigned int
0x140031d7a  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140031d7f  mov     eax, 0C007EE01h
0x140031d84  jmp     short loc_140031DE3
0x140031d86  lea     rdx, [rsp+28h+arg_10]; unsigned int *
0x140031d8b  mov     rcx, rsi; struct _UNICODE_STRING *
0x140031d8e  call    ?StringToUlong@@YAKAEAU_UNICODE_STRING@@PEAK@Z; StringToUlong(_UNICODE_STRING &,ulong *)
0x140031d93  mov     ebx, eax
0x140031d95  cmp     eax, 0C007EE20h
0x140031d9a  jnz     short loc_140031DC6
0x140031d9c  mov     rcx, [rdi]
0x140031d9f  lea     rdx, [rsp+28h+arg_0]
0x140031da4  mov     rax, [rcx+0A8h]
0x140031dab  mov     rcx, rdi
0x140031dae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031db3  mov     edx, [rsp+28h+arg_0]
0x140031db7  mov     r8, rsi
0x140031dba  mov     ecx, 427h; unsigned int
0x140031dbf  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140031dc4  jmp     short loc_140031DCA
0x140031dc6  test    ebx, ebx
0x140031dc8  jz      short loc_140031DCE
0x140031dca  mov     eax, ebx
0x140031dcc  jmp     short loc_140031DE3
0x140031dce  mov     eax, [rsp+28h+arg_10]
0x140031dd2  or      byte ptr [r11+0DCh], 10h
0x140031dda  mov     [r11+0D0h], eax
0x140031de1  xor     eax, eax
0x140031de3  mov     rbx, [rsp+28h+arg_8]
0x140031de8  mov     rsi, [rsp+28h+arg_18]
0x140031ded  add     rsp, 20h
0x140031df1  pop     rdi
0x140031df2  retn
```
