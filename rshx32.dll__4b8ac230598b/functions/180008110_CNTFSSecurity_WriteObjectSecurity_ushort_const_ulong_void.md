# CNTFSSecurity::WriteObjectSecurity(ushort const *,ulong,void *)

- ea: `0x180008110`
- end: `0x18000822f`
- name: `?WriteObjectSecurity@CNTFSSecurity@@MEAAJPEBGKPEAX@Z`
- size: `287`
- prototype: `__int64 __fastcall(CNTFSSecurity *__hidden this, const unsigned __int16 *, unsigned int, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180008110`
- `0x18000c8b0`

## import_xrefs

- `SHELL32!SHChangeNotify` at `0x180008201`
- `SHELL32!SHChangeNotify` at `0x180008201`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180008150`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180008150`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180008197`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180008197`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x1800081be`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x1800081be`

## pseudocode

```c
__int64 __fastcall CNTFSSecurity::WriteObjectSecurity(
        CNTFSSecurity *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        void *a4)
{
  int v8; // r14d
  int v9; // ebx
  DWORD dwRevision[14]; // [rsp+20h] [rbp-38h] BYREF
  WORD pControl; // [rsp+78h] [rbp+20h] BYREF

  if ( !a4 || !a2 )
    return 2147500035LL;
  if ( a3 && IsValidSecurityDescriptor(a4) )
  {
    v8 = CSecurityInformation::WriteObjectSecurity(this, a2, a3, a4);
    if ( v8 == -2147024891 )
    {
      pControl = 0;
      dwRevision[0] = 0;
      GetSecurityDescriptorControl(a4, &pControl, dwRevision);
      v9 = a3 & 4;
      if ( (a3 & 4) == 0
        || (pControl & 0x1000) == 0 && (*((_DWORD *)this + 16) & 0x200) == 0
        || !SetFileSecurityW(a2, a3, a4) )
      {
        return (unsigned int)v8;
      }
      v8 = CSecurityInformation::WriteObjectSecurity(this, a2, a3, a4);
    }
    else
    {
      v9 = a3 & 4;
    }
    if ( v8 >= 0 && v9 && (*((_BYTE *)this + 64) & 4) != 0 )
      SHChangeNotify(4096, 0x3005u, a2, 0);
    return (unsigned int)v8;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180008110  mov     [rsp+arg_0], rbx
0x180008115  mov     [rsp+arg_8], rbp
0x18000811a  push    rsi
0x18000811b  push    rdi
0x18000811c  push    r12
0x18000811e  push    r14
0x180008120  push    r15
0x180008122  sub     rsp, 30h
0x180008126  mov     rsi, r9
0x180008129  mov     edi, r8d
0x18000812c  mov     rbp, rdx
0x18000812f  mov     r15, rcx
0x180008132  test    r9, r9
0x180008135  jz      loc_180008213
0x18000813b  test    rdx, rdx
0x18000813e  jz      loc_180008213
0x180008144  test    r8d, r8d
0x180008147  jz      loc_18000820C
0x18000814d  mov     rcx, r9; pSecurityDescriptor
0x180008150  call    cs:__imp_IsValidSecurityDescriptor
0x180008156  test    eax, eax
0x180008158  jz      loc_18000820C
0x18000815e  mov     r9, rsi; void *
0x180008161  mov     r8d, edi; unsigned int
0x180008164  mov     rdx, rbp; unsigned __int16 *
0x180008167  mov     rcx, r15; this
0x18000816a  call    ?WriteObjectSecurity@CSecurityInformation@@MEAAJPEBGKPEAX@Z; CSecurityInformation::WriteObjectSecurity(ushort const *,ulong,void *)
0x18000816f  mov     r14d, eax
0x180008172  mov     r12d, 1000h
0x180008178  cmp     eax, 80070005h
0x18000817d  jnz     short loc_1800081DE
0x18000817f  xor     ecx, ecx
0x180008181  lea     r8, [rsp+58h+dwRevision]; lpdwRevision
0x180008186  mov     [rsp+58h+pControl], cx
0x18000818b  lea     rdx, [rsp+58h+pControl]; pControl
0x180008190  mov     [rsp+58h+dwRevision], ecx
0x180008194  mov     rcx, rsi; pSecurityDescriptor
0x180008197  call    cs:__imp_GetSecurityDescriptorControl
0x18000819d  mov     ebx, edi
0x18000819f  and     ebx, 4
0x1800081a2  jz      short loc_180008207
0x1800081a4  test    [rsp+58h+pControl], r12w
0x1800081aa  jnz     short loc_1800081B6
0x1800081ac  test    dword ptr [r15+40h], 200h
0x1800081b4  jz      short loc_180008207
0x1800081b6  mov     r8, rsi; pSecurityDescriptor
0x1800081b9  mov     edx, edi; SecurityInformation
0x1800081bb  mov     rcx, rbp; lpFileName
0x1800081be  call    cs:__imp_SetFileSecurityW
0x1800081c4  test    eax, eax
0x1800081c6  jz      short loc_180008207
0x1800081c8  mov     r9, rsi; void *
0x1800081cb  mov     r8d, edi; unsigned int
0x1800081ce  mov     rdx, rbp; unsigned __int16 *
0x1800081d1  mov     rcx, r15; this
0x1800081d4  call    ?WriteObjectSecurity@CSecurityInformation@@MEAAJPEBGKPEAX@Z; CSecurityInformation::WriteObjectSecurity(ushort const *,ulong,void *)
0x1800081d9  mov     r14d, eax
0x1800081dc  jmp     short loc_1800081E3
0x1800081de  mov     ebx, edi
0x1800081e0  and     ebx, 4
0x1800081e3  test    r14d, r14d
0x1800081e6  js      short loc_180008207
0x1800081e8  test    ebx, ebx
0x1800081ea  jz      short loc_180008207
0x1800081ec  test    byte ptr [r15+40h], 4
0x1800081f1  jz      short loc_180008207
0x1800081f3  xor     r9d, r9d; dwItem2
0x1800081f6  mov     r8, rbp; dwItem1
0x1800081f9  mov     edx, 3005h; uFlags
0x1800081fe  mov     ecx, r12d; wEventId
0x180008201  call    cs:__imp_SHChangeNotify
0x180008207  mov     eax, r14d
0x18000820a  jmp     short loc_180008218
0x18000820c  mov     eax, 80070057h
0x180008211  jmp     short loc_180008218
0x180008213  mov     eax, 80004003h
0x180008218  mov     rbx, [rsp+58h+arg_0]
0x18000821d  mov     rbp, [rsp+58h+arg_8]
0x180008222  add     rsp, 30h
0x180008226  pop     r15
0x180008228  pop     r14
0x18000822a  pop     r12
0x18000822c  pop     rdi
0x18000822d  pop     rsi
0x18000822e  retn
```
