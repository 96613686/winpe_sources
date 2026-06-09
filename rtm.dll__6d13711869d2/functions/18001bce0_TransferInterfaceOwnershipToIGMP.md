# TransferInterfaceOwnershipToIGMP

- ea: `0x18001bce0`
- end: `0x18001be63`
- name: `TransferInterfaceOwnershipToIGMP`
- size: `387`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180014580`

## callees

- `0x18001b9ac`
- `0x18001ba30`
- `0x18001bce0`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x180020010`

## string_xrefs

- `0x18001bd4b`: `TransferInterfaceOwnershipToProtocol : Could not find IGMP protocol entry`

## pseudocode

```c
__int64 __fastcall TransferInterfaceOwnershipToIGMP(__int64 a1, __int64 a2)
{
  __int64 i; // rbx
  __int64 v5; // r9
  __int64 v6; // r8
  unsigned int v7; // esi
  __int64 v9; // rdx
  int v10; // [rsp+20h] [rbp-828h] BYREF
  _BYTE v11[2044]; // [rsp+24h] [rbp-824h] BYREF

  v10 = 0;
  memset_0(v11, 0, sizeof(v11));
  for ( i = qword_18002B9A8; ; i = *(_QWORD *)i )
  {
    if ( (__int64 *)i == &qword_18002B9A8 )
      goto LABEL_5;
    if ( *(_DWORD *)(i + 16) == 10 )
      break;
  }
  if ( !i )
  {
LABEL_5:
    if ( qword_18002B8A8 )
    {
      v5 = *(unsigned int *)(a2 + 20);
      v6 = *(unsigned int *)(a2 + 16);
      LOWORD(v10) = 0;
      FormatRRASErrorString(&v10, L"TransferInterfaceOwnershipToProtocol : Could not find IGMP protocol entry", v6, v5);
      ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v10);
    }
    return 635;
  }
  v7 = 0;
  if ( qword_18002B8A8 )
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gMgmTemplateFunc)(
      gMgmEtwContext,
      qword_18002B8A8,
      L"Invoked Disable IGMP Alert ");
  (*(void (__fastcall **)(_QWORD, _QWORD))(i + 96))(*(unsigned int *)(a2 + 16), *(unsigned int *)(a2 + 20));
  DeleteInInterfaceRefs(a2 + 56);
  DeleteOutInterfaceRefs(a1, a2, 0);
  *(_WORD *)(a2 + 32) &= ~0x4000u;
  DeleteOutInterfaceRefs(a1, a2, 1);
  v9 = qword_18002B8A8;
  *(_DWORD *)(a2 + 24) = *(_DWORD *)(i + 16);
  *(_DWORD *)(a2 + 28) = *(_DWORD *)(i + 20);
  if ( v9 )
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gMgmTemplateFunc)(
      gMgmEtwContext,
      v9,
      L"Invoked Enable IGMP Alert ");
  (*(void (__fastcall **)(_QWORD, _QWORD))(i + 104))(*(unsigned int *)(a2 + 16), *(unsigned int *)(a2 + 20));
  return v7;
}

```

## disassembly

