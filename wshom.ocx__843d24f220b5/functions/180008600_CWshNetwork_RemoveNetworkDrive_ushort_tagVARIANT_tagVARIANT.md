# CWshNetwork::RemoveNetworkDrive(ushort *,tagVARIANT *,tagVARIANT *)

- ea: `0x180008600`
- end: `0x1800087af`
- name: `?RemoveNetworkDrive@CWshNetwork@@UEAAJPEAGPEAUtagVARIANT@@1@Z`
- size: `431`
- prototype: `int(CWshNetwork *__hidden this, unsigned __int16 *, struct tagVARIANT *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180003f3c`
- `0x180008600`
- `0x180009c04`
- `0x180009c40`
- `0x180010250`
- `0x1800102e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800086e6`
- `KERNEL32!GetLastError` at `0x1800086e6`
- `KERNEL32!WideCharToMultiByte` at `0x1800086d9`
- `KERNEL32!WideCharToMultiByte` at `0x18000874e`
- `KERNEL32!WideCharToMultiByte` at `0x1800086d9`
- `KERNEL32!WideCharToMultiByte` at `0x18000874e`
- `MPR!WNetCancelConnection2W` at `0x1800086a0`
- `MPR!WNetCancelConnection2W` at `0x1800086a0`
- `MPR!WNetCancelConnection2A` at `0x180008760`
- `MPR!WNetCancelConnection2A` at `0x180008760`

## string_xrefs

- `0x18000877c`: `WSHNetwork.RemoveNetworkDrive`

## pseudocode

