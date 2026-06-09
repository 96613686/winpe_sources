# COfflineObjectItem_CreateInstance(COfflineFolder *,uint,_ITEMIDLIST const * *,_GUID const &,void * *)

- ea: `0x18000e9c8`
- end: `0x18000eb6e`
- name: `?COfflineObjectItem_CreateInstance@@YAJPEAVCOfflineFolder@@IPEAPEFBU_ITEMIDLIST@@AEBU_GUID@@PEAPEAX@Z`
- size: `422`
- prototype: `__int64 __fastcall(struct COfflineFolder *, unsigned int, const struct _ITEMIDLIST **, const struct _GUID *Buf1, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000a080`

## callees

- `0x18000e9c8`
- `0x18000f098`
- `0x18001ba08`
- `0x180029236`
- `0x18002a010`

## import_xrefs

- `USER32!RegisterClipboardFormatW` at `0x18000eb13`
- `USER32!RegisterClipboardFormatW` at `0x18000eb26`
- `USER32!RegisterClipboardFormatW` at `0x18000eb39`
- `USER32!RegisterClipboardFormatW` at `0x18000eb4c`
- `USER32!RegisterClipboardFormatW` at `0x18000eb13`
- `USER32!RegisterClipboardFormatW` at `0x18000eb26`
- `USER32!RegisterClipboardFormatW` at `0x18000eb39`
- `USER32!RegisterClipboardFormatW` at `0x18000eb4c`

## string_xrefs

- `0x18000eb0c`: `FileGroupDescriptorW`

## pseudocode

