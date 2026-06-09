# CUserTile::SetImageToMapiProp(ushort const *,IMAPIProp *)

- ea: `0x18006c5f8`
- end: `0x18006c954`
- name: `?SetImageToMapiProp@CUserTile@@QEAAJPEBGPEAUIMAPIProp@@@Z`
- size: `860`
- prototype: `__int64 __fastcall(CUserTile *__hidden this, const unsigned __int16 *, struct IMAPIProp *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180053424`

## callees

- `0x180002818`
- `0x1800045e4`
- `0x180006f7c`
- `0x180008f74`
- `0x1800140b8`
- `0x180045494`
- `0x18006c0e8`
- `0x18006c5f8`
- `0x18006d278`
- `0x180091ef0`
- `0x180093010`

## import_xrefs

- `MSOERT2!OpenFileStreamShareW` at `0x18006c798`
- `MSOERT2!OpenFileStreamShareW` at `0x18006c798`
- `MSOERT2!HrStreamToByte` at `0x18006c8bf`
- `MSOERT2!HrStreamToByte` at `0x18006c8bf`
- `SHLWAPI!SHRegGetUSValueW` at `0x18006c6b7`
- `SHLWAPI!SHRegGetUSValueW` at `0x18006c6b7`
- `KERNEL32!LocalAlloc` at `0x18006c805`
- `KERNEL32!LocalAlloc` at `0x18006c805`
- `KERNEL32!LocalFree` at `0x18006c70d`
- `KERNEL32!LocalFree` at `0x18006c71b`
- `KERNEL32!LocalFree` at `0x18006c70d`
- `KERNEL32!LocalFree` at `0x18006c71b`
- `ole32!CoTaskMemFree` at `0x18006c726`
- `ole32!CoTaskMemFree` at `0x18006c726`

## string_xrefs

- `0x18006c69f`: `Store Picture As Link`

## pseudocode

