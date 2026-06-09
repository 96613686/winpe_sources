# SBF2::CComSBFTable::GetInfo(ushort * *,ulong *,uchar * *)

- ea: `0x18009d8e0`
- end: `0x18009d9eb`
- name: `?GetInfo@CComSBFTable@SBF2@@UEAAJPEAPEAGPEAKPEAPEAE@Z`
- size: `267`
- prototype: `int(SBF2::CComSBFTable *__hidden this, unsigned __int16 **, unsigned int *, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002e68`
- `0x18000624c`
- `0x18009d8e0`
- `0x1800a7a1c`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18009d943`
- `ole32!CoTaskMemAlloc` at `0x18009d992`
- `ole32!CoTaskMemAlloc` at `0x18009d943`
- `ole32!CoTaskMemAlloc` at `0x18009d992`
- `ole32!CoTaskMemFree` at `0x18009d9b8`
- `ole32!CoTaskMemFree` at `0x18009d9c8`
- `ole32!CoTaskMemFree` at `0x18009d9b8`
- `ole32!CoTaskMemFree` at `0x18009d9c8`

## pseudocode

```c
__int64 __fastcall SBF2::CComSBFTable::GetInfo(const unsigned __int16 **this, LPVOID *a2, unsigned int *a3, LPVOID *a4)
{
  int Header; // ebx
  unsigned __int8 *v9; // rax
  unsigned __int64 v10; // rbx
  unsigned __int16 *v11; // rax
  unsigned __int64 v13; // [rsp+70h] [rbp+18h] BYREF

  v13 = 0;
  if ( a3 && a2 && a4 )
  {
    *a4 = 0;
    *a2 = 0;
    Header = SBF2::CSBFSALIndex::GetHeader((SBF2::CSBFSALIndex *)(this + 1), a3, 0);
    if ( Header >= 0 )
    {
      v9 = (unsigned __int8 *)CoTaskMemAlloc(*a3);
      *a4 = v9;
      if ( !v9 )
        goto LABEL_6;
      Header = SBF2::CSBFSALIndex::GetHeader((SBF2::CSBFSALIndex *)(this + 1), a3, v9);
      if ( Header < 0 )
        goto LABEL_11;
      Header = StringCchLengthW(this[6], 0x104u, &v13);
      if ( Header < 0 )
        goto LABEL_11;
      v10 = v13 + 1;
      v11 = (unsigned __int16 *)CoTaskMemAlloc(2 * (v13 + 1));
      *a2 = v11;
      if ( v11 )
      {
        Header = StringCchCopyW(v11, v10, this[6]);
        if ( Header >= 0 )
          return (unsigned int)Header;
      }
      else
      {
LABEL_6:
        Header = -2147024882;
      }
    }
LABEL_11:
    CoTaskMemFree(*a4);
    *a4 = 0;
    CoTaskMemFree(*a2);
    *a2 = 0;
    return (unsigned int)Header;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x18009d8e0  push    rbx
0x18009d8e2  push    rbp
0x18009d8e3  push    rsi
0x18009d8e4  push    rdi
0x18009d8e5  push    r14
0x18009d8e7  push    r15
0x18009d8e9  sub     rsp, 28h
0x18009d8ed  mov     [rsp+58h+arg_10], 0
0x18009d8f6  mov     rdi, r9
0x18009d8f9  mov     rbp, r8
0x18009d8fc  mov     rsi, rdx
0x18009d8ff  mov     r14, rcx
0x18009d902  test    r8, r8
0x18009d905  jz      loc_18009D9D9
0x18009d90b  test    rdx, rdx
0x18009d90e  jz      loc_18009D9D9
0x18009d914  test    r9, r9
0x18009d917  jz      loc_18009D9D9
0x18009d91d  mov     qword ptr [r9], 0
0x18009d924  xor     r8d, r8d; unsigned __int8 *
0x18009d927  mov     qword ptr [rdx], 0
0x18009d92e  add     rcx, 8; this
0x18009d932  mov     rdx, rbp; unsigned int *
0x18009d935  call    ?GetHeader@CSBFSALIndex@SBF2@@QEAAJPEAKPEAE@Z; SBF2::CSBFSALIndex::GetHeader(ulong *,uchar *)
0x18009d93a  mov     ebx, eax
0x18009d93c  test    eax, eax
0x18009d93e  js      short loc_18009D9B5
0x18009d940  mov     ecx, [rbp+0]; cb
0x18009d943  call    cs:__imp_CoTaskMemAlloc
0x18009d949  mov     [rdi], rax
0x18009d94c  test    rax, rax
0x18009d94f  jnz     short loc_18009D958
0x18009d951  mov     ebx, 8007000Eh
0x18009d956  jmp     short loc_18009D9B5
0x18009d958  mov     r8, rax; unsigned __int8 *
0x18009d95b  lea     rcx, [r14+8]; this
0x18009d95f  mov     rdx, rbp; unsigned int *
0x18009d962  call    ?GetHeader@CSBFSALIndex@SBF2@@QEAAJPEAKPEAE@Z; SBF2::CSBFSALIndex::GetHeader(ulong *,uchar *)
0x18009d967  mov     ebx, eax
0x18009d969  test    eax, eax
0x18009d96b  js      short loc_18009D9B5
0x18009d96d  mov     rcx, [r14+30h]; unsigned __int16 *
0x18009d971  lea     r8, [rsp+58h+arg_10]; unsigned __int64 *
0x18009d976  mov     edx, 104h; unsigned __int64
0x18009d97b  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18009d980  mov     ebx, eax
0x18009d982  test    eax, eax
0x18009d984  js      short loc_18009D9B5
0x18009d986  mov     rbx, [rsp+58h+arg_10]
0x18009d98b  inc     rbx
0x18009d98e  lea     rcx, [rbx+rbx]; cb
0x18009d992  call    cs:__imp_CoTaskMemAlloc
0x18009d998  mov     [rsi], rax
0x18009d99b  test    rax, rax
0x18009d99e  jz      short loc_18009D951
0x18009d9a0  mov     r8, [r14+30h]; unsigned __int16 *
0x18009d9a4  mov     rdx, rbx; unsigned __int64
0x18009d9a7  mov     rcx, rax; unsigned __int16 *
0x18009d9aa  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18009d9af  mov     ebx, eax
0x18009d9b1  test    eax, eax
0x18009d9b3  jns     short loc_18009D9D5
0x18009d9b5  mov     rcx, [rdi]; pv
0x18009d9b8  call    cs:__imp_CoTaskMemFree
0x18009d9be  mov     qword ptr [rdi], 0
0x18009d9c5  mov     rcx, [rsi]; pv
0x18009d9c8  call    cs:__imp_CoTaskMemFree
0x18009d9ce  mov     qword ptr [rsi], 0
0x18009d9d5  mov     eax, ebx
0x18009d9d7  jmp     short loc_18009D9DE
0x18009d9d9  mov     eax, 80004003h
0x18009d9de  add     rsp, 28h
0x18009d9e2  pop     r15
0x18009d9e4  pop     r14
0x18009d9e6  pop     rdi
0x18009d9e7  pop     rsi
0x18009d9e8  pop     rbp
0x18009d9e9  pop     rbx
0x18009d9ea  retn
```
