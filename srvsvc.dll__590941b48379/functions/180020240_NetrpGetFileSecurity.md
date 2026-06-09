# NetrpGetFileSecurity

- ea: `0x180020240`
- end: `0x180020342`
- name: `NetrpGetFileSecurity`
- size: `258`
- prototype: `__int64 __fastcall(PCWSTR, PCWSTR SourceString, PCWSTR pszPathIn, SECURITY_INFORMATION RequestedInformation, HLOCAL *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18001fdc4`
- `0x180020240`
- `0x18003b61c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020279`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020279`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002031b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020328`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002031b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020328`
- `RPCRT4!RpcImpersonateClient` at `0x1800202d3`
- `RPCRT4!RpcImpersonateClient` at `0x1800202d3`
- `RPCRT4!RpcRevertToSelf` at `0x180020310`
- `RPCRT4!RpcRevertToSelf` at `0x180020310`

## pseudocode

```c
__int64 __fastcall NetrpGetFileSecurity(
        PCWSTR a1,
        PCWSTR SourceString,
        PCWSTR pszPathIn,
        SECURITY_INFORMATION RequestedInformation,
        HLOCAL *a5)
{
  HLOCAL v9; // rax
  int v11; // eax
  unsigned int FileSecurity; // ebx

  v9 = LocalAlloc(0x40u, 0x10u);
  *a5 = v9;
  if ( !v9 )
    return 8;
  v11 = ((RequestedInformation & 7) != 0 ? 0x20000 : 0) | 0x1000000;
  if ( (RequestedInformation & 8) == 0 )
    v11 = (RequestedInformation & 7) != 0 ? 0x20000 : 0;
  FileSecurity = AdtCheckShareAccessAndGetFullPath(SourceString, a1, pszPathIn, v11);
  if ( FileSecurity )
    goto LABEL_11;
  FileSecurity = RpcImpersonateClient(0);
  if ( !FileSecurity )
  {
    FileSecurity = PrivateGetFileSecurity(0, RequestedInformation);
    if ( !FileSecurity )
    {
      *(_DWORD *)*a5 = 0;
      *((_QWORD *)*a5 + 1) = 0;
    }
    RpcRevertToSelf();
  }
  LocalFree(0);
  if ( FileSecurity )
  {
LABEL_11:
    LocalFree(*a5);
    *a5 = 0;
  }
  return FileSecurity;
}

```

## disassembly

```asm
0x180020240  push    rbx
0x180020242  push    rbp
0x180020243  push    rsi
0x180020244  push    rdi
0x180020245  push    r14
0x180020247  sub     rsp, 50h
0x18002024b  mov     rbp, rdx
0x18002024e  mov     [rsp+78h+var_38], 0
0x180020257  mov     edx, 10h; uBytes
0x18002025c  mov     [rsp+78h+var_48], 0
0x180020264  mov     r14, rcx
0x180020267  mov     [rsp+78h+hMem], 0
0x180020270  mov     esi, r9d
0x180020273  mov     rbx, r8
0x180020276  lea     ecx, [rdx+30h]; uFlags
0x180020279  call    cs:__imp_LocalAlloc
0x18002027f  mov     rdi, [rsp+78h+arg_20]
0x180020287  mov     [rdi], rax
0x18002028a  test    rax, rax
0x18002028d  jnz     short loc_180020299
0x18002028f  mov     eax, 8
0x180020294  jmp     loc_180020337
0x180020299  mov     eax, esi
0x18002029b  lea     r9, [rsp+78h+hMem]
0x1800202a0  and     al, 7
0x1800202a2  mov     r8, rbx; pszPathIn
0x1800202a5  neg     al
0x1800202a7  mov     rcx, rbp; SourceString
0x1800202aa  sbb     edx, edx
0x1800202ac  and     edx, 20000h
0x1800202b2  mov     eax, edx
0x1800202b4  bts     eax, 18h
0x1800202b8  test    sil, 8
0x1800202bc  cmovz   eax, edx
0x1800202bf  mov     rdx, r14; PCWSTR
0x1800202c2  mov     [rsp+78h+var_58], eax; int
0x1800202c6  call    AdtCheckShareAccessAndGetFullPath
0x1800202cb  mov     ebx, eax
0x1800202cd  test    eax, eax
0x1800202cf  jnz     short loc_180020325
0x1800202d1  xor     ecx, ecx; BindingHandle
0x1800202d3  call    cs:__imp_RpcImpersonateClient
0x1800202d9  mov     ebx, eax
0x1800202db  test    eax, eax
0x1800202dd  jnz     short loc_180020316
0x1800202df  mov     rcx, [rsp+78h+hMem]; lpFileName
0x1800202e4  lea     r9, [rsp+78h+var_48]
0x1800202e9  lea     r8, [rsp+78h+var_38]
0x1800202ee  mov     edx, esi; RequestedInformation
0x1800202f0  call    PrivateGetFileSecurity
0x1800202f5  mov     ebx, eax
0x1800202f7  test    eax, eax
0x1800202f9  jnz     short loc_180020310
0x1800202fb  mov     rdx, [rdi]
0x1800202fe  mov     eax, [rsp+78h+var_48]
0x180020302  mov     [rdx], eax
0x180020304  mov     rdx, [rdi]
0x180020307  mov     rax, [rsp+78h+var_38]
0x18002030c  mov     [rdx+8], rax
0x180020310  call    cs:__imp_RpcRevertToSelf
0x180020316  mov     rcx, [rsp+78h+hMem]; hMem
0x18002031b  call    cs:__imp_LocalFree
0x180020321  test    ebx, ebx
0x180020323  jz      short loc_180020335
0x180020325  mov     rcx, [rdi]; hMem
0x180020328  call    cs:__imp_LocalFree
0x18002032e  mov     qword ptr [rdi], 0
0x180020335  mov     eax, ebx
0x180020337  add     rsp, 50h
0x18002033b  pop     r14
0x18002033d  pop     rdi
0x18002033e  pop     rsi
0x18002033f  pop     rbp
0x180020340  pop     rbx
0x180020341  retn
```
