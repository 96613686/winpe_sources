# GetObjectID(IPortableDevice *,ushort *,ushort *,uint)

- ea: `0x1800147ec`
- end: `0x180014b51`
- name: `?GetObjectID@@YAJPEAUIPortableDevice@@PEAG1I@Z`
- size: `869`
- prototype: `__int64 __fastcall(struct IPortableDevice *, unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800118d4`
- `0x180012cc0`
- `0x180014140`

## callees

- `0x1800147ec`
- `0x18002ff5c`
- `0x180039dd4`
- `0x180039e80`
- `0x180039ef8`
- `0x180078010`

## import_xrefs

- `SHLWAPI!StrCmpIW` at `0x1800149f5`
- `SHLWAPI!StrCmpIW` at `0x1800149f5`
- `ole32!PropVariantClear` at `0x180014acb`
- `ole32!PropVariantClear` at `0x180014acb`
- `ole32!CoCreateInstance` at `0x1800148c6`
- `ole32!CoCreateInstance` at `0x1800148c6`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall GetObjectID(struct IPortableDevice *a1, unsigned __int16 *a2, unsigned __int16 *a3, unsigned int a4)
{
  __int64 v4; // r14
  unsigned int v7; // ebx
  HRESULT v8; // eax
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  int v11; // eax
  _QWORD *v12; // rcx
  int v13; // edx
  __int64 v14; // rax
  BSTR bstrVal; // rcx
  __int64 v16; // rdx
  unsigned __int16 *v17; // r8
  unsigned __int16 v18; // r9
  unsigned __int16 *v19; // rcx
  __int64 v21; // [rsp+30h] [rbp-48h] BYREF
  __int64 v22; // [rsp+38h] [rbp-40h] BYREF
  PROPVARIANT psz2; // [rsp+40h] [rbp-38h] BYREF
  __int128 v24; // [rsp+58h] [rbp-20h] BYREF
  __int64 v25; // [rsp+68h] [rbp-10h]
  LPVOID ppv; // [rsp+C0h] [rbp+48h] BYREF

  v4 = a4;
  v22 = 0;
  v21 = 0;
  ppv = 0;
  memset(&psz2, 0, sizeof(psz2));
  v24 = 0;
  v25 = 0;
  if ( !a1 || !a2 || !a3 || !a4 )
  {
    v7 = -2147024809;
    goto LABEL_47;
  }
  *a3 = 0;
  v8 = ((__int64 (__fastcall *)(struct IPortableDevice *, __int64 *))a1->lpVtbl->Content)(a1, &v22);
  v7 = v8;
  if ( v8 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v10 = 25;
LABEL_10:
      WPP_SF_d(v9[2], v10, &WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids, (unsigned int)v8);
      goto LABEL_47;
    }
    goto LABEL_47;
  }
  v8 = CoCreateInstance(
         &CLSID_PortableDevicePropVariantCollection,
         0,
         1u,
         &GUID_89b2e422_4f1b_4316_bcef_a44afea83eb3,
         &ppv);
  v7 = v8;
  if ( v8 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v10 = 26;
      goto LABEL_10;
    }
    goto LABEL_47;
  }
  LOWORD(v24) = 31;
  *((_QWORD *)&v24 + 1) = a2;
  v11 = (*(__int64 (__fastcall **)(LPVOID, __int128 *))(*(_QWORD *)ppv + 40LL))(ppv, &v24);
  v7 = v11;
  if ( v11 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_47;
    v13 = 27;
    goto LABEL_19;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, LPVOID, __int64 *))(*(_QWORD *)v22 + 72LL))(v22, ppv, &v21);
  v7 = v11;
  if ( v11 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_47;
    v13 = 28;
LABEL_19:
    WPP_SF_Sd(v12[2], v13, (unsigned int)&WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids, (_DWORD)a2, v11);
    goto LABEL_47;
  }
  v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, PROPVARIANT *))(*(_QWORD *)v21 + 32LL))(v21, 0, &psz2);
  v7 = v8;
  if ( v8 >= 0 )
  {
    if ( psz2.vt != 31 || !psz2.hVal.QuadPart || !StrCmpIW(&String, psz2.bstrVal) )
    {
      v7 = -2147418113;
      goto LABEL_47;
    }
    if ( (unsigned int)v4 <= 0x7FFFFFFF )
    {
      v14 = 2147483646;
      bstrVal = psz2.bstrVal;
      v16 = v4;
      v17 = a3;
      do
      {
        if ( !v14 )
          break;
        v18 = *bstrVal;
        if ( !*bstrVal )
          break;
        ++bstrVal;
        *v17++ = v18;
        --v14;
        --v16;
      }
      while ( v16 );
      v19 = v17 - 1;
      if ( v16 )
        v19 = v17;
      *v19 = 0;
      v7 = v16 == 0 ? 0x8007007A : 0;
      if ( v16 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_SS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            31,
            (unsigned int)&WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids,
            (_DWORD)a2,
            (__int64)a3);
        goto LABEL_47;
      }
    }
    else
    {
      v7 = -2147024809;
      *a3 = 0;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_Sdd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        30,
        (unsigned int)&WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids,
        psz2.lVal,
        v4,
        v7);
    goto LABEL_47;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v10 = 29;
    goto LABEL_10;
  }
