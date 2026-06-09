# SecMgrInitializeAdapter(void *,MSMSEC_ADAPTER_INIT_PARAMS *,void *,MSMSEC_INTF_CONTEXT *)

- ea: `0x180004d44`
- end: `0x1800050a0`
- name: `?SecMgrInitializeAdapter@@YAKPEAXPEAUMSMSEC_ADAPTER_INIT_PARAMS@@0PEAUMSMSEC_INTF_CONTEXT@@@Z`
- size: `860`
- prototype: `unsigned int(void *, struct MSMSEC_ADAPTER_INIT_PARAMS *, void *, struct MSMSEC_INTF_CONTEXT *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800040b0`

## callees

- `0x180004c3c`
- `0x180004d44`
- `0x1800050a8`
- `0x180005418`
- `0x18000577c`
- `0x1800063f4`
- `0x18000892c`
- `0x180008998`
- `0x180044554`

## import_xrefs

- `MobileNetworking!CreateReadWriteLock` at `0x180004e72`
- `MobileNetworking!CreateReadWriteLock` at `0x180004e72`

## pseudocode

```c
__int64 __fastcall SecMgrInitializeAdapter(
        void *a1,
        struct MSMSEC_ADAPTER_INIT_PARAMS *a2,
        void *a3,
        struct MSMSEC_INTF_CONTEXT *a4)
{
  int v5; // r13d
  int v6; // r12d
  _OWORD *v10; // rcx
  __int64 v11; // rdx
  _OWORD *v12; // rax
  __int128 v13; // xmm1
  unsigned int v14; // eax
  unsigned int v15; // ebx
  int v16; // r15d
  _QWORD *v17; // rcx
  __int64 v19; // rdx

  v5 = 0;
  v6 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 52, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids);
  *((_DWORD *)a4 + 654) = 0;
  *((_QWORD *)a4 + 3) = a1;
  *((_OWORD *)a4 + 2) = *((_OWORD *)a2 + 10);
  memcpy_0((char *)a4 + 48, (char *)a2 + 180, 0x802u);
  v10 = (_OWORD *)((char *)a4 + 2104);
  v11 = 2;
  *((_DWORD *)a4 + 525) = *((_DWORD *)a2 + 44);
  v12 = *(_OWORD **)a2;
  do
  {
    *v10 = *v12;
    v10[1] = v12[1];
    v10[2] = v12[2];
    v10[3] = v12[3];
    v10[4] = v12[4];
    v10[5] = v12[5];
    v10[6] = v12[6];
    v13 = v12[7];
    v12 += 8;
    v10[7] = v13;
    v10 += 8;
    --v11;
  }
  while ( v11 );
  *((_DWORD *)a4 + 625) = *((_DWORD *)a2 + 2);
  *((_QWORD *)a4 + 313) = *((_QWORD *)a2 + 2);
  *((_QWORD *)a4 + 333) = 0;
  *((_QWORD *)a4 + 335) = (char *)a4 + 2672;
  *((_QWORD *)a4 + 334) = (char *)a4 + 2672;
  *((_QWORD *)a4 + 337) = (char *)a4 + 2688;
  *((_QWORD *)a4 + 336) = (char *)a4 + 2688;
  *((_QWORD *)a4 + 339) = (char *)a4 + 2704;
  *((_QWORD *)a4 + 338) = (char *)a4 + 2704;
  *((_QWORD *)a4 + 328) = 0;
  *((_QWORD *)a4 + 331) = a3;
  v14 = CreateReadWriteLock((char *)a4 + 2512);
  v15 = v14;
  if ( v14 )
  {
    v16 = 0;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_11;
    v19 = 53;
    goto LABEL_30;
  }
  *((_DWORD *)a4 + 590) = *((_DWORD *)a2 + 6);
  *((_WORD *)a4 + 1182) = *((_WORD *)a2 + 14);
  v16 = 1;
  v14 = CopyNICCapabilities(
          (struct MSMSEC_ADAPTER_INIT_PARAMS *)((char *)a2 + 32),
          (struct MSMSEC_INTF_CONTEXT *)((char *)a4 + 2368));
  v15 = v14;
  if ( v14 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_11;
    v19 = 54;
    goto LABEL_30;
  }
  *((_DWORD *)a4 + 624) = _InterlockedIncrement((_DWORD *)&qword_1800AEFB0 + 1);
  v14 = PmkCacheInitialize((struct MSMSEC_INTF_CONTEXT *)((char *)a4 + 3000), *((_DWORD *)a2 + 36), a3);
  v15 = v14;
  if ( v14 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_11;
    v19 = 55;
    goto LABEL_30;
  }
  v5 = 1;
  v14 = PreAuthInitialize((struct MSMSEC_INTF_CONTEXT *)((char *)a4 + 2912), a3);
  v15 = v14;
  if ( v14 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_11;
    v19 = 56;
    goto LABEL_30;
  }
  v14 = GroupKeyInitialize((void **)a4 + 407, a3);
  v15 = v14;
  if ( v14 )
  {
    v6 = 1;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_11;
    v19 = 57;
LABEL_30:
    WPP_SF_d(v17[7], v19, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids, v14);
LABEL_11:
    SecMgrDeinitializeAdapterHelper(a4, v16, v5, v6, 0);
    goto LABEL_12;
  }
  *((_DWORD *)a4 + 681) = 1;
LABEL_12:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 58, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids, v15);
  return v15;
}

```

