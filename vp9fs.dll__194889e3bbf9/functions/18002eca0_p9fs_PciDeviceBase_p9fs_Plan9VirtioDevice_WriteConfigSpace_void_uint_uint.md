# p9fs::PciDeviceBase<p9fs::Plan9VirtioDevice>::WriteConfigSpace(void *,uint,uint)

- ea: `0x18002eca0`
- end: `0x18002ed60`
- name: `?WriteConfigSpace@?$PciDeviceBase@VPlan9VirtioDevice@p9fs@@@p9fs@@SAJPEAXII@Z`
- size: `192`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180004120`
- `0x180009fe4`
- `0x18002eb6c`
- `0x18002eca0`

## import_xrefs

- `vmvirtio!VirtioWriteConfigSpace` at `0x18002ecf9`
- `vmvirtio!VirtioWriteConfigSpace` at `0x18002ecf9`

## string_xrefs

- `0x18002ed0d`: `onecore\vm\dv\storage\plan9\dll\windows\p9virtio.cpp`

## pseudocode

```c
__int64 __fastcall p9fs::PciDeviceBase<p9fs::Plan9VirtioDevice>::WriteConfigSpace(
        __int64 a1,
        __int64 a2,
        unsigned int a3)
{
  int v4; // eax
  const char *v5; // r9
  unsigned int v6; // ebx
  __int64 result; // rax
  __int64 v8; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v9; // [rsp+38h] [rbp-20h] BYREF
  unsigned int v10; // [rsp+40h] [rbp-18h]
  unsigned int v11; // [rsp+44h] [rbp-14h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v9 = a3;
  v8 = 0;
  v10 = 0;
  v11 = 0;
  v4 = VirtioWriteConfigSpace(*(_QWORD *)(a1 + 136), a2, &v9, &v11);
  v6 = v4;
  if ( v4 >= 0 )
  {
    if ( v10 )
      DeviceRegisters<_VIRTIO_PCI_CAPABILITY>::Write(a1 + 88, v11, v8, v10);
    v6 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9F,
      (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9virtio.cpp",
      (const char *)(unsigned int)v4,
      (int)&v8);
  }
  result = v6;
  while ( 2 )
  {
    try
    {
    }
    catch ( ... )
    {
      v9 = wil::details::in1diag3::Return_CaughtException(
             retaddr,
             (void *)0x59,
             (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\pcidevicebase.h",
             v5);
      result = v9;
      continue;
    }
    break;
  }
  return result;
}

```

## disassembly

```asm
0x18002eca0  mov     r11, rsp
0x18002eca3  mov     [r11+20h], rbx
0x18002eca7  push    rdi
0x18002eca8  sub     rsp, 50h
0x18002ecac  mov     rax, cs:__security_cookie
0x18002ecb3  xor     rax, rsp
0x18002ecb6  mov     [rsp+58h+var_10], rax
0x18002ecbb  mov     rdi, rcx
0x18002ecbe  mov     [r11-20h], r8d
0x18002ecc2  mov     qword ptr [r11-28h], 0
0x18002ecca  mov     [rsp+58h+var_18], 0
0x18002ecd2  mov     [rsp+58h+var_14], 0
0x18002ecda  lea     rax, [r11-18h]
0x18002ecde  mov     [r11-30h], rax
0x18002ece2  lea     rax, [r11-28h]
0x18002ece6  mov     [r11-38h], rax
0x18002ecea  lea     r9, [r11-14h]
0x18002ecee  lea     r8, [r11-20h]
0x18002ecf2  mov     rcx, [rcx+88h]
0x18002ecf9  call    cs:__imp_VirtioWriteConfigSpace
0x18002ecff  mov     ebx, eax
0x18002ed01  test    eax, eax
0x18002ed03  jns     short loc_18002ED20
0x18002ed05  mov     rcx, [rsp+58h]; this
0x18002ed0a  mov     r9d, eax; char *
0x18002ed0d  lea     r8, aOnecoreVmDvSto_0; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x18002ed14  mov     edx, 9Fh; void *
0x18002ed19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ed1e  jmp     short loc_18002ED3F
0x18002ed20  mov     eax, [rsp+58h+var_18]
0x18002ed24  test    eax, eax
0x18002ed26  jz      short loc_18002ED3D
0x18002ed28  mov     r9d, eax
0x18002ed2b  mov     edx, [rsp+58h+var_14]
0x18002ed2f  lea     rcx, [rdi+58h]
0x18002ed33  mov     r8, [rsp+58h+var_28]
0x18002ed38  call    ?Write@?$DeviceRegisters@U_VIRTIO_PCI_CAPABILITY@@@@QEAAX_KPEBX0@Z; DeviceRegisters<_VIRTIO_PCI_CAPABILITY>::Write(unsigned __int64,void const *,unsigned __int64)
0x18002ed3d  xor     ebx, ebx
0x18002ed3f  mov     eax, ebx
0x18002ed41  jmp     short loc_18002ED47
0x18002ed43  mov     eax, [rsp+58h+var_20]
0x18002ed47  mov     rcx, [rsp+58h+var_10]
0x18002ed4c  xor     rcx, rsp; StackCookie
0x18002ed4f  call    __security_check_cookie
0x18002ed54  mov     rbx, [rsp+58h+arg_18]
0x18002ed59  add     rsp, 50h
0x18002ed5d  pop     rdi
0x18002ed5e  retn
```
