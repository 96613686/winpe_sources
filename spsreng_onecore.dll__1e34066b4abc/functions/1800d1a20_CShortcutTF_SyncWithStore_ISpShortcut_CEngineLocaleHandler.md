# CShortcutTF::SyncWithStore(ISpShortcut *,CEngineLocaleHandler *)

- ea: `0x1800d1a20`
- end: `0x1800d1b32`
- name: `?SyncWithStore@CShortcutTF@@QEAAJPEAUISpShortcut@@PEAVCEngineLocaleHandler@@@Z`
- size: `274`
- prototype: `__int64 __fastcall(CShortcutTF *__hidden this, struct ISpShortcut *, struct CEngineLocaleHandler *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800c942c`

## callees

- `0x1800d0f4c`
- `0x1800d0f8c`
- `0x1800d164c`
- `0x1800d1a20`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d1a9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d1a9a`

## pseudocode

```c
__int64 __fastcall CShortcutTF::SyncWithStore(
        CShortcutTF *this,
        struct ISpShortcut *a2,
        struct CEngineLocaleHandler *a3)
{
  _DWORD *v3; // r14
  HRESULT (__stdcall *GetWordsFromGenerationChange)(ISpShortcut *, DWORD *, SPWORDLIST *); // rax
  int v8; // eax
  unsigned int v9; // edx
  int v10; // ebx
  Entry *v12; // rcx
  int v13; // esi
  struct SPWORDLIST pv[3]; // [rsp+30h] [rbp-58h] BYREF
  int v15; // [rsp+90h] [rbp+8h] BYREF

