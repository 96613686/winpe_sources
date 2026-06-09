# EcbGetClientCertificate(_EXTENSION_CONTROL_BLOCK *,char *,int,int *,__int64 *)

- ea: `0x180010df0`
- end: `0x18001100d`
- name: `?EcbGetClientCertificate@@YAHPEAU_EXTENSION_CONTROL_BLOCK@@PEADHPEAHPEA_J@Z`
- size: `541`
- prototype: `int(struct _EXTENSION_CONTROL_BLOCK *, char *, int, int *, __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180001ea4`

## callees

- `0x180010df0`
- `0x18004d350`
- `0x18004d6c8`
- `0x18004d754`
- `0x1800653ba`
- `0x180065b60`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180010e9f`
- `KERNEL32!GetLastError` at `0x180010eb6`
- `KERNEL32!GetLastError` at `0x180010e9f`
- `KERNEL32!GetLastError` at `0x180010eb6`
- `CRYPT32!CertCreateCertificateContext` at `0x180010f0c`
- `CRYPT32!CertCreateCertificateContext` at `0x180010f0c`
- `CRYPT32!CertFreeCertificateContext` at `0x180010fd0`
- `CRYPT32!CertFreeCertificateContext` at `0x180010fd0`

## pseudocode

```c
__int64 __fastcall EcbGetClientCertificate(
        struct _EXTENSION_CONTROL_BLOCK *a1,
        char *a2,
        signed int a3,
        int *a4,
        __int64 *a5)
{
  int LastWin32Error; // ebx
  unsigned int v10; // esi
  PCCERT_CONTEXT CertificateContext; // rax
  const CERT_CONTEXT *v12; // rdi
  PCERT_INFO pCertInfo; // rcx
  size_t v14; // r8
  signed int v15; // edx
  const void *v16; // rdx
  int v17; // eax
  size_t cbData; // rcx
  size_t v19; // rcx
  DWORD dwCertEncodingType[4]; // [rsp+30h] [rbp-30h] BYREF
  DWORD cbCertEncoded[4]; // [rsp+40h] [rbp-20h]
  unsigned __int64 v23[2]; // [rsp+50h] [rbp-10h]

  LastWin32Error = 0;
  v10 = 1;
  *(_OWORD *)dwCertEncodingType = 0;
  *(_OWORD *)cbCertEncoded = 0;
  *(_OWORD *)v23 = 0;
  if ( a1 && a2 && a5 && a4 )
  {
    LODWORD(v23[1]) = 0x2000;
    *(_QWORD *)&dwCertEncodingType[2] = MemAllocClear(0x2000u);
    if ( !*(_QWORD *)&dwCertEncodingType[2] )
    {
LABEL_6:
      LastWin32Error = -2147024882;
      goto LABEL_24;
    }
    if ( !((unsigned int (__fastcall *)(HCONN, __int64, DWORD *, _QWORD, _QWORD))a1->ServerSupportFunction)(
            a1->ConnID,
            1015,
            dwCertEncodingType,
            0,
            0) )
    {
      if ( GetLastError() != 122 )
        goto LABEL_9;
      if ( GetLastError() == 122 )
      {
        MemFree(*(void **)&dwCertEncodingType[2]);
        *(_QWORD *)&dwCertEncodingType[2] = MemAllocClear(LODWORD(v23[1]));
        if ( !*(_QWORD *)&dwCertEncodingType[2] )
          goto LABEL_6;
        if ( !((unsigned int (__fastcall *)(HCONN, __int64, DWORD *, _QWORD, _QWORD))a1->ServerSupportFunction)(
                a1->ConnID,
                1015,
                dwCertEncodingType,
                0,
                0) )
          goto LABEL_9;
      }
    }
    CertificateContext = CertCreateCertificateContext(
                           dwCertEncodingType[0],
                           *(const BYTE **)&dwCertEncodingType[2],
                           cbCertEncoded[0]);
    v12 = CertificateContext;
    if ( CertificateContext )
    {
      pCertInfo = CertificateContext->pCertInfo;
      if ( pCertInfo )
      {
        v14 = (int)cbCertEncoded[0];
        v15 = cbCertEncoded[0] + pCertInfo->Issuer.cbData + pCertInfo->SubjectPublicKeyInfo.PublicKey.cbData;
        if ( a3 >= v15 )
        {
          v16 = *(const void **)&dwCertEncodingType[2];
          *a5 = (__int64)pCertInfo->NotBefore;
          v17 = dwCertEncodingType[0];
          a5[1] = (__int64)v12->pCertInfo->NotAfter;
          *a4 = v17;
          a4[1] = v14;
          memcpy_0(a2, v16, v14);
          cbData = (int)v12->pCertInfo->Issuer.cbData;
          a4[2] = cbData;
          if ( (int)cbData > 0 )
            memcpy_0(&a2[a4[1]], v12->pCertInfo->Issuer.pbData, cbData);
          v19 = (int)v12->pCertInfo->SubjectPublicKeyInfo.PublicKey.cbData;
          a4[3] = v19;
          if ( (int)v19 > 0 )
            memcpy_0(&a2[a4[1] + a4[2]], v12->pCertInfo->SubjectPublicKeyInfo.PublicKey.pbData, v19);
        }
        else
        {
          v10 = -v15;
        }
      }
      else
      {
        LastWin32Error = GetLastWin32Error();
      }
      CertFreeCertificateContext(v12);
    }
    else
    {
LABEL_9:
      LastWin32Error = GetLastWin32Error();
    }
  }
  else
  {
    LastWin32Error = -2147024809;
  }
LABEL_24:
  MemFree(*(void **)&dwCertEncodingType[2]);
  if ( LastWin32Error )
    return 0;
  return v10;
}

