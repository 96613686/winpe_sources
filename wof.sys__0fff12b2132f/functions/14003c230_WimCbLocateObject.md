# WimCbLocateObject

- ea: `0x14003c230`
- end: `0x14003c3f4`
- name: `WimCbLocateObject`
- size: `452`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x14002cbe4`
- `0x14002e4f0`
- `0x14003c230`
- `0x14003c3fc`
- `0x14003c4c8`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14003c323`
- `ntoskrnl!RtlCompareMemory` at `0x14003c323`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14003c3d8`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14003c3d8`

## pseudocode

```c
__int64 __fastcall WimCbLocateObject(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        char a7,
        int a8,
        __int64 a9)
{
  __int64 v9; // rdi
  __int64 result; // rax
  __int64 v14; // rsi
  __int64 v15; // r14
  char v16; // bp
  unsigned int v17; // ebx
  __int64 v18; // rdx
  __int64 v19; // rcx
  bool v20; // zf
  __int64 v21; // [rsp+38h] [rbp-40h]
  __int64 v22; // [rsp+88h] [rbp+10h] BYREF

  v9 = a5;
  v22 = 0;
  result = WimFSFFindOverlayByDataSource(a2, *(_QWORD *)(a5 + 8), &v22);
  if ( (int)result >= 0 )
  {
    v14 = v22;
LABEL_6:
    v15 = 0;
    if ( (unsigned __int8)WimFSFAcquireRundownAndRemount(a1, a2, v14) )
    {
      v16 = 1;
      if ( *(_DWORD *)v9 == 1 )
      {
        v15 = WimFSFFindStreamResource(a1, v14, v9 + 16);
        if ( !v15 )
        {
LABEL_9:
          v17 = -1073741275;
          goto LABEL_23;
        }
      }
      else
      {
        v18 = *(_QWORD *)(v14 + 104);
        if ( (*(_DWORD *)(v18 + 100) & 2) != 0
          && RtlCompareMemory((const void *)(v9 + 36), (const void *)(v18 + 946), 0x14u) != 20 )
        {
          goto LABEL_9;
        }
      }
    }
    else
    {
      v16 = 0;
    }
    v19 = a9;
    if ( a9 )
    {
      *(_QWORD *)(a9 + 24) = v14;
      if ( v15 )
      {
        *(_OWORD *)(v19 + 4) = *(_OWORD *)(v15 + 30);
        *(_DWORD *)(v19 + 20) = *(_DWORD *)(v15 + 46);
        *(_QWORD *)(v19 + 40) = *(_QWORD *)v15 & 0xFFFFFFFFFFFFFFLL;
        *(_QWORD *)(v19 + 48) = *(_QWORD *)(v15 + 16);
        *(_QWORD *)(v19 + 56) = *(_QWORD *)(v15 + 8);
        v20 = (*(_BYTE *)(v15 + 7) & 4) == 0;
      }
      else
      {
        *(_OWORD *)(v19 + 4) = *(_OWORD *)(v9 + 16);
        *(_DWORD *)(v19 + 20) = *(_DWORD *)(v9 + 32);
        if ( *(_DWORD *)v9 != 2 )
        {
          *(_QWORD *)(v19 + 48) = a4;
          goto LABEL_22;
        }
        *(_QWORD *)(v19 + 40) = *(_QWORD *)(v9 + 64);
        *(_QWORD *)(v19 + 48) = *(_QWORD *)(v9 + 56);
        *(_QWORD *)(v19 + 56) = *(_QWORD *)(v9 + 72);
        v20 = *(_QWORD *)(v9 + 56) == *(_QWORD *)(v9 + 64);
      }
      if ( !v20 )
        *(_DWORD *)v19 |= 2u;
    }
LABEL_22:
    v17 = 0;
    if ( !v16 )
      return v17;
LABEL_23:
    ExReleaseRundownProtection(*(PEX_RUNDOWN_REF *)(v14 + 96));
    return v17;
  }
  if ( a7 )
  {
    result = WimFSFCreateOverlay(&v22, a2, 0, *(_QWORD *)(v9 + 8), 0, 0, 0, v21);
    if ( (int)result >= 0 )
    {
      v14 = v22;
      _InterlockedOr((volatile signed __int32 *)(v22 + 40), 4u);
      goto LABEL_6;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14003c230  mov     rax, rsp
0x14003c233  push    rbx
0x14003c234  push    rbp
0x14003c235  push    rsi
0x14003c236  push    rdi
0x14003c237  push    r14
0x14003c239  push    r15
0x14003c23b  sub     rsp, 48h
0x14003c23f  mov     rdi, [rsp+78h+arg_20]
0x14003c247  lea     r8, [rax+10h]
0x14003c24b  mov     rbp, rdx
0x14003c24e  mov     qword ptr [rax+10h], 0
0x14003c256  mov     r15, rcx
0x14003c259  mov     rbx, r9
0x14003c25c  mov     rcx, rbp
0x14003c25f  mov     rdx, [rdi+8]
0x14003c263  call    WimFSFFindOverlayByDataSource
0x14003c268  test    eax, eax
0x14003c26a  jns     short loc_14003C2C1
0x14003c26c  cmp     [rsp+78h+arg_30], 0
0x14003c274  jz      loc_14003C3E6
0x14003c27a  mov     r9, [rdi+8]
0x14003c27e  lea     rcx, [rsp+78h+arg_8]
0x14003c286  mov     [rsp+78h+var_48], 0
0x14003c28e  xor     r8d, r8d
0x14003c291  mov     [rsp+78h+var_50], 0
0x14003c299  mov     rdx, rbp
0x14003c29c  mov     [rsp+78h+var_58], 0
0x14003c2a5  call    WimFSFCreateOverlay
0x14003c2aa  test    eax, eax
0x14003c2ac  js      loc_14003C3E6
0x14003c2b2  mov     rsi, [rsp+78h+arg_8]
0x14003c2ba  lock or dword ptr [rsi+28h], 4
0x14003c2bf  jmp     short loc_14003C2C9
0x14003c2c1  mov     rsi, [rsp+78h+arg_8]
0x14003c2c9  mov     r8, rsi
0x14003c2cc  mov     rdx, rbp
0x14003c2cf  mov     rcx, r15
0x14003c2d2  xor     r14d, r14d
0x14003c2d5  call    WimFSFAcquireRundownAndRemount
0x14003c2da  test    al, al
0x14003c2dc  jz      short loc_14003C337
0x14003c2de  lea     ebp, [r14+1]
0x14003c2e2  cmp     [rdi], ebp
0x14003c2e4  jnz     short loc_14003C307
0x14003c2e6  lea     r8, [rdi+10h]
0x14003c2ea  mov     rdx, rsi
0x14003c2ed  mov     rcx, r15
0x14003c2f0  call    WimFSFFindStreamResource
0x14003c2f5  mov     r14, rax
0x14003c2f8  test    rax, rax
0x14003c2fb  jnz     short loc_14003C33A
0x14003c2fd  mov     ebx, 0C0000225h
0x14003c302  jmp     loc_14003C3D4
0x14003c307  mov     rdx, [rsi+68h]
0x14003c30b  mov     eax, [rdx+64h]
0x14003c30e  test    al, 2
0x14003c310  jz      short loc_14003C33A
0x14003c312  add     rdx, 3B2h; Source2
0x14003c319  lea     rcx, [rdi+24h]; Source1
0x14003c31d  mov     r8d, 14h; Length
0x14003c323  call    cs:__imp_RtlCompareMemory
0x14003c32a  nop     dword ptr [rax+rax+00h]
0x14003c32f  cmp     rax, 14h
0x14003c333  jz      short loc_14003C33A
0x14003c335  jmp     short loc_14003C2FD
0x14003c337  xor     bpl, bpl
0x14003c33a  mov     rcx, [rsp+78h+arg_40]
0x14003c342  test    rcx, rcx
0x14003c345  jz      loc_14003C3CD
0x14003c34b  mov     [rcx+18h], rsi
0x14003c34f  test    r14, r14
0x14003c352  jz      short loc_14003C38F
0x14003c354  movups  xmm0, xmmword ptr [r14+1Eh]
0x14003c359  mov     rdx, 0FFFFFFFFFFFFFFh
0x14003c363  movups  xmmword ptr [rcx+4], xmm0
0x14003c367  mov     eax, [r14+2Eh]
0x14003c36b  mov     [rcx+14h], eax
0x14003c36e  mov     rax, [r14]
0x14003c371  and     rax, rdx
0x14003c374  mov     [rcx+28h], rax
0x14003c378  mov     rax, [r14+10h]
0x14003c37c  mov     [rcx+30h], rax
0x14003c380  mov     rax, [r14+8]
0x14003c384  mov     [rcx+38h], rax
0x14003c388  test    byte ptr [r14+7], 4
0x14003c38d  jmp     short loc_14003C3C2
0x14003c38f  movups  xmm0, xmmword ptr [rdi+10h]
0x14003c393  movups  xmmword ptr [rcx+4], xmm0
0x14003c397  mov     eax, [rdi+20h]
0x14003c39a  mov     [rcx+14h], eax
0x14003c39d  cmp     dword ptr [rdi], 2
0x14003c3a0  jnz     short loc_14003C3C9
0x14003c3a2  mov     rax, [rdi+40h]
0x14003c3a6  mov     [rcx+28h], rax
0x14003c3aa  mov     rax, [rdi+38h]
0x14003c3ae  mov     [rcx+30h], rax
0x14003c3b2  mov     rax, [rdi+48h]
0x14003c3b6  mov     [rcx+38h], rax
0x14003c3ba  mov     rax, [rdi+40h]
0x14003c3be  cmp     [rdi+38h], rax
0x14003c3c2  jz      short loc_14003C3CD
0x14003c3c4  or      dword ptr [rcx], 2
0x14003c3c7  jmp     short loc_14003C3CD
0x14003c3c9  mov     [rcx+30h], rbx
0x14003c3cd  xor     ebx, ebx
0x14003c3cf  test    bpl, bpl
0x14003c3d2  jz      short loc_14003C3E4
0x14003c3d4  mov     rcx, [rsi+60h]; RunRef
0x14003c3d8  call    cs:__imp_ExReleaseRundownProtection
0x14003c3df  nop     dword ptr [rax+rax+00h]
0x14003c3e4  mov     eax, ebx
0x14003c3e6  add     rsp, 48h
0x14003c3ea  pop     r15
0x14003c3ec  pop     r14
0x14003c3ee  pop     rdi
0x14003c3ef  pop     rsi
0x14003c3f0  pop     rbp
0x14003c3f1  pop     rbx
0x14003c3f2  retn
```
