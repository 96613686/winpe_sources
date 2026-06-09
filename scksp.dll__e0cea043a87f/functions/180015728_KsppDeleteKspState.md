# KsppDeleteKspState

- ea: `0x180015728`
- end: `0x180015944`
- name: `KsppDeleteKspState`
- size: `540`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180009f20`

## callees

- `0x180009e82`
- `0x18000a408`
- `0x18000d2a8`
- `0x180011fd8`
- `0x1800134fc`
- `0x180015728`
- `0x18002ce34`
- `0x180037070`
- `0x180037258`
- `0x1800374f4`
- `0x18003af5c`
- `0x18003b408`
- `0x18003b920`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800157db`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800157f1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180015807`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800157db`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800157f1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180015807`
- `ncrypt!NCryptFreeObject` at `0x180015915`
- `ncrypt!NCryptFreeObject` at `0x180015915`

## pseudocode

```c
__int64 KsppDeleteKspState()
{
  int v0; // eax
  __int64 v1; // rcx
  char v2; // bl
  _QWORD *v3; // rcx
  int v4; // edx
  int v5; // edx
  int v6; // r8d
  int v7; // eax
  __int64 v8; // rcx
  unsigned int v9; // ebx
  __int64 v10; // rsi
  struct _CARD_STATE *v11; // rdi
  _QWORD v13[5]; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v14; // [rsp+60h] [rbp+8h] BYREF
  __int64 v15; // [rsp+68h] [rbp+10h] BYREF

  v15 = 0;
  v14 = 0;
  v0 = HtDismantleHandleTable();
  v2 = v0;
  if ( v0 )
  {
    WppTraceIndent(v1, 2);
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v4 = 64;
LABEL_6:
      WPP_SF_sd(v3[2], v4, (unsigned int)&WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids, (_DWORD)WPP_pszIndent, v2);
      return 0;
    }
    return 0;
  }
  I_TransactionManagerCleanup((struct _TRANSACTION_MANAGER_STATE *)g_pTransactionManagerState, 1);
  g_pTransactionManagerState = 0;
  if ( dword_18004C270 )
    DeleteCriticalSection(&stru_18004C248);
  if ( dword_18004C238 )
    DeleteCriticalSection(&stru_18004C210);
  if ( dword_18004C208 )
    DeleteCriticalSection(&g_KspState);
  if ( !qword_18004C240 )
  {
LABEL_24:
    if ( phProvider )
      NCryptFreeObject(phProvider);
    memset_0(&g_KspState, 0, 0xE8u);
    return 0;
  }
  v7 = ScCacheEnumItems(qword_18004C240, v5, v6, (unsigned int)&v15, (__int64)&v14);
  v2 = v7;
  if ( !v7 )
  {
    v9 = v14;
    v10 = v15;
    while ( v9 )
    {
      v11 = **(struct _CARD_STATE ***)(v10 + 16LL * --v9 + 8);
      if ( !(unsigned int)KspEnterCriticalSection((char *)v11 + 624) )
      {
        v13[0] = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
        v13[1] = (char *)v11 + 624;
        TransactionManagerForceEndTransaction(v11);
        v13[0] = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
        Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(v13);
      }
      CardStateReleaseRef(v11, 1);
    }
    ScCacheFreeEnumItems(qword_18004C240, v10, v14);
    ScCacheDeleteCache(qword_18004C240);
    qword_18004C240 = 0;
    goto LABEL_24;
  }
  WppTraceIndent(v8, 2);
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v4 = 65;
    goto LABEL_6;
  }
  return 0;
}

