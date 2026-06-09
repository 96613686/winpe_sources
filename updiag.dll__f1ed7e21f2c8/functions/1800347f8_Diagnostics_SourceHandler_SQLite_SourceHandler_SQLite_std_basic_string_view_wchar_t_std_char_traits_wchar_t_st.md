# Diagnostics::SourceHandler_SQLite::SourceHandler_SQLite(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::filesystem::path const &)

- ea: `0x1800347f8`
- end: `0x180034941`
- name: `??0SourceHandler_SQLite@Diagnostics@@AEAA@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBVpath@filesystem@3@@Z`
- size: `329`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, const WCHAR *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180033d70`

## callees

- `0x18001544c`
- `0x180018b04`
- `0x180018e64`
- `0x180019080`
- `0x180034620`
- `0x1800347f8`
- `0x1800664ec`
- `0x18007a3e8`
- `0x18008fe00`

## import_xrefs

- `winsqlite3!sqlite3_errmsg` at `0x1800348f5`
- `winsqlite3!sqlite3_errmsg` at `0x1800348f5`
- `winsqlite3!sqlite3_initialize` at `0x1800348b0`
- `winsqlite3!sqlite3_initialize` at `0x1800348b0`
- `winsqlite3!sqlite3_open16` at `0x1800348c7`
- `winsqlite3!sqlite3_open16` at `0x1800348c7`

## string_xrefs

- `0x18003490e`: `Failed to open SQLite database`
- `0x180034934`: `last_write_time`

## pseudocode

```c
_QWORD *__fastcall Diagnostics::SourceHandler_SQLite::SourceHandler_SQLite(_QWORD *a1, __int64 a2, const WCHAR *a3)
{
  _QWORD *v5; // rcx
  const WCHAR *v6; // rcx
  unsigned int stats; // eax
  unsigned int v8; // ebx
  __int64 v10; // rax
  const char *v11; // [rsp+28h] [rbp-50h]
  _QWORD v12[2]; // [rsp+30h] [rbp-48h] BYREF
  _OWORD v13[2]; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v12[1] = a1;
  *a1 = &Diagnostics::SourceHandler_SQLite::`vftable';
  v5 = a1 + 1;
  *(_OWORD *)v5 = 0;
  v5[2] = 0;
  v5[3] = 0;
  std::wstring::_Construct<1,wchar_t const *>(v5, *(const void **)a2, *(_QWORD *)(a2 + 8));
  std::wstring::wstring((__int64)(a1 + 5), (__int64)a3);
  a1[9] = 0;
  memset(v13, 0, sizeof(v13));
  v6 = a3;
  if ( *((_QWORD *)a3 + 3) > 7u )
    v6 = *(const WCHAR **)a3;
  stats = _std_fs_get_stats(v6);
  if ( stats )
    std::filesystem::_Throw_fs_error("last_write_time", stats, a3);
  v12[0] = *(_QWORD *)&v13[0];
  std::chrono::clock_cast<std::chrono::system_clock,std::filesystem::_File_time_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>(
    a1 + 10,
    v12);
  sqlite3_initialize();
  if ( *((_QWORD *)a3 + 3) > 7u )
    a3 = *(const WCHAR **)a3;
  v8 = sqlite3_open16(a3, a1 + 9);
  if ( v8 )
  {
    v10 = sqlite3_errmsg(a1[9]);
    std::string::string(v13, v10);
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0xAB,
      (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\SourceHandler_SQLite.hpp",
      (const char *)v8,
      (unsigned int)"Failed to open SQLite database",
      v11);
  }
  return a1;
}

```

## disassembly

```asm
0x1800347f8  mov     [rsp+arg_18], rbx
0x1800347fd  push    rdi
0x1800347fe  sub     rsp, 70h
0x180034802  mov     rax, cs:__security_cookie
0x180034809  xor     rax, rsp
0x18003480c  mov     [rsp+78h+var_18], rax
0x180034811  mov     rbx, r8
0x180034814  mov     rdi, rcx
0x180034817  mov     [rsp+78h+var_40], rcx
0x18003481c  lea     rax, ??_7SourceHandler_SQLite@Diagnostics@@6B@; const Diagnostics::SourceHandler_SQLite::`vftable'
0x180034823  mov     [rcx], rax
0x180034826  add     rcx, 8
0x18003482a  xorps   xmm0, xmm0
0x18003482d  movups  xmmword ptr [rcx], xmm0
0x180034830  mov     qword ptr [rcx+10h], 0
0x180034838  mov     qword ptr [rcx+18h], 0
0x180034840  mov     r8, [rdx+8]
0x180034844  mov     rdx, [rdx]
0x180034847  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18003484c  nop
0x18003484d  lea     rcx, [rdi+28h]
0x180034851  mov     rdx, rbx
0x180034854  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180034859  nop
0x18003485a  mov     qword ptr [rdi+48h], 0
0x180034862  xorps   xmm0, xmm0
0x180034865  movups  [rsp+78h+var_38], xmm0
0x18003486a  movups  [rsp+78h+var_28], xmm0
0x18003486f  mov     rcx, rbx
0x180034872  cmp     qword ptr [rbx+18h], 7
0x180034877  jbe     short loc_18003487C
0x180034879  mov     rcx, [rbx]; lpFileName
0x18003487c  or      r9d, 0FFFFFFFFh
0x180034880  mov     r8d, 21h ; '!'
0x180034886  lea     rdx, [rsp+78h+var_38]
0x18003488b  call    __std_fs_get_stats
0x180034890  test    eax, eax
0x180034892  jnz     loc_18003492F
0x180034898  mov     rax, qword ptr [rsp+78h+var_38]
0x18003489d  mov     [rsp+78h+var_48], rax
0x1800348a2  lea     rcx, [rdi+50h]
0x1800348a6  lea     rdx, [rsp+78h+var_48]
0x1800348ab  call    ??$clock_cast@Usystem_clock@chrono@std@@U_File_time_clock@filesystem@3@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@YA?A_PAEBV?$time_point@U_File_time_clock@filesystem@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@3@@01@@Z
0x1800348b0  call    cs:__imp_sqlite3_initialize
0x1800348b6  cmp     qword ptr [rbx+18h], 7
0x1800348bb  jbe     short loc_1800348C0
0x1800348bd  mov     rbx, [rbx]
0x1800348c0  lea     rdx, [rdi+48h]
0x1800348c4  mov     rcx, rbx
0x1800348c7  call    cs:__imp_sqlite3_open16
0x1800348cd  mov     ebx, eax
0x1800348cf  test    eax, eax
0x1800348d1  jnz     short loc_1800348F1
0x1800348d3  mov     rax, rdi
0x1800348d6  mov     rcx, [rsp+78h+var_18]
0x1800348db  xor     rcx, rsp; StackCookie
0x1800348de  call    __security_check_cookie
0x1800348e3  mov     rbx, [rsp+78h+arg_18]
0x1800348eb  add     rsp, 70h
0x1800348ef  pop     rdi
0x1800348f0  retn
0x1800348f1  mov     rcx, [rdi+48h]
0x1800348f5  call    cs:__imp_sqlite3_errmsg
0x1800348fb  mov     rdx, rax
0x1800348fe  lea     rcx, [rsp+78h+var_38]
0x180034903  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180034908  nop
0x180034909  mov     rcx, [rsp+78h]; this
0x18003490e  lea     rax, aFailedToOpenSq; "Failed to open SQLite database"
0x180034915  mov     qword ptr [rsp+78h+var_58], rax; unsigned int
0x18003491a  mov     r9d, ebx; char *
0x18003491d  lea     r8, aCW1SSrcCalliop_4; "C:\\__w\\1\\s\\src\\Calliope\\libs\\dia"...
0x180034924  mov     edx, 0ABh; void *
0x180034929  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18003492f  mov     r8, rbx
0x180034932  mov     edx, eax
0x180034934  lea     rcx, aLastWriteTime; "last_write_time"
0x18003493b  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDW4__std_win_error@@AEBVpath@12@@Z; std::filesystem::_Throw_fs_error(char const *,__std_win_error,std::filesystem::path const &)
```