## disassembly

```asm
0x180004d44  push    rbx
0x180004d46  push    rbp
0x180004d47  push    rsi
0x180004d48  push    rdi
0x180004d49  push    r12
0x180004d4b  push    r13
0x180004d4d  push    r14
0x180004d4f  push    r15
0x180004d51  sub     rsp, 38h
0x180004d55  xor     esi, esi
0x180004d57  mov     rdi, r9
0x180004d5a  mov     r13d, esi
0x180004d5d  mov     r12d, esi
0x180004d60  mov     rbp, r8
0x180004d63  mov     r14, rdx
0x180004d66  mov     rbx, rcx
0x180004d69  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d70  lea     rax, WPP_GLOBAL_Control
0x180004d77  cmp     rcx, rax
0x180004d7a  jnz     loc_180004FA7
0x180004d80  mov     [rdi+0A38h], esi
0x180004d86  lea     rcx, [rdi+30h]; void *
0x180004d8a  mov     [rdi+18h], rbx
0x180004d8e  lea     rdx, [r14+0B4h]; Src
0x180004d95  movups  xmm0, xmmword ptr [r14+0A0h]
0x180004d9d  mov     r8d, 802h; Size
0x180004da3  movdqu  xmmword ptr [rdi+20h], xmm0
0x180004da8  call    memcpy_0
0x180004dad  mov     eax, [r14+0B0h]
0x180004db4  lea     rcx, [rdi+838h]
0x180004dbb  mov     edx, 2
0x180004dc0  mov     [rdi+834h], eax
0x180004dc6  mov     rax, [r14]
0x180004dc9  lea     r8d, [rdx+7Eh]
0x180004dcd  movups  xmm0, xmmword ptr [rax]
0x180004dd0  movups  xmmword ptr [rcx], xmm0
0x180004dd3  movups  xmm1, xmmword ptr [rax+10h]
0x180004dd7  movups  xmmword ptr [rcx+10h], xmm1
0x180004ddb  movups  xmm0, xmmword ptr [rax+20h]
0x180004ddf  movups  xmmword ptr [rcx+20h], xmm0
0x180004de3  movups  xmm1, xmmword ptr [rax+30h]
0x180004de7  movups  xmmword ptr [rcx+30h], xmm1
0x180004deb  movups  xmm0, xmmword ptr [rax+40h]
0x180004def  movups  xmmword ptr [rcx+40h], xmm0
0x180004df3  movups  xmm1, xmmword ptr [rax+50h]
0x180004df7  movups  xmmword ptr [rcx+50h], xmm1
0x180004dfb  movups  xmm0, xmmword ptr [rax+60h]
0x180004dff  movups  xmmword ptr [rcx+60h], xmm0
0x180004e03  movups  xmm1, xmmword ptr [rax+70h]
0x180004e07  add     rax, r8
0x180004e0a  movups  xmmword ptr [rcx+70h], xmm1
0x180004e0e  add     rcx, r8
0x180004e11  sub     rdx, 1
0x180004e15  jnz     short loc_180004DCD
0x180004e17  mov     eax, [r14+8]
0x180004e1b  lea     rcx, [rdi+9D0h]
0x180004e22  mov     [rdi+9C4h], eax
0x180004e28  mov     rax, [r14+10h]
0x180004e2c  mov     [rdi+9C8h], rax
0x180004e33  lea     rax, [rdi+0A70h]
0x180004e3a  mov     [rdi+0A68h], rsi
0x180004e41  mov     [rax+8], rax
0x180004e45  mov     [rax], rax
0x180004e48  lea     rax, [rdi+0A80h]
0x180004e4f  mov     [rax+8], rax
0x180004e53  mov     [rax], rax
0x180004e56  lea     rax, [rdi+0A90h]
0x180004e5d  mov     [rax+8], rax
0x180004e61  mov     [rax], rax
0x180004e64  mov     [rdi+0A40h], rsi
0x180004e6b  mov     [rdi+0A58h], rbp
0x180004e72  call    cs:__imp_CreateReadWriteLock
0x180004e79  nop     dword ptr [rax+rax+00h]
0x180004e7e  mov     ebx, eax
0x180004e80  test    eax, eax
0x180004e82  jnz     loc_180004FCE
0x180004e88  lea     esi, [rax+1]
0x180004e8b  mov     eax, [r14+18h]
0x180004e8f  mov     [rdi+938h], eax
0x180004e95  lea     rdx, [rdi+940h]; struct DOT11_MSMSEC_NIC_CAPABILITIES *
0x180004e9c  movzx   eax, word ptr [r14+1Ch]
0x180004ea1  lea     rcx, [r14+20h]; struct DOT11_MSMSEC_NIC_CAPABILITIES *
0x180004ea5  mov     [rdi+93Ch], ax
0x180004eac  mov     r15d, esi
0x180004eaf  call    ?CopyNICCapabilities@@YAKAEBUDOT11_MSMSEC_NIC_CAPABILITIES@@PEAU1@@Z; CopyNICCapabilities(DOT11_MSMSEC_NIC_CAPABILITIES const &,DOT11_MSMSEC_NIC_CAPABILITIES *)
0x180004eb4  mov     ebx, eax
0x180004eb6  test    eax, eax
0x180004eb8  jnz     short loc_180004F30
0x180004eba  mov     eax, esi
0x180004ebc  lock xadd dword ptr cs:qword_1800AEFB0+4, eax
0x180004ec4  add     eax, esi
0x180004ec6  lea     rcx, [rdi+0BB8h]; struct MSMSEC_PMKCACHE_CONTEXT *
0x180004ecd  mov     [rdi+9C0h], eax
0x180004ed3  mov     r8, rbp; void *
0x180004ed6  mov     edx, [r14+90h]; unsigned int
0x180004edd  call    ?PmkCacheInitialize@@YAKPEAUMSMSEC_PMKCACHE_CONTEXT@@KPEAX@Z; PmkCacheInitialize(MSMSEC_PMKCACHE_CONTEXT *,ulong,void *)
0x180004ee2  mov     ebx, eax
0x180004ee4  test    eax, eax
0x180004ee6  jnz     loc_180004F84
0x180004eec  lea     rcx, [rdi+0B60h]; struct MSMSEC_PREAUTH_CONTEXT *
0x180004ef3  mov     rdx, rbp; void *
0x180004ef6  mov     r13d, esi
0x180004ef9  call    ?PreAuthInitialize@@YAKPEAUMSMSEC_PREAUTH_CONTEXT@@PEAX@Z; PreAuthInitialize(MSMSEC_PREAUTH_CONTEXT *,void *)
0x180004efe  mov     ebx, eax
0x180004f00  test    eax, eax
0x180004f02  jnz     loc_18000500D
0x180004f08  lea     rcx, [rdi+0CB8h]; void **
0x180004f0f  mov     rdx, rbp; void *
0x180004f12  call    ?GroupKeyInitialize@@YAKPEAUMSMSEC_GROUP_KEY_CONTEXT@@PEAX@Z; GroupKeyInitialize(MSMSEC_GROUP_KEY_CONTEXT *,void *)
0x180004f17  mov     ebx, eax
0x180004f19  test    eax, eax
0x180004f1b  jnz     loc_180005035
0x180004f21  mov     [rdi+0AA4h], esi
0x180004f27  lea     rbp, WPP_GLOBAL_Control
0x180004f2e  jmp     short loc_180004F60
0x180004f30  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f37  lea     rbp, WPP_GLOBAL_Control
0x180004f3e  cmp     rcx, rbp
0x180004f41  jnz     loc_180004FFC
0x180004f47  mov     r9d, r12d; int
0x180004f4a  mov     [rsp+78h+var_58], 0; int
0x180004f52  mov     r8d, r13d; int
0x180004f55  mov     edx, r15d; int
0x180004f58  mov     rcx, rdi; struct MSMSEC_INTF_CONTEXT *
0x180004f5b  call    ?SecMgrDeinitializeAdapterHelper@@YAXPEAUMSMSEC_INTF_CONTEXT@@HHHH@Z; SecMgrDeinitializeAdapterHelper(MSMSEC_INTF_CONTEXT *,int,int,int,int)
0x180004f60  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f67  cmp     rcx, rbp
0x180004f6a  jnz     loc_180005076
0x180004f70  mov     eax, ebx
0x180004f72  add     rsp, 38h
0x180004f76  pop     r15
0x180004f78  pop     r14
0x180004f7a  pop     r13
0x180004f7c  pop     r12
0x180004f7e  pop     rdi
0x180004f7f  pop     rsi
0x180004f80  pop     rbp
0x180004f81  pop     rbx
0x180004f82  retn
0x180004f84  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f8b  lea     rbp, WPP_GLOBAL_Control
0x180004f92  cmp     rcx, rbp
0x180004f95  jz      short loc_180004F47
0x180004f97  test    [rcx+44h], sil
0x180004f9b  jz      short loc_180004F47
0x180004f9d  mov     edx, 37h ; '7'
0x180004fa2  jmp     loc_18000505E
0x180004fa7  test    dword ptr [rcx+44h], 100h
0x180004fae  jz      loc_180004D80
0x180004fb4  mov     rcx, [rcx+38h]
0x180004fb8  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x180004fbf  mov     edx, 34h ; '4'
0x180004fc4  call    WPP_SF_
0x180004fc9  jmp     loc_180004D80
0x180004fce  mov     r15d, esi
0x180004fd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180004fd8  lea     rbp, WPP_GLOBAL_Control
0x180004fdf  cmp     rcx, rbp
0x180004fe2  jz      loc_180004F47
0x180004fe8  mov     esi, 1
0x180004fed  test    [rcx+44h], sil
0x180004ff1  jz      loc_180004F47
0x180004ff7  lea     edx, [rsi+34h]
0x180004ffa  jmp     short loc_18000505E
0x180004ffc  test    [rcx+44h], sil
0x180005000  jz      loc_180004F47
0x180005006  mov     edx, 36h ; '6'
0x18000500b  jmp     short loc_18000505E
0x18000500d  mov     rcx, cs:WPP_GLOBAL_Control
0x180005014  lea     rbp, WPP_GLOBAL_Control
0x18000501b  cmp     rcx, rbp
0x18000501e  jz      loc_180004F47
0x180005024  test    [rcx+44h], sil
0x180005028  jz      loc_180004F47
0x18000502e  mov     edx, 38h ; '8'
0x180005033  jmp     short loc_18000505E
0x180005035  mov     r12d, esi
0x180005038  mov     rcx, cs:WPP_GLOBAL_Control
0x18000503f  lea     rbp, WPP_GLOBAL_Control
0x180005046  cmp     rcx, rbp
0x180005049  jz      loc_180004F47
0x18000504f  test    [rcx+44h], sil
0x180005053  jz      loc_180004F47
0x180005059  mov     edx, 39h ; '9'
0x18000505e  mov     rcx, [rcx+38h]
0x180005062  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x180005069  mov     r9d, eax
0x18000506c  call    WPP_SF_d
0x180005071  jmp     loc_180004F47
0x180005076  test    dword ptr [rcx+44h], 100h
0x18000507d  jz      loc_180004F70
0x180005083  mov     rcx, [rcx+38h]
0x180005087  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x18000508e  mov     edx, 3Ah ; ':'
0x180005093  mov     r9d, ebx
0x180005096  call    WPP_SF_d
0x18000509b  jmp     loc_180004F70
```
