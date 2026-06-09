# EventTableAttributeTask(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_EVENT_TABLE *)

- ea: `0x140034a38`
- end: `0x140034b05`
- name: `?EventTableAttributeTask@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_EVENT_TABLE@@@Z`
- size: `205`
- prototype: `unsigned int(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING *, struct _TRACERPT_EVENT_TABLE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140034dc4`

## callees

- `0x140034a38`
- `0x14003694c`
- `0x140037a74`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall EventTableAttributeTask(
        struct _XMRW_OPEN_CONTEXT *a1,
        struct _UNICODE_STRING *a2,
        struct _TRACERPT_EVENT_TABLE *a3)
{
  bool v3; // sf
  __int64 v4; // rdi
  unsigned int v7; // ebx
  __int64 v8; // r11
  __int16 v9; // ax
  unsigned int v10; // [rsp+30h] [rbp+8h] BYREF
  unsigned int v11; // [rsp+40h] [rbp+18h] BYREF

  v3 = *((char *)a3 + 680) < 0;
  v4 = *((_QWORD *)a1 + 3);
  v11 = 0;
  v10 = 0;
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v4 + 168LL))(v4, &v10);
    PrintMessage(0x419u, v10);
    return 3221745153LL;
  }
  v7 = StringToUlong(a2, &v11);
  if ( v7 == -1073222112 )
  {
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v4 + 168LL))(v4, &v10);
    PrintMessage(0x41Au, v10, a2);
    return v7;
  }
  if ( v7 )
    return v7;
  v9 = v11;
  *(_BYTE *)(v8 + 680) |= 0x80u;
  *(_WORD *)(v8 + 210) = v9;
  return 0;
}

```

## disassembly

```asm
0x140034a38  mov     rax, rsp
0x140034a3b  mov     [rax+10h], rbx
0x140034a3f  mov     [rax+20h], rsi
0x140034a43  push    rdi
0x140034a44  sub     rsp, 20h
0x140034a48  cmp     byte ptr [r8+2A8h], 0
0x140034a50  mov     r11, r8
0x140034a53  mov     rdi, [rcx+18h]
0x140034a57  mov     rsi, rdx
0x140034a5a  mov     dword ptr [rax+18h], 0
0x140034a61  mov     dword ptr [rax+8], 0
0x140034a68  jge     short loc_140034A96
0x140034a6a  mov     rax, [rdi]
0x140034a6d  lea     rdx, [rsp+28h+arg_0]
0x140034a72  mov     rcx, rdi
0x140034a75  mov     rax, [rax+0A8h]
0x140034a7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034a81  mov     edx, [rsp+28h+arg_0]
0x140034a85  mov     ecx, 419h; unsigned int
0x140034a8a  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140034a8f  mov     eax, 0C007EE01h
0x140034a94  jmp     short loc_140034AF5
0x140034a96  lea     rdx, [rsp+28h+arg_10]; unsigned int *
0x140034a9b  mov     rcx, rsi; struct _UNICODE_STRING *
0x140034a9e  call    ?StringToUlong@@YAKAEAU_UNICODE_STRING@@PEAK@Z; StringToUlong(_UNICODE_STRING &,ulong *)
0x140034aa3  mov     ebx, eax
0x140034aa5  cmp     eax, 0C007EE20h
0x140034aaa  jnz     short loc_140034AD6
0x140034aac  mov     rcx, [rdi]
0x140034aaf  lea     rdx, [rsp+28h+arg_0]
0x140034ab4  mov     rax, [rcx+0A8h]
0x140034abb  mov     rcx, rdi
0x140034abe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034ac3  mov     edx, [rsp+28h+arg_0]
0x140034ac7  mov     r8, rsi
0x140034aca  mov     ecx, 41Ah; unsigned int
0x140034acf  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140034ad4  jmp     short loc_140034ADA
0x140034ad6  test    ebx, ebx
0x140034ad8  jz      short loc_140034ADE
0x140034ada  mov     eax, ebx
0x140034adc  jmp     short loc_140034AF5
0x140034ade  movzx   eax, word ptr [rsp+28h+arg_10]
0x140034ae3  or      byte ptr [r11+2A8h], 80h
0x140034aeb  mov     [r11+0D2h], ax
0x140034af3  xor     eax, eax
0x140034af5  mov     rbx, [rsp+28h+arg_8]
0x140034afa  mov     rsi, [rsp+28h+arg_18]
0x140034aff  add     rsp, 20h
0x140034b03  pop     rdi
0x140034b04  retn
```
