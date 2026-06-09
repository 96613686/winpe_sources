# CListenerEx::GetSecurityDescriptor(uchar * *,ulong *)

- ea: `0x1800158e0`
- end: `0x1800159cf`
- name: `?GetSecurityDescriptor@CListenerEx@@UEAAJPEAPEAEPEAK@Z`
- size: `239`
- prototype: `__int64 __fastcall(CListenerEx *__hidden this, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000a210`
- `0x1800158e0`
- `0x180032700`
- `0x1800c4e0c`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x1800159b7`
- `ntdll!RtlReleaseResource` at `0x1800159b7`
- `ntdll!RtlAcquireResourceShared` at `0x180015917`
- `ntdll!RtlAcquireResourceShared` at `0x180015917`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180015950`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180015950`

## string_xrefs

- `0x180015979`: `CListenerEx::GetSecurityDescriptor`
- `0x180015983`: `Failed to allocate memory for *pSecurityDescriptor failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CListenerEx::GetSecurityDescriptor(CListenerEx *this, unsigned __int8 **a2, unsigned int *a3)
{
  struct _RTL_RESOURCE *v6; // rdi
  void *v7; // rbp
  unsigned int v8; // ebx
  DWORD SecurityDescriptorLength; // eax
  size_t v10; // r15
  unsigned __int8 *v11; // rax

  v6 = (struct _RTL_RESOURCE *)((char *)this + 1592);
  if ( *((_DWORD *)this + 422) )
    RtlAcquireResourceShared((PRTL_RESOURCE)((char *)this + 1592), 1u);
  if ( a2 && a3 )
  {
    *a2 = 0;
    *a3 = 0;
    v7 = (void *)*((_QWORD *)this + 393);
    if ( v7 && (SecurityDescriptorLength = GetSecurityDescriptorLength(v7), (v10 = SecurityDescriptorLength) != 0) )
    {
      v11 = (unsigned __int8 *)operator new[](SecurityDescriptorLength, (const struct std::nothrow_t *)std::nothrow);
      *a2 = v11;
      if ( v11 )
      {
        v8 = 0;
        *a3 = v10;
        memcpy_0(*a2, v7, v10);
      }
      else
      {
        v8 = -2147024882;
        _DbgPrintMessage(
          8,
          "Failed to allocate memory for *pSecurityDescriptor failed: 0x%x in %s",
          -2147024882,
          "CListenerEx::GetSecurityDescriptor");
      }
    }
    else
    {
      v8 = -2147023558;
    }
  }
  else
  {
    v8 = -2147024809;
  }
  if ( LODWORD(v6[1].Lock.DebugInfo) )
    RtlReleaseResource(v6);
  return v8;
}

```

## disassembly

```asm
0x1800158e0  push    rbx
0x1800158e2  push    rbp
0x1800158e3  push    rsi
0x1800158e4  push    rdi
0x1800158e5  push    r12
0x1800158e7  push    r14
0x1800158e9  push    r15
0x1800158eb  sub     rsp, 30h
0x1800158ef  mov     r14, r8
0x1800158f2  mov     rsi, rdx
0x1800158f5  mov     rbp, rcx
0x1800158f8  lea     rdi, [rcx+638h]
0x1800158ff  mov     [rsp+68h+var_48], rdi
0x180015904  mov     [rsp+68h+var_40], 1
0x18001590c  cmp     dword ptr [rdi+60h], 0
0x180015910  jz      short loc_18001591E
0x180015912  mov     dl, 1; Wait
0x180015914  mov     rcx, rdi; Resource
0x180015917  call    cs:__imp_RtlAcquireResourceShared
0x18001591d  nop
0x18001591e  test    rsi, rsi
0x180015921  jz      loc_1800159A9
0x180015927  test    r14, r14
0x18001592a  jz      short loc_1800159A9
0x18001592c  mov     qword ptr [rsi], 0
0x180015933  mov     dword ptr [r14], 0
0x18001593a  mov     rbp, [rbp+0C48h]
0x180015941  test    rbp, rbp
0x180015944  jnz     short loc_18001594D
0x180015946  mov     ebx, 8007053Ah
0x18001594b  jmp     short loc_1800159AE
0x18001594d  mov     rcx, rbp; pSecurityDescriptor
0x180015950  call    cs:__imp_GetSecurityDescriptorLength
0x180015956  mov     r15d, eax
0x180015959  test    eax, eax
0x18001595b  jz      short loc_180015946
0x18001595d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180015964  mov     ecx, r15d; unsigned __int64
0x180015967  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001596c  mov     [rsi], rax
0x18001596f  test    rax, rax
0x180015972  jnz     short loc_180015994
0x180015974  mov     ebx, 8007000Eh
0x180015979  lea     r9, aClistenerexGet_0; "CListenerEx::GetSecurityDescriptor"
0x180015980  mov     r8d, ebx
0x180015983  lea     rdx, aFailedToAlloca; "Failed to allocate memory for *pSecurit"...
0x18001598a  lea     ecx, [rax+8]; int
0x18001598d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180015992  jmp     short loc_1800159AE
0x180015994  xor     ebx, ebx
0x180015996  mov     [r14], r15d
0x180015999  mov     r8, r15; Size
0x18001599c  mov     rdx, rbp; Src
0x18001599f  mov     rcx, [rsi]; void *
0x1800159a2  call    memcpy_0
0x1800159a7  jmp     short loc_1800159AE
0x1800159a9  mov     ebx, 80070057h
0x1800159ae  cmp     dword ptr [rdi+60h], 0
0x1800159b2  jz      short loc_1800159BE
0x1800159b4  mov     rcx, rdi; Resource
0x1800159b7  call    cs:__imp_RtlReleaseResource
0x1800159bd  nop
0x1800159be  mov     eax, ebx
0x1800159c0  add     rsp, 30h
0x1800159c4  pop     r15
0x1800159c6  pop     r14
0x1800159c8  pop     r12
0x1800159ca  pop     rdi
0x1800159cb  pop     rsi
0x1800159cc  pop     rbp
0x1800159cd  pop     rbx
0x1800159ce  retn
```
