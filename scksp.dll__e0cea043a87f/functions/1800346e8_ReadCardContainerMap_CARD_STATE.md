# ReadCardContainerMap(_CARD_STATE *)

- ea: `0x1800346e8`
- end: `0x18003484d`
- name: `?ReadCardContainerMap@@YAKPEAU_CARD_STATE@@@Z`
- size: `357`
- prototype: `__int64 __fastcall(struct _CARD_STATE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180032cf4`

## callees

- `0x18000a408`
- `0x18000d9d0`
- `0x180011fd8`
- `0x180013734`
- `0x18002de34`
- `0x1800346e8`

## pseudocode

```c
__int64 __fastcall ReadCardContainerMap(struct _CARD_STATE *a1)
{
  __int64 v2; // rcx
  unsigned int File; // ebx
  __int64 v4; // rcx
  unsigned __int64 v5; // r8
  __int128 v7; // [rsp+30h] [rbp-18h] BYREF

  v7 = 0;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids, WPP_pszIndent);
  }
  File = CspReadFile((__int64)a1, "mscp", "cmapfile", 0, (_QWORD *)&v7 + 1, (__int64)&v7);
  if ( File )
  {
    WppTraceIndent(v2, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        28,
        (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
        (_DWORD)WPP_pszIndent,
        File);
    }
    v4 = *((_QWORD *)&v7 + 1);
  }
  else
  {
    v4 = 0;
    v5 = (unsigned int)v7;
    *((_QWORD *)a1 + 71) = *((_QWORD *)&v7 + 1);
    *((_QWORD *)&v7 + 1) = 0;
    *((_DWORD *)a1 + 144) = v5 / 0x56;
  }
  if ( v4 )
    CspFreeH(v4);
  WppTraceIndent(v4, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      29,
      (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
      (_DWORD)WPP_pszIndent,
      File);
  }
  return File;
}

```

## disassembly

```asm
0x1800346e8  mov     [rsp+arg_0], rbx
0x1800346ed  mov     [rsp+arg_8], rbp
0x1800346f2  push    rdi
0x1800346f3  sub     rsp, 40h
0x1800346f7  xorps   xmm0, xmm0
0x1800346fa  xor     edx, edx
0x1800346fc  movups  [rsp+48h+var_18], xmm0
0x180034701  mov     rdi, rcx
0x180034704  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180034709  mov     rcx, cs:WPP_GLOBAL_Control
0x180034710  lea     rbp, WPP_GLOBAL_Control
0x180034717  cmp     rcx, rbp
0x18003471a  jz      short loc_180034744
0x18003471c  test    byte ptr [rcx+1Ch], 2
0x180034720  jz      short loc_180034744
0x180034722  cmp     byte ptr [rcx+19h], 5
0x180034726  jb      short loc_180034744
0x180034728  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18003472f  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180034736  mov     rcx, [rcx+10h]
0x18003473a  mov     edx, 1Bh
0x18003473f  call    WPP_SF_s
0x180034744  lea     rax, [rsp+48h+var_18]
0x180034749  xor     r9d, r9d
0x18003474c  mov     [rsp+48h+var_20], rax
0x180034751  lea     r8, aCmapfile; "cmapfile"
0x180034758  lea     rax, [rsp+48h+var_18+8]
0x18003475d  mov     rcx, rdi
0x180034760  lea     rdx, aMscp; "mscp"
0x180034767  mov     [rsp+48h+var_28], rax
0x18003476c  call    CspReadFile
0x180034771  mov     ebx, eax
0x180034773  test    eax, eax
0x180034775  jz      short loc_1800347C0
0x180034777  mov     edx, 2
0x18003477c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180034781  mov     rcx, cs:WPP_GLOBAL_Control
0x180034788  cmp     rcx, rbp
0x18003478b  jz      short loc_1800347B9
0x18003478d  test    byte ptr [rcx+1Ch], 1
0x180034791  jz      short loc_1800347B9
0x180034793  cmp     byte ptr [rcx+19h], 2
0x180034797  jb      short loc_1800347B9
0x180034799  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800347a0  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x1800347a7  mov     rcx, [rcx+10h]
0x1800347ab  mov     edx, 1Ch
0x1800347b0  mov     dword ptr [rsp+48h+var_28], ebx
0x1800347b4  call    WPP_SF_sd
0x1800347b9  mov     rcx, qword ptr [rsp+48h+var_18+8]
0x1800347be  jmp     short loc_1800347EF
0x1800347c0  mov     rax, qword ptr [rsp+48h+var_18+8]
0x1800347c5  xor     ecx, ecx
0x1800347c7  mov     r8d, dword ptr [rsp+48h+var_18]
0x1800347cc  mov     [rdi+238h], rax
0x1800347d3  mov     rax, 0BE82FA0BE82FA0BFh
0x1800347dd  mul     r8
0x1800347e0  mov     qword ptr [rsp+48h+var_18+8], rcx
0x1800347e5  shr     rdx, 6
0x1800347e9  mov     [rdi+240h], edx
0x1800347ef  test    rcx, rcx
0x1800347f2  jz      short loc_1800347F9
0x1800347f4  call    CspFreeH
0x1800347f9  mov     edx, 1
0x1800347fe  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180034803  mov     rcx, cs:WPP_GLOBAL_Control
0x18003480a  cmp     rcx, rbp
0x18003480d  jz      short loc_18003483B
0x18003480f  test    byte ptr [rcx+1Ch], 2
0x180034813  jz      short loc_18003483B
0x180034815  cmp     byte ptr [rcx+19h], 5
0x180034819  jb      short loc_18003483B
0x18003481b  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180034822  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180034829  mov     rcx, [rcx+10h]
0x18003482d  mov     edx, 1Dh
0x180034832  mov     dword ptr [rsp+48h+var_28], ebx
0x180034836  call    WPP_SF_sd
0x18003483b  mov     rbp, [rsp+48h+arg_8]
0x180034840  mov     eax, ebx
0x180034842  mov     rbx, [rsp+48h+arg_0]
0x180034847  add     rsp, 40h
0x18003484b  pop     rdi
0x18003484c  retn
```
