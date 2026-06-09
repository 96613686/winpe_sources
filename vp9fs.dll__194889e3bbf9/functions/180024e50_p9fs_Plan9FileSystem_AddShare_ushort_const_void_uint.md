# p9fs::Plan9FileSystem::AddShare(ushort const *,void *,uint)

- ea: `0x180024e50`
- end: `0x180024f86`
- name: `?AddShare@Plan9FileSystem@p9fs@@UEAAJPEBGPEAXI@Z`
- size: `310`
- prototype: `int(p9fs::Plan9FileSystem *__hidden this, const unsigned __int16 *, void *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x180004120`
- `0x18000c208`
- `0x180024af0`
- `0x180024e50`
- `0x1800283c8`
- `0x1800286fc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180024e8f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180024e98`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180024e8f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180024e98`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180024ebe`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180024ebe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024f45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024f45`

## string_xrefs

- `0x180024f73`: `onecore\vm\dv\storage\plan9\dll\windows\p9fs.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall p9fs::Plan9FileSystem::AddShare(RTL_SRWLOCK *this, const unsigned __int16 *a2, void *a3, int a4)
{
  unsigned __int64 v8; // rdi
  HANDLE CurrentProcess; // rbx
  HANDLE v10; // rax
  BOOL v11; // eax
  const char *v12; // r9
  const char *v13; // r9
  __int64 result; // rax
  _OWORD Src[2]; // [rsp+48h] [rbp-70h] BYREF
  HANDLE TargetHandle; // [rsp+68h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v8 = -1;
  TargetHandle = (HANDLE)-1LL;
  CurrentProcess = GetCurrentProcess();
  v10 = GetCurrentProcess();
  v11 = DuplicateHandle(v10, a3, CurrentProcess, &TargetHandle, 0, 0, 2u);
  try
  {
    if ( !v11 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x27D,
        (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9fs.cpp",
        v12);
    Src[0] = 0;
    Src[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(Src[0]) = 0;
    do
      ++v8;
    while ( a2[v8] );
    Vml::WideToMultiByte(Src, a2, v8);
    p9fs::ShareList::Add(this + 28, (size_t *)Src, (__int64 *)&TargetHandle, a4);
    std::string::~string(Src);
    if ( (char *)TargetHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TargetHandle);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x282,
                           (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9fs.cpp",
                           v13);
  }
  return result;
}

```

## disassembly

```asm
0x180024e50  push    rbx
0x180024e52  push    rsi
0x180024e53  push    rdi
0x180024e54  push    r12
0x180024e56  push    r13
0x180024e58  push    r14
0x180024e5a  push    r15
0x180024e5c  sub     rsp, 80h
0x180024e63  mov     rax, cs:__security_cookie
0x180024e6a  xor     rax, rsp
0x180024e6d  mov     [rsp+0B8h+var_48], rax
0x180024e72  mov     r14d, r9d
0x180024e75  mov     r12, r8
0x180024e78  mov     rsi, rdx
0x180024e7b  mov     r15, rcx
0x180024e7e  xor     r13d, r13d
0x180024e81  mov     [rsp+0B8h+var_78], r13d
0x180024e86  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180024e8a  mov     [rsp+0B8h+TargetHandle], rdi
0x180024e8f  call    cs:__imp_GetCurrentProcess
0x180024e95  mov     rbx, rax
0x180024e98  call    cs:__imp_GetCurrentProcess
0x180024e9e  mov     [rsp+0B8h+dwOptions], 2; dwOptions
0x180024ea6  mov     [rsp+0B8h+bInheritHandle], r13d; bInheritHandle
0x180024eab  mov     [rsp+0B8h+dwDesiredAccess], r13d; dwDesiredAccess
0x180024eb0  lea     r9, [rsp+0B8h+TargetHandle]; lpTargetHandle
0x180024eb5  mov     r8, rbx; hTargetProcessHandle
0x180024eb8  mov     rdx, r12; hSourceHandle
0x180024ebb  mov     rcx, rax; hSourceProcessHandle
0x180024ebe  call    cs:__imp_DuplicateHandle
0x180024ec4  mov     rcx, [rsp+0B8h]; this
0x180024ecc  test    eax, eax
0x180024ece  jz      loc_180024F73
0x180024ed4  xorps   xmm0, xmm0
0x180024ed7  movups  [rsp+0B8h+Src], xmm0
0x180024edc  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x180024ee4  movdqu  [rsp+0B8h+var_60], xmm1
0x180024eea  mov     byte ptr [rsp+0B8h+Src], r13b
0x180024eef  mov     [rsp+0B8h+var_78], 1
0x180024ef7  inc     rdi
0x180024efa  cmp     [rsi+rdi*2], r13w
0x180024eff  jnz     short loc_180024EF7
0x180024f01  mov     r8, rdi; cchWideChar
0x180024f04  mov     rdx, rsi; lpWideCharStr
0x180024f07  lea     rcx, [rsp+0B8h+Src]; Src
0x180024f0c  call    ?WideToMultiByte@Vml@@YAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBG_KI@Z; Vml::WideToMultiByte(std::string &,ushort const *,unsigned __int64,uint)
0x180024f11  lea     rcx, [r15+0E0h]
0x180024f18  mov     r9d, r14d
0x180024f1b  lea     r8, [rsp+0B8h+TargetHandle]
0x180024f20  lea     rdx, [rsp+0B8h+Src]
0x180024f25  call    ?Add@ShareList@p9fs@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$$QEAV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@W4Plan9ShareFlags@Storage@Resources@VirtualMachines@Schema@@@Z; p9fs::ShareList::Add(std::string const &,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&,Schema::VirtualMachines::Resources::Storage::Plan9ShareFlags)
0x180024f2a  nop
0x180024f2b  lea     rcx, [rsp+0B8h+Src]
0x180024f30  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180024f35  nop
0x180024f36  mov     rcx, [rsp+0B8h+TargetHandle]; hObject
0x180024f3b  lea     rax, [rcx-1]
0x180024f3f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180024f43  ja      short loc_180024F4B
0x180024f45  call    cs:__imp_CloseHandle
0x180024f4b  xor     eax, eax
0x180024f4d  jmp     short loc_180024F53
0x180024f4f  mov     eax, [rsp+0B8h+var_78]
0x180024f53  mov     rcx, [rsp+0B8h+var_48]
0x180024f58  xor     rcx, rsp; StackCookie
0x180024f5b  call    __security_check_cookie
0x180024f60  add     rsp, 80h
0x180024f67  pop     r15
0x180024f69  pop     r14
0x180024f6b  pop     r13
0x180024f6d  pop     r12
0x180024f6f  pop     rdi
0x180024f70  pop     rsi
0x180024f71  pop     rbx
0x180024f72  retn
0x180024f73  lea     r8, aOnecoreVmDvSto_8; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x180024f7a  mov     edx, 27Dh; void *
0x180024f7f  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
