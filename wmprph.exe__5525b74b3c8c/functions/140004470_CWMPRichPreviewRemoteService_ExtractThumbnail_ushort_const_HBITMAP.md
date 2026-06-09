# CWMPRichPreviewRemoteService::ExtractThumbnail(ushort const *,HBITMAP__ * *)

- ea: `0x140004470`
- end: `0x14000453a`
- name: `?ExtractThumbnail@CWMPRichPreviewRemoteService@@EEAAJPEBGPEAPEAUHBITMAP__@@@Z`
- size: `202`
- prototype: `__int64 __fastcall(CWMPRichPreviewRemoteService *__hidden this, const unsigned __int16 *, HBITMAP *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x140004470`
- `0x14000f010`

## pseudocode

```c
__int64 __fastcall CWMPRichPreviewRemoteService::ExtractThumbnail(
        CWMPRichPreviewRemoteService *this,
        const unsigned __int16 *a2,
        HBITMAP *a3)
{
  _QWORD *v6; // rsi
  bool v7; // zf
  int v8; // edi
  int v9; // [rsp+60h] [rbp+8h] BYREF
  __int64 v10; // [rsp+78h] [rbp+20h] BYREF

  if ( !*((_QWORD *)this + 5) )
    return 2147500037LL;
  v6 = (_QWORD *)((char *)this + 48);
  v9 = 0;
  v7 = *((_QWORD *)this + 6) == 0;
  v10 = 0;
  if ( !v7
    || (v8 = (*(__int64 (__fastcall **)(CWMPRichPreviewRemoteService *, const unsigned __int16 *, __int64 *))(*(_QWORD *)this + 88LL))(
               this,
               a2,
               &v10),
        v8 >= 0)
    && (v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, _QWORD *, int *, _QWORD))(**((_QWORD **)this + 5)
                                                                                                  + 24LL))(
               *((_QWORD *)this + 5),
               v10,
               128,
               0,
               v6,
               &v9,
               0),
        v8 >= 0) )
  {
    v8 = (*(__int64 (__fastcall **)(_QWORD, HBITMAP *))(*(_QWORD *)*v6 + 24LL))(*v6, a3);
  }
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140004470  mov     [rsp+arg_8], rbx
0x140004475  push    rbp
0x140004476  push    rsi
0x140004477  push    rdi
0x140004478  sub     rsp, 40h
0x14000447c  cmp     qword ptr [rcx+28h], 0
0x140004481  mov     rbp, r8
0x140004484  mov     rbx, rcx
0x140004487  jnz     short loc_140004493
0x140004489  mov     eax, 80004005h
0x14000448e  jmp     loc_14000452D
0x140004493  lea     rsi, [rcx+30h]
0x140004497  mov     [rsp+58h+arg_0], 0
0x14000449f  cmp     qword ptr [rsi], 0
0x1400044a3  mov     [rsp+58h+arg_18], 0
0x1400044ac  jnz     short loc_140004501
0x1400044ae  mov     rax, [rcx]
0x1400044b1  lea     r8, [rsp+58h+arg_18]
0x1400044b6  mov     rax, [rax+58h]
0x1400044ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400044bf  mov     edi, eax
0x1400044c1  test    eax, eax
0x1400044c3  js      short loc_140004515
0x1400044c5  mov     rcx, [rbx+28h]
0x1400044c9  lea     rdx, [rsp+58h+arg_0]
0x1400044ce  mov     [rsp+58h+var_28], 0
0x1400044d7  xor     r9d, r9d
0x1400044da  mov     [rsp+58h+var_30], rdx
0x1400044df  mov     r8d, 80h
0x1400044e5  mov     rdx, [rsp+58h+arg_18]
0x1400044ea  mov     rax, [rcx]
0x1400044ed  mov     [rsp+58h+var_38], rsi
0x1400044f2  mov     rax, [rax+18h]
0x1400044f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400044fb  mov     edi, eax
0x1400044fd  test    eax, eax
0x1400044ff  js      short loc_140004515
0x140004501  mov     rcx, [rsi]
0x140004504  mov     rdx, rbp
0x140004507  mov     rax, [rcx]
0x14000450a  mov     rax, [rax+18h]
0x14000450e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004513  mov     edi, eax
0x140004515  mov     rcx, [rsp+58h+arg_18]
0x14000451a  test    rcx, rcx
0x14000451d  jz      short loc_14000452B
0x14000451f  mov     rax, [rcx]
0x140004522  mov     rax, [rax+10h]
0x140004526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000452b  mov     eax, edi
0x14000452d  mov     rbx, [rsp+58h+arg_8]
0x140004532  add     rsp, 40h
0x140004536  pop     rdi
0x140004537  pop     rsi
0x140004538  pop     rbp
0x140004539  retn
```
