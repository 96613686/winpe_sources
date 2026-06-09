# bcpLog(tagDBC *,ushort,int)

- ea: `0x3839804e0`
- end: `0x383981186`
- name: `?bcpLog@@YAFPEAUtagDBC@@GH@Z`
- size: `3238`
- prototype: `__int16 __fastcall(struct tagDBC *, unsigned __int16, int)`
- caller_count: `3`
- callee_count: `19`
- tags: `file_ops`

## callers

- `0x383974c60`
- `0x383976ea0`
- `0x383978590`

## callees

- `0x3838427d0`
- `0x3838434c0`
- `0x3838435e0`
- `0x38386d3c0`
- `0x38387e070`
- `0x383884bb0`
- `0x38388f760`
- `0x38389a4e0`
- `0x38391aed0`
- `0x383968a90`
- `0x383968ae0`
- `0x383974210`
- `0x383976a90`
- `0x383980420`
- `0x3839804e0`
- `0x383986b80`
- `0x383986bc0`
- `0x38398cad0`
- `0x383a9f040`

## import_xrefs

- `MSVCR100!strerror` at `0x383980646`
- `MSVCR100!strerror` at `0x383980646`
- `MSVCR100!_errno` at `0x3839805f4`
- `MSVCR100!_errno` at `0x38398063e`
- `MSVCR100!_errno` at `0x3839805f4`
- `MSVCR100!_errno` at `0x38398063e`
- `KERNEL32!WriteFile` at `0x383980ed4`
- `KERNEL32!WriteFile` at `0x383980ed4`
- `USER32!LoadStringA` at `0x38398062e`
- `USER32!LoadStringA` at `0x3839808a2`
- `USER32!LoadStringA` at `0x38398062e`
- `USER32!LoadStringA` at `0x3839808a2`
- `USER32!CharToOemA` at `0x38398069c`
- `USER32!CharToOemA` at `0x38398069c`

## pseudocode

