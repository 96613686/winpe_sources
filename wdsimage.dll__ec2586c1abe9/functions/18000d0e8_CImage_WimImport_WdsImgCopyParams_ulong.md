# CImage::WimImport(WdsImgCopyParams *,ulong)

- ea: `0x18000d0e8`
- end: `0x18000d1c1`
- name: `?WimImport@CImage@@AEAAJPEAUWdsImgCopyParams@@K@Z`
- size: `217`
- prototype: `__int64 __fastcall(CImage *__hidden this, struct WdsImgCopyParams *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000abe0`

## callees

- `0x1800093d8`
- `0x18000d0e8`
- `0x18000d5b0`

## pseudocode

```c
__int64 __fastcall CImage::WimImport(CImage *this, struct WdsImgCopyParams *a2, int a3)
{
  int v4; // edi
  unsigned int v5; // ebx
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rdx
  _OWORD v14[3]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v15; // [rsp+60h] [rbp-18h]

  v4 = 0;
  v5 = 0;
  memset(v14, 0, 32);
  *((_DWORD *)a2 + 14) = 1;
  v14[2] = 0;
  v15 = 0;
  v7 = 259;
  if ( a3 != 256 )
    v7 = a3;
  v8 = v7 - 256;
  if ( v8 )
  {
    v9 = v8 - 1;
    if ( !v9 )
      goto LABEL_10;
    v10 = v9 - 1;
    if ( !v10 )
    {
      v4 = 1;
      goto LABEL_10;
    }
    if ( v10 == 1 )
    {
      v4 = 2;
      goto LABEL_10;
    }
  }
  v5 = -1056833008;
LABEL_10:
  if ( (int)ElValidateHr_5(v5, 1, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 2323) >= 0 )
  {
    v11 = *((_QWORD *)this + 49);
    LODWORD(v15) = v4;
    LODWORD(v14[0]) = 21;
    v5 = CDepCopyConnector<&public: long CImage::WimCallback(_DEP_IMAGE_COPY_CALLBACK_PARAMS *,WdsImgCopyParams *,int *)>::Copy(
           (__int64)this,
           v11,
           (__int64)a2,
           (__int64)v14,
           0);
    ElValidateHr_5(v5, v12, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 2343);
  }
  return v5;
}

```

## disassembly

```asm
0x18000d0e8  mov     r11, rsp
0x18000d0eb  mov     [r11+8], rbx
0x18000d0ef  mov     [r11+10h], rbp
0x18000d0f3  mov     [r11+18h], rsi
0x18000d0f7  push    rdi
0x18000d0f8  sub     rsp, 70h
0x18000d0fc  xor     eax, eax
0x18000d0fe  xorps   xmm0, xmm0
0x18000d101  mov     rbp, rdx
0x18000d104  xor     edi, edi
0x18000d106  xor     ebx, ebx
0x18000d108  mov     rsi, rcx
0x18000d10b  movups  [rsp+78h+var_48], xmm0
0x18000d110  lea     edx, [rax+1]
0x18000d113  movups  [rsp+78h+var_38], xmm0
0x18000d118  mov     [rbp+38h], edx
0x18000d11b  movups  [rsp+78h+var_28], xmm0
0x18000d120  mov     [r11-18h], rax
0x18000d124  mov     eax, 103h
0x18000d129  lea     ecx, [rax-3]
0x18000d12c  cmp     r8d, ecx
0x18000d12f  cmovnz  eax, r8d
0x18000d133  sub     eax, ecx
0x18000d135  jz      short loc_18000D14C
0x18000d137  sub     eax, edx
0x18000d139  jz      short loc_18000D151
0x18000d13b  sub     eax, edx
0x18000d13d  jz      short loc_18000D148
0x18000d13f  cmp     eax, edx
0x18000d141  jnz     short loc_18000D14C
0x18000d143  lea     edi, [rdx+1]
0x18000d146  jmp     short loc_18000D151
0x18000d148  mov     edi, edx
0x18000d14a  jmp     short loc_18000D151
0x18000d14c  mov     ebx, 0C1020210h
0x18000d151  mov     r9d, 913h
0x18000d157  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000d15e  mov     ecx, ebx
0x18000d160  call    ElValidateHr_5
0x18000d165  test    eax, eax
0x18000d167  js      short loc_18000D1A8
0x18000d169  mov     rdx, [rsi+188h]
0x18000d170  lea     r9, [rsp+78h+var_48]
0x18000d175  and     [rsp+78h+var_58], 0
0x18000d17b  mov     r8, rbp
0x18000d17e  mov     rcx, rsi
0x18000d181  mov     dword ptr [rsp+78h+var_18], edi
0x18000d185  mov     dword ptr [rsp+78h+var_48], 15h
0x18000d18d  call    ?Copy@?$CDepCopyConnector@$1?WimCallback@CImage@@QEAAJPEAU_DEP_IMAGE_COPY_CALLBACK_PARAMS@@PEAUWdsImgCopyParams@@PEAH@Z@@SAJPEAVCImage@@PEAVIDepImageResolved@@PEAUWdsImgCopyParams@@PEAU_DEP_IMAGE_COPY_PARAMS@@PEAPEAVIDepImage@@@Z; CDepCopyConnector<&CImage::WimCallback(_DEP_IMAGE_COPY_CALLBACK_PARAMS *,WdsImgCopyParams *,int *)>::Copy(CImage *,IDepImageResolved *,WdsImgCopyParams *,_DEP_IMAGE_COPY_PARAMS *,IDepImage * *)
0x18000d192  mov     r9d, 927h
0x18000d198  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000d19f  mov     ecx, eax
0x18000d1a1  mov     ebx, eax
0x18000d1a3  call    ElValidateHr_5
0x18000d1a8  lea     r11, [rsp+78h+var_8]
0x18000d1ad  mov     eax, ebx
0x18000d1af  mov     rbx, [r11+10h]
0x18000d1b3  mov     rbp, [r11+18h]
0x18000d1b7  mov     rsi, [r11+20h]
0x18000d1bb  mov     rsp, r11
0x18000d1be  pop     rdi
0x18000d1bf  retn
```
