# ATL::CSecurityDesc::Init(_SECURITY_DESCRIPTOR const &)

- ea: `0x18004b8f0`
- end: `0x18004b9db`
- name: `?Init@CSecurityDesc@ATL@@IEAAXAEBU_SECURITY_DESCRIPTOR@@@Z`
- size: `235`
- prototype: `void(ATL::CSecurityDesc *__hidden this, const struct _SECURITY_DESCRIPTOR *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006bb70`

## callees

- `0x18001fc54`
- `0x18004b8f0`
- `0x1800504b4`
- `0x1800528ac`

## import_xrefs

- `msvcrt!malloc` at `0x18004b917`
- `msvcrt!malloc` at `0x18004b917`
- `msvcrt!memcpy_s` at `0x18004b98d`
- `msvcrt!memcpy_s` at `0x18004b98d`
- `msvcrt!free` at `0x18004b95a`
- `msvcrt!free` at `0x18004b9c5`
- `msvcrt!free` at `0x18004b95a`
- `msvcrt!free` at `0x18004b9c5`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18004b9b0`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18004b9b0`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18004b90b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18004b90b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18004b945`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18004b945`

## pseudocode

```c
void __fastcall ATL::CSecurityDesc::Init(ATL::CSecurityDesc *this, struct _SECURITY_DESCRIPTOR *a2)
{
  void *v4; // rax
  unsigned int Error; // ebx
  errno_t v6; // eax
  unsigned int v7; // ebx
  WORD pControl; // [rsp+30h] [rbp+8h] BYREF
  rsize_t SourceSize; // [rsp+38h] [rbp+10h] BYREF
  DWORD dwRevision; // [rsp+40h] [rbp+18h] BYREF

  dwRevision = 0;
  LODWORD(SourceSize) = GetSecurityDescriptorLength(a2);
  v4 = malloc((unsigned int)SourceSize);
  *((_QWORD *)this + 1) = v4;
  if ( !v4 )
    ATL::PrivateAtlThrow(0x8007000E);
  pControl = 0;
  if ( !GetSecurityDescriptorControl(a2, &pControl, &dwRevision) )
  {
    Error = ATL::AtlHresultFromLastError();
    free(*((void **)this + 1));
    *((_QWORD *)this + 1) = 0;
    ATL::PrivateAtlThrow(Error);
  }
  if ( (pControl & 0x8000u) == 0 )
  {
    if ( !MakeSelfRelativeSD(a2, *((PSECURITY_DESCRIPTOR *)this + 1), (LPDWORD)&SourceSize) )
    {
      v7 = ATL::AtlHresultFromLastError();
      free(*((void **)this + 1));
      *((_QWORD *)this + 1) = 0;
      ATL::PrivateAtlThrow(v7);
    }
  }
  else
  {
    v6 = memcpy_s(*((void *const *)this + 1), (unsigned int)SourceSize, a2, (unsigned int)SourceSize);
    ATL::AtlCrtErrorCheck(v6);
  }
}

```

## disassembly

```asm
0x18004b8f0  mov     [rsp+arg_18], rbx
0x18004b8f5  push    rdi
0x18004b8f6  sub     rsp, 20h
0x18004b8fa  mov     rdi, rcx
0x18004b8fd  mov     [rsp+28h+dwRevision], 0
0x18004b905  mov     rcx, rdx; pSecurityDescriptor
0x18004b908  mov     rbx, rdx
0x18004b90b  call    cs:__imp_GetSecurityDescriptorLength
0x18004b911  mov     ecx, eax; Size
0x18004b913  mov     dword ptr [rsp+28h+SourceSize], ecx
0x18004b917  call    cs:__imp_malloc
0x18004b91d  mov     [rdi+8], rax
0x18004b921  test    rax, rax
0x18004b924  jnz     short loc_18004B931
0x18004b926  mov     ecx, 8007000Eh; unsigned int
0x18004b92b  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18004b931  xor     eax, eax
0x18004b933  lea     r8, [rsp+28h+dwRevision]; lpdwRevision
0x18004b938  lea     rdx, [rsp+28h+pControl]; pControl
0x18004b93d  mov     [rsp+28h+pControl], ax
0x18004b942  mov     rcx, rbx; pSecurityDescriptor
0x18004b945  call    cs:__imp_GetSecurityDescriptorControl
0x18004b94b  test    eax, eax
0x18004b94d  jnz     short loc_18004B970
0x18004b94f  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18004b954  mov     rcx, [rdi+8]; Block
0x18004b958  mov     ebx, eax
0x18004b95a  call    cs:__imp_free
0x18004b960  mov     ecx, ebx; unsigned int
0x18004b962  mov     qword ptr [rdi+8], 0
0x18004b96a  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18004b970  mov     rax, [rdi+8]
0x18004b974  mov     ecx, 8000h
0x18004b979  test    [rsp+28h+pControl], cx
0x18004b97e  jz      short loc_18004B9A5
0x18004b980  mov     edx, dword ptr [rsp+28h+SourceSize]; DestinationSize
0x18004b984  mov     r8, rbx; Source
0x18004b987  mov     r9d, edx; SourceSize
0x18004b98a  mov     rcx, rax; Destination
0x18004b98d  call    cs:__imp_memcpy_s
0x18004b993  mov     ecx, eax; int
0x18004b995  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18004b99a  mov     rbx, [rsp+28h+arg_18]
0x18004b99f  add     rsp, 20h
0x18004b9a3  pop     rdi
0x18004b9a4  retn
0x18004b9a5  lea     r8, [rsp+28h+SourceSize]; lpdwBufferLength
0x18004b9aa  mov     rdx, rax; pSelfRelativeSecurityDescriptor
0x18004b9ad  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x18004b9b0  call    cs:__imp_MakeSelfRelativeSD
0x18004b9b6  test    eax, eax
0x18004b9b8  jnz     short loc_18004B99A
0x18004b9ba  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18004b9bf  mov     rcx, [rdi+8]; Block
0x18004b9c3  mov     ebx, eax
0x18004b9c5  call    cs:__imp_free
0x18004b9cb  mov     ecx, ebx; unsigned int
0x18004b9cd  mov     qword ptr [rdi+8], 0
0x18004b9d5  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
```
