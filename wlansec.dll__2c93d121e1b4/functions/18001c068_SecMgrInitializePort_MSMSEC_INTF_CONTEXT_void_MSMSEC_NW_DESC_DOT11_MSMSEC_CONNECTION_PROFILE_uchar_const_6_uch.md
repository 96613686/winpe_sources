# SecMgrInitializePort(MSMSEC_INTF_CONTEXT *,void *,MSMSEC_NW_DESC *,DOT11_MSMSEC_CONNECTION_PROFILE *,uchar const (&)[6],uchar const (&)[6],_DOT11_AUTH_ALGORITHM,MSMSEC_PORT_CONTEXT *)

- ea: `0x18001c068`
- end: `0x18001c59b`
- name: `?SecMgrInitializePort@@YAKPEAUMSMSEC_INTF_CONTEXT@@PEAXPEAUMSMSEC_NW_DESC@@PEAUDOT11_MSMSEC_CONNECTION_PROFILE@@AEAY05$$CBE4W4_DOT11_AUTH_ALGORITHM@@PEAUMSMSEC_PORT_CONTEXT@@@Z`
- size: `1331`
- prototype: `unsigned int __fastcall(struct MSMSEC_INTF_CONTEXT *, void *, struct MSMSEC_NW_DESC *, struct DOT11_MSMSEC_CONNECTION_PROFILE *, const unsigned __int8 (*)[6], const unsigned __int8 (*)[6], enum _DOT11_AUTH_ALGORITHM, struct MSMSEC_PORT_CONTEXT *)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x1800293ac`

## callees

- `0x1800065a4`
- `0x18000892c`
- `0x180008998`
- `0x18001c068`
- `0x18001c5a4`
- `0x18001c968`
- `0x18001ca50`
- `0x18001cadc`
- `0x18002091c`
- `0x180041e44`
- `0x18004456c`
- `0x180057c50`
- `0x180057d3c`

## import_xrefs

- `MobileNetworking!CreateReadWriteLock` at `0x18001c1b4`
- `MobileNetworking!CreateReadWriteLock` at `0x18001c1b4`

## pseudocode

