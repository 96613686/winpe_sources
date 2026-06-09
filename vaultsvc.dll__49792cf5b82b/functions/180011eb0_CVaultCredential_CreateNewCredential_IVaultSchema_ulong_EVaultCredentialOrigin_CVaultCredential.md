# CVaultCredential::CreateNewCredential(IVaultSchema *,ulong,EVaultCredentialOrigin,CVaultCredential * *)

- ea: `0x180011eb0`
- end: `0x1800121c8`
- name: `?CreateNewCredential@CVaultCredential@@SAKPEAUIVaultSchema@@KW4EVaultCredentialOrigin@@PEAPEAV1@@Z`
- size: `792`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180010520`
- `0x180031df0`

## callees

- `0x180006324`
- `0x180011eb0`
- `0x1800121d0`
- `0x180012210`
- `0x18003b7b0`
- `0x18003b7d8`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011f30`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011f30`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVaultCredential::CreateNewCredential(__int64 a1, unsigned int a2, int a3, char **a4)
{
  __int64 v6; // rdi
  bool v8; // cf
  unsigned int v9; // eax
  char *v10; // rax
  char *v11; // rbx
  char *v12; // r14
  char *v13; // r14
  int v14; // edi
  __int64 result; // rax
  unsigned int v16; // edi
  unsigned int v17; // eax
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  char *v20; // [rsp+60h] [rbp+8h]

  v6 = a2;
  if ( ((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1) & 1) != 0 )
    v8 = (unsigned int)v6 < 2;
  else
    v8 = (unsigned int)v6 < 3;
  if ( v8 )
    return 87;
  if ( (unsigned int)v6 > (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)a1 + 96LL))(a1) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 96LL))(a1);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_49114d8a939f3a3d6447d5db247a3e77_Traceguids, v17);
    }
    return 87;
  }
  v9 = (_DWORD)v6 << 6;
  if ( (unsigned __int64)(v6 << 6) > 0xFFFFFFFF )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      return 534;
    v19 = 34;
    goto LABEL_33;
  }
  if ( v9 + 224 < v9 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      return 534;
    v19 = 35;
LABEL_33:
    WPP_SF_(v18[2], v19, WPP_49114d8a939f3a3d6447d5db247a3e77_Traceguids);
    return 534;
  }
  v10 = (char *)LocalAlloc(0x40u, v9 + 224);
  v11 = v10;
  v20 = v10;
  if ( !v10 )
    return 14;
  try
  {
    v12 = v10 + 224;
    *(_QWORD *)v10 = &CVaultCredential::`vftable';
    *((_QWORD *)v10 + 1) = a1;
    *((_QWORD *)v10 + 2) = 0;
    *((_DWORD *)v10 + 14) = 0;
    *((_DWORD *)v10 + 36) = 0;
    *((_QWORD *)v10 + 20) = 0;
    *((_QWORD *)v10 + 21) = 0;
    std::_Tree<std::_Tmap_traits<enum VAULT_SCHEMA_ELEMENT_ID,CVaultCredElement *,std::less<enum VAULT_SCHEMA_ELEMENT_ID>,std::allocator<std::pair<enum VAULT_SCHEMA_ELEMENT_ID const,CVaultCredElement *>>,0>>::_Alloc_sentinel_and_proxy(v10 + 160);
    *((_DWORD *)v11 + 44) = 0;
    *((_DWORD *)v11 + 45) = -1;
    *((_DWORD *)v11 + 52) = 0;
    *((_QWORD *)v11 + 27) = 0;
    *((_QWORD *)v11 + 23) = 0;
    *((_QWORD *)v11 + 24) = 0;
    (***((void (__fastcall ****)(_QWORD))v11 + 1))(*((_QWORD *)v11 + 1));
    *(_QWORD *)v12 = &CVaultCredElement::`vftable';
    v12[56] = 0;
    *(_OWORD *)(v12 + 24) = 0;
    *(_OWORD *)(v12 + 40) = 0;
    *((_QWORD *)v11 + 4) = v12;
    *((_QWORD *)v12 + 8) = &CVaultCredElement::`vftable';
    v12[120] = 0;
    *(_OWORD *)(v12 + 88) = 0;
    *(_OWORD *)(v12 + 104) = 0;
    *((_QWORD *)v11 + 5) = v12 + 64;
    v13 = v12 + 128;
    v14 = v6 - 2;
    if ( v14 && ((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1) & 1) == 0 )
    {
      *(_QWORD *)v13 = &CVaultCredElement::`vftable';
      v13[56] = 0;
      *(_OWORD *)(v13 + 24) = 0;
      *(_OWORD *)(v13 + 40) = 0;
      *((_QWORD *)v11 + 3) = v13;
      v13 += 64;
      --v14;
    }
    if ( v14 )
    {
      *((_QWORD *)v11 + 19) = v13;
      *((_WORD *)v11 + 74) = v14;
      do
      {
        *(_QWORD *)v13 = &CVaultCredElement::`vftable';
        v13[56] = 0;
        *(_OWORD *)(v13 + 24) = 0;
        *(_OWORD *)(v13 + 40) = 0;
        v13 += 64;
        --v14;
      }
      while ( v14 );
    }
    else
    {
      *((_WORD *)v11 + 74) = 0;
    }
    *(_OWORD *)(v11 + 60) = 0;
    *(_OWORD *)(v11 + 76) = 0;
    *(_OWORD *)(v11 + 92) = 0;
    *(_OWORD *)(v11 + 108) = 0;
    *(_OWORD *)(v11 + 124) = 0;
    *((_WORD *)v11 + 70) = 0;
    *((_DWORD *)v11 + 51) = 1;
    if ( a3 || (v16 = CVaultCredential::InitializeCredential((CVaultCredential *)v11)) == 0 )
    {
      *a4 = v11;
      result = 0;
    }
    else
    {
      (*(void (__fastcall **)(char *, _QWORD))(*(_QWORD *)v11 + 16LL))(v11, 0);
      VaultFreeInternal(v11);
      result = v16;
    }
  }
  catch ( std::bad_alloc )
  {
    VaultFreeInternal(v20);
    return 14;
  }
  return result;
}

