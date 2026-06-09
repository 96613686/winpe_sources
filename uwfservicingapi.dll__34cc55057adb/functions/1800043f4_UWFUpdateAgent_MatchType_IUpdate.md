# UWFUpdateAgent::MatchType(IUpdate *)

- ea: `0x1800043f4`
- end: `0x1800045c7`
- name: `?MatchType@UWFUpdateAgent@@AEAAHPEAUIUpdate@@@Z`
- size: `467`
- prototype: `__int64 __fastcall(UWFUpdateAgent *__hidden this, struct IUpdate *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x18000490c`

## callees

- `0x180001536`
- `0x180002570`
- `0x180002db0`
- `0x1800043f4`
- `0x180006010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180004568`
- `msvcrt!_wcsicmp` at `0x180004596`
- `msvcrt!_wcsicmp` at `0x180004568`
- `msvcrt!_wcsicmp` at `0x180004596`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000445e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000450e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000445e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000450e`

## pseudocode

```c
__int64 __fastcall UWFUpdateAgent::MatchType(UWFUpdateAgent *this, struct IUpdate *a2)
{
  LSTATUS MultiString; // eax
  DWORD v4; // ecx
  unsigned __int64 v6; // rdi
  size_t v7; // rax
  void *v8; // rsi
  size_t v9; // rax
  const unsigned __int16 *v10; // rdx
  HKEY v11; // rcx
  unsigned __int16 **v12; // rdi
  LSTATUS v13; // eax
  struct IUpdateVtbl *lpVtbl; // rax
  unsigned int v15; // r14d
  int v16; // ebx
  int v17; // ebx
  UWFUpdateAgent *v18; // [rsp+70h] [rbp+30h] BYREF
  int v19; // [rsp+78h] [rbp+38h] BYREF
  int v20; // [rsp+80h] [rbp+40h] BYREF

  v18 = this;
  if ( !a2 )
    return 0;
  LODWORD(v18) = 0;
  v19 = 0;
  MultiString = UwfServicingRegGetMultiString(
                  (HKEY)this,
                  (const unsigned __int16 *)a2,
                  L"Type",
                  0,
                  &v19,
                  0,
                  (int *)&v18);
  if ( MultiString < 0 )
  {
    if ( (MultiString & 0x1FFF0000) == 0x70000 )
      MultiString = (unsigned __int16)MultiString;
    v4 = MultiString;
    goto LABEL_6;
  }
  if ( !v19 )
    return 0;
  v6 = (int)v18;
  if ( !(_DWORD)v18 )
    return 0;
  v7 = 2LL * v19;
  if ( !is_mul_ok(v19, 2u) )
    v7 = -1;
  v8 = operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v8 )
  {
LABEL_13:
    v4 = 14;
LABEL_6:
    SetLastError(v4);
    return 0;
  }
  v9 = 8 * v6;
  if ( !is_mul_ok(v6, 8u) )
    v9 = -1;
  v12 = (unsigned __int16 **)operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v12 )
  {
    operator delete(v8);
    goto LABEL_13;
  }
  v13 = UwfServicingRegGetMultiString(v11, v10, L"Type", (unsigned __int16 *)v8, &v19, v12, (int *)&v18);
  if ( v13 < 0 )
  {
    SetLastError(v13);
    operator delete(v8);
    operator delete(v12);
    return 0;
  }
  lpVtbl = a2->lpVtbl;
  v20 = 0;
  v15 = 0;
  if ( ((int (__fastcall *)(struct IUpdate *, int *))lpVtbl->get_Type)(a2, &v20) >= 0 )
  {
    if ( v20 != 1 )
    {
      if ( v20 != 2 )
        goto LABEL_32;
      v17 = 0;
      if ( (int)v18 <= 0 )
        goto LABEL_32;
      while ( _wcsicmp(L"driver", v12[v17]) )
      {
        if ( ++v17 >= (int)v18 )
          goto LABEL_32;
      }
      goto LABEL_31;
    }
    v16 = 0;
    if ( (int)v18 > 0 )
    {
      while ( _wcsicmp(L"software", v12[v16]) )
      {
        if ( ++v16 >= (int)v18 )
          goto LABEL_32;
      }
LABEL_31:
      v15 = 1;
    }
  }
LABEL_32:
  operator delete(v8);
  operator delete(v12);
  return v15;
}

