# SdpInitializeCom(int *)

- ea: `0x140001ee4`
- end: `0x140002230`
- name: `?SdpInitializeCom@@YAJPEAH@Z`
- size: `844`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002490`

## callees

- `0x140001ee4`
- `0x1400057b8`
- `0x140005964`

## import_xrefs

- `ADVAPI32!MakeAbsoluteSD` at `0x140001fd9`
- `ADVAPI32!MakeAbsoluteSD` at `0x1400021b6`
- `ADVAPI32!MakeAbsoluteSD` at `0x140001fd9`
- `ADVAPI32!MakeAbsoluteSD` at `0x1400021b6`
- `KERNEL32!GetProcessHeap` at `0x140002035`
- `KERNEL32!GetProcessHeap` at `0x14000204e`
- `KERNEL32!GetProcessHeap` at `0x140002067`
- `KERNEL32!GetProcessHeap` at `0x140002080`
- `KERNEL32!GetProcessHeap` at `0x1400020ad`
- `KERNEL32!GetProcessHeap` at `0x1400020e0`
- `KERNEL32!GetProcessHeap` at `0x140002113`
- `KERNEL32!GetProcessHeap` at `0x140002146`
- `KERNEL32!GetProcessHeap` at `0x140002035`
- `KERNEL32!GetProcessHeap` at `0x14000204e`
- `KERNEL32!GetProcessHeap` at `0x140002067`
- `KERNEL32!GetProcessHeap` at `0x140002080`
- `KERNEL32!GetProcessHeap` at `0x1400020ad`
- `KERNEL32!GetProcessHeap` at `0x1400020e0`
- `KERNEL32!GetProcessHeap` at `0x140002113`
- `KERNEL32!GetProcessHeap` at `0x140002146`
- `KERNEL32!HeapFree` at `0x140002043`
- `KERNEL32!HeapFree` at `0x14000205c`
- `KERNEL32!HeapFree` at `0x140002075`
- `KERNEL32!HeapFree` at `0x14000208e`
- `KERNEL32!HeapFree` at `0x140002043`
- `KERNEL32!HeapFree` at `0x14000205c`
- `KERNEL32!HeapFree` at `0x140002075`
- `KERNEL32!HeapFree` at `0x14000208e`
- `KERNEL32!LocalFree` at `0x14000202a`
- `KERNEL32!LocalFree` at `0x14000202a`
- `KERNEL32!HeapAlloc` at `0x1400020bb`
- `KERNEL32!HeapAlloc` at `0x1400020ee`
- `KERNEL32!HeapAlloc` at `0x140002121`
- `KERNEL32!HeapAlloc` at `0x140002154`
- `KERNEL32!HeapAlloc` at `0x1400020bb`
- `KERNEL32!HeapAlloc` at `0x1400020ee`
- `KERNEL32!HeapAlloc` at `0x140002121`
- `KERNEL32!HeapAlloc` at `0x140002154`
- `KERNEL32!GetLastError` at `0x140001fe3`
- `KERNEL32!GetLastError` at `0x1400021c0`
- `KERNEL32!GetLastError` at `0x140001fe3`
- `KERNEL32!GetLastError` at `0x1400021c0`
- `ole32!CoInitializeSecurity` at `0x140002212`
- `ole32!CoInitializeSecurity` at `0x140002212`
- `ole32!CoInitializeEx` at `0x140001f5f`
- `ole32!CoInitializeEx` at `0x140001f5f`

## string_xrefs

- `0x140001f43`: `SdpInitializeCom`
- `0x140002016`: `SdpInitializeCom`

## pseudocode

```c
__int64 __fastcall SdpInitializeCom(int *a1)
{
  void *v2; // rsi
  struct _ACL *v3; // r12
  void *pOwner; // r15
  void *v5; // r14
  signed int v6; // ebx
  int v7; // r8d
  int v8; // r9d
  void *lpSecurityDescriptor; // rdi
  HRESULT v10; // eax
  int SecurityDescriptor; // eax
  unsigned int v12; // ecx
  signed int LastError; // eax
  int v14; // r8d
  int v15; // r9d
  HANDLE v16; // rax
  HANDLE v17; // rax
  HANDLE v18; // rax
  HANDLE v19; // rax
  DWORD v21; // ebx
  HANDLE ProcessHeap; // rax
  DWORD v23; // ebx
  HANDLE v24; // rax
  DWORD v25; // ebx
  HANDLE v26; // rax
  DWORD v27; // ebx
  HANDLE v28; // rax
  void *pPrimaryGroup; // rax
  signed int v30; // eax
  HRESULT v31; // eax
  DWORD dwSaclSize; // [rsp+60h] [rbp-9h] BYREF
  struct _SECURITY_ATTRIBUTES pSelfRelativeSecurityDescriptor[3]; // [rsp+68h] [rbp-1h] BYREF
  DWORD dwPrimaryGroupSize; // [rsp+D0h] [rbp+67h] BYREF
  DWORD dwOwnerSize; // [rsp+D8h] [rbp+6Fh] BYREF
  DWORD dwDaclSize; // [rsp+E0h] [rbp+77h] BYREF
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+E8h] [rbp+7Fh] BYREF

  dwAbsoluteSecurityDescriptorSize = 0;
  dwDaclSize = 0;
  dwSaclSize = 0;
  v2 = 0;
  dwOwnerSize = 0;
  v3 = 0;
  dwPrimaryGroupSize = 0;
  pOwner = 0;
  v5 = 0;
  memset(pSelfRelativeSecurityDescriptor, 0, 24);
  if ( !a1 )
  {
    v6 = -2147024809;
    v7 = 175;
    v8 = -2147024809;
LABEL_3:
    SdpDebugTrace((unsigned int)a1, L"SdpInitializeCom", v7, v8);
    lpSecurityDescriptor = pSelfRelativeSecurityDescriptor[0].lpSecurityDescriptor;
    goto LABEL_17;
  }
  *a1 = 0;
  v10 = CoInitializeEx(0, 0);
  v6 = v10;
  if ( v10 < 0 )
  {
    v8 = v10;
    v7 = 181;
    goto LABEL_3;
  }
  *a1 = 1;
  SecurityDescriptor = SdpCreateSecurityDescriptor((unsigned int)a1, pSelfRelativeSecurityDescriptor);
  v6 = SecurityDescriptor;
  if ( SecurityDescriptor < 0 )
  {
    v8 = SecurityDescriptor;
    v7 = 186;
    goto LABEL_3;
  }
  lpSecurityDescriptor = pSelfRelativeSecurityDescriptor[0].lpSecurityDescriptor;
  if ( MakeAbsoluteSD(
         pSelfRelativeSecurityDescriptor[0].lpSecurityDescriptor,
         0,
         &dwAbsoluteSecurityDescriptorSize,
         0,
         &dwDaclSize,
         0,
         &dwSaclSize,
         0,
         &dwOwnerSize,
         0,
         &dwPrimaryGroupSize) )
  {
    goto LABEL_13;
  }
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( v6 != -2147024774 )
  {
    if ( v6 < 0 )
    {
LABEL_14:
      v14 = 204;
LABEL_15:
      v15 = v6;
LABEL_16:
      SdpDebugTrace(v12, L"SdpInitializeCom", v14, v15);
      goto LABEL_17;
    }
LABEL_13:
    v6 = -2147418113;
    goto LABEL_14;
  }
  v21 = dwAbsoluteSecurityDescriptorSize;
  ProcessHeap = GetProcessHeap();
  v2 = HeapAlloc(ProcessHeap, 0, v21);
  if ( !v2 )
  {
    v15 = -2147024882;
    v14 = 208;
    v6 = -2147024882;
    goto LABEL_16;
  }
  v23 = dwDaclSize;
  v24 = GetProcessHeap();
  v3 = (struct _ACL *)HeapAlloc(v24, 0, v23);
  if ( !v3 )
  {
    v15 = -2147024882;
    v14 = 211;
    v6 = -2147024882;
    goto LABEL_16;
  }
  v25 = dwOwnerSize;
  v26 = GetProcessHeap();
  pOwner = HeapAlloc(v26, 0, v25);
  if ( !pOwner )
  {
    v15 = -2147024882;
    v14 = 214;
    v6 = -2147024882;
    goto LABEL_16;
  }
  v27 = dwPrimaryGroupSize;
  v28 = GetProcessHeap();
  pPrimaryGroup = HeapAlloc(v28, 0, v27);
  v5 = pPrimaryGroup;
  if ( !pPrimaryGroup )
  {
    v15 = -2147024882;
    v14 = 217;
    v6 = -2147024882;
    goto LABEL_16;
  }
  if ( !MakeAbsoluteSD(
          lpSecurityDescriptor,
          v2,
          &dwAbsoluteSecurityDescriptorSize,
          v3,
          &dwDaclSize,
          0,
          &dwSaclSize,
          pOwner,
          &dwOwnerSize,
          pPrimaryGroup,
          &dwPrimaryGroupSize) )
  {
    v30 = GetLastError();
    v6 = v30;
    if ( v30 > 0 )
      v6 = (unsigned __int16)v30 | 0x80070000;
    if ( v6 < 0 )
    {
      v14 = 230;
      goto LABEL_15;
    }
  }
  v31 = CoInitializeSecurity(v2, -1, 0, 0, 6u, 2u, 0, 0x2000u, 0);
  v6 = v31;
  if ( v31 < 0 )
  {
    v15 = v31;
    v14 = 241;
    goto LABEL_16;
  }
