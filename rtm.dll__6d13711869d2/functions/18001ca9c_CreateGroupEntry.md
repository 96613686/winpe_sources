# CreateGroupEntry

- ea: `0x18001ca9c`
- end: `0x18001cd8d`
- name: `CreateGroupEntry`
- size: `753`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180018070`
- `0x18001c1a8`

## callees

- `0x180014d2c`
- `0x180015178`
- `0x18001ca9c`
- `0x18001dc28`
- `0x18001e374`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x18001fa10`
- `0x180020010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18001cb14`
- `KERNEL32!HeapAlloc` at `0x18001cb14`
- `rtutils!RouterLogEventA` at `0x18001cb94`
- `rtutils!RouterLogEventA` at `0x18001cb94`

## string_xrefs

- `0x18001cb36`: `CreateGroupEntry : failed to allocate group entry %x`
- `0x18001ccb2`: `AddToGroupList Group Entry already exists for : %x, %x`

## pseudocode

```c
__int64 __fastcall CreateGroupEntry(__int64 a1, int a2, int a3, __int64 *a4)
{
  SIZE_T v8; // rsi
  void *v9; // rax
  __int64 v10; // rbx
  unsigned int v11; // edi
  unsigned int v12; // r8d
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rcx
  _QWORD *v16; // rax
  _QWORD *v17; // rcx
  int v18; // r8d
  unsigned int v19; // edx
  __int64 v20; // r9
  __int64 v21; // rax
  __int64 *v22; // rcx
  __int64 *v23; // rax
  __int64 v25; // [rsp+30h] [rbp-D0h] BYREF
  int v26; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v27[2044]; // [rsp+44h] [rbp-BCh] BYREF
  int v28; // [rsp+840h] [rbp+740h] BYREF
  _BYTE v29[2044]; // [rsp+844h] [rbp+744h] BYREF

  v26 = 0;
  memset_0(v27, 0, sizeof(v27));
  v8 = (unsigned int)(16 * (dword_18002B934 - 1) + 104);
  v9 = HeapAlloc(hHeap, 0, v8);
  v10 = (__int64)v9;
  if ( v9 )
  {
    memset_0(v9, 0, v8);
    v12 = 0;
    *(_DWORD *)(v10 + 32) = a2;
    *(_DWORD *)(v10 + 36) = a3;
    *(_QWORD *)(v10 + 48) = 0;
    for ( *(_QWORD *)(v10 + 40) = 0; v12 < dword_18002B934; *(_QWORD *)(v13 + v10 + 88) = v15 )
    {
      v13 = 16LL * v12;
      v14 = 2 * (v12 + 6LL);
      v15 = v13 + v10 + 88;
      ++v12;
      *(_QWORD *)(v10 + 8 * v14) = v15;
    }
    *(_QWORD *)(v10 + 80) = v10 + 72;
    *(_QWORD *)(v10 + 72) = v10 + 72;
    *(_QWORD *)(v10 + 64) = v10 + 56;
    *(_QWORD *)(v10 + 56) = v10 + 56;
    v16 = (_QWORD *)(v10 + 16);
    *(_QWORD *)(v10 + 24) = v10 + 16;
    *(_QWORD *)(v10 + 16) = v10 + 16;
    v17 = *(_QWORD **)(a1 + 8);
    if ( *v17 == a1 )
    {
      *(_QWORD *)(v10 + 24) = v17;
      *v16 = a1;
      *v17 = v16;
      *(_QWORD *)(a1 + 8) = v16;
      v28 = 0;
      *(_QWORD *)(v10 + 8) = v10;
      *(_QWORD *)v10 = v10;
      v25 = 0;
      memset_0(v29, 0, sizeof(v29));
      AcquireWriteLock(&qword_18002BA10);
      if ( (unsigned int)FindGroupEntry(
                           (unsigned int)&qword_18002BA00,
                           *(_DWORD *)(v10 + 32),
                           v18,
                           (unsigned int)&v25,
                           0) )
      {
        if ( qword_18002B8A8 )
        {
          v20 = *(unsigned int *)(v10 + 36);
          LOWORD(v28) = 0;
          FormatRRASErrorString(&v28, L"AddToGroupList Group Entry already exists for : %x, %x", v19, v20);
          ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v28);
        }
LABEL_19:
        v11 = 0;
        ReleaseWriteLock(&qword_18002BA10);
        *a4 = v10;
        return v11;
      }
      v21 = v25;
      if ( v25 )
      {
        v22 = *(__int64 **)(v25 + 8);
        if ( *v22 == v25 )
        {
          *(_QWORD *)v10 = v25;
          *(_QWORD *)(v10 + 8) = v22;
          *v22 = v10;
          *(_QWORD *)(v21 + 8) = v10;
          goto LABEL_17;
        }
      }
      else
      {
        v23 = (__int64 *)qword_18002BA08;
        if ( *(__int64 **)qword_18002BA08 == &qword_18002BA00 )
        {
          *(_QWORD *)v10 = &qword_18002BA00;
          *(_QWORD *)(v10 + 8) = v23;
          *v23 = v10;
          qword_18002BA08 = v10;
LABEL_17:
          if ( (unsigned int)++dword_18002B9F8 > 0x10 )
            MergeTempAndMasterGroupLists(&qword_18002BA00);
          goto LABEL_19;
        }
      }
    }
    __fastfail(3u);
  }
  v11 = 8;
  if ( qword_18002B8A8 )
  {
    LOWORD(v26) = 0;
    FormatRRASErrorString(&v26, L"CreateGroupEntry : failed to allocate group entry %x", 8);
    ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v26);
  }
  if ( dword_18002BA54 )
    RouterLogEventA(qword_18002BA58, 1u, 0xC353u, 0, 0, 8u);
  return v11;
}

```

