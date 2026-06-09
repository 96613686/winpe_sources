# SxspCreateAssemblyIdentity(ulong,ulong,_ASSEMBLY_IDENTITY * *,ulong,_INTERNAL_ASSEMBLY_IDENTITY_ATTRIBUTE const * const *)

- ea: `0x180011170`
- end: `0x180011573`
- name: `?SxspCreateAssemblyIdentity@@YAHKKPEAPEAU_ASSEMBLY_IDENTITY@@KPEBQEBU_INTERNAL_ASSEMBLY_IDENTITY_ATTRIBUTE@@@Z`
- size: `1027`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, struct _ASSEMBLY_IDENTITY **, unsigned int, const struct _INTERNAL_ASSEMBLY_IDENTITY_ATTRIBUTE *const *)`
- caller_count: `4`
- callee_count: `13`
- tags: `file_ops, loader_planting`

## callers

- `0x18000f170`
- `0x180010bd0`
- `0x180010e20`
- `0x180021150`

## callees

- `0x18000dffc`
- `0x180011170`
- `0x180011580`
- `0x18001be10`
- `0x18001c2c8`
- `0x180022f60`
- `0x18004cda0`
- `0x18005d2e4`
- `0x180067548`
- `0x180067680`
- `0x180069c88`
- `0x18006a0f5`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x1800112cd`
- `ntdll!RtlPopFrame` at `0x1800112cd`
- `ntdll!RtlPushFrame` at `0x1800111ef`
- `ntdll!RtlPushFrame` at `0x1800111ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011559`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011559`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001127d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011343`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011451`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011476`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001127d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011343`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011451`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011476`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800112fb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800112fb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800113ff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800113ff`

## pseudocode

