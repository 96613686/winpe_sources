# SxGetAllVolumeNames(ushort const *,ushort * * *,ulong *)

- ea: `0x18009130c`
- end: `0x180091670`
- name: `?SxGetAllVolumeNames@@YAJPEBGPEAPEAPEAGPEAK@Z`
- size: `868`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 ***, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x18004a340`

## callees

- `0x180008240`
- `0x1800145f4`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008ecfc`
- `0x18008ffb8`
- `0x180090064`
- `0x1800900d8`
- `0x18009057c`
- `0x180090c30`
- `0x18009130c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800914a2`
- `KERNEL32!GetLastError` at `0x1800914a2`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x180091494`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x180091494`
- `ole32!CoTaskMemFree` at `0x1800915cd`
- `ole32!CoTaskMemFree` at `0x1800915d6`
- `ole32!CoTaskMemFree` at `0x1800915f4`
- `ole32!CoTaskMemFree` at `0x180091621`
- `ole32!CoTaskMemFree` at `0x18009163a`
- `ole32!CoTaskMemFree` at `0x1800915cd`
- `ole32!CoTaskMemFree` at `0x1800915d6`
- `ole32!CoTaskMemFree` at `0x1800915f4`
- `ole32!CoTaskMemFree` at `0x180091621`
- `ole32!CoTaskMemFree` at `0x18009163a`
- `ole32!CoTaskMemRealloc` at `0x180091467`
- `ole32!CoTaskMemRealloc` at `0x180091467`

## pseudocode

