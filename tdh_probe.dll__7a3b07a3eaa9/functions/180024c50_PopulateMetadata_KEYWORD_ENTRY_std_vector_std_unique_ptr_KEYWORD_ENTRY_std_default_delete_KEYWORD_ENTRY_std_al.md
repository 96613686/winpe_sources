# PopulateMetadata<KEYWORD_ENTRY>(std::vector<std::unique_ptr<KEYWORD_ENTRY,std::default_delete<KEYWORD_ENTRY>>,std::allocator<std::unique_ptr<KEYWORD_ENTRY,std::default_delete<KEYWORD_ENTRY>>>> &,_EVENT_FIELD_TYPE,TDH_MOF_INFO *)

- ea: `0x180024c50`
- end: `0x180024e04`
- name: `??$PopulateMetadata@VKEYWORD_ENTRY@@@@YAKAEAV?$vector@V?$unique_ptr@VKEYWORD_ENTRY@@U?$default_delete@VKEYWORD_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VKEYWORD_ENTRY@@U?$default_delete@VKEYWORD_ENTRY@@@std@@@std@@@2@@std@@W4_EVENT_FIELD_TYPE@@PEAUTDH_MOF_INFO@@@Z`
- size: `436`
- prototype: `__int64 __fastcall(const wchar_t ***, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180025b8c`

## callees

- `0x18000b9d0`
- `0x180012f34`
- `0x1800137e8`
- `0x180018350`
- `0x180024c50`
- `0x180037138`
- `0x180037160`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180024cae`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180024d2e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180024d92`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180024cae`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180024d2e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180024d92`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024c9d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024d1d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024d81`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024c9d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024d1d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024d81`

## pseudocode

