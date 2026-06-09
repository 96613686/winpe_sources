# mciSendCommandA

- ea: `0x180011610`
- end: `0x180011e8a`
- name: `mciSendCommandA`
- size: `2170`
- prototype: `MCIERROR __stdcall(MCIDEVICEID mciId, UINT uMsg, DWORD_PTR dwParam1, DWORD_PTR dwParam2)`
- caller_count: `0`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180009a90`
- `0x18000a264`
- `0x18000b1f8`
- `0x18000b6d4`
- `0x18000c990`
- `0x18000d470`
- `0x18000f99c`
- `0x180010f8c`
- `0x180010fd8`
- `0x1800110cc`
- `0x180011124`
- `0x180011610`
- `0x180012a50`
- `0x180012ed0`
- `0x180015d50`
- `0x180015ddc`
- `0x18001a408`
- `0x18001a811`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011aca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011b6b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011c5b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011cc6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011cdc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011e26`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011e42`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011e5e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011aca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011b6b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011c5b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011cc6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011cdc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011e26`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011e42`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011e5e`

## pseudocode

```c
MCIERROR __stdcall mciSendCommandA(MCIDEVICEID mciId, UINT uMsg, DWORD_PTR dwParam1, DWORD_PTR dwParam2)
{
  UINT v4; // ebx
  DWORD_PTR v5; // rdi
  DWORD_PTR v6; // r15
  MCIDEVICEID v7; // r13d
  __int64 CommandItem; // rbx
  __int64 v10; // r11
  int v11; // eax
  unsigned int v12; // ebx
  char *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  unsigned int v16; // eax
  __int64 v17; // r11
  __int64 v18; // rcx
  int v19; // edx
  unsigned int v20; // ebx
  int v21; // r14d
  unsigned int v22; // eax
  unsigned int v23; // r11d
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 *v26; // rsi
  unsigned int v27; // r12d
  unsigned int v28; // ebx
  unsigned int ParamSize; // eax
  int v30; // r11d
  unsigned int v31; // eax
  unsigned int v32; // eax
  __int64 v33; // rax
  unsigned int v34; // eax
  __int64 v35; // r8
  _QWORD *v36; // r9
  unsigned int v37; // ebx
  DWORD_PTR *p_dwParam2a; // r9
  __int64 v39; // rdx
  __int64 v40; // r8
  MCIERROR v41; // r15d
  unsigned __int64 v42; // rbx
  const char *v43; // r8
  char *v44; // rcx
  unsigned __int64 v45; // rbx
  unsigned __int64 v46; // rdx
  unsigned int v47; // edi
  unsigned int i; // ebx
  unsigned __int64 v49; // rbx
  char *v50; // rsi
  CHAR *v51; // r14
  __int64 v52; // rax
  MCIERROR v53; // eax
  unsigned __int64 v54; // rbx
  unsigned __int64 v55; // rdx
  HANDLE v56; // rcx
  __int64 v57; // rsi
  CHAR *v58; // r14
  CHAR *v59; // r12
  __int64 v60; // rax
  MCIERROR v61; // ebx
  __int64 v62; // rax
  __int64 v63; // rax
  unsigned int v64; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v65; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v66; // [rsp+38h] [rbp-C8h]
  unsigned int v67; // [rsp+3Ch] [rbp-C4h] BYREF
  __int64 *v68; // [rsp+40h] [rbp-C0h]
  int v69; // [rsp+48h] [rbp-B8h]
  unsigned int v70; // [rsp+4Ch] [rbp-B4h]
  __int64 v71; // [rsp+50h] [rbp-B0h]
  int v72; // [rsp+58h] [rbp-A8h]
  unsigned int v73; // [rsp+5Ch] [rbp-A4h]
  UINT uMsga; // [rsp+60h] [rbp-A0h]
  MCIDEVICEID mciIda; // [rsp+64h] [rbp-9Ch]
  PCHAR MbString; // [rsp+68h] [rbp-98h]
  DWORD_PTR dwParam2a; // [rsp+70h] [rbp-90h] BYREF
  LPVOID lpMem; // [rsp+78h] [rbp-88h] BYREF
  __int64 v79; // [rsp+80h] [rbp-80h]

  v4 = uMsg;
  v5 = dwParam2;
  uMsga = uMsg;
  v6 = dwParam1;
  mciIda = mciId;
  v7 = mciId;
  if ( !dwParam1 )
    return mciSendCommandW(mciId, uMsg, dwParam1, dwParam2);
  switch ( uMsg )
  {
    case 0x801u:
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids);
      }
      break;
    case 0x802u:
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids);
      }
      uMsg = 2050;
      goto LABEL_121;
    case 0x803u:
      break;
    case 0x810u:
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids);
      }
      if ( (v6 & 0x100) != 0 )
      {
        uMsg = 2064;
LABEL_121:
        dwParam1 = v6;
        dwParam2 = v5;
        mciId = v7;
        return mciSendCommandW(mciId, uMsg, dwParam1, dwParam2);
      }
      v49 = 2LL * *(unsigned int *)(v5 + 16);
      if ( v49 > 0xFFFFFFFF )
        return 264;
      v50 = *(char **)(v5 + 8);
      v51 = 0;
      if ( (_DWORD)v49 )
      {
        if ( v50 )
        {
          v52 = winmmAlloc((unsigned int)v49);
          *(_QWORD *)(v5 + 8) = v52;
          if ( !v52 )
          {
LABEL_103:
            *(_QWORD *)(v5 + 8) = v50;
            return 264;
          }
          v51 = (CHAR *)winmmAlloc((unsigned int)v49);
          if ( !v51 )
          {
            HeapFree(hHeap, 0, *(LPVOID *)(v5 + 8));
            goto LABEL_103;
          }
        }
      }
      else
      {
        *(_QWORD *)(v5 + 8) = 0;
      }
      v53 = mciSendCommandW(v7, 0x810u, v6, v5);
      v41 = v53;
      if ( (_DWORD)v49 && v50 )
      {
        if ( !v53 )
        {
          UnicodeStrToAsciiStr(v51);
          v54 = (unsigned __int64)(unsigned int)v49 >> 1;
          v55 = 2LL * (unsigned int)(*(_DWORD *)(v5 + 16) + 1);
          if ( v55 >= v54 )
            v55 = v54;
          StringCbCopyA(v50, v55, v51);
        }
        HeapFree(hHeap, 0, *(LPVOID *)(v5 + 8));
        v56 = hHeap;
        *(_QWORD *)(v5 + 8) = v50;
        HeapFree(v56, 0, v51);
      }
      return v41;
    default:
      dwParam2 = 0;
      v64 = 0;
      v65 = 0;
      v67 = 0;
      if ( v5 )
      {
        CommandItem = FindCommandItem(mciId, uMsg, uMsg, 0, (__int64)&v67);
        if ( !CommandItem )
          return 274;
        v69 = 0;
        MbString = 0;
        v67 = 0;
        memset_0(&dwParam2a, 0, 0xD8u);
        if ( (v6 & 1) != 0 )
          dwParam2a = *(_QWORD *)v5;
        v68 = (__int64 *)(CommandItem + (unsigned int)mciEatCommandEntry(CommandItem, 0, 0));
        v66 = mciEatCommandEntry(v68, &v65, &v64);
        if ( v64 != 4 )
        {
          v16 = 0;
          v18 = v10;
          v19 = 8;
LABEL_30:
          v20 = 0;
          v72 = v19;
          v70 = 0;
          v21 = 1;
          v71 = v18;
          v73 = v16;
          do
          {
            if ( (v21 & (unsigned int)v6) != 0 )
            {
              v66 = v19;
              v22 = mciEatCommandEntry(v18, &v65, &v64);
              v18 = v71;
              v24 = v64;
              v68 = (__int64 *)(v71 + v22);
              if ( v64 != 3 )
              {
                while ( 1 )
                {
                  v25 = v65;
                  if ( v65 == v21 || v23 > 0xB8 )
                    break;
                  if ( (_DWORD)v24 == 8 )
                  {
                    v26 = v68;
                    v27 = 0;
                    v28 = v65;
                    do
                    {
                      ParamSize = mciGetParamSize(v28, v24);
                      if ( v27 <= ParamSize )
                        v27 = ParamSize;
                      v26 = (__int64 *)((char *)v26 + (unsigned int)mciEatCommandEntry(v26, 0, &v64));
                      v24 = v64;
                    }
                    while ( v64 != 9 );
                    v20 = v70;
                    v66 = v27;
                    v31 = v27;
                    v68 = v26;
                  }
                  else
                  {
                    v31 = mciGetParamSize(v65, v24);
                  }
                  v66 = v31 + v30;
                  v32 = mciEatCommandEntry(v68, &v65, &v64);
                  v68 = (__int64 *)((char *)v68 + v32);
                  v24 = v64;
                  if ( v64 == 3 )
                  {
                    v25 = v65;
                    break;
                  }
                }
                if ( (_DWORD)v24 != 3 )
                {
                  v68 = (__int64 *)((char *)&dwParam2a + v23);
                  if ( (_DWORD)v24 == 1 )
                  {
                    v33 = AllocUnicodeStr(*(CHAR **)(v23 + v5));
                    *v68 = v33;
                    v20 |= 1 << ((v66 >> 2) - 1);
                    v70 = v20;
                  }
                  else
                  {
                    v34 = mciGetParamSize(v25, v24);
                    v64 = v34;
                    if ( v34 )
                    {
                      if ( v34 == 4 )
                        *v36 = *(unsigned int *)(v35 + v5);
                      else
                        memcpy_0(v36, (const void *)(v35 + v5), v34);
                    }
                  }
                }
                v18 = v71;
              }
            }
            v19 = v72;
            v21 *= 2;
          }
          while ( v21 );
          if ( v20 | v69 )
          {
            if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_DD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                28,
                WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids,
                v20,
                v69);
            }
            v37 = v73;
            p_dwParam2a = &dwParam2a;
          }
          else
          {
            if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids, uMsga);
            }
            v37 = 0;
            p_dwParam2a = (DWORD_PTR *)v5;
          }
          v41 = mciSendCommandW(mciIda, uMsga, v6, (DWORD_PTR)p_dwParam2a);
          if ( v69 && v67 )
          {
            if ( !v41 )
            {
              v42 = v67;
              UnicodeStrToAsciiStr(MbString);
              v43 = MbString;
              v44 = *(char **)(v5 + 8);
              v45 = v42 >> 1;
              v46 = 2 * v79 + 2;
              *(_QWORD *)(v5 + 16) = v79;
              if ( v46 >= v45 )
                v46 = v45;
              StringCbCopyA(v44, v46, v43);
            }
            if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_P(*((_QWORD *)WPP_GLOBAL_Control + 2), v39, v40, lpMem);
            }
            HeapFree(hHeap, 0, lpMem);
          }
          else if ( v37 )
          {
            if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids, v37);
            }
            memcpy_0((void *)(v5 + 4), &lpMem, v37);
          }
          v47 = v70;
          for ( i = 1; v47; v47 >>= 1 )
          {
            if ( (v47 & 1) != 0 )
            {
              if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                WPP_SF_dPS(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  *(&dwParam2a + i),
                  v40,
                  i,
                  *(&dwParam2a + i),
                  *(&dwParam2a + i));
              }
              HeapFree(hHeap, 0, (LPVOID)*(&dwParam2a + i));
            }
            ++i;
          }
          if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids);
          }
          return v41;
        }
        if ( v65 != 1 )
        {
LABEL_28:
          v16 = mciGetParamSize(v65, 4);
          v18 = v17 + v66;
          v19 = v16 + 8;
          goto LABEL_30;
        }
        if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids);
        }
        if ( *(_QWORD *)(v5 + 16) >= 0x7FFFFFFFu || (v11 = *(_DWORD *)(v5 + 16), v12 = 2 * v11, (v67 = 2 * v11) == 0) )
        {
          lpMem = 0;
          goto LABEL_27;
        }
        v13 = (char *)winmmAlloc((unsigned int)(4 * v11));
        lpMem = v13;
        if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_dP(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, v15, v12, v13);
          v13 = (char *)lpMem;
        }
        if ( v13 )
        {
          v69 = 1;
          MbString = &v13[v12];
LABEL_27:
          v79 = *(_QWORD *)(v5 + 16);
          goto LABEL_28;
        }
        return 264;
      }
      return mciSendCommandW(mciId, uMsg, dwParam1, dwParam2);
  }
  v57 = *(_QWORD *)(v5 + 12);
  v58 = *(CHAR **)(v5 + 20);
  v59 = *(CHAR **)(v5 + 28);
  if ( v57 )
  {
    if ( (v6 & 0x3000) == 0x2000 )
    {
      v60 = AllocUnicodeStr(*(CHAR **)(v5 + 12));
      *(_QWORD *)(v5 + 12) = v60;
      if ( !v60 )
      {
        v61 = 264;
LABEL_149:
        *(_QWORD *)(v5 + 12) = v57;
        return v61;
      }
    }
    else
    {
      v57 = 0;
    }
  }
  if ( v58 )
  {
    if ( (v6 & 0xA00) == 0x200 )
    {
      v62 = AllocUnicodeStr(v58);
      *(_QWORD *)(v5 + 20) = v62;
      if ( !v62 )
      {
        v61 = 264;
        goto LABEL_146;
      }
    }
    else
    {
      v58 = 0;
    }
  }
  if ( v59 )
  {
    if ( (v6 & 0x400) != 0 )
    {
      v63 = AllocUnicodeStr(v59);
      *(_QWORD *)(v5 + 28) = v63;
      if ( !v63 )
      {
        v61 = 264;
LABEL_143:
        *(_QWORD *)(v5 + 28) = v59;
        goto LABEL_144;
      }
    }
    else
    {
      v59 = 0;
    }
  }
  v61 = mciSendCommandW(v7, v4, v6, v5);
  if ( v59 )
  {
    HeapFree(hHeap, 0, *(LPVOID *)(v5 + 28));
    goto LABEL_143;
  }
LABEL_144:
  if ( !v58 )
    goto LABEL_147;
  HeapFree(hHeap, 0, *(LPVOID *)(v5 + 20));
LABEL_146:
  *(_QWORD *)(v5 + 20) = v58;
LABEL_147:
  if ( v57 )
  {
    HeapFree(hHeap, 0, *(LPVOID *)(v5 + 12));
    goto LABEL_149;
  }
  return v61;
}

```

