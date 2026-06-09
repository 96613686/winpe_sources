# UtilCreateFile(wchar_t const *,wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *,tlx::unique_any<tlx::file_handle_traits> *)

- ea: `0x180040f04`
- end: `0x1800410b4`
- name: `?UtilCreateFile@@YAJPEB_W0KKPEAU_SECURITY_ATTRIBUTES@@KKPEAXPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z`
- size: `432`
- prototype: `__int64 __usercall@<rax>(wchar_t *@<rcx>, LPSECURITY_ATTRIBUTES lpSecurityAttributes, DWORD, DWORD, HANDLE, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003be90`

## callees

- `0x180007fd8`
- `0x180008004`
- `0x180009684`
- `0x18000cf50`
- `0x18000db80`
- `0x180028760`
- `0x18002a758`
- `0x18003fb94`
- `0x180040f04`
- `0x1800410bc`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180041000`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180041000`
- `ext-ms-win-wer-xbox-l1-2-0!XerShouldWerManageRootDirectory` at `0x18004103f`
- `ext-ms-win-wer-xbox-l1-2-0!XerShouldWerManageRootDirectory` at `0x18004103f`

## string_xrefs

- `0x180040f35`: `onecore\windows\feedback\core\common\lib\utility.cpp`
- `0x180040fb6`: `onecore\windows\feedback\core\common\lib\utility.cpp`
- `0x180041021`: `onecore\windows\feedback\core\common\lib\utility.cpp`
- `0x180041067`: `onecore\windows\feedback\core\common\lib\utility.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UtilCreateFile(
        wchar_t *a1,
        void *a2,
        DWORD a3,
        DWORD a4,
        LPSECURITY_ATTRIBUTES lpSecurityAttributes,
        DWORD a6,
        DWORD dwFlagsAndAttributes,
        HANDLE hTemplateFile,
        __int64 a9)
{
  __int64 v12; // rdx
  unsigned int LastError; // ebx
  DWORD v14; // r14d
  int ParentDirectory; // eax
  __int64 v16; // rdx
  HANDLE FileW; // rbx
  const char *v18; // r9
  int v19; // eax
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-40h]
  DWORD dwCreationDispositiona; // [rsp+20h] [rbp-40h]
  wchar_t *v23[4]; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  __int64 v25; // [rsp+90h] [rbp+30h] BYREF
  HANDLE v26; // [rsp+98h] [rbp+38h] BYREF

  v26 = a2;
  if ( a1 )
  {
    if ( !a9 )
    {
      v12 = 6093;
      goto LABEL_3;
    }
    tlx::unique_any<tlx::file_handle_traits>::reset(a9, 0);
    v25 = 0;
    v14 = a6;
    if ( a6 != 3 )
    {
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v23);
      ParentDirectory = UtilGetParentDirectory(a1, v23);
      LastError = ParentDirectory;
      if ( ParentDirectory < 0 )
      {
        v16 = 6117;
LABEL_11:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v16,
          (unsigned int)"onecore\\windows\\feedback\\core\\common\\lib\\utility.cpp",
          (const char *)(unsigned int)ParentDirectory,
          dwCreationDisposition);
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v23);
        goto LABEL_20;
      }
      ParentDirectory = UtilVerifyAndLockDirectory(v23[0], (__int64)&v25);
      LastError = ParentDirectory;
      if ( ParentDirectory < 0 )
      {
        v16 = 6123;
        goto LABEL_11;
      }
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v23);
    }
    FileW = CreateFileW(a1, a3, a4, lpSecurityAttributes, v14, dwFlagsAndAttributes, hTemplateFile);
    v26 = FileW;
    if ( (unsigned __int64)FileW + 1 > 1 )
    {
      if ( !(unsigned __int8)XerShouldWerManageRootDirectory()
        || (v19 = UtilVerifyFilePath(a1, FileW), LastError = v19, v19 >= 0) )
      {
        tlx::unique_any<tlx::file_handle_traits>::operator=(a9, &v26);
        tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v26);
        LastError = 0;
        goto LABEL_20;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1807,
        (unsigned int)"onecore\\windows\\feedback\\core\\common\\lib\\utility.cpp",
        (const char *)(unsigned int)v19,
        dwCreationDispositiona);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x17F6,
                    (unsigned int)"onecore\\windows\\feedback\\core\\common\\lib\\utility.cpp",
                    v18);
    }
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v26);
LABEL_20:
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v25);
    return LastError;
  }
  v12 = 6092;
LABEL_3:
  LastError = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"onecore\\windows\\feedback\\core\\common\\lib\\utility.cpp",
    (const char *)0x80070057LL,
    dwCreationDisposition);
  return LastError;
}

```

## disassembly

