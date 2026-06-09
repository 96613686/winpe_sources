# PrepareCommandline(ushort *,_GUID const &,ushort const *,ushort *,ulong)

- ea: `0x18003c610`
- end: `0x18003c7dc`
- name: `?PrepareCommandline@@YAXPEAGAEBU_GUID@@PEBG0K@Z`
- size: `460`
- prototype: `void(unsigned __int16 *, const struct _GUID *, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18003bea0`

## callees

- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18001c210`
- `0x18002de18`
- `0x18002def8`
- `0x18002f290`
- `0x180033cc0`
- `0x180034658`
- `0x18003c610`
- `0x18003d0d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18003c644`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18003c644`
- `ole32!StringFromGUID2` at `0x18003c71e`
- `ole32!StringFromGUID2` at `0x18003c71e`

## string_xrefs

- `0x18003c746`: `Could not find second percent sign in the commandline`
- `0x18003c76c`: `Could not find second percent sign in the commandline`
- `0x18003c755`: `PrepareCommandline`
- `0x18003c784`: `PrepareCommandline`
- `0x18003c7b2`: `PrepareCommandline`
- `0x18003c775`: `Could not find percent sign in the commandline`
- `0x18003c79b`: `Could not find percent sign in the commandline`

## pseudocode

```c
void __fastcall PrepareCommandline(
        unsigned __int16 *a1,
        const struct _GUID *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  wchar_t *v8; // rax
  unsigned __int16 v9; // dx
  unsigned __int16 v10; // dx
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // rcx
  unsigned __int16 *v13; // rax
  char *v14; // rbx
  void *v15; // rdx
  void **lpMem; // rax
  void *v17; // rdx
  __int64 v18; // rcx
  char *v19; // rbx
  void *v20; // rdx
  OLECHAR sz[40]; // [rsp+30h] [rbp-368h] BYREF
  unsigned __int16 v22[368]; // [rsp+80h] [rbp-318h] BYREF

  v8 = wcschr(a3, 0x25u);
  if ( v8 && wcschr(v8 + 1, v9) )
  {
    memset_0(v22, 0, 0x2DCu);
    StringCbCopyW(v22, 0x2DCu, a3);
  }
  else
  {
    StringCbPrintfW(v22, 0x2DCu, L"%s /StiDevice:%%1 /StiEvent:%%2", a3);
  }
  v22[365] = 0;
  v11 = wcschr(v22, v10);
  if ( !v11 )
  {
    v19 = (char *)WiaTrace_TraceLog("Could not find percent sign in the commandline");
    WriteDbgTraceErrorWI("PrepareCommandline", v19);
    WiaTrcLib::Free((WiaTrcLib *)v19, v20);
    lpMem = (void **)WiaTrace_Trace("Could not find percent sign in the commandline");
    goto LABEL_14;
  }
  v12 = v11 + 1;
  if ( (unsigned __int64)(v11 - v22) < 0x16C )
    *v12 = 115;
  v13 = wcschr(v12, (unsigned __int16)v22);
  if ( !v13 )
  {
    v14 = (char *)WiaTrace_TraceLog("Could not find second percent sign in the commandline");
    WriteDbgTraceErrorWI("PrepareCommandline", v14);
    WiaTrcLib::Free((WiaTrcLib *)v14, v15);
    lpMem = (void **)WiaTrace_Trace("Could not find second percent sign in the commandline");
LABEL_14:
    WiaTrace_ProcessTrace_Ex(v18, v17, (void *)"PrepareCommandline", 1, lpMem);
    return;
  }
  if ( (unsigned __int64)(v13 - v22) < 0x16C )
    v13[1] = 115;
  StringFromGUID2(a2, sz, 40);
  StringCbPrintfW(a4, 0x2DCu, v22, a1, sz);
}

```

## disassembly

