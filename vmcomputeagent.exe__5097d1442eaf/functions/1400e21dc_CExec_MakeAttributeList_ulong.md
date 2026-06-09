# CExec::MakeAttributeList(ulong)

- ea: `0x1400e21dc`
- end: `0x1400e22cb`
- name: `?MakeAttributeList@CExec@@YA?AV?$unique_ptr@U_PROC_THREAD_ATTRIBUTE_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@K@Z`
- size: `239`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400e0b10`

## callees

- `0x140005360`
- `0x1400083bc`
- `0x14000ddac`
- `0x14000ea60`
- `0x140093ee8`
- `0x1400e21dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400e2222`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400e2222`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400e2234`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400e2234`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1400e2218`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1400e225e`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1400e2218`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1400e225e`

## string_xrefs

- `0x1400e2283`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x1400e22a7`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x1400e22b9`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct _PROC_THREAD_ATTRIBUTE_LIST **__fastcall CExec::MakeAttributeList(struct _PROC_THREAD_ATTRIBUTE_LIST **a1)
{
  __int64 v2; // rdx
  struct _PROC_THREAD_ATTRIBUTE_LIST *v3; // rax
  const char *v4; // r9
  const char *v5; // r9
  unsigned int v7; // eax
  ULONG_PTR Size; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  Size = 0;
  if ( InitializeProcThreadAttributeList(0, 3u, 0, &Size) || GetLastError() != 122 )
  {
    v7 = wil::verify_hresult<long>(2147549183LL, v2);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x51,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
      (const char *)v7,
      0);
  }
  v3 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)LocalAlloc(0, Size);
  *a1 = v3;
  if ( !v3 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x57,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
      v4);
  if ( !InitializeProcThreadAttributeList(v3, 3u, 0, &Size) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x58,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
      v5);
  return a1;
}

```

## disassembly

```asm
0x1400e21dc  push    rbx
0x1400e21de  sub     rsp, 40h
0x1400e21e2  mov     rax, cs:__security_cookie
0x1400e21e9  xor     rax, rsp
0x1400e21ec  mov     [rsp+48h+var_10], rax
0x1400e21f1  mov     rbx, rcx
0x1400e21f4  mov     [rsp+48h+var_20], rcx
0x1400e21f9  mov     [rsp+48h+var_28], 0; int
0x1400e2201  mov     [rsp+48h+Size], 0
0x1400e220a  lea     r9, [rsp+48h+Size]; lpSize
0x1400e220f  xor     r8d, r8d; dwFlags
0x1400e2212  lea     edx, [r8+3]; dwAttributeCount
0x1400e2216  xor     ecx, ecx; lpAttributeList
0x1400e2218  call    cs:__imp_InitializeProcThreadAttributeList
0x1400e221e  test    eax, eax
0x1400e2220  jnz     short loc_1400E2295
0x1400e2222  call    cs:__imp_GetLastError
0x1400e2228  cmp     eax, 7Ah ; 'z'
0x1400e222b  jnz     short loc_1400E2295
0x1400e222d  mov     rdx, [rsp+48h+Size]; uBytes
0x1400e2232  xor     ecx, ecx; uFlags
0x1400e2234  call    cs:__imp_LocalAlloc
0x1400e223a  mov     [rbx], rax
0x1400e223d  mov     [rsp+48h+var_28], 1
0x1400e2245  mov     rcx, [rsp+48h]; this
0x1400e224a  test    rax, rax
0x1400e224d  jz      short loc_1400E22B9
0x1400e224f  lea     r9, [rsp+48h+Size]; lpSize
0x1400e2254  xor     r8d, r8d; dwFlags
0x1400e2257  lea     edx, [r8+3]; dwAttributeCount
0x1400e225b  mov     rcx, rax; lpAttributeList
0x1400e225e  call    cs:__imp_InitializeProcThreadAttributeList
0x1400e2264  test    eax, eax
0x1400e2266  jz      short loc_1400E227E
0x1400e2268  mov     rax, rbx
0x1400e226b  mov     rcx, [rsp+48h+var_10]
0x1400e2270  xor     rcx, rsp; StackCookie
0x1400e2273  call    __security_check_cookie
0x1400e2278  add     rsp, 40h
0x1400e227c  pop     rbx
0x1400e227d  retn
0x1400e227e  mov     rcx, [rsp+48h]; this
0x1400e2283  lea     r8, aOnecoreVmCompu_27; "onecore\\vm\\compute\\service\\cexec\\l"...
0x1400e228a  mov     edx, 58h ; 'X'; void *
0x1400e228f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400e2295  mov     ecx, 8000FFFFh
0x1400e229a  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1400e229f  mov     r9d, eax; char *
0x1400e22a2  mov     rcx, [rsp+48h]; this
0x1400e22a7  lea     r8, aOnecoreVmCompu_27; "onecore\\vm\\compute\\service\\cexec\\l"...
0x1400e22ae  mov     edx, 51h ; 'Q'; void *
0x1400e22b3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400e22b9  lea     r8, aOnecoreVmCompu_27; "onecore\\vm\\compute\\service\\cexec\\l"...
0x1400e22c0  mov     edx, 57h ; 'W'; void *
0x1400e22c5  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
