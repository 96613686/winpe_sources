# FindDispatcherFromDescriptor

- ea: `0x14000d7c0`
- end: `0x14000da89`
- name: `FindDispatcherFromDescriptor`
- size: `713`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x14000cbf0`
- `0x14001a938`

## callees

- `0x14000d7c0`
- `0x14000da90`
- `0x14001ab4c`
- `0x14001b15c`
- `0x140040a70`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000d9ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d9ad`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000d91c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000d91c`

## pseudocode

```c
__int64 __fastcall FindDispatcherFromDescriptor(__int64 a1, __int64 a2)
{
  __int64 v2; // r8
  __m128i v4; // xmm6
  __m128i *v5; // rdi
  __m128i *v6; // rcx
  unsigned __int64 v7; // xmm0_8
  __int64 v8; // rdx
  int v10; // eax
  int v11; // ebx
  __m128i *PoolWithTag; // rax
  __m128i *v13; // rbx
  int v14; // r14d
  __m128i **v15; // rax
  __m128i v16; // [rsp+30h] [rbp-20h] BYREF
  __int64 v17; // [rsp+70h] [rbp+20h] BYREF
  __int64 v18; // [rsp+78h] [rbp+28h] BYREF

  v2 = *(unsigned __int8 *)(a2 + 2);
  v17 = 0;
  v18 = 0;
  if ( (_BYTE)v2 == 14 )
  {
    v4 = *(__m128i *)(a2 + 21);
    v16 = v4;
  }
  else
  {
    v16.m128i_i32[3] = -212161756;
    v16.m128i_i32[0] = v2 + 1882549696;
    *(__int64 *)((char *)v16.m128i_i64 + 4) = 0xA2280394434A2C1EuLL;
    v4 = v16;
  }
  v5 = (__m128i *)(a1 + 592);
  v6 = *(__m128i **)(a1 + 592);
  if ( v6 != v5 )
  {
    v7 = _mm_srli_si128(v4, 8).m128i_u64[0];
    while ( v6 != v5 )
    {
      v8 = v4.m128i_i64[0] - v6[1].m128i_i64[0];
      if ( v4.m128i_i64[0] == v6[1].m128i_i64[0] )
        v8 = v7 - v6[1].m128i_i64[1];
      if ( !v8 )
        return v6[2].m128i_i64[0];
      v6 = (__m128i *)v6->m128i_i64[0];
    }
  }
  v10 = UvcFmtCreateHandler(v2, &v16, v2, &v18);
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_092df6b9c3fc3deff23d72b76b446421_Traceguids, a1, v10);
    return 0;
  }
  v11 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v18)(v18, &IID_IUVCFormatPlugin, &v17);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_092df6b9c3fc3deff23d72b76b446421_Traceguids, a1, v11);
    return 0;
  }
  PoolWithTag = (__m128i *)ExAllocatePoolWithTag((POOL_TYPE)1536, 0x28u, 0x56425355u);
  v13 = PoolWithTag;
  if ( !ExPoolZeroingNativelySupported )
  {
    if ( PoolWithTag )
    {
      *PoolWithTag = 0;
      PoolWithTag[1] = 0;
      PoolWithTag[2].m128i_i64[0] = 0;
      goto LABEL_23;
    }
LABEL_29:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_092df6b9c3fc3deff23d72b76b446421_Traceguids, a1);
    return 0;
  }
  if ( !PoolWithTag )
    goto LABEL_29;
LABEL_23:
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 760) + 8LL))(*(_QWORD *)(a1 + 760));
  v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v17 + 24LL))(
          v17,
          *(_QWORD *)(a1 + 760),
          *(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL),
          *(unsigned int *)(a1 + 716));
  if ( v14 < 0 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    ExFreePoolWithTag(v13, 0x56425355u);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_092df6b9c3fc3deff23d72b76b446421_Traceguids, a1, v14);
    return 0;
  }
  v15 = (__m128i **)v5->m128i_i64[1];
  if ( *v15 != v5 )
    __fastfail(3u);
  v13->m128i_i64[0] = (__int64)v5;
  v13->m128i_i64[1] = (__int64)v15;
  *v15 = v13;
  v5->m128i_i64[1] = (__int64)v13;
  v13[1] = v4;
  v13[2].m128i_i64[0] = v17;
  return v17;
}

