# PopulateMetadata<LEVEL_ENTRY>(std::vector<std::unique_ptr<LEVEL_ENTRY,std::default_delete<LEVEL_ENTRY>>,std::allocator<std::unique_ptr<LEVEL_ENTRY,std::default_delete<LEVEL_ENTRY>>>> &,_EVENT_FIELD_TYPE,TDH_MOF_INFO *)

- ea: `0x180024e0c`
- end: `0x180024fc0`
- name: `??$PopulateMetadata@VLEVEL_ENTRY@@@@YAKAEAV?$vector@V?$unique_ptr@VLEVEL_ENTRY@@U?$default_delete@VLEVEL_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VLEVEL_ENTRY@@U?$default_delete@VLEVEL_ENTRY@@@std@@@std@@@2@@std@@W4_EVENT_FIELD_TYPE@@PEAUTDH_MOF_INFO@@@Z`
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
- `0x180024e0c`
- `0x180037138`
- `0x180037160`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180024e6a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180024eea`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180024f4e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180024e6a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180024eea`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180024f4e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024e59`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024ed9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024f3d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024e59`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024ed9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024f3d`

## pseudocode

```c
__int64 __fastcall PopulateMetadata<LEVEL_ENTRY>(const wchar_t ***a1, __int64 a2, __int64 a3)
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

  v4 = (struct FIELD_INFOLIST *)(a3 + 6208);
  v5 = (unsigned int *)(a3 + 6216);
  *(_DWORD *)(a3 + 6216) = 0;
  *(_QWORD *)(a3 + 6208) = 0;
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
      *(_QWORD *)(v13 + 8 * v12 + 32) = *((unsigned __int8 *)v23 + 32);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x180024e0c  push    rbx