```c
__int64 __fastcall bcpLog(struct tagDBC *a1, unsigned __int16 a2, int a3)
{
  __int16 v3; // r15
  __int64 *v4; // r14
  __int64 *v5; // rbp
  unsigned __int16 v7; // r13
  struct tagDBC *v8; // rsi
  char *v9; // r12
  const unsigned __int8 *v10; // r9
  CHAR *v11; // r11
  int *v12; // rax
  const unsigned __int8 *v13; // r9
  __int64 v14; // rax
  bool v15; // zf
  __int16 v16; // r13
  unsigned __int16 v17; // bx
  struct BCPFILE *v18; // rdx
  __int64 v19; // rax
  char *v20; // rsi
  __int64 v21; // r13
  __int16 v22; // bp
  __int64 v23; // rbx
  __int64 v24; // rdi
  unsigned __int16 v25; // ax
  __int64 v26; // rcx
  unsigned __int8 v27; // al
  unsigned __int64 v28; // rax
  unsigned __int64 v29; // r8
  unsigned int v30; // eax
  unsigned __int8 *v31; // r9
  __int64 v32; // rdi
  unsigned __int16 v33; // r11
  int v34; // eax
  __int64 v35; // rdx
  char *v36; // rcx
  char v37; // al
  void *v38; // rbp
  unsigned __int64 v39; // rdx
  __int64 v40; // rax
  const WCHAR *v41; // rbx
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // r8
  _BYTE *v46; // rdx
  char v47; // al
  const void *v48; // rdx
  __int64 v49; // rdx
  char *v50; // rcx
  char v51; // al
  __int64 v52; // rdi
  unsigned __int16 v53; // r11
  __int16 v54; // bx
  __int64 v55; // rdx
  __int64 v56; // rdx
  int v58; // [rsp+30h] [rbp-1E8h]
  int v59; // [rsp+48h] [rbp-1D0h]
  char v60; // [rsp+70h] [rbp-1A8h]
  unsigned __int16 v62; // [rsp+80h] [rbp-198h]
  void *v63; // [rsp+88h] [rbp-190h]
  DWORD NumberOfBytesWritten; // [rsp+90h] [rbp-188h] BYREF
  unsigned __int16 v65; // [rsp+94h] [rbp-184h]
  unsigned __int64 v66; // [rsp+A0h] [rbp-178h]
  __int64 v67; // [rsp+A8h] [rbp-170h]
  unsigned __int64 v68; // [rsp+B0h] [rbp-168h]
  __int64 *v69; // [rsp+B8h] [rbp-160h]
  __int64 v70; // [rsp+C0h] [rbp-158h]
  CHAR Buffer[256]; // [rsp+D0h] [rbp-148h] BYREF

  v3 = 0;
  v4 = (__int64 *)*((_QWORD *)a1 + 1006);
  v5 = v4 + 218;
  v7 = a2;
  v65 = a2;
  v8 = a1;
  v66 = 0;
  v69 = v4 + 218;
  if ( !v4[218] )
  {
    v3 = -1;
    if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
      bidTraceW(off_383B43238[0], 13305865, off_383B49120[0], 12994);
    goto LABEL_167;
  }
  v9 = (char *)SQLAllocateMemory(a1, 0x200u);
  if ( !v9 )
  {
    if ( (bidGblFlags & 2) != 0 )
      bidTraceW(off_383B43238[0], 1096737, off_383B494E8[0], 0xFFFFFFFFLL);
    v3 = -1;
    goto LABEL_172;
  }
  ++*((_WORD *)v4 + 908);
  if ( !*_errno() )
  {
    if ( !v7 )
      goto LABEL_21;
    goto LABEL_14;
  }
  if ( v7 )
  {
LABEL_14:
    LoadStringA(g_hinstance_language, v7, Buffer, 255);
    v11 = Buffer;
    goto LABEL_16;
  }
  v12 = _errno();
  v11 = strerror(*v12);
LABEL_16:
  StringCchPrintfA(
    v9,
    0x200u,
    "#@ %s %I64d, %s %d: %s @#\r\n",
    szRow,
    *((_QWORD *)v8 + 1266) + *((unsigned __int16 *)v4 + 908),
    szCol,
    a3 + 1,
    v11);
  CharToOemA(v9, v9);
  v14 = -1;
  do
    ++v14;
  while ( v9[v14] );
  if ( (unsigned __int16)bcpWrite((struct tagDBC *)(v4 + 218), (unsigned int)v14, v9, v13) == 0xFFFF )
  {
    ((void (__fastcall *)(struct IMalloc *, char *))g_pMO->lpVtbl->Free)(g_pMO, v9);
    v3 = bcpError(v8, 0x9D16u);
    goto LABEL_172;
  }
  *v9 = 0;
LABEL_21:
  v15 = (*((_BYTE *)v4 + 51) & 1) == 0;
  v16 = 0;
  NumberOfBytesWritten = 0;
  if ( v15 || (v17 = 0, v18 = (struct BCPFILE *)(v4 + 209), v62 = 0, !*((_DWORD *)v4 + 5)) )
  {
LABEL_141:
    v54 = 0;
    if ( (unsigned __int64)(v5[5] + 2) > 0x10000 )
    {
      if ( !WriteFile((HANDLE)*v5, (LPCVOID)v5[3], *((_DWORD *)v5 + 10), &NumberOfBytesWritten, 0) )
      {
        v5[5] = 0x10000;
        v54 = -1;
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_160;
        if ( off_383B49120[0] )
          bidTraceW(off_383B43238[0], 6652937, off_383B49120[0], 6497);
LABEL_154:
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( !v54 && (bidGblFlags & 0x40) == 0 )
          {
LABEL_161:
            if ( !v16 )
            {
LABEL_166:
              ((void (__fastcall *)(struct IMalloc *, char *))g_pMO->lpVtbl->Free)(g_pMO, v9);
              v8 = a1;
              v7 = v65;
LABEL_167:
              if ( v7 )
              {
                if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
                  bidTraceW(off_383B43238[0], 13575177, off_383B49120[0], 13257);
                PostSQLErrorEx(v8, v7, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
              }
              goto LABEL_172;
            }
LABEL_162:
            if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
              bidTraceW(off_383B43238[0], 13568009, off_383B49120[0], 13250);
            PostSQLErrorEx(v8, 0x9D16u, 0, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFF);
            goto LABEL_166;
          }
          v55 = 6685697;
          if ( v54 )
            v55 = 6685729;
          bidTraceW(off_383B43238[0], v55, off_383B494E8[0], (unsigned int)v54);
        }
LABEL_160:
        if ( v54 )
          goto LABEL_162;
        goto LABEL_161;
      }
      v5[5] = 0;
    }
    *(_WORD *)(v5[5] + v5[3]) = *(_WORD *)"\r\n";
    v5[5] += 2;
    v5[6] += 2;
    goto LABEL_154;
  }
  while ( 1 )
  {
    v19 = *v4;
    if ( !*v4 )
    {
LABEL_140:
      v16 = NumberOfBytesWritten;
      v5 = v69;
      goto LABEL_141;
    }
    v60 = 0;
    v20 = v9;
    v68 = 0;
    v21 = 448LL * v17;
    v22 = *(unsigned __int8 *)(v19 + v21 + 100);
    LODWORD(v23) = *(_DWORD *)(v19 + v21 + 88);
    v24 = v19 + v21;
    v25 = *(_WORD *)(v19 + v21 + 48);
    if ( !v25 )
    {
      v67 = 0;
      goto LABEL_70;
    }
    v26 = v4[1] + 600LL * v25 - 600;
    v67 = v26;
    v27 = *(_BYTE *)(v26 + 36);
    if ( v27 != 34 && v27 != 99 && v27 != 35 )
    {
      if ( v27 == 0xA5 || v27 == 0xA7 || v27 == 0xE7 )
      {
        if ( *(_QWORD *)(v26 + 8) != 0xFFFF )
          goto LABEL_70;
      }
      else if ( v27 <= 0xEFu || v27 > 0xF1u )
      {
        goto LABEL_70;
      }
    }
    if ( *(_QWORD *)(v24 + 72) )
    {
      if ( (_DWORD)v23 )
      {
        v34 = *(_DWORD *)(v24 + 92);
        if ( v34 && v34 < (int)v23 )
          LODWORD(v23) = *(_DWORD *)(v24 + 92);
      }
      else
      {
        LODWORD(v23) = *(_DWORD *)(v24 + 92);
      }
      goto LABEL_70;
    }
    v28 = bcpPosition(a1, v18);
    v29 = *(_QWORD *)(v24 + 56);
    v66 = v28;
    if ( *((_DWORD *)v4 + 434) )
    {
      v4[216] = v29;
      goto LABEL_39;
    }
    if ( bcpSeek64(a1, (struct BCPFILE *)(v4 + 209), v29) == -1 )
      break;
LABEL_39:
    v30 = *(_DWORD *)(*v4 + v21 + 32);
    if ( v30 <= 0x800 )
    {
      LODWORD(v23) = 511;
      if ( v30 > 0x1FF )
        LODWORD(v23) = *(_DWORD *)(*v4 + v21 + 32);
    }
    else
    {
      LODWORD(v23) = 2048;
    }
    v70 = *(_QWORD *)(*v4 + v21 + 72);
    *(_QWORD *)(*v4 + v21 + 72) = SQLAllocateMemory(a1, (int)v23);
    v31 = *(unsigned __int8 **)(*v4 + v21 + 72);
    if ( !v31 )
    {
      v3 = -1;
      if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
        bidTraceW(off_383B43238[0], 13406217, off_383B49120[0], 13092);
      goto LABEL_166;
    }
    v60 = 1;
    if ( (unsigned __int16)bcpRead(a1, (struct BCPFILE *)(v4 + 209), v23, v31) )
    {
      LoadStringA(g_hinstance_language, 0x9C5Eu, Buffer, 255);
      if ( *(_BYTE *)(v67 + 36) == 34 )
      {
        LOWORD(v59) = 0;
        LOWORD(v58) = -2;
        Convert(a1, Buffer, 1, -3, -3, *(_QWORD *)(*v4 + v21 + 72), v58, (int)v23, 0, v59, 0, 1, 0);
      }
      else
      {
        StringCchCopyA(*(char **)(*v4 + v21 + 72), (int)v23, Buffer);
        v23 = -1;
        do
          ++v23;
        while ( Buffer[v23] );
      }
    }
    else
    {
      if ( *(_DWORD *)(*v4 + v21 + 32) > 0x800u )
      {
        LODWORD(v23) = 2048;
        goto LABEL_52;
      }
      LODWORD(v23) = *(_DWORD *)(*v4 + v21 + 32);
    }
LABEL_70:
    if ( (_DWORD)v23 == -1 )
    {
      v35 = 512;
      v36 = v9;
      while ( v35 != -2147483134 )
      {
        v37 = v36["<NULL>" - v9];
        if ( !v37 )
          break;
        *v36++ = v37;
        if ( !--v35 )
        {
          --v36;
          break;
        }
      }
      *v36 = 0;
      goto LABEL_77;
    }
LABEL_52:
    if ( v22 == 34 )
    {
      v68 = 2 * (int)v23 + 2;
      v63 = SQLAllocateMemory(a1, v68);
      if ( !v63 )
      {
        v49 = 512;
        v50 = v9;
        while ( v49 != -2147483134 )
        {
          v51 = v50["<Large IMAGE value>" - v9];
          if ( !v51 )
            break;
          *v50++ = v51;
          if ( !--v49 )
          {
            --v50;
            break;
          }
        }
        *v50 = 0;
LABEL_125:
        v38 = v63;
        v20 = v9;
        goto LABEL_78;
      }
      if ( !*v4 )
        goto LABEL_125;
      v52 = *(_QWORD *)(v21 + *v4 + 72);
      if ( !v52 )
        goto LABEL_125;
      if ( (_BYTE)v22 == 41 || (_BYTE)v22 == 43 )
        v53 = -2;
      else
        v53 = Srv2NativeCType(v22, v23);
      LOWORD(v59) = 0;
      LOWORD(v58) = 1;
      Convert(a1, v52, v53, (int)v23, (int)v23, v9, v58, 2 * (int)v23 + 1, 0, v59, 0, 1, 0);
      v38 = v63;
      v20 = (char *)v63;
    }
    else
    {
      if ( v22 != 35 && v22 != 99 )
      {
        if ( v22 == 231 || v22 == 239 )
        {
          v41 = *(const WCHAR **)(*v4 + v21 + 72);
          memset(v9, 0, 0x200u);
          v42 = -1;
          do
            ++v42;
          while ( v41[v42] );
          FastWideCharToMultiByte(*((_DWORD *)a1 + 2514), v41, (unsigned int)v42, v9, 512, 0);
          v43 = -1;
          do
            ++v43;
          while ( v41[v43] );
          if ( (unsigned __int64)(4 * v43) >= 0x1FE )
          {
            v9[510] = 0;
          }
          else
          {
            v44 = -1;
            do
              ++v44;
            while ( v41[v44] );
            v9[4 * v44] = 0;
          }
        }
        else if ( *v4 )
        {
          v32 = *(_QWORD *)(v21 + *v4 + 72);
          if ( v32 )
          {
            if ( (_BYTE)v22 == 41 || (_BYTE)v22 == 43 )
              v33 = -2;
            else
              v33 = Srv2NativeCType(v22, v23);
            LOWORD(v59) = 0;
            LOWORD(v58) = 1;
            Convert(a1, v32, v33, (int)v23, (int)v23, v9, v58, 511, 0, v59, 0, 1, 0);
          }
        }
LABEL_77:
        v38 = 0;
        goto LABEL_78;
      }
      v68 = (int)v23 + 2;
      v38 = SQLAllocateMemory(a1, v68);
      if ( v38 )
      {
        if ( *v4 )
        {
          v48 = *(const void **)(*v4 + v21 + 72);
          if ( v48 )
          {
            memcpy(v38, v48, (int)v23);
            v20 = (char *)v38;
          }
        }
      }
      else
      {
        v45 = 512;
        v46 = v9;
        v10 = (const unsigned __int8 *)("<Large TEXT value>" - v9);
        while ( v45 != -2147483134 )
        {
          v47 = v46[(_QWORD)v10];
          if ( !v47 )
            break;
          *v46++ = v47;
          if ( !--v45 )
          {
            *(v46 - 1) = 0;
            goto LABEL_78;
          }
        }
        *v46 = 0;
      }
    }
LABEL_78:
    if ( v62 < *((unsigned __int16 *)v4 + 12) - 1 )
    {
      v39 = 512;
      if ( v38 )
        v39 = v68;
      StringCchCatA(v20, v39, "\t");
    }
    v40 = -1;
    do
      ++v40;
    while ( v20[v40] );
    if ( (unsigned __int16)bcpWrite((struct tagDBC *)(v4 + 218), (unsigned int)v40, v20, v10) )
      NumberOfBytesWritten = 1;
    if ( v38 )
      ((void (__fastcall *)(struct IMalloc *, void *))g_pMO->lpVtbl->Free)(g_pMO, v38);
    if ( !v67 || !(unsigned int)FIsBCPBlobType(*(_BYTE *)(v67 + 36), *(_QWORD *)(v67 + 8)) )
    {
      v8 = a1;
LABEL_138:
      v18 = (struct BCPFILE *)(v4 + 209);
      goto LABEL_139;
    }
    if ( v60 && *(_QWORD *)(*v4 + v21 + 72) )
      ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl->Free)(g_pMO);
    v8 = a1;
    *(_QWORD *)(*v4 + v21 + 72) = v70;
    v18 = (struct BCPFILE *)(v4 + 209);
    if ( *(_QWORD *)(*v4 + v21 + 72) )
      goto LABEL_139;
    if ( !*((_DWORD *)v4 + 434) )
    {
      if ( bcpSeek64(a1, v18, v66) == -1 )
      {
        ((void (__fastcall *)(struct IMalloc *, char *))g_pMO->lpVtbl->Free)(g_pMO, v9);
        v3 = -1;
        if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
          bidTraceW(off_383B43238[0], 13557769, off_383B49120[0], 13240);
        goto LABEL_172;
      }
      goto LABEL_138;
    }
    v4[216] = v66;
LABEL_139:
    v17 = v62 + 1;
    v62 = v17;
    if ( (unsigned int)v17 >= *((_DWORD *)v4 + 5) )
      goto LABEL_140;
  }
  ((void (__fastcall *)(struct IMalloc *, char *))g_pMO->lpVtbl->Free)(g_pMO, v9);
  v3 = -1;
  if ( (bidGblFlags & 2) != 0 && off_383B49120[0] )
    bidTraceW(off_383B43238[0], 13393929, off_383B49120[0], 13080);
LABEL_172:
  if ( (bidGblFlags & 2) != 0 && (v3 || (bidGblFlags & 0x40) != 0) )
  {
    v56 = 13578241;
    if ( v3 )
      v56 = 13578273;
    bidTraceW(off_383B43238[0], v56, off_383B494E8[0], (unsigned int)v3);
  }
  return (unsigned __int16)v3;
}

```

