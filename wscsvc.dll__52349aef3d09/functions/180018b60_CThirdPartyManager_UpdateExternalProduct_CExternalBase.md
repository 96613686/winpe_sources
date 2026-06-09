# CThirdPartyManager::UpdateExternalProduct(CExternalBase *)

- ea: `0x180018b60`
- end: `0x180018d66`
- name: `?UpdateExternalProduct@CThirdPartyManager@@QEAAJPEAVCExternalBase@@@Z`
- size: `518`
- prototype: `__int64 __fastcall(CThirdPartyManager *__hidden this, struct CExternalBase *)`
- caller_count: `9`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180016d50`
- `0x180024630`
- `0x180024b40`
- `0x180025520`
- `0x180026450`
- `0x18002fc00`
- `0x180037460`
- `0x180038a1c`
- `0x180038b20`

## callees

- `0x180008e48`
- `0x180018b60`
- `0x180018d70`
- `0x18001fe40`
- `0x180020018`
- `0x1800202e8`
- `0x180029158`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180018c3e`
- `msvcrt!_wcsicmp` at `0x180018c3e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018c65`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018cbc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018ccf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018c65`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018cbc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018ccf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018bce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018bce`

## pseudocode

```c
__int64 __fastcall CThirdPartyManager::UpdateExternalProduct(CThirdPartyManager *this, struct CExternalBase *a2)
{
  unsigned int v5; // esi
  int v6; // r12d
  _QWORD *v7; // rax
  _QWORD *i; // rbx
  const wchar_t **v9; // r14
  _QWORD *v10; // rcx
  const wchar_t **j; // r15
  _WORD *v12; // rax
  int v13; // eax

  if ( a2 )
  {
    v5 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    v6 = 0;
    v7 = (_QWORD *)(*((_QWORD *)this + 7) + 56LL);
    for ( i = (_QWORD *)*v7; !i[2]; i = (_QWORD *)*i )
      ;
    if ( i == v7 )
      i = 0;
    v9 = (const wchar_t **)((char *)a2 + 8);
    do
    {
      if ( !i )
        goto LABEL_24;
      v10 = (_QWORD *)*i;
      for ( j = (const wchar_t **)i[2]; !v10[2]; v10 = (_QWORD *)*v10 )
        ;
      v9 = (const wchar_t **)((char *)a2 + 8);
      i = 0;
      if ( v10 != (_QWORD *)(*((_QWORD *)this + 7) + 56LL) )
        i = v10;
    }
    while ( _wcsicmp(*v9, j[1]) );
    v12 = (_WORD *)*((_QWORD *)a2 + 2);
    if ( v12 && !*v12 )
    {
      CThirdPartyManager::RemoveExternalProduct(this, a2);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
      return v5;
    }
    v6 = 1;
    v13 = CExternalBase::CopyValuesFrom((CExternalBase *)j, (const unsigned __int16 **)a2);
    v5 = v13;
    if ( v13 >= 0
      || WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
LABEL_24:
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
      if ( !v6 )
      {
        if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_945edad5fd7435d1f807bc12083ac763_Traceguids, *v9);
        }
        v5 = CThirdPartyManager::AddExternalProduct(this, a2);
      }
      if ( (v5 & 0x80000000) == 0 )
        return v5;
    }
    else
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        WPP_945edad5fd7435d1f807bc12083ac763_Traceguids,
        (unsigned int)v13);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    }
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_945edad5fd7435d1f807bc12083ac763_Traceguids, v5);
    }
    return v5;
  }
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_945edad5fd7435d1f807bc12083ac763_Traceguids);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180018b60  push    rbp
0x180018b62  push    rdi
0x180018b63  sub     rsp, 38h
0x180018b67  mov     rdi, rdx
0x180018b6a  mov     rbp, rcx
0x180018b6d  test    rdx, rdx
0x180018b70  jnz     short loc_180018BAA
0x180018b72  mov     rcx, cs:WPP_GLOBAL_Control
0x180018b79  lea     rax, WPP_GLOBAL_Control
0x180018b80  cmp     rcx, rax
0x180018b83  jz      short loc_180018BA0
0x180018b85  test    byte ptr [rcx+1Ch], 1
0x180018b89  jz      short loc_180018BA0
0x180018b8b  mov     rcx, [rcx+10h]
0x180018b8f  lea     r8, WPP_945edad5fd7435d1f807bc12083ac763_Traceguids
0x180018b96  mov     edx, 0Dh
0x180018b9b  call    WPP_SF_
0x180018ba0  mov     eax, 80070057h
0x180018ba5  jmp     loc_180018D5F
0x180018baa  mov     [rsp+48h+arg_0], rbx
0x180018baf  add     rcx, 10h; lpCriticalSection
0x180018bb3  mov     [rsp+48h+arg_8], rsi
0x180018bb8  xor     esi, esi
0x180018bba  mov     [rsp+48h+arg_10], r12
0x180018bbf  mov     [rsp+48h+var_18], r13
0x180018bc4  mov     [rsp+48h+var_20], r14
0x180018bc9  mov     [rsp+48h+var_28], r15
0x180018bce  call    cs:__imp_EnterCriticalSection
0x180018bd4  mov     rax, [rbp+38h]
0x180018bd8  xor     r12d, r12d
0x180018bdb  add     rax, 38h ; '8'
0x180018bdf  mov     rbx, [rax]
0x180018be2  cmp     [rbx+10h], rsi
0x180018be6  jnz     short loc_180018BF1
0x180018be8  mov     rbx, [rbx]
0x180018beb  cmp     [rbx+10h], rsi
0x180018bef  jz      short loc_180018BE8
0x180018bf1  cmp     rbx, rax
0x180018bf4  jnz     short loc_180018BF8
0x180018bf6  xor     ebx, ebx
0x180018bf8  lea     r14, [rdi+8]
0x180018bfc  lea     r15, WPP_GLOBAL_Control
0x180018c03  test    rbx, rbx
0x180018c06  jz      loc_180018CCB
0x180018c0c  mov     rcx, [rbx]
0x180018c0f  mov     rax, [rbp+38h]
0x180018c13  mov     r15, [rbx+10h]
0x180018c17  cmp     [rcx+10h], rsi
0x180018c1b  jnz     short loc_180018C26
0x180018c1d  mov     rcx, [rcx]
0x180018c20  cmp     [rcx+10h], rsi
0x180018c24  jz      short loc_180018C1D
0x180018c26  mov     rdx, [r15+8]; String2
0x180018c2a  lea     r14, [rdi+8]
0x180018c2e  add     rax, 38h ; '8'
0x180018c32  xor     ebx, ebx
0x180018c34  cmp     rcx, rax
0x180018c37  cmovnz  rbx, rcx
0x180018c3b  mov     rcx, [r14]; String1
0x180018c3e  call    cs:__imp__wcsicmp
0x180018c44  test    eax, eax
0x180018c46  jnz     short loc_180018BFC
0x180018c48  mov     rax, [rdi+10h]
0x180018c4c  test    rax, rax
0x180018c4f  jz      short loc_180018C70
0x180018c51  cmp     [rax], si
0x180018c54  jnz     short loc_180018C70
0x180018c56  mov     rdx, rdi; struct CExternalBase *
0x180018c59  mov     rcx, rbp; this
0x180018c5c  call    ?RemoveExternalProduct@CThirdPartyManager@@QEAAJPEAVCExternalBase@@@Z; CThirdPartyManager::RemoveExternalProduct(CExternalBase *)
0x180018c61  lea     rcx, [rbp+10h]; lpCriticalSection
0x180018c65  call    cs:__imp_LeaveCriticalSection
0x180018c6b  jmp     loc_180018D3F
0x180018c70  mov     rdx, rdi; struct CExternalBase *
0x180018c73  mov     rcx, r15; this
0x180018c76  mov     r12d, 1
0x180018c7c  call    ?CopyValuesFrom@CExternalBase@@QEAAJPEAV1@@Z; CExternalBase::CopyValuesFrom(CExternalBase *)
0x180018c81  mov     esi, eax
0x180018c83  test    eax, eax
0x180018c85  jns     short loc_180018CC4
0x180018c87  mov     rcx, cs:WPP_GLOBAL_Control
0x180018c8e  lea     r15, WPP_GLOBAL_Control
0x180018c95  cmp     rcx, r15
0x180018c98  jz      short loc_180018CCB
0x180018c9a  test    [rcx+1Ch], r12b
0x180018c9e  jz      short loc_180018CCB
0x180018ca0  mov     rcx, [rcx+10h]
0x180018ca4  lea     r8, WPP_945edad5fd7435d1f807bc12083ac763_Traceguids
0x180018cab  mov     edx, 0Eh
0x180018cb0  mov     r9d, eax
0x180018cb3  call    WPP_SF_d
0x180018cb8  lea     rcx, [rbp+10h]; lpCriticalSection
0x180018cbc  call    cs:__imp_LeaveCriticalSection
0x180018cc2  jmp     short loc_180018D15
0x180018cc4  lea     r15, WPP_GLOBAL_Control
0x180018ccb  lea     rcx, [rbp+10h]; lpCriticalSection
0x180018ccf  call    cs:__imp_LeaveCriticalSection
0x180018cd5  test    r12d, r12d
0x180018cd8  jnz     short loc_180018D11
0x180018cda  mov     rcx, cs:WPP_GLOBAL_Control
0x180018ce1  cmp     rcx, r15
0x180018ce4  jz      short loc_180018D04
0x180018ce6  test    byte ptr [rcx+1Ch], 4
0x180018cea  jz      short loc_180018D04
0x180018cec  mov     r9, [r14]
0x180018cef  lea     r8, WPP_945edad5fd7435d1f807bc12083ac763_Traceguids
0x180018cf6  mov     rcx, [rcx+10h]
0x180018cfa  mov     edx, 0Fh
0x180018cff  call    WPP_SF_S
0x180018d04  mov     rdx, rdi; struct CExternalBase *
0x180018d07  mov     rcx, rbp; this
0x180018d0a  call    ?AddExternalProduct@CThirdPartyManager@@QEAAJPEAVCExternalBase@@@Z; CThirdPartyManager::AddExternalProduct(CExternalBase *)
0x180018d0f  mov     esi, eax
0x180018d11  test    esi, esi
0x180018d13  jns     short loc_180018D3F
0x180018d15  mov     rcx, cs:WPP_GLOBAL_Control
0x180018d1c  cmp     rcx, r15
0x180018d1f  jz      short loc_180018D3F
0x180018d21  test    byte ptr [rcx+1Ch], 1
0x180018d25  jz      short loc_180018D3F
0x180018d27  mov     rcx, [rcx+10h]
0x180018d2b  lea     r8, WPP_945edad5fd7435d1f807bc12083ac763_Traceguids
0x180018d32  mov     edx, 10h
0x180018d37  mov     r9d, esi
0x180018d3a  call    WPP_SF_d
0x180018d3f  mov     r15, [rsp+48h+var_28]
0x180018d44  mov     eax, esi
0x180018d46  mov     rsi, [rsp+48h+arg_8]
0x180018d4b  mov     r14, [rsp+48h+var_20]
0x180018d50  mov     r13, [rsp+48h+var_18]
0x180018d55  mov     r12, [rsp+48h+arg_10]
0x180018d5a  mov     rbx, [rsp+48h+arg_0]
0x180018d5f  add     rsp, 38h
0x180018d63  pop     rdi
0x180018d64  pop     rbp
0x180018d65  retn
```