```

## disassembly

```asm
0x14000d7c0  mov     [rsp-18h+arg_10], rbx
0x14000d7c5  mov     [rsp-18h+arg_18], rsi
0x14000d7ca  push    rbp
0x14000d7cb  push    rdi
0x14000d7cc  push    r14
0x14000d7ce  mov     rbp, rsp
0x14000d7d1  sub     rsp, 50h
0x14000d7d5  movzx   r8d, byte ptr [rdx+2]
0x14000d7da  mov     rsi, rcx
0x14000d7dd  movaps  [rsp+50h+var_10], xmm6
0x14000d7e2  mov     [rbp+arg_0], 0
0x14000d7ea  mov     [rbp+arg_8], 0
0x14000d7f2  cmp     r8b, 0Eh
0x14000d7f6  jnz     short loc_14000D802
0x14000d7f8  movups  xmm6, xmmword ptr [rdx+15h]
0x14000d7fc  movups  [rbp+var_20], xmm6
0x14000d800  jmp     short loc_14000D826
0x14000d802  mov     eax, cs:dword_1400461CC
0x14000d808  movsd   xmm0, cs:qword_1400461C4
0x14000d810  mov     dword ptr [rbp+var_20+0Ch], eax
0x14000d813  lea     eax, [r8+70356DC0h]
0x14000d81a  mov     dword ptr [rbp+var_20], eax
0x14000d81d  movsd   qword ptr [rbp+var_20+4], xmm0
0x14000d822  movups  xmm6, [rbp+var_20]
0x14000d826  lea     rdi, [rcx+250h]
0x14000d82d  mov     rcx, [rdi]
0x14000d830  cmp     rcx, rdi
0x14000d833  jz      short loc_14000D86A
0x14000d835  movdqa  xmm0, xmm6
0x14000d839  psrldq  xmm0, 8
0x14000d83e  cmp     rcx, rdi
0x14000d841  jz      short loc_14000D86A
0x14000d843  movq    rdx, xmm6
0x14000d848  sub     rdx, [rcx+10h]
0x14000d84c  jnz     short loc_14000D857
0x14000d84e  movq    rdx, xmm0
0x14000d853  sub     rdx, [rcx+18h]
0x14000d857  test    rdx, rdx
0x14000d85a  jz      short loc_14000D861
0x14000d85c  mov     rcx, [rcx]
0x14000d85f  jmp     short loc_14000D83E
0x14000d861  mov     rax, [rcx+20h]
0x14000d865  jmp     loc_14000DA6E
0x14000d86a  lea     r9, [rbp+arg_8]
0x14000d86e  mov     cl, r8b
0x14000d871  lea     rdx, [rbp+var_20]
0x14000d875  call    UvcFmtCreateHandler
0x14000d87a  test    eax, eax
0x14000d87c  jns     short loc_14000D8AD
0x14000d87e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d885  lea     rdx, WPP_GLOBAL_Control
0x14000d88c  cmp     rcx, rdx
0x14000d88f  jz      loc_14000D9EF
0x14000d895  cmp     byte ptr [rcx+29h], 2
0x14000d899  jb      loc_14000D9EF
0x14000d89f  mov     edx, 0Ah
0x14000d8a4  mov     [rsp+50h+var_30], eax
0x14000d8a8  jmp     loc_14000D9DC
0x14000d8ad  mov     rcx, [rbp+arg_8]
0x14000d8b1  lea     r8, [rbp+arg_0]
0x14000d8b5  lea     rdx, IID_IUVCFormatPlugin
0x14000d8bc  mov     rax, [rcx]
0x14000d8bf  mov     rax, [rax]
0x14000d8c2  call    _guard_dispatch_icall
0x14000d8c7  mov     rcx, [rbp+arg_8]
0x14000d8cb  mov     ebx, eax
0x14000d8cd  mov     rdx, [rcx]
0x14000d8d0  mov     rax, [rdx+10h]
0x14000d8d4  call    _guard_dispatch_icall
0x14000d8d9  test    ebx, ebx
0x14000d8db  jns     short loc_14000D90C
0x14000d8dd  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d8e4  lea     rdx, WPP_GLOBAL_Control
0x14000d8eb  cmp     rcx, rdx
0x14000d8ee  jz      loc_14000D9EF
0x14000d8f4  cmp     byte ptr [rcx+29h], 2
0x14000d8f8  jb      loc_14000D9EF
0x14000d8fe  mov     edx, 0Bh
0x14000d903  mov     [rsp+50h+var_30], ebx
0x14000d907  jmp     loc_14000D9DC
0x14000d90c  mov     edx, 28h ; '('; NumberOfBytes
0x14000d911  mov     ecx, 600h; PoolType
0x14000d916  mov     r8d, 56425355h; Tag
0x14000d91c  call    cs:__imp_ExAllocatePoolWithTag
0x14000d923  nop     dword ptr [rax+rax+00h]
0x14000d928  cmp     cs:ExPoolZeroingNativelySupported, 0
0x14000d92f  mov     rbx, rax
0x14000d932  jnz     loc_14000D9F3
0x14000d938  test    rax, rax
0x14000d93b  jz      loc_14000D9FC
0x14000d941  xorps   xmm0, xmm0
0x14000d944  xor     eax, eax
0x14000d946  movups  xmmword ptr [rbx], xmm0
0x14000d949  movups  xmmword ptr [rbx+10h], xmm0
0x14000d94d  mov     [rbx+20h], rax
0x14000d951  mov     rcx, [rsi+2F8h]
0x14000d958  mov     rax, [rcx]
0x14000d95b  mov     rax, [rax+8]
0x14000d95f  call    _guard_dispatch_icall
0x14000d964  mov     rcx, [rbp+arg_0]
0x14000d968  mov     r8, [rsi+18h]
0x14000d96c  mov     r9d, [rsi+2CCh]
0x14000d973  mov     rdx, [rsi+2F8h]
0x14000d97a  mov     rax, [rcx]
0x14000d97d  mov     r8, [r8+8]
0x14000d981  mov     rax, [rax+18h]
0x14000d985  call    _guard_dispatch_icall
0x14000d98a  mov     r14d, eax
0x14000d98d  test    eax, eax
0x14000d98f  jns     loc_14000DA3F
0x14000d995  mov     rcx, [rbp+arg_0]
0x14000d999  mov     r8, [rcx]
0x14000d99c  mov     rax, [r8+10h]
0x14000d9a0  call    _guard_dispatch_icall
0x14000d9a5  mov     edx, 56425355h; Tag
0x14000d9aa  mov     rcx, rbx; P
0x14000d9ad  call    cs:__imp_ExFreePoolWithTag
0x14000d9b4  nop     dword ptr [rax+rax+00h]
0x14000d9b9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d9c0  lea     rdx, WPP_GLOBAL_Control
0x14000d9c7  cmp     rcx, rdx
0x14000d9ca  jz      short loc_14000D9EF
0x14000d9cc  cmp     byte ptr [rcx+29h], 2
0x14000d9d0  jb      short loc_14000D9EF
0x14000d9d2  mov     edx, 0Dh
0x14000d9d7  mov     [rsp+50h+var_30], r14d
0x14000d9dc  mov     rcx, [rcx+18h]
0x14000d9e0  lea     r8, WPP_092df6b9c3fc3deff23d72b76b446421_Traceguids
0x14000d9e7  mov     r9, rsi
0x14000d9ea  call    WPP_SF_qD
0x14000d9ef  xor     eax, eax
0x14000d9f1  jmp     short loc_14000DA6E
0x14000d9f3  test    rbx, rbx
0x14000d9f6  jnz     loc_14000D951
0x14000d9fc  mov     rcx, [rbp+arg_0]
0x14000da00  mov     rax, [rcx]
0x14000da03  mov     rax, [rax+10h]
0x14000da07  call    _guard_dispatch_icall
0x14000da0c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000da13  lea     rdx, WPP_GLOBAL_Control
0x14000da1a  cmp     rcx, rdx
0x14000da1d  jz      short loc_14000D9EF
0x14000da1f  cmp     byte ptr [rcx+29h], 2
0x14000da23  jb      short loc_14000D9EF
0x14000da25  mov     rcx, [rcx+18h]
0x14000da29  lea     r8, WPP_092df6b9c3fc3deff23d72b76b446421_Traceguids
0x14000da30  mov     edx, 0Ch
0x14000da35  mov     r9, rsi
0x14000da38  call    WPP_SF_q
0x14000da3d  jmp     short loc_14000D9EF
0x14000da3f  mov     rax, [rdi+8]
0x14000da43  cmp     [rax], rdi
0x14000da46  jz      short loc_14000DA4F
0x14000da48  mov     ecx, 3
0x14000da4d  int     29h; Win8: RtlFailFast(ecx)
0x14000da4f  mov     [rbx], rdi
0x14000da52  mov     [rbx+8], rax
0x14000da56  mov     [rax], rbx
0x14000da59  mov     [rdi+8], rbx
0x14000da5d  movdqu  xmmword ptr [rbx+10h], xmm6
0x14000da62  mov     rax, [rbp+arg_0]
0x14000da66  mov     [rbx+20h], rax
0x14000da6a  mov     rax, [rbp+arg_0]
0x14000da6e  movaps  xmm6, [rsp+50h+var_10]
0x14000da73  lea     r11, [rsp+50h+var_s0]
0x14000da78  mov     rbx, [r11+30h]
0x14000da7c  mov     rsi, [r11+38h]
0x14000da80  mov     rsp, r11
0x14000da83  pop     r14
0x14000da85  pop     rdi
0x14000da86  pop     rbp
0x14000da87  retn
```
