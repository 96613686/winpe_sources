# EventFieldAttributeVersion(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_FIELD *)

- ea: `0x1400338f8`
- end: `0x1400339c0`
- name: `?EventFieldAttributeVersion@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_FIELD@@@Z`
- size: `200`
- prototype: `__int64 __fastcall(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING *, struct _TRACERPT_FIELD *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400339c8`

## callees

- `0x1400338f8`
- `0x14003694c`
- `0x140037a74`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall EventFieldAttributeVersion(
        struct _XMRW_OPEN_CONTEXT *a1,
        struct _UNICODE_STRING *a2,
        struct _TRACERPT_FIELD *a3)
{
  bool v3; // zf
  __int64 v4; // rdi
  unsigned int v7; // ebx
  __int64 v8; // r11
  char v9; // al
  unsigned int v10; // [rsp+30h] [rbp+8h] BYREF
  unsigned int v11; // [rsp+40h] [rbp+18h] BYREF

  v3 = (*((_BYTE *)a3 + 216) & 0x10) == 0;
  v4 = *((_QWORD *)a1 + 3);
  v11 = 0;
  v10 = 0;
  if ( !v3 )
  {
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v4 + 168LL))(v4, &v10);
    PrintMessage(0x448u, v10);
    return 3221745153LL;
  }
  v7 = StringToUlong(a2, &v11);
  if ( v7 == -1073222112 )
  {
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v4 + 168LL))(v4, &v10);
    PrintMessage(0x449u, v10, a2);
    return v7;
  }
  if ( v7 )
    return v7;
  v9 = v11;
  *(_BYTE *)(v8 + 216) |= 0x10u;
  *(_BYTE *)(v8 + 98) = v9;
  return 0;
}

```

## disassembly

```asm
0x1400338f8  mov     rax, rsp
0x1400338fb  mov     [rax+10h], rbx
0x1400338ff  mov     [rax+20h], rsi
0x140033903  push    rdi
0x140033904  sub     rsp, 20h
0x140033908  test    byte ptr [r8+0D8h], 10h
0x140033910  mov     r11, r8
0x140033913  mov     rdi, [rcx+18h]
0x140033917  mov     rsi, rdx
0x14003391a  mov     dword ptr [rax+18h], 0
0x140033921  mov     dword ptr [rax+8], 0
0x140033928  jz      short loc_140033956
0x14003392a  mov     rax, [rdi]
0x14003392d  lea     rdx, [rsp+28h+arg_0]
0x140033932  mov     rcx, rdi
0x140033935  mov     rax, [rax+0A8h]
0x14003393c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033941  mov     edx, [rsp+28h+arg_0]
0x140033945  mov     ecx, 448h; unsigned int
0x14003394a  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x14003394f  mov     eax, 0C007EE01h
0x140033954  jmp     short loc_1400339B0
0x140033956  lea     rdx, [rsp+28h+arg_10]; unsigned int *
0x14003395b  mov     rcx, rsi; struct _UNICODE_STRING *
0x14003395e  call    ?StringToUlong@@YAKAEAU_UNICODE_STRING@@PEAK@Z; StringToUlong(_UNICODE_STRING &,ulong *)
0x140033963  mov     ebx, eax
0x140033965  cmp     eax, 0C007EE20h
0x14003396a  jnz     short loc_140033996
0x14003396c  mov     rcx, [rdi]
0x14003396f  lea     rdx, [rsp+28h+arg_0]
0x140033974  mov     rax, [rcx+0A8h]
0x14003397b  mov     rcx, rdi
0x14003397e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033983  mov     edx, [rsp+28h+arg_0]
0x140033987  mov     r8, rsi
0x14003398a  mov     ecx, 449h; unsigned int
0x14003398f  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140033994  jmp     short loc_14003399A
0x140033996  test    ebx, ebx
0x140033998  jz      short loc_14003399E
0x14003399a  mov     eax, ebx
0x14003399c  jmp     short loc_1400339B0
0x14003399e  mov     al, byte ptr [rsp+28h+arg_10]
0x1400339a2  or      byte ptr [r11+0D8h], 10h
0x1400339aa  mov     [r11+62h], al
0x1400339ae  xor     eax, eax
0x1400339b0  mov     rbx, [rsp+28h+arg_8]
0x1400339b5  mov     rsi, [rsp+28h+arg_18]
0x1400339ba  add     rsp, 20h
0x1400339be  pop     rdi
0x1400339bf  retn
```
