# SXReader::`vector deleting destructor'(uint)

- ea: `0x1004043c0`
- end: `0x100404597`
- name: `??_ESXReader@@MEAAPEAXI@Z`
- size: `471`
- prototype: `void *__fastcall(SXReader *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1004011f0`
- `0x1004043c0`
- `0x10040e630`
- `0x100424580`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x100404401`
- `KERNEL32!EnterCriticalSection` at `0x100404401`
- `KERNEL32!LeaveCriticalSection` at `0x100404439`
- `KERNEL32!LeaveCriticalSection` at `0x100404439`
- `KERNEL32!HeapFree` at `0x100404500`
- `KERNEL32!HeapFree` at `0x10040455e`
- `KERNEL32!HeapFree` at `0x100404500`
- `KERNEL32!HeapFree` at `0x10040455e`

## pseudocode

```c
SXReader *__fastcall SXReader::`vector deleting destructor'(SXReader *this, char a2)
{
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  void *v8; // r8
  struct IMalloc *v9; // rcx
  struct IMalloc *v10; // rcx

  *(_QWORD *)this = &SXReader::`vftable'{for `SXReadBase'};
  *((_QWORD *)this + 182) = &SXReader::`vftable'{for `ISAXXMLReader'};
  *((_QWORD *)this + 183) = &SXReader::`vftable'{for `ISAXLocator'};
  EnterCriticalSection(&s_cs);
  if ( !--s_cComponents && s_pMultiLanguage2 )
  {
    ((void (__fastcall *)(struct IMultiLanguage2 *))s_pMultiLanguage2->lpVtbl->Release)(s_pMultiLanguage2);
    s_pMultiLanguage2 = 0;
  }
  LeaveCriticalSection(&s_cs);
  v4 = *((_QWORD *)this + 185);
  if ( v4 )
  {
    *((_QWORD *)this + 185) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  v5 = *((_QWORD *)this + 186);
  if ( v5 )
  {
    *((_QWORD *)this + 186) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  v6 = *((_QWORD *)this + 187);
  if ( v6 )
  {
    *((_QWORD *)this + 187) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  v7 = *((_QWORD *)this + 188);
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v7 + 16) + 16LL))(v7 + 16);
    *((_QWORD *)this + 188) = 0;
  }
  v8 = (void *)*((_QWORD *)this + 190);
  if ( v8 )
  {
    v9 = (struct IMalloc *)*((_QWORD *)this + 1);
    if ( v9 || (v9 = g_pMalloc) != 0 )
      ((void (__fastcall *)(struct IMalloc *, _QWORD))v9->lpVtbl->Free)(v9, *((_QWORD *)this + 190));
    else
      HeapFree(g_hHeap, 0, v8);
  }
  SXReadBase::~SXReadBase(this);
  if ( (a2 & 1) == 0 )
    return this;
  if ( (a2 & 4) != 0 )
  {
    __global_delete(this);
    return this;
  }
  v10 = (struct IMalloc *)*((_QWORD *)this + 1);
  if ( v10 || (v10 = g_pMalloc) != 0 )
  {
    ((void (__fastcall *)(struct IMalloc *, SXReader *))v10->lpVtbl->Free)(v10, this);
    return this;
  }
  else
  {
    HeapFree(g_hHeap, 0, this);
    return this;
  }
}