## disassembly

```asm
0x18001ca9c  mov     [rsp-8+arg_8], rbx
0x18001caa1  mov     [rsp-8+arg_10], rsi
0x18001caa6  push    rbp
0x18001caa7  push    rdi
0x18001caa8  push    r12
0x18001caaa  push    r14
0x18001caac  push    r15
0x18001caae  lea     rbp, [rsp-0F50h]
0x18001cab6  mov     eax, 1050h
0x18001cabb  call    _alloca_probe
0x18001cac0  sub     rsp, rax
0x18001cac3  mov     rax, cs:__security_cookie
0x18001caca  xor     rax, rsp
0x18001cacd  mov     [rbp+0F70h+var_30], rax
0x18001cad4  mov     r14d, r8d
0x18001cad7  mov     r15d, edx
0x18001cada  mov     rdi, rcx
0x18001cadd  xor     eax, eax
0x18001cadf  xor     edx, edx; Val
0x18001cae1  mov     [rsp+1070h+var_1030], eax
0x18001cae5  mov     r8d, 7FCh; Size
0x18001caeb  lea     rcx, [rsp+1070h+var_102C]; void *
0x18001caf0  mov     r12, r9
0x18001caf3  call    memset_0
0x18001caf8  mov     eax, cs:dword_18002B934
0x18001cafe  xor     edx, edx; dwFlags
0x18001cb00  mov     rcx, cs:hHeap; hHeap
0x18001cb07  dec     eax
0x18001cb09  shl     eax, 4
0x18001cb0c  add     eax, 68h ; 'h'
0x18001cb0f  mov     r8d, eax; dwBytes
0x18001cb12  mov     esi, eax
0x18001cb14  call    cs:__imp_HeapAlloc
0x18001cb1a  mov     rbx, rax
0x18001cb1d  test    rax, rax
0x18001cb20  jnz     short loc_18001CB9F
0x18001cb22  cmp     cs:qword_18002B8A8, rax
0x18001cb29  lea     edi, [rax+8]
0x18001cb2c  jz      short loc_18001CB66
0x18001cb2e  mov     r8d, edi
0x18001cb31  mov     word ptr [rsp+1070h+var_1030], ax
0x18001cb36  lea     rdx, aCreategroupent; "CreateGroupEntry : failed to allocate g"...
0x18001cb3d  lea     rcx, [rsp+1070h+var_1030]
0x18001cb42  call    FormatRRASErrorString
0x18001cb47  mov     rdx, cs:qword_18002B8A8
0x18001cb4e  lea     r8, [rsp+1070h+var_1030]
0x18001cb53  mov     rcx, cs:gMgmEtwContext
0x18001cb5a  mov     rax, cs:gMgmTemplateFunc
0x18001cb61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb66  cmp     cs:dword_18002BA54, 1
0x18001cb6d  jb      loc_18001CD59
0x18001cb73  mov     rcx, cs:qword_18002BA58; hLogHandle
0x18001cb7a  xor     r9d, r9d; dwSubStringCount
0x18001cb7d  mov     [rsp+1070h+dwErrorCode], edi; dwErrorCode
0x18001cb81  mov     r8d, 0C353h; dwMessageId
0x18001cb87  mov     [rsp+1070h+plpszSubStringArray], 0; plpszSubStringArray
0x18001cb90  lea     edx, [r9+1]; dwEventType
0x18001cb94  call    cs:__imp_RouterLogEventA
0x18001cb9a  jmp     loc_18001CD59
0x18001cb9f  mov     r8, rsi; Size
0x18001cba2  xor     edx, edx; Val
0x18001cba4  mov     rcx, rbx; void *
0x18001cba7  call    memset_0
0x18001cbac  xor     r8d, r8d
0x18001cbaf  mov     [rbx+20h], r15d
0x18001cbb3  mov     [rbx+24h], r14d
0x18001cbb7  mov     qword ptr [rbx+30h], 0
0x18001cbbf  mov     qword ptr [rbx+28h], 0
0x18001cbc7  cmp     cs:dword_18002B934, r8d
0x18001cbce  jbe     short loc_18001CBFD
0x18001cbd0  mov     eax, r8d
0x18001cbd3  lea     rcx, [rbx+58h]
0x18001cbd7  add     rax, 6
0x18001cbdb  mov     edx, r8d
0x18001cbde  shl     rdx, 4
0x18001cbe2  add     rax, rax
0x18001cbe5  add     rcx, rdx
0x18001cbe8  inc     r8d
0x18001cbeb  mov     [rbx+rax*8], rcx
0x18001cbef  mov     [rdx+rbx+58h], rcx
0x18001cbf4  cmp     r8d, cs:dword_18002B934
0x18001cbfb  jb      short loc_18001CBD0
0x18001cbfd  lea     rax, [rbx+48h]
0x18001cc01  mov     [rax+8], rax
0x18001cc05  mov     [rax], rax
0x18001cc08  lea     rax, [rbx+38h]
0x18001cc0c  mov     [rax+8], rax
0x18001cc10  mov     [rax], rax
0x18001cc13  lea     rax, [rbx+10h]
0x18001cc17  mov     [rax+8], rax
0x18001cc1b  mov     [rax], rax
0x18001cc1e  mov     rcx, [rdi+8]
0x18001cc22  cmp     [rcx], rdi
0x18001cc25  jnz     loc_18001CD86
0x18001cc2b  mov     [rax+8], rcx
0x18001cc2f  xor     edx, edx; Val
0x18001cc31  mov     [rax], rdi
0x18001cc34  mov     r8d, 7FCh; Size
0x18001cc3a  mov     [rcx], rax
0x18001cc3d  lea     rcx, [rbp+0F70h+var_82C]; void *
0x18001cc44  mov     [rdi+8], rax
0x18001cc48  xor     eax, eax
0x18001cc4a  mov     [rbp+0F70h+var_830], eax
0x18001cc50  mov     [rbx+8], rbx
0x18001cc54  mov     [rbx], rbx
0x18001cc57  mov     [rsp+1070h+var_1040], 0
0x18001cc60  call    memset_0
0x18001cc65  lea     rcx, qword_18002BA10
0x18001cc6c  call    AcquireWriteLock
0x18001cc71  mov     edx, [rbx+20h]
0x18001cc74  lea     rdi, qword_18002BA00
0x18001cc7b  mov     rcx, rdi
0x18001cc7e  mov     dword ptr [rsp+1070h+plpszSubStringArray], 0
0x18001cc86  lea     r9, [rsp+1070h+var_1040]
0x18001cc8b  call    FindGroupEntry
0x18001cc90  test    eax, eax
0x18001cc92  jz      short loc_18001CCE8
0x18001cc94  cmp     cs:qword_18002B8A8, 0
0x18001cc9c  jz      loc_18001CD47
0x18001cca2  mov     r9d, [rbx+24h]
0x18001cca6  lea     rcx, [rbp+0F70h+var_830]
0x18001ccad  xor     eax, eax
0x18001ccaf  mov     r8d, edx
0x18001ccb2  lea     rdx, aAddtogrouplist_0; "AddToGroupList Group Entry already exis"...
0x18001ccb9  mov     word ptr [rbp+0F70h+var_830], ax
0x18001ccc0  call    FormatRRASErrorString
0x18001ccc5  mov     rdx, cs:qword_18002B8A8
0x18001cccc  lea     r8, [rbp+0F70h+var_830]
0x18001ccd3  mov     rcx, cs:gMgmEtwContext
0x18001ccda  mov     rax, cs:gMgmTemplateFunc
0x18001cce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cce6  jmp     short loc_18001CD47
0x18001cce8  mov     rax, [rsp+1070h+var_1040]
0x18001cced  test    rax, rax
0x18001ccf0  jz      short loc_18001CD0F
0x18001ccf2  mov     rcx, [rax+8]
0x18001ccf6  cmp     [rcx], rax
0x18001ccf9  jnz     loc_18001CD86
0x18001ccff  mov     [rbx], rax
0x18001cd02  mov     [rbx+8], rcx
0x18001cd06  mov     [rcx], rbx
0x18001cd09  mov     [rax+8], rbx
0x18001cd0d  jmp     short loc_18001CD2C
0x18001cd0f  mov     rax, cs:qword_18002BA08
0x18001cd16  cmp     [rax], rdi
0x18001cd19  jnz     short loc_18001CD86
0x18001cd1b  mov     [rbx], rdi
0x18001cd1e  mov     [rbx+8], rax
0x18001cd22  mov     [rax], rbx
0x18001cd25  mov     cs:qword_18002BA08, rbx
0x18001cd2c  mov     eax, cs:dword_18002B9F8
0x18001cd32  inc     eax
0x18001cd34  mov     cs:dword_18002B9F8, eax
0x18001cd3a  cmp     eax, 10h
0x18001cd3d  jbe     short loc_18001CD47
0x18001cd3f  mov     rcx, rdi
0x18001cd42  call    MergeTempAndMasterGroupLists
0x18001cd47  xor     edi, edi
0x18001cd49  lea     rcx, qword_18002BA10
0x18001cd50  call    ReleaseWriteLock
0x18001cd55  mov     [r12], rbx
0x18001cd59  mov     eax, edi
0x18001cd5b  mov     rcx, [rbp+0F70h+var_30]
0x18001cd62  xor     rcx, rsp; StackCookie
0x18001cd65  call    __security_check_cookie
0x18001cd6a  lea     r11, [rsp+1070h+var_20]
0x18001cd72  mov     rbx, [r11+38h]
0x18001cd76  mov     rsi, [r11+40h]
0x18001cd7a  mov     rsp, r11
0x18001cd7d  pop     r15
0x18001cd7f  pop     r14
0x18001cd81  pop     r12
0x18001cd83  pop     rdi
0x18001cd84  pop     rbp
0x18001cd85  retn
0x18001cd86  mov     ecx, 3
0x18001cd8b  int     29h; Win8: RtlFailFast(ecx)
```
