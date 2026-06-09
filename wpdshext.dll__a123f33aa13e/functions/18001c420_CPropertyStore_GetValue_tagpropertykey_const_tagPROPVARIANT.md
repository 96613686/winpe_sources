# CPropertyStore::GetValue(_tagpropertykey const &,tagPROPVARIANT *)

- ea: `0x18001c420`
- end: `0x18001c909`
- name: `?GetValue@CPropertyStore@@UEAAJAEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z`
- size: `1257`
- prototype: `int(CPropertyStore *__hidden this, const struct _tagpropertykey *, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001c420`
- `0x18001c910`
- `0x18001d6b0`
- `0x180022c04`
- `0x18002e0d8`
- `0x18002ff5c`
- `0x180078010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001c8af`
- `KERNEL32!GetLastError` at `0x18001c8af`
- `KERNEL32!DeactivateActCtx` at `0x18001c8be`
- `KERNEL32!DeactivateActCtx` at `0x18001c8d8`
- `KERNEL32!DeactivateActCtx` at `0x18001c8be`
- `KERNEL32!DeactivateActCtx` at `0x18001c8d8`
- `KERNEL32!SetLastError` at `0x18001c8c6`
- `KERNEL32!SetLastError` at `0x18001c8c6`
- `ole32!PropVariantCopy` at `0x18001c5dd`
- `ole32!PropVariantCopy` at `0x18001c5dd`
- `ole32!CoTaskMemAlloc` at `0x18001c71a`
- `ole32!CoTaskMemAlloc` at `0x18001c71a`
- `ole32!PropVariantClear` at `0x18001c4bc`
- `ole32!PropVariantClear` at `0x18001c839`
- `ole32!PropVariantClear` at `0x18001c4bc`
- `ole32!PropVariantClear` at `0x18001c839`

## pseudocode

