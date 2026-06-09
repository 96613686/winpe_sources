# com::application_reputation_static::~application_reputation_static(void)

- ea: `0x18000abc8`
- end: `0x18000ac07`
- name: `??1application_reputation_static@com@@UEAA@XZ`
- size: `63`
- prototype: `void __fastcall(com::application_reputation_static *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000af20`

## callees

- `0x180008828`
- `0x18000aba0`

## pseudocode

```c
void __fastcall com::application_reputation_static::~application_reputation_static(
        com::application_reputation_static *this)
{
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)this + 30);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)this + 29);
  api_guard::~api_guard((com::application_reputation_static *)((char *)this + 96));
  *((_DWORD *)this + 17) = -1073741823;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)this + 4);
}

```

## disassembly

```asm
0x18000abc8  push    rbx
0x18000abca  sub     rsp, 20h
0x18000abce  mov     rbx, rcx
0x18000abd1  add     rcx, 0F0h
0x18000abd8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000abdd  lea     rcx, [rbx+0E8h]
0x18000abe4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000abe9  lea     rcx, [rbx+60h]; this
0x18000abed  call    ??1api_guard@@QEAA@XZ; api_guard::~api_guard(void)
0x18000abf2  lea     rcx, [rbx+20h]
0x18000abf6  mov     dword ptr [rbx+44h], 0C0000001h
0x18000abfd  add     rsp, 20h
0x18000ac01  pop     rbx
0x18000ac02  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
