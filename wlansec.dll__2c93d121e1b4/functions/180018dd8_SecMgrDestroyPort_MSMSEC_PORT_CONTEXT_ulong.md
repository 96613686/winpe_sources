# SecMgrDestroyPort(MSMSEC_PORT_CONTEXT *,ulong *)

- ea: `0x180018dd8`
- end: `0x1800190a9`
- name: `?SecMgrDestroyPort@@YAKPEAUMSMSEC_PORT_CONTEXT@@PEAK@Z`
- size: `721`
- prototype: `unsigned int __fastcall(struct MSMSEC_PORT_CONTEXT *, unsigned int *)`
- caller_count: `4`
- callee_count: `14`
- tags: ``

## callers

- `0x180005e80`
- `0x1800141d0`
- `0x180015600`
- `0x1800293ac`

## callees

- `0x18000892c`
- `0x180008998`
- `0x180013600`
- `0x180018d40`
- `0x180018dd8`
- `0x1800190b0`
- `0x180019290`
- `0x1800193cc`
- `0x1800194f0`
- `0x18001958c`
- `0x180019648`
- `0x18001ce60`
- `0x180041c10`
- `0x180055a38`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180018f50`
- `MobileNetworking!ReleaseWriteLock` at `0x180018f50`
- `MobileNetworking!AcquireWriteLock` at `0x180018e4e`
- `MobileNetworking!AcquireWriteLock` at `0x180018e4e`

## pseudocode

```c
__int64 __fastcall SecMgrDestroyPort(struct MSMSEC_PORT_CONTEXT *a1, unsigned int *a2)
{
  unsigned int v2; // esi
  unsigned int v4; // ebp
  int v6; // r8d
  int v7; // r8d
  unsigned int v8; // eax
  int v9; // r8d

  v2 = 0;
  v4 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 109, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids);
  SecMgrReleasePeerIpAddress(a1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_Ls(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, v6, *((_DWORD *)a1 + 78), (__int64)">>> Locking >>>");
  AcquireWriteLock(a1, (char *)a1 + 320, "SecMgrDestroyPort", 1369);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
    WPP_SF_LDDDDDD(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      110,
      &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids,
      *((unsigned int *)a1 + 78),
      *((unsigned __int8 *)a1 + 302),
      *((unsigned __int8 *)a1 + 303),
      *((unsigned __int8 *)a1 + 304),
      *((unsigned __int8 *)a1 + 305),
      *((unsigned __int8 *)a1 + 306),
      *((unsigned __int8 *)a1 + 307));
  if ( a2 && (unsigned int)SecMgrPSKMismatchSuspected(a1) )
    v4 = 294932;
  SecMgrPreDestroyAdhocPort(a1);
  if ( !*((_DWORD *)a1 + 109) )
  {
    CancelAllPortTimers(a1);
    FlushPortEventQueues(a1);
    v8 = CreateAndQueuePublicPortEventWithoutScheduler(a1);
    v2 = v8;
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 111, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids, v8);
    }
    else
    {
      ProcessPublicPortEventInternal(a1);
    }
    *((_DWORD *)a1 + 109) = 1;
    SecMgrClearPortParams(a1);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_Ls(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, v7, *((_DWORD *)a1 + 78), (__int64)"<<< Unlocking <<<");
  ReleaseWriteLock(a1, (char *)a1 + 320, "SecMgrDestroyPort", 1442);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_Ls(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, v9, *((_DWORD *)a1 + 78), (__int64)"<<< Derefing <<<");
  SecMgrDerefPortEx(a1, "SecMgrDestroyPort", 1446);
  if ( a2 )
    *a2 = v4;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 112, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids, v2);
  return v2;
}