LABEL_47:
  PropVariantClear(&psz2);
  if ( (v7 & 0x80000000) != 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids, v7);
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  return v7;
}

```

## disassembly

```asm
0x1800147ec  push    rbp
0x1800147ee  push    rbx
0x1800147ef  push    rsi
0x1800147f0  push    rdi
0x1800147f1  push    r12
0x1800147f3  push    r13
0x1800147f5  push    r14
0x1800147f7  push    r15
0x1800147f9  mov     rbp, rsp
0x1800147fc  sub     rsp, 78h
0x180014800  mov     r14d, r9d
0x180014803  mov     rdi, r8
0x180014806  mov     rsi, rdx
0x180014809  xor     r15d, r15d
0x18001480c  mov     [rbp+var_40], r15
0x180014810  mov     [rbp+var_48], r15
0x180014814  mov     [rbp+arg_0], r15
0x180014818  xorps   xmm0, xmm0
0x18001481b  xor     eax, eax
0x18001481d  movups  xmmword ptr [rbp+psz2], xmm0
0x180014821  mov     [rbp+var_28], rax
0x180014825  xorps   xmm1, xmm1
0x180014828  movups  [rbp+var_20], xmm1
0x18001482c  mov     [rbp+var_10], rax
0x180014830  lea     r12, WPP_GLOBAL_Control
0x180014837  lea     r13, WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids
0x18001483e  test    rcx, rcx
0x180014841  jnz     short loc_18001484D
0x180014843  mov     ebx, 80070057h
0x180014848  jmp     loc_180014AC7
0x18001484d  test    rsi, rsi
0x180014850  jz      short loc_180014843
0x180014852  test    rdi, rdi
0x180014855  jz      short loc_180014843
0x180014857  test    r9d, r9d
0x18001485a  jz      short loc_180014843
0x18001485c  mov     [r8], r15w
0x180014860  mov     rax, [rcx]
0x180014863  lea     rdx, [rbp+var_40]
0x180014867  mov     rax, [rax+28h]
0x18001486b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014870  mov     ebx, eax
0x180014872  test    eax, eax
0x180014874  jns     short loc_1800148A9
0x180014876  mov     rcx, cs:WPP_GLOBAL_Control
0x18001487d  cmp     rcx, r12
0x180014880  jz      loc_180014AC7
0x180014886  test    byte ptr [rcx+1Ch], 2
0x18001488a  jz      loc_180014AC7
0x180014890  mov     edx, 19h
0x180014895  mov     r9d, eax
0x180014898  mov     r8, r13
0x18001489b  mov     rcx, [rcx+10h]
0x18001489f  call    WPP_SF_d
0x1800148a4  jmp     loc_180014AC7
0x1800148a9  lea     rax, [rbp+arg_0]
0x1800148ad  mov     [rsp+78h+ppv], rax; ppv
0x1800148b2  lea     r9, _GUID_89b2e422_4f1b_4316_bcef_a44afea83eb3; riid
0x1800148b9  xor     edx, edx; pUnkOuter
0x1800148bb  lea     r8d, [rdx+1]; dwClsContext
0x1800148bf  lea     rcx, CLSID_PortableDevicePropVariantCollection; rclsid
0x1800148c6  call    cs:__imp_CoCreateInstance
0x1800148cc  mov     ebx, eax
0x1800148ce  test    eax, eax
0x1800148d0  jns     short loc_1800148F3
0x1800148d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800148d9  cmp     rcx, r12
0x1800148dc  jz      loc_180014AC7
0x1800148e2  test    byte ptr [rcx+1Ch], 2
0x1800148e6  jz      loc_180014AC7
0x1800148ec  mov     edx, 1Ah
0x1800148f1  jmp     short loc_180014895
0x1800148f3  mov     eax, 1Fh
0x1800148f8  mov     word ptr [rbp+var_20], ax
0x1800148fc  mov     qword ptr [rbp+var_20+8], rsi
0x180014900  mov     rcx, [rbp+arg_0]
0x180014904  mov     rax, [rcx]
0x180014907  lea     rdx, [rbp+var_20]
0x18001490b  mov     rax, [rax+28h]
0x18001490f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014914  mov     ebx, eax
0x180014916  test    eax, eax
0x180014918  jns     short loc_180014951
0x18001491a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014921  cmp     rcx, r12
0x180014924  jz      loc_180014AC7
0x18001492a  test    byte ptr [rcx+1Ch], 2
0x18001492e  jz      loc_180014AC7
0x180014934  mov     edx, 1Bh
0x180014939  mov     dword ptr [rsp+78h+ppv], eax
0x18001493d  mov     r9, rsi
0x180014940  mov     r8, r13
0x180014943  mov     rcx, [rcx+10h]
0x180014947  call    WPP_SF_Sd
0x18001494c  jmp     loc_180014AC7
0x180014951  mov     rcx, [rbp+var_40]
0x180014955  mov     rax, [rcx]
0x180014958  lea     r8, [rbp+var_48]
0x18001495c  mov     rdx, [rbp+arg_0]
0x180014960  mov     rax, [rax+48h]
0x180014964  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014969  mov     ebx, eax
0x18001496b  test    eax, eax
0x18001496d  jns     short loc_180014990
0x18001496f  mov     rcx, cs:WPP_GLOBAL_Control
0x180014976  cmp     rcx, r12
0x180014979  jz      loc_180014AC7
0x18001497f  test    byte ptr [rcx+1Ch], 2
0x180014983  jz      loc_180014AC7
0x180014989  mov     edx, 1Ch
0x18001498e  jmp     short loc_180014939
0x180014990  mov     rcx, [rbp+var_48]
0x180014994  mov     rax, [rcx]
0x180014997  lea     r8, [rbp+psz2]
0x18001499b  xor     edx, edx
0x18001499d  mov     rax, [rax+20h]
0x1800149a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149a6  mov     ebx, eax
0x1800149a8  test    eax, eax
0x1800149aa  jns     short loc_1800149D0
0x1800149ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800149b3  cmp     rcx, r12
0x1800149b6  jz      loc_180014AC7
0x1800149bc  test    byte ptr [rcx+1Ch], 2
0x1800149c0  jz      loc_180014AC7
0x1800149c6  mov     edx, 1Dh
0x1800149cb  jmp     loc_180014895
0x1800149d0  mov     eax, 1Fh
0x1800149d5  cmp     ax, word ptr [rbp+psz2]
0x1800149d9  jz      short loc_1800149E5
0x1800149db  mov     ebx, 8000FFFFh
0x1800149e0  jmp     loc_180014AC7
0x1800149e5  mov     rdx, [rbp+psz2+8]; psz2
0x1800149e9  test    rdx, rdx
0x1800149ec  jz      short loc_1800149DB
0x1800149ee  lea     rcx, String; psz1
0x1800149f5  call    cs:__imp_StrCmpIW
0x1800149fb  test    eax, eax
0x1800149fd  jz      short loc_1800149DB
0x1800149ff  cmp     r14d, 7FFFFFFFh
0x180014a06  jbe     short loc_180014A13
0x180014a08  mov     ebx, 80070057h
0x180014a0d  mov     [rdi], r15w
0x180014a11  jmp     short loc_180014A67
0x180014a13  mov     eax, 7FFFFFFEh
0x180014a18  mov     rcx, [rbp+psz2+8]
0x180014a1c  mov     rdx, r14
0x180014a1f  mov     r8, rdi
0x180014a22  test    rax, rax
0x180014a25  jz      short loc_180014A46
0x180014a27  movzx   r9d, word ptr [rcx]
0x180014a2b  test    r9w, r9w
0x180014a2f  jz      short loc_180014A46
0x180014a31  add     rcx, 2
0x180014a35  mov     [r8], r9w
0x180014a39  add     r8, 2
0x180014a3d  dec     rax
0x180014a40  sub     rdx, 1
0x180014a44  jnz     short loc_180014A22
0x180014a46  mov     rax, rdx
0x180014a49  neg     rax
0x180014a4c  sbb     ebx, ebx
0x180014a4e  not     ebx
0x180014a50  lea     rcx, [r8-2]
0x180014a54  test    rdx, rdx
0x180014a57  cmovnz  rcx, r8
0x180014a5b  mov     [rcx], r15w
0x180014a5f  and     ebx, 8007007Ah
0x180014a65  jns     short loc_180014A9C
0x180014a67  mov     r8d, ebx
0x180014a6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014a71  cmp     rcx, r12
0x180014a74  jz      short loc_180014AC7
0x180014a76  test    byte ptr [rcx+1Ch], 2
0x180014a7a  jz      short loc_180014AC7
0x180014a7c  mov     edx, 1Eh
0x180014a81  mov     [rsp+78h+var_50], ebx
0x180014a85  mov     dword ptr [rsp+78h+ppv], r14d
0x180014a8a  mov     r9, [rbp+psz2+8]
0x180014a8e  mov     r8, r13
0x180014a91  mov     rcx, [rcx+10h]
0x180014a95  call    WPP_SF_Sdd
0x180014a9a  jmp     short loc_180014AC7
0x180014a9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180014aa3  cmp     rcx, r12
0x180014aa6  jz      short loc_180014AC7
0x180014aa8  test    byte ptr [rcx+1Ch], 40h
0x180014aac  jz      short loc_180014AC7
0x180014aae  mov     edx, 1Fh
0x180014ab3  mov     [rsp+78h+ppv], rdi
0x180014ab8  mov     r9, rsi
0x180014abb  mov     r8, r13
0x180014abe  mov     rcx, [rcx+10h]
0x180014ac2  call    WPP_SF_SS
0x180014ac7  lea     rcx, [rbp+psz2]; pvar
0x180014acb  call    cs:__imp_PropVariantClear
0x180014ad1  test    ebx, ebx
0x180014ad3  jns     short loc_180014AFC
0x180014ad5  mov     rcx, cs:WPP_GLOBAL_Control
0x180014adc  cmp     rcx, r12
0x180014adf  jz      short loc_180014AFC
0x180014ae1  test    byte ptr [rcx+1Ch], 2
0x180014ae5  jz      short loc_180014AFC
0x180014ae7  mov     edx, 20h ; ' '
0x180014aec  mov     r9d, ebx
0x180014aef  mov     r8, r13
0x180014af2  mov     rcx, [rcx+10h]
0x180014af6  call    WPP_SF_d
0x180014afb  nop
0x180014afc  mov     rcx, [rbp+arg_0]
0x180014b00  test    rcx, rcx
0x180014b03  jz      short loc_180014B12
0x180014b05  mov     rax, [rcx]
0x180014b08  mov     rax, [rax+10h]
0x180014b0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b11  nop
0x180014b12  mov     rcx, [rbp+var_48]
0x180014b16  test    rcx, rcx
0x180014b19  jz      short loc_180014B28
0x180014b1b  mov     rax, [rcx]
0x180014b1e  mov     rax, [rax+10h]
0x180014b22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b27  nop
0x180014b28  mov     rcx, [rbp+var_40]
0x180014b2c  test    rcx, rcx
0x180014b2f  jz      short loc_180014B3E
0x180014b31  mov     rax, [rcx]
0x180014b34  mov     rax, [rax+10h]
0x180014b38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b3d  nop
0x180014b3e  mov     eax, ebx
0x180014b40  add     rsp, 78h
0x180014b44  pop     r15
0x180014b46  pop     r14
0x180014b48  pop     r13
0x180014b4a  pop     r12
0x180014b4c  pop     rdi
0x180014b4d  pop     rsi
0x180014b4e  pop     rbx
0x180014b4f  pop     rbp
0x180014b50  retn
```
