# BaseSrvActivationContextCacheLookupEntry

- ea: `0x1800041d0`
- end: `0x18000449c`
- name: `BaseSrvActivationContextCacheLookupEntry`
- size: `716`
- prototype: `NTSTATUS __fastcall(__int128 *, void **, __int64, _DWORD *, struct _RTL_BALANCED_LINKS **, _WORD *, _OWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180003170`

## callees

- `0x1800041d0`
- `0x180006c13`
- `0x180006c30`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x180004289`
- `ntdll!RtlEnterCriticalSection` at `0x180004289`
- `ntdll!RtlLeaveCriticalSection` at `0x18000446a`
- `ntdll!RtlLeaveCriticalSection` at `0x180006ef0`
- `ntdll!RtlLeaveCriticalSection` at `0x18000446a`
- `ntdll!RtlLeaveCriticalSection` at `0x180006ef0`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x1800042ac`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x1800042ac`
- `ntdll!NtDuplicateObject` at `0x1800042e7`
- `ntdll!NtDuplicateObject` at `0x1800042e7`

## pseudocode

```c
NTSTATUS __fastcall BaseSrvActivationContextCacheLookupEntry(
        __int128 *a1,
        void **a2,
        __int64 a3,
        _DWORD *a4,
        struct _RTL_BALANCED_LINKS **a5,
        _WORD *a6,
        _OWORD *a7,
        _DWORD *a8)
{
  _WORD *v12; // r14
  NTSTATUS result; // eax
  struct _RTL_BALANCED_LINKS *v14; // rbx
  NTSTATUS v15; // edi
  struct _RTL_BALANCED_LINKS *Parent; // rcx
  PVOID *p_Parent; // rax
  PRTL_AVL_TABLE v18; // rax
  struct _RTL_BALANCED_LINKS *v19; // rcx
  _WORD *v20; // rax
  __int64 v21; // r8
  __int64 v22; // rcx
  __int64 v23; // r9
  _BYTE Buffer[16]; // [rsp+80h] [rbp-108h] BYREF
  __int128 v25; // [rsp+90h] [rbp-F8h]
  __int128 v26; // [rsp+A0h] [rbp-E8h]
  __int128 v27; // [rsp+B0h] [rbp-D8h]
  __int128 v28; // [rsp+C0h] [rbp-C8h]
  __int128 v29; // [rsp+D0h] [rbp-B8h]
  __int128 v30; // [rsp+E0h] [rbp-A8h]

  v12 = a6;
  memset_0(Buffer, 0, 0xB8u);
  v25 = *a1;
  v26 = a1[1];
  v27 = a1[2];
  v28 = a1[3];
  v29 = a1[4];
  v30 = a1[5];
  result = RtlEnterCriticalSection(&SxsActCtxCacheCS);
  if ( result >= 0 )
  {
    v14 = (struct _RTL_BALANCED_LINKS *)RtlLookupElementGenericTableAvl(g_SxsActCtxCache, Buffer);
    if ( v14 )
    {
      v15 = NtDuplicateObject(
              (HANDLE)0xFFFFFFFFFFFFFFFFLL,
              v14[3].RightChild,
              (HANDLE)0xFFFFFFFFFFFFFFFFLL,
              a2,
              0,
              0,
              2u);
      if ( v15 >= 0 )
      {
        Parent = v14->Parent;
        p_Parent = (PVOID *)&v14->LeftChild->Parent;
        if ( v14->Parent->LeftChild != v14
          || *p_Parent != v14
          || (*p_Parent = Parent,
              Parent->LeftChild = (struct _RTL_BALANCED_LINKS *)p_Parent,
              v18 = g_SxsActCtxCache + 1,
              v19 = g_SxsActCtxCache[1].BalancedRoot.Parent,
              (PRTL_AVL_TABLE)v19->LeftChild != &g_SxsActCtxCache[1]) )
        {
          __fastfail(3u);
        }
        v14->Parent = v19;
        v14->LeftChild = &v18->BalancedRoot;
        v19->LeftChild = v14;
        v18->BalancedRoot.Parent = v14;
        ++LODWORD(v14[5].RightChild);
      }
      *(_QWORD *)a3 = *(_QWORD *)&v14[3].Balance;
      *(_DWORD *)(a3 + 8) = v14[4].Parent;
      *a4 = HIDWORD(v14[4].Parent);
      *a5 = v14[4].LeftChild;
      *a7 = *(_OWORD *)&v14[5].Parent;
      *a8 = HIDWORD(v14[5].RightChild);
      memset_0(a6, 0, 0x104u);
      v20 = *(_WORD **)&v14[4].Balance;
      if ( v20 )
      {
        v21 = 2147483646;
        v22 = 130;
        v23 = 0;
        while ( v22 )
        {
          if ( !v21 || !*v20 )
            goto LABEL_16;
          *v12++ = *v20++;
          --v22;
          --v21;
          ++v23;
        }
        --v12;
LABEL_16:
        *v12 = 0;
      }
    }
    else
    {
      v15 = -1073741275;
    }
    RtlLeaveCriticalSection(&SxsActCtxCacheCS);
    return v15;
  }
  return result;
}