## disassembly

```asm
0x180011610  push    rbp
0x180011612  push    rbx
0x180011613  push    rsi
0x180011614  push    rdi
0x180011615  push    r12
0x180011617  push    r13
0x180011619  push    r14
0x18001161b  push    r15
0x18001161d  lea     rbp, [rsp-68h]
0x180011622  sub     rsp, 168h
0x180011629  mov     rax, cs:__security_cookie
0x180011630  xor     rax, rsp
0x180011633  mov     [rbp+0A0h+var_50], rax
0x180011637  mov     ebx, edx
0x180011639  mov     rdi, r9
0x18001163c  mov     [rsp+1A0h+uMsg], ebx
0x180011640  mov     r15, r8
0x180011643  mov     [rsp+1A0h+mciId], ecx
0x180011647  mov     r13d, ecx
0x18001164a  test    r8, r8
0x18001164d  jnz     short loc_18001165B
0x18001164f  mov     edx, ebx; uMsg
0x180011651  call    mciSendCommandW
0x180011656  jmp     loc_180011E6A
0x18001165b  mov     eax, ebx
0x18001165d  sub     eax, 801h
0x180011662  jz      loc_180011D35
0x180011668  sub     eax, 1
0x18001166b  jz      loc_180011CEA
0x180011671  sub     eax, 1
0x180011674  jz      loc_180011D6D
0x18001167a  cmp     eax, 0Dh
0x18001167d  jz      loc_180011BB5
0x180011683  xor     r9d, r9d
0x180011686  mov     [rsp+1A0h+var_170], 0
0x18001168e  mov     [rsp+1A0h+var_16C], 0
0x180011696  mov     [rsp+1A0h+var_164], 0
0x18001169e  test    rdi, rdi
0x1800116a1  jz      short loc_18001164F
0x1800116a3  lea     rax, [rsp+1A0h+var_164]
0x1800116a8  mov     r8, rbx
0x1800116ab  mov     [rsp+1A0h+var_180], rax
0x1800116b0  call    FindCommandItem
0x1800116b5  mov     rbx, rax
0x1800116b8  test    rax, rax
0x1800116bb  jnz     short loc_1800116C7
0x1800116bd  mov     eax, 112h
0x1800116c2  jmp     loc_180011E6A
0x1800116c7  xor     r8d, r8d
0x1800116ca  mov     [rsp+1A0h+var_158], 0
0x1800116d2  mov     [rsp+1A0h+MbString], r8
0x1800116d7  lea     rcx, [rsp+1A0h+dwParam2]; void *
0x1800116dc  mov     [rsp+1A0h+var_164], r8d
0x1800116e1  xor     edx, edx; Val
0x1800116e3  mov     r8d, 0D8h; Size
0x1800116e9  call    memset_0
0x1800116ee  mov     r13d, 1
0x1800116f4  test    r13b, r15b
0x1800116f7  jz      short loc_180011701
0x1800116f9  mov     rax, [rdi]
0x1800116fc  mov     [rsp+1A0h+dwParam2], rax
0x180011701  xor     r8d, r8d
0x180011704  xor     edx, edx
0x180011706  mov     rcx, rbx
0x180011709  call    mciEatCommandEntry
0x18001170e  mov     r11d, eax
0x180011711  lea     r8, [rsp+1A0h+var_170]
0x180011716  add     r11, rbx
0x180011719  lea     rdx, [rsp+1A0h+var_16C]
0x18001171e  mov     rcx, r11
0x180011721  mov     [rsp+1A0h+var_160], r11
0x180011726  call    mciEatCommandEntry
0x18001172b  cmp     [rsp+1A0h+var_170], 4
0x180011730  lea     r14, WPP_GLOBAL_Control
0x180011737  mov     [rsp+1A0h+var_168], eax
0x18001173b  mov     esi, 400000h
0x180011740  mov     r12b, 5
0x180011743  jnz     loc_18001181C
0x180011749  cmp     [rsp+1A0h+var_16C], r13d
0x18001174e  jnz     loc_180011802
0x180011754  mov     rcx, cs:WPP_GLOBAL_Control
0x18001175b  cmp     rcx, r14
0x18001175e  jz      short loc_180011780
0x180011760  test    [rcx+1Ch], esi
0x180011763  jz      short loc_180011780
0x180011765  cmp     [rcx+19h], r12b
0x180011769  jb      short loc_180011780
0x18001176b  mov     rcx, [rcx+10h]
0x18001176f  lea     r8, WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids
0x180011776  mov     edx, 17h
0x18001177b  call    WPP_SF_
0x180011780  cmp     qword ptr [rdi+10h], 7FFFFFFFh
0x180011788  jnb     short loc_1800117EC
0x18001178a  mov     eax, [rdi+10h]
0x18001178d  lea     ebx, [rax+rax]
0x180011790  mov     [rsp+1A0h+var_164], ebx
0x180011794  test    ebx, ebx
0x180011796  jz      short loc_1800117EC
0x180011798  lea     ecx, [rbx+rbx]; Size
0x18001179b  call    winmmAlloc
0x1800117a0  mov     [rsp+1A0h+lpMem], rax
0x1800117a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800117ac  cmp     rcx, r14
0x1800117af  jz      short loc_1800117D2
0x1800117b1  test    [rcx+1Ch], esi
0x1800117b4  jz      short loc_1800117D2
0x1800117b6  cmp     [rcx+19h], r12b
0x1800117ba  jb      short loc_1800117D2
0x1800117bc  mov     rcx, [rcx+10h]
0x1800117c0  mov     r9d, ebx
0x1800117c3  mov     [rsp+1A0h+var_180], rax
0x1800117c8  call    WPP_SF_dP
0x1800117cd  mov     rax, [rsp+1A0h+lpMem]
0x1800117d2  test    rax, rax
0x1800117d5  jz      loc_180011C35
0x1800117db  mov     ecx, ebx
0x1800117dd  add     rcx, rax
0x1800117e0  mov     [rsp+1A0h+var_158], r13d
0x1800117e5  mov     [rsp+1A0h+MbString], rcx
0x1800117ea  jmp     short loc_1800117F5
0x1800117ec  mov     [rsp+1A0h+lpMem], 0
0x1800117f5  mov     rax, [rdi+10h]
0x1800117f9  mov     r11, [rsp+1A0h+var_160]
0x1800117fe  mov     [rbp+0A0h+var_120], rax
0x180011802  mov     ecx, [rsp+1A0h+var_16C]
0x180011806  mov     edx, 4
0x18001180b  call    mciGetParamSize
0x180011810  mov     ecx, [rsp+1A0h+var_168]
0x180011814  add     rcx, r11
0x180011817  lea     edx, [rax+8]
0x18001181a  jmp     short loc_180011824
0x18001181c  xor     eax, eax
0x18001181e  mov     rcx, r11
0x180011821  lea     edx, [rax+8]
0x180011824  xor     ebx, ebx
0x180011826  mov     [rsp+1A0h+var_148], edx
0x18001182a  mov     [rsp+1A0h+var_154], ebx
0x18001182e  mov     r14d, r13d
0x180011831  mov     [rsp+1A0h+var_150], rcx
0x180011836  mov     [rsp+1A0h+var_144], eax
0x18001183a  mov     eax, r14d
0x18001183d  test    r15, rax
0x180011840  jz      loc_180011993
0x180011846  mov     r11d, edx
0x180011849  mov     [rsp+1A0h+var_168], edx
0x18001184d  lea     rdx, [rsp+1A0h+var_16C]
0x180011852  lea     r8, [rsp+1A0h+var_170]
0x180011857  call    mciEatCommandEntry
0x18001185c  mov     rcx, [rsp+1A0h+var_150]
0x180011861  mov     edx, [rsp+1A0h+var_170]
0x180011865  mov     eax, eax
0x180011867  add     rax, rcx
0x18001186a  mov     [rsp+1A0h+var_160], rax
0x18001186f  cmp     edx, 3
0x180011872  jz      loc_180011993
0x180011878  mov     ecx, [rsp+1A0h+var_16C]
0x18001187c  cmp     ecx, r14d
0x18001187f  jz      loc_180011921
0x180011885  cmp     r11d, 0B8h
0x18001188c  ja      loc_180011921
0x180011892  cmp     edx, 8
0x180011895  jnz     short loc_1800118E8
0x180011897  mov     rsi, [rsp+1A0h+var_160]
0x18001189c  xor     r12d, r12d
0x18001189f  mov     ebx, ecx
0x1800118a1  mov     ecx, ebx
0x1800118a3  call    mciGetParamSize
0x1800118a8  cmp     r12d, eax
0x1800118ab  lea     r8, [rsp+1A0h+var_170]
0x1800118b0  mov     rcx, rsi
0x1800118b3  cmovbe  r12d, eax
0x1800118b7  xor     edx, edx
0x1800118b9  call    mciEatCommandEntry
0x1800118be  mov     edx, eax
0x1800118c0  add     rsi, rdx
0x1800118c3  mov     edx, [rsp+1A0h+var_170]
0x1800118c7  cmp     edx, 9
0x1800118ca  jnz     short loc_1800118A1
0x1800118cc  mov     ebx, [rsp+1A0h+var_154]
0x1800118d0  mov     [rsp+1A0h+var_168], r12d
0x1800118d5  mov     r12b, 5
0x1800118d8  mov     eax, [rsp+1A0h+var_168]
0x1800118dc  mov     [rsp+1A0h+var_160], rsi
0x1800118e1  mov     esi, 400000h
0x1800118e6  jmp     short loc_1800118ED
0x1800118e8  call    mciGetParamSize
0x1800118ed  mov     rcx, [rsp+1A0h+var_160]
0x1800118f2  lea     r8, [rsp+1A0h+var_170]
0x1800118f7  add     r11d, eax
0x1800118fa  lea     rdx, [rsp+1A0h+var_16C]
0x1800118ff  mov     [rsp+1A0h+var_168], r11d
0x180011904  call    mciEatCommandEntry
0x180011909  mov     edx, eax
0x18001190b  add     [rsp+1A0h+var_160], rdx
0x180011910  mov     edx, [rsp+1A0h+var_170]
0x180011914  cmp     edx, 3
0x180011917  jnz     loc_180011878
0x18001191d  mov     ecx, [rsp+1A0h+var_16C]
0x180011921  cmp     edx, 3
0x180011924  jz      short loc_18001198E
0x180011926  mov     r8d, r11d
0x180011929  lea     r9, [rsp+1A0h+dwParam2]
0x18001192e  add     r9, r8
0x180011931  mov     [rsp+1A0h+var_160], r9
0x180011936  cmp     edx, r13d
0x180011939  jnz     short loc_180011963
0x18001193b  mov     rcx, [r8+rdi]; MultiByteString
0x18001193f  call    AllocUnicodeStr
0x180011944  mov     rcx, [rsp+1A0h+var_160]
0x180011949  mov     [rcx], rax
0x18001194c  mov     eax, r13d
0x18001194f  mov     ecx, [rsp+1A0h+var_168]
0x180011953  shr     ecx, 2
0x180011956  sub     ecx, r13d
0x180011959  shl     eax, cl
0x18001195b  or      ebx, eax
0x18001195d  mov     [rsp+1A0h+var_154], ebx
0x180011961  jmp     short loc_18001198E
0x180011963  call    mciGetParamSize
0x180011968  mov     [rsp+1A0h+var_170], eax
0x18001196c  test    eax, eax
0x18001196e  jz      short loc_18001198E
0x180011970  lea     rcx, [r8+rdi]
0x180011974  cmp     eax, 4
0x180011977  jz      short loc_180011989
0x180011979  mov     rdx, rcx; Src
0x18001197c  mov     r8d, eax; Size
0x18001197f  mov     rcx, r9; void *
0x180011982  call    memcpy_0
0x180011987  jmp     short loc_18001198E
0x180011989  mov     eax, [rcx]
0x18001198b  mov     [r9], rax
0x18001198e  mov     rcx, [rsp+1A0h+var_150]
0x180011993  mov     edx, [rsp+1A0h+var_148]
0x180011997  add     r14d, r14d
0x18001199a  jnz     loc_18001183A
0x1800119a0  mov     r8d, [rsp+1A0h+var_158]
0x1800119a5  lea     r14, WPP_GLOBAL_Control
0x1800119ac  mov     eax, r8d
0x1800119af  or      eax, ebx
0x1800119b1  jnz     short loc_1800119EB
0x1800119b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800119ba  cmp     rcx, r14
0x1800119bd  jz      short loc_1800119E4
0x1800119bf  test    [rcx+1Ch], esi
0x1800119c2  jz      short loc_1800119E4
0x1800119c4  cmp     [rcx+19h], r12b
0x1800119c8  jb      short loc_1800119E4
0x1800119ca  mov     r9d, [rsp+1A0h+uMsg]
0x1800119cf  lea     r8, WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids
0x1800119d6  mov     rcx, [rcx+10h]
0x1800119da  mov     edx, 1Bh
0x1800119df  call    WPP_SF_d
0x1800119e4  xor     ebx, ebx
0x1800119e6  mov     r9, rdi
0x1800119e9  jmp     short loc_180011A28
0x1800119eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800119f2  cmp     rcx, r14
0x1800119f5  jz      short loc_180011A1F
0x1800119f7  test    [rcx+1Ch], esi
0x1800119fa  jz      short loc_180011A1F
0x1800119fc  cmp     [rcx+19h], r12b
0x180011a00  jb      short loc_180011A1F
0x180011a02  mov     rcx, [rcx+10h]
0x180011a06  mov     edx, 1Ch
0x180011a0b  mov     dword ptr [rsp+1A0h+var_180], r8d
0x180011a10  mov     r9d, ebx
0x180011a13  lea     r8, WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids
0x180011a1a  call    WPP_SF_DD
0x180011a1f  mov     ebx, [rsp+1A0h+var_144]
0x180011a23  lea     r9, [rsp+1A0h+dwParam2]; dwParam2
0x180011a28  mov     edx, [rsp+1A0h+uMsg]; uMsg
0x180011a2c  mov     r8, r15; dwParam1
0x180011a2f  mov     ecx, [rsp+1A0h+mciId]; mciId
0x180011a33  call    mciSendCommandW
0x180011a38  cmp     [rsp+1A0h+var_158], 0
0x180011a3d  mov     r15d, eax
0x180011a40  jz      loc_180011AD2
0x180011a46  mov     eax, [rsp+1A0h+var_164]
0x180011a4a  test    eax, eax
0x180011a4c  jz      loc_180011AD2
0x180011a52  test    r15d, r15d
0x180011a55  jnz     short loc_180011A97
0x180011a57  mov     r8, [rsp+1A0h+lpMem]
0x180011a5c  mov     ebx, eax
0x180011a5e  mov     rax, [rsp+1A0h+MbString]
0x180011a63  mov     rcx, rax; MbString
0x180011a66  lea     rdx, [rbx+rax]
0x180011a6a  call    UnicodeStrToAsciiStr
0x180011a6f  mov     rax, [rbp+0A0h+var_120]
0x180011a73  mov     r8, [rsp+1A0h+MbString]; char *
0x180011a78  mov     rcx, [rdi+8]; char *
0x180011a7c  shr     rbx, 1
0x180011a7f  lea     rdx, ds:2[rax*2]
0x180011a87  mov     [rdi+10h], rax
0x180011a8b  cmp     rdx, rbx
0x180011a8e  cmovnb  rdx, rbx; unsigned __int64
0x180011a92  call    ?StringCbCopyA@@YAJPEAD_KPEBD@Z; StringCbCopyA(char *,unsigned __int64,char const *)
0x180011a97  mov     rcx, cs:WPP_GLOBAL_Control
0x180011a9e  cmp     rcx, r14
  ... truncated ...
```
