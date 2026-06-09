# pSetUILanguage

- ea: `0x18000859c`
- end: `0x1800086bb`
- name: `pSetUILanguage`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800087e0`

## callees

- `0x180005da4`
- `0x18000720c`
- `0x18000859c`
- `0x18000a624`
- `0x18000bca4`
- `0x180021ed8`
- `0x1800274de`
- `0x180027510`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000868d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800281f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000868d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800281f3`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x180008679`
- `api-ms-win-core-localization-l1-2-0!SetThreadPreferredUILanguages` at `0x180008679`

## pseudocode

```c
void __fastcall pSetUILanguage(__int64 a1, struct CONTENTS_FILE **a2)
{
  __int64 v4; // rdx
  struct CONTENTS_FILE *v5; // rcx
  struct CONTENTS_FILE *v6; // rax
  __int64 v7; // rdx
  int v8; // r9d
  int v9; // r8d
  const wchar_t *v10; // rax
  ULONG pulNumLanguages; // [rsp+20h] [rbp-238h] BYREF
  __int64 v12; // [rsp+28h] [rbp-230h]
  wchar_t pszDest[264]; // [rsp+30h] [rbp-228h] BYREF

  v12 = a1;
  pulNumLanguages = 0;
  memset_0(pszDest, 0, 0x208u);
  if ( a2 && (unsigned int)IsWorkQueueAccessible(L"pSetUILanguage") )
  {
    pLock(a1);
    v4 = *(_QWORD *)(a1 + 256);
    if ( v4 )
    {
      v5 = *a2;
      if ( !*a2 )
        goto LABEL_9;
      v6 = *a2;
      v7 = v4 - (_QWORD)v5;
      do
      {
        v8 = *(unsigned __int16 *)((char *)v6 + v7);
        v9 = *(unsigned __int16 *)v6 - v8;
        if ( v9 )
          break;
        v6 = (struct CONTENTS_FILE *)((char *)v6 + 2);
      }
      while ( v8 );
      if ( v9 )
      {
LABEL_9:
        pDestructContentsFile(v5);
        v10 = (const wchar_t *)DuplicateTextW(*(unsigned __int16 **)(a1 + 256));
        *a2 = (struct CONTENTS_FILE *)v10;
        if ( v10 )
        {
          if ( StringCchCopyW(pszDest, 0x103u, v10) >= 0 )
            SetThreadPreferredUILanguages(8u, pszDest, &pulNumLanguages);
        }
      }
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 184));
  }
}

```

## disassembly

```asm
0x18000859c  mov     [rsp+arg_10], rbx
0x1800085a1  push    rdi
0x1800085a2  sub     rsp, 250h
0x1800085a9  mov     rax, cs:__security_cookie
0x1800085b0  xor     rax, rsp
0x1800085b3  mov     [rsp+258h+var_18], rax
0x1800085bb  mov     rdi, rdx
0x1800085be  mov     rbx, rcx
0x1800085c1  mov     [rsp+258h+var_230], rcx
0x1800085c6  mov     [rsp+258h+pulNumLanguages], 0
0x1800085ce  xor     edx, edx; Val
0x1800085d0  mov     r8d, 208h; Size
0x1800085d6  lea     rcx, [rsp+258h+pszDest]; void *
0x1800085db  call    memset_0
0x1800085e0  test    rdi, rdi
0x1800085e3  jz      loc_180008699
0x1800085e9  lea     rcx, aPsetuilanguage; "pSetUILanguage"
0x1800085f0  call    IsWorkQueueAccessible
0x1800085f5  test    eax, eax
0x1800085f7  jz      loc_180008699
0x1800085fd  mov     rcx, rbx
0x180008600  call    pLock
0x180008605  mov     rdx, [rbx+100h]
0x18000860c  test    rdx, rdx
0x18000860f  jz      short loc_180008686
0x180008611  mov     rcx, [rdi]; struct CONTENTS_FILE *
0x180008614  test    rcx, rcx
0x180008617  jz      short loc_18000863B
0x180008619  mov     rax, rcx
0x18000861c  sub     rdx, rcx
0x18000861f  movzx   r8d, word ptr [rax]
0x180008623  movzx   r9d, word ptr [rax+rdx]
0x180008628  sub     r8d, r9d
0x18000862b  jnz     short loc_180008636
0x18000862d  add     rax, 2
0x180008631  test    r9d, r9d
0x180008634  jnz     short loc_18000861F
0x180008636  test    r8d, r8d
0x180008639  jz      short loc_180008686
0x18000863b  call    ?pDestructContentsFile@@YAXPEAUCONTENTS_FILE@@@Z; pDestructContentsFile(CONTENTS_FILE *)
0x180008640  mov     rcx, [rbx+100h]; unsigned __int16 *
0x180008647  call    DuplicateTextW
0x18000864c  mov     [rdi], rax
0x18000864f  test    rax, rax
0x180008652  jz      short loc_180008686
0x180008654  mov     r8, rax; pszSrc
0x180008657  mov     edx, 103h; cchDest
0x18000865c  lea     rcx, [rsp+258h+pszDest]; pszDest
0x180008661  call    StringCchCopyW
0x180008666  test    eax, eax
0x180008668  js      short loc_180008686
0x18000866a  lea     r8, [rsp+258h+pulNumLanguages]; pulNumLanguages
0x18000866f  lea     rdx, [rsp+258h+pszDest]; pwszLanguagesBuffer
0x180008674  mov     ecx, 8; dwFlags
0x180008679  call    cs:__imp_SetThreadPreferredUILanguages
0x180008680  nop     dword ptr [rax+rax+00h]
0x180008685  nop
0x180008686  lea     rcx, [rbx+0B8h]; lpCriticalSection
0x18000868d  call    cs:__imp_LeaveCriticalSection
0x180008694  nop     dword ptr [rax+rax+00h]
0x180008699  mov     rcx, [rsp+258h+var_18]
0x1800086a1  xor     rcx, rsp; StackCookie
0x1800086a4  call    __security_check_cookie
0x1800086a9  mov     rbx, [rsp+258h+arg_10]
0x1800086b1  add     rsp, 250h
0x1800086b8  pop     rdi
0x1800086b9  retn
0x1800281df  push    rbp
0x1800281e1  sub     rsp, 20h
0x1800281e5  mov     rbp, rdx
0x1800281e8  mov     rcx, [rbp+28h]
0x1800281ec  add     rcx, 0B8h; lpCriticalSection
0x1800281f3  call    cs:__imp_LeaveCriticalSection
0x1800281fa  nop     dword ptr [rax+rax+00h]
0x1800281ff  nop
0x180028200  add     rsp, 20h
0x180028204  pop     rbp
0x180028205  retn
```
