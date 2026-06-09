# WIATRACE_OutputString(int,void *,void *,HINSTANCE__ *,char const *,_SYSTEMTIME *,ulong,ulong,tagWiaTraceData_Type *)

- ea: `0x180001300`
- end: `0x180001f10`
- name: `?WIATRACE_OutputString@@YAXHPEAX0PEAUHINSTANCE__@@PEBDPEAU_SYSTEMTIME@@KKPEAUtagWiaTraceData_Type@@@Z`
- size: `3088`
- prototype: `void __fastcall(int, void *, void *, HINSTANCE, const char *, struct _SYSTEMTIME *, void *, unsigned int, struct tagWiaTraceData_Type *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops`

## callees

- `0x180001010`
- `0x180001300`
- `0x180001f20`
- `0x180001fb0`
- `0x180002300`
- `0x1800024e0`
- `0x180002980`
- `0x1800031fa`
- `0x180003390`

## import_xrefs

- `KERNEL32!SetFilePointerEx` at `0x1800014ad`
- `KERNEL32!SetFilePointerEx` at `0x1800014c9`
- `KERNEL32!SetFilePointerEx` at `0x1800014ad`
- `KERNEL32!SetFilePointerEx` at `0x1800014c9`
- `KERNEL32!ReleaseMutex` at `0x180001509`
- `KERNEL32!ReleaseMutex` at `0x180001509`
- `KERNEL32!WaitForSingleObject` at `0x180001482`
- `KERNEL32!WaitForSingleObject` at `0x180001482`
- `KERNEL32!WriteFile` at `0x180001500`
- `KERNEL32!WriteFile` at `0x180001e01`
- `KERNEL32!WriteFile` at `0x180001e6c`
- `KERNEL32!WriteFile` at `0x180001500`
- `KERNEL32!WriteFile` at `0x180001e01`
- `KERNEL32!WriteFile` at `0x180001e6c`

## string_xrefs

- `0x180001da9`: `WIA: ERROR!!! Failed to write to trace file, couldn't gain access!!!, WaitResult = %lu`

## pseudocode

