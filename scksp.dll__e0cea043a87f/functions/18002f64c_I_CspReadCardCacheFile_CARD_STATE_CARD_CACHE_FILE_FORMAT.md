# I_CspReadCardCacheFile(_CARD_STATE *,_CARD_CACHE_FILE_FORMAT *)

- ea: `0x18002f64c`
- end: `0x18002f78e`
- name: `?I_CspReadCardCacheFile@@YAKPEAU_CARD_STATE@@PEAU_CARD_CACHE_FILE_FORMAT@@@Z`
- size: `322`
- prototype: `unsigned int __fastcall(struct _CARD_STATE *, struct _CARD_CACHE_FILE_FORMAT *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18002fc8c`
- `0x18002fd88`
- `0x18002fe08`

## callees

- `0x18000d9d0`
- `0x180011fd8`
- `0x18002eb6c`
- `0x18002f64c`
- `0x18003d010`

## pseudocode

```c
__int64 __fastcall I_CspReadCardCacheFile(struct _CARD_STATE *a1, struct _CARD_CACHE_FILE_FORMAT *a2)
{
  __int64 v2; // rax
  unsigned int v5; // edi
  int v6; // r9d
  int v7; // ecx
  __int64 v8; // rcx
  __int128 v10; // [rsp+40h] [rbp-18h] BYREF

  v2 = *((_QWORD *)a1 + 1);
  v10 = 0;
  if ( v2 )
  {
    v5 = 0;
    if ( !*((_DWORD *)a1 + 155) )
    {
      v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, const char *, _QWORD, char *, __int128 *))(v2 + 248))(
             v2,
             0,
             "cardcf",
             0,
             (char *)&v10 + 8,
             &v10);
      if ( v5 )
        goto LABEL_14;
      v7 = v10;
      if ( (unsigned int)v10 < 6 )
      {
        v5 = 24;
        goto LABEL_14;
      }
      if ( *((_QWORD *)a1 + 76) )
      {
        CspFreeH(*((_QWORD *)a1 + 76));
        v7 = v10;
      }
      *((_QWORD *)a1 + 76) = *((_QWORD *)&v10 + 1);
      *((_DWORD *)a1 + 154) = v7;
      *((_DWORD *)a1 + 155) = 1;
      *((_QWORD *)&v10 + 1) = 0;
    }
    v8 = *((_QWORD *)a1 + 76);
    *(_DWORD *)a2 = *(_DWORD *)v8;
    *((_WORD *)a2 + 2) = *(_WORD *)(v8 + 4);
  }
  else
  {
    v5 = 87;
    WppTraceIndent((__int64)a1, 2u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_ss(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        (unsigned int)WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids,
        v6,
        (__int64)"pCardState->pCardData");
    }
  }
LABEL_14:
  if ( *((_QWORD *)&v10 + 1) )
    CspFreeH(*((_QWORD *)&v10 + 1));
  return v5;
}

```

## disassembly

```asm
0x18002f64c  mov     [rsp+arg_0], rbx
0x18002f651  mov     [rsp+arg_8], rsi
0x18002f656  push    rdi
0x18002f657  sub     rsp, 50h
0x18002f65b  mov     rax, [rcx+8]
0x18002f65f  xorps   xmm0, xmm0
0x18002f662  mov     rsi, rdx
0x18002f665  mov     rbx, rcx
0x18002f668  movups  [rsp+58h+var_18], xmm0
0x18002f66d  test    rax, rax
0x18002f670  jnz     short loc_18002F6CC
0x18002f672  lea     edx, [rax+2]
0x18002f675  lea     edi, [rax+57h]
0x18002f678  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002f67d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f684  lea     rax, WPP_GLOBAL_Control
0x18002f68b  cmp     rcx, rax
0x18002f68e  jz      loc_18002F76D
0x18002f694  test    byte ptr [rcx+1Ch], 1
0x18002f698  jz      loc_18002F76D
0x18002f69e  cmp     byte ptr [rcx+19h], 2
0x18002f6a2  jb      loc_18002F76D
0x18002f6a8  mov     rcx, [rcx+10h]
0x18002f6ac  lea     rax, aPcardstatePcar; "pCardState->pCardData"
0x18002f6b3  lea     edx, [rdi-4Ah]
0x18002f6b6  mov     [rsp+58h+var_38], rax
0x18002f6bb  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x18002f6c2  call    WPP_SF_ss
0x18002f6c7  jmp     loc_18002F76D
0x18002f6cc  xor     edi, edi
0x18002f6ce  cmp     [rcx+26Ch], edi
0x18002f6d4  jnz     loc_18002F75A
0x18002f6da  lea     rcx, [rsp+58h+var_18]
0x18002f6df  xor     r9d, r9d
0x18002f6e2  mov     [rsp+58h+var_30], rcx
0x18002f6e7  lea     r8, aCardcf; "cardcf"
0x18002f6ee  lea     rcx, [rsp+58h+var_18+8]
0x18002f6f3  xor     edx, edx
0x18002f6f5  mov     [rsp+58h+var_38], rcx
0x18002f6fa  mov     rcx, rax
0x18002f6fd  mov     rax, [rax+0F8h]
0x18002f704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f709  mov     edi, eax
0x18002f70b  test    eax, eax
0x18002f70d  jnz     short loc_18002F76D
0x18002f70f  mov     ecx, dword ptr [rsp+58h+var_18]
0x18002f713  cmp     ecx, 6
0x18002f716  jnb     short loc_18002F71D
0x18002f718  lea     edi, [rax+18h]
0x18002f71b  jmp     short loc_18002F76D
0x18002f71d  mov     rax, [rbx+260h]
0x18002f724  test    rax, rax
0x18002f727  jz      short loc_18002F735
0x18002f729  mov     rcx, rax
0x18002f72c  call    CspFreeH
0x18002f731  mov     ecx, dword ptr [rsp+58h+var_18]
0x18002f735  mov     rax, qword ptr [rsp+58h+var_18+8]
0x18002f73a  mov     [rbx+260h], rax
0x18002f741  mov     [rbx+268h], ecx
0x18002f747  mov     dword ptr [rbx+26Ch], 1
0x18002f751  mov     qword ptr [rsp+58h+var_18+8], 0
0x18002f75a  mov     rcx, [rbx+260h]
0x18002f761  mov     eax, [rcx]
0x18002f763  mov     [rsi], eax
0x18002f765  movzx   eax, word ptr [rcx+4]
0x18002f769  mov     [rsi+4], ax
0x18002f76d  mov     rcx, qword ptr [rsp+58h+var_18+8]
0x18002f772  test    rcx, rcx
0x18002f775  jz      short loc_18002F77C
0x18002f777  call    CspFreeH
0x18002f77c  mov     rbx, [rsp+58h+arg_0]
0x18002f781  mov     eax, edi
0x18002f783  mov     rsi, [rsp+58h+arg_8]
0x18002f788  add     rsp, 50h
0x18002f78c  pop     rdi
0x18002f78d  retn
```
