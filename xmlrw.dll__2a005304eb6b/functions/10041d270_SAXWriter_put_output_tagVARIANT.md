# SAXWriter::put_output(tagVARIANT)

- ea: `0x10041d270`
- end: `0x10041d3be`
- name: `?put_output@SAXWriter@@UEAAJUtagVARIANT@@@Z`
- size: `334`
- prototype: `int(SAXWriter *__hidden this, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x100401780`
- `0x10041d090`
- `0x10041d270`
- `0x10041d8a0`
- `0x1004238c0`
- `0x100423e80`
- `0x100439df0`

## pseudocode

```c
__int64 __fastcall SAXWriter::put_output(SAXWriter *this, struct tagVARIANT *a2)
{
  struct tagVARIANT *v2; // r9
  unsigned int v4; // edi
  VARTYPE vt; // r8
  struct tagVARIANT *pvarVal; // rcx
  unsigned __int16 v7; // r8
  int (__fastcall ***llVal)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v9; // rbx
  __int64 *v10; // r14
  __int64 v11; // rax
  __int64 *v12; // rcx
  __int64 v14; // [rsp+78h] [rbp+10h] BYREF
  int (__fastcall ***v15)(_QWORD, _QWORD, _QWORD); // [rsp+80h] [rbp+18h]

  v2 = a2;
  v4 = 0;
  vt = a2->vt;
  if ( a2->vt == 16396 )
  {
    pvarVal = a2->pvarVal;
    if ( pvarVal )
      vt = Variant::getBaseVariant(pvarVal)->vt;
  }
  v7 = vt & 0xBFFF;
  v14 = 0;
  if ( ((v7 - 9) & 0xFFFB) != 0 )
  {
    if ( v7 >= 2u )
    {
      MXRRaiseException(-2147024809);
      __debugbreak();
      JUMPOUT(0x10041D3BELL);
    }
    goto LABEL_14;
  }
  llVal = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))Variant::getBaseVariant(v2)->llVal;
  v15 = llVal;
  if ( !llVal )
  {
LABEL_14:
    v12 = (__int64 *)*((_QWORD *)this + 10);
    *((_QWORD *)this + 10) = 0;
    if ( !v12 )
      goto LABEL_17;
    v11 = *v12;
    goto LABEL_16;
  }
  if ( (**llVal)(llVal, &IID_IStream, &v14) < 0 )
  {
    v4 = -2147024809;
    goto LABEL_17;
  }
  v9 = v14;
  v10 = (__int64 *)*((_QWORD *)this + 10);
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
  *((_QWORD *)this + 10) = v9;
  if ( v10 )
  {
    v11 = *v10;
    v12 = v10;
LABEL_16:
    (*(void (__fastcall **)(__int64 *))(v11 + 16))(v12);
  }
LABEL_17:
  SAXWriter::setStream((SAXWriter *)((char *)this - 16), *((struct IStream **)this + 10));
  SAXWriter::setEncoding((SAXWriter *)((char *)this - 16), *((const wchar_t **)this + 18), *((_BYTE *)this + 210));
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  return v4;
}

```

## disassembly

