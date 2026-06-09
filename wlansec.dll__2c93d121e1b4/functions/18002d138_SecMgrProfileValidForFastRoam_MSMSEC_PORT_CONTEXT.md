# SecMgrProfileValidForFastRoam(MSMSEC_PORT_CONTEXT *)

- ea: `0x18002d138`
- end: `0x18002d253`
- name: `?SecMgrProfileValidForFastRoam@@YAHPEAUMSMSEC_PORT_CONTEXT@@@Z`
- size: `283`
- prototype: `__int64 __fastcall(struct MSMSEC_PORT_CONTEXT *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18002cb8c`
- `0x18003e1e4`

## callees

- `0x18002d138`
- `0x180055a38`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x18002d1cd`
- `MobileNetworking!ReleaseWriteLock` at `0x18002d1cd`
- `MobileNetworking!AcquireWriteLock` at `0x18002d183`
- `MobileNetworking!AcquireWriteLock` at `0x18002d183`

## pseudocode

```c
_BOOL8 __fastcall SecMgrProfileValidForFastRoam(struct MSMSEC_PORT_CONTEXT *a1, __int64 a2, int a3)
{
  int v4; // r8d
  __int64 v5; // r9
  unsigned int v6; // edi
  int v7; // eax
  _BOOL8 result; // rax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_Ls(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      11,
      a3,
      *(_DWORD *)(*((_QWORD *)a1 + 3) + 2496LL),
      (__int64)">>> Locking >>>");
  AcquireWriteLock(*((_QWORD *)a1 + 3), *((_QWORD *)a1 + 3) + 2512LL, "SecMgrProfileValidForFastRoam", 29);
  v5 = *((_QWORD *)a1 + 3);
  v6 = **(_DWORD **)(*(_QWORD *)(v5 + 2784) + 24LL);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_Ls(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, v4, *(_DWORD *)(v5 + 2496), (__int64)"<<< Unlocking <<<");
  ReleaseWriteLock(*((_QWORD *)a1 + 3), *((_QWORD *)a1 + 3) + 2512LL, "SecMgrProfileValidForFastRoam", 36);
  result = 0;
  if ( v6 <= 0xB )
  {
    v7 = 2368;
    if ( _bittest(&v7, v6) )
      return 1;
  }
  return result;
}

```

## disassembly

```asm
0x18002d138  mov     [rsp+arg_0], rbx
0x18002d13d  mov     [rsp+arg_8], rdi
0x18002d142  push    r14
0x18002d144  sub     rsp, 30h
0x18002d148  mov     rbx, rcx
0x18002d14b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d152  lea     r14, WPP_GLOBAL_Control
0x18002d159  cmp     rcx, r14
0x18002d15c  jz      short loc_18002D16B
0x18002d15e  test    dword ptr [rcx+44h], 100h
0x18002d165  jnz     loc_18002D203
0x18002d16b  mov     rcx, [rbx+18h]
0x18002d16f  lea     r8, aSecmgrprofilev; "SecMgrProfileValidForFastRoam"
0x18002d176  mov     r9d, 1Dh
0x18002d17c  lea     rdx, [rcx+9D0h]
0x18002d183  call    cs:__imp_AcquireWriteLock
0x18002d18a  nop     dword ptr [rax+rax+00h]
0x18002d18f  mov     r9, [rbx+18h]
0x18002d193  mov     rax, [r9+0AE0h]
0x18002d19a  mov     rcx, [rax+18h]
0x18002d19e  mov     edi, [rcx]
0x18002d1a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d1a7  cmp     rcx, r14
0x18002d1aa  jz      short loc_18002D1B5
0x18002d1ac  test    dword ptr [rcx+44h], 100h
0x18002d1b3  jnz     short loc_18002D22D
0x18002d1b5  mov     rcx, [rbx+18h]
0x18002d1b9  lea     r8, aSecmgrprofilev; "SecMgrProfileValidForFastRoam"
0x18002d1c0  mov     r9d, 24h ; '$'
0x18002d1c6  lea     rdx, [rcx+9D0h]
0x18002d1cd  call    cs:__imp_ReleaseWriteLock
0x18002d1d4  nop     dword ptr [rax+rax+00h]
0x18002d1d9  cmp     edi, 0Bh
0x18002d1dc  ja      short loc_18002D1EF
0x18002d1de  mov     eax, 940h
0x18002d1e3  bt      eax, edi
0x18002d1e6  jnb     short loc_18002D1EF
0x18002d1e8  mov     eax, 1
0x18002d1ed  jmp     short loc_18002D1F1
0x18002d1ef  xor     eax, eax
0x18002d1f1  mov     rbx, [rsp+38h+arg_0]
0x18002d1f6  mov     rdi, [rsp+38h+arg_8]
0x18002d1fb  add     rsp, 30h
0x18002d1ff  pop     r14
0x18002d201  retn
0x18002d203  mov     r9, [rbx+18h]
0x18002d207  lea     rax, aLocking; ">>> Locking >>>"
0x18002d20e  mov     rcx, [rcx+38h]
0x18002d212  mov     edx, 0Bh
0x18002d217  mov     [rsp+38h+var_18], rax
0x18002d21c  mov     r9d, [r9+9C0h]
0x18002d223  call    WPP_SF_Ls
0x18002d228  jmp     loc_18002D16B
0x18002d22d  mov     r9d, [r9+9C0h]
0x18002d234  lea     rax, aUnlocking; "<<< Unlocking <<<"
0x18002d23b  mov     rcx, [rcx+38h]
0x18002d23f  mov     edx, 0Bh
0x18002d244  mov     [rsp+38h+var_18], rax
0x18002d249  call    WPP_SF_Ls
0x18002d24e  jmp     loc_18002D1B5
```
