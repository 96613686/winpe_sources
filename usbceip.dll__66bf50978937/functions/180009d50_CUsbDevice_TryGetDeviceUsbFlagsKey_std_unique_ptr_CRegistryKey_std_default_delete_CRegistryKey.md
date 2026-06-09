# CUsbDevice::TryGetDeviceUsbFlagsKey(std::unique_ptr<CRegistryKey,std::default_delete<CRegistryKey>> &)

- ea: `0x180009d50`
- end: `0x180009e4a`
- name: `?TryGetDeviceUsbFlagsKey@CUsbDevice@@AEAAEAEAV?$unique_ptr@VCRegistryKey@@U?$default_delete@VCRegistryKey@@@std@@@std@@@Z`
- size: `250`
- prototype: `char __fastcall(unsigned __int16 *, HKEY **)`
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
- `0x180009d50`
- `0x18000bc7c`
- `0x18000c088`

## pseudocode

```c
char __fastcall CUsbDevice::TryGetDeviceUsbFlagsKey(unsigned __int16 *a1, HKEY **a2)
{
  int v4; // ebp
  int v5; // r14d
  unsigned int v6; // r15d
  char v7; // di
  size_t v8; // rdx
  const unsigned __int16 **v9; // rbx
  unsigned __int16 *v10; // rcx
  const unsigned __int16 *v11; // rdx
  HKEY *v12; // rax
  const unsigned __int16 *v13; // r8
  CRegistryKey *v14; // rax
  __int64 v15; // rcx
  HKEY *v16; // rdx
  OLECHAR **v18; // [rsp+60h] [rbp+8h] BYREF
  HKEY *v19; // [rsp+70h] [rbp+18h]

  v18 = 0;
  _bstr_t::operator=((_bstr_t *)&v18, L"SYSTEM\\CurrentControlSet\\Control\\usbflags\\VVVVPPPPRRRR");
  v4 = a1[26];
  v5 = a1[25];
  v6 = a1[24];
  v7 = 1;
  v8 = _bstr_t::length(&v18) + 1;
  v9 = (const unsigned __int16 **)v18;
  if ( v18 )
    v10 = *v18;
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
    v19 = v12;
    if ( v9 )
      v13 = *v9;
    else
      v13 = 0;
    v14 = CRegistryKey::CRegistryKey(v12, HKEY_LOCAL_MACHINE, v13);
    v16 = *a2;
    *a2 = (HKEY *)v14;
    if ( v16 )
      std::default_delete<CRegistryKey>::operator()(v15, v16);
  }
  else
  {
    v7 = 0;
  }
  _bstr_t::_Free((_bstr_t *)&v18);
  return v7;
}

```

## disassembly

```asm
0x180009d50  mov     [rsp+arg_8], rbx
0x180009d55  push    rbp
0x180009d56  push    rsi
0x180009d57  push    rdi
0x180009d58  push    r14
0x180009d5a  push    r15
0x180009d5c  sub     rsp, 30h
0x180009d60  mov     rsi, rdx
0x180009d63  mov     rbx, rcx
0x180009d66  mov     [rsp+58h+arg_0], 0
0x180009d6f  lea     rdx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Control\\usb"...
0x180009d76  lea     rcx, [rsp+58h+arg_0]
0x180009d7b  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x180009d80  movzx   ebp, word ptr [rbx+34h]
0x180009d84  movzx   r14d, word ptr [rbx+32h]
0x180009d89  movzx   r15d, word ptr [rbx+30h]
0x180009d8e  lea     rcx, [rsp+58h+arg_0]; this
0x180009d93  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x180009d98  mov     edi, 1
0x180009d9d  lea     edx, [rdi+rax]; unsigned __int64
0x180009da0  mov     rbx, [rsp+58h+arg_0]
0x180009da5  test    rbx, rbx
0x180009da8  jz      short loc_180009DAF
0x180009daa  mov     rcx, [rbx]
0x180009dad  jmp     short loc_180009DB1
0x180009daf  xor     ecx, ecx; unsigned __int16 *
0x180009db1  mov     [rsp+58h+var_30], ebp
0x180009db5  mov     [rsp+58h+var_38], r14d
0x180009dba  mov     r9d, r15d
0x180009dbd  lea     r8, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Control\\usb"...
0x180009dc4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009dc9  test    rbx, rbx
0x180009dcc  jz      short loc_180009DD3
0x180009dce  mov     rdx, [rbx]
0x180009dd1  jmp     short loc_180009DD5
0x180009dd3  xor     edx, edx; unsigned __int16 *
0x180009dd5  mov     rbp, 0FFFFFFFF80000002h
0x180009ddc  mov     rcx, rbp; HKEY
0x180009ddf  call    ?KeyExists@CRegistryKey@@SAEPEAUHKEY__@@PEBG@Z; CRegistryKey::KeyExists(HKEY__ *,ushort const *)
0x180009de4  test    al, al
0x180009de6  jnz     short loc_180009DED
0x180009de8  xor     dil, dil
0x180009deb  jmp     short loc_180009E2C
0x180009ded  mov     ecx, 20h ; ' '; Size
0x180009df2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009df7  mov     [rsp+58h+arg_10], rax
0x180009dfc  test    rbx, rbx
0x180009dff  jz      short loc_180009E06
0x180009e01  mov     r8, [rbx]
0x180009e04  jmp     short loc_180009E09
0x180009e06  xor     r8d, r8d; unsigned __int16 *
0x180009e09  mov     r9d, 20019h; unsigned int
0x180009e0f  mov     rdx, rbp; HKEY
0x180009e12  mov     rcx, rax; phkResult
0x180009e15  call    ??0CRegistryKey@@QEAA@PEAUHKEY__@@PEBGK@Z; CRegistryKey::CRegistryKey(HKEY__ *,ushort const *,ulong)
0x180009e1a  nop
0x180009e1b  mov     rdx, [rsi]
0x180009e1e  mov     [rsi], rax
0x180009e21  test    rdx, rdx
0x180009e24  jz      short loc_180009E2C
0x180009e26  call    ??R?$default_delete@VCRegistryKey@@@std@@QEBAXPEAVCRegistryKey@@@Z; std::default_delete<CRegistryKey>::operator()(CRegistryKey *)
0x180009e2b  nop
0x180009e2c  lea     rcx, [rsp+58h+arg_0]; this
0x180009e31  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180009e36  mov     al, dil
0x180009e39  mov     rbx, [rsp+58h+arg_8]
0x180009e3e  add     rsp, 30h
0x180009e42  pop     r15
0x180009e44  pop     r14
0x180009e46  pop     rdi
0x180009e47  pop     rsi
0x180009e48  pop     rbp
0x180009e49  retn
```
