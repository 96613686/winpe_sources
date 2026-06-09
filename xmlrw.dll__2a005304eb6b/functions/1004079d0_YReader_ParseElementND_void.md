# YReader::ParseElementND(void)

- ea: `0x1004079d0`
- end: `0x100407b80`
- name: `?ParseElementND@YReader@@AEAAXXZ`
- size: `432`
- prototype: `void __fastcall(YReader *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x100401780`
- `0x1004019c0`
- `0x1004079d0`
- `0x10040ae50`
- `0x10040b230`
- `0x10040b4c0`
- `0x10040c8e0`
- `0x1004157a0`
- `0x1004169d0`
- `0x100439df0`

## pseudocode

```c
void __fastcall YReader::ParseElementND(YReader *this)
{
  char *v1; // rbx
  unsigned int v3; // ecx
  _QWORD *v4; // rsi
  __int64 v5; // rax
  __int64 v6; // rcx
  void (__fastcall *v7)(char *); // rax
  struct DeclElement *v8; // rax
  char *v9; // rbx
  __int64 v10; // rcx
  __int64 v11; // rax

  v1 = (char *)this + 1864;
  v3 = *((_DWORD *)this + 472);
  if ( *((_DWORD *)v1 + 7) == v3 )
  {
    _stack<YReader::Element,16>::grow((__int64)v1, 0);
    v3 = *((_DWORD *)v1 + 6);
  }
  *((_DWORD *)v1 + 6) = v3 + 1;
  v4 = (_QWORD *)((char *)this + 1568);
  *((_QWORD *)this + 349) = *((_QWORD *)v1 + 2) + 56LL * v3;
  YReader::GetTokenQName(this, (YReader *)((char *)this + 1568), (YReader *)((char *)this + 1584));
  ++*((_DWORD *)this + 132);
  v5 = *((_QWORD *)this + 55);
  *((_QWORD *)this + 350) = 0;
  v6 = *(_QWORD *)(v5 + 16);
  v7 = (void (__fastcall *)(char *))*((_QWORD *)this + 194);
  *((_QWORD *)this + 231) = v6;
  v7((char *)this + *((int *)this + 390));
  *((_QWORD *)this + 230) = *(_QWORD *)(*((_QWORD *)this + 55) + 16LL);
  v8 = DeclDoctype::LookupElement((YReader *)((char *)this + 1256), (YReader *)((char *)this + 1568));
  if ( v8 && *((_DWORD *)v8 + 20) )
  {
    v9 = (char *)v8 + 56;
    YReader::GraftNsAttDefsN((__int64)this, (__int64)v8 + 56);
    YReader::GraftAttDefs(this, v9);
  }
  YReader::ProcessAttributesN(this);
  v10 = *((unsigned int *)this + 398);
  if ( (_DWORD)v10 )
  {
    *((_QWORD *)this + 202) = *v4 + 2LL + 2 * v10;
    *((_DWORD *)this + 406) = *((_DWORD *)this + 394) - v10 - 1;
  }
  else
  {
    *((_OWORD *)this + 101) = *(_OWORD *)v4;
  }
  if ( !NamespaceSupport::ProcessPrefix(
          (YReader *)((char *)this + 512),
          (YReader *)((char *)this + 1584),
          (YReader *)((char *)this + 1600)) )
  {
    MXRRaiseException(-1072894363);
    JUMPOUT(0x100407B7FLL);
  }
  *(_OWORD *)*((_QWORD *)this + 349) = *(_OWORD *)v4;
  *(_OWORD *)(*((_QWORD *)this + 349) + 16LL) = *((_OWORD *)this + 100);
  *(_OWORD *)(*((_QWORD *)this + 349) + 32LL) = *((_OWORD *)this + 101);
  v11 = *((_QWORD *)this + 349);
  *((_BYTE *)this + 1784) = 1;
  *(_DWORD *)(v11 + 48) = 0;
}

```

## disassembly