```asm
0x180040f04  mov     [rsp-28h+arg_10], rbx
0x180040f09  mov     [rsp-28h+arg_8], rdx
0x180040f0e  push    rbp
0x180040f0f  push    rsi
0x180040f10  push    r12
0x180040f12  push    r14
0x180040f14  push    r15
0x180040f16  mov     rbp, rsp
0x180040f19  sub     rsp, 60h
0x180040f1d  mov     r15d, r9d
0x180040f20  mov     r12d, r8d
0x180040f23  mov     rsi, rcx
0x180040f26  test    rcx, rcx
0x180040f29  jnz     short loc_180040F4D
0x180040f2b  mov     edx, 17CCh; void *
0x180040f30  mov     ebx, 80070057h
0x180040f35  lea     r8, aOnecoreWindows_1; "onecore\\windows\\feedback\\core\\commo"...
0x180040f3c  mov     r9d, ebx; char *
0x180040f3f  mov     rcx, [rbp+28h]; this
0x180040f43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040f48  jmp     loc_18004109C
0x180040f4d  cmp     [rbp+arg_40], 0
0x180040f52  jnz     short loc_180040F5B
0x180040f54  mov     edx, 17CDh
0x180040f59  jmp     short loc_180040F30
0x180040f5b  xor     edx, edx
0x180040f5d  mov     rcx, [rbp+arg_40]
0x180040f61  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180040f66  mov     [rbp+arg_0], 0
0x180040f6e  mov     r14d, [rbp+arg_28]
0x180040f72  cmp     r14d, 3
0x180040f76  jz      short loc_180040FDE
0x180040f78  lea     rcx, [rbp+var_20]; void *
0x180040f7c  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180040f81  nop
0x180040f82  lea     rdx, [rbp+var_20]
0x180040f86  mov     rcx, rsi
0x180040f89  call    ?UtilGetParentDirectory@@YAJPEB_WAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetParentDirectory(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x180040f8e  mov     ebx, eax
0x180040f90  test    eax, eax
0x180040f92  jns     short loc_180040F9B
0x180040f94  mov     edx, 17E5h
0x180040f99  jmp     short loc_180040FB3
0x180040f9b  lea     rdx, [rbp+arg_0]
0x180040f9f  mov     rcx, [rbp+var_20]; wchar_t *
0x180040fa3  call    ?UtilVerifyAndLockDirectory@@YAJPEB_WPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; UtilVerifyAndLockDirectory(wchar_t const *,tlx::unique_any<tlx::file_handle_traits> *)
0x180040fa8  mov     ebx, eax
0x180040faa  test    eax, eax
0x180040fac  jns     short loc_180040FD5
0x180040fae  mov     edx, 17EBh; void *
0x180040fb3  mov     r9d, eax; char *
0x180040fb6  lea     r8, aOnecoreWindows_1; "onecore\\windows\\feedback\\core\\commo"...
0x180040fbd  mov     rcx, [rbp+28h]; this
0x180040fc1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040fc6  nop
0x180040fc7  lea     rcx, [rbp+var_20]; void *
0x180040fcb  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180040fd0  jmp     loc_180041093
0x180040fd5  lea     rcx, [rbp+var_20]; void *
0x180040fd9  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180040fde  mov     rax, [rbp+arg_38]
0x180040fe2  mov     [rsp+60h+hTemplateFile], rax; hTemplateFile
0x180040fe7  mov     eax, [rbp+arg_30]
0x180040fea  mov     [rsp+60h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x180040fee  mov     [rsp+60h+dwCreationDisposition], r14d; int
0x180040ff3  mov     r9, [rbp+lpSecurityAttributes]; lpSecurityAttributes
0x180040ff7  mov     r8d, r15d; dwShareMode
0x180040ffa  mov     edx, r12d; dwDesiredAccess
0x180040ffd  mov     rcx, rsi; lpFileName
0x180041000  call    cs:__imp_CreateFileW
0x180041007  nop     dword ptr [rax+rax+00h]
0x18004100c  mov     rbx, rax
0x18004100f  mov     [rbp+arg_8], rax
0x180041013  lea     rcx, [rax+1]
0x180041017  cmp     rcx, 1
0x18004101b  ja      short loc_18004103F
0x18004101d  mov     rcx, [rbp+28h]; this
0x180041021  lea     r8, aOnecoreWindows_1; "onecore\\windows\\feedback\\core\\commo"...
0x180041028  mov     edx, 17F6h; void *
0x18004102d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180041032  mov     ebx, eax
0x180041034  lea     rcx, [rbp+arg_8]
0x180041038  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18004103d  jmp     short loc_180041093
0x18004103f  call    cs:__imp_XerShouldWerManageRootDirectory
0x180041046  nop     dword ptr [rax+rax+00h]
0x18004104b  test    al, al
0x18004104d  jz      short loc_18004107A
0x18004104f  mov     rdx, rbx; void *
0x180041052  mov     rcx, rsi; wchar_t *
0x180041055  call    ?UtilVerifyFilePath@@YAJPEB_WPEAX@Z; UtilVerifyFilePath(wchar_t const *,void *)
0x18004105a  mov     ebx, eax
0x18004105c  test    eax, eax
0x18004105e  jns     short loc_18004107A
0x180041060  mov     rcx, [rbp+28h]; this
0x180041064  mov     r9d, eax; char *
0x180041067  lea     r8, aOnecoreWindows_1; "onecore\\windows\\feedback\\core\\commo"...
0x18004106e  mov     edx, 1807h; void *
0x180041073  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041078  jmp     short loc_180041034
0x18004107a  lea     rdx, [rbp+arg_8]
0x18004107e  mov     rcx, [rbp+arg_40]
0x180041082  call    ??4?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAAEAV01@$$QEAV01@@Z; tlx::unique_any<tlx::file_handle_traits>::operator=(tlx::unique_any<tlx::file_handle_traits> &&)
0x180041087  nop
0x180041088  lea     rcx, [rbp+arg_8]
0x18004108c  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180041091  xor     ebx, ebx
0x180041093  lea     rcx, [rbp+arg_0]
0x180041097  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18004109c  mov     eax, ebx
0x18004109e  mov     rbx, [rsp+60h+arg_10]
0x1800410a6  add     rsp, 60h
0x1800410aa  pop     r15
0x1800410ac  pop     r14
0x1800410ae  pop     r12
0x1800410b0  pop     rsi
0x1800410b1  pop     rbp
0x1800410b2  retn
```
