# BaseSrvActivationContextCacheInsertEntry

- ea: `0x180005170`
- end: `0x18000556e`
- name: `BaseSrvActivationContextCacheInsertEntry`
- size: `1022`
- prototype: `__int64 __fastcall(__int64, void *, __int64, _DWORD *, _QWORD *, const WCHAR *SourceString, const void **, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x180003310`

## callees

- `0x180005170`
- `0x180005580`
- `0x1800056a0`
- `0x1800057d0`
- `0x180006ccd`
- `0x180006cf0`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x180005236`
- `ntdll!RtlEnterCriticalSection` at `0x180005236`
- `ntdll!RtlLeaveCriticalSection` at `0x180005479`
- `ntdll!RtlLeaveCriticalSection` at `0x180007019`
- `ntdll!RtlLeaveCriticalSection` at `0x180005479`
- `ntdll!RtlLeaveCriticalSection` at `0x180007019`
- `ntdll!DbgPrintEx` at `0x1800053ef`
- `ntdll!DbgPrintEx` at `0x1800053ef`
- `ntdll!RtlInitUnicodeString` at `0x180005521`
- `ntdll!RtlInitUnicodeString` at `0x180005521`
- `ntdll!RtlLookupElementGenericTableFullAvl` at `0x180005262`
- `ntdll!RtlLookupElementGenericTableFullAvl` at `0x180005262`
- `ntdll!RtlInsertElementGenericTableFullAvl` at `0x1800052a1`
- `ntdll!RtlInsertElementGenericTableFullAvl` at `0x1800052a1`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x1800052f1`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x1800052f1`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800053cd`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800053cd`
- `ntdll!NtDuplicateObject` at `0x1800051fe`
- `ntdll!NtDuplicateObject` at `0x1800051fe`

## string_xrefs

- `0x1800053e1`: `Fail to remove cache entry\n`

## pseudocode

```c
__int64 __fastcall BaseSrvActivationContextCacheInsertEntry(
        __int64 a1,
        void *a2,
        __int64 a3,
        _DWORD *a4,
        _QWORD *a5,
        const WCHAR *SourceString,
        const void **a7,
        int a8)
{
  int v12; // ebx
  NTSTATUS v13; // edi
  struct _RTL_BALANCED_LINKS *v14; // rax
  struct _RTL_BALANCED_LINKS *v15; // rdx
  struct _RTL_BALANCED_LINKS *inserted; // rbx
  struct _RTL_AVL_TABLE *v17; // rcx
  PRTL_AVL_TABLE v18; // rax
  struct _RTL_BALANCED_LINKS *v19; // rdx
  struct _RTL_AVL_TABLE *v20; // r9
  PRTL_AVL_TABLE v21; // rax
  struct _RTL_BALANCED_LINKS *v22; // rdx
  struct _RTL_BALANCED_LINKS *v23; // rcx
  struct _RTL_BALANCED_LINKS *Parent; // rax
  struct _RTL_BALANCED_LINKS *LeftChild; // rcx
  PRTL_AVL_TABLE v26; // rax
  struct _RTL_BALANCED_LINKS *v27; // rcx
  TABLE_SEARCH_RESULT SearchResult; // [rsp+40h] [rbp-118h] BYREF
  PVOID NodeOrParent; // [rsp+48h] [rbp-110h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-108h] BYREF
  __int128 Buffer; // [rsp+60h] [rbp-F8h] BYREF
  _OWORD v33[6]; // [rsp+70h] [rbp-E8h] BYREF
  void *TargetHandle[2]; // [rsp+D0h] [rbp-88h] BYREF
  __int128 v35; // [rsp+E0h] [rbp-78h]
  __int128 v36; // [rsp+F0h] [rbp-68h] BYREF
  __int128 v37; // [rsp+100h] [rbp-58h] BYREF
  struct _RTL_BALANCED_LINKS *RightChild; // [rsp+110h] [rbp-48h]

  NodeOrParent = 0;
  SearchResult = TableEmptyTree;
  memset_0(&Buffer, 0, 0xB8u);
  v12 = NtDuplicateObject((HANDLE)0xFFFFFFFFFFFFFFFFLL, a2, (HANDLE)0xFFFFFFFFFFFFFFFFLL, TargetHandle, 0, 0, 2u);
  if ( v12 >= 0 )
  {
    v12 = BaseSrvActivationContextCacheDuplicateKey(v33, a1);
    if ( v12 >= 0 )
    {
      v12 = BaseSrvActivationContextCacheDuplicateUnicodeString((__int64)&v37, a7);
      if ( v12 >= 0 )
      {
        TargetHandle[1] = *(void **)a3;
        LODWORD(v35) = *(_DWORD *)(a3 + 8);
        DWORD1(v35) = *a4;
        HIDWORD(RightChild) = a8;
        *((_QWORD *)&v35 + 1) = *a5;
        DestinationString = 0;
        RtlInitUnicodeString(&DestinationString, SourceString);
        v12 = BaseSrvActivationContextCacheDuplicateUnicodeString((__int64)&v36, (const void **)&DestinationString);
      }
    }
  }
  if ( v12 >= 0 )
  {
    v13 = RtlEnterCriticalSection(&SxsActCtxCacheCS);
    if ( v13 < 0 )
    {
      BaseSrvActivationContextCacheFreeEntry(&Buffer);
      return (unsigned int)v13;
    }
    v14 = (struct _RTL_BALANCED_LINKS *)RtlLookupElementGenericTableFullAvl(
                                          g_SxsActCtxCache,
                                          &Buffer,
                                          &NodeOrParent,
                                          &SearchResult);
    v15 = v14;
    if ( SearchResult == TableFoundNode )
    {
      Parent = v14->Parent;
      if ( Parent->LeftChild != v15 )
        goto LABEL_19;
      LeftChild = v15->LeftChild;
      if ( LeftChild->Parent != v15 )
        goto LABEL_19;
      LeftChild->Parent = Parent;
      Parent->LeftChild = LeftChild;
      v26 = g_SxsActCtxCache + 1;
      v27 = g_SxsActCtxCache[1].BalancedRoot.Parent;
      if ( (PRTL_AVL_TABLE)v27->LeftChild != &g_SxsActCtxCache[1] )
        goto LABEL_19;
      v15->Parent = v27;
      v15->LeftChild = &v26->BalancedRoot;
      v27->LeftChild = v15;
      v26->BalancedRoot.Parent = v15;
    }
    else
    {
      inserted = (struct _RTL_BALANCED_LINKS *)RtlInsertElementGenericTableFullAvl(
                                                 g_SxsActCtxCache,
                                                 &Buffer,
                                                 0xB8u,
                                                 0,
                                                 NodeOrParent,
                                                 SearchResult);
      if ( inserted )
      {
        memset_0(&Buffer, 0, 0xB8u);
        v17 = g_SxsActCtxCache;
        v18 = g_SxsActCtxCache + 1;
        v19 = g_SxsActCtxCache[1].BalancedRoot.Parent;
        if ( (PRTL_AVL_TABLE)v19->LeftChild == &g_SxsActCtxCache[1] )
        {
          inserted->Parent = v19;
          inserted->LeftChild = &v18->BalancedRoot;
          v19->LeftChild = inserted;
          v18->BalancedRoot.Parent = inserted;
          if ( RtlNumberGenericTableElementsAvl(v17) <= 0x100 )
            goto LABEL_20;
          v20 = g_SxsActCtxCache;
          v21 = g_SxsActCtxCache + 1;
          v22 = g_SxsActCtxCache[1].BalancedRoot.LeftChild;
          if ( (PRTL_AVL_TABLE)v22->Parent == &g_SxsActCtxCache[1] )
          {
            v23 = v22->LeftChild;
            if ( v23->Parent == v22 )
            {
              g_SxsActCtxCache[1].BalancedRoot.LeftChild = v23;
              v23->Parent = &v21->BalancedRoot;
              Buffer = *(_OWORD *)&v22->Parent;
              v33[0] = *(_OWORD *)&v22->RightChild;
              v33[1] = *(_OWORD *)&v22[1].Parent;
              v33[2] = *(_OWORD *)&v22[1].RightChild;
              v33[3] = *(_OWORD *)&v22[2].Parent;
              v33[4] = *(_OWORD *)&v22[2].RightChild;
              v33[5] = *(_OWORD *)&v22[3].Parent;
              *(_OWORD *)TargetHandle = *(_OWORD *)&v22[3].RightChild;
              v35 = *(_OWORD *)&v22[4].Parent;
              v36 = *(_OWORD *)&v22[4].RightChild;
              v37 = *(_OWORD *)&v22[5].Parent;
              RightChild = v22[5].RightChild;
              if ( !RtlDeleteElementGenericTableAvl(v20, v22) )
              {
                DbgPrintEx(0x33u, 0, "Fail to remove cache entry\n");
                memset_0(&Buffer, 0, 0xB8u);
                v13 = -1073741271;
              }
              goto LABEL_20;
            }
          }
        }
LABEL_19:
        __fastfail(3u);
      }
      v13 = -1073741801;
    }
LABEL_20:
    BaseSrvActivationContextCacheFreeEntry(&Buffer);
    RtlLeaveCriticalSection(&SxsActCtxCacheCS);
    return (unsigned int)v13;
  }
  BaseSrvActivationContextCacheFreeEntry(&Buffer);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180005170  mov     [rsp+arg_10], rbx
0x180005175  mov     [rsp+arg_18], rsi
0x18000517a  push    rdi
0x18000517b  push    r12
0x18000517d  push    r13
0x18000517f  push    r14
0x180005181  push    r15
0x180005183  sub     rsp, 130h
0x18000518a  mov     rax, cs:__security_cookie
0x180005191  xor     rax, rsp
0x180005194  mov     [rsp+158h+var_38], rax
0x18000519c  mov     r15, r9
0x18000519f  mov     rdi, r8
0x1800051a2  mov     rbx, rdx
0x1800051a5  mov     rsi, rcx
0x1800051a8  mov     r12, [rsp+158h+SourceString]
0x1800051b0  mov     r14, [rsp+158h+arg_30]
0x1800051b8  xor     r13d, r13d
0x1800051bb  mov     [rsp+158h+NodeOrParent], r13
0x1800051c0  mov     [rsp+158h+SearchResult], r13d
0x1800051c5  xor     edx, edx; Val
0x1800051c7  mov     r8d, 0B8h; Size
0x1800051cd  lea     rcx, [rsp+158h+Buffer]; void *
0x1800051d2  call    memset_0
0x1800051d7  mov     [rsp+158h+Options], 2; Options
0x1800051df  mov     [rsp+158h+HandleAttributes], r13d; HandleAttributes
0x1800051e4  mov     [rsp+158h+DesiredAccess], r13d; DesiredAccess
0x1800051e9  lea     r9, [rsp+158h+TargetHandle]; TargetHandle
0x1800051f1  mov     r8, 0FFFFFFFFFFFFFFFFh; TargetProcessHandle
0x1800051f8  mov     rdx, rbx; SourceHandle
0x1800051fb  mov     rcx, r8; SourceProcessHandle
0x1800051fe  call    cs:__imp_NtDuplicateObject
0x180005205  nop     dword ptr [rax+rax+00h]
0x18000520a  mov     ebx, eax
0x18000520c  test    eax, eax
0x18000520e  js      short loc_180005227
0x180005210  mov     rdx, rsi
0x180005213  lea     rcx, [rsp+158h+var_E8]
0x180005218  call    BaseSrvActivationContextCacheDuplicateKey
0x18000521d  mov     ebx, eax
0x18000521f  test    eax, eax
0x180005221  jns     loc_1800054B5
0x180005227  test    ebx, ebx
0x180005229  js      loc_180005546
0x18000522f  lea     rcx, SxsActCtxCacheCS; CriticalSection
0x180005236  call    cs:__imp_RtlEnterCriticalSection
0x18000523d  nop     dword ptr [rax+rax+00h]
0x180005242  mov     edi, eax
0x180005244  test    eax, eax
0x180005246  js      loc_18000555F
0x18000524c  lea     r9, [rsp+158h+SearchResult]; SearchResult
0x180005251  lea     r8, [rsp+158h+NodeOrParent]; NodeOrParent
0x180005256  lea     rdx, [rsp+158h+Buffer]; Buffer
0x18000525b  mov     rcx, cs:g_SxsActCtxCache; Table
0x180005262  call    cs:__imp_RtlLookupElementGenericTableFullAvl
0x180005269  nop     dword ptr [rax+rax+00h]
0x18000526e  mov     rdx, rax
0x180005271  mov     ecx, [rsp+158h+SearchResult]
0x180005275  cmp     ecx, 1
0x180005278  jz      loc_180005417
0x18000527e  mov     [rsp+158h+HandleAttributes], ecx; SearchResult
0x180005282  mov     rax, [rsp+158h+NodeOrParent]
0x180005287  mov     qword ptr [rsp+158h+DesiredAccess], rax; NodeOrParent
0x18000528c  xor     r9d, r9d; NewElement
0x18000528f  mov     r8d, 0B8h; BufferSize
0x180005295  lea     rdx, [rsp+158h+Buffer]; Buffer
0x18000529a  mov     rcx, cs:g_SxsActCtxCache; Table
0x1800052a1  call    cs:__imp_RtlInsertElementGenericTableFullAvl
0x1800052a8  nop     dword ptr [rax+rax+00h]
0x1800052ad  mov     rbx, rax
0x1800052b0  test    rax, rax
0x1800052b3  jz      loc_180005457
0x1800052b9  xor     edx, edx; Val
0x1800052bb  mov     r8d, 0B8h; Size
0x1800052c1  lea     rcx, [rsp+158h+Buffer]; void *
0x1800052c6  call    memset_0
0x1800052cb  mov     rcx, cs:g_SxsActCtxCache; Table
0x1800052d2  lea     rax, [rcx+68h]
0x1800052d6  mov     rdx, [rax]
0x1800052d9  cmp     [rdx+8], rax
0x1800052dd  jnz     loc_180005461
0x1800052e3  mov     [rbx], rdx
0x1800052e6  mov     [rbx+8], rax
0x1800052ea  mov     [rdx+8], rbx
0x1800052ee  mov     [rax], rbx
0x1800052f1  call    cs:__imp_RtlNumberGenericTableElementsAvl
0x1800052f8  nop     dword ptr [rax+rax+00h]
0x1800052fd  cmp     eax, 100h
0x180005302  ja      short loc_180005309
0x180005304  jmp     loc_180005468
0x180005309  mov     r9, cs:g_SxsActCtxCache
0x180005310  lea     rax, [r9+68h]
0x180005314  mov     rdx, [rax+8]; Buffer
0x180005318  cmp     [rdx], rax
0x18000531b  jnz     loc_180005461
0x180005321  mov     rcx, [rdx+8]
0x180005325  cmp     [rcx], rdx
0x180005328  jnz     loc_180005461
0x18000532e  mov     [rax+8], rcx
0x180005332  mov     [rcx], rax
0x180005335  movups  xmm0, xmmword ptr [rdx]
0x180005338  movups  [rsp+158h+Buffer], xmm0
0x18000533d  movups  xmm1, xmmword ptr [rdx+10h]
0x180005341  movups  [rsp+158h+var_E8], xmm1
0x180005346  movups  xmm0, xmmword ptr [rdx+20h]
0x18000534a  movups  [rsp+158h+var_D8], xmm0
0x180005352  movups  xmm1, xmmword ptr [rdx+30h]
0x180005356  movups  [rsp+158h+var_C8], xmm1
0x18000535e  movups  xmm0, xmmword ptr [rdx+40h]
0x180005362  movups  [rsp+158h+var_B8], xmm0
0x18000536a  movups  xmm1, xmmword ptr [rdx+50h]
0x18000536e  movups  [rsp+158h+var_A8], xmm1
0x180005376  movups  xmm0, xmmword ptr [rdx+60h]
0x18000537a  movups  [rsp+158h+var_98], xmm0
0x180005382  movups  xmm1, xmmword ptr [rdx+70h]
0x180005386  movups  xmmword ptr [rsp+158h+TargetHandle], xmm1
0x18000538e  movups  xmm0, xmmword ptr [rdx+80h]
0x180005395  movups  [rsp+158h+var_78], xmm0
0x18000539d  movups  xmm1, xmmword ptr [rdx+90h]
0x1800053a4  movups  [rsp+158h+var_68], xmm1
0x1800053ac  movups  xmm0, xmmword ptr [rdx+0A0h]
0x1800053b3  movups  [rsp+158h+var_58], xmm0
0x1800053bb  mov     rax, [rdx+0B0h]
0x1800053c2  mov     [rsp+158h+var_48], rax
0x1800053ca  mov     rcx, r9; Table
0x1800053cd  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1800053d4  nop     dword ptr [rax+rax+00h]
0x1800053d9  test    al, al
0x1800053db  jnz     loc_180005304
0x1800053e1  lea     r8, aFailToRemoveCa; "Fail to remove cache entry\n"
0x1800053e8  xor     edx, edx; Level
0x1800053ea  mov     ecx, 33h ; '3'; ComponentId
0x1800053ef  call    cs:__imp_DbgPrintEx
0x1800053f6  nop     dword ptr [rax+rax+00h]
0x1800053fb  xor     edx, edx; Val
0x1800053fd  mov     r8d, 0B8h; Size
0x180005403  lea     rcx, [rsp+158h+Buffer]; void *
0x180005408  call    memset_0
0x18000540d  mov     edi, 0C0000229h
0x180005412  jmp     loc_180005304
0x180005417  mov     rax, [rax]
0x18000541a  cmp     [rax+8], rdx
0x18000541e  jnz     short loc_180005461
0x180005420  mov     rcx, [rdx+8]
0x180005424  cmp     [rcx], rdx
0x180005427  jnz     short loc_180005461
0x180005429  mov     [rcx], rax
0x18000542c  mov     [rax+8], rcx
0x180005430  mov     rax, cs:g_SxsActCtxCache
0x180005437  add     rax, 68h ; 'h'
0x18000543b  mov     rcx, [rax]
0x18000543e  cmp     [rcx+8], rax
0x180005442  jnz     short loc_180005461
0x180005444  mov     [rdx], rcx
0x180005447  mov     [rdx+8], rax
0x18000544b  mov     [rcx+8], rdx
0x18000544f  mov     [rax], rdx
0x180005452  jmp     loc_180005304
0x180005457  mov     edi, 0C0000017h
0x18000545c  jmp     loc_180005304
0x180005461  mov     ecx, 3
0x180005466  int     29h; Win8: RtlFailFast(ecx)
0x180005468  lea     rcx, [rsp+158h+Buffer]
0x18000546d  call    BaseSrvActivationContextCacheFreeEntry
0x180005472  lea     rcx, SxsActCtxCacheCS; CriticalSection
0x180005479  call    cs:__imp_RtlLeaveCriticalSection
0x180005480  nop     dword ptr [rax+rax+00h]
0x180005485  mov     eax, edi
0x180005487  mov     rcx, [rsp+158h+var_38]
0x18000548f  xor     rcx, rsp; StackCookie
0x180005492  call    __security_check_cookie
0x180005497  lea     r11, [rsp+158h+var_28]
0x18000549f  mov     rbx, [r11+40h]
0x1800054a3  mov     rsi, [r11+48h]
0x1800054a7  mov     rsp, r11
0x1800054aa  pop     r15
0x1800054ac  pop     r14
0x1800054ae  pop     r13
0x1800054b0  pop     r12
0x1800054b2  pop     rdi
0x1800054b3  retn
0x1800054b5  mov     rdx, r14
0x1800054b8  lea     rcx, [rsp+158h+var_58]
0x1800054c0  call    BaseSrvActivationContextCacheDuplicateUnicodeString
0x1800054c5  mov     ebx, eax
0x1800054c7  test    eax, eax
0x1800054c9  js      loc_180005227
0x1800054cf  movsd   xmm0, qword ptr [rdi]
0x1800054d3  movsd   [rsp+158h+TargetHandle+8], xmm0
0x1800054dc  mov     eax, [rdi+8]
0x1800054df  mov     dword ptr [rsp+158h+var_78], eax
0x1800054e6  mov     eax, [r15]
0x1800054e9  mov     dword ptr [rsp+158h+var_78+4], eax
0x1800054f0  mov     eax, [rsp+158h+arg_38]
0x1800054f7  mov     dword ptr [rsp+158h+var_48+4], eax
0x1800054fe  mov     rax, [rsp+158h+arg_20]
0x180005506  mov     rcx, [rax]
0x180005509  mov     qword ptr [rsp+158h+var_78+8], rcx
0x180005511  xorps   xmm0, xmm0
0x180005514  movups  xmmword ptr [rsp+158h+DestinationString.Length], xmm0
0x180005519  mov     rdx, r12; SourceString
0x18000551c  lea     rcx, [rsp+158h+DestinationString]; DestinationString
0x180005521  call    cs:__imp_RtlInitUnicodeString
0x180005528  nop     dword ptr [rax+rax+00h]
0x18000552d  lea     rdx, [rsp+158h+DestinationString]
0x180005532  lea     rcx, [rsp+158h+var_68]
0x18000553a  call    BaseSrvActivationContextCacheDuplicateUnicodeString
0x18000553f  mov     ebx, eax
0x180005541  jmp     loc_180005227
0x180005546  lea     rcx, [rsp+158h+Buffer]
0x18000554b  call    BaseSrvActivationContextCacheFreeEntry
0x180005550  test    ebx, ebx
0x180005552  jns     loc_18000522F
0x180005558  mov     eax, ebx
0x18000555a  jmp     loc_180005487
0x18000555f  lea     rcx, [rsp+158h+Buffer]
0x180005564  call    BaseSrvActivationContextCacheFreeEntry
0x180005569  jmp     loc_180005485
0x180007000  push    rbp
0x180007002  sub     rsp, 40h
0x180007006  mov     rbp, rdx
0x180007009  lea     rcx, [rbp+60h]
0x18000700d  call    BaseSrvActivationContextCacheFreeEntry
0x180007012  lea     rcx, SxsActCtxCacheCS; CriticalSection
0x180007019  call    cs:__imp_RtlLeaveCriticalSection
0x180007020  nop     dword ptr [rax+rax+00h]
0x180007025  nop
0x180007026  add     rsp, 40h
0x18000702a  pop     rbp
0x18000702b  retn
```
