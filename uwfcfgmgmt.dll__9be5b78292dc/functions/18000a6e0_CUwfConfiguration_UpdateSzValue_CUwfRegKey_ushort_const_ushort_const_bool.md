# CUwfConfiguration::UpdateSzValue(CUwfRegKey &,ushort const *,ushort const *,bool)

- ea: `0x18000a6e0`
- end: `0x18000a81c`
- name: `?UpdateSzValue@CUwfConfiguration@@QEAAJAEAVCUwfRegKey@@PEBG1_N@Z`
- size: `316`
- prototype: `__int64 __fastcall(CUwfConfiguration *this, HKEY *, const unsigned __int16 *, const unsigned __int16 *, bool)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18000bfa0`
- `0x18000c540`
- `0x18000d130`

## callees

- `0x180001384`
- `0x1800079a0`
- `0x18000a6e0`
- `0x18000e580`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000a80d`
- `msvcrt!_wcsicmp` at `0x18000a80d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000a7ac`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000a7ed`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000a7ac`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000a7ed`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a726`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a78c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a726`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a78c`

## pseudocode

```c
__int64 __fastcall CUwfConfiguration::UpdateSzValue(
        CUwfConfiguration *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        bool a5)
{
  wchar_t *v5; // rsi
  LSTATUS ValueW; // eax
  int v11; // ebx
  void *pvData; // rdi
  DWORD pcbData; // [rsp+40h] [rbp-48h] BYREF
  DWORD pdwType[17]; // [rsp+44h] [rbp-44h] BYREF

  v5 = 0;
  pdwType[0] = 0;
  pcbData = 0;
  ValueW = RegGetValueW(*a2, 0, a3, 2u, pdwType, 0, &pcbData);
  v11 = ValueW;
  if ( ValueW )
  {
    pvData = 0;
    goto LABEL_6;
  }
  pvData = operator new[](saturated_mul((unsigned __int64)pcbData >> 1, 2u));
  if ( pvData )
  {
    ValueW = RegGetValueW(*a2, 0, a3, 2u, pdwType, pvData, &pcbData);
    v11 = ValueW;
    if ( !ValueW )
    {
      v5 = (wchar_t *)pvData;
LABEL_16:
      if ( !_wcsicmp(v5, a4) )
      {
        v11 = 1;
        goto LABEL_14;
      }
      goto LABEL_11;
    }
LABEL_6:
    if ( ValueW > 0 )
      v11 = (unsigned __int16)ValueW | 0x80070000;
    if ( v11 >= 0 )
      goto LABEL_10;
    goto LABEL_9;
  }
  v11 = -2147024882;
LABEL_9:
  operator delete[](pvData);
  if ( v11 != -2147024894 )
    goto LABEL_14;
LABEL_10:
  if ( v11 != -2147024894 )
    goto LABEL_16;
LABEL_11:
  if ( !a5 || (v11 = CUwfConfiguration::FixupUpdatedSettings(this), v11 >= 0) )
    v11 = CUwfRegKey::SetSzValue(a2, a3, (const BYTE *)a4);
LABEL_14:
  operator delete[](v5);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000a6e0  mov     r11, rsp
0x18000a6e3  push    rbx
0x18000a6e4  push    rbp
0x18000a6e5  push    rsi
0x18000a6e6  push    rdi
0x18000a6e7  push    r12
0x18000a6e9  push    r14
0x18000a6eb  push    r15
0x18000a6ed  sub     rsp, 50h
0x18000a6f1  xor     esi, esi
0x18000a6f3  lea     rax, [r11-48h]
0x18000a6f7  mov     [r11-58h], rax
0x18000a6fb  mov     r15, rdx
0x18000a6fe  mov     rbp, r9
0x18000a701  mov     [r11-60h], rsi
0x18000a705  mov     r12, rcx
0x18000a708  mov     [rsp+88h+var_44], esi
0x18000a70c  lea     rax, [r11-44h]
0x18000a710  mov     [rsp+88h+var_48], esi
0x18000a714  mov     rcx, [r15]; hkey
0x18000a717  lea     edi, [rsi+2]
0x18000a71a  mov     r9d, edi; dwFlags
0x18000a71d  mov     [r11-68h], rax
0x18000a721  xor     edx, edx; lpSubKey
0x18000a723  mov     r14, r8
0x18000a726  call    cs:__imp_RegGetValueW
0x18000a72c  mov     ebx, eax
0x18000a72e  test    eax, eax
0x18000a730  jz      short loc_18000A736
0x18000a732  xor     edi, edi
0x18000a734  jmp     short loc_18000A798
0x18000a736  mov     ecx, [rsp+88h+var_48]
0x18000a73a  mov     rax, rdi
0x18000a73d  shr     rcx, 1
0x18000a740  mul     rcx
0x18000a743  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000a74a  cmovb   rax, rcx
0x18000a74e  mov     rcx, rax; unsigned __int64
0x18000a751  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000a756  mov     rdi, rax
0x18000a759  test    rax, rax
0x18000a75c  jnz     short loc_18000A765
0x18000a75e  mov     ebx, 8007000Eh
0x18000a763  jmp     short loc_18000A7A9
0x18000a765  mov     rcx, [r15]; hkey
0x18000a768  lea     rax, [rsp+88h+var_48]
0x18000a76d  mov     [rsp+88h+pcbData], rax; pcbData
0x18000a772  mov     r9d, 2; dwFlags
0x18000a778  lea     rax, [rsp+88h+var_44]
0x18000a77d  mov     [rsp+88h+pvData], rdi; pvData
0x18000a782  mov     r8, r14; lpValue
0x18000a785  mov     [rsp+88h+pdwType], rax; pdwType
0x18000a78a  xor     edx, edx; lpSubKey
0x18000a78c  call    cs:__imp_RegGetValueW
0x18000a792  mov     ebx, eax
0x18000a794  test    eax, eax
0x18000a796  jz      short loc_18000A804
0x18000a798  test    eax, eax
0x18000a79a  jle     short loc_18000A7A5
0x18000a79c  movzx   ebx, ax
0x18000a79f  or      ebx, 80070000h
0x18000a7a5  test    ebx, ebx
0x18000a7a7  jns     short loc_18000A7BA
0x18000a7a9  mov     rcx, rdi
0x18000a7ac  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000a7b2  cmp     ebx, 80070002h
0x18000a7b8  jnz     short loc_18000A7EA
0x18000a7ba  cmp     ebx, 80070002h
0x18000a7c0  jnz     short loc_18000A807
0x18000a7c2  cmp     [rsp+88h+arg_20], 0
0x18000a7ca  jz      short loc_18000A7DA
0x18000a7cc  mov     rcx, r12; this
0x18000a7cf  call    ?FixupUpdatedSettings@CUwfConfiguration@@QEAAJXZ; CUwfConfiguration::FixupUpdatedSettings(void)
0x18000a7d4  mov     ebx, eax
0x18000a7d6  test    eax, eax
0x18000a7d8  js      short loc_18000A7EA
0x18000a7da  mov     r8, rbp; unsigned __int16 *
0x18000a7dd  mov     rdx, r14; unsigned __int16 *
0x18000a7e0  mov     rcx, r15; this
0x18000a7e3  call    ?SetSzValue@CUwfRegKey@@QEAAJPEBG0@Z; CUwfRegKey::SetSzValue(ushort const *,ushort const *)
0x18000a7e8  mov     ebx, eax
0x18000a7ea  mov     rcx, rsi
0x18000a7ed  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000a7f3  mov     eax, ebx
0x18000a7f5  add     rsp, 50h
0x18000a7f9  pop     r15
0x18000a7fb  pop     r14
0x18000a7fd  pop     r12
0x18000a7ff  pop     rdi
0x18000a800  pop     rsi
0x18000a801  pop     rbp
0x18000a802  pop     rbx
0x18000a803  retn
0x18000a804  mov     rsi, rdi
0x18000a807  mov     rdx, rbp; String2
0x18000a80a  mov     rcx, rsi; String1
0x18000a80d  call    cs:__imp__wcsicmp
0x18000a813  test    eax, eax
0x18000a815  jnz     short loc_18000A7C2
0x18000a817  lea     ebx, [rax+1]
0x18000a81a  jmp     short loc_18000A7EA
```