```c
__int64 __fastcall CUserTile::SetImageToMapiProp(CUserTile *this, const unsigned __int16 *a2, struct IMAPIProp *a3)
{
  unsigned __int16 *v6; // r15
  unsigned __int16 *v7; // r14
  int v8; // r12d
  int ImageType; // ebx
  __int64 v11; // rbx
  __int64 v12; // rdx
  unsigned __int16 *v13; // rax
  struct IMAPIPropVtbl *v14; // rax
  DWORD *v15; // rdx
  int v16; // eax
  struct IMAPIPropVtbl *lpVtbl; // rax
  int pvData; // [rsp+40h] [rbp-C0h] BYREF
  struct IStream *v19; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v20; // [rsp+50h] [rbp-B0h] BYREF
  int pvDefaultData; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v23[6]; // [rsp+68h] [rbp-98h] BYREF
  int v24; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v25[24]; // [rsp+A0h] [rbp-60h] BYREF
  DWORD pdwType[2]; // [rsp+B8h] [rbp-48h] BYREF
  int v27; // [rsp+C0h] [rbp-40h]
  DWORD pcbData[2]; // [rsp+C8h] [rbp-38h] BYREF
  _DWORD v29[4]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v30[40]; // [rsp+E0h] [rbp-20h] BYREF

  v29[0] = 3;
  v19 = 0;
  pv = 0;
  v29[1] = 268239106;
  v29[2] = 1712128031;
  v29[3] = 1712193567;
  v20 = 0;
  v6 = 0;
  v7 = 0;
  STRW::STRW((STRW *)&v24, v30, 0x28u);
  pdwType[0] = 0;
  v8 = 1;
  pcbData[0] = 4;
  pvData = 0;
  pvDefaultData = 1;
  if ( SHRegGetUSValueW(
         L"Software\\Microsoft\\WAB\\Advanced Settings",
         L"Store Picture As Link",
         pdwType,
         &pvData,
         pcbData,
         0,
         &pvDefaultData,
         4u)
    || !pvData )
  {
    v8 = 0;
  }
  if ( !a2 )
  {
    ImageType = ((__int64 (__fastcall *)(struct IMAPIProp *, _DWORD *, _QWORD))a3->lpVtbl->DeleteProps)(a3, v29, 0);
    goto LABEL_6;
  }
  memset(v23, 0, sizeof(v23));
  v19 = 0;
  ImageType = OpenFileStreamShareW(a2, 3, 0x80000000LL, 5, &v19);
  if ( ImageType >= 0 )
  {
    if ( !v8 || *((_DWORD *)this + 3) )
    {
      *(_QWORD *)pdwType = 0;
      pcbData[0] = 1;
      pcbData[1] = 1712193567;
      ImageType = HrStreamToByte(v19, &pv, pdwType);
      if ( ImageType >= 0 )
      {
        ImageType = GetImageType(a2, (struct STRW *)&v24);
        if ( ImageType >= 0 )
        {
          v16 = LocalAllocFromSTRW(&v20, (const struct STRW *)&v24);
          v6 = v20;
          ImageType = v16;
          if ( v16 >= 0 )
          {
            v23[2] = pv;
            LODWORD(v23[1]) = pdwType[0];
            lpVtbl = a3->lpVtbl;
            LODWORD(v23[0]) = 268239106;
            LODWORD(v23[3]) = 1712128031;
            v23[4] = v20;
            ImageType = ((__int64 (__fastcall *)(struct IMAPIProp *, __int64, _QWORD *))lpVtbl->SetProps)(a3, 2, v23);
            if ( ImageType >= 0 )
            {
              v15 = pcbData;
              goto LABEL_24;
            }
          }
        }
      }
    }
    else
    {
      pdwType[0] = 2;
      pdwType[1] = 268239106;
      v27 = 1712128031;
      if ( !(unsigned int)IsPathLocal(a2) )
      {
        ImageType = 1;
        goto LABEL_6;
      }
      v11 = -1;
      v12 = -1;
      do
        ++v12;
      while ( a2[v12] );
      v13 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v12 + 2);
      v20 = v13;
      v7 = v13;
      if ( !v13 )
      {
        ImageType = -2147024882;
        goto LABEL_6;
      }
      do
        ++v11;
      while ( a2[v11] );
      ImageType = StringCchCopyW(v13, v11 + 1, a2);
      if ( ImageType >= 0 )
      {
        v14 = a3->lpVtbl;
        LODWORD(v23[0]) = 1712193567;
        v23[1] = __PAIR64__(HIDWORD(v20), (unsigned int)v7);
        ImageType = ((__int64 (__fastcall *)(struct IMAPIProp *, __int64, _QWORD *))v14->SetProps)(a3, 1, v23);
        if ( ImageType >= 0 )
        {
          v15 = pdwType;
LABEL_24:
          ImageType = ((__int64 (__fastcall *)(struct IMAPIProp *, DWORD *, _QWORD))a3->lpVtbl->DeleteProps)(a3, v15, 0);
        }
      }
    }
  }
LABEL_6:
  CUserTile::_LoadUserTile(this, v19);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v19);
  if ( v6 )
    LocalFree(v6);
  if ( v7 )
    LocalFree(v7);
  CoTaskMemFree(pv);
  v24 = 0;
  BUFFER::ReleaseStorage((BUFFER *)v25);
  return (unsigned int)ImageType;
}

```

## disassembly

