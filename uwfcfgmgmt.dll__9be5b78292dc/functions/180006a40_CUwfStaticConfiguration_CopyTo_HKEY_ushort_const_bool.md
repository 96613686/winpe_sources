# CUwfStaticConfiguration::CopyTo(HKEY__ *,ushort const *,bool)

- ea: `0x180006a40`
- end: `0x180006ad6`
- name: `?CopyTo@CUwfStaticConfiguration@@QEAAJPEAUHKEY__@@PEBG_N@Z`
- size: `150`
- prototype: `__int64 __fastcall(CUwfConfiguration **this, HKEY, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180008730`

## callees

- `0x180006a40`
- `0x180006ae0`
- `0x180006b20`
- `0x18000d5f0`

## pseudocode

```c
__int64 __fastcall CUwfStaticConfiguration::CopyTo(
        CUwfConfiguration **this,
        HKEY a2,
        const unsigned __int16 *a3,
        bool a4)
{
  int v6; // ebx
  HKEY v8[3]; // [rsp+40h] [rbp-18h] BYREF
  unsigned int v9; // [rsp+60h] [rbp+8h] BYREF

  v9 = 0;
  v8[0] = 0;
  v6 = CUwfConfiguration::CreateKey(this[4], a2, a3, 0xF003Fu, 0, &v9, (struct CUwfRegKey *)v8);
  if ( v6 < 0 || (v6 = CUwfConfiguration::CopyTree(this[4], (struct CUwfRegKey *)(this + 2), 0, v8[0], a4), v6 < 0) )
    *((_DWORD *)this[4] + 4) = v6;
  CUwfRegKey::Close(v8);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180006a40  mov     r11, rsp
0x180006a43  mov     [r11+10h], rbx
0x180006a47  mov     [r11+18h], rsi
0x180006a4b  push    rdi
0x180006a4c  sub     rsp, 50h
0x180006a50  lea     rax, [r11-18h]
0x180006a54  mov     [rsp+58h+arg_0], 0
0x180006a5c  mov     [r11-28h], rax
0x180006a60  mov     sil, r9b
0x180006a63  lea     rax, [r11+8]
0x180006a67  mov     qword ptr [r11-18h], 0
0x180006a6f  mov     rdi, rcx
0x180006a72  mov     [r11-30h], rax
0x180006a76  mov     rcx, [rcx+20h]; this
0x180006a7a  mov     r9d, 0F003Fh; unsigned int
0x180006a80  mov     dword ptr [rsp+58h+var_38], 0; unsigned int
0x180006a88  call    ?CreateKey@CUwfConfiguration@@QEAAJPEAUHKEY__@@PEBGKKPEAKAEAVCUwfRegKey@@@Z; CUwfConfiguration::CreateKey(HKEY__ *,ushort const *,ulong,ulong,ulong *,CUwfRegKey &)
0x180006a8d  mov     ebx, eax
0x180006a8f  test    eax, eax
0x180006a91  js      short loc_180006AB3
0x180006a93  mov     r9, [rsp+58h+var_18]; HKEY
0x180006a98  lea     rdx, [rdi+10h]; struct CUwfRegKey *
0x180006a9c  mov     rcx, [rdi+20h]; this
0x180006aa0  xor     r8d, r8d; unsigned __int16 *
0x180006aa3  mov     [rsp+58h+var_38], sil; bool
0x180006aa8  call    ?CopyTree@CUwfConfiguration@@QEAAJAEAVCUwfRegKey@@PEBGPEAUHKEY__@@_N@Z; CUwfConfiguration::CopyTree(CUwfRegKey &,ushort const *,HKEY__ *,bool)
0x180006aad  mov     ebx, eax
0x180006aaf  test    eax, eax
0x180006ab1  jns     short loc_180006ABA
0x180006ab3  mov     rax, [rdi+20h]
0x180006ab7  mov     [rax+10h], ebx
0x180006aba  lea     rcx, [rsp+58h+var_18]; this
0x180006abf  call    ?Close@CUwfRegKey@@QEAAJXZ; CUwfRegKey::Close(void)
0x180006ac4  mov     rsi, [rsp+58h+arg_10]
0x180006ac9  mov     eax, ebx
0x180006acb  mov     rbx, [rsp+58h+arg_8]
0x180006ad0  add     rsp, 50h
0x180006ad4  pop     rdi
0x180006ad5  retn
```
