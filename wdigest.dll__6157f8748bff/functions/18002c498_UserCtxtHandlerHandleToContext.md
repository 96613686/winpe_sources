# UserCtxtHandlerHandleToContext

- ea: `0x18002c498`
- end: `0x18002c643`
- name: `UserCtxtHandlerHandleToContext`
- size: `427`
- prototype: ``
- caller_count: `8`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180030d40`
- `0x180030ee0`
- `0x180031080`
- `0x1800316a0`
- `0x180031910`
- `0x180032060`
- `0x1800322b0`
- `0x180032670`

## callees

- `0x180011fec`
- `0x1800185b8`
- `0x1800192a8`
- `0x18002c498`
- `0x18002c8bc`
- `0x18002c920`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18002c604`
- `ntdll!RtlLeaveCriticalSection` at `0x18002c604`
- `ntdll!RtlEnterCriticalSection` at `0x18002c4e6`
- `ntdll!RtlEnterCriticalSection` at `0x18002c4e6`

## pseudocode

```c
__int64 __fastcall UserCtxtHandlerHandleToContext(struct _LIST_ENTRY *a1, char a2, char a3, struct _LIST_ENTRY **a4)
{
  __int64 v8; // r8
  PVOID *v9; // rcx
  struct _LIST_ENTRY *i; // rbx
  struct _LIST_ENTRY *v11; // rdi
  int Blink_high; // eax
  unsigned int v13; // esi

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x11u, &WPP_1f673aa1758432778e545cfd98b4c3cf_Traceguids);
  RtlEnterCriticalSection(&l_UserCtxtCritSect);
  v9 = (PVOID *)WPP_GLOBAL_Control;
  for ( i = l_UserCtxtList.Flink; ; i = i->Flink )
  {
    if ( i == &l_UserCtxtList )
    {
      if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 2) != 0 )
        WPP_SF_q((TRACEHANDLE)v9[2], 0x15u, &WPP_1f673aa1758432778e545cfd98b4c3cf_Traceguids, a1);
      v11 = 0;
      goto LABEL_27;
    }
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 4) != 0 )
    {
      WPP_SF_qq(v9[2], 18, &WPP_1f673aa1758432778e545cfd98b4c3cf_Traceguids, i[1].Blink, a1);
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( i[1].Blink == a1 )
      break;
  }
  v11 = 0;
  if ( a2 )
  {
    Blink_high = HIDWORD(i[2].Blink);
    if ( Blink_high > 0 )
    {
      HIDWORD(i[2].Blink) = Blink_high - 1;
      v9 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_14;
    }
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 )
      WPP_SF_qll(v9[2], 19, v8, i, i[2].Blink, Blink_high);
LABEL_27:
    v13 = -1073741772;
    goto LABEL_28;
  }
LABEL_14:
  v13 = 0;
  if ( a3 )
  {
    ++HIDWORD(i[2].Blink);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 4) != 0 )
    WPP_SF_qll(v9[2], 20, v8, i, i[2].Blink, HIDWORD(i[2].Blink));
  v11 = i;
  ++LODWORD(i[2].Blink);
LABEL_28:
  *a4 = v11;
  RtlLeaveCriticalSection(&l_UserCtxtCritSect);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x16u, &WPP_1f673aa1758432778e545cfd98b4c3cf_Traceguids, v13);
  return v13;
}

```

## disassembly

