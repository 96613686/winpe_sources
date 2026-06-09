# CUsbDevice::TryGetDeviceUsbCeipKey(std::unique_ptr<CRegistryKey,std::default_delete<CRegistryKey>> &)

- ea: `0x180009c50`
- end: `0x180009d4a`
- name: `?TryGetDeviceUsbCeipKey@CUsbDevice@@AEAAEAEAV?$unique_ptr@VCRegistryKey@@U?$default_delete@VCRegistryKey@@@std@@@std@@@Z`
- size: `250`
- prototype: `char __fastcall(unsigned __int16 *, CRegistryKey **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800045d0`

## callees

- `0x18000246c`
- `0x180003a80`
- `0x180003fec`
- `0x180007264`
- `0x180007294`
- `0x180007afc`
- `0x180009c50`
- `0x18000bc7c`
- `0x18000c088`

## pseudocode

```c
char __fastcall CUsbDevice::TryGetDeviceUsbCeipKey(unsigned __int16 *a1, CRegistryKey **a2)
{
  int v4; // ebp
  int v5; // r14d
  unsigned int v6; // r15d
  char v7; // di
  unsigned __int64 v8; // rdx
  const unsigned __int16 **v9; // rbx
  unsigned __int16 *v10; // rcx
  const unsigned __int16 *v11; // rdx
  HKEY *v12; // rax
  const unsigned __int16 *v13; // r8
  CRegistryKey *v14; // rax
  CRegistryKey *v15; // rdx
  unsigned __int16 **v17; // [rsp+60h] [rbp+8h] BYREF
  HKEY *v18; // [rsp+70h] [rbp+18h]

  v17 = 0;
  _bstr_t::operator=(&v17, L"SYSTEM\\CurrentControlSet\\Control\\usbflags\\VVVVPPPPRRRR");
  v4 = a1[26];
  v5 = a1[25];
  v6 = a1[24];
  v7 = 1;
  v8 = _bstr_t::length((_bstr_t *)&v17) + 1;
  v9 = (const unsigned __int16 **)v17;
  if ( v17 )
    v10 = *v17;
  else
    v10 = 0;
  StringCchPrintfW(v10, v8, L"SYSTEM\\CurrentControlSet\\Control\\usbflags\\%0.4x%0.4x%0.4x", v6, v5, v4);
  if ( v9 )
    v11 = *v9;
  else
    v11 = 0;
  if ( CRegistryKey::KeyExists(HKEY_LOCAL_MACHINE, v11) )
  {
    v12 = (HKEY *)operator new(0x20u);
    v18 = v12;
    if ( v9 )
      v13 = *v9;
    else
      v13 = 0;
    v14 = CRegistryKey::CRegistryKey(v12, HKEY_LOCAL_MACHINE, v13);
    v15 = *a2;
    *a2 = v14;
    if ( v15 )
      std::default_delete<CRegistryKey>::operator()();
  }
  else
  {
    v7 = 0;
  }
  _bstr_t::_Free((_bstr_t *)&v17);
  return v7;
}

```

## disassembly

```asm
0x180009c50  mov     [rsp+arg_8], rbx
0x180009c55  push    rbp
0x180009c56  push    rsi
0x180009c57  push    rdi
0x180009c58  push    r14
0x180009c5a  push    r15
0x180009c5c  sub     rsp, 30h
0x180009c60  mov     rsi, rdx
0x180009c63  mov     rbx, rcx
0x180009c66  mov     [rsp+58h+arg_0], 0
0x180009c6f  lea     rdx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Control\\usb"...
0x180009c76  lea     rcx, [rsp+58h+arg_0]
0x180009c7b  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x180009c80  movzx   ebp, word ptr [rbx+34h]
0x180009c84  movzx   r14d, word ptr [rbx+32h]
0x180009c89  movzx   r15d, word ptr [rbx+30h]
0x180009c8e  lea     rcx, [rsp+58h+arg_0]; this
0x180009c93  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x180009c98  mov     edi, 1
0x180009c9d  lea     edx, [rdi+rax]; unsigned __int64
0x180009ca0  mov     rbx, [rsp+58h+arg_0]
0x180009ca5  test    rbx, rbx
0x180009ca8  jz      short loc_180009CAF
0x180009caa  mov     rcx, [rbx]
0x180009cad  jmp     short loc_180009CB1
0x180009caf  xor     ecx, ecx; unsigned __int16 *
0x180009cb1  mov     [rsp+58h+var_30], ebp
0x180009cb5  mov     [rsp+58h+var_38], r14d
0x180009cba  mov     r9d, r15d
0x180009cbd  lea     r8, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Control\\usb"...
0x180009cc4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009cc9  test    rbx, rbx
0x180009ccc  jz      short loc_180009CD3
0x180009cce  mov     rdx, [rbx]
0x180009cd1  jmp     short loc_180009CD5
0x180009cd3  xor     edx, edx; unsigned __int16 *
0x180009cd5  mov     rbp, 0FFFFFFFF80000002h
0x180009cdc  mov     rcx, rbp; HKEY
0x180009cdf  call    ?KeyExists@CRegistryKey@@SAEPEAUHKEY__@@PEBG@Z; CRegistryKey::KeyExists(HKEY__ *,ushort const *)
0x180009ce4  test    al, al
0x180009ce6  jnz     short loc_180009CED
0x180009ce8  xor     dil, dil
0x180009ceb  jmp     short loc_180009D2C
0x180009ced  mov     ecx, 20h ; ' '; Size
0x180009cf2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009cf7  mov     [rsp+58h+arg_10], rax
0x180009cfc  test    rbx, rbx
0x180009cff  jz      short loc_180009D06
0x180009d01  mov     r8, [rbx]
0x180009d04  jmp     short loc_180009D09
0x180009d06  xor     r8d, r8d; unsigned __int16 *
0x180009d09  mov     r9d, 3; unsigned int
0x180009d0f  mov     rdx, rbp; HKEY
0x180009d12  mov     rcx, rax; phkResult
0x180009d15  call    ??0CRegistryKey@@QEAA@PEAUHKEY__@@PEBGK@Z; CRegistryKey::CRegistryKey(HKEY__ *,ushort const *,ulong)
0x180009d1a  nop
0x180009d1b  mov     rdx, [rsi]
0x180009d1e  mov     [rsi], rax
0x180009d21  test    rdx, rdx
0x180009d24  jz      short loc_180009D2C
0x180009d26  call    ??R?$default_delete@VCRegistryKey@@@std@@QEBAXPEAVCRegistryKey@@@Z; std::default_delete<CRegistryKey>::operator()(CRegistryKey *)
0x180009d2b  nop
0x180009d2c  lea     rcx, [rsp+58h+arg_0]; this
0x180009d31  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180009d36  mov     al, dil
0x180009d39  mov     rbx, [rsp+58h+arg_8]
0x180009d3e  add     rsp, 30h
0x180009d42  pop     r15
0x180009d44  pop     r14
0x180009d46  pop     rdi
0x180009d47  pop     rsi
0x180009d48  pop     rbp
0x180009d49  retn
```
