# ATL::CSecurityDesc::Init(_SECURITY_DESCRIPTOR const &)

- ea: `0x18004dd70`
- end: `0x18004de86`
- name: `?Init@CSecurityDesc@ATL@@IEAAXAEBU_SECURITY_DESCRIPTOR@@@Z`
- size: `278`
- prototype: `void(ATL::CSecurityDesc *__hidden this, const struct _SECURITY_DESCRIPTOR *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006f17c`

## callees

- `0x18002c2f4`
- `0x18004dd70`
- `0x1800529a0`
- `0x180055004`

## import_xrefs

- `msvcrt!malloc` at `0x18004dd9d`
- `msvcrt!malloc` at `0x18004dd9d`
- `msvcrt!memcpy_s` at `0x18004de25`
- `msvcrt!memcpy_s` at `0x18004de25`
- `msvcrt!free` at `0x18004ddec`
- `msvcrt!free` at `0x18004de6a`
- `msvcrt!free` at `0x18004ddec`
- `msvcrt!free` at `0x18004de6a`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18004de4f`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18004de4f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18004dd8b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18004dd8b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18004ddd1`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18004ddd1`

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
0x18004dd70  mov     [rsp+arg_18], rbx
0x18004dd75  push    rdi
0x18004dd76  sub     rsp, 20h
0x18004dd7a  mov     rdi, rcx
0x18004dd7d  mov     [rsp+28h+dwRevision], 0
0x18004dd85  mov     rcx, rdx; pSecurityDescriptor
0x18004dd88  mov     rbx, rdx
0x18004dd8b  call    cs:__imp_GetSecurityDescriptorLength
0x18004dd92  nop     dword ptr [rax+rax+00h]
0x18004dd97  mov     ecx, eax; Size
0x18004dd99  mov     dword ptr [rsp+28h+SourceSize], ecx
0x18004dd9d  call    cs:__imp_malloc
0x18004dda4  nop     dword ptr [rax+rax+00h]
0x18004dda9  mov     [rdi+8], rax
0x18004ddad  test    rax, rax
0x18004ddb0  jnz     short loc_18004DDBD
0x18004ddb2  mov     ecx, 8007000Eh; unsigned int
0x18004ddb7  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18004ddbd  xor     eax, eax
0x18004ddbf  lea     r8, [rsp+28h+dwRevision]; lpdwRevision
0x18004ddc4  lea     rdx, [rsp+28h+pControl]; pControl
0x18004ddc9  mov     [rsp+28h+pControl], ax
0x18004ddce  mov     rcx, rbx; pSecurityDescriptor
0x18004ddd1  call    cs:__imp_GetSecurityDescriptorControl
0x18004ddd8  nop     dword ptr [rax+rax+00h]
0x18004dddd  test    eax, eax
0x18004dddf  jnz     short loc_18004DE08
0x18004dde1  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18004dde6  mov     rcx, [rdi+8]; Block
0x18004ddea  mov     ebx, eax
0x18004ddec  call    cs:__imp_free
0x18004ddf3  nop     dword ptr [rax+rax+00h]
0x18004ddf8  mov     ecx, ebx; unsigned int
0x18004ddfa  mov     qword ptr [rdi+8], 0
0x18004de02  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18004de08  mov     rax, [rdi+8]
0x18004de0c  mov     ecx, 8000h
0x18004de11  test    [rsp+28h+pControl], cx
0x18004de16  jz      short loc_18004DE44
0x18004de18  mov     edx, dword ptr [rsp+28h+SourceSize]; DestinationSize
0x18004de1c  mov     r8, rbx; Source
0x18004de1f  mov     r9d, edx; SourceSize
0x18004de22  mov     rcx, rax; Destination
0x18004de25  call    cs:__imp_memcpy_s
0x18004de2c  nop     dword ptr [rax+rax+00h]
0x18004de31  mov     ecx, eax; int
0x18004de33  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18004de38  mov     rbx, [rsp+28h+arg_18]
0x18004de3d  add     rsp, 20h
0x18004de41  pop     rdi
0x18004de42  retn
0x18004de44  lea     r8, [rsp+28h+SourceSize]; lpdwBufferLength
0x18004de49  mov     rdx, rax; pSelfRelativeSecurityDescriptor
0x18004de4c  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x18004de4f  call    cs:__imp_MakeSelfRelativeSD
0x18004de56  nop     dword ptr [rax+rax+00h]
0x18004de5b  test    eax, eax
0x18004de5d  jnz     short loc_18004DE38
0x18004de5f  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18004de64  mov     rcx, [rdi+8]; Block
0x18004de68  mov     ebx, eax
0x18004de6a  call    cs:__imp_free
0x18004de71  nop     dword ptr [rax+rax+00h]
0x18004de76  mov     ecx, ebx; unsigned int
0x18004de78  mov     qword ptr [rdi+8], 0
0x18004de80  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
```
