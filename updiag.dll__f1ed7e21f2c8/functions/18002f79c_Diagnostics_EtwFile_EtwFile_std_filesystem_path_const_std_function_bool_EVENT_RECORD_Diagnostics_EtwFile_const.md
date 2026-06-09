# Diagnostics::EtwFile::EtwFile(std::filesystem::path const &,std::function<bool (_EVENT_RECORD *,Diagnostics::EtwFile const &)>)

- ea: `0x18002f79c`
- end: `0x18002f96a`
- name: `??0EtwFile@Diagnostics@@QEAA@AEBVpath@filesystem@std@@V?$function@$$A6A_NPEAU_EVENT_RECORD@@AEBVEtwFile@Diagnostics@@@Z@4@@Z`
- size: `462`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18002f56c`

## callees

- `0x180018b04`
- `0x180018bec`
- `0x180018e64`
- `0x18002f79c`
- `0x18008fe00`
- `0x180096170`
- `0x1800961f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f8d0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f8d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f8bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f92d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f8bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f92d`
- `api-ms-win-eventing-consumer-l1-1-2!OpenTraceFromFile` at `0x18002f8a7`
- `api-ms-win-eventing-consumer-l1-1-2!OpenTraceFromFile` at `0x18002f8a7`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x18002f8c8`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x18002f8c8`

## string_xrefs

- `0x18002f94c`: `Failed to open ETW trace file, throwing: %ls`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Diagnostics::EtwFile::EtwFile(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rbp
  TRACEHANDLE v12; // r14
  DWORD LastError; // ebx
  __int64 v14; // rcx
  const char *v16; // rax
  const char *v17; // r9
  __int128 v18; // [rsp+40h] [rbp-68h] BYREF
  __int128 v19; // [rsp+50h] [rbp-58h]
  __int64 v20; // [rsp+60h] [rbp-48h]
  __int64 v21; // [rsp+68h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v21 = a3;
  std::wstring::wstring(a1, a2);
  *(_QWORD *)(a1 + 88) = 0;
  v6 = *(_QWORD *)(a3 + 56);
  if ( v6 )
  {
    if ( v6 == a3 )
    {
      *(_QWORD *)(a1 + 88) = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 8LL))(v6, a1 + 32);
      v8 = *(_QWORD *)(a3 + 56);
      if ( !v8 )
        goto LABEL_7;
      LOBYTE(v7) = v8 != a3;
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 32LL))(v8, v7);
    }
    else
    {
      *(_QWORD *)(a1 + 88) = v6;
    }
    *(_QWORD *)(a3 + 56) = 0;
  }
LABEL_7:
  *(_BYTE *)(a1 + 96) = 0;
  memset((void *)(a1 + 104), 0, 0x118u);
  *(_QWORD *)(a1 + 384) = -1;
  *(_QWORD *)(a1 + 392) = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  if ( *(_QWORD *)(a1 + 88) )
  {
    *((_QWORD *)&v18 + 1) = Diagnostics::EtwFile::EventRecordCallback;
    *(_QWORD *)&v19 = a1;
    *((_QWORD *)&v19 + 1) = Diagnostics::EtwFile::BufferCallback;
    v20 = a1;
  }
  v9 = a1;
  if ( *(_QWORD *)(a1 + 24) > 7u )
    v9 = *(_QWORD *)a1;
  v11 = OpenTraceFromFile(v9, &v18, a1 + 104);
  v12 = *(_QWORD *)(a1 + 384);
  if ( v12 != -1 )
  {
    LastError = GetLastError();
    CloseTrace(v12);
    SetLastError(LastError);
  }
  *(_QWORD *)(a1 + 384) = v11;
  if ( v11 == -1 )
  {
    GetLastError();
    v16 = (const char *)std::wstring::c_str(a2);
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0xBB,
      (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\diag\\EtwFileProcessor.hpp",
      v17,
      (unsigned int)"Failed to open ETW trace file, throwing: %ls",
      v16);
  }
  v14 = *(_QWORD *)(a3 + 56);
  if ( v14 )
  {
    LOBYTE(v10) = v14 != a3;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v14 + 32LL))(v14, v10);
    *(_QWORD *)(a3 + 56) = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x18002f79c  mov     [rsp+arg_18], rbx
0x18002f7a1  push    rbp
0x18002f7a2  push    rsi
0x18002f7a3  push    rdi
0x18002f7a4  push    r14
0x18002f7a6  push    r15
0x18002f7a8  sub     rsp, 80h
0x18002f7af  mov     rax, cs:__security_cookie
0x18002f7b6  xor     rax, rsp
0x18002f7b9  mov     [rsp+0A8h+var_38], rax
0x18002f7be  mov     rsi, r8
0x18002f7c1  mov     r15, rdx
0x18002f7c4  mov     rdi, rcx
0x18002f7c7  mov     [rsp+0A8h+var_70], rcx
0x18002f7cc  mov     [rsp+0A8h+var_40], r8
0x18002f7d1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002f7d6  nop
0x18002f7d7  mov     qword ptr [rdi+58h], 0
0x18002f7df  mov     rcx, [rsi+38h]
0x18002f7e3  test    rcx, rcx
0x18002f7e6  jz      short loc_18002F82A
0x18002f7e8  cmp     rcx, rsi
0x18002f7eb  jnz     short loc_18002F81E
0x18002f7ed  mov     rax, [rcx]
0x18002f7f0  lea     rdx, [rdi+20h]
0x18002f7f4  mov     rax, [rax+8]
0x18002f7f8  call    _guard_dispatch_icall
0x18002f7fd  mov     [rdi+58h], rax
0x18002f801  mov     rcx, [rsi+38h]
0x18002f805  test    rcx, rcx
0x18002f808  jz      short loc_18002F82A
0x18002f80a  cmp     rcx, rsi
0x18002f80d  setnz   dl
0x18002f810  mov     rax, [rcx]
0x18002f813  mov     rax, [rax+20h]
0x18002f817  call    _guard_dispatch_icall
0x18002f81c  jmp     short loc_18002F822
0x18002f81e  mov     [rdi+58h], rcx
0x18002f822  mov     qword ptr [rsi+38h], 0
0x18002f82a  mov     byte ptr [rdi+60h], 0
0x18002f82e  xor     edx, edx; Val
0x18002f830  mov     r8d, 118h; Size
0x18002f836  lea     rcx, [rdi+68h]; void *
0x18002f83a  call    memset
0x18002f83f  mov     qword ptr [rdi+180h], 0FFFFFFFFFFFFFFFFh
0x18002f84a  mov     qword ptr [rdi+188h], 0
0x18002f855  xorps   xmm0, xmm0
0x18002f858  xor     eax, eax
0x18002f85a  movups  [rsp+0A8h+var_68], xmm0
0x18002f85f  movups  [rsp+0A8h+var_58], xmm0
0x18002f864  mov     [rsp+0A8h+var_48], rax
0x18002f869  cmp     [rdi+58h], rax
0x18002f86d  jz      short loc_18002F891
0x18002f86f  lea     rax, ?EventRecordCallback@EtwFile@Diagnostics@@SAXPEAU_EVENT_RECORD@@@Z; Diagnostics::EtwFile::EventRecordCallback(_EVENT_RECORD *)
0x18002f876  mov     qword ptr [rsp+0A8h+var_68+8], rax
0x18002f87b  mov     qword ptr [rsp+0A8h+var_58], rdi
0x18002f880  lea     rax, ?BufferCallback@EtwFile@Diagnostics@@SAHPEBUETW_BUFFER_HEADER@@KPEBUETW_BUFFER_CALLBACK_INFORMATION@@PEAX@Z; Diagnostics::EtwFile::BufferCallback(ETW_BUFFER_HEADER const *,ulong,ETW_BUFFER_CALLBACK_INFORMATION const *,void *)
0x18002f887  mov     qword ptr [rsp+0A8h+var_58+8], rax
0x18002f88c  mov     [rsp+0A8h+var_48], rdi
0x18002f891  mov     rcx, rdi
0x18002f894  cmp     qword ptr [rdi+18h], 7
0x18002f899  jbe     short loc_18002F89E
0x18002f89b  mov     rcx, [rdi]
0x18002f89e  lea     r8, [rdi+68h]
0x18002f8a2  lea     rdx, [rsp+0A8h+var_68]
0x18002f8a7  call    cs:__imp_OpenTraceFromFile
0x18002f8ad  mov     rbp, rax
0x18002f8b0  mov     r14, [rdi+180h]
0x18002f8b7  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18002f8bb  jz      short loc_18002F8D6
0x18002f8bd  call    cs:__imp_GetLastError
0x18002f8c3  mov     ebx, eax
0x18002f8c5  mov     rcx, r14; TraceHandle
0x18002f8c8  call    cs:__imp_CloseTrace
0x18002f8ce  mov     ecx, ebx; dwErrCode
0x18002f8d0  call    cs:__imp_SetLastError
0x18002f8d6  mov     [rdi+180h], rbp
0x18002f8dd  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x18002f8e1  jz      short loc_18002F92D
0x18002f8e3  mov     rcx, [rsi+38h]
0x18002f8e7  test    rcx, rcx
0x18002f8ea  jz      short loc_18002F906
0x18002f8ec  cmp     rcx, rsi
0x18002f8ef  setnz   dl
0x18002f8f2  mov     r8, [rcx]
0x18002f8f5  mov     rax, [r8+20h]
0x18002f8f9  call    _guard_dispatch_icall
0x18002f8fe  mov     qword ptr [rsi+38h], 0
0x18002f906  mov     rax, rdi
0x18002f909  mov     rcx, [rsp+0A8h+var_38]
0x18002f90e  xor     rcx, rsp; StackCookie
0x18002f911  call    __security_check_cookie
0x18002f916  mov     rbx, [rsp+0A8h+arg_18]
0x18002f91e  add     rsp, 80h
0x18002f925  pop     r15
0x18002f927  pop     r14
0x18002f929  pop     rdi
0x18002f92a  pop     rsi
0x18002f92b  pop     rbp
0x18002f92c  retn
0x18002f92d  call    cs:__imp_GetLastError
0x18002f933  nop
0x18002f934  mov     r9d, eax
0x18002f937  mov     rcx, r15
0x18002f93a  call    ?c_str@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAPEB_WXZ; std::wstring::c_str(void)
0x18002f93f  mov     rcx, [rsp+0A8h]; this
0x18002f947  mov     [rsp+0A8h+var_80], rax; char *
0x18002f94c  lea     rax, aFailedToOpenEt; "Failed to open ETW trace file, throwing"...
0x18002f953  mov     qword ptr [rsp+0A8h+var_88], rax; unsigned int
0x18002f958  lea     r8, aCW1SSrcCalliop_5; "C:\\__w\\1\\s\\src\\Calliope\\libs\\dia"...
0x18002f95f  mov     edx, 0BBh; void *
0x18002f964  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
