# SecpFindDll(_UNICODE_STRING *,int)

- ea: `0x18000d420`
- end: `0x18000d52e`
- name: `?SecpFindDll@@YAPEAU_SECP_DLL_BINDING@@PEAU_UNICODE_STRING@@H@Z`
- size: `270`
- prototype: `struct _SECP_DLL_BINDING *__fastcall(struct _UNICODE_STRING *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000d3a8`

## callees

- `0x18000d420`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!_wcsicmp` at `0x18000d4a8`
- `api-ms-win-core-crt-l1-1-0!_wcsicmp` at `0x18000d4a8`
- `api-ms-win-core-crt-l1-1-0!wcsrchr` at `0x18000d4f8`
- `api-ms-win-core-crt-l1-1-0!wcsrchr` at `0x18000d518`
- `api-ms-win-core-crt-l1-1-0!wcsrchr` at `0x18000d4f8`
- `api-ms-win-core-crt-l1-1-0!wcsrchr` at `0x18000d518`
- `ntdll!RtlReleaseResource` at `0x18000d4c3`
- `ntdll!RtlReleaseResource` at `0x18000d4c3`
- `ntdll!RtlAcquireResourceShared` at `0x18000d46a`
- `ntdll!RtlAcquireResourceShared` at `0x18000d46a`

## pseudocode

```c
struct _SECP_DLL_BINDING *__fastcall SecpFindDll(struct _UNICODE_STRING *a1, int a2)
{
  struct _RTL_RESOURCE *v4; // r14
  unsigned int v5; // ecx
  __int64 v6; // rbp
  __int64 v7; // rbx
  const wchar_t *Buffer; // rdi
  const wchar_t *v9; // rdx
  __int64 v10; // rbx
  wchar_t *v12; // rax
  const wchar_t *v13; // rbx
  wchar_t *v14; // rcx
  wchar_t *v15; // rax

  v4 = (struct _RTL_RESOURCE *)&SecPackageListLock[12
                                                 * (unsigned __int8)((SecPackageListLockCount - 1)
                                                                   & NtCurrentTeb()->CurrentIdealProcessor.Reserved)];
  RtlAcquireResourceShared(v4, 1u);
  v5 = SecPackageDllCount;
  v6 = 0;
  if ( !SecPackageDllCount )
    goto LABEL_8;
  while ( 1 )
  {
    v7 = *((_QWORD *)SecPackageDllList + v6);
    if ( v7 )
      break;
LABEL_7:
    v6 = (unsigned int)(v6 + 1);
    if ( (unsigned int)v6 >= v5 )
      goto LABEL_8;
  }
  Buffer = a1->Buffer;
  if ( a2 )
  {
    v9 = *(const wchar_t **)(v7 + 24);
  }
  else
  {
    v12 = wcsrchr(a1->Buffer, 0x5Cu);
    v13 = *(const wchar_t **)(v7 + 24);
    v14 = v12 + 1;
    if ( !v12 )
      v14 = (wchar_t *)Buffer;
    Buffer = v14;
    v15 = wcsrchr(v13, 0x5Cu);
    v9 = v15 + 1;
    if ( !v15 )
      v9 = v13;
  }
  if ( _wcsicmp(Buffer, v9) )
  {
    v5 = SecPackageDllCount;
    goto LABEL_7;
  }
  if ( (unsigned int)v6 < SecPackageDllCount )
  {
    v10 = *((_QWORD *)SecPackageDllList + v6);
    goto LABEL_9;
  }
LABEL_8:
  v10 = 0;
LABEL_9:
  RtlReleaseResource(v4);
  return (struct _SECP_DLL_BINDING *)v10;
}

