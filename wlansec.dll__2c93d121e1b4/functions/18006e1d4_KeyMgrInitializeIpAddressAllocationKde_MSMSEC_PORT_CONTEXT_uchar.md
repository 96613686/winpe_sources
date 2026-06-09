# KeyMgrInitializeIpAddressAllocationKde(MSMSEC_PORT_CONTEXT *,uchar *)

- ea: `0x18006e1d4`
- end: `0x18006e3ec`
- name: `?KeyMgrInitializeIpAddressAllocationKde@@YAKPEAUMSMSEC_PORT_CONTEXT@@PEAE@Z`
- size: `536`
- prototype: `unsigned int __fastcall(struct MSMSEC_PORT_CONTEXT *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18006ed94`

## callees

- `0x18000892c`
- `0x180008998`
- `0x1800169c0`
- `0x18006e1d4`
- `0x180075710`
- `0x180075d30`
- `0x180076198`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x18006e3a5`
- `MobileNetworking!ReleaseWriteLock` at `0x18006e3a5`
- `MobileNetworking!AcquireWriteLock` at `0x18006e262`
- `MobileNetworking!AcquireWriteLock` at `0x18006e262`

## pseudocode

```c
__int64 __fastcall KeyMgrInitializeIpAddressAllocationKde(struct MSMSEC_PORT_CONTEXT *a1, unsigned __int8 *a2)
{
  __int64 v2; // rsi
  struct _IP_ALLOCATION_MGR *v5; // rbx
  unsigned int v6; // edi
  unsigned int LocalAddress; // eax
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  unsigned __int8 v10; // cl
  ULONG S_addr; // eax
  unsigned __int8 v13; // [rsp+60h] [rbp+8h] BYREF
  struct in_addr v14; // [rsp+68h] [rbp+10h] BYREF
  in_addr v15; // [rsp+70h] [rbp+18h] BYREF

  v2 = *((_QWORD *)a1 + 3);
  v15 = 0;
  v14 = 0;
  v13 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 134, &WPP_bae8f620b4973c46822a562a2a1b1dbf_Traceguids);
  TraceAdapterId(*(_DWORD *)(v2 + 2496), ">>> Locking >>>");
  AcquireWriteLock(v2, v2 + 2512, "KeyMgrInitializeIpAddressAllocationKde", 1498);
  v5 = *(struct _IP_ALLOCATION_MGR **)(v2 + 3336);
  if ( !v5 )
  {
    v6 = 50;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 135, &WPP_bae8f620b4973c46822a562a2a1b1dbf_Traceguids);
    goto LABEL_18;
  }
  LocalAddress = IpAllocationMgrGetLocalAddress(*(struct _IP_ALLOCATION_MGR **)(v2 + 3336), &v15, &v13);
  v6 = LocalAddress;
  if ( LocalAddress )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_18;
    v9 = 136;
LABEL_12:
    WPP_SF_d(v8[7], v9, &WPP_bae8f620b4973c46822a562a2a1b1dbf_Traceguids, LocalAddress);
    goto LABEL_18;
  }
  LocalAddress = IpAllocationMgrAllocate(v5, (unsigned __int8 *const)a1 + 302, &v14);
  v6 = LocalAddress;
  if ( !LocalAddress )
  {
    v10 = v13;
    *(_WORD *)a2 = 4317;
    *((_WORD *)a2 + 1) = (_WORD)WFA_KEY_DATA_OUI;
    a2[4] = byte_1800AE902;
    S_addr = v14.S_un.S_addr;
    a2[5] = 5;
    *(_DWORD *)(a2 + 6) = S_addr;
    SetToSubnetMask(v10, a2 + 10);
    *(in_addr *)(a2 + 14) = v15;
    goto LABEL_18;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    v9 = 137;
    goto LABEL_12;
  }
