# WimCbMountVolume

- ea: `0x140026df0`
- end: `0x140026ef1`
- name: `WimCbMountVolume`
- size: `257`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x14000fb90`
- `0x14000fce4`
- `0x140026df0`
- `0x14002d3d4`

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
0x140026df0  mov     r11, rsp
0x140026df3  mov     [r11+8], rbx
0x140026df7  push    rdi
0x140026df8  sub     rsp, 40h
0x140026dfc  mov     eax, cs:dword_14001A2FC
0x140026e02  mov     rdi, rcx
0x140026e05  mov     [r11-18h], rcx
0x140026e09  sub     rdi, rax
0x140026e0c  lea     rcx, [r11-18h]
0x140026e10  mov     qword ptr [r11-10h], 0
0x140026e18  call    WimFSFInitializeVolume
0x140026e1d  mov     ebx, dword ptr [rsp+48h+var_10]
0x140026e21  test    ebx, ebx
0x140026e23  js      short loc_140026E48
0x140026e25  mov     rcx, cs:WPP_GLOBAL_Control
0x140026e2c  mov     eax, [rcx+2Ch]
0x140026e2f  test    al, 8
0x140026e31  jz      loc_140026EE3
0x140026e37  cmp     byte ptr [rcx+29h], 4
0x140026e3b  jb      loc_140026EE3
0x140026e41  mov     edx, 15h
0x140026e46  jmp     short loc_140026E81
0x140026e48  cmp     ebx, 0C0000034h
0x140026e4e  jz      short loc_140026EB2
0x140026e50  cmp     ebx, 0C000003Ah
0x140026e56  jz      short loc_140026EB2
0x140026e58  cmp     ebx, 0C0000102h
0x140026e5e  jz      short loc_140026EB2
0x140026e60  cmp     ebx, 0C000000Fh
0x140026e66  jnz     short loc_140026E97
0x140026e68  mov     rcx, cs:WPP_GLOBAL_Control
0x140026e6f  mov     eax, [rcx+2Ch]
0x140026e72  test    al, 8
0x140026e74  jz      short loc_140026EE3
0x140026e76  cmp     byte ptr [rcx+29h], 5
0x140026e7a  jb      short loc_140026EE3
0x140026e7c  mov     edx, 17h
0x140026e81  mov     rcx, [rcx+18h]
0x140026e85  lea     r9, [rdi+40h]
0x140026e89  lea     r8, WPP_ea753fa6f9d83b7566c7b1a5ff90ffd6_Traceguids
0x140026e90  call    WPP_SF_Z
0x140026e95  jmp     short loc_140026EE3
0x140026e97  mov     rcx, cs:WPP_GLOBAL_Control
0x140026e9e  mov     eax, [rcx+2Ch]
0x140026ea1  test    al, 8
0x140026ea3  jz      short loc_140026EE3
0x140026ea5  cmp     byte ptr [rcx+29h], 2
0x140026ea9  jb      short loc_140026EE3
0x140026eab  mov     edx, 18h
0x140026eb0  jmp     short loc_140026ECB
0x140026eb2  mov     rcx, cs:WPP_GLOBAL_Control
0x140026eb9  mov     eax, [rcx+2Ch]
0x140026ebc  test    al, 8
0x140026ebe  jz      short loc_140026EE3
0x140026ec0  cmp     byte ptr [rcx+29h], 2
0x140026ec4  jb      short loc_140026EE3
0x140026ec6  mov     edx, 16h
0x140026ecb  mov     rcx, [rcx+18h]
0x140026ecf  lea     r9, [rdi+40h]
0x140026ed3  lea     r8, WPP_ea753fa6f9d83b7566c7b1a5ff90ffd6_Traceguids
0x140026eda  mov     [rsp+48h+var_28], ebx
0x140026ede  call    WPP_SF_Zd
0x140026ee3  mov     eax, ebx
0x140026ee5  mov     rbx, [rsp+48h+arg_0]
0x140026eea  add     rsp, 40h
0x140026eee  pop     rdi
0x140026eef  retn
```