```c
__int64 __fastcall SecMgrInitializePort(
        struct MSMSEC_INTF_CONTEXT *a1,
        void *a2,
        struct MSMSEC_NW_DESC *a3,
        struct DOT11_MSMSEC_CONNECTION_PROFILE *a4,
        const unsigned __int8 (*a5)[6],
        const unsigned __int8 (*a6)[6],
        enum _DOT11_AUTH_ALGORITHM a7,
        struct MSMSEC_PORT_CONTEXT *a8)
{
  int v8; // r13d
  int v12; // ebx
  int v13; // r12d
  _OWORD *v14; // rcx
  __int64 v15; // rdx
  _OWORD *v16; // rax
  __int128 v17; // xmm1
  unsigned int v18; // eax
  unsigned int v19; // ebx
  int v20; // esi
  __int64 v22; // rcx
  __int64 v23; // rax
  unsigned int v24; // eax
  struct MSMSEC_HOST_DESC *v25; // rdx
  unsigned int v26; // eax
  _QWORD *v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // r9
  unsigned int v30; // eax
  int v31; // [rsp+30h] [rbp-48h]
  int v33; // [rsp+90h] [rbp+18h]

  v8 = 0;
  v31 = 0;
  v33 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 55, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids);
  v12 = *((_DWORD *)a3 + 9);
  v13 = *((_DWORD *)a1 + 694);
  memset_0(a8, 0, 0x7F0u);
  ScrubAndFreeKeyMaterial((char *)a8 + 1176, (char *)a8 + 1168);
  *((_QWORD *)a8 + 1) = a8;
  v14 = (_OWORD *)((char *)a1 + 2104);
  *(_QWORD *)a8 = a8;
  v15 = 2;
  *((_QWORD *)a8 + 3) = a1;
  *((_QWORD *)a8 + 4) = *((_QWORD *)a1 + 3);
  v16 = (_OWORD *)((char *)a8 + 40);
  do
  {
    *v16 = *v14;
    v16[1] = v14[1];
    v16[2] = v14[2];
    v16[3] = v14[3];
    v16[4] = v14[4];
    v16[5] = v14[5];
    v16[6] = v14[6];
    v17 = v14[7];
    v14 += 8;
    v16[7] = v17;
    v16 += 8;
    --v15;
  }
  while ( v15 );
  *((_DWORD *)a8 + 74) = *(_DWORD *)a5;
  *((_WORD *)a8 + 150) = *(_WORD *)&(*a5)[4];
  *(_DWORD *)((char *)a8 + 302) = *(_DWORD *)a6;
  *((_WORD *)a8 + 153) = *(_WORD *)&(*a6)[4];
  *((_DWORD *)a8 + 77) = v12;
  *((_DWORD *)a8 + 78) = _InterlockedIncrement(&dword_1800AEFB8);
  v18 = CreateReadWriteLock((char *)a8 + 320);
  v19 = v18;
  if ( v18 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 56, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids, v18);
    v20 = 0;
    goto LABEL_7;
  }
  *((_DWORD *)a8 + 109) = 1;
  *((_DWORD *)a8 + 108) = 0;
  v8 = 1;
  *((_DWORD *)a8 + 110) = 1;
  v22 = 0;
  *((_QWORD *)a8 + 57) = (char *)a8 + 448;
  *((_QWORD *)a8 + 56) = (char *)a8 + 448;
  *((_QWORD *)a8 + 59) = (char *)a8 + 464;
  *((_QWORD *)a8 + 58) = (char *)a8 + 464;
  *((_DWORD *)a8 + 121) = 0;
  *((_QWORD *)a8 + 61) = 0;
  *((_QWORD *)a8 + 62) = 1;
  do
  {
    *((_DWORD *)a8 + 4 * v22 + 128) = 0;
    v23 = 2 * v22++;
    *((_QWORD *)a8 + v23 + 65) = 0;
  }
  while ( v22 != 8 );
  *((_DWORD *)a8 + 160) = 0;
  *((_QWORD *)a8 + 81) = 0;
  memset_0((char *)a8 + 672, 0, 0x64u);
  *((_DWORD *)a8 + 506) = 0;
  switch ( a7 )
  {
    case 1:
      if ( *((_DWORD *)a4 + 8) )
        goto LABEL_20;
      goto LABEL_21;
    case 3:
      goto LABEL_20;
    case 4:
LABEL_43:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 59, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids);
      if ( v13 == 32 )
        v30 = SecMgrStorePSKFromPeerKeyList(a8, a3, (struct _LIST_ENTRY *)a1 + 169);
      else
        v30 = SecMgrStorePSKFromProfile(a8, a3, a4);
      v19 = v30;
      if ( v30 )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          goto LABEL_42;
        v28 = 60;
        v29 = v30;
        goto LABEL_41;
      }
LABEL_53:
      *((_DWORD *)a8 + 126) = 0;
      goto LABEL_21;
    case 6:
LABEL_20:
      *((_DWORD *)a8 + 126) = 1;
      goto LABEL_21;
    case 7:
      goto LABEL_43;
    case 8:
      goto LABEL_20;
    case 9:
      if ( v13 != 32 )
        goto LABEL_21;
      v24 = SecMgrStoreSaePmkFromPendingList(a8, a6, a1);
      v19 = v24;
      if ( v24 )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          goto LABEL_42;
        v28 = 57;
LABEL_40:
        v29 = v24;
LABEL_41:
        WPP_SF_d(v27[7], v28, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids, v29);
LABEL_42:
        v20 = 0;
        goto LABEL_7;
      }
      goto LABEL_53;
    case 11:
      goto LABEL_20;
  }
  *((_DWORD *)a8 + 126) = 0;
LABEL_21:
  v24 = AuthMgrInitialize(a8);
  v19 = v24;
  if ( v24 )
  {
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_42;
    v28 = 61;
    goto LABEL_40;
  }
  v31 = 1;
  v24 = KeyMgrInitialize(a8, a2);
  v19 = v24;
  if ( v24 )
  {
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_42;
    v28 = 62;
    goto LABEL_40;
  }
  v33 = 1;
  v24 = KeyCacheInitialize((struct MSMSEC_PORT_CONTEXT *)((char *)a8 + 776));
  v19 = v24;
  if ( v24 )
  {
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_42;
    v28 = 63;
    goto LABEL_40;
  }
  v26 = WpsAuthMgrInitialize(a8, v25);
  v19 = v26;
  if ( !v26 )
    goto LABEL_8;
  v20 = 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 64, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids, v26);
LABEL_7:
  SecMgrDeinitializePortHelper(a8, v8, v31, v33, v20, 0);
LABEL_8:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 65, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids, v19);
  return v19;
}

```

