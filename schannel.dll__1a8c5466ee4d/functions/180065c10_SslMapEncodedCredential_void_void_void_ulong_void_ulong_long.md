# SslMapEncodedCredential(void * *,void *,void *,ulong,void * *,ulong *,long *)

- ea: `0x180065c10`
- end: `0x180065fce`
- name: `?SslMapEncodedCredential@@YAJPEAPEAXPEAX1K0PEAKPEAJ@Z`
- size: `958`
- prototype: `__int64 __fastcall(void **, void *, void *, unsigned int, HANDLE hObject, unsigned int *, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180068f60`

## callees

- `0x180014240`
- `0x180021da8`
- `0x180021eb0`
- `0x180057c8c`
- `0x180065c10`
- `0x180065fd4`
- `0x1800680c8`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065d60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065d60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180065f5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180065f5d`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180065f73`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180065f73`
- `CRYPT32!CertFreeCertificateContext` at `0x180065f81`
- `CRYPT32!CertFreeCertificateContext` at `0x180065f81`
- `CRYPT32!CertCreateCertificateContext` at `0x180065d39`
- `CRYPT32!CertCreateCertificateContext` at `0x180065d39`

## pseudocode

```c
__int64 __fastcall SslMapEncodedCredential(
        void **a1,
        unsigned int *a2,
        void *a3,
        unsigned int a4,
        _QWORD *hObject,
        unsigned int *a6,
        int *a7)
{
  const CERT_CONTEXT *CertificateContext; // r15
  void *v9; // rsi
  _QWORD *v11; // r14
  int v12; // ebx
  unsigned int *v13; // r12
  BYTE *v14; // rax
  BYTE *v15; // r13
  __int64 v16; // r9
  __int64 v17; // rdx
  int v18; // eax
  CCipherMill *v19; // rcx
  __int64 v20; // rdx
  void **v21; // rcx
  void *v22; // r8
  DWORD LastError; // eax
  __int64 v24; // rdx
  __int64 v25; // r8
  unsigned int v26; // eax
  int *v27; // rdi
  __int64 v28; // r9
  __int64 (*v29)(void); // rax
  unsigned int v30; // edi
  int v31; // eax
  void *v33; // [rsp+40h] [rbp-30h] BYREF
  _DWORD v34[4]; // [rsp+48h] [rbp-28h] BYREF
  const CERT_CONTEXT *v35; // [rsp+58h] [rbp-18h]
  unsigned int v36; // [rsp+60h] [rbp-10h]
  int v37; // [rsp+64h] [rbp-Ch]
  __int64 v38; // [rsp+B0h] [rbp+40h] BYREF
  unsigned int v39; // [rsp+C0h] [rbp+50h] BYREF
  int v40; // [rsp+C4h] [rbp+54h]

  v40 = HIDWORD(a3);
  CertificateContext = 0;
  v34[3] = 0;
  v9 = 0;
  v37 = 0;
  v33 = 0;
  v39 = 0;
  v38 = 0;
  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_e1738149d20f31dfe7380947af7f2303_Traceguids);
  v11 = hObject;
  if ( !hObject || (v13 = a6, *hObject = 0, *v13 = 0, a4 < 0x28) || a2[1] != 40 )
  {
    v12 = -1073741811;
    goto LABEL_47;
  }
  v14 = (BYTE *)SPExternalAlloc(a2[4]);
  v15 = v14;
  if ( !v14 )
  {
    v12 = -1073741801;
    goto LABEL_47;
  }
  v16 = *((_QWORD *)a2 + 3);
  v17 = a2[4];
  hObject = 0;
  v18 = (*(__int64 (__fastcall **)(_QWORD, __int64, BYTE *, __int64))(LsaTable + 80))(0, v17, v14, v16);
  v12 = v18;
  if ( v18 < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
      goto LABEL_41;
    v20 = 66;
    goto LABEL_15;
  }
  CertificateContext = CertCreateCertificateContext(a2[3], v15, a2[4]);
  if ( !CertificateContext )
  {
    if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_l(*((_QWORD *)WPP_GLOBAL_Control + 2), v24, v25, LastError);
    }
    v12 = -1073741811;
    goto LABEL_41;
  }
  v34[2] = a2[2];
  v26 = a2[8];
  v27 = a7;
  v36 = v26;
  v34[0] = 6;
  v34[1] = 32;
  v35 = CertificateContext;
  v12 = SslMapExternalCredential(v21, v34, v22, 0x20u, &v33, &v39, a7);
  if ( v12 < 0 )
  {
LABEL_40:
    v9 = v33;
    goto LABEL_41;
  }
  v28 = (unsigned int)*v27;
  if ( (int)v28 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_e1738149d20f31dfe7380947af7f2303_Traceguids, v28);
    goto LABEL_40;
  }
  v9 = v33;
  v29 = *(__int64 (**)(void))(LsaTable + 440);
  hObject = (_QWORD *)*((_QWORD *)v33 + 1);
  v18 = v29();
  v12 = v18;
  if ( v18 < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CCipherMill *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
      goto LABEL_41;
    v20 = 69;
    goto LABEL_15;
  }
  v30 = v39;
  v18 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(LsaTable + 56))(0, v39, &v38);
  v12 = v18;
  if ( v18 >= 0 )
  {
    v31 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, void *))(LsaTable + 72))(0, v30, v38, v9);
    v12 = v31;
    if ( v31 >= 0 )
    {
      *v11 = v38;
      *v13 = v30;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          71,
          WPP_e1738149d20f31dfe7380947af7f2303_Traceguids,
          (unsigned int)v31);
      }
      (*(void (__fastcall **)(_QWORD, __int64))(LsaTable + 64))(0, v38);
    }
    goto LABEL_41;
  }
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    v20 = 70;
LABEL_15:
    WPP_SF_d(*((_QWORD *)v19 + 2), v20, WPP_e1738149d20f31dfe7380947af7f2303_Traceguids, (unsigned int)v18);
  }