```c
__int64 __fastcall SxspCreateAssemblyIdentity(
        int a1,
        int a2,
        struct _ASSEMBLY_IDENTITY **a3,
        unsigned int a4,
        const struct _INTERNAL_ASSEMBLY_IDENTITY_ATTRIBUTE *const *a5)
{
  unsigned int v9; // edi
  unsigned __int64 v10; // rax
  DWORD v11; // ecx
  unsigned int v12; // ebx
  _DWORD *v14; // rax
  const char *v15; // rcx
  _DWORD *v16; // r15
  char *v17; // r13
  __int64 i; // rbx
  struct _ASSEMBLY_IDENTITY_NAMESPACE *v19; // rdi
  __int64 v20; // rsi
  const struct _INTERNAL_ASSEMBLY_IDENTITY_ATTRIBUTE *v21; // rax
  bool v22; // zf
  char **v23; // rcx
  struct _ASSEMBLY_IDENTITY_NAMESPACE **v24; // rbx
  __int64 v25; // rbx
  unsigned int v26; // esi
  __int64 v27; // rdi
  DWORD LastError; // eax
  unsigned int v29; // [rsp+48h] [rbp-51h]
  unsigned int v30; // [rsp+4Ch] [rbp-4Dh] BYREF
  unsigned int v31; // [rsp+50h] [rbp-49h] BYREF
  int v32; // [rsp+54h] [rbp-45h]
  int v33; // [rsp+58h] [rbp-41h]
  struct _ASSEMBLY_IDENTITY_NAMESPACE **v34; // [rsp+60h] [rbp-39h] BYREF
  struct _ASSEMBLY_IDENTITY **v35; // [rsp+68h] [rbp-31h]
  int v36; // [rsp+70h] [rbp-29h] BYREF
  struct _ASSEMBLY_IDENTITY_NAMESPACE *v37; // [rsp+78h] [rbp-21h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+80h] [rbp-19h] BYREF
  __int64 v39; // [rsp+98h] [rbp-1h]
  int v40; // [rsp+A0h] [rbp+7h]
  int *v41; // [rsp+A8h] [rbp+Fh]

  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006CA00;
  v36 = 0;
  Frame.Previous = 0;
  v35 = a3;
  v32 = a2;
  Frame.Flags = 1;
  v39 = 544438355;
  v40 = 1329;
  v41 = &v36;
  RtlPushFrame(&Frame);
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallEntry();
  v34 = 0;
  v31 = 0;
  v30 = 0;
  if ( a3 )
    *a3 = 0;
  if ( (a1 & 0xFFFFFFFE) != 0 || (unsigned int)(a2 - 1) > 2 || a4 && !a5 )
  {
    v11 = 87;
    goto LABEL_13;
  }
  v33 = a1 & 1;
  if ( (a1 & 1) != 0 )
    v9 = a4;
  else
    v9 = (a4 + 8) & 0xFFFFFFF8;
  v10 = 8LL * v9;
  v29 = v9;
  v37 = 0;
  if ( !is_mul_ok(v9, 8u) || v10 >= 0xFFFFFFFFFFFFFFC8uLL )
  {
    v11 = 534;
LABEL_13:
    SetLastError(v11);
    goto LABEL_14;
  }
  v14 = HeapAlloc(g_hHeap, 0, v10 + 56);
  v16 = v14;
  if ( v14 )
  {
    v17 = 0;
    if ( v9 )
    {
      v17 = (char *)(v14 + 14);
      memset_0(v14 + 14, 0, 8LL * v9);
    }
    for ( i = 0; (unsigned int)i < a4; i = (unsigned int)(i + 1) )
    {
      v19 = 0;
      v20 = i;
      v21 = a5[i];
      v37 = 0;
      if ( *((_QWORD *)v21 + 1) )
      {
        SetLastError(0);
        if ( !(unsigned int)SxspFindAssemblyIdentityNamespaceInArray(
                              1u,
                              &v34,
                              &v31,
                              &v30,
                              *((const unsigned __int16 **)a5[v20] + 4),
                              *((_QWORD *)a5[v20] + 1),
                              &v37) )
        {
          v23 = off_18007CEE0;
          *v41 = 0;
LABEL_28:
          FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v23);
          if ( v17 && a4 )
          {
            v25 = 0;
            do
            {
              if ( (unsigned int)v25 >= v29 )
                break;
              SxspDeallocateInternalAssemblyIdentityAttribute(*(struct _INTERNAL_ASSEMBLY_IDENTITY_ATTRIBUTE **)&v17[8 * v25]);
              v25 = (unsigned int)(v25 + 1);
            }
            while ( (unsigned int)v25 < a4 );
          }
          v24 = v34;
          if ( v34 )
          {
            v26 = v30;
            if ( v30 )
            {
              v27 = 0;
              do
              {
                SxspDeallocateAssemblyIdentityNamespace(v24[v27]);
                v27 = (unsigned int)(v27 + 1);
              }
              while ( (unsigned int)v27 < v26 );
              operator delete(v24);
            }
          }
          HeapFree(g_hHeap, 0, v16);
          goto LABEL_14;
        }
        v19 = v37;
      }
      SetLastError(0);
      if ( !(unsigned int)SxspDuplicateInternalAssemblyIdentityAttribute(
                            v19,
                            a5[v20],
                            (const struct _INTERNAL_ASSEMBLY_IDENTITY_ATTRIBUTE **)&v17[v20 * 8]) )
      {
        v23 = off_18006CD60;
        *v41 = 0;
        goto LABEL_28;
      }
    }
    v22 = v33 == 0;
    v16[7] = v31;
    v16[6] = v30;
    *((_QWORD *)v16 + 6) = v34;
    v16[2] = v32;
    v16[5] = v29;
    v16[4] = a4;
    *((_QWORD *)v16 + 5) = v17;
    *v16 = 0;
    v16[1] = 4;
    v16[8] = 1;
    if ( !v22 )
      *v16 = 0x80000000;
    v36 = 1;
    *v35 = (struct _ASSEMBLY_IDENTITY *)v16;
  }
  else
  {
    FusionpTraceAllocFailure(v15);
    SetLastError(0xEu);
    *v41 = 0;
  }
LABEL_14:
  v12 = v36;
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( *v41 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      LastError = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(LastError, 0);
    }
  }
  RtlPopFrame(&Frame);
  return v12;
}

```

