# PopulateMetadata<OPCODE_ENTRY>(std::vector<std::unique_ptr<OPCODE_ENTRY,std::default_delete<OPCODE_ENTRY>>,std::allocator<std::unique_ptr<OPCODE_ENTRY,std::default_delete<OPCODE_ENTRY>>>> &,_EVENT_FIELD_TYPE,TDH_MOF_INFO *)

- ea: `0x180024fc8`
- end: `0x1800251a0`
- name: `??$PopulateMetadata@VOPCODE_ENTRY@@@@YAKAEAV?$vector@V?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VOPCODE_ENTRY@@U?$default_delete@VOPCODE_ENTRY@@@std@@@std@@@2@@std@@W4_EVENT_FIELD_TYPE@@PEAUTDH_MOF_INFO@@@Z`
- size: `472`
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
- `0x180024fc8`
- `0x180037138`
- `0x180037160`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025026`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800250a6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002510a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025026`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800250a6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002510a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025015`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025095`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800250f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025015`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025095`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800250f9`

## pseudocode

```c
__int64 __fastcall PopulateMetadata<OPCODE_ENTRY>(const wchar_t ***a1, __int64 a2, __int64 a3)
{
  struct FIELD_INFOLIST *v4; // r13
  unsigned int *v5; // rdi
  unsigned __int64 v6; // rcx
  HANDLE ProcessHeap; // rax
  LPVOID v8; // rax
  unsigned int v9; // esi
  unsigned __int64 v10; // r15
  const wchar_t **i; // rbx
  __int64 v12; // r14
  unsigned int v13; // edi
  HANDLE v14; // rax
  wchar_t *v15; // rax
  const wchar_t *v16; // r8
  unsigned int v17; // edi
  HANDLE v18; // rax
  LPVOID v19; // rax
  const wchar_t *TranslationValue; // rax
  wchar_t *v21; // r9
  __int64 v22; // rcx
  const wchar_t *v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rdx
  SIZE_T dwBytes; // [rsp+70h] [rbp+8h] BYREF

  v4 = (struct FIELD_INFOLIST *)(a3 + 6256);
  v5 = (unsigned int *)(a3 + 6264);
  *(_DWORD *)(a3 + 6264) = 0;
  *(_QWORD *)(a3 + 6256) = 0;
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
LABEL_18:
    v9 = 8;
    TdhpClearFieldInfoList(v4);
  }
  else
  {
    v9 = 0;
    v10 = 0;
    for ( i = *a1; v10 < *v5 && i != a1[1]; ++i )
    {
      v12 = *(_QWORD *)v4;
      if ( *((_QWORD *)*i + 2) )
      {
        v13 = 2 * *((_DWORD *)*i + 4) + 2;
        *(_DWORD *)(v12 + 40 * v10 + 16) = v13;
        v14 = GetProcessHeap();
        v15 = (wchar_t *)HeapAlloc(v14, 8u, v13);
        *(_QWORD *)(v12 + 40 * v10) = v15;
        if ( !v15 )
          goto LABEL_18;
        v16 = *i;
        if ( *((_QWORD *)*i + 3) > 7u )
          v16 = *(const wchar_t **)v16;
        StringCbCopyW(v15, *(unsigned int *)(v12 + 40 * v10 + 16), v16);
      }
      if ( *((_QWORD *)*i + 15) )
      {
        *(_DWORD *)(v12 + 40 * v10 + 24) = 0;
        v17 = 2 * STRING_ENTRY::FirstTranslationValueLength(*((STRING_ENTRY **)*i + 15)) + 2;
        *(_DWORD *)(v12 + 40 * v10 + 20) = v17;
        v18 = GetProcessHeap();
        v19 = HeapAlloc(v18, 8u, v17);
        *(_QWORD *)(v12 + 40 * v10 + 8) = v19;
        if ( !v19 )
          goto LABEL_18;
        TranslationValue = STRING_ENTRY::FirstTranslationValue(*((STRING_ENTRY **)*i + 15));
        StringCbCopyW(v21, *(unsigned int *)(v12 + 40 * v10 + 20), TranslationValue);
      }
      v22 = *((unsigned __int8 *)*i + 32);
      *(_QWORD *)(v12 + 40 * v10 + 32) = v22;
      v23 = *i;
      v24 = v22 << 16;
      *(_QWORD *)(v12 + 40 * v10 + 32) = v24;
      v25 = *((_QWORD *)v23 + 16);
      if ( v25 )
        *(_QWORD *)(v12 + 40 * v10 + 32) = v24 | *(unsigned __int16 *)(v25 + 32);
      ++v10;
      v5 = (unsigned int *)((char *)v4 + 8);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x180024fc8  push    rbx
0x180024fca  push    rbp
0x180024fcb  push    rsi
0x180024fcc  push    rdi
0x180024fcd  push    r12
0x180024fcf  push    r13
0x180024fd1  push    r14
0x180024fd3  push    r15
0x180024fd5  sub     rsp, 28h
0x180024fd9  mov     r12, rcx
0x180024fdc  lea     r13, [r8+1870h]
0x180024fe3  xor     ebx, ebx
0x180024fe5  lea     rdi, [r13+8]
0x180024fe9  mov     [rdi], ebx
0x180024feb  lea     r8, [rsp+68h+dwBytes]; unsigned __int64 *
0x180024ff0  mov     [r13+0], rbx
0x180024ff4  mov     rcx, [rcx+8]
0x180024ff8  sub     rcx, [r12]
0x180024ffc  lea     edx, [rbx+28h]; unsigned __int64
0x180024fff  sar     rcx, 3; unsigned __int64
0x180025003  mov     [rsp+68h+dwBytes], rbx
0x180025008  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18002500d  test    eax, eax
0x18002500f  js      loc_18002518A
0x180025015  call    cs:__imp_GetProcessHeap
0x18002501b  mov     r8, [rsp+68h+dwBytes]; dwBytes
0x180025020  lea     edx, [rbx+8]; dwFlags
0x180025023  mov     rcx, rax; hHeap
0x180025026  call    cs:__imp_HeapAlloc
0x18002502c  mov     [r13+0], rax
0x180025030  test    rax, rax
0x180025033  jz      loc_18002518A
0x180025039  mov     rcx, [r12+8]
0x18002503e  mov     rdx, rdi; unsigned int *
0x180025041  sub     rcx, [r12]
0x180025045  sar     rcx, 3; unsigned __int64
0x180025049  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18002504e  test    eax, eax
0x180025050  js      loc_180025179
0x180025056  mov     esi, ebx
0x180025058  mov     r15d, ebx
0x18002505b  mov     rbx, [r12]
0x18002505f  mov     eax, [rdi]
0x180025061  cmp     r15, rax
0x180025064  jnb     loc_180025186
0x18002506a  cmp     rbx, [r12+8]
0x18002506f  jz      loc_180025186
0x180025075  mov     rax, [rbx]
0x180025078  lea     rbp, [r15+r15*4]
0x18002507c  mov     r14, [r13+0]
0x180025080  cmp     [rax+10h], rsi
0x180025084  jz      short loc_1800250D3
0x180025086  mov     eax, [rax+10h]
0x180025089  lea     edi, ds:2[rax*2]
0x180025090  mov     [r14+rbp*8+10h], edi
0x180025095  call    cs:__imp_GetProcessHeap
0x18002509b  mov     r8d, edi; dwBytes
0x18002509e  mov     edx, 8; dwFlags
0x1800250a3  mov     rcx, rax; hHeap
0x1800250a6  call    cs:__imp_HeapAlloc
0x1800250ac  mov     [r14+rbp*8], rax
0x1800250b0  test    rax, rax
0x1800250b3  jz      loc_180025179
0x1800250b9  mov     r8, [rbx]
0x1800250bc  cmp     qword ptr [r8+18h], 7
0x1800250c1  jbe     short loc_1800250C6
0x1800250c3  mov     r8, [r8]; wchar_t *
0x1800250c6  mov     edx, [r14+rbp*8+10h]; unsigned __int64
0x1800250cb  mov     rcx, rax; wchar_t *
0x1800250ce  call    ?StringCbCopyW@@YAJPEA_W_KPEB_W@Z; StringCbCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800250d3  mov     rax, [rbx]
0x1800250d6  cmp     [rax+78h], rsi
0x1800250da  jz      short loc_180025139
0x1800250dc  mov     [r14+rbp*8+18h], esi
0x1800250e1  mov     rcx, [rbx]
0x1800250e4  mov     rcx, [rcx+78h]; this
0x1800250e8  call    ?FirstTranslationValueLength@STRING_ENTRY@@QEBA_KXZ; STRING_ENTRY::FirstTranslationValueLength(void)
0x1800250ed  lea     edi, ds:2[rax*2]
0x1800250f4  mov     [r14+rbp*8+14h], edi
0x1800250f9  call    cs:__imp_GetProcessHeap
0x1800250ff  mov     r8d, edi; dwBytes
0x180025102  mov     edx, 8; dwFlags
0x180025107  mov     rcx, rax; hHeap
0x18002510a  call    cs:__imp_HeapAlloc
0x180025110  mov     [r14+rbp*8+8], rax
0x180025115  mov     r9, rax
0x180025118  test    rax, rax
0x18002511b  jz      short loc_180025179
0x18002511d  mov     rcx, [rbx]
0x180025120  mov     rcx, [rcx+78h]; this
0x180025124  call    ?FirstTranslationValue@STRING_ENTRY@@QEBAPEB_WXZ; STRING_ENTRY::FirstTranslationValue(void)
0x180025129  mov     edx, [r14+rbp*8+14h]; unsigned __int64
0x18002512e  mov     r8, rax; wchar_t *
0x180025131  mov     rcx, r9; wchar_t *
0x180025134  call    ?StringCbCopyW@@YAJPEA_W_KPEB_W@Z; StringCbCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180025139  mov     rax, [rbx]
0x18002513c  movzx   ecx, byte ptr [rax+20h]
0x180025140  mov     [r14+rbp*8+20h], rcx
0x180025145  mov     rax, [rbx]
0x180025148  shl     rcx, 10h
0x18002514c  mov     [r14+rbp*8+20h], rcx
0x180025151  mov     rdx, [rax+80h]
0x180025158  test    rdx, rdx
0x18002515b  jz      short loc_180025169
0x18002515d  movzx   eax, word ptr [rdx+20h]
0x180025161  or      rax, rcx
0x180025164  mov     [r14+rbp*8+20h], rax
0x180025169  inc     r15
0x18002516c  lea     rdi, [r13+8]
0x180025170  add     rbx, 8
0x180025174  jmp     loc_18002505F
0x180025179  mov     esi, 8
0x18002517e  mov     rcx, r13; struct FIELD_INFOLIST *
0x180025181  call    ?TdhpClearFieldInfoList@@YAXPEAUFIELD_INFOLIST@@@Z; TdhpClearFieldInfoList(FIELD_INFOLIST *)
0x180025186  mov     eax, esi
0x180025188  jmp     short loc_18002518F
0x18002518a  mov     eax, 8
0x18002518f  add     rsp, 28h
0x180025193  pop     r15
0x180025195  pop     r14
0x180025197  pop     r13
0x180025199  pop     r12
0x18002519b  pop     rdi
0x18002519c  pop     rsi
0x18002519d  pop     rbp
0x18002519e  pop     rbx
0x18002519f  retn
```