```c
__int64 __fastcall SxGetAllVolumeNames(const unsigned __int16 *a1, unsigned __int16 ***a2, unsigned int *a3)
{
  void *v6; // r12
  void *v7; // rdi
  unsigned __int16 *v8; // rsi
  __int16 v9; // ax
  int AllVolumeGUIDNames; // eax
  bool v11; // sf
  const WCHAR *v12; // rbx
  DWORD v13; // eax
  signed int LastError; // eax
  const unsigned __int16 *i; // rbx
  int v16; // eax
  __int64 v17; // rax
  void *v18; // rcx
  unsigned __int16 **v19; // rax
  unsigned int j; // esi
  __int64 v21; // rbx
  LPVOID *v22; // rcx
  unsigned int k; // esi
  __int64 v24; // rbx
  unsigned int v25; // ebx
  unsigned __int16 *v27; // [rsp+30h] [rbp-48h] BYREF
  int v28; // [rsp+38h] [rbp-40h] BYREF
  __int16 v29; // [rsp+3Ch] [rbp-3Ch]
  __int16 v30; // [rsp+3Eh] [rbp-3Ah]
  DWORD cchReturnLength; // [rsp+C0h] [rbp+48h] BYREF
  unsigned int v32; // [rsp+C8h] [rbp+50h] BYREF
  LPVOID pv; // [rsp+D0h] [rbp+58h] BYREF
  void *Block; // [rsp+D8h] [rbp+60h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids, a1);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v28, "SxGetAllVolumeNames", 401, 1);
  cchReturnLength = 0;
  v6 = 0;
  Block = 0;
  v7 = 0;
  v27 = 0;
  v8 = 0;
  pv = 0;
  v32 = 0;
  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  v9 = 418;
  if ( !a1 || (v29 = 418, v9 = 419, !a2) || (v29 = 419, v9 = 420, !a3) )
  {
    v28 = -2147024809;
    goto LABEL_38;
  }
  v28 = 0;
  v29 = 420;
  v28 = CSxSimpleArray<unsigned short *>::CreateInstance(&Block);
  v9 = 422;
  if ( v28 < 0 )
  {
    v7 = Block;
LABEL_38:
    v30 = v9;
    goto LABEL_39;
  }
  v29 = 422;
  AllVolumeGUIDNames = SxGetAllVolumeGUIDNames(a1, (unsigned __int16 ***)&pv, &v32);
  v7 = Block;
  v11 = AllVolumeGUIDNames < 0;
  v28 = AllVolumeGUIDNames;
  v9 = 427;
  if ( v11 )
    goto LABEL_38;
  v29 = 427;
  v28 = CSxSimpleArray<unsigned short *>::Attach(Block, v32, &pv);
  v9 = 428;
  if ( v28 < 0 )
    goto LABEL_38;
  v29 = 428;
  v12 = (const WCHAR *)**((_QWORD **)v7 + 1);
  v13 = 261;
  for ( cchReturnLength = 261; ; v13 = cchReturnLength )
  {
    v6 = CoTaskMemRealloc(v6, 2LL * v13);
    v9 = 443;
    if ( !v6 )
    {
      v28 = -2147024882;
      goto LABEL_38;
    }
    v28 = 0;
    v29 = 443;
    if ( GetVolumePathNamesForVolumeNameW(v12, (LPWCH)v6, cchReturnLength, &cchReturnLength) )
      break;
    LastError = GetLastError();
    if ( LastError == 122 || LastError == 234 )
    {
      LastError = 0;
    }
    else if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
    }
    v28 = LastError;
    if ( LastError < 0 )
    {
      v30 = 453;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
        WPP_SF_sSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          (unsigned int)WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids,
          (unsigned int)"dwErr",
          (__int64)v12,
          LastError);
      goto LABEL_39;
    }
    v29 = 453;
  }
  for ( i = (const unsigned __int16 *)v6; *i; i += v17 + 1 )
  {
    v16 = SxCopyString(i, &v27);
    v8 = v27;
    v11 = v16 < 0;
    v28 = v16;
    v9 = 463;
    if ( v11 )
      goto LABEL_38;
    v29 = 463;
    v28 = CSxSimpleArray<unsigned short *>::Append(v7, v27);
    v9 = 464;
    if ( v28 < 0 )
      goto LABEL_38;
    v29 = 464;
    v8 = 0;
    v17 = -1;
    v27 = 0;
    do
      ++v17;
    while ( i[v17] );
  }
  v18 = v7;
  *a3 = *((_DWORD *)v7 + 4);
  v19 = (unsigned __int16 **)*((_QWORD *)v7 + 1);
  *((_QWORD *)v7 + 1) = 0;
  *((_QWORD *)v7 + 2) = 0;
  v7 = 0;
  *a2 = v19;
  CSxSimpleArray<unsigned short *>::Release(v18);
LABEL_39:
  CoTaskMemFree(v6);
  CoTaskMemFree(v8);
  if ( v7 )
  {
    for ( j = 0; j < *((_DWORD *)v7 + 4); *(_QWORD *)(*((_QWORD *)v7 + 1) + 8 * v21) = 0 )
    {
      v21 = j;
      CoTaskMemFree(*(LPVOID *)(*((_QWORD *)v7 + 1) + 8LL * j++));
    }
  }
  v22 = (LPVOID *)pv;
  if ( pv )
  {
    for ( k = 0; k < v32; v22 = (LPVOID *)pv )
    {
      v24 = k;
      CoTaskMemFree(v22[k++]);
      *((_QWORD *)pv + v24) = 0;
    }
    CoTaskMemFree(v22);
    pv = 0;
  }
  v25 = v28;
  if ( v7 )
    CSxSimpleArray<unsigned short *>::Release(v7);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v28);
  return v25;
}

```

## disassembly

