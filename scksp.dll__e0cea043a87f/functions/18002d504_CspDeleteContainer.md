# CspDeleteContainer

- ea: `0x18002d504`
- end: `0x18002d613`
- name: `CspDeleteContainer`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18002e180`

## callees

- `0x180011fd8`
- `0x18002cda8`
- `0x18002d504`
- `0x18002eb6c`
- `0x18002fd88`
- `0x18003001c`
- `0x18003c240`
- `0x18003d010`

## string_xrefs

- `0x18002d5be`: `Cached_ContainerInfo`

## pseudocode

```c
__int64 __fastcall CspDeleteContainer(__int64 a1, unsigned __int8 a2)
{
  int v2; // esi
  unsigned int v4; // ebx
  int v5; // r9d
  __int64 v6; // rdx
  unsigned __int16 v8[264]; // [rsp+40h] [rbp-228h] BYREF

  v2 = a2;
  if ( *(_QWORD *)(a1 + 8) )
  {
    v4 = CspIncrementCacheFreshness((struct _CARD_STATE *)a1);
    if ( !v4 )
    {
      LOBYTE(v6) = v2;
      v4 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(*(_QWORD *)(a1 + 8) + 136LL))(
             *(_QWORD *)(a1 + 8),
             v6,
             0);
      if ( !v4 )
      {
        StringCbPrintfW(v8, 0x104u, L"%s_%02x", L"Cached_ContainerInfo", v2);
        DeleteCachedCardData(a1, v8);
      }
    }
  }
  else
  {
    v4 = 87;
    WppTraceIndent(a1, 2u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_ss(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        (unsigned int)WPP_49528bda70d5313d10aecefe918ddecf_Traceguids,
        v5,
        (__int64)"pCardState->pCardData");
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18002d504  mov     [rsp+arg_10], rbx
0x18002d509  mov     [rsp+arg_18], rsi
0x18002d50e  push    rdi
0x18002d50f  sub     rsp, 260h
0x18002d516  mov     rax, cs:__security_cookie
0x18002d51d  xor     rax, rsp
0x18002d520  mov     [rsp+268h+var_18], rax
0x18002d528  xor     eax, eax
0x18002d52a  movzx   esi, dl
0x18002d52d  mov     rdi, rcx
0x18002d530  mov     [rsp+268h+var_238], eax
0x18002d534  mov     [rsp+268h+var_234], ax
0x18002d539  lea     edx, [rax+2]
0x18002d53c  cmp     [rcx+8], rax
0x18002d540  jnz     short loc_18002D592
0x18002d542  lea     ebx, [rax+57h]
0x18002d545  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002d54a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d551  lea     rax, WPP_GLOBAL_Control
0x18002d558  cmp     rcx, rax
0x18002d55b  jz      loc_18002D5EC
0x18002d561  test    byte ptr [rcx+1Ch], 1
0x18002d565  jz      loc_18002D5EC
0x18002d56b  cmp     byte ptr [rcx+19h], 2
0x18002d56f  jb      short loc_18002D5EC
0x18002d571  mov     rcx, [rcx+10h]
0x18002d575  lea     rax, aPcardstatePcar; "pCardState->pCardData"
0x18002d57c  lea     edx, [rbx-4Bh]
0x18002d57f  mov     [rsp+268h+var_248], rax
0x18002d584  lea     r8, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids
0x18002d58b  call    WPP_SF_ss
0x18002d590  jmp     short loc_18002D5EC
0x18002d592  lea     r8, [rsp+268h+var_238]
0x18002d597  call    CspIncrementCacheFreshness
0x18002d59c  mov     ebx, eax
0x18002d59e  test    eax, eax
0x18002d5a0  jnz     short loc_18002D5EC
0x18002d5a2  mov     rcx, [rdi+8]
0x18002d5a6  xor     r8d, r8d
0x18002d5a9  mov     dl, sil
0x18002d5ac  mov     rax, [rcx+88h]
0x18002d5b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d5b8  mov     ebx, eax
0x18002d5ba  test    eax, eax
0x18002d5bc  jnz     short loc_18002D5EC
0x18002d5be  lea     r9, aCachedContaine_0; "Cached_ContainerInfo"
0x18002d5c5  mov     dword ptr [rsp+268h+var_248], esi
0x18002d5c9  lea     r8, aS02x; "%s_%02x"
0x18002d5d0  mov     edx, 104h; unsigned __int64
0x18002d5d5  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x18002d5da  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002d5df  lea     rdx, [rsp+268h+var_228]
0x18002d5e4  mov     rcx, rdi
0x18002d5e7  call    DeleteCachedCardData
0x18002d5ec  mov     eax, ebx
0x18002d5ee  mov     rcx, [rsp+268h+var_18]
0x18002d5f6  xor     rcx, rsp; StackCookie
0x18002d5f9  call    __security_check_cookie
0x18002d5fe  lea     r11, [rsp+268h+var_8]
0x18002d606  mov     rbx, [r11+20h]
0x18002d60a  mov     rsi, [r11+28h]
0x18002d60e  mov     rsp, r11
0x18002d611  pop     rdi
0x18002d612  retn
```
