# CUwfConfiguration::UpdateMultiSzValue(CUwfRegKey &,ushort const *,_MULTISZ * const,bool)

- ea: `0x18000a240`
- end: `0x18000a3a6`
- name: `?UpdateMultiSzValue@CUwfConfiguration@@QEAAJAEAVCUwfRegKey@@PEBGQEAU_MULTISZ@@_N@Z`
- size: `358`
- prototype: `__int64 __fastcall(CUwfConfiguration *this, HKEY *, const unsigned __int16 *, const BYTE **, bool)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18000cd30`

## callees

- `0x180001384`
- `0x1800079a0`
- `0x18000a240`
- `0x18000e4d0`
- `0x180011a30`
- `0x18001afd6`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000a32d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000a38f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000a32d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000a38f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a284`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a300`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a284`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a300`

## pseudocode

```c
__int64 __fastcall CUwfConfiguration::UpdateMultiSzValue(
        CUwfConfiguration *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        const BYTE **a4,
        bool a5)
{
  __int64 v5; // rsi
  LSTATUS ValueW; // eax
  int v11; // ebx
  void *pvData; // rdi
  bool v13; // cc
  DWORD pcbData; // [rsp+40h] [rbp-48h] BYREF
  DWORD pdwType[17]; // [rsp+44h] [rbp-44h] BYREF

  v5 = 0;
  pdwType[0] = 0;
  pcbData = 0;
  ValueW = RegGetValueW(*a2, 0, a3, 0x20u, pdwType, 0, &pcbData);
  v11 = ValueW;
  if ( ValueW )
  {
    pvData = 0;
    v13 = ValueW <= 0;
LABEL_3:
    if ( !v13 )
      v11 = (unsigned __int16)ValueW | 0x80070000;
    goto LABEL_10;
  }
  pvData = operator new[](saturated_mul((unsigned __int64)pcbData >> 1, 2u));
  if ( !pvData )
  {
    v11 = -2147024882;
    goto LABEL_10;
  }
  ValueW = RegGetValueW(*a2, 0, a3, 0x20u, pdwType, pvData, &pcbData);
  v11 = ValueW;
  v13 = ValueW <= 0;
  if ( ValueW )
    goto LABEL_3;
  v5 = MultiSzAlloc(pvData);
  v11 = -2147024882;
  if ( v5 )
    v11 = 0;
LABEL_10:
  operator delete[](pvData);
  if ( (int)(v11 + 0x80000000) < 0 || v11 == -2147024894 )
  {
    if ( v11 == -2147024894 || memcmp_0(*(const void **)v5, *a4, *(unsigned int *)(v5 + 8)) )
    {
      if ( !a5 || (v11 = CUwfConfiguration::FixupUpdatedSettings(this), v11 >= 0) )
        v11 = CUwfRegKey::SetMultiSzValue(a2, a3, a4);
    }
    else
    {
      v11 = 1;
    }
  }
  operator delete[]((void *)v5);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000a240  mov     r11, rsp
0x18000a243  push    rbx
0x18000a244  push    rbp
0x18000a245  push    rsi
0x18000a246  push    rdi
0x18000a247  push    r12
0x18000a249  push    r14
0x18000a24b  push    r15
0x18000a24d  sub     rsp, 50h
0x18000a251  xor     esi, esi
0x18000a253  lea     rax, [r11-48h]
0x18000a257  mov     [r11-58h], rax
0x18000a25b  mov     r15, rdx
0x18000a25e  mov     r14, r9
0x18000a261  mov     [r11-60h], rsi
0x18000a265  mov     r12, rcx
0x18000a268  mov     [rsp+88h+var_44], esi
0x18000a26c  lea     rax, [r11-44h]
0x18000a270  mov     [rsp+88h+var_48], esi
0x18000a274  mov     rcx, [r15]; hkey
0x18000a277  lea     r9d, [rsi+20h]; dwFlags
0x18000a27b  xor     edx, edx; lpSubKey
0x18000a27d  mov     [r11-68h], rax
0x18000a281  mov     rbp, r8
0x18000a284  call    cs:__imp_RegGetValueW
0x18000a28a  mov     ebx, eax
0x18000a28c  test    eax, eax
0x18000a28e  jz      short loc_18000A2A8
0x18000a290  xor     edi, edi
0x18000a292  test    eax, eax
0x18000a294  jle     loc_18000A32A
0x18000a29a  movzx   ebx, ax
0x18000a29d  or      ebx, 80070000h
0x18000a2a3  jmp     loc_18000A32A
0x18000a2a8  mov     ecx, [rsp+88h+var_48]
0x18000a2ac  mov     eax, 2
0x18000a2b1  shr     rcx, 1
0x18000a2b4  mul     rcx
0x18000a2b7  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000a2be  cmovb   rax, rcx
0x18000a2c2  mov     rcx, rax; unsigned __int64
0x18000a2c5  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000a2ca  mov     rdi, rax
0x18000a2cd  test    rax, rax
0x18000a2d0  jnz     short loc_18000A2D9
0x18000a2d2  mov     ebx, 8007000Eh
0x18000a2d7  jmp     short loc_18000A32A
0x18000a2d9  mov     rcx, [r15]; hkey
0x18000a2dc  lea     rax, [rsp+88h+var_48]
0x18000a2e1  mov     [rsp+88h+pcbData], rax; pcbData
0x18000a2e6  mov     r9d, 20h ; ' '; dwFlags
0x18000a2ec  lea     rax, [rsp+88h+var_44]
0x18000a2f1  mov     [rsp+88h+pvData], rdi; pvData
0x18000a2f6  mov     r8, rbp; lpValue
0x18000a2f9  mov     [rsp+88h+pdwType], rax; pdwType
0x18000a2fe  xor     edx, edx; lpSubKey
0x18000a300  call    cs:__imp_RegGetValueW
0x18000a306  mov     ebx, eax
0x18000a308  test    eax, eax
0x18000a30a  jnz     short loc_18000A294
0x18000a30c  mov     edx, [rsp+88h+var_48]
0x18000a310  mov     rcx, rdi; Src
0x18000a313  shr     edx, 1
0x18000a315  call    MultiSzAlloc
0x18000a31a  mov     rsi, rax
0x18000a31d  mov     ebx, 8007000Eh
0x18000a322  xor     eax, eax
0x18000a324  test    rsi, rsi
0x18000a327  cmovnz  ebx, eax
0x18000a32a  mov     rcx, rdi
0x18000a32d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000a333  mov     ecx, 80000000h
0x18000a338  mov     edx, 80070002h
0x18000a33d  lea     eax, [rbx+rcx]
0x18000a340  test    ecx, eax
0x18000a342  jnz     short loc_18000A348
0x18000a344  cmp     ebx, edx
0x18000a346  jnz     short loc_18000A38C
0x18000a348  cmp     ebx, edx
0x18000a34a  jz      short loc_18000A364
0x18000a34c  mov     r8d, [rsi+8]; Size
0x18000a350  mov     rdx, [r14]; Buf2
0x18000a353  mov     rcx, [rsi]; Buf1
0x18000a356  call    memcmp_0
0x18000a35b  test    eax, eax
0x18000a35d  jnz     short loc_18000A364
0x18000a35f  lea     ebx, [rax+1]
0x18000a362  jmp     short loc_18000A38C
0x18000a364  cmp     [rsp+88h+arg_20], 0
0x18000a36c  jz      short loc_18000A37C
0x18000a36e  mov     rcx, r12; this
0x18000a371  call    ?FixupUpdatedSettings@CUwfConfiguration@@QEAAJXZ; CUwfConfiguration::FixupUpdatedSettings(void)
0x18000a376  mov     ebx, eax
0x18000a378  test    eax, eax
0x18000a37a  js      short loc_18000A38C
0x18000a37c  mov     r8, r14; struct _MULTISZ *
0x18000a37f  mov     rdx, rbp; unsigned __int16 *
0x18000a382  mov     rcx, r15; this
0x18000a385  call    ?SetMultiSzValue@CUwfRegKey@@QEAAJPEBGQEAU_MULTISZ@@@Z; CUwfRegKey::SetMultiSzValue(ushort const *,_MULTISZ * const)
0x18000a38a  mov     ebx, eax
0x18000a38c  mov     rcx, rsi
0x18000a38f  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000a395  mov     eax, ebx
0x18000a397  add     rsp, 50h
0x18000a39b  pop     r15
0x18000a39d  pop     r14
0x18000a39f  pop     r12
0x18000a3a1  pop     rdi
0x18000a3a2  pop     rsi
0x18000a3a3  pop     rbp
0x18000a3a4  pop     rbx
0x18000a3a5  retn
```