LABEL_41:
  SPExternalFree(v15);
  if ( hObject )
    CloseHandle(hObject);
  if ( v9 )
    VirtualFree(v9, 0, 0x8000u);
  if ( CertificateContext )
    CertFreeCertificateContext(CertificateContext);
LABEL_47:
  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      72,
      WPP_e1738149d20f31dfe7380947af7f2303_Traceguids,
      (unsigned int)v12);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180065c10  mov     [rsp-38h+arg_8], rbx
0x180065c15  mov     qword ptr [rsp-38h+arg_10], r8
0x180065c1a  mov     [rsp-38h+arg_0], rcx
0x180065c1f  push    rbp
0x180065c20  push    rsi
0x180065c21  push    rdi
0x180065c22  push    r12
0x180065c24  push    r13
0x180065c26  push    r14
0x180065c28  push    r15
0x180065c2a  mov     rbp, rsp
0x180065c2d  sub     rsp, 70h
0x180065c31  xor     r15d, r15d
0x180065c34  mov     ebx, r9d
0x180065c37  mov     [rbp+var_1C], r15d
0x180065c3b  mov     esi, r15d
0x180065c3e  mov     [rbp+var_C], r15d
0x180065c42  mov     rdi, rdx
0x180065c45  mov     [rbp+var_30], r15
0x180065c49  mov     [rbp+arg_10], r15d
0x180065c4d  mov     [rbp+arg_0], r15
0x180065c51  mov     rcx, cs:WPP_GLOBAL_Control
0x180065c58  lea     rax, WPP_GLOBAL_Control
0x180065c5f  cmp     rcx, rax
0x180065c62  jz      short loc_180065C81
0x180065c64  test    dword ptr [rcx+1Ch], 100h
0x180065c6b  jz      short loc_180065C81
0x180065c6d  mov     rcx, [rcx+10h]
0x180065c71  lea     edx, [r15+41h]
0x180065c75  lea     r8, WPP_e1738149d20f31dfe7380947af7f2303_Traceguids
0x180065c7c  call    WPP_SF_
0x180065c81  mov     r14, [rbp+hObject]
0x180065c85  test    r14, r14
0x180065c88  jnz     short loc_180065C9B
0x180065c8a  mov     ebx, 0C000000Dh
0x180065c8f  lea     rdi, WPP_GLOBAL_Control
0x180065c96  jmp     loc_180065F87
0x180065c9b  mov     r12, [rbp+arg_28]
0x180065c9f  mov     [r14], r15
0x180065ca2  mov     [r12], r15d
0x180065ca6  cmp     ebx, 28h ; '('
0x180065ca9  jb      short loc_180065C8A
0x180065cab  cmp     dword ptr [rdi+4], 28h ; '('
0x180065caf  jnz     short loc_180065C8A
0x180065cb1  mov     ecx, [rdi+10h]; uBytes
0x180065cb4  call    ?SPExternalAlloc@@YAPEAXK@Z; SPExternalAlloc(ulong)
0x180065cb9  mov     r13, rax
0x180065cbc  test    rax, rax
0x180065cbf  jnz     short loc_180065CC8
0x180065cc1  mov     ebx, 0C0000017h
0x180065cc6  jmp     short loc_180065C8F
0x180065cc8  mov     rax, cs:LsaTable
0x180065ccf  mov     r8, r13
0x180065cd2  mov     r9, [rdi+18h]
0x180065cd6  xor     ecx, ecx
0x180065cd8  mov     edx, [rdi+10h]
0x180065cdb  mov     [rbp+hObject], r15
0x180065cdf  mov     rax, [rax+50h]
0x180065ce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065ce8  mov     ebx, eax
0x180065cea  test    eax, eax
0x180065cec  jns     short loc_180065D2F
0x180065cee  mov     rcx, cs:WPP_GLOBAL_Control
0x180065cf5  lea     rdi, WPP_GLOBAL_Control
0x180065cfc  cmp     rcx, rdi
0x180065cff  jz      loc_180065F49
0x180065d05  test    dword ptr [rcx+1Ch], 100h
0x180065d0c  jz      loc_180065F49
0x180065d12  mov     edx, 42h ; 'B'
0x180065d17  mov     rcx, [rcx+10h]
0x180065d1b  lea     r8, WPP_e1738149d20f31dfe7380947af7f2303_Traceguids
0x180065d22  mov     r9d, eax
0x180065d25  call    WPP_SF_d
0x180065d2a  jmp     loc_180065F49
0x180065d2f  mov     r8d, [rdi+10h]; cbCertEncoded
0x180065d33  mov     rdx, r13; pbCertEncoded
0x180065d36  mov     ecx, [rdi+0Ch]; dwCertEncodingType
0x180065d39  call    cs:__imp_CertCreateCertificateContext
0x180065d3f  mov     r15, rax
0x180065d42  test    rax, rax
0x180065d45  jnz     short loc_180065D83
0x180065d47  mov     rcx, cs:WPP_GLOBAL_Control
0x180065d4e  lea     rdi, WPP_GLOBAL_Control
0x180065d55  cmp     rcx, rdi
0x180065d58  jz      short loc_180065D79
0x180065d5a  test    byte ptr [rcx+1Ch], 1
0x180065d5e  jz      short loc_180065D79
0x180065d60  call    cs:__imp_GetLastError
0x180065d66  mov     rcx, cs:WPP_GLOBAL_Control
0x180065d6d  mov     r9d, eax
0x180065d70  mov     rcx, [rcx+10h]
0x180065d74  call    WPP_SF_l
0x180065d79  mov     ebx, 0C000000Dh
0x180065d7e  jmp     loc_180065F49
0x180065d83  mov     eax, [rdi+8]
0x180065d86  lea     rdx, [rbp+var_28]; void *
0x180065d8a  mov     [rbp+var_20], eax
0x180065d8d  mov     r9d, 20h ; ' '; unsigned int
0x180065d93  mov     eax, [rdi+20h]
0x180065d96  mov     rdi, [rbp+arg_30]
0x180065d9a  mov     [rbp+var_10], eax
0x180065d9d  lea     rax, [rbp+arg_10]
0x180065da1  mov     [rsp+70h+var_40], rdi; int *
0x180065da6  mov     [rsp+70h+var_48], rax; unsigned int *
0x180065dab  lea     rax, [rbp+var_30]
0x180065daf  mov     [rsp+70h+var_50], rax; void **
0x180065db4  mov     [rbp+var_28], 6
0x180065dbb  mov     [rbp+var_24], r9d
0x180065dbf  mov     [rbp+var_18], r15
0x180065dc3  call    ?SslMapExternalCredential@@YAJPEAPEAXPEAX1K0PEAKPEAJ@Z; SslMapExternalCredential(void * *,void *,void *,ulong,void * *,ulong *,long *)
0x180065dc8  mov     ebx, eax
0x180065dca  test    eax, eax
0x180065dcc  js      loc_180065F3E
0x180065dd2  mov     r9d, [rdi]
0x180065dd5  test    r9d, r9d
0x180065dd8  jns     short loc_180065E18
0x180065dda  mov     rcx, cs:WPP_GLOBAL_Control
0x180065de1  lea     rdi, WPP_GLOBAL_Control
0x180065de8  cmp     rcx, rdi
0x180065deb  jz      loc_180065F45
0x180065df1  test    dword ptr [rcx+1Ch], 100h
0x180065df8  jz      loc_180065F45
0x180065dfe  mov     rcx, [rcx+10h]
0x180065e02  lea     r8, WPP_e1738149d20f31dfe7380947af7f2303_Traceguids
0x180065e09  mov     edx, 44h ; 'D'
0x180065e0e  call    WPP_SF_d
0x180065e13  jmp     loc_180065F45
0x180065e18  mov     rax, cs:LsaTable
0x180065e1f  mov     rsi, [rbp+var_30]
0x180065e23  mov     rax, [rax+1B8h]
0x180065e2a  lea     rdx, [rsi+8]
0x180065e2e  mov     rcx, [rdx]
0x180065e31  mov     [rbp+hObject], rcx
0x180065e35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065e3a  mov     ebx, eax
0x180065e3c  test    eax, eax
0x180065e3e  jns     short loc_180065E6E
0x180065e40  mov     rcx, cs:WPP_GLOBAL_Control
0x180065e47  lea     rdi, WPP_GLOBAL_Control
0x180065e4e  cmp     rcx, rdi
0x180065e51  jz      loc_180065F49
0x180065e57  test    dword ptr [rcx+1Ch], 100h
0x180065e5e  jz      loc_180065F49
0x180065e64  mov     edx, 45h ; 'E'
0x180065e69  jmp     loc_180065D17
0x180065e6e  mov     rax, cs:LsaTable
0x180065e75  lea     r8, [rbp+arg_0]
0x180065e79  mov     edi, [rbp+arg_10]
0x180065e7c  xor     ecx, ecx
0x180065e7e  mov     edx, edi
0x180065e80  mov     rax, [rax+38h]
0x180065e84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065e89  mov     ebx, eax
0x180065e8b  test    eax, eax
0x180065e8d  jns     short loc_180065EBD
0x180065e8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180065e96  lea     rdi, WPP_GLOBAL_Control
0x180065e9d  cmp     rcx, rdi
0x180065ea0  jz      loc_180065F49
0x180065ea6  test    dword ptr [rcx+1Ch], 100h
0x180065ead  jz      loc_180065F49
0x180065eb3  mov     edx, 46h ; 'F'
0x180065eb8  jmp     loc_180065D17
0x180065ebd  mov     rax, cs:LsaTable
0x180065ec4  mov     r9, rsi
0x180065ec7  mov     r8, [rbp+arg_0]
0x180065ecb  mov     edx, edi
0x180065ecd  xor     ecx, ecx
0x180065ecf  mov     rax, [rax+48h]
0x180065ed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065ed8  mov     ebx, eax
0x180065eda  test    eax, eax
0x180065edc  jns     short loc_180065F2A
0x180065ede  mov     rcx, cs:WPP_GLOBAL_Control
0x180065ee5  lea     rdi, WPP_GLOBAL_Control
0x180065eec  cmp     rcx, rdi
0x180065eef  jz      short loc_180065F12
0x180065ef1  test    dword ptr [rcx+1Ch], 100h
0x180065ef8  jz      short loc_180065F12
0x180065efa  mov     rcx, [rcx+10h]
0x180065efe  lea     r8, WPP_e1738149d20f31dfe7380947af7f2303_Traceguids
0x180065f05  mov     edx, 47h ; 'G'
0x180065f0a  mov     r9d, eax
0x180065f0d  call    WPP_SF_d
0x180065f12  mov     rax, cs:LsaTable
0x180065f19  xor     ecx, ecx
0x180065f1b  mov     rdx, [rbp+arg_0]
0x180065f1f  mov     rax, [rax+40h]
0x180065f23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065f28  jmp     short loc_180065F49
0x180065f2a  mov     rax, [rbp+arg_0]
0x180065f2e  mov     [r14], rax
0x180065f31  mov     [r12], edi
0x180065f35  lea     rdi, WPP_GLOBAL_Control
0x180065f3c  jmp     short loc_180065F49
0x180065f3e  lea     rdi, WPP_GLOBAL_Control
0x180065f45  mov     rsi, [rbp+var_30]
0x180065f49  mov     rcx, r13; void *
0x180065f4c  call    ?SPExternalFree@@YAXPEAX@Z; SPExternalFree(void *)
0x180065f51  mov     rax, [rbp+hObject]
0x180065f55  test    rax, rax
0x180065f58  jz      short loc_180065F63
0x180065f5a  mov     rcx, rax; hObject
0x180065f5d  call    cs:__imp_CloseHandle
0x180065f63  test    rsi, rsi
0x180065f66  jz      short loc_180065F79
0x180065f68  xor     edx, edx; dwSize
0x180065f6a  mov     r8d, 8000h; dwFreeType
0x180065f70  mov     rcx, rsi; lpAddress
0x180065f73  call    cs:__imp_VirtualFree
0x180065f79  test    r15, r15
0x180065f7c  jz      short loc_180065F87
0x180065f7e  mov     rcx, r15; pCertContext
0x180065f81  call    cs:__imp_CertFreeCertificateContext
0x180065f87  mov     rcx, cs:WPP_GLOBAL_Control
0x180065f8e  cmp     rcx, rdi
0x180065f91  jz      short loc_180065FB4
0x180065f93  test    dword ptr [rcx+1Ch], 100h
0x180065f9a  jz      short loc_180065FB4
0x180065f9c  mov     rcx, [rcx+10h]
0x180065fa0  lea     r8, WPP_e1738149d20f31dfe7380947af7f2303_Traceguids
0x180065fa7  mov     edx, 48h ; 'H'
0x180065fac  mov     r9d, ebx
0x180065faf  call    WPP_SF_d
0x180065fb4  mov     eax, ebx
0x180065fb6  mov     rbx, [rsp+70h+arg_8]
0x180065fbe  add     rsp, 70h
0x180065fc2  pop     r15
0x180065fc4  pop     r14
0x180065fc6  pop     r13
0x180065fc8  pop     r12
0x180065fca  pop     rdi
0x180065fcb  pop     rsi
0x180065fcc  pop     rbp
0x180065fcd  retn
```