```

## disassembly

```asm
0x1800041d0  push    rbx
0x1800041d2  push    rsi
0x1800041d3  push    rdi
0x1800041d4  push    r12
0x1800041d6  push    r13
0x1800041d8  push    r14
0x1800041da  push    r15
0x1800041dc  sub     rsp, 150h
0x1800041e3  mov     rax, cs:__security_cookie
0x1800041ea  xor     rax, rsp
0x1800041ed  mov     [rsp+188h+var_48], rax
0x1800041f5  mov     r15, r9
0x1800041f8  mov     rsi, r8
0x1800041fb  mov     rdi, rdx
0x1800041fe  mov     rbx, rcx
0x180004201  mov     r12, [rsp+188h+arg_20]
0x180004209  mov     r14, [rsp+188h+arg_28]
0x180004211  mov     r13, [rsp+188h+arg_30]
0x180004219  mov     rax, [rsp+188h+arg_38]
0x180004221  mov     [rsp+188h+var_130], rax
0x180004226  xor     edx, edx; Val
0x180004228  mov     r8d, 0B8h; Size
0x18000422e  lea     rcx, [rsp+188h+Buffer]; void *
0x180004236  call    memset_0
0x18000423b  movaps  xmm0, xmmword ptr [rbx]
0x18000423e  movaps  [rsp+188h+var_F8], xmm0
0x180004246  movaps  xmm1, xmmword ptr [rbx+10h]
0x18000424a  movaps  [rsp+188h+var_E8], xmm1
0x180004252  movaps  xmm0, xmmword ptr [rbx+20h]
0x180004256  movaps  [rsp+188h+var_D8], xmm0
0x18000425e  movaps  xmm1, xmmword ptr [rbx+30h]
0x180004262  movaps  [rsp+188h+var_C8], xmm1
0x18000426a  movaps  xmm0, xmmword ptr [rbx+40h]
0x18000426e  movaps  [rsp+188h+var_B8], xmm0
0x180004276  movaps  xmm1, xmmword ptr [rbx+50h]
0x18000427a  movaps  [rsp+188h+var_A8], xmm1
0x180004282  lea     rcx, SxsActCtxCacheCS; CriticalSection
0x180004289  call    cs:__imp_RtlEnterCriticalSection
0x180004290  nop     dword ptr [rax+rax+00h]
0x180004295  test    eax, eax
0x180004297  js      loc_180004478
0x18000429d  lea     rdx, [rsp+188h+Buffer]; Buffer
0x1800042a5  mov     rcx, cs:g_SxsActCtxCache; Table
0x1800042ac  call    cs:__imp_RtlLookupElementGenericTableAvl
0x1800042b3  nop     dword ptr [rax+rax+00h]
0x1800042b8  mov     rbx, rax
0x1800042bb  test    rax, rax
0x1800042be  jz      loc_180004451
0x1800042c4  mov     [rsp+188h+Options], 2; Options
0x1800042cc  xor     eax, eax
0x1800042ce  mov     [rsp+188h+HandleAttributes], eax; HandleAttributes
0x1800042d2  mov     [rsp+188h+DesiredAccess], eax; DesiredAccess
0x1800042d6  mov     r9, rdi; TargetHandle
0x1800042d9  mov     r8, 0FFFFFFFFFFFFFFFFh; TargetProcessHandle
0x1800042e0  mov     rdx, [rbx+70h]; SourceHandle
0x1800042e4  mov     rcx, r8; SourceProcessHandle
0x1800042e7  call    cs:__imp_NtDuplicateObject
0x1800042ee  nop     dword ptr [rax+rax+00h]
0x1800042f3  mov     edi, eax
0x1800042f5  mov     [rsp+188h+var_144], eax
0x1800042f9  test    eax, eax
0x1800042fb  js      short loc_180004352
0x1800042fd  mov     rcx, [rbx]
0x180004300  mov     rax, [rbx+8]
0x180004304  cmp     [rcx+8], rbx
0x180004308  jnz     loc_18000445C
0x18000430e  cmp     [rax], rbx
0x180004311  jnz     loc_18000445C
0x180004317  mov     [rax], rcx
0x18000431a  mov     [rcx+8], rax
0x18000431e  mov     rax, cs:g_SxsActCtxCache
0x180004325  add     rax, 68h ; 'h'
0x180004329  mov     rcx, [rax]
0x18000432c  cmp     [rcx+8], rax
0x180004330  jnz     loc_18000445C
0x180004336  mov     [rbx], rcx
0x180004339  mov     [rbx+8], rax
0x18000433d  mov     [rcx+8], rbx
0x180004341  mov     [rax], rbx
0x180004344  mov     eax, [rbx+0B0h]
0x18000434a  inc     eax
0x18000434c  mov     [rbx+0B0h], eax
0x180004352  movsd   xmm0, qword ptr [rbx+78h]
0x180004357  movsd   qword ptr [rsi], xmm0
0x18000435b  mov     eax, [rbx+80h]
0x180004361  mov     [rsi+8], eax
0x180004364  mov     eax, [rbx+84h]
0x18000436a  mov     [r15], eax
0x18000436d  mov     rax, [rbx+88h]
0x180004374  mov     [r12], rax
0x180004378  movups  xmm0, xmmword ptr [rbx+0A0h]
0x18000437f  movups  xmmword ptr [r13+0], xmm0
0x180004384  mov     eax, [rbx+0B4h]
0x18000438a  mov     rcx, [rsp+188h+var_130]
0x18000438f  mov     [rcx], eax
0x180004391  xor     edx, edx; Val
0x180004393  mov     r8d, 104h; Size
0x180004399  mov     rcx, r14; void *
0x18000439c  call    memset_0
0x1800043a1  mov     rax, [rbx+98h]
0x1800043a8  test    rax, rax
0x1800043ab  jz      loc_180004463
0x1800043b1  xor     r11d, r11d
0x1800043b4  mov     [rsp+188h+var_148], r11d
0x1800043b9  mov     [rsp+188h+var_148], r11d
0x1800043be  mov     r8d, 7FFFFFFEh
0x1800043c4  mov     [rsp+188h+var_118], r8
0x1800043c9  mov     [rsp+188h+var_128], rax
0x1800043ce  mov     ecx, 82h
0x1800043d3  mov     [rsp+188h+var_120], rcx
0x1800043d8  mov     [rsp+188h+var_140], r14
0x1800043dd  mov     r10d, r11d
0x1800043e0  mov     r9d, r11d
0x1800043e3  mov     [rsp+188h+var_138], r11
0x1800043e8  test    rcx, rcx
0x1800043eb  jz      short loc_18000442F
0x1800043ed  test    r8, r8
0x1800043f0  jz      short loc_18000442A
0x1800043f2  movzx   edx, word ptr [rax]
0x1800043f5  test    dx, dx
0x1800043f8  jz      short loc_18000442A
0x1800043fa  mov     [r14], dx
0x1800043fe  add     r14, 2
0x180004402  mov     [rsp+188h+var_140], r14
0x180004407  add     rax, 2
0x18000440b  mov     [rsp+188h+var_128], rax
0x180004410  dec     rcx
0x180004413  mov     [rsp+188h+var_120], rcx
0x180004418  dec     r8
0x18000441b  mov     [rsp+188h+var_118], r8
0x180004420  inc     r9
0x180004423  mov     [rsp+188h+var_138], r9
0x180004428  jmp     short loc_1800043E8
0x18000442a  test    rcx, rcx
0x18000442d  jnz     short loc_180004446
0x18000442f  sub     r14, 2
0x180004433  mov     [rsp+188h+var_140], r14
0x180004438  dec     r9
0x18000443b  mov     [rsp+188h+var_138], r9
0x180004440  mov     r10d, 8007007Ah
0x180004446  mov     [r14], r11w
0x18000444a  mov     [rsp+188h+var_148], r10d
0x18000444f  jmp     short loc_180004463
0x180004451  mov     edi, 0C0000225h
0x180004456  mov     [rsp+188h+var_144], edi
0x18000445a  jmp     short loc_180004463
0x18000445c  mov     ecx, 3
0x180004461  int     29h; Win8: RtlFailFast(ecx)
0x180004463  lea     rcx, SxsActCtxCacheCS; CriticalSection
0x18000446a  call    cs:__imp_RtlLeaveCriticalSection
0x180004471  nop     dword ptr [rax+rax+00h]
0x180004476  mov     eax, edi
0x180004478  mov     rcx, [rsp+188h+var_48]
0x180004480  xor     rcx, rsp; StackCookie
0x180004483  call    __security_check_cookie
0x180004488  add     rsp, 150h
0x18000448f  pop     r15
0x180004491  pop     r14
0x180004493  pop     r13
0x180004495  pop     r12
0x180004497  pop     rdi
0x180004498  pop     rsi
0x180004499  pop     rbx
0x18000449a  retn
0x180006ee0  push    rbp
0x180006ee2  sub     rsp, 40h
0x180006ee6  mov     rbp, rdx
0x180006ee9  lea     rcx, SxsActCtxCacheCS; CriticalSection
0x180006ef0  call    cs:__imp_RtlLeaveCriticalSection
0x180006ef7  nop     dword ptr [rax+rax+00h]
0x180006efc  nop
0x180006efd  add     rsp, 40h
0x180006f01  pop     rbp
0x180006f02  retn
```