```c
__int64 __fastcall PopulateMetadata<KEYWORD_ENTRY>(const wchar_t ***a1, __int64 a2, __int64 a3)
{
  struct FIELD_INFOLIST *v4; // r13
  unsigned int *v5; // rdi
  unsigned __int64 v6; // rcx
  HANDLE ProcessHeap; // rax
  LPVOID v8; // rax
  unsigned int v9; // esi
  unsigned __int64 v10; // r14
  const wchar_t **i; // rbx
  __int64 v12; // rbp
  __int64 v13; // r15
  unsigned int v14; // edi
  HANDLE v15; // rax
  wchar_t *v16; // rax
  const wchar_t *v17; // r8
  unsigned int v18; // edi
  HANDLE v19; // rax
  LPVOID v20; // rax
  const wchar_t *TranslationValue; // rax
  wchar_t *v22; // r9
  const wchar_t *v23; // rax
  SIZE_T dwBytes; // [rsp+70h] [rbp+8h] BYREF

  v4 = (struct FIELD_INFOLIST *)(a3 + 6192);
  v5 = (unsigned int *)(a3 + 6200);
  *(_DWORD *)(a3 + 6200) = 0;
  *(_QWORD *)(a3 + 6192) = 0;
  v6 = a1[1] - *a1;
  dwBytes = 0;
  if ( (int)ULongLongMult(v6, 0x28u, &dwBytes) < 0 )
    return 8;
  ProcessHeap = GetProcessHeap();
  v8 = HeapAlloc(ProcessHeap, 8u, dwBytes);
  *(_QWORD *)v4 = v8;
  if ( !v8 )
    return 8;
  if ( (int)ULongLongToULong(a1[1] - *a1, v5) < 0 )
  {
LABEL_16:
    v9 = 8;
    TdhpClearFieldInfoList(v4);
  }
  else
  {
    v9 = 0;
    v10 = 0;
    for ( i = *a1; v10 < *v5 && i != a1[1]; ++i )
    {
      v12 = 5 * v10;
      v13 = *(_QWORD *)v4;
      if ( *((_QWORD *)*i + 2) )
      {
        v14 = 2 * *((_DWORD *)*i + 4) + 2;
        *(_DWORD *)(v13 + 40 * v10 + 16) = v14;
        v15 = GetProcessHeap();
        v16 = (wchar_t *)HeapAlloc(v15, 8u, v14);
        *(_QWORD *)(v13 + 40 * v10) = v16;
        if ( !v16 )
          goto LABEL_16;
        v17 = *i;
        if ( *((_QWORD *)*i + 3) > 7u )
          v17 = *(const wchar_t **)v17;
        StringCbCopyW(v16, *(unsigned int *)(v13 + 40 * v10 + 16), v17);
      }
      if ( *((_QWORD *)*i + 14) )
      {
        *(_DWORD *)(v13 + 40 * v10 + 24) = 0;
        v18 = 2 * STRING_ENTRY::FirstTranslationValueLength(*((STRING_ENTRY **)*i + 14)) + 2;
        *(_DWORD *)(v13 + 40 * v10 + 20) = v18;
        v19 = GetProcessHeap();
        v20 = HeapAlloc(v19, 8u, v18);
        *(_QWORD *)(v13 + 40 * v10 + 8) = v20;
        if ( !v20 )
          goto LABEL_16;
        TranslationValue = STRING_ENTRY::FirstTranslationValue(*((STRING_ENTRY **)*i + 14));
        StringCbCopyW(v22, *(unsigned int *)(v13 + 40 * v10 + 20), TranslationValue);
      }
      v23 = *i;
      v5 = (unsigned int *)((char *)v4 + 8);
      ++v10;
      *(_QWORD *)(v13 + 8 * v12 + 32) = *((_QWORD *)v23 + 4);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x180024c50  push    rbx
0x180024c52  push    rbp
0x180024c53  push    rsi
0x180024c54  push    rdi
0x180024c55  push    r12
0x180024c57  push    r13
0x180024c59  push    r14
0x180024c5b  push    r15
0x180024c5d  sub     rsp, 28h
0x180024c61  mov     r12, rcx
0x180024c64  lea     r13, [r8+1830h]
0x180024c6b  xor     ebx, ebx
0x180024c6d  lea     rdi, [r13+8]
0x180024c71  mov     [rdi], ebx
0x180024c73  lea     r8, [rsp+68h+dwBytes]; unsigned __int64 *
0x180024c78  mov     [r13+0], rbx
0x180024c7c  mov     rcx, [rcx+8]
0x180024c80  sub     rcx, [r12]
0x180024c84  lea     edx, [rbx+28h]; unsigned __int64
0x180024c87  sar     rcx, 3; unsigned __int64
0x180024c8b  mov     [rsp+68h+dwBytes], rbx
0x180024c90  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180024c95  test    eax, eax
0x180024c97  js      loc_180024DEE
0x180024c9d  call    cs:__imp_GetProcessHeap
0x180024ca3  mov     r8, [rsp+68h+dwBytes]; dwBytes
0x180024ca8  lea     edx, [rbx+8]; dwFlags
0x180024cab  mov     rcx, rax; hHeap
0x180024cae  call    cs:__imp_HeapAlloc
0x180024cb4  mov     [r13+0], rax
0x180024cb8  test    rax, rax
0x180024cbb  jz      loc_180024DEE
0x180024cc1  mov     rcx, [r12+8]
0x180024cc6  mov     rdx, rdi; unsigned int *
0x180024cc9  sub     rcx, [r12]
0x180024ccd  sar     rcx, 3; unsigned __int64
0x180024cd1  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180024cd6  test    eax, eax
0x180024cd8  js      loc_180024DDD
0x180024cde  mov     esi, ebx
0x180024ce0  mov     r14d, ebx
0x180024ce3  mov     rbx, [r12]
0x180024ce7  mov     eax, [rdi]
0x180024ce9  cmp     r14, rax
0x180024cec  jnb     loc_180024DEA
0x180024cf2  cmp     rbx, [r12+8]
0x180024cf7  jz      loc_180024DEA
0x180024cfd  mov     rax, [rbx]
0x180024d00  lea     rbp, [r14+r14*4]
0x180024d04  mov     r15, [r13+0]
0x180024d08  cmp     [rax+10h], rsi
0x180024d0c  jz      short loc_180024D5B
0x180024d0e  mov     eax, [rax+10h]
0x180024d11  lea     edi, ds:2[rax*2]
0x180024d18  mov     [r15+rbp*8+10h], edi
0x180024d1d  call    cs:__imp_GetProcessHeap
0x180024d23  mov     r8d, edi; dwBytes
0x180024d26  mov     edx, 8; dwFlags
0x180024d2b  mov     rcx, rax; hHeap
0x180024d2e  call    cs:__imp_HeapAlloc
0x180024d34  mov     [r15+rbp*8], rax
0x180024d38  test    rax, rax
0x180024d3b  jz      loc_180024DDD
0x180024d41  mov     r8, [rbx]
0x180024d44  cmp     qword ptr [r8+18h], 7
0x180024d49  jbe     short loc_180024D4E
0x180024d4b  mov     r8, [r8]; wchar_t *
0x180024d4e  mov     edx, [r15+rbp*8+10h]; unsigned __int64
0x180024d53  mov     rcx, rax; wchar_t *
0x180024d56  call    ?StringCbCopyW@@YAJPEA_W_KPEB_W@Z; StringCbCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180024d5b  mov     rax, [rbx]
0x180024d5e  cmp     [rax+70h], rsi
0x180024d62  jz      short loc_180024DC1
0x180024d64  mov     [r15+rbp*8+18h], esi
0x180024d69  mov     rcx, [rbx]
0x180024d6c  mov     rcx, [rcx+70h]; this
0x180024d70  call    ?FirstTranslationValueLength@STRING_ENTRY@@QEBA_KXZ; STRING_ENTRY::FirstTranslationValueLength(void)
0x180024d75  lea     edi, ds:2[rax*2]
0x180024d7c  mov     [r15+rbp*8+14h], edi
0x180024d81  call    cs:__imp_GetProcessHeap
0x180024d87  mov     r8d, edi; dwBytes
0x180024d8a  mov     edx, 8; dwFlags
0x180024d8f  mov     rcx, rax; hHeap
0x180024d92  call    cs:__imp_HeapAlloc
0x180024d98  mov     [r15+rbp*8+8], rax
0x180024d9d  mov     r9, rax
0x180024da0  test    rax, rax
0x180024da3  jz      short loc_180024DDD
0x180024da5  mov     rcx, [rbx]
0x180024da8  mov     rcx, [rcx+70h]; this
0x180024dac  call    ?FirstTranslationValue@STRING_ENTRY@@QEBAPEB_WXZ; STRING_ENTRY::FirstTranslationValue(void)
0x180024db1  mov     edx, [r15+rbp*8+14h]; unsigned __int64
0x180024db6  mov     r8, rax; wchar_t *
0x180024db9  mov     rcx, r9; wchar_t *
0x180024dbc  call    ?StringCbCopyW@@YAJPEA_W_KPEB_W@Z; StringCbCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180024dc1  mov     rax, [rbx]
0x180024dc4  lea     rdi, [r13+8]
0x180024dc8  inc     r14
0x180024dcb  add     rbx, 8
0x180024dcf  mov     rcx, [rax+20h]
0x180024dd3  mov     [r15+rbp*8+20h], rcx
0x180024dd8  jmp     loc_180024CE7
0x180024ddd  mov     esi, 8
0x180024de2  mov     rcx, r13; struct FIELD_INFOLIST *
0x180024de5  call    ?TdhpClearFieldInfoList@@YAXPEAUFIELD_INFOLIST@@@Z; TdhpClearFieldInfoList(FIELD_INFOLIST *)
0x180024dea  mov     eax, esi
0x180024dec  jmp     short loc_180024DF3
0x180024dee  mov     eax, 8
0x180024df3  add     rsp, 28h
0x180024df7  pop     r15
0x180024df9  pop     r14
0x180024dfb  pop     r13
0x180024dfd  pop     r12
0x180024dff  pop     rdi
0x180024e00  pop     rsi
0x180024e01  pop     rbp
0x180024e02  pop     rbx
0x180024e03  retn
```