```

## disassembly

```asm
0x180018dd8  push    rbx
0x180018dda  push    rbp
0x180018ddb  push    rsi
0x180018ddc  push    rdi
0x180018ddd  push    r12
0x180018ddf  push    r13
0x180018de1  push    r14
0x180018de3  push    r15
0x180018de5  sub     rsp, 58h
0x180018de9  xor     esi, esi
0x180018deb  mov     r14, rdx
0x180018dee  xor     ebp, ebp
0x180018df0  mov     rdi, rcx
0x180018df3  mov     rcx, cs:WPP_GLOBAL_Control
0x180018dfa  lea     r12, WPP_GLOBAL_Control
0x180018e01  mov     r13d, 100h
0x180018e07  cmp     rcx, r12
0x180018e0a  jz      short loc_180018E16
0x180018e0c  test    [rcx+44h], r13d
0x180018e10  jnz     loc_180018FE6
0x180018e16  mov     rcx, rdi; struct MSMSEC_PORT_CONTEXT *
0x180018e19  call    ?SecMgrReleasePeerIpAddress@@YAXPEAUMSMSEC_PORT_CONTEXT@@@Z; SecMgrReleasePeerIpAddress(MSMSEC_PORT_CONTEXT *)
0x180018e1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180018e25  cmp     rcx, r12
0x180018e28  jz      short loc_180018E34
0x180018e2a  test    [rcx+44h], r13d
0x180018e2e  jnz     loc_180019000
0x180018e34  lea     r15, [rdi+140h]
0x180018e3b  mov     r9d, 559h
0x180018e41  mov     rdx, r15
0x180018e44  lea     r8, aSecmgrdestroyp_0; "SecMgrDestroyPort"
0x180018e4b  mov     rcx, rdi
0x180018e4e  call    cs:__imp_AcquireWriteLock
0x180018e55  nop     dword ptr [rax+rax+00h]
0x180018e5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180018e61  cmp     rcx, r12
0x180018e64  jz      short loc_180018ED2
0x180018e66  test    byte ptr [rcx+44h], 2
0x180018e6a  jz      short loc_180018ED2
0x180018e6c  movzx   r8d, byte ptr [rdi+132h]
0x180018e74  mov     edx, 6Eh ; 'n'
0x180018e79  movzx   r9d, byte ptr [rdi+131h]
0x180018e81  movzx   eax, byte ptr [rdi+133h]
0x180018e88  movzx   r10d, byte ptr [rdi+130h]
0x180018e90  movzx   r11d, byte ptr [rdi+12Fh]
0x180018e98  movzx   ebx, byte ptr [rdi+12Eh]
0x180018e9f  mov     rcx, [rcx+38h]
0x180018ea3  mov     [rsp+98h+var_50], eax
0x180018ea7  mov     [rsp+98h+var_58], r8d
0x180018eac  lea     r8, WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids
0x180018eb3  mov     [rsp+98h+var_60], r9d
0x180018eb8  mov     r9d, [rdi+138h]
0x180018ebf  mov     [rsp+98h+var_68], r10d
0x180018ec4  mov     [rsp+98h+var_70], r11d
0x180018ec9  mov     dword ptr [rsp+98h+var_78], ebx
0x180018ecd  call    WPP_SF_LDDDDDD
0x180018ed2  test    r14, r14
0x180018ed5  jnz     loc_180018FAF
0x180018edb  mov     rcx, rdi; struct MSMSEC_PORT_CONTEXT *
0x180018ede  call    ?SecMgrPreDestroyAdhocPort@@YAXPEAUMSMSEC_PORT_CONTEXT@@@Z; SecMgrPreDestroyAdhocPort(MSMSEC_PORT_CONTEXT *)
0x180018ee3  cmp     [rdi+1B4h], esi
0x180018ee9  jnz     short loc_180018F27
0x180018eeb  mov     rcx, rdi; struct MSMSEC_PORT_CONTEXT *
0x180018eee  call    ?CancelAllPortTimers@@YAXPEAUMSMSEC_PORT_CONTEXT@@@Z; CancelAllPortTimers(MSMSEC_PORT_CONTEXT *)
0x180018ef3  mov     rcx, rdi; struct MSMSEC_PORT_CONTEXT *
0x180018ef6  call    ?FlushPortEventQueues@@YAXPEAUMSMSEC_PORT_CONTEXT@@@Z; FlushPortEventQueues(MSMSEC_PORT_CONTEXT *)
0x180018efb  mov     rcx, rdi
0x180018efe  call    ?CreateAndQueuePublicPortEventWithoutScheduler@@YAKPEAUMSMSEC_PORT_CONTEXT@@W4MSMSEC_PORT_EVENT_TYPE@@@Z; CreateAndQueuePublicPortEventWithoutScheduler(MSMSEC_PORT_CONTEXT *,MSMSEC_PORT_EVENT_TYPE)
0x180018f03  mov     esi, eax
0x180018f05  test    eax, eax
0x180018f07  jnz     loc_180019026
0x180018f0d  mov     rcx, rdi; struct MSMSEC_PORT_CONTEXT *
0x180018f10  call    ?ProcessPublicPortEventInternal@@YAKPEAUMSMSEC_PORT_CONTEXT@@@Z; ProcessPublicPortEventInternal(MSMSEC_PORT_CONTEXT *)
0x180018f15  mov     rcx, rdi; struct MSMSEC_PORT_CONTEXT *
0x180018f18  mov     dword ptr [rdi+1B4h], 1
0x180018f22  call    ?SecMgrClearPortParams@@YAXPEAUMSMSEC_PORT_CONTEXT@@@Z; SecMgrClearPortParams(MSMSEC_PORT_CONTEXT *)
0x180018f27  mov     rcx, cs:WPP_GLOBAL_Control
0x180018f2e  cmp     rcx, r12
0x180018f31  jz      short loc_180018F3D
0x180018f33  test    [rcx+44h], r13d
0x180018f37  jnz     loc_18001905D
0x180018f3d  mov     r9d, 5A2h
0x180018f43  lea     r8, aSecmgrdestroyp_0; "SecMgrDestroyPort"
0x180018f4a  mov     rdx, r15
0x180018f4d  mov     rcx, rdi
0x180018f50  call    cs:__imp_ReleaseWriteLock
0x180018f57  nop     dword ptr [rax+rax+00h]
0x180018f5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180018f63  cmp     rcx, r12
0x180018f66  jz      short loc_180018F72
0x180018f68  test    [rcx+44h], r13d
0x180018f6c  jnz     loc_180019083
0x180018f72  mov     r8d, 5A6h; int
0x180018f78  lea     rdx, aSecmgrdestroyp_0; "SecMgrDestroyPort"
0x180018f7f  mov     rcx, rdi; struct MSMSEC_PORT_CONTEXT *
0x180018f82  call    ?SecMgrDerefPortEx@@YAXPEAUMSMSEC_PORT_CONTEXT@@PEBDH@Z; SecMgrDerefPortEx(MSMSEC_PORT_CONTEXT *,char const *,int)
0x180018f87  test    r14, r14
0x180018f8a  jz      short loc_180018F8F
0x180018f8c  mov     [r14], ebp
0x180018f8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180018f96  cmp     rcx, r12
0x180018f99  jnz     short loc_180018FC6
0x180018f9b  mov     eax, esi
0x180018f9d  add     rsp, 58h
0x180018fa1  pop     r15
0x180018fa3  pop     r14
0x180018fa5  pop     r13
0x180018fa7  pop     r12
0x180018fa9  pop     rdi
0x180018faa  pop     rsi
0x180018fab  pop     rbp
0x180018fac  pop     rbx
0x180018fad  retn
0x180018faf  mov     rcx, rdi; struct MSMSEC_PORT_CONTEXT *
0x180018fb2  call    ?SecMgrPSKMismatchSuspected@@YAHPEAUMSMSEC_PORT_CONTEXT@@@Z; SecMgrPSKMismatchSuspected(MSMSEC_PORT_CONTEXT *)
0x180018fb7  test    eax, eax
0x180018fb9  mov     ecx, 48014h
0x180018fbe  cmovnz  ebp, ecx
0x180018fc1  jmp     loc_180018EDB
0x180018fc6  test    [rcx+44h], r13d
0x180018fca  jz      short loc_180018F9B
0x180018fcc  mov     rcx, [rcx+38h]
0x180018fd0  lea     r8, WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids
0x180018fd7  mov     edx, 70h ; 'p'
0x180018fdc  mov     r9d, esi
0x180018fdf  call    WPP_SF_d
0x180018fe4  jmp     short loc_180018F9B
0x180018fe6  mov     rcx, [rcx+38h]
0x180018fea  lea     r8, WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids
0x180018ff1  mov     edx, 6Dh ; 'm'
0x180018ff6  call    WPP_SF_
0x180018ffb  jmp     loc_180018E16
0x180019000  mov     r9d, [rdi+138h]
0x180019007  lea     rax, aLocking; ">>> Locking >>>"
0x18001900e  mov     rcx, [rcx+38h]
0x180019012  mov     edx, 0Ch
0x180019017  mov     [rsp+98h+var_78], rax
0x18001901c  call    WPP_SF_Ls
0x180019021  jmp     loc_180018E34
0x180019026  mov     rcx, cs:WPP_GLOBAL_Control
0x18001902d  cmp     rcx, r12
0x180019030  jz      loc_180018F15
0x180019036  test    byte ptr [rcx+44h], 1
0x18001903a  jz      loc_180018F15
0x180019040  mov     rcx, [rcx+38h]
0x180019044  lea     r8, WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids
0x18001904b  mov     edx, 6Fh ; 'o'
0x180019050  mov     r9d, eax
0x180019053  call    WPP_SF_d
0x180019058  jmp     loc_180018F15
0x18001905d  mov     r9d, [rdi+138h]
0x180019064  lea     rax, aUnlocking; "<<< Unlocking <<<"
0x18001906b  mov     rcx, [rcx+38h]
0x18001906f  mov     edx, 0Ch
0x180019074  mov     [rsp+98h+var_78], rax
0x180019079  call    WPP_SF_Ls
0x18001907e  jmp     loc_180018F3D
0x180019083  mov     r9d, [rdi+138h]
0x18001908a  lea     rax, aDerefing; "<<< Derefing <<<"
0x180019091  mov     rcx, [rcx+38h]
0x180019095  mov     edx, 0Ch
0x18001909a  mov     [rsp+98h+var_78], rax
0x18001909f  call    WPP_SF_Ls
0x1800190a4  jmp     loc_180018F72
```
