# CspReadFile

- ea: `0x18002de34`
- end: `0x18002e02d`
- name: `CspReadFile`
- size: `505`
- prototype: `__int64 __fastcall(__int64, char *, char *, unsigned int, _QWORD *, __int64)`
- caller_count: `5`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x18002f1c8`
- `0x180031154`
- `0x18003179c`
- `0x1800346e8`
- `0x180034854`

## callees

- `0x18000d9d0`
- `0x180011fd8`
- `0x18002c4d8`
- `0x18002de34`
- `0x18002eb6c`
- `0x18002fb68`
- `0x180030378`
- `0x18003c240`
- `0x18003d010`

## pseudocode

```c
__int64 __fastcall CspReadFile(__int64 a1, char *a2, char *a3, unsigned int a4, _QWORD *a5, __int64 a6)
{
  unsigned int v6; // r15d
  int v9; // ebp
  __int64 v11; // rcx
  unsigned int String; // ebx
  unsigned int CachedCardData; // eax
  __int64 v14; // rax
  int v15; // r9d
  unsigned int v16; // eax
  _DWORD v18[4]; // [rsp+40h] [rbp-278h] BYREF
  unsigned __int16 v19[264]; // [rsp+50h] [rbp-268h] BYREF

  v6 = a4 & 0xFFFEFFFF;
  v18[0] = 0;
  v9 = a4 & 0x10000;
  if ( (a4 & 0x10000) == 0 )
    v6 = a4;
  String = I_BuildFileCacheQueryString(v19, (unsigned int)a2, a2, a3);
  if ( String )
    goto LABEL_20;
  if ( v9 )
    goto LABEL_7;
  CachedCardData = GetCachedCardData(a1, v19, String + 4, String + 1, a5, a6, v18);
  String = CachedCardData;
  if ( CachedCardData )
  {
    if ( CachedCardData != 1168 )
      goto LABEL_20;
LABEL_7:
    v14 = *(_QWORD *)(a1 + 8);
    if ( !v14 )
    {
      String = 87;
      WppTraceIndent(v11, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_ss(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          (unsigned int)WPP_49528bda70d5313d10aecefe918ddecf_Traceguids,
          v15,
          (__int64)"pCardState->pCardData");
      }
      goto LABEL_20;
    }
    v16 = (*(__int64 (__fastcall **)(_QWORD, char *, char *, _QWORD, _QWORD *, __int64))(v14 + 248))(
            *(_QWORD *)(a1 + 8),
            a2,
            a3,
            v6,
            a5,
            a6);
    String = v16;
    if ( !v9 )
    {
      if ( v16 )
      {
        if ( v16 == -2146435036 )
        {
          AddCachedCardData(a1, v19, 4);
          goto LABEL_20;
        }
      }
      else
      {
        String = AddCachedCardData(a1, v19, 4);
      }
    }
    if ( !String )
      return String;
    goto LABEL_20;
  }
  if ( (v18[0] & 2) == 0 )
    return String;
  String = -2146435036;
LABEL_20:
  if ( *a5 )
  {
    CspFreeH(*a5);
    *a5 = 0;
  }
  return String;
}

