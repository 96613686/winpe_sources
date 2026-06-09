# QuerySecurityContextToken

- ea: `0x180001600`
- end: `0x18000169e`
- name: `QuerySecurityContextToken`
- size: `158`
- prototype: `SECURITY_STATUS __stdcall(PCtxtHandle phContext, void **Token)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001600`
- `0x180001f90`
- `0x180022190`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180001657`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180001657`

## pseudocode

```c
SECURITY_STATUS __stdcall QuerySecurityContextToken(PCtxtHandle phContext, void **Token)
{
  struct _DLL_SECURITY_PACKAGE *v3; // rax
  struct _DLL_SECURITY_PACKAGE *v4; // rbx
  struct _SecHandle v6; // [rsp+20h] [rbp-28h] BYREF

  v6 = 0;
  v3 = SecpValidateHandle(1, phContext, &v6);
  v4 = v3;
  if ( !v3 )
    return -2146893055;
  if ( !*(_QWORD *)(*((_QWORD *)v3 + 22) + 192LL) )
    return -2146893054;
  TlsSetValue(SecTlsPackage, 0);
  return (*(__int64 (__fastcall **)(struct _SecHandle *, void **))(*((_QWORD *)v4 + 22) + 192LL))(&v6, Token);
}

```

## disassembly

```asm
0x180001600  mov     [rsp+arg_10], rbx
0x180001605  push    rdi
0x180001606  sub     rsp, 40h
0x18000160a  mov     rax, cs:__security_cookie
0x180001611  xor     rax, rsp
0x180001614  mov     [rsp+48h+var_18], rax
0x180001619  mov     rdi, rdx
0x18000161c  lea     r8, [rsp+48h+var_28]; struct _SecHandle *
0x180001621  mov     rdx, rcx; struct _SecHandle *
0x180001624  xorps   xmm0, xmm0
0x180001627  mov     ecx, 1; int
0x18000162c  movups  xmmword ptr [rsp+48h+var_28.dwLower], xmm0
0x180001631  call    ?SecpValidateHandle@@YAPEAU_DLL_SECURITY_PACKAGE@@HPEAU_SecHandle@@0@Z; SecpValidateHandle(int,_SecHandle *,_SecHandle *)
0x180001636  mov     rbx, rax
0x180001639  test    rax, rax
0x18000163c  jz      short loc_180001681
0x18000163e  mov     rcx, [rax+0B0h]
0x180001645  cmp     qword ptr [rcx+0C0h], 0
0x18000164d  jz      short loc_18000167A
0x18000164f  mov     ecx, cs:SecTlsPackage; dwTlsIndex
0x180001655  xor     edx, edx; lpTlsValue
0x180001657  call    cs:__imp_TlsSetValue
0x18000165d  mov     rax, [rbx+0B0h]
0x180001664  lea     rcx, [rsp+48h+var_28]
0x180001669  mov     rdx, rdi
0x18000166c  mov     rax, [rax+0C0h]
0x180001673  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001678  jmp     short loc_180001686
0x18000167a  mov     eax, 80090302h
0x18000167f  jmp     short loc_180001686
0x180001681  mov     eax, 80090301h
0x180001686  mov     rcx, [rsp+48h+var_18]
0x18000168b  xor     rcx, rsp; StackCookie
0x18000168e  call    __security_check_cookie
0x180001693  mov     rbx, [rsp+48h+arg_10]
0x180001698  add     rsp, 40h
0x18000169c  pop     rdi
0x18000169d  retn
```