```

## disassembly

```asm
0x180010df0  mov     [rsp-28h+arg_0], rbx
0x180010df5  mov     [rsp-28h+arg_8], rsi
0x180010dfa  mov     [rsp-28h+arg_10], rdi
0x180010dff  push    rbp
0x180010e00  push    r12
0x180010e02  push    r13
0x180010e04  push    r14
0x180010e06  push    r15
0x180010e08  mov     rbp, rsp
0x180010e0b  sub     rsp, 60h
0x180010e0f  xor     eax, eax
0x180010e11  xorps   xmm0, xmm0
0x180010e14  mov     r14, r9
0x180010e17  mov     r13d, r8d
0x180010e1a  mov     r15, rdx
0x180010e1d  mov     rdi, rcx
0x180010e20  mov     ebx, eax
0x180010e22  lea     esi, [rax+1]
0x180010e25  movups  xmmword ptr [rbp+dwCertEncodingType], xmm0
0x180010e29  movups  xmmword ptr [rbp+cbCertEncoded], xmm0
0x180010e2d  movups  xmmword ptr [rbp+var_10], xmm0
0x180010e31  test    rcx, rcx
0x180010e34  jz      loc_180010FD8
0x180010e3a  test    rdx, rdx
0x180010e3d  jz      loc_180010FD8
0x180010e43  mov     r12, [rbp+arg_20]
0x180010e47  test    r12, r12
0x180010e4a  jz      loc_180010FD8
0x180010e50  test    r9, r9
0x180010e53  jz      loc_180010FD8
0x180010e59  mov     ecx, 2000h; unsigned __int64
0x180010e5e  mov     dword ptr [rbp+var_10+8], ecx
0x180010e61  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x180010e66  mov     qword ptr [rbp+dwCertEncodingType+8], rax
0x180010e6a  test    rax, rax
0x180010e6d  jnz     short loc_180010E79
0x180010e6f  mov     ebx, 8007000Eh
0x180010e74  jmp     loc_180010FDD
0x180010e79  mov     rcx, [rdi+8]
0x180010e7d  lea     r8, [rbp+dwCertEncodingType]
0x180010e81  mov     rax, [rdi+0B8h]
0x180010e88  xor     r9d, r9d
0x180010e8b  and     [rsp+60h+var_40], rbx
0x180010e90  mov     edx, 3F7h
0x180010e95  call    cs:__guard_dispatch_icall_fptr
0x180010e9b  test    eax, eax
0x180010e9d  jnz     short loc_180010F01
0x180010e9f  call    cs:__imp_GetLastError
0x180010ea5  cmp     eax, 7Ah ; 'z'
0x180010ea8  jz      short loc_180010EB6
0x180010eaa  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180010eaf  mov     ebx, eax
0x180010eb1  jmp     loc_180010FDD
0x180010eb6  call    cs:__imp_GetLastError
0x180010ebc  cmp     eax, 7Ah ; 'z'
0x180010ebf  jnz     short loc_180010F01
0x180010ec1  mov     rcx, qword ptr [rbp+dwCertEncodingType+8]; lpMem
0x180010ec5  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180010eca  mov     ecx, dword ptr [rbp+var_10+8]; unsigned __int64
0x180010ecd  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x180010ed2  mov     qword ptr [rbp+dwCertEncodingType+8], rax
0x180010ed6  test    rax, rax
0x180010ed9  jz      short loc_180010E6F
0x180010edb  mov     rcx, [rdi+8]
0x180010edf  lea     r8, [rbp+dwCertEncodingType]
0x180010ee3  mov     rax, [rdi+0B8h]
0x180010eea  xor     r9d, r9d
0x180010eed  and     [rsp+60h+var_40], rbx
0x180010ef2  mov     edx, 3F7h
0x180010ef7  call    cs:__guard_dispatch_icall_fptr
0x180010efd  test    eax, eax
0x180010eff  jz      short loc_180010EAA
0x180010f01  mov     r8d, [rbp+cbCertEncoded]; cbCertEncoded
0x180010f05  mov     rdx, qword ptr [rbp+dwCertEncodingType+8]; pbCertEncoded
0x180010f09  mov     ecx, [rbp+dwCertEncodingType]; dwCertEncodingType
0x180010f0c  call    cs:__imp_CertCreateCertificateContext
0x180010f12  mov     rdi, rax
0x180010f15  test    rax, rax
0x180010f18  jz      short loc_180010EAA
0x180010f1a  mov     rcx, [rax+18h]
0x180010f1e  test    rcx, rcx
0x180010f21  jnz     short loc_180010F2F
0x180010f23  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180010f28  mov     ebx, eax
0x180010f2a  jmp     loc_180010FCD
0x180010f2f  mov     edx, [rcx+78h]
0x180010f32  add     edx, [rcx+30h]
0x180010f35  movsxd  r8, [rbp+cbCertEncoded]; Size
0x180010f39  add     edx, r8d
0x180010f3c  cmp     r13d, edx
0x180010f3f  jge     short loc_180010F4A
0x180010f41  mov     esi, edx
0x180010f43  neg     esi
0x180010f45  jmp     loc_180010FCD
0x180010f4a  mov     rax, [rcx+40h]
0x180010f4e  mov     rdx, qword ptr [rbp+dwCertEncodingType+8]; Src
0x180010f52  mov     [r12], rax
0x180010f56  mov     rax, [rdi+18h]
0x180010f5a  mov     rcx, [rax+48h]
0x180010f5e  mov     eax, [rbp+dwCertEncodingType]
0x180010f61  mov     [r12+8], rcx
0x180010f66  mov     rcx, r15; void *
0x180010f69  mov     [r14], eax
0x180010f6c  mov     [r14+4], r8d
0x180010f70  call    memcpy_0
0x180010f75  mov     rax, [rdi+18h]
0x180010f79  movsxd  rcx, dword ptr [rax+30h]
0x180010f7d  mov     [r14+8], ecx
0x180010f81  test    ecx, ecx
0x180010f83  jle     short loc_180010F9C
0x180010f85  mov     rdx, [rdi+18h]
0x180010f89  mov     r8, rcx; Size
0x180010f8c  movsxd  rcx, dword ptr [r14+4]
0x180010f90  add     rcx, r15; void *
0x180010f93  mov     rdx, [rdx+38h]; Src
0x180010f97  call    memcpy_0
0x180010f9c  mov     rax, [rdi+18h]
0x180010fa0  movsxd  rcx, dword ptr [rax+78h]
0x180010fa4  mov     [r14+0Ch], ecx
0x180010fa8  test    ecx, ecx
0x180010faa  jle     short loc_180010FCD
0x180010fac  mov     eax, [r14+8]
0x180010fb0  mov     r8, rcx; Size
0x180010fb3  mov     rdx, [rdi+18h]
0x180010fb7  add     eax, [r14+4]
0x180010fbb  movsxd  rcx, eax
0x180010fbe  add     rcx, r15; void *
0x180010fc1  mov     rdx, [rdx+80h]; Src
0x180010fc8  call    memcpy_0
0x180010fcd  mov     rcx, rdi; pCertContext
0x180010fd0  call    cs:__imp_CertFreeCertificateContext
0x180010fd6  jmp     short loc_180010FDD
0x180010fd8  mov     ebx, 80070057h
0x180010fdd  mov     rcx, qword ptr [rbp+dwCertEncodingType+8]; lpMem
0x180010fe1  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180010fe6  xor     eax, eax
0x180010fe8  lea     r11, [rsp+60h+var_s0]
0x180010fed  mov     rdi, [r11+40h]
0x180010ff1  test    ebx, ebx
0x180010ff3  mov     rbx, [r11+30h]
0x180010ff7  cmovnz  esi, eax
0x180010ffa  mov     eax, esi
0x180010ffc  mov     rsi, [r11+38h]
0x180011000  mov     rsp, r11
0x180011003  pop     r15
0x180011005  pop     r14
0x180011007  pop     r13
0x180011009  pop     r12
0x18001100b  pop     rbp
0x18001100c  retn
```
