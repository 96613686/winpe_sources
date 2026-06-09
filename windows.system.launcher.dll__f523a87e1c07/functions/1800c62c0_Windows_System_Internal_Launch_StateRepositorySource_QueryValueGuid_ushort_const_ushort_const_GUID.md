# Windows::System::Internal::Launch::StateRepositorySource::QueryValueGuid(ushort const *,ushort const *,_GUID *)

- ea: `0x1800c62c0`
- end: `0x1800c63d9`
- name: `?QueryValueGuid@StateRepositorySource@Launch@Internal@System@Windows@@UEAAJPEBG0PEAU_GUID@@@Z`
- size: `281`
- prototype: `int(Windows::System::Internal::Launch::StateRepositorySource *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct _GUID *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180010c04`
- `0x1800c62c0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c6325`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c637d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c6325`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c637d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c635e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c635e`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800c6392`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800c63c2`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800c6392`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800c63c2`

## pseudocode

```c
__int64 __fastcall Windows::System::Internal::Launch::StateRepositorySource::QueryValueGuid(
        Windows::System::Internal::Launch::StateRepositorySource *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct _GUID *a4)
{
  unsigned int v7; // edi
  const WCHAR *StringRawBuffer; // rax
  HRESULT v9; // ebx
  __int64 v10; // rdx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-18h]
  BOOL bIgnoreCasea; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( !a3 )
    return 2147942487LL;
  if ( !a4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x164,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.queryassociations.cpp",
      (const char *)0x80070057LL,
      bIgnoreCase);
    return 2147942487LL;
  }
  v7 = -2147024894;
  if ( CompareStringOrdinal(a3, -1, L"DelegateExecute", -1, 1) != 2 )
    return v7;
  if ( *((_BYTE *)this + 204) )
  {
    *a4 = CLSID_AppShellVerbHandler;
    return 0;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 15), 0);
  if ( CompareStringOrdinal(StringRawBuffer, -1, L"Windows.File", -1, 1) == 2 )
  {
    v9 = CLSIDFromString(L"{BFEC0C93-0B7D-4F2C-B09C-AFFFC4BDAE78}", a4);
    if ( v9 >= 0 )
      return 0;
    v10 = 371;
  }
  else
  {
    v9 = CLSIDFromString(L"{A56A841F-E974-45C1-8001-7E3F8A085917}", a4);
    if ( v9 >= 0 )
      return 0;
    v10 = 375;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.queryassociations.cpp",
    (const char *)(unsigned int)v9,
    bIgnoreCasea);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800c62c0  mov     [rsp+arg_0], rbx
0x1800c62c5  mov     [rsp+arg_8], rsi
0x1800c62ca  push    rdi
0x1800c62cb  sub     rsp, 30h
0x1800c62cf  mov     rbx, r9
0x1800c62d2  mov     rax, r8
0x1800c62d5  mov     rsi, rcx
0x1800c62d8  test    r8, r8
0x1800c62db  jnz     short loc_1800C62E4
0x1800c62dd  mov     eax, 80070057h
0x1800c62e2  jmp     short loc_1800C6348
0x1800c62e4  test    rbx, rbx
0x1800c62e7  jnz     short loc_1800C6307
0x1800c62e9  mov     rcx, [rsp+38h]; this
0x1800c62ee  lea     r8, aOnecoreuapShel_28; "onecoreuap\\shell\\windows.system.launc"...
0x1800c62f5  mov     r9d, 80070057h; char *
0x1800c62fb  mov     edx, 164h; void *
0x1800c6300  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c6305  jmp     short loc_1800C62DD
0x1800c6307  or      r9d, 0FFFFFFFFh; cchCount2
0x1800c630b  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x1800c6313  or      edx, r9d; cchCount1
0x1800c6316  lea     r8, aDelegateexecut; "DelegateExecute"
0x1800c631d  mov     rcx, rax; lpString1
0x1800c6320  mov     edi, 80070002h
0x1800c6325  call    cs:__imp_CompareStringOrdinal
0x1800c632b  cmp     eax, 2
0x1800c632e  jnz     short loc_1800C6346
0x1800c6330  cmp     byte ptr [rsi+0CCh], 0
0x1800c6337  jz      short loc_1800C6358
0x1800c6339  movups  xmm0, xmmword ptr cs:CLSID_AppShellVerbHandler.Data1
0x1800c6340  movdqu  xmmword ptr [rbx], xmm0
0x1800c6344  xor     edi, edi
0x1800c6346  mov     eax, edi
0x1800c6348  mov     rbx, [rsp+38h+arg_0]
0x1800c634d  mov     rsi, [rsp+38h+arg_8]
0x1800c6352  add     rsp, 30h
0x1800c6356  pop     rdi
0x1800c6357  retn
0x1800c6358  mov     rcx, [rsi+78h]; string
0x1800c635c  xor     edx, edx; length
0x1800c635e  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c6364  or      r9d, 0FFFFFFFFh; cchCount2
0x1800c6368  mov     [rsp+38h+bIgnoreCase], 1; int
0x1800c6370  or      edx, r9d; cchCount1
0x1800c6373  lea     r8, aWindowsFile; "Windows.File"
0x1800c637a  mov     rcx, rax; lpString1
0x1800c637d  call    cs:__imp_CompareStringOrdinal
0x1800c6383  mov     rdx, rbx; pclsid
0x1800c6386  cmp     eax, 2
0x1800c6389  jnz     short loc_1800C63BB
0x1800c638b  lea     rcx, sz; "{BFEC0C93-0B7D-4F2C-B09C-AFFFC4BDAE78}"
0x1800c6392  call    cs:__imp_CLSIDFromString
0x1800c6398  mov     ebx, eax
0x1800c639a  test    eax, eax
0x1800c639c  jns     short loc_1800C6344
0x1800c639e  mov     edx, 173h; void *
0x1800c63a3  mov     rcx, [rsp+38h]; this
0x1800c63a8  lea     r8, aOnecoreuapShel_28; "onecoreuap\\shell\\windows.system.launc"...
0x1800c63af  mov     r9d, ebx; char *
0x1800c63b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c63b7  mov     eax, ebx
0x1800c63b9  jmp     short loc_1800C6348
0x1800c63bb  lea     rcx, aA56a841fE97445; "{A56A841F-E974-45C1-8001-7E3F8A085917}"
0x1800c63c2  call    cs:__imp_CLSIDFromString
0x1800c63c8  mov     ebx, eax
0x1800c63ca  test    eax, eax
0x1800c63cc  jns     loc_1800C6344
0x1800c63d2  mov     edx, 177h
0x1800c63d7  jmp     short loc_1800C63A3
```