```c
__int64 __fastcall COfflineObjectItem_CreateInstance(
        struct COfflineFolder *a1,
        unsigned int a2,
        const struct _ITEMIDLIST **a3,
        const struct _GUID *Buf1,
        void **a5)
{
  __int64 v9; // r10
  const struct _ITEMIDLIST *v10; // rcx
  _QWORD *v12; // rax
  _QWORD *v13; // rbx
  int v14; // edi

  v9 = 0;
  *a5 = 0;
  while ( (unsigned int)v9 < a2 )
  {
    v10 = a3[v9];
    if ( v10->mkid.cb <= 0xE0u || *(_WORD *)v10->mkid.abID != 29701 )
      return 2147500037LL;
    v9 = (unsigned int)(v9 + 1);
  }
  if ( (!memcmp_0(Buf1, &IID_IExtractIconA, 0x10u) || !memcmp_0(Buf1, &IID_IExtractIconW, 0x10u)) && a2 != 1 )
    return 2147500037LL;
  v12 = operator new(0x50u);
  v13 = v12;
  if ( !v12 )
    return 2147942414LL;
  *v12 = &COfflineObjectItem::`vftable'{for `IContextMenu'};
  v12[1] = &COfflineObjectItem::`vftable'{for `IExtractIconA'};
  v12[2] = &COfflineObjectItem::`vftable'{for `IExtractIconW'};
  v12[3] = &COfflineObjectItem::`vftable'{for `IDataObject'};
  v12[4] = &COfflineObjectItem::`vftable'{for `IQueryInfo'};
  _InterlockedIncrement((volatile signed __int32 *)&g_cObj);
  v12[6] = 0;
  v12[8] = 0;
  v12[9] = 0;
  *((_DWORD *)v12 + 10) = 1;
  v14 = COfflineObjectItem::Initialize((COfflineObjectItem *)v12, a1, a2, a3);
  if ( v14 >= 0 )
    v14 = (*(__int64 (__fastcall **)(_QWORD *, const struct _GUID *, void **))*v13)(v13, Buf1, a5);
  (*(void (__fastcall **)(_QWORD *))(*v13 + 16LL))(v13);
  if ( !g_cfPrefDropEffect )
  {
    g_cfFileDescriptor = RegisterClipboardFormatW(L"FileGroupDescriptorW");
    g_cfFileContents = RegisterClipboardFormatW(L"FileContents");
    g_cfPrefDropEffect = RegisterClipboardFormatW(L"Preferred DropEffect");
    g_cfURL = RegisterClipboardFormatW(L"UniformResourceLocator");
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18000e9c8  push    rbx
0x18000e9ca  push    rbp
0x18000e9cb  push    rsi
0x18000e9cc  push    rdi
0x18000e9cd  push    r14
0x18000e9cf  push    r15
0x18000e9d1  sub     rsp, 28h
0x18000e9d5  mov     r14, [rsp+58h+arg_20]
0x18000e9dd  mov     rsi, r9
0x18000e9e0  mov     r15, r8
0x18000e9e3  mov     edi, edx
0x18000e9e5  mov     rbp, rcx
0x18000e9e8  xor     r10d, r10d
0x18000e9eb  mov     qword ptr [r14], 0
0x18000e9f2  cmp     r10d, edi
0x18000e9f5  jnb     short loc_18000EA15
0x18000e9f7  mov     rcx, [r8+r10*8]
0x18000e9fb  mov     eax, 0E0h
0x18000ea00  cmp     [rcx], ax
0x18000ea03  jbe     short loc_18000EA4B
0x18000ea05  mov     eax, 7405h
0x18000ea0a  cmp     [rcx+2], ax
0x18000ea0e  jnz     short loc_18000EA4B
0x18000ea10  inc     r10d
0x18000ea13  jmp     short loc_18000E9F2
0x18000ea15  mov     ebx, 10h
0x18000ea1a  lea     rdx, IID_IExtractIconA; Buf2
0x18000ea21  mov     r8d, ebx; Size
0x18000ea24  mov     rcx, rsi; Buf1
0x18000ea27  call    memcmp_0
0x18000ea2c  test    eax, eax
0x18000ea2e  jz      short loc_18000EA46
0x18000ea30  mov     r8d, ebx; Size
0x18000ea33  lea     rdx, IID_IExtractIconW; Buf2
0x18000ea3a  mov     rcx, rsi; Buf1
0x18000ea3d  call    memcmp_0
0x18000ea42  test    eax, eax
0x18000ea44  jnz     short loc_18000EA55
0x18000ea46  cmp     edi, 1
0x18000ea49  jz      short loc_18000EA55
0x18000ea4b  mov     eax, 80004005h
0x18000ea50  jmp     loc_18000EB61
0x18000ea55  mov     ecx, 50h ; 'P'; dwBytes
0x18000ea5a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ea5f  mov     rbx, rax
0x18000ea62  test    rax, rax
0x18000ea65  jz      loc_18000EB5C
0x18000ea6b  lea     rax, ??_7COfflineObjectItem@@6BIContextMenu@@@; const COfflineObjectItem::`vftable'{for `IContextMenu'}
0x18000ea72  mov     [rbx], rax
0x18000ea75  lea     rax, ??_7COfflineObjectItem@@6BIExtractIconA@@@; const COfflineObjectItem::`vftable'{for `IExtractIconA'}
0x18000ea7c  mov     [rbx+8], rax
0x18000ea80  lea     rax, ??_7COfflineObjectItem@@6BIExtractIconW@@@; const COfflineObjectItem::`vftable'{for `IExtractIconW'}
0x18000ea87  mov     [rbx+10h], rax
0x18000ea8b  lea     rax, ??_7COfflineObjectItem@@6BIDataObject@@@; const COfflineObjectItem::`vftable'{for `IDataObject'}
0x18000ea92  mov     [rbx+18h], rax
0x18000ea96  lea     rax, ??_7COfflineObjectItem@@6BIQueryInfo@@@; const COfflineObjectItem::`vftable'{for `IQueryInfo'}
0x18000ea9d  mov     [rbx+20h], rax
0x18000eaa1  lock inc cs:?g_cObj@@3KA; ulong g_cObj
0x18000eaa8  mov     r9, r15; struct _ITEMIDLIST **
0x18000eaab  mov     qword ptr [rbx+30h], 0
0x18000eab3  mov     r8d, edi; unsigned int
0x18000eab6  mov     qword ptr [rbx+40h], 0
0x18000eabe  mov     rdx, rbp; struct COfflineFolder *
0x18000eac1  mov     qword ptr [rbx+48h], 0
0x18000eac9  mov     rcx, rbx; this
0x18000eacc  mov     dword ptr [rbx+28h], 1
0x18000ead3  call    ?Initialize@COfflineObjectItem@@QEAAJPEAVCOfflineFolder@@IPEAPEFBU_ITEMIDLIST@@@Z; COfflineObjectItem::Initialize(COfflineFolder *,uint,_ITEMIDLIST const * *)
0x18000ead8  mov     edi, eax
0x18000eada  test    eax, eax
0x18000eadc  js      short loc_18000EAF4
0x18000eade  mov     rax, [rbx]
0x18000eae1  mov     r8, r14
0x18000eae4  mov     rdx, rsi
0x18000eae7  mov     rcx, rbx
0x18000eaea  mov     rax, [rax]
0x18000eaed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eaf2  mov     edi, eax
0x18000eaf4  mov     rax, [rbx]
0x18000eaf7  mov     rcx, rbx
0x18000eafa  mov     rax, [rax+10h]
0x18000eafe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb03  cmp     cs:?g_cfPrefDropEffect@@3IA, 0; uint g_cfPrefDropEffect
0x18000eb0a  jnz     short loc_18000EB58
0x18000eb0c  lea     rcx, aFilegroupdescr; "FileGroupDescriptorW"
0x18000eb13  call    cs:__imp_RegisterClipboardFormatW
0x18000eb19  lea     rcx, aFilecontents; "FileContents"
0x18000eb20  mov     cs:?g_cfFileDescriptor@@3IA, eax; uint g_cfFileDescriptor
0x18000eb26  call    cs:__imp_RegisterClipboardFormatW
0x18000eb2c  lea     rcx, aPreferredDrope; "Preferred DropEffect"
0x18000eb33  mov     cs:?g_cfFileContents@@3IA, eax; uint g_cfFileContents
0x18000eb39  call    cs:__imp_RegisterClipboardFormatW
0x18000eb3f  lea     rcx, aUniformresourc; "UniformResourceLocator"
0x18000eb46  mov     cs:?g_cfPrefDropEffect@@3IA, eax; uint g_cfPrefDropEffect
0x18000eb4c  call    cs:__imp_RegisterClipboardFormatW
0x18000eb52  mov     cs:?g_cfURL@@3IA, eax; uint g_cfURL
0x18000eb58  mov     eax, edi
0x18000eb5a  jmp     short loc_18000EB61
0x18000eb5c  mov     eax, 8007000Eh
0x18000eb61  add     rsp, 28h
0x18000eb65  pop     r15
0x18000eb67  pop     r14
0x18000eb69  pop     rdi
0x18000eb6a  pop     rsi
0x18000eb6b  pop     rbp
0x18000eb6c  pop     rbx
0x18000eb6d  retn
```
