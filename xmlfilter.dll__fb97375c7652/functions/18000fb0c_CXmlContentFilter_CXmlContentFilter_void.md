# CXmlContentFilter::CXmlContentFilter(void)

- ea: `0x18000fb0c`
- end: `0x18000fbf1`
- name: `??0CXmlContentFilter@@QEAA@XZ`
- size: `229`
- prototype: `CXmlContentFilter *__fastcall(CXmlContentFilter *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x180011574`
- `0x1800116b0`

## callees

- `0x18000c188`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
CXmlContentFilter *__fastcall CXmlContentFilter::CXmlContentFilter(CXmlContentFilter *this)
{
  char *v2; // rbx
  char *v3; // rcx

  *((_DWORD *)this + 6) = 0;
  *((_OWORD *)this + 2) = 0;
  *((_OWORD *)this + 3) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_BYTE *)this + 72) = 0;
  *((_QWORD *)this + 10) = 0;
  v2 = (char *)this + 88;
  *((_QWORD *)this + 12) = 0;
  *((_BYTE *)this + 104) = 0;
  *((_QWORD *)this + 11) = &CFilterImpContentHandler::`vftable';
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_BYTE *)this + 128) = 0;
  v3 = (char *)this + 136;
  *(_QWORD *)v3 = 16;
  *((_QWORD *)v3 + 1) = 0;
  *((_QWORD *)v3 + 7) = v3 + 16;
  *((_WORD *)v3 + 8) = 0;
  TVarString<16>::SetMinimalSize(v3, 4096);
  v2[116] = 0;
  *((_QWORD *)v2 + 15) = v2 + 136;
  v2[128] = 0;
  *((_DWORD *)v2 + 98) = 0;
  *(_QWORD *)(v2 + 396) = 64;
  *((_QWORD *)v2 + 51) = 0;
  *((_QWORD *)v2 + 52) = 0;
  *((_DWORD *)v2 + 106) = 0;
  *((_BYTE *)this + 520) = 0;
  *((_QWORD *)this + 66) = 0;
  *((_BYTE *)this + 536) = 0;
  return this;
}

```

## disassembly

```asm
0x18000fb0c  mov     r11, rsp
0x18000fb0f  mov     [r11+18h], rbx
0x18000fb13  mov     [r11+20h], rsi
0x18000fb17  mov     [r11+8], rcx
0x18000fb1b  push    rdi
0x18000fb1c  sub     rsp, 30h
0x18000fb20  mov     rdi, rcx
0x18000fb23  xor     esi, esi
0x18000fb25  mov     [rcx+18h], esi
0x18000fb28  xorps   xmm0, xmm0
0x18000fb2b  xor     eax, eax
0x18000fb2d  movups  xmmword ptr [rcx+20h], xmm0
0x18000fb31  movups  xmmword ptr [rcx+30h], xmm0
0x18000fb35  mov     [rcx+40h], rax
0x18000fb39  mov     [rcx+48h], sil
0x18000fb3d  mov     [rcx+50h], rsi
0x18000fb41  lea     rbx, [rcx+58h]
0x18000fb45  mov     [r11+10h], rbx
0x18000fb49  mov     [rbx+8], rsi
0x18000fb4d  mov     [rbx+10h], sil
0x18000fb51  lea     rax, ??_7CFilterImpContentHandler@@6B@; const CFilterImpContentHandler::`vftable'
0x18000fb58  mov     [rbx], rax
0x18000fb5b  xor     eax, eax
0x18000fb5d  mov     [rbx+18h], rax
0x18000fb61  mov     [rbx+20h], rsi
0x18000fb65  mov     [rbx+28h], sil
0x18000fb69  lea     rcx, [rbx+30h]
0x18000fb6d  mov     qword ptr [rcx], 10h
0x18000fb74  mov     [rcx+8], rsi
0x18000fb78  lea     rdx, [rcx+10h]
0x18000fb7c  mov     [rcx+38h], rdx
0x18000fb80  mov     [rdx], si
0x18000fb83  mov     edx, 1000h
0x18000fb88  call    ?SetMinimalSize@?$TVarString@$0BA@@@QEAAX_K@Z; TVarString<16>::SetMinimalSize(unsigned __int64)
0x18000fb8d  nop
0x18000fb8e  mov     [rbx+74h], sil
0x18000fb92  lea     rax, [rbx+88h]
0x18000fb99  mov     [rbx+78h], rax
0x18000fb9d  mov     [rbx+80h], sil
0x18000fba4  mov     [rbx+188h], esi
0x18000fbaa  mov     qword ptr [rbx+18Ch], 40h ; '@'
0x18000fbb5  mov     [rbx+198h], rsi
0x18000fbbc  mov     [rbx+1A0h], rsi
0x18000fbc3  mov     [rbx+1A8h], esi
0x18000fbc9  mov     [rdi+208h], sil
0x18000fbd0  mov     [rdi+210h], rsi
0x18000fbd7  mov     [rdi+218h], sil
0x18000fbde  mov     rax, rdi
0x18000fbe1  mov     rbx, [rsp+38h+arg_10]
0x18000fbe6  mov     rsi, [rsp+38h+arg_18]
0x18000fbeb  add     rsp, 30h
0x18000fbef  pop     rdi
0x18000fbf0  retn
```
