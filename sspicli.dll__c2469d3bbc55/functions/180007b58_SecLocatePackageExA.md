# SecLocatePackageExA

- ea: `0x180007b58`
- end: `0x180007c82`
- name: `SecLocatePackageExA`
- size: `298`
- prototype: `__int64 __fastcall(int)`
- caller_count: `7`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000996c`
- `0x180010f00`
- `0x18001a33c`
- `0x18001a510`
- `0x18001aa60`
- `0x18001adc0`
- `0x18001c1f0`

## callees

- `0x180007200`
- `0x180007b58`
- `0x180008fc4`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180007c4b`
- `ntdll!RtlAcquireResourceExclusive` at `0x180007c4b`
- `ntdll!RtlReleaseResource` at `0x180007c04`
- `ntdll!RtlReleaseResource` at `0x180007c70`
- `ntdll!RtlReleaseResource` at `0x180007c04`
- `ntdll!RtlReleaseResource` at `0x180007c70`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x180007b83`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x180007b83`
- `ntdll!RtlFreeUnicodeString` at `0x180007bb9`
- `ntdll!RtlFreeUnicodeString` at `0x180007bb9`

## pseudocode

```c
__int64 __fastcall SecLocatePackageExA(int a1, const char *a2, struct _DLL_SECURITY_PACKAGE **a3)
{
  __int64 v5; // rbx
  __int64 v6; // rdx
  int v7; // r8d
  struct _DLL_SECURITY_PACKAGE *v8; // rdi
  int v9; // eax
  __int64 v10; // rsi
  __int64 v12; // rbx
  struct _UNICODE_STRING UnicodeString; // [rsp+30h] [rbp-28h] BYREF
  struct _DLL_SECURITY_PACKAGE *v14; // [rsp+78h] [rbp+20h] BYREF

  v14 = 0;
  UnicodeString = 0;
  if ( !RtlCreateUnicodeStringFromAsciiz(&UnicodeString, a2) )
  {
    LODWORD(v5) = -2146893056;
    return (unsigned int)v5;
  }
  v5 = (unsigned int)SecpLocatePackageEx(a1, 0x10u, &UnicodeString, 0xFFFFFFFF, &v14);
  RtlFreeUnicodeString(&UnicodeString);
  if ( (_DWORD)v5 )
    return (unsigned int)v5;
  v8 = v14;
  if ( (*((_BYTE *)v14 + 36) & 4) != 0 )
  {
    v9 = SecPackageListLockCount;
    if ( SecPackageListLockCount )
    {
      do
      {
        RtlAcquireResourceExclusive((PRTL_RESOURCE)&SecPackageListLock[12 * v5], 1u);
        v9 = SecPackageListLockCount;
        v5 = (unsigned int)(v5 + 1);
      }
      while ( (unsigned int)v5 < SecPackageListLockCount );
    }
    if ( (*((_BYTE *)v8 + 36) & 4) != 0 )
    {
      v10 = 0;
      for ( LODWORD(v5) = SecpSnapPackage(v8, v6, v7);
            (unsigned int)v10 < SecPackageListLockCount;
            v10 = (unsigned int)(v10 + 1) )
      {
        RtlReleaseResource((PRTL_RESOURCE)&SecPackageListLock[12 * v10]);
      }
      if ( !(_DWORD)v5 )
        *a3 = v8;
      return (unsigned int)v5;
    }
    v12 = 0;
    if ( v9 )
    {
      do
      {
        RtlReleaseResource((PRTL_RESOURCE)&SecPackageListLock[12 * v12]);
        v12 = (unsigned int)(v12 + 1);
      }
      while ( (unsigned int)v12 < SecPackageListLockCount );
    }
  }
  *a3 = v8;
  return 0;
}

```

## disassembly