## disassembly

```asm
0x3839804e0  mov     r11, rsp
0x3839804e3  push    r15
0x3839804e5  sub     rsp, 210h
0x3839804ec  mov     rax, cs:__security_cookie
0x3839804f3  xor     rax, rsp
0x3839804f6  mov     [rsp+218h+var_48], rax
0x3839804fe  mov     [r11+20h], rbx
0x383980502  mov     [r11-10h], rbp
0x383980506  mov     [r11-18h], rsi
0x38398050a  mov     [r11-20h], rdi
0x38398050e  mov     [r11-28h], r12
0x383980512  mov     [r11-30h], r13
0x383980516  xor     r15d, r15d
0x383980519  mov     [r11-38h], r14
0x38398051d  mov     r14, [rcx+1F70h]
0x383980524  lea     rbp, [r14+6D0h]
0x38398052b  mov     ebx, r8d
0x38398052e  movzx   r13d, dx
0x383980532  mov     [rsp+218h+var_184], dx
0x38398053a  mov     rsi, rcx
0x38398053d  mov     [rsp+218h+var_1A0], rcx
0x383980542  mov     [rsp+218h+var_178], r15
0x38398054a  mov     [rsp+218h+var_160], rbp
0x383980552  cmp     [rbp+0], r15
0x383980556  jnz     short loc_3839805A0
0x383980558  or      rdi, 0FFFFFFFFFFFFFFFFh
0x38398055c  test    byte ptr cs:_bidGblFlags, 2
0x383980563  movzx   r15d, di
0x383980567  jz      loc_38398109D
0x38398056d  mov     rcx, cs:off_383B43238; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383980574  mov     rax, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x38398057b  test    rax, rax
0x38398057e  jz      loc_38398109D
0x383980584  mov     r8, cs:off_383B49120; "<Trace|MARK> line %d\n"
0x38398058b  mov     r9d, 32C2h
0x383980591  mov     edx, 0CB0809h
0x383980596  call    _bidTraceW
0x38398059b  jmp     loc_38398109D
0x3839805a0  mov     edx, 200h; unsigned __int64
0x3839805a5  call    ?SQLAllocateMemory@@YAPEAXPEAUtagOBJBASE@@_K@Z; SQLAllocateMemory(tagOBJBASE *,unsigned __int64)
0x3839805aa  mov     r12, rax
0x3839805ad  test    rax, rax
0x3839805b0  jnz     short loc_3839805EC
0x3839805b2  test    byte ptr cs:_bidGblFlags, 2
0x3839805b9  jz      short loc_3839805E3
0x3839805bb  mov     rcx, cs:off_383B43238; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x3839805c2  mov     r8, cs:off_383B494E8; "<ODBC|DRIVER|RET> %d{SQLRETURN}\n"
0x3839805c9  or      rbx, 0FFFFFFFFFFFFFFFFh
0x3839805cd  mov     r9d, ebx
0x3839805d0  mov     edx, 10BC21h
0x3839805d5  call    _bidTraceW
0x3839805da  movzx   r15d, bx
0x3839805de  jmp     loc_3839810F0
0x3839805e3  or      r15, 0FFFFFFFFFFFFFFFFh
0x3839805e7  jmp     loc_3839810F0
0x3839805ec  inc     word ptr [r14+718h]
0x3839805f4  call    cs:__imp__errno
0x3839805fa  or      rdi, 0FFFFFFFFFFFFFFFFh
0x3839805fe  cmp     [rax], r15d
0x383980601  jnz     short loc_38398060F
0x383980603  test    r13w, r13w
0x383980607  jz      loc_3839806EB
0x38398060d  jmp     short loc_383980615
0x38398060f  test    r13w, r13w
0x383980613  jz      short loc_38398063E
0x383980615  mov     rcx, cs:?g_hinstance_language@@3PEAUHINSTANCE__@@EA; hInstance
0x38398061c  lea     r8, [rsp+218h+Buffer]; lpBuffer
0x383980624  movzx   edx, r13w; uID
0x383980628  mov     r9d, 0FFh; cchBufferMax
0x38398062e  call    cs:__imp_LoadStringA
0x383980634  lea     r11, [rsp+218h+Buffer]
0x38398063c  jmp     short loc_38398064F
0x38398063e  call    cs:__imp__errno
0x383980644  mov     ecx, [rax]; ErrorMessage
0x383980646  call    cs:__imp_strerror
0x38398064c  mov     r11, rax
0x38398064f  movzx   ecx, word ptr [r14+718h]
0x383980657  mov     [rsp+218h+var_1E0], r11
0x38398065c  lea     eax, [rbx+1]
0x38398065f  add     rcx, [rsi+2790h]
0x383980666  mov     [rsp+218h+var_1E8], eax
0x38398066a  lea     rax, ?szCol@@3PADA; char near * szCol
0x383980671  mov     [rsp+218h+var_1F0], rax
0x383980676  mov     [rsp+218h+lpOverlapped], rcx
0x38398067b  lea     r9, ?szRow@@3PADA; char near * szRow
0x383980682  lea     r8, aSI64dSDS; "#@ %s %I64d, %s %d: %s @#\r\n"
0x383980689  mov     rcx, r12; char *
0x38398068c  mov     edx, 200h; unsigned __int64
0x383980691  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x383980696  mov     rdx, r12; pDst
0x383980699  mov     rcx, r12; pSrc
0x38398069c  call    cs:__imp_CharToOemA
0x3839806a2  mov     rax, rdi
0x3839806a5  inc     rax
0x3839806a8  cmp     [r12+rax], r15b
0x3839806ac  jnz     short loc_3839806A5
0x3839806ae  mov     edx, eax; struct BCPFILE *
0x3839806b0  mov     r8, r12; __int64
0x3839806b3  mov     rcx, rbp; struct tagDBC *
0x3839806b6  call    ?bcpWrite@@YAFPEAUtagDBC@@PEAUBCPFILE@@_JPEBE@Z; bcpWrite(tagDBC *,BCPFILE *,__int64,uchar const *)
0x3839806bb  cmp     ax, 0FFFFh
0x3839806bf  jnz     short loc_3839806E7
0x3839806c1  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x3839806c8  mov     rdx, r12
0x3839806cb  mov     rax, [rcx]
0x3839806ce  call    qword ptr [rax+28h]
0x3839806d1  mov     edx, 9D16h; unsigned __int16
0x3839806d6  mov     rcx, rsi; struct tagDBC *
0x3839806d9  call    ?bcpError@@YAFPEAUtagDBC@@G@Z; bcpError(tagDBC *,ushort)
0x3839806de  movzx   r15d, ax
0x3839806e2  jmp     loc_3839810F0
0x3839806e7  mov     [r12], r15b
0x3839806eb  test    byte ptr [r14+33h], 1
0x3839806f0  movzx   r13d, r15w
0x3839806f4  mov     [rsp+218h+NumberOfBytesWritten], r13d
0x3839806fc  jz      loc_383980EA3
0x383980702  movzx   ebx, r15w
0x383980706  lea     rdx, [r14+688h]; struct BCPFILE *
0x38398070d  mov     [rsp+218h+var_198], bx
0x383980715  cmp     [r14+14h], r15d
0x383980719  jbe     loc_383980EA3
0x38398071f  nop
0x383980720  mov     rax, [r14]
0x383980723  test    rax, rax
0x383980726  jz      loc_383980E93
0x38398072c  movzx   r13d, bx
0x383980730  mov     [rsp+218h+var_1A8], r15b
0x383980735  mov     rsi, r12
0x383980738  mov     [rsp+218h+var_168], r15
0x383980740  imul    r13, 1C0h
0x383980747  movzx   ebp, byte ptr [rax+r13+64h]
0x38398074d  mov     ebx, [rax+r13+58h]
0x383980752  lea     rdi, [rax+r13]
0x383980756  mov     rax, r15
0x383980759  movzx   eax, word ptr [rdi+30h]
0x38398075d  test    ax, ax
0x383980760  jz      loc_3839809F2
0x383980766  movzx   ecx, ax
0x383980769  mov     rax, [r14+8]
0x38398076d  imul    rcx, 258h
0x383980774  add     rcx, 0FFFFFFFFFFFFFDA8h
0x38398077b  add     rcx, rax
0x38398077e  mov     [rsp+218h+var_170], rcx
0x383980786  movzx   eax, byte ptr [rcx+24h]
0x38398078a  cmp     al, 22h ; '"'
0x38398078c  jz      short loc_3839807C2
0x38398078e  cmp     al, 63h ; 'c'
0x383980790  jz      short loc_3839807C2
0x383980792  cmp     al, 23h ; '#'
0x383980794  jz      short loc_3839807C2
0x383980796  cmp     al, 0A5h
0x383980798  jz      short loc_3839807B4
0x38398079a  cmp     al, 0A7h
0x38398079c  jz      short loc_3839807B4
0x38398079e  cmp     al, 0E7h
0x3839807a0  jz      short loc_3839807B4
0x3839807a2  cmp     al, 0EFh
0x3839807a4  jbe     loc_3839809FD
0x3839807aa  cmp     al, 0F1h
0x3839807ac  ja      loc_3839809FD
0x3839807b2  jmp     short loc_3839807C2
0x3839807b4  cmp     qword ptr [rcx+8], 0FFFFh
0x3839807bc  jnz     loc_3839809FD
0x3839807c2  cmp     [rdi+48h], r15
0x3839807c6  jnz     loc_3839809DB
0x3839807cc  mov     rbx, [rsp+218h+var_1A0]
0x3839807d1  mov     rcx, rbx; struct tagDBC *
0x3839807d4  call    ?bcpPosition@@YA_KPEAUtagDBC@@PEAUBCPFILE@@@Z; bcpPosition(tagDBC *,BCPFILE *)
0x3839807d9  mov     r8, [rdi+38h]; unsigned __int64
0x3839807dd  mov     [rsp+218h+var_178], rax
0x3839807e5  cmp     [r14+6C8h], r15d
0x3839807ec  jz      short loc_3839807F7
0x3839807ee  mov     [r14+6C0h], r8
0x3839807f5  jmp     short loc_383980810
0x3839807f7  lea     rdx, [r14+688h]; struct BCPFILE *
0x3839807fe  mov     rcx, rbx; struct tagDBC *
0x383980801  call    ?bcpSeek64@@YAFPEAUtagDBC@@PEAUBCPFILE@@_K@Z; bcpSeek64(tagDBC *,BCPFILE *,unsigned __int64)
0x383980806  cmp     ax, 0FFFFh
0x38398080a  jz      loc_383980F74
0x383980810  mov     rcx, [r14]
0x383980813  mov     eax, [rcx+r13+20h]
0x383980818  cmp     eax, 800h
0x38398081d  jbe     short loc_383980826
0x38398081f  mov     ebx, 800h
0x383980824  jmp     short loc_383980830
0x383980826  mov     ebx, 1FFh
0x38398082b  cmp     eax, ebx
0x38398082d  cmova   ebx, eax
0x383980830  mov     rax, [rcx+r13+48h]
0x383980835  mov     rcx, [rsp+218h+var_1A0]; struct tagOBJBASE *
0x38398083a  movsxd  rdi, ebx
0x38398083d  mov     rdx, rdi; unsigned __int64
0x383980840  mov     [rsp+218h+var_158], rax
0x383980848  call    ?SQLAllocateMemory@@YAPEAXPEAUtagOBJBASE@@_K@Z; SQLAllocateMemory(tagOBJBASE *,unsigned __int64)
0x38398084d  mov     rcx, [r14]
0x383980850  mov     [rcx+r13+48h], rax
0x383980855  mov     rax, [r14]
0x383980858  mov     r9, [rax+r13+48h]; unsigned __int8 *
0x38398085d  test    r9, r9
0x383980860  jz      loc_383980F2C
0x383980866  mov     rcx, [rsp+218h+var_1A0]; struct tagDBC *
0x38398086b  lea     rdx, [r14+688h]; struct BCPFILE *
0x383980872  mov     r8d, ebx; unsigned int
0x383980875  mov     [rsp+218h+var_1A8], 1
0x38398087a  call    ?bcpRead@@YAFPEAUtagDBC@@PEAUBCPFILE@@IPEAE@Z; bcpRead(tagDBC *,BCPFILE *,uint,uchar *)
0x38398087f  test    ax, ax
0x383980882  jz      loc_38398094E
0x383980888  mov     rcx, cs:?g_hinstance_language@@3PEAUHINSTANCE__@@EA; hInstance
0x38398088f  lea     r8, [rsp+218h+Buffer]; lpBuffer
0x383980897  mov     r9d, 0FFh; cchBufferMax
0x38398089d  mov     edx, 9C5Eh; uID
0x3839808a2  call    cs:__imp_LoadStringA
0x3839808a8  mov     r11, [rsp+218h+var_170]
0x3839808b0  cmp     byte ptr [r11+24h], 22h ; '"'
0x3839808b5  jnz     short loc_38398091B
0x3839808b7  mov     rax, [r14]
0x3839808ba  mov     [rsp+218h+var_1B8], r15d
0x3839808bf  mov     ecx, 1
0x3839808c4  mov     rax, [rax+r13+48h]
0x3839808c9  mov     [rsp+218h+var_1C0], ecx
0x3839808cd  mov     [rsp+218h+var_1C8], r15
0x3839808d2  mov     [rsp+218h+var_1D0], r15w
0x3839808d8  mov     [rsp+218h+var_1D8], r15
0x3839808dd  mov     r8d, ecx
0x3839808e0  mov     [rsp+218h+var_1E0], rdi
0x3839808e5  mov     ecx, 0FFFFFFFEh
0x3839808ea  lea     rdx, [rsp+218h+Buffer]
0x3839808f2  mov     word ptr [rsp+218h+var_1E8], cx
0x3839808f7  mov     rcx, [rsp+218h+var_1A0]
0x3839808fc  mov     [rsp+218h+var_1F0], rax
0x383980901  mov     r9, 0FFFFFFFFFFFFFFFDh
0x383980908  mov     [rsp+218h+lpOverlapped], 0FFFFFFFFFFFFFFFDh
0x383980911  call    ?Convert@@YAGPEAUtagDBC@@PEAXF_J21F2PEA_JF3HW4XLATDIR@@@Z; Convert(tagDBC *,void *,short,__int64,__int64,void *,short,__int64,__int64 *,short,__int64 *,int,XLATDIR)
0x383980916  jmp     loc_3839809FD
0x38398091b  mov     rcx, [r14]
0x38398091e  lea     r8, [rsp+218h+Buffer]; char *
0x383980926  mov     rdx, rdi; unsigned __int64
0x383980929  mov     rcx, [rcx+r13+48h]; char *
0x38398092e  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x383980933  lea     r11, [rsp+218h+Buffer]
0x38398093b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x38398093f  nop
0x383980940  inc     rbx
0x383980943  cmp     [r11+rbx], r15b
0x383980947  jnz     short loc_383980940
0x383980949  jmp     loc_3839809FD
0x38398094e  mov     rax, [r14]
0x383980951  mov     ecx, [rax+r13+20h]
0x383980956  cmp     ecx, 800h
0x38398095c  jbe     short loc_3839809D7
0x38398095e  mov     ebx, 800h
0x383980963  movsx   ecx, bp
0x383980966  sub     ecx, 22h ; '"'
0x383980969  jz      loc_383980CEB
0x38398096f  dec     ecx
0x383980971  jz      loc_383980C45
0x383980977  sub     ecx, 40h ; '@'
0x38398097a  jz      loc_383980C45
0x383980980  sub     ecx, 84h
0x383980986  jz      loc_383980BB1
0x38398098c  cmp     ecx, 8
0x38398098f  jz      loc_383980BB1
0x383980995  mov     rax, [r14]
0x383980998  test    rax, rax
0x38398099b  jz      loc_383980A4C
0x3839809a1  mov     rdi, [r13+rax+48h]
0x3839809a6  test    rdi, rdi
0x3839809a9  jz      loc_383980A4C
0x3839809af  cmp     bpl, 29h ; ')'
0x3839809b3  jz      loc_383980B5C
0x3839809b9  cmp     bpl, 2Bh ; '+'
0x3839809bd  jz      loc_383980B5C
0x3839809c3  mov     edx, ebx; int
0x3839809c5  movzx   ecx, bpl; unsigned __int8
0x3839809c9  call    ?Srv2NativeCType@@YAFEJ@Z; Srv2NativeCType(uchar,long)
0x3839809ce  movzx   r11d, ax
0x3839809d2  jmp     loc_383980B62
0x3839809d7  mov     ebx, ecx
0x3839809d9  jmp     short loc_3839809FD
0x3839809db  test    ebx, ebx
0x3839809dd  jz      short loc_3839809ED
0x3839809df  mov     eax, [rdi+5Ch]
0x3839809e2  test    eax, eax
0x3839809e4  jz      short loc_3839809FD
0x3839809e6  cmp     eax, ebx
0x3839809e8  cmovl   ebx, eax
0x3839809eb  jmp     short loc_3839809FD
0x3839809ed  mov     ebx, [rdi+5Ch]
0x3839809f0  jmp     short loc_3839809FD
0x3839809f2  mov     r11, r15
0x3839809f5  mov     [rsp+218h+var_170], r15
0x3839809fd  cmp     ebx, 0FFFFFFFFh
0x383980a00  jnz     loc_383980963
0x383980a06  lea     r8, aNull_2; "<NULL>"
0x383980a0d  mov     edx, 200h
0x383980a12  mov     rcx, r12
0x383980a15  sub     r8, r12
0x383980a18  nop     dword ptr [rax+rax+00000000h]
0x383980a20  lea     rax, [rdx+7FFFFDFEh]
0x383980a27  test    rax, rax
  ... truncated ...
```
