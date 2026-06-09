# SecMgrLockAndCheckPortActive(MSMSEC_PORT_CONTEXT *)

- ea: `0x18002b3f8`
- end: `0x18002b57d`
- name: `?SecMgrLockAndCheckPortActive@@YAKPEAUMSMSEC_PORT_CONTEXT@@@Z`
- size: `389`
- prototype: `unsigned int __fastcall(struct MSMSEC_PORT_CONTEXT *)`
- caller_count: `10`
- callee_count: `5`
- tags: ``

## callers

- `0x180012df0`
- `0x180014d24`
- `0x180017cf0`
- `0x18002a638`
- `0x180053c30`
- `0x1800540d0`
- `0x180056ea4`
- `0x180057390`
- `0x180057930`
- `0x180057b18`

## callees

- `0x18000892c`
- `0x180008998`
- `0x18002b3f8`
- `0x18002bb08`
- `0x180055a38`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x18002b56c`
- `MobileNetworking!ReleaseWriteLock` at `0x18002b56c`
- `MobileNetworking!AcquireWriteLock` at `0x18002b45b`
- `MobileNetworking!AcquireWriteLock` at `0x18002b45b`

## pseudocode

```c
__int64 __fastcall SecMgrLockAndCheckPortActive(struct MSMSEC_PORT_CONTEXT *a1, __int64 a2, int a3)
{
  PVOID *v4; // rcx
  unsigned int v5; // ebx

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 45, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v5 = 0;
  if ( a1 )
  {
    if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 17) & 0x100) != 0 )
      WPP_SF_Ls((unsigned int)v4[7], 12, a3, *((_DWORD *)a1 + 78), (__int64)">>> Locking >>>");
    AcquireWriteLock(a1, (char *)a1 + 320, "SecMgrLockAndCheckPortActive", 492);
    if ( *((_DWORD *)a1 + 109) )
    {
      v5 = 6;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 47, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids);
      TracePortId(*((_DWORD *)a1 + 78), "<<< Unlocking <<<");
      ReleaseWriteLock(a1, (char *)a1 + 320, "SecMgrLockAndCheckPortActive", 506);
    }
    goto LABEL_9;
  }
  v5 = 87;
  if ( v4 == &WPP_GLOBAL_Control )
    return v5;
  if ( (*((_BYTE *)v4 + 68) & 1) != 0 )
  {
    WPP_SF_(v4[7], 46, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids);
LABEL_9:
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 17) & 0x100) != 0 )
    WPP_SF_d(v4[7], 48, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x18002b3f8  push    rbx
0x18002b3fa  push    rbp
0x18002b3fb  push    rsi
0x18002b3fc  push    rdi
0x18002b3fd  sub     rsp, 38h
0x18002b401  mov     rdi, rcx
0x18002b404  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b40b  lea     rbp, WPP_GLOBAL_Control
0x18002b412  cmp     rcx, rbp
0x18002b415  jz      short loc_18002B424
0x18002b417  test    dword ptr [rcx+44h], 100h
0x18002b41e  jnz     loc_18002B4AE
0x18002b424  xor     ebx, ebx
0x18002b426  test    rdi, rdi
0x18002b429  jz      loc_18002B4CF
0x18002b42f  cmp     rcx, rbp
0x18002b432  jz      short loc_18002B441
0x18002b434  test    dword ptr [rcx+44h], 100h
0x18002b43b  jnz     loc_18002B4F7
0x18002b441  lea     rsi, [rdi+140h]
0x18002b448  mov     r9d, 1ECh
0x18002b44e  mov     rdx, rsi
0x18002b451  lea     r8, aSecmgrlockandc_0; "SecMgrLockAndCheckPortActive"
0x18002b458  mov     rcx, rdi
0x18002b45b  call    cs:__imp_AcquireWriteLock
0x18002b462  nop     dword ptr [rax+rax+00h]
0x18002b467  cmp     [rdi+1B4h], ebx
0x18002b46d  jnz     loc_18002B51D
0x18002b473  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b47a  cmp     rcx, rbp
0x18002b47d  jnz     short loc_18002B48B
0x18002b47f  mov     eax, ebx
0x18002b481  add     rsp, 38h
0x18002b485  pop     rdi
0x18002b486  pop     rsi
0x18002b487  pop     rbp
0x18002b488  pop     rbx
0x18002b489  retn
0x18002b48b  test    dword ptr [rcx+44h], 100h
0x18002b492  jz      short loc_18002B47F
0x18002b494  mov     rcx, [rcx+38h]
0x18002b498  lea     r8, WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids
0x18002b49f  mov     edx, 30h ; '0'
0x18002b4a4  mov     r9d, ebx
0x18002b4a7  call    WPP_SF_d
0x18002b4ac  jmp     short loc_18002B47F
0x18002b4ae  mov     rcx, [rcx+38h]
0x18002b4b2  lea     r8, WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids
0x18002b4b9  mov     edx, 2Dh ; '-'
0x18002b4be  call    WPP_SF_
0x18002b4c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b4ca  jmp     loc_18002B424
0x18002b4cf  mov     ebx, 57h ; 'W'
0x18002b4d4  cmp     rcx, rbp
0x18002b4d7  jz      short loc_18002B47F
0x18002b4d9  test    byte ptr [rcx+44h], 1
0x18002b4dd  jz      short loc_18002B47A
0x18002b4df  mov     rcx, [rcx+38h]
0x18002b4e3  lea     edx, [rbx-29h]
0x18002b4e6  lea     r8, WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids
0x18002b4ed  call    WPP_SF_
0x18002b4f2  jmp     loc_18002B473
0x18002b4f7  mov     r9d, [rdi+138h]
0x18002b4fe  lea     rax, aLocking; ">>> Locking >>>"
0x18002b505  mov     rcx, [rcx+38h]
0x18002b509  mov     edx, 0Ch
0x18002b50e  mov     [rsp+58h+var_38], rax
0x18002b513  call    WPP_SF_Ls
0x18002b518  jmp     loc_18002B441
0x18002b51d  mov     ebx, 6
0x18002b522  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b529  cmp     rcx, rbp
0x18002b52c  jz      short loc_18002B547
0x18002b52e  test    byte ptr [rcx+44h], 1
0x18002b532  jz      short loc_18002B547
0x18002b534  mov     rcx, [rcx+38h]
0x18002b538  lea     edx, [rbx+29h]
0x18002b53b  lea     r8, WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids
0x18002b542  call    WPP_SF_
0x18002b547  mov     ecx, [rdi+138h]; unsigned int
0x18002b54d  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x18002b554  call    ?TracePortId@@YAXKPEBD@Z; TracePortId(ulong,char const *)
0x18002b559  mov     r9d, 1FAh
0x18002b55f  lea     r8, aSecmgrlockandc_0; "SecMgrLockAndCheckPortActive"
0x18002b566  mov     rdx, rsi
0x18002b569  mov     rcx, rdi
0x18002b56c  call    cs:__imp_ReleaseWriteLock
0x18002b573  nop     dword ptr [rax+rax+00h]
0x18002b578  jmp     loc_18002B473
```
