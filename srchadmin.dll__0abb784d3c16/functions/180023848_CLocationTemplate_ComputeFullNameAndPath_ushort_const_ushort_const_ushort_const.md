# CLocationTemplate::_ComputeFullNameAndPath(ushort const *,ushort const *,ushort const *)

- ea: `0x180023848`
- end: `0x180023938`
- name: `?_ComputeFullNameAndPath@CLocationTemplate@@AEAAJPEBG00@Z`
- size: `240`
- prototype: `__int64 __fastcall(WCHAR *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x180023d8c`

## callees

- `0x180005cc0`
- `0x1800094f0`
- `0x18000957c`
- `0x180023848`
- `0x18002f484`

## import_xrefs

- `SHELL32!__imp_PathCleanupSpec` at `0x1800238e9`
- `SHELL32!__imp_PathCleanupSpec` at `0x1800238e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023912`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023912`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180023905`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180023905`

## pseudocode

```c
__int64 __fastcall CLocationTemplate::_ComputeFullNameAndPath(
        WCHAR *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  HRESULT v6; // ebx
  LPVOID pv[2]; // [rsp+30h] [rbp-258h] BYREF
  WCHAR pszSpec[264]; // [rsp+40h] [rbp-248h] BYREF

  pv[0] = 0;
  if ( !*a4 )
    goto LABEL_4;
  v6 = SHFormatResMessageArgAlloc(Globals, 1801, pv);
  if ( v6 >= 0 )
  {
    a3 = (const unsigned __int16 *)pv[0];
LABEL_4:
    if ( !*a3 )
      goto LABEL_5;
    v6 = StringCchCopyW(pszSpec, 0x104u, a3);
    if ( v6 < 0 )
      goto LABEL_10;
    v6 = StringCchCatW(pszSpec, 0x104u, L".searchconnector-ms");
    if ( v6 < 0 )
      goto LABEL_10;
    if ( PathCleanupSpec(a2, pszSpec) >= 0 )
      v6 = PathCchCombine(this + 270, 0x104u, a2, pszSpec);
    else
LABEL_5:
      v6 = -2147024809;
LABEL_10:
    CoTaskMemFree(pv[0]);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180023848  push    rbx
0x18002384a  push    rbp
0x18002384b  push    rsi
0x18002384c  push    rdi
0x18002384d  push    r14
0x18002384f  sub     rsp, 260h
0x180023856  mov     rax, cs:__security_cookie
0x18002385d  xor     rax, rsp
0x180023860  mov     [rsp+288h+var_38], rax
0x180023868  xor     ebp, ebp
0x18002386a  mov     rdi, rdx
0x18002386d  mov     rsi, rcx
0x180023870  mov     [rsp+288h+pv], rbp
0x180023875  cmp     [r9], bp
0x180023879  jz      short loc_1800238A1
0x18002387b  mov     rcx, cs:Globals
0x180023882  mov     edx, 709h
0x180023887  mov     [rsp+288h+var_268], r8
0x18002388c  lea     r8, [rsp+288h+pv]
0x180023891  call    SHFormatResMessageArgAlloc
0x180023896  mov     ebx, eax
0x180023898  test    eax, eax
0x18002389a  js      short loc_180023918
0x18002389c  mov     r8, [rsp+288h+pv]; unsigned __int16 *
0x1800238a1  cmp     [r8], bp
0x1800238a5  jnz     short loc_1800238AE
0x1800238a7  mov     ebx, 80070057h
0x1800238ac  jmp     short loc_18002390D
0x1800238ae  mov     r14d, 104h
0x1800238b4  lea     rcx, [rsp+288h+pszSpec]; unsigned __int16 *
0x1800238b9  mov     edx, r14d; unsigned __int64
0x1800238bc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800238c1  mov     ebx, eax
0x1800238c3  test    eax, eax
0x1800238c5  js      short loc_18002390D
0x1800238c7  lea     r8, aSearchconnecto; ".searchconnector-ms"
0x1800238ce  mov     edx, r14d; unsigned __int64
0x1800238d1  lea     rcx, [rsp+288h+pszSpec]; unsigned __int16 *
0x1800238d6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800238db  mov     ebx, eax
0x1800238dd  test    eax, eax
0x1800238df  js      short loc_18002390D
0x1800238e1  lea     rdx, [rsp+288h+pszSpec]; pszSpec
0x1800238e6  mov     rcx, rdi; pszDir
0x1800238e9  call    cs:__imp_PathCleanupSpec
0x1800238ef  test    eax, eax
0x1800238f1  js      short loc_1800238A7
0x1800238f3  lea     rcx, [rsi+21Ch]; pszPathOut
0x1800238fa  mov     r8, rdi; pszPathIn
0x1800238fd  lea     r9, [rsp+288h+pszSpec]; pszMore
0x180023902  mov     edx, r14d; cchPathOut
0x180023905  call    cs:__imp_PathCchCombine
0x18002390b  mov     ebx, eax
0x18002390d  mov     rcx, [rsp+288h+pv]; pv
0x180023912  call    cs:__imp_CoTaskMemFree
0x180023918  mov     eax, ebx
0x18002391a  mov     rcx, [rsp+288h+var_38]
0x180023922  xor     rcx, rsp; StackCookie
0x180023925  call    __security_check_cookie
0x18002392a  add     rsp, 260h
0x180023931  pop     r14
0x180023933  pop     rdi
0x180023934  pop     rsi
0x180023935  pop     rbp
0x180023936  pop     rbx
0x180023937  retn
```
