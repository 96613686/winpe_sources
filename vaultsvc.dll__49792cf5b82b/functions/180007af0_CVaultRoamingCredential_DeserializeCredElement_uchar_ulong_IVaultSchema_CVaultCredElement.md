# CVaultRoamingCredential::DeserializeCredElement(uchar * &,ulong &,IVaultSchema *,CVaultCredElement * *)

- ea: `0x180007af0`
- end: `0x180008040`
- name: `?DeserializeCredElement@CVaultRoamingCredential@@CAKAEAPEAEAEAKPEAUIVaultSchema@@PEAPEAVCVaultCredElement@@@Z`
- size: `1360`
- prototype: `unsigned int __fastcall(unsigned __int8 **, unsigned int *, struct IVaultSchema *, struct CVaultCredElement **)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180009a20`
- `0x18002a9e0`

## callees

- `0x180003140`
- `0x180007890`
- `0x180007af0`
- `0x180008bb4`
- `0x18002f340`
- `0x18003b7d8`
- `0x18003be38`
- `0x18004b43c`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007bfc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007d74`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007bfc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007d74`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180007d21`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180007d21`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVaultRoamingCredential::DeserializeCredElement(
        unsigned __int8 **a1,
        unsigned int *a2,
        struct IVaultSchema *a3,
        struct CVaultCredElement **a4)
{
  struct IVaultSchema *v4; // rsi
  unsigned int *v5; // rdi
  unsigned __int8 **v6; // rbp
  unsigned int v7; // ebx
  unsigned int v8; // r15d
  struct IVaultCredentialElement *v9; // r14
  unsigned __int8 *v10; // rcx
  int v11; // eax
  _WORD *v12; // rbx
  unsigned int v13; // r13d
  unsigned int v14; // eax
  HLOCAL v15; // rax
  unsigned int v16; // ebx
  unsigned int v17; // r15d
  struct IVaultSchemaElement *v18; // rax
  SIZE_T v20; // rsi
  char *v21; // rbp
  __int64 i; // rbx
  HLOCAL v23; // rax
  unsigned int Source2; // [rsp+30h] [rbp-78h] BYREF
  unsigned int v25; // [rsp+34h] [rbp-74h] BYREF
  _DWORD *v26; // [rsp+38h] [rbp-70h] BYREF
  void (__fastcall *v27)(HLOCAL); // [rsp+40h] [rbp-68h] BYREF
  struct IVaultCredentialElement *v28; // [rsp+48h] [rbp-60h] BYREF
  int v29; // [rsp+50h] [rbp-58h]

