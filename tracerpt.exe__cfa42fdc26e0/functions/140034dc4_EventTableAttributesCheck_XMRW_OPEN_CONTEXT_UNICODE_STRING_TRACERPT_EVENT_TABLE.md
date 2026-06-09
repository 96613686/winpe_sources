# EventTableAttributesCheck(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_EVENT_TABLE *)

- ea: `0x140034dc4`
- end: `0x140035066`
- name: `?EventTableAttributesCheck@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_EVENT_TABLE@@@Z`
- size: `674`
- prototype: `unsigned int __fastcall(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING *, struct _TRACERPT_EVENT_TABLE *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task`

## callers

- `0x140035300`

## callees

- `0x140016808`
- `0x140030910`
- `0x1400347c4`
- `0x140034898`
- `0x14003496c`
- `0x140034a38`
- `0x140034b0c`
- `0x140034bd8`
- `0x140034cc8`
- `0x140034dc4`
- `0x14003694c`
- `0x140041010`

## pseudocode

```c
unsigned int __fastcall EventTableAttributesCheck(
        struct _XMRW_OPEN_CONTEXT *a1,
        struct _UNICODE_STRING *a2,
        struct _TRACERPT_EVENT_TABLE *a3)
{
  __int64 v4; // rcx
  struct _UNICODE_STRING v7; // xmm0
  char v9; // al
  char v10; // al
  char *v11; // rcx
  char v12; // al
  struct _UNICODE_STRING v13; // [rsp+20h] [rbp-20h] BYREF
  struct _UNICODE_STRING v14; // [rsp+30h] [rbp-10h] BYREF
  int v15; // [rsp+60h] [rbp+20h] BYREF
  unsigned int v16; // [rsp+68h] [rbp+28h] BYREF
  WCHAR *v17; // [rsp+78h] [rbp+38h] BYREF

  v17 = 0;
  v4 = *((_QWORD *)a1 + 3);
  v15 = 0;
  v13 = 0;
  (*(void (__fastcall **)(__int64, WCHAR **, int *))(*(_QWORD *)v4 + 128LL))(v4, &v17, &v15);
  v7 = *a2;
  v13.Buffer = v17;
  v13.MaximumLength = 2 * v15;
  v13.Length = 2 * v15;
  v14 = v7;
  if ( EqualString(&v14, L"name", 0) )
    return EventTableAttributeTitle(a1, &v13, a3);
  v14 = *a2;
  if ( EqualString(&v14, L"topic", 0) )
  {
    v9 = *((_BYTE *)a3 + 680);
    v16 = 0;
    if ( (v9 & 2) != 0 )
    {
      (*(void (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)a1 + 3) + 168LL))(*((_QWORD *)a1 + 3), &v16);
      PrintMessage(0x410u, v16);
      return -1073222143;
    }
    v10 = v9 | 2;
    v11 = (char *)a3 + 112;
LABEL_8:
    *((_BYTE *)a3 + 680) = v10;
    v11[32] = 1;
    RPT_STRING::operator=((__int64)v11, (const void **)&v13);
    return 0;
  }
  v14 = *a2;
  if ( EqualString(&v14, L"level", 0) )
    return EventTableAttributeLevel(a1, &v13, a3);
  v14 = *a2;
  if ( EqualString(&v14, L"key", 0) )
    return EventTableAttributeKey(a1, &v13, a3);
  v14 = *a2;
  if ( EqualString(&v14, L"note", 0) )
  {
    v12 = *((_BYTE *)a3 + 680);
    v16 = 0;
    if ( (v12 & 4) != 0 )
    {
      (*(void (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)a1 + 3) + 168LL))(*((_QWORD *)a1 + 3), &v16);
      PrintMessage(0x41Fu, v16);
      return -1073222143;
    }
    v10 = v12 | 4;
    v11 = (char *)a3 + 152;
    goto LABEL_8;
  }
  v14 = *a2;
  if ( EqualString(&v14, L"threshold", 0) )
    return EventTableAttributeThreshold(a1, &v13, a3);
  v14 = *a2;
  if ( EqualString(&v14, L"transaction", 0) )
    return EventTableAttributeTransaction(a1, &v13, a3);
  v14 = *a2;
  if ( EqualString(&v14, L"task", 0) )
    return EventTableAttributeTask(a1, &v13, a3);
  v14 = *a2;
  if ( !EqualString(&v14, L"rowcount", 0) )
    return 0;
  return EventTableAttributeRowCount(a1, &v13, a3);
}

```

## disassembly

