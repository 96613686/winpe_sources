# XE_StaticPackage<1>::GetLocalizedString(ulong,ulong,wchar_t *,ulong)

- ea: `0x100464680`
- end: `0x100464829`
- name: `?GetLocalizedString@?$XE_StaticPackage@$00@@UEAAHKKPEA_WK@Z`
- size: `425`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x100403070`
- `0x10044acd0`
- `0x100464680`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x10046476f`
- `KERNEL32!LoadLibraryExW` at `0x1004647be`
- `KERNEL32!LoadLibraryExW` at `0x10046476f`
- `KERNEL32!LoadLibraryExW` at `0x1004647be`
- `KERNEL32!FreeLibrary` at `0x10046471a`
- `KERNEL32!FreeLibrary` at `0x10046471a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall XE_StaticPackage<1>::GetLocalizedString(
        __int64 a1,
        int a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5)
{
  __int64 v8; // r14
  unsigned int v9; // edi
  int v10; // esi
  int v11; // eax
  BOOL v12; // r15d
  HMODULE Library; // rsi
  HMODULE v14; // rcx
  __int64 v16; // [rsp+20h] [rbp-298h]
  WCHAR LibFileName[264]; // [rsp+50h] [rbp-268h] BYREF

  v8 = *(_QWORD *)(a1 + 560);
  v9 = 0;
  v10 = 0;
  v11 = qword_100714F50(v8, 0xFFFFFFFFLL, 0);
  v12 = v11 == 0;
  if ( !v11 )
  {
    Library = 0;
    if ( *(_DWORD *)(a1 + 544) == a2 )
    {
      Library = *(HMODULE *)(a1 + 552);
LABEL_12:
      v10 = (*(__int64 (__fastcall **)(HMODULE, _QWORD, __int64, _QWORD))(a1 + 568))(Library, a3, a4, a5);
      goto LABEL_13;
    }
    v14 = *(HMODULE *)(a1 + 552);
    if ( v14 )
    {
      FreeLibrary(v14);
      *(_DWORD *)(a1 + 544) = 0;
      *(_QWORD *)(a1 + 552) = 0;
    }
    LibFileName[0] = 0;
    if ( (int)StringCchPrintfW(
                LibFileName,
                0x104u,
                L"%s\\%d\\%s",
                a1 + 24,
                a2,
                *(_QWORD *)(**(_QWORD **)(a1 + 8) + 48LL)) < 0
      || (Library = LoadLibraryExW(LibFileName, 0, 0x22u)) == 0 )
    {
      LODWORD(v16) = 1033;
      if ( (int)StringCchPrintfW(
                  LibFileName,
                  0x104u,
                  L"%s\\%d\\%s",
                  a1 + 24,
                  v16,
                  *(_QWORD *)(**(_QWORD **)(a1 + 8) + 48LL)) < 0 )
      {
LABEL_11:
        *(_QWORD *)(a1 + 552) = Library;
        goto LABEL_12;
      }
      Library = LoadLibraryExW(LibFileName, 0, 0x22u);
    }
    *(_DWORD *)(a1 + 544) = a2;
    goto LABEL_11;
  }
LABEL_13:
  if ( v12 )
    qword_100714F58(v8);
  LOBYTE(v9) = v10 > 0;
  return v9;
}

```

## disassembly

