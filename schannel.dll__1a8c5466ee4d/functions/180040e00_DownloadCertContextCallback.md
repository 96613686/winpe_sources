# DownloadCertContextCallback

- ea: `0x180040e00`
- end: `0x18004112c`
- name: `DownloadCertContextCallback`
- size: `812`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180021da8`
- `0x180021e64`
- `0x180025c38`
- `0x180040e00`
- `0x180057c8c`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041041`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041041`
- `CRYPT32!CertOpenStore` at `0x180040ed1`
- `CRYPT32!CertOpenStore` at `0x180040ed1`
- `CRYPT32!CertCloseStore` at `0x180040f53`
- `CRYPT32!CertCloseStore` at `0x180040fe9`
- `CRYPT32!CertCloseStore` at `0x18004108c`
- `CRYPT32!CertCloseStore` at `0x180040f53`
- `CRYPT32!CertCloseStore` at `0x180040fe9`
- `CRYPT32!CertCloseStore` at `0x18004108c`
- `CRYPT32!CertAddSerializedElementToStore` at `0x180040f40`
- `CRYPT32!CertAddSerializedElementToStore` at `0x180040f40`

## pseudocode

```c
__int64 __fastcall DownloadCertContextCallback(__int64 a1, __int64 a2, unsigned int *a3, __int64 a4)
{
  unsigned __int64 v6; // rbp
  const BYTE *v7; // r15
  __int64 v8; // rcx
  HCERTSTORE v9; // r12
  unsigned int v10; // ebp
  __int64 v11; // r8
  int v12; // ebp
  void *v13; // rcx
  CCipherMill *v15; // rcx
  __int64 v16; // rdx
  void *ppvContext; // [rsp+40h] [rbp-48h] BYREF
  __int128 pvPara; // [rsp+48h] [rbp-40h] BYREF

  ppvContext = 0;
  if ( !(unsigned int)SchannelInit(1) )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 5) == 0 )
      return 2148074244LL;
    v16 = 51;
    goto LABEL_44;
  }
  if ( !a3 || !a4 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 5) == 0 )
      return 2148074244LL;
    v16 = 52;
LABEL_44:
    WPP_SF_dd(*((_QWORD *)v15 + 2), v16, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids, 2148074244LL, -2146893052);
    return 2148074244LL;
  }
  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids);
  v6 = *a3;
  pvPara = 0;
  if ( (unsigned int)v6 < 4 )
  {
    v12 = -2146893043;
  }
  else
  {
    v7 = (const BYTE *)*((_QWORD *)a3 + 1);
    v8 = *(unsigned int *)v7;
    LODWORD(pvPara) = v8;
    *((_QWORD *)&pvPara + 1) = v7 + 4;
    if ( (unsigned int)v8 >= 0xFFFFFFFA )
    {
      v12 = -2146893043;
    }
    else if ( v6 < v8 + 4 )
    {
      v12 = -2146893043;
    }
    else
    {
      v9 = CertOpenStore((LPCSTR)6, 1u, 0, 4u, &pvPara);
      if ( !v9 )
      {
LABEL_25:
        v12 = -2146893043;
        goto LABEL_16;
      }
      v10 = v6 - pvPara - 4;
      if ( v10 < 4 || (v11 = *(unsigned int *)&v7[(unsigned int)pvPara + 4], (unsigned int)v11 >= 0xFFFFFFFA) )
      {
LABEL_24:
        CertCloseStore(v9, 0);
        goto LABEL_25;
      }
      if ( v10 >= (unsigned __int64)(v11 + 4) )
      {
        if ( CertAddSerializedElementToStore(
               v9,
               &v7[(unsigned int)pvPara + 8],
               v11,
               2u,
               0,
               2u,
               0,
               (const void **)&ppvContext) )
        {
          CertCloseStore(v9, 0);
          v12 = 0;
          goto LABEL_16;
        }
        if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_e44b5bfab80d3987b415a3d047a1d288_Traceguids);
        goto LABEL_24;
      }
      CertCloseStore(v9, 0);
      v12 = -2146893043;
    }
  }
LABEL_16:
  *(_DWORD *)a4 = *a3;
  v13 = (void *)*((_QWORD *)a3 + 1);
  if ( LsaTable )
    (*(void (__fastcall **)(void *))(LsaTable + 48))(v13);
  else
    LocalFree(v13);
  *((_QWORD *)a3 + 1) = 0;
  *(_QWORD *)a3 = 0;
  if ( v12 < 0 )
  {
    *(_QWORD *)a4 = 0;
    *(_QWORD *)(a4 + 8) = 0;
    if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        54,
        WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids,
        (unsigned int)v12);
    return (unsigned int)v12;
  }
  else
  {
    **(_QWORD **)(a4 + 8) = ppvContext;
    if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids);
    return 0;
  }
}

