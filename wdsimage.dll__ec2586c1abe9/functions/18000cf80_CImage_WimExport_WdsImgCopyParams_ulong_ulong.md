# CImage::WimExport(WdsImgCopyParams *,ulong,ulong *)

- ea: `0x18000cf80`
- end: `0x18000d0e1`
- name: `?WimExport@CImage@@AEAAJPEAUWdsImgCopyParams@@KPEAK@Z`
- size: `353`
- prototype: `__int64 __fastcall(CImage *__hidden this, struct WdsImgCopyParams *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180009cb4`

## callees

- `0x1800093d8`
- `0x18000cf80`
- `0x18000d5b0`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall CImage::WimExport(CImage *this, struct WdsImgCopyParams *a2, int a3, unsigned int *a4)
{
  int v4; // edi
  int v5; // eax
  __int64 v6; // rbx
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // ecx
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rcx
  _QWORD *v20; // [rsp+30h] [rbp-40h] BYREF
  _OWORD v21[3]; // [rsp+38h] [rbp-38h] BYREF
  __int64 v22; // [rsp+68h] [rbp-8h]
  unsigned int v23; // [rsp+A0h] [rbp+30h] BYREF

  v20 = 0;
  v23 = 0;
  v4 = 0;
  v22 = 0;
  v5 = 259;
  LODWORD(v6) = 0;
  memset(v21, 0, 32);
  if ( a3 != 256 )
    v5 = a3;
  v21[2] = 0;
  v10 = v5 - 256;
  if ( v10 )
  {
    v11 = v10 - 1;
    if ( !v11 )
      goto LABEL_10;
    v12 = v11 - 1;
    if ( !v12 )
    {
      v4 = 1;
      goto LABEL_10;
    }
    if ( v12 == 1 )
    {
      v4 = 2;
      goto LABEL_10;
    }
  }
  LODWORD(v6) = -1056833008;
LABEL_10:
  if ( (int)ElValidateHr_5((unsigned int)v6, 1, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 2919) >= 0 )
  {
    v13 = *((_DWORD *)a2 + 7);
    v14 = LODWORD(v21[0]) | 0x10;
    *((_DWORD *)a2 + 14) = 0;
    LODWORD(v22) = v4;
    if ( (unsigned int)(v13 - 2) <= 1 )
      v14 = 1;
    v15 = *((_QWORD *)this + 49);
    LODWORD(v21[0]) = v14;
    v6 = (unsigned int)CDepCopyConnector<&public: long CImage::WimCallback(_DEP_IMAGE_COPY_CALLBACK_PARAMS *,WdsImgCopyParams *,int *)>::Copy(
                         (__int64)this,
                         v15,
                         (__int64)a2,
                         (__int64)v21,
                         (__int64)&v20);
    if ( (int)ElValidateHr_5(v6, v16, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 2945) >= 0 )
    {
      v6 = (*(unsigned int (__fastcall **)(_QWORD *, unsigned int *))(*v20 + 8LL))(v20, &v23);
      if ( (int)ElValidateHr_5(v6, v17, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 2951) >= 0 )
        *a4 = v23;
    }
  }
  if ( v20 )
  {
    v18 = (__int64)v20 + *(int *)(v20[1] + 4LL) + 8;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000cf80  mov     [rsp-18h+arg_0], rbx
0x18000cf85  mov     [rsp-18h+arg_8], rsi
0x18000cf8a  mov     [rsp-18h+arg_18], rdi
0x18000cf8f  push    rbp
0x18000cf90  push    r14
0x18000cf92  push    r15
0x18000cf94  mov     rbp, rsp
0x18000cf97  sub     rsp, 70h
0x18000cf9b  and     [rbp+var_40], 0
0x18000cfa0  xor     eax, eax
0x18000cfa2  and     [rbp+arg_10], 0
0x18000cfa6  xor     edi, edi
0x18000cfa8  mov     [rbp+var_8], rax
0x18000cfac  xorps   xmm0, xmm0
0x18000cfaf  mov     eax, 103h
0x18000cfb4  xor     ebx, ebx
0x18000cfb6  mov     r15, rcx
0x18000cfb9  mov     r14, rdx
0x18000cfbc  mov     rsi, r9
0x18000cfbf  lea     edx, [rdi+1]
0x18000cfc2  movups  [rbp+var_38], xmm0
0x18000cfc6  lea     ecx, [rax-3]
0x18000cfc9  cmp     r8d, ecx
0x18000cfcc  movups  [rbp+var_28], xmm0
0x18000cfd0  cmovnz  eax, r8d
0x18000cfd4  movups  [rbp+var_18], xmm0
0x18000cfd8  sub     eax, ecx
0x18000cfda  jz      short loc_18000CFF1
0x18000cfdc  sub     eax, edx
0x18000cfde  jz      short loc_18000CFF6
0x18000cfe0  sub     eax, edx
0x18000cfe2  jz      short loc_18000CFED
0x18000cfe4  cmp     eax, edx
0x18000cfe6  jnz     short loc_18000CFF1
0x18000cfe8  lea     edi, [rbx+2]
0x18000cfeb  jmp     short loc_18000CFF6
0x18000cfed  mov     edi, edx
0x18000cfef  jmp     short loc_18000CFF6
0x18000cff1  mov     ebx, 0C1020210h
0x18000cff6  mov     r9d, 0B67h
0x18000cffc  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000d003  mov     ecx, ebx
0x18000d005  call    ElValidateHr_5
0x18000d00a  test    eax, eax
0x18000d00c  js      loc_18000D0A0
0x18000d012  mov     ecx, dword ptr [rbp+var_38]
0x18000d015  lea     r9, [rbp+var_38]
0x18000d019  mov     eax, [r14+1Ch]
0x18000d01d  or      ecx, 10h
0x18000d020  and     dword ptr [r14+38h], 0
0x18000d025  sub     eax, 2
0x18000d028  mov     edx, 1
0x18000d02d  mov     dword ptr [rbp+var_8], edi
0x18000d030  cmp     eax, edx
0x18000d032  mov     r8, r14
0x18000d035  lea     rax, [rbp+var_40]
0x18000d039  cmovbe  ecx, edx
0x18000d03c  mov     [rsp+70h+var_50], rax
0x18000d041  mov     rdx, [r15+188h]
0x18000d048  mov     dword ptr [rbp+var_38], ecx
0x18000d04b  mov     rcx, r15
0x18000d04e  call    ?Copy@?$CDepCopyConnector@$1?WimCallback@CImage@@QEAAJPEAU_DEP_IMAGE_COPY_CALLBACK_PARAMS@@PEAUWdsImgCopyParams@@PEAH@Z@@SAJPEAVCImage@@PEAVIDepImageResolved@@PEAUWdsImgCopyParams@@PEAU_DEP_IMAGE_COPY_PARAMS@@PEAPEAVIDepImage@@@Z; CDepCopyConnector<&CImage::WimCallback(_DEP_IMAGE_COPY_CALLBACK_PARAMS *,WdsImgCopyParams *,int *)>::Copy(CImage *,IDepImageResolved *,WdsImgCopyParams *,_DEP_IMAGE_COPY_PARAMS *,IDepImage * *)
0x18000d053  mov     r9d, 0B81h
0x18000d059  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000d060  mov     ecx, eax
0x18000d062  mov     ebx, eax
0x18000d064  call    ElValidateHr_5
0x18000d069  test    eax, eax
0x18000d06b  js      short loc_18000D0A0
0x18000d06d  mov     rcx, [rbp+var_40]
0x18000d071  lea     rdx, [rbp+arg_10]
0x18000d075  mov     rax, [rcx]
0x18000d078  mov     rax, [rax+8]
0x18000d07c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d081  mov     r9d, 0B87h
0x18000d087  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000d08e  mov     ecx, eax
0x18000d090  mov     ebx, eax
0x18000d092  call    ElValidateHr_5
0x18000d097  test    eax, eax
0x18000d099  js      short loc_18000D0A0
0x18000d09b  mov     eax, [rbp+arg_10]
0x18000d09e  mov     [rsi], eax
0x18000d0a0  mov     rdx, [rbp+var_40]
0x18000d0a4  test    rdx, rdx
0x18000d0a7  jz      short loc_18000D0C4
0x18000d0a9  mov     rax, [rdx+8]
0x18000d0ad  add     rdx, 8
0x18000d0b1  movsxd  rcx, dword ptr [rax+4]
0x18000d0b5  add     rcx, rdx
0x18000d0b8  mov     rax, [rcx]
0x18000d0bb  mov     rax, [rax+10h]
0x18000d0bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0c4  lea     r11, [rsp+70h+var_s0]
0x18000d0c9  mov     eax, ebx
0x18000d0cb  mov     rbx, [r11+20h]
0x18000d0cf  mov     rsi, [r11+28h]
0x18000d0d3  mov     rdi, [r11+38h]
0x18000d0d7  mov     rsp, r11
0x18000d0da  pop     r15
0x18000d0dc  pop     r14
0x18000d0de  pop     rbp
0x18000d0df  retn
```
