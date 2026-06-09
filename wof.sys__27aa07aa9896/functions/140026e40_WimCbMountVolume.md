# WimCbMountVolume

- ea: `0x140026e40`
- end: `0x140026f41`
- name: `WimCbMountVolume`
- size: `257`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x14000fb90`
- `0x14000fce4`
- `0x140026e40`
- `0x14002d424`

## pseudocode

```c
__int64 __fastcall WimCbMountVolume(__int64 a1)
{
  __int64 v1; // rdi
  unsigned int v2; // ebx
  PDEVICE_OBJECT v3; // rcx
  __int64 v4; // rdx
  PDEVICE_OBJECT v5; // rcx
  int v6; // edx
  __int64 v8; // [rsp+30h] [rbp-18h] BYREF
  __int64 v9; // [rsp+38h] [rbp-10h]

  v8 = a1;
  v1 = a1 - (unsigned int)dword_14001A2FC;
  v9 = 0;
  WimFSFInitializeVolume(&v8);
  v2 = v9;
  if ( (int)v9 >= 0 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      v4 = 21;
LABEL_12:
      WPP_SF_Z(v3->AttachedDevice, v4, WPP_ea753fa6f9d83b7566c7b1a5ff90ffd6_Traceguids, v1 + 64);
      return v2;
    }
    return v2;
  }
  if ( (_DWORD)v9 == -1073741772 || (_DWORD)v9 == -1073741766 || (_DWORD)v9 == -1073741566 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      return v2;
    v6 = 22;
LABEL_19:
    WPP_SF_Zd(v5->AttachedDevice, v6, (unsigned int)WPP_ea753fa6f9d83b7566c7b1a5ff90ffd6_Traceguids, v1 + 64, v9);
    return v2;
  }
  if ( (_DWORD)v9 != -1073741809 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      return v2;
    v6 = 24;
    goto LABEL_19;
  }
  v3 = WPP_GLOBAL_Control;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    v4 = 23;
    goto LABEL_12;
  }
  return v2;
}

```

## disassembly

```asm
0x140026e40  mov     r11, rsp
0x140026e43  mov     [r11+8], rbx
0x140026e47  push    rdi
0x140026e48  sub     rsp, 40h
0x140026e4c  mov     eax, cs:dword_14001A2FC
0x140026e52  mov     rdi, rcx
0x140026e55  mov     [r11-18h], rcx
0x140026e59  sub     rdi, rax
0x140026e5c  lea     rcx, [r11-18h]
0x140026e60  mov     qword ptr [r11-10h], 0
0x140026e68  call    WimFSFInitializeVolume
0x140026e6d  mov     ebx, dword ptr [rsp+48h+var_10]
0x140026e71  test    ebx, ebx
0x140026e73  js      short loc_140026E98
0x140026e75  mov     rcx, cs:WPP_GLOBAL_Control
0x140026e7c  mov     eax, [rcx+2Ch]
0x140026e7f  test    al, 8
0x140026e81  jz      loc_140026F33
0x140026e87  cmp     byte ptr [rcx+29h], 4
0x140026e8b  jb      loc_140026F33
0x140026e91  mov     edx, 15h
0x140026e96  jmp     short loc_140026ED1
0x140026e98  cmp     ebx, 0C0000034h
0x140026e9e  jz      short loc_140026F02
0x140026ea0  cmp     ebx, 0C000003Ah
0x140026ea6  jz      short loc_140026F02
0x140026ea8  cmp     ebx, 0C0000102h
0x140026eae  jz      short loc_140026F02
0x140026eb0  cmp     ebx, 0C000000Fh
0x140026eb6  jnz     short loc_140026EE7
0x140026eb8  mov     rcx, cs:WPP_GLOBAL_Control
0x140026ebf  mov     eax, [rcx+2Ch]
0x140026ec2  test    al, 8
0x140026ec4  jz      short loc_140026F33
0x140026ec6  cmp     byte ptr [rcx+29h], 5
0x140026eca  jb      short loc_140026F33
0x140026ecc  mov     edx, 17h
0x140026ed1  mov     rcx, [rcx+18h]
0x140026ed5  lea     r9, [rdi+40h]
0x140026ed9  lea     r8, WPP_ea753fa6f9d83b7566c7b1a5ff90ffd6_Traceguids
0x140026ee0  call    WPP_SF_Z
0x140026ee5  jmp     short loc_140026F33
0x140026ee7  mov     rcx, cs:WPP_GLOBAL_Control
0x140026eee  mov     eax, [rcx+2Ch]
0x140026ef1  test    al, 8
0x140026ef3  jz      short loc_140026F33
0x140026ef5  cmp     byte ptr [rcx+29h], 2
0x140026ef9  jb      short loc_140026F33
0x140026efb  mov     edx, 18h
0x140026f00  jmp     short loc_140026F1B
0x140026f02  mov     rcx, cs:WPP_GLOBAL_Control
0x140026f09  mov     eax, [rcx+2Ch]
0x140026f0c  test    al, 8
0x140026f0e  jz      short loc_140026F33
0x140026f10  cmp     byte ptr [rcx+29h], 2
0x140026f14  jb      short loc_140026F33
0x140026f16  mov     edx, 16h
0x140026f1b  mov     rcx, [rcx+18h]
0x140026f1f  lea     r9, [rdi+40h]
0x140026f23  lea     r8, WPP_ea753fa6f9d83b7566c7b1a5ff90ffd6_Traceguids
0x140026f2a  mov     [rsp+48h+var_28], ebx
0x140026f2e  call    WPP_SF_Zd
0x140026f33  mov     eax, ebx
0x140026f35  mov     rbx, [rsp+48h+arg_0]
0x140026f3a  add     rsp, 40h
0x140026f3e  pop     rdi
0x140026f3f  retn
```
