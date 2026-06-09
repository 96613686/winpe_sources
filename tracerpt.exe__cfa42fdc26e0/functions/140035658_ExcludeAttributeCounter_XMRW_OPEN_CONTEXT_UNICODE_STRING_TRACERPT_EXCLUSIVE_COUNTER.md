# ExcludeAttributeCounter(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_EXCLUSIVE_COUNTER *)

- ea: `0x140035658`
- end: `0x140035794`
- name: `?ExcludeAttributeCounter@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_EXCLUSIVE_COUNTER@@@Z`
- size: `316`
- prototype: `unsigned int __fastcall(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING *, struct _TRACERPT_EXCLUSIVE_COUNTER *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14003579c`

## callees

- `0x140019b1c`
- `0x140030910`
- `0x140035658`
- `0x14003694c`
- `0x140041010`

## pseudocode

```c
unsigned int __fastcall ExcludeAttributeCounter(
        struct _XMRW_OPEN_CONTEXT *a1,
        struct _UNICODE_STRING *a2,
        struct _TRACERPT_EXCLUSIVE_COUNTER *a3)
{
  __int64 v3; // r10
  unsigned int result; // eax
  unsigned __int16 *Buffer; // rdi
  __int64 v8; // r10
  __int64 v9; // r11
  char v10; // dl
  __int16 v11; // r8
  char v12; // al
  const void *v13[2]; // [rsp+20h] [rbp-10h] BYREF
  unsigned int v14; // [rsp+50h] [rbp+20h] BYREF
  int v15; // [rsp+60h] [rbp+30h] BYREF

  v3 = *((_QWORD *)a1 + 3);
  v15 = 0;
  HIDWORD(v13[0]) = 0;
  v14 = 0;
  if ( (*((_BYTE *)a3 + 56) & 1) != 0 )
  {
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v3 + 168LL))(v3, &v14);
    PrintMessage(0x42Bu, v14);
    return -1073222143;
  }
  else
  {
    Buffer = a2->Buffer;
    result = ParsePatternString(Buffer, a2->Length >> 1, &v15);
    if ( result )
    {
      if ( result == 13 )
      {
        (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v8 + 168LL))(v8, &v14);
        PrintMessage(0x42Cu, v14, a2);
        return -1073222112;
      }
    }
    else
    {
      v10 = v15;
      v11 = 2;
      if ( !v15 )
        v11 = 1;
      v13[1] = (char *)Buffer + (-(__int64)(v15 != 0) & 2) + 2;
      Buffer[v9 - 1] = 0;
      v12 = *((_BYTE *)a3 + 56);
      *((_BYTE *)a3 + 48) = 0;
      LOWORD(v13[0]) = 2 * (v9 - v11);
      WORD1(v13[0]) = v13[0];
      *((_BYTE *)a3 + 56) = v12 & 0xFD | (2 * (v10 & 1)) | 1;
      RPT_STRING::operator=((__int64)a3 + 16, v13);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140035658  mov     [rsp-18h+arg_8], rbx
0x14003565d  mov     [rsp-18h+arg_18], rsi
0x140035662  push    rbp
0x140035663  push    rdi
0x140035664  push    r15
0x140035666  mov     rbp, rsp
0x140035669  sub     rsp, 30h
0x14003566d  mov     r10, [rcx+18h]
0x140035671  mov     r15d, 1
0x140035677  mov     rsi, r8
0x14003567a  mov     rbx, rdx
0x14003567d  mov     [rbp+arg_10], 0
0x140035684  mov     [rbp+var_C], 0
0x14003568b  mov     [rbp+arg_0], 0
0x140035692  test    [r8+38h], r15b
0x140035696  jz      short loc_1400356C5
0x140035698  mov     rax, [r10]
0x14003569b  lea     rdx, [rbp+arg_0]
0x14003569f  mov     rcx, r10
0x1400356a2  mov     rax, [rax+0A8h]
0x1400356a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400356ae  mov     edx, [rbp+arg_0]
0x1400356b1  mov     ecx, 42Bh; unsigned int
0x1400356b6  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x1400356bb  mov     eax, 0C007EE01h
0x1400356c0  jmp     loc_140035781
0x1400356c5  movzx   eax, word ptr [rdx]
0x1400356c8  lea     r8, [rbp+arg_10]; int *
0x1400356cc  mov     rdi, [rdx+8]
0x1400356d0  shr     ax, 1
0x1400356d3  mov     rcx, rdi; unsigned __int16 *
0x1400356d6  movzx   r11d, ax
0x1400356da  mov     edx, r11d; unsigned __int64
0x1400356dd  call    ?ParsePatternString@@YAKPEAG_KPEAH@Z; ParsePatternString(ushort *,unsigned __int64,int *)
0x1400356e2  test    eax, eax
0x1400356e4  jz      short loc_14003571C
0x1400356e6  cmp     eax, 0Dh
0x1400356e9  jnz     loc_140035781
0x1400356ef  mov     rax, [r10]
0x1400356f2  lea     rdx, [rbp+arg_0]
0x1400356f6  mov     rcx, r10
0x1400356f9  mov     rax, [rax+0A8h]
0x140035700  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035705  mov     edx, [rbp+arg_0]
0x140035708  mov     r8, rbx
0x14003570b  mov     ecx, 42Ch; unsigned int
0x140035710  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140035715  mov     eax, 0C007EE20h
0x14003571a  jmp     short loc_140035781
0x14003571c  mov     edx, [rbp+arg_10]
0x14003571f  mov     r8d, 2
0x140035725  mov     eax, edx
0x140035727  neg     eax
0x140035729  sbb     rcx, rcx
0x14003572c  and     rcx, r8
0x14003572f  lea     r9, [r8+rcx]
0x140035733  add     r9, rdi
0x140035736  test    edx, edx
0x140035738  jnz     short loc_14003573E
0x14003573a  movzx   r8d, r15w
0x14003573e  and     dl, r15b
0x140035741  mov     [rbp+var_8], r9
0x140035745  xor     eax, eax
0x140035747  lea     rcx, [rsi+10h]
0x14003574b  mov     [rdi+r11*2-2], ax
0x140035751  add     dl, dl
0x140035753  mov     al, [rsi+38h]
0x140035756  sub     r11w, r8w
0x14003575a  add     r11w, r11w
0x14003575e  mov     byte ptr [rcx+20h], 0
0x140035762  and     al, 0FDh
0x140035764  mov     [rbp+var_10], r11w
0x140035769  or      dl, al
0x14003576b  mov     [rbp+var_E], r11w
0x140035770  or      dl, r15b
0x140035773  mov     [rsi+38h], dl
0x140035776  lea     rdx, [rbp+var_10]
0x14003577a  call    ??4RPT_STRING@@QEAAPEBV0@AEAU_UNICODE_STRING@@@Z; RPT_STRING::operator=(_UNICODE_STRING &)
0x14003577f  xor     eax, eax
0x140035781  mov     rbx, [rsp+30h+arg_8]
0x140035786  mov     rsi, [rsp+30h+arg_18]
0x14003578b  add     rsp, 30h
0x14003578f  pop     r15
0x140035791  pop     rdi
0x140035792  pop     rbp
0x140035793  retn
```
