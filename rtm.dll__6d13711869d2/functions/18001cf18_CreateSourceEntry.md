# CreateSourceEntry

- ea: `0x18001cf18`
- end: `0x18001d1e4`
- name: `CreateSourceEntry`
- size: `716`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x180018070`
- `0x18001c1a8`

## callees

- `0x18001cf18`
- `0x18001dd8c`
- `0x18001e4b0`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x18001fa10`
- `0x180020010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18001cf8a`
- `KERNEL32!HeapAlloc` at `0x18001cf8a`
- `rtutils!RouterLogEventA` at `0x18001d00a`
- `rtutils!RouterLogEventA` at `0x18001d00a`

## string_xrefs

- `0x18001cfac`: `CreateSourceEntry : failed to allocate source entry %x`
- `0x18001d12a`: `AddToGroupList Source Entry already exists for : %x, %x`

## pseudocode

```c
__int64 __fastcall CreateSourceEntry(__int64 a1, __int64 a2, int a3, int a4, _QWORD *a5)
{
  char *v9; // rax
  char *v10; // rbx
  unsigned int v11; // ebx
  _QWORD *v12; // rax
  _QWORD *v13; // rcx
  __int64 v14; // rdi
  int v15; // r8d
  unsigned int v16; // edx
  __int64 v17; // r9
  __int64 v18; // rax
  _QWORD *v19; // rcx
  _QWORD *v20; // rax
  __int64 v22; // [rsp+30h] [rbp-D0h] BYREF
  int v23; // [rsp+40h] [rbp-C0h] BYREF
  char v24[2044]; // [rsp+44h] [rbp-BCh] BYREF
  int v25; // [rsp+840h] [rbp+740h] BYREF
  char v26[2044]; // [rsp+844h] [rbp+744h] BYREF

  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  v9 = (char *)HeapAlloc(hHeap, 0, 0x110u);
  v10 = v9;
  if ( v9 )
  {
    memset_0(v9, 0, 0x110u);
    *((_DWORD *)v10 + 26) = a3;
    *((_DWORD *)v10 + 27) = a4;
    *((_DWORD *)v10 + 34) = -1;
    *((_DWORD *)v10 + 35) = -1;
    *((_DWORD *)v10 + 8) = 0;
    *((_DWORD *)v10 + 42) = 0;
    *((_QWORD *)v10 + 22) = 0;
    memset_0(v10 + 184, 0, 0x54u);
    *(_QWORD *)(v10 + 36) = 0;
    *((_QWORD *)v10 + 7) = v10 + 48;
    *((_QWORD *)v10 + 6) = v10 + 48;
    *((_QWORD *)v10 + 9) = v10 + 64;
    *((_QWORD *)v10 + 8) = v10 + 64;
    *((_QWORD *)v10 + 12) = v10 + 88;
    *((_QWORD *)v10 + 11) = v10 + 88;
    v12 = v10 + 16;
    *((_QWORD *)v10 + 3) = v10 + 16;
    *((_QWORD *)v10 + 2) = v10 + 16;
    *((_DWORD *)v10 + 20) = 0;
    v13 = *(_QWORD **)(a2 + 8);
    if ( *v13 == a2 )
    {
      *((_QWORD *)v10 + 3) = v13;
      *v12 = a2;
      *v13 = v12;
      *(_QWORD *)(a2 + 8) = v12;
      v25 = 0;
      *((_QWORD *)v10 + 1) = v10;
      *(_QWORD *)v10 = v10;
      v22 = 0;
      memset_0(v26, 0, sizeof(v26));
      v14 = a1 + 56;
      if ( (unsigned int)FindSourceEntry((int)a1 + 56, *((_DWORD *)v10 + 26), v15, (unsigned int)&v22, 0) )
      {
        if ( qword_18002B8A8 )
        {
          v17 = *((unsigned int *)v10 + 27);
          LOWORD(v25) = 0;
          FormatRRASErrorString(&v25, L"AddToGroupList Source Entry already exists for : %x, %x", v16, v17);
          ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v25);
        }
LABEL_17:
        *a5 = v10;
        return 0;
      }
      v18 = v22;
      if ( v22 )
      {
        v19 = *(_QWORD **)(v22 + 8);
        if ( *v19 == v22 )
        {
          *(_QWORD *)v10 = v22;
          *((_QWORD *)v10 + 1) = v19;
          *v19 = v10;
          *(_QWORD *)(v18 + 8) = v10;
          goto LABEL_15;
        }
      }
      else
      {
        v20 = *(_QWORD **)(a1 + 64);
        if ( *v20 == v14 )
        {
          *(_QWORD *)v10 = v14;
          *((_QWORD *)v10 + 1) = v20;
          *v20 = v10;
          *(_QWORD *)(a1 + 64) = v10;
LABEL_15:
          if ( ++*(_DWORD *)(a1 + 52) > 0x10u )
            MergeTempAndMasterSourceLists(a1);
          goto LABEL_17;
        }
      }
    }
    __fastfail(3u);
  }
  v11 = 8;
  if ( qword_18002B8A8 )
  {
    LOWORD(v23) = 0;
    FormatRRASErrorString(&v23, L"CreateSourceEntry : failed to allocate source entry %x", 8);
    ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v23);
  }
  if ( dword_18002BA54 )
    RouterLogEventA(qword_18002BA58, 1u, 0xC353u, 0, 0, 8u);
  return v11;
}

```

