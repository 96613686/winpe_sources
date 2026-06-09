# TerminationStore::ConvertKeyToItem(HKEY__ *,wchar_t const *,TerminationItem *)

- ea: `0x18002d084`
- end: `0x18002d1e8`
- name: `?ConvertKeyToItem@TerminationStore@@AEAAJPEAUHKEY__@@PEB_WPEAUTerminationItem@@@Z`
- size: `356`
- prototype: `int __fastcall(TerminationStore *this, HKEY, const wchar_t *, struct TerminationItem *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002d1f0`
- `0x18002d9d8`

## callees

- `0x1800029f4`
- `0x18000cb10`
- `0x18000ff1c`
- `0x18000fff0`
- `0x18002d084`
- `0x18002dad8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18002d09f`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18002d09f`

## string_xrefs

- `0x18002d0b6`: `onecore\windows\feedback\core\common\libex\terminationstore.cpp`
- `0x18002d136`: `onecore\windows\feedback\core\common\libex\terminationstore.cpp`

## pseudocode

```c
int __fastcall TerminationStore::ConvertKeyToItem(
        TerminationStore *this,
        HKEY a2,
        const wchar_t *a3,
        struct TerminationItem *a4)
{
  unsigned int v6; // eax
  __int64 v7; // rdx
  int DWORD; // eax
  signed int String; // ebx
  __int64 v11; // rdx
  _WORD *v12; // r9
  _WORD *v13; // r8
  _WORD *v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rdx
  _WORD *v17; // rcx
  bool *v18; // [rsp+20h] [rbp-48h]
  int v19; // [rsp+20h] [rbp-48h]
  bool v20; // [rsp+28h] [rbp-40h]
  DWORD v21; // [rsp+28h] [rbp-40h]
  void *v22[2]; // [rsp+40h] [rbp-28h] BYREF
  _WORD v23[12]; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+20h]

  v6 = wcstoul(a3, 0, 10);
  *(_DWORD *)a4 = v6;
  if ( !v6 )
  {
    v7 = 204;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v7,
             (unsigned int)"onecore\\windows\\feedback\\core\\common\\libex\\terminationstore.cpp",
             (const char *)0xD,
             (unsigned int)v18);
  }
  DWORD = UtilRegGetDWORD(a2, 0, L"Reason", 5u, v18, v20);
  *((_DWORD *)a4 + 33) = DWORD;
  if ( DWORD >= 5 )
  {
    v7 = 214;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v7,
             (unsigned int)"onecore\\windows\\feedback\\core\\common\\libex\\terminationstore.cpp",
             (const char *)0xD,
             (unsigned int)v18);
  }
  v23[0] = 0;
  v22[0] = v23;
  v22[1] = v23;
  String = UtilRegGetString(a2, 0, L"Terminator", (__int64)v22, v21);
  if ( String < 0 )
  {
    v11 = 223;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\windows\\feedback\\core\\common\\libex\\terminationstore.cpp",
      (const char *)(unsigned int)String,
      v19);
    if ( v22[0] != v23 )
      operator delete(v22[0], (const struct std::nothrow_t *)&std::nothrow);
    return String;
  }
  v12 = v22[0];
  v13 = (_WORD *)((char *)a4 + 4);
  v14 = v22[0];
  v15 = 2147483646;
  v16 = 64;
  do
  {
    if ( !v15 )
      break;
    if ( !*v14 )
      break;
    *v13++ = *v14++;
    --v15;
    --v16;
  }
  while ( v16 );
  v17 = v13 - 1;
  String = v16 == 0 ? 0x8007007A : 0;
  if ( v16 )
    v17 = v13;
  *v17 = 0;
  if ( !v16 )
  {
    v11 = 225;
    goto LABEL_8;
  }
  if ( v12 != v23 )
    operator delete(v12, (const struct std::nothrow_t *)&std::nothrow);
  return 0;
}

