# IncludeAttributeInstance(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_INCLUSIVE_INSTANCE *)

- ea: `0x140036114`
- end: `0x140036250`
- name: `?IncludeAttributeInstance@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_INCLUSIVE_INSTANCE@@@Z`
- size: `316`
- prototype: `unsigned int __fastcall(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING *, struct _TRACERPT_INCLUSIVE_INSTANCE *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140036258`

## callees

- `0x140019b1c`
- `0x140030910`
- `0x140036114`
- `0x14003694c`
- `0x140041010`

## pseudocode

```c
unsigned int __fastcall IncludeAttributeInstance(
        struct _XMRW_OPEN_CONTEXT *a1,
        struct _UNICODE_STRING *a2,
        struct _TRACERPT_INCLUSIVE_INSTANCE *a3)
{
  __int64 v3; // r10
  unsigned int result; // eax
  unsigned __int16 *Buffer; // rdi
  __int64 v8; // r10
  __int64 v9; // r11
  char v10; // dl
  __int16 v11; // r8
  char v12; // al
  _WORD v13[2]; // [rsp+20h] [rbp-10h] BYREF
  int v14; // [rsp+24h] [rbp-Ch]
  char *v15; // [rsp+28h] [rbp-8h]
  unsigned int v16; // [rsp+50h] [rbp+20h] BYREF
  int v17; // [rsp+60h] [rbp+30h] BYREF

  v3 = *((_QWORD *)a1 + 3);
  v17 = 0;
  v14 = 0;
  v16 = 0;
  if ( (*((_BYTE *)a3 + 56) & 1) != 0 )
  {
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v3 + 168LL))(v3, &v16);
    PrintMessage(0x42Du, v16);
    return -1073222143;
  }
  else
  {
    Buffer = a2->Buffer;
    result = ParsePatternString(Buffer, a2->Length >> 1, &v17);
    if ( result )
    {
      if ( result == 13 )
      {
        (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v8 + 168LL))(v8, &v16);
        PrintMessage(0x42Eu, v16, a2);
        return -1073222112;
      }
    }
    else
    {
      v10 = v17;
      v11 = 2;
      if ( !v17 )
        v11 = 1;
      v15 = (char *)Buffer + (-(__int64)(v17 != 0) & 2) + 2;
      Buffer[v9 - 1] = 0;
      v12 = *((_BYTE *)a3 + 56);
      *((_BYTE *)a3 + 48) = 0;
      v13[0] = 2 * (v9 - v11);
      v13[1] = v13[0];
      *((_BYTE *)a3 + 56) = v12 & 0xFD | (2 * (v10 & 1)) | 1;
      RPT_STRING::operator=((char *)a3 + 16, v13);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140036114  mov     [rsp-18h+arg_8], rbx
0x140036119  mov     [rsp-18h+arg_18], rsi
0x14003611e  push    rbp
0x14003611f  push    rdi
0x140036120  push    r15
0x140036122  mov     rbp, rsp
0x140036125  sub     rsp, 30h
0x140036129  mov     r10, [rcx+18h]
0x14003612d  mov     r15d, 1
0x140036133  mov     rsi, r8
0x140036136  mov     rbx, rdx
0x140036139  mov     [rbp+arg_10], 0
0x140036140  mov     [rbp+var_C], 0
0x140036147  mov     [rbp+arg_0], 0
0x14003614e  test    [r8+38h], r15b
0x140036152  jz      short loc_140036181
0x140036154  mov     rax, [r10]
0x140036157  lea     rdx, [rbp+arg_0]
0x14003615b  mov     rcx, r10
0x14003615e  mov     rax, [rax+0A8h]
0x140036165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003616a  mov     edx, [rbp+arg_0]
0x14003616d  mov     ecx, 42Dh; unsigned int
0x140036172  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140036177  mov     eax, 0C007EE01h
0x14003617c  jmp     loc_14003623D
0x140036181  movzx   eax, word ptr [rdx]
0x140036184  lea     r8, [rbp+arg_10]; int *
0x140036188  mov     rdi, [rdx+8]
0x14003618c  shr     ax, 1
0x14003618f  mov     rcx, rdi; unsigned __int16 *
0x140036192  movzx   r11d, ax
0x140036196  mov     edx, r11d; unsigned __int64
0x140036199  call    ?ParsePatternString@@YAKPEAG_KPEAH@Z; ParsePatternString(ushort *,unsigned __int64,int *)
0x14003619e  test    eax, eax
0x1400361a0  jz      short loc_1400361D8
0x1400361a2  cmp     eax, 0Dh
0x1400361a5  jnz     loc_14003623D
0x1400361ab  mov     rax, [r10]
0x1400361ae  lea     rdx, [rbp+arg_0]
0x1400361b2  mov     rcx, r10
0x1400361b5  mov     rax, [rax+0A8h]
0x1400361bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400361c1  mov     edx, [rbp+arg_0]
0x1400361c4  mov     r8, rbx
0x1400361c7  mov     ecx, 42Eh; unsigned int
0x1400361cc  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x1400361d1  mov     eax, 0C007EE20h
0x1400361d6  jmp     short loc_14003623D
0x1400361d8  mov     edx, [rbp+arg_10]
0x1400361db  mov     r8d, 2
0x1400361e1  mov     eax, edx
0x1400361e3  neg     eax
0x1400361e5  sbb     rcx, rcx
0x1400361e8  and     rcx, r8
0x1400361eb  lea     r9, [r8+rcx]
0x1400361ef  add     r9, rdi
0x1400361f2  test    edx, edx
0x1400361f4  jnz     short loc_1400361FA
0x1400361f6  movzx   r8d, r15w
0x1400361fa  and     dl, r15b
0x1400361fd  mov     [rbp+var_8], r9
0x140036201  xor     eax, eax
0x140036203  lea     rcx, [rsi+10h]
0x140036207  mov     [rdi+r11*2-2], ax
0x14003620d  add     dl, dl
0x14003620f  mov     al, [rsi+38h]
0x140036212  sub     r11w, r8w
0x140036216  add     r11w, r11w
0x14003621a  mov     byte ptr [rcx+20h], 0
0x14003621e  and     al, 0FDh
0x140036220  mov     [rbp+var_10], r11w
0x140036225  or      dl, al
0x140036227  mov     [rbp+var_E], r11w
0x14003622c  or      dl, r15b
0x14003622f  mov     [rsi+38h], dl
0x140036232  lea     rdx, [rbp+var_10]
0x140036236  call    ??4RPT_STRING@@QEAAPEBV0@AEAU_UNICODE_STRING@@@Z; RPT_STRING::operator=(_UNICODE_STRING &)
0x14003623b  xor     eax, eax
0x14003623d  mov     rbx, [rsp+30h+arg_8]
0x140036242  mov     rsi, [rsp+30h+arg_18]
0x140036247  add     rsp, 30h
0x14003624b  pop     r15
0x14003624d  pop     rdi
0x14003624e  pop     rbp
0x14003624f  retn
```