```asm
0x10041d270  mov     [rsp+arg_0], rbx
0x10041d275  push    rsi
0x10041d276  push    rdi
0x10041d277  push    r14
0x10041d279  sub     rsp, 50h
0x10041d27d  mov     r9, rdx
0x10041d280  mov     rsi, rcx
0x10041d283  xor     edi, edi
0x10041d285  mov     [rsp+68h+var_40], edi
0x10041d289  movzx   r8d, word ptr [rdx]
0x10041d28d  mov     eax, 400Ch
0x10041d292  cmp     r8w, ax
0x10041d296  jnz     short loc_10041D2AA
0x10041d298  mov     rcx, [rdx+8]; struct tagVARIANT *
0x10041d29c  test    rcx, rcx
0x10041d29f  jz      short loc_10041D2AA
0x10041d2a1  call    ?getBaseVariant@Variant@@SAPEAUtagVARIANT@@PEAU2@@Z; Variant::getBaseVariant(tagVARIANT *)
0x10041d2a6  movzx   r8d, word ptr [rax]
0x10041d2aa  mov     eax, 0BFFFh
0x10041d2af  and     r8w, ax
0x10041d2b3  mov     [rsp+68h+arg_8], rdi
0x10041d2b8  lea     eax, [r8-9]
0x10041d2bc  mov     ecx, 0FFFBh
0x10041d2c1  test    cx, ax
0x10041d2c4  jz      short loc_10041D2D3
0x10041d2c6  cmp     r8w, 2
0x10041d2cb  jnb     loc_10041D3B2
0x10041d2d1  jmp     short loc_10041D342
0x10041d2d3  mov     rcx, r9; struct tagVARIANT *
0x10041d2d6  call    ?getBaseVariant@Variant@@SAPEAUtagVARIANT@@PEAU2@@Z; Variant::getBaseVariant(tagVARIANT *)
0x10041d2db  mov     rcx, [rax+8]
0x10041d2df  mov     [rsp+68h+arg_10], rcx
0x10041d2e7  test    rcx, rcx
0x10041d2ea  jz      short loc_10041D342
0x10041d2ec  mov     rax, [rcx]
0x10041d2ef  lea     r8, [rsp+68h+arg_8]
0x10041d2f4  lea     rdx, IID_IStream
0x10041d2fb  mov     rax, [rax]
0x10041d2fe  call    cs:__guard_dispatch_icall_fptr
0x10041d304  test    eax, eax
0x10041d306  js      short loc_10041D337
0x10041d308  mov     rbx, [rsp+68h+arg_8]
0x10041d30d  mov     r14, [rsi+50h]
0x10041d311  test    rbx, rbx
0x10041d314  jz      short loc_10041D326
0x10041d316  mov     rax, [rbx]
0x10041d319  mov     rcx, rbx
0x10041d31c  mov     rax, [rax+8]
0x10041d320  call    cs:__guard_dispatch_icall_fptr
0x10041d326  mov     [rsi+50h], rbx
0x10041d32a  test    r14, r14
0x10041d32d  jz      short loc_10041D35C
0x10041d32f  mov     rax, [r14]
0x10041d332  mov     rcx, r14
0x10041d335  jmp     short loc_10041D352
0x10041d337  mov     edi, 80070057h
0x10041d33c  mov     [rsp+68h+var_40], edi
0x10041d340  jmp     short loc_10041D35C
0x10041d342  mov     rcx, [rsi+50h]
0x10041d346  test    rcx, rcx
0x10041d349  mov     [rsi+50h], rdi
0x10041d34d  jz      short loc_10041D35C
0x10041d34f  mov     rax, [rcx]
0x10041d352  mov     rax, [rax+10h]
0x10041d356  call    cs:__guard_dispatch_icall_fptr
0x10041d35c  mov     rdx, [rsi+50h]; struct IStream *
0x10041d360  lea     rcx, [rsi-10h]; this
0x10041d364  call    ?setStream@SAXWriter@@QEAAXPEAUIStream@@@Z; SAXWriter::setStream(IStream *)
0x10041d369  movzx   r8d, byte ptr [rsi+0D2h]; bool
0x10041d371  mov     rdx, [rsi+90h]; wchar_t *
0x10041d378  lea     rcx, [rsi-10h]; this
0x10041d37c  call    ?setEncoding@SAXWriter@@QEAAXPEB_W_N@Z; SAXWriter::setEncoding(wchar_t const *,bool)
0x10041d381  jmp     short loc_10041D38B
0x10041d383  mov     edi, [rsp+68h+var_48]
0x10041d387  mov     [rsp+68h+var_40], edi
0x10041d38b  mov     rcx, [rsp+68h+arg_8]
0x10041d390  test    rcx, rcx
0x10041d393  jz      short loc_10041D3A2
0x10041d395  mov     rdx, [rcx]
0x10041d398  mov     rax, [rdx+10h]
0x10041d39c  call    cs:__guard_dispatch_icall_fptr
0x10041d3a2  mov     eax, edi
0x10041d3a4  mov     rbx, [rsp+68h+arg_0]
0x10041d3a9  add     rsp, 50h
0x10041d3ad  pop     r14
0x10041d3af  pop     rdi
0x10041d3b0  pop     rsi
0x10041d3b1  retn
0x10041d3b2  mov     ecx, 80070057h; int
0x10041d3b7  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10041d3bc  nop
0x10041d3bd  int     3; Trap to Debugger
0x10043a070  push    rbp
0x10043a072  sub     rsp, 20h
0x10043a076  mov     rbp, rdx
0x10043a079  mov     [rbp+40h], rcx
0x10043a07d  mov     [rbp+38h], rcx
0x10043a081  mov     rax, [rbp+38h]
0x10043a085  mov     rcx, [rax]
0x10043a088  mov     [rbp+30h], rcx
0x10043a08c  mov     rax, [rbp+30h]
0x10043a090  mov     eax, [rax]
0x10043a092  cmp     eax, 0C0000005h
0x10043a097  jz      short loc_10043A0C9
0x10043a099  add     eax, 1FFFFFFFh
0x10043a09e  cmp     eax, 1
0x10043a0a1  ja      short loc_10043A0B9
0x10043a0a3  mov     rax, [rbp+30h]
0x10043a0a7  cmp     dword ptr [rax+18h], 1
0x10043a0ab  jnz     short loc_10043A0B9
0x10043a0ad  mov     rax, [rbp+30h]
0x10043a0b1  mov     ecx, [rax+20h]
0x10043a0b4  mov     [rbp+20h], ecx
0x10043a0b7  jmp     short loc_10043A0C0
0x10043a0b9  mov     dword ptr [rbp+20h], 8000FFFFh
0x10043a0c0  mov     dword ptr [rbp+24h], 1
0x10043a0c7  jmp     short loc_10043A0D0
0x10043a0c9  mov     dword ptr [rbp+24h], 0
0x10043a0d0  mov     eax, [rbp+24h]
0x10043a0d3  add     rsp, 20h
0x10043a0d7  pop     rbp
0x10043a0d8  retn
```
