# EventFieldAttributesCheck(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_FIELD *)

- ea: `0x1400339c8`
- end: `0x140033ba6`
- name: `?EventFieldAttributesCheck@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_FIELD@@@Z`
- size: `478`
- prototype: `unsigned int __fastcall(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING *, struct _TRACERPT_FIELD *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140033ec4`

## callees

- `0x140016808`
- `0x140030910`
- `0x140033414`
- `0x14003357c`
- `0x14003364c`
- `0x140033810`
- `0x1400338f8`
- `0x1400339c8`
- `0x14003694c`
- `0x140041010`

## pseudocode

```c
unsigned int __fastcall EventFieldAttributesCheck(
        struct _XMRW_OPEN_CONTEXT *a1,
        struct _UNICODE_STRING *a2,
        struct _TRACERPT_FIELD *a3)
{
  __int64 v4; // rcx
  struct _UNICODE_STRING v7; // xmm0
  char v9; // al
  struct _UNICODE_STRING v10; // [rsp+20h] [rbp-20h] BYREF
  struct _UNICODE_STRING v11; // [rsp+30h] [rbp-10h] BYREF
  int v12; // [rsp+60h] [rbp+20h] BYREF
  unsigned int v13; // [rsp+68h] [rbp+28h] BYREF
  WCHAR *v14; // [rsp+78h] [rbp+38h] BYREF

  v14 = 0;
  v4 = *((_QWORD *)a1 + 3);
  v12 = 0;
  v10 = 0;
  (*(void (__fastcall **)(__int64, WCHAR **, int *))(*(_QWORD *)v4 + 128LL))(v4, &v14, &v12);
  v7 = *a2;
  v10.Buffer = v14;
  v10.MaximumLength = 2 * v12;
  v10.Length = 2 * v12;
  v11 = v7;
  if ( EqualString(&v11, L"field", 0) )
    return EventFieldAttributeField(a1, &v10, a3);
  v11 = *a2;
  if ( EqualString(&v11, L"payloadGuid", 0) )
    return EventFieldAttributeProviderID(a1, &v10, a3);
  v11 = *a2;
  if ( EqualString(&v11, L"payloadId", 0) )
    return EventFieldAttributeEventID(a1, &v10, a3);
  v11 = *a2;
  if ( EqualString(&v11, L"version", 0) )
    return EventFieldAttributeVersion(a1, &v10, a3);
  v11 = *a2;
  if ( EqualString(&v11, L"aggregate", 0) )
    return EventFieldAttributeAggregate(a1, &v10, a3);
  v11 = *a2;
  if ( EqualString(&v11, L"note", 0) )
  {
    v9 = *((_BYTE *)a3 + 216);
    v13 = 0;
    if ( v9 < 0 )
    {
      (*(void (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)a1 + 3) + 168LL))(*((_QWORD *)a1 + 3), &v13);
      PrintMessage(0x44Du, v13);
      return -1073222143;
    }
    *((_BYTE *)a3 + 32) = 1;
    *((_BYTE *)a3 + 216) = v9 | 0x80;
    RPT_STRING::operator=((__int64)a3, (const void **)&v10);
  }
  return 0;
}

```

## disassembly