```c
__int64 __fastcall CPropertyStore::GetValue(
        CPropertyStore *this,
        const struct _tagpropertykey *a2,
        struct tagPROPVARIANT *a3)
{
  __int64 v6; // rax
  DWORD pid; // eax
  int v8; // eax
  unsigned int v9; // ebx
  unsigned int i; // ebx
  __int64 (__fastcall *v11)(__int64, _QWORD); // rdi
  __int64 v12; // rsi
  __int64 v13; // rax
  __int64 v15; // rax
  PVOID *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // r14
  int v23; // edi
  __int64 v24; // rcx
  __int64 v25; // rsi
  int v26; // ebp
  unsigned int v27; // ebx
  BYTE *v28; // rax
  __int64 Ptr; // rax
  int v30; // ecx
  __int64 v31; // rax
  DWORD LastError; // edi
  unsigned int v33; // [rsp+60h] [rbp+18h] BYREF
  ULONG_PTR ulCookie; // [rsp+68h] [rbp+20h] BYREF

  v33 = 0;
  if ( !a3 )
  {
    v9 = -2147467261;
    goto LABEL_62;
  }
  *(_OWORD *)&a3->vt = 0;
  a3->bstrblobVal.pData = 0;
  v6 = *(_QWORD *)&WPD_DEVICE_PROPERTIES_V1.Data1 - *(_QWORD *)&a2->fmtid.Data1;
  if ( *(_QWORD *)&WPD_DEVICE_PROPERTIES_V1.Data1 == *(_QWORD *)&a2->fmtid.Data1 )
    v6 = *(_QWORD *)WPD_DEVICE_PROPERTIES_V1.Data4 - *(_QWORD *)a2->fmtid.Data4;
  if ( v6 )
  {
    pid = a2->pid;
    switch ( pid )
    {
      case 5u:
        v19 = *(_QWORD *)&PKEY_PercentFull.fmtid.Data1 - *(_QWORD *)&a2->fmtid.Data1;
        if ( *(_QWORD *)&PKEY_PercentFull.fmtid.Data1 == *(_QWORD *)&a2->fmtid.Data1 )
          v19 = *(_QWORD *)PKEY_PercentFull.fmtid.Data4 - *(_QWORD *)a2->fmtid.Data4;
        if ( !v19 )
        {
          v8 = CPropertyStore::_EnsureExtraProperties(this);
          v9 = v8;
          if ( v8 < 0 )
          {
            v16 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
              return v9;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
              goto LABEL_63;
            v17 = 19;
            goto LABEL_67;
          }
        }
        break;
      case 2u:
        v15 = *(_QWORD *)&PKEY_FreeSpace.fmtid.Data1 - *(_QWORD *)&a2->fmtid.Data1;
        if ( *(_QWORD *)&PKEY_FreeSpace.fmtid.Data1 == *(_QWORD *)&a2->fmtid.Data1 )
          v15 = *(_QWORD *)PKEY_FreeSpace.fmtid.Data4 - *(_QWORD *)a2->fmtid.Data4;
        if ( !v15 )
        {
          v8 = CPropertyStore::_EnsureExtraProperties(this);
          v9 = v8;
          if ( v8 < 0 )
          {
            v16 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
              return v9;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
              goto LABEL_63;
            v17 = 20;
            goto LABEL_67;
          }
        }
        break;
      case 7u:
        v20 = *(_QWORD *)&PKEY_Computer_DecoratedFreeSpace.fmtid.Data1 - *(_QWORD *)&a2->fmtid.Data1;
        if ( *(_QWORD *)&PKEY_Computer_DecoratedFreeSpace.fmtid.Data1 == *(_QWORD *)&a2->fmtid.Data1 )
          v20 = *(_QWORD *)PKEY_Computer_DecoratedFreeSpace.fmtid.Data4 - *(_QWORD *)a2->fmtid.Data4;
        if ( !v20 )
        {
          v8 = CPropertyStore::_EnsureExtraProperties(this);
          v9 = v8;
          if ( v8 < 0 )
          {
            v16 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
              return v9;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
              goto LABEL_63;
            v17 = 21;
            goto LABEL_67;
          }
          v8 = (*(__int64 (__fastcall **)(CPropertyStore *, unsigned int *))(*(_QWORD *)this + 24LL))(this, &v33);
          v9 = v8;
          if ( v8 < 0 )
          {
            v16 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
              return v9;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
              goto LABEL_63;
            v17 = 22;
            goto LABEL_67;
          }
          v22 = 0;
          v25 = 0;
          v23 = 0;
          v26 = 0;
          v27 = 0;
          if ( !v33 )
            goto LABEL_79;
          do
          {
            Ptr = IsolationAwareDPA_GetPtr(*((_QWORD *)this + 14), v27);
            if ( Ptr )
            {
              v30 = *(_DWORD *)(Ptr + 16);
              if ( v30 == 2 )
              {
                v21 = *(_QWORD *)&PKEY_FreeSpace.fmtid.Data1 - *(_QWORD *)Ptr;
                if ( *(_QWORD *)&PKEY_FreeSpace.fmtid.Data1 == *(_QWORD *)Ptr )
                  v21 = *(_QWORD *)PKEY_FreeSpace.fmtid.Data4 - *(_QWORD *)(Ptr + 8);
                if ( !v21 )
                {
                  v22 = *(_QWORD *)(Ptr + 32);
                  if ( v26 )
                    goto LABEL_59;
                  v23 = 1;
                }
              }
              else if ( v30 == 4 )
              {
                v24 = *(_QWORD *)&WPD_STORAGE_CAPACITY.fmtid.Data1 - *(_QWORD *)Ptr;
                if ( *(_QWORD *)&WPD_STORAGE_CAPACITY.fmtid.Data1 == *(_QWORD *)Ptr )
                  v24 = *(_QWORD *)WPD_STORAGE_CAPACITY.fmtid.Data4 - *(_QWORD *)(Ptr + 8);
                if ( !v24 )
                {
                  v25 = *(_QWORD *)(Ptr + 32);
                  v26 = 1;
                  if ( v23 )
                    goto LABEL_59;
                }
              }
            }
            ++v27;
          }
          while ( v27 < v33 );
          if ( !v23 )
            goto LABEL_79;
LABEL_59:
          if ( !v25 )
          {
LABEL_79:
            PropVariantClear(a3);
            return 0;
          }
          v28 = (BYTE *)CoTaskMemAlloc(0x10u);
          a3->bstrblobVal.pData = v28;
          if ( !v28 )
          {
            v9 = -2147024882;
            goto LABEL_62;
          }
          a3->vt = 4117;
          a3->lVal = 2;
          *(_QWORD *)v28 = v22;
          *((_QWORD *)a3->bstrblobVal.pData + 1) = v25;
          return 0;
        }
        break;
    }
  }
  else
  {
    v8 = CPropertyStore::_EnsureExtraProperties(this);
    v9 = v8;
    if ( v8 < 0 )
    {
      v16 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v9;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_63;
      v17 = 18;
      goto LABEL_67;
    }
  }
  v8 = (*(__int64 (__fastcall **)(CPropertyStore *, unsigned int *))(*(_QWORD *)this + 24LL))(this, &v33);
  v9 = v8;
  if ( v8 < 0 )
  {
    v16 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v9;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_63;
    v17 = 23;
LABEL_67:
    WPP_SF_d(v16[2], v17, WPP_eee6ab0784cc3755dd69d149bd4fe9da_Traceguids, (unsigned int)v8);
    goto LABEL_62;
  }
  PropVariantClear(a3);
  for ( i = 0; ; ++i )
  {
    if ( i >= v33 )
      return 0;
    v11 = (__int64 (__fastcall *)(__int64, _QWORD))`IsolationAwareDPA_GetPtr'::`2'::s_pfn;
    v12 = *((_QWORD *)this + 14);
    if ( !`IsolationAwareDPA_GetPtr'::`2'::s_pfn )
    {
      ulCookie = 0;
      if ( !IsolationAwarePrivateT_SAbnPgpgk
        && !IsolationAwarePrivateT_SqbjaYRiRY
        && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
      {
        continue;
      }
      v31 = Dpa_dsaIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY("DPA_GetPtr");
      v11 = (__int64 (__fastcall *)(__int64, _QWORD))v31;
      if ( IsolationAwarePrivateT_SqbjaYRiRY )
      {
        if ( !v31 )
          continue;
      }
      else
      {
        if ( !v31 )
        {
          LastError = GetLastError();
          DeactivateActCtx(0, ulCookie);
          SetLastError(LastError);
          continue;
        }
        DeactivateActCtx(0, ulCookie);
      }
      `IsolationAwareDPA_GetPtr'::`2'::s_pfn = (__int64)v11;
    }
    v13 = v11(v12, i);
    if ( v13 && a2->pid == *(_DWORD *)(v13 + 16) )
    {
      v18 = *(_QWORD *)&a2->fmtid.Data1 - *(_QWORD *)v13;
      if ( *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)v13 )
        v18 = *(_QWORD *)a2->fmtid.Data4 - *(_QWORD *)(v13 + 8);
      if ( !v18 )
        break;
    }
  }
  if ( *(_WORD *)(v13 + 24) != 10 )
  {
    v9 = PropVariantCopy(a3, (const PROPVARIANT *)(v13 + 24));
    goto LABEL_32;
  }
  v9 = *(_DWORD *)(v13 + 32);
  if ( v9 == -2147023728 )
    return 0;
