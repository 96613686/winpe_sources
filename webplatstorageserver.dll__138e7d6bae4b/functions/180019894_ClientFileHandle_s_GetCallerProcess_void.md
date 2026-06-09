# ClientFileHandle::s_GetCallerProcess(void)

- ea: `0x180019894`
- end: `0x18001996a`
- name: `?s_GetCallerProcess@ClientFileHandle@@CA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ`
- size: `214`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180018dd4`
- `0x180019360`
- `0x18001b428`

## callees

- `0x180019894`
- `0x180061c90`
- `0x180080fb0`
- `0x180081b40`
- `0x180093f70`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180019902`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180019902`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x1800198e6`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x1800198e6`

## string_xrefs

- `0x180019926`: `onecoreuap\inetcore\webplatstorageserver\cachestorage\clientfilehandle.cxx`
- `0x18001993b`: `onecoreuap\inetcore\webplatstorageserver\cachestorage\clientfilehandle.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall ClientFileHandle::s_GetCallerProcess(_QWORD *a1)
{
  unsigned int v2; // eax
  HANDLE v3; // rax
  const char *v4; // r9
  _DWORD RpcCallAttributes[2]; // [rsp+30h] [rbp-98h] BYREF
  _BYTE v7[56]; // [rsp+38h] [rbp-90h] BYREF
  DWORD dwProcessId; // [rsp+70h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  memset_0(v7, 0, 0x70u);
  RpcCallAttributes[0] = 2;
  RpcCallAttributes[1] = 16;
  v2 = RpcServerInqCallAttributesW(0, RpcCallAttributes);
  if ( v2 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x5F,
      (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\cachestorage\\clientfilehandle.cxx",
      (const char *)v2,
      0);
  v3 = OpenProcess(0x40u, 0, dwProcessId);
  *a1 = v3;
  if ( (((unsigned __int64)v3 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x67,
      (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\cachestorage\\clientfilehandle.cxx",
      v4);
  return a1;
}

```

## disassembly

```asm
0x180019894  push    rbx
0x180019896  sub     rsp, 0C0h
0x18001989d  mov     rax, cs:__security_cookie
0x1800198a4  xor     rax, rsp
0x1800198a7  mov     [rsp+0C8h+var_18], rax
0x1800198af  mov     rbx, rcx
0x1800198b2  mov     [rsp+0C8h+var_A0], rcx
0x1800198b7  mov     [rsp+0C8h+var_A8], 0; unsigned int
0x1800198bf  xor     edx, edx; Val
0x1800198c1  lea     r8d, [rdx+70h]; Size
0x1800198c5  lea     rcx, [rsp+0C8h+var_90]; void *
0x1800198ca  call    memset_0
0x1800198cf  mov     [rsp+0C8h+RpcCallAttributes], 2
0x1800198d7  mov     [rsp+0C8h+var_94], 10h
0x1800198df  lea     rdx, [rsp+0C8h+RpcCallAttributes]; RpcCallAttributes
0x1800198e4  xor     ecx, ecx; ClientBinding
0x1800198e6  call    cs:__imp_RpcServerInqCallAttributesW
0x1800198ec  mov     rcx, [rsp+0C8h]; this
0x1800198f4  test    eax, eax
0x1800198f6  jnz     short loc_180019938
0x1800198f8  mov     r8d, [rsp+0C8h+dwProcessId]; dwProcessId
0x1800198fd  xor     edx, edx; bInheritHandle
0x1800198ff  lea     ecx, [rax+40h]; dwDesiredAccess
0x180019902  call    cs:__imp_OpenProcess
0x180019908  mov     [rbx], rax
0x18001990b  mov     [rsp+0C8h+var_A8], 1
0x180019913  inc     rax
0x180019916  test    rax, 0FFFFFFFFFFFFFFFEh
0x18001991c  jnz     short loc_18001994D
0x18001991e  mov     rcx, [rsp+0C8h]; this
0x180019926  lea     r8, aOnecoreuapInet_77; "onecoreuap\\inetcore\\webplatstorageser"...
0x18001992d  mov     edx, 67h ; 'g'; void *
0x180019932  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180019938  mov     r9d, eax; char *
0x18001993b  lea     r8, aOnecoreuapInet_77; "onecoreuap\\inetcore\\webplatstorageser"...
0x180019942  mov     edx, 5Fh ; '_'; void *
0x180019947  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18001994d  mov     rax, rbx
0x180019950  mov     rcx, [rsp+0C8h+var_18]
0x180019958  xor     rcx, rsp; StackCookie
0x18001995b  call    __security_check_cookie
0x180019960  add     rsp, 0C0h
0x180019967  pop     rbx
0x180019968  retn
```
