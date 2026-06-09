# CVaultCredential::VaultDeserializeCredElement(uchar * &,ulong &,IVaultSchema *,CVaultCredElement &)

- ea: `0x180006d30`
- end: `0x180007208`
- name: `?VaultDeserializeCredElement@CVaultCredential@@CAKAEAPEAEAEAKPEAUIVaultSchema@@AEAVCVaultCredElement@@@Z`
- size: `1240`
- prototype: `static unsigned int(unsigned __int8 **, unsigned int *, struct IVaultSchema *, struct CVaultCredElement *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006680`

## callees

- `0x180006d30`
- `0x180007890`
- `0x18002f340`
- `0x18003b7d8`
- `0x18003be38`
- `0x18004b43c`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006e21`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006f95`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006e21`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006f95`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180006f6c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180006f6c`

## pseudocode

```c
unsigned int __fastcall CVaultCredential::VaultDeserializeCredElement(
        unsigned __int8 **a1,
        unsigned int *a2,
        struct IVaultSchema *a3,
        struct CVaultCredElement *a4)
{
  struct IVaultSchema *v4; // rdi
  unsigned int *v5; // r8
  unsigned __int8 **v7; // rdx
  unsigned int v8; // r15d
  unsigned __int8 *v9; // r10
  int v10; // eax
  unsigned int *v11; // rbx
  unsigned int v12; // r12d
  unsigned int v13; // eax
  HLOCAL v14; // rax
  int v15; // eax
  unsigned int v16; // r15d
  unsigned int v17; // ebx
  struct IVaultSchemaElement *v18; // rax
  char *v20; // rbp
  SIZE_T v21; // rsi
  __int64 i; // rbx
  HLOCAL v23; // rax
  unsigned int v24; // [rsp+30h] [rbp-58h] BYREF
  _DWORD *v25; // [rsp+38h] [rbp-50h] BYREF
  unsigned int Source2; // [rsp+A8h] [rbp+20h] BYREF