LABEL_32:
  if ( (v9 & 0x80000000) == 0 )
    return v9;
LABEL_62:
  v16 = (PVOID *)WPP_GLOBAL_Control;
LABEL_63:
  if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 2) != 0 )
    WPP_SF_d(v16[2], 24, WPP_eee6ab0784cc3755dd69d149bd4fe9da_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x18001c420  mov     [rsp+arg_0], rbx
0x18001c425  mov     [rsp+arg_8], rbp
0x18001c42a  push    rsi
0x18001c42b  push    rdi
0x18001c42c  push    r12
0x18001c42e  push    r14
0x18001c430  push    r15
0x18001c432  sub     rsp, 20h
0x18001c436  mov     [rsp+48h+arg_10], 0
0x18001c43e  mov     r12, r8
0x18001c441  mov     r14, rdx
0x18001c444  mov     r15, rcx
0x18001c447  test    r8, r8
0x18001c44a  jz      loc_18001C771
0x18001c450  xor     eax, eax
0x18001c452  xorps   xmm0, xmm0
0x18001c455  movups  xmmword ptr [r8], xmm0
0x18001c459  mov     [r8+10h], rax
0x18001c45d  mov     rax, qword ptr cs:WPD_DEVICE_PROPERTIES_V1.Data1
0x18001c464  sub     rax, [rdx]
0x18001c467  jnz     short loc_18001C474
0x18001c469  mov     rax, qword ptr cs:WPD_DEVICE_PROPERTIES_V1.Data4
0x18001c470  sub     rax, [rdx+8]
0x18001c474  test    rax, rax
0x18001c477  jz      loc_18001C576
0x18001c47d  mov     eax, [rdx+10h]
0x18001c480  cmp     eax, 5
0x18001c483  jz      loc_18001C5F4
0x18001c489  cmp     eax, 2
0x18001c48c  jz      loc_18001C51C
0x18001c492  cmp     eax, 7
0x18001c495  jz      loc_18001C64A
0x18001c49b  mov     rax, [r15]
0x18001c49e  lea     rdx, [rsp+48h+arg_10]
0x18001c4a3  mov     rcx, r15
0x18001c4a6  mov     rax, [rax+18h]
0x18001c4aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c4af  mov     ebx, eax
0x18001c4b1  test    eax, eax
0x18001c4b3  js      loc_18001C846
0x18001c4b9  mov     rcx, r12; pvar
0x18001c4bc  call    cs:__imp_PropVariantClear
0x18001c4c2  xor     ebp, ebp
0x18001c4c4  xor     ebx, ebx
0x18001c4c6  cmp     ebx, [rsp+48h+arg_10]
0x18001c4ca  jnb     short loc_18001C503
0x18001c4cc  mov     rdi, cs:?s_pfn@?1??IsolationAwareDPA_GetPtr@@9@4P6APEAXPEAU_DPA@@_J@ZEA; void * (*`IsolationAwareDPA_GetPtr'::`2'::s_pfn)(_DPA *,__int64)
0x18001c4d3  mov     rsi, [r15+70h]
0x18001c4d7  test    rdi, rdi
0x18001c4da  jz      loc_18001C86C
0x18001c4e0  mov     edx, ebx
0x18001c4e2  mov     rcx, rsi
0x18001c4e5  mov     rax, rdi
0x18001c4e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c4ed  test    rax, rax
0x18001c4f0  jz      short loc_18001C4FF
0x18001c4f2  mov     ecx, [rax+10h]; this
0x18001c4f5  cmp     [r14+10h], ecx
0x18001c4f9  jz      loc_18001C5AC
0x18001c4ff  inc     ebx
0x18001c501  jmp     short loc_18001C4C6
0x18001c503  mov     eax, ebp
0x18001c505  mov     rbx, [rsp+48h+arg_0]
0x18001c50a  mov     rbp, [rsp+48h+arg_8]
0x18001c50f  add     rsp, 20h
0x18001c513  pop     r15
0x18001c515  pop     r14
0x18001c517  pop     r12
0x18001c519  pop     rdi
0x18001c51a  pop     rsi
0x18001c51b  retn
0x18001c51c  mov     rax, qword ptr cs:PKEY_FreeSpace.fmtid.Data1
0x18001c523  sub     rax, [rdx]
0x18001c526  jnz     short loc_18001C533
0x18001c528  mov     rax, qword ptr cs:PKEY_FreeSpace.fmtid.Data4
0x18001c52f  sub     rax, [rdx+8]
0x18001c533  test    rax, rax
0x18001c536  jnz     loc_18001C49B
0x18001c53c  call    ?_EnsureExtraProperties@CPropertyStore@@AEAAJXZ; CPropertyStore::_EnsureExtraProperties(void)
0x18001c541  mov     ebx, eax
0x18001c543  test    eax, eax
0x18001c545  jns     loc_18001C49B
0x18001c54b  mov     rcx, cs:WPP_GLOBAL_Control; this
0x18001c552  lea     rdi, WPP_GLOBAL_Control
0x18001c559  cmp     rcx, rdi
0x18001c55c  jz      loc_18001C5ED
0x18001c562  test    byte ptr [rcx+1Ch], 2
0x18001c566  jz      loc_18001C741
0x18001c56c  mov     edx, 14h
0x18001c571  jmp     loc_18001C77D
0x18001c576  call    ?_EnsureExtraProperties@CPropertyStore@@AEAAJXZ; CPropertyStore::_EnsureExtraProperties(void)
0x18001c57b  mov     ebx, eax
0x18001c57d  test    eax, eax
0x18001c57f  jns     loc_18001C49B
0x18001c585  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c58c  lea     rdi, WPP_GLOBAL_Control
0x18001c593  cmp     rcx, rdi
0x18001c596  jz      short loc_18001C5ED
0x18001c598  test    byte ptr [rcx+1Ch], 2
0x18001c59c  jz      loc_18001C741
0x18001c5a2  mov     edx, 12h
0x18001c5a7  jmp     loc_18001C77D
0x18001c5ac  mov     rcx, [r14]
0x18001c5af  sub     rcx, [rax]
0x18001c5b2  jnz     short loc_18001C5BC
0x18001c5b4  mov     rcx, [r14+8]
0x18001c5b8  sub     rcx, [rax+8]
0x18001c5bc  test    rcx, rcx
0x18001c5bf  jnz     loc_18001C4FF
0x18001c5c5  lea     rbx, [rax+18h]
0x18001c5c9  mov     eax, 0Ah
0x18001c5ce  cmp     ax, [rbx]
0x18001c5d1  jz      loc_18001C8F5
0x18001c5d7  mov     rdx, rbx; pvarSrc
0x18001c5da  mov     rcx, r12; pvarDest
0x18001c5dd  call    cs:__imp_PropVariantCopy
0x18001c5e3  mov     ebx, eax
0x18001c5e5  test    ebx, ebx
0x18001c5e7  js      loc_18001C733
0x18001c5ed  mov     eax, ebx
0x18001c5ef  jmp     loc_18001C505
0x18001c5f4  mov     rax, qword ptr cs:PKEY_PercentFull.fmtid.Data1
0x18001c5fb  sub     rax, [rdx]
0x18001c5fe  jnz     short loc_18001C60B
0x18001c600  mov     rax, qword ptr cs:PKEY_PercentFull.fmtid.Data4
0x18001c607  sub     rax, [rdx+8]
0x18001c60b  test    rax, rax
0x18001c60e  jnz     loc_18001C49B
0x18001c614  call    ?_EnsureExtraProperties@CPropertyStore@@AEAAJXZ; CPropertyStore::_EnsureExtraProperties(void)
0x18001c619  mov     ebx, eax
0x18001c61b  test    eax, eax
0x18001c61d  jns     loc_18001C49B
0x18001c623  mov     rcx, cs:WPP_GLOBAL_Control; this
0x18001c62a  lea     rdi, WPP_GLOBAL_Control
0x18001c631  cmp     rcx, rdi
0x18001c634  jz      short loc_18001C5ED
0x18001c636  test    byte ptr [rcx+1Ch], 2
0x18001c63a  jz      loc_18001C741
0x18001c640  mov     edx, 13h
0x18001c645  jmp     loc_18001C77D
0x18001c64a  mov     rax, qword ptr cs:PKEY_Computer_DecoratedFreeSpace.fmtid.Data1
0x18001c651  sub     rax, [rdx]
0x18001c654  jnz     short loc_18001C661
0x18001c656  mov     rax, qword ptr cs:PKEY_Computer_DecoratedFreeSpace.fmtid.Data4
0x18001c65d  sub     rax, [rdx+8]
0x18001c661  test    rax, rax
0x18001c664  jnz     loc_18001C49B
0x18001c66a  call    ?_EnsureExtraProperties@CPropertyStore@@AEAAJXZ; CPropertyStore::_EnsureExtraProperties(void)
0x18001c66f  mov     ebx, eax
0x18001c671  test    eax, eax
0x18001c673  jns     loc_18001C792
0x18001c679  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c680  lea     rdi, WPP_GLOBAL_Control
0x18001c687  cmp     rcx, rdi
0x18001c68a  jz      loc_18001C5ED
0x18001c690  test    byte ptr [rcx+1Ch], 2
0x18001c694  jz      loc_18001C741
0x18001c69a  mov     edx, 15h
0x18001c69f  jmp     loc_18001C77D
0x18001c6a4  mov     rcx, qword ptr cs:PKEY_FreeSpace.fmtid.Data1
0x18001c6ab  sub     rcx, [rax]
0x18001c6ae  jnz     short loc_18001C6BB
0x18001c6b0  mov     rcx, qword ptr cs:PKEY_FreeSpace.fmtid.Data4
0x18001c6b7  sub     rcx, [rax+8]
0x18001c6bb  test    rcx, rcx
0x18001c6be  jnz     short loc_18001C6F8
0x18001c6c0  mov     r14, [rax+20h]
0x18001c6c4  test    ebp, ebp
0x18001c6c6  jnz     short loc_18001C70C
0x18001c6c8  mov     edi, 1
0x18001c6cd  jmp     short loc_18001C6F8
0x18001c6cf  mov     rcx, qword ptr cs:WPD_STORAGE_CAPACITY.fmtid.Data1
0x18001c6d6  sub     rcx, [rax]
0x18001c6d9  jnz     short loc_18001C6E6
0x18001c6db  mov     rcx, qword ptr cs:WPD_STORAGE_CAPACITY.fmtid.Data4
0x18001c6e2  sub     rcx, [rax+8]
0x18001c6e6  test    rcx, rcx
0x18001c6e9  jnz     short loc_18001C6F8
0x18001c6eb  mov     rsi, [rax+20h]
0x18001c6ef  mov     ebp, 1
0x18001c6f4  test    edi, edi
0x18001c6f6  jnz     short loc_18001C70C
0x18001c6f8  inc     ebx
0x18001c6fa  cmp     ebx, [rsp+48h+arg_10]
0x18001c6fe  jb      loc_18001C7E5
0x18001c704  test    edi, edi
0x18001c706  jz      loc_18001C836
0x18001c70c  test    rsi, rsi
0x18001c70f  jz      loc_18001C836
0x18001c715  mov     ecx, 10h; cb
0x18001c71a  call    cs:__imp_CoTaskMemAlloc
0x18001c720  mov     [r12+10h], rax
0x18001c725  test    rax, rax
0x18001c728  jnz     loc_18001C813
0x18001c72e  mov     ebx, 8007000Eh
0x18001c733  lea     rdi, WPP_GLOBAL_Control
0x18001c73a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c741  cmp     rcx, rdi
0x18001c744  jz      loc_18001C5ED
0x18001c74a  test    byte ptr [rcx+1Ch], 2
0x18001c74e  jz      loc_18001C5ED
0x18001c754  mov     rcx, [rcx+10h]
0x18001c758  lea     r8, WPP_eee6ab0784cc3755dd69d149bd4fe9da_Traceguids
0x18001c75f  mov     edx, 18h
0x18001c764  mov     r9d, ebx
0x18001c767  call    WPP_SF_d
0x18001c76c  jmp     loc_18001C5ED
0x18001c771  mov     ebx, 80004003h
0x18001c776  jmp     short loc_18001C733
0x18001c778  mov     edx, 17h
0x18001c77d  mov     rcx, [rcx+10h]
0x18001c781  lea     r8, WPP_eee6ab0784cc3755dd69d149bd4fe9da_Traceguids
0x18001c788  mov     r9d, eax
0x18001c78b  call    WPP_SF_d
0x18001c790  jmp     short loc_18001C73A
0x18001c792  mov     rax, [r15]
0x18001c795  lea     rdx, [rsp+48h+arg_10]
0x18001c79a  mov     rcx, r15
0x18001c79d  mov     rax, [rax+18h]
0x18001c7a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c7a6  mov     ebx, eax
0x18001c7a8  test    eax, eax
0x18001c7aa  jns     short loc_18001C7D4
0x18001c7ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c7b3  lea     rdi, WPP_GLOBAL_Control
0x18001c7ba  cmp     rcx, rdi
0x18001c7bd  jz      loc_18001C5ED
0x18001c7c3  test    byte ptr [rcx+1Ch], 2
0x18001c7c7  jz      loc_18001C741
0x18001c7cd  mov     edx, 16h
0x18001c7d2  jmp     short loc_18001C77D
0x18001c7d4  xor     r14d, r14d
0x18001c7d7  xor     esi, esi
0x18001c7d9  xor     edi, edi
0x18001c7db  xor     ebp, ebp
0x18001c7dd  xor     ebx, ebx
0x18001c7df  cmp     [rsp+48h+arg_10], ebx
0x18001c7e3  jbe     short loc_18001C836
0x18001c7e5  mov     rcx, [r15+70h]
0x18001c7e9  mov     edx, ebx
0x18001c7eb  call    IsolationAwareDPA_GetPtr
0x18001c7f0  test    rax, rax
0x18001c7f3  jz      loc_18001C6F8
0x18001c7f9  mov     ecx, [rax+10h]
0x18001c7fc  cmp     ecx, 2
0x18001c7ff  jz      loc_18001C6A4
0x18001c805  cmp     ecx, 4
0x18001c808  jnz     loc_18001C6F8
0x18001c80e  jmp     loc_18001C6CF
0x18001c813  mov     word ptr [r12], 1015h
0x18001c81a  mov     dword ptr [r12+8], 2
0x18001c823  mov     [rax], r14
0x18001c826  mov     rax, [r12+10h]
0x18001c82b  mov     [rax+8], rsi
0x18001c82f  xor     eax, eax
0x18001c831  jmp     loc_18001C505
0x18001c836  mov     rcx, r12; pvar
0x18001c839  call    cs:__imp_PropVariantClear
0x18001c83f  xor     eax, eax
0x18001c841  jmp     loc_18001C505
0x18001c846  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c84d  lea     rdi, WPP_GLOBAL_Control
0x18001c854  cmp     rcx, rdi
0x18001c857  jz      loc_18001C5ED
0x18001c85d  test    byte ptr [rcx+1Ch], 2
0x18001c861  jz      loc_18001C741
0x18001c867  jmp     loc_18001C778
0x18001c86c  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, ebp
0x18001c872  mov     [rsp+48h+ulCookie], rbp
0x18001c877  jnz     short loc_18001C893
0x18001c879  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, ebp
0x18001c87f  jnz     short loc_18001C893
0x18001c881  lea     rcx, [rsp+48h+ulCookie]; lpCookie
0x18001c886  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18001c88b  test    eax, eax
0x18001c88d  jz      loc_18001C4FF
0x18001c893  lea     rcx, aDpaGetptr; "DPA_GetPtr"
0x18001c89a  call    Dpa_dsaIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x18001c89f  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, ebp
0x18001c8a5  mov     rdi, rax
0x18001c8a8  jnz     short loc_18001C8E0
0x18001c8aa  test    rax, rax
0x18001c8ad  jnz     short loc_18001C8D1
0x18001c8af  call    cs:__imp_GetLastError
0x18001c8b5  mov     rdx, [rsp+48h+ulCookie]; ulCookie
0x18001c8ba  xor     ecx, ecx; dwFlags
0x18001c8bc  mov     edi, eax
0x18001c8be  call    cs:__imp_DeactivateActCtx
0x18001c8c4  mov     ecx, edi; dwErrCode
0x18001c8c6  call    cs:__imp_SetLastError
0x18001c8cc  jmp     loc_18001C4FF
0x18001c8d1  mov     rdx, [rsp+48h+ulCookie]; ulCookie
0x18001c8d6  xor     ecx, ecx; dwFlags
0x18001c8d8  call    cs:__imp_DeactivateActCtx
0x18001c8de  jmp     short loc_18001C8E9
0x18001c8e0  test    rdi, rdi
0x18001c8e3  jz      loc_18001C4FF
0x18001c8e9  mov     cs:?s_pfn@?1??IsolationAwareDPA_GetPtr@@9@4P6APEAXPEAU_DPA@@_J@ZEA, rdi; void * (*`IsolationAwareDPA_GetPtr'::`2'::s_pfn)(_DPA *,__int64)
0x18001c8f0  jmp     loc_18001C4E0
0x18001c8f5  mov     ebx, [rbx+8]
  ... truncated ...
```
