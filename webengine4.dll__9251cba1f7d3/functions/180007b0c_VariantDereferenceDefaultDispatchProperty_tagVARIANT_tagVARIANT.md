# VariantDereferenceDefaultDispatchProperty(tagVARIANT *,tagVARIANT *)

- ea: `0x180007b0c`
- end: `0x180007c08`
- name: `?VariantDereferenceDefaultDispatchProperty@@YAJPEAUtagVARIANT@@0@Z`
- size: `252`
- prototype: `__int64 __fastcall(VARIANTARG *pvarg, VARIANTARG *pvargSrc)`
- caller_count: `4`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180005130`
- `0x1800074e4`
- `0x180007524`
- `0x1800079c0`

## callees

- `0x180007b0c`
- `0x180065b60`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180007b31`
- `OLEAUT32!__imp_VariantInit` at `0x180007b72`
- `OLEAUT32!__imp_VariantInit` at `0x180007b31`
- `OLEAUT32!__imp_VariantInit` at `0x180007b72`
- `OLEAUT32!__imp_VariantClear` at `0x180007bd2`
- `OLEAUT32!__imp_VariantClear` at `0x180007bd2`
- `OLEAUT32!__imp_VariantCopy` at `0x180007b4f`
- `OLEAUT32!__imp_VariantCopy` at `0x180007b4f`
- `OLEAUT32!__imp_VariantCopyInd` at `0x180007b47`
- `OLEAUT32!__imp_VariantCopyInd` at `0x180007b47`

## pseudocode

```c
__int64 __fastcall VariantDereferenceDefaultDispatchProperty(VARIANTARG *pvarg, VARIANTARG *pvargSrc)
{
  HRESULT v4; // eax
  IRecordInfo *pRecInfo; // xmm1_8
  int v7; // [rsp+20h] [rbp-A8h]
  __int128 v8; // [rsp+50h] [rbp-78h] BYREF
  int v9; // [rsp+60h] [rbp-68h]
  int v10; // [rsp+64h] [rbp-64h]
  VARIANTARG pvarga; // [rsp+68h] [rbp-60h] BYREF
  _BYTE v12[72]; // [rsp+80h] [rbp-48h] BYREF

  v9 = 0;
  v10 = 0;
  v8 = 0;
  VariantInit(pvarg);
  if ( (pvargSrc->vt & 0x4000) != 0 )
    v4 = VariantCopyInd(pvarg, pvargSrc);
  else
    v4 = VariantCopy(pvarg, pvargSrc);
  if ( !v4 )
  {
    while ( pvarg->vt == 9 )
    {
      if ( !pvarg->llVal )
        break;
      VariantInit(&pvarga);
      LOWORD(v7) = 3;
      if ( (*(unsigned int (__fastcall **)(LONGLONG, _QWORD, GUID *, __int64, int, __int128 *, VARIANTARG *, _BYTE *, _QWORD))(*pvarg->pllVal + 48))(
             pvarg->llVal,
             0,
             &GUID_NULL,
             2048,
             v7,
             &v8,
             &pvarga,
             v12,
             0) )
      {
        break;
      }
      VariantClear(pvarg);
      pRecInfo = pvarga.pRecInfo;
      *(_OWORD *)&pvarg->vt = *(_OWORD *)&pvarga.vt;
      pvarg->pRecInfo = pRecInfo;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180007b0c  mov     rax, rsp
0x180007b0f  mov     [rax+8], rbx
0x180007b13  push    rdi
0x180007b14  sub     rsp, 0C0h
0x180007b1b  and     dword ptr [rax-68h], 0
0x180007b1f  xorps   xmm0, xmm0
0x180007b22  and     dword ptr [rax-64h], 0
0x180007b26  mov     rdi, rdx
0x180007b29  movdqu  xmmword ptr [rax-78h], xmm0
0x180007b2e  mov     rbx, rcx
0x180007b31  call    cs:__imp_VariantInit
0x180007b37  mov     eax, 4000h
0x180007b3c  mov     rdx, rdi; pvargSrc
0x180007b3f  mov     rcx, rbx; pvargDest
0x180007b42  test    [rdi], ax
0x180007b45  jz      short loc_180007B4F
0x180007b47  call    cs:__imp_VariantCopyInd
0x180007b4d  jmp     short loc_180007B55
0x180007b4f  call    cs:__imp_VariantCopy
0x180007b55  test    eax, eax
0x180007b57  jnz     loc_180007BF5
0x180007b5d  jmp     loc_180007BEB
0x180007b62  cmp     qword ptr [rbx+8], 0
0x180007b67  jz      loc_180007BF5
0x180007b6d  lea     rcx, [rsp+0C8h+pvarg]; pvarg
0x180007b72  call    cs:__imp_VariantInit
0x180007b78  and     [rsp+0C8h+var_88], 0
0x180007b7e  lea     rdx, [rsp+0C8h+var_48]
0x180007b86  mov     rcx, [rbx+8]
0x180007b8a  mov     r8d, 3
0x180007b90  mov     [rsp+0C8h+var_90], rdx
0x180007b95  mov     r9d, 800h
0x180007b9b  lea     rdx, [rsp+0C8h+pvarg]
0x180007ba0  mov     [rsp+0C8h+var_98], rdx
0x180007ba5  lea     rdx, [rsp+0C8h+var_78]
0x180007baa  mov     rax, [rcx]
0x180007bad  mov     [rsp+0C8h+var_A0], rdx
0x180007bb2  xor     edx, edx
0x180007bb4  mov     [rsp+0C8h+var_A8], r8w
0x180007bba  lea     r8, GUID_NULL
0x180007bc1  mov     rax, [rax+30h]
0x180007bc5  call    cs:__guard_dispatch_icall_fptr
0x180007bcb  test    eax, eax
0x180007bcd  jnz     short loc_180007BF5
0x180007bcf  mov     rcx, rbx; pvarg
0x180007bd2  call    cs:__imp_VariantClear
0x180007bd8  movups  xmm0, xmmword ptr [rsp+0C8h+pvarg]
0x180007bdd  movsd   xmm1, qword ptr [rsp+0C8h+pvarg+10h]
0x180007be3  movups  xmmword ptr [rbx], xmm0
0x180007be6  movsd   qword ptr [rbx+10h], xmm1
0x180007beb  cmp     word ptr [rbx], 9
0x180007bef  jz      loc_180007B62
0x180007bf5  mov     rbx, [rsp+0C8h+arg_0]
0x180007bfd  xor     eax, eax
0x180007bff  add     rsp, 0C0h
0x180007c06  pop     rdi
0x180007c07  retn
```
