# CListenerEx::GetSecurityDescriptor(uchar * *,ulong *)

- ea: `0x1800163a0`
- end: `0x1800164a6`
- name: `?GetSecurityDescriptor@CListenerEx@@UEAAJPEAPEAEPEAK@Z`
- size: `262`
- prototype: `__int64 __fastcall(CListenerEx *__hidden this, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180009940`
- `0x1800163a0`
- `0x180034470`
- `0x1800caedc`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180016487`
- `ntdll!RtlReleaseResource` at `0x180016487`
- `ntdll!RtlAcquireResourceShared` at `0x1800163d7`
- `ntdll!RtlAcquireResourceShared` at `0x1800163d7`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18001641a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18001641a`

## string_xrefs

- `0x180016449`: `CListenerEx::GetSecurityDescriptor`
- `0x180016453`: `Failed to allocate memory for *pSecurityDescriptor failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x1800163a0  push    rbx
0x1800163a2  push    rbp
0x1800163a3  push    rsi
0x1800163a4  push    rdi
0x1800163a5  push    r12
0x1800163a7  push    r14
0x1800163a9  push    r15
0x1800163ab  sub     rsp, 30h
0x1800163af  mov     r14, r8
0x1800163b2  mov     rsi, rdx
0x1800163b5  mov     rbp, rcx
0x1800163b8  lea     rdi, [rcx+638h]
0x1800163bf  mov     [rsp+68h+var_48], rdi
0x1800163c4  mov     [rsp+68h+var_40], 1
0x1800163cc  cmp     dword ptr [rdi+60h], 0
0x1800163d0  jz      short loc_1800163E4
0x1800163d2  mov     dl, 1; Wait
0x1800163d4  mov     rcx, rdi; Resource
0x1800163d7  call    cs:__imp_RtlAcquireResourceShared
0x1800163de  nop     dword ptr [rax+rax+00h]
0x1800163e3  nop
0x1800163e4  test    rsi, rsi
0x1800163e7  jz      loc_180016479
0x1800163ed  test    r14, r14
0x1800163f0  jz      loc_180016479
0x1800163f6  mov     qword ptr [rsi], 0
0x1800163fd  mov     dword ptr [r14], 0
0x180016404  mov     rbp, [rbp+0C48h]
0x18001640b  test    rbp, rbp
0x18001640e  jnz     short loc_180016417
0x180016410  mov     ebx, 8007053Ah
0x180016415  jmp     short loc_18001647E
0x180016417  mov     rcx, rbp; pSecurityDescriptor
0x18001641a  call    cs:__imp_GetSecurityDescriptorLength
0x180016421  nop     dword ptr [rax+rax+00h]
0x180016426  mov     r15d, eax
0x180016429  test    eax, eax
0x18001642b  jz      short loc_180016410
0x18001642d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180016434  mov     ecx, r15d; unsigned __int64
0x180016437  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001643c  mov     [rsi], rax
0x18001643f  test    rax, rax
0x180016442  jnz     short loc_180016464
0x180016444  mov     ebx, 8007000Eh
0x180016449  lea     r9, aClistenerexGet_0; "CListenerEx::GetSecurityDescriptor"
0x180016450  mov     r8d, ebx
0x180016453  lea     rdx, aFailedToAlloca; "Failed to allocate memory for *pSecurit"...
0x18001645a  lea     ecx, [rax+8]; int
0x18001645d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180016462  jmp     short loc_18001647E
0x180016464  xor     ebx, ebx
0x180016466  mov     [r14], r15d
0x180016469  mov     r8, r15; Size
0x18001646c  mov     rdx, rbp; Src
0x18001646f  mov     rcx, [rsi]; void *
0x180016472  call    memcpy_0
0x180016477  jmp     short loc_18001647E
0x180016479  mov     ebx, 80070057h
0x18001647e  cmp     dword ptr [rdi+60h], 0
0x180016482  jz      short loc_180016494
0x180016484  mov     rcx, rdi; Resource
0x180016487  call    cs:__imp_RtlReleaseResource
0x18001648e  nop     dword ptr [rax+rax+00h]
0x180016493  nop
0x180016494  mov     eax, ebx
0x180016496  add     rsp, 30h
0x18001649a  pop     r15
0x18001649c  pop     r14
0x18001649e  pop     r12
0x1800164a0  pop     rdi
0x1800164a1  pop     rsi
0x1800164a2  pop     rbp
0x1800164a3  pop     rbx
0x1800164a4  retn
```
