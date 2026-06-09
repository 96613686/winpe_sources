# AspCompatRequest::BinaryRead(tagVARIANT *,tagVARIANT *)

- ea: `0x180004ff0`
- end: `0x18000512e`
- name: `?BinaryRead@AspCompatRequest@@UEAAJPEAUtagVARIANT@@0@Z`
- size: `318`
- prototype: `int(AspCompatRequest *__hidden this, struct tagVARIANT *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004ff0`
- `0x180065b60`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180005018`
- `OLEAUT32!__imp_VariantInit` at `0x180005021`
- `OLEAUT32!__imp_VariantInit` at `0x180005018`
- `OLEAUT32!__imp_VariantInit` at `0x180005021`
- `OLEAUT32!__imp_VariantClear` at `0x1800050e6`
- `OLEAUT32!__imp_VariantClear` at `0x180005113`
- `OLEAUT32!__imp_VariantClear` at `0x1800050e6`
- `OLEAUT32!__imp_VariantClear` at `0x180005113`
- `OLEAUT32!__imp_VariantChangeType` at `0x180005054`
- `OLEAUT32!__imp_VariantChangeType` at `0x180005054`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180005077`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180005077`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800050a0`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800050a0`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800050dd`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800050dd`

## pseudocode

```c
__int64 __fastcall AspCompatRequest::BinaryRead(AspCompatRequest *this, struct tagVARIANT *a2, struct tagVARIANT *a3)
{
  SAFEARRAY *v4; // rsi
  __int64 v7; // r12
  unsigned int v8; // ebx
  ULONG Lo; // r15d
  LONG v10; // eax
  IRecordInfo *pRecInfo; // xmm1_8
  VARIANTARG pvarg; // [rsp+30h] [rbp-20h] BYREF
  LONG v14; // [rsp+90h] [rbp+40h] BYREF
  void *ppvData; // [rsp+98h] [rbp+48h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+A8h] [rbp+58h] BYREF

  v4 = 0;
  v14 = 0;
  ppvData = 0;
  VariantInit(&pvarg);
  VariantInit(a3);
  v7 = *(_QWORD *)(*((_QWORD *)this + 9) + 48LL);
  if ( v7 )
  {
    if ( a2->vt == 3 || (v8 = VariantChangeType(a2, a2, 0, 3u)) == 0 )
    {
      Lo = a2->cyVal.Lo;
      rgsabound.lLbound = 0;
      rgsabound.cElements = Lo;
      v4 = SafeArrayCreate(0x11u, 1u, &rgsabound);
      if ( v4 )
      {
        pvarg.llVal = (LONGLONG)v4;
        pvarg.vt = 8209;
        v8 = SafeArrayAccessData(v4, &ppvData);
        if ( !v8 )
          v8 = (*(__int64 (__fastcall **)(__int64, void *, _QWORD, LONG *))(*(_QWORD *)v7 + 128LL))(
                 v7,
                 ppvData,
                 Lo,
                 &v14);
      }
      else
      {
        v8 = -2147024882;
      }
    }
  }
  else
  {
    v8 = -2147418113;
  }
  if ( ppvData )
    SafeArrayUnaccessData(v4);
  VariantClear(a2);
  a2->vt = 3;
  if ( v8 )
  {
    VariantClear(&pvarg);
    a2->lVal = 0;
  }
  else
  {
    v10 = v14;
    pRecInfo = pvarg.pRecInfo;
    *(_OWORD *)&a3->vt = *(_OWORD *)&pvarg.vt;
    a3->pRecInfo = pRecInfo;
    a2->lVal = v10;
  }
  return v8;
}

