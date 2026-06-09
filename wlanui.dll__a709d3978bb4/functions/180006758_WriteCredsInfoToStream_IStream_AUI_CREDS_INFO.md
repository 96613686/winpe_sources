# WriteCredsInfoToStream(IStream *,_AUI_CREDS_INFO *)

- ea: `0x180006758`
- end: `0x18000682d`
- name: `?WriteCredsInfoToStream@@YAJPEAUIStream@@PEAU_AUI_CREDS_INFO@@@Z`
- size: `213`
- prototype: `__int64 __fastcall(struct IStream *, struct _AUI_CREDS_INFO *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f370`

## callees

- `0x180006758`
- `0x18001d010`

## import_xrefs

- `SHLWAPI!__imp_IStream_Reset` at `0x180006770`
- `SHLWAPI!__imp_IStream_Reset` at `0x180006770`

## pseudocode

```c
__int64 __fastcall WriteCredsInfoToStream(struct IStream *a1, struct _AUI_CREDS_INFO *a2)
{
  int v4; // eax
  unsigned int v5; // edx
  __int64 v6; // r8
  unsigned int v7; // eax
  int v9; // [rsp+40h] [rbp+8h] BYREF

  v9 = 0;
  IStream_Reset(a1);
  v4 = (*(__int64 (__fastcall **)(struct IStream *, struct _AUI_CREDS_INFO *, __int64, int *))(*(_QWORD *)a1 + 32LL))(
         a1,
         a2,
         56,
         &v9);
  v5 = v4;
  if ( v9 != 56 )
    return (unsigned int)-2147467259;
  if ( v4 < 0 )
    return v5;
  v6 = *((unsigned int *)a2 + 6);
  if ( (_DWORD)v6 )
  {
    v5 = (*(__int64 (__fastcall **)(struct IStream *, _QWORD, __int64, int *))(*(_QWORD *)a1 + 32LL))(
           a1,
           *((_QWORD *)a2 + 4),
           v6,
           &v9);
    if ( v9 != *((_DWORD *)a2 + 6) )
      return (unsigned int)-2147467259;
    if ( (v5 & 0x80000000) != 0 )
      return v5;
  }
  if ( *((_DWORD *)a2 + 10) )
  {
    v7 = (*(__int64 (__fastcall **)(struct IStream *, _QWORD, _QWORD, int *))(*(_QWORD *)a1 + 32LL))(
           a1,
           *((_QWORD *)a2 + 6),
           ((2580 * *((_DWORD *)a2 + 10)) & 0xFFFFFFF0) + 16,
           &v9);
    if ( v9 != ((2580 * *((_DWORD *)a2 + 10)) & 0xFFFFFFF0) + 16 )
      return (unsigned int)-2147467259;
    return v7;
  }
  return v5;
}

```

## disassembly

```asm
0x180006758  mov     [rsp+arg_8], rbx
0x18000675d  push    rdi
0x18000675e  sub     rsp, 30h
0x180006762  mov     rbx, rdx
0x180006765  mov     [rsp+38h+arg_0], 0
0x18000676d  mov     rdi, rcx
0x180006770  call    cs:__imp_IStream_Reset
0x180006776  mov     rax, [rdi]
0x180006779  lea     r9, [rsp+38h+arg_0]
0x18000677e  mov     r8d, 38h ; '8'
0x180006784  mov     rdx, rbx
0x180006787  mov     rcx, rdi
0x18000678a  mov     rax, [rax+20h]
0x18000678e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006793  cmp     [rsp+38h+arg_0], 38h ; '8'
0x180006798  mov     edx, eax
0x18000679a  jz      short loc_1800067A3
0x18000679c  mov     edx, 80004005h
0x1800067a1  jmp     short loc_180006820
0x1800067a3  test    eax, eax
0x1800067a5  js      short loc_180006820
0x1800067a7  mov     r8d, [rbx+18h]
0x1800067ab  test    r8d, r8d
0x1800067ae  jz      short loc_1800067D7
0x1800067b0  mov     rax, [rdi]
0x1800067b3  lea     r9, [rsp+38h+arg_0]
0x1800067b8  mov     rdx, [rbx+20h]
0x1800067bc  mov     rcx, rdi
0x1800067bf  mov     rax, [rax+20h]
0x1800067c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067c8  mov     edx, eax
0x1800067ca  mov     eax, [rbx+18h]
0x1800067cd  cmp     [rsp+38h+arg_0], eax
0x1800067d1  jnz     short loc_18000679C
0x1800067d3  test    edx, edx
0x1800067d5  js      short loc_180006820
0x1800067d7  cmp     dword ptr [rbx+28h], 0
0x1800067db  jbe     short loc_180006820
0x1800067dd  imul    r8d, [rbx+28h], 0A14h
0x1800067e5  lea     r9, [rsp+38h+arg_0]
0x1800067ea  mov     rax, [rdi]
0x1800067ed  mov     rcx, rdi
0x1800067f0  mov     rdx, [rbx+30h]
0x1800067f4  mov     rax, [rax+20h]
0x1800067f8  and     r8d, 0FFFFFFF0h
0x1800067fc  add     r8d, 10h
0x180006800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006805  imul    ecx, [rbx+28h], 0A14h
0x18000680c  mov     edx, 80004005h
0x180006811  and     ecx, 0FFFFFFF0h
0x180006814  add     ecx, 10h
0x180006817  cmp     [rsp+38h+arg_0], ecx
0x18000681b  cmovnz  eax, edx
0x18000681e  mov     edx, eax
0x180006820  mov     rbx, [rsp+38h+arg_8]
0x180006825  mov     eax, edx
0x180006827  add     rsp, 30h
0x18000682b  pop     rdi
0x18000682c  retn
```
