# p9fs::Plan9VirtioDevice::MemoryAperture::~MemoryAperture(void)

- ea: `0x18002d4c8`
- end: `0x18002d529`
- name: `??1MemoryAperture@Plan9VirtioDevice@p9fs@@UEAA@XZ`
- size: `97`
- prototype: `void(p9fs::Plan9VirtioDevice::MemoryAperture *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002d6f0`

## callees

- `0x18001c75c`
- `0x18002d4c8`

## import_xrefs

- `vmdevicehost!HdvDestroyGuestMemoryAperture` at `0x18002d4f0`
- `vmdevicehost!HdvDestroyGuestMemoryAperture` at `0x18002d4f0`

## string_xrefs

- `0x18002d516`: `onecore\vm\dv\storage\plan9\dll\windows\pcidevicebase.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall p9fs::Plan9VirtioDevice::MemoryAperture::~MemoryAperture(p9fs::Plan9VirtioDevice::MemoryAperture *this)
{
  p9fs::Plan9VirtioDevice::MemoryAperture *v1; // rbx
  void *v2; // rdx
  HRESULT v3; // eax
  const char *v4; // r9
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  p9fs::Plan9VirtioDevice::MemoryAperture *v7; // [rsp+30h] [rbp+8h]

  v1 = this;
  *(_QWORD *)this = &p9fs::Plan9VirtioDevice::MemoryAperture::`vftable';
  v2 = (void *)*((_QWORD *)this + 3);
  if ( v2 )
  {
    v3 = HdvDestroyGuestMemoryAperture(*(HDV_DEVICE *)(*((_QWORD *)this + 2) + 32LL), v2);
    if ( v3 < 0 )
    {
      try
      {
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x88,
          (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\pcidevicebase.h",
          (const char *)(unsigned int)v3,
          v5);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x1AF,
          (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9virtio.cpp",
          v4);
        v1 = v7;
      }
    }
  }
  *((_DWORD *)v1 + 3) = -1073741823;
}

```

## disassembly

```asm
0x18002d4c8  mov     [rsp+arg_0], rcx
0x18002d4cd  push    rbx; int
0x18002d4ce  sub     rsp, 20h
0x18002d4d2  mov     rbx, rcx
0x18002d4d5  lea     rax, ??_7MemoryAperture@Plan9VirtioDevice@p9fs@@6B@; const p9fs::Plan9VirtioDevice::MemoryAperture::`vftable'
0x18002d4dc  mov     [rcx], rax
0x18002d4df  mov     rdx, [rcx+18h]; mappedAddress
0x18002d4e3  test    rdx, rdx
0x18002d4e6  jz      short loc_18002D506
0x18002d4e8  mov     rcx, [rcx+10h]
0x18002d4ec  mov     rcx, [rcx+20h]; requestor
0x18002d4f0  call    cs:__imp_HdvDestroyGuestMemoryAperture
0x18002d4f6  mov     rcx, [rsp+28h]; this
0x18002d4fb  test    eax, eax
0x18002d4fd  js      short loc_18002D513
0x18002d4ff  jmp     short loc_18002D506
0x18002d501  mov     rbx, [rsp+28h+arg_0]
0x18002d506  mov     dword ptr [rbx+0Ch], 0C0000001h
0x18002d50d  add     rsp, 20h
0x18002d511  pop     rbx
0x18002d512  retn
0x18002d513  mov     r9d, eax; char *
0x18002d516  lea     r8, aOnecoreVmDvSto_2; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x18002d51d  mov     edx, 88h; void *
0x18002d522  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