```asm
0x100464680  push    rbx
0x100464682  push    rbp
0x100464683  push    rsi
0x100464684  push    rdi
0x100464685  push    r12
0x100464687  push    r13
0x100464689  push    r14
0x10046468b  push    r15
0x10046468d  sub     rsp, 278h
0x100464694  mov     [rsp+2B8h+var_270], 0FFFFFFFFFFFFFFFEh
0x10046469d  mov     rax, cs:__security_cookie
0x1004646a4  xor     rax, rsp
0x1004646a7  mov     [rsp+2B8h+var_58], rax
0x1004646af  mov     [rsp+2B8h+var_288], r9
0x1004646b4  mov     r13d, r8d
0x1004646b7  mov     ebp, edx
0x1004646b9  mov     rbx, rcx
0x1004646bc  mov     r14, [rcx+230h]
0x1004646c3  mov     [rsp+2B8h+var_280], r14
0x1004646c8  xor     edi, edi
0x1004646ca  mov     [rsp+2B8h+var_278], rdi
0x1004646cf  mov     esi, edi
0x1004646d1  xor     r8d, r8d
0x1004646d4  mov     edx, 0FFFFFFFFh
0x1004646d9  mov     rcx, r14
0x1004646dc  call    cs:qword_100714F50
0x1004646e2  mov     r15d, edi
0x1004646e5  test    eax, eax
0x1004646e7  setz    r15b
0x1004646eb  mov     dword ptr [rsp+2B8h+var_278], r15d
0x1004646f0  test    eax, eax
0x1004646f2  jnz     loc_1004647EF
0x1004646f8  mov     esi, edi
0x1004646fa  cmp     [rbx+220h], ebp
0x100464700  jnz     short loc_10046470E
0x100464702  mov     rsi, [rbx+228h]
0x100464709  jmp     loc_1004647D4
0x10046470e  mov     rcx, [rbx+228h]; hLibModule
0x100464715  test    rcx, rcx
0x100464718  jz      short loc_10046472D
0x10046471a  call    cs:__imp_FreeLibrary
0x100464720  mov     [rbx+220h], edi
0x100464726  mov     [rbx+228h], rdi
0x10046472d  mov     [rsp+2B8h+LibFileName], di
0x100464732  mov     rax, [rbx+8]
0x100464736  mov     rcx, [rax]
0x100464739  mov     rax, [rcx+30h]
0x10046473d  mov     [rsp+2B8h+var_290], rax
0x100464742  mov     dword ptr [rsp+2B8h+var_298], ebp
0x100464746  lea     r9, [rbx+18h]
0x10046474a  lea     r8, aSDS; "%s\\%d\\%s"
0x100464751  mov     edx, 104h; unsigned __int64
0x100464756  lea     rcx, [rsp+2B8h+LibFileName]; Buffer
0x10046475b  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x100464760  test    eax, eax
0x100464762  js      short loc_10046477D
0x100464764  xor     edx, edx; hFile
0x100464766  lea     r8d, [rdx+22h]; dwFlags
0x10046476a  lea     rcx, [rsp+2B8h+LibFileName]; lpLibFileName
0x10046476f  call    cs:__imp_LoadLibraryExW
0x100464775  mov     rsi, rax
0x100464778  test    rax, rax
0x10046477b  jnz     short loc_1004647C7
0x10046477d  mov     rax, [rbx+8]
0x100464781  mov     rcx, [rax]
0x100464784  mov     rax, [rcx+30h]
0x100464788  mov     [rsp+2B8h+var_290], rax
0x10046478d  mov     dword ptr [rsp+2B8h+var_298], 409h
0x100464795  lea     r9, [rbx+18h]
0x100464799  lea     r8, aSDS; "%s\\%d\\%s"
0x1004647a0  mov     edx, 104h; unsigned __int64
0x1004647a5  lea     rcx, [rsp+2B8h+LibFileName]; Buffer
0x1004647aa  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1004647af  test    eax, eax
0x1004647b1  js      short loc_1004647CD
0x1004647b3  xor     edx, edx; hFile
0x1004647b5  lea     r8d, [rdx+22h]; dwFlags
0x1004647b9  lea     rcx, [rsp+2B8h+LibFileName]; lpLibFileName
0x1004647be  call    cs:__imp_LoadLibraryExW
0x1004647c4  mov     rsi, rax
0x1004647c7  mov     [rbx+220h], ebp
0x1004647cd  mov     [rbx+228h], rsi
0x1004647d4  mov     r9d, [rsp+2B8h+arg_20]
0x1004647dc  mov     r8, [rsp+2B8h+var_288]
0x1004647e1  mov     edx, r13d
0x1004647e4  mov     rcx, rsi
0x1004647e7  call    qword ptr [rbx+238h]
0x1004647ed  mov     esi, eax
0x1004647ef  test    esi, esi
0x1004647f1  setnle  dil
0x1004647f5  test    r15d, r15d
0x1004647f8  jz      short loc_100464803
0x1004647fa  mov     rcx, r14
0x1004647fd  call    cs:qword_100714F58
0x100464803  mov     eax, edi
0x100464805  mov     rcx, [rsp+2B8h+var_58]
0x10046480d  xor     rcx, rsp; StackCookie
0x100464810  call    __security_check_cookie
0x100464815  add     rsp, 278h
0x10046481c  pop     r15
0x10046481e  pop     r14
0x100464820  pop     r13
0x100464822  pop     r12
0x100464824  pop     rdi
0x100464825  pop     rsi
0x100464826  pop     rbp
0x100464827  pop     rbx
0x100464828  retn
```
