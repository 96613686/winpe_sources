# SetBinaryProp<ushort,18>(ushort const *,unsigned __int64,tagVARIANT *)

- ea: `0x383a43090`
- end: `0x383a43210`
- name: `??$SetBinaryProp@G$0BC@@@YAJPEBG_KPEAUtagVARIANT@@@Z`
- size: `384`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x383867510`

## callees

- `0x3838427d0`
- `0x38391aed0`
- `0x38391afe0`
- `0x383a43090`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x383a431f3`
- `OLEAUT32!__imp_VariantClear` at `0x383a431f3`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x383a430e5`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x383a430e5`
- `OLEAUT32!__imp_SafeArrayLock` at `0x383a43132`
- `OLEAUT32!__imp_SafeArrayLock` at `0x383a43132`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x383a43175`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x383a43175`

## pseudocode

```c
__int64 __fastcall SetBinaryProp<unsigned short,18>(void *Src, unsigned __int64 a2, VARIANTARG *a3)
{
  SAFEARRAY *v6; // rax
  unsigned int v7; // ebx
  char *v8; // rcx
  __int64 v9; // rdx
  HRESULT v10; // eax
  HRESULT v11; // eax
  SAFEARRAYBOUND rgsabound; // [rsp+48h] [rbp+10h] BYREF

  rgsabound.cElements = a2;
  rgsabound.lLbound = 0;
  if ( !a2 || !Src || a2 >= 0xFFFF )
  {
    v7 = -2147024809;
    if ( (bidGblFlags & 2) != 0 )
    {
      v8 = `SetBinaryProp<unsigned short,18>'::`2'::_bidSrcFile2A[0];
      if ( off_383B49128[0] )
      {
        v9 = 2428969;
        goto LABEL_20;
      }
    }
