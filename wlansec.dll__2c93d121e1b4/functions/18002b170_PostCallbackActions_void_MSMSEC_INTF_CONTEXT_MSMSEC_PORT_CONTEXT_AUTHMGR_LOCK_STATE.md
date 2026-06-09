# PostCallbackActions(void *,MSMSEC_INTF_CONTEXT *,MSMSEC_PORT_CONTEXT *,_AUTHMGR_LOCK_STATE *)

- ea: `0x18002b170`
- end: `0x18002b3f2`
- name: `?PostCallbackActions@@YAKPEAXPEAUMSMSEC_INTF_CONTEXT@@PEAUMSMSEC_PORT_CONTEXT@@PEAU_AUTHMGR_LOCK_STATE@@@Z`
- size: `642`
- prototype: `unsigned int(void *, struct MSMSEC_INTF_CONTEXT *, struct MSMSEC_PORT_CONTEXT *, struct _AUTHMGR_LOCK_STATE *)`
- caller_count: `12`
- callee_count: `8`
- tags: ``

## callers

- `0x180028750`
- `0x180029660`
- `0x18002a040`
- `0x18002a390`
- `0x18002a638`
- `0x18002b770`
- `0x18002be40`
- `0x180072f00`
- `0x1800733b0`
- `0x180073760`
- `0x180075140`
- `0x180075390`

## callees

- `0x18000892c`
- `0x180008998`
- `0x180013600`
- `0x180013bc0`
- `0x1800163e0`
- `0x18002b170`
- `0x18002bb08`
- `0x180055a38`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x18002b1e1`
- `MobileNetworking!ReleaseWriteLock` at `0x18002b301`
- `MobileNetworking!ReleaseWriteLock` at `0x18002b1e1`
- `MobileNetworking!ReleaseWriteLock` at `0x18002b301`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x18002b29a`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x18002b29a`

## pseudocode

```c
__int64 __fastcall PostCallbackActions(
        void *a1,
        struct MSMSEC_INTF_CONTEXT *a2,
        struct MSMSEC_PORT_CONTEXT *a3,
        struct _AUTHMGR_LOCK_STATE *a4)
{
  unsigned int v8; // edi
  PVOID *v9; // rcx
  unsigned int v10; // eax

  v8 = 0;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 16, WPP_20060763357235bdafa6f501eee46e60_Traceguids);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *(_DWORD *)a4 )
  {
    if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 17) & 0x100) != 0 )
      WPP_SF_Ls((unsigned int)v9[7], 11, (_DWORD)a3, *((_DWORD *)a2 + 624), (__int64)"<<< Unlocking <<<");
    ReleaseWriteLock(a2, (char *)a2 + 2512, "PostCallbackActions", 100);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((_DWORD *)a4 + 1) )
  {
    if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 17) & 0x100) != 0 )
      WPP_SF_Ls((unsigned int)v9[7], 11, (_DWORD)a3, *((_DWORD *)a2 + 624), (__int64)"<<< Derefing <<<");
    SecMgrDerefAdapterEx(a2, "PostCallbackActions", 104);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((_DWORD *)a4 + 2) )
  {
    TracePortId(*((_DWORD *)a3 + 78), "<<< Unlocking <<<");
    ReleaseWriteLock(a3, (char *)a3 + 320, "PostCallbackActions", 108);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((_DWORD *)a4 + 3) )
  {
    if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 17) & 0x100) != 0 )
      WPP_SF_Ls((unsigned int)v9[7], 12, (_DWORD)a3, *((_DWORD *)a3 + 78), (__int64)"<<< Derefing <<<");
    SecMgrDerefPortEx(a3, "PostCallbackActions", 112);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((_DWORD *)a4 + 4) )
  {
    DecThreadCountEx("PostCallbackActions", 116);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !*((_DWORD *)a4 + 5) )
    goto LABEL_26;
  v10 = HtDereferenceHandleWithTag(qword_1800AEFA8, a1, 2);
  v8 = v10;
  if ( !v10 )
    goto LABEL_25;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v8;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 17, WPP_20060763357235bdafa6f501eee46e60_Traceguids, v10);
