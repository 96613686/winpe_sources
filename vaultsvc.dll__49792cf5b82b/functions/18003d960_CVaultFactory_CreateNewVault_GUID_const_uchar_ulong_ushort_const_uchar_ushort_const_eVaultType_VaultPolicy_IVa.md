# CVaultFactory::CreateNewVault(_GUID const *,uchar *,ulong,ushort const *,uchar,ushort const *,eVaultType,VaultPolicy *,IVaultStore * *)

- ea: `0x18003d960`
- end: `0x18003da27`
- name: `?CreateNewVault@CVaultFactory@@UEAAKPEBU_GUID@@PEAEKPEBGE2W4eVaultType@@PEAUVaultPolicy@@PEAPEAUIVaultStore@@@Z`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x180037f5c`

## callees

- `0x180003140`
- `0x18003b920`
- `0x18003d960`
- `0x180040944`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVaultFactory::CreateNewVault(
        __int64 a1,
        const struct _GUID *a2,
        __int64 a3,
        unsigned int a4,
        wchar_t *Source,
        __int64 a6,
        __int64 a7,
        int a8,
        __int64 a9,
        _QWORD *a10)
{
  unsigned int v14; // ebx
  unsigned int v15; // [rsp+20h] [rbp-50h]
  CVaultFileStore *v16; // [rsp+50h] [rbp-20h] BYREF
  __int64 v17; // [rsp+58h] [rbp-18h] BYREF
  unsigned __int16 *v18; // [rsp+60h] [rbp-10h] BYREF
  int v19; // [rsp+68h] [rbp-8h]

  v18 = 0;
  v19 = 0;
  v17 = 0;
  v16 = 0;
  if ( Source )
  {
    v14 = BuildVaultPath(Source, a2, &v18);
    if ( v14 )
    {
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v17);
    }
    else
    {
      v14 = CVaultFileStore::CreateNewVault((__int64)a2, a3, a4, v18, v15, a7, a8, a9, &v16);
      if ( !v14 )
        *a10 = v16;
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v17);
    }
    return v14;
  }
  else
  {
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v17);
    return 87;
  }
}

```

## disassembly

```asm
0x18003d960  push    rbp
0x18003d962  push    rbx
0x18003d963  push    rsi
0x18003d964  push    rdi
0x18003d965  push    r14
0x18003d967  mov     rbp, rsp
0x18003d96a  sub     rsp, 70h
0x18003d96e  mov     esi, r9d
0x18003d971  mov     r14, r8
0x18003d974  mov     rdi, rdx
0x18003d977  mov     [rbp+var_10], 0
0x18003d97f  mov     [rbp+var_8], 0
0x18003d986  mov     [rbp+var_18], 0
0x18003d98e  mov     [rbp+var_20], 0
0x18003d996  mov     rcx, [rbp+Source]; Source
0x18003d99a  test    rcx, rcx
0x18003d99d  jnz     short loc_18003D9B0
0x18003d99f  lea     rcx, [rbp+var_18]
0x18003d9a3  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003d9a8  nop
0x18003d9a9  mov     eax, 57h ; 'W'
0x18003d9ae  jmp     short loc_18003DA1C
0x18003d9b0  lea     r8, [rbp+var_10]; unsigned __int16 **
0x18003d9b4  call    ?BuildVaultPath@@YAKPEBGPEBU_GUID@@PEAPEAG@Z; BuildVaultPath(ushort const *,_GUID const *,ushort * *)
0x18003d9b9  mov     ebx, eax
0x18003d9bb  test    eax, eax
0x18003d9bd  jz      short loc_18003D9CB
0x18003d9bf  lea     rcx, [rbp+var_18]
0x18003d9c3  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003d9c8  nop
0x18003d9c9  jmp     short loc_18003DA1A
0x18003d9cb  lea     rax, [rbp+var_20]
0x18003d9cf  mov     [rsp+70h+var_30], rax
0x18003d9d4  mov     rax, [rbp+arg_40]
0x18003d9d8  mov     [rsp+70h+var_38], rax
0x18003d9dd  mov     eax, [rbp+arg_38]
0x18003d9e0  mov     [rsp+70h+var_40], eax
0x18003d9e4  mov     rax, [rbp+arg_30]
0x18003d9e8  mov     [rsp+70h+var_48], rax
0x18003d9ed  mov     r9, [rbp+var_10]
0x18003d9f1  mov     r8d, esi
0x18003d9f4  mov     rdx, r14
0x18003d9f7  mov     rcx, rdi
0x18003d9fa  call    ?CreateNewVault@CVaultFileStore@@SAKPEBU_GUID@@PEAEKPEBGE2W4eVaultType@@PEAUVaultPolicy@@PEAPEAV1@@Z; CVaultFileStore::CreateNewVault(_GUID const *,uchar *,ulong,ushort const *,uchar,ushort const *,eVaultType,VaultPolicy *,CVaultFileStore * *)
0x18003d9ff  mov     ebx, eax
0x18003da01  test    eax, eax
0x18003da03  jnz     short loc_18003DA10
0x18003da05  mov     rdx, [rbp+arg_48]
0x18003da09  mov     rcx, [rbp+var_20]
0x18003da0d  mov     [rdx], rcx
0x18003da10  lea     rcx, [rbp+var_18]
0x18003da14  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003da19  nop
0x18003da1a  mov     eax, ebx
0x18003da1c  add     rsp, 70h
0x18003da20  pop     r14
0x18003da22  pop     rdi
0x18003da23  pop     rsi
0x18003da24  pop     rbx
0x18003da25  pop     rbp
0x18003da26  retn
```
