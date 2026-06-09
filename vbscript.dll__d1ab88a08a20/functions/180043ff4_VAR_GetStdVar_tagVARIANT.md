# VAR::GetStdVar(tagVARIANT *)

- ea: `0x180043ff4`
- end: `0x180044087`
- name: `?GetStdVar@VAR@@QEAAJPEAUtagVARIANT@@@Z`
- size: `147`
- prototype: `HRESULT __fastcall(VAR *this, struct tagVARIANT *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18001cb70`
- `0x18006cd20`

## callees

- `0x180002e60`
- `0x180026150`
- `0x180043ff4`
- `0x180079490`

## import_xrefs

- `OLEAUT32!__imp_VariantCopyInd` at `0x180044054`
- `OLEAUT32!__imp_VariantCopyInd` at `0x180044054`

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
0x180043ff4  push    rbx
0x180043ff6  sub     rsp, 40h
0x180043ffa  mov     rax, cs:__security_cookie
0x180044001  xor     rax, rsp
0x180044004  mov     [rsp+48h+var_10], rax
0x180044009  xor     eax, eax
0x18004400b  xorps   xmm0, xmm0
0x18004400e  movups  xmmword ptr [rsp+48h+pvarDest], xmm0
0x180044013  mov     qword ptr [rsp+48h+pvarDest+10h], rax
0x180044018  mov     rbx, rdx
0x18004401b  call    ?PvarCutAll@VAR@@QEAAPEAV1@XZ; VAR::PvarCutAll(void)
0x180044020  mov     r9, rax
0x180044023  movzx   r10d, word ptr [rax]
0x180044027  mov     ecx, r10d; int
0x18004402a  call    ?IsSimpleType@VAR@@SAHH@Z; VAR::IsSimpleType(int)
0x18004402f  test    eax, eax
0x180044031  jz      short loc_18004404C
0x180044033  bt      r10w, 0Eh
0x180044039  jb      short loc_18004404C
0x18004403b  movups  xmm0, xmmword ptr [r9]
0x18004403f  xor     eax, eax
0x180044041  movups  xmmword ptr [rbx], xmm0
0x180044044  movsd   xmm1, qword ptr [r9+10h]
0x18004404a  jmp     short loc_18004406E
0x18004404c  mov     rdx, r9; pvargSrc
0x18004404f  lea     rcx, [rsp+48h+pvarDest]; pvarDest
0x180044054  call    cs:__imp_VariantCopyInd
0x18004405b  nop     dword ptr [rax+rax+00h]
0x180044060  movups  xmm0, xmmword ptr [rsp+48h+pvarDest]
0x180044065  movsd   xmm1, qword ptr [rsp+48h+pvarDest+10h]
0x18004406b  movups  xmmword ptr [rbx], xmm0
0x18004406e  movsd   qword ptr [rbx+10h], xmm1
0x180044073  mov     rcx, [rsp+48h+var_10]
0x180044078  xor     rcx, rsp; StackCookie
0x18004407b  call    __security_check_cookie
0x180044080  add     rsp, 40h
0x180044084  pop     rbx
0x180044085  retn
```