```

## disassembly

```asm
0x18000d420  push    rbx
0x18000d422  push    rbp
0x18000d423  push    rsi
0x18000d424  push    rdi
0x18000d425  push    r13
0x18000d427  push    r14
0x18000d429  push    r15
0x18000d42b  sub     rsp, 20h
0x18000d42f  mov     rax, gs:30h
0x18000d438  mov     r13, rcx
0x18000d43b  mov     r8d, cs:SecPackageListLockCount
0x18000d442  lea     rcx, SecPackageListLock
0x18000d449  dec     r8d
0x18000d44c  mov     r15d, edx
0x18000d44f  mov     dl, 1; Wait
0x18000d451  movzx   r9d, byte ptr [rax+1747h]
0x18000d459  and     r9, r8
0x18000d45c  lea     r14, [r9+r9*2]
0x18000d460  shl     r14, 5
0x18000d464  add     r14, rcx
0x18000d467  mov     rcx, r14; Resource
0x18000d46a  call    cs:__imp_RtlAcquireResourceShared
0x18000d470  mov     ecx, cs:?SecPackageDllCount@@3KA; ulong SecPackageDllCount
0x18000d476  xor     ebp, ebp
0x18000d478  test    ecx, ecx
0x18000d47a  jz      short loc_18000D4BE
0x18000d47c  nop     dword ptr [rax+00h]
0x18000d480  mov     rax, cs:?SecPackageDllList@@3PEAPEAU_SECP_DLL_BINDING@@EA; _SECP_DLL_BINDING * * SecPackageDllList
0x18000d487  lea     rsi, ds:0[rbp*8]
0x18000d48f  mov     rbx, [rsi+rax]
0x18000d493  test    rbx, rbx
0x18000d496  jz      short loc_18000D4B8
0x18000d498  mov     rdi, [r13+8]
0x18000d49c  test    r15d, r15d
0x18000d49f  jz      short loc_18000D4F0
0x18000d4a1  mov     rdx, [rbx+18h]; String2
0x18000d4a5  mov     rcx, rdi; String1
0x18000d4a8  call    cs:__imp__wcsicmp
0x18000d4ae  test    eax, eax
0x18000d4b0  jz      short loc_18000D4DB
0x18000d4b2  mov     ecx, cs:?SecPackageDllCount@@3KA; ulong SecPackageDllCount
0x18000d4b8  inc     ebp
0x18000d4ba  cmp     ebp, ecx
0x18000d4bc  jb      short loc_18000D480
0x18000d4be  xor     ebx, ebx
0x18000d4c0  mov     rcx, r14; Resource
0x18000d4c3  call    cs:__imp_RtlReleaseResource
0x18000d4c9  mov     rax, rbx
0x18000d4cc  add     rsp, 20h
0x18000d4d0  pop     r15
0x18000d4d2  pop     r14
0x18000d4d4  pop     r13
0x18000d4d6  pop     rdi
0x18000d4d7  pop     rsi
0x18000d4d8  pop     rbp
0x18000d4d9  pop     rbx
0x18000d4da  retn
0x18000d4db  cmp     ebp, cs:?SecPackageDllCount@@3KA; ulong SecPackageDllCount
0x18000d4e1  jnb     short loc_18000D4BE
0x18000d4e3  mov     rbx, cs:?SecPackageDllList@@3PEAPEAU_SECP_DLL_BINDING@@EA; _SECP_DLL_BINDING * * SecPackageDllList
0x18000d4ea  mov     rbx, [rsi+rbx]
0x18000d4ee  jmp     short loc_18000D4C0
0x18000d4f0  mov     edx, 5Ch ; '\'; Ch
0x18000d4f5  mov     rcx, rdi; Str
0x18000d4f8  call    cs:__imp_wcsrchr
0x18000d4fe  mov     rbx, [rbx+18h]
0x18000d502  mov     edx, 5Ch ; '\'; Ch
0x18000d507  test    rax, rax
0x18000d50a  lea     rcx, [rax+2]
0x18000d50e  cmovz   rcx, rdi
0x18000d512  mov     rdi, rcx
0x18000d515  mov     rcx, rbx; Str
0x18000d518  call    cs:__imp_wcsrchr
0x18000d51e  test    rax, rax
0x18000d521  lea     rdx, [rax+2]
0x18000d525  cmovz   rdx, rbx
0x18000d529  jmp     loc_18000D4A5
```
