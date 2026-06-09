# EFIOSBECreate

- ea: `0x180012dfc`
- end: `0x1800130ec`
- name: `EFIOSBECreate`
- size: `752`
- prototype: `_QWORD *__fastcall(__int64, __int64, int)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x18001378c`

## callees

- `0x18000e834`
- `0x180012d4c`
- `0x180012d74`
- `0x180012dfc`
- `0x180013e38`
- `0x180013e8c`
- `0x180013ee0`
- `0x180013f98`
- `0x180013fec`
- `0x180014444`
- `0x1800179c5`
- `0x180018010`

## pseudocode

```c
_QWORD *__fastcall EFIOSBECreate(__int64 a1, __int64 a2, int a3)
{
  _QWORD *v5; // rbx
  _QWORD *v6; // rax
  __int64 v7; // rsi
  _DWORD *v8; // r14
  __int64 v9; // rcx
  _DWORD *v10; // rax
  _DWORD *v11; // r15
  __int64 v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r14
  __int64 v16; // r12
  __int64 v17; // rax
  _DWORD *v18; // r14
  __int64 v19; // rax
  _DWORD *v20; // r14
  __int64 v21; // rcx
  _DWORD *v22; // rax
  _DWORD *v23; // rdi
  __int64 v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // r14
  size_t Size; // [rsp+80h] [rbp+58h] BYREF

  LODWORD(Size) = a3;
  v5 = 0;
  if ( a1 )
  {
    if ( a2 )
    {
      if ( AllocRoutine )
      {
        v6 = (_QWORD *)AllocRoutine(3176);
        v5 = v6;
        if ( v6 )
        {
          LODWORD(Size) = 0;
          memset_0(v6, 0, 0xC68u);
          v5[394] = EFIOSBEDelete;
          v5[395] = EFIOSBEFlush;
          *((_DWORD *)v5 + 1) = *(_DWORD *)(a1 + 8);
          v5[392] = a2;
          if ( (*(_BYTE *)(a1 + 12) & 4) != 0 )
            *((_DWORD *)v5 + 782) |= 4u;
          OSBESetFriendlyName(v5, a1 + *(unsigned int *)(a1 + 16));
          v7 = -1;
          v8 = (_DWORD *)(a1 + *(unsigned int *)(a1 + 20));
          if ( v8[2] == 3 )
          {
            v18 = v8 + 3;
            OSBESetOsLoaderVolumeName(v5, v18);
            v19 = -1;
            do
              ++v19;
            while ( *((_WORD *)v18 + v19) );
            OSBESetOsLoaderPath(v5, (char *)v18 + 2 * v19 + 2);
          }
          else
          {
            v9 = (unsigned int)(v8[1] + 16);
            LODWORD(Size) = v8[1] + 16;
            if ( AllocRoutine )
            {
              v10 = (_DWORD *)AllocRoutine(v9);
              v11 = v10;
              if ( v10 )
              {
                memset_0(v10, 0, (unsigned int)Size);
                if ( EFIGetHardDrivePath(v8, v11) )
                {
                  LODWORD(Size) = 0;
                  EfiTranslateFilePath(v11, v12, 0, &Size);
                  if ( (_DWORD)Size )
                  {
                    if ( AllocRoutine )
                    {
                      v13 = AllocRoutine((unsigned int)Size);
                      v15 = v13;
                      if ( v13 )
                      {
                        if ( (int)EfiTranslateFilePath(v11, v14, v13, &Size) >= 0 )
                        {
                          v16 = v15 + 12;
                          OSBESetOsLoaderVolumeName(v5, v15 + 12);
                          v17 = -1;
                          do
                            ++v17;
                          while ( *(_WORD *)(v16 + 2 * v17) );
                          OSBESetOsLoaderPath(v5, v16 + 2 * (v17 + 1));
                        }
                        SBE_FREE(v15);
                      }
                    }
                  }
                }
                SBE_FREE(v11);
              }
            }
          }
          if ( (*(_BYTE *)(a1 + 12) & 4) != 0 )
          {
            OSBESetOsLoadOptions(v5, a1 + 48);
            v20 = (_DWORD *)(a1 + *(unsigned int *)(a1 + 44));
            if ( v20[9] == 3 )
            {
              OSBESetBootVolumeName(v5, v20 + 10);
              do
                ++v7;
              while ( *((_WORD *)v20 + v7 + 20) );
              OSBESetBootPath(v5, (char *)v20 + 2 * v7 + 42);
            }
            else
            {
              v21 = (unsigned int)(v20[8] + 16);
              LODWORD(Size) = v20[8] + 16;
              if ( AllocRoutine )
              {
                v22 = (_DWORD *)AllocRoutine(v21);
                v23 = v22;
                if ( v22 )
                {
                  memset_0(v22, 0, (unsigned int)Size);
                  if ( EFIGetHardDrivePath(v20 + 7, v23) )
                  {
                    LODWORD(Size) = 0;
                    EfiTranslateFilePath(v23, v24, 0, &Size);
                    if ( (_DWORD)Size )
                    {
                      if ( AllocRoutine )
                      {
                        v25 = AllocRoutine((unsigned int)Size);
                        v27 = v25;
                        if ( v25 )
                        {
                          if ( (int)EfiTranslateFilePath(v23, v26, v25, &Size) >= 0 )
                          {
                            OSBESetBootVolumeName(v5, v27 + 12);
                            do
                              ++v7;
                            while ( *(_WORD *)(v27 + 2 * v7 + 12) );
                            OSBESetBootPath(v5, v27 + 14 + 2 * v7);
                          }
                          SBE_FREE(v27);
                        }
                      }
                    }
                  }
                  SBE_FREE(v23);
                }
              }
            }
          }
        }
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180012dfc  mov     dword ptr [rsp-40h+Size], r8d
0x180012e01  push    rbp
0x180012e02  push    rbx
0x180012e03  push    rsi
0x180012e04  push    rdi
0x180012e05  push    r12
0x180012e07  push    r13
0x180012e09  push    r14
0x180012e0b  push    r15
0x180012e0d  mov     rbp, rsp
0x180012e10  sub     rsp, 28h
0x180012e14  xor     r13d, r13d
0x180012e17  mov     rsi, rdx
0x180012e1a  mov     rdi, rcx
0x180012e1d  mov     ebx, r13d
0x180012e20  test    rcx, rcx
0x180012e23  jz      loc_1800130D8
0x180012e29  test    rdx, rdx
0x180012e2c  jz      loc_1800130D8
0x180012e32  mov     rax, cs:AllocRoutine
0x180012e39  test    rax, rax
0x180012e3c  jz      loc_1800130D8
0x180012e42  mov     r14d, 0C68h
0x180012e48  mov     ecx, r14d
0x180012e4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e50  mov     rbx, rax
0x180012e53  test    rax, rax
0x180012e56  jz      loc_1800130D8
0x180012e5c  mov     r8d, r14d; Size
0x180012e5f  mov     dword ptr [rbp+Size], r13d
0x180012e63  xor     edx, edx; Val
0x180012e65  mov     rcx, rax; void *
0x180012e68  call    memset_0
0x180012e6d  lea     rax, EFIOSBEDelete
0x180012e74  mov     [rbx+0C50h], rax
0x180012e7b  lea     rax, EFIOSBEFlush
0x180012e82  mov     [rbx+0C58h], rax
0x180012e89  mov     eax, [rdi+8]
0x180012e8c  mov     [rbx+4], eax
0x180012e8f  mov     [rbx+0C40h], rsi
0x180012e96  test    byte ptr [rdi+0Ch], 4
0x180012e9a  jz      short loc_180012EA3
0x180012e9c  or      dword ptr [rbx+0C38h], 4
0x180012ea3  mov     edx, [rdi+10h]
0x180012ea6  mov     rcx, rbx
0x180012ea9  add     rdx, rdi
0x180012eac  call    OSBESetFriendlyName
0x180012eb1  mov     r14d, [rdi+14h]
0x180012eb5  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180012eb9  add     r14, rdi
0x180012ebc  cmp     dword ptr [r14+8], 3
0x180012ec1  jz      loc_180012F94
0x180012ec7  mov     eax, [r14+4]
0x180012ecb  add     eax, 10h
0x180012ece  mov     ecx, eax
0x180012ed0  mov     dword ptr [rbp+Size], eax
0x180012ed3  mov     rax, cs:AllocRoutine
0x180012eda  test    rax, rax
0x180012edd  jz      loc_180012FBF
0x180012ee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ee8  mov     r15, rax
0x180012eeb  test    rax, rax
0x180012eee  jz      loc_180012FBF
0x180012ef4  mov     r8d, dword ptr [rbp+Size]; Size
0x180012ef8  xor     edx, edx; Val
0x180012efa  mov     rcx, rax; void *
0x180012efd  call    memset_0
0x180012f02  mov     rdx, r15
0x180012f05  mov     rcx, r14
0x180012f08  call    EFIGetHardDrivePath
0x180012f0d  test    al, al
0x180012f0f  jz      short loc_180012F8A
0x180012f11  lea     r9, [rbp+Size]
0x180012f15  mov     dword ptr [rbp+Size], r13d
0x180012f19  xor     r8d, r8d
0x180012f1c  mov     rcx, r15
0x180012f1f  call    EfiTranslateFilePath
0x180012f24  mov     ecx, dword ptr [rbp+Size]
0x180012f27  test    ecx, ecx
0x180012f29  jz      short loc_180012F8A
0x180012f2b  mov     rax, cs:AllocRoutine
0x180012f32  test    rax, rax
0x180012f35  jz      short loc_180012F8A
0x180012f37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f3c  mov     r14, rax
0x180012f3f  test    rax, rax
0x180012f42  jz      short loc_180012F8A
0x180012f44  lea     r9, [rbp+Size]
0x180012f48  mov     r8, rax
0x180012f4b  mov     rcx, r15
0x180012f4e  call    EfiTranslateFilePath
0x180012f53  test    eax, eax
0x180012f55  js      short loc_180012F82
0x180012f57  lea     r12, [r14+0Ch]
0x180012f5b  mov     rcx, rbx
0x180012f5e  mov     rdx, r12
0x180012f61  call    OSBESetOsLoaderVolumeName
0x180012f66  mov     rax, rsi
0x180012f69  inc     rax
0x180012f6c  cmp     [r12+rax*2], r13w
0x180012f71  jnz     short loc_180012F69
0x180012f73  inc     rax
0x180012f76  mov     rcx, rbx
0x180012f79  lea     rdx, [r12+rax*2]
0x180012f7d  call    OSBESetOsLoaderPath
0x180012f82  mov     rcx, r14
0x180012f85  call    SBE_FREE
0x180012f8a  mov     rcx, r15
0x180012f8d  call    SBE_FREE
0x180012f92  jmp     short loc_180012FBF
0x180012f94  add     r14, 0Ch
0x180012f98  mov     rcx, rbx
0x180012f9b  mov     rdx, r14
0x180012f9e  call    OSBESetOsLoaderVolumeName
0x180012fa3  mov     rax, rsi
0x180012fa6  inc     rax
0x180012fa9  cmp     [r14+rax*2], r13w
0x180012fae  jnz     short loc_180012FA6
0x180012fb0  inc     rax
0x180012fb3  mov     rcx, rbx
0x180012fb6  lea     rdx, [r14+rax*2]
0x180012fba  call    OSBESetOsLoaderPath
0x180012fbf  test    byte ptr [rdi+0Ch], 4
0x180012fc3  jz      loc_1800130D8
0x180012fc9  lea     rdx, [rdi+30h]
0x180012fcd  mov     rcx, rbx
0x180012fd0  call    OSBESetOsLoadOptions
0x180012fd5  mov     r14d, [rdi+2Ch]
0x180012fd9  add     r14, rdi
0x180012fdc  cmp     dword ptr [r14+24h], 3
0x180012fe1  jz      loc_1800130B1
0x180012fe7  mov     eax, [r14+20h]
0x180012feb  add     eax, 10h
0x180012fee  mov     ecx, eax
0x180012ff0  mov     dword ptr [rbp+Size], eax
0x180012ff3  mov     rax, cs:AllocRoutine
0x180012ffa  test    rax, rax
0x180012ffd  jz      loc_1800130D8
0x180013003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013008  mov     rdi, rax
0x18001300b  test    rax, rax
0x18001300e  jz      loc_1800130D8
0x180013014  mov     r8d, dword ptr [rbp+Size]; Size
0x180013018  xor     edx, edx; Val
0x18001301a  mov     rcx, rax; void *
0x18001301d  call    memset_0
0x180013022  mov     rdx, rdi
0x180013025  lea     rcx, [r14+1Ch]
0x180013029  call    EFIGetHardDrivePath
0x18001302e  test    al, al
0x180013030  jz      short loc_1800130A7
0x180013032  lea     r9, [rbp+Size]
0x180013036  mov     dword ptr [rbp+Size], r13d
0x18001303a  xor     r8d, r8d
0x18001303d  mov     rcx, rdi
0x180013040  call    EfiTranslateFilePath
0x180013045  mov     ecx, dword ptr [rbp+Size]
0x180013048  test    ecx, ecx
0x18001304a  jz      short loc_1800130A7
0x18001304c  mov     rax, cs:AllocRoutine
0x180013053  test    rax, rax
0x180013056  jz      short loc_1800130A7
0x180013058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001305d  mov     r14, rax
0x180013060  test    rax, rax
0x180013063  jz      short loc_1800130A7
0x180013065  lea     r9, [rbp+Size]
0x180013069  mov     r8, rax
0x18001306c  mov     rcx, rdi
0x18001306f  call    EfiTranslateFilePath
0x180013074  test    eax, eax
0x180013076  js      short loc_18001309F
0x180013078  lea     rdx, [r14+0Ch]
0x18001307c  mov     rcx, rbx
0x18001307f  call    OSBESetBootVolumeName
0x180013084  inc     rsi
0x180013087  cmp     [r14+rsi*2+0Ch], r13w
0x18001308d  jnz     short loc_180013084
0x18001308f  lea     rdx, [r14+0Eh]
0x180013093  mov     rcx, rbx
0x180013096  lea     rdx, [rdx+rsi*2]
0x18001309a  call    OSBESetBootPath
0x18001309f  mov     rcx, r14
0x1800130a2  call    SBE_FREE
0x1800130a7  mov     rcx, rdi
0x1800130aa  call    SBE_FREE
0x1800130af  jmp     short loc_1800130D8
0x1800130b1  lea     rdx, [r14+28h]
0x1800130b5  mov     rcx, rbx
0x1800130b8  call    OSBESetBootVolumeName
0x1800130bd  inc     rsi
0x1800130c0  cmp     [r14+rsi*2+28h], r13w
0x1800130c6  jnz     short loc_1800130BD
0x1800130c8  lea     rdx, [r14+2Ah]
0x1800130cc  mov     rcx, rbx
0x1800130cf  lea     rdx, [rdx+rsi*2]
0x1800130d3  call    OSBESetBootPath
0x1800130d8  mov     rax, rbx
0x1800130db  add     rsp, 28h
0x1800130df  pop     r15
0x1800130e1  pop     r14
0x1800130e3  pop     r13
0x1800130e5  pop     r12
0x1800130e7  pop     rdi
0x1800130e8  pop     rsi
0x1800130e9  pop     rbx
0x1800130ea  pop     rbp
0x1800130eb  retn
```
