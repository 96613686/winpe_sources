# Diagnostics::OTelFile::AppendLogRecord(Diagnostics::OTelLogRecord const &)

- ea: `0x18002da90`
- end: `0x18002dce7`
- name: `?AppendLogRecord@OTelFile@Diagnostics@@QEAAXAEBVOTelLogRecord@2@@Z`
- size: `599`
- prototype: `void __fastcall(Diagnostics::OTelFile *__hidden this, const struct Diagnostics::OTelLogRecord *)`
- caller_count: `16`
- callee_count: `19`
- tags: `registry_config`

## callers

- `0x18002e380`
- `0x180031aa0`
- `0x180033e10`
- `0x1800425d0`
- `0x180043340`
- `0x1800434a0`
- `0x180043d60`
- `0x180043ec0`
- `0x180044c10`
- `0x180044d70`
- `0x180045cb0`
- `0x180045e10`
- `0x180049d5c`
- `0x1800602d0`
- `0x180069510`
- `0x180069b90`

## callees

- `0x180008a2c`
- `0x1800106e8`
- `0x180011be4`
- `0x180016ce4`
- `0x18001815c`
- `0x180018bec`
- `0x180018e64`
- `0x180018eec`
- `0x1800295f0`
- `0x18002964c`
- `0x18002a854`
- `0x18002da90`
- `0x18002de8c`
- `0x18003b3bc`
- `0x180068298`
- `0x1800682a4`
- `0x18008fa9b`
- `0x18008fe00`
- `0x1800961f0`

## string_xrefs

- `0x18002dc38`: `Attempted to write to log file that was unable to be opened for write`
- `0x18002dc0d`: `Failed to write log record to file: %ls (state=0x%x, bad=%d, eof=%d, errno=%d: %S, data=%ls)`
- `0x18002dcc9`: `Attempted to append log record with timestamp %ls earlier than the last appended record %ls`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Diagnostics::OTelFile::AppendLogRecord(
        Diagnostics::OTelFile *this,
        const struct Diagnostics::OTelLogRecord *a2)
{
  __int64 LastRecordTimestamp; // rax
  __int64 v5; // rbx
  _QWORD *v6; // rdx
  __int64 v7; // rax
  unsigned int v8; // r14d
  int v9; // esi
  std::ios_base *v10; // rcx
  BOOL v11; // edi
  std::ios_base *v12; // rcx
  BOOL v13; // ebx
  const char *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rax
  unsigned int v18; // eax
  const char *v19; // rdx
  __int64 v20; // r8
  char *v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+30h] [rbp-D0h]
  BOOL v23; // [rsp+38h] [rbp-C8h]
  BOOL v24; // [rsp+40h] [rbp-C0h]
  int v25; // [rsp+48h] [rbp-B8h]
  _BYTE v26[8]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v27[8]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v28[4]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v29[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v30[32]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v31[256]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  if ( *((_BYTE *)this + 320) )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x85,
      (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\OTelFile.hpp",
      (const char *)0x1D,
      (unsigned int)"Attempted to write to log file that was unable to be opened for write",
      v21);
  LastRecordTimestamp = *((_QWORD *)this + 84);
  if ( !LastRecordTimestamp )
  {
    LastRecordTimestamp = Diagnostics::OTelFile::ReadLastRecordTimestamp(this);
    *((_QWORD *)this + 84) = LastRecordTimestamp;
  }
  v5 = 100LL * *((_QWORD *)a2 + 16);
  if ( v5 < LastRecordTimestamp )
  {
    v16 = System::Convert::ToTimePointFromNanos(v26, 100LL * *((_QWORD *)a2 + 16));
    Diagnostics::DataStyles::TimePoint(v30, v16);
    v17 = System::Convert::ToTimePointFromNanos(v27, *((_QWORD *)this + 84));
    Diagnostics::DataStyles::TimePoint(v29, v17);
    std::wstring::c_str(v29);
    std::wstring::c_str(v30);
    v18 = wil::verify_hresult<long>(2151677952LL);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x95,
      (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\OTelFile.hpp",
      (const char *)v18,
      (int)"Attempted to append log record with timestamp %ls earlier than the last appended record %ls",
      v19,
      v20);
  }
  Diagnostics::OTelLogRecord::ToJsonLine(a2, v28);
  v6 = v28;
  if ( v28[3] > 7u )
    v6 = (_QWORD *)v28[0];
  v7 = std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>((__int64)this + 56, (__int64)v6, v28[2]);
  std::operator<<<wchar_t,std::char_traits<wchar_t>>(v7, (__int64)L"\n");
  if ( (*((_BYTE *)this + *(int *)(*((_QWORD *)this + 5) + 4LL) + 56) & 6) != 0 )
  {
    v8 = *(_DWORD *)o__errno_0();
    v9 = std::ios_base::rdstate((Diagnostics::OTelFile *)((char *)this + *(int *)(*((_QWORD *)this + 5) + 4LL) + 40));
    v11 = std::ios_base::bad(v10);
    v13 = std::ios_base::eof(v12);
    memset(v31, 0, sizeof(v31));
    strerror_s<256>(v31, v8);
    std::wstring::c_str(v28);
    v14 = (const char *)std::wstring::c_str((char *)this + 8);
    v25 = v8;
    v24 = v13;
    v23 = v11;
    v22 = v9;
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0xA7,
      (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\OTelFile.hpp",
      (const char *)0x1D,
      (unsigned int)"Failed to write log record to file: %ls (state=0x%x, bad=%d, eof=%d, errno=%d: %S, data=%ls)",
      v14,
      v22,
      v23,
      v24,
      v25,
      v31,
      v15);
  }
  *((_QWORD *)this + 84) = v5;
  ++*((_DWORD *)this + 174);
  std::wstring::~wstring((__int64)v28);
}

