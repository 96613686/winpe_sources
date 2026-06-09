# SecMgrReleasePeerIpAddress(MSMSEC_PORT_CONTEXT *)

- ea: `0x180019648`
- end: `0x1800197e2`
- name: `?SecMgrReleasePeerIpAddress@@YAXPEAUMSMSEC_PORT_CONTEXT@@@Z`
- size: `410`
- prototype: `void __fastcall(struct MSMSEC_PORT_CONTEXT *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180018dd8`

## callees

- `0x18000892c`
- `0x180008998`
- `0x180019648`
- `0x18001b3d0`
- `0x180055a38`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x1800196f2`
- `MobileNetworking!ReleaseWriteLock` at `0x1800196f2`
- `MobileNetworking!AcquireWriteLock` at `0x18001969b`
- `MobileNetworking!AcquireWriteLock` at `0x18001969b`

## pseudocode

```c
void __fastcall SecMgrReleasePeerIpAddress(struct MSMSEC_PORT_CONTEXT *a1, __int64 a2, int a3)
{
  PVOID *v4; // rcx
  int v5; // r8d
  struct _IP_ALLOCATION_MGR *v6; // rcx
  unsigned int v7; // edi
  PVOID *v8; // rcx

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 106, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids);
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 17) & 0x100) != 0 )
      WPP_SF_Ls((unsigned int)v4[7], 11, a3, *(_DWORD *)(*((_QWORD *)a1 + 3) + 2496LL), (__int64)">>> Locking >>>");
  }
  AcquireWriteLock(*((_QWORD *)a1 + 3), *((_QWORD *)a1 + 3) + 2512LL, "SecMgrReleasePeerIpAddress", 1339);
  v6 = *(struct _IP_ALLOCATION_MGR **)(*((_QWORD *)a1 + 3) + 3336LL);
  if ( v6 )
  {
    v7 = IpAllocationMgrRelease(v6, (unsigned __int8 *const)a1 + 302);
LABEL_9:
    v8 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_10;
  }
  v8 = (PVOID *)WPP_GLOBAL_Control;
  v7 = 0;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_13;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      107,
      &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids,
      *((unsigned int *)a1 + 78));
    goto LABEL_9;
  }
LABEL_10:
  if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 17) & 0x100) != 0 )
    WPP_SF_Ls((unsigned int)v8[7], 11, v5, *(_DWORD *)(*((_QWORD *)a1 + 3) + 2496LL), (__int64)"<<< Unlocking <<<");
LABEL_13:
  ReleaseWriteLock(*((_QWORD *)a1 + 3), *((_QWORD *)a1 + 3) + 2512LL, "SecMgrReleasePeerIpAddress", 1350);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 108, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids, v7);
}

