# ClusApi::NodeEnumerator::OpenEnum(ulong)

- ea: `0x18002b450`
- end: `0x18002b4d7`
- name: `?OpenEnum@NodeEnumerator@ClusApi@@MEAAKK@Z`
- size: `135`
- prototype: `unsigned int(ClusApi::NodeEnumerator *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002aa0c`
- `0x18002b450`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b4b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b4b6`
- `CLUSAPI!ClusterNodeOpenEnumEx` at `0x18002b490`
- `CLUSAPI!ClusterNodeOpenEnumEx` at `0x18002b490`

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
0x18002b450  mov     [rsp+arg_0], rbx
0x18002b455  mov     [rsp+arg_8], rsi
0x18002b45a  push    rdi
0x18002b45b  sub     rsp, 20h
0x18002b45f  lea     rsi, [rcx+20h]
0x18002b463  xor     edi, edi
0x18002b465  mov     rax, [rsi]
0x18002b468  mov     ebx, edx
0x18002b46a  inc     rax
0x18002b46d  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002b473  jnz     short loc_18002B4C4
0x18002b475  mov     rcx, [rcx+30h]
0x18002b479  mov     rax, [rcx]
0x18002b47c  mov     rax, [rax+98h]
0x18002b483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b488  mov     rcx, rax; hNode
0x18002b48b  xor     r8d, r8d; pOptions
0x18002b48e  mov     edx, ebx; dwType
0x18002b490  call    cs:__imp_ClusterNodeOpenEnumEx
0x18002b497  nop     dword ptr [rax+rax+00h]
0x18002b49c  mov     rcx, rsi
0x18002b49f  mov     rbx, rax
0x18002b4a2  call    ?Close@?$AutoHandle@PEAU_HNODEENUMEX@@K$1?ClusterNodeCloseEnumEx@@YAKPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HNODEENUMEX *,ulong,&ClusterNodeCloseEnumEx(_HNODEENUMEX *),0>::Close(void)
0x18002b4a7  lea     rax, [rbx+1]
0x18002b4ab  mov     [rsi], rbx
0x18002b4ae  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002b4b4  jnz     short loc_18002B4C4
0x18002b4b6  call    cs:__imp_GetLastError
0x18002b4bd  nop     dword ptr [rax+rax+00h]
0x18002b4c2  mov     edi, eax
0x18002b4c4  mov     rbx, [rsp+28h+arg_0]
0x18002b4c9  mov     eax, edi
0x18002b4cb  mov     rsi, [rsp+28h+arg_8]
0x18002b4d0  add     rsp, 20h
0x18002b4d4  pop     rdi
0x18002b4d5  retn
```
