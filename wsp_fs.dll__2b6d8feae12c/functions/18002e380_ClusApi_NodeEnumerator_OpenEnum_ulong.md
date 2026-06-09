# ClusApi::NodeEnumerator::OpenEnum(ulong)

- ea: `0x18002e380`
- end: `0x18002e3fa`
- name: `?OpenEnum@NodeEnumerator@ClusApi@@MEAAKK@Z`
- size: `122`
- prototype: `unsigned int(ClusApi::NodeEnumerator *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002d9e8`
- `0x18002e380`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e3e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e3e0`
- `CLUSAPI!ClusterNodeOpenEnumEx` at `0x18002e3c0`
- `CLUSAPI!ClusterNodeOpenEnumEx` at `0x18002e3c0`

## pseudocode

```c
__int64 __fastcall ClusApi::NodeEnumerator::OpenEnum(ClusApi::NodeEnumerator *this, DWORD a2)
{
  HNODEENUMEX *v2; // rsi
  unsigned int v3; // edi
  struct _HNODE *v5; // rax
  HNODEENUMEX v6; // rbx

  v2 = (HNODEENUMEX *)((char *)this + 32);
  v3 = 0;
  if ( ((*((_QWORD *)this + 4) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v5 = (struct _HNODE *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 152LL))(*((_QWORD *)this + 6));
    v6 = ClusterNodeOpenEnumEx(v5, a2, 0);
    cxl::AutoHandle<_HNODEENUMEX *,unsigned long,&unsigned long ClusterNodeCloseEnumEx(_HNODEENUMEX *),0>::Close(v2);
    *v2 = v6;
    if ( (((unsigned __int64)v6 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      return GetLastError();
  }
  return v3;
}

```

## disassembly

```asm
0x18002e380  mov     [rsp+arg_0], rbx
0x18002e385  mov     [rsp+arg_8], rsi
0x18002e38a  push    rdi
0x18002e38b  sub     rsp, 20h
0x18002e38f  lea     rsi, [rcx+20h]
0x18002e393  xor     edi, edi
0x18002e395  mov     rax, [rsi]
0x18002e398  mov     ebx, edx
0x18002e39a  inc     rax
0x18002e39d  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002e3a3  jnz     short loc_18002E3E8
0x18002e3a5  mov     rcx, [rcx+30h]
0x18002e3a9  mov     rax, [rcx]
0x18002e3ac  mov     rax, [rax+98h]
0x18002e3b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e3b8  mov     rcx, rax; hNode
0x18002e3bb  xor     r8d, r8d; pOptions
0x18002e3be  mov     edx, ebx; dwType
0x18002e3c0  call    cs:__imp_ClusterNodeOpenEnumEx
0x18002e3c6  mov     rcx, rsi
0x18002e3c9  mov     rbx, rax
0x18002e3cc  call    ?Close@?$AutoHandle@PEAU_HNODEENUMEX@@K$1?ClusterNodeCloseEnumEx@@YAKPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HNODEENUMEX *,ulong,&ClusterNodeCloseEnumEx(_HNODEENUMEX *),0>::Close(void)
0x18002e3d1  lea     rax, [rbx+1]
0x18002e3d5  mov     [rsi], rbx
0x18002e3d8  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002e3de  jnz     short loc_18002E3E8
0x18002e3e0  call    cs:__imp_GetLastError
0x18002e3e6  mov     edi, eax
0x18002e3e8  mov     rbx, [rsp+28h+arg_0]
0x18002e3ed  mov     eax, edi
0x18002e3ef  mov     rsi, [rsp+28h+arg_8]
0x18002e3f4  add     rsp, 20h
0x18002e3f8  pop     rdi
0x18002e3f9  retn
```
