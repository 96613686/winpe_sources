# SkhalpPciSaveAndRemoveFunctionConfig

- ea: `0x14008d3cc`
- end: `0x14008d688`
- name: `SkhalpPciSaveAndRemoveFunctionConfig`
- size: `700`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14008b580`
- `0x14008e0dc`

## callees

- `0x1400119c4`
- `0x14008ac3c`
- `0x14008d3cc`
- `0x1400f3620`

## pseudocode

```c
__int64 __fastcall SkhalpPciSaveAndRemoveFunctionConfig(__int64 a1, char a2)
{
  bool v2; // di
  unsigned __int8 v5; // r9
  unsigned int v6; // r8d
  int v7; // eax
  unsigned __int8 v8; // r9
  unsigned int v9; // r8d
  int v10; // eax
  int v11; // eax
  __int64 v12; // rcx
  int v13; // r9d
  __int64 v14; // rdx
  __int64 v15; // r10
  int v16; // r11d
  unsigned __int8 v17; // r9
  unsigned int v18; // r8d
  __int64 result; // rax
  unsigned __int8 BugCheckParameter4; // [rsp+20h] [rbp-60h]
  char v21; // [rsp+28h] [rbp-58h]
  ULONG_PTR v22; // [rsp+30h] [rbp-50h]
  ULONG_PTR v23; // [rsp+30h] [rbp-50h]
  size_t Size; // [rsp+38h] [rbp-48h]
  size_t Sizea; // [rsp+38h] [rbp-48h]
  unsigned __int16 v26; // [rsp+50h] [rbp-30h] BYREF
  __int128 v27; // [rsp+58h] [rbp-28h] BYREF
  __int64 v28; // [rsp+68h] [rbp-18h]

  v2 = 0;
  if ( a2 )
  {
    v5 = *(_BYTE *)(a1 + 48);
    v6 = *(_DWORD *)(a1 + 44);
    v26 = 0;
    LODWORD(Size) = 2;
    LODWORD(v22) = 4;
    v7 = SkhalpPciAccessDeviceInternal(1, 0, v6, v5, *(_BYTE *)(a1 + 49), *(_BYTE *)(a1 + 50), v22, Size, &v26);
    if ( v7 < 0 )
      SkeBugCheckEx(0x121u, v7, 0x47666350000001BDuLL, 4u, 0);
    v2 = (v26 & 2) != 0;
  }
  v8 = *(_BYTE *)(a1 + 48);
  v9 = *(_DWORD *)(a1 + 44);
  v26 = 0;
  LODWORD(Size) = 2;
  LODWORD(v22) = 4;
  v10 = SkhalpPciAccessDeviceInternal(1, 1, v9, v8, *(_BYTE *)(a1 + 49), *(_BYTE *)(a1 + 50), v22, Size, &v26);
  if ( v10 < 0 )
    SkeBugCheckEx(0x121u, v10, 0x47666350000001D9uLL, 4u, v26);
  v28 = 0;
  v27 = 0;
  if ( v2 && a2 )
  {
    LODWORD(Sizea) = 24;
    LODWORD(v23) = 16;
    v11 = SkhalpPciAccessDeviceInternal(
            1,
            0,
            *(_DWORD *)(a1 + 44),
            *(_BYTE *)(a1 + 48),
            *(_BYTE *)(a1 + 49),
            *(_BYTE *)(a1 + 50),
            v23,
            Sizea,
            &v27);
    if ( v11 < 0 )
      SkeBugCheckEx(0x121u, v11, 0x47666350000001F1uLL, 0x10u, 0);
    v12 = 0;
    do
    {
      v13 = *((_DWORD *)&v27 + v12);
      v14 = 3 * v12;
      *(_BYTE *)(a1 + 24 * v12 + 225) = 1;
      if ( (v13 & 1) == 0 )
      {
        v15 = (unsigned int)(v12 + 1);
        if ( (unsigned int)v12 >= 5 )
          v16 = 0;
        else
          v16 = *((_DWORD *)&v27 + v15);
        if ( (v13 & 6) == 4 )
        {
          *(_DWORD *)(a1 + 24 * v12 + 212) = v16;
          LODWORD(v12) = v12 + 1;
          *(_BYTE *)(a1 + 8 * v14 + 224) = 1;
          if ( (unsigned int)v15 < 6 )
            *(_BYTE *)(a1 + 24 * v15 + 225) = 1;
        }
        else
        {
          *(_DWORD *)(a1 + 24 * v12 + 212) = 0;
        }
        *(_DWORD *)(a1 + 8 * v14 + 208) = v13 & 0xFFFFFFF0;
        if ( *(_QWORD *)(a1 + 8 * v14 + 208) )
          *(_BYTE *)(a1 + 8 * v14 + 225) = 0;
      }
      v12 = (unsigned int)(v12 + 1);
    }
    while ( (unsigned int)v12 < 6 );
  }
  v17 = *(_BYTE *)(a1 + 48);
  v18 = *(_DWORD *)(a1 + 44);
  v28 = 0;
  LODWORD(Sizea) = 24;
  LODWORD(v23) = 16;
  v21 = *(_BYTE *)(a1 + 50);
  BugCheckParameter4 = *(_BYTE *)(a1 + 49);
  v27 = 0;
  result = SkhalpPciAccessDeviceInternal(1, 1, v18, v17, BugCheckParameter4, v21, v23, Sizea, &v27);
  if ( (int)result < 0 )
    SkeBugCheckEx(0x121u, (int)result, 0x476663500000022EuLL, 0x10u, 0);
  return result;
}

