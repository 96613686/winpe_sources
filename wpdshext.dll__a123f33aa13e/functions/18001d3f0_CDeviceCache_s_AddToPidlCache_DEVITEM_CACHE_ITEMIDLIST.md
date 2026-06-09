# CDeviceCache::s_AddToPidlCache(DEVITEM_CACHE *,_ITEMIDLIST *)

- ea: `0x18001d3f0`
- end: `0x18001d69d`
- name: `?s_AddToPidlCache@CDeviceCache@@CAJPEAUDEVITEM_CACHE@@PEFAU_ITEMIDLIST@@@Z`
- size: `685`
- prototype: `static int(struct DEVITEM_CACHE *, struct _ITEMIDLIST *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000ce68`

## callees

- `0x18000bde4`
- `0x18001d3f0`
- `0x18001d6b0`
- `0x180022c04`
- `0x18002e0d8`
- `0x18002ff5c`
- `0x180055a6c`
- `0x18007559c`
- `0x180078010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001d595`
- `KERNEL32!GetLastError` at `0x18001d595`
- `KERNEL32!DeactivateActCtx` at `0x18001d5aa`
- `KERNEL32!DeactivateActCtx` at `0x18001d5aa`
- `KERNEL32!SetLastError` at `0x18001d5b6`
- `KERNEL32!SetLastError` at `0x18001d5b6`
- `SHELL32!__imp_ILRemoveLastID` at `0x18001d4a7`
- `SHELL32!__imp_ILRemoveLastID` at `0x18001d4a7`
- `SHELL32!__imp_ILClone` at `0x18001d481`
- `SHELL32!__imp_ILClone` at `0x18001d481`
- `SHELL32!__imp_ILIsParent` at `0x18001d4fd`
- `SHELL32!__imp_ILIsParent` at `0x18001d4fd`
- `SHELL32!__imp_ILGetSize` at `0x18001d465`
- `SHELL32!__imp_ILGetSize` at `0x18001d4d7`
- `SHELL32!__imp_ILGetSize` at `0x18001d465`
- `SHELL32!__imp_ILGetSize` at `0x18001d4d7`
- `SHELL32!__imp_ILFree` at `0x18001d51d`
- `SHELL32!__imp_ILFree` at `0x18001d656`
- `SHELL32!__imp_ILFree` at `0x18001d51d`
- `SHELL32!__imp_ILFree` at `0x18001d656`

## pseudocode