```

## disassembly

```asm
0x180015728  mov     rax, rsp
0x18001572b  mov     [rax+18h], rbx
0x18001572f  mov     [rax+20h], rbp
0x180015733  push    rsi
0x180015734  push    rdi
0x180015735  push    r15
0x180015737  sub     rsp, 40h
0x18001573b  mov     qword ptr [rax+10h], 0
0x180015743  mov     dword ptr [rax+8], 0
0x18001574a  call    HtDismantleHandleTable
0x18001574f  mov     ebx, eax
0x180015751  test    eax, eax
0x180015753  jz      short loc_1800157AF
0x180015755  mov     edx, 2
0x18001575a  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001575f  mov     rcx, cs:WPP_GLOBAL_Control
0x180015766  lea     rdx, WPP_GLOBAL_Control
0x18001576d  cmp     rcx, rdx
0x180015770  jz      loc_18001592F
0x180015776  test    byte ptr [rcx+1Ch], 1
0x18001577a  jz      loc_18001592F
0x180015780  cmp     byte ptr [rcx+19h], 2
0x180015784  jb      loc_18001592F
0x18001578a  mov     edx, 40h ; '@'
0x18001578f  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180015796  lea     r8, WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids
0x18001579d  mov     rcx, [rcx+10h]
0x1800157a1  mov     dword ptr [rsp+58h+var_38], ebx
0x1800157a5  call    WPP_SF_sd
0x1800157aa  jmp     loc_18001592F
0x1800157af  mov     rcx, cs:?g_pTransactionManagerState@@3PEAU_TRANSACTION_MANAGER_STATE@@EA; struct _TRANSACTION_MANAGER_STATE *
0x1800157b6  mov     edx, 1; int
0x1800157bb  call    ?I_TransactionManagerCleanup@@YAXPEAU_TRANSACTION_MANAGER_STATE@@H@Z; I_TransactionManagerCleanup(_TRANSACTION_MANAGER_STATE *,int)
0x1800157c0  cmp     cs:dword_18004C270, 0
0x1800157c7  mov     cs:?g_pTransactionManagerState@@3PEAU_TRANSACTION_MANAGER_STATE@@EA, 0; _TRANSACTION_MANAGER_STATE * g_pTransactionManagerState
0x1800157d2  jz      short loc_1800157E1
0x1800157d4  lea     rcx, stru_18004C248; lpCriticalSection
0x1800157db  call    cs:__imp_DeleteCriticalSection
0x1800157e1  cmp     cs:dword_18004C238, 0
0x1800157e8  jz      short loc_1800157F7
0x1800157ea  lea     rcx, stru_18004C210; lpCriticalSection
0x1800157f1  call    cs:__imp_DeleteCriticalSection
0x1800157f7  cmp     cs:dword_18004C208, 0
0x1800157fe  jz      short loc_18001580D
0x180015800  lea     rcx, g_KspState; lpCriticalSection
0x180015807  call    cs:__imp_DeleteCriticalSection
0x18001580d  mov     rcx, cs:qword_18004C240
0x180015814  test    rcx, rcx
0x180015817  jz      loc_180015909
0x18001581d  lea     rax, [rsp+58h+arg_0]
0x180015822  lea     r9, [rsp+58h+arg_8]
0x180015827  mov     [rsp+58h+var_38], rax
0x18001582c  call    ScCacheEnumItems
0x180015831  mov     ebx, eax
0x180015833  test    eax, eax
0x180015835  jz      short loc_180015876
0x180015837  mov     edx, 2
0x18001583c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180015841  mov     rcx, cs:WPP_GLOBAL_Control
0x180015848  lea     rdx, WPP_GLOBAL_Control
0x18001584f  cmp     rcx, rdx
0x180015852  jz      loc_18001592F
0x180015858  test    byte ptr [rcx+1Ch], 1
0x18001585c  jz      loc_18001592F
0x180015862  cmp     byte ptr [rcx+19h], 2
0x180015866  jb      loc_18001592F
0x18001586c  mov     edx, 41h ; 'A'
0x180015871  jmp     loc_18001578F
0x180015876  mov     ebx, [rsp+58h+arg_0]
0x18001587a  mov     rsi, [rsp+58h+arg_8]
0x18001587f  test    ebx, ebx
0x180015881  jz      short loc_1800158DE
0x180015883  lea     r15, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x18001588a  dec     ebx
0x18001588c  mov     eax, ebx
0x18001588e  add     rax, rax
0x180015891  mov     rax, [rsi+rax*8+8]
0x180015896  mov     rdi, [rax]
0x180015899  lea     rbp, [rdi+270h]
0x1800158a0  mov     rcx, rbp
0x1800158a3  call    KspEnterCriticalSection
0x1800158a8  test    eax, eax
0x1800158aa  jnz     short loc_1800158CD
0x1800158ac  mov     rcx, rdi; struct _CARD_STATE *
0x1800158af  mov     [rsp+58h+var_28], r15
0x1800158b4  mov     [rsp+58h+var_20], rbp
0x1800158b9  call    TransactionManagerForceEndTransaction
0x1800158be  lea     rcx, [rsp+58h+var_28]
0x1800158c3  mov     [rsp+58h+var_28], r15
0x1800158c8  call    ?Close@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(void)
0x1800158cd  mov     edx, 1
0x1800158d2  mov     rcx, rdi
0x1800158d5  call    CardStateReleaseRef
0x1800158da  test    ebx, ebx
0x1800158dc  jnz     short loc_18001588A
0x1800158de  mov     r8d, [rsp+58h+arg_0]
0x1800158e3  mov     rdx, rsi
0x1800158e6  mov     rcx, cs:qword_18004C240
0x1800158ed  call    ScCacheFreeEnumItems
0x1800158f2  mov     rcx, cs:qword_18004C240
0x1800158f9  call    ScCacheDeleteCache
0x1800158fe  mov     cs:qword_18004C240, 0
0x180015909  mov     rcx, cs:phProvider; hObject
0x180015910  test    rcx, rcx
0x180015913  jz      short loc_18001591B
0x180015915  call    cs:__imp_NCryptFreeObject
0x18001591b  xor     edx, edx; Val
0x18001591d  lea     rcx, g_KspState; void *
0x180015924  mov     r8d, 0E8h; Size
0x18001592a  call    memset_0
0x18001592f  mov     rbx, [rsp+58h+arg_10]
0x180015934  xor     eax, eax
0x180015936  mov     rbp, [rsp+58h+arg_18]
0x18001593b  add     rsp, 40h
0x18001593f  pop     r15
0x180015941  pop     rdi
0x180015942  pop     rsi
0x180015943  retn
```