```asm
0x140034dc4  mov     [rsp-18h+arg_10], rbx
0x140034dc9  push    rbp
0x140034dca  push    rsi
0x140034dcb  push    rdi
0x140034dcc  mov     rbp, rsp
0x140034dcf  sub     rsp, 40h
0x140034dd3  mov     rdi, rcx
0x140034dd6  mov     [rbp+arg_18], 0
0x140034dde  mov     rcx, [rcx+18h]
0x140034de2  xorps   xmm0, xmm0
0x140034de5  mov     [rbp+arg_0], 0
0x140034dec  mov     rbx, r8
0x140034def  movups  xmmword ptr [rbp+var_20.Length], xmm0
0x140034df3  mov     rsi, rdx
0x140034df6  lea     r8, [rbp+arg_0]
0x140034dfa  mov     rax, [rcx]
0x140034dfd  lea     rdx, [rbp+arg_18]
0x140034e01  mov     rax, [rax+80h]
0x140034e08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034e0d  mov     rax, [rbp+arg_18]
0x140034e11  lea     rdx, aName_0; "name"
0x140034e18  movups  xmm0, xmmword ptr [rsi]
0x140034e1b  mov     [rbp+var_20.Buffer], rax
0x140034e1f  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140034e23  movzx   eax, word ptr [rbp+arg_0]
0x140034e27  xor     r8d, r8d; unsigned __int8
0x140034e2a  add     ax, ax
0x140034e2d  mov     [rbp+var_20.MaximumLength], ax
0x140034e31  mov     [rbp+var_20.Length], ax
0x140034e35  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140034e3a  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140034e3f  test    al, al
0x140034e41  jz      short loc_140034E54
0x140034e43  mov     r8, rbx; struct _TRACERPT_EVENT_TABLE *
0x140034e46  lea     rdx, [rbp+var_20]; struct _UNICODE_STRING *
0x140034e4a  mov     rcx, rdi; struct _XMRW_OPEN_CONTEXT *
0x140034e4d  call    ?EventTableAttributeTitle@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_EVENT_TABLE@@@Z; EventTableAttributeTitle(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_EVENT_TABLE *)
0x140034e52  jmp     short loc_140034ECA
0x140034e54  movups  xmm0, xmmword ptr [rsi]
0x140034e57  xor     r8d, r8d; unsigned __int8
0x140034e5a  lea     rdx, aTopic; "topic"
0x140034e61  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140034e65  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140034e6a  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140034e6f  test    al, al
0x140034e71  jz      short loc_140034ED7
0x140034e73  mov     al, [rbx+2A8h]
0x140034e79  mov     [rbp+arg_8], 0
0x140034e80  test    al, 2
0x140034e82  jz      short loc_140034EAF
0x140034e84  mov     rcx, [rdi+18h]
0x140034e88  lea     rdx, [rbp+arg_8]
0x140034e8c  mov     rax, [rcx]
0x140034e8f  mov     rax, [rax+0A8h]
0x140034e96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034e9b  mov     ecx, 410h; unsigned int
0x140034ea0  mov     edx, [rbp+arg_8]
0x140034ea3  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140034ea8  mov     eax, 0C007EE01h
0x140034ead  jmp     short loc_140034ECA
0x140034eaf  or      al, 2
0x140034eb1  lea     rcx, [rbx+70h]
0x140034eb5  lea     rdx, [rbp+var_20]
0x140034eb9  mov     [rbx+2A8h], al
0x140034ebf  mov     byte ptr [rcx+20h], 1
0x140034ec3  call    ??4RPT_STRING@@QEAAPEBV0@AEAU_UNICODE_STRING@@@Z; RPT_STRING::operator=(_UNICODE_STRING &)
0x140034ec8  xor     eax, eax
0x140034eca  mov     rbx, [rsp+40h+arg_10]
0x140034ecf  add     rsp, 40h
0x140034ed3  pop     rdi
0x140034ed4  pop     rsi
0x140034ed5  pop     rbp
0x140034ed6  retn
0x140034ed7  movups  xmm0, xmmword ptr [rsi]
0x140034eda  xor     r8d, r8d; unsigned __int8
0x140034edd  lea     rdx, aLevel; "level"
0x140034ee4  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140034ee8  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140034eed  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140034ef2  test    al, al
0x140034ef4  jz      short loc_140034F07
0x140034ef6  mov     r8, rbx; struct _TRACERPT_EVENT_TABLE *
0x140034ef9  lea     rdx, [rbp+var_20]; struct _UNICODE_STRING *
0x140034efd  mov     rcx, rdi; struct _XMRW_OPEN_CONTEXT *
0x140034f00  call    ?EventTableAttributeLevel@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_EVENT_TABLE@@@Z; EventTableAttributeLevel(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_EVENT_TABLE *)
0x140034f05  jmp     short loc_140034ECA
0x140034f07  movups  xmm0, xmmword ptr [rsi]
0x140034f0a  xor     r8d, r8d; unsigned __int8
0x140034f0d  lea     rdx, aKey; "key"
0x140034f14  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140034f18  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140034f1d  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140034f22  test    al, al
0x140034f24  jz      short loc_140034F37
0x140034f26  mov     r8, rbx; struct _TRACERPT_EVENT_TABLE *
0x140034f29  lea     rdx, [rbp+var_20]; struct _UNICODE_STRING *
0x140034f2d  mov     rcx, rdi; struct _XMRW_OPEN_CONTEXT *
0x140034f30  call    ?EventTableAttributeKey@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_EVENT_TABLE@@@Z; EventTableAttributeKey(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_EVENT_TABLE *)
0x140034f35  jmp     short loc_140034ECA
0x140034f37  movups  xmm0, xmmword ptr [rsi]
0x140034f3a  xor     r8d, r8d; unsigned __int8
0x140034f3d  lea     rdx, aNote; "note"
0x140034f44  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140034f48  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140034f4d  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140034f52  test    al, al
0x140034f54  jz      short loc_140034F96
0x140034f56  mov     al, [rbx+2A8h]
0x140034f5c  mov     [rbp+arg_8], 0
0x140034f63  test    al, 4
0x140034f65  jz      short loc_140034F88
0x140034f67  mov     rcx, [rdi+18h]
0x140034f6b  lea     rdx, [rbp+arg_8]
0x140034f6f  mov     rax, [rcx]
0x140034f72  mov     rax, [rax+0A8h]
0x140034f79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034f7e  mov     ecx, 41Fh
0x140034f83  jmp     loc_140034EA0
0x140034f88  or      al, 4
0x140034f8a  lea     rcx, [rbx+98h]
0x140034f91  jmp     loc_140034EB5
0x140034f96  movups  xmm0, xmmword ptr [rsi]
0x140034f99  xor     r8d, r8d; unsigned __int8
0x140034f9c  lea     rdx, aThreshold; "threshold"
0x140034fa3  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140034fa7  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140034fac  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140034fb1  test    al, al
0x140034fb3  jz      short loc_140034FC9
0x140034fb5  mov     r8, rbx; struct _TRACERPT_EVENT_TABLE *
0x140034fb8  lea     rdx, [rbp+var_20]; struct _UNICODE_STRING *
0x140034fbc  mov     rcx, rdi; struct _XMRW_OPEN_CONTEXT *
0x140034fbf  call    ?EventTableAttributeThreshold@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_EVENT_TABLE@@@Z; EventTableAttributeThreshold(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_EVENT_TABLE *)
0x140034fc4  jmp     loc_140034ECA
0x140034fc9  movups  xmm0, xmmword ptr [rsi]
0x140034fcc  xor     r8d, r8d; unsigned __int8
0x140034fcf  lea     rdx, aTransaction; "transaction"
0x140034fd6  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140034fda  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140034fdf  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140034fe4  test    al, al
0x140034fe6  jz      short loc_140034FFC
0x140034fe8  mov     r8, rbx; struct _TRACERPT_EVENT_TABLE *
0x140034feb  lea     rdx, [rbp+var_20]; struct _UNICODE_STRING *
0x140034fef  mov     rcx, rdi; struct _XMRW_OPEN_CONTEXT *
0x140034ff2  call    ?EventTableAttributeTransaction@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_EVENT_TABLE@@@Z; EventTableAttributeTransaction(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_EVENT_TABLE *)
0x140034ff7  jmp     loc_140034ECA
0x140034ffc  movups  xmm0, xmmword ptr [rsi]
0x140034fff  xor     r8d, r8d; unsigned __int8
0x140035002  lea     rdx, aTask_0; "task"
0x140035009  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x14003500d  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140035012  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140035017  test    al, al
0x140035019  jz      short loc_14003502F
0x14003501b  mov     r8, rbx; struct _TRACERPT_EVENT_TABLE *
0x14003501e  lea     rdx, [rbp+var_20]; struct _UNICODE_STRING *
0x140035022  mov     rcx, rdi; struct _XMRW_OPEN_CONTEXT *
0x140035025  call    ?EventTableAttributeTask@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_EVENT_TABLE@@@Z; EventTableAttributeTask(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_EVENT_TABLE *)
0x14003502a  jmp     loc_140034ECA
0x14003502f  movups  xmm0, xmmword ptr [rsi]
0x140035032  xor     r8d, r8d; unsigned __int8
0x140035035  lea     rdx, aRowcount; "rowcount"
0x14003503c  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140035040  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140035045  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x14003504a  test    al, al
0x14003504c  jz      loc_140034EC8
0x140035052  mov     r8, rbx; struct _TRACERPT_EVENT_TABLE *
0x140035055  lea     rdx, [rbp+var_20]; struct _UNICODE_STRING *
0x140035059  mov     rcx, rdi; struct _XMRW_OPEN_CONTEXT *
0x14003505c  call    ?EventTableAttributeRowCount@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_EVENT_TABLE@@@Z; EventTableAttributeRowCount(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_EVENT_TABLE *)
0x140035061  jmp     loc_140034ECA
```
