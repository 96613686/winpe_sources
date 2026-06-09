# CVssDiffMgmt::ChangeDiffAreaMaximumSize(ushort *,ushort *,__int64)

- ea: `0x1800287d0`
- end: `0x180028a92`
- name: `?ChangeDiffAreaMaximumSize@CVssDiffMgmt@@UEAAJPEAG0_J@Z`
- size: `706`
- prototype: `__int64 __fastcall(CVssDiffMgmt *__hidden this, unsigned __int16 *, unsigned __int16 *, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, installer_update`

## callees

- `0x180001674`
- `0x180001af0`
- `0x18000212c`
- `0x1800287d0`
- `0x180033a8c`
- `0x180033c78`
- `0x1800367b8`
- `0x18003da74`
- `0x18004b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180028914`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180028922`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180028914`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180028922`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180028902`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180028902`

## string_xrefs

- `0x18002880d`: `CVssDiffMgmt::ChangeDiffAreaMaximumSize`
- `0x180028976`: `CVssDiffMgmt::ChangeDiffAreaMaximumSize`
- `0x1800289e9`: `CVssDiffMgmt::ChangeDiffAreaMaximumSize`
- `0x1800289b1`: `An AMSI provider has determined that this is an unauthorized request`
- `0x180028a26`: `pAmsiBuffer allocation failed`

## pseudocode

```c
__int64 __fastcall CVssDiffMgmt::ChangeDiffAreaMaximumSize(
        CVssDiffMgmt *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        __int64 a4)
{
  CVssDiffMgmt *v6; // rdi
  __int64 v7; // rax
  __int64 v8; // rcx
  unsigned int v9; // r14d
  unsigned int v10; // ebx
  unsigned int v11; // esi
  char *v12; // r15
  int v13; // ebx
  unsigned int v14; // ebx
  __int64 v16; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *v17; // [rsp+38h] [rbp-C8h] BYREF
  const wchar_t *v18; // [rsp+40h] [rbp-C0h]
  const unsigned __int16 *v19; // [rsp+48h] [rbp-B8h]
  int v20; // [rsp+50h] [rbp-B0h]
  int v21; // [rsp+54h] [rbp-ACh]
  int v22; // [rsp+58h] [rbp-A8h]
  _BYTE v23[120]; // [rsp+60h] [rbp-A0h] BYREF
  int v24; // [rsp+D8h] [rbp-28h]
  LPVOID v25[20]; // [rsp+E0h] [rbp-20h] BYREF

  v20 = 380;
  v17 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
  v21 = 2;
  v18 = L"CVssDiffMgmt::ChangeDiffAreaMaximumSize";
  v22 = 255;
  v6 = this;
  v19 = L"SPRDIFMC";
  v24 = 0x1000000;
  memset_0(v23, 0, sizeof(v23));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v25, (__int64)&v17, 0);
  v16 = qword_18006B4B0;
  if ( !qword_18006B4B0 )
    goto LABEL_13;
  if ( !*(_BYTE *)(qword_18006B4B0 + 16) )
    goto LABEL_13;
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( a3[v8] );
  do
    ++v7;
  while ( a2[v7] );
  v9 = v7 + v8 + 2;
  v10 = 2 * v9;
  if ( 2 * v9 <= v9 )
    goto LABEL_13;
  v11 = v10 + 40;
  if ( v10 + 40 < v10 )
    goto LABEL_13;
  v12 = (char *)operator new[](v11, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v12 )
  {
    v20 = 420;
    v17 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
    v21 = 2;
    v18 = L"CVssDiffMgmt::ChangeDiffAreaMaximumSize";
    v22 = 255;
    v19 = L"SPRDIFMC";
    v24 = 0x1000000;
    memset_0(v23, 0, sizeof(v23));
    CVssFunctionTracer::Trace(v25, &v17, L"pAmsiBuffer allocation failed");
LABEL_13:
    v14 = (*(__int64 (__fastcall **)(CVssDiffMgmt *, unsigned __int16 *, unsigned __int16 *, __int64, _DWORD))(*(_QWORD *)v6 + 72LL))(
            v6,
            a2,
            a3,
            a4,
            0);
    goto LABEL_14;
  }
  *(_QWORD *)(v12 + 28) = a4;
  *((_DWORD *)v12 + 9) = v9;
  memset_0(v12 + 40, 0, v10);
  _o_wcscpy_s(v12 + 40, v10, a2);
  _o_wcscat_s(v12 + 40, v10, L";");
  _o_wcscat_s(v12 + 40, v10, a3);
  *(_WORD *)&v12[2 * v9 + 38] = 0;
  v13 = CVssAmsi::Scan(v16, v12, v11);
  operator delete(v12);
  if ( v13 < 0x8000 )
  {
    v6 = this;
    goto LABEL_13;
  }
  v20 = 414;
  v17 = L"base\\stor\\vss\\modules\\softprv\\src\\diffmgmt.cxx";
  v21 = 2;
  v18 = L"CVssDiffMgmt::ChangeDiffAreaMaximumSize";
  v22 = 255;
  v19 = L"SPRDIFMC";
  v24 = 0x1000000;
  memset_0(v23, 0, sizeof(v23));
  CVssFunctionTracer::Trace(v25, &v17, L"An AMSI provider has determined that this is an unauthorized request");
  v14 = -2147024891;
