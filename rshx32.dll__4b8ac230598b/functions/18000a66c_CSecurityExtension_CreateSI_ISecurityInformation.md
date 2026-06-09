# CSecurityExtension::_CreateSI(ISecurityInformation * *)

- ea: `0x18000a66c`
- end: `0x18000a79a`
- name: `?_CreateSI@CSecurityExtension@@AEAAJPEAPEAUISecurityInformation@@@Z`
- size: `302`
- prototype: `__int64 __fastcall(CSecurityExtension *__hidden this, struct ISecurityInformation **)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009c90`
- `0x18000a39c`

## callees

- `0x1800061b0`
- `0x18000a66c`
- `0x18000be34`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a698`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a6c9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a698`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a6c9`

## pseudocode

```c
__int64 __fastcall CSecurityExtension::_CreateSI(CSecurityExtension *this, struct ISecurityInformation **a2)
{
  bool v2; // zf
  int v5; // esi
  CNTFSSecurity *v6; // rax
  struct ISecurityInformation *v7; // rbx
  CSecurityInformation *v8; // rax

  v2 = *((_DWORD *)this + 7) == 1;
  *a2 = 0;
  v5 = -2147024882;
  if ( !v2 )
  {
    v8 = (CSecurityInformation *)LocalAlloc(0x40u, 0x140u);
    v7 = (struct ISecurityInformation *)v8;
    if ( !v8 )
      return (unsigned int)v5;
    CSecurityInformation::CSecurityInformation(v8, *((enum _SE_OBJECT_TYPE *)this + 7));
    v7->lpVtbl = (struct ISecurityInformationVtbl *)&CPrintSecurity::`vftable'{for `ISecurityInformation'};
    v7[1].lpVtbl = (struct ISecurityInformationVtbl *)&CSecurityInformation::`vftable'{for `IEffectivePermission'};
    v7[2].lpVtbl = (struct ISecurityInformationVtbl *)&CPrintSecurity::`vftable'{for `IEffectivePermission2'};
    v7[3].lpVtbl = (struct ISecurityInformationVtbl *)&CPrintSecurity::`vftable'{for `ISecurityObjectTypeInfo'};
    v7[4].lpVtbl = (struct ISecurityInformationVtbl *)&CPrintSecurity::`vftable'{for `ISecurityInformation3'};
    v7[5].lpVtbl = (struct ISecurityInformationVtbl *)&CPrintSecurity::`vftable'{for `ISecurityInformation4'};
    goto LABEL_9;
  }
  v6 = (CNTFSSecurity *)LocalAlloc(0x40u, 0x278u);
  if ( v6 )
    v7 = (struct ISecurityInformation *)CNTFSSecurity::CNTFSSecurity(
                                          v6,
                                          (enum _SE_OBJECT_TYPE)*((_DWORD *)this + 7),
                                          *((_DWORD *)this + 18));
  else
    v7 = 0;
  if ( v7 )
  {
LABEL_9:
    v5 = ((__int64 (__fastcall *)(struct ISecurityInformation *, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD))v7->lpVtbl[1].AddRef)(
           v7,
           *((_QWORD *)this + 8),
           *((unsigned int *)this + 11),
           *((_QWORD *)this + 6),
           *((_QWORD *)this + 7),
           *((_DWORD *)this + 19));
    if ( v5 < 0 )
    {
      ((void (__fastcall *)(struct ISecurityInformation *))v7->lpVtbl->Release)(v7);
    }
    else
    {
      *a2 = v7;
      *((_QWORD *)this + 8) = 0;
      *((_QWORD *)this + 6) = 0;
      *((_QWORD *)this + 7) = 0;
      *((_DWORD *)this + 10) = -1;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000a66c  push    rbx
0x18000a66e  push    rsi
0x18000a66f  push    rdi
0x18000a670  push    r14
0x18000a672  sub     rsp, 48h
0x18000a676  cmp     dword ptr [rcx+1Ch], 1
0x18000a67a  mov     rdi, rcx
0x18000a67d  mov     ecx, 40h ; '@'; uFlags
0x18000a682  mov     qword ptr [rdx], 0
0x18000a689  mov     r14, rdx
0x18000a68c  mov     esi, 8007000Eh
0x18000a691  jnz     short loc_18000A6C4
0x18000a693  mov     edx, 278h; uBytes
0x18000a698  call    cs:__imp_LocalAlloc
0x18000a69e  test    rax, rax
0x18000a6a1  jz      short loc_18000A6B7
0x18000a6a3  mov     r8d, [rdi+48h]; int
0x18000a6a7  mov     rcx, rax; this
0x18000a6aa  mov     edx, [rdi+1Ch]; enum _SE_OBJECT_TYPE
0x18000a6ad  call    ??0CNTFSSecurity@@QEAA@W4_SE_OBJECT_TYPE@@H@Z; CNTFSSecurity::CNTFSSecurity(_SE_OBJECT_TYPE,int)
0x18000a6b2  mov     rbx, rax
0x18000a6b5  jmp     short loc_18000A6B9
0x18000a6b7  xor     ebx, ebx
0x18000a6b9  test    rbx, rbx
0x18000a6bc  jz      loc_18000A78E
0x18000a6c2  jmp     short loc_18000A727
0x18000a6c4  mov     edx, 140h; uBytes
0x18000a6c9  call    cs:__imp_LocalAlloc
0x18000a6cf  mov     rbx, rax
0x18000a6d2  test    rax, rax
0x18000a6d5  jz      loc_18000A78E
0x18000a6db  mov     edx, [rdi+1Ch]; enum _SE_OBJECT_TYPE
0x18000a6de  mov     rcx, rax; this
0x18000a6e1  call    ??0CSecurityInformation@@QEAA@W4_SE_OBJECT_TYPE@@@Z; CSecurityInformation::CSecurityInformation(_SE_OBJECT_TYPE)
0x18000a6e6  lea     rax, ??_7CPrintSecurity@@6BISecurityInformation@@@; const CPrintSecurity::`vftable'{for `ISecurityInformation'}
0x18000a6ed  mov     [rbx], rax
0x18000a6f0  lea     rax, ??_7CSecurityInformation@@6BIEffectivePermission@@@; const CSecurityInformation::`vftable'{for `IEffectivePermission'}
0x18000a6f7  mov     [rbx+8], rax
0x18000a6fb  lea     rax, ??_7CPrintSecurity@@6BIEffectivePermission2@@@; const CPrintSecurity::`vftable'{for `IEffectivePermission2'}
0x18000a702  mov     [rbx+10h], rax
0x18000a706  lea     rax, ??_7CPrintSecurity@@6BISecurityObjectTypeInfo@@@; const CPrintSecurity::`vftable'{for `ISecurityObjectTypeInfo'}
0x18000a70d  mov     [rbx+18h], rax
0x18000a711  lea     rax, ??_7CPrintSecurity@@6BISecurityInformation3@@@; const CPrintSecurity::`vftable'{for `ISecurityInformation3'}
0x18000a718  mov     [rbx+20h], rax
0x18000a71c  lea     rax, ??_7CPrintSecurity@@6BISecurityInformation4@@@; const CPrintSecurity::`vftable'{for `ISecurityInformation4'}
0x18000a723  mov     [rbx+28h], rax
0x18000a727  mov     rax, [rbx]
0x18000a72a  mov     rcx, rbx
0x18000a72d  mov     r9, [rdi+30h]
0x18000a731  mov     r8d, [rdi+2Ch]
0x18000a735  mov     rdx, [rdi+40h]
0x18000a739  mov     r10, [rax+58h]
0x18000a73d  mov     eax, [rdi+4Ch]
0x18000a740  mov     [rsp+68h+var_40], eax
0x18000a744  mov     rax, [rdi+38h]
0x18000a748  mov     [rsp+68h+var_48], rax
0x18000a74d  mov     rax, r10
0x18000a750  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a755  mov     esi, eax
0x18000a757  test    eax, eax
0x18000a759  js      short loc_18000A77F
0x18000a75b  mov     [r14], rbx
0x18000a75e  mov     qword ptr [rdi+40h], 0
0x18000a766  mov     qword ptr [rdi+30h], 0
0x18000a76e  mov     qword ptr [rdi+38h], 0
0x18000a776  mov     dword ptr [rdi+28h], 0FFFFFFFFh
0x18000a77d  jmp     short loc_18000A78E
0x18000a77f  mov     rax, [rbx]
0x18000a782  mov     rcx, rbx
0x18000a785  mov     rax, [rax+10h]
0x18000a789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a78e  mov     eax, esi
0x18000a790  add     rsp, 48h
0x18000a794  pop     r14
0x18000a796  pop     rdi
0x18000a797  pop     rsi
0x18000a798  pop     rbx
0x18000a799  retn
```
