# YReader::ParseDeclEntityValue(DeclEntity *)

- ea: `0x1004069e0`
- end: `0x100406cad`
- name: `?ParseDeclEntityValue@YReader@@AEAAXPEAVDeclEntity@@@Z`
- size: `717`
- prototype: `void __fastcall(YReader *__hidden this, struct DeclEntity *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x1004064a0`

## callees

- `0x100401780`
- `0x1004018f0`
- `0x100401ab0`
- `0x1004069e0`
- `0x10040a270`
- `0x100415490`
- `0x100417b70`
- `0x100417c20`
- `0x100439df0`

## pseudocode

```c
void __fastcall YReader::ParseDeclEntityValue(YReader *this, struct DeclEntity *a2)
{
  char *v2; // rbx
  int v4; // eax
  int v5; // eax
  int v6; // eax
  int v7; // eax
  unsigned int v8; // esi
  signed int v9; // r8d
  char *v10; // rax
  __int64 v11; // rcx
  wchar_t *v12; // rax
  __int64 v13; // rcx
  int v14; // edx
  unsigned int v15; // esi
  signed int v16; // r8d
  char *v17; // rax
  __int64 v18; // rcx
  wchar_t *v19; // rax
  __int64 v20; // rcx
  wchar_t *v21; // rax
  int v22; // eax
  char *v23; // rax
  unsigned int *v24; // r9
  int v25; // edx
  char *v26; // r8
  int v27; // eax
  unsigned int v28; // esi
  signed int v29; // r8d
  char *v30; // rax
  __int64 v31; // rcx
  wchar_t *v32; // rax
  __int64 v33; // rcx
  wchar_t *v34; // [rsp+20h] [rbp-18h] BYREF
  unsigned int v35[4]; // [rsp+28h] [rbp-10h] BYREF

  v34 = 0;
  v2 = (char *)a2 + 96;
  v35[0] = 0;
  while ( 1 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        while ( 1 )
        {
          v4 = YReader::GetTokenDeclLiteral(this) - 7;
          if ( v4 )
            break;
          if ( *(_QWORD *)v2 )
          {
            v28 = *((_DWORD *)v2 + 2);
            if ( v28 > 0x3FFFFFFF
              || (v29 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 96LL))(*((_QWORD *)this + 13))
                      + 2 * v28,
                  v29 < 0) )
            {
LABEL_39:
              MXRRaiseException(-2147024882);
              JUMPOUT(0x100406CACLL);
            }
            _mm_lfence();
            v30 = BlockAlloc::ReallocData((YReader *)((char *)this + 416), *(char **)v2, v29);
            v31 = *((unsigned int *)v2 + 2);
            *(_QWORD *)v2 = v30;
            v32 = (wchar_t *)&v30[2 * v31];
            v33 = *((_QWORD *)this + 13);
            v34 = v32;
            (*(void (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v33 + 104LL))(v33, &v34);
            *((_DWORD *)v2 + 2) += v35[0];
          }
          else
          {
            YReader::GetTokenData(this, (struct StringPtr *)v2);
          }
        }
        v5 = v4 - 2;
        if ( v5 )
          break;
        YReader::SetTokenData3(this, 0xAu, (struct StringPtr *)v2);
      }
      v6 = v5 - 1;
      if ( v6 )
        break;
      v34 = 0;
      if ( *(_QWORD *)v2 )
      {
        v15 = *((_DWORD *)v2 + 2);
        if ( v15 > 0x3FFFFFFF )
          goto LABEL_39;
        v16 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 96LL))(*((_QWORD *)this + 13)) + 2 * v15;
        if ( v16 < 0 )
          goto LABEL_39;
        _mm_lfence();
        v17 = BlockAlloc::ReallocData((YReader *)((char *)this + 416), *(char **)v2, v16);
        v18 = *((unsigned int *)v2 + 2);
        *(_QWORD *)v2 = v17;
        v19 = (wchar_t *)&v17[2 * v18];
        v20 = *((_QWORD *)this + 13);
        v34 = v19;
        (*(void (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v20 + 104LL))(v20, &v34);
        v14 = v35[0];
        *((_DWORD *)v2 + 2) += v35[0];
      }
      else
      {
        YReader::GetTokenData(this, (struct StringPtr *)v2);
        v14 = v35[0];
      }
      v21 = v34;
      if ( v34 )
      {
        *((_DWORD *)v2 + 2) -= v14;
        if ( *v21 == 120 )
          v22 = HexCharEntity2Utf16(v21 + 1, v14 - 1, v21, v35);
        else
          v22 = CharEntity2Utf16(v21, v14, v21, v35);
        if ( v22 < 0 )
        {
          _mm_lfence();
          MXRRaiseException(v22);
          __debugbreak();
        }
        *((_DWORD *)v2 + 2) += v35[0];
      }
      else
      {
        v23 = *(char **)v2;
        v24 = (unsigned int *)(v2 + 8);
        v25 = *((_DWORD *)v2 + 2);
        v26 = *(char **)v2;
        if ( **(_WORD **)v2 == 120 )
          v27 = HexCharEntity2Utf16((const wchar_t *)v23 + 1, v25 - 1, (wchar_t *)v26, v24);
        else
          v27 = CharEntity2Utf16((const wchar_t *)v23, v25, (wchar_t *)v26, v24);
        if ( v27 < 0 )
        {
          _mm_lfence();
          MXRRaiseException(v27);
          __debugbreak();
        }
      }
    }
    v7 = v6 - 1;
    if ( v7 )
      break;
    YReader::SetTokenData3(this, 0x26u, (struct StringPtr *)v2);
    if ( *(_QWORD *)v2 )
    {
      v8 = *((_DWORD *)v2 + 2);
      if ( v8 > 0x3FFFFFFF )
        goto LABEL_39;
      v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 96LL))(*((_QWORD *)this + 13)) + 2 * v8;
      if ( v9 < 0 )
        goto LABEL_39;
      _mm_lfence();
      v10 = BlockAlloc::ReallocData((YReader *)((char *)this + 416), *(char **)v2, v9);
      v11 = *((unsigned int *)v2 + 2);
      *(_QWORD *)v2 = v10;
      v12 = (wchar_t *)&v10[2 * v11];
      v13 = *((_QWORD *)this + 13);
      v34 = v12;
      (*(void (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v13 + 104LL))(v13, &v34);
      *((_DWORD *)v2 + 2) += v35[0];
    }
    else
    {
      YReader::GetTokenData(this, (struct StringPtr *)v2);
    }
    YReader::SetTokenData3(this, 0x3Bu, (struct StringPtr *)v2);
  }
  if ( v7 != 43 )
  {
    MXRRaiseException(-1072894419);
    __debugbreak();
  }
}

```

