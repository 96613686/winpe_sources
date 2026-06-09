# SecMgrDestroyPortInternal(MSMSEC_PORT_CONTEXT * *)

- ea: `0x180013950`
- end: `0x180013bba`
- name: `?SecMgrDestroyPortInternal@@YAXPEAPEAUMSMSEC_PORT_CONTEXT@@@Z`
- size: `618`
- prototype: `void __fastcall(struct MSMSEC_PORT_CONTEXT **)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180013600`

## callees

- `0x18000892c`
- `0x180008998`
- `0x18000e620`
- `0x180013950`
- `0x1800169c0`
- `0x180018d40`
- `0x18001c9ac`
- `0x18002bb08`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180013a3d`
- `MobileNetworking!ReleaseWriteLock` at `0x180013a85`
- `MobileNetworking!ReleaseWriteLock` at `0x180013a3d`
- `MobileNetworking!ReleaseWriteLock` at `0x180013a85`
- `MobileNetworking!AcquireWriteLock` at `0x1800139a0`
- `MobileNetworking!AcquireWriteLock` at `0x1800139f0`
- `MobileNetworking!AcquireWriteLock` at `0x1800139a0`
- `MobileNetworking!AcquireWriteLock` at `0x1800139f0`

## pseudocode

```c
void __fastcall SecMgrDestroyPortInternal(struct MSMSEC_PORT_CONTEXT **a1)
{
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 119, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids);
  TracePortId(*((_DWORD *)*a1 + 78), ">>> Locking >>>");
  AcquireWriteLock(*a1, (char *)*a1 + 320, "SecMgrDestroyPortInternal", 1574);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
    WPP_SF_LDDDDDD(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      120,
      &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids,
      *((unsigned int *)*a1 + 78),
      *((unsigned __int8 *)*a1 + 302),
      *((unsigned __int8 *)*a1 + 303),
      *((unsigned __int8 *)*a1 + 304),
      *((unsigned __int8 *)*a1 + 305),
      *((unsigned __int8 *)*a1 + 306),
      *((unsigned __int8 *)*a1 + 307));
  TraceAdapterId(*(_DWORD *)(*((_QWORD *)*a1 + 3) + 2496LL), ">>> Locking >>>");
  AcquireWriteLock(*((_QWORD *)*a1 + 3), *((_QWORD *)*a1 + 3) + 2512LL, "SecMgrDestroyPortInternal", 1592);
  --*(_DWORD *)(*((_QWORD *)*a1 + 3) + 2656LL);
  TraceAdapterId(*(_DWORD *)(*((_QWORD *)*a1 + 3) + 2496LL), "<<< Unlocking <<<");
  ReleaseWriteLock(*((_QWORD *)*a1 + 3), *((_QWORD *)*a1 + 3) + 2512LL, "SecMgrDestroyPortInternal", 1594);
  if ( *((_DWORD *)*a1 + 110) != 1
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 121, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids);
  }
  TracePortId(*((_DWORD *)*a1 + 78), "<<< Unlocking <<<");
  ReleaseWriteLock(*a1, (char *)*a1 + 320, "SecMgrDestroyPortInternal", 1602);
  SecMgrDeinitializePort(*a1);
  FreeMSMSecMemory(a1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 122, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids, 0);
}

