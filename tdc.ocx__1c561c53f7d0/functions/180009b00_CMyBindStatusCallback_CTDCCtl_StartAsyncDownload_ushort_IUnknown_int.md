# CMyBindStatusCallback<CTDCCtl>::_StartAsyncDownload(ushort *,IUnknown *,int)

- ea: `0x180009b00`
- end: `0x180009d48`
- name: `?_StartAsyncDownload@?$CMyBindStatusCallback@VCTDCCtl@@@@QEAAJPEAGPEAUIUnknown@@H@Z`
- size: `584`
- prototype: `__int64 __fastcall(IBindStatusCallback *pBSCb)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006c40`

## callees

- `0x180009b00`
- `0x180015010`

## import_xrefs

- `urlmon!RegisterBindStatusCallback` at `0x180009c09`
- `urlmon!RegisterBindStatusCallback` at `0x180009c09`
- `ole32!CreateBindCtx` at `0x180009bed`
- `ole32!CreateBindCtx` at `0x180009bed`
- `ole32!CoTaskMemFree` at `0x180009cb8`
- `ole32!CoTaskMemFree` at `0x180009cb8`

## pseudocode

```c
__int64 __fastcall CMyBindStatusCallback<CTDCCtl>::_StartAsyncDownload(
        IBindStatusCallback *pBSCb,
        __int64 a2,
        void (__fastcall ***a3)(_QWORD, GUID *, __int64 *))
{
  __int64 v4; // rcx
  LPBC *v8; // rsi
  HRESULT BindCtx; // ebx
  IBindStatusCallback *v10; // r14
  struct IBindStatusCallbackVtbl *lpVtbl; // rcx
  LPBC v12; // rdx
  int v13; // eax
  void *v14; // r10
  __int64 v15; // rdx
  _WORD *v16; // rax
  _WORD *v17; // r9
  __int64 v18; // r8
  _WORD *v19; // rdx
  __int64 v20; // [rsp+40h] [rbp-10h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-8h] BYREF
  __int64 v22; // [rsp+80h] [rbp+30h] BYREF
  __int64 v23; // [rsp+90h] [rbp+40h] BYREF

  pBSCb[536].lpVtbl = 0;
  v4 = 0;
  v23 = 0;
  if ( a3 )
  {
    (**a3)(a3, &IID_IServiceProvider, &v23);
    v4 = v23;
  }
  v22 = 0;
  v20 = 0;
  if ( v4 )
    (*(void (__fastcall **)(__int64, GUID *, GUID *, __int64 *))(*(_QWORD *)v4 + 24LL))(
      v4,
      &IID_IBindHost,
      &IID_IBindHost,
      &v22);
  (**a3)(a3, &IID_IOleClientSite, (__int64 *)&pBSCb[10]);
  if ( v22 )
  {
    v8 = (LPBC *)&pBSCb[6];
    BindCtx = CreateBindCtx(0, (LPBC *)&pBSCb[6]);
    if ( BindCtx >= 0 )
    {
      BindCtx = RegisterBindStatusCallback(*v8, pBSCb, 0, 0);
      if ( BindCtx >= 0 )
      {
        v10 = pBSCb + 5;
        BindCtx = (*(__int64 (__fastcall **)(__int64, __int64, LPBC, IBindStatusCallback *, _DWORD))(*(_QWORD *)v22 + 24LL))(
                    v22,
                    a2,
                    *v8,
                    pBSCb + 5,
                    0);
        if ( BindCtx >= 0 )
        {
          lpVtbl = v10->lpVtbl;
          v12 = *v8;
          pv = 0;
          v13 = (*((__int64 (__fastcall **)(struct IBindStatusCallbackVtbl *, LPBC, _QWORD, LPVOID *))lpVtbl->QueryInterface
                 + 20))(
                  lpVtbl,
                  v12,
                  0,
                  &pv);
          v14 = pv;
          if ( !v13 && pv )
          {
            v15 = 2147483646;
            v16 = (_WORD *)&pBSCb[11].lpVtbl + 2;
            v17 = pv;
            v18 = 2084;
            do
            {
              if ( !v15 )
                break;
              if ( !*v17 )
                break;
              *v16++ = *v17++;
              --v15;
              --v18;
            }
            while ( v18 );
            v19 = v16 - 1;
            if ( v18 )
              v19 = v16;
            *v19 = 0;
          }
          CoTaskMemFree(v14);
          BindCtx = (*(__int64 (__fastcall **)(__int64, struct IBindStatusCallbackVtbl *, _QWORD, IBindStatusCallback *, GUID *, __int64 *))(*(_QWORD *)v22 + 32LL))(
                      v22,
                      v10->lpVtbl,
                      0,
                      pBSCb,
                      &IID_IStream,
                      &v20);
        }
      }
    }
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    return (unsigned int)BindCtx;
  }
  else
  {
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    return 2147500034LL;
  }
}

```

