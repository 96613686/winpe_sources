# IsPathTracked(_UNICODE_STRING const *,_UNICODE_STRING const *,_TRACKING_MODE *)

- ea: `0x140006600`
- end: `0x14000691d`
- name: `?IsPathTracked@@YAEPEBU_UNICODE_STRING@@0PEAW4_TRACKING_MODE@@@Z`
- size: `797`
- prototype: `unsigned __int8 __fastcall(PCUNICODE_STRING FullName, PCUNICODE_STRING String2, enum _TRACKING_MODE *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001e808`

## callees

- `0x140006600`

## import_xrefs

- `ntoskrnl!FsRtlDissectName` at `0x1400066f2`
- `ntoskrnl!FsRtlDissectName` at `0x1400067a5`
- `ntoskrnl!FsRtlDissectName` at `0x1400068b2`
- `ntoskrnl!FsRtlDissectName` at `0x1400066f2`
- `ntoskrnl!FsRtlDissectName` at `0x1400067a5`
- `ntoskrnl!FsRtlDissectName` at `0x1400068b2`
- `ntoskrnl!FsRtlIsNameInExpression` at `0x140006713`
- `ntoskrnl!FsRtlIsNameInExpression` at `0x1400067c6`
- `ntoskrnl!FsRtlIsNameInExpression` at `0x1400068d9`
- `ntoskrnl!FsRtlIsNameInExpression` at `0x140006713`
- `ntoskrnl!FsRtlIsNameInExpression` at `0x1400067c6`
- `ntoskrnl!FsRtlIsNameInExpression` at `0x1400068d9`
- `ntoskrnl!RtlFindUnicodePrefix` at `0x140006643`
- `ntoskrnl!RtlFindUnicodePrefix` at `0x14000680b`
- `ntoskrnl!RtlFindUnicodePrefix` at `0x140006643`
- `ntoskrnl!RtlFindUnicodePrefix` at `0x14000680b`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000686b`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000686b`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000662a`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000662a`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140006753`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140006851`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400068f8`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140006753`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140006851`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400068f8`

## pseudocode

