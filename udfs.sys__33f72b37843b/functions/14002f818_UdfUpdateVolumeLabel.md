# UdfUpdateVolumeLabel

- ea: `0x14002f818`
- end: `0x14002f932`
- name: `UdfUpdateVolumeLabel`
- size: `282`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x140003148`
- `0x140049f80`

## callees

- `0x14000a7f8`
- `0x14000cad4`
- `0x140011c30`
- `0x14001bd80`
- `0x14002f818`
- `0x1400544a0`
- `0x140054d70`

## pseudocode

```c
void *__fastcall UdfUpdateVolumeLabel(int a1, void *a2, _WORD *a3, __int64 a4)
{
  int v4; // ebx
  int v8; // ecx
  int v9; // r9d
  __int16 v10; // bx
  void *result; // rax
  __int64 v12; // [rsp+30h] [rbp-38h] BYREF
  void *Src; // [rsp+38h] [rbp-30h]

  v4 = a4;
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x800) != 0 )
  {
    WPP_SF_qqD(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      125,
      WPP_808b98bda8443bb0d475e79494837b3d_Traceguids,
      a2,
      a4,
      128);
  }
  LOBYTE(a4) = 0x80;
  if ( (unsigned __int8)UdfCheckLegalCS0Dstring(a1, v4, 0, a4, 1) )
  {
    v12 = 0x400000;
    LOBYTE(v9) = 0x80;
    Src = a2;
    UdfConvertCS0DstringToUnicode(v8, v4, 0, v9, (__int64)&v12);
    v10 = v12;
    result = memmove(a2, Src, (unsigned __int16)v12);
    *a3 = v10;
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x800) != 0 )
    {
      return (void *)WPP_SF_Z(
                       *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
                       126,
                       WPP_808b98bda8443bb0d475e79494837b3d_Traceguids,
                       &v12);
    }
  }
  else
  {
    result = 0;
    *a3 = 0;
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x800) != 0 )
    {
      return (void *)WPP_SF_(
                       *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
                       127,
                       WPP_808b98bda8443bb0d475e79494837b3d_Traceguids);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14002f818  push    rbx
0x14002f81a  push    rbp
0x14002f81b  push    rsi
0x14002f81c  push    rdi
0x14002f81d  push    r12
0x14002f81f  sub     rsp, 40h
0x14002f823  mov     rbx, r9
0x14002f826  mov     rsi, r8
0x14002f829  mov     rdi, rdx
0x14002f82c  mov     rbp, rcx
0x14002f82f  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f836  lea     r12, WPP_GLOBAL_Control
0x14002f83d  cmp     rcx, r12
0x14002f840  jz      short loc_14002F870
0x14002f842  test    dword ptr [rcx+2Ch], 800h
0x14002f849  jz      short loc_14002F870
0x14002f84b  mov     rcx, [rcx+18h]
0x14002f84f  lea     r8, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids
0x14002f856  mov     edx, 7Dh ; '}'
0x14002f85b  mov     [rsp+68h+var_40], 80h
0x14002f863  mov     r9, rdi
0x14002f866  mov     [rsp+68h+var_48], rbx
0x14002f86b  call    WPP_SF_qqD
0x14002f870  mov     r9b, 80h
0x14002f873  mov     byte ptr [rsp+68h+var_48], 1
0x14002f878  xor     r8d, r8d
0x14002f87b  mov     rdx, rbx
0x14002f87e  mov     rcx, rbp
0x14002f881  call    UdfCheckLegalCS0Dstring
0x14002f886  test    al, al
0x14002f888  jz      short loc_14002F8F9
0x14002f88a  lea     rax, [rsp+68h+var_38]
0x14002f88f  mov     [rsp+68h+var_38], 400000h
0x14002f898  mov     r9b, 80h
0x14002f89b  mov     [rsp+68h+var_48], rax
0x14002f8a0  xor     r8d, r8d
0x14002f8a3  mov     [rsp+68h+Src], rdi
0x14002f8a8  mov     rdx, rbx
0x14002f8ab  call    UdfConvertCS0DstringToUnicode
0x14002f8b0  movzx   ebx, word ptr [rsp+68h+var_38]
0x14002f8b5  mov     rcx, rdi; void *
0x14002f8b8  mov     rdx, [rsp+68h+Src]; Src
0x14002f8bd  mov     r8d, ebx; Size
0x14002f8c0  call    memmove
0x14002f8c5  mov     [rsi], bx
0x14002f8c8  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f8cf  cmp     rcx, r12
0x14002f8d2  jz      short loc_14002F926
0x14002f8d4  test    dword ptr [rcx+2Ch], 800h
0x14002f8db  jz      short loc_14002F926
0x14002f8dd  mov     rcx, [rcx+18h]
0x14002f8e1  lea     r9, [rsp+68h+var_38]
0x14002f8e6  mov     edx, 7Eh ; '~'
0x14002f8eb  lea     r8, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids
0x14002f8f2  call    WPP_SF_Z
0x14002f8f7  jmp     short loc_14002F926
0x14002f8f9  xor     eax, eax
0x14002f8fb  mov     [rsi], ax
0x14002f8fe  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f905  cmp     rcx, r12
0x14002f908  jz      short loc_14002F926
0x14002f90a  test    dword ptr [rcx+2Ch], 800h
0x14002f911  jz      short loc_14002F926
0x14002f913  mov     rcx, [rcx+18h]
0x14002f917  lea     edx, [rax+7Fh]
0x14002f91a  lea     r8, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids
0x14002f921  call    WPP_SF_
0x14002f926  add     rsp, 40h
0x14002f92a  pop     r12
0x14002f92c  pop     rdi
0x14002f92d  pop     rsi
0x14002f92e  pop     rbp
0x14002f92f  pop     rbx
0x14002f930  retn
```
