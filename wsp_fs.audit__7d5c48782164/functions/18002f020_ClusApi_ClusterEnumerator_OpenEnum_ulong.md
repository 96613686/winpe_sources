# ClusApi::ClusterEnumerator::OpenEnum(ulong)

- ea: `0x18002f020`
- end: `0x18002f0a7`
- name: `?OpenEnum@ClusterEnumerator@ClusApi@@MEAAKK@Z`
- size: `135`
- prototype: `unsigned int(ClusApi::ClusterEnumerator *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002e76c`
- `0x18002f020`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f086`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f086`
- `CLUSAPI!ClusterOpenEnumEx` at `0x18002f060`
- `CLUSAPI!ClusterOpenEnumEx` at `0x18002f060`

## pseudocode

```c
__int64 __fastcall ClusApi::ClusterEnumerator::OpenEnum(ClusApi::ClusterEnumerator *this, DWORD a2)
{
  HCLUSENUMEX *v2; // rsi
  unsigned int v3; // edi
  struct _HCLUSTER *v5; // rax
  HCLUSENUMEX v6; // rbx

  v2 = (HCLUSENUMEX *)((char *)this + 32);
  v3 = 0;
  if ( ((*((_QWORD *)this + 4) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v5 = (struct _HCLUSTER *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 392LL))(*((_QWORD *)this + 6));
    v6 = ClusterOpenEnumEx(v5, a2, 0);
    cxl::AutoHandle<_HCLUSENUMEX *,unsigned long,&unsigned long ClusterCloseEnumEx(_HCLUSENUMEX *),0>::Close(v2);
    *v2 = v6;
    if ( (((unsigned __int64)v6 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      return GetLastError();
  }
  return v3;
}

```

## disassembly

```asm
0x18002f020  mov     [rsp+arg_0], rbx
0x18002f025  mov     [rsp+arg_8], rsi
0x18002f02a  push    rdi
0x18002f02b  sub     rsp, 20h
0x18002f02f  lea     rsi, [rcx+20h]
0x18002f033  xor     edi, edi
0x18002f035  mov     rax, [rsi]
0x18002f038  mov     ebx, edx
0x18002f03a  inc     rax
0x18002f03d  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002f043  jnz     short loc_18002F094
0x18002f045  mov     rcx, [rcx+30h]
0x18002f049  mov     rax, [rcx]
0x18002f04c  mov     rax, [rax+188h]
0x18002f053  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f058  mov     rcx, rax; hCluster
0x18002f05b  xor     r8d, r8d; pOptions
0x18002f05e  mov     edx, ebx; dwType
0x18002f060  call    cs:__imp_ClusterOpenEnumEx
0x18002f067  nop     dword ptr [rax+rax+00h]
0x18002f06c  mov     rcx, rsi
0x18002f06f  mov     rbx, rax
0x18002f072  call    ?Close@?$AutoHandle@PEAU_HCLUSENUMEX@@K$1?ClusterCloseEnumEx@@YAKPEAU1@@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<_HCLUSENUMEX *,ulong,&ClusterCloseEnumEx(_HCLUSENUMEX *),0>::Close(void)
0x18002f077  lea     rax, [rbx+1]
0x18002f07b  mov     [rsi], rbx
0x18002f07e  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002f084  jnz     short loc_18002F094
0x18002f086  call    cs:__imp_GetLastError
0x18002f08d  nop     dword ptr [rax+rax+00h]
0x18002f092  mov     edi, eax
0x18002f094  mov     rbx, [rsp+28h+arg_0]
0x18002f099  mov     eax, edi
0x18002f09b  mov     rsi, [rsp+28h+arg_8]
0x18002f0a0  add     rsp, 20h
0x18002f0a4  pop     rdi
0x18002f0a5  retn
```