```c
void __fastcall WIATRACE_OutputString(
        int a1,
        void *a2,
        void *a3,
        HINSTANCE a4,
        const char *a5,
        struct _SYSTEMTIME *a6,
        void *a7,
        unsigned int a8,
        struct tagWiaTraceData_Type *a9)
{
  const char *v12; // rdx
  __int64 v13; // rbx
  char *v14; // rdi
  __int64 v15; // rcx
  int v16; // eax
  const char *v17; // rax
  unsigned int v18; // r11d
  __int64 v19; // r9
  DWORD v20; // r14d
  struct _SYSTEMTIME *v21; // rdx
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  const char *v26; // rax
  const char *v27; // rax
  const char *v28; // r8
  const char *QuadPart; // r8
  __int64 v30; // rax
  unsigned int v31; // r10d
  int v32; // r11d
  const char *v33; // r9
  const char *v34; // r8
  __int64 v35; // rax
  const char *v36; // r8
  const char *v37; // r8
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rax
  int v45; // eax
  const char *v46; // r8
  const char *v47; // r9
  __int64 v48; // rax
  int v49; // ecx
  const char *v50; // r8
  void *v51; // rdx
  __int64 v52; // r8
  __int64 v53; // r8
  char *lpOverlapped; // [rsp+20h] [rbp-E0h]
  char *lpOverlappeda; // [rsp+20h] [rbp-E0h]
  unsigned int v56; // [rsp+28h] [rbp-D8h]
  char *v57; // [rsp+28h] [rbp-D8h]
  DWORD NumberOfBytesWritten[2]; // [rsp+70h] [rbp-90h] BYREF
  LARGE_INTEGER v59; // [rsp+78h] [rbp-88h] BYREF
  LARGE_INTEGER NewFilePointer; // [rsp+80h] [rbp-80h] BYREF
  struct _SYSTEMTIME v61; // [rsp+90h] [rbp-70h] BYREF
  char Buffer[2048]; // [rsp+190h] [rbp+90h] BYREF
  char v63[2048]; // [rsp+990h] [rbp+890h] BYREF

  *(_QWORD *)NumberOfBytesWritten = a5;
  NewFilePointer.QuadPart = (LONGLONG)a6;
  memset_0(Buffer, 0, sizeof(Buffer));
  memset_0(v63, 0, sizeof(v63));
  if ( !a9 )
    return;
  v12 = *(const char **)a9;
  if ( !*(_QWORD *)a9 )
    return;
  v13 = -1;
  if ( ((unsigned int)a7 & 0xFEFF0000) == 0 )
  {
    v14 = Buffer;
    v15 = 0;
    v16 = *((_DWORD *)a9 + 12);
    if ( ((unsigned int)a7 & 0xFFFF0000) != 0x1000000 )
      v15 = *((_QWORD *)a9 + 3);
    if ( v16 == 16 )
      goto LABEL_7;
    v22 = v16 - 1;
    if ( v22 )
    {
      v23 = v22 - 1;
      if ( !v23 )
      {
        v27 = (const char *)*((_QWORD *)a9 + 5);
        v18 = *((_DWORD *)a9 + 2);
        if ( !v15 )
        {
          v19 = *((unsigned int *)a9 + 3);
          if ( v27 )
          {
            StringCchPrintfA(
              Buffer,
              0x800u,
              "WIA: %lu.%lu %lu %X %lu [%s] WARNING: %s, %s\r\n",
              v19,
              *((_DWORD *)a9 + 4),
              v18,
              *((_DWORD *)a9 + 13),
              *((_DWORD *)a9 + 14),
              *(const char **)NumberOfBytesWritten,
              v27,
              v12);
            goto LABEL_10;
          }
          v28 = "WIA: %lu.%lu %lu %X %lu [%s] WARNING: %s\r\n";
          goto LABEL_31;
        }
        v49 = *((_DWORD *)a9 + 8);
        if ( v27 )
          v50 = "%hs(%lu) : %lu.%lu %lu %X %lu [%s] WIA: WARNING: %s, %s\r\n";
        else
          v50 = "%hs(%lu) : %lu.%lu %lu %X %lu [%s] WIA: WARNING: %s\r\n";
LABEL_105:
        v56 = *((_DWORD *)a9 + 3);
        LODWORD(lpOverlapped) = v49;
        StringCchPrintfA(Buffer, 0x800u, v50);
        goto LABEL_10;
      }
      v24 = v23 - 2;
      if ( !v24 || (v25 = v24 - 4) == 0 )
      {
LABEL_7:
        v17 = (const char *)*((_QWORD *)a9 + 5);
        v18 = *((_DWORD *)a9 + 2);
        if ( !v15 )
        {
          v19 = *((unsigned int *)a9 + 3);
          if ( v17 )
          {
            StringCchPrintfA(
              Buffer,
              0x800u,
              "WIA: %lu.%lu %lu %X %lu [%s] %s, %s\r\n",
              v19,
              *((_DWORD *)a9 + 4),
              v18,
              *((_DWORD *)a9 + 13),
              *((_DWORD *)a9 + 14),
              *(const char **)NumberOfBytesWritten,
              v17,
              v12);
            goto LABEL_10;
          }
          v28 = "WIA: %lu.%lu %lu %X %lu [%s] %s\r\n";
LABEL_31:
          v56 = v18;
          StringCchPrintfA(Buffer, 0x800u, v28, v19, *((_DWORD *)a9 + 4));
          goto LABEL_10;
        }
        v49 = *((_DWORD *)a9 + 8);
        if ( v17 )
          v50 = "%hs(%lu) : %lu.%lu %lu %X %lu [%s] WIA: %s, %s\r\n";
        else
          v50 = "%hs(%lu) : %lu.%lu %lu %X %lu [%s] WIA: %s\r\n";
        goto LABEL_105;
      }
      if ( v25 != 120 )
        goto LABEL_10;
    }
    v26 = (const char *)*((_QWORD *)a9 + 5);
    v18 = *((_DWORD *)a9 + 2);
    if ( !v15 )
    {
      v19 = *((unsigned int *)a9 + 3);
      if ( v26 )
      {
        StringCchPrintfA(
          Buffer,
          0x800u,
          "WIA: %lu.%lu %lu %X %lu [%s] ERROR: %s, %s\r\n",
          v19,
          *((_DWORD *)a9 + 4),
          v18,
          *((_DWORD *)a9 + 13),
          *((_DWORD *)a9 + 14),
          *(const char **)NumberOfBytesWritten,
          v26,
          v12);
        goto LABEL_10;
      }
      v28 = "WIA: %lu.%lu %lu %X %lu [%s] ERROR: %s\r\n";
      goto LABEL_31;
    }
    v49 = *((_DWORD *)a9 + 8);
    if ( v26 )
      v50 = "%hs(%lu) : %lu.%lu %lu %X %lu [%s] WIA: ERROR: %s, %s\r\n";
    else
      v50 = "%hs(%lu) : %lu.%lu %lu %X %lu [%s] WIA: ERROR: %s\r\n";
    goto LABEL_105;
  }
  QuadPart = (const char *)*((_QWORD *)a9 + 3);
  v59.QuadPart = (LONGLONG)QuadPart;
  if ( ((unsigned __int16)a7 & 0x2000) != 0 )
  {
    v14 = Buffer;
  }
  else
  {
    v14 = v63;
    switch ( *((_DWORD *)a9 + 12) )
    {
      case 1:
      case 0x80:
        v35 = *((_QWORD *)a9 + 5);
        v31 = *((_DWORD *)a9 + 2);
        v32 = *((_DWORD *)a9 + 4);
        if ( QuadPart )
        {
          v33 = QuadPart;
          if ( v35 )
            v34 = "%hs(%lu) : %lu.%lu %lu %X %lu [%s] WIA: ERROR: %s, %s\r\n";
          else
            v34 = "%hs(%lu) : %lu.%lu %lu %X %lu [%s] WIA: ERROR: %s\r\n";
          goto LABEL_43;
        }
        if ( v35 )
        {
          v36 = "WIA: %lu.%lu %lu %X %lu [%s] ERROR: %s, %s\r\n";
          goto LABEL_58;
        }
        v37 = "WIA: %lu.%lu %lu %X %lu [%s] ERROR: %s\r\n";
        goto LABEL_48;
      case 2:
        v30 = *((_QWORD *)a9 + 5);
        v31 = *((_DWORD *)a9 + 2);
        v32 = *((_DWORD *)a9 + 4);
        if ( QuadPart )
        {
          v33 = QuadPart;
          if ( v30 )
            v34 = "%hs(%lu) : %lu.%lu %lu %X %lu [%s] WIA: WARNING: %s, %s\r\n";
          else
            v34 = "%hs(%lu) : %lu.%lu %lu %X %lu [%s] WIA: WARNING: %s\r\n";
          goto LABEL_43;
        }
        if ( v30 )
        {
          v36 = "WIA: %lu.%lu %lu %X %lu [%s] WARNING: %s, %s\r\n";
          goto LABEL_58;
        }
        v37 = "WIA: %lu.%lu %lu %X %lu [%s] WARNING: %s\r\n";
        goto LABEL_48;
      case 4:
      case 8:
      case 0x10:
        v38 = *((_QWORD *)a9 + 5);
        v31 = *((_DWORD *)a9 + 2);
        v32 = *((_DWORD *)a9 + 4);
        if ( QuadPart )
        {
          if ( !v38 )
          {
            StringCchPrintfA(
              v63,
              0x800u,
              "%hs(%lu) : %lu.%lu %lu %X %lu [%s] WIA: %s\r\n",
              QuadPart,
              *((_DWORD *)a9 + 8),
              *((_DWORD *)a9 + 3),
              v32,
              v31,
              *((_DWORD *)a9 + 13),
              *((_DWORD *)a9 + 14),
              *(const char **)NumberOfBytesWritten,
              v12);
            QuadPart = (const char *)v59.QuadPart;
            break;
          }
          v33 = QuadPart;
          v34 = "%hs(%lu) : %lu.%lu %lu %X %lu [%s] WIA: %s, %s\r\n";
LABEL_43:
          v56 = *((_DWORD *)a9 + 3);
          StringCchPrintfA(v63, 0x800u, v34, v33, *((_DWORD *)a9 + 8));
          goto LABEL_59;
        }
        if ( v38 )
        {
          v36 = "WIA: %lu.%lu %lu %X %lu [%s] %s, %s\r\n";
LABEL_58:
          v56 = v31;
          StringCchPrintfA(v63, 0x800u, v36, *((unsigned int *)a9 + 3), v32);
LABEL_59:
          QuadPart = (const char *)v59.QuadPart;
          break;
        }
        v37 = "WIA: %lu.%lu %lu %X %lu [%s] %s\r\n";
LABEL_48:
        v56 = v31;
        StringCchPrintfA(v63, 0x800u, v37, *((unsigned int *)a9 + 3), v32);
        QuadPart = (const char *)v59.QuadPart;
        break;
      default:
        break;
    }
  }
  if ( ((unsigned int)a7 & 0x1000000) == 0 && QuadPart && *((_DWORD *)a9 + 8) )
  {
    v39 = -1;
    do
      ++v39;
    while ( Buffer[v39] );
    StringCchPrintfA(
      &Buffer[(unsigned int)v39],
      2048LL - (unsigned int)v39,
      "%hs(%lu) : ",
      QuadPart,
      *((_DWORD *)a9 + 8));
  }
  if ( ((unsigned int)a7 & 0x4000000) == 0 )
  {
    v40 = -1;
    do
      ++v40;
    while ( Buffer[v40] );
    StringCchPrintfA(
      &Buffer[(unsigned int)v40],
      2048LL - (unsigned int)v40,
      "%lu.%lu ",
      *((_DWORD *)a9 + 3),
      *((_DWORD *)a9 + 4));
  }
  if ( ((unsigned int)a7 & 0x2000000) == 0 )
  {
    v41 = -1;
    do
      ++v41;
    while ( Buffer[v41] );
    StringCchPrintfA(&Buffer[(unsigned int)v41], 2048LL - (unsigned int)v41, "%lu ", *((_DWORD *)a9 + 2));
  }
  if ( ((unsigned int)a7 & 0x10000000) == 0 )
  {
    v42 = -1;
    do
      ++v42;
    while ( Buffer[v42] );
    StringCchPrintfA(&Buffer[(unsigned int)v42], 2048LL - (unsigned int)v42, "%X ", *((_DWORD *)a9 + 13));
  }
  if ( ((unsigned int)a7 & 0x20000000) == 0 )
  {
    v43 = -1;
    do
      ++v43;
    while ( Buffer[v43] );
    StringCchPrintfA(&Buffer[(unsigned int)v43], 2048LL - (unsigned int)v43, "%lu ", *((_DWORD *)a9 + 14));
  }
  if ( ((unsigned int)a7 & 0x8000000) == 0 )
  {
    v44 = -1;
    do
      ++v44;
    while ( Buffer[v44] );
    StringCchPrintfA(
      &Buffer[(unsigned int)v44],
      2048LL - (unsigned int)v44,
      "[%s] ",
      *(const char **)NumberOfBytesWritten);
  }
  if ( ((unsigned int)a7 & 0x40000000) == 0 )
    StringCchCatA(Buffer, 0x800u, "WIA: ");
  if ( (int)a7 >= 0 )
  {
    v45 = *((_DWORD *)a9 + 12);
    if ( v45 == 1 || v45 == 128 )
    {
      v46 = "ERROR: ";
    }
    else
    {
      if ( v45 != 2 )
        goto LABEL_96;
      v46 = "WARNING: ";
    }
    StringCchCatA(Buffer, 0x800u, v46);
  }
LABEL_96:
  if ( ((unsigned int)a7 & 0x800000) == 0 )
  {
    v47 = (const char *)*((_QWORD *)a9 + 5);
    if ( v47 )
    {
      v48 = -1;
      do
        ++v48;
      while ( Buffer[v48] );
      StringCchPrintfA(&Buffer[(unsigned int)v48], 2048LL - (unsigned int)v48, "%s, ", v47);
    }
  }
  StringCchCatA(Buffer, 0x800u, *(const char **)a9);
  StringCchCatA(Buffer, 0x800u, "\r\n");
LABEL_10:
  if ( a1 )
  {
    memset_0(&v61, 0, 0x100u);
    WiaTrace::GetBanner(
      (WiaTrace *)1,
      NumberOfBytesWritten[0],
      (const char *)NewFilePointer.QuadPart,
      &v61,
      lpOverlapped,
      v56);
    WiaTrace::WriteToFile(a2, a3, (void *)(unsigned int)a7, a8, (unsigned int)&v61, v57);
  }
  NumberOfBytesWritten[0] = 0;
  if ( !WiaTrace::g_TraceOutput_bMaxFileSizeReached )
  {
    v20 = WaitForSingleObject(a3, 0x2710u);
    if ( (v20 & 0xFFFFFF7F) != 0 )
    {
      memset_0(&v61, 0, 0x100u);
      StringCchPrintfA(
        (char *)&v61,
        0x100u,
        "WIA: ERROR!!! Failed to write to trace file, couldn't gain access!!!, WaitResult = %lu",
        v20);
      return;
    }
    NewFilePointer.QuadPart = 0;
    SetFilePointerEx(a2, 0, &NewFilePointer, 2u);
    v59.QuadPart = 0;
    SetFilePointerEx(a2, 0, &v59, 1u);
    if ( v59.QuadPart > (unsigned __int64)a8 )
    {
      memset_0(&v61, 0, 0x100u);
      if ( ((unsigned __int16)a7 & 0x200) != 0 )
      {
        WiaTrace::g_TraceOutput_bMaxFileSizeReached = 1;
        v52 = -1;
        do
          ++v52;
        while ( v14[v52] );
        WriteFile(a2, v14, v52, NumberOfBytesWritten, 0);
        WiaTrace::GetBanner((WiaTrace *)3, 0, 0, &v61, lpOverlappeda, v56);
        do
          ++v13;
        while ( *((_BYTE *)&v61.wYear + v13) );
        v21 = &v61;
        goto LABEL_17;
      }
      WiaTrace::WrapFile(a2, v51);
      WiaTrace::GetBanner((WiaTrace *)2, 0, 0, &v61, lpOverlapped, v56);
      v53 = -1;
      do
        ++v53;
      while ( *((_BYTE *)&v61.wYear + v53) );
      WriteFile(a2, &v61, v53, NumberOfBytesWritten, 0);
      do
        ++v13;
      while ( v14[v13] );
    }
    else
    {
      do
        ++v13;
      while ( v14[v13] );
    }
    v21 = (struct _SYSTEMTIME *)v14;
LABEL_17:
    WriteFile(a2, v21, v13, NumberOfBytesWritten, 0);
    ReleaseMutex(a3);
  }
}

```

