# SectionAttributeTitle(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_SECTION *)

- ea: `0x140037124`
- end: `0x14003720d`
- name: `?SectionAttributeTitle@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_SECTION@@@Z`
- size: `233`
- prototype: `__int64 __fastcall(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING *, struct _TRACERPT_SECTION *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140037214`

## callees

- `0x140030910`
- `0x140035a14`
- `0x1400365a8`
- `0x14003694c`
- `0x140037124`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall SectionAttributeTitle(
        struct _XMRW_OPEN_CONTEXT *a1,
        struct _UNICODE_STRING *a2,
        struct _TRACERPT_SECTION *a3)
{
  __int64 v3; // rsi
  __int64 result; // rax
  char v6; // al
  __int64 v7; // rbx
  char *v8; // rdi
  __int64 v9; // r9
  unsigned int v10; // [rsp+40h] [rbp+8h] BYREF
  __int64 v11; // [rsp+58h] [rbp+20h] BYREF

  v3 = *((_QWORD *)a1 + 8);
  v11 = 0;
  v10 = 0;
  if ( !v3 )
    return 0;
  v6 = *((_BYTE *)a3 + 192);
  v7 = *((_QWORD *)a1 + 3);
  if ( (v6 & 1) != 0 )
  {
    (*(void (__fastcall **)(_QWORD, unsigned int *))(*(_QWORD *)v7 + 168LL))(*((_QWORD *)a1 + 3), &v10);
    PrintMessage(0x3ECu, v10);
    return 3221745153LL;
  }
  else
  {
    v8 = (char *)a3 + 104;
    *((_BYTE *)a3 + 192) = v6 | 1;
    *((_BYTE *)a3 + 136) = 1;
    RPT_STRING::operator=((__int64)a3 + 104, (const void **)a2);
    result = HashTable<RPT_STRING,0,0>::Find(v3 + 48, (const UNICODE_STRING *)(v8 + 8), &v11, v9);
    if ( (_DWORD)result )
    {
      if ( (_DWORD)result == 1168 )
        return HashTable<RPT_STRING,0,0>::Insert((_QWORD *)(v3 + 48), (__int64)v8);
    }
    else
    {
      (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v7 + 168LL))(v7, &v10);
      PrintMessage(0x3EDu, v10, a2);
      return 3221745154LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140037124  mov     [rsp+arg_8], rbx
0x140037129  push    rbp
0x14003712a  push    rsi
0x14003712b  push    rdi
0x14003712c  sub     rsp, 20h
0x140037130  mov     rsi, [rcx+40h]
0x140037134  mov     rbp, rdx
0x140037137  mov     [rsp+38h+arg_18], 0
0x140037140  mov     [rsp+38h+arg_0], 0
0x140037148  test    rsi, rsi
0x14003714b  jnz     short loc_140037154
0x14003714d  xor     eax, eax
0x14003714f  jmp     loc_140037200
0x140037154  mov     al, [r8+0C0h]
0x14003715b  mov     rbx, [rcx+18h]
0x14003715f  test    al, 1
0x140037161  jz      short loc_14003718F
0x140037163  mov     rax, [rbx]
0x140037166  lea     rdx, [rsp+38h+arg_0]
0x14003716b  mov     rcx, rbx
0x14003716e  mov     rax, [rax+0A8h]
0x140037175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003717a  mov     edx, [rsp+38h+arg_0]
0x14003717e  mov     ecx, 3ECh; unsigned int
0x140037183  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140037188  mov     eax, 0C007EE01h
0x14003718d  jmp     short loc_140037200
0x14003718f  lea     rdi, [r8+68h]
0x140037193  or      al, 1
0x140037195  mov     rcx, rdi
0x140037198  mov     [r8+0C0h], al
0x14003719f  mov     byte ptr [rdi+20h], 1
0x1400371a3  call    ??4RPT_STRING@@QEAAPEBV0@AEAU_UNICODE_STRING@@@Z; RPT_STRING::operator=(_UNICODE_STRING &)
0x1400371a8  lea     rdx, [rdi+8]
0x1400371ac  lea     r8, [rsp+38h+arg_18]
0x1400371b1  lea     rcx, [rsi+30h]
0x1400371b5  call    ?Find@?$HashTable@VRPT_STRING@@$0A@$0A@@@QEAAKPEAU_UNICODE_STRING@@PEAPEAVRPT_STRING@@@Z; HashTable<RPT_STRING,0,0>::Find(_UNICODE_STRING *,RPT_STRING * *)
0x1400371ba  test    eax, eax
0x1400371bc  jz      short loc_1400371D3
0x1400371be  cmp     eax, 490h
0x1400371c3  jnz     short loc_140037200
0x1400371c5  mov     rdx, rdi
0x1400371c8  lea     rcx, [rsi+30h]
0x1400371cc  call    ?Insert@?$HashTable@VRPT_STRING@@$0A@$0A@@@QEAAKPEAVRPT_STRING@@@Z; HashTable<RPT_STRING,0,0>::Insert(RPT_STRING *)
0x1400371d1  jmp     short loc_140037200
0x1400371d3  mov     rax, [rbx]
0x1400371d6  lea     rdx, [rsp+38h+arg_0]
0x1400371db  mov     rcx, rbx
0x1400371de  mov     rax, [rax+0A8h]
0x1400371e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400371ea  mov     edx, [rsp+38h+arg_0]
0x1400371ee  mov     r8, rbp
0x1400371f1  mov     ecx, 3EDh; unsigned int
0x1400371f6  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x1400371fb  mov     eax, 0C007EE02h
0x140037200  mov     rbx, [rsp+38h+arg_8]
0x140037205  add     rsp, 20h
0x140037209  pop     rdi
0x14003720a  pop     rsi
0x14003720b  pop     rbp
0x14003720c  retn
```
