# _ClientEventCallback(tagCL_INSTANCE_INFO *,tagEVENT_PACKET *)

- ea: `0x180062d00`
- end: `0x1800631ee`
- name: `?_ClientEventCallback@@YAKPEAUtagCL_INSTANCE_INFO@@PEAUtagEVENT_PACKET@@@Z`
- size: `1262`
- prototype: `unsigned int __fastcall(struct tagCL_INSTANCE_INFO *, struct tagEVENT_PACKET *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180094900`

## callees

- `0x1800198dc`
- `0x180019b20`
- `0x180043b70`
- `0x180062d00`
- `0x180068c40`
- `0x180073c08`
- `0x18007f2e4`
- `0x180096e00`

## import_xrefs

- `ntdll!RtlUnicodeToMultiByteN` at `0x180063136`
- `ntdll!RtlUnicodeToMultiByteN` at `0x180063136`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18006310f`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18006310f`
- `ntdll!RtlEnterCriticalSection` at `0x180062d33`
- `ntdll!RtlEnterCriticalSection` at `0x180062d33`
- `ntdll!RtlLeaveCriticalSection` at `0x1800631c3`
- `ntdll!RtlLeaveCriticalSection` at `0x1800631c3`
- `ntdll!RtlFreeHeap` at `0x1800630c1`
- `ntdll!RtlFreeHeap` at `0x1800630c1`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x180062e52`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x180062f2d`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x180062f37`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x18006304d`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x180063057`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x180062e52`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x180062f2d`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x180062f37`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x18006304d`
- `api-ms-win-core-atoms-l1-1-0!DeleteAtom` at `0x180063057`

## pseudocode

```c
__int64 __fastcall _ClientEventCallback(struct tagCL_INSTANCE_INFO *a1, struct tagEVENT_PACKET *a2)
{
  __m128i v4; // xmm2
  __int64 v5; // xmm1_8
  unsigned __int16 v6; // ax
  unsigned int v7; // r8d
  HDDEDATA hData; // rax
  HDDEDATA v9; // rsi
  ATOM v10; // cx
  __m128i v11; // xmm2
  __int128 v12; // xmm1
  unsigned __int16 v13; // ax
  unsigned int v14; // r8d
  HDDEDATA v15; // rax
  HDDEDATA v16; // rsi
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int64 v19; // rcx
  __int128 v20; // xmm2
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  unsigned __int16 v27; // ax
  HDDEDATA v28; // rax
  HDDEDATA v29; // rsi
  int v30; // eax
  char v31; // al
  ULONG BytesInMultiByteString; // eax
  ULONG v33; // eax
  __m128i v34; // xmm1
  HDDEDATA DataHandle; // rax
  HDDEDATA v36; // rsi
  PVOID P[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 v39[16]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v40; // [rsp+70h] [rbp-90h]
  __int64 v41; // [rsp+80h] [rbp-80h]
  __int64 v42; // [rsp+88h] [rbp-78h]
  __int128 v43; // [rsp+90h] [rbp-70h]
  __int128 v44; // [rsp+A0h] [rbp-60h]
  __int128 v45; // [rsp+B0h] [rbp-50h]
  __int128 v46; // [rsp+C0h] [rbp-40h]
  __int128 v47; // [rsp+D0h] [rbp-30h]
  __int128 v48; // [rsp+E0h] [rbp-20h]
  __int64 v49; // [rsp+F0h] [rbp-10h]
  WCHAR UnicodeString[8]; // [rsp+100h] [rbp+0h] BYREF
  __m128i v51; // [rsp+110h] [rbp+10h]
  __int128 v52; // [rsp+120h] [rbp+20h]
  __int128 v53; // [rsp+130h] [rbp+30h]
  __int64 v54; // [rsp+140h] [rbp+40h]

  RtlEnterCriticalSection(&gcsDDEML);
  switch ( *(_DWORD *)a2 )
  {
    case 0:
      *((_DWORD *)a1 + 6) = *((_DWORD *)a2 + 2);
      break;
    case 0x1000000:
      if ( *((__int16 *)a1 + 54) >= 0 )
      {
        v30 = *((unsigned __int16 *)a2 + 3) - *((_DWORD *)a2 + 2);
        P[0] = 0;
        if ( (unsigned int)WCSToMBEx(0, (char *)a2 + 40, (unsigned __int64)v30 >> 1, P, v30, 1) )
        {
          StringCbCopyA(
            (char *)a2 + 40,
            (unsigned __int64)(*((unsigned __int16 *)a2 + 3) - *((_DWORD *)a2 + 2)) >> 1,
            (const char *)P[0]);
          RtlFreeHeap(pUserHeap, 0, P[0]);
        }
        *((_DWORD *)a2 + 2) = 40;
      }
LABEL_23:
      if ( *(_DWORD *)a2 != 0x4000000 )
        goto LABEL_35;
      goto LABEL_24;
    case 0x2000000:
      goto LABEL_23;
    case 0x4000000:
LABEL_24:
      if ( *((_DWORD *)a2 + 10) != 1000 )
        goto LABEL_35;
      v31 = *((_BYTE *)a2 + 84);
      if ( *((__int16 *)a1 + 54) >= 0 )
      {
        if ( v31 )
          goto LABEL_35;
        v33 = *((_DWORD *)a2 + 20);
        if ( v33 > 0x20 )
          v33 = 32;
        RtlUnicodeToMultiByteN((PCHAR)UnicodeString, 0x20u, 0, (PCWCH)a2 + 42, v33);
      }
      else
      {
        if ( !v31 )
          goto LABEL_35;
        BytesInMultiByteString = *((_DWORD *)a2 + 20);
        if ( BytesInMultiByteString > 0x20 )
          BytesInMultiByteString = 32;
        RtlMultiByteToUnicodeN(UnicodeString, 0x20u, 0, (const CHAR *)a2 + 84, BytesInMultiByteString);
      }
      v34 = v51;
      *(_OWORD *)((char *)a2 + 84) = *(_OWORD *)UnicodeString;
      *(__m128i *)((char *)a2 + 100) = v34;
LABEL_35:
      DataHandle = InternalCreateDataHandle(
                     a1,
                     (unsigned __int8 *)a2 + 8,
                     *((unsigned __int16 *)a2 + 3),
                     0,
                     0xC100u,
                     0,
                     0);
      v36 = DataHandle;
      if ( DataHandle )
      {
        DoCallback(a1, 0x80F2u, 0, 0, 0, 0, DataHandle, 0, *(unsigned int *)a2);
        InternalFreeDataHandle(v36, 1);
      }
      break;
    case 0x8000000:
      v17 = *(_OWORD *)((char *)a2 + 8);
      v18 = *(_OWORD *)((char *)a2 + 24);
      v19 = *((_QWORD *)a2 + 6);
      v20 = *(_OWORD *)((char *)a2 + 40);
      v49 = *((_QWORD *)a2 + 19);
      *(_OWORD *)v39 = v17;
      v21 = *(_OWORD *)((char *)a2 + 56);
      v40 = v18;
      v22 = *(_OWORD *)((char *)a2 + 72);
      v43 = v21;
      v23 = *(_OWORD *)((char *)a2 + 88);
      v44 = v22;
      v24 = *(_OWORD *)((char *)a2 + 104);
      v45 = v23;
      v25 = *(_OWORD *)((char *)a2 + 120);
      v46 = v24;
      v26 = *(_OWORD *)((char *)a2 + 136);
      v47 = v25;
      v48 = v26;
      v41 = v20;
      v42 = GlobalToLocalAtom(v19);
      v27 = GlobalToLocalAtom(v43);
      *(_QWORD *)&v43 = v27;
      if ( DWORD1(v40) == 32930 || DWORD1(v40) == 32978 )
        *(_QWORD *)&v43 = v27 | 0x10000LL;
      v28 = InternalCreateDataHandle(a1, v39, *((unsigned __int16 *)a2 + 3), 0, 0xC100u, 0, 0);
      v29 = v28;
      if ( v28 )
      {
        DoCallback(a1, 0x80F2u, 0, 0, 0, 0, v28, 0, *(unsigned int *)a2);
        InternalFreeDataHandle(v29, 1);
        DeleteAtom(v42);
        v10 = v43;
        goto LABEL_18;
      }
      break;
    case 0x10000000:
      goto LABEL_35;
    case 0x20000000:
      v11 = *(__m128i *)((char *)a2 + 24);
      v12 = *(_OWORD *)((char *)a2 + 56);
      *(_OWORD *)UnicodeString = *(_OWORD *)((char *)a2 + 8);
      v52 = *(_OWORD *)((char *)a2 + 40);
      v54 = *((_QWORD *)a2 + 9);
      v51 = v11;
      v53 = v12;
      v51.m128i_i64[1] = GlobalToLocalAtom(_mm_extract_epi16(v11, 4));
      *(_QWORD *)&v52 = GlobalToLocalAtom(v52);
      v13 = GlobalToLocalAtom(WORD4(v52));
      v14 = *((unsigned __int16 *)a2 + 3);
      *((_QWORD *)&v52 + 1) = v13;
      v15 = InternalCreateDataHandle(a1, (unsigned __int8 *)UnicodeString, v14, 0, 0xC100u, 0, 0);
      v16 = v15;
      if ( v15 )
      {
        DoCallback(a1, 0x80F2u, 0, 0, 0, 0, v15, 0, *(unsigned int *)a2);
        InternalFreeDataHandle(v16, 1);
        DeleteAtom(v51.m128i_u16[4]);
        DeleteAtom(v52);
        v10 = WORD4(v52);
        goto LABEL_18;
      }
      break;
    case 0x40000000:
      v4 = *(__m128i *)((char *)a2 + 24);
      v5 = *((_QWORD *)a2 + 7);
      *(_OWORD *)UnicodeString = *(_OWORD *)((char *)a2 + 8);
      v52 = *(_OWORD *)((char *)a2 + 40);
      v51 = v4;
      *(_QWORD *)&v53 = v5;
      v51.m128i_i64[1] = GlobalToLocalAtom(_mm_extract_epi16(v4, 4));
      v6 = GlobalToLocalAtom(v52);
      v7 = *((unsigned __int16 *)a2 + 3);
      *(_QWORD *)&v52 = v6;
      hData = InternalCreateDataHandle(a1, (unsigned __int8 *)UnicodeString, v7, 0, 0xC100u, 0, 0);
      v9 = hData;
      if ( hData )
      {
        DoCallback(a1, 0x80F2u, 0, 0, 0, 0, hData, 0, *(unsigned int *)a2);
        InternalFreeDataHandle(v9, 1);
        DeleteAtom(v51.m128i_u16[4]);
        v10 = v52;
LABEL_18:
        DeleteAtom(v10);
      }
      break;
  }
  RtlLeaveCriticalSection(&gcsDDEML);
  return 0;
}

```

## disassembly

```asm
0x180062d00  mov     [rsp-8+arg_10], rbx
0x180062d05  push    rbp
0x180062d06  push    rsi
0x180062d07  push    rdi
0x180062d08  push    r14
0x180062d0a  push    r15
0x180062d0c  lea     rbp, [rsp-60h]
0x180062d11  sub     rsp, 160h
0x180062d18  mov     rax, cs:__security_cookie
0x180062d1f  xor     rax, rsp
0x180062d22  mov     [rbp+80h+var_30], rax
0x180062d26  mov     rdi, rcx
0x180062d29  mov     rbx, rdx
0x180062d2c  lea     rcx, ?gcsDDEML@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180062d33  call    cs:__imp_RtlEnterCriticalSection
0x180062d39  xor     r14d, r14d
0x180062d3c  cmp     [rbx], r14d
0x180062d3f  jz      loc_1800631B6
0x180062d45  cmp     dword ptr [rbx], 1000000h
0x180062d4b  lea     r15d, [r14+1]
0x180062d4f  jz      loc_180063062
0x180062d55  cmp     dword ptr [rbx], 2000000h
0x180062d5b  jz      loc_1800630CE
0x180062d61  cmp     dword ptr [rbx], 4000000h
0x180062d67  jz      loc_1800630D6
0x180062d6d  cmp     dword ptr [rbx], 8000000h
0x180062d73  jz      loc_180062F46
0x180062d79  cmp     dword ptr [rbx], 10000000h
0x180062d7f  jz      loc_18006314B
0x180062d85  cmp     dword ptr [rbx], 20000000h
0x180062d8b  jz      loc_180062E61
0x180062d91  cmp     dword ptr [rbx], 40000000h
0x180062d97  jnz     loc_1800631BC
0x180062d9d  movups  xmm0, xmmword ptr [rbx+8]
0x180062da1  movups  xmm2, xmmword ptr [rbx+18h]
0x180062da5  movsd   xmm1, qword ptr [rbx+38h]
0x180062daa  movups  xmmword ptr [rbp+80h+UnicodeString], xmm0
0x180062dae  movups  xmm0, xmmword ptr [rbx+28h]
0x180062db2  pextrw  ecx, xmm2, 4; unsigned __int16
0x180062db7  movups  [rbp+80h+var_60], xmm0
0x180062dbb  movups  [rbp+80h+var_70], xmm2
0x180062dbf  movsd   qword ptr [rbp+80h+var_50], xmm1
0x180062dc4  call    ?GlobalToLocalAtom@@YAGG@Z; GlobalToLocalAtom(ushort)
0x180062dc9  movzx   ecx, word ptr [rbp+80h+var_60]; unsigned __int16
0x180062dcd  movzx   eax, ax
0x180062dd0  mov     qword ptr [rbp+80h+var_70+8], rax
0x180062dd4  call    ?GlobalToLocalAtom@@YAGG@Z; GlobalToLocalAtom(ushort)
0x180062dd9  movzx   r8d, word ptr [rbx+6]; unsigned int
0x180062dde  lea     rdx, [rbp+80h+UnicodeString]; unsigned __int8 *
0x180062de2  movzx   eax, ax
0x180062de5  xor     r9d, r9d; unsigned int
0x180062de8  mov     word ptr [rsp+180h+hData], r14w; unsigned __int16
0x180062dee  mov     rcx, rdi; struct tagCL_INSTANCE_INFO *
0x180062df1  mov     word ptr [rsp+180h+var_158], r14w; unsigned __int16
0x180062df7  mov     qword ptr [rbp+80h+var_60], rax
0x180062dfb  mov     [rsp+180h+BytesInMultiByteString], 0C100h; unsigned int
0x180062e03  call    ?InternalCreateDataHandle@@YAPEAUHDDEDATA__@@PEAUtagCL_INSTANCE_INFO@@PEAEKKKGG@Z; InternalCreateDataHandle(tagCL_INSTANCE_INFO *,uchar *,ulong,ulong,ulong,ushort,ushort)
0x180062e08  mov     rsi, rax
0x180062e0b  test    rax, rax
0x180062e0e  jz      loc_1800631BC
0x180062e14  mov     r9d, [rbx]
0x180062e17  xor     r8d, r8d; unsigned __int16
0x180062e1a  mov     [rsp+180h+var_140], r9; unsigned __int64
0x180062e1f  mov     edx, 80F2h; unsigned __int16
0x180062e24  mov     [rsp+180h+var_148], r14; unsigned __int64
0x180062e29  xor     r9d, r9d; HCONV
0x180062e2c  mov     [rsp+180h+hData], rax; hData
0x180062e31  mov     rcx, rdi; struct tagCL_INSTANCE_INFO *
0x180062e34  mov     [rsp+180h+var_158], r14; HSZ
0x180062e39  mov     qword ptr [rsp+180h+BytesInMultiByteString], r14; HSZ
0x180062e3e  call    ?DoCallback@@YAPEAUHDDEDATA__@@PEAUtagCL_INSTANCE_INFO@@GGPEAUHCONV__@@PEAUHSZ__@@2PEAU1@_K4@Z; DoCallback(tagCL_INSTANCE_INFO *,ushort,ushort,HCONV__ *,HSZ__ *,HSZ__ *,HDDEDATA__ *,unsigned __int64,unsigned __int64)
0x180062e43  mov     edx, r15d; int
0x180062e46  mov     rcx, rsi; HDDEDATA
0x180062e49  call    ?InternalFreeDataHandle@@YAHPEAUHDDEDATA__@@H@Z; InternalFreeDataHandle(HDDEDATA__ *,int)
0x180062e4e  movzx   ecx, word ptr [rbp+80h+var_70+8]; nAtom
0x180062e52  call    cs:__imp_DeleteAtom
0x180062e58  movzx   ecx, word ptr [rbp+80h+var_60]
0x180062e5c  jmp     loc_180063057
0x180062e61  movups  xmm0, xmmword ptr [rbx+8]
0x180062e65  movups  xmm2, xmmword ptr [rbx+18h]
0x180062e69  movups  xmm1, xmmword ptr [rbx+38h]
0x180062e6d  movaps  xmmword ptr [rbp+80h+UnicodeString], xmm0
0x180062e71  movups  xmm0, xmmword ptr [rbx+28h]
0x180062e75  pextrw  ecx, xmm2, 4; unsigned __int16
0x180062e7a  movaps  [rbp+80h+var_60], xmm0
0x180062e7e  movsd   xmm0, qword ptr [rbx+48h]
0x180062e83  movsd   [rbp+80h+var_40], xmm0
0x180062e88  movaps  [rbp+80h+var_70], xmm2
0x180062e8c  movaps  [rbp+80h+var_50], xmm1
0x180062e90  call    ?GlobalToLocalAtom@@YAGG@Z; GlobalToLocalAtom(ushort)
0x180062e95  movzx   ecx, word ptr [rbp+80h+var_60]; unsigned __int16
0x180062e99  movzx   eax, ax
0x180062e9c  mov     qword ptr [rbp+80h+var_70+8], rax
0x180062ea0  call    ?GlobalToLocalAtom@@YAGG@Z; GlobalToLocalAtom(ushort)
0x180062ea5  movzx   ecx, word ptr [rbp+80h+var_60+8]; unsigned __int16
0x180062ea9  movzx   eax, ax
0x180062eac  mov     qword ptr [rbp+80h+var_60], rax
0x180062eb0  call    ?GlobalToLocalAtom@@YAGG@Z; GlobalToLocalAtom(ushort)
0x180062eb5  movzx   r8d, word ptr [rbx+6]; unsigned int
0x180062eba  lea     rdx, [rbp+80h+UnicodeString]; unsigned __int8 *
0x180062ebe  movzx   eax, ax
0x180062ec1  xor     r9d, r9d; unsigned int
0x180062ec4  mov     word ptr [rsp+180h+hData], r14w; unsigned __int16
0x180062eca  mov     rcx, rdi; struct tagCL_INSTANCE_INFO *
0x180062ecd  mov     word ptr [rsp+180h+var_158], r14w; unsigned __int16
0x180062ed3  mov     qword ptr [rbp+80h+var_60+8], rax
0x180062ed7  mov     [rsp+180h+BytesInMultiByteString], 0C100h; unsigned int
0x180062edf  call    ?InternalCreateDataHandle@@YAPEAUHDDEDATA__@@PEAUtagCL_INSTANCE_INFO@@PEAEKKKGG@Z; InternalCreateDataHandle(tagCL_INSTANCE_INFO *,uchar *,ulong,ulong,ulong,ushort,ushort)
0x180062ee4  mov     rsi, rax
0x180062ee7  test    rax, rax
0x180062eea  jz      loc_1800631BC
0x180062ef0  mov     ecx, [rbx]
0x180062ef2  xor     r8d, r8d; unsigned __int16
0x180062ef5  mov     [rsp+180h+var_140], rcx; unsigned __int64
0x180062efa  mov     edx, 80F2h; unsigned __int16
0x180062eff  mov     [rsp+180h+var_148], r14; unsigned __int64
0x180062f04  xor     r9d, r9d; HCONV
0x180062f07  mov     [rsp+180h+hData], rax; hData
0x180062f0c  mov     rcx, rdi; struct tagCL_INSTANCE_INFO *
0x180062f0f  mov     [rsp+180h+var_158], r14; HSZ
0x180062f14  mov     qword ptr [rsp+180h+BytesInMultiByteString], r14; HSZ
0x180062f19  call    ?DoCallback@@YAPEAUHDDEDATA__@@PEAUtagCL_INSTANCE_INFO@@GGPEAUHCONV__@@PEAUHSZ__@@2PEAU1@_K4@Z; DoCallback(tagCL_INSTANCE_INFO *,ushort,ushort,HCONV__ *,HSZ__ *,HSZ__ *,HDDEDATA__ *,unsigned __int64,unsigned __int64)
0x180062f1e  mov     edx, r15d; int
0x180062f21  mov     rcx, rsi; HDDEDATA
0x180062f24  call    ?InternalFreeDataHandle@@YAHPEAUHDDEDATA__@@H@Z; InternalFreeDataHandle(HDDEDATA__ *,int)
0x180062f29  movzx   ecx, word ptr [rbp+80h+var_70+8]; nAtom
0x180062f2d  call    cs:__imp_DeleteAtom
0x180062f33  movzx   ecx, word ptr [rbp+80h+var_60]; nAtom
0x180062f37  call    cs:__imp_DeleteAtom
0x180062f3d  movzx   ecx, word ptr [rbp+80h+var_60+8]
0x180062f41  jmp     loc_180063057
0x180062f46  movups  xmm0, xmmword ptr [rbx+8]
0x180062f4a  mov     rax, [rbx+98h]
0x180062f51  movups  xmm1, xmmword ptr [rbx+18h]
0x180062f55  mov     rcx, [rbx+30h]; unsigned __int16
0x180062f59  movups  xmm2, xmmword ptr [rbx+28h]
0x180062f5d  mov     [rbp+80h+var_90], rax
0x180062f61  movups  xmmword ptr [rsp+180h+var_120], xmm0
0x180062f66  movups  xmm0, xmmword ptr [rbx+38h]
0x180062f6a  movups  [rsp+180h+var_110], xmm1
0x180062f6f  movups  xmm1, xmmword ptr [rbx+48h]
0x180062f73  movups  [rbp+80h+var_F0], xmm0
0x180062f77  movups  xmm0, xmmword ptr [rbx+58h]
0x180062f7b  movups  [rbp+80h+var_E0], xmm1
0x180062f7f  movups  xmm1, xmmword ptr [rbx+68h]
0x180062f83  movups  [rbp+80h+var_D0], xmm0
0x180062f87  movups  xmm0, xmmword ptr [rbx+78h]
0x180062f8b  movups  [rbp+80h+var_C0], xmm1
0x180062f8f  movups  xmm1, xmmword ptr [rbx+88h]
0x180062f96  movups  [rbp+80h+var_B0], xmm0
0x180062f9a  movups  [rbp+80h+var_A0], xmm1
0x180062f9e  movaps  [rbp+80h+var_100], xmm2
0x180062fa2  call    ?GlobalToLocalAtom@@YAGG@Z; GlobalToLocalAtom(ushort)
0x180062fa7  movzx   ecx, word ptr [rbp+80h+var_F0]; unsigned __int16
0x180062fab  movzx   eax, ax
0x180062fae  mov     qword ptr [rbp+80h+var_100+8], rax
0x180062fb2  call    ?GlobalToLocalAtom@@YAGG@Z; GlobalToLocalAtom(ushort)
0x180062fb7  cmp     dword ptr [rsp+180h+var_110+4], 80A2h
0x180062fbf  movzx   eax, ax
0x180062fc2  mov     qword ptr [rbp+80h+var_F0], rax
0x180062fc6  jz      short loc_180062FD2
0x180062fc8  cmp     dword ptr [rsp+180h+var_110+4], 80D2h
0x180062fd0  jnz     short loc_180062FDB
0x180062fd2  bts     rax, 10h
0x180062fd7  mov     qword ptr [rbp+80h+var_F0], rax
0x180062fdb  movzx   r8d, word ptr [rbx+6]; unsigned int
0x180062fe0  lea     rdx, [rsp+180h+var_120]; unsigned __int8 *
0x180062fe5  mov     word ptr [rsp+180h+hData], r14w; unsigned __int16
0x180062feb  xor     r9d, r9d; unsigned int
0x180062fee  mov     word ptr [rsp+180h+var_158], r14w; unsigned __int16
0x180062ff4  mov     rcx, rdi; struct tagCL_INSTANCE_INFO *
0x180062ff7  mov     [rsp+180h+BytesInMultiByteString], 0C100h; unsigned int
0x180062fff  call    ?InternalCreateDataHandle@@YAPEAUHDDEDATA__@@PEAUtagCL_INSTANCE_INFO@@PEAEKKKGG@Z; InternalCreateDataHandle(tagCL_INSTANCE_INFO *,uchar *,ulong,ulong,ulong,ushort,ushort)
0x180063004  mov     rsi, rax
0x180063007  test    rax, rax
0x18006300a  jz      loc_1800631BC
0x180063010  mov     ecx, [rbx]
0x180063012  xor     r8d, r8d; unsigned __int16
0x180063015  mov     [rsp+180h+var_140], rcx; unsigned __int64
0x18006301a  mov     edx, 80F2h; unsigned __int16
0x18006301f  mov     [rsp+180h+var_148], r14; unsigned __int64
0x180063024  xor     r9d, r9d; HCONV
0x180063027  mov     [rsp+180h+hData], rax; hData
0x18006302c  mov     rcx, rdi; struct tagCL_INSTANCE_INFO *
0x18006302f  mov     [rsp+180h+var_158], r14; HSZ
0x180063034  mov     qword ptr [rsp+180h+BytesInMultiByteString], r14; HSZ
0x180063039  call    ?DoCallback@@YAPEAUHDDEDATA__@@PEAUtagCL_INSTANCE_INFO@@GGPEAUHCONV__@@PEAUHSZ__@@2PEAU1@_K4@Z; DoCallback(tagCL_INSTANCE_INFO *,ushort,ushort,HCONV__ *,HSZ__ *,HSZ__ *,HDDEDATA__ *,unsigned __int64,unsigned __int64)
0x18006303e  mov     edx, r15d; int
0x180063041  mov     rcx, rsi; HDDEDATA
0x180063044  call    ?InternalFreeDataHandle@@YAHPEAUHDDEDATA__@@H@Z; InternalFreeDataHandle(HDDEDATA__ *,int)
0x180063049  movzx   ecx, word ptr [rbp+80h+var_100+8]; nAtom
0x18006304d  call    cs:__imp_DeleteAtom
0x180063053  movzx   ecx, word ptr [rbp+80h+var_F0]; nAtom
0x180063057  call    cs:__imp_DeleteAtom
0x18006305d  jmp     loc_1800631BC
0x180063062  cmp     [rdi+6Ch], r14w
0x180063067  jl      short loc_1800630CE
0x180063069  movzx   eax, word ptr [rbx+6]
0x18006306d  lea     r9, [rsp+180h+P]
0x180063072  sub     eax, [rbx+8]
0x180063075  lea     rdx, [rbx+28h]
0x180063079  movsxd  r8, eax
0x18006307c  xor     ecx, ecx
0x18006307e  shr     r8, 1
0x180063081  mov     dword ptr [rsp+180h+var_158], r15d
0x180063086  mov     [rsp+180h+P], r14
0x18006308b  mov     [rsp+180h+BytesInMultiByteString], eax
0x18006308f  call    WCSToMBEx
0x180063094  test    eax, eax
0x180063096  jz      short loc_1800630C7
0x180063098  movzx   eax, word ptr [rbx+6]
0x18006309c  lea     rcx, [rbx+28h]; char *
0x1800630a0  sub     eax, [rbx+8]
0x1800630a3  mov     r8, [rsp+180h+P]; char *
0x1800630a8  movsxd  rdx, eax
0x1800630ab  shr     rdx, 1; unsigned __int64
0x1800630ae  call    ?StringCbCopyA@@YAJPEAD_KPEBD@Z; StringCbCopyA(char *,unsigned __int64,char const *)
0x1800630b3  mov     r8, [rsp+180h+P]; P
0x1800630b8  xor     edx, edx; Flags
0x1800630ba  mov     rcx, cs:pUserHeap; HeapHandle
0x1800630c1  call    cs:__imp_RtlFreeHeap
0x1800630c7  mov     dword ptr [rbx+8], 28h ; '('
0x1800630ce  cmp     dword ptr [rbx], 4000000h
0x1800630d4  jnz     short loc_18006314B
0x1800630d6  cmp     dword ptr [rbx+28h], 3E8h
0x1800630dd  jnz     short loc_18006314B
0x1800630df  mov     ecx, 8000h
0x1800630e4  lea     rsi, [rbx+54h]
0x1800630e8  mov     al, [rsi]
0x1800630ea  test    [rdi+6Ch], cx
0x1800630ee  jz      short loc_180063117
0x1800630f0  test    al, al
0x1800630f2  jz      short loc_18006314B
0x1800630f4  mov     eax, [rbx+50h]
0x1800630f7  lea     rcx, [rbp+80h+UnicodeString]; UnicodeString
0x1800630fb  mov     edx, 20h ; ' '; MaxBytesInUnicodeString
0x180063100  mov     r9, rsi; MultiByteString
0x180063103  cmp     eax, edx
0x180063105  cmova   eax, edx
0x180063108  xor     r8d, r8d; BytesInUnicodeString
0x18006310b  mov     [rsp+180h+BytesInMultiByteString], eax; BytesInMultiByteString
0x18006310f  call    cs:__imp_RtlMultiByteToUnicodeN
0x180063115  jmp     short loc_18006313C
0x180063117  test    al, al
0x180063119  jnz     short loc_18006314B
0x18006311b  mov     eax, [rbx+50h]
0x18006311e  lea     rcx, [rbp+80h+UnicodeString]; MbString
0x180063122  mov     edx, 20h ; ' '; MbSize
0x180063127  mov     r9, rsi; UnicodeString
0x18006312a  cmp     eax, edx
0x18006312c  cmova   eax, edx
0x18006312f  xor     r8d, r8d; ResultSize
0x180063132  mov     [rsp+180h+BytesInMultiByteString], eax; UnicodeSize
0x180063136  call    cs:__imp_RtlUnicodeToMultiByteN
0x18006313c  movups  xmm0, xmmword ptr [rbp+80h+UnicodeString]
0x180063140  movups  xmm1, [rbp+80h+var_70]
0x180063144  movups  xmmword ptr [rsi], xmm0
0x180063147  movups  xmmword ptr [rsi+10h], xmm1
0x18006314b  movzx   r8d, word ptr [rbx+6]; unsigned int
0x180063150  lea     rdx, [rbx+8]; unsigned __int8 *
0x180063154  mov     word ptr [rsp+180h+hData], r14w; unsigned __int16
0x18006315a  xor     r9d, r9d; unsigned int
0x18006315d  mov     word ptr [rsp+180h+var_158], r14w; unsigned __int16
0x180063163  mov     rcx, rdi; struct tagCL_INSTANCE_INFO *
0x180063166  mov     [rsp+180h+BytesInMultiByteString], 0C100h; unsigned int
0x18006316e  call    ?InternalCreateDataHandle@@YAPEAUHDDEDATA__@@PEAUtagCL_INSTANCE_INFO@@PEAEKKKGG@Z; InternalCreateDataHandle(tagCL_INSTANCE_INFO *,uchar *,ulong,ulong,ulong,ushort,ushort)
0x180063173  mov     rsi, rax
0x180063176  test    rax, rax
0x180063179  jz      short loc_1800631BC
0x18006317b  mov     ecx, [rbx]
0x18006317d  xor     r8d, r8d; unsigned __int16
0x180063180  mov     [rsp+180h+var_140], rcx; unsigned __int64
0x180063185  mov     edx, 80F2h; unsigned __int16
0x18006318a  mov     [rsp+180h+var_148], r14; unsigned __int64
0x18006318f  xor     r9d, r9d; HCONV
0x180063192  mov     [rsp+180h+hData], rax; hData
0x180063197  mov     rcx, rdi; struct tagCL_INSTANCE_INFO *
0x18006319a  mov     [rsp+180h+var_158], r14; HSZ
0x18006319f  mov     qword ptr [rsp+180h+BytesInMultiByteString], r14; HSZ
0x1800631a4  call    ?DoCallback@@YAPEAUHDDEDATA__@@PEAUtagCL_INSTANCE_INFO@@GGPEAUHCONV__@@PEAUHSZ__@@2PEAU1@_K4@Z; DoCallback(tagCL_INSTANCE_INFO *,ushort,ushort,HCONV__ *,HSZ__ *,HSZ__ *,HDDEDATA__ *,unsigned __int64,unsigned __int64)
0x1800631a9  mov     edx, r15d; int
0x1800631ac  mov     rcx, rsi; HDDEDATA
0x1800631af  call    ?InternalFreeDataHandle@@YAHPEAUHDDEDATA__@@H@Z; InternalFreeDataHandle(HDDEDATA__ *,int)
0x1800631b4  jmp     short loc_1800631BC
0x1800631b6  mov     eax, [rbx+8]
0x1800631b9  mov     [rdi+18h], eax
0x1800631bc  lea     rcx, ?gcsDDEML@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x1800631c3  call    cs:__imp_RtlLeaveCriticalSection
0x1800631c9  xor     eax, eax
0x1800631cb  mov     rcx, [rbp+80h+var_30]
0x1800631cf  xor     rcx, rsp; StackCookie
0x1800631d2  call    __security_check_cookie
0x1800631d7  mov     rbx, [rsp+180h+arg_10]
0x1800631df  add     rsp, 160h
0x1800631e6  pop     r15
0x1800631e8  pop     r14
0x1800631ea  pop     rdi
0x1800631eb  pop     rsi
0x1800631ec  pop     rbp
0x1800631ed  retn
  ... truncated ...
```
