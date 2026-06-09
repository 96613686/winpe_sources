# CUwfStaticVolumeConfiguration::set_SwapfileSize(ulong)

- ea: `0x18000cef0`
- end: `0x18000cf39`
- name: `?set_SwapfileSize@CUwfStaticVolumeConfiguration@@QEAAJK@Z`
- size: `73`
- prototype: `__int64 __fastcall(CUwfConfiguration **this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x18001a620`

## callees

- `0x18000a150`
- `0x18000cef0`

## pseudocode

```c
__int64 __fastcall CUwfStaticVolumeConfiguration::set_SwapfileSize(CUwfConfiguration **this, unsigned int a2)
{
  int updated; // edx

  if ( *((_BYTE *)this + 9) )
  {
    updated = -2147024891;
  }
  else
  {
    updated = CUwfConfiguration::UpdateDWORDValue(this[3], (struct CUwfRegKey *)(this + 2), L"SwapfileSize", a2, 1);
    if ( updated >= 0 )
      return 0;
  }
  *((_DWORD *)this[3] + 4) = updated;
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18000cef0  push    rbx
0x18000cef2  sub     rsp, 30h
0x18000cef6  cmp     byte ptr [rcx+9], 0
0x18000cefa  mov     r9d, edx; unsigned int
0x18000cefd  mov     rbx, rcx
0x18000cf00  jz      short loc_18000CF16
0x18000cf02  mov     edx, 80070005h
0x18000cf07  mov     rax, [rbx+18h]
0x18000cf0b  mov     [rax+10h], edx
0x18000cf0e  mov     eax, edx
0x18000cf10  add     rsp, 30h
0x18000cf14  pop     rbx
0x18000cf15  retn
0x18000cf16  lea     rdx, [rcx+10h]; struct CUwfRegKey *
0x18000cf1a  mov     [rsp+38h+var_18], 1; bool
0x18000cf1f  mov     rcx, [rcx+18h]; this
0x18000cf23  lea     r8, aSwapfilesize; "SwapfileSize"
0x18000cf2a  call    ?UpdateDWORDValue@CUwfConfiguration@@QEAAJAEAVCUwfRegKey@@PEBGK_N@Z; CUwfConfiguration::UpdateDWORDValue(CUwfRegKey &,ushort const *,ulong,bool)
0x18000cf2f  mov     edx, eax
0x18000cf31  test    eax, eax
0x18000cf33  js      short loc_18000CF07
0x18000cf35  xor     edx, edx
0x18000cf37  jmp     short loc_18000CF0E
```
