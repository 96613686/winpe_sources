# VAR::GetStdVar(tagVARIANT *)

- ea: `0x180042974`
- end: `0x180042a00`
- name: `?GetStdVar@VAR@@QEAAJPEAUtagVARIANT@@@Z`
- size: `140`
- prototype: `__int64 __fastcall(VAR *__hidden this, struct tagVARIANT *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180021540`
- `0x18006abd0`

## callees

- `0x180003850`
- `0x18001bd20`
- `0x180042974`
- `0x1800767a0`

## import_xrefs

- `OLEAUT32!__imp_VariantCopyInd` at `0x1800429d4`
- `OLEAUT32!__imp_VariantCopyInd` at `0x1800429d4`

## pseudocode

```c
HRESULT __fastcall VAR::GetStdVar(VAR *this, struct tagVARIANT *a2)
{
  struct VAR *v3; // rax
  const VARIANTARG *v4; // r9
  __int16 v5; // r10
  HRESULT result; // eax
  IRecordInfo *pRecInfo; // xmm1_8
  VARIANT pvarDest; // [rsp+20h] [rbp-28h] BYREF

  memset(&pvarDest, 0, sizeof(pvarDest));
  v3 = VAR::PvarCutAll(this);
  if ( !(unsigned int)VAR::IsSimpleType(*(unsigned __int16 *)v3) || (v5 & 0x4000) != 0 )
  {
    result = VariantCopyInd(&pvarDest, v4);
    pRecInfo = pvarDest.pRecInfo;
    *(_OWORD *)&a2->vt = *(_OWORD *)&pvarDest.vt;
  }
  else
  {
    result = 0;
    *(_OWORD *)&a2->vt = *(_OWORD *)&v4->vt;
    pRecInfo = v4->pRecInfo;
  }
  a2->pRecInfo = pRecInfo;
  return result;
}

```

## disassembly

```asm
0x180042974  push    rbx
0x180042976  sub     rsp, 40h
0x18004297a  mov     rax, cs:__security_cookie
0x180042981  xor     rax, rsp
0x180042984  mov     [rsp+48h+var_10], rax
0x180042989  xor     eax, eax
0x18004298b  xorps   xmm0, xmm0
0x18004298e  movups  xmmword ptr [rsp+48h+pvarDest], xmm0
0x180042993  mov     qword ptr [rsp+48h+pvarDest+10h], rax
0x180042998  mov     rbx, rdx
0x18004299b  call    ?PvarCutAll@VAR@@QEAAPEAV1@XZ; VAR::PvarCutAll(void)
0x1800429a0  mov     r9, rax
0x1800429a3  movzx   r10d, word ptr [rax]
0x1800429a7  mov     ecx, r10d; int
0x1800429aa  call    ?IsSimpleType@VAR@@SAHH@Z; VAR::IsSimpleType(int)
0x1800429af  test    eax, eax
0x1800429b1  jz      short loc_1800429CC
0x1800429b3  bt      r10w, 0Eh
0x1800429b9  jb      short loc_1800429CC
0x1800429bb  movups  xmm0, xmmword ptr [r9]
0x1800429bf  xor     eax, eax
0x1800429c1  movups  xmmword ptr [rbx], xmm0
0x1800429c4  movsd   xmm1, qword ptr [r9+10h]
0x1800429ca  jmp     short loc_1800429E8
0x1800429cc  mov     rdx, r9; pvargSrc
0x1800429cf  lea     rcx, [rsp+48h+pvarDest]; pvarDest
0x1800429d4  call    cs:__imp_VariantCopyInd
0x1800429da  movups  xmm0, xmmword ptr [rsp+48h+pvarDest]
0x1800429df  movsd   xmm1, qword ptr [rsp+48h+pvarDest+10h]
0x1800429e5  movups  xmmword ptr [rbx], xmm0
0x1800429e8  movsd   qword ptr [rbx+10h], xmm1
0x1800429ed  mov     rcx, [rsp+48h+var_10]
0x1800429f2  xor     rcx, rsp; StackCookie
0x1800429f5  call    __security_check_cookie
0x1800429fa  add     rsp, 40h
0x1800429fe  pop     rbx
0x1800429ff  retn
```
