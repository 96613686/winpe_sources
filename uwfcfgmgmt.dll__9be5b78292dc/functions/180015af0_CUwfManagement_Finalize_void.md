# CUwfManagement::Finalize(void)

- ea: `0x180015af0`
- end: `0x180015bad`
- name: `?Finalize@CUwfManagement@@QEAAJXZ`
- size: `189`
- prototype: `__int64 __fastcall(CUwfManagement *this, __int64)`
- caller_count: `21`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180017230`
- `0x180017be0`
- `0x1800181a0`
- `0x180018240`
- `0x1800184b0`
- `0x1800187b0`
- `0x180018830`
- `0x180018f50`
- `0x180018fe0`
- `0x180019110`
- `0x180019600`
- `0x1800198d0`
- `0x180019940`
- `0x1800199b0`
- `0x180019d70`
- `0x180019df0`
- `0x18001a1a0`
- `0x18001a240`
- `0x18001a920`
- `0x18001a9a0`
- `0x18001aa94`

## callees

- `0x180015af0`
- `0x180016664`

## import_xrefs

- `ntdll!NtRollbackTransaction` at `0x180015b41`
- `ntdll!NtRollbackTransaction` at `0x180015b41`
- `ntdll!NtCommitTransaction` at `0x180015b1e`
- `ntdll!NtCommitTransaction` at `0x180015b1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015b61`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015b7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015b61`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015b7f`

## pseudocode

```c
__int64 __fastcall CUwfManagement::Finalize(CUwfManagement *this, __int64 a2)
{
  int v2; // edi
  __int64 v4; // rcx
  BOOL v5; // esi
  unsigned int v6; // eax
  unsigned int v7; // eax
  void *v8; // rcx
  __int64 result; // rax

  v2 = 0;
  v4 = *((_QWORD *)this + 2);
  v5 = 1;
  if ( v4 != -1 )
  {
    if ( *((int *)this + 3) < 0 || *((int *)this + 24) < 0 )
    {
      LOBYTE(a2) = 1;
      v7 = NtRollbackTransaction(v4, a2);
      if ( (v7 & 0xC0000000) == 0xC0000000 )
        v2 = wil::details::NtStatusToHr((wil::details *)v7, -1073741824);
      goto LABEL_9;
    }
    LOBYTE(a2) = 1;
    v6 = NtCommitTransaction(v4, a2);
    if ( (v6 & 0xC0000000) != 0xC0000000 || (v2 = wil::details::NtStatusToHr((wil::details *)v6, -1073741824), v2 >= 0) )
    {
LABEL_9:
      v5 = CloseHandle(*((HANDLE *)this + 2));
      *((_QWORD *)this + 2) = -1;
    }
  }
  v8 = (void *)*((_QWORD *)this + 2);
  if ( v8 != (void *)-1LL && !v5 )
  {
    CloseHandle(v8);
    *((_QWORD *)this + 2) = -1;
  }
  result = (unsigned int)v2;
  *((_DWORD *)this + 3) = 0;
  *((_DWORD *)this + 24) = 0;
  return result;
}

```

## disassembly

```asm
0x180015af0  mov     [rsp+arg_0], rbx
0x180015af5  mov     [rsp+arg_8], rsi
0x180015afa  push    rdi
0x180015afb  sub     rsp, 20h
0x180015aff  xor     edi, edi
0x180015b01  mov     rbx, rcx
0x180015b04  mov     rcx, [rcx+10h]
0x180015b08  lea     esi, [rdi+1]
0x180015b0b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180015b0f  jz      short loc_180015B71
0x180015b11  cmp     [rbx+0Ch], edi
0x180015b14  jl      short loc_180015B3E
0x180015b16  cmp     [rbx+60h], edi
0x180015b19  jl      short loc_180015B3E
0x180015b1b  mov     dl, sil
0x180015b1e  call    cs:__imp_NtCommitTransaction
0x180015b24  mov     edx, 0C0000000h; int
0x180015b29  mov     ecx, eax; this
0x180015b2b  and     eax, edx
0x180015b2d  cmp     eax, edx
0x180015b2f  jnz     short loc_180015B5D
0x180015b31  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180015b36  mov     edi, eax
0x180015b38  test    eax, eax
0x180015b3a  js      short loc_180015B71
0x180015b3c  jmp     short loc_180015B5D
0x180015b3e  mov     dl, sil
0x180015b41  call    cs:__imp_NtRollbackTransaction
0x180015b47  mov     edx, 0C0000000h; int
0x180015b4c  mov     ecx, eax
0x180015b4e  and     ecx, edx
0x180015b50  cmp     ecx, edx
0x180015b52  jnz     short loc_180015B5D
0x180015b54  mov     ecx, eax; this
0x180015b56  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180015b5b  mov     edi, eax
0x180015b5d  mov     rcx, [rbx+10h]; hObject
0x180015b61  call    cs:__imp_CloseHandle
0x180015b67  mov     esi, eax
0x180015b69  mov     qword ptr [rbx+10h], 0FFFFFFFFFFFFFFFFh
0x180015b71  mov     rcx, [rbx+10h]; hObject
0x180015b75  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180015b79  jz      short loc_180015B8D
0x180015b7b  test    esi, esi
0x180015b7d  jnz     short loc_180015B8D
0x180015b7f  call    cs:__imp_CloseHandle
0x180015b85  mov     qword ptr [rbx+10h], 0FFFFFFFFFFFFFFFFh
0x180015b8d  mov     rsi, [rsp+28h+arg_8]
0x180015b92  mov     eax, edi
0x180015b94  mov     dword ptr [rbx+0Ch], 0
0x180015b9b  mov     dword ptr [rbx+60h], 0
0x180015ba2  mov     rbx, [rsp+28h+arg_0]
0x180015ba7  add     rsp, 20h
0x180015bab  pop     rdi
0x180015bac  retn
```
