# SkmmCommitPreRegisterHvImage

- ea: `0x14004b838`
- end: `0x14004ba4a`
- name: `SkmmCommitPreRegisterHvImage`
- size: `530`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140002900`
- `0x14000b084`
- `0x14004b838`
- `0x140095cd8`
- `0x1400ee8b0`
- `0x1400f3620`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmmCommitPreRegisterHvImage(int a1)
{
  _QWORD *v1; // rcx
  __int64 v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r9
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  bool v7; // zf
  __int64 v9; // rdi
  __int64 v10; // rsi
  __int64 v11; // r14
  __int64 v12; // r8
  __int64 v13; // r9
  _QWORD *StackBase; // rcx
  __int64 v15; // rdx
  unsigned int v16; // [rsp+30h] [rbp-49h] BYREF
  __int64 v17; // [rsp+38h] [rbp-41h]
  __int64 v18; // [rsp+40h] [rbp-39h]
  __int64 v19; // [rsp+48h] [rbp-31h]
  __int64 v20; // [rsp+50h] [rbp-29h]
  __int64 v21; // [rsp+58h] [rbp-21h]

  if ( a1 != -1073740682 )
  {
    if ( !a1 )
    {
      memset_0(&v16, 0, 0x68u);
      HIWORD(v16) = 50;
      v17 = (unsigned int)SkmiHvImageCheckSum;
      v18 = (unsigned int)SkmiHvImageTimeDateStamp;
      SkCallNormalMode(&v16);
      v9 = DWORD2(SkmiHvPreRegisteredImage);
      v10 = (unsigned int)SkmiHvPreRegisteredImage;
      v11 = DWORD1(SkmiHvPreRegisteredImage);
      __SET_PAIR__(SkmiHvImageTimeDateStamp, SkmiHvImageCheckSum, SkmiHvPreRegisteredImage);
      SkmiHvPatchSequence = DWORD2(SkmiHvPreRegisteredImage);
      if ( DWORD2(SkmiHvPreRegisteredImage) )
      {
        memset_0(&v16, 0, 0x68u);
        v17 = v10;
        HIWORD(v16) = 49;
        v20 = HIDWORD(SkmiHvPreRegisteredImage);
        v21 = (unsigned int)dword_140157070;
        v18 = v11;
        v19 = v9;
        SkCallNormalMode(&v16);
      }
      SkmiHvPreRegisteredImageValid = 0;
      SkmiHvPreRegisteredImage = 0;
      dword_140157070 = 0;
    }
    RtlReleaseSRWLockExclusive(&SkmiHvImageLock);
    StackBase = KeGetPcr()->NtTib.StackBase;
    if ( StackBase )
    {
      v15 = StackBase[18];
      if ( v15 )
      {
        v7 = (*(_WORD *)(v15 + xmmword_140167150))++ == 0xFFFF;
        if ( v7
          && *(_QWORD *)(v15 + xmmword_140167160) != (_QWORD)xmmword_140167160 + StackBase[17]
          && !*(_WORD *)(v15 + *((_QWORD *)&xmmword_140167150 + 1)) )
        {
          SkiCheckForKernelApcDelivery(xmmword_140167160, v15, v12, v13);
        }
      }
    }
    return 0;
  }
  v1 = KeGetPcr()->NtTib.StackBase;
  if ( v1 )
  {
    v2 = v1[18];
    if ( v2 )
      --*(_WORD *)(v2 + xmmword_140167150);
  }
  SkAcquirePushLockExclusive(&SkmiHvImageLock);
  if ( SkmiHvPreRegisteredImageValid )
    return 0;
  RtlReleaseSRWLockExclusive(&SkmiHvImageLock);
  v5 = KeGetPcr()->NtTib.StackBase;
  if ( v5 )
  {
    v6 = v5[18];
    if ( v6 )
    {
      v7 = (*(_WORD *)(v6 + xmmword_140167150))++ == 0xFFFF;
      if ( v7
        && *(_QWORD *)(v6 + xmmword_140167160) != (_QWORD)xmmword_140167160 + v5[17]
        && !*(_WORD *)(v6 + *((_QWORD *)&xmmword_140167150 + 1)) )
      {
        SkiCheckForKernelApcDelivery(xmmword_140167160, v6, v3, v4);
      }
    }
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x14004b838  push    rbp
0x14004b83a  push    rbx
0x14004b83b  push    rsi
0x14004b83c  push    rdi
0x14004b83d  push    r14
0x14004b83f  lea     rbp, [rsp-37h]
0x14004b844  sub     rsp, 0B0h
0x14004b84b  mov     rax, cs:__security_cookie
0x14004b852  xor     rax, rsp
0x14004b855  mov     [rbp+57h+var_30], rax
0x14004b859  xor     ebx, ebx
0x14004b85b  cmp     ecx, 0C0000476h
0x14004b861  jnz     loc_14004B90E
0x14004b867  mov     rcx, gs:8
0x14004b870  test    rcx, rcx
0x14004b873  jz      short loc_14004B88D
0x14004b875  mov     rcx, [rcx+90h]
0x14004b87c  test    rcx, rcx
0x14004b87f  jz      short loc_14004B88D
0x14004b881  mov     rax, qword ptr cs:xmmword_140167150
0x14004b888  dec     word ptr [rcx+rax]
0x14004b88c  nop
0x14004b88d  lea     rcx, SkmiHvImageLock
0x14004b894  call    SkAcquirePushLockExclusive
0x14004b899  cmp     cs:SkmiHvPreRegisteredImageValid, bl
0x14004b89f  jnz     loc_14004BA2D
0x14004b8a5  lea     rcx, SkmiHvImageLock
0x14004b8ac  call    RtlReleaseSRWLockExclusive
0x14004b8b1  mov     rcx, gs:8
0x14004b8ba  test    rcx, rcx
0x14004b8bd  jz      short loc_14004B904
0x14004b8bf  mov     rdx, [rcx+90h]
0x14004b8c6  test    rdx, rdx
0x14004b8c9  jz      short loc_14004B904
0x14004b8cb  nop
0x14004b8cc  mov     rax, qword ptr cs:xmmword_140167150
0x14004b8d3  add     word ptr [rdx+rax], 1
0x14004b8d8  jnz     short loc_14004B904
0x14004b8da  mov     rax, [rcx+88h]
0x14004b8e1  nop
0x14004b8e2  mov     rcx, qword ptr cs:xmmword_140167160
0x14004b8e9  add     rax, rcx
0x14004b8ec  cmp     [rdx+rcx], rax
0x14004b8f0  jz      short loc_14004B904
0x14004b8f2  mov     rax, qword ptr cs:xmmword_140167150+8
0x14004b8f9  cmp     [rdx+rax], bx
0x14004b8fd  jnz     short loc_14004B904
0x14004b8ff  call    SkiCheckForKernelApcDelivery
0x14004b904  mov     eax, 0C000000Dh
0x14004b909  jmp     loc_14004BA2F
0x14004b90e  test    ecx, ecx
0x14004b910  jnz     loc_14004B9CE
0x14004b916  lea     r8d, [rcx+68h]; Size
0x14004b91a  xor     edx, edx; Val
0x14004b91c  lea     rcx, [rbp+57h+var_A0]; void *
0x14004b920  call    memset_0
0x14004b925  mov     eax, 32h ; '2'
0x14004b92a  lea     rcx, [rbp+57h+var_A0]
0x14004b92e  mov     [rbp+57h+var_9E], ax
0x14004b932  mov     eax, cs:SkmiHvImageCheckSum
0x14004b938  mov     [rbp+57h+var_98], rax
0x14004b93c  mov     eax, cs:SkmiHvImageTimeDateStamp
0x14004b942  mov     [rbp+57h+var_90], rax
0x14004b946  call    SkCallNormalMode
0x14004b94b  mov     edi, dword ptr cs:SkmiHvPreRegisteredImage+8
0x14004b951  mov     esi, dword ptr cs:SkmiHvPreRegisteredImage
0x14004b957  mov     r14d, dword ptr cs:SkmiHvPreRegisteredImage+4
0x14004b95e  mov     cs:SkmiHvImageCheckSum, esi
0x14004b964  mov     cs:SkmiHvImageTimeDateStamp, r14d
0x14004b96b  mov     cs:SkmiHvPatchSequence, edi
0x14004b971  test    edi, edi
0x14004b973  jz      short loc_14004B9B6
0x14004b975  xor     edx, edx; Val
0x14004b977  lea     rcx, [rbp+57h+var_A0]; void *
0x14004b97b  lea     r8d, [rdx+68h]; Size
0x14004b97f  call    memset_0
0x14004b984  mov     eax, 31h ; '1'
0x14004b989  mov     [rbp+57h+var_98], rsi
0x14004b98d  mov     [rbp+57h+var_9E], ax
0x14004b991  lea     rcx, [rbp+57h+var_A0]
0x14004b995  mov     eax, dword ptr cs:SkmiHvPreRegisteredImage+0Ch
0x14004b99b  mov     [rbp+57h+var_80], rax
0x14004b99f  mov     eax, cs:dword_140157070
0x14004b9a5  mov     [rbp+57h+var_78], rax
0x14004b9a9  mov     [rbp+57h+var_90], r14
0x14004b9ad  mov     [rbp+57h+var_88], rdi
0x14004b9b1  call    SkCallNormalMode
0x14004b9b6  xorps   xmm0, xmm0
0x14004b9b9  mov     cs:SkmiHvPreRegisteredImageValid, bl
0x14004b9bf  xor     eax, eax
0x14004b9c1  movups  cs:SkmiHvPreRegisteredImage, xmm0
0x14004b9c8  mov     cs:dword_140157070, eax
0x14004b9ce  lea     rcx, SkmiHvImageLock
0x14004b9d5  call    RtlReleaseSRWLockExclusive
0x14004b9da  mov     rcx, gs:8
0x14004b9e3  test    rcx, rcx
0x14004b9e6  jz      short loc_14004BA2D
0x14004b9e8  mov     rdx, [rcx+90h]
0x14004b9ef  test    rdx, rdx
0x14004b9f2  jz      short loc_14004BA2D
0x14004b9f4  nop
0x14004b9f5  mov     rax, qword ptr cs:xmmword_140167150
0x14004b9fc  add     word ptr [rdx+rax], 1
0x14004ba01  jnz     short loc_14004BA2D
0x14004ba03  mov     rax, [rcx+88h]
0x14004ba0a  nop
0x14004ba0b  mov     rcx, qword ptr cs:xmmword_140167160
0x14004ba12  add     rax, rcx
0x14004ba15  cmp     [rdx+rcx], rax
0x14004ba19  jz      short loc_14004BA2D
0x14004ba1b  mov     rax, qword ptr cs:xmmword_140167150+8
0x14004ba22  cmp     [rdx+rax], bx
0x14004ba26  jnz     short loc_14004BA2D
0x14004ba28  call    SkiCheckForKernelApcDelivery
0x14004ba2d  xor     eax, eax
0x14004ba2f  mov     rcx, [rbp+57h+var_30]
0x14004ba33  xor     rcx, rsp; StackCookie
0x14004ba36  call    __security_check_cookie
0x14004ba3b  add     rsp, 0B0h
0x14004ba42  pop     r14
0x14004ba44  pop     rdi
0x14004ba45  pop     rsi
0x14004ba46  pop     rbx
0x14004ba47  pop     rbp
0x14004ba48  retn
```