```asm
0x18003c610  push    rbx
0x18003c612  push    rbp
0x18003c613  push    rsi
0x18003c614  push    rdi
0x18003c615  push    r14
0x18003c617  sub     rsp, 370h
0x18003c61e  mov     rax, cs:__security_cookie
0x18003c625  xor     rax, rsp
0x18003c628  mov     [rsp+398h+var_38], rax
0x18003c630  mov     rbp, rdx
0x18003c633  mov     rsi, rcx
0x18003c636  mov     edx, 25h ; '%'; Ch
0x18003c63b  mov     rcx, r8; Str
0x18003c63e  mov     r14, r9
0x18003c641  mov     rdi, r8
0x18003c644  call    cs:__imp_wcschr
0x18003c64a  test    rax, rax
0x18003c64d  jz      short loc_18003C688
0x18003c64f  lea     rcx, [rax+2]; unsigned __int16 *
0x18003c653  call    ?wcschr@@YAPEAGPEAGG@Z; wcschr(ushort *,ushort)
0x18003c658  test    rax, rax
0x18003c65b  jz      short loc_18003C688
0x18003c65d  mov     ebx, 2DCh
0x18003c662  lea     rcx, [rsp+398h+var_318]; void *
0x18003c66a  mov     r8d, ebx; Size
0x18003c66d  xor     edx, edx; Val
0x18003c66f  call    memset_0
0x18003c674  mov     r8, rdi; unsigned __int16 *
0x18003c677  lea     rcx, [rsp+398h+var_318]; unsigned __int16 *
0x18003c67f  mov     edx, ebx; unsigned __int64
0x18003c681  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18003c686  jmp     short loc_18003C6A6
0x18003c688  mov     ebx, 2DCh
0x18003c68d  lea     r8, aSStidevice1Sti; "%s /StiDevice:%%1 /StiEvent:%%2"
0x18003c694  mov     edx, ebx; unsigned __int64
0x18003c696  lea     rcx, [rsp+398h+var_318]; unsigned __int16 *
0x18003c69e  mov     r9, rdi
0x18003c6a1  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003c6a6  xor     eax, eax
0x18003c6a8  lea     rcx, [rsp+398h+var_318]; unsigned __int16 *
0x18003c6b0  mov     [rsp+398h+var_3E], ax
0x18003c6b8  call    ?wcschr@@YAPEAGPEAGG@Z; wcschr(ushort *,ushort)
0x18003c6bd  test    rax, rax
0x18003c6c0  jz      loc_18003C775
0x18003c6c6  lea     rcx, [rax+2]; unsigned __int16 *
0x18003c6ca  mov     edi, 73h ; 's'
0x18003c6cf  lea     rdx, [rsp+398h+var_318]; unsigned __int16
0x18003c6d7  sub     rax, rdx
0x18003c6da  sar     rax, 1
0x18003c6dd  cmp     rax, 16Ch
0x18003c6e3  jnb     short loc_18003C6E8
0x18003c6e5  mov     [rcx], di
0x18003c6e8  call    ?wcschr@@YAPEAGPEAGG@Z; wcschr(ushort *,ushort)
0x18003c6ed  test    rax, rax
0x18003c6f0  jz      short loc_18003C746
0x18003c6f2  lea     rcx, [rsp+398h+var_318]
0x18003c6fa  mov     rdx, rax
0x18003c6fd  sub     rdx, rcx
0x18003c700  sar     rdx, 1
0x18003c703  cmp     rdx, 16Ch
0x18003c70a  jnb     short loc_18003C710
0x18003c70c  mov     [rax+2], di
0x18003c710  mov     r8d, 28h ; '('; cchMax
0x18003c716  lea     rdx, [rsp+398h+sz]; lpsz
0x18003c71b  mov     rcx, rbp; rguid
0x18003c71e  call    cs:__imp_StringFromGUID2
0x18003c724  lea     rax, [rsp+398h+sz]
0x18003c729  mov     r9, rsi
0x18003c72c  lea     r8, [rsp+398h+var_318]; unsigned __int16 *
0x18003c734  mov     [rsp+398h+lpMem], rax
0x18003c739  mov     rdx, rbx; unsigned __int64
0x18003c73c  mov     rcx, r14; unsigned __int16 *
0x18003c73f  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003c744  jmp     short loc_18003C7BE
0x18003c746  lea     rcx, aCouldNotFindSe; "Could not find second percent sign in t"...
0x18003c74d  call    WiaTrace_TraceLog
0x18003c752  mov     rdx, rax; char *
0x18003c755  lea     rcx, aPreparecommand; "PrepareCommandline"
0x18003c75c  mov     rbx, rax
0x18003c75f  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18003c764  mov     rcx, rbx; this
0x18003c767  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003c76c  lea     rcx, aCouldNotFindSe; "Could not find second percent sign in t"...
0x18003c773  jmp     short loc_18003C7A2
0x18003c775  lea     rcx, aCouldNotFindPe; "Could not find percent sign in the comm"...
0x18003c77c  call    WiaTrace_TraceLog
0x18003c781  mov     rdx, rax; char *
0x18003c784  lea     rcx, aPreparecommand; "PrepareCommandline"
0x18003c78b  mov     rbx, rax
0x18003c78e  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18003c793  mov     rcx, rbx; this
0x18003c796  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003c79b  lea     rcx, aCouldNotFindPe; "Could not find percent sign in the comm"...
0x18003c7a2  call    WiaTrace_Trace
0x18003c7a7  mov     r9d, 1; int
0x18003c7ad  mov     [rsp+398h+lpMem], rax; lpMem
0x18003c7b2  lea     r8, aPreparecommand; "PrepareCommandline"
0x18003c7b9  call    WiaTrace_ProcessTrace_Ex
0x18003c7be  mov     rcx, [rsp+398h+var_38]
0x18003c7c6  xor     rcx, rsp; StackCookie
0x18003c7c9  call    __security_check_cookie
0x18003c7ce  add     rsp, 370h
0x18003c7d5  pop     r14
0x18003c7d7  pop     rdi
0x18003c7d8  pop     rsi
0x18003c7d9  pop     rbp
0x18003c7da  pop     rbx
0x18003c7db  retn
```
