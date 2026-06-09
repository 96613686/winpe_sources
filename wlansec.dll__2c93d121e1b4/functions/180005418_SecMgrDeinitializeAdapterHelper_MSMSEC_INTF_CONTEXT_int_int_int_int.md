# SecMgrDeinitializeAdapterHelper(MSMSEC_INTF_CONTEXT *,int,int,int,int)

- ea: `0x180005418`
- end: `0x18000553b`
- name: `?SecMgrDeinitializeAdapterHelper@@YAXPEAUMSMSEC_INTF_CONTEXT@@HHHH@Z`
- size: `291`
- prototype: `void __fastcall(struct MSMSEC_INTF_CONTEXT *, int, int, int, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180004d44`
- `0x1800184ec`

## callees

- `0x18000367c`
- `0x1800045b8`
- `0x180005418`
- `0x180005544`
- `0x180005728`
- `0x18000892c`
- `0x180008998`
- `0x18001c8a8`

## import_xrefs

- `MobileNetworking!DeleteReadWriteLock` at `0x1800054ec`
- `MobileNetworking!DeleteReadWriteLock` at `0x1800054ec`

## pseudocode

```c
void __fastcall SecMgrDeinitializeAdapterHelper(struct MSMSEC_INTF_CONTEXT *a1, int a2, int a3, int a4, int a5)
{
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 50, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids);
  if ( a5 )
    GroupKeyDeinitialize((struct MSMSEC_INTF_CONTEXT *)((char *)a1 + 3256));
  if ( a4 )
    PreAuthDeinitialize((struct MSMSEC_INTF_CONTEXT *)((char *)a1 + 2912));
  if ( a3 )
    PmkCacheDeinitialize((struct MSMSEC_INTF_CONTEXT *)((char *)a1 + 3000));
  FreeNICCapabilities((struct MSMSEC_INTF_CONTEXT *)((char *)a1 + 2368));
  if ( a2 )
    DeleteReadWriteLock((char *)a1 + 2512);
  if ( *((_QWORD *)a1 + 348) )
    FreeMSMSecConfig((char *)a1 + 2784);
  if ( *((_QWORD *)a1 + 349) )
    FreeMSMSecConfig((char *)a1 + 2792);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 51, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids, 0);
}

```

## disassembly

```asm
0x180005418  push    rbx
0x18000541a  push    rbp
0x18000541b  push    rsi
0x18000541c  push    rdi
0x18000541d  push    r12
0x18000541f  sub     rsp, 20h
0x180005423  mov     edi, r9d
0x180005426  mov     esi, r8d
0x180005429  mov     ebp, edx
0x18000542b  mov     rbx, rcx
0x18000542e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005435  lea     r12, WPP_GLOBAL_Control
0x18000543c  cmp     rcx, r12
0x18000543f  jnz     short loc_1800054BE
0x180005441  cmp     [rsp+48h+arg_20], 0
0x180005446  jnz     short loc_1800054B0
0x180005448  test    edi, edi
0x18000544a  jnz     short loc_1800054A2
0x18000544c  test    esi, esi
0x18000544e  jz      short loc_18000545C
0x180005450  lea     rcx, [rbx+0BB8h]; struct MSMSEC_PMKCACHE_CONTEXT *
0x180005457  call    ?PmkCacheDeinitialize@@YAXPEAUMSMSEC_PMKCACHE_CONTEXT@@@Z; PmkCacheDeinitialize(MSMSEC_PMKCACHE_CONTEXT *)
0x18000545c  lea     rcx, [rbx+940h]; struct DOT11_MSMSEC_NIC_CAPABILITIES *
0x180005463  call    ?FreeNICCapabilities@@YAXAEAUDOT11_MSMSEC_NIC_CAPABILITIES@@@Z; FreeNICCapabilities(DOT11_MSMSEC_NIC_CAPABILITIES &)
0x180005468  test    ebp, ebp
0x18000546a  jnz     short loc_1800054E5
0x18000546c  lea     rcx, [rbx+0AE0h]
0x180005473  cmp     qword ptr [rcx], 0
0x180005477  jnz     loc_1800054FD
0x18000547d  lea     rcx, [rbx+0AE8h]
0x180005484  cmp     qword ptr [rcx], 0
0x180005488  jnz     short loc_180005507
0x18000548a  mov     rcx, cs:WPP_GLOBAL_Control
0x180005491  cmp     rcx, r12
0x180005494  jnz     short loc_180005511
0x180005496  add     rsp, 20h
0x18000549a  pop     r12
0x18000549c  pop     rdi
0x18000549d  pop     rsi
0x18000549e  pop     rbp
0x18000549f  pop     rbx
0x1800054a0  retn
0x1800054a2  lea     rcx, [rbx+0B60h]; struct MSMSEC_PREAUTH_CONTEXT *
0x1800054a9  call    ?PreAuthDeinitialize@@YAXPEAUMSMSEC_PREAUTH_CONTEXT@@@Z; PreAuthDeinitialize(MSMSEC_PREAUTH_CONTEXT *)
0x1800054ae  jmp     short loc_18000544C
0x1800054b0  lea     rcx, [rbx+0CB8h]; struct MSMSEC_GROUP_KEY_CONTEXT *
0x1800054b7  call    ?GroupKeyDeinitialize@@YAKPEAUMSMSEC_GROUP_KEY_CONTEXT@@@Z; GroupKeyDeinitialize(MSMSEC_GROUP_KEY_CONTEXT *)
0x1800054bc  jmp     short loc_180005448
0x1800054be  test    dword ptr [rcx+44h], 100h
0x1800054c5  jz      loc_180005441
0x1800054cb  mov     rcx, [rcx+38h]
0x1800054cf  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x1800054d6  mov     edx, 32h ; '2'
0x1800054db  call    WPP_SF_
0x1800054e0  jmp     loc_180005441
0x1800054e5  lea     rcx, [rbx+9D0h]
0x1800054ec  call    cs:__imp_DeleteReadWriteLock
0x1800054f3  nop     dword ptr [rax+rax+00h]
0x1800054f8  jmp     loc_18000546C
0x1800054fd  call    FreeMSMSecConfig
0x180005502  jmp     loc_18000547D
0x180005507  call    FreeMSMSecConfig
0x18000550c  jmp     loc_18000548A
0x180005511  test    dword ptr [rcx+44h], 100h
0x180005518  jz      loc_180005496
0x18000551e  mov     rcx, [rcx+38h]
0x180005522  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x180005529  mov     edx, 33h ; '3'
0x18000552e  xor     r9d, r9d
0x180005531  call    WPP_SF_d
0x180005536  jmp     loc_180005496
```