```

## disassembly

```asm
0x180040e00  push    rbx
0x180040e02  push    rsi
0x180040e03  push    r13
0x180040e05  push    r14
0x180040e07  sub     rsp, 68h
0x180040e0b  xor     r13d, r13d
0x180040e0e  mov     ecx, 1; int
0x180040e13  mov     [rsp+88h+var_48], r13
0x180040e18  mov     rsi, r9
0x180040e1b  mov     rbx, r8
0x180040e1e  call    ?SchannelInit@@YAHH@Z; SchannelInit(int)
0x180040e23  test    eax, eax
0x180040e25  jz      loc_18004101E
0x180040e2b  test    rbx, rbx
0x180040e2e  jz      loc_180041101
0x180040e34  test    rsi, rsi
0x180040e37  jz      loc_180041101
0x180040e3d  mov     [rsp+88h+arg_0], rbp
0x180040e45  mov     [rsp+88h+arg_8], rdi
0x180040e4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180040e54  lea     r14, WPP_GLOBAL_Control
0x180040e5b  cmp     rcx, r14
0x180040e5e  jz      short loc_180040E6A
0x180040e60  test    byte ptr [rcx+1Ch], 4
0x180040e64  jnz     loc_18004105C
0x180040e6a  mov     ebp, [rbx]
0x180040e6c  xorps   xmm0, xmm0
0x180040e6f  movups  [rsp+88h+var_40], xmm0
0x180040e74  cmp     ebp, 4
0x180040e77  jb      loc_180041076
0x180040e7d  mov     [rsp+88h+var_28], r15
0x180040e82  mov     r15, [rbx+8]
0x180040e86  mov     ecx, [r15]
0x180040e89  lea     rax, [r15+4]
0x180040e8d  mov     dword ptr [rsp+88h+var_40], ecx
0x180040e91  mov     qword ptr [rsp+88h+var_40+8], rax
0x180040e96  cmp     ecx, 0FFFFFFFAh
0x180040e99  jnb     loc_180041080
0x180040e9f  add     rcx, 4
0x180040ea3  cmp     rbp, rcx
0x180040ea6  jb      loc_180040FF9
0x180040eac  lea     rax, [rsp+88h+var_40]
0x180040eb1  mov     [rsp+88h+arg_10], r12
0x180040eb9  mov     r9d, 4; dwFlags
0x180040ebf  mov     [rsp+88h+pvPara], rax; pvPara
0x180040ec4  xor     r8d, r8d; hCryptProv
0x180040ec7  mov     edx, 1; dwEncodingType
0x180040ecc  mov     ecx, 6; lpszStoreProvider
0x180040ed1  call    cs:__imp_CertOpenStore
0x180040ed7  mov     r12, rax
0x180040eda  test    rax, rax
0x180040edd  jz      loc_180040FEF
0x180040ee3  mov     eax, dword ptr [rsp+88h+var_40]
0x180040ee7  sub     ebp, eax
0x180040ee9  add     ebp, 0FFFFFFFCh
0x180040eec  cmp     ebp, 4
0x180040eef  jb      loc_180040FE4
0x180040ef5  mov     r8d, [r15+rax+4]; cbElement
0x180040efa  lea     rdx, [r15+rax]
0x180040efe  cmp     r8d, 0FFFFFFFAh
0x180040f02  jnb     loc_180040FE4
0x180040f08  lea     rcx, [r8+4]
0x180040f0c  mov     eax, ebp
0x180040f0e  cmp     rax, rcx
0x180040f11  mov     rcx, r12; hCertStore
0x180040f14  jb      loc_18004108A
0x180040f1a  lea     rax, [rsp+88h+var_48]
0x180040f1f  add     rdx, 8; pbElement
0x180040f23  mov     [rsp+88h+ppvContext], rax; ppvContext
0x180040f28  mov     r9d, 2; dwAddDisposition
0x180040f2e  mov     [rsp+88h+pdwContextType], r13; pdwContextType
0x180040f33  mov     [rsp+88h+dwContextTypeFlags], 2; dwContextTypeFlags
0x180040f3b  mov     dword ptr [rsp+88h+pvPara], r13d; dwFlags
0x180040f40  call    cs:__imp_CertAddSerializedElementToStore
0x180040f46  test    eax, eax
0x180040f48  jz      loc_180040FD4
0x180040f4e  xor     edx, edx; dwFlags
0x180040f50  mov     rcx, r12; hCertStore
0x180040f53  call    cs:__imp_CertCloseStore
0x180040f59  mov     ebp, r13d
0x180040f5c  mov     r12, [rsp+88h+arg_10]
0x180040f64  mov     r15, [rsp+88h+var_28]
0x180040f69  mov     eax, [rbx]
0x180040f6b  mov     [rsi], eax
0x180040f6d  mov     rax, cs:LsaTable
0x180040f74  mov     rcx, [rbx+8]; hMem
0x180040f78  test    rax, rax
0x180040f7b  jz      loc_180041041
0x180040f81  mov     rax, [rax+30h]
0x180040f85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040f8a  mov     rdi, [rsp+88h+arg_8]
0x180040f92  mov     [rbx+8], r13
0x180040f96  mov     [rbx], r13
0x180040f99  test    ebp, ebp
0x180040f9b  js      short loc_180041003
0x180040f9d  mov     rcx, [rsi+8]
0x180040fa1  mov     rax, [rsp+88h+var_48]
0x180040fa6  mov     [rcx], rax
0x180040fa9  mov     rcx, cs:WPP_GLOBAL_Control
0x180040fb0  cmp     rcx, r14
0x180040fb3  jz      short loc_180040FBF
0x180040fb5  test    byte ptr [rcx+1Ch], 4
0x180040fb9  jnz     loc_1800410E7
0x180040fbf  xor     eax, eax
0x180040fc1  mov     rbp, [rsp+88h+arg_0]
0x180040fc9  add     rsp, 68h
0x180040fcd  pop     r14
0x180040fcf  pop     r13
0x180040fd1  pop     rsi
0x180040fd2  pop     rbx
0x180040fd3  retn
0x180040fd4  mov     rcx, cs:WPP_GLOBAL_Control
0x180040fdb  cmp     rcx, r14
0x180040fde  jnz     loc_18004109C
0x180040fe4  xor     edx, edx; dwFlags
0x180040fe6  mov     rcx, r12; hCertStore
0x180040fe9  call    cs:__imp_CertCloseStore
0x180040fef  mov     ebp, 8009030Dh
0x180040ff4  jmp     loc_180040F5C
0x180040ff9  mov     ebp, 8009030Dh
0x180040ffe  jmp     loc_180040F64
0x180041003  mov     [rsi], r13
0x180041006  mov     [rsi+8], r13
0x18004100a  mov     rcx, cs:WPP_GLOBAL_Control
0x180041011  cmp     rcx, r14
0x180041014  jnz     loc_1800410C0
0x18004101a  mov     eax, ebp
0x18004101c  jmp     short loc_180040FC1
0x18004101e  mov     rcx, cs:WPP_GLOBAL_Control
0x180041025  lea     r14, WPP_GLOBAL_Control
0x18004102c  cmp     rcx, r14
0x18004102f  jnz     short loc_18004104C
0x180041031  mov     eax, 80090304h
0x180041036  add     rsp, 68h
0x18004103a  pop     r14
0x18004103c  pop     r13
0x18004103e  pop     rsi
0x18004103f  pop     rbx
0x180041040  retn
0x180041041  call    cs:__imp_LocalFree
0x180041047  jmp     loc_180040F8A
0x18004104c  test    byte ptr [rcx+1Ch], 5
0x180041050  jz      short loc_180041031
0x180041052  mov     edx, 33h ; '3'
0x180041057  jmp     loc_18008FCE0
0x18004105c  mov     rcx, [rcx+10h]
0x180041060  lea     r8, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids
0x180041067  mov     edx, 35h ; '5'
0x18004106c  call    WPP_SF_
0x180041071  jmp     loc_180040E6A
0x180041076  mov     ebp, 8009030Dh
0x18004107b  jmp     loc_180040F69
0x180041080  mov     ebp, 8009030Dh
0x180041085  jmp     loc_180040F64
0x18004108a  xor     edx, edx; dwFlags
0x18004108c  call    cs:__imp_CertCloseStore
0x180041092  mov     ebp, 8009030Dh
0x180041097  jmp     loc_180040F5C
0x18004109c  test    byte ptr [rcx+1Ch], 2
0x1800410a0  jz      loc_180040FE4
0x1800410a6  mov     rcx, [rcx+10h]
0x1800410aa  lea     r8, WPP_e44b5bfab80d3987b415a3d047a1d288_Traceguids
0x1800410b1  mov     edx, 31h ; '1'
0x1800410b6  call    WPP_SF_
0x1800410bb  jmp     loc_180040FE4
0x1800410c0  test    byte ptr [rcx+1Ch], 1
0x1800410c4  jz      loc_18004101A
0x1800410ca  mov     rcx, [rcx+10h]
0x1800410ce  lea     r8, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids
0x1800410d5  mov     edx, 36h ; '6'
0x1800410da  mov     r9d, ebp
0x1800410dd  call    WPP_SF_d
0x1800410e2  jmp     loc_18004101A
0x1800410e7  mov     rcx, [rcx+10h]
0x1800410eb  lea     r8, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids
0x1800410f2  mov     edx, 37h ; '7'
0x1800410f7  call    WPP_SF_
0x1800410fc  jmp     loc_180040FBF
0x180041101  mov     rcx, cs:WPP_GLOBAL_Control
0x180041108  lea     r14, WPP_GLOBAL_Control
0x18004110f  cmp     rcx, r14
0x180041112  jz      loc_180041031
0x180041118  test    byte ptr [rcx+1Ch], 5
0x18004111c  jz      loc_180041031
0x180041122  mov     edx, 34h ; '4'
0x180041127  jmp     loc_18008FCE0
0x18008fce0  mov     rcx, [rcx+10h]
0x18008fce4  lea     r8, WPP_afafbaf638ed37b28ae3c1cec484c558_Traceguids
0x18008fceb  mov     r9d, 80090304h
0x18008fcf1  mov     dword ptr [rsp+88h+pvPara], 80090304h
0x18008fcf9  call    WPP_SF_dd
0x18008fcfe  nop
0x18008fcff  jmp     loc_180041031
```
