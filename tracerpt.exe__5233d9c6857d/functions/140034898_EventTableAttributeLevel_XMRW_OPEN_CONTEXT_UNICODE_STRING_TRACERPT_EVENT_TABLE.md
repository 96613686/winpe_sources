# EventTableAttributeLevel(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_EVENT_TABLE *)

- ea: `0x140034898`
- end: `0x140034963`
- name: `?EventTableAttributeLevel@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_EVENT_TABLE@@@Z`
- size: `203`
- prototype: `unsigned int(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING *, struct _TRACERPT_EVENT_TABLE *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140034dc4`

## callees

- `0x140034898`
- `0x14003694c`
- `0x140037a74`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall EventTableAttributeLevel(
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

  v3 = (*((_BYTE *)a3 + 680) & 8) == 0;
  v4 = *((_QWORD *)a1 + 3);
  v11 = 0;
  v10 = 0;
  if ( !v3 )
  {
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v4 + 168LL))(v4, &v10);
    PrintMessage(0x413u, v10);
    return 3221745153LL;
  }
  v7 = StringToUlong(a2, &v11);
  if ( v7 == -1073222112 )
  {
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v4 + 168LL))(v4, &v10);
    PrintMessage(0x414u, v10, a2);
    return v7;
  }
  if ( v7 )
    return v7;
  v9 = v11;
  *(_BYTE *)(v8 + 680) |= 8u;
  *(_DWORD *)(v8 + 192) = v9;
  return 0;
}

```

## disassembly

```asm
0x140034898  mov     rax, rsp
0x14003489b  mov     [rax+10h], rbx
0x14003489f  mov     [rax+20h], rsi
0x1400348a3  push    rdi
0x1400348a4  sub     rsp, 20h
0x1400348a8  test    byte ptr [r8+2A8h], 8
0x1400348b0  mov     r11, r8
0x1400348b3  mov     rdi, [rcx+18h]
0x1400348b7  mov     rsi, rdx
0x1400348ba  mov     dword ptr [rax+18h], 0
0x1400348c1  mov     dword ptr [rax+8], 0
0x1400348c8  jz      short loc_1400348F6
0x1400348ca  mov     rax, [rdi]
0x1400348cd  lea     rdx, [rsp+28h+arg_0]
0x1400348d2  mov     rcx, rdi
0x1400348d5  mov     rax, [rax+0A8h]
0x1400348dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400348e1  mov     edx, [rsp+28h+arg_0]
0x1400348e5  mov     ecx, 413h; unsigned int
0x1400348ea  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x1400348ef  mov     eax, 0C007EE01h
0x1400348f4  jmp     short loc_140034953
0x1400348f6  lea     rdx, [rsp+28h+arg_10]; unsigned int *
0x1400348fb  mov     rcx, rsi; struct _UNICODE_STRING *
0x1400348fe  call    ?StringToUlong@@YAKAEAU_UNICODE_STRING@@PEAK@Z; StringToUlong(_UNICODE_STRING &,ulong *)
0x140034903  mov     ebx, eax
0x140034905  cmp     eax, 0C007EE20h
0x14003490a  jnz     short loc_140034936
0x14003490c  mov     rcx, [rdi]
0x14003490f  lea     rdx, [rsp+28h+arg_0]
0x140034914  mov     rax, [rcx+0A8h]
0x14003491b  mov     rcx, rdi
0x14003491e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034923  mov     edx, [rsp+28h+arg_0]
0x140034927  mov     r8, rsi
0x14003492a  mov     ecx, 414h; unsigned int
0x14003492f  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140034934  jmp     short loc_14003493A
0x140034936  test    ebx, ebx
0x140034938  jz      short loc_14003493E
0x14003493a  mov     eax, ebx
0x14003493c  jmp     short loc_140034953
0x14003493e  mov     eax, [rsp+28h+arg_10]
0x140034942  or      byte ptr [r11+2A8h], 8
0x14003494a  mov     [r11+0C0h], eax
0x140034951  xor     eax, eax
0x140034953  mov     rbx, [rsp+28h+arg_8]
0x140034958  mov     rsi, [rsp+28h+arg_18]
0x14003495d  add     rsp, 20h
0x140034961  pop     rdi
0x140034962  retn
```