LABEL_14:
  CVssFunctionTracer::~CVssFunctionTracer(v25);
  return v14;
}

```

## disassembly

```asm
0x1800287d0  mov     [rsp-8+arg_8], rbx
0x1800287d5  mov     [rsp-8+arg_18], r9
0x1800287da  mov     [rsp-8+arg_0], rcx
0x1800287df  push    rbp
0x1800287e0  push    rsi
0x1800287e1  push    rdi
0x1800287e2  push    r12
0x1800287e4  push    r13
0x1800287e6  push    r14
0x1800287e8  push    r15
0x1800287ea  lea     rbp, [rsp-50h]
0x1800287ef  sub     rsp, 150h
0x1800287f6  lea     rax, aBaseStorVssMod_2; "base\\stor\\vss\\modules\\softprv\\src"...
0x1800287fd  mov     [rsp+180h+var_130], 17Ch
0x180028805  mov     [rsp+180h+var_148], rax
0x18002880a  mov     r12, r8
0x18002880d  lea     rax, aCvssdiffmgmtCh; "CVssDiffMgmt::ChangeDiffAreaMaximumSize"
0x180028814  mov     [rsp+180h+var_12C], 2
0x18002881c  mov     [rsp+180h+var_140], rax
0x180028821  mov     r13, rdx
0x180028824  lea     rax, aSprdifmc; "SPRDIFMC"
0x18002882b  mov     [rsp+180h+var_128], 0FFh
0x180028833  mov     rdi, rcx
0x180028836  mov     [rsp+180h+var_138], rax
0x18002883b  xor     r14d, r14d
0x18002883e  mov     [rbp+80h+var_A8], 1000000h
0x180028845  xor     edx, edx; Val
0x180028847  lea     rcx, [rsp+180h+var_120]; void *
0x18002884c  lea     r8d, [r14+78h]; Size
0x180028850  call    memset_0
0x180028855  xor     r8d, r8d
0x180028858  lea     rdx, [rsp+180h+var_148]
0x18002885d  lea     rcx, [rbp+80h+var_A0]
0x180028861  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x180028866  mov     rax, cs:qword_18006B4B0
0x18002886d  mov     [rsp+180h+var_150], rax
0x180028872  test    rax, rax
0x180028875  jz      loc_180028A49
0x18002887b  cmp     [rax+10h], r14b
0x18002887f  jz      loc_180028A49
0x180028885  or      rax, 0FFFFFFFFFFFFFFFFh
0x180028889  mov     rcx, rax
0x18002888c  inc     rcx
0x18002888f  cmp     [r12+rcx*2], r14w
0x180028894  jnz     short loc_18002888C
0x180028896  inc     rax
0x180028899  cmp     [r13+rax*2+0], r14w
0x18002889f  jnz     short loc_180028896
0x1800288a1  lea     r14d, [rcx+2]
0x1800288a5  add     r14d, eax
0x1800288a8  lea     ebx, [r14+r14]
0x1800288ac  cmp     ebx, r14d
0x1800288af  jbe     loc_180028A46
0x1800288b5  lea     esi, [rbx+28h]
0x1800288b8  cmp     esi, ebx
0x1800288ba  jbe     loc_180028A46
0x1800288c0  mov     ecx, esi; unsigned __int64
0x1800288c2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800288c9  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800288ce  mov     r15, rax
0x1800288d1  test    rax, rax
0x1800288d4  jz      loc_1800289D0
0x1800288da  mov     rax, [rbp+80h+arg_18]
0x1800288e1  lea     rdi, [r15+28h]
0x1800288e5  mov     rcx, rdi; void *
0x1800288e8  mov     [r15+1Ch], rax
0x1800288ec  mov     r8d, ebx; Size
0x1800288ef  mov     [r15+24h], r14d
0x1800288f3  xor     edx, edx; Val
0x1800288f5  call    memset_0
0x1800288fa  mov     r8, r13
0x1800288fd  mov     edx, ebx
0x1800288ff  mov     rcx, rdi
0x180028902  call    cs:__imp__o_wcscpy_s
0x180028908  lea     r8, asc_18005A640; ";"
0x18002890f  mov     edx, ebx
0x180028911  mov     rcx, rdi
0x180028914  call    cs:__imp__o_wcscat_s
0x18002891a  mov     r8, r12
0x18002891d  mov     edx, ebx
0x18002891f  mov     rcx, rdi
0x180028922  call    cs:__imp__o_wcscat_s
0x180028928  mov     rcx, [rsp+180h+var_150]
0x18002892d  lea     eax, [r14-1]
0x180028931  xor     r14d, r14d
0x180028934  mov     r8d, esi
0x180028937  mov     rdx, r15
0x18002893a  mov     [rdi+rax*2], r14w
0x18002893f  call    ?Scan@CVssAmsi@@QEAA?AW4AMSI_RESULT@@PEAXKW4_VSS_AMSI_TYPE@@@Z; CVssAmsi::Scan(void *,ulong,_VSS_AMSI_TYPE)
0x180028944  lea     edx, [r14+2Ah]
0x180028948  mov     rcx, r15; Block
0x18002894b  mov     ebx, eax
0x18002894d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180028952  cmp     ebx, 8000h
0x180028958  jl      loc_180028A3D
0x18002895e  lea     rax, aBaseStorVssMod_2; "base\\stor\\vss\\modules\\softprv\\src"...
0x180028965  mov     [rsp+180h+var_130], 19Eh
0x18002896d  mov     [rsp+180h+var_148], rax
0x180028972  lea     r8d, [r14+78h]; Size
0x180028976  lea     rax, aCvssdiffmgmtCh; "CVssDiffMgmt::ChangeDiffAreaMaximumSize"
0x18002897d  mov     [rsp+180h+var_12C], 2
0x180028985  mov     [rsp+180h+var_140], rax
0x18002898a  lea     rcx, [rsp+180h+var_120]; void *
0x18002898f  lea     rax, aSprdifmc; "SPRDIFMC"
0x180028996  mov     [rsp+180h+var_128], 0FFh
0x18002899e  xor     edx, edx; Val
0x1800289a0  mov     [rsp+180h+var_138], rax
0x1800289a5  mov     [rbp+80h+var_A8], 1000000h
0x1800289ac  call    memset_0
0x1800289b1  lea     r8, aAnAmsiProvider; "An AMSI provider has determined that th"...
0x1800289b8  lea     rdx, [rsp+180h+var_148]
0x1800289bd  lea     rcx, [rbp+80h+var_A0]
0x1800289c1  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1800289c6  mov     ebx, 80070005h
0x1800289cb  jmp     loc_180028A6C
0x1800289d0  lea     rax, aBaseStorVssMod_2; "base\\stor\\vss\\modules\\softprv\\src"...
0x1800289d7  mov     [rsp+180h+var_130], 1A4h
0x1800289df  mov     [rsp+180h+var_148], rax
0x1800289e4  lea     rcx, [rsp+180h+var_120]; void *
0x1800289e9  lea     rax, aCvssdiffmgmtCh; "CVssDiffMgmt::ChangeDiffAreaMaximumSize"
0x1800289f0  mov     [rsp+180h+var_12C], 2
0x1800289f8  mov     [rsp+180h+var_140], rax
0x1800289fd  xor     r14d, r14d
0x180028a00  lea     rax, aSprdifmc; "SPRDIFMC"
0x180028a07  mov     [rsp+180h+var_128], 0FFh
0x180028a0f  xor     edx, edx; Val
0x180028a11  mov     [rsp+180h+var_138], rax
0x180028a16  mov     [rbp+80h+var_A8], 1000000h
0x180028a1d  lea     r8d, [r14+78h]; Size
0x180028a21  call    memset_0
0x180028a26  lea     r8, aPamsibufferAll; "pAmsiBuffer allocation failed"
0x180028a2d  lea     rdx, [rsp+180h+var_148]
0x180028a32  lea     rcx, [rbp+80h+var_A0]
0x180028a36  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x180028a3b  jmp     short loc_180028A49
0x180028a3d  mov     rdi, [rbp+80h+arg_0]
0x180028a44  jmp     short loc_180028A49
0x180028a46  xor     r14d, r14d
0x180028a49  mov     rax, [rdi]
0x180028a4c  mov     r8, r12
0x180028a4f  mov     r9, [rbp+80h+arg_18]
0x180028a56  mov     rdx, r13
0x180028a59  mov     rcx, rdi
0x180028a5c  mov     [rsp+180h+var_160], r14d
0x180028a61  mov     rax, [rax+48h]
0x180028a65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a6a  mov     ebx, eax
0x180028a6c  lea     rcx, [rbp+80h+var_A0]; this
0x180028a70  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x180028a75  mov     eax, ebx
0x180028a77  mov     rbx, [rsp+180h+arg_8]
0x180028a7f  add     rsp, 150h
0x180028a86  pop     r15
0x180028a88  pop     r14
0x180028a8a  pop     r13
0x180028a8c  pop     r12
0x180028a8e  pop     rdi
0x180028a8f  pop     rsi
0x180028a90  pop     rbp
0x180028a91  retn
```