  v4 = a3;
  v5 = a2;
  v6 = a1;
  v25 = 0;
  v28 = 0;
  v29 = 0;
  v27 = CVaultCredElement::FreeCredElement;
  v7 = CVaultCredElement::CreateCredElement(&v28);
  if ( v7 )
  {
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v27);
    return v7;
  }
  v8 = *v5;
  if ( *v5 < 4
    || (v9 = v28, v10 = *v6, *((_DWORD *)v28 + 6) = *(_DWORD *)*v6, v8 - 4 < 4)
    || (*((_DWORD *)v9 + 3) = *((_DWORD *)v10 + 1), v8 - 8 < 4)
    || (*((_DWORD *)v9 + 4) = *((_DWORD *)v10 + 2), v8 - 12 < 4) )
  {
    v16 = 122;
    goto LABEL_28;
  }
  v11 = *((_DWORD *)v10 + 3);
  *((_DWORD *)v9 + 8) = v11;
  v12 = v10 + 16;
  v26 = v10 + 16;
  v13 = v8 - 16;
  Source2 = v8 - 16;
  if ( v11 == 7 )
  {
    LOWORD(Source2) = 0;
    if ( v13 < 4 )
    {
      v16 = 122;
    }
    else
    {
      v20 = *(unsigned int *)v12;
      v21 = (char *)(v10 + 20);
      v13 = v8 - 20;
      if ( (unsigned int)v20 < 2 )
      {
        *((_QWORD *)v9 + 5) = 0;
        v16 = 0;
        v4 = a3;
        v6 = a1;
      }
      else if ( (unsigned int)v20 > v8 - 20 )
      {
        v16 = 122;
        v4 = a3;
        v6 = a1;
      }
      else
      {
        if ( (v20 & 1) == 0 )
        {
          for ( i = 0; ; i = (unsigned int)(i + 2) )
          {
            if ( (unsigned int)i >= (unsigned int)v20 )
              goto LABEL_34;
            if ( RtlCompareMemory(&v21[i], &Source2, 2u) == 2 )
              break;
          }
          if ( (unsigned int)i == v20 - 2 )
          {
            v23 = LocalAlloc(0x40u, v20);
            *((_QWORD *)v9 + 5) = v23;
            if ( !v23 )
            {
              v16 = 14;
              v6 = a1;
              v4 = a3;
LABEL_13:
              v5 = a2;
              goto LABEL_14;
            }
            memcpy_0(v23, v21, v20);
            v13 -= v20;
            v16 = 0;
          }
          else
          {
LABEL_34:
            v16 = 1358;
          }
          v6 = a1;
          v4 = a3;
          goto LABEL_13;
        }
        v16 = 1358;
        v4 = a3;
        v6 = a1;
      }
    }
  }
  else
  {
    if ( v11 != 8 )
    {
      switch ( v11 )
      {
        case 0:
          v16 = VaultDeserialize<unsigned char>(&v26, &Source2, (char *)v9 + 40);
          v13 = Source2;
          goto LABEL_14;
        case 1:
        case 2:
          if ( v13 >= 2 )
          {
            *((_WORD *)v9 + 20) = *v12;
            v13 = v8 - 18;
            v16 = 0;
          }
          else
          {
            v16 = 122;
          }
          goto LABEL_14;
        case 3:
        case 4:
          if ( v13 >= 4 )
          {
            *((_DWORD *)v9 + 10) = *(_DWORD *)v12;
            v13 = v8 - 20;
            v16 = 0;
          }
          else
          {
            v16 = 122;
          }
          goto LABEL_14;
        case 5:
          if ( v13 >= 8 )
          {
            *((_QWORD *)v9 + 5) = *(_QWORD *)v12;
            v13 = v8 - 24;
            v16 = 0;
          }
          else
          {
            v16 = 122;
          }
          goto LABEL_14;
        case 6:
          if ( v13 < 0x10 )
          {
            v16 = 122;
          }
          else
          {
            *(_OWORD *)((char *)v9 + 40) = *(_OWORD *)v12;
            v13 = v8 - 32;
            v16 = 0;
          }
          goto LABEL_14;
        case 10:
          break;
        default:
          v16 = 87;
          goto LABEL_28;
      }
    }
    *(_OWORD *)((char *)v9 + 40) = 0;
    if ( v13 >= 4 )
    {
      v14 = *(_DWORD *)v12;
      *((_DWORD *)v9 + 10) = *(_DWORD *)v12;
      v13 = v8 - 20;
      if ( v14 > v8 - 20 )
      {
        v16 = 122;
      }
      else if ( v14 )
      {
        v15 = LocalAlloc(0x40u, v14);
        *((_QWORD *)v9 + 6) = v15;
        if ( v15 )
        {
          memcpy_0(v15, v12 + 2, *((unsigned int *)v9 + 10));
          v13 -= *((_DWORD *)v9 + 10);
          v16 = 0;
        }
        else
        {
          v16 = 14;
        }
      }
      else
      {
        v16 = 0;
      }
      goto LABEL_13;
    }
    v16 = 122;
  }
LABEL_14:
  if ( v16 )
  {
LABEL_28:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_b8c320665cdb3030ba0f4297ba888b62_Traceguids, v16);
    goto LABEL_42;
  }
  *((_BYTE *)v9 + 56) = 1;
  v17 = v8 - v13;
  *v6 += v17;
  *v5 -= v17;
  v16 = (*(__int64 (__fastcall **)(struct IVaultCredentialElement *, unsigned int *))(*(_QWORD *)v9 + 8LL))(v9, &v25);
  if ( v16 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_b8c320665cdb3030ba0f4297ba888b62_Traceguids, v16);