```

## disassembly

```asm
0x18002de34  push    rbx
0x18002de36  push    rbp
0x18002de37  push    rsi
0x18002de38  push    rdi
0x18002de39  push    r12
0x18002de3b  push    r13
0x18002de3d  push    r14
0x18002de3f  push    r15
0x18002de41  sub     rsp, 278h
0x18002de48  mov     rax, cs:__security_cookie
0x18002de4f  xor     rax, rsp
0x18002de52  mov     [rsp+2B8h+var_58], rax
0x18002de5a  mov     rdi, [rsp+2B8h+arg_20]
0x18002de62  mov     r15d, r9d
0x18002de65  mov     r14, [rsp+2B8h+arg_28]
0x18002de6d  mov     ebp, r9d
0x18002de70  btr     r15d, 10h
0x18002de75  mov     [rsp+2B8h+var_278], 0
0x18002de7d  mov     r13, r8
0x18002de80  mov     rsi, rcx
0x18002de83  and     ebp, 10000h
0x18002de89  lea     rcx, [rsp+2B8h+var_268]; unsigned __int16 *
0x18002de8e  mov     r12, rdx
0x18002de91  cmovz   r15d, r9d
0x18002de95  mov     r9, r8; char *
0x18002de98  mov     r8, rdx; char *
0x18002de9b  call    ?I_BuildFileCacheQueryString@@YAKPEAGKPEAD1@Z; I_BuildFileCacheQueryString(ushort *,ulong,char *,char *)
0x18002dea0  mov     ebx, eax
0x18002dea2  test    eax, eax
0x18002dea4  jnz     loc_18002DFF3
0x18002deaa  test    ebp, ebp
0x18002deac  jnz     short loc_18002DEE8
0x18002deae  lea     rax, [rsp+2B8h+var_278]
0x18002deb3  mov     rcx, rsi
0x18002deb6  mov     [rsp+2B8h+var_288], rax
0x18002debb  lea     r9d, [rbx+1]
0x18002debf  mov     [rsp+2B8h+var_290], r14
0x18002dec4  lea     r8d, [rbx+4]
0x18002dec8  lea     rdx, [rsp+2B8h+var_268]
0x18002decd  mov     [rsp+2B8h+var_298], rdi
0x18002ded2  call    GetCachedCardData
0x18002ded7  mov     ebx, eax
0x18002ded9  test    eax, eax
0x18002dedb  jz      short loc_18002DF4B
0x18002dedd  cmp     eax, 490h
0x18002dee2  jnz     loc_18002DFF3
0x18002dee8  mov     rax, [rsi+8]
0x18002deec  test    rax, rax
0x18002deef  jnz     short loc_18002DF60
0x18002def1  lea     edx, [rax+2]
0x18002def4  lea     ebx, [rax+57h]
0x18002def7  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002defc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002df03  lea     rax, WPP_GLOBAL_Control
0x18002df0a  cmp     rcx, rax
0x18002df0d  jz      loc_18002DFF3
0x18002df13  test    byte ptr [rcx+1Ch], 1
0x18002df17  jz      loc_18002DFF3
0x18002df1d  cmp     byte ptr [rcx+19h], 2
0x18002df21  jb      loc_18002DFF3
0x18002df27  mov     rcx, [rcx+10h]
0x18002df2b  lea     rax, aPcardstatePcar; "pCardState->pCardData"
0x18002df32  lea     edx, [rbx-3Ch]
0x18002df35  mov     [rsp+2B8h+var_298], rax
0x18002df3a  lea     r8, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids
0x18002df41  call    WPP_SF_ss
0x18002df46  jmp     loc_18002DFF3
0x18002df4b  test    byte ptr [rsp+2B8h+var_278], 2
0x18002df50  jz      loc_18002E007
0x18002df56  mov     ebx, 80100024h
0x18002df5b  jmp     loc_18002DFF3
0x18002df60  mov     rcx, rax
0x18002df63  mov     [rsp+2B8h+var_290], r14
0x18002df68  mov     rax, [rax+0F8h]
0x18002df6f  mov     r9d, r15d
0x18002df72  mov     r8, r13
0x18002df75  mov     [rsp+2B8h+var_298], rdi
0x18002df7a  mov     rdx, r12
0x18002df7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002df82  mov     ebx, eax
0x18002df84  test    ebp, ebp
0x18002df86  jnz     short loc_18002DFEF
0x18002df88  test    eax, eax
0x18002df8a  jz      short loc_18002DFBF
0x18002df8c  cmp     eax, 80100024h
0x18002df91  jnz     short loc_18002DFEF
0x18002df93  mov     dword ptr [rsp+2B8h+var_288], 2
0x18002df9b  lea     r9d, [rbp+1]
0x18002df9f  mov     dword ptr [rsp+2B8h+var_290], ebp
0x18002dfa3  lea     r8d, [rbp+4]
0x18002dfa7  lea     rdx, [rsp+2B8h+var_268]
0x18002dfac  mov     [rsp+2B8h+var_298], 0
0x18002dfb5  mov     rcx, rsi
0x18002dfb8  call    AddCachedCardData
0x18002dfbd  jmp     short loc_18002DFF3
0x18002dfbf  mov     eax, [r14]
0x18002dfc2  lea     rdx, [rsp+2B8h+var_268]
0x18002dfc7  mov     r9d, 1
0x18002dfcd  mov     dword ptr [rsp+2B8h+var_288], 0
0x18002dfd5  mov     dword ptr [rsp+2B8h+var_290], eax
0x18002dfd9  mov     rcx, rsi
0x18002dfdc  mov     rax, [rdi]
0x18002dfdf  mov     [rsp+2B8h+var_298], rax
0x18002dfe4  lea     r8d, [r9+3]
0x18002dfe8  call    AddCachedCardData
0x18002dfed  mov     ebx, eax
0x18002dfef  test    ebx, ebx
0x18002dff1  jz      short loc_18002E007
0x18002dff3  mov     rcx, [rdi]
0x18002dff6  test    rcx, rcx
0x18002dff9  jz      short loc_18002E007
0x18002dffb  call    CspFreeH
0x18002e000  mov     qword ptr [rdi], 0
0x18002e007  mov     eax, ebx
0x18002e009  mov     rcx, [rsp+2B8h+var_58]
0x18002e011  xor     rcx, rsp; StackCookie
0x18002e014  call    __security_check_cookie
0x18002e019  add     rsp, 278h
0x18002e020  pop     r15
0x18002e022  pop     r14
0x18002e024  pop     r13
0x18002e026  pop     r12
0x18002e028  pop     rdi
0x18002e029  pop     rsi
0x18002e02a  pop     rbp
0x18002e02b  pop     rbx
0x18002e02c  retn
```