```

## disassembly

```asm
0x18002da90  mov     [rsp-8+arg_10], rbx
0x18002da95  push    rbp
0x18002da96  push    rsi
0x18002da97  push    rdi
0x18002da98  push    r14
0x18002da9a  push    r15
0x18002da9c  lea     rbp, [rsp-0E0h]
0x18002daa4  sub     rsp, 1E0h
0x18002daab  mov     rax, cs:__security_cookie
0x18002dab2  xor     rax, rsp
0x18002dab5  mov     [rbp+100h+var_30], rax
0x18002dabc  mov     rdi, rdx
0x18002dabf  mov     r15, rcx
0x18002dac2  cmp     byte ptr [rcx+140h], 0
0x18002dac9  jnz     loc_18002DC31
0x18002dacf  mov     rax, [rcx+2A0h]
0x18002dad6  test    rax, rax
0x18002dad9  jnz     short loc_18002DAE7
0x18002dadb  call    ?ReadLastRecordTimestamp@OTelFile@Diagnostics@@AEAA_JXZ; Diagnostics::OTelFile::ReadLastRecordTimestamp(void)
0x18002dae0  mov     [r15+2A0h], rax
0x18002dae7  imul    rbx, [rdi+80h], 64h ; 'd'
0x18002daef  cmp     rbx, rax
0x18002daf2  jl      loc_18002DC5B
0x18002daf8  lea     rdx, [rsp+200h+var_190]
0x18002dafd  mov     rcx, rdi
0x18002db00  call    ?ToJsonLine@OTelLogRecord@Diagnostics@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Diagnostics::OTelLogRecord::ToJsonLine(void)
0x18002db05  nop
0x18002db06  lea     rdx, [rsp+200h+var_190]
0x18002db0b  cmp     [rbp+100h+var_178], 7
0x18002db10  cmova   rdx, [rsp+200h+var_190]
0x18002db16  lea     rcx, [r15+38h]
0x18002db1a  mov     r8, [rbp+100h+var_180]
0x18002db1e  call    ??$_Insert_string@_WU?$char_traits@_W@std@@_K@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@QEB_W_K@Z; std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(std::wostream &,wchar_t const * const,unsigned __int64)
0x18002db23  lea     rdx, asc_1800A2C80; "\n"
0x18002db2a  mov     rcx, rax
0x18002db2d  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x18002db32  mov     rax, [r15+28h]
0x18002db36  movsxd  rcx, dword ptr [rax+4]
0x18002db3a  test    byte ptr [rcx+r15+38h], 6
0x18002db40  jnz     short loc_18002DB80
0x18002db42  mov     [r15+2A0h], rbx
0x18002db49  inc     dword ptr [r15+2B8h]
0x18002db50  lea     rcx, [rsp+200h+var_190]
0x18002db55  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002db5a  mov     rcx, [rbp+100h+var_30]
0x18002db61  xor     rcx, rsp; StackCookie
0x18002db64  call    __security_check_cookie
0x18002db69  mov     rbx, [rsp+200h+arg_10]
0x18002db71  add     rsp, 1E0h
0x18002db78  pop     r15
0x18002db7a  pop     r14
0x18002db7c  pop     rdi
0x18002db7d  pop     rsi
0x18002db7e  pop     rbp
0x18002db7f  retn
0x18002db80  call    _o__errno_0
0x18002db85  nop
0x18002db86  mov     r14d, [rax]
0x18002db89  mov     rax, [r15+28h]
0x18002db8d  movsxd  rcx, dword ptr [rax+4]
0x18002db91  add     rcx, 28h ; '('
0x18002db95  add     rcx, r15; this
0x18002db98  call    ?rdstate@ios_base@std@@QEBAHXZ; std::ios_base::rdstate(void)
0x18002db9d  mov     esi, eax
0x18002db9f  call    ?bad@ios_base@std@@QEBA_NXZ; std::ios_base::bad(void)
0x18002dba4  movzx   edi, al
0x18002dba7  call    ?eof@ios_base@std@@QEBA_NXZ; std::ios_base::eof(void)
0x18002dbac  movzx   ebx, al
0x18002dbaf  xor     edx, edx; Val
0x18002dbb1  mov     r8d, 100h; Size
0x18002dbb7  lea     rcx, [rbp+100h+var_130]; void *
0x18002dbbb  call    memset
0x18002dbc0  mov     edx, r14d
0x18002dbc3  lea     rcx, [rbp+100h+var_130]
0x18002dbc7  call    ??$strerror_s@$0BAA@@@YAHAEAY0BAA@DH@Z; strerror_s<256>(char (&)[256],int)
0x18002dbcc  lea     rcx, [rsp+200h+var_190]
0x18002dbd1  call    ?c_str@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAPEB_WXZ; std::wstring::c_str(void)
0x18002dbd6  mov     rdx, rax
0x18002dbd9  lea     rcx, [r15+8]
0x18002dbdd  call    ?c_str@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAPEB_WXZ; std::wstring::c_str(void)
0x18002dbe2  mov     rcx, [rbp+108h]; this
0x18002dbe9  mov     [rsp+200h+var_1A8], rdx
0x18002dbee  lea     rdx, [rbp+100h+var_130]
0x18002dbf2  mov     [rsp+200h+var_1B0], rdx
0x18002dbf7  mov     [rsp+200h+var_1B8], r14d
0x18002dbfc  mov     [rsp+200h+var_1C0], ebx
0x18002dc00  mov     [rsp+200h+var_1C8], edi
0x18002dc04  mov     dword ptr [rsp+200h+var_1D0], esi
0x18002dc08  mov     [rsp+200h+var_1D8], rax; char *
0x18002dc0d  lea     rax, aFailedToWriteL; "Failed to write log record to file: %ls"...
0x18002dc14  mov     qword ptr [rsp+200h+var_1E0], rax; unsigned int
0x18002dc19  mov     r9d, 1Dh; char *
0x18002dc1f  lea     r8, aCW1SSrcCalliop_11; "C:\\__w\\1\\s\\src\\Calliope\\libs\\dia"...
0x18002dc26  mov     edx, 0A7h; void *
0x18002dc2b  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002dc31  mov     rcx, [rbp+108h]; this
0x18002dc38  lea     rax, aAttemptedToWri; "Attempted to write to log file that was"...
0x18002dc3f  mov     qword ptr [rsp+200h+var_1E0], rax; unsigned int
0x18002dc44  mov     r9d, 1Dh; char *
0x18002dc4a  lea     r8, aCW1SSrcCalliop_11; "C:\\__w\\1\\s\\src\\Calliope\\libs\\dia"...
0x18002dc51  lea     edx, [r9+68h]; void *
0x18002dc55  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18002dc5b  mov     rdx, rbx
0x18002dc5e  lea     rcx, [rsp+200h+var_1A0]
0x18002dc63  call    ?ToTimePointFromNanos@Convert@System@@SA?AV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@_J@Z; System::Convert::ToTimePointFromNanos(__int64)
0x18002dc68  mov     rdx, rax
0x18002dc6b  lea     rcx, [rbp+100h+var_150]
0x18002dc6f  call    ?TimePoint@DataStyles@Diagnostics@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@4@@Z; Diagnostics::DataStyles::TimePoint(std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x18002dc74  nop
0x18002dc75  mov     rdx, [r15+2A0h]
0x18002dc7c  lea     rcx, [rsp+200h+var_198]
0x18002dc81  call    ?ToTimePointFromNanos@Convert@System@@SA?AV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@_J@Z; System::Convert::ToTimePointFromNanos(__int64)
0x18002dc86  mov     rdx, rax
0x18002dc89  lea     rcx, [rbp+100h+var_170]
0x18002dc8d  call    ?TimePoint@DataStyles@Diagnostics@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@4@@Z; Diagnostics::DataStyles::TimePoint(std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x18002dc92  nop
0x18002dc93  lea     rcx, [rbp+100h+var_170]
0x18002dc97  call    ?c_str@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAPEB_WXZ; std::wstring::c_str(void)
0x18002dc9c  mov     r8, rax
0x18002dc9f  lea     rcx, [rbp+100h+var_150]
0x18002dca3  call    ?c_str@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAPEB_WXZ; std::wstring::c_str(void)
0x18002dca8  mov     rdx, rax
0x18002dcab  mov     ecx, 80400000h
0x18002dcb0  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002dcb5  mov     r9d, eax; char *
0x18002dcb8  mov     rcx, [rbp+108h]; this
0x18002dcbf  mov     [rsp+200h+var_1D0], r8
0x18002dcc4  mov     [rsp+200h+var_1D8], rdx; char *
0x18002dcc9  lea     rax, aAttemptedToApp; "Attempted to append log record with tim"...
0x18002dcd0  mov     qword ptr [rsp+200h+var_1E0], rax; int
0x18002dcd5  lea     r8, aCW1SSrcCalliop_11; "C:\\__w\\1\\s\\src\\Calliope\\libs\\dia"...
0x18002dcdc  mov     edx, 95h; void *
0x18002dce1  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
