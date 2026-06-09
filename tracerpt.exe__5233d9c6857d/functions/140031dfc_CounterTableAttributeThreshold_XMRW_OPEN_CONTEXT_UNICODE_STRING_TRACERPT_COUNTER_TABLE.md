# CounterTableAttributeThreshold(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_COUNTER_TABLE *)

- ea: `0x140031dfc`
- end: `0x140031ec2`
- name: `?CounterTableAttributeThreshold@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_COUNTER_TABLE@@@Z`
- size: `198`
- prototype: `unsigned int(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING *, struct _TRACERPT_COUNTER_TABLE *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140031fb8`

## callees

- `0x140031dfc`
- `0x14003694c`
- `0x140037a74`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall CounterTableAttributeThreshold(
        struct _XMRW_OPEN_CONTEXT *a1,
        struct _UNICODE_STRING *a2,
        struct _TRACERPT_COUNTER_TABLE *a3)
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

  v3 = (*((_BYTE *)a3 + 220) & 0x40) == 0;
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
      PrintMessage(0x42Au, v12, a2);
    }
    if ( v11 )
    {
      return v11;
    }
    else
    {
      *((_BYTE *)a3 + 220) |= 0x40u;
      result = 0;
      *((_DWORD *)a3 + 54) = v10;
    }
  }
  else
  {
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v5 + 168LL))(v5, &v12);
    PrintMessage(0x429u, v12);
    return 3221745153LL;
  }
  return result;
}

```

## disassembly

```asm
0x140031dfc  mov     [rsp+arg_8], rbx
0x140031e01  push    rbp
0x140031e02  push    rsi
0x140031e03  push    rdi
0x140031e04  sub     rsp, 20h
0x140031e08  test    byte ptr [r8+0DCh], 40h
0x140031e10  mov     rbx, r8
0x140031e13  mov     r11, [rcx+18h]
0x140031e17  mov     rbp, rdx
0x140031e1a  mov     [rsp+38h+arg_10], 0
0x140031e22  mov     [rsp+38h+arg_0], 0
0x140031e2a  jz      short loc_140031E58
0x140031e2c  mov     rax, [r11]
0x140031e2f  lea     rdx, [rsp+38h+arg_0]
0x140031e34  mov     rcx, r11
0x140031e37  mov     rax, [rax+0A8h]
0x140031e3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031e43  mov     edx, [rsp+38h+arg_0]
0x140031e47  mov     ecx, 429h; unsigned int
0x140031e4c  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140031e51  mov     eax, 0C007EE01h
0x140031e56  jmp     short loc_140031EB5
0x140031e58  lea     rdx, [rsp+38h+arg_10]; unsigned int *
0x140031e5d  mov     rcx, rbp; struct _UNICODE_STRING *
0x140031e60  call    ?StringToUlong@@YAKAEAU_UNICODE_STRING@@PEAK@Z; StringToUlong(_UNICODE_STRING &,ulong *)
0x140031e65  mov     esi, [rsp+38h+arg_10]
0x140031e69  mov     edi, eax
0x140031e6b  cmp     eax, 0C007EE20h
0x140031e70  jz      short loc_140031E76
0x140031e72  test    esi, esi
0x140031e74  jnz     short loc_140031E9E
0x140031e76  mov     rcx, [r11]
0x140031e79  lea     rdx, [rsp+38h+arg_0]
0x140031e7e  mov     rax, [rcx+0A8h]
0x140031e85  mov     rcx, r11
0x140031e88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031e8d  mov     edx, [rsp+38h+arg_0]
0x140031e91  mov     r8, rbp
0x140031e94  mov     ecx, 42Ah; unsigned int
0x140031e99  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140031e9e  test    edi, edi
0x140031ea0  jz      short loc_140031EA6
0x140031ea2  mov     eax, edi
0x140031ea4  jmp     short loc_140031EB5
0x140031ea6  or      byte ptr [rbx+0DCh], 40h
0x140031ead  xor     eax, eax
0x140031eaf  mov     [rbx+0D8h], esi
0x140031eb5  mov     rbx, [rsp+38h+arg_8]
0x140031eba  add     rsp, 20h
0x140031ebe  pop     rdi
0x140031ebf  pop     rsi
0x140031ec0  pop     rbp
0x140031ec1  retn
```