```asm
0x18009130c  push    rbp
0x18009130e  push    rbx
0x18009130f  push    rsi
0x180091310  push    rdi
0x180091311  push    r12
0x180091313  push    r13
0x180091315  push    r14
0x180091317  push    r15
0x180091319  mov     rbp, rsp
0x18009131c  sub     rsp, 78h
0x180091320  mov     r14, r8
0x180091323  mov     r15, rdx
0x180091326  mov     rbx, rcx
0x180091329  mov     rcx, cs:WPP_GLOBAL_Control
0x180091330  lea     rax, WPP_GLOBAL_Control
0x180091337  cmp     rcx, rax
0x18009133a  jz      short loc_18009135D
0x18009133c  test    dword ptr [rcx+1Ch], 20000000h
0x180091343  jz      short loc_18009135D
0x180091345  mov     rcx, [rcx+10h]
0x180091349  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x180091350  mov     edx, 10h
0x180091355  mov     r9, rbx
0x180091358  call    WPP_SF_S
0x18009135d  mov     r9d, 1; unsigned __int16
0x180091363  lea     rdx, aSxgetallvolume_0; "SxGetAllVolumeNames"
0x18009136a  mov     r8d, 191h; unsigned __int16
0x180091370  lea     rcx, [rbp+var_40]; this
0x180091374  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180091379  xor     r13d, r13d
0x18009137c  mov     [rbp+cchReturnLength], r13d
0x180091380  mov     r12d, r13d
0x180091383  mov     [rbp+Block], r13
0x180091387  mov     edi, r13d
0x18009138a  mov     [rbp+var_48], r13
0x18009138e  mov     esi, r13d
0x180091391  mov     [rbp+pv], r13
0x180091395  mov     [rbp+arg_8], r13d
0x180091399  test    r15, r15
0x18009139c  jz      short loc_1800913A1
0x18009139e  mov     [r15], r13
0x1800913a1  test    r14, r14
0x1800913a4  jz      short loc_1800913A9
0x1800913a6  mov     [r14], r13d
0x1800913a9  mov     eax, 1A2h
0x1800913ae  test    rbx, rbx
0x1800913b1  jz      loc_1800915BF
0x1800913b7  mov     [rbp+var_3C], ax
0x1800913bb  mov     eax, 1A3h
0x1800913c0  test    r15, r15
0x1800913c3  jz      loc_1800915BF
0x1800913c9  mov     [rbp+var_3C], ax
0x1800913cd  mov     eax, 1A4h
0x1800913d2  test    r14, r14
0x1800913d5  jz      loc_1800915BF
0x1800913db  lea     rcx, [rbp+Block]
0x1800913df  mov     [rbp+var_40], r13d
0x1800913e3  mov     [rbp+var_3C], ax
0x1800913e7  call    ?CreateInstance@?$CSxSimpleArray@PEAG@@SAJPEAPEAV1@@Z; CSxSimpleArray<ushort *>::CreateInstance(CSxSimpleArray<ushort *> * *)
0x1800913ec  mov     [rbp+var_40], eax
0x1800913ef  test    eax, eax
0x1800913f1  mov     eax, 1A6h
0x1800913f6  jns     short loc_180091401
0x1800913f8  mov     rdi, [rbp+Block]
0x1800913fc  jmp     loc_1800915C6
0x180091401  lea     r8, [rbp+arg_8]; unsigned int *
0x180091405  mov     [rbp+var_3C], ax
0x180091409  lea     rdx, [rbp+pv]; unsigned __int16 ***
0x18009140d  mov     rcx, rbx; unsigned __int16 *
0x180091410  call    ?SxGetAllVolumeGUIDNames@@YAJPEBGPEAPEAPEAGPEAK@Z; SxGetAllVolumeGUIDNames(ushort const *,ushort * * *,ulong *)
0x180091415  mov     rdi, [rbp+Block]
0x180091419  test    eax, eax
0x18009141b  mov     [rbp+var_40], eax
0x18009141e  mov     eax, 1ABh
0x180091423  js      loc_1800915C6
0x180091429  mov     edx, [rbp+arg_8]
0x18009142c  lea     r8, [rbp+pv]
0x180091430  mov     rcx, rdi
0x180091433  mov     [rbp+var_3C], ax
0x180091437  call    ?Attach@?$CSxSimpleArray@PEAG@@QEAAJKPEAPEAPEAG@Z; CSxSimpleArray<ushort *>::Attach(ulong,ushort * * *)
0x18009143c  mov     [rbp+var_40], eax
0x18009143f  test    eax, eax
0x180091441  mov     eax, 1ACh
0x180091446  js      loc_1800915C6
0x18009144c  mov     [rbp+var_3C], ax
0x180091450  mov     rax, [rdi+8]
0x180091454  mov     rbx, [rax]
0x180091457  mov     eax, 105h
0x18009145c  mov     [rbp+cchReturnLength], eax
0x18009145f  mov     edx, eax
0x180091461  mov     rcx, r12; pv
0x180091464  add     rdx, rdx; cb
0x180091467  call    cs:__imp_CoTaskMemRealloc
0x18009146d  mov     r12, rax
0x180091470  test    rax, rax
0x180091473  mov     eax, 1BBh
0x180091478  jz      loc_1800915B6
0x18009147e  mov     r8d, [rbp+cchReturnLength]; cchBufferLength
0x180091482  lea     r9, [rbp+cchReturnLength]; lpcchReturnLength
0x180091486  mov     rdx, r12; lpszVolumePathNames
0x180091489  mov     [rbp+var_40], r13d
0x18009148d  mov     rcx, rbx; lpszVolumeName
0x180091490  mov     [rbp+var_3C], ax
0x180091494  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x18009149a  test    eax, eax
0x18009149c  jnz     loc_180091531
0x1800914a2  call    cs:__imp_GetLastError
0x1800914a8  cmp     eax, 7Ah ; 'z'
0x1800914ab  jz      short loc_1800914C2
0x1800914ad  cmp     eax, 0EAh
0x1800914b2  jz      short loc_1800914C2
0x1800914b4  test    eax, eax
0x1800914b6  jle     short loc_1800914C5
0x1800914b8  movzx   eax, ax
0x1800914bb  or      eax, 80070000h
0x1800914c0  jmp     short loc_1800914C5
0x1800914c2  mov     eax, r13d
0x1800914c5  mov     [rbp+var_40], eax
0x1800914c8  test    eax, eax
0x1800914ca  js      short loc_1800914DA
0x1800914cc  mov     eax, 1C5h
0x1800914d1  mov     [rbp+var_3C], ax
0x1800914d5  mov     eax, [rbp+cchReturnLength]
0x1800914d8  jmp     short loc_18009145F
0x1800914da  mov     ecx, 1C5h
0x1800914df  mov     [rbp+var_3A], cx
0x1800914e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800914ea  lea     rdx, WPP_GLOBAL_Control
0x1800914f1  cmp     rcx, rdx
0x1800914f4  jz      loc_1800915CA
0x1800914fa  test    dword ptr [rcx+1Ch], 2000000h
0x180091501  jz      loc_1800915CA
0x180091507  mov     rcx, [rcx+10h]
0x18009150b  lea     r9, aDwerr; "dwErr"
0x180091512  mov     [rsp+78h+var_50], eax
0x180091516  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x18009151d  mov     edx, 11h
0x180091522  mov     [rsp+78h+var_58], rbx
0x180091527  call    WPP_SF_sSd
0x18009152c  jmp     loc_1800915CA
0x180091531  mov     rbx, r12
0x180091534  cmp     [rbx], r13w
0x180091538  jz      short loc_180091594
0x18009153a  lea     rdx, [rbp+var_48]; unsigned __int16 **
0x18009153e  mov     rcx, rbx; Src
0x180091541  call    ?SxCopyString@@YAJPEBGPEAPEAG@Z; SxCopyString(ushort const *,ushort * *)
0x180091546  mov     rsi, [rbp+var_48]
0x18009154a  test    eax, eax
0x18009154c  mov     [rbp+var_40], eax
0x18009154f  mov     eax, 1CFh
0x180091554  js      short loc_1800915C6
0x180091556  mov     rdx, rsi
0x180091559  mov     [rbp+var_3C], ax
0x18009155d  mov     rcx, rdi
0x180091560  call    ?Append@?$CSxSimpleArray@PEAG@@QEAAJPEAG@Z; CSxSimpleArray<ushort *>::Append(ushort *)
0x180091565  mov     [rbp+var_40], eax
0x180091568  test    eax, eax
0x18009156a  mov     eax, 1D0h
0x18009156f  js      short loc_1800915C6
0x180091571  mov     [rbp+var_3C], ax
0x180091575  mov     rsi, r13
0x180091578  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009157c  mov     [rbp+var_48], r13
0x180091580  inc     rax
0x180091583  cmp     [rbx+rax*2], r13w
0x180091588  jnz     short loc_180091580
0x18009158a  lea     rbx, [rbx+rax*2]
0x18009158e  add     rbx, 2
0x180091592  jmp     short loc_180091534
0x180091594  mov     eax, [rdi+10h]
0x180091597  mov     rcx, rdi; Block
0x18009159a  mov     [r14], eax
0x18009159d  mov     rax, [rdi+8]
0x1800915a1  mov     [rdi+8], r13
0x1800915a5  mov     [rdi+10h], r13
0x1800915a9  mov     rdi, r13
0x1800915ac  mov     [r15], rax
0x1800915af  call    ?Release@?$CSxSimpleArray@PEAG@@QEAAKXZ; CSxSimpleArray<ushort *>::Release(void)
0x1800915b4  jmp     short loc_1800915CA
0x1800915b6  mov     [rbp+var_40], 8007000Eh
0x1800915bd  jmp     short loc_1800915C6
0x1800915bf  mov     [rbp+var_40], 80070057h
0x1800915c6  mov     [rbp+var_3A], ax
0x1800915ca  mov     rcx, r12; pv
0x1800915cd  call    cs:__imp_CoTaskMemFree
0x1800915d3  mov     rcx, rsi; pv
0x1800915d6  call    cs:__imp_CoTaskMemFree
0x1800915dc  test    rdi, rdi
0x1800915df  jz      short loc_180091609
0x1800915e1  mov     esi, r13d
0x1800915e4  cmp     [rdi+10h], r13d
0x1800915e8  jbe     short loc_180091609
0x1800915ea  mov     rcx, [rdi+8]
0x1800915ee  mov     ebx, esi
0x1800915f0  mov     rcx, [rcx+rbx*8]; pv
0x1800915f4  call    cs:__imp_CoTaskMemFree
0x1800915fa  mov     rax, [rdi+8]
0x1800915fe  inc     esi
0x180091600  mov     [rax+rbx*8], r13
0x180091604  cmp     esi, [rdi+10h]
0x180091607  jb      short loc_1800915EA
0x180091609  mov     rcx, [rbp+pv]
0x18009160d  test    rcx, rcx
0x180091610  jz      short loc_180091644
0x180091612  mov     esi, r13d
0x180091615  cmp     [rbp+arg_8], r13d
0x180091619  jbe     short loc_18009163A
0x18009161b  mov     ebx, esi
0x18009161d  mov     rcx, [rcx+rbx*8]; pv
0x180091621  call    cs:__imp_CoTaskMemFree
0x180091627  mov     rax, [rbp+pv]
0x18009162b  inc     esi
0x18009162d  mov     [rax+rbx*8], r13
0x180091631  mov     rcx, [rbp+pv]; pv
0x180091635  cmp     esi, [rbp+arg_8]
0x180091638  jb      short loc_18009161B
0x18009163a  call    cs:__imp_CoTaskMemFree
0x180091640  mov     [rbp+pv], r13
0x180091644  mov     ebx, [rbp+var_40]
0x180091647  test    rdi, rdi
0x18009164a  jz      short loc_180091654
0x18009164c  mov     rcx, rdi; Block
0x18009164f  call    ?Release@?$CSxSimpleArray@PEAG@@QEAAKXZ; CSxSimpleArray<ushort *>::Release(void)
0x180091654  lea     rcx, [rbp+var_40]; this
0x180091658  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18009165d  mov     eax, ebx
0x18009165f  add     rsp, 78h
0x180091663  pop     r15
0x180091665  pop     r14
0x180091667  pop     r13
0x180091669  pop     r12
0x18009166b  pop     rdi
0x18009166c  pop     rsi
0x18009166d  pop     rbx
0x18009166e  pop     rbp
0x18009166f  retn
```
