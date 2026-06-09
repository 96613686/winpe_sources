# RegistryFunctions::RegDeleteKeyValueW(HKEY__ *,ushort const *,ushort const *)

- ea: `0x18000ff80`
- end: `0x18000fffc`
- name: `?RegDeleteKeyValueW@RegistryFunctions@@UEAAJPEAUHKEY__@@PEBG1@Z`
- size: `124`
- prototype: `__int64 __fastcall(RegistryFunctions *this, HKEY, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000ff80`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000ffce`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000ffce`

## pseudocode

```c
__int64 __fastcall RegistryFunctions::RegDeleteKeyValueW(
        RegistryFunctions *this,
        HKEY a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  __int64 v4; // rax
  unsigned int v7; // ebx
  HKEY hKey; // [rsp+50h] [rbp+8h] BYREF

  v4 = *(_QWORD *)this;
  hKey = 0;
  v7 = (*(__int64 (__fastcall **)(RegistryFunctions *, HKEY, const unsigned __int16 *, _QWORD, int, HKEY *))(v4 + 80))(
         this,
         a2,
         a3,
         0,
         2,
         &hKey);
  if ( !v7 )
  {
    v7 = RegDeleteValueW(hKey, a4);
    (*(void (__fastcall **)(RegistryFunctions *, HKEY))(*(_QWORD *)this + 8LL))(this, hKey);
  }
  return v7;
}

```

## disassembly

```asm
0x18000ff80  mov     r11, rsp
0x18000ff83  mov     [r11+10h], rbx
0x18000ff87  mov     [r11+18h], rsi
0x18000ff8b  push    rdi
0x18000ff8c  sub     rsp, 40h
0x18000ff90  mov     rax, [rcx]
0x18000ff93  mov     rdi, rcx
0x18000ff96  lea     rcx, [r11+8]
0x18000ff9a  mov     qword ptr [r11+8], 0
0x18000ffa2  mov     [r11-20h], rcx
0x18000ffa6  mov     rsi, r9
0x18000ffa9  xor     r9d, r9d
0x18000ffac  mov     [rsp+48h+var_28], 2
0x18000ffb4  mov     rax, [rax+50h]
0x18000ffb8  mov     rcx, rdi
0x18000ffbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffc0  mov     ebx, eax
0x18000ffc2  test    eax, eax
0x18000ffc4  jnz     short loc_18000FFEA
0x18000ffc6  mov     rcx, [rsp+48h+hKey]; hKey
0x18000ffcb  mov     rdx, rsi; lpValueName
0x18000ffce  call    cs:__imp_RegDeleteValueW
0x18000ffd4  mov     rdx, [rsp+48h+hKey]
0x18000ffd9  mov     rcx, rdi
0x18000ffdc  mov     ebx, eax
0x18000ffde  mov     rax, [rdi]
0x18000ffe1  mov     rax, [rax+8]
0x18000ffe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffea  mov     rsi, [rsp+48h+arg_10]
0x18000ffef  mov     eax, ebx
0x18000fff1  mov     rbx, [rsp+48h+arg_8]
0x18000fff6  add     rsp, 40h
0x18000fffa  pop     rdi
0x18000fffb  retn
```
