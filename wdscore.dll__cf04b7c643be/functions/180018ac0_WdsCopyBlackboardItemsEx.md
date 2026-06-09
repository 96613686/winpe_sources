# WdsCopyBlackboardItemsEx

- ea: `0x180018ac0`
- end: `0x180018d4d`
- name: `WdsCopyBlackboardItemsEx`
- size: `653`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180018a90`

## callees

- `0x18000f73c`
- `0x18001220c`
- `0x180012464`
- `0x180012d1c`
- `0x1800179a4`
- `0x180017ab4`
- `0x180018140`
- `0x180018ac0`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall WdsCopyBlackboardItemsEx(
        CBlackboard *a1,
        struct _BLACKBOARD *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5)
{
  CBlackboardFactory *v6; // rbx
  __int64 v7; // rdx
  unsigned int v8; // r14d
  unsigned int v9; // r15d
  volatile int *v10; // rdi
  struct SEnumContext *v11; // r12
  char *v12; // rsi
  __int64 v13; // rsi
  volatile int *v14; // rsi
  __int64 v15; // rdi
  unsigned __int16 *v17[2]; // [rsp+60h] [rbp-68h] BYREF
  struct WDS_DATA *v18[2]; // [rsp+70h] [rbp-58h]
  __int64 v19; // [rsp+80h] [rbp-48h]

  if ( !a1 || !a2 )
  {
    v7 = 6;
    goto LABEL_47;
  }
  v6 = Block;
  if ( !Block )
  {
    v7 = 21;
LABEL_47:
    (*(void (__fastcall **)(struct IKernel32Interface *, __int64))(*(_QWORD *)g_Kernel32 + 8LL))(g_Kernel32, v7);
    return 0;
  }
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  if ( (unsigned __int64)a1 < 0x64 )
    goto LABEL_12;
  v12 = (char *)a1 - 100;
  if ( *((_QWORD *)Block + 2) <= (unsigned __int64)a1 - 100 )
    goto LABEL_12;
  AcquireReadAccess((volatile int *)Block);
  v13 = *((_QWORD *)v6 + 1) + 16LL * (_QWORD)v12;
  if ( v13 && *(_QWORD *)v13 )
    AcquireReadAccess((volatile int *)(*(_QWORD *)v13 + 128LL));
  ReleaseAccess((volatile int *)v6);
  v6 = Block;
  if ( v13 )
    v14 = *(volatile int **)v13;
  else
LABEL_12:
    v14 = 0;
  if ( !v14 )
    goto LABEL_14;
  if ( (unsigned __int64)a2 < 0x64 || *((_QWORD *)v6 + 2) <= (unsigned __int64)a2 - 100 )
    goto LABEL_22;
  AcquireReadAccess((volatile int *)v6);
  v15 = *((_QWORD *)v6 + 1) + 16LL * ((_QWORD)a2 - 100);
  if ( v15 && *(_QWORD *)v15 )
    AcquireReadAccess((volatile int *)(*(_QWORD *)v15 + 128LL));
  ReleaseAccess((volatile int *)v6);
  if ( v15 )
    v10 = *(volatile int **)v15;
  else
LABEL_22:
    v10 = 0;
  if ( v10 )
  {
    if ( v14 == v10 )
    {
      v8 = 87;
    }
    else
    {
      v11 = CBlackboard::EnumFirst((CBlackboard *)v14, a3, a4, 6u);
      if ( v11 )
      {
        *(_OWORD *)v17 = 0;
        *(_OWORD *)v18 = 0;
        v19 = 0;
        while ( (unsigned int)CBlackboard::EnumNext((CBlackboard *)v14, v11, (struct WDS_BLACKBOARD_ENUM *)v17) )
        {
          if ( !(unsigned int)CBlackboard::SetValue(
                                (CBlackboard *)v10,
                                v17[1],
                                (const unsigned __int16 *)v18[0],
                                v18[1],
                                0) )
          {
            v8 = 5;
            goto LABEL_34;
          }
        }
        v9 = 1;
      }
      else
      {
        v8 = 2;
      }
    }
  }
  else
  {
LABEL_14:
    v8 = 6;
  }
LABEL_34:
  if ( v14 )
  {
    if ( v11 )
      CBlackboard::EnumClose(a1, v11);
    ReleaseAccess(v14 + 32);
  }
  if ( v10 )
    ReleaseAccess(v10 + 32);
  if ( v9 )
  {
    if ( a5 )
    {
      if ( !(unsigned int)CBlackboardFactory::Redirect(a1, a1, a2) )
      {
        v9 = 0;
        (*(void (__fastcall **)(struct IKernel32Interface *, __int64))(*(_QWORD *)g_Kernel32 + 8LL))(g_Kernel32, 8);
      }
    }
  }
  else
  {
    (*(void (__fastcall **)(struct IKernel32Interface *, _QWORD))(*(_QWORD *)g_Kernel32 + 8LL))(g_Kernel32, v8);
  }
  return v9;
}

```

