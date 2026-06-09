# SBFThunk::Cv1RecAttributes::TableIsValid(ISBFTable *)

- ea: `0x18004d810`
- end: `0x18004d93f`
- name: `?TableIsValid@Cv1RecAttributes@SBFThunk@@AEAAHPEAUISBFTable@@@Z`
- size: `303`
- prototype: `__int64 __fastcall(SBFThunk::Cv1RecAttributes *__hidden this, struct ISBFTable *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18004ad1c`

## callees

- `0x180001c00`
- `0x180002e68`
- `0x18004d810`
- `0x180057140`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x18004d8ac`
- `KERNEL32!lstrcmpiW` at `0x18004d8eb`
- `KERNEL32!lstrcmpiW` at `0x18004d8ac`
- `KERNEL32!lstrcmpiW` at `0x18004d8eb`
- `ole32!CoTaskMemFree` at `0x18004d911`
- `ole32!CoTaskMemFree` at `0x18004d91b`
- `ole32!CoTaskMemFree` at `0x18004d911`
- `ole32!CoTaskMemFree` at `0x18004d91b`

## pseudocode

```c
__int64 __fastcall SBFThunk::Cv1RecAttributes::TableIsValid(SBFThunk::Cv1RecAttributes *this, struct ISBFTable *a2)
{
  __int64 v2; // rax
  unsigned int v3; // edi
  const WCHAR *v4; // rbx
  int v6; // [rsp+20h] [rbp-30h]
  int v7; // [rsp+20h] [rbp-30h]
  LPCWSTR lpString1; // [rsp+30h] [rbp-20h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-18h] BYREF
  unsigned int v10; // [rsp+40h] [rbp-10h] BYREF

  v2 = *(_QWORD *)a2;
  v10 = 0;
  pv = 0;
  lpString1 = 0;
  v3 = 0;
  if ( (*(int (__fastcall **)(struct ISBFTable *, LPCWSTR *, unsigned int *, LPVOID *))(v2 + 24))(
         a2,
         &lpString1,
         &v10,
         &pv) >= 0
    && v10 >= 0x50
    && *(_DWORD *)pv == -1
    && !*((_DWORD *)pv + 1) )
  {
    v4 = (const WCHAR *)((char *)pv + 16);
    if ( (int)StringCchLengthW((const unsigned __int16 *)pv + 8, 0x20u, 0) >= 0 )
    {
      if ( lstrcmpiW(v4, L"legacy_attrib") )
      {
        v6 = 3786;
        CSbeFileLog::LogEvent(
          0x10u,
          1u,
          L"%s(%d) : bad table name: \"%s\"",
          L"multimedia\\dshow\\filters\\sbe\\dvrfilters\\shared\\v2thunk.cpp",
          v6,
          v4);
      }
      else if ( lstrcmpiW(lpString1, L"legacy_attrib") )
      {
        v7 = 3794;
        CSbeFileLog::LogEvent(
          0x10u,
          1u,
          L"%s(%d) : bad table name: \"%s\"",
          L"multimedia\\dshow\\filters\\sbe\\dvrfilters\\shared\\v2thunk.cpp",
          v7,
          lpString1);
      }
      else
      {
        v3 = 1;
      }
    }
  }
  CoTaskMemFree(pv);
  CoTaskMemFree((LPVOID)lpString1);
  return v3;
}

```

## disassembly

```asm
0x18004d810  mov     [rsp-8+arg_0], rbx
0x18004d815  mov     [rsp-8+arg_10], rdi
0x18004d81a  push    rbp
0x18004d81b  mov     rbp, rsp
0x18004d81e  sub     rsp, 50h
0x18004d822  mov     rax, cs:__security_cookie
0x18004d829  xor     rax, rsp
0x18004d82c  mov     [rbp+var_8], rax
0x18004d830  mov     rax, [rdx]
0x18004d833  lea     r9, [rbp+pv]
0x18004d837  mov     rcx, rdx
0x18004d83a  mov     [rbp+var_10], 0
0x18004d841  lea     r8, [rbp+var_10]
0x18004d845  mov     [rbp+pv], 0
0x18004d84d  lea     rdx, [rbp+lpString1]
0x18004d851  mov     [rbp+lpString1], 0
0x18004d859  mov     rax, [rax+18h]
0x18004d85d  xor     edi, edi
0x18004d85f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d864  test    eax, eax
0x18004d866  js      loc_18004D90D
0x18004d86c  cmp     [rbp+var_10], 50h ; 'P'
0x18004d870  jb      loc_18004D90D
0x18004d876  mov     rax, [rbp+pv]
0x18004d87a  cmp     dword ptr [rax], 0FFFFFFFFh
0x18004d87d  jnz     loc_18004D90D
0x18004d883  cmp     [rax+4], edi
0x18004d886  jnz     loc_18004D90D
0x18004d88c  lea     rbx, [rax+10h]
0x18004d890  xor     r8d, r8d; unsigned __int64 *
0x18004d893  mov     rcx, rbx; unsigned __int16 *
0x18004d896  lea     edx, [rdi+20h]; unsigned __int64
0x18004d899  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18004d89e  test    eax, eax
0x18004d8a0  js      short loc_18004D90D
0x18004d8a2  lea     rdx, aLegacyAttrib; "legacy_attrib"
0x18004d8a9  mov     rcx, rbx; lpString1
0x18004d8ac  call    cs:__imp_lstrcmpiW
0x18004d8b2  test    eax, eax
0x18004d8b4  jz      short loc_18004D8E0
0x18004d8b6  mov     [rsp+50h+var_28], rbx
0x18004d8bb  mov     [rsp+50h+var_30], 0ECAh
0x18004d8c3  mov     edx, 1; unsigned __int8
0x18004d8c8  lea     r9, aMultimediaDsho_12; "multimedia\\dshow\\filters\\sbe\\dvrfil"...
0x18004d8cf  lea     r8, aSDBadTableName; "%s(%d) : bad table name: \"%s\""
0x18004d8d6  lea     ecx, [rdx+0Fh]; unsigned int
0x18004d8d9  call    ?LogEvent@CSbeFileLog@@SAJKEPEBGZZ; CSbeFileLog::LogEvent(ulong,uchar,ushort const *,...)
0x18004d8de  jmp     short loc_18004D90D
0x18004d8e0  mov     rcx, [rbp+lpString1]; lpString1
0x18004d8e4  lea     rdx, aLegacyAttrib; "legacy_attrib"
0x18004d8eb  call    cs:__imp_lstrcmpiW
0x18004d8f1  test    eax, eax
0x18004d8f3  jz      short loc_18004D908
0x18004d8f5  mov     rax, [rbp+lpString1]
0x18004d8f9  mov     [rsp+50h+var_28], rax
0x18004d8fe  mov     [rsp+50h+var_30], 0ED2h
0x18004d906  jmp     short loc_18004D8C3
0x18004d908  mov     edi, 1
0x18004d90d  mov     rcx, [rbp+pv]; pv
0x18004d911  call    cs:__imp_CoTaskMemFree
0x18004d917  mov     rcx, [rbp+lpString1]; pv
0x18004d91b  call    cs:__imp_CoTaskMemFree
0x18004d921  mov     eax, edi
0x18004d923  mov     rcx, [rbp+var_8]
0x18004d927  xor     rcx, rsp; StackCookie
0x18004d92a  call    __security_check_cookie
0x18004d92f  mov     rbx, [rsp+50h+arg_0]
0x18004d934  mov     rdi, [rsp+50h+arg_10]
0x18004d939  add     rsp, 50h
0x18004d93d  pop     rbp
0x18004d93e  retn
```