LABEL_17:
  if ( lpSecurityDescriptor )
    LocalFree(lpSecurityDescriptor);
  if ( v2 )
  {
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v2);
  }
  if ( v3 )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v3);
  }
  if ( pOwner )
  {
    v18 = GetProcessHeap();
    HeapFree(v18, 0, pOwner);
  }
  if ( v5 )
  {
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v5);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140001ee4  push    rbp
0x140001ee6  push    rbx
0x140001ee7  push    rsi
0x140001ee8  push    rdi
0x140001ee9  push    r12
0x140001eeb  push    r13
0x140001eed  push    r14
0x140001eef  push    r15
0x140001ef1  lea     rbp, [rsp-1Fh]
0x140001ef6  sub     rsp, 88h
0x140001efd  xor     r13d, r13d
0x140001f00  xor     eax, eax
0x140001f02  mov     [rbp+57h+dwAbsoluteSecurityDescriptorSize], r13d
0x140001f06  xorps   xmm0, xmm0
0x140001f09  mov     [rbp+57h+dwDaclSize], r13d
0x140001f0d  mov     rdi, rcx
0x140001f10  mov     [rbp+57h+dwSaclSize], r13d
0x140001f14  mov     esi, r13d
0x140001f17  mov     [rbp+57h+dwOwnerSize], r13d
0x140001f1b  mov     r12d, r13d
0x140001f1e  mov     [rbp+57h+dwPrimaryGroupSize], r13d
0x140001f22  mov     r15d, r13d
0x140001f25  mov     [rbp+57h+var_48], rax
0x140001f29  mov     r14d, r13d
0x140001f2c  movups  xmmword ptr [rbp+57h+pSelfRelativeSecurityDescriptor], xmm0
0x140001f30  test    rcx, rcx
0x140001f33  jnz     short loc_140001F58
0x140001f35  mov     ebx, 80070057h
0x140001f3a  mov     r8d, 0AFh; int
0x140001f40  mov     r9d, ebx; int
0x140001f43  lea     rdx, aSdpinitializec; "SdpInitializeCom"
0x140001f4a  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x140001f4f  mov     rdi, [rbp+57h+pSelfRelativeSecurityDescriptor+8]
0x140001f53  jmp     loc_140002022
0x140001f58  mov     [rcx], r13d
0x140001f5b  xor     edx, edx; dwCoInit
0x140001f5d  xor     ecx, ecx; pvReserved
0x140001f5f  call    cs:__imp_CoInitializeEx
0x140001f65  mov     ebx, eax
0x140001f67  test    eax, eax
0x140001f69  jns     short loc_140001F76
0x140001f6b  mov     r9d, eax
0x140001f6e  mov     r8d, 0B5h
0x140001f74  jmp     short loc_140001F43
0x140001f76  lea     rdx, [rbp+57h+pSelfRelativeSecurityDescriptor]; struct _SECURITY_ATTRIBUTES *
0x140001f7a  mov     dword ptr [rdi], 1
0x140001f80  call    ?SdpCreateSecurityDescriptor@@YAJKPEAU_SECURITY_ATTRIBUTES@@@Z; SdpCreateSecurityDescriptor(ulong,_SECURITY_ATTRIBUTES *)
0x140001f85  mov     ebx, eax
0x140001f87  test    eax, eax
0x140001f89  jns     short loc_140001F96
0x140001f8b  mov     r9d, eax
0x140001f8e  mov     r8d, 0BAh
0x140001f94  jmp     short loc_140001F43
0x140001f96  mov     rdi, [rbp+57h+pSelfRelativeSecurityDescriptor+8]
0x140001f9a  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x140001f9e  mov     [rsp+0C0h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x140001fa3  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x140001fa7  mov     [rsp+0C0h+pPrimaryGroup], r13; pPrimaryGroup
0x140001fac  lea     rax, [rbp+57h+dwOwnerSize]
0x140001fb0  mov     [rsp+0C0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x140001fb5  xor     r9d, r9d; pDacl
0x140001fb8  mov     [rsp+0C0h+pOwner], r13; pOwner
0x140001fbd  lea     rax, [rbp+57h+dwSaclSize]
0x140001fc1  mov     [rsp+0C0h+lpdwSaclSize], rax; lpdwSaclSize
0x140001fc6  xor     edx, edx; pAbsoluteSecurityDescriptor
0x140001fc8  lea     rax, [rbp+57h+dwDaclSize]
0x140001fcc  mov     [rsp+0C0h+pSacl], r13; pSacl
0x140001fd1  mov     rcx, rdi; pSelfRelativeSecurityDescriptor
0x140001fd4  mov     [rsp+0C0h+lpdwDaclSize], rax; lpdwDaclSize
0x140001fd9  call    cs:__imp_MakeAbsoluteSD
0x140001fdf  test    eax, eax
0x140001fe1  jnz     short loc_140002008
0x140001fe3  call    cs:__imp_GetLastError
0x140001fe9  mov     ebx, eax
0x140001feb  test    eax, eax
0x140001fed  jle     short loc_140001FF8
0x140001fef  movzx   ebx, ax
0x140001ff2  or      ebx, 80070000h
0x140001ff8  cmp     ebx, 8007007Ah
0x140001ffe  jz      loc_1400020AA
0x140002004  test    ebx, ebx
0x140002006  js      short loc_14000200D
0x140002008  mov     ebx, 8000FFFFh
0x14000200d  mov     r8d, 0CCh; int
0x140002013  mov     r9d, ebx; int
0x140002016  lea     rdx, aSdpinitializec; "SdpInitializeCom"
0x14000201d  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x140002022  test    rdi, rdi
0x140002025  jz      short loc_140002030
0x140002027  mov     rcx, rdi; hMem
0x14000202a  call    cs:__imp_LocalFree
0x140002030  test    rsi, rsi
0x140002033  jz      short loc_140002049
0x140002035  call    cs:__imp_GetProcessHeap
0x14000203b  mov     r8, rsi; lpMem
0x14000203e  xor     edx, edx; dwFlags
0x140002040  mov     rcx, rax; hHeap
0x140002043  call    cs:__imp_HeapFree
0x140002049  test    r12, r12
0x14000204c  jz      short loc_140002062
0x14000204e  call    cs:__imp_GetProcessHeap
0x140002054  mov     r8, r12; lpMem
0x140002057  xor     edx, edx; dwFlags
0x140002059  mov     rcx, rax; hHeap
0x14000205c  call    cs:__imp_HeapFree
0x140002062  test    r15, r15
0x140002065  jz      short loc_14000207B
0x140002067  call    cs:__imp_GetProcessHeap
0x14000206d  mov     r8, r15; lpMem
0x140002070  xor     edx, edx; dwFlags
0x140002072  mov     rcx, rax; hHeap
0x140002075  call    cs:__imp_HeapFree
0x14000207b  test    r14, r14
0x14000207e  jz      short loc_140002094
0x140002080  call    cs:__imp_GetProcessHeap
0x140002086  mov     r8, r14; lpMem
0x140002089  xor     edx, edx; dwFlags
0x14000208b  mov     rcx, rax; hHeap
0x14000208e  call    cs:__imp_HeapFree
0x140002094  mov     eax, ebx
0x140002096  add     rsp, 88h
0x14000209d  pop     r15
0x14000209f  pop     r14
0x1400020a1  pop     r13
0x1400020a3  pop     r12
0x1400020a5  pop     rdi
0x1400020a6  pop     rsi
0x1400020a7  pop     rbx
0x1400020a8  pop     rbp
0x1400020a9  retn
0x1400020aa  mov     ebx, [rbp+57h+dwAbsoluteSecurityDescriptorSize]
0x1400020ad  call    cs:__imp_GetProcessHeap
0x1400020b3  mov     r8d, ebx; dwBytes
0x1400020b6  xor     edx, edx; dwFlags
0x1400020b8  mov     rcx, rax; hHeap
0x1400020bb  call    cs:__imp_HeapAlloc
0x1400020c1  mov     rsi, rax
0x1400020c4  test    rax, rax
0x1400020c7  jnz     short loc_1400020DD
0x1400020c9  mov     r9d, 8007000Eh
0x1400020cf  mov     r8d, 0D0h
0x1400020d5  mov     ebx, r9d
0x1400020d8  jmp     loc_140002016
0x1400020dd  mov     ebx, [rbp+57h+dwDaclSize]
0x1400020e0  call    cs:__imp_GetProcessHeap
0x1400020e6  mov     r8d, ebx; dwBytes
0x1400020e9  xor     edx, edx; dwFlags
0x1400020eb  mov     rcx, rax; hHeap
0x1400020ee  call    cs:__imp_HeapAlloc
0x1400020f4  mov     r12, rax
0x1400020f7  test    rax, rax
0x1400020fa  jnz     short loc_140002110
0x1400020fc  mov     r9d, 8007000Eh
0x140002102  mov     r8d, 0D3h
0x140002108  mov     ebx, r9d
0x14000210b  jmp     loc_140002016
0x140002110  mov     ebx, [rbp+57h+dwOwnerSize]
0x140002113  call    cs:__imp_GetProcessHeap
0x140002119  mov     r8d, ebx; dwBytes
0x14000211c  xor     edx, edx; dwFlags
0x14000211e  mov     rcx, rax; hHeap
0x140002121  call    cs:__imp_HeapAlloc
0x140002127  mov     r15, rax
0x14000212a  test    rax, rax
0x14000212d  jnz     short loc_140002143
0x14000212f  mov     r9d, 8007000Eh
0x140002135  mov     r8d, 0D6h
0x14000213b  mov     ebx, r9d
0x14000213e  jmp     loc_140002016
0x140002143  mov     ebx, [rbp+57h+dwPrimaryGroupSize]
0x140002146  call    cs:__imp_GetProcessHeap
0x14000214c  mov     r8d, ebx; dwBytes
0x14000214f  xor     edx, edx; dwFlags
0x140002151  mov     rcx, rax; hHeap
0x140002154  call    cs:__imp_HeapAlloc
0x14000215a  mov     r14, rax
0x14000215d  test    rax, rax
0x140002160  jnz     short loc_140002176
0x140002162  mov     r9d, 8007000Eh
0x140002168  mov     r8d, 0D9h
0x14000216e  mov     ebx, r9d
0x140002171  jmp     loc_140002016
0x140002176  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x14000217a  mov     r9, r12; pDacl
0x14000217d  mov     [rsp+0C0h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x140002182  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x140002186  mov     [rsp+0C0h+pPrimaryGroup], r14; pPrimaryGroup
0x14000218b  lea     rax, [rbp+57h+dwOwnerSize]
0x14000218f  mov     [rsp+0C0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x140002194  mov     rdx, rsi; pAbsoluteSecurityDescriptor
0x140002197  mov     [rsp+0C0h+pOwner], r15; pOwner
0x14000219c  lea     rax, [rbp+57h+dwSaclSize]
0x1400021a0  mov     [rsp+0C0h+lpdwSaclSize], rax; lpdwSaclSize
0x1400021a5  mov     rcx, rdi; pSelfRelativeSecurityDescriptor
0x1400021a8  lea     rax, [rbp+57h+dwDaclSize]
0x1400021ac  mov     [rsp+0C0h+pSacl], r13; pSacl
0x1400021b1  mov     [rsp+0C0h+lpdwDaclSize], rax; lpdwDaclSize
0x1400021b6  call    cs:__imp_MakeAbsoluteSD
0x1400021bc  test    eax, eax
0x1400021be  jnz     short loc_1400021E4
0x1400021c0  call    cs:__imp_GetLastError
0x1400021c6  mov     ebx, eax
0x1400021c8  test    eax, eax
0x1400021ca  jle     short loc_1400021D5
0x1400021cc  movzx   ebx, ax
0x1400021cf  or      ebx, 80070000h
0x1400021d5  test    ebx, ebx
0x1400021d7  jns     short loc_1400021E4
0x1400021d9  mov     r8d, 0E6h
0x1400021df  jmp     loc_140002013
0x1400021e4  mov     [rsp+0C0h+lpdwOwnerSize], r13; pReserved3
0x1400021e9  xor     r9d, r9d; pReserved1
0x1400021ec  mov     dword ptr [rsp+0C0h+pOwner], 2000h; dwCapabilities
0x1400021f4  xor     r8d, r8d; asAuthSvc
0x1400021f7  mov     [rsp+0C0h+lpdwSaclSize], r13; pAuthList
0x1400021fc  or      edx, 0FFFFFFFFh; cAuthSvc
0x1400021ff  mov     dword ptr [rsp+0C0h+pSacl], 2; dwImpLevel
0x140002207  mov     rcx, rsi; pSecDesc
0x14000220a  mov     dword ptr [rsp+0C0h+lpdwDaclSize], 6; dwAuthnLevel
0x140002212  call    cs:__imp_CoInitializeSecurity
0x140002218  mov     ebx, eax
0x14000221a  test    eax, eax
0x14000221c  jns     loc_140002022
0x140002222  mov     r9d, eax
0x140002225  mov     r8d, 0F1h
0x14000222b  jmp     loc_140002016
```
