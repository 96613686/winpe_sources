# CExec::MakeAttributeList(ulong)

- ea: `0x1402828a8`
- end: `0x1402829ad`
- name: `?MakeAttributeList@CExec@@YA?AV?$unique_ptr@U_PROC_THREAD_ATTRIBUTE_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@K@Z`
- size: `261`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x140080ed8`

## callees

- `0x140080180`
- `0x1400c40e0`
- `0x140105824`
- `0x1401332f0`
- `0x1402828a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1402828f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1402828f8`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1402828e4`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x140282954`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1402828e4`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x140282954`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140282914`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140282914`

## string_xrefs

- `0x140282935`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x140282969`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x14028299b`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct _PROC_THREAD_ATTRIBUTE_LIST **__fastcall CExec::MakeAttributeList(struct _PROC_THREAD_ATTRIBUTE_LIST **a1)
{
  struct _PROC_THREAD_ATTRIBUTE_LIST *v2; // rax
  const char *v3; // r9
  const char *v4; // r9
  ULONG_PTR Size; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  Size = 0;
  if ( InitializeProcThreadAttributeList(0, 3u, 0, &Size) || GetLastError() != 122 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x51,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
      (const char *)0x8000FFFFLL,
      0);
  v2 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)LocalAlloc(0, Size);
  *a1 = v2;
  if ( !v2 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x57,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
      v3);
  if ( !InitializeProcThreadAttributeList(v2, 3u, 0, &Size) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x58,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
      v4);
  return a1;
}

```

## disassembly

```asm
0x1402828a8  push    rbx
0x1402828aa  sub     rsp, 40h
0x1402828ae  mov     rax, cs:__security_cookie
0x1402828b5  xor     rax, rsp
0x1402828b8  mov     [rsp+48h+var_10], rax
0x1402828bd  mov     rbx, rcx
0x1402828c0  mov     [rsp+48h+var_20], rcx
0x1402828c5  mov     [rsp+48h+var_28], 0; int
0x1402828cd  mov     [rsp+48h+Size], 0
0x1402828d6  lea     r9, [rsp+48h+Size]; lpSize
0x1402828db  xor     r8d, r8d; dwFlags
0x1402828de  lea     edx, [r8+3]; dwAttributeCount
0x1402828e2  xor     ecx, ecx; lpAttributeList
0x1402828e4  call    cs:__imp_InitializeProcThreadAttributeList
0x1402828eb  nop     dword ptr [rax+rax+00h]
0x1402828f0  test    eax, eax
0x1402828f2  jnz     loc_140282990
0x1402828f8  call    cs:__imp_GetLastError
0x1402828ff  nop     dword ptr [rax+rax+00h]
0x140282904  cmp     eax, 7Ah ; 'z'
0x140282907  jnz     loc_140282990
0x14028290d  mov     rdx, [rsp+48h+Size]; uBytes
0x140282912  xor     ecx, ecx; uFlags
0x140282914  call    cs:__imp_LocalAlloc
0x14028291b  nop     dword ptr [rax+rax+00h]
0x140282920  mov     [rbx], rax
0x140282923  mov     [rsp+48h+var_28], 1
0x14028292b  mov     rcx, [rsp+48h]; this
0x140282930  test    rax, rax
0x140282933  jnz     short loc_140282945
0x140282935  lea     r8, aOnecoreVmCompu_63; "onecore\\vm\\compute\\service\\cexec\\l"...
0x14028293c  lea     edx, [rax+57h]; void *
0x14028293f  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x140282945  lea     r9, [rsp+48h+Size]; lpSize
0x14028294a  xor     r8d, r8d; dwFlags
0x14028294d  lea     edx, [r8+3]; dwAttributeCount
0x140282951  mov     rcx, rax; lpAttributeList
0x140282954  call    cs:__imp_InitializeProcThreadAttributeList
0x14028295b  nop     dword ptr [rax+rax+00h]
0x140282960  test    eax, eax
0x140282962  jnz     short loc_140282979
0x140282964  mov     rcx, [rsp+48h]; this
0x140282969  lea     r8, aOnecoreVmCompu_63; "onecore\\vm\\compute\\service\\cexec\\l"...
0x140282970  lea     edx, [rax+58h]; void *
0x140282973  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140282979  mov     rax, rbx
0x14028297c  mov     rcx, [rsp+48h+var_10]
0x140282981  xor     rcx, rsp; StackCookie
0x140282984  call    __security_check_cookie
0x140282989  add     rsp, 40h
0x14028298d  pop     rbx
0x14028298e  retn
0x140282990  mov     rcx, [rsp+48h]; this
0x140282995  mov     r9d, 8000FFFFh; char *
0x14028299b  lea     r8, aOnecoreVmCompu_63; "onecore\\vm\\compute\\service\\cexec\\l"...
0x1402829a2  mov     edx, 51h ; 'Q'; void *
0x1402829a7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
