# USCopyPropVals

- ea: `0x18002e3d0`
- end: `0x18002e6a1`
- name: `USCopyPropVals`
- size: `721`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000c610`
- `0x18002ea70`
- `0x18003a020`
- `0x18003e8f0`
- `0x180053e18`

## callees

- `0x1800068f0`
- `0x18002e3d0`
- `0x18002e6b0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18002e696`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18002e696`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e529`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e529`

## string_xrefs

- `0x18002e402`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\storeutil.cpp`
- `0x18002e41d`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\storeutil.cpp`
- `0x18002e4cb`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\storeutil.cpp`
- `0x18002e581`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\storeutil.cpp`
- `0x18002e622`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\storeutil.cpp`
- `0x18002e657`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\storeutil.cpp`

## pseudocode

```c
__int64 __fastcall USCopyPropVals(unsigned int a1, __int64 a2, char a3, HLOCAL *a4, unsigned int *a5)
{
  unsigned int v5; // r10d
  __int64 v6; // rsi
  __int64 v9; // rbp
  unsigned int v10; // r14d
  __int64 v11; // r9
  __int64 v13; // rax
  unsigned int v14; // edx
  int v15; // r8d
  __int64 v16; // r9
  __int64 v17; // r9
  unsigned int *v18; // rdi
  int v19; // ebx
  unsigned int v20; // ebx
  HLOCAL v21; // rax
  char *v22; // rbx
  unsigned int v23; // edi
  int v24; // eax
  _WORD *v25; // rcx
  __int64 v26; // r8
  int v27; // ebx
  int v28; // r9d
  unsigned int v29; // [rsp+60h] [rbp+8h] BYREF
  __int64 v30; // [rsp+68h] [rbp+10h] BYREF

  v5 = 0;
  v6 = a1;
  v29 = 0;
  v9 = a2;
  if ( a1 && !a2 )
  {
    v10 = -2147024809;
    Log_UnistoreHREvent_0(
      2147942487LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\storeutil.cpp",
      61);
    goto LABEL_4;
  }
  v13 = a2;
  v14 = a1;
  v10 = -2147024809;
  while ( 1 )
  {
    if ( !v14 )
    {
      if ( a4 )
      {
        v18 = a5;
        if ( a5 )
        {
          v19 = v5 + 24 * v6;
          if ( !v19 )
          {
            v17 = 230;
            goto LABEL_21;
          }
          v20 = (v19 + 3) & 0xFFFFFFFC;
          if ( v20 > *a5 )
          {
            if ( (a3 & 1) == 0 )
            {
              *a5 = v20;
              v17 = 241;
              v10 = -2147024774;
              goto LABEL_21;
            }
            if ( *a4 )
              v21 = LocalReAlloc(*a4, v20, 2u);
            else
              v21 = LocalAlloc(0, v20);
            if ( !v21 )
            {
              v17 = 265;
              v10 = -2147024882;
              goto LABEL_21;
            }
            *a4 = v21;
          }
          *v18 = v20;
          v22 = (char *)*a4;
          v23 = 0;
          v30 = (__int64)*a4 + 24 * v6;
          while ( (_DWORD)v6 )
          {
            v24 = USCopyPropVal(v9, v22, &v29, &v30);
            v23 = v24;
            if ( v24 < 0 )
            {
              Log_UnistoreHREvent_0(
                (unsigned int)v24,
                1,
                "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\storeutil.cpp",
                497);
              return v23;
            }
            v9 += 24;
            v22 += 24;
            LODWORD(v6) = v6 - 1;
          }
          return v23;
        }
        v17 = 229;
      }
      else
      {
        v17 = 228;
      }
      v10 = -2147467261;
LABEL_21:
      Log_UnistoreHREvent_0(
        v10,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\storeutil.cpp",
        v17);
      v11 = 487;
      goto LABEL_5;
    }
    if ( (*(_WORD *)(v13 + 6) & 0x100) != 0 )
      goto LABEL_9;
    if ( *(_WORD *)v13 == 31 )
      break;
    if ( *(_WORD *)v13 == 65 || *(_WORD *)v13 == 100 || *(_WORD *)v13 == 101 || *(_WORD *)v13 == 103 )
    {
      v15 = *(_DWORD *)(v13 + 8);
      if ( v15 && !*(_QWORD *)(v13 + 16) )
      {
        v16 = 85;
        goto LABEL_47;
      }
      v5 = v15 + 4 * (((unsigned __int64)v5 + 3) >> 2);
      v29 = v5;
    }
LABEL_9:
    --v14;
    v13 += 24;
  }
  v25 = *(_WORD **)(v13 + 8);
  if ( v25 )
  {
    v26 = 0x7FFFFFFF;
    while ( *v25 )
    {
      ++v25;
      if ( !--v26 )
      {
        v27 = -2147024809;
        v28 = 0;
        goto LABEL_44;
      }
    }
    v27 = 0;
    v28 = 2 * (0x7FFFFFFF - v26);
LABEL_44:
    if ( v27 < 0 )
    {
      Log_UnistoreHREvent_0(
        (unsigned int)v27,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\storeutil.cpp",
        76);
      v10 = v27;
      goto LABEL_4;
    }
    v5 = v28 + 4 * (((unsigned __int64)v5 + 3) >> 2) + 2;
    v29 = v5;
    goto LABEL_9;
  }
  v16 = 72;
LABEL_47:
  Log_UnistoreHREvent_0(
    2147942487LL,
    0,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\storeutil.cpp",
    v16);
LABEL_4:
  v11 = 484;
LABEL_5:
  Log_UnistoreHREvent_0(
    v10,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\storeutil.cpp",
    v11);
  return v10;
}

```