```

## disassembly

```asm
0x180019648  push    rbx
0x18001964a  push    rbp
0x18001964b  push    rsi
0x18001964c  push    rdi
0x18001964d  sub     rsp, 38h
0x180019651  mov     rbx, rcx
0x180019654  mov     rcx, cs:WPP_GLOBAL_Control
0x18001965b  lea     rsi, WPP_GLOBAL_Control
0x180019662  mov     ebp, 100h
0x180019667  cmp     rcx, rsi
0x18001966a  jz      short loc_180019683
0x18001966c  test    [rcx+44h], ebp
0x18001966f  jnz     loc_180019750
0x180019675  cmp     rcx, rsi
0x180019678  jz      short loc_180019683
0x18001967a  test    [rcx+44h], ebp
0x18001967d  jnz     loc_180019771
0x180019683  mov     rcx, [rbx+18h]
0x180019687  lea     r8, aSecmgrreleasep; "SecMgrReleasePeerIpAddress"
0x18001968e  mov     r9d, 53Bh
0x180019694  lea     rdx, [rcx+9D0h]
0x18001969b  call    cs:__imp_AcquireWriteLock
0x1800196a2  nop     dword ptr [rax+rax+00h]
0x1800196a7  mov     rax, [rbx+18h]
0x1800196ab  mov     rcx, [rax+0D08h]; struct _IP_ALLOCATION_MGR *
0x1800196b2  test    rcx, rcx
0x1800196b5  jz      short loc_18001971D
0x1800196b7  lea     rdx, [rbx+12Eh]; unsigned __int8 *
0x1800196be  call    ?IpAllocationMgrRelease@@YAKPEAU_IP_ALLOCATION_MGR@@QEAE@Z; IpAllocationMgrRelease(_IP_ALLOCATION_MGR *,uchar * const)
0x1800196c3  mov     edi, eax
0x1800196c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800196cc  cmp     rcx, rsi
0x1800196cf  jz      short loc_1800196DA
0x1800196d1  test    [rcx+44h], ebp
0x1800196d4  jnz     loc_18001979B
0x1800196da  mov     rcx, [rbx+18h]
0x1800196de  lea     r8, aSecmgrreleasep; "SecMgrReleasePeerIpAddress"
0x1800196e5  mov     r9d, 546h
0x1800196eb  lea     rdx, [rcx+9D0h]
0x1800196f2  call    cs:__imp_ReleaseWriteLock
0x1800196f9  nop     dword ptr [rax+rax+00h]
0x1800196fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180019705  cmp     rcx, rsi
0x180019708  jz      short loc_180019713
0x18001970a  test    [rcx+44h], ebp
0x18001970d  jnz     loc_1800197C5
0x180019713  add     rsp, 38h
0x180019717  pop     rdi
0x180019718  pop     rsi
0x180019719  pop     rbp
0x18001971a  pop     rbx
0x18001971b  retn
0x18001971d  mov     rcx, cs:WPP_GLOBAL_Control
0x180019724  xor     edi, edi
0x180019726  cmp     rcx, rsi
0x180019729  jz      short loc_1800196DA
0x18001972b  test    byte ptr [rcx+44h], 2
0x18001972f  jz      short loc_1800196CC
0x180019731  mov     r9d, [rbx+138h]
0x180019738  lea     edx, [rdi+6Bh]
0x18001973b  mov     rcx, [rcx+38h]
0x18001973f  lea     r8, WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids
0x180019746  call    WPP_SF_d
0x18001974b  jmp     loc_1800196C5
0x180019750  mov     rcx, [rcx+38h]
0x180019754  lea     r8, WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids
0x18001975b  mov     edx, 6Ah ; 'j'
0x180019760  call    WPP_SF_
0x180019765  mov     rcx, cs:WPP_GLOBAL_Control
0x18001976c  jmp     loc_180019675
0x180019771  mov     r9, [rbx+18h]
0x180019775  lea     rax, aLocking; ">>> Locking >>>"
0x18001977c  mov     rcx, [rcx+38h]
0x180019780  mov     edx, 0Bh
0x180019785  mov     [rsp+58h+var_38], rax
0x18001978a  mov     r9d, [r9+9C0h]
0x180019791  call    WPP_SF_Ls
0x180019796  jmp     loc_180019683
0x18001979b  mov     r9, [rbx+18h]
0x18001979f  lea     rax, aUnlocking; "<<< Unlocking <<<"
0x1800197a6  mov     rcx, [rcx+38h]
0x1800197aa  mov     edx, 0Bh
0x1800197af  mov     [rsp+58h+var_38], rax
0x1800197b4  mov     r9d, [r9+9C0h]
0x1800197bb  call    WPP_SF_Ls
0x1800197c0  jmp     loc_1800196DA
0x1800197c5  mov     rcx, [rcx+38h]
0x1800197c9  lea     r8, WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids
0x1800197d0  mov     edx, 6Ch ; 'l'
0x1800197d5  mov     r9d, edi
0x1800197d8  call    WPP_SF_d
0x1800197dd  jmp     loc_180019713
```
