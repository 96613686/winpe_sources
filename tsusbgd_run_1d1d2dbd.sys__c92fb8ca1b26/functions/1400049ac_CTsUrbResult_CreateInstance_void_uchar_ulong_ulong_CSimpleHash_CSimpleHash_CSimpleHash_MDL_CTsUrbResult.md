# CTsUrbResult::CreateInstance(void *,uchar *,ulong,ulong,CSimpleHash *,CSimpleHash *,CSimpleHash *,_MDL *,CTsUrbResult * *)

- ea: `0x1400049ac`
- end: `0x140004dd3`
- name: `?CreateInstance@CTsUrbResult@@SAJPEAXPEAEKKPEAVCSimpleHash@@22PEAU_MDL@@PEAPEAV1@@Z`
- size: `1063`
- prototype: `__int64 __fastcall(void ***, unsigned __int8 *, unsigned int, unsigned int, struct CSimpleHash *, struct CSimpleHash *, struct CSimpleHash *, struct _MDL *, void ****)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140002c60`

## callees

- `0x140004898`
- `0x1400049ac`
- `0x140006370`
- `0x140006440`

## pseudocode

```c
__int64 __fastcall CTsUrbResult::CreateInstance(
        void ***a1,
        unsigned __int8 *a2,
        unsigned int a3,
        unsigned int a4,
        struct CSimpleHash *a5,
        struct CSimpleHash *a6,
        struct CSimpleHash *a7,
        struct _MDL *a8,
        void ****a9)
{
  int v13; // edi
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  void **v17; // rax
  unsigned int v18; // ecx
  unsigned int v19; // ecx
  unsigned int v20; // ecx
  unsigned int v21; // ecx
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  unsigned int v27; // ecx
  unsigned int v28; // ecx
  unsigned int v29; // ecx
  unsigned int v30; // ecx
  unsigned int v31; // ecx
  unsigned int v32; // ecx
  unsigned int v33; // ecx
  unsigned int v34; // ecx
  unsigned int v35; // ecx
  unsigned int v36; // ecx
  unsigned int v37; // ecx
  unsigned int v38; // ecx
  unsigned int v39; // ecx
  unsigned int v40; // ecx

  if ( a3 < 8 )
    return (unsigned int)-1073741811;
  v14 = *((unsigned __int16 *)a2 + 1);
  if ( v14 > 0x1A )
  {
    if ( v14 > 0x28 )
    {
      if ( v14 > 0x2F )
      {
        v39 = v14 - 48;
        if ( !v39 || (v40 = v39 - 1) == 0 )
        {
          if ( !a1 )
            return (unsigned int)-1073741637;
LABEL_84:
          memset(a1, 0, 0x6C0u);
          v17 = &CTsUrbResultPipeRequest::`vftable';
          goto LABEL_85;
        }
        if ( v40 != 1 || !a1 )
          return (unsigned int)-1073741637;
        memset(a1, 0, 0x6C0u);
        v17 = &CTsUrbResultControlTransferEx::`vftable';
        goto LABEL_85;
      }
      if ( v14 == 47 )
        return (unsigned int)-1073741637;
      v38 = v14 - 41;
      if ( v38 )
      {
        if ( v38 != 1 || !a1 )
          return (unsigned int)-1073741637;
        memset(a1, 0, 0x6C0u);
        v17 = &CTsUrbResultOsFeatureDescriptor::`vftable';
        goto LABEL_85;
      }
    }
    else if ( v14 != 40 )
    {
      if ( v14 <= 0x21 )
      {
        if ( v14 == 33 )
          goto LABEL_42;
        v30 = v14 - 27;
        if ( v30 )
        {
          v31 = v30 - 1;
          if ( v31 )
          {
            v32 = v31 - 1;
            if ( !v32 )
              return (unsigned int)-1073741637;
            v29 = v32 - 1;
            if ( !v29 )
            {
LABEL_12:
              if ( !a1 )
                return (unsigned int)-1073741637;
              goto LABEL_84;
            }
LABEL_49:
            if ( v29 - 1 > 1 )
              return (unsigned int)-1073741637;
          }
        }
LABEL_50:
        if ( !a1 )
          return (unsigned int)-1073741637;
        memset(a1, 0, 0x6C0u);
        v17 = &CTsUrbResultClassRequest::`vftable';
        goto LABEL_85;
      }
      v33 = v14 - 34;
      if ( !v33 )
        goto LABEL_44;
      v34 = v33 - 1;
      if ( !v34 )
        goto LABEL_44;
      v35 = v34 - 1;
      if ( v35 )
      {
        v36 = v35 - 1;
        if ( v36 )
        {
          v37 = v36 - 1;
          if ( !v37 )
          {
            if ( !a1 )
              return (unsigned int)-1073741637;
            memset(a1, 0, 0x6C0u);
            v17 = &CTsUrbResultGetConfigRequest::`vftable';
            goto LABEL_85;
          }
          if ( v37 != 1 || !a1 )
            return (unsigned int)-1073741637;
LABEL_43:
          memset(a1, 0, 0x6C0u);
          v17 = &CTsUrbResultGetStatus::`vftable';
          goto LABEL_85;
        }
      }
    }
LABEL_24:
    if ( !a1 )
      return (unsigned int)-1073741637;
    memset(a1, 0, 0x6C0u);
    v17 = &CTsUrbResultControlDescriptor::`vftable';
    goto LABEL_85;
  }
  if ( v14 == 26 )
    goto LABEL_50;
  if ( v14 > 0xD )
  {
    if ( v14 <= 0x14 )
    {
      if ( v14 != 20 )
      {
        v22 = v14 - 14;
        if ( !v22 )
          goto LABEL_44;
        v23 = v22 - 1;
        if ( !v23 )
          goto LABEL_44;
        v24 = v23 - 1;
        if ( !v24 )
          goto LABEL_44;
        v25 = v24 - 1;
        if ( !v25 )
          goto LABEL_44;
        v26 = v25 - 1;
        if ( !v26 )
          goto LABEL_44;
        if ( v26 != 1 )
          return (unsigned int)-1073741637;
      }
      goto LABEL_42;
    }
    v27 = v14 - 21;
    if ( v27 )
    {
      v28 = v27 - 1;
      if ( !v28 )
        return (unsigned int)-1073741637;
      v29 = v28 - 1;
      if ( !v29 )
        goto LABEL_50;
      goto LABEL_49;
    }
LABEL_42:
    if ( !a1 )
      return (unsigned int)-1073741637;
    goto LABEL_43;
  }
  if ( v14 == 13 )
  {
LABEL_44:
    if ( !a1 )
      return (unsigned int)-1073741637;
    memset(a1, 0, 0x6C0u);
    v17 = &CTsUrbResultControlFeature::`vftable';
    goto LABEL_85;
  }
  if ( v14 > 6 )
  {
    v18 = v14 - 7;
    if ( !v18 )
    {
      if ( !a1 )
        return (unsigned int)-1073741637;
      memset(a1, 0, 0x6C0u);
      v17 = &CTsUrbResultCurrentFrame::`vftable';
      goto LABEL_85;
    }
    v19 = v18 - 1;
    if ( !v19 )
    {
      if ( !a1 )
        return (unsigned int)-1073741637;
      memset(a1, 0, 0x6C0u);
      v17 = &CTsUrbResultControlTransfer::`vftable';
      goto LABEL_85;
    }
    v20 = v19 - 1;
    if ( !v20 )
    {
      if ( !a1 )
        return (unsigned int)-1073741637;
      memset(a1, 0, 0x6C0u);
      v17 = &CTsUrbResultBulkTransfer::`vftable';
      goto LABEL_85;
    }
    v21 = v20 - 1;
    if ( !v21 )
    {
      if ( !a1 )
        return (unsigned int)-1073741637;
      memset(a1, 0, 0x6C0u);
      v17 = &CTsUrbResultIsochTransfer::`vftable';
      goto LABEL_85;
    }
    if ( v21 - 1 > 1 )
      return (unsigned int)-1073741637;
    goto LABEL_24;
  }
  if ( v14 == 6 )
    return (unsigned int)-1073741637;
  if ( *((_WORD *)a2 + 1) )
  {
    v15 = v14 - 1;
    if ( v15 )
    {
      if ( v15 != 1 )
        return (unsigned int)-1073741637;
      goto LABEL_12;
    }
    if ( !a1 )
      return (unsigned int)-1073741637;
    memset(a1, 0, 0x6C0u);
    v17 = &CTsUrbResultSelectInterface::`vftable';
  }
  else
  {
    if ( !a1 )
      return (unsigned int)-1073741637;
    memset(a1, 0, 0x6C0u);
    v17 = &CTsUrbResultSelectConfig::`vftable';
  }
LABEL_85:
  *a1 = v17;
  v13 = ((__int64 (__fastcall *)(void ***, unsigned __int8 *, _QWORD, _QWORD, struct CSimpleHash *, struct CSimpleHash *, struct CSimpleHash *, struct _MDL *))**a1)(
          a1,
          a2,
          a3,
          a4,
          a5,
          a6,
          a7,
          a8);
  if ( v13 < 0 )
  {
    CTsUrbResult::~CTsUrbResult((CTsUrbResult *)a1);
  }
  else
  {
    v13 = 0;
    *a9 = a1;
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1400049ac  push    rbx
0x1400049ae  push    rbp
0x1400049af  push    rsi
0x1400049b0  push    rdi
0x1400049b1  sub     rsp, 58h
0x1400049b5  mov     ebp, r9d
0x1400049b8  mov     esi, r8d
0x1400049bb  mov     rdi, rdx
0x1400049be  mov     rbx, rcx
0x1400049c1  cmp     r8d, 8
0x1400049c5  jnb     short loc_1400049CE
0x1400049c7  mov     edi, 0C000000Dh
0x1400049cc  jmp     short loc_140004A22
0x1400049ce  movzx   ecx, word ptr [rdx+2]
0x1400049d2  cmp     ecx, 1Ah
0x1400049d5  ja      loc_140004C08
0x1400049db  jz      loc_140004BE3
0x1400049e1  cmp     ecx, 0Dh
0x1400049e4  ja      loc_140004B4F
0x1400049ea  jz      loc_140004B9D
0x1400049f0  cmp     ecx, 6
0x1400049f3  ja      short loc_140004A70
0x1400049f5  jz      short loc_140004A1D
0x1400049f7  test    ecx, ecx
0x1400049f9  jz      short loc_140004A4F
0x1400049fb  sub     ecx, 1
0x1400049fe  jz      short loc_140004A2E
0x140004a00  sub     ecx, 1
0x140004a03  jnz     loc_140004CDE
0x140004a09  test    rbx, rbx
0x140004a0c  jnz     loc_140004D46
0x140004a12  xor     ebx, ebx
0x140004a14  test    rbx, rbx
0x140004a17  jnz     loc_140004D60
0x140004a1d  mov     edi, 0C00000BBh
0x140004a22  mov     eax, edi
0x140004a24  add     rsp, 58h
0x140004a28  pop     rdi
0x140004a29  pop     rsi
0x140004a2a  pop     rbp
0x140004a2b  pop     rbx
0x140004a2c  retn
0x140004a2e  test    rbx, rbx
0x140004a31  jz      short loc_140004A12
0x140004a33  xor     edx, edx; Val
0x140004a35  mov     r8d, 6C0h; Size
0x140004a3b  mov     rcx, rbx; void *
0x140004a3e  call    memset
0x140004a43  lea     rax, ??_7CTsUrbResultSelectInterface@@6B@; const CTsUrbResultSelectInterface::`vftable'
0x140004a4a  jmp     loc_140004D5D
0x140004a4f  test    rbx, rbx
0x140004a52  jz      short loc_140004A12
0x140004a54  xor     edx, edx; Val
0x140004a56  mov     r8d, 6C0h; Size
0x140004a5c  mov     rcx, rbx; void *
0x140004a5f  call    memset
0x140004a64  lea     rax, ??_7CTsUrbResultSelectConfig@@6B@; const CTsUrbResultSelectConfig::`vftable'
0x140004a6b  jmp     loc_140004D5D
0x140004a70  sub     ecx, 7
0x140004a73  jz      loc_140004B2A
0x140004a79  sub     ecx, 1
0x140004a7c  jz      loc_140004B05
0x140004a82  sub     ecx, 1
0x140004a85  jz      short loc_140004AE0
0x140004a87  sub     ecx, 1
0x140004a8a  jz      short loc_140004ABB
0x140004a8c  sub     ecx, 1
0x140004a8f  jz      short loc_140004A96
0x140004a91  cmp     ecx, 1
0x140004a94  jnz     short loc_140004A1D
0x140004a96  test    rbx, rbx
0x140004a99  jz      loc_140004A12
0x140004a9f  xor     edx, edx; Val
0x140004aa1  mov     r8d, 6C0h; Size
0x140004aa7  mov     rcx, rbx; void *
0x140004aaa  call    memset
0x140004aaf  lea     rax, ??_7CTsUrbResultControlDescriptor@@6B@; const CTsUrbResultControlDescriptor::`vftable'
0x140004ab6  jmp     loc_140004D5D
0x140004abb  test    rbx, rbx
0x140004abe  jz      loc_140004A12
0x140004ac4  xor     edx, edx; Val
0x140004ac6  mov     r8d, 6C0h; Size
0x140004acc  mov     rcx, rbx; void *
0x140004acf  call    memset
0x140004ad4  lea     rax, ??_7CTsUrbResultIsochTransfer@@6B@; const CTsUrbResultIsochTransfer::`vftable'
0x140004adb  jmp     loc_140004D5D
0x140004ae0  test    rbx, rbx
0x140004ae3  jz      loc_140004A12
0x140004ae9  xor     edx, edx; Val
0x140004aeb  mov     r8d, 6C0h; Size
0x140004af1  mov     rcx, rbx; void *
0x140004af4  call    memset
0x140004af9  lea     rax, ??_7CTsUrbResultBulkTransfer@@6B@; const CTsUrbResultBulkTransfer::`vftable'
0x140004b00  jmp     loc_140004D5D
0x140004b05  test    rbx, rbx
0x140004b08  jz      loc_140004A12
0x140004b0e  xor     edx, edx; Val
0x140004b10  mov     r8d, 6C0h; Size
0x140004b16  mov     rcx, rbx; void *
0x140004b19  call    memset
0x140004b1e  lea     rax, ??_7CTsUrbResultControlTransfer@@6B@; const CTsUrbResultControlTransfer::`vftable'
0x140004b25  jmp     loc_140004D5D
0x140004b2a  test    rbx, rbx
0x140004b2d  jz      loc_140004A12
0x140004b33  xor     edx, edx; Val
0x140004b35  mov     r8d, 6C0h; Size
0x140004b3b  mov     rcx, rbx; void *
0x140004b3e  call    memset
0x140004b43  lea     rax, ??_7CTsUrbResultCurrentFrame@@6B@; const CTsUrbResultCurrentFrame::`vftable'
0x140004b4a  jmp     loc_140004D5D
0x140004b4f  cmp     ecx, 14h
0x140004b52  ja      short loc_140004BC2
0x140004b54  jz      short loc_140004B78
0x140004b56  sub     ecx, 0Eh
0x140004b59  jz      short loc_140004B9D
0x140004b5b  sub     ecx, 1
0x140004b5e  jz      short loc_140004B9D
0x140004b60  sub     ecx, 1
0x140004b63  jz      short loc_140004B9D
0x140004b65  sub     ecx, 1
0x140004b68  jz      short loc_140004B9D
0x140004b6a  sub     ecx, 1
0x140004b6d  jz      short loc_140004B9D
0x140004b6f  cmp     ecx, 1
0x140004b72  jnz     loc_140004A1D
0x140004b78  test    rbx, rbx
0x140004b7b  jz      loc_140004A12
0x140004b81  xor     edx, edx; Val
0x140004b83  mov     r8d, 6C0h; Size
0x140004b89  mov     rcx, rbx; void *
0x140004b8c  call    memset
0x140004b91  lea     rax, ??_7CTsUrbResultGetStatus@@6B@; const CTsUrbResultGetStatus::`vftable'
0x140004b98  jmp     loc_140004D5D
0x140004b9d  test    rbx, rbx
0x140004ba0  jz      loc_140004A12
0x140004ba6  xor     edx, edx; Val
0x140004ba8  mov     r8d, 6C0h; Size
0x140004bae  mov     rcx, rbx; void *
0x140004bb1  call    memset
0x140004bb6  lea     rax, ??_7CTsUrbResultControlFeature@@6B@; const CTsUrbResultControlFeature::`vftable'
0x140004bbd  jmp     loc_140004D5D
0x140004bc2  sub     ecx, 15h
0x140004bc5  jz      short loc_140004B78
0x140004bc7  sub     ecx, 1
0x140004bca  jz      loc_140004A1D
0x140004bd0  sub     ecx, 1
0x140004bd3  jz      short loc_140004BE3
0x140004bd5  sub     ecx, 1
0x140004bd8  jz      short loc_140004BE3
0x140004bda  cmp     ecx, 1
0x140004bdd  jnz     loc_140004A1D
0x140004be3  test    rbx, rbx
0x140004be6  jz      loc_140004A12
0x140004bec  xor     edx, edx; Val
0x140004bee  mov     r8d, 6C0h; Size
0x140004bf4  mov     rcx, rbx; void *
0x140004bf7  call    memset
0x140004bfc  lea     rax, ??_7CTsUrbResultClassRequest@@6B@; const CTsUrbResultClassRequest::`vftable'
0x140004c03  jmp     loc_140004D5D
0x140004c08  cmp     ecx, 28h ; '('
0x140004c0b  ja      loc_140004CBC
0x140004c11  jz      loc_140004A96
0x140004c17  cmp     ecx, 21h ; '!'
0x140004c1a  ja      short loc_140004C40
0x140004c1c  jz      loc_140004B78
0x140004c22  sub     ecx, 1Bh
0x140004c25  jz      short loc_140004BE3
0x140004c27  sub     ecx, 1
0x140004c2a  jz      short loc_140004BE3
0x140004c2c  sub     ecx, 1
0x140004c2f  jz      loc_140004A1D
0x140004c35  sub     ecx, 1
0x140004c38  jz      loc_140004A09
0x140004c3e  jmp     short loc_140004BD5
0x140004c40  sub     ecx, 22h ; '"'
0x140004c43  jz      loc_140004B9D
0x140004c49  sub     ecx, 1
0x140004c4c  jz      loc_140004B9D
0x140004c52  sub     ecx, 1
0x140004c55  jz      loc_140004A96
0x140004c5b  sub     ecx, 1
0x140004c5e  jz      loc_140004A96
0x140004c64  sub     ecx, 1
0x140004c67  jz      short loc_140004C97
0x140004c69  cmp     ecx, 1
0x140004c6c  jnz     loc_140004A1D
0x140004c72  test    rbx, rbx
0x140004c75  jz      loc_140004A12
0x140004c7b  xor     edx, edx; Val
0x140004c7d  mov     r8d, 6C0h; Size
0x140004c83  mov     rcx, rbx; void *
0x140004c86  call    memset
0x140004c8b  lea     rax, ??_7CTsUrbResultGetStatus@@6B@; const CTsUrbResultGetStatus::`vftable'
0x140004c92  jmp     loc_140004D5D
0x140004c97  test    rbx, rbx
0x140004c9a  jz      loc_140004A12
0x140004ca0  xor     edx, edx; Val
0x140004ca2  mov     r8d, 6C0h; Size
0x140004ca8  mov     rcx, rbx; void *
0x140004cab  call    memset
0x140004cb0  lea     rax, ??_7CTsUrbResultGetConfigRequest@@6B@; const CTsUrbResultGetConfigRequest::`vftable'
0x140004cb7  jmp     loc_140004D5D
0x140004cbc  cmp     ecx, 2Fh ; '/'
0x140004cbf  ja      short loc_140004D08
0x140004cc1  jz      loc_140004A1D
0x140004cc7  sub     ecx, 29h ; ')'
0x140004cca  jz      loc_140004A96
0x140004cd0  sub     ecx, 1
0x140004cd3  jz      short loc_140004CE6
0x140004cd5  sub     ecx, 1
0x140004cd8  jz      loc_140004A1D
0x140004cde  sub     ecx, 1
0x140004ce1  jmp     loc_140004A1D
0x140004ce6  test    rbx, rbx
0x140004ce9  jz      loc_140004A12
0x140004cef  xor     edx, edx; Val
0x140004cf1  mov     r8d, 6C0h; Size
0x140004cf7  mov     rcx, rbx; void *
0x140004cfa  call    memset
0x140004cff  lea     rax, ??_7CTsUrbResultOsFeatureDescriptor@@6B@; const CTsUrbResultOsFeatureDescriptor::`vftable'
0x140004d06  jmp     short loc_140004D5D
0x140004d08  sub     ecx, 30h ; '0'
0x140004d0b  jz      short loc_140004D3D
0x140004d0d  sub     ecx, 1
0x140004d10  jz      short loc_140004D3D
0x140004d12  sub     ecx, 1
0x140004d15  jnz     loc_140004A1D
0x140004d1b  test    rbx, rbx
0x140004d1e  jz      loc_140004A12
0x140004d24  xor     edx, edx; Val
0x140004d26  mov     r8d, 6C0h; Size
0x140004d2c  mov     rcx, rbx; void *
0x140004d2f  call    memset
0x140004d34  lea     rax, ??_7CTsUrbResultControlTransferEx@@6B@; const CTsUrbResultControlTransferEx::`vftable'
0x140004d3b  jmp     short loc_140004D5D
0x140004d3d  test    rbx, rbx
0x140004d40  jz      loc_140004A1D
0x140004d46  mov     r8d, 6C0h; Size
0x140004d4c  xor     edx, edx; Val
0x140004d4e  mov     rcx, rbx; void *
0x140004d51  call    memset
0x140004d56  lea     rax, ??_7CTsUrbResultPipeRequest@@6B@; const CTsUrbResultPipeRequest::`vftable'
0x140004d5d  mov     [rbx], rax
0x140004d60  mov     rax, [rbx]
0x140004d63  mov     r9d, ebp
0x140004d66  mov     r8d, esi
0x140004d69  mov     rdx, rdi
0x140004d6c  mov     rcx, rbx
0x140004d6f  mov     r10, [rax]
0x140004d72  mov     rax, [rsp+78h+arg_38]
0x140004d7a  mov     [rsp+78h+var_40], rax
0x140004d7f  mov     rax, [rsp+78h+arg_30]
0x140004d87  mov     [rsp+78h+var_48], rax
0x140004d8c  mov     rax, [rsp+78h+arg_28]
0x140004d94  mov     [rsp+78h+var_50], rax
0x140004d99  mov     rax, [rsp+78h+arg_20]
0x140004da1  mov     [rsp+78h+var_58], rax
0x140004da6  mov     rax, r10
0x140004da9  call    _guard_dispatch_icall
0x140004dae  mov     edi, eax
0x140004db0  test    eax, eax
0x140004db2  js      short loc_140004DC6
0x140004db4  mov     rax, [rsp+78h+arg_40]
0x140004dbc  xor     edi, edi
0x140004dbe  mov     [rax], rbx
0x140004dc1  jmp     loc_140004A22
0x140004dc6  mov     rcx, rbx; this
0x140004dc9  call    ??1CTsUrbResult@@QEAA@XZ; CTsUrbResult::~CTsUrbResult(void)
0x140004dce  jmp     loc_140004A22
```
