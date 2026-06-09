# bSpEnableSprites

- ea: `0x14022a070`
- end: `0x14022a44b`
- name: `bSpEnableSprites`
- size: `987`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140119d14`
- `0x14022a070`
- `0x14022a454`
- `0x14030c344`

## import_xrefs

- `ntoskrnl!RtlInitializeBitMap` at `0x14022a144`
- `ntoskrnl!RtlInitializeBitMap` at `0x14022a144`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14022a1db`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14022a1eb`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14022a1fb`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14022a1db`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14022a1eb`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14022a1fb`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x14022a290`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x14022a290`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x14022a2b7`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x14022a2b7`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x14022a167`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x14022a177`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x14022a187`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x14022a167`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x14022a177`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x14022a187`
- `win32kbase!GreInitializePushLock` at `0x14022a157`
- `win32kbase!GreInitializePushLock` at `0x14022a157`
- `win32kbase!GreCreateSemaphore` at `0x14022a108`
- `win32kbase!GreCreateSemaphore` at `0x14022a11f`
- `win32kbase!GreCreateSemaphore` at `0x14022a108`
- `win32kbase!GreCreateSemaphore` at `0x14022a11f`
- `win32kbase!?vStamp@REGION@@AEAAXXZ` at `0x14022a2ce`
- `win32kbase!?vStamp@REGION@@AEAAXXZ` at `0x14022a2ce`
- `win32kbase!GreDeleteSemaphore` at `0x14022a429`
- `win32kbase!GreDeleteSemaphore` at `0x14022a43a`
- `win32kbase!GreDeleteSemaphore` at `0x14022a429`
- `win32kbase!GreDeleteSemaphore` at `0x14022a43a`
- `win32kbase!GreCreateRectRgn` at `0x14022a2ef`
- `win32kbase!GreCreateRectRgn` at `0x14022a2ef`
- `win32kbase!Win32AllocPoolZInit` at `0x14022a218`
- `win32kbase!Win32AllocPoolZInit` at `0x14022a218`
- `win32kbase!Win32FreePool` at `0x14022a418`
- `win32kbase!Win32FreePool` at `0x14022a418`

## pseudocode

```c
__int64 __fastcall bSpEnableSprites(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // rbx
  const struct _RECTL *v4; // r14
  __int64 v5; // r8
  int v6; // ecx
  _DWORD *v8; // rsi
  struct _SURFOBJ *Surface; // rdx
  struct REGION *v10; // rdx
  REGION *v11; // rcx
  int v12; // [rsp+20h] [rbp-10h]
  struct REGION *v13; // [rsp+60h] [rbp+30h] BYREF
  REGION *v14; // [rsp+68h] [rbp+38h] BYREF
  __int64 v15; // [rsp+70h] [rbp+40h] BYREF

  if ( (*(_DWORD *)(a1 + 40) & 1) == 0 )
    return 1;
  v2 = *(_QWORD *)(a1 + 2544);
  v3 = a1 + 80;
  *(_QWORD *)(a1 + 80) = a1;
  v4 = (const struct _RECTL *)(a1 + 120);
  v5 = (v2 + 24) & -(__int64)(v2 != 0);
  *(_QWORD *)(a1 + 112) = v5 & -(__int64)(v5 != 24);
  *(_DWORD *)(a1 + 188) = *(_DWORD *)(v5 + 0x48);
  v6 = *(unsigned __int16 *)(v5 + 0x4C);
  *(_DWORD *)(v3 + 96) = v6;
  LODWORD(v2) = *(_DWORD *)(v5 + 0x78);
  *(_DWORD *)(v3 + 92) = v2;
  *(_DWORD *)(v3 + 104) = v6;
  *(_DWORD *)(v3 + 100) = v2;
  *(_DWORD *)(v3 + 112) = **(_DWORD **)(*(_QWORD *)(v5 + 136) + 112LL)
                        | *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v5 + 136) + 112LL) + 8LL);
  v4->left = 0;
  *(_DWORD *)(v3 + 48) = *(_DWORD *)(v5 + 32);
  *(_DWORD *)(v3 + 44) = 0;
  *(_DWORD *)(v3 + 52) = *(_DWORD *)(v5 + 36);
  *(_QWORD *)(v3 + 120) = GreCreateSemaphore();
  *(_BYTE *)(v3 + 128) = 0;
  *(_QWORD *)(v3 + 136) = GreCreateSemaphore();
  RtlInitializeBitMap((PRTL_BITMAP)(v3 + 672), (PULONG)(v3 + 688), 0x40u);
  GreInitializePushLock((struct W32_PUSH_LOCK *)(v3 + 696));
  RGNMEMOBJ::RGNMEMOBJ((RGNMEMOBJ *)&v14);
  RGNMEMOBJ::RGNMEMOBJ((RGNMEMOBJ *)&v15);
  RGNMEMOBJ::RGNMEMOBJ((RGNMEMOBJ *)&v13);
  if ( v14 )
  {
    if ( v15 )
    {
      if ( v13 )
      {
        if ( *(_QWORD *)(v3 + 120) )
        {
          if ( *(_QWORD *)(v3 + 136) )
          {
            v8 = (_DWORD *)Win32AllocPoolZInit(40, 1919972167);
            if ( v8 )
            {
              Surface = psoSpCreateSurface((struct _SPRITESTATE *)v3, 0, 1, 1, v12);
              if ( Surface )
              {
                *v8 = *(_DWORD *)(v3 + 44);
                v8[1] = *(_DWORD *)(v3 + 52);
                *((_QWORD *)v8 + 1) = 40;
                *((_QWORD *)v8 + 2) = 0;
                v8[6] = v4->left;
                v8[7] = *(_DWORD *)(v3 + 48);
                *((_QWORD *)v8 + 4) = 0;
                *(_QWORD *)(v3 + 1032) = Surface;
                *(_QWORD *)(v3 + 144) = v8;
                *(_QWORD *)(v3 + 152) = v8 + 10;
                RGNOBJ::vSet((RGNOBJ *)&v13, v4);
                v10 = v13;
                *(_QWORD *)(v3 + 872) = v13;
                XCLIPOBJ::vSetup((XCLIPOBJ *)(v3 + 880), v10, (const struct ERECTL *)v4, 1);
                v11 = v14;
                *(_QWORD *)(v3 + 704) = v14;
                REGION::vStamp(v11);
                *(_QWORD *)(v3 + 712) = v15;
                *(_QWORD *)(v3 + 1064) = GreCreateRectRgn(0, 0, 0, 0);
                *(_QWORD *)(v3 + 1200) = *(_QWORD *)(a1 + 2808);
                *(_QWORD *)(v3 + 1208) = *(_QWORD *)(a1 + 2792);
                *(_QWORD *)(v3 + 1216) = *(_QWORD *)(a1 + 2800);
                *(_QWORD *)(v3 + 1232) = *(_QWORD *)(a1 + 2824);
                *(_QWORD *)(v3 + 1240) = *(_QWORD *)(a1 + 2832);
                *(_QWORD *)(v3 + 1248) = *(_QWORD *)(a1 + 2840);
                *(_QWORD *)(v3 + 1256) = *(_QWORD *)(a1 + 2864);
                *(_QWORD *)(v3 + 1264) = *(_QWORD *)(a1 + 2928);
                *(_QWORD *)(v3 + 1272) = *(_QWORD *)(a1 + 3272);
                *(_QWORD *)(v3 + 1280) = *(_QWORD *)(a1 + 3248);
                *(_QWORD *)(v3 + 1288) = *(_QWORD *)(a1 + 3240);
                *(_QWORD *)(v3 + 1296) = *(_QWORD *)(a1 + 3224);
                *(_QWORD *)(v3 + 1312) = *(_QWORD *)(a1 + 3232);
                *(_QWORD *)(v3 + 1304) = *(_QWORD *)(a1 + 3000);
                *(_QWORD *)(v3 + 1320) = *(_QWORD *)(a1 + 3400);
                if ( (*(_DWORD *)(a1 + 40) & 0x20000) == 0 )
                {
                  vSpHook((struct _SPRITESTATE *)v3);
                  vSpComputeSpriteRanges();
                }
                return 1;
              }
              Win32FreePool(v8);
            }
          }
        }
      }
    }
  }
  if ( *(_QWORD *)(v3 + 120) )
    GreDeleteSemaphore();
  if ( *(_QWORD *)(v3 + 136) )
    GreDeleteSemaphore();
  *(_QWORD *)(v3 + 120) = 0;
  *(_QWORD *)(v3 + 136) = 0;
  RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v14);
  RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v15);
  RGNOBJ::vDeleteRGNOBJ((RGNOBJ *)&v13);
  return 0;
}

