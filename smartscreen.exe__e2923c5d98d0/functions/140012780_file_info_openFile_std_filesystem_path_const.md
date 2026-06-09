# file_info::openFile(std::filesystem::path const &)

- ea: `0x140012780`
- end: `0x1400128be`
- name: `?openFile@file_info@@CA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBVpath@filesystem@std@@@Z`
- size: `318`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140032240`

## callees

- `0x140012780`
- `0x1400128c4`
- `0x140018a9c`
- `0x140018b58`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400127f4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400127f4`

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
0x140012780  mov     [rsp-8+arg_0], rcx
0x140012785  push    rbp
0x140012786  push    rbx
0x140012787  push    rsi
0x140012788  push    rdi
0x140012789  lea     rbp, [rsp-3Fh]
0x14001278e  sub     rsp, 98h
0x140012795  mov     rdi, rdx
0x140012798  mov     rsi, rcx
0x14001279b  xorps   xmm0, xmm0
0x14001279e  movups  xmmword ptr [rbp+57h+lpFileName], xmm0
0x1400127a2  xorps   xmm1, xmm1
0x1400127a5  movdqu  [rbp+57h+var_58], xmm1
0x1400127aa  cmp     qword ptr [rdx+18h], 7
0x1400127af  jbe     short loc_1400127B4
0x1400127b1  mov     rdx, [rdx]
0x1400127b4  mov     r8, [rdi+10h]
0x1400127b8  lea     rcx, [rbp+57h+lpFileName]
0x1400127bc  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x1400127c1  lea     rcx, [rbp+57h+lpFileName]
0x1400127c5  cmp     qword ptr [rbp+57h+var_58+8], 7
0x1400127ca  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x1400127cf  mov     [rsp+0B0h+hTemplateFile], 0; hTemplateFile
0x1400127d8  mov     [rsp+0B0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1400127e0  mov     [rsp+0B0h+dwCreationDisposition], 3; dwCreationDisposition
0x1400127e8  xor     r9d, r9d; lpSecurityAttributes
0x1400127eb  mov     edx, 80000000h; dwDesiredAccess
0x1400127f0  lea     r8d, [r9+7]; dwShareMode
0x1400127f4  call    cs:__imp_CreateFileW
0x1400127fa  mov     rbx, rax
0x1400127fd  mov     [rbp+57h+arg_0], rax
0x140012801  mov     rdx, qword ptr [rbp+57h+var_58+8]
0x140012805  cmp     rdx, 7
0x140012809  jbe     short loc_14001281C
0x14001280b  lea     rdx, ds:2[rdx*2]
0x140012813  mov     rcx, [rbp+57h+lpFileName]
0x140012817  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x14001281c  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x140012824  movdqu  [rbp+57h+var_58], xmm0
0x140012829  xor     eax, eax
0x14001282b  mov     word ptr [rbp+57h+lpFileName], ax
0x14001282f  xorps   xmm0, xmm0
0x140012832  movups  xmmword ptr [rbp+57h+var_48], xmm0
0x140012836  xorps   xmm1, xmm1
0x140012839  movdqu  [rbp+57h+var_38], xmm1
0x14001283e  mov     r8, [rdi+10h]
0x140012842  cmp     qword ptr [rdi+18h], 7
0x140012847  jbe     short loc_14001284C
0x140012849  mov     rdi, [rdi]
0x14001284c  mov     rdx, rdi
0x14001284f  lea     rcx, [rbp+57h+var_48]
0x140012853  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x140012858  nop
0x140012859  lea     rax, [rbp+57h+var_48]
0x14001285d  cmp     qword ptr [rbp+57h+var_38+8], 7
0x140012862  cmova   rax, [rbp+57h+var_48]
0x140012867  mov     rcx, [rbp+5Fh]; this
0x14001286b  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], rax; char *
0x140012870  lea     rax, aWs; "%ws"
0x140012877  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax; void *
0x14001287c  mov     r9, rbx; char *
0x14001287f  lea     r8, aOnecoreAmcoreS_9; "onecore\\amcore\\smartscreen\\src\\clie"...
0x140012886  mov     edx, 0EDh; void *
0x14001288b  call    ?Throw_IfHandleInvalidMsg@in1diag3@details@wil@@YAPEAXPEAXIPEBD01ZZ; wil::details::in1diag3::Throw_IfHandleInvalidMsg(void *,uint,char const *,void *,char const *,...)
0x140012890  nop
0x140012891  mov     rdx, qword ptr [rbp+57h+var_38+8]
0x140012895  cmp     rdx, 7
0x140012899  jbe     short loc_1400128AC
0x14001289b  lea     rdx, ds:2[rdx*2]
0x1400128a3  mov     rcx, [rbp+57h+var_48]
0x1400128a7  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1400128ac  mov     [rsi], rbx
0x1400128af  mov     rax, rsi
0x1400128b2  add     rsp, 98h
0x1400128b9  pop     rdi
0x1400128ba  pop     rsi
0x1400128bb  pop     rbx
0x1400128bc  pop     rbp
0x1400128bd  retn
```
