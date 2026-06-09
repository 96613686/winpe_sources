# NCoreLibrary::TLink::~TLink(void)

- ea: `0x140014038`
- end: `0x140014070`
- name: `??1TLink@NCoreLibrary@@UEAA@XZ`
- size: `56`
- prototype: `void __fastcall(NCoreLibrary::TLink *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140010614`
- `0x1400106ec`
- `0x140010964`
- `0x1400132a8`
- `0x140014080`

## callees

- `0x140014038`

## pseudocode

```c
void __fastcall NCoreLibrary::TLink::~TLink(NCoreLibrary::TLink *this)
{
  NCoreLibrary::TLink *v2; // rcx
  NCoreLibrary::TLink *v3; // rax

  *(_QWORD *)this = &NCoreLibrary::TLink::`vftable';
  v2 = (NCoreLibrary::TLink *)*((_QWORD *)this + 2);
  if ( v2 != this )
  {
    v3 = (NCoreLibrary::TLink *)*((_QWORD *)this + 3);
    if ( v3 != this )
    {
      *((_QWORD *)v2 + 3) = v3;
      *(_QWORD *)(*((_QWORD *)this + 3) + 16LL) = *((_QWORD *)this + 2);
      *((_QWORD *)this + 2) = this;
      *((_QWORD *)this + 3) = this;
    }
  }
}

```

## disassembly

```asm
0x140014038  mov     rdx, rcx
0x14001403b  lea     rax, ??_7TLink@NCoreLibrary@@6B@; const NCoreLibrary::TLink::`vftable'
0x140014042  mov     [rcx], rax
0x140014045  mov     rcx, [rcx+10h]
0x140014049  cmp     rcx, rdx
0x14001404c  jz      short locret_14001406F
0x14001404e  mov     rax, [rdx+18h]
0x140014052  cmp     rax, rdx
0x140014055  jz      short locret_14001406F
0x140014057  mov     [rcx+18h], rax
0x14001405b  mov     rcx, [rdx+18h]
0x14001405f  mov     rax, [rdx+10h]
0x140014063  mov     [rcx+10h], rax
0x140014067  mov     [rdx+10h], rdx
0x14001406b  mov     [rdx+18h], rdx
0x14001406f  retn
```
