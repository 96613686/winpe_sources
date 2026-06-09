# CUsbDevice::TryGetPersistedDeviceUsbFlagsKey(std::unique_ptr<CRegistryKey,std::default_delete<CRegistryKey>> &)

- ea: `0x180009e50`
- end: `0x180009fa9`
- name: `?TryGetPersistedDeviceUsbFlagsKey@CUsbDevice@@AEAAEAEAV?$unique_ptr@VCRegistryKey@@U?$default_delete@VCRegistryKey@@@std@@@std@@@Z`
- size: `345`
- prototype: `char __fastcall(unsigned __int16 *, CRegistryKey **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x1800045d0`

## callees

- `0x180002434`
- `0x18000246c`
- `0x180002fbc`
- `0x180003a80`
- `0x180007264`
- `0x180009e50`
- `0x18000bc7c`
- `0x18000c088`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x180009e93`
- `ntdll!RtlGetPersistedStateLocation` at `0x180009eea`
- `ntdll!RtlGetPersistedStateLocation` at `0x180009e93`
- `ntdll!RtlGetPersistedStateLocation` at `0x180009eea`

## pseudocode

```c
char __fastcall CUsbDevice::TryGetPersistedDeviceUsbFlagsKey(unsigned __int16 *a1, CRegistryKey **a2)
{
  void *v4; // rbx
  CRegistryKey *v6; // rax
  CRegistryKey *v7; // rdx
  char v8; // di
  __int64 v9; // [rsp+20h] [rbp-28h]
  __int64 v10; // [rsp+28h] [rbp-20h]
  unsigned int v11; // [rsp+60h] [rbp+18h] BYREF
  PHKEY v12; // [rsp+68h] [rbp+20h]

  v11 = 0;
  v4 = 0;
  if ( (unsigned int)RtlGetPersistedStateLocation(
                       L"UsbFlags",
                       0,
                       L"System\\CurrentControlSet\\Control\\usbflags",
                       0,
                       0,
                       0,
                       &v11) == -2147483643
    && (v4 = operator new[](saturated_mul(v11 + 14LL, 2u)),
        (int)RtlGetPersistedStateLocation(
               L"UsbFlags",
               0,
               L"System\\CurrentControlSet\\Control\\usbflags",
               0,
               v4,
               v11,
               0) < 0) )
  {
    operator delete(v4);
    return 0;
  }
  else
  {
    LODWORD(v10) = a1[26];
    LODWORD(v9) = a1[25];
    if ( (int)StringCchPrintfW(
                (unsigned __int16 *)v4 + ((unsigned __int64)v11 >> 1) - 1,
                0x1Cu,
                L"\\%04X%04X%04X",
                a1[24],
                v9,
                v10) >= 0
      && CRegistryKey::KeyExists(HKEY_LOCAL_MACHINE, (const unsigned __int16 *)v4) )
    {
      v12 = (PHKEY)operator new(0x20u);
      v6 = CRegistryKey::CRegistryKey(v12, HKEY_LOCAL_MACHINE, (const unsigned __int16 *)v4, 0x20019u);
      v7 = *a2;
      *a2 = v6;
      if ( v7 )
        std::default_delete<CRegistryKey>::operator()();
      v8 = 1;
    }
    else
    {
      v8 = 0;
    }
    operator delete(v4);
    return v8;
  }
}

