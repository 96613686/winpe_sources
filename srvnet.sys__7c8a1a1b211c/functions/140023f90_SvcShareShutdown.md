# SvcShareShutdown

- ea: `0x140023f90`
- end: `0x1400240f8`
- name: `SvcShareShutdown`
- size: `360`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x140011cb8`
- `0x140025760`

## callees

- `0x140007160`
- `0x14000ef40`
- `0x1400227cc`
- `0x140023f90`
- `0x140029b7c`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x1400240c2`
- `ntoskrnl!KeBugCheckEx` at `0x1400240c2`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140023ff8`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140023ff8`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140023fc8`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140024041`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140023fc8`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140024041`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140024063`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140024063`
- `ntoskrnl!ExReleaseResourceLite` at `0x140024087`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400240d2`
- `ntoskrnl!ExReleaseResourceLite` at `0x140024087`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400240d2`

## pseudocode

```c
__int64 __fastcall SvcShareShutdown(__int64 a1, __int64 a2)
{
  int v2; // r15d
  struct _ERESOURCE *v3; // rsi
  int v4; // r12d
  __int64 v7; // rax
  _DWORD *v8; // rbx

  v2 = *(_DWORD *)(a2 + 80);
  v3 = (struct _ERESOURCE *)(a1 + 200);
  v4 = *(_DWORD *)(a2 + 84);
  ExAcquireResourceExclusiveLite((PERESOURCE)(a1 + 200), 1u);
  while ( 1 )
  {
    v7 = RfsTableEnumerate(*(PEX_SPIN_LOCK *)(a1 + 72));
    v8 = (_DWORD *)v7;
    if ( !v7 )
      break;
    if ( RtlEqualUnicodeString((PCUNICODE_STRING)(v7 + 24), (PCUNICODE_STRING)a2, 1u)
      && (v2 & v8[31]) == v2
      && (v8[31] & v4) == 0 )
    {
      v8[34] = 1;
      SrvAdminUpdateProvidersOfShare(v8, 2261015);
      ExAcquireResourceExclusiveLite((PERESOURCE)(a1 + 96), 1u);
      RfsTableRemove(*(PEX_SPIN_LOCK *)(a1 + 72));
      if ( !RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(a1 + 408), v8 + 2) )
        KeBugCheckEx(0x54u, (ULONG_PTR)"onecore\\base\\fs\\remotefs\\smb\\srv\\srvadmin\\svcshare.c", 0x777u, 0, 0);
      SrvAdminDereferenceShare(v8);
      SrvAdminDereferenceShare(v8);
      ExReleaseResourceLite((PERESOURCE)(a1 + 96));
    }
    else
    {
      SrvAdminDereferenceShare(v8);
    }
  }
  ExReleaseResourceLite(v3);
  return 0;
}

```

## disassembly

```asm
0x140023f90  mov     [rsp+arg_8], rbx
0x140023f95  mov     [rsp+arg_10], rbp
0x140023f9a  push    rsi
0x140023f9b  push    rdi
0x140023f9c  push    r12
0x140023f9e  push    r14
0x140023fa0  push    r15
0x140023fa2  sub     rsp, 30h
0x140023fa6  mov     r15d, [rdx+50h]
0x140023faa  lea     rsi, [rcx+0C8h]
0x140023fb1  mov     r12d, [rdx+54h]
0x140023fb5  mov     r14, rdx
0x140023fb8  mov     rdi, rcx
0x140023fbb  mov     [rsp+58h+arg_0], 0
0x140023fc3  mov     rcx, rsi; Resource
0x140023fc6  mov     dl, 1; Wait
0x140023fc8  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140023fcf  nop     dword ptr [rax+rax+00h]
0x140023fd4  mov     rcx, [rdi+48h]; SpinLock
0x140023fd8  lea     rdx, [rsp+58h+arg_0]
0x140023fdd  call    RfsTableEnumerate
0x140023fe2  mov     rbx, rax
0x140023fe5  test    rax, rax
0x140023fe8  jz      loc_1400240CF
0x140023fee  lea     rcx, [rax+18h]; String1
0x140023ff2  mov     r8b, 1; CaseInSensitive
0x140023ff5  mov     rdx, r14; String2
0x140023ff8  call    cs:__imp_RtlEqualUnicodeString
0x140023fff  nop     dword ptr [rax+rax+00h]
0x140024004  test    al, al
0x140024006  jz      loc_140024098
0x14002400c  mov     edx, [rbx+7Ch]
0x14002400f  mov     eax, edx
0x140024011  and     eax, r15d
0x140024014  cmp     eax, r15d
0x140024017  setz    cl
0x14002401a  test    r12d, edx
0x14002401d  setz    al
0x140024020  test    al, cl
0x140024022  jz      short loc_140024098
0x140024024  mov     edx, 228017h
0x140024029  mov     dword ptr [rbx+88h], 1
0x140024033  mov     rcx, rbx
0x140024036  call    SrvAdminUpdateProvidersOfShare
0x14002403b  mov     dl, 1; Wait
0x14002403d  lea     rcx, [rdi+60h]; Resource
0x140024041  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140024048  nop     dword ptr [rax+rax+00h]
0x14002404d  mov     edx, [rbx]
0x14002404f  mov     rcx, [rdi+48h]; SpinLock
0x140024053  call    RfsTableRemove
0x140024058  lea     rdx, [rbx+8]; Buffer
0x14002405c  lea     rcx, [rdi+198h]; Table
0x140024063  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x14002406a  nop     dword ptr [rax+rax+00h]
0x14002406f  test    al, al
0x140024071  jz      short loc_1400240A5
0x140024073  mov     rcx, rbx
0x140024076  call    SrvAdminDereferenceShare
0x14002407b  mov     rcx, rbx
0x14002407e  call    SrvAdminDereferenceShare
0x140024083  lea     rcx, [rdi+60h]; Resource
0x140024087  call    cs:__imp_ExReleaseResourceLite
0x14002408e  nop     dword ptr [rax+rax+00h]
0x140024093  jmp     loc_140023FD4
0x140024098  mov     rcx, rbx
0x14002409b  call    SrvAdminDereferenceShare
0x1400240a0  jmp     loc_140023FD4
0x1400240a5  xor     r9d, r9d; BugCheckParameter3
0x1400240a8  mov     [rsp+58h+BugCheckParameter4], 0; BugCheckParameter4
0x1400240b1  mov     r8d, 777h; BugCheckParameter2
0x1400240b7  lea     rdx, aOnecoreBaseFsR; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x1400240be  lea     ecx, [r9+54h]; BugCheckCode
0x1400240c2  call    cs:__imp_KeBugCheckEx
0x1400240cf  mov     rcx, rsi; Resource
0x1400240d2  call    cs:__imp_ExReleaseResourceLite
0x1400240d9  nop     dword ptr [rax+rax+00h]
0x1400240de  mov     rbx, [rsp+58h+arg_8]
0x1400240e3  xor     eax, eax
0x1400240e5  mov     rbp, [rsp+58h+arg_10]
0x1400240ea  add     rsp, 30h
0x1400240ee  pop     r15
0x1400240f0  pop     r14
0x1400240f2  pop     r12
0x1400240f4  pop     rdi
0x1400240f5  pop     rsi
0x1400240f6  retn
```
