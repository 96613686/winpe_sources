# SpDeleteUserModeContext(unsigned __int64)

- ea: `0x180003d30`
- end: `0x180003def`
- name: `?SpDeleteUserModeContext@@YAJ_K@Z`
- size: `191`
- prototype: `__int64 __fastcall(unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180003d30`
- `0x180003e00`
- `0x18000b550`
- `0x18000c1a4`
- `0x1800177b0`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180003d9c`
- `ntdll!RtlReleaseResource` at `0x180003dd5`
- `ntdll!RtlReleaseResource` at `0x180003d9c`
- `ntdll!RtlReleaseResource` at `0x180003dd5`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180003d8a`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180003d8a`
- `ntdll!RtlAcquireResourceShared` at `0x180003d78`
- `ntdll!RtlAcquireResourceShared` at `0x180003d78`

## pseudocode

```c
__int64 __fastcall SpDeleteUserModeContext(__int64 a1)
{
  volatile signed __int32 **v2; // rax
  volatile signed __int32 *v4; // rbx
  _BYTE *Buffer; // [rsp+20h] [rbp-148h] BYREF
  _BYTE v6[8]; // [rsp+30h] [rbp-138h] BYREF
  __int64 v7; // [rsp+38h] [rbp-130h]

  memset_0(v6, 0, 0x118u);
  v7 = a1;
  Buffer = v6;
  RtlAcquireResourceShared(&Resource, 1u);
  v2 = (volatile signed __int32 **)RtlLookupElementGenericTableAvl(&Table, &Buffer);
  if ( v2 )
  {
    if ( *v2 )
      _InterlockedIncrement(*v2);
    v4 = *v2;
    RtlReleaseResource(&Resource);
    TSContextTableDelete((struct _TS_CONTEXT *)v4);
    TSDereferenceContext((struct _TS_CONTEXT *)v4);
    return 0;
  }
  else
  {
    RtlReleaseResource(&Resource);
    return 2148074241LL;
  }
}

```

## disassembly

```asm
0x180003d30  push    rbx
0x180003d32  sub     rsp, 160h
0x180003d39  mov     rax, cs:__security_cookie
0x180003d40  xor     rax, rsp
0x180003d43  mov     [rsp+168h+var_18], rax
0x180003d4b  mov     rbx, rcx
0x180003d4e  xor     edx, edx; Val
0x180003d50  lea     rcx, [rsp+168h+var_138]; void *
0x180003d55  mov     r8d, 118h; Size
0x180003d5b  call    memset_0
0x180003d60  lea     rax, [rsp+168h+var_138]
0x180003d65  mov     [rsp+168h+var_130], rbx
0x180003d6a  mov     dl, 1; Wait
0x180003d6c  mov     [rsp+168h+Buffer], rax
0x180003d71  lea     rcx, Resource; Resource
0x180003d78  call    cs:__imp_RtlAcquireResourceShared
0x180003d7e  lea     rdx, [rsp+168h+Buffer]; Buffer
0x180003d83  lea     rcx, Table; Table
0x180003d8a  call    cs:__imp_RtlLookupElementGenericTableAvl
0x180003d90  test    rax, rax
0x180003d93  jnz     short loc_180003DC0
0x180003d95  lea     rcx, Resource; Resource
0x180003d9c  call    cs:__imp_RtlReleaseResource
0x180003da2  mov     eax, 80090301h
0x180003da7  mov     rcx, [rsp+168h+var_18]
0x180003daf  xor     rcx, rsp; StackCookie
0x180003db2  call    __security_check_cookie
0x180003db7  add     rsp, 160h
0x180003dbe  pop     rbx
0x180003dbf  retn
0x180003dc0  mov     rdx, [rax]
0x180003dc3  test    rdx, rdx
0x180003dc6  jz      short loc_180003DCB
0x180003dc8  lock inc dword ptr [rdx]
0x180003dcb  mov     rbx, [rax]
0x180003dce  lea     rcx, Resource; Resource
0x180003dd5  call    cs:__imp_RtlReleaseResource
0x180003ddb  mov     rcx, rbx; struct _TS_CONTEXT *
0x180003dde  call    ?TSContextTableDelete@@YAXPEAU_TS_CONTEXT@@@Z; TSContextTableDelete(_TS_CONTEXT *)
0x180003de3  mov     rcx, rbx; struct _TS_CONTEXT *
0x180003de6  call    ?TSDereferenceContext@@YAXPEAU_TS_CONTEXT@@@Z; TSDereferenceContext(_TS_CONTEXT *)
0x180003deb  xor     eax, eax
0x180003ded  jmp     short loc_180003DA7
```