## disassembly

```asm
0x18001cf18  mov     [rsp-8+arg_10], rbx
0x18001cf1d  mov     [rsp-8+arg_18], rsi
0x18001cf22  push    rbp
0x18001cf23  push    rdi
0x18001cf24  push    r12
0x18001cf26  push    r14
0x18001cf28  push    r15
0x18001cf2a  lea     rbp, [rsp-0F50h]
0x18001cf32  mov     eax, 1050h
0x18001cf37  call    _alloca_probe
0x18001cf3c  sub     rsp, rax
0x18001cf3f  mov     rax, cs:__security_cookie
0x18001cf46  xor     rax, rsp
0x18001cf49  mov     [rbp+0F70h+var_30], rax
0x18001cf50  mov     r14, [rbp+0F70h+arg_20]
0x18001cf57  mov     r12d, r8d
0x18001cf5a  mov     rdi, rdx
0x18001cf5d  mov     rsi, rcx
0x18001cf60  xor     eax, eax
0x18001cf62  lea     rcx, [rsp+1070h+var_102C]; void *
0x18001cf67  xor     edx, edx; Val
0x18001cf69  mov     [rsp+1070h+var_1030], eax
0x18001cf6d  mov     r8d, 7FCh; Size
0x18001cf73  mov     r15d, r9d
0x18001cf76  call    memset_0
0x18001cf7b  mov     rcx, cs:hHeap; hHeap
0x18001cf82  xor     edx, edx; dwFlags
0x18001cf84  mov     r8d, 110h; dwBytes
0x18001cf8a  call    cs:__imp_HeapAlloc
0x18001cf90  mov     rbx, rax
0x18001cf93  test    rax, rax
0x18001cf96  jnz     short loc_18001D015
0x18001cf98  cmp     cs:qword_18002B8A8, rax
0x18001cf9f  lea     ebx, [rax+8]
0x18001cfa2  jz      short loc_18001CFDC
0x18001cfa4  mov     r8d, ebx
0x18001cfa7  mov     word ptr [rsp+1070h+var_1030], ax
0x18001cfac  lea     rdx, aCreatesourceen; "CreateSourceEntry : failed to allocate "...
0x18001cfb3  lea     rcx, [rsp+1070h+var_1030]
0x18001cfb8  call    FormatRRASErrorString
0x18001cfbd  mov     rdx, cs:qword_18002B8A8
0x18001cfc4  lea     r8, [rsp+1070h+var_1030]
0x18001cfc9  mov     rcx, cs:gMgmEtwContext
0x18001cfd0  mov     rax, cs:gMgmTemplateFunc
0x18001cfd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cfdc  cmp     cs:dword_18002BA54, 1
0x18001cfe3  jb      loc_18001D1B0
0x18001cfe9  mov     rcx, cs:qword_18002BA58; hLogHandle
0x18001cff0  xor     r9d, r9d; dwSubStringCount
0x18001cff3  mov     [rsp+1070h+dwErrorCode], ebx; dwErrorCode
0x18001cff7  mov     r8d, 0C353h; dwMessageId
0x18001cffd  mov     [rsp+1070h+plpszSubStringArray], 0; plpszSubStringArray
0x18001d006  lea     edx, [r9+1]; dwEventType
0x18001d00a  call    cs:__imp_RouterLogEventA
0x18001d010  jmp     loc_18001D1B0
0x18001d015  xor     edx, edx; Val
0x18001d017  mov     r8d, 110h; Size
0x18001d01d  mov     rcx, rbx; void *
0x18001d020  call    memset_0
0x18001d025  or      eax, 0FFFFFFFFh
0x18001d028  mov     [rbx+68h], r12d
0x18001d02c  xor     edx, edx; Val
0x18001d02e  mov     [rbx+6Ch], r15d
0x18001d032  lea     rcx, [rbx+0B8h]; void *
0x18001d039  mov     [rbx+88h], eax
0x18001d03f  mov     [rbx+8Ch], eax
0x18001d045  mov     dword ptr [rbx+20h], 0
0x18001d04c  lea     r8d, [rdx+54h]; Size
0x18001d050  mov     dword ptr [rbx+0A8h], 0
0x18001d05a  mov     qword ptr [rbx+0B0h], 0
0x18001d065  call    memset_0
0x18001d06a  lea     rax, [rbx+30h]
0x18001d06e  mov     qword ptr [rbx+24h], 0
0x18001d076  mov     [rax+8], rax
0x18001d07a  mov     [rax], rax
0x18001d07d  lea     rax, [rbx+40h]
0x18001d081  mov     [rax+8], rax
0x18001d085  mov     [rax], rax
0x18001d088  lea     rax, [rbx+58h]
0x18001d08c  mov     [rax+8], rax
0x18001d090  mov     [rax], rax
0x18001d093  lea     rax, [rbx+10h]
0x18001d097  mov     [rax+8], rax
0x18001d09b  mov     [rax], rax
0x18001d09e  mov     dword ptr [rbx+50h], 0
0x18001d0a5  mov     rcx, [rdi+8]
0x18001d0a9  cmp     [rcx], rdi
0x18001d0ac  jnz     loc_18001D1DD
0x18001d0b2  mov     [rax+8], rcx
0x18001d0b6  xor     edx, edx; Val
0x18001d0b8  mov     [rax], rdi
0x18001d0bb  mov     r8d, 7FCh; Size
0x18001d0c1  mov     [rcx], rax
0x18001d0c4  lea     rcx, [rbp+0F70h+var_82C]; void *
0x18001d0cb  mov     [rdi+8], rax
0x18001d0cf  xor     eax, eax
0x18001d0d1  mov     [rbp+0F70h+var_830], eax
0x18001d0d7  mov     [rbx+8], rbx
0x18001d0db  mov     [rbx], rbx
0x18001d0de  mov     [rsp+1070h+var_1040], 0
0x18001d0e7  call    memset_0
0x18001d0ec  mov     edx, [rbx+68h]
0x18001d0ef  lea     rdi, [rsi+38h]
0x18001d0f3  mov     rcx, rdi
0x18001d0f6  mov     dword ptr [rsp+1070h+plpszSubStringArray], 0
0x18001d0fe  lea     r9, [rsp+1070h+var_1040]
0x18001d103  call    FindSourceEntry
0x18001d108  test    eax, eax
0x18001d10a  jz      short loc_18001D160
0x18001d10c  cmp     cs:qword_18002B8A8, 0
0x18001d114  jz      loc_18001D1AB
0x18001d11a  mov     r9d, [rbx+6Ch]
0x18001d11e  lea     rcx, [rbp+0F70h+var_830]
0x18001d125  xor     eax, eax
0x18001d127  mov     r8d, edx
0x18001d12a  lea     rdx, aAddtogrouplist; "AddToGroupList Source Entry already exi"...
0x18001d131  mov     word ptr [rbp+0F70h+var_830], ax
0x18001d138  call    FormatRRASErrorString
0x18001d13d  mov     rdx, cs:qword_18002B8A8
0x18001d144  lea     r8, [rbp+0F70h+var_830]
0x18001d14b  mov     rcx, cs:gMgmEtwContext
0x18001d152  mov     rax, cs:gMgmTemplateFunc
0x18001d159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d15e  jmp     short loc_18001D1AB
0x18001d160  mov     rax, [rsp+1070h+var_1040]
0x18001d165  test    rax, rax
0x18001d168  jz      short loc_18001D183
0x18001d16a  mov     rcx, [rax+8]
0x18001d16e  cmp     [rcx], rax
0x18001d171  jnz     short loc_18001D1DD
0x18001d173  mov     [rbx], rax
0x18001d176  mov     [rbx+8], rcx
0x18001d17a  mov     [rcx], rbx
0x18001d17d  mov     [rax+8], rbx
0x18001d181  jmp     short loc_18001D19A
0x18001d183  mov     rax, [rdi+8]
0x18001d187  cmp     [rax], rdi
0x18001d18a  jnz     short loc_18001D1DD
0x18001d18c  mov     [rbx], rdi
0x18001d18f  mov     [rbx+8], rax
0x18001d193  mov     [rax], rbx
0x18001d196  mov     [rdi+8], rbx
0x18001d19a  inc     dword ptr [rsi+34h]
0x18001d19d  cmp     dword ptr [rsi+34h], 10h
0x18001d1a1  jbe     short loc_18001D1AB
0x18001d1a3  mov     rcx, rsi
0x18001d1a6  call    MergeTempAndMasterSourceLists
0x18001d1ab  mov     [r14], rbx
0x18001d1ae  xor     ebx, ebx
0x18001d1b0  mov     eax, ebx
0x18001d1b2  mov     rcx, [rbp+0F70h+var_30]
0x18001d1b9  xor     rcx, rsp; StackCookie
0x18001d1bc  call    __security_check_cookie
0x18001d1c1  lea     r11, [rsp+1070h+var_20]
0x18001d1c9  mov     rbx, [r11+40h]
0x18001d1cd  mov     rsi, [r11+48h]
0x18001d1d1  mov     rsp, r11
0x18001d1d4  pop     r15
0x18001d1d6  pop     r14
0x18001d1d8  pop     r12
0x18001d1da  pop     rdi
0x18001d1db  pop     rbp
0x18001d1dc  retn
0x18001d1dd  mov     ecx, 3
0x18001d1e2  int     29h; Win8: RtlFailFast(ecx)
```
