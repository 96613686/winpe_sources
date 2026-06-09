# ReadCardSerialNumber(_CARD_STATE *,uchar * *,ulong *)

- ea: `0x180034854`
- end: `0x180034a99`
- name: `?ReadCardSerialNumber@@YAKPEAU_CARD_STATE@@PEAPEAEPEAK@Z`
- size: `581`
- prototype: `unsigned int __fastcall(struct _CARD_STATE *, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180032cf4`
- `0x18003385c`

## callees

- `0x180009e76`
- `0x18000a408`
- `0x18000d9d0`
- `0x180011fd8`
- `0x180013734`
- `0x18002b140`
- `0x18002de34`
- `0x180034854`
- `0x180036b04`

## pseudocode

```c
__int64 __fastcall ReadCardSerialNumber(struct _CARD_STATE *a1, unsigned __int8 **a2, unsigned int *a3)
{
  _DWORD *v6; // rcx
  __int64 v7; // rcx
  unsigned int CardProperty; // ebx
  _QWORD *v9; // rcx
  int v10; // edx
  __int64 v11; // rcx
  unsigned __int8 *v12; // rax
  __int64 v13; // rcx
  unsigned __int8 *v14; // rdi
  unsigned int v15; // eax
  __int64 v16; // rcx
  size_t size[2]; // [rsp+30h] [rbp-38h] BYREF

  *(_OWORD *)size = 0;
  WppTraceIndent((__int64)a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids, WPP_pszIndent);
  }
  if ( !a1 || !a2 || !a3 || !*((_QWORD *)a1 + 1) )
  {
    CardProperty = 87;
    goto LABEL_28;
  }
  *a2 = 0;
  *a3 = 0;
  v6 = (_DWORD *)*((_QWORD *)a1 + 1);
  if ( *v6 >= 6u )
  {
    CardProperty = GetCardProperty((__int64)v6, L"Card Identifier", &size[1], (__int64)size, 0);
    if ( CardProperty )
    {
      WppTraceIndent(v7, 2u);
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v10 = 31;
LABEL_15:
        WPP_SF_sd(
          v9[2],
          v10,
          (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
          (_DWORD)WPP_pszIndent,
          CardProperty);
        goto LABEL_28;
      }
      goto LABEL_28;
    }
LABEL_21:
    v12 = (unsigned __int8 *)MIDL_user_allocate(LODWORD(size[0]));
    v14 = v12;
    if ( v12 )
    {
      memcpy_0(v12, (const void *)size[1], LODWORD(size[0]));
      v15 = size[0];
      *a2 = v14;
      *a3 = v15;
    }
    else
    {
      WppTraceIndent(v13, 2u);
      CardProperty = 8;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          33,
          &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
          WPP_pszIndent);
      }
    }
    goto LABEL_28;
  }
  CardProperty = CspReadFile((__int64)a1, 0, "cardid", 0x10000u, &size[1], (__int64)size);
  if ( !CardProperty )
    goto LABEL_21;
  WppTraceIndent(v11, 2u);
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v10 = 32;
    goto LABEL_15;
  }
LABEL_28:
  v16 = size[1];
  if ( size[1] )
    CspFreeH(size[1]);
  WppTraceIndent(v16, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      34,
      (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
      (_DWORD)WPP_pszIndent,
      CardProperty);
  }
  return CardProperty;
}

```

## disassembly

