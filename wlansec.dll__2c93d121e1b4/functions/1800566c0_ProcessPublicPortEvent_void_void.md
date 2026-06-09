# ProcessPublicPortEvent(void *,void *)

- ea: `0x1800566c0`
- end: `0x18005681a`
- name: `?ProcessPublicPortEvent@@YAXPEAX0@Z`
- size: `346`
- prototype: `void __fastcall(struct MSMSEC_PORT_CONTEXT *, void *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180008998`
- `0x180013600`
- `0x18002bb08`
- `0x180041c10`
- `0x1800566c0`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x1800567d8`
- `MobileNetworking!ReleaseWriteLock` at `0x1800567d8`
- `MobileNetworking!AcquireWriteLock` at `0x180056733`
- `MobileNetworking!AcquireWriteLock` at `0x180056733`

## pseudocode

```c
void __fastcall ProcessPublicPortEvent(struct MSMSEC_PORT_CONTEXT *a1, void *a2)
{
  unsigned int v3; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      34,
      &WPP_4b473b0d41083bd40dfc61d99b047aaf_Traceguids,
      *((unsigned int *)a1 + 78));
  TracePortId(*((_DWORD *)a1 + 78), ">>> Locking >>>");
  AcquireWriteLock(a1, (char *)a1 + 320, "ProcessPublicPortEvent", 659);
  if ( !*((_DWORD *)a1 + 109) )
  {
    v3 = ProcessPublicPortEventInternal(a1);
    if ( v3 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 35, &WPP_4b473b0d41083bd40dfc61d99b047aaf_Traceguids, v3);
    }
  }
  *((_DWORD *)a1 + 108) &= ~1u;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      36,
      &WPP_4b473b0d41083bd40dfc61d99b047aaf_Traceguids,
      *((unsigned int *)a1 + 78));
  TracePortId(*((_DWORD *)a1 + 78), "<<< Unlocking <<<");
  ReleaseWriteLock(a1, (char *)a1 + 320, "ProcessPublicPortEvent", 677);
  TracePortId(*((_DWORD *)a1 + 78), "<<< Derefing <<<");
  SecMgrDerefPortEx(a1, "ProcessPublicPortEvent", 681);
}

```

## disassembly

```asm
0x1800566c0  mov     [rsp+arg_0], rbx
0x1800566c5  mov     [rsp+arg_8], rsi
0x1800566ca  push    rdi
0x1800566cb  sub     rsp, 20h
0x1800566cf  mov     rbx, rcx
0x1800566d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800566d9  lea     rsi, WPP_GLOBAL_Control
0x1800566e0  cmp     rcx, rsi
0x1800566e3  jz      short loc_180056707
0x1800566e5  test    byte ptr [rcx+44h], 8
0x1800566e9  jz      short loc_180056707
0x1800566eb  mov     r9d, [rbx+138h]
0x1800566f2  lea     r8, WPP_4b473b0d41083bd40dfc61d99b047aaf_Traceguids
0x1800566f9  mov     rcx, [rcx+38h]
0x1800566fd  mov     edx, 22h ; '"'
0x180056702  call    WPP_SF_d
0x180056707  mov     ecx, [rbx+138h]; unsigned int
0x18005670d  lea     rdx, aLocking; ">>> Locking >>>"
0x180056714  call    ?TracePortId@@YAXKPEBD@Z; TracePortId(ulong,char const *)
0x180056719  lea     rdi, [rbx+140h]
0x180056720  mov     r9d, 293h
0x180056726  mov     rdx, rdi
0x180056729  lea     r8, aProcesspublicp; "ProcessPublicPortEvent"
0x180056730  mov     rcx, rbx
0x180056733  call    cs:__imp_AcquireWriteLock
0x18005673a  nop     dword ptr [rax+rax+00h]
0x18005673f  cmp     dword ptr [rbx+1B4h], 0
0x180056746  jnz     short loc_18005677E
0x180056748  mov     rcx, rbx; struct MSMSEC_PORT_CONTEXT *
0x18005674b  call    ?ProcessPublicPortEventInternal@@YAKPEAUMSMSEC_PORT_CONTEXT@@@Z; ProcessPublicPortEventInternal(MSMSEC_PORT_CONTEXT *)
0x180056750  test    eax, eax
0x180056752  jz      short loc_18005677E
0x180056754  mov     rcx, cs:WPP_GLOBAL_Control
0x18005675b  cmp     rcx, rsi
0x18005675e  jz      short loc_18005677E
0x180056760  test    byte ptr [rcx+44h], 1
0x180056764  jz      short loc_18005677E
0x180056766  mov     rcx, [rcx+38h]
0x18005676a  lea     r8, WPP_4b473b0d41083bd40dfc61d99b047aaf_Traceguids
0x180056771  mov     edx, 23h ; '#'
0x180056776  mov     r9d, eax
0x180056779  call    WPP_SF_d
0x18005677e  and     dword ptr [rbx+1B0h], 0FFFFFFFEh
0x180056785  mov     rcx, cs:WPP_GLOBAL_Control
0x18005678c  cmp     rcx, rsi
0x18005678f  jz      short loc_1800567B3
0x180056791  test    byte ptr [rcx+44h], 8
0x180056795  jz      short loc_1800567B3
0x180056797  mov     r9d, [rbx+138h]
0x18005679e  lea     r8, WPP_4b473b0d41083bd40dfc61d99b047aaf_Traceguids
0x1800567a5  mov     rcx, [rcx+38h]
0x1800567a9  mov     edx, 24h ; '$'
0x1800567ae  call    WPP_SF_d
0x1800567b3  mov     ecx, [rbx+138h]; unsigned int
0x1800567b9  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x1800567c0  call    ?TracePortId@@YAXKPEBD@Z; TracePortId(ulong,char const *)
0x1800567c5  mov     r9d, 2A5h
0x1800567cb  lea     r8, aProcesspublicp; "ProcessPublicPortEvent"
0x1800567d2  mov     rdx, rdi
0x1800567d5  mov     rcx, rbx
0x1800567d8  call    cs:__imp_ReleaseWriteLock
0x1800567df  nop     dword ptr [rax+rax+00h]
0x1800567e4  mov     ecx, [rbx+138h]; unsigned int
0x1800567ea  lea     rdx, aDerefing; "<<< Derefing <<<"
0x1800567f1  call    ?TracePortId@@YAXKPEBD@Z; TracePortId(ulong,char const *)
0x1800567f6  mov     r8d, 2A9h; int
0x1800567fc  lea     rdx, aProcesspublicp; "ProcessPublicPortEvent"
0x180056803  mov     rcx, rbx; struct MSMSEC_PORT_CONTEXT *
0x180056806  mov     rbx, [rsp+28h+arg_0]
0x18005680b  mov     rsi, [rsp+28h+arg_8]
0x180056810  add     rsp, 20h
0x180056814  pop     rdi
0x180056815  jmp     ?SecMgrDerefPortEx@@YAXPEAUMSMSEC_PORT_CONTEXT@@PEBDH@Z; SecMgrDerefPortEx(MSMSEC_PORT_CONTEXT *,char const *,int)
```
