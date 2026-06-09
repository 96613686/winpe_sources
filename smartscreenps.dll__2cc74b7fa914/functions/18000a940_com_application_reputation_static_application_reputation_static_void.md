# com::application_reputation_static::~application_reputation_static(void)

- ea: `0x18000a940`
- end: `0x18000a97f`
- name: `??1application_reputation_static@com@@UEAA@XZ`
- size: `63`
- prototype: `void __fastcall(com::application_reputation_static *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ac90`

## callees

- `0x18000871c`
- `0x18000a918`

## pseudocode

```c
void __fastcall com::application_reputation_static::~application_reputation_static(
        com::application_reputation_static *this)
{
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 240);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 232);
  api_guard::~api_guard((com::application_reputation_static *)((char *)this + 96));
  *((_DWORD *)this + 17) = -1073741823;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 32);
}

```

## disassembly

```asm
0x18000a940  push    rbx
0x18000a942  sub     rsp, 20h
0x18000a946  mov     rbx, rcx
0x18000a949  add     rcx, 0F0h
0x18000a950  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000a955  lea     rcx, [rbx+0E8h]
0x18000a95c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000a961  lea     rcx, [rbx+60h]; this
0x18000a965  call    ??1api_guard@@QEAA@XZ; api_guard::~api_guard(void)
0x18000a96a  lea     rcx, [rbx+20h]
0x18000a96e  mov     dword ptr [rbx+44h], 0C0000001h
0x18000a975  add     rsp, 20h
0x18000a979  pop     rbx
0x18000a97a  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