```

## disassembly

```asm
0x180013950  push    rbx
0x180013952  push    rsi
0x180013953  push    rdi
0x180013954  push    r14
0x180013956  sub     rsp, 58h
0x18001395a  mov     rsi, rcx
0x18001395d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013964  lea     r14, WPP_GLOBAL_Control
0x18001396b  cmp     rcx, r14
0x18001396e  jnz     loc_180013ABC
0x180013974  mov     rcx, [rsi]
0x180013977  lea     rdx, aLocking; ">>> Locking >>>"
0x18001397e  mov     ecx, [rcx+138h]; unsigned int
0x180013984  call    ?TracePortId@@YAXKPEBD@Z; TracePortId(ulong,char const *)
0x180013989  mov     rcx, [rsi]
0x18001398c  lea     r8, aSecmgrdestroyp; "SecMgrDestroyPortInternal"
0x180013993  mov     r9d, 626h
0x180013999  lea     rdx, [rcx+140h]
0x1800139a0  call    cs:__imp_AcquireWriteLock
0x1800139a7  nop     dword ptr [rax+rax+00h]
0x1800139ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800139b3  cmp     rcx, r14
0x1800139b6  jnz     loc_180013AE3
0x1800139bc  mov     rax, [rsi]
0x1800139bf  lea     rdx, aLocking; ">>> Locking >>>"
0x1800139c6  mov     rcx, [rax+18h]
0x1800139ca  mov     ecx, [rcx+9C0h]; unsigned int
0x1800139d0  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x1800139d5  mov     rax, [rsi]
0x1800139d8  lea     r8, aSecmgrdestroyp; "SecMgrDestroyPortInternal"
0x1800139df  mov     r9d, 638h
0x1800139e5  mov     rcx, [rax+18h]
0x1800139e9  lea     rdx, [rcx+9D0h]
0x1800139f0  call    cs:__imp_AcquireWriteLock
0x1800139f7  nop     dword ptr [rax+rax+00h]
0x1800139fc  mov     rax, [rsi]
0x1800139ff  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180013a06  mov     rcx, [rax+18h]
0x180013a0a  dec     dword ptr [rcx+0A60h]
0x180013a10  mov     rax, [rsi]
0x180013a13  mov     rcx, [rax+18h]
0x180013a17  mov     ecx, [rcx+9C0h]; unsigned int
0x180013a1d  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180013a22  mov     rax, [rsi]
0x180013a25  lea     r8, aSecmgrdestroyp; "SecMgrDestroyPortInternal"
0x180013a2c  mov     r9d, 63Ah
0x180013a32  mov     rcx, [rax+18h]
0x180013a36  lea     rdx, [rcx+9D0h]
0x180013a3d  call    cs:__imp_ReleaseWriteLock
0x180013a44  nop     dword ptr [rax+rax+00h]
0x180013a49  mov     rax, [rsi]
0x180013a4c  cmp     dword ptr [rax+1B8h], 1
0x180013a53  jnz     loc_180013B5C
0x180013a59  mov     rcx, [rsi]
0x180013a5c  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180013a63  mov     ecx, [rcx+138h]; unsigned int
0x180013a69  call    ?TracePortId@@YAXKPEBD@Z; TracePortId(ulong,char const *)
0x180013a6e  mov     rcx, [rsi]
0x180013a71  lea     r8, aSecmgrdestroyp; "SecMgrDestroyPortInternal"
0x180013a78  mov     r9d, 642h
0x180013a7e  lea     rdx, [rcx+140h]
0x180013a85  call    cs:__imp_ReleaseWriteLock
0x180013a8c  nop     dword ptr [rax+rax+00h]
0x180013a91  mov     rcx, [rsi]; struct MSMSEC_PORT_CONTEXT *
0x180013a94  call    ?SecMgrDeinitializePort@@YAXPEAUMSMSEC_PORT_CONTEXT@@@Z; SecMgrDeinitializePort(MSMSEC_PORT_CONTEXT *)
0x180013a99  mov     rcx, rsi
0x180013a9c  call    FreeMSMSecMemory
0x180013aa1  mov     rcx, cs:WPP_GLOBAL_Control
0x180013aa8  cmp     rcx, r14
0x180013aab  jnz     loc_180013B90
0x180013ab1  add     rsp, 58h
0x180013ab5  pop     r14
0x180013ab7  pop     rdi
0x180013ab8  pop     rsi
0x180013ab9  pop     rbx
0x180013aba  retn
0x180013abc  test    dword ptr [rcx+44h], 100h
0x180013ac3  jz      loc_180013974
0x180013ac9  mov     rcx, [rcx+38h]
0x180013acd  lea     r8, WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids
0x180013ad4  mov     edx, 77h ; 'w'
0x180013ad9  call    WPP_SF_
0x180013ade  jmp     loc_180013974
0x180013ae3  test    byte ptr [rcx+44h], 2
0x180013ae7  jz      loc_1800139BC
0x180013aed  mov     r9, [rsi]
0x180013af0  mov     edx, 78h ; 'x'
0x180013af5  mov     rcx, [rcx+38h]
0x180013af9  movzx   r8d, byte ptr [r9+132h]
0x180013b01  movzx   eax, byte ptr [r9+133h]
0x180013b09  movzx   r10d, byte ptr [r9+131h]
0x180013b11  movzx   r11d, byte ptr [r9+130h]
0x180013b19  movzx   ebx, byte ptr [r9+12Fh]
0x180013b21  movzx   edi, byte ptr [r9+12Eh]
0x180013b29  mov     r9d, [r9+138h]
0x180013b30  mov     [rsp+78h+var_30], eax
0x180013b34  mov     [rsp+78h+var_38], r8d
0x180013b39  lea     r8, WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids
0x180013b40  mov     [rsp+78h+var_40], r10d
0x180013b45  mov     [rsp+78h+var_48], r11d
0x180013b4a  mov     [rsp+78h+var_50], ebx
0x180013b4e  mov     [rsp+78h+var_58], edi
0x180013b52  call    WPP_SF_LDDDDDD
0x180013b57  jmp     loc_1800139BC
0x180013b5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180013b63  cmp     rcx, r14
0x180013b66  jz      loc_180013A59
0x180013b6c  test    byte ptr [rcx+44h], 1
0x180013b70  jz      loc_180013A59
0x180013b76  mov     rcx, [rcx+38h]
0x180013b7a  lea     r8, WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids
0x180013b81  mov     edx, 79h ; 'y'
0x180013b86  call    WPP_SF_
0x180013b8b  jmp     loc_180013A59
0x180013b90  test    dword ptr [rcx+44h], 100h
0x180013b97  jz      loc_180013AB1
0x180013b9d  mov     rcx, [rcx+38h]
0x180013ba1  lea     r8, WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids
0x180013ba8  mov     edx, 7Ah ; 'z'
0x180013bad  xor     r9d, r9d
0x180013bb0  call    WPP_SF_d
0x180013bb5  jmp     loc_180013AB1
```