```c
__int64 __fastcall CDeviceCache::s_AddToPidlCache(struct DEVITEM_CACHE *a1, struct _ITEMIDLIST *a2)
{
  int **v2; // r14
  unsigned int v4; // ebx
  PVOID *v5; // rcx
  UINT v6; // r13d
  ITEMIDLIST *v7; // rax
  ITEMIDLIST *v8; // rdi
  int v9; // esi
  int *v10; // rcx
  int v11; // eax
  const ITEMIDLIST *Ptr; // rax
  const ITEMIDLIST *v13; // rbp
  UINT v14; // eax
  ITEMIDLIST *v15; // rax
  int *v16; // r14
  int v17; // eax
  unsigned int (__fastcall *v18)(int *, __int64, struct _ITEMIDLIST *); // rsi
  __int64 v19; // rax
  DWORD LastError; // ebp
  ULONG_PTR ulCookie; // [rsp+70h] [rbp+8h] BYREF

  v2 = (int **)((char *)a1 + 24);
  if ( !*((_QWORD *)a1 + 3) && !(unsigned int)CDPA_Base<PROPERTY_ITEM>::Create((char *)a1 + 24) )
  {
    v4 = -2147024882;
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v4;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids, 2147942414LL);
      v5 = (PVOID *)WPP_GLOBAL_Control;
    }
    goto LABEL_51;
  }
  v6 = ILGetSize(a2);
  if ( a2 )
  {
    v7 = ILClone(a2);
    v8 = v7;
    v4 = v7 == 0 ? 0x8007000E : 0;
    if ( v7 )
    {
      ILRemoveLastID(v7);
      v9 = 0;
      v4 = 1;
      while ( 1 )
      {
        v10 = *v2;
        v11 = *v2 ? *v10 : 0;
        if ( v9 >= v11 )
          break;
        Ptr = (const ITEMIDLIST *)IsolationAwareDPA_GetPtr(v10, v9);
        v13 = Ptr;
        if ( !Ptr )
          goto LABEL_23;
        v14 = ILGetSize(Ptr);
        if ( v14 == v6 && !memcmp_0(v13, a2, v14) )
          break;
        if ( ILIsParent(v8, v13, 1) )
        {
          v15 = (ITEMIDLIST *)IsolationAwareDPA_DeletePtr(*v2, (unsigned int)v9);
          if ( v15 )
            ILFree(v15);
          v9 = 0x7FFFFFFF;
          break;
        }
        ++v9;
      }
      v16 = *v2;
      if ( v16 )
        v17 = *v16;
      else
        v17 = 0;
      if ( v9 < v17 )
        goto LABEL_47;
      v18 = (unsigned int (__fastcall *)(int *, __int64, struct _ITEMIDLIST *))`IsolationAwareDPA_InsertPtr'::`2'::s_pfn;
      if ( !`IsolationAwareDPA_InsertPtr'::`2'::s_pfn )
      {
        ulCookie = 0;
        if ( !IsolationAwarePrivateT_SAbnPgpgk
          && IsolationAwarePrivateT_SqbjaYRiRY == (_DWORD)`IsolationAwareDPA_InsertPtr'::`2'::s_pfn
          && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
        {
          goto LABEL_23;
        }
        v19 = Dpa_dsaIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY("DPA_InsertPtr");
        v18 = (unsigned int (__fastcall *)(int *, __int64, struct _ITEMIDLIST *))v19;
        if ( !IsolationAwarePrivateT_SqbjaYRiRY )
        {
          if ( v19 )
          {
            v4 = 0;
            LastError = 0;
          }
          else
          {
            LastError = GetLastError();
          }
          DeactivateActCtx(0, ulCookie);
          if ( v4 )
            SetLastError(LastError);
        }
        if ( !v18 )
          goto LABEL_23;
        `IsolationAwareDPA_InsertPtr'::`2'::s_pfn = (__int64)v18;
      }
      if ( v18(v16, 0x7FFFFFFF, a2) != -1 )
      {
        v4 = 0;
LABEL_47:
        v5 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_48;
      }
LABEL_23:
      v4 = -2147467259;
      goto LABEL_47;
    }
  }
  else
  {
    v8 = 0;
    v4 = -2147024809;
  }
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_d7637b305d8b3afba9326780f352c02a_Traceguids, v4);
      v5 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 2) != 0 )
    {
      WPP_SF_d(v5[2], 15, WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids, v4);
      goto LABEL_47;
    }
  }
