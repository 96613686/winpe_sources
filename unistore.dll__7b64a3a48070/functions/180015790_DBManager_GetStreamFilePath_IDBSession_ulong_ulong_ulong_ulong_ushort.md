# DBManager::GetStreamFilePath(IDBSession *,ulong,ulong,ulong,ulong,ushort * *)

- ea: `0x180015790`
- end: `0x1800159a7`
- name: `?GetStreamFilePath@DBManager@@SAJPEAVIDBSession@@KKKKPEAPEAG@Z`
- size: `535`
- prototype: `static int(struct IDBSession *, unsigned int, unsigned int, unsigned int, unsigned int, unsigned __int16 **)`
- caller_count: `6`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18002ea70`
- `0x180031d70`
- `0x180033ebc`
- `0x18004e690`
- `0x1800687f0`
- `0x180094ed0`

## callees

- `0x1800068f0`
- `0x180014bd0`
- `0x180015790`
- `0x180028ef4`
- `0x180032170`
- `0x1800c50f0`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001584a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800158b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015914`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001584a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800158b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015914`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180015900`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180015900`

## string_xrefs

- `0x180015894`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180015951`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`

## pseudocode

```c
__int64 __fastcall DBManager::GetStreamFilePath(
        struct IDBSession *a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned __int16 **a6)
{
  __int64 v6; // rax
  __int64 v9; // r14
  __int64 (__fastcall *v11)(struct IDBSession *); // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  int v14; // r15d
  __int64 v15; // rcx
  __int64 i; // rax
  int DefaultStreamRootPath; // eax
  int v18; // ebx
  __int64 v19; // r9
  __int64 v21; // r9
  HLOCAL hMem; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v23; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v24[264]; // [rsp+50h] [rbp-B0h] BYREF

  v6 = *(_QWORD *)a1;
  v9 = a2;
  v23 = 0;
  v11 = *(__int64 (__fastcall **)(struct IDBSession *))(v6 + 112);
  hMem = 0;
  v14 = v11(a1);
  if ( v14 )
  {
    v18 = (*(__int64 (__fastcall **)(struct IDBSession *, unsigned __int16 **))(*(_QWORD *)a1 + 128LL))(a1, &v23);
    if ( v18 < 0 )
    {
      v19 = 3095;
LABEL_11:
      Log_UnistoreHREvent_0(
        (unsigned int)v18,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
        v19);
      if ( hMem )
        LocalFree(hMem);
      return (unsigned int)v18;
    }
  }
  v15 = 12 * v9;
  for ( i = 0; (unsigned int)i < LODWORD((&g_rgTableInfo)[v15 + 3]); i = (unsigned int)(i + 1) )
  {
    v13 = (__int64)*(&g_rgTableInfo + v15 + 7);
    if ( *(_DWORD *)(v13 + 8 * i) == a4 )
    {
      a4 = *(_DWORD *)(v13 + 8 * i + 4);
      if ( a4 == -1 )
        a4 = *(_DWORD *)(v13 + 8 * i);
      break;
    }
  }
  DefaultStreamRootPath = StreamHelper::GetDefaultStreamRootPath(v24, v12, v13);
  v18 = DefaultStreamRootPath;
  if ( DefaultStreamRootPath < 0 )
  {
    v21 = 3106;
    goto LABEL_22;
  }
  hMem = 0;
  v18 = StreamHelper::BuildStreamPropertyFilePath(v24, v9, a3, a4, v23, 0, (unsigned __int16 **)&hMem);
  if ( v18 < 0 )
  {
    v19 = 3109;
    goto LABEL_11;
  }
  if ( v14 && a5 == 0x80000000 && !PathFileExistsW((LPCWSTR)hMem) )
  {
    if ( hMem )
      LocalFree(hMem);
    hMem = 0;
    DefaultStreamRootPath = StreamHelper::BuildStreamPropertyFilePath(v24, v9, a3, a4, 0, 0, (unsigned __int16 **)&hMem);
    v18 = DefaultStreamRootPath;
    if ( DefaultStreamRootPath < 0 )
    {
      v21 = 3117;
LABEL_22:
      Log_UnistoreHREvent_0(
        (unsigned int)DefaultStreamRootPath,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
        v21);
      auto_local_array_ptr<unsigned char>::~auto_local_array_ptr<unsigned char>(&hMem);
      return (unsigned int)v18;
    }
  }
  *a6 = (unsigned __int16 *)hMem;
  return 0;
}

