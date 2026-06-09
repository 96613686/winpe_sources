# CAddRemoveSynchronizer::Create(int,int,ushort const *,CAddRemoveSynchronizer * *)

- ea: `0x18002195c`
- end: `0x180021aae`
- name: `?Create@CAddRemoveSynchronizer@@SAJHHPEBGPEAPEAV1@@Z`
- size: `338`
- prototype: `static int(int, int, const unsigned __int16 *, struct CAddRemoveSynchronizer **)`
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, registry_config`

## callers

- `0x180022b78`
- `0x180022cc0`

## callees

- `0x180005cc0`
- `0x180006234`
- `0x18000d4dc`
- `0x18002195c`
- `0x1800225f0`
- `0x180032010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_Set` at `0x180021a72`
- `SHLWAPI!__imp_IUnknown_Set` at `0x180021a72`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180021a25`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180021a4e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180021a25`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180021a4e`

## string_xrefs

- `0x1800219dd`: `ReadyToAdd`
- `0x180021a01`: `ReadyToRemove`

## pseudocode

```c
__int64 __fastcall CAddRemoveSynchronizer::Create(int a1, BOOL a2, const unsigned __int16 *a3, IUnknown **a4)
{
  IUnknown *v8; // rax
  IUnknown *v9; // rdi
  unsigned __int64 v10; // r9
  int ObjectNameForSearchRoot; // ebx
  unsigned __int64 v12; // r9
  struct IUnknownVtbl *EventW; // rax
  struct IUnknownVtbl *v14; // rax
  WCHAR Name[512]; // [rsp+30h] [rbp-838h] BYREF
  WCHAR v17[512]; // [rsp+430h] [rbp-438h] BYREF

  *a4 = 0;
  v8 = (IUnknown *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v8;
  if ( !v8 )
    return (unsigned int)-2147024882;
  LODWORD(v8[1].lpVtbl) = 0;
  v8->lpVtbl = (struct IUnknownVtbl *)&CAddRemoveSynchronizer::`vftable';
  ((void (__fastcall *)(IUnknown *))CTRefBase<CAddRemoveSynchronizer,IUnknown,CTRefBase_NoModuleLifetimePolicy>::AddRef)(v8);
  LODWORD(v9[2].lpVtbl) = a1;
  ObjectNameForSearchRoot = GetObjectNameForSearchRoot(a3, L"ReadyToAdd", Name, v10);
  if ( ObjectNameForSearchRoot >= 0 )
  {
    ObjectNameForSearchRoot = GetObjectNameForSearchRoot(a3, L"ReadyToRemove", v17, v12);
    if ( ObjectNameForSearchRoot >= 0 )
    {
      EventW = (struct IUnknownVtbl *)CreateEventW(0, 0, !a2, Name);
      v9[3].lpVtbl = EventW;
      if ( EventW || (ObjectNameForSearchRoot = ResultFromKnownLastError(), ObjectNameForSearchRoot >= 0) )
      {
        v14 = (struct IUnknownVtbl *)CreateEventW(0, 0, a2, v17);
        v9[4].lpVtbl = v14;
        if ( v14 )
        {
          ObjectNameForSearchRoot = 0;
LABEL_9:
          IUnknown_Set(a4, v9);
          goto LABEL_10;
        }
        ObjectNameForSearchRoot = ResultFromKnownLastError();
        if ( ObjectNameForSearchRoot >= 0 )
          goto LABEL_9;
      }
    }
  }
LABEL_10:
  ((void (__fastcall *)(IUnknown *))v9->lpVtbl->Release)(v9);
  return (unsigned int)ObjectNameForSearchRoot;
}