```

## disassembly

```asm
0x14022a070  mov     [rsp-28h+arg_18], rbx
0x14022a075  push    rbp
0x14022a076  push    rsi
0x14022a077  push    rdi
0x14022a078  push    r14
0x14022a07a  push    r15
0x14022a07c  mov     rbp, rsp
0x14022a07f  sub     rsp, 30h
0x14022a083  mov     eax, [rcx+28h]
0x14022a086  mov     rdi, rcx
0x14022a089  test    al, 1
0x14022a08b  jz      loc_14022A3DD
0x14022a091  mov     rax, [rcx+9F0h]
0x14022a098  lea     rbx, [rcx+50h]
0x14022a09c  mov     [rbx], rcx
0x14022a09f  lea     r14, [rbx+28h]
0x14022a0a3  lea     rdx, [rax+18h]
0x14022a0a7  neg     rax
0x14022a0aa  sbb     r8, r8
0x14022a0ad  and     r8, rdx
0x14022a0b0  lea     rax, [r8-18h]
0x14022a0b4  neg     rax
0x14022a0b7  sbb     rcx, rcx
0x14022a0ba  xor     r15d, r15d
0x14022a0bd  and     rcx, r8
0x14022a0c0  mov     [rbx+20h], rcx
0x14022a0c4  mov     eax, [r8+48h]
0x14022a0c8  mov     [rbx+6Ch], eax
0x14022a0cb  movzx   ecx, word ptr [r8+4Ch]
0x14022a0d0  mov     [rbx+60h], ecx
0x14022a0d3  mov     eax, [r8+78h]
0x14022a0d7  mov     [rbx+5Ch], eax
0x14022a0da  mov     [rbx+68h], ecx
0x14022a0dd  mov     [rbx+64h], eax
0x14022a0e0  mov     rax, [r8+88h]
0x14022a0e7  mov     rcx, [rax+70h]
0x14022a0eb  mov     edx, [rcx+8]
0x14022a0ee  or      edx, [rcx]
0x14022a0f0  mov     [rbx+70h], edx
0x14022a0f3  mov     [r14], r15d
0x14022a0f6  mov     eax, [r8+20h]
0x14022a0fa  mov     [rbx+30h], eax
0x14022a0fd  mov     [rbx+2Ch], r15d
0x14022a101  mov     eax, [r8+24h]
0x14022a105  mov     [rbx+34h], eax
0x14022a108  call    cs:__imp_GreCreateSemaphore
0x14022a10f  nop     dword ptr [rax+rax+00h]
0x14022a114  mov     [rbx+78h], rax
0x14022a118  mov     [rbx+80h], r15b
0x14022a11f  call    cs:__imp_GreCreateSemaphore
0x14022a126  nop     dword ptr [rax+rax+00h]
0x14022a12b  lea     rdx, [rbx+2B0h]; BitMapBuffer
0x14022a132  mov     [rbx+88h], rax
0x14022a139  lea     rcx, [rbx+2A0h]; BitMapHeader
0x14022a140  lea     r8d, [r15+40h]; SizeOfBitMap
0x14022a144  call    cs:__imp_RtlInitializeBitMap
0x14022a14b  nop     dword ptr [rax+rax+00h]
0x14022a150  lea     rcx, [rbx+2B8h]
0x14022a157  call    cs:__imp_?GreInitializePushLock@@YAXPEAVW32_PUSH_LOCK@@@Z; GreInitializePushLock(W32_PUSH_LOCK *)
0x14022a15e  nop     dword ptr [rax+rax+00h]
0x14022a163  lea     rcx, [rbp+arg_8]
0x14022a167  call    cs:__imp_??0RGNMEMOBJ@@QEAA@XZ; RGNMEMOBJ::RGNMEMOBJ(void)
0x14022a16e  nop     dword ptr [rax+rax+00h]
0x14022a173  lea     rcx, [rbp+arg_10]
0x14022a177  call    cs:__imp_??0RGNMEMOBJ@@QEAA@XZ; RGNMEMOBJ::RGNMEMOBJ(void)
0x14022a17e  nop     dword ptr [rax+rax+00h]
0x14022a183  lea     rcx, [rbp+arg_0]
0x14022a187  call    cs:__imp_??0RGNMEMOBJ@@QEAA@XZ; RGNMEMOBJ::RGNMEMOBJ(void)
0x14022a18e  nop     dword ptr [rax+rax+00h]
0x14022a193  cmp     [rbp+arg_8], r15
0x14022a197  jz      short loc_14022A1AF
0x14022a199  cmp     [rbp+arg_10], r15
0x14022a19d  jz      short loc_14022A1AF
0x14022a19f  cmp     [rbp+arg_0], r15
0x14022a1a3  jz      short loc_14022A1AF
0x14022a1a5  cmp     [rbx+78h], r15
0x14022a1a9  jnz     loc_14022A3F4
0x14022a1af  mov     rcx, [rbx+78h]
0x14022a1b3  test    rcx, rcx
0x14022a1b6  jnz     loc_14022A429
0x14022a1bc  mov     rcx, [rbx+88h]
0x14022a1c3  test    rcx, rcx
0x14022a1c6  jnz     loc_14022A43A
0x14022a1cc  lea     rcx, [rbp+arg_8]
0x14022a1d0  mov     [rbx+78h], r15
0x14022a1d4  mov     [rbx+88h], r15
0x14022a1db  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x14022a1e2  nop     dword ptr [rax+rax+00h]
0x14022a1e7  lea     rcx, [rbp+arg_10]
0x14022a1eb  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x14022a1f2  nop     dword ptr [rax+rax+00h]
0x14022a1f7  lea     rcx, [rbp+arg_0]
0x14022a1fb  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x14022a202  nop     dword ptr [rax+rax+00h]
0x14022a207  xor     eax, eax
0x14022a209  jmp     loc_14022A3E2
0x14022a20e  mov     edx, 72707347h
0x14022a213  mov     ecx, 28h ; '('
0x14022a218  call    cs:__imp_Win32AllocPoolZInit
0x14022a21f  nop     dword ptr [rax+rax+00h]
0x14022a224  mov     rsi, rax
0x14022a227  test    rax, rax
0x14022a22a  jz      short loc_14022A1AF
0x14022a22c  xor     edx, edx; unsigned int
0x14022a22e  mov     rcx, rbx; struct _SPRITESTATE *
0x14022a231  lea     r9d, [rdx+1]; int
0x14022a235  mov     r8d, r9d; int
0x14022a238  call    ?psoSpCreateSurface@@YAPEAU_SURFOBJ@@PEAU_SPRITESTATE@@KJJH@Z; psoSpCreateSurface(_SPRITESTATE *,ulong,long,long,int)
0x14022a23d  mov     rdx, rax
0x14022a240  test    rax, rax
0x14022a243  jz      loc_14022A415
0x14022a249  mov     ecx, [rbx+2Ch]
0x14022a24c  lea     rax, [rsi+28h]
0x14022a250  mov     [rsi], ecx
0x14022a252  mov     ecx, [rbx+34h]
0x14022a255  mov     [rsi+4], ecx
0x14022a258  mov     qword ptr [rsi+8], 28h ; '('
0x14022a260  mov     [rsi+10h], r15
0x14022a264  mov     ecx, [r14]
0x14022a267  mov     [rsi+18h], ecx
0x14022a26a  mov     ecx, [rbx+30h]
0x14022a26d  mov     [rsi+1Ch], ecx
0x14022a270  lea     rcx, [rbp+arg_0]
0x14022a274  mov     [rsi+20h], r15
0x14022a278  mov     [rbx+408h], rdx
0x14022a27f  mov     rdx, r14
0x14022a282  mov     [rbx+90h], rsi
0x14022a289  mov     [rbx+98h], rax
0x14022a290  call    cs:__imp_?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z; RGNOBJ::vSet(_RECTL const * const)
0x14022a297  nop     dword ptr [rax+rax+00h]
0x14022a29c  mov     rdx, [rbp+arg_0]
0x14022a2a0  lea     rcx, [rbx+370h]
0x14022a2a7  mov     r9d, 1
0x14022a2ad  mov     [rbx+368h], rdx
0x14022a2b4  mov     r8, r14
0x14022a2b7  call    cs:__imp_?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z; XCLIPOBJ::vSetup(REGION *,ERECTL const &,int)
0x14022a2be  nop     dword ptr [rax+rax+00h]
0x14022a2c3  mov     rcx, [rbp+arg_8]
0x14022a2c7  mov     [rbx+2C0h], rcx
0x14022a2ce  call    cs:__imp_?vStamp@REGION@@AEAAXXZ; REGION::vStamp(void)
0x14022a2d5  nop     dword ptr [rax+rax+00h]
0x14022a2da  mov     rax, [rbp+arg_10]
0x14022a2de  xor     r9d, r9d
0x14022a2e1  xor     r8d, r8d
0x14022a2e4  mov     [rbx+2C8h], rax
0x14022a2eb  xor     edx, edx
0x14022a2ed  xor     ecx, ecx
0x14022a2ef  call    cs:__imp_GreCreateRectRgn
0x14022a2f6  nop     dword ptr [rax+rax+00h]
0x14022a2fb  mov     [rbx+428h], rax
0x14022a302  mov     rax, [rdi+0AF8h]
0x14022a309  mov     [rbx+4B0h], rax
0x14022a310  mov     rax, [rdi+0AE8h]
0x14022a317  mov     [rbx+4B8h], rax
0x14022a31e  mov     rax, [rdi+0AF0h]
0x14022a325  mov     [rbx+4C0h], rax
0x14022a32c  mov     rax, [rdi+0B08h]
0x14022a333  mov     [rbx+4D0h], rax
0x14022a33a  mov     rax, [rdi+0B10h]
0x14022a341  mov     [rbx+4D8h], rax
0x14022a348  mov     rax, [rdi+0B18h]
0x14022a34f  mov     [rbx+4E0h], rax
0x14022a356  mov     rax, [rdi+0B30h]
0x14022a35d  mov     [rbx+4E8h], rax
0x14022a364  mov     rax, [rdi+0B70h]
0x14022a36b  mov     [rbx+4F0h], rax
0x14022a372  mov     rax, [rdi+0CC8h]
0x14022a379  mov     [rbx+4F8h], rax
0x14022a380  mov     rax, [rdi+0CB0h]
0x14022a387  mov     [rbx+500h], rax
0x14022a38e  mov     rax, [rdi+0CA8h]
0x14022a395  mov     [rbx+508h], rax
0x14022a39c  mov     rax, [rdi+0C98h]
0x14022a3a3  mov     [rbx+510h], rax
0x14022a3aa  mov     rax, [rdi+0CA0h]
0x14022a3b1  mov     [rbx+520h], rax
0x14022a3b8  mov     rax, [rdi+0BB8h]
0x14022a3bf  mov     [rbx+518h], rax
0x14022a3c6  mov     rax, [rdi+0D48h]
0x14022a3cd  mov     [rbx+528h], rax
0x14022a3d4  test    dword ptr [rdi+28h], 20000h
0x14022a3db  jz      short loc_14022A406
0x14022a3dd  mov     eax, 1
0x14022a3e2  mov     rbx, [rsp+30h+arg_18]
0x14022a3e7  add     rsp, 30h
0x14022a3eb  pop     r15
0x14022a3ed  pop     r14
0x14022a3ef  pop     rdi
0x14022a3f0  pop     rsi
0x14022a3f1  pop     rbp
0x14022a3f2  retn
0x14022a3f4  cmp     [rbx+88h], r15
0x14022a3fb  jz      loc_14022A1AF
0x14022a401  jmp     loc_14022A20E
0x14022a406  mov     rcx, rbx; struct _SPRITESTATE *
0x14022a409  call    ?vSpHook@@YAXPEAU_SPRITESTATE@@@Z; vSpHook(_SPRITESTATE *)
0x14022a40e  call    ?vSpComputeSpriteRanges@@YAXPEAU_SPRITESTATE@@W4vSpComputeSpriteRangesOptions@@@Z; vSpComputeSpriteRanges(_SPRITESTATE *,vSpComputeSpriteRangesOptions)
0x14022a413  jmp     short loc_14022A3DD
0x14022a415  mov     rcx, rsi
0x14022a418  call    cs:__imp_Win32FreePool
0x14022a41f  nop     dword ptr [rax+rax+00h]
0x14022a424  jmp     loc_14022A1AF
0x14022a429  call    cs:__imp_GreDeleteSemaphore
0x14022a430  nop     dword ptr [rax+rax+00h]
0x14022a435  jmp     loc_14022A1BC
0x14022a43a  call    cs:__imp_GreDeleteSemaphore
0x14022a441  nop     dword ptr [rax+rax+00h]
0x14022a446  jmp     loc_14022A1CC
```