```asm
0x1004079d0  mov     [rsp+arg_0], rbx
0x1004079d5  mov     [rsp+arg_8], rbp
0x1004079da  mov     [rsp+arg_10], rsi
0x1004079df  mov     [rsp+arg_18], rdi
0x1004079e4  push    r14
0x1004079e6  sub     rsp, 20h
0x1004079ea  lea     rbx, [rcx+748h]
0x1004079f1  mov     rdi, rcx
0x1004079f4  mov     ecx, [rbx+18h]
0x1004079f7  cmp     [rbx+1Ch], ecx
0x1004079fa  jnz     short loc_100407A09
0x1004079fc  xor     edx, edx
0x1004079fe  mov     rcx, rbx
0x100407a01  call    ?grow@?$_stack@UElement@YReader@@$0BA@@@AEAAXI@Z; _stack<YReader::Element,16>::grow(uint)
0x100407a06  mov     ecx, [rbx+18h]
0x100407a09  lea     eax, [rcx+1]
0x100407a0c  mov     [rbx+18h], eax
0x100407a0f  lea     rsi, [rdi+620h]
0x100407a16  mov     eax, ecx
0x100407a18  lea     r8, [rdi+630h]; struct StringPtr *
0x100407a1f  imul    rcx, rax, 38h ; '8'
0x100407a23  mov     rdx, rsi; struct StringPtr *
0x100407a26  add     rcx, [rbx+10h]
0x100407a2a  mov     [rdi+0AE8h], rcx
0x100407a31  mov     rcx, rdi; this
0x100407a34  call    ?GetTokenQName@YReader@@AEAAXPEAUStringPtr@@0@Z; YReader::GetTokenQName(StringPtr *,StringPtr *)
0x100407a39  inc     dword ptr [rdi+210h]
0x100407a3f  mov     rax, [rdi+1B8h]
0x100407a46  mov     qword ptr [rdi+0AF0h], 0
0x100407a51  mov     rcx, [rax+10h]
0x100407a55  mov     rax, [rdi+610h]
0x100407a5c  mov     [rdi+738h], rcx
0x100407a63  movsxd  rcx, dword ptr [rdi+618h]
0x100407a6a  add     rcx, rdi
0x100407a6d  call    cs:__guard_dispatch_icall_fptr
0x100407a73  mov     rax, [rdi+1B8h]
0x100407a7a  mov     rdx, rsi; struct StringPtr *
0x100407a7d  mov     rcx, [rax+10h]
0x100407a81  mov     [rdi+730h], rcx
0x100407a88  lea     rcx, [rdi+4E8h]; this
0x100407a8f  call    ?LookupElement@DeclDoctype@@QEAAPEAVDeclElement@@PEAUStringPtr@@@Z; DeclDoctype::LookupElement(StringPtr *)
0x100407a94  test    rax, rax
0x100407a97  jz      short loc_100407AB9
0x100407a99  cmp     dword ptr [rax+50h], 0
0x100407a9d  jz      short loc_100407AB9
0x100407a9f  lea     rbx, [rax+38h]
0x100407aa3  mov     rcx, rdi
0x100407aa6  mov     rdx, rbx
0x100407aa9  call    ?GraftNsAttDefsN@YReader@@AEAAXPEAV?$_stack@PEAVDeclAttDef@@$03@@@Z; YReader::GraftNsAttDefsN(_stack<DeclAttDef *,4> *)
0x100407aae  mov     rdx, rbx
0x100407ab1  mov     rcx, rdi
0x100407ab4  call    ?GraftAttDefs@YReader@@AEAAXPEAV?$_stack@PEAVDeclAttDef@@$03@@@Z; YReader::GraftAttDefs(_stack<DeclAttDef *,4> *)
0x100407ab9  mov     rcx, rdi; this
0x100407abc  call    ?ProcessAttributesN@YReader@@AEAAXXZ; YReader::ProcessAttributesN(void)
0x100407ac1  mov     ecx, [rdi+638h]
0x100407ac7  test    ecx, ecx
0x100407ac9  jnz     short loc_100407AD7
0x100407acb  movups  xmm0, xmmword ptr [rsi]
0x100407ace  movups  xmmword ptr [rdi+650h], xmm0
0x100407ad5  jmp     short loc_100407AF6
0x100407ad7  mov     rax, [rsi]
0x100407ada  add     rax, 2
0x100407ade  lea     r8, [rax+rcx*2]
0x100407ae2  mov     [rdi+650h], r8
0x100407ae9  mov     eax, [rsi+8]
0x100407aec  sub     eax, ecx
0x100407aee  dec     eax
0x100407af0  mov     [rdi+658h], eax
0x100407af6  lea     r8, [rdi+640h]; struct StringPtr *
0x100407afd  lea     rdx, [rdi+630h]; struct StringPtr *
0x100407b04  lea     rcx, [rdi+200h]; this
0x100407b0b  call    ?ProcessPrefix@NamespaceSupport@@QEAA_NPEAUStringPtr@@0@Z; NamespaceSupport::ProcessPrefix(StringPtr *,StringPtr *)
0x100407b10  test    al, al
0x100407b12  jz      short loc_100407B75
0x100407b14  mov     rax, [rdi+0AE8h]
0x100407b1b  movups  xmm0, xmmword ptr [rsi]
0x100407b1e  mov     rbx, [rsp+28h+arg_0]
0x100407b23  mov     rbp, [rsp+28h+arg_8]
0x100407b28  mov     rsi, [rsp+28h+arg_10]
0x100407b2d  movups  xmmword ptr [rax], xmm0
0x100407b30  mov     rax, [rdi+0AE8h]
0x100407b37  movups  xmm0, xmmword ptr [rdi+640h]
0x100407b3e  movups  xmmword ptr [rax+10h], xmm0
0x100407b42  mov     rax, [rdi+0AE8h]
0x100407b49  movups  xmm0, xmmword ptr [rdi+650h]
0x100407b50  movups  xmmword ptr [rax+20h], xmm0
0x100407b54  mov     rax, [rdi+0AE8h]
0x100407b5b  mov     byte ptr [rdi+6F8h], 1
0x100407b62  mov     rdi, [rsp+28h+arg_18]
0x100407b67  mov     dword ptr [rax+30h], 0
0x100407b6e  add     rsp, 20h
0x100407b72  pop     r14
0x100407b74  retn
0x100407b75  mov     ecx, 0C00CEE65h; int
0x100407b7a  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