```asm
0x180007b58  mov     rax, rsp
0x180007b5b  mov     [rax+8], rbx
0x180007b5f  mov     [rax+10h], rbp
0x180007b63  push    rsi
0x180007b64  push    rdi
0x180007b65  push    r14
0x180007b67  sub     rsp, 40h
0x180007b6b  mov     ebx, ecx
0x180007b6d  mov     qword ptr [rax+20h], 0
0x180007b75  xorps   xmm0, xmm0
0x180007b78  lea     rcx, [rax-28h]; Destination
0x180007b7c  movups  xmmword ptr [rax-28h], xmm0
0x180007b80  mov     r14, r8
0x180007b83  call    cs:__imp_RtlCreateUnicodeStringFromAsciiz
0x180007b89  test    al, al
0x180007b8b  jz      loc_180007C1D
0x180007b91  lea     rax, [rsp+58h+arg_18]
0x180007b96  mov     r9d, 0FFFFFFFFh; unsigned __int64
0x180007b9c  lea     r8, [rsp+58h+UnicodeString]; struct _UNICODE_STRING *
0x180007ba1  mov     [rsp+58h+var_38], rax; struct _DLL_SECURITY_PACKAGE **
0x180007ba6  mov     edx, 10h; unsigned int
0x180007bab  mov     ecx, ebx; int
0x180007bad  call    ?SecpLocatePackageEx@@YAJHKPEAU_UNICODE_STRING@@_KPEAPEAU_DLL_SECURITY_PACKAGE@@@Z; SecpLocatePackageEx(int,ulong,_UNICODE_STRING *,unsigned __int64,_DLL_SECURITY_PACKAGE * *)
0x180007bb2  lea     rcx, [rsp+58h+UnicodeString]; UnicodeString
0x180007bb7  mov     ebx, eax
0x180007bb9  call    cs:__imp_RtlFreeUnicodeString
0x180007bbf  test    ebx, ebx
0x180007bc1  jnz     short loc_180007C22
0x180007bc3  mov     rdi, [rsp+58h+arg_18]
0x180007bc8  test    byte ptr [rdi+24h], 4
0x180007bcc  jz      short loc_180007C37
0x180007bce  mov     eax, cs:SecPackageListLockCount
0x180007bd4  lea     rbp, SecPackageListLock
0x180007bdb  test    eax, eax
0x180007bdd  jnz     short loc_180007C3E
0x180007bdf  test    byte ptr [rdi+24h], 4
0x180007be3  jz      short loc_180007C5F
0x180007be5  mov     rcx, rdi; struct _DLL_SECURITY_PACKAGE *
0x180007be8  call    ?SecpSnapPackage@@YAJPEAU_DLL_SECURITY_PACKAGE@@@Z; SecpSnapPackage(_DLL_SECURITY_PACKAGE *)
0x180007bed  xor     esi, esi
0x180007bef  mov     ebx, eax
0x180007bf1  cmp     cs:SecPackageListLockCount, esi
0x180007bf7  jbe     short loc_180007C14
0x180007bf9  lea     rcx, [rsi+rsi*2]
0x180007bfd  shl     rcx, 5
0x180007c01  add     rcx, rbp; Resource
0x180007c04  call    cs:__imp_RtlReleaseResource
0x180007c0a  inc     esi
0x180007c0c  cmp     esi, cs:SecPackageListLockCount
0x180007c12  jb      short loc_180007BF9
0x180007c14  test    ebx, ebx
0x180007c16  jnz     short loc_180007C22
0x180007c18  mov     [r14], rdi
0x180007c1b  jmp     short loc_180007C22
0x180007c1d  mov     ebx, 80090300h
0x180007c22  mov     eax, ebx
0x180007c24  mov     rbx, [rsp+58h+arg_0]
0x180007c29  mov     rbp, [rsp+58h+arg_8]
0x180007c2e  add     rsp, 40h
0x180007c32  pop     r14
0x180007c34  pop     rdi
0x180007c35  pop     rsi
0x180007c36  retn
0x180007c37  mov     [r14], rdi
0x180007c3a  xor     eax, eax
0x180007c3c  jmp     short loc_180007C24
0x180007c3e  lea     rcx, [rbx+rbx*2]
0x180007c42  mov     dl, 1; Wait
0x180007c44  shl     rcx, 5
0x180007c48  add     rcx, rbp; Resource
0x180007c4b  call    cs:__imp_RtlAcquireResourceExclusive
0x180007c51  mov     eax, cs:SecPackageListLockCount
0x180007c57  inc     ebx
0x180007c59  cmp     ebx, eax
0x180007c5b  jb      short loc_180007C3E
0x180007c5d  jmp     short loc_180007BDF
0x180007c5f  xor     ebx, ebx
0x180007c61  test    eax, eax
0x180007c63  jz      short loc_180007C37
0x180007c65  lea     rcx, [rbx+rbx*2]
0x180007c69  shl     rcx, 5
0x180007c6d  add     rcx, rbp; Resource
0x180007c70  call    cs:__imp_RtlReleaseResource
0x180007c76  inc     ebx
0x180007c78  cmp     ebx, cs:SecPackageListLockCount
0x180007c7e  jb      short loc_180007C65
0x180007c80  jmp     short loc_180007C37
```