## disassembly

```asm
0x180001300  push    rbp
0x180001302  push    rsi
0x180001303  push    r12
0x180001305  push    r14
0x180001307  push    r15
0x180001309  lea     rbp, [rsp-10B0h]
0x180001311  mov     eax, 11B0h
0x180001316  call    _alloca_probe
0x18000131b  sub     rsp, rax
0x18000131e  mov     rax, cs:__security_cookie
0x180001325  xor     rax, rsp
0x180001328  mov     [rbp+10D0h+var_40], rax
0x18000132f  mov     rax, [rbp+10D0h+arg_20]
0x180001336  mov     r12, r8
0x180001339  mov     rsi, [rbp+10D0h+arg_40]
0x180001340  mov     r15, rdx
0x180001343  mov     qword ptr [rsp+11D0h+NumberOfBytesWritten], rax
0x180001348  mov     r14d, ecx
0x18000134b  mov     rax, [rbp+10D0h+arg_28]
0x180001352  lea     rcx, [rbp+10D0h+Buffer]; void *
0x180001359  xor     edx, edx; Val
0x18000135b  mov     qword ptr [rbp+10D0h+NewFilePointer], rax
0x18000135f  mov     r8d, 800h; Size
0x180001365  call    memset_0
0x18000136a  xor     edx, edx; Val
0x18000136c  lea     rcx, [rbp+10D0h+var_840]; void *
0x180001373  mov     r8d, 800h; Size
0x180001379  call    memset_0
0x18000137e  test    rsi, rsi
0x180001381  jz      loc_180001527
0x180001387  mov     rdx, [rsi]
0x18000138a  test    rdx, rdx
0x18000138d  jz      loc_180001527
0x180001393  mov     [rsp+11D0h+arg_0], rbx
0x18000139b  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800013a2  mov     [rsp+11D0h+var_30], r13
0x1800013aa  mov     r13d, dword ptr [rbp+10D0h+arg_30]
0x1800013b1  mov     eax, r13d
0x1800013b4  and     eax, 0FFFF0000h
0x1800013b9  mov     [rsp+11D0h+var_28], rdi
0x1800013c1  test    eax, 0FEFFFFFFh
0x1800013c6  jnz     loc_1800016E8
0x1800013cc  mov     r9, [rsi+18h]
0x1800013d0  lea     rdi, [rbp+10D0h+Buffer]
0x1800013d7  xor     ecx, ecx
0x1800013d9  cmp     eax, 1000000h
0x1800013de  mov     eax, [rsi+30h]
0x1800013e1  cmovnz  rcx, r9
0x1800013e5  cmp     eax, 10h
0x1800013e8  jnz     loc_180001546
0x1800013ee  mov     rax, [rsi+28h]
0x1800013f2  mov     r8d, [rsi+38h]
0x1800013f6  mov     r10d, [rsi+34h]
0x1800013fa  mov     r11d, [rsi+8]
0x1800013fe  test    rcx, rcx
0x180001401  jnz     loc_180001D1C
0x180001407  mov     r9d, [rsi+0Ch]
0x18000140b  lea     rcx, [rbp+10D0h+Buffer]; char *
0x180001412  test    rax, rax
0x180001415  jz      loc_180001D75
0x18000141b  mov     [rsp+11D0h+var_1180], rdx
0x180001420  mov     edx, 800h; unsigned __int64
0x180001425  mov     [rsp+11D0h+var_1188], rax
0x18000142a  mov     rax, qword ptr [rsp+11D0h+NumberOfBytesWritten]
0x18000142f  mov     [rsp+11D0h+var_1190], rax
0x180001434  mov     eax, [rsi+10h]
0x180001437  mov     [rsp+11D0h+var_1198], r8d
0x18000143c  lea     r8, aWiaLuLuLuXLuSS_0; "WIA: %lu.%lu %lu %X %lu [%s] %s, %s\r\n"
0x180001443  mov     [rsp+11D0h+var_11A0], r10d
0x180001448  mov     dword ptr [rsp+11D0h+var_11A8], r11d; unsigned int
0x18000144d  mov     dword ptr [rsp+11D0h+lpOverlapped], eax; char *
0x180001451  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180001456  mov     esi, [rbp+10D0h+arg_38]
0x18000145c  test    r14d, r14d
0x18000145f  jnz     loc_180001649
0x180001465  cmp     cs:?g_TraceOutput_bMaxFileSizeReached@WiaTrace@@3HA, 0; int WiaTrace::g_TraceOutput_bMaxFileSizeReached
0x18000146c  mov     [rsp+11D0h+NumberOfBytesWritten], 0
0x180001474  jnz     loc_18000150F
0x18000147a  mov     edx, 2710h; dwMilliseconds
0x18000147f  mov     rcx, r12; hHandle
0x180001482  call    cs:__imp_WaitForSingleObject
0x180001488  mov     r14d, eax
0x18000148b  test    eax, 0FFFFFF7Fh
0x180001490  jnz     loc_180001D95
0x180001496  xor     r14d, r14d
0x180001499  lea     r8, [rbp+10D0h+NewFilePointer]; lpNewFilePointer
0x18000149d  mov     edx, r14d; liDistanceToMove
0x1800014a0  mov     qword ptr [rbp+10D0h+NewFilePointer], r14
0x1800014a4  mov     r9d, 2; dwMoveMethod
0x1800014aa  mov     rcx, r15; hFile
0x1800014ad  call    cs:__imp_SetFilePointerEx
0x1800014b3  mov     r9d, 1; dwMoveMethod
0x1800014b9  mov     qword ptr [rsp+11D0h+var_1158], r14
0x1800014be  lea     r8, [rsp+11D0h+var_1158]; lpNewFilePointer
0x1800014c3  mov     edx, r14d; liDistanceToMove
0x1800014c6  mov     rcx, r15; hFile
0x1800014c9  call    cs:__imp_SetFilePointerEx
0x1800014cf  cmp     dword ptr [rsp+11D0h+var_1158+4], r14d
0x1800014d4  jnz     loc_180001DC3
0x1800014da  cmp     dword ptr [rsp+11D0h+var_1158], esi
0x1800014de  ja      loc_180001DC3
0x1800014e4  inc     rbx
0x1800014e7  cmp     [rdi+rbx], r14b
0x1800014eb  jnz     short loc_1800014E4
0x1800014ed  mov     rdx, rdi; lpBuffer
0x1800014f0  lea     r9, [rsp+11D0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800014f5  mov     [rsp+11D0h+lpOverlapped], r14; lpOverlapped
0x1800014fa  mov     r8d, ebx; nNumberOfBytesToWrite
0x1800014fd  mov     rcx, r15; hFile
0x180001500  call    cs:__imp_WriteFile
0x180001506  mov     rcx, r12; hMutex
0x180001509  call    cs:__imp_ReleaseMutex
0x18000150f  mov     rdi, [rsp+11D0h+var_28]
0x180001517  mov     rbx, [rsp+11D0h+arg_0]
0x18000151f  mov     r13, [rsp+11D0h+var_30]
0x180001527  mov     rcx, [rbp+10D0h+var_40]
0x18000152e  xor     rcx, rsp; StackCookie
0x180001531  call    __security_check_cookie
0x180001536  add     rsp, 11B0h
0x18000153d  pop     r15
0x18000153f  pop     r14
0x180001541  pop     r12
0x180001543  pop     rsi
0x180001544  pop     rbp
0x180001545  retn
0x180001546  sub     eax, 1
0x180001549  jz      short loc_18000156F
0x18000154b  sub     eax, 1
0x18000154e  jz      loc_1800015DC
0x180001554  sub     eax, 2
0x180001557  jz      loc_1800013EE
0x18000155d  sub     eax, 4
0x180001560  jz      loc_1800013EE
0x180001566  cmp     eax, 78h ; 'x'
0x180001569  jnz     loc_180001456
0x18000156f  mov     rax, [rsi+28h]
0x180001573  mov     r8d, [rsi+38h]
0x180001577  mov     r10d, [rsi+34h]
0x18000157b  mov     r11d, [rsi+8]
0x18000157f  test    rcx, rcx
0x180001582  jnz     loc_180001CD5
0x180001588  mov     r9d, [rsi+0Ch]
0x18000158c  lea     rcx, [rbp+10D0h+Buffer]; char *
0x180001593  test    rax, rax
0x180001596  jz      loc_180001690
0x18000159c  mov     [rsp+11D0h+var_1180], rdx
0x1800015a1  mov     edx, 800h; unsigned __int64
0x1800015a6  mov     [rsp+11D0h+var_1188], rax
0x1800015ab  mov     rax, qword ptr [rsp+11D0h+NumberOfBytesWritten]
0x1800015b0  mov     [rsp+11D0h+var_1190], rax
0x1800015b5  mov     eax, [rsi+10h]
0x1800015b8  mov     [rsp+11D0h+var_1198], r8d
0x1800015bd  lea     r8, aWiaLuLuLuXLuSE_0; "WIA: %lu.%lu %lu %X %lu [%s] ERROR: %s,"...
0x1800015c4  mov     [rsp+11D0h+var_11A0], r10d
0x1800015c9  mov     dword ptr [rsp+11D0h+var_11A8], r11d
0x1800015ce  mov     dword ptr [rsp+11D0h+lpOverlapped], eax
0x1800015d2  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800015d7  jmp     loc_180001456
0x1800015dc  mov     rax, [rsi+28h]
0x1800015e0  mov     r8d, [rsi+38h]
0x1800015e4  mov     r10d, [rsi+34h]
0x1800015e8  mov     r11d, [rsi+8]
0x1800015ec  test    rcx, rcx
0x1800015ef  jnz     loc_180001C3C
0x1800015f5  mov     r9d, [rsi+0Ch]
0x1800015f9  lea     rcx, [rbp+10D0h+Buffer]; char *
0x180001600  test    rax, rax
0x180001603  jz      loc_1800016CB
0x180001609  mov     [rsp+11D0h+var_1180], rdx
0x18000160e  mov     edx, 800h; unsigned __int64
0x180001613  mov     [rsp+11D0h+var_1188], rax
0x180001618  mov     rax, qword ptr [rsp+11D0h+NumberOfBytesWritten]
0x18000161d  mov     [rsp+11D0h+var_1190], rax
0x180001622  mov     eax, [rsi+10h]
0x180001625  mov     [rsp+11D0h+var_1198], r8d
0x18000162a  lea     r8, aWiaLuLuLuXLuSW; "WIA: %lu.%lu %lu %X %lu [%s] WARNING: %"...
0x180001631  mov     [rsp+11D0h+var_11A0], r10d
0x180001636  mov     dword ptr [rsp+11D0h+var_11A8], r11d
0x18000163b  mov     dword ptr [rsp+11D0h+lpOverlapped], eax
0x18000163f  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180001644  jmp     loc_180001456
0x180001649  xor     edx, edx; Val
0x18000164b  lea     rcx, [rbp+10D0h+var_1140]; void *
0x18000164f  mov     r8d, 100h; Size
0x180001655  call    memset_0
0x18000165a  mov     r8, qword ptr [rbp+10D0h+NewFilePointer]; char *
0x18000165e  lea     r9, [rbp+10D0h+var_1140]; struct _SYSTEMTIME *
0x180001662  mov     rdx, qword ptr [rsp+11D0h+NumberOfBytesWritten]; unsigned int
0x180001667  mov     ecx, 1; this
0x18000166c  call    ?GetBanner@WiaTrace@@YAJKPEBDPEAU_SYSTEMTIME@@PEADK@Z; WiaTrace::GetBanner(ulong,char const *,_SYSTEMTIME *,char *,ulong)
0x180001671  lea     rax, [rbp+10D0h+var_1140]
0x180001675  mov     r9d, esi; unsigned int
0x180001678  mov     r8d, r13d; void *
0x18000167b  mov     [rsp+11D0h+lpOverlapped], rax; unsigned int
0x180001680  mov     rdx, r12; hMutex
0x180001683  mov     rcx, r15; hFile
0x180001686  call    ?WriteToFile@WiaTrace@@YAJPEAX0KKPEBD@Z; WiaTrace::WriteToFile(void *,void *,ulong,ulong,char const *)
0x18000168b  jmp     loc_180001465
0x180001690  mov     rax, qword ptr [rsp+11D0h+NumberOfBytesWritten]
0x180001695  mov     [rsp+11D0h+var_1188], rdx
0x18000169a  mov     [rsp+11D0h+var_1190], rax
0x18000169f  mov     [rsp+11D0h+var_1198], r8d
0x1800016a4  lea     r8, aWiaLuLuLuXLuSE; "WIA: %lu.%lu %lu %X %lu [%s] ERROR: %s"...
0x1800016ab  mov     eax, [rsi+10h]
0x1800016ae  mov     edx, 800h; unsigned __int64
0x1800016b3  mov     [rsp+11D0h+var_11A0], r10d
0x1800016b8  mov     dword ptr [rsp+11D0h+var_11A8], r11d
0x1800016bd  mov     dword ptr [rsp+11D0h+lpOverlapped], eax
0x1800016c1  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800016c6  jmp     loc_180001456
0x1800016cb  mov     rax, qword ptr [rsp+11D0h+NumberOfBytesWritten]
0x1800016d0  mov     [rsp+11D0h+var_1188], rdx
0x1800016d5  mov     [rsp+11D0h+var_1190], rax
0x1800016da  mov     [rsp+11D0h+var_1198], r8d
0x1800016df  lea     r8, aWiaLuLuLuXLuSW_0; "WIA: %lu.%lu %lu %X %lu [%s] WARNING: %"...
0x1800016e6  jmp     short loc_1800016AB
0x1800016e8  mov     r8, [rsi+18h]
0x1800016ec  mov     qword ptr [rsp+11D0h+var_1158], r8
0x1800016f1  bt      r13d, 0Dh
0x1800016f6  jb      loc_1800019DA
0x1800016fc  mov     eax, [rsi+30h]
0x1800016ff  lea     rdi, [rbp+10D0h+var_840]
0x180001706  dec     eax; switch 128 cases
0x180001708  cmp     eax, 7Fh
0x18000170b  ja      def_18000172C; jumptable 000000018000172C default case, cases 3,5-7,9-15,17-127
0x180001711  lea     r9, cs:180000000h
0x180001718  movzx   eax, ds:(byte_180001E90 - 180000000h)[r9+rax]
0x180001721  mov     ecx, ds:(jpt_18000172C - 180000000h)[r9+rax*4]
0x180001729  add     rcx, r9
0x18000172c  jmp     rcx; switch jump
0x18000172e  mov     rax, [rsi+28h]; jumptable 000000018000172C case 2
0x180001732  mov     ecx, [rsi+38h]
0x180001735  mov     r9d, [rsi+34h]
0x180001739  mov     r10d, [rsi+8]
0x18000173d  mov     r11d, [rsi+10h]
0x180001741  test    r8, r8
0x180001744  jz      loc_1800018F7
0x18000174a  test    rax, rax
0x18000174d  jz      loc_1800017F0
0x180001753  mov     [rsp+11D0h+var_1170], rdx
0x180001758  mov     [rsp+11D0h+var_1178], rax
0x18000175d  mov     rax, qword ptr [rsp+11D0h+NumberOfBytesWritten]
0x180001762  mov     [rsp+11D0h+var_1180], rax
0x180001767  mov     dword ptr [rsp+11D0h+var_1188], ecx
0x18000176b  mov     dword ptr [rsp+11D0h+var_1190], r9d
0x180001770  mov     r9, r8
0x180001773  lea     r8, aHsLuLuLuLuXLuS_2; "%hs(%lu) : %lu.%lu %lu %X %lu [%s] WIA:"...
0x18000177a  jmp     loc_1800018C9
0x18000177f  mov     rax, [rsi+28h]; jumptable 000000018000172C cases 1,128
0x180001783  mov     ecx, [rsi+38h]
0x180001786  mov     r9d, [rsi+34h]
0x18000178a  mov     r10d, [rsi+8]
0x18000178e  mov     r11d, [rsi+10h]
0x180001792  test    r8, r8
0x180001795  jz      loc_180001840
0x18000179b  test    rax, rax
0x18000179e  jz      short loc_1800017CC
0x1800017a0  mov     [rsp+11D0h+var_1170], rdx
0x1800017a5  mov     [rsp+11D0h+var_1178], rax
0x1800017aa  mov     rax, qword ptr [rsp+11D0h+NumberOfBytesWritten]
0x1800017af  mov     [rsp+11D0h+var_1180], rax
0x1800017b4  mov     dword ptr [rsp+11D0h+var_1188], ecx
0x1800017b8  mov     dword ptr [rsp+11D0h+var_1190], r9d
0x1800017bd  mov     r9, r8
0x1800017c0  lea     r8, aHsLuLuLuLuXLuS_0; "%hs(%lu) : %lu.%lu %lu %X %lu [%s] WIA:"...
0x1800017c7  jmp     loc_1800018C9
0x1800017cc  mov     rax, qword ptr [rsp+11D0h+NumberOfBytesWritten]
0x1800017d1  mov     [rsp+11D0h+var_1178], rdx
0x1800017d6  mov     [rsp+11D0h+var_1180], rax
0x1800017db  mov     dword ptr [rsp+11D0h+var_1188], ecx
0x1800017df  mov     dword ptr [rsp+11D0h+var_1190], r9d
0x1800017e4  mov     r9, r8
0x1800017e7  lea     r8, aHsLuLuLuLuXLuS_3; "%hs(%lu) : %lu.%lu %lu %X %lu [%s] WIA:"...
0x1800017ee  jmp     short loc_180001812
0x1800017f0  mov     rax, qword ptr [rsp+11D0h+NumberOfBytesWritten]
0x1800017f5  mov     [rsp+11D0h+var_1178], rdx
0x1800017fa  mov     [rsp+11D0h+var_1180], rax
0x1800017ff  mov     dword ptr [rsp+11D0h+var_1188], ecx
0x180001803  mov     dword ptr [rsp+11D0h+var_1190], r9d
0x180001808  mov     r9, r8
0x18000180b  lea     r8, aHsLuLuLuLuXLuS_1; "%hs(%lu) : %lu.%lu %lu %X %lu [%s] WIA:"...
0x180001812  mov     eax, [rsi+0Ch]
0x180001815  lea     rcx, [rbp+10D0h+var_840]; char *
0x18000181c  mov     [rsp+11D0h+var_1198], r10d
0x180001821  mov     edx, 800h; unsigned __int64
0x180001826  mov     [rsp+11D0h+var_11A0], r11d
0x18000182b  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x18000182f  mov     eax, [rsi+20h]
0x180001832  mov     dword ptr [rsp+11D0h+lpOverlapped], eax
0x180001836  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18000183b  jmp     loc_1800019D3
0x180001840  test    rax, rax
0x180001843  jz      short loc_180001851
0x180001845  lea     r8, aWiaLuLuLuXLuSE_0; "WIA: %lu.%lu %lu %X %lu [%s] ERROR: %s,"...
0x18000184c  jmp     loc_180001997
0x180001851  lea     r8, aWiaLuLuLuXLuSE; "WIA: %lu.%lu %lu %X %lu [%s] ERROR: %s"...
0x180001858  jmp     short loc_180001861
0x18000185a  lea     r8, aWiaLuLuLuXLuSS; "WIA: %lu.%lu %lu %X %lu [%s] %s\r\n"
0x180001861  mov     rax, qword ptr [rsp+11D0h+NumberOfBytesWritten]
0x180001866  mov     [rsp+11D0h+var_1188], rdx
  ... truncated ...
```