## disassembly

```asm
0x18002e3d0  mov     [rsp+arg_10], rbx
0x18002e3d5  push    rbp
0x18002e3d6  push    rsi
0x18002e3d7  push    rdi
0x18002e3d8  push    r14
0x18002e3da  push    r15
0x18002e3dc  sub     rsp, 30h
0x18002e3e0  xor     r10d, r10d
0x18002e3e3  mov     esi, ecx
0x18002e3e5  mov     [rsp+58h+arg_0], r10d
0x18002e3ea  mov     r15, r9
0x18002e3ed  mov     r11d, r8d
0x18002e3f0  mov     rbp, rdx
0x18002e3f3  test    ecx, ecx
0x18002e3f5  jz      short loc_18002E445
0x18002e3f7  test    rdx, rdx
0x18002e3fa  jnz     short loc_18002E445
0x18002e3fc  mov     r14d, 80070057h
0x18002e402  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18002e409  mov     ecx, r14d
0x18002e40c  mov     r9d, 3Dh ; '='
0x18002e412  call    Log_UnistoreHREvent_0
0x18002e417  mov     r9d, 1E4h
0x18002e41d  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18002e424  mov     edx, 1
0x18002e429  mov     ecx, r14d
0x18002e42c  call    Log_UnistoreHREvent_0
0x18002e431  mov     eax, r14d
0x18002e434  mov     rbx, [rsp+58h+arg_10]
0x18002e439  add     rsp, 30h
0x18002e43d  pop     r15
0x18002e43f  pop     r14
0x18002e441  pop     rdi
0x18002e442  pop     rsi
0x18002e443  pop     rbp
0x18002e444  retn
0x18002e445  mov     rax, rdx
0x18002e448  xor     ebx, ebx
0x18002e44a  mov     edx, esi
0x18002e44c  mov     edi, 100h
0x18002e451  mov     r14d, 80070057h
0x18002e457  test    edx, edx
0x18002e459  jz      short loc_18002E4B2
0x18002e45b  test    [rax+6], di
0x18002e45f  jz      short loc_18002E469
0x18002e461  dec     edx
0x18002e463  add     rax, 18h
0x18002e467  jmp     short loc_18002E457
0x18002e469  movzx   r8d, word ptr [rax]
0x18002e46d  sub     r8d, 1Fh
0x18002e471  jz      loc_18002E5C3
0x18002e477  sub     r8d, 22h ; '"'
0x18002e47b  jz      short loc_18002E48F
0x18002e47d  sub     r8d, 23h ; '#'
0x18002e481  jz      short loc_18002E48F
0x18002e483  sub     r8d, 1
0x18002e487  jz      short loc_18002E48F
0x18002e489  cmp     r8d, 2
0x18002e48d  jnz     short loc_18002E461
0x18002e48f  mov     r8d, [rax+8]
0x18002e493  test    r8d, r8d
0x18002e496  jz      loc_18002E638
0x18002e49c  cmp     qword ptr [rax+10h], 0
0x18002e4a1  jnz     loc_18002E638
0x18002e4a7  mov     r9d, 55h ; 'U'
0x18002e4ad  jmp     loc_18002E622
0x18002e4b2  test    ebx, ebx
0x18002e4b4  js      loc_18002E66A
0x18002e4ba  test    r15, r15
0x18002e4bd  jnz     short loc_18002E4E7
0x18002e4bf  mov     r9d, 0E4h
0x18002e4c5  mov     r14d, 80004003h
0x18002e4cb  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18002e4d2  xor     edx, edx
0x18002e4d4  mov     ecx, r14d
0x18002e4d7  call    Log_UnistoreHREvent_0
0x18002e4dc  mov     r9d, 1E7h
0x18002e4e2  jmp     loc_18002E41D
0x18002e4e7  mov     rdi, [rsp+58h+arg_20]
0x18002e4ef  test    rdi, rdi
0x18002e4f2  jz      loc_18002E5B8
0x18002e4f8  lea     eax, [rsi+rsi*2]
0x18002e4fb  lea     ebx, [r10+rax*8]
0x18002e4ff  test    ebx, ebx
0x18002e501  jz      loc_18002E672
0x18002e507  add     ebx, 3
0x18002e50a  and     ebx, 0FFFFFFFCh
0x18002e50d  cmp     ebx, [rdi]
0x18002e50f  jbe     short loc_18002E537
0x18002e511  test    r11b, 1
0x18002e515  jz      loc_18002E67D
0x18002e51b  mov     rcx, [r15]; hMem
0x18002e51e  mov     edx, ebx; uBytes
0x18002e520  test    rcx, rcx
0x18002e523  jnz     loc_18002E690
0x18002e529  call    cs:__imp_LocalAlloc
0x18002e52f  test    rax, rax
0x18002e532  jz      short loc_18002E5A7
0x18002e534  mov     [r15], rax
0x18002e537  mov     [rdi], ebx
0x18002e539  lea     rcx, [rsi+rsi*2]
0x18002e53d  mov     rbx, [r15]
0x18002e540  xor     edi, edi
0x18002e542  lea     rax, [rbx+rcx*8]
0x18002e546  mov     [rsp+58h+arg_8], rax
0x18002e54b  nop     dword ptr [rax+rax+00h]
0x18002e550  test    esi, esi
0x18002e552  jz      short loc_18002E594
0x18002e554  lea     r9, [rsp+58h+arg_8]
0x18002e559  mov     rdx, rbx
0x18002e55c  lea     r8, [rsp+58h+arg_0]
0x18002e561  mov     rcx, rbp
0x18002e564  call    USCopyPropVal
0x18002e569  mov     edi, eax
0x18002e56b  test    eax, eax
0x18002e56d  js      short loc_18002E57B
0x18002e56f  add     rbp, 18h
0x18002e573  add     rbx, 18h
0x18002e577  dec     esi
0x18002e579  jmp     short loc_18002E550
0x18002e57b  mov     r9d, 1F1h
0x18002e581  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18002e588  mov     edx, 1
0x18002e58d  mov     ecx, edi
0x18002e58f  call    Log_UnistoreHREvent_0
0x18002e594  mov     rbx, [rsp+58h+arg_10]
0x18002e599  mov     eax, edi
0x18002e59b  add     rsp, 30h
0x18002e59f  pop     r15
0x18002e5a1  pop     r14
0x18002e5a3  pop     rdi
0x18002e5a4  pop     rsi
0x18002e5a5  pop     rbp
0x18002e5a6  retn
0x18002e5a7  mov     r9d, 109h
0x18002e5ad  mov     r14d, 8007000Eh
0x18002e5b3  jmp     loc_18002E4CB
0x18002e5b8  mov     r9d, 0E5h
0x18002e5be  jmp     loc_18002E4C5
0x18002e5c3  mov     rcx, [rax+8]
0x18002e5c7  test    rcx, rcx
0x18002e5ca  jz      short loc_18002E61C
0x18002e5cc  mov     r8d, 7FFFFFFFh
0x18002e5d2  cmp     word ptr [rcx], 0
0x18002e5d6  jz      short loc_18002E5EA
0x18002e5d8  add     rcx, 2
0x18002e5dc  sub     r8, 1
0x18002e5e0  jnz     short loc_18002E5D2
0x18002e5e2  mov     ebx, r14d
0x18002e5e5  xor     r9d, r9d
0x18002e5e8  jmp     short loc_18002E5F8
0x18002e5ea  mov     r9d, 7FFFFFFFh
0x18002e5f0  xor     ebx, ebx
0x18002e5f2  sub     r9, r8
0x18002e5f5  add     r9, r9
0x18002e5f8  test    ebx, ebx
0x18002e5fa  js      short loc_18002E651
0x18002e5fc  mov     ecx, r10d
0x18002e5ff  add     rcx, 3
0x18002e603  shr     rcx, 2
0x18002e607  lea     r10d, ds:2[rcx*4]
0x18002e60f  add     r10d, r9d
0x18002e612  mov     [rsp+58h+arg_0], r10d
0x18002e617  jmp     loc_18002E461
0x18002e61c  mov     r9d, 48h ; 'H'
0x18002e622  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18002e629  xor     edx, edx
0x18002e62b  mov     ecx, r14d
0x18002e62e  call    Log_UnistoreHREvent_0
0x18002e633  jmp     loc_18002E417
0x18002e638  mov     ecx, r10d
0x18002e63b  add     rcx, 3
0x18002e63f  shr     rcx, 2
0x18002e643  lea     r10d, [r8+rcx*4]
0x18002e647  mov     [rsp+58h+arg_0], r10d
0x18002e64c  jmp     loc_18002E461
0x18002e651  mov     r9d, 4Ch ; 'L'
0x18002e657  lea     r8, aOnecoreuapBase_40; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18002e65e  mov     edx, 1
0x18002e663  mov     ecx, ebx
0x18002e665  call    Log_UnistoreHREvent_0
0x18002e66a  mov     r14d, ebx
0x18002e66d  jmp     loc_18002E417
0x18002e672  mov     r9d, 0E6h
0x18002e678  jmp     loc_18002E4CB
0x18002e67d  mov     [rdi], ebx
0x18002e67f  mov     r9d, 0F1h
0x18002e685  mov     r14d, 8007007Ah
0x18002e68b  jmp     loc_18002E4CB
0x18002e690  mov     r8d, 2; uFlags
0x18002e696  call    cs:__imp_LocalReAlloc
0x18002e69c  jmp     loc_18002E52F
```