```c
char __fastcall IsPathTracked(PCUNICODE_STRING FullName, PCUNICODE_STRING String2, enum _TRACKING_MODE *a3)
{
  char v4; // di
  PUNICODE_PREFIX_TABLE_ENTRY UnicodePrefix; // rax
  PUNICODE_PREFIX_TABLE_ENTRY v8; // rbx
  unsigned __int64 NodeTypeCode; // rax
  unsigned __int16 Length; // cx
  wchar_t *Buffer; // r8
  unsigned __int64 v12; // rax
  wchar_t v13; // dx
  int CaseMatch; // eax
  struct _RTL_SPLAY_LINKS *Parent; // rbx
  UNICODE_STRING v16; // xmm1
  unsigned int v17; // r14d
  BOOLEAN IsNameInExpression; // al
  UNICODE_STRING v20; // xmm1
  unsigned int v21; // r14d
  PUNICODE_PREFIX_TABLE_ENTRY v23; // rax
  wchar_t v24; // r8
  UNICODE_STRING v26; // xmm1
  UNICODE_STRING String2a; // [rsp+20h] [rbp-48h] BYREF
  struct _UNICODE_STRING RemainingName; // [rsp+30h] [rbp-38h] BYREF
  struct _UNICODE_STRING FirstName; // [rsp+40h] [rbp-28h] BYREF
  UNICODE_STRING Path; // [rsp+50h] [rbp-18h] BYREF

  v4 = 0;
  ExAcquireFastMutex(&stru_140019468);
  UnicodePrefix = RtlFindUnicodePrefix(&g_TrackingInfo, FullName, 0);
  v8 = UnicodePrefix;
  String2a = 0;
  if ( !UnicodePrefix )
    goto LABEL_32;
  NodeTypeCode = (unsigned __int16)UnicodePrefix[1].NodeTypeCode;
  Length = FullName->Length;
  if ( FullName->Length > (unsigned __int16)NodeTypeCode )
  {
    Buffer = FullName->Buffer;
    v12 = NodeTypeCode >> 1;
    v13 = Buffer[v12];
    if ( v13 == 92 )
    {
      String2a.Buffer = &Buffer[v12 + 1];
      String2a.Length = Length - v8[1].NodeTypeCode - 2;
      String2a.MaximumLength = String2a.Length;
    }
    else if ( v13 != 58 )
    {
      goto LABEL_32;
    }
  }
  CaseMatch = (int)v8[1].CaseMatch;
  v4 = 1;
  Parent = v8[1].Links.Parent;
  *(_DWORD *)a3 = CaseMatch;
  while ( Parent )
  {
    if ( LODWORD(Parent[1].Parent) )
    {
      v16 = *String2;
      v17 = 0;
      RemainingName = *String2;
      while ( v17 < LODWORD(Parent[1].Parent) )
      {
        Path = v16;
        FirstName = 0;
        FsRtlDissectName(&Path, &FirstName, &RemainingName);
        if ( !FsRtlIsNameInExpression((PUNICODE_STRING)Parent[1].LeftChild + v17++, &FirstName, 1u, 0) )
          goto LABEL_41;
        v16 = RemainingName;
      }
      if ( RemainingName.Length )
        goto LABEL_41;
      IsNameInExpression = 1;
    }
    else
    {
      IsNameInExpression = 1;
      if ( LOWORD(Parent->LeftChild) )
      {
        IsNameInExpression = RtlEqualUnicodeString((PCUNICODE_STRING)&Parent->LeftChild, String2, 1u);
        if ( !IsNameInExpression )
          goto LABEL_41;
      }
    }
    if ( !String2a.Length )
      goto LABEL_40;
    if ( !LODWORD(Parent[2].LeftChild) )
    {
      if ( LOBYTE(Parent[3].Parent) )
      {
        v26 = String2a;
        FirstName = 0;
        for ( RemainingName = String2a; ; v26 = RemainingName )
        {
          Path = v26;
          FsRtlDissectName(&Path, &FirstName, &RemainingName);
          if ( !RemainingName.Length )
            break;
        }
        IsNameInExpression = FsRtlIsNameInExpression((PUNICODE_STRING)&Parent[1].RightChild, &FirstName, 1u, 0);
      }
      else if ( LOWORD(Parent[1].RightChild) )
      {
        IsNameInExpression = RtlEqualUnicodeString((PCUNICODE_STRING)&Parent[1].RightChild, &String2a, 1u);
      }
LABEL_40:
      if ( IsNameInExpression )
        goto LABEL_23;
      goto LABEL_41;
    }
    v20 = String2a;
    v21 = 0;
    RemainingName = String2a;
    while ( v21 < LODWORD(Parent[2].LeftChild) )
    {
      Path = v20;
      FirstName = 0;
      FsRtlDissectName(&Path, &FirstName, &RemainingName);
      if ( !FsRtlIsNameInExpression((PUNICODE_STRING)Parent[2].RightChild + v21++, &FirstName, 1u, 0) )
        goto LABEL_41;
      v20 = RemainingName;
    }
    if ( !RemainingName.Length )
    {
LABEL_23:
      *(_DWORD *)a3 = HIDWORD(Parent[3].Parent);
      break;
    }
LABEL_41:
    Parent = Parent->Parent;
  }
  if ( (unsigned int)(*(_DWORD *)a3 - 3) <= 1 )
  {
    v23 = RtlFindUnicodePrefix(&PrefixTable, FullName, 0);
    if ( v23 )
    {
      if ( FullName->Length <= (unsigned int)v23[1].NodeTypeCode
        || (v24 = FullName->Buffer[(unsigned __int64)(unsigned __int16)v23[1].NodeTypeCode >> 1], v24 == 92)
        || v24 == 58 )
      {
        if ( !LOWORD(v23[1].CaseMatch) || RtlEqualUnicodeString((PCUNICODE_STRING)&v23[1].CaseMatch, String2, 1u) )
          *(_DWORD *)a3 = 1;
      }
    }
  }
LABEL_32:
  ExReleaseFastMutex(&stru_140019468);
  return v4;
}

```

