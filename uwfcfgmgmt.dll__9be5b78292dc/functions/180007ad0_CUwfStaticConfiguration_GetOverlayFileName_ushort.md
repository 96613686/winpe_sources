# CUwfStaticConfiguration::GetOverlayFileName(ushort * *)

- ea: `0x180007ad0`
- end: `0x180007e32`
- name: `?GetOverlayFileName@CUwfStaticConfiguration@@QEAAJPEAPEAG@Z`
- size: `866`
- prototype: `__int64 __fastcall(CUwfStaticConfiguration *__hidden this, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `11`
- tags: `file_ops, registry_config`

## callers

- `0x180006bb0`
- `0x180007250`
- `0x1800085b0`
- `0x1800098d0`

## callees

- `0x180001384`
- `0x180001390`
- `0x180002686`
- `0x1800054d0`
- `0x180007ad0`
- `0x180008300`
- `0x180008cf0`
- `0x18000e0f0`
- `0x18000e320`
- `0x180012084`
- `0x18001c010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180007c39`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007c56`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007d54`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007d95`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007db9`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007dfb`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007e08`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007c39`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007c56`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007d54`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007d95`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007db9`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007dfb`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007e08`

## pseudocode

```c
__int64 __fastcall CUwfStaticConfiguration::GetOverlayFileName(CUwfStaticConfiguration *this, unsigned __int16 **a2)
{
  unsigned __int16 *v2; // rdi
  signed int DWORDValue; // ebx
  unsigned int i; // r15d
  unsigned __int16 *v7; // r14
  unsigned __int16 *v8; // rax
  int v9; // eax
  unsigned __int64 v10; // rbx
  _WORD *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rdi
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // rbx
  void *v16; // rcx
  unsigned __int16 *v17; // rcx
  _BYTE v19[18]; // [rsp+30h] [rbp-40h]
  unsigned int v20; // [rsp+B8h] [rbp+48h] BYREF
  unsigned __int16 *v21; // [rsp+C0h] [rbp+50h] BYREF
  void *Src; // [rsp+C8h] [rbp+58h] BYREF

  v2 = 0;
  *a2 = 0;
  LODWORD(v21) = 0;
  DWORDValue = CUwfRegKey::QueryDWORDValue(
                 (CUwfStaticConfiguration *)((char *)this + 24),
                 L"NumVolumes",
                 (unsigned int *)&v21);
  if ( DWORDValue < 0 )
    goto LABEL_38;
  for ( i = 0; i < (unsigned int)v21; ++i )
  {
    v7 = (unsigned __int16 *)*((_QWORD *)this + 5);
    if ( v7 )
    {
      DWORDValue = 0;
    }
    else
    {
      v8 = (unsigned __int16 *)operator new(0x28u);
      v2 = v8;
      if ( !v8 )
        goto LABEL_31;
      *((_QWORD *)v8 + 2) = 0;
      *((_QWORD *)v8 + 3) = 0;
      v7 = 0;
      *((_QWORD *)v8 + 4) = 0;
      *(_QWORD *)v8 = &CUwfStaticVolumeConfiguration::`vftable';
      *(unsigned __int16 *)((char *)v8 + 9) = 1;
      *((_DWORD *)v8 + 3) = -1;
      DWORDValue = CUwfStaticVolumeConfiguration::Initialize(
                     (CUwfStaticVolumeConfiguration *)v8,
                     *((HKEY *)this + 3),
                     i,
                     *((_BYTE *)this + 8),
                     *((struct CUwfConfiguration **)this + 4),
                     this);
      if ( DWORDValue < 0 )
        goto LABEL_10;
      *((_QWORD *)this + 5) = v2;
      v7 = v2;
    }
    if ( *((_DWORD *)v7 + 3) == i )
      goto LABEL_12;
    v7 = 0;
    DWORDValue = -2147024891;
LABEL_10:
    if ( v2 )
      (**(void (__fastcall ***)(unsigned __int16 *, __int64))v2)(v2, 1);