  v3 = (_DWORD *)((char *)this + 4);
  GetWordsFromGenerationChange = a2->lpVtbl->GetWordsFromGenerationChange;
  memset(pv, 0, 24);
  v8 = ((__int64 (__fastcall *)(struct ISpShortcut *, char *, struct SPWORDLIST *))GetWordsFromGenerationChange)(
         a2,
         (char *)this + 4,
         pv);
  v10 = v8;
  if ( v8 < 0 )
  {
    if ( v8 != -2147200997 )
      goto LABEL_7;
    v12 = (Entry *)*((_QWORD *)this + 1);
    if ( v12 )
      Entry::`vector deleting destructor'(v12, v9);
    *((_QWORD *)this + 1) = 0;
    *v3 = 0;
    *((_QWORD *)this + 2) = 0;
    v15 = 0;
    while ( 1 )
    {
      v13 = ((__int64 (__fastcall *)(struct ISpShortcut *, _DWORD *, int *, struct SPWORDLIST *))a2->lpVtbl->GetWords)(
              a2,
              v3,
              &v15,
              pv);
      v10 = v13;
      if ( v13 < 0 )
        break;
      v10 = CShortcutTF::ProcessWordList(this, pv);
      if ( v10 < 0 )
        goto LABEL_7;
      if ( v13 != 1 )
        goto LABEL_5;
    }
LABEL_4:
    if ( v10 < 0 )
      goto LABEL_7;
    goto LABEL_5;
  }
  if ( v8 != 282650 )
  {
    v10 = CShortcutTF::ProcessWordList(this, pv);
    goto LABEL_4;
  }
LABEL_5:
  if ( v10 != 282650 )
    v10 = CShortcutTF::FinalizeTable(this, a3);
LABEL_7:
  CoTaskMemFree(pv[0].pvBuffer);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800d1a20  push    rbx
0x1800d1a22  push    rbp
0x1800d1a23  push    rsi
0x1800d1a24  push    rdi
0x1800d1a25  push    r14
0x1800d1a27  push    r15
0x1800d1a29  sub     rsp, 58h
0x1800d1a2d  xor     eax, eax
0x1800d1a2f  lea     r14, [rcx+4]
0x1800d1a33  mov     [rsp+88h+var_48], rax
0x1800d1a38  mov     r15, rdx
0x1800d1a3b  mov     rax, [rdx]
0x1800d1a3e  mov     rbp, r8
0x1800d1a41  mov     rdi, rcx
0x1800d1a44  lea     r8, [rsp+88h+pv]
0x1800d1a49  xorps   xmm0, xmm0
0x1800d1a4c  mov     rdx, r14
0x1800d1a4f  mov     rcx, r15
0x1800d1a52  mov     rax, [rax+38h]
0x1800d1a56  movups  xmmword ptr [rsp+88h+pv], xmm0
0x1800d1a5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1a60  mov     ebx, eax
0x1800d1a62  test    eax, eax
0x1800d1a64  js      short loc_1800D1AAF
0x1800d1a66  cmp     eax, 4501Ah
0x1800d1a6b  jz      short loc_1800D1A80
0x1800d1a6d  lea     rdx, [rsp+88h+pv]; struct SPWORDLIST *
0x1800d1a72  mov     rcx, rdi; this
0x1800d1a75  call    ?ProcessWordList@CShortcutTF@@AEAAJPEBUSPWORDLIST@@@Z; CShortcutTF::ProcessWordList(SPWORDLIST const *)
0x1800d1a7a  mov     ebx, eax
0x1800d1a7c  test    ebx, ebx
0x1800d1a7e  js      short loc_1800D1A95
0x1800d1a80  cmp     ebx, 4501Ah
0x1800d1a86  jz      short loc_1800D1A95
0x1800d1a88  mov     rdx, rbp; struct CEngineLocaleHandler *
0x1800d1a8b  mov     rcx, rdi; this
0x1800d1a8e  call    ?FinalizeTable@CShortcutTF@@AEAAJPEAVCEngineLocaleHandler@@@Z; CShortcutTF::FinalizeTable(CEngineLocaleHandler *)
0x1800d1a93  mov     ebx, eax
0x1800d1a95  mov     rcx, [rsp+88h+pv+8]; pv
0x1800d1a9a  call    cs:__imp_CoTaskMemFree
0x1800d1aa0  mov     eax, ebx
0x1800d1aa2  add     rsp, 58h
0x1800d1aa6  pop     r15
0x1800d1aa8  pop     r14
0x1800d1aaa  pop     rdi
0x1800d1aab  pop     rsi
0x1800d1aac  pop     rbp
0x1800d1aad  pop     rbx
0x1800d1aae  retn
0x1800d1aaf  cmp     eax, 8004501Bh
0x1800d1ab4  jnz     short loc_1800D1A95
0x1800d1ab6  mov     rcx, [rdi+8]; this
0x1800d1aba  test    rcx, rcx
0x1800d1abd  jz      short loc_1800D1AC4
0x1800d1abf  call    ??_EEntry@@QEAAPEAXI@Z; Entry::`vector deleting destructor'(uint)
0x1800d1ac4  mov     qword ptr [rdi+8], 0
0x1800d1acc  mov     dword ptr [r14], 0
0x1800d1ad3  mov     qword ptr [rdi+10h], 0
0x1800d1adb  mov     [rsp+88h+arg_0], 0
0x1800d1ae6  mov     rax, [r15]
0x1800d1ae9  lea     r9, [rsp+88h+pv]
0x1800d1aee  lea     r8, [rsp+88h+arg_0]
0x1800d1af6  mov     rdx, r14
0x1800d1af9  mov     rcx, r15
0x1800d1afc  mov     rax, [rax+40h]
0x1800d1b00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1b05  mov     esi, eax
0x1800d1b07  mov     ebx, eax
0x1800d1b09  test    eax, eax
0x1800d1b0b  js      loc_1800D1A7C
0x1800d1b11  lea     rdx, [rsp+88h+pv]; struct SPWORDLIST *
0x1800d1b16  mov     rcx, rdi; this
0x1800d1b19  call    ?ProcessWordList@CShortcutTF@@AEAAJPEBUSPWORDLIST@@@Z; CShortcutTF::ProcessWordList(SPWORDLIST const *)
0x1800d1b1e  mov     ebx, eax
0x1800d1b20  test    eax, eax
0x1800d1b22  js      loc_1800D1A95
0x1800d1b28  cmp     esi, 1
0x1800d1b2b  jz      short loc_1800D1AE6
0x1800d1b2d  jmp     loc_1800D1A80
```