## disassembly

```asm
0x180011170  mov     r11, rsp
0x180011173  push    rbp
0x180011174  push    rbx
0x180011175  lea     rbp, [r11-57h]
0x180011179  sub     rsp, 0D8h
0x180011180  mov     rax, cs:__security_cookie
0x180011187  xor     rax, rsp
0x18001118a  mov     [rbp+4Fh+var_38], rax
0x18001118e  mov     [r11+8], rsi
0x180011192  lea     rax, qword_18006CA00
0x180011199  mov     [r11-18h], rdi
0x18001119d  mov     rbx, r8
0x1800111a0  mov     [r11-20h], r12
0x1800111a4  mov     esi, ecx
0x1800111a6  mov     r12, [rbp+4Fh+arg_20]
0x1800111aa  lea     rcx, [rbp+4Fh+Frame]; Frame
0x1800111ae  mov     [r11-30h], r14
0x1800111b2  mov     edi, edx
0x1800111b4  mov     [r11-38h], r15
0x1800111b8  mov     r14d, r9d
0x1800111bb  mov     [rbp+4Fh+Frame.Context], rax
0x1800111bf  xor     r15d, r15d
0x1800111c2  lea     rax, [rbp+4Fh+var_78]
0x1800111c6  mov     [rbp+4Fh+var_78], r15d
0x1800111ca  mov     [rbp+4Fh+Frame.Previous], r15
0x1800111ce  mov     [rbp+4Fh+var_80], rbx
0x1800111d2  mov     [rbp+4Fh+var_94], edx
0x1800111d5  mov     [rbp+4Fh+Frame.Flags], 1
0x1800111dc  mov     [rbp+4Fh+var_50], 20737853h
0x1800111e4  mov     [rbp+4Fh+var_48], 531h
0x1800111eb  mov     [rbp+4Fh+var_40], rax
0x1800111ef  call    cs:__imp_RtlPushFrame
0x1800111f6  nop     dword ptr [rax+rax+00h]
0x1800111fb  cmp     cs:g_FusionEnterExitTracingEnabled, r15b
0x180011202  jnz     loc_18001143D
0x180011208  mov     [rbp+4Fh+var_88], r15
0x18001120c  mov     [rbp+4Fh+var_98], r15d
0x180011210  mov     [rbp+4Fh+var_9C], r15d
0x180011214  test    rbx, rbx
0x180011217  jz      short loc_18001121C
0x180011219  mov     [rbx], r15
0x18001121c  mov     [rsp+0E0h+var_20], r13
0x180011224  test    esi, 0FFFFFFFEh
0x18001122a  jnz     loc_180011419
0x180011230  lea     eax, [rdi-1]
0x180011233  cmp     eax, 2
0x180011236  ja      loc_180011419
0x18001123c  test    r14d, r14d
0x18001123f  jnz     loc_180011410
0x180011245  and     esi, 1
0x180011248  mov     [rbp+4Fh+var_90], esi
0x18001124b  jnz     loc_18001146C
0x180011251  lea     edi, [r14+8]
0x180011255  and     edi, 0FFFFFFF8h
0x180011258  mov     ebx, edi
0x18001125a  mov     eax, 8
0x18001125f  mul     rbx
0x180011262  mov     [rbp+4Fh+var_A0], edi
0x180011265  mov     [rbp+4Fh+var_70], r15
0x180011269  test    rdx, rdx
0x18001126c  jnz     short loc_180011278
0x18001126e  lea     r8, [rax+38h]; dwBytes
0x180011272  cmp     r8, 38h ; '8'
0x180011276  jnb     short loc_1800112F2
0x180011278  mov     ecx, 216h; dwErrCode
0x18001127d  call    cs:__imp_SetLastError
0x180011284  nop     dword ptr [rax+rax+00h]
0x180011289  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x180011290  mov     ebx, [rbp+4Fh+var_78]
0x180011293  mov     r15, [rsp+0E0h+var_30]
0x18001129b  mov     r14, [rsp+0E0h+var_28]
0x1800112a3  mov     r13, [rsp+0E0h+var_20]
0x1800112ab  mov     r12, [rsp+0E0h+var_18]
0x1800112b3  mov     rdi, [rsp+0D0h]
0x1800112bb  mov     rsi, [rsp+0E0h+arg_0]
0x1800112c3  jnz     loc_180011544
0x1800112c9  lea     rcx, [rbp+4Fh+Frame]; Frame
0x1800112cd  call    cs:__imp_RtlPopFrame
0x1800112d4  nop     dword ptr [rax+rax+00h]
0x1800112d9  mov     eax, ebx
0x1800112db  mov     rcx, [rbp+4Fh+var_38]
0x1800112df  xor     rcx, rsp; StackCookie
0x1800112e2  call    __security_check_cookie
0x1800112e7  add     rsp, 0D8h
0x1800112ee  pop     rbx
0x1800112ef  pop     rbp
0x1800112f0  retn
0x1800112f2  mov     rcx, cs:g_hHeap; hHeap
0x1800112f9  xor     edx, edx; dwFlags
0x1800112fb  call    cs:__imp_HeapAlloc
0x180011302  nop     dword ptr [rax+rax+00h]
0x180011307  mov     r15, rax
0x18001130a  test    rax, rax
0x18001130d  jz      loc_180011447
0x180011313  xor     r13d, r13d
0x180011316  test    edi, edi
0x180011318  jnz     loc_180011423
0x18001131e  xor     ebx, ebx
0x180011320  cmp     ebx, r14d
0x180011323  jnb     short loc_180011367
0x180011325  xor     edi, edi
0x180011327  lea     rsi, ds:0[rbx*8]
0x18001132f  mov     rax, [rsi+r12]
0x180011333  mov     [rbp+4Fh+var_70], rdi
0x180011337  cmp     [rax+8], rdi
0x18001133b  jnz     loc_180011474
0x180011341  xor     ecx, ecx; dwErrCode
0x180011343  call    cs:__imp_SetLastError
0x18001134a  nop     dword ptr [rax+rax+00h]
0x18001134f  mov     rdx, [rsi+r12]; struct _INTERNAL_ASSEMBLY_IDENTITY_ATTRIBUTE *
0x180011353  lea     r8, [rsi+r13]; struct _INTERNAL_ASSEMBLY_IDENTITY_ATTRIBUTE **
0x180011357  mov     rcx, rdi; struct _ASSEMBLY_IDENTITY_NAMESPACE *
0x18001135a  call    ?SxspDuplicateInternalAssemblyIdentityAttribute@@YAHPEBU_ASSEMBLY_IDENTITY_NAMESPACE@@PEAU_INTERNAL_ASSEMBLY_IDENTITY_ATTRIBUTE@@PEAPEBU2@@Z; SxspDuplicateInternalAssemblyIdentityAttribute(_ASSEMBLY_IDENTITY_NAMESPACE const *,_INTERNAL_ASSEMBLY_IDENTITY_ATTRIBUTE *,_INTERNAL_ASSEMBLY_IDENTITY_ATTRIBUTE const * *)
0x18001135f  test    eax, eax
0x180011361  jz      short loc_1800113C7
0x180011363  inc     ebx
0x180011365  jmp     short loc_180011320
0x180011367  cmp     [rbp+4Fh+var_90], 0
0x18001136b  mov     eax, [rbp+4Fh+var_98]
0x18001136e  mov     edi, [rbp+4Fh+var_A0]
0x180011371  mov     [r15+1Ch], eax
0x180011375  mov     eax, [rbp+4Fh+var_9C]
0x180011378  mov     [r15+18h], eax
0x18001137c  mov     rax, [rbp+4Fh+var_88]
0x180011380  mov     [r15+30h], rax
0x180011384  mov     eax, [rbp+4Fh+var_94]
0x180011387  mov     [r15+8], eax
0x18001138b  mov     [r15+14h], edi
0x18001138f  mov     [r15+10h], r14d
0x180011393  mov     [r15+28h], r13
0x180011397  mov     dword ptr [r15], 0
0x18001139e  mov     dword ptr [r15+4], 4
0x1800113a6  mov     dword ptr [r15+20h], 1
0x1800113ae  jnz     loc_180011538
0x1800113b4  mov     rax, [rbp+4Fh+var_80]
0x1800113b8  mov     [rbp+4Fh+var_78], 1
0x1800113bf  mov     [rax], r15
0x1800113c2  jmp     loc_180011289
0x1800113c7  mov     rax, [rbp+4Fh+var_40]
0x1800113cb  lea     rcx, off_18006CD60; struct _CALL_SITE_INFO *
0x1800113d2  mov     dword ptr [rax], 0
0x1800113d8  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x1800113dd  test    r13, r13
0x1800113e0  jnz     loc_1800114D6
0x1800113e6  mov     rbx, [rbp+4Fh+var_88]
0x1800113ea  test    rbx, rbx
0x1800113ed  jnz     loc_18001150B
0x1800113f3  mov     rcx, cs:g_hHeap; hHeap
0x1800113fa  mov     r8, r15; lpMem
0x1800113fd  xor     edx, edx; dwFlags
0x1800113ff  call    cs:__imp_HeapFree
0x180011406  nop     dword ptr [rax+rax+00h]
0x18001140b  jmp     loc_180011289
0x180011410  test    r12, r12
0x180011413  jnz     loc_180011245
0x180011419  mov     ecx, 57h ; 'W'
0x18001141e  jmp     loc_18001127D
0x180011423  lea     r13, [rax+38h]
0x180011427  shl     rbx, 3
0x18001142b  mov     r8, rbx; Size
0x18001142e  mov     rcx, r13; void *
0x180011431  xor     edx, edx; Val
0x180011433  call    memset_0
0x180011438  jmp     loc_18001131E
0x18001143d  call    ?FusionpTraceCallEntry@@YAXXZ; FusionpTraceCallEntry(void)
0x180011442  jmp     loc_180011208
0x180011447  call    ?FusionpTraceAllocFailure@@YAXPEBD@Z; FusionpTraceAllocFailure(char const *)
0x18001144c  mov     ecx, 0Eh; dwErrCode
0x180011451  call    cs:__imp_SetLastError
0x180011458  nop     dword ptr [rax+rax+00h]
0x18001145d  mov     rax, [rbp+4Fh+var_40]
0x180011461  mov     dword ptr [rax], 0
0x180011467  jmp     loc_180011289
0x18001146c  mov     edi, r14d
0x18001146f  jmp     loc_180011258
0x180011474  xor     ecx, ecx; dwErrCode
0x180011476  call    cs:__imp_SetLastError
0x18001147d  nop     dword ptr [rax+rax+00h]
0x180011482  mov     rcx, [rsi+r12]
0x180011486  lea     rax, [rbp+4Fh+var_70]
0x18001148a  mov     [rsp+30h], rax; struct _ASSEMBLY_IDENTITY_NAMESPACE **
0x18001148f  lea     r9, [rbp+4Fh+var_9C]; unsigned int *
0x180011493  lea     r8, [rbp+4Fh+var_98]; unsigned int *
0x180011497  lea     rdx, [rbp+4Fh+var_88]; struct _ASSEMBLY_IDENTITY_NAMESPACE ***
0x18001149b  mov     rax, [rcx+8]
0x18001149f  mov     [rsp+0E0h+var_B8], rax; unsigned __int64
0x1800114a4  mov     rax, [rcx+20h]
0x1800114a8  mov     ecx, 1; unsigned int
0x1800114ad  mov     [rsp+0E0h+var_C0], rax; unsigned __int16 *
0x1800114b2  call    ?SxspFindAssemblyIdentityNamespaceInArray@@YAHKPEAPEAPEBU_ASSEMBLY_IDENTITY_NAMESPACE@@PEAK1PEBG_KPEAPEBU1@@Z; SxspFindAssemblyIdentityNamespaceInArray(ulong,_ASSEMBLY_IDENTITY_NAMESPACE const * * *,ulong *,ulong *,ushort const *,unsigned __int64,_ASSEMBLY_IDENTITY_NAMESPACE const * *)
0x1800114b7  test    eax, eax
0x1800114b9  jz      short loc_1800114C4
0x1800114bb  mov     rdi, [rbp+4Fh+var_70]
0x1800114bf  jmp     loc_180011341
0x1800114c4  mov     rax, [rbp+4Fh+var_40]
0x1800114c8  lea     rcx, off_18007CEE0; "clientcore\\base\\win32\\fusion\\id\\id"...
0x1800114cf  mov     [rax], edi
0x1800114d1  jmp     loc_1800113D8
0x1800114d6  test    r14d, r14d
0x1800114d9  jz      loc_1800113E6
0x1800114df  xor     ebx, ebx
0x1800114e1  test    r14d, r14d
0x1800114e4  jz      loc_1800113E6
0x1800114ea  mov     edi, [rbp+4Fh+var_A0]
0x1800114ed  cmp     ebx, edi
0x1800114ef  jnb     loc_1800113E6
0x1800114f5  mov     rcx, [r13+rbx*8+0]; struct _INTERNAL_ASSEMBLY_IDENTITY_ATTRIBUTE *
0x1800114fa  call    ?SxspDeallocateInternalAssemblyIdentityAttribute@@YAXPEAU_INTERNAL_ASSEMBLY_IDENTITY_ATTRIBUTE@@@Z; SxspDeallocateInternalAssemblyIdentityAttribute(_INTERNAL_ASSEMBLY_IDENTITY_ATTRIBUTE *)
0x1800114ff  inc     ebx
0x180011501  cmp     ebx, r14d
0x180011504  jb      short loc_1800114ED
0x180011506  jmp     loc_1800113E6
0x18001150b  mov     esi, [rbp+4Fh+var_9C]
0x18001150e  test    esi, esi
0x180011510  jz      loc_1800113F3
0x180011516  xor     edi, edi
0x180011518  test    esi, esi
0x18001151a  jz      short loc_18001152B
0x18001151c  mov     rcx, [rbx+rdi*8]; lpMem
0x180011520  call    ?SxspDeallocateAssemblyIdentityNamespace@@YAXPEBU_ASSEMBLY_IDENTITY_NAMESPACE@@@Z; SxspDeallocateAssemblyIdentityNamespace(_ASSEMBLY_IDENTITY_NAMESPACE const *)
0x180011525  inc     edi
0x180011527  cmp     edi, esi
0x180011529  jb      short loc_18001151C
0x18001152b  mov     rcx, rbx; void *
0x18001152e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011533  jmp     loc_1800113F3
0x180011538  mov     dword ptr [r15], 80000000h
0x18001153f  jmp     loc_1800113B4
0x180011544  mov     rax, [rbp+4Fh+var_40]
0x180011548  cmp     dword ptr [rax], 0
0x18001154b  jz      short loc_180011559
0x18001154d  xor     ecx, ecx; char *
0x18001154f  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x180011554  jmp     loc_1800112C9
0x180011559  call    cs:__imp_GetLastError
0x180011560  nop     dword ptr [rax+rax+00h]
0x180011565  mov     ecx, eax; unsigned int
0x180011567  xor     edx, edx; Format
0x180011569  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x18001156e  jmp     loc_1800112C9
```
