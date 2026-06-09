# CWSHExtension::iQueryInterface(_GUID const &,void * *)

- ea: `0x1800030f0`
- end: `0x1800031ee`
- name: `?iQueryInterface@CWSHExtension@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `254`
- prototype: `__int64 __fastcall(CWSHExtension *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800030f0`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall CWSHExtension::iQueryInterface(CWSHExtension *this, const struct _GUID *a2, void **a3)
{
  __int64 v4; // rax
  char *v5; // r8
  unsigned __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rax
  char *v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rax

  v4 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IShellExtInit.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IShellExtInit.Data1 )
    v4 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IShellExtInit.Data4;
  if ( !v4 )
  {
    v5 = (char *)this - 40;
    v6 = (unsigned __int64)this - 32;
LABEL_17:
    v9 = (char *)(v6 & ((unsigned __int128)-(__int128)(unsigned __int64)v5 >> 64));
    goto LABEL_24;
  }
  v7 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IShellPropSheetExt.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IShellPropSheetExt.Data1 )
    v7 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IShellPropSheetExt.Data4;
  if ( !v7 )
  {
    v5 = (char *)this - 40;
    v6 = (unsigned __int64)this - 24;
    goto LABEL_17;
  }
  v8 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IWSHExtension.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IWSHExtension.Data1 )
    v8 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IWSHExtension.Data4;
  if ( !v8 )
  {
    v9 = (char *)this - 40;
    v5 = (char *)this - 40;
LABEL_24:
    *a3 = v9;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v5 + 8LL))(v5);
    return 0;
  }
  v10 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IDropTarget.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IDropTarget.Data1 )
    v10 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IDropTarget.Data4;
  if ( !v10 )
  {
    v5 = (char *)this - 40;
    v6 = (unsigned __int64)this - 16;
    goto LABEL_17;
  }
  v11 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IPersistFile.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IPersistFile.Data1 )
    v11 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IPersistFile.Data4;
  if ( !v11 )
  {
    v5 = (char *)this - 40;
    if ( this == (CWSHExtension *)40 )
      v9 = 0;
    else
      v9 = (char *)this - 8;
    goto LABEL_24;
  }
  *a3 = 0;
  return 2147500034LL;
}

```

## disassembly

```asm
0x1800030f0  sub     rsp, 28h
0x1800030f4  mov     rax, [rdx]
0x1800030f7  mov     r9, r8
0x1800030fa  sub     rax, qword ptr cs:IID_IShellExtInit.Data1
0x180003101  jnz     short loc_18000310E
0x180003103  mov     rax, [rdx+8]
0x180003107  sub     rax, qword ptr cs:IID_IShellExtInit.Data4
0x18000310e  test    rax, rax
0x180003111  jnz     short loc_18000311D
0x180003113  lea     r8, [rcx-28h]
0x180003117  add     rcx, 0FFFFFFFFFFFFFFE0h
0x18000311b  jmp     short loc_18000318C
0x18000311d  mov     rax, [rdx]
0x180003120  sub     rax, qword ptr cs:IID_IShellPropSheetExt.Data1
0x180003127  jnz     short loc_180003134
0x180003129  mov     rax, [rdx+8]
0x18000312d  sub     rax, qword ptr cs:IID_IShellPropSheetExt.Data4
0x180003134  test    rax, rax
0x180003137  jnz     short loc_180003143
0x180003139  lea     r8, [rcx-28h]
0x18000313d  add     rcx, 0FFFFFFFFFFFFFFE8h
0x180003141  jmp     short loc_18000318C
0x180003143  mov     rax, [rdx]
0x180003146  sub     rax, qword ptr cs:IID_IWSHExtension.Data1
0x18000314d  jnz     short loc_18000315A
0x18000314f  mov     rax, [rdx+8]
0x180003153  sub     rax, qword ptr cs:IID_IWSHExtension.Data4
0x18000315a  test    rax, rax
0x18000315d  jnz     short loc_180003168
0x18000315f  lea     rdx, [rcx-28h]
0x180003163  mov     r8, rdx
0x180003166  jmp     short loc_1800031C7
0x180003168  mov     rax, [rdx]
0x18000316b  sub     rax, qword ptr cs:IID_IDropTarget.Data1
0x180003172  jnz     short loc_18000317F
0x180003174  mov     rax, [rdx+8]
0x180003178  sub     rax, qword ptr cs:IID_IDropTarget.Data4
0x18000317f  test    rax, rax
0x180003182  jnz     short loc_18000319A
0x180003184  lea     r8, [rcx-28h]
0x180003188  add     rcx, 0FFFFFFFFFFFFFFF0h
0x18000318c  mov     rax, r8
0x18000318f  neg     rax
0x180003192  sbb     rdx, rdx
0x180003195  and     rdx, rcx
0x180003198  jmp     short loc_1800031C7
0x18000319a  mov     rax, [rdx]
0x18000319d  sub     rax, qword ptr cs:IID_IPersistFile.Data1
0x1800031a4  jnz     short loc_1800031B1
0x1800031a6  mov     rax, [rdx+8]
0x1800031aa  sub     rax, qword ptr cs:IID_IPersistFile.Data4
0x1800031b1  test    rax, rax
0x1800031b4  jnz     short loc_1800031DD
0x1800031b6  lea     r8, [rcx-28h]
0x1800031ba  test    r8, r8
0x1800031bd  jz      short loc_1800031C5
0x1800031bf  lea     rdx, [rcx-8]
0x1800031c3  jmp     short loc_1800031C7
0x1800031c5  xor     edx, edx
0x1800031c7  mov     [r9], rdx
0x1800031ca  mov     rcx, r8
0x1800031cd  mov     rax, [r8]
0x1800031d0  mov     rax, [rax+8]
0x1800031d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031d9  xor     eax, eax
0x1800031db  jmp     short loc_1800031E9
0x1800031dd  mov     qword ptr [r8], 0
0x1800031e4  mov     eax, 80004002h
0x1800031e9  add     rsp, 28h
0x1800031ed  retn
```
