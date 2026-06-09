# CDlpActionWimLayout::WimMatchImageCriteria(_UNATTEND_CONTEXT *,ushort const *,ushort const *,ulong,ushort const *)

- ea: `0x180030740`
- end: `0x18003088b`
- name: `?WimMatchImageCriteria@CDlpActionWimLayout@@AEAAJPEAU_UNATTEND_CONTEXT@@PEBG1K1@Z`
- size: `331`
- prototype: `__int64 __fastcall(CDlpActionWimLayout *__hidden this, struct _UNATTEND_CONTEXT *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, PCNZWCH lpString1)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002eae4`

## callees

- `0x18000aba4`
- `0x180012f5c`
- `0x18001fd60`
- `0x180030740`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180030822`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180030822`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030865`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030865`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030873`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030873`
- `UNATTEND!UnattendCtxGetString` at `0x18003077e`
- `UNATTEND!UnattendCtxGetString` at `0x18003077e`

## string_xrefs

- `0x1800307f2`: `WimMatchImageCriteria: Comparing image [%d] value [%s] against [%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDlpActionWimLayout::WimMatchImageCriteria(
        CDlpActionWimLayout *this,
        struct _UNATTEND_CONTEXT *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        PCNZWCH lpString1)
{
  unsigned int v7; // esi
  int String; // eax
  unsigned int v9; // ebx
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rcx
  const WCHAR *v14; // rdi
  __int64 v15; // rcx
  WCHAR *v16; // rdi
  HANDLE ProcessHeap; // rax
  int lpString2; // [rsp+20h] [rbp-18h]
  PCNZWCH v20; // [rsp+58h] [rbp+20h] BYREF

  v20 = 0;
  v7 = a5;
  lpString2 = a5 - 1;
  String = UnattendCtxGetString(a2, a3, 0, &v20);
  v9 = String;
  if ( String < 0 )
  {
    v10 = *((_QWORD *)this + 11);
    if ( v10 )
    {
      v11 = CDlpLogT<CEmptyType>::DlpLogFormat(
              v10,
              4u,
              (__int64)L"%s(%d): Result = 0x%X",
              L"CDlpActionWimLayout::WimMatchImageCriteria",
              2440,
              String);
      v12 = (unsigned int)v11;
      if ( v11 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v11);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v12);
    }
    goto LABEL_15;
  }
  if ( String )
  {
    if ( String != 1 )
      goto LABEL_15;
    v15 = *((_QWORD *)this + 11);
    if ( v15 )
      CDlpLogT<CEmptyType>::DlpLogFormat(
        v15,
        1u,
        (__int64)L"WimMatchImageCriteria: Image [%d] value not found",
        v7,
        lpString2);
    goto LABEL_14;
  }
  v13 = *((_QWORD *)this + 11);
  v14 = lpString1;
  if ( v13 )
    CDlpLogT<CEmptyType>::DlpLogFormat(
      v13,
      1u,
      (__int64)L"WimMatchImageCriteria: Comparing image [%d] value [%s] against [%s]",
      v7,
      v20,
      lpString1);
  if ( CompareStringW(0x409u, 1u, v14, -1, v20, -1) != 2 )
LABEL_14:
    v9 = -2147023728;
LABEL_15:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v9);
  v16 = (WCHAR *)v20;
  if ( v20 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v16);
  }
  return v9;
}

```

## disassembly

