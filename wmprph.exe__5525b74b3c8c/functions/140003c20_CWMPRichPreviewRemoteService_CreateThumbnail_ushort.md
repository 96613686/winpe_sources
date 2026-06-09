# CWMPRichPreviewRemoteService::CreateThumbnail(ushort * *)

- ea: `0x140003c20`
- end: `0x140003d4b`
- name: `?CreateThumbnail@CWMPRichPreviewRemoteService@@UEAAJPEAPEAG@Z`
- size: `299`
- prototype: `__int64 __fastcall(CWMPRichPreviewRemoteService *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task`

## callees

- `0x140003c20`
- `0x14000d978`
- `0x14000f010`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x140003c4b`
- `KERNEL32!DeleteFileW` at `0x140003c4b`
- `OLEAUT32!__imp_SysAllocString` at `0x140003c6a`
- `OLEAUT32!__imp_SysAllocString` at `0x140003d03`
- `OLEAUT32!__imp_SysAllocString` at `0x140003c6a`
- `OLEAUT32!__imp_SysAllocString` at `0x140003d03`

## pseudocode

```c
__int64 __fastcall CWMPRichPreviewRemoteService::CreateThumbnail(
        CWMPRichPreviewRemoteService *this,
        unsigned __int16 **a2)
{
  unsigned __int16 **v2; // r14
  const WCHAR *v4; // rcx
  _QWORD *v6; // rbx
  __int64 v8; // [rsp+50h] [rbp+8h] BYREF
  __int64 v9; // [rsp+60h] [rbp+18h] BYREF

  v2 = (unsigned __int16 **)((char *)this + 56);
  v4 = (const WCHAR *)*((_QWORD *)this + 7);
  if ( v4 && *v4 )
  {
    DeleteFileW(v4);
    WString::DeleteString(v2);
  }
  v6 = (_QWORD *)*((_QWORD *)this + 4);
  if ( v6[6] )
  {
    v9 = 0;
    v8 = 0;
    if ( v6 )
      (*(void (__fastcall **)(_QWORD *))(*v6 + 8LL))(v6);
    if ( (*(int (__fastcall **)(CWMPRichPreviewRemoteService *, _QWORD, __int64 *))(*(_QWORD *)this + 96LL))(
           this,
           *(_QWORD *)(*((_QWORD *)this + 4) + 56LL),
           &v9) < 0
      || (***(int (__fastcall ****)(_QWORD, GUID *, __int64 *))(*((_QWORD *)this + 4) + 48LL))(
           *(_QWORD *)(*((_QWORD *)this + 4) + 48LL),
           &GUID_3608a1bb_1883_4cc0_9da8_b4cf25943842,
           &v8) < 0
      || (*(int (__fastcall **)(__int64, __int64, unsigned __int16 **, unsigned __int16 **))(*(_QWORD *)v8 + 176LL))(
           v8,
           v9,
           v2,
           a2) < 0 )
    {
      *a2 = SysAllocString(L"res://wmploc/RT_IMAGE/#521");
    }
    if ( v6 )
      (*(void (__fastcall **)(_QWORD *))(*v6 + 16LL))(v6);
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  else
  {
    *a2 = SysAllocString(L"res://wmploc/RT_IMAGE/#521");
  }
  return 0;
}

```

## disassembly

```asm
0x140003c20  mov     [rsp+arg_8], rbx
0x140003c25  mov     [rsp+arg_18], rbp
0x140003c2a  push    rsi
0x140003c2b  push    rdi
0x140003c2c  push    r14
0x140003c2e  sub     rsp, 30h
0x140003c32  lea     r14, [rcx+38h]
0x140003c36  mov     rdi, rcx
0x140003c39  mov     rcx, [r14]; lpFileName
0x140003c3c  xor     ebp, ebp
0x140003c3e  mov     rsi, rdx
0x140003c41  test    rcx, rcx
0x140003c44  jz      short loc_140003C59
0x140003c46  cmp     [rcx], bp
0x140003c49  jz      short loc_140003C59
0x140003c4b  call    cs:__imp_DeleteFileW
0x140003c51  mov     rcx, r14; this
0x140003c54  call    ?DeleteString@WString@@QEAAXXZ; WString::DeleteString(void)
0x140003c59  mov     rbx, [rdi+20h]
0x140003c5d  cmp     [rbx+30h], rbp
0x140003c61  jnz     short loc_140003C78
0x140003c63  lea     rcx, psz; "res://wmploc/RT_IMAGE/#521"
0x140003c6a  call    cs:__imp_SysAllocString
0x140003c70  mov     [rsi], rax
0x140003c73  jmp     loc_140003D36
0x140003c78  mov     [rsp+48h+arg_10], rbp
0x140003c7d  mov     [rsp+48h+arg_0], rbp
0x140003c82  test    rbx, rbx
0x140003c85  jz      short loc_140003C96
0x140003c87  mov     rax, [rbx]
0x140003c8a  mov     rcx, rbx
0x140003c8d  mov     rax, [rax+8]
0x140003c91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003c96  mov     rax, [rdi]
0x140003c99  lea     r8, [rsp+48h+arg_10]
0x140003c9e  mov     rdx, [rdi+20h]
0x140003ca2  mov     rcx, rdi
0x140003ca5  mov     rax, [rax+60h]
0x140003ca9  mov     rdx, [rdx+38h]
0x140003cad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003cb2  test    eax, eax
0x140003cb4  js      short loc_140003CFC
0x140003cb6  mov     rax, [rdi+20h]
0x140003cba  lea     r8, [rsp+48h+arg_0]
0x140003cbf  lea     rdx, _GUID_3608a1bb_1883_4cc0_9da8_b4cf25943842
0x140003cc6  mov     rcx, [rax+30h]
0x140003cca  mov     rax, [rcx]
0x140003ccd  mov     rax, [rax]
0x140003cd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003cd5  test    eax, eax
0x140003cd7  js      short loc_140003CFC
0x140003cd9  mov     rcx, [rsp+48h+arg_0]
0x140003cde  mov     r9, rsi
0x140003ce1  mov     rdx, [rsp+48h+arg_10]
0x140003ce6  mov     r8, r14
0x140003ce9  mov     rax, [rcx]
0x140003cec  mov     rax, [rax+0B0h]
0x140003cf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003cf8  test    eax, eax
0x140003cfa  jns     short loc_140003D0C
0x140003cfc  lea     rcx, psz; "res://wmploc/RT_IMAGE/#521"
0x140003d03  call    cs:__imp_SysAllocString
0x140003d09  mov     [rsi], rax
0x140003d0c  test    rbx, rbx
0x140003d0f  jz      short loc_140003D20
0x140003d11  mov     rax, [rbx]
0x140003d14  mov     rcx, rbx
0x140003d17  mov     rax, [rax+10h]
0x140003d1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003d20  mov     rcx, [rsp+48h+arg_0]
0x140003d25  test    rcx, rcx
0x140003d28  jz      short loc_140003D36
0x140003d2a  mov     rax, [rcx]
0x140003d2d  mov     rax, [rax+10h]
0x140003d31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003d36  mov     rbx, [rsp+48h+arg_8]
0x140003d3b  xor     eax, eax
0x140003d3d  mov     rbp, [rsp+48h+arg_18]
0x140003d42  add     rsp, 30h
0x140003d46  pop     r14
0x140003d48  pop     rdi
0x140003d49  pop     rsi
0x140003d4a  retn
```
