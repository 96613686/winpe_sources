# Microsoft::Windows::Performance::CCvDDCache::Find(ushort const *,ulong,ulong *,_CVDD const * *,ulong const * *,CODEVIEW_INFORMATION_1 const * *,ulong *,ulong *,EMBEDDED_PDB_INFORMATION &,bool &,ushort *,ulong)

- ea: `0x180018de8`
- end: `0x180018ff3`
- name: `?Find@CCvDDCache@Performance@Windows@Microsoft@@QEAAJPEBGKPEAKPEAPEBT_CVDD@@PEAPEBKPEAPEBUCODEVIEW_INFORMATION_1@@11AEAUEMBEDDED_PDB_INFORMATION@@AEA_NPEAGK@Z`
- size: `523`
- prototype: `int(Microsoft::Windows::Performance::CCvDDCache *__hidden this, const unsigned __int16 *, unsigned int, unsigned int *, const union _CVDD **, const unsigned int **, const struct CODEVIEW_INFORMATION_1 **, unsigned int *, unsigned int *, struct EMBEDDED_PDB_INFORMATION *, bool *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180016698`

## callees

- `0x1800059d8`
- `0x180015950`
- `0x180018de8`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180018e4c`
- `msvcrt!_wcsicmp` at `0x180018e7d`
- `msvcrt!_wcsicmp` at `0x180018eb0`
- `msvcrt!_wcsicmp` at `0x180018ee2`
- `msvcrt!_wcsicmp` at `0x180018e4c`
- `msvcrt!_wcsicmp` at `0x180018e7d`
- `msvcrt!_wcsicmp` at `0x180018eb0`
- `msvcrt!_wcsicmp` at `0x180018ee2`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CCvDDCache::Find(
        __int64 **this,
        const unsigned __int16 *a2,
        int a3,
        unsigned int *a4,
        const union _CVDD **a5,
        const unsigned int **a6,
        const struct CODEVIEW_INFORMATION_1 **a7,
        unsigned int *a8,
        unsigned int *a9,
        struct EMBEDDED_PDB_INFORMATION *a10,
        bool *a11,
        unsigned __int16 *a12)
{
  __int64 v14; // rbx
  char v15; // si
  bool *v16; // r13
  __int64 *v17; // r14
  __int64 v18; // rsi
  __int64 v19; // rdi
  __int64 *v20; // rax
  __int64 *v21; // r14
  __int64 v22; // rdi
  struct EMBEDDED_PDB_INFORMATION *v23; // rcx
  const unsigned __int16 *v24; // r8
  __int64 result; // rax
  int v26; // [rsp+70h] [rbp+18h] BYREF
  unsigned int *v27; // [rsp+78h] [rbp+20h]

  v27 = a4;
  v26 = a3;
  try
  {
    v14 = 0;
    v15 = 0;
    v16 = a11;
    *a11 = 0;
    if ( a3 )
    {
      v17 = std::map<unsigned long,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>::operator[](
              this + 2,
              &v26);
      v18 = *v17;
      v19 = *(_QWORD *)(*v17 + 8);
      while ( !*(_BYTE *)(v19 + 25) )
      {
        if ( _wcsicmp(*(const wchar_t **)(v19 + 32), a2) >= 0 )
        {
          v18 = v19;
          v19 = *(_QWORD *)v19;
        }
        else
        {
          v19 = *(_QWORD *)(v19 + 16);
        }
      }
      v20 = (__int64 *)*v17;
      if ( v18 != *v17 )
      {
        if ( _wcsicmp(a2, *(const wchar_t **)(v18 + 32)) >= 0 )
          v20 = (__int64 *)v18;
        else
          v20 = (__int64 *)*v17;
      }
      if ( v20 == (__int64 *)*v17 )
      {
        v15 = 0;
        goto LABEL_25;
      }
    }
    else
    {
      v21 = this[4];
      v22 = v21[1];
      while ( !*(_BYTE *)(v22 + 25) )
      {
        if ( _wcsicmp(*(const wchar_t **)(v22 + 32), a2) >= 0 )
        {
          v21 = (__int64 *)v22;
          v22 = *(_QWORD *)v22;
        }
        else
        {
          v22 = *(_QWORD *)(v22 + 16);
        }
      }
      v20 = this[4];
      if ( v21 != v20 )
      {
        if ( _wcsicmp(a2, (const wchar_t *)v21[4]) >= 0 )
          v20 = v21;
        else
          v20 = this[4];
      }
      if ( v20 == this[4] )
        goto LABEL_25;
    }
    v15 = 1;
    v14 = v20[5];
LABEL_25:
    if ( v15 )
    {
      if ( v14 )
      {
        *v27 = *(_DWORD *)(v14 + 64);
        *a5 = *(const union _CVDD **)(v14 + 72);
        *a6 = *(const unsigned int **)(v14 + 80);
        if ( a7 )
          *a7 = *(const struct CODEVIEW_INFORMATION_1 **)(v14 + 88);
        *a8 = *(_DWORD *)(v14 + 132);
        *a9 = *(_DWORD *)(v14 + 136);
        v23 = a10;
        *(_DWORD *)a10 = *(_DWORD *)(v14 + 104) - *(_DWORD *)(v14 + 96);
        *((_QWORD *)v23 + 1) = *(_QWORD *)(v14 + 96);
        *((_WORD *)v23 + 8) = *(_WORD *)(v14 + 122);
        *((_WORD *)v23 + 9) = *(_WORD *)(v14 + 120);
        *v16 = *(_BYTE *)(v14 + 124);
        v24 = (const unsigned __int16 *)(v14 + 32);
        if ( *(_QWORD *)(v14 + 56) >= 8u )
          v24 = *(const unsigned __int16 **)v24;
        result = StringCchCopyW(a12, 0x30Cu, v24);
      }
      else
      {
        result = 2147500037LL;
      }
    }
    else
    {
      result = 2147943568LL;
    }
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x180018de8  mov     rax, rsp
0x180018deb  mov     [rax+20h], r9
0x180018def  mov     [rax+18h], r8d
0x180018df3  push    rdi
0x180018df4  push    r12
0x180018df6  push    r13
0x180018df8  push    r14
0x180018dfa  push    r15
0x180018dfc  sub     rsp, 30h
0x180018e00  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x180018e08  mov     [rax+8], rbx
0x180018e0c  mov     [rax+10h], rsi
0x180018e10  mov     r12, rdx
0x180018e13  mov     r15, rcx
0x180018e16  xor     ebx, ebx
0x180018e18  xor     sil, sil
0x180018e1b  mov     r13, [rsp+58h+arg_50]
0x180018e23  mov     [r13+0], bl
0x180018e27  test    r8d, r8d
0x180018e2a  jz      short loc_180018E9F
0x180018e2c  add     rcx, 10h
0x180018e30  lea     rdx, [rax+18h]
0x180018e34  call    ??A?$map@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@@std@@QEAAAEAV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@1@AEBK@Z; std::map<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>::operator[](ulong const &)
0x180018e39  mov     r14, rax
0x180018e3c  mov     rsi, [rax]
0x180018e3f  mov     rdi, [rsi+8]
0x180018e43  jmp     short loc_180018E68
0x180018e45  mov     rdx, r12; String2
0x180018e48  mov     rcx, [rdi+20h]; String1
0x180018e4c  call    cs:__imp__wcsicmp
0x180018e53  nop     dword ptr [rax+rax+00h]
0x180018e58  test    eax, eax
0x180018e5a  jns     short loc_180018E62
0x180018e5c  mov     rdi, [rdi+10h]
0x180018e60  jmp     short loc_180018E68
0x180018e62  mov     rsi, rdi
0x180018e65  mov     rdi, [rdi]
0x180018e68  cmp     byte ptr [rdi+19h], 0
0x180018e6c  jz      short loc_180018E45
0x180018e6e  mov     rax, [r14]
0x180018e71  cmp     rsi, rax
0x180018e74  jz      short loc_180018E95
0x180018e76  mov     rdx, [rsi+20h]; String2
0x180018e7a  mov     rcx, r12; String1
0x180018e7d  call    cs:__imp__wcsicmp
0x180018e84  nop     dword ptr [rax+rax+00h]
0x180018e89  test    eax, eax
0x180018e8b  jns     short loc_180018E92
0x180018e8d  mov     rax, [r14]
0x180018e90  jmp     short loc_180018E95
0x180018e92  mov     rax, rsi
0x180018e95  cmp     rax, [r14]
0x180018e98  jnz     short loc_180018F01
0x180018e9a  xor     sil, sil
0x180018e9d  jmp     short loc_180018F08
0x180018e9f  mov     r14, [rcx+20h]
0x180018ea3  mov     rdi, [r14+8]
0x180018ea7  jmp     short loc_180018ECC
0x180018ea9  mov     rdx, r12; String2
0x180018eac  mov     rcx, [rdi+20h]; String1
0x180018eb0  call    cs:__imp__wcsicmp
0x180018eb7  nop     dword ptr [rax+rax+00h]
0x180018ebc  test    eax, eax
0x180018ebe  jns     short loc_180018EC6
0x180018ec0  mov     rdi, [rdi+10h]
0x180018ec4  jmp     short loc_180018ECC
0x180018ec6  mov     r14, rdi
0x180018ec9  mov     rdi, [rdi]
0x180018ecc  cmp     byte ptr [rdi+19h], 0
0x180018ed0  jz      short loc_180018EA9
0x180018ed2  mov     rax, [r15+20h]
0x180018ed6  cmp     r14, rax
0x180018ed9  jz      short loc_180018EFB
0x180018edb  mov     rdx, [r14+20h]; String2
0x180018edf  mov     rcx, r12; String1
0x180018ee2  call    cs:__imp__wcsicmp
0x180018ee9  nop     dword ptr [rax+rax+00h]
0x180018eee  test    eax, eax
0x180018ef0  jns     short loc_180018EF8
0x180018ef2  mov     rax, [r15+20h]
0x180018ef6  jmp     short loc_180018EFB
0x180018ef8  mov     rax, r14
0x180018efb  cmp     rax, [r15+20h]
0x180018eff  jz      short loc_180018F08
0x180018f01  mov     sil, 1
0x180018f04  mov     rbx, [rax+28h]
0x180018f08  test    sil, sil
0x180018f0b  jz      loc_180018FCE
0x180018f11  test    rbx, rbx
0x180018f14  jz      loc_180018FC7
0x180018f1a  mov     eax, [rbx+40h]
0x180018f1d  mov     rcx, [rsp+58h+arg_18]
0x180018f22  mov     [rcx], eax
0x180018f24  mov     rcx, [rbx+48h]
0x180018f28  mov     rax, [rsp+58h+arg_20]
0x180018f30  mov     [rax], rcx
0x180018f33  mov     rcx, [rbx+50h]
0x180018f37  mov     rax, [rsp+58h+arg_28]
0x180018f3f  mov     [rax], rcx
0x180018f42  mov     rcx, [rsp+58h+arg_30]
0x180018f4a  test    rcx, rcx
0x180018f4d  jz      short loc_180018F56
0x180018f4f  mov     rax, [rbx+58h]
0x180018f53  mov     [rcx], rax
0x180018f56  mov     ecx, [rbx+84h]
0x180018f5c  mov     rax, [rsp+58h+arg_38]
0x180018f64  mov     [rax], ecx
0x180018f66  mov     ecx, [rbx+88h]
0x180018f6c  mov     rax, [rsp+58h+arg_40]
0x180018f74  mov     [rax], ecx
0x180018f76  mov     eax, [rbx+68h]
0x180018f79  sub     eax, [rbx+60h]
0x180018f7c  mov     rcx, [rsp+58h+arg_48]
0x180018f84  mov     [rcx], eax
0x180018f86  mov     rax, [rbx+60h]
0x180018f8a  mov     [rcx+8], rax
0x180018f8e  movzx   eax, word ptr [rbx+7Ah]
0x180018f92  mov     [rcx+10h], ax
0x180018f96  movzx   eax, word ptr [rbx+78h]
0x180018f9a  mov     [rcx+12h], ax
0x180018f9e  mov     al, [rbx+7Ch]
0x180018fa1  mov     [r13+0], al
0x180018fa5  lea     r8, [rbx+20h]
0x180018fa9  cmp     qword ptr [r8+18h], 8
0x180018fae  jb      short loc_180018FB3
0x180018fb0  mov     r8, [r8]; unsigned __int16 *
0x180018fb3  mov     edx, 30Ch; unsigned __int64
0x180018fb8  mov     rcx, [rsp+58h+arg_58]; unsigned __int16 *
0x180018fc0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180018fc5  jmp     short loc_180018FDA
0x180018fc7  mov     eax, 80004005h
0x180018fcc  jmp     short loc_180018FDA
0x180018fce  mov     eax, 80070490h
0x180018fd3  jmp     short loc_180018FDA
0x180018fd5  mov     eax, 8007000Eh
0x180018fda  mov     rbx, [rsp+58h+arg_0]
0x180018fdf  mov     rsi, [rsp+58h+arg_8]
0x180018fe4  add     rsp, 30h
0x180018fe8  pop     r15
0x180018fea  pop     r14
0x180018fec  pop     r13
0x180018fee  pop     r12
0x180018ff0  pop     rdi
0x180018ff1  retn
```
