# ASNDllMain(HINSTANCE__ *,ulong,void *)

- ea: `0x18000dc90`
- end: `0x18000dd43`
- name: `?ASNDllMain@@YAHPEAUHINSTANCE__@@KPEAX@Z`
- size: `179`
- prototype: `__int64 __fastcall(HINSTANCE, unsigned int, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x18000dab0`

## callees

- `0x18000dc90`

## import_xrefs

- `MSASN1!ASN1_CreateModule` at `0x18000dcea`
- `MSASN1!ASN1_CreateModule` at `0x18000dcea`
- `MSASN1!ASN1_CloseModule` at `0x18000dd2c`
- `MSASN1!ASN1_CloseModule` at `0x18000dd2c`
- `CRYPT32!I_CryptUninstallAsn1Module` at `0x18000dd1f`
- `CRYPT32!I_CryptUninstallAsn1Module` at `0x18000dd1f`
- `CRYPT32!I_CryptInstallAsn1Module` at `0x18000dcff`
- `CRYPT32!I_CryptInstallAsn1Module` at `0x18000dcff`

## pseudocode

```c
_BOOL8 __fastcall ASNDllMain(HINSTANCE a1, int a2, void *a3)
{
  if ( !a2 )
  {
    I_CryptUninstallAsn1Module(hAsn1Module);
    ASN1_CloseModule(WTASN_Module);
    WTASN_Module = 0;
    return 1;
  }
  if ( a2 != 1 )
    return 1;
  WTASN_Module = ASN1_CreateModule(
                   0x10000,
                   1024,
                   4096,
                   18,
                   off_180052250,
                   off_1800521C0,
                   &off_180052130,
                   qword_180055B90,
                   29815);
  hAsn1Module = I_CryptInstallAsn1Module((ASN1module_t)WTASN_Module, 0, 0);
  return hAsn1Module != 0;
}

```

## disassembly

```asm
0x18000dc90  mov     r11, rsp
0x18000dc93  sub     rsp, 58h
0x18000dc97  test    edx, edx
0x18000dc99  jz      short loc_18000DD19
0x18000dc9b  cmp     edx, 1
0x18000dc9e  jnz     short loc_18000DD0F
0x18000dca0  mov     [rsp+58h+var_18], 7477h
0x18000dca8  lea     rax, qword_180055B90
0x18000dcaf  mov     [r11-20h], rax
0x18000dcb3  mov     edx, 400h
0x18000dcb8  lea     rax, off_180052130
0x18000dcbf  mov     ecx, 10000h
0x18000dcc4  mov     [r11-28h], rax
0x18000dcc8  mov     r9d, 12h
0x18000dcce  lea     rax, off_1800521C0
0x18000dcd5  mov     r8d, 1000h
0x18000dcdb  mov     [r11-30h], rax
0x18000dcdf  lea     rax, off_180052250
0x18000dce6  mov     [r11-38h], rax
0x18000dcea  call    cs:__imp_ASN1_CreateModule
0x18000dcf0  xor     r8d, r8d; pvReserved
0x18000dcf3  xor     edx, edx; dwFlags
0x18000dcf5  mov     rcx, rax; pMod
0x18000dcf8  mov     cs:WTASN_Module, rax
0x18000dcff  call    cs:__imp_I_CryptInstallAsn1Module
0x18000dd05  mov     cs:hAsn1Module, eax
0x18000dd0b  test    eax, eax
0x18000dd0d  jz      short loc_18000DD3F
0x18000dd0f  mov     eax, 1
0x18000dd14  add     rsp, 58h
0x18000dd18  retn
0x18000dd19  mov     ecx, cs:hAsn1Module; hAsn1Module
0x18000dd1f  call    cs:__imp_I_CryptUninstallAsn1Module
0x18000dd25  mov     rcx, cs:WTASN_Module
0x18000dd2c  call    cs:__imp_ASN1_CloseModule
0x18000dd32  mov     cs:WTASN_Module, 0
0x18000dd3d  jmp     short loc_18000DD0F
0x18000dd3f  xor     eax, eax
0x18000dd41  jmp     short loc_18000DD14
```
