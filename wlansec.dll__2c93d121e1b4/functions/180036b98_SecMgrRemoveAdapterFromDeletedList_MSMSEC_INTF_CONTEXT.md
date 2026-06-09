# SecMgrRemoveAdapterFromDeletedList(MSMSEC_INTF_CONTEXT *)

- ea: `0x180036b98`
- end: `0x180036c91`
- name: `?SecMgrRemoveAdapterFromDeletedList@@YAXPEAUMSMSEC_INTF_CONTEXT@@@Z`
- size: `249`
- prototype: `void __fastcall(struct MSMSEC_INTF_CONTEXT *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800115c0`
- `0x180013bc0`

## callees

- `0x180004518`
- `0x180036b98`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180036c7e`
- `MobileNetworking!AcquireWriteLock` at `0x180036bc0`
- `MobileNetworking!AcquireWriteLock` at `0x180036bc0`

## string_xrefs

- `0x180036ba5`: `SecMgrRemoveAdapterFromDeletedList`
- `0x180036c55`: `SecMgrRemoveAdapterFromDeletedList`

## pseudocode

```c
void __fastcall SecMgrRemoveAdapterFromDeletedList(struct MSMSEC_INTF_CONTEXT ***a1)
{
  struct MSMSEC_INTF_CONTEXT **v2; // rax
  struct MSMSEC_INTF_CONTEXT **v3; // r9

  AcquireWriteLock(&g_MSMSecState, qword_1800AEFC0, "SecMgrRemoveAdapterFromDeletedList", 436);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
    WPP_SF_qDDDDDD(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      24,
      *((unsigned __int8 *)a1 + 2364),
      a1,
      *((unsigned __int8 *)a1 + 2360),
      *((unsigned __int8 *)a1 + 2361),
      *((unsigned __int8 *)a1 + 2362),
      *((unsigned __int8 *)a1 + 2363),
      *((unsigned __int8 *)a1 + 2364),
      *((unsigned __int8 *)a1 + 2365));
  v2 = *a1;
  if ( (*a1)[1] != (struct MSMSEC_INTF_CONTEXT *)a1 || (v3 = a1[1], *v3 != (struct MSMSEC_INTF_CONTEXT *)a1) )
    __fastfail(3u);
  *v3 = (struct MSMSEC_INTF_CONTEXT *)v2;
  v2[1] = (struct MSMSEC_INTF_CONTEXT *)v3;
  ReleaseWriteLock(&g_MSMSecState, qword_1800AEFC0, "SecMgrRemoveAdapterFromDeletedList", 451);
}

```

## disassembly

```asm
0x180036b98  mov     [rsp+arg_0], rbx
0x180036b9d  push    rdi
0x180036b9e  sub     rsp, 50h
0x180036ba2  mov     rdi, rcx
0x180036ba5  lea     r8, aSecmgrremovead; "SecMgrRemoveAdapterFromDeletedList"
0x180036bac  lea     rcx, ?g_MSMSecState@@3UMSMSEC_GLOBAL_STATE@@A; MSMSEC_GLOBAL_STATE g_MSMSecState
0x180036bb3  mov     r9d, 1B4h
0x180036bb9  lea     rdx, qword_1800AEFC0
0x180036bc0  call    cs:__imp_AcquireWriteLock
0x180036bc7  nop     dword ptr [rax+rax+00h]
0x180036bcc  mov     rcx, cs:WPP_GLOBAL_Control
0x180036bd3  lea     rax, WPP_GLOBAL_Control
0x180036bda  cmp     rcx, rax
0x180036bdd  jz      short loc_180036C40
0x180036bdf  test    byte ptr [rcx+44h], 2
0x180036be3  jz      short loc_180036C40
0x180036be5  movzx   r9d, byte ptr [rdi+93Bh]
0x180036bed  mov     edx, 18h
0x180036bf2  movzx   eax, byte ptr [rdi+93Dh]
0x180036bf9  movzx   r8d, byte ptr [rdi+93Ch]
0x180036c01  movzx   r10d, byte ptr [rdi+93Ah]
0x180036c09  movzx   r11d, byte ptr [rdi+939h]
0x180036c11  movzx   ebx, byte ptr [rdi+938h]
0x180036c18  mov     rcx, [rcx+38h]
0x180036c1c  mov     [rsp+58h+var_10], eax
0x180036c20  mov     [rsp+58h+var_18], r8d
0x180036c25  mov     [rsp+58h+var_20], r9d
0x180036c2a  mov     r9, rdi
0x180036c2d  mov     [rsp+58h+var_28], r10d
0x180036c32  mov     [rsp+58h+var_30], r11d
0x180036c37  mov     [rsp+58h+var_38], ebx
0x180036c3b  call    WPP_SF_qDDDDDD
0x180036c40  mov     rax, [rdi]
0x180036c43  cmp     [rax+8], rdi
0x180036c47  jnz     short loc_180036C8A
0x180036c49  mov     r9, [rdi+8]
0x180036c4d  cmp     [r9], rdi
0x180036c50  jnz     short loc_180036C8A
0x180036c52  mov     [r9], rax
0x180036c55  lea     r8, aSecmgrremovead; "SecMgrRemoveAdapterFromDeletedList"
0x180036c5c  mov     [rax+8], r9
0x180036c60  lea     rdx, qword_1800AEFC0
0x180036c67  mov     r9d, 1C3h
0x180036c6d  lea     rcx, ?g_MSMSecState@@3UMSMSEC_GLOBAL_STATE@@A; MSMSEC_GLOBAL_STATE g_MSMSecState
0x180036c74  mov     rbx, [rsp+58h+arg_0]
0x180036c79  add     rsp, 50h
0x180036c7d  pop     rdi
0x180036c7e  jmp     cs:__imp_ReleaseWriteLock
0x180036c8a  mov     ecx, 3
0x180036c8f  int     29h; Win8: RtlFailFast(ecx)
```
