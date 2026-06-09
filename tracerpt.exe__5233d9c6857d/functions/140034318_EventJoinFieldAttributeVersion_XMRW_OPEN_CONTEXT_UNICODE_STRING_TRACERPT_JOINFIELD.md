# EventJoinFieldAttributeVersion(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_JOINFIELD *)

- ea: `0x140034318`
- end: `0x1400343e0`
- name: `?EventJoinFieldAttributeVersion@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_JOINFIELD@@@Z`
- size: `200`
- prototype: `unsigned int(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING *, struct _TRACERPT_JOINFIELD *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14003451c`

## callees

- `0x140034318`
- `0x14003694c`
- `0x140037a74`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall EventJoinFieldAttributeVersion(
        struct _XMRW_OPEN_CONTEXT *a1,
        struct _UNICODE_STRING *a2,
        struct _TRACERPT_JOINFIELD *a3)
{
  bool v3; // zf
  __int64 v4; // rdi
  unsigned int v7; // ebx
  __int64 v8; // r11
  char v9; // al
  unsigned int v10; // [rsp+30h] [rbp+8h] BYREF
  unsigned int v11; // [rsp+40h] [rbp+18h] BYREF

  v3 = (*((_BYTE *)a3 + 176) & 4) == 0;
  v4 = *((_QWORD *)a1 + 3);
  v11 = 0;
  v10 = 0;
  if ( !v3 )
  {
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v4 + 168LL))(v4, &v10);
    PrintMessage(0x457u, v10);
    return 3221745153LL;
  }
  v7 = StringToUlong(a2, &v11);
  if ( v7 == -1073222112 )
  {
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v4 + 168LL))(v4, &v10);
    PrintMessage(0x458u, v10, a2);
    return v7;
  }
  if ( v7 )
    return v7;
  v9 = v11;
  *(_BYTE *)(v8 + 176) |= 4u;
  *(_BYTE *)(v8 + 58) = v9;
  return 0;
}

```

## disassembly

```asm
0x140034318  mov     rax, rsp
0x14003431b  mov     [rax+10h], rbx
0x14003431f  mov     [rax+20h], rsi
0x140034323  push    rdi
0x140034324  sub     rsp, 20h
0x140034328  test    byte ptr [r8+0B0h], 4
0x140034330  mov     r11, r8
0x140034333  mov     rdi, [rcx+18h]
0x140034337  mov     rsi, rdx
0x14003433a  mov     dword ptr [rax+18h], 0
0x140034341  mov     dword ptr [rax+8], 0
0x140034348  jz      short loc_140034376
0x14003434a  mov     rax, [rdi]
0x14003434d  lea     rdx, [rsp+28h+arg_0]
0x140034352  mov     rcx, rdi
0x140034355  mov     rax, [rax+0A8h]
0x14003435c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034361  mov     edx, [rsp+28h+arg_0]
0x140034365  mov     ecx, 457h; unsigned int
0x14003436a  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x14003436f  mov     eax, 0C007EE01h
0x140034374  jmp     short loc_1400343D0
0x140034376  lea     rdx, [rsp+28h+arg_10]; unsigned int *
0x14003437b  mov     rcx, rsi; struct _UNICODE_STRING *
0x14003437e  call    ?StringToUlong@@YAKAEAU_UNICODE_STRING@@PEAK@Z; StringToUlong(_UNICODE_STRING &,ulong *)
0x140034383  mov     ebx, eax
0x140034385  cmp     eax, 0C007EE20h
0x14003438a  jnz     short loc_1400343B6
0x14003438c  mov     rcx, [rdi]
0x14003438f  lea     rdx, [rsp+28h+arg_0]
0x140034394  mov     rax, [rcx+0A8h]
0x14003439b  mov     rcx, rdi
0x14003439e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400343a3  mov     edx, [rsp+28h+arg_0]
0x1400343a7  mov     r8, rsi
0x1400343aa  mov     ecx, 458h; unsigned int
0x1400343af  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x1400343b4  jmp     short loc_1400343BA
0x1400343b6  test    ebx, ebx
0x1400343b8  jz      short loc_1400343BE
0x1400343ba  mov     eax, ebx
0x1400343bc  jmp     short loc_1400343D0
0x1400343be  mov     al, byte ptr [rsp+28h+arg_10]
0x1400343c2  or      byte ptr [r11+0B0h], 4
0x1400343ca  mov     [r11+3Ah], al
0x1400343ce  xor     eax, eax
0x1400343d0  mov     rbx, [rsp+28h+arg_8]
0x1400343d5  mov     rsi, [rsp+28h+arg_18]
0x1400343da  add     rsp, 20h
0x1400343de  pop     rdi
0x1400343df  retn
```
