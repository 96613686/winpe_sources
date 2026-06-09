# ReadCredsInfoFromStream(IStream *,_AUI_CREDS_INFO *)

- ea: `0x180006164`
- end: `0x180006374`
- name: `?ReadCredsInfoFromStream@@YAJPEAUIStream@@PEAU_AUI_CREDS_INFO@@@Z`
- size: `528`
- prototype: `__int64 __fastcall(IUnknown *pstm, struct _AUI_CREDS_INFO *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180011720`

## callees

- `0x180006164`
- `0x18001d010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1800062a5`
- `KERNEL32!HeapAlloc` at `0x18000630c`
- `KERNEL32!HeapAlloc` at `0x1800062a5`
- `KERNEL32!HeapAlloc` at `0x18000630c`
- `KERNEL32!GetProcessHeap` at `0x180006294`
- `KERNEL32!GetProcessHeap` at `0x1800062eb`
- `KERNEL32!GetProcessHeap` at `0x180006294`
- `KERNEL32!GetProcessHeap` at `0x1800062eb`
- `ole32!CoImpersonateClient` at `0x180006181`
- `ole32!CoImpersonateClient` at `0x180006181`
- `ole32!CoSetProxyBlanket` at `0x1800061cb`
- `ole32!CoSetProxyBlanket` at `0x18000622d`
- `ole32!CoSetProxyBlanket` at `0x1800061cb`
- `ole32!CoSetProxyBlanket` at `0x18000622d`
- `ole32!CoRevertToSelf` at `0x180006244`
- `ole32!CoRevertToSelf` at `0x180006244`
- `SHLWAPI!__imp_IStream_Reset` at `0x18000624d`
- `SHLWAPI!__imp_IStream_Reset` at `0x18000624d`

## pseudocode

```c
__int64 __fastcall ReadCredsInfoFromStream(IUnknown *pstm, struct _AUI_CREDS_INFO *a2)
{
  HRESULT v4; // eax
  unsigned int v5; // r8d
  HRESULT v6; // eax
  struct IUnknownVtbl *lpVtbl; // rax
  int v8; // eax
  unsigned int v9; // esi
  HANDLE ProcessHeap; // rax
  LPVOID v11; // rax
  int v12; // esi
  HANDLE v13; // rax
  LPVOID v14; // rax
  int v16; // [rsp+60h] [rbp+18h] BYREF
  __int64 v17; // [rsp+68h] [rbp+20h] BYREF

  v16 = 0;
  v4 = CoImpersonateClient();
  v5 = 0;
  if ( v4 != -2147417833 )
    v5 = v4;
  if ( (v5 & 0x80000000) == 0 )
  {
    v6 = CoSetProxyBlanket(pstm, 0xFFFFFFFF, 0, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x20u);
    if ( !v6 || v6 == -2147467262 )
    {
      lpVtbl = pstm->lpVtbl;
      v17 = 0;
      if ( ((__int64 (__fastcall *)(IUnknown *, GUID *, __int64 *))lpVtbl->QueryInterface)(
             pstm,
             &GUID_00000000_0000_0000_c000_000000000046,
             &v17) >= 0 )
      {
        CoSetProxyBlanket(pstm, 0xFFFFFFFF, 0, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x20u);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      }
    }
    CoRevertToSelf();
    IStream_Reset((IStream *)pstm);
    v8 = ((__int64 (__fastcall *)(IUnknown *, struct _AUI_CREDS_INFO *, __int64, int *))pstm->lpVtbl[1].QueryInterface)(
           pstm,
           a2,
           56,
           &v16);
    v5 = v8;
    if ( v16 != 56 )
      return (unsigned int)-2147467259;
    if ( v8 < 0 )
      return v5;
    v9 = *((_DWORD *)a2 + 6);
    if ( v9 )
    {
      ProcessHeap = GetProcessHeap();
      v11 = HeapAlloc(ProcessHeap, 8u, v9);
      *((_QWORD *)a2 + 4) = v11;
      if ( !v11 )
        return (unsigned int)-2147024882;
      v5 = ((__int64 (__fastcall *)(IUnknown *, LPVOID, _QWORD, int *))pstm->lpVtbl[1].QueryInterface)(
             pstm,
             v11,
             *((unsigned int *)a2 + 6),
             &v16);
      if ( v16 != *((_DWORD *)a2 + 6) )
        return (unsigned int)-2147467259;
      if ( (v5 & 0x80000000) != 0 )
        return v5;
    }
    v12 = *((_DWORD *)a2 + 10);
    if ( !v12 )
      return v5;
    v13 = GetProcessHeap();
    v14 = HeapAlloc(v13, 8u, ((2580 * v12) & 0xFFFFFFF0) + 16);
    *((_QWORD *)a2 + 6) = v14;
    if ( v14 )
    {
      v5 = ((__int64 (__fastcall *)(IUnknown *, LPVOID, _QWORD, int *))pstm->lpVtbl[1].QueryInterface)(
             pstm,
             v14,
             ((2580 * *((_DWORD *)a2 + 10)) & 0xFFFFFFF0) + 16,
             &v16);
      if ( v16 == ((2580 * *((_DWORD *)a2 + 10)) & 0xFFFFFFF0) + 16 )
        return v5;
      return (unsigned int)-2147467259;
    }
    return (unsigned int)-2147024882;
  }
  return v5;
}

```