```asm
0x1400339c8  mov     [rsp-18h+arg_10], rbx
0x1400339cd  push    rbp
0x1400339ce  push    rsi
0x1400339cf  push    rdi
0x1400339d0  mov     rbp, rsp
0x1400339d3  sub     rsp, 40h
0x1400339d7  mov     rdi, rcx
0x1400339da  mov     [rbp+arg_18], 0
0x1400339e2  mov     rcx, [rcx+18h]
0x1400339e6  xorps   xmm0, xmm0
0x1400339e9  mov     [rbp+arg_0], 0
0x1400339f0  mov     rbx, r8
0x1400339f3  movups  xmmword ptr [rbp+var_20.Length], xmm0
0x1400339f7  mov     rsi, rdx
0x1400339fa  lea     r8, [rbp+arg_0]
0x1400339fe  mov     rax, [rcx]
0x140033a01  lea     rdx, [rbp+arg_18]
0x140033a05  mov     rax, [rax+80h]
0x140033a0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033a11  mov     rax, [rbp+arg_18]
0x140033a15  lea     rdx, aField; "field"
0x140033a1c  movups  xmm0, xmmword ptr [rsi]
0x140033a1f  mov     [rbp+var_20.Buffer], rax
0x140033a23  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140033a27  movzx   eax, word ptr [rbp+arg_0]
0x140033a2b  xor     r8d, r8d; unsigned __int8
0x140033a2e  add     ax, ax
0x140033a31  mov     [rbp+var_20.MaximumLength], ax
0x140033a35  mov     [rbp+var_20.Length], ax
0x140033a39  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140033a3e  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140033a43  test    al, al
0x140033a45  jz      short loc_140033A5B
0x140033a47  mov     r8, rbx; struct _TRACERPT_FIELD *
0x140033a4a  lea     rdx, [rbp+var_20]; struct _UNICODE_STRING *
0x140033a4e  mov     rcx, rdi; struct _XMRW_OPEN_CONTEXT *
0x140033a51  call    ?EventFieldAttributeField@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_FIELD@@@Z; EventFieldAttributeField(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_FIELD *)
0x140033a56  jmp     loc_140033B99
0x140033a5b  movups  xmm0, xmmword ptr [rsi]
0x140033a5e  xor     r8d, r8d; unsigned __int8
0x140033a61  lea     rdx, aPayloadguid; "payloadGuid"
0x140033a68  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140033a6c  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140033a71  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140033a76  test    al, al
0x140033a78  jz      short loc_140033A8E
0x140033a7a  mov     r8, rbx; struct _TRACERPT_FIELD *
0x140033a7d  lea     rdx, [rbp+var_20]; struct _UNICODE_STRING *
0x140033a81  mov     rcx, rdi; struct _XMRW_OPEN_CONTEXT *
0x140033a84  call    ?EventFieldAttributeProviderID@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_FIELD@@@Z; EventFieldAttributeProviderID(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_FIELD *)
0x140033a89  jmp     loc_140033B99
0x140033a8e  movups  xmm0, xmmword ptr [rsi]
0x140033a91  xor     r8d, r8d; unsigned __int8
0x140033a94  lea     rdx, aPayloadid; "payloadId"
0x140033a9b  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140033a9f  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140033aa4  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140033aa9  test    al, al
0x140033aab  jz      short loc_140033AC1
0x140033aad  mov     r8, rbx; struct _TRACERPT_FIELD *
0x140033ab0  lea     rdx, [rbp+var_20]; struct _UNICODE_STRING *
0x140033ab4  mov     rcx, rdi; struct _XMRW_OPEN_CONTEXT *
0x140033ab7  call    ?EventFieldAttributeEventID@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_FIELD@@@Z; EventFieldAttributeEventID(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_FIELD *)
0x140033abc  jmp     loc_140033B99
0x140033ac1  movups  xmm0, xmmword ptr [rsi]
0x140033ac4  xor     r8d, r8d; unsigned __int8
0x140033ac7  lea     rdx, aVersion; "version"
0x140033ace  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140033ad2  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140033ad7  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140033adc  test    al, al
0x140033ade  jz      short loc_140033AF4
0x140033ae0  mov     r8, rbx; struct _TRACERPT_FIELD *
0x140033ae3  lea     rdx, [rbp+var_20]; struct _UNICODE_STRING *
0x140033ae7  mov     rcx, rdi; struct _XMRW_OPEN_CONTEXT *
0x140033aea  call    ?EventFieldAttributeVersion@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_FIELD@@@Z; EventFieldAttributeVersion(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_FIELD *)
0x140033aef  jmp     loc_140033B99
0x140033af4  movups  xmm0, xmmword ptr [rsi]
0x140033af7  xor     r8d, r8d; unsigned __int8
0x140033afa  lea     rdx, aAggregate; "aggregate"
0x140033b01  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140033b05  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140033b0a  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140033b0f  test    al, al
0x140033b11  jz      short loc_140033B24
0x140033b13  mov     r8, rbx; struct _TRACERPT_FIELD *
0x140033b16  lea     rdx, [rbp+var_20]; struct _UNICODE_STRING *
0x140033b1a  mov     rcx, rdi; struct _XMRW_OPEN_CONTEXT *
0x140033b1d  call    ?EventFieldAttributeAggregate@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_FIELD@@@Z; EventFieldAttributeAggregate(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_FIELD *)
0x140033b22  jmp     short loc_140033B99
0x140033b24  movups  xmm0, xmmword ptr [rsi]
0x140033b27  xor     r8d, r8d; unsigned __int8
0x140033b2a  lea     rdx, aNote; "note"
0x140033b31  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140033b35  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140033b3a  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140033b3f  test    al, al
0x140033b41  jz      short loc_140033B97
0x140033b43  mov     al, [rbx+0D8h]
0x140033b49  mov     [rbp+arg_8], 0
0x140033b50  test    al, al
0x140033b52  jns     short loc_140033B7F
0x140033b54  mov     rcx, [rdi+18h]
0x140033b58  lea     rdx, [rbp+arg_8]
0x140033b5c  mov     rax, [rcx]
0x140033b5f  mov     rax, [rax+0A8h]
0x140033b66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033b6b  mov     edx, [rbp+arg_8]
0x140033b6e  mov     ecx, 44Dh; unsigned int
0x140033b73  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140033b78  mov     eax, 0C007EE01h
0x140033b7d  jmp     short loc_140033B99
0x140033b7f  or      al, 80h
0x140033b81  mov     byte ptr [rbx+20h], 1
0x140033b85  lea     rdx, [rbp+var_20]
0x140033b89  mov     [rbx+0D8h], al
0x140033b8f  mov     rcx, rbx
0x140033b92  call    ??4RPT_STRING@@QEAAPEBV0@AEAU_UNICODE_STRING@@@Z; RPT_STRING::operator=(_UNICODE_STRING &)
0x140033b97  xor     eax, eax
0x140033b99  mov     rbx, [rsp+40h+arg_10]
0x140033b9e  add     rsp, 40h
0x140033ba2  pop     rdi
0x140033ba3  pop     rsi
0x140033ba4  pop     rbp
0x140033ba5  retn
```
