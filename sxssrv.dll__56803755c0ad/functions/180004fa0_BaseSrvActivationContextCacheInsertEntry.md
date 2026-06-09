# BaseSrvActivationContextCacheInsertEntry

- ea: `0x180004fa0`
- end: `0x18000538d`
- name: `BaseSrvActivationContextCacheInsertEntry`
- size: `1005`
- prototype: `__int64 __fastcall(__int64, void *, __int64, _DWORD *, _QWORD *, const WCHAR *SourceString, const void **, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x180003170`

## callees

- `0x180004fa0`
- `0x1800053a0`
- `0x1800054c0`
- `0x1800055f0`
- `0x180006c13`
- `0x180006c30`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x180005066`
- `ntdll!RtlEnterCriticalSection` at `0x180005066`
- `ntdll!RtlLeaveCriticalSection` at `0x180005298`
- `ntdll!RtlLeaveCriticalSection` at `0x180006f59`
- `ntdll!RtlLeaveCriticalSection` at `0x180005298`
- `ntdll!RtlLeaveCriticalSection` at `0x180006f59`
- `ntdll!DbgPrintEx` at `0x18000520e`
- `ntdll!DbgPrintEx` at `0x18000520e`
- `ntdll!RtlInitUnicodeString` at `0x180005340`
- `ntdll!RtlInitUnicodeString` at `0x180005340`
- `ntdll!RtlLookupElementGenericTableFullAvl` at `0x180005092`
- `ntdll!RtlLookupElementGenericTableFullAvl` at `0x180005092`
- `ntdll!RtlInsertElementGenericTableFullAvl` at `0x1800050d1`
- `ntdll!RtlInsertElementGenericTableFullAvl` at `0x1800050d1`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x180005121`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x180005121`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800051ee`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800051ee`
- `ntdll!NtDuplicateObject` at `0x18000502e`
- `ntdll!NtDuplicateObject` at `0x18000502e`

## string_xrefs

- `0x180005202`: `Fail to remove cache entry\n`

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
  struct _RTL_AVL_TABLE *v20; // r10
  PRTL_AVL_TABLE v21; // rax
  struct _RTL_BALANCED_LINKS *LeftChild; // rdx
  struct _RTL_BALANCED_LINKS *v23; // rcx
  struct _RTL_BALANCED_LINKS *Parent; // rcx
  struct _RTL_BALANCED_LINKS **p_Parent; // rax
  PRTL_AVL_TABLE v26; // rax
  struct _RTL_BALANCED_LINKS *v27; // rcx
  TABLE_SEARCH_RESULT SearchResult; // [rsp+40h] [rbp-118h] BYREF
  PVOID NodeOrParent; // [rsp+48h] [rbp-110h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-108h] BYREF
  __int128 Buffer; // [rsp+60h] [rbp-F8h] BYREF
  _OWORD v33[6]; // [rsp+70h] [rbp-E8h] BYREF
  __int128 TargetHandle; // [rsp+D0h] [rbp-88h] BYREF
  __int128 v35; // [rsp+E0h] [rbp-78h]
  __int128 v36; // [rsp+F0h] [rbp-68h] BYREF
  __int128 v37; // [rsp+100h] [rbp-58h] BYREF
  struct _RTL_BALANCED_LINKS *RightChild; // [rsp+110h] [rbp-48h]

  NodeOrParent = 0;
  SearchResult = TableEmptyTree;
  memset_0(&Buffer, 0, 0xB8u);
  v12 = NtDuplicateObject(
          (HANDLE)0xFFFFFFFFFFFFFFFFLL,
          a2,
          (HANDLE)0xFFFFFFFFFFFFFFFFLL,
          (PHANDLE)&TargetHandle,
          0,
          0,
          2u);
  if ( v12 >= 0 )
  {
    v12 = BaseSrvActivationContextCacheDuplicateKey(v33, a1);
    if ( v12 >= 0 )
    {
      v12 = BaseSrvActivationContextCacheDuplicateUnicodeString((__int64)&v37, a7);
      if ( v12 >= 0 )
      {
        *((_QWORD *)&TargetHandle + 1) = *(_QWORD *)a3;
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
      p_Parent = &v14->LeftChild->Parent;
      if ( Parent->LeftChild != v15 )
        goto LABEL_19;
      if ( *p_Parent != v15 )
        goto LABEL_19;
      *p_Parent = Parent;
      Parent->LeftChild = (struct _RTL_BALANCED_LINKS *)p_Parent;
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
          LeftChild = g_SxsActCtxCache[1].BalancedRoot.LeftChild;
          v23 = LeftChild->LeftChild;
          if ( (PRTL_AVL_TABLE)LeftChild->Parent == &g_SxsActCtxCache[1] && v23->Parent == LeftChild )
          {
            g_SxsActCtxCache[1].BalancedRoot.LeftChild = v23;
            v23->Parent = &v21->BalancedRoot;
            Buffer = *(_OWORD *)&LeftChild->Parent;
            v33[0] = *(_OWORD *)&LeftChild->RightChild;
            v33[1] = *(_OWORD *)&LeftChild[1].Parent;
            v33[2] = *(_OWORD *)&LeftChild[1].RightChild;
            v33[3] = *(_OWORD *)&LeftChild[2].Parent;
            v33[4] = *(_OWORD *)&LeftChild[2].RightChild;
            v33[5] = *(_OWORD *)&LeftChild[3].Parent;
            TargetHandle = *(_OWORD *)&LeftChild[3].RightChild;
            v35 = *(_OWORD *)&LeftChild[4].Parent;
            v36 = *(_OWORD *)&LeftChild[4].RightChild;
            v37 = *(_OWORD *)&LeftChild[5].Parent;
            RightChild = LeftChild[5].RightChild;
            if ( !RtlDeleteElementGenericTableAvl(v20, LeftChild) )
            {
              DbgPrintEx(0x33u, 0, "Fail to remove cache entry\n");
              memset_0(&Buffer, 0, 0xB8u);
              v13 = -1073741271;
            }
            goto LABEL_20;
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
0x180004fa0  mov     [rsp+arg_10], rbx
0x180004fa5  mov     [rsp+arg_18], rsi
0x180004faa  push    rdi
0x180004fab  push    r12
0x180004fad  push    r13
0x180004faf  push    r14
0x180004fb1  push    r15
0x180004fb3  sub     rsp, 130h
0x180004fba  mov     rax, cs:__security_cookie
0x180004fc1  xor     rax, rsp
0x180004fc4  mov     [rsp+158h+var_38], rax
0x180004fcc  mov     r15, r9
0x180004fcf  mov     rdi, r8
0x180004fd2  mov     rbx, rdx
0x180004fd5  mov     rsi, rcx
0x180004fd8  mov     r12, [rsp+158h+SourceString]
0x180004fe0  mov     r14, [rsp+158h+arg_30]
0x180004fe8  xor     r13d, r13d
0x180004feb  mov     [rsp+158h+NodeOrParent], r13
0x180004ff0  mov     [rsp+158h+SearchResult], r13d
0x180004ff5  xor     edx, edx; Val
0x180004ff7  mov     r8d, 0B8h; Size
0x180004ffd  lea     rcx, [rsp+158h+Buffer]; void *
0x180005002  call    memset_0
0x180005007  mov     [rsp+158h+Options], 2; Options
0x18000500f  mov     [rsp+158h+HandleAttributes], r13d; HandleAttributes
0x180005014  mov     [rsp+158h+DesiredAccess], r13d; DesiredAccess
0x180005019  lea     r9, [rsp+158h+TargetHandle]; TargetHandle
0x180005021  mov     r8, 0FFFFFFFFFFFFFFFFh; TargetProcessHandle
0x180005028  mov     rdx, rbx; SourceHandle
0x18000502b  mov     rcx, r8; SourceProcessHandle
0x18000502e  call    cs:__imp_NtDuplicateObject
0x180005035  nop     dword ptr [rax+rax+00h]
0x18000503a  mov     ebx, eax
0x18000503c  test    eax, eax
0x18000503e  js      short loc_180005057
0x180005040  mov     rdx, rsi
0x180005043  lea     rcx, [rsp+158h+var_E8]
0x180005048  call    BaseSrvActivationContextCacheDuplicateKey
0x18000504d  mov     ebx, eax
0x18000504f  test    eax, eax
0x180005051  jns     loc_1800052D4
0x180005057  test    ebx, ebx
0x180005059  js      loc_180005365
0x18000505f  lea     rcx, SxsActCtxCacheCS; CriticalSection
0x180005066  call    cs:__imp_RtlEnterCriticalSection
0x18000506d  nop     dword ptr [rax+rax+00h]
0x180005072  mov     edi, eax
0x180005074  test    eax, eax
0x180005076  js      loc_18000537E
0x18000507c  lea     r9, [rsp+158h+SearchResult]; SearchResult
0x180005081  lea     r8, [rsp+158h+NodeOrParent]; NodeOrParent
0x180005086  lea     rdx, [rsp+158h+Buffer]; Buffer
0x18000508b  mov     rcx, cs:g_SxsActCtxCache; Table
0x180005092  call    cs:__imp_RtlLookupElementGenericTableFullAvl
0x180005099  nop     dword ptr [rax+rax+00h]
0x18000509e  mov     rdx, rax
0x1800050a1  mov     ecx, [rsp+158h+SearchResult]
0x1800050a5  cmp     ecx, 1
0x1800050a8  jz      loc_180005236
0x1800050ae  mov     [rsp+158h+HandleAttributes], ecx; SearchResult
0x1800050b2  mov     rax, [rsp+158h+NodeOrParent]
0x1800050b7  mov     qword ptr [rsp+158h+DesiredAccess], rax; NodeOrParent
0x1800050bc  xor     r9d, r9d; NewElement
0x1800050bf  mov     r8d, 0B8h; BufferSize
0x1800050c5  lea     rdx, [rsp+158h+Buffer]; Buffer
0x1800050ca  mov     rcx, cs:g_SxsActCtxCache; Table
0x1800050d1  call    cs:__imp_RtlInsertElementGenericTableFullAvl
0x1800050d8  nop     dword ptr [rax+rax+00h]
0x1800050dd  mov     rbx, rax
0x1800050e0  test    rax, rax
0x1800050e3  jz      loc_180005276
0x1800050e9  xor     edx, edx; Val
0x1800050eb  mov     r8d, 0B8h; Size
0x1800050f1  lea     rcx, [rsp+158h+Buffer]; void *
0x1800050f6  call    memset_0
0x1800050fb  mov     rcx, cs:g_SxsActCtxCache; Table
0x180005102  lea     rax, [rcx+68h]
0x180005106  mov     rdx, [rax]
0x180005109  cmp     [rdx+8], rax
0x18000510d  jnz     loc_180005280
0x180005113  mov     [rbx], rdx
0x180005116  mov     [rbx+8], rax
0x18000511a  mov     [rdx+8], rbx
0x18000511e  mov     [rax], rbx
0x180005121  call    cs:__imp_RtlNumberGenericTableElementsAvl
0x180005128  nop     dword ptr [rax+rax+00h]
0x18000512d  cmp     eax, 100h
0x180005132  ja      short loc_180005139
0x180005134  jmp     loc_180005287
0x180005139  mov     r10, cs:g_SxsActCtxCache
0x180005140  lea     rax, [r10+68h]
0x180005144  mov     rdx, [rax+8]; Buffer
0x180005148  mov     rcx, [rdx+8]
0x18000514c  cmp     [rdx], rax
0x18000514f  jnz     loc_180005280
0x180005155  cmp     [rcx], rdx
0x180005158  jnz     loc_180005280
0x18000515e  mov     [rax+8], rcx
0x180005162  mov     [rcx], rax
0x180005165  lea     r9, [rsp+158h+Buffer]
0x18000516a  movups  xmm0, xmmword ptr [rdx]
0x18000516d  movups  xmmword ptr [r9], xmm0
0x180005171  movups  xmm1, xmmword ptr [rdx+10h]
0x180005175  movups  xmmword ptr [r9+10h], xmm1
0x18000517a  movups  xmm0, xmmword ptr [rdx+20h]
0x18000517e  movups  xmmword ptr [r9+20h], xmm0
0x180005183  movups  xmm1, xmmword ptr [rdx+30h]
0x180005187  movups  xmmword ptr [r9+30h], xmm1
0x18000518c  movups  xmm0, xmmword ptr [rdx+40h]
0x180005190  movups  xmmword ptr [r9+40h], xmm0
0x180005195  movups  xmm1, xmmword ptr [rdx+50h]
0x180005199  movups  xmmword ptr [r9+50h], xmm1
0x18000519e  movups  xmm0, xmmword ptr [rdx+60h]
0x1800051a2  movups  xmmword ptr [r9+60h], xmm0
0x1800051a7  movups  xmm0, xmmword ptr [rdx+70h]
0x1800051ab  movups  xmmword ptr [r9+70h], xmm0
0x1800051b0  movups  xmm1, xmmword ptr [rdx+80h]
0x1800051b7  movups  xmmword ptr [r9+80h], xmm1
0x1800051bf  movups  xmm0, xmmword ptr [rdx+90h]
0x1800051c6  movups  xmmword ptr [r9+90h], xmm0
0x1800051ce  movups  xmm1, xmmword ptr [rdx+0A0h]
0x1800051d5  movups  xmmword ptr [r9+0A0h], xmm1
0x1800051dd  mov     rax, [rdx+0B0h]
0x1800051e4  mov     [r9+0B0h], rax
0x1800051eb  mov     rcx, r10; Table
0x1800051ee  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1800051f5  nop     dword ptr [rax+rax+00h]
0x1800051fa  test    al, al
0x1800051fc  jnz     loc_180005134
0x180005202  lea     r8, aFailToRemoveCa; "Fail to remove cache entry\n"
0x180005209  xor     edx, edx; Level
0x18000520b  lea     ecx, [rdx+33h]; ComponentId
0x18000520e  call    cs:__imp_DbgPrintEx
0x180005215  nop     dword ptr [rax+rax+00h]
0x18000521a  xor     edx, edx; Val
0x18000521c  mov     r8d, 0B8h; Size
0x180005222  lea     rcx, [rsp+158h+Buffer]; void *
0x180005227  call    memset_0
0x18000522c  mov     edi, 0C0000229h
0x180005231  jmp     loc_180005134
0x180005236  mov     rcx, [rax]
0x180005239  mov     rax, [rax+8]
0x18000523d  cmp     [rcx+8], rdx
0x180005241  jnz     short loc_180005280
0x180005243  cmp     [rax], rdx
0x180005246  jnz     short loc_180005280
0x180005248  mov     [rax], rcx
0x18000524b  mov     [rcx+8], rax
0x18000524f  mov     rax, cs:g_SxsActCtxCache
0x180005256  add     rax, 68h ; 'h'
0x18000525a  mov     rcx, [rax]
0x18000525d  cmp     [rcx+8], rax
0x180005261  jnz     short loc_180005280
0x180005263  mov     [rdx], rcx
0x180005266  mov     [rdx+8], rax
0x18000526a  mov     [rcx+8], rdx
0x18000526e  mov     [rax], rdx
0x180005271  jmp     loc_180005134
0x180005276  mov     edi, 0C0000017h
0x18000527b  jmp     loc_180005134
0x180005280  mov     ecx, 3
0x180005285  int     29h; Win8: RtlFailFast(ecx)
0x180005287  lea     rcx, [rsp+158h+Buffer]
0x18000528c  call    BaseSrvActivationContextCacheFreeEntry
0x180005291  lea     rcx, SxsActCtxCacheCS; CriticalSection
0x180005298  call    cs:__imp_RtlLeaveCriticalSection
0x18000529f  nop     dword ptr [rax+rax+00h]
0x1800052a4  mov     eax, edi
0x1800052a6  mov     rcx, [rsp+158h+var_38]
0x1800052ae  xor     rcx, rsp; StackCookie
0x1800052b1  call    __security_check_cookie
0x1800052b6  lea     r11, [rsp+158h+var_28]
0x1800052be  mov     rbx, [r11+40h]
0x1800052c2  mov     rsi, [r11+48h]
0x1800052c6  mov     rsp, r11
0x1800052c9  pop     r15
0x1800052cb  pop     r14
0x1800052cd  pop     r13
0x1800052cf  pop     r12
0x1800052d1  pop     rdi
0x1800052d2  retn
0x1800052d4  mov     rdx, r14
0x1800052d7  lea     rcx, [rsp+158h+var_58]
0x1800052df  call    BaseSrvActivationContextCacheDuplicateUnicodeString
0x1800052e4  mov     ebx, eax
0x1800052e6  test    eax, eax
0x1800052e8  js      loc_180005057
0x1800052ee  movsd   xmm0, qword ptr [rdi]
0x1800052f2  movsd   [rsp+158h+var_80], xmm0
0x1800052fb  mov     eax, [rdi+8]
0x1800052fe  mov     [rsp+158h+var_78], eax
0x180005305  mov     eax, [r15]
0x180005308  mov     [rsp+158h+var_74], eax
0x18000530f  mov     eax, [rsp+158h+arg_38]
0x180005316  mov     [rsp+158h+var_44], eax
0x18000531d  mov     rax, [rsp+158h+arg_20]
0x180005325  mov     rcx, [rax]
0x180005328  mov     [rsp+158h+var_70], rcx
0x180005330  xorps   xmm0, xmm0
0x180005333  movups  xmmword ptr [rsp+158h+DestinationString.Length], xmm0
0x180005338  mov     rdx, r12; SourceString
0x18000533b  lea     rcx, [rsp+158h+DestinationString]; DestinationString
0x180005340  call    cs:__imp_RtlInitUnicodeString
0x180005347  nop     dword ptr [rax+rax+00h]
0x18000534c  lea     rdx, [rsp+158h+DestinationString]
0x180005351  lea     rcx, [rsp+158h+var_68]
0x180005359  call    BaseSrvActivationContextCacheDuplicateUnicodeString
0x18000535e  mov     ebx, eax
0x180005360  jmp     loc_180005057
0x180005365  lea     rcx, [rsp+158h+Buffer]
0x18000536a  call    BaseSrvActivationContextCacheFreeEntry
0x18000536f  test    ebx, ebx
0x180005371  jns     loc_18000505F
0x180005377  mov     eax, ebx
0x180005379  jmp     loc_1800052A6
0x18000537e  lea     rcx, [rsp+158h+Buffer]
0x180005383  call    BaseSrvActivationContextCacheFreeEntry
0x180005388  jmp     loc_1800052A4
0x180006f40  push    rbp
0x180006f42  sub     rsp, 40h
0x180006f46  mov     rbp, rdx
0x180006f49  lea     rcx, [rbp+60h]
0x180006f4d  call    BaseSrvActivationContextCacheFreeEntry
0x180006f52  lea     rcx, SxsActCtxCacheCS; CriticalSection
0x180006f59  call    cs:__imp_RtlLeaveCriticalSection
0x180006f60  nop     dword ptr [rax+rax+00h]
0x180006f65  nop
0x180006f66  add     rsp, 40h
0x180006f6a  pop     rbp
0x180006f6b  retn
```