LABEL_18:
  TraceAdapterId(*(_DWORD *)(v2 + 2496), "<<< Unlocking <<<");
  ReleaseWriteLock(v2, v2 + 2512, "KeyMgrInitializeIpAddressAllocationKde", 1545);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 138, &WPP_bae8f620b4973c46822a562a2a1b1dbf_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x18006e1d4  push    rbx
0x18006e1d6  push    rbp
0x18006e1d7  push    rsi
0x18006e1d8  push    rdi
0x18006e1d9  push    r13
0x18006e1db  push    r14
0x18006e1dd  push    r15
0x18006e1df  sub     rsp, 20h
0x18006e1e3  mov     rsi, [rcx+18h]
0x18006e1e7  mov     r14, rdx
0x18006e1ea  mov     rbp, rcx
0x18006e1ed  mov     dword ptr [rsp+58h+arg_10.S_un], 0
0x18006e1f5  mov     dword ptr [rsp+58h+arg_8.S_un], 0
0x18006e1fd  mov     [rsp+58h+arg_0], 0
0x18006e202  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e209  lea     rax, WPP_GLOBAL_Control
0x18006e210  lea     r13, WPP_bae8f620b4973c46822a562a2a1b1dbf_Traceguids
0x18006e217  cmp     rcx, rax
0x18006e21a  jz      short loc_18006E236
0x18006e21c  test    dword ptr [rcx+44h], 100h
0x18006e223  jz      short loc_18006E236
0x18006e225  mov     rcx, [rcx+38h]
0x18006e229  mov     edx, 86h
0x18006e22e  mov     r8, r13
0x18006e231  call    WPP_SF_
0x18006e236  mov     ecx, [rsi+9C0h]; unsigned int
0x18006e23c  lea     rdx, aLocking; ">>> Locking >>>"
0x18006e243  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x18006e248  lea     r15, [rsi+9D0h]
0x18006e24f  mov     r9d, 5DAh
0x18006e255  mov     rdx, r15
0x18006e258  lea     r8, aKeymgrinitiali; "KeyMgrInitializeIpAddressAllocationKde"
0x18006e25f  mov     rcx, rsi
0x18006e262  call    cs:__imp_AcquireWriteLock
0x18006e269  nop     dword ptr [rax+rax+00h]
0x18006e26e  mov     rbx, [rsi+0D08h]
0x18006e275  test    rbx, rbx
0x18006e278  jnz     short loc_18006E2B2
0x18006e27a  lea     edi, [rbx+32h]
0x18006e27d  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e284  lea     rbx, WPP_GLOBAL_Control
0x18006e28b  cmp     rcx, rbx
0x18006e28e  jz      loc_18006E380
0x18006e294  test    byte ptr [rcx+44h], 1
0x18006e298  jz      loc_18006E380
0x18006e29e  mov     rcx, [rcx+38h]
0x18006e2a2  lea     edx, [rdi+55h]
0x18006e2a5  mov     r8, r13
0x18006e2a8  call    WPP_SF_
0x18006e2ad  jmp     loc_18006E380
0x18006e2b2  lea     r8, [rsp+58h+arg_0]; unsigned __int8 *
0x18006e2b7  mov     rcx, rbx; struct _IP_ALLOCATION_MGR *
0x18006e2ba  lea     rdx, [rsp+58h+arg_10]; struct in_addr *
0x18006e2bf  call    ?IpAllocationMgrGetLocalAddress@@YAKPEAU_IP_ALLOCATION_MGR@@PEAUin_addr@@PEAE@Z; IpAllocationMgrGetLocalAddress(_IP_ALLOCATION_MGR *,in_addr *,uchar *)
0x18006e2c4  mov     edi, eax
0x18006e2c6  test    eax, eax
0x18006e2c8  jz      short loc_18006E301
0x18006e2ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e2d1  lea     rbx, WPP_GLOBAL_Control
0x18006e2d8  cmp     rcx, rbx
0x18006e2db  jz      loc_18006E380
0x18006e2e1  test    byte ptr [rcx+44h], 1
0x18006e2e5  jz      loc_18006E380
0x18006e2eb  mov     edx, 88h
0x18006e2f0  mov     rcx, [rcx+38h]
0x18006e2f4  mov     r9d, eax
0x18006e2f7  mov     r8, r13
0x18006e2fa  call    WPP_SF_d
0x18006e2ff  jmp     short loc_18006E380
0x18006e301  lea     rdx, [rbp+12Eh]; unsigned __int8 *
0x18006e308  mov     rcx, rbx; struct _IP_ALLOCATION_MGR *
0x18006e30b  lea     r8, [rsp+58h+arg_8]; struct in_addr *
0x18006e310  call    ?IpAllocationMgrAllocate@@YAKPEAU_IP_ALLOCATION_MGR@@QEAEPEAUin_addr@@@Z; IpAllocationMgrAllocate(_IP_ALLOCATION_MGR *,uchar * const,in_addr *)
0x18006e315  mov     edi, eax
0x18006e317  test    eax, eax
0x18006e319  jz      short loc_18006E33B
0x18006e31b  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e322  lea     rbx, WPP_GLOBAL_Control
0x18006e329  cmp     rcx, rbx
0x18006e32c  jz      short loc_18006E380
0x18006e32e  test    byte ptr [rcx+44h], 1
0x18006e332  jz      short loc_18006E380
0x18006e334  mov     edx, 89h
0x18006e339  jmp     short loc_18006E2F0
0x18006e33b  mov     cl, [rsp+58h+arg_0]; unsigned __int8
0x18006e33f  lea     rdx, [r14+0Ah]; unsigned __int8 *
0x18006e343  mov     word ptr [r14], 10DDh
0x18006e349  movzx   eax, cs:?WFA_KEY_DATA_OUI@@3PAEA; uchar near * WFA_KEY_DATA_OUI
0x18006e350  mov     [r14+2], ax
0x18006e355  mov     al, cs:byte_1800AE902
0x18006e35b  mov     [r14+4], al
0x18006e35f  mov     eax, dword ptr [rsp+58h+arg_8.S_un]
0x18006e363  mov     byte ptr [r14+5], 5
0x18006e368  mov     [r14+6], eax
0x18006e36c  call    ?SetToSubnetMask@@YAXEPEAE@Z; SetToSubnetMask(uchar,uchar *)
0x18006e371  mov     eax, dword ptr [rsp+58h+arg_10.S_un]
0x18006e375  lea     rbx, WPP_GLOBAL_Control
0x18006e37c  mov     [r14+0Eh], eax
0x18006e380  mov     ecx, [rsi+9C0h]; unsigned int
0x18006e386  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x18006e38d  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x18006e392  mov     r9d, 609h
0x18006e398  lea     r8, aKeymgrinitiali; "KeyMgrInitializeIpAddressAllocationKde"
0x18006e39f  mov     rdx, r15
0x18006e3a2  mov     rcx, rsi
0x18006e3a5  call    cs:__imp_ReleaseWriteLock
0x18006e3ac  nop     dword ptr [rax+rax+00h]
0x18006e3b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e3b8  cmp     rcx, rbx
0x18006e3bb  jz      short loc_18006E3DA
0x18006e3bd  test    dword ptr [rcx+44h], 100h
0x18006e3c4  jz      short loc_18006E3DA
0x18006e3c6  mov     rcx, [rcx+38h]
0x18006e3ca  mov     edx, 8Ah
0x18006e3cf  mov     r9d, edi
0x18006e3d2  mov     r8, r13
0x18006e3d5  call    WPP_SF_d
0x18006e3da  mov     eax, edi
0x18006e3dc  add     rsp, 20h
0x18006e3e0  pop     r15
0x18006e3e2  pop     r14
0x18006e3e4  pop     r13
0x18006e3e6  pop     rdi
0x18006e3e7  pop     rsi
0x18006e3e8  pop     rbp
0x18006e3e9  pop     rbx
0x18006e3ea  retn
```