```

## disassembly

```asm
0x180004ff0  push    rbp
0x180004ff2  push    rbx
0x180004ff3  push    rsi
0x180004ff4  push    rdi
0x180004ff5  push    r12
0x180004ff7  push    r14
0x180004ff9  push    r15
0x180004ffb  mov     rbp, rsp
0x180004ffe  sub     rsp, 50h
0x180005002  mov     rbx, rcx
0x180005005  xor     esi, esi
0x180005007  and     [rbp+arg_0], esi
0x18000500a  lea     rcx, [rbp+pvarg]; pvarg
0x18000500e  and     [rbp+ppvData], rsi
0x180005012  mov     r14, r8
0x180005015  mov     rdi, rdx
0x180005018  call    cs:__imp_VariantInit
0x18000501e  mov     rcx, r14; pvarg
0x180005021  call    cs:__imp_VariantInit
0x180005027  mov     rax, [rbx+48h]
0x18000502b  lea     r15d, [rsi+3]
0x18000502f  mov     r12, [rax+30h]
0x180005033  test    r12, r12
0x180005036  jnz     short loc_180005042
0x180005038  mov     ebx, 8000FFFFh
0x18000503d  jmp     loc_1800050D3
0x180005042  cmp     [rdi], r15w
0x180005046  jz      short loc_180005060
0x180005048  mov     r9d, r15d; vt
0x18000504b  xor     r8d, r8d; wFlags
0x18000504e  mov     rdx, rdi; pvarSrc
0x180005051  mov     rcx, rdi; pvargDest
0x180005054  call    cs:__imp_VariantChangeType
0x18000505a  mov     ebx, eax
0x18000505c  test    eax, eax
0x18000505e  jnz     short loc_1800050D3
0x180005060  mov     r15d, [rdi+8]
0x180005064  lea     r8, [rbp+rgsabound]; rgsabound
0x180005068  and     [rbp+rgsabound.lLbound], esi
0x18000506b  mov     ecx, 11h; vt
0x180005070  mov     [rbp+rgsabound.cElements], r15d
0x180005074  lea     edx, [rcx-10h]; cDims
0x180005077  call    cs:__imp_SafeArrayCreate
0x18000507d  mov     rsi, rax
0x180005080  test    rax, rax
0x180005083  jnz     short loc_18000508C
0x180005085  mov     ebx, 8007000Eh
0x18000508a  jmp     short loc_1800050CD
0x18000508c  mov     eax, 2011h
0x180005091  mov     qword ptr [rbp+pvarg+8], rsi
0x180005095  lea     rdx, [rbp+ppvData]; ppvData
0x180005099  mov     word ptr [rbp+pvarg], ax
0x18000509d  mov     rcx, rsi; psa
0x1800050a0  call    cs:__imp_SafeArrayAccessData
0x1800050a6  mov     ebx, eax
0x1800050a8  test    eax, eax
0x1800050aa  jnz     short loc_1800050CD
0x1800050ac  mov     rax, [r12]
0x1800050b0  lea     r9, [rbp+arg_0]
0x1800050b4  mov     rdx, [rbp+ppvData]
0x1800050b8  mov     r8d, r15d
0x1800050bb  mov     rcx, r12
0x1800050be  mov     rax, [rax+80h]
0x1800050c5  call    cs:__guard_dispatch_icall_fptr
0x1800050cb  mov     ebx, eax
0x1800050cd  mov     r15d, 3
0x1800050d3  cmp     [rbp+ppvData], 0
0x1800050d8  jz      short loc_1800050E3
0x1800050da  mov     rcx, rsi; psa
0x1800050dd  call    cs:__imp_SafeArrayUnaccessData
0x1800050e3  mov     rcx, rdi; pvarg
0x1800050e6  call    cs:__imp_VariantClear
0x1800050ec  mov     [rdi], r15w
0x1800050f0  test    ebx, ebx
0x1800050f2  jnz     short loc_18000510F
0x1800050f4  movups  xmm0, xmmword ptr [rbp+pvarg]
0x1800050f8  mov     eax, [rbp+arg_0]
0x1800050fb  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x180005100  movups  xmmword ptr [r14], xmm0
0x180005104  movsd   qword ptr [r14+10h], xmm1
0x18000510a  mov     [rdi+8], eax
0x18000510d  jmp     short loc_18000511D
0x18000510f  lea     rcx, [rbp+pvarg]; pvarg
0x180005113  call    cs:__imp_VariantClear
0x180005119  and     dword ptr [rdi+8], 0
0x18000511d  mov     eax, ebx
0x18000511f  add     rsp, 50h
0x180005123  pop     r15
0x180005125  pop     r14
0x180005127  pop     r12
0x180005129  pop     rdi
0x18000512a  pop     rsi
0x18000512b  pop     rbx
0x18000512c  pop     rbp
0x18000512d  retn
```