```asm
0x18002c498  push    rbx
0x18002c49a  push    rbp
0x18002c49b  push    rsi
0x18002c49c  push    rdi
0x18002c49d  push    r14
0x18002c49f  push    r15
0x18002c4a1  sub     rsp, 38h
0x18002c4a5  mov     r14, r9
0x18002c4a8  mov     bpl, r8b
0x18002c4ab  mov     sil, dl
0x18002c4ae  mov     rdi, rcx
0x18002c4b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c4b8  lea     r15, WPP_GLOBAL_Control
0x18002c4bf  cmp     rcx, r15
0x18002c4c2  jz      short loc_18002C4DF
0x18002c4c4  test    byte ptr [rcx+1Ch], 80h
0x18002c4c8  jz      short loc_18002C4DF
0x18002c4ca  mov     rcx, [rcx+10h]
0x18002c4ce  lea     r8, WPP_1f673aa1758432778e545cfd98b4c3cf_Traceguids
0x18002c4d5  mov     edx, 11h
0x18002c4da  call    WPP_SF_
0x18002c4df  lea     rcx, ?l_UserCtxtCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18002c4e6  call    cs:__imp_RtlEnterCriticalSection
0x18002c4ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c4f3  mov     rbx, cs:?l_UserCtxtList@@3U_LIST_ENTRY@@A; _LIST_ENTRY l_UserCtxtList
0x18002c4fa  lea     rax, ?l_UserCtxtList@@3U_LIST_ENTRY@@A; _LIST_ENTRY l_UserCtxtList
0x18002c501  cmp     rbx, rax
0x18002c504  jz      loc_18002C5D0
0x18002c50a  cmp     rcx, r15
0x18002c50d  jz      short loc_18002C53A
0x18002c50f  test    byte ptr [rcx+1Ch], 4
0x18002c513  jz      short loc_18002C53A
0x18002c515  mov     r9, [rbx+18h]
0x18002c519  lea     r8, WPP_1f673aa1758432778e545cfd98b4c3cf_Traceguids
0x18002c520  mov     rcx, [rcx+10h]
0x18002c524  mov     edx, 12h
0x18002c529  mov     [rsp+68h+var_48], rdi
0x18002c52e  call    WPP_SF_qq
0x18002c533  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c53a  cmp     [rbx+18h], rdi
0x18002c53e  jz      short loc_18002C545
0x18002c540  mov     rbx, [rbx]
0x18002c543  jmp     short loc_18002C4FA
0x18002c545  xor     edi, edi
0x18002c547  test    sil, sil
0x18002c54a  jz      short loc_18002C55F
0x18002c54c  mov     eax, [rbx+2Ch]
0x18002c54f  test    eax, eax
0x18002c551  jle     short loc_18002C5A7
0x18002c553  dec     eax
0x18002c555  mov     [rbx+2Ch], eax
0x18002c558  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c55f  mov     esi, edi
0x18002c561  test    bpl, bpl
0x18002c564  jz      short loc_18002C570
0x18002c566  inc     dword ptr [rbx+2Ch]
0x18002c569  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c570  cmp     rcx, r15
0x18002c573  jz      short loc_18002C59A
0x18002c575  test    byte ptr [rcx+1Ch], 4
0x18002c579  jz      short loc_18002C59A
0x18002c57b  mov     eax, [rbx+2Ch]
0x18002c57e  mov     edx, 14h
0x18002c583  mov     rcx, [rcx+10h]
0x18002c587  mov     r9, rbx
0x18002c58a  mov     [rsp+68h+var_40], eax
0x18002c58e  mov     eax, [rbx+28h]
0x18002c591  mov     dword ptr [rsp+68h+var_48], eax
0x18002c595  call    WPP_SF_qll
0x18002c59a  mov     eax, [rbx+28h]
0x18002c59d  mov     rdi, rbx
0x18002c5a0  inc     eax
0x18002c5a2  mov     [rbx+28h], eax
0x18002c5a5  jmp     short loc_18002C5FA
0x18002c5a7  cmp     rcx, r15
0x18002c5aa  jz      short loc_18002C5F5
0x18002c5ac  test    byte ptr [rcx+1Ch], 1
0x18002c5b0  jz      short loc_18002C5F5
0x18002c5b2  mov     rcx, [rcx+10h]
0x18002c5b6  mov     edx, 13h
0x18002c5bb  mov     [rsp+68h+var_40], eax
0x18002c5bf  mov     r9, rbx
0x18002c5c2  mov     eax, [rbx+28h]
0x18002c5c5  mov     dword ptr [rsp+68h+var_48], eax
0x18002c5c9  call    WPP_SF_qll
0x18002c5ce  jmp     short loc_18002C5F5
0x18002c5d0  cmp     rcx, r15
0x18002c5d3  jz      short loc_18002C5F3
0x18002c5d5  test    byte ptr [rcx+1Ch], 2
0x18002c5d9  jz      short loc_18002C5F3
0x18002c5db  mov     rcx, [rcx+10h]
0x18002c5df  lea     r8, WPP_1f673aa1758432778e545cfd98b4c3cf_Traceguids
0x18002c5e6  mov     edx, 15h
0x18002c5eb  mov     r9, rdi
0x18002c5ee  call    WPP_SF_q
0x18002c5f3  xor     edi, edi
0x18002c5f5  mov     esi, 0C0000034h
0x18002c5fa  lea     rcx, ?l_UserCtxtCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18002c601  mov     [r14], rdi
0x18002c604  call    cs:__imp_RtlLeaveCriticalSection
0x18002c60a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c611  cmp     rcx, r15
0x18002c614  jz      short loc_18002C634
0x18002c616  test    byte ptr [rcx+1Ch], 80h
0x18002c61a  jz      short loc_18002C634
0x18002c61c  mov     rcx, [rcx+10h]
0x18002c620  lea     r8, WPP_1f673aa1758432778e545cfd98b4c3cf_Traceguids
0x18002c627  mov     edx, 16h
0x18002c62c  mov     r9d, esi
0x18002c62f  call    WPP_SF_d
0x18002c634  mov     eax, esi
0x18002c636  add     rsp, 38h
0x18002c63a  pop     r15
0x18002c63c  pop     r14
0x18002c63e  pop     rdi
0x18002c63f  pop     rsi
0x18002c640  pop     rbp
0x18002c641  pop     rbx
0x18002c642  retn
```
