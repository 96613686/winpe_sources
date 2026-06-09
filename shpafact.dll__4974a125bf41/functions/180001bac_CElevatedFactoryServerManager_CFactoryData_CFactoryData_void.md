# CElevatedFactoryServerManager::CFactoryData::~CFactoryData(void)

- ea: `0x180001bac`
- end: `0x180001be2`
- name: `??1CFactoryData@CElevatedFactoryServerManager@@UEAA@XZ`
- size: `54`
- prototype: `void __fastcall(CElevatedFactoryServerManager::CFactoryData *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001c80`

## callees

- `0x180001bac`
- `0x180004010`

## pseudocode

```c
void __fastcall CElevatedFactoryServerManager::CFactoryData::~CFactoryData(
        CElevatedFactoryServerManager::CFactoryData *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &CElevatedFactoryServerManager::CFactoryData::`vftable';
  v2 = *((_QWORD *)this + 3);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 3) = 0;
  }
}

```

## disassembly

```asm
0x180001bac  push    rbx
0x180001bae  sub     rsp, 20h
0x180001bb2  lea     rax, ??_7CFactoryData@CElevatedFactoryServerManager@@6B@; const CElevatedFactoryServerManager::CFactoryData::`vftable'
0x180001bb9  mov     rbx, rcx
0x180001bbc  mov     [rcx], rax
0x180001bbf  mov     rcx, [rcx+18h]
0x180001bc3  test    rcx, rcx
0x180001bc6  jz      short loc_180001BDC
0x180001bc8  mov     rax, [rcx]
0x180001bcb  mov     rax, [rax+10h]
0x180001bcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001bd4  mov     qword ptr [rbx+18h], 0
0x180001bdc  add     rsp, 20h
0x180001be0  pop     rbx
0x180001be1  retn
```
