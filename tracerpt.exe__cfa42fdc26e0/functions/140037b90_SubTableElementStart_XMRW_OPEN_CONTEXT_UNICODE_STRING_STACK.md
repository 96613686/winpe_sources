# SubTableElementStart(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING_STACK *)

- ea: `0x140037b90`
- end: `0x140037d23`
- name: `?SubTableElementStart@@YAKPEAU_XMRW_OPEN_CONTEXT@@PEAU_UNICODE_STRING_STACK@@@Z`
- size: `403`
- prototype: `__int64 __fastcall(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING_STACK *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140032dcc`

## callees

- `0x140016808`
- `0x14003694c`
- `0x140037ac4`
- `0x140037b90`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall SubTableElementStart(struct _XMRW_OPEN_CONTEXT *a1, struct _UNICODE_STRING_STACK *a2)
{
  struct _TRACERPT_EVENT_TABLE *v2; // rsi
  __int64 v4; // rbx
  __int64 result; // rax
  __int64 v6; // rcx
  WCHAR *v7; // [rsp+20h] [rbp-40h] BYREF
  WCHAR *v8; // [rsp+28h] [rbp-38h] BYREF
  struct _UNICODE_STRING v9; // [rsp+30h] [rbp-30h]
  struct _UNICODE_STRING v10; // [rsp+40h] [rbp-20h] BYREF
  struct _UNICODE_STRING v11; // [rsp+50h] [rbp-10h] BYREF
  int v12; // [rsp+80h] [rbp+20h] BYREF
  int v13; // [rsp+90h] [rbp+30h] BYREF
  unsigned int v14; // [rsp+98h] [rbp+38h] BYREF

  v2 = (struct _TRACERPT_EVENT_TABLE *)*((_QWORD *)a1 + 10);
  v7 = 0;
  v12 = 0;
  v14 = 0;
  v9 = 0;
  if ( !v2 )
    return 0;
  if ( !a2 )
    return 0;
  if ( *((_DWORD *)a1 + 12) != 5 )
    return 0;
  v4 = *((_QWORD *)a1 + 3);
  v10 = *(struct _UNICODE_STRING *)((char *)a2 + 8);
  if ( !EqualString(&v10, L"EventTable", 0) )
    return 0;
  while ( 1 )
  {
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 72LL))(v4);
    if ( (_DWORD)result )
      break;
    ++*((_DWORD *)a1 + 11);
    (*(void (__fastcall **)(__int64, WCHAR **, int *))(*(_QWORD *)v4 + 112LL))(v4, &v7, &v12);
    v6 = *((_QWORD *)a1 + 3);
    v9.Buffer = v7;
    v8 = 0;
    v9.MaximumLength = 2 * v12;
    v9.Length = 2 * v12;
    v13 = 0;
    v10 = 0;
    (*(void (__fastcall **)(__int64, WCHAR **, int *))(*(_QWORD *)v6 + 128LL))(v6, &v8, &v13);
    v10.Buffer = v8;
    v11 = v9;
    v10.MaximumLength = 2 * v13;
    v10.Length = 2 * v13;
    if ( EqualString(&v11, L"rowcount", 0) )
    {
      result = SubTableAttributeRowCount(a1, &v10, v2);
      if ( (_DWORD)result )
        return result;
    }
  }
  if ( (int)result >= 0 )
  {
    if ( (*((_BYTE *)v2 + 681) & 5) != 1 )
    {
      (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v4 + 168LL))(v4, &v14);
      PrintMessage(0x45Du, v14);
      return 3221745221LL;
    }
    *((_BYTE *)v2 + 681) |= 4u;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140037b90  mov     [rsp-18h+arg_8], rbx
