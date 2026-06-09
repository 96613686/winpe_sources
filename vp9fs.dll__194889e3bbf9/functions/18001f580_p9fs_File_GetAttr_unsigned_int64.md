# p9fs::File::GetAttr(unsigned __int64)

- ea: `0x18001f580`
- end: `0x18001f937`
- name: `?GetAttr@File@p9fs@@UEAA?AV?$BasicExpected@V?$tuple@_KUQid@p9fs@@UStatResult@2@@std@@J@util@@_K@Z`
- size: `951`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180022728`

## callees

- `0x180004120`
- `0x180004c80`
- `0x18001cd30`
- `0x18001d940`
- `0x18001f580`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001f5e7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001f5e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001f625`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001f625`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f903`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f903`
- `lxutil!LxUtilFsGetLxAttributes` at `0x18001f6f5`
- `lxutil!LxUtilFsGetLxAttributes` at `0x18001f6f5`
- `lxutil!LxUtilFsIsAppExecLink` at `0x18001f718`
- `lxutil!LxUtilFsIsAppExecLink` at `0x18001f718`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall p9fs::File::GetAttr(__int64 a1, __int64 a2, __int16 a3)
{
  RTL_SRWLOCK *v6; // r14
  __int128 v7; // xmm6
  _QWORD *v8; // rdx
  __int64 v9; // r15
  int LxAttributes; // eax
  HANDLE v11; // rcx
  bool v12; // cc
  _DWORD *v13; // r9
  char IsAppExecLink; // r14
  int v15; // eax
  __int64 v16; // rax
  __int64 v17; // r8
  __int64 v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rdx
  int v25; // eax
  __int64 v26; // r8
  int v27; // esi
  int v28; // eax
  __int64 v29; // rax
  __int128 v31; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v32; // [rsp+68h] [rbp-A0h]
  __int128 v33; // [rsp+78h] [rbp-90h]
  __int128 v34; // [rsp+88h] [rbp-80h]
  __int128 v35; // [rsp+98h] [rbp-70h]
  __int128 v36; // [rsp+A8h] [rbp-60h]
  __int64 v37; // [rsp+B8h] [rbp-50h]
  RTL_SRWLOCK *v38; // [rsp+C8h] [rbp-40h]
  char v39; // [rsp+D0h] [rbp-38h]
  HANDLE hObject; // [rsp+D8h] [rbp-30h]
  _OWORD v41[2]; // [rsp+E0h] [rbp-28h] BYREF
  _BYTE v42[16]; // [rsp+108h] [rbp+0h] BYREF
  __int64 v43; // [rsp+118h] [rbp+10h]
  int v44; // [rsp+120h] [rbp+18h]
  int v45; // [rsp+124h] [rbp+1Ch]
  int v46; // [rsp+128h] [rbp+20h]
  __int64 v47; // [rsp+130h] [rbp+28h]
  __int64 v48; // [rsp+138h] [rbp+30h]
  __int64 v49; // [rsp+140h] [rbp+38h]
  __int64 v50; // [rsp+148h] [rbp+40h]
  __int64 v51; // [rsp+150h] [rbp+48h]
  __int64 v52; // [rsp+158h] [rbp+50h]
  __int64 v53; // [rsp+160h] [rbp+58h]
  __int64 v54; // [rsp+168h] [rbp+60h]
  __int64 v55; // [rsp+170h] [rbp+68h]
  __int64 v56; // [rsp+178h] [rbp+70h]
  _BYTE v57[8]; // [rsp+198h] [rbp+90h] BYREF
  _DWORD v58[26]; // [rsp+1A0h] [rbp+98h] BYREF

  v39 = 1;
  hObject = (HANDLE)-1LL;
  v41[0] = 0;
  v41[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v41[0]) = 0;
  v6 = (RTL_SRWLOCK *)(a1 + 8);
  AcquireSRWLockShared((PSRWLOCK)(a1 + 8));
  v38 = v6;
  v7 = *(_OWORD *)(a1 + 120);
  v8 = (_QWORD *)(a1 + 16);
  if ( v41 != (_OWORD *)(a1 + 16) )
  {
    if ( *(_QWORD *)(a1 + 40) > 7u )
      v8 = (_QWORD *)*v8;
    std::wstring::_Assign<unsigned short>(v41, v8, *(_QWORD *)(a1 + 32));
  }
  v9 = *(_QWORD *)(a1 + 48);
  if ( v6 )
    ReleaseSRWLockShared(v6);
  (*(void (__fastcall **)(_QWORD, _BYTE *, _QWORD, _OWORD *, _QWORD, __int64, _DWORD))(**(_QWORD **)(*(_QWORD *)(a1 + 72) + 112LL)
                                                                                     + 24LL))(
    *(_QWORD *)(*(_QWORD *)(a1 + 72) + 112LL),
    v57,
    *(_QWORD *)(*(_QWORD *)(a1 + 72) + 24LL),
    v41,
    *(_QWORD *)(a1 + 72),
    v9,
    0);
  if ( !v57[0] )
  {
    LxAttributes = v58[0];
LABEL_9:
    *(_BYTE *)a2 = 0;
    *(_DWORD *)(a2 + 8) = LxAttributes;
    std::wstring::~wstring(v41);
    if ( !v39 )
      return a2;
    v11 = hObject;
    v12 = (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
    goto LABEL_52;
  }
  memset_0(v42, 0, 0x90u);
  v13 = *(_DWORD **)(a1 + 72);
  LxAttributes = LxUtilFsGetLxAttributes(
                   v13 + 8,
                   v58,
                   1,
                   (unsigned int)v13[27],
                   v13[22],
                   v13[23],
                   v13[24],
                   v13[25],
                   v13[26],
                   v42);
  if ( LxAttributes )
    goto LABEL_9;
  *(_DWORD *)(a1 + 136) = v44;
  IsAppExecLink = LxUtilFsIsAppExecLink(v58[14], v58[15]);
  *(_BYTE *)(a1 + 113) = IsAppExecLink != 0;
  memset_0(&v31, 0, 0x68u);
  v15 = v31;
  if ( (a3 & 1) != 0 )
    v15 = v44;
  LODWORD(v31) = v15;
  v16 = v32;
  if ( (a3 & 2) != 0 )
    v16 = v43;
  *(_QWORD *)&v32 = v16;
  v17 = ((a3 & 1) + 256LL) | 2;
  if ( (a3 & 2) == 0 )
    v17 = (a3 & 1) + 256LL;
  v18 = *((_QWORD *)&v32 + 1);
  if ( (a3 & 0x10) != 0 )
    v18 = v47;
  *((_QWORD *)&v32 + 1) = v18;
  v19 = v17 | 0x10;
  if ( (a3 & 0x10) == 0 )
    v19 = v17;
  if ( (a3 & 0x200) != 0 )
  {
    v20 = v48;
    if ( IsAppExecLink )
      v20 = 2;
    *(_QWORD *)&v33 = v20;
    v19 |= 0x200uLL;
  }
  if ( (a3 & 0x400) != 0 )
  {
    *((_QWORD *)&v33 + 1) = v49;
    *(_QWORD *)&v34 = v50;
  }
  v21 = v19 | 0x400;
  if ( (a3 & 0x400) == 0 )
    v21 = v19;
  if ( (a3 & 0x20) != 0 )
  {
    *((_QWORD *)&v34 + 1) = v51;
    *(_QWORD *)&v35 = v52;
  }
  v22 = v21 | 0x20;
  if ( (a3 & 0x20) == 0 )
    v22 = v21;
  if ( (a3 & 0x40) != 0 )
  {
    *((_QWORD *)&v35 + 1) = v53;
    *(_QWORD *)&v36 = v54;
  }
  v23 = v22 | 0x40;
  if ( (a3 & 0x40) == 0 )
    v23 = v22;
  if ( (a3 & 0x80) != 0 )
  {
    *((_QWORD *)&v36 + 1) = v55;
    v37 = v56;
  }
  v24 = v23 | 0x80;
  if ( (a3 & 0x80) == 0 )
    v24 = v23;
  v25 = DWORD1(v31);
  if ( (a3 & 4) != 0 )
    v25 = v45;
  DWORD1(v31) = v25;
  v26 = v24 | 4;
  if ( (a3 & 4) == 0 )
    v26 = v24;
  v27 = a3 & 8;
  v28 = DWORD2(v31);
  if ( v27 )
    v28 = v46;
  DWORD2(v31) = v28;
  *(_BYTE *)a2 = 1;
  *(_OWORD *)(a2 + 8) = v31;
  *(_OWORD *)(a2 + 24) = v32;
  *(_OWORD *)(a2 + 40) = v33;
  *(_OWORD *)(a2 + 56) = v34;
  *(_OWORD *)(a2 + 72) = v35;
  *(_OWORD *)(a2 + 88) = v36;
  *(_QWORD *)(a2 + 104) = v37;
  *(_OWORD *)(a2 + 112) = v7;
  v29 = v26 | 8;
  if ( !v27 )
    v29 = v26;
  *(_QWORD *)(a2 + 128) = v29;
  std::wstring::~wstring(v41);
  if ( v39 )
  {
    v11 = hObject;
    v12 = (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
LABEL_52:
    if ( v12 )
      CloseHandle(v11);
  }
  return a2;
}

```

