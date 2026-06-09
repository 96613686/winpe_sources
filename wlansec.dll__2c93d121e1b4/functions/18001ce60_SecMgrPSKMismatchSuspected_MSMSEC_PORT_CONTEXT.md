# SecMgrPSKMismatchSuspected(MSMSEC_PORT_CONTEXT *)

- ea: `0x18001ce60`
- end: `0x18001cffc`
- name: `?SecMgrPSKMismatchSuspected@@YAHPEAUMSMSEC_PORT_CONTEXT@@@Z`
- size: `412`
- prototype: `__int64 __fastcall(struct MSMSEC_PORT_CONTEXT *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180018dd8`
- `0x18001ccb0`

## callees

- `0x18000892c`
- `0x18001ce60`
- `0x18001d004`
- `0x180055a38`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x18001cf10`
- `MobileNetworking!ReleaseWriteLock` at `0x18001cf10`
- `MobileNetworking!AcquireWriteLock` at `0x18001cead`
- `MobileNetworking!AcquireWriteLock` at `0x18001cead`

## pseudocode

```c
__int64 __fastcall SecMgrPSKMismatchSuspected(struct MSMSEC_PORT_CONTEXT *a1, __int64 a2, int a3)
{
  int v4; // r8d
  unsigned int v5; // edi
  int v6; // esi
  PVOID *v7; // rcx
  int v9; // [rsp+60h] [rbp+8h] BYREF

  v9 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_Ls(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      11,
      a3,
      *(_DWORD *)(*((_QWORD *)a1 + 3) + 2496LL),
      (__int64)">>> Locking >>>");
  AcquireWriteLock(*((_QWORD *)a1 + 3), *((_QWORD *)a1 + 3) + 2512LL, "SecMgrPSKMismatchSuspected", 2206);
  v5 = 1;
  if ( (unsigned int)MSMSecProfileIsPSKKeyNeeded(*(_QWORD *)(*((_QWORD *)a1 + 3) + 2784LL), &v9) )
  {
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 178, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids);
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
    v6 = 0;
  }
  else
  {
    v6 = v9;
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 17) & 0x100) != 0 )
    WPP_SF_Ls((unsigned int)v7[7], 11, v4, *(_DWORD *)(*((_QWORD *)a1 + 3) + 2496LL), (__int64)"<<< Unlocking <<<");
  ReleaseWriteLock(*((_QWORD *)a1 + 3), *((_QWORD *)a1 + 3) + 2512LL, "SecMgrPSKMismatchSuspected", 2217);
  if ( v6 && (*((_DWORD *)a1 + 257) || *((_DWORD *)a1 + 172) >= 2u && !*((_DWORD *)a1 + 175)) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 179, &WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids);
  }
  else
  {
    return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x18001ce60  push    rbx
0x18001ce62  push    rsi
0x18001ce63  push    rdi
0x18001ce64  push    r14
0x18001ce66  sub     rsp, 38h
0x18001ce6a  mov     rbx, rcx
0x18001ce6d  mov     [rsp+58h+arg_0], 0
0x18001ce75  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ce7c  lea     r14, WPP_GLOBAL_Control
0x18001ce83  cmp     rcx, r14
0x18001ce86  jz      short loc_18001CE95
0x18001ce88  test    dword ptr [rcx+44h], 100h
0x18001ce8f  jnz     loc_18001CF73
0x18001ce95  mov     rcx, [rbx+18h]
0x18001ce99  lea     r8, aSecmgrpskmisma; "SecMgrPSKMismatchSuspected"
0x18001cea0  mov     r9d, 89Eh
0x18001cea6  lea     rdx, [rcx+9D0h]
0x18001cead  call    cs:__imp_AcquireWriteLock
0x18001ceb4  nop     dword ptr [rax+rax+00h]
0x18001ceb9  mov     rcx, [rbx+18h]
0x18001cebd  lea     rdx, [rsp+58h+arg_0]
0x18001cec2  mov     rcx, [rcx+0AE0h]
0x18001cec9  call    MSMSecProfileIsPSKKeyNeeded
0x18001cece  mov     edi, 1
0x18001ced3  test    eax, eax
0x18001ced5  jnz     loc_18001CF9D
0x18001cedb  mov     esi, [rsp+58h+arg_0]
0x18001cedf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cee6  cmp     rcx, r14
0x18001cee9  jz      short loc_18001CEF8
0x18001ceeb  test    dword ptr [rcx+44h], 100h
0x18001cef2  jnz     loc_18001CFD2
0x18001cef8  mov     rcx, [rbx+18h]
0x18001cefc  lea     r8, aSecmgrpskmisma; "SecMgrPSKMismatchSuspected"
0x18001cf03  mov     r9d, 8A9h
0x18001cf09  lea     rdx, [rcx+9D0h]
0x18001cf10  call    cs:__imp_ReleaseWriteLock
0x18001cf17  nop     dword ptr [rax+rax+00h]
0x18001cf1c  test    esi, esi
0x18001cf1e  jz      short loc_18001CF32
0x18001cf20  cmp     dword ptr [rbx+404h], 0
0x18001cf27  jnz     short loc_18001CF4A
0x18001cf29  cmp     dword ptr [rbx+2B0h], 2
0x18001cf30  jnb     short loc_18001CF41
0x18001cf32  xor     edi, edi
0x18001cf34  mov     eax, edi
0x18001cf36  add     rsp, 38h
0x18001cf3a  pop     r14
0x18001cf3c  pop     rdi
0x18001cf3d  pop     rsi
0x18001cf3e  pop     rbx
0x18001cf3f  retn
0x18001cf41  cmp     dword ptr [rbx+2BCh], 0
0x18001cf48  jnz     short loc_18001CF32
0x18001cf4a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cf51  cmp     rcx, r14
0x18001cf54  jz      short loc_18001CF34
0x18001cf56  test    [rcx+44h], dil
0x18001cf5a  jz      short loc_18001CF34
0x18001cf5c  mov     rcx, [rcx+38h]
0x18001cf60  lea     r8, WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids
0x18001cf67  mov     edx, 0B3h
0x18001cf6c  call    WPP_SF_
0x18001cf71  jmp     short loc_18001CF34
0x18001cf73  mov     r9, [rbx+18h]
0x18001cf77  lea     rax, aLocking; ">>> Locking >>>"
0x18001cf7e  mov     rcx, [rcx+38h]
0x18001cf82  mov     edx, 0Bh
0x18001cf87  mov     [rsp+58h+var_38], rax
0x18001cf8c  mov     r9d, [r9+9C0h]
0x18001cf93  call    WPP_SF_Ls
0x18001cf98  jmp     loc_18001CE95
0x18001cf9d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cfa4  cmp     rcx, r14
0x18001cfa7  jz      short loc_18001CFCB
0x18001cfa9  test    [rcx+44h], dil
0x18001cfad  jz      short loc_18001CFCB
0x18001cfaf  mov     rcx, [rcx+38h]
0x18001cfb3  lea     r8, WPP_a2450a132fbd3209f27e739a44aefecd_Traceguids
0x18001cfba  mov     edx, 0B2h
0x18001cfbf  call    WPP_SF_
0x18001cfc4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cfcb  xor     esi, esi
0x18001cfcd  jmp     loc_18001CEE6
0x18001cfd2  mov     r9, [rbx+18h]
0x18001cfd6  lea     rax, aUnlocking; "<<< Unlocking <<<"
0x18001cfdd  mov     rcx, [rcx+38h]
0x18001cfe1  mov     edx, 0Bh
0x18001cfe6  mov     [rsp+58h+var_38], rax
0x18001cfeb  mov     r9d, [r9+9C0h]
0x18001cff2  call    WPP_SF_Ls
0x18001cff7  jmp     loc_18001CEF8
```