```

## disassembly

```asm
0x180011eb0  mov     [rsp+arg_8], rbx
0x180011eb5  mov     [rsp+arg_10], rsi
0x180011eba  push    rdi
0x180011ebb  push    r12
0x180011ebd  push    r13
0x180011ebf  push    r14
0x180011ec1  push    r15
0x180011ec3  sub     rsp, 30h
0x180011ec7  mov     r15, r9
0x180011eca  mov     r12d, r8d
0x180011ecd  mov     edi, edx
0x180011ecf  mov     rsi, rcx
0x180011ed2  mov     rax, [rcx]
0x180011ed5  mov     rax, [rax+20h]
0x180011ed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ede  test    al, 1
0x180011ee0  jnz     loc_180012069
0x180011ee6  cmp     edi, 3
0x180011ee9  jb      loc_1800120B1
0x180011eef  mov     rax, [rsi]
0x180011ef2  mov     rcx, rsi
0x180011ef5  mov     rax, [rax+60h]
0x180011ef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011efe  cmp     edi, eax
0x180011f00  ja      loc_18001209E
0x180011f06  mov     rax, rdi
0x180011f09  shl     rax, 6
0x180011f0d  mov     ecx, 0FFFFFFFFh
0x180011f12  cmp     rax, rcx
0x180011f15  ja      loc_180012190
0x180011f1b  lea     ecx, [rax+0E0h]
0x180011f21  cmp     ecx, eax
0x180011f23  jb      loc_1800120EE
0x180011f29  mov     edx, ecx; uBytes
0x180011f2b  mov     ecx, 40h ; '@'; uFlags
0x180011f30  call    cs:__imp_LocalAlloc
0x180011f36  mov     rbx, rax
0x180011f39  mov     [rsp+58h+arg_0], rax
0x180011f3e  test    rax, rax
0x180011f41  jz      loc_180012062
0x180011f47  mov     [rsp+58h+var_38], rax
0x180011f4c  lea     r14, [rax+0E0h]
0x180011f53  lea     rax, ??_7CVaultCredential@@6B@; const CVaultCredential::`vftable'
0x180011f5a  mov     [rbx], rax
0x180011f5d  mov     [rbx+8], rsi
0x180011f61  xor     r13d, r13d
0x180011f64  mov     [rbx+10h], r13
0x180011f68  mov     [rbx+38h], r13d
0x180011f6c  mov     [rbx+90h], r13d
0x180011f73  lea     rcx, [rbx+0A0h]
0x180011f7a  mov     [rcx], r13
0x180011f7d  mov     [rcx+8], r13
0x180011f81  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@W4VAULT_SCHEMA_ELEMENT_ID@@PEAVCVaultCredElement@@U?$less@W4VAULT_SCHEMA_ELEMENT_ID@@@std@@V?$allocator@U?$pair@$$CBW4VAULT_SCHEMA_ELEMENT_ID@@PEAVCVaultCredElement@@@std@@@4@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<VAULT_SCHEMA_ELEMENT_ID,CVaultCredElement *,std::less<VAULT_SCHEMA_ELEMENT_ID>,std::allocator<std::pair<VAULT_SCHEMA_ELEMENT_ID const,CVaultCredElement *>>,0>>::_Alloc_sentinel_and_proxy(void)
0x180011f86  nop
0x180011f87  mov     [rbx+0B0h], r13d
0x180011f8e  mov     dword ptr [rbx+0B4h], 0FFFFFFFFh
0x180011f98  mov     [rbx+0D0h], r13d
0x180011f9f  mov     [rbx+0D8h], r13
0x180011fa6  mov     [rbx+0B8h], r13
0x180011fad  mov     [rbx+0C0h], r13
0x180011fb4  mov     rcx, [rbx+8]
0x180011fb8  mov     rax, [rcx]
0x180011fbb  mov     rax, [rax]
0x180011fbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011fc3  lea     rcx, ??_7CVaultCredElement@@6B@; const CVaultCredElement::`vftable'
0x180011fca  mov     [r14], rcx
0x180011fcd  mov     [r14+38h], r13b
0x180011fd1  xorps   xmm0, xmm0
0x180011fd4  movups  xmmword ptr [r14+18h], xmm0
0x180011fd9  movups  xmmword ptr [r14+28h], xmm0
0x180011fde  mov     [rbx+20h], r14
0x180011fe2  lea     rax, [r14+40h]
0x180011fe6  mov     [rax], rcx
0x180011fe9  mov     [rax+38h], r13b
0x180011fed  movups  xmmword ptr [rax+18h], xmm0
0x180011ff1  movups  xmmword ptr [rax+28h], xmm0
0x180011ff5  mov     [rbx+28h], rax
0x180011ff9  lea     r14, [rax+40h]
0x180011ffd  add     edi, 0FFFFFFFEh
0x180012000  jnz     loc_180012119
0x180012006  test    edi, edi
0x180012008  jnz     loc_18001215B
0x18001200e  mov     [rbx+94h], r13w
0x180012016  xorps   xmm0, xmm0
0x180012019  xor     eax, eax
0x18001201b  movups  xmmword ptr [rbx+3Ch], xmm0
0x18001201f  movups  xmmword ptr [rbx+4Ch], xmm0
0x180012023  movups  xmmword ptr [rbx+5Ch], xmm0
0x180012027  movups  xmmword ptr [rbx+6Ch], xmm0
0x18001202b  movups  xmmword ptr [rbx+7Ch], xmm0
0x18001202f  mov     [rbx+8Ch], ax
0x180012036  mov     dword ptr [rbx+0CCh], 1
0x180012040  test    r12d, r12d
0x180012043  jz      short loc_180012071
0x180012045  mov     [r15], rbx
0x180012048  xor     eax, eax
0x18001204a  mov     rbx, [rsp+58h+arg_8]
0x18001204f  mov     rsi, [rsp+58h+arg_10]
0x180012054  add     rsp, 30h
0x180012058  pop     r15
0x18001205a  pop     r14
0x18001205c  pop     r13
0x18001205e  pop     r12
0x180012060  pop     rdi
0x180012061  retn
0x180012062  mov     eax, 0Eh
0x180012067  jmp     short loc_18001204A
0x180012069  cmp     edi, 2
0x18001206c  jmp     loc_180011EE9
0x180012071  mov     rcx, rbx; this
0x180012074  call    ?InitializeCredential@CVaultCredential@@QEAAKXZ; CVaultCredential::InitializeCredential(void)
0x180012079  mov     edi, eax
0x18001207b  test    eax, eax
0x18001207d  jz      short loc_180012045
0x18001207f  mov     rcx, [rbx]
0x180012082  mov     rax, [rcx+10h]
0x180012086  xor     edx, edx
0x180012088  mov     rcx, rbx
0x18001208b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012090  mov     rcx, rbx; hMem
0x180012093  call    ?VaultFreeInternal@@YAXPEAE@Z; VaultFreeInternal(uchar *)
0x180012098  mov     eax, edi
0x18001209a  jmp     short loc_18001204A
0x18001209c  jmp     short loc_180012062
0x18001209e  lea     rax, WPP_GLOBAL_Control
0x1800120a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800120ac  cmp     rcx, rax
0x1800120af  jnz     short loc_1800120B8
0x1800120b1  mov     eax, 57h ; 'W'
0x1800120b6  jmp     short loc_18001204A
0x1800120b8  test    byte ptr [rcx+1Ch], 2
0x1800120bc  jz      short loc_1800120B1
0x1800120be  mov     rax, [rsi]
0x1800120c1  mov     rcx, rsi
0x1800120c4  mov     rax, [rax+60h]
0x1800120c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120cd  mov     edx, 21h ; '!'
0x1800120d2  mov     r9d, eax
0x1800120d5  lea     r8, WPP_49114d8a939f3a3d6447d5db247a3e77_Traceguids
0x1800120dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800120e3  mov     rcx, [rcx+10h]
0x1800120e7  call    WPP_SF_d
0x1800120ec  jmp     short loc_1800120B1
0x1800120ee  lea     rax, WPP_GLOBAL_Control
0x1800120f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800120fc  cmp     rcx, rax
0x1800120ff  jz      loc_1800121BE
0x180012105  test    byte ptr [rcx+1Ch], 2
0x180012109  jz      loc_1800121BE
0x18001210f  mov     edx, 23h ; '#'
0x180012114  jmp     loc_1800121AE
0x180012119  mov     rax, [rsi]
0x18001211c  mov     rcx, rsi
0x18001211f  mov     rax, [rax+20h]
0x180012123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012128  lea     rcx, ??_7CVaultCredElement@@6B@; const CVaultCredElement::`vftable'
0x18001212f  test    al, 1
0x180012131  jnz     loc_180012006
0x180012137  mov     [r14], rcx
0x18001213a  mov     byte ptr [r14+38h], 0
0x18001213f  xorps   xmm0, xmm0
0x180012142  movups  xmmword ptr [r14+18h], xmm0
0x180012147  movups  xmmword ptr [r14+28h], xmm0
0x18001214c  mov     [rbx+18h], r14
0x180012150  add     r14, 40h ; '@'
0x180012154  dec     edi
0x180012156  jmp     loc_180012006
0x18001215b  mov     [rbx+98h], r14
0x180012162  mov     [rbx+94h], di
0x180012169  mov     eax, 0FFFFFFFFh
0x18001216e  mov     [r14], rcx
0x180012171  mov     byte ptr [r14+38h], 0
0x180012176  xorps   xmm0, xmm0
0x180012179  movups  xmmword ptr [r14+18h], xmm0
0x18001217e  movups  xmmword ptr [r14+28h], xmm0
0x180012183  lea     r14, [r14+40h]
0x180012187  add     edi, eax
0x180012189  jnz     short loc_18001216E
0x18001218b  jmp     loc_180012016
0x180012190  lea     rax, WPP_GLOBAL_Control
0x180012197  mov     rcx, cs:WPP_GLOBAL_Control
0x18001219e  cmp     rcx, rax
0x1800121a1  jz      short loc_1800121BE
0x1800121a3  test    byte ptr [rcx+1Ch], 2
0x1800121a7  jz      short loc_1800121BE
0x1800121a9  mov     edx, 22h ; '"'
0x1800121ae  lea     r8, WPP_49114d8a939f3a3d6447d5db247a3e77_Traceguids
0x1800121b5  mov     rcx, [rcx+10h]
0x1800121b9  call    WPP_SF_
0x1800121be  mov     eax, 216h
0x1800121c3  jmp     loc_18001204A
```
