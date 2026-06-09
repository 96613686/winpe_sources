# BaseSrvActivationContextCacheLookupEntry

- ea: `0x180004390`
- end: `0x180004659`
- name: `BaseSrvActivationContextCacheLookupEntry`
- size: `713`
- prototype: `NTSTATUS __fastcall(__int128 *, void **, __int64, _DWORD *, struct _RTL_BALANCED_LINKS **, _WORD *, _OWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180003310`

## callees

- `0x180004390`
- `0x180006ccd`
- `0x180006cf0`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x180004449`
- `ntdll!RtlEnterCriticalSection` at `0x180004449`
- `ntdll!RtlLeaveCriticalSection` at `0x180004627`
- `ntdll!RtlLeaveCriticalSection` at `0x180006fb0`
- `ntdll!RtlLeaveCriticalSection` at `0x180004627`
- `ntdll!RtlLeaveCriticalSection` at `0x180006fb0`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18000446c`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18000446c`
- `ntdll!NtDuplicateObject` at `0x1800044a7`
- `ntdll!NtDuplicateObject` at `0x1800044a7`

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
  struct _RTL_BALANCED_LINKS *Parent; // rax
  PVOID *p_Parent; // rcx
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
        if ( v14->Parent->LeftChild != v14
          || (p_Parent = (PVOID *)&v14->LeftChild->Parent, *p_Parent != v14)
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
0x180004390  push    rbx
0x180004392  push    rsi
0x180004393  push    rdi
0x180004394  push    r12
0x180004396  push    r13
0x180004398  push    r14
0x18000439a  push    r15
0x18000439c  sub     rsp, 150h
0x1800043a3  mov     rax, cs:__security_cookie
0x1800043aa  xor     rax, rsp
0x1800043ad  mov     [rsp+188h+var_48], rax
0x1800043b5  mov     r15, r9
0x1800043b8  mov     rsi, r8
0x1800043bb  mov     rdi, rdx
0x1800043be  mov     rbx, rcx
0x1800043c1  mov     r12, [rsp+188h+arg_20]
0x1800043c9  mov     r14, [rsp+188h+arg_28]
0x1800043d1  mov     r13, [rsp+188h+arg_30]
0x1800043d9  mov     rax, [rsp+188h+arg_38]
0x1800043e1  mov     [rsp+188h+var_130], rax
0x1800043e6  xor     edx, edx; Val
0x1800043e8  mov     r8d, 0B8h; Size
0x1800043ee  lea     rcx, [rsp+188h+Buffer]; void *
0x1800043f6  call    memset_0
0x1800043fb  movaps  xmm0, xmmword ptr [rbx]
0x1800043fe  movaps  [rsp+188h+var_F8], xmm0
0x180004406  movaps  xmm1, xmmword ptr [rbx+10h]
0x18000440a  movaps  [rsp+188h+var_E8], xmm1
0x180004412  movaps  xmm0, xmmword ptr [rbx+20h]
0x180004416  movaps  [rsp+188h+var_D8], xmm0
0x18000441e  movaps  xmm1, xmmword ptr [rbx+30h]
0x180004422  movaps  [rsp+188h+var_C8], xmm1
0x18000442a  movaps  xmm0, xmmword ptr [rbx+40h]
0x18000442e  movaps  [rsp+188h+var_B8], xmm0
0x180004436  movaps  xmm1, xmmword ptr [rbx+50h]
0x18000443a  movaps  [rsp+188h+var_A8], xmm1
0x180004442  lea     rcx, SxsActCtxCacheCS; CriticalSection
0x180004449  call    cs:__imp_RtlEnterCriticalSection
0x180004450  nop     dword ptr [rax+rax+00h]
0x180004455  test    eax, eax
0x180004457  js      loc_180004635
0x18000445d  lea     rdx, [rsp+188h+Buffer]; Buffer
0x180004465  mov     rcx, cs:g_SxsActCtxCache; Table
0x18000446c  call    cs:__imp_RtlLookupElementGenericTableAvl
0x180004473  nop     dword ptr [rax+rax+00h]
0x180004478  mov     rbx, rax
0x18000447b  test    rax, rax
0x18000447e  jz      loc_18000460E
0x180004484  mov     [rsp+188h+Options], 2; Options
0x18000448c  xor     eax, eax
0x18000448e  mov     [rsp+188h+HandleAttributes], eax; HandleAttributes
0x180004492  mov     [rsp+188h+DesiredAccess], eax; DesiredAccess
0x180004496  mov     r9, rdi; TargetHandle
0x180004499  mov     r8, 0FFFFFFFFFFFFFFFFh; TargetProcessHandle
0x1800044a0  mov     rdx, [rbx+70h]; SourceHandle
0x1800044a4  mov     rcx, r8; SourceProcessHandle
0x1800044a7  call    cs:__imp_NtDuplicateObject
0x1800044ae  nop     dword ptr [rax+rax+00h]
0x1800044b3  mov     edi, eax
0x1800044b5  mov     [rsp+188h+var_144], eax
0x1800044b9  test    eax, eax
0x1800044bb  js      short loc_18000450A
0x1800044bd  mov     rax, [rbx]
0x1800044c0  cmp     [rax+8], rbx
0x1800044c4  jnz     loc_180004619
0x1800044ca  mov     rcx, [rbx+8]
0x1800044ce  cmp     [rcx], rbx
0x1800044d1  jnz     loc_180004619
0x1800044d7  mov     [rcx], rax
0x1800044da  mov     [rax+8], rcx
0x1800044de  mov     rax, cs:g_SxsActCtxCache
0x1800044e5  add     rax, 68h ; 'h'
0x1800044e9  mov     rcx, [rax]
0x1800044ec  cmp     [rcx+8], rax
0x1800044f0  jnz     loc_180004619
0x1800044f6  mov     [rbx], rcx
0x1800044f9  mov     [rbx+8], rax
0x1800044fd  mov     [rcx+8], rbx
0x180004501  mov     [rax], rbx
0x180004504  inc     dword ptr [rbx+0B0h]
0x18000450a  movsd   xmm0, qword ptr [rbx+78h]
0x18000450f  movsd   qword ptr [rsi], xmm0
0x180004513  mov     eax, [rbx+80h]
0x180004519  mov     [rsi+8], eax
0x18000451c  mov     eax, [rbx+84h]
0x180004522  mov     [r15], eax
0x180004525  mov     rax, [rbx+88h]
0x18000452c  mov     [r12], rax
0x180004530  movups  xmm0, xmmword ptr [rbx+0A0h]
0x180004537  movups  xmmword ptr [r13+0], xmm0
0x18000453c  mov     eax, [rbx+0B4h]
0x180004542  mov     rcx, [rsp+188h+var_130]
0x180004547  mov     [rcx], eax
0x180004549  xor     edx, edx; Val
0x18000454b  mov     r8d, 104h; Size
0x180004551  mov     rcx, r14; void *
0x180004554  call    memset_0
0x180004559  mov     rax, [rbx+98h]
0x180004560  test    rax, rax
0x180004563  jz      loc_180004620
0x180004569  mov     [rsp+188h+var_148], 0
0x180004571  mov     [rsp+188h+var_148], 0
0x180004579  mov     r8d, 7FFFFFFEh
0x18000457f  mov     [rsp+188h+var_118], r8
0x180004584  mov     [rsp+188h+var_128], rax
0x180004589  mov     ecx, 82h
0x18000458e  mov     [rsp+188h+var_120], rcx
0x180004593  mov     [rsp+188h+var_140], r14
0x180004598  xor     r10d, r10d
0x18000459b  xor     r9d, r9d
0x18000459e  mov     [rsp+188h+var_138], r9
0x1800045a3  test    rcx, rcx
0x1800045a6  jz      short loc_1800045EA
0x1800045a8  test    r8, r8
0x1800045ab  jz      short loc_1800045E5
0x1800045ad  movzx   edx, word ptr [rax]
0x1800045b0  test    dx, dx
0x1800045b3  jz      short loc_1800045E5
0x1800045b5  mov     [r14], dx
0x1800045b9  add     r14, 2
0x1800045bd  mov     [rsp+188h+var_140], r14
0x1800045c2  add     rax, 2
0x1800045c6  mov     [rsp+188h+var_128], rax
0x1800045cb  dec     rcx
0x1800045ce  mov     [rsp+188h+var_120], rcx
0x1800045d3  dec     r8
0x1800045d6  mov     [rsp+188h+var_118], r8
0x1800045db  inc     r9
0x1800045de  mov     [rsp+188h+var_138], r9
0x1800045e3  jmp     short loc_1800045A3
0x1800045e5  test    rcx, rcx
0x1800045e8  jnz     short loc_180004601
0x1800045ea  sub     r14, 2
0x1800045ee  mov     [rsp+188h+var_140], r14
0x1800045f3  dec     r9
0x1800045f6  mov     [rsp+188h+var_138], r9
0x1800045fb  mov     r10d, 8007007Ah
0x180004601  xor     eax, eax
0x180004603  mov     [r14], ax
0x180004607  mov     [rsp+188h+var_148], r10d
0x18000460c  jmp     short loc_180004620
0x18000460e  mov     edi, 0C0000225h
0x180004613  mov     [rsp+188h+var_144], edi
0x180004617  jmp     short loc_180004620
0x180004619  mov     ecx, 3
0x18000461e  int     29h; Win8: RtlFailFast(ecx)
0x180004620  lea     rcx, SxsActCtxCacheCS; CriticalSection
0x180004627  call    cs:__imp_RtlLeaveCriticalSection
0x18000462e  nop     dword ptr [rax+rax+00h]
0x180004633  mov     eax, edi
0x180004635  mov     rcx, [rsp+188h+var_48]
0x18000463d  xor     rcx, rsp; StackCookie
0x180004640  call    __security_check_cookie
0x180004645  add     rsp, 150h
0x18000464c  pop     r15
0x18000464e  pop     r14
0x180004650  pop     r13
0x180004652  pop     r12
0x180004654  pop     rdi
0x180004655  pop     rsi
0x180004656  pop     rbx
0x180004657  retn
0x180006fa0  push    rbp
0x180006fa2  sub     rsp, 40h
0x180006fa6  mov     rbp, rdx
0x180006fa9  lea     rcx, SxsActCtxCacheCS; CriticalSection
0x180006fb0  call    cs:__imp_RtlLeaveCriticalSection
0x180006fb7  nop     dword ptr [rax+rax+00h]
0x180006fbc  nop
0x180006fbd  add     rsp, 40h
0x180006fc1  pop     rbp
0x180006fc2  retn
```
