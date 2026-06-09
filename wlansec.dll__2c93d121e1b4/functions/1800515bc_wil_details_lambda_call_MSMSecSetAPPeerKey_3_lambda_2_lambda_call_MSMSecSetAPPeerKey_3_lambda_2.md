# wil::details::lambda_call__MSMSecSetAPPeerKey_::_3_::_lambda_2___::_lambda_call__MSMSecSetAPPeerKey_::_3_::_lambda_2___

- ea: `0x1800515bc`
- end: `0x180051645`
- name: `wil::details::lambda_call__MSMSecSetAPPeerKey_::_3_::_lambda_2___::_lambda_call__MSMSecSetAPPeerKey_::_3_::_lambda_2___`
- size: `137`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180095418`

## callees

- `0x180013bc0`
- `0x1800169c0`
- `0x1800515bc`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180051601`
- `MobileNetworking!ReleaseWriteLock` at `0x180051601`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::lambda_call__MSMSecSetAPPeerKey_::_3_::_lambda_2___::_lambda_call__MSMSecSetAPPeerKey_::_3_::_lambda_2___(
        _BYTE *a1)
{
  if ( a1[8] )
  {
    a1[8] = 0;
    TraceAdapterId(*(_DWORD *)(**(_QWORD **)a1 + 2496LL), "<<< Unlocking <<<");
    ReleaseWriteLock(**(_QWORD **)a1, **(_QWORD **)a1 + 2512LL, "MSMSecSetAPPeerKey::<lambda_2>::operator ()", 2493);
    TraceAdapterId(*(_DWORD *)(**(_QWORD **)a1 + 2496LL), "<<< Derefing <<<");
    SecMgrDerefAdapterEx(**(struct MSMSEC_INTF_CONTEXT ***)a1, "MSMSecSetAPPeerKey::<lambda_2>::operator ()", 2494);
  }
}

```

## disassembly

```asm
0x1800515bc  push    rbx
0x1800515be  sub     rsp, 20h
0x1800515c2  mov     rbx, rcx
0x1800515c5  cmp     byte ptr [rcx+8], 0
0x1800515c9  jz      short loc_18005163E
0x1800515cb  mov     byte ptr [rcx+8], 0
0x1800515cf  mov     rax, [rcx]
0x1800515d2  mov     rcx, [rax]
0x1800515d5  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x1800515dc  mov     ecx, [rcx+9C0h]; unsigned int
0x1800515e2  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x1800515e7  mov     rax, [rbx]
0x1800515ea  mov     rcx, [rax]
0x1800515ed  lea     rdx, [rcx+9D0h]
0x1800515f4  mov     r9d, 9BDh
0x1800515fa  lea     r8, aMsmsecsetappee_2; "MSMSecSetAPPeerKey::<lambda_2>::operato"...
0x180051601  call    cs:__imp_ReleaseWriteLock
0x180051608  nop     dword ptr [rax+rax+00h]
0x18005160d  mov     rax, [rbx]
0x180051610  mov     rcx, [rax]
0x180051613  lea     rdx, aDerefing; "<<< Derefing <<<"
0x18005161a  mov     ecx, [rcx+9C0h]; unsigned int
0x180051620  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180051625  mov     rcx, [rbx]
0x180051628  mov     r8d, 9BEh; int
0x18005162e  lea     rdx, aMsmsecsetappee_2; "MSMSecSetAPPeerKey::<lambda_2>::operato"...
0x180051635  mov     rcx, [rcx]; struct MSMSEC_INTF_CONTEXT *
0x180051638  call    ?SecMgrDerefAdapterEx@@YAXPEAUMSMSEC_INTF_CONTEXT@@PEBDH@Z; SecMgrDerefAdapterEx(MSMSEC_INTF_CONTEXT *,char const *,int)
0x18005163d  nop
0x18005163e  add     rsp, 20h
0x180051642  pop     rbx
0x180051643  retn
```
