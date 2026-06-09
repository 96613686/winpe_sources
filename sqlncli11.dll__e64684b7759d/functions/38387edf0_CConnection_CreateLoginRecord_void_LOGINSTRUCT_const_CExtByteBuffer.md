# CConnection::CreateLoginRecord(void *,_LOGINSTRUCT const *,CExtByteBuffer *)

- ea: `0x38387edf0`
- end: `0x38387f19d`
- name: `?CreateLoginRecord@CConnection@@AEAAJPEAXPEBU_LOGINSTRUCT@@PEAVCExtByteBuffer@@@Z`
- size: `941`
- prototype: `__int64 __fastcall(CConnection *__hidden this, void *, const struct _LOGINSTRUCT *, struct CExtByteBuffer *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x383884e60`

## callees

- `0x3838427d0`
- `0x3838434c0`
- `0x3838435e0`
- `0x3838463a4`
- `0x38387d6c0`
- `0x38387edf0`
- `0x38387f1b0`
- `0x38391aed0`
- `0x38391afe0`
- `0x383ace860`
- `0x383ace8b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x38390e24f`
- `KERNEL32!GetLastError` at `0x38390e61f`
- `KERNEL32!GetLastError` at `0x38390e696`
- `KERNEL32!GetLastError` at `0x38390e24f`
- `KERNEL32!GetLastError` at `0x38390e61f`
- `KERNEL32!GetLastError` at `0x38390e696`
- `KERNEL32!GetTimeZoneInformation` at `0x38387eef9`
- `KERNEL32!GetTimeZoneInformation` at `0x38387eef9`
- `KERNEL32!GetCurrentProcessId` at `0x38387ee68`
- `KERNEL32!GetCurrentProcessId` at `0x38387ee68`

## pseudocode

