# CSwitchThumbnailDeviceManager::_LoadPVLInfoForTarget(DCompThumbnailAnimation,int,int)

- ea: `0x18006a0ac`
- end: `0x18006a426`
- name: `?_LoadPVLInfoForTarget@CSwitchThumbnailDeviceManager@@AEAAJW4DCompThumbnailAnimation@@HH@Z`
- size: `890`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180069ec4`

## callees

- `0x18006a0ac`
- `0x18006a42c`
- `0x18006a478`
- `0x18013d354`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a1be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a241`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a2ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a2e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a35d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a36e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a1be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a241`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a2ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a2e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a35d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a36e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006a1b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006a236`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006a1b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006a236`
- `UxTheme!GetThemeAnimationTransform` at `0x18006a19c`
- `UxTheme!GetThemeAnimationTransform` at `0x18006a1f1`
- `UxTheme!GetThemeAnimationTransform` at `0x18006a19c`
- `UxTheme!GetThemeAnimationTransform` at `0x18006a1f1`
- `UxTheme!OpenThemeData` at `0x18006a0ea`
- `UxTheme!OpenThemeData` at `0x18006a10c`
- `UxTheme!OpenThemeData` at `0x18006a0ea`
- `UxTheme!OpenThemeData` at `0x18006a10c`
- `UxTheme!GetThemeAnimationProperty` at `0x18006a150`
- `UxTheme!GetThemeAnimationProperty` at `0x18006a150`
- `UxTheme!GetThemeTimingFunction` at `0x18006a21f`
- `UxTheme!GetThemeTimingFunction` at `0x18006a26a`
- `UxTheme!GetThemeTimingFunction` at `0x18006a21f`
- `UxTheme!GetThemeTimingFunction` at `0x18006a26a`
- `UxTheme!CloseThemeData` at `0x18006a38b`
- `UxTheme!CloseThemeData` at `0x18006a394`
- `UxTheme!CloseThemeData` at `0x18006a38b`
- `UxTheme!CloseThemeData` at `0x18006a394`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSwitchThumbnailDeviceManager::_LoadPVLInfoForTarget(
        __int64 a1,
        int a2,
        unsigned int a3,
        unsigned int a4)
{
  unsigned int v4; // r12d
  unsigned int v5; // esi
  int ThemeAnimationProperty; // r14d
  HTHEME v7; // rdi
  HTHEME v8; // r15
  unsigned int v9; // ebx
  unsigned int *v10; // r13
  void *v11; // rsi
  LPVOID v12; // r12
  void *v13; // rdi
  _QWORD *v14; // rax
  _QWORD *v15; // r15
  void *v16; // rcx
  void *v17; // rcx
  __int64 v18; // rdx
  _QWORD *v19; // rdx
  __int64 v21; // rax
  unsigned int cb; // [rsp+48h] [rbp-29h] BYREF
  unsigned int cb_4; // [rsp+4Ch] [rbp-25h] BYREF
  unsigned int v24; // [rsp+50h] [rbp-21h] BYREF
  int i; // [rsp+54h] [rbp-1Dh]
  int v26; // [rsp+58h] [rbp-19h] BYREF
  HTHEME v27; // [rsp+60h] [rbp-11h]
  HTHEME v28; // [rsp+68h] [rbp-9h]
  _QWORD *v29; // [rsp+70h] [rbp-1h]
  __int64 v30; // [rsp+78h] [rbp+7h]
  __int64 v31; // [rsp+80h] [rbp+Fh]

  v4 = a4;
  v5 = a3;
  ThemeAnimationProperty = -2147467259;
  v7 = OpenThemeData(0, L"ANIMATIONS");
  v28 = v7;
  if ( v7 )
  {
    v8 = OpenThemeData(0, L"TIMINGFUNCTION");
    v27 = v8;
    if ( v8 )
    {
      v26 = 0;
      v24 = 0;
      ThemeAnimationProperty = GetThemeAnimationProperty(v7, v5, v4, 1, &v24, 4, &v26);
      if ( ThemeAnimationProperty >= 0 )
      {
        v9 = 0;
        for ( i = 0; v9 < v24; i = ++v9 )
        {
          if ( ThemeAnimationProperty < 0 )
            break;
          cb = 0;
          ThemeAnimationProperty = GetThemeAnimationTransform(v7, v5, v4, v9, 0, 0, &cb);
          if ( ThemeAnimationProperty == -2147024662 )
          {
            v10 = (unsigned int *)CoTaskMemAlloc(cb);
            CoTaskMemFree(0);
            v11 = v10;
            if ( v10 )
            {
              ThemeAnimationProperty = GetThemeAnimationTransform(v7, a3, v4, v9, v10, cb, &cb);
              if ( ThemeAnimationProperty >= 0 )
              {
                cb_4 = 0;
                ThemeAnimationProperty = GetThemeTimingFunction(v8, v10[1], 0, 0, &cb_4);
                if ( ThemeAnimationProperty == -2147024662 )
                {
                  v12 = CoTaskMemAlloc(cb_4);
                  CoTaskMemFree(0);
                  v13 = v12;
                  if ( v12 )
                  {
                    ThemeAnimationProperty = GetThemeTimingFunction(v8, v10[1], v12, cb_4, &cb_4);
                    if ( ThemeAnimationProperty >= 0 )
                    {
                      v14 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
                      v15 = v14;
                      v29 = v14;
                      ThemeAnimationProperty = 0;
                      if ( v14 )
                      {
                        *(_OWORD *)v14 = 0;
                        v14[1] = 0;
                        v14[2] = 0;
                      }
                      else
                      {
                        v15 = 0;
                      }
                      if ( v15 )
                      {
                        *(_DWORD *)v15 = a2;
                        v11 = 0;
                        v29 = 0;
                        v16 = (void *)v15[1];
                        v15[1] = 0;
                        CoTaskMemFree(v16);
                        v15[1] = v10;
                        v13 = 0;
                        v30 = 0;
                        v17 = (void *)v15[2];
                        v15[2] = 0;
                        CoTaskMemFree(v17);
                        v15[2] = v12;
                        if ( *(_BYTE *)(a1 + 258) )
                        {
                          v21 = v15[1];
                          if ( *(_DWORD *)v21 == 260 )
                          {
                            *(float *)(v21 + 36) = *(float *)(v21 + 36) * -1.0;
                            *(float *)(v21 + 44) = 1.0 - *(float *)(v21 + 44);
                            *(float *)(v21 + 24) = *(float *)(v21 + 24) * -1.0;
                          }
                        }
                        v31 = 0;
                        v18 = *(_QWORD *)(a1 + 168);
                        if ( v18 != *(_QWORD *)(a1 + 184)
                          || (ThemeAnimationProperty = CTSimpleArray<CSwitchThumbnailDeviceManager::AnimationPVLInfo *,4294967294,CTPolicyCoTaskMem<CSwitchThumbnailDeviceManager::AnimationPVLInfo *>,CSimpleArrayStandardCompareHelper<CSwitchThumbnailDeviceManager::AnimationPVLInfo *>,CSimpleArrayStandardMergeHelper<CSwitchThumbnailDeviceManager::AnimationPVLInfo *>>::_EnsureCapacity(
                                                         a1 + 160,
                                                         v18 + 1),
                              ThemeAnimationProperty >= 0) )
                        {
                          v19 = (_QWORD *)(*(_QWORD *)(a1 + 160) + 8 * (*(_QWORD *)(a1 + 168))++);
                          if ( v19 )
                            *v19 = v15;
                        }
                      }
                      else
                      {
                        ThemeAnimationProperty = -2147024882;
                      }
                      CTContainer_PolicyNewMem::Destroy<CSwitchThumbnailDeviceManager::AnimationPVLInfo>(0);
                      v9 = i;
                      v8 = v27;
                    }
                  }
                  else
                  {
                    ThemeAnimationProperty = -2147024882;
                  }
                  CoTaskMemFree(v13);
                  v7 = v28;
                  v4 = a4;
                }
              }
            }
            else
            {
              ThemeAnimationProperty = -2147024882;
            }
            CoTaskMemFree(v11);
            v5 = a3;
          }
        }
      }
      CloseThemeData(v8);
    }
    CloseThemeData(v7);
  }
  return (unsigned int)ThemeAnimationProperty;
}

```

