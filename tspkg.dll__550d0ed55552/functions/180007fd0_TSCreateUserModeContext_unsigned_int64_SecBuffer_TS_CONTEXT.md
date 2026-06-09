# TSCreateUserModeContext(unsigned __int64,_SecBuffer *,_TS_CONTEXT * *)

- ea: `0x180007fd0`
- end: `0x1800087db`
- name: `?TSCreateUserModeContext@@YAJ_KPEAU_SecBuffer@@PEAPEAU_TS_CONTEXT@@@Z`
- size: `2059`
- prototype: `__int64 __fastcall(unsigned __int64, struct _SecBuffer *, struct _TS_CONTEXT **)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180017e60`

## callees

- `0x1800032c0`
- `0x180003e00`
- `0x180003ea0`
- `0x180005ed0`
- `0x180007fd0`
- `0x180009db4`
- `0x18000c1a4`
- `0x1800162e4`
- `0x18001c63c`
- `0x18001d010`

## import_xrefs

- `SspiCli!SspiValidateAuthIdentity` at `0x1800082a1`
- `SspiCli!SspiValidateAuthIdentity` at `0x1800082a1`

## pseudocode

```c
__int64 __fastcall TSCreateUserModeContext(__int64 a1, struct _SecBuffer *a2, struct _TS_CONTEXT **a3)
{
  _BYTE *v4; // r12
  __int64 cbBuffer; // rax
  int *pvBuffer; // rsi
  char *v8; // rbx
  int v9; // edi
  int v10; // eax
  size_t v11; // r14
  __int64 v12; // r9
  WCHAR *v13; // r15
  char *v14; // r8
  char *v15; // rdx
  char *v16; // rcx
  __int64 v17; // r11
  char *v18; // rdi
  __int64 v19; // r10
  size_t v20; // r13
  USHORT v21; // ax
  char *v22; // r9
  char *v23; // r8
  struct _UNICODE_STRING *v24; // rdx
  _WORD *v25; // r15
  int v26; // eax
  __int64 v27; // rdx
  _BYTE *v28; // rax
  unsigned int v29; // eax
  size_t Length; // rdi
  _WORD *v31; // rax
  void *v32; // rdx
  char *v33; // rbx
  PWSTR v34; // rdx
  char *v35; // rbx
  size_t v36; // r8
  char *v37; // rcx
  PWSTR v38; // rdx
  unsigned int v39; // edx
  _WORD *v40; // rax
  unsigned int v41; // ecx
  char *v42; // rbx
  void *v43; // rdx
  size_t v44; // r8
  void *v45; // rdx
  char *v46; // rbx
  PWSTR Buffer; // rdx
  char *v48; // rbx
  size_t v49; // r8
  __int64 v50; // rcx
  void *v51; // rdx
  char *v52; // rcx
  __int64 v53; // rbx
  void *v54; // rax
  void *v55; // rax
  unsigned int v56; // eax
  _WORD *v57; // rdi
  __int64 v58; // rcx
  __int64 v59; // rax
  _WORD *v60; // r13
  __int64 v61; // rax
  bool v62; // zf
  unsigned int v63; // ebx
  __int64 v64; // rax
  _DWORD *v65; // rcx
  __int64 v66; // rax
  __int64 v67; // rsi
  __int64 v68; // rbx
  size_t v69; // r8
  __int64 v70; // rcx
  _BYTE *i; // rax
  unsigned int v72; // [rsp+30h] [rbp-D0h]
  USHORT v73; // [rsp+34h] [rbp-CCh]
  unsigned int v74; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v75; // [rsp+3Ch] [rbp-C4h]
  PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthData; // [rsp+40h] [rbp-C0h] BYREF
  void *v77; // [rsp+48h] [rbp-B8h]
  void *v78; // [rsp+50h] [rbp-B0h]
  void *v79; // [rsp+58h] [rbp-A8h]
  char *v80; // [rsp+60h] [rbp-A0h]
  char v81[8]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v82; // [rsp+78h] [rbp-88h]
  __int16 v83; // [rsp+7Ah] [rbp-86h]
  void *Src; // [rsp+80h] [rbp-80h]
  struct _UNICODE_STRING v85; // [rsp+88h] [rbp-78h] BYREF
  struct _UNICODE_STRING v86; // [rsp+98h] [rbp-68h] BYREF
  char *v87; // [rsp+B0h] [rbp-50h]
  size_t Size; // [rsp+B8h] [rbp-48h]
  char *v89; // [rsp+108h] [rbp+8h]
  int v90; // [rsp+110h] [rbp+10h]
  size_t v92; // [rsp+1B8h] [rbp+B8h] BYREF
  struct _TS_CONTEXT **v93; // [rsp+1C0h] [rbp+C0h]
  size_t v94; // [rsp+1C8h] [rbp+C8h]

  v93 = a3;
  v92 = 0;
  v72 = 0;
  v4 = 0;
  v74 = 0;
  AuthData = 0;
  memset_0(v81, 0, 0xE8u);
  cbBuffer = a2->cbBuffer;
  if ( (unsigned int)cbBuffer >= 0x54 )
  {
    pvBuffer = (int *)a2->pvBuffer;
    v8 = (char *)pvBuffer + cbBuffer;
    if ( (int *)((char *)pvBuffer + cbBuffer) < pvBuffer )
      return (unsigned int)-1073741811;
    v10 = TSAllocateContext((struct _TS_CONTEXT **)&v92, 1u);
    v11 = v92;
    v9 = v10;
    if ( v10 >= 0 )
    {
      *(_QWORD *)(v92 + 40) = *pvBuffer;
      *(_QWORD *)(v11 + 48) = pvBuffer[1];
      *(_QWORD *)(v11 + 56) = pvBuffer[2];
      *(_DWORD *)(v11 + 120) = pvBuffer[3];
      *(_QWORD *)(v11 + 132) = *(_QWORD *)(pvBuffer + 19);
      v12 = *((unsigned __int16 *)pvBuffer + 13);
      v13 = (WCHAR *)((char *)pvBuffer + (unsigned int)pvBuffer[7]);
      v14 = (char *)pvBuffer + (unsigned int)pvBuffer[5];
      v15 = (char *)pvBuffer + (unsigned int)pvBuffer[9];
      v16 = (char *)pvBuffer + (unsigned int)pvBuffer[10];
      v17 = *((unsigned __int16 *)pvBuffer + 9);
      v18 = (char *)pvBuffer + (unsigned int)pvBuffer[12];
      v19 = (unsigned int)pvBuffer[11];
      v20 = (unsigned int)pvBuffer[13];
      v73 = *((_WORD *)pvBuffer + 12);
      v85.Length = v73;
      LOWORD(v94) = *((_WORD *)pvBuffer + 8);
      v82 = v94;
      LOWORD(v92) = *((_WORD *)pvBuffer + 16);
      v86.Length = v92;
      v21 = *((_WORD *)pvBuffer + 17);
      v86.MaximumLength = v21;
      v85.MaximumLength = v12;
      v85.Buffer = v13;
      v83 = v17;
      v78 = v14;
      Src = v14;
      v77 = v15;
      v86.Buffer = (PWSTR)v15;
      LODWORD(Size) = v19;
      v79 = v16;
      v87 = v16;
      v90 = v20;
      v80 = v18;
      v89 = v18;
      if ( v73 <= (unsigned __int16)v12
        && (unsigned __int16)v94 <= (unsigned __int16)v17
        && (unsigned __int16)v92 <= v21
        && v13 >= (WCHAR *)pvBuffer )
      {
        v22 = (char *)v13 + v12;
        if ( v22 >= (char *)v13
          && v22 <= v8
          && v14 >= (char *)pvBuffer
          && &v14[v17] >= v14
          && &v14[v17] <= v8
          && v15 >= (char *)pvBuffer )
        {
          v23 = &v15[v21];
          if ( v23 >= v15 && v23 <= v8 && v16 >= (char *)pvBuffer )
          {
            v24 = (struct _UNICODE_STRING *)&v16[v19];
            if ( &v16[v19] >= v16
              && v24 <= (struct _UNICODE_STRING *)v8
              && v18 >= (char *)pvBuffer
              && &v18[v20] >= v18
              && &v18[v20] <= v8 )
            {
              v25 = 0;
              v75 = 0;
              if ( (_DWORD)v19 )
              {
                v39 = ((unsigned __int16)v94 + (unsigned __int16)v92 + v73 + 93) & 0xFFFFFFF8;
                v74 = v39 + v19;
                if ( v39 + (unsigned int)v19 >= v39 )
                {
                  v40 = TSAllocate(v39 + (unsigned int)v19);
                  if ( v40 )
                  {
                    v41 = (unsigned __int16)v92;
                    v42 = (char *)(v40 + 40);
                    v43 = v77;
                    v25 = v40;
                    v40[20] = v92;
                    *(_DWORD *)v40 = 13;
                    v9 = 0;
                    v40[21] = v41 + 2;
                    *((_QWORD *)v40 + 6) = 80;
                    memcpy_0(v40 + 40, v43, v41);
                    v44 = (unsigned __int16)v94;
                    v45 = v78;
                    v46 = &v42[(unsigned __int16)v25[21]];
                    v25[4] = v94;
                    v25[5] = v44 + 2;
                    *((_QWORD *)v25 + 2) = v46 - (char *)v25;
                    memcpy_0(v46, v45, v44);
                    Buffer = v85.Buffer;
                    v48 = &v46[(unsigned __int16)v25[5]];
                    v25[12] = v73;
                    v25[13] = v73 + 2;
                    *((_QWORD *)v25 + 4) = v48 - (char *)v25;
                    memcpy_0(v48, Buffer, v73);
                    v49 = (unsigned int)Size;
                    v50 = (unsigned __int16)v25[13] + 7LL;
                    *((_DWORD *)v25 + 15) = Size;
                    v51 = v79;
                    v52 = (char *)((unsigned __int64)&v48[v50] & 0xFFFFFFFFFFFFFFF8uLL);
                    *((_QWORD *)v25 + 8) = v52 - (char *)v25;
                    memcpy_0(v52, v51, v49);
                    v75 = v74;
                  }
                  else
                  {
                    v9 = -1073741670;
                  }
                }
                else
                {
                  v9 = -1073741675;
                }
                if ( v9 < 0 )
                  goto LABEL_79;
                v18 = v80;
              }
              else if ( !(_DWORD)v20 )
              {
                v26 = TSDecodeAuthIdFromCred(&v85, v24, &v86, (unsigned __int8 **)&AuthData, &v74);
                v4 = AuthData;
                v9 = v26;
                if ( v26 == -1073741637 )
                {
                  v72 = v74;
                }
                else
                {
                  if ( v26 < 0 )
                  {
                    v29 = v74;
                    goto LABEL_84;
                  }
                  if ( SspiValidateAuthIdentity(AuthData) >= 0 )
                  {
                    v72 = v74;
                  }
                  else
                  {
                    v27 = v74;
                    v28 = v4;
                    if ( v74 )
                    {
                      do
                      {
                        *v28++ = 0;
                        --v27;
                      }
                      while ( v27 );
                    }
                    TSFree(v4);
                    v4 = 0;
                    v72 = 0;
                  }
                }
                Length = v86.Length;
                v20 = v82;
                v75 = v86.Length + v82 + v85.Length + 70;
                v31 = TSAllocate(v75);
                v25 = v31;
                if ( !v31 )
                {
                  v9 = -1073741670;
LABEL_83:
                  v29 = v72;
LABEL_84:
                  if ( v4 )
                  {
                    v70 = v29;
                    for ( i = v4; v70; --v70 )
                      *i++ = 0;
                    TSFree(v4);
                  }
                  goto LABEL_89;
                }
                v32 = Src;
                v33 = (char *)(v31 + 32);
                *(_DWORD *)v31 = 2;
                v31[4] = v20;
                *((_QWORD *)v31 + 2) = 64;
                v31[5] = v20 + 2;
                memcpy_0(v31 + 32, v32, v20);
                v34 = v86.Buffer;
                v35 = &v33[(unsigned __int16)v25[5]];
                v25[20] = Length;
                v25[21] = Length + 2;
                *((_QWORD *)v25 + 6) = v35 - (char *)v25;
                memcpy_0(v35, v34, Length);
                v36 = v85.Length;
                v37 = &v35[(unsigned __int16)v25[21]];
                v25[12] = v85.Length;
                v38 = v85.Buffer;
                v25[13] = v36 + 2;
                *((_QWORD *)v25 + 4) = v37 - (char *)v25;
                memcpy_0(v37, v38, v36);
                LODWORD(v20) = v90;
                v18 = v89;
                if ( (*(_BYTE *)(v11 + 120) & 4) != 0 )
                  *(_DWORD *)v25 = 83;
              }
              if ( TSGlobalState == 1 )
              {
                v53 = ((__int64 (__fastcall *)(__int64))TSGlobalLsaFunctions->AllocatePrivateHeap)(232);
              }
              else
              {
                v54 = (void *)((__int64 (__fastcall *)(__int64))TSGlobalDllFunctions->AllocateHeap)(232);
                v53 = (__int64)v54;
                if ( v54 )
                {
                  memset_0(v54, 0, 0xE8u);
LABEL_55:
                  if ( !(_DWORD)v20 )
                  {
                    v56 = v75;
                    *(_QWORD *)(v53 + 152) = v25;
                    v25 = 0;
                    *(_DWORD *)(v53 + 160) = v56;
                    goto LABEL_63;
                  }
                  v55 = TSAllocate((unsigned int)v20);
                  *(_QWORD *)(v53 + 152) = v55;
                  if ( v55 )
                  {
                    memcpy_0(v55, v18, (unsigned int)v20);
                    *(_DWORD *)(v53 + 160) = v20;
LABEL_63:
                    v57 = 0;
                    *(_QWORD *)(v53 + 168) = v4;
                    v58 = -1;
                    *(_DWORD *)(v53 + 176) = v72;
                    v4 = 0;
                    *(_QWORD *)(v11 + 96) = v53;
                    v59 = (unsigned int)pvBuffer[17];
                    LODWORD(v94) = 0;
                    if ( (_DWORD)v59 )
                    {
                      v60 = (_WORD *)((char *)pvBuffer + v59);
                      v61 = -1;
                      do
                        v62 = v60[++v61] == 0;
                      while ( !v62 );
                      LODWORD(v92) = 2 * v61 + 2;
                      v63 = 2 * v61 + 34;
                    }
                    else
                    {
                      v63 = 32;
                      LODWORD(v92) = 0;
                      v60 = 0;
                    }
                    v64 = (unsigned int)pvBuffer[18];
                    if ( (_DWORD)v64 )
                    {
                      v57 = (_WORD *)((char *)pvBuffer + v64);
                      do
                        v62 = v57[++v58] == 0;
                      while ( !v62 );
                      LODWORD(v94) = 2 * v58 + 2;
                      v63 += v94;
                    }
                    *(_QWORD *)(v11 + 104) = TSAllocate(v63);
                    *(_DWORD *)(v11 + 112) = v63;
                    v65 = *(_DWORD **)(v11 + 104);
                    if ( v65 )
                    {
                      *v65 = pvBuffer[14];
                      *(_WORD *)(*(_QWORD *)(v11 + 104) + 4LL) = *((_WORD *)pvBuffer + 30);
                      *(_WORD *)(*(_QWORD *)(v11 + 104) + 6LL) = *((_WORD *)pvBuffer + 31);
                      *(_DWORD *)(*(_QWORD *)(v11 + 104) + 8LL) = pvBuffer[16];
                      v66 = *(_QWORD *)(v11 + 104);
                      v67 = v66 + 32;
                      if ( v60 )
                      {
                        v68 = (unsigned int)v92;
                        *(_QWORD *)(v66 + 16) = v67;
                        memcpy_0(*(void **)(*(_QWORD *)(v11 + 104) + 16LL), v60, (unsigned int)v68);
                        v67 += v68;
                      }
                      if ( v57 )
                      {
                        v69 = (unsigned int)v94;
                        *(_QWORD *)(*(_QWORD *)(v11 + 104) + 24LL) = v67;
                        memcpy_0(*(void **)(*(_QWORD *)(v11 + 104) + 24LL), v57, v69);
                      }
                      *(_QWORD *)(v11 + 8) = a1;
                      *v93 = (struct _TS_CONTEXT *)v11;
                      v11 = 0;
                      v9 = 0;
                    }
                    else
                    {
                      v9 = -1073741670;
                    }
                    goto LABEL_79;
                  }
                  if ( TSGlobalState == 1 )
                    ((void (__fastcall *)(__int64))TSGlobalLsaFunctions->FreePrivateHeap)(v53);
                  else
                    ((void (__fastcall *)(__int64))TSGlobalDllFunctions->FreeHeap)(v53);
                  v9 = -1073741670;
LABEL_79:
                  if ( v25 )
                  {
                    if ( TSGlobalState == 1 )
                      ((void (__fastcall *)(_WORD *))TSGlobalLsaFunctions->FreePrivateHeap)(v25);
                    else
                      ((void (__fastcall *)(_WORD *))TSGlobalDllFunctions->FreeHeap)(v25);
                  }
                  goto LABEL_83;
                }
              }
              if ( !v53 )
              {
                v9 = -1073741670;
                goto LABEL_79;
              }
              goto LABEL_55;
            }
          }
        }
      }
      v9 = -1073741595;
    }
LABEL_89:
    if ( v11 )
      TSDereferenceContext((struct _TS_CONTEXT *)v11);
    return (unsigned int)v9;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_DD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_db1a68f5ebef3d020188f602ddce2ab8_Traceguids,
      (unsigned int)cbBuffer,
      84);
  return 3221225485LL;
}

```