```

## disassembly

```asm
0x1800043f4  mov     r11, rsp
0x1800043f7  mov     [r11+8], rcx
0x1800043fb  push    rbp
0x1800043fc  push    rbx
0x1800043fd  push    rsi
0x1800043fe  push    rdi
0x1800043ff  push    r14
0x180004401  mov     rbp, rsp
0x180004404  sub     rsp, 40h
0x180004408  mov     rbx, rdx
0x18000440b  test    rdx, rdx
0x18000440e  jz      short loc_180004464
0x180004410  lea     rax, [rbp+arg_0]
0x180004414  mov     dword ptr [rbp+arg_0], 0
0x18000441b  mov     [r11-38h], rax
0x18000441f  lea     r8, aType; "Type"
0x180004426  lea     rax, [rbp+arg_8]
0x18000442a  mov     qword ptr [r11-40h], 0
0x180004432  xor     r9d, r9d; unsigned __int16 *
0x180004435  mov     [r11-48h], rax
0x180004439  mov     [rbp+arg_8], 0
0x180004440  call    ?UwfServicingRegGetMultiString@@YAJPEAUHKEY__@@PEBG1PEAGPEAJPEAPEAG3@Z; UwfServicingRegGetMultiString(HKEY__ *,ushort const *,ushort const *,ushort *,long *,ushort * *,long *)
0x180004445  test    eax, eax
0x180004447  jns     short loc_180004471
0x180004449  mov     ecx, eax
0x18000444b  and     ecx, 1FFF0000h
0x180004451  cmp     ecx, 70000h
0x180004457  jnz     short loc_18000445C
0x180004459  movzx   eax, ax
0x18000445c  mov     ecx, eax; dwErrCode
0x18000445e  call    cs:__imp_SetLastError
0x180004464  xor     eax, eax
0x180004466  add     rsp, 40h
0x18000446a  pop     r14
0x18000446c  pop     rdi
0x18000446d  pop     rsi
0x18000446e  pop     rbx
0x18000446f  pop     rbp
0x180004470  retn
0x180004471  movsxd  rax, [rbp+arg_8]
0x180004475  test    eax, eax
0x180004477  jz      short loc_180004464
0x180004479  movsxd  rdi, dword ptr [rbp+arg_0]
0x18000447d  test    edi, edi
0x18000447f  jz      short loc_180004464
0x180004481  mov     rcx, rax
0x180004484  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18000448b  mov     eax, 2
0x180004490  mul     rcx
0x180004493  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000449a  cmovb   rax, r14
0x18000449e  mov     rcx, rax; unsigned __int64
0x1800044a1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800044a6  mov     rsi, rax
0x1800044a9  test    rax, rax
0x1800044ac  jnz     short loc_1800044B5
0x1800044ae  mov     ecx, 0Eh
0x1800044b3  jmp     short loc_18000445E
0x1800044b5  mov     eax, 8
0x1800044ba  mul     rdi
0x1800044bd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800044c4  cmovb   rax, r14
0x1800044c8  mov     rcx, rax; unsigned __int64
0x1800044cb  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800044d0  mov     rdi, rax
0x1800044d3  test    rax, rax
0x1800044d6  jnz     short loc_1800044E2
0x1800044d8  mov     rcx, rsi; void *
0x1800044db  call    ??3@YAXPEAX@Z_0; operator delete(void *)
0x1800044e0  jmp     short loc_1800044AE
0x1800044e2  lea     rax, [rbp+arg_0]
0x1800044e6  mov     r9, rsi; unsigned __int16 *
0x1800044e9  mov     [rsp+40h+var_10], rax; int *
0x1800044ee  lea     r8, aType; "Type"
0x1800044f5  lea     rax, [rbp+arg_8]
0x1800044f9  mov     [rsp+40h+var_18], rdi; unsigned __int16 **
0x1800044fe  mov     [rsp+40h+var_20], rax; int *
0x180004503  call    ?UwfServicingRegGetMultiString@@YAJPEAUHKEY__@@PEBG1PEAGPEAJPEAPEAG3@Z; UwfServicingRegGetMultiString(HKEY__ *,ushort const *,ushort const *,ushort *,long *,ushort * *,long *)
0x180004508  test    eax, eax
0x18000450a  jns     short loc_180004529
0x18000450c  mov     ecx, eax; dwErrCode
0x18000450e  call    cs:__imp_SetLastError
0x180004514  mov     rcx, rsi; void *
0x180004517  call    ??3@YAXPEAX@Z_0; operator delete(void *)
0x18000451c  mov     rcx, rdi; void *
0x18000451f  call    ??3@YAXPEAX@Z_0; operator delete(void *)
0x180004524  jmp     loc_180004464
0x180004529  mov     rax, [rbx]
0x18000452c  lea     rdx, [rbp+arg_10]
0x180004530  mov     rcx, rbx
0x180004533  mov     [rbp+arg_10], 0
0x18000453a  xor     r14d, r14d
0x18000453d  mov     rax, [rax+150h]
0x180004544  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004549  test    eax, eax
0x18000454b  js      short loc_1800045AF
0x18000454d  cmp     [rbp+arg_10], 1
0x180004551  jnz     short loc_18000457B
0x180004553  xor     ebx, ebx
0x180004555  cmp     dword ptr [rbp+arg_0], ebx
0x180004558  jle     short loc_1800045AF
0x18000455a  movsxd  rdx, ebx
0x18000455d  lea     rcx, aSoftware; "software"
0x180004564  mov     rdx, [rdi+rdx*8]; String2
0x180004568  call    cs:__imp__wcsicmp
0x18000456e  test    eax, eax
0x180004570  jz      short loc_1800045A9
0x180004572  inc     ebx
0x180004574  cmp     ebx, dword ptr [rbp+arg_0]
0x180004577  jl      short loc_18000455A
0x180004579  jmp     short loc_1800045AF
0x18000457b  cmp     [rbp+arg_10], 2
0x18000457f  jnz     short loc_1800045AF
0x180004581  xor     ebx, ebx
0x180004583  cmp     dword ptr [rbp+arg_0], ebx
0x180004586  jle     short loc_1800045AF
0x180004588  movsxd  rdx, ebx
0x18000458b  lea     rcx, aDriver; "driver"
0x180004592  mov     rdx, [rdi+rdx*8]; String2
0x180004596  call    cs:__imp__wcsicmp
0x18000459c  test    eax, eax
0x18000459e  jz      short loc_1800045A9
0x1800045a0  inc     ebx
0x1800045a2  cmp     ebx, dword ptr [rbp+arg_0]
0x1800045a5  jl      short loc_180004588
0x1800045a7  jmp     short loc_1800045AF
0x1800045a9  mov     r14d, 1
0x1800045af  mov     rcx, rsi; void *
0x1800045b2  call    ??3@YAXPEAX@Z_0; operator delete(void *)
0x1800045b7  mov     rcx, rdi; void *
0x1800045ba  call    ??3@YAXPEAX@Z_0; operator delete(void *)
0x1800045bf  mov     eax, r14d
0x1800045c2  jmp     loc_180004466
```