0x140037b95  push    rbp
0x140037b96  push    rsi
0x140037b97  push    rdi
0x140037b98  mov     rbp, rsp
0x140037b9b  sub     rsp, 60h
0x140037b9f  mov     rsi, [rcx+50h]
0x140037ba3  xorps   xmm0, xmm0
0x140037ba6  mov     [rbp+var_40], 0
0x140037bae  mov     rdi, rcx
0x140037bb1  mov     [rbp+arg_0], 0
0x140037bb8  mov     [rbp+arg_18], 0
0x140037bbf  movups  [rbp+var_30], xmm0
0x140037bc3  test    rsi, rsi
0x140037bc6  jz      short loc_140037BFB
0x140037bc8  test    rdx, rdx
0x140037bcb  jz      short loc_140037BFB
0x140037bcd  cmp     dword ptr [rcx+30h], 5
0x140037bd1  jnz     short loc_140037BFB
0x140037bd3  movups  xmm0, xmmword ptr [rdx+8]
0x140037bd7  mov     rbx, [rcx+18h]
0x140037bdb  lea     rdx, aEventtable; "EventTable"
0x140037be2  xor     r8d, r8d; unsigned __int8
0x140037be5  lea     rcx, [rbp+var_20]; struct _UNICODE_STRING
0x140037be9  movdqu  xmmword ptr [rbp+var_20.Length], xmm0
0x140037bee  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140037bf3  test    al, al
0x140037bf5  jnz     loc_140037CBD
0x140037bfb  xor     eax, eax
0x140037bfd  mov     rbx, [rsp+60h+arg_8]
0x140037c05  add     rsp, 60h
0x140037c09  pop     rdi
0x140037c0a  pop     rsi
0x140037c0b  pop     rbp
0x140037c0c  retn
0x140037c0d  inc     dword ptr [rdi+2Ch]
0x140037c10  lea     r8, [rbp+arg_0]
0x140037c14  mov     rax, [rbx]
0x140037c17  lea     rdx, [rbp+var_40]
0x140037c1b  mov     rcx, rbx
0x140037c1e  mov     rax, [rax+70h]
0x140037c22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037c27  mov     rax, [rbp+var_40]
0x140037c2b  lea     r8, [rbp+arg_10]
0x140037c2f  mov     rcx, [rdi+18h]
0x140037c33  lea     rdx, [rbp+var_38]
0x140037c37  mov     qword ptr [rbp+var_30+8], rax
0x140037c3b  xorps   xmm0, xmm0
0x140037c3e  movzx   eax, word ptr [rbp+arg_0]
0x140037c42  add     ax, ax
0x140037c45  mov     [rbp+var_38], 0
0x140037c4d  mov     word ptr [rbp+var_30+2], ax
0x140037c51  mov     word ptr [rbp+var_30], ax
0x140037c55  mov     [rbp+arg_10], 0
0x140037c5c  movups  xmmword ptr [rbp+var_20.Length], xmm0
0x140037c60  mov     rax, [rcx]
0x140037c63  mov     rax, [rax+80h]
0x140037c6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037c6f  mov     rax, [rbp+var_38]
0x140037c73  lea     rdx, aRowcount; "rowcount"
0x140037c7a  movaps  xmm0, [rbp+var_30]
0x140037c7e  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140037c82  mov     [rbp+var_20.Buffer], rax
0x140037c86  xor     r8d, r8d; unsigned __int8
0x140037c89  movzx   eax, word ptr [rbp+arg_10]
0x140037c8d  add     ax, ax
0x140037c90  movdqa  xmmword ptr [rbp+var_10.Length], xmm0
0x140037c95  mov     [rbp+var_20.MaximumLength], ax
0x140037c99  mov     [rbp+var_20.Length], ax
0x140037c9d  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140037ca2  test    al, al
0x140037ca4  jz      short loc_140037CBD
0x140037ca6  mov     r8, rsi; struct _TRACERPT_EVENT_TABLE *
0x140037ca9  lea     rdx, [rbp+var_20]; struct _UNICODE_STRING *
0x140037cad  mov     rcx, rdi; struct _XMRW_OPEN_CONTEXT *
0x140037cb0  call    ?SubTableAttributeRowCount@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_EVENT_TABLE@@@Z; SubTableAttributeRowCount(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_EVENT_TABLE *)
0x140037cb5  test    eax, eax
0x140037cb7  jnz     loc_140037BFD
0x140037cbd  mov     rax, [rbx]
0x140037cc0  mov     rcx, rbx
0x140037cc3  mov     rax, [rax+48h]
0x140037cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037ccc  test    eax, eax
0x140037cce  jz      loc_140037C0D
0x140037cd4  js      loc_140037BFD
0x140037cda  mov     cl, [rsi+2A9h]
0x140037ce0  mov     al, cl
0x140037ce2  and     al, 5
0x140037ce4  cmp     al, 1
0x140037ce6  jnz     short loc_140037CF6
0x140037ce8  or      cl, 4
0x140037ceb  mov     [rsi+2A9h], cl
0x140037cf1  jmp     loc_140037BFB
0x140037cf6  mov     rax, [rbx]
0x140037cf9  lea     rdx, [rbp+arg_18]
0x140037cfd  mov     rcx, rbx
0x140037d00  mov     rax, [rax+0A8h]
0x140037d07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037d0c  mov     edx, [rbp+arg_18]
0x140037d0f  mov     ecx, 45Dh; unsigned int
0x140037d14  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x140037d19  mov     eax, 0C007EE45h
0x140037d1e  jmp     loc_140037BFD
```
