# XmlReader::OpenInputMemory(void const *,unsigned __int64,long *)

- ea: `0x180039184`
- end: `0x180039262`
- name: `?OpenInputMemory@XmlReader@@QEAAXPEBX_KPEAJ@Z`
- size: `222`
- prototype: `void __fastcall(xp::XmlReader **this, const void *, unsigned __int64, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18003a720`

## callees

- `0x18001ee78`
- `0x18003538c`
- `0x180039184`
- `0x180039268`
- `0x18003a6d8`
- `0x18004c010`

## string_xrefs

- `0x18003923d`: `OpenInputMemory`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall XmlReader::OpenInputMemory(xp::XmlReader **this, const void *a2, unsigned __int64 a3, int *a4)
{
  xp::XmlReader *v8; // r12
  int v9; // edi
  unsigned int v10; // r9d
  struct IStream *v11; // rbx
  bool v12; // [rsp+20h] [rbp-38h]
  const wchar_t *v13; // [rsp+28h] [rbp-30h]
  struct IStream *v14; // [rsp+60h] [rbp+8h] BYREF

  v8 = *this;
  v14 = 0;
  v9 = xp::XmlReader::CreateMemoryStream(a2, a3, &v14);
  if ( v9 >= 0 )
  {
    v11 = v14;
    v9 = (*(__int64 (__fastcall **)(xp::XmlReader *, struct IStream *))(*(_QWORD *)v8 + 24LL))(v8, v14);
    (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v11 + 16LL))(v11);
  }
  if ( v9 >= 0 )
    v9 = ReadToElement(*this);
  *a4 = 0;
  if ( v9 == -1072897938 || (unsigned int)(v9 + 1072894462) <= 2 )
  {
    *a4 = v9;
    v9 = xp::XmlReader::OpenInputMemoryWithEncodingCodePage(*this, a2, a3, v10, v12, v13);
    if ( v9 >= 0 )
      v9 = ReadToElement(*this);
  }
  XmlReader::ThrowIfFailed((XmlReader *)this, "OpenInputMemory", v9);
}

```

## disassembly

```asm
0x180039184  mov     rax, rsp
0x180039187  mov     [rax+10h], rbx
0x18003918b  mov     [rax+18h], rbp
0x18003918f  push    rsi
0x180039190  push    rdi
0x180039191  push    r12
0x180039193  push    r14
0x180039195  push    r15
0x180039197  sub     rsp, 30h
0x18003919b  mov     r14, r9
0x18003919e  mov     rbp, r8
0x1800391a1  mov     r15, rdx
0x1800391a4  mov     rsi, rcx
0x1800391a7  mov     r12, [rcx]
0x1800391aa  mov     qword ptr [rax+8], 0
0x1800391b2  lea     r8, [rax+8]; struct IStream **
0x1800391b6  mov     rdx, rbp; unsigned __int64
0x1800391b9  mov     rcx, r15; void *
0x1800391bc  call    ?CreateMemoryStream@XmlReader@xp@@SAJPEBX_KPEAPEAUIStream@@@Z; xp::XmlReader::CreateMemoryStream(void const *,unsigned __int64,IStream * *)
0x1800391c1  mov     edi, eax
0x1800391c3  test    eax, eax
0x1800391c5  js      short loc_1800391F1
0x1800391c7  mov     rax, [r12]
0x1800391cb  mov     rbx, [rsp+58h+arg_0]
0x1800391d0  mov     rdx, rbx
0x1800391d3  mov     rcx, r12
0x1800391d6  mov     rax, [rax+18h]
0x1800391da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800391df  mov     edi, eax
0x1800391e1  mov     rax, [rbx]
0x1800391e4  mov     rcx, rbx
0x1800391e7  mov     rax, [rax+10h]
0x1800391eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800391f0  nop
0x1800391f1  test    edi, edi
0x1800391f3  js      short loc_1800391FF
0x1800391f5  mov     rcx, [rsi]; this
0x1800391f8  call    ReadToElement
0x1800391fd  mov     edi, eax
0x1800391ff  mov     dword ptr [r14], 0
0x180039206  cmp     edi, 0C00CE06Eh
0x18003920c  jz      short loc_180039219
0x18003920e  lea     eax, [rdi+3FF311FEh]
0x180039214  cmp     eax, 2
0x180039217  ja      short loc_18003923A
0x180039219  mov     [r14], edi
0x18003921c  mov     r8, rbp; unsigned __int64
0x18003921f  mov     rdx, r15; void *
0x180039222  mov     rcx, [rsi]; this
0x180039225  call    ?OpenInputMemoryWithEncodingCodePage@XmlReader@xp@@QEAAJPEBX_KI_NPEB_W@Z; xp::XmlReader::OpenInputMemoryWithEncodingCodePage(void const *,unsigned __int64,uint,bool,wchar_t const *)
0x18003922a  mov     edi, eax
0x18003922c  test    eax, eax
0x18003922e  js      short loc_18003923A
0x180039230  mov     rcx, [rsi]; this
0x180039233  call    ReadToElement
0x180039238  mov     edi, eax
0x18003923a  mov     r8d, edi; int
0x18003923d  lea     rdx, aOpeninputmemor; "OpenInputMemory"
0x180039244  mov     rcx, rsi; this
0x180039247  mov     rbx, [rsp+58h+arg_8]
0x18003924c  mov     rbp, [rsp+58h+arg_10]
0x180039251  add     rsp, 30h
0x180039255  pop     r15
0x180039257  pop     r14
0x180039259  pop     r12
0x18003925b  pop     rdi
0x18003925c  pop     rsi
0x18003925d  jmp     ?ThrowIfFailed@XmlReader@@AEBAXPEBDJ@Z; XmlReader::ThrowIfFailed(char const *,long)
```
