# I_UpdateCardState(_CARD_STATE *,ushort *,int)

- ea: `0x18002cb34`
- end: `0x18002ccf1`
- name: `?I_UpdateCardState@@YAKPEAU_CARD_STATE@@PEAGH@Z`
- size: `445`
- prototype: `unsigned int(struct _CARD_STATE *, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x18002e7a0`

## callees

- `0x18000a408`
- `0x180011fd8`
- `0x180013734`
- `0x180013c94`
- `0x18002cb34`
- `0x18002e65c`
- `0x18002eb6c`
- `0x1800307d0`
- `0x180037070`

## pseudocode

```c
__int64 __fastcall I_UpdateCardState(struct _CARD_STATE *a1, unsigned __int16 *a2, int a3)
{
  __int64 v3; // r14
  PVOID v7; // rcx
  unsigned int CardActivityCount; // edi
  int v9; // r9d
  _DWORD *v10; // rcx
  SCARDCONTEXT v11; // rcx
  int v12; // esi
  bool v13; // zf
  __int64 v14; // rcx

  v3 = *((_QWORD *)a1 + 1);
  WppTraceIndent((__int64)a1, 0);
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids, WPP_pszIndent);
  }
  if ( *((_QWORD *)a1 + 1) )
  {
    v11 = *(_QWORD *)(v3 + 96);
    CardActivityCount = 0;
    v12 = 0;
    if ( v11 )
    {
      CardActivityCount = GetCardActivityCount(v11);
      if ( !CardActivityCount )
      {
        v13 = *((_DWORD *)a1 + 176) == 0;
        *((_DWORD *)a1 + 176) = 0;
        LOBYTE(v12) = !v13;
      }
    }
    v10 = (_DWORD *)*((_QWORD *)a1 + 1);
    if ( *v10 >= 6u && *((_DWORD *)a1 + 174) == 2 )
    {
      if ( !a3 && !CardActivityCount && !v12 )
        goto LABEL_20;
      ScCacheDeleteCache(*((_QWORD *)a1 + 84));
      v14 = *((_QWORD *)a1 + 85);
      *((_QWORD *)a1 + 84) = 0;
      ScCacheDeleteCache(v14);
      *((_QWORD *)a1 + 85) = 0;
      InitializeCacheHandles(a1);
    }
    if ( a3 )
      goto LABEL_21;
LABEL_20:
    StringCbCopyW((unsigned __int16 *)a1 + 16, 0x208u, a2);
    goto LABEL_21;
  }
  CardActivityCount = 87;
  WppTraceIndent((__int64)v7, 2u);
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_ss(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      41,
      (unsigned int)WPP_49528bda70d5313d10aecefe918ddecf_Traceguids,
      v9,
      (__int64)"pCardState->pCardData");
  }
LABEL_21:
  WppTraceIndent((__int64)v10, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      42,
      (unsigned int)WPP_49528bda70d5313d10aecefe918ddecf_Traceguids,
      (_DWORD)WPP_pszIndent,
      CardActivityCount);
  }
  return CardActivityCount;
}

```

## disassembly