```asm
0x18001bce0  mov     [rsp+arg_10], rbx
0x18001bce5  push    rbp
0x18001bce6  push    rsi
0x18001bce7  push    rdi
0x18001bce8  sub     rsp, 830h
0x18001bcef  mov     rax, cs:__security_cookie
0x18001bcf6  xor     rax, rsp
0x18001bcf9  mov     [rsp+848h+var_28], rax
0x18001bd01  mov     rdi, rdx
0x18001bd04  mov     rbp, rcx
0x18001bd07  xor     eax, eax
0x18001bd09  lea     rcx, [rsp+848h+var_824]; void *
0x18001bd0e  xor     edx, edx; Val
0x18001bd10  mov     [rsp+848h+var_828], eax
0x18001bd14  mov     r8d, 7FCh; Size
0x18001bd1a  call    memset_0
0x18001bd1f  mov     rbx, cs:qword_18002B9A8
0x18001bd26  lea     rax, qword_18002B9A8
0x18001bd2d  jmp     short loc_18001BD38
0x18001bd2f  cmp     dword ptr [rbx+10h], 0Ah
0x18001bd33  jz      short loc_18001BDB0
0x18001bd35  mov     rbx, [rbx]
0x18001bd38  cmp     rbx, rax
0x18001bd3b  jnz     short loc_18001BD2F
0x18001bd3d  cmp     cs:qword_18002B8A8, 0
0x18001bd45  jz      short loc_18001BD86
0x18001bd47  mov     r9d, [rdi+14h]
0x18001bd4b  lea     rdx, aTransferinterf; "TransferInterfaceOwnershipToProtocol : "...
0x18001bd52  mov     r8d, [rdi+10h]
0x18001bd56  lea     rcx, [rsp+848h+var_828]
0x18001bd5b  xor     eax, eax
0x18001bd5d  mov     word ptr [rsp+848h+var_828], ax
0x18001bd62  call    FormatRRASErrorString
0x18001bd67  mov     rdx, cs:qword_18002B8A8
0x18001bd6e  lea     r8, [rsp+848h+var_828]
0x18001bd73  mov     rcx, cs:gMgmEtwContext
0x18001bd7a  mov     rax, cs:gMgmTemplateFunc
0x18001bd81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd86  mov     esi, 27Bh
0x18001bd8b  mov     eax, esi
0x18001bd8d  mov     rcx, [rsp+848h+var_28]
0x18001bd95  xor     rcx, rsp; StackCookie
0x18001bd98  call    __security_check_cookie
0x18001bd9d  mov     rbx, [rsp+848h+arg_10]
0x18001bda5  add     rsp, 830h
0x18001bdac  pop     rdi
0x18001bdad  pop     rsi
0x18001bdae  pop     rbp
0x18001bdaf  retn
0x18001bdb0  test    rbx, rbx
0x18001bdb3  jz      short loc_18001BD3D
0x18001bdb5  mov     rdx, cs:qword_18002B8A8
0x18001bdbc  xor     esi, esi
0x18001bdbe  test    rdx, rdx
0x18001bdc1  jz      short loc_18001BDDD
0x18001bdc3  mov     rcx, cs:gMgmEtwContext
0x18001bdca  lea     r8, aInvokedDisable; "Invoked Disable IGMP Alert "
0x18001bdd1  mov     rax, cs:gMgmTemplateFunc
0x18001bdd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bddd  mov     edx, [rdi+14h]
0x18001bde0  mov     ecx, [rdi+10h]
0x18001bde3  mov     rax, [rbx+60h]
0x18001bde7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bdec  lea     rcx, [rdi+38h]
0x18001bdf0  call    DeleteInInterfaceRefs
0x18001bdf5  xor     r8d, r8d
0x18001bdf8  mov     rdx, rdi
0x18001bdfb  mov     rcx, rbp
0x18001bdfe  call    DeleteOutInterfaceRefs
0x18001be03  mov     eax, 0BFFFh
0x18001be08  mov     r8d, 1
0x18001be0e  and     [rdi+20h], ax
0x18001be12  mov     rdx, rdi
0x18001be15  mov     rcx, rbp
0x18001be18  call    DeleteOutInterfaceRefs
0x18001be1d  mov     eax, [rbx+10h]
0x18001be20  mov     rdx, cs:qword_18002B8A8
0x18001be27  mov     [rdi+18h], eax
0x18001be2a  mov     eax, [rbx+14h]
0x18001be2d  mov     [rdi+1Ch], eax
0x18001be30  test    rdx, rdx
0x18001be33  jz      short loc_18001BE4F
0x18001be35  mov     rcx, cs:gMgmEtwContext
0x18001be3c  lea     r8, aInvokedEnableI; "Invoked Enable IGMP Alert "
0x18001be43  mov     rax, cs:gMgmTemplateFunc
0x18001be4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be4f  mov     edx, [rdi+14h]
0x18001be52  mov     ecx, [rdi+10h]
0x18001be55  mov     rax, [rbx+68h]
0x18001be59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be5e  jmp     loc_18001BD8B
```
