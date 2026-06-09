# CspWriteFile

- ea: `0x18002e3bc`
- end: `0x18002e526`
- name: `CspWriteFile`
- size: `362`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x18001a59c`
- `0x18002ec40`
- `0x18002ee0c`
- `0x18002f108`
- `0x1800318e8`

## callees

- `0x180011fd8`
- `0x18002c4d8`
- `0x18002e3bc`
- `0x18002eb6c`
- `0x18002fb68`
- `0x18002fd88`
- `0x18003001c`
- `0x18003c240`
- `0x18003d010`

## pseudocode

```c
__int64 __fastcall CspWriteFile(__int64 a1, __int64 a2, char *a3, __int64 a4, void *a5, unsigned int a6)
{
  __int64 v8; // rdx
  unsigned int String; // ebx
  unsigned int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rax
  int v13; // r9d
  unsigned __int16 v15[264]; // [rsp+50h] [rbp-238h] BYREF

  String = CspIncrementCacheFreshness((struct _CARD_STATE *)a1);
  if ( !String )
  {
    String = I_BuildFileCacheQueryString(v15, v8, "mscp", a3);
    if ( !String )
    {
      v10 = DeleteCachedCardData(a1, v15);
      if ( v10 != 1168 )
        String = v10;
      if ( !String )
      {
        v12 = *(_QWORD *)(a1 + 8);
        if ( v12 )
        {
          String = (*(__int64 (__fastcall **)(_QWORD, const char *, char *, _QWORD, void *, unsigned int))(v12 + 256))(
                     *(_QWORD *)(a1 + 8),
                     "mscp",
                     a3,
                     0,
                     a5,
                     a6);
          if ( !String )
            return (unsigned int)AddCachedCardData(a1, v15, 4u, 1u, a5, a6, 0);
        }
        else
        {
          String = 87;
          WppTraceIndent(v11, 2u);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_ss(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              28,
              (unsigned int)WPP_49528bda70d5313d10aecefe918ddecf_Traceguids,
              v13,
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
0x18002e3bc  mov     [rsp+arg_8], rbx
0x18002e3c1  mov     [rsp+arg_18], rbp
0x18002e3c6  push    rsi
0x18002e3c7  push    rdi
0x18002e3c8  push    r14
0x18002e3ca  sub     rsp, 270h
0x18002e3d1  mov     rax, cs:__security_cookie
0x18002e3d8  xor     rax, rsp
0x18002e3db  mov     [rsp+288h+var_28], rax
0x18002e3e3  mov     r14, [rsp+288h+arg_20]
0x18002e3eb  xor     eax, eax
0x18002e3ed  mov     rbp, r8
0x18002e3f0  mov     [rsp+288h+var_248], eax
0x18002e3f4  lea     r8, [rsp+288h+var_248]
0x18002e3f9  mov     [rsp+288h+var_244], ax
0x18002e3fe  mov     rdi, rcx
0x18002e401  lea     edx, [rax+4]
0x18002e404  call    CspIncrementCacheFreshness
0x18002e409  mov     ebx, eax
0x18002e40b  test    eax, eax
0x18002e40d  jnz     loc_18002E4FC
0x18002e413  mov     r9, rbp; char *
0x18002e416  lea     r8, aMscp; "mscp"
0x18002e41d  lea     rcx, [rsp+288h+var_238]; unsigned __int16 *
0x18002e422  call    ?I_BuildFileCacheQueryString@@YAKPEAGKPEAD1@Z; I_BuildFileCacheQueryString(ushort *,ulong,char *,char *)
0x18002e427  mov     ebx, eax
0x18002e429  test    eax, eax
0x18002e42b  jnz     loc_18002E4FC
0x18002e431  lea     rdx, [rsp+288h+var_238]
0x18002e436  mov     rcx, rdi
0x18002e439  call    DeleteCachedCardData
0x18002e43e  cmp     eax, 490h
0x18002e443  cmovnz  ebx, eax
0x18002e446  test    ebx, ebx
0x18002e448  jnz     loc_18002E4FC
0x18002e44e  mov     rax, [rdi+8]
0x18002e452  test    rax, rax
0x18002e455  jnz     short loc_18002E4A6
0x18002e457  lea     edx, [rax+2]
0x18002e45a  lea     ebx, [rax+57h]
0x18002e45d  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002e462  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e469  lea     rax, WPP_GLOBAL_Control
0x18002e470  cmp     rcx, rax
0x18002e473  jz      loc_18002E4FC
0x18002e479  test    byte ptr [rcx+1Ch], 1
0x18002e47d  jz      short loc_18002E4FC
0x18002e47f  cmp     byte ptr [rcx+19h], 2
0x18002e483  jb      short loc_18002E4FC
0x18002e485  mov     rcx, [rcx+10h]
0x18002e489  lea     rax, aPcardstatePcar; "pCardState->pCardData"
0x18002e490  lea     edx, [rbx-3Bh]
0x18002e493  mov     [rsp+288h+var_268], rax
0x18002e498  lea     r8, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids
0x18002e49f  call    WPP_SF_ss
0x18002e4a4  jmp     short loc_18002E4FC
0x18002e4a6  mov     esi, [rsp+288h+arg_28]
0x18002e4ad  lea     rdx, aMscp; "mscp"
0x18002e4b4  mov     rcx, rax
0x18002e4b7  mov     [rsp+288h+var_260], esi
0x18002e4bb  mov     rax, [rax+100h]
0x18002e4c2  xor     r9d, r9d
0x18002e4c5  mov     r8, rbp
0x18002e4c8  mov     [rsp+288h+var_268], r14
0x18002e4cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e4d2  mov     ebx, eax
0x18002e4d4  test    eax, eax
0x18002e4d6  jnz     short loc_18002E4FC
0x18002e4d8  mov     [rsp+288h+var_258], eax
0x18002e4dc  lea     r9d, [rax+1]
0x18002e4e0  mov     [rsp+288h+var_260], esi
0x18002e4e4  lea     r8d, [rax+4]
0x18002e4e8  lea     rdx, [rsp+288h+var_238]
0x18002e4ed  mov     [rsp+288h+var_268], r14
0x18002e4f2  mov     rcx, rdi
0x18002e4f5  call    AddCachedCardData
0x18002e4fa  mov     ebx, eax
0x18002e4fc  mov     eax, ebx
0x18002e4fe  mov     rcx, [rsp+288h+var_28]
0x18002e506  xor     rcx, rsp; StackCookie
0x18002e509  call    __security_check_cookie
0x18002e50e  lea     r11, [rsp+288h+var_18]
0x18002e516  mov     rbx, [r11+28h]
0x18002e51a  mov     rbp, [r11+38h]
0x18002e51e  mov     rsp, r11
0x18002e521  pop     r14
0x18002e523  pop     rdi
0x18002e524  pop     rsi
0x18002e525  retn
```
