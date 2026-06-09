# WscDSA_OutOfBoxExperience(CWmiEventManagerAvFw *,CThirdPartyManager *)

- ea: `0x18003c204`
- end: `0x18003c473`
- name: `?WscDSA_OutOfBoxExperience@@YAJPEAVCWmiEventManagerAvFw@@PEAVCThirdPartyManager@@@Z`
- size: `623`
- prototype: `__int64 __fastcall(struct CWmiEventManagerAvFw *this, struct CThirdPartyManager *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18003d100`

## callees

- `0x18000760c`
- `0x1800088b0`
- `0x180008e48`
- `0x18000a490`
- `0x18001c690`
- `0x1800202e8`
- `0x180032e48`
- `0x18003c204`
- `0x18003ce18`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c422`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c422`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c264`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c264`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18003c371`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18003c371`

## pseudocode

```c
__int64 __fastcall WscDSA_OutOfBoxExperience(struct CWmiEventManagerAvFw *this, struct CThirdPartyManager *a2)
{
  unsigned int v4; // edi
  int NumberOfProducts; // ebx
  CThirdPartyManager *v6; // rcx
  __int64 *v7; // r15
  __int64 *v8; // rsi
  __int64 *v9; // rbx
  FILETIME v10; // rax
  struct CExternalBase *v11; // r8
  FILETIME FileTime1; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v14; // [rsp+88h] [rbp+48h] BYREF
  FILETIME FileTime2; // [rsp+90h] [rbp+50h] BYREF
  struct CExternalBase *v16; // [rsp+98h] [rbp+58h] BYREF

  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, WPP_728c66c465713f49a85befae87578f6c_Traceguids);
  v4 = 0;
  v14 = 0;
  FileTime1 = 0;
  FileTime2 = 0;
  v16 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 16));
  NumberOfProducts = CThirdPartyManager::GetNumberOfProducts(a2, &v14);
  if ( NumberOfProducts < 0 )
    goto LABEL_36;
  v6 = WPP_GLOBAL_Control;
  v7 = 0;
  v8 = 0;
  while ( v4 < v14 )
  {
    NumberOfProducts = CThirdPartyManager::GetProductAtOffset(a2, v4, &v16);
    if ( NumberOfProducts < 0 )
      goto LABEL_36;
    v9 = (__int64 *)v16;
    if ( (unsigned int)ExtractProductOwner(*((_DWORD *)v16 + 20)) == 256 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, WPP_728c66c465713f49a85befae87578f6c_Traceguids);
        v6 = WPP_GLOBAL_Control;
      }
      v7 = v9;
    }
    else
    {
      if ( (unsigned int)CExternalBase::GetProductState((__int64)v9) == 4096
        || (unsigned int)CExternalBase::GetProductState((__int64)v9) == 0x2000 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          WPP_SF_SS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            100,
            (unsigned int)WPP_728c66c465713f49a85befae87578f6c_Traceguids,
            v9[2],
            v9[1]);
          v6 = WPP_GLOBAL_Control;
        }
        v10 = (FILETIME)v9[8];
        FileTime2 = v10;
        if ( !v4 )
          goto LABEL_21;
        if ( CompareFileTime(&FileTime1, &FileTime2) > 0 )
        {
          v10 = FileTime2;
          v6 = WPP_GLOBAL_Control;
LABEL_21:
          v8 = v9;
          FileTime1 = v10;
          goto LABEL_22;
        }
      }
      v6 = WPP_GLOBAL_Control;
    }
LABEL_22:
    ++v4;
  }
  if ( v8 )
  {
    if ( v6 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
      WPP_SF_SS(*((_QWORD *)v6 + 2), 101, (unsigned int)WPP_728c66c465713f49a85befae87578f6c_Traceguids, v8[2], v8[1]);
    v11 = (struct CExternalBase *)v8;
    goto LABEL_34;
  }
  if ( v7 )
  {
    if ( v6 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)v6 + 2), 102, WPP_728c66c465713f49a85befae87578f6c_Traceguids);
    v11 = (struct CExternalBase *)v7;
LABEL_34:
    NumberOfProducts = WscDSA_SaveDefaultByPtr(this, a2, v11);
  }
  else
  {
    NumberOfProducts = -2147418113;
  }
LABEL_36:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 16));
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      103,
      WPP_728c66c465713f49a85befae87578f6c_Traceguids,
      (unsigned int)NumberOfProducts);
  return (unsigned int)NumberOfProducts;
}

```

## disassembly