## disassembly

```asm
0x140006600  push    rbp
0x140006602  push    rbx
0x140006603  push    rsi
0x140006604  push    rdi
0x140006605  push    r12
0x140006607  push    r13
0x140006609  push    r14
0x14000660b  push    r15
0x14000660d  mov     rbp, rsp
0x140006610  sub     rsp, 68h
0x140006614  mov     rsi, rcx
0x140006617  xor     r13d, r13d
0x14000661a  lea     rcx, stru_140019468; FastMutex
0x140006621  mov     dil, r13b
0x140006624  mov     r15, r8
0x140006627  mov     r12, rdx
0x14000662a  call    cs:__imp_ExAcquireFastMutex
0x140006631  nop     dword ptr [rax+rax+00h]
0x140006636  xor     r8d, r8d; CaseInsensitiveIndex
0x140006639  lea     rcx, ?g_TrackingInfo@@3U_TRACKED_PATHS_TABLE@@A; PrefixTable
0x140006640  mov     rdx, rsi; FullName
0x140006643  call    cs:__imp_RtlFindUnicodePrefix
0x14000664a  nop     dword ptr [rax+rax+00h]
0x14000664f  xorps   xmm0, xmm0
0x140006652  mov     rbx, rax
0x140006655  movups  xmmword ptr [rbp+String2.Length], xmm0
0x140006659  test    rax, rax
0x14000665c  jz      loc_140006864
0x140006662  movzx   eax, word ptr [rax+38h]
0x140006666  movzx   ecx, word ptr [rsi]
0x140006669  cmp     cx, ax
0x14000666c  jbe     short loc_14000668A
0x14000666e  mov     r8, [rsi+8]
0x140006672  shr     rax, 1
0x140006675  movzx   edx, word ptr [r8+rax*2]
0x14000667a  cmp     dx, 5Ch ; '\'
0x14000667e  jz      short loc_1400066A5
0x140006680  cmp     dx, 3Ah ; ':'
0x140006684  jnz     loc_140006864
0x14000668a  mov     eax, dword ptr [rbp+String2.Length]
0x14000668d  mov     [rbp+String2.Length], ax
0x140006691  mov     eax, [rbx+48h]
0x140006694  mov     edi, 1
0x140006699  mov     rbx, [rbx+50h]
0x14000669d  mov     [r15], eax
0x1400066a0  jmp     loc_14000690F
0x1400066a5  inc     rax
0x1400066a8  lea     rax, [r8+rax*2]
0x1400066ac  mov     [rbp+String2.Buffer], rax
0x1400066b0  sub     cx, [rbx+38h]
0x1400066b4  sub     cx, 2
0x1400066b8  mov     [rbp+String2.Length], cx
0x1400066bc  mov     [rbp+String2.MaximumLength], cx
0x1400066c0  jmp     short loc_140006691
0x1400066c2  cmp     [rbx+18h], r13d
0x1400066c6  jbe     short loc_140006740
0x1400066c8  movups  xmm1, xmmword ptr [r12]
0x1400066cd  mov     r14d, r13d
0x1400066d0  movaps  xmmword ptr [rbp+RemainingName.Length], xmm1
0x1400066d4  cmp     r14d, [rbx+18h]
0x1400066d8  jnb     short loc_140006730
0x1400066da  xorps   xmm0, xmm0
0x1400066dd  movdqa  xmmword ptr [rbp+Path.Length], xmm1
0x1400066e2  lea     r8, [rbp+RemainingName]; RemainingName
0x1400066e6  lea     rdx, [rbp+FirstName]; FirstName
0x1400066ea  lea     rcx, [rbp+Path]; Path
0x1400066ee  movups  xmmword ptr [rbp+FirstName.Length], xmm0
0x1400066f2  call    cs:__imp_FsRtlDissectName
0x1400066f9  nop     dword ptr [rax+rax+00h]
0x1400066fe  mov     ecx, r14d
0x140006701  lea     rdx, [rbp+FirstName]; Name
0x140006705  shl     rcx, 4
0x140006709  xor     r9d, r9d; UpcaseTable
0x14000670c  add     rcx, [rbx+20h]; Expression
0x140006710  mov     r8b, dil; IgnoreCase
0x140006713  call    cs:__imp_FsRtlIsNameInExpression
0x14000671a  nop     dword ptr [rax+rax+00h]
0x14000671f  add     r14d, edi
0x140006722  test    al, al
0x140006724  jz      loc_14000690C
0x14000672a  movaps  xmm1, xmmword ptr [rbp+RemainingName.Length]
0x14000672e  jmp     short loc_1400066D4
0x140006730  cmp     [rbp+RemainingName.Length], r13w
0x140006735  jnz     loc_14000690C
0x14000673b  mov     al, dil
0x14000673e  jmp     short loc_140006767
0x140006740  lea     rcx, [rbx+8]; String1
0x140006744  mov     al, dil
0x140006747  cmp     [rcx], r13w
0x14000674b  jbe     short loc_140006767
0x14000674d  mov     r8b, dil; CaseInSensitive
0x140006750  mov     rdx, r12; String2
0x140006753  call    cs:__imp_RtlEqualUnicodeString
0x14000675a  nop     dword ptr [rax+rax+00h]
0x14000675f  test    al, al
0x140006761  jz      loc_14000690C
0x140006767  cmp     [rbp+String2.Length], r13w
0x14000676c  jbe     loc_140006904
0x140006772  cmp     [rbx+38h], r13d
0x140006776  jbe     loc_14000688C
0x14000677c  movaps  xmm1, xmmword ptr [rbp+String2.Length]
0x140006780  mov     r14d, r13d
0x140006783  movaps  xmmword ptr [rbp+RemainingName.Length], xmm1
0x140006787  cmp     r14d, [rbx+38h]
0x14000678b  jnb     short loc_1400067E3
0x14000678d  xorps   xmm0, xmm0
0x140006790  movdqa  xmmword ptr [rbp+Path.Length], xmm1
0x140006795  lea     r8, [rbp+RemainingName]; RemainingName
0x140006799  lea     rdx, [rbp+FirstName]; FirstName
0x14000679d  lea     rcx, [rbp+Path]; Path
0x1400067a1  movups  xmmword ptr [rbp+FirstName.Length], xmm0
0x1400067a5  call    cs:__imp_FsRtlDissectName
0x1400067ac  nop     dword ptr [rax+rax+00h]
0x1400067b1  mov     ecx, r14d
0x1400067b4  lea     rdx, [rbp+FirstName]; Name
0x1400067b8  shl     rcx, 4
0x1400067bc  xor     r9d, r9d; UpcaseTable
0x1400067bf  add     rcx, [rbx+40h]; Expression
0x1400067c3  mov     r8b, dil; IgnoreCase
0x1400067c6  call    cs:__imp_FsRtlIsNameInExpression
0x1400067cd  nop     dword ptr [rax+rax+00h]
0x1400067d2  add     r14d, edi
0x1400067d5  test    al, al
0x1400067d7  jz      loc_14000690C
0x1400067dd  movaps  xmm1, xmmword ptr [rbp+RemainingName.Length]
0x1400067e1  jmp     short loc_140006787
0x1400067e3  cmp     [rbp+RemainingName.Length], r13w
0x1400067e8  jnz     loc_14000690C
0x1400067ee  mov     eax, [rbx+4Ch]
0x1400067f1  mov     [r15], eax
0x1400067f4  mov     eax, [r15]
0x1400067f7  sub     eax, 3
0x1400067fa  cmp     eax, edi
0x1400067fc  ja      short loc_140006864
0x1400067fe  xor     r8d, r8d; CaseInsensitiveIndex
0x140006801  lea     rcx, PrefixTable; PrefixTable
0x140006808  mov     rdx, rsi; FullName
0x14000680b  call    cs:__imp_RtlFindUnicodePrefix
0x140006812  nop     dword ptr [rax+rax+00h]
0x140006817  test    rax, rax
0x14000681a  jz      short loc_140006864
0x14000681c  movzx   ecx, word ptr [rax+38h]
0x140006820  cmp     [rsi], cx
0x140006823  jbe     short loc_140006841
0x140006825  mov     edx, ecx
0x140006827  mov     rcx, [rsi+8]
0x14000682b  shr     rdx, 1
0x14000682e  movzx   r8d, word ptr [rcx+rdx*2]
0x140006833  cmp     r8w, 5Ch ; '\'
0x140006838  jz      short loc_140006841
0x14000683a  cmp     r8w, 3Ah ; ':'
0x14000683f  jnz     short loc_140006864
0x140006841  lea     rcx, [rax+48h]; String1
0x140006845  cmp     [rcx], r13w
0x140006849  jz      short loc_140006861
0x14000684b  mov     r8b, dil; CaseInSensitive
0x14000684e  mov     rdx, r12; String2
0x140006851  call    cs:__imp_RtlEqualUnicodeString
0x140006858  nop     dword ptr [rax+rax+00h]
0x14000685d  test    al, al
0x14000685f  jz      short loc_140006864
0x140006861  mov     [r15], edi
0x140006864  lea     rcx, stru_140019468; FastMutex
0x14000686b  call    cs:__imp_ExReleaseFastMutex
0x140006872  nop     dword ptr [rax+rax+00h]
0x140006877  mov     al, dil
0x14000687a  add     rsp, 68h
0x14000687e  pop     r15
0x140006880  pop     r14
0x140006882  pop     r13
0x140006884  pop     r12
0x140006886  pop     rdi
0x140006887  pop     rsi
0x140006888  pop     rbx
0x140006889  pop     rbp
0x14000688a  retn
0x14000688c  cmp     [rbx+48h], r13b
0x140006890  jz      short loc_1400068E7
0x140006892  movaps  xmm1, xmmword ptr [rbp+String2.Length]
0x140006896  xorps   xmm0, xmm0
0x140006899  movups  xmmword ptr [rbp+FirstName.Length], xmm0
0x14000689d  movaps  xmmword ptr [rbp+RemainingName.Length], xmm1
0x1400068a1  lea     r8, [rbp+RemainingName]; RemainingName
0x1400068a5  movdqa  xmmword ptr [rbp+Path.Length], xmm1
0x1400068aa  lea     rdx, [rbp+FirstName]; FirstName
0x1400068ae  lea     rcx, [rbp+Path]; Path
0x1400068b2  call    cs:__imp_FsRtlDissectName
0x1400068b9  nop     dword ptr [rax+rax+00h]
0x1400068be  cmp     [rbp+RemainingName.Length], r13w
0x1400068c3  jbe     short loc_1400068CB
0x1400068c5  movaps  xmm1, xmmword ptr [rbp+RemainingName.Length]
0x1400068c9  jmp     short loc_1400068A1
0x1400068cb  lea     rcx, [rbx+28h]; Expression
0x1400068cf  xor     r9d, r9d; UpcaseTable
0x1400068d2  mov     r8b, dil; IgnoreCase
0x1400068d5  lea     rdx, [rbp+FirstName]; Name
0x1400068d9  call    cs:__imp_FsRtlIsNameInExpression
0x1400068e0  nop     dword ptr [rax+rax+00h]
0x1400068e5  jmp     short loc_140006904
0x1400068e7  lea     rcx, [rbx+28h]; String1
0x1400068eb  cmp     [rcx], r13w
0x1400068ef  jbe     short loc_140006904
0x1400068f1  mov     r8b, dil; CaseInSensitive
0x1400068f4  lea     rdx, [rbp+String2]; String2
0x1400068f8  call    cs:__imp_RtlEqualUnicodeString
0x1400068ff  nop     dword ptr [rax+rax+00h]
0x140006904  test    al, al
0x140006906  jnz     loc_1400067EE
0x14000690c  mov     rbx, [rbx]
0x14000690f  test    rbx, rbx
0x140006912  jnz     loc_1400066C2
0x140006918  jmp     loc_1400067F4
```
