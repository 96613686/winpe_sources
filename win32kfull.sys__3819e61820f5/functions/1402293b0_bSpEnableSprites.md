# bSpEnableSprites

- ea: `0x1402293b0`
- end: `0x14022978e`
- name: `bSpEnableSprites`
- size: `990`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1401a3ddc`
- `0x1402293b0`
- `0x140229794`
- `0x14030a678`

## import_xrefs

- `ntoskrnl!RtlInitializeBitMap` at `0x140229487`
- `ntoskrnl!RtlInitializeBitMap` at `0x140229487`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14022951e`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14022952e`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14022953e`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14022951e`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14022952e`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14022953e`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x1402295d3`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x1402295d3`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x1402295fa`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x1402295fa`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x1402294aa`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x1402294ba`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x1402294ca`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x1402294aa`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x1402294ba`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x1402294ca`
- `win32kbase!GreInitializePushLock` at `0x14022949a`
- `win32kbase!GreInitializePushLock` at `0x14022949a`
- `win32kbase!GreCreateSemaphore` at `0x14022944b`
- `win32kbase!GreCreateSemaphore` at `0x140229462`
- `win32kbase!GreCreateSemaphore` at `0x14022944b`
- `win32kbase!GreCreateSemaphore` at `0x140229462`
- `win32kbase!?vStamp@REGION@@AEAAXXZ` at `0x140229611`
- `win32kbase!?vStamp@REGION@@AEAAXXZ` at `0x140229611`
- `win32kbase!GreDeleteSemaphore` at `0x14022976c`
- `win32kbase!GreDeleteSemaphore` at `0x14022977d`
- `win32kbase!GreDeleteSemaphore` at `0x14022976c`
- `win32kbase!GreDeleteSemaphore` at `0x14022977d`
- `win32kbase!GreCreateRectRgn` at `0x140229632`
- `win32kbase!GreCreateRectRgn` at `0x140229632`
- `win32kbase!Win32AllocPoolZInit` at `0x14022955b`
- `win32kbase!Win32AllocPoolZInit` at `0x14022955b`
- `win32kbase!Win32FreePool` at `0x14022975b`
- `win32kbase!Win32FreePool` at `0x14022975b`

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
  LODWORD(v2) = *(_DWORD *)(v5 + 0x88);
  *(_DWORD *)(v3 + 92) = v2;
  *(_DWORD *)(v3 + 104) = v6;
  *(_DWORD *)(v3 + 100) = v2;
  *(_DWORD *)(v3 + 112) = **(_DWORD **)(*(_QWORD *)(v5 + 152) + 112LL)
                        | *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v5 + 152) + 112LL) + 8LL);
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
0x1402293b0  mov     [rsp-28h+arg_18], rbx
0x1402293b5  push    rbp
0x1402293b6  push    rsi
0x1402293b7  push    rdi
0x1402293b8  push    r14
0x1402293ba  push    r15
0x1402293bc  mov     rbp, rsp
0x1402293bf  sub     rsp, 30h
0x1402293c3  mov     eax, [rcx+28h]
0x1402293c6  mov     rdi, rcx
0x1402293c9  test    al, 1
0x1402293cb  jz      loc_140229720
0x1402293d1  mov     rax, [rcx+9F0h]
0x1402293d8  lea     rbx, [rcx+50h]
0x1402293dc  mov     [rbx], rcx
0x1402293df  lea     r14, [rbx+28h]
0x1402293e3  lea     rdx, [rax+18h]
0x1402293e7  neg     rax
0x1402293ea  sbb     r8, r8
0x1402293ed  and     r8, rdx
0x1402293f0  lea     rax, [r8-18h]
0x1402293f4  neg     rax
0x1402293f7  sbb     rcx, rcx
0x1402293fa  xor     r15d, r15d
0x1402293fd  and     rcx, r8
0x140229400  mov     [rbx+20h], rcx
0x140229404  mov     eax, [r8+48h]
0x140229408  mov     [rbx+6Ch], eax
0x14022940b  movzx   ecx, word ptr [r8+4Ch]
0x140229410  mov     [rbx+60h], ecx
0x140229413  mov     eax, [r8+88h]
0x14022941a  mov     [rbx+5Ch], eax
0x14022941d  mov     [rbx+68h], ecx
0x140229420  mov     [rbx+64h], eax
0x140229423  mov     rax, [r8+98h]
0x14022942a  mov     rcx, [rax+70h]
0x14022942e  mov     edx, [rcx+8]
0x140229431  or      edx, [rcx]
0x140229433  mov     [rbx+70h], edx
0x140229436  mov     [r14], r15d
0x140229439  mov     eax, [r8+20h]
0x14022943d  mov     [rbx+30h], eax
0x140229440  mov     [rbx+2Ch], r15d
0x140229444  mov     eax, [r8+24h]
0x140229448  mov     [rbx+34h], eax
0x14022944b  call    cs:__imp_GreCreateSemaphore
0x140229452  nop     dword ptr [rax+rax+00h]
0x140229457  mov     [rbx+78h], rax
0x14022945b  mov     [rbx+80h], r15b
0x140229462  call    cs:__imp_GreCreateSemaphore
0x140229469  nop     dword ptr [rax+rax+00h]
0x14022946e  lea     rdx, [rbx+2B0h]; BitMapBuffer
0x140229475  mov     [rbx+88h], rax
0x14022947c  lea     rcx, [rbx+2A0h]; BitMapHeader
0x140229483  lea     r8d, [r15+40h]; SizeOfBitMap
0x140229487  call    cs:__imp_RtlInitializeBitMap
0x14022948e  nop     dword ptr [rax+rax+00h]
0x140229493  lea     rcx, [rbx+2B8h]
0x14022949a  call    cs:__imp_?GreInitializePushLock@@YAXPEAVW32_PUSH_LOCK@@@Z; GreInitializePushLock(W32_PUSH_LOCK *)
0x1402294a1  nop     dword ptr [rax+rax+00h]
0x1402294a6  lea     rcx, [rbp+arg_8]
0x1402294aa  call    cs:__imp_??0RGNMEMOBJ@@QEAA@XZ; RGNMEMOBJ::RGNMEMOBJ(void)
0x1402294b1  nop     dword ptr [rax+rax+00h]
0x1402294b6  lea     rcx, [rbp+arg_10]
0x1402294ba  call    cs:__imp_??0RGNMEMOBJ@@QEAA@XZ; RGNMEMOBJ::RGNMEMOBJ(void)
0x1402294c1  nop     dword ptr [rax+rax+00h]
0x1402294c6  lea     rcx, [rbp+arg_0]
0x1402294ca  call    cs:__imp_??0RGNMEMOBJ@@QEAA@XZ; RGNMEMOBJ::RGNMEMOBJ(void)
0x1402294d1  nop     dword ptr [rax+rax+00h]
0x1402294d6  cmp     [rbp+arg_8], r15
0x1402294da  jz      short loc_1402294F2
0x1402294dc  cmp     [rbp+arg_10], r15
0x1402294e0  jz      short loc_1402294F2
0x1402294e2  cmp     [rbp+arg_0], r15
0x1402294e6  jz      short loc_1402294F2
0x1402294e8  cmp     [rbx+78h], r15
0x1402294ec  jnz     loc_140229737
0x1402294f2  mov     rcx, [rbx+78h]
0x1402294f6  test    rcx, rcx
0x1402294f9  jnz     loc_14022976C
0x1402294ff  mov     rcx, [rbx+88h]
0x140229506  test    rcx, rcx
0x140229509  jnz     loc_14022977D
0x14022950f  lea     rcx, [rbp+arg_8]
0x140229513  mov     [rbx+78h], r15
0x140229517  mov     [rbx+88h], r15
0x14022951e  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x140229525  nop     dword ptr [rax+rax+00h]
0x14022952a  lea     rcx, [rbp+arg_10]
0x14022952e  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x140229535  nop     dword ptr [rax+rax+00h]
0x14022953a  lea     rcx, [rbp+arg_0]
0x14022953e  call    cs:__imp_?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ; RGNOBJ::vDeleteRGNOBJ(void)
0x140229545  nop     dword ptr [rax+rax+00h]
0x14022954a  xor     eax, eax
0x14022954c  jmp     loc_140229725
0x140229551  mov     edx, 72707347h
0x140229556  mov     ecx, 28h ; '('
0x14022955b  call    cs:__imp_Win32AllocPoolZInit
0x140229562  nop     dword ptr [rax+rax+00h]
0x140229567  mov     rsi, rax
0x14022956a  test    rax, rax
0x14022956d  jz      short loc_1402294F2
0x14022956f  xor     edx, edx; unsigned int
0x140229571  mov     rcx, rbx; struct _SPRITESTATE *
0x140229574  lea     r9d, [rdx+1]; int
0x140229578  mov     r8d, r9d; int
0x14022957b  call    ?psoSpCreateSurface@@YAPEAU_SURFOBJ@@PEAU_SPRITESTATE@@KJJH@Z; psoSpCreateSurface(_SPRITESTATE *,ulong,long,long,int)
0x140229580  mov     rdx, rax
0x140229583  test    rax, rax
0x140229586  jz      loc_140229758
0x14022958c  mov     ecx, [rbx+2Ch]
0x14022958f  lea     rax, [rsi+28h]
0x140229593  mov     [rsi], ecx
0x140229595  mov     ecx, [rbx+34h]
0x140229598  mov     [rsi+4], ecx
0x14022959b  mov     qword ptr [rsi+8], 28h ; '('
0x1402295a3  mov     [rsi+10h], r15
0x1402295a7  mov     ecx, [r14]
0x1402295aa  mov     [rsi+18h], ecx
0x1402295ad  mov     ecx, [rbx+30h]
0x1402295b0  mov     [rsi+1Ch], ecx
0x1402295b3  lea     rcx, [rbp+arg_0]
0x1402295b7  mov     [rsi+20h], r15
0x1402295bb  mov     [rbx+408h], rdx
0x1402295c2  mov     rdx, r14
0x1402295c5  mov     [rbx+90h], rsi
0x1402295cc  mov     [rbx+98h], rax
0x1402295d3  call    cs:__imp_?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z; RGNOBJ::vSet(_RECTL const * const)
0x1402295da  nop     dword ptr [rax+rax+00h]
0x1402295df  mov     rdx, [rbp+arg_0]
0x1402295e3  lea     rcx, [rbx+370h]
0x1402295ea  mov     r9d, 1
0x1402295f0  mov     [rbx+368h], rdx
0x1402295f7  mov     r8, r14
0x1402295fa  call    cs:__imp_?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z; XCLIPOBJ::vSetup(REGION *,ERECTL const &,int)
0x140229601  nop     dword ptr [rax+rax+00h]
0x140229606  mov     rcx, [rbp+arg_8]
0x14022960a  mov     [rbx+2C0h], rcx
0x140229611  call    cs:__imp_?vStamp@REGION@@AEAAXXZ; REGION::vStamp(void)
0x140229618  nop     dword ptr [rax+rax+00h]
0x14022961d  mov     rax, [rbp+arg_10]
0x140229621  xor     r9d, r9d
0x140229624  xor     r8d, r8d
0x140229627  mov     [rbx+2C8h], rax
0x14022962e  xor     edx, edx
0x140229630  xor     ecx, ecx
0x140229632  call    cs:__imp_GreCreateRectRgn
0x140229639  nop     dword ptr [rax+rax+00h]
0x14022963e  mov     [rbx+428h], rax
0x140229645  mov     rax, [rdi+0AF8h]
0x14022964c  mov     [rbx+4B0h], rax
0x140229653  mov     rax, [rdi+0AE8h]
0x14022965a  mov     [rbx+4B8h], rax
0x140229661  mov     rax, [rdi+0AF0h]
0x140229668  mov     [rbx+4C0h], rax
0x14022966f  mov     rax, [rdi+0B08h]
0x140229676  mov     [rbx+4D0h], rax
0x14022967d  mov     rax, [rdi+0B10h]
0x140229684  mov     [rbx+4D8h], rax
0x14022968b  mov     rax, [rdi+0B18h]
0x140229692  mov     [rbx+4E0h], rax
0x140229699  mov     rax, [rdi+0B30h]
0x1402296a0  mov     [rbx+4E8h], rax
0x1402296a7  mov     rax, [rdi+0B70h]
0x1402296ae  mov     [rbx+4F0h], rax
0x1402296b5  mov     rax, [rdi+0CC8h]
0x1402296bc  mov     [rbx+4F8h], rax
0x1402296c3  mov     rax, [rdi+0CB0h]
0x1402296ca  mov     [rbx+500h], rax
0x1402296d1  mov     rax, [rdi+0CA8h]
0x1402296d8  mov     [rbx+508h], rax
0x1402296df  mov     rax, [rdi+0C98h]
0x1402296e6  mov     [rbx+510h], rax
0x1402296ed  mov     rax, [rdi+0CA0h]
0x1402296f4  mov     [rbx+520h], rax
0x1402296fb  mov     rax, [rdi+0BB8h]
0x140229702  mov     [rbx+518h], rax
0x140229709  mov     rax, [rdi+0D48h]
0x140229710  mov     [rbx+528h], rax
0x140229717  test    dword ptr [rdi+28h], 20000h
0x14022971e  jz      short loc_140229749
0x140229720  mov     eax, 1
0x140229725  mov     rbx, [rsp+30h+arg_18]
0x14022972a  add     rsp, 30h
0x14022972e  pop     r15
0x140229730  pop     r14
0x140229732  pop     rdi
0x140229733  pop     rsi
0x140229734  pop     rbp
0x140229735  retn
0x140229737  cmp     [rbx+88h], r15
0x14022973e  jz      loc_1402294F2
0x140229744  jmp     loc_140229551
0x140229749  mov     rcx, rbx; struct _SPRITESTATE *
0x14022974c  call    ?vSpHook@@YAXPEAU_SPRITESTATE@@@Z; vSpHook(_SPRITESTATE *)
0x140229751  call    ?vSpComputeSpriteRanges@@YAXPEAU_SPRITESTATE@@W4vSpComputeSpriteRangesOptions@@@Z; vSpComputeSpriteRanges(_SPRITESTATE *,vSpComputeSpriteRangesOptions)
0x140229756  jmp     short loc_140229720
0x140229758  mov     rcx, rsi
0x14022975b  call    cs:__imp_Win32FreePool
0x140229762  nop     dword ptr [rax+rax+00h]
0x140229767  jmp     loc_1402294F2
0x14022976c  call    cs:__imp_GreDeleteSemaphore
0x140229773  nop     dword ptr [rax+rax+00h]
0x140229778  jmp     loc_1402294FF
0x14022977d  call    cs:__imp_GreDeleteSemaphore
0x140229784  nop     dword ptr [rax+rax+00h]
0x140229789  jmp     loc_14022950F
```