## disassembly

```asm
0x180007fd0  mov     [rsp-8+arg_10], r8
0x180007fd5  mov     [rsp-8+arg_0], rcx
0x180007fda  push    rbp
0x180007fdb  push    rsi
0x180007fdc  push    rdi
0x180007fdd  push    r12
0x180007fdf  lea     rbp, [rsp-88h]
0x180007fe7  sub     rsp, 188h
0x180007fee  xor     eax, eax
0x180007ff0  mov     [rbp+0A0h+arg_8], 0
0x180007ffb  mov     rsi, rdx
0x180007ffe  mov     [rsp+1A0h+var_170], eax
0x180008002  xor     r12d, r12d
0x180008005  mov     [rsp+1A0h+var_168], eax
0x180008009  xor     edx, edx; Val
0x18000800b  mov     [rsp+1A0h+AuthData], r12
0x180008010  mov     r8d, 0E8h; Size
0x180008016  lea     rcx, [rsp+1A0h+var_130]; void *
0x18000801b  call    memset_0
0x180008020  mov     eax, [rsi]
0x180008022  cmp     eax, 54h ; 'T'
0x180008025  jnb     short loc_180008072
0x180008027  mov     rcx, cs:WPP_GLOBAL_Control
0x18000802e  lea     rdx, WPP_GLOBAL_Control
0x180008035  cmp     rcx, rdx
0x180008038  jz      short loc_180008060
0x18000803a  test    byte ptr [rcx+1Ch], 1
0x18000803e  jz      short loc_180008060
0x180008040  mov     rcx, [rcx+10h]
0x180008044  lea     r8, WPP_db1a68f5ebef3d020188f602ddce2ab8_Traceguids
0x18000804b  mov     edx, 0Ah
0x180008050  mov     dword ptr [rsp+1A0h+var_180], 54h ; 'T'
0x180008058  mov     r9d, eax
0x18000805b  call    WPP_SF_DD
0x180008060  mov     eax, 0C000000Dh
0x180008065  add     rsp, 188h
0x18000806c  pop     r12
0x18000806e  pop     rdi
0x18000806f  pop     rsi
0x180008070  pop     rbp
0x180008071  retn
0x180008072  mov     rsi, [rsi+8]
0x180008076  mov     [rsp+1A0h+var_20], rbx
0x18000807e  lea     rbx, [rsi+rax]
0x180008082  cmp     rbx, rsi
0x180008085  jnb     short loc_180008091
0x180008087  mov     edi, 0C000000Dh
0x18000808c  jmp     loc_1800087C4
0x180008091  mov     [rsp+1A0h+var_28], r13
0x180008099  lea     rcx, [rbp+0A0h+arg_8]; struct _TS_CONTEXT **
0x1800080a0  mov     [rsp+1A0h+var_30], r14
0x1800080a8  mov     dl, 1; unsigned __int8
0x1800080aa  mov     [rsp+1A0h+var_38], r15
0x1800080b2  call    ?TSAllocateContext@@YAJPEAPEAU_TS_CONTEXT@@E@Z; TSAllocateContext(_TS_CONTEXT * *,uchar)
0x1800080b7  mov     r14, [rbp+0A0h+arg_8]
0x1800080be  mov     edi, eax
0x1800080c0  test    eax, eax
0x1800080c2  js      loc_18000879F
0x1800080c8  movsxd  rax, dword ptr [rsi]
0x1800080cb  mov     [r14+28h], rax
0x1800080cf  movsxd  rax, dword ptr [rsi+4]
0x1800080d3  mov     [r14+30h], rax
0x1800080d7  movsxd  rax, dword ptr [rsi+8]
0x1800080db  mov     [r14+38h], rax
0x1800080df  mov     eax, [rsi+0Ch]
0x1800080e2  mov     [r14+78h], eax
0x1800080e6  mov     rax, [rsi+4Ch]
0x1800080ea  mov     [r14+84h], rax
0x1800080f1  movzx   eax, word ptr [rsi+18h]
0x1800080f5  movzx   r9d, word ptr [rsi+1Ah]
0x1800080fa  mov     r15d, [rsi+1Ch]
0x1800080fe  mov     r8d, [rsi+14h]
0x180008102  add     r15, rsi
0x180008105  mov     edx, [rsi+24h]
0x180008108  add     r8, rsi
0x18000810b  mov     ecx, [rsi+28h]
0x18000810e  add     rdx, rsi
0x180008111  mov     edi, [rsi+30h]
0x180008114  add     rcx, rsi
0x180008117  movzx   r11d, word ptr [rsi+12h]
0x18000811c  add     rdi, rsi
0x18000811f  mov     r10d, [rsi+2Ch]
0x180008123  mov     r13d, [rsi+34h]
0x180008127  mov     [rsp+1A0h+var_16C], ax
0x18000812c  mov     [rbp+0A0h+var_118.Length], ax
0x180008130  movzx   eax, word ptr [rsi+10h]
0x180008134  mov     word ptr [rbp+0A0h+arg_18], ax
0x18000813b  mov     [rsp+1A0h+var_128], ax
0x180008140  movzx   eax, word ptr [rsi+20h]
0x180008144  mov     word ptr [rbp+0A0h+arg_8], ax
0x18000814b  mov     [rbp+0A0h+var_108.Length], ax
0x18000814f  movzx   eax, word ptr [rsi+22h]
0x180008153  mov     [rbp+0A0h+var_108.MaximumLength], ax
0x180008157  mov     [rbp+0A0h+var_118.MaximumLength], r9w
0x18000815c  mov     [rbp+0A0h+var_118.Buffer], r15
0x180008160  mov     [rsp+1A0h+var_126], r11w
0x180008166  mov     [rsp+1A0h+var_150], r8
0x18000816b  mov     [rbp+0A0h+Src], r8
0x18000816f  mov     [rsp+1A0h+var_158], rdx
0x180008174  mov     [rbp+0A0h+var_108.Buffer], rdx
0x180008178  mov     dword ptr [rbp+0A0h+Size], r10d
0x18000817c  mov     [rsp+1A0h+var_148], rcx
0x180008181  mov     [rbp+0A0h+var_F0], rcx
0x180008185  mov     [rbp+0A0h+var_90], r13d
0x180008189  mov     [rsp+1A0h+var_140], rdi
0x18000818e  mov     [rbp+0A0h+var_98], rdi
0x180008192  cmp     [rsp+1A0h+var_16C], r9w
0x180008198  ja      loc_18000879A
0x18000819e  cmp     word ptr [rbp+0A0h+arg_18], r11w
0x1800081a6  ja      loc_18000879A
0x1800081ac  cmp     word ptr [rbp+0A0h+arg_8], ax
0x1800081b3  ja      loc_18000879A
0x1800081b9  cmp     r15, rsi
0x1800081bc  jb      loc_18000879A
0x1800081c2  add     r9, r15
0x1800081c5  cmp     r9, r15
0x1800081c8  jb      loc_18000879A
0x1800081ce  cmp     r9, rbx
0x1800081d1  ja      loc_18000879A
0x1800081d7  cmp     r8, rsi
0x1800081da  jb      loc_18000879A
0x1800081e0  lea     r9, [r8+r11]
0x1800081e4  cmp     r9, r8
0x1800081e7  jb      loc_18000879A
0x1800081ed  cmp     r9, rbx
0x1800081f0  ja      loc_18000879A
0x1800081f6  cmp     rdx, rsi
0x1800081f9  jb      loc_18000879A
0x1800081ff  movzx   r8d, ax
0x180008203  add     r8, rdx
0x180008206  cmp     r8, rdx
0x180008209  jb      loc_18000879A
0x18000820f  cmp     r8, rbx
0x180008212  ja      loc_18000879A
0x180008218  cmp     rcx, rsi
0x18000821b  jb      loc_18000879A
0x180008221  lea     rdx, [rcx+r10]; struct _UNICODE_STRING *
0x180008225  cmp     rdx, rcx
0x180008228  jb      loc_18000879A
0x18000822e  cmp     rdx, rbx
0x180008231  ja      loc_18000879A
0x180008237  cmp     rdi, rsi
0x18000823a  jb      loc_18000879A
0x180008240  lea     rcx, [rdi+r13]
0x180008244  cmp     rcx, rdi
0x180008247  jb      loc_18000879A
0x18000824d  cmp     rcx, rbx
0x180008250  ja      loc_18000879A
0x180008256  xor     r15d, r15d
0x180008259  mov     [rsp+1A0h+var_164], r12d
0x18000825e  test    r10d, r10d
0x180008261  jnz     loc_1800083D9
0x180008267  test    r13d, r13d
0x18000826a  jnz     loc_180008508
0x180008270  lea     rax, [rsp+1A0h+var_168]
0x180008275  lea     r9, [rsp+1A0h+AuthData]; unsigned __int8 **
0x18000827a  mov     [rsp+1A0h+var_180], rax; unsigned int *
0x18000827f  lea     r8, [rbp+0A0h+var_108]; struct _UNICODE_STRING *
0x180008283  lea     rcx, [rbp+0A0h+var_118]; struct _UNICODE_STRING *
0x180008287  call    ?TSDecodeAuthIdFromCred@@YAJPEAU_UNICODE_STRING@@00PEAPEAEPEAK@Z; TSDecodeAuthIdFromCred(_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,uchar * *,ulong *)
0x18000828c  mov     r12, [rsp+1A0h+AuthData]
0x180008291  mov     edi, eax
0x180008293  cmp     eax, 0C00000BBh
0x180008298  jz      short loc_1800082F2
0x18000829a  test    eax, eax
0x18000829c  js      short loc_1800082E9
0x18000829e  mov     rcx, r12; AuthData
0x1800082a1  call    cs:__imp_SspiValidateAuthIdentity
0x1800082a7  test    eax, eax
0x1800082a9  jns     short loc_1800082DF
0x1800082ab  mov     edx, [rsp+1A0h+var_168]
0x1800082af  mov     rax, r12
0x1800082b2  test    rdx, rdx
0x1800082b5  jz      short loc_1800082CD
0x1800082b7  nop     word ptr [rax+rax+00000000h]
0x1800082c0  mov     [rax], r15b
0x1800082c3  lea     rax, [rax+1]
0x1800082c7  sub     rdx, 1
0x1800082cb  jnz     short loc_1800082C0
0x1800082cd  mov     rcx, r12; void *
0x1800082d0  call    ?TSFree@@YAXPEAX@Z; TSFree(void *)
0x1800082d5  xor     r12d, r12d
0x1800082d8  mov     [rsp+1A0h+var_170], r12d
0x1800082dd  jmp     short loc_1800082FA
0x1800082df  mov     ebx, [rsp+1A0h+var_168]
0x1800082e3  mov     [rsp+1A0h+var_170], ebx
0x1800082e7  jmp     short loc_1800082FA
0x1800082e9  mov     eax, [rsp+1A0h+var_168]
0x1800082ed  jmp     loc_180008774
0x1800082f2  mov     eax, [rsp+1A0h+var_168]
0x1800082f6  mov     [rsp+1A0h+var_170], eax
0x1800082fa  movzx   eax, [rbp+0A0h+var_118.Length]
0x1800082fe  movzx   edi, [rbp+0A0h+var_108.Length]
0x180008302  add     eax, 46h ; 'F'
0x180008305  movzx   r13d, [rsp+1A0h+var_128]
0x18000830b  lea     ecx, [rdi+r13]
0x18000830f  add     eax, ecx
0x180008311  mov     ecx, eax; Size
0x180008313  mov     [rsp+1A0h+var_164], eax
0x180008317  call    ?TSAllocate@@YAPEAX_K@Z; TSAllocate(unsigned __int64)
0x18000831c  mov     r15, rax
0x18000831f  test    rax, rax
0x180008322  jnz     short loc_18000832E
0x180008324  mov     edi, 0C000009Ah
0x180008329  jmp     loc_180008770
0x18000832e  mov     rdx, [rbp+0A0h+Src]; Src
0x180008332  lea     rbx, [rax+40h]
0x180008336  mov     dword ptr [rax], 2
0x18000833c  mov     rcx, rbx; void *
0x18000833f  mov     [rax+8], r13w
0x180008344  mov     r8, r13; Size
0x180008347  lea     eax, [r13+2]
0x18000834b  mov     qword ptr [r15+10h], 40h ; '@'
0x180008353  mov     [r15+0Ah], ax
0x180008358  call    memcpy_0
0x18000835d  movzx   eax, word ptr [r15+0Ah]
0x180008362  mov     r8, rdi; Size
0x180008365  mov     rdx, [rbp+0A0h+var_108.Buffer]; Src
0x180008369  add     rbx, rax
0x18000836c  lea     eax, [rdi+2]
0x18000836f  mov     [r15+28h], di
0x180008374  mov     [r15+2Ah], ax
0x180008379  mov     rcx, rbx; void *
0x18000837c  mov     rax, rbx
0x18000837f  sub     rax, r15
0x180008382  mov     [r15+30h], rax
0x180008386  call    memcpy_0
0x18000838b  movzx   edx, [rbp+0A0h+var_118.Length]
0x18000838f  movzx   ecx, word ptr [r15+2Ah]
0x180008394  mov     r8d, edx; Size
0x180008397  add     rcx, rbx; void *
0x18000839a  mov     [r15+18h], dx
0x18000839f  lea     eax, [rdx+2]
0x1800083a2  mov     rdx, [rbp+0A0h+var_118.Buffer]; Src
0x1800083a6  mov     [r15+1Ah], ax
0x1800083ab  mov     rax, rcx
0x1800083ae  sub     rax, r15
0x1800083b1  mov     [r15+20h], rax
0x1800083b5  call    memcpy_0
0x1800083ba  test    byte ptr [r14+78h], 4
0x1800083bf  mov     r13d, [rbp+0A0h+var_90]
0x1800083c3  mov     rdi, [rbp+0A0h+var_98]
0x1800083c7  jz      loc_180008508
0x1800083cd  mov     dword ptr [r15], 53h ; 'S'
0x1800083d4  jmp     loc_180008508
0x1800083d9  movzx   eax, word ptr [rbp+0A0h+arg_18]
0x1800083e0  movzx   ecx, word ptr [rbp+0A0h+arg_8]
0x1800083e7  movzx   edx, [rsp+1A0h+var_16C]
0x1800083ec  add     ecx, eax
0x1800083ee  add     edx, 5Dh ; ']'
0x1800083f1  add     edx, ecx
0x1800083f3  and     edx, 0FFFFFFF8h
0x1800083f6  lea     eax, [rdx+r10]
0x1800083fa  mov     [rsp+1A0h+var_168], eax
0x1800083fe  cmp     eax, edx
0x180008400  jnb     short loc_18000840C
0x180008402  mov     edi, 0C0000095h
0x180008407  jmp     loc_1800084FB
0x18000840c  mov     ecx, eax; Size
0x18000840e  call    ?TSAllocate@@YAPEAX_K@Z; TSAllocate(unsigned __int64)
0x180008413  test    rax, rax
0x180008416  jnz     short loc_180008422
0x180008418  mov     edi, 0C000009Ah
0x18000841d  jmp     loc_1800084FB
0x180008422  movzx   ecx, word ptr [rbp+0A0h+arg_8]
0x180008429  lea     rbx, [rax+50h]
0x18000842d  mov     rdx, [rsp+1A0h+var_158]; Src
0x180008432  mov     r15, rax
0x180008435  mov     [rax+28h], cx
0x180008439  mov     r8d, ecx; Size
0x18000843c  mov     dword ptr [rax], 0Dh
0x180008442  xor     edi, edi
0x180008444  lea     eax, [rcx+2]
0x180008447  mov     rcx, rbx; void *
0x18000844a  mov     [r15+2Ah], ax
0x18000844f  mov     qword ptr [r15+30h], 50h ; 'P'
0x180008457  call    memcpy_0
0x18000845c  movzx   ecx, word ptr [rbp+0A0h+arg_18]
0x180008463  movzx   eax, word ptr [r15+2Ah]
0x180008468  mov     r8d, ecx; Size
0x18000846b  mov     rdx, [rsp+1A0h+var_150]; Src
0x180008470  add     rbx, rax
0x180008473  mov     [r15+8], cx
0x180008478  lea     eax, [rcx+2]
0x18000847b  mov     rcx, rbx; void *
0x18000847e  mov     [r15+0Ah], ax
0x180008483  mov     rax, rbx
0x180008486  sub     rax, r15
0x180008489  mov     [r15+10h], rax
0x18000848d  call    memcpy_0
0x180008492  movzx   ecx, [rsp+1A0h+var_16C]
0x180008497  movzx   eax, word ptr [r15+0Ah]
0x18000849c  mov     r8d, ecx; Size
0x18000849f  mov     rdx, [rbp+0A0h+var_118.Buffer]; Src
0x1800084a3  add     rbx, rax
0x1800084a6  mov     [r15+18h], cx
0x1800084ab  lea     eax, [rcx+2]
0x1800084ae  mov     rcx, rbx; void *
0x1800084b1  mov     [r15+1Ah], ax
0x1800084b6  mov     rax, rbx
  ... truncated ...
```