```asm
0x18006c5f8  mov     [rsp-8+arg_18], rbx
0x18006c5fd  push    rbp
0x18006c5fe  push    rsi
0x18006c5ff  push    rdi
0x18006c600  push    r12
0x18006c602  push    r13
0x18006c604  push    r14
0x18006c606  push    r15
0x18006c608  lea     rbp, [rsp-40h]
0x18006c60d  sub     rsp, 140h
0x18006c614  mov     rax, cs:__security_cookie
0x18006c61b  xor     rax, rsp
0x18006c61e  mov     [rbp+70h+var_40], rax
0x18006c622  xor     ebx, ebx
0x18006c624  mov     [rbp+70h+var_A0], 3
0x18006c62b  mov     rdi, r8
0x18006c62e  mov     [rsp+170h+var_128], rbx
0x18006c633  mov     r13, rcx
0x18006c636  mov     [rsp+170h+pv], rbx
0x18006c63b  mov     rsi, rdx
0x18006c63e  mov     [rbp+70h+var_9C], 0FFD0102h
0x18006c645  lea     r8d, [rbx+28h]; unsigned int
0x18006c649  mov     [rbp+70h+var_98], 660D001Fh
0x18006c650  lea     rdx, [rbp+70h+var_90]; unsigned __int16 *
0x18006c654  mov     [rbp+70h+var_94], 660E001Fh
0x18006c65b  lea     rcx, [rbp+70h+var_D8]; this
0x18006c65f  mov     [rsp+170h+var_120], rbx
0x18006c664  mov     r15d, ebx
0x18006c667  mov     r14d, ebx
0x18006c66a  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x18006c66f  lea     eax, [rbx+4]
0x18006c672  mov     [rbp+70h+pdwType], ebx
0x18006c675  mov     [rsp+170h+dwDefaultDataSize], eax; dwDefaultDataSize
0x18006c679  lea     r12d, [rbx+1]
0x18006c67d  mov     [rbp+70h+var_A8], eax
0x18006c680  lea     r9, [rsp+170h+pvData]; pvData
0x18006c685  lea     rax, [rsp+170h+var_118]
0x18006c68a  mov     [rsp+170h+pvData], ebx
0x18006c68e  mov     [rsp+170h+pvDefaultData], rax; pvDefaultData
0x18006c693  lea     r8, [rbp+70h+pdwType]; pdwType
0x18006c697  lea     rax, [rbp+70h+var_A8]
0x18006c69b  mov     [rsp+170h+fIgnoreHKCU], ebx; fIgnoreHKCU
0x18006c69f  lea     rdx, aStorePictureAs; "Store Picture As Link"
0x18006c6a6  mov     [rsp+170h+pcbData], rax; pcbData
0x18006c6ab  lea     rcx, aSoftwareMicros_13; "Software\\Microsoft\\WAB\\Advanced Sett"...
0x18006c6b2  mov     [rsp+170h+var_118], r12d
0x18006c6b7  call    cs:__imp_SHRegGetUSValueW
0x18006c6bd  test    eax, eax
0x18006c6bf  jnz     short loc_18006C6C7
0x18006c6c1  cmp     [rsp+170h+pvData], ebx
0x18006c6c5  jnz     short loc_18006C6CA
0x18006c6c7  mov     r12d, ebx
0x18006c6ca  test    rsi, rsi
0x18006c6cd  jnz     loc_18006C762
0x18006c6d3  mov     rax, [rdi]
0x18006c6d6  lea     rdx, [rbp+70h+var_A0]
0x18006c6da  xor     r8d, r8d
0x18006c6dd  mov     rcx, rdi
0x18006c6e0  mov     rax, [rax+48h]
0x18006c6e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c6e9  mov     ebx, eax
0x18006c6eb  xor     r12d, r12d
0x18006c6ee  mov     rdx, [rsp+170h+var_128]; struct IStream *
0x18006c6f3  mov     rcx, r13; this
0x18006c6f6  call    ?_LoadUserTile@CUserTile@@AEAAJPEAUIStream@@@Z; CUserTile::_LoadUserTile(IStream *)
0x18006c6fb  lea     rcx, [rsp+170h+var_128]
0x18006c700  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18006c705  test    r15, r15
0x18006c708  jz      short loc_18006C713
0x18006c70a  mov     rcx, r15; hMem
0x18006c70d  call    cs:__imp_LocalFree
0x18006c713  test    r14, r14
0x18006c716  jz      short loc_18006C721
0x18006c718  mov     rcx, r14; hMem
0x18006c71b  call    cs:__imp_LocalFree
0x18006c721  mov     rcx, [rsp+170h+pv]; pv
0x18006c726  call    cs:__imp_CoTaskMemFree
0x18006c72c  lea     rcx, [rbp+70h+var_D0]; this
0x18006c730  mov     [rbp+70h+var_D8], r12d
0x18006c734  call    ?ReleaseStorage@BUFFER@@QEAAXXZ; BUFFER::ReleaseStorage(void)
0x18006c739  mov     eax, ebx
0x18006c73b  mov     rcx, [rbp+70h+var_40]
0x18006c73f  xor     rcx, rsp; StackCookie
0x18006c742  call    __security_check_cookie
0x18006c747  mov     rbx, [rsp+170h+arg_18]
0x18006c74f  add     rsp, 140h
0x18006c756  pop     r15
0x18006c758  pop     r14
0x18006c75a  pop     r13
0x18006c75c  pop     r12
0x18006c75e  pop     rdi
0x18006c75f  pop     rsi
0x18006c760  pop     rbp
0x18006c761  retn
0x18006c762  xorps   xmm0, xmm0
0x18006c765  mov     [rsp+170h+var_108], ebx
0x18006c769  mov     edx, 3
0x18006c76e  mov     [rsp+170h+var_128], rbx
0x18006c773  lea     rax, [rsp+170h+var_128]
0x18006c778  mov     r8d, 80000000h
0x18006c77e  movups  [rsp+170h+var_F4], xmm0
0x18006c783  mov     rcx, rsi
0x18006c786  mov     [rsp+170h+pcbData], rax
0x18006c78b  lea     r9d, [rdx+2]
0x18006c78f  movups  [rsp+170h+var_104], xmm0
0x18006c794  movups  [rbp+70h+var_F4+0Ch], xmm0
0x18006c798  call    cs:__imp_OpenFileStreamShareW
0x18006c79e  mov     ebx, eax
0x18006c7a0  test    eax, eax
0x18006c7a2  js      loc_18006C6EB
0x18006c7a8  test    r12d, r12d
0x18006c7ab  jz      loc_18006C89C
0x18006c7b1  xor     r12d, r12d
0x18006c7b4  cmp     [r13+0Ch], r12d
0x18006c7b8  jnz     loc_18006C89F
0x18006c7be  mov     rcx, rsi; pszPath
0x18006c7c1  mov     [rbp+70h+pdwType], 2
0x18006c7c8  mov     [rbp+70h+pdwType+4], 0FFD0102h
0x18006c7cf  mov     [rbp+70h+var_B0], 660D001Fh
0x18006c7d6  call    ?IsPathLocal@@YAHPEBG@Z; IsPathLocal(ushort const *)
0x18006c7db  test    eax, eax
0x18006c7dd  jnz     short loc_18006C7E7
0x18006c7df  lea     ebx, [rax+1]
0x18006c7e2  jmp     loc_18006C6EE
0x18006c7e7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18006c7eb  mov     rdx, rbx
0x18006c7ee  inc     rdx
0x18006c7f1  cmp     [rsi+rdx*2], r12w
0x18006c7f6  jnz     short loc_18006C7EE
0x18006c7f8  lea     rdx, ds:2[rdx*2]; uBytes
0x18006c800  mov     ecx, 40h ; '@'; uFlags
0x18006c805  call    cs:__imp_LocalAlloc
0x18006c80b  mov     [rsp+170h+var_120], rax
0x18006c810  mov     r14, rax
0x18006c813  test    rax, rax
0x18006c816  jnz     short loc_18006C822
0x18006c818  mov     ebx, 8007000Eh
0x18006c81d  jmp     loc_18006C6EE
0x18006c822  inc     rbx
0x18006c825  cmp     [rsi+rbx*2], r12w
0x18006c82a  jnz     short loc_18006C822
0x18006c82c  lea     rdx, [rbx+1]; unsigned __int64
0x18006c830  mov     r8, rsi; unsigned __int16 *
0x18006c833  mov     rcx, r14; unsigned __int16 *
0x18006c836  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006c83b  mov     ebx, eax
0x18006c83d  test    eax, eax
0x18006c83f  js      loc_18006C6EE
0x18006c845  mov     eax, dword ptr [rsp+170h+var_120+4]
0x18006c849  lea     r8, [rsp+170h+var_108]
0x18006c84e  mov     dword ptr [rsp+170h+var_104+8], eax
0x18006c852  xor     r9d, r9d
0x18006c855  mov     rax, [rdi]
0x18006c858  mov     rcx, rdi
0x18006c85b  mov     [rsp+170h+var_108], 660E001Fh
0x18006c863  mov     dword ptr [rsp+170h+var_104+4], r14d
0x18006c868  lea     edx, [r9+1]
0x18006c86c  mov     rax, [rax+40h]
0x18006c870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c875  mov     ebx, eax
0x18006c877  test    eax, eax
0x18006c879  js      loc_18006C6EE
0x18006c87f  lea     rdx, [rbp+70h+pdwType]
0x18006c883  mov     rax, [rdi]
0x18006c886  xor     r8d, r8d
0x18006c889  mov     rcx, rdi
0x18006c88c  mov     rax, [rax+48h]
0x18006c890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c895  mov     ebx, eax
0x18006c897  jmp     loc_18006C6EE
0x18006c89c  xor     r12d, r12d
0x18006c89f  mov     rcx, [rsp+170h+var_128]
0x18006c8a4  lea     r8, [rbp+70h+pdwType]
0x18006c8a8  lea     rdx, [rsp+170h+pv]
0x18006c8ad  mov     qword ptr [rbp+70h+pdwType], r12
0x18006c8b1  mov     [rbp+70h+var_A8], 1
0x18006c8b8  mov     [rbp+70h+var_A4], 660E001Fh
0x18006c8bf  call    cs:__imp_HrStreamToByte
0x18006c8c5  mov     ebx, eax
0x18006c8c7  test    eax, eax
0x18006c8c9  js      loc_18006C6EE
0x18006c8cf  lea     rdx, [rbp+70h+var_D8]; struct STRW *
0x18006c8d3  mov     rcx, rsi; unsigned __int16 *
0x18006c8d6  call    ?GetImageType@@YAJPEBGPEAVSTRW@@@Z; GetImageType(ushort const *,STRW *)
0x18006c8db  mov     ebx, eax
0x18006c8dd  test    eax, eax
0x18006c8df  js      loc_18006C6EE
0x18006c8e5  lea     rdx, [rbp+70h+var_D8]; struct STRW *
0x18006c8e9  lea     rcx, [rsp+170h+var_120]; unsigned __int16 **
0x18006c8ee  call    ?LocalAllocFromSTRW@@YAJPEAPEAGPEBVSTRW@@@Z; LocalAllocFromSTRW(ushort * *,STRW const *)
0x18006c8f3  mov     r15, [rsp+170h+var_120]
0x18006c8f8  mov     ebx, eax
0x18006c8fa  test    eax, eax
0x18006c8fc  js      loc_18006C6EE
0x18006c902  mov     rax, [rsp+170h+pv]
0x18006c907  lea     r8, [rsp+170h+var_108]
0x18006c90c  mov     qword ptr [rsp+170h+var_104+0Ch], rax
0x18006c911  xor     r9d, r9d
0x18006c914  mov     eax, [rbp+70h+pdwType]
0x18006c917  mov     rcx, rdi
0x18006c91a  mov     dword ptr [rsp+170h+var_104+4], eax
0x18006c91e  mov     rax, [rdi]
0x18006c921  lea     edx, [r9+2]
0x18006c925  mov     [rsp+170h+var_108], 0FFD0102h
0x18006c92d  mov     dword ptr [rbp+70h+var_F4+4], 660D001Fh
0x18006c934  mov     qword ptr [rbp+70h+var_F4+0Ch], r15
0x18006c938  mov     rax, [rax+40h]
0x18006c93c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c941  mov     ebx, eax
0x18006c943  test    eax, eax
0x18006c945  js      loc_18006C6EE
0x18006c94b  lea     rdx, [rbp+70h+var_A8]
0x18006c94f  jmp     loc_18006C883
```