```c
int __fastcall CWshNetwork::RemoveNetworkDrive(
        CWshNetwork *this,
        unsigned __int16 *a2,
        struct tagVARIANT *a3,
        struct tagVARIANT *a4)
{
  int v6; // edi
  VARIANTARG *v7; // rcx
  int result; // eax
  DWORD v9; // ebx
  VARIANTARG *v10; // rcx
  signed int v11; // eax
  int cbMultiByte; // eax
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // rcx
  void *v15; // rsp
  void *v16; // rsp
  unsigned int v17; // ebx
  bool v18; // sf
  CHAR MultiByteStr[4]; // [rsp+40h] [rbp+0h] BYREF
  int v20; // [rsp+44h] [rbp+4h] BYREF

  if ( !a2 || !a3 || !a4 )
    return -2147467261;
  v6 = 0;
  *(_DWORD *)MultiByteStr = 0;
  v20 = 0;
  if ( fOptionalArgSupplied(a3) )
  {
    result = Variant_BOOL(v7, (int *)MultiByteStr);
    if ( result < 0 )
      return result;
    v6 = *(_DWORD *)MultiByteStr;
  }
  v9 = 0;
  if ( fOptionalArgSupplied(a4) )
  {
    result = Variant_BOOL(v10, &v20);
    if ( result < 0 )
      return result;
    v9 = v20 != 0;
  }
  if ( Global::g_fWindowsNT )
  {
    v11 = WNetCancelConnection2W(a2, v9, v6);
LABEL_19:
    v17 = v11;
    v18 = v11 < 0;
    if ( v11 > 0 )
    {
      v17 = (unsigned __int16)v11 | 0x80070000;
      v18 = 1;
    }
    if ( v18 )
      Signal_ExceptionHR(&IID_IWshNetwork, L"WSHNetwork.RemoveNetworkDrive", v17);
    return v17;
  }
  cbMultiByte = WideCharToMultiByte(0, 0, a2, -1, 0, 0, 0, 0);
  if ( cbMultiByte )
  {
    v13 = cbMultiByte + 15LL;
    if ( v13 < cbMultiByte )
      v13 = 0xFFFFFFFFFFFFFF0LL;
    v14 = v13 & 0xFFFFFFFFFFFFFFF0uLL;
    v15 = alloca(v14);
    v16 = alloca(v14);
    if ( WideCharToMultiByte(0, 0, a2, -1, MultiByteStr, cbMultiByte, 0, 0) )
    {
      v11 = WNetCancelConnection2A(MultiByteStr, v9, v6);
      goto LABEL_19;
    }
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180008600  push    rbp
0x180008602  push    rbx
0x180008603  push    rsi
0x180008604  push    rdi
0x180008605  push    r14
0x180008607  sub     rsp, 50h
0x18000860b  lea     rbp, [rsp+40h]
0x180008610  mov     rax, cs:__security_cookie
0x180008617  xor     rax, rbp
0x18000861a  mov     [rbp+30h+var_28], rax
0x18000861e  mov     rsi, r9
0x180008621  mov     r14, rdx
0x180008624  test    rdx, rdx
0x180008627  jz      loc_180008793
0x18000862d  test    r8, r8
0x180008630  jz      loc_180008793
0x180008636  test    r9, r9
0x180008639  jz      loc_180008793
0x18000863f  xor     edi, edi
0x180008641  mov     rcx, r8; struct tagVARIANT *
0x180008644  mov     dword ptr [rbp+30h+MultiByteStr], edi
0x180008647  mov     [rbp+30h+var_2C], edi
0x18000864a  call    ?fOptionalArgSupplied@@YA_NPEBUtagVARIANT@@@Z; fOptionalArgSupplied(tagVARIANT const *)
0x18000864f  test    al, al
0x180008651  jz      short loc_180008667
0x180008653  lea     rdx, [rbp+30h+MultiByteStr]; int *
0x180008657  call    ?Variant_BOOL@@YAJPEAUtagVARIANT@@PEAH@Z; Variant_BOOL(tagVARIANT *,int *)
0x18000865c  test    eax, eax
0x18000865e  js      loc_180008798
0x180008664  mov     edi, dword ptr [rbp+30h+MultiByteStr]
0x180008667  mov     rcx, rsi; struct tagVARIANT *
0x18000866a  xor     ebx, ebx
0x18000866c  call    ?fOptionalArgSupplied@@YA_NPEBUtagVARIANT@@@Z; fOptionalArgSupplied(tagVARIANT const *)
0x180008671  test    al, al
0x180008673  jz      short loc_18000868F
0x180008675  lea     rdx, [rbp+30h+var_2C]; int *
0x180008679  call    ?Variant_BOOL@@YAJPEAUtagVARIANT@@PEAH@Z; Variant_BOOL(tagVARIANT *,int *)
0x18000867e  test    eax, eax
0x180008680  js      loc_180008798
0x180008686  cmp     [rbp+30h+var_2C], ebx
0x180008689  lea     eax, [rbx+1]
0x18000868c  cmovnz  ebx, eax
0x18000868f  cmp     cs:?g_fWindowsNT@Global@@2_NA, 0; bool Global::g_fWindowsNT
0x180008696  jz      short loc_1800086AB
0x180008698  mov     r8d, edi; fForce
0x18000869b  mov     edx, ebx; dwFlags
0x18000869d  mov     rcx, r14; lpName
0x1800086a0  call    cs:__imp_WNetCancelConnection2W
0x1800086a6  jmp     loc_180008766
0x1800086ab  mov     [rsp+70h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x1800086b4  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800086b8  mov     [rsp+70h+lpDefaultChar], 0; lpDefaultChar
0x1800086c1  mov     r8, r14; lpWideCharStr
0x1800086c4  mov     [rsp+70h+cbMultiByte], 0; cbMultiByte
0x1800086cc  xor     edx, edx; dwFlags
0x1800086ce  xor     ecx, ecx; CodePage
0x1800086d0  mov     [rsp+70h+lpMultiByteStr], 0; lpMultiByteStr
0x1800086d9  call    cs:__imp_WideCharToMultiByte
0x1800086df  movsxd  rdx, eax
0x1800086e2  test    eax, eax
0x1800086e4  jnz     short loc_180008701
0x1800086e6  call    cs:__imp_GetLastError
0x1800086ec  test    eax, eax
0x1800086ee  jle     loc_180008798
0x1800086f4  movzx   eax, ax
0x1800086f7  or      eax, 80070000h
0x1800086fc  jmp     loc_180008798
0x180008701  lea     rcx, [rdx+0Fh]
0x180008705  cmp     rcx, rdx
0x180008708  ja      short loc_180008714
0x18000870a  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180008714  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180008718  mov     rax, rcx
0x18000871b  call    _alloca_probe
0x180008720  sub     rsp, rcx
0x180008723  or      r9d, 0FFFFFFFFh; cchWideChar
0x180008727  mov     r8, r14; lpWideCharStr
0x18000872a  xor     ecx, ecx; CodePage
0x18000872c  mov     [rsp+70h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180008735  lea     rsi, [rsp+70h+MultiByteStr]
0x18000873a  mov     [rsp+70h+lpDefaultChar], 0; lpDefaultChar
0x180008743  mov     [rsp+70h+cbMultiByte], edx; cbMultiByte
0x180008747  xor     edx, edx; dwFlags
0x180008749  mov     [rsp+70h+lpMultiByteStr], rsi; lpMultiByteStr
0x18000874e  call    cs:__imp_WideCharToMultiByte
0x180008754  test    eax, eax
0x180008756  jz      short loc_1800086E6
0x180008758  mov     r8d, edi; fForce
0x18000875b  mov     edx, ebx; dwFlags
0x18000875d  mov     rcx, rsi; lpName
0x180008760  call    cs:__imp_WNetCancelConnection2A
0x180008766  mov     ebx, eax
0x180008768  test    eax, eax
0x18000876a  jle     short loc_180008777
0x18000876c  movzx   ebx, bx
0x18000876f  or      ebx, 80070000h
0x180008775  test    ebx, ebx
0x180008777  jns     short loc_18000878F
0x180008779  mov     r8d, ebx; int
0x18000877c  lea     rdx, aWshnetworkRemo; "WSHNetwork.RemoveNetworkDrive"
0x180008783  lea     rcx, IID_IWshNetwork; struct _GUID *
0x18000878a  call    ?Signal_ExceptionHR@@YAJAEBU_GUID@@PEBGJZZ; Signal_ExceptionHR(_GUID const &,ushort const *,long,...)
0x18000878f  mov     eax, ebx
0x180008791  jmp     short loc_180008798
0x180008793  mov     eax, 80004003h
0x180008798  mov     rcx, [rbp+30h+var_28]
0x18000879c  xor     rcx, rbp; StackCookie
0x18000879f  call    __security_check_cookie
0x1800087a4  lea     rsp, [rbp+10h]
0x1800087a8  pop     r14
0x1800087aa  pop     rdi
0x1800087ab  pop     rsi
0x1800087ac  pop     rbx
0x1800087ad  pop     rbp
0x1800087ae  retn
```