## disassembly

```asm
0x180018ac0  mov     [rsp+arg_18], r9
0x180018ac5  mov     [rsp+arg_10], r8
0x180018aca  mov     [rsp+arg_0], rcx
0x180018acf  push    rbx
0x180018ad0  push    rsi
0x180018ad1  push    rdi
0x180018ad2  push    r12
0x180018ad4  push    r13
0x180018ad6  push    r14
0x180018ad8  push    r15
0x180018ada  sub     rsp, 90h
0x180018ae1  mov     r13, rdx
0x180018ae4  mov     rax, rcx
0x180018ae7  test    rcx, rcx
0x180018aea  jz      loc_180018D1F
0x180018af0  test    rdx, rdx
0x180018af3  jz      loc_180018D1F
0x180018af9  mov     rbx, cs:Block
0x180018b00  test    rbx, rbx
0x180018b03  jnz     short loc_180018B0D
0x180018b05  lea     edx, [rbx+15h]
0x180018b08  jmp     loc_180018D24
0x180018b0d  xor     r14d, r14d
0x180018b10  xor     r15d, r15d
0x180018b13  mov     [rsp+0C8h+var_98], r14
0x180018b18  xor     edi, edi
0x180018b1a  mov     [rsp+0C8h+var_88], rdi
0x180018b1f  xor     r12d, r12d
0x180018b22  mov     [rsp+0C8h+var_90], r12
0x180018b27  mov     [rsp+0C8h+var_78], r12
0x180018b2c  cmp     rax, 64h ; 'd'
0x180018b30  jb      short loc_180018B80
0x180018b32  lea     rsi, [rcx-64h]
0x180018b36  cmp     [rbx+10h], rsi
0x180018b3a  jbe     short loc_180018B80
0x180018b3c  mov     [rsp+0C8h+var_78], rsi
0x180018b41  mov     rcx, rbx; volatile int *
0x180018b44  call    ?AcquireReadAccess@@YAXPECJ@Z; AcquireReadAccess(long volatile *)
0x180018b49  shl     rsi, 4
0x180018b4d  mov     rax, [rbx+8]
0x180018b51  add     rsi, rax
0x180018b54  jz      short loc_180018B67
0x180018b56  mov     rcx, [rsi]
0x180018b59  test    rcx, rcx
0x180018b5c  jz      short loc_180018B67
0x180018b5e  sub     rcx, 0FFFFFFFFFFFFFF80h; volatile int *
0x180018b62  call    ?AcquireReadAccess@@YAXPECJ@Z; AcquireReadAccess(long volatile *)
0x180018b67  mov     rcx, rbx; volatile int *
0x180018b6a  call    ?ReleaseAccess@@YAXPECJ@Z; ReleaseAccess(long volatile *)
0x180018b6f  mov     rbx, cs:Block
0x180018b76  test    rsi, rsi
0x180018b79  jz      short loc_180018B80
0x180018b7b  mov     rsi, [rsi]
0x180018b7e  jmp     short loc_180018B82
0x180018b80  xor     esi, esi
0x180018b82  mov     [rsp+0C8h+var_98], rsi
0x180018b87  test    rsi, rsi
0x180018b8a  jnz     short loc_180018B97
0x180018b8c  mov     r14d, 6
0x180018b92  jmp     loc_180018C9B
0x180018b97  mov     [rsp+0C8h+var_70], 0
0x180018ba0  cmp     r13, 64h ; 'd'
0x180018ba4  jb      short loc_180018BED
0x180018ba6  lea     rdi, [r13-64h]
0x180018baa  cmp     [rbx+10h], rdi
0x180018bae  jbe     short loc_180018BED
0x180018bb0  mov     [rsp+0C8h+var_70], rdi
0x180018bb5  mov     rcx, rbx; volatile int *
0x180018bb8  call    ?AcquireReadAccess@@YAXPECJ@Z; AcquireReadAccess(long volatile *)
0x180018bbd  shl     rdi, 4
0x180018bc1  mov     rax, [rbx+8]
0x180018bc5  add     rdi, rax
0x180018bc8  jz      short loc_180018BDB
0x180018bca  mov     rcx, [rdi]
0x180018bcd  test    rcx, rcx
0x180018bd0  jz      short loc_180018BDB
0x180018bd2  sub     rcx, 0FFFFFFFFFFFFFF80h; volatile int *
0x180018bd6  call    ?AcquireReadAccess@@YAXPECJ@Z; AcquireReadAccess(long volatile *)
0x180018bdb  mov     rcx, rbx; volatile int *
0x180018bde  call    ?ReleaseAccess@@YAXPECJ@Z; ReleaseAccess(long volatile *)
0x180018be3  test    rdi, rdi
0x180018be6  jz      short loc_180018BED
0x180018be8  mov     rdi, [rdi]
0x180018beb  jmp     short loc_180018BEF
0x180018bed  xor     edi, edi
0x180018bef  mov     [rsp+0C8h+var_88], rdi
0x180018bf4  test    rdi, rdi
0x180018bf7  jz      short loc_180018B8C
0x180018bf9  cmp     rsi, rdi
0x180018bfc  jnz     short loc_180018C09
0x180018bfe  mov     r14d, 57h ; 'W'
0x180018c04  jmp     loc_180018C9B
0x180018c09  mov     r9d, 6; unsigned int
0x180018c0f  mov     r8, [rsp+0C8h+arg_18]; unsigned __int16 *
0x180018c17  mov     rdx, [rsp+0C8h+arg_10]; unsigned __int16 *
0x180018c1f  mov     rcx, rsi; this
0x180018c22  call    ?EnumFirst@CBlackboard@@QEAAPEAUSEnumContext@@PEBG0K@Z; CBlackboard::EnumFirst(ushort const *,ushort const *,ulong)
0x180018c27  mov     r12, rax
0x180018c2a  mov     [rsp+0C8h+var_90], rax
0x180018c2f  test    rax, rax
0x180018c32  jnz     short loc_180018C3A
0x180018c34  lea     r14d, [rax+2]
0x180018c38  jmp     short loc_180018C9B
0x180018c3a  xorps   xmm0, xmm0
0x180018c3d  xor     eax, eax
0x180018c3f  movups  xmmword ptr [rsp+0C8h+var_68], xmm0
0x180018c44  movups  xmmword ptr [rsp+0C8h+var_58], xmm0
0x180018c49  mov     [rsp+0C8h+var_48], rax
0x180018c51  lea     r8, [rsp+0C8h+var_68]; struct WDS_BLACKBOARD_ENUM *
0x180018c56  mov     rdx, r12; struct SEnumContext *
0x180018c59  mov     rcx, rsi; this
0x180018c5c  call    ?EnumNext@CBlackboard@@QEAAHPEAUSEnumContext@@PEAUWDS_BLACKBOARD_ENUM@@@Z; CBlackboard::EnumNext(SEnumContext *,WDS_BLACKBOARD_ENUM *)
0x180018c61  test    eax, eax
0x180018c63  jz      short loc_180018C90
0x180018c65  mov     [rsp+0C8h+var_A8], 0; int
0x180018c6d  mov     r9, [rsp+0C8h+var_58+8]; struct WDS_DATA *
0x180018c72  mov     r8, [rsp+0C8h+var_58]; unsigned __int16 *
0x180018c77  mov     rdx, [rsp+0C8h+var_68+8]; unsigned __int16 *
0x180018c7c  mov     rcx, rdi; this
0x180018c7f  call    ?SetValue@CBlackboard@@QEAAHPEBG0PEBUWDS_DATA@@H@Z; CBlackboard::SetValue(ushort const *,ushort const *,WDS_DATA const *,int)
0x180018c84  test    eax, eax
0x180018c86  jnz     short loc_180018C8E
0x180018c88  lea     r14d, [rax+5]
0x180018c8c  jmp     short loc_180018C9B
0x180018c8e  jmp     short loc_180018C51
0x180018c90  mov     r15d, 1
0x180018c96  mov     [rsp+0C8h+var_80], r15d
0x180018c9b  test    rsi, rsi
0x180018c9e  jz      short loc_180018CB9
0x180018ca0  test    r12, r12
0x180018ca3  jz      short loc_180018CAD
0x180018ca5  mov     rdx, r12; struct SEnumContext *
0x180018ca8  call    ?EnumClose@CBlackboard@@QEAAHPEAUSEnumContext@@@Z; CBlackboard::EnumClose(SEnumContext *)
0x180018cad  lea     rcx, [rsi+80h]; volatile int *
0x180018cb4  call    ?ReleaseAccess@@YAXPECJ@Z; ReleaseAccess(long volatile *)
0x180018cb9  test    rdi, rdi
0x180018cbc  jz      short loc_180018CCA
0x180018cbe  lea     rcx, [rdi+80h]; volatile int *
0x180018cc5  call    ?ReleaseAccess@@YAXPECJ@Z; ReleaseAccess(long volatile *)
0x180018cca  test    r15d, r15d
0x180018ccd  jnz     short loc_180018CE2
0x180018ccf  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x180018cd6  mov     rax, [rcx]
0x180018cd9  mov     edx, r14d
0x180018cdc  mov     rax, [rax+8]
0x180018ce0  jmp     short loc_180018D15
0x180018ce2  cmp     [rsp+0C8h+arg_20], 0
0x180018cea  jz      short loc_180018D1A
0x180018cec  mov     r8, r13; struct _BLACKBOARD *
0x180018cef  mov     rdx, [rsp+0C8h+arg_0]; struct _BLACKBOARD *
0x180018cf7  call    ?Redirect@CBlackboardFactory@@QEAAHPEAU_BLACKBOARD@@0@Z; CBlackboardFactory::Redirect(_BLACKBOARD *,_BLACKBOARD *)
0x180018cfc  test    eax, eax
0x180018cfe  jnz     short loc_180018D1A
0x180018d00  xor     r15d, r15d
0x180018d03  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x180018d0a  mov     rdx, [rcx]
0x180018d0d  mov     rax, [rdx+8]
0x180018d11  lea     edx, [r15+8]
0x180018d15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d1a  mov     eax, r15d
0x180018d1d  jmp     short loc_180018D39
0x180018d1f  mov     edx, 6
0x180018d24  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x180018d2b  mov     rax, [rcx]
0x180018d2e  mov     rax, [rax+8]
0x180018d32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d37  xor     eax, eax
0x180018d39  add     rsp, 90h
0x180018d40  pop     r15
0x180018d42  pop     r14
0x180018d44  pop     r13
0x180018d46  pop     r12
0x180018d48  pop     rdi
0x180018d49  pop     rsi
0x180018d4a  pop     rbx
0x180018d4b  retn
0x180028fab  push    rbx
0x180028fad  push    rbp
0x180028fae  sub     rsp, 38h
0x180028fb2  mov     rbp, rdx
0x180028fb5  mov     rbx, [rbp+30h]
0x180028fb9  test    rbx, rbx
0x180028fbc  jz      short loc_180028FDA
0x180028fbe  mov     rdx, [rbp+38h]; struct SEnumContext *
0x180028fc2  test    rdx, rdx
0x180028fc5  jz      short loc_180028FCD
0x180028fc7  call    ?EnumClose@CBlackboard@@QEAAHPEAUSEnumContext@@@Z; CBlackboard::EnumClose(SEnumContext *)
0x180028fcc  nop
0x180028fcd  lea     rcx, [rbx+80h]; volatile int *
0x180028fd4  call    ?ReleaseAccess@@YAXPECJ@Z; ReleaseAccess(long volatile *)
0x180028fd9  nop
0x180028fda  mov     rcx, [rbp+40h]
0x180028fde  test    rcx, rcx
0x180028fe1  jz      short loc_180028FED
0x180028fe3  sub     rcx, 0FFFFFFFFFFFFFF80h; volatile int *
0x180028fe7  call    ?ReleaseAccess@@YAXPECJ@Z; ReleaseAccess(long volatile *)
0x180028fec  nop
0x180028fed  add     rsp, 38h
0x180028ff1  pop     rbp
0x180028ff2  pop     rbx
0x180028ff3  retn
```