```

## disassembly

```asm
0x18002d084  push    rbp
0x18002d086  push    rbx
0x18002d087  push    rsi
0x18002d088  push    rdi
0x18002d089  mov     rbp, rsp
0x18002d08c  sub     rsp, 68h
0x18002d090  mov     rbx, rdx
0x18002d093  mov     rcx, r8; String
0x18002d096  xor     edx, edx; EndPtr
0x18002d098  mov     rdi, r9
0x18002d09b  lea     r8d, [rdx+0Ah]; Radix
0x18002d09f  call    cs:__imp_wcstoul
0x18002d0a5  xor     esi, esi
0x18002d0a7  mov     [rdi], eax
0x18002d0a9  test    eax, eax
0x18002d0ab  jnz     short loc_18002D0CD
0x18002d0ad  mov     edx, 0CCh; void *
0x18002d0b2  mov     rcx, [rbp+20h]; this
0x18002d0b6  lea     r8, aOnecoreWindows_3; "onecore\\windows\\feedback\\core\\commo"...
0x18002d0bd  mov     r9d, 0Dh; char *
0x18002d0c3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002d0c8  jmp     loc_18002D1DF
0x18002d0cd  mov     r9d, 5; unsigned int
0x18002d0d3  lea     r8, aReason; "Reason"
0x18002d0da  xor     edx, edx; lpSubKey
0x18002d0dc  mov     rcx, rbx; hKey
0x18002d0df  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x18002d0e4  mov     [rdi+84h], eax
0x18002d0ea  cmp     eax, 5
0x18002d0ed  jl      short loc_18002D0F6
0x18002d0ef  mov     edx, 0D6h
0x18002d0f4  jmp     short loc_18002D0B2
0x18002d0f6  lea     rax, [rbp+var_18]
0x18002d0fa  mov     [rbp+var_18], si
0x18002d0fe  mov     [rbp+var_28], rax
0x18002d102  lea     r8, ValueName; "Terminator"
0x18002d109  lea     rax, [rbp+var_18]
0x18002d10d  xor     r9d, r9d
0x18002d110  mov     [rbp+var_20], rax
0x18002d114  xor     edx, edx; lpSubKey
0x18002d116  lea     rax, [rbp+var_28]
0x18002d11a  mov     rcx, rbx; hKey
0x18002d11d  mov     [rsp+68h+var_48], rax; int
0x18002d122  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x18002d127  mov     ebx, eax
0x18002d129  test    eax, eax
0x18002d12b  jns     short loc_18002D162
0x18002d12d  mov     edx, 0DFh; void *
0x18002d132  mov     rcx, [rbp+20h]; this
0x18002d136  lea     r8, aOnecoreWindows_3; "onecore\\windows\\feedback\\core\\commo"...
0x18002d13d  mov     r9d, ebx; char *
0x18002d140  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d145  mov     rcx, [rbp+var_28]; void *
0x18002d149  lea     rax, [rbp+var_18]
0x18002d14d  cmp     rcx, rax
0x18002d150  jz      short loc_18002D15E
0x18002d152  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002d159  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002d15e  mov     eax, ebx
0x18002d160  jmp     short loc_18002D1DF
0x18002d162  mov     r9, [rbp+var_28]
0x18002d166  lea     r8, [rdi+4]
0x18002d16a  mov     rcx, r9
0x18002d16d  mov     eax, 7FFFFFFEh
0x18002d172  mov     edx, 40h ; '@'
0x18002d177  test    rax, rax
0x18002d17a  jz      short loc_18002D19B
0x18002d17c  movzx   r10d, word ptr [rcx]
0x18002d180  test    r10w, r10w
0x18002d184  jz      short loc_18002D19B
0x18002d186  mov     [r8], r10w
0x18002d18a  add     rcx, 2
0x18002d18e  add     r8, 2
0x18002d192  dec     rax
0x18002d195  sub     rdx, 1
0x18002d199  jnz     short loc_18002D177
0x18002d19b  mov     rax, rdx
0x18002d19e  lea     rcx, [r8-2]
0x18002d1a2  neg     rax
0x18002d1a5  sbb     ebx, ebx
0x18002d1a7  not     ebx
0x18002d1a9  and     ebx, 8007007Ah
0x18002d1af  test    rdx, rdx
0x18002d1b2  cmovnz  rcx, r8
0x18002d1b6  mov     [rcx], si
0x18002d1b9  jnz     short loc_18002D1C5
0x18002d1bb  mov     edx, 0E1h
0x18002d1c0  jmp     loc_18002D132
0x18002d1c5  lea     rax, [rbp+var_18]
0x18002d1c9  cmp     r9, rax
0x18002d1cc  jz      short loc_18002D1DD
0x18002d1ce  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002d1d5  mov     rcx, r9; void *
0x18002d1d8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002d1dd  xor     eax, eax
0x18002d1df  add     rsp, 68h
0x18002d1e3  pop     rdi
0x18002d1e4  pop     rsi
0x18002d1e5  pop     rbx
0x18002d1e6  pop     rbp
0x18002d1e7  retn
```
