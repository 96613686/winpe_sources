# CspDeleteFile

- ea: `0x18002d61c`
- end: `0x18002d738`
- name: `CspDeleteFile`
- size: `284`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18001a59c`
- `0x18002e180`
- `0x1800318e8`

## callees

- `0x180011fd8`
- `0x18002c4d8`
- `0x18002d61c`
- `0x18002eb6c`
- `0x18002fd88`
- `0x18003001c`
- `0x18003c240`
- `0x18003d010`

## pseudocode

```c
__int64 __fastcall CspDeleteFile(__int64 a1, __int64 a2, __int64 a3, char *a4)
{
  __int64 v6; // rdx
  unsigned int String; // ebx
  unsigned int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // rax
  int v11; // r9d
  unsigned __int16 v13[264]; // [rsp+40h] [rbp-228h] BYREF

  String = CspIncrementCacheFreshness((struct _CARD_STATE *)a1);
  if ( !String )
  {
    String = I_BuildFileCacheQueryString(v13, v6, "mscp", a4);
    if ( !String )
    {
      v8 = DeleteCachedCardData(a1, v13);
      if ( v8 != 1168 )
        String = v8;
      if ( !String )
      {
        v10 = *(_QWORD *)(a1 + 8);
        if ( v10 )
        {
          return (*(unsigned int (__fastcall **)(_QWORD, const char *, char *, _QWORD))(v10 + 264))(
                   *(_QWORD *)(a1 + 8),
                   "mscp",
                   a4,
                   0);
        }
        else
        {
          String = 87;
          WppTraceIndent(v9, 2u);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_ss(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              29,
              (unsigned int)WPP_49528bda70d5313d10aecefe918ddecf_Traceguids,
              v11,
              (__int64)"pCardState->pCardData");
          }
        }
      }
    }
  }
  return String;
}

```

## disassembly

```asm
0x18002d61c  mov     [rsp+arg_8], rbx
0x18002d621  mov     [rsp+arg_10], rsi
0x18002d626  push    rdi
0x18002d627  sub     rsp, 260h
0x18002d62e  mov     rax, cs:__security_cookie
0x18002d635  xor     rax, rsp
0x18002d638  mov     [rsp+268h+var_18], rax
0x18002d640  xor     eax, eax
0x18002d642  lea     r8, [rsp+268h+var_238]
0x18002d647  mov     rsi, r9
0x18002d64a  mov     [rsp+268h+var_238], eax
0x18002d64e  mov     rdi, rcx
0x18002d651  mov     [rsp+268h+var_234], ax
0x18002d656  lea     edx, [rax+4]
0x18002d659  call    CspIncrementCacheFreshness
0x18002d65e  mov     ebx, eax
0x18002d660  test    eax, eax
0x18002d662  jnz     loc_18002D711
0x18002d668  mov     r9, rsi; char *
0x18002d66b  lea     r8, aMscp; "mscp"
0x18002d672  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x18002d677  call    ?I_BuildFileCacheQueryString@@YAKPEAGKPEAD1@Z; I_BuildFileCacheQueryString(ushort *,ulong,char *,char *)
0x18002d67c  mov     ebx, eax
0x18002d67e  test    eax, eax
0x18002d680  jnz     loc_18002D711
0x18002d686  lea     rdx, [rsp+268h+var_228]
0x18002d68b  mov     rcx, rdi
0x18002d68e  call    DeleteCachedCardData
0x18002d693  cmp     eax, 490h
0x18002d698  cmovnz  ebx, eax
0x18002d69b  test    ebx, ebx
0x18002d69d  jnz     short loc_18002D711
0x18002d69f  mov     rax, [rdi+8]
0x18002d6a3  test    rax, rax
0x18002d6a6  jnz     short loc_18002D6F3
0x18002d6a8  lea     edx, [rax+2]
0x18002d6ab  lea     ebx, [rax+57h]
0x18002d6ae  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002d6b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d6ba  lea     rax, WPP_GLOBAL_Control
0x18002d6c1  cmp     rcx, rax
0x18002d6c4  jz      short loc_18002D711
0x18002d6c6  test    byte ptr [rcx+1Ch], 1
0x18002d6ca  jz      short loc_18002D711
0x18002d6cc  cmp     byte ptr [rcx+19h], 2
0x18002d6d0  jb      short loc_18002D711
0x18002d6d2  mov     rcx, [rcx+10h]
0x18002d6d6  lea     rax, aPcardstatePcar; "pCardState->pCardData"
0x18002d6dd  lea     edx, [rbx-3Ah]
0x18002d6e0  mov     [rsp+268h+var_248], rax
0x18002d6e5  lea     r8, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids
0x18002d6ec  call    WPP_SF_ss
0x18002d6f1  jmp     short loc_18002D711
0x18002d6f3  mov     rcx, rax
0x18002d6f6  lea     rdx, aMscp; "mscp"
0x18002d6fd  mov     rax, [rax+108h]
0x18002d704  xor     r9d, r9d
0x18002d707  mov     r8, rsi
0x18002d70a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d70f  mov     ebx, eax
0x18002d711  mov     eax, ebx
0x18002d713  mov     rcx, [rsp+268h+var_18]
0x18002d71b  xor     rcx, rsp; StackCookie
0x18002d71e  call    __security_check_cookie
0x18002d723  lea     r11, [rsp+268h+var_8]
0x18002d72b  mov     rbx, [r11+18h]
0x18002d72f  mov     rsi, [r11+20h]
0x18002d733  mov     rsp, r11
0x18002d736  pop     rdi
0x18002d737  retn
```
