# Windows::Internal::StateRepository::TileViewFactoryServer::CopyTo(Windows::Internal::StateRepository::ITileViewQueryFilter *,StateRepository::Entity::TileViewQueryFilter &)

- ea: `0x180041544`
- end: `0x180041786`
- name: `?CopyTo@TileViewFactoryServer@StateRepository@Internal@Windows@@QEAAJPEAUITileViewQueryFilter@234@AEAVTileViewQueryFilter@Entity@2@@Z`
- size: `578`
- prototype: `__int64 __fastcall(Windows::Internal::StateRepository::TileViewFactoryServer *__hidden this, struct Windows::Internal::StateRepository::ITileViewQueryFilter *, struct StateRepository::Entity::TileViewQueryFilter *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180040e40`

## callees

- `0x18001a9e0`
- `0x1800337a4`
- `0x180041544`
- `0x180041f30`
- `0x18027e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800415a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800415f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800416cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041716`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004173e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800415a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800415f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800416cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041716`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004173e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800415cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800416f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800415cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800416f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::StateRepository::TileViewFactoryServer::CopyTo(
        Windows::Internal::StateRepository::TileViewFactoryServer *this,
        struct Windows::Internal::StateRepository::ITileViewQueryFilter *a2,
        struct StateRepository::Entity::TileViewQueryFilter *a3)
{
  int v5; // ebx
  __int64 (__fastcall *v6)(struct Windows::Internal::StateRepository::ITileViewQueryFilter *, HSTRING *); // rbx
  int v7; // eax
  const unsigned __int16 *StringRawBuffer; // rax
  __int64 v10; // rdx
  __int64 (__fastcall *v11)(struct Windows::Internal::StateRepository::ITileViewQueryFilter *, HSTRING *); // rbx
  const unsigned __int16 *v12; // rax
  __int64 v13; // rdx
  HSTRING string[2]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  Windows::Internal::StateRepository::TileViewFactoryServer *v16; // [rsp+50h] [rbp+20h] BYREF
  int v17; // [rsp+58h] [rbp+28h] BYREF
  int v18; // [rsp+68h] [rbp+38h] BYREF

  v16 = this;
  LOBYTE(v16) = 0;
  v5 = (*(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::ITileViewQueryFilter *, Windows::Internal::StateRepository::TileViewFactoryServer **))(*(_QWORD *)a2 + 160LL))(
         a2,
         &v16);
  if ( v5 < 0 )
  {
    v10 = 21;
    goto LABEL_13;
  }
  if ( !(_BYTE)v16 )
  {
    string[0] = 0;
    v6 = *(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::ITileViewQueryFilter *, HSTRING *))(*(_QWORD *)a2 + 176LL);
    WindowsDeleteString(0);
    string[0] = 0;
    v7 = v6(a2, string);
    v5 = v7;
    if ( v7 < 0 )
    {
      v13 = 25;
    }
    else
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string[0], 0);
      v7 = StateRepository::Text::Set(
             (struct StateRepository::Entity::TileViewQueryFilter *)((char *)a3 + 16),
             StringRawBuffer,
             0x80u);
      v5 = v7;
      if ( v7 >= 0 )
      {
        WindowsDeleteString(string[0]);
        goto LABEL_6;
      }
      v13 = 26;
    }
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\windows.internal.staterepository.tilev"
                    "iewfactory-custom.cpp",
      (const char *)(unsigned int)v7,
      (int)string[0]);
    WindowsDeleteString(string[0]);
    return (unsigned int)v5;
  }
  StateRepository::TextA::Reset((struct StateRepository::Entity::TileViewQueryFilter *)((char *)a3 + 16));
LABEL_6:
  v17 = 0;
  v5 = (*(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::ITileViewQueryFilter *, int *))(*(_QWORD *)a2 + 64LL))(
         a2,
         &v17);
  if ( v5 < 0 )
  {
    v10 = 34;
  }
  else
  {
    *((_DWORD *)a3 + 1) = v17;
    v18 = 0;
    v5 = (*(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::ITileViewQueryFilter *, int *))(*(_QWORD *)a2 + 48LL))(
           a2,
           &v18);
    if ( v5 < 0 )
    {
      v10 = 38;
    }
    else
    {
      *(_DWORD *)a3 = v18;
      v5 = (*(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::ITileViewQueryFilter *, Windows::Internal::StateRepository::TileViewFactoryServer **))(*(_QWORD *)a2 + 192LL))(
             a2,
             &v16);
      if ( v5 >= 0 )
      {
        if ( (_BYTE)v16 )
        {
          StateRepository::TextA::Reset((struct StateRepository::Entity::TileViewQueryFilter *)((char *)a3 + 32));
          return 0;
        }
        string[0] = 0;
        v11 = *(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::ITileViewQueryFilter *, HSTRING *))(*(_QWORD *)a2 + 208LL);
        WindowsDeleteString(0);
        string[0] = 0;
        v7 = v11(a2, string);
        v5 = v7;
        if ( v7 < 0 )
        {
          v13 = 45;
        }
        else
        {
          v12 = WindowsGetStringRawBuffer(string[0], 0);
          v7 = StateRepository::Text::Set(
                 (struct StateRepository::Entity::TileViewQueryFilter *)((char *)a3 + 32),
                 v12,
                 0x823u);
          v5 = v7;
          if ( v7 >= 0 )
          {
            WindowsDeleteString(string[0]);
            return 0;
          }
          v13 = 46;
        }
        goto LABEL_21;
      }
      v10 = 41;
    }
  }
LABEL_13:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\windows.internal.staterepository.tilevie"
                  "wfactory-custom.cpp",
    (const char *)(unsigned int)v5,
    (int)string[0]);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180041544  mov     [rsp-18h+arg_10], rbx
0x180041549  mov     [rsp-18h+arg_0], rcx
0x18004154e  push    rbp
0x18004154f  push    rsi
0x180041550  push    rdi
0x180041551  mov     rbp, rsp
0x180041554  sub     rsp, 30h
0x180041558  mov     rsi, r8
0x18004155b  mov     rdi, rdx
0x18004155e  mov     byte ptr [rbp+arg_0], 0
0x180041562  mov     rax, [rdx]
0x180041565  lea     rdx, [rbp+arg_0]
0x180041569  mov     rcx, rdi
0x18004156c  mov     rax, [rax+0A0h]
0x180041573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041578  mov     ebx, eax
0x18004157a  test    eax, eax
0x18004157c  js      loc_180041686
0x180041582  cmp     byte ptr [rbp+arg_0], 0
0x180041586  jnz     loc_1800416A2
0x18004158c  mov     [rbp+string], 0
0x180041594  mov     rax, [rdi]
0x180041597  mov     rbx, [rax+0B0h]
0x18004159e  xor     ecx, ecx; string
0x1800415a0  call    cs:__imp_WindowsDeleteString
0x1800415a6  mov     [rbp+string], 0
0x1800415ae  lea     rdx, [rbp+string]
0x1800415b2  mov     rcx, rdi
0x1800415b5  mov     rax, rbx
0x1800415b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800415bd  mov     ebx, eax
0x1800415bf  test    eax, eax
0x1800415c1  js      loc_180041721
0x1800415c7  xor     edx, edx; length
0x1800415c9  mov     rcx, [rbp+string]; string
0x1800415cd  call    cs:__imp_WindowsGetStringRawBuffer
0x1800415d3  lea     rcx, [rsi+10h]; this
0x1800415d7  mov     r8d, 80h; unsigned __int64
0x1800415dd  mov     rdx, rax; unsigned __int16 *
0x1800415e0  call    ?Set@Text@StateRepository@@QEAAJPEBG_K@Z; StateRepository::Text::Set(ushort const *,unsigned __int64)
0x1800415e5  mov     ebx, eax
0x1800415e7  test    eax, eax
0x1800415e9  js      loc_180041753
0x1800415ef  mov     rcx, [rbp+string]; string
0x1800415f3  call    cs:__imp_WindowsDeleteString
0x1800415f9  mov     [rbp+arg_8], 0
0x180041600  mov     rax, [rdi]
0x180041603  lea     rdx, [rbp+arg_8]
0x180041607  mov     rcx, rdi
0x18004160a  mov     rax, [rax+40h]
0x18004160e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041613  mov     ebx, eax
0x180041615  test    eax, eax
0x180041617  js      loc_180041749
0x18004161d  mov     eax, [rbp+arg_8]
0x180041620  mov     [rsi+4], eax
0x180041623  mov     [rbp+arg_18], 0
0x18004162a  mov     rax, [rdi]
0x18004162d  lea     rdx, [rbp+arg_18]
0x180041631  mov     rcx, rdi
0x180041634  mov     rax, [rax+30h]
0x180041638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004163d  mov     ebx, eax
0x18004163f  test    eax, eax
0x180041641  js      loc_18004175A
0x180041647  mov     eax, [rbp+arg_18]
0x18004164a  mov     [rsi], eax
0x18004164c  mov     rax, [rdi]
0x18004164f  lea     rdx, [rbp+arg_0]
0x180041653  mov     rcx, rdi
0x180041656  mov     rax, [rax+0C0h]
0x18004165d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041662  mov     ebx, eax
0x180041664  test    eax, eax
0x180041666  js      short loc_1800416B0
0x180041668  cmp     byte ptr [rbp+arg_0], 0
0x18004166c  jz      short loc_1800416B7
0x18004166e  lea     rcx, [rsi+20h]; this
0x180041672  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x180041677  xor     eax, eax
0x180041679  mov     rbx, [rsp+30h+arg_10]
0x18004167e  add     rsp, 30h
0x180041682  pop     rdi
0x180041683  pop     rsi
0x180041684  pop     rbp
0x180041685  retn
0x180041686  mov     edx, 15h; void *
0x18004168b  lea     r8, aOnecoreBaseApp_359; "onecore\\base\\appmodel\\staterepositor"...
0x180041692  mov     r9d, ebx; char *
0x180041695  mov     rcx, [rbp+18h]; this
0x180041699  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004169e  mov     eax, ebx
0x1800416a0  jmp     short loc_180041679
0x1800416a2  lea     rcx, [rsi+10h]; this
0x1800416a6  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x1800416ab  jmp     loc_1800415F9
0x1800416b0  mov     edx, 29h ; ')'
0x1800416b5  jmp     short loc_18004168B
0x1800416b7  mov     [rbp+string], 0
0x1800416bf  mov     rax, [rdi]
0x1800416c2  mov     rbx, [rax+0D0h]
0x1800416c9  xor     ecx, ecx; string
0x1800416cb  call    cs:__imp_WindowsDeleteString
0x1800416d1  mov     [rbp+string], 0
0x1800416d9  lea     rdx, [rbp+string]
0x1800416dd  mov     rcx, rdi
0x1800416e0  mov     rax, rbx
0x1800416e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800416e8  mov     ebx, eax
0x1800416ea  test    eax, eax
0x1800416ec  js      short loc_180041764
0x1800416ee  xor     edx, edx; length
0x1800416f0  mov     rcx, [rbp+string]; string
0x1800416f4  call    cs:__imp_WindowsGetStringRawBuffer
0x1800416fa  lea     rcx, [rsi+20h]; this
0x1800416fe  mov     r8d, 823h; unsigned __int64
0x180041704  mov     rdx, rax; unsigned __int16 *
0x180041707  call    ?Set@Text@StateRepository@@QEAAJPEBG_K@Z; StateRepository::Text::Set(ushort const *,unsigned __int64)
0x18004170c  mov     ebx, eax
0x18004170e  test    eax, eax
0x180041710  js      short loc_18004176B
0x180041712  mov     rcx, [rbp+string]; string
0x180041716  call    cs:__imp_WindowsDeleteString
0x18004171c  jmp     loc_180041677
0x180041721  mov     edx, 19h; void *
0x180041726  mov     r9d, eax; char *
0x180041729  lea     r8, aOnecoreBaseApp_359; "onecore\\base\\appmodel\\staterepositor"...
0x180041730  mov     rcx, [rbp+18h]; this
0x180041734  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041739  nop
0x18004173a  mov     rcx, [rbp+string]; string
0x18004173e  call    cs:__imp_WindowsDeleteString
0x180041744  jmp     loc_18004169E
0x180041749  mov     edx, 22h ; '"'
0x18004174e  jmp     loc_18004168B
0x180041753  mov     edx, 1Ah
0x180041758  jmp     short loc_180041726
0x18004175a  mov     edx, 26h ; '&'
0x18004175f  jmp     loc_18004168B
0x180041764  mov     edx, 2Dh ; '-'
0x180041769  jmp     short loc_180041770
0x18004176b  mov     edx, 2Eh ; '.'; void *
0x180041770  mov     r9d, eax; char *
0x180041773  lea     r8, aOnecoreBaseApp_359; "onecore\\base\\appmodel\\staterepositor"...
0x18004177a  mov     rcx, [rbp+18h]; this
0x18004177e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041783  nop
0x180041784  jmp     short loc_18004173A
```
