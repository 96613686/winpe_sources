# SHFindConnectedUserBySid(ushort const *,_GUID const &,void * *)

- ea: `0x180071694`
- end: `0x180071787`
- name: `?SHFindConnectedUserBySid@@YAJPEBGAEBU_GUID@@PEAPEAX@Z`
- size: `243`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002d000`
- `0x18002e3b0`

## callees

- `0x180071694`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800716f2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800716f2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180071715`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180071715`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071777`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071777`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800716b9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800716b9`

## pseudocode

```c
__int64 __fastcall SHFindConnectedUserBySid(const unsigned __int16 *a1, struct _GUID *a2, void **a3)
{
  HRESULT v4; // ebx
  __int64 (__fastcall *v5)(LPVOID, PSID, _QWORD, __int64 *); // rbx
  DWORD LengthSid; // eax
  LPVOID ppv; // [rsp+58h] [rbp+28h] BYREF
  PSID Sid; // [rsp+60h] [rbp+30h] BYREF
  __int64 v10; // [rsp+68h] [rbp+38h] BYREF

  ppv = a2;
  *a3 = 0;
  Sid = 0;
  if ( ConvertStringSidToSidW(a1, &Sid) )
  {
    ppv = 0;
    v4 = CoCreateInstance(
           &GUID_40afa0b6_3b2f_4654_8c3f_161de85cf80e,
           0,
           1u,
           &GUID_9ec044bc_b01d_4c18_8634_59bd3ff5dcc1,
           &ppv);
    if ( v4 >= 0 )
    {
      v10 = 0;
      v5 = *(__int64 (__fastcall **)(LPVOID, PSID, _QWORD, __int64 *))(*(_QWORD *)ppv + 56LL);
      LengthSid = GetLengthSid(Sid);
      v4 = v5(ppv, Sid, LengthSid, &v10);
      if ( v4 >= 0 )
      {
        v4 = (**(__int64 (__fastcall ***)(__int64, GUID *, void **))v10)(
               v10,
               &GUID_9d5f2149_de8c_45f2_b313_6587a04f771d,
               a3);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      }
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    LocalFree(Sid);
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180071694  mov     [rsp-18h+arg_8], rdx
0x180071699  push    rbp
0x18007169a  push    rbx
0x18007169b  push    rdi
0x18007169c  mov     rbp, rsp
0x18007169f  sub     rsp, 30h
0x1800716a3  lea     rdx, [rbp+Sid]; Sid
0x1800716a7  mov     qword ptr [r8], 0
0x1800716ae  mov     rdi, r8
0x1800716b1  mov     [rbp+Sid], 0
0x1800716b9  call    cs:__imp_ConvertStringSidToSidW
0x1800716bf  test    eax, eax
0x1800716c1  jnz     short loc_1800716CD
0x1800716c3  mov     ebx, 80004005h
0x1800716c8  jmp     loc_18007177D
0x1800716cd  xor     edx, edx; pUnkOuter
0x1800716cf  mov     [rbp+arg_8], 0
0x1800716d7  lea     rax, [rbp+arg_8]
0x1800716db  lea     r9, _GUID_9ec044bc_b01d_4c18_8634_59bd3ff5dcc1; riid
0x1800716e2  mov     [rsp+30h+ppv], rax; ppv
0x1800716e7  lea     rcx, _GUID_40afa0b6_3b2f_4654_8c3f_161de85cf80e; rclsid
0x1800716ee  lea     r8d, [rdx+1]; dwClsContext
0x1800716f2  call    cs:__imp_CoCreateInstance
0x1800716f8  mov     ebx, eax
0x1800716fa  test    eax, eax
0x1800716fc  js      short loc_180071773
0x1800716fe  mov     rax, [rbp+arg_8]
0x180071702  mov     [rbp+arg_18], 0
0x18007170a  mov     rcx, [rax]
0x18007170d  mov     rbx, [rcx+38h]
0x180071711  mov     rcx, [rbp+Sid]; pSid
0x180071715  call    cs:__imp_GetLengthSid
0x18007171b  mov     rdx, [rbp+Sid]
0x18007171f  lea     r9, [rbp+arg_18]
0x180071723  mov     rcx, [rbp+arg_8]
0x180071727  mov     r8d, eax
0x18007172a  mov     rax, rbx
0x18007172d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071732  mov     ebx, eax
0x180071734  test    eax, eax
0x180071736  js      short loc_180071763
0x180071738  mov     rcx, [rbp+arg_18]
0x18007173c  lea     rdx, _GUID_9d5f2149_de8c_45f2_b313_6587a04f771d
0x180071743  mov     r8, rdi
0x180071746  mov     rax, [rcx]
0x180071749  mov     rax, [rax]
0x18007174c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071751  mov     rcx, [rbp+arg_18]
0x180071755  mov     ebx, eax
0x180071757  mov     rax, [rcx]
0x18007175a  mov     rax, [rax+10h]
0x18007175e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071763  mov     rcx, [rbp+arg_8]
0x180071767  mov     rax, [rcx]
0x18007176a  mov     rax, [rax+10h]
0x18007176e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071773  mov     rcx, [rbp+Sid]; hMem
0x180071777  call    cs:__imp_LocalFree
0x18007177d  mov     eax, ebx
0x18007177f  add     rsp, 30h
0x180071783  pop     rdi
0x180071784  pop     rbx
0x180071785  pop     rbp
0x180071786  retn
```