LABEL_12:
    v2 = 0;
    if ( DWORDValue != -2147024893 )
    {
      if ( DWORDValue < 0 )
        goto LABEL_38;
      Src = 0;
      DWORDValue = CUwfRegKey::QuerySzValue((CUwfRegKey *)(v7 + 8), L"VolumeName", (unsigned __int16 **)&Src);
      if ( DWORDValue < 0 )
        goto LABEL_37;
      v20 = 0;
      v9 = CUwfRegKey::QueryDWORDValue((CUwfRegKey *)(v7 + 8), L"SwapfileSize", &v20);
      DWORDValue = v9;
      if ( v9 == -2147024894 )
      {
        v20 = 0;
      }
      else
      {
        if ( v9 < 0 )
        {
          v16 = Src;
          goto LABEL_36;
        }
        if ( v20 )
        {
          if ( Src )
          {
            v11 = Src;
            v12 = 0x7FFFFFFF;
            do
            {
              if ( !*v11 )
                break;
              ++v11;
              --v12;
            }
            while ( v12 );
            DWORDValue = v12 == 0 ? 0x80070057 : 0;
            v13 = (0x7FFFFFFF - v12) & -(__int64)(v12 != 0);
            if ( v12 )
            {
              *(_OWORD *)v19 = *(_OWORD *)L"\\uwfswap.sys";
              *(_QWORD *)&v19[10] = *(_QWORD *)L"wap.sys";
              v14 = (unsigned __int16 *)operator new[](saturated_mul(v13 + 18, 2u));
              v15 = v14;
              if ( !v14 )
              {
                operator delete[](Src);
                CUwfStaticConfiguration::ReleaseStaticVolumeConfiguration(this);
LABEL_31:
                DWORDValue = -2147024882;
                goto LABEL_38;
              }
              *(_QWORD *)v14 = *(_QWORD *)L"\\??\\";
              v14[4] = asc_180020470[4];
              memcpy_0(v14 + 4, Src, 2 * v13);
              *(_OWORD *)&v15[v13 + 4] = *(_OWORD *)v19;
              *(_OWORD *)&v15[v13 + 9] = *(_OWORD *)L"wap.sys";
              operator delete[](Src);
              CUwfStaticConfiguration::ReleaseStaticVolumeConfiguration(this);
              *a2 = v15;
              DWORDValue = 0;
LABEL_38:
              v17 = 0;
LABEL_43:
              operator delete[](v17);
              return (unsigned int)DWORDValue;
            }
          }
          else
          {
            DWORDValue = -2147024809;
          }
          v16 = Src;
LABEL_36:
          operator delete[](v16);
LABEL_37:
          CUwfStaticConfiguration::ReleaseStaticVolumeConfiguration(this);
          goto LABEL_38;
        }
      }
      operator delete[](Src);
      CUwfStaticConfiguration::ReleaseStaticVolumeConfiguration(this);
    }
  }
  operator delete[](0);
  v21 = 0;
  v20 = 0;
  DWORDValue = ExpandEnvironmentStringsHelper(L"\\??\\%SystemDrive%", &v21, &v20);
  if ( DWORDValue >= 0 )
  {
    v10 = v20 + 13;
    v2 = (unsigned __int16 *)operator new[](saturated_mul(v10, 2u));
    if ( v2 )
    {
      DWORDValue = StringCchPrintfW(v2, v10, L"%s\\%s", v21, L"uwfswap.sys");
      if ( DWORDValue >= 0 )
        *a2 = v2;
    }
    else
    {
      DWORDValue = -2147024882;
    }
  }
  operator delete[](v21);
  if ( DWORDValue < 0 )
  {
    v17 = v2;
    goto LABEL_43;
  }
  return (unsigned int)DWORDValue;
}

