# MSXML2::IXMLDOMNode::Gettext(void)

- ea: `0x180029680`
- end: `0x180029738`
- name: `?Gettext@IXMLDOMNode@MSXML2@@QEAA?AV_bstr_t@@XZ`
- size: `184`
- prototype: `_QWORD *__fastcall(struct IUnknown *, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023974`

## callees

- `0x180002590`
- `0x1800029c0`
- `0x180029680`
- `0x18003127c`
- `0x180031290`
- `0x180033010`

## pseudocode

```c
_QWORD *__fastcall MSXML2::IXMLDOMNode::Gettext(struct IUnknown *a1, _QWORD *a2)
{
  int v4; // eax
  __int64 v5; // rdi
  _QWORD *v6; // rax
  __int64 v8; // [rsp+30h] [rbp-18h] BYREF

  v8 = 0;
  v4 = ((__int64 (__fastcall *)(struct IUnknown *, __int64 *))a1->lpVtbl[8].Release)(a1, &v8);
  if ( v4 < 0 )
    _com_issue_errorex(v4, a1, &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60);
  v5 = v8;
  v6 = operator new(0x18u);
  if ( v6 )
  {
    *(_OWORD *)v6 = 0;
    v6[2] = 0;
    v6[1] = 0;
    *((_DWORD *)v6 + 4) = 1;
    *v6 = v5;
  }
  *a2 = v6;
  if ( !v6 )
    _com_issue_error(-2147024882);
  return a2;
}

```

## disassembly

```asm
0x180029680  mov     [rsp+arg_10], rbx
0x180029685  push    rdi
0x180029686  sub     rsp, 40h
0x18002968a  mov     rax, cs:__security_cookie
0x180029691  xor     rax, rsp
0x180029694  mov     [rsp+48h+var_10], rax
0x180029699  mov     rbx, rdx
0x18002969c  mov     rdi, rcx
0x18002969f  mov     [rsp+48h+var_18], rdx
0x1800296a4  mov     [rsp+48h+var_18], 0
0x1800296ad  mov     rax, [rcx]
0x1800296b0  lea     rdx, [rsp+48h+var_18]
0x1800296b5  mov     rax, [rax+0D0h]
0x1800296bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800296c1  test    eax, eax
0x1800296c3  js      short loc_180029726
0x1800296c5  mov     rdi, [rsp+48h+var_18]
0x1800296ca  mov     ecx, 18h; Size
0x1800296cf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800296d4  mov     [rsp+48h+var_20], rax
0x1800296d9  test    rax, rax
0x1800296dc  jz      short loc_1800296F8
0x1800296de  xorps   xmm0, xmm0
0x1800296e1  xor     ecx, ecx
0x1800296e3  movups  xmmword ptr [rax], xmm0
0x1800296e6  mov     [rax+10h], rcx
0x1800296ea  mov     [rax+8], rcx
0x1800296ee  mov     dword ptr [rax+10h], 1
0x1800296f5  mov     [rax], rdi
0x1800296f8  mov     [rbx], rax
0x1800296fb  test    rax, rax
0x1800296fe  jz      short loc_18002971B
0x180029700  mov     rax, rbx
0x180029703  mov     rcx, [rsp+48h+var_10]
0x180029708  xor     rcx, rsp; StackCookie
0x18002970b  call    __security_check_cookie
0x180029710  mov     rbx, [rsp+48h+arg_10]
0x180029715  add     rsp, 40h
0x180029719  pop     rdi
0x18002971a  retn
0x18002971b  mov     ecx, 8007000Eh; int
0x180029720  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180029726  lea     r8, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60; struct _GUID *
0x18002972d  mov     rdx, rdi; struct IUnknown *
0x180029730  mov     ecx, eax; int
0x180029732  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
```
