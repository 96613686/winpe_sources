# RtlpReadExtendedContext

- ea: `0x1400fdb7c`
- end: `0x1400fdddc`
- name: `RtlpReadExtendedContext`
- size: `608`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140040e04`
- `0x14009c610`

## callees

- `0x1400442ac`
- `0x1400d6de4`
- `0x1400d85cc`
- `0x1400d9398`
- `0x1400d9434`
- `0x1400f3620`
- `0x1400fdb7c`
- `0x1400fdde4`

## pseudocode

```c
__int64 __fastcall RtlpReadExtendedContext(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, __int64 a5)
{
  __int64 result; // rax
  int v8; // ecx
  char v9; // r15
  ULONG v10; // esi
  __int64 v11; // r14
  int v12; // r11d
  __int64 v13; // rax
  _QWORD *XStateConfiguration2; // rax
  __int64 v15; // r10
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r9
  int v19; // [rsp+30h] [rbp-78h] BYREF
  __int64 v20; // [rsp+38h] [rbp-70h] BYREF
  int v21; // [rsp+40h] [rbp-68h]
  unsigned int v22; // [rsp+48h] [rbp-60h]
  __int64 v23; // [rsp+50h] [rbp-58h]
  SIZE_T Length[2]; // [rsp+58h] [rbp-50h] BYREF
  SIZE_T v25[2]; // [rsp+68h] [rbp-40h]

  v23 = a3;
  v22 = a4;
  v19 = 0;
  *(_OWORD *)Length = 0;
  *(_OWORD *)v25 = 0;
  result = RtlpValidateContextFlags(a4, &v19);
  if ( (int)result >= 0 )
  {
    v9 = v19;
    v10 = 4;
    if ( (v19 & 4) != 0 )
      return 3221225659LL;
    result = RtlpReadExtendedContextLayout(v8, a4, a5, v19, (__int64)Length);
    if ( (int)result >= 0 )
    {
      LODWORD(v20) = a4 & 0x10000;
      if ( (a4 & 0x10000) != 0 )
      {
        v11 = a5 + 716;
LABEL_14:
        if ( (v9 & 1) != 0 )
          ProbeForRead((volatile void *)(v11 + SLODWORD(Length[1])), HIDWORD(Length[1]), v10);
        if ( (v9 & 2) != 0 )
          ProbeForRead((volatile void *)(v11 + SLODWORD(v25[0])), HIDWORD(v25[0]), 0x40u);
        v12 = RtlpCopyExtendedContext(2, a3, 0, a4, v11, (__int64)Length);
        v21 = v12;
        if ( v12 < 0 )
          return (unsigned int)v12;
        v13 = *(int *)(a3 + 8);
        if ( (a4 & 0x10000) != 0 )
          goto LABEL_24;
        if ( (a4 & 0x100000) != 0 )
        {
          *(_DWORD *)(v13 + a3 + 48) = a4;
          goto LABEL_25;
        }
        if ( (a4 & 0x200000) != 0 || (a4 & 0x400000) != 0 )
LABEL_24:
          *(_DWORD *)(v13 + a3) = a4;
LABEL_25:
        if ( (v9 & 2) != 0 )
        {
          XStateConfiguration2 = (_QWORD *)RtlpGetXStateConfiguration2(a4);
          v20 = *XStateConfiguration2 | XStateConfiguration2[102];
          RtlpRemoveArchDisallowedXStateFeatures(a4, &v20, v20, XStateConfiguration2);
          v16 = v20;
          *(_QWORD *)(v15 + a3) &= v20 & 0xFFFFFFFFFFFFFFFCuLL;
          v17 = *(_QWORD *)(v15 + a3);
          if ( (*(_DWORD *)(v18 + 20) & 2) != 0 )
          {
            *(_QWORD *)(v15 + a3 + 8) &= v16 | 0x8000000000000000uLL;
            if ( (~*(_QWORD *)(v15 + a3 + 8) & v17) != 0 )
              return 3221225485LL;
          }
          else
          {
            *(_QWORD *)(v15 + a3 + 8) = 0;
          }
          *(_OWORD *)(v15 + a3 + 16) = 0;
          *(_OWORD *)(v15 + a3 + 32) = 0;
          *(_OWORD *)(v15 + a3 + 48) = 0;
        }
        return (unsigned int)v12;
      }
      if ( (a4 & 0x100000) != 0 )
      {
        v11 = a5 + 1232;
      }
      else
      {
        if ( (a4 & 0x200000) != 0 )
        {
          v10 = 8;
          v11 = a5 + 416;
          goto LABEL_14;
        }
        v10 = 0;
        v11 = 0;
        if ( (a4 & 0x400000) == 0 )
          goto LABEL_14;
        v11 = a5 + 912;
      }
      v10 = 16;
      goto LABEL_14;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400fdb7c  mov     [rsp+arg_0], rbx
0x1400fdb81  mov     [rsp+arg_8], rsi
0x1400fdb86  push    rdi
0x1400fdb87  push    r12
0x1400fdb89  push    r13
0x1400fdb8b  push    r14
0x1400fdb8d  push    r15
0x1400fdb8f  sub     rsp, 80h
0x1400fdb96  mov     rax, cs:__security_cookie
0x1400fdb9d  xor     rax, rsp
0x1400fdba0  mov     [rsp+0A8h+var_30], rax
0x1400fdba5  mov     edi, r9d
0x1400fdba8  mov     rbx, r8
0x1400fdbab  mov     [rsp+0A8h+var_58], rbx
0x1400fdbb0  mov     [rsp+0A8h+var_60], r9d
0x1400fdbb5  mov     r13, [rsp+0A8h+arg_20]
0x1400fdbbd  mov     [rsp+0A8h+var_78], 0
0x1400fdbc5  xorps   xmm0, xmm0
0x1400fdbc8  movups  xmmword ptr [rsp+0A8h+Length], xmm0
0x1400fdbcd  movups  xmmword ptr [rsp+0A8h+var_40], xmm0
0x1400fdbd2  lea     rdx, [rsp+0A8h+var_78]
0x1400fdbd7  mov     ecx, r9d
0x1400fdbda  call    RtlpValidateContextFlags
0x1400fdbdf  test    eax, eax
0x1400fdbe1  js      loc_1400FDDB1
0x1400fdbe7  mov     r15d, [rsp+0A8h+var_78]
0x1400fdbec  mov     esi, 4
0x1400fdbf1  test    sil, r15b
0x1400fdbf4  jz      short loc_1400FDC00
0x1400fdbf6  mov     eax, 0C00000BBh
0x1400fdbfb  jmp     loc_1400FDDB1
0x1400fdc00  lea     rax, [rsp+0A8h+Length]
0x1400fdc05  mov     [rsp+0A8h+var_88], rax
0x1400fdc0a  mov     r9d, r15d
0x1400fdc0d  mov     r8, r13
0x1400fdc10  mov     edx, edi
0x1400fdc12  call    RtlpReadExtendedContextLayout
0x1400fdc17  test    eax, eax
0x1400fdc19  js      loc_1400FDDB1
0x1400fdc1f  mov     r12d, edi
0x1400fdc22  and     r12d, 10000h
0x1400fdc29  mov     dword ptr [rsp+0A8h+var_70], r12d
0x1400fdc2e  jz      short loc_1400FDC39
0x1400fdc30  lea     r14, [r13+2CCh]
0x1400fdc37  jmp     short loc_1400FDC73
0x1400fdc39  bt      edi, 14h
0x1400fdc3d  jnb     short loc_1400FDC48
0x1400fdc3f  lea     r14, [r13+4D0h]
0x1400fdc46  jmp     short loc_1400FDC6E
0x1400fdc48  bt      edi, 15h
0x1400fdc4c  jnb     short loc_1400FDC5C
0x1400fdc4e  mov     esi, 8
0x1400fdc53  lea     r14, [r13+1A0h]
0x1400fdc5a  jmp     short loc_1400FDC73
0x1400fdc5c  xor     esi, esi
0x1400fdc5e  xor     r14d, r14d
0x1400fdc61  bt      edi, 16h
0x1400fdc65  jnb     short loc_1400FDC73
0x1400fdc67  lea     r14, [r13+390h]
0x1400fdc6e  mov     esi, 10h
0x1400fdc73  test    r15b, 1
0x1400fdc77  jz      short loc_1400FDC8D
0x1400fdc79  mov     edx, dword ptr [rsp+0A8h+Length+0Ch]; Length
0x1400fdc7d  movsxd  rcx, dword ptr [rsp+0A8h+Length+8]
0x1400fdc82  add     rcx, r14; Address
0x1400fdc85  mov     r8d, esi; Alignment
0x1400fdc88  call    ProbeForRead
0x1400fdc8d  test    r15b, 2
0x1400fdc91  jz      short loc_1400FDCAA
0x1400fdc93  mov     edx, dword ptr [rsp+0A8h+var_40+4]; Length
0x1400fdc97  movsxd  rcx, dword ptr [rsp+0A8h+var_40]
0x1400fdc9c  add     rcx, r14; Address
0x1400fdc9f  mov     r8d, 40h ; '@'; Alignment
0x1400fdca5  call    ProbeForRead
0x1400fdcaa  lea     rax, [rsp+0A8h+Length]
0x1400fdcaf  mov     [rsp+0A8h+var_80], rax
0x1400fdcb4  mov     [rsp+0A8h+var_88], r14
0x1400fdcb9  mov     r9d, edi
0x1400fdcbc  xor     r8d, r8d
0x1400fdcbf  mov     rdx, rbx
0x1400fdcc2  lea     ecx, [r8+2]
0x1400fdcc6  call    RtlpCopyExtendedContext
0x1400fdccb  mov     r11d, eax
0x1400fdcce  mov     [rsp+0A8h+var_68], eax
0x1400fdcd2  jmp     short loc_1400FDCEE
0x1400fdcd4  mov     r11d, eax
0x1400fdcd7  mov     [rsp+0A8h+var_68], eax
0x1400fdcdb  mov     r15d, [rsp+0A8h+var_78]
0x1400fdce0  mov     rbx, [rsp+0A8h+var_58]
0x1400fdce5  mov     edi, [rsp+0A8h+var_60]
0x1400fdce9  mov     r12d, dword ptr [rsp+0A8h+var_70]
0x1400fdcee  test    r11d, r11d
0x1400fdcf1  js      loc_1400FDDAE
0x1400fdcf7  movsxd  rax, dword ptr [rbx+8]
0x1400fdcfb  test    r12d, r12d
0x1400fdcfe  jnz     short loc_1400FDD18
0x1400fdd00  bt      edi, 14h
0x1400fdd04  jnb     short loc_1400FDD0C
0x1400fdd06  mov     [rax+rbx+30h], edi
0x1400fdd0a  jmp     short loc_1400FDD1B
0x1400fdd0c  bt      edi, 15h
0x1400fdd10  jb      short loc_1400FDD18
0x1400fdd12  bt      edi, 16h
0x1400fdd16  jnb     short loc_1400FDD1B
0x1400fdd18  mov     [rax+rbx], edi
0x1400fdd1b  test    r15b, 2
0x1400fdd1f  jz      loc_1400FDDAE
0x1400fdd25  mov     ecx, edi
0x1400fdd27  call    RtlpGetXStateConfiguration2
0x1400fdd2c  mov     r9, rax
0x1400fdd2f  movsxd  r10, dword ptr [rbx+10h]
0x1400fdd33  mov     r8, [rax+330h]
0x1400fdd3a  or      r8, [rax]
0x1400fdd3d  mov     [rsp+0A8h+var_70], r8
0x1400fdd42  lea     rdx, [rsp+0A8h+var_70]
0x1400fdd47  mov     ecx, edi
0x1400fdd49  call    RtlpRemoveArchDisallowedXStateFeatures
0x1400fdd4e  mov     rdx, [rsp+0A8h+var_70]
0x1400fdd53  mov     rcx, rdx
0x1400fdd56  and     rcx, 0FFFFFFFFFFFFFFFCh
0x1400fdd5a  and     [r10+rbx], rcx
0x1400fdd5e  mov     rcx, [r10+rbx]
0x1400fdd62  mov     eax, [r9+14h]
0x1400fdd66  test    al, 2
0x1400fdd68  jz      short loc_1400FDD90
0x1400fdd6a  mov     rax, 8000000000000000h
0x1400fdd74  or      rdx, rax
0x1400fdd77  and     [r10+rbx+8], rdx
0x1400fdd7c  mov     rax, [r10+rbx+8]
0x1400fdd81  not     rax
0x1400fdd84  test    rcx, rax
0x1400fdd87  jz      short loc_1400FDD99
0x1400fdd89  mov     eax, 0C000000Dh
0x1400fdd8e  jmp     short loc_1400FDDB1
0x1400fdd90  mov     qword ptr [r10+rbx+8], 0
0x1400fdd99  xorps   xmm0, xmm0
0x1400fdd9c  movups  xmmword ptr [r10+rbx+10h], xmm0
0x1400fdda2  movups  xmmword ptr [r10+rbx+20h], xmm0
0x1400fdda8  movups  xmmword ptr [r10+rbx+30h], xmm0
0x1400fddae  mov     eax, r11d
0x1400fddb1  mov     rcx, [rsp+0A8h+var_30]
0x1400fddb6  xor     rcx, rsp; StackCookie
0x1400fddb9  call    __security_check_cookie
0x1400fddbe  lea     r11, [rsp+0A8h+var_28]
0x1400fddc6  mov     rbx, [r11+30h]
0x1400fddca  mov     rsi, [r11+38h]
0x1400fddce  mov     rsp, r11
0x1400fddd1  pop     r15
0x1400fddd3  pop     r14
0x1400fddd5  pop     r13
0x1400fddd7  pop     r12
0x1400fddd9  pop     rdi
0x1400fddda  retn
```