0x180024e0e  push    rbp
0x180024e0f  push    rsi
0x180024e10  push    rdi
0x180024e11  push    r12
0x180024e13  push    r13
0x180024e15  push    r14
0x180024e17  push    r15
0x180024e19  sub     rsp, 28h
0x180024e1d  mov     r12, rcx
0x180024e20  lea     r13, [r8+1840h]
0x180024e27  xor     ebx, ebx
0x180024e29  lea     rdi, [r13+8]
0x180024e2d  mov     [rdi], ebx
0x180024e2f  lea     r8, [rsp+68h+dwBytes]; unsigned __int64 *
0x180024e34  mov     [r13+0], rbx
0x180024e38  mov     rcx, [rcx+8]
0x180024e3c  sub     rcx, [r12]
0x180024e40  lea     edx, [rbx+28h]; unsigned __int64
0x180024e43  sar     rcx, 3; unsigned __int64
0x180024e47  mov     [rsp+68h+dwBytes], rbx
0x180024e4c  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180024e51  test    eax, eax
0x180024e53  js      loc_180024FAA
0x180024e59  call    cs:__imp_GetProcessHeap
0x180024e5f  mov     r8, [rsp+68h+dwBytes]; dwBytes
0x180024e64  lea     edx, [rbx+8]; dwFlags
0x180024e67  mov     rcx, rax; hHeap
0x180024e6a  call    cs:__imp_HeapAlloc
0x180024e70  mov     [r13+0], rax
0x180024e74  test    rax, rax
0x180024e77  jz      loc_180024FAA
0x180024e7d  mov     rcx, [r12+8]
0x180024e82  mov     rdx, rdi; unsigned int *
0x180024e85  sub     rcx, [r12]
0x180024e89  sar     rcx, 3; unsigned __int64
0x180024e8d  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180024e92  test    eax, eax
0x180024e94  js      loc_180024F99
0x180024e9a  mov     esi, ebx
0x180024e9c  mov     r14d, ebx
0x180024e9f  mov     rbx, [r12]
0x180024ea3  mov     eax, [rdi]
0x180024ea5  cmp     r14, rax
0x180024ea8  jnb     loc_180024FA6
0x180024eae  cmp     rbx, [r12+8]
0x180024eb3  jz      loc_180024FA6
0x180024eb9  mov     rax, [rbx]
0x180024ebc  lea     rbp, [r14+r14*4]
0x180024ec0  mov     r15, [r13+0]
0x180024ec4  cmp     [rax+10h], rsi
0x180024ec8  jz      short loc_180024F17
0x180024eca  mov     eax, [rax+10h]
0x180024ecd  lea     edi, ds:2[rax*2]
0x180024ed4  mov     [r15+rbp*8+10h], edi
0x180024ed9  call    cs:__imp_GetProcessHeap
0x180024edf  mov     r8d, edi; dwBytes
0x180024ee2  mov     edx, 8; dwFlags
0x180024ee7  mov     rcx, rax; hHeap
0x180024eea  call    cs:__imp_HeapAlloc
0x180024ef0  mov     [r15+rbp*8], rax
0x180024ef4  test    rax, rax
0x180024ef7  jz      loc_180024F99
0x180024efd  mov     r8, [rbx]
0x180024f00  cmp     qword ptr [r8+18h], 7
0x180024f05  jbe     short loc_180024F0A
0x180024f07  mov     r8, [r8]; wchar_t *
0x180024f0a  mov     edx, [r15+rbp*8+10h]; unsigned __int64
0x180024f0f  mov     rcx, rax; wchar_t *
0x180024f12  call    ?StringCbCopyW@@YAJPEA_W_KPEB_W@Z; StringCbCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180024f17  mov     rax, [rbx]
0x180024f1a  cmp     [rax+70h], rsi
0x180024f1e  jz      short loc_180024F7D
0x180024f20  mov     [r15+rbp*8+18h], esi
0x180024f25  mov     rcx, [rbx]
0x180024f28  mov     rcx, [rcx+70h]; this
0x180024f2c  call    ?FirstTranslationValueLength@STRING_ENTRY@@QEBA_KXZ; STRING_ENTRY::FirstTranslationValueLength(void)
0x180024f31  lea     edi, ds:2[rax*2]
0x180024f38  mov     [r15+rbp*8+14h], edi
0x180024f3d  call    cs:__imp_GetProcessHeap
0x180024f43  mov     r8d, edi; dwBytes
0x180024f46  mov     edx, 8; dwFlags
0x180024f4b  mov     rcx, rax; hHeap
0x180024f4e  call    cs:__imp_HeapAlloc
0x180024f54  mov     [r15+rbp*8+8], rax
0x180024f59  mov     r9, rax
0x180024f5c  test    rax, rax
0x180024f5f  jz      short loc_180024F99
0x180024f61  mov     rcx, [rbx]
0x180024f64  mov     rcx, [rcx+70h]; this
0x180024f68  call    ?FirstTranslationValue@STRING_ENTRY@@QEBAPEB_WXZ; STRING_ENTRY::FirstTranslationValue(void)
0x180024f6d  mov     edx, [r15+rbp*8+14h]; unsigned __int64
0x180024f72  mov     r8, rax; wchar_t *
0x180024f75  mov     rcx, r9; wchar_t *
0x180024f78  call    ?StringCbCopyW@@YAJPEA_W_KPEB_W@Z; StringCbCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180024f7d  mov     rax, [rbx]
0x180024f80  lea     rdi, [r13+8]
0x180024f84  inc     r14
0x180024f87  add     rbx, 8
0x180024f8b  movzx   ecx, byte ptr [rax+20h]
0x180024f8f  mov     [r15+rbp*8+20h], rcx
0x180024f94  jmp     loc_180024EA3
0x180024f99  mov     esi, 8
0x180024f9e  mov     rcx, r13; struct FIELD_INFOLIST *
0x180024fa1  call    ?TdhpClearFieldInfoList@@YAXPEAUFIELD_INFOLIST@@@Z; TdhpClearFieldInfoList(FIELD_INFOLIST *)
0x180024fa6  mov     eax, esi
0x180024fa8  jmp     short loc_180024FAF
0x180024faa  mov     eax, 8
0x180024faf  add     rsp, 28h
0x180024fb3  pop     r15
0x180024fb5  pop     r14
0x180024fb7  pop     r13
0x180024fb9  pop     r12
0x180024fbb  pop     rdi
0x180024fbc  pop     rsi
0x180024fbd  pop     rbp
0x180024fbe  pop     rbx
0x180024fbf  retn
```
