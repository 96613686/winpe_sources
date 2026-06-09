# XMLOutputHelper::XMLOutputHelper(IMalloc *,IStream *,int,wchar_t const *,bool,bool,bool)

- ea: `0x100421280`
- end: `0x100421390`
- name: `??0XMLOutputHelper@@IEAA@PEAUIMalloc@@PEAUIStream@@HPEB_W_N33@Z`
- size: `272`
- prototype: `XMLOutputHelper *__fastcall(XMLOutputHelper *__hidden this, struct IMalloc *, struct IStream *, int, const wchar_t *, bool, bool, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x10041d960`

## callees

- `0x100421280`
- `0x100439df0`

## pseudocode

```c
XMLOutputHelper *__fastcall XMLOutputHelper::XMLOutputHelper(
        XMLOutputHelper *this,
        struct IMalloc *a2,
        struct IStream *a3,
        int a4,
        const wchar_t *a5,
        bool a6,
        bool a7,
        bool a8)
{
  XMLOutputHelper *result; // rax

  *((_QWORD *)this + 1) = a2;
  *(_QWORD *)this = &OutputHelper::`vftable'{for `Base'};
  *((_QWORD *)this + 2) = &OutputHelper::`vftable'{for `EncodingWriterContext'};
  *((_QWORD *)this + 8) = &EncodingWriter::`vftable';
  *((_QWORD *)this + 9) = a2;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_DWORD *)this + 34) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 29) = 0;
  if ( a3 )
    ((void (__fastcall *)(struct IStream *))a3->lpVtbl->AddRef)(a3);
  *((_QWORD *)this + 29) = a3;
  *((_DWORD *)this + 14) = a4;
  *((_QWORD *)this + 4) = (char *)this + 4290;
  *((_BYTE *)this + 61) = a7;
  *((_BYTE *)this + 62) = a8;
  *((_WORD *)this + 84) = 0;
  *((_QWORD *)this + 27) = (char *)this + 168;
  *(_QWORD *)this = &XMLOutputHelper::`vftable'{for `Base'};
  *((_QWORD *)this + 2) = &XMLOutputHelper::`vftable'{for `EncodingWriterContext'};
  result = this;
  *((_DWORD *)this + 13) = 0;
  *((_BYTE *)this + 60) = 0;
  *((_WORD *)this + 120) = 0;
  *((_QWORD *)this + 5) = (char *)this + 242;
  *((_QWORD *)this + 3) = (char *)this + 242;
  *((_DWORD *)this + 56) = 24;
  return result;
}

```

## disassembly

```asm
0x100421280  mov     [rsp+arg_0], rbx
0x100421285  mov     [rsp+arg_8], rbp
0x10042128a  mov     [rsp+arg_10], rsi
0x10042128f  push    rdi
0x100421290  sub     rsp, 20h
0x100421294  xor     ebp, ebp
0x100421296  mov     [rcx+8], rdx
0x10042129a  lea     rax, ??_7OutputHelper@@6BBase@@@; const OutputHelper::`vftable'{for `Base'}
0x1004212a1  mov     esi, r9d
0x1004212a4  mov     [rcx], rax
0x1004212a7  lea     rax, ??_7OutputHelper@@6BEncodingWriterContext@@@; const OutputHelper::`vftable'{for `EncodingWriterContext'}
0x1004212ae  mov     [rcx+10h], rax
0x1004212b2  lea     rax, ??_7EncodingWriter@@6B@; const EncodingWriter::`vftable'
0x1004212b9  mov     [rcx+40h], rax
0x1004212bd  mov     rdi, r8
0x1004212c0  mov     [rcx+48h], rdx
0x1004212c4  mov     rbx, rcx
0x1004212c7  mov     [rcx+50h], rbp
0x1004212cb  mov     [rcx+68h], rbp
0x1004212cf  mov     [rcx+80h], rbp
0x1004212d6  mov     [rcx+88h], ebp
0x1004212dc  mov     [rcx+0A0h], rbp
0x1004212e3  mov     [rcx+98h], rbp
0x1004212ea  mov     [rcx+0E8h], rbp
0x1004212f1  test    r8, r8
0x1004212f4  jz      short loc_100421306
0x1004212f6  mov     rax, [r8]
0x1004212f9  mov     rcx, r8
0x1004212fc  mov     rax, [rax+8]
0x100421300  call    cs:__guard_dispatch_icall_fptr
0x100421306  mov     [rbx+0E8h], rdi
0x10042130d  lea     rcx, [rbx+0F2h]
0x100421314  lea     rax, [rcx+0FD0h]
0x10042131b  mov     [rbx+38h], esi
0x10042131e  mov     rsi, [rsp+28h+arg_10]
0x100421323  mov     [rbx+20h], rax
0x100421327  movzx   eax, [rsp+28h+arg_30]
0x10042132c  mov     [rbx+3Dh], al
0x10042132f  movzx   eax, [rsp+28h+arg_38]
0x100421334  mov     [rbx+3Eh], al
0x100421337  lea     rax, [rbx+0A8h]
0x10042133e  mov     [rax], bp
0x100421341  mov     [rbx+0D8h], rax
0x100421348  lea     rax, ??_7XMLOutputHelper@@6BBase@@@; const XMLOutputHelper::`vftable'{for `Base'}
0x10042134f  mov     [rbx], rax
0x100421352  lea     rax, ??_7XMLOutputHelper@@6BEncodingWriterContext@@@; const XMLOutputHelper::`vftable'{for `EncodingWriterContext'}
0x100421359  mov     [rbx+10h], rax
0x10042135d  mov     rax, rbx
0x100421360  mov     [rbx+34h], ebp
0x100421363  mov     [rbx+3Ch], bpl
0x100421367  mov     [rbx+0F0h], bp
0x10042136e  mov     rbp, [rsp+28h+arg_8]
0x100421373  mov     [rbx+28h], rcx
0x100421377  mov     [rbx+18h], rcx
0x10042137b  mov     dword ptr [rbx+0E0h], 18h
0x100421385  mov     rbx, [rsp+28h+arg_0]
0x10042138a  add     rsp, 20h
0x10042138e  pop     rdi
0x10042138f  retn
```