LABEL_21:
    if ( a3 )
      VariantClear(a3);
    return v7;
  }
  v6 = SafeArrayCreate(0x12u, 1u, &rgsabound);
  a3->llVal = (LONGLONG)v6;
  if ( !v6 )
  {
    v7 = -2147024882;
    if ( (bidGblFlags & 2) != 0 )
    {
      v8 = `SetBinaryProp<unsigned short,18>'::`2'::_bidSrcFile2A[0];
      if ( off_383B49128[0] )
      {
        v9 = 2436137;
LABEL_20:
        bidTraceW(v8, v9, off_383B49128[0], v7);
        goto LABEL_21;
      }
    }
    goto LABEL_21;
  }
  v10 = SafeArrayLock(v6);
  v7 = v10;
  if ( v10 >= 0 )
  {
    memcpy(*(void **)(a3->llVal + 16), Src, 2 * a2);
    v11 = SafeArrayUnlock(a3->parray);
    v7 = v11;
    if ( v11 >= 0 )
    {
      a3->vt = 8210;
    }
    else if ( (bidGblFlags & 2) != 0 )
    {
      bidTraceHR(`SetBinaryProp<unsigned short,18>'::`2'::_bidSrcFile2A[0], 2449417, (unsigned int)v11);
    }
  }
  else if ( (bidGblFlags & 2) != 0 )
  {
    bidTraceHR(`SetBinaryProp<unsigned short,18>'::`2'::_bidSrcFile2A[0], 2442249, (unsigned int)v10);
  }
  if ( (v7 & 0x80000000) != 0 )
    goto LABEL_21;
  return v7;
}

```

## disassembly

```asm
0x383a43090  mov     [rsp+arg_0], rbx
0x383a43095  mov     [rsp+arg_10], rbp
0x383a4309a  mov     [rsp+arg_18], rsi
0x383a4309f  push    rdi
0x383a430a0  sub     rsp, 30h
0x383a430a4  mov     rdi, r8
0x383a430a7  mov     rsi, rdx
0x383a430aa  mov     rbp, rcx
0x383a430ad  mov     [rsp+38h+rgsabound.cElements], edx
0x383a430b1  mov     [rsp+38h+rgsabound.lLbound], 0
0x383a430b9  test    rdx, rdx
0x383a430bc  jz      loc_383A431AE
0x383a430c2  test    rcx, rcx
0x383a430c5  jz      loc_383A431AE
0x383a430cb  cmp     rdx, 0FFFFh
0x383a430d2  jnb     loc_383A431AE
0x383a430d8  mov     ecx, 12h; vt
0x383a430dd  lea     r8, [rsp+38h+rgsabound]; rgsabound
0x383a430e2  lea     edx, [rcx-11h]; cDims
0x383a430e5  call    cs:__imp_SafeArrayCreate
0x383a430eb  mov     [rdi+8], rax
0x383a430ef  test    rax, rax
0x383a430f2  jnz     short loc_383A4312F
0x383a430f4  test    byte ptr cs:_bidGblFlags, 2
0x383a430fb  mov     ebx, 8007000Eh
0x383a43100  jz      loc_383A431EB
0x383a43106  mov     rcx, cs:?_bidSrcFile2A@?1???$SetBinaryProp@G$0BC@@@YAJPEBG_KPEAUtagVARIANT@@@Z@4REBDEB; char const * const `SetBinaryProp<ushort,18>(ushort const *,unsigned __int64,tagVARIANT *)'::`2'::_bidSrcFile2A
0x383a4310d  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383a43114  test    rax, rax
0x383a43117  jz      loc_383A431EB
0x383a4311d  mov     [rsp+38h+var_18], 94Bh
0x383a43125  mov     edx, 252C29h
0x383a4312a  jmp     loc_383A431DC
0x383a4312f  mov     rcx, rax; psa
0x383a43132  call    cs:__imp_SafeArrayLock
0x383a43138  mov     ebx, eax
0x383a4313a  test    eax, eax
0x383a4313c  jns     short loc_383A4315D
0x383a4313e  test    byte ptr cs:_bidGblFlags, 2
0x383a43145  jz      short loc_383A431A8
0x383a43147  mov     rcx, cs:?_bidSrcFile2A@?1???$SetBinaryProp@G$0BC@@@YAJPEBG_KPEAUtagVARIANT@@@Z@4REBDEB; char const * const `SetBinaryProp<ushort,18>(ushort const *,unsigned __int64,tagVARIANT *)'::`2'::_bidSrcFile2A
0x383a4314e  mov     r8d, eax
0x383a43151  mov     edx, 254409h
0x383a43156  call    _bidTraceHR
0x383a4315b  jmp     short loc_383A431A8
0x383a4315d  mov     rcx, [rdi+8]
0x383a43161  lea     r8, [rsi+rsi]; Size
0x383a43165  mov     rdx, rbp; Src
0x383a43168  mov     rcx, [rcx+10h]; void *
0x383a4316c  call    memcpy
0x383a43171  mov     rcx, [rdi+8]; psa
0x383a43175  call    cs:__imp_SafeArrayUnlock
0x383a4317b  mov     ebx, eax
0x383a4317d  test    eax, eax
0x383a4317f  jns     short loc_383A431A0
0x383a43181  test    byte ptr cs:_bidGblFlags, 2
0x383a43188  jz      short loc_383A431A8
0x383a4318a  mov     rcx, cs:?_bidSrcFile2A@?1???$SetBinaryProp@G$0BC@@@YAJPEBG_KPEAUtagVARIANT@@@Z@4REBDEB; char const * const `SetBinaryProp<ushort,18>(ushort const *,unsigned __int64,tagVARIANT *)'::`2'::_bidSrcFile2A
0x383a43191  mov     r8d, eax
0x383a43194  mov     edx, 256009h
0x383a43199  call    _bidTraceHR
0x383a4319e  jmp     short loc_383A431A8
0x383a431a0  mov     eax, 2012h
0x383a431a5  mov     [rdi], ax
0x383a431a8  test    ebx, ebx
0x383a431aa  js      short loc_383A431EB
0x383a431ac  jmp     short loc_383A431F9
0x383a431ae  test    byte ptr cs:_bidGblFlags, 2
0x383a431b5  mov     ebx, 80070057h
0x383a431ba  jz      short loc_383A431EB
0x383a431bc  mov     rcx, cs:?_bidSrcFile2A@?1???$SetBinaryProp@G$0BC@@@YAJPEBG_KPEAUtagVARIANT@@@Z@4REBDEB; char const * const `SetBinaryProp<ushort,18>(ushort const *,unsigned __int64,tagVARIANT *)'::`2'::_bidSrcFile2A
0x383a431c3  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383a431ca  test    rax, rax
0x383a431cd  jz      short loc_383A431EB
0x383a431cf  mov     [rsp+38h+var_18], 944h
0x383a431d7  mov     edx, 251029h
0x383a431dc  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383a431e3  mov     r9d, ebx
0x383a431e6  call    _bidTraceW
0x383a431eb  test    rdi, rdi
0x383a431ee  jz      short loc_383A431F9
0x383a431f0  mov     rcx, rdi; pvarg
0x383a431f3  call    cs:__imp_VariantClear
0x383a431f9  mov     rbp, [rsp+38h+arg_10]
0x383a431fe  mov     rsi, [rsp+38h+arg_18]
0x383a43203  mov     eax, ebx
0x383a43205  mov     rbx, [rsp+38h+arg_0]
0x383a4320a  add     rsp, 30h
0x383a4320e  pop     rdi
0x383a4320f  retn
```