```asm
0x18003c204  mov     [rsp-38h+arg_0], rbx
0x18003c209  push    rbp
0x18003c20a  push    rsi
0x18003c20b  push    rdi
0x18003c20c  push    r12
0x18003c20e  push    r13
0x18003c210  push    r14
0x18003c212  push    r15
0x18003c214  mov     rbp, rsp
0x18003c217  sub     rsp, 40h
0x18003c21b  mov     r14, rdx
0x18003c21e  mov     r12, rcx
0x18003c221  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c228  lea     rax, WPP_GLOBAL_Control
0x18003c22f  cmp     rcx, rax
0x18003c232  jz      short loc_18003C24F
0x18003c234  test    byte ptr [rcx+1Ch], 8
0x18003c238  jz      short loc_18003C24F
0x18003c23a  mov     rcx, [rcx+10h]
0x18003c23e  lea     r8, WPP_728c66c465713f49a85befae87578f6c_Traceguids
0x18003c245  mov     edx, 62h ; 'b'
0x18003c24a  call    WPP_SF_
0x18003c24f  xor     edi, edi
0x18003c251  lea     rcx, [r14+10h]; lpCriticalSection
0x18003c255  mov     [rbp+arg_8], edi
0x18003c258  mov     qword ptr [rbp+FileTime1.dwLowDateTime], rdi
0x18003c25c  mov     qword ptr [rbp+FileTime2.dwLowDateTime], rdi
0x18003c260  mov     [rbp+arg_18], rdi
0x18003c264  call    cs:__imp_EnterCriticalSection
0x18003c26a  lea     rdx, [rbp+arg_8]; unsigned int *
0x18003c26e  mov     rcx, r14; this
0x18003c271  call    ?GetNumberOfProducts@CThirdPartyManager@@QEAAJAEAK@Z; CThirdPartyManager::GetNumberOfProducts(ulong &)
0x18003c276  mov     ebx, eax
0x18003c278  test    eax, eax
0x18003c27a  js      loc_18003C41E
0x18003c280  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c287  mov     r15d, edi
0x18003c28a  mov     esi, edi
0x18003c28c  cmp     edi, [rbp+arg_8]
0x18003c28f  jnb     loc_18003C39D
0x18003c295  lea     r8, [rbp+arg_18]; struct CExternalBase **
0x18003c299  mov     edx, edi; unsigned int
0x18003c29b  mov     rcx, r14; this
0x18003c29e  call    ?GetProductAtOffset@CThirdPartyManager@@QEAAJKPEAPEAVCExternalBase@@@Z; CThirdPartyManager::GetProductAtOffset(ulong,CExternalBase * *)
0x18003c2a3  mov     ebx, eax
0x18003c2a5  test    eax, eax
0x18003c2a7  js      loc_18003C41E
0x18003c2ad  mov     rbx, [rbp+arg_18]
0x18003c2b1  mov     ecx, [rbx+50h]
0x18003c2b4  call    ?ExtractProductOwner@@YA?AW4ProductOwner@@K@Z; ExtractProductOwner(ulong)
0x18003c2b9  cmp     eax, 100h
0x18003c2be  jnz     short loc_18003C2FD
0x18003c2c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c2c7  lea     rax, WPP_GLOBAL_Control
0x18003c2ce  cmp     rcx, rax
0x18003c2d1  jz      short loc_18003C2F5
0x18003c2d3  test    byte ptr [rcx+1Ch], 8
0x18003c2d7  jz      short loc_18003C2F5
0x18003c2d9  mov     rcx, [rcx+10h]
0x18003c2dd  lea     r8, WPP_728c66c465713f49a85befae87578f6c_Traceguids
0x18003c2e4  mov     edx, 63h ; 'c'
0x18003c2e9  call    WPP_SF_
0x18003c2ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c2f5  mov     r15, rbx
0x18003c2f8  jmp     loc_18003C38D
0x18003c2fd  mov     rcx, rbx
0x18003c300  call    ?GetProductState@CExternalBase@@QEAA?AW4ProductState@@XZ; CExternalBase::GetProductState(void)
0x18003c305  cmp     eax, 1000h
0x18003c30a  jz      short loc_18003C31B
0x18003c30c  mov     rcx, rbx
0x18003c30f  call    ?GetProductState@CExternalBase@@QEAA?AW4ProductState@@XZ; CExternalBase::GetProductState(void)
0x18003c314  cmp     eax, 2000h
0x18003c319  jnz     short loc_18003C394
0x18003c31b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c322  lea     rax, WPP_GLOBAL_Control
0x18003c329  cmp     rcx, rax
0x18003c32c  jz      short loc_18003C35D
0x18003c32e  test    byte ptr [rcx+1Ch], 8
0x18003c332  jz      short loc_18003C35D
0x18003c334  mov     rax, [rbx+8]
0x18003c338  lea     r8, WPP_728c66c465713f49a85befae87578f6c_Traceguids
0x18003c33f  mov     r9, [rbx+10h]
0x18003c343  mov     edx, 64h ; 'd'
0x18003c348  mov     rcx, [rcx+10h]
0x18003c34c  mov     [rsp+40h+var_20], rax
0x18003c351  call    WPP_SF_SS
0x18003c356  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c35d  mov     rax, [rbx+40h]
0x18003c361  mov     qword ptr [rbp+FileTime2.dwLowDateTime], rax
0x18003c365  test    edi, edi
0x18003c367  jz      short loc_18003C386
0x18003c369  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x18003c36d  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x18003c371  call    cs:__imp_CompareFileTime
0x18003c377  test    eax, eax
0x18003c379  jle     short loc_18003C394
0x18003c37b  mov     rax, qword ptr [rbp+FileTime2.dwLowDateTime]
0x18003c37f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c386  mov     rsi, rbx
0x18003c389  mov     qword ptr [rbp+FileTime1.dwLowDateTime], rax
0x18003c38d  inc     edi
0x18003c38f  jmp     loc_18003C28C
0x18003c394  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c39b  jmp     short loc_18003C38D
0x18003c39d  test    rsi, rsi
0x18003c3a0  jz      short loc_18003C3DB
0x18003c3a2  lea     rax, WPP_GLOBAL_Control
0x18003c3a9  cmp     rcx, rax
0x18003c3ac  jz      short loc_18003C3D6
0x18003c3ae  test    byte ptr [rcx+1Ch], 8
0x18003c3b2  jz      short loc_18003C3D6
0x18003c3b4  mov     rax, [rsi+8]
0x18003c3b8  lea     r8, WPP_728c66c465713f49a85befae87578f6c_Traceguids
0x18003c3bf  mov     r9, [rsi+10h]
0x18003c3c3  mov     edx, 65h ; 'e'
0x18003c3c8  mov     rcx, [rcx+10h]
0x18003c3cc  mov     [rsp+40h+var_20], rax
0x18003c3d1  call    WPP_SF_SS
0x18003c3d6  mov     r8, rsi
0x18003c3d9  jmp     short loc_18003C40A
0x18003c3db  test    r15, r15
0x18003c3de  jz      short loc_18003C419
0x18003c3e0  lea     rax, WPP_GLOBAL_Control
0x18003c3e7  cmp     rcx, rax
0x18003c3ea  jz      short loc_18003C407
0x18003c3ec  test    byte ptr [rcx+1Ch], 8
0x18003c3f0  jz      short loc_18003C407
0x18003c3f2  mov     rcx, [rcx+10h]
0x18003c3f6  lea     r8, WPP_728c66c465713f49a85befae87578f6c_Traceguids
0x18003c3fd  mov     edx, 66h ; 'f'
0x18003c402  call    WPP_SF_
0x18003c407  mov     r8, r15; struct CExternalBase *
0x18003c40a  mov     rdx, r14; struct CThirdPartyManager *
0x18003c40d  mov     rcx, r12; this
0x18003c410  call    ?WscDSA_SaveDefaultByPtr@@YAJPEAVCWmiEventManagerAvFw@@PEAVCThirdPartyManager@@PEAVCExternalBase@@@Z; WscDSA_SaveDefaultByPtr(CWmiEventManagerAvFw *,CThirdPartyManager *,CExternalBase *)
0x18003c415  mov     ebx, eax
0x18003c417  jmp     short loc_18003C41E
0x18003c419  mov     ebx, 8000FFFFh
0x18003c41e  lea     rcx, [r14+10h]; lpCriticalSection
0x18003c422  call    cs:__imp_LeaveCriticalSection
0x18003c428  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c42f  lea     rax, WPP_GLOBAL_Control
0x18003c436  cmp     rcx, rax
0x18003c439  jz      short loc_18003C459
0x18003c43b  test    byte ptr [rcx+1Ch], 8
0x18003c43f  jz      short loc_18003C459
0x18003c441  mov     rcx, [rcx+10h]
0x18003c445  lea     r8, WPP_728c66c465713f49a85befae87578f6c_Traceguids
0x18003c44c  mov     edx, 67h ; 'g'
0x18003c451  mov     r9d, ebx
0x18003c454  call    WPP_SF_d
0x18003c459  mov     eax, ebx
0x18003c45b  mov     rbx, [rsp+40h+arg_0]
0x18003c463  add     rsp, 40h
0x18003c467  pop     r15
0x18003c469  pop     r14
0x18003c46b  pop     r13
0x18003c46d  pop     r12
0x18003c46f  pop     rdi
0x18003c470  pop     rsi
0x18003c471  pop     rbp
0x18003c472  retn
```