  v4 = a3;
  v5 = a2;
  v24 = 0;
  v7 = a1;
  v8 = *v5;
  if ( *v5 < 4 )
    goto LABEL_17;
  v9 = *a1;
  *((_DWORD *)a4 + 6) = *(_DWORD *)*a1;
  if ( v8 - 4 < 4 )
    goto LABEL_17;
  *((_DWORD *)a4 + 3) = *((_DWORD *)v9 + 1);
  if ( v8 - 8 < 4 )
    goto LABEL_17;
  *((_DWORD *)a4 + 4) = *((_DWORD *)v9 + 2);
  if ( v8 - 12 < 4 )
    goto LABEL_17;
  v10 = *((_DWORD *)v9 + 3);
  v11 = (unsigned int *)(v9 + 16);
  v12 = v8 - 16;
  Source2 = v8 - 16;
  *((_DWORD *)a4 + 8) = v10;
  v25 = v9 + 16;
  if ( v10 == 7 )
  {
    LOWORD(Source2) = 0;
    if ( v12 < 4 )
    {
      v15 = 122;
    }
    else
    {
      v20 = (char *)(v9 + 20);
      v21 = *v11;
      v12 = v8 - 20;
      if ( (unsigned int)v21 < 2 )
      {
        *((_QWORD *)a4 + 5) = 0;
        v15 = 0;
      }
      else if ( (unsigned int)v21 > v8 - 20 )
      {
        v15 = 122;
      }
      else if ( (v21 & 1) != 0 )
      {
LABEL_14:
        v15 = 1358;
      }
      else
      {
        for ( i = 0; ; i = (unsigned int)(i + 2) )
        {
          if ( (unsigned int)i >= (unsigned int)v21 )
            goto LABEL_13;
          if ( RtlCompareMemory(&v20[i], &Source2, 2u) == 2 )
            break;
        }
        if ( (unsigned int)i != v21 - 2 )
        {
LABEL_13:
          v4 = a3;
          v5 = a2;
          v7 = a1;
          goto LABEL_14;
        }
        v23 = LocalAlloc(0x40u, v21);
        *((_QWORD *)a4 + 5) = v23;
        if ( v23 )
        {
          memcpy_0(v23, v20, v21);
          v7 = a1;
          v12 -= v21;
          v5 = a2;
          v15 = 0;
        }
        else
        {
          v7 = a1;
          v15 = 14;
          v5 = a2;
        }
        v4 = a3;
      }
    }
    goto LABEL_15;
  }
  if ( v10 == 8 )
  {
LABEL_7:
    *(_OWORD *)((char *)a4 + 40) = 0;
    if ( v12 < 4 )
    {
      v15 = 122;
    }
    else
    {
      v13 = *v11;
      *((_DWORD *)a4 + 10) = *v11;
      v12 = v8 - 20;
      if ( v13 > v8 - 20 )
      {
        v4 = a3;
        v15 = 122;
      }
      else if ( v13 )
      {
        v14 = LocalAlloc(0x40u, v13);
        *((_QWORD *)a4 + 6) = v14;
        if ( v14 )
        {
          memcpy_0(v14, v11 + 1, *((unsigned int *)a4 + 10));
          v12 -= *((_DWORD *)a4 + 10);
          v7 = a1;
          v15 = 0;
        }
        else
        {
          v7 = a1;
          v15 = 14;
        }
        v5 = a2;
        v4 = a3;
      }
      else
      {
        v4 = a3;
        v15 = 0;
      }
    }
LABEL_15:
    if ( !v15 )
    {
      v16 = v8 - v12;
      *((_BYTE *)a4 + 56) = 1;
      *v7 += v16;
      *v5 -= v16;
    }
    goto LABEL_17;
  }
  switch ( v10 )
  {
    case 0:
      v15 = VaultDeserialize<unsigned char>(&v25, &Source2, (char *)a4 + 40);
      v7 = a1;
      v12 = Source2;
      v5 = a2;
      goto LABEL_15;
    case 1:
    case 2:
      if ( v12 >= 2 )
      {
        v12 = v8 - 18;
        *((_WORD *)a4 + 20) = *(_WORD *)v11;
        v15 = 0;
      }
      else
      {
        v15 = 122;
      }
      goto LABEL_15;
    case 3:
    case 4:
      if ( v12 >= 4 )
      {
        v12 = v8 - 20;
        *((_DWORD *)a4 + 10) = *v11;
        v15 = 0;
      }
      else
      {
        v15 = 122;
      }
      goto LABEL_15;
    case 5:
      if ( v12 >= 8 )
      {
        v12 = v8 - 24;
        *((_QWORD *)a4 + 5) = *(_QWORD *)v11;
        v15 = 0;
      }
      else
      {
        v15 = 122;
      }
      goto LABEL_15;
    case 6:
      if ( v12 < 0x10 )
      {
        v15 = 122;
      }
      else
      {
        v12 = v8 - 32;
        v15 = 0;
        *(_OWORD *)((char *)a4 + 40) = *(_OWORD *)v11;
      }
      goto LABEL_15;
    case 10:
      goto LABEL_7;
    default:
      break;
  }
LABEL_17:
  v17 = (*(__int64 (__fastcall **)(struct CVaultCredElement *, unsigned int *))(*(_QWORD *)a4 + 8LL))(a4, &v24);
  if ( v17 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_49114d8a939f3a3d6447d5db247a3e77_Traceguids, v17);
    return v17;
  }
  else
  {
    v18 = (struct IVaultSchemaElement *)(*(__int64 (__fastcall **)(struct IVaultSchema *, _QWORD))(*(_QWORD *)v4 + 152LL))(
                                          v4,
                                          v24);
    if ( v18 )
    {
      return CVaultCredElement::ValidateCredentialElement(v18, a4);
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_49114d8a939f3a3d6447d5db247a3e77_Traceguids, v24, 87);
      return 87;
    }
  }
}

