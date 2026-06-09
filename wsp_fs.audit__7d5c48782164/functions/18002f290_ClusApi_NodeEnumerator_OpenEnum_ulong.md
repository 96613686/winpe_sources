# ClusApi::NodeEnumerator::OpenEnum(ulong)

- ea: `0x18002f290`
- end: `0x18002f317`
- name: `?OpenEnum@NodeEnumerator@ClusApi@@MEAAKK@Z`
- size: `135`
- prototype: `unsigned int(ClusApi::NodeEnumerator *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002e84c`
- `0x18002f290`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f2f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f2f6`
- `CLUSAPI!ClusterNodeOpenEnumEx` at `0x18002f2d0`
- `CLUSAPI!ClusterNodeOpenEnumEx` at `0x18002f2d0`

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
0x18002f290  mov     [rsp+arg_0], rbx
0x18002f295  mov     [rsp+arg_8], rsi
0x18002f29a  push    rdi
0x18002f29b  sub     rsp, 20h
0x18002f29f  lea     rsi, [rcx+20h]
0x18002f2a3  xor     edi, edi
0x18002f2a5  mov     rax, [rsi]
0x18002f2a8  mov     ebx, edx
0x18002f2aa  inc     rax
0x18002f2ad  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002f2b3  jnz     short loc_18002F304
0x18002f2b5  mov     rcx, [rcx+30h]
0x18002f2b9  mov     rax, [rcx]
0x18002f2bc  mov     rax, [rax+98h]
0x18002f2c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f2c8  mov     rcx, rax; hNode
0x18002f2cb  xor     r8d, r8d; pOptions
0x18002f2ce  mov     edx, ebx; dwType
0x18002f2d0  call    cs:__imp_ClusterNodeOpenEnumEx
0x18002f2d7  nop     dword ptr [rax+rax+00h]
0x18002f2dc  mov     rcx, rsi
0x18002f2df  mov     rbx, rax
0x18002f2e2  call    ?Close@?$AutoHandle@PEAU_HNODEENUMEX@@K$1?ClusterNodeCloseEnumEx@@YAKPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HNODEENUMEX *,ulong,&ClusterNodeCloseEnumEx(_HNODEENUMEX *),0>::Close(void)
0x18002f2e7  lea     rax, [rbx+1]
0x18002f2eb  mov     [rsi], rbx
0x18002f2ee  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002f2f4  jnz     short loc_18002F304
0x18002f2f6  call    cs:__imp_GetLastError
0x18002f2fd  nop     dword ptr [rax+rax+00h]
0x18002f302  mov     edi, eax
0x18002f304  mov     rbx, [rsp+28h+arg_0]
0x18002f309  mov     eax, edi
0x18002f30b  mov     rsi, [rsp+28h+arg_8]
0x18002f310  add     rsp, 20h
0x18002f314  pop     rdi
0x18002f315  retn
```