## disassembly

```asm
0x180009b00  mov     [rsp-28h+arg_8], rbx
0x180009b05  mov     [rsp-28h+arg_18], rsi
0x180009b0a  push    rbp
0x180009b0b  push    rdi
0x180009b0c  push    r12
0x180009b0e  push    r14
0x180009b10  push    r15
0x180009b12  mov     rbp, rsp
0x180009b15  sub     rsp, 50h
0x180009b19  xor     r12d, r12d
0x180009b1c  mov     rdi, rcx
0x180009b1f  mov     [rcx+10C0h], r12
0x180009b26  mov     ecx, r12d
0x180009b29  mov     [rbp+arg_10], rcx
0x180009b2d  mov     rbx, r8
0x180009b30  mov     r15, rdx
0x180009b33  test    r8, r8
0x180009b36  jz      short loc_180009B55
0x180009b38  mov     rax, [r8]
0x180009b3b  lea     rdx, IID_IServiceProvider
0x180009b42  lea     r8, [rbp+arg_10]
0x180009b46  mov     rcx, rbx
0x180009b49  mov     rax, [rax]
0x180009b4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b51  mov     rcx, [rbp+arg_10]
0x180009b55  mov     [rbp+arg_0], r12
0x180009b59  mov     [rbp+var_10], r12
0x180009b5d  test    rcx, rcx
0x180009b60  jz      short loc_180009B7C
0x180009b62  mov     rax, [rcx]
0x180009b65  lea     rdx, IID_IBindHost
0x180009b6c  lea     r9, [rbp+arg_0]
0x180009b70  mov     r8, rdx
0x180009b73  mov     rax, [rax+18h]
0x180009b77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b7c  mov     rax, [rbx]
0x180009b7f  lea     r8, [rdi+50h]
0x180009b83  lea     rdx, IID_IOleClientSite
0x180009b8a  mov     rcx, rbx
0x180009b8d  mov     rax, [rax]
0x180009b90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b95  cmp     [rbp+arg_0], r12
0x180009b99  jnz     short loc_180009BE4
0x180009b9b  mov     rcx, [rbp+var_10]
0x180009b9f  test    rcx, rcx
0x180009ba2  jz      short loc_180009BC5
0x180009ba4  mov     rax, [rcx]
0x180009ba7  mov     rax, [rax+10h]
0x180009bab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bb0  mov     rcx, [rbp+arg_0]
0x180009bb4  test    rcx, rcx
0x180009bb7  jz      short loc_180009BC5
0x180009bb9  mov     rax, [rcx]
0x180009bbc  mov     rax, [rax+10h]
0x180009bc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bc5  mov     rcx, [rbp+arg_10]
0x180009bc9  test    rcx, rcx
0x180009bcc  jz      short loc_180009BDA
0x180009bce  mov     rax, [rcx]
0x180009bd1  mov     rax, [rax+10h]
0x180009bd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bda  mov     eax, 80004002h
0x180009bdf  jmp     loc_180009D2F
0x180009be4  lea     rsi, [rdi+30h]
0x180009be8  xor     ecx, ecx; reserved
0x180009bea  mov     rdx, rsi; ppbc
0x180009bed  call    cs:__imp_CreateBindCtx
0x180009bf3  mov     ebx, eax
0x180009bf5  test    eax, eax
0x180009bf7  js      loc_180009CEE
0x180009bfd  mov     rcx, [rsi]; pBC
0x180009c00  xor     r9d, r9d; dwReserved
0x180009c03  xor     r8d, r8d; ppBSCBPrev
0x180009c06  mov     rdx, rdi; pBSCb
0x180009c09  call    cs:__imp_RegisterBindStatusCallback
0x180009c0f  mov     ebx, eax
0x180009c11  test    eax, eax
0x180009c13  js      loc_180009CEE
0x180009c19  mov     rcx, [rbp+arg_0]
0x180009c1d  lea     r14, [rdi+28h]
0x180009c21  mov     r8, [rsi]
0x180009c24  mov     r9, r14
0x180009c27  mov     rdx, r15
0x180009c2a  mov     dword ptr [rsp+50h+var_30], r12d
0x180009c2f  mov     rax, [rcx]
0x180009c32  mov     rax, [rax+18h]
0x180009c36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c3b  mov     ebx, eax
0x180009c3d  test    eax, eax
0x180009c3f  js      loc_180009CEE
0x180009c45  mov     rcx, [r14]
0x180009c48  lea     r9, [rbp+pv]
0x180009c4c  mov     rdx, [rsi]
0x180009c4f  xor     r8d, r8d
0x180009c52  mov     [rbp+pv], r12
0x180009c56  mov     rax, [rcx]
0x180009c59  mov     rax, [rax+0A0h]
0x180009c60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c65  mov     r10, [rbp+pv]
0x180009c69  test    eax, eax
0x180009c6b  jnz     short loc_180009CB5
0x180009c6d  test    r10, r10
0x180009c70  jz      short loc_180009CB5
0x180009c72  mov     edx, 7FFFFFFEh
0x180009c77  lea     rax, [rdi+5Ch]
0x180009c7b  mov     r9, r10
0x180009c7e  mov     r8d, 824h
0x180009c84  test    rdx, rdx
0x180009c87  jz      short loc_180009CA6
0x180009c89  movzx   ecx, word ptr [r9]
0x180009c8d  test    cx, cx
0x180009c90  jz      short loc_180009CA6
0x180009c92  mov     [rax], cx
0x180009c95  add     r9, 2
0x180009c99  add     rax, 2
0x180009c9d  dec     rdx
0x180009ca0  sub     r8, 1
0x180009ca4  jnz     short loc_180009C84
0x180009ca6  test    r8, r8
0x180009ca9  lea     rdx, [rax-2]
0x180009cad  cmovnz  rdx, rax
0x180009cb1  mov     [rdx], r12w
0x180009cb5  mov     rcx, r10; pv
0x180009cb8  call    cs:__imp_CoTaskMemFree
0x180009cbe  mov     rcx, [rbp+arg_0]
0x180009cc2  lea     rdx, [rbp+var_10]
0x180009cc6  mov     [rsp+50h+var_28], rdx
0x180009ccb  mov     r9, rdi
0x180009cce  lea     rdx, IID_IStream
0x180009cd5  xor     r8d, r8d
0x180009cd8  mov     [rsp+50h+var_30], rdx
0x180009cdd  mov     rax, [rcx]
0x180009ce0  mov     rdx, [r14]
0x180009ce3  mov     rax, [rax+20h]
0x180009ce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009cec  mov     ebx, eax
0x180009cee  mov     rcx, [rbp+var_10]
0x180009cf2  test    rcx, rcx
0x180009cf5  jz      short loc_180009D03
0x180009cf7  mov     rax, [rcx]
0x180009cfa  mov     rax, [rax+10h]
0x180009cfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d03  mov     rcx, [rbp+arg_0]
0x180009d07  test    rcx, rcx
0x180009d0a  jz      short loc_180009D18
0x180009d0c  mov     rax, [rcx]
0x180009d0f  mov     rax, [rax+10h]
0x180009d13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d18  mov     rcx, [rbp+arg_10]
0x180009d1c  test    rcx, rcx
0x180009d1f  jz      short loc_180009D2D
0x180009d21  mov     rax, [rcx]
0x180009d24  mov     rax, [rax+10h]
0x180009d28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d2d  mov     eax, ebx
0x180009d2f  lea     r11, [rsp+50h+var_s0]
0x180009d34  mov     rbx, [r11+38h]
0x180009d38  mov     rsi, [r11+48h]
0x180009d3c  mov     rsp, r11
0x180009d3f  pop     r15
0x180009d41  pop     r14
0x180009d43  pop     r12
0x180009d45  pop     rdi
0x180009d46  pop     rbp
0x180009d47  retn
```
