# TSUpdateCredentialsPassword(_SECPKG_PRIMARY_CRED *,_TS_CREDENTIAL *)

- ea: `0x1800161a0`
- end: `0x180016275`
- name: `?TSUpdateCredentialsPassword@@YAJPEAU_SECPKG_PRIMARY_CRED@@PEAU_TS_CREDENTIAL@@@Z`
- size: `213`
- prototype: `__int64 __fastcall(struct _SECPKG_PRIMARY_CRED *, struct _TS_CREDENTIAL *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x180002570`

## callees

- `0x180006530`
- `0x180008810`
- `0x1800090a0`
- `0x1800161a0`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x1800161f4`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800161f4`
- `ntdll!RtlReleaseResource` at `0x18001624c`
- `ntdll!RtlReleaseResource` at `0x18001624c`

## pseudocode

```c
__int64 __fastcall TSUpdateCredentialsPassword(struct _SECPKG_PRIMARY_CRED *a1, struct _TS_CREDENTIAL *a2)
{
  int v3; // edi
  __int64 v4; // rax
  _BYTE *v5; // rdx
  __int64 i; // rax
  struct _UNICODE_STRING v7; // xmm0
  __int64 v8; // rax
  struct _UNICODE_STRING v10; // [rsp+20h] [rbp-18h] BYREF

  v10 = 0;
  if ( !a2 || !*((_QWORD *)a2 + 17) )
    return 3221225485LL;
  v3 = TSDuplicatePassword(&v10, &a1->Password);
  if ( v3 >= 0 )
  {
    TSHidePassword(&v10);
    RtlAcquireResourceExclusive((PRTL_RESOURCE)((char *)a2 + 8), 1u);
    v4 = *((_QWORD *)a2 + 17);
    v5 = *(_BYTE **)(v4 + 48);
    if ( v5 )
    {
      for ( i = *(unsigned __int16 *)(v4 + 42); i; --i )
        *v5++ = 0;
    }
    TSFreeString((struct _UNICODE_STRING *)(*((_QWORD *)a2 + 17) + 40LL));
    v7 = v10;
    v8 = *((_QWORD *)a2 + 17);
    v10 = 0;
    *(struct _UNICODE_STRING *)(v8 + 40) = v7;
    RtlReleaseResource((PRTL_RESOURCE)((char *)a2 + 8));
  }
  TSFreeString(&v10);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800161a0  mov     rax, rsp
0x1800161a3  mov     [rax+8], rbx
0x1800161a7  mov     [rax+10h], rsi
0x1800161ab  push    rdi
0x1800161ac  sub     rsp, 30h
0x1800161b0  xorps   xmm0, xmm0
0x1800161b3  mov     rbx, rdx
0x1800161b6  movups  xmmword ptr [rax-18h], xmm0
0x1800161ba  test    rdx, rdx
0x1800161bd  jz      loc_180016260
0x1800161c3  cmp     qword ptr [rdx+88h], 0
0x1800161cb  jz      loc_180016260
0x1800161d1  lea     rdx, [rcx+28h]; struct _UNICODE_STRING *
0x1800161d5  lea     rcx, [rax-18h]; struct _UNICODE_STRING *
0x1800161d9  call    ?TSDuplicatePassword@@YAJPEAU_UNICODE_STRING@@0@Z; TSDuplicatePassword(_UNICODE_STRING *,_UNICODE_STRING *)
0x1800161de  mov     edi, eax
0x1800161e0  test    eax, eax
0x1800161e2  js      short loc_180016252
0x1800161e4  lea     rcx, [rsp+38h+var_18]; struct _UNICODE_STRING *
0x1800161e9  call    ?TSHidePassword@@YAXPEAU_UNICODE_STRING@@@Z; TSHidePassword(_UNICODE_STRING *)
0x1800161ee  mov     dl, 1; Wait
0x1800161f0  lea     rcx, [rbx+8]; Resource
0x1800161f4  call    cs:__imp_RtlAcquireResourceExclusive
0x1800161fa  mov     rax, [rbx+88h]
0x180016201  mov     rdx, [rax+30h]
0x180016205  test    rdx, rdx
0x180016208  jz      short loc_18001621F
0x18001620a  movzx   eax, word ptr [rax+2Ah]
0x18001620e  test    rax, rax
0x180016211  jz      short loc_18001621F
0x180016213  mov     byte ptr [rdx], 0
0x180016216  inc     rdx
0x180016219  sub     rax, 1
0x18001621d  jnz     short loc_180016213
0x18001621f  mov     rcx, [rbx+88h]
0x180016226  add     rcx, 28h ; '('; struct _UNICODE_STRING *
0x18001622a  call    ?TSFreeString@@YAXPEAU_UNICODE_STRING@@@Z; TSFreeString(_UNICODE_STRING *)
0x18001622f  movups  xmm0, xmmword ptr [rsp+38h+var_18.Length]
0x180016234  mov     rax, [rbx+88h]
0x18001623b  lea     rcx, [rbx+8]; Resource
0x18001623f  xorps   xmm1, xmm1
0x180016242  movups  xmmword ptr [rsp+38h+var_18.Length], xmm1
0x180016247  movdqu  xmmword ptr [rax+28h], xmm0
0x18001624c  call    cs:__imp_RtlReleaseResource
0x180016252  lea     rcx, [rsp+38h+var_18]; struct _UNICODE_STRING *
0x180016257  call    ?TSFreeString@@YAXPEAU_UNICODE_STRING@@@Z; TSFreeString(_UNICODE_STRING *)
0x18001625c  mov     eax, edi
0x18001625e  jmp     short loc_180016265
0x180016260  mov     eax, 0C000000Dh
0x180016265  mov     rbx, [rsp+38h+arg_0]
0x18001626a  mov     rsi, [rsp+38h+arg_8]
0x18001626f  add     rsp, 30h
0x180016273  pop     rdi
0x180016274  retn
```