```

## disassembly

```asm
0x18002195c  push    rbx
0x18002195e  push    rbp
0x18002195f  push    rsi
0x180021960  push    rdi
0x180021961  push    r14
0x180021963  sub     rsp, 840h
0x18002196a  mov     rax, cs:__security_cookie
0x180021971  xor     rax, rsp
0x180021974  mov     [rsp+868h+var_38], rax
0x18002197c  mov     esi, edx
0x18002197e  mov     qword ptr [r9], 0
0x180021985  mov     ebx, ecx
0x180021987  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002198e  mov     ecx, 28h ; '('; unsigned __int64
0x180021993  mov     r14, r9
0x180021996  mov     rbp, r8
0x180021999  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002199e  mov     [rsp+868h+var_848], rax
0x1800219a3  mov     rdi, rax
0x1800219a6  test    rax, rax
0x1800219a9  jz      loc_180021A89
0x1800219af  mov     dword ptr [rax+8], 0
0x1800219b6  lea     rax, ??_7CAddRemoveSynchronizer@@6B@; const CAddRemoveSynchronizer::`vftable'
0x1800219bd  mov     [rdi], rax
0x1800219c0  test    rdi, rdi
0x1800219c3  jz      loc_180021A89
0x1800219c9  mov     rax, [rax+8]
0x1800219cd  mov     rcx, rdi
0x1800219d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800219d5  lea     r8, [rsp+868h+Name]; unsigned __int16 *
0x1800219da  mov     [rdi+10h], ebx
0x1800219dd  lea     rdx, aReadytoadd; "ReadyToAdd"
0x1800219e4  mov     rcx, rbp; unsigned __int16 *
0x1800219e7  call    ?GetObjectNameForSearchRoot@@YAJPEBG0PEAG_K@Z; GetObjectNameForSearchRoot(ushort const *,ushort const *,ushort *,unsigned __int64)
0x1800219ec  mov     ebx, eax
0x1800219ee  test    eax, eax
0x1800219f0  js      loc_180021A78
0x1800219f6  lea     r8, [rsp+868h+var_438]; unsigned __int16 *
0x1800219fe  mov     rcx, rbp; unsigned __int16 *
0x180021a01  lea     rdx, aReadytoremove; "ReadyToRemove"
0x180021a08  call    ?GetObjectNameForSearchRoot@@YAJPEBG0PEAG_K@Z; GetObjectNameForSearchRoot(ushort const *,ushort const *,ushort *,unsigned __int64)
0x180021a0d  mov     ebx, eax
0x180021a0f  test    eax, eax
0x180021a11  js      short loc_180021A78
0x180021a13  xor     r8d, r8d
0x180021a16  lea     r9, [rsp+868h+Name]; lpName
0x180021a1b  test    esi, esi
0x180021a1d  setz    r8b; bInitialState
0x180021a21  xor     edx, edx; bManualReset
0x180021a23  xor     ecx, ecx; lpEventAttributes
0x180021a25  call    cs:__imp_CreateEventW
0x180021a2b  mov     [rdi+18h], rax
0x180021a2f  test    rax, rax
0x180021a32  jnz     short loc_180021A3F
0x180021a34  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180021a39  mov     ebx, eax
0x180021a3b  test    eax, eax
0x180021a3d  js      short loc_180021A78
0x180021a3f  lea     r9, [rsp+868h+var_438]; lpName
0x180021a47  mov     r8d, esi; bInitialState
0x180021a4a  xor     edx, edx; bManualReset
0x180021a4c  xor     ecx, ecx; lpEventAttributes
0x180021a4e  call    cs:__imp_CreateEventW
0x180021a54  mov     [rdi+20h], rax
0x180021a58  test    rax, rax
0x180021a5b  jz      short loc_180021A61
0x180021a5d  xor     ebx, ebx
0x180021a5f  jmp     short loc_180021A6C
0x180021a61  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180021a66  mov     ebx, eax
0x180021a68  test    eax, eax
0x180021a6a  js      short loc_180021A78
0x180021a6c  mov     rdx, rdi; punk
0x180021a6f  mov     rcx, r14; ppunk
0x180021a72  call    cs:__imp_IUnknown_Set
0x180021a78  mov     rax, [rdi]
0x180021a7b  mov     rcx, rdi
0x180021a7e  mov     rax, [rax+10h]
0x180021a82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a87  jmp     short loc_180021A8E
0x180021a89  mov     ebx, 8007000Eh
0x180021a8e  mov     eax, ebx
0x180021a90  mov     rcx, [rsp+868h+var_38]
0x180021a98  xor     rcx, rsp; StackCookie
0x180021a9b  call    __security_check_cookie
0x180021aa0  add     rsp, 840h
0x180021aa7  pop     r14
0x180021aa9  pop     rdi
0x180021aaa  pop     rsi
0x180021aab  pop     rbp
0x180021aac  pop     rbx
0x180021aad  retn
```
