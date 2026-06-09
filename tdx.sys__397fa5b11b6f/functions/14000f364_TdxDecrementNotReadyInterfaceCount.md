# TdxDecrementNotReadyInterfaceCount

- ea: `0x14000f364`
- end: `0x14000f42f`
- name: `TdxDecrementNotReadyInterfaceCount`
- size: `203`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000cfc0`
- `0x14000db08`
- `0x14000e368`
- `0x14000f0fc`
- `0x140010998`
- `0x140011820`
- `0x140014c84`

## callees

- `0x14000f364`
- `0x140012fd0`
- `0x14001521c`

## import_xrefs

- `TDI!TdiProviderReady` at `0x14000f3de`
- `TDI!TdiProviderReady` at `0x14000f3de`

## string_xrefs

- `0x14000f409`: `TdxDecrementNotReadyInterfaceCount`

## pseudocode

```c
char __fastcall TdxDecrementNotReadyInterfaceCount(unsigned int a1, __int64 a2, __int64 a3)
{
  char v3; // bl

  v3 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
  {
    WPP_SF_ddd(WPP_GLOBAL_Control->AttachedDevice, 11, a3, a1, qword_14001E508, WPP_MAIN_CB.ActiveThreadCount);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)&WPP_MAIN_CB.ActiveThreadCount, 0xFFFFFFFF) == 1
    && !_InterlockedCompareExchange((volatile signed __int32 *)&qword_14001E508, 1, 0) )
  {
    v3 = 1;
    TdiProviderReady(TdxTdiProviderHandle);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    {
      WPP_SF_s(
        WPP_GLOBAL_Control->AttachedDevice,
        12,
        WPP_97be8db14fc035ddabf5f66f78f15bd4_Traceguids,
        "TdxDecrementNotReadyInterfaceCount");
    }
  }
  return v3;
}

```

## disassembly

```asm
0x14000f364  mov     [rsp+arg_0], rbx
0x14000f369  push    rsi
0x14000f36a  sub     rsp, 30h
0x14000f36e  mov     r9d, ecx
0x14000f371  xor     bl, bl
0x14000f373  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f37a  lea     rsi, WPP_GLOBAL_Control
0x14000f381  cmp     rcx, rsi
0x14000f384  jz      short loc_14000F3B7
0x14000f386  cmp     byte ptr [rcx+29h], 3
0x14000f38a  jb      short loc_14000F3B7
0x14000f38c  test    dword ptr [rcx+2Ch], 200h
0x14000f393  jz      short loc_14000F3B7
0x14000f395  mov     eax, cs:WPP_MAIN_CB.ActiveThreadCount
0x14000f39b  mov     edx, 0Bh
0x14000f3a0  mov     rcx, [rcx+18h]
0x14000f3a4  mov     [rsp+38h+var_10], eax
0x14000f3a8  mov     eax, dword ptr cs:qword_14001E508
0x14000f3ae  mov     [rsp+38h+var_18], eax
0x14000f3b2  call    WPP_SF_ddd
0x14000f3b7  or      eax, 0FFFFFFFFh
0x14000f3ba  lock xadd cs:WPP_MAIN_CB.ActiveThreadCount, eax
0x14000f3c2  cmp     eax, 1
0x14000f3c5  jnz     short loc_14000F421
0x14000f3c7  mov     ecx, eax
0x14000f3c9  xor     eax, eax
0x14000f3cb  lock cmpxchg dword ptr cs:qword_14001E508, ecx
0x14000f3d3  jnz     short loc_14000F421
0x14000f3d5  mov     bl, cl
0x14000f3d7  mov     rcx, cs:TdxTdiProviderHandle; ProviderHandle
0x14000f3de  call    cs:__imp_TdiProviderReady
0x14000f3e5  nop     dword ptr [rax+rax+00h]
0x14000f3ea  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f3f1  cmp     rcx, rsi
0x14000f3f4  jz      short loc_14000F421
0x14000f3f6  cmp     byte ptr [rcx+29h], 3
0x14000f3fa  jb      short loc_14000F421
0x14000f3fc  test    dword ptr [rcx+2Ch], 200h
0x14000f403  jz      short loc_14000F421
0x14000f405  mov     rcx, [rcx+18h]
0x14000f409  lea     r9, aTdxdecrementno; "TdxDecrementNotReadyInterfaceCount"
0x14000f410  mov     edx, 0Ch
0x14000f415  lea     r8, WPP_97be8db14fc035ddabf5f66f78f15bd4_Traceguids
0x14000f41c  call    WPP_SF_s
0x14000f421  mov     al, bl
0x14000f423  mov     rbx, [rsp+38h+arg_0]
0x14000f428  add     rsp, 30h
0x14000f42c  pop     rsi
0x14000f42d  retn
```