## disassembly

```asm
0x18001c068  mov     [rsp+arg_18], rbx
0x18001c06d  mov     [rsp+arg_8], rdx
0x18001c072  push    rbp
0x18001c073  push    rsi
0x18001c074  push    rdi
0x18001c075  push    r12
0x18001c077  push    r13
0x18001c079  push    r14
0x18001c07b  push    r15
0x18001c07d  sub     rsp, 40h
0x18001c081  xor     r13d, r13d
0x18001c084  mov     r14, r9
0x18001c087  mov     [rsp+78h+var_48], r13d
0x18001c08c  mov     rbp, r8
0x18001c08f  mov     [rsp+78h+arg_10], r13d
0x18001c097  mov     rsi, rcx
0x18001c09a  mov     [rsp+78h+arg_0], r13d
0x18001c0a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c0a9  lea     rax, WPP_GLOBAL_Control
0x18001c0b0  cmp     rcx, rax
0x18001c0b3  jnz     loc_18001C3D9
0x18001c0b9  mov     rdi, [rsp+78h+arg_38]
0x18001c0c1  xor     edx, edx; Val
0x18001c0c3  mov     ebx, [rbp+24h]
0x18001c0c6  mov     rcx, rdi; void *
0x18001c0c9  mov     r12d, [rsi+0AD8h]
0x18001c0d0  mov     r8d, 7F0h; Size
0x18001c0d6  call    memset_0
0x18001c0db  lea     rdx, [rdi+490h]
0x18001c0e2  lea     rcx, [rdx+8]
0x18001c0e6  call    ScrubAndFreeKeyMaterial
0x18001c0eb  mov     [rdi+8], rdi
0x18001c0ef  lea     rcx, [rsi+838h]
0x18001c0f6  mov     [rdi], rdi
0x18001c0f9  mov     edx, 2
0x18001c0fe  mov     [rdi+18h], rsi
0x18001c102  mov     rax, [rsi+18h]
0x18001c106  mov     [rdi+20h], rax
0x18001c10a  lea     rax, [rdi+28h]
0x18001c10e  lea     r8d, [rdx+7Eh]
0x18001c112  movups  xmm0, xmmword ptr [rcx]
0x18001c115  movups  xmmword ptr [rax], xmm0
0x18001c118  movups  xmm1, xmmword ptr [rcx+10h]
0x18001c11c  movups  xmmword ptr [rax+10h], xmm1
0x18001c120  movups  xmm0, xmmword ptr [rcx+20h]
0x18001c124  movups  xmmword ptr [rax+20h], xmm0
0x18001c128  movups  xmm1, xmmword ptr [rcx+30h]
0x18001c12c  movups  xmmword ptr [rax+30h], xmm1
0x18001c130  movups  xmm0, xmmword ptr [rcx+40h]
0x18001c134  movups  xmmword ptr [rax+40h], xmm0
0x18001c138  movups  xmm1, xmmword ptr [rcx+50h]
0x18001c13c  movups  xmmword ptr [rax+50h], xmm1
0x18001c140  movups  xmm0, xmmword ptr [rcx+60h]
0x18001c144  movups  xmmword ptr [rax+60h], xmm0
0x18001c148  movups  xmm1, xmmword ptr [rcx+70h]
0x18001c14c  add     rcx, r8
0x18001c14f  movups  xmmword ptr [rax+70h], xmm1
0x18001c153  add     rax, r8
0x18001c156  sub     rdx, 1
0x18001c15a  jnz     short loc_18001C112
0x18001c15c  mov     rcx, [rsp+78h+arg_20]
0x18001c164  mov     r15, [rsp+78h+arg_28]
0x18001c16c  mov     eax, [rcx]
0x18001c16e  mov     [rdi+128h], eax
0x18001c174  movzx   eax, word ptr [rcx+4]
0x18001c178  mov     [rdi+12Ch], ax
0x18001c17f  mov     eax, [r15]
0x18001c182  mov     [rdi+12Eh], eax
0x18001c188  movzx   eax, word ptr [r15+4]
0x18001c18d  mov     [rdi+132h], ax
0x18001c194  lea     eax, [rdx+1]
0x18001c197  mov     [rdi+134h], ebx
0x18001c19d  lock xadd cs:dword_1800AEFB8, eax
0x18001c1a5  inc     eax
0x18001c1a7  lea     rcx, [rdi+140h]
0x18001c1ae  mov     [rdi+138h], eax
0x18001c1b4  call    cs:__imp_CreateReadWriteLock
0x18001c1bb  nop     dword ptr [rax+rax+00h]
0x18001c1c0  mov     ebx, eax
0x18001c1c2  test    eax, eax
0x18001c1c4  jz      short loc_18001C22F
0x18001c1c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c1cd  lea     r15, WPP_GLOBAL_Control
0x18001c1d4  cmp     rcx, r15
0x18001c1d7  jnz     loc_18001C400
0x18001c1dd  mov     esi, r13d
0x18001c1e0  mov     r9d, [rsp+78h+arg_10]; int
0x18001c1e8  mov     edx, r13d; int
0x18001c1eb  mov     r8d, [rsp+78h+var_48]; int
0x18001c1f0  mov     rcx, rdi; struct MSMSEC_PORT_CONTEXT *
0x18001c1f3  mov     [rsp+78h+var_50], 0; int
0x18001c1fb  mov     [rsp+78h+var_58], esi; int
0x18001c1ff  call    ?SecMgrDeinitializePortHelper@@YAXPEAUMSMSEC_PORT_CONTEXT@@HHHHH@Z; SecMgrDeinitializePortHelper(MSMSEC_PORT_CONTEXT *,int,int,int,int,int)
0x18001c204  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c20b  cmp     rcx, r15
0x18001c20e  jnz     loc_18001C3AF
0x18001c214  mov     eax, ebx
0x18001c216  mov     rbx, [rsp+78h+arg_18]
0x18001c21e  add     rsp, 40h
0x18001c222  pop     r15
0x18001c224  pop     r14
0x18001c226  pop     r13
0x18001c228  pop     r12
0x18001c22a  pop     rdi
0x18001c22b  pop     rsi
0x18001c22c  pop     rbp
0x18001c22d  retn
0x18001c22f  mov     edx, 1
0x18001c234  lea     rax, [rdi+1C0h]
0x18001c23b  xor     ebx, ebx
0x18001c23d  mov     [rdi+1B4h], edx
0x18001c243  mov     [rdi+1B0h], ebx
0x18001c249  mov     r13d, edx
0x18001c24c  mov     [rdi+1B8h], edx
0x18001c252  mov     ecx, ebx
0x18001c254  mov     [rax+8], rax
0x18001c258  mov     [rax], rax
0x18001c25b  lea     rax, [rdi+1D0h]
0x18001c262  mov     [rax+8], rax
0x18001c266  mov     [rax], rax
0x18001c269  mov     [rdi+1E4h], ebx
0x18001c26f  mov     [rdi+1E8h], rbx
0x18001c276  mov     [rdi+1F0h], rdx
0x18001c27d  lea     rax, [rcx+20h]
0x18001c281  add     rax, rax
0x18001c284  mov     [rdi+rax*8], ebx
0x18001c287  mov     rax, rcx
0x18001c28a  add     rax, rax
0x18001c28d  add     rcx, rdx
0x18001c290  mov     [rdi+rax*8+208h], rbx
0x18001c298  cmp     rcx, 8
0x18001c29c  jnz     short loc_18001C27D
0x18001c29e  xor     edx, edx; Val
0x18001c2a0  mov     [rdi+280h], ebx
0x18001c2a6  lea     rcx, [rdi+2A0h]; void *
0x18001c2ad  mov     [rdi+288h], rbx
0x18001c2b4  lea     r8d, [rdx+64h]; Size
0x18001c2b8  call    memset_0
0x18001c2bd  mov     ecx, [rsp+78h+arg_30]
0x18001c2c4  mov     [rdi+7E8h], ebx
0x18001c2ca  sub     ecx, r13d
0x18001c2cd  jz      loc_18001C525
0x18001c2d3  sub     ecx, 2
0x18001c2d6  jz      short loc_18001C306
0x18001c2d8  sub     ecx, r13d
0x18001c2db  jz      loc_18001C4A2
0x18001c2e1  sub     ecx, 2
0x18001c2e4  jz      short loc_18001C306
0x18001c2e6  sub     ecx, r13d
0x18001c2e9  jz      loc_18001C4A2
0x18001c2ef  sub     ecx, r13d
0x18001c2f2  jz      short loc_18001C306
0x18001c2f4  sub     ecx, r13d
0x18001c2f7  jz      loc_18001C432
0x18001c2fd  cmp     ecx, 2
0x18001c300  jnz     loc_18001C427
0x18001c306  mov     [rdi+1F8h], r13d
0x18001c30d  lea     r15, WPP_GLOBAL_Control
0x18001c314  mov     rcx, rdi; struct MSMSEC_PORT_CONTEXT *
0x18001c317  call    ?AuthMgrInitialize@@YAKPEAUMSMSEC_PORT_CONTEXT@@@Z; AuthMgrInitialize(MSMSEC_PORT_CONTEXT *)
0x18001c31c  mov     ebx, eax
0x18001c31e  test    eax, eax
0x18001c320  jnz     loc_18001C534
0x18001c326  mov     rdx, [rsp+78h+arg_8]; void *
0x18001c32e  mov     rcx, rdi; struct MSMSEC_PORT_CONTEXT *
0x18001c331  mov     [rsp+78h+var_48], r13d
0x18001c336  call    ?KeyMgrInitialize@@YAKPEAUMSMSEC_PORT_CONTEXT@@PEAX@Z; KeyMgrInitialize(MSMSEC_PORT_CONTEXT *,void *)
0x18001c33b  mov     ebx, eax
0x18001c33d  test    eax, eax
0x18001c33f  jnz     loc_18001C558
0x18001c345  lea     rcx, [rdi+308h]; struct MSMSEC_EAPOL_KEY_CACHE *
0x18001c34c  mov     [rsp+78h+arg_10], r13d
0x18001c354  call    ?KeyCacheInitialize@@YAKPEAUMSMSEC_EAPOL_KEY_CACHE@@@Z; KeyCacheInitialize(MSMSEC_EAPOL_KEY_CACHE *)
0x18001c359  mov     ebx, eax
0x18001c35b  test    eax, eax
0x18001c35d  jnz     loc_18001C57C
0x18001c363  mov     rcx, rdi; struct MSMSEC_PORT_CONTEXT *
0x18001c366  call    ?WpsAuthMgrInitialize@@YAKPEAUMSMSEC_PORT_CONTEXT@@PEAUMSMSEC_HOST_DESC@@@Z; WpsAuthMgrInitialize(MSMSEC_PORT_CONTEXT *,MSMSEC_HOST_DESC *)
0x18001c36b  mov     ebx, eax
0x18001c36d  test    eax, eax
0x18001c36f  jz      loc_18001C204
0x18001c375  mov     esi, r13d
0x18001c378  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c37f  cmp     rcx, r15
0x18001c382  jz      loc_18001C1E0
0x18001c388  test    [rcx+44h], sil
0x18001c38c  jz      loc_18001C1E0
0x18001c392  mov     rcx, [rcx+38h]
0x18001c396  lea     r8, WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids
0x18001c39d  mov     edx, 40h ; '@'
0x18001c3a2  mov     r9d, eax
0x18001c3a5  call    WPP_SF_d
0x18001c3aa  jmp     loc_18001C1E0
0x18001c3af  test    dword ptr [rcx+44h], 100h
0x18001c3b6  jz      loc_18001C214
0x18001c3bc  mov     rcx, [rcx+38h]
0x18001c3c0  lea     r8, WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids
0x18001c3c7  mov     edx, 41h ; 'A'
0x18001c3cc  mov     r9d, ebx
0x18001c3cf  call    WPP_SF_d
0x18001c3d4  jmp     loc_18001C214
0x18001c3d9  test    dword ptr [rcx+44h], 100h
0x18001c3e0  jz      loc_18001C0B9
0x18001c3e6  mov     rcx, [rcx+38h]
0x18001c3ea  lea     r8, WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids
0x18001c3f1  mov     edx, 37h ; '7'
0x18001c3f6  call    WPP_SF_
0x18001c3fb  jmp     loc_18001C0B9
0x18001c400  test    byte ptr [rcx+44h], 1
0x18001c404  jz      loc_18001C1DD
0x18001c40a  mov     rcx, [rcx+38h]
0x18001c40e  lea     r8, WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids
0x18001c415  mov     edx, 38h ; '8'
0x18001c41a  mov     r9d, eax
0x18001c41d  call    WPP_SF_d
0x18001c422  jmp     loc_18001C1DD
0x18001c427  mov     [rdi+1F8h], ebx
0x18001c42d  jmp     loc_18001C30D
0x18001c432  cmp     r12d, 20h ; ' '
0x18001c436  jnz     loc_18001C30D
0x18001c43c  mov     r8, rsi; struct MSMSEC_INTF_CONTEXT *
0x18001c43f  mov     rdx, r15; unsigned __int8 (*)[6]
0x18001c442  mov     rcx, rdi; struct MSMSEC_PORT_CONTEXT *
0x18001c445  call    ?SecMgrStoreSaePmkFromPendingList@@YAKPEAUMSMSEC_PORT_CONTEXT@@AEAY05$$CBEAEAUMSMSEC_INTF_CONTEXT@@@Z; SecMgrStoreSaePmkFromPendingList(MSMSEC_PORT_CONTEXT *,uchar const (&)[6],MSMSEC_INTF_CONTEXT &)
0x18001c44a  mov     ebx, eax
0x18001c44c  test    eax, eax
0x18001c44e  jz      loc_18001C50F
0x18001c454  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c45b  lea     r15, WPP_GLOBAL_Control
0x18001c462  cmp     rcx, r15
0x18001c465  jz      short loc_18001C496
0x18001c467  test    [rcx+44h], r13b
0x18001c46b  jz      short loc_18001C496
0x18001c46d  lea     edx, [r12+19h]
0x18001c472  jmp     short loc_18001C479
0x18001c474  mov     edx, 3Fh ; '?'
0x18001c479  mov     r9d, eax
0x18001c47c  jmp     short loc_18001C486
0x18001c47e  mov     edx, 3Ch ; '<'
0x18001c483  mov     r9d, ebx
0x18001c486  mov     rcx, [rcx+38h]
0x18001c48a  lea     r8, WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids
0x18001c491  call    WPP_SF_d
0x18001c496  mov     esi, [rsp+78h+arg_0]
0x18001c49d  jmp     loc_18001C1E0
0x18001c4a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c4a9  lea     r15, WPP_GLOBAL_Control
0x18001c4b0  cmp     rcx, r15
0x18001c4b3  jz      short loc_18001C4D0
0x18001c4b5  test    byte ptr [rcx+44h], 2
0x18001c4b9  jz      short loc_18001C4D0
0x18001c4bb  mov     rcx, [rcx+38h]
0x18001c4bf  lea     r8, WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids
0x18001c4c6  mov     edx, 3Bh ; ';'
0x18001c4cb  call    WPP_SF_
0x18001c4d0  mov     rdx, rbp; struct MSMSEC_NW_DESC *
0x18001c4d3  mov     rcx, rdi; struct MSMSEC_PORT_CONTEXT *
0x18001c4d6  cmp     r12d, 20h ; ' '
0x18001c4da  jnz     short loc_18001C4EA
0x18001c4dc  lea     r8, [rsi+0A90h]; struct _LIST_ENTRY *
0x18001c4e3  call    ?SecMgrStorePSKFromPeerKeyList@@YAKPEAUMSMSEC_PORT_CONTEXT@@PEAUMSMSEC_NW_DESC@@PEAU_LIST_ENTRY@@@Z; SecMgrStorePSKFromPeerKeyList(MSMSEC_PORT_CONTEXT *,MSMSEC_NW_DESC *,_LIST_ENTRY *)
0x18001c4e8  jmp     short loc_18001C4F2
0x18001c4ea  mov     r8, r14; struct DOT11_MSMSEC_CONNECTION_PROFILE *
0x18001c4ed  call    ?SecMgrStorePSKFromProfile@@YAKPEAUMSMSEC_PORT_CONTEXT@@PEAUMSMSEC_NW_DESC@@PEAUDOT11_MSMSEC_CONNECTION_PROFILE@@@Z; SecMgrStorePSKFromProfile(MSMSEC_PORT_CONTEXT *,MSMSEC_NW_DESC *,DOT11_MSMSEC_CONNECTION_PROFILE *)
0x18001c4f2  mov     ebx, eax
0x18001c4f4  test    eax, eax
0x18001c4f6  jz      short loc_18001C516
0x18001c4f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c4ff  cmp     rcx, r15
0x18001c502  jz      short loc_18001C496
0x18001c504  test    [rcx+44h], r13b
0x18001c508  jz      short loc_18001C496
0x18001c50a  jmp     loc_18001C47E
0x18001c50f  lea     r15, WPP_GLOBAL_Control
0x18001c516  mov     dword ptr [rdi+1F8h], 0
0x18001c520  jmp     loc_18001C314
0x18001c525  cmp     [r14+20h], ebx
0x18001c529  jz      loc_18001C30D
0x18001c52f  jmp     loc_18001C306
0x18001c534  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c53b  cmp     rcx, r15
0x18001c53e  jz      loc_18001C496
0x18001c544  test    [rcx+44h], r13b
0x18001c548  jz      loc_18001C496
0x18001c54e  mov     edx, 3Dh ; '='
0x18001c553  jmp     loc_18001C479
0x18001c558  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c55f  cmp     rcx, r15
0x18001c562  jz      loc_18001C496
0x18001c568  test    [rcx+44h], r13b
0x18001c56c  jz      loc_18001C496
0x18001c572  mov     edx, 3Eh ; '>'
0x18001c577  jmp     loc_18001C479
0x18001c57c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c583  cmp     rcx, r15
0x18001c586  jz      loc_18001C496
0x18001c58c  test    [rcx+44h], r13b
0x18001c590  jz      loc_18001C496
0x18001c596  jmp     loc_18001C474
```