```

## disassembly

```asm
0x1004043c0  mov     [rsp+arg_0], rbx
0x1004043c5  mov     [rsp+arg_8], rsi
0x1004043ca  push    rdi
0x1004043cb  sub     rsp, 20h
0x1004043cf  lea     rax, ??_7SXReader@@6BSXReadBase@@@; const SXReader::`vftable'{for `SXReadBase'}
0x1004043d6  mov     rbx, rcx
0x1004043d9  mov     [rcx], rax
0x1004043dc  mov     edi, edx
0x1004043de  lea     rax, ??_7SXReader@@6BISAXXMLReader@@@; const SXReader::`vftable'{for `ISAXXMLReader'}
0x1004043e5  mov     [rcx+5B0h], rax
0x1004043ec  lea     rax, ??_7SXReader@@6BISAXLocator@@@; const SXReader::`vftable'{for `ISAXLocator'}
0x1004043f3  mov     [rcx+5B8h], rax
0x1004043fa  lea     rcx, ?s_cs@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x100404401  call    cs:__imp_EnterCriticalSection
0x100404407  xor     esi, esi
0x100404409  sub     cs:?s_cComponents@@3JA, 1; long s_cComponents
0x100404410  jnz     short loc_100404432
0x100404412  mov     rcx, cs:?s_pMultiLanguage2@@3PEAUIMultiLanguage2@@EA; IMultiLanguage2 * s_pMultiLanguage2
0x100404419  test    rcx, rcx
0x10040441c  jz      short loc_100404432
0x10040441e  mov     rax, [rcx]
0x100404421  mov     rax, [rax+10h]
0x100404425  call    cs:__guard_dispatch_icall_fptr
0x10040442b  mov     cs:?s_pMultiLanguage2@@3PEAUIMultiLanguage2@@EA, rsi; IMultiLanguage2 * s_pMultiLanguage2
0x100404432  lea     rcx, ?s_cs@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x100404439  call    cs:__imp_LeaveCriticalSection
0x10040443f  mov     rcx, [rbx+5C8h]
0x100404446  test    rcx, rcx
0x100404449  jz      short loc_10040445F
0x10040444b  mov     [rbx+5C8h], rsi
0x100404452  mov     rax, [rcx]
0x100404455  mov     rax, [rax+10h]
0x100404459  call    cs:__guard_dispatch_icall_fptr
0x10040445f  mov     rcx, [rbx+5D0h]
0x100404466  test    rcx, rcx
0x100404469  jz      short loc_10040447F
0x10040446b  mov     [rbx+5D0h], rsi
0x100404472  mov     rax, [rcx]
0x100404475  mov     rax, [rax+10h]
0x100404479  call    cs:__guard_dispatch_icall_fptr
0x10040447f  mov     rcx, [rbx+5D8h]
0x100404486  test    rcx, rcx
0x100404489  jz      short loc_10040449F
0x10040448b  mov     [rbx+5D8h], rsi
0x100404492  mov     rax, [rcx]
0x100404495  mov     rax, [rax+10h]
0x100404499  call    cs:__guard_dispatch_icall_fptr
0x10040449f  mov     rcx, [rbx+5E0h]
0x1004044a6  test    rcx, rcx
0x1004044a9  jz      short loc_1004044C4
0x1004044ab  mov     rax, [rcx+10h]
0x1004044af  add     rcx, 10h
0x1004044b3  mov     rax, [rax+10h]
0x1004044b7  call    cs:__guard_dispatch_icall_fptr
0x1004044bd  mov     [rbx+5E0h], rsi
0x1004044c4  mov     r8, [rbx+5F0h]; lpMem
0x1004044cb  test    r8, r8
0x1004044ce  jz      short loc_100404506
0x1004044d0  mov     rcx, [rbx+8]
0x1004044d4  test    rcx, rcx
0x1004044d7  jnz     short loc_1004044E5
0x1004044d9  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x1004044e0  test    rcx, rcx
0x1004044e3  jz      short loc_1004044F7
0x1004044e5  mov     rax, [rcx]
0x1004044e8  mov     rdx, r8
0x1004044eb  mov     rax, [rax+28h]
0x1004044ef  call    cs:__guard_dispatch_icall_fptr
0x1004044f5  jmp     short loc_100404506
0x1004044f7  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x1004044fe  xor     edx, edx; dwFlags
0x100404500  call    cs:__imp_HeapFree
0x100404506  mov     rcx, rbx; this
0x100404509  call    ??1SXReadBase@@MEAA@XZ; SXReadBase::~SXReadBase(void)
0x10040450e  test    dil, 1
0x100404512  jz      short loc_100404584
0x100404514  test    dil, 4
0x100404518  jnz     short loc_100404577
0x10040451a  mov     rcx, [rbx+8]
0x10040451e  test    rcx, rcx
0x100404521  jz      short loc_100404546
0x100404523  mov     rax, [rcx]
0x100404526  mov     rdx, rbx
0x100404529  mov     rax, [rax+28h]
0x10040452d  call    cs:__guard_dispatch_icall_fptr
0x100404533  mov     rax, rbx
0x100404536  mov     rbx, [rsp+28h+arg_0]
0x10040453b  mov     rsi, [rsp+28h+arg_8]
0x100404540  add     rsp, 20h
0x100404544  pop     rdi
0x100404545  retn
0x100404546  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10040454d  test    rcx, rcx
0x100404550  jnz     short loc_100404523
0x100404552  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x100404559  mov     r8, rbx; lpMem
0x10040455c  xor     edx, edx; dwFlags
0x10040455e  call    cs:__imp_HeapFree
0x100404564  mov     rax, rbx
0x100404567  mov     rbx, [rsp+28h+arg_0]
0x10040456c  mov     rsi, [rsp+28h+arg_8]
0x100404571  add     rsp, 20h
0x100404575  pop     rdi
0x100404576  retn
0x100404577  mov     edx, 600h; unsigned __int64
0x10040457c  mov     rcx, rbx; void *
0x10040457f  call    ?__global_delete@@YAXPEAX_K@Z; __global_delete(void *,unsigned __int64)
0x100404584  mov     rsi, [rsp+28h+arg_8]
0x100404589  mov     rax, rbx
0x10040458c  mov     rbx, [rsp+28h+arg_0]
0x100404591  add     rsp, 20h
0x100404595  pop     rdi
0x100404596  retn
```
