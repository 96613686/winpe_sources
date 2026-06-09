# CLI::App::_process_config_file(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,bool)

- ea: `0x140024db0`
- end: `0x140024fa0`
- name: `?_process_config_file@App@CLI@@IEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N@Z`
- size: `496`
- prototype: `__int64 __fastcall(CLI::App *this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x140024fb0`

## callees

- `0x140008a50`
- `0x14000f7e0`
- `0x140010668`
- `0x140015db0`
- `0x14001a5b0`
- `0x14001a6d0`
- `0x14001ceb0`
- `0x140022ef0`
- `0x140024db0`
- `0x140067010`

## import_xrefs

- `msvcp_win!?good@ios_base@std@@QEBA_NXZ` at `0x140024e84`
- `msvcp_win!?good@ios_base@std@@QEBA_NXZ` at `0x140024e84`
- `msvcp_win!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x140024eec`
- `msvcp_win!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x140024eec`
- `msvcp_win!??1?$basic_istream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x140024ede`
- `msvcp_win!??1?$basic_istream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x140024ede`
- `api-ms-win-crt-private-l1-1-0!_o__stat64` at `0x140024df6`
- `api-ms-win-crt-private-l1-1-0!_o__stat64` at `0x140024df6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CLI::App::_process_config_file(CLI::App *this, _QWORD *a2, char a3)
{
  _QWORD *v6; // rcx
  __int64 result; // rax
  __int64 v8; // rdi
  _QWORD *v9; // rax
  _QWORD *v10; // rax
  _BYTE v11[24]; // [rsp+38h] [rbp-210h] BYREF
  _QWORD v12[2]; // [rsp+50h] [rbp-1F8h] BYREF
  _BYTE v13[8]; // [rsp+60h] [rbp-1E8h] BYREF
  _BYTE v14[152]; // [rsp+68h] [rbp-1E0h] BYREF
  _BYTE v15[96]; // [rsp+100h] [rbp-148h] BYREF
  _BYTE v16[6]; // [rsp+160h] [rbp-E8h] BYREF
  __int16 v17; // [rsp+166h] [rbp-E2h]
  _BYTE v18[64]; // [rsp+1A0h] [rbp-A8h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+1E0h] [rbp-68h] BYREF

  v6 = a2;
  if ( a2[3] > 0xFu )
    v6 = (_QWORD *)*a2;
  result = _o__stat64(v6, v16);
  if ( (_DWORD)result || (result = 0x4000, (v17 & 0x4000) != 0) )
  {
    if ( a3 )
    {
      v9 = (_QWORD *)std::string::string(v16, a2);
      CLI::FileError::Missing((__int64)pExceptionObject, v9);
      throw (CLI::FileError *)pExceptionObject;
    }
  }
  else
  {
    v8 = *((_QWORD *)this + 114);
    try
    {
      std::ifstream::ifstream(v12);
      *(_QWORD *)((char *)v12 + *(int *)(v12[0] + 4LL)) = &std::ifstream::`vftable';
      *(_DWORD *)&v11[*(int *)(v12[0] + 4LL) + 20] = *(_DWORD *)(v12[0] + 4LL) - 176;
      if ( !std::ios_base::good((std::ios_base *)((char *)v12 + *(int *)(v12[0] + 4LL))) )
      {
        v10 = (_QWORD *)std::string::string(v16, a2);
        CLI::FileError::Missing((__int64)v18, v10);
        throw (CLI::FileError *)v18;
      }
      (*(void (__fastcall **)(__int64, _BYTE *, _QWORD *))(*(_QWORD *)v8 + 8LL))(v8, v11, v12);
      *(_QWORD *)((char *)v12 + *(int *)(v12[0] + 4LL)) = &std::ifstream::`vftable';
      *(_DWORD *)&v11[*(int *)(v12[0] + 4LL) + 20] = *(_DWORD *)(v12[0] + 4LL) - 176;
      std::filebuf::~filebuf<char,std::char_traits<char>>(v13);
      std::istream::~istream<char,std::char_traits<char>>(v14);
      std::ios::~ios<char,std::char_traits<char>>(v15);
      CLI::App::_parse_config(this);
      result = std::vector<CLI::ConfigItem>::~vector<CLI::ConfigItem>(v11);
    }
    catch ( CLI::FileError )
    {
      if ( a3 )
        throw;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140024db0  mov     [rsp+arg_18], rbx
0x140024db5  mov     [rsp+arg_10], r8b
0x140024dba  push    rsi
0x140024dbb  push    rdi
0x140024dbc  push    r14
0x140024dbe  sub     rsp, 230h
0x140024dc5  mov     rax, cs:__security_cookie
0x140024dcc  xor     rax, rsp
0x140024dcf  mov     [rsp+248h+var_28], rax
0x140024dd7  movzx   edi, r8b
0x140024ddb  mov     rbx, rdx
0x140024dde  mov     rsi, rcx
0x140024de1  mov     rcx, rdx
0x140024de4  cmp     qword ptr [rdx+18h], 0Fh
0x140024de9  jbe     short loc_140024DEE
0x140024deb  mov     rcx, [rdx]
0x140024dee  lea     rdx, [rsp+248h+var_E8]
0x140024df6  call    cs:__imp__o__stat64
0x140024dfc  test    eax, eax
0x140024dfe  jnz     loc_140024F30
0x140024e04  mov     eax, 4000h
0x140024e09  test    [rsp+248h+var_E2], ax
0x140024e11  jnz     loc_140024F30
0x140024e17  mov     rdi, [rsi+390h]
0x140024e1e  cmp     qword ptr [rbx+18h], 0Fh
0x140024e23  jbe     short loc_140024E2A
0x140024e25  mov     rdx, [rbx]
0x140024e28  jmp     short loc_140024E2D
0x140024e2a  mov     rdx, rbx
0x140024e2d  mov     [rsp+248h+var_228], 1
0x140024e35  mov     r9d, 40h ; '@'
0x140024e3b  mov     r8d, 1
0x140024e41  lea     rcx, [rsp+248h+var_1F8]
0x140024e46  call    ??0?$basic_ifstream@DU?$char_traits@D@std@@@std@@QEAA@PEBDHH@Z; std::ifstream::ifstream(char const *,int,int)
0x140024e4b  mov     rax, [rsp+248h+var_1F8]
0x140024e50  movsxd  rcx, dword ptr [rax+4]
0x140024e54  lea     r14, ??_7?$basic_ifstream@DU?$char_traits@D@std@@@std@@6B@; const std::ifstream::`vftable'
0x140024e5b  mov     [rsp+rcx+248h+var_1F8], r14
0x140024e60  mov     rax, [rsp+248h+var_1F8]
0x140024e65  movsxd  rcx, dword ptr [rax+4]
0x140024e69  lea     edx, [rcx-0B0h]
0x140024e6f  mov     [rsp+rcx+248h+var_1FC], edx
0x140024e73  mov     rax, [rsp+248h+var_1F8]
0x140024e78  movsxd  rcx, dword ptr [rax+4]
0x140024e7c  lea     rax, [rsp+248h+var_1F8]
0x140024e81  add     rcx, rax
0x140024e84  call    cs:__imp_?good@ios_base@std@@QEBA_NXZ; std::ios_base::good(void)
0x140024e8a  test    al, al
0x140024e8c  jz      loc_140024F6A
0x140024e92  mov     rax, [rdi]
0x140024e95  lea     r8, [rsp+248h+var_1F8]
0x140024e9a  lea     rdx, [rsp+248h+var_210]
0x140024e9f  mov     rcx, rdi
0x140024ea2  mov     rax, [rax+8]
0x140024ea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024eab  nop
0x140024eac  mov     rax, [rsp+248h+var_1F8]
0x140024eb1  movsxd  rcx, dword ptr [rax+4]
0x140024eb5  mov     [rsp+rcx+248h+var_1F8], r14
0x140024eba  mov     rax, [rsp+248h+var_1F8]
0x140024ebf  movsxd  rdx, dword ptr [rax+4]
0x140024ec3  lea     r8d, [rdx-0B0h]
0x140024eca  mov     [rsp+rdx+248h+var_1FC], r8d
0x140024ecf  lea     rcx, [rsp+248h+var_1E8]
0x140024ed4  call    ??1?$basic_filebuf@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::filebuf::~filebuf<char,std::char_traits<char>>(void)
0x140024ed9  lea     rcx, [rsp+248h+var_1E0]
0x140024ede  call    cs:__imp_??1?$basic_istream@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::istream::~istream<char,std::char_traits<char>>(void)
0x140024ee4  lea     rcx, [rsp+248h+var_148]
0x140024eec  call    cs:__imp_??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::ios::~ios<char,std::char_traits<char>>(void)
0x140024ef2  nop
0x140024ef3  lea     rdx, [rsp+248h+var_210]
0x140024ef8  mov     rcx, rsi; this
0x140024efb  call    ?_parse_config@App@CLI@@IEAAXAEBV?$vector@UConfigItem@CLI@@V?$allocator@UConfigItem@CLI@@@std@@@std@@@Z; CLI::App::_parse_config(std::vector<CLI::ConfigItem> const &)
0x140024f00  nop
0x140024f01  lea     rcx, [rsp+248h+var_210]
0x140024f06  call    ??1?$vector@UConfigItem@CLI@@V?$allocator@UConfigItem@CLI@@@std@@@std@@QEAA@XZ; std::vector<CLI::ConfigItem>::~vector<CLI::ConfigItem>(void)
0x140024f0b  nop
0x140024f0c  mov     rcx, [rsp+248h+var_28]
0x140024f14  xor     rcx, rsp; StackCookie
0x140024f17  call    __security_check_cookie
0x140024f1c  mov     rbx, [rsp+248h+arg_18]
0x140024f24  add     rsp, 230h
0x140024f2b  pop     r14
0x140024f2d  pop     rdi
0x140024f2e  pop     rsi
0x140024f2f  retn
0x140024f30  test    dil, dil
0x140024f33  jz      short loc_140024F0C
0x140024f35  mov     rdx, rbx
0x140024f38  lea     rcx, [rsp+248h+var_E8]
0x140024f40  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x140024f45  mov     rdx, rax
0x140024f48  lea     rcx, [rsp+248h+pExceptionObject]
0x140024f50  call    ?Missing@FileError@CLI@@SA?AV12@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; CLI::FileError::Missing(std::string)
0x140024f55  lea     rdx, _TI5?AVFileError@CLI@@; pThrowInfo
0x140024f5c  lea     rcx, [rsp+248h+pExceptionObject]; pExceptionObject
0x140024f64  call    _CxxThrowException_0
0x140024f6a  mov     rdx, rbx
0x140024f6d  lea     rcx, [rsp+248h+var_E8]
0x140024f75  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x140024f7a  mov     rdx, rax
0x140024f7d  lea     rcx, [rsp+248h+var_A8]
0x140024f85  call    ?Missing@FileError@CLI@@SA?AV12@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; CLI::FileError::Missing(std::string)
0x140024f8a  lea     rdx, _TI5?AVFileError@CLI@@; pThrowInfo
0x140024f91  lea     rcx, [rsp+248h+var_A8]; pExceptionObject
0x140024f99  call    _CxxThrowException_0
```
