# WindowsUpdateAdministration::RoGetUpdateAdministrator(wchar_t const *,_GUID const &,void * *)

- ea: `0x180040e90`
- end: `0x18004102c`
- name: `?RoGetUpdateAdministrator@WindowsUpdateAdministration@@UEAAJPEB_WAEBU_GUID@@PEAPEAX@Z`
- size: `412`
- prototype: `__int64 __fastcall(WindowsUpdateAdministration *__hidden this, const wchar_t *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180008e64`
- `0x180032028`
- `0x180040a08`
- `0x180040e90`
- `0x1800dd930`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040f1e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040f7f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040fe0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180041004`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040f1e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040f7f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040fe0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180041004`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040eec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040eec`

## string_xrefs

- `0x180040eca`: `C:\__w\1\s\src\orchestrator\core\USOSvc\WindowsUpdateAdministrationImpl.cpp`
- `0x180040f09`: `C:\__w\1\s\src\orchestrator\core\USOSvc\WindowsUpdateAdministrationImpl.cpp`
- `0x180040f53`: `C:\__w\1\s\src\orchestrator\core\USOSvc\WindowsUpdateAdministrationImpl.cpp`
- `0x180040fb4`: `C:\__w\1\s\src\orchestrator\core\USOSvc\WindowsUpdateAdministrationImpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WindowsUpdateAdministration::RoGetUpdateAdministrator(
        WindowsUpdateAdministration *this,
        const wchar_t *a2,
        const struct _GUID *a3,
        void **a4)
{
  const char *v7; // r9
  __int64 result; // rax
  int CoreWorker; // eax
  unsigned int v10; // ebx
  int v11; // eax
  int v12; // [rsp+20h] [rbp-58h]
  void *v13; // [rsp+38h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  try
  {
    if ( !IsSystemOrAdmin() )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE0,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\WindowsUpdateAdministrationImpl.cpp",
        (const char *)0x80070005LL,
        v12);
      return 2147942405LL;
    }
    EnterCriticalSection(&CriticalSection);
    if ( !a4 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE4,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\WindowsUpdateAdministrationImpl.cpp",
        (const char *)0x80070057LL,
        v12);
      LeaveCriticalSection(&CriticalSection);
      return 2147942487LL;
    }
    v13 = 0;
    CoreWorker = GetCoreWorker(&GUID_af2ba583_e24f_43f1_b92b_fc8125f93d16, &v13);
    v10 = CoreWorker;
    if ( CoreWorker < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE7,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\WindowsUpdateAdministrationImpl.cpp",
        (const char *)(unsigned int)CoreWorker,
        v12);
      if ( v13 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v13 + 16LL))(v13);