```

## disassembly

```asm
0x180006d30  mov     [rsp+arg_10], r8
0x180006d35  mov     [rsp+arg_8], rdx
0x180006d3a  mov     [rsp+arg_0], rcx
0x180006d3f  push    rbx
0x180006d40  push    rdi
0x180006d41  push    r14
0x180006d43  sub     rsp, 70h
0x180006d47  mov     rdi, r8
0x180006d4a  mov     [rsp+88h+var_40], r15
0x180006d4f  mov     r8, rdx
0x180006d52  mov     [rsp+88h+var_58], 0
0x180006d5a  mov     r14, r9
0x180006d5d  mov     rdx, rcx
0x180006d60  mov     r15d, [r8]
0x180006d63  cmp     r15d, 4
0x180006d67  jb      loc_180006EAD
0x180006d6d  mov     r10, [rcx]
0x180006d70  lea     r11d, [r15-4]
0x180006d74  mov     eax, [r10]
0x180006d77  mov     [r9+18h], eax
0x180006d7b  cmp     r11d, 4
0x180006d7f  jb      loc_180006EAD
0x180006d85  mov     eax, [r10+4]
0x180006d89  add     r11d, 0FFFFFFFCh
0x180006d8d  mov     [r9+0Ch], eax
0x180006d91  cmp     r11d, 4
0x180006d95  jb      loc_180006EAD
0x180006d9b  mov     eax, [r10+8]
0x180006d9f  mov     [rsp+88h+var_38], r13
0x180006da4  lea     r13d, [r11-4]
0x180006da8  mov     [r9+10h], eax
0x180006dac  cmp     r13d, 4
0x180006db0  jb      loc_180006EA8
0x180006db6  movsxd  rax, dword ptr [r10+0Ch]
0x180006dba  lea     rbx, [r10+10h]
0x180006dbe  mov     [rsp+88h+var_30], r12
0x180006dc3  lea     r12d, [r13-4]
0x180006dc7  mov     [rsp+88h+Source2], r12d
0x180006dcf  mov     [r9+20h], eax
0x180006dd3  mov     [rsp+88h+var_50], rbx
0x180006dd8  cmp     eax, 7
0x180006ddb  jz      loc_180006F03
0x180006de1  cmp     eax, 8
0x180006de4  jnz     loc_180007009
0x180006dea  xorps   xmm0, xmm0; jumptable 0000000180007024 case 10
0x180006ded  movups  xmmword ptr [r14+28h], xmm0
0x180006df2  cmp     r12d, 4
0x180006df6  jb      loc_180007117
0x180006dfc  mov     eax, [rbx]
0x180006dfe  lea     edi, [r12-4]
0x180006e03  mov     [r14+28h], eax
0x180006e07  mov     r12d, edi
0x180006e0a  cmp     eax, edi
0x180006e0c  ja      loc_180007121
0x180006e12  test    eax, eax
0x180006e14  jz      loc_180007065
0x180006e1a  mov     edx, eax; uBytes
0x180006e1c  mov     ecx, 40h ; '@'; uFlags
0x180006e21  call    cs:__imp_LocalAlloc
0x180006e27  mov     [r14+30h], rax
0x180006e2b  test    rax, rax
0x180006e2e  jz      loc_180007133
0x180006e34  mov     r8d, [r14+28h]; Size
0x180006e38  lea     rdx, [rbx+4]; Src
0x180006e3c  mov     rcx, rax; void *
0x180006e3f  call    memcpy_0
0x180006e44  sub     r12d, [r14+28h]
0x180006e48  mov     rdx, [rsp+88h+arg_0]
0x180006e50  xor     eax, eax
0x180006e52  mov     r8, [rsp+88h+arg_8]
0x180006e5a  mov     rdi, [rsp+88h+arg_10]
0x180006e62  jmp     short loc_180006E8B
0x180006e64  mov     rdi, [rsp+88h+arg_10]
0x180006e6c  mov     r8, [rsp+88h+arg_8]
0x180006e74  mov     rdx, [rsp+88h+arg_0]
0x180006e7c  mov     eax, 54Eh
0x180006e81  mov     rsi, [rsp+88h+var_28]
0x180006e86  mov     rbp, [rsp+88h+var_20]
0x180006e8b  test    eax, eax
0x180006e8d  jnz     short def_180007024; jumptable 0000000180007024 default case, cases 7-9,11
0x180006e8f  sub     r15d, r12d
0x180006e92  mov     byte ptr [r14+38h], 1
0x180006e97  mov     eax, r15d
0x180006e9a  mov     r13d, r12d
0x180006e9d  add     [rdx], rax
0x180006ea0  sub     [r8], eax
0x180006ea3  mov     r12, [rsp+88h+var_30]; jumptable 0000000180007024 default case, cases 7-9,11
0x180006ea8  mov     r13, [rsp+88h+var_38]
0x180006ead  mov     rax, [r14]
0x180006eb0  lea     rdx, [rsp+88h+var_58]
0x180006eb5  mov     rcx, r14
0x180006eb8  mov     rax, [rax+8]
0x180006ebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ec1  mov     r15, [rsp+88h+var_40]
0x180006ec6  mov     ebx, eax
0x180006ec8  test    eax, eax
0x180006eca  jnz     loc_180006FD8
0x180006ed0  mov     rax, [rdi]
0x180006ed3  mov     rcx, rdi
0x180006ed6  mov     edx, [rsp+88h+var_58]
0x180006eda  mov     rax, [rax+98h]
0x180006ee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ee6  test    rax, rax
0x180006ee9  jz      loc_180007190
0x180006eef  mov     rdx, r14; struct IVaultCredentialElement *
0x180006ef2  mov     rcx, rax; struct IVaultSchemaElement *
0x180006ef5  call    ?ValidateCredentialElement@CVaultCredElement@@SAKPEAUIVaultSchemaElement@@PEAUIVaultCredentialElement@@@Z; CVaultCredElement::ValidateCredentialElement(IVaultSchemaElement *,IVaultCredentialElement *)
0x180006efa  add     rsp, 70h
0x180006efe  pop     r14
0x180006f00  pop     rdi
0x180006f01  pop     rbx
0x180006f02  retn
0x180006f03  xor     eax, eax
0x180006f05  mov     word ptr [rsp+88h+Source2], ax
0x180006f0d  cmp     r12d, 4
0x180006f11  jb      loc_180007155
0x180006f17  mov     [rsp+88h+var_20], rbp
0x180006f1c  lea     eax, [r12-4]
0x180006f21  mov     [rsp+88h+var_28], rsi
0x180006f26  lea     rbp, [rbx+4]
0x180006f2a  mov     esi, [rbx]
0x180006f2c  mov     r12d, eax
0x180006f2f  cmp     esi, 2
0x180006f32  jb      loc_180006FFA
0x180006f38  cmp     esi, eax
0x180006f3a  ja      loc_18000715F
0x180006f40  test    sil, 1
0x180006f44  jnz     loc_180006E7C
0x180006f4a  xor     ebx, ebx
0x180006f4c  nop     dword ptr [rax+00h]
0x180006f50  cmp     ebx, esi
0x180006f52  jnb     loc_180006E64
0x180006f58  lea     rcx, [rbx+rbp]; Source1
0x180006f5c  mov     edi, ebx
0x180006f5e  mov     r8d, 2; Length
0x180006f64  lea     rdx, [rsp+88h+Source2]; Source2
0x180006f6c  call    cs:__imp_RtlCompareMemory
0x180006f72  cmp     rax, 2
0x180006f76  jz      short loc_180006F7D
0x180006f78  add     ebx, 2
0x180006f7b  jmp     short loc_180006F50
0x180006f7d  lea     rax, [rsi-2]
0x180006f81  mov     rbx, rsi
0x180006f84  cmp     rdi, rax
0x180006f87  jnz     loc_180006E64
0x180006f8d  mov     rdx, rbx; uBytes
0x180006f90  mov     ecx, 40h ; '@'; uFlags
0x180006f95  call    cs:__imp_LocalAlloc
0x180006f9b  mov     [r14+28h], rax
0x180006f9f  test    rax, rax
0x180006fa2  jz      loc_180007043
0x180006fa8  mov     r8, rbx; Size
0x180006fab  mov     rdx, rbp; Src
0x180006fae  mov     rcx, rax; void *
0x180006fb1  call    memcpy_0
0x180006fb6  mov     rdx, [rsp+88h+arg_0]
0x180006fbe  sub     r12d, esi
0x180006fc1  mov     r8, [rsp+88h+arg_8]
0x180006fc9  xor     eax, eax
0x180006fcb  mov     rdi, [rsp+88h+arg_10]
0x180006fd3  jmp     loc_180006E81
0x180006fd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180006fdf  lea     rax, WPP_GLOBAL_Control
0x180006fe6  cmp     rcx, rax
0x180006fe9  jnz     loc_180007169
0x180006fef  mov     eax, ebx
0x180006ff1  add     rsp, 70h
0x180006ff5  pop     r14
0x180006ff7  pop     rdi
0x180006ff8  pop     rbx
0x180006ff9  retn
0x180006ffa  mov     qword ptr [r9+28h], 0
0x180007002  xor     eax, eax
0x180007004  jmp     loc_180006E81
0x180007009  cmp     eax, 0Bh; switch 12 cases
0x18000700c  ja      def_180007024; jumptable 0000000180007024 default case, cases 7-9,11
0x180007012  lea     r9, __ImageBase
0x180007019  mov     ecx, ds:(jpt_180007024 - 180000000h)[r9+rax*4]
0x180007021  add     rcx, r9
0x180007024  jmp     rcx; switch jump
0x180007026  cmp     r12d, 10h; jumptable 0000000180007024 case 6
0x18000702a  jb      loc_18000710D
0x180007030  movups  xmm0, xmmword ptr [rbx]
0x180007033  add     r12d, 0FFFFFFF0h
0x180007037  xor     eax, eax
0x180007039  movups  xmmword ptr [r14+28h], xmm0
0x18000703e  jmp     loc_180006E8B
0x180007043  mov     rdx, [rsp+88h+arg_0]
0x18000704b  mov     eax, 0Eh
0x180007050  mov     r8, [rsp+88h+arg_8]
0x180007058  mov     rdi, [rsp+88h+arg_10]
0x180007060  jmp     loc_180006E81
0x180007065  mov     rdi, [rsp+88h+arg_10]
0x18000706d  xor     eax, eax
0x18000706f  jmp     loc_180006E8B
0x180007074  cmp     r12d, 2; jumptable 0000000180007024 cases 1,2
0x180007078  jnb     short loc_180007084
0x18000707a  mov     eax, 7Ah ; 'z'
0x18000707f  jmp     loc_180006E8B
0x180007084  movzx   eax, word ptr [rbx]
0x180007087  add     r12d, 0FFFFFFFEh
0x18000708b  mov     [r14+28h], ax
0x180007090  xor     eax, eax
0x180007092  jmp     loc_180006E8B
0x180007097  cmp     r12d, 4; jumptable 0000000180007024 cases 3,4
0x18000709b  jnb     short loc_1800070A7
0x18000709d  mov     eax, 7Ah ; 'z'
0x1800070a2  jmp     loc_180006E8B
0x1800070a7  mov     eax, [rbx]
0x1800070a9  add     r12d, 0FFFFFFFCh
0x1800070ad  mov     [r14+28h], eax
0x1800070b1  xor     eax, eax
0x1800070b3  jmp     loc_180006E8B
0x1800070b8  cmp     r12d, 8; jumptable 0000000180007024 case 5
0x1800070bc  jnb     short loc_1800070C8
0x1800070be  mov     eax, 7Ah ; 'z'
0x1800070c3  jmp     loc_180006E8B
0x1800070c8  mov     rax, [rbx]
0x1800070cb  add     r12d, 0FFFFFFF8h
0x1800070cf  mov     [r14+28h], rax
0x1800070d3  xor     eax, eax
0x1800070d5  jmp     loc_180006E8B
0x1800070da  lea     r8, [r14+28h]; jumptable 0000000180007024 case 0
0x1800070de  lea     rdx, [rsp+88h+Source2]
0x1800070e6  lea     rcx, [rsp+88h+var_50]
0x1800070eb  call    ??$VaultDeserialize@E@@YAKAEAPEAEAEAKAEAE@Z; VaultDeserialize<uchar>(uchar * &,ulong &,uchar &)
0x1800070f0  mov     rdx, [rsp+88h+arg_0]
0x1800070f8  mov     r12d, [rsp+88h+Source2]
0x180007100  mov     r8, [rsp+88h+arg_8]
0x180007108  jmp     loc_180006E8B
0x18000710d  mov     eax, 7Ah ; 'z'
0x180007112  jmp     loc_180006E8B
0x180007117  mov     eax, 7Ah ; 'z'
0x18000711c  jmp     loc_180006E8B
0x180007121  mov     rdi, [rsp+88h+arg_10]
0x180007129  mov     eax, 7Ah ; 'z'
0x18000712e  jmp     loc_180006E8B
0x180007133  mov     rdx, [rsp+88h+arg_0]
0x18000713b  mov     eax, 0Eh
0x180007140  mov     r8, [rsp+88h+arg_8]
0x180007148  mov     rdi, [rsp+88h+arg_10]
0x180007150  jmp     loc_180006E8B
0x180007155  mov     eax, 7Ah ; 'z'
0x18000715a  jmp     loc_180006E8B
0x18000715f  mov     eax, 7Ah ; 'z'
0x180007164  jmp     loc_180006E81
0x180007169  test    byte ptr [rcx+1Ch], 2
0x18000716d  jz      loc_180006FEF
0x180007173  mov     rcx, [rcx+10h]
0x180007177  lea     r8, WPP_49114d8a939f3a3d6447d5db247a3e77_Traceguids
0x18000717e  mov     edx, 24h ; '$'
0x180007183  mov     r9d, ebx
0x180007186  call    WPP_SF_d
0x18000718b  jmp     loc_180006FEF
0x180007190  mov     rcx, cs:WPP_GLOBAL_Control
0x180007197  lea     rax, WPP_GLOBAL_Control
0x18000719e  cmp     rcx, rax
0x1800071a1  jz      short loc_1800071CB
0x1800071a3  test    byte ptr [rcx+1Ch], 2
0x1800071a7  jz      short loc_1800071CB
0x1800071a9  mov     r9d, [rsp+88h+var_58]
0x1800071ae  lea     r8, WPP_49114d8a939f3a3d6447d5db247a3e77_Traceguids
0x1800071b5  mov     rcx, [rcx+10h]
0x1800071b9  mov     edx, 25h ; '%'
0x1800071be  mov     [rsp+88h+var_68], 57h ; 'W'
0x1800071c6  call    WPP_SF_dd
0x1800071cb  mov     eax, 57h ; 'W'
0x1800071d0  jmp     loc_180006EFA
```