```asm
0x180030740  mov     rax, rsp
0x180030743  mov     [rax+8], rbx
0x180030747  mov     [rax+10h], rsi
0x18003074b  mov     [rax+20h], r9
0x18003074f  push    rdi
0x180030750  sub     rsp, 30h
0x180030754  mov     r10, r8
0x180030757  mov     r11, rdx
0x18003075a  mov     rdi, rcx
0x18003075d  mov     qword ptr [rax+20h], 0
0x180030765  mov     esi, [rsp+38h+arg_20]
0x180030769  lea     eax, [rsi-1]
0x18003076c  mov     dword ptr [rsp+38h+lpString2], eax
0x180030770  lea     r9, [rsp+38h+arg_18]
0x180030775  xor     r8d, r8d
0x180030778  mov     rdx, r10
0x18003077b  mov     rcx, r11
0x18003077e  call    cs:__imp_UnattendCtxGetString
0x180030784  mov     ebx, eax
0x180030786  test    eax, eax
0x180030788  jns     short loc_1800307D0
0x18003078a  mov     rcx, [rdi+58h]
0x18003078e  test    rcx, rcx
0x180030791  jz      loc_180030853
0x180030797  mov     [rsp+38h+cchCount2], eax
0x18003079b  mov     dword ptr [rsp+38h+lpString2], 988h
0x1800307a3  lea     r9, aCdlpactionwiml_22; "CDlpActionWimLayout::WimMatchImageCrite"...
0x1800307aa  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x1800307b1  mov     edx, 4
0x1800307b6  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x1800307bb  mov     ecx, eax
0x1800307bd  test    eax, eax
0x1800307bf  jns     short loc_1800307C6
0x1800307c1  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800307c6  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800307cb  jmp     loc_180030853
0x1800307d0  jnz     short loc_18003082F
0x1800307d2  mov     rcx, [rdi+58h]
0x1800307d6  mov     rdi, [rsp+38h+lpString1]
0x1800307db  test    rcx, rcx
0x1800307de  jz      short loc_180030803
0x1800307e0  mov     rax, [rsp+38h+arg_18]
0x1800307e5  mov     qword ptr [rsp+38h+cchCount2], rdi
0x1800307ea  mov     [rsp+38h+lpString2], rax
0x1800307ef  mov     r9d, esi
0x1800307f2  lea     r8, aWimmatchimagec; "WimMatchImageCriteria: Comparing image "...
0x1800307f9  mov     edx, 1
0x1800307fe  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180030803  mov     rax, [rsp+38h+arg_18]
0x180030808  or      r9d, 0FFFFFFFFh; cchCount1
0x18003080c  mov     [rsp+38h+cchCount2], r9d; cchCount2
0x180030811  mov     [rsp+38h+lpString2], rax; lpString2
0x180030816  mov     r8, rdi; lpString1
0x180030819  lea     edx, [r9+2]; dwCmpFlags
0x18003081d  mov     ecx, 409h; Locale
0x180030822  call    cs:__imp_CompareStringW
0x180030828  cmp     eax, 2
0x18003082b  jz      short loc_180030853
0x18003082d  jmp     short loc_18003084E
0x18003082f  cmp     eax, 1
0x180030832  jnz     short loc_180030853
0x180030834  mov     rcx, [rdi+58h]
0x180030838  test    rcx, rcx
0x18003083b  jz      short loc_18003084E
0x18003083d  mov     r9d, esi
0x180030840  lea     r8, aWimmatchimagec_0; "WimMatchImageCriteria: Image [%d] value"...
0x180030847  mov     edx, eax
0x180030849  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18003084e  mov     ebx, 80070490h
0x180030853  mov     ecx, ebx
0x180030855  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003085a  nop
0x18003085b  mov     rdi, [rsp+38h+arg_18]
0x180030860  test    rdi, rdi
0x180030863  jz      short loc_180030879
0x180030865  call    cs:__imp_GetProcessHeap
0x18003086b  mov     rcx, rax; hHeap
0x18003086e  mov     r8, rdi; lpMem
0x180030871  xor     edx, edx; dwFlags
0x180030873  call    cs:__imp_HeapFree
0x180030879  mov     eax, ebx
0x18003087b  mov     rbx, [rsp+38h+arg_0]
0x180030880  mov     rsi, [rsp+38h+arg_8]
0x180030885  add     rsp, 30h
0x180030889  pop     rdi
0x18003088a  retn
```
