# CArchiveIDList::AppendRelPathAndName(int,ushort *,uint)

- ea: `0x18000f370`
- end: `0x18000f529`
- name: `?AppendRelPathAndName@CArchiveIDList@@QEBAJHPEAGI@Z`
- size: `441`
- prototype: `__int64 __fastcall(CArchiveIDList *this, ASSOCKEY, unsigned __int16 *, const WCHAR *)`
- caller_count: `6`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000d244`
- `0x18000d6cc`
- `0x18000f200`
- `0x18001ea30`
- `0x180029d2c`
- `0x18002b0b0`

## callees

- `0x18000f370`
- `0x18000f530`
- `0x18000f5f0`
- `0x18000f698`
- `0x18000f6f8`

## import_xrefs

- `SHLWAPI!PathAppendW` at `0x18000f511`
- `SHLWAPI!PathAppendW` at `0x18000f511`
- `SHLWAPI!__imp_ualstrcpynW` at `0x18000f456`
- `SHLWAPI!__imp_ualstrcpynW` at `0x18000f456`
- `SHLWAPI!__imp_ualstrlenW` at `0x18000f4a1`
- `SHLWAPI!__imp_ualstrlenW` at `0x18000f4a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f4c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f4dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f4c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f4dd`

## pseudocode

```c
__int64 __fastcall CArchiveIDList::AppendRelPathAndName(
        CArchiveIDList *this,
        ASSOCKEY a2,
        unsigned __int16 *a3,
        const WCHAR *a4)
{
  WCHAR *v6; // rdi
  int v7; // ebx
  unsigned __int64 v8; // rdx
  PWSTR *v9; // r9
  unsigned __int64 v11; // rax
  __int64 v12; // rcx
  unsigned __int64 v13; // r14
  unsigned __int64 v14; // rdi
  HKEY *v15; // [rsp+20h] [rbp-48h]
  unsigned __int16 **v16; // [rsp+20h] [rbp-48h]
  unsigned __int64 *v17; // [rsp+28h] [rbp-40h]
  unsigned int v18; // [rsp+30h] [rbp-38h]
  PCWSTR pszExt[5]; // [rsp+40h] [rbp-28h] BYREF

  *(_OWORD *)pszExt = 0;
  if ( a2 )
  {
    v6 = (WCHAR *)((char *)this + 2 * *((int *)this + 21) + 94);
    pszExt[1] = v6;
    if ( ((unsigned __int8)v6 & 1) == 0 )
    {
LABEL_3:
      v7 = StringCchCatW(a3, 0x104u, v6);
      if ( v7 < 0 )
        goto LABEL_10;
      if ( v6 != pszExt[1] && v6 != &psz )
        LocalFree(v6);
      pszExt[0] = 0;
      v7 = CTempAlignedString::Set((CTempAlignedString *)pszExt, (const unsigned __int16 *)this + 46);
      if ( v7 >= 0 )
      {
        v6 = (WCHAR *)pszExt[0];
        v7 = StringCchCatW(a3, 0x104u, pszExt[0]);
        goto LABEL_10;
      }
      goto LABEL_22;
    }
    LODWORD(v11) = ualstrlenW((ASSOCF)v6, a2, a3, a4, v15);
    v13 = v11;
    v14 = v11 + 1;
    if ( v11 + 1 >= v11 )
    {
      v7 = _AllocArray<unsigned short,CTLocalAllocPolicy>(v12, 0, v11 + 1, pszExt);
      if ( v7 >= 0 )
      {
        v8 = v14;
        v6 = (WCHAR *)pszExt[0];
        StringCchCopyNExW((unsigned __int16 *)pszExt[0], v8, 0, v13, v16, v17, v18);
        ualstrcpynW(v6, (PERCEIVED *)pszExt[1], (PERCEIVEDFLAG *)(unsigned int)(v13 + 1), v9);
        goto LABEL_9;
      }
    }
    else
    {
      v7 = -2147024362;
    }
    v6 = (WCHAR *)&psz;
LABEL_9:
    if ( v7 < 0 )
      goto LABEL_10;
    goto LABEL_3;
  }
  v7 = CTempAlignedString::Set((CTempAlignedString *)pszExt, (const unsigned __int16 *)this + 46);
  if ( v7 < 0 )
  {
LABEL_22:
    v6 = (WCHAR *)pszExt[0];
LABEL_10:
    if ( v7 == -2147024774 )
      v7 = -2147417803;
    goto LABEL_12;
  }
  v6 = (WCHAR *)pszExt[0];
  if ( !PathAppendW(a3, pszExt[0]) )
    v7 = -2147417803;
LABEL_12:
  if ( v6 != pszExt[1] && v6 != &psz )
    LocalFree(v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000f370  push    rbx
0x18000f372  push    rdi
0x18000f373  push    r15
0x18000f375  sub     rsp, 50h
0x18000f379  mov     [rsp+68h+arg_0], rbp
0x18000f37e  xorps   xmm0, xmm0
0x18000f381  mov     [rsp+68h+arg_8], rsi
0x18000f386  mov     rsi, rcx
0x18000f389  lea     r15, psz
0x18000f390  mov     rbp, r8
0x18000f393  movdqu  xmmword ptr [rsp+68h+pszExt], xmm0
0x18000f399  test    edx, edx
0x18000f39b  jz      loc_18000F4E8
0x18000f3a1  movsxd  rdi, dword ptr [rcx+54h]
0x18000f3a5  add     rdi, 2Fh ; '/'
0x18000f3a9  lea     rdi, [rcx+rdi*2]
0x18000f3ad  mov     [rsp+68h+pszExt+8], rdi
0x18000f3b2  test    dil, 1
0x18000f3b6  jnz     loc_18000F496
0x18000f3bc  mov     r8, rdi; unsigned __int16 *
0x18000f3bf  mov     edx, 104h; unsigned __int64
0x18000f3c4  mov     rcx, rbp; unsigned __int16 *
0x18000f3c7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000f3cc  mov     ebx, eax
0x18000f3ce  test    eax, eax
0x18000f3d0  js      loc_18000F46C
0x18000f3d6  cmp     rdi, [rsp+68h+pszExt+8]
0x18000f3db  jnz     loc_18000F4D1
0x18000f3e1  lea     rdx, [rsi+5Ch]; unsigned __int16 *
0x18000f3e5  mov     [rsp+68h+pszExt], 0
0x18000f3ee  lea     rcx, [rsp+68h+pszExt]; this
0x18000f3f3  call    ?Set@CTempAlignedString@@QEAAJPEFBG@Z; CTempAlignedString::Set(ushort const *)
0x18000f3f8  mov     ebx, eax
0x18000f3fa  test    eax, eax
0x18000f3fc  js      loc_18000F4FC
0x18000f402  mov     rdi, [rsp+68h+pszExt]
0x18000f407  mov     edx, 104h; unsigned __int64
0x18000f40c  mov     r8, rdi; unsigned __int16 *
0x18000f40f  mov     rcx, rbp; unsigned __int16 *
0x18000f412  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000f417  mov     ebx, eax
0x18000f419  jmp     short loc_18000F46C
0x18000f41b  lea     r9, [rsp+68h+pszExt]
0x18000f420  mov     r8, rdi
0x18000f423  xor     edx, edx
0x18000f425  call    ??$_AllocArray@GVCTLocalAllocPolicy@@@@YAJPEAXK_KPEAPEAG@Z; _AllocArray<ushort,CTLocalAllocPolicy>(void *,ulong,unsigned __int64,ushort * *)
0x18000f42a  mov     ebx, eax
0x18000f42c  test    eax, eax
0x18000f42e  js      loc_18000F4BC
0x18000f434  mov     rdx, rdi; unsigned __int64
0x18000f437  mov     r9, r14; unsigned __int64
0x18000f43a  mov     rdi, [rsp+68h+pszExt]
0x18000f43f  xor     r8d, r8d; unsigned __int16 *
0x18000f442  mov     rcx, rdi; unsigned __int16 *
0x18000f445  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x18000f44a  mov     rdx, [rsp+68h+pszExt+8]; ptype
0x18000f44f  lea     r8d, [r14+1]; pflag
0x18000f453  mov     rcx, rdi; pszExt
0x18000f456  call    cs:__imp_ualstrcpynW
0x18000f45c  mov     r14, [rsp+68h+arg_10]
0x18000f464  test    ebx, ebx
0x18000f466  jns     loc_18000F3BC
0x18000f46c  cmp     ebx, 8007007Ah
0x18000f472  mov     eax, 80010135h
0x18000f477  cmovz   ebx, eax
0x18000f47a  mov     rsi, [rsp+68h+arg_8]
0x18000f47f  mov     rbp, [rsp+68h+arg_0]
0x18000f484  cmp     rdi, [rsp+68h+pszExt+8]
0x18000f489  jnz     short loc_18000F4C1
0x18000f48b  mov     eax, ebx
0x18000f48d  add     rsp, 50h
0x18000f491  pop     r15
0x18000f493  pop     rdi
0x18000f494  pop     rbx
0x18000f495  retn
0x18000f496  mov     rcx, rdi; flags
0x18000f499  mov     [rsp+68h+arg_10], r14
0x18000f4a1  call    cs:__imp_ualstrlenW
0x18000f4a7  mov     r14, rax
0x18000f4aa  lea     rdi, [rax+1]
0x18000f4ae  cmp     rdi, rax
0x18000f4b1  jnb     loc_18000F41B
0x18000f4b7  mov     ebx, 80070216h
0x18000f4bc  mov     rdi, r15
0x18000f4bf  jmp     short loc_18000F45C
0x18000f4c1  cmp     rdi, r15
0x18000f4c4  jz      short loc_18000F48B
0x18000f4c6  mov     rcx, rdi; hMem
0x18000f4c9  call    cs:__imp_LocalFree
0x18000f4cf  jmp     short loc_18000F48B
0x18000f4d1  cmp     rdi, r15
0x18000f4d4  jz      loc_18000F3E1
0x18000f4da  mov     rcx, rdi; hMem
0x18000f4dd  call    cs:__imp_LocalFree
0x18000f4e3  jmp     loc_18000F3E1
0x18000f4e8  lea     rdx, [rcx+5Ch]; unsigned __int16 *
0x18000f4ec  lea     rcx, [rsp+68h+pszExt]; this
0x18000f4f1  call    ?Set@CTempAlignedString@@QEAAJPEFBG@Z; CTempAlignedString::Set(ushort const *)
0x18000f4f6  mov     ebx, eax
0x18000f4f8  test    eax, eax
0x18000f4fa  jns     short loc_18000F506
0x18000f4fc  mov     rdi, [rsp+68h+pszExt]
0x18000f501  jmp     loc_18000F46C
0x18000f506  mov     rdi, [rsp+68h+pszExt]
0x18000f50b  mov     rcx, rbp; pszPath
0x18000f50e  mov     rdx, rdi; pszMore
0x18000f511  call    cs:__imp_PathAppendW
0x18000f517  test    eax, eax
0x18000f519  jnz     loc_18000F47A
0x18000f51f  mov     ebx, 80010135h
0x18000f524  jmp     loc_18000F47A
```
