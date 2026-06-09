# CompareIDsImpl(IShellFolder2 *,__int64,_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE const *)

- ea: `0x18004a048`
- end: `0x18004a26d`
- name: `?CompareIDsImpl@@YAJPEAUIShellFolder2@@_JPEFBU_ITEMIDLIST_RELATIVE@@2@Z`
- size: `549`
- prototype: `int(struct IShellFolder2 *, __int64, const struct _ITEMIDLIST_RELATIVE *, const struct _ITEMIDLIST_RELATIVE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180049f60`

## callees

- `0x18000acfc`
- `0x18000d5e4`
- `0x18003326c`
- `0x180036f50`
- `0x18004a048`
- `0x18004c320`
- `0x180071010`

## import_xrefs

- `PROPSYS!VariantCompare` at `0x18004a1f5`
- `PROPSYS!VariantCompare` at `0x18004a1f5`
- `SHELL32!__imp_ILFree` at `0x18004a23c`
- `SHELL32!__imp_ILFree` at `0x18004a245`
- `SHELL32!__imp_ILFree` at `0x18004a23c`
- `SHELL32!__imp_ILFree` at `0x18004a245`
- `SHLWAPI!__imp_IsAppCompatModeEnabled` at `0x18004a15d`
- `SHLWAPI!__imp_IsAppCompatModeEnabled` at `0x18004a1d9`
- `SHLWAPI!__imp_IsAppCompatModeEnabled` at `0x18004a15d`
- `SHLWAPI!__imp_IsAppCompatModeEnabled` at `0x18004a1d9`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18004a1e7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18004a1e7`
- `OLEAUT32!__imp_VariantInit` at `0x18004a194`
- `OLEAUT32!__imp_VariantInit` at `0x18004a1ce`
- `OLEAUT32!__imp_VariantInit` at `0x18004a194`
- `OLEAUT32!__imp_VariantInit` at `0x18004a1ce`
- `OLEAUT32!__imp_VariantClear` at `0x18004a229`
- `OLEAUT32!__imp_VariantClear` at `0x18004a233`
- `OLEAUT32!__imp_VariantClear` at `0x18004a229`
- `OLEAUT32!__imp_VariantClear` at `0x18004a233`

## pseudocode

```c
__int64 __fastcall CompareIDsImpl(
        struct IShellFolder2 *a1,
        __int64 a2,
        const struct _ITEMIDLIST_RELATIVE *a3,
        const struct _ITEMIDLIST_RELATIVE *a4)
{
  ITEMIDLIST *v4; // r15
  int v8; // ebx
  ITEMIDLIST *v9; // r14
  const struct _ITEMIDLIST_RELATIVE *v10; // rcx
  struct _ITEMID_CHILD *v11; // r12
  const struct _ITEMIDLIST_RELATIVE *v12; // rcx
  struct IShellFolder2Vtbl *lpVtbl; // rax
  const WCHAR *v14; // rdx
  int v15; // ebx
  struct IShellFolder2Vtbl *v16; // rax
  const WCHAR *v17; // rdx
  int v18; // eax
  struct _ITEMID_CHILD *v20; // [rsp+30h] [rbp-49h] BYREF
  __int64 v21; // [rsp+38h] [rbp-41h]
  __int128 v22; // [rsp+40h] [rbp-39h] BYREF
  int v23; // [rsp+50h] [rbp-29h]
  VARIANTARG var2; // [rsp+58h] [rbp-21h] BYREF
  VARIANTARG pvarg; // [rsp+70h] [rbp-9h] BYREF

  v4 = 0;
  v21 = a2;
  v8 = -2147024809;
  if ( a3 && a4 && *(_WORD *)a3 && *(_WORD *)a4 )
  {
    if ( a3 == a4 )
      return 0;
    v20 = 0;
    v9 = 0;
    if ( (unsigned int)ILIsChild(a3) )
    {
      v11 = a3;
    }
    else
    {
      v8 = SHILCloneFirst(v10, &v20);
      if ( v8 < 0 )
        return (unsigned int)v8;
      v9 = (ITEMIDLIST *)v20;
      v11 = v20;
    }
    v20 = 0;
    if ( (unsigned int)ILIsChild(a4) )
    {
      v20 = a4;
    }
    else
    {
      v8 = SHILCloneFirst(v12, &v20);
      if ( v8 < 0 )
      {
LABEL_32:
        ILFree(v9);
        return (unsigned int)v8;
      }
      v4 = (ITEMIDLIST *)v20;
    }
    v23 = 0;
    lpVtbl = a1->lpVtbl;
    v22 = 0;
    v8 = ((__int64 (__fastcall *)(struct IShellFolder2 *, _QWORD, __int128 *))lpVtbl->MapColumnToSCID)(
           a1,
           (unsigned __int16)v21,
           &v22);
    if ( v8 >= 0 )
    {
      memset(&pvarg, 0, sizeof(pvarg));
      v15 = 0;
      if ( IsAppCompatModeEnabled((LPCWSTR)0x19, v14) )
        v15 = SHCoInitialize();
      if ( ((int (__fastcall *)(struct IShellFolder2 *, struct _ITEMID_CHILD *, __int128 *, VARIANTARG *))a1->lpVtbl->GetDetailsEx)(
             a1,
             v11,
             &v22,
             &pvarg) < 0 )
        VariantInit(&pvarg);
      v16 = a1->lpVtbl;
      memset(&var2, 0, sizeof(var2));
      if ( ((int (__fastcall *)(struct IShellFolder2 *, struct _ITEMID_CHILD *, __int128 *, VARIANTARG *))v16->GetDetailsEx)(
             a1,
             v20,
             &v22,
             &var2) < 0 )
        VariantInit(&var2);
      if ( IsAppCompatModeEnabled((LPCWSTR)0x19, v17) && !v15 )
        CoUninitialize();
      v18 = VariantCompare(&pvarg, &var2);
      if ( v18 )
      {
        if ( v18 >= 0 )
          v8 = v18 > 0;
        else
          v8 = 0xFFFF;
      }
      else
      {
        v8 = ILCompareRelIDs(a1, a3, a4, v21);
      }
      VariantClear(&var2);
      VariantClear(&pvarg);
    }
    ILFree(v4);
    goto LABEL_32;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18004a048  push    rbp
0x18004a04a  push    rbx
0x18004a04b  push    rsi
0x18004a04c  push    rdi
0x18004a04d  push    r12
0x18004a04f  push    r13
0x18004a051  push    r14
0x18004a053  push    r15
0x18004a055  lea     rbp, [rsp-1Fh]
0x18004a05a  sub     rsp, 98h
0x18004a061  mov     rax, cs:__security_cookie
0x18004a068  xor     rax, rsp
0x18004a06b  mov     [rbp+57h+var_48], rax
0x18004a06f  xor     r15d, r15d
0x18004a072  mov     [rbp+57h+var_98], rdx
0x18004a076  mov     rdi, r9
0x18004a079  mov     rsi, r8
0x18004a07c  mov     r13, rcx
0x18004a07f  mov     ebx, 80070057h
0x18004a084  test    r8, r8
0x18004a087  jz      loc_18004A24B
0x18004a08d  test    r9, r9
0x18004a090  jz      loc_18004A24B
0x18004a096  cmp     [r8], r15w
0x18004a09a  jz      loc_18004A24B
0x18004a0a0  cmp     [r9], r15w
0x18004a0a4  jz      loc_18004A24B
0x18004a0aa  cmp     r8, r9
0x18004a0ad  jnz     short loc_18004A0B7
0x18004a0af  mov     ebx, r15d
0x18004a0b2  jmp     loc_18004A24B
0x18004a0b7  mov     rcx, rsi; struct _ITEMIDLIST_RELATIVE *
0x18004a0ba  mov     [rbp+57h+var_A0], r15
0x18004a0be  mov     r14, r15
0x18004a0c1  call    ?ILIsChild@@YAHPEFBU_ITEMIDLIST_RELATIVE@@@Z; ILIsChild(_ITEMIDLIST_RELATIVE const *)
0x18004a0c6  test    eax, eax
0x18004a0c8  jz      short loc_18004A0CF
0x18004a0ca  mov     r12, rsi
0x18004a0cd  jmp     short loc_18004A0E9
0x18004a0cf  lea     rdx, [rbp+57h+var_A0]; struct _ITEMID_CHILD **
0x18004a0d3  call    ?SHILCloneFirst@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU_ITEMID_CHILD@@@Z; SHILCloneFirst(_ITEMIDLIST_RELATIVE const *,_ITEMID_CHILD * *)
0x18004a0d8  mov     ebx, eax
0x18004a0da  test    eax, eax
0x18004a0dc  js      loc_18004A24B
0x18004a0e2  mov     r14, [rbp+57h+var_A0]
0x18004a0e6  mov     r12, r14
0x18004a0e9  mov     rcx, rdi; struct _ITEMIDLIST_RELATIVE *
0x18004a0ec  mov     [rbp+57h+var_A0], r15
0x18004a0f0  call    ?ILIsChild@@YAHPEFBU_ITEMIDLIST_RELATIVE@@@Z; ILIsChild(_ITEMIDLIST_RELATIVE const *)
0x18004a0f5  test    eax, eax
0x18004a0f7  jz      short loc_18004A0FF
0x18004a0f9  mov     [rbp+57h+var_A0], rdi
0x18004a0fd  jmp     short loc_18004A11A
0x18004a0ff  lea     rdx, [rbp+57h+var_A0]; struct _ITEMID_CHILD **
0x18004a103  call    ?SHILCloneFirst@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU_ITEMID_CHILD@@@Z; SHILCloneFirst(_ITEMIDLIST_RELATIVE const *,_ITEMID_CHILD * *)
0x18004a108  mov     ebx, eax
0x18004a10a  test    eax, eax
0x18004a10c  js      loc_18004A242
0x18004a112  mov     r15, [rbp+57h+var_A0]
0x18004a116  mov     [rbp+57h+var_A0], r15
0x18004a11a  movzx   edx, word ptr [rbp+57h+var_98]
0x18004a11e  lea     r8, [rbp+57h+var_90]
0x18004a122  xor     eax, eax
0x18004a124  xorps   xmm0, xmm0
0x18004a127  mov     [rbp+57h+var_80], eax
0x18004a12a  mov     rcx, r13
0x18004a12d  mov     rax, [r13+0]
0x18004a131  movups  [rbp+57h+var_90], xmm0
0x18004a135  mov     rax, [rax+98h]
0x18004a13c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a141  mov     ebx, eax
0x18004a143  test    eax, eax
0x18004a145  js      loc_18004A239
0x18004a14b  xor     eax, eax
0x18004a14d  xorps   xmm0, xmm0
0x18004a150  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18004a154  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18004a158  xor     ebx, ebx
0x18004a15a  lea     ecx, [rax+19h]; pszPath
0x18004a15d  call    cs:__imp_IsAppCompatModeEnabled
0x18004a163  test    eax, eax
0x18004a165  jz      short loc_18004A16E
0x18004a167  call    ?SHCoInitialize@@YAJXZ; SHCoInitialize(void)
0x18004a16c  mov     ebx, eax
0x18004a16e  mov     rcx, [r13+0]
0x18004a172  lea     r9, [rbp+57h+pvarg]
0x18004a176  lea     r8, [rbp+57h+var_90]
0x18004a17a  mov     rdx, r12
0x18004a17d  mov     rax, [rcx+88h]
0x18004a184  mov     rcx, r13
0x18004a187  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a18c  test    eax, eax
0x18004a18e  jns     short loc_18004A19A
0x18004a190  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18004a194  call    cs:__imp_VariantInit
0x18004a19a  mov     rdx, [rbp+57h+var_A0]
0x18004a19e  lea     r9, [rbp+57h+var2]
0x18004a1a2  xor     eax, eax
0x18004a1a4  lea     r8, [rbp+57h+var_90]
0x18004a1a8  mov     qword ptr [rbp+57h+var2+10h], rax
0x18004a1ac  xorps   xmm0, xmm0
0x18004a1af  mov     rax, [r13+0]
0x18004a1b3  mov     rcx, r13
0x18004a1b6  movups  xmmword ptr [rbp+57h+var2], xmm0
0x18004a1ba  mov     rax, [rax+88h]
0x18004a1c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a1c6  test    eax, eax
0x18004a1c8  jns     short loc_18004A1D4
0x18004a1ca  lea     rcx, [rbp+57h+var2]; pvarg
0x18004a1ce  call    cs:__imp_VariantInit
0x18004a1d4  mov     ecx, 19h; pszPath
0x18004a1d9  call    cs:__imp_IsAppCompatModeEnabled
0x18004a1df  test    eax, eax
0x18004a1e1  jz      short loc_18004A1ED
0x18004a1e3  test    ebx, ebx
0x18004a1e5  jnz     short loc_18004A1ED
0x18004a1e7  call    cs:__imp_CoUninitialize
0x18004a1ed  lea     rdx, [rbp+57h+var2]; var2
0x18004a1f1  lea     rcx, [rbp+57h+pvarg]; var1
0x18004a1f5  call    cs:__imp_VariantCompare
0x18004a1fb  test    eax, eax
0x18004a1fd  jz      short loc_18004A211
0x18004a1ff  jns     short loc_18004A208
0x18004a201  mov     ebx, 0FFFFh
0x18004a206  jmp     short loc_18004A225
0x18004a208  xor     ebx, ebx
0x18004a20a  test    eax, eax
0x18004a20c  setnle  bl
0x18004a20f  jmp     short loc_18004A225
0x18004a211  mov     r9, [rbp+57h+var_98]
0x18004a215  mov     r8, rdi
0x18004a218  mov     rdx, rsi
0x18004a21b  mov     rcx, r13
0x18004a21e  call    ILCompareRelIDs
0x18004a223  mov     ebx, eax
0x18004a225  lea     rcx, [rbp+57h+var2]; pvarg
0x18004a229  call    cs:__imp_VariantClear
0x18004a22f  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18004a233  call    cs:__imp_VariantClear
0x18004a239  mov     rcx, r15; pidl
0x18004a23c  call    cs:__imp_ILFree
0x18004a242  mov     rcx, r14; pidl
0x18004a245  call    cs:__imp_ILFree
0x18004a24b  mov     eax, ebx
0x18004a24d  mov     rcx, [rbp+57h+var_48]
0x18004a251  xor     rcx, rsp; StackCookie
0x18004a254  call    __security_check_cookie
0x18004a259  add     rsp, 98h
0x18004a260  pop     r15
0x18004a262  pop     r14
0x18004a264  pop     r13
0x18004a266  pop     r12
0x18004a268  pop     rdi
0x18004a269  pop     rsi
0x18004a26a  pop     rbx
0x18004a26b  pop     rbp
0x18004a26c  retn
```
