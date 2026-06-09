# CWdsTptNamespaceStore::CreateInstance(ushort const *,ushort const *,CWdsTptNamespaceStore * *)

- ea: `0x18001a9ec`
- end: `0x18001aaad`
- name: `?CreateInstance@CWdsTptNamespaceStore@@SAKPEBG0PEAPEAV1@@Z`
- size: `193`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, const unsigned __int16 *, struct CWdsTptNamespaceStore **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task`

## callers

- `0x1800053a0`

## callees

- `0x18001a9a8`
- `0x18001a9ec`
- `0x18001b8b4`
- `0x180025850`
- `0x1800266a0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001aa8d`
- `KERNEL32!DeleteCriticalSection` at `0x18001aa8d`
- `KERNEL32!InitializeCriticalSection` at `0x18001aa29`
- `KERNEL32!InitializeCriticalSection` at `0x18001aa29`
- `ADVAPI32!RegCloseKey` at `0x18001aa7e`
- `ADVAPI32!RegCloseKey` at `0x18001aa7e`

## string_xrefs

- `0x18001aa45`: `System\CurrentControlSet\Services\WDSServer\Providers\WDSMC\Namespaces`

## pseudocode

```c
__int64 __fastcall CWdsTptNamespaceStore::CreateInstance(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        struct CWdsTptNamespaceStore **a3)
{
  unsigned int v4; // edi
  char *v5; // rax
  const unsigned __int16 *v6; // rdx
  char *v7; // rbx
  const char *v8; // rdx
  HKEY v9; // rcx

  if ( a3 )
  {
    v5 = (char *)operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
    v7 = v5;
    if ( v5 )
    {
      InitializeCriticalSection((LPCRITICAL_SECTION)(v5 + 8));
      *((_QWORD *)v7 + 6) = 0;
      *(_DWORD *)v7 = 0;
    }
    else
    {
      v7 = 0;
    }
    if ( v7 )
    {
      v4 = CWdsTptNamespaceStore::Initialize(
             (CWdsTptNamespaceStore *)v7,
             v6,
             L"System\\CurrentControlSet\\Services\\WDSServer\\Providers\\WDSMC\\Namespaces");
      if ( !ElValidateWin32(v4, v8, "base\\eco\\wds\\wdsnsstore\\src\\wdstptnamespacestore.cpp", 0x72u) )
        *a3 = (struct CWdsTptNamespaceStore *)v7;
      if ( v4 )
      {
        v9 = (HKEY)*((_QWORD *)v7 + 6);
        if ( v9 )
        {
          RegCloseKey(v9);
          *((_QWORD *)v7 + 6) = 0;
        }
        DeleteCriticalSection((LPCRITICAL_SECTION)(v7 + 8));
        operator delete(v7);
      }
    }
    else
    {
      return 8;
    }
  }
  else
  {
    return 87;
  }
  return v4;
}

```

## disassembly

```asm
0x18001a9ec  mov     [rsp+arg_0], rbx
0x18001a9f1  mov     [rsp+arg_8], rsi
0x18001a9f6  push    rdi
0x18001a9f7  sub     rsp, 20h
0x18001a9fb  mov     rsi, r8
0x18001a9fe  test    r8, r8
0x18001aa01  jnz     short loc_18001AA0C
0x18001aa03  lea     edi, [r8+57h]
0x18001aa07  jmp     loc_18001AA9B
0x18001aa0c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001aa13  mov     ecx, 38h ; '8'; unsigned __int64
0x18001aa18  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001aa1d  mov     rbx, rax
0x18001aa20  test    rax, rax
0x18001aa23  jz      short loc_18001AA39
0x18001aa25  lea     rcx, [rax+8]; lpCriticalSection
0x18001aa29  call    cs:__imp_InitializeCriticalSection
0x18001aa2f  and     qword ptr [rbx+30h], 0
0x18001aa34  and     dword ptr [rbx], 0
0x18001aa37  jmp     short loc_18001AA3B
0x18001aa39  xor     ebx, ebx
0x18001aa3b  test    rbx, rbx
0x18001aa3e  jnz     short loc_18001AA45
0x18001aa40  lea     edi, [rbx+8]
0x18001aa43  jmp     short loc_18001AA9B
0x18001aa45  lea     r8, aSystemCurrentc; "System\\CurrentControlSet\\Services\\WD"...
0x18001aa4c  mov     rcx, rbx; this
0x18001aa4f  call    ?Initialize@CWdsTptNamespaceStore@@AEAAKPEBG0@Z; CWdsTptNamespaceStore::Initialize(ushort const *,ushort const *)
0x18001aa54  mov     r9d, 72h ; 'r'; unsigned int
0x18001aa5a  lea     r8, aBaseEcoWdsWdsn; "base\\eco\\wds\\wdsnsstore\\src\\wdstpt"...
0x18001aa61  mov     ecx, eax; unsigned int
0x18001aa63  mov     edi, eax
0x18001aa65  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001aa6a  test    eax, eax
0x18001aa6c  jnz     short loc_18001AA71
0x18001aa6e  mov     [rsi], rbx
0x18001aa71  test    edi, edi
0x18001aa73  jz      short loc_18001AA9B
0x18001aa75  mov     rcx, [rbx+30h]; hKey
0x18001aa79  test    rcx, rcx
0x18001aa7c  jz      short loc_18001AA89
0x18001aa7e  call    cs:__imp_RegCloseKey
0x18001aa84  and     qword ptr [rbx+30h], 0
0x18001aa89  lea     rcx, [rbx+8]; lpCriticalSection
0x18001aa8d  call    cs:__imp_DeleteCriticalSection
0x18001aa93  mov     rcx, rbx; void *
0x18001aa96  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001aa9b  mov     rbx, [rsp+28h+arg_0]
0x18001aaa0  mov     eax, edi
0x18001aaa2  mov     rsi, [rsp+28h+arg_8]
0x18001aaa7  add     rsp, 20h
0x18001aaab  pop     rdi
0x18001aaac  retn
```
