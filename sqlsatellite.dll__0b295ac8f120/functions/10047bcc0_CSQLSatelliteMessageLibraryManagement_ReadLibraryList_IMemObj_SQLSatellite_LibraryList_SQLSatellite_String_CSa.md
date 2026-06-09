# CSQLSatelliteMessageLibraryManagement::ReadLibraryList(IMemObj *,_SQLSatellite_LibraryList *,_SQLSatellite_String * *,CSatelliteSessionContext *)

- ea: `0x10047bcc0`
- end: `0x10047c332`
- name: `?ReadLibraryList@CSQLSatelliteMessageLibraryManagement@@AEAAJPEAVIMemObj@@PEAU_SQLSatellite_LibraryList@@PEAPEAU_SQLSatellite_String@@PEAVCSatelliteSessionContext@@@Z`
- size: `1650`
- prototype: `__int64 __fastcall(CSQLSatelliteMessageLibraryManagement *this, struct IMemObj *, struct _SQLSatellite_LibraryList *, struct _SQLSatellite_String **, struct CSatelliteSessionContext *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1004089b0`

## callees

- `0x10047bcc0`
- `0x10047c340`
- `0x100486af0`

## import_xrefs

- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10047be3d`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10047c06b`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10047be3d`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10047c06b`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10047be00`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10047bebf`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10047bfb7`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10047c298`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10047be00`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10047bebf`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10047bfb7`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10047c298`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10047bda0`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10047bda0`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10047bd94`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10047bd94`

## string_xrefs

