# CTDCCtl::SecurityCheckDataURL(ushort *)

- ea: `0x180008b40`
- end: `0x180008d6a`
- name: `?SecurityCheckDataURL@CTDCCtl@@EEAAJPEAG@Z`
- size: `554`
- prototype: `__int64 __fastcall(CTDCCtl *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001938`
- `0x180005bd4`
- `0x180008b40`
- `0x180014226`
- `0x180014270`
- `0x180015010`

## import_xrefs

- `urlmon!CoInternetCreateSecurityManager` at `0x180008bd0`
- `urlmon!CoInternetCreateSecurityManager` at `0x180008bd0`
- `ole32!CoTaskMemFree` at `0x180008cf8`
- `ole32!CoTaskMemFree` at `0x180008cf8`

## pseudocode

```c
__int64 __fastcall CTDCCtl::SecurityCheckDataURL(CTDCCtl *this, unsigned __int16 *a2)
{
  void (__fastcall ***v2)(_QWORD, GUID *, IServiceProvider **); // r9
  IServiceProvider *v4; // rcx
  HRESULT v6; // ebx
  int v7; // eax
  int v8; // ecx
  struct IOleClientSite *v9; // rcx
  void *v10; // rcx
  size_t Size; // [rsp+30h] [rbp-D0h] BYREF
  IServiceProvider *pSP; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v14; // [rsp+40h] [rbp-C0h] BYREF
  IInternetSecurityManager *ppSM; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE Buf1[512]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE Buf2[512]; // [rsp+260h] [rbp+160h] BYREF

  v2 = (void (__fastcall ***)(_QWORD, GUID *, IServiceProvider **))*((_QWORD *)this + 4);
  v4 = 0;
  pSP = 0;
  if ( v2 )
  {
    (**v2)(v2, &IID_IServiceProvider, &pSP);
    v4 = pSP;
  }
  ppSM = 0;
  v14 = 0;
  Size = 0;
  if ( !v4 )
    goto LABEL_11;
  v6 = CoInternetCreateSecurityManager(v4, &ppSM, 0);
  if ( v6 >= 0 )
  {
    v6 = ((__int64 (__fastcall *)(IServiceProvider *, GUID *, GUID *, __int64 *))pSP->lpVtbl->QueryService)(
           pSP,
           &IID_IInternetHostSecurityManager,
           &IID_IInternetHostSecurityManager,
           &v14);
    if ( v6 >= 0 )
    {
      LODWORD(Size) = 511;
      v6 = (*(__int64 (__fastcall **)(__int64, _BYTE *, size_t *, _QWORD))(*(_QWORD *)v14 + 24LL))(v14, Buf1, &Size, 0);
      if ( v6 < 0 )
      {
        LODWORD(Size) = 0;
        goto LABEL_15;
      }
      HIDWORD(Size) = 511;
      v6 = ((__int64 (__fastcall *)(IInternetSecurityManager *, unsigned __int16 *, _BYTE *, char *, _QWORD))ppSM->lpVtbl->GetSecurityId)(
             ppSM,
             a2,
             Buf2,
             (char *)&Size + 4,
             0);
      if ( v6 < 0 )
      {
        HIDWORD(Size) = 0;
        goto LABEL_15;
      }
      if ( (_DWORD)Size != HIDWORD(Size) )
      {
LABEL_11:
        v6 = -2147467259;
        goto LABEL_15;
      }
      v7 = memcmp_0(Buf1, Buf2, (unsigned int)Size);
      v8 = v6;
      if ( v7 )
        v8 = -2147467259;
      v6 = v8;
    }
  }
LABEL_15:
  v9 = (struct IOleClientSite *)*((_QWORD *)this + 4);
  pv = 0;
  GetHostURL(v9, (unsigned __int16 **)&pv);
  if ( (unsigned int)Size >= 0x200uLL || (Buf1[(unsigned int)Size] = 0, HIDWORD(Size) >= 0x200uLL) )
    _report_rangecheckfailure();
  v10 = pv;
  Buf2[HIDWORD(Size)] = 0;
  CoTaskMemFree(v10);
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  if ( ppSM )
    ((void (__fastcall *)(IInternetSecurityManager *))ppSM->lpVtbl->Release)(ppSM);
  if ( pSP )
    ((void (__fastcall *)(IServiceProvider *))pSP->lpVtbl->Release)(pSP);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180008b40  mov     [rsp-8+arg_10], rbx
0x180008b45  push    rbp
0x180008b46  push    rsi
0x180008b47  push    rdi
0x180008b48  lea     rbp, [rsp-370h]
0x180008b50  sub     rsp, 470h
0x180008b57  mov     rax, cs:__security_cookie
0x180008b5e  xor     rax, rsp
0x180008b61  mov     [rbp+380h+var_20], rax
0x180008b68  mov     r9, [rcx+20h]
0x180008b6c  mov     rdi, rcx
0x180008b6f  xor     ecx, ecx
0x180008b71  mov     rsi, rdx
0x180008b74  mov     [rsp+480h+pSP], rcx
0x180008b79  test    r9, r9
0x180008b7c  jz      short loc_180008B9D
0x180008b7e  mov     rax, [r9]
0x180008b81  lea     r8, [rsp+480h+pSP]
0x180008b86  lea     rdx, IID_IServiceProvider
0x180008b8d  mov     rcx, r9
0x180008b90  mov     rax, [rax]
0x180008b93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b98  mov     rcx, [rsp+480h+pSP]; pSP
0x180008b9d  mov     [rsp+480h+ppSM], 0
0x180008ba6  mov     [rsp+480h+var_440], 0
0x180008baf  mov     dword ptr [rsp+480h+Size], 0
0x180008bb7  mov     dword ptr [rsp+480h+Size+4], 0
0x180008bbf  test    rcx, rcx
0x180008bc2  jz      loc_180008C8B
0x180008bc8  xor     r8d, r8d; dwReserved
0x180008bcb  lea     rdx, [rsp+480h+ppSM]; ppSM
0x180008bd0  call    cs:__imp_CoInternetCreateSecurityManager
0x180008bd6  mov     ebx, eax
0x180008bd8  test    eax, eax
0x180008bda  js      loc_180008CB4
0x180008be0  mov     rcx, [rsp+480h+pSP]
0x180008be5  lea     rdx, IID_IInternetHostSecurityManager
0x180008bec  lea     r9, [rsp+480h+var_440]
0x180008bf1  mov     r8, rdx
0x180008bf4  mov     rax, [rcx]
0x180008bf7  mov     rax, [rax+18h]
0x180008bfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c00  mov     ebx, eax
0x180008c02  test    eax, eax
0x180008c04  js      loc_180008CB4
0x180008c0a  mov     rcx, [rsp+480h+var_440]
0x180008c0f  lea     r8, [rsp+480h+Size]
0x180008c14  mov     dword ptr [rsp+480h+Size], 1FFh
0x180008c1c  lea     rdx, [rsp+480h+Buf1]
0x180008c21  xor     r9d, r9d
0x180008c24  mov     rax, [rcx]
0x180008c27  mov     rax, [rax+18h]
0x180008c2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c30  mov     ebx, eax
0x180008c32  test    eax, eax
0x180008c34  jns     short loc_180008C40
0x180008c36  mov     dword ptr [rsp+480h+Size], 0
0x180008c3e  jmp     short loc_180008CB4
0x180008c40  mov     rcx, [rsp+480h+ppSM]
0x180008c45  lea     r9, [rsp+480h+Size+4]
0x180008c4a  mov     dword ptr [rsp+480h+Size+4], 1FFh
0x180008c52  lea     r8, [rbp+380h+Buf2]
0x180008c59  mov     rdx, rsi
0x180008c5c  mov     [rsp+480h+var_460], 0
0x180008c65  mov     rax, [rcx]
0x180008c68  mov     rax, [rax+30h]
0x180008c6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c71  mov     ebx, eax
0x180008c73  test    eax, eax
0x180008c75  jns     short loc_180008C81
0x180008c77  mov     dword ptr [rsp+480h+Size+4], 0
0x180008c7f  jmp     short loc_180008CB4
0x180008c81  mov     eax, dword ptr [rsp+480h+Size]
0x180008c85  cmp     eax, dword ptr [rsp+480h+Size+4]
0x180008c89  jz      short loc_180008C92
0x180008c8b  mov     ebx, 80004005h
0x180008c90  jmp     short loc_180008CB4
0x180008c92  mov     r8, rax; Size
0x180008c95  lea     rdx, [rbp+380h+Buf2]; Buf2
0x180008c9c  lea     rcx, [rsp+480h+Buf1]; Buf1
0x180008ca1  call    memcmp_0
0x180008ca6  mov     ecx, ebx
0x180008ca8  test    eax, eax
0x180008caa  mov     ebx, 80004005h
0x180008caf  cmovnz  ecx, ebx
0x180008cb2  mov     ebx, ecx
0x180008cb4  mov     rcx, [rdi+20h]; struct IOleClientSite *
0x180008cb8  lea     rdx, [rsp+480h+pv]; unsigned __int16 **
0x180008cbd  mov     [rsp+480h+pv], 0
0x180008cc6  call    ?GetHostURL@@YAJPEAUIOleClientSite@@PEAPEAG@Z; GetHostURL(IOleClientSite *,ushort * *)
0x180008ccb  mov     eax, dword ptr [rsp+480h+Size]
0x180008ccf  mov     ecx, 200h
0x180008cd4  cmp     rax, rcx
0x180008cd7  jnb     loc_180008D64
0x180008cdd  mov     [rsp+rax+480h+Buf1], 0
0x180008ce2  mov     eax, dword ptr [rsp+480h+Size+4]
0x180008ce6  cmp     rax, rcx
0x180008ce9  jnb     short loc_180008D64
0x180008ceb  mov     rcx, [rsp+480h+pv]; pv
0x180008cf0  mov     [rbp+rax+380h+Buf2], 0
0x180008cf8  call    cs:__imp_CoTaskMemFree
0x180008cfe  mov     rcx, [rsp+480h+var_440]
0x180008d03  test    rcx, rcx
0x180008d06  jz      short loc_180008D14
0x180008d08  mov     rax, [rcx]
0x180008d0b  mov     rax, [rax+10h]
0x180008d0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d14  mov     rcx, [rsp+480h+ppSM]
0x180008d19  test    rcx, rcx
0x180008d1c  jz      short loc_180008D2A
0x180008d1e  mov     rax, [rcx]
0x180008d21  mov     rax, [rax+10h]
0x180008d25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d2a  mov     rcx, [rsp+480h+pSP]
0x180008d2f  test    rcx, rcx
0x180008d32  jz      short loc_180008D40
0x180008d34  mov     rax, [rcx]
0x180008d37  mov     rax, [rax+10h]
0x180008d3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d40  mov     eax, ebx
0x180008d42  mov     rcx, [rbp+380h+var_20]
0x180008d49  xor     rcx, rsp; StackCookie
0x180008d4c  call    __security_check_cookie
0x180008d51  mov     rbx, [rsp+480h+arg_10]
0x180008d59  add     rsp, 470h
0x180008d60  pop     rdi
0x180008d61  pop     rsi
0x180008d62  pop     rbp
0x180008d63  retn
0x180008d64  call    __report_rangecheckfailure
```