```asm
0x180034854  push    rbx
0x180034856  push    rsi
0x180034857  push    rdi
0x180034858  push    r13
0x18003485a  push    r14
0x18003485c  sub     rsp, 40h
0x180034860  mov     r14, rdx
0x180034863  xorps   xmm0, xmm0
0x180034866  xor     edx, edx
0x180034868  mov     rsi, r8
0x18003486b  movups  xmmword ptr [rsp+68h+size], xmm0
0x180034870  mov     rbx, rcx
0x180034873  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180034878  mov     rcx, cs:WPP_GLOBAL_Control
0x18003487f  lea     r13, WPP_GLOBAL_Control
0x180034886  cmp     rcx, r13
0x180034889  jz      short loc_1800348B3
0x18003488b  test    byte ptr [rcx+1Ch], 2
0x18003488f  jz      short loc_1800348B3
0x180034891  cmp     byte ptr [rcx+19h], 5
0x180034895  jb      short loc_1800348B3
0x180034897  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18003489e  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x1800348a5  mov     rcx, [rcx+10h]
0x1800348a9  mov     edx, 1Eh
0x1800348ae  call    WPP_SF_s
0x1800348b3  test    rbx, rbx
0x1800348b6  jz      loc_180034A35
0x1800348bc  test    r14, r14
0x1800348bf  jz      loc_180034A35
0x1800348c5  test    rsi, rsi
0x1800348c8  jz      loc_180034A35
0x1800348ce  cmp     qword ptr [rbx+8], 0
0x1800348d3  jz      loc_180034A35
0x1800348d9  mov     qword ptr [r14], 0
0x1800348e0  mov     dword ptr [rsi], 0
0x1800348e6  mov     rcx, [rbx+8]
0x1800348ea  cmp     dword ptr [rcx], 6
0x1800348ed  jb      short loc_18003496A
0x1800348ef  lea     r9, [rsp+68h+size]
0x1800348f4  mov     dword ptr [rsp+68h+var_48], 0
0x1800348fc  lea     r8, [rsp+68h+size+8]
0x180034901  lea     rdx, aCardIdentifier; "Card Identifier"
0x180034908  call    GetCardProperty
0x18003490d  mov     ebx, eax
0x18003490f  test    eax, eax
0x180034911  jz      loc_1800349C8
0x180034917  mov     edx, 2
0x18003491c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180034921  mov     rcx, cs:WPP_GLOBAL_Control
0x180034928  cmp     rcx, r13
0x18003492b  jz      loc_180034A3A
0x180034931  test    byte ptr [rcx+1Ch], 1
0x180034935  jz      loc_180034A3A
0x18003493b  cmp     byte ptr [rcx+19h], 2
0x18003493f  jb      loc_180034A3A
0x180034945  mov     edx, 1Fh
0x18003494a  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180034951  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180034958  mov     rcx, [rcx+10h]
0x18003495c  mov     dword ptr [rsp+68h+var_48], ebx
0x180034960  call    WPP_SF_sd
0x180034965  jmp     loc_180034A3A
0x18003496a  lea     rax, [rsp+68h+size]
0x18003496f  mov     r9d, 10000h
0x180034975  mov     [rsp+68h+var_40], rax
0x18003497a  lea     r8, aCardid; "cardid"
0x180034981  lea     rax, [rsp+68h+size+8]
0x180034986  xor     edx, edx
0x180034988  mov     rcx, rbx
0x18003498b  mov     [rsp+68h+var_48], rax
0x180034990  call    CspReadFile
0x180034995  mov     ebx, eax
0x180034997  test    eax, eax
0x180034999  jz      short loc_1800349C8
0x18003499b  mov     edx, 2
0x1800349a0  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800349a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800349ac  cmp     rcx, r13
0x1800349af  jz      loc_180034A3A
0x1800349b5  test    byte ptr [rcx+1Ch], 1
0x1800349b9  jz      short loc_180034A3A
0x1800349bb  cmp     byte ptr [rcx+19h], 2
0x1800349bf  jb      short loc_180034A3A
0x1800349c1  mov     edx, 20h ; ' '
0x1800349c6  jmp     short loc_18003494A
0x1800349c8  mov     ecx, dword ptr [rsp+68h+size]; size
0x1800349cc  call    MIDL_user_allocate
0x1800349d1  mov     rdi, rax
0x1800349d4  test    rax, rax
0x1800349d7  jnz     short loc_180034A18
0x1800349d9  lea     edx, [rax+2]
0x1800349dc  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800349e1  lea     ebx, [rdi+8]
0x1800349e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800349eb  cmp     rcx, r13
0x1800349ee  jz      short loc_180034A3A
0x1800349f0  test    byte ptr [rcx+1Ch], 1
0x1800349f4  jz      short loc_180034A3A
0x1800349f6  cmp     byte ptr [rcx+19h], 2
0x1800349fa  jb      short loc_180034A3A
0x1800349fc  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180034a03  lea     edx, [rdi+21h]
0x180034a06  mov     rcx, [rcx+10h]
0x180034a0a  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180034a11  call    WPP_SF_s
0x180034a16  jmp     short loc_180034A3A
0x180034a18  mov     r8d, dword ptr [rsp+68h+size]; Size
0x180034a1d  mov     rcx, rdi; void *
0x180034a20  mov     rdx, [rsp+68h+size+8]; Src
0x180034a25  call    memcpy_0
0x180034a2a  mov     eax, dword ptr [rsp+68h+size]
0x180034a2e  mov     [r14], rdi
0x180034a31  mov     [rsi], eax
0x180034a33  jmp     short loc_180034A3A
0x180034a35  mov     ebx, 57h ; 'W'
0x180034a3a  mov     rcx, [rsp+68h+size+8]
0x180034a3f  test    rcx, rcx
0x180034a42  jz      short loc_180034A49
0x180034a44  call    CspFreeH
0x180034a49  mov     edx, 1
0x180034a4e  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180034a53  mov     rcx, cs:WPP_GLOBAL_Control
0x180034a5a  cmp     rcx, r13
0x180034a5d  jz      short loc_180034A8B
0x180034a5f  test    byte ptr [rcx+1Ch], 2
0x180034a63  jz      short loc_180034A8B
0x180034a65  cmp     byte ptr [rcx+19h], 5
0x180034a69  jb      short loc_180034A8B
0x180034a6b  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180034a72  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180034a79  mov     rcx, [rcx+10h]
0x180034a7d  mov     edx, 22h ; '"'
0x180034a82  mov     dword ptr [rsp+68h+var_48], ebx
0x180034a86  call    WPP_SF_sd
0x180034a8b  mov     eax, ebx
0x180034a8d  add     rsp, 40h
0x180034a91  pop     r14
0x180034a93  pop     r13
0x180034a95  pop     rdi
0x180034a96  pop     rsi
0x180034a97  pop     rbx
0x180034a98  retn
```