LABEL_9:
      LeaveCriticalSection(&CriticalSection);
      return v10;
    }
    v11 = (*(__int64 (__fastcall **)(void *, const wchar_t *, const struct _GUID *, void **))(*(_QWORD *)v13 + 72LL))(
            v13,
            a2,
            a3,
            a4);
    v10 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE9,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\WindowsUpdateAdministrationImpl.cpp",
        (const char *)(unsigned int)v11,
        v12);
      if ( v13 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v13 + 16LL))(v13);
      goto LABEL_9;
    }
    if ( v13 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v13 + 16LL))(v13);
    LeaveCriticalSection(&CriticalSection);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xED,
                           (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\WindowsUpdateAdministrationImpl.cpp",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x180040e90  push    rbx
0x180040e92  push    rsi
0x180040e93  push    rdi
0x180040e94  push    r14
0x180040e96  push    r15
0x180040e98  sub     rsp, 50h
0x180040e9c  mov     rax, cs:__security_cookie
0x180040ea3  xor     rax, rsp
0x180040ea6  mov     [rsp+78h+var_38], rax
0x180040eab  mov     rdi, r9
0x180040eae  mov     r14, r8
0x180040eb1  mov     rsi, rdx
0x180040eb4  call    ?IsSystemOrAdmin@@YA_NXZ; IsSystemOrAdmin(void)
0x180040eb9  test    al, al
0x180040ebb  jnz     short loc_180040EE2
0x180040ebd  mov     rcx, [rsp+78h]; this
0x180040ec2  mov     ebx, 80070005h
0x180040ec7  mov     r9d, ebx; char *
0x180040eca  lea     r8, aCW1SSrcOrchest_2; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x180040ed1  mov     edx, 0E0h; void *
0x180040ed6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040edb  mov     eax, ebx
0x180040edd  jmp     loc_180041012
0x180040ee2  lea     r15, CriticalSection
0x180040ee9  mov     rcx, r15; lpCriticalSection
0x180040eec  call    cs:__imp_EnterCriticalSection
0x180040ef2  mov     [rsp+78h+var_48], r15
0x180040ef7  test    rdi, rdi
0x180040efa  jnz     short loc_180040F2B
0x180040efc  mov     rcx, [rsp+78h]; this
0x180040f01  mov     ebx, 80070057h
0x180040f06  mov     r9d, ebx; char *
0x180040f09  lea     r8, aCW1SSrcOrchest_2; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x180040f10  mov     edx, 0E4h; void *
0x180040f15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040f1a  nop
0x180040f1b  mov     rcx, r15; lpCriticalSection
0x180040f1e  call    cs:__imp_LeaveCriticalSection
0x180040f24  mov     eax, ebx
0x180040f26  jmp     loc_180041012
0x180040f2b  mov     [rsp+78h+var_40], 0
0x180040f34  lea     rdx, [rsp+78h+var_40]; void **
0x180040f39  lea     rcx, _GUID_af2ba583_e24f_43f1_b92b_fc8125f93d16; riid
0x180040f40  call    ?GetCoreWorker@@YAJAEBU_GUID@@PEAPEAX@Z; GetCoreWorker(_GUID const &,void * *)
0x180040f45  mov     ebx, eax
0x180040f47  test    eax, eax
0x180040f49  jns     short loc_180040F8C
0x180040f4b  mov     rcx, [rsp+78h]; this
0x180040f50  mov     r9d, eax; char *
0x180040f53  lea     r8, aCW1SSrcOrchest_2; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x180040f5a  mov     edx, 0E7h; void *
0x180040f5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040f64  nop
0x180040f65  mov     rcx, [rsp+78h+var_40]
0x180040f6a  test    rcx, rcx
0x180040f6d  jz      short loc_180040F7C
0x180040f6f  mov     rax, [rcx]
0x180040f72  mov     rax, [rax+10h]
0x180040f76  call    _guard_dispatch_icall
0x180040f7b  nop
0x180040f7c  mov     rcx, r15; lpCriticalSection
0x180040f7f  call    cs:__imp_LeaveCriticalSection
0x180040f85  mov     eax, ebx
0x180040f87  jmp     loc_180041012
0x180040f8c  mov     rcx, [rsp+78h+var_40]
0x180040f91  mov     rax, [rcx]
0x180040f94  mov     r9, rdi
0x180040f97  mov     r8, r14
0x180040f9a  mov     rdx, rsi
0x180040f9d  mov     rax, [rax+48h]
0x180040fa1  call    _guard_dispatch_icall
0x180040fa6  mov     ebx, eax
0x180040fa8  test    eax, eax
0x180040faa  jns     short loc_180040FEA
0x180040fac  mov     rcx, [rsp+78h]; this
0x180040fb1  mov     r9d, eax; char *
0x180040fb4  lea     r8, aCW1SSrcOrchest_2; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x180040fbb  mov     edx, 0E9h; void *
0x180040fc0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040fc5  nop
0x180040fc6  mov     rcx, [rsp+78h+var_40]
0x180040fcb  test    rcx, rcx
0x180040fce  jz      short loc_180040FDD
0x180040fd0  mov     rax, [rcx]
0x180040fd3  mov     rax, [rax+10h]
0x180040fd7  call    _guard_dispatch_icall
0x180040fdc  nop
0x180040fdd  mov     rcx, r15; lpCriticalSection
0x180040fe0  call    cs:__imp_LeaveCriticalSection
0x180040fe6  mov     eax, ebx
0x180040fe8  jmp     short loc_180041012
0x180040fea  mov     rcx, [rsp+78h+var_40]
0x180040fef  test    rcx, rcx
0x180040ff2  jz      short loc_180041001
0x180040ff4  mov     rax, [rcx]
0x180040ff7  mov     rax, [rax+10h]
0x180040ffb  call    _guard_dispatch_icall
0x180041000  nop
0x180041001  mov     rcx, r15; lpCriticalSection
0x180041004  call    cs:__imp_LeaveCriticalSection
0x18004100a  xor     eax, eax
0x18004100c  jmp     short loc_180041012
0x18004100e  mov     eax, dword ptr [rsp+78h+var_40]
0x180041012  mov     rcx, [rsp+78h+var_38]
0x180041017  xor     rcx, rsp; StackCookie
0x18004101a  call    __security_check_cookie
0x18004101f  add     rsp, 50h
0x180041023  pop     r15
0x180041025  pop     r14
0x180041027  pop     rdi
0x180041028  pop     rsi
0x180041029  pop     rbx
0x18004102a  retn
```
