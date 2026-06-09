# CWordMatch::_PutWordMatch(ulong,ushort const *,ulong,ulong)

- ea: `0x18007f360`
- end: `0x18007f4f9`
- name: `?_PutWordMatch@CWordMatch@@AEAAJKPEBGKK@Z`
- size: `409`
- prototype: `int(CWordMatch *__hidden this, unsigned int, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18007bd00`
- `0x18007bd10`

## callees

- `0x1800366cc`
- `0x180078c80`
- `0x18007f360`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18007f4d3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18007f4d3`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18007f445`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18007f498`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18007f445`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x18007f498`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f3f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f459`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f3f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f459`

## pseudocode

```c
__int64 __fastcall CWordMatch::_PutWordMatch(CWordMatch *this, __int64 a2, const unsigned __int16 *a3)
{
  __int64 result; // rax
  __int64 v6; // rcx
  int v7; // ebx
  const WCHAR *lpStringValue; // rcx
  __int64 v9; // r9
  __int64 cchValue; // rax
  WCHAR *v11; // rbx
  __int64 v12; // r9
  const WCHAR *v13; // r8
  __int64 v14; // r9
  LPCWSTR lpStringSource; // [rsp+40h] [rbp-18h] BYREF

  result = 1;
  if ( !*((_DWORD *)this + 136) )
  {
    v6 = (unsigned int)(*((_DWORD *)this + 137) - 12);
    if ( (_DWORD)v6 )
    {
      if ( (_DWORD)v6 == 1 )
      {
        if ( *((_QWORD *)this + 67) )
        {
          lpStringSource = 0;
          if ( (int)_AllocStringWorker<CTCoAllocPolicy>(v6, a2, a3, (unsigned int)a2) >= 0 )
          {
            v7 = CKoreanDecomposition::DecomposeKoreanForPrefixMatch(
                   (CKoreanDecomposition *)g_koreanDecomposition,
                   0,
                   (unsigned __int16 **)&lpStringSource);
            CoTaskMemFree(0);
            if ( v7 >= 0 )
            {
              lpStringValue = (const WCHAR *)*((_QWORD *)this + 67);
              v9 = -1;
              cchValue = -1;
              do
                ++cchValue;
              while ( lpStringValue[cchValue] );
              v11 = (WCHAR *)lpStringSource;
              do
                ++v9;
              while ( lpStringSource[v9] );
              *((_DWORD *)this + 136) = FindNLSString(
                                          *((_DWORD *)this + 138),
                                          *((_DWORD *)this + 139) | 0x100000,
                                          lpStringSource,
                                          v9,
                                          lpStringValue,
                                          cchValue,
                                          0) >= 0;
              CoTaskMemFree(v11);
            }
          }
        }
        else
        {
          v12 = -1;
          do
            ++v12;
          while ( *((_WORD *)this + v12 + 6) );
          *((_DWORD *)this + 136) = FindNLSString(
                                      *((_DWORD *)this + 138),
                                      *((_DWORD *)this + 139) | 0x100000,
                                      a3,
                                      a2,
                                      (LPCWSTR)this + 6,
                                      v12,
                                      0) >= 0;
        }
      }
    }
    else
    {
      v13 = (const WCHAR *)((char *)this + 12);
      v14 = -1;
      do
        ++v14;
      while ( v13[v14] );
      *((_DWORD *)this + 136) = CompareStringW(*((_DWORD *)this + 138), *((_DWORD *)this + 139), v13, v14, a3, a2) == 2;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18007f360  mov     [rsp+arg_8], rbx
0x18007f365  mov     [rsp+arg_10], rsi
0x18007f36a  push    rdi
0x18007f36b  sub     rsp, 50h
0x18007f36f  xor     esi, esi
0x18007f371  mov     r11d, edx
0x18007f374  mov     r10, r8
0x18007f377  mov     rdi, rcx
0x18007f37a  mov     eax, 1
0x18007f37f  cmp     [rcx+220h], esi
0x18007f385  jnz     loc_18007F4E9
0x18007f38b  mov     ecx, [rcx+224h]
0x18007f391  sub     ecx, 0Ch
0x18007f394  jz      loc_18007F4AB
0x18007f39a  cmp     ecx, eax
0x18007f39c  jnz     loc_18007F4E7
0x18007f3a2  cmp     [rdi+218h], rsi
0x18007f3a9  jz      loc_18007F464
0x18007f3af  lea     rax, [rsp+58h+pv]
0x18007f3b4  mov     [rsp+58h+lpStringSource], rsi
0x18007f3b9  mov     r9d, r11d
0x18007f3bc  mov     qword ptr [rsp+58h+cchValue], rax
0x18007f3c1  mov     [rsp+58h+pv], rsi
0x18007f3c6  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18007f3cb  test    eax, eax
0x18007f3cd  js      loc_18007F4E7
0x18007f3d3  mov     rdx, [rsp+58h+pv]; unsigned __int16 *
0x18007f3d8  lea     r8, [rsp+58h+lpStringSource]; unsigned __int16 **
0x18007f3dd  lea     rcx, ?g_koreanDecomposition@@3VCKoreanDecomposition@@A; this
0x18007f3e4  call    ?DecomposeKoreanForPrefixMatch@CKoreanDecomposition@@QEAAJPEBGPEAPEAG@Z; CKoreanDecomposition::DecomposeKoreanForPrefixMatch(ushort const *,ushort * *)
0x18007f3e9  mov     rcx, [rsp+58h+pv]; pv
0x18007f3ee  mov     ebx, eax
0x18007f3f0  call    cs:__imp_CoTaskMemFree
0x18007f3f6  test    ebx, ebx
0x18007f3f8  js      loc_18007F4E7
0x18007f3fe  mov     rcx, [rdi+218h]
0x18007f405  or      r9, 0FFFFFFFFFFFFFFFFh
0x18007f409  mov     rax, r9
0x18007f40c  inc     rax
0x18007f40f  cmp     [rcx+rax*2], si
0x18007f413  jnz     short loc_18007F40C
0x18007f415  mov     rbx, [rsp+58h+lpStringSource]
0x18007f41a  inc     r9; cchSource
0x18007f41d  cmp     [rbx+r9*2], si
0x18007f422  jnz     short loc_18007F41A
0x18007f424  mov     edx, [rdi+22Ch]
0x18007f42a  mov     r8, rbx; lpStringSource
0x18007f42d  mov     [rsp+58h+pcchFound], rsi; pcchFound
0x18007f432  bts     edx, 14h; dwFindNLSStringFlags
0x18007f436  mov     [rsp+58h+cchValue], eax; cchValue
0x18007f43a  mov     [rsp+58h+lpStringValue], rcx; lpStringValue
0x18007f43f  mov     ecx, [rdi+228h]; Locale
0x18007f445  call    cs:__imp_FindNLSString
0x18007f44b  not     eax
0x18007f44d  mov     rcx, rbx; pv
0x18007f450  shr     eax, 1Fh
0x18007f453  mov     [rdi+220h], eax
0x18007f459  call    cs:__imp_CoTaskMemFree
0x18007f45f  jmp     loc_18007F4E7
0x18007f464  lea     rax, [rdi+0Ch]
0x18007f468  or      r9, 0FFFFFFFFFFFFFFFFh
0x18007f46c  inc     r9
0x18007f46f  cmp     [rax+r9*2], si
0x18007f474  jnz     short loc_18007F46C
0x18007f476  mov     edx, [rdi+22Ch]
0x18007f47c  mov     ecx, [rdi+228h]; Locale
0x18007f482  bts     edx, 14h; dwFindNLSStringFlags
0x18007f486  mov     [rsp+58h+pcchFound], rsi; pcchFound
0x18007f48b  mov     [rsp+58h+cchValue], r9d; cchValue
0x18007f490  mov     r9d, r11d; cchSource
0x18007f493  mov     [rsp+58h+lpStringValue], rax; lpStringValue
0x18007f498  call    cs:__imp_FindNLSString
0x18007f49e  not     eax
0x18007f4a0  shr     eax, 1Fh
0x18007f4a3  mov     [rdi+220h], eax
0x18007f4a9  jmp     short loc_18007F4E7
0x18007f4ab  lea     r8, [rdi+0Ch]; lpString1
0x18007f4af  or      r9, 0FFFFFFFFFFFFFFFFh
0x18007f4b3  inc     r9; cchCount1
0x18007f4b6  cmp     [r8+r9*2], si
0x18007f4bb  jnz     short loc_18007F4B3
0x18007f4bd  mov     edx, [rdi+22Ch]; dwCmpFlags
0x18007f4c3  mov     ecx, [rdi+228h]; Locale
0x18007f4c9  mov     [rsp+58h+cchValue], r11d; cchCount2
0x18007f4ce  mov     [rsp+58h+lpStringValue], r10; lpString2
0x18007f4d3  call    cs:__imp_CompareStringW
0x18007f4d9  mov     ecx, esi
0x18007f4db  cmp     eax, 2
0x18007f4de  setz    cl
0x18007f4e1  mov     [rdi+220h], ecx
0x18007f4e7  mov     eax, esi
0x18007f4e9  mov     rbx, [rsp+58h+arg_8]
0x18007f4ee  mov     rsi, [rsp+58h+arg_10]
0x18007f4f3  add     rsp, 50h
0x18007f4f7  pop     rdi
0x18007f4f8  retn
```