```

## disassembly

```asm
0x14008d3cc  mov     r11, rsp
0x14008d3cf  mov     [r11+10h], rbx
0x14008d3d3  mov     [r11+18h], rsi
0x14008d3d7  push    rbp
0x14008d3d8  push    rdi
0x14008d3d9  push    r12
0x14008d3db  push    r13
0x14008d3dd  push    r15
0x14008d3df  mov     rbp, rsp
0x14008d3e2  sub     rsp, 80h
0x14008d3e9  mov     rax, cs:__security_cookie
0x14008d3f0  xor     rax, rsp
0x14008d3f3  mov     [rbp+var_10], rax
0x14008d3f7  mov     r12d, 2
0x14008d3fd  xor     dil, dil
0x14008d400  mov     sil, dl
0x14008d403  mov     rbx, rcx
0x14008d406  lea     r13d, [r12+2]
0x14008d40b  lea     r15d, [r12-1]
0x14008d410  test    dl, dl
0x14008d412  jz      short loc_14008D47E
0x14008d414  mov     r9b, [rcx+30h]; int
0x14008d418  xor     eax, eax
0x14008d41a  mov     r8d, [rcx+2Ch]; int
0x14008d41e  xor     edx, edx; int
0x14008d420  mov     [rbp+var_30], ax
0x14008d424  lea     rax, [rbp+var_30]
0x14008d428  mov     [r11-68h], rax
0x14008d42c  mov     al, [rcx+32h]
0x14008d42f  mov     [r11-70h], r12d
0x14008d433  mov     [r11-78h], r13d
0x14008d437  mov     [rsp+80h+var_58], al; char
0x14008d43b  mov     al, [rcx+31h]
0x14008d43e  mov     cl, r15b; int
0x14008d441  mov     byte ptr [rsp+80h+BugCheckParameter4], al; char
0x14008d445  call    SkhalpPciAccessDeviceInternal
0x14008d44a  test    eax, eax
0x14008d44c  jns     short loc_14008D472
0x14008d44e  movsxd  rdx, eax; BugCheckParameter1
0x14008d451  mov     r9d, r13d; BugCheckParameter3
0x14008d454  mov     ecx, 121h; BugCheckCode
0x14008d459  mov     [rsp+80h+BugCheckParameter4], 0; BugCheckParameter4
0x14008d462  mov     r8, 47666350000001BDh; BugCheckParameter2
0x14008d46c  call    SkeBugCheckEx
0x14008d472  test    byte ptr [rbp+var_30], r12b
0x14008d476  movzx   edi, dil
0x14008d47a  cmovnz  edi, r15d
0x14008d47e  mov     r9b, [rbx+30h]; int
0x14008d482  xor     eax, eax
0x14008d484  mov     r8d, [rbx+2Ch]; int
0x14008d488  mov     dl, r15b; int
0x14008d48b  mov     [rbp+var_30], ax
0x14008d48f  mov     cl, r15b; int
0x14008d492  lea     rax, [rbp+var_30]
0x14008d496  mov     [rsp+80h+var_40], rax; void *
0x14008d49b  mov     al, [rbx+32h]
0x14008d49e  mov     dword ptr [rsp+80h+Size], r12d; Size
0x14008d4a3  mov     dword ptr [rsp+80h+var_50], r13d; ULONG_PTR
0x14008d4a8  mov     [rsp+80h+var_58], al; char
0x14008d4ac  mov     al, [rbx+31h]
0x14008d4af  mov     byte ptr [rsp+80h+BugCheckParameter4], al; char
0x14008d4b3  call    SkhalpPciAccessDeviceInternal
0x14008d4b8  test    eax, eax
0x14008d4ba  jns     short loc_14008D4E0
0x14008d4bc  movzx   ecx, [rbp+var_30]
0x14008d4c0  mov     r9, r13; BugCheckParameter3
0x14008d4c3  mov     [rsp+80h+BugCheckParameter4], rcx; BugCheckParameter4
0x14008d4c8  mov     r8, 47666350000001D9h; BugCheckParameter2
0x14008d4d2  mov     ecx, 121h; BugCheckCode
0x14008d4d7  movsxd  rdx, eax; BugCheckParameter1
0x14008d4da  call    SkeBugCheckEx
0x14008d4e0  xor     eax, eax
0x14008d4e2  xorps   xmm0, xmm0
0x14008d4e5  mov     [rbp+var_18], rax
0x14008d4e9  movups  [rbp+var_28], xmm0
0x14008d4ed  lea     r12d, [rax+10h]
0x14008d4f1  test    dil, dil
0x14008d4f4  jz      loc_14008D5F3
0x14008d4fa  test    sil, sil
0x14008d4fd  jz      loc_14008D5F3
0x14008d503  mov     r9b, [rbx+30h]; int
0x14008d507  lea     rax, [rbp+var_28]
0x14008d50b  mov     r8d, [rbx+2Ch]; int
0x14008d50f  xor     edx, edx; int
0x14008d511  mov     [rsp+80h+var_40], rax; void *
0x14008d516  mov     cl, r15b; int
0x14008d519  mov     al, [rbx+32h]
0x14008d51c  mov     dword ptr [rsp+80h+Size], 18h; Size
0x14008d524  mov     dword ptr [rsp+80h+var_50], r12d; ULONG_PTR
0x14008d529  mov     [rsp+80h+var_58], al; char
0x14008d52d  mov     al, [rbx+31h]
0x14008d530  mov     byte ptr [rsp+80h+BugCheckParameter4], al; char
0x14008d534  call    SkhalpPciAccessDeviceInternal
0x14008d539  test    eax, eax
0x14008d53b  jns     short loc_14008D561
0x14008d53d  movsxd  rdx, eax; BugCheckParameter1
0x14008d540  mov     r9d, r12d; BugCheckParameter3
0x14008d543  mov     ecx, 121h; BugCheckCode
0x14008d548  mov     [rsp+80h+BugCheckParameter4], 0; BugCheckParameter4
0x14008d551  mov     r8, 47666350000001F1h; BugCheckParameter2
0x14008d55b  call    SkeBugCheckEx
0x14008d561  xor     ecx, ecx
0x14008d563  mov     r9d, dword ptr [rbp+rcx*4+var_28]
0x14008d568  lea     rdx, [rcx+rcx*2]
0x14008d56c  mov     [rbx+rdx*8+0E1h], r15b
0x14008d574  test    r15b, r9b
0x14008d577  jnz     short loc_14008D5E7
0x14008d579  lea     r10d, [rcx+1]
0x14008d57d  cmp     ecx, 5
0x14008d580  jnb     short loc_14008D589
0x14008d582  mov     r11d, dword ptr [rbp+r10*4+var_28]
0x14008d587  jmp     short loc_14008D58C
0x14008d589  xor     r11d, r11d
0x14008d58c  mov     eax, r9d
0x14008d58f  and     al, 6
0x14008d591  cmp     al, r13b
0x14008d594  jnz     short loc_14008D5BD
0x14008d596  mov     [rbx+rdx*8+0D4h], r11d
0x14008d59e  mov     ecx, r10d
0x14008d5a1  mov     [rbx+rdx*8+0E0h], r15b
0x14008d5a9  cmp     r10d, 6
0x14008d5ad  jnb     short loc_14008D5C8
0x14008d5af  lea     rax, [r10+r10*2]
0x14008d5b3  mov     [rbx+rax*8+0E1h], r15b
0x14008d5bb  jmp     short loc_14008D5C8
0x14008d5bd  mov     dword ptr [rbx+rdx*8+0D4h], 0
0x14008d5c8  and     r9d, 0FFFFFFF0h
0x14008d5cc  mov     [rbx+rdx*8+0D0h], r9d
0x14008d5d4  cmp     qword ptr [rbx+rdx*8+0D0h], 0
0x14008d5dd  jz      short loc_14008D5E7
0x14008d5df  mov     byte ptr [rbx+rdx*8+0E1h], 0
0x14008d5e7  add     ecx, r15d
0x14008d5ea  cmp     ecx, 6
0x14008d5ed  jb      loc_14008D563
0x14008d5f3  mov     r9b, [rbx+30h]; int
0x14008d5f7  xor     eax, eax
0x14008d5f9  mov     r8d, [rbx+2Ch]; int
0x14008d5fd  xorps   xmm0, xmm0
0x14008d600  mov     [rbp+var_18], rax
0x14008d604  mov     dl, r15b; int
0x14008d607  lea     rax, [rbp+var_28]
0x14008d60b  mov     cl, r15b; int
0x14008d60e  mov     [rsp+80h+var_40], rax; void *
0x14008d613  mov     al, [rbx+32h]
0x14008d616  mov     dword ptr [rsp+80h+Size], 18h; Size
0x14008d61e  mov     dword ptr [rsp+80h+var_50], r12d; ULONG_PTR
0x14008d623  mov     [rsp+80h+var_58], al; char
0x14008d627  mov     al, [rbx+31h]
0x14008d62a  mov     byte ptr [rsp+80h+BugCheckParameter4], al; char
0x14008d62e  movups  [rbp+var_28], xmm0
0x14008d632  call    SkhalpPciAccessDeviceInternal
0x14008d637  test    eax, eax
0x14008d639  jns     short loc_14008D65F
0x14008d63b  movsxd  rdx, eax; BugCheckParameter1
0x14008d63e  mov     r9, r12; BugCheckParameter3
0x14008d641  mov     ecx, 121h; BugCheckCode
0x14008d646  mov     [rsp+80h+BugCheckParameter4], 0; BugCheckParameter4
0x14008d64f  mov     r8, 476663500000022Eh; BugCheckParameter2
0x14008d659  call    SkeBugCheckEx
0x14008d65f  mov     rcx, [rbp+var_10]
0x14008d663  xor     rcx, rsp; StackCookie
0x14008d666  call    __security_check_cookie
0x14008d66b  lea     r11, [rsp+80h+var_s0]
0x14008d673  mov     rbx, [r11+38h]
0x14008d677  mov     rsi, [r11+40h]
0x14008d67b  mov     rsp, r11
0x14008d67e  pop     r15
0x14008d680  pop     r13
0x14008d682  pop     r12
0x14008d684  pop     rdi
0x14008d685  pop     rbp
0x14008d686  retn
```