## disassembly

```asm
0x1004069e0  mov     [rsp+arg_8], rbx
0x1004069e5  mov     [rsp+arg_10], rbp
0x1004069ea  push    rdi
0x1004069eb  sub     rsp, 30h
0x1004069ef  xor     ebp, ebp
0x1004069f1  mov     [rsp+38h+arg_0], rsi
0x1004069f6  mov     [rsp+38h+var_18], rbp
0x1004069fb  lea     rbx, [rdx+60h]
0x1004069ff  mov     [rsp+38h+var_10], ebp
0x100406a03  mov     rdi, rcx
0x100406a06  mov     rcx, rdi; this
0x100406a09  call    ?GetTokenDeclLiteral@YReader@@AEAAHXZ; YReader::GetTokenDeclLiteral(void)
0x100406a0e  sub     eax, 7
0x100406a11  jz      loc_100406BE6
0x100406a17  sub     eax, 2
0x100406a1a  jz      loc_100406BD1
0x100406a20  sub     eax, 1
0x100406a23  jz      loc_100406AD2
0x100406a29  sub     eax, 1
0x100406a2c  jnz     loc_100406C67
0x100406a32  lea     edx, [rax+26h]; wchar_t
0x100406a35  mov     r8, rbx; struct StringPtr *
0x100406a38  mov     rcx, rdi; this
0x100406a3b  call    ?SetTokenData3@YReader@@AEAAX_WPEAUStringPtr@@@Z; YReader::SetTokenData3(wchar_t,StringPtr *)
0x100406a40  cmp     [rbx], rbp
0x100406a43  jnz     short loc_100406A52
0x100406a45  mov     rdx, rbx; struct StringPtr *
0x100406a48  mov     rcx, rdi; this
0x100406a4b  call    ?GetTokenData@YReader@@AEAAXPEAUStringPtr@@@Z; YReader::GetTokenData(StringPtr *)
0x100406a50  jmp     short loc_100406ABD
0x100406a52  mov     esi, [rbx+8]
0x100406a55  cmp     esi, 3FFFFFFFh
0x100406a5b  ja      loc_100406CA2
0x100406a61  mov     rcx, [rdi+68h]
0x100406a65  mov     rax, [rcx]
0x100406a68  mov     rax, [rax+60h]
0x100406a6c  call    cs:__guard_dispatch_icall_fptr
0x100406a72  lea     r8d, [rax+rsi*2]; unsigned int
0x100406a76  test    r8d, r8d
0x100406a79  js      loc_100406CA2
0x100406a7f  lfence
0x100406a82  mov     rdx, [rbx]; void *
0x100406a85  lea     rcx, [rdi+1A0h]; this
0x100406a8c  call    ?ReallocData@BlockAlloc@@QEAAPEAXPEAXK@Z; BlockAlloc::ReallocData(void *,ulong)
0x100406a91  mov     ecx, [rbx+8]
0x100406a94  lea     rdx, [rsp+38h+var_18]
0x100406a99  mov     [rbx], rax
0x100406a9c  lea     rax, [rax+rcx*2]
0x100406aa0  mov     rcx, [rdi+68h]
0x100406aa4  mov     [rsp+38h+var_18], rax
0x100406aa9  mov     rax, [rcx]
0x100406aac  mov     rax, [rax+68h]
0x100406ab0  call    cs:__guard_dispatch_icall_fptr
0x100406ab6  mov     eax, [rsp+38h+var_10]
0x100406aba  add     [rbx+8], eax
0x100406abd  mov     edx, 3Bh ; ';'; wchar_t
0x100406ac2  mov     r8, rbx; struct StringPtr *
0x100406ac5  mov     rcx, rdi; this
0x100406ac8  call    ?SetTokenData3@YReader@@AEAAX_WPEAUStringPtr@@@Z; YReader::SetTokenData3(wchar_t,StringPtr *)
0x100406acd  jmp     loc_100406A06
0x100406ad2  mov     [rsp+38h+var_18], rbp
0x100406ad7  cmp     [rbx], rbp
0x100406ada  jnz     short loc_100406AED
0x100406adc  mov     rdx, rbx; struct StringPtr *
0x100406adf  mov     rcx, rdi; this
0x100406ae2  call    ?GetTokenData@YReader@@AEAAXPEAUStringPtr@@@Z; YReader::GetTokenData(StringPtr *)
0x100406ae7  mov     edx, [rsp+38h+var_10]
0x100406aeb  jmp     short loc_100406B58
0x100406aed  mov     esi, [rbx+8]
0x100406af0  cmp     esi, 3FFFFFFFh
0x100406af6  ja      loc_100406CA2
0x100406afc  mov     rcx, [rdi+68h]
0x100406b00  mov     rax, [rcx]
0x100406b03  mov     rax, [rax+60h]
0x100406b07  call    cs:__guard_dispatch_icall_fptr
0x100406b0d  lea     r8d, [rax+rsi*2]; unsigned int
0x100406b11  test    r8d, r8d
0x100406b14  js      loc_100406CA2
0x100406b1a  lfence
0x100406b1d  mov     rdx, [rbx]; void *
0x100406b20  lea     rcx, [rdi+1A0h]; this
0x100406b27  call    ?ReallocData@BlockAlloc@@QEAAPEAXPEAXK@Z; BlockAlloc::ReallocData(void *,ulong)
0x100406b2c  mov     ecx, [rbx+8]
0x100406b2f  lea     rdx, [rsp+38h+var_18]
0x100406b34  mov     [rbx], rax
0x100406b37  lea     rax, [rax+rcx*2]
0x100406b3b  mov     rcx, [rdi+68h]
0x100406b3f  mov     [rsp+38h+var_18], rax
0x100406b44  mov     rax, [rcx]
0x100406b47  mov     rax, [rax+68h]
0x100406b4b  call    cs:__guard_dispatch_icall_fptr
0x100406b51  mov     edx, [rsp+38h+var_10]; int
0x100406b55  add     [rbx+8], edx
0x100406b58  mov     rax, [rsp+38h+var_18]
0x100406b5d  test    rax, rax
0x100406b60  jz      short loc_100406B9C
0x100406b62  sub     [rbx+8], edx
0x100406b65  lea     r9, [rsp+38h+var_10]; unsigned int *
0x100406b6a  cmp     word ptr [rax], 78h ; 'x'
0x100406b6e  mov     r8, rax; wchar_t *
0x100406b71  jnz     short loc_100406B80
0x100406b73  dec     edx; int
0x100406b75  lea     rcx, [rax+2]; wchar_t *
0x100406b79  call    ?HexCharEntity2Utf16@@YAJPEB_WHPEA_WPEAI@Z; HexCharEntity2Utf16(wchar_t const *,int,wchar_t *,uint *)
0x100406b7e  jmp     short loc_100406B88
0x100406b80  mov     rcx, rax; wchar_t *
0x100406b83  call    ?CharEntity2Utf16@@YAJPEB_WHPEA_WPEAI@Z; CharEntity2Utf16(wchar_t const *,int,wchar_t *,uint *)
0x100406b88  test    eax, eax
0x100406b8a  js      loc_100406C97
0x100406b90  mov     eax, [rsp+38h+var_10]
0x100406b94  add     [rbx+8], eax
0x100406b97  jmp     loc_100406A06
0x100406b9c  mov     rax, [rbx]
0x100406b9f  lea     r9, [rbx+8]; unsigned int *
0x100406ba3  mov     edx, [rbx+8]; int
0x100406ba6  mov     r8, rax; wchar_t *
0x100406ba9  cmp     word ptr [rax], 78h ; 'x'
0x100406bad  jnz     short loc_100406BBC
0x100406baf  dec     edx; int
0x100406bb1  lea     rcx, [rax+2]; wchar_t *
0x100406bb5  call    ?HexCharEntity2Utf16@@YAJPEB_WHPEA_WPEAI@Z; HexCharEntity2Utf16(wchar_t const *,int,wchar_t *,uint *)
0x100406bba  jmp     short loc_100406BC4
0x100406bbc  mov     rcx, rax; wchar_t *
0x100406bbf  call    ?CharEntity2Utf16@@YAJPEB_WHPEA_WPEAI@Z; CharEntity2Utf16(wchar_t const *,int,wchar_t *,uint *)
0x100406bc4  test    eax, eax
0x100406bc6  js      loc_100406C81
0x100406bcc  jmp     loc_100406A06
0x100406bd1  mov     edx, 0Ah; wchar_t
0x100406bd6  mov     r8, rbx; struct StringPtr *
0x100406bd9  mov     rcx, rdi; this
0x100406bdc  call    ?SetTokenData3@YReader@@AEAAX_WPEAUStringPtr@@@Z; YReader::SetTokenData3(wchar_t,StringPtr *)
0x100406be1  jmp     loc_100406A06
0x100406be6  cmp     [rbx], rbp
0x100406be9  jnz     short loc_100406BFB
0x100406beb  mov     rdx, rbx; struct StringPtr *
0x100406bee  mov     rcx, rdi; this
0x100406bf1  call    ?GetTokenData@YReader@@AEAAXPEAUStringPtr@@@Z; YReader::GetTokenData(StringPtr *)
0x100406bf6  jmp     loc_100406A06
0x100406bfb  mov     esi, [rbx+8]
0x100406bfe  cmp     esi, 3FFFFFFFh
0x100406c04  ja      loc_100406CA2
0x100406c0a  mov     rcx, [rdi+68h]
0x100406c0e  mov     rax, [rcx]
0x100406c11  mov     rax, [rax+60h]
0x100406c15  call    cs:__guard_dispatch_icall_fptr
0x100406c1b  lea     r8d, [rax+rsi*2]; unsigned int
0x100406c1f  test    r8d, r8d
0x100406c22  js      short loc_100406CA2
0x100406c24  lfence
0x100406c27  mov     rdx, [rbx]; void *
0x100406c2a  lea     rcx, [rdi+1A0h]; this
0x100406c31  call    ?ReallocData@BlockAlloc@@QEAAPEAXPEAXK@Z; BlockAlloc::ReallocData(void *,ulong)
0x100406c36  mov     ecx, [rbx+8]
0x100406c39  lea     rdx, [rsp+38h+var_18]
0x100406c3e  mov     [rbx], rax
0x100406c41  lea     rax, [rax+rcx*2]
0x100406c45  mov     rcx, [rdi+68h]
0x100406c49  mov     [rsp+38h+var_18], rax
0x100406c4e  mov     rax, [rcx]
0x100406c51  mov     rax, [rax+68h]
0x100406c55  call    cs:__guard_dispatch_icall_fptr
0x100406c5b  mov     eax, [rsp+38h+var_10]
0x100406c5f  add     [rbx+8], eax
0x100406c62  jmp     loc_100406A06
0x100406c67  cmp     eax, 2Bh ; '+'
0x100406c6a  jnz     short loc_100406C8C
0x100406c6c  mov     rsi, [rsp+38h+arg_0]
0x100406c71  mov     rbx, [rsp+38h+arg_8]
0x100406c76  mov     rbp, [rsp+38h+arg_10]
0x100406c7b  add     rsp, 30h
0x100406c7f  pop     rdi
0x100406c80  retn
0x100406c81  lfence
0x100406c84  mov     ecx, eax; int
0x100406c86  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100406c8b  int     3; Trap to Debugger
0x100406c8c  mov     ecx, 0C00CEE2Dh; int
0x100406c91  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100406c96  int     3; Trap to Debugger
0x100406c97  lfence
0x100406c9a  mov     ecx, eax; int
0x100406c9c  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100406ca1  int     3; Trap to Debugger
0x100406ca2  mov     ecx, 8007000Eh; int
0x100406ca7  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