LABEL_25:
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_26:
  if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 17) & 0x100) != 0 )
    WPP_SF_d(v9[7], 18, WPP_20060763357235bdafa6f501eee46e60_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x18002b170  push    rbx
0x18002b172  push    rbp
0x18002b173  push    rsi
0x18002b174  push    rdi
0x18002b175  push    r12
0x18002b177  push    r13
0x18002b179  push    r14
0x18002b17b  sub     rsp, 30h
0x18002b17f  mov     rbx, r9
0x18002b182  mov     rbp, r8
0x18002b185  mov     rsi, rdx
0x18002b188  mov     r14, rcx
0x18002b18b  xor     edi, edi
0x18002b18d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b194  lea     r12, WPP_GLOBAL_Control
0x18002b19b  mov     r13d, 100h
0x18002b1a1  cmp     rcx, r12
0x18002b1a4  jz      short loc_18002B1B0
0x18002b1a6  test    [rcx+44h], r13d
0x18002b1aa  jnz     loc_18002B319
0x18002b1b0  lea     rax, aUnlocking; "<<< Unlocking <<<"
0x18002b1b7  cmp     [rbx], edi
0x18002b1b9  jz      short loc_18002B1F4
0x18002b1bb  cmp     rcx, r12
0x18002b1be  jz      short loc_18002B1CA
0x18002b1c0  test    [rcx+44h], r13d
0x18002b1c4  jnz     loc_18002B33A
0x18002b1ca  lea     rdx, [rsi+9D0h]
0x18002b1d1  mov     r9d, 64h ; 'd'
0x18002b1d7  lea     r8, aPostcallbackac_0; "PostCallbackActions"
0x18002b1de  mov     rcx, rsi
0x18002b1e1  call    cs:__imp_ReleaseWriteLock
0x18002b1e8  nop     dword ptr [rax+rax+00h]
0x18002b1ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b1f4  lea     rax, aDerefing; "<<< Derefing <<<"
0x18002b1fb  cmp     [rbx+4], edi
0x18002b1fe  jz      short loc_18002B22B
0x18002b200  cmp     rcx, r12
0x18002b203  jz      short loc_18002B20F
0x18002b205  test    [rcx+44h], r13d
0x18002b209  jnz     loc_18002B359
0x18002b20f  mov     r8d, 68h ; 'h'; int
0x18002b215  lea     rdx, aPostcallbackac_0; "PostCallbackActions"
0x18002b21c  mov     rcx, rsi; struct MSMSEC_INTF_CONTEXT *
0x18002b21f  call    ?SecMgrDerefAdapterEx@@YAXPEAUMSMSEC_INTF_CONTEXT@@PEBDH@Z; SecMgrDerefAdapterEx(MSMSEC_INTF_CONTEXT *,char const *,int)
0x18002b224  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b22b  cmp     [rbx+8], edi
0x18002b22e  jnz     loc_18002B2D8
0x18002b234  cmp     [rbx+0Ch], edi
0x18002b237  jz      short loc_18002B264
0x18002b239  cmp     rcx, r12
0x18002b23c  jz      short loc_18002B248
0x18002b23e  test    [rcx+44h], r13d
0x18002b242  jnz     loc_18002B378
0x18002b248  mov     r8d, 70h ; 'p'; int
0x18002b24e  lea     rdx, aPostcallbackac_0; "PostCallbackActions"
0x18002b255  mov     rcx, rbp; struct MSMSEC_PORT_CONTEXT *
0x18002b258  call    ?SecMgrDerefPortEx@@YAXPEAUMSMSEC_PORT_CONTEXT@@PEBDH@Z; SecMgrDerefPortEx(MSMSEC_PORT_CONTEXT *,char const *,int)
0x18002b25d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b264  cmp     [rbx+10h], edi
0x18002b267  jz      short loc_18002B281
0x18002b269  mov     edx, 74h ; 't'; int
0x18002b26e  lea     rcx, aPostcallbackac_0; "PostCallbackActions"
0x18002b275  call    ?DecThreadCountEx@@YAXPEBDH@Z; DecThreadCountEx(char const *,int)
0x18002b27a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b281  cmp     [rbx+14h], edi
0x18002b284  jz      short loc_18002B2B7
0x18002b286  mov     rcx, cs:qword_1800AEFA8
0x18002b28d  mov     r9d, 1
0x18002b293  mov     rdx, r14
0x18002b296  lea     r8d, [r9+1]
0x18002b29a  call    cs:__imp_HtDereferenceHandleWithTag
0x18002b2a1  nop     dword ptr [rax+rax+00h]
0x18002b2a6  mov     edi, eax
0x18002b2a8  test    eax, eax
0x18002b2aa  jnz     loc_18002B39E
0x18002b2b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b2b7  cmp     rcx, r12
0x18002b2ba  jz      short loc_18002B2C6
0x18002b2bc  test    [rcx+44h], r13d
0x18002b2c0  jnz     loc_18002B3D5
0x18002b2c6  mov     eax, edi
0x18002b2c8  add     rsp, 30h
0x18002b2cc  pop     r14
0x18002b2ce  pop     r13
0x18002b2d0  pop     r12
0x18002b2d2  pop     rdi
0x18002b2d3  pop     rsi
0x18002b2d4  pop     rbp
0x18002b2d5  pop     rbx
0x18002b2d6  retn
0x18002b2d8  mov     ecx, [rbp+138h]; unsigned int
0x18002b2de  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x18002b2e5  call    ?TracePortId@@YAXKPEBD@Z; TracePortId(ulong,char const *)
0x18002b2ea  lea     rdx, [rbp+140h]
0x18002b2f1  mov     r9d, 6Ch ; 'l'
0x18002b2f7  lea     r8, aPostcallbackac_0; "PostCallbackActions"
0x18002b2fe  mov     rcx, rbp
0x18002b301  call    cs:__imp_ReleaseWriteLock
0x18002b308  nop     dword ptr [rax+rax+00h]
0x18002b30d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b314  jmp     loc_18002B234
0x18002b319  mov     rcx, [rcx+38h]
0x18002b31d  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x18002b324  mov     edx, 10h
0x18002b329  call    WPP_SF_
0x18002b32e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b335  jmp     loc_18002B1B0
0x18002b33a  mov     r9d, [rsi+9C0h]
0x18002b341  mov     edx, 0Bh
0x18002b346  mov     rcx, [rcx+38h]
0x18002b34a  mov     [rsp+68h+var_48], rax
0x18002b34f  call    WPP_SF_Ls
0x18002b354  jmp     loc_18002B1CA
0x18002b359  mov     r9d, [rsi+9C0h]
0x18002b360  mov     edx, 0Bh
0x18002b365  mov     rcx, [rcx+38h]
0x18002b369  mov     [rsp+68h+var_48], rax
0x18002b36e  call    WPP_SF_Ls
0x18002b373  jmp     loc_18002B20F
0x18002b378  mov     r9d, [rbp+138h]
0x18002b37f  lea     rax, aDerefing; "<<< Derefing <<<"
0x18002b386  mov     rcx, [rcx+38h]
0x18002b38a  mov     edx, 0Ch
0x18002b38f  mov     [rsp+68h+var_48], rax
0x18002b394  call    WPP_SF_Ls
0x18002b399  jmp     loc_18002B248
0x18002b39e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b3a5  cmp     rcx, r12
0x18002b3a8  jz      loc_18002B2C6
0x18002b3ae  test    byte ptr [rcx+44h], 1
0x18002b3b2  jz      loc_18002B2B7
0x18002b3b8  mov     rcx, [rcx+38h]
0x18002b3bc  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x18002b3c3  mov     edx, 11h
0x18002b3c8  mov     r9d, eax
0x18002b3cb  call    WPP_SF_d
0x18002b3d0  jmp     loc_18002B2B0
0x18002b3d5  mov     rcx, [rcx+38h]
0x18002b3d9  lea     r8, WPP_20060763357235bdafa6f501eee46e60_Traceguids
0x18002b3e0  mov     edx, 12h
0x18002b3e5  mov     r9d, edi
0x18002b3e8  call    WPP_SF_d
0x18002b3ed  jmp     loc_18002B2C6
```