## disassembly

```asm
0x18006a0ac  mov     rax, rsp
0x18006a0af  mov     [rax+20h], r9d
0x18006a0b3  mov     [rax+18h], r8d
0x18006a0b7  mov     [rax+10h], edx
0x18006a0ba  mov     [rax+8], rcx
0x18006a0be  push    rbp
0x18006a0bf  push    rbx
0x18006a0c0  push    rsi
0x18006a0c1  push    rdi
0x18006a0c2  push    r12
0x18006a0c4  push    r13
0x18006a0c6  push    r14
0x18006a0c8  push    r15
0x18006a0ca  lea     rbp, [rax-5Fh]
0x18006a0ce  sub     rsp, 88h
0x18006a0d5  mov     r12d, r9d
0x18006a0d8  mov     esi, r8d
0x18006a0db  mov     r14d, 80004005h
0x18006a0e1  lea     rdx, aAnimations; "ANIMATIONS"
0x18006a0e8  xor     ecx, ecx; hwnd
0x18006a0ea  call    cs:__imp_OpenThemeData
0x18006a0f0  mov     rdi, rax
0x18006a0f3  mov     [rbp+57h+var_60], rax
0x18006a0f7  xor     r13d, r13d
0x18006a0fa  test    rax, rax
0x18006a0fd  jz      loc_18006A39A
0x18006a103  lea     rdx, aTimingfunction; "TIMINGFUNCTION"
0x18006a10a  xor     ecx, ecx; hwnd
0x18006a10c  call    cs:__imp_OpenThemeData
0x18006a112  mov     r15, rax
0x18006a115  mov     [rbp+57h+var_68], rax
0x18006a119  test    rax, rax
0x18006a11c  jz      loc_18006A391
0x18006a122  mov     [rbp+57h+var_70], r13d
0x18006a126  mov     [rbp+57h+var_78], r13d
0x18006a12a  lea     rax, [rbp+57h+var_70]
0x18006a12e  mov     [rsp+30h], rax
0x18006a133  mov     dword ptr [rsp+0C0h+var_98], 4
0x18006a13b  lea     rax, [rbp+57h+var_78]
0x18006a13f  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18006a144  lea     r9d, [r13+1]
0x18006a148  mov     r8d, r12d
0x18006a14b  mov     edx, esi
0x18006a14d  mov     rcx, rdi
0x18006a150  call    cs:__imp_GetThemeAnimationProperty
0x18006a156  mov     r14d, eax
0x18006a159  test    eax, eax
0x18006a15b  js      loc_18006A388
0x18006a161  mov     ebx, r13d
0x18006a164  mov     [rbp+57h+var_74], ebx
0x18006a167  cmp     [rbp+57h+var_78], r13d
0x18006a16b  jbe     loc_18006A388
0x18006a171  test    r14d, r14d
0x18006a174  js      loc_18006A388
0x18006a17a  mov     dword ptr [rbp+57h+cb], r13d
0x18006a17e  lea     rax, [rbp+57h+cb]
0x18006a182  mov     [rsp+30h], rax
0x18006a187  mov     dword ptr [rsp+0C0h+var_98], r13d
0x18006a18c  mov     qword ptr [rsp+0C0h+var_A0], r13
0x18006a191  mov     r9d, ebx
0x18006a194  mov     r8d, r12d
0x18006a197  mov     edx, esi
0x18006a199  mov     rcx, rdi
0x18006a19c  call    cs:__imp_GetThemeAnimationTransform
0x18006a1a2  mov     r14d, eax
0x18006a1a5  cmp     eax, 800700EAh
0x18006a1aa  jnz     loc_18006A37A
0x18006a1b0  mov     ecx, dword ptr [rbp+57h+cb]; cb
0x18006a1b3  call    cs:__imp_CoTaskMemAlloc
0x18006a1b9  mov     r13, rax
0x18006a1bc  xor     ecx, ecx; pv
0x18006a1be  call    cs:__imp_CoTaskMemFree
0x18006a1c4  mov     rsi, r13
0x18006a1c7  test    r13, r13
0x18006a1ca  jz      loc_18006A41A
0x18006a1d0  mov     ecx, dword ptr [rbp+57h+cb]
0x18006a1d3  lea     rax, [rbp+57h+cb]
0x18006a1d7  mov     [rsp+30h], rax
0x18006a1dc  mov     dword ptr [rsp+0C0h+var_98], ecx
0x18006a1e0  mov     qword ptr [rsp+0C0h+var_A0], r13
0x18006a1e5  mov     r9d, ebx
0x18006a1e8  mov     r8d, r12d
0x18006a1eb  mov     edx, [rbp+57h+arg_10]
0x18006a1ee  mov     rcx, rdi
0x18006a1f1  call    cs:__imp_GetThemeAnimationTransform
0x18006a1f7  mov     r14d, eax
0x18006a1fa  test    eax, eax
0x18006a1fc  js      loc_18006A36B
0x18006a202  mov     dword ptr [rbp+57h+cb+4], 0
0x18006a209  lea     rax, [rbp+57h+cb+4]
0x18006a20d  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18006a212  xor     r9d, r9d
0x18006a215  xor     r8d, r8d
0x18006a218  mov     edx, [r13+4]
0x18006a21c  mov     rcx, r15
0x18006a21f  call    cs:__imp_GetThemeTimingFunction
0x18006a225  mov     r14d, eax
0x18006a228  cmp     eax, 800700EAh
0x18006a22d  jnz     loc_18006A36B
0x18006a233  mov     ecx, dword ptr [rbp+57h+cb+4]; cb
0x18006a236  call    cs:__imp_CoTaskMemAlloc
0x18006a23c  mov     r12, rax
0x18006a23f  xor     ecx, ecx; pv
0x18006a241  call    cs:__imp_CoTaskMemFree
0x18006a247  mov     rdi, r12
0x18006a24a  test    r12, r12
0x18006a24d  jz      loc_18006A40F
0x18006a253  lea     rax, [rbp+57h+cb+4]
0x18006a257  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18006a25c  mov     r9d, dword ptr [rbp+57h+cb+4]
0x18006a260  mov     r8, r12
0x18006a263  mov     edx, [r13+4]
0x18006a267  mov     rcx, r15
0x18006a26a  call    cs:__imp_GetThemeTimingFunction
0x18006a270  mov     r14d, eax
0x18006a273  test    eax, eax
0x18006a275  js      loc_18006A35A
0x18006a27b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18006a282  mov     ecx, 18h; unsigned __int64
0x18006a287  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18006a28c  mov     r15, rax
0x18006a28f  mov     [rbp+57h+var_58], rax
0x18006a293  xor     r14d, r14d
0x18006a296  test    rax, rax
0x18006a299  jz      loc_18006A3B1
0x18006a29f  xorps   xmm0, xmm0
0x18006a2a2  movups  xmmword ptr [rax], xmm0
0x18006a2a5  mov     [rax+8], r14
0x18006a2a9  mov     [rax+10h], r14
0x18006a2ad  mov     rbx, r15
0x18006a2b0  test    r15, r15
0x18006a2b3  jz      loc_18006A404
0x18006a2b9  mov     eax, [rbp+57h+arg_8]
0x18006a2bc  mov     [r15], eax
0x18006a2bf  mov     rsi, r14
0x18006a2c2  mov     [rbp+57h+var_58], r14
0x18006a2c6  mov     rcx, [r15+8]; pv
0x18006a2ca  mov     [r15+8], r14
0x18006a2ce  call    cs:__imp_CoTaskMemFree
0x18006a2d4  mov     [r15+8], r13
0x18006a2d8  mov     rdi, r14
0x18006a2db  mov     [rbp+57h+var_50], r14
0x18006a2df  mov     rcx, [r15+10h]; pv
0x18006a2e3  mov     [r15+10h], r14
0x18006a2e7  call    cs:__imp_CoTaskMemFree
0x18006a2ed  mov     [r15+10h], r12
0x18006a2f1  mov     rcx, [rbp+57h+arg_0]
0x18006a2f5  cmp     [rcx+102h], r14b
0x18006a2fc  jnz     loc_18006A3B9
0x18006a302  lea     r12, [rcx+0A0h]
0x18006a309  mov     rbx, r14
0x18006a30c  mov     [rbp+57h+var_48], rbx
0x18006a310  mov     rdx, [r12+8]
0x18006a315  cmp     rdx, [r12+18h]
0x18006a31a  jnz     short loc_18006A32E
0x18006a31c  inc     rdx
0x18006a31f  mov     rcx, r12
0x18006a322  call    ?_EnsureCapacity@?$CTSimpleArray@PEAUAnimationPVLInfo@CSwitchThumbnailDeviceManager@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@PEAUAnimationPVLInfo@CSwitchThumbnailDeviceManager@@@@V?$CSimpleArrayStandardCompareHelper@PEAUAnimationPVLInfo@CSwitchThumbnailDeviceManager@@@@V?$CSimpleArrayStandardMergeHelper@PEAUAnimationPVLInfo@CSwitchThumbnailDeviceManager@@@@@@QEAAJ_K0@Z; CTSimpleArray<CSwitchThumbnailDeviceManager::AnimationPVLInfo *,4294967294,CTPolicyCoTaskMem<CSwitchThumbnailDeviceManager::AnimationPVLInfo *>,CSimpleArrayStandardCompareHelper<CSwitchThumbnailDeviceManager::AnimationPVLInfo *>,CSimpleArrayStandardMergeHelper<CSwitchThumbnailDeviceManager::AnimationPVLInfo *>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x18006a327  mov     r14d, eax
0x18006a32a  test    eax, eax
0x18006a32c  js      short loc_18006A34B
0x18006a32e  inc     qword ptr [r12+8]
0x18006a333  mov     rdx, [r12+8]
0x18006a338  mov     rax, [r12]
0x18006a33c  dec     rdx
0x18006a33f  lea     rdx, [rax+rdx*8]
0x18006a343  test    rdx, rdx
0x18006a346  jz      short loc_18006A34B
0x18006a348  mov     [rdx], r15
0x18006a34b  mov     rcx, rbx; Block
0x18006a34e  call    ??$Destroy@UAnimationPVLInfo@CSwitchThumbnailDeviceManager@@@CTContainer_PolicyNewMem@@SAXPEAUAnimationPVLInfo@CSwitchThumbnailDeviceManager@@@Z; CTContainer_PolicyNewMem::Destroy<CSwitchThumbnailDeviceManager::AnimationPVLInfo>(CSwitchThumbnailDeviceManager::AnimationPVLInfo *)
0x18006a353  mov     ebx, [rbp+57h+var_74]
0x18006a356  mov     r15, [rbp+57h+var_68]
0x18006a35a  mov     rcx, rdi; pv
0x18006a35d  call    cs:__imp_CoTaskMemFree
0x18006a363  mov     rdi, [rbp+57h+var_60]
0x18006a367  mov     r12d, [rbp+57h+arg_18]
0x18006a36b  mov     rcx, rsi; pv
0x18006a36e  call    cs:__imp_CoTaskMemFree
0x18006a374  mov     esi, [rbp+57h+arg_10]
0x18006a377  xor     r13d, r13d
0x18006a37a  inc     ebx
0x18006a37c  mov     [rbp+57h+var_74], ebx
0x18006a37f  cmp     ebx, [rbp+57h+var_78]
0x18006a382  jb      loc_18006A171
0x18006a388  mov     rcx, r15; hTheme
0x18006a38b  call    cs:__imp_CloseThemeData
0x18006a391  mov     rcx, rdi; hTheme
0x18006a394  call    cs:__imp_CloseThemeData
0x18006a39a  mov     eax, r14d
0x18006a39d  add     rsp, 88h
0x18006a3a4  pop     r15
0x18006a3a6  pop     r14
0x18006a3a8  pop     r13
0x18006a3aa  pop     r12
0x18006a3ac  pop     rdi
0x18006a3ad  pop     rsi
0x18006a3ae  pop     rbx
0x18006a3af  pop     rbp
0x18006a3b0  retn
0x18006a3b1  mov     r15, r14
0x18006a3b4  jmp     loc_18006A2AD
0x18006a3b9  mov     rax, [r15+8]
0x18006a3bd  cmp     dword ptr [rax], 104h
0x18006a3c3  jnz     loc_18006A302
0x18006a3c9  movss   xmm0, dword ptr [rax+24h]
0x18006a3ce  mulss   xmm0, cs:__real@bf800000
0x18006a3d6  movss   dword ptr [rax+24h], xmm0
0x18006a3db  movss   xmm1, cs:__real@3f800000
0x18006a3e3  subss   xmm1, dword ptr [rax+2Ch]
0x18006a3e8  movss   dword ptr [rax+2Ch], xmm1
0x18006a3ed  movss   xmm0, dword ptr [rax+18h]
0x18006a3f2  mulss   xmm0, cs:__real@bf800000
0x18006a3fa  movss   dword ptr [rax+18h], xmm0
0x18006a3ff  jmp     loc_18006A302
0x18006a404  mov     r14d, 8007000Eh
0x18006a40a  jmp     loc_18006A34B
0x18006a40f  mov     r14d, 8007000Eh
0x18006a415  jmp     loc_18006A35A
0x18006a41a  mov     r14d, 8007000Eh
0x18006a420  jmp     loc_18006A36B
```