- `0x10047bde2`: `Sql\Ntdbms\extensibility\common\src\satellitesessioncontext.cpp`
- `0x10047be1f`: `Sql\Ntdbms\extensibility\common\src\satellitesessioncontext.cpp`
- `0x10047bead`: `Sql\Ntdbms\extensibility\common\src\satellitesessioncontext.cpp`
- `0x10047bf86`: `Sql\Ntdbms\extensibility\common\src\protocolmessage.cpp`
- `0x10047c055`: `Sql\Ntdbms\extensibility\common\src\protocolmessage.cpp`
- `0x10047c283`: `Sql\Ntdbms\extensibility\common\src\protocolmessage.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CSQLSatelliteMessageLibraryManagement::ReadLibraryList(
        CSQLSatelliteMessageLibraryManagement *this,
        struct IMemObj *a2,
        struct _SQLSatellite_LibraryList *a3,
        struct _SQLSatellite_String **a4,
        struct CSatelliteSessionContext *a5)
{
  int v5; // esi
  struct _SQLSatellite_String **v6; // r13
  struct _SQLSatellite_LibraryList *v7; // rdi
  int v11; // ecx
  _DWORD *v12; // r8
  int v13; // edx
  unsigned __int64 v14; // r15
  char v15; // di
  _QWORD *v16; // rax
  _QWORD *v17; // rcx
  __int64 v18; // rdi
  __int64 v19; // rcx
  int v20; // edx
  unsigned __int64 v21; // rax
  char v22; // al
  struct _SQLSatellite_LibraryList **v23; // rax
  int v24; // eax
  int v25; // ecx
  int SQLSatelliteString; // eax
  unsigned __int64 v27; // rax
  void *v28; // rax
  struct _SQLSatellite_LibraryList **v29; // rax
  unsigned int v30; // ebp
  char v31; // r13
  bool v32; // zf
  int v33; // r15d
  char *v34; // rsi
  int v35; // eax
  bool v36; // cf
  int v37; // ecx
  int v38; // eax
  __int64 v39; // rcx
  int v40; // edx
  char v41; // dl
  struct _SQLSatellite_LibraryList **v42; // rax
  int v43; // ecx
  char *v44; // rax
  char v45; // r8
  int v46; // ecx
  struct _SQLSatellite_LibraryList **v47; // rax
  int v48; // eax
  struct _SQLSatellite_LibraryList **v49; // rcx
  unsigned __int64 v50; // rsi
  unsigned __int64 v51; // rax
  struct _SQLSatellite_String *v52; // rax
  unsigned int v53; // edi
  int i; // eax
  __int128 v57; // [rsp+48h] [rbp-70h]

  v5 = *((_DWORD *)this + 17);
  v6 = a4;
  v7 = a3;
  if ( !a3 )
    v7 = 0;
  if ( v5 != 2 )
  {
    if ( v5 != 3 )
      goto LABEL_75;
    goto LABEL_48;
  }
  *((_DWORD *)this + 9) = -2089418750;
  v11 = *((_DWORD *)this + 6);
  if ( (unsigned int)v11 < 4
    || ((v12 = (_DWORD *)*((_QWORD *)this + 2), v13 = 0, *((_DWORD *)this + 14) = *v12, v11 < 4)
      ? (v13 = -2089418750)
      : (*((_QWORD *)this + 2) = v12 + 1, *((_DWORD *)this + 6) = v11 - 4),
        *((_DWORD *)this + 9) = v13,
        v7 = a3,
        v13 < 0) )
  {
LABEL_45:
    v7 = a3;
LABEL_46:
    *((_DWORD *)this + 9) = -2089418750;
    goto LABEL_75;
  }
  if ( !a5 )
    goto LABEL_31;
  if ( *((_DWORD *)a5 + 37) == 2 )
  {
    if ( *((_QWORD *)this + 1) == -8 )
    {
      v57 = 0;
      *_errno() = 22;
      _invalid_parameter_noinfo();
    }
    else
    {
      v57 = *(_OWORD *)(*((_QWORD *)this + 1) + 8LL);
    }
    if ( v57 != *(_OWORD *)((char *)a5 + 8) )
      goto LABEL_46;
    v14 = *((unsigned int *)this + 14);
    v15 = *((_BYTE *)this + 60);
    if ( !*((_QWORD *)a5 + 4) )
    {
      v16 = operator new[](
              0x10u,
              *(struct IMemObj **)a5,
              1,
              "Sql\\Ntdbms\\extensibility\\common\\src\\satellitesessioncontext.cpp",
              246,
              6u);
      *((_QWORD *)a5 + 4) = v16;
      if ( !v16 )
        goto LABEL_22;
      v16[1] = 0;
      **((_QWORD **)a5 + 4) = 0;
    }
    v17 = operator new(
            0x19u,
            *(struct IMemObj **)a5,
            1,
            "Sql\\Ntdbms\\extensibility\\common\\src\\satellitesessioncontext.cpp",
            187,
            6u);
    if ( v17 )
    {
      *(_OWORD *)v17 = 0;
      v17[2] = 0;
      *((_BYTE *)v17 + 24) = 0;
    }
    else
    {
      v17 = 0;
    }
    v18 = v15 != 0 ? 8 : 0;
    *(_QWORD *)(v18 + *((_QWORD *)a5 + 4)) = v17;
    v19 = *(_QWORD *)(v18 + *((_QWORD *)a5 + 4));
    if ( v19 )
    {
      *(_DWORD *)(v19 + 20) = v14;
      v21 = 8 * v14;
      if ( !is_mul_ok(v14, 8u) )
        v21 = -1;
      *(_QWORD *)(*(_QWORD *)(*((_QWORD *)a5 + 4) + v18) + 12LL) = operator new[](
                                                                     v21,
                                                                     *(struct IMemObj **)a5,
                                                                     1,
                                                                     "Sql\\Ntdbms\\extensibility\\common\\src\\satellites"
                                                                     "essioncontext.cpp",
                                                                     195,
                                                                     6u);
      v20 = 0;
      if ( !*(_QWORD *)(*(_QWORD *)(*((_QWORD *)a5 + 4) + v18) + 12LL) )
        v20 = -2147024882;
LABEL_27:
      v22 = *((_BYTE *)this + 61);
      *((_DWORD *)this + 9) = v20;
      *((_BYTE *)a5 + 40) = v22;
      if ( *((int *)this + 9) >= 0 )
        goto LABEL_28;
      goto LABEL_45;
    }
LABEL_22:
    v20 = -2147024882;
    goto LABEL_27;
  }
LABEL_28:
  v23 = (struct _SQLSatellite_LibraryList **)(*((_QWORD *)a5 + 4) + 8LL);
  if ( !*((_BYTE *)this + 60) )
    v23 = (struct _SQLSatellite_LibraryList **)*((_QWORD *)a5 + 4);
  v7 = *v23;
LABEL_31:
  v24 = *((_DWORD *)this + 6);
  v25 = -2089418750;
  *((_DWORD *)this + 9) = -2089418750;
  if ( v24 )
  {
    *((_BYTE *)v7 + 24) = **((_BYTE **)this + 2);
    v25 = 0;
    v24 = *((_DWORD *)this + 6);
    if ( v24 < 1 )
    {
      v25 = -2089418750;
    }
    else
    {
      ++*((_QWORD *)this + 2);
      *((_DWORD *)this + 6) = --v24;
    }
  }
  *((_DWORD *)this + 9) = v25;
  if ( v25 < 0 || (unsigned int)v24 < 4 )
    goto LABEL_46;
  SQLSatelliteString = CSQLSatelliteMessageLibraryManagement::ReadSQLSatelliteString(
                         this,
                         v7,
                         a2,
                         *((_DWORD *)this + 13));
  *((_DWORD *)this + 9) = SQLSatelliteString;
  if ( SQLSatelliteString >= 0 && !a5 )
  {
    _mm_lfence();
    v27 = 8LL * *((unsigned int *)this + 14);
    if ( !is_mul_ok(*((unsigned int *)this + 14), 8u) )
      v27 = -1;
    v28 = operator new[](v27, a2, 1, "Sql\\Ntdbms\\extensibility\\common\\src\\protocolmessage.cpp", 3516, 6u);
    *(_QWORD *)((char *)v7 + 12) = v28;
    if ( !v28 )
      *((_DWORD *)this + 9) = -2147024882;
  }
  if ( *((int *)this + 9) < 0 )
    goto LABEL_75;
  *((_DWORD *)v7 + 5) = *((_DWORD *)this + 14);
  *((_DWORD *)this + 17) = 3;
LABEL_48:
  if ( !v7 )
  {
    v29 = (struct _SQLSatellite_LibraryList **)(*((_QWORD *)a5 + 4) + 8LL);
    if ( !*((_BYTE *)this + 60) )
      v29 = (struct _SQLSatellite_LibraryList **)*((_QWORD *)a5 + 4);
    v7 = *v29;
  }
  v30 = *((_DWORD *)this + 18);
  v31 = *((_BYTE *)v7 + 24);
  v32 = v30 == *((_DWORD *)v7 + 5);
  if ( v30 < *((_DWORD *)v7 + 5) )
  {
    v33 = 12;
    if ( v31 == 2 )
      v33 = 8;
    while ( *((_DWORD *)this + 6) >= v33 )
    {
      v34 = (char *)operator new(0x1Cu, a2, 1, "Sql\\Ntdbms\\extensibility\\common\\src\\protocolmessage.cpp", 3646, 6u);
      if ( !v34 )
      {
        *((_DWORD *)this + 9) = -2147024882;
        break;
      }
      *(_OWORD *)v34 = 0;
      *((_QWORD *)v34 + 2) = 0;
      *((_DWORD *)v34 + 6) = 0;
      v35 = CSQLSatelliteMessageLibraryManagement::ReadSQLSatelliteString(
              this,
              (struct _SQLSatellite_String *)v34,
              a2,
              *((_DWORD *)this + 13));
      *((_DWORD *)this + 9) = v35;
      if ( v35 >= 0 )
      {
        v36 = *((_DWORD *)this + 6) < 4u;
        v37 = -2089418750;
        *((_DWORD *)this + 9) = -2089418750;
        if ( !v36 )
        {
          *((_DWORD *)v34 + 3) = **((_DWORD **)this + 2);
          v37 = 0;
          v38 = *((_DWORD *)this + 6);
          if ( v38 < 4 )
          {
            v37 = -2089418750;
          }
          else
          {
            *((_QWORD *)this + 2) += 4LL;
            *((_DWORD *)this + 6) = v38 - 4;
          }
        }
        *((_DWORD *)this + 9) = v37;
        if ( v37 >= 0 )
        {
          if ( v31 == 2 )
          {
            *((_QWORD *)v34 + 2) = 0;
            *((_DWORD *)v34 + 6) = 0;
          }
          else
          {
            *((_DWORD *)this + 9) = CSQLSatelliteMessageLibraryManagement::ReadSQLSatelliteString(
                                      this,
                                      (struct _SQLSatellite_String *)(v34 + 16),
                                      a2,
                                      *((_DWORD *)this + 13));
          }
        }
      }
      if ( *((int *)this + 9) >= 0 )
      {
        v39 = v30++;
        *(_QWORD *)(*(_QWORD *)((char *)v7 + 12) + 8 * v39) = v34;
        ++*((_DWORD *)this + 18);
        if ( v30 < *((_DWORD *)v7 + 5) )
          continue;
      }
      break;
    }
    v32 = v30 == *((_DWORD *)v7 + 5);
  }
  if ( v32 && *((int *)this + 9) >= 0 )
    *(_QWORD *)((char *)this + 68) = 4;
  v5 = *((_DWORD *)this + 17);
  v6 = a4;
LABEL_75:
  v40 = *((_DWORD *)this + 9);
  if ( v40 >= 0 && v5 == 4 )
  {
    v41 = *((_BYTE *)this + 60);
    if ( !v7 )
    {
      v42 = (struct _SQLSatellite_LibraryList **)(*((_QWORD *)a5 + 4) + 8LL);
      if ( !v41 )
        v42 = (struct _SQLSatellite_LibraryList **)*((_QWORD *)a5 + 4);
      v7 = *v42;
    }
    v32 = v41 == 0;
    v40 = *((_DWORD *)this + 9);
    if ( v32 )
    {
      v43 = *((_DWORD *)this + 6);
      if ( v43 )
      {
        v44 = (char *)*((_QWORD *)this + 2);
        v40 = 0;
        *((_DWORD *)this + 9) = -2089418750;
        v45 = *v44;
        if ( v43 < 1 )
        {
          v40 = -2089418750;
        }
        else
        {
          *((_QWORD *)this + 2) = v44 + 1;
          *((_DWORD *)this + 6) = v43 - 1;
          if ( v45 )
            *((_DWORD *)this + 17) = 5;
          else
            *((_DWORD *)this + 17) = 15;
        }
      }
    }
    else
    {
      *((_DWORD *)this + 17) = 5;
    }
    v5 = *((_DWORD *)this + 17);
    *((_DWORD *)this + 9) = v40;
  }
  v46 = v40;
  if ( v40 >= 0 && v5 == 5 )
  {
    if ( !v7 )
    {
      v47 = (struct _SQLSatellite_LibraryList **)(*((_QWORD *)a5 + 4) + 8LL);
      if ( !*((_BYTE *)this + 60) )
        v47 = (struct _SQLSatellite_LibraryList **)*((_QWORD *)a5 + 4);
      v7 = *v47;
    }
    v48 = *((_DWORD *)this + 6);
    v46 = v40;
    if ( (unsigned int)v48 >= 4 )
    {
      v46 = 0;
      if ( v48 < 4 )
      {
        v46 = -2089418750;
      }
      else
      {
        *((_QWORD *)this + 2) += 4LL;
        *((_DWORD *)this + 17) = 6;
        *((_DWORD *)this + 6) = v48 - 4;
      }
    }
    v5 = *((_DWORD *)this + 17);
    *((_DWORD *)this + 9) = v46;
  }
  if ( v46 >= 0 && v5 == 6 )
  {
    if ( !v7 )
    {
      v49 = (struct _SQLSatellite_LibraryList **)(*((_QWORD *)a5 + 4) + 8LL);
      if ( !*((_BYTE *)this + 60) )
        v49 = (struct _SQLSatellite_LibraryList **)*((_QWORD *)a5 + 4);
      v7 = *v49;
    }
    v50 = *((unsigned int *)v7 + 5);
    if ( !*v6 )
    {
      v51 = 12 * v50;
      if ( !is_mul_ok(v50, 0xCu) )
        v51 = -1;
      v52 = (struct _SQLSatellite_String *)operator new[](
                                             v51,
                                             a2,
                                             1,
                                             "Sql\\Ntdbms\\extensibility\\common\\src\\protocolmessage.cpp",
                                             3827,
                                             6u);
      *v6 = v52;
      if ( !v52 )
        *((_DWORD *)this + 9) = -2147024882;
    }
    v46 = *((_DWORD *)this + 9);
    if ( v46 >= 0 )
    {
      v53 = *((_DWORD *)this + 19);
      for ( i = *((_DWORD *)this + 9); v53 < (unsigned int)v50; v46 = i )
      {
        i = v46;
        if ( *((int *)this + 6) <= 0 )
          break;
        i = CSQLSatelliteMessageLibraryManagement::ReadSQLSatelliteString(
              this,
              (struct _SQLSatellite_String *)((char *)*v6 + 12 * v53),
              a2,
              *((_DWORD *)this + 12));
        *((_DWORD *)this + 9) = i;
        if ( i < 0 )
          break;
        ++*((_DWORD *)this + 19);
        ++v53;
      }
      v46 = i;
      if ( i >= 0 && v53 == (_DWORD)v50 )
      {
        *((_DWORD *)this + 19) = 0;
        *((_DWORD *)this + 17) = 15;
      }
    }
    *((_DWORD *)this + 9) = v46;
  }
  return (unsigned int)v46;
}

```

