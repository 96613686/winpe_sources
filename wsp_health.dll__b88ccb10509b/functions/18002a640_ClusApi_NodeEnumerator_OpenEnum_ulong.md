# ClusApi::NodeEnumerator::OpenEnum(ulong)

- ea: `0x18002a640`
- end: `0x18002a6ba`
- name: `?OpenEnum@NodeEnumerator@ClusApi@@MEAAKK@Z`
- size: `122`
- prototype: `unsigned int(ClusApi::NodeEnumerator *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180029ca8`
- `0x18002a640`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a6a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a6a0`
- `CLUSAPI!ClusterNodeOpenEnumEx` at `0x18002a680`
- `CLUSAPI!ClusterNodeOpenEnumEx` at `0x18002a680`

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
0x18002a640  mov     [rsp+arg_0], rbx
0x18002a645  mov     [rsp+arg_8], rsi
0x18002a64a  push    rdi
0x18002a64b  sub     rsp, 20h
0x18002a64f  lea     rsi, [rcx+20h]
0x18002a653  xor     edi, edi
0x18002a655  mov     rax, [rsi]
0x18002a658  mov     ebx, edx
0x18002a65a  inc     rax
0x18002a65d  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002a663  jnz     short loc_18002A6A8
0x18002a665  mov     rcx, [rcx+30h]
0x18002a669  mov     rax, [rcx]
0x18002a66c  mov     rax, [rax+98h]
0x18002a673  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a678  mov     rcx, rax; hNode
0x18002a67b  xor     r8d, r8d; pOptions
0x18002a67e  mov     edx, ebx; dwType
0x18002a680  call    cs:__imp_ClusterNodeOpenEnumEx
0x18002a686  mov     rcx, rsi
0x18002a689  mov     rbx, rax
0x18002a68c  call    ?Close@?$AutoHandle@PEAU_HNODEENUMEX@@K$1?ClusterNodeCloseEnumEx@@YAKPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HNODEENUMEX *,ulong,&ClusterNodeCloseEnumEx(_HNODEENUMEX *),0>::Close(void)
0x18002a691  lea     rax, [rbx+1]
0x18002a695  mov     [rsi], rbx
0x18002a698  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002a69e  jnz     short loc_18002A6A8
0x18002a6a0  call    cs:__imp_GetLastError
0x18002a6a6  mov     edi, eax
0x18002a6a8  mov     rbx, [rsp+28h+arg_0]
0x18002a6ad  mov     eax, edi
0x18002a6af  mov     rsi, [rsp+28h+arg_8]
0x18002a6b4  add     rsp, 20h
0x18002a6b8  pop     rdi
0x18002a6b9  retn
```
