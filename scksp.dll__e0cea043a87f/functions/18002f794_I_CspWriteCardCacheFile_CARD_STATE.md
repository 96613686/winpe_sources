# I_CspWriteCardCacheFile(_CARD_STATE *)

- ea: `0x18002f794`
- end: `0x18002f82a`
- name: `?I_CspWriteCardCacheFile@@YAKPEAU_CARD_STATE@@@Z`
- size: `150`
- prototype: `unsigned int __fastcall(struct _CARD_STATE *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18002fd88`

## callees

- `0x180011fd8`
- `0x18002eb6c`
- `0x18002f794`
- `0x18003d010`

## pseudocode

```c
__int64 __fastcall I_CspWriteCardCacheFile(struct _CARD_STATE *a1)
{
  __int64 v1; // r10
  unsigned int v2; // ebx
  int v3; // r9d

  v1 = *((_QWORD *)a1 + 1);
  if ( v1 )
  {
    return (*(unsigned int (__fastcall **)(__int64, _QWORD, const char *, _QWORD, _QWORD, _DWORD))(v1 + 256))(
             v1,
             0,
             "cardcf",
             0,
             *((_QWORD *)a1 + 76),
             *((_DWORD *)a1 + 154));
  }
  else
  {
    v2 = 87;
    WppTraceIndent((__int64)a1, 2u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_ss(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        (unsigned int)WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids,
        v3,
        (__int64)"pCardState->pCardData");
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18002f794  push    rbx
0x18002f796  sub     rsp, 40h
0x18002f79a  mov     r10, [rcx+8]
0x18002f79e  test    r10, r10
0x18002f7a1  jnz     short loc_18002F7EF
0x18002f7a3  lea     ebx, [r10+57h]
0x18002f7a7  lea     edx, [rbx-55h]
0x18002f7aa  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002f7af  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f7b6  lea     rax, WPP_GLOBAL_Control
0x18002f7bd  cmp     rcx, rax
0x18002f7c0  jz      short loc_18002F822
0x18002f7c2  test    byte ptr [rcx+1Ch], 1
0x18002f7c6  jz      short loc_18002F822
0x18002f7c8  cmp     byte ptr [rcx+19h], 2
0x18002f7cc  jb      short loc_18002F822
0x18002f7ce  mov     rcx, [rcx+10h]
0x18002f7d2  lea     rax, aPcardstatePcar; "pCardState->pCardData"
0x18002f7d9  lea     edx, [rbx-49h]
0x18002f7dc  mov     [rsp+48h+var_28], rax
0x18002f7e1  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x18002f7e8  call    WPP_SF_ss
0x18002f7ed  jmp     short loc_18002F822
0x18002f7ef  mov     eax, [rcx+268h]
0x18002f7f5  lea     r8, aCardcf; "cardcf"
0x18002f7fc  mov     [rsp+48h+var_20], eax
0x18002f800  xor     r9d, r9d
0x18002f803  mov     rax, [rcx+260h]
0x18002f80a  xor     edx, edx
0x18002f80c  mov     [rsp+48h+var_28], rax
0x18002f811  mov     rcx, r10
0x18002f814  mov     rax, [r10+100h]
0x18002f81b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f820  mov     ebx, eax
0x18002f822  mov     eax, ebx
0x18002f824  add     rsp, 40h
0x18002f828  pop     rbx
0x18002f829  retn
```
