# file_info::openFile(std::filesystem::path const &)

- ea: `0x14001317c`
- end: `0x1400132c1`
- name: `?openFile@file_info@@CA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBVpath@filesystem@std@@@Z`
- size: `325`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14003369c`

## callees

- `0x14001317c`
- `0x1400132c8`
- `0x140019784`
- `0x140019844`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400131f0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400131f0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
const char **__fastcall file_info::openFile(const char **a1, _QWORD *a2)
{
  _QWORD *v2; // rdi
  const WCHAR *v4; // rcx
  const char *FileW; // rbx
  __int64 v6; // r8
  const char *v7; // rax
  LPCWSTR lpFileName[2]; // [rsp+48h] [rbp-11h] BYREF
  __m128i si128; // [rsp+58h] [rbp-1h]
  char *v11[2]; // [rsp+68h] [rbp+Fh] BYREF
  __int128 v12; // [rsp+78h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v2 = a2;
  *(_OWORD *)lpFileName = 0;
  si128 = 0;
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  std::wstring::_Construct<2,unsigned short const *>(lpFileName, a2, v2[2]);
  v4 = (const WCHAR *)lpFileName;
  if ( si128.m128i_i64[1] > 7uLL )
    v4 = lpFileName[0];
  FileW = (const char *)CreateFileW(v4, 0x80000000, 7u, 0, 3u, 0x80u, 0);
  if ( si128.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(lpFileName[0], 2 * si128.m128i_i64[1] + 2);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpFileName[0]) = 0;
  *(_OWORD *)v11 = 0;
  v12 = 0;
  v6 = v2[2];
  if ( v2[3] > 7u )
    v2 = (_QWORD *)*v2;
  std::wstring::_Construct<2,unsigned short const *>(v11, v2, v6);
  v7 = (const char *)v11;
  if ( *((_QWORD *)&v12 + 1) > 7u )
    v7 = v11[0];
  wil::details::in1diag3::Throw_IfHandleInvalidMsg(
    retaddr,
    (void *)0xED,
    (unsigned int)"onecore\\amcore\\smartscreen\\src\\client\\helpers\\utilities.h",
    FileW,
    "%ws",
    v7);
  if ( *((_QWORD *)&v12 + 1) > 7u )
    std::_Deallocate<16>(v11[0], 2LL * *((_QWORD *)&v12 + 1) + 2);
  *a1 = FileW;
  return a1;
}

```

## disassembly

```asm
0x14001317c  mov     [rsp-8+arg_0], rcx
0x140013181  push    rbp
0x140013182  push    rbx
0x140013183  push    rsi
0x140013184  push    rdi
0x140013185  lea     rbp, [rsp-3Fh]
0x14001318a  sub     rsp, 98h
0x140013191  mov     rdi, rdx
0x140013194  mov     rsi, rcx
0x140013197  xorps   xmm0, xmm0
0x14001319a  movups  xmmword ptr [rbp+57h+lpFileName], xmm0
0x14001319e  xorps   xmm1, xmm1
0x1400131a1  movdqu  [rbp+57h+var_58], xmm1
0x1400131a6  cmp     qword ptr [rdx+18h], 7
0x1400131ab  jbe     short loc_1400131B0
0x1400131ad  mov     rdx, [rdx]
0x1400131b0  mov     r8, [rdi+10h]
0x1400131b4  lea     rcx, [rbp+57h+lpFileName]
0x1400131b8  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x1400131bd  lea     rcx, [rbp+57h+lpFileName]
0x1400131c1  cmp     qword ptr [rbp+57h+var_58+8], 7
0x1400131c6  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x1400131cb  mov     [rsp+0B0h+hTemplateFile], 0; hTemplateFile
0x1400131d4  mov     [rsp+0B0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1400131dc  mov     [rsp+0B0h+dwCreationDisposition], 3; dwCreationDisposition
0x1400131e4  xor     r9d, r9d; lpSecurityAttributes
0x1400131e7  mov     edx, 80000000h; dwDesiredAccess
0x1400131ec  lea     r8d, [r9+7]; dwShareMode
0x1400131f0  call    cs:__imp_CreateFileW
0x1400131f7  nop     dword ptr [rax+rax+00h]
0x1400131fc  mov     rbx, rax
0x1400131ff  mov     [rbp+57h+arg_0], rax
0x140013203  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x140013207  cmp     rdx, 7
0x14001320b  jbe     short loc_14001321E
0x14001320d  lea     rdx, ds:2[rdx*2]
0x140013215  mov     rcx, [rbp+57h+lpFileName]
0x140013219  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x14001321e  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x140013226  movdqu  [rbp+57h+var_58], xmm0
0x14001322b  xor     eax, eax
0x14001322d  mov     word ptr [rbp+57h+lpFileName], ax
0x140013231  xorps   xmm0, xmm0
0x140013234  movups  xmmword ptr [rbp+57h+var_48], xmm0
0x140013238  xorps   xmm1, xmm1
0x14001323b  movdqu  [rbp+57h+var_38], xmm1
0x140013240  mov     r8, [rdi+10h]
0x140013244  cmp     qword ptr [rdi+18h], 7
0x140013249  jbe     short loc_14001324E
0x14001324b  mov     rdi, [rdi]
0x14001324e  mov     rdx, rdi
0x140013251  lea     rcx, [rbp+57h+var_48]
0x140013255  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x14001325a  nop
0x14001325b  lea     rax, [rbp+57h+var_48]
0x14001325f  cmp     qword ptr [rbp+57h+var_38+8], 7
0x140013264  cmova   rax, [rbp+57h+var_48]
0x140013269  mov     rcx, [rbp+5Fh]; this
0x14001326d  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], rax; char *
0x140013272  lea     rax, aWs; "%ws"
0x140013279  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax; void *
0x14001327e  mov     r9, rbx; char *
0x140013281  lea     r8, aOnecoreAmcoreS_9; "onecore\\amcore\\smartscreen\\src\\clie"...
0x140013288  mov     edx, 0EDh; void *
0x14001328d  call    ?Throw_IfHandleInvalidMsg@in1diag3@details@wil@@YAPEAXPEAXIPEBD01ZZ; wil::details::in1diag3::Throw_IfHandleInvalidMsg(void *,uint,char const *,void *,char const *,...)
0x140013292  nop
0x140013293  mov     rdx, qword ptr [rbp+57h+var_38+8]
0x140013297  cmp     rdx, 7
0x14001329b  jbe     short loc_1400132AE
0x14001329d  lea     rdx, ds:2[rdx*2]
0x1400132a5  mov     rcx, [rbp+57h+var_48]
0x1400132a9  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1400132ae  mov     [rsi], rbx
0x1400132b1  mov     rax, rsi
0x1400132b4  add     rsp, 98h
0x1400132bb  pop     rdi
0x1400132bc  pop     rsi
0x1400132bd  pop     rbx
0x1400132be  pop     rbp
0x1400132bf  retn
```
