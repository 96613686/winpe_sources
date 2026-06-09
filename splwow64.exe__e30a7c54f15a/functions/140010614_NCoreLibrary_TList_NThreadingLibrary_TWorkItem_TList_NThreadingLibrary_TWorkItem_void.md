# NCoreLibrary::TList<NThreadingLibrary::TWorkItem>::~TList<NThreadingLibrary::TWorkItem>(void)

- ea: `0x140010614`
- end: `0x14001065b`
- name: `??1?$TList@VTWorkItem@NThreadingLibrary@@@NCoreLibrary@@QEAA@XZ`
- size: `71`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140010810`
- `0x1400131c4`

## callees

- `0x140010614`
- `0x140014038`
- `0x140016010`

## pseudocode

```c
void __fastcall NCoreLibrary::TList<NThreadingLibrary::TWorkItem>::~TList<NThreadingLibrary::TWorkItem>(__int64 a1)
{
  __int64 v1; // rbx
  NCoreLibrary::TLink *v2; // rdi
  void (__fastcall ***v3)(_QWORD, __int64); // rcx

  v1 = *(_QWORD *)(a1 + 24);
  v2 = (NCoreLibrary::TLink *)(a1 + 8);
  while ( (NCoreLibrary::TLink *)v1 != v2 )
  {
    v3 = (void (__fastcall ***)(_QWORD, __int64))v1;
    v1 = *(_QWORD *)(v1 + 16);
    if ( v3 )
      (**v3)(v3, 1);
  }
  NCoreLibrary::TLink::~TLink(v2);
}

```

## disassembly

```asm
0x140010614  mov     [rsp+arg_0], rbx
0x140010619  push    rdi
0x14001061a  sub     rsp, 20h
0x14001061e  mov     rbx, [rcx+18h]
0x140010622  lea     rdi, [rcx+8]
0x140010626  jmp     short loc_140010644
0x140010628  mov     rcx, rbx
0x14001062b  mov     rbx, [rbx+10h]
0x14001062f  test    rcx, rcx
0x140010632  jz      short loc_140010644
0x140010634  mov     rax, [rcx]
0x140010637  mov     edx, 1
0x14001063c  mov     rax, [rax]
0x14001063f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010644  cmp     rbx, rdi
0x140010647  jnz     short loc_140010628
0x140010649  mov     rcx, rdi; this
0x14001064c  mov     rbx, [rsp+28h+arg_0]
0x140010651  add     rsp, 20h
0x140010655  pop     rdi
0x140010656  jmp     ??1TLink@NCoreLibrary@@UEAA@XZ; NCoreLibrary::TLink::~TLink(void)
```