LABEL_48:
  if ( v8 )
  {
    ILFree(v8);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (v4 & 0x80000000) != 0 )
  {
LABEL_51:
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 2) != 0 )
      WPP_SF_d(v5[2], 16, WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x18001d3f0  push    rbx
0x18001d3f2  push    rbp
0x18001d3f3  push    rsi
0x18001d3f4  push    rdi
0x18001d3f5  push    r12
0x18001d3f7  push    r13
0x18001d3f9  push    r14
0x18001d3fb  push    r15
0x18001d3fd  sub     rsp, 28h
0x18001d401  lea     r14, [rcx+18h]
0x18001d405  mov     r12, rdx
0x18001d408  cmp     qword ptr [r14], 0
0x18001d40c  jnz     short loc_18001D462
0x18001d40e  mov     rcx, r14
0x18001d411  call    ?Create@?$CDPA_Base@UPROPERTY_ITEM@@@@QEAAHH@Z; CDPA_Base<PROPERTY_ITEM>::Create(int)
0x18001d416  test    eax, eax
0x18001d418  jnz     short loc_18001D462
0x18001d41a  mov     ebx, 8007000Eh
0x18001d41f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d426  lea     r15, WPP_GLOBAL_Control
0x18001d42d  cmp     rcx, r15
0x18001d430  jz      loc_18001D68A
0x18001d436  test    byte ptr [rcx+1Ch], 2
0x18001d43a  jz      loc_18001D667
0x18001d440  mov     rcx, [rcx+10h]
0x18001d444  lea     edx, [rax+0Eh]
0x18001d447  mov     r9d, ebx
0x18001d44a  lea     r8, WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids
0x18001d451  call    WPP_SF_d
0x18001d456  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d45d  jmp     loc_18001D667
0x18001d462  mov     rcx, r12; pidl
0x18001d465  call    cs:__imp_ILGetSize
0x18001d46b  lea     r15, WPP_GLOBAL_Control
0x18001d472  mov     r13d, eax
0x18001d475  test    r12, r12
0x18001d478  jz      loc_18001D5EC
0x18001d47e  mov     rcx, r12; pidl
0x18001d481  call    cs:__imp_ILClone
0x18001d487  mov     rcx, rax
0x18001d48a  mov     ebx, 8007000Eh
0x18001d48f  neg     rcx
0x18001d492  mov     rdi, rax
0x18001d495  sbb     edx, edx
0x18001d497  not     edx
0x18001d499  and     ebx, edx
0x18001d49b  test    rax, rax
0x18001d49e  jz      loc_18001D5F3
0x18001d4a4  mov     rcx, rax; pidl
0x18001d4a7  call    cs:__imp_ILRemoveLastID
0x18001d4ad  xor     esi, esi
0x18001d4af  lea     ebx, [rsi+1]
0x18001d4b2  mov     rcx, [r14]
0x18001d4b5  test    rcx, rcx
0x18001d4b8  jz      short loc_18001D4BE
0x18001d4ba  mov     eax, [rcx]
0x18001d4bc  jmp     short loc_18001D4C0
0x18001d4be  xor     eax, eax
0x18001d4c0  cmp     esi, eax
0x18001d4c2  jge     short loc_18001D528
0x18001d4c4  movsxd  rdx, esi
0x18001d4c7  call    IsolationAwareDPA_GetPtr
0x18001d4cc  mov     rbp, rax
0x18001d4cf  test    rax, rax
0x18001d4d2  jz      short loc_18001D535
0x18001d4d4  mov     rcx, rax; pidl
0x18001d4d7  call    cs:__imp_ILGetSize
0x18001d4dd  cmp     eax, r13d
0x18001d4e0  jnz     short loc_18001D4F4
0x18001d4e2  mov     r8d, eax; Size
0x18001d4e5  mov     rdx, r12; Buf2
0x18001d4e8  mov     rcx, rbp; Buf1
0x18001d4eb  call    memcmp_0
0x18001d4f0  test    eax, eax
0x18001d4f2  jz      short loc_18001D528
0x18001d4f4  mov     r8d, ebx; fImmediate
0x18001d4f7  mov     rdx, rbp; pidl2
0x18001d4fa  mov     rcx, rdi; pidl1
0x18001d4fd  call    cs:__imp_ILIsParent
0x18001d503  test    eax, eax
0x18001d505  jnz     short loc_18001D50B
0x18001d507  add     esi, ebx
0x18001d509  jmp     short loc_18001D4B2
0x18001d50b  mov     rcx, [r14]
0x18001d50e  mov     edx, esi
0x18001d510  call    IsolationAwareDPA_DeletePtr
0x18001d515  test    rax, rax
0x18001d518  jz      short loc_18001D523
0x18001d51a  mov     rcx, rax; pidl
0x18001d51d  call    cs:__imp_ILFree
0x18001d523  mov     esi, 7FFFFFFFh
0x18001d528  mov     r14, [r14]
0x18001d52b  test    r14, r14
0x18001d52e  jz      short loc_18001D53F
0x18001d530  mov     eax, [r14]
0x18001d533  jmp     short loc_18001D541
0x18001d535  mov     ebx, 80004005h
0x18001d53a  jmp     loc_18001D647
0x18001d53f  xor     eax, eax
0x18001d541  cmp     esi, eax
0x18001d543  jl      loc_18001D647
0x18001d549  mov     rsi, cs:?s_pfn@?1??IsolationAwareDPA_InsertPtr@@9@4P6AHPEAU_DPA@@HPEAX@ZEA; int (*`IsolationAwareDPA_InsertPtr'::`2'::s_pfn)(_DPA *,int,void *)
0x18001d550  test    rsi, rsi
0x18001d553  jnz     short loc_18001D5CC
0x18001d555  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, esi
0x18001d55b  mov     [rsp+68h+ulCookie], rsi
0x18001d560  jnz     short loc_18001D578
0x18001d562  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, esi
0x18001d568  jnz     short loc_18001D578
0x18001d56a  lea     rcx, [rsp+68h+ulCookie]; lpCookie
0x18001d56f  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18001d574  test    eax, eax
0x18001d576  jz      short loc_18001D535
0x18001d578  lea     rcx, aDpaInsertptr; "DPA_InsertPtr"
0x18001d57f  call    Dpa_dsaIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x18001d584  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18001d58b  mov     rsi, rax
0x18001d58e  jnz     short loc_18001D5BC
0x18001d590  test    rax, rax
0x18001d593  jnz     short loc_18001D59F
0x18001d595  call    cs:__imp_GetLastError
0x18001d59b  mov     ebp, eax
0x18001d59d  jmp     short loc_18001D5A3
0x18001d59f  xor     ebx, ebx
0x18001d5a1  xor     ebp, ebp
0x18001d5a3  mov     rdx, [rsp+68h+ulCookie]; ulCookie
0x18001d5a8  xor     ecx, ecx; dwFlags
0x18001d5aa  call    cs:__imp_DeactivateActCtx
0x18001d5b0  test    ebx, ebx
0x18001d5b2  jz      short loc_18001D5BC
0x18001d5b4  mov     ecx, ebp; dwErrCode
0x18001d5b6  call    cs:__imp_SetLastError
0x18001d5bc  test    rsi, rsi
0x18001d5bf  jz      loc_18001D535
0x18001d5c5  mov     cs:?s_pfn@?1??IsolationAwareDPA_InsertPtr@@9@4P6AHPEAU_DPA@@HPEAX@ZEA, rsi; int (*`IsolationAwareDPA_InsertPtr'::`2'::s_pfn)(_DPA *,int,void *)
0x18001d5cc  mov     r8, r12
0x18001d5cf  mov     edx, 7FFFFFFFh
0x18001d5d4  mov     rcx, r14
0x18001d5d7  mov     rax, rsi
0x18001d5da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5df  cmp     eax, 0FFFFFFFFh
0x18001d5e2  jz      loc_18001D535
0x18001d5e8  xor     ebx, ebx
0x18001d5ea  jmp     short loc_18001D647
0x18001d5ec  xor     edi, edi
0x18001d5ee  mov     ebx, 80070057h
0x18001d5f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d5fa  cmp     rcx, r15
0x18001d5fd  jz      short loc_18001D64E
0x18001d5ff  test    byte ptr [rcx+1Ch], 2
0x18001d603  jz      short loc_18001D624
0x18001d605  mov     rcx, [rcx+10h]
0x18001d609  lea     r8, WPP_d7637b305d8b3afba9326780f352c02a_Traceguids
0x18001d610  mov     edx, 46h ; 'F'
0x18001d615  mov     r9d, ebx
0x18001d618  call    WPP_SF_d
0x18001d61d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d624  cmp     rcx, r15
0x18001d627  jz      short loc_18001D64E
0x18001d629  test    byte ptr [rcx+1Ch], 2
0x18001d62d  jz      short loc_18001D64E
0x18001d62f  mov     rcx, [rcx+10h]
0x18001d633  lea     r8, WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids
0x18001d63a  mov     edx, 0Fh
0x18001d63f  mov     r9d, ebx
0x18001d642  call    WPP_SF_d
0x18001d647  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d64e  test    rdi, rdi
0x18001d651  jz      short loc_18001D663
0x18001d653  mov     rcx, rdi; pidl
0x18001d656  call    cs:__imp_ILFree
0x18001d65c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d663  test    ebx, ebx
0x18001d665  jns     short loc_18001D68A
0x18001d667  cmp     rcx, r15
0x18001d66a  jz      short loc_18001D68A
0x18001d66c  test    byte ptr [rcx+1Ch], 2
0x18001d670  jz      short loc_18001D68A
0x18001d672  mov     rcx, [rcx+10h]
0x18001d676  lea     r8, WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids
0x18001d67d  mov     edx, 10h
0x18001d682  mov     r9d, ebx
0x18001d685  call    WPP_SF_d
0x18001d68a  mov     eax, ebx
0x18001d68c  add     rsp, 28h
0x18001d690  pop     r15
0x18001d692  pop     r14
0x18001d694  pop     r13
0x18001d696  pop     r12
0x18001d698  pop     rdi
0x18001d699  pop     rsi
0x18001d69a  pop     rbp
0x18001d69b  pop     rbx
0x18001d69c  retn
```