LABEL_42:
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v27);
    return v16;
  }
  v18 = (struct IVaultSchemaElement *)(*(__int64 (__fastcall **)(struct IVaultSchema *, _QWORD))(*(_QWORD *)v4 + 152LL))(
                                        v4,
                                        v25);
  if ( v18 )
  {
    v16 = CVaultCredElement::ValidateCredentialElement(v18, v9);
    if ( !v16 )
    {
      v28 = 0;
      *a4 = v9;
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v27);
      return 0;
    }
    goto LABEL_42;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_b8c320665cdb3030ba0f4297ba888b62_Traceguids, v25, 87);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v27);
  return 87;
}

```

## disassembly

```asm
0x180007af0  mov     r11, rsp
0x180007af3  mov     [r11+20h], r9
0x180007af7  mov     [r11+18h], r8
0x180007afb  mov     [r11+10h], rdx
0x180007aff  mov     [r11+8], rcx
0x180007b03  push    rbx
0x180007b04  push    rbp
0x180007b05  push    rsi
0x180007b06  push    rdi
0x180007b07  push    r12
0x180007b09  push    r13
0x180007b0b  push    r14
0x180007b0d  push    r15
0x180007b0f  sub     rsp, 68h
0x180007b13  mov     rsi, r8
0x180007b16  mov     rdi, rdx
0x180007b19  mov     rbp, rcx
0x180007b1c  xor     eax, eax
0x180007b1e  mov     [rsp+0A8h+var_74], eax
0x180007b22  mov     [r11-60h], rax
0x180007b26  mov     [rsp+0A8h+var_58], eax
0x180007b2a  lea     rax, ?FreeCredElement@CVaultCredElement@@SAXPEAV1@@Z; CVaultCredElement::FreeCredElement(CVaultCredElement *)
0x180007b31  mov     [r11-68h], rax
0x180007b35  lea     rcx, [r11-60h]; struct CVaultCredElement **
0x180007b39  call    ?CreateCredElement@CVaultCredElement@@SAKPEAPEAV1@@Z; CVaultCredElement::CreateCredElement(CVaultCredElement * *)
0x180007b3e  mov     ebx, eax
0x180007b40  test    eax, eax
0x180007b42  jnz     loc_180007E84
0x180007b48  mov     r15d, [rdi]
0x180007b4b  cmp     r15d, 4
0x180007b4f  jb      loc_180007D32
0x180007b55  mov     r14, [rsp+0A8h+var_60]
0x180007b5a  mov     rcx, [rbp+0]
0x180007b5e  mov     eax, [rcx]
0x180007b60  mov     [r14+18h], eax
0x180007b64  lea     edx, [r15-4]
0x180007b68  cmp     edx, 4
0x180007b6b  jb      loc_180007D32
0x180007b71  mov     eax, [rcx+4]
0x180007b74  mov     [r14+0Ch], eax
0x180007b78  add     edx, 0FFFFFFFCh
0x180007b7b  cmp     edx, 4
0x180007b7e  jb      loc_180007D32
0x180007b84  mov     eax, [rcx+8]
0x180007b87  mov     [r14+10h], eax
0x180007b8b  lea     r12d, [rdx-4]
0x180007b8f  cmp     r12d, 4
0x180007b93  jb      loc_180007D32
0x180007b99  movsxd  rax, dword ptr [rcx+0Ch]
0x180007b9d  mov     [r14+20h], eax
0x180007ba1  lea     rbx, [rcx+10h]
0x180007ba5  mov     [rsp+0A8h+var_70], rbx
0x180007baa  lea     r13d, [r12-4]
0x180007baf  mov     [rsp+0A8h+Source2], r13d
0x180007bb4  cmp     eax, 7
0x180007bb7  jz      loc_180007CCD
0x180007bbd  cmp     eax, 8
0x180007bc0  jnz     loc_180007DD5
0x180007bc6  xorps   xmm0, xmm0; jumptable 0000000180007DEF case 10
0x180007bc9  movups  xmmword ptr [r14+28h], xmm0
0x180007bce  cmp     r13d, 4
0x180007bd2  jb      loc_180007F2F
0x180007bd8  mov     eax, [rbx]
0x180007bda  mov     [r14+28h], eax
0x180007bde  lea     edi, [r13-4]
0x180007be2  mov     r13d, edi
0x180007be5  cmp     eax, edi
0x180007be7  ja      loc_180007F39
0x180007bed  test    eax, eax
0x180007bef  jz      loc_180007E63
0x180007bf5  mov     edx, eax; uBytes
0x180007bf7  mov     ecx, 40h ; '@'; uFlags
0x180007bfc  call    cs:__imp_LocalAlloc
0x180007c02  mov     [r14+30h], rax
0x180007c06  test    rax, rax
0x180007c09  jz      loc_180007F43
0x180007c0f  mov     r8d, [r14+28h]; Size
0x180007c13  lea     rdx, [rbx+4]; Src
0x180007c17  mov     rcx, rax; void *
0x180007c1a  call    memcpy_0
0x180007c1f  sub     r13d, [r14+28h]
0x180007c23  xor     ebx, ebx
0x180007c25  mov     rdi, [rsp+0A8h+arg_8]
0x180007c2d  test    ebx, ebx
0x180007c2f  jnz     loc_180007D37
0x180007c35  mov     r12d, r13d
0x180007c38  mov     byte ptr [r14+38h], 1
0x180007c3d  sub     r15d, r13d
0x180007c40  mov     eax, r15d
0x180007c43  add     [rbp+0], rax
0x180007c47  sub     [rdi], eax
0x180007c49  mov     rax, [r14]
0x180007c4c  lea     rdx, [rsp+0A8h+var_74]
0x180007c51  mov     rcx, r14
0x180007c54  mov     rax, [rax+8]
0x180007c58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c5d  mov     ebx, eax
0x180007c5f  test    eax, eax
0x180007c61  jnz     loc_180007E3A
0x180007c67  mov     rax, [rsi]
0x180007c6a  mov     edx, [rsp+0A8h+var_74]
0x180007c6e  mov     rcx, rsi
0x180007c71  mov     rax, [rax+98h]
0x180007c78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c7d  test    rax, rax
0x180007c80  jz      loc_180007FBF
0x180007c86  mov     rdx, r14; struct IVaultCredentialElement *
0x180007c89  mov     rcx, rax; struct IVaultSchemaElement *
0x180007c8c  call    ?ValidateCredentialElement@CVaultCredElement@@SAKPEAUIVaultSchemaElement@@PEAUIVaultCredentialElement@@@Z; CVaultCredElement::ValidateCredentialElement(IVaultSchemaElement *,IVaultCredentialElement *)
0x180007c91  mov     ebx, eax
0x180007c93  test    eax, eax
0x180007c95  jnz     loc_180007E0E
0x180007c9b  mov     [rsp+0A8h+var_60], 0
0x180007ca4  mov     rax, [rsp+0A8h+arg_18]
0x180007cac  mov     [rax], r14
0x180007caf  lea     rcx, [rsp+0A8h+var_68]
0x180007cb4  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180007cb9  nop
0x180007cba  xor     eax, eax
0x180007cbc  add     rsp, 68h
0x180007cc0  pop     r15
0x180007cc2  pop     r14
0x180007cc4  pop     r13
0x180007cc6  pop     r12
0x180007cc8  pop     rdi
0x180007cc9  pop     rsi
0x180007cca  pop     rbp
0x180007ccb  pop     rbx
0x180007ccc  retn
0x180007ccd  xor     eax, eax
0x180007ccf  mov     word ptr [rsp+0A8h+Source2], ax
0x180007cd4  cmp     r13d, 4
0x180007cd8  jb      loc_180007F4D
0x180007cde  mov     esi, [rbx]
0x180007ce0  lea     rbp, [rbx+4]
0x180007ce4  lea     eax, [r13-4]
0x180007ce8  mov     r13d, eax
0x180007ceb  cmp     esi, 2
0x180007cee  jb      loc_180007DB6
0x180007cf4  cmp     esi, eax
0x180007cf6  ja      loc_180007F57
0x180007cfc  test    sil, 1
0x180007d00  jnz     loc_180007E6A
0x180007d06  xor     ebx, ebx
0x180007d08  cmp     ebx, esi
0x180007d0a  jnb     loc_180007DAF
0x180007d10  mov     edi, ebx
0x180007d12  lea     rcx, [rbx+rbp]; Source1
0x180007d16  mov     r8d, 2; Length
0x180007d1c  lea     rdx, [rsp+0A8h+Source2]; Source2
0x180007d21  call    cs:__imp_RtlCompareMemory
0x180007d27  cmp     rax, 2
0x180007d2b  jz      short loc_180007D60
0x180007d2d  add     ebx, 2
0x180007d30  jmp     short loc_180007D08
0x180007d32  mov     ebx, 7Ah ; 'z'
0x180007d37  lea     rax, WPP_GLOBAL_Control
0x180007d3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d45  cmp     rcx, rax
0x180007d48  jnz     loc_180007F71
0x180007d4e  lea     rcx, [rsp+0A8h+var_68]
0x180007d53  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180007d58  nop
0x180007d59  mov     eax, ebx
0x180007d5b  jmp     loc_180007CBC
0x180007d60  mov     rbx, rsi
0x180007d63  lea     rax, [rsi-2]
0x180007d67  cmp     rdi, rax
0x180007d6a  jnz     short loc_180007DAF
0x180007d6c  mov     rdx, rbx; uBytes
0x180007d6f  mov     ecx, 40h ; '@'; uFlags
0x180007d74  call    cs:__imp_LocalAlloc
0x180007d7a  mov     [r14+28h], rax
0x180007d7e  test    rax, rax
0x180007d81  jz      loc_180007E20
0x180007d87  mov     r8, rbx; Size
0x180007d8a  mov     rdx, rbp; Src
0x180007d8d  mov     rcx, rax; void *
0x180007d90  call    memcpy_0
0x180007d95  sub     r13d, esi
0x180007d98  xor     ebx, ebx
0x180007d9a  mov     rbp, [rsp+0A8h+arg_0]
0x180007da2  mov     rsi, [rsp+0A8h+arg_10]
0x180007daa  jmp     loc_180007C25
0x180007daf  mov     ebx, 54Eh
0x180007db4  jmp     short loc_180007D9A
0x180007db6  mov     qword ptr [r14+28h], 0
0x180007dbe  xor     ebx, ebx
0x180007dc0  mov     rsi, [rsp+0A8h+arg_10]
0x180007dc8  mov     rbp, [rsp+0A8h+arg_0]
0x180007dd0  jmp     loc_180007C2D
0x180007dd5  cmp     eax, 0Bh; switch 12 cases
0x180007dd8  ja      def_180007DEF; jumptable 0000000180007DEF default case, cases 7-9,11
0x180007dde  lea     rdx, __ImageBase
0x180007de5  mov     ecx, ds:(jpt_180007DEF - 180000000h)[rdx+rax*4]
0x180007dec  add     rcx, rdx
0x180007def  jmp     rcx; switch jump
0x180007df1  cmp     r13d, 10h; jumptable 0000000180007DEF case 6
0x180007df5  jb      loc_180007F1B
0x180007dfb  movups  xmm0, xmmword ptr [rbx]
0x180007dfe  movups  xmmword ptr [r14+28h], xmm0
0x180007e03  add     r13d, 0FFFFFFF0h
0x180007e07  xor     ebx, ebx
0x180007e09  jmp     loc_180007C2D
0x180007e0e  lea     rcx, [rsp+0A8h+var_68]
0x180007e13  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180007e18  nop
0x180007e19  mov     eax, ebx
0x180007e1b  jmp     loc_180007CBC
0x180007e20  mov     ebx, 0Eh
0x180007e25  mov     rbp, [rsp+0A8h+arg_0]
0x180007e2d  mov     rsi, [rsp+0A8h+arg_10]
0x180007e35  jmp     loc_180007C25
0x180007e3a  lea     rax, WPP_GLOBAL_Control
0x180007e41  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e48  cmp     rcx, rax
0x180007e4b  jnz     loc_180007F98
0x180007e51  lea     rcx, [rsp+0A8h+var_68]
0x180007e56  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180007e5b  nop
0x180007e5c  mov     eax, ebx
0x180007e5e  jmp     loc_180007CBC
0x180007e63  xor     ebx, ebx
0x180007e65  jmp     loc_180007C25
0x180007e6a  mov     ebx, 54Eh
0x180007e6f  mov     rsi, [rsp+0A8h+arg_10]
0x180007e77  mov     rbp, [rsp+0A8h+arg_0]
0x180007e7f  jmp     loc_180007C2D
0x180007e84  lea     rcx, [rsp+0A8h+var_68]
0x180007e89  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180007e8e  nop
0x180007e8f  mov     eax, ebx
0x180007e91  jmp     loc_180007CBC
0x180007e96  cmp     r13d, 2; jumptable 0000000180007DEF cases 1,2
0x180007e9a  jnb     short loc_180007EA6
0x180007e9c  mov     ebx, 7Ah ; 'z'
0x180007ea1  jmp     loc_180007C2D
0x180007ea6  movzx   eax, word ptr [rbx]
0x180007ea9  mov     [r14+28h], ax
0x180007eae  add     r13d, 0FFFFFFFEh
0x180007eb2  xor     ebx, ebx
0x180007eb4  jmp     loc_180007C2D
0x180007eb9  cmp     r13d, 4; jumptable 0000000180007DEF cases 3,4
0x180007ebd  jnb     short loc_180007EC9
0x180007ebf  mov     ebx, 7Ah ; 'z'
0x180007ec4  jmp     loc_180007C2D
0x180007ec9  mov     eax, [rbx]
0x180007ecb  mov     [r14+28h], eax
0x180007ecf  add     r13d, 0FFFFFFFCh
0x180007ed3  xor     ebx, ebx
0x180007ed5  jmp     loc_180007C2D
0x180007eda  cmp     r13d, 8; jumptable 0000000180007DEF case 5
0x180007ede  jnb     short loc_180007EEA
0x180007ee0  mov     ebx, 7Ah ; 'z'
0x180007ee5  jmp     loc_180007C2D
0x180007eea  mov     rax, [rbx]
0x180007eed  mov     [r14+28h], rax
0x180007ef1  add     r13d, 0FFFFFFF8h
0x180007ef5  xor     ebx, ebx
0x180007ef7  jmp     loc_180007C2D
0x180007efc  lea     r8, [r14+28h]; jumptable 0000000180007DEF case 0
0x180007f00  lea     rdx, [rsp+0A8h+Source2]
0x180007f05  lea     rcx, [rsp+0A8h+var_70]
0x180007f0a  call    ??$VaultDeserialize@E@@YAKAEAPEAEAEAKAEAE@Z; VaultDeserialize<uchar>(uchar * &,ulong &,uchar &)
0x180007f0f  mov     ebx, eax
0x180007f11  mov     r13d, [rsp+0A8h+Source2]
0x180007f16  jmp     loc_180007C2D
0x180007f1b  mov     ebx, 7Ah ; 'z'
0x180007f20  jmp     loc_180007C2D
0x180007f25  mov     ebx, 57h ; 'W'; jumptable 0000000180007DEF default case, cases 7-9,11
0x180007f2a  jmp     loc_180007D37
0x180007f2f  mov     ebx, 7Ah ; 'z'
0x180007f34  jmp     loc_180007C2D
0x180007f39  mov     ebx, 7Ah ; 'z'
0x180007f3e  jmp     loc_180007C25
0x180007f43  mov     ebx, 0Eh
0x180007f48  jmp     loc_180007C25
0x180007f4d  mov     ebx, 7Ah ; 'z'
0x180007f52  jmp     loc_180007C2D
0x180007f57  mov     ebx, 7Ah ; 'z'
0x180007f5c  mov     rsi, [rsp+0A8h+arg_10]
0x180007f64  mov     rbp, [rsp+0A8h+arg_0]
0x180007f6c  jmp     loc_180007C2D
0x180007f71  test    byte ptr [rcx+1Ch], 2
0x180007f75  jz      loc_180007D4E
0x180007f7b  mov     edx, 23h ; '#'
0x180007f80  mov     r9d, ebx
0x180007f83  lea     r8, WPP_b8c320665cdb3030ba0f4297ba888b62_Traceguids
0x180007f8a  mov     rcx, [rcx+10h]
0x180007f8e  call    WPP_SF_d
0x180007f93  jmp     loc_180007D4E
0x180007f98  test    byte ptr [rcx+1Ch], 2
0x180007f9c  jz      loc_180007E51
0x180007fa2  mov     edx, 24h ; '$'
0x180007fa7  mov     r9d, ebx
0x180007faa  lea     r8, WPP_b8c320665cdb3030ba0f4297ba888b62_Traceguids
0x180007fb1  mov     rcx, [rcx+10h]
0x180007fb5  call    WPP_SF_d
0x180007fba  jmp     loc_180007E51
0x180007fbf  lea     rax, WPP_GLOBAL_Control
  ... truncated ...
```
