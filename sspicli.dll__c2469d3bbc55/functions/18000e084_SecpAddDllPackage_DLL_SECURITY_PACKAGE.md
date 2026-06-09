# SecpAddDllPackage(_DLL_SECURITY_PACKAGE *)

- ea: `0x18000e084`
- end: `0x18000e13f`
- name: `?SecpAddDllPackage@@YAXPEAU_DLL_SECURITY_PACKAGE@@@Z`
- size: `187`
- prototype: `void __fastcall(struct _DLL_SECURITY_PACKAGE *)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800069d8`
- `0x18000d6ec`
- `0x18000d8ac`

## callees

- `0x18000e084`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18000e107`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000e107`
- `ntdll!RtlReleaseResource` at `0x18000e126`
- `ntdll!RtlReleaseResource` at `0x18000e126`

## pseudocode

```c
void __fastcall SecpAddDllPackage(struct _DLL_SECURITY_PACKAGE *a1)
{
  int v2; // ecx
  __int64 i; // rdi
  _QWORD *v4; // rax
  __int64 v5; // rbx

  v2 = SecPackageListLockCount;
  for ( i = 0; (unsigned int)i < SecPackageListLockCount; i = (unsigned int)(i + 1) )
  {
    RtlAcquireResourceExclusive((PRTL_RESOURCE)&SecPackageListLock[12 * i], 1u);
    v2 = SecPackageListLockCount;
  }
  v4 = (_QWORD *)qword_18003FED0;
  if ( *(HLOCAL **)qword_18003FED0 != &SecPackageControlList )
    __fastfail(3u);
  *(_QWORD *)a1 = &SecPackageControlList;
  *((_QWORD *)a1 + 1) = v4;
  *v4 = a1;
  qword_18003FED0 = (__int64)a1;
  ++*(_DWORD *)(*((_QWORD *)a1 + 7) + 32LL);
  if ( (*((_DWORD *)a1 + 20) & 0x100000) != 0 )
    SecGlobalExtenderPackage = a1;
  v5 = 0;
  if ( v2 )
  {
    do
    {
      RtlReleaseResource((PRTL_RESOURCE)&SecPackageListLock[12 * v5]);
      v5 = (unsigned int)(v5 + 1);
    }
    while ( (unsigned int)v5 < SecPackageListLockCount );
  }
}

```

## disassembly

```asm
0x18000e084  mov     [rsp+arg_0], rbx
0x18000e089  mov     [rsp+arg_8], rsi
0x18000e08e  push    rdi
0x18000e08f  sub     rsp, 20h
0x18000e093  mov     rbx, rcx
0x18000e096  lea     rsi, SecPackageListLock
0x18000e09d  mov     ecx, cs:SecPackageListLockCount
0x18000e0a3  xor     edi, edi
0x18000e0a5  test    ecx, ecx
0x18000e0a7  jnz     short loc_18000E0FA
0x18000e0a9  mov     rax, cs:qword_18003FED0
0x18000e0b0  lea     rdx, ?SecPackageControlList@@3U_LIST_ENTRY@@A; _LIST_ENTRY SecPackageControlList
0x18000e0b7  cmp     [rax], rdx
0x18000e0ba  jnz     short loc_18000E138
0x18000e0bc  mov     [rbx], rdx
0x18000e0bf  mov     [rbx+8], rax
0x18000e0c3  mov     [rax], rbx
0x18000e0c6  mov     cs:qword_18003FED0, rbx
0x18000e0cd  mov     rax, [rbx+38h]
0x18000e0d1  inc     dword ptr [rax+20h]
0x18000e0d4  test    dword ptr [rbx+50h], 100000h
0x18000e0db  jz      short loc_18000E0E4
0x18000e0dd  mov     cs:?SecGlobalExtenderPackage@@3PEAU_DLL_SECURITY_PACKAGE@@EA, rbx; _DLL_SECURITY_PACKAGE * SecGlobalExtenderPackage
0x18000e0e4  xor     ebx, ebx
0x18000e0e6  test    ecx, ecx
0x18000e0e8  jnz     short loc_18000E11B
0x18000e0ea  mov     rbx, [rsp+28h+arg_0]
0x18000e0ef  mov     rsi, [rsp+28h+arg_8]
0x18000e0f4  add     rsp, 20h
0x18000e0f8  pop     rdi
0x18000e0f9  retn
0x18000e0fa  lea     rcx, [rdi+rdi*2]
0x18000e0fe  mov     dl, 1; Wait
0x18000e100  shl     rcx, 5
0x18000e104  add     rcx, rsi; Resource
0x18000e107  call    cs:__imp_RtlAcquireResourceExclusive
0x18000e10d  mov     ecx, cs:SecPackageListLockCount
0x18000e113  inc     edi
0x18000e115  cmp     edi, ecx
0x18000e117  jnb     short loc_18000E0A9
0x18000e119  jmp     short loc_18000E0FA
0x18000e11b  lea     rcx, [rbx+rbx*2]
0x18000e11f  shl     rcx, 5
0x18000e123  add     rcx, rsi; Resource
0x18000e126  call    cs:__imp_RtlReleaseResource
0x18000e12c  inc     ebx
0x18000e12e  cmp     ebx, cs:SecPackageListLockCount
0x18000e134  jnb     short loc_18000E0EA
0x18000e136  jmp     short loc_18000E11B
0x18000e138  mov     ecx, 3
0x18000e13d  int     29h; Win8: RtlFailFast(ecx)
```