```asm
0x18002cb34  push    rbx
0x18002cb36  push    rbp
0x18002cb37  push    rsi
0x18002cb38  push    rdi
0x18002cb39  push    r14
0x18002cb3b  push    r15
0x18002cb3d  sub     rsp, 38h
0x18002cb41  mov     r14, [rcx+8]
0x18002cb45  mov     r15, rdx
0x18002cb48  xor     edx, edx
0x18002cb4a  mov     [rsp+68h+arg_0], 0
0x18002cb52  mov     ebp, r8d
0x18002cb55  mov     rbx, rcx
0x18002cb58  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002cb5d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cb64  lea     rax, WPP_GLOBAL_Control
0x18002cb6b  cmp     rcx, rax
0x18002cb6e  jz      short loc_18002CB98
0x18002cb70  test    byte ptr [rcx+1Ch], 2
0x18002cb74  jz      short loc_18002CB98
0x18002cb76  cmp     byte ptr [rcx+19h], 5
0x18002cb7a  jb      short loc_18002CB98
0x18002cb7c  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002cb83  lea     r8, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids
0x18002cb8a  mov     rcx, [rcx+10h]
0x18002cb8e  mov     edx, 28h ; '('
0x18002cb93  call    WPP_SF_s
0x18002cb98  cmp     qword ptr [rbx+8], 0
0x18002cb9d  jnz     short loc_18002CBFB
0x18002cb9f  mov     edi, 57h ; 'W'
0x18002cba4  lea     edx, [rdi-55h]
0x18002cba7  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002cbac  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cbb3  lea     rbx, WPP_GLOBAL_Control
0x18002cbba  cmp     rcx, rbx
0x18002cbbd  jz      loc_18002CCA0
0x18002cbc3  test    byte ptr [rcx+1Ch], 1
0x18002cbc7  jz      loc_18002CCA0
0x18002cbcd  cmp     byte ptr [rcx+19h], 2
0x18002cbd1  jb      loc_18002CCA0
0x18002cbd7  mov     rcx, [rcx+10h]
0x18002cbdb  lea     rax, aPcardstatePcar; "pCardState->pCardData"
0x18002cbe2  lea     edx, [rdi-2Eh]
0x18002cbe5  mov     [rsp+68h+var_48], rax
0x18002cbea  lea     r8, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids
0x18002cbf1  call    WPP_SF_ss
0x18002cbf6  jmp     loc_18002CCA0
0x18002cbfb  mov     rcx, [r14+60h]; hContext
0x18002cbff  xor     edi, edi
0x18002cc01  xor     esi, esi
0x18002cc03  test    rcx, rcx
0x18002cc06  jz      short loc_18002CC30
0x18002cc08  lea     rdx, [rbx+20h]
0x18002cc0c  lea     r8, [rsp+68h+arg_0]
0x18002cc11  call    GetCardActivityCount
0x18002cc16  mov     edi, eax
0x18002cc18  test    eax, eax
0x18002cc1a  jnz     short loc_18002CC30
0x18002cc1c  mov     ecx, [rsp+68h+arg_0]
0x18002cc20  cmp     [rbx+2C0h], ecx
0x18002cc26  mov     [rbx+2C0h], ecx
0x18002cc2c  setnz   sil
0x18002cc30  mov     rcx, [rbx+8]
0x18002cc34  cmp     dword ptr [rcx], 6
0x18002cc37  jb      short loc_18002CC84
0x18002cc39  cmp     dword ptr [rbx+2B8h], 2
0x18002cc40  jnz     short loc_18002CC84
0x18002cc42  test    ebp, ebp
0x18002cc44  jnz     short loc_18002CC4E
0x18002cc46  test    edi, edi
0x18002cc48  jnz     short loc_18002CC4E
0x18002cc4a  test    esi, esi
0x18002cc4c  jz      short loc_18002CC88
0x18002cc4e  mov     rcx, [rbx+2A0h]
0x18002cc55  call    ScCacheDeleteCache
0x18002cc5a  mov     rcx, [rbx+2A8h]
0x18002cc61  mov     qword ptr [rbx+2A0h], 0
0x18002cc6c  call    ScCacheDeleteCache
0x18002cc71  mov     rcx, rbx
0x18002cc74  mov     qword ptr [rbx+2A8h], 0
0x18002cc7f  call    InitializeCacheHandles
0x18002cc84  test    ebp, ebp
0x18002cc86  jnz     short loc_18002CC99
0x18002cc88  lea     rcx, [rbx+20h]; unsigned __int16 *
0x18002cc8c  mov     r8, r15; unsigned __int16 *
0x18002cc8f  mov     edx, 208h; unsigned __int64
0x18002cc94  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18002cc99  lea     rbx, WPP_GLOBAL_Control
0x18002cca0  mov     edx, 1
0x18002cca5  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002ccaa  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ccb1  cmp     rcx, rbx
0x18002ccb4  jz      short loc_18002CCE2
0x18002ccb6  test    byte ptr [rcx+1Ch], 2
0x18002ccba  jz      short loc_18002CCE2
0x18002ccbc  cmp     byte ptr [rcx+19h], 5
0x18002ccc0  jb      short loc_18002CCE2
0x18002ccc2  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002ccc9  lea     r8, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids
0x18002ccd0  mov     rcx, [rcx+10h]
0x18002ccd4  mov     edx, 2Ah ; '*'
0x18002ccd9  mov     dword ptr [rsp+68h+var_48], edi
0x18002ccdd  call    WPP_SF_sd
0x18002cce2  mov     eax, edi
0x18002cce4  add     rsp, 38h
0x18002cce8  pop     r15
0x18002ccea  pop     r14
0x18002ccec  pop     rdi
0x18002cced  pop     rsi
0x18002ccee  pop     rbp
0x18002ccef  pop     rbx
0x18002ccf0  retn
```