```

## disassembly

```asm
0x180015790  push    rbp
0x180015792  push    rbx
0x180015793  push    rsi
0x180015794  push    r12
0x180015796  push    r13
0x180015798  push    r14
0x18001579a  push    r15
0x18001579c  lea     rbp, [rsp-170h]
0x1800157a4  sub     rsp, 270h
0x1800157ab  mov     rax, cs:__security_cookie
0x1800157b2  xor     rax, rsp
0x1800157b5  mov     [rbp+1A0h+var_40], rax
0x1800157bc  mov     rax, [rcx]
0x1800157bf  mov     esi, r9d
0x1800157c2  mov     r13, [rbp+1A0h+arg_28]
0x1800157c9  mov     r12d, r8d
0x1800157cc  mov     r14d, edx
0x1800157cf  mov     rbx, rcx
0x1800157d2  mov     [rsp+2A0h+var_258], 0
0x1800157db  mov     rax, [rax+70h]
0x1800157df  mov     [rsp+2A0h+hMem], 0
0x1800157e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157ed  mov     r15d, eax
0x1800157f0  test    eax, eax
0x1800157f2  jnz     loc_180015973
0x1800157f8  lea     rcx, [r14+r14*2]
0x1800157fc  shl     rcx, 5
0x180015800  lea     r9, ?g_rgTableInfo@@3QBUUSTableInfo@@B; USTableInfo const near * const g_rgTableInfo
0x180015807  xor     eax, eax
0x180015809  cmp     eax, [rcx+r9+30h]
0x18001580e  jnb     short loc_18001582C
0x180015810  mov     r8, [rcx+r9+38h]
0x180015815  cmp     [r8+rax*8], esi
0x180015819  jz      short loc_18001581F
0x18001581b  inc     eax
0x18001581d  jmp     short loc_180015809
0x18001581f  mov     esi, [r8+rax*8+4]
0x180015824  cmp     esi, 0FFFFFFFFh
0x180015827  cmovz   esi, [r8+rax*8]
0x18001582c  lea     rcx, [rsp+2A0h+var_250]; unsigned __int16 *
0x180015831  call    ?GetDefaultStreamRootPath@StreamHelper@@SAJPEAGK@Z; StreamHelper::GetDefaultStreamRootPath(ushort *,ulong)
0x180015836  mov     ebx, eax
0x180015838  test    eax, eax
0x18001583a  js      loc_18001599F
0x180015840  mov     rcx, [rsp+2A0h+hMem]; hMem
0x180015845  test    rcx, rcx
0x180015848  jz      short loc_180015850
0x18001584a  call    cs:__imp_LocalFree
0x180015850  mov     rax, [rsp+2A0h+var_258]
0x180015855  lea     rcx, [rsp+2A0h+hMem]
0x18001585a  mov     [rsp+2A0h+var_270], rcx; unsigned __int16 **
0x18001585f  mov     r9d, esi; unsigned int
0x180015862  mov     [rsp+2A0h+var_278], 0; int
0x18001586a  lea     rcx, [rsp+2A0h+var_250]; unsigned __int16 *
0x18001586f  mov     r8d, r12d; unsigned int
0x180015872  mov     [rsp+2A0h+var_280], rax; unsigned __int16 *
0x180015877  mov     edx, r14d; unsigned int
0x18001587a  mov     [rsp+2A0h+hMem], 0
0x180015883  call    ?BuildStreamPropertyFilePath@StreamHelper@@SAJPEBGKKK0HPEAPEAG@Z; StreamHelper::BuildStreamPropertyFilePath(ushort const *,ulong,ulong,ulong,ushort const *,int,ushort * *)
0x180015888  mov     ebx, eax
0x18001588a  test    eax, eax
0x18001588c  jns     short loc_1800158DB
0x18001588e  mov     r9d, 0C25h
0x180015894  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001589b  mov     edx, 1
0x1800158a0  mov     ecx, ebx
0x1800158a2  call    Log_UnistoreHREvent_0
0x1800158a7  mov     rcx, [rsp+2A0h+hMem]; hMem
0x1800158ac  test    rcx, rcx
0x1800158af  jz      short loc_1800158B7
0x1800158b1  call    cs:__imp_LocalFree
0x1800158b7  mov     eax, ebx
0x1800158b9  mov     rcx, [rbp+1A0h+var_40]
0x1800158c0  xor     rcx, rsp; StackCookie
0x1800158c3  call    __security_check_cookie
0x1800158c8  add     rsp, 270h
0x1800158cf  pop     r15
0x1800158d1  pop     r14
0x1800158d3  pop     r13
0x1800158d5  pop     r12
0x1800158d7  pop     rsi
0x1800158d8  pop     rbx
0x1800158d9  pop     rbp
0x1800158da  retn
0x1800158db  xor     ebx, ebx
0x1800158dd  test    r15d, r15d
0x1800158e0  jnz     short loc_1800158EF
0x1800158e2  mov     rax, [rsp+2A0h+hMem]
0x1800158e7  mov     [r13+0], rax
0x1800158eb  xor     eax, eax
0x1800158ed  jmp     short loc_1800158B9
0x1800158ef  cmp     [rbp+1A0h+arg_20], 80000000h
0x1800158f9  jnz     short loc_1800158E2
0x1800158fb  mov     rcx, [rsp+2A0h+hMem]; pszPath
0x180015900  call    cs:__imp_PathFileExistsW
0x180015906  test    eax, eax
0x180015908  jnz     short loc_1800158E2
0x18001590a  mov     rcx, [rsp+2A0h+hMem]; hMem
0x18001590f  test    rcx, rcx
0x180015912  jz      short loc_18001591A
0x180015914  call    cs:__imp_LocalFree
0x18001591a  lea     rax, [rsp+2A0h+hMem]
0x18001591f  mov     [rsp+2A0h+hMem], rbx
0x180015924  mov     [rsp+2A0h+var_270], rax; unsigned __int16 **
0x180015929  lea     rcx, [rsp+2A0h+var_250]; unsigned __int16 *
0x18001592e  mov     [rsp+2A0h+var_278], ebx; int
0x180015932  mov     r9d, esi; unsigned int
0x180015935  mov     r8d, r12d; unsigned int
0x180015938  mov     [rsp+2A0h+var_280], rbx; unsigned __int16 *
0x18001593d  mov     edx, r14d; unsigned int
0x180015940  call    ?BuildStreamPropertyFilePath@StreamHelper@@SAJPEBGKKK0HPEAPEAG@Z; StreamHelper::BuildStreamPropertyFilePath(ushort const *,ulong,ulong,ulong,ushort const *,int,ushort * *)
0x180015945  mov     ebx, eax
0x180015947  test    eax, eax
0x180015949  jns     short loc_1800158E2
0x18001594b  mov     r9d, 0C2Dh
0x180015951  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180015958  mov     edx, 1
0x18001595d  mov     ecx, eax
0x18001595f  call    Log_UnistoreHREvent_0
0x180015964  lea     rcx, [rsp+2A0h+hMem]
0x180015969  call    ??1?$auto_local_array_ptr@E@@QEAA@XZ; auto_local_array_ptr<uchar>::~auto_local_array_ptr<uchar>(void)
0x18001596e  jmp     loc_1800158B7
0x180015973  mov     rdx, [rbx]
0x180015976  mov     rcx, rbx
0x180015979  mov     rax, [rdx+80h]
0x180015980  lea     rdx, [rsp+2A0h+var_258]
0x180015985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001598a  mov     ebx, eax
0x18001598c  test    eax, eax
0x18001598e  jns     loc_1800157F8
0x180015994  mov     r9d, 0C17h
0x18001599a  jmp     loc_180015894
0x18001599f  mov     r9d, 0C22h
0x1800159a5  jmp     short loc_180015951
```