## disassembly

```asm
0x10047bcc0  push    rbx
0x10047bcc2  push    rbp
0x10047bcc3  push    rsi
0x10047bcc4  push    rdi
0x10047bcc5  push    r12
0x10047bcc7  push    r13
0x10047bcc9  push    r14
0x10047bccb  push    r15
0x10047bccd  sub     rsp, 78h
0x10047bcd1  mov     rax, cs:__security_cookie
0x10047bcd8  xor     rax, rsp
0x10047bcdb  mov     [rsp+0B8h+var_50], rax
0x10047bce0  mov     esi, [rcx+44h]
0x10047bce3  mov     r13, r9
0x10047bce6  mov     r14, [rsp+0B8h+arg_20]
0x10047bcee  mov     rdi, r8
0x10047bcf1  mov     [rsp+0B8h+var_88], r9
0x10047bcf6  mov     r12, rdx
0x10047bcf9  xor     r9d, r9d
0x10047bcfc  mov     rbp, r8
0x10047bcff  test    r8, r8
0x10047bd02  mov     rbx, rcx
0x10047bd05  mov     r15d, 8007000Eh
0x10047bd0b  cmovz   rdi, r9
0x10047bd0f  lea     edx, [r9+8]
0x10047bd13  cmp     esi, 2
0x10047bd16  jnz     loc_10047BFF7
0x10047bd1c  mov     dword ptr [rcx+24h], 83760002h
0x10047bd23  mov     ecx, [rcx+18h]
0x10047bd26  cmp     ecx, 4
0x10047bd29  jb      loc_10047BFE8
0x10047bd2f  mov     r8, [rbx+10h]
0x10047bd33  mov     edx, r9d
0x10047bd36  mov     eax, [r8]
0x10047bd39  mov     [rbx+38h], eax
0x10047bd3c  jl      short loc_10047BD4E
0x10047bd3e  lea     rax, [r8+4]
0x10047bd42  mov     [rbx+10h], rax
0x10047bd46  lea     eax, [rcx-4]
0x10047bd49  mov     [rbx+18h], eax
0x10047bd4c  jmp     short loc_10047BD53
0x10047bd4e  mov     edx, 83760002h
0x10047bd53  mov     [rbx+24h], edx
0x10047bd56  mov     rdi, rbp
0x10047bd59  test    edx, edx
0x10047bd5b  js      loc_10047BFE8
0x10047bd61  test    r14, r14
0x10047bd64  jz      loc_10047BF15
0x10047bd6a  cmp     dword ptr [r14+94h], 2
0x10047bd72  jnz     loc_10047BF02
0x10047bd78  mov     rax, [rbx+8]
0x10047bd7c  add     rax, 8
0x10047bd80  jz      short loc_10047BD8C
0x10047bd82  movups  xmm0, xmmword ptr [rax]
0x10047bd85  movups  [rsp+0B8h+var_70], xmm0
0x10047bd8a  jmp     short loc_10047BDA6
0x10047bd8c  xorps   xmm0, xmm0
0x10047bd8f  movups  [rsp+0B8h+var_70], xmm0
0x10047bd94  call    cs:__imp__errno
0x10047bd9a  mov     dword ptr [rax], 16h
0x10047bda0  call    cs:__imp__invalid_parameter_noinfo
0x10047bda6  movups  xmm0, xmmword ptr [r14+8]
0x10047bdab  movq    rax, xmm0
0x10047bdb0  movups  [rsp+0B8h+var_60], xmm0
0x10047bdb5  cmp     qword ptr [rsp+0B8h+var_70], rax
0x10047bdba  jnz     loc_10047BFEB
0x10047bdc0  mov     rax, qword ptr [rsp+0B8h+var_70+8]
0x10047bdc5  cmp     rax, qword ptr [rsp+0B8h+var_60+8]
0x10047bdca  jnz     loc_10047BFEB
0x10047bdd0  cmp     qword ptr [r14+20h], 0
0x10047bdd5  mov     r15d, [rbx+38h]
0x10047bdd9  movzx   edi, byte ptr [rbx+3Ch]
0x10047bddd  jnz     short loc_10047BE1C
0x10047bddf  mov     rdx, [r14]
0x10047bde2  lea     r9, aSqlNtdbmsExten_3; "Sql\\Ntdbms\\extensibility\\common\\src"...
0x10047bde9  mov     r8d, 1
0x10047bdef  mov     [rsp+0B8h+var_90], 6
0x10047bdf4  mov     [rsp+0B8h+var_98], 0F6h
0x10047bdfc  lea     ecx, [r8+0Fh]
0x10047be00  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10047be06  mov     [r14+20h], rax
0x10047be0a  test    rax, rax
0x10047be0d  jz      short loc_10047BE7C
0x10047be0f  xor     ecx, ecx
0x10047be11  mov     [rax+8], rcx
0x10047be15  mov     rax, [r14+20h]
0x10047be19  mov     [rax], rcx
0x10047be1c  mov     rdx, [r14]
0x10047be1f  lea     r9, aSqlNtdbmsExten_3; "Sql\\Ntdbms\\extensibility\\common\\src"...
0x10047be26  mov     r8d, 1
0x10047be2c  mov     [rsp+0B8h+var_90], 6
0x10047be31  mov     [rsp+0B8h+var_98], 0BBh
0x10047be39  lea     ecx, [r8+18h]
0x10047be3d  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10047be43  mov     rcx, rax
0x10047be46  test    rax, rax
0x10047be49  jz      short loc_10047BE5C
0x10047be4b  xor     eax, eax
0x10047be4d  xorps   xmm0, xmm0
0x10047be50  movups  xmmword ptr [rcx], xmm0
0x10047be53  mov     [rcx+10h], rax
0x10047be57  mov     [rcx+18h], al
0x10047be5a  jmp     short loc_10047BE5E
0x10047be5c  xor     ecx, ecx
0x10047be5e  mov     rax, [r14+20h]
0x10047be62  neg     dil
0x10047be65  sbb     rdi, rdi
0x10047be68  and     edi, 8
0x10047be6b  mov     [rdi+rax], rcx
0x10047be6f  mov     rax, [r14+20h]
0x10047be73  mov     rcx, [rdi+rax]
0x10047be77  test    rcx, rcx
0x10047be7a  jnz     short loc_10047BE8A
0x10047be7c  mov     r15d, 8007000Eh
0x10047be82  xor     r9d, r9d
0x10047be85  mov     edx, r15d
0x10047be88  jmp     short loc_10047BEED
0x10047be8a  mov     [rcx+14h], r15d
0x10047be8e  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10047be95  mov     [rsp+0B8h+var_90], 6
0x10047be9a  mov     eax, 8
0x10047be9f  mov     [rsp+0B8h+var_98], 0C3h
0x10047bea7  mul     r15
0x10047beaa  mov     rdx, [r14]
0x10047bead  lea     r9, aSqlNtdbmsExten_3; "Sql\\Ntdbms\\extensibility\\common\\src"...
0x10047beb4  lea     r8d, [rcx+2]
0x10047beb8  cmovo   rax, rcx
0x10047bebc  mov     rcx, rax
0x10047bebf  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10047bec5  mov     rcx, [r14+20h]
0x10047bec9  xor     r9d, r9d
0x10047becc  mov     r15d, 8007000Eh
0x10047bed2  mov     rdx, [rcx+rdi]
0x10047bed6  mov     [rdx+0Ch], rax
0x10047beda  mov     edx, r9d
0x10047bedd  mov     rax, [r14+20h]
0x10047bee1  mov     rcx, [rax+rdi]
0x10047bee5  cmp     [rcx+0Ch], rdx
0x10047bee9  cmovz   edx, r15d
0x10047beed  movzx   eax, byte ptr [rbx+3Dh]
0x10047bef1  mov     [rbx+24h], edx
0x10047bef4  mov     [r14+28h], al
0x10047bef8  cmp     dword ptr [rbx+24h], 0
0x10047befc  jl      loc_10047BFE8
0x10047bf02  mov     rcx, [r14+20h]
0x10047bf06  cmp     byte ptr [rbx+3Ch], 0
0x10047bf0a  lea     rax, [rcx+8]
0x10047bf0e  cmovz   rax, rcx
0x10047bf12  mov     rdi, [rax]
0x10047bf15  mov     eax, [rbx+18h]
0x10047bf18  mov     ecx, 83760002h
0x10047bf1d  mov     dword ptr [rbx+24h], 83760002h
0x10047bf24  cmp     eax, 1
0x10047bf27  jb      short loc_10047BF4E
0x10047bf29  mov     rax, [rbx+10h]
0x10047bf2d  movzx   ecx, byte ptr [rax]
0x10047bf30  mov     [rdi+18h], cl
0x10047bf33  mov     ecx, r9d
0x10047bf36  mov     eax, [rbx+18h]
0x10047bf39  cmp     eax, 1
0x10047bf3c  jl      short loc_10047BF49
0x10047bf3e  inc     qword ptr [rbx+10h]
0x10047bf42  dec     eax
0x10047bf44  mov     [rbx+18h], eax
0x10047bf47  jmp     short loc_10047BF4E
0x10047bf49  mov     ecx, 83760002h
0x10047bf4e  mov     [rbx+24h], ecx
0x10047bf51  test    ecx, ecx
0x10047bf53  js      loc_10047BFEB
0x10047bf59  cmp     eax, 4
0x10047bf5c  jb      loc_10047BFEB
0x10047bf62  mov     r9d, [rbx+34h]; unsigned int
0x10047bf66  mov     r8, r12; struct IMemObj *
0x10047bf69  mov     rdx, rdi; struct _SQLSatellite_String *
0x10047bf6c  mov     rcx, rbx; this
0x10047bf6f  call    ?ReadSQLSatelliteString@CSQLSatelliteMessageLibraryManagement@@AEAAJPEAU_SQLSatellite_String@@PEAVIMemObj@@I@Z; CSQLSatelliteMessageLibraryManagement::ReadSQLSatelliteString(_SQLSatellite_String *,IMemObj *,uint)
0x10047bf74  mov     [rbx+24h], eax
0x10047bf77  test    eax, eax
0x10047bf79  js      short loc_10047BFCA
0x10047bf7b  test    r14, r14
0x10047bf7e  jnz     short loc_10047BFCA
0x10047bf80  lfence
0x10047bf83  mov     ecx, [rbx+38h]
0x10047bf86  lea     r9, aSqlNtdbmsExten_2; "Sql\\Ntdbms\\extensibility\\common\\src"...
0x10047bf8d  mov     eax, 8
0x10047bf92  mov     [rsp+0B8h+var_90], 6
0x10047bf97  mul     rcx
0x10047bf9a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10047bfa1  mov     [rsp+0B8h+var_98], 0DBCh
0x10047bfa9  lea     r8d, [r14+1]
0x10047bfad  mov     rdx, r12
0x10047bfb0  cmovo   rax, rcx
0x10047bfb4  mov     rcx, rax
0x10047bfb7  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10047bfbd  mov     [rdi+0Ch], rax
0x10047bfc1  test    rax, rax
0x10047bfc4  jnz     short loc_10047BFCA
0x10047bfc6  mov     [rbx+24h], r15d
0x10047bfca  cmp     dword ptr [rbx+24h], 0
0x10047bfce  jl      loc_10047C159
0x10047bfd4  mov     eax, [rbx+38h]
0x10047bfd7  mov     edx, 8
0x10047bfdc  mov     [rdi+14h], eax
0x10047bfdf  mov     dword ptr [rbx+44h], 3
0x10047bfe6  jmp     short loc_10047C000
0x10047bfe8  mov     rdi, rbp
0x10047bfeb  mov     dword ptr [rbx+24h], 83760002h
0x10047bff2  jmp     loc_10047C159
0x10047bff7  cmp     esi, 3
0x10047bffa  jnz     loc_10047C159
0x10047c000  test    rdi, rdi
0x10047c003  jnz     short loc_10047C018
0x10047c005  mov     rcx, [r14+20h]
0x10047c009  cmp     [rbx+3Ch], dil
0x10047c00d  lea     rax, [rcx+8]
0x10047c011  cmovz   rax, rcx
0x10047c015  mov     rdi, [rax]
0x10047c018  mov     ebp, [rbx+48h]
0x10047c01b  movzx   r13d, byte ptr [rdi+18h]
0x10047c020  cmp     ebp, [rdi+14h]
0x10047c023  jnb     loc_10047C141
0x10047c029  cmp     r13b, 2
0x10047c02d  mov     r15d, 0Ch
0x10047c033  cmovz   r15d, edx
0x10047c037  nop     word ptr [rax+rax+00000000h]
0x10047c040  cmp     [rbx+18h], r15d
0x10047c044  jl      loc_10047C13E
0x10047c04a  mov     r8d, 1
0x10047c050  mov     [rsp+0B8h+var_90], 6
0x10047c055  lea     r9, aSqlNtdbmsExten_2; "Sql\\Ntdbms\\extensibility\\common\\src"...
0x10047c05c  mov     [rsp+0B8h+var_98], 0E3Eh
0x10047c064  mov     rdx, r12
0x10047c067  lea     ecx, [r8+1Bh]
0x10047c06b  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10047c071  mov     rsi, rax
0x10047c074  test    rax, rax
0x10047c077  jz      loc_10047C137
0x10047c07d  xor     eax, eax
0x10047c07f  xorps   xmm0, xmm0
0x10047c082  movups  xmmword ptr [rsi], xmm0
0x10047c085  mov     [rsi+10h], rax
0x10047c089  mov     r8, r12; struct IMemObj *
0x10047c08c  mov     [rsi+18h], eax
0x10047c08f  mov     rdx, rsi; struct _SQLSatellite_String *
0x10047c092  mov     r9d, [rbx+34h]; unsigned int
0x10047c096  mov     rcx, rbx; this
0x10047c099  call    ?ReadSQLSatelliteString@CSQLSatelliteMessageLibraryManagement@@AEAAJPEAU_SQLSatellite_String@@PEAVIMemObj@@I@Z; CSQLSatelliteMessageLibraryManagement::ReadSQLSatelliteString(_SQLSatellite_String *,IMemObj *,uint)
0x10047c09e  mov     [rbx+24h], eax
0x10047c0a1  cmp     eax, 0
0x10047c0a4  jl      short loc_10047C117
0x10047c0a6  cmp     dword ptr [rbx+18h], 4
0x10047c0aa  mov     ecx, 83760002h
0x10047c0af  mov     dword ptr [rbx+24h], 83760002h
0x10047c0b6  jb      short loc_10047C0DD
0x10047c0b8  mov     rax, [rbx+10h]
0x10047c0bc  mov     ecx, [rax]
0x10047c0be  mov     [rsi+0Ch], ecx
0x10047c0c1  xor     ecx, ecx
0x10047c0c3  mov     eax, [rbx+18h]
0x10047c0c6  cmp     eax, 4
0x10047c0c9  jl      short loc_10047C0D8
0x10047c0cb  add     qword ptr [rbx+10h], 4
0x10047c0d0  add     eax, 0FFFFFFFCh
0x10047c0d3  mov     [rbx+18h], eax
0x10047c0d6  jmp     short loc_10047C0DD
0x10047c0d8  mov     ecx, 83760002h
0x10047c0dd  mov     [rbx+24h], ecx
0x10047c0e0  test    ecx, ecx
0x10047c0e2  js      short loc_10047C117
0x10047c0e4  cmp     r13b, 2
0x10047c0e8  jz      short loc_10047C102
0x10047c0ea  mov     r9d, [rbx+34h]; unsigned int
0x10047c0ee  lea     rdx, [rsi+10h]; struct _SQLSatellite_String *
0x10047c0f2  mov     r8, r12; struct IMemObj *
0x10047c0f5  mov     rcx, rbx; this
0x10047c0f8  call    ?ReadSQLSatelliteString@CSQLSatelliteMessageLibraryManagement@@AEAAJPEAU_SQLSatellite_String@@PEAVIMemObj@@I@Z; CSQLSatelliteMessageLibraryManagement::ReadSQLSatelliteString(_SQLSatellite_String *,IMemObj *,uint)
0x10047c0fd  mov     [rbx+24h], eax
0x10047c100  jmp     short loc_10047C117
0x10047c102  xor     ecx, ecx
0x10047c104  mov     [rsp+0B8h+var_80], rcx
0x10047c109  movsd   xmm0, [rsp+0B8h+var_80]
0x10047c10f  movsd   qword ptr [rsi+10h], xmm0
0x10047c114  mov     [rsi+18h], ecx
0x10047c117  cmp     dword ptr [rbx+24h], 0
0x10047c11b  jl      short loc_10047C13E
0x10047c11d  mov     rax, [rdi+0Ch]
0x10047c121  mov     ecx, ebp
0x10047c123  inc     ebp
0x10047c125  mov     [rax+rcx*8], rsi
0x10047c129  inc     dword ptr [rbx+48h]
0x10047c12c  cmp     ebp, [rdi+14h]
0x10047c12f  jb      loc_10047C040
0x10047c135  jmp     short loc_10047C13E
0x10047c137  mov     dword ptr [rbx+24h], 8007000Eh
0x10047c13e  cmp     ebp, [rdi+14h]
0x10047c141  jnz     short loc_10047C151
0x10047c143  cmp     dword ptr [rbx+24h], 0
0x10047c147  jl      short loc_10047C151
0x10047c149  mov     qword ptr [rbx+44h], 4
0x10047c151  mov     esi, [rbx+44h]
  ... truncated ...
```
