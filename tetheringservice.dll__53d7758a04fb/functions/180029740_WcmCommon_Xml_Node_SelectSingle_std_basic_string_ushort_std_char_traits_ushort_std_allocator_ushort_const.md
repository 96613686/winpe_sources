# WcmCommon::Xml::Node::SelectSingle(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180029740`
- end: `0x18002989f`
- name: `?SelectSingle@Node@Xml@WcmCommon@@QEBA?AV?$shared_ptr@VNode@Xml@WcmCommon@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@@Z`
- size: `351`
- prototype: `struct NodeVtbl *__fastcall(struct IUnknown ***, struct NodeVtbl *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023974`

## callees

- `0x180002590`
- `0x1800029c0`
- `0x180028678`
- `0x180028be8`
- `0x180028c8c`
- `0x180028e74`
- `0x180029740`
- `0x18003127c`
- `0x180031290`
- `0x180033010`

## pseudocode

```c
struct NodeVtbl *__fastcall WcmCommon::Xml::Node::SelectSingle(
        struct IUnknown ***a1,
        struct NodeVtbl *a2,
        const unsigned __int16 *a3)
{
  struct IUnknown *v4; // rbx
  _bstr_t *v5; // rdi
  _QWORD *v6; // rdx
  int v7; // eax
  struct NodeVtbl *v8; // rbx
  WcmCommon::Xml::Node *v9; // rdi
  WcmCommon::Xml::Node *v10; // rax
  struct Node v12; // [rsp+20h] [rbp-30h] BYREF
  int v13; // [rsp+28h] [rbp-28h]
  _bstr_t *v14; // [rsp+30h] [rbp-20h]
  WcmCommon::Xml::Node *v15; // [rsp+38h] [rbp-18h] BYREF

  v12.lpVtbl = a2;
  v13 = 0;
  v4 = **a1;
  if ( !v4 )
    _com_issue_error(-2147467261);
  if ( *((_QWORD *)a3 + 3) > 7u )
    a3 = *(const unsigned __int16 **)a3;
  v5 = _bstr_t::_bstr_t((_bstr_t *)&v12, a3);
  v14 = v5;
  v15 = 0;
  v6 = *(_QWORD **)v5;
  if ( *(_QWORD *)v5 )
    v6 = (_QWORD *)*v6;
  v7 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD *, WcmCommon::Xml::Node **))v4->lpVtbl[12].AddRef)(
         v4,
         v6,
         &v15);
  if ( v7 < 0 )
    _com_issue_errorex(v7, v4, &GUID_2933bf80_7b36_11d2_b20e_00c04f983e60);
  v8 = (struct NodeVtbl *)v15;
  v14 = v15;
  _bstr_t::~_bstr_t(v5);
  if ( v8 )
  {
    v9 = (WcmCommon::Xml::Node *)operator new(0x10u);
    v15 = v9;
    *(_OWORD *)v9 = 0;
    v12.lpVtbl = v8;
    (*((void (__fastcall **)(struct NodeVtbl *))v8->QueryInterface + 1))(v8);
    v13 = 5;
    v10 = WcmCommon::Xml::Node::Node(v9, &v12);
    std::shared_ptr<WcmCommon::Xml::Document>::shared_ptr<WcmCommon::Xml::Document>(a2, (__int64)v10);
    (*((void (__fastcall **)(struct NodeVtbl *))v8->QueryInterface + 2))(v8);
    (*((void (__fastcall **)(struct NodeVtbl *))v8->QueryInterface + 2))(v8);
  }
  else
  {
    a2->QueryInterface = 0;
    a2->AddRef = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x180029740  mov     [rsp-18h+arg_18], rbx
0x180029745  push    rbp
0x180029746  push    rsi
0x180029747  push    rdi
0x180029748  mov     rbp, rsp
0x18002974b  sub     rsp, 50h
0x18002974f  mov     rax, cs:__security_cookie
0x180029756  xor     rax, rsp
0x180029759  mov     [rbp+var_10], rax
0x18002975d  mov     rsi, rdx
0x180029760  mov     [rbp+var_30.lpVtbl], rdx
0x180029764  mov     [rbp+var_28], 0
0x18002976b  mov     rax, [rcx]
0x18002976e  mov     rbx, [rax]
0x180029771  test    rbx, rbx
0x180029774  jz      loc_180029894
0x18002977a  cmp     qword ptr [r8+18h], 7
0x18002977f  jbe     short loc_180029784
0x180029781  mov     r8, [r8]
0x180029784  mov     rdx, r8; unsigned __int16 *
0x180029787  lea     rcx, [rbp+var_30]; this
0x18002978b  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180029790  mov     rdi, rax
0x180029793  mov     [rbp+var_20], rax
0x180029797  mov     [rbp+var_18], 0
0x18002979f  mov     rax, [rbx]
0x1800297a2  mov     rdx, [rdi]
0x1800297a5  test    rdx, rdx
0x1800297a8  jz      short loc_1800297AD
0x1800297aa  mov     rdx, [rdx]
0x1800297ad  lea     r8, [rbp+var_18]
0x1800297b1  mov     rcx, rbx
0x1800297b4  mov     rax, [rax+128h]
0x1800297bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800297c0  test    eax, eax
0x1800297c2  js      loc_180029882
0x1800297c8  mov     rbx, [rbp+var_18]
0x1800297cc  mov     [rbp+var_20], rbx
0x1800297d0  mov     rcx, rdi; this
0x1800297d3  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800297d8  nop
0x1800297d9  test    rbx, rbx
0x1800297dc  jz      loc_180029871
0x1800297e2  mov     ecx, 10h; Size
0x1800297e7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800297ec  mov     rdi, rax
0x1800297ef  mov     [rbp+var_18], rax
0x1800297f3  xorps   xmm0, xmm0
0x1800297f6  movups  xmmword ptr [rax], xmm0
0x1800297f9  mov     [rbp+var_30.lpVtbl], rbx
0x1800297fd  mov     rax, [rbx]
0x180029800  mov     rcx, rbx
0x180029803  mov     rax, [rax+8]
0x180029807  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002980c  nop
0x18002980d  mov     [rbp+var_28], 5
0x180029814  lea     rdx, [rbp+var_30]; struct Node *
0x180029818  mov     rcx, rdi; this
0x18002981b  call    ??0Node@Xml@WcmCommon@@AEAA@AEBU0Details@12@@Z; WcmCommon::Xml::Node::Node(WcmCommon::Xml::Details::Node const &)
0x180029820  nop
0x180029821  mov     rdx, rax
0x180029824  mov     rcx, rsi
0x180029827  call    ??$?0VDocument@Xml@WcmCommon@@$0A@@?$shared_ptr@VDocument@Xml@WcmCommon@@@std@@QEAA@PEAVDocument@Xml@WcmCommon@@@Z; std::shared_ptr<WcmCommon::Xml::Document>::shared_ptr<WcmCommon::Xml::Document>(WcmCommon::Xml::Document *)
0x18002982c  nop
0x18002982d  test    rbx, rbx
0x180029830  jz      short loc_180029842
0x180029832  mov     rax, [rbx]
0x180029835  mov     rcx, rbx
0x180029838  mov     rax, [rax+10h]
0x18002983c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029841  nop
0x180029842  mov     rcx, [rbx]
0x180029845  mov     rax, [rcx+10h]
0x180029849  mov     rcx, rbx
0x18002984c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029851  nop
0x180029852  mov     rax, rsi
0x180029855  mov     rcx, [rbp+var_10]
0x180029859  xor     rcx, rsp; StackCookie
0x18002985c  call    __security_check_cookie
0x180029861  mov     rbx, [rsp+50h+arg_18]
0x180029869  add     rsp, 50h
0x18002986d  pop     rdi
0x18002986e  pop     rsi
0x18002986f  pop     rbp
0x180029870  retn
0x180029871  mov     qword ptr [rsi], 0
0x180029878  mov     qword ptr [rsi+8], 0
0x180029880  jmp     short loc_180029852
0x180029882  lea     r8, _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60; struct _GUID *
0x180029889  mov     rdx, rbx; struct IUnknown *
0x18002988c  mov     ecx, eax; int
0x18002988e  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x180029894  mov     ecx, 80004003h; int
0x180029899  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
