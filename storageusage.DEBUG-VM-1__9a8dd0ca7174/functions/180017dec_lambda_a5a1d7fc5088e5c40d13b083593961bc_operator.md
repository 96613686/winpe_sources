# _lambda_a5a1d7fc5088e5c40d13b083593961bc_::operator()

- ea: `0x180017dec`
- end: `0x180018090`
- name: `_lambda_a5a1d7fc5088e5c40d13b083593961bc_::operator()`
- size: `676`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180017970`

## callees

- `0x1800010b0`
- `0x180002198`
- `0x1800050f0`
- `0x180005c94`
- `0x180017dec`
- `0x180019edc`
- `0x18001f5e4`
- `0x18001f6a4`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180018067`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180018067`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180017ebd`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180017ebd`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180017ed2`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180017ed2`

## pseudocode

```c
void __fastcall lambda_a5a1d7fc5088e5c40d13b083593961bc_::operator()(__int64 a1, __int64 *a2)
{
  struct _GUID v3; // xmm0
  int KFPathFromGUID; // esi
  unsigned __int16 *v5; // rax
  int v6; // r8d
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  bool v11; // [rsp+70h] [rbp-90h] BYREF
  bool v12; // [rsp+71h] [rbp-8Fh] BYREF
  unsigned __int16 *v13; // [rsp+78h] [rbp-88h] BYREF
  int v14; // [rsp+80h] [rbp-80h] BYREF
  int v15; // [rsp+84h] [rbp-7Ch] BYREF
  int v16; // [rsp+88h] [rbp-78h] BYREF
  int v17; // [rsp+8Ch] [rbp-74h] BYREF
  int v18[4]; // [rsp+90h] [rbp-70h] BYREF
  struct _GUID v19; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v20; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR *v21; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v22; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR szFileName[264]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v24[528]; // [rsp+2E0h] [rbp+1E0h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+4F0h] [rbp+3F0h] BYREF
  _BYTE v26[528]; // [rsp+700h] [rbp+600h] BYREF

  memset_0(szFileName, 0, 0x208u);
  memset_0(v24, 0, 0x208u);
  memset_0(v26, 0, 0x208u);
  v13 = (unsigned __int16 *)v26;
  memset_0(szVolumePathName, 0, 0x208u);
  v3 = *(struct _GUID *)(a2 + 1);
  v11 = 0;
  v12 = 0;
  v19 = v3;
  KFPathFromGUID = GetKFPathFromGUID(&v19, 0, (struct DirQueItem *)szFileName);
  if ( KFPathFromGUID >= 0 )
  {
    if ( GetVolumePathNameW(szFileName, szVolumePathName, 0x104u) )
    {
      if ( GetDriveTypeW(szVolumePathName) == 3 )
      {
        IsSystemDrive(szVolumePathName, &v11);
        if ( v11 )
        {
          v19 = *(struct _GUID *)(a2 + 1);
          if ( (unsigned int)GetKFPathFromGUID(&v19, 0x400u, (struct DirQueItem *)v24) != -2147467259 )
          {
            v5 = (unsigned __int16 *)v24;
            do
            {
              v6 = *(v5 - 264);
              if ( *v5 - v6 )
                break;
              ++v5;
            }
            while ( v6 );
          }
        }
      }
    }
    IsFolderInSyncRoot(szFileName, &v12, &v13);
  }
  if ( (unsigned int)dword_180040010 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180040010, 0x400000000000LL) )
  {
    v20 = v13;
    v21 = szVolumePathName;
    v22 = *a2;
    v14 = 2;
    v15 = -1;
    v16 = 2;
    v17 = 2;
    v18[0] = 2;
    LODWORD(v13) = KFPathFromGUID;
    *(_QWORD *)&v19.Data1 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      v8,
      (unsigned int)&unk_180037E10,
      v9,
      v10,
      (__int64)&v19,
      (__int64)&v22,
      (__int64)&v21,
      (__int64)&v13,
      (__int64)v18,
      (__int64)&v17,
      (__int64)&v16,
      (__int64)&v15,
      (__int64)&v14,
      (__int64)&v20);
  }
  Sleep(0x28u);
}

