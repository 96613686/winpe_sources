# RtlUpdateImportRelocationsInImage

- ea: `0x1400ddb64`
- end: `0x1400ddd63`
- name: `RtlUpdateImportRelocationsInImage`
- size: `511`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14007df94`
- `0x14007f214`

## callees

- `0x14000f0f0`
- `0x140037e68`
- `0x1400d65ac`
- `0x1400dd0c8`
- `0x1400dd34c`
- `0x1400ddb64`
- `0x1400dde38`

## pseudocode

```c
__int64 __fastcall RtlUpdateImportRelocationsInImage(
        __int64 a1,
        int a2,
        unsigned int a3,
        int a4,
        __int64 a5,
        __int64 a6,
        unsigned int a7,
        unsigned __int8 a8)
{
  int v12; // ebx
  int v13; // eax
  __int64 v14; // r14
  unsigned __int64 v15; // rax
  unsigned __int64 v16; // rdx
  __int64 v17; // rcx
  _DWORD *v18; // rbx
  unsigned __int64 v19; // r12
  unsigned __int64 v20; // r15
  _DWORD *v21; // rsi
  unsigned __int64 v23; // [rsp+40h] [rbp-51h] BYREF
  __int64 Pool; // [rsp+48h] [rbp-49h]
  __int128 v25; // [rsp+50h] [rbp-41h] BYREF
  __int128 v26; // [rsp+60h] [rbp-31h]
  __int128 v27; // [rsp+70h] [rbp-21h]
  __int64 v28; // [rsp+80h] [rbp-11h]

  v28 = 0;
  LODWORD(v23) = 0;
  a7 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v12 = RtlpCaptureRetpolineBinaryInfoForImage(a1, a2, a3, a5, a6, (__int64)&v25);
  if ( v12 >= 0 )
  {
    v13 = RtlCaptureRetpolineImportRvas(a1, a2, a3, a4, 0, (__int64)&a7);
    v12 = v13;
    if ( v13 >= 0 )
    {
      return (unsigned int)-1073741637;
    }
    else if ( v13 == -1073741789 )
    {
      Pool = SkAllocatePool(1, a7);
      v14 = Pool;
      if ( Pool )
      {
        v12 = RtlCaptureRetpolineImportRvas(a1, a2, a3, a4, Pool, (__int64)&a7);
        if ( v12 >= 0 )
        {
          *(_QWORD *)&v26 = Pool;
          v12 = RtlpCaptureDynamicRelocationTableRva(a1, a3, &v23);
          if ( v12 >= 0 )
          {
            if ( *(_DWORD *)((unsigned int)v23 + a1) == 1 )
            {
              v15 = a1 + (unsigned int)v23 + 8LL;
              v16 = v15 + *(unsigned int *)((unsigned int)v23 + a1 + 4);
              while ( v15 < v16 )
              {
                v17 = *(unsigned int *)(v15 + 8);
                if ( *(_QWORD *)v15 == 3 )
                {
                  v18 = (_DWORD *)(v15 + 12);
                  v19 = v17 + v15 + 12;
                  v23 = v19;
                  if ( v15 + 12 < v19 )
                  {
                    do
                    {
                      v20 = (unsigned __int64)v18 + (unsigned int)v18[1];
                      v21 = v18 + 2;
                      if ( (unsigned __int64)(v18 + 2) < v20 )
                      {
                        do
                        {
                          if ( (*v21 & 0xFFF) == 0 && v21 != v18 + 2 )
                            break;
                          RtlApplyImportRelocationToImage(a1, a3, (unsigned int)&v25, a6, *v18, (__int64)v21++, 1, a8);
                        }
                        while ( (unsigned __int64)v21 < v20 );
                        v19 = v23;
                      }
                      v18 = (_DWORD *)((char *)v18 + (unsigned int)v18[1]);
                    }
                    while ( (unsigned __int64)v18 < v19 );
                    v14 = Pool;
                  }
                  v12 = 0;
                  goto LABEL_23;
                }
                v15 += v17 + 12;
              }
            }
            v12 = -1073741637;
          }
        }
LABEL_23:
        SkFreePool(1, v14);
      }
      else
      {
        return (unsigned int)-1073741801;
      }
    }
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1400ddb64  mov     [rsp-8+arg_10], r8d
0x1400ddb69  push    rbp
0x1400ddb6a  push    rbx
0x1400ddb6b  push    rsi
0x1400ddb6c  push    rdi
0x1400ddb6d  push    r12
0x1400ddb6f  push    r13
0x1400ddb71  push    r14
0x1400ddb73  push    r15
0x1400ddb75  lea     rbp, [rsp-7]
0x1400ddb7a  sub     rsp, 98h
0x1400ddb81  xor     eax, eax
0x1400ddb83  mov     r13d, r8d
0x1400ddb86  xorps   xmm0, xmm0
0x1400ddb89  mov     [rbp+3Fh+var_50], rax
0x1400ddb8d  lea     rax, [rbp+3Fh+var_80]
0x1400ddb91  mov     r12, r9
0x1400ddb94  mov     r9, [rbp+3Fh+arg_20]
0x1400ddb98  xor     r14d, r14d
0x1400ddb9b  mov     [rsp+0D0h+var_A8], rax
0x1400ddba0  mov     r15, rdx
0x1400ddba3  mov     rax, [rbp+3Fh+arg_28]
0x1400ddba7  mov     rdi, rcx
0x1400ddbaa  mov     [rsp+0D0h+var_B0], rax
0x1400ddbaf  mov     dword ptr [rbp+3Fh+var_90], r14d
0x1400ddbb3  mov     [rbp+3Fh+arg_30], r14d
0x1400ddbb7  movups  [rbp+3Fh+var_80], xmm0
0x1400ddbbb  movups  [rbp+3Fh+var_70], xmm0
0x1400ddbbf  movups  [rbp+3Fh+var_60], xmm0
0x1400ddbc3  call    RtlpCaptureRetpolineBinaryInfoForImage
0x1400ddbc8  mov     ebx, eax
0x1400ddbca  test    eax, eax
0x1400ddbcc  js      loc_1400DDD4C
0x1400ddbd2  lea     rax, [rbp+3Fh+arg_30]
0x1400ddbd6  mov     r9, r12
0x1400ddbd9  mov     [rsp+0D0h+var_A8], rax
0x1400ddbde  mov     r8d, r13d
0x1400ddbe1  mov     rdx, r15
0x1400ddbe4  mov     [rsp+0D0h+var_B0], r14
0x1400ddbe9  mov     rcx, rdi
0x1400ddbec  call    RtlCaptureRetpolineImportRvas
0x1400ddbf1  mov     ebx, eax
0x1400ddbf3  test    eax, eax
0x1400ddbf5  jns     loc_1400DDD47
0x1400ddbfb  cmp     eax, 0C0000023h
0x1400ddc00  jnz     loc_1400DDD4C
0x1400ddc06  mov     edx, [rbp+3Fh+arg_30]
0x1400ddc09  lea     ecx, [r14+1]
0x1400ddc0d  mov     r8d, 496C7052h
0x1400ddc13  call    SkAllocatePool
0x1400ddc18  mov     [rbp+3Fh+var_88], rax
0x1400ddc1c  mov     r14, rax
0x1400ddc1f  test    rax, rax
0x1400ddc22  jnz     short loc_1400DDC2E
0x1400ddc24  mov     ebx, 0C0000017h
0x1400ddc29  jmp     loc_1400DDD4C
0x1400ddc2e  lea     rax, [rbp+3Fh+arg_30]
0x1400ddc32  mov     r9, r12
0x1400ddc35  mov     [rsp+0D0h+var_A8], rax
0x1400ddc3a  mov     r8, r13
0x1400ddc3d  mov     rdx, r15
0x1400ddc40  mov     [rsp+0D0h+var_B0], r14
0x1400ddc45  mov     rcx, rdi
0x1400ddc48  call    RtlCaptureRetpolineImportRvas
0x1400ddc4d  mov     ebx, eax
0x1400ddc4f  test    eax, eax
0x1400ddc51  js      loc_1400DDD38
0x1400ddc57  lea     r8, [rbp+3Fh+var_90]
0x1400ddc5b  mov     qword ptr [rbp+3Fh+var_70], r14
0x1400ddc5f  mov     edx, r13d
0x1400ddc62  mov     rcx, rdi
0x1400ddc65  call    RtlpCaptureDynamicRelocationTableRva
0x1400ddc6a  mov     ebx, eax
0x1400ddc6c  test    eax, eax
0x1400ddc6e  js      loc_1400DDD38
0x1400ddc74  mov     ecx, dword ptr [rbp+3Fh+var_90]
0x1400ddc77  cmp     dword ptr [rcx+rdi], 1
0x1400ddc7b  jnz     loc_1400DDD33
0x1400ddc81  mov     edx, [rcx+rdi+4]
0x1400ddc85  lea     rax, [rcx+8]
0x1400ddc89  add     rax, rdi
0x1400ddc8c  add     rdx, rax
0x1400ddc8f  cmp     rax, rdx
0x1400ddc92  jnb     loc_1400DDD33
0x1400ddc98  cmp     qword ptr [rax], 3
0x1400ddc9c  mov     ecx, [rax+8]
0x1400ddc9f  jz      short loc_1400DDCAA
0x1400ddca1  add     rax, 0Ch
0x1400ddca5  add     rax, rcx
0x1400ddca8  jmp     short loc_1400DDC8F
0x1400ddcaa  lea     rbx, [rax+0Ch]
0x1400ddcae  lea     r12, [rcx+rbx]
0x1400ddcb2  mov     [rbp+3Fh+var_90], r12
0x1400ddcb6  cmp     rbx, r12
0x1400ddcb9  jnb     short loc_1400DDD2F
0x1400ddcbb  mov     r14d, [rbp+3Fh+arg_10]
0x1400ddcbf  mov     r15d, [rbx+4]
0x1400ddcc3  lea     r13, [rbx+8]
0x1400ddcc7  add     r15, rbx
0x1400ddcca  mov     rsi, r13
0x1400ddccd  cmp     r13, r15
0x1400ddcd0  jnb     short loc_1400DDD20
0x1400ddcd2  mov     r12, [rbp+3Fh+arg_28]
0x1400ddcd6  test    dword ptr [rsi], 0FFFh
0x1400ddcdc  jnz     short loc_1400DDCE3
0x1400ddcde  cmp     rsi, r13
0x1400ddce1  jnz     short loc_1400DDD1C
0x1400ddce3  movzx   eax, [rbp+3Fh+arg_38]
0x1400ddcea  lea     r8, [rbp+3Fh+var_80]
0x1400ddcee  mov     [rsp+0D0h+var_98], eax
0x1400ddcf2  mov     r9, r12
0x1400ddcf5  mov     eax, [rbx]
0x1400ddcf7  mov     edx, r14d
0x1400ddcfa  mov     [rsp+0D0h+var_A0], 1
0x1400ddd02  mov     rcx, rdi
0x1400ddd05  mov     [rsp+0D0h+var_A8], rsi
0x1400ddd0a  mov     dword ptr [rsp+0D0h+var_B0], eax
0x1400ddd0e  call    RtlApplyImportRelocationToImage
0x1400ddd13  add     rsi, 4
0x1400ddd17  cmp     rsi, r15
0x1400ddd1a  jb      short loc_1400DDCD6
0x1400ddd1c  mov     r12, [rbp+3Fh+var_90]
0x1400ddd20  mov     eax, [rbx+4]
0x1400ddd23  add     rbx, rax
0x1400ddd26  cmp     rbx, r12
0x1400ddd29  jb      short loc_1400DDCBF
0x1400ddd2b  mov     r14, [rbp+3Fh+var_88]
0x1400ddd2f  xor     ebx, ebx
0x1400ddd31  jmp     short loc_1400DDD38
0x1400ddd33  mov     ebx, 0C00000BBh
0x1400ddd38  mov     rdx, r14
0x1400ddd3b  mov     ecx, 1
0x1400ddd40  call    SkFreePool
0x1400ddd45  jmp     short loc_1400DDD4C
0x1400ddd47  mov     ebx, 0C00000BBh
0x1400ddd4c  mov     eax, ebx
0x1400ddd4e  add     rsp, 98h
0x1400ddd55  pop     r15
0x1400ddd57  pop     r14
0x1400ddd59  pop     r13
0x1400ddd5b  pop     r12
0x1400ddd5d  pop     rdi
0x1400ddd5e  pop     rsi
0x1400ddd5f  pop     rbx
0x1400ddd60  pop     rbp
0x1400ddd61  retn
```
