# CUwfConfiguration::ResetUwfSettings(void)

- ea: `0x1800091f0`
- end: `0x18000929f`
- name: `?ResetUwfSettings@CUwfConfiguration@@QEAAJXZ`
- size: `175`
- prototype: `__int64 __fastcall(HKEY *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x1800166c0`

## callees

- `0x180006ae0`
- `0x1800079a0`
- `0x180008924`
- `0x1800091f0`
- `0x18000d5f0`

## pseudocode

```c
__int64 __fastcall CUwfConfiguration::ResetUwfSettings(HKEY *this)
{
  int v2; // ebx
  HKEY v4; // [rsp+58h] [rbp+28h] BYREF
  HKEY v5; // [rsp+60h] [rbp+30h] BYREF
  HKEY v6; // [rsp+68h] [rbp+38h] BYREF

  v6 = 0;
  v5 = 0;
  v4 = 0;
  v2 = CUwfConfiguration::FixupUpdatedSettings((CUwfConfiguration *)this);
  if ( v2 < 0
    || (v2 = CUwfConfiguration::OpenUwfSettingKeys((CUwfConfiguration *)this, &v6, &v5, &v4), v2 < 0)
    || (v2 = CUwfConfiguration::CopyTree((CUwfConfiguration *)this, (struct CUwfRegKey *)&v6, 0, this[3], 1), v2 < 0)
    || (v2 = CUwfConfiguration::CopyTree((CUwfConfiguration *)this, (struct CUwfRegKey *)&v5, 0, v4, 1), v2 < 0) )
  {
    *((_DWORD *)this + 4) = v2;
  }
  CUwfRegKey::Close(&v4);
  CUwfRegKey::Close(&v5);
  CUwfRegKey::Close(&v6);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800091f0  push    rbp
0x1800091f2  push    rbx
0x1800091f3  push    rdi
0x1800091f4  mov     rbp, rsp
0x1800091f7  sub     rsp, 30h
0x1800091fb  mov     rdi, rcx
0x1800091fe  mov     [rbp+arg_18], 0
0x180009206  mov     [rbp+arg_10], 0
0x18000920e  mov     [rbp+arg_8], 0
0x180009216  call    ?FixupUpdatedSettings@CUwfConfiguration@@QEAAJXZ; CUwfConfiguration::FixupUpdatedSettings(void)
0x18000921b  mov     ebx, eax
0x18000921d  test    eax, eax
0x18000921f  js      short loc_180009277
0x180009221  lea     r9, [rbp+arg_8]; struct CUwfRegKey *
0x180009225  mov     rcx, rdi; this
0x180009228  lea     r8, [rbp+arg_10]; struct CUwfRegKey *
0x18000922c  lea     rdx, [rbp+arg_18]; struct CUwfRegKey *
0x180009230  call    ?OpenUwfSettingKeys@CUwfConfiguration@@AEAAJAEAVCUwfRegKey@@00@Z; CUwfConfiguration::OpenUwfSettingKeys(CUwfRegKey &,CUwfRegKey &,CUwfRegKey &)
0x180009235  mov     ebx, eax
0x180009237  test    eax, eax
0x180009239  js      short loc_180009277
0x18000923b  mov     r9, [rdi+18h]; HKEY
0x18000923f  lea     rdx, [rbp+arg_18]; struct CUwfRegKey *
0x180009243  xor     r8d, r8d; unsigned __int16 *
0x180009246  mov     [rsp+30h+var_10], 1; bool
0x18000924b  mov     rcx, rdi; this
0x18000924e  call    ?CopyTree@CUwfConfiguration@@QEAAJAEAVCUwfRegKey@@PEBGPEAUHKEY__@@_N@Z; CUwfConfiguration::CopyTree(CUwfRegKey &,ushort const *,HKEY__ *,bool)
0x180009253  mov     ebx, eax
0x180009255  test    eax, eax
0x180009257  js      short loc_180009277
0x180009259  mov     r9, [rbp+arg_8]; HKEY
0x18000925d  lea     rdx, [rbp+arg_10]; struct CUwfRegKey *
0x180009261  xor     r8d, r8d; unsigned __int16 *
0x180009264  mov     [rsp+30h+var_10], 1; bool
0x180009269  mov     rcx, rdi; this
0x18000926c  call    ?CopyTree@CUwfConfiguration@@QEAAJAEAVCUwfRegKey@@PEBGPEAUHKEY__@@_N@Z; CUwfConfiguration::CopyTree(CUwfRegKey &,ushort const *,HKEY__ *,bool)
0x180009271  mov     ebx, eax
0x180009273  test    eax, eax
0x180009275  jns     short loc_18000927A
0x180009277  mov     [rdi+10h], ebx
0x18000927a  lea     rcx, [rbp+arg_8]; this
0x18000927e  call    ?Close@CUwfRegKey@@QEAAJXZ; CUwfRegKey::Close(void)
0x180009283  lea     rcx, [rbp+arg_10]; this
0x180009287  call    ?Close@CUwfRegKey@@QEAAJXZ; CUwfRegKey::Close(void)
0x18000928c  lea     rcx, [rbp+arg_18]; this
0x180009290  call    ?Close@CUwfRegKey@@QEAAJXZ; CUwfRegKey::Close(void)
0x180009295  mov     eax, ebx
0x180009297  add     rsp, 30h
0x18000929b  pop     rdi
0x18000929c  pop     rbx
0x18000929d  pop     rbp
0x18000929e  retn
```
