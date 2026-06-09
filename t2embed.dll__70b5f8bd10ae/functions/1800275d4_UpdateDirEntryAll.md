# UpdateDirEntryAll

- ea: `0x1800275d4`
- end: `0x18002769d`
- name: `UpdateDirEntryAll`
- size: `201`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180012a18`
- `0x180029228`

## callees

- `0x18000edd4`
- `0x180011640`
- `0x180013514`
- `0x180017de0`
- `0x1800275d4`
- `0x18002a590`

## pseudocode

```c
__int16 __fastcall UpdateDirEntryAll(__int64 a1, _DWORD *a2, unsigned int a3, unsigned int a4)
{
  unsigned int TTDirectory; // edi
  __int16 result; // ax
  __int16 v9; // [rsp+30h] [rbp-48h] BYREF
  __int128 v10; // [rsp+38h] [rbp-40h] BYREF

  v9 = 0;
  v10 = 0;
  if ( a3 > a4 + a3 )
    return 1000;
  if ( a4 + a3 > *(_DWORD *)(a1 + 8) )
    return 1000;
  TTDirectory = GetTTDirectory((__int64 *)a1, a2, (__int64)&v10);
  if ( !TTDirectory )
    return 1000;
  HIDWORD(v10) = a3;
  result = ZeroLongWordAlign(a1, a4, (char *)&v10 + 8);
  if ( !result )
  {
    result = CalcChecksum(a1, DWORD2(v10), HIDWORD(v10), (char *)&v10 + 4);
    if ( !result )
      return WriteGeneric(a1, (__int64)&v10, 0x10u, (unsigned __int8 *)&DIRECTORY_CONTROL, TTDirectory, &v9);
  }
  return result;
}

```

## disassembly

```asm
0x1800275d4  push    rbx
0x1800275d6  push    rbp
0x1800275d7  push    rsi
0x1800275d8  push    rdi
0x1800275d9  push    r14
0x1800275db  sub     rsp, 50h
0x1800275df  mov     rax, cs:__security_cookie
0x1800275e6  xor     rax, rsp
0x1800275e9  mov     [rsp+78h+var_30], rax
0x1800275ee  xor     ebp, ebp
0x1800275f0  lea     eax, [r9+r8]
0x1800275f4  mov     [rsp+78h+var_48], bp
0x1800275f9  xorps   xmm0, xmm0
0x1800275fc  mov     r14d, r9d
0x1800275ff  mov     esi, r8d
0x180027602  mov     rbx, rcx
0x180027605  movups  [rsp+78h+var_40], xmm0
0x18002760a  cmp     r8d, eax
0x18002760d  ja      short loc_180027680
0x18002760f  cmp     eax, [rcx+8]
0x180027612  ja      short loc_180027680
0x180027614  lea     r8, [rsp+78h+var_40]
0x180027619  call    GetTTDirectory
0x18002761e  mov     edi, eax
0x180027620  test    eax, eax
0x180027622  jz      short loc_180027680
0x180027624  lea     r8, [rsp+78h+var_40+8]
0x180027629  mov     dword ptr [rsp+78h+var_40+0Ch], esi
0x18002762d  mov     edx, r14d
0x180027630  mov     rcx, rbx
0x180027633  call    ZeroLongWordAlign
0x180027638  test    ax, ax
0x18002763b  jnz     short loc_180027685
0x18002763d  mov     r8d, dword ptr [rsp+78h+var_40+0Ch]
0x180027642  lea     r9, [rsp+78h+var_40+4]
0x180027647  mov     edx, dword ptr [rsp+78h+var_40+8]
0x18002764b  mov     rcx, rbx
0x18002764e  call    CalcChecksum
0x180027653  test    ax, ax
0x180027656  jnz     short loc_180027685
0x180027658  lea     rax, [rsp+78h+var_48]
0x18002765d  mov     rcx, rbx
0x180027660  mov     [rsp+78h+var_50], rax
0x180027665  lea     r8d, [rbp+10h]
0x180027669  lea     r9, DIRECTORY_CONTROL
0x180027670  mov     [rsp+78h+var_58], edi
0x180027674  lea     rdx, [rsp+78h+var_40]
0x180027679  call    WriteGeneric
0x18002767e  jmp     short loc_180027685
0x180027680  mov     eax, 3E8h
0x180027685  mov     rcx, [rsp+78h+var_30]
0x18002768a  xor     rcx, rsp; StackCookie
0x18002768d  call    __security_check_cookie
0x180027692  add     rsp, 50h
0x180027696  pop     r14
0x180027698  pop     rdi
0x180027699  pop     rsi
0x18002769a  pop     rbp
0x18002769b  pop     rbx
0x18002769c  retn
```