```

## disassembly

```asm
0x180007ad0  mov     [rsp-38h+arg_0], rbx
0x180007ad5  push    rbp
0x180007ad6  push    rsi
0x180007ad7  push    rdi
0x180007ad8  push    r12
0x180007ada  push    r13
0x180007adc  push    r14
0x180007ade  push    r15
0x180007ae0  mov     rbp, rsp
0x180007ae3  sub     rsp, 70h
0x180007ae7  xor     edi, edi
0x180007ae9  movaps  [rsp+70h+var_10], xmm6
0x180007aee  mov     [rdx], rdi
0x180007af1  lea     r8, [rbp+arg_10]; unsigned int *
0x180007af5  mov     r12, rdx
0x180007af8  movaps  [rsp+70h+var_20], xmm7
0x180007afd  mov     rsi, rcx
0x180007b00  mov     dword ptr [rbp+arg_10], edi
0x180007b03  lea     rdx, aNumvolumes; "NumVolumes"
0x180007b0a  add     rcx, 18h; this
0x180007b0e  call    ?QueryDWORDValue@CUwfRegKey@@QEAAJPEBGPEAK@Z; CUwfRegKey::QueryDWORDValue(ushort const *,ulong *)
0x180007b13  mov     ebx, eax
0x180007b15  test    eax, eax
0x180007b17  js      loc_180007DC7
0x180007b1d  mov     r15d, edi
0x180007b20  cmp     dword ptr [rbp+arg_10], edi
0x180007b23  jbe     loc_180007C54
0x180007b29  mov     r14, [rsi+28h]
0x180007b2d  test    r14, r14
0x180007b30  jnz     short loc_180007BA1
0x180007b32  lea     ecx, [r14+28h]; Size
0x180007b36  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007b3b  xor     ecx, ecx
0x180007b3d  mov     rdi, rax
0x180007b40  test    rax, rax
0x180007b43  jz      loc_180007D62
0x180007b49  mov     [rdi+10h], rcx
0x180007b4d  lea     rax, ??_7CUwfStaticVolumeConfiguration@@6B@; const CUwfStaticVolumeConfiguration::`vftable'
0x180007b54  mov     [rdi+18h], rcx
0x180007b58  mov     r14d, ecx
0x180007b5b  mov     [rdi+20h], rcx
0x180007b5f  mov     r8d, r15d; unsigned int
0x180007b62  mov     [rdi], rax
0x180007b65  mov     rcx, rdi; this
0x180007b68  mov     word ptr [rdi+9], 1
0x180007b6e  mov     dword ptr [rdi+0Ch], 0FFFFFFFFh
0x180007b75  mov     rax, [rsi+20h]
0x180007b79  mov     r9b, [rsi+8]; bool
0x180007b7d  mov     rdx, [rsi+18h]; HKEY
0x180007b81  mov     [rsp+70h+var_48], rsi; struct CUwfStaticConfiguration *
0x180007b86  mov     [rsp+70h+var_50], rax; struct CUwfConfiguration *
0x180007b8b  call    ?Initialize@CUwfStaticVolumeConfiguration@@QEAAJPEAUHKEY__@@K_NPEAVCUwfConfiguration@@PEAVCUwfStaticConfiguration@@@Z; CUwfStaticVolumeConfiguration::Initialize(HKEY__ *,ulong,bool,CUwfConfiguration *,CUwfStaticConfiguration *)
0x180007b90  mov     ebx, eax
0x180007b92  xor     eax, eax
0x180007b94  test    ebx, ebx
0x180007b96  js      short loc_180007BB3
0x180007b98  mov     [rsi+28h], rdi
0x180007b9c  mov     r14, rdi
0x180007b9f  jmp     short loc_180007BA5
0x180007ba1  xor     eax, eax
0x180007ba3  mov     ebx, eax
0x180007ba5  cmp     [r14+0Ch], r15d
0x180007ba9  jz      short loc_180007BCB
0x180007bab  mov     r14, rax
0x180007bae  mov     ebx, 80070005h
0x180007bb3  test    rdi, rdi
0x180007bb6  jz      short loc_180007BCB
0x180007bb8  mov     rax, [rdi]
0x180007bbb  mov     edx, 1
0x180007bc0  mov     rcx, rdi
0x180007bc3  mov     rax, [rax]
0x180007bc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bcb  xor     edi, edi
0x180007bcd  cmp     ebx, 80070003h
0x180007bd3  jz      short loc_180007C47
0x180007bd5  test    ebx, ebx
0x180007bd7  js      loc_180007DC7
0x180007bdd  lea     r8, [rbp+Src]; unsigned __int16 **
0x180007be1  mov     [rbp+Src], rdi
0x180007be5  lea     rdx, aVolumename; "VolumeName"
0x180007bec  lea     rcx, [r14+10h]; this
0x180007bf0  call    ?QuerySzValue@CUwfRegKey@@QEAAJPEBGPEAPEAG@Z; CUwfRegKey::QuerySzValue(ushort const *,ushort * *)
0x180007bf5  mov     ebx, eax
0x180007bf7  test    eax, eax
0x180007bf9  js      loc_180007DBF
0x180007bff  lea     r8, [rbp+arg_8]; unsigned int *
0x180007c03  mov     [rbp+arg_8], edi
0x180007c06  lea     rdx, aSwapfilesize; "SwapfileSize"
0x180007c0d  lea     rcx, [r14+10h]; this
0x180007c11  call    ?QueryDWORDValue@CUwfRegKey@@QEAAJPEBGPEAK@Z; CUwfRegKey::QueryDWORDValue(ushort const *,ulong *)
0x180007c16  mov     ebx, eax
0x180007c18  cmp     eax, 80070002h
0x180007c1d  jnz     short loc_180007C24
0x180007c1f  mov     [rbp+arg_8], edi
0x180007c22  jmp     short loc_180007C35
0x180007c24  test    eax, eax
0x180007c26  js      loc_180007DB5
0x180007c2c  cmp     [rbp+arg_8], edi
0x180007c2f  jnz     loc_180007CB5
0x180007c35  mov     rcx, [rbp+Src]
0x180007c39  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180007c3f  mov     rcx, rsi; this
0x180007c42  call    ?ReleaseStaticVolumeConfiguration@CUwfStaticConfiguration@@QEAAXXZ; CUwfStaticConfiguration::ReleaseStaticVolumeConfiguration(void)
0x180007c47  inc     r15d
0x180007c4a  cmp     r15d, dword ptr [rbp+arg_10]
0x180007c4e  jb      loc_180007B29
0x180007c54  xor     ecx, ecx
0x180007c56  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180007c5c  xor     esi, esi
0x180007c5e  mov     [rbp+arg_10], rdi
0x180007c62  lea     r8, [rbp+arg_8]; unsigned int *
0x180007c66  mov     [rbp+arg_8], esi
0x180007c69  lea     rdx, [rbp+arg_10]; unsigned __int16 **
0x180007c6d  lea     rcx, aSystemdrive_0; "\\??\\%SystemDrive%"
0x180007c74  call    ?ExpandEnvironmentStringsHelper@@YAJPEBGPEAPEAGPEAK@Z; ExpandEnvironmentStringsHelper(ushort const *,ushort * *,ulong *)
0x180007c79  mov     ebx, eax
0x180007c7b  test    eax, eax
0x180007c7d  js      loc_180007DF7
0x180007c83  mov     ebx, [rbp+arg_8]
0x180007c86  lea     rcx, [rsi-1]
0x180007c8a  add     ebx, 0Dh
0x180007c8d  lea     eax, [rsi+2]
0x180007c90  mul     rbx
0x180007c93  cmovb   rax, rcx
0x180007c97  mov     rcx, rax; unsigned __int64
0x180007c9a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180007c9f  mov     rdi, rax
0x180007ca2  test    rax, rax
0x180007ca5  jnz     loc_180007DCB
0x180007cab  mov     ebx, 8007000Eh
0x180007cb0  jmp     loc_180007DF7
0x180007cb5  mov     r8, [rbp+Src]
0x180007cb9  test    r8, r8
0x180007cbc  jz      loc_180007DAB
0x180007cc2  mov     edx, 7FFFFFFFh
0x180007cc7  mov     rax, r8
0x180007cca  mov     ecx, edx
0x180007ccc  cmp     [rax], di
0x180007ccf  jz      short loc_180007CDB
0x180007cd1  add     rax, 2
0x180007cd5  sub     rcx, 1
0x180007cd9  jnz     short loc_180007CCC
0x180007cdb  mov     rax, rcx
0x180007cde  neg     rax
0x180007ce1  mov     rax, rcx
0x180007ce4  sbb     ebx, ebx
0x180007ce6  sub     rdx, rcx
0x180007ce9  not     ebx
0x180007ceb  and     ebx, 80070057h
0x180007cf1  neg     rax
0x180007cf4  sbb     rdi, rdi
0x180007cf7  and     rdi, rdx
0x180007cfa  test    rcx, rcx
0x180007cfd  jz      loc_180007DB0
0x180007d03  movups  xmm0, xmmword ptr cs:aUwfswapSys; "\\uwfswap.sys"
0x180007d0a  movzx   r14d, word ptr cs:asc_180020470+8; ""
0x180007d12  lea     rcx, [rdi+12h]
0x180007d16  movups  xmm6, xmmword ptr cs:aUwfswapSys+0Ah; "wap.sys"
0x180007d1d  mov     eax, 2
0x180007d22  movsd   xmm7, qword ptr cs:asc_180020470; "\\??\\"
0x180007d2a  mul     rcx
0x180007d2d  movups  [rbp+var_40], xmm0
0x180007d31  movups  [rbp+var_40+0Ah], xmm6
0x180007d35  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180007d3c  cmovb   rax, rcx
0x180007d40  mov     rcx, rax; unsigned __int64
0x180007d43  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180007d48  mov     rbx, rax
0x180007d4b  test    rax, rax
0x180007d4e  jnz     short loc_180007D69
0x180007d50  mov     rcx, [rbp+Src]
0x180007d54  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180007d5a  mov     rcx, rsi; this
0x180007d5d  call    ?ReleaseStaticVolumeConfiguration@CUwfStaticConfiguration@@QEAAXXZ; CUwfStaticConfiguration::ReleaseStaticVolumeConfiguration(void)
0x180007d62  mov     ebx, 8007000Eh
0x180007d67  jmp     short loc_180007DC7
0x180007d69  movsd   qword ptr [rax], xmm7
0x180007d6d  lea     r8, [rdi+rdi]; Size
0x180007d71  mov     [rax+8], r14w
0x180007d76  lea     rcx, [rax+8]; void *
0x180007d7a  mov     rdx, [rbp+Src]; Src
0x180007d7e  call    memcpy_0
0x180007d83  movups  xmm0, [rbp+var_40]
0x180007d87  movups  xmmword ptr [rbx+rdi*2+8], xmm0
0x180007d8c  movups  xmmword ptr [rbx+rdi*2+12h], xmm6
0x180007d91  mov     rcx, [rbp+Src]
0x180007d95  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180007d9b  mov     rcx, rsi; this
0x180007d9e  call    ?ReleaseStaticVolumeConfiguration@CUwfStaticConfiguration@@QEAAXXZ; CUwfStaticConfiguration::ReleaseStaticVolumeConfiguration(void)
0x180007da3  mov     [r12], rbx
0x180007da7  xor     ebx, ebx
0x180007da9  jmp     short loc_180007DC7
0x180007dab  mov     ebx, 80070057h
0x180007db0  mov     rcx, r8
0x180007db3  jmp     short loc_180007DB9
0x180007db5  mov     rcx, [rbp+Src]
0x180007db9  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180007dbf  mov     rcx, rsi; this
0x180007dc2  call    ?ReleaseStaticVolumeConfiguration@CUwfStaticConfiguration@@QEAAXXZ; CUwfStaticConfiguration::ReleaseStaticVolumeConfiguration(void)
0x180007dc7  xor     ecx, ecx
0x180007dc9  jmp     short loc_180007E08
0x180007dcb  mov     r9, [rbp+arg_10]
0x180007dcf  lea     rax, aUwfswapSys_0; "uwfswap.sys"
0x180007dd6  lea     r8, aSS; "%s\\%s"
0x180007ddd  mov     [rsp+70h+var_50], rax
0x180007de2  mov     rdx, rbx; unsigned __int64
0x180007de5  mov     rcx, rdi; unsigned __int16 *
0x180007de8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007ded  mov     ebx, eax
0x180007def  test    eax, eax
0x180007df1  js      short loc_180007DF7
0x180007df3  mov     [r12], rdi
0x180007df7  mov     rcx, [rbp+arg_10]
0x180007dfb  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180007e01  test    ebx, ebx
0x180007e03  jns     short loc_180007E0E
0x180007e05  mov     rcx, rdi
0x180007e08  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180007e0e  movaps  xmm6, [rsp+70h+var_10]
0x180007e13  mov     eax, ebx
0x180007e15  mov     rbx, [rsp+70h+arg_0]
0x180007e1d  movaps  xmm7, [rsp+70h+var_20]
0x180007e22  add     rsp, 70h
0x180007e26  pop     r15
0x180007e28  pop     r14
0x180007e2a  pop     r13
0x180007e2c  pop     r12
0x180007e2e  pop     rdi
0x180007e2f  pop     rsi
0x180007e30  pop     rbp
0x180007e31  retn
```