```c
__int64 __fastcall CConnection::CreateLoginRecord(
        CConnection *this,
        void *a2,
        const struct _LOGINSTRUCT *a3,
        struct CExtByteBuffer *a4)
{
  __int64 v4; // r13
  int v9; // eax
  DWORD CurrentProcessId; // eax
  char v11; // cl
  char v12; // r8
  const wchar_t *v13; // rdi
  char v14; // r8
  __int64 v15; // rcx
  bool v16; // zf
  char v17; // dl
  _WORD *v18; // rsi
  const unsigned __int16 *v19; // r9
  int v20; // esi
  __int64 v21; // rbp
  _WORD *v22; // rdx
  __int64 v23; // rcx
  __int16 v24; // ax
  _WORD *v25; // rdi
  _WORD *v26; // rax
  _WORD *v27; // rdx
  __int64 v28; // rcx
  __int16 v29; // ax
  _WORD *v30; // rdx
  __int64 v31; // rdi
  unsigned __int64 v32; // rax
  __int64 v33; // rcx
  __int16 v34; // ax
  int v35; // eax
  const unsigned __int16 *v36; // r9
  int v37; // eax
  const unsigned __int16 *v38; // r9
  int v39; // eax
  const unsigned __int16 *v40; // r9
  _DWORD *v41; // rdx
  int v42; // eax
  __int64 v43; // rdi
  __int64 v44; // rax
  unsigned __int16 v45; // r9
  const void *v46; // rdx
  unsigned int v47; // ebp
  size_t v48; // r8
  int v49; // eax
  _WORD *v51; // rdx
  __int64 v52; // rcx
  __int16 v53; // ax
  __int64 v54; // rdi
  DWORD LastError; // eax
  wchar_t *v56; // r8
  __int64 v57; // rdx
  __int64 v58; // rcx
  __int16 v59; // ax
  int v60; // eax
  char *v61; // rcx
  __int64 i; // rdx
  char v63; // al
  __int16 v64; // ax
  DWORD v65; // eax
  __int64 v66; // rdi
  DWORD v67; // eax
  __int16 v68; // ax
  char *v69; // rcx
  __int64 j; // rdx
  char v71; // al
  __int64 v72; // [rsp+20h] [rbp-258h]
  int v73; // [rsp+30h] [rbp-248h]
  int v74; // [rsp+38h] [rbp-240h]
  size_t Size[2]; // [rsp+40h] [rbp-238h] BYREF
  _TIME_ZONE_INFORMATION TimeZoneInformation; // [rsp+50h] [rbp-228h] BYREF
  _WORD Src[144]; // [rsp+100h] [rbp-178h] BYREF

  v4 = *((_QWORD *)a4 + 4);
  *((_QWORD *)a4 + 1) = 94;
  memset((void *)v4, 0, 0x5Eu);
  *(_DWORD *)(v4 + 4) = *((unsigned __int16 *)this + 621) | (*((unsigned __int16 *)this + 620) << 16);
  v9 = *((_DWORD *)a3 + 32);
  *(_DWORD *)(v4 + 12) = 117440512;
  *(_DWORD *)(v4 + 8) = v9;
  CurrentProcessId = GetCurrentProcessId();
  *(_BYTE *)(v4 + 24) &= 0xFCu;
  v11 = *(_BYTE *)(v4 + 24);
  v12 = *(_BYTE *)(v4 + 25);
  *(_DWORD *)(v4 + 16) = CurrentProcessId;
  *(_DWORD *)(v4 + 20) = 0;
  v13 = L"ODBC";
  LOBYTE(CurrentProcessId) = *((_DWORD *)a3 + 44) != 0;
  *(_BYTE *)(v4 + 26) &= 0xF0u;
  v14 = v12 & 0xFA | 1;
  LOBYTE(CurrentProcessId) = v11 & 3 | (16 * (CurrentProcessId | 0xFE));
  *(_BYTE *)(v4 + 25) = v14;
  v15 = 5;
  *(_BYTE *)(v4 + 24) = CurrentProcessId;
  v17 = *(_BYTE *)(v4 + 26) ^ (*(_BYTE *)(v4 + 26) ^ (32 * (*((_DWORD *)a3 + 55) == 1))) & 0x20;
  v16 = v17 == 0;
  *(_BYTE *)(v4 + 26) = v17;
  v18 = (_WORD *)*((_QWORD *)a3 + 12);
  do
  {
    if ( !v15 )
      break;
    v16 = *v18++ == *v13++;
    --v15;
  }
  while ( v16 );
  if ( v16 )
    *(_BYTE *)(v4 + 25) = v14 | 2;
  else
    *(_BYTE *)(v4 + 26) = v17 | 0x10;
  if ( GetTimeZoneInformation(&TimeZoneInformation) != -1 )
    *(_DWORD *)(v4 + 28) = TimeZoneInformation.Bias;
  v20 = 0;
  v21 = -1;
  *(_DWORD *)(v4 + 32) = *((_DWORD *)a3 + 47);
  v22 = (_WORD *)*((_QWORD *)a3 + 7);
  if ( v22 )
  {
    v23 = -1;
    do
      ++v23;
    while ( v22[v23] );
  }
  else
  {
    LOWORD(v23) = 0;
  }
  v24 = *((_WORD *)a4 + 4);
  *(_WORD *)(v4 + 38) = v23;
  *(_WORD *)(v4 + 36) = v24;
  if ( (_WORD)v23 )
    v20 = CExtByteBuffer::WriteIntoExtBuffer(a4, v22, 2LL * (unsigned __int16)v23);
  if ( v20 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
      bidTraceW(off_383B435A0[0], 1372201, off_383B49128[0], (unsigned int)v20);
    return (unsigned int)v20;
  }
  v25 = (_WORD *)*((_QWORD *)a4 + 4);
  if ( !*((_DWORD *)a3 + 33) || (v26 = (_WORD *)*((_QWORD *)a3 + 9)) != 0 && *v26 )
  {
    v51 = (_WORD *)*((_QWORD *)a3 + 4);
    v20 = 0;
    if ( v51 )
    {
      v52 = -1;
      do
        ++v52;
      while ( v51[v52] );
    }
    else
    {
      LOWORD(v52) = 0;
    }
    v53 = *((_WORD *)a4 + 4);
    v25[21] = v52;
    v25[20] = v53;
    if ( (_WORD)v52 )
      v20 = CExtByteBuffer::WriteIntoExtBuffer(a4, v51, 2LL * (unsigned __int16)v52);
    if ( v20 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
        bidTraceHR(off_383B435A0[0], 1379337, (unsigned int)v20);
      return (unsigned int)v20;
    }
    v54 = *((_QWORD *)a4 + 4);
    if ( g_pfnCryptUnprotectMemory )
    {
      memcpy(Src, *((const void **)a3 + 5), sizeof(Src));
      if ( !(unsigned int)((__int64 (__fastcall *)(_WORD *, __int64, _QWORD))g_pfnCryptUnprotectMemory)(Src, 288, 0) )
      {
        if ( (bidGblFlags & 2) != 0 && off_383B4A5D8[0] )
        {
          LastError = GetLastError();
          bidTraceW(off_383B435A0[0], 1402880, off_383B4A5D8[0], LastError);
        }
        v20 = -2147467259;
        if ( (bidGblFlags & 2) == 0 || !off_383B4A5D0[0] )
          goto LABEL_128;
        v56 = off_383B4A5D0[0];
        v57 = 1404928;
LABEL_127:
        v74 = -2147467259;
        v73 = 40488;
        HIDWORD(v72) = HIDWORD(a2);
        bidTraceW(off_383B435A0[0], v57, v56, this);
LABEL_128:
        v66 = *((_QWORD *)this + 157);
        v67 = GetLastError();
        LODWORD(v72) = -2147467259;
        CTdsParser::PostFormattedParserErrorEx(v66, a2, 3, 40488, v72, v67, v73, v74);
        return (unsigned int)v20;
      }
      v20 = 0;
      v58 = -1;
      do
        ++v58;
      while ( Src[v58] );
      v59 = *((_WORD *)a4 + 4);
      *(_WORD *)(v54 + 46) = v58;
      *(_WORD *)(v54 + 44) = v59;
      if ( (_WORD)v58 )
        v20 = CExtByteBuffer::WriteIntoExtBuffer(a4, Src, 2LL * (unsigned __int16)v58);
      memset(Src, 0, sizeof(Src));
      if ( v20 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
          bidTraceHR(off_383B435A0[0], 1416201, (unsigned int)v20);
        return (unsigned int)v20;
      }
    }
    else
    {
      v60 = CConnection::AddToLoginRec(a4, (struct CExtByteBuffer *)(v54 + 44), *((struct OFFLEN **)a3 + 5), v19);
      v20 = v60;
      if ( v60 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
          bidTraceHR(off_383B435A0[0], 1421321, (unsigned int)v60);
        return (unsigned int)v20;
      }
    }
    v25 = (_WORD *)*((_QWORD *)a4 + 4);
    v61 = (char *)v25 + (unsigned __int16)v25[22];
    for ( i = 2LL * (unsigned __int16)v25[23]; i; --i )
    {
      v63 = *v61++;
      *(v61 - 1) = __ROL1__(v63, 4) ^ 0xA5;
    }
  }
  v27 = (_WORD *)*((_QWORD *)a3 + 11);
  v20 = 0;
  if ( v27 )
  {
    v28 = -1;
    do
      ++v28;
    while ( v27[v28] );
  }
  else
  {
    LOWORD(v28) = 0;
  }
  v29 = *((_WORD *)a4 + 4);
  v25[25] = v28;
  v25[24] = v29;
  if ( (_WORD)v28 )
    v20 = CExtByteBuffer::WriteIntoExtBuffer(a4, v27, 2LL * (unsigned __int16)v28);
  if ( v20 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
      bidTraceHR(off_383B435A0[0], 1431561, (unsigned int)v20);
    return (unsigned int)v20;
  }
  v30 = (_WORD *)*((_QWORD *)a3 + 9);
  v31 = *((_QWORD *)a4 + 4);
  if ( v30 && *v30 )
  {
    *(_BYTE *)(v31 + 25) &= 0xAFu;
    *(_BYTE *)(v31 + 25) |= 0x20u;
  }
  else
  {
    v30 = (_WORD *)*((_QWORD *)a3 + 10);
    if ( v30 && *v30 )
    {
      *(_BYTE *)(v31 + 25) &= ~0x40u;
      *(_BYTE *)(v31 + 25) |= 0x30u;
    }
    else
    {
      v30 = (_WORD *)*((_QWORD *)a3 + 8);
      *(_BYTE *)(v31 + 25) &= 0x8Fu;
    }
  }
  if ( v30 && (*(_BYTE *)(v31 + 25) & 0x70) == 0 )
  {
    v32 = -1;
    do
      ++v32;
    while ( v30[v32] );
    LOWORD(v33) = 128;
    if ( v32 < 0x80 )
    {
      v33 = -1;
      do
        ++v33;
      while ( v30[v33] );
    }
    v34 = *((_WORD *)a4 + 4);
    *(_WORD *)(v31 + 54) = v33;
    *(_WORD *)(v31 + 52) = v34;
    goto LABEL_33;
  }
  v20 = 0;
  if ( v30 )
  {
    v33 = -1;
    do
      ++v33;
    while ( v30[v33] );
  }
  else
  {
    LOWORD(v33) = 0;
  }
  v64 = *((_WORD *)a4 + 4);
  *(_WORD *)(v31 + 54) = v33;
  *(_WORD *)(v31 + 52) = v64;
  if ( (_WORD)v33 )
LABEL_33:
    v20 = CExtByteBuffer::WriteIntoExtBuffer(a4, v30, 2LL * (unsigned __int16)v33);
  if ( v20 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
      bidTraceHR(off_383B435A0[0], 1464329, (unsigned int)v20);
  }
  else
  {
    v35 = CConnection::AddToLoginRec(
            a4,
            (struct CExtByteBuffer *)(*((_QWORD *)a4 + 4) + 60LL),
            *((struct OFFLEN **)a3 + 12),
            v19);
    v20 = v35;
    if ( v35 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
        bidTraceHR(off_383B435A0[0], 1468425, (unsigned int)v35);
    }
    else
    {
      v37 = CConnection::AddToLoginRec(
              a4,
              (struct CExtByteBuffer *)(*((_QWORD *)a4 + 4) + 64LL),
              *((struct OFFLEN **)a3 + 3),
              v36);
      v20 = v37;
      if ( v37 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
          bidTraceHR(off_383B435A0[0], 1472521, (unsigned int)v37);
      }
      else
      {
        v39 = CConnection::AddToLoginRec(
                a4,
                (struct CExtByteBuffer *)(*((_QWORD *)a4 + 4) + 68LL),
                *((struct OFFLEN **)a3 + 2),
                v38);
        v20 = v39;
        if ( v39 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
            bidTraceHR(off_383B435A0[0], 1476617, (unsigned int)v39);
        }
        else
        {
          v41 = (_DWORD *)*((_QWORD *)a4 + 4);
          v41[18] = *((_DWORD *)a3 + 48);
          v41 = (_DWORD *)((char *)v41 + 82);
          *((_WORD *)v41 - 3) = *((_WORD *)a3 + 98);
          v42 = CConnection::AddToLoginRec(a4, (struct CExtByteBuffer *)v41, *((struct OFFLEN **)a3 + 13), v40);
          v20 = v42;
          if ( v42 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 )
              bidTraceHR(off_383B435A0[0], 1484809, (unsigned int)v42);
          }
          else
          {
            v43 = *((_QWORD *)a4 + 4);
            if ( *((_DWORD *)a3 + 33) )
            {
              *(_BYTE *)(v43 + 25) |= 0x80u;
              v44 = ((__int64 (__fastcall *)(struct IMalloc *, _QWORD))g_pMO->lpVtbl[1].Free)(
                      g_pMO,
                      *(unsigned int *)(*((_QWORD *)this + 157) + 172LL));
              *((_QWORD *)this + 9) = v44;
              if ( v44 )
              {
                v20 = CConnection::GenClientContext(this, 0, 0, (unsigned int *)Size);
                if ( v20 < 0 )
                {
                  if ( (bidGblFlags & 2) != 0 && off_383B4A5C0[0] )
                    bidTraceW(off_383B435A0[0], 1507328, off_383B4A5C0[0], this);
                  CTdsParser::PostSNIErrorEx(
                    *((CTdsParser **)this + 157),
                    *(struct CConnection **)(*((_QWORD *)this + 2) + 96LL),
                    (void *)0x9D25,
                    v45);
                }
                else
                {
                  v46 = (const void *)*((_QWORD *)this + 9);
                  v47 = Size[0];
                  v48 = LODWORD(Size[0]);
                  *(_WORD *)(v43 + 78) = *((_WORD *)a4 + 4);
                  *(_WORD *)(v43 + 80) = v47;
                  v49 = CExtByteBuffer::WriteIntoExtBuffer(a4, v46, v48);
                  v20 = v49;
                  if ( v49 >= 0 )
                  {
                    v43 = *((_QWORD *)a4 + 4);
                    if ( v47 > 0xFFFF )
                    {
                      *(_WORD *)(v43 + 80) = -1;
                      *(_DWORD *)(v43 + 90) = v47;
                    }
                    goto LABEL_45;
                  }
                  if ( (bidGblFlags & 2) != 0 )
                    bidTraceHR(off_383B435A0[0], 1518601, (unsigned int)v49);
                }
              }
              else
              {
                v20 = -2147024882;
                if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
                  bidTraceW(off_383B435A0[0], 1502249, off_383B49128[0], 2147942414LL);
              }
            }
            else
            {
              *(_BYTE *)(v43 + 25) &= ~0x80u;
              if ( !*((_QWORD *)a3 + 6) )
              {
LABEL_45:
                *(_DWORD *)v43 = *((_DWORD *)a4 + 2);
                return (unsigned int)v20;
              }
              *(_BYTE *)(v43 + 27) |= 1u;
              *((_DWORD *)this + 103) = 1;
              memcpy(Src, *((const void **)a3 + 6), sizeof(Src));
              if ( g_pfnCryptUnprotectMemory && !g_pfnCryptUnprotectMemory(Src, 0x120u, 0) )
              {
                if ( (bidGblFlags & 2) != 0 && off_383B4A5C8[0] )
                {
                  v65 = GetLastError();
                  bidTraceW(off_383B435A0[0], 1555456, off_383B4A5C8[0], v65);
                }
                v20 = -2147467259;
                if ( (bidGblFlags & 2) == 0 || !off_383B4A5B8[0] )
                  goto LABEL_128;
                v56 = off_383B4A5B8[0];
                v57 = 1557504;
                goto LABEL_127;
              }
              v20 = 0;
              do
                ++v21;
              while ( Src[v21] );
              v68 = *((_WORD *)a4 + 4);
              *(_WORD *)(v43 + 88) = v21;
              *(_WORD *)(v43 + 86) = v68;
              if ( (_WORD)v21 )
                v20 = CExtByteBuffer::WriteIntoExtBuffer(a4, Src, 2LL * (unsigned __int16)v21);
              memset(Src, 0, sizeof(Src));
              if ( v20 >= 0 )
              {
                v43 = *((_QWORD *)a4 + 4);
                v69 = (char *)(v43 + *(unsigned __int16 *)(v43 + 86));
                for ( j = 2LL * *(unsigned __int16 *)(v43 + 88); j; --j )
                {
                  v71 = *v69++;
                  *(v69 - 1) = __ROL1__(v71, 4) ^ 0xA5;
                }
                goto LABEL_45;
              }
              if ( (bidGblFlags & 2) != 0 )
                bidTraceHR(off_383B435A0[0], 1569801, (unsigned int)v20);
            }
          }
        }
      }
    }
  }
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x38387edf0  push    rbx
0x38387edf2  push    rbp
0x38387edf3  push    rsi
0x38387edf4  push    rdi
0x38387edf5  push    r12
0x38387edf7  push    r13
0x38387edf9  push    r14
0x38387edfb  push    r15
0x38387edfd  sub     rsp, 238h
0x38387ee04  mov     rax, cs:__security_cookie
0x38387ee0b  xor     rax, rsp
0x38387ee0e  mov     [rsp+278h+var_58], rax
0x38387ee16  mov     r13, [r9+20h]
0x38387ee1a  mov     r12, rdx
0x38387ee1d  xor     edx, edx; Val
0x38387ee1f  mov     r14, r8
0x38387ee22  mov     r15, rcx
0x38387ee25  lea     r8d, [rdx+5Eh]; Size
0x38387ee29  mov     rcx, r13; void *
0x38387ee2c  mov     rbx, r9
0x38387ee2f  mov     qword ptr [r9+8], 5Eh ; '^'
0x38387ee37  call    memset
0x38387ee3c  movzx   eax, word ptr [r15+4DAh]
0x38387ee44  movzx   edx, word ptr [r15+4D8h]
0x38387ee4c  shl     edx, 10h
0x38387ee4f  or      edx, eax
0x38387ee51  mov     [r13+4], edx
0x38387ee55  mov     eax, [r14+80h]
0x38387ee5c  mov     dword ptr [r13+0Ch], 7000000h
0x38387ee64  mov     [r13+8], eax
0x38387ee68  call    cs:__imp_GetCurrentProcessId
0x38387ee6e  and     byte ptr [r13+18h], 0FCh
0x38387ee73  movzx   ecx, byte ptr [r13+18h]
0x38387ee78  movzx   r8d, byte ptr [r13+19h]
0x38387ee7d  mov     [r13+10h], eax
0x38387ee81  mov     dword ptr [r13+14h], 0
0x38387ee89  cmp     dword ptr [r14+0B0h], 0
0x38387ee91  lea     rdi, aOdbc; "ODBC"
0x38387ee98  setnz   al
0x38387ee9b  and     byte ptr [r13+1Ah], 0F0h
0x38387eea0  and     cl, 3
0x38387eea3  or      al, 0FEh
0x38387eea5  and     r8b, 0FBh
0x38387eea9  shl     al, 4
0x38387eeac  or      r8b, 1
0x38387eeb0  or      al, cl
0x38387eeb2  mov     [r13+19h], r8b
0x38387eeb6  mov     ecx, 5
0x38387eebb  mov     [r13+18h], al
0x38387eebf  cmp     dword ptr [r14+0DCh], 1
0x38387eec7  movzx   eax, byte ptr [r13+1Ah]
0x38387eecc  setz    dl
0x38387eecf  shl     dl, 5
0x38387eed2  xor     dl, al
0x38387eed4  and     dl, 20h
0x38387eed7  xor     dl, al
0x38387eed9  mov     [r13+1Ah], dl
0x38387eedd  mov     rsi, [r14+60h]
0x38387eee1  repe cmpsw
0x38387eee4  jnz     loc_38388796B
0x38387eeea  or      r8b, 2
0x38387eeee  mov     [r13+19h], r8b
0x38387eef2  jmp     short $+2
0x38387eef4  lea     rcx, [rsp+278h+TimeZoneInformation]; lpTimeZoneInformation
0x38387eef9  call    cs:__imp_GetTimeZoneInformation
0x38387eeff  cmp     eax, 0FFFFFFFFh
0x38387ef02  jz      short loc_38387EF0C
0x38387ef04  mov     eax, [rsp+278h+TimeZoneInformation.Bias]
0x38387ef08  mov     [r13+1Ch], eax
0x38387ef0c  mov     eax, [r14+0BCh]
0x38387ef13  xor     esi, esi
0x38387ef15  or      rbp, 0FFFFFFFFFFFFFFFFh
0x38387ef19  mov     [r13+20h], eax
0x38387ef1d  mov     rdx, [r14+38h]; Src
0x38387ef21  test    rdx, rdx
0x38387ef24  jz      loc_38390E139
0x38387ef2a  mov     rcx, rbp
0x38387ef2d  nop     dword ptr [rax]
0x38387ef30  inc     rcx
0x38387ef33  cmp     [rdx+rcx*2], si
0x38387ef37  jnz     short loc_38387EF30
0x38387ef39  jmp     short $+2
0x38387ef3b  movzx   eax, word ptr [rbx+8]
0x38387ef3f  mov     [r13+26h], cx
0x38387ef44  mov     [r13+24h], ax
0x38387ef49  test    cx, cx
0x38387ef4c  jz      short loc_38387EF5F
0x38387ef4e  movzx   r8d, cx
0x38387ef52  mov     rcx, rbx; this
0x38387ef55  add     r8, r8; Size
0x38387ef58  call    ?WriteIntoExtBuffer@CExtByteBuffer@@QEAAJPEBX_K@Z; CExtByteBuffer::WriteIntoExtBuffer(void const *,unsigned __int64)
0x38387ef5d  mov     esi, eax
0x38387ef5f  test    esi, esi
0x38387ef61  js      loc_38390E140
0x38387ef67  cmp     dword ptr [r14+84h], 0
0x38387ef6f  mov     rdi, [rbx+20h]
0x38387ef73  jz      loc_38390E185
0x38387ef79  mov     rax, [r14+48h]
0x38387ef7d  test    rax, rax
0x38387ef80  jnz     loc_383887977
0x38387ef86  mov     rdx, [r14+58h]; Src
0x38387ef8a  xor     esi, esi
0x38387ef8c  test    rdx, rdx
0x38387ef8f  jz      loc_38390E395
0x38387ef95  mov     rcx, rbp
0x38387ef98  inc     rcx
0x38387ef9b  cmp     [rdx+rcx*2], si
0x38387ef9f  jnz     short loc_38387EF98
0x38387efa1  jmp     short $+2
0x38387efa3  movzx   eax, word ptr [rbx+8]
0x38387efa7  mov     [rdi+32h], cx
0x38387efab  mov     [rdi+30h], ax
0x38387efaf  test    cx, cx
0x38387efb2  jnz     loc_3838A3813
0x38387efb8  test    esi, esi
0x38387efba  js      loc_38390E39C
0x38387efc0  mov     rdx, [r14+48h]
0x38387efc4  mov     rdi, [rbx+20h]
0x38387efc8  test    rdx, rdx
0x38387efcb  jnz     loc_383887986
0x38387efd1  mov     rdx, [r14+50h]
0x38387efd5  test    rdx, rdx
0x38387efd8  jnz     loc_383887995
0x38387efde  mov     rdx, [r14+40h]; Src
0x38387efe2  and     byte ptr [rdi+19h], 8Fh
0x38387efe6  test    rdx, rdx
0x38387efe9  jz      loc_38390E3DC
0x38387efef  test    byte ptr [rdi+19h], 70h
0x38387eff3  jnz     loc_38390E3DC
0x38387eff9  mov     rax, rbp
0x38387effc  inc     rax
0x38387efff  cmp     word ptr [rdx+rax*2], 0
0x38387f004  jnz     short loc_38387EFFC
0x38387f006  mov     ecx, 80h
0x38387f00b  cmp     rax, rcx
0x38387f00e  jnb     short loc_38387F02A
0x38387f010  mov     rcx, rbp
0x38387f013  nop     dword ptr [rax+00000000h]
0x38387f01a  nop     word ptr [rax+rax+00h]
0x38387f020  inc     rcx
0x38387f023  cmp     word ptr [rdx+rcx*2], 0
0x38387f028  jnz     short loc_38387F020
0x38387f02a  movzx   eax, word ptr [rbx+8]
0x38387f02e  mov     [rdi+36h], cx
0x38387f032  mov     [rdi+34h], ax
0x38387f036  jmp     short $+2
0x38387f038  movzx   r8d, cx
0x38387f03c  mov     rcx, rbx; this
0x38387f03f  add     r8, r8; Size
0x38387f042  call    ?WriteIntoExtBuffer@CExtByteBuffer@@QEAAJPEBX_K@Z; CExtByteBuffer::WriteIntoExtBuffer(void const *,unsigned __int64)
0x38387f047  mov     esi, eax
0x38387f049  test    esi, esi
0x38387f04b  js      loc_38390E40D
0x38387f051  mov     rdx, [rbx+20h]
0x38387f055  mov     r8, [r14+60h]; struct OFFLEN *
0x38387f059  mov     rcx, rbx; this
0x38387f05c  add     rdx, 3Ch ; '<'; struct CExtByteBuffer *
0x38387f060  call    ?AddToLoginRec@CConnection@@AEAAJPEAVCExtByteBuffer@@PEAUOFFLEN@@PEBG@Z; CConnection::AddToLoginRec(CExtByteBuffer *,OFFLEN *,ushort const *)
0x38387f065  mov     esi, eax
0x38387f067  test    eax, eax
0x38387f069  js      loc_38390E433
0x38387f06f  mov     rdx, [rbx+20h]
0x38387f073  mov     r8, [r14+18h]; struct OFFLEN *
0x38387f077  mov     rcx, rbx; this
0x38387f07a  add     rdx, 40h ; '@'; struct CExtByteBuffer *
0x38387f07e  call    ?AddToLoginRec@CConnection@@AEAAJPEAVCExtByteBuffer@@PEAUOFFLEN@@PEBG@Z; CConnection::AddToLoginRec(CExtByteBuffer *,OFFLEN *,ushort const *)
0x38387f083  mov     esi, eax
0x38387f085  test    eax, eax
0x38387f087  js      loc_38390E459
0x38387f08d  mov     rdx, [rbx+20h]
0x38387f091  mov     r8, [r14+10h]; struct OFFLEN *
0x38387f095  mov     rcx, rbx; this
0x38387f098  add     rdx, 44h ; 'D'; struct CExtByteBuffer *
0x38387f09c  call    ?AddToLoginRec@CConnection@@AEAAJPEAVCExtByteBuffer@@PEAUOFFLEN@@PEBG@Z; CConnection::AddToLoginRec(CExtByteBuffer *,OFFLEN *,ushort const *)
0x38387f0a1  mov     esi, eax
0x38387f0a3  test    eax, eax
0x38387f0a5  js      loc_38390E47F
0x38387f0ab  mov     rdx, [rbx+20h]
0x38387f0af  mov     eax, [r14+0C0h]
0x38387f0b6  mov     rcx, rbx; this
0x38387f0b9  mov     [rdx+48h], eax
0x38387f0bc  movzx   eax, word ptr [r14+0C4h]
0x38387f0c4  add     rdx, 52h ; 'R'; struct CExtByteBuffer *
0x38387f0c8  mov     [rdx-6], ax
0x38387f0cc  mov     r8, [r14+68h]; struct OFFLEN *
0x38387f0d0  call    ?AddToLoginRec@CConnection@@AEAAJPEAVCExtByteBuffer@@PEAUOFFLEN@@PEBG@Z; CConnection::AddToLoginRec(CExtByteBuffer *,OFFLEN *,ushort const *)
0x38387f0d5  mov     esi, eax
0x38387f0d7  test    eax, eax
0x38387f0d9  js      loc_38390E4A5
0x38387f0df  cmp     dword ptr [r14+84h], 0
0x38387f0e7  mov     rdi, [rbx+20h]
0x38387f0eb  jz      loc_38390E5AB
0x38387f0f1  or      byte ptr [rdi+19h], 80h
0x38387f0f5  mov     rax, [r15+4E8h]
0x38387f0fc  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x38387f103  mov     edx, [rax+0ACh]
0x38387f109  mov     rax, [rcx]
0x38387f10c  call    qword ptr [rax+70h]
0x38387f10f  mov     [r15+48h], rax
0x38387f113  test    rax, rax
0x38387f116  jz      loc_38390E4CB
0x38387f11c  lea     r9, [rsp+278h+Size]; unsigned int *
0x38387f121  xor     r8d, r8d; unsigned __int64
0x38387f124  xor     edx, edx; unsigned __int8 *
0x38387f126  mov     rcx, r15; this
0x38387f129  call    ?GenClientContext@CConnection@@AEAAJPEAE_KPEAK@Z; CConnection::GenClientContext(uchar *,unsigned __int64,ulong *)
0x38387f12e  mov     esi, eax
0x38387f130  test    eax, eax
0x38387f132  js      loc_38390E515
0x38387f138  movzx   eax, word ptr [rbx+8]
0x38387f13c  mov     rdx, [r15+48h]; Src
0x38387f140  mov     ebp, dword ptr [rsp+278h+Size]
0x38387f144  mov     r8d, ebp; Size
0x38387f147  mov     rcx, rbx; this
0x38387f14a  mov     [rdi+4Eh], ax
0x38387f14e  mov     [rdi+50h], bp
0x38387f152  call    ?WriteIntoExtBuffer@CExtByteBuffer@@QEAAJPEBX_K@Z; CExtByteBuffer::WriteIntoExtBuffer(void const *,unsigned __int64)
0x38387f157  mov     esi, eax
0x38387f159  test    eax, eax
0x38387f15b  js      loc_38390E579
0x38387f161  mov     rdi, [rbx+20h]
0x38387f165  mov     eax, 0FFFFh
0x38387f16a  cmp     ebp, eax
0x38387f16c  ja      loc_38390E59F
0x38387f172  mov     eax, [rbx+8]
0x38387f175  mov     [rdi], eax
0x38387f177  mov     eax, esi
0x38387f179  mov     rcx, [rsp+278h+var_58]
0x38387f181  xor     rcx, rsp; StackCookie
0x38387f184  call    __security_check_cookie
0x38387f189  add     rsp, 238h
0x38387f190  pop     r15
0x38387f192  pop     r14
0x38387f194  pop     r13
0x38387f196  pop     r12
0x38387f198  pop     rdi
0x38387f199  pop     rsi
0x38387f19a  pop     rbp
0x38387f19b  pop     rbx
0x38387f19c  retn
0x38388796b  or      dl, 10h
0x38388796e  mov     [r13+1Ah], dl
0x383887972  jmp     loc_38387EEF4
0x383887977  cmp     word ptr [rax], 0
0x38388797b  jz      loc_38387EF86
0x383887981  jmp     loc_38390E185
0x383887986  cmp     word ptr [rdx], 0
0x38388798a  jz      loc_38387EFD1
0x383887990  jmp     loc_38390E3C2
0x383887995  cmp     word ptr [rdx], 0
0x383887999  jz      loc_38387EFDE
0x38388799f  jmp     loc_38390E3CF
0x3838a3813  movzx   r8d, cx
0x3838a3817  mov     rcx, rbx; this
0x3838a381a  add     r8, r8; Size
0x3838a381d  call    ?WriteIntoExtBuffer@CExtByteBuffer@@QEAAJPEBX_K@Z; CExtByteBuffer::WriteIntoExtBuffer(void const *,unsigned __int64)
0x3838a3822  mov     esi, eax
0x3838a3824  jmp     loc_38387EFB8
0x38390e139  xor     ecx, ecx
0x38390e13b  jmp     loc_38387EF3B
0x38390e140  test    byte ptr cs:_bidGblFlags, 2
0x38390e147  jz      loc_38387F177
0x38390e14d  mov     rcx, cs:off_383B435A0; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x38390e154  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x38390e15b  test    rax, rax
0x38390e15e  jz      loc_38387F177
0x38390e164  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x38390e16b  mov     r9d, esi
0x38390e16e  mov     edx, 14F029h
0x38390e173  mov     dword ptr [rsp+278h+var_258], 53Ch
0x38390e17b  call    _bidTraceW
0x38390e180  jmp     loc_38387F177
0x38390e185  mov     rdx, [r14+20h]; Src
0x38390e189  xor     esi, esi
0x38390e18b  test    rdx, rdx
0x38390e18e  jz      short loc_38390E1AB
0x38390e190  mov     rcx, rbp
0x38390e193  nop     dword ptr [rax+00000000h]
0x38390e19a  nop     word ptr [rax+rax+00h]
0x38390e1a0  inc     rcx
0x38390e1a3  cmp     [rdx+rcx*2], si
0x38390e1a7  jnz     short loc_38390E1A0
0x38390e1a9  jmp     short loc_38390E1AD
0x38390e1ab  xor     ecx, ecx
0x38390e1ad  movzx   eax, word ptr [rbx+8]
0x38390e1b1  mov     [rdi+2Ah], cx
0x38390e1b5  mov     [rdi+28h], ax
0x38390e1b9  test    cx, cx
0x38390e1bc  jz      short loc_38390E1CF
0x38390e1be  movzx   r8d, cx
0x38390e1c2  mov     rcx, rbx; this
0x38390e1c5  add     r8, r8; Size
0x38390e1c8  call    ?WriteIntoExtBuffer@CExtByteBuffer@@QEAAJPEBX_K@Z; CExtByteBuffer::WriteIntoExtBuffer(void const *,unsigned __int64)
0x38390e1cd  mov     esi, eax
0x38390e1cf  test    esi, esi
0x38390e1d1  jns     short loc_38390E1F9
0x38390e1d3  test    byte ptr cs:_bidGblFlags, 2
0x38390e1da  jz      loc_38387F177
0x38390e1e0  mov     rcx, cs:off_383B435A0; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x38390e1e7  mov     r8d, esi
  ... truncated ...
```