```

## disassembly

```asm
0x180017dec  push    rbp
0x180017dee  push    rbx
0x180017def  push    rsi
0x180017df0  push    rdi
0x180017df1  push    r12
0x180017df3  push    r13
0x180017df5  push    r14
0x180017df7  push    r15
0x180017df9  lea     rbp, [rsp-828h]
0x180017e01  sub     rsp, 928h
0x180017e08  mov     rax, cs:__security_cookie
0x180017e0f  xor     rax, rsp
0x180017e12  mov     [rbp+860h+var_50], rax
0x180017e19  mov     r13, rdx
0x180017e1c  lea     rcx, [rbp+860h+szFileName]; void *
0x180017e20  mov     ebx, 208h
0x180017e25  xor     edx, edx; Val
0x180017e27  mov     r8d, ebx; Size
0x180017e2a  call    memset_0
0x180017e2f  mov     r8d, ebx; Size
0x180017e32  lea     rcx, [rbp+860h+var_680]; void *
0x180017e39  xor     edx, edx; Val
0x180017e3b  call    memset_0
0x180017e40  mov     r8d, ebx; Size
0x180017e43  lea     rcx, [rbp+860h+var_260]; void *
0x180017e4a  xor     edx, edx; Val
0x180017e4c  call    memset_0
0x180017e51  lea     rax, [rbp+860h+var_260]
0x180017e58  mov     r8d, ebx; Size
0x180017e5b  xor     edx, edx; Val
0x180017e5d  mov     [rsp+960h+var_8E8], rax
0x180017e62  lea     rcx, [rbp+860h+szVolumePathName]; void *
0x180017e69  or      r12d, 0FFFFFFFFh
0x180017e6d  call    memset_0
0x180017e72  movups  xmm0, xmmword ptr [r13+8]
0x180017e77  lea     ebx, [r12+3]
0x180017e7c  mov     [rsp+960h+var_8F0], 0
0x180017e81  lea     r8, [rbp+860h+szFileName]; struct DirQueItem *
0x180017e85  mov     [rsp+960h+var_8EF], 0
0x180017e8a  xor     edx, edx; unsigned int
0x180017e8c  lea     rcx, [rbp+860h+var_8C0]; struct _GUID
0x180017e90  movdqu  xmmword ptr [rbp+860h+var_8C0.Data1], xmm0
0x180017e95  mov     edi, ebx
0x180017e97  mov     r14d, ebx
0x180017e9a  mov     r15d, ebx
0x180017e9d  call    ?GetKFPathFromGUID@@YAJU_GUID@@KAEAUDirQueItem@@@Z; GetKFPathFromGUID(_GUID,ulong,DirQueItem &)
0x180017ea2  mov     esi, eax
0x180017ea4  test    eax, eax
0x180017ea6  js      loc_180017F94
0x180017eac  mov     r8d, 104h; cchBufferLength
0x180017eb2  lea     rdx, [rbp+860h+szVolumePathName]; lpszVolumePathName
0x180017eb9  lea     rcx, [rbp+860h+szFileName]; lpszFileName
0x180017ebd  call    cs:__imp_GetVolumePathNameW
0x180017ec3  test    eax, eax
0x180017ec5  jz      loc_180017F71
0x180017ecb  lea     rcx, [rbp+860h+szVolumePathName]; lpRootPathName
0x180017ed2  call    cs:__imp_GetDriveTypeW
0x180017ed8  mov     r12d, eax
0x180017edb  cmp     eax, 3
0x180017ede  jz      short loc_180017EEA
0x180017ee0  xor     edi, edi
0x180017ee2  lea     ebx, [rdi+1]
0x180017ee5  jmp     loc_180017F71
0x180017eea  lea     rdx, [rsp+960h+var_8F0]; bool *
0x180017eef  lea     rcx, [rbp+860h+szVolumePathName]; unsigned __int16 *
0x180017ef6  call    ?IsSystemDrive@@YAJPEBGAEA_N@Z; IsSystemDrive(ushort const *,bool &)
0x180017efb  mov     cl, [rsp+960h+var_8F0]
0x180017eff  test    eax, eax
0x180017f01  js      short loc_180017F0B
0x180017f03  xor     edi, edi
0x180017f05  test    cl, cl
0x180017f07  setnz   dil
0x180017f0b  test    cl, cl
0x180017f0d  jz      short loc_180017F71
0x180017f0f  movups  xmm0, xmmword ptr [r13+8]
0x180017f14  lea     r8, [rbp+860h+var_680]; struct DirQueItem *
0x180017f1b  mov     edx, 400h; unsigned int
0x180017f20  lea     rcx, [rbp+860h+var_8C0]; struct _GUID
0x180017f24  movdqu  xmmword ptr [rbp+860h+var_8C0.Data1], xmm0
0x180017f29  call    ?GetKFPathFromGUID@@YAJU_GUID@@KAEAUDirQueItem@@@Z; GetKFPathFromGUID(_GUID,ulong,DirQueItem &)
0x180017f2e  mov     esi, eax
0x180017f30  cmp     eax, 80004005h
0x180017f35  jz      short loc_180017F69
0x180017f37  lea     rax, [rbp+860h+var_680]
0x180017f3e  lea     rdx, [rbp+860h+szFileName]
0x180017f42  sub     rdx, rax
0x180017f45  movzx   ecx, word ptr [rax]
0x180017f48  movzx   r8d, word ptr [rax+rdx]
0x180017f4d  sub     ecx, r8d
0x180017f50  jnz     short loc_180017F5A
0x180017f52  add     rax, rbx
0x180017f55  test    r8d, r8d
0x180017f58  jnz     short loc_180017F45
0x180017f5a  test    ecx, ecx
0x180017f5c  jnz     short loc_180017F69
0x180017f5e  test    esi, esi
0x180017f60  js      short loc_180017F71
0x180017f62  xor     r14d, r14d
0x180017f65  xor     ebx, ebx
0x180017f67  jmp     short loc_180017F71
0x180017f69  mov     ebx, 1
0x180017f6e  mov     r14d, ebx
0x180017f71  lea     r8, [rsp+960h+var_8E8]; unsigned __int16 **
0x180017f76  lea     rdx, [rsp+960h+var_8EF]; bool *
0x180017f7b  lea     rcx, [rbp+860h+szFileName]; Str
0x180017f7f  call    ?IsFolderInSyncRoot@@YAJPEBGAEA_NPEAPEAG@Z; IsFolderInSyncRoot(ushort const *,bool &,ushort * *)
0x180017f84  test    eax, eax
0x180017f86  js      short loc_180017F94
0x180017f88  xor     r15d, r15d
0x180017f8b  cmp     [rsp+960h+var_8EF], r15b
0x180017f90  setnz   r15b
0x180017f94  mov     eax, cs:dword_180040010
0x180017f9a  cmp     eax, 5
0x180017f9d  jbe     loc_180018062
0x180017fa3  mov     rdx, 400000000000h
0x180017fad  lea     rcx, dword_180040010
0x180017fb4  call    _tlgKeywordOn
0x180017fb9  test    al, al
0x180017fbb  jz      loc_180018062
0x180017fc1  mov     rax, [rsp+960h+var_8E8]
0x180017fc6  lea     rdx, unk_180037E10
0x180017fcd  mov     [rbp+860h+var_8B0], rax
0x180017fd1  lea     rax, [rbp+860h+szVolumePathName]
0x180017fd8  mov     [rbp+860h+var_8A8], rax
0x180017fdc  mov     rax, [r13+0]
0x180017fe0  mov     [rbp+860h+var_8A0], rax
0x180017fe4  lea     rax, [rbp+860h+var_8B0]
0x180017fe8  mov     [rsp+960h+var_8F8], rax
0x180017fed  lea     rax, [rbp+860h+var_8E0]
0x180017ff1  mov     [rsp+960h+var_900], rax
0x180017ff6  lea     rax, [rbp+860h+var_8DC]
0x180017ffa  mov     [rsp+960h+var_908], rax
0x180017fff  lea     rax, [rbp+860h+var_8D8]
0x180018003  mov     [rsp+960h+var_910], rax
0x180018008  lea     rax, [rbp+860h+var_8D4]
0x18001800c  mov     [rsp+960h+var_918], rax
0x180018011  lea     rax, [rbp+860h+var_8D0]
0x180018015  mov     [rsp+960h+var_920], rax
0x18001801a  lea     rax, [rsp+960h+var_8E8]
0x18001801f  mov     [rsp+960h+var_928], rax
0x180018024  lea     rax, [rbp+860h+var_8A8]
0x180018028  mov     [rsp+960h+var_930], rax
0x18001802d  lea     rax, [rbp+860h+var_8A0]
0x180018031  mov     [rsp+960h+var_938], rax
0x180018036  lea     rax, [rbp+860h+var_8C0]
0x18001803a  mov     [rsp+960h+var_940], rax
0x18001803f  mov     [rbp+860h+var_8E0], r15d
0x180018043  mov     [rbp+860h+var_8DC], r12d
0x180018047  mov     [rbp+860h+var_8D8], r14d
0x18001804b  mov     [rbp+860h+var_8D4], edi
0x18001804e  mov     [rbp+860h+var_8D0], ebx
0x180018051  mov     dword ptr [rsp+960h+var_8E8], esi
0x180018055  mov     qword ptr [rbp+860h+var_8C0.Data1], 1000000h
0x18001805d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@U3@U3@U3@U3@U3@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@555554@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x180018062  mov     ecx, 28h ; '('; dwMilliseconds
0x180018067  call    cs:__imp_Sleep
0x18001806d  mov     rcx, [rbp+860h+var_50]
0x180018074  xor     rcx, rsp; StackCookie
0x180018077  call    __security_check_cookie
0x18001807c  add     rsp, 928h
0x180018083  pop     r15
0x180018085  pop     r14
0x180018087  pop     r13
0x180018089  pop     r12
0x18001808b  pop     rdi
0x18001808c  pop     rsi
0x18001808d  pop     rbx
0x18001808e  pop     rbp
0x18001808f  retn
```