```

## disassembly

```asm
0x180009e50  mov     r11, rsp
0x180009e53  mov     [r11+8], rbx
0x180009e57  mov     [r11+10h], rsi
0x180009e5b  push    rdi
0x180009e5c  sub     rsp, 40h
0x180009e60  mov     rsi, rdx
0x180009e63  mov     rdi, rcx
0x180009e66  mov     [rsp+48h+arg_10], 0
0x180009e6e  xor     ebx, ebx
0x180009e70  lea     rax, [r11+18h]
0x180009e74  mov     [r11-18h], rax
0x180009e78  mov     dword ptr [rsp+48h+var_20], ebx
0x180009e7c  mov     [r11-28h], rbx
0x180009e80  xor     r9d, r9d
0x180009e83  lea     r8, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\usb"...
0x180009e8a  xor     edx, edx
0x180009e8c  lea     rcx, aUsbflags; "UsbFlags"
0x180009e93  call    cs:__imp_RtlGetPersistedStateLocation
0x180009e99  cmp     eax, 80000005h
0x180009e9e  jnz     short loc_180009F03
0x180009ea0  mov     ecx, [rsp+48h+arg_10]
0x180009ea4  add     rcx, 0Eh
0x180009ea8  lea     eax, [rbx+2]
0x180009eab  mul     rcx
0x180009eae  lea     rdx, [rbx-1]
0x180009eb2  cmovb   rax, rdx
0x180009eb6  mov     rcx, rax; unsigned __int64
0x180009eb9  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180009ebe  mov     rbx, rax
0x180009ec1  mov     [rsp+48h+var_18], 0
0x180009eca  mov     eax, [rsp+48h+arg_10]
0x180009ece  mov     dword ptr [rsp+48h+var_20], eax
0x180009ed2  mov     [rsp+48h+var_28], rbx
0x180009ed7  xor     r9d, r9d
0x180009eda  lea     r8, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\usb"...
0x180009ee1  xor     edx, edx
0x180009ee3  lea     rcx, aUsbflags; "UsbFlags"
0x180009eea  call    cs:__imp_RtlGetPersistedStateLocation
0x180009ef0  test    eax, eax
0x180009ef2  jns     short loc_180009F03
0x180009ef4  mov     rcx, rbx; Block
0x180009ef7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009efc  xor     al, al
0x180009efe  jmp     loc_180009F99
0x180009f03  movzx   edx, word ptr [rdi+34h]
0x180009f07  movzx   r8d, word ptr [rdi+32h]
0x180009f0c  movzx   r9d, word ptr [rdi+30h]
0x180009f11  mov     eax, [rsp+48h+arg_10]
0x180009f15  shr     rax, 1
0x180009f18  dec     rax
0x180009f1b  lea     rcx, [rbx+rax*2]; unsigned __int16 *
0x180009f1f  mov     dword ptr [rsp+48h+var_20], edx
0x180009f23  mov     dword ptr [rsp+48h+var_28], r8d
0x180009f28  lea     r8, a04x04x04x; "\\%04X%04X%04X"
0x180009f2f  mov     edx, 1Ch; unsigned __int64
0x180009f34  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009f39  test    eax, eax
0x180009f3b  js      short loc_180009F8C
0x180009f3d  mov     rdx, rbx; unsigned __int16 *
0x180009f40  mov     rdi, 0FFFFFFFF80000002h
0x180009f47  mov     rcx, rdi; HKEY
0x180009f4a  call    ?KeyExists@CRegistryKey@@SAEPEAUHKEY__@@PEBG@Z; CRegistryKey::KeyExists(HKEY__ *,ushort const *)
0x180009f4f  test    al, al
0x180009f51  jz      short loc_180009F8C
0x180009f53  mov     ecx, 20h ; ' '; Size
0x180009f58  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009f5d  mov     [rsp+48h+arg_18], rax
0x180009f62  mov     r9d, 20019h; unsigned int
0x180009f68  mov     r8, rbx; unsigned __int16 *
0x180009f6b  mov     rdx, rdi; HKEY
0x180009f6e  mov     rcx, rax; phkResult
0x180009f71  call    ??0CRegistryKey@@QEAA@PEAUHKEY__@@PEBGK@Z; CRegistryKey::CRegistryKey(HKEY__ *,ushort const *,ulong)
0x180009f76  nop
0x180009f77  mov     rdx, [rsi]
0x180009f7a  mov     [rsi], rax
0x180009f7d  test    rdx, rdx
0x180009f80  jz      short loc_180009F87
0x180009f82  call    ??R?$default_delete@VCRegistryKey@@@std@@QEBAXPEAVCRegistryKey@@@Z; std::default_delete<CRegistryKey>::operator()(CRegistryKey *)
0x180009f87  mov     dil, 1
0x180009f8a  jmp     short loc_180009F8E
0x180009f8c  xor     edi, edi
0x180009f8e  mov     rcx, rbx; Block
0x180009f91  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009f96  mov     al, dil
0x180009f99  mov     rbx, [rsp+48h+arg_0]
0x180009f9e  mov     rsi, [rsp+48h+arg_8]
0x180009fa3  add     rsp, 40h
0x180009fa7  pop     rdi
0x180009fa8  retn
```