## disassembly

```asm
0x180006164  mov     [rsp+arg_0], rbx
0x180006169  mov     [rsp+arg_8], rsi
0x18000616e  push    rdi
0x18000616f  sub     rsp, 40h
0x180006173  mov     rbx, rdx
0x180006176  mov     [rsp+48h+arg_10], 0
0x18000617e  mov     rdi, rcx
0x180006181  call    cs:__imp_CoImpersonateClient
0x180006187  xor     r8d, r8d
0x18000618a  cmp     eax, 80010117h
0x18000618f  cmovnz  r8d, eax
0x180006193  test    r8d, r8d
0x180006196  js      loc_180006361
0x18000619c  mov     esi, 20h ; ' '
0x1800061a1  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x1800061a5  mov     [rsp+48h+dwCapabilities], esi; dwCapabilities
0x1800061a9  xor     r8d, r8d; dwAuthzSvc
0x1800061ac  mov     [rsp+48h+pAuthInfo], 0; pAuthInfo
0x1800061b5  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x1800061b8  mov     [rsp+48h+dwImpLevel], 3; dwImpLevel
0x1800061c0  mov     rcx, rdi; pProxy
0x1800061c3  mov     [rsp+48h+dwAuthnLevel], 0; dwAuthnLevel
0x1800061cb  call    cs:__imp_CoSetProxyBlanket
0x1800061d1  test    eax, eax
0x1800061d3  jz      short loc_1800061DC
0x1800061d5  cmp     eax, 80004002h
0x1800061da  jnz     short loc_180006244
0x1800061dc  mov     rax, [rdi]
0x1800061df  lea     r8, [rsp+48h+arg_18]
0x1800061e4  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800061eb  mov     [rsp+48h+arg_18], 0
0x1800061f4  mov     rcx, rdi
0x1800061f7  mov     rax, [rax]
0x1800061fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061ff  test    eax, eax
0x180006201  js      short loc_180006244
0x180006203  mov     [rsp+48h+dwCapabilities], esi; dwCapabilities
0x180006207  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18000620b  mov     [rsp+48h+pAuthInfo], 0; pAuthInfo
0x180006214  xor     r8d, r8d; dwAuthzSvc
0x180006217  mov     [rsp+48h+dwImpLevel], 3; dwImpLevel
0x18000621f  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x180006222  mov     rcx, rdi; pProxy
0x180006225  mov     [rsp+48h+dwAuthnLevel], 0; dwAuthnLevel
0x18000622d  call    cs:__imp_CoSetProxyBlanket
0x180006233  mov     rcx, [rsp+48h+arg_18]
0x180006238  mov     rax, [rcx]
0x18000623b  mov     rax, [rax+10h]
0x18000623f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006244  call    cs:__imp_CoRevertToSelf
0x18000624a  mov     rcx, rdi; pstm
0x18000624d  call    cs:__imp_IStream_Reset
0x180006253  mov     rax, [rdi]
0x180006256  lea     r9, [rsp+48h+arg_10]
0x18000625b  mov     r8d, 38h ; '8'
0x180006261  mov     rdx, rbx
0x180006264  mov     rcx, rdi
0x180006267  mov     rax, [rax+18h]
0x18000626b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006270  cmp     [rsp+48h+arg_10], 38h ; '8'
0x180006275  mov     r8d, eax
0x180006278  jz      short loc_180006285
0x18000627a  mov     r8d, 80004005h
0x180006280  jmp     loc_180006361
0x180006285  test    eax, eax
0x180006287  js      loc_180006361
0x18000628d  mov     esi, [rbx+18h]
0x180006290  test    esi, esi
0x180006292  jz      short loc_1800062E4
0x180006294  call    cs:__imp_GetProcessHeap
0x18000629a  mov     r8d, esi; dwBytes
0x18000629d  mov     edx, 8; dwFlags
0x1800062a2  mov     rcx, rax; hHeap
0x1800062a5  call    cs:__imp_HeapAlloc
0x1800062ab  mov     [rbx+20h], rax
0x1800062af  mov     rdx, rax
0x1800062b2  test    rax, rax
0x1800062b5  jz      loc_18000635B
0x1800062bb  mov     rcx, [rdi]
0x1800062be  lea     r9, [rsp+48h+arg_10]
0x1800062c3  mov     r8d, [rbx+18h]
0x1800062c7  mov     rax, [rcx+18h]
0x1800062cb  mov     rcx, rdi
0x1800062ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062d3  mov     r8d, eax
0x1800062d6  mov     eax, [rbx+18h]
0x1800062d9  cmp     [rsp+48h+arg_10], eax
0x1800062dd  jnz     short loc_18000627A
0x1800062df  test    r8d, r8d
0x1800062e2  js      short loc_180006361
0x1800062e4  mov     esi, [rbx+28h]
0x1800062e7  test    esi, esi
0x1800062e9  jz      short loc_180006361
0x1800062eb  call    cs:__imp_GetProcessHeap
0x1800062f1  imul    r8d, esi, 0A14h
0x1800062f8  mov     edx, 8; dwFlags
0x1800062fd  mov     esi, 0FFFFFFF0h
0x180006302  mov     rcx, rax; hHeap
0x180006305  and     r8d, esi
0x180006308  add     r8d, 10h; dwBytes
0x18000630c  call    cs:__imp_HeapAlloc
0x180006312  mov     [rbx+30h], rax
0x180006316  mov     rdx, rax
0x180006319  test    rax, rax
0x18000631c  jz      short loc_18000635B
0x18000631e  mov     rcx, [rdi]
0x180006321  lea     r9, [rsp+48h+arg_10]
0x180006326  imul    r8d, [rbx+28h], 0A14h
0x18000632e  mov     rax, [rcx+18h]
0x180006332  mov     rcx, rdi
0x180006335  and     r8d, esi
0x180006338  add     r8d, 10h
0x18000633c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006341  mov     r8d, eax
0x180006344  imul    eax, [rbx+28h], 0A14h
0x18000634b  and     eax, esi
0x18000634d  add     eax, 10h
0x180006350  cmp     [rsp+48h+arg_10], eax
0x180006354  jz      short loc_180006361
0x180006356  jmp     loc_18000627A
0x18000635b  mov     r8d, 8007000Eh
0x180006361  mov     rbx, [rsp+48h+arg_0]
0x180006366  mov     eax, r8d
0x180006369  mov     rsi, [rsp+48h+arg_8]
0x18000636e  add     rsp, 40h
0x180006372  pop     rdi
0x180006373  retn
```