## disassembly

```asm
0x18001f580  mov     rax, rsp
0x18001f583  mov     [rax+18h], rbx
0x18001f587  push    rbp
0x18001f588  push    rsi
0x18001f589  push    rdi
0x18001f58a  push    r14
0x18001f58c  push    r15
0x18001f58e  lea     rbp, [rax-148h]
0x18001f595  sub     rsp, 220h
0x18001f59c  movaps  xmmword ptr [rax-38h], xmm6
0x18001f5a0  mov     rax, cs:__security_cookie
0x18001f5a7  xor     rax, rsp
0x18001f5aa  mov     [rbp+140h+var_40], rax
0x18001f5b1  mov     rsi, r8
0x18001f5b4  mov     rbx, rdx
0x18001f5b7  mov     rdi, rcx
0x18001f5ba  mov     [rbp+140h+var_178], 1
0x18001f5be  mov     [rbp+140h+hObject], 0FFFFFFFFFFFFFFFFh
0x18001f5c6  xorps   xmm0, xmm0
0x18001f5c9  movups  [rbp+140h+var_168], xmm0
0x18001f5cd  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001f5d5  movdqu  [rbp+140h+var_158], xmm1
0x18001f5da  xor     eax, eax
0x18001f5dc  mov     word ptr [rbp+140h+var_168], ax
0x18001f5e0  lea     r14, [rcx+8]
0x18001f5e4  mov     rcx, r14; SRWLock
0x18001f5e7  call    cs:__imp_AcquireSRWLockShared
0x18001f5ed  mov     [rbp+140h+var_180], r14
0x18001f5f1  movups  xmm6, xmmword ptr [rdi+78h]
0x18001f5f5  lea     rdx, [rdi+10h]
0x18001f5f9  lea     rax, [rbp+140h+var_168]
0x18001f5fd  cmp     rax, rdx
0x18001f600  jz      short loc_18001F619
0x18001f602  mov     r8, [rdx+10h]
0x18001f606  cmp     qword ptr [rdx+18h], 7
0x18001f60b  jbe     short loc_18001F610
0x18001f60d  mov     rdx, [rdx]
0x18001f610  lea     rcx, [rbp+140h+var_168]
0x18001f614  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18001f619  mov     r15, [rdi+30h]
0x18001f61d  test    r14, r14
0x18001f620  jz      short loc_18001F62B
0x18001f622  mov     rcx, r14; SRWLock
0x18001f625  call    cs:__imp_ReleaseSRWLockShared
0x18001f62b  mov     r8, [rdi+48h]
0x18001f62f  mov     rcx, [r8+70h]
0x18001f633  mov     rax, [rcx]
0x18001f636  mov     [rsp+240h+var_210], 0
0x18001f63e  mov     qword ptr [rsp+240h+var_218], r15
0x18001f643  mov     [rsp+240h+var_220], r8
0x18001f648  lea     r9, [rbp+140h+var_168]
0x18001f64c  mov     r8, [r8+18h]
0x18001f650  lea     rdx, [rbp+140h+var_B0]
0x18001f657  mov     rax, [rax+18h]
0x18001f65b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f660  cmp     [rbp+140h+var_B0], 0
0x18001f667  jnz     short loc_18001F69A
0x18001f669  mov     eax, [rbp+140h+var_A8]
0x18001f66f  mov     byte ptr [rbx], 0
0x18001f672  mov     [rbx+8], eax
0x18001f675  lea     rcx, [rbp+140h+var_168]
0x18001f679  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001f67e  nop
0x18001f67f  cmp     [rbp+140h+var_178], 0
0x18001f683  jz      loc_18001F909
0x18001f689  mov     rcx, [rbp+140h+hObject]
0x18001f68d  lea     rax, [rcx-1]
0x18001f691  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001f695  jmp     loc_18001F901
0x18001f69a  xor     edx, edx; Val
0x18001f69c  mov     r8d, 90h; Size
0x18001f6a2  lea     rcx, [rbp+140h+var_140]; void *
0x18001f6a6  call    memset_0
0x18001f6ab  mov     r9, [rdi+48h]
0x18001f6af  lea     rcx, [r9+20h]
0x18001f6b3  lea     rax, [rbp+140h+var_140]
0x18001f6b7  mov     qword ptr [rsp+240h+var_1F8], rax
0x18001f6bc  mov     eax, [r9+68h]
0x18001f6c0  mov     dword ptr [rsp+240h+var_200], eax
0x18001f6c4  mov     eax, [r9+64h]
0x18001f6c8  mov     [rsp+240h+var_208], eax
0x18001f6cc  mov     eax, [r9+60h]
0x18001f6d0  mov     [rsp+240h+var_210], eax
0x18001f6d4  mov     eax, [r9+5Ch]
0x18001f6d8  mov     [rsp+240h+var_218], eax
0x18001f6dc  mov     eax, [r9+58h]
0x18001f6e0  mov     dword ptr [rsp+240h+var_220], eax
0x18001f6e4  mov     r9d, [r9+6Ch]
0x18001f6e8  mov     r8d, 1
0x18001f6ee  lea     rdx, [rbp+140h+var_A8]
0x18001f6f5  call    cs:__imp_LxUtilFsGetLxAttributes
0x18001f6fb  test    eax, eax
0x18001f6fd  jnz     loc_18001F66F
0x18001f703  mov     eax, [rbp+140h+var_128]
0x18001f706  mov     [rdi+88h], eax
0x18001f70c  mov     edx, [rbp+140h+var_6C]
0x18001f712  mov     ecx, [rbp+140h+var_70]
0x18001f718  call    cs:__imp_LxUtilFsIsAppExecLink
0x18001f71e  mov     r14b, al
0x18001f721  test    al, al
0x18001f723  setnz   al
0x18001f726  mov     [rdi+71h], al
0x18001f729  xor     edx, edx; Val
0x18001f72b  lea     r8d, [rdx+68h]; Size
0x18001f72f  lea     rcx, [rsp+240h+var_1F8+8]; void *
0x18001f734  call    memset_0
0x18001f739  mov     rdx, rsi
0x18001f73c  and     edx, 1
0x18001f73f  mov     eax, dword ptr [rsp+240h+var_1F8+8]
0x18001f743  cmovnz  eax, [rbp+140h+var_128]
0x18001f747  mov     dword ptr [rsp+240h+var_1F8+8], eax
0x18001f74b  add     rdx, 100h
0x18001f752  mov     r9d, 2
0x18001f758  test    r9, rsi
0x18001f75b  mov     rax, qword ptr [rsp+240h+var_1E8+8]
0x18001f760  cmovnz  rax, [rbp+140h+var_130]
0x18001f765  mov     qword ptr [rsp+240h+var_1E8+8], rax
0x18001f76a  mov     r8, rdx
0x18001f76d  or      r8, r9
0x18001f770  test    r9, rsi
0x18001f773  cmovz   r8, rdx
0x18001f777  mov     rcx, rsi
0x18001f77a  and     ecx, 10h
0x18001f77d  mov     rax, qword ptr [rsp+240h+var_1D8]
0x18001f782  cmovnz  rax, [rbp+140h+var_118]
0x18001f787  mov     qword ptr [rsp+240h+var_1D8], rax
0x18001f78c  mov     rdx, r8
0x18001f78f  or      rdx, 10h
0x18001f793  test    rcx, rcx
0x18001f796  cmovz   rdx, r8
0x18001f79a  mov     ecx, 200h
0x18001f79f  test    rcx, rsi
0x18001f7a2  jz      short loc_18001F7B7
0x18001f7a4  mov     rax, [rbp+140h+var_110]
0x18001f7a8  test    r14b, r14b
0x18001f7ab  cmovnz  rax, r9
0x18001f7af  mov     qword ptr [rsp+240h+var_1D8+8], rax
0x18001f7b4  or      rdx, rcx
0x18001f7b7  mov     r8, rsi
0x18001f7ba  mov     r9d, 400h
0x18001f7c0  and     r8, r9
0x18001f7c3  jz      short loc_18001F7D6
0x18001f7c5  mov     rax, [rbp+140h+var_108]
0x18001f7c9  mov     [rsp+240h+var_1C8], rax
0x18001f7ce  mov     rax, [rbp+140h+var_100]
0x18001f7d2  mov     qword ptr [rbp+140h+var_1C0], rax
0x18001f7d6  mov     rcx, rdx
0x18001f7d9  or      rcx, r9
0x18001f7dc  test    r8, r8
0x18001f7df  cmovz   rcx, rdx
0x18001f7e3  mov     r8, rsi
0x18001f7e6  and     r8d, 20h
0x18001f7ea  jz      short loc_18001F7FC
0x18001f7ec  mov     rax, [rbp+140h+var_F8]
0x18001f7f0  mov     qword ptr [rbp+140h+var_1C0+8], rax
0x18001f7f4  mov     rax, [rbp+140h+var_F0]
0x18001f7f8  mov     qword ptr [rbp+140h+var_1B0], rax
0x18001f7fc  mov     rdx, rcx
0x18001f7ff  or      rdx, 20h
0x18001f803  test    r8, r8
0x18001f806  cmovz   rdx, rcx
0x18001f80a  mov     r8, rsi
0x18001f80d  and     r8d, 40h
0x18001f811  jz      short loc_18001F823
0x18001f813  mov     rax, [rbp+140h+var_E8]
0x18001f817  mov     qword ptr [rbp+140h+var_1B0+8], rax
0x18001f81b  mov     rax, [rbp+140h+var_E0]
0x18001f81f  mov     qword ptr [rbp+140h+var_1A0], rax
0x18001f823  mov     rcx, rdx
0x18001f826  or      rcx, 40h
0x18001f82a  test    r8, r8
0x18001f82d  cmovz   rcx, rdx
0x18001f831  mov     r8, rsi
0x18001f834  mov     r9d, 80h
0x18001f83a  and     r8, r9
0x18001f83d  jz      short loc_18001F84F
0x18001f83f  mov     rax, [rbp+140h+var_D8]
0x18001f843  mov     qword ptr [rbp+140h+var_1A0+8], rax
0x18001f847  mov     rax, [rbp+140h+var_D0]
0x18001f84b  mov     [rbp+140h+var_190], rax
0x18001f84f  mov     rdx, rcx
0x18001f852  or      rdx, r9
0x18001f855  test    r8, r8
0x18001f858  cmovz   rdx, rcx
0x18001f85c  mov     rcx, rsi
0x18001f85f  and     ecx, 4
0x18001f862  mov     eax, dword ptr [rsp+240h+var_1F8+0Ch]
0x18001f866  cmovnz  eax, [rbp+140h+var_124]
0x18001f86a  mov     dword ptr [rsp+240h+var_1F8+0Ch], eax
0x18001f86e  mov     r8, rdx
0x18001f871  or      r8, 4
0x18001f875  test    rcx, rcx
0x18001f878  cmovz   r8, rdx
0x18001f87c  and     esi, 8
0x18001f87f  mov     eax, dword ptr [rsp+240h+var_1E8]
0x18001f883  cmovnz  eax, [rbp+140h+var_120]
0x18001f887  mov     dword ptr [rsp+240h+var_1E8], eax
0x18001f88b  mov     byte ptr [rbx], 1
0x18001f88e  movaps  xmm0, [rsp+240h+var_1F8+8]
0x18001f893  movups  xmmword ptr [rbx+8], xmm0
0x18001f897  movaps  xmm1, [rsp+240h+var_1E8+8]
0x18001f89c  movups  xmmword ptr [rbx+18h], xmm1
0x18001f8a0  movaps  xmm0, [rsp+240h+var_1D8+8]
0x18001f8a5  movups  xmmword ptr [rbx+28h], xmm0
0x18001f8a9  movaps  xmm1, [rbp+140h+var_1C0]
0x18001f8ad  movups  xmmword ptr [rbx+38h], xmm1
0x18001f8b1  movaps  xmm0, [rbp+140h+var_1B0]
0x18001f8b5  movups  xmmword ptr [rbx+48h], xmm0
0x18001f8b9  movaps  xmm1, [rbp+140h+var_1A0]
0x18001f8bd  movups  xmmword ptr [rbx+58h], xmm1
0x18001f8c1  movsd   xmm0, [rbp+140h+var_190]
0x18001f8c6  movsd   qword ptr [rbx+68h], xmm0
0x18001f8cb  movdqu  xmmword ptr [rbx+70h], xmm6
0x18001f8d0  mov     rax, r8
0x18001f8d3  or      rax, 8
0x18001f8d7  test    rsi, rsi
0x18001f8da  cmovz   rax, r8
0x18001f8de  mov     [rbx+80h], rax
0x18001f8e5  lea     rcx, [rbp+140h+var_168]
0x18001f8e9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001f8ee  nop
0x18001f8ef  cmp     [rbp+140h+var_178], 0
0x18001f8f3  jz      short loc_18001F909
0x18001f8f5  mov     rcx, [rbp+140h+hObject]; hObject
0x18001f8f9  lea     rdx, [rcx-1]
0x18001f8fd  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001f901  ja      short loc_18001F909
0x18001f903  call    cs:__imp_CloseHandle
0x18001f909  mov     rax, rbx
0x18001f90c  mov     rcx, [rbp+140h+var_40]
0x18001f913  xor     rcx, rsp; StackCookie
0x18001f916  call    __security_check_cookie
0x18001f91b  lea     r11, [rsp+240h+var_20]
0x18001f923  mov     rbx, [r11+40h]
0x18001f927  movaps  xmm6, xmmword ptr [r11-10h]
0x18001f92c  mov     rsp, r11
0x18001f92f  pop     r15
0x18001f931  pop     r14
0x18001f933  pop     rdi
0x18001f934  pop     rsi
0x18001f935  pop     rbp
0x18001f936  retn
```
